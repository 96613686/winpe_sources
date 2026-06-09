# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800096c8`
- end: `0x18000975e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003ea4`
- `0x180003ff8`
- `0x18000a8e0`
- `0x18000ac78`
- `0x18000bd0c`

## callees

- `0x1800066f4`
- `0x1800096c8`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009711`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009711`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800096ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800096ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096dc`

## string_xrefs

- `0x18000970a`: `ntdll.dll`

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
0x1800096c8  mov     [rsp+arg_0], rbx
0x1800096cd  mov     [rsp+arg_8], rsi
0x1800096d2  push    rdi
0x1800096d3  sub     rsp, 20h
0x1800096d7  mov     rbx, rdx
0x1800096da  mov     edi, ecx
0x1800096dc  call    cs:__imp_GetProcessHeap
0x1800096e2  mov     rsi, rax
0x1800096e5  mov     r8, rbx; dwBytes
0x1800096e8  mov     edx, edi; dwFlags
0x1800096ea  mov     rcx, rax; hHeap
0x1800096ed  call    cs:__imp_HeapAlloc
0x1800096f3  mov     rbx, rax
0x1800096f6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800096fd  test    rax, rax
0x180009700  jnz     short loc_180009740
0x180009702  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009708  jnz     short loc_18000974B
0x18000970a  lea     rcx, ModuleName; "ntdll.dll"
0x180009711  call    cs:__imp_GetModuleHandleW
0x180009717  test    rax, rax
0x18000971a  jz      short loc_18000972D
0x18000971c  mov     rcx, rax
0x18000971f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180009724  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000972b  jmp     short loc_180009734
0x18000972d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009734  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000973b  test    rax, rax
0x18000973e  jz      short loc_18000974B
0x180009740  mov     rdx, rbx
0x180009743  mov     rcx, rsi
0x180009746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000974b  mov     rax, rbx
0x18000974e  mov     rbx, [rsp+28h+arg_0]
0x180009753  mov     rsi, [rsp+28h+arg_8]
0x180009758  add     rsp, 20h
0x18000975c  pop     rdi
0x18000975d  retn
```
