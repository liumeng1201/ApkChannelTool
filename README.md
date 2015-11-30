# ApkChannelTool
apk批量修改渠道工具

基于`https://github.com/SSOOnline/ApkCustomizationTool`的**ApkCusomizationTool**工具进行调整。适用于批量调整已有apk的渠道号。

GUI基于JavaFx，因此请安装**最新版JDK 1.8（u65及以上版本）**。

---

![struct](sc1.png)

1. 使用前请配置signer.properties文件，调整keystore文件相关配置
1. 渠道相关配置在data.xml文件中，具体配置请查看该文件
1. 使用时直接运行ApkCustomizationTool.jar即可

---

#重要说明

data.xml部分内容如下：

    <!-- 渠道配置 -->
    <channel>
        <!-- mark是渠道标记, name是渠道名称 -->
        <item mark="Google" name="GooglePlay"/>
        <item mark="360" name="_360app"/>
        <item mark="xioami" name="xiaomiapp"/>
        <item mark="meizu" name="meizustore"/>
    </channel>

    <!-- 当前apk中的渠道号 -->
    <currentChannel>
        <item name="currentChannel"/>
    </currentChannel>

data.xml文件中最重要的配置如上所示，channel标签下即为要配置的渠道ID，currentChannel标签下为要调整的apk文件中已有的渠道ID，例如：已有如下渠道配置

	<meta-data
        android:name="UMENG_CHANNEL"
        android:value="test" />
则

	<currentChannel>
        <item name="test"/>
    </currentChannel>

之后运行工具会将test替换为之前配置的渠道号。