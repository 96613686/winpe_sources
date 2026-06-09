# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180088260`
- end: `0x180088317`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18006f310`
- `0x180087d38`
- `0x180087e64`
- `0x180088cb8`
- `0x180088f28`

## callees

- `0x180088260`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800882d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800882d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800882b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800882b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088274`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180088274`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008828b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008828b`

## string_xrefs

- `0x1800882ae`: `ntdll.dll`

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
0x180088260  mov     [rsp+arg_0], rbx
0x180088265  mov     [rsp+arg_8], rsi
0x18008826a  push    rdi
0x18008826b  sub     rsp, 20h
0x18008826f  mov     rbx, rdx
0x180088272  mov     edi, ecx
0x180088274  call    cs:__imp_GetProcessHeap
0x18008827b  nop     dword ptr [rax+rax+00h]
0x180088280  mov     r8, rbx; dwBytes
0x180088283  mov     edx, edi; dwFlags
0x180088285  mov     rcx, rax; hHeap
0x180088288  mov     rsi, rax
0x18008828b  call    cs:__imp_HeapAlloc
0x180088292  nop     dword ptr [rax+rax+00h]
0x180088297  mov     rbx, rax
0x18008829a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800882a1  test    rax, rax
0x1800882a4  jnz     short loc_1800882F8
0x1800882a6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800882ac  jnz     short loc_180088303
0x1800882ae  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800882b5  call    cs:__imp_GetModuleHandleW
0x1800882bc  nop     dword ptr [rax+rax+00h]
0x1800882c1  test    rax, rax
0x1800882c4  jz      short loc_1800882E5
0x1800882c6  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800882cd  mov     rcx, rax; hModule
0x1800882d0  call    cs:__imp_GetProcAddress
0x1800882d7  nop     dword ptr [rax+rax+00h]
0x1800882dc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800882e3  jmp     short loc_1800882EC
0x1800882e5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800882ec  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800882f3  test    rax, rax
0x1800882f6  jz      short loc_180088303
0x1800882f8  mov     rdx, rbx
0x1800882fb  mov     rcx, rsi
0x1800882fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088303  mov     rsi, [rsp+28h+arg_8]
0x180088308  mov     rax, rbx
0x18008830b  mov     rbx, [rsp+28h+arg_0]
0x180088310  add     rsp, 20h
0x180088314  pop     rdi
0x180088315  retn
```
