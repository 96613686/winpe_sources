# ArchiveDragDropHandler::~ArchiveDragDropHandler(void)

- ea: `0x180029f70`
- end: `0x180029fac`
- name: `??1ArchiveDragDropHandler@@UEAA@XZ`
- size: `60`
- prototype: `void __fastcall(ArchiveDragDropHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180029f34`

## callees

- `0x180023834`
- `0x180029f70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029f91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029f91`

## pseudocode

```c
void __fastcall ArchiveDragDropHandler::~ArchiveDragDropHandler(ArchiveDragDropHandler *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
    CoTaskMemFree(v3);
  _InterlockedDecrement(&g_cRefThisDll);
  winrt::impl::root_implements<ArchiveDragDropHandler,IContextMenu,IShellExtInit>::~root_implements<ArchiveDragDropHandler,IContextMenu,IShellExtInit>((char *)this + 16);
}

```

## disassembly

```asm
0x180029f70  push    rbx
0x180029f72  sub     rsp, 20h
0x180029f76  mov     rbx, rcx
0x180029f79  mov     rcx, [rcx+30h]; pv
0x180029f7d  test    rcx, rcx
0x180029f80  jz      short loc_180029F88
0x180029f82  call    cs:__imp_CoTaskMemFree
0x180029f88  mov     rcx, [rbx+28h]; pv
0x180029f8c  test    rcx, rcx
0x180029f8f  jz      short loc_180029F97
0x180029f91  call    cs:__imp_CoTaskMemFree
0x180029f97  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180029f9e  lea     rcx, [rbx+10h]
0x180029fa2  add     rsp, 20h
0x180029fa6  pop     rbx
0x180029fa7  jmp     ??1?$root_implements@UArchiveDragDropHandler@@UIContextMenu@@UIShellExtInit@@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<ArchiveDragDropHandler,IContextMenu,IShellExtInit>::~root_implements<ArchiveDragDropHandler,IContextMenu,IShellExtInit>(void)
```
