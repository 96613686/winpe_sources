# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140003a14`
- end: `0x140003a8e`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400096a4`

## callees

- `0x140003850`
- `0x140003a14`
- `0x140005c30`
- `0x140006280`

## string_xrefs

- `0x140003a2b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140003a5c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140003a14  mov     [rsp+arg_0], rbx
0x140003a19  mov     [rsp+arg_8], rsi
0x140003a1e  push    rdi
0x140003a1f  sub     rsp, 60h
0x140003a23  mov     rsi, [rsp+68h+arg_28]
0x140003a2b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003a32  mov     [rsp+68h+var_40], rsi; char *
0x140003a37  mov     ebx, edx
0x140003a39  mov     rdi, rcx
0x140003a3c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140003a41  test    eax, eax
0x140003a43  jle     short loc_140003A4D
0x140003a45  movzx   eax, ax
0x140003a48  or      eax, 80070000h
0x140003a4d  mov     ecx, eax; this
0x140003a4f  mov     [rsp+68h+var_18], eax
0x140003a53  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003a58  mov     [rsp+68h+var_14], eax
0x140003a5c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003a63  lea     rax, [rsp+68h+var_18]
0x140003a68  mov     [rsp+68h+var_30], 0
0x140003a71  mov     [rsp+68h+var_38], rax
0x140003a76  mov     edx, ebx
0x140003a78  mov     rcx, rdi
0x140003a7b  mov     [rsp+68h+var_40], rsi
0x140003a80  mov     [rsp+68h+var_10], 0
0x140003a88  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
