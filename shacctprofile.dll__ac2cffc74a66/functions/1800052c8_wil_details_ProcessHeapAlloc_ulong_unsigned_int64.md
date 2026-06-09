# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800052c8`
- end: `0x180005366`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003bd0`
- `0x180004280`
- `0x180005610`

## callees

- `0x1800052c8`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005326`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005326`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005311`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800052ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800052ed`

## string_xrefs

- `0x18000530a`: `ntdll.dll`

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
0x1800052c8  mov     [rsp+arg_0], rbx
0x1800052cd  mov     [rsp+arg_8], rsi
0x1800052d2  push    rdi
0x1800052d3  sub     rsp, 20h
0x1800052d7  mov     rbx, rdx
0x1800052da  mov     edi, ecx
0x1800052dc  call    cs:__imp_GetProcessHeap
0x1800052e2  mov     r8, rbx; dwBytes
0x1800052e5  mov     edx, edi; dwFlags
0x1800052e7  mov     rcx, rax; hHeap
0x1800052ea  mov     rsi, rax
0x1800052ed  call    cs:__imp_HeapAlloc
0x1800052f3  mov     rbx, rax
0x1800052f6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800052fd  test    rax, rax
0x180005300  jnz     short loc_180005348
0x180005302  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005308  jnz     short loc_180005353
0x18000530a  lea     rcx, ModuleName; "ntdll.dll"
0x180005311  call    cs:__imp_GetModuleHandleW
0x180005317  test    rax, rax
0x18000531a  jz      short loc_180005335
0x18000531c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005323  mov     rcx, rax; hModule
0x180005326  call    cs:__imp_GetProcAddress
0x18000532c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005333  jmp     short loc_18000533C
0x180005335  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000533c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005343  test    rax, rax
0x180005346  jz      short loc_180005353
0x180005348  mov     rdx, rbx
0x18000534b  mov     rcx, rsi
0x18000534e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005353  mov     rsi, [rsp+28h+arg_8]
0x180005358  mov     rax, rbx
0x18000535b  mov     rbx, [rsp+28h+arg_0]
0x180005360  add     rsp, 20h
0x180005364  pop     rdi
0x180005365  retn
```
