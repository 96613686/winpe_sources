# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001edd8`
- end: `0x18001ee6e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001eb9c`
- `0x18001f0ac`
- `0x18001f224`

## callees

- `0x18001d450`
- `0x18001edd8`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ee21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ee21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001edec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001edec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001edfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001edfd`

## string_xrefs

- `0x18001ee1a`: `ntdll.dll`

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
0x18001edd8  mov     [rsp+arg_0], rbx
0x18001eddd  mov     [rsp+arg_8], rsi
0x18001ede2  push    rdi
0x18001ede3  sub     rsp, 20h
0x18001ede7  mov     rbx, rdx
0x18001edea  mov     edi, ecx
0x18001edec  call    cs:__imp_GetProcessHeap
0x18001edf2  mov     r8, rbx; dwBytes
0x18001edf5  mov     edx, edi; dwFlags
0x18001edf7  mov     rcx, rax; hHeap
0x18001edfa  mov     rsi, rax
0x18001edfd  call    cs:__imp_HeapAlloc
0x18001ee03  mov     rbx, rax
0x18001ee06  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001ee0d  test    rax, rax
0x18001ee10  jnz     short loc_18001EE50
0x18001ee12  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001ee18  jnz     short loc_18001EE5B
0x18001ee1a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001ee21  call    cs:__imp_GetModuleHandleW
0x18001ee27  test    rax, rax
0x18001ee2a  jz      short loc_18001EE3D
0x18001ee2c  mov     rcx, rax
0x18001ee2f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18001ee34  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001ee3b  jmp     short loc_18001EE44
0x18001ee3d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001ee44  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001ee4b  test    rax, rax
0x18001ee4e  jz      short loc_18001EE5B
0x18001ee50  mov     rdx, rbx
0x18001ee53  mov     rcx, rsi
0x18001ee56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee5b  mov     rsi, [rsp+28h+arg_8]
0x18001ee60  mov     rax, rbx
0x18001ee63  mov     rbx, [rsp+28h+arg_0]
0x18001ee68  add     rsp, 20h
0x18001ee6c  pop     rdi
0x18001ee6d  retn
```
