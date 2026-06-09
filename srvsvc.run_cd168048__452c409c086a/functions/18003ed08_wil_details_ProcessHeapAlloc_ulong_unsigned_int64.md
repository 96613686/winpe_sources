# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003ed08`
- end: `0x18003eda6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003e900`
- `0x18003ea28`
- `0x18003fb54`
- `0x18003fd80`
- `0x180040bec`

## callees

- `0x18003ed08`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ed66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ed66`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ed51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ed51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ed1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ed1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ed2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ed2d`

## string_xrefs

- `0x18003ed4a`: `ntdll.dll`

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
0x18003ed08  mov     [rsp+arg_0], rbx
0x18003ed0d  mov     [rsp+arg_8], rsi
0x18003ed12  push    rdi
0x18003ed13  sub     rsp, 20h
0x18003ed17  mov     rbx, rdx
0x18003ed1a  mov     edi, ecx
0x18003ed1c  call    cs:__imp_GetProcessHeap
0x18003ed22  mov     r8, rbx; dwBytes
0x18003ed25  mov     edx, edi; dwFlags
0x18003ed27  mov     rcx, rax; hHeap
0x18003ed2a  mov     rsi, rax
0x18003ed2d  call    cs:__imp_HeapAlloc
0x18003ed33  mov     rbx, rax
0x18003ed36  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003ed3d  test    rax, rax
0x18003ed40  jnz     short loc_18003ED88
0x18003ed42  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18003ed48  jnz     short loc_18003ED93
0x18003ed4a  lea     rcx, ModuleName; "ntdll.dll"
0x18003ed51  call    cs:__imp_GetModuleHandleW
0x18003ed57  test    rax, rax
0x18003ed5a  jz      short loc_18003ED75
0x18003ed5c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18003ed63  mov     rcx, rax; hModule
0x18003ed66  call    cs:__imp_GetProcAddress
0x18003ed6c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18003ed73  jmp     short loc_18003ED7C
0x18003ed75  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003ed7c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18003ed83  test    rax, rax
0x18003ed86  jz      short loc_18003ED93
0x18003ed88  mov     rdx, rbx
0x18003ed8b  mov     rcx, rsi
0x18003ed8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed93  mov     rsi, [rsp+28h+arg_8]
0x18003ed98  mov     rax, rbx
0x18003ed9b  mov     rbx, [rsp+28h+arg_0]
0x18003eda0  add     rsp, 20h
0x18003eda4  pop     rdi
0x18003eda5  retn
```
