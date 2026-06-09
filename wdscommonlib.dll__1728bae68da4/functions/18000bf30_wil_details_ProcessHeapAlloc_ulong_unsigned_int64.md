# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000bf30`
- end: `0x18000bfe7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009c54`
- `0x18000a04c`
- `0x18000d3f0`
- `0x18000d784`
- `0x18000e6d0`

## callees

- `0x18000bf30`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000bfa0`
- `KERNEL32!GetProcAddress` at `0x18000bfa0`
- `KERNEL32!GetProcessHeap` at `0x18000bf44`
- `KERNEL32!GetProcessHeap` at `0x18000bf44`
- `KERNEL32!HeapAlloc` at `0x18000bf5b`
- `KERNEL32!HeapAlloc` at `0x18000bf5b`
- `KERNEL32!GetModuleHandleW` at `0x18000bf85`
- `KERNEL32!GetModuleHandleW` at `0x18000bf85`

## string_xrefs

- `0x18000bf7e`: `ntdll.dll`

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
0x18000bf30  mov     [rsp+arg_0], rbx
0x18000bf35  mov     [rsp+arg_8], rsi
0x18000bf3a  push    rdi
0x18000bf3b  sub     rsp, 20h
0x18000bf3f  mov     rbx, rdx
0x18000bf42  mov     edi, ecx
0x18000bf44  call    cs:__imp_GetProcessHeap
0x18000bf4b  nop     dword ptr [rax+rax+00h]
0x18000bf50  mov     r8, rbx; dwBytes
0x18000bf53  mov     edx, edi; dwFlags
0x18000bf55  mov     rcx, rax; hHeap
0x18000bf58  mov     rsi, rax
0x18000bf5b  call    cs:__imp_HeapAlloc
0x18000bf62  nop     dword ptr [rax+rax+00h]
0x18000bf67  mov     rbx, rax
0x18000bf6a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000bf71  test    rax, rax
0x18000bf74  jnz     short loc_18000BFC8
0x18000bf76  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000bf7c  jnz     short loc_18000BFD3
0x18000bf7e  lea     rcx, ModuleName; "ntdll.dll"
0x18000bf85  call    cs:__imp_GetModuleHandleW
0x18000bf8c  nop     dword ptr [rax+rax+00h]
0x18000bf91  test    rax, rax
0x18000bf94  jz      short loc_18000BFB5
0x18000bf96  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000bf9d  mov     rcx, rax; hModule
0x18000bfa0  call    cs:__imp_GetProcAddress
0x18000bfa7  nop     dword ptr [rax+rax+00h]
0x18000bfac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000bfb3  jmp     short loc_18000BFBC
0x18000bfb5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000bfbc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000bfc3  test    rax, rax
0x18000bfc6  jz      short loc_18000BFD3
0x18000bfc8  mov     rdx, rbx
0x18000bfcb  mov     rcx, rsi
0x18000bfce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfd3  mov     rsi, [rsp+28h+arg_8]
0x18000bfd8  mov     rax, rbx
0x18000bfdb  mov     rbx, [rsp+28h+arg_0]
0x18000bfe0  add     rsp, 20h
0x18000bfe4  pop     rdi
0x18000bfe5  retn
```
