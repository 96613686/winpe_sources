# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000ace0`
- end: `0x18000ad97`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a904`
- `0x18000bd00`

## callees

- `0x18000ace0`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000ad35`
- `KERNEL32!GetModuleHandleW` at `0x18000ad35`
- `KERNEL32!GetProcAddress` at `0x18000ad50`
- `KERNEL32!GetProcAddress` at `0x18000ad50`
- `KERNEL32!GetProcessHeap` at `0x18000acf4`
- `KERNEL32!GetProcessHeap` at `0x18000acf4`
- `KERNEL32!HeapAlloc` at `0x18000ad0b`
- `KERNEL32!HeapAlloc` at `0x18000ad0b`

## string_xrefs

- `0x18000ad2e`: `ntdll.dll`

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
0x18000ace0  mov     [rsp+arg_0], rbx
0x18000ace5  mov     [rsp+arg_8], rsi
0x18000acea  push    rdi
0x18000aceb  sub     rsp, 20h
0x18000acef  mov     rbx, rdx
0x18000acf2  mov     edi, ecx
0x18000acf4  call    cs:__imp_GetProcessHeap
0x18000acfb  nop     dword ptr [rax+rax+00h]
0x18000ad00  mov     rsi, rax
0x18000ad03  mov     r8, rbx; dwBytes
0x18000ad06  mov     edx, edi; dwFlags
0x18000ad08  mov     rcx, rax; hHeap
0x18000ad0b  call    cs:__imp_HeapAlloc
0x18000ad12  nop     dword ptr [rax+rax+00h]
0x18000ad17  mov     rbx, rax
0x18000ad1a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ad21  test    rax, rax
0x18000ad24  jnz     short loc_18000AD78
0x18000ad26  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ad2c  jnz     short loc_18000AD83
0x18000ad2e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ad35  call    cs:__imp_GetModuleHandleW
0x18000ad3c  nop     dword ptr [rax+rax+00h]
0x18000ad41  test    rax, rax
0x18000ad44  jz      short loc_18000AD65
0x18000ad46  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000ad4d  mov     rcx, rax; hModule
0x18000ad50  call    cs:__imp_GetProcAddress
0x18000ad57  nop     dword ptr [rax+rax+00h]
0x18000ad5c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000ad63  jmp     short loc_18000AD6C
0x18000ad65  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ad6c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ad73  test    rax, rax
0x18000ad76  jz      short loc_18000AD83
0x18000ad78  mov     rdx, rbx
0x18000ad7b  mov     rcx, rsi
0x18000ad7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad83  mov     rax, rbx
0x18000ad86  mov     rbx, [rsp+28h+arg_0]
0x18000ad8b  mov     rsi, [rsp+28h+arg_8]
0x18000ad90  add     rsp, 20h
0x18000ad94  pop     rdi
0x18000ad95  retn
```
