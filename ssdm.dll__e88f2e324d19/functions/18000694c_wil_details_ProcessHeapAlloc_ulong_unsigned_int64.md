# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000694c`
- end: `0x1800069ea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005a9c`
- `0x180008080`
- `0x180009474`

## callees

- `0x18000694c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006995`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006995`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800069aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800069aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006960`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006971`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006971`

## string_xrefs

- `0x18000698e`: `ntdll.dll`

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
0x18000694c  mov     [rsp+arg_0], rbx
0x180006951  mov     [rsp+arg_8], rsi
0x180006956  push    rdi
0x180006957  sub     rsp, 20h
0x18000695b  mov     rbx, rdx
0x18000695e  mov     edi, ecx
0x180006960  call    cs:__imp_GetProcessHeap
0x180006966  mov     rsi, rax
0x180006969  mov     r8, rbx; dwBytes
0x18000696c  mov     edx, edi; dwFlags
0x18000696e  mov     rcx, rax; hHeap
0x180006971  call    cs:__imp_HeapAlloc
0x180006977  mov     rbx, rax
0x18000697a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006981  test    rax, rax
0x180006984  jnz     short loc_1800069CC
0x180006986  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000698c  jnz     short loc_1800069D7
0x18000698e  lea     rcx, ModuleName; "ntdll.dll"
0x180006995  call    cs:__imp_GetModuleHandleW
0x18000699b  test    rax, rax
0x18000699e  jz      short loc_1800069B9
0x1800069a0  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800069a7  mov     rcx, rax; hModule
0x1800069aa  call    cs:__imp_GetProcAddress
0x1800069b0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800069b7  jmp     short loc_1800069C0
0x1800069b9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800069c0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800069c7  test    rax, rax
0x1800069ca  jz      short loc_1800069D7
0x1800069cc  mov     rdx, rbx
0x1800069cf  mov     rcx, rsi
0x1800069d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d7  mov     rax, rbx
0x1800069da  mov     rbx, [rsp+28h+arg_0]
0x1800069df  mov     rsi, [rsp+28h+arg_8]
0x1800069e4  add     rsp, 20h
0x1800069e8  pop     rdi
0x1800069e9  retn
```
