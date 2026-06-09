# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400063dc`
- end: `0x14000647a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003410`
- `0x140006cd4`

## callees

- `0x1400063dc`
- `0x14002f010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140006401`
- `KERNEL32!HeapAlloc` at `0x140006401`
- `KERNEL32!GetProcAddress` at `0x14000643a`
- `KERNEL32!GetProcAddress` at `0x14000643a`
- `KERNEL32!GetProcessHeap` at `0x1400063f0`
- `KERNEL32!GetProcessHeap` at `0x1400063f0`
- `KERNEL32!GetModuleHandleW` at `0x140006425`
- `KERNEL32!GetModuleHandleW` at `0x140006425`

## string_xrefs

- `0x14000641e`: `ntdll.dll`

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
0x1400063dc  mov     [rsp+arg_0], rbx
0x1400063e1  mov     [rsp+arg_8], rsi
0x1400063e6  push    rdi
0x1400063e7  sub     rsp, 20h
0x1400063eb  mov     rbx, rdx
0x1400063ee  mov     edi, ecx
0x1400063f0  call    cs:__imp_GetProcessHeap
0x1400063f6  mov     rsi, rax
0x1400063f9  mov     r8, rbx; dwBytes
0x1400063fc  mov     edx, edi; dwFlags
0x1400063fe  mov     rcx, rax; hHeap
0x140006401  call    cs:__imp_HeapAlloc
0x140006407  mov     rbx, rax
0x14000640a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006411  test    rax, rax
0x140006414  jnz     short loc_14000645C
0x140006416  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000641c  jnz     short loc_140006467
0x14000641e  lea     rcx, LibFileName; "ntdll.dll"
0x140006425  call    cs:__imp_GetModuleHandleW
0x14000642b  test    rax, rax
0x14000642e  jz      short loc_140006449
0x140006430  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140006437  mov     rcx, rax; hModule
0x14000643a  call    cs:__imp_GetProcAddress
0x140006440  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140006447  jmp     short loc_140006450
0x140006449  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006450  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006457  test    rax, rax
0x14000645a  jz      short loc_140006467
0x14000645c  mov     rdx, rbx
0x14000645f  mov     rcx, rsi
0x140006462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006467  mov     rax, rbx
0x14000646a  mov     rbx, [rsp+28h+arg_0]
0x14000646f  mov     rsi, [rsp+28h+arg_8]
0x140006474  add     rsp, 20h
0x140006478  pop     rdi
0x140006479  retn
```
