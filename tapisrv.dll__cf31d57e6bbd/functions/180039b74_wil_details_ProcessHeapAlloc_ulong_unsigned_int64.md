# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180039b74`
- end: `0x180039c12`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800396e4`
- `0x18003980c`
- `0x18003add4`
- `0x18003b0ac`
- `0x18003c66c`

## callees

- `0x180039b74`
- `0x180040010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180039b88`
- `KERNEL32!GetProcessHeap` at `0x180039b88`
- `KERNEL32!HeapAlloc` at `0x180039b99`
- `KERNEL32!HeapAlloc` at `0x180039b99`
- `KERNEL32!GetModuleHandleW` at `0x180039bbd`
- `KERNEL32!GetModuleHandleW` at `0x180039bbd`
- `KERNEL32!GetProcAddress` at `0x180039bd2`
- `KERNEL32!GetProcAddress` at `0x180039bd2`

## string_xrefs

- `0x180039bb6`: `ntdll.dll`

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
0x180039b74  mov     [rsp+arg_0], rbx
0x180039b79  mov     [rsp+arg_8], rsi
0x180039b7e  push    rdi
0x180039b7f  sub     rsp, 20h
0x180039b83  mov     rbx, rdx
0x180039b86  mov     edi, ecx
0x180039b88  call    cs:__imp_GetProcessHeap
0x180039b8e  mov     r8, rbx; dwBytes
0x180039b91  mov     edx, edi; dwFlags
0x180039b93  mov     rcx, rax; hHeap
0x180039b96  mov     rsi, rax
0x180039b99  call    cs:__imp_HeapAlloc
0x180039b9f  mov     rbx, rax
0x180039ba2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180039ba9  test    rax, rax
0x180039bac  jnz     short loc_180039BF4
0x180039bae  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180039bb4  jnz     short loc_180039BFF
0x180039bb6  lea     rcx, ModuleName; "ntdll.dll"
0x180039bbd  call    cs:__imp_GetModuleHandleW
0x180039bc3  test    rax, rax
0x180039bc6  jz      short loc_180039BE1
0x180039bc8  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180039bcf  mov     rcx, rax; hModule
0x180039bd2  call    cs:__imp_GetProcAddress
0x180039bd8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180039bdf  jmp     short loc_180039BE8
0x180039be1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180039be8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180039bef  test    rax, rax
0x180039bf2  jz      short loc_180039BFF
0x180039bf4  mov     rdx, rbx
0x180039bf7  mov     rcx, rsi
0x180039bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bff  mov     rsi, [rsp+28h+arg_8]
0x180039c04  mov     rax, rbx
0x180039c07  mov     rbx, [rsp+28h+arg_0]
0x180039c0c  add     rsp, 20h
0x180039c10  pop     rdi
0x180039c11  retn
```
