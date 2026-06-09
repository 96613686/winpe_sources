# CUpdate::get_InternalProperty(ulong,tagVARIANT *)

- ea: `0x18004fdc0`
- end: `0x1800505fa`
- name: `?get_InternalProperty@CUpdate@@UEAAJKPEAUtagVARIANT@@@Z`
- size: `2106`
- prototype: `int(CUpdate *__hidden this, unsigned int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x18000ed90`
- `0x1800220b0`
- `0x18002d324`
- `0x18002d41c`
- `0x180047704`
- `0x18004fdc0`
- `0x180091c70`
- `0x180096bb0`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180050019`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180050105`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180050019`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180050105`
- `OLEAUT32!__imp_SysAllocString` at `0x180050083`
- `OLEAUT32!__imp_SysAllocString` at `0x180050143`
- `OLEAUT32!__imp_SysAllocString` at `0x180050083`
- `OLEAUT32!__imp_SysAllocString` at `0x180050143`
- `OLEAUT32!__imp_SysFreeString` at `0x18004febb`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fef9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ff6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180050529`
- `OLEAUT32!__imp_SysFreeString` at `0x1800505c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004febb`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fef9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ff6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180050529`
- `OLEAUT32!__imp_SysFreeString` at `0x1800505c8`
- `OLEAUT32!__imp_SysStringLen` at `0x180050488`
- `OLEAUT32!__imp_SysStringLen` at `0x180050488`
- `OLEAUT32!__imp_VariantInit` at `0x18004fe08`
- `OLEAUT32!__imp_VariantInit` at `0x18004fe13`
- `OLEAUT32!__imp_VariantInit` at `0x18004fe30`
- `OLEAUT32!__imp_VariantInit` at `0x18005056e`
- `OLEAUT32!__imp_VariantInit` at `0x18004fe08`
- `OLEAUT32!__imp_VariantInit` at `0x18004fe13`
- `OLEAUT32!__imp_VariantInit` at `0x18004fe30`
- `OLEAUT32!__imp_VariantInit` at `0x18005056e`
- `OLEAUT32!__imp_VariantClear` at `0x1800505bf`
- `OLEAUT32!__imp_VariantClear` at `0x1800505bf`
- `OLEAUT32!__imp_VariantCopy` at `0x18005058e`
- `OLEAUT32!__imp_VariantCopy` at `0x18005058e`

## string_xrefs

