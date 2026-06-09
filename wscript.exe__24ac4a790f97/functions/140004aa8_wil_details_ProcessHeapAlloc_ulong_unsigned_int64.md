# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004aa8`
- end: `0x140004b46`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400038f0`
- `0x1400054cc`

## callees

- `0x140004aa8`
- `0x140018010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140004acd`
- `KERNEL32!HeapAlloc` at `0x140004acd`
- `KERNEL32!GetProcAddress` at `0x140004b06`
- `KERNEL32!GetProcAddress` at `0x140004b06`
- `KERNEL32!GetProcessHeap` at `0x140004abc`
- `KERNEL32!GetProcessHeap` at `0x140004abc`
- `KERNEL32!GetModuleHandleW` at `0x140004af1`
- `KERNEL32!GetModuleHandleW` at `0x140004af1`

## string_xrefs

- `0x140004aea`: `ntdll.dll`

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
0x140004aa8  mov     [rsp+arg_0], rbx
0x140004aad  mov     [rsp+arg_8], rsi
0x140004ab2  push    rdi
0x140004ab3  sub     rsp, 20h
0x140004ab7  mov     rbx, rdx
0x140004aba  mov     edi, ecx
0x140004abc  call    cs:__imp_GetProcessHeap
0x140004ac2  mov     r8, rbx; dwBytes
0x140004ac5  mov     edx, edi; dwFlags
0x140004ac7  mov     rcx, rax; hHeap
0x140004aca  mov     rsi, rax
0x140004acd  call    cs:__imp_HeapAlloc
0x140004ad3  mov     rbx, rax
0x140004ad6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140004add  test    rax, rax
0x140004ae0  jnz     short loc_140004B28
0x140004ae2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004ae8  jnz     short loc_140004B33
0x140004aea  lea     rcx, ModuleName; "ntdll.dll"
0x140004af1  call    cs:__imp_GetModuleHandleW
0x140004af7  test    rax, rax
0x140004afa  jz      short loc_140004B15
0x140004afc  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140004b03  mov     rcx, rax; hModule
0x140004b06  call    cs:__imp_GetProcAddress
0x140004b0c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140004b13  jmp     short loc_140004B1C
0x140004b15  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140004b1c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004b23  test    rax, rax
0x140004b26  jz      short loc_140004B33
0x140004b28  mov     rdx, rbx
0x140004b2b  mov     rcx, rsi
0x140004b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b33  mov     rsi, [rsp+28h+arg_8]
0x140004b38  mov     rax, rbx
0x140004b3b  mov     rbx, [rsp+28h+arg_0]
0x140004b40  add     rsp, 20h
0x140004b44  pop     rdi
0x140004b45  retn
```
