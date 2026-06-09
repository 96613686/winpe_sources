# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180003020`
- end: `0x180003077`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180003020`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000305a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000305a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003043`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003043`

## string_xrefs

- `0x18000303c`: `ntdll.dll`
- `0x180003050`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x180003020  sub     rsp, 28h
0x180003024  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000302b  test    rax, rax
0x18000302e  jnz     short loc_18000306C
0x180003030  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003037  test    rax, rax
0x18000303a  jnz     short loc_180003050
0x18000303c  lea     rcx, ModuleName; "ntdll.dll"
0x180003043  call    cs:__imp_GetModuleHandleW
0x180003049  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003050  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180003057  mov     rcx, rax; hModule
0x18000305a  call    cs:__imp_GetProcAddress
0x180003060  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180003067  test    rax, rax
0x18000306a  jz      short loc_180003072
0x18000306c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003071  nop
0x180003072  add     rsp, 28h
0x180003076  retn
```
