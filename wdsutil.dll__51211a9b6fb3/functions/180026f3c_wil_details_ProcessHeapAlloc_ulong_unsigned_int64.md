# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180026f3c`
- end: `0x180026ffe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `194`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800263f0`
- `0x1800277c4`

## callees

- `0x180026f3c`
- `0x180034010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180026f71`
- `KERNEL32!HeapAlloc` at `0x180026f71`
- `KERNEL32!GetProcessHeap` at `0x180026f5a`
- `KERNEL32!GetProcessHeap` at `0x180026f5a`
- `KERNEL32!GetProcAddress` at `0x180026fb6`
- `KERNEL32!GetProcAddress` at `0x180026fb6`
- `KERNEL32!GetModuleHandleW` at `0x180026f9b`
- `KERNEL32!GetModuleHandleW` at `0x180026f9b`

## string_xrefs

- `0x180026f94`: `ntdll.dll`

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
0x180026f3c  push    rdi
0x180026f3e  sub     rsp, 30h
0x180026f42  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180026f4b  mov     [rsp+38h+arg_0], rbx
0x180026f50  mov     [rsp+38h+arg_8], rsi
0x180026f55  mov     rbx, rdx
0x180026f58  mov     edi, ecx
0x180026f5a  call    cs:__imp_GetProcessHeap
0x180026f61  nop     dword ptr [rax+rax+00h]
0x180026f66  mov     rsi, rax
0x180026f69  mov     r8, rbx; dwBytes
0x180026f6c  mov     edx, edi; dwFlags
0x180026f6e  mov     rcx, rax; hHeap
0x180026f71  call    cs:__imp_HeapAlloc
0x180026f78  nop     dword ptr [rax+rax+00h]
0x180026f7d  mov     rbx, rax
0x180026f80  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180026f87  test    rax, rax
0x180026f8a  jnz     short loc_180026FDF
0x180026f8c  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180026f92  jnz     short loc_180026FEA
0x180026f94  lea     rcx, LibFileName; "ntdll.dll"
0x180026f9b  call    cs:__imp_GetModuleHandleW
0x180026fa2  nop     dword ptr [rax+rax+00h]
0x180026fa7  test    rax, rax
0x180026faa  jz      short loc_180026FCC
0x180026fac  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180026fb3  mov     rcx, rax; hModule
0x180026fb6  call    cs:__imp_GetProcAddress
0x180026fbd  nop     dword ptr [rax+rax+00h]
0x180026fc2  nop
0x180026fc3  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180026fca  jmp     short loc_180026FD3
0x180026fcc  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180026fd3  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180026fda  test    rax, rax
0x180026fdd  jz      short loc_180026FEA
0x180026fdf  mov     rdx, rbx
0x180026fe2  mov     rcx, rsi
0x180026fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fea  mov     rax, rbx
0x180026fed  mov     rbx, [rsp+38h+arg_0]
0x180026ff2  mov     rsi, [rsp+38h+arg_8]
0x180026ff7  add     rsp, 30h
0x180026ffb  pop     rdi
0x180026ffc  retn
```
