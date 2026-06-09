# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004fe8`
- end: `0x180005086`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000383c`
- `0x180003fa0`
- `0x180005328`
- `0x180019328`
- `0x18001a148`

## callees

- `0x180004fe8`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005046`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005046`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005031`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005031`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ffc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ffc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000500d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000500d`

## string_xrefs

- `0x18000502a`: `ntdll.dll`

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
0x180004fe8  mov     [rsp+arg_0], rbx
0x180004fed  mov     [rsp+arg_8], rsi
0x180004ff2  push    rdi
0x180004ff3  sub     rsp, 20h
0x180004ff7  mov     rbx, rdx
0x180004ffa  mov     edi, ecx
0x180004ffc  call    cs:__imp_GetProcessHeap
0x180005002  mov     r8, rbx; dwBytes
0x180005005  mov     edx, edi; dwFlags
0x180005007  mov     rcx, rax; hHeap
0x18000500a  mov     rsi, rax
0x18000500d  call    cs:__imp_HeapAlloc
0x180005013  mov     rbx, rax
0x180005016  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000501d  test    rax, rax
0x180005020  jnz     short loc_180005068
0x180005022  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005028  jnz     short loc_180005073
0x18000502a  lea     rcx, ModuleName; "ntdll.dll"
0x180005031  call    cs:__imp_GetModuleHandleW
0x180005037  test    rax, rax
0x18000503a  jz      short loc_180005055
0x18000503c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005043  mov     rcx, rax; hModule
0x180005046  call    cs:__imp_GetProcAddress
0x18000504c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005053  jmp     short loc_18000505C
0x180005055  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000505c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005063  test    rax, rax
0x180005066  jz      short loc_180005073
0x180005068  mov     rdx, rbx
0x18000506b  mov     rcx, rsi
0x18000506e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005073  mov     rsi, [rsp+28h+arg_8]
0x180005078  mov     rax, rbx
0x18000507b  mov     rbx, [rsp+28h+arg_0]
0x180005080  add     rsp, 20h
0x180005084  pop     rdi
0x180005085  retn
```
