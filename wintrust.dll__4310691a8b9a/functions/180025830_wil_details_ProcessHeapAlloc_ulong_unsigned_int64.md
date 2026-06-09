# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180025830`
- end: `0x1800258c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002d400`
- `0x1800342b8`
- `0x180034450`
- `0x180034c24`
- `0x180034d60`

## callees

- `0x180025830`
- `0x180032b38`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025879`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025879`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025844`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025844`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025855`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025855`

## string_xrefs

- `0x180025872`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  void (__fastcall *ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)(HANDLE, LPVOID); // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (void (__fastcall *)(HANDLE, LPVOID))(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW),
                                              `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z) )
  {
    ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ProcessHeap, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180025830  mov     [rsp+arg_0], rbx
0x180025835  mov     [rsp+arg_8], rsi
0x18002583a  push    rdi
0x18002583b  sub     rsp, 20h
0x18002583f  mov     rbx, rdx
0x180025842  mov     edi, ecx
0x180025844  call    cs:__imp_GetProcessHeap
0x18002584a  mov     rsi, rax
0x18002584d  mov     r8, rbx; dwBytes
0x180025850  mov     edx, edi; dwFlags
0x180025852  mov     rcx, rax; hHeap
0x180025855  call    cs:__imp_HeapAlloc
0x18002585b  mov     rbx, rax
0x18002585e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180025865  test    rax, rax
0x180025868  jnz     short loc_18002589F
0x18002586a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180025870  jnz     short loc_1800258AA
0x180025872  lea     rcx, ModuleName; "ntdll.dll"
0x180025879  call    cs:__imp_GetModuleHandleW
0x18002587f  test    rax, rax
0x180025882  jz      short loc_1800258BD
0x180025884  mov     rcx, rax
0x180025887  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18002588c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180025893  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002589a  test    rax, rax
0x18002589d  jz      short loc_1800258AA
0x18002589f  mov     rdx, rbx
0x1800258a2  mov     rcx, rsi
0x1800258a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258aa  mov     rax, rbx
0x1800258ad  mov     rbx, [rsp+28h+arg_0]
0x1800258b2  mov     rsi, [rsp+28h+arg_8]
0x1800258b7  add     rsp, 20h
0x1800258bb  pop     rdi
0x1800258bc  retn
0x1800258bd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800258c4  jmp     short loc_180025893
```
