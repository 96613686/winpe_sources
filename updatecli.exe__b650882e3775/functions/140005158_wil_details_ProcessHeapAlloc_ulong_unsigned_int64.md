# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005158`
- end: `0x1400051f6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003a18`
- `0x140004100`
- `0x1400054c0`

## callees

- `0x140005158`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400051a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400051a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400051b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400051b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000517d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000517d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000516c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000516c`

## string_xrefs

- `0x14000519a`: `ntdll.dll`

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
0x140005158  mov     [rsp+arg_0], rbx
0x14000515d  mov     [rsp+arg_8], rsi
0x140005162  push    rdi
0x140005163  sub     rsp, 20h
0x140005167  mov     rbx, rdx
0x14000516a  mov     edi, ecx
0x14000516c  call    cs:__imp_GetProcessHeap
0x140005172  mov     rsi, rax
0x140005175  mov     r8, rbx; dwBytes
0x140005178  mov     edx, edi; dwFlags
0x14000517a  mov     rcx, rax; hHeap
0x14000517d  call    cs:__imp_HeapAlloc
0x140005183  mov     rbx, rax
0x140005186  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000518d  test    rax, rax
0x140005190  jnz     short loc_1400051D8
0x140005192  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005198  jnz     short loc_1400051E3
0x14000519a  lea     rcx, ModuleName; "ntdll.dll"
0x1400051a1  call    cs:__imp_GetModuleHandleW
0x1400051a7  test    rax, rax
0x1400051aa  jz      short loc_1400051C5
0x1400051ac  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400051b3  mov     rcx, rax; hModule
0x1400051b6  call    cs:__imp_GetProcAddress
0x1400051bc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400051c3  jmp     short loc_1400051CC
0x1400051c5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400051cc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400051d3  test    rax, rax
0x1400051d6  jz      short loc_1400051E3
0x1400051d8  mov     rdx, rbx
0x1400051db  mov     rcx, rsi
0x1400051de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051e3  mov     rax, rbx
0x1400051e6  mov     rbx, [rsp+28h+arg_0]
0x1400051eb  mov     rsi, [rsp+28h+arg_8]
0x1400051f0  add     rsp, 20h
0x1400051f4  pop     rdi
0x1400051f5  retn
```
