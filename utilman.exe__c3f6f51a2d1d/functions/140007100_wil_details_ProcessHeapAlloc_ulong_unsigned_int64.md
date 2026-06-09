# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140007100`
- end: `0x1400071a9`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140005cd4`
- `0x140006a94`
- `0x140006bf8`
- `0x140008214`
- `0x1400086b4`
- `0x140009be0`

## callees

- `0x1400037b8`
- `0x140007100`
- `0x140029010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000712b`
- `KERNEL32!HeapAlloc` at `0x14000712b`
- `KERNEL32!GetProcessHeap` at `0x140007114`
- `KERNEL32!GetProcessHeap` at `0x140007114`
- `KERNEL32!GetModuleHandleW` at `0x140007155`
- `KERNEL32!GetModuleHandleW` at `0x140007155`

## string_xrefs

- `0x14000714e`: `ntdll.dll`

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
0x140007100  mov     [rsp+arg_0], rbx
0x140007105  mov     [rsp+arg_8], rsi
0x14000710a  push    rdi
0x14000710b  sub     rsp, 20h
0x14000710f  mov     rbx, rdx
0x140007112  mov     edi, ecx
0x140007114  call    cs:__imp_GetProcessHeap
0x14000711b  nop     dword ptr [rax+rax+00h]
0x140007120  mov     rsi, rax
0x140007123  mov     r8, rbx; dwBytes
0x140007126  mov     edx, edi; dwFlags
0x140007128  mov     rcx, rax; hHeap
0x14000712b  call    cs:__imp_HeapAlloc
0x140007132  nop     dword ptr [rax+rax+00h]
0x140007137  mov     rbx, rax
0x14000713a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140007141  test    rax, rax
0x140007144  jnz     short loc_14000718A
0x140007146  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000714c  jnz     short loc_140007195
0x14000714e  lea     rcx, ModuleName; "ntdll.dll"
0x140007155  call    cs:__imp_GetModuleHandleW
0x14000715c  nop     dword ptr [rax+rax+00h]
0x140007161  test    rax, rax
0x140007164  jz      short loc_140007177
0x140007166  mov     rcx, rax
0x140007169  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x14000716e  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140007175  jmp     short loc_14000717E
0x140007177  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000717e  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140007185  test    rax, rax
0x140007188  jz      short loc_140007195
0x14000718a  mov     rdx, rbx
0x14000718d  mov     rcx, rsi
0x140007190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007195  mov     rax, rbx
0x140007198  mov     rbx, [rsp+28h+arg_0]
0x14000719d  mov     rsi, [rsp+28h+arg_8]
0x1400071a2  add     rsp, 20h
0x1400071a6  pop     rdi
0x1400071a7  retn
```
