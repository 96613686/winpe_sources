# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180027330`
- end: `0x18002739e`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `110`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180027330`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180027379`
- `KERNEL32!GetProcAddress` at `0x180027379`
- `KERNEL32!GetModuleHandleW` at `0x18002735c`
- `KERNEL32!GetModuleHandleW` at `0x18002735c`

## string_xrefs

- `0x180027355`: `ntdll.dll`
- `0x18002736f`: `RtlDllShutdownInProgress`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180027330  sub     rsp, 38h
0x180027334  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002733d  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180027344  test    rax, rax
0x180027347  jnz     short loc_180027392
0x180027349  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027350  test    rax, rax
0x180027353  jnz     short loc_18002736F
0x180027355  lea     rcx, LibFileName; "ntdll.dll"
0x18002735c  call    cs:__imp_GetModuleHandleW
0x180027363  nop     dword ptr [rax+rax+00h]
0x180027368  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002736f  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180027376  mov     rcx, rax; hModule
0x180027379  call    cs:__imp_GetProcAddress
0x180027380  nop     dword ptr [rax+rax+00h]
0x180027385  nop
0x180027386  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18002738d  test    rax, rax
0x180027390  jz      short loc_180027398
0x180027392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027397  nop
0x180027398  add     rsp, 38h
0x18002739c  retn
```
