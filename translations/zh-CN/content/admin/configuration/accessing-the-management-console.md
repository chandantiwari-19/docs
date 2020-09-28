---
title: Accessing the management console
intro: '使用 {{ site.data.variables.enterprise.management_console }} 可以设置和配置 {{ site.data.variables.product.product_location }}、排定维护窗口、排查问题以及管理许可。'
redirect_from:
  - /enterprise/admin/articles/about-the-management-console/
  - /enterprise/admin/articles/management-console-for-emergency-recovery/
  - /enterprise/admin/articles/web-based-management-console/
  - /enterprise/admin/categories/management-console/
  - /enterprise/admin/articles/accessing-the-management-console/
  - /enterprise/admin/guides/installation/web-based-management-console/
  - /enterprise/admin/installation/accessing-the-management-console
  - /enterprise/admin/configuration/accessing-the-management-console
versions:
  enterprise-server: '*'
---

### 关于 {{ site.data.variables.enterprise.management_console }}

使用 {{ site.data.variables.enterprise.management_console }} 执行基本管理活动：
- **初始设置**：首次启动 {{ site.data.variables.product.product_location_enterprise }} 时，在浏览器中访问 {{ site.data.variables.product.product_location_enterprise }} 的 IP 地址，简单了解初始设置流程。
- **配置实例的基本设置**：在“Settings”页面上配置 DNS、主机名、SSL、用户身份验证、电子邮件、监视服务和日志转发。
- **排定维护窗口**：使用 {{ site.data.variables.enterprise.management_console }} 或管理 shell 执行维护时，使 {{ site.data.variables.product.product_location_enterprise }} 进入脱机状态。
- **排查问题**：生成支持包或查看高级诊断信息。
- **许可管理**：查看或更新 {{ site.data.variables.product.prodname_enterprise }} 许可。

即使在实例处于维护模式，存在重大应用程序故障或者主机名或 SSL 错误配置的情况下，您也始终可以通过 {{ site.data.variables.product.product_location_enterprise }} 的 IP 地址访问 {{ site.data.variables.enterprise.management_console }}。

要访问 {{ site.data.variables.enterprise.management_console }}，您必须使用在 {{ site.data.variables.product.product_location_enterprise }} 初始设置期间确定的管理员密码。 您还必须能够连接到端口 8443 上的虚拟机主机。 如果无法访问 {{ site.data.variables.enterprise.management_console }}，请检查中间防火墙和安全组配置。

### 以站点管理员身份访问 {{ site.data.variables.enterprise.management_console }}

The first time that you access the {{ site.data.variables.enterprise.management_console }} as a site administrator, you must upload your {{ site.data.variables.product.prodname_enterprise }} license file to authenticate into the app. For more information, see "[Managing your {{ site.data.variables.product.prodname_enterprise}} license](/enterprise/{{ currentVersion }}/admin/guides/installation/managing-your-github-enterprise-license)."

{{ site.data.reusables.enterprise_site_admin_settings.access-settings }}
{{ site.data.reusables.enterprise_site_admin_settings.management-console }}
{{ site.data.reusables.enterprise_management_console.type-management-console-password }}

### 以未验证用户身份访问 {{ site.data.variables.enterprise.management_console }}

1. 在浏览器中访问此 URL，用您的实际 {{ site.data.variables.product.prodname_ghe_server }} 主机名或 IP 地址替换 `hostname`：
  ```shell
  http(s)://HOSTNAME/setup
  ```
{{ site.data.reusables.enterprise_management_console.type-management-console-password }}

### 登录尝试失败后解锁 {{ site.data.variables.enterprise.management_console }}

如果十分钟内登录尝试失败十次，{{ site.data.variables.enterprise.management_console }} 将锁定。 您必须等待登录屏幕自动解锁，然后才能再次尝试登录。 一旦前十分钟内登录尝试失败次数不足十次，登录屏幕便会自动解锁。 成功登录后，计数器会复位。

要立即解锁 {{ site.data.variables.enterprise.management_console }}，请通过管理 shell 使用 `ghe-reactivate-admin-login` 命令。 更多信息请参阅“[命令行实用程序](/enterprise/{{ currentVersion }}/admin/guides/installation/command-line-utilities#ghe-reactivate-admin-login)”和“[访问管理 shell (SSH)](/enterprise/{{ currentVersion }}/admin/guides/installation/accessing-the-administrative-shell-ssh/)”。