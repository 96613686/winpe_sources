# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008344`
- end: `0x1800083fb`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003b34`
- `0x180003f2c`
- `0x18000a120`
- `0x18000a4b4`
- `0x18000b958`

## callees

- `0x180008344`
- `0x18000e010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000836f`
- `KERNEL32!HeapAlloc` at `0x18000836f`
- `KERNEL32!GetProcAddress` at `0x1800083b4`
- `KERNEL32!GetProcAddress` at `0x1800083b4`
- `KERNEL32!GetProcessHeap` at `0x180008358`
- `KERNEL32!GetProcessHeap` at `0x180008358`
- `KERNEL32!GetModuleHandleW` at `0x180008399`
- `KERNEL32!GetModuleHandleW` at `0x180008399`

## string_xrefs

- `0x180008392`: `ntdll.dll`

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
0x180008344  mov     [rsp+arg_0], rbx
0x180008349  mov     [rsp+arg_8], rsi
0x18000834e  push    rdi
0x18000834f  sub     rsp, 20h
0x180008353  mov     rbx, rdx
0x180008356  mov     edi, ecx
0x180008358  call    cs:__imp_GetProcessHeap
0x18000835f  nop     dword ptr [rax+rax+00h]
0x180008364  mov     r8, rbx; dwBytes
0x180008367  mov     edx, edi; dwFlags
0x180008369  mov     rcx, rax; hHeap
0x18000836c  mov     rsi, rax
0x18000836f  call    cs:__imp_HeapAlloc
0x180008376  nop     dword ptr [rax+rax+00h]
0x18000837b  mov     rbx, rax
0x18000837e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008385  test    rax, rax
0x180008388  jnz     short loc_1800083DC
0x18000838a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008390  jnz     short loc_1800083E7
0x180008392  lea     rcx, ModuleName; "ntdll.dll"
0x180008399  call    cs:__imp_GetModuleHandleW
0x1800083a0  nop     dword ptr [rax+rax+00h]
0x1800083a5  test    rax, rax
0x1800083a8  jz      short loc_1800083C9
0x1800083aa  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800083b1  mov     rcx, rax; hModule
0x1800083b4  call    cs:__imp_GetProcAddress
0x1800083bb  nop     dword ptr [rax+rax+00h]
0x1800083c0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800083c7  jmp     short loc_1800083D0
0x1800083c9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800083d0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800083d7  test    rax, rax
0x1800083da  jz      short loc_1800083E7
0x1800083dc  mov     rdx, rbx
0x1800083df  mov     rcx, rsi
0x1800083e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083e7  mov     rsi, [rsp+28h+arg_8]
0x1800083ec  mov     rax, rbx
0x1800083ef  mov     rbx, [rsp+28h+arg_0]
0x1800083f4  add     rsp, 20h
0x1800083f8  pop     rdi
0x1800083f9  retn
```
