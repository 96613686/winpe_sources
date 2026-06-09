# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800195a8`
- end: `0x180019646`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800191a8`
- `0x1800192d0`
- `0x18001a404`
- `0x18001a630`
- `0x18001b450`

## callees

- `0x1800195a8`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800195bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800195bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800195cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800195cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800195f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800195f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019606`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019606`

## string_xrefs

- `0x1800195ea`: `ntdll.dll`

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
0x1800195a8  mov     [rsp+arg_0], rbx
0x1800195ad  mov     [rsp+arg_8], rsi
0x1800195b2  push    rdi
0x1800195b3  sub     rsp, 20h
0x1800195b7  mov     rbx, rdx
0x1800195ba  mov     edi, ecx
0x1800195bc  call    cs:__imp_GetProcessHeap
0x1800195c2  mov     r8, rbx; dwBytes
0x1800195c5  mov     edx, edi; dwFlags
0x1800195c7  mov     rcx, rax; hHeap
0x1800195ca  mov     rsi, rax
0x1800195cd  call    cs:__imp_HeapAlloc
0x1800195d3  mov     rbx, rax
0x1800195d6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800195dd  test    rax, rax
0x1800195e0  jnz     short loc_180019628
0x1800195e2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800195e8  jnz     short loc_180019633
0x1800195ea  lea     rcx, ModuleName; "ntdll.dll"
0x1800195f1  call    cs:__imp_GetModuleHandleW
0x1800195f7  test    rax, rax
0x1800195fa  jz      short loc_180019615
0x1800195fc  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180019603  mov     rcx, rax; hModule
0x180019606  call    cs:__imp_GetProcAddress
0x18001960c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180019613  jmp     short loc_18001961C
0x180019615  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001961c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180019623  test    rax, rax
0x180019626  jz      short loc_180019633
0x180019628  mov     rdx, rbx
0x18001962b  mov     rcx, rsi
0x18001962e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019633  mov     rsi, [rsp+28h+arg_8]
0x180019638  mov     rax, rbx
0x18001963b  mov     rbx, [rsp+28h+arg_0]
0x180019640  add     rsp, 20h
0x180019644  pop     rdi
0x180019645  retn
```
