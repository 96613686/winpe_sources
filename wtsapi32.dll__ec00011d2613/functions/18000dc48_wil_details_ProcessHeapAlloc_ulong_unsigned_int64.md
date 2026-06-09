# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000dc48`
- end: `0x18000dce6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d9d4`
- `0x18000e01c`
- `0x18000e194`
- `0x180012040`

## callees

- `0x18000dc48`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dc91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dc91`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dca6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dca6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dc5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dc5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc6d`

## string_xrefs

- `0x18000dc8a`: `ntdll.dll`

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
0x18000dc48  mov     [rsp+arg_0], rbx
0x18000dc4d  mov     [rsp+arg_8], rsi
0x18000dc52  push    rdi
0x18000dc53  sub     rsp, 20h
0x18000dc57  mov     rbx, rdx
0x18000dc5a  mov     edi, ecx
0x18000dc5c  call    cs:__imp_GetProcessHeap
0x18000dc62  mov     r8, rbx; dwBytes
0x18000dc65  mov     edx, edi; dwFlags
0x18000dc67  mov     rcx, rax; hHeap
0x18000dc6a  mov     rsi, rax
0x18000dc6d  call    cs:__imp_HeapAlloc
0x18000dc73  mov     rbx, rax
0x18000dc76  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000dc7d  test    rax, rax
0x18000dc80  jnz     short loc_18000DCC8
0x18000dc82  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000dc88  jnz     short loc_18000DCD3
0x18000dc8a  lea     rcx, ModuleName; "ntdll.dll"
0x18000dc91  call    cs:__imp_GetModuleHandleW
0x18000dc97  test    rax, rax
0x18000dc9a  jz      short loc_18000DCB5
0x18000dc9c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000dca3  mov     rcx, rax; hModule
0x18000dca6  call    cs:__imp_GetProcAddress
0x18000dcac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000dcb3  jmp     short loc_18000DCBC
0x18000dcb5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000dcbc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000dcc3  test    rax, rax
0x18000dcc6  jz      short loc_18000DCD3
0x18000dcc8  mov     rdx, rbx
0x18000dccb  mov     rcx, rsi
0x18000dcce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcd3  mov     rsi, [rsp+28h+arg_8]
0x18000dcd8  mov     rax, rbx
0x18000dcdb  mov     rbx, [rsp+28h+arg_0]
0x18000dce0  add     rsp, 20h
0x18000dce4  pop     rdi
0x18000dce5  retn
```
