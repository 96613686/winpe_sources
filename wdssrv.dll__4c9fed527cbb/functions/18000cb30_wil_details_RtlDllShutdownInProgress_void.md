# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000cb30`
- end: `0x18000cb9c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `108`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000cb30`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000cb57`
- `KERNEL32!GetModuleHandleW` at `0x18000cb57`
- `KERNEL32!GetProcAddress` at `0x18000cb74`
- `KERNEL32!GetProcAddress` at `0x18000cb74`

## string_xrefs

- `0x18000cb50`: `ntdll.dll`
- `0x18000cb6a`: `RtlDllShutdownInProgress`

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
0x18000cb30  push    rbx
0x18000cb32  sub     rsp, 20h
0x18000cb36  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000cb3d  xor     ebx, ebx
0x18000cb3f  test    rax, rax
0x18000cb42  jnz     short loc_18000CB8C
0x18000cb44  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cb4b  test    rax, rax
0x18000cb4e  jnz     short loc_18000CB6A
0x18000cb50  lea     rcx, ModuleName; "ntdll.dll"
0x18000cb57  call    cs:__imp_GetModuleHandleW
0x18000cb5e  nop     dword ptr [rax+rax+00h]
0x18000cb63  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cb6a  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000cb71  mov     rcx, rax; hModule
0x18000cb74  call    cs:__imp_GetProcAddress
0x18000cb7b  nop     dword ptr [rax+rax+00h]
0x18000cb80  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000cb87  test    rax, rax
0x18000cb8a  jz      short loc_18000CB93
0x18000cb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb91  mov     bl, al
0x18000cb93  mov     al, bl
0x18000cb95  add     rsp, 20h
0x18000cb99  pop     rbx
0x18000cb9a  retn
```
