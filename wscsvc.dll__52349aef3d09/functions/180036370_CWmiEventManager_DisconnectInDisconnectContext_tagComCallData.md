# CWmiEventManager::DisconnectInDisconnectContext(tagComCallData *)

- ea: `0x180036370`
- end: `0x1800363f0`
- name: `?DisconnectInDisconnectContext@CWmiEventManager@@CAJPEAUtagComCallData@@@Z`
- size: `128`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180036370`
- `0x180039540`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800363a6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800363a6`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x180036381`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x180036381`

## string_xrefs

- `0x180036399`: `wscsvc.dll`

## pseudocode

```c
__int64 __fastcall CWmiEventManager::DisconnectInDisconnectContext(struct tagComCallData *a1)
{
  _QWORD *pUserDefined; // rdi
  HRESULT v2; // ebx
  __int64 v3; // rcx

  pUserDefined = a1->pUserDefined;
  v2 = CoDisconnectContext(0xFFFFFFFF);
  if ( v2 >= 0 )
  {
    v3 = pUserDefined[4];
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 40LL))(v3, 1);
      pUserDefined[4] = 0;
    }
  }
  else
  {
    if ( !g_hSelfDll )
      g_hSelfDll = LoadLibraryExW(L"wscsvc.dll", 0, 0x800u);
    EvtLog_LogErrorWithHresult(0xC000000A, v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180036370  mov     [rsp+arg_0], rbx
0x180036375  push    rdi
0x180036376  sub     rsp, 20h
0x18003637a  mov     rdi, [rcx+8]
0x18003637e  or      ecx, 0FFFFFFFFh; dwTimeout
0x180036381  call    cs:__imp_CoDisconnectContext
0x180036387  mov     ebx, eax
0x180036389  test    eax, eax
0x18003638b  jns     short loc_1800363C1
0x18003638d  cmp     cs:?g_hSelfDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hSelfDll
0x180036395  jnz     short loc_1800363B3
0x180036397  xor     edx, edx; hFile
0x180036399  lea     rcx, aWscsvcDll_0; "wscsvc.dll"
0x1800363a0  mov     r8d, 800h; dwFlags
0x1800363a6  call    cs:__imp_LoadLibraryExW
0x1800363ac  mov     cs:?g_hSelfDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hSelfDll
0x1800363b3  mov     edx, ebx; int
0x1800363b5  mov     ecx, 0C000000Ah; dwEventID
0x1800363ba  call    ?EvtLog_LogErrorWithHresult@@YAXKJ@Z; EvtLog_LogErrorWithHresult(ulong,long)
0x1800363bf  jmp     short loc_1800363E3
0x1800363c1  mov     rcx, [rdi+20h]
0x1800363c5  test    rcx, rcx
0x1800363c8  jz      short loc_1800363E3
0x1800363ca  mov     rax, [rcx]
0x1800363cd  mov     edx, 1
0x1800363d2  mov     rax, [rax+28h]
0x1800363d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363db  mov     qword ptr [rdi+20h], 0
0x1800363e3  mov     eax, ebx
0x1800363e5  mov     rbx, [rsp+28h+arg_0]
0x1800363ea  add     rsp, 20h
0x1800363ee  pop     rdi
0x1800363ef  retn
```
