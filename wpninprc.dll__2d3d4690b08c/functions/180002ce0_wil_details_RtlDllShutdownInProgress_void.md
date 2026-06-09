# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180002ce0`
- end: `0x180002d37`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002ce0`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002d03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002d03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002d1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002d1a`

## string_xrefs

- `0x180002cfc`: `ntdll.dll`
- `0x180002d10`: `RtlDllShutdownInProgress`

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
0x180002ce0  sub     rsp, 28h
0x180002ce4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180002ceb  test    rax, rax
0x180002cee  jnz     short loc_180002D2C
0x180002cf0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002cf7  test    rax, rax
0x180002cfa  jnz     short loc_180002D10
0x180002cfc  lea     rcx, ModuleName; "ntdll.dll"
0x180002d03  call    cs:__imp_GetModuleHandleW
0x180002d09  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180002d10  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180002d17  mov     rcx, rax; hModule
0x180002d1a  call    cs:__imp_GetProcAddress
0x180002d20  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180002d27  test    rax, rax
0x180002d2a  jz      short loc_180002D32
0x180002d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d31  nop
0x180002d32  add     rsp, 28h
0x180002d36  retn
```
