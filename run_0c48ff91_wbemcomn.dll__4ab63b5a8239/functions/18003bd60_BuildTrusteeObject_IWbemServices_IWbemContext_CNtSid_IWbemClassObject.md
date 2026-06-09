# BuildTrusteeObject(IWbemServices *,IWbemContext *,CNtSid *,IWbemClassObject * *)

- ea: `0x18003bd60`
- end: `0x18003c6f0`
- name: `?BuildTrusteeObject@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAVCNtSid@@PEAPEAUIWbemClassObject@@@Z`
- size: `2448`
- prototype: `int(struct IWbemServices *, struct IWbemContext *, struct CNtSid *, struct IWbemClassObject **)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003ad34`
- `0x18003b580`

## callees

- `0x18000a290`
- `0x18000ab30`
- `0x180013564`
- `0x180014120`
- `0x18001bb20`
- `0x1800269d4`
- `0x180028484`
- `0x18002ee96`
- `0x18003a678`
- `0x18003a6b8`
- `0x18003ac1c`
- `0x18003ac40`
- `0x18003bd60`
- `0x18003e5a0`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c2c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c2c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c557`
- `OLEAUT32!__imp_VariantInit` at `0x18003bff2`
- `OLEAUT32!__imp_VariantInit` at `0x18003bff2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003bea0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003bea0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18003bf0d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003bf29`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003bf29`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003bfa0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003bfa0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003c13b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003c2b6`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003c13b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18003c2b6`

## string_xrefs

- `0x18003c49d`: `SIDLength`
- `0x18003c590`: `SIDString`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall BuildTrusteeObject(
        struct IWbemServices *a1,
        struct IWbemContext *a2,
        struct CNtSid *a3,
        struct IWbemClassObject **a4)
{
  int v6; // eax
  unsigned int v7; // edi
  int v9; // eax
  _QWORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r9
  SAFEARRAY *v13; // rax
  SAFEARRAY *v14; // rsi
  HRESULT v15; // eax
  _QWORD *v16; // r10
  __int64 v17; // rdx
  HRESULT v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  _QWORD *v24; // rax
  __int64 v25; // rdx
  WCHAR *v26; // rax
  __int64 v27; // r9
  __int64 v28; // rcx
  signed int LastError; // eax
  int v30; // eax
  _QWORD *v31; // r10
  int v32; // eax
  int v33; // eax
  int TextSid; // eax
  int v35; // eax
  struct IWbemClassObject *v36; // rax
  struct IWbemClassObject *v37; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR Name; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR v45; // [rsp+78h] [rbp-88h]
  __int64 v46; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v47; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v49[24]; // [rsp+A8h] [rbp-58h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v51[24]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v52[24]; // [rsp+E0h] [rbp-20h] BYREF
  void *ppvData; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v54[24]; // [rsp+108h] [rbp+8h] BYREF
  _OWORD v55[4]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v56[4]; // [rsp+160h] [rbp+60h] BYREF

  v42 = 0;
  v6 = ((__int64 (__fastcall *)(struct IWbemServices *, const wchar_t *, _QWORD, struct IWbemContext *, __int64 *, _QWORD))a1->lpVtbl->GetObjectA)(
         a1,
         L"__Trustee",
         0,
         a2,
         &v42,
         0);
  v7 = v6;
  if ( v6 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v6);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v7);
    }
    goto LABEL_6;
  }
  v37 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IWbemClassObject **))(*(_QWORD *)v42 + 120LL))(v42, 0, &v37);
  v7 = v9;
  if ( v9 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v9);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_97;
    }
    v11 = 18;
    v12 = v7;
    goto LABEL_17;
  }
  rgsabound.cElements = CNtSid::GetSize(a3);
  rgsabound.lLbound = 0;
  v13 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v14 = v13;
  if ( !v13 )
  {
    v7 = -2147217402;
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, -2147217402);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_97;
    }
    v11 = 19;
    v12 = 2147749894LL;
LABEL_17:
    WPP_SF_D(v10[2], v11, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v12);
