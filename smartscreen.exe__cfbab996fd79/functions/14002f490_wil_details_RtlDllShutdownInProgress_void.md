# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14002f490`
- end: `0x14002f4c4`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `52`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14002f490`
- `0x14002f84c`
- `0x14006a010`

## string_xrefs

- `0x14002f4a0`: `RtlDllShutdownInProgress`

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
0x14002f490  sub     rsp, 28h
0x14002f494  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14002f49b  test    rax, rax
0x14002f49e  jnz     short loc_14002F4B8
0x14002f4a0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14002f4a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14002f4ac  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14002f4b3  test    rax, rax
0x14002f4b6  jz      short loc_14002F4BE
0x14002f4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f4bd  nop
0x14002f4be  add     rsp, 28h
0x14002f4c2  retn
```
