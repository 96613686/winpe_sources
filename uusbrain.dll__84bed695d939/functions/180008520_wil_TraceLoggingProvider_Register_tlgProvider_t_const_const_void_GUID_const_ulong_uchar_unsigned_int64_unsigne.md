# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180008520`
- end: `0x1800085de`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000868c`
- `0x1800097d8`
- `0x18003c6b8`

## callees

- `0x180008520`
- `0x1800427d0`
- `0x180047a30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000858d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000858d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800085a5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800085a5`

## pseudocode

```c

```
