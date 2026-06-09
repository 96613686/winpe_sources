# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005cd0`
- end: `0x140005d6e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006524`
- `0x140008c5c`
- `0x140009000`
- `0x140009be0`
- `0x14000c028`

## callees

- `0x140005cd0`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140005d19`
- `KERNEL32!GetModuleHandleW` at `0x140005d19`
- `KERNEL32!HeapAlloc` at `0x140005cf5`
- `KERNEL32!HeapAlloc` at `0x140005cf5`
- `KERNEL32!GetProcessHeap` at `0x140005ce4`
- `KERNEL32!GetProcessHeap` at `0x140005ce4`
- `KERNEL32!GetProcAddress` at `0x140005d2e`
- `KERNEL32!GetProcAddress` at `0x140005d2e`

## string_xrefs

- `0x140005d12`: `ntdll.dll`

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
0x140005cd0  mov     [rsp+arg_0], rbx
0x140005cd5  mov     [rsp+arg_8], rsi
0x140005cda  push    rdi
0x140005cdb  sub     rsp, 20h
0x140005cdf  mov     rbx, rdx
0x140005ce2  mov     edi, ecx
0x140005ce4  call    cs:__imp_GetProcessHeap
0x140005cea  mov     r8, rbx; dwBytes
0x140005ced  mov     edx, edi; dwFlags
0x140005cef  mov     rcx, rax; hHeap
0x140005cf2  mov     rsi, rax
0x140005cf5  call    cs:__imp_HeapAlloc
0x140005cfb  mov     rbx, rax
0x140005cfe  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005d05  test    rax, rax
0x140005d08  jnz     short loc_140005D50
0x140005d0a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005d10  jnz     short loc_140005D5B
0x140005d12  lea     rcx, ModuleName; "ntdll.dll"
0x140005d19  call    cs:__imp_GetModuleHandleW
0x140005d1f  test    rax, rax
0x140005d22  jz      short loc_140005D3D
0x140005d24  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140005d2b  mov     rcx, rax; hModule
0x140005d2e  call    cs:__imp_GetProcAddress
0x140005d34  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005d3b  jmp     short loc_140005D44
0x140005d3d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005d44  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005d4b  test    rax, rax
0x140005d4e  jz      short loc_140005D5B
0x140005d50  mov     rdx, rbx
0x140005d53  mov     rcx, rsi
0x140005d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d5b  mov     rsi, [rsp+28h+arg_8]
0x140005d60  mov     rax, rbx
0x140005d63  mov     rbx, [rsp+28h+arg_0]
0x140005d68  add     rsp, 20h
0x140005d6c  pop     rdi
0x140005d6d  retn
```
