# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000502c`
- end: `0x1800050ca`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004144`
- `0x180004720`
- `0x1800052f0`

## callees

- `0x18000502c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005075`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005075`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000508a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000508a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005040`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005040`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005051`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005051`

## string_xrefs

- `0x18000506e`: `ntdll.dll`

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
0x18000502c  mov     [rsp+arg_0], rbx
0x180005031  mov     [rsp+arg_8], rsi
0x180005036  push    rdi
0x180005037  sub     rsp, 20h
0x18000503b  mov     rbx, rdx
0x18000503e  mov     edi, ecx
0x180005040  call    cs:__imp_GetProcessHeap
0x180005046  mov     rsi, rax
0x180005049  mov     r8, rbx; dwBytes
0x18000504c  mov     edx, edi; dwFlags
0x18000504e  mov     rcx, rax; hHeap
0x180005051  call    cs:__imp_HeapAlloc
0x180005057  mov     rbx, rax
0x18000505a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005061  test    rax, rax
0x180005064  jnz     short loc_1800050AC
0x180005066  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000506c  jnz     short loc_1800050B7
0x18000506e  lea     rcx, ModuleName; "ntdll.dll"
0x180005075  call    cs:__imp_GetModuleHandleW
0x18000507b  test    rax, rax
0x18000507e  jz      short loc_180005099
0x180005080  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005087  mov     rcx, rax; hModule
0x18000508a  call    cs:__imp_GetProcAddress
0x180005090  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005097  jmp     short loc_1800050A0
0x180005099  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800050a0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800050a7  test    rax, rax
0x1800050aa  jz      short loc_1800050B7
0x1800050ac  mov     rdx, rbx
0x1800050af  mov     rcx, rsi
0x1800050b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b7  mov     rax, rbx
0x1800050ba  mov     rbx, [rsp+28h+arg_0]
0x1800050bf  mov     rsi, [rsp+28h+arg_8]
0x1800050c4  add     rsp, 20h
0x1800050c8  pop     rdi
0x1800050c9  retn
```
