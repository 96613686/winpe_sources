# Windows::System::Internal::Implementation::UserProfileManager::ReadUsersFromRegistry(void)

- ea: `0x1800c2d18`
- end: `0x1800c303c`
- name: `?ReadUsersFromRegistry@UserProfileManager@Implementation@Internal@System@Windows@@AEAAJXZ`
- size: `804`
- prototype: `__int64 __fastcall(Windows::System::Internal::Implementation::UserProfileManager *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180087498`

## callees

- `0x18000ce48`
- `0x180012890`
- `0x180015250`
- `0x180018bc0`
- `0x180025cd4`
- `0x18002799c`
- `0x18003d38c`
- `0x18004e508`
- `0x18004e75c`
- `0x1800616c0`
- `0x1800c2ae0`
- `0x1800c2d18`
- `0x1800c32ac`
- `0x1800c354c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c2e83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c2e83`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800c2e53`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800c2e53`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c2f05`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c2f05`

## string_xrefs

- `0x1800c3000`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c3014`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x1800c3029`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`

## pseudocode

```c

```
