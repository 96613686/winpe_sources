# ?GetNextRunTime@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJPEAN@Z

- ea: `0x180049d40`
- end: `0x180049f8b`
- name: `?GetNextRunTime@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJPEAN@Z`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x1800169e0`
- `0x180022c60`
- `0x180025830`
- `0x180025b80`
- `0x18003c5c0`
- `0x180049154`
- `0x180049874`
- `0x180049d40`
- `0x18004ae50`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180049f4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180049f5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180049f4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180049f5d`
- `OLEAUT32!__imp_SysStringLen` at `0x180049d97`
- `OLEAUT32!__imp_SysStringLen` at `0x180049ea0`
- `OLEAUT32!__imp_SysStringLen` at `0x180049ec1`
- `OLEAUT32!__imp_SysStringLen` at `0x180049d97`
- `OLEAUT32!__imp_SysStringLen` at `0x180049ea0`
- `OLEAUT32!__imp_SysStringLen` at `0x180049ec1`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180049f1b`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180049f1b`

## pseudocode

```c
__int64 __fastcall _GetNextRunTime__QIMaintenanceScheduler__TaskServiceImpl__UEAAJPEAN_Z(__int64 *a1, DOUBLE *a2)
{
  __int64 v2; // rax
  bool v5; // dl
  int v6; // ebx
  UINT v7; // eax
  bool v8; // dl
  __int64 v9; // rax
  int v10; // eax
  OLECHAR *v11; // rcx
  UINT v12; // eax
  signed int LastError; // eax
  BSTR pbstr; // [rsp+20h] [rbp-59h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-51h] BYREF
  __int64 v17; // [rsp+30h] [rbp-49h] BYREF
  int v18; // [rsp+38h] [rbp-41h]
  __int16 v19; // [rsp+3Ch] [rbp-3Dh]
  __int128 v20; // [rsp+40h] [rbp-39h] BYREF
  __int128 v21; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v22[16]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v23[16]; // [rsp+70h] [rbp-9h] BYREF
  struct _SYSTEMTIME v24; // [rsp+80h] [rbp+7h] BYREF
  struct _SYSTEMTIME v25; // [rsp+90h] [rbp+17h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp+27h] BYREF

  v2 = *a1;
  pbstr = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v2 + 64))(a1, &pbstr);
  if ( v6 >= 0 )
  {
    TSTime::TSTime((TSTime *)v22, v5);
    v7 = SysStringLen(pbstr);
    v6 = TSParser::ParseDateTime(pbstr, v7, (struct TSTime *)v22);
    if ( v6 >= 0 )
    {
      TSTime::ToLocal(v22, &v21);
      TSTime::TSTime((TSTime *)&v20, v8);
      TSTime::ToLocal(&v20, v23);
      TSTime::ToSYSTEMTIME((TSTime *)&v21, &v24);
      TSTime::ToSYSTEMTIME((TSTime *)v23, &v25);
      v24.wYear = v25.wYear;
      v24.wMonth = v25.wMonth;
      v24.wDay = v25.wDay;
      LOBYTE(v20) = 1;
      TSTime::FromSYSTEMTIME((TSTime *)&v20, &v24);
      v21 = v20;
      while ( 1 )
      {
        TSTime::EqualizeLocality(&v21, &v20, v23);
        if ( *((_QWORD *)&v21 + 1) > *((_QWORD *)&v20 + 1) )
          break;
        if ( *((_QWORD *)&v21 + 1) <= 0xFFFFFF36D5963FFFuLL )
          *((_QWORD *)&v21 + 1) += 864000000000LL;
        else
          *((_QWORD *)&v21 + 1) = -1;
      }
      v9 = *a1;
      bstrString = 0;
      v10 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v9 + 96))(a1, &bstrString);
      v11 = bstrString;
      v6 = v10;
      if ( v10 < 0 )
        goto LABEL_19;
      if ( bstrString && SysStringLen(bstrString) )
      {
        v17 = 0;
        v18 = 0;
        v19 = 0;
        v12 = SysStringLen(bstrString);
        v6 = TSParser::ParseTimePeriod(bstrString, v12, (struct TSTimePeriod *)&v17);
        if ( v6 < 0 )
        {
LABEL_18:
          v11 = bstrString;
LABEL_19:
          SysFreeString(v11);
          goto LABEL_20;
        }
        DWORD2(v20) = v18;
        WORD6(v20) = v19;
        *(_QWORD *)&v20 = v17;
        TSTime::operator+=((TSTime *)&v21);
      }
      TSTime::ToSYSTEMTIME((TSTime *)&v21, &SystemTime);
      if ( SystemTimeToVariantTime(&SystemTime, a2) )
      {
        v6 = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v6 = LastError;
      }
      goto LABEL_18;
    }
  }
LABEL_20:
  SysFreeString(pbstr);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180049d40  mov     [rsp-8+arg_10], rbx
0x180049d45  push    rbp
0x180049d46  push    rsi
0x180049d47  push    rdi
0x180049d48  lea     rbp, [rsp-47h]
0x180049d4d  sub     rsp, 0C0h
0x180049d54  mov     rax, cs:__security_cookie
0x180049d5b  xor     rax, rsp
0x180049d5e  mov     [rbp+57h+var_20], rax
0x180049d62  mov     rax, [rcx]
0x180049d65  mov     rsi, rdx
0x180049d68  lea     rdx, [rbp+57h+pbstr]
0x180049d6c  mov     [rbp+57h+pbstr], 0
0x180049d74  mov     rdi, rcx
0x180049d77  mov     rax, [rax+40h]
0x180049d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d80  mov     ebx, eax
0x180049d82  test    eax, eax
0x180049d84  js      loc_180049F59
0x180049d8a  lea     rcx, [rbp+57h+var_70]; this
0x180049d8e  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x180049d93  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180049d97  call    cs:__imp_SysStringLen
0x180049d9e  nop     dword ptr [rax+rax+00h]
0x180049da3  mov     rcx, [rbp+57h+pbstr]; unsigned __int16 *
0x180049da7  lea     r8, [rbp+57h+var_70]; struct TSTime *
0x180049dab  mov     edx, eax; unsigned __int64
0x180049dad  call    ?ParseDateTime@TSParser@@SAJPEBG_KAEAVTSTime@@@Z; TSParser::ParseDateTime(ushort const *,unsigned __int64,TSTime &)
0x180049db2  mov     ebx, eax
0x180049db4  test    eax, eax
0x180049db6  js      loc_180049F59
0x180049dbc  lea     rdx, [rbp+57h+var_80]
0x180049dc0  lea     rcx, [rbp+57h+var_70]
0x180049dc4  call    ?ToLocal@TSTime@@QEBA?AV1@XZ; TSTime::ToLocal(void)
0x180049dc9  lea     rcx, [rbp+57h+var_90]; this
0x180049dcd  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x180049dd2  lea     rdx, [rbp+57h+var_60]
0x180049dd6  lea     rcx, [rbp+57h+var_90]
0x180049dda  call    ?ToLocal@TSTime@@QEBA?AV1@XZ; TSTime::ToLocal(void)
0x180049ddf  lea     rdx, [rbp+57h+var_50]; retstr
0x180049de3  lea     rcx, [rbp+57h+var_80]; this
0x180049de7  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x180049dec  lea     rdx, [rbp+57h+var_40]; retstr
0x180049df0  lea     rcx, [rbp+57h+var_60]; this
0x180049df4  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x180049df9  movzx   eax, [rbp+57h+var_40.wYear]
0x180049dfd  lea     rdx, [rbp+57h+var_50]; struct _SYSTEMTIME *
0x180049e01  mov     [rbp+57h+var_50.wYear], ax
0x180049e05  lea     rcx, [rbp+57h+var_90]; this
0x180049e09  movzx   eax, [rbp+57h+var_40.wMonth]
0x180049e0d  mov     [rbp+57h+var_50.wMonth], ax
0x180049e11  movzx   eax, [rbp+57h+var_40.wDay]
0x180049e15  mov     [rbp+57h+var_50.wDay], ax
0x180049e19  mov     byte ptr [rbp+57h+var_90], 1
0x180049e1d  call    ?FromSYSTEMTIME@TSTime@@QEAAXAEBU_SYSTEMTIME@@@Z; TSTime::FromSYSTEMTIME(_SYSTEMTIME const &)
0x180049e22  movaps  xmm0, [rbp+57h+var_90]
0x180049e26  movdqa  [rbp+57h+var_80], xmm0
0x180049e2b  lea     r8, [rbp+57h+var_60]
0x180049e2f  lea     rdx, [rbp+57h+var_90]
0x180049e33  lea     rcx, [rbp+57h+var_80]
0x180049e37  call    ?EqualizeLocality@TSTime@@AEBA?AV1@AEBV1@@Z; TSTime::EqualizeLocality(TSTime const &)
0x180049e3c  mov     rax, qword ptr [rbp+57h+var_80+8]
0x180049e40  cmp     rax, qword ptr [rbp+57h+var_90+8]
0x180049e44  ja      short loc_180049E72
0x180049e46  mov     rcx, 0FFFFFF36D5963FFFh
0x180049e50  cmp     rax, rcx
0x180049e53  jbe     short loc_180049E5F
0x180049e55  mov     qword ptr [rbp+57h+var_80+8], 0FFFFFFFFFFFFFFFFh
0x180049e5d  jmp     short loc_180049E2B
0x180049e5f  mov     rcx, 0C92A69C000h
0x180049e69  add     rax, rcx
0x180049e6c  mov     qword ptr [rbp+57h+var_80+8], rax
0x180049e70  jmp     short loc_180049E2B
0x180049e72  mov     rax, [rdi]
0x180049e75  lea     rdx, [rbp+57h+bstrString]
0x180049e79  mov     rcx, rdi
0x180049e7c  mov     [rbp+57h+bstrString], 0
0x180049e84  mov     rax, [rax+60h]
0x180049e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e8d  mov     rcx, [rbp+57h+bstrString]; pbstr
0x180049e91  mov     ebx, eax
0x180049e93  test    eax, eax
0x180049e95  js      loc_180049F4D
0x180049e9b  test    rcx, rcx
0x180049e9e  jz      short loc_180049F07
0x180049ea0  call    cs:__imp_SysStringLen
0x180049ea7  nop     dword ptr [rax+rax+00h]
0x180049eac  test    eax, eax
0x180049eae  jz      short loc_180049F07
0x180049eb0  mov     rcx, [rbp+57h+bstrString]; pbstr
0x180049eb4  xor     eax, eax
0x180049eb6  mov     [rbp+57h+var_A0], rax
0x180049eba  mov     [rbp+57h+var_98], eax
0x180049ebd  mov     [rbp+57h+var_94], ax
0x180049ec1  call    cs:__imp_SysStringLen
0x180049ec8  nop     dword ptr [rax+rax+00h]
0x180049ecd  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x180049ed1  lea     r8, [rbp+57h+var_A0]; struct TSTimePeriod *
0x180049ed5  mov     edx, eax; unsigned __int64
0x180049ed7  call    ?ParseTimePeriod@TSParser@@SAJPEBG_KAEAVTSTimePeriod@@@Z; TSParser::ParseTimePeriod(ushort const *,unsigned __int64,TSTimePeriod &)
0x180049edc  mov     ebx, eax
0x180049ede  test    eax, eax
0x180049ee0  js      short loc_180049F49
0x180049ee2  mov     eax, [rbp+57h+var_98]
0x180049ee5  lea     rdx, [rbp+57h+var_90]
0x180049ee9  movsd   xmm0, [rbp+57h+var_A0]
0x180049eee  lea     rcx, [rbp+57h+var_80]; this
0x180049ef2  mov     dword ptr [rbp+57h+var_90+8], eax
0x180049ef5  movzx   eax, [rbp+57h+var_94]
0x180049ef9  mov     word ptr [rbp+57h+var_90+0Ch], ax
0x180049efd  movsd   qword ptr [rbp+57h+var_90], xmm0
0x180049f02  call    ??YTSTime@@QEAAAEBV0@VTSTimePeriod@@@Z; TSTime::operator+=(TSTimePeriod)
0x180049f07  lea     rdx, [rbp+57h+SystemTime]; retstr
0x180049f0b  lea     rcx, [rbp+57h+var_80]; this
0x180049f0f  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x180049f14  mov     rdx, rsi; pvtime
0x180049f17  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180049f1b  call    cs:__imp_SystemTimeToVariantTime
0x180049f22  nop     dword ptr [rax+rax+00h]
0x180049f27  test    eax, eax
0x180049f29  jnz     short loc_180049F47
0x180049f2b  call    cs:__imp_GetLastError
0x180049f32  nop     dword ptr [rax+rax+00h]
0x180049f37  test    eax, eax
0x180049f39  jle     short loc_180049F43
0x180049f3b  movzx   eax, ax
0x180049f3e  or      eax, 80070000h
0x180049f43  mov     ebx, eax
0x180049f45  jmp     short loc_180049F49
0x180049f47  xor     ebx, ebx
0x180049f49  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180049f4d  call    cs:__imp_SysFreeString
0x180049f54  nop     dword ptr [rax+rax+00h]
0x180049f59  mov     rcx, [rbp+57h+pbstr]; bstrString
0x180049f5d  call    cs:__imp_SysFreeString
0x180049f64  nop     dword ptr [rax+rax+00h]
0x180049f69  mov     eax, ebx
0x180049f6b  mov     rcx, [rbp+57h+var_20]
0x180049f6f  xor     rcx, rsp; StackCookie
0x180049f72  call    __security_check_cookie
0x180049f77  mov     rbx, [rsp+0D0h+arg_10]
0x180049f7f  add     rsp, 0C0h
0x180049f86  pop     rdi
0x180049f87  pop     rsi
0x180049f88  pop     rbp
0x180049f89  retn
```
