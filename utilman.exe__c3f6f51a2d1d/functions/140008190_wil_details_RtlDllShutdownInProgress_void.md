# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x140008190`
- end: `0x1400081c4`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `52`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140008190`
- `0x14000a118`
- `0x140029010`

## string_xrefs

- `0x1400081a0`: `RtlDllShutdownInProgress`

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
0x140008190  sub     rsp, 28h
0x140008194  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000819b  test    rax, rax
0x14000819e  jnz     short loc_1400081B8
0x1400081a0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1400081a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400081ac  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x1400081b3  test    rax, rax
0x1400081b6  jz      short loc_1400081BE
0x1400081b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400081bd  nop
0x1400081be  add     rsp, 28h
0x1400081c2  retn
```
