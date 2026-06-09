# AppDefaultHelpers::CheckCredentials(HSTRING__ *,HSTRING__ *,Windows::UI::WindowId,Windows::Internal::ApplicationDefaults::CheckCredentialsResult *)

- ea: `0x180381dd0`
- end: `0x180382598`
- name: `?CheckCredentials@AppDefaultHelpers@@UEAAJPEAUHSTRING__@@0UWindowId@UI@Windows@@PEAW4CheckCredentialsResult@ApplicationDefaults@Internal@5@@Z`
- size: `1992`
- prototype: `int __high(HSTRING, HSTRING, struct Windows::UI::WindowId, enum Windows::Internal::ApplicationDefaults::CheckCredentialsResult *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001adbc`
- `0x180038f50`
- `0x180044320`
- `0x180077880`
- `0x18007ea3c`
- `0x180083c94`
- `0x1800ff160`
- `0x1801720d0`
- `0x18017fe2c`
- `0x1801865e0`
- `0x180186610`
- `0x180370e34`
- `0x180381dd0`
- `0x1803825a0`
- `0x1803825c4`
- `0x180389834`
- `0x1803b1f60`
- `0x18054b99c`
- `0x18056b1a0`
- `0x18056b308`
- `0x18056b344`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18038225e`
- `ntdll!RtlNtStatusToDosError` at `0x18038225e`
- `ntdll!RtlInitString` at `0x180381e36`
- `ntdll!RtlInitString` at `0x180381e54`
- `ntdll!RtlInitString` at `0x180381e36`
- `ntdll!RtlInitString` at `0x180381e54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180382172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180382172`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x1803822b5`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x1803822b5`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x1803820fd`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x1803821a6`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x1803820fd`
- `ext-ms-win-security-credui-l1-1-0!CredPackAuthenticationBufferW` at `0x1803821a6`
- `Secur32!LsaFreeReturnBuffer` at `0x180382323`
- `Secur32!LsaFreeReturnBuffer` at `0x180382323`
- `Secur32!LsaLogonUser` at `0x1803823a2`
- `Secur32!LsaLogonUser` at `0x1803823a2`
- `Secur32!LsaLookupAuthenticationPackage` at `0x180381ebe`
- `Secur32!LsaLookupAuthenticationPackage` at `0x180381ebe`
- `Secur32!LsaConnectUntrusted` at `0x180381e92`
- `Secur32!LsaConnectUntrusted` at `0x180381e92`
- `Secur32!LsaDeregisterLogonProcess` at `0x180381e75`
- `Secur32!LsaDeregisterLogonProcess` at `0x180381e75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180382225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038223b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180382225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18038223b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180381f2c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180382036`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180381f2c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180382036`

## pseudocode

```c

```
