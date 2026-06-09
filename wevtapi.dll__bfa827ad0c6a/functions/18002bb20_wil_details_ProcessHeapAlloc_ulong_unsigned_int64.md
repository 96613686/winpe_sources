# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002bb20`
- end: `0x18002bbbe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800202a0`
- `0x18002b640`
- `0x18002b764`
- `0x18002c4b0`
- `0x18002c714`

## callees

- `0x18002bb20`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bb34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bb34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bb45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002bb45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bb7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bb7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002bb69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002bb69`

## string_xrefs

- `0x18002bb62`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress) )
  {
    ((void (__fastcall *)(HANDLE, LPVOID))ProcAddress)(ProcessHeap, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18002bb20  mov     [rsp+arg_0], rbx
0x18002bb25  mov     [rsp+arg_8], rsi
0x18002bb2a  push    rdi
0x18002bb2b  sub     rsp, 20h
0x18002bb2f  mov     rbx, rdx
0x18002bb32  mov     edi, ecx
0x18002bb34  call    cs:__imp_GetProcessHeap
0x18002bb3a  mov     rsi, rax
0x18002bb3d  mov     r8, rbx; dwBytes
0x18002bb40  mov     edx, edi; dwFlags
0x18002bb42  mov     rcx, rax; hHeap
0x18002bb45  call    cs:__imp_HeapAlloc
0x18002bb4b  mov     rbx, rax
0x18002bb4e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002bb55  test    rax, rax
0x18002bb58  jnz     short loc_18002BBA0
0x18002bb5a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002bb60  jnz     short loc_18002BBAB
0x18002bb62  lea     rcx, ModuleName; "ntdll.dll"
0x18002bb69  call    cs:__imp_GetModuleHandleW
0x18002bb6f  test    rax, rax
0x18002bb72  jz      short loc_18002BB8D
0x18002bb74  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18002bb7b  mov     rcx, rax; hModule
0x18002bb7e  call    cs:__imp_GetProcAddress
0x18002bb84  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002bb8b  jmp     short loc_18002BB94
0x18002bb8d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002bb94  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002bb9b  test    rax, rax
0x18002bb9e  jz      short loc_18002BBAB
0x18002bba0  mov     rdx, rbx
0x18002bba3  mov     rcx, rsi
0x18002bba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbab  mov     rax, rbx
0x18002bbae  mov     rbx, [rsp+28h+arg_0]
0x18002bbb3  mov     rsi, [rsp+28h+arg_8]
0x18002bbb8  add     rsp, 20h
0x18002bbbc  pop     rdi
0x18002bbbd  retn
```
