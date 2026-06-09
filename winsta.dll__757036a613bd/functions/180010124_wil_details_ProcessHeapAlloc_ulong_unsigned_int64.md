# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180010124`
- end: `0x1800101ba`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001f6c0`
- `0x180026c44`
- `0x180027458`
- `0x1800275d0`

## callees

- `0x180010124`
- `0x180024760`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001016d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001016d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010149`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010149`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010138`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010138`

## string_xrefs

- `0x180010166`: `ntdll.dll`

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
0x180010124  mov     [rsp+arg_0], rbx
0x180010129  mov     [rsp+arg_8], rsi
0x18001012e  push    rdi
0x18001012f  sub     rsp, 20h
0x180010133  mov     rbx, rdx
0x180010136  mov     edi, ecx
0x180010138  call    cs:__imp_GetProcessHeap
0x18001013e  mov     r8, rbx; dwBytes
0x180010141  mov     edx, edi; dwFlags
0x180010143  mov     rcx, rax; hHeap
0x180010146  mov     rsi, rax
0x180010149  call    cs:__imp_HeapAlloc
0x18001014f  mov     rbx, rax
0x180010152  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010159  test    rax, rax
0x18001015c  jnz     short loc_180010193
0x18001015e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180010164  jnz     short loc_18001019E
0x180010166  lea     rcx, ModuleName; "ntdll.dll"
0x18001016d  call    cs:__imp_GetModuleHandleW
0x180010173  test    rax, rax
0x180010176  jz      short loc_1800101B1
0x180010178  mov     rcx, rax
0x18001017b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180010180  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180010187  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001018e  test    rax, rax
0x180010191  jz      short loc_18001019E
0x180010193  mov     rdx, rbx
0x180010196  mov     rcx, rsi
0x180010199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001019e  mov     rsi, [rsp+28h+arg_8]
0x1800101a3  mov     rax, rbx
0x1800101a6  mov     rbx, [rsp+28h+arg_0]
0x1800101ab  add     rsp, 20h
0x1800101af  pop     rdi
0x1800101b0  retn
0x1800101b1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800101b8  jmp     short loc_180010187
```
