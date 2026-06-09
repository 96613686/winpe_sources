# Windows::System::User::GetLogonSid(HSTRING__ * *)

- ea: `0x180008070`
- end: `0x18000819e`
- name: `?GetLogonSid@User@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `302`
- prototype: `int(Windows::System::User *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008070`
- `0x1800088e8`
- `0x1800179c0`
- `0x18004a338`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800080c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000810f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800080c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000810f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000808c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000808c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180008125`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180008125`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800080f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180008169`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180008180`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800080f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180008169`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180008180`

## string_xrefs

- `0x1800080a1`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`
- `0x18000813b`: `onecore\ds\security\umstartup\usermgr\lib\user.cpp`

## pseudocode

```c

```
