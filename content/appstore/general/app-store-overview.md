---
title: "Marketplace Overview"
category: "General Info"
menu_order: 10
description: "Presents an overview of how to find and use content from the Mendix Marketplace."
tags: ["marketplace",  "widget", "connector", "module", "partner"]
aliases:
    - /community/app-store/app-store-overview.html
    - /developerportal/app-store/app-store-overview.html
---

## 1 Introduction

The [Mendix Marketplace](https://appstore.home.mendix.com/index3.html) is a vibrant marketplace containing complete sample apps that can be used right away as well as various components (connectors, widgets, and modules) that can be used to build custom apps more quickly. In the Mendix Marketplace, you can browse all the content, get what you need, and share the content you have created.

This document describes the different sections of the Mendix Marketplace.

## 2 Marketplace Home Page {#home}

The home page of the Mendix Marketplace has three main tabs at the top:

* **Discover** – the home page, where you can browse various component categories and filter what is displayed
* **My Marketplace** – click this to go to [My Marketplace](#my-marketplace)
* **{Your company's private Marketplace page}** – click this to go to your [Company Content](#company-content)

![](attachments/app-store-overview/home-page.jpg)

<a name="catalog"></a>It also presents various content catalogs:

| Catalog | Description |
| --- | --- |
| **Get Studio Pro** | All the versions of [Studio Pro](/releasenotes/studio-pro/) available for download. |
| [Widgets](/appstore/widgets/) | Single user-interface elements that can be configured, such as containers, drop-down menus, and buttons. |
| [Connectors](/appstore/connectors/) | Connectors can be used to connect your Mendix app with other systems.  |
| [Modules](/appstore/modules/) | These elements enable new functionality with accompanying domain models and security options. |
| **App Design** | Start building your app based on a [layout](/refguide/layout) that is ready to use with commons structures and widgets or a [theme](/appstore/themes/) that contains styling options you can apply for different elements and devices. |
| **Solutions** | Fully-formed solutions for your apps. |

The following filter options are also available:

* **Tags**
* **Ratings**

## 3 Component Details Page {#details}

Clicking the tile of a Marketplace component will bring you to its details page with the sections described below.

![](attachments/app-store-overview/component-details.jpg)

### 3.1 Header & Usage

The header for each component presents the following details:

* The name and category of the component
* The review average (in stars) and the number of reviews
* The number of times the component has been downloaded
* <a name="saved"></a>The **Add to Saved** button which, when clicked, will add the component to the list on the [Dashboard](#dashboard) and [Saved](#saved-components) pages
* The **Share** button, which allows you to copy the URL of the component and share it to your networks
* **Download** – click this to download the component
	* This is only available for components that have a file attached (meaning, all shared Studio Pro components, but not promotions)
	* The best practice is to download a component from the Marketplace that is accessible in Studio Pro, because it then downloads directly into Studio Pro (for details on importing downloaded Marketplace content into Studio Pro, see [How to Import & Export Objects](/howto/integration/importing-and-exporting-objects))

<a name="usage"></a>The **Usage** section presents  the following information (depending on the type of component):

* The latest **Version** number of the component
* The Studio Pro version that the component **Requires** to work
* The type of [license](share-app-store-content#license) for the component

The **Publisher** section presents the name of the company who created the component as well as the **Date** when the component was first published.

The **Developers** section presents the names of the developers who most recently updated the component, with links to their [Mendix Profile](/developerportal/mendix-profile/).

The **Support** section presents the category of support Mendix offers for the component (for more details, see [Marketplace Content Support](app-store-content-support)).

* A **GitHub** link, which will take you to the GitHub source files of the component

### 3.2 Tabs

The details page for a component presents the following item information tabs:

*  **Overview** – contains the following sections:
	* **Description** – a description of the component
	* **Screenshots** – screenshots of the component
	* **User Reviews** – user reviews of the component; to leave a review for the component, click **Add Review**, which will open a section where you can add text, rate the component, and submit the review (your reviews will be listed on your [Reviews](#my-reviews) page); if you are a developer of the component, you can **Reply** to a review
*  **Documentation** – can include details on typical use cases, features and limitations, dependencies, installation and configuration, and frequently asked questions
	* [Platform-supported](app-store-content-support#category) components are documented in the various categories of this *Marketplace Guide*
	* Click **Edit documentation** to open a text editor where you can edit the Marketplace component's documentation
* **Pricing**  – lists the pricing options (only for paid components)
* **Releases** – lists all the versions of the component (any of which can be downloaded by clicking **Download**) along with details like the **Framework version** and the **UUID** (which can be used in the [CreateNewApp operation](/apidocs-mxsdk/apidocs/projects-api#createnewapp) in the *Projects API*): 

## 4 My Marketplace {#my-marketplace}

### 4.1 Dashboard {#dashboard}

The **Dashboard** page presents your Marketplace activity:

* Your numbers for [Published Content](#content) and [Submitted Reviews](#my-reviews)
* [Notifications](#notifications) on components you created and favorited
* Content [Drafts](#drafts) you have created
* Your content [Favorites](#saved)

![](attachments/app-store-overview/my_app_store.png)

### 4.2 My Content {#content}

On this page, you can see the Marketplace content for which you have created at least one version:

![](attachments/app-store-overview/my-content.png)

You may see the **Company only** label on a component, which means it is your company's private Marketplace content (for details on how this is configured, see the [Adding New Marketplace Content](share-app-store-content#private-app-store) section of *How to Share Marketplace Content*). This content can be shared with [guests](#guests).

In addition, you may see a label on a component name for the [user group](#user-groups) to which the component is assigned as user group [content](#content).

To see the component's [details](#details) page, click **View**.

At the top of this page, there is a check box to **Receive notification** when there is a change made to your components (for example, a new version is published, or a component is unpublished). When checked, you will receive email notifications if a component status has changed. Clear this box to stop receiving these emails.

#### 4.2.1 Managing a Component {#manage}

Click **Manage** to manage the component:

![](attachments/app-store-overview/content-management.png)

On this page, you will see the following buttons:

* **Create new draft version** – click this to create a new draft version of the component
	* Only one draft version of a component can exist at a time, so when one draft version is in progress, another draft cannot be initiated – if there is a draft version in progress, click **View draft** to see it
	* For more information on creating a draft version, see the [Updating Existing Marketplace Content](share-app-store-content#updating) section of *How to Share Marketplace Content*
* **Unpublish** – click this to remove one version or all versions of the component
	* If the component is protected [content](#content) from a [user group](#user-groups), a group [member](#members) can unpublish any version
	* If the component is not the protected content of a user group, you can only unpublish a version that you have published yourself
	* Select **Unpublish all versions** to remove all versions of the component
* **Edit** – click this to edit the component (for details on editing, see the [Adding New Marketplace Content](share-app-store-content#adding) section of *How to Share Marketplace Content*)

### 4.3 Drafts {#drafts}

This page contains drafts of Marketplace content you have started:

![](attachments/app-store-overview/drafts.png)

Click the name of a Marketplace component to be taken to the [DRAFT](share-app-store-content#adding) page, where you can continue editing the component details.

Click **Delete** to delete a draft.

Click **Withdraw** to withdraw the content from the review process after you have [submitted it for approval](share-app-store-content#approval), which will return the content to the draft state:

![](attachments/app-store-overview/draft-withdraw.png)

### 4.4 Shared with Me {#shared-with-me}

This page contains private content shared with you by other companies who have marked you as a [guest](#guests):

![](attachments/app-store-overview/shared-with-me.png)

### 4.5 Reviews {#my-reviews}

This page contains reviews of [Your content](#content) by other users as well as **Your reviews** that you have written of other content:

![](attachments/app-store-overview/your-reviews.png)

At the top of this page, there are check boxes to **Receive notification** of reviews added to your components and of replies to your reviews. When checked, you will receive a relevant email about the review and/or reply. Clear these check boxes to stop receiving emails.

### 4.6 Notifications {#notifications}

This page presents a history of notifications on content you have contributed to:

![](attachments/app-store-overview/notifications.png)

### 4.7 Favorites {#saved-components}

This page presents the Marketplace content you have [favorited](#saved):

![](attachments/app-store-overview/favorites.png)

When the **Subscribe** box is checked next to a favorite component, you will receive email notifications when new versions of that component are published. Clear the check box if you do not want to receive these notifications.

## 5 Your Company's Marketplace

### 5.1 Company Content {#company-content}

On this page, you can see all the content your company has published:

![](attachments/app-store-overview/company-content.png)

The **Manage** button is available to you if one of the following conditions is true:

* The component is not assigned to any [user groups](#user-groups) (in which case it can be managed by anyone in the company)
* The component is assigned to a user group, and you are a [member](#members) of that group
* You are a [Mendix Admin](/developerportal/control-center/#company) of the company that published the component

To manage a component, click **Manage** (for more information, see the [Managing a Component](#manage) section above).

To see the component's [details](#details) page, click **View**.

### 5.2 Reviews

This page contains reviews of **Your company's content** as well as **Your company's reviews** that users from your company have written of other content.

![](attachments/app-store-overview/your-company-reviews.png)

### 5.3 User Groups {#user-groups}

You can configure user groups for various levels of access to your company content. The available configuration tabs for each user group page are described in the sections below.

{{% alert type="info" %}}
The **User Groups** menu item and page are visible to all users. However, only [Mendix Admins](/developerportal/control-center/#company) can create and delete user groups. Both [Group Admins](#members) and Mendix Admins can manage user groups.
{{% /alert %}}

#### 5.3.1 Members Tab {#members}

On this tab, you can enter the email address of a Mendix Platform user from your company and click **Add Member** to add them as a user group member. User group members can manage the [content](#content) assigned to the group.

Once a member is added, you can select their permission level: **Member** or **Group Admin**. A Group Admin can manage the user group.

![](attachments/app-store-overview/members.png)

To remove a member, click **Remove** next to their name.

#### 5.3.2 Guests Tab {#guests}

A guest is a Mendix Platform user from outside your organization who can download the selected private [Content](#content) of this group. To add a guest, enter their email address in the box and click **Add Guest**:

![](attachments/app-store-overview/guests.png)

The guest will receive an email notifying them of access to the private content. They can then see all the private Marketplace content shared with them in their [Shared with Me](#shared-with-me) page.

{{% alert type="info" %}}
The guest must be a registered Mendix Platform user; otherwise, they will not be able to access the shared content.
{{% /alert %}}

To remove a guest, click **Remove**.

#### 5.3.3 Content Tab {#content}

On this tab, you can assign content to this user group that can only be managed by members of this group. To assign a component to a user group, click **Assign Content** and select a company Marketplace component from the dialog box:

![](attachments/app-store-overview/group-content.png)

{{% alert type="info" %}}
A Mendix Marketplace component can only be assigned to one user group at a time. If a component is already assigned to another user group, it will not appear in this dialog box.
{{% /alert %}}

To manage a component assigned to the user group, click **Manage** (for more information, see the [Managing a Component](#manage) section above).

To see the component's [details](#details) page, click **View**.

To remove a component from the user group, click **Remove**.

[Group Admins](#members) and [Mendix Admins](/developerportal/control-center/#company) can check the **Allow guests to download** box of this component can be downloaded by [guests](#guests).

#### 5.3.4 Settings Tab

On this tab, you can enter a **Name** and **Description** for the user group.

To delete a group, a Mendix Admin can click **Delete Group**.

## 6 Service Management Dashboard {#service-management}

To use an app service in your app, you need binding keys. You can create and manage these keys on the **Service Management** dashboard.

### 6.1 Creating Binding Keys

To create binding keys, go to the **Service Management** dashboard, select a **Product**, and click **Generate Keys** at the bottom of the page:

![](attachments/app-store-overview/binding-keys-1.png)

In the **Provide a Name for Your App Connection** field of the **Connect Your Service** dialog box, enter a name for the connection:

![](attachments/app-store-overview/binding-keys-2.png)

After you click **Create Keys**, a page will appear with your keys – **clientID**, **TokenURL**, and **clientSecret**:

![](attachments/app-store-overview/binding-keys-3.png)

Click **Copy** for each key and manually save the keys somewhere safe, as you will not be able to access them again.

{{% alert type="warning" %}}
Once you close this page of the Service Management dashboard, you will not be able to retrieve the keys again.
{{% /alert %}}

To use the binding keys, see the [Using the Binding Keys](#using) section below.

Click **Return to the overview** to go to the main page of the Service Management dashboard. On the main page, you can hover over the **Binding Keys** column to see the binding keys that have already been created as well as to delete a binding key:

![](attachments/app-store-overview/binding-keys-4.png)

You can also highlight a product and click **Manage** to go to the app service provider's configuration page, where you can do further app service-specific configuration:

![](attachments/app-store-overview/binding-keys-5.png)

{{% alert type="info" %}}
This additional management option is only available for specific app services where necessary.
{{% /alert %}}

### 6.2 Using the Binding Keys {#using}

When you are developing your app, set the app service's **clientID** and **clientSecret** as [constants](/refguide/configuration#constants) in the [App Settings](/refguide/project-settings).

For details on using binding keys in the MindSphere app service, see the [Authenticating MindSphere REST Calls](/partners/siemens/mindsphere-app-service#authenticating) section of *MindSphere App Service*.

## 7 Read More

* [How to Use Marketplace Content in Studio Pro](app-store-content)
* [How to Share Marketplace Content](share-app-store-content)
* [Marketplace Content Support](app-store-content-support)
