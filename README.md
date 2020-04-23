# umi-react-native

> 👷 正在施工...

[umi](https://umijs.org/) react-native 插件。

## 进度

- [x] umi-runtime-react-native: done
- [x] umi-renderer-react-native: done
- [x] umi-plugin-react-native: done
- [ ] umi-plugin-react-native-bundler-metro: developing
- [ ] umi-plugin-react-native-bundler-haul

## 必备

- umi 3.0 及以上版本；
- RN 工程（已有，或使用`react-native init`新建）；
- [RN 开发环境](https://reactnative.dev/docs/environment-setup)。

## 安装

选用官方[metro](https://facebook.github.io/metro/)打包：

```npm
yarn add umi-plugin-react-native umi-plugin-react-native-bundler-metro  --dev
```

选用第三方[haul](https://github.com/callstack/haul)打包：

```npm
yarn add umi-plugin-react-native umi-plugin-react-native-bundler-haul  --dev
```

### 注意

`umi-plugin-react-native-bundler-metro` 和 `umi-plugin-react-native-bundler-haul` 只能二选一，同时安装会导致 umi 报错（`dev-rn`和`build-rn`命令行工具冲突）。

## 使用

零配置，umi 3.0 后似乎会自动探测并装配 package.json 依赖申明中的插件。

### 开发

修改`package.json`文件，使用`umi`取代原本的`react-native`：

```diff
{
  "scripts": {
    "android": "react-native run-android",
    "ios": "react-native run-ios",
-   "start": "react-native start",
+   "start": "umi dev-rn",
  },
}
```

执行`yarn start`之后，再使用 `yarn android` 或者 `yarn ios`。

### 构建离线包（offline bundle）

```shell
umi build-rn --platform <ios|android>
```
