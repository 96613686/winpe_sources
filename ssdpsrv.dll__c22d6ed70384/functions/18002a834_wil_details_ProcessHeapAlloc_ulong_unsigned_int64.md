# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002a834`
- end: `0x18002a8d2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180022bf4`
- `0x18002a2f8`
- `0x18002a41c`
- `0x18002b4c4`
- `0x18002b728`

## callees

- `0x18002a834`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a87d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a87d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a892`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a892`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a859`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a859`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a848`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a848`

## string_xrefs

- `0x18002a876`: `ntdll.dll`

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
0x18002a834  mov     [rsp+arg_0], rbx
0x18002a839  mov     [rsp+arg_8], rsi
0x18002a83e  push    rdi
0x18002a83f  sub     rsp, 20h
0x18002a843  mov     rbx, rdx
0x18002a846  mov     edi, ecx
0x18002a848  call    cs:__imp_GetProcessHeap
0x18002a84e  mov     r8, rbx; dwBytes
0x18002a851  mov     edx, edi; dwFlags
0x18002a853  mov     rcx, rax; hHeap
0x18002a856  mov     rsi, rax
0x18002a859  call    cs:__imp_HeapAlloc
0x18002a85f  mov     rbx, rax
0x18002a862  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002a869  test    rax, rax
0x18002a86c  jnz     short loc_18002A8B4
0x18002a86e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002a874  jnz     short loc_18002A8BF
0x18002a876  lea     rcx, ModuleName; "ntdll.dll"
0x18002a87d  call    cs:__imp_GetModuleHandleW
0x18002a883  test    rax, rax
0x18002a886  jz      short loc_18002A8A1
0x18002a888  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18002a88f  mov     rcx, rax; hModule
0x18002a892  call    cs:__imp_GetProcAddress
0x18002a898  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002a89f  jmp     short loc_18002A8A8
0x18002a8a1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002a8a8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002a8af  test    rax, rax
0x18002a8b2  jz      short loc_18002A8BF
0x18002a8b4  mov     rdx, rbx
0x18002a8b7  mov     rcx, rsi
0x18002a8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8bf  mov     rsi, [rsp+28h+arg_8]
0x18002a8c4  mov     rax, rbx
0x18002a8c7  mov     rbx, [rsp+28h+arg_0]
0x18002a8cc  add     rsp, 20h
0x18002a8d0  pop     rdi
0x18002a8d1  retn
```
