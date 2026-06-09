# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180005a40`
- end: `0x180005a97`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005a40`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005a63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005a63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a7a`

## string_xrefs

- `0x180005a5c`: `ntdll.dll`
- `0x180005a70`: `RtlDllShutdownInProgress`

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
0x180005a40  sub     rsp, 28h
0x180005a44  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180005a4b  test    rax, rax
0x180005a4e  jnz     short loc_180005A8C
0x180005a50  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005a57  test    rax, rax
0x180005a5a  jnz     short loc_180005A70
0x180005a5c  lea     rcx, Src; "ntdll.dll"
0x180005a63  call    cs:__imp_GetModuleHandleW
0x180005a69  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005a70  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180005a77  mov     rcx, rax; hModule
0x180005a7a  call    cs:__imp_GetProcAddress
0x180005a80  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005a87  test    rax, rax
0x180005a8a  jz      short loc_180005A92
0x180005a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a91  nop
0x180005a92  add     rsp, 28h
0x180005a96  retn
```
