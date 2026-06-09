# GetSecurityDescriptorFromParameters(CNtSecurityDescriptor *,IWbemClassObject *,bool *,CNtSecurityDescriptor * *,ulong *)

- ea: `0x18003d310`
- end: `0x18003df5a`
- name: `?GetSecurityDescriptorFromParameters@@YAJPEAVCNtSecurityDescriptor@@PEAUIWbemClassObject@@PEA_NPEAPEAV1@PEAK@Z`
- size: `3146`
- prototype: `__int64 __fastcall(struct CNtSecurityDescriptor *, struct IWbemClassObject *, bool *, struct CNtSecurityDescriptor **, unsigned int *)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a290`
- `0x180013564`
- `0x180014120`
- `0x18001a730`
- `0x18001c010`
- `0x18001d19c`
- `0x180023800`
- `0x180023a60`
- `0x180025aa0`
- `0x180025e00`
- `0x1800269d4`
- `0x180028484`
- `0x18002cc00`
- `0x18003a790`
- `0x18003ac1c`
- `0x18003ad10`
- `0x18003c6f8`
- `0x18003d310`
- `0x18003e7c4`
- `0x18003eff4`
- `0x18003f9b0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003de56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003de56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003de17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003de17`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003de2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003de2d`
- `OLEAUT32!__imp_VariantInit` at `0x18003d343`
- `OLEAUT32!__imp_VariantInit` at `0x18003d343`

## string_xrefs

- `0x18003d35f`: `Descriptor`
- `0x18003de1f`: `SetSecurityDescriptorControl`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GetSecurityDescriptorFromParameters(
        struct CNtSecurityDescriptor *a1,
        struct IWbemClassObject *a2,
        bool *a3,
        struct CNtSecurityDescriptor **a4,
        unsigned int *a5)
{
  char v7; // r14
  signed int v8; // eax
  unsigned int v9; // ebx
  HRESULT (__stdcall *QueryInterface)(IRecordInfo *, const IID *const, void **); // rbx
  _QWORD *v11; // rax
  __int64 v12; // rdx
  struct IErrorInfo *v13; // rdx
  __int64 v14; // rax
  bool v15; // r8
  bool v16; // cl
  __int16 v17; // di
  struct IErrorInfo *v18; // rdx
  __int64 v19; // rax
  char v20; // r12
  HRESULT (__stdcall *v21)(IRecordInfo *, const IID *const, void **); // rbx
  _QWORD *v22; // r10
  __int64 v23; // rdx
  signed int v24; // eax
  struct IErrorInfo *v25; // rdx
  __int64 v26; // rax
  unsigned int v27; // edx
  char v28; // si
  HRESULT (__stdcall *v29)(IRecordInfo *, const IID *const, void **); // rbx
  _QWORD *v30; // r10
  __int64 v31; // rdx
  unsigned int v32; // edx
  signed int v33; // eax
  struct IErrorInfo *v34; // rdx
  __int64 v35; // rax
  unsigned int v36; // edx
  char v37; // r15
  signed int v38; // eax
  unsigned int v39; // edx
  struct IErrorInfo *v40; // rdx
  __int64 v41; // rax
  unsigned int v42; // edx
  signed int v43; // eax
  unsigned int v44; // edx
  CNtSecurityDescriptor *v45; // rax
  __int64 v46; // rdx
  CNtSecurityDescriptor *v47; // rbx
  unsigned int v48; // edx
  _QWORD *v49; // rax
  __int64 v50; // rdx
  unsigned int v51; // edx
  bool v52; // al
  __int64 v53; // r14
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax
  signed int LastError; // eax
  int v57; // eax
  unsigned int v58; // edx
  unsigned int v59; // edx
  unsigned int v60; // edx
  unsigned int v61; // edx
  __int64 v63; // [rsp+48h] [rbp-A1h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-99h] BYREF
  IRecordInfo *v65; // [rsp+68h] [rbp-81h]
  CNtSid *v66; // [rsp+70h] [rbp-79h] BYREF
  struct IWbemClassObject *v67; // [rsp+78h] [rbp-71h] BYREF
  struct IWbemClassObject *v68; // [rsp+80h] [rbp-69h] BYREF
  CNtAcl *v69; // [rsp+88h] [rbp-61h] BYREF
  CNtAcl *v70; // [rsp+90h] [rbp-59h] BYREF
  struct CNtSid *v71; // [rsp+98h] [rbp-51h] BYREF
  struct CNtSid *v72; // [rsp+A0h] [rbp-49h] BYREF
  struct CNtAcl *v73; // [rsp+A8h] [rbp-41h] BYREF
  struct CNtAcl *v74; // [rsp+B0h] [rbp-39h] BYREF
  struct tagVARIANT v75; // [rsp+C8h] [rbp-21h] BYREF
  _BYTE v76[24]; // [rsp+E8h] [rbp-1h] BYREF
  CNtSecurityDescriptor *v77; // [rsp+100h] [rbp+17h]
  __int16 v78; // [rsp+150h] [rbp+67h]

  v7 = 0;
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  v8 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, ULONG *, _QWORD, _QWORD))a2->lpVtbl->Get)(
         a2,
         L"Descriptor",
         0,
         &pvarg.decVal.Lo32,
         0,
         0);
  v9 = v8;
  if ( v8 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v8);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
    }
    goto LABEL_167;
  }
  if ( pvarg.iVal != 13 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749896LL);
    }
    goto LABEL_11;
  }
  v63 = 0;
  QueryInterface = pvarg.pRecInfo->lpVtbl->QueryInterface;
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v63);
  v63 = 0;
  if ( ((int (__fastcall *)(IRecordInfo *, GUID *, __int64 *))QueryInterface)(
         pvarg.pRecInfo,
         &IID_IWbemClassObject,
         &v63) < 0 )
  {
    _variant_t::Clear((_variant_t *)&pvarg.decVal.8);
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v12 = 107;
    goto LABEL_42;
  }
  _variant_t::Clear((_variant_t *)&pvarg.decVal.8);
  v14 = _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(
          &v63,
          v13);
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, CY *, _QWORD, _QWORD))(*(_QWORD *)v14 + 32LL))(
         v14,
         L"ControlFlags",
         0,
         &pvarg.cyVal,
         0,
         0) < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v12 = 108;
    goto LABEL_42;
  }
  if ( pvarg.iVal != 3 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v12 = 109;
    goto LABEL_42;
  }
  v78 = *((_WORD *)&pvarg.decVal + 8);
  v15 = 0;
  if ( (*(_WORD *)(&pvarg.decVal + 1) & 0x2000) == 0 )
    v15 = (*(_WORD *)(&pvarg.decVal + 1) & 0x800) != 0;
  v16 = 0;
  if ( (*(_WORD *)(&pvarg.decVal + 1) & 0x1000) == 0 )
    v16 = (*(_WORD *)(&pvarg.decVal + 1) & 0x400) != 0;
  if ( v16 )
  {
    if ( v15 )
      v17 = 16128;
    else
      v17 = 14080;
  }
  else
  {
    v17 = 13056;
    if ( v15 )
      v17 = 15104;
  }
  v72 = 0;
  _variant_t::Clear((_variant_t *)&pvarg.decVal.8);
  v19 = _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(
          &v63,
          v18);
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, CY *, _QWORD, _QWORD))(*(_QWORD *)v19 + 32LL))(
         v19,
         L"Group",
         0,
         &pvarg.cyVal,
         0,
         0) < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v12 = 110;
LABEL_42:
    WPP_SF_D(v11[2], v12, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749896LL);
LABEL_43:
    _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v63);
LABEL_11:
    v9 = -2147217400;
    goto LABEL_167;
  }
  if ( pvarg.iVal != 13 )
  {
    v20 = 0;
    goto LABEL_60;
  }
  v67 = 0;
  v21 = pvarg.pRecInfo->lpVtbl->QueryInterface;
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v67);
  v67 = 0;
  v9 = ((__int64 (__fastcall *)(IRecordInfo *, GUID *, struct IWbemClassObject **))v21)(
         pvarg.pRecInfo,
         &IID_IWbemClassObject,
         &v67);
  if ( (v9 & 0x80000000) != 0 )
  {
    _variant_t::Clear((_variant_t *)&pvarg.decVal.8);
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v9);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_52;
    }
    v23 = 111;
LABEL_51:
    WPP_SF_D(v22[2], v23, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
LABEL_52:
    _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v67);
LABEL_53:
    _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v63);
    goto LABEL_167;
  }
  _variant_t::Clear((_variant_t *)&pvarg.decVal.8);
  v24 = LoadSIDFromTrustee(v67, &v72);
  v9 = v24;
  if ( v24 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v24);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_52;
    }
    v23 = 112;
    goto LABEL_51;
  }
  v20 = 1;
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v67);
LABEL_60:
  *(_QWORD *)&pvarg.vt = v72;
  v71 = 0;
  _variant_t::Clear((_variant_t *)&pvarg.decVal.8);
  v26 = _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(
          &v63,
          v25);
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, CY *, _QWORD, _QWORD))(*(_QWORD *)v26 + 32LL))(
         v26,
         L"Owner",
         0,
         &pvarg.cyVal,
         0,
         0) < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749896LL);
    }
    goto LABEL_65;
  }
  if ( pvarg.iVal != 13 )
  {
    v28 = 0;
    goto LABEL_82;
  }
  v68 = 0;
  v29 = pvarg.pRecInfo->lpVtbl->QueryInterface;
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v68);
  v68 = 0;
  v9 = ((__int64 (__fastcall *)(IRecordInfo *, GUID *, struct IWbemClassObject **))v29)(
         pvarg.pRecInfo,
         &IID_IWbemClassObject,
         &v68);
  if ( (v9 & 0x80000000) != 0 )
  {
    _variant_t::Clear((_variant_t *)&pvarg.decVal.8);
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v9);
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v31 = 114;
LABEL_73:
    WPP_SF_D(v30[2], v31, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
LABEL_74:
    _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v68);
LABEL_75:
    CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>((CNtSid **)&pvarg, v32);
    goto LABEL_53;
  }
  _variant_t::Clear((_variant_t *)&pvarg.decVal.8);
  v33 = LoadSIDFromTrustee(v68, &v71);
  v9 = v33;
  if ( v33 < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v33);
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v31 = 115;
    goto LABEL_73;
  }
  v28 = 1;
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&v68);
LABEL_82:
  v66 = v71;
  v73 = 0;
  _variant_t::Clear((_variant_t *)&pvarg.decVal.8);
  v35 = _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(
          &v63,
          v34);
  if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, CY *, _QWORD, _QWORD))(*(_QWORD *)v35 + 32LL))(
         v35,
         L"DACL",
         0,
         &pvarg.cyVal,
         0,
         0) < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749896LL);
    }
    goto LABEL_87;
  }
  if ( pvarg.iVal == 8205 )
  {
    v37 = 1;
    *(_OWORD *)&v75.vt = *(_OWORD *)&pvarg.decVal.Lo32;
    v75.pRecInfo = v65;
    v38 = LoadACLFromACEArrayVar(&v75, &v73);
    v9 = v38;
    if ( v38 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v38);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
      }
      goto LABEL_95;
    }
  }
  else
  {
    v37 = 0;
  }
  v69 = v73;
  v74 = 0;
  _variant_t::Clear((_variant_t *)&pvarg.decVal.8);
  v41 = _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(
          &v63,
          v40);
  if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, CY *, _QWORD, _QWORD))(*(_QWORD *)v41 + 32LL))(
         v41,
         L"SACL",
         0,
         &pvarg.cyVal,
         0,
         0) < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749896LL);
    }
    goto LABEL_101;
  }
  if ( pvarg.iVal == 8205 )
  {
    v7 = 1;
    *(_OWORD *)&v75.vt = *(_OWORD *)&pvarg.decVal.Lo32;
    v75.pRecInfo = v65;
    v43 = LoadACLFromACEArrayVar(&v75, &v74);
    v9 = v43;
    if ( v43 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v43);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
      }
      goto LABEL_108;
    }
  }
  v70 = v74;
  v45 = (CNtSecurityDescriptor *)CWin32DefaultArena::WbemMemAlloc(0x10u);
  v77 = v45;
  if ( v45 )
    v47 = CNtSecurityDescriptor::CNtSecurityDescriptor(v45);
  else
    v47 = 0;
  if ( !v47 )
  {
    v9 = -2147217402;
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041006);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749894LL);
    }
LABEL_117:
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v70, v48);
LABEL_108:
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v69, v44);
LABEL_95:
    CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v66, v39);
    goto LABEL_75;
  }
  if ( a1 )
    CNtSecurityDescriptor::operator=((__int64)v47, (__int64)a1);
  MakeGuard<void (*)(CNtSecurityDescriptor const *),CNtSecurityDescriptor *>((__int64)v76, v46, (__int64)v47);
  if ( v28 && !(unsigned int)CNtSecurityDescriptor::SetOwner(v47, v71) )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_145;
    }
    v50 = 121;
LABEL_144:
    WPP_SF_D(v49[2], v50, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749896LL);
LABEL_145:
    ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>((__int64)v76);
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v70, v51);
LABEL_101:
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v69, v42);
LABEL_87:
    CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v66, v36);
LABEL_65:
    CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>((CNtSid **)&pvarg, v27);
    goto LABEL_43;
  }
  if ( v20 && !(unsigned int)CNtSecurityDescriptor::SetGroup(v47, v72) )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_145;
    }
    v50 = 122;
    goto LABEL_144;
  }
  if ( v37 && !(unsigned int)CNtSecurityDescriptor::SetDacl(v47, v73) )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_145;
    }
    v50 = 123;
    goto LABEL_144;
  }
  if ( v7 )
  {
    if ( !(unsigned int)CNtSecurityDescriptor::SetSacl(v47, v74) )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
      v49 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_145;
      }
      v50 = 124;
      goto LABEL_144;
    }
    v52 = 1;
  }
  else
  {
    v52 = 0;
  }
  *a3 = v52;
  v53 = *(_QWORD *)v47;
  ProcAddress = (FARPROC)qword_180070360;
  if ( !qword_180070360 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
LABEL_153:
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (v9 & 0x80000000) != 0 )
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v9);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v9);
      }
      ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>((__int64)v76);
      goto LABEL_117;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "SetSecurityDescriptorControl");
    qword_180070360 = (__int64)ProcAddress;
    if ( !ProcAddress )
      goto LABEL_153;
  }
  if ( !((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD))ProcAddress)(
          v53,
          (unsigned __int16)(v78 & v17),
          (unsigned __int16)(v78 & v17)) )
    goto LABEL_153;
  *a5 = 0;
  v57 = 0;
  if ( v28 )
  {
    *a5 = 1;
    v57 = 1;
  }
  if ( v20 )
    *a5 = v57 | 2;
  *a4 = v47;
  v76[0] = 1;
  ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>((__int64)v76);
  CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v70, v58);
  CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v69, v59);
  CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v66, v60);
  CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>((CNtSid **)&pvarg, v61);
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v63);
  v9 = 0;
LABEL_167:
  _variant_t::~_variant_t((VARIANTARG *)&pvarg.decVal.8);
  return v9;
}

```

