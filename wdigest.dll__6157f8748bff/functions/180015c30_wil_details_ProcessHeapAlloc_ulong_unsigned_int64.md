# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180015c30`
- end: `0x180015cc6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010d98`
- `0x1800158f8`
- `0x180015a1c`
- `0x180016198`
- `0x1800162d4`

## callees

- `0x180013ccc`
- `0x180015c30`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015c79`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015c79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015c55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015c55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015c44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015c44`

## string_xrefs

- `0x180015c72`: `ntdll.dll`

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
0x180015c30  mov     [rsp+arg_0], rbx
0x180015c35  mov     [rsp+arg_8], rsi
0x180015c3a  push    rdi
0x180015c3b  sub     rsp, 20h
0x180015c3f  mov     rbx, rdx
0x180015c42  mov     edi, ecx
0x180015c44  call    cs:__imp_GetProcessHeap
0x180015c4a  mov     r8, rbx; dwBytes
0x180015c4d  mov     edx, edi; dwFlags
0x180015c4f  mov     rcx, rax; hHeap
0x180015c52  mov     rsi, rax
0x180015c55  call    cs:__imp_HeapAlloc
0x180015c5b  mov     rbx, rax
0x180015c5e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180015c65  test    rax, rax
0x180015c68  jnz     short loc_180015CA8
0x180015c6a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180015c70  jnz     short loc_180015CB3
0x180015c72  lea     rcx, ModuleName; "ntdll.dll"
0x180015c79  call    cs:__imp_GetModuleHandleW
0x180015c7f  test    rax, rax
0x180015c82  jz      short loc_180015C95
0x180015c84  mov     rcx, rax
0x180015c87  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180015c8c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180015c93  jmp     short loc_180015C9C
0x180015c95  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180015c9c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180015ca3  test    rax, rax
0x180015ca6  jz      short loc_180015CB3
0x180015ca8  mov     rdx, rbx
0x180015cab  mov     rcx, rsi
0x180015cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cb3  mov     rsi, [rsp+28h+arg_8]
0x180015cb8  mov     rax, rbx
0x180015cbb  mov     rbx, [rsp+28h+arg_0]
0x180015cc0  add     rsp, 20h
0x180015cc4  pop     rdi
0x180015cc5  retn
```
