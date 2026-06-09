# WwanSapSendNotification(WWAN_SAP *,_L2_NOTIFICATION_DATA *,ulong)

- ea: `0x1800b4160`
- end: `0x1800b4264`
- name: `?WwanSapSendNotification@@YAKPEAUWWAN_SAP@@PEAU_L2_NOTIFICATION_DATA@@K@Z`
- size: `260`
- prototype: `unsigned int __fastcall(struct WWAN_SAP *, struct _L2_NOTIFICATION_DATA *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800aa998`
- `0x1800aad9c`
- `0x1800abb24`

## callees

- `0x1800b18a4`
- `0x1800b4160`
- `0x1800b641c`
- `0x1800b6980`
- `0x1800b6a40`
- `0x1800b6ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b4174`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b4174`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b41e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b4221`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b41e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b4221`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800b424a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800b424a`

## pseudocode

```c

```
