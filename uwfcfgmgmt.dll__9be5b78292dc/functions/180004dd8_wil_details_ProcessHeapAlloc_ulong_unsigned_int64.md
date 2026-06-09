# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004dd8`
- end: `0x180004e76`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800036bc`
- `0x180003d80`
- `0x180005188`

## callees

- `0x180004dd8`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e36`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e21`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004dfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004dfd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dec`

## string_xrefs

- `0x180004e1a`: `ntdll.dll`

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
0x180004dd8  mov     [rsp+arg_0], rbx
0x180004ddd  mov     [rsp+arg_8], rsi
0x180004de2  push    rdi
0x180004de3  sub     rsp, 20h
0x180004de7  mov     rbx, rdx
0x180004dea  mov     edi, ecx
0x180004dec  call    cs:__imp_GetProcessHeap
0x180004df2  mov     r8, rbx; dwBytes
0x180004df5  mov     edx, edi; dwFlags
0x180004df7  mov     rcx, rax; hHeap
0x180004dfa  mov     rsi, rax
0x180004dfd  call    cs:__imp_HeapAlloc
0x180004e03  mov     rbx, rax
0x180004e06  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004e0d  test    rax, rax
0x180004e10  jnz     short loc_180004E58
0x180004e12  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004e18  jnz     short loc_180004E63
0x180004e1a  lea     rcx, ModuleName; "ntdll.dll"
0x180004e21  call    cs:__imp_GetModuleHandleW
0x180004e27  test    rax, rax
0x180004e2a  jz      short loc_180004E45
0x180004e2c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004e33  mov     rcx, rax; hModule
0x180004e36  call    cs:__imp_GetProcAddress
0x180004e3c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004e43  jmp     short loc_180004E4C
0x180004e45  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004e4c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004e53  test    rax, rax
0x180004e56  jz      short loc_180004E63
0x180004e58  mov     rdx, rbx
0x180004e5b  mov     rcx, rsi
0x180004e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e63  mov     rsi, [rsp+28h+arg_8]
0x180004e68  mov     rax, rbx
0x180004e6b  mov     rbx, [rsp+28h+arg_0]
0x180004e70  add     rsp, 20h
0x180004e74  pop     rdi
0x180004e75  retn
```
