# CRegistryChangeListener::~CRegistryChangeListener(void)

- ea: `0x180073e08`
- end: `0x180073e6a`
- name: `??1CRegistryChangeListener@@AEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CRegistryChangeListener *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073e80`
- `0x180074060`
- `0x1800743d0`

## callees

- `0x180073e08`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073e2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073e3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073e3e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180073e4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180073e4d`

## pseudocode

```c
void __fastcall CRegistryChangeListener::~CRegistryChangeListener(CRegistryChangeListener *this)
{
  void *v2; // rcx
  HKEY v3; // rcx
  struct _TP_WORK *v4; // rcx

  *(_QWORD *)this = &CRegistryChangeListener::`vftable'{for `IOleCommandTarget'};
  *((_QWORD *)this + 1) = &CRegistryChangeListener::`vftable'{for `IRegistryChangeListener'};
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    CloseHandle(v2);
  v3 = (HKEY)*((_QWORD *)this + 4);
  if ( v3 )
    RegCloseKey(v3);
  v4 = (struct _TP_WORK *)*((_QWORD *)this + 8);
  if ( v4 )
    CloseThreadpoolWork(v4);
  CoTaskMemFree(*((LPVOID *)this + 10));
  _InterlockedDecrement(&g_cLocks);
}

```

## disassembly

```asm
0x180073e08  push    rbx
0x180073e0a  sub     rsp, 20h
0x180073e0e  lea     rax, ??_7CRegistryChangeListener@@6BIOleCommandTarget@@@; const CRegistryChangeListener::`vftable'{for `IOleCommandTarget'}
0x180073e15  mov     rbx, rcx
0x180073e18  mov     [rcx], rax
0x180073e1b  lea     rax, ??_7CRegistryChangeListener@@6BIRegistryChangeListener@@@; const CRegistryChangeListener::`vftable'{for `IRegistryChangeListener'}
0x180073e22  mov     [rcx+8], rax
0x180073e26  mov     rcx, [rcx+18h]; hObject
0x180073e2a  test    rcx, rcx
0x180073e2d  jz      short loc_180073E35
0x180073e2f  call    cs:__imp_CloseHandle
0x180073e35  mov     rcx, [rbx+20h]; hKey
0x180073e39  test    rcx, rcx
0x180073e3c  jz      short loc_180073E44
0x180073e3e  call    cs:__imp_RegCloseKey
0x180073e44  mov     rcx, [rbx+40h]; pwk
0x180073e48  test    rcx, rcx
0x180073e4b  jz      short loc_180073E53
0x180073e4d  call    cs:__imp_CloseThreadpoolWork
0x180073e53  mov     rcx, [rbx+50h]; pv
0x180073e57  call    cs:__imp_CoTaskMemFree
0x180073e5d  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x180073e64  add     rsp, 20h
0x180073e68  pop     rbx
0x180073e69  retn
```
