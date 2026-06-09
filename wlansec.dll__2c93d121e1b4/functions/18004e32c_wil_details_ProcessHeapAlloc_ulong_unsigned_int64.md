# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004e32c`
- end: `0x18004e3d5`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800369b0`
- `0x18003fb70`
- `0x18004ded0`
- `0x18004dff4`
- `0x18004ed74`
- `0x18004efac`

## callees

- `0x18004bd04`
- `0x18004e32c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004e381`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004e381`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e340`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e340`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e357`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e357`

## string_xrefs

- `0x18004e37a`: `ntdll.dll`

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
0x18004e32c  mov     [rsp+arg_0], rbx
0x18004e331  mov     [rsp+arg_8], rsi
0x18004e336  push    rdi
0x18004e337  sub     rsp, 20h
0x18004e33b  mov     rbx, rdx
0x18004e33e  mov     edi, ecx
0x18004e340  call    cs:__imp_GetProcessHeap
0x18004e347  nop     dword ptr [rax+rax+00h]
0x18004e34c  mov     rsi, rax
0x18004e34f  mov     r8, rbx; dwBytes
0x18004e352  mov     edx, edi; dwFlags
0x18004e354  mov     rcx, rax; hHeap
0x18004e357  call    cs:__imp_HeapAlloc
0x18004e35e  nop     dword ptr [rax+rax+00h]
0x18004e363  mov     rbx, rax
0x18004e366  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004e36d  test    rax, rax
0x18004e370  jnz     short loc_18004E3B6
0x18004e372  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004e378  jnz     short loc_18004E3C1
0x18004e37a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18004e381  call    cs:__imp_GetModuleHandleW
0x18004e388  nop     dword ptr [rax+rax+00h]
0x18004e38d  test    rax, rax
0x18004e390  jz      short loc_18004E3A3
0x18004e392  mov     rcx, rax
0x18004e395  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18004e39a  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18004e3a1  jmp     short loc_18004E3AA
0x18004e3a3  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004e3aa  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004e3b1  test    rax, rax
0x18004e3b4  jz      short loc_18004E3C1
0x18004e3b6  mov     rdx, rbx
0x18004e3b9  mov     rcx, rsi
0x18004e3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3c1  mov     rax, rbx
0x18004e3c4  mov     rbx, [rsp+28h+arg_0]
0x18004e3c9  mov     rsi, [rsp+28h+arg_8]
0x18004e3ce  add     rsp, 20h
0x18004e3d2  pop     rdi
0x18004e3d3  retn
```
