# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180032890`
- end: `0x1800328e7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180032890`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800328ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800328ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800328b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800328b3`

## string_xrefs

- `0x1800328ac`: `ntdll.dll`
- `0x1800328c0`: `RtlDllShutdownInProgress`

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
0x180032890  sub     rsp, 28h
0x180032894  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18003289b  test    rax, rax
0x18003289e  jnz     short loc_1800328DC
0x1800328a0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800328a7  test    rax, rax
0x1800328aa  jnz     short loc_1800328C0
0x1800328ac  lea     rcx, ModuleName; "ntdll.dll"
0x1800328b3  call    cs:__imp_GetModuleHandleW
0x1800328b9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800328c0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800328c7  mov     rcx, rax; hModule
0x1800328ca  call    cs:__imp_GetProcAddress
0x1800328d0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800328d7  test    rax, rax
0x1800328da  jz      short loc_1800328E2
0x1800328dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328e1  nop
0x1800328e2  add     rsp, 28h
0x1800328e6  retn
```
