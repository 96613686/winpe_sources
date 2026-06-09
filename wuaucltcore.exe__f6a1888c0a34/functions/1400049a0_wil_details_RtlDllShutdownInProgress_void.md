# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1400049a0`
- end: `0x1400049ff`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `95`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400049a0`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400049de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400049de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400049c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400049c7`

## string_xrefs

- `0x1400049c0`: `ntdll.dll`
- `0x1400049d4`: `RtlDllShutdownInProgress`

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
0x1400049a0  push    rbx
0x1400049a2  sub     rsp, 20h
0x1400049a6  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1400049ad  xor     ebx, ebx
0x1400049af  test    rax, rax
0x1400049b2  jnz     short loc_1400049F0
0x1400049b4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400049bb  test    rax, rax
0x1400049be  jnz     short loc_1400049D4
0x1400049c0  lea     rcx, ModuleName; "ntdll.dll"
0x1400049c7  call    cs:__imp_GetModuleHandleW
0x1400049cd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400049d4  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1400049db  mov     rcx, rax; hModule
0x1400049de  call    cs:__imp_GetProcAddress
0x1400049e4  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1400049eb  test    rax, rax
0x1400049ee  jz      short loc_1400049F7
0x1400049f0  call    _guard_dispatch_icall
0x1400049f5  mov     bl, al
0x1400049f7  mov     al, bl
0x1400049f9  add     rsp, 20h
0x1400049fd  pop     rbx
0x1400049fe  retn
```
