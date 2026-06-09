# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180003584`
- end: `0x180003622`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003628`
- `0x1800062c8`
- `0x180006730`
- `0x1800070ac`
- `0x180007a74`

## callees

- `0x180003584`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800035a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800035a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003598`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003598`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800035cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800035cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800035e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800035e2`

## string_xrefs

- `0x1800035c6`: `ntdll.dll`

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
0x180003584  mov     [rsp+arg_0], rbx
0x180003589  mov     [rsp+arg_8], rsi
0x18000358e  push    rdi
0x18000358f  sub     rsp, 20h
0x180003593  mov     rbx, rdx
0x180003596  mov     edi, ecx
0x180003598  call    cs:__imp_GetProcessHeap
0x18000359e  mov     rsi, rax
0x1800035a1  mov     r8, rbx; dwBytes
0x1800035a4  mov     edx, edi; dwFlags
0x1800035a6  mov     rcx, rax; hHeap
0x1800035a9  call    cs:__imp_HeapAlloc
0x1800035af  mov     rbx, rax
0x1800035b2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800035b9  test    rax, rax
0x1800035bc  jnz     short loc_180003604
0x1800035be  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800035c4  jnz     short loc_18000360F
0x1800035c6  lea     rcx, ModuleName; "ntdll.dll"
0x1800035cd  call    cs:__imp_GetModuleHandleW
0x1800035d3  test    rax, rax
0x1800035d6  jz      short loc_1800035F1
0x1800035d8  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800035df  mov     rcx, rax; hModule
0x1800035e2  call    cs:__imp_GetProcAddress
0x1800035e8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800035ef  jmp     short loc_1800035F8
0x1800035f1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800035f8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800035ff  test    rax, rax
0x180003602  jz      short loc_18000360F
0x180003604  mov     rdx, rbx
0x180003607  mov     rcx, rsi
0x18000360a  call    _guard_dispatch_icall
0x18000360f  mov     rax, rbx
0x180003612  mov     rbx, [rsp+28h+arg_0]
0x180003617  mov     rsi, [rsp+28h+arg_8]
0x18000361c  add     rsp, 20h
0x180003620  pop     rdi
0x180003621  retn
```
