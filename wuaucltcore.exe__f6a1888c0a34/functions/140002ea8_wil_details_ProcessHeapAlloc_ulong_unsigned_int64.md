# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140002ea8`
- end: `0x140002f46`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400042b0`
- `0x140004710`
- `0x140004b40`
- `0x140005b58`

## callees

- `0x140002ea8`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002f06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002f06`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140002ef1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140002ef1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140002ecd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140002ecd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002ebc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002ebc`

## string_xrefs

- `0x140002eea`: `ntdll.dll`

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
0x140002ea8  mov     [rsp+arg_0], rbx
0x140002ead  mov     [rsp+arg_8], rsi
0x140002eb2  push    rdi
0x140002eb3  sub     rsp, 20h
0x140002eb7  mov     rbx, rdx
0x140002eba  mov     edi, ecx
0x140002ebc  call    cs:__imp_GetProcessHeap
0x140002ec2  mov     rsi, rax
0x140002ec5  mov     r8, rbx; dwBytes
0x140002ec8  mov     edx, edi; dwFlags
0x140002eca  mov     rcx, rax; hHeap
0x140002ecd  call    cs:__imp_HeapAlloc
0x140002ed3  mov     rbx, rax
0x140002ed6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140002edd  test    rax, rax
0x140002ee0  jnz     short loc_140002F28
0x140002ee2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140002ee8  jnz     short loc_140002F33
0x140002eea  lea     rcx, ModuleName; "ntdll.dll"
0x140002ef1  call    cs:__imp_GetModuleHandleW
0x140002ef7  test    rax, rax
0x140002efa  jz      short loc_140002F15
0x140002efc  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140002f03  mov     rcx, rax; hModule
0x140002f06  call    cs:__imp_GetProcAddress
0x140002f0c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140002f13  jmp     short loc_140002F1C
0x140002f15  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140002f1c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140002f23  test    rax, rax
0x140002f26  jz      short loc_140002F33
0x140002f28  mov     rdx, rbx
0x140002f2b  mov     rcx, rsi
0x140002f2e  call    _guard_dispatch_icall
0x140002f33  mov     rax, rbx
0x140002f36  mov     rbx, [rsp+28h+arg_0]
0x140002f3b  mov     rsi, [rsp+28h+arg_8]
0x140002f40  add     rsp, 20h
0x140002f44  pop     rdi
0x140002f45  retn
```
