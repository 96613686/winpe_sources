# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14002e280`
- end: `0x14002e2b3`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14002e280`
- `0x14002e608`
- `0x140068010`

## string_xrefs

- `0x14002e290`: `RtlDllShutdownInProgress`

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
0x14002e280  sub     rsp, 28h
0x14002e284  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14002e28b  test    rax, rax
0x14002e28e  jnz     short loc_14002E2A8
0x14002e290  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14002e297  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14002e29c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14002e2a3  test    rax, rax
0x14002e2a6  jz      short loc_14002E2AE
0x14002e2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e2ad  nop
0x14002e2ae  add     rsp, 28h
0x14002e2b2  retn
```
