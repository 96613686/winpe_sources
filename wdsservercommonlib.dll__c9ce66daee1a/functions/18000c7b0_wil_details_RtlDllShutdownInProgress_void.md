# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000c7b0`
- end: `0x18000c81c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `108`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000c7b0`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000c7f4`
- `KERNEL32!GetProcAddress` at `0x18000c7f4`
- `KERNEL32!GetModuleHandleW` at `0x18000c7d7`
- `KERNEL32!GetModuleHandleW` at `0x18000c7d7`

## string_xrefs

- `0x18000c7d0`: `ntdll.dll`
- `0x18000c7ea`: `RtlDllShutdownInProgress`

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
0x18000c7b0  push    rbx
0x18000c7b2  sub     rsp, 20h
0x18000c7b6  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000c7bd  xor     ebx, ebx
0x18000c7bf  test    rax, rax
0x18000c7c2  jnz     short loc_18000C80C
0x18000c7c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c7cb  test    rax, rax
0x18000c7ce  jnz     short loc_18000C7EA
0x18000c7d0  lea     rcx, ModuleName; "ntdll.dll"
0x18000c7d7  call    cs:__imp_GetModuleHandleW
0x18000c7de  nop     dword ptr [rax+rax+00h]
0x18000c7e3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c7ea  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000c7f1  mov     rcx, rax; hModule
0x18000c7f4  call    cs:__imp_GetProcAddress
0x18000c7fb  nop     dword ptr [rax+rax+00h]
0x18000c800  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000c807  test    rax, rax
0x18000c80a  jz      short loc_18000C813
0x18000c80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c811  mov     bl, al
0x18000c813  mov     al, bl
0x18000c815  add     rsp, 20h
0x18000c819  pop     rbx
0x18000c81a  retn
```
