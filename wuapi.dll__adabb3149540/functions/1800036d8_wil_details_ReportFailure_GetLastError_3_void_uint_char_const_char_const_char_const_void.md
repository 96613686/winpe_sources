# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800036d8`
- end: `0x180003758`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800037a4`

## callees

- `0x180002130`
- `0x180002748`
- `0x18000363c`

## string_xrefs

- `0x1800036ef`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180003726`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

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
  int v6; // edi
  int v7; // esi
  int LastErrorFail; // eax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // xmm0_8
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
                    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v13,
                    a6,
                    v15);
  v9 = (unsigned __int16)LastErrorFail | 0x80070000;
  if ( LastErrorFail <= 0 )
    v9 = (unsigned int)LastErrorFail;
  v10 = wil::details::ResultStatus::FromResult(v18, v9);
  v11 = *(_QWORD *)v10;
  v17 = *(_DWORD *)(v10 + 8);
  v16 = v11;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
    v12,
    v14,
    (__int64)a6,
    (__int64)&v16,
    0);
}

```

## disassembly

```asm
0x1800036d8  mov     [rsp+arg_0], rbx
0x1800036dd  mov     [rsp+arg_8], rsi
0x1800036e2  push    rdi
0x1800036e3  sub     rsp, 70h
0x1800036e7  mov     rbx, [rsp+78h+arg_28]
0x1800036ef  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800036f6  mov     [rsp+78h+var_50], rbx; char *
0x1800036fb  mov     edi, edx
0x1800036fd  mov     rsi, rcx
0x180003700  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180003705  movzx   edx, ax
0x180003708  lea     rcx, [rsp+78h+var_18]
0x18000370d  or      edx, 80070000h
0x180003713  test    eax, eax
0x180003715  cmovle  edx, eax
0x180003718  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18000371d  mov     [rsp+78h+var_40], 0
0x180003726  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000372d  mov     edx, edi
0x18000372f  mov     rcx, rsi
0x180003732  movsd   xmm0, qword ptr [rax]
0x180003736  mov     eax, [rax+8]
0x180003739  mov     [rsp+78h+var_20], eax
0x18000373d  lea     rax, [rsp+78h+var_28]
0x180003742  mov     [rsp+78h+var_48], rax
0x180003747  mov     [rsp+78h+var_50], rbx
0x18000374c  movsd   [rsp+78h+var_28], xmm0
0x180003752  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
