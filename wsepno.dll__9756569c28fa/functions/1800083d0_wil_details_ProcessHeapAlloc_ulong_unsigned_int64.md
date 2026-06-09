# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800083d0`
- end: `0x18000846e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000558c`
- `0x18000595c`
- `0x1800071a0`
- `0x18000a398`
- `0x18000b74c`

## callees

- `0x1800083d0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000842e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000842e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008419`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008419`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800083f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800083f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083e4`

## string_xrefs

- `0x180008412`: `ntdll.dll`

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
0x1800083d0  mov     [rsp+arg_0], rbx
0x1800083d5  mov     [rsp+arg_8], rsi
0x1800083da  push    rdi
0x1800083db  sub     rsp, 20h
0x1800083df  mov     rbx, rdx
0x1800083e2  mov     edi, ecx
0x1800083e4  call    cs:__imp_GetProcessHeap
0x1800083ea  mov     rsi, rax
0x1800083ed  mov     r8, rbx; dwBytes
0x1800083f0  mov     edx, edi; dwFlags
0x1800083f2  mov     rcx, rax; hHeap
0x1800083f5  call    cs:__imp_HeapAlloc
0x1800083fb  mov     rbx, rax
0x1800083fe  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008405  test    rax, rax
0x180008408  jnz     short loc_180008450
0x18000840a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008410  jnz     short loc_18000845B
0x180008412  lea     rcx, ModuleName; "ntdll.dll"
0x180008419  call    cs:__imp_GetModuleHandleW
0x18000841f  test    rax, rax
0x180008422  jz      short loc_18000843D
0x180008424  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000842b  mov     rcx, rax; hModule
0x18000842e  call    cs:__imp_GetProcAddress
0x180008434  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000843b  jmp     short loc_180008444
0x18000843d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008444  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000844b  test    rax, rax
0x18000844e  jz      short loc_18000845B
0x180008450  mov     rdx, rbx
0x180008453  mov     rcx, rsi
0x180008456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000845b  mov     rax, rbx
0x18000845e  mov     rbx, [rsp+28h+arg_0]
0x180008463  mov     rsi, [rsp+28h+arg_8]
0x180008468  add     rsp, 20h
0x18000846c  pop     rdi
0x18000846d  retn
```