- `0x180050549`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x1800505a9`: `C:\__w\1\s\src\Client\comapi\Update.cpp`

## pseudocode

```c
__int64 __fastcall CUpdate::get_InternalProperty(CUpdate *this, unsigned int a2, struct tagVARIANT *a3)
{
  OLECHAR *v4; // rbx
  unsigned int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // edi
  unsigned int v12; // edi
  unsigned int v13; // edi
  unsigned int v14; // edi
  unsigned int v15; // edi
  unsigned int v16; // edi
  unsigned int v17; // edi
  unsigned int v18; // edi
  SHORT v19; // ax
  const wchar_t *v20; // rdi
  int v21; // eax
  const wchar_t *v22; // rdi
  int v23; // eax
  LONG v24; // eax
  const wchar_t *v25; // rdi
  int v26; // eax
  const wchar_t *v27; // rcx
  HRESULT LastError; // eax
  __int64 v29; // r9
  volatile signed __int64 *v30; // rcx
  const char *v31; // r9
  BSTR v32; // rax
  TraceLoggingCorrelationVector *v33; // rcx
  const char *v34; // r9
  BSTR v35; // rax
  unsigned int v36; // edi
  unsigned int v37; // edi
  unsigned int v38; // edi
  unsigned int v39; // edi
  unsigned int v40; // edi
  unsigned int v41; // edi
  unsigned int v42; // edi
  unsigned int v43; // edi
  __int128 *v44; // rdi
  char IsEnabled; // al
  __int128 v46; // xmm1
  __int64 v47; // r9
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int64 v53; // rax
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm0
  __int128 v60; // xmm1
  __int128 v61; // xmm0
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  __int64 v64; // rax
  __int128 v65; // xmm0
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  const wchar_t *v70; // rcx
  const wchar_t *v71; // rcx
  const wchar_t *v72; // rcx
  OLECHAR *v73; // rcx
  const wchar_t *v74; // rdi
  int v75; // eax
  BSTR *lpWideCharStr; // [rsp+20h] [rbp-E0h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  __int128 MultiByteStr; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v81; // [rsp+60h] [rbp-A0h]
  __int128 v82; // [rsp+70h] [rbp-90h]
  __int128 v83; // [rsp+80h] [rbp-80h]
  __int128 v84; // [rsp+90h] [rbp-70h]
  __int128 v85; // [rsp+A0h] [rbp-60h]
  __int128 v86; // [rsp+B0h] [rbp-50h]
  __int128 v87; // [rsp+C0h] [rbp-40h]
  __int128 v88; // [rsp+D0h] [rbp-30h]
  __int128 v89; // [rsp+E0h] [rbp-20h]
  __int128 v90; // [rsp+F0h] [rbp-10h]
  __int128 v91; // [rsp+100h] [rbp+0h]
  __int128 v92; // [rsp+110h] [rbp+10h]
  __int128 v93; // [rsp+120h] [rbp+20h]
  __int64 v94; // [rsp+130h] [rbp+30h]
  WCHAR WideCharStr[136]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = 0;
  bstrString = 0;
  VariantInit(&pvarg);
  VariantInit(&pvarg);
  if ( !a3 )
  {
    v7 = -2147467261;
    v8 = 1718;
LABEL_45:
    v29 = v7;
    goto LABEL_94;
  }
  VariantInit(a3);
  if ( a2 <= 0x110007 )
  {
    if ( a2 == 1114119 )
    {
      pvarg.vt = 11;
      if ( (*(int (__fastcall **)(char *, CY *))(*((_QWORD *)this - 6) + 64LL))((char *)this - 48, &pvarg.cyVal) < 0 )
        pvarg.iVal = 0;
      goto LABEL_91;
    }
    v11 = a2 - 1;
    if ( !v11 )
    {
      v33 = (TraceLoggingCorrelationVector *)*((_QWORD *)this + 123);
      LOBYTE(MultiByteStr) = 0;
      if ( v33 && !TraceLoggingCorrelationVector::Increment(v33, (char *)&MultiByteStr) )
      {
        v7 = -2147418113;
        v8 = 1768;
        goto LABEL_45;
      }
      if ( MultiByteToWideChar(0, 1u, (LPCCH)&MultiByteStr, -1, WideCharStr, 129)
        || (LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x7F,
                          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MultiByteUtil.cpp",
                          v34),
            v7 = LastError,
            LastError >= 0) )
      {
        pvarg.vt = 8;
        v35 = SysAllocString(WideCharStr);
        pvarg.llVal = (LONGLONG)v35;
        if ( WideCharStr[0] && !v35 )
        {
          v7 = -2147024882;
          v8 = 1777;
          v29 = 2147942414LL;
          goto LABEL_94;
        }
        goto LABEL_91;
      }
      v8 = 1771;
      goto LABEL_93;
    }
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 2;
      if ( v13 )
      {
        v14 = v13 - 1114109;
        if ( !v14 )
        {
          v25 = (const wchar_t *)*((_QWORD *)this + 95);
          if ( v25 )
          {
            SysFreeString(0);
            v26 = CSusBSTR::Append((CSusBSTR *)&bstrString, v25);
            v4 = bstrString;
            v7 = v26;
            if ( v26 < 0 )
            {
              v8 = 1725;
              goto LABEL_45;
            }
          }
          goto LABEL_90;
        }
        v15 = v14 - 1;
        if ( !v15 )
        {
          pvarg.vt = 11;
          v19 = *((_WORD *)this + 288);
          goto LABEL_24;
        }
        v16 = v15 - 1;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( v18 )
            {
              if ( v18 == 1 )
              {
                pvarg.vt = 11;
                v19 = *((_WORD *)this + 289);
LABEL_24:
                pvarg.iVal = v19;
                goto LABEL_91;
              }
LABEL_63:
              v7 = -2147024809;
              v8 = 1898;
              v29 = 2147942487LL;
              goto LABEL_94;
            }
            v20 = (const wchar_t *)*((_QWORD *)this + 100);
            if ( v20 )
            {
              SysFreeString(0);
              v21 = CSusBSTR::Append((CSusBSTR *)&bstrString, v20);
              v4 = bstrString;
              v7 = v21;
              if ( v21 < 0 )
              {
                v8 = 1735;
                goto LABEL_45;
              }
            }
          }
          else
          {
            v22 = (const wchar_t *)*((_QWORD *)this + 99);
            if ( v22 )
            {
              SysFreeString(0);
              v23 = CSusBSTR::Append((CSusBSTR *)&bstrString, v22);
              v4 = bstrString;
              v7 = v23;
              if ( v23 < 0 )
              {
                v8 = 1730;
                goto LABEL_45;
              }
            }
          }
LABEL_90:
          VariantInit(&pvarg);
          pvarg.llVal = (LONGLONG)v4;
          pvarg.vt = 8;
          v4 = 0;
          goto LABEL_91;
        }
        pvarg.vt = 19;
        v24 = *((_DWORD *)this + 230);
