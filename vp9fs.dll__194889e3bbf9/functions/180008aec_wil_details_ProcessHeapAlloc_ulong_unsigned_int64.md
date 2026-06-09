# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008aec`
- end: `0x180008b8a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000671c`
- `0x180006af8`
- `0x1800078a0`
- `0x18000a0d4`
- `0x18000b8cc`

## callees

- `0x180008aec`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b35`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b11`

## string_xrefs

- `0x180008b2e`: `ntdll.dll`

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
0x180008aec  mov     [rsp+arg_0], rbx
0x180008af1  mov     [rsp+arg_8], rsi
0x180008af6  push    rdi
0x180008af7  sub     rsp, 20h
0x180008afb  mov     rbx, rdx
0x180008afe  mov     edi, ecx
0x180008b00  call    cs:__imp_GetProcessHeap
0x180008b06  mov     rsi, rax
0x180008b09  mov     r8, rbx; dwBytes
0x180008b0c  mov     edx, edi; dwFlags
0x180008b0e  mov     rcx, rax; hHeap
0x180008b11  call    cs:__imp_HeapAlloc
0x180008b17  mov     rbx, rax
0x180008b1a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008b21  test    rax, rax
0x180008b24  jnz     short loc_180008B6C
0x180008b26  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008b2c  jnz     short loc_180008B77
0x180008b2e  lea     rcx, ModuleName; "ntdll.dll"
0x180008b35  call    cs:__imp_GetModuleHandleW
0x180008b3b  test    rax, rax
0x180008b3e  jz      short loc_180008B59
0x180008b40  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008b47  mov     rcx, rax; hModule
0x180008b4a  call    cs:__imp_GetProcAddress
0x180008b50  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008b57  jmp     short loc_180008B60
0x180008b59  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008b60  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008b67  test    rax, rax
0x180008b6a  jz      short loc_180008B77
0x180008b6c  mov     rdx, rbx
0x180008b6f  mov     rcx, rsi
0x180008b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b77  mov     rax, rbx
0x180008b7a  mov     rbx, [rsp+28h+arg_0]
0x180008b7f  mov     rsi, [rsp+28h+arg_8]
0x180008b84  add     rsp, 20h
0x180008b88  pop     rdi
0x180008b89  retn
```
