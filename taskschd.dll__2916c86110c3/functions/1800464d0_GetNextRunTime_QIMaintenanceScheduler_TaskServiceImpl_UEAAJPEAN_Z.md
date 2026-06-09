# ?GetNextRunTime@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJPEAN@Z

- ea: `0x1800464d0`
- end: `0x1800466f0`
- name: `?GetNextRunTime@?QIMaintenanceScheduler@@TaskServiceImpl@@UEAAJPEAN@Z`
- size: `544`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x1800158b0`
- `0x180021240`
- `0x180023ac0`
- `0x180023dcc`
- `0x1800394b4`
- `0x1800459e8`
- `0x18004607c`
- `0x1800464d0`
- `0x180047458`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800466a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800466a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800466bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800466c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800466bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800466c9`
- `OLEAUT32!__imp_SysStringLen` at `0x180046527`
- `OLEAUT32!__imp_SysStringLen` at `0x18004662a`
- `OLEAUT32!__imp_SysStringLen` at `0x180046645`
- `OLEAUT32!__imp_SysStringLen` at `0x180046527`
- `OLEAUT32!__imp_SysStringLen` at `0x18004662a`
- `OLEAUT32!__imp_SysStringLen` at `0x180046645`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180046699`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180046699`

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
0x1800464d0  mov     [rsp-8+arg_10], rbx
0x1800464d5  push    rbp
0x1800464d6  push    rsi
0x1800464d7  push    rdi
0x1800464d8  lea     rbp, [rsp-47h]
0x1800464dd  sub     rsp, 0C0h
0x1800464e4  mov     rax, cs:__security_cookie
0x1800464eb  xor     rax, rsp
0x1800464ee  mov     [rbp+57h+var_20], rax
0x1800464f2  mov     rax, [rcx]
0x1800464f5  mov     rsi, rdx
0x1800464f8  lea     rdx, [rbp+57h+pbstr]
0x1800464fc  mov     [rbp+57h+pbstr], 0
0x180046504  mov     rdi, rcx
0x180046507  mov     rax, [rax+40h]
0x18004650b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046510  mov     ebx, eax
0x180046512  test    eax, eax
0x180046514  js      loc_1800466C5
0x18004651a  lea     rcx, [rbp+57h+var_70]; this
0x18004651e  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x180046523  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180046527  call    cs:__imp_SysStringLen
0x18004652d  mov     rcx, [rbp+57h+pbstr]; unsigned __int16 *
0x180046531  lea     r8, [rbp+57h+var_70]; struct TSTime *
0x180046535  mov     edx, eax; unsigned __int64
0x180046537  call    ?ParseDateTime@TSParser@@SAJPEBG_KAEAVTSTime@@@Z; TSParser::ParseDateTime(ushort const *,unsigned __int64,TSTime &)
0x18004653c  mov     ebx, eax
0x18004653e  test    eax, eax
0x180046540  js      loc_1800466C5
0x180046546  lea     rdx, [rbp+57h+var_80]
0x18004654a  lea     rcx, [rbp+57h+var_70]
0x18004654e  call    ?ToLocal@TSTime@@QEBA?AV1@XZ; TSTime::ToLocal(void)
0x180046553  lea     rcx, [rbp+57h+var_90]; this
0x180046557  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x18004655c  lea     rdx, [rbp+57h+var_60]
0x180046560  lea     rcx, [rbp+57h+var_90]
0x180046564  call    ?ToLocal@TSTime@@QEBA?AV1@XZ; TSTime::ToLocal(void)
0x180046569  lea     rdx, [rbp+57h+var_50]; retstr
0x18004656d  lea     rcx, [rbp+57h+var_80]; this
0x180046571  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x180046576  lea     rdx, [rbp+57h+var_40]; retstr
0x18004657a  lea     rcx, [rbp+57h+var_60]; this
0x18004657e  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x180046583  movzx   eax, [rbp+57h+var_40.wYear]
0x180046587  lea     rdx, [rbp+57h+var_50]; struct _SYSTEMTIME *
0x18004658b  mov     [rbp+57h+var_50.wYear], ax
0x18004658f  lea     rcx, [rbp+57h+var_90]; this
0x180046593  movzx   eax, [rbp+57h+var_40.wMonth]
0x180046597  mov     [rbp+57h+var_50.wMonth], ax
0x18004659b  movzx   eax, [rbp+57h+var_40.wDay]
0x18004659f  mov     [rbp+57h+var_50.wDay], ax
0x1800465a3  mov     byte ptr [rbp+57h+var_90], 1
0x1800465a7  call    ?FromSYSTEMTIME@TSTime@@QEAAXAEBU_SYSTEMTIME@@@Z; TSTime::FromSYSTEMTIME(_SYSTEMTIME const &)
0x1800465ac  movaps  xmm0, [rbp+57h+var_90]
0x1800465b0  movdqa  [rbp+57h+var_80], xmm0
0x1800465b5  lea     r8, [rbp+57h+var_60]
0x1800465b9  lea     rdx, [rbp+57h+var_90]
0x1800465bd  lea     rcx, [rbp+57h+var_80]
0x1800465c1  call    ?EqualizeLocality@TSTime@@AEBA?AV1@AEBV1@@Z; TSTime::EqualizeLocality(TSTime const &)
0x1800465c6  mov     rax, qword ptr [rbp+57h+var_80+8]
0x1800465ca  cmp     rax, qword ptr [rbp+57h+var_90+8]
0x1800465ce  ja      short loc_1800465FC
0x1800465d0  mov     rcx, 0FFFFFF36D5963FFFh
0x1800465da  cmp     rax, rcx
0x1800465dd  jbe     short loc_1800465E9
0x1800465df  mov     qword ptr [rbp+57h+var_80+8], 0FFFFFFFFFFFFFFFFh
0x1800465e7  jmp     short loc_1800465B5
0x1800465e9  mov     rcx, 0C92A69C000h
0x1800465f3  add     rax, rcx
0x1800465f6  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800465fa  jmp     short loc_1800465B5
0x1800465fc  mov     rax, [rdi]
0x1800465ff  lea     rdx, [rbp+57h+bstrString]
0x180046603  mov     rcx, rdi
0x180046606  mov     [rbp+57h+bstrString], 0
0x18004660e  mov     rax, [rax+60h]
0x180046612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046617  mov     rcx, [rbp+57h+bstrString]; pbstr
0x18004661b  mov     ebx, eax
0x18004661d  test    eax, eax
0x18004661f  js      loc_1800466BF
0x180046625  test    rcx, rcx
0x180046628  jz      short loc_180046685
0x18004662a  call    cs:__imp_SysStringLen
0x180046630  test    eax, eax
0x180046632  jz      short loc_180046685
0x180046634  mov     rcx, [rbp+57h+bstrString]; pbstr
0x180046638  xor     eax, eax
0x18004663a  mov     [rbp+57h+var_A0], rax
0x18004663e  mov     [rbp+57h+var_98], eax
0x180046641  mov     [rbp+57h+var_94], ax
0x180046645  call    cs:__imp_SysStringLen
0x18004664b  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x18004664f  lea     r8, [rbp+57h+var_A0]; struct TSTimePeriod *
0x180046653  mov     edx, eax; unsigned __int64
0x180046655  call    ?ParseTimePeriod@TSParser@@SAJPEBG_KAEAVTSTimePeriod@@@Z; TSParser::ParseTimePeriod(ushort const *,unsigned __int64,TSTimePeriod &)
0x18004665a  mov     ebx, eax
0x18004665c  test    eax, eax
0x18004665e  js      short loc_1800466BB
0x180046660  mov     eax, [rbp+57h+var_98]
0x180046663  lea     rdx, [rbp+57h+var_90]
0x180046667  movsd   xmm0, [rbp+57h+var_A0]
0x18004666c  lea     rcx, [rbp+57h+var_80]; this
0x180046670  mov     dword ptr [rbp+57h+var_90+8], eax
0x180046673  movzx   eax, [rbp+57h+var_94]
0x180046677  mov     word ptr [rbp+57h+var_90+0Ch], ax
0x18004667b  movsd   qword ptr [rbp+57h+var_90], xmm0
0x180046680  call    ??YTSTime@@QEAAAEBV0@VTSTimePeriod@@@Z; TSTime::operator+=(TSTimePeriod)
0x180046685  lea     rdx, [rbp+57h+SystemTime]; retstr
0x180046689  lea     rcx, [rbp+57h+var_80]; this
0x18004668d  call    ?ToSYSTEMTIME@TSTime@@QEBA?AU_SYSTEMTIME@@XZ; TSTime::ToSYSTEMTIME(void)
0x180046692  mov     rdx, rsi; pvtime
0x180046695  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180046699  call    cs:__imp_SystemTimeToVariantTime
0x18004669f  test    eax, eax
0x1800466a1  jnz     short loc_1800466B9
0x1800466a3  call    cs:__imp_GetLastError
0x1800466a9  test    eax, eax
0x1800466ab  jle     short loc_1800466B5
0x1800466ad  movzx   eax, ax
0x1800466b0  or      eax, 80070000h
0x1800466b5  mov     ebx, eax
0x1800466b7  jmp     short loc_1800466BB
0x1800466b9  xor     ebx, ebx
0x1800466bb  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800466bf  call    cs:__imp_SysFreeString
0x1800466c5  mov     rcx, [rbp+57h+pbstr]; bstrString
0x1800466c9  call    cs:__imp_SysFreeString
0x1800466cf  mov     eax, ebx
0x1800466d1  mov     rcx, [rbp+57h+var_20]
0x1800466d5  xor     rcx, rsp; StackCookie
0x1800466d8  call    __security_check_cookie
0x1800466dd  mov     rbx, [rsp+0D0h+arg_10]
0x1800466e5  add     rsp, 0C0h
0x1800466ec  pop     rdi
0x1800466ed  pop     rsi
0x1800466ee  pop     rbp
0x1800466ef  retn
```
