## [0.18.0] - 2023-01-14
#### Dependencies

  * [[#62](https://github.com/swelham/ueberauth_microsoft/pull/62)] Updated `oauth2` from `2.0.1` to `2.1.0`.

## [0.17.0] - 2022-10-04
#### Dependencies

  * [[#53](https://github.com/swelham/ueberauth_microsoft/pull/53)] Updated `oauth2` from `2.0.0` to `2.0.1`.
  * [[#58](https://github.com/swelham/ueberauth_microsoft/pull/58)] Updated `ueberauth` from `0.7.0` to `0.10.3`.

## [0.16.0] - 2022-08-23
#### Enhancements

  * [[#55](https://github.com/swelham/ueberauth_microsoft/pull/55)] Allow dynamic configs ([@ryanzidago](https://github.com/ryanzidago))

## [0.15.0] - 2022-04-06
#### :boom: Breaking Changes

  * [[#48](https://github.com/swelham/ueberauth_microsoft/pull/48)] Parse scopes to match Ueberauth typespec ([@bismark](https://github.com/bismark))

This change updates the `Ueberauth.Auth.Credentials.scopes` attribute to a list of strings instead of a comma separated string. This aligns the attribute with the Ueberauth typespec and other Ueberauth strategies.

To migrate to this version, any code expecting `Credentials.scopes` to be a string will need to be updated to expect a list of strings.

```elixir
# Previous format
%Ueberauth.Auth{
  credentials: %Ueberauth.Auth.Credentials{
    scopes: "scope1,scope2",
    ...
  },
  ...
}

# New format
%Ueberauth.Auth{
  credentials: %Ueberauth.Auth.Credentials{
    scopes: ["scope1","scope2"],
    ...
  },
  ...
}
```