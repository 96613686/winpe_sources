# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140008a10`
- end: `0x140008a6a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140008a10`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008a4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008a4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008a33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008a33`

## string_xrefs

- `0x140008a2c`: `ntdll.dll`
- `0x140008a40`: `RtlDllShutdownInProgress`

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
0x140008a10  sub     rsp, 28h
0x140008a14  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140008a1b  test    rax, rax
0x140008a1e  jnz     short loc_140008A61
0x140008a20  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008a27  test    rax, rax
0x140008a2a  jnz     short loc_140008A40
0x140008a2c  lea     rcx, ModuleName; "ntdll.dll"
0x140008a33  call    cs:__imp_GetModuleHandleW
0x140008a39  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008a40  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140008a47  mov     rcx, rax; hModule
0x140008a4a  call    cs:__imp_GetProcAddress
0x140008a50  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140008a57  test    rax, rax
0x140008a5a  jnz     short loc_140008A61
0x140008a5c  add     rsp, 28h
0x140008a60  retn
0x140008a61  add     rsp, 28h
0x140008a65  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
