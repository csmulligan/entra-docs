---
title: Microsoft Entra SSO integration with Contentstack
description: Learn how to configure single sign-on between Microsoft Entra ID and Contentstack.

author: jeevansd
manager: CelesteDG
ms.reviewer: CelesteDG
ms.service: active-directory
ms.subservice: saas-app-tutorial

ms.topic: how-to
ms.date: 12/11/2023
ms.author: jeedes

---

# Microsoft Entra SSO integration with Contentstack

In this tutorial, you'll learn how to integrate Contentstack with Microsoft Entra ID. When you integrate Contentstack with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Contentstack.
* Enable your users to be automatically signed-in to Contentstack with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

To integrate Microsoft Entra ID with Contentstack, you need:

* A Microsoft Entra subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Contentstack single sign-on (SSO) enabled subscription.

## Scenario description

In this tutorial, you configure and test Microsoft Entra SSO in a test environment.

* Contentstack supports both **SP and IDP** initiated SSO.
* Contentstack supports **Just In Time** user provisioning.

## Add Contentstack from the gallery

To configure the integration of Contentstack into Microsoft Entra ID, you need to add Contentstack from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Identity** > **Applications** > **Enterprise applications** > **New application**.
1. In the **Add from the gallery** section, type **Contentstack** in the search box.
1. Select **Contentstack** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

## Configure and test Microsoft Entra SSO for Contentstack

Configure and test Microsoft Entra SSO with Contentstack using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Contentstack.

