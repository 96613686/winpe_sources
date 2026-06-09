# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180010de8`
- end: `0x180010e91`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180020d6c`
- `0x1800286b4`
- `0x180028f04`
- `0x180029090`

## callees

- `0x180010de8`
- `0x1800260d0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010e3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010e3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010e13`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010e13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010dfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010dfc`

## string_xrefs

- `0x180010e36`: `ntdll.dll`

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
0x180010de8  mov     [rsp+arg_0], rbx
0x180010ded  mov     [rsp+arg_8], rsi
0x180010df2  push    rdi
0x180010df3  sub     rsp, 20h
0x180010df7  mov     rbx, rdx
0x180010dfa  mov     edi, ecx
0x180010dfc  call    cs:__imp_GetProcessHeap
0x180010e03  nop     dword ptr [rax+rax+00h]
0x180010e08  mov     r8, rbx; dwBytes
0x180010e0b  mov     edx, edi; dwFlags
0x180010e0d  mov     rcx, rax; hHeap
0x180010e10  mov     rsi, rax
0x180010e13  call    cs:__imp_HeapAlloc
0x180010e1a  nop     dword ptr [rax+rax+00h]
0x180010e1f  mov     rbx, rax
0x180010e22  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010e29  test    rax, rax
0x180010e2c  jnz     short loc_180010E69
0x180010e2e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180010e34  jnz     short loc_180010E74
0x180010e36  lea     rcx, ModuleName; "ntdll.dll"
0x180010e3d  call    cs:__imp_GetModuleHandleW
0x180010e44  nop     dword ptr [rax+rax+00h]
0x180010e49  test    rax, rax
0x180010e4c  jz      short loc_180010E88
0x180010e4e  mov     rcx, rax
0x180010e51  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180010e56  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180010e5d  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180010e64  test    rax, rax
0x180010e67  jz      short loc_180010E74
0x180010e69  mov     rdx, rbx
0x180010e6c  mov     rcx, rsi
0x180010e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e74  mov     rsi, [rsp+28h+arg_8]
0x180010e79  mov     rax, rbx
0x180010e7c  mov     rbx, [rsp+28h+arg_0]
0x180010e81  add     rsp, 20h
0x180010e85  pop     rdi
0x180010e86  retn
0x180010e88  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010e8f  jmp     short loc_180010E5D
```
