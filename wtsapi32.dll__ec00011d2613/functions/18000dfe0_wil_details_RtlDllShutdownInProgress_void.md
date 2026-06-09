# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18000dfe0`
- end: `0x18000e016`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `54`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000dfe0`
- `0x18000ec48`
- `0x180016010`

## string_xrefs

- `0x18000dff0`: `RtlDllShutdownInProgress`

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
0x18000dfe0  sub     rsp, 28h
0x18000dfe4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18000dfeb  test    rax, rax
0x18000dfee  jnz     short loc_18000E00D
0x18000dff0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18000dff7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000dffc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18000e003  test    rax, rax
0x18000e006  jnz     short loc_18000E00D
0x18000e008  add     rsp, 28h
0x18000e00c  retn
0x18000e00d  add     rsp, 28h
0x18000e011  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
