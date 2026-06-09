# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000f008`
- end: `0x18000f09e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a704`
- `0x18000a858`
- `0x18000fa84`
- `0x18000fce8`
- `0x180010a7c`

## callees

- `0x18000caf8`
- `0x18000f008`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f051`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f01c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f01c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f02d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f02d`

## string_xrefs

- `0x18000f04a`: `ntdll.dll`

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
0x18000f008  mov     [rsp+arg_0], rbx
0x18000f00d  mov     [rsp+arg_8], rsi
0x18000f012  push    rdi
0x18000f013  sub     rsp, 20h
0x18000f017  mov     rbx, rdx
0x18000f01a  mov     edi, ecx
0x18000f01c  call    cs:__imp_GetProcessHeap
0x18000f022  mov     r8, rbx; dwBytes
0x18000f025  mov     edx, edi; dwFlags
0x18000f027  mov     rcx, rax; hHeap
0x18000f02a  mov     rsi, rax
0x18000f02d  call    cs:__imp_HeapAlloc
0x18000f033  mov     rbx, rax
0x18000f036  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000f03d  test    rax, rax
0x18000f040  jnz     short loc_18000F080
0x18000f042  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000f048  jnz     short loc_18000F08B
0x18000f04a  lea     rcx, ModuleName; "ntdll.dll"
0x18000f051  call    cs:__imp_GetModuleHandleW
0x18000f057  test    rax, rax
0x18000f05a  jz      short loc_18000F06D
0x18000f05c  mov     rcx, rax
0x18000f05f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000f064  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000f06b  jmp     short loc_18000F074
0x18000f06d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000f074  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000f07b  test    rax, rax
0x18000f07e  jz      short loc_18000F08B
0x18000f080  mov     rdx, rbx
0x18000f083  mov     rcx, rsi
0x18000f086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f08b  mov     rsi, [rsp+28h+arg_8]
0x18000f090  mov     rax, rbx
0x18000f093  mov     rbx, [rsp+28h+arg_0]
0x18000f098  add     rsp, 20h
0x18000f09c  pop     rdi
0x18000f09d  retn
```
