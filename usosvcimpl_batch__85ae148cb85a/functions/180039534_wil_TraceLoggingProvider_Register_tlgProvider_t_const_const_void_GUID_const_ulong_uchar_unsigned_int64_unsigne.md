# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180039534`
- end: `0x1800395f2`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180030620`
- `0x180085644`
- `0x1800857a8`
- `0x180086670`

## callees

- `0x180039534`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800395a1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800395a1`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800395b9`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800395b9`

## pseudocode

```c

```
