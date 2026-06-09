# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000fe98`
- end: `0x18000ff37`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fa94`
- `0x18000fbbc`
- `0x180010d80`
- `0x180011208`
- `0x18001261c`

## callees

- `0x18000fe98`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000febd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000febd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000feac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000feac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fef6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fef6`

## string_xrefs

- `0x18000feda`: `ntdll.dll`

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
0x18000fe98  mov     [rsp+arg_0], rbx
0x18000fe9d  mov     [rsp+arg_8], rsi
0x18000fea2  push    rdi
0x18000fea3  sub     rsp, 20h
0x18000fea7  mov     rbx, rdx
0x18000feaa  mov     edi, ecx
0x18000feac  call    cs:__imp_GetProcessHeap
0x18000feb2  mov     rsi, rax
0x18000feb5  mov     r8, rbx; dwBytes
0x18000feb8  mov     edx, edi; dwFlags
0x18000feba  mov     rcx, rax; hHeap
0x18000febd  call    cs:__imp_HeapAlloc
0x18000fec3  mov     rbx, rax
0x18000fec6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000fecd  test    rax, rax
0x18000fed0  jnz     short loc_18000FF19
0x18000fed2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000fed8  jnz     short loc_18000FF24
0x18000feda  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000fee1  call    cs:__imp_GetModuleHandleW
0x18000fee7  test    rax, rax
0x18000feea  jz      short loc_18000FF06
0x18000feec  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000fef3  mov     rcx, rax; hModule
0x18000fef6  call    cs:__imp_GetProcAddress
0x18000fefc  nop
0x18000fefd  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000ff04  jmp     short loc_18000FF0D
0x18000ff06  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ff0d  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ff14  test    rax, rax
0x18000ff17  jz      short loc_18000FF24
0x18000ff19  mov     rdx, rbx
0x18000ff1c  mov     rcx, rsi
0x18000ff1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff24  mov     rax, rbx
0x18000ff27  mov     rbx, [rsp+28h+arg_0]
0x18000ff2c  mov     rsi, [rsp+28h+arg_8]
0x18000ff31  add     rsp, 20h
0x18000ff35  pop     rdi
0x18000ff36  retn
```
