# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180013d60`
- end: `0x180013dfe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013ca0`
- `0x18001eb38`
- `0x18001ec5c`
- `0x18001f3b4`
- `0x18001f52c`

## callees

- `0x180013d60`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013d85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013d85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013d74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013d74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013dbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013dbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013da9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013da9`

## string_xrefs

- `0x180013da2`: `ntdll.dll`

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
0x180013d60  mov     [rsp+arg_0], rbx
0x180013d65  mov     [rsp+arg_8], rsi
0x180013d6a  push    rdi
0x180013d6b  sub     rsp, 20h
0x180013d6f  mov     rbx, rdx
0x180013d72  mov     edi, ecx
0x180013d74  call    cs:__imp_GetProcessHeap
0x180013d7a  mov     r8, rbx; dwBytes
0x180013d7d  mov     edx, edi; dwFlags
0x180013d7f  mov     rcx, rax; hHeap
0x180013d82  mov     rsi, rax
0x180013d85  call    cs:__imp_HeapAlloc
0x180013d8b  mov     rbx, rax
0x180013d8e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180013d95  test    rax, rax
0x180013d98  jnz     short loc_180013DE0
0x180013d9a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180013da0  jnz     short loc_180013DEB
0x180013da2  lea     rcx, ModuleName; "ntdll.dll"
0x180013da9  call    cs:__imp_GetModuleHandleW
0x180013daf  test    rax, rax
0x180013db2  jz      short loc_180013DCD
0x180013db4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180013dbb  mov     rcx, rax; hModule
0x180013dbe  call    cs:__imp_GetProcAddress
0x180013dc4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180013dcb  jmp     short loc_180013DD4
0x180013dcd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180013dd4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180013ddb  test    rax, rax
0x180013dde  jz      short loc_180013DEB
0x180013de0  mov     rdx, rbx
0x180013de3  mov     rcx, rsi
0x180013de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013deb  mov     rsi, [rsp+28h+arg_8]
0x180013df0  mov     rax, rbx
0x180013df3  mov     rbx, [rsp+28h+arg_0]
0x180013df8  add     rsp, 20h
0x180013dfc  pop     rdi
0x180013dfd  retn
```
