# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18001c310`
- end: `0x18001c36a`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `90`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18001c310`
- `0x18001e010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001c333`
- `KERNEL32!GetModuleHandleW` at `0x18001c333`
- `KERNEL32!GetProcAddress` at `0x18001c34a`
- `KERNEL32!GetProcAddress` at `0x18001c34a`

## string_xrefs

- `0x18001c32c`: `ntdll.dll`
- `0x18001c340`: `RtlDllShutdownInProgress`

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
0x18001c310  sub     rsp, 28h
0x18001c314  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001c31b  test    rax, rax
0x18001c31e  jnz     short loc_18001C361
0x18001c320  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c327  test    rax, rax
0x18001c32a  jnz     short loc_18001C340
0x18001c32c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001c333  call    cs:__imp_GetModuleHandleW
0x18001c339  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001c340  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18001c347  mov     rcx, rax; hModule
0x18001c34a  call    cs:__imp_GetProcAddress
0x18001c350  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18001c357  test    rax, rax
0x18001c35a  jnz     short loc_18001C361
0x18001c35c  add     rsp, 28h
0x18001c360  retn
0x18001c361  add     rsp, 28h
0x18001c365  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
