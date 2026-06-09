# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002675c`
- end: `0x1800267f2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180025dc0`
- `0x180026a3c`
- `0x180026bb4`

## callees

- `0x180024110`
- `0x18002675c`
- `0x18002a010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180026781`
- `KERNEL32!HeapAlloc` at `0x180026781`
- `KERNEL32!GetProcessHeap` at `0x180026770`
- `KERNEL32!GetProcessHeap` at `0x180026770`
- `KERNEL32!GetModuleHandleW` at `0x1800267a5`
- `KERNEL32!GetModuleHandleW` at `0x1800267a5`

## string_xrefs

- `0x18002679e`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  void (__fastcall *ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)(HANDLE, LPVOID); // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (void (__fastcall *)(HANDLE, LPVOID))(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW),
                                              `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z) )
  {
    ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ProcessHeap, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18002675c  mov     [rsp+arg_0], rbx
0x180026761  mov     [rsp+arg_8], rsi
0x180026766  push    rdi
0x180026767  sub     rsp, 20h
0x18002676b  mov     rbx, rdx
0x18002676e  mov     edi, ecx
0x180026770  call    cs:__imp_GetProcessHeap
0x180026776  mov     r8, rbx; dwBytes
0x180026779  mov     edx, edi; dwFlags
0x18002677b  mov     rcx, rax; hHeap
0x18002677e  mov     rsi, rax
0x180026781  call    cs:__imp_HeapAlloc
0x180026787  mov     rbx, rax
0x18002678a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180026791  test    rax, rax
0x180026794  jnz     short loc_1800267D4
0x180026796  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002679c  jnz     short loc_1800267DF
0x18002679e  lea     rcx, ModuleName; "ntdll.dll"
0x1800267a5  call    cs:__imp_GetModuleHandleW
0x1800267ab  test    rax, rax
0x1800267ae  jz      short loc_1800267C1
0x1800267b0  mov     rcx, rax
0x1800267b3  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800267b8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800267bf  jmp     short loc_1800267C8
0x1800267c1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800267c8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800267cf  test    rax, rax
0x1800267d2  jz      short loc_1800267DF
0x1800267d4  mov     rdx, rbx
0x1800267d7  mov     rcx, rsi
0x1800267da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267df  mov     rsi, [rsp+28h+arg_8]
0x1800267e4  mov     rax, rbx
0x1800267e7  mov     rbx, [rsp+28h+arg_0]
0x1800267ec  add     rsp, 20h
0x1800267f0  pop     rdi
0x1800267f1  retn
```
