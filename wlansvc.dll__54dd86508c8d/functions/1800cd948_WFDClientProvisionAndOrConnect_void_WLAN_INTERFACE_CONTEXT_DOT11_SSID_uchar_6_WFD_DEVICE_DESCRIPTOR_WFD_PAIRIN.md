# WFDClientProvisionAndOrConnect(void *,_WLAN_INTERFACE_CONTEXT *,_DOT11_SSID *,uchar (*)[6],_WFD_DEVICE_DESCRIPTOR *,_WFD_PAIRING_PARAMETERS_2 *,ulong,_DOT11_WFD_CHANNEL *,_DOT11_WPS_CONFIG_METHOD,_DOT11_WPS_DEVICE_PASSWORD_ID,_WFD_WPS_INFO *,ulong,uchar,uchar,WfdTelemSessionHandleInternal *)

- ea: `0x1800cd948`
- end: `0x1800cdc1d`
- name: `?WFDClientProvisionAndOrConnect@@YAKPEAXPEAU_WLAN_INTERFACE_CONTEXT@@PEAU_DOT11_SSID@@PEAY05EPEAU_WFD_DEVICE_DESCRIPTOR@@PEAU_WFD_PAIRING_PARAMETERS_2@@KPEAU_DOT11_WFD_CHANNEL@@W4_DOT11_WPS_CONFIG_METHOD@@W4_DOT11_WPS_DEVICE_PASSWORD_ID@@PEAU_WFD_WPS_INFO@@KEEPEAUWfdTelemSessionHandleInternal@@@Z`
- size: `725`
- prototype: `unsigned int __high(void *, struct _WLAN_INTERFACE_CONTEXT *, struct _DOT11_SSID *, unsigned __int8 (*)[6], struct _WFD_DEVICE_DESCRIPTOR *, struct _WFD_PAIRING_PARAMETERS_2 *, unsigned int, struct _DOT11_WFD_CHANNEL *, enum _DOT11_WPS_CONFIG_METHOD, enum _DOT11_WPS_DEVICE_PASSWORD_ID, struct _WFD_WPS_INFO *, unsigned int, unsigned __int8, unsigned __int8, struct WfdTelemSessionHandleInternal *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800efd78`
- `0x1801951c4`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1800893cc`
- `0x180089478`
- `0x1800c6774`
- `0x1800cd948`
- `0x1801a5cb4`
- `0x1801a5fb0`
- `0x1801a6278`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cdad9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cdb7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cdbc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cdad9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cdb7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cdbc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cda54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cda54`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800cdb6d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800cdb6d`

## pseudocode

```c

```
