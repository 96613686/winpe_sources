# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007838`
- end: `0x1800078ce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000616c`
- `0x180006e10`
- `0x180007dd4`
- `0x18000834c`
- `0x18000b054`
- `0x18000d604`

## callees

- `0x18000454c`
- `0x180007838`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000784c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000784c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000785d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000785d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007881`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007881`

## string_xrefs

- `0x18000787a`: `ntdll.dll`

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
0x180007838  mov     [rsp+arg_0], rbx
0x18000783d  mov     [rsp+arg_8], rsi
0x180007842  push    rdi
0x180007843  sub     rsp, 20h
0x180007847  mov     rbx, rdx
0x18000784a  mov     edi, ecx
0x18000784c  call    cs:__imp_GetProcessHeap
0x180007852  mov     r8, rbx; dwBytes
0x180007855  mov     edx, edi; dwFlags
0x180007857  mov     rcx, rax; hHeap
0x18000785a  mov     rsi, rax
0x18000785d  call    cs:__imp_HeapAlloc
0x180007863  mov     rbx, rax
0x180007866  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000786d  test    rax, rax
0x180007870  jnz     short loc_1800078B0
0x180007872  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007878  jnz     short loc_1800078BB
0x18000787a  lea     rcx, ModuleName; "ntdll.dll"
0x180007881  call    cs:__imp_GetModuleHandleW
0x180007887  test    rax, rax
0x18000788a  jz      short loc_18000789D
0x18000788c  mov     rcx, rax
0x18000788f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180007894  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000789b  jmp     short loc_1800078A4
0x18000789d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800078a4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800078ab  test    rax, rax
0x1800078ae  jz      short loc_1800078BB
0x1800078b0  mov     rdx, rbx
0x1800078b3  mov     rcx, rsi
0x1800078b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078bb  mov     rsi, [rsp+28h+arg_8]
0x1800078c0  mov     rax, rbx
0x1800078c3  mov     rbx, [rsp+28h+arg_0]
0x1800078c8  add     rsp, 20h
0x1800078cc  pop     rdi
0x1800078cd  retn
```
