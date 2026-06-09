# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140003dec`
- end: `0x140003e6c`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003e94`

## callees

- `0x140002a30`
- `0x140003220`
- `0x140003d50`

## string_xrefs

- `0x140003e03`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140003e3a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

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
0x140003dec  mov     [rsp+arg_0], rbx
0x140003df1  mov     [rsp+arg_8], rsi
0x140003df6  push    rdi
0x140003df7  sub     rsp, 70h
0x140003dfb  mov     rbx, [rsp+78h+arg_28]
0x140003e03  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140003e0a  mov     [rsp+78h+var_50], rbx; char *
0x140003e0f  mov     edi, edx
0x140003e11  mov     rsi, rcx
0x140003e14  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140003e19  movzx   edx, ax
0x140003e1c  lea     rcx, [rsp+78h+var_18]
0x140003e21  or      edx, 80070000h
0x140003e27  test    eax, eax
0x140003e29  cmovle  edx, eax
0x140003e2c  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x140003e31  mov     [rsp+78h+var_40], 0
0x140003e3a  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140003e41  mov     edx, edi
0x140003e43  mov     rcx, rsi
0x140003e46  movsd   xmm0, qword ptr [rax]
0x140003e4a  mov     eax, [rax+8]
0x140003e4d  mov     [rsp+78h+var_20], eax
0x140003e51  lea     rax, [rsp+78h+var_28]
0x140003e56  mov     [rsp+78h+var_48], rax
0x140003e5b  mov     [rsp+78h+var_50], rbx
0x140003e60  movsd   [rsp+78h+var_28], xmm0
0x140003e66  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
