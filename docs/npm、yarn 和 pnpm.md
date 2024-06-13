## npm、yarn 和 pnpm 三者比较及使用详解

### 1 简介

在 Vue 项目中，我们需要使用许多第三方依赖库，如 Vue Router、Vuex、Axios、Element UI 等等。这些依赖库通常以 NPM 包的形式提供，而且在使用时需要进行版本管理。因此，我们需要使用一个包管理工具来统一管理这些依赖库，避免版本冲突和管理繁琐。

常见的 Vue 项目包管理工具包括：

NPM：NPM（Node Package Manager）是 Node.js 自带的包管理工具，也是最常用的包管理工具之一。它可以方便地安装、升级、卸载依赖包，还可以发布自己的包到 NPM 仓库。

Yarn：Yarn 是 Facebook 推出的包管理工具，具有速度快、缓存机制好等优点。与 NPM 相比，Yarn 可以更快地下载依赖包，并且支持离线模式。

PNPM：PNPM（Permissive NPM）是一款新兴的包管理工具，与 NPM 不同的是，PNPM 采用了类似软链接的方式，将依赖包安装到每个项目的 node_modules 目录下，从而避免了大量的重复安装。

这些包管理工具都提供了一种方便的方式来管理项目中的依赖库，并且都能够很好地集成到 Vue 项目中。


#### 中文官网地址

以下是这些工具的中文官网地址：