To configure and test Microsoft Entra SSO with Contentstack, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-microsoft-entra-sso)** - to enable your users to use this feature.
    1. **[Create a Microsoft Entra ID test user](#create-a-microsoft-entra-id-test-user)** - to test Microsoft Entra single sign-on with B.Simon.
    1. **[Assign the Microsoft Entra ID test user](#assign-the-microsoft-entra-id-test-user)** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Contentstack SSO](#configure-contentstack-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Contentstack test user](#create-contentstack-test-user)** - to have a counterpart of B.Simon in Contentstack that is linked to the Microsoft Entra ID representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO in the Microsoft Entra admin center.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator) and browse to **Identity** > **Applications** > **Enterprise applications**.
1. Now click on **+ New Application** and search for Contentstack then click **Create**. Once created, click on the **Single sign-on** button from the left menu. 
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot shows how to edit Basic SAML Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier** text box, type a URL using one of the following patterns:

    |**Identifier**|
    |--------------|
    |`https://app.contentstack.com/<SSO_NAME>`|
    |`https://<ENVIRONMENT>-app.contentstack.com/<SSO_NAME>`|

    b. In the **Reply URL** text box, type a URL using one of the following patterns:

    |**Reply URL**|
    |-------------|
    |`https://app.contentstack.com/api/sso/saml2/<SSO_NAME>`|
    |`https://<ENVIRONMENT>-app.contentstack.com/api/sso/saml2/<SSO_NAME>`|

1. Perform the following step, if you wish to configure the application in **SP** initiated mode:

    In the **Sign on URL** text box, type a URL using one of the following patterns:

    |**Sign on URL**|
    |---------------|
    |`https://app.contentstack.com/#!/login/sso/<SSO_NAME>`|
    |`https://<ENVIRONMENT>-app.contentstack.com/#!/login/sso/<SSO_NAME>`|

	> [!NOTE]
	> These values are not real. Update these values with the actual Identifier, Reply URL and Sign on URL. You will get these values from the [**Configure Contentstack SSO**](#configure-contentstack-sso) section. If you have queriers, please contact [Contentstack support team](mailto:support@contentstack.com) or follow [Contentstack SSO guide](https://www.contentstack.com/docs/developers/single-sign-on).

1. Contentstack application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![Screenshot shows the image of attributes configuration.](common/default-attributes.png "Image")

1. In addition to above, Contentstack application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.
	
	| Name | Source Attribute|
	| ----- | --------------- |
    | first_name | user.givenname |
    | last_name | user.surname |
    | email | user.userprincipalname |
    | roles | user.assignedroles|

    > [!NOTE]
    > Please click [here](~/identity-platform/howto-add-app-roles-in-apps.md#app-roles-ui) to know how to configure Role in Microsoft Entra ID.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section, find **Certificate (Base64)** and select **Download** to download the certificate and save it on your computer.

	![Screenshot shows the Certificate download link.](common/certificatebase64.png "Certificate")

1. On the **Set up Contentstack** section, copy the appropriate URL(s) based on your requirement.

	![Screenshot shows to copy configuration URLs.](common/copy-configuration-urls.png "Metadata")

### Create a Microsoft Entra ID test user

In this section, you'll create a test user in the Microsoft Entra admin center called B.Simon.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [User Administrator](~/identity/role-based-access-control/permissions-reference.md#user-administrator).
1. Browse to **Identity** > **Users** > **All users**.
1. Select **New user** > **Create new user**, at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Display name** field, enter `B.Simon`.  
   1. In the **User principal name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Select **Review + create**.
1. Select **Create**.

### Assign the Microsoft Entra ID test user

In this section, you'll enable B.Simon to use Microsoft Entra single sign-on by granting access to Contentstack.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Identity** > **Applications** > **Enterprise applications** > **Contentstack**.
1. In the app's overview page, select **Users and groups**.
1. Select **Add user/group**, then select **Users and groups** in the **Add Assignment** dialog.
   1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
   1. If you are expecting a role to be assigned to the users, you can select it from the **Select a role** dropdown. If no role has been set up for this app, you see "Default Access" role selected.
   1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure Contentstack SSO

1. Log in to your Contentstack company site as an administrator.

1. Go to the Organization Settings page and click
on the **Single Sign-On** tab on the left menu.

1. In the **Single Sign-On** page, navigate to **SSO Configuration** section and perform the following steps:

    1. Enter a valid **SSO Name** and click **Create**.
        
        ![Screenshot shows settings of the configuration.](./media/contentstack-tutorial/name.png "SSO Provider")

    1. Copy **Assertion Consumer Service URL** and paste in the **Reply URL** textbox in the **Basic SAML configuration** section in Microsoft Entra admin center.

    1. Copy **Entity ID** and paste in the **Identifier** textbox in the **Basic SAML configuration** section in Microsoft Entra admin center and click **Next**.

        ![Screenshot shows the configuration values.](./media/contentstack-tutorial/values.png "Identifier")

1. Navigate to **Idp Configuration** tab and perform the following steps:

    ![Screenshot shows the login values from Identity.](./media/contentstack-tutorial/admin.png "Identity Provider")

    1. In the **Single Sign-On Url** textbox, paste the **Login URL**, which you have copied from the Microsoft Entra admin center.

    1. Open the downloaded **Certificate (Base64)** from Microsoft Entra admin center and upload into the **Certificate** field.

    1. Click **Next**.

1. In the **User Management** section, enable [**Strict Mode**](https://www.contentstack.com/docs/developers/single-sign-on/set-up-sso-in-contentstack#strict-mode) and click **Next**.

    ![Screenshot shows User Management section.](./media/contentstack-tutorial/manage.png "Users")

1. In the **Test & Enable** section, click **Enable SSO** button and click **Next**.

    ![Screenshot shows the enable testing section.](./media/contentstack-tutorial/test.png "Testing")

1. Once this is enabled, users can access the organization through SSO. If needed, you can also **Disable SSO** from this page as well.

    ![Screenshot shows disabling the access page.](./media/contentstack-tutorial/access.png "Page")

    1. Copy **SSO One-Click URL** and paste in the **Sign on URL** textbox in **Basic SAML configuration** section in the Microsoft Entra admin center, if you wish to configure the application in SP initiated mode.

> [!NOTE]
> Please refer [Contentstack SSO guide](https://www.contentstack.com/docs/developers/single-sign-on) for more information.
        
### Create Contentstack test user

In this section, a user called Britta Simon is created in Contentstack. Contentstack supports just-in-time user provisioning, which is enabled by default. There is no action item for you in this section. If a user doesn't already exist in Contentstack, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options.
 
#### SP initiated:
 
* Click on **Test this application** in Microsoft Entra admin center. This will redirect to Contentstack Sign on URL where you can initiate the login flow.  
 
* Go to Contentstack Sign-on URL directly and initiate the login flow from there.
 
#### IDP initiated:
 
* Click on **Test this application** in Microsoft Entra admin center and you should be automatically signed in to the Contentstack for which you set up the SSO.
 
You can also use Microsoft My Apps to test the application in any mode. When you click the Contentstack tile in the My Apps, if configured in SP mode you would be redirected to the application sign-on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Contentstack for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Next steps

Once you configure Contentstack you can enforce session control, which protects exfiltration and infiltration of your organization's sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).