# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004ba4`
- end: `0x180004c42`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800048b8`
- `0x18000503c`
- `0x1800053d4`

## callees

- `0x180004ba4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004bed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004bed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004c02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bb8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004bc9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004bc9`

## string_xrefs

- `0x180004be6`: `ntdll.dll`

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
0x180004ba4  mov     [rsp+arg_0], rbx
0x180004ba9  mov     [rsp+arg_8], rsi
0x180004bae  push    rdi
0x180004baf  sub     rsp, 20h
0x180004bb3  mov     rbx, rdx
0x180004bb6  mov     edi, ecx
0x180004bb8  call    cs:__imp_GetProcessHeap
0x180004bbe  mov     rsi, rax
0x180004bc1  mov     r8, rbx; dwBytes
0x180004bc4  mov     edx, edi; dwFlags
0x180004bc6  mov     rcx, rax; hHeap
0x180004bc9  call    cs:__imp_HeapAlloc
0x180004bcf  mov     rbx, rax
0x180004bd2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004bd9  test    rax, rax
0x180004bdc  jnz     short loc_180004C24
0x180004bde  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004be4  jnz     short loc_180004C2F
0x180004be6  lea     rcx, aNtdllDll; "ntdll.dll"
0x180004bed  call    cs:__imp_GetModuleHandleW
0x180004bf3  test    rax, rax
0x180004bf6  jz      short loc_180004C11
0x180004bf8  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004bff  mov     rcx, rax; hModule
0x180004c02  call    cs:__imp_GetProcAddress
0x180004c08  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004c0f  jmp     short loc_180004C18
0x180004c11  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004c18  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004c1f  test    rax, rax
0x180004c22  jz      short loc_180004C2F
0x180004c24  mov     rdx, rbx
0x180004c27  mov     rcx, rsi
0x180004c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c2f  mov     rax, rbx
0x180004c32  mov     rbx, [rsp+28h+arg_0]
0x180004c37  mov     rsi, [rsp+28h+arg_8]
0x180004c3c  add     rsp, 20h
0x180004c40  pop     rdi
0x180004c41  retn
```
