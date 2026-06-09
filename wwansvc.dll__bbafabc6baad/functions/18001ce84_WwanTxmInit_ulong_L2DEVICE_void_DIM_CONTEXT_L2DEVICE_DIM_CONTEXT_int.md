# WwanTxmInit(ulong (*)(_L2DEVICE *,void *,_DIM_CONTEXT * *),_L2DEVICE *,_DIM_CONTEXT * *,int)

- ea: `0x18001ce84`
- end: `0x18001d1cd`
- name: `?WwanTxmInit@@YAKP6AKPEAU_L2DEVICE@@PEAXPEAPEAU_DIM_CONTEXT@@@Z02H@Z`
- size: `841`
- prototype: `unsigned int(unsigned int (*)(struct _L2DEVICE *, void *, struct _DIM_CONTEXT **), struct _L2DEVICE *, struct _DIM_CONTEXT **, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18008c82c`

## callees

- `0x18000a2dc`
- `0x180012300`
- `0x180014f1c`
- `0x18001c86c`
- `0x18001ce84`
- `0x18001d1d4`
- `0x18001e358`
- `0x18001e3d0`
- `0x1800856b0`
- `0x1800b6a40`
- `0x1800c5d28`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cf08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cf08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d1b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d1b4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001cf64`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001cf64`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001d161`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001d161`
- `MobileNetworking!HtNewHandle` at `0x18001d0e0`
- `MobileNetworking!HtNewHandle` at `0x18001d0e0`

## string_xrefs

- `0x18001ceb5`: `pfnDIMCreateContext is nullptr`
- `0x18001cfbc`: `CreateTimer Failed [%u]`
- `0x18001d10a`: `txRspTimer.CreateTimer, handle=(0x%p)`
- `0x18001d133`: `dim-create-context failed [%u]`
- `0x18001d19b`: `TXM Initialization Completed`

## pseudocode

```c

```