LABEL_97:
    _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v37);
LABEL_6:
    _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v42);
    return v7;
  }
  MakeGuard<void * (*)(void *),unsigned short *>(v49, SafeArrayDestroy, v13);
  ppvData = 0;
  v15 = SafeArrayAccessData(v14, &ppvData);
  v7 = v15;
  if ( v15 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v15);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_96;
    }
    v17 = 20;
    goto LABEL_23;
  }
  memcpy_0(ppvData, *(const void **)a3, rgsabound.cElements);
  v18 = SafeArrayUnaccessData(v14);
  v7 = v18;
  if ( v18 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v18);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_96;
    }
    v17 = 21;
LABEL_23:
    WPP_SF_D(v16[2], v17, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v7);
LABEL_96:
    ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>(v49);
    goto LABEL_97;
  }
  VariantInit(&pvarg);
  pvarg.vt = 8209;
  pvarg.llVal = (LONGLONG)v14;
  v49[0] = 1;
  v19 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))v37->lpVtbl->Put)(
          v37,
          L"SID",
          0,
          &pvarg,
          0);
  v7 = v19;
  if ( v19 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v19);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v7);
    }
    goto LABEL_95;
  }
  peUse = SidTypeUnknown;
  Name = 0;
  cchName = 0;
  MakeGuard<void (*)(unsigned short *),RefHolder<unsigned short *>>(v52, v20, &Name);
  v56[0] = *(_OWORD *)L"Unknown Account";
  v56[1] = *(_OWORD *)L"Account";
  memset(&v56[2], 0, 32);
  ReferencedDomainName = 0;
  cchReferencedDomainName = 0;
  MakeGuard<void (*)(unsigned short *),RefHolder<unsigned short *>>(v51, v21, &ReferencedDomainName);
  v55[0] = *(_OWORD *)L"Unknown Domain";
  *(_OWORD *)((char *)v55 + 14) = *(_OWORD *)L" Domain";
  memset((char *)&v55[1] + 14, 0, 34);
  if ( LookupAccountSidLocalW(*(PSID *)a3, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, -2147217379);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v23 = 27;
    goto LABEL_103;
  }
  if ( GetLastError() == 122 )
  {
    if ( cchName )
    {
      Name = (LPWSTR)CWin32DefaultArena::WbemMemAlloc(saturated_mul(cchName, 2u));
      if ( !Name )
      {
        v7 = -2147217402;
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, -2147217402);
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_94;
        }
        v25 = 24;
        goto LABEL_52;
      }
    }
    if ( cchReferencedDomainName )
    {
      v26 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(cchReferencedDomainName, 2u));
      ReferencedDomainName = v26;
      if ( !v26 )
      {
        v7 = -2147217402;
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, -2147217402);
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_94;
        }
        v25 = 25;
LABEL_52:
        v27 = 2147749894LL;
