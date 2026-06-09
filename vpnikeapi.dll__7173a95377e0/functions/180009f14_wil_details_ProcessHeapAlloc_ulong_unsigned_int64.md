# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009f14`
- end: `0x180009fb2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009a80`
- `0x180009ba8`
- `0x18000ae54`
- `0x18000b080`
- `0x18000bf00`

## callees

- `0x180009f14`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f39`

## string_xrefs

- `0x180009f56`: `ntdll.dll`

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
0x180009f14  mov     [rsp+arg_0], rbx
0x180009f19  mov     [rsp+arg_8], rsi
0x180009f1e  push    rdi
0x180009f1f  sub     rsp, 20h
0x180009f23  mov     rbx, rdx
0x180009f26  mov     edi, ecx
0x180009f28  call    cs:__imp_GetProcessHeap
0x180009f2e  mov     r8, rbx; dwBytes
0x180009f31  mov     edx, edi; dwFlags
0x180009f33  mov     rcx, rax; hHeap
0x180009f36  mov     rsi, rax
0x180009f39  call    cs:__imp_HeapAlloc
0x180009f3f  mov     rbx, rax
0x180009f42  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009f49  test    rax, rax
0x180009f4c  jnz     short loc_180009F94
0x180009f4e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009f54  jnz     short loc_180009F9F
0x180009f56  lea     rcx, ModuleName; "ntdll.dll"
0x180009f5d  call    cs:__imp_GetModuleHandleW
0x180009f63  test    rax, rax
0x180009f66  jz      short loc_180009F81
0x180009f68  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180009f6f  mov     rcx, rax; hModule
0x180009f72  call    cs:__imp_GetProcAddress
0x180009f78  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180009f7f  jmp     short loc_180009F88
0x180009f81  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009f88  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009f8f  test    rax, rax
0x180009f92  jz      short loc_180009F9F
0x180009f94  mov     rdx, rbx
0x180009f97  mov     rcx, rsi
0x180009f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f9f  mov     rsi, [rsp+28h+arg_8]
0x180009fa4  mov     rax, rbx
0x180009fa7  mov     rbx, [rsp+28h+arg_0]
0x180009fac  add     rsp, 20h
0x180009fb0  pop     rdi
0x180009fb1  retn
```
