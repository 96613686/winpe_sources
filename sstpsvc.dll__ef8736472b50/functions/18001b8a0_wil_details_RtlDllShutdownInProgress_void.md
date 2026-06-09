# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18001b8a0`
- end: `0x18001b8d7`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `55`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001b8a0`
- `0x18001cb50`
- `0x18001e010`

## string_xrefs

- `0x18001b8b0`: `RtlDllShutdownInProgress`

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
0x18001b8a0  sub     rsp, 28h
0x18001b8a4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001b8ab  test    rax, rax
0x18001b8ae  jnz     short loc_18001B8CE
0x18001b8b0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18001b8b7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001b8bc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18001b8c3  test    rax, rax
0x18001b8c6  jnz     short loc_18001B8CE
0x18001b8c8  add     rsp, 28h
0x18001b8cc  retn
0x18001b8ce  add     rsp, 28h
0x18001b8d2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
