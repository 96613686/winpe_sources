# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180008f48`
- end: `0x180008fd9`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `145`
- prototype: `__int64 __fastcall(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d178`

## callees

- `0x180008f48`
- `0x1800092b4`
- `0x18000cb3c`
- `0x18000ff48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fc8`

## string_xrefs

- `0x180008f59`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180008f91`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
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
  DWORD v9; // ebx
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  const char *v13; // [rsp+20h] [rbp-68h]
  void *v14; // [rsp+30h] [rbp-58h]
  _DWORD v15[14]; // [rsp+50h] [rbp-38h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                    a4,
                    v13,
                    a6,
                    v14);
  v9 = LastErrorFail;
  if ( LastErrorFail > 0 )
    v10 = (unsigned __int16)LastErrorFail | 0x80070000;
  else
    v10 = (unsigned int)LastErrorFail;
  v15[0] = v10;
  v15[1] = wil::details::HrToNtStatus((wil::details *)v10, 0);
  v15[2] = v11;
  wil::details::ReportFailure_Base<2,0>(
    v7,
    v6,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    0,
    v11,
    (__int64)a6,
    (__int64)v15,
    v11);
  SetLastError(v9);
  return v9;
}

```

## disassembly

```asm
0x180008f48  push    rbx
0x180008f4a  push    rbp
0x180008f4b  push    rsi
0x180008f4c  push    rdi
0x180008f4d  sub     rsp, 68h
0x180008f51  mov     rbp, [rsp+88h+arg_28]
0x180008f59  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180008f60  mov     [rsp+88h+var_60], rbp; char *
0x180008f65  mov     edi, edx
0x180008f67  mov     rsi, rcx
0x180008f6a  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180008f6f  xor     edx, edx; int
0x180008f71  mov     ebx, eax
0x180008f73  test    eax, eax
0x180008f75  jg      short loc_180008F7B
0x180008f77  mov     ecx, eax
0x180008f79  jmp     short loc_180008F84
0x180008f7b  movzx   ecx, bx
0x180008f7e  or      ecx, 80070000h; this
0x180008f84  mov     [rsp+88h+var_38], ecx
0x180008f88  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008f8d  mov     [rsp+88h+var_40], edx
0x180008f91  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180008f98  mov     [rsp+88h+var_50], rdx
0x180008f9d  xor     r9d, r9d
0x180008fa0  mov     [rsp+88h+var_34], eax
0x180008fa4  mov     rcx, rsi
0x180008fa7  lea     rax, [rsp+88h+var_38]
0x180008fac  mov     [rsp+88h+var_30], edx
0x180008fb0  mov     [rsp+88h+var_58], rax
0x180008fb5  mov     [rsp+88h+var_60], rbp
0x180008fba  mov     [rsp+88h+var_68], rdx
0x180008fbf  mov     edx, edi
0x180008fc1  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180008fc6  mov     ecx, ebx; dwErrCode
0x180008fc8  call    cs:__imp_SetLastError
0x180008fce  mov     eax, ebx
0x180008fd0  add     rsp, 68h
0x180008fd4  pop     rdi
0x180008fd5  pop     rsi
0x180008fd6  pop     rbp
0x180008fd7  pop     rbx
0x180008fd8  retn
```
