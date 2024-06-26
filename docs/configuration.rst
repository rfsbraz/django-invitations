Configuration
=============


General settings
----------------

``INVITATIONS_INVITATION_EXPIRY``
*********************************

Type: Integer

Default: ``3``

How many days before the invitation expires.

----

``INVITATIONS_CONFIRM_INVITE_ON_GET``
*************************************

Type: Boolean

Default: ``True``

If confirmations can be accepted via a ``GET`` request.

----

``INVITATIONS_ACCEPT_INVITE_AFTER_SIGNUP``
******************************************

Type: Boolean

Default: ``False``

If ``True``, invitations will be accepted after users finish signup.
If ``False``, invitations will be accepted right after the invitation link is clicked.
Note that this only works with Allauth for now, which means ``ACCOUNT_ADAPTER`` has to be
``invitations.models.InvitationsAdapter``.

----

``INVITATIONS_GONE_ON_ACCEPT_ERROR``
************************************

Type: Boolean

Default: ``True``

If ``True``, return an HTTP 410 GONE response if the invitation key
is invalid, or the invitation is expired or previously accepted when
accepting an invite. If `False`, display an error message and redirect on
errors:

* Redirects to ``INVITATIONS_SIGNUP_REDIRECT`` on an expired key
* Otherwise, redirects to ``INVITATIONS_LOGIN_REDIRECT`` on other errors.

----

``INVITATIONS_ALLOW_JSON_INVITES``
**********************************

Type: Boolean

Default: ``False``

Expose a URL for authenticated posting of invitees

----

``INVITATIONS_SIGNUP_REDIRECT``
*******************************

Type: String

Default: ``"account_signup"``

URL name of your signup URL.

----

``INVITATIONS_LOGIN_REDIRECT``
******************************

Type: String

Default: ``LOGIN_URL`` from Django settings

URL name of your login URL.

----

``INVITATIONS_ADAPTER``
***********************

Type: String

Default: ``"invitations.adapters.BaseInvitationsAdapter"``

Used for custom integrations. Set this to ``ACCOUNT_ADAPTER`` if using django-allauth.

----

``INVITATIONS_EMAIL_MAX_LENGTH``
********************************

Type: Integer

Default: ``254``

If set to ``None`` (the default), invitation email max length will be set up to 254. Set this to an integer value to set up a custome email max length value.

----

``INVITATIONS_EMAIL_SUBJECT_PREFIX``
************************************

Type: String or None

Default: ``None``

If set to ``None`` (the default), invitation email subjects will be prefixed with the name of the current Site in brackets (such as `[example.com]`). Set this to a string to for a custom email subject prefix, or an empty string for no prefix.

----

``INVITATIONS_INVITATION_MODEL``
********************************

Type: String

Default: ``"invitations.Invitation"``

App registry path of the invitation model used in the current project, for customization purposes.

----

``INVITATIONS_INVITE_FORM``
***************************

Type: String

Default: ``"invitations.forms.InviteForm"``

Form class used for sending invites outside admin.

----

``INVITATIONS_ADMIN_ADD_FORM``
******************************

Type: String

Default: ``"invitations.forms.InvitationAdminAddForm"``

Form class used for sending invites in admin.

----

``INVITATIONS_ADMIN_CHANGE_FORM``
*********************************

Type: String

Default: ``"invitations.forms.InvitationAdminChangeForm"``

Form class used for updating invites in admin.

----

``INVITATIONS_CONFIRMATION_URL_NAME``
*************************************
Type: String

Default: ``"invitations:accept-invite"``

Invitation confirmation URL

Allauth related settings
------------------------

``INVITATIONS_INVITATION_ONLY``
*******************************

Type: Boolean

Default: ``False``

If the site is invite only, or open to all (only relevant when using allauth).
