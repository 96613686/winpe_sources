# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140012db8`
- end: `0x140012e56`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000c4c0`
- `0x14002e300`
- `0x14002e43c`

## callees

- `0x140012db8`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012e16`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012e16`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012e01`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012e01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012dcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012dcc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012ddd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140012ddd`

## string_xrefs

- `0x140012dfa`: `ntdll.dll`

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
0x140012db8  mov     [rsp+arg_0], rbx
0x140012dbd  mov     [rsp+arg_8], rsi
0x140012dc2  push    rdi
0x140012dc3  sub     rsp, 20h
0x140012dc7  mov     rbx, rdx
0x140012dca  mov     edi, ecx
0x140012dcc  call    cs:__imp_GetProcessHeap
0x140012dd2  mov     rsi, rax
0x140012dd5  mov     r8, rbx; dwBytes
0x140012dd8  mov     edx, edi; dwFlags
0x140012dda  mov     rcx, rax; hHeap
0x140012ddd  call    cs:__imp_HeapAlloc
0x140012de3  mov     rbx, rax
0x140012de6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140012ded  test    rax, rax
0x140012df0  jnz     short loc_140012E38
0x140012df2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140012df8  jnz     short loc_140012E43
0x140012dfa  lea     rcx, ModuleName; "ntdll.dll"
0x140012e01  call    cs:__imp_GetModuleHandleW
0x140012e07  test    rax, rax
0x140012e0a  jz      short loc_140012E25
0x140012e0c  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140012e13  mov     rcx, rax; hModule
0x140012e16  call    cs:__imp_GetProcAddress
0x140012e1c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140012e23  jmp     short loc_140012E2C
0x140012e25  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140012e2c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140012e33  test    rax, rax
0x140012e36  jz      short loc_140012E43
0x140012e38  mov     rdx, rbx
0x140012e3b  mov     rcx, rsi
0x140012e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e43  mov     rax, rbx
0x140012e46  mov     rbx, [rsp+28h+arg_0]
0x140012e4b  mov     rsi, [rsp+28h+arg_8]
0x140012e50  add     rsp, 20h
0x140012e54  pop     rdi
0x140012e55  retn
```
