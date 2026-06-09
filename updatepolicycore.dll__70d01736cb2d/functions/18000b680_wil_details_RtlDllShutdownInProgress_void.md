# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000b680`
- end: `0x18000b6df`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `95`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000b680`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b6a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b6a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b6be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b6be`

## string_xrefs

- `0x18000b6a0`: `ntdll.dll`
- `0x18000b6b4`: `RtlDllShutdownInProgress`

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
0x18000b680  push    rbx
0x18000b682  sub     rsp, 20h
0x18000b686  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000b68d  xor     ebx, ebx
0x18000b68f  test    rax, rax
0x18000b692  jnz     short loc_18000B6D0
0x18000b694  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b69b  test    rax, rax
0x18000b69e  jnz     short loc_18000B6B4
0x18000b6a0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000b6a7  call    cs:__imp_GetModuleHandleW
0x18000b6ad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b6b4  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000b6bb  mov     rcx, rax; hModule
0x18000b6be  call    cs:__imp_GetProcAddress
0x18000b6c4  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000b6cb  test    rax, rax
0x18000b6ce  jz      short loc_18000B6D7
0x18000b6d0  call    _guard_dispatch_icall
0x18000b6d5  mov     bl, al
0x18000b6d7  mov     al, bl
0x18000b6d9  add     rsp, 20h
0x18000b6dd  pop     rbx
0x18000b6de  retn
```
