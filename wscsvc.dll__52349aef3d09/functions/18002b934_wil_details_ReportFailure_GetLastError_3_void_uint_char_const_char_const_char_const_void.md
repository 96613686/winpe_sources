# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18002b934`
- end: `0x18002b9a5`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002eaf4`

## callees

- `0x180022e1c`
- `0x180026d20`
- `0x18002b908`
- `0x18002b934`

## string_xrefs

- `0x18002b94b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002b97c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    (__int64)v14);
}

```

## disassembly

```asm
0x18002b934  mov     [rsp+arg_0], rbx
0x18002b939  mov     [rsp+arg_8], rsi
0x18002b93e  push    rdi
0x18002b93f  sub     rsp, 60h
0x18002b943  mov     rsi, [rsp+68h+arg_28]
0x18002b94b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b952  mov     [rsp+68h+var_40], rsi; char *
0x18002b957  mov     ebx, edx
0x18002b959  mov     rdi, rcx
0x18002b95c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18002b961  test    eax, eax
0x18002b963  jle     short loc_18002B96D
0x18002b965  movzx   eax, ax
0x18002b968  or      eax, 80070000h
0x18002b96d  mov     ecx, eax; this
0x18002b96f  mov     [rsp+68h+var_18], eax
0x18002b973  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002b978  mov     [rsp+68h+var_14], eax
0x18002b97c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b983  lea     rax, [rsp+68h+var_18]
0x18002b988  mov     [rsp+68h+var_10], 0
0x18002b990  mov     [rsp+68h+var_38], rax
0x18002b995  mov     edx, ebx
0x18002b997  mov     rcx, rdi
0x18002b99a  mov     [rsp+68h+var_40], rsi
0x18002b99f  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
