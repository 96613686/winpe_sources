# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005ce8`
- end: `0x180005d86`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003a3c`
- `0x180003de0`
- `0x180004a90`
- `0x1800072f8`
- `0x18000847c`

## callees

- `0x180005ce8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005d31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005d31`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005d46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005d46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005d0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005d0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005cfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005cfc`

## string_xrefs

- `0x180005d2a`: `ntdll.dll`

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
0x180005ce8  mov     [rsp+arg_0], rbx
0x180005ced  mov     [rsp+arg_8], rsi
0x180005cf2  push    rdi
0x180005cf3  sub     rsp, 20h
0x180005cf7  mov     rbx, rdx
0x180005cfa  mov     edi, ecx
0x180005cfc  call    cs:__imp_GetProcessHeap
0x180005d02  mov     r8, rbx; dwBytes
0x180005d05  mov     edx, edi; dwFlags
0x180005d07  mov     rcx, rax; hHeap
0x180005d0a  mov     rsi, rax
0x180005d0d  call    cs:__imp_HeapAlloc
0x180005d13  mov     rbx, rax
0x180005d16  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005d1d  test    rax, rax
0x180005d20  jnz     short loc_180005D68
0x180005d22  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005d28  jnz     short loc_180005D73
0x180005d2a  lea     rcx, ModuleName; "ntdll.dll"
0x180005d31  call    cs:__imp_GetModuleHandleW
0x180005d37  test    rax, rax
0x180005d3a  jz      short loc_180005D55
0x180005d3c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005d43  mov     rcx, rax; hModule
0x180005d46  call    cs:__imp_GetProcAddress
0x180005d4c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005d53  jmp     short loc_180005D5C
0x180005d55  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005d5c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005d63  test    rax, rax
0x180005d66  jz      short loc_180005D73
0x180005d68  mov     rdx, rbx
0x180005d6b  mov     rcx, rsi
0x180005d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d73  mov     rsi, [rsp+28h+arg_8]
0x180005d78  mov     rax, rbx
0x180005d7b  mov     rbx, [rsp+28h+arg_0]
0x180005d80  add     rsp, 20h
0x180005d84  pop     rdi
0x180005d85  retn
```
