# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14004868c`
- end: `0x14004872a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400480e0`
- `0x140048230`
- `0x1400496a0`
- `0x140049b20`
- `0x14004af28`

## callees

- `0x14004868c`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400486ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400486ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400486d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400486d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400486b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400486b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400486a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400486a0`

## string_xrefs

- `0x1400486ce`: `ntdll.dll`

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
0x14004868c  mov     [rsp+arg_0], rbx
0x140048691  mov     [rsp+arg_8], rsi
0x140048696  push    rdi
0x140048697  sub     rsp, 20h
0x14004869b  mov     rbx, rdx
0x14004869e  mov     edi, ecx
0x1400486a0  call    cs:__imp_GetProcessHeap
0x1400486a6  mov     rsi, rax
0x1400486a9  mov     r8, rbx; dwBytes
0x1400486ac  mov     edx, edi; dwFlags
0x1400486ae  mov     rcx, rax; hHeap
0x1400486b1  call    cs:__imp_HeapAlloc
0x1400486b7  mov     rbx, rax
0x1400486ba  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400486c1  test    rax, rax
0x1400486c4  jnz     short loc_14004870C
0x1400486c6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400486cc  jnz     short loc_140048717
0x1400486ce  lea     rcx, aNtdllDll; "ntdll.dll"
0x1400486d5  call    cs:__imp_GetModuleHandleW
0x1400486db  test    rax, rax
0x1400486de  jz      short loc_1400486F9
0x1400486e0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400486e7  mov     rcx, rax; hModule
0x1400486ea  call    cs:__imp_GetProcAddress
0x1400486f0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400486f7  jmp     short loc_140048700
0x1400486f9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140048700  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140048707  test    rax, rax
0x14004870a  jz      short loc_140048717
0x14004870c  mov     rdx, rbx
0x14004870f  mov     rcx, rsi
0x140048712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048717  mov     rax, rbx
0x14004871a  mov     rbx, [rsp+28h+arg_0]
0x14004871f  mov     rsi, [rsp+28h+arg_8]
0x140048724  add     rsp, 20h
0x140048728  pop     rdi
0x140048729  retn
```
