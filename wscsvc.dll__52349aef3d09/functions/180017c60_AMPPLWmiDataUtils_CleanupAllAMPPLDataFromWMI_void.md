# AMPPLWmiDataUtils::CleanupAllAMPPLDataFromWMI(void)

- ea: `0x180017c60`
- end: `0x1800186d8`
- name: `?CleanupAllAMPPLDataFromWMI@AMPPLWmiDataUtils@@YAJXZ`
- size: `2680`
- prototype: `__int64 __fastcall(AMPPLWmiDataUtils *this, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001d9e0`

## callees

- `0x180005220`
- `0x180006a70`
- `0x180008e48`
- `0x180017a48`
- `0x180017c60`
- `0x1800186e0`
- `0x180018750`
- `0x1800202e8`
- `0x18002751c`
- `0x18002818c`
- `0x180029e74`
- `0x1800325d0`
- `0x18003edc4`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180017daa`
- `OLEAUT32!__imp_SysAllocString` at `0x180018506`
- `OLEAUT32!__imp_SysAllocString` at `0x180017daa`
- `OLEAUT32!__imp_SysAllocString` at `0x180018506`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e41`
- `OLEAUT32!__imp_SysFreeString` at `0x18001857a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800185fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e41`
- `OLEAUT32!__imp_SysFreeString` at `0x18001857a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800185fc`
- `OLEAUT32!__imp_VariantInit` at `0x180017e8e`
- `OLEAUT32!__imp_VariantInit` at `0x180017e8e`
- `OLEAUT32!__imp_VariantClear` at `0x18001844c`
- `OLEAUT32!__imp_VariantClear` at `0x18001844c`

## string_xrefs

- `0x180017f36`: `pathToSignedProductExe`
- `0x18001801d`: `pathToCaller`

## pseudocode

```c
__int64 __fastcall AMPPLWmiDataUtils::CleanupAllAMPPLDataFromWMI(AMPPLWmiDataUtils *this, __int64 a2)
{
  OLECHAR *v3; // rdi
  struct CWmiEventManagerAvFw *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rbx
  OLECHAR *v7; // rsi
  int v8; // r14d
  int v9; // r12d
  int v10; // eax
  int v11; // eax
  const unsigned __int16 *v12; // r8
  int v13; // eax
  void *v14; // r15
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // rdx
  CommonUtil *v17; // r14
  int v18; // eax
  unsigned __int64 v19; // rcx
  char *v20; // rax
  signed __int64 v21; // rdx
  CommonUtil *v22; // rcx
  unsigned int v23; // r15d
  void *v24; // r14
  unsigned __int64 v25; // rcx
  _QWORD *v26; // r14
  OLECHAR *v27; // r14
  __int64 v28; // [rsp+0h] [rbp-148h] BYREF
  unsigned __int64 v29; // [rsp+40h] [rbp-108h]
  __int64 v30; // [rsp+48h] [rbp-100h] BYREF
  __int64 v31; // [rsp+50h] [rbp-F8h] BYREF
  void *Block; // [rsp+58h] [rbp-F0h] BYREF
  CommonUtil *v33; // [rsp+60h] [rbp-E8h] BYREF
  void *v34; // [rsp+68h] [rbp-E0h]
  OLECHAR *psz; // [rsp+70h] [rbp-D8h] BYREF
  int v36; // [rsp+78h] [rbp-D0h] BYREF
  __int128 v37; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+90h] [rbp-B8h]
  __int64 v39; // [rsp+98h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-A8h] BYREF
  OLECHAR *v41; // [rsp+B8h] [rbp-90h]
  signed __int64 v42; // [rsp+C0h] [rbp-88h]
  void *v43[4]; // [rsp+C8h] [rbp-80h] BYREF
  const exception *v44; // [rsp+E8h] [rbp-60h] BYREF

  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl'::`2'::impl,
    a2);
  if ( !g_pWmiEventManagerAvFw )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_93277130f4d6304520323beb48801075_Traceguids);
    }
    return 2147500037LL;
  }
  v31 = 0;
  v3 = 0;
  psz = 0;
  v4 = g_pWmiEventManagerAvFw;
  v5 = *((_QWORD *)g_pWmiEventManagerAvFw + 8);
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_93277130f4d6304520323beb48801075_Traceguids, 2147500037LL);
    }
    CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v31);
    return 2147500037LL;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  v6 = *((_QWORD *)v4 + 8);
  v31 = v6;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_93277130f4d6304520323beb48801075_Traceguids);
    }
    CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v31);
    return 2147942487LL;
  }
  v7 = SysAllocString(L"WSC_CallerAMPPLData");
  v41 = v7;
  if ( v7 )
  {
    v39 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, _QWORD, __int64 *))(*(_QWORD *)v6 + 144LL))(
           v6,
           v7,
           48,
           0,
           &v39);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          WPP_93277130f4d6304520323beb48801075_Traceguids,
          (unsigned int)v8);
      }
      CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v39);
      SysFreeString(v7);
      CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v31);
      return (unsigned int)v8;
    }
    v9 = 0;
    v37 = 0;
    v38 = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v29 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v34 = 0;
