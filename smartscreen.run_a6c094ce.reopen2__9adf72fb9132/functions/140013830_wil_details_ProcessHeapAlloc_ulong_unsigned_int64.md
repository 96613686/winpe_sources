# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140013830`
- end: `0x1400138e7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000cbc0`
- `0x14002f514`
- `0x14002f660`

## callees

- `0x140013830`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400138a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400138a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140013885`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140013885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013844`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013844`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001385b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001385b`

## string_xrefs

- `0x14001387e`: `ntdll.dll`

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
0x140013830  mov     [rsp+arg_0], rbx
0x140013835  mov     [rsp+arg_8], rsi
0x14001383a  push    rdi
0x14001383b  sub     rsp, 20h
0x14001383f  mov     rbx, rdx
0x140013842  mov     edi, ecx
0x140013844  call    cs:__imp_GetProcessHeap
0x14001384b  nop     dword ptr [rax+rax+00h]
0x140013850  mov     rsi, rax
0x140013853  mov     r8, rbx; dwBytes
0x140013856  mov     edx, edi; dwFlags
0x140013858  mov     rcx, rax; hHeap
0x14001385b  call    cs:__imp_HeapAlloc
0x140013862  nop     dword ptr [rax+rax+00h]
0x140013867  mov     rbx, rax
0x14001386a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140013871  test    rax, rax
0x140013874  jnz     short loc_1400138C8
0x140013876  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14001387c  jnz     short loc_1400138D3
0x14001387e  lea     rcx, ModuleName; "ntdll.dll"
0x140013885  call    cs:__imp_GetModuleHandleW
0x14001388c  nop     dword ptr [rax+rax+00h]
0x140013891  test    rax, rax
0x140013894  jz      short loc_1400138B5
0x140013896  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x14001389d  mov     rcx, rax; hModule
0x1400138a0  call    cs:__imp_GetProcAddress
0x1400138a7  nop     dword ptr [rax+rax+00h]
0x1400138ac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400138b3  jmp     short loc_1400138BC
0x1400138b5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400138bc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400138c3  test    rax, rax
0x1400138c6  jz      short loc_1400138D3
0x1400138c8  mov     rdx, rbx
0x1400138cb  mov     rcx, rsi
0x1400138ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400138d3  mov     rax, rbx
0x1400138d6  mov     rbx, [rsp+28h+arg_0]
0x1400138db  mov     rsi, [rsp+28h+arg_8]
0x1400138e0  add     rsp, 20h
0x1400138e4  pop     rdi
0x1400138e5  retn
```
