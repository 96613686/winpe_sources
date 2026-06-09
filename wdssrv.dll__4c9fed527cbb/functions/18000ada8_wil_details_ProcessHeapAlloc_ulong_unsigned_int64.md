# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000ada8`
- end: `0x18000ae5f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000794c`
- `0x180007d44`
- `0x18000cee8`
- `0x18000d27c`
- `0x18000ecd8`

## callees

- `0x18000ada8`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000adbc`
- `KERNEL32!GetProcessHeap` at `0x18000adbc`
- `KERNEL32!HeapAlloc` at `0x18000add3`
- `KERNEL32!HeapAlloc` at `0x18000add3`
- `KERNEL32!GetModuleHandleW` at `0x18000adfd`
- `KERNEL32!GetModuleHandleW` at `0x18000adfd`
- `KERNEL32!GetProcAddress` at `0x18000ae18`
- `KERNEL32!GetProcAddress` at `0x18000ae18`

## string_xrefs

- `0x18000adf6`: `ntdll.dll`

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
0x18000ada8  mov     [rsp+arg_0], rbx
0x18000adad  mov     [rsp+arg_8], rsi
0x18000adb2  push    rdi
0x18000adb3  sub     rsp, 20h
0x18000adb7  mov     rbx, rdx
0x18000adba  mov     edi, ecx
0x18000adbc  call    cs:__imp_GetProcessHeap
0x18000adc3  nop     dword ptr [rax+rax+00h]
0x18000adc8  mov     r8, rbx; dwBytes
0x18000adcb  mov     edx, edi; dwFlags
0x18000adcd  mov     rcx, rax; hHeap
0x18000add0  mov     rsi, rax
0x18000add3  call    cs:__imp_HeapAlloc
0x18000adda  nop     dword ptr [rax+rax+00h]
0x18000addf  mov     rbx, rax
0x18000ade2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ade9  test    rax, rax
0x18000adec  jnz     short loc_18000AE40
0x18000adee  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000adf4  jnz     short loc_18000AE4B
0x18000adf6  lea     rcx, ModuleName; "ntdll.dll"
0x18000adfd  call    cs:__imp_GetModuleHandleW
0x18000ae04  nop     dword ptr [rax+rax+00h]
0x18000ae09  test    rax, rax
0x18000ae0c  jz      short loc_18000AE2D
0x18000ae0e  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000ae15  mov     rcx, rax; hModule
0x18000ae18  call    cs:__imp_GetProcAddress
0x18000ae1f  nop     dword ptr [rax+rax+00h]
0x18000ae24  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000ae2b  jmp     short loc_18000AE34
0x18000ae2d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ae34  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ae3b  test    rax, rax
0x18000ae3e  jz      short loc_18000AE4B
0x18000ae40  mov     rdx, rbx
0x18000ae43  mov     rcx, rsi
0x18000ae46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae4b  mov     rsi, [rsp+28h+arg_8]
0x18000ae50  mov     rax, rbx
0x18000ae53  mov     rbx, [rsp+28h+arg_0]
0x18000ae58  add     rsp, 20h
0x18000ae5c  pop     rdi
0x18000ae5d  retn
```
