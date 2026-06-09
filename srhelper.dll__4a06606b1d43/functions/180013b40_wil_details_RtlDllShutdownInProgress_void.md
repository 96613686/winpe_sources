# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180013b40`
- end: `0x180013b9a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180013b40`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180013b7a`
- `KERNEL32!GetProcAddress` at `0x180013b7a`
- `KERNEL32!GetModuleHandleW` at `0x180013b63`
- `KERNEL32!GetModuleHandleW` at `0x180013b63`

## string_xrefs

- `0x180013b5c`: `ntdll.dll`
- `0x180013b70`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180013b40  sub     rsp, 28h
0x180013b44  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180013b4b  test    rax, rax
0x180013b4e  jnz     short loc_180013B91
0x180013b50  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013b57  test    rax, rax
0x180013b5a  jnz     short loc_180013B70
0x180013b5c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180013b63  call    cs:__imp_GetModuleHandleW
0x180013b69  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013b70  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180013b77  mov     rcx, rax; hModule
0x180013b7a  call    cs:__imp_GetProcAddress
0x180013b80  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180013b87  test    rax, rax
0x180013b8a  jnz     short loc_180013B91
0x180013b8c  add     rsp, 28h
0x180013b90  retn
0x180013b91  add     rsp, 28h
0x180013b95  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
