# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140008ea8`
- end: `0x140008f46`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000e154`
- `0x140010778`
- `0x140010b80`
- `0x1400117e0`
- `0x140013534`

## callees

- `0x140008ea8`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008f06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008f06`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008ef1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008ef1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ebc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ebc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008ecd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008ecd`

## string_xrefs

- `0x140008eea`: `ntdll.dll`

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
0x140008ea8  mov     [rsp+arg_0], rbx
0x140008ead  mov     [rsp+arg_8], rsi
0x140008eb2  push    rdi
0x140008eb3  sub     rsp, 20h
0x140008eb7  mov     rbx, rdx
0x140008eba  mov     edi, ecx
0x140008ebc  call    cs:__imp_GetProcessHeap
0x140008ec2  mov     rsi, rax
0x140008ec5  mov     r8, rbx; dwBytes
0x140008ec8  mov     edx, edi; dwFlags
0x140008eca  mov     rcx, rax; hHeap
0x140008ecd  call    cs:__imp_HeapAlloc
0x140008ed3  mov     rbx, rax
0x140008ed6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140008edd  test    rax, rax
0x140008ee0  jnz     short loc_140008F28
0x140008ee2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008ee8  jnz     short loc_140008F33
0x140008eea  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140008ef1  call    cs:__imp_GetModuleHandleW
0x140008ef7  test    rax, rax
0x140008efa  jz      short loc_140008F15
0x140008efc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140008f03  mov     rcx, rax; hModule
0x140008f06  call    cs:__imp_GetProcAddress
0x140008f0c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140008f13  jmp     short loc_140008F1C
0x140008f15  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140008f1c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008f23  test    rax, rax
0x140008f26  jz      short loc_140008F33
0x140008f28  mov     rdx, rbx
0x140008f2b  mov     rcx, rsi
0x140008f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f33  mov     rax, rbx
0x140008f36  mov     rbx, [rsp+28h+arg_0]
0x140008f3b  mov     rsi, [rsp+28h+arg_8]
0x140008f40  add     rsp, 20h
0x140008f44  pop     rdi
0x140008f45  retn
```
