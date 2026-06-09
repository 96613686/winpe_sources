# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18003ad50`
- end: `0x18003ad86`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `54`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18003ad50`
- `0x18003c898`
- `0x180040010`

## string_xrefs

- `0x18003ad60`: `RtlDllShutdownInProgress`

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
0x18003ad50  sub     rsp, 28h
0x18003ad54  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18003ad5b  test    rax, rax
0x18003ad5e  jnz     short loc_18003AD7D
0x18003ad60  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18003ad67  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18003ad6c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18003ad73  test    rax, rax
0x18003ad76  jnz     short loc_18003AD7D
0x18003ad78  add     rsp, 28h
0x18003ad7c  retn
0x18003ad7d  add     rsp, 28h
0x18003ad81  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
