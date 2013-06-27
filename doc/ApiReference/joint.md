# Joint

Joint abstract class.
A Joint represents a node in the hierarchy.

## API

### on()
`public method` _on(event, fn, [context])_

Adds a listener for an upcast or broadcast event.
Duplicate listeners for the same event will be discarded.

**Parameters**   
event:String - The event name.   
fn:Function - The handler.   
context:Object (optional) - The context to be used to call the handler, defaults to the joint instance.

**Returns**   
Joint - The instance itself to allow chaining.

### once()
`public method` _once(event, fn, [context])_

Adds a one time listener for an upcast or broadcast event.
Duplicate listeners for the same event will be discarded.

**Parameters**   
event:String - The event name.   
fn:Function - The handler.   
context:Object (optional) - The context to be used to call the handler, defaults to the joint instance.

**Returns**   
Joint - The instance itself to allow chaining.

### off()
`public method` _off(event, fn, [context])_

Removes a previously added listener.

**Parameters**   
event:String - The event name.   
fn:Function - The handler.   
context:Object (optional) - The context passed to the on() method.

**Returns**   
Joint - The instance itself to allow chaining.

### destroy()
`public method` _destroy()_

Destroys the instance, releasing all of its resources.
Note that all downlinks will also be destroyed.

### _link()
`protected method` __link(joint)_

Creates a link between this joint and another one.

**Parameters**   
joint:Joint - Another joint to link to this one.

**Returns**   
Joint - The joint passed in as the argument.

### _unlink()
`protected method` __unlink(joint)_

Removes a previously created link between a joint and another one.

**Parameters**   
joint:Joint - Another joint to link to this one.

**Returns**   
Joint - The instance itself to allow chaining.

### _upcast()
`protected method` __upcast(event, [args])_

Fires an event upwards the chain.

**Parameters**   
event:String - The event name.   
args:...mixed (optional) - The arguments to pass along with the event.

**Returns**   
Joint - The instance itself to allow chaining.

### _broadcast()
`protected method` __broadcast(event, [args])_

Fires an event to all the joints.

**Parameters**   
event:String - The event name.   
args:...mixed (optional) - The arguments to pass along with the event.

**Returns**   
Joint - The instance itself to allow chaining.

### _onDestroy()
`protected method` __onDestroy()_

Method called after calling destroy().
Subclasses should override this method to release additional resources.   
The default implementation will also destroy any linked joints.