# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001fc00`
- end: `0x18001fc9e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f734`
- `0x18001f868`
- `0x180020f2c`
- `0x180021158`
- `0x180022500`

## callees

- `0x18001fc00`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fc25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fc25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001fc49`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001fc49`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fc5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fc5e`

## string_xrefs

- `0x18001fc42`: `ntdll.dll`

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
0x18001fc00  mov     [rsp+arg_0], rbx
0x18001fc05  mov     [rsp+arg_8], rsi
0x18001fc0a  push    rdi
0x18001fc0b  sub     rsp, 20h
0x18001fc0f  mov     rbx, rdx
0x18001fc12  mov     edi, ecx
0x18001fc14  call    cs:__imp_GetProcessHeap
0x18001fc1a  mov     r8, rbx; dwBytes
0x18001fc1d  mov     edx, edi; dwFlags
0x18001fc1f  mov     rcx, rax; hHeap
0x18001fc22  mov     rsi, rax
0x18001fc25  call    cs:__imp_HeapAlloc
0x18001fc2b  mov     rbx, rax
0x18001fc2e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001fc35  test    rax, rax
0x18001fc38  jnz     short loc_18001FC80
0x18001fc3a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001fc40  jnz     short loc_18001FC8B
0x18001fc42  lea     rcx, ModuleName; "ntdll.dll"
0x18001fc49  call    cs:__imp_GetModuleHandleW
0x18001fc4f  test    rax, rax
0x18001fc52  jz      short loc_18001FC6D
0x18001fc54  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18001fc5b  mov     rcx, rax; hModule
0x18001fc5e  call    cs:__imp_GetProcAddress
0x18001fc64  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001fc6b  jmp     short loc_18001FC74
0x18001fc6d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001fc74  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001fc7b  test    rax, rax
0x18001fc7e  jz      short loc_18001FC8B
0x18001fc80  mov     rdx, rbx
0x18001fc83  mov     rcx, rsi
0x18001fc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc8b  mov     rsi, [rsp+28h+arg_8]
0x18001fc90  mov     rax, rbx
0x18001fc93  mov     rbx, [rsp+28h+arg_0]
0x18001fc98  add     rsp, 20h
0x18001fc9c  pop     rdi
0x18001fc9d  retn
```
