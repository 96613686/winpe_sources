# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006678`
- end: `0x180006716`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003e4c`
- `0x1800041f0`
- `0x180005100`
- `0x180007c88`
- `0x180008d9c`

## callees

- `0x180006678`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000669d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000669d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000668c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000668c`

## string_xrefs

- `0x1800066ba`: `ntdll.dll`

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
0x180006678  mov     [rsp+arg_0], rbx
0x18000667d  mov     [rsp+arg_8], rsi
0x180006682  push    rdi
0x180006683  sub     rsp, 20h
0x180006687  mov     rbx, rdx
0x18000668a  mov     edi, ecx
0x18000668c  call    cs:__imp_GetProcessHeap
0x180006692  mov     r8, rbx; dwBytes
0x180006695  mov     edx, edi; dwFlags
0x180006697  mov     rcx, rax; hHeap
0x18000669a  mov     rsi, rax
0x18000669d  call    cs:__imp_HeapAlloc
0x1800066a3  mov     rbx, rax
0x1800066a6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800066ad  test    rax, rax
0x1800066b0  jnz     short loc_1800066F8
0x1800066b2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800066b8  jnz     short loc_180006703
0x1800066ba  lea     rcx, ModuleName; "ntdll.dll"
0x1800066c1  call    cs:__imp_GetModuleHandleW
0x1800066c7  test    rax, rax
0x1800066ca  jz      short loc_1800066E5
0x1800066cc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800066d3  mov     rcx, rax; hModule
0x1800066d6  call    cs:__imp_GetProcAddress
0x1800066dc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800066e3  jmp     short loc_1800066EC
0x1800066e5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800066ec  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800066f3  test    rax, rax
0x1800066f6  jz      short loc_180006703
0x1800066f8  mov     rdx, rbx
0x1800066fb  mov     rcx, rsi
0x1800066fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006703  mov     rsi, [rsp+28h+arg_8]
0x180006708  mov     rax, rbx
0x18000670b  mov     rbx, [rsp+28h+arg_0]
0x180006710  add     rsp, 20h
0x180006714  pop     rdi
0x180006715  retn
```
