- Registry
    - Register model
        - Allow endpoints other than git?
        - Allow easy unregister
        - Possible ways to get rid of shim repos
          - https://github.com/twitter/bower/issues/172#issuecomment-13017880
          - https://github.com/twitter/bower/issues/198
          - But then.. how would versions be handled here?? different versions might have changed the deps
    - Publish model
- Commands
    - Bower script x
         - post-install (only useful for moving files around)
         - pre-publish
         - etc
    - bower test
    - bower install & update
        - Ability to target specific commits and not only versions
            - But then, how would a version be guessed from it?!
            - It would be ok project wise, but if used within a reusable package, it must have a version!
        - Option to install deps in a tree structure like npm? see: https://github.com/twitter/bower/issues/157
        - Print a tree like npm with the deps
        - Allow overrides of the registry for easier fork integration? this need to be discussed as part of the spec, see: https://github.com/twitter/bower/issues/342
- Contributing.md
  - Copy from master
  - Tell users to learn about promises
  - Tell users to not forget to call .done() to throw unhandled promise errors in tests

- Add command to clear internal runtime cache (to be used programmatically on long running programs using bower)
- Use yeomen insight!!
- Bower could setup a git hook on folders that are github repos to make validation of the json (if it conforms with the spec)
- In prod dont forget to Q.longStackJumpLimit = 0;
- Ddd perf tests
  - http://trace.gl
- Discuss ability to specify folders inside bower_components.. e.g. components/fonts/
- Discuss namespaces in the registry
- Cache dir location: https://github.com/bower/bower/issues/448
- Implement shrinkwrap?
- Switch everything related with fs. to .graceful-fs??
  - ifo so. don't forget to do the same on all bower org modules

Not BC changes:
- shorthand_resolver -> shorthandResolver
- shorthand resolver syntax {{{}}} to just {{}}
- "latest" targets are no longer supported, they might conflict with branches or tags
- remove json property from the config