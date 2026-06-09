# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180011ef0`
- end: `0x180011f2c`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `60`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180011ef0`
- `0x180011f34`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011f0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011f0f`

## string_xrefs

- `0x180011f08`: `RtlDllShutdownInProgress`

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
0x180011ef0  sub     rsp, 28h
0x180011ef4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x180011efb  test    rax, rax
0x180011efe  jnz     short loc_180011F21
0x180011f00  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180011f05  mov     rcx, rax; hModule
0x180011f08  lea     rdx, ProcName; "RtlDllShutdownInProgress"
0x180011f0f  call    cs:__imp_GetProcAddress
0x180011f15  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180011f1c  test    rax, rax
0x180011f1f  jz      short loc_180011F27
0x180011f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f26  nop
0x180011f27  add     rsp, 28h
0x180011f2b  retn
```
