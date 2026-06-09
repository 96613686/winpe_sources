# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800448a0`
- end: `0x180044957`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004423c`
- `0x1800443d8`
- `0x180045c04`
- `0x180046094`
- `0x180048c08`

## callees

- `0x1800448a0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800448cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800448cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800448b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800448b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044910`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044910`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800448f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800448f5`

## string_xrefs

- `0x1800448ee`: `ntdll.dll`

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
0x1800448a0  mov     [rsp+arg_0], rbx
0x1800448a5  mov     [rsp+arg_8], rsi
0x1800448aa  push    rdi
0x1800448ab  sub     rsp, 20h
0x1800448af  mov     rbx, rdx
0x1800448b2  mov     edi, ecx
0x1800448b4  call    cs:__imp_GetProcessHeap
0x1800448bb  nop     dword ptr [rax+rax+00h]
0x1800448c0  mov     rsi, rax
0x1800448c3  mov     r8, rbx; dwBytes
0x1800448c6  mov     edx, edi; dwFlags
0x1800448c8  mov     rcx, rax; hHeap
0x1800448cb  call    cs:__imp_HeapAlloc
0x1800448d2  nop     dword ptr [rax+rax+00h]
0x1800448d7  mov     rbx, rax
0x1800448da  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800448e1  test    rax, rax
0x1800448e4  jnz     short loc_180044938
0x1800448e6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800448ec  jnz     short loc_180044943
0x1800448ee  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800448f5  call    cs:__imp_GetModuleHandleW
0x1800448fc  nop     dword ptr [rax+rax+00h]
0x180044901  test    rax, rax
0x180044904  jz      short loc_180044925
0x180044906  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18004490d  mov     rcx, rax; hModule
0x180044910  call    cs:__imp_GetProcAddress
0x180044917  nop     dword ptr [rax+rax+00h]
0x18004491c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180044923  jmp     short loc_18004492C
0x180044925  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004492c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180044933  test    rax, rax
0x180044936  jz      short loc_180044943
0x180044938  mov     rdx, rbx
0x18004493b  mov     rcx, rsi
0x18004493e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044943  mov     rax, rbx
0x180044946  mov     rbx, [rsp+28h+arg_0]
0x18004494b  mov     rsi, [rsp+28h+arg_8]
0x180044950  add     rsp, 20h
0x180044954  pop     rdi
0x180044955  retn
```
