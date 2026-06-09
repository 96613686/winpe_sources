# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180006378`
- end: `0x1800063f8`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006444`

## callees

- `0x180004dd0`
- `0x1800053e8`
- `0x1800062dc`

## string_xrefs

- `0x18000638f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1800063c6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int v7; // esi
  int LastErrorFail; // eax
  __int64 v9; // rdx
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-58h]
  void *v12; // [rsp+30h] [rbp-48h]
  _BYTE v13[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v11,
                    a6,
                    v12);
  v9 = (unsigned __int16)LastErrorFail | 0x80070000;
  if ( LastErrorFail <= 0 )
    v9 = (unsigned int)LastErrorFail;
  wil::details::ResultStatus::FromResult(v13, v9);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
    v10);
}

```

## disassembly

```asm
0x180006378  mov     [rsp+arg_0], rbx
0x18000637d  mov     [rsp+arg_8], rsi
0x180006382  push    rdi
0x180006383  sub     rsp, 70h
0x180006387  mov     rbx, [rsp+78h+arg_28]
0x18000638f  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180006396  mov     [rsp+78h+var_50], rbx; char *
0x18000639b  mov     edi, edx
0x18000639d  mov     rsi, rcx
0x1800063a0  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800063a5  movzx   edx, ax
0x1800063a8  lea     rcx, [rsp+78h+var_18]
0x1800063ad  or      edx, 80070000h
0x1800063b3  test    eax, eax
0x1800063b5  cmovle  edx, eax
0x1800063b8  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800063bd  mov     [rsp+78h+var_40], 0
0x1800063c6  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800063cd  mov     edx, edi
0x1800063cf  mov     rcx, rsi
0x1800063d2  movsd   xmm0, qword ptr [rax]
0x1800063d6  mov     eax, [rax+8]
0x1800063d9  mov     [rsp+78h+var_20], eax
0x1800063dd  lea     rax, [rsp+78h+var_28]
0x1800063e2  mov     [rsp+78h+var_48], rax
0x1800063e7  mov     [rsp+78h+var_50], rbx
0x1800063ec  movsd   [rsp+78h+var_28], xmm0
0x1800063f2  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
