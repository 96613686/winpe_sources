# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009e24`
- end: `0x180009ecd`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800041a8`
- `0x180004300`
- `0x18000b1c4`
- `0x18000b578`
- `0x18000c6a0`

## callees

- `0x180006a78`
- `0x180009e24`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e79`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e38`

## string_xrefs

- `0x180009e72`: `ntdll.dll`

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
0x180009e24  mov     [rsp+arg_0], rbx
0x180009e29  mov     [rsp+arg_8], rsi
0x180009e2e  push    rdi
0x180009e2f  sub     rsp, 20h
0x180009e33  mov     rbx, rdx
0x180009e36  mov     edi, ecx
0x180009e38  call    cs:__imp_GetProcessHeap
0x180009e3f  nop     dword ptr [rax+rax+00h]
0x180009e44  mov     rsi, rax
0x180009e47  mov     r8, rbx; dwBytes
0x180009e4a  mov     edx, edi; dwFlags
0x180009e4c  mov     rcx, rax; hHeap
0x180009e4f  call    cs:__imp_HeapAlloc
0x180009e56  nop     dword ptr [rax+rax+00h]
0x180009e5b  mov     rbx, rax
0x180009e5e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009e65  test    rax, rax
0x180009e68  jnz     short loc_180009EAE
0x180009e6a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009e70  jnz     short loc_180009EB9
0x180009e72  lea     rcx, ModuleName; "ntdll.dll"
0x180009e79  call    cs:__imp_GetModuleHandleW
0x180009e80  nop     dword ptr [rax+rax+00h]
0x180009e85  test    rax, rax
0x180009e88  jz      short loc_180009E9B
0x180009e8a  mov     rcx, rax
0x180009e8d  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180009e92  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180009e99  jmp     short loc_180009EA2
0x180009e9b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009ea2  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009ea9  test    rax, rax
0x180009eac  jz      short loc_180009EB9
0x180009eae  mov     rdx, rbx
0x180009eb1  mov     rcx, rsi
0x180009eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eb9  mov     rax, rbx
0x180009ebc  mov     rbx, [rsp+28h+arg_0]
0x180009ec1  mov     rsi, [rsp+28h+arg_8]
0x180009ec6  add     rsp, 20h
0x180009eca  pop     rdi
0x180009ecb  retn
```
