# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800044b0`
- end: `0x18000450f`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `95`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800044b0`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800044ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800044ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800044d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800044d7`

## string_xrefs

- `0x1800044d0`: `ntdll.dll`
- `0x1800044e4`: `RtlDllShutdownInProgress`

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
0x1800044b0  push    rbx
0x1800044b2  sub     rsp, 20h
0x1800044b6  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800044bd  xor     ebx, ebx
0x1800044bf  test    rax, rax
0x1800044c2  jnz     short loc_180004500
0x1800044c4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800044cb  test    rax, rax
0x1800044ce  jnz     short loc_1800044E4
0x1800044d0  lea     rcx, ModuleName; "ntdll.dll"
0x1800044d7  call    cs:__imp_GetModuleHandleW
0x1800044dd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800044e4  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800044eb  mov     rcx, rax; hModule
0x1800044ee  call    cs:__imp_GetProcAddress
0x1800044f4  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1800044fb  test    rax, rax
0x1800044fe  jz      short loc_180004507
0x180004500  call    _guard_dispatch_icall
0x180004505  mov     bl, al
0x180004507  mov     al, bl
0x180004509  add     rsp, 20h
0x18000450d  pop     rbx
0x18000450e  retn
```
