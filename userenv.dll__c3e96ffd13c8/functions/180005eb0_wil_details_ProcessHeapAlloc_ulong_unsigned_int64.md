# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005eb0`
- end: `0x180005f46`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800058dc`
- `0x180010fec`
- `0x180011280`
- `0x1800113bc`
- `0x1800159c8`
- `0x180017bfc`

## callees

- `0x180005eb0`
- `0x18000ff28`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ef9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ef9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ed5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ed5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ec4`

## string_xrefs

- `0x180005ef2`: `ntdll.dll`

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
0x180005eb0  mov     [rsp+arg_0], rbx
0x180005eb5  mov     [rsp+arg_8], rsi
0x180005eba  push    rdi
0x180005ebb  sub     rsp, 20h
0x180005ebf  mov     rbx, rdx
0x180005ec2  mov     edi, ecx
0x180005ec4  call    cs:__imp_GetProcessHeap
0x180005eca  mov     rsi, rax
0x180005ecd  mov     r8, rbx; dwBytes
0x180005ed0  mov     edx, edi; dwFlags
0x180005ed2  mov     rcx, rax; hHeap
0x180005ed5  call    cs:__imp_HeapAlloc
0x180005edb  mov     rbx, rax
0x180005ede  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005ee5  test    rax, rax
0x180005ee8  jnz     short loc_180005F1F
0x180005eea  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005ef0  jnz     short loc_180005F2A
0x180005ef2  lea     rcx, ModuleName; "ntdll.dll"
0x180005ef9  call    cs:__imp_GetModuleHandleW
0x180005eff  test    rax, rax
0x180005f02  jz      short loc_180005F3D
0x180005f04  mov     rcx, rax
0x180005f07  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180005f0c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005f13  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005f1a  test    rax, rax
0x180005f1d  jz      short loc_180005F2A
0x180005f1f  mov     rdx, rbx
0x180005f22  mov     rcx, rsi
0x180005f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f2a  mov     rax, rbx
0x180005f2d  mov     rbx, [rsp+28h+arg_0]
0x180005f32  mov     rsi, [rsp+28h+arg_8]
0x180005f37  add     rsp, 20h
0x180005f3b  pop     rdi
0x180005f3c  retn
0x180005f3d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005f44  jmp     short loc_180005F13
```
