[[Gitlab-Runner]]

Configuration
```
external_url 'https://gitlab.skycalhl.duckdns.org'
gitlab_rails['omniauth_providers'] = [
  {
    name: "openid_connect", # do not change this parameter
    label: "Azure AD", # optional label for login button, defaults to "Openid Connect"
    args: {
      name: "openid_connect",
      scope: ["openid","profile","email"],
      response_type: "code",
      issuer: "https://login.microsoftonline.com/<tenantid>/v2.0",
      discovery: true,
      client_auth_method: "query",
      uid_field: "2",
      send_scope_to_token_endpoint: "false",
      pkce: true,
      client_options: {
        identifier: "a5ced9f3-1abc-4d75-8285-ae684621ad3b",
        secret: "<client secret>",
        redirect_uri: "https://gitlab.skycalhl.duckdns.org/users/auth/openid_connect/callback" # configure the same on app reg 
      }
    }
  }
]
```