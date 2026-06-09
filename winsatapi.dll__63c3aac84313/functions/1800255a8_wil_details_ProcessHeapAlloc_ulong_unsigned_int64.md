# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800255a8`
- end: `0x180025648`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `160`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001208c`
- `0x1800121e0`
- `0x1800260dc`
- `0x180026560`
- `0x180029a50`

## callees

- `0x180021cdc`
- `0x1800255a8`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800255fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800255fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800255d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800255d7`

## string_xrefs

- `0x1800255f4`: `ntdll.dll`

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
0x1800255a8  push    rdi
0x1800255aa  sub     rsp, 30h
0x1800255ae  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800255b7  mov     [rsp+38h+arg_0], rbx
0x1800255bc  mov     [rsp+38h+arg_8], rsi
0x1800255c1  mov     rbx, rdx
0x1800255c4  mov     edi, ecx
0x1800255c6  call    cs:__imp_GetProcessHeap
0x1800255cc  mov     rsi, rax
0x1800255cf  mov     r8, rbx; dwBytes
0x1800255d2  mov     edx, edi; dwFlags
0x1800255d4  mov     rcx, rax; hHeap
0x1800255d7  call    cs:__imp_HeapAlloc
0x1800255dd  mov     rbx, rax
0x1800255e0  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800255e7  test    rax, rax
0x1800255ea  jnz     short loc_18002562A
0x1800255ec  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800255f2  jnz     short loc_180025635
0x1800255f4  lea     rcx, LibFileName; "ntdll.dll"
0x1800255fb  call    cs:__imp_GetModuleHandleW
0x180025601  test    rax, rax
0x180025604  jz      short loc_180025617
0x180025606  mov     rcx, rax
0x180025609  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18002560e  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180025615  jmp     short loc_18002561E
0x180025617  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002561e  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180025625  test    rax, rax
0x180025628  jz      short loc_180025635
0x18002562a  mov     rdx, rbx
0x18002562d  mov     rcx, rsi
0x180025630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025635  mov     rax, rbx
0x180025638  mov     rbx, [rsp+38h+arg_0]
0x18002563d  mov     rsi, [rsp+38h+arg_8]
0x180025642  add     rsp, 30h
0x180025646  pop     rdi
0x180025647  retn
```
