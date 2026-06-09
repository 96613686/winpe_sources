# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002d704`
- end: `0x18002d79a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005e90`
- `0x180029408`
- `0x18002956c`
- `0x18002dcf0`
- `0x18002e088`
- `0x18002f180`

## callees

- `0x18002b884`
- `0x18002d704`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d74d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d74d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d729`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d729`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d718`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d718`

## string_xrefs

- `0x18002d746`: `ntdll.dll`

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
0x18002d704  mov     [rsp+arg_0], rbx
0x18002d709  mov     [rsp+arg_8], rsi
0x18002d70e  push    rdi
0x18002d70f  sub     rsp, 20h
0x18002d713  mov     rbx, rdx
0x18002d716  mov     edi, ecx
0x18002d718  call    cs:__imp_GetProcessHeap
0x18002d71e  mov     rsi, rax
0x18002d721  mov     r8, rbx; dwBytes
0x18002d724  mov     edx, edi; dwFlags
0x18002d726  mov     rcx, rax; hHeap
0x18002d729  call    cs:__imp_HeapAlloc
0x18002d72f  mov     rbx, rax
0x18002d732  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002d739  test    rax, rax
0x18002d73c  jnz     short loc_18002D77C
0x18002d73e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002d744  jnz     short loc_18002D787
0x18002d746  lea     rcx, ModuleName; "ntdll.dll"
0x18002d74d  call    cs:__imp_GetModuleHandleW
0x18002d753  test    rax, rax
0x18002d756  jz      short loc_18002D769
0x18002d758  mov     rcx, rax
0x18002d75b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18002d760  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002d767  jmp     short loc_18002D770
0x18002d769  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002d770  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002d777  test    rax, rax
0x18002d77a  jz      short loc_18002D787
0x18002d77c  mov     rdx, rbx
0x18002d77f  mov     rcx, rsi
0x18002d782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d787  mov     rax, rbx
0x18002d78a  mov     rbx, [rsp+28h+arg_0]
0x18002d78f  mov     rsi, [rsp+28h+arg_8]
0x18002d794  add     rsp, 20h
0x18002d798  pop     rdi
0x18002d799  retn
```
