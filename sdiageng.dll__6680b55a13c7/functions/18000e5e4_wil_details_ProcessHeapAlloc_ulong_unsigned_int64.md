# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000e5e4`
- end: `0x18000e682`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000988c`
- `0x180009c30`
- `0x180010b78`
- `0x1800129fc`

## callees

- `0x18000e5e4`
- `0x18002a010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000e609`
- `KERNEL32!HeapAlloc` at `0x18000e609`
- `KERNEL32!GetProcessHeap` at `0x18000e5f8`
- `KERNEL32!GetProcessHeap` at `0x18000e5f8`
- `KERNEL32!GetModuleHandleW` at `0x18000e62d`
- `KERNEL32!GetModuleHandleW` at `0x18000e62d`
- `KERNEL32!GetProcAddress` at `0x18000e642`
- `KERNEL32!GetProcAddress` at `0x18000e642`

## string_xrefs

- `0x18000e626`: `ntdll.dll`

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
0x18000e5e4  mov     [rsp+arg_0], rbx
0x18000e5e9  mov     [rsp+arg_8], rsi
0x18000e5ee  push    rdi
0x18000e5ef  sub     rsp, 20h
0x18000e5f3  mov     rbx, rdx
0x18000e5f6  mov     edi, ecx
0x18000e5f8  call    cs:__imp_GetProcessHeap
0x18000e5fe  mov     rsi, rax
0x18000e601  mov     r8, rbx; dwBytes
0x18000e604  mov     edx, edi; dwFlags
0x18000e606  mov     rcx, rax; hHeap
0x18000e609  call    cs:__imp_HeapAlloc
0x18000e60f  mov     rbx, rax
0x18000e612  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e619  test    rax, rax
0x18000e61c  jnz     short loc_18000E664
0x18000e61e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e624  jnz     short loc_18000E66F
0x18000e626  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e62d  call    cs:__imp_GetModuleHandleW
0x18000e633  test    rax, rax
0x18000e636  jz      short loc_18000E651
0x18000e638  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000e63f  mov     rcx, rax; hModule
0x18000e642  call    cs:__imp_GetProcAddress
0x18000e648  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000e64f  jmp     short loc_18000E658
0x18000e651  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e658  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e65f  test    rax, rax
0x18000e662  jz      short loc_18000E66F
0x18000e664  mov     rdx, rbx
0x18000e667  mov     rcx, rsi
0x18000e66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e66f  mov     rax, rbx
0x18000e672  mov     rbx, [rsp+28h+arg_0]
0x18000e677  mov     rsi, [rsp+28h+arg_8]
0x18000e67c  add     rsp, 20h
0x18000e680  pop     rdi
0x18000e681  retn
```
