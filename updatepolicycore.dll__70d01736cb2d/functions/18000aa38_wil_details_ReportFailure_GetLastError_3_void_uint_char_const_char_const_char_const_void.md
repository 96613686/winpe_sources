# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000aa38`
- end: `0x18000aab8`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ab04`

## callees

- `0x180009490`
- `0x180009aa8`
- `0x18000a99c`

## string_xrefs

- `0x18000aa4f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18000aa86`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

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
0x18000aa38  mov     [rsp+arg_0], rbx
0x18000aa3d  mov     [rsp+arg_8], rsi
0x18000aa42  push    rdi
0x18000aa43  sub     rsp, 70h
0x18000aa47  mov     rbx, [rsp+78h+arg_28]
0x18000aa4f  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000aa56  mov     [rsp+78h+var_50], rbx; char *
0x18000aa5b  mov     edi, edx
0x18000aa5d  mov     rsi, rcx
0x18000aa60  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000aa65  movzx   edx, ax
0x18000aa68  lea     rcx, [rsp+78h+var_18]
0x18000aa6d  or      edx, 80070000h
0x18000aa73  test    eax, eax
0x18000aa75  cmovle  edx, eax
0x18000aa78  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18000aa7d  mov     [rsp+78h+var_40], 0
0x18000aa86  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000aa8d  mov     edx, edi
0x18000aa8f  mov     rcx, rsi
0x18000aa92  movsd   xmm0, qword ptr [rax]
0x18000aa96  mov     eax, [rax+8]
0x18000aa99  mov     [rsp+78h+var_20], eax
0x18000aa9d  lea     rax, [rsp+78h+var_28]
0x18000aaa2  mov     [rsp+78h+var_48], rax
0x18000aaa7  mov     [rsp+78h+var_50], rbx
0x18000aaac  movsd   [rsp+78h+var_28], xmm0
0x18000aab2  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
