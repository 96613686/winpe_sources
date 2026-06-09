# UbpmProxySingleton::GetLastRunInfo(JobMoniker const &,_FILETIME &,_FILETIME &,_FILETIME &,ulong &)

- ea: `0x1800412d0`
- end: `0x1800414b9`
- name: `?GetLastRunInfo@UbpmProxySingleton@@UEAAJAEBVJobMoniker@@AEAU_FILETIME@@11AEAK@Z`
- size: `489`
- prototype: `__int64 __fastcall(UbpmProxySingleton *__hidden this, const struct JobMoniker *, struct _FILETIME *, struct _FILETIME *, struct _FILETIME *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800412d0`
- `0x180059140`

## import_xrefs

- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x18004138b`
- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x18004138b`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18004149d`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18004149d`
- `UBPM!UbpmApiBufferFree` at `0x18004147f`
- `UBPM!UbpmApiBufferFree` at `0x18004147f`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18004130f`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18004130f`

## pseudocode

```c

```
