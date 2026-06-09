# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x18001a380`
- end: `0x18001a3b6`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `54`
- prototype: `unsigned __int8 __fastcall(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001a380`
- `0x18001b67c`
- `0x18001d010`

## string_xrefs

- `0x18001a390`: `RtlDllShutdownInProgress`

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
0x18001a380  sub     rsp, 28h
0x18001a384  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x18001a38b  test    rax, rax
0x18001a38e  jnz     short loc_18001A3AD
0x18001a390  lea     rcx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x18001a397  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001a39c  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x18001a3a3  test    rax, rax
0x18001a3a6  jnz     short loc_18001A3AD
0x18001a3a8  add     rsp, 28h
0x18001a3ac  retn
0x18001a3ad  add     rsp, 28h
0x18001a3b1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
