# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000c350`
- end: `0x18000c3b7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `103`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000c350`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000c390`
- `KERNEL32!GetProcAddress` at `0x18000c390`
- `KERNEL32!GetModuleHandleW` at `0x18000c373`
- `KERNEL32!GetModuleHandleW` at `0x18000c373`

## string_xrefs

- `0x18000c36c`: `ntdll.dll`
- `0x18000c386`: `RtlDllShutdownInProgress`

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
0x18000c350  sub     rsp, 28h
0x18000c354  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000c35b  test    rax, rax
0x18000c35e  jnz     short loc_18000C3AE
0x18000c360  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c367  test    rax, rax
0x18000c36a  jnz     short loc_18000C386
0x18000c36c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000c373  call    cs:__imp_GetModuleHandleW
0x18000c37a  nop     dword ptr [rax+rax+00h]
0x18000c37f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c386  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000c38d  mov     rcx, rax; hModule
0x18000c390  call    cs:__imp_GetProcAddress
0x18000c397  nop     dword ptr [rax+rax+00h]
0x18000c39c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000c3a3  test    rax, rax
0x18000c3a6  jnz     short loc_18000C3AE
0x18000c3a8  add     rsp, 28h
0x18000c3ac  retn
0x18000c3ae  add     rsp, 28h
0x18000c3b2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
