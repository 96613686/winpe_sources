# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000ae8c`
- end: `0x18000af43`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800054e0`
- `0x18000a5c0`
- `0x18000c3c0`

## callees

- `0x18000ae8c`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000aefc`
- `KERNEL32!GetProcAddress` at `0x18000aefc`
- `KERNEL32!GetModuleHandleW` at `0x18000aee1`
- `KERNEL32!GetModuleHandleW` at `0x18000aee1`
- `KERNEL32!HeapAlloc` at `0x18000aeb7`
- `KERNEL32!HeapAlloc` at `0x18000aeb7`
- `KERNEL32!GetProcessHeap` at `0x18000aea0`
- `KERNEL32!GetProcessHeap` at `0x18000aea0`

## string_xrefs

- `0x18000aeda`: `ntdll.dll`

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
0x18000ae8c  mov     [rsp+arg_0], rbx
0x18000ae91  mov     [rsp+arg_8], rsi
0x18000ae96  push    rdi
0x18000ae97  sub     rsp, 20h
0x18000ae9b  mov     rbx, rdx
0x18000ae9e  mov     edi, ecx
0x18000aea0  call    cs:__imp_GetProcessHeap
0x18000aea7  nop     dword ptr [rax+rax+00h]
0x18000aeac  mov     r8, rbx; dwBytes
0x18000aeaf  mov     edx, edi; dwFlags
0x18000aeb1  mov     rcx, rax; hHeap
0x18000aeb4  mov     rsi, rax
0x18000aeb7  call    cs:__imp_HeapAlloc
0x18000aebe  nop     dword ptr [rax+rax+00h]
0x18000aec3  mov     rbx, rax
0x18000aec6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000aecd  test    rax, rax
0x18000aed0  jnz     short loc_18000AF24
0x18000aed2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000aed8  jnz     short loc_18000AF2F
0x18000aeda  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000aee1  call    cs:__imp_GetModuleHandleW
0x18000aee8  nop     dword ptr [rax+rax+00h]
0x18000aeed  test    rax, rax
0x18000aef0  jz      short loc_18000AF11
0x18000aef2  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000aef9  mov     rcx, rax; hModule
0x18000aefc  call    cs:__imp_GetProcAddress
0x18000af03  nop     dword ptr [rax+rax+00h]
0x18000af08  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000af0f  jmp     short loc_18000AF18
0x18000af11  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000af18  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000af1f  test    rax, rax
0x18000af22  jz      short loc_18000AF2F
0x18000af24  mov     rdx, rbx
0x18000af27  mov     rcx, rsi
0x18000af2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af2f  mov     rsi, [rsp+28h+arg_8]
0x18000af34  mov     rax, rbx
0x18000af37  mov     rbx, [rsp+28h+arg_0]
0x18000af3c  add     rsp, 20h
0x18000af40  pop     rdi
0x18000af41  retn
```
