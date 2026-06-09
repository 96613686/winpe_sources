# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000a010`
- end: `0x18000a067`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a010`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a04a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a04a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a033`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a033`

## string_xrefs

- `0x18000a02c`: `ntdll.dll`
- `0x18000a040`: `RtlDllShutdownInProgress`

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
0x18000a010  sub     rsp, 28h
0x18000a014  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000a01b  test    rax, rax
0x18000a01e  jnz     short loc_18000A05C
0x18000a020  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a027  test    rax, rax
0x18000a02a  jnz     short loc_18000A040
0x18000a02c  lea     rcx, ModuleName; "ntdll.dll"
0x18000a033  call    cs:__imp_GetModuleHandleW
0x18000a039  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a040  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000a047  mov     rcx, rax; hModule
0x18000a04a  call    cs:__imp_GetProcAddress
0x18000a050  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000a057  test    rax, rax
0x18000a05a  jz      short loc_18000A062
0x18000a05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a061  nop
0x18000a062  add     rsp, 28h
0x18000a066  retn
```