LABEL_22:
        pvarg.lVal = v24;
LABEL_91:
        LastError = VariantCopy(a3, &pvarg);
        v7 = LastError;
        if ( LastError >= 0 )
        {
          v7 = 0;
          goto LABEL_96;
        }
        v8 = 1902;
        goto LABEL_93;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl) )
      {
        v27 = (const wchar_t *)*((_QWORD *)this + 129);
        pvarg.vt = 8;
        LastError = SusSysAllocString(v27, &pvarg.bstrVal);
        v7 = LastError;
        if ( LastError >= 0 )
          goto LABEL_91;
        v8 = 1886;
        goto LABEL_93;
      }
      v7 = -2147024809;
      v8 = 1891;
      v29 = 2147942487LL;
    }
    else
    {
      v30 = (volatile signed __int64 *)*((_QWORD *)this + 124);
      if ( v30 )
      {
        if ( !TraceLoggingCorrelationVector::ToStringImpl(
                (TraceLoggingCorrelationVector *)v30,
                _InterlockedExchangeAdd64(v30 + 17, 0),
                (char *)&MultiByteStr) )
        {
          v7 = -2147418113;
          v8 = 1787;
          v29 = 2147549183LL;
          goto LABEL_94;
        }
      }
      else
      {
        LOBYTE(MultiByteStr) = 0;
      }
      if ( !MultiByteToWideChar(0, 1u, (LPCCH)&MultiByteStr, -1, WideCharStr, 129) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x7F,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MultiByteUtil.cpp",
                      v31);
        v7 = LastError;
        if ( LastError < 0 )
        {
          v8 = 1790;
          goto LABEL_93;
        }
      }
      pvarg.vt = 8;
      v32 = SysAllocString(WideCharStr);
      pvarg.llVal = (LONGLONG)v32;
      if ( !WideCharStr[0] || v32 )
        goto LABEL_91;
      v7 = -2147024882;
      v8 = 1796;
      v29 = 2147942414LL;
    }
