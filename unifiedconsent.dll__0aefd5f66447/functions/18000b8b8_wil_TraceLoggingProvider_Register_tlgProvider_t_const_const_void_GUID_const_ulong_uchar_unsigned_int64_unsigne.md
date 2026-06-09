# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18000b8b8`
- end: `0x18000b976`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180009d2c`
- `0x180009de8`
- `0x1800285e0`
- `0x18004460c`

## callees

- `0x180002810`
- `0x18000b8b8`
- `0x18007d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000b93d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000b93d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000b925`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000b925`

## pseudocode

```c

```
