# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800086c0`
- end: `0x180008737`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f210`

## callees

- `0x180008694`
- `0x1800086c0`
- `0x18000adec`
- `0x18000b674`

## string_xrefs

- `0x1800086d1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180008705`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  int v7; // edi
  int v8; // esi
  signed int LastErrorFail; // eax
  __int64 v10; // rax
  __int64 v11; // xmm0_8
  const char *v12; // [rsp+20h] [rbp-78h]
  int v13; // [rsp+20h] [rbp-78h]
  void *v14; // [rsp+30h] [rbp-68h]
  __int64 v15; // [rsp+50h] [rbp-48h] BYREF
  int v16; // [rsp+58h] [rbp-40h]
  _BYTE v17[56]; // [rsp+60h] [rbp-38h] BYREF

  v6 = (int)a4;
  v7 = (int)a2;
  v8 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v12,
                    a6,
                    v14);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v10 = wil::details::ResultStatus::FromResult(v17, (unsigned int)LastErrorFail);
  v11 = *(_QWORD *)v10;
  v16 = *(_DWORD *)(v10 + 8);
  v15 = v11;
  wil::details::ReportFailure_Base<3,0>(
    v8,
    v7,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6,
    v13,
    (__int64)a6,
    (__int64)&v15);
}

```

## disassembly

```asm
0x1800086c0  push    rbx
0x1800086c2  push    rbp
0x1800086c3  push    rsi
0x1800086c4  push    rdi
0x1800086c5  sub     rsp, 78h
0x1800086c9  mov     rbp, [rsp+98h+arg_28]
0x1800086d1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800086d8  mov     [rsp+98h+var_70], rbp; char *
0x1800086dd  mov     rbx, r9
0x1800086e0  mov     edi, edx
0x1800086e2  mov     rsi, rcx
0x1800086e5  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800086ea  test    eax, eax
0x1800086ec  jle     short loc_1800086F6
0x1800086ee  movzx   eax, ax
0x1800086f1  or      eax, 80070000h
0x1800086f6  mov     edx, eax
0x1800086f8  lea     rcx, [rsp+98h+var_38]
0x1800086fd  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180008702  mov     r9, rbx
0x180008705  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000870c  mov     edx, edi
0x18000870e  mov     rcx, rsi
0x180008711  movsd   xmm0, qword ptr [rax]
0x180008715  mov     eax, [rax+8]
0x180008718  mov     [rsp+98h+var_40], eax
0x18000871c  lea     rax, [rsp+98h+var_48]
0x180008721  mov     [rsp+98h+var_68], rax
0x180008726  mov     [rsp+98h+var_70], rbp
0x18000872b  movsd   [rsp+98h+var_48], xmm0
0x180008731  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
