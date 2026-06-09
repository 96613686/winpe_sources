# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001aa40`
- end: `0x18001aaf7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a624`
- `0x18001a74c`
- `0x18001b928`
- `0x18001bb64`
- `0x18001c904`

## callees

- `0x18001aa40`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aa54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aa54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aa6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aa6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001aa95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001aa95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001aab0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001aab0`

## string_xrefs

- `0x18001aa8e`: `ntdll.dll`

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
0x18001aa40  mov     [rsp+arg_0], rbx
0x18001aa45  mov     [rsp+arg_8], rsi
0x18001aa4a  push    rdi
0x18001aa4b  sub     rsp, 20h
0x18001aa4f  mov     rbx, rdx
0x18001aa52  mov     edi, ecx
0x18001aa54  call    cs:__imp_GetProcessHeap
0x18001aa5b  nop     dword ptr [rax+rax+00h]
0x18001aa60  mov     r8, rbx; dwBytes
0x18001aa63  mov     edx, edi; dwFlags
0x18001aa65  mov     rcx, rax; hHeap
0x18001aa68  mov     rsi, rax
0x18001aa6b  call    cs:__imp_HeapAlloc
0x18001aa72  nop     dword ptr [rax+rax+00h]
0x18001aa77  mov     rbx, rax
0x18001aa7a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001aa81  test    rax, rax
0x18001aa84  jnz     short loc_18001AAD8
0x18001aa86  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001aa8c  jnz     short loc_18001AAE3
0x18001aa8e  lea     rcx, ModuleName; "ntdll.dll"
0x18001aa95  call    cs:__imp_GetModuleHandleW
0x18001aa9c  nop     dword ptr [rax+rax+00h]
0x18001aaa1  test    rax, rax
0x18001aaa4  jz      short loc_18001AAC5
0x18001aaa6  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18001aaad  mov     rcx, rax; hModule
0x18001aab0  call    cs:__imp_GetProcAddress
0x18001aab7  nop     dword ptr [rax+rax+00h]
0x18001aabc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001aac3  jmp     short loc_18001AACC
0x18001aac5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001aacc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001aad3  test    rax, rax
0x18001aad6  jz      short loc_18001AAE3
0x18001aad8  mov     rdx, rbx
0x18001aadb  mov     rcx, rsi
0x18001aade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aae3  mov     rsi, [rsp+28h+arg_8]
0x18001aae8  mov     rax, rbx
0x18001aaeb  mov     rbx, [rsp+28h+arg_0]
0x18001aaf0  add     rsp, 20h
0x18001aaf4  pop     rdi
0x18001aaf5  retn
```
