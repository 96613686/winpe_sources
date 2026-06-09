# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140005f00`
- end: `0x140005f5a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140005f00`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005f23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005f23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005f3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005f3a`

## string_xrefs

- `0x140005f1c`: `ntdll.dll`
- `0x140005f30`: `RtlDllShutdownInProgress`

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
0x140005f00  sub     rsp, 28h
0x140005f04  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x140005f0b  test    rax, rax
0x140005f0e  jnz     short loc_140005F51
0x140005f10  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005f17  test    rax, rax
0x140005f1a  jnz     short loc_140005F30
0x140005f1c  lea     rcx, ModuleName; "ntdll.dll"
0x140005f23  call    cs:__imp_GetModuleHandleW
0x140005f29  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005f30  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140005f37  mov     rcx, rax; hModule
0x140005f3a  call    cs:__imp_GetProcAddress
0x140005f40  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140005f47  test    rax, rax
0x140005f4a  jnz     short loc_140005F51
0x140005f4c  add     rsp, 28h
0x140005f50  retn
0x140005f51  add     rsp, 28h
0x140005f55  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
