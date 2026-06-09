# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180023b00`
- end: `0x180023b96`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800238ec`
- `0x180023de4`
- `0x18002417c`
- `0x1800265c0`
- `0x180028500`

## callees

- `0x1800217c8`
- `0x180023b00`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023b49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023b49`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023b25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023b25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023b14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023b14`

## string_xrefs

- `0x180023b42`: `ntdll.dll`

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
0x180023b00  mov     [rsp+arg_0], rbx
0x180023b05  mov     [rsp+arg_8], rsi
0x180023b0a  push    rdi
0x180023b0b  sub     rsp, 20h
0x180023b0f  mov     rbx, rdx
0x180023b12  mov     edi, ecx
0x180023b14  call    cs:__imp_GetProcessHeap
0x180023b1a  mov     rsi, rax
0x180023b1d  mov     r8, rbx; dwBytes
0x180023b20  mov     edx, edi; dwFlags
0x180023b22  mov     rcx, rax; hHeap
0x180023b25  call    cs:__imp_HeapAlloc
0x180023b2b  mov     rbx, rax
0x180023b2e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180023b35  test    rax, rax
0x180023b38  jnz     short loc_180023B78
0x180023b3a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180023b40  jnz     short loc_180023B83
0x180023b42  lea     rcx, ModuleName; "ntdll.dll"
0x180023b49  call    cs:__imp_GetModuleHandleW
0x180023b4f  test    rax, rax
0x180023b52  jz      short loc_180023B65
0x180023b54  mov     rcx, rax
0x180023b57  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180023b5c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180023b63  jmp     short loc_180023B6C
0x180023b65  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180023b6c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180023b73  test    rax, rax
0x180023b76  jz      short loc_180023B83
0x180023b78  mov     rdx, rbx
0x180023b7b  mov     rcx, rsi
0x180023b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b83  mov     rax, rbx
0x180023b86  mov     rbx, [rsp+28h+arg_0]
0x180023b8b  mov     rsi, [rsp+28h+arg_8]
0x180023b90  add     rsp, 20h
0x180023b94  pop     rdi
0x180023b95  retn
```
