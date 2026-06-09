# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009870`
- end: `0x18000990e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005198`
- `0x180005568`
- `0x180007470`
- `0x18000b834`
- `0x18000d7e4`

## callees

- `0x180009870`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800098b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800098b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800098ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800098ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009884`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009884`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009895`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009895`

## string_xrefs

- `0x1800098b2`: `ntdll.dll`

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
0x180009870  mov     [rsp+arg_0], rbx
0x180009875  mov     [rsp+arg_8], rsi
0x18000987a  push    rdi
0x18000987b  sub     rsp, 20h
0x18000987f  mov     rbx, rdx
0x180009882  mov     edi, ecx
0x180009884  call    cs:__imp_GetProcessHeap
0x18000988a  mov     rsi, rax
0x18000988d  mov     r8, rbx; dwBytes
0x180009890  mov     edx, edi; dwFlags
0x180009892  mov     rcx, rax; hHeap
0x180009895  call    cs:__imp_HeapAlloc
0x18000989b  mov     rbx, rax
0x18000989e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800098a5  test    rax, rax
0x1800098a8  jnz     short loc_1800098F0
0x1800098aa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800098b0  jnz     short loc_1800098FB
0x1800098b2  lea     rcx, ModuleName; "ntdll.dll"
0x1800098b9  call    cs:__imp_GetModuleHandleW
0x1800098bf  test    rax, rax
0x1800098c2  jz      short loc_1800098DD
0x1800098c4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800098cb  mov     rcx, rax; hModule
0x1800098ce  call    cs:__imp_GetProcAddress
0x1800098d4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800098db  jmp     short loc_1800098E4
0x1800098dd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800098e4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800098eb  test    rax, rax
0x1800098ee  jz      short loc_1800098FB
0x1800098f0  mov     rdx, rbx
0x1800098f3  mov     rcx, rsi
0x1800098f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098fb  mov     rax, rbx
0x1800098fe  mov     rbx, [rsp+28h+arg_0]
0x180009903  mov     rsi, [rsp+28h+arg_8]
0x180009908  add     rsp, 20h
0x18000990c  pop     rdi
0x18000990d  retn
```
