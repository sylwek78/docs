---
title: Disabling authentication for Enterprise Managed Users
allowTitleToDifferFromFilename: true
shortTitle: Disable authentication
intro: 'You can disable SAML or OIDC single sign-on (SSO) authentication for {% data variables.product.prodname_emus %} by using a recovery code to sign in as the setup user.'
versions:
  ghec: '*'
type: overview
topics:
  - Accounts
  - Authentication
  - Enterprise
  - SSO
permissions: 'The setup user can disable SAML or OIDC authentication for {% data variables.product.prodname_emus %}.'
redirect_from:
  - /admin/identity-and-access-management/using-enterprise-managed-users-for-iam/disabling-authentication-for-enterprise-managed-users
  - /admin/identity-and-access-management/configuring-authentication-for-enterprise-managed-users/disabling-authentication-for-enterprise-managed-users
  - /admin/identity-and-access-management/configuring-authentication-for-enterprise-managed-users/disabling-authentication-and-provisioning-for-enterprise-managed-users
---

## About disabled authentication for {% data variables.product.prodname_emus %}

After you disable SAML or OIDC authentication for your enterprise, the following effects apply:

* All external identities for the enterprise, and associated email addresses for {% data variables.enterprise.prodname_managed_users %}, will be removed. For more information, see [AUTOTITLE](/admin/user-management/managing-users-in-your-enterprise/viewing-and-managing-a-users-saml-access-to-your-enterprise).
* All {% data variables.enterprise.prodname_managed_users %} will be suspended. The suspended accounts will not be renamed. For more information, see [AUTOTITLE](/admin/user-management/managing-users-in-your-enterprise/viewing-people-in-your-enterprise#viewing-suspended-members).
* All {% data variables.product.pat_generic_plural %} and SSH keys associated with {% data variables.enterprise.prodname_managed_users %} will be deleted.
* All of the external groups provisioned by SCIM will be deleted. For more information, see [AUTOTITLE](/admin/identity-and-access-management/using-enterprise-managed-users-for-iam/managing-team-memberships-with-identity-provider-groups).

If you later reconfigure authentication for the enterprise, external groups must be reprovisioned via SCIM, and {% data variables.enterprise.prodname_managed_users %} must be reprovisioned before users can sign in.

> [!NOTE]
> When a {% data variables.enterprise.prodname_managed_user %} is suspended, the user's avatar is permanently deleted. If you reprovision the user, the user will need to reupload their avatar.

If you want to migrate to a new identity provider (IdP) or tenant rather than disabling authentication entirely, see [AUTOTITLE](/admin/identity-and-access-management/using-enterprise-managed-users-for-iam/migrating-your-enterprise-to-a-new-identity-provider-or-tenant).

## Disabling authentication

> [!WARNING]
> Disabling authentication and provisioning will prevent your enterprise's {% data variables.enterprise.prodname_managed_users %} from signing in to access your enterprise on {% data variables.product.github %}.

{% data reusables.emus.sign-in-as-setup-user %}
1. Attempt to access your enterprise account, and use a recovery code to bypass SAML SSO or OIDC. For more information, see [AUTOTITLE](/admin/identity-and-access-management/managing-recovery-codes-for-your-enterprise/accessing-your-enterprise-account-if-your-identity-provider-is-unavailable).
{% data reusables.enterprise-accounts.access-enterprise-emu %}
{% data reusables.enterprise-accounts.identity-provider-tab %}
{% data reusables.enterprise-accounts.sso-configuration %}
1. Next to "SAML single sign-on" or "OIDC single sign-on", click to deselect **SAML single sign-on** or **OIDC single sign-on**.
1. To confirm, click **Disable SAML single sign-on** or **Disable OIDC single sign-on**.
