# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000d2f0`
- end: `0x18000d35c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `108`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000d2f0`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d334`
- `KERNEL32!GetProcAddress` at `0x18000d334`
- `KERNEL32!GetModuleHandleW` at `0x18000d317`
- `KERNEL32!GetModuleHandleW` at `0x18000d317`

## string_xrefs

- `0x18000d310`: `ntdll.dll`
- `0x18000d32a`: `RtlDllShutdownInProgress`

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
0x18000d2f0  push    rbx
0x18000d2f2  sub     rsp, 20h
0x18000d2f6  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000d2fd  xor     ebx, ebx
0x18000d2ff  test    rax, rax
0x18000d302  jnz     short loc_18000D34C
0x18000d304  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d30b  test    rax, rax
0x18000d30e  jnz     short loc_18000D32A
0x18000d310  lea     rcx, ModuleName; "ntdll.dll"
0x18000d317  call    cs:__imp_GetModuleHandleW
0x18000d31e  nop     dword ptr [rax+rax+00h]
0x18000d323  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d32a  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000d331  mov     rcx, rax; hModule
0x18000d334  call    cs:__imp_GetProcAddress
0x18000d33b  nop     dword ptr [rax+rax+00h]
0x18000d340  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000d347  test    rax, rax
0x18000d34a  jz      short loc_18000D353
0x18000d34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d351  mov     bl, al
0x18000d353  mov     al, bl
0x18000d355  add     rsp, 20h
0x18000d359  pop     rbx
0x18000d35a  retn
```
