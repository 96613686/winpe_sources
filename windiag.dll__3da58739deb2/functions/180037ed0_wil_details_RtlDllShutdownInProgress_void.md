# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180037ed0`
- end: `0x180037f27`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180037ed0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037f0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037f0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180037ef3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180037ef3`

## string_xrefs

- `0x180037eec`: `ntdll.dll`
- `0x180037f00`: `RtlDllShutdownInProgress`

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
0x180037ed0  sub     rsp, 28h
0x180037ed4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180037edb  test    rax, rax
0x180037ede  jnz     short loc_180037F1C
0x180037ee0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180037ee7  test    rax, rax
0x180037eea  jnz     short loc_180037F00
0x180037eec  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180037ef3  call    cs:__imp_GetModuleHandleW
0x180037ef9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180037f00  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180037f07  mov     rcx, rax; hModule
0x180037f0a  call    cs:__imp_GetProcAddress
0x180037f10  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180037f17  test    rax, rax
0x180037f1a  jz      short loc_180037F22
0x180037f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f21  nop
0x180037f22  add     rsp, 28h
0x180037f26  retn
```
