---

copyright:
  years: 2017, 2019
lastupdated: "2019-01-28"

keywords: create connection, connect a service, bind, alias

subcollection: resources

---

{:shortdesc: .shortdesc}

# 管理連線
{: #connect_app}

您可以從服務儀表板的**連線**標籤，將服務連接至現有或新的 {{site.data.keyword.Bluemix}} 應用程式。將服務連接至應用程式時，會建立它們之間的連結。您可以從**連線**標籤取消連結、新增其他連線或刪除連線。

不過，當您將 {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) 所管理的服務實例連接至應用程式時，會使用您指定的連結資訊在對應的空間中自動建立由 IAM 所管理的服務別名。此別名會以 IAM 管理服務的服務實例來代表。
{:shortdesc}

## 何謂別名？
{: #what_is_alias}

別名是資源群組內的 IAM 管理服務，與組織或空間內的應用程式，兩者之間的連線。在 {{site.data.keyword.Bluemix_notm}} 主控台中，此連線（別名）會以服務實例來代表。您可以藉由修改代表您連線的服務實例來管理別名。

別名類似於符號鏈結，它會保留對遠端資源的參照，並支援整個平台中實例的交互作業能力和重複使用。例如，您可以在資源群組中建立服務的實例，然後從任何可用的地區中重複使用它，方法是在那些地區的組織或空間中建立別名。

下列規則適用於別名：

* 別名不需要額外費用，但每一個別名都會計入您組織中的配額。
* 在 {{site.data.keyword.Bluemix_notm}} 主控台中，每個空間只能建立一個別名。不過，使用 {{site.data.keyword.Bluemix_notm}} CLI 可以為每個空間建立多個別名。如需相關資訊，請參閱[使用資源和資源群組](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource)。
* 如果您具有許可權，則可以在 IAM 管理服務，與相同帳戶中任何空間、組織及地區內的任何應用程式之間，建立多個連線。
* 相同空間中從 IAM 管理服務實例到不同應用程式所建立的多個連線，將會使用相同的別名。
* 取消連結 IAM 管理服務實例*不會* 刪除代表別名的服務實例。
* 刪除 IAM 管理服務實例連接至的應用程式*不會* 刪除代表別名的實例。
* 刪除 IAM 管理服務實例*會刪除* 代表別名的服務實例。

## 在 IAM 管理服務與應用程式之間建立連線（別名）
{: #creating_alias}

若要將 IAM 管理服務實例連接至應用程式，請執行下列動作：

1. 移至儀表板。

2. 按一下應用程式的名稱，以開啟應用程式詳細資料視圖。

3. 按一下**連接現有項目**，然後從現有應用程式中進行選擇。或者，按一下**建立連線**，以建立要連接至的應用程式。

4. 指定**連線的存取角色**。此值會設定 IAM 服務存取角色。如需相關資訊，請參閱 [IAM 存取](/docs/iam?topic=iam-userroles)。

5. 您可以選擇性地提供**連線的服務 ID**，方法是容許 IAM 為您產生唯一值，或提供現有的服務 ID。如需相關資訊，請參閱[建立及使用服務 ID](/docs/iam?topic=iam-serviceids)。

6. 按一下**建立**。

## 檢視別名
{: #view_alias}

在 IAM 管理服務與應用程式之間建立連線之後，別名就會顯示在所連接應用程式的**連線**標籤上。此外，在資源清單上，別名會顯示為執行中的服務實例，而且只有在您開啟它時，才會包含**連線**標籤。

1. 移至您的資源清單。
2. 從**應用程式服務**表格，按一下服務實例的名稱，以開啟服務詳細資料視圖。如果其中只有**連線**標籤，則它是別名。

## 刪除別名
{: #delete_alias}

刪除別名的最簡單方式是刪除 IAM 管理的服務實例。不過，您可以維護 IAM 管理的服務實例，並改為直接刪除別名。

1. 移至您的資源清單。
2. 從**應用程式服務**表格，按一下服務實例的名稱，以開啟服務詳細資料視圖。如果其中只有**連線**標籤，則它是別名。
3. 刪除實例。

## 建立多個服務之間的連線
{: #multiple_services}

如需相關資訊，請參閱[在另一個服務中使用服務](/docs/resources?topic=resources-s2s_binding)。
