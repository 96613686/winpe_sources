# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000ae30`
- end: `0x18000aece`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000900c`
- `0x1800093dc`
- `0x18000a4f0`
- `0x18000cb34`
- `0x18001171c`

## callees

- `0x18000ae30`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ae79`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ae79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ae55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ae55`

## string_xrefs

- `0x18000ae72`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000ae30  mov     [rsp+arg_0], rbx
0x18000ae35  mov     [rsp+arg_8], rsi
0x18000ae3a  push    rdi
0x18000ae3b  sub     rsp, 20h
0x18000ae3f  mov     rbx, rdx
0x18000ae42  mov     edi, ecx
0x18000ae44  call    cs:__imp_GetProcessHeap
0x18000ae4a  mov     rsi, rax
0x18000ae4d  mov     r8, rbx; dwBytes
0x18000ae50  mov     edx, edi; dwFlags
0x18000ae52  mov     rcx, rax; hHeap
0x18000ae55  call    cs:__imp_HeapAlloc
0x18000ae5b  mov     rbx, rax
0x18000ae5e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ae65  test    rax, rax
0x18000ae68  jnz     short loc_18000AEB0
0x18000ae6a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ae70  jnz     short loc_18000AEBB
0x18000ae72  lea     rcx, Src; "ntdll.dll"
0x18000ae79  call    cs:__imp_GetModuleHandleW
0x18000ae7f  test    rax, rax
0x18000ae82  jz      short loc_18000AE9D
0x18000ae84  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000ae8b  mov     rcx, rax; hModule
0x18000ae8e  call    cs:__imp_GetProcAddress
0x18000ae94  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000ae9b  jmp     short loc_18000AEA4
0x18000ae9d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000aea4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000aeab  test    rax, rax
0x18000aeae  jz      short loc_18000AEBB
0x18000aeb0  mov     rdx, rbx
0x18000aeb3  mov     rcx, rsi
0x18000aeb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aebb  mov     rax, rbx
0x18000aebe  mov     rbx, [rsp+28h+arg_0]
0x18000aec3  mov     rsi, [rsp+28h+arg_8]
0x18000aec8  add     rsp, 20h
0x18000aecc  pop     rdi
0x18000aecd  retn
```
