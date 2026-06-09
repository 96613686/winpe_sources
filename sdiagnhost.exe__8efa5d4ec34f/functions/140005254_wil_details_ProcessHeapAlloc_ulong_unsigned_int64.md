# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005254`
- end: `0x1400052fc`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003bd0`
- `0x140006584`

## callees

- `0x140005254`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400052bc`
- `KERNEL32!GetProcAddress` at `0x1400052bc`
- `KERNEL32!GetModuleHandleW` at `0x1400052a7`
- `KERNEL32!GetModuleHandleW` at `0x1400052a7`
- `KERNEL32!GetProcessHeap` at `0x140005272`
- `KERNEL32!GetProcessHeap` at `0x140005272`
- `KERNEL32!HeapAlloc` at `0x140005283`
- `KERNEL32!HeapAlloc` at `0x140005283`

## string_xrefs

- `0x1400052a0`: `ntdll.dll`

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
0x140005254  push    rdi
0x140005256  sub     rsp, 30h
0x14000525a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140005263  mov     [rsp+38h+arg_0], rbx
0x140005268  mov     [rsp+38h+arg_8], rsi
0x14000526d  mov     rbx, rdx
0x140005270  mov     edi, ecx
0x140005272  call    cs:__imp_GetProcessHeap
0x140005278  mov     rsi, rax
0x14000527b  mov     r8, rbx; dwBytes
0x14000527e  mov     edx, edi; dwFlags
0x140005280  mov     rcx, rax; hHeap
0x140005283  call    cs:__imp_HeapAlloc
0x140005289  mov     rbx, rax
0x14000528c  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005293  test    rax, rax
0x140005296  jnz     short loc_1400052DE
0x140005298  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000529e  jnz     short loc_1400052E9
0x1400052a0  lea     rcx, ModuleName; "ntdll.dll"
0x1400052a7  call    cs:__imp_GetModuleHandleW
0x1400052ad  test    rax, rax
0x1400052b0  jz      short loc_1400052CB
0x1400052b2  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400052b9  mov     rcx, rax; hModule
0x1400052bc  call    cs:__imp_GetProcAddress
0x1400052c2  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400052c9  jmp     short loc_1400052D2
0x1400052cb  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400052d2  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400052d9  test    rax, rax
0x1400052dc  jz      short loc_1400052E9
0x1400052de  mov     rdx, rbx
0x1400052e1  mov     rcx, rsi
0x1400052e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052e9  mov     rax, rbx
0x1400052ec  mov     rbx, [rsp+38h+arg_0]
0x1400052f1  mov     rsi, [rsp+38h+arg_8]
0x1400052f6  add     rsp, 30h
0x1400052fa  pop     rdi
0x1400052fb  retn
```
