# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a438`
- end: `0x18000a4d6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b1a4`
- `0x18000b650`
- `0x18000bba4`
- `0x18000c18c`

## callees

- `0x18000a438`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a481`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a481`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a496`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a496`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a45d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a45d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a44c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a44c`

## string_xrefs

- `0x18000a47a`: `ntdll.dll`

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
0x18000a438  mov     [rsp+arg_0], rbx
0x18000a43d  mov     [rsp+arg_8], rsi
0x18000a442  push    rdi
0x18000a443  sub     rsp, 20h
0x18000a447  mov     rbx, rdx
0x18000a44a  mov     edi, ecx
0x18000a44c  call    cs:__imp_GetProcessHeap
0x18000a452  mov     rsi, rax
0x18000a455  mov     r8, rbx; dwBytes
0x18000a458  mov     edx, edi; dwFlags
0x18000a45a  mov     rcx, rax; hHeap
0x18000a45d  call    cs:__imp_HeapAlloc
0x18000a463  mov     rbx, rax
0x18000a466  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a46d  test    rax, rax
0x18000a470  jnz     short loc_18000A4B8
0x18000a472  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a478  jnz     short loc_18000A4C3
0x18000a47a  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000a481  call    cs:__imp_GetModuleHandleW
0x18000a487  test    rax, rax
0x18000a48a  jz      short loc_18000A4A5
0x18000a48c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000a493  mov     rcx, rax; hModule
0x18000a496  call    cs:__imp_GetProcAddress
0x18000a49c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000a4a3  jmp     short loc_18000A4AC
0x18000a4a5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a4ac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a4b3  test    rax, rax
0x18000a4b6  jz      short loc_18000A4C3
0x18000a4b8  mov     rdx, rbx
0x18000a4bb  mov     rcx, rsi
0x18000a4be  call    _guard_dispatch_icall
0x18000a4c3  mov     rax, rbx
0x18000a4c6  mov     rbx, [rsp+28h+arg_0]
0x18000a4cb  mov     rsi, [rsp+28h+arg_8]
0x18000a4d0  add     rsp, 20h
0x18000a4d4  pop     rdi
0x18000a4d5  retn
```
