# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180008960`
- end: `0x1800089b7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180008960`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008983`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000899a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000899a`

## string_xrefs

- `0x18000897c`: `ntdll.dll`
- `0x180008990`: `RtlDllShutdownInProgress`

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
0x180008960  sub     rsp, 28h
0x180008964  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000896b  test    rax, rax
0x18000896e  jnz     short loc_1800089AC
0x180008970  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008977  test    rax, rax
0x18000897a  jnz     short loc_180008990
0x18000897c  lea     rcx, ModuleName; "ntdll.dll"
0x180008983  call    cs:__imp_GetModuleHandleW
0x180008989  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008990  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180008997  mov     rcx, rax; hModule
0x18000899a  call    cs:__imp_GetProcAddress
0x1800089a0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800089a7  test    rax, rax
0x1800089aa  jz      short loc_1800089B2
0x1800089ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089b1  nop
0x1800089b2  add     rsp, 28h
0x1800089b6  retn
```
