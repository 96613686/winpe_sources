# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180009010`
- end: `0x180009067`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009010`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009033`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009033`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000904a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000904a`

## string_xrefs

- `0x18000902c`: `ntdll.dll`
- `0x180009040`: `RtlDllShutdownInProgress`

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
0x180009010  sub     rsp, 28h
0x180009014  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000901b  test    rax, rax
0x18000901e  jnz     short loc_18000905C
0x180009020  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009027  test    rax, rax
0x18000902a  jnz     short loc_180009040
0x18000902c  lea     rcx, ModuleName; "ntdll.dll"
0x180009033  call    cs:__imp_GetModuleHandleW
0x180009039  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009040  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180009047  mov     rcx, rax; hModule
0x18000904a  call    cs:__imp_GetProcAddress
0x180009050  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180009057  test    rax, rax
0x18000905a  jz      short loc_180009062
0x18000905c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009061  nop
0x180009062  add     rsp, 28h
0x180009066  retn
```
