---
title: 从模板创建仓库
intro: 您可以生成具有与现有仓库相同的目录结构和文件的新仓库。
redirect_from:
  - /articles/creating-a-repository-from-a-template
versions:
  free-pro-team: '*'
  enterprise-server: '>=2.18'
---

### About repository templates

任何对模板仓库具有读取权限的人都可以从该模板创建仓库。 更多信息请参阅“[创建模板仓库](/articles/creating-a-template-repository)”。

{% if currentVersion == "free-pro-team@latest" or currentVersion ver_gt "enterprise-server@2.19" %}
{% tip %}

**Tip**: You can also create a repository from a template using the {{ site.data.variables.product.prodname_cli }}. For more information, see "[`gh repo create`](https://cli.github.com/manual/gh_repo_create)" in the {{ site.data.variables.product.product_location }} documentation.

{% endtip %}
{% endif %}

{% if currentVersion == "free-pro-team@latest" or currentVersion ver_gt "enterprise-server@2.20" %}
您可以选择仅包括模板仓库的默认分支中的目录结构和文件，或者包括所有分支。
{% endif %}

从模板创建仓库类似于创建仓库的复刻，但存在一些重要差异：
- 新的复刻包含父仓库的整个提交历史记录，而从模板创建的仓库从一个提交开始记录。
- 对复刻的提交不会显示在您的贡献图中，而对从模板创建的仓库的提交会显示在您的贡献图中。
- 复刻可能是向现有项目贡献代码的临时方式，而从模板创建的仓库可以快速启动新项目。

有关复刻的更多信息，请参阅“[关于复刻](/articles/about-forks)”。

### 从模板创建仓库

{{ site.data.reusables.repositories.navigate-to-repo }}
2. 在文件列表上方，单击 **Use this template（使用此模板）**。 ![使用此模板按钮](/assets/images/help/repository/use-this-template-button.png)
{{ site.data.reusables.repositories.owner-drop-down }}
{{ site.data.reusables.repositories.repo-name }}
{{ site.data.reusables.repositories.choose-repo-visibility }}{% if currentVersion == "free-pro-team@latest" or currentVersion ver_gt "enterprise-server@2.20" %}
6. （可选）要包括模板中所有分支的目录结构和文件，而不仅仅是默认分支，请选择 **Include all branches（包括所有分支）**。 ![Include all branches checkbox](/assets/images/help/repository/include-all-branches.png){% endif %}
{{ site.data.reusables.repositories.select-marketplace-apps }}
8. 单击 **Create repository from template（从模板创建仓库）**。