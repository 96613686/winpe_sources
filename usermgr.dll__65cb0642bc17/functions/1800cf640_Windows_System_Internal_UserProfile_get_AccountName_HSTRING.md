# Windows::System::Internal::UserProfile::get_AccountName(HSTRING__ * *)

- ea: `0x1800cf640`
- end: `0x1800cf786`
- name: `?get_AccountName@UserProfile@Internal@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `326`
- prototype: `int(Windows::System::Internal::UserProfile *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000acdc`
- `0x180012890`
- `0x180015250`
- `0x1800179c0`
- `0x18002799c`
- `0x1800cf640`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800cf6c0`
- `msvcrt!_wcsicmp` at `0x1800cf6c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cf68d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cf68d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf6a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf6b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf6a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf6b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800cf6d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800cf6e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800cf6d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800cf6e5`

## string_xrefs

- `0x1800cf74a`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800cf75f`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800cf773`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c

```
