# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002f2d4`
- end: `0x18002f36a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002dc70`
- `0x180047bf0`
- `0x180047d14`
- `0x180048354`
- `0x1800484cc`

## callees

- `0x18002f2d4`
- `0x1800465bc`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002f31d`
- `KERNEL32!GetModuleHandleW` at `0x18002f31d`
- `KERNEL32!GetProcessHeap` at `0x18002f2e8`
- `KERNEL32!GetProcessHeap` at `0x18002f2e8`
- `KERNEL32!HeapAlloc` at `0x18002f2f9`
- `KERNEL32!HeapAlloc` at `0x18002f2f9`

## string_xrefs

- `0x18002f316`: `ntdll.dll`

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
0x18002f2d4  mov     [rsp+arg_0], rbx
0x18002f2d9  mov     [rsp+arg_8], rsi
0x18002f2de  push    rdi
0x18002f2df  sub     rsp, 20h
0x18002f2e3  mov     rbx, rdx
0x18002f2e6  mov     edi, ecx
0x18002f2e8  call    cs:__imp_GetProcessHeap
0x18002f2ee  mov     r8, rbx; dwBytes
0x18002f2f1  mov     edx, edi; dwFlags
0x18002f2f3  mov     rcx, rax; hHeap
0x18002f2f6  mov     rsi, rax
0x18002f2f9  call    cs:__imp_HeapAlloc
0x18002f2ff  mov     rbx, rax
0x18002f302  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002f309  test    rax, rax
0x18002f30c  jnz     short loc_18002F34C
0x18002f30e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002f314  jnz     short loc_18002F357
0x18002f316  lea     rcx, ModuleName; "ntdll.dll"
0x18002f31d  call    cs:__imp_GetModuleHandleW
0x18002f323  test    rax, rax
0x18002f326  jz      short loc_18002F339
0x18002f328  mov     rcx, rax
0x18002f32b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18002f330  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002f337  jmp     short loc_18002F340
0x18002f339  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002f340  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002f347  test    rax, rax
0x18002f34a  jz      short loc_18002F357
0x18002f34c  mov     rdx, rbx
0x18002f34f  mov     rcx, rsi
0x18002f352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f357  mov     rsi, [rsp+28h+arg_8]
0x18002f35c  mov     rax, rbx
0x18002f35f  mov     rbx, [rsp+28h+arg_0]
0x18002f364  add     rsp, 20h
0x18002f368  pop     rdi
0x18002f369  retn
```
