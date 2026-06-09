# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008c20`
- end: `0x180008cbe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008970`
- `0x180009080`
- `0x180009418`
- `0x18000ac00`
- `0x18000c6a4`

## callees

- `0x180008c20`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008c7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008c7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c45`

## string_xrefs

- `0x180008c62`: `ntdll.dll`

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
0x180008c20  mov     [rsp+arg_0], rbx
0x180008c25  mov     [rsp+arg_8], rsi
0x180008c2a  push    rdi
0x180008c2b  sub     rsp, 20h
0x180008c2f  mov     rbx, rdx
0x180008c32  mov     edi, ecx
0x180008c34  call    cs:__imp_GetProcessHeap
0x180008c3a  mov     rsi, rax
0x180008c3d  mov     r8, rbx; dwBytes
0x180008c40  mov     edx, edi; dwFlags
0x180008c42  mov     rcx, rax; hHeap
0x180008c45  call    cs:__imp_HeapAlloc
0x180008c4b  mov     rbx, rax
0x180008c4e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008c55  test    rax, rax
0x180008c58  jnz     short loc_180008CA0
0x180008c5a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008c60  jnz     short loc_180008CAB
0x180008c62  lea     rcx, ModuleName; "ntdll.dll"
0x180008c69  call    cs:__imp_GetModuleHandleW
0x180008c6f  test    rax, rax
0x180008c72  jz      short loc_180008C8D
0x180008c74  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180008c7b  mov     rcx, rax; hModule
0x180008c7e  call    cs:__imp_GetProcAddress
0x180008c84  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008c8b  jmp     short loc_180008C94
0x180008c8d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008c94  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008c9b  test    rax, rax
0x180008c9e  jz      short loc_180008CAB
0x180008ca0  mov     rdx, rbx
0x180008ca3  mov     rcx, rsi
0x180008ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cab  mov     rax, rbx
0x180008cae  mov     rbx, [rsp+28h+arg_0]
0x180008cb3  mov     rsi, [rsp+28h+arg_8]
0x180008cb8  add     rsp, 20h
0x180008cbc  pop     rdi
0x180008cbd  retn
```
