# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006668`
- end: `0x180006711`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000608c`
- `0x180011efc`
- `0x1800121ac`
- `0x1800122f8`
- `0x180017180`
- `0x180019510`

## callees

- `0x180006668`
- `0x180010d78`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006693`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006693`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000667c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000667c`

## string_xrefs

- `0x1800066b6`: `ntdll.dll`

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
0x180006668  mov     [rsp+arg_0], rbx
0x18000666d  mov     [rsp+arg_8], rsi
0x180006672  push    rdi
0x180006673  sub     rsp, 20h
0x180006677  mov     rbx, rdx
0x18000667a  mov     edi, ecx
0x18000667c  call    cs:__imp_GetProcessHeap
0x180006683  nop     dword ptr [rax+rax+00h]
0x180006688  mov     rsi, rax
0x18000668b  mov     r8, rbx; dwBytes
0x18000668e  mov     edx, edi; dwFlags
0x180006690  mov     rcx, rax; hHeap
0x180006693  call    cs:__imp_HeapAlloc
0x18000669a  nop     dword ptr [rax+rax+00h]
0x18000669f  mov     rbx, rax
0x1800066a2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800066a9  test    rax, rax
0x1800066ac  jnz     short loc_1800066E9
0x1800066ae  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800066b4  jnz     short loc_1800066F4
0x1800066b6  lea     rcx, ModuleName; "ntdll.dll"
0x1800066bd  call    cs:__imp_GetModuleHandleW
0x1800066c4  nop     dword ptr [rax+rax+00h]
0x1800066c9  test    rax, rax
0x1800066cc  jz      short loc_180006708
0x1800066ce  mov     rcx, rax
0x1800066d1  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800066d6  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800066dd  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800066e4  test    rax, rax
0x1800066e7  jz      short loc_1800066F4
0x1800066e9  mov     rdx, rbx
0x1800066ec  mov     rcx, rsi
0x1800066ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f4  mov     rax, rbx
0x1800066f7  mov     rbx, [rsp+28h+arg_0]
0x1800066fc  mov     rsi, [rsp+28h+arg_8]
0x180006701  add     rsp, 20h
0x180006705  pop     rdi
0x180006706  retn
0x180006708  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000670f  jmp     short loc_1800066DD
```
