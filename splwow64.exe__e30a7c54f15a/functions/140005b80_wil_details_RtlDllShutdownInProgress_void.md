# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140005b80`
- end: `0x140005bda`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140005b80`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140005bba`
- `KERNEL32!GetProcAddress` at `0x140005bba`
- `KERNEL32!GetModuleHandleW` at `0x140005ba3`
- `KERNEL32!GetModuleHandleW` at `0x140005ba3`

## string_xrefs

- `0x140005b9c`: `ntdll.dll`
- `0x140005bb0`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x140005b80  sub     rsp, 28h
0x140005b84  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140005b8b  test    rax, rax
0x140005b8e  jnz     short loc_140005BD1
0x140005b90  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005b97  test    rax, rax
0x140005b9a  jnz     short loc_140005BB0
0x140005b9c  lea     rcx, ModuleName; "ntdll.dll"
0x140005ba3  call    cs:__imp_GetModuleHandleW
0x140005ba9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA, rax; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005bb0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140005bb7  mov     rcx, rax; hModule
0x140005bba  call    cs:__imp_GetProcAddress
0x140005bc0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140005bc7  test    rax, rax
0x140005bca  jnz     short loc_140005BD1
0x140005bcc  add     rsp, 28h
0x140005bd0  retn
0x140005bd1  add     rsp, 28h
0x140005bd5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