## disassembly

```asm
0x18003d310  mov     rax, rsp
0x18003d313  mov     [rax+8], rbx
0x18003d317  mov     [rax+20h], r9
0x18003d31b  mov     [rax+18h], r8
0x18003d31f  push    rbp
0x18003d320  push    rsi
0x18003d321  push    rdi
0x18003d322  push    r12
0x18003d324  push    r13
0x18003d326  push    r14
0x18003d328  push    r15
0x18003d32a  lea     rbp, [rax-57h]
0x18003d32e  sub     rsp, 100h
0x18003d335  mov     rbx, rdx
0x18003d338  mov     r13, rcx
0x18003d33b  xor     r14d, r14d
0x18003d33e  lea     rcx, [rsp+130h+pvarg+8]; pvarg
0x18003d343  call    cs:__imp_VariantInit
0x18003d349  nop
0x18003d34a  mov     rax, [rbx]
0x18003d34d  mov     [rsp+28h], r14
0x18003d352  mov     [rsp+130h+var_110], r14
0x18003d357  lea     r9, [rsp+130h+pvarg+8]
0x18003d35c  xor     r8d, r8d
0x18003d35f  lea     rdx, aDescriptor; "Descriptor"
0x18003d366  mov     rcx, rbx
0x18003d369  mov     rax, [rax+20h]
0x18003d36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d372  mov     ebx, eax
0x18003d374  test    eax, eax
0x18003d376  jns     short loc_18003D3CD
0x18003d378  mov     edx, eax; int
0x18003d37a  lea     rcx, qword_18006A9C0; this
0x18003d381  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d386  lea     rcx, WPP_GLOBAL_Control
0x18003d38d  mov     rax, cs:WPP_GLOBAL_Control
0x18003d394  cmp     rax, rcx
0x18003d397  jz      loc_18003DF33
0x18003d39d  test    byte ptr [rax+1Ch], 1
0x18003d3a1  jz      loc_18003DF33
0x18003d3a7  cmp     byte ptr [rax+19h], 2
0x18003d3ab  jb      loc_18003DF33
0x18003d3b1  lea     edx, [r14+69h]
0x18003d3b5  mov     r9d, ebx
0x18003d3b8  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003d3bf  mov     rcx, [rax+10h]
0x18003d3c3  call    WPP_SF_D
0x18003d3c8  jmp     loc_18003DF33
0x18003d3cd  cmp     word ptr [rsp+130h+pvarg+8], 0Dh
0x18003d3d3  jz      short loc_18003D42A
0x18003d3d5  mov     edx, 80041008h; int
0x18003d3da  lea     rcx, qword_18006A9C0; this
0x18003d3e1  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d3e6  lea     rcx, WPP_GLOBAL_Control
0x18003d3ed  mov     rax, cs:WPP_GLOBAL_Control
0x18003d3f4  cmp     rax, rcx
0x18003d3f7  jz      short loc_18003D420
0x18003d3f9  test    byte ptr [rax+1Ch], 1
0x18003d3fd  jz      short loc_18003D420
0x18003d3ff  cmp     byte ptr [rax+19h], 2
0x18003d403  jb      short loc_18003D420
0x18003d405  mov     edx, 6Ah ; 'j'
0x18003d40a  mov     r9d, 80041008h
0x18003d410  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003d417  mov     rcx, [rax+10h]
0x18003d41b  call    WPP_SF_D
0x18003d420  mov     ebx, 80041008h
0x18003d425  jmp     loc_18003DF33
0x18003d42a  mov     [rsp+130h+var_F0], r14
0x18003d42f  mov     rax, qword ptr [rsp+130h+pvarg+10h]
0x18003d434  mov     rcx, [rax]
0x18003d437  mov     rbx, [rcx]
0x18003d43a  lea     rcx, [rsp+130h+var_F0]
0x18003d43f  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003d444  mov     [rsp+130h+var_F0], r14
0x18003d449  lea     r8, [rsp+130h+var_F0]
0x18003d44e  lea     rsi, IID_IWbemClassObject
0x18003d455  mov     rdx, rsi
0x18003d458  mov     rcx, qword ptr [rsp+130h+pvarg+10h]
0x18003d45d  mov     rax, rbx
0x18003d460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d465  lea     rcx, [rsp+130h+pvarg+8]; this
0x18003d46a  test    eax, eax
0x18003d46c  jns     short loc_18003D4B9
0x18003d46e  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003d473  mov     edx, 80041008h; int
0x18003d478  lea     rcx, qword_18006A9C0; this
0x18003d47f  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d484  lea     rcx, WPP_GLOBAL_Control
0x18003d48b  mov     rax, cs:WPP_GLOBAL_Control
0x18003d492  cmp     rax, rcx
0x18003d495  jz      loc_18003D68E
0x18003d49b  test    byte ptr [rax+1Ch], 1
0x18003d49f  jz      loc_18003D68E
0x18003d4a5  cmp     byte ptr [rax+19h], 2
0x18003d4a9  jb      loc_18003D68E
0x18003d4af  mov     edx, 6Bh ; 'k'
0x18003d4b4  jmp     loc_18003D677
0x18003d4b9  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003d4be  lea     rcx, [rsp+130h+var_F0]
0x18003d4c3  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEBAPEAUIWbemClassObject@@XZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(void)
0x18003d4c8  mov     r10, rax
0x18003d4cb  mov     rcx, [rax]
0x18003d4ce  mov     rax, [rcx+20h]
0x18003d4d2  mov     [rsp+28h], r14
0x18003d4d7  mov     [rsp+130h+var_110], r14
0x18003d4dc  lea     r9, [rsp+130h+pvarg+8]
0x18003d4e1  xor     r8d, r8d
0x18003d4e4  lea     rdx, aControlflags; "ControlFlags"
0x18003d4eb  mov     rcx, r10
0x18003d4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4f3  test    eax, eax
0x18003d4f5  jns     short loc_18003D53D
0x18003d4f7  mov     edx, 80041008h; int
0x18003d4fc  lea     rcx, qword_18006A9C0; this
0x18003d503  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d508  lea     rcx, WPP_GLOBAL_Control
0x18003d50f  mov     rax, cs:WPP_GLOBAL_Control
0x18003d516  cmp     rax, rcx
0x18003d519  jz      loc_18003D68E
0x18003d51f  test    byte ptr [rax+1Ch], 1
0x18003d523  jz      loc_18003D68E
0x18003d529  cmp     byte ptr [rax+19h], 2
0x18003d52d  jb      loc_18003D68E
0x18003d533  mov     edx, 6Ch ; 'l'
0x18003d538  jmp     loc_18003D677
0x18003d53d  cmp     word ptr [rsp+130h+pvarg+8], 3
0x18003d543  jz      short loc_18003D58B
0x18003d545  mov     edx, 80041008h; int
0x18003d54a  lea     rcx, qword_18006A9C0; this
0x18003d551  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d556  lea     rcx, WPP_GLOBAL_Control
0x18003d55d  mov     rax, cs:WPP_GLOBAL_Control
0x18003d564  cmp     rax, rcx
0x18003d567  jz      loc_18003D68E
0x18003d56d  test    byte ptr [rax+1Ch], 1
0x18003d571  jz      loc_18003D68E
0x18003d577  cmp     byte ptr [rax+19h], 2
0x18003d57b  jb      loc_18003D68E
0x18003d581  mov     edx, 6Dh ; 'm'
0x18003d586  jmp     loc_18003D677
0x18003d58b  movzx   r9d, word ptr [rsp+130h+pvarg+10h]
0x18003d591  mov     [rbp+4Fh+arg_8], r9w
0x18003d596  movzx   ecx, r9w
0x18003d59a  mov     eax, 2000h
0x18003d59f  and     cx, ax
0x18003d5a2  movzx   eax, r9w
0x18003d5a6  shr     ax, 0Bh
0x18003d5aa  and     al, 1
0x18003d5ac  mov     r8d, r14d
0x18003d5af  test    cx, cx
0x18003d5b2  cmovz   r8d, eax
0x18003d5b6  movzx   edx, r9w
0x18003d5ba  mov     eax, 1000h
0x18003d5bf  and     dx, ax
0x18003d5c2  movzx   eax, r9w
0x18003d5c6  shr     ax, 0Ah
0x18003d5ca  and     al, 1
0x18003d5cc  mov     ecx, r14d
0x18003d5cf  test    dx, dx
0x18003d5d2  cmovz   ecx, eax
0x18003d5d5  test    cl, cl
0x18003d5d7  jz      short loc_18003D5EC
0x18003d5d9  test    r8b, r8b
0x18003d5dc  jz      short loc_18003D5E5
0x18003d5de  mov     edi, 3F00h
0x18003d5e3  jmp     short loc_18003D5FB
0x18003d5e5  mov     edi, 3700h
0x18003d5ea  jmp     short loc_18003D5FB
0x18003d5ec  test    r8b, r8b
0x18003d5ef  mov     edi, 3300h
0x18003d5f4  jz      short loc_18003D5FB
0x18003d5f6  mov     edi, 3B00h
0x18003d5fb  mov     [rbp+4Fh+var_98], r14
0x18003d5ff  lea     rcx, [rsp+130h+pvarg+8]; this
0x18003d604  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003d609  lea     rcx, [rsp+130h+var_F0]
0x18003d60e  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEBAPEAUIWbemClassObject@@XZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(void)
0x18003d613  mov     r10, rax
0x18003d616  mov     rcx, [rax]
0x18003d619  mov     rax, [rcx+20h]
0x18003d61d  mov     [rsp+28h], r14
0x18003d622  mov     [rsp+130h+var_110], r14
0x18003d627  lea     r9, [rsp+130h+pvarg+8]
0x18003d62c  xor     r8d, r8d
0x18003d62f  lea     rdx, aGroup_0; "Group"
0x18003d636  mov     rcx, r10
0x18003d639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d63e  test    eax, eax
0x18003d640  jns     short loc_18003D69D
0x18003d642  mov     edx, 80041008h; int
0x18003d647  lea     rcx, qword_18006A9C0; this
0x18003d64e  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d653  lea     rcx, WPP_GLOBAL_Control
0x18003d65a  mov     rax, cs:WPP_GLOBAL_Control
0x18003d661  cmp     rax, rcx
0x18003d664  jz      short loc_18003D68E
0x18003d666  test    byte ptr [rax+1Ch], 1
0x18003d66a  jz      short loc_18003D68E
0x18003d66c  cmp     byte ptr [rax+19h], 2
0x18003d670  jb      short loc_18003D68E
0x18003d672  mov     edx, 6Eh ; 'n'
0x18003d677  mov     r9d, 80041008h
0x18003d67d  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003d684  mov     rcx, [rax+10h]
0x18003d688  call    WPP_SF_D
0x18003d68d  nop
0x18003d68e  lea     rcx, [rsp+130h+var_F0]
0x18003d693  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003d698  jmp     loc_18003D420
0x18003d69d  cmp     word ptr [rsp+130h+pvarg+8], 0Dh
0x18003d6a3  jz      short loc_18003D6AD
0x18003d6a5  mov     r12b, r14b
0x18003d6a8  jmp     loc_18003D7A8
0x18003d6ad  mov     [rbp+4Fh+var_C0], r14
0x18003d6b1  mov     rax, qword ptr [rsp+130h+pvarg+10h]
0x18003d6b6  mov     rcx, [rax]
0x18003d6b9  mov     rbx, [rcx]
0x18003d6bc  lea     rcx, [rbp+4Fh+var_C0]
0x18003d6c0  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003d6c5  mov     [rbp+4Fh+var_C0], r14
0x18003d6c9  lea     r8, [rbp+4Fh+var_C0]
0x18003d6cd  mov     rdx, rsi
0x18003d6d0  mov     rcx, qword ptr [rsp+130h+pvarg+10h]
0x18003d6d5  mov     rax, rbx
0x18003d6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6dd  mov     ebx, eax
0x18003d6df  lea     rcx, [rsp+130h+pvarg+8]; this
0x18003d6e4  test    eax, eax
0x18003d6e6  jns     short loc_18003D74E
0x18003d6e8  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003d6ed  mov     edx, ebx; int
0x18003d6ef  lea     rcx, qword_18006A9C0; this
0x18003d6f6  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d6fb  lea     rcx, WPP_GLOBAL_Control
0x18003d702  mov     r10, cs:WPP_GLOBAL_Control
0x18003d709  cmp     r10, rcx
0x18003d70c  jz      short loc_18003D735
0x18003d70e  test    byte ptr [r10+1Ch], 1
0x18003d713  jz      short loc_18003D735
0x18003d715  cmp     byte ptr [r10+19h], 2
0x18003d71a  jb      short loc_18003D735
0x18003d71c  mov     edx, 6Fh ; 'o'
0x18003d721  mov     r9d, ebx
0x18003d724  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003d72b  mov     rcx, [r10+10h]
0x18003d72f  call    WPP_SF_D
0x18003d734  nop
0x18003d735  lea     rcx, [rbp+4Fh+var_C0]
0x18003d739  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003d73e  nop
0x18003d73f  lea     rcx, [rsp+130h+var_F0]
0x18003d744  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003d749  jmp     loc_18003DF33
0x18003d74e  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003d753  lea     rdx, [rbp+4Fh+var_98]; struct CNtSid **
0x18003d757  mov     rcx, [rbp+4Fh+var_C0]; struct IWbemClassObject *
0x18003d75b  call    ?LoadSIDFromTrustee@@YAJPEAUIWbemClassObject@@PEAPEAVCNtSid@@@Z; LoadSIDFromTrustee(IWbemClassObject *,CNtSid * *)
0x18003d760  mov     ebx, eax
0x18003d762  test    eax, eax
0x18003d764  jns     short loc_18003D79C
0x18003d766  mov     edx, eax; int
0x18003d768  lea     rcx, qword_18006A9C0; this
0x18003d76f  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d774  lea     rcx, WPP_GLOBAL_Control
0x18003d77b  mov     r10, cs:WPP_GLOBAL_Control
0x18003d782  cmp     r10, rcx
0x18003d785  jz      short loc_18003D735
0x18003d787  test    byte ptr [r10+1Ch], 1
0x18003d78c  jz      short loc_18003D735
0x18003d78e  cmp     byte ptr [r10+19h], 2
0x18003d793  jb      short loc_18003D735
0x18003d795  mov     edx, 70h ; 'p'
0x18003d79a  jmp     short loc_18003D721
0x18003d79c  mov     r12b, 1
0x18003d79f  lea     rcx, [rbp+4Fh+var_C0]
0x18003d7a3  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003d7a8  mov     rax, [rbp+4Fh+var_98]
0x18003d7ac  mov     qword ptr [rsp+130h+pvarg], rax
0x18003d7b1  mov     [rbp+4Fh+var_A0], r14
0x18003d7b5  lea     rcx, [rsp+130h+pvarg+8]; this
0x18003d7ba  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003d7bf  lea     rcx, [rsp+130h+var_F0]
0x18003d7c4  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@QEBAPEAUIWbemClassObject@@XZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::operator->(void)
0x18003d7c9  mov     r10, rax
0x18003d7cc  mov     rcx, [rax]
0x18003d7cf  mov     rax, [rcx+20h]
0x18003d7d3  mov     [rsp+28h], r14
0x18003d7d8  mov     [rsp+130h+var_110], r14
0x18003d7dd  lea     r9, [rsp+130h+pvarg+8]
0x18003d7e2  xor     r8d, r8d
0x18003d7e5  lea     rdx, aOwner; "Owner"
0x18003d7ec  mov     rcx, r10
0x18003d7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7f4  test    eax, eax
0x18003d7f6  jns     short loc_18003D853
0x18003d7f8  mov     edx, 80041008h; int
0x18003d7fd  lea     rcx, qword_18006A9C0; this
0x18003d804  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003d809  lea     rcx, WPP_GLOBAL_Control
  ... truncated ...
```
