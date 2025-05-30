---
title: About SCIM for organizations
intro: 'With System for Cross-domain Identity Management (SCIM), administrators can automate the exchange of user identity information between systems.'
redirect_from:
  - /articles/about-scim
  - /github/setting-up-and-managing-organizations-and-teams/about-scim
  - /organizations/managing-saml-single-sign-on-for-your-organization/about-scim
versions:
  ghec: '*'
topics:
  - Organizations
  - Teams
---

>[!IMPORTANT] This article describes the SCIM integration for managing membership of organizations, available to **enterprises that use personal accounts on {% data variables.product.prodname_dotcom_the_website %}**. If you're looking for the SCIM integration for provisioning user accounts for **{% data variables.product.prodname_emus %}** or **{% data variables.product.prodname_ghe_server %}**, see [AUTOTITLE](/enterprise-cloud@latest/admin/managing-iam/provisioning-user-accounts-with-scim/configuring-scim-provisioning-for-users) or [AUTOTITLE](/enterprise-server@latest/admin/managing-iam/provisioning-user-accounts-with-scim/user-provisioning-with-scim-on-ghes).

## About SCIM for organizations

If your organization uses [SAML SSO](/organizations/managing-saml-single-sign-on-for-your-organization/about-identity-and-access-management-with-saml-single-sign-on), you can implement SCIM to add, manage, and remove organization members' access to {% data variables.product.github %}. For example, an administrator can deprovision an organization member using SCIM and automatically remove the member from the organization.

{% data reusables.saml.ghec-only %}

{% data reusables.scim.enterprise-account-scim %}

If you use SAML SSO without implementing SCIM, you won't have automatic deprovisioning. When organization members' sessions expire after their access is removed from the IdP, they aren't automatically removed from the organization. Authorized tokens grant access to the organization even after their sessions expire. If SCIM is not used, to fully remove a member's access, an organization owner must remove the member's access in the IdP and manually remove the member from the organization on {% data variables.product.prodname_dotcom %}.

{% data reusables.scim.changes-should-come-from-idp %}

## Supported identity providers

These identity providers (IdPs) are compatible with the {% data variables.product.github %} SCIM API for organizations. For more information, see [AUTOTITLE](/rest/scim).
* Microsoft Entra ID (previously known as Azure AD)
* Okta
* OneLogin

## About SCIM configuration for organizations

{% data reusables.scim.dedicated-configuration-account %}

Before you authorize the {% data variables.product.prodname_oauth_app %}, you must have an active SAML session. For more information, see [AUTOTITLE](/authentication/authenticating-with-saml-single-sign-on/about-authentication-with-saml-single-sign-on#about-oauth-apps-github-apps-and-saml-sso).

> [!NOTE]
> {% data reusables.scim.nameid-and-username-must-match %}

## Further reading

* [AUTOTITLE](/organizations/granting-access-to-your-organization-with-saml-single-sign-on/viewing-and-managing-a-members-saml-access-to-your-organization)
