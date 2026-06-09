# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140006870`
- end: `0x1400068c7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140006870`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400068aa`
- `KERNEL32!GetProcAddress` at `0x1400068aa`
- `KERNEL32!GetModuleHandleW` at `0x140006893`
- `KERNEL32!GetModuleHandleW` at `0x140006893`

## string_xrefs

- `0x14000688c`: `ntdll.dll`
- `0x1400068a0`: `RtlDllShutdownInProgress`

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
0x140006870  sub     rsp, 28h
0x140006874  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000687b  test    rax, rax
0x14000687e  jnz     short loc_1400068BC
0x140006880  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006887  test    rax, rax
0x14000688a  jnz     short loc_1400068A0
0x14000688c  lea     rcx, LibFileName; "ntdll.dll"
0x140006893  call    cs:__imp_GetModuleHandleW
0x140006899  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400068a0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1400068a7  mov     rcx, rax; hModule
0x1400068aa  call    cs:__imp_GetProcAddress
0x1400068b0  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1400068b7  test    rax, rax
0x1400068ba  jz      short loc_1400068C2
0x1400068bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068c1  nop
0x1400068c2  add     rsp, 28h
0x1400068c6  retn
```
