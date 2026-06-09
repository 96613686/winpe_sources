# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180037cd4`
- end: `0x180037d8b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003308c`
- `0x180037864`
- `0x180037988`
- `0x1800388a0`
- `0x180038b10`

## callees

- `0x180037cd4`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180037d29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180037d29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037d44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037d44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037cff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037cff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037ce8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037ce8`

## string_xrefs

- `0x180037d22`: `ntdll.dll`

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
0x180037cd4  mov     [rsp+arg_0], rbx
0x180037cd9  mov     [rsp+arg_8], rsi
0x180037cde  push    rdi
0x180037cdf  sub     rsp, 20h
0x180037ce3  mov     rbx, rdx
0x180037ce6  mov     edi, ecx
0x180037ce8  call    cs:__imp_GetProcessHeap
0x180037cef  nop     dword ptr [rax+rax+00h]
0x180037cf4  mov     r8, rbx; dwBytes
0x180037cf7  mov     edx, edi; dwFlags
0x180037cf9  mov     rcx, rax; hHeap
0x180037cfc  mov     rsi, rax
0x180037cff  call    cs:__imp_HeapAlloc
0x180037d06  nop     dword ptr [rax+rax+00h]
0x180037d0b  mov     rbx, rax
0x180037d0e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180037d15  test    rax, rax
0x180037d18  jnz     short loc_180037D6C
0x180037d1a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180037d20  jnz     short loc_180037D77
0x180037d22  lea     rcx, ModuleName; "ntdll.dll"
0x180037d29  call    cs:__imp_GetModuleHandleW
0x180037d30  nop     dword ptr [rax+rax+00h]
0x180037d35  test    rax, rax
0x180037d38  jz      short loc_180037D59
0x180037d3a  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180037d41  mov     rcx, rax; hModule
0x180037d44  call    cs:__imp_GetProcAddress
0x180037d4b  nop     dword ptr [rax+rax+00h]
0x180037d50  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180037d57  jmp     short loc_180037D60
0x180037d59  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180037d60  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180037d67  test    rax, rax
0x180037d6a  jz      short loc_180037D77
0x180037d6c  mov     rdx, rbx
0x180037d6f  mov     rcx, rsi
0x180037d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d77  mov     rsi, [rsp+28h+arg_8]
0x180037d7c  mov     rax, rbx
0x180037d7f  mov     rbx, [rsp+28h+arg_0]
0x180037d84  add     rsp, 20h
0x180037d88  pop     rdi
0x180037d89  retn
```
