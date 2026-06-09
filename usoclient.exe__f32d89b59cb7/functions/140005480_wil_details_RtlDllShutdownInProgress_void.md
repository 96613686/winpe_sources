# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140005480`
- end: `0x1400054d7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140005480`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400054ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400054ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400054a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400054a3`

## string_xrefs

- `0x14000549c`: `ntdll.dll`
- `0x1400054b0`: `RtlDllShutdownInProgress`

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
0x140005480  sub     rsp, 28h
0x140005484  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000548b  test    rax, rax
0x14000548e  jnz     short loc_1400054CC
0x140005490  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005497  test    rax, rax
0x14000549a  jnz     short loc_1400054B0
0x14000549c  lea     rcx, ModuleName; "ntdll.dll"
0x1400054a3  call    cs:__imp_GetModuleHandleW
0x1400054a9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400054b0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1400054b7  mov     rcx, rax; hModule
0x1400054ba  call    cs:__imp_GetProcAddress
0x1400054c0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1400054c7  test    rax, rax
0x1400054ca  jz      short loc_1400054D2
0x1400054cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054d1  nop
0x1400054d2  add     rsp, 28h
0x1400054d6  retn
```
