# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800442d8`
- end: `0x18004436e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800440c8`
- `0x18004479c`
- `0x180044b34`

## callees

- `0x180041be0`
- `0x1800442d8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180044321`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180044321`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800442ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800442ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800442fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800442fd`

## string_xrefs

- `0x18004431a`: `ntdll.dll`

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
0x1800442d8  mov     [rsp+arg_0], rbx
0x1800442dd  mov     [rsp+arg_8], rsi
0x1800442e2  push    rdi
0x1800442e3  sub     rsp, 20h
0x1800442e7  mov     rbx, rdx
0x1800442ea  mov     edi, ecx
0x1800442ec  call    cs:__imp_GetProcessHeap
0x1800442f2  mov     rsi, rax
0x1800442f5  mov     r8, rbx; dwBytes
0x1800442f8  mov     edx, edi; dwFlags
0x1800442fa  mov     rcx, rax; hHeap
0x1800442fd  call    cs:__imp_HeapAlloc
0x180044303  mov     rbx, rax
0x180044306  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004430d  test    rax, rax
0x180044310  jnz     short loc_180044350
0x180044312  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180044318  jnz     short loc_18004435B
0x18004431a  lea     rcx, ModuleName; "ntdll.dll"
0x180044321  call    cs:__imp_GetModuleHandleW
0x180044327  test    rax, rax
0x18004432a  jz      short loc_18004433D
0x18004432c  mov     rcx, rax
0x18004432f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180044334  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18004433b  jmp     short loc_180044344
0x18004433d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180044344  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004434b  test    rax, rax
0x18004434e  jz      short loc_18004435B
0x180044350  mov     rdx, rbx
0x180044353  mov     rcx, rsi
0x180044356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004435b  mov     rax, rbx
0x18004435e  mov     rbx, [rsp+28h+arg_0]
0x180044363  mov     rsi, [rsp+28h+arg_8]
0x180044368  add     rsp, 20h
0x18004436c  pop     rdi
0x18004436d  retn
```
