# Atlassian plugin system

by [Chris Darroch](https://twitter.com/chrisdarroch/)

Atlassian has 4000+ Apps in the marketplace, making it quite successful even if the API has limitations.

- APIs

  - first version in 2004
  - v2 2008
  - "Connect" 2014
  - all APIs are still available / in production

- Limitations

  - We are behind a firewall
  - We don't host the environment
  - We can't guarantee HTTPS
  - We can't guarantee environment support (node version, ...)
  - We support multiple environment dependencies (>240 characters in URLs may be problematic due to some)
  - We don't control all source for all features.

- Using GraphQL might cause problems for API stability / versioning...

- Apps are in-process

- Front end plugin primitives: web-fragments (outputs HTML fragments) and web-resources (bundles of assets)
- Web resources format is like a chunk. Having dependencies in the web-resource XML metadata might make you have to
  declare your dependencies twice. Once in XML, once in your JavaScript. It is to keep the files you need in
  co-location.
- There is a small wrapper around `require` to load all files necessary for a plugin. That kind of bundling has to be
  maintained by Atlassian.

## Technical lessons learned

- Always have explicit dependencies for everything. Having jQuery there implicitly, it's hard to get it out again. Also
  everything that is a side-effect, have it as a dependency.
- Care about when code runs.
- Limit the scope that plugin code can affect.
- Care about what you expose to plugins. (www.hyrumslaw.com)
- Share at build-time, not runtime. Manifest file should not be manually edited (it would be nice to have for )
- Hope for good code; plan for bad code. You have to struck a balance between limiting it and flexibility.
- Developers want to be lazy. Embrace and enable that. Having perfect security will cause performance issues
