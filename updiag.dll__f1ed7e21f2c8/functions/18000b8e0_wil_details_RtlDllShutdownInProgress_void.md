# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000b8e0`
- end: `0x18000b93f`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `95`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000b8e0`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b907`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b907`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b91e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b91e`

## string_xrefs

- `0x18000b900`: `ntdll.dll`
- `0x18000b914`: `RtlDllShutdownInProgress`

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
0x18000b8e0  push    rbx
0x18000b8e2  sub     rsp, 20h
0x18000b8e6  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000b8ed  xor     ebx, ebx
0x18000b8ef  test    rax, rax
0x18000b8f2  jnz     short loc_18000B930
0x18000b8f4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b8fb  test    rax, rax
0x18000b8fe  jnz     short loc_18000B914
0x18000b900  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000b907  call    cs:__imp_GetModuleHandleW
0x18000b90d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b914  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000b91b  mov     rcx, rax; hModule
0x18000b91e  call    cs:__imp_GetProcAddress
0x18000b924  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000b92b  test    rax, rax
0x18000b92e  jz      short loc_18000B937
0x18000b930  call    _guard_dispatch_icall
0x18000b935  mov     bl, al
0x18000b937  mov     al, bl
0x18000b939  add     rsp, 20h
0x18000b93d  pop     rbx
0x18000b93e  retn
```