LABEL_94:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)v29,
      (int)lpWideCharStr);
    goto LABEL_96;
  }
  v36 = a2 - 1114120;
  if ( v36 )
  {
    v37 = v36 - 1;
    if ( v37 )
    {
      v38 = v37 - 1;
      if ( v38 )
      {
        v39 = v38 - 1;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( !v40 )
          {
            pvarg.vt = 11;
            pvarg.iVal = -(*((_BYTE *)this + 944) != 0);
            goto LABEL_91;
          }
          v41 = v40 - 1;
          if ( v41 )
          {
            v42 = v41 - 1;
            if ( !v42 )
            {
              pvarg.vt = 21;
              pvarg.llVal = *((_QWORD *)this + 120);
              goto LABEL_91;
            }
            v43 = v42 - 1;
            if ( v43 )
            {
              if ( v43 != 1 )
                goto LABEL_63;
              LODWORD(bstrString) = 0;
              v44 = (__int128 *)((char *)this + 632);
              IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl);
              v46 = *(_OWORD *)((char *)this + 648);
              if ( IsEnabled )
              {
                v47 = *((_QWORD *)this + 129);
                MultiByteStr = *v44;
                v48 = *(_OWORD *)((char *)this + 664);
                v81 = v46;
                v49 = *(_OWORD *)((char *)this + 680);
                v82 = v48;
                v50 = *(_OWORD *)((char *)this + 696);
                v83 = v49;
                v51 = *(_OWORD *)((char *)this + 712);
                v84 = v50;
                v52 = *(_OWORD *)((char *)this + 728);
                v85 = v51;
                v86 = v52;
                v87 = *(_OWORD *)((char *)this + 744);
                v53 = *((_QWORD *)this + 107);
                v54 = *(_OWORD *)((char *)this + 776);
                v88 = *(_OWORD *)((char *)this + 760);
                v55 = *(_OWORD *)((char *)this + 792);
                v89 = v54;
                v56 = *(_OWORD *)((char *)this + 808);
                v90 = v55;
                v57 = *(_OWORD *)((char *)this + 824);
                v91 = v56;
                v58 = *(_OWORD *)((char *)this + 840);
                v92 = v57;
                v93 = v58;
                v94 = v53;
                lpWideCharStr = &bstrString;
                LastError = CSusInternalWrapper::GetReserveScenarioId(
                              (char *)this + 16,
                              (char *)this + 880,
                              &MultiByteStr,
                              v47);
                v7 = LastError;
                if ( LastError < 0 )
                {
                  v8 = 1866;
                  goto LABEL_93;
                }
              }
              else
              {
                MultiByteStr = *v44;
                v59 = *(_OWORD *)((char *)this + 664);
                v81 = v46;
                v60 = *(_OWORD *)((char *)this + 680);
                v82 = v59;
                v61 = *(_OWORD *)((char *)this + 696);
                v83 = v60;
                v62 = *(_OWORD *)((char *)this + 712);
                v84 = v61;
                v63 = *(_OWORD *)((char *)this + 728);
                v85 = v62;
                v86 = v63;
                v87 = *(_OWORD *)((char *)this + 744);
                v64 = *((_QWORD *)this + 107);
                v65 = *(_OWORD *)((char *)this + 776);
                v88 = *(_OWORD *)((char *)this + 760);
                v66 = *(_OWORD *)((char *)this + 792);
                v89 = v65;
                v67 = *(_OWORD *)((char *)this + 808);
                v90 = v66;
                v68 = *(_OWORD *)((char *)this + 824);
                v91 = v67;
                v69 = *(_OWORD *)((char *)this + 840);
                v92 = v68;
                v93 = v69;
                v94 = v64;
                lpWideCharStr = &bstrString;
                LastError = CSusInternalWrapper::GetReserveScenarioId(
                              (char *)this + 16,
                              (char *)this + 880,
                              &MultiByteStr,
                              0);
                v7 = LastError;
                if ( LastError < 0 )
                {
                  v8 = 1873;
                  goto LABEL_93;
                }
              }
              pvarg.vt = 19;
              v24 = (int)bstrString;
              goto LABEL_22;
            }
            v70 = (const wchar_t *)*((_QWORD *)this + 119);
            pvarg.vt = 8;
            LastError = SusSysAllocString(v70, &pvarg.bstrVal);
            v7 = LastError;
            if ( LastError >= 0 )
              goto LABEL_91;
            v8 = 1855;
          }
          else
          {
            v71 = (const wchar_t *)*((_QWORD *)this + 105);
            pvarg.vt = 8;
            LastError = SusSysAllocString(v71, &pvarg.bstrVal);
            v7 = LastError;
            if ( LastError >= 0 )
              goto LABEL_91;
            v8 = 1845;
          }
        }
        else
        {
          v72 = (const wchar_t *)*((_QWORD *)this + 117);
          pvarg.vt = 8;
          LastError = SusSysAllocString(v72, &pvarg.bstrVal);
          v7 = LastError;
          if ( LastError >= 0 )
            goto LABEL_91;
          v8 = 1835;
        }
      }
      else
      {
        v73 = (OLECHAR *)*((_QWORD *)this + 116);
        pvarg.vt = 8;
        if ( SysStringLen(v73) || *((_DWORD *)this + 130) != 2 )
        {
          LastError = SusSysAllocString(*((const wchar_t **)this + 116), &pvarg.bstrVal);
          v7 = LastError;
          if ( LastError >= 0 )
            goto LABEL_91;
          v8 = 1827;
        }
        else
        {
          LastError = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)(*((_QWORD *)this + 53) + 8LL) + 64LL))(
                        *((_QWORD *)this + 53) + 8LL,
                        &pvarg.cyVal);
          v7 = LastError;
          if ( LastError >= 0 )
            goto LABEL_91;
          v8 = 1823;
        }
      }
    }
    else
    {
      pvarg.vt = 7;
      LastError = FileTimeToVariantTime((char *)this + 832, &pvarg.decVal.Lo32, v9, v10);
      v7 = LastError;
      if ( LastError >= 0 )
        goto LABEL_91;
      v8 = 1807;
    }
