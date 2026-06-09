# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009900`
- end: `0x18000999e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006d88`
- `0x1800096fc`
- `0x180009bd4`
- `0x180009d4c`
- `0x18000b6cc`

## callees

- `0x180009900`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000995e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000995e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009949`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009949`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009914`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009914`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009925`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009925`

## string_xrefs

- `0x180009942`: `ntdll.dll`

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
0x180009900  mov     [rsp+arg_0], rbx
0x180009905  mov     [rsp+arg_8], rsi
0x18000990a  push    rdi
0x18000990b  sub     rsp, 20h
0x18000990f  mov     rbx, rdx
0x180009912  mov     edi, ecx
0x180009914  call    cs:__imp_GetProcessHeap
0x18000991a  mov     r8, rbx; dwBytes
0x18000991d  mov     edx, edi; dwFlags
0x18000991f  mov     rcx, rax; hHeap
0x180009922  mov     rsi, rax
0x180009925  call    cs:__imp_HeapAlloc
0x18000992b  mov     rbx, rax
0x18000992e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009935  test    rax, rax
0x180009938  jnz     short loc_180009980
0x18000993a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009940  jnz     short loc_18000998B
0x180009942  lea     rcx, ModuleName; "ntdll.dll"
0x180009949  call    cs:__imp_GetModuleHandleW
0x18000994f  test    rax, rax
0x180009952  jz      short loc_18000996D
0x180009954  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000995b  mov     rcx, rax; hModule
0x18000995e  call    cs:__imp_GetProcAddress
0x180009964  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000996b  jmp     short loc_180009974
0x18000996d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009974  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000997b  test    rax, rax
0x18000997e  jz      short loc_18000998B
0x180009980  mov     rdx, rbx
0x180009983  mov     rcx, rsi
0x180009986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000998b  mov     rsi, [rsp+28h+arg_8]
0x180009990  mov     rax, rbx
0x180009993  mov     rbx, [rsp+28h+arg_0]
0x180009998  add     rsp, 20h
0x18000999c  pop     rdi
0x18000999d  retn
```
