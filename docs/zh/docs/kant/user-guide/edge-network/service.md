# 服务

应用网格提供了服务管理功能，创建服务时给服务绑定应用实例，并配置访问端口，从而可以实现节点上应用间的相互访问。

## 创建服务

!!! 说明

    创建的服务确保可以访问的前提是：必须在发起访问的节点上安装 EdgeMesh 应用。

操作步骤如下：

1. 选择左侧导航栏的`边缘计算` -> `云边协同`，进入边缘单元列表页面，点击`边缘单元名称`，进入边缘单元详情页。

2. 选择左侧菜单`应用网格` -> `服务`，点击服务列表右上角`创建服务`按钮。

    ![创建服务](https://docs.daocloud.io/daocloud-docs-images/docs/zh/docs/kant/images/service-01.png)

3. 填写相关参数。

    | 参数             | 说明                                                         | 举例值    |
    | ---------------- | :----------------------------------------------------------- | :-------- |
    | 访问类型         | 【类型】无须填写<br />【含义】指定 Pod 服务发现的方式，默认集群内访问（ClusterIP）。 | ClusterIP |
    | 服务名称         | 【类型】必填<br />【含义】输入新建服务的名称。<br />【注意】请输入4 到 63 个字符的字符串，可以包含小写英文字母、数字和中划线（-），并以小写英文字母开头，小写英文字母或数字结尾。 | Svc-01    |
    | 命名空间         | 【类型】必填<br />【含义】选择新建服务所在的命名空间。关于命名空间更多信息请参考[命名空间概述](../namespaces/createns.md)。<br />【注意】请输入4 到 63 个字符的字符串，可以包含小写英文字母、数字和中划线（-），并以小写英文字母开头，小写英文字母或数字结尾。 | default   |
    | 标签选择器       | 【类型】必填<br />【含义】添加标签，Service 根据标签选择 Pod，填写后点击“添加”。 | app:job01 |
    | 端口配置         | 【类型】必填<br />【含义】为服务添加协议端口，需要先选择端口协议类型，目前支持 TCP、UDP 两种传输协议。<br />**端口名称**：输入自定义的端口的名称。<br />**服务端口（port）**：Pod 对外提供服务的访问端口。<br />**容器端口（targetport）**：工作负载实际监听的容器端口，用来对集群内暴露服务。 |           |
    | 会话保持         | 【类型】选填<br />【含义】开启后，相同客户端的请求将转发至同一 Pod | 开启      |
    | 会话保持最大时长 | 【类型】选填<br />【含义】开启会话保持后，保持的最大时长，默认为 30 秒 | 30 秒     |
    | 标签             | 【类型】选填<br />【含义】为服务添加标签<br />               |           |
    | 注解             | 【类型】选填<br />【含义】为服务添加注解<br />               |           |

    ![创建服务](https://docs.daocloud.io/daocloud-docs-images/docs/zh/docs/kant/images/service-02.png)

4. 点击`确定`，即创建服务成功，返回到服务列表页面，可以在服务列表中查看服务对应的访问端口。

!!! tip

    也可以通过 `YAML 创建`一个服务。

## 更新服务

服务支持更新服务别名、标签选择器、端口配置、会话保持等设置。

更新服务操作流程如下：

1. 进入边缘单元详情页，选择左侧导航栏的`应用网格` -> `服务`。

2. 点击服务名称，进入服务详情页，在页面右上角点击 `⋮` 按钮， 在弹出菜单中选择`更新`，可以对服务别名、标签选择器、端口配置、会话保持等设置进行修改操作。

    ![更新服务](https://docs.daocloud.io/daocloud-docs-images/docs/zh/docs/kant/images/service-03.png)

## 查看事件

支持查看服务事件信息。

服务详情页，选择`事件` tab，查看服务事件信息。

![查看服务事件](https://docs.daocloud.io/daocloud-docs-images/docs/zh/docs/kant/images/service-04.png)

## 删除服务

1. 进入边缘单元详情页，选择左侧导航栏的`应用网格` -> `服务`。

2. 点击服务名称，进入服务详情页，在页面右上角点击 `⋮` 按钮， 在弹出菜单中选择`删除`，可以对服务别名、标签选择器、端口配置、会话保持等设置进行修改操作。

    ![删除服务](https://docs.daocloud.io/daocloud-docs-images/docs/zh/docs/kant/images/service-05.png)
