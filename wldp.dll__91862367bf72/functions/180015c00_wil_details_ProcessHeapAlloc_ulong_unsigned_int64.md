# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180015c00`
- end: `0x180015c9e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800029c0`
- `0x180002aa0`
- `0x180002d80`
- `0x1800032c4`
- `0x180005660`
- `0x1800058c4`
- `0x180005ad0`
- `0x180025958`
- `0x180025af0`
- `0x180026110`
- `0x1800264a8`

## callees

- `0x180015c00`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015c49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015c49`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015c5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015c5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015c14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015c14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015c25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015c25`

## string_xrefs

- `0x180015c42`: `ntdll.dll`

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
0x180015c00  mov     [rsp+arg_0], rbx
0x180015c05  mov     [rsp+arg_8], rsi
0x180015c0a  push    rdi
0x180015c0b  sub     rsp, 20h
0x180015c0f  mov     rbx, rdx
0x180015c12  mov     edi, ecx
0x180015c14  call    cs:__imp_GetProcessHeap
0x180015c1a  mov     rsi, rax
0x180015c1d  mov     r8, rbx; dwBytes
0x180015c20  mov     edx, edi; dwFlags
0x180015c22  mov     rcx, rax; hHeap
0x180015c25  call    cs:__imp_HeapAlloc
0x180015c2b  mov     rbx, rax
0x180015c2e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180015c35  test    rax, rax
0x180015c38  jnz     short loc_180015C77
0x180015c3a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180015c40  jnz     short loc_180015C82
0x180015c42  lea     rcx, ModuleName; "ntdll.dll"
0x180015c49  call    cs:__imp_GetModuleHandleW
0x180015c4f  test    rax, rax
0x180015c52  jz      short loc_180015C95
0x180015c54  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180015c5b  mov     rcx, rax; hModule
0x180015c5e  call    cs:__imp_GetProcAddress
0x180015c64  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180015c6b  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180015c72  test    rax, rax
0x180015c75  jz      short loc_180015C82
0x180015c77  mov     rdx, rbx
0x180015c7a  mov     rcx, rsi
0x180015c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c82  mov     rax, rbx
0x180015c85  mov     rbx, [rsp+28h+arg_0]
0x180015c8a  mov     rsi, [rsp+28h+arg_8]
0x180015c8f  add     rsp, 20h
0x180015c93  pop     rdi
0x180015c94  retn
0x180015c95  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180015c9c  jmp     short loc_180015C6B
```
