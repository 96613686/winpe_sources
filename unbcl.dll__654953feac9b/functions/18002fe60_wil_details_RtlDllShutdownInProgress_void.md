# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18002fe60`
- end: `0x18002fec0`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `96`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18002fe60`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002fe8c`
- `KERNEL32!GetModuleHandleW` at `0x18002fe8c`
- `KERNEL32!GetProcAddress` at `0x18002fea3`
- `KERNEL32!GetProcAddress` at `0x18002fea3`

## string_xrefs

- `0x18002fe85`: `ntdll.dll`
- `0x18002fe99`: `RtlDllShutdownInProgress`

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
0x18002fe60  sub     rsp, 38h
0x18002fe64  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002fe6d  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18002fe74  test    rax, rax
0x18002fe77  jnz     short loc_18002FEB5
0x18002fe79  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002fe80  test    rax, rax
0x18002fe83  jnz     short loc_18002FE99
0x18002fe85  lea     rcx, ModuleName; "ntdll.dll"
0x18002fe8c  call    cs:__imp_GetModuleHandleW
0x18002fe92  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002fe99  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18002fea0  mov     rcx, rax; hModule
0x18002fea3  call    cs:__imp_GetProcAddress
0x18002fea9  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18002feb0  test    rax, rax
0x18002feb3  jz      short loc_18002FEBB
0x18002feb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002feba  nop
0x18002febb  add     rsp, 38h
0x18002febf  retn
```
