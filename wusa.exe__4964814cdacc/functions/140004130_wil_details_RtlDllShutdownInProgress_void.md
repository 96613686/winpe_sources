# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140004130`
- end: `0x14000418a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140004130`
- `0x140015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000416a`
- `KERNEL32!GetProcAddress` at `0x14000416a`
- `KERNEL32!GetModuleHandleW` at `0x140004153`
- `KERNEL32!GetModuleHandleW` at `0x140004153`

## string_xrefs

- `0x14000414c`: `ntdll.dll`
- `0x140004160`: `RtlDllShutdownInProgress`

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
0x140004130  sub     rsp, 28h
0x140004134  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000413b  test    rax, rax
0x14000413e  jnz     short loc_140004181
0x140004140  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004147  test    rax, rax
0x14000414a  jnz     short loc_140004160
0x14000414c  lea     rcx, ModuleName; "ntdll.dll"
0x140004153  call    cs:__imp_GetModuleHandleW
0x140004159  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140004160  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x140004167  mov     rcx, rax; hModule
0x14000416a  call    cs:__imp_GetProcAddress
0x140004170  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x140004177  test    rax, rax
0x14000417a  jnz     short loc_140004181
0x14000417c  add     rsp, 28h
0x140004180  retn
0x140004181  add     rsp, 28h
0x140004185  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
