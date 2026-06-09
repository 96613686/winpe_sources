# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180002720`
- end: `0x18000277a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002720`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000275a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000275a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002743`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002743`

## string_xrefs

- `0x18000273c`: `ntdll.dll`
- `0x180002750`: `RtlDllShutdownInProgress`

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
0x180002720  sub     rsp, 28h
0x180002724  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000272b  test    rax, rax
0x18000272e  jnz     short loc_180002771
0x180002730  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002737  test    rax, rax
0x18000273a  jnz     short loc_180002750
0x18000273c  lea     rcx, ModuleName; "ntdll.dll"
0x180002743  call    cs:__imp_GetModuleHandleW
0x180002749  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002750  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180002757  mov     rcx, rax; hModule
0x18000275a  call    cs:__imp_GetProcAddress
0x180002760  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180002767  test    rax, rax
0x18000276a  jnz     short loc_180002771
0x18000276c  add     rsp, 28h
0x180002770  retn
0x180002771  add     rsp, 28h
0x180002775  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
