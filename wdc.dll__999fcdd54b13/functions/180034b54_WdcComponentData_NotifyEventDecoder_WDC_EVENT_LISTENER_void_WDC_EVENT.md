# WdcComponentData::NotifyEventDecoder(_WDC_EVENT_LISTENER *,void *,_WDC_EVENT *)

- ea: `0x180034b54`
- end: `0x180034d2a`
- name: `?NotifyEventDecoder@WdcComponentData@@CAJPEAU_WDC_EVENT_LISTENER@@PEAXPEAU_WDC_EVENT@@@Z`
- size: `470`
- prototype: `static int(struct _WDC_EVENT_LISTENER *, void *, struct _WDC_EVENT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800493f0`

## callees

- `0x18000b854`
- `0x180034b54`
- `0x1800679d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180034bbd`
- `KERNEL32!GetLastError` at `0x180034c7a`
- `KERNEL32!GetLastError` at `0x180034bbd`
- `KERNEL32!GetLastError` at `0x180034c7a`
- `wevtapi!EvtRender` at `0x180034bb3`
- `wevtapi!EvtRender` at `0x180034c6c`
- `wevtapi!EvtRender` at `0x180034bb3`
- `wevtapi!EvtRender` at `0x180034c6c`

## string_xrefs

- `0x180034d00`: `WdcComponentData::NotifyEventDecoder`
- `0x180034d07`: `base\diagnosis\pdui\perfmon\mmc\componentdata.cpp`

## pseudocode

```c

```
