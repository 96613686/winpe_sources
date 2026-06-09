# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180033f7c`
- end: `0x180034025`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180032728`
- `0x1800490ec`
- `0x180049210`
- `0x1800498b8`
- `0x180049a44`

## callees

- `0x180033f7c`
- `0x1800479e0`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180033fd1`
- `KERNEL32!GetModuleHandleW` at `0x180033fd1`
- `KERNEL32!GetProcessHeap` at `0x180033f90`
- `KERNEL32!GetProcessHeap` at `0x180033f90`
- `KERNEL32!HeapAlloc` at `0x180033fa7`
- `KERNEL32!HeapAlloc` at `0x180033fa7`

## string_xrefs

- `0x180033fca`: `ntdll.dll`

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
0x180033f7c  mov     [rsp+arg_0], rbx
0x180033f81  mov     [rsp+arg_8], rsi
0x180033f86  push    rdi
0x180033f87  sub     rsp, 20h
0x180033f8b  mov     rbx, rdx
0x180033f8e  mov     edi, ecx
0x180033f90  call    cs:__imp_GetProcessHeap
0x180033f97  nop     dword ptr [rax+rax+00h]
0x180033f9c  mov     r8, rbx; dwBytes
0x180033f9f  mov     edx, edi; dwFlags
0x180033fa1  mov     rcx, rax; hHeap
0x180033fa4  mov     rsi, rax
0x180033fa7  call    cs:__imp_HeapAlloc
0x180033fae  nop     dword ptr [rax+rax+00h]
0x180033fb3  mov     rbx, rax
0x180033fb6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180033fbd  test    rax, rax
0x180033fc0  jnz     short loc_180034006
0x180033fc2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180033fc8  jnz     short loc_180034011
0x180033fca  lea     rcx, ModuleName; "ntdll.dll"
0x180033fd1  call    cs:__imp_GetModuleHandleW
0x180033fd8  nop     dword ptr [rax+rax+00h]
0x180033fdd  test    rax, rax
0x180033fe0  jz      short loc_180033FF3
0x180033fe2  mov     rcx, rax
0x180033fe5  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180033fea  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180033ff1  jmp     short loc_180033FFA
0x180033ff3  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180033ffa  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180034001  test    rax, rax
0x180034004  jz      short loc_180034011
0x180034006  mov     rdx, rbx
0x180034009  mov     rcx, rsi
0x18003400c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034011  mov     rsi, [rsp+28h+arg_8]
0x180034016  mov     rax, rbx
0x180034019  mov     rbx, [rsp+28h+arg_0]
0x18003401e  add     rsp, 20h
0x180034022  pop     rdi
0x180034023  retn
```
