# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800086f4`
- end: `0x180008764`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c478`

## callees

- `0x1800086c8`
- `0x1800086f4`
- `0x180009990`
- `0x180009e4c`

## string_xrefs

- `0x18000870b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  signed int LastErrorFail; // eax
  __int64 v9; // rax
  __int64 v10; // xmm0_8
  int v11; // r8d
  int v12; // r9d
  const char *v13; // [rsp+20h] [rbp-58h]
  int v14; // [rsp+20h] [rbp-58h]
  void *v15; // [rsp+30h] [rbp-48h]
  __int64 v16; // [rsp+50h] [rbp-28h] BYREF
  int v17; // [rsp+58h] [rbp-20h]
  _BYTE v18[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v13,
                    a6,
                    v15);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v9 = wil::details::ResultStatus::FromResult(v18, (unsigned int)LastErrorFail);
  v10 = *(_QWORD *)v9;
  v17 = *(_DWORD *)(v9 + 8);
  v16 = v10;
  wil::details::ReportFailure_Base<3,0>(v7, v6, v11, v12, v14, (__int64)a6, (__int64)&v16);
}

```

## disassembly

```asm
0x1800086f4  mov     [rsp+arg_0], rbx
0x1800086f9  mov     [rsp+arg_8], rsi
0x1800086fe  push    rdi
0x1800086ff  sub     rsp, 70h
0x180008703  mov     rsi, [rsp+78h+arg_28]
0x18000870b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008712  mov     [rsp+78h+var_50], rsi; char *
0x180008717  mov     ebx, edx
0x180008719  mov     rdi, rcx
0x18000871c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180008721  test    eax, eax
0x180008723  jle     short loc_18000872D
0x180008725  movzx   eax, ax
0x180008728  or      eax, 80070000h
0x18000872d  mov     edx, eax
0x18000872f  lea     rcx, [rsp+78h+var_18]
0x180008734  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180008739  mov     edx, ebx
0x18000873b  mov     rcx, rdi
0x18000873e  movsd   xmm0, qword ptr [rax]
0x180008742  mov     eax, [rax+8]
0x180008745  mov     [rsp+78h+var_20], eax
0x180008749  lea     rax, [rsp+78h+var_28]
0x18000874e  mov     [rsp+78h+var_48], rax
0x180008753  mov     [rsp+78h+var_50], rsi
0x180008758  movsd   [rsp+78h+var_28], xmm0
0x18000875e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
