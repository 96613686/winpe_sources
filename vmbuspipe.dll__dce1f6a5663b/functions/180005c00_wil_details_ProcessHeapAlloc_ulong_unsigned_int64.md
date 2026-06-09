# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005c00`
- end: `0x180005c96`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800056bc`
- `0x180005ea0`
- `0x180006238`

## callees

- `0x180003134`
- `0x180005c00`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005c25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005c25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c14`

## string_xrefs

- `0x180005c42`: `ntdll.dll`

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
0x180005c00  mov     [rsp+arg_0], rbx
0x180005c05  mov     [rsp+arg_8], rsi
0x180005c0a  push    rdi
0x180005c0b  sub     rsp, 20h
0x180005c0f  mov     rbx, rdx
0x180005c12  mov     edi, ecx
0x180005c14  call    cs:__imp_GetProcessHeap
0x180005c1a  mov     rsi, rax
0x180005c1d  mov     r8, rbx; dwBytes
0x180005c20  mov     edx, edi; dwFlags
0x180005c22  mov     rcx, rax; hHeap
0x180005c25  call    cs:__imp_HeapAlloc
0x180005c2b  mov     rbx, rax
0x180005c2e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005c35  test    rax, rax
0x180005c38  jnz     short loc_180005C78
0x180005c3a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005c40  jnz     short loc_180005C83
0x180005c42  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180005c49  call    cs:__imp_GetModuleHandleW
0x180005c4f  test    rax, rax
0x180005c52  jz      short loc_180005C65
0x180005c54  mov     rcx, rax
0x180005c57  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180005c5c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005c63  jmp     short loc_180005C6C
0x180005c65  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005c6c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005c73  test    rax, rax
0x180005c76  jz      short loc_180005C83
0x180005c78  mov     rdx, rbx
0x180005c7b  mov     rcx, rsi
0x180005c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c83  mov     rax, rbx
0x180005c86  mov     rbx, [rsp+28h+arg_0]
0x180005c8b  mov     rsi, [rsp+28h+arg_8]
0x180005c90  add     rsp, 20h
0x180005c94  pop     rdi
0x180005c95  retn
```
