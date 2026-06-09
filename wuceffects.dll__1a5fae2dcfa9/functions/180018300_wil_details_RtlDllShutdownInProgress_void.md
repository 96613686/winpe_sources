# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180018300`
- end: `0x18001833e`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `62`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180018300`
- `0x180018960`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001832a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001832a`

## string_xrefs

- `0x180018323`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE NtDllModuleHandle; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  result = GetProcAddress(NtDllModuleHandle, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x180018300  sub     rsp, 28h
0x180018304  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001830b  test    rax, rax
0x18001830e  jz      short loc_18001831B
0x180018310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018315  nop
0x180018316  add     rsp, 28h
0x18001831a  retn
0x18001831b  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180018320  mov     rcx, rax; hModule
0x180018323  lea     rdx, ProcName; "RtlDllShutdownInProgress"
0x18001832a  call    cs:__imp_GetProcAddress
0x180018330  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180018337  test    rax, rax
0x18001833a  jnz     short loc_180018310
0x18001833c  jmp     short loc_180018316
```
