# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000da6c`
- end: `0x18000db0a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b794`
- `0x18000bb64`
- `0x18000c8a0`
- `0x18000ee88`
- `0x18000ff84`

## callees

- `0x18000da6c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000daca`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000daca`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000dab5`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000dab5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000da80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000da80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000da91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000da91`

## string_xrefs

- `0x18000daae`: `ntdll.dll`

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
0x18000da6c  mov     [rsp+arg_0], rbx
0x18000da71  mov     [rsp+arg_8], rsi
0x18000da76  push    rdi
0x18000da77  sub     rsp, 20h
0x18000da7b  mov     rbx, rdx
0x18000da7e  mov     edi, ecx
0x18000da80  call    cs:__imp_GetProcessHeap
0x18000da86  mov     r8, rbx; dwBytes
0x18000da89  mov     edx, edi; dwFlags
0x18000da8b  mov     rcx, rax; hHeap
0x18000da8e  mov     rsi, rax
0x18000da91  call    cs:__imp_HeapAlloc
0x18000da97  mov     rbx, rax
0x18000da9a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000daa1  test    rax, rax
0x18000daa4  jnz     short loc_18000DAEC
0x18000daa6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000daac  jnz     short loc_18000DAF7
0x18000daae  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000dab5  call    cs:__imp_GetModuleHandleW
0x18000dabb  test    rax, rax
0x18000dabe  jz      short loc_18000DAD9
0x18000dac0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000dac7  mov     rcx, rax; hModule
0x18000daca  call    cs:__imp_GetProcAddress
0x18000dad0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000dad7  jmp     short loc_18000DAE0
0x18000dad9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000dae0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000dae7  test    rax, rax
0x18000daea  jz      short loc_18000DAF7
0x18000daec  mov     rdx, rbx
0x18000daef  mov     rcx, rsi
0x18000daf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daf7  mov     rsi, [rsp+28h+arg_8]
0x18000dafc  mov     rax, rbx
0x18000daff  mov     rbx, [rsp+28h+arg_0]
0x18000db04  add     rsp, 20h
0x18000db08  pop     rdi
0x18000db09  retn
```
