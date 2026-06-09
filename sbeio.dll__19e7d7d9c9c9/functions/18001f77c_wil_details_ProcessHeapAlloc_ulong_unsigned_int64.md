# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001f77c`
- end: `0x18001f81a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001d87c`
- `0x1800244ac`
- `0x180024cbc`
- `0x180027200`

## callees

- `0x18001f77c`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001f7da`
- `KERNEL32!GetProcAddress` at `0x18001f7da`
- `KERNEL32!HeapAlloc` at `0x18001f7a1`
- `KERNEL32!HeapAlloc` at `0x18001f7a1`
- `KERNEL32!GetProcessHeap` at `0x18001f790`
- `KERNEL32!GetProcessHeap` at `0x18001f790`
- `KERNEL32!GetModuleHandleW` at `0x18001f7c5`
- `KERNEL32!GetModuleHandleW` at `0x18001f7c5`

## string_xrefs

- `0x18001f7be`: `ntdll.dll`

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
0x18001f77c  mov     [rsp+arg_0], rbx
0x18001f781  mov     [rsp+arg_8], rsi
0x18001f786  push    rdi
0x18001f787  sub     rsp, 20h
0x18001f78b  mov     rbx, rdx
0x18001f78e  mov     edi, ecx
0x18001f790  call    cs:__imp_GetProcessHeap
0x18001f796  mov     r8, rbx; dwBytes
0x18001f799  mov     edx, edi; dwFlags
0x18001f79b  mov     rcx, rax; hHeap
0x18001f79e  mov     rsi, rax
0x18001f7a1  call    cs:__imp_HeapAlloc
0x18001f7a7  mov     rbx, rax
0x18001f7aa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001f7b1  test    rax, rax
0x18001f7b4  jnz     short loc_18001F7FC
0x18001f7b6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001f7bc  jnz     short loc_18001F807
0x18001f7be  lea     rcx, aNtdllDll; "ntdll.dll"
0x18001f7c5  call    cs:__imp_GetModuleHandleW
0x18001f7cb  test    rax, rax
0x18001f7ce  jz      short loc_18001F7E9
0x18001f7d0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18001f7d7  mov     rcx, rax; hModule
0x18001f7da  call    cs:__imp_GetProcAddress
0x18001f7e0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001f7e7  jmp     short loc_18001F7F0
0x18001f7e9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001f7f0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001f7f7  test    rax, rax
0x18001f7fa  jz      short loc_18001F807
0x18001f7fc  mov     rdx, rbx
0x18001f7ff  mov     rcx, rsi
0x18001f802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f807  mov     rsi, [rsp+28h+arg_8]
0x18001f80c  mov     rax, rbx
0x18001f80f  mov     rbx, [rsp+28h+arg_0]
0x18001f814  add     rsp, 20h
0x18001f818  pop     rdi
0x18001f819  retn
```
