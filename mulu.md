

### 数据处理
- 处理时间使用date-fns或者date.js插件 https://zhuanlan.zhihu.com/p/354019460
- 处理数据使用lodash插件 https://www.lodashjs.com/ 
- 处理页面打印插件vue-print-nb插件  https://www.npmjs.com/package/vue-print-nb
- 处理浮点数 math.js

## 目录结构

```
├── public                     # 静态资源
│   │── favicon.ico            # favicon图标
│   └── index.html             # html模板
├──src                         # 源代码
│   ├──api                     # 所有请求
│   ├──assets                  # 主题 字体等静态资源
│   ├──components              # 全局公用组件
│   ├──filters                 # 全局公用过滤器
│   ├──mixins                  # 全局公用混入
│   ├──router                  # 路由
│   ├──store                   # 全局 store管理
│   ├──style                   # 共用style
│   ├──utils                   # 全局公用方法
│   ├──views                   # views 所有页面
│   ├── App.vue                # 入口页面
│   ├── main.js                # 入口 加载组件 初始化等
│   └── public-path.js         # 配置乾坤项-勿动
├── .env.development           # 配置开发环境
├── .env.production            # 配置生产环境
├── .env.release               # 配置预览环境
├── .env.staging               # 配置测试环境
├── .gitignore.md              # git上传需要忽略的文件格式
├──  babel.config.js           # ES6语法编译配置
├──  package.json              # 依赖包
├──  README.md                 # 项目说明文档
└──  vue.config.js             # 项目启动配置项
```

## views 目录结构
- 如果子集页面有constants配置文件，新建一个文件夹包含constants.js文件和当前页面，如果没有就直接作为子集，
- 子文件夹不超过三级,超过三级直接放置在第三级结构

```
├── views                                      # views 所有页面
│   │── moduleA [一级]                         # 模块A-有子集
│   │   │── moduleA-a[二级]                    # 模块A-a-有子集 
│   │   │   │── index.vue                      # 模块A-a-首页
│   │   │   │── add文件夹[三级]                 # 模块A-a-新增文件夹
│   │   │   │     │── index.vue                # 模块A-a-新增页面
│   │   │   │     └── constants.js             # 模块A-a-新增页面配置项
│   │   │   │── edit.vue                       # 模块A-a-编辑
│   │   │   │── detail.vue                     # 模块A-a-详情
│   │   │   │── [other].vue                    # 模块A-a-其它页面
│   │   │   │── constants.js                   # 模块A-a-配置项
│   │   │   └── [other].js                     # 模块A-a-其它方法
│   │   └── moduleA-b                          # 模块A-b-没有子集
│   │       │── index.vue                      # 模块A-b-首页
│   │       │── add.vue                        # 模块A-b-新增
│   │       │── edit.vue                       # 模块A-b-编辑
│   │       │── detail.vue                     # 模块A-b-详情
│   │       │── [other].vue                    # 模块A-b-其它页面
│   │       │── constants.js                   # 模块A-b-配置项
│   │       └── [other].js                     # 模块A-b-其它方法
│   └── moduleB[一级]                          # 模块B-有子集
│       │── index.vue                          # 模块B-首页
│       │── add.vue                            # 模块B-新增
│       │── edit.vue                           # 模块B-编辑
│       │── detail.vue                         # 模块B-详情
│       │── [other].vue                        # 模块B-其它页面
│       │── constants.js                       # 模块B-配置项
│       └── [other].js                         # 模块B-其它方
└── index.vue                                  # 页面

```

## router 目录结构
- moduleA（模块A）路由放在 router/index.js 中，
- 子路由放在对应 moduleA或者moduleB等文件夹下的文件中；
```
├── router
│   │── moduleA
│   │   │── [a].js
│   │   └── [b].js
│   └── moduleB
│   |    │──[a].js
│   |    └──[b].js
│   └──index.js
                              

```

## api 目录结构
- 按模块下的页面建立对应的接口文件（如 [a].js ，[b].js），
```
├── api
│   │── moduleA
│   │   │── [a].js
│   │   └── [b].js
│   └── moduleB
│       │──[a].js
│       └──[b].js
```