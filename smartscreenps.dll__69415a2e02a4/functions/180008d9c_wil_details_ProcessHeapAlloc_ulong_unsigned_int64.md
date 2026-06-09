# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008d9c`
- end: `0x180008e45`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008bf0`
- `0x18000926c`
- `0x180009620`

## callees

- `0x180006c04`
- `0x180008d9c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008df1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008df1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008db0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008db0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008dc7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008dc7`

## string_xrefs

- `0x180008dea`: `ntdll.dll`

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
0x180008d9c  mov     [rsp+arg_0], rbx
0x180008da1  mov     [rsp+arg_8], rsi
0x180008da6  push    rdi
0x180008da7  sub     rsp, 20h
0x180008dab  mov     rbx, rdx
0x180008dae  mov     edi, ecx
0x180008db0  call    cs:__imp_GetProcessHeap
0x180008db7  nop     dword ptr [rax+rax+00h]
0x180008dbc  mov     rsi, rax
0x180008dbf  mov     r8, rbx; dwBytes
0x180008dc2  mov     edx, edi; dwFlags
0x180008dc4  mov     rcx, rax; hHeap
0x180008dc7  call    cs:__imp_HeapAlloc
0x180008dce  nop     dword ptr [rax+rax+00h]
0x180008dd3  mov     rbx, rax
0x180008dd6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008ddd  test    rax, rax
0x180008de0  jnz     short loc_180008E26
0x180008de2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008de8  jnz     short loc_180008E31
0x180008dea  lea     rcx, ModuleName; "ntdll.dll"
0x180008df1  call    cs:__imp_GetModuleHandleW
0x180008df8  nop     dword ptr [rax+rax+00h]
0x180008dfd  test    rax, rax
0x180008e00  jz      short loc_180008E13
0x180008e02  mov     rcx, rax
0x180008e05  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180008e0a  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008e11  jmp     short loc_180008E1A
0x180008e13  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008e1a  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008e21  test    rax, rax
0x180008e24  jz      short loc_180008E31
0x180008e26  mov     rdx, rbx
0x180008e29  mov     rcx, rsi
0x180008e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e31  mov     rax, rbx
0x180008e34  mov     rbx, [rsp+28h+arg_0]
0x180008e39  mov     rsi, [rsp+28h+arg_8]
0x180008e3e  add     rsp, 20h
0x180008e42  pop     rdi
0x180008e43  retn
```
