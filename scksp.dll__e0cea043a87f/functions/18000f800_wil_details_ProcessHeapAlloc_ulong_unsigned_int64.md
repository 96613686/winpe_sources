# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000f800`
- end: `0x18000f89f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f2cc`
- `0x18000f3fc`
- `0x180010d30`
- `0x1800111b8`
- `0x180012560`

## callees

- `0x18000f800`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f85e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f85e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f849`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f849`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f825`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f825`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f814`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f814`

## string_xrefs

- `0x18000f842`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000f800  mov     [rsp+arg_0], rbx
0x18000f805  mov     [rsp+arg_8], rsi
0x18000f80a  push    rdi
0x18000f80b  sub     rsp, 20h
0x18000f80f  mov     rbx, rdx
0x18000f812  mov     edi, ecx
0x18000f814  call    cs:__imp_GetProcessHeap
0x18000f81a  mov     rsi, rax
0x18000f81d  mov     r8, rbx; dwBytes
0x18000f820  mov     edx, edi; dwFlags
0x18000f822  mov     rcx, rax; hHeap
0x18000f825  call    cs:__imp_HeapAlloc
0x18000f82b  mov     rbx, rax
0x18000f82e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000f835  test    rax, rax
0x18000f838  jnz     short loc_18000F881
0x18000f83a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000f840  jnz     short loc_18000F88C
0x18000f842  lea     rcx, ModuleName; "ntdll.dll"
0x18000f849  call    cs:__imp_GetModuleHandleW
0x18000f84f  test    rax, rax
0x18000f852  jz      short loc_18000F86E
0x18000f854  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000f85b  mov     rcx, rax; hModule
0x18000f85e  call    cs:__imp_GetProcAddress
0x18000f864  nop
0x18000f865  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000f86c  jmp     short loc_18000F875
0x18000f86e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000f875  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000f87c  test    rax, rax
0x18000f87f  jz      short loc_18000F88C
0x18000f881  mov     rdx, rbx
0x18000f884  mov     rcx, rsi
0x18000f887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f88c  mov     rax, rbx
0x18000f88f  mov     rbx, [rsp+28h+arg_0]
0x18000f894  mov     rsi, [rsp+28h+arg_8]
0x18000f899  add     rsp, 20h
0x18000f89d  pop     rdi
0x18000f89e  retn
```
