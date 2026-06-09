# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002214c`
- end: `0x1800221ea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f330`
- `0x180021fa8`
- `0x180022550`
- `0x1800228e8`
- `0x18002aa90`

## callees

- `0x18002214c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022195`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022195`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800221aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800221aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022160`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022160`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022171`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022171`

## string_xrefs

- `0x18002218e`: `ntdll.dll`

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
0x18002214c  mov     [rsp+arg_0], rbx
0x180022151  mov     [rsp+arg_8], rsi
0x180022156  push    rdi
0x180022157  sub     rsp, 20h
0x18002215b  mov     rbx, rdx
0x18002215e  mov     edi, ecx
0x180022160  call    cs:__imp_GetProcessHeap
0x180022166  mov     rsi, rax
0x180022169  mov     r8, rbx; dwBytes
0x18002216c  mov     edx, edi; dwFlags
0x18002216e  mov     rcx, rax; hHeap
0x180022171  call    cs:__imp_HeapAlloc
0x180022177  mov     rbx, rax
0x18002217a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180022181  test    rax, rax
0x180022184  jnz     short loc_1800221CC
0x180022186  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002218c  jnz     short loc_1800221D7
0x18002218e  lea     rcx, ModuleName; "ntdll.dll"
0x180022195  call    cs:__imp_GetModuleHandleW
0x18002219b  test    rax, rax
0x18002219e  jz      short loc_1800221B9
0x1800221a0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800221a7  mov     rcx, rax; hModule
0x1800221aa  call    cs:__imp_GetProcAddress
0x1800221b0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800221b7  jmp     short loc_1800221C0
0x1800221b9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800221c0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800221c7  test    rax, rax
0x1800221ca  jz      short loc_1800221D7
0x1800221cc  mov     rdx, rbx
0x1800221cf  mov     rcx, rsi
0x1800221d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221d7  mov     rax, rbx
0x1800221da  mov     rbx, [rsp+28h+arg_0]
0x1800221df  mov     rsi, [rsp+28h+arg_8]
0x1800221e4  add     rsp, 20h
0x1800221e8  pop     rdi
0x1800221e9  retn
```
