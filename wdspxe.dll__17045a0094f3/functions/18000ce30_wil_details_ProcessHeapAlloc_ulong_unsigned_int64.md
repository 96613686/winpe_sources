# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000ce30`
- end: `0x18000cee7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a204`
- `0x18000a5fc`
- `0x18000f64c`
- `0x18000fa7c`
- `0x180010b88`

## callees

- `0x18000ce30`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000cea0`
- `KERNEL32!GetProcAddress` at `0x18000cea0`
- `KERNEL32!GetProcessHeap` at `0x18000ce44`
- `KERNEL32!GetProcessHeap` at `0x18000ce44`
- `KERNEL32!HeapAlloc` at `0x18000ce5b`
- `KERNEL32!HeapAlloc` at `0x18000ce5b`
- `KERNEL32!GetModuleHandleW` at `0x18000ce85`
- `KERNEL32!GetModuleHandleW` at `0x18000ce85`

## string_xrefs

- `0x18000ce7e`: `ntdll.dll`

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
0x18000ce30  mov     [rsp+arg_0], rbx
0x18000ce35  mov     [rsp+arg_8], rsi
0x18000ce3a  push    rdi
0x18000ce3b  sub     rsp, 20h
0x18000ce3f  mov     rbx, rdx
0x18000ce42  mov     edi, ecx
0x18000ce44  call    cs:__imp_GetProcessHeap
0x18000ce4b  nop     dword ptr [rax+rax+00h]
0x18000ce50  mov     r8, rbx; dwBytes
0x18000ce53  mov     edx, edi; dwFlags
0x18000ce55  mov     rcx, rax; hHeap
0x18000ce58  mov     rsi, rax
0x18000ce5b  call    cs:__imp_HeapAlloc
0x18000ce62  nop     dword ptr [rax+rax+00h]
0x18000ce67  mov     rbx, rax
0x18000ce6a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ce71  test    rax, rax
0x18000ce74  jnz     short loc_18000CEC8
0x18000ce76  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ce7c  jnz     short loc_18000CED3
0x18000ce7e  lea     rcx, ModuleName; "ntdll.dll"
0x18000ce85  call    cs:__imp_GetModuleHandleW
0x18000ce8c  nop     dword ptr [rax+rax+00h]
0x18000ce91  test    rax, rax
0x18000ce94  jz      short loc_18000CEB5
0x18000ce96  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000ce9d  mov     rcx, rax; hModule
0x18000cea0  call    cs:__imp_GetProcAddress
0x18000cea7  nop     dword ptr [rax+rax+00h]
0x18000ceac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000ceb3  jmp     short loc_18000CEBC
0x18000ceb5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000cebc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000cec3  test    rax, rax
0x18000cec6  jz      short loc_18000CED3
0x18000cec8  mov     rdx, rbx
0x18000cecb  mov     rcx, rsi
0x18000cece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ced3  mov     rsi, [rsp+28h+arg_8]
0x18000ced8  mov     rax, rbx
0x18000cedb  mov     rbx, [rsp+28h+arg_0]
0x18000cee0  add     rsp, 20h
0x18000cee4  pop     rdi
0x18000cee5  retn
```
