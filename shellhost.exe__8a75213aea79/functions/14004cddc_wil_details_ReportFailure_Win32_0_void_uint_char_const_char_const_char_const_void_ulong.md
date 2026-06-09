# wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x14004cddc`
- end: `0x14004ce33`
- name: `??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14005d1c8`

## callees

- `0x1400478bc`
- `0x14004cbf0`
- `0x14004cddc`

## string_xrefs

- `0x14004ce04`: `shellcommon\internal\shell\inc\SingletonHelpers.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Win32<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  unsigned __int64 v7; // rcx
  int v8; // edx
  int v9; // r9d

  v7 = (unsigned int)a7;
  if ( a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<0,0>(
    v9,
    v8,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
    v9);
}

```

## disassembly

```asm
0x14004cddc  sub     rsp, 68h
0x14004cde0  mov     r9, rcx
0x14004cde3  mov     ecx, [rsp+68h+arg_30]
0x14004cdea  test    ecx, ecx
0x14004cdec  jle     short loc_14004CDF7
0x14004cdee  movzx   ecx, cx
0x14004cdf1  or      ecx, 80070000h; this
0x14004cdf7  mov     [rsp+68h+var_18], ecx
0x14004cdfb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14004ce00  mov     [rsp+68h+var_14], eax
0x14004ce04  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Sing"...
0x14004ce0b  lea     rax, [rsp+68h+var_18]
0x14004ce10  mov     [rsp+68h+var_10], 0
0x14004ce18  mov     [rsp+68h+var_38], rax
0x14004ce1d  mov     rcx, r9
0x14004ce20  mov     rax, [rsp+68h+arg_28]
0x14004ce28  mov     [rsp+68h+var_40], rax
0x14004ce2d  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