LABEL_53:
        v28 = v24[2];
        goto LABEL_54;
      }
    }
    else
    {
      v26 = ReferencedDomainName;
    }
    if ( !LookupAccountSidLocalW(*(PSID *)a3, Name, &cchName, v26, &cchReferencedDomainName, &peUse) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError != 1332 )
      {
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( (v7 & 0x80000000) != 0 )
          CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v7);
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_94;
        }
        v25 = 26;
        v27 = v7;
        goto LABEL_53;
      }
      CMUILocale::_Free(Name);
      v52[0] = 1;
      Name = (LPWSTR)v56;
      CMUILocale::_Free(ReferencedDomainName);
      v51[0] = 1;
      ReferencedDomainName = (LPWSTR)v55;
    }
    v46 = 0;
    v44 = 8;
    v45 = Name;
    v30 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, __int64 *, _DWORD))v37->lpVtbl->Put)(
            v37,
            L"Name",
            0,
            &v44,
            0);
    v7 = v30;
    if ( v30 >= 0 )
    {
      v45 = ReferencedDomainName;
      v32 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, __int64 *, _DWORD))v37->lpVtbl->Put)(
              v37,
              L"Domain",
              0,
              &v44,
              0);
      v7 = v32;
      if ( v32 >= 0 )
      {
        LOWORD(v44) = 3;
        LODWORD(v45) = CNtSid::GetSize(a3);
        v33 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, __int64 *, _DWORD))v37->lpVtbl->Put)(
                v37,
                L"SIDLength",
                0,
                &v44,
                0);
        v7 = v33;
        if ( v33 >= 0 )
        {
          v47 = 0;
          TextSid = CNtSid::GetTextSid(a3, &v47);
          v7 = TextSid;
          if ( TextSid >= 0 )
          {
            MakeGuard<void * (*)(void *),unsigned short *>(v54, LocalFree, v47);
            LOWORD(v44) = 8;
            v45 = v47;
            v35 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, __int64 *, _DWORD))v37->lpVtbl->Put)(
                    v37,
                    L"SIDString",
                    0,
                    &v44,
                    0);
            v7 = v35;
            if ( v35 >= 0 )
            {
              v36 = v37;
              v37 = 0;
              *a4 = v36;
            }
            else
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v35);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v7);
              }
            }
            ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>(v54);
            goto LABEL_94;
          }
          CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, TextSid);
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_94:
            ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>(v51);
            ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>(v52);
LABEL_95:
            _variant_t::~_variant_t((_variant_t *)&pvarg);
            goto LABEL_96;
          }
          v25 = 31;
        }
        else
        {
          CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v33);
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_94;
          }
          v25 = 30;
        }
      }
      else
      {
        CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v32);
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_94;
        }
        v25 = 29;
      }
    }
    else
    {
      CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v30);
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_94;
      }
      v25 = 28;
    }
    v27 = v7;
    v28 = v31[2];
LABEL_54:
    WPP_SF_D(v28, v25, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v27);
    goto LABEL_94;
  }
  CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, -2147217379);
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_104;
  }
  v23 = 23;
LABEL_103:
  WPP_SF_D(v22[2], v23, &WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749917LL);
LABEL_104:
  ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>(v51);
  ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>(v52);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>(v49);
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v37);
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v42);
  return 2147749917LL;
}

