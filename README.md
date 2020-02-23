## 踩坑记录

- 启动项目，务必参考`CONTRIBUTING.md`.
- 如果根目录下，执行yarn报错：
  - 第一步翻墙，不然会出现`⚠ connect ECONNREFUSED 151.101.228.133:443`的报错
  - 确保yarn是最新版本（我目前是1.22.0，可以尝试`curl -o- -L https://yarnpkg.com/install.sh
  | bash`），node版本是10.16.2（nvm install 10.16.2 && nvm use 10.16.2）
  - 如果出现node_modules/sharp下的报错，如：
  ```
error /Users/yangxiayan/Documents/duoduo/codesandbox-client-code/node_modules/sharp: Command failed.
Exit code: 1
Command: (node install/libvips && node install/dll-copy && prebuild-install) || (node-gyp rebuild && node install/dll-copy)
  ```
  可以尝试删除_libvips下的东西，
  ```
➜  _libvips ll
total 29624
-rw-r--r--  1 yangxiayan  staff   5.3M  2  8 17:56 libvips-8.7.4-darwin-x64.tar.gz
-rw-r--r--  1 yangxiayan  staff   8.8M  2 22 19:08 libvips-8.8.1-darwin-x64.tar.gz
  ```
  yarn成功后，可以执行 `yarn start`启动项目，或者`yarn start:fast`