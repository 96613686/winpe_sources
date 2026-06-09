# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800037a0`
- end: `0x180003810`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005920`

## callees

- `0x1800024d8`
- `0x180003774`
- `0x1800037a0`
- `0x180004930`

## string_xrefs

- `0x1800037b7`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
0x1800037a0  mov     [rsp+arg_0], rbx
0x1800037a5  mov     [rsp+arg_8], rsi
0x1800037aa  push    rdi
0x1800037ab  sub     rsp, 70h
0x1800037af  mov     rsi, [rsp+78h+arg_28]
0x1800037b7  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800037be  mov     [rsp+78h+var_50], rsi; char *
0x1800037c3  mov     ebx, edx
0x1800037c5  mov     rdi, rcx
0x1800037c8  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800037cd  test    eax, eax
0x1800037cf  jle     short loc_1800037D9
0x1800037d1  movzx   eax, ax
0x1800037d4  or      eax, 80070000h
0x1800037d9  mov     edx, eax
0x1800037db  lea     rcx, [rsp+78h+var_18]
0x1800037e0  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800037e5  mov     edx, ebx
0x1800037e7  mov     rcx, rdi
0x1800037ea  movsd   xmm0, qword ptr [rax]
0x1800037ee  mov     eax, [rax+8]
0x1800037f1  mov     [rsp+78h+var_20], eax
0x1800037f5  lea     rax, [rsp+78h+var_28]
0x1800037fa  mov     [rsp+78h+var_48], rax
0x1800037ff  mov     [rsp+78h+var_50], rsi
0x180003804  movsd   [rsp+78h+var_28], xmm0
0x18000380a  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
