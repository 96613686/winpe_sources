# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x1800051e0`
- end: `0x180005213`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `51`
- prototype: `__int64 (*__fastcall(wil::details *this))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800051e0`
- `0x180005f48`
- `0x180037010`

## string_xrefs

- `0x1800051f0`: `RtlDllShutdownInProgress`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x1800051e0  sub     rsp, 28h
0x1800051e4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x1800051eb  test    rax, rax
0x1800051ee  jnz     short loc_180005208
0x1800051f0  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x1800051f7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800051fc  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x180005203  test    rax, rax
0x180005206  jz      short loc_18000520E
0x180005208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000520d  nop
0x18000520e  add     rsp, 28h
0x180005212  retn
```
