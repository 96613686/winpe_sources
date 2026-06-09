# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000b020`
- end: `0x18000b08c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `108`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000b020`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000b047`
- `KERNEL32!GetModuleHandleW` at `0x18000b047`
- `KERNEL32!GetProcAddress` at `0x18000b064`
- `KERNEL32!GetProcAddress` at `0x18000b064`

## string_xrefs

- `0x18000b040`: `ntdll.dll`
- `0x18000b05a`: `RtlDllShutdownInProgress`

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
0x18000b020  push    rbx
0x18000b022  sub     rsp, 20h
0x18000b026  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000b02d  xor     ebx, ebx
0x18000b02f  test    rax, rax
0x18000b032  jnz     short loc_18000B07C
0x18000b034  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b03b  test    rax, rax
0x18000b03e  jnz     short loc_18000B05A
0x18000b040  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000b047  call    cs:__imp_GetModuleHandleW
0x18000b04e  nop     dword ptr [rax+rax+00h]
0x18000b053  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b05a  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000b061  mov     rcx, rax; hModule
0x18000b064  call    cs:__imp_GetProcAddress
0x18000b06b  nop     dword ptr [rax+rax+00h]
0x18000b070  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000b077  test    rax, rax
0x18000b07a  jz      short loc_18000B083
0x18000b07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b081  mov     bl, al
0x18000b083  mov     al, bl
0x18000b085  add     rsp, 20h
0x18000b089  pop     rbx
0x18000b08a  retn
```
