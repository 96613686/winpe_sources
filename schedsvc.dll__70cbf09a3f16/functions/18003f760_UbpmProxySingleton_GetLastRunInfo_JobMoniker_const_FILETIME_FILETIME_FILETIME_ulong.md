# UbpmProxySingleton::GetLastRunInfo(JobMoniker const &,_FILETIME &,_FILETIME &,_FILETIME &,ulong &)

- ea: `0x18003f760`
- end: `0x18003f930`
- name: `?GetLastRunInfo@UbpmProxySingleton@@UEAAJAEBVJobMoniker@@AEAU_FILETIME@@11AEAK@Z`
- size: `464`
- prototype: `__int64 __fastcall(UbpmProxySingleton *__hidden this, const struct JobMoniker *, struct _FILETIME *, struct _FILETIME *, struct _FILETIME *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18003f760`
- `0x180056794`

## import_xrefs

- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x18003f815`
- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x18003f815`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18003f91b`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18003f91b`
- `UBPM!UbpmApiBufferFree` at `0x18003f903`
- `UBPM!UbpmApiBufferFree` at `0x18003f903`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18003f79f`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18003f79f`

## pseudocode

```c

```
