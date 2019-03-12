# Plugin and extension systems

The main motivation stems from letting users extend your product. It helps keeping the core smaller and maintainable and
you could use plugins to create a community around your product if you allow sharing of them.

## Discussion

**Would it be nice, to allow asynchronous instantiation of plugins?**

My impression was that you wouldn't be able to use the (synchronous) CLI and in user code this leads to some
boilerplate. Two things were mentioned:

1. Is that a feature that really should be supported if you know already that it's possible to do?
2. You can have the hooks be asynchronous, so if the plugin is not done instantiation until the first hook is called, it
   could just wait for the promise to finish.

**How to handle dependencies between plugins?**

Code them side-effect-free. This is not always possible and it's hard to solve at all, especially if some kind of
transformation is involved. It would be a good idea to have a look at the `eslint fix` functionality or how babel solves
that problem.

**Possibility to run plugin hooks in parallel?**

Yes, you can have async hooks and you can pass that info over when registering your hook. Also if you want to say that
plugins may run in parallel or need to be run asynchronous but sequentially could be told there.

**Security issues? Untrusted code? In Web: Use of iframes sufficient?**

Workers or iframes would isolate untrusted code. This comes with a performance penalty, so you might want to check what
your level of trust should be for your product. Depends on the user. For best security, you should not only isolate the
code, but make sure to have it in separate processes. Whitelisting usually does not work as there are always some
escapes.

**Possibility to have a system that you can hook in your tool to provide plugin/extension functionality?**

Webpack open sourced their plugin system: It's called [Tapable](https://github.com/webpack/tapable) and can be used in
other projects as well.
