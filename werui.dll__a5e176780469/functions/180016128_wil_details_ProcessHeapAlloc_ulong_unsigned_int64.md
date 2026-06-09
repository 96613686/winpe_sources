# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180016128`
- end: `0x1800161c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180015fd8`
- `0x180016364`
- `0x1800164a0`

## callees

- `0x180016128`
- `0x180018010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001614d`
- `KERNEL32!HeapAlloc` at `0x18001614d`
- `KERNEL32!GetProcessHeap` at `0x18001613c`
- `KERNEL32!GetProcessHeap` at `0x18001613c`
- `KERNEL32!GetModuleHandleW` at `0x180016171`
- `KERNEL32!GetModuleHandleW` at `0x180016171`
- `KERNEL32!GetProcAddress` at `0x180016186`
- `KERNEL32!GetProcAddress` at `0x180016186`

## string_xrefs

- `0x18001616a`: `ntdll.dll`

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
0x180016128  mov     [rsp+arg_0], rbx
0x18001612d  mov     [rsp+arg_8], rsi
0x180016132  push    rdi
0x180016133  sub     rsp, 20h
0x180016137  mov     rbx, rdx
0x18001613a  mov     edi, ecx
0x18001613c  call    cs:__imp_GetProcessHeap
0x180016142  mov     r8, rbx; dwBytes
0x180016145  mov     edx, edi; dwFlags
0x180016147  mov     rcx, rax; hHeap
0x18001614a  mov     rsi, rax
0x18001614d  call    cs:__imp_HeapAlloc
0x180016153  mov     rbx, rax
0x180016156  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001615d  test    rax, rax
0x180016160  jnz     short loc_1800161A8
0x180016162  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180016168  jnz     short loc_1800161B3
0x18001616a  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x180016171  call    cs:__imp_GetModuleHandleW
0x180016177  test    rax, rax
0x18001617a  jz      short loc_180016195
0x18001617c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180016183  mov     rcx, rax; hModule
0x180016186  call    cs:__imp_GetProcAddress
0x18001618c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180016193  jmp     short loc_18001619C
0x180016195  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001619c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800161a3  test    rax, rax
0x1800161a6  jz      short loc_1800161B3
0x1800161a8  mov     rdx, rbx
0x1800161ab  mov     rcx, rsi
0x1800161ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161b3  mov     rsi, [rsp+28h+arg_8]
0x1800161b8  mov     rax, rbx
0x1800161bb  mov     rbx, [rsp+28h+arg_0]
0x1800161c0  add     rsp, 20h
0x1800161c4  pop     rdi
0x1800161c5  retn
```
