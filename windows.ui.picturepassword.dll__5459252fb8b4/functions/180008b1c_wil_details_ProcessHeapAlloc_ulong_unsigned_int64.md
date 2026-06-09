# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008b1c`
- end: `0x180008bba`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000755c`
- `0x1800083f8`
- `0x1800095cc`
- `0x180009a34`
- `0x18001b6f4`
- `0x18001cce0`

## callees

- `0x180008b1c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b41`

## string_xrefs

- `0x180008b5e`: `ntdll.dll`

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
0x180008b1c  mov     [rsp+arg_0], rbx
0x180008b21  mov     [rsp+arg_8], rsi
0x180008b26  push    rdi
0x180008b27  sub     rsp, 20h
0x180008b2b  mov     rbx, rdx
0x180008b2e  mov     edi, ecx
0x180008b30  call    cs:__imp_GetProcessHeap
0x180008b36  mov     r8, rbx; dwBytes
0x180008b39  mov     edx, edi; dwFlags
0x180008b3b  mov     rcx, rax; hHeap
0x180008b3e  mov     rsi, rax
0x180008b41  call    cs:__imp_HeapAlloc
0x180008b47  mov     rbx, rax
0x180008b4a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008b51  test    rax, rax
0x180008b54  jnz     short loc_180008B9C
0x180008b56  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008b5c  jnz     short loc_180008BA7
0x180008b5e  lea     rcx, ModuleName; "ntdll.dll"
0x180008b65  call    cs:__imp_GetModuleHandleW
0x180008b6b  test    rax, rax
0x180008b6e  jz      short loc_180008B89
0x180008b70  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180008b77  mov     rcx, rax; hModule
0x180008b7a  call    cs:__imp_GetProcAddress
0x180008b80  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008b87  jmp     short loc_180008B90
0x180008b89  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008b90  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008b97  test    rax, rax
0x180008b9a  jz      short loc_180008BA7
0x180008b9c  mov     rdx, rbx
0x180008b9f  mov     rcx, rsi
0x180008ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ba7  mov     rsi, [rsp+28h+arg_8]
0x180008bac  mov     rax, rbx
0x180008baf  mov     rbx, [rsp+28h+arg_0]
0x180008bb4  add     rsp, 20h
0x180008bb8  pop     rdi
0x180008bb9  retn
```
