# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000fa00`
- end: `0x18000fa36`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `54`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000fa00`
- `0x180010c54`
- `0x18001d010`

## string_xrefs

- `0x18000fa10`: `RtlDllShutdownInProgress`

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
0x18000fa00  sub     rsp, 28h
0x18000fa04  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000fa0b  test    rax, rax
0x18000fa0e  jnz     short loc_18000FA2D
0x18000fa10  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000fa17  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000fa1c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000fa23  test    rax, rax
0x18000fa26  jnz     short loc_18000FA2D
0x18000fa28  add     rsp, 28h
0x18000fa2c  retn
0x18000fa2d  add     rsp, 28h
0x18000fa31  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
