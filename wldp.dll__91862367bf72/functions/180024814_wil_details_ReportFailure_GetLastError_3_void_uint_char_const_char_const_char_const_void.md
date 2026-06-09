# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180024814`
- end: `0x18002488e`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800267dc`

## callees

- `0x18001b884`
- `0x18001fad4`
- `0x1800247dc`
- `0x180024814`

## string_xrefs

- `0x18002482b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002485c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // edx
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-48h]
  int v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]
  _DWORD v14[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v14[0] = LastErrorFail;
  v14[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  v14[2] = 0;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v10,
    v12,
    (__int64)a6,
    (__int64)v14,
    0);
}

```

## disassembly

```asm
0x180024814  mov     [rsp+arg_0], rbx
0x180024819  mov     [rsp+arg_8], rsi
0x18002481e  push    rdi
0x18002481f  sub     rsp, 60h
0x180024823  mov     rsi, [rsp+68h+arg_28]
0x18002482b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024832  mov     [rsp+68h+var_40], rsi; char *
0x180024837  mov     ebx, edx
0x180024839  mov     rdi, rcx
0x18002483c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180024841  test    eax, eax
0x180024843  jle     short loc_18002484D
0x180024845  movzx   eax, ax
0x180024848  or      eax, 80070000h
0x18002484d  mov     ecx, eax; this
0x18002484f  mov     [rsp+68h+var_18], eax
0x180024853  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180024858  mov     [rsp+68h+var_14], eax
0x18002485c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024863  lea     rax, [rsp+68h+var_18]
0x180024868  mov     [rsp+68h+var_30], 0
0x180024871  mov     [rsp+68h+var_38], rax
0x180024876  mov     edx, ebx
0x180024878  mov     rcx, rdi
0x18002487b  mov     [rsp+68h+var_40], rsi
0x180024880  mov     [rsp+68h+var_10], 0
0x180024888  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
