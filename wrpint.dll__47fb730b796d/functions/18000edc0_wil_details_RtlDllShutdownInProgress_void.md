# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000edc0`
- end: `0x18000ee1a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000edc0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000edfa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000edfa`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000ede3`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000ede3`

## string_xrefs

- `0x18000eddc`: `ntdll.dll`
- `0x18000edf0`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x18000edc0  sub     rsp, 28h
0x18000edc4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000edcb  test    rax, rax
0x18000edce  jnz     short loc_18000EE11
0x18000edd0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000edd7  test    rax, rax
0x18000edda  jnz     short loc_18000EDF0
0x18000eddc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ede3  call    cs:__imp_GetModuleHandleW
0x18000ede9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000edf0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000edf7  mov     rcx, rax; hModule
0x18000edfa  call    cs:__imp_GetProcAddress
0x18000ee00  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000ee07  test    rax, rax
0x18000ee0a  jnz     short loc_18000EE11
0x18000ee0c  add     rsp, 28h
0x18000ee10  retn
0x18000ee11  add     rsp, 28h
0x18000ee15  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
