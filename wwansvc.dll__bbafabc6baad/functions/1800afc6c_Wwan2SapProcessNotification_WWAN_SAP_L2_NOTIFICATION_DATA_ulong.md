# Wwan2SapProcessNotification(WWAN_SAP *,_L2_NOTIFICATION_DATA *,ulong)

- ea: `0x1800afc6c`
- end: `0x1800afed8`
- name: `?Wwan2SapProcessNotification@@YAHPEAUWWAN_SAP@@PEAU_L2_NOTIFICATION_DATA@@K@Z`
- size: `620`
- prototype: `__int64 __fastcall(struct WWAN_SAP *, struct _L2_NOTIFICATION_DATA *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800aa998`

## callees

- `0x1800094dc`
- `0x180012300`
- `0x180014f1c`
- `0x1800afc6c`
- `0x1800b645c`
- `0x1800b651c`
- `0x1800b6a40`
- `0x1800b6ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800afd23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800afe45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800afd23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800afe45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800afde9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800afde9`

## string_xrefs

- `0x1800afd00`: `[%p] Device service command session subscription request %d completed with %d`
- `0x1800afd97`: `[%p] Failed to cache device service subscribe list on completion`
- `0x1800afe65`: `[%p] Flushing device services sap state `
- `0x1800afdd1`: `[%p] Unexpected device service subscribe completion`

## pseudocode

```c

```
