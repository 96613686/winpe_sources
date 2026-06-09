# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x14000f904`
- end: `0x14000f97b`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `119`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400148d0`

## callees

- `0x1400067e8`
- `0x140007624`
- `0x14000f8d8`
- `0x14000f904`

## string_xrefs

- `0x14000f915`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000f949`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x14000f904  push    rbx
0x14000f906  push    rbp
0x14000f907  push    rsi
0x14000f908  push    rdi
0x14000f909  sub     rsp, 78h
0x14000f90d  mov     rbp, [rsp+98h+arg_28]
0x14000f915  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000f91c  mov     [rsp+98h+var_70], rbp; char *
0x14000f921  mov     rbx, r9
0x14000f924  mov     edi, edx
0x14000f926  mov     rsi, rcx
0x14000f929  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x14000f92e  test    eax, eax
0x14000f930  jle     short loc_14000F93A
0x14000f932  movzx   eax, ax
0x14000f935  or      eax, 80070000h
0x14000f93a  mov     edx, eax
0x14000f93c  lea     rcx, [rsp+98h+var_38]
0x14000f941  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000f946  mov     r9, rbx
0x14000f949  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000f950  mov     edx, edi
0x14000f952  mov     rcx, rsi
0x14000f955  movsd   xmm0, qword ptr [rax]
0x14000f959  mov     eax, [rax+8]
0x14000f95c  mov     [rsp+98h+var_40], eax
0x14000f960  lea     rax, [rsp+98h+var_48]
0x14000f965  mov     [rsp+98h+var_68], rax
0x14000f96a  mov     [rsp+98h+var_70], rbp
0x14000f96f  movsd   [rsp+98h+var_48], xmm0
0x14000f975  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
