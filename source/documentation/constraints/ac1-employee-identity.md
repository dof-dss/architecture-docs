## AC1 - Employee identity management source is Active Directory exposing OpenID Connect and SAML-P endpoints

**Rationale**

At present NI Government is using Active Directory as the source identity management solution for Government employees. Active Directory Federation Services is used to federate-in partner employees requiring access to Government systems.

**Implication**

Active Directory and solutions depending on its data must be used as the employee identity source going forward. SAML-P is to be used as the most prominent protocol for authentication in enterprises - all employee facing solutions exposing UI should use [SAML-P](https://en.wikipedia.org/wiki/SAML_2.0) or [OpenID Connect](https://openid.net/connect) as authentication protocols.
