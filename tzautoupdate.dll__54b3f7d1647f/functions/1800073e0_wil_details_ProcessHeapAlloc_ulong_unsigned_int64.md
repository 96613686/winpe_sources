# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800073e0`
- end: `0x18000747e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006eec`
- `0x18000704c`
- `0x180008954`
- `0x180008ddc`
- `0x18000b638`

## callees

- `0x1800073e0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007429`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007429`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000743e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000743e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007405`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007405`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073f4`

## string_xrefs

- `0x180007422`: `ntdll.dll`

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
0x1800073e0  mov     [rsp+arg_0], rbx
0x1800073e5  mov     [rsp+arg_8], rsi
0x1800073ea  push    rdi
0x1800073eb  sub     rsp, 20h
0x1800073ef  mov     rbx, rdx
0x1800073f2  mov     edi, ecx
0x1800073f4  call    cs:__imp_GetProcessHeap
0x1800073fa  mov     rsi, rax
0x1800073fd  mov     r8, rbx; dwBytes
0x180007400  mov     edx, edi; dwFlags
0x180007402  mov     rcx, rax; hHeap
0x180007405  call    cs:__imp_HeapAlloc
0x18000740b  mov     rbx, rax
0x18000740e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007415  test    rax, rax
0x180007418  jnz     short loc_180007460
0x18000741a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007420  jnz     short loc_18000746B
0x180007422  lea     rcx, ModuleName; "ntdll.dll"
0x180007429  call    cs:__imp_GetModuleHandleW
0x18000742f  test    rax, rax
0x180007432  jz      short loc_18000744D
0x180007434  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000743b  mov     rcx, rax; hModule
0x18000743e  call    cs:__imp_GetProcAddress
0x180007444  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000744b  jmp     short loc_180007454
0x18000744d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007454  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000745b  test    rax, rax
0x18000745e  jz      short loc_18000746B
0x180007460  mov     rdx, rbx
0x180007463  mov     rcx, rsi
0x180007466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000746b  mov     rax, rbx
0x18000746e  mov     rbx, [rsp+28h+arg_0]
0x180007473  mov     rsi, [rsp+28h+arg_8]
0x180007478  add     rsp, 20h
0x18000747c  pop     rdi
0x18000747d  retn
```