LABEL_23:
    if ( v9 >= 0 && v9 != 1 )
    {
      while ( 1 )
      {
        v30 = 0;
        v36 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v39 + 32LL))(
                v39,
                1000,
                1,
                &v30,
                &v36);
        v9 = v10;
        if ( v10 < 0 || !v36 || v10 == 1 )
        {
          if ( !v30 )
            goto LABEL_23;
          goto LABEL_101;
        }
        v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v30 + 32LL))(
                v30,
                L"pathToSignedProductExe",
                0,
                &pvarg,
                0,
                0);
        v9 = v11;
        if ( v11 >= 0 )
        {
          if ( pvarg.vt != 8 )
          {
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                44,
                WPP_93277130f4d6304520323beb48801075_Traceguids,
                pvarg.vt);
            }
            goto LABEL_52;
          }
          Block = 0;
          v13 = ((int (__stdcall *)(CommonUtil *, unsigned __int16 **, const unsigned __int16 *))CommonUtil::HrDuplicateStringW)(
                  (CommonUtil *)&Block,
                  pvarg.pbstrVal,
                  v12);
          v14 = Block;
          if ( v13 < 0 && Block )
          {
            operator delete(Block);
            v14 = 0;
            Block = 0;
          }
          v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v30 + 32LL))(
                 v30,
                 L"pathToCaller",
                 0,
                 &pvarg,
                 0,
                 0);
          if ( v9 >= 0 )
          {
            if ( pvarg.vt != 8 )
            {
              if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  46,
                  WPP_93277130f4d6304520323beb48801075_Traceguids,
                  pvarg.vt);
              }
              if ( v14 )
                operator delete(v14);
              goto LABEL_52;
            }
            v33 = 0;
            v9 = ((int (__stdcall *)(CommonUtil *, unsigned __int16 **, const unsigned __int16 *))CommonUtil::HrDuplicateStringW)(
                   (CommonUtil *)&v33,
                   pvarg.pbstrVal,
                   v15);
            v17 = v33;
            if ( v9 < 0 )
            {
              if ( v33 )
              {
                operator delete(v33);
                v17 = 0;
                v33 = 0;
              }
              v9 = 0;
            }
            if ( v14 && (int)CommonUtil::UtilIsFileExists((CommonUtil *)v14, v16) >= 0
              || v17 && (int)CommonUtil::UtilIsFileExists(v17, v16) >= 0 )
            {
              if ( v17 )
                operator delete(v17);
              if ( v14 )
                goto LABEL_64;
              goto LABEL_52;
            }
            v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v30 + 32LL))(
                    v30,
                    L"instanceGuid",
                    0,
                    &pvarg,
                    0,
                    0);
            v9 = v18;
            if ( v18 >= 0 )
            {
              if ( pvarg.vt != 8 )
              {
                if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    48,
                    WPP_93277130f4d6304520323beb48801075_Traceguids,
                    pvarg.vt);
                }
                if ( v17 )
                  operator delete(v17);
                if ( v14 )
LABEL_64:
                  operator delete(v14);
