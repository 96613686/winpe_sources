# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b550`
- end: `0x18000b5ee`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000514c`
- `0x18000b2c4`
- `0x18000b9d0`
- `0x18000bd68`
- `0x18000f0a8`

## callees

- `0x18000b550`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b5ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b5ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b599`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b599`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b564`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b564`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b575`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b575`

## string_xrefs

- `0x18000b592`: `ntdll.dll`

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
0x18000b550  mov     [rsp+arg_0], rbx
0x18000b555  mov     [rsp+arg_8], rsi
0x18000b55a  push    rdi
0x18000b55b  sub     rsp, 20h
0x18000b55f  mov     rbx, rdx
0x18000b562  mov     edi, ecx
0x18000b564  call    cs:__imp_GetProcessHeap
0x18000b56a  mov     rsi, rax
0x18000b56d  mov     r8, rbx; dwBytes
0x18000b570  mov     edx, edi; dwFlags
0x18000b572  mov     rcx, rax; hHeap
0x18000b575  call    cs:__imp_HeapAlloc
0x18000b57b  mov     rbx, rax
0x18000b57e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b585  test    rax, rax
0x18000b588  jnz     short loc_18000B5D0
0x18000b58a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b590  jnz     short loc_18000B5DB
0x18000b592  lea     rcx, ModuleName; "ntdll.dll"
0x18000b599  call    cs:__imp_GetModuleHandleW
0x18000b59f  test    rax, rax
0x18000b5a2  jz      short loc_18000B5BD
0x18000b5a4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000b5ab  mov     rcx, rax; hModule
0x18000b5ae  call    cs:__imp_GetProcAddress
0x18000b5b4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000b5bb  jmp     short loc_18000B5C4
0x18000b5bd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b5c4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b5cb  test    rax, rax
0x18000b5ce  jz      short loc_18000B5DB
0x18000b5d0  mov     rdx, rbx
0x18000b5d3  mov     rcx, rsi
0x18000b5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5db  mov     rax, rbx
0x18000b5de  mov     rbx, [rsp+28h+arg_0]
0x18000b5e3  mov     rsi, [rsp+28h+arg_8]
0x18000b5e8  add     rsp, 20h
0x18000b5ec  pop     rdi
0x18000b5ed  retn
```
