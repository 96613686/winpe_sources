# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18007892c`
- end: `0x1800789c2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180078694`
- `0x180078fcc`
- `0x18007926c`

## callees

- `0x1800760cc`
- `0x18007892c`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180078975`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180078975`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078940`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078940`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078951`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078951`

## string_xrefs

- `0x18007896e`: `ntdll.dll`

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
0x18007892c  mov     [rsp+arg_0], rbx
0x180078931  mov     [rsp+arg_8], rsi
0x180078936  push    rdi
0x180078937  sub     rsp, 20h
0x18007893b  mov     rbx, rdx
0x18007893e  mov     edi, ecx
0x180078940  call    cs:__imp_GetProcessHeap
0x180078946  mov     r8, rbx; dwBytes
0x180078949  mov     edx, edi; dwFlags
0x18007894b  mov     rcx, rax; hHeap
0x18007894e  mov     rsi, rax
0x180078951  call    cs:__imp_HeapAlloc
0x180078957  mov     rbx, rax
0x18007895a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180078961  test    rax, rax
0x180078964  jnz     short loc_1800789A4
0x180078966  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18007896c  jnz     short loc_1800789AF
0x18007896e  lea     rcx, ModuleName; "ntdll.dll"
0x180078975  call    cs:__imp_GetModuleHandleW
0x18007897b  test    rax, rax
0x18007897e  jz      short loc_180078991
0x180078980  mov     rcx, rax
0x180078983  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180078988  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18007898f  jmp     short loc_180078998
0x180078991  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180078998  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18007899f  test    rax, rax
0x1800789a2  jz      short loc_1800789AF
0x1800789a4  mov     rdx, rbx
0x1800789a7  mov     rcx, rsi
0x1800789aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800789af  mov     rsi, [rsp+28h+arg_8]
0x1800789b4  mov     rax, rbx
0x1800789b7  mov     rbx, [rsp+28h+arg_0]
0x1800789bc  add     rsp, 20h
0x1800789c0  pop     rdi
0x1800789c1  retn
```
