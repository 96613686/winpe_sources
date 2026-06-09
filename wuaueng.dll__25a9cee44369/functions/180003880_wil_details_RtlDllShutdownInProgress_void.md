# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180003880`
- end: `0x1800038df`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `95`
- prototype: `char __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180003880`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800038be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800038be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800038a7`

## string_xrefs

- `0x1800038a0`: `ntdll.dll`
- `0x1800038b4`: `RtlDllShutdownInProgress`

## pseudocode

```c
char __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC ProcAddress; // rax
  char v2; // bl
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  v2 = 0;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return ((__int64 (__fastcall *)(wil::details *))ProcAddress)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(wil::details *))ProcAddress)(this);
  return v2;
}

```

## disassembly

```asm
0x180003880  push    rbx
0x180003882  sub     rsp, 20h
0x180003886  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000388d  xor     ebx, ebx
0x18000388f  test    rax, rax
0x180003892  jnz     short loc_1800038D0
0x180003894  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000389b  test    rax, rax
0x18000389e  jnz     short loc_1800038B4
0x1800038a0  lea     rcx, ModuleName; "ntdll.dll"
0x1800038a7  call    cs:__imp_GetModuleHandleW
0x1800038ad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800038b4  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800038bb  mov     rcx, rax; hModule
0x1800038be  call    cs:__imp_GetProcAddress
0x1800038c4  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800038cb  test    rax, rax
0x1800038ce  jz      short loc_1800038D7
0x1800038d0  call    _guard_dispatch_icall
0x1800038d5  mov     bl, al
0x1800038d7  mov     al, bl
0x1800038d9  add     rsp, 20h
0x1800038dd  pop     rbx
0x1800038de  retn
```
