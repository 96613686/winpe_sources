# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180012878`
- end: `0x180012916`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001078c`
- `0x180010b30`
- `0x180011710`
- `0x180013c08`
- `0x180014a04`

## callees

- `0x180012878`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800128d6`
- `KERNEL32!GetProcAddress` at `0x1800128d6`
- `KERNEL32!GetModuleHandleW` at `0x1800128c1`
- `KERNEL32!GetModuleHandleW` at `0x1800128c1`
- `KERNEL32!HeapAlloc` at `0x18001289d`
- `KERNEL32!HeapAlloc` at `0x18001289d`
- `KERNEL32!GetProcessHeap` at `0x18001288c`
- `KERNEL32!GetProcessHeap` at `0x18001288c`

## string_xrefs

- `0x1800128ba`: `ntdll.dll`

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
0x180012878  mov     [rsp+arg_0], rbx
0x18001287d  mov     [rsp+arg_8], rsi
0x180012882  push    rdi
0x180012883  sub     rsp, 20h
0x180012887  mov     rbx, rdx
0x18001288a  mov     edi, ecx
0x18001288c  call    cs:__imp_GetProcessHeap
0x180012892  mov     r8, rbx; dwBytes
0x180012895  mov     edx, edi; dwFlags
0x180012897  mov     rcx, rax; hHeap
0x18001289a  mov     rsi, rax
0x18001289d  call    cs:__imp_HeapAlloc
0x1800128a3  mov     rbx, rax
0x1800128a6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800128ad  test    rax, rax
0x1800128b0  jnz     short loc_1800128F8
0x1800128b2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800128b8  jnz     short loc_180012903
0x1800128ba  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800128c1  call    cs:__imp_GetModuleHandleW
0x1800128c7  test    rax, rax
0x1800128ca  jz      short loc_1800128E5
0x1800128cc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800128d3  mov     rcx, rax; hModule
0x1800128d6  call    cs:__imp_GetProcAddress
0x1800128dc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800128e3  jmp     short loc_1800128EC
0x1800128e5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800128ec  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800128f3  test    rax, rax
0x1800128f6  jz      short loc_180012903
0x1800128f8  mov     rdx, rbx
0x1800128fb  mov     rcx, rsi
0x1800128fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012903  mov     rsi, [rsp+28h+arg_8]
0x180012908  mov     rax, rbx
0x18001290b  mov     rbx, [rsp+28h+arg_0]
0x180012910  add     rsp, 20h
0x180012914  pop     rdi
0x180012915  retn
```
