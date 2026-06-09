# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000eb64`
- end: `0x18000ec0d`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e240`
- `0x18000e39c`
- `0x18000fde8`
- `0x180010030`
- `0x180010e4c`

## callees

- `0x18000b250`
- `0x18000eb64`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ebb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ebb9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eb8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eb8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb78`

## string_xrefs

- `0x18000ebb2`: `ntdll.dll`

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
0x18000eb64  mov     [rsp+arg_0], rbx
0x18000eb69  mov     [rsp+arg_8], rsi
0x18000eb6e  push    rdi
0x18000eb6f  sub     rsp, 20h
0x18000eb73  mov     rbx, rdx
0x18000eb76  mov     edi, ecx
0x18000eb78  call    cs:__imp_GetProcessHeap
0x18000eb7f  nop     dword ptr [rax+rax+00h]
0x18000eb84  mov     rsi, rax
0x18000eb87  mov     r8, rbx; dwBytes
0x18000eb8a  mov     edx, edi; dwFlags
0x18000eb8c  mov     rcx, rax; hHeap
0x18000eb8f  call    cs:__imp_HeapAlloc
0x18000eb96  nop     dword ptr [rax+rax+00h]
0x18000eb9b  mov     rbx, rax
0x18000eb9e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000eba5  test    rax, rax
0x18000eba8  jnz     short loc_18000EBEE
0x18000ebaa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ebb0  jnz     short loc_18000EBF9
0x18000ebb2  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000ebb9  call    cs:__imp_GetModuleHandleW
0x18000ebc0  nop     dword ptr [rax+rax+00h]
0x18000ebc5  test    rax, rax
0x18000ebc8  jz      short loc_18000EBDB
0x18000ebca  mov     rcx, rax
0x18000ebcd  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000ebd2  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000ebd9  jmp     short loc_18000EBE2
0x18000ebdb  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ebe2  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ebe9  test    rax, rax
0x18000ebec  jz      short loc_18000EBF9
0x18000ebee  mov     rdx, rbx
0x18000ebf1  mov     rcx, rsi
0x18000ebf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebf9  mov     rax, rbx
0x18000ebfc  mov     rbx, [rsp+28h+arg_0]
0x18000ec01  mov     rsi, [rsp+28h+arg_8]
0x18000ec06  add     rsp, 20h
0x18000ec0a  pop     rdi
0x18000ec0b  retn
```
