# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180021f9c`
- end: `0x180022014`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `120`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180023eb4`

## callees

- `0x180006218`
- `0x180006760`
- `0x180021f70`
- `0x180021f9c`

## string_xrefs

- `0x180021fae`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180021fdf`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  signed int LastErrorFail; // eax
  __int64 v8; // rax
  __int64 v9; // xmm0_8
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-58h]
  int v12; // [rsp+20h] [rbp-58h]
  void *v13; // [rsp+30h] [rbp-48h]
  __int64 v14; // [rsp+50h] [rbp-28h] BYREF
  int v15; // [rsp+58h] [rbp-20h]
  _BYTE v16[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x1CC8,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v8 = wil::details::ResultStatus::FromResult(v16, (unsigned int)LastErrorFail);
  v9 = *(_QWORD *)v8;
  v15 = *(_DWORD *)(v8 + 8);
  v14 = v9;
  wil::details::ReportFailure_Base<0,0>(
    v6,
    7368,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
    v10,
    v12,
    (__int64)a6,
    (__int64)&v14);
}

```

## disassembly

```asm
0x180021f9c  mov     [rsp+arg_0], rbx
0x180021fa1  push    rdi
0x180021fa2  sub     rsp, 70h
0x180021fa6  mov     rdi, [rsp+78h+arg_28]
0x180021fae  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021fb5  mov     edx, 1CC8h; void *
0x180021fba  mov     [rsp+78h+var_50], rdi; char *
0x180021fbf  mov     rbx, rcx
0x180021fc2  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180021fc7  test    eax, eax
0x180021fc9  jle     short loc_180021FD3
0x180021fcb  movzx   eax, ax
0x180021fce  or      eax, 80070000h
0x180021fd3  mov     edx, eax
0x180021fd5  lea     rcx, [rsp+78h+var_18]
0x180021fda  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180021fdf  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021fe6  mov     edx, 1CC8h
0x180021feb  mov     rcx, rbx
0x180021fee  movsd   xmm0, qword ptr [rax]
0x180021ff2  mov     eax, [rax+8]
0x180021ff5  mov     [rsp+78h+var_20], eax
0x180021ff9  lea     rax, [rsp+78h+var_28]
0x180021ffe  mov     [rsp+78h+var_48], rax
0x180022003  mov     [rsp+78h+var_50], rdi
0x180022008  movsd   [rsp+78h+var_28], xmm0
0x18002200e  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
