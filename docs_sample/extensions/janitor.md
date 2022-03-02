# Janitor

## Custom cleanup methods

Other garbage collection implementations such as Maid don't give you a choice with how you clean up objects. You can either give a function, a connection, an Instance, or a table with a Destroy method. Janitor allows you to specify how you clean up objects, so you can cancel a Tween when the Janitor is cleaned up.

## Promise Support

Janitor supports adding Promises to it natively, which will then cancel if the Janitor is cleaned up. This makes Janitor the only library of its kind with support for this implementation of Promises.

## Instances linking

Janitor's LinkToInstance method allows you to cleanup the Janitor when a linked Instance is destroyed. This allows you to execute behavior on destruction as well as cleanup objects quickly.

## Links

- [Site](https://howmanysmall.github.io/Janitor/)
- [Github](https://github.com/howmanysmall/Janitor)
- [DevForum](https://devforum.community/t/janitor-a-better-garbage-collection-solution/338)
