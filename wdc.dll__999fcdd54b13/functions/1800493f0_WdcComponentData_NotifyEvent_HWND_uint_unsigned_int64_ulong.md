# WdcComponentData::NotifyEvent(HWND__ *,uint,unsigned __int64,ulong)

- ea: `0x1800493f0`
- end: `0x1800494f2`
- name: `?NotifyEvent@WdcComponentData@@CAXPEAUHWND__@@I_KK@Z`
- size: `258`
- prototype: `void __stdcall(HWND, UINT, UINT_PTR, DWORD)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000b854`
- `0x180034b54`
- `0x1800493f0`
- `0x18004ad4c`

## import_xrefs

- `wevtapi!EvtNext` at `0x18004944a`
- `wevtapi!EvtNext` at `0x18004944a`
- `wevtapi!EvtClose` at `0x18004947e`
- `wevtapi!EvtClose` at `0x1800494d9`
- `wevtapi!EvtClose` at `0x18004947e`
- `wevtapi!EvtClose` at `0x1800494d9`

## string_xrefs

- `0x1800494bf`: `base\diagnosis\pdui\perfmon\mmc\componentdata.cpp`
- `0x1800494b8`: `WdcComponentData::NotifyEvent`

## pseudocode

```c

```
