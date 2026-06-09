# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c354`
- end: `0x18000c3f2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009b78`
- `0x180009f58`
- `0x18000b0a0`
- `0x18000d9a4`
- `0x180011038`

## callees

- `0x18000c354`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c3b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c3b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c39d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c39d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c379`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c379`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c368`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c368`

## string_xrefs

- `0x18000c396`: `ntdll.dll`

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
0x18000c354  mov     [rsp+arg_0], rbx
0x18000c359  mov     [rsp+arg_8], rsi
0x18000c35e  push    rdi
0x18000c35f  sub     rsp, 20h
0x18000c363  mov     rbx, rdx
0x18000c366  mov     edi, ecx
0x18000c368  call    cs:__imp_GetProcessHeap
0x18000c36e  mov     r8, rbx; dwBytes
0x18000c371  mov     edx, edi; dwFlags
0x18000c373  mov     rcx, rax; hHeap
0x18000c376  mov     rsi, rax
0x18000c379  call    cs:__imp_HeapAlloc
0x18000c37f  mov     rbx, rax
0x18000c382  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c389  test    rax, rax
0x18000c38c  jnz     short loc_18000C3D4
0x18000c38e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c394  jnz     short loc_18000C3DF
0x18000c396  lea     rcx, ModuleName; "ntdll.dll"
0x18000c39d  call    cs:__imp_GetModuleHandleW
0x18000c3a3  test    rax, rax
0x18000c3a6  jz      short loc_18000C3C1
0x18000c3a8  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000c3af  mov     rcx, rax; hModule
0x18000c3b2  call    cs:__imp_GetProcAddress
0x18000c3b8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000c3bf  jmp     short loc_18000C3C8
0x18000c3c1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c3c8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c3cf  test    rax, rax
0x18000c3d2  jz      short loc_18000C3DF
0x18000c3d4  mov     rdx, rbx
0x18000c3d7  mov     rcx, rsi
0x18000c3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3df  mov     rsi, [rsp+28h+arg_8]
0x18000c3e4  mov     rax, rbx
0x18000c3e7  mov     rbx, [rsp+28h+arg_0]
0x18000c3ec  add     rsp, 20h
0x18000c3f0  pop     rdi
0x18000c3f1  retn
```
