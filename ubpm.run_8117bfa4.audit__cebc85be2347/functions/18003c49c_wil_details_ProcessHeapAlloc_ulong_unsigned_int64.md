# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003c49c`
- end: `0x18003c553`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180031d44`
- `0x18003c00c`
- `0x18003c140`
- `0x18003d194`
- `0x18003d40c`

## callees

- `0x18003c49c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c50c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c50c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003c4f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003c4f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c4c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c4c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c4b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c4b0`

## string_xrefs

- `0x18003c4ea`: `ntdll.dll`

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
0x18003c49c  mov     [rsp+arg_0], rbx
0x18003c4a1  mov     [rsp+arg_8], rsi
0x18003c4a6  push    rdi
0x18003c4a7  sub     rsp, 20h
0x18003c4ab  mov     rbx, rdx
0x18003c4ae  mov     edi, ecx
0x18003c4b0  call    cs:__imp_GetProcessHeap
0x18003c4b7  nop     dword ptr [rax+rax+00h]
0x18003c4bc  mov     r8, rbx; dwBytes
0x18003c4bf  mov     edx, edi; dwFlags
0x18003c4c1  mov     rcx, rax; hHeap
0x18003c4c4  mov     rsi, rax
0x18003c4c7  call    cs:__imp_HeapAlloc
0x18003c4ce  nop     dword ptr [rax+rax+00h]
0x18003c4d3  mov     rbx, rax
0x18003c4d6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003c4dd  test    rax, rax
0x18003c4e0  jnz     short loc_18003C534
0x18003c4e2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18003c4e8  jnz     short loc_18003C53F
0x18003c4ea  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18003c4f1  call    cs:__imp_GetModuleHandleW
0x18003c4f8  nop     dword ptr [rax+rax+00h]
0x18003c4fd  test    rax, rax
0x18003c500  jz      short loc_18003C521
0x18003c502  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18003c509  mov     rcx, rax; hModule
0x18003c50c  call    cs:__imp_GetProcAddress
0x18003c513  nop     dword ptr [rax+rax+00h]
0x18003c518  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18003c51f  jmp     short loc_18003C528
0x18003c521  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003c528  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18003c52f  test    rax, rax
0x18003c532  jz      short loc_18003C53F
0x18003c534  mov     rdx, rbx
0x18003c537  mov     rcx, rsi
0x18003c53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c53f  mov     rsi, [rsp+28h+arg_8]
0x18003c544  mov     rax, rbx
0x18003c547  mov     rbx, [rsp+28h+arg_0]
0x18003c54c  add     rsp, 20h
0x18003c550  pop     rdi
0x18003c551  retn
```
