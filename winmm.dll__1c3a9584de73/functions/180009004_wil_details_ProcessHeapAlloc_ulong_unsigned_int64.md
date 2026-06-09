# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009004`
- end: `0x1800090a3`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b0e0`
- `0x180018290`
- `0x1800183b4`
- `0x180018d00`
- `0x180019098`

## callees

- `0x180009004`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009062`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009062`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000904d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000904d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009018`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009018`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009029`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009029`

## string_xrefs

- `0x180009046`: `ntdll.dll`

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
0x180009004  mov     [rsp+arg_0], rbx
0x180009009  mov     [rsp+arg_8], rsi
0x18000900e  push    rdi
0x18000900f  sub     rsp, 20h
0x180009013  mov     rbx, rdx
0x180009016  mov     edi, ecx
0x180009018  call    cs:__imp_GetProcessHeap
0x18000901e  mov     rsi, rax
0x180009021  mov     r8, rbx; dwBytes
0x180009024  mov     edx, edi; dwFlags
0x180009026  mov     rcx, rax; hHeap
0x180009029  call    cs:__imp_HeapAlloc
0x18000902f  mov     rbx, rax
0x180009032  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009039  test    rax, rax
0x18000903c  jnz     short loc_18000907C
0x18000903e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009044  jnz     short loc_180009087
0x180009046  lea     rcx, ModuleName; "ntdll.dll"
0x18000904d  call    cs:__imp_GetModuleHandleW
0x180009053  test    rax, rax
0x180009056  jz      short loc_18000909A
0x180009058  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000905f  mov     rcx, rax; hModule
0x180009062  call    cs:__imp_GetProcAddress
0x180009068  nop
0x180009069  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180009070  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009077  test    rax, rax
0x18000907a  jz      short loc_180009087
0x18000907c  mov     rdx, rbx
0x18000907f  mov     rcx, rsi
0x180009082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009087  mov     rax, rbx
0x18000908a  mov     rbx, [rsp+28h+arg_0]
0x18000908f  mov     rsi, [rsp+28h+arg_8]
0x180009094  add     rsp, 20h
0x180009098  pop     rdi
0x180009099  retn
0x18000909a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800090a1  jmp     short loc_180009070
```
