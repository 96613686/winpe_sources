# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000acd4`
- end: `0x18000ad54`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ada0`

## callees

- `0x18000a14c`
- `0x18000a34c`
- `0x18000a6d0`

## string_xrefs

- `0x18000aceb`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18000ad22`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x18000acd4  mov     [rsp+arg_0], rbx
0x18000acd9  mov     [rsp+arg_8], rsi
0x18000acde  push    rdi
0x18000acdf  sub     rsp, 70h
0x18000ace3  mov     rbx, [rsp+78h+arg_28]
0x18000aceb  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000acf2  mov     [rsp+78h+var_50], rbx; char *
0x18000acf7  mov     edi, edx
0x18000acf9  mov     rsi, rcx
0x18000acfc  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000ad01  movzx   edx, ax
0x18000ad04  lea     rcx, [rsp+78h+var_18]
0x18000ad09  or      edx, 80070000h
0x18000ad0f  test    eax, eax
0x18000ad11  cmovle  edx, eax
0x18000ad14  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18000ad19  mov     [rsp+78h+var_40], 0
0x18000ad22  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000ad29  mov     edx, edi
0x18000ad2b  mov     rcx, rsi
0x18000ad2e  movsd   xmm0, qword ptr [rax]
0x18000ad32  mov     eax, [rax+8]
0x18000ad35  mov     [rsp+78h+var_20], eax
0x18000ad39  lea     rax, [rsp+78h+var_28]
0x18000ad3e  mov     [rsp+78h+var_48], rax
0x18000ad43  mov     [rsp+78h+var_50], rbx
0x18000ad48  movsd   [rsp+78h+var_28], xmm0
0x18000ad4e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
