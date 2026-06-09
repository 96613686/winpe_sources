# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001ba20`
- end: `0x18001babe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019cb8`
- `0x18001a590`
- `0x18001c370`

## callees

- `0x18001ba20`
- `0x18001e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18001ba34`
- `KERNEL32!GetProcessHeap` at `0x18001ba34`
- `KERNEL32!GetModuleHandleW` at `0x18001ba69`
- `KERNEL32!GetModuleHandleW` at `0x18001ba69`
- `KERNEL32!GetProcAddress` at `0x18001ba7e`
- `KERNEL32!GetProcAddress` at `0x18001ba7e`
- `KERNEL32!HeapAlloc` at `0x18001ba45`
- `KERNEL32!HeapAlloc` at `0x18001ba45`

## string_xrefs

- `0x18001ba62`: `ntdll.dll`

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
0x18001ba20  mov     [rsp+arg_0], rbx
0x18001ba25  mov     [rsp+arg_8], rsi
0x18001ba2a  push    rdi
0x18001ba2b  sub     rsp, 20h
0x18001ba2f  mov     rbx, rdx
0x18001ba32  mov     edi, ecx
0x18001ba34  call    cs:__imp_GetProcessHeap
0x18001ba3a  mov     r8, rbx; dwBytes
0x18001ba3d  mov     edx, edi; dwFlags
0x18001ba3f  mov     rcx, rax; hHeap
0x18001ba42  mov     rsi, rax
0x18001ba45  call    cs:__imp_HeapAlloc
0x18001ba4b  mov     rbx, rax
0x18001ba4e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001ba55  test    rax, rax
0x18001ba58  jnz     short loc_18001BAA0
0x18001ba5a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001ba60  jnz     short loc_18001BAAB
0x18001ba62  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001ba69  call    cs:__imp_GetModuleHandleW
0x18001ba6f  test    rax, rax
0x18001ba72  jz      short loc_18001BA8D
0x18001ba74  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18001ba7b  mov     rcx, rax; hModule
0x18001ba7e  call    cs:__imp_GetProcAddress
0x18001ba84  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001ba8b  jmp     short loc_18001BA94
0x18001ba8d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001ba94  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001ba9b  test    rax, rax
0x18001ba9e  jz      short loc_18001BAAB
0x18001baa0  mov     rdx, rbx
0x18001baa3  mov     rcx, rsi
0x18001baa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baab  mov     rsi, [rsp+28h+arg_8]
0x18001bab0  mov     rax, rbx
0x18001bab3  mov     rbx, [rsp+28h+arg_0]
0x18001bab8  add     rsp, 20h
0x18001babc  pop     rdi
0x18001babd  retn
```