+ [Node.js 中文官网地址](https://nodejs.org/en)
+ [Vue.js V2 中文官网地址](https://v2.cn.vuejs.org/)
+ [Vue.js V3 中文官网地址](https://cn.vuejs.org/)
+ [npm 中文官网地址](https://www.npmjs.cn/)
+ [Yarn V1 中文官网地址](https://yarn.bootcss.com)
+ [Yarn V2 中文官网地址](https://www.yarnpkg.cn)
+ [PNPM 中文官网地址](https://pnpm.io/zh)

### 2 NPM

#### 2.1 NPM 简介

NPM（Node Package Manager）是 Node.js 默认的包管理器，它是世界上最大的软件注册表之一，有超过 100 万个包（package）可供下载使用。NPM 可以让开发者轻松地分享、安装和管理 Node.js 中的代码包和依赖项，它是构建现代 JavaScript 应用程序的关键组件之一。

除了作为 Node.js 的包管理器之外，NPM 也可以用于前端开发。在前端开发中，NPM 主要用于安装、管理和更新前端项目的各种依赖包，例如 Vue、React、Angular 等常用框架。NPM 可以帮助开发者快速、方便地安装和管理这些依赖，以便在项目中使用它们。

总之，NPM 是一个非常重要的开发工具，它提供了丰富的功能和生态系统，帮助开发者更轻松、更高效地构建应用程序。

#### 2.2 NPM 安装

详细的安装说明，可以参考菜鸟教程中的 [Node.js 安装配置](https://m.runoob.com/nodejs/nodejs-install-setup.html) 教程。

安装好 Node.js 之后，npm 会自动安装在电脑上，因此无需另行安装。你可以在命令行中输入 npm -v 命令，检查 npm 是否已经正确安装。如果输出了版本号，则说明 npm 安装成功。

```Shell
# 查看 Node.js 版本信息
node -v

# 查看 npm 版本信息
npm -v
```

#### 2.3 NPM 常用命令

下面列举一些常用的 npm 命令及其详细介绍：

```Shell
# 1、创建一个新的 Node.js 应用程序或模块，并在 package.json 文件中定义依赖项。
npm init

# 2、安装依赖项。如果在安装时没有指定包的版本号，则将安装最新版本的包。
npm install

# 3、安装指定的依赖项，并将其添加到 package.json 文件中的 dependencies 中。
npm install <package name> --save

# 4、安装指定的开发依赖项，并将其添加到 package.json 文件中的 devDependencies 中。
npm install <package name> --save-dev

# 5、将包安装为全局包，以便在系统的任何位置使用它们。
npm install -g <package name>

# 6、更新 package.json 文件中指定的所有包的版本。
npm update

# 7、更新指定的包的版本。
npm update <package name>

# 8、卸载指定的依赖项，并将其从 package.json 文件中的 dependencies 或 devDependencies 中删除。
npm uninstall <package name>

# 9、查看指定的包的详细信息，包括其版本、描述、关键字、维护者等。
npm view <package name>

# 10、搜索与指定关键字匹配的包。
npm search <keywords>

# 11、清除 npm 的缓存。
npm cache clean

# 12、启动 Node.js 应用程序。
npm start

# 13、运行测试套件。
npm test

# 14、运行 package.json 文件中指定的脚本。
npm run <script name>

# 15、列出当前项目中已安装的所有包及其依赖关系。
npm ls

# 16、检查当前项目中已安装的包是否有过时的版本。
npm outdated：

# 17、查看指定包的详细信息。
npm view <package name>

# 18、查看指定包的摘要信息。
npm info <package name>

# 19、将当前目录下的代码发布为一个 npm 包。
npm publish

# 20、查看当前登录的 npm 用户名。
npm whoami
```

以上是一些常用的 npm 命令及其详细介绍，可以根据您的需要选择使用。

#### 2.4、NPM 创建项目

要创建一个 Vue 项目，可以使用 Vue CLI（Command Line Interface）命令行工具来生成基本的项目结构和文件。

##### 2.4.1、vue init

vue init 是在 Vue CLI 2.x 版本中使用的创建项目的命令，可以快速创建一个模板项目，例如从一个 GitHub 模板中拉取 Vue 项目模板进行初始化。可以通过命令行交互式地选择需要的模板以及一些配置信息。vue init 指令已经被 Vue CLI 3.x 中的 vue create 替代，不再更新。

使用 vue init 创建 Vue 项目示例：

```Shell
# 全局安装 Vue CLI 2.x
npm install -g vue-cli

# 查看 Vue 版本信息
vue --version

# 从 GitHub 上拉取 webpack 模板
vue init webpack my-project

# 安装依赖
cd my-project
npm install

# 运行项目
npm run dev
```

##### 2.4.2、vue create

vue create 是在 Vue CLI 3.x 版本中使用的创建项目的命令，可以快速创建一个新的 Vue 项目，从而让开发者快速搭建起一个基本的 Vue 项目架构。

vue create 提供了默认的配置以及插件管理，开发者可以根据自己的需要进行配置和管理。

使用 vue create 创建 Vue 项目示例：

```Shell
# 全局安装 Vue CLI 3.x
npm install -g @vue/cli

# 查看 Vue 版本信息
vue --version

# 创建一个新项目
vue create my-project

# 安装依赖
cd my-project
npm install

# 运行项目
npm run serve
```

在创建项目时，vue create 提供了更多的配置选项和插件，比如使用 TypeScript、使用 Vue Router、使用 Vuex 等等。同时，使用 vue create 创建项目可以直接在项目中添加插件，而不需要像 vue init 一样手动添加。


### 3 Yarn

#### 3.1 Yarn 简介

Yarn 是一个 JavaScript 的包管理器，它是由 Facebook、Google、Tilde 以及其他社区成员共同维护的开源项目。Yarn 在 NPM 的基础上进行了改进和增强，旨在提高依赖包的安装速度和可靠性。

相对于 NPM，Yarn 有以下几个特点：

> + 快速：Yarn 通过并行安装依赖包，从而比 NPM 更快地完成依赖包的安装。
> + 可靠：Yarn 会生成一个锁定文件（yarn.lock），确保每次安装的依赖包版本是相同的，从而避免了版本不一致的问题。
> + 安全：Yarn 通过对依赖包的哈希校验，确保安装的依赖包是安全的，并且没有被篡改。
> + 离线模式：Yarn 可以在没有网络的情况下运行，从而提高了开发者的灵活性。

需要注意的是，Yarn 和 NPM 本质上都是包管理工具，它们都可以管理 JavaScript 项目的依赖包。在使用 Yarn 或 NPM 时，建议了解其使用方法和命令，以便更好地管理项目的依赖包。


#### 3.2 Yarn 安装

如果您已经安装了 Node.js，可以通过 npm 来安装 Yarn。通过 npm 安装 Yarn 有两种方式：

1、全局安装

```Shell
# 全局安装
npm install -g yarn

# 查看 Yarn 版本信息
yarn -v
```

这种方式会将 Yarn 安装到全局环境中，从而可以在任意位置使用 yarn 命令。

2、本地安装

```Shell
# 本地安装
npm install yarn

# 查看 Yarn 版本信息
yarn -v
```

这种方式会将 Yarn 安装到当前目录的 node_modules 文件夹中。可以通过 ./node_modules/yarn/bin/yarn 命令来运行 Yarn。

**$\color{#FF0000}{注意：可以使用以下命令来安装特定版本的 Yarn}$**

```Shell
# 查看可用的 Yarn 版本
npm view yarn versions

# 全局安装特定版本
npm install -g yarn@<version>

# 本地安装特定版本
npm install yarn@<version>

# 查看 Yarn 版本信息
yarn -v
```

#### 3.3 Yarn 常用命令

下面列举一些常用的 Yarn 命令及其详细介绍：

```Shell
# 1、该命令将引导您创建一个新的 package.json 文件。您可以提供一些信息，例如项目名称、版本号、作者、描述等。
yarn init

# 2、该命令将安装指定的软件包并将其添加到项目依赖项中。您可以使用 @ 版本前缀来安装特定版本的软件包。例如：yarn add package@1.0.0。
yarn add [package]

# 3、该命令将从项目依赖项中删除指定的软件包。
yarn remove [package]

# 4、该命令将更新指定软件包的版本。您可以使用 @ 版本前缀来更新特定版本的软件包。例如：yarn upgrade package@1.0.0。
yarn upgrade [package]

# 5、该命令将根据项目中的 package.json 文件安装所有依赖项。如果您在运行时指定了 --production 标志，则只会安装生产依赖项。
yarn install

# 6、该命令将清除 Yarn 的缓存。这可能会释放一些磁盘空间并解决某些依赖项问题。
yarn cache clean

# 7、该命令将全局安装指定的软件包。这通常用于安装全局命令行工具。
yarn global add [package]

# 8、该命令将从全局安装中删除指定的软件包。
yarn global remove [package]

# 9、该命令将列出当前项目中的所有依赖项。
yarn list

# 10、该命令将运行项目中指定的脚本。例如：yarn run start。
yarn run [script]

# 11、该命令将运行项目中的测试脚本。
yarn test

# 12、该命令将根据项目中的配置文件构建项目。
yarn build

# 13、该命令将发布您的软件包到 Yarn 存储库中。
yarn publish

# 14、该命令将显示有关指定软件包的详细信息。
yarn info [package]

# 15、该命令将使您登录到 Yarn 存储库。
yarn login

# 16、该命令将使您从 Yarn 存储库注销。
yarn logout

# 17、该命令将允许您将本地软件包链接到项目中。
yarn link [package]

# 18、该命令将从项目中取消链接指定的软件包。
yarn unlink [package]

# 19、该命令将显示指定软件包的依赖项信息。
yarn why [package]

# 20、该命令将显示项目依赖项的许可证信息。
yarn licenses ls
```

以上是一些常用的 Yarn 命令及其详细介绍，可以根据您的需要选择使用。


#### 3.4 Yarn 创建项目

##### 3.4.1 yarn create vue-app
yarn create vue-app 创建的是基于 Vue CLI 2.x 版本的项目，该版本的 Vue CLI 使用 webpack 进行打包，需要配置一些基本的项目信息和插件。

使用 yarn create vue-app 创建 Vue 2.x 项目：

```Shell
# 创建一个 Vue 2.x 项目
yarn create vue-app my-project

# 安装依赖
cd my-project
yarn install

# 运行项目
yarn serve
```

##### 3.4.2 yarn create vite-app

yarn create vite-app 创建的是基于 Vue CLI 3.x 版本的项目，该版本的 Vue CLI 使用了 vite 构建工具，具有更快的构建速度和更少的配置，适合较小的项目和快速原型开发。

使用 yarn create vite-app 创建 Vue 3.x 项目：

```Shell
# 创建一个 Vue 3.x 项目
yarn create vite-app my-project --template vue

# 安装依赖
cd my-project
yarn install

# 运行项目
yarn serve
```

在上面的命令中，my-project 是项目名称，可以根据实际情况进行更改。同时，–template 参数用于指定创建的项目模板，如果不指定，默认是 JavaScript 模板。对于 Vue 3.x 项目，需要指定 --template vue。

### 4 PNPM

#### 4.1 PNPM 简介

PNPM 是一个 Node.js 包管理工具，类似于 NPM 和 Yarn。PNPM 采用了一种不同于 NPM 和 Yarn 的方式来管理 Node.js 包，它使用硬链接来共享依赖包，从而减少了存储空间的占用和安装的时间。同时，PNPM 也可以像 NPM 和 Yarn 一样在全局和本地范围内安装和使用 Node.js 模块。PNPM 还提供了一些其他的功能，比如支持自动清理未使用的包，以及支持多个版本的 Node.js 和 NPM。

相比于 NPM 和 Yarn，PNPM 具有以下优点：

> + 节约磁盘空间：PNPM 使用硬链接来共享依赖包，因此只需要存储一份依赖包的副本，可以大大节约磁盘空间。
> + 加速安装：PNPM 可以同时下载和安装多个依赖包，从而加速安装过程。
> + 更好的稳定性：PNPM 可以在多个项目之间共享依赖包，从而减少了不同版本的包之间的冲突和版本不一致的问题。
> + PNPM 的主要缺点是相对于 NPM 和 Yarn，它的社区和生态系统还比较小，因此在某些方面可能缺乏支持和文档。

#### 4.2 PNPM 安装

1、使用 npm 全局安装

```Shell
# 使用 npm 全局安装
npm install -g pnpm

# 查看 pnpm 版本信息
pnpm --version
```

2、使用 yarn 全局安装

```Shell
# 使用 yarn 全局安装
yarn global add pnpm

# 查看 pnpm 版本信息
pnpm --version
```

**$\color{#FF0000}{注意：可以使用以下命令来安装特定版本的 pnpm}$**

```Shell
# 查看可用的 pnpm 版本
npm view pnpm versions

# 使用 npm 全局安装特定版本
npm install -g pnpm@<version>

# 使用 npm 本地安装特定版本
npm install pnpm@<version>

# 查看 pnpm 版本信息
pnpm --version
```

#### 4.3 PNPM 常用命令

下面列举一些常用的 pnpm 命令及其详细介绍：

```Shell
# 1、用于安装项目中的所有依赖。
pnpm install

# 2、用于安装指定的依赖包，例如 pnpm install react。
pnpm install [package]

# 3、用于全局安装指定的依赖包，例如 pnpm install --global typescript。
pnpm install --global [package]

# 4、用于更新项目中的所有依赖。
pnpm update

# 5、用于更新指定的依赖包，例如 pnpm update react。
pnpm update [package]

# 6、用于删除指定的依赖包，例如 pnpm remove react。
pnpm remove [package]

# 7、用于列出当前项目中已安装的所有依赖包。
pnpm list

# 8、用于列出当前系统中已全局安装的所有依赖包。
pnpm list --global

# 9、用于列出当前项目中已安装的所有依赖包及其直接依赖项。
pnpm list --depth=1

# 10、用于查看指定依赖包的详细信息，例如 pnpm info react。
pnpm info [package]

# 11、用于将指定的依赖包添加到 devDependencies，例如 pnpm add jest --save-dev。
pnpm add [package] --save-dev

# 12、用于将指定的依赖包添加到 dependencies，例如 pnpm add react --save。
pnpm add [package] --save

# 13、用于全局安装指定的依赖包，例如 pnpm add typescript --global。
pnpm add [package] --global

# 14、用于重新构建项目中的所有依赖。
pnpm rebuild

# 15、用于运行项目中的脚本命令，例如 pnpm run start。
pnpm run [script]

# 16、用于查看本地包存储状态。
pnpm store status

# 17、用于清理本地存储的未被任何项目使用的包。
pnpm store prune

# 18、用于将指定的依赖包添加到本地存储，以便其他项目使用。
pnpm store add [package]

# 19、用于启动本地包服务器。
pnpm server

# 20、用于在所有项目中执行指定命令，例如 pnpm recursive install。
pnpm recursive [command]
```

以上是一些常用的 pnpm 命令及其详细介绍，可以根据您的需要选择使用。

#### 4.4 PNPM 创建项目

创建 Vue 项目的方式与 PNPM 无关，与使用的脚手架工具有关。

无论使用哪种方式创建 Vue 项目，都可以在项目目录下使用 PNPM 进行依赖安装。例如，在使用 Vue CLI 创建项目后，进入项目目录后可以使用 pnpm install 安装依赖。

##### 4.4.1 pnpm create vue-app

pnpm create vue-app 创建的是基于 Vue CLI 2.x 版本的项目，该版本的 Vue CLI 使用 webpack 进行打包，需要配置一些基本的项目信息和插件。

使用 pnpm create vue-app 创建 Vue 2.x 项目：

```Shell
# 创建一个 Vue 2.x 项目
pnpm create vue-app my-project

# 安装依赖
cd my-project
pnpm install

# 运行项目
pnpm serve
```

##### 4.4.2 pnpm create vite-app
pnpm create vite-app 创建的是基于 Vue CLI 3.x 版本的项目，该版本的 Vue CLI 使用了 vite 构建工具，具有更快的构建速度和更少的配置，适合较小的项目和快速原型开发。

使用 pnpm create vite-app 创建 Vue 3.x 项目：

```Shell
# 创建一个 Vue 3.x 项目
pnpm create vite-app my-project --template vue

# 安装依赖
cd my-project
pnpm install

# 运行项目
pnpm serve
```

在上面的命令中，my-project 是项目名称，可以根据实际情况进行更改。同时，–template 参数用于指定创建的项目模板，如果不指定，默认是 JavaScript 模板。对于 Vue 3.x 项目，需要指定 --template vue。


### 5 项目笔记

#### 5.1 server 和 run dev

##### 5.1.1、yarn serve 和 yarn run dev

yarn serve 和 yarn run dev 都是用来启动前端项目开发环境的命令，但是对应的使用场景和实现方式不同。

通常情况下，yarn run dev 是在 package.json 文件中配置的一个脚本命令，用于启动开发环境的服务。比如：

```javascript
{
  "scripts": {
    "dev": "webpack-dev-server --open"
  }
}
```

在上面的示例中，运行 yarn run dev 命令时，实际上执行的是 webpack-dev-server --open 命令，用于启动一个开发环境的服务器，实时监控文件变化并重新构建项目。

而 yarn serve 则是一个独立的命令，需要先安装 serve 这个包。它的作用也是启动一个本地服务器，用于开发环境的调试和测试。例如，我们可以通过以下命令来安装和使用 serve：

```Shell
# 安装 serve 包
yarn global add serve

# 在当前目录启动一个服务器，默认使用 5000 端口
yarn serve
```

在默认情况下，yarn serve 会在当前目录下启动一个本地服务器，可以在浏览器中通过 http://localhost:5000 访问。与 yarn run dev 相比，yarn serve 不需要在项目中配置脚本命令，更加方便快捷。

##### 5.1.2 pnpm server 和 pnpm run dev
pnpm server 和 pnpm run dev 都是运行项目的命令，但是具体的区别取决于项目的配置文件和脚本配置。

通常来说，pnpm run dev 是在项目中定义的脚本命令，用于在开发模式下启动项目。开发模式一般会启用热更新、调试模式等功能，方便开发人员实时调试和查看项目的效果。

而 pnpm server 则是一个比较通用的命令，可以在终端中直接输入来启动一个 web 服务器，并将当前目录作为网站的根目录。该命令不仅仅可以用于前端项目，还可以用于一些静态网站的开发和部署。

需要注意的是，具体命令的使用方式和效果取决于项目的具体配置和脚本命令，如果不确定应该使用哪个命令，可以参考项目的文档或者询问开发人员。

#### 5.2 Node.js、Vue.js、npm、Yarn 和 PNPM 之间版本关系

不同版本的 Node.js、Vue.js、npm、Yarn 和 PNPM 之间是有关联的。下面是它们之间的关系总结：

##### 5.2.1 Node.js 版本和 Vue.js 版本的关联

Node.js 版本和 Vue.js 版本之间存在一定的关联，不同的 Vue.js 版本对 Node.js 版本有不同的要求。具体来说，Vue.js 2.x.x 支持的 Node.js 版本为 8.9 或更高版本，Vue.js 3.x.x 支持的 Node.js 版本为 10 或更高版本。

Node.js 是 Vue.js 的运行环境，因此 Vue.js 的版本兼容性取决于Node.js 的版本兼容性。

需要注意的是，Node.js 版本过低或过高都可能导致 Vue.js 项目无法正常运行。因此，在使用 Vue.js 时，需要根据具体的 Vue.js 版本要求选择合适的 Node.js 版本，并且保持 Node.js 版本的稳定性和更新。

##### 5.2.2 Node.js 版本和 npm版本的关联

Node.js 版本和 npm 版本有一定的关联性，因为 npm 是随 Node.js 一起安装的。通常情况下，当你升级 Node.js 时，npm 的版本也会随之更新。但是，有时候可能需要手动升级 npm 版本，以满足项目的需求。

通过 node -v 命令查看安装的 Node.js 版本，再通过 npm -v 命令查看对应的 npm 版本。

需要注意的是，在 Node.js v0.6.x 及以下版本中，npm 是一个独立的包管理器，需要手动安装和升级。从 Node.js v0.8.x 开始，npm 被作为默认的包管理器一同安装。因此，在这些较老的 Node.js 版本中，可能需要手动安装或升级 npm 版本。

##### 5.2.3、Node.js 版本和 Yarn 版本的关联

Yarn 是一款独立于 Node.js 的包管理工具，但它需要 Node.js 的运行环境。

Node.js 版本和 Yarn 版本的关联如下：

Yarn 1.x.x 版本要求 Node.js 版本 >= 10.13.0 。

Yarn 2.x.x 版本要求 Node.js 版本 >= 12.13.0 。

这是因为 Yarn 2.x.x 版本使用了 Node.js 12.x.x 的新特性，而旧版 Node.js 不支持这些特性。因此，在安装 Yarn 2.x.x 之前，必须先安装 Node.js 12.13.0 或更高版本。

需要注意的是，不同操作系统下 Yarn 的最新版本可能不同，因此在安装 Yarn 时需要根据自己的操作系统和 Node.js 版本选择合适的 Yarn 版本。

##### 5.2.4 Node.js 版本和 PNPM 版本的关联

PNPM 是一款独立于 Node.js 的包管理工具，但它需要 Node.js 的运行环境。

Node.js 版本和 PNPM 版本的关联与 Node.js 版本和 npm 版本的关联类似，因为 PNPM 是基于 npm 的改进版本。所以，在安装 PNPM 时需要先安装 Node.js 和 npm。一般来说，PNPM 会支持与当前 Node.js 版本兼容的最新版本，具体兼容版本可以在 PNPM 的官方文档中查看。另外，PNPM 还提供了对特定 Node.js 版本的支持，可以使用 PNPM 的特定版本来安装适用于特定 Node.js 版本的 PNPM，例如使用 npm i -g pnpm@6.14.11 命令安装 PNPM 的 6.14.11 版本，以适用于 Node.js v14.x 的版本。总之，PNPM 的版本需要与当前的 Node.js 版本兼容，才能保证正常使用。

##### 5.2.5 Vue.js 版本和 npm、Yarn、PNPM 版本的关联

Vue.js 版本和包管理工具（npm、Yarn、PNPM）的版本之间并没有直接的关联。Vue.js 官方会在每个版本发布时指定支持的 Node.js 版本和 npm 版本的最小要求，这些要求和包管理工具的版本没有直接的关系，但是包管理工具需要在指定的 Node.js 版本和 npm 版本的基础上运行才能正常工作。

比如，Vue.js 2.x 支持的最小 Node.js 版本是 4.0.0，支持的最小 npm 版本是 3.0.0。如果要使用 Yarn 或 PNPM 来管理依赖，需要确保安装的 Yarn 或 PNPM 版本能够在 Node.js 4.0.0 和 npm 3.0.0 的环境中正常工作。

需要注意的是，Vue CLI 的某些版本可能会要求使用特定版本的包管理工具。比如，Vue CLI 3.0 要求使用 Yarn 1.x，而不支持 Yarn 2.x。在使用 Vue CLI 时，建议查看官方文档中的要求和建议，以保证开发环境的兼容性。


### 6 总结

npm、yarn 和 pnpm 都是用于管理 JavaScript 包和依赖项的工具，它们之间有一些不同之处，下面是它们的对比总结：

+ **安装依赖速度**
npm 和 yarn 都需要下载和解压缩整个包，而 pnpm 则使用一种独特的方法来避免这个问题。它会将包存储在本地，并在项目中创建符号链接。这意味着使用 pnpm 时，不需要在本地下载重复的包，因此安装速度更快。

+ **缓存机制**
npm 和 yarn 都有自己的缓存机制，以便在安装依赖项时重新使用相同的依赖项，以节省时间和空间。pnpm 也有缓存机制，但与 npm 和 yarn 不同的是，它将包存储在本地，并使用符号链接将它们链接到项目中。这使得 pnpm 可以更快地重用依赖项，因为它们不需要从缓存中解压缩。

+ **命令**
npm、yarn 和 pnpm 都具有相似的命令，例如 install、remove、update等。它们之间的不同之处在于一些额外的命令，例如 yarn 有 workspace 命令，可用于处理多个包。

+ **跨平台支持**
npm 和 yarn 都支持跨平台，可在 Windows、macOS 和 Linux 上运行。pnpm 也支持跨平台，但在 Windows 上的性能可能会受到影响。

+ **社区支持**
npm 是最早推出的 JavaScript 包管理器之一，因此具有庞大的社区支持。yarn 也拥有庞大的社区，但相对于 npm 来说要小一些。pnpm 是最新的包管理器之一，因此相对于 npm 和 yarn 来说，它的社区支持要少一些。

总的来说，选择使用哪种包管理工具取决于个人需求和项目需求。如果需要快速安装依赖项并具有良好的缓存机制，则可以选择 pnpm。如果需要具有大量社区支持和广泛的生态系统，则可以选择 npm。如果需要支持工作区和锁定文件，则可以选择 yarn。
