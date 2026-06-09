# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002c7f4`
- end: `0x18002c8ab`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180024610`
- `0x18002c2a0`
- `0x18002c3c4`
- `0x18002d448`
- `0x18002d6b8`

## callees

- `0x18002c7f4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c849`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c849`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c864`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c864`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c81f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c81f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c808`

## string_xrefs

- `0x18002c842`: `ntdll.dll`

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
0x18002c7f4  mov     [rsp+arg_0], rbx
0x18002c7f9  mov     [rsp+arg_8], rsi
0x18002c7fe  push    rdi
0x18002c7ff  sub     rsp, 20h
0x18002c803  mov     rbx, rdx
0x18002c806  mov     edi, ecx
0x18002c808  call    cs:__imp_GetProcessHeap
0x18002c80f  nop     dword ptr [rax+rax+00h]
0x18002c814  mov     r8, rbx; dwBytes
0x18002c817  mov     edx, edi; dwFlags
0x18002c819  mov     rcx, rax; hHeap
0x18002c81c  mov     rsi, rax
0x18002c81f  call    cs:__imp_HeapAlloc
0x18002c826  nop     dword ptr [rax+rax+00h]
0x18002c82b  mov     rbx, rax
0x18002c82e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002c835  test    rax, rax
0x18002c838  jnz     short loc_18002C88C
0x18002c83a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002c840  jnz     short loc_18002C897
0x18002c842  lea     rcx, ModuleName; "ntdll.dll"
0x18002c849  call    cs:__imp_GetModuleHandleW
0x18002c850  nop     dword ptr [rax+rax+00h]
0x18002c855  test    rax, rax
0x18002c858  jz      short loc_18002C879
0x18002c85a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18002c861  mov     rcx, rax; hModule
0x18002c864  call    cs:__imp_GetProcAddress
0x18002c86b  nop     dword ptr [rax+rax+00h]
0x18002c870  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002c877  jmp     short loc_18002C880
0x18002c879  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002c880  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002c887  test    rax, rax
0x18002c88a  jz      short loc_18002C897
0x18002c88c  mov     rdx, rbx
0x18002c88f  mov     rcx, rsi
0x18002c892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c897  mov     rsi, [rsp+28h+arg_8]
0x18002c89c  mov     rax, rbx
0x18002c89f  mov     rbx, [rsp+28h+arg_0]
0x18002c8a4  add     rsp, 20h
0x18002c8a8  pop     rdi
0x18002c8a9  retn
```
