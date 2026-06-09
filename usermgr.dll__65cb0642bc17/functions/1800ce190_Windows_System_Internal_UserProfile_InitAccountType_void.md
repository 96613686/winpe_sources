# Windows::System::Internal::UserProfile::InitAccountType(void)

- ea: `0x1800ce190`
- end: `0x1800ce274`
- name: `?InitAccountType@UserProfile@Internal@System@Windows@@AEAAXXZ`
- size: `228`
- prototype: `void __fastcall __noreturn(Windows::System::Internal::UserProfile *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ceb24`
- `0x1800cec24`

## callees

- `0x18000acdc`
- `0x180014e7c`
- `0x180014e9c`
- `0x18004e4e8`
- `0x18004e58c`
- `0x18004ea38`
- `0x1800ce190`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ce1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ce246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ce1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ce246`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ce1d5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800ce1d5`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800ce200`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800ce200`

## string_xrefs

- `0x1800ce1e4`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800ce212`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800ce262`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c

```
