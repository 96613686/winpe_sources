# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b3f0`
- end: `0x18000b4a7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009110`
- `0x180009508`
- `0x18000c8b0`
- `0x18000cc44`
- `0x18000db90`

## callees

- `0x18000b3f0`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b460`
- `KERNEL32!GetProcAddress` at `0x18000b460`
- `KERNEL32!GetProcessHeap` at `0x18000b404`
- `KERNEL32!GetProcessHeap` at `0x18000b404`
- `KERNEL32!HeapAlloc` at `0x18000b41b`
- `KERNEL32!HeapAlloc` at `0x18000b41b`
- `KERNEL32!GetModuleHandleW` at `0x18000b445`
- `KERNEL32!GetModuleHandleW` at `0x18000b445`

## string_xrefs

- `0x18000b43e`: `ntdll.dll`

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
0x18000b3f0  mov     [rsp+arg_0], rbx
0x18000b3f5  mov     [rsp+arg_8], rsi
0x18000b3fa  push    rdi
0x18000b3fb  sub     rsp, 20h
0x18000b3ff  mov     rbx, rdx
0x18000b402  mov     edi, ecx
0x18000b404  call    cs:__imp_GetProcessHeap
0x18000b40b  nop     dword ptr [rax+rax+00h]
0x18000b410  mov     r8, rbx; dwBytes
0x18000b413  mov     edx, edi; dwFlags
0x18000b415  mov     rcx, rax; hHeap
0x18000b418  mov     rsi, rax
0x18000b41b  call    cs:__imp_HeapAlloc
0x18000b422  nop     dword ptr [rax+rax+00h]
0x18000b427  mov     rbx, rax
0x18000b42a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b431  test    rax, rax
0x18000b434  jnz     short loc_18000B488
0x18000b436  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b43c  jnz     short loc_18000B493
0x18000b43e  lea     rcx, ModuleName; "ntdll.dll"
0x18000b445  call    cs:__imp_GetModuleHandleW
0x18000b44c  nop     dword ptr [rax+rax+00h]
0x18000b451  test    rax, rax
0x18000b454  jz      short loc_18000B475
0x18000b456  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000b45d  mov     rcx, rax; hModule
0x18000b460  call    cs:__imp_GetProcAddress
0x18000b467  nop     dword ptr [rax+rax+00h]
0x18000b46c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000b473  jmp     short loc_18000B47C
0x18000b475  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b47c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b483  test    rax, rax
0x18000b486  jz      short loc_18000B493
0x18000b488  mov     rdx, rbx
0x18000b48b  mov     rcx, rsi
0x18000b48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b493  mov     rsi, [rsp+28h+arg_8]
0x18000b498  mov     rax, rbx
0x18000b49b  mov     rbx, [rsp+28h+arg_0]
0x18000b4a0  add     rsp, 20h
0x18000b4a4  pop     rdi
0x18000b4a5  retn
```
