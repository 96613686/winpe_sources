# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180009800`
- end: `0x180009898`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ddf0`

## callees

- `0x180009800`
- `0x180009b7c`
- `0x18000d87c`
- `0x180010da0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009880`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009880`

## string_xrefs

- `0x180009811`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180009849`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

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
0x180009800  push    rbx
0x180009802  push    rbp
0x180009803  push    rsi
0x180009804  push    rdi
0x180009805  sub     rsp, 68h
0x180009809  mov     rbp, [rsp+88h+arg_28]
0x180009811  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180009818  mov     [rsp+88h+var_60], rbp; char *
0x18000981d  mov     edi, edx
0x18000981f  mov     rsi, rcx
0x180009822  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180009827  xor     edx, edx; int
0x180009829  mov     ebx, eax
0x18000982b  test    eax, eax
0x18000982d  jg      short loc_180009833
0x18000982f  mov     ecx, eax
0x180009831  jmp     short loc_18000983C
0x180009833  movzx   ecx, bx
0x180009836  or      ecx, 80070000h; this
0x18000983c  mov     [rsp+88h+var_38], ecx
0x180009840  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009845  mov     [rsp+88h+var_40], edx
0x180009849  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180009850  mov     [rsp+88h+var_50], rdx
0x180009855  xor     r9d, r9d
0x180009858  mov     [rsp+88h+var_34], eax
0x18000985c  mov     rcx, rsi
0x18000985f  lea     rax, [rsp+88h+var_38]
0x180009864  mov     [rsp+88h+var_30], edx
0x180009868  mov     [rsp+88h+var_58], rax
0x18000986d  mov     [rsp+88h+var_60], rbp
0x180009872  mov     [rsp+88h+var_68], rdx
0x180009877  mov     edx, edi
0x180009879  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000987e  mov     ecx, ebx; dwErrCode
0x180009880  call    cs:__imp_SetLastError
0x180009887  nop     dword ptr [rax+rax+00h]
0x18000988c  mov     eax, ebx
0x18000988e  add     rsp, 68h
0x180009892  pop     rdi
0x180009893  pop     rsi
0x180009894  pop     rbp
0x180009895  pop     rbx
0x180009896  retn
```
