# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180009a30`
- end: `0x180009a9c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `108`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180009a30`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180009a74`
- `KERNEL32!GetProcAddress` at `0x180009a74`
- `KERNEL32!GetModuleHandleW` at `0x180009a57`
- `KERNEL32!GetModuleHandleW` at `0x180009a57`

## string_xrefs

- `0x180009a50`: `ntdll.dll`
- `0x180009a6a`: `RtlDllShutdownInProgress`

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
0x180009a30  push    rbx
0x180009a32  sub     rsp, 20h
0x180009a36  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180009a3d  xor     ebx, ebx
0x180009a3f  test    rax, rax
0x180009a42  jnz     short loc_180009A8C
0x180009a44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009a4b  test    rax, rax
0x180009a4e  jnz     short loc_180009A6A
0x180009a50  lea     rcx, ModuleName; "ntdll.dll"
0x180009a57  call    cs:__imp_GetModuleHandleW
0x180009a5e  nop     dword ptr [rax+rax+00h]
0x180009a63  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009a6a  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180009a71  mov     rcx, rax; hModule
0x180009a74  call    cs:__imp_GetProcAddress
0x180009a7b  nop     dword ptr [rax+rax+00h]
0x180009a80  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180009a87  test    rax, rax
0x180009a8a  jz      short loc_180009A93
0x180009a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a91  mov     bl, al
0x180009a93  mov     al, bl
0x180009a95  add     rsp, 20h
0x180009a99  pop     rbx
0x180009a9a  retn
```
