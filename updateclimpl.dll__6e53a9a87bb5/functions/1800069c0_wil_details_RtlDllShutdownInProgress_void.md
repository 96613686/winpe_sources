# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800069c0`
- end: `0x180006a1f`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `95`
- prototype: `char __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800069c0`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800069e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800069e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800069fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800069fe`

## string_xrefs

- `0x1800069e0`: `ntdll.dll`
- `0x1800069f4`: `RtlDllShutdownInProgress`

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
0x1800069c0  push    rbx
0x1800069c2  sub     rsp, 20h
0x1800069c6  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800069cd  xor     ebx, ebx
0x1800069cf  test    rax, rax
0x1800069d2  jnz     short loc_180006A10
0x1800069d4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800069db  test    rax, rax
0x1800069de  jnz     short loc_1800069F4
0x1800069e0  lea     rcx, ModuleName; "ntdll.dll"
0x1800069e7  call    cs:__imp_GetModuleHandleW
0x1800069ed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800069f4  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800069fb  mov     rcx, rax; hModule
0x1800069fe  call    cs:__imp_GetProcAddress
0x180006a04  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180006a0b  test    rax, rax
0x180006a0e  jz      short loc_180006A17
0x180006a10  call    _guard_dispatch_icall
0x180006a15  mov     bl, al
0x180006a17  mov     al, bl
0x180006a19  add     rsp, 20h
0x180006a1d  pop     rbx
0x180006a1e  retn
```
