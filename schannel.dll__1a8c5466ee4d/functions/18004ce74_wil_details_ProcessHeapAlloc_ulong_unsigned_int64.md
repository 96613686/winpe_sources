# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004ce74`
- end: `0x18004cf12`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004b580`
- `0x180062b9c`
- `0x180062cc0`
- `0x180063934`
- `0x180063aac`

## callees

- `0x18004ce74`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004ced2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004ced2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004cebd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004cebd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ce99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ce99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ce88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ce88`

## string_xrefs

- `0x18004ceb6`: `ntdll.dll`

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
0x18004ce74  mov     [rsp+arg_0], rbx
0x18004ce79  mov     [rsp+arg_8], rsi
0x18004ce7e  push    rdi
0x18004ce7f  sub     rsp, 20h
0x18004ce83  mov     rbx, rdx
0x18004ce86  mov     edi, ecx
0x18004ce88  call    cs:__imp_GetProcessHeap
0x18004ce8e  mov     r8, rbx; dwBytes
0x18004ce91  mov     edx, edi; dwFlags
0x18004ce93  mov     rcx, rax; hHeap
0x18004ce96  mov     rsi, rax
0x18004ce99  call    cs:__imp_HeapAlloc
0x18004ce9f  mov     rbx, rax
0x18004cea2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004cea9  test    rax, rax
0x18004ceac  jnz     short loc_18004CEF4
0x18004ceae  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004ceb4  jnz     short loc_18004CEFF
0x18004ceb6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18004cebd  call    cs:__imp_GetModuleHandleW
0x18004cec3  test    rax, rax
0x18004cec6  jz      short loc_18004CEE1
0x18004cec8  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18004cecf  mov     rcx, rax; hModule
0x18004ced2  call    cs:__imp_GetProcAddress
0x18004ced8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18004cedf  jmp     short loc_18004CEE8
0x18004cee1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18004cee8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18004ceef  test    rax, rax
0x18004cef2  jz      short loc_18004CEFF
0x18004cef4  mov     rdx, rbx
0x18004cef7  mov     rcx, rsi
0x18004cefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ceff  mov     rsi, [rsp+28h+arg_8]
0x18004cf04  mov     rax, rbx
0x18004cf07  mov     rbx, [rsp+28h+arg_0]
0x18004cf0c  add     rsp, 20h
0x18004cf10  pop     rdi
0x18004cf11  retn
```
