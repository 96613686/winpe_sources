# FaultInIEFeature

- ea: `0x18007c9b0`
- end: `0x18007cc38`
- name: `FaultInIEFeature`
- size: `648`
- prototype: `HRESULT __stdcall(HWND hWnd, uCLSSPEC *pClassSpec, QUERYCONTEXT *pQuery, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007b6e0`
- `0x1800f5be0`

## callees

- `0x180028510`
- `0x18002fee0`
- `0x18007c9b0`
- `0x18007cc40`
- `0x1800be9f8`
- `0x1801285e6`
- `0x180128660`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18007ca11`
- `msvcrt!memcpy_s` at `0x18007cae6`
- `msvcrt!memcpy_s` at `0x18007ca11`
- `msvcrt!memcpy_s` at `0x18007cae6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007cb9d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007cbb2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007cb9d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007cbb2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007cb7f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007cb7f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetUSValueA` at `0x18007cb34`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegGetUSValueA` at `0x18007cb34`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x18007cbcd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x18007cbcd`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x18007cc0c`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x18007cc0c`
- `ext-ms-win-ntuser-window-l1-1-3!GetLastActivePopup` at `0x18007cbe1`
- `ext-ms-win-ntuser-window-l1-1-3!GetLastActivePopup` at `0x18007cbe1`

## string_xrefs

- `0x18007cb16`: `Software\Microsoft\Active Setup\Declined Install On Demand IEv5`

## pseudocode

```c

```
