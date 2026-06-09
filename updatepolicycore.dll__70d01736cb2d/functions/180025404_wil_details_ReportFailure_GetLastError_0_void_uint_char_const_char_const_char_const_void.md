# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180025404`
- end: `0x180025470`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `108`
- prototype: `void __fastcall __noreturn(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025478`

## callees

- `0x180009490`
- `0x180009aa8`
- `0x1800253d8`

## string_xrefs

- `0x180025416`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int LastErrorFail; // eax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // xmm0_8
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  const char *v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+20h] [rbp-58h]
  void *v16; // [rsp+30h] [rbp-48h]
  __int64 v17; // [rsp+50h] [rbp-28h] BYREF
  int v18; // [rsp+58h] [rbp-20h]
  _BYTE v19[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x1CA0,
                    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\"
                                  "wil\\result_macros.h",
                    a4,
                    v14,
                    a6,
                    v16);
  v8 = (unsigned __int16)LastErrorFail | 0x80070000;
  if ( LastErrorFail <= 0 )
    v8 = (unsigned int)LastErrorFail;
  v9 = wil::details::ResultStatus::FromResult(v19, v8);
  v10 = *(_QWORD *)v9;
  v18 = *(_DWORD *)(v9 + 8);
  v17 = v10;
  wil::details::ReportFailure_Base<0,0>(v6, v11, v12, v13, v15, (__int64)a6, (__int64)&v17);
}

```

## disassembly

```asm
0x180025404  mov     [rsp+arg_0], rbx
0x180025409  push    rdi
0x18002540a  sub     rsp, 70h
0x18002540e  mov     rbx, [rsp+78h+arg_28]
0x180025416  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18002541d  mov     edx, 1CA0h; void *
0x180025422  mov     [rsp+78h+var_50], rbx; char *
0x180025427  mov     rdi, rcx
0x18002542a  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18002542f  movzx   edx, ax
0x180025432  lea     rcx, [rsp+78h+var_18]
0x180025437  or      edx, 80070000h
0x18002543d  test    eax, eax
0x18002543f  cmovle  edx, eax
0x180025442  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180025447  mov     rcx, rdi
0x18002544a  movsd   xmm0, qword ptr [rax]
0x18002544e  mov     eax, [rax+8]
0x180025451  mov     [rsp+78h+var_20], eax
0x180025455  lea     rax, [rsp+78h+var_28]
0x18002545a  mov     [rsp+78h+var_48], rax
0x18002545f  mov     [rsp+78h+var_50], rbx
0x180025464  movsd   [rsp+78h+var_28], xmm0
0x18002546a  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
