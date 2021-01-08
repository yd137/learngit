chatbi
├── amplify
│   ├── backend
│   │   ├── api
│   │   │   ├── adminApi     	AWS Cognito操作API
│   │   │   │   ├── group-users  AWS Cognito用户操作API
│   │   │   │   ├── groups       AWS Cognito组操作API
│   │   │   ├── chatbiApi    AWS DynamoDB生成
│   │   │   │   ├── schema.graphql  AWS DynamoDB生成语句
│   │   │   ├── commonApi    chatbi共通操作API
│   │   │   │   ├── current-datetime  AWS服务器时间获取API
│   │   │   ├── elasticsearchApi      ES图表操作API
│   │   │   │   ├── actual-results   日报工作量统计API
│   │   │   │   ├── mentions         slack消息数统计API
│   │   │   └── slackApi     slack操作API
│   │   │   │   ├── actions  日报上传界面打开API 
│   │   │   │   ├── events   slack信息处理API
│   │   │   │   ├── reports  日报上传API
│   │   ├── auth
│   │   │   ├── chatbiAuth       chatibi项目权限设置
│   │   │   └── userPoolGroups   AWS Cognito权限设置
│   │   ├── function
│   │   │   ├── adminUserPoolGroups  AWS Cognito组操作Lambda
│   │   │   ├── adminUserPoolGroupUsers   AWS Cognito用户操作Lambda
│   │   │   ├── chatbiAuthPostConfirmation  注册用户发送emailLambda
│   │   │   ├── chatMessageAlert            消息数少于平均数警告Lambda
│   │   │   ├── chatMessageDBListener        chatMessage保存到ES处理Lambda
│   │   │   ├── chatMessageMentionDBListener chatMessageMention保存到ES处理Lambda
│   │   │   ├── chatToolMention     slack消息数统计Lambda
│   │   │   ├── common      共通Layer模块
│   │   │   │   ├── opt
│   │   │   │   │   ├── axios
│   │   │   │   │   │   └── index.js   http请求共通处理模块
│   │   │   │   │   ├── const
│   │   │   │   │   │   └── index.js   常量管理模块
│   │   │   │   │   ├── date-time
│   │   │   │   │   │   └── index.js   日期时间处理模块
│   │   │   │   │   ├── dynamo-db       
│   │   │   │   │   │   ├── const.js    DynamoDB常量定义模块
│   │   │   │   │   │   └── service.js  DynamoDB API操作模块
│   │   │   │   │   ├── elasticsearch   
│   │   │   │   │   │   ├── const.js    elasticsearch常量定义模块
│   │   │   │   │   │   └── service.js  elasticsearch操作模块
│   │   │   │   │   ├── lambda
│   │   │   │   │   │   └── index.js    lambda响应跨域处理模块
│   │   │   │   │   ├── slack
│   │   │   │   │   │   ├── check.js    slack请求令牌验证模块
│   │   │   │   │   │   └── const.js    slack常量定义模块
│   │   │   │   │   └── step
│   │   │   │   │       └── index.js    stepFucnton 统一处理模块
│   │   │   ├── dailyReportDBListener    dailyReport保存到ES处理Lambda
│   │   │   ├── dailyReportTaskDBListener dailyReportTask保存到ES处理Lambda
│   │   │   ├── getCurrentDatetime       AWS日期获取Lambda
│   │   │   ├── memberActualResult       日报工作量统计Lambda
│   │   │   ├── slackActionReportDateChange 日报上报日期变更处理Lambda
│   │   │   ├── slackActionReportSubmit   日报数据处理Lambda
│   │   │   ├── slackActionsListener      日报上报处理Lambda
│   │   │   ├── slackCommandReport        日报上报界面打开 Lambda
│   │   │   ├── slackEventChatMessage     slack数据处理Lambda
│   │   │   ├── slackEventsListener       slack数据接收Lambda
│   │   │   └── stepEntryPoint            stepfunction统一处理Lambda
│   │   ├── hosting
│   │   │   └── amplifyhosting
│   │   │       └── amplifyhosting-template.json
│   │   └── step
│   │       ├── slackActionsStep     日报上报stepFunction
│   │       └── slackEventsStep      slack数据处理stepFunction
│   └── team-provider-info.json
├── aws
│   ├── elastic-search
│   │   └── ddl.txt           elasticsearch创建Index语句   
│   ├── elastic-search-policy
│   │   ├── elastic-search.json Elasticsearch域的集群配置参数
│   │   └── elastic-search.sh   elasticsearch域的集群配置shell
│   ├── hosting-spa
│   │   └── readme.txt          amplify自定义域说明
│   └── simple-email-service
│       ├── add-mail-address
│       │   └── add-mail-address.sh   AWS SES 注册email shell
│       ├── chat-message-alert
│       │   ├── chat-message-alert-template.sh  AWS SES报警模板添加 hell 
│       │   └── chat-message-alert.json         AWS SES报警模板参数
│       └── new-user-template
│           ├── create-new-user-template.sh    AWS SES注册用户模板添加shell 
│           └── new-user-template.json         AWS SES注册用户模板参数
└── src
    ├── components  组件
    │   ├── common
    │   │   ├── block
    │   │   │   ├── Detail.vue              新增/修改界面共通组件
    │   │   │   ├── SearchCondition.vue     查询条件共通组件
    │   │   │   └── SearchResult.vue        查询结果共通组件
    │   │   ├── layout
    │   │   │   ├── Container.vue           Container布局
    │   │   │   ├── Default.vue             默认布局
    │   │   │   ├── Everyone.vue            Everyone布局
    │   │   │   └── Footer.vue	            Footer布局
    │   │   ├── modal-dialog
    │   │   │   └── ModalDialog.vue         模态框组件
    │   │   ├── overlay
    │   │   │   ├── index.js
    │   │   │   └── Overlay.vue             遮罩层组件
    │   │   └── snackbar
    │   │       └── Snackbar.vue            Snackbar组件
    │   ├── molecules
    │   │   ├── ConfirmButtons.vue          确认按钮组件
    │   │   ├── SearchButtons.vue           查询按钮组件
    │   │   ├── SectionTitle.vue            新增/修改界面title组件
    │   │   └── Transfer.vue                人员管理组件
    │   └── organisms
    │       ├── admin
    │       │   ├── group
    │       │   │   ├── AdminGroupDetail.vue   AWS Cognito用户组新增/修改界面组件
    │       │   │   ├── AdminGroupSearchCondition.vue  AWS Cognito用户组查询条件组件
    │       │   │   └── AdminGroupSearchResult.vue   AWS Cognito用户组查询结果显示组件
    │       │   └── user
    │       │       ├── AdminUserDetail.vue     AWS Cognito用户新增/修改界面组件
    │       │       ├── AdminUserSearchCondition.vue  AWS Cognito用户查询条件组件
    │       │       └── AdminUserSearchResult.vue     AWS Cognito用户查询结果显示组件
    │       ├── auth
    │       │   └── Auth.vue     权限验证组件
    │       ├── chat-message-alert
    │       │   ├── ChatMessageAlertDetail.vue    报警信息新增/修改界面组件
    │       │   ├── ChatMessageAlertSearchCondition.vue  报警信息查询条件组件
    │       │   └── ChatMessageAlertSearchResult.vue   报警信息查询结果显示组件
    │       ├── group
    │       │   ├── GroupDetail.vue              项目组新增/修改界面组件
    │       │   ├── GroupSearchCondition.vue     项目组查询条件组件
    │       │   └── GroupSearchResult.vue        项目组查询结果显示组件
    │       ├── member
    │       │   ├── MemberDetail.vue             系统人员新增/修改界面组件
    │       │   ├── MemberSearchCondition.vue    系统人员查询条件组件
    │       │   └── MemberSearchResult.vue       系统人员查询结果显示组件
    │       └── project
    │           ├── ProjectDetail.vue            项目新增/修改界面组件
    │           ├── ProjectSearchCondition.vue   项目查询条件组件
    │           └── ProjectSearchResult.vue      项目查询结果显示组件
    ├── config
    │   ├── const.js    通用常量管理
    │   └── es.js       elasticsearch常量管理
    ├── graphql
    │   ├── schema.json    graphql定义
    ├── layouts
    │   ├── default.vue    默认布局
    │   ├── error.vue      异常信息布局
    │   └── everyone.vue   everyone布局
    ├── middleware             中间件
    │   ├── authentication.js  AWS 用户获取中间件
    │   ├── models.js          datastore操作中间件
    │   ├── permission.js      权限控制中间件
    │   ├── projects.js        项目信息获取中间件
    │   └── README.md          中间件说明
    ├── models                 Datastore操作相关模块
    │   ├── index.d.ts         
    │   ├── index.js
    │   ├── README.md
    │   ├── schema.d.ts
    │   └── schema.js
    ├── pages
    │   ├── admin
    │   │   ├── group
    │   │   │   ├── index.vue   AWS Cognito用户组查询界面
    │   │   │   └── _id.vue     AWS Cognito用户组新增/修改界面
    │   │   └── user
    │   │       ├── index.vue   AWS Cognito用户查询界面
    │   │       └── _id.vue     AWS Cognito用户新增/修改界面
    │   ├── auth.vue
    │   ├── chat-message-alert
    │   │   ├── index.vue       报警信息查询界面
    │   │   └── _id.vue         报警信息新增/修改界面
    │   ├── group
    │   │   ├── index.vue       项目组查询界面
    │   │   └── _id.vue         项目组新增/修改界面
    │   ├── index.vue           首页
    │   ├── member
    │   │   ├── index.vue       系统用户查询界面
    │   │   └── _id.vue         系统用户新增/修改界面
    │   ├── project
    │   │   ├── index.vue       项目查询界面
    │   │   └── _id.vue         项目新增/修改界面
    │   └── waiting.vue         未分配组等待界面
    ├── plugins        插件
    │   ├── amplify.js         AWS amplify插件
    │   ├── logger.js          log 插件
    │   ├── modal-dialog.js    模态框插件
    │   ├── overlay.js         遮罩层插件
    │   ├── scrollbar.js       滚动条插件
    │   └── snackbar.js        snackbar插件
    ├── static
    │   └── favicon.ico        项目图标
    ├── test                 测试
    │   └── Logo.spec.js
    └── utils              工具模块
        ├── array.js       数组工具js
        ├── date-time.js   日期操作工具js
        └── validator.js   验证工具js
