# 项目说明

## 文件说明

- config

  > 相关配置变量

  - dev.env,prod.env
    > 开发环境，生成环境相关变量配置

- src

  - api

    > 接口例子:设置默认 data 为空对象，data 会自动设置*access_token*,_user_id_,当
    > 前机构*org_id* 等字段

    ```
    export function apiName(data = {}) {
    return request(apiUrl, data);
    }
    ```

    | 主要模块   | 文件                                                                                     |
    | ---------- | ---------------------------------------------------------------------------------------- |
    | 报名管理   | student_control、course_control、order                                                   |
    | 教务管理   | class_control、date_template                                                             |
    | 数据中心   | statistical                                                                              |
    | 财务中心   | deliver、financial                                                                       |
    | 小程序中心 | article_control、banner_control、balance、relation、miniProgram_center、recommend_course |
    | 超级拼课   | group_course                                                                             |
    | 图册生成器 | pic_generator                                                                            |

  - common
    > common/stylus 基础样式，ui 框架样式改写
  - components

    > 公共组件

    - date_check
      > 日期选择组件，包含了日期，时间范围，星期等。
    - top_box

      > 列表顶部过滤组件

      - mutex_check_bar

        > 不限，多选互斥组件

      - radio_bar
        > 单选框组件
      - search_bar (较少用)

        > 搜索组件,新版 **_<span style='color:red'>listViewTemplate</span>_** 中有集成，所以较为少用

      - tags_bar
        > 页签组件
      - time_bar
        > 时间范围选择组件,带快捷选择

    - listViewTemplate(大量使用)

      > 集成了翻页，导出中心弹框，搜索栏，过滤项插槽，列表上方框插槽

    - pub_editor_new(主要使用于 **<span style='color:red'>超级拼课</span>**)

      > 基于 ueditor，集成了秀米的富文本编辑器组件。

    - pub_editor
      > tinymce 富文本编辑器组件
    - pub_table_setting

      > 表头设置组件

    - pub_upload_list,pub_upload
      > 基础上传组件，可自定义设置图片需求。

  - router

    > 路由配置，通过 **<span style='color:red'>webpackChunkName</span>** 进行代码路由拆分,列子如下:

    ```
     const studentOrder = () => import(/* webpackChunkName: "group-student" */ "@/views/recruit_student/student_order/index.vue");
    ```

  - store
    > vuex 配置文件，主要文件是 modules/common,modules/user,modules/course。
  - utils
    > 工具类，vuePubFunc 是公共工具，通过插件形式应用于 vue。
  - views
    > 视图文件,course(报名管理)、data(数据中心)、group_course(超级拼课)、miniProgram_center(小程序中心)、operations_center(运维中心、组织架构 )、recruit_student(教务管理)、picGenerator(图册生成器)

- static

  > 项目静态文件

  - tinymce
    > tinymce 富文本编辑器的语言配置和皮肤
  - ueditor(主要用于 **_<span style='color:red'>超级拼课</span>_** )
    > ueditor 富文本编辑器,包含了富文本的相关插件，和集成了秀米。

---

## 重要说明

1.  页面跳转都会请求 is-login 接口，判断是否在登录状态，非登录状态则跳转到登录页
    。
2.  接口都带一个 version 字段，用于匹配当前版本号是否一致，不一致需刷新页面，解
    决打包后 js，css 报错。
3.  路由表生成，当前路由有无权限,用户状态等，均在 src\router\index.js 文件中进行
    判断。
4.  vuex 的 common 模块存储了公共筛选项数据，机构列表，机构数等数据。
5.  **<span style='color:red'>发布后，需手动更新版本号</span>**。
6.  topbar 标题,可通过路由配置 meta 对象 title 属性设置，或通过 dispatch
    ("setTopTitle")进行更改
7.  通过 cdn 引入了 echarts 和 font-awesome,在页面可直接使用，无需重复引入。
