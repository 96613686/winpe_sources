# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x180013120`
- end: `0x180013157`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `55`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180013120`
- `0x180015550`
- `0x180034010`

## string_xrefs

- `0x180013130`: `RtlDllShutdownInProgress`

## pseudocode

```c
__int64 (*__fastcall wil::details::RtlDllShutdownInProgress(wil::details *this))(void)
{
  __int64 (*result)(void); // rax

  result = (__int64 (*)(void))`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (__int64 (*)(void))((__int64 (__fastcall *)(wil::details *))result)(this);
  result = wil_details_GetNtDllProcedureAddress("RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (__int64 (*)(void))((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x180013120  sub     rsp, 28h
0x180013124  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001312b  test    rax, rax
0x18001312e  jnz     short loc_180013148
0x180013130  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x180013137  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001313c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180013143  test    rax, rax
0x180013146  jz      short loc_180013151
0x180013148  add     rsp, 28h
0x18001314c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180013151  add     rsp, 28h
0x180013155  retn
```
