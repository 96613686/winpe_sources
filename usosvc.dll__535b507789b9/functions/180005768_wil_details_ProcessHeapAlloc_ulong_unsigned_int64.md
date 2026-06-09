# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005768`
- end: `0x180005806`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003f78`
- `0x180004710`
- `0x180005ab4`
- `0x18000b35c`
- `0x18000dfc4`

## callees

- `0x180005768`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800057b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800057b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000577c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000577c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000578d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000578d`

## string_xrefs

- `0x1800057aa`: `ntdll.dll`

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
0x180005768  mov     [rsp+arg_0], rbx
0x18000576d  mov     [rsp+arg_8], rsi
0x180005772  push    rdi
0x180005773  sub     rsp, 20h
0x180005777  mov     rbx, rdx
0x18000577a  mov     edi, ecx
0x18000577c  call    cs:__imp_GetProcessHeap
0x180005782  mov     rsi, rax
0x180005785  mov     r8, rbx; dwBytes
0x180005788  mov     edx, edi; dwFlags
0x18000578a  mov     rcx, rax; hHeap
0x18000578d  call    cs:__imp_HeapAlloc
0x180005793  mov     rbx, rax
0x180005796  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000579d  test    rax, rax
0x1800057a0  jnz     short loc_1800057E8
0x1800057a2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800057a8  jnz     short loc_1800057F3
0x1800057aa  lea     rcx, ModuleName; "ntdll.dll"
0x1800057b1  call    cs:__imp_GetModuleHandleW
0x1800057b7  test    rax, rax
0x1800057ba  jz      short loc_1800057D5
0x1800057bc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800057c3  mov     rcx, rax; hModule
0x1800057c6  call    cs:__imp_GetProcAddress
0x1800057cc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800057d3  jmp     short loc_1800057DC
0x1800057d5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800057dc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800057e3  test    rax, rax
0x1800057e6  jz      short loc_1800057F3
0x1800057e8  mov     rdx, rbx
0x1800057eb  mov     rcx, rsi
0x1800057ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057f3  mov     rax, rbx
0x1800057f6  mov     rbx, [rsp+28h+arg_0]
0x1800057fb  mov     rsi, [rsp+28h+arg_8]
0x180005800  add     rsp, 20h
0x180005804  pop     rdi
0x180005805  retn
```
