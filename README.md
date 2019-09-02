### octolinker
---
https://github.com/OctoLinker/OctoLinker

```js
// packages/core/__tests__/load-plugins.test.js

import assert from 'assert';
import * as loadPlugins from '../load-plugins.js';

describe('load-plugins', () => {
  it('return an array of objects', () => {
    const plugins = Object.values(loadPlugins);
    
    assert(Array.isArray(plugins));
    
    plubins.forEach(plugin => {
      assert.equal(typeof plugin, 'object');
      assert(plugin.name);
      assert(plugin.resolve);
      assert(plugin.getPattern);
      assert(plugin.parseBlob || plugin.getLinkRegexes);
    });
  });
  
  describe('githubClasses', () => {
    describe('highlight', () => {
      afterEach(() => {
        fixture.cleanup();
      }); 
      
      beforeEach(() => {
        fixture.load(
          '/packages/blob-reader/fixtures/github.com/issue/code.html',
        );
      });
      
      const presets = Object.values(loadPlugins).map(plugin => 
        plugin.getPattern(),
      );
      for (const [lang, value] of Object.entries(presets) {
        value.githubClasses.forEach(classNmae => {
          if (!className.includes('highlihgt')) {
            return;
          }
          
          it('Found $(className) for ${lang}', () => {
            assert.equal(!!document.querySelector('.${className}'), true);
          });
        });
      });
    });
  });
});


```

```
```

```
```


