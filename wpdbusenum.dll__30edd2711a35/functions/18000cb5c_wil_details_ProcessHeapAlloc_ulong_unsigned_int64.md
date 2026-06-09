# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000cb5c`
- end: `0x18000cbfa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008678`
- `0x18000c9ac`
- `0x18000cebc`
- `0x18000d254`

## callees

- `0x18000cb5c`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cbba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cbba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cba5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cba5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cb81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cb81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb70`

## string_xrefs

- `0x18000cb9e`: `ntdll.dll`

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
0x18000cb5c  mov     [rsp+arg_0], rbx
0x18000cb61  mov     [rsp+arg_8], rsi
0x18000cb66  push    rdi
0x18000cb67  sub     rsp, 20h
0x18000cb6b  mov     rbx, rdx
0x18000cb6e  mov     edi, ecx
0x18000cb70  call    cs:__imp_GetProcessHeap
0x18000cb76  mov     rsi, rax
0x18000cb79  mov     r8, rbx; dwBytes
0x18000cb7c  mov     edx, edi; dwFlags
0x18000cb7e  mov     rcx, rax; hHeap
0x18000cb81  call    cs:__imp_HeapAlloc
0x18000cb87  mov     rbx, rax
0x18000cb8a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000cb91  test    rax, rax
0x18000cb94  jnz     short loc_18000CBDC
0x18000cb96  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000cb9c  jnz     short loc_18000CBE7
0x18000cb9e  lea     rcx, ModuleName; "ntdll.dll"
0x18000cba5  call    cs:__imp_GetModuleHandleW
0x18000cbab  test    rax, rax
0x18000cbae  jz      short loc_18000CBC9
0x18000cbb0  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000cbb7  mov     rcx, rax; hModule
0x18000cbba  call    cs:__imp_GetProcAddress
0x18000cbc0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000cbc7  jmp     short loc_18000CBD0
0x18000cbc9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000cbd0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000cbd7  test    rax, rax
0x18000cbda  jz      short loc_18000CBE7
0x18000cbdc  mov     rdx, rbx
0x18000cbdf  mov     rcx, rsi
0x18000cbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbe7  mov     rax, rbx
0x18000cbea  mov     rbx, [rsp+28h+arg_0]
0x18000cbef  mov     rsi, [rsp+28h+arg_8]
0x18000cbf4  add     rsp, 20h
0x18000cbf8  pop     rdi
0x18000cbf9  retn
```
