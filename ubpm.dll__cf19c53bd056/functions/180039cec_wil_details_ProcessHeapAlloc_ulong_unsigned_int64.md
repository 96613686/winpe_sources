# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180039cec`
- end: `0x180039d8a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002fad4`
- `0x180039880`
- `0x1800399b0`
- `0x18003a960`
- `0x18003abc4`

## callees

- `0x180039cec`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039d4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039d4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039d35`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039d35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039d11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039d11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039d00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039d00`

## string_xrefs

- `0x180039d2e`: `ntdll.dll`

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
0x180039cec  mov     [rsp+arg_0], rbx
0x180039cf1  mov     [rsp+arg_8], rsi
0x180039cf6  push    rdi
0x180039cf7  sub     rsp, 20h
0x180039cfb  mov     rbx, rdx
0x180039cfe  mov     edi, ecx
0x180039d00  call    cs:__imp_GetProcessHeap
0x180039d06  mov     r8, rbx; dwBytes
0x180039d09  mov     edx, edi; dwFlags
0x180039d0b  mov     rcx, rax; hHeap
0x180039d0e  mov     rsi, rax
0x180039d11  call    cs:__imp_HeapAlloc
0x180039d17  mov     rbx, rax
0x180039d1a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180039d21  test    rax, rax
0x180039d24  jnz     short loc_180039D6C
0x180039d26  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180039d2c  jnz     short loc_180039D77
0x180039d2e  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180039d35  call    cs:__imp_GetModuleHandleW
0x180039d3b  test    rax, rax
0x180039d3e  jz      short loc_180039D59
0x180039d40  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180039d47  mov     rcx, rax; hModule
0x180039d4a  call    cs:__imp_GetProcAddress
0x180039d50  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180039d57  jmp     short loc_180039D60
0x180039d59  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180039d60  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180039d67  test    rax, rax
0x180039d6a  jz      short loc_180039D77
0x180039d6c  mov     rdx, rbx
0x180039d6f  mov     rcx, rsi
0x180039d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d77  mov     rsi, [rsp+28h+arg_8]
0x180039d7c  mov     rax, rbx
0x180039d7f  mov     rbx, [rsp+28h+arg_0]
0x180039d84  add     rsp, 20h
0x180039d88  pop     rdi
0x180039d89  retn
```
