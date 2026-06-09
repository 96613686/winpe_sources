# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000eca0`
- end: `0x18000ed0c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `108`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000eca0`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000ece4`
- `KERNEL32!GetProcAddress` at `0x18000ece4`
- `KERNEL32!GetModuleHandleW` at `0x18000ecc7`
- `KERNEL32!GetModuleHandleW` at `0x18000ecc7`

## string_xrefs

- `0x18000ecc0`: `ntdll.dll`
- `0x18000ecda`: `RtlDllShutdownInProgress`

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
0x18000eca0  push    rbx
0x18000eca2  sub     rsp, 20h
0x18000eca6  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000ecad  xor     ebx, ebx
0x18000ecaf  test    rax, rax
0x18000ecb2  jnz     short loc_18000ECFC
0x18000ecb4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ecbb  test    rax, rax
0x18000ecbe  jnz     short loc_18000ECDA
0x18000ecc0  lea     rcx, ModuleName; "ntdll.dll"
0x18000ecc7  call    cs:__imp_GetModuleHandleW
0x18000ecce  nop     dword ptr [rax+rax+00h]
0x18000ecd3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ecda  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000ece1  mov     rcx, rax; hModule
0x18000ece4  call    cs:__imp_GetProcAddress
0x18000eceb  nop     dword ptr [rax+rax+00h]
0x18000ecf0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000ecf7  test    rax, rax
0x18000ecfa  jz      short loc_18000ED03
0x18000ecfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed01  mov     bl, al
0x18000ed03  mov     al, bl
0x18000ed05  add     rsp, 20h
0x18000ed09  pop     rbx
0x18000ed0a  retn
```
