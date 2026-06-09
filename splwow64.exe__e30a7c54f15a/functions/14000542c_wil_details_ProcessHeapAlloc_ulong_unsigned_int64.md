# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000542c`
- end: `0x1400054ca`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400036fc`
- `0x140004120`
- `0x140005c48`
- `0x140009214`
- `0x14000c354`

## callees

- `0x14000542c`
- `0x140016010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140005451`
- `KERNEL32!HeapAlloc` at `0x140005451`
- `KERNEL32!GetProcAddress` at `0x14000548a`
- `KERNEL32!GetProcAddress` at `0x14000548a`
- `KERNEL32!GetProcessHeap` at `0x140005440`
- `KERNEL32!GetProcessHeap` at `0x140005440`
- `KERNEL32!GetModuleHandleW` at `0x140005475`
- `KERNEL32!GetModuleHandleW` at `0x140005475`

## string_xrefs

- `0x14000546e`: `ntdll.dll`

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
0x14000542c  mov     [rsp+arg_0], rbx
0x140005431  mov     [rsp+arg_8], rsi
0x140005436  push    rdi
0x140005437  sub     rsp, 20h
0x14000543b  mov     rbx, rdx
0x14000543e  mov     edi, ecx
0x140005440  call    cs:__imp_GetProcessHeap
0x140005446  mov     r8, rbx; dwBytes
0x140005449  mov     edx, edi; dwFlags
0x14000544b  mov     rcx, rax; hHeap
0x14000544e  mov     rsi, rax
0x140005451  call    cs:__imp_HeapAlloc
0x140005457  mov     rbx, rax
0x14000545a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005461  test    rax, rax
0x140005464  jnz     short loc_1400054AC
0x140005466  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000546c  jnz     short loc_1400054B7
0x14000546e  lea     rcx, ModuleName; "ntdll.dll"
0x140005475  call    cs:__imp_GetModuleHandleW
0x14000547b  test    rax, rax
0x14000547e  jz      short loc_140005499
0x140005480  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140005487  mov     rcx, rax; hModule
0x14000548a  call    cs:__imp_GetProcAddress
0x140005490  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005497  jmp     short loc_1400054A0
0x140005499  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400054a0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400054a7  test    rax, rax
0x1400054aa  jz      short loc_1400054B7
0x1400054ac  mov     rdx, rbx
0x1400054af  mov     rcx, rsi
0x1400054b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054b7  mov     rsi, [rsp+28h+arg_8]
0x1400054bc  mov     rax, rbx
0x1400054bf  mov     rbx, [rsp+28h+arg_0]
0x1400054c4  add     rsp, 20h
0x1400054c8  pop     rdi
0x1400054c9  retn
```
