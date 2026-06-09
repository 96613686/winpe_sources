# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000215c`
- end: `0x1800021fa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003dd0`
- `0x180004230`
- `0x18000521c`

## callees

- `0x18000215c`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800021ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800021ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800021a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800021a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002170`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002170`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002181`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002181`

## string_xrefs

- `0x18000219e`: `ntdll.dll`

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
0x18000215c  mov     [rsp+arg_0], rbx
0x180002161  mov     [rsp+arg_8], rsi
0x180002166  push    rdi
0x180002167  sub     rsp, 20h
0x18000216b  mov     rbx, rdx
0x18000216e  mov     edi, ecx
0x180002170  call    cs:__imp_GetProcessHeap
0x180002176  mov     rsi, rax
0x180002179  mov     r8, rbx; dwBytes
0x18000217c  mov     edx, edi; dwFlags
0x18000217e  mov     rcx, rax; hHeap
0x180002181  call    cs:__imp_HeapAlloc
0x180002187  mov     rbx, rax
0x18000218a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180002191  test    rax, rax
0x180002194  jnz     short loc_1800021DC
0x180002196  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000219c  jnz     short loc_1800021E7
0x18000219e  lea     rcx, ModuleName; "ntdll.dll"
0x1800021a5  call    cs:__imp_GetModuleHandleW
0x1800021ab  test    rax, rax
0x1800021ae  jz      short loc_1800021C9
0x1800021b0  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800021b7  mov     rcx, rax; hModule
0x1800021ba  call    cs:__imp_GetProcAddress
0x1800021c0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800021c7  jmp     short loc_1800021D0
0x1800021c9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800021d0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800021d7  test    rax, rax
0x1800021da  jz      short loc_1800021E7
0x1800021dc  mov     rdx, rbx
0x1800021df  mov     rcx, rsi
0x1800021e2  call    _guard_dispatch_icall
0x1800021e7  mov     rax, rbx
0x1800021ea  mov     rbx, [rsp+28h+arg_0]
0x1800021ef  mov     rsi, [rsp+28h+arg_8]
0x1800021f4  add     rsp, 20h
0x1800021f8  pop     rdi
0x1800021f9  retn
```
