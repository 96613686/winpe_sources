# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180038754`
- end: `0x1800387b6`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `98`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180038730`

## callees

- `0x180033a8c`
- `0x180038754`
- `0x1800387bc`

## string_xrefs

- `0x180038784`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<1,0>(v9, v8, "onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp");
  return v7;
}

```

## disassembly

```asm
0x180038754  push    rbx
0x180038756  sub     rsp, 60h
0x18003875a  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180038761  mov     r9, rcx
0x180038764  test    ebx, ebx
0x180038766  jle     short loc_180038771
0x180038768  movzx   ebx, bx
0x18003876b  or      ebx, 80070000h
0x180038771  mov     ecx, ebx; this
0x180038773  mov     [rsp+68h+var_18], ebx
0x180038777  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003877c  mov     rcx, [rsp+68h+arg_28]
0x180038784  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18003878b  mov     [rsp+68h+var_14], eax
0x18003878f  lea     rax, [rsp+68h+var_18]
0x180038794  mov     [rsp+68h+var_38], rax
0x180038799  mov     [rsp+68h+var_40], rcx
0x18003879e  mov     rcx, r9
0x1800387a1  mov     [rsp+68h+var_10], 0
0x1800387a9  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800387ae  mov     eax, ebx
0x1800387b0  add     rsp, 60h
0x1800387b4  pop     rbx
0x1800387b5  retn
```
