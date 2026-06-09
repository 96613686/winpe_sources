# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800071b8`
- end: `0x180007256`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005188`
- `0x18000555c`
- `0x180006250`
- `0x180008a24`
- `0x18000a35c`

## callees

- `0x1800071b8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007201`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007201`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007216`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007216`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800071dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800071dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071cc`

## string_xrefs

- `0x1800071fa`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800071b8  mov     [rsp+arg_0], rbx
0x1800071bd  mov     [rsp+arg_8], rsi
0x1800071c2  push    rdi
0x1800071c3  sub     rsp, 20h
0x1800071c7  mov     rbx, rdx
0x1800071ca  mov     edi, ecx
0x1800071cc  call    cs:__imp_GetProcessHeap
0x1800071d2  mov     rsi, rax
0x1800071d5  mov     r8, rbx; dwBytes
0x1800071d8  mov     edx, edi; dwFlags
0x1800071da  mov     rcx, rax; hHeap
0x1800071dd  call    cs:__imp_HeapAlloc
0x1800071e3  mov     rbx, rax
0x1800071e6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800071ed  test    rax, rax
0x1800071f0  jnz     short loc_180007238
0x1800071f2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800071f8  jnz     short loc_180007243
0x1800071fa  lea     rcx, ModuleName; "ntdll.dll"
0x180007201  call    cs:__imp_GetModuleHandleW
0x180007207  test    rax, rax
0x18000720a  jz      short loc_180007225
0x18000720c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007213  mov     rcx, rax; hModule
0x180007216  call    cs:__imp_GetProcAddress
0x18000721c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007223  jmp     short loc_18000722C
0x180007225  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000722c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007233  test    rax, rax
0x180007236  jz      short loc_180007243
0x180007238  mov     rdx, rbx
0x18000723b  mov     rcx, rsi
0x18000723e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007243  mov     rax, rbx
0x180007246  mov     rbx, [rsp+28h+arg_0]
0x18000724b  mov     rsi, [rsp+28h+arg_8]
0x180007250  add     rsp, 20h
0x180007254  pop     rdi
0x180007255  retn
```
