# Windows::System::Internal::Implementation::UserProfileManager::DeleteUserFromRegistry(uint)

- ea: `0x180018bc0`
- end: `0x180018d0b`
- name: `?DeleteUserFromRegistry@UserProfileManager@Implementation@Internal@System@Windows@@AEAAJI@Z`
- size: `331`
- prototype: `int(Windows::System::Internal::Implementation::UserProfileManager *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060f48`
- `0x180062820`
- `0x1800c2068`
- `0x1800c2d18`

## callees

- `0x18000ce48`
- `0x180018bc0`
- `0x180034454`
- `0x1800344b8`
- `0x18004a9cc`
- `0x18004e75c`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x180018c23`
- `msvcrt!_ui64tow_s` at `0x180018c23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018cb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018cb9`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180018cda`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180018cda`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180018cd0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180018cd0`

## string_xrefs

- `0x180018c7f`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`

## pseudocode

```c

```
