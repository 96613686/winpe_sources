# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800094bc`
- end: `0x18000955a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000af08`
- `0x18000b370`
- `0x18000c628`
- `0x1800102fc`

## callees

- `0x1800094bc`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009505`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009505`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000951a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000951a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800094e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800094e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094d0`

## string_xrefs

- `0x1800094fe`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x1800094bc  mov     [rsp+arg_0], rbx
0x1800094c1  mov     [rsp+arg_8], rsi
0x1800094c6  push    rdi
0x1800094c7  sub     rsp, 20h
0x1800094cb  mov     rbx, rdx
0x1800094ce  mov     edi, ecx
0x1800094d0  call    cs:__imp_GetProcessHeap
0x1800094d6  mov     rsi, rax
0x1800094d9  mov     r8, rbx; dwBytes
0x1800094dc  mov     edx, edi; dwFlags
0x1800094de  mov     rcx, rax; hHeap
0x1800094e1  call    cs:__imp_HeapAlloc
0x1800094e7  mov     rbx, rax
0x1800094ea  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800094f1  test    rax, rax
0x1800094f4  jnz     short loc_18000953C
0x1800094f6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800094fc  jnz     short loc_180009547
0x1800094fe  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009505  call    cs:__imp_GetModuleHandleW
0x18000950b  test    rax, rax
0x18000950e  jz      short loc_180009529
0x180009510  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180009517  mov     rcx, rax; hModule
0x18000951a  call    cs:__imp_GetProcAddress
0x180009520  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180009527  jmp     short loc_180009530
0x180009529  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009530  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009537  test    rax, rax
0x18000953a  jz      short loc_180009547
0x18000953c  mov     rdx, rbx
0x18000953f  mov     rcx, rsi
0x180009542  call    _guard_dispatch_icall
0x180009547  mov     rax, rbx
0x18000954a  mov     rbx, [rsp+28h+arg_0]
0x18000954f  mov     rsi, [rsp+28h+arg_8]
0x180009554  add     rsp, 20h
0x180009558  pop     rdi
0x180009559  retn
```