```

## disassembly

```asm
0x18003bd60  push    rbp
0x18003bd62  push    rsi
0x18003bd63  push    rdi
0x18003bd64  push    r12
0x18003bd66  push    r14
0x18003bd68  push    r15
0x18003bd6a  lea     rbp, [rsp-0B8h]
0x18003bd72  sub     rsp, 1B8h
0x18003bd79  mov     rax, cs:__security_cookie
0x18003bd80  xor     rax, rsp
0x18003bd83  mov     [rbp+0E0h+var_40], rax
0x18003bd8a  mov     r15, r9
0x18003bd8d  mov     r14, r8
0x18003bd90  xor     r12d, r12d
0x18003bd93  mov     [rsp+1E0h+var_180], r12
0x18003bd98  mov     rax, [rcx]
0x18003bd9b  mov     [rsp+1E0h+peUse], r12
0x18003bda0  lea     r8, [rsp+1E0h+var_180]
0x18003bda5  mov     [rsp+1E0h+cchReferencedDomainName], r8
0x18003bdaa  mov     r9, rdx
0x18003bdad  xor     r8d, r8d
0x18003bdb0  lea     rdx, aTrustee; "__Trustee"
0x18003bdb7  mov     rax, [rax+30h]
0x18003bdbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdc0  mov     edi, eax
0x18003bdc2  test    eax, eax
0x18003bdc4  jns     short loc_18003BE1F
0x18003bdc6  mov     edx, eax; int
0x18003bdc8  lea     rcx, unk_18006A9C0; this
0x18003bdcf  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003bdd4  lea     rcx, WPP_GLOBAL_Control
0x18003bddb  mov     r10, cs:WPP_GLOBAL_Control
0x18003bde2  cmp     r10, rcx
0x18003bde5  jz      short loc_18003BE0E
0x18003bde7  test    byte ptr [r10+1Ch], 1
0x18003bdec  jz      short loc_18003BE0E
0x18003bdee  cmp     byte ptr [r10+19h], 2
0x18003bdf3  jb      short loc_18003BE0E
0x18003bdf5  lea     edx, [r12+11h]
0x18003bdfa  mov     r9d, edi
0x18003bdfd  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003be04  mov     rcx, [r10+10h]
0x18003be08  call    WPP_SF_D
0x18003be0d  nop
0x18003be0e  lea     rcx, [rsp+1E0h+var_180]
0x18003be13  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003be18  mov     eax, edi
0x18003be1a  jmp     loc_18003C6D0
0x18003be1f  mov     [rsp+1E0h+var_1A0], r12
0x18003be24  mov     rcx, [rsp+1E0h+var_180]
0x18003be29  mov     rax, [rcx]
0x18003be2c  lea     r8, [rsp+1E0h+var_1A0]
0x18003be31  xor     edx, edx
0x18003be33  mov     rax, [rax+78h]
0x18003be37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be3c  mov     edi, eax
0x18003be3e  test    eax, eax
0x18003be40  jns     short loc_18003BE85
0x18003be42  mov     edx, eax; int
0x18003be44  lea     rcx, unk_18006A9C0; this
0x18003be4b  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003be50  lea     rcx, WPP_GLOBAL_Control
0x18003be57  mov     rax, cs:WPP_GLOBAL_Control
0x18003be5e  cmp     rax, rcx
0x18003be61  jz      loc_18003C624
0x18003be67  test    byte ptr [rax+1Ch], 1
0x18003be6b  jz      loc_18003C624
0x18003be71  cmp     byte ptr [rax+19h], 2
0x18003be75  jb      loc_18003C624
0x18003be7b  mov     edx, 12h
0x18003be80  mov     r9d, edi
0x18003be83  jmp     short loc_18003BEF5
0x18003be85  mov     rcx, r14; this
0x18003be88  call    ?GetSize@CNtSid@@QEAAKXZ; CNtSid::GetSize(void)
0x18003be8d  mov     [rbp+0E0h+rgsabound.cElements], eax
0x18003be90  mov     [rbp+0E0h+rgsabound.lLbound], r12d
0x18003be94  mov     ecx, 11h; vt
0x18003be99  lea     r8, [rbp+0E0h+rgsabound]; rgsabound
0x18003be9d  lea     edx, [rcx-10h]; cDims
0x18003bea0  call    cs:__imp_SafeArrayCreate
0x18003bea6  mov     rsi, rax
0x18003bea9  test    rax, rax
0x18003beac  jnz     short loc_18003BF0A
0x18003beae  mov     edi, 80041006h
0x18003beb3  mov     edx, edi; int
0x18003beb5  lea     rcx, unk_18006A9C0; this
0x18003bebc  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003bec1  lea     rcx, WPP_GLOBAL_Control
0x18003bec8  mov     rax, cs:WPP_GLOBAL_Control
0x18003becf  cmp     rax, rcx
0x18003bed2  jz      loc_18003C624
0x18003bed8  test    byte ptr [rax+1Ch], 1
0x18003bedc  jz      loc_18003C624
0x18003bee2  cmp     byte ptr [rax+19h], 2
0x18003bee6  jb      loc_18003C624
0x18003beec  lea     edx, [rsi+13h]
0x18003beef  mov     r9d, 80041006h
0x18003bef5  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003befc  mov     rcx, [rax+10h]
0x18003bf00  call    WPP_SF_D
0x18003bf05  jmp     loc_18003C624
0x18003bf0a  mov     r8, rsi
0x18003bf0d  mov     rdx, cs:__imp_SafeArrayDestroy
0x18003bf14  lea     rcx, [rbp+0E0h+var_138]
0x18003bf18  call    ??$MakeGuard@P6APEAXPEAX@ZPEAG@@YA?AV?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@@P6APEAXPEAX@ZPEAG@Z; MakeGuard<void * (*)(void *),ushort *>(void * (*)(void *),ushort *)
0x18003bf1d  nop
0x18003bf1e  mov     [rbp+0E0h+ppvData], r12
0x18003bf22  lea     rdx, [rbp+0E0h+ppvData]; ppvData
0x18003bf26  mov     rcx, rsi; psa
0x18003bf29  call    cs:__imp_SafeArrayAccessData
0x18003bf2f  mov     edi, eax
0x18003bf31  test    eax, eax
0x18003bf33  jns     short loc_18003BF8D
0x18003bf35  mov     edx, eax; int
0x18003bf37  lea     rcx, unk_18006A9C0; this
0x18003bf3e  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003bf43  lea     rcx, WPP_GLOBAL_Control
0x18003bf4a  mov     r10, cs:WPP_GLOBAL_Control
0x18003bf51  cmp     r10, rcx
0x18003bf54  jz      loc_18003C61A
0x18003bf5a  test    byte ptr [r10+1Ch], 1
0x18003bf5f  jz      loc_18003C61A
0x18003bf65  cmp     byte ptr [r10+19h], 2
0x18003bf6a  jb      loc_18003C61A
0x18003bf70  mov     edx, 14h
0x18003bf75  mov     r9d, edi
0x18003bf78  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003bf7f  mov     rcx, [r10+10h]
0x18003bf83  call    WPP_SF_D
0x18003bf88  jmp     loc_18003C61A
0x18003bf8d  mov     r8d, [rbp+0E0h+rgsabound.cElements]; Size
0x18003bf91  mov     rdx, [r14]; Src
0x18003bf94  mov     rcx, [rbp+0E0h+ppvData]; void *
0x18003bf98  call    memcpy_0
0x18003bf9d  mov     rcx, rsi; psa
0x18003bfa0  call    cs:__imp_SafeArrayUnaccessData
0x18003bfa6  mov     edi, eax
0x18003bfa8  test    eax, eax
0x18003bfaa  jns     short loc_18003BFEE
0x18003bfac  mov     edx, eax; int
0x18003bfae  lea     rcx, unk_18006A9C0; this
0x18003bfb5  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003bfba  lea     rcx, WPP_GLOBAL_Control
0x18003bfc1  mov     r10, cs:WPP_GLOBAL_Control
0x18003bfc8  cmp     r10, rcx
0x18003bfcb  jz      loc_18003C61A
0x18003bfd1  test    byte ptr [r10+1Ch], 1
0x18003bfd6  jz      loc_18003C61A
0x18003bfdc  cmp     byte ptr [r10+19h], 2
0x18003bfe1  jb      loc_18003C61A
0x18003bfe7  mov     edx, 15h
0x18003bfec  jmp     short loc_18003BF75
0x18003bfee  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x18003bff2  call    cs:__imp_VariantInit
0x18003bff8  nop
0x18003bff9  mov     eax, 2011h
0x18003bffe  mov     word ptr [rbp+0E0h+pvarg], ax
0x18003c002  mov     qword ptr [rbp+0E0h+pvarg+8], rsi
0x18003c006  mov     [rbp+0E0h+var_138], 1
0x18003c00a  mov     rcx, [rsp+1E0h+var_1A0]
0x18003c00f  mov     rax, [rcx]
0x18003c012  mov     dword ptr [rsp+1E0h+cchReferencedDomainName], r12d
0x18003c017  lea     r9, [rbp+0E0h+pvarg]
0x18003c01b  xor     r8d, r8d
0x18003c01e  lea     rdx, aSid; "SID"
0x18003c025  mov     rax, [rax+28h]
0x18003c029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c02e  mov     edi, eax
0x18003c030  test    eax, eax
0x18003c032  jns     short loc_18003C08C
0x18003c034  mov     edx, eax; int
0x18003c036  lea     rcx, unk_18006A9C0; this
0x18003c03d  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c042  lea     rcx, WPP_GLOBAL_Control
0x18003c049  mov     r10, cs:WPP_GLOBAL_Control
0x18003c050  cmp     r10, rcx
0x18003c053  jz      loc_18003C610
0x18003c059  test    byte ptr [r10+1Ch], 1
0x18003c05e  jz      loc_18003C610
0x18003c064  cmp     byte ptr [r10+19h], 2
0x18003c069  jb      loc_18003C610
0x18003c06f  mov     edx, 16h
0x18003c074  mov     r9d, edi
0x18003c077  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003c07e  mov     rcx, [r10+10h]
0x18003c082  call    WPP_SF_D
0x18003c087  jmp     loc_18003C610
0x18003c08c  mov     esi, 8
0x18003c091  mov     [rsp+1E0h+var_178], esi
0x18003c095  mov     [rsp+1E0h+Name], r12
0x18003c09a  mov     [rsp+1E0h+cchName], r12d
0x18003c09f  lea     r8, [rsp+1E0h+Name]
0x18003c0a4  lea     rcx, [rbp+0E0h+var_100]
0x18003c0a8  call    ??$MakeGuard@P6AXPEAG@ZV?$RefHolder@PEAG@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAG@ZV?$RefHolder@PEAG@@@@P6AXPEAG@ZV?$RefHolder@PEAG@@@Z; MakeGuard<void (*)(ushort *),RefHolder<ushort *>>(void (*)(ushort *),RefHolder<ushort *>)
0x18003c0ad  nop
0x18003c0ae  movups  xmm0, xmmword ptr cs:aUnknownAccount; "Unknown Account"
0x18003c0b5  movaps  [rbp+0E0h+var_80], xmm0
0x18003c0b9  movups  xmm1, xmmword ptr cs:aUnknownAccount+10h; "Account"
0x18003c0c0  movaps  [rbp+0E0h+var_70], xmm1
0x18003c0c4  xorps   xmm0, xmm0
0x18003c0c7  movups  [rbp+0E0h+var_60], xmm0
0x18003c0ce  movups  [rbp+0E0h+var_50], xmm0
0x18003c0d5  mov     [rsp+1E0h+ReferencedDomainName], r12
0x18003c0da  mov     [rsp+1E0h+var_188], r12d
0x18003c0df  lea     r8, [rsp+1E0h+ReferencedDomainName]
0x18003c0e4  lea     rcx, [rbp+0E0h+var_118]
0x18003c0e8  call    ??$MakeGuard@P6AXPEAG@ZV?$RefHolder@PEAG@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAG@ZV?$RefHolder@PEAG@@@@P6AXPEAG@ZV?$RefHolder@PEAG@@@Z; MakeGuard<void (*)(ushort *),RefHolder<ushort *>>(void (*)(ushort *),RefHolder<ushort *>)
0x18003c0ed  nop
0x18003c0ee  movups  xmm0, xmmword ptr cs:aUnknownDomain; "Unknown Domain"
0x18003c0f5  movaps  xmmword ptr [rbp+0E0h+var_C0], xmm0
0x18003c0f9  movups  xmm1, xmmword ptr cs:aUnknownDomain+0Eh; " Domain"
0x18003c100  movups  xmmword ptr [rbp+0E0h+var_C0+0Eh], xmm1
0x18003c104  xorps   xmm0, xmm0
0x18003c107  xor     eax, eax
0x18003c109  movups  [rbp+0E0h+var_A2], xmm0
0x18003c10d  movups  [rbp+0E0h+var_92], xmm0
0x18003c111  mov     [rbp+0E0h+var_82], ax
0x18003c115  lea     rax, [rsp+1E0h+var_178]
0x18003c11a  mov     [rsp+1E0h+peUse], rax; peUse
0x18003c11f  lea     rax, [rsp+1E0h+var_188]
0x18003c124  mov     [rsp+1E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003c129  mov     r9, [rsp+1E0h+ReferencedDomainName]; ReferencedDomainName
0x18003c12e  lea     r8, [rsp+1E0h+cchName]; cchName
0x18003c133  mov     rdx, [rsp+1E0h+Name]; Name
0x18003c138  mov     rcx, [r14]; Sid
0x18003c13b  call    cs:__imp_LookupAccountSidLocalW
0x18003c141  test    eax, eax
0x18003c143  jnz     loc_18003C642
0x18003c149  call    cs:__imp_GetLastError
0x18003c14f  cmp     eax, 7Ah ; 'z'
0x18003c152  jz      short loc_18003C198
0x18003c154  mov     edx, 8004101Dh; int
0x18003c159  lea     rcx, unk_18006A9C0; this
0x18003c160  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c165  lea     rcx, WPP_GLOBAL_Control
0x18003c16c  mov     rax, cs:WPP_GLOBAL_Control
0x18003c173  cmp     rax, rcx
0x18003c176  jz      loc_18003C68E
0x18003c17c  test    byte ptr [rax+1Ch], 1
0x18003c180  jz      loc_18003C68E
0x18003c186  cmp     byte ptr [rax+19h], 2
0x18003c18a  jb      loc_18003C68E
0x18003c190  lea     edx, [rsi+0Fh]
0x18003c193  jmp     loc_18003C677
0x18003c198  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003c19c  mov     eax, [rsp+1E0h+cchName]
0x18003c1a0  test    eax, eax
0x18003c1a2  jz      short loc_18003C207
0x18003c1a4  mov     ecx, eax
0x18003c1a6  lea     eax, [rdi+3]
0x18003c1a9  mul     rcx
0x18003c1ac  cmovb   rax, rdi
0x18003c1b0  mov     rcx, rax; unsigned __int64
0x18003c1b3  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003c1b8  mov     [rsp+1E0h+Name], rax
0x18003c1bd  test    rax, rax
0x18003c1c0  jnz     short loc_18003C207
0x18003c1c2  mov     edi, 80041006h
0x18003c1c7  mov     edx, edi; int
0x18003c1c9  lea     rcx, unk_18006A9C0; this
0x18003c1d0  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c1d5  lea     rcx, WPP_GLOBAL_Control
0x18003c1dc  mov     rax, cs:WPP_GLOBAL_Control
0x18003c1e3  cmp     rax, rcx
0x18003c1e6  jz      loc_18003C5FC
0x18003c1ec  test    byte ptr [rax+1Ch], 1
0x18003c1f0  jz      loc_18003C5FC
0x18003c1f6  cmp     byte ptr [rax+19h], 2
0x18003c1fa  jb      loc_18003C5FC
0x18003c200  mov     edx, 18h
0x18003c205  jmp     short loc_18003C272
0x18003c207  mov     eax, [rsp+1E0h+var_188]
0x18003c20b  test    eax, eax
0x18003c20d  jz      short loc_18003C28D
0x18003c20f  mov     ecx, eax
0x18003c211  mov     eax, 2
0x18003c216  mul     rcx
0x18003c219  cmovb   rax, rdi
0x18003c21d  mov     rcx, rax; unsigned __int64
0x18003c220  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003c225  mov     [rsp+1E0h+ReferencedDomainName], rax
0x18003c22a  test    rax, rax
0x18003c22d  jnz     short loc_18003C292
0x18003c22f  mov     edi, 80041006h
0x18003c234  mov     edx, edi; int
0x18003c236  lea     rcx, unk_18006A9C0; this
0x18003c23d  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c242  lea     rcx, WPP_GLOBAL_Control
0x18003c249  mov     rax, cs:WPP_GLOBAL_Control
0x18003c250  cmp     rax, rcx
0x18003c253  jz      loc_18003C5FC
0x18003c259  test    byte ptr [rax+1Ch], 1
0x18003c25d  jz      loc_18003C5FC
0x18003c263  cmp     byte ptr [rax+19h], 2
0x18003c267  jb      loc_18003C5FC
0x18003c26d  mov     edx, 19h
0x18003c272  mov     r9d, 80041006h
0x18003c278  mov     rcx, [rax+10h]
0x18003c27c  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003c283  call    WPP_SF_D
  ... truncated ...
```
