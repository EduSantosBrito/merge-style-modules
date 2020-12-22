<h1 align="center">Welcome to merge-style-modules 👋</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
  <a href="https://github.com/EduSantosBrito/merge-style-modules#readme" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="https://github.com/EduSantosBrito/merge-style-modules/graphs/commit-activity" target="_blank">
    <img alt="Maintenance" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" />
  </a>
  <a href="https://github.com/EduSantosBrito/merge-style-modules/blob/master/LICENSE" target="_blank">
    <img alt="License: ISC" src="https://img.shields.io/github/license/EduSantosBrito/merge-style-modules" />
  </a>
  <a href="https://twitter.com/edusantosbrito" target="_blank">
    <img alt="Twitter: edusantosbrito" src="https://img.shields.io/twitter/follow/edusantosbrito.svg?style=social" />
  </a>
</p>

> A package that merge style modules

## Install

```sh
yarn add merge-style-modules
```

## How to use

Sometimes you want to use more than one file with SASS/CSS modules like that:

```css
/* @styles/default.modules.scss */

.container {
  background-color: red;
}
```

```css
/* @styles/component.modules.scss */

.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

```jsx
import defaultStyle from "@styles/default.modules.scss";
import componentStyle from "@styles/component.modules.scss";
import { useMemo } from "react";

const Component = () => {
  // You can't just merge these objects because of property conflicts
  const styles = useMemo(() => ({ ...defaultStyle, ...componentStyle }), []);

  return <div className={styles.container}>test</div>;
};
```

So I've created this package :)

Now you just have to do that:

```jsx
import defaultStyle from "@styles/default.modules.scss";
import componentStyle from "@styles/component.modules.scss";
import { mergeStyles } from "merge-style-modules";
import { useMemo } from "react";

const Component = () => {
  const styles = useMemo(() => mergeStyles(defaultStyle, componentStyle), []);
  return <div className={styles.container}>test</div>;
};
```

## Author

👤 **edusantosbrito**

- Website: https://brito.top
- Twitter: [@edusantosbrito](https://twitter.com/edusantosbrito)
- Github: [@EduSantosBrito](https://github.com/EduSantosBrito)

## Show your support

Give a ⭐️ if this project helped you!

## 📝 License

Copyright © 2020 [edusantosbrito](https://github.com/EduSantosBrito).<br />
This project is [ISC](https://github.com/EduSantosBrito/merge-style-modules/blob/master/LICENSE) licensed.

---

_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
