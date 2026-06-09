# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002551c`
- end: `0x1800255ba`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001bcdc`
- `0x180025070`
- `0x180025aec`
- `0x180025e88`

## callees

- `0x18002551c`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002557a`
- `KERNEL32!GetProcAddress` at `0x18002557a`
- `KERNEL32!HeapAlloc` at `0x180025541`
- `KERNEL32!HeapAlloc` at `0x180025541`
- `KERNEL32!GetProcessHeap` at `0x180025530`
- `KERNEL32!GetProcessHeap` at `0x180025530`
- `KERNEL32!GetModuleHandleW` at `0x180025565`
- `KERNEL32!GetModuleHandleW` at `0x180025565`

## string_xrefs

- `0x18002555e`: `ntdll.dll`

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
0x18002551c  mov     [rsp+arg_0], rbx
0x180025521  mov     [rsp+arg_8], rsi
0x180025526  push    rdi
0x180025527  sub     rsp, 20h
0x18002552b  mov     rbx, rdx
0x18002552e  mov     edi, ecx
0x180025530  call    cs:__imp_GetProcessHeap
0x180025536  mov     r8, rbx; dwBytes
0x180025539  mov     edx, edi; dwFlags
0x18002553b  mov     rcx, rax; hHeap
0x18002553e  mov     rsi, rax
0x180025541  call    cs:__imp_HeapAlloc
0x180025547  mov     rbx, rax
0x18002554a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180025551  test    rax, rax
0x180025554  jnz     short loc_18002559C
0x180025556  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002555c  jnz     short loc_1800255A7
0x18002555e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180025565  call    cs:__imp_GetModuleHandleW
0x18002556b  test    rax, rax
0x18002556e  jz      short loc_180025589
0x180025570  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180025577  mov     rcx, rax; hModule
0x18002557a  call    cs:__imp_GetProcAddress
0x180025580  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180025587  jmp     short loc_180025590
0x180025589  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180025590  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180025597  test    rax, rax
0x18002559a  jz      short loc_1800255A7
0x18002559c  mov     rdx, rbx
0x18002559f  mov     rcx, rsi
0x1800255a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255a7  mov     rsi, [rsp+28h+arg_8]
0x1800255ac  mov     rax, rbx
0x1800255af  mov     rbx, [rsp+28h+arg_0]
0x1800255b4  add     rsp, 20h
0x1800255b8  pop     rdi
0x1800255b9  retn
```
