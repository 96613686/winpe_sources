# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000ffe0`
- end: `0x180010037`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ffe0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180010003`
- `KERNEL32!GetModuleHandleW` at `0x180010003`
- `KERNEL32!GetProcAddress` at `0x18001001a`
- `KERNEL32!GetProcAddress` at `0x18001001a`

## string_xrefs

- `0x18000fffc`: `ntdll.dll`
- `0x180010010`: `RtlDllShutdownInProgress`

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
0x18000ffe0  sub     rsp, 28h
0x18000ffe4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000ffeb  test    rax, rax
0x18000ffee  jnz     short loc_18001002C
0x18000fff0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fff7  test    rax, rax
0x18000fffa  jnz     short loc_180010010
0x18000fffc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180010003  call    cs:__imp_GetModuleHandleW
0x180010009  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010010  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180010017  mov     rcx, rax; hModule
0x18001001a  call    cs:__imp_GetProcAddress
0x180010020  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180010027  test    rax, rax
0x18001002a  jz      short loc_180010032
0x18001002c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010031  nop
0x180010032  add     rsp, 28h
0x180010036  retn
```