LABEL_93:
    v29 = (unsigned int)LastError;
    goto LABEL_94;
  }
  v74 = (const wchar_t *)*((_QWORD *)this + 103);
  if ( !v74 )
    goto LABEL_90;
  SysFreeString(0);
  v75 = CSusBSTR::Append((CSusBSTR *)&bstrString, v74);
  v7 = v75;
  if ( v75 >= 0 )
  {
    v4 = bstrString;
    goto LABEL_90;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x709,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
    (const char *)(unsigned int)v75,
    (int)lpWideCharStr);
  v4 = bstrString;
LABEL_96:
  VariantClear(&pvarg);
  SysFreeString(v4);
  return v7;
}

```

## disassembly

```asm
0x18004fdc0  mov     [rsp-8+arg_8], rbx
0x18004fdc5  push    rbp
0x18004fdc6  push    rsi
0x18004fdc7  push    rdi
0x18004fdc8  push    r12
0x18004fdca  push    r13
0x18004fdcc  push    r14
0x18004fdce  push    r15
0x18004fdd0  lea     rbp, [rsp-160h]
0x18004fdd8  sub     rsp, 260h
0x18004fddf  mov     rax, cs:__security_cookie
0x18004fde6  xor     rax, rsp
0x18004fde9  mov     [rbp+190h+var_40], rax
0x18004fdf0  mov     rsi, rcx
0x18004fdf3  xor     r13d, r13d
0x18004fdf6  mov     ebx, r13d
0x18004fdf9  lea     rcx, [rsp+290h+pvarg]; pvarg
0x18004fdfe  mov     [rsp+290h+bstrString], rbx
0x18004fe03  mov     r12, r8
0x18004fe06  mov     edi, edx
0x18004fe08  call    cs:__imp_VariantInit
0x18004fe0e  lea     rcx, [rsp+290h+pvarg]; pvarg
0x18004fe13  call    cs:__imp_VariantInit
0x18004fe19  test    r12, r12
0x18004fe1c  jnz     short loc_18004FE2D
0x18004fe1e  mov     edi, 80004003h
0x18004fe23  mov     edx, 6B6h
0x18004fe28  jmp     loc_1800500DD
0x18004fe2d  mov     rcx, r12; pvarg
0x18004fe30  call    cs:__imp_VariantInit
0x18004fe36  mov     eax, 110007h
0x18004fe3b  cmp     edi, eax
0x18004fe3d  ja      loc_1800501A6
0x18004fe43  jz      loc_180050174
0x18004fe49  sub     edi, 1
0x18004fe4c  jz      loc_1800500B4
0x18004fe52  sub     edi, 1
0x18004fe55  jz      loc_18004FFE8
0x18004fe5b  sub     edi, 2
0x18004fe5e  jz      loc_18004FF97
0x18004fe64  sub     edi, 10FFFDh
0x18004fe6a  jz      loc_18004FF59
0x18004fe70  sub     edi, 1
0x18004fe73  jz      loc_18004FF3E
0x18004fe79  sub     edi, 1
0x18004fe7c  jz      loc_18004FF25
0x18004fe82  sub     edi, 1
0x18004fe85  jz      short loc_18004FEE7
0x18004fe87  sub     edi, 1
0x18004fe8a  jz      short loc_18004FEA9
0x18004fe8c  cmp     edi, 1
0x18004fe8f  jnz     loc_1800501F6
0x18004fe95  lea     eax, [rdi+0Ah]
0x18004fe98  mov     word ptr [rsp+290h+pvarg], ax
0x18004fe9d  movzx   eax, word ptr [rsi+242h]
0x18004fea4  jmp     loc_18004FF4F
0x18004fea9  mov     rdi, [rsi+320h]
0x18004feb0  test    rdi, rdi
0x18004feb3  jz      loc_180050569
0x18004feb9  xor     ecx, ecx; bstrString
0x18004febb  call    cs:__imp_SysFreeString
0x18004fec1  mov     rdx, rdi; wchar_t *
0x18004fec4  lea     rcx, [rsp+290h+bstrString]; this
0x18004fec9  call    ?Append@CSusBSTR@@QEAAJPEB_W@Z; CSusBSTR::Append(wchar_t const *)
0x18004fece  mov     rbx, [rsp+290h+bstrString]
0x18004fed3  mov     edi, eax
0x18004fed5  test    eax, eax
0x18004fed7  jns     loc_180050569
0x18004fedd  mov     edx, 6C7h
0x18004fee2  jmp     loc_1800500DD
0x18004fee7  mov     rdi, [rsi+318h]
0x18004feee  test    rdi, rdi
0x18004fef1  jz      loc_180050569
0x18004fef7  xor     ecx, ecx; bstrString
0x18004fef9  call    cs:__imp_SysFreeString
0x18004feff  mov     rdx, rdi; wchar_t *
0x18004ff02  lea     rcx, [rsp+290h+bstrString]; this
0x18004ff07  call    ?Append@CSusBSTR@@QEAAJPEB_W@Z; CSusBSTR::Append(wchar_t const *)
0x18004ff0c  mov     rbx, [rsp+290h+bstrString]
0x18004ff11  mov     edi, eax
0x18004ff13  test    eax, eax
0x18004ff15  jns     loc_180050569
0x18004ff1b  mov     edx, 6C2h
0x18004ff20  jmp     loc_1800500DD
0x18004ff25  mov     eax, 13h
0x18004ff2a  mov     word ptr [rsp+290h+pvarg], ax
0x18004ff2f  mov     eax, [rsi+398h]
0x18004ff35  mov     dword ptr [rsp+290h+pvarg+8], eax
0x18004ff39  jmp     loc_180050586
0x18004ff3e  mov     eax, 0Bh
0x18004ff43  mov     word ptr [rsp+290h+pvarg], ax
0x18004ff48  movzx   eax, word ptr [rsi+240h]
0x18004ff4f  mov     word ptr [rsp+290h+pvarg+8], ax
0x18004ff54  jmp     loc_180050586
0x18004ff59  mov     rdi, [rsi+2F8h]
0x18004ff60  test    rdi, rdi
0x18004ff63  jz      loc_180050569
0x18004ff69  xor     ecx, ecx; bstrString
0x18004ff6b  call    cs:__imp_SysFreeString
0x18004ff71  mov     rdx, rdi; wchar_t *
0x18004ff74  lea     rcx, [rsp+290h+bstrString]; this
0x18004ff79  call    ?Append@CSusBSTR@@QEAAJPEB_W@Z; CSusBSTR::Append(wchar_t const *)
0x18004ff7e  mov     rbx, [rsp+290h+bstrString]
0x18004ff83  mov     edi, eax
0x18004ff85  test    eax, eax
0x18004ff87  jns     loc_180050569
0x18004ff8d  mov     edx, 6BDh
0x18004ff92  jmp     loc_1800500DD
0x18004ff97  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x18004ff9e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(void)
0x18004ffa3  test    al, al
0x18004ffa5  jz      short loc_18004FFD6
0x18004ffa7  mov     rcx, [rsi+408h]; wchar_t *
0x18004ffae  lea     rdx, [rsp+290h+pvarg+8]; wchar_t **
0x18004ffb3  mov     eax, 8
0x18004ffb8  mov     word ptr [rsp+290h+pvarg], ax
0x18004ffbd  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x18004ffc2  mov     edi, eax
0x18004ffc4  test    eax, eax
0x18004ffc6  jns     loc_180050586
0x18004ffcc  mov     edx, 75Eh
0x18004ffd1  jmp     loc_18005059F
0x18004ffd6  mov     edi, 80070057h
0x18004ffdb  mov     edx, 763h
0x18004ffe0  mov     r9d, edi
0x18004ffe3  jmp     loc_1800505A2
0x18004ffe8  mov     rcx, [rsi+3E0h]; this
0x18004ffef  test    rcx, rcx
0x18004fff2  jnz     short loc_180050049
0x18004fff4  mov     byte ptr [rsp+290h+MultiByteStr], r13b
0x18004fff9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18004fffd  mov     [rsp+290h+cchWideChar], 81h; cchWideChar
0x180050005  lea     rax, [rbp+190h+WideCharStr]
0x180050009  xor     ecx, ecx; CodePage
0x18005000b  lea     r8, [rsp+290h+MultiByteStr]; lpMultiByteStr
0x180050010  mov     [rsp+290h+lpWideCharStr], rax; lpWideCharStr
0x180050015  lea     edx, [r9+2]; dwFlags
0x180050019  call    cs:__imp_MultiByteToWideChar
0x18005001f  test    eax, eax
0x180050021  jnz     short loc_180050075
0x180050023  mov     rcx, [rbp+198h]; this
0x18005002a  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180050031  lea     edx, [rax+7Fh]; void *
0x180050034  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180050039  mov     edi, eax
0x18005003b  test    eax, eax
0x18005003d  jns     short loc_180050075
0x18005003f  mov     edx, 6FEh
0x180050044  jmp     loc_18005059F
0x180050049  mov     rdx, r13
0x18005004c  lock xadd [rcx+88h], rdx; unsigned __int64
0x180050055  lea     r8, [rsp+290h+MultiByteStr]; char *
0x18005005a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18005005f  test    al, al
0x180050061  jnz     short loc_18004FFF9
0x180050063  mov     edi, 8000FFFFh
0x180050068  mov     edx, 6FBh
0x18005006d  mov     r9d, edi
0x180050070  jmp     loc_1800505A2
0x180050075  mov     eax, 8
0x18005007a  lea     rcx, [rbp+190h+WideCharStr]; psz
0x18005007e  mov     word ptr [rsp+290h+pvarg], ax
0x180050083  call    cs:__imp_SysAllocString
0x180050089  mov     qword ptr [rsp+290h+pvarg+8], rax
0x18005008e  cmp     [rbp+190h+WideCharStr], r13w
0x180050093  jz      loc_180050586
0x180050099  test    rax, rax
0x18005009c  jnz     loc_180050586
0x1800500a2  mov     edi, 8007000Eh
0x1800500a7  mov     edx, 704h
0x1800500ac  mov     r9d, edi
0x1800500af  jmp     loc_1800505A2
0x1800500b4  mov     rcx, [rsi+3D8h]; this
0x1800500bb  mov     byte ptr [rsp+290h+MultiByteStr], r13b
0x1800500c0  test    rcx, rcx
0x1800500c3  jz      short loc_1800500E5
0x1800500c5  lea     rdx, [rsp+290h+MultiByteStr]; char *
0x1800500ca  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800500cf  test    al, al
0x1800500d1  jnz     short loc_1800500E5
0x1800500d3  mov     edi, 8000FFFFh
0x1800500d8  mov     edx, 6E8h
0x1800500dd  mov     r9d, edi
0x1800500e0  jmp     loc_1800505A2
0x1800500e5  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800500e9  mov     [rsp+290h+cchWideChar], 81h; cchWideChar
0x1800500f1  lea     rax, [rbp+190h+WideCharStr]
0x1800500f5  xor     ecx, ecx; CodePage
0x1800500f7  lea     r8, [rsp+290h+MultiByteStr]; lpMultiByteStr
0x1800500fc  mov     [rsp+290h+lpWideCharStr], rax; lpWideCharStr
0x180050101  lea     edx, [r9+2]; dwFlags
0x180050105  call    cs:__imp_MultiByteToWideChar
0x18005010b  test    eax, eax
0x18005010d  jnz     short loc_180050135
0x18005010f  mov     rcx, [rbp+198h]; this
0x180050116  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005011d  lea     edx, [rax+7Fh]; void *
0x180050120  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180050125  mov     edi, eax
0x180050127  test    eax, eax
0x180050129  jns     short loc_180050135
0x18005012b  mov     edx, 6EBh
0x180050130  jmp     loc_18005059F
0x180050135  mov     eax, 8
0x18005013a  lea     rcx, [rbp+190h+WideCharStr]; psz
0x18005013e  mov     word ptr [rsp+290h+pvarg], ax
0x180050143  call    cs:__imp_SysAllocString
0x180050149  mov     qword ptr [rsp+290h+pvarg+8], rax
0x18005014e  cmp     [rbp+190h+WideCharStr], r13w
0x180050153  jz      loc_180050586
0x180050159  test    rax, rax
0x18005015c  jnz     loc_180050586
0x180050162  mov     edi, 8007000Eh
0x180050167  mov     edx, 6F1h
0x18005016c  mov     r9d, edi
0x18005016f  jmp     loc_1800505A2
0x180050174  mov     eax, 0Bh
0x180050179  lea     rcx, [rsi-30h]
0x18005017d  mov     word ptr [rsp+290h+pvarg], ax
0x180050182  lea     rdx, [rsp+290h+pvarg+8]
0x180050187  mov     rax, [rcx]
0x18005018a  mov     rax, [rax+40h]
0x18005018e  call    _guard_dispatch_icall
0x180050193  test    eax, eax
0x180050195  jns     loc_180050586
0x18005019b  mov     word ptr [rsp+290h+pvarg+8], r13w
0x1800501a1  jmp     loc_180050586
0x1800501a6  sub     edi, 110008h
0x1800501ac  jz      loc_18005051B
0x1800501b2  sub     edi, 1
0x1800501b5  jz      loc_1800504F0
0x1800501bb  sub     edi, 1
0x1800501be  jz      loc_180050477
0x1800501c4  sub     edi, 1
0x1800501c7  jz      loc_180050448
0x1800501cd  sub     edi, 1
0x1800501d0  jz      loc_180050429
0x1800501d6  sub     edi, 1
0x1800501d9  jz      loc_1800503FA
0x1800501df  sub     edi, 1
0x1800501e2  jz      loc_1800503DF
0x1800501e8  sub     edi, 1
0x1800501eb  jz      loc_1800503B0
0x1800501f1  cmp     edi, 1
0x1800501f4  jz      short loc_180050208
0x1800501f6  mov     edi, 80070057h
0x1800501fb  mov     edx, 76Ah
0x180050200  mov     r9d, edi
0x180050203  jmp     loc_1800505A2
0x180050208  mov     dword ptr [rsp+290h+bstrString], r13d
0x18005020d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x180050214  lea     r14, [rsi+370h]
0x18005021b  lea     rdi, [rsi+278h]
0x180050222  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(void)
0x180050227  movups  xmm0, xmmword ptr [rdi]
0x18005022a  test    al, al
0x18005022c  mov     eax, 80h
0x180050231  movups  xmm1, xmmword ptr [rdi+10h]
0x180050235  jz      loc_1800502F7
0x18005023b  mov     r9, [rsi+408h]
0x180050242  lea     r8, [rsp+290h+MultiByteStr]
0x180050247  movups  xmmword ptr [r8], xmm0
0x18005024b  mov     rdx, r14
0x18005024e  lea     rcx, [rsi+10h]
0x180050252  movups  xmm0, xmmword ptr [rdi+20h]
0x180050256  movups  xmmword ptr [r8+10h], xmm1
0x18005025b  movups  xmm1, xmmword ptr [rdi+30h]
0x18005025f  movups  xmmword ptr [r8+20h], xmm0
0x180050264  movups  xmm0, xmmword ptr [rdi+40h]
0x180050268  movups  xmmword ptr [r8+30h], xmm1
0x18005026d  movups  xmm1, xmmword ptr [rdi+50h]
0x180050271  movups  xmmword ptr [r8+40h], xmm0
0x180050276  movups  xmm0, xmmword ptr [rdi+60h]
0x18005027a  movups  xmmword ptr [r8+50h], xmm1
0x18005027f  movups  xmmword ptr [r8+60h], xmm0
0x180050284  add     r8, rax
0x180050287  movups  xmm0, xmmword ptr [rdi+70h]
0x18005028b  add     rdi, rax
0x18005028e  movups  xmmword ptr [r8-10h], xmm0
0x180050293  movups  xmm1, xmmword ptr [rdi]
0x180050296  mov     rax, [rdi+60h]
0x18005029a  movups  xmm0, xmmword ptr [rdi+10h]
0x18005029e  movups  xmmword ptr [r8], xmm1
0x1800502a2  movups  xmm1, xmmword ptr [rdi+20h]
0x1800502a6  movups  xmmword ptr [r8+10h], xmm0
0x1800502ab  movups  xmm0, xmmword ptr [rdi+30h]
0x1800502af  movups  xmmword ptr [r8+20h], xmm1
0x1800502b4  movups  xmm1, xmmword ptr [rdi+40h]
0x1800502b8  movups  xmmword ptr [r8+30h], xmm0
0x1800502bd  movups  xmm0, xmmword ptr [rdi+50h]
0x1800502c1  movups  xmmword ptr [r8+40h], xmm1
0x1800502c6  movups  xmmword ptr [r8+50h], xmm0
0x1800502cb  mov     [r8+60h], rax
0x1800502cf  lea     rax, [rsp+290h+bstrString]
0x1800502d4  lea     r8, [rsp+290h+MultiByteStr]
0x1800502d9  mov     [rsp+290h+lpWideCharStr], rax
0x1800502de  call    ?GetReserveScenarioId@CSusInternalWrapper@@QEAAJAEBU_GUID@@UtagMatchingUpdate@@PEB_WPEAK@Z; CSusInternalWrapper::GetReserveScenarioId(_GUID const &,tagMatchingUpdate,wchar_t const *,ulong *)
0x1800502e3  mov     edi, eax
0x1800502e5  test    eax, eax
0x1800502e7  jns     loc_18005039D
  ... truncated ...
```