LABEL_52:
                CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v30);
                goto LABEL_23;
              }
              if ( __eh34_try(0, 1) )
              {
                __eh34_scope_strut(1);
                std::wstring::wstring(v43, pvarg.llVal);
                v19 = v29;
                if ( (unsigned __int64)v43 >= v29 || (v20 = (char *)v34, v34 > v43) )
                {
                  if ( v29 == v38 )
                  {
                    std::vector<std::wstring>::_Reserve(&v37);
                    v19 = *((_QWORD *)&v37 + 1);
                    v29 = *((_QWORD *)&v37 + 1);
                    v34 = (void *)v37;
                  }
                  std::wstring::wstring(v19, v43);
                  v29 += 32LL;
                  *((_QWORD *)&v37 + 1) = v29;
                }
                else
                {
                  v21 = (char *)v43 - (_BYTE *)v34;
                  v42 = (char *)v43 - (_BYTE *)v34;
                  if ( v29 == v38 )
                  {
                    std::vector<std::wstring>::_Reserve(&v37);
                    v19 = *((_QWORD *)&v37 + 1);
                    v29 = *((_QWORD *)&v37 + 1);
                    v20 = (char *)v37;
                    v34 = (void *)v37;
                    v21 = v42;
                  }
                  std::wstring::wstring(v19, &v20[v21 & 0xFFFFFFFFFFFFFFE0uLL]);
                  v29 += 32LL;
                  *((_QWORD *)&v37 + 1) = v29;
                }
                if ( v43[3] >= (void *)8 )
                  operator delete(v43[0]);
              }
              if ( __eh34_catch(1) )
              {
                if ( __eh34_catch_type(1, &exception `RTTI Type Descriptor', &v44) )
                  CommonUtil::HrFromStdException(v22, (const struct exception *)&v28);
              }
              if ( v17 )
                operator delete(v17);
              if ( v14 )
                operator delete(v14);
              if ( v30 )
              {
LABEL_101:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                goto LABEL_23;
              }
              goto LABEL_23;
            }
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                WPP_93277130f4d6304520323beb48801075_Traceguids,
                (unsigned int)v18);
            }
            if ( v17 )
              operator delete(v17);
            if ( v14 )
LABEL_73:
              operator delete(v14);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                45,
                WPP_93277130f4d6304520323beb48801075_Traceguids,
                pvarg.vt);
            }
            if ( v14 )
              goto LABEL_73;
          }
        }
        else if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v11);
        }
        CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v30);
      }
    }
    VariantClear(&pvarg);
    v23 = 0;
    while ( 1 )
    {
      v24 = v34;
      v25 = (__int64)(v29 - (_QWORD)v34) >> 5;
      if ( v23 >= v25 )
      {
        if ( v34 )
        {
          std::vector<std::wstring>::_Destroy(v25, v34, v29);
          operator delete(v24);
        }
        if ( v39 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        SysFreeString(v7);
        if ( v3 )
          operator delete(v3);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v9 < 0
          && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            WPP_93277130f4d6304520323beb48801075_Traceguids,
            (unsigned int)v9);
        }
        return (unsigned int)v9;
      }
      v26 = (char *)v34 + 32 * v23;
      if ( v26[3] >= 8u )
        v26 = (_QWORD *)*v26;
      if ( v3 )
      {
        operator delete(v3);
        psz = 0;
      }
      v9 = CommonUtil::NewSprintfW(
             (CommonUtil *)&psz,
             (wchar_t *)L"%ls.%ls=\"%ls\"",
             L"WSC_CallerAMPPLData",
             L"instanceGuid",
             v26);
      if ( v9 < 0 )
        break;
      v3 = psz;
      v27 = SysAllocString(psz);
      v42 = (signed __int64)v27;
      if ( v27 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v6 + 128LL))(
               v6,
               v27,
               0,
               0,
               0);
        if ( v9 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              WPP_93277130f4d6304520323beb48801075_Traceguids,
              (unsigned int)v9);
          }
          v9 = 0;
        }
        SysFreeString(v27);
        ++v23;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_93277130f4d6304520323beb48801075_Traceguids);
        }
LABEL_123:
        ++v23;
      }
    }
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        WPP_93277130f4d6304520323beb48801075_Traceguids,
        (unsigned int)v9);
    }
    v9 = 0;
    v3 = psz;
    goto LABEL_123;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_93277130f4d6304520323beb48801075_Traceguids, 2147942414LL);
  CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(&v31);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180017c60  push    rbx
0x180017c62  push    rsi
0x180017c63  push    rdi
0x180017c64  push    r12
0x180017c66  push    r13
0x180017c68  push    r14
0x180017c6a  push    r15
0x180017c6c  sub     rsp, 110h
0x180017c73  movaps  [rsp+148h+var_48], xmm6
0x180017c7b  mov     rax, cs:__security_cookie
0x180017c82  xor     rax, rsp
0x180017c85  mov     [rsp+148h+var_50], rax
0x180017c8d  mov     dl, 1
0x180017c8f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::GetImpl(void)'::`2'::impl
0x180017c96  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WSCPersistAMPPLDataToWmi>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180017c9b  cmp     cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA, 0; CWmiEventManagerAvFw * g_pWmiEventManagerAvFw
0x180017ca3  jnz     short loc_180017CDD
0x180017ca5  lea     rax, WPP_GLOBAL_Control
0x180017cac  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cb3  cmp     rcx, rax
0x180017cb6  jz      short loc_180017CD3
0x180017cb8  test    byte ptr [rcx+1Ch], 1
0x180017cbc  jz      short loc_180017CD3
0x180017cbe  mov     edx, 26h ; '&'
0x180017cc3  lea     r8, WPP_93277130f4d6304520323beb48801075_Traceguids
0x180017cca  mov     rcx, [rcx+10h]
0x180017cce  call    WPP_SF_
0x180017cd3  mov     eax, 80004005h
0x180017cd8  jmp     loc_1800186AC
0x180017cdd  xor     r13d, r13d
0x180017ce0  mov     [rsp+148h+var_F8], r13
0x180017ce5  mov     edi, r13d
0x180017ce8  mov     [rsp+148h+psz], r13
0x180017ced  mov     rbx, cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA; CWmiEventManagerAvFw * g_pWmiEventManagerAvFw
0x180017cf4  mov     rcx, [rbx+40h]
0x180017cf8  test    rcx, rcx
0x180017cfb  jnz     short loc_180017D46
0x180017cfd  lea     rax, WPP_GLOBAL_Control
0x180017d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d0b  cmp     rcx, rax
0x180017d0e  jz      short loc_180017D32
0x180017d10  test    byte ptr [rcx+1Ch], 1
0x180017d14  jz      short loc_180017D32
0x180017d16  mov     edx, 27h ; '''
0x180017d1b  mov     r9d, 80004005h
0x180017d21  lea     r8, WPP_93277130f4d6304520323beb48801075_Traceguids
0x180017d28  mov     rcx, [rcx+10h]
0x180017d2c  call    WPP_SF_d
0x180017d31  nop
0x180017d32  lea     rcx, [rsp+148h+var_F8]
0x180017d37  call    ??1?$AutoRef@UIEnumWbemClassObject@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(void)
0x180017d3c  mov     eax, 80004005h
0x180017d41  jmp     loc_1800186AC
0x180017d46  mov     rax, [rcx]
0x180017d49  mov     rax, [rax+8]
0x180017d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d52  mov     rbx, [rbx+40h]
0x180017d56  mov     [rsp+148h+var_F8], rbx
0x180017d5b  test    rbx, rbx
0x180017d5e  jnz     short loc_180017DA3
0x180017d60  lea     rax, WPP_GLOBAL_Control
0x180017d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d6e  cmp     rcx, rax
0x180017d71  jz      short loc_180017D8F
0x180017d73  test    byte ptr [rcx+1Ch], 1
0x180017d77  jz      short loc_180017D8F
0x180017d79  mov     edx, 28h ; '('
0x180017d7e  lea     r8, WPP_93277130f4d6304520323beb48801075_Traceguids
0x180017d85  mov     rcx, [rcx+10h]
0x180017d89  call    WPP_SF_
0x180017d8e  nop
0x180017d8f  lea     rcx, [rsp+148h+var_F8]
0x180017d94  call    ??1?$AutoRef@UIEnumWbemClassObject@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(void)
0x180017d99  mov     eax, 80070057h
0x180017d9e  jmp     loc_1800186AC
0x180017da3  lea     rcx, psz; "WSC_CallerAMPPLData"
0x180017daa  call    cs:__imp_SysAllocString
0x180017db0  mov     rsi, rax
0x180017db3  mov     [rsp+148h+var_90], rax
0x180017dbb  test    rax, rax
0x180017dbe  jz      loc_180018628
0x180017dc4  mov     [rsp+148h+var_B0], r13
0x180017dcc  mov     rax, [rbx]
0x180017dcf  lea     rcx, [rsp+148h+var_B0]
0x180017dd7  mov     [rsp+148h+var_128], rcx
0x180017ddc  xor     r9d, r9d
0x180017ddf  mov     r8d, 30h ; '0'
0x180017de5  mov     rdx, rsi
0x180017de8  mov     rcx, rbx
0x180017deb  mov     rax, [rax+90h]
0x180017df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017df7  mov     r14d, eax
0x180017dfa  test    eax, eax
0x180017dfc  jns     short loc_180017E5A
0x180017dfe  lea     rax, WPP_GLOBAL_Control
0x180017e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e0c  cmp     rcx, rax
0x180017e0f  jz      short loc_180017E30
0x180017e11  test    byte ptr [rcx+1Ch], 1
0x180017e15  jz      short loc_180017E30
0x180017e17  mov     edx, 2Ah ; '*'
0x180017e1c  mov     r9d, r14d
0x180017e1f  lea     r8, WPP_93277130f4d6304520323beb48801075_Traceguids
0x180017e26  mov     rcx, [rcx+10h]
0x180017e2a  call    WPP_SF_d
0x180017e2f  nop
0x180017e30  lea     rcx, [rsp+148h+var_B0]
0x180017e38  call    ??1?$AutoRef@UIEnumWbemClassObject@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(void)
0x180017e3d  nop
0x180017e3e  mov     rcx, rsi; bstrString
0x180017e41  call    cs:__imp_SysFreeString
0x180017e47  nop
0x180017e48  lea     rcx, [rsp+148h+var_F8]
0x180017e4d  call    ??1?$AutoRef@UIEnumWbemClassObject@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(void)
0x180017e52  mov     eax, r14d
0x180017e55  jmp     loc_1800186AC
0x180017e5a  mov     r12d, r13d
0x180017e5d  xorps   xmm6, xmm6
0x180017e60  movdqu  [rsp+148h+var_C8], xmm6
0x180017e69  mov     [rsp+148h+var_B8], r13
0x180017e71  xorps   xmm0, xmm0
0x180017e74  xor     eax, eax
0x180017e76  movups  xmmword ptr [rsp+148h+pvarg], xmm0
0x180017e7e  mov     qword ptr [rsp+148h+pvarg+10h], rax
0x180017e86  lea     rcx, [rsp+148h+pvarg]; pvarg
0x180017e8e  call    cs:__imp_VariantInit
0x180017e94  xorps   xmm0, xmm0
0x180017e97  psrldq  xmm0, 8
0x180017e9c  movq    [rsp+148h+var_108], xmm0
0x180017ea2  movq    [rsp+148h+var_E0], xmm6
0x180017ea8  lea     r14, WPP_GLOBAL_Control
0x180017eaf  test    r12d, r12d
0x180017eb2  js      loc_180018444
0x180017eb8  cmp     r12d, 1
0x180017ebc  jz      loc_180018444
0x180017ec2  mov     [rsp+148h+var_100], r13
0x180017ec7  mov     [rsp+148h+var_D0], r13d
0x180017ecc  mov     rcx, [rsp+148h+var_B0]
0x180017ed4  mov     rax, [rcx]
0x180017ed7  lea     rdx, [rsp+148h+var_D0]
0x180017edc  mov     [rsp+148h+var_128], rdx
0x180017ee1  lea     r9, [rsp+148h+var_100]
0x180017ee6  mov     edx, 3E8h
0x180017eeb  mov     r8d, 1
0x180017ef1  mov     rax, [rax+20h]
0x180017ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017efa  mov     r12d, eax
0x180017efd  test    eax, eax
0x180017eff  js      loc_180018425
0x180017f05  cmp     [rsp+148h+var_D0], 0
0x180017f0a  jz      loc_180018425
0x180017f10  cmp     eax, 1
0x180017f13  jz      loc_180018425
0x180017f19  mov     rcx, [rsp+148h+var_100]
0x180017f1e  mov     rax, [rcx]
0x180017f21  mov     [rsp+148h+var_120], r13
0x180017f26  mov     [rsp+148h+var_128], r13
0x180017f2b  lea     r9, [rsp+148h+pvarg]
0x180017f33  xor     r8d, r8d
0x180017f36  lea     rdx, aPathtosignedpr; "pathToSignedProductExe"
0x180017f3d  mov     rax, [rax+20h]
0x180017f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f46  mov     r12d, eax
0x180017f49  test    eax, eax
0x180017f4b  jns     short loc_180017F84
0x180017f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f54  cmp     rcx, r14
0x180017f57  jz      loc_1800181E0
0x180017f5d  test    byte ptr [rcx+1Ch], 1
0x180017f61  jz      loc_1800181E0
0x180017f67  mov     edx, 2Bh ; '+'
0x180017f6c  mov     r9d, eax
0x180017f6f  lea     r8, WPP_93277130f4d6304520323beb48801075_Traceguids
0x180017f76  mov     rcx, [rcx+10h]
0x180017f7a  call    WPP_SF_d
0x180017f7f  jmp     loc_1800181E0
0x180017f84  movzx   eax, word ptr [rsp+148h+pvarg]
0x180017f8c  cmp     eax, 8
0x180017f8f  jz      short loc_180017FCB
0x180017f91  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f98  cmp     rcx, r14
0x180017f9b  jz      short loc_180017FBC
0x180017f9d  test    byte ptr [rcx+1Ch], 1
0x180017fa1  jz      short loc_180017FBC
0x180017fa3  mov     r9d, eax
0x180017fa6  mov     edx, 2Ch ; ','
0x180017fab  lea     r8, WPP_93277130f4d6304520323beb48801075_Traceguids
0x180017fb2  mov     rcx, [rcx+10h]
0x180017fb6  call    WPP_SF_d
0x180017fbb  nop
0x180017fbc  lea     rcx, [rsp+148h+var_100]
0x180017fc1  call    ??1?$AutoRef@UIEnumWbemClassObject@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(void)
0x180017fc6  jmp     loc_180017EAF
0x180017fcb  mov     [rsp+148h+Block], r13
0x180017fd0  mov     rdx, qword ptr [rsp+148h+pvarg+8]; unsigned __int16 **
0x180017fd8  lea     rcx, [rsp+148h+Block]; this
0x180017fdd  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x180017fe2  mov     r15, [rsp+148h+Block]
0x180017fe7  test    eax, eax
0x180017fe9  jns     short loc_180018000
0x180017feb  test    r15, r15
0x180017fee  jz      short loc_180018000
0x180017ff0  mov     rcx, r15; Block
0x180017ff3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017ff8  mov     r15, r13
0x180017ffb  mov     [rsp+148h+Block], r13
0x180018000  mov     rcx, [rsp+148h+var_100]
0x180018005  mov     rax, [rcx]
0x180018008  mov     [rsp+148h+var_120], r13
0x18001800d  mov     [rsp+148h+var_128], r13
0x180018012  lea     r9, [rsp+148h+pvarg]
0x18001801a  xor     r8d, r8d
0x18001801d  lea     rdx, aPathtocaller; "pathToCaller"
0x180018024  mov     rax, [rax+20h]
0x180018028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001802d  mov     r12d, eax
0x180018030  test    eax, eax
0x180018032  jns     short loc_18001807B
0x180018034  mov     rcx, cs:WPP_GLOBAL_Control
0x18001803b  cmp     rcx, r14
0x18001803e  jz      short loc_180018065
0x180018040  test    byte ptr [rcx+1Ch], 1
0x180018044  jz      short loc_180018065
0x180018046  movzx   r9d, word ptr [rsp+148h+pvarg]
0x18001804f  mov     edx, 2Dh ; '-'
0x180018054  lea     r8, WPP_93277130f4d6304520323beb48801075_Traceguids
0x18001805b  mov     rcx, [rcx+10h]
0x18001805f  call    WPP_SF_d
0x180018064  nop
0x180018065  test    r15, r15
0x180018068  jz      loc_1800181E0
0x18001806e  mov     rcx, r15; Block
0x180018071  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018076  jmp     loc_1800181E0
0x18001807b  movzx   eax, word ptr [rsp+148h+pvarg]
0x180018083  cmp     eax, 8
0x180018086  jz      short loc_1800180D0
0x180018088  mov     rcx, cs:WPP_GLOBAL_Control
0x18001808f  cmp     rcx, r14
0x180018092  jz      short loc_1800180B3
0x180018094  test    byte ptr [rcx+1Ch], 1
0x180018098  jz      short loc_1800180B3
0x18001809a  mov     r9d, eax
0x18001809d  mov     edx, 2Eh ; '.'
0x1800180a2  lea     r8, WPP_93277130f4d6304520323beb48801075_Traceguids
0x1800180a9  mov     rcx, [rcx+10h]
0x1800180ad  call    WPP_SF_d
0x1800180b2  nop
0x1800180b3  test    r15, r15
0x1800180b6  jz      short loc_1800180C1
0x1800180b8  mov     rcx, r15; Block
0x1800180bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800180c0  nop
0x1800180c1  lea     rcx, [rsp+148h+var_100]
0x1800180c6  call    ??1?$AutoRef@UIEnumWbemClassObject@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(void)
0x1800180cb  jmp     loc_180017EAF
0x1800180d0  mov     [rsp+148h+var_E8], r13
0x1800180d5  mov     rdx, qword ptr [rsp+148h+pvarg+8]; unsigned __int16 **
0x1800180dd  lea     rcx, [rsp+148h+var_E8]; this
0x1800180e2  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x1800180e7  mov     r12d, eax
0x1800180ea  mov     r14, [rsp+148h+var_E8]
0x1800180ef  test    eax, eax
0x1800180f1  jns     short loc_18001810B
0x1800180f3  test    r14, r14
0x1800180f6  jz      short loc_180018108
0x1800180f8  mov     rcx, r14; Block
0x1800180fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018100  mov     r14, r13
0x180018103  mov     [rsp+148h+var_E8], r13
0x180018108  mov     r12d, r13d
0x18001810b  test    r15, r15
0x18001810e  jz      short loc_18001811C
0x180018110  mov     rcx, r15; this
0x180018113  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x180018118  test    eax, eax
0x18001811a  jns     short loc_18001812D
0x18001811c  test    r14, r14
0x18001811f  jz      short loc_180018158
0x180018121  mov     rcx, r14; this
0x180018124  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x180018129  test    eax, eax
0x18001812b  js      short loc_180018158
0x18001812d  test    r14, r14
0x180018130  jz      short loc_18001813B
0x180018132  mov     rcx, r14; Block
0x180018135  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001813a  nop
0x18001813b  test    r15, r15
0x18001813e  jz      short loc_180018149
0x180018140  mov     rcx, r15; Block
0x180018143  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018148  nop
0x180018149  lea     rcx, [rsp+148h+var_100]
0x18001814e  call    ??1?$AutoRef@UIEnumWbemClassObject@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IEnumWbemClassObject>::~AutoRef<IEnumWbemClassObject>(void)
0x180018153  jmp     loc_180017EA8
0x180018158  mov     rcx, [rsp+148h+var_100]
0x18001815d  mov     rax, [rcx]
0x180018160  mov     [rsp+148h+var_120], r13
0x180018165  mov     [rsp+148h+var_128], r13
  ... truncated ...
```
