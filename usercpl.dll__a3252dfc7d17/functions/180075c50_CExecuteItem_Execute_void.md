# CExecuteItem::Execute(void)

- ea: `0x180075c50`
- end: `0x18007646e`
- name: `?Execute@CExecuteItem@@QEAAJXZ`
- size: `2078`
- prototype: `__int64 __fastcall(CExecuteItem *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180074580`

## callees

- `0x180006a74`
- `0x180058324`
- `0x180075b04`
- `0x180075c50`
- `0x180076f08`
- `0x180076ff8`
- `0x180078010`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x180075e2c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x180075fe5`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x180075e2c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x180075fe5`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180075eb6`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180075f7d`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180076125`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180075eb6`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180075f7d`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180076125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075fad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075fad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076461`
- `ole32!CreateBindCtx` at `0x180075c91`
- `ole32!CreateBindCtx` at `0x180075c91`
- `ole32!CoAllowSetForegroundWindow` at `0x1800763b6`
- `ole32!CoAllowSetForegroundWindow` at `0x1800763b6`
- `USER32!CreatePopupMenu` at `0x180075dfd`
- `USER32!CreatePopupMenu` at `0x180075dfd`
- `USER32!GetMenuDefaultItem` at `0x180075f22`
- `USER32!GetMenuDefaultItem` at `0x180075f22`
- `USER32!DestroyMenu` at `0x180075f86`
- `USER32!DestroyMenu` at `0x180075f86`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180075d09`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180075d09`

## pseudocode

```c
__int64 __fastcall CExecuteItem::Execute(CExecuteItem *this)
{
  HRESULT lambda_c0828ba839c9b98e640d08a0c85a758f; // ebx
  const unsigned __int16 *v4; // rdx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, IUnknown **); // rcx
  __int64 v6; // rcx
  IUnknown *v7; // rcx
  IUnknown *v8; // rcx
  void *v9; // rcx
  LPBC v10; // rcx
  __int64 v11; // rdx
  HMENU PopupMenu; // rdi
  const CHAR *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  UINT MenuDefaultItem; // eax
  LPBC v17; // rax
  IUnknown *v18; // rcx
  LPBC v19; // rcx
  const CHAR *v20; // rcx
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  IUnknown *v26; // rcx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, _QWORD, const GUID *, GUID *); // rbx
  int v29; // eax
  LPBC v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  char IsEnabled; // al
  LPBC v34; // rbx
  void *v35; // rcx
  HRESULT (__stdcall *QueryInterface)(IBindCtx *, const IID *const, void **); // rdi
  __int64 v37; // rdx
  void *v38; // rcx
  char v39; // al
  HRESULT (__stdcall *v40)(IBindCtx *, const IID *const, void **); // rdi
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rcx
  void *v44; // rcx
  LPBC v45; // rcx
  __int64 v46; // rcx
  IUnknown *v47; // rcx
  IUnknown **p_punk; // [rsp+20h] [rbp-48h]
  int v49[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v50; // [rsp+48h] [rbp-20h] BYREF
  IUnknown *punk; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  LPBC ppbc; // [rsp+A0h] [rbp+38h] BYREF
  __int64 v54; // [rsp+A8h] [rbp+40h] BYREF
  IUnknown *punkSite; // [rsp+B0h] [rbp+48h] BYREF
  void *ppvOut; // [rsp+B8h] [rbp+50h] BYREF

  punk = 0;
  if ( !*((_QWORD *)this + 21) )
    return (unsigned int)-2147024882;
  ppbc = 0;
  CreateBindCtx(0, &ppbc);
  lambda_c0828ba839c9b98e640d08a0c85a758f = wil::ShellBindContextHelper::SetNamedBoolean(
                                              (wil::ShellBindContextHelper *)&ppbc,
                                              v4);
  if ( lambda_c0828ba839c9b98e640d08a0c85a758f >= 0 )
  {
    p_punk = &punk;
    lambda_c0828ba839c9b98e640d08a0c85a758f = (*(__int64 (__fastcall **)(_QWORD, LPBC, const GUID *, GUID *))(**((_QWORD **)this + 21) + 24LL))(
                                                *((_QWORD *)this + 21),
                                                ppbc,
                                                &BHID_SFUIObject,
                                                &GUID_000214e4_0000_0000_c000_000000000046);
    if ( lambda_c0828ba839c9b98e640d08a0c85a758f >= 0 )
    {
      if ( *((_QWORD *)this + 23) )
      {
        ppvOut = 0;
        lambda_c0828ba839c9b98e640d08a0c85a758f = IUnknown_QueryService(
                                                    punk,
                                                    (const GUID *const)&SID_CtxQueryAssociations,
                                                    &GUID_d8820afb_ada1_45db_bd57_cf29047ee2bf,
                                                    &ppvOut);
        if ( lambda_c0828ba839c9b98e640d08a0c85a758f < 0 )
          goto LABEL_16;
        v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, IUnknown **))*((_QWORD *)this + 23);
        punkSite = 0;
        lambda_c0828ba839c9b98e640d08a0c85a758f = (**v5)(v5, &GUID_d8820afb_ada1_45db_bd57_cf29047ee2bf, &punkSite);
        if ( lambda_c0828ba839c9b98e640d08a0c85a758f >= 0 )
        {
          v54 = 0;
          lambda_c0828ba839c9b98e640d08a0c85a758f = ((__int64 (__fastcall *)(IUnknown *, __int64 *))punkSite->lpVtbl[1].AddRef)(
                                                      punkSite,
                                                      &v54);
          if ( lambda_c0828ba839c9b98e640d08a0c85a758f >= 0 )
            lambda_c0828ba839c9b98e640d08a0c85a758f = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvOut
                                                                                                 + 24LL))(
                                                        ppvOut,
                                                        v54);
          v6 = v54;
          if ( v54 )
          {
            v54 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          }
        }
        v7 = punkSite;
        if ( punkSite )
        {
          punkSite = 0;
          ((void (__fastcall *)(IUnknown *))v7->lpVtbl->Release)(v7);
        }
        if ( lambda_c0828ba839c9b98e640d08a0c85a758f < 0 )
        {
LABEL_16:
          v8 = punk;
          punk = 0;
          if ( v8 )
            ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
        }
        v9 = ppvOut;
        if ( ppvOut )
        {
          ppvOut = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
    }
  }
  v10 = ppbc;
  if ( ppbc )
  {
    ppbc = 0;
    ((void (__fastcall *)(LPBC))v10->lpVtbl->Release)(v10);
  }
  if ( lambda_c0828ba839c9b98e640d08a0c85a758f >= 0 )
  {
    PopupMenu = CreatePopupMenu();
    if ( !PopupMenu )
    {
      lambda_c0828ba839c9b98e640d08a0c85a758f = -2147024882;
LABEL_46:
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      return (unsigned int)lambda_c0828ba839c9b98e640d08a0c85a758f;
    }
    v13 = (const CHAR *)*((_QWORD *)this + 2);
    ppbc = 0;
    if ( v13 && SHStrDupA(v13, (LPWSTR *)&ppbc) >= 0 )
    {
      v54 = 0;
      if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))punk->lpVtbl->QueryInterface)(
             punk,
             &GUID_649e2263_dc09_466f_9d66_3eb133ee8f81,
             &v54) >= 0 )
      {
        ppvOut = ppbc;
        (*(void (__fastcall **)(__int64, void **, __int64))(*(_QWORD *)v54 + 24LL))(v54, &ppvOut, 1);
      }
      v14 = v54;
      if ( v54 )
      {
        v54 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    v15 = *((_QWORD *)this + 22);
    punkSite = 0;
    lambda_c0828ba839c9b98e640d08a0c85a758f = ServiceProviderImpl::Make__lambda_c0828ba839c9b98e640d08a0c85a758f___(
                                                v15,
                                                v11,
                                                &punkSite);
    if ( lambda_c0828ba839c9b98e640d08a0c85a758f < 0 )
    {
LABEL_43:
      DestroyMenu(PopupMenu);
      v18 = punkSite;
      if ( punkSite )
      {
        punkSite = 0;
        ((void (__fastcall *)(IUnknown *))v18->lpVtbl->Release)(v18);
      }
      v19 = ppbc;
      ppbc = 0;
      CoTaskMemFree(v19);
      goto LABEL_46;
    }
    IUnknown_SetSite(punk, punkSite);
    LODWORD(p_punk) = 255;
    lambda_c0828ba839c9b98e640d08a0c85a758f = ((__int64 (__fastcall *)(IUnknown *, HMENU, _QWORD, __int64, IUnknown **, unsigned int))punk->lpVtbl[1].QueryInterface)(
                                                punk,
                                                PopupMenu,
                                                0,
                                                1,
                                                p_punk,
                                                (*((_QWORD *)this + 2) != 0 ? 2048 : 1)
                                              | (unsigned int)(*((_BYTE *)this + 208) == 0 ? 2 : 0));
    if ( lambda_c0828ba839c9b98e640d08a0c85a758f >= 0 )
    {
      if ( *((_QWORD *)this + 2) )
        goto LABEL_39;
      MenuDefaultItem = GetMenuDefaultItem(PopupMenu, 0, 0);
      if ( MenuDefaultItem != -1 )
        *((_QWORD *)this + 2) = (unsigned __int16)(MenuDefaultItem - 1);
      if ( *((_QWORD *)this + 2) )
      {
LABEL_39:
        if ( *((_QWORD *)this + 2) >= 0x10000u )
        {
          v17 = ppbc;
          *((_DWORD *)this + 1) |= 0x4000u;
          *((_QWORD *)this + 8) = v17;
        }
      }
      else if ( MenuDefaultItem == -1 )
      {
        lambda_c0828ba839c9b98e640d08a0c85a758f = -2147467259;
        goto LABEL_42;
      }
      lambda_c0828ba839c9b98e640d08a0c85a758f = ((__int64 (__fastcall *)(IUnknown *, CExecuteItem *))punk->lpVtbl[1].AddRef)(
                                                  punk,
                                                  this);
    }
LABEL_42:
    IUnknown_SetSite(punk, 0);
    goto LABEL_43;
  }
  if ( lambda_c0828ba839c9b98e640d08a0c85a758f != -2147024769 )
    return (unsigned int)lambda_c0828ba839c9b98e640d08a0c85a758f;
  v20 = (const CHAR *)*((_QWORD *)this + 2);
  punkSite = 0;
  if ( v20 )
    SHStrDupA(v20, (LPWSTR *)&punkSite);
  v21 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 23);
  v54 = 0;
  if ( v21 )
  {
    v22 = **v21;
    v23 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(&v54);
    lambda_c0828ba839c9b98e640d08a0c85a758f = v22(v21, &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f, v23);
    if ( lambda_c0828ba839c9b98e640d08a0c85a758f < 0 )
    {
      v24 = 379;
LABEL_53:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecoreuap\\shell\\lib\\executeitem\\executeitem.cpp",
        (const char *)(unsigned int)lambda_c0828ba839c9b98e640d08a0c85a758f,
        (int)p_punk);
LABEL_54:
      v25 = v54;
      if ( v54 )
      {
        v54 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      v26 = punkSite;
      punkSite = 0;
      CoTaskMemFree(v26);
      return (unsigned int)lambda_c0828ba839c9b98e640d08a0c85a758f;
    }
  }
  else
  {
    v27 = *((_QWORD *)this + 21);
    v28 = *(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, GUID *))(*(_QWORD *)v27 + 24LL);
    LODWORD(p_punk) = (unsigned int)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(&v54);
    lambda_c0828ba839c9b98e640d08a0c85a758f = v28(
                                                v27,
                                                0,
                                                &BHID_AssociationArray,
                                                &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f);
    if ( lambda_c0828ba839c9b98e640d08a0c85a758f < 0 )
    {
      v24 = 383;
      goto LABEL_53;
    }
  }
  ppbc = 0;
  v29 = (*(__int64 (__fastcall **)(__int64, __int64, IUnknown *, GUID *))(*(_QWORD *)v54 + 64LL))(
          v54,
          35651600,
          punkSite,
          &GUID_7f9185b0_cb92_43c5_80a9_92277a4f7b54);
  lambda_c0828ba839c9b98e640d08a0c85a758f = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"onecoreuap\\shell\\lib\\executeitem\\executeitem.cpp",
      (const char *)(unsigned int)v29,
      (int)&ppbc);
LABEL_61:
    v30 = ppbc;
    if ( ppbc )
    {
      ppbc = 0;
      ((void (__fastcall *)(LPBC))v30->lpVtbl->Release)(v30);
    }
    goto LABEL_54;
  }
  IUnknown_SetSite((IUnknown *)ppbc, *((IUnknown **)this + 22));
  *(_QWORD *)v49 = 0;
  v31 = (*(__int64 (__fastcall **)(__int64, __int64, IUnknown *, GUID *))(*(_QWORD *)v54 + 64LL))(
          v54,
          35651598,
          punkSite,
          &GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502);
  lambda_c0828ba839c9b98e640d08a0c85a758f = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x187,
      (unsigned int)"onecoreuap\\shell\\lib\\executeitem\\executeitem.cpp",
      (const char *)(unsigned int)v31,
      (int)v49);
LABEL_65:
    v32 = *(_QWORD *)v49;
    if ( *(_QWORD *)v49 )
    {
      *(_QWORD *)v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    goto LABEL_61;
  }
  ppvOut = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TVSFixInCExecuteItem>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TVSFixInCExecuteItem>::GetImpl'::`2'::impl);
  v34 = ppbc;
  v35 = ppvOut;
  QueryInterface = ppbc->lpVtbl->QueryInterface;
  if ( IsEnabled )
  {
    if ( ppvOut )
    {
      ppvOut = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
    }
    if ( ((int (__fastcall *)(LPBC, GUID *, void **))QueryInterface)(
           v34,
           &GUID_e157c3a1_a532_4de2_9480_1452b7426eee,
           &ppvOut) >= 0 )
    {
      if ( ppvOut )
      {
        lambda_c0828ba839c9b98e640d08a0c85a758f = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 24LL))(
                                                    ppvOut,
                                                    *(_QWORD *)v49);
        if ( lambda_c0828ba839c9b98e640d08a0c85a758f < 0 )
        {
          v37 = 399;
LABEL_74:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v37,
            (unsigned int)"onecoreuap\\shell\\lib\\executeitem\\executeitem.cpp",
            (const char *)(unsigned int)lambda_c0828ba839c9b98e640d08a0c85a758f,
            (int)v49);
LABEL_75:
          v38 = ppvOut;
          if ( ppvOut )
          {
            ppvOut = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
          }
          goto LABEL_65;
        }
      }
    }
  }
  else
  {
    if ( ppvOut )
    {
      ppvOut = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
    }
    ((void (__fastcall *)(LPBC, GUID *, void **))QueryInterface)(
      v34,
      &GUID_e157c3a1_a532_4de2_9480_1452b7426eee,
      &ppvOut);
    lambda_c0828ba839c9b98e640d08a0c85a758f = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 24LL))(
                                                ppvOut,
                                                *(_QWORD *)v49);
    if ( lambda_c0828ba839c9b98e640d08a0c85a758f < 0 )
    {
      v37 = 406;
      goto LABEL_74;
    }
  }
  v50 = 0;
  v39 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TVSFixInCExecuteItem>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TVSFixInCExecuteItem>::GetImpl'::`2'::impl);
  v40 = ppbc->lpVtbl->QueryInterface;
  if ( v39 )
  {
    if ( ((int (__fastcall *)(LPBC, GUID *, __int64 *))v40)(ppbc, &GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c, &v50) >= 0 )
    {
      if ( v50 )
      {
        lambda_c0828ba839c9b98e640d08a0c85a758f = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v50 + 24LL))(
                                                    v50,
                                                    *((_QWORD *)this + 21));
        if ( lambda_c0828ba839c9b98e640d08a0c85a758f < 0 )
        {
          v41 = 416;
          goto LABEL_86;
        }
      }
    }
  }
  else
  {
    ((void (__fastcall *)(LPBC, GUID *, __int64 *))v40)(ppbc, &GUID_1c9cd5bb_98e9_4491_a60f_31aacc72b83c, &v50);
    lambda_c0828ba839c9b98e640d08a0c85a758f = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v50 + 24LL))(
                                                v50,
                                                *((_QWORD *)this + 21));
    if ( lambda_c0828ba839c9b98e640d08a0c85a758f < 0 )
    {
      v41 = 423;
      goto LABEL_86;
    }
  }
  CoAllowSetForegroundWindow((IUnknown *)ppbc, 0);
  lambda_c0828ba839c9b98e640d08a0c85a758f = ((__int64 (__fastcall *)(LPBC))ppbc->lpVtbl->RegisterObjectParam)(ppbc);
  if ( lambda_c0828ba839c9b98e640d08a0c85a758f < 0 )
  {
    v41 = 431;
LABEL_86:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecoreuap\\shell\\lib\\executeitem\\executeitem.cpp",
      (const char *)(unsigned int)lambda_c0828ba839c9b98e640d08a0c85a758f,
      (int)v49);
    v42 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    goto LABEL_75;
  }
  v43 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = ppvOut;
  if ( ppvOut )
  {
    ppvOut = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = ppbc;
  if ( ppbc )
  {
    ppbc = 0;
    ((void (__fastcall *)(LPBC))v45->lpVtbl->Release)(v45);
  }
  v46 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = punkSite;
  punkSite = 0;
  CoTaskMemFree(v47);
  return 0;
}

```

## disassembly

```asm
0x180075c50  push    rbp
0x180075c52  push    rbx
0x180075c53  push    rsi
0x180075c54  push    rdi
0x180075c55  push    r14
0x180075c57  push    r15
0x180075c59  mov     rbp, rsp
0x180075c5c  sub     rsp, 68h
0x180075c60  xor     r14d, r14d
0x180075c63  mov     rsi, rcx
0x180075c66  mov     [rbp+punk], r14
0x180075c6a  cmp     [rcx+0A8h], r14
0x180075c71  jnz     short loc_180075C87
0x180075c73  mov     ebx, 8007000Eh
0x180075c78  mov     eax, ebx
0x180075c7a  add     rsp, 68h
0x180075c7e  pop     r15
0x180075c80  pop     r14
0x180075c82  pop     rdi
0x180075c83  pop     rsi
0x180075c84  pop     rbx
0x180075c85  pop     rbp
0x180075c86  retn
0x180075c87  lea     rdx, [rbp+ppbc]; ppbc
0x180075c8b  mov     [rbp+ppbc], r14
0x180075c8f  xor     ecx, ecx; reserved
0x180075c91  call    cs:__imp_CreateBindCtx
0x180075c97  lea     rcx, [rbp+ppbc]; this
0x180075c9b  call    ?SetNamedBoolean@ShellBindContextHelper@wil@@QEAAJPEBG@Z; wil::ShellBindContextHelper::SetNamedBoolean(ushort const *)
0x180075ca0  mov     ebx, eax
0x180075ca2  test    eax, eax
0x180075ca4  js      loc_180075DDC
0x180075caa  mov     rcx, [rsi+0A8h]
0x180075cb1  lea     rdx, [rbp+punk]
0x180075cb5  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180075cba  lea     r9, _GUID_000214e4_0000_0000_c000_000000000046
0x180075cc1  mov     rdx, [rbp+ppbc]
0x180075cc5  lea     r8, BHID_SFUIObject
0x180075ccc  mov     rax, [rcx]
0x180075ccf  mov     rax, [rax+18h]
0x180075cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cd8  mov     ebx, eax
0x180075cda  test    eax, eax
0x180075cdc  js      loc_180075DDC
0x180075ce2  cmp     [rsi+0B8h], r14
0x180075ce9  jz      loc_180075DDC
0x180075cef  mov     rcx, [rbp+punk]; punk
0x180075cf3  lea     r9, [rbp+ppvOut]; ppvOut
0x180075cf7  lea     r8, _GUID_d8820afb_ada1_45db_bd57_cf29047ee2bf; riid
0x180075cfe  mov     [rbp+ppvOut], r14
0x180075d02  lea     rdx, SID_CtxQueryAssociations; guidService
0x180075d09  call    cs:__imp_IUnknown_QueryService
0x180075d0f  mov     ebx, eax
0x180075d11  test    eax, eax
0x180075d13  js      loc_180075DAA
0x180075d19  mov     rcx, [rsi+0B8h]
0x180075d20  lea     r8, [rbp+punkSite]
0x180075d24  mov     [rbp+punkSite], r14
0x180075d28  lea     rdx, _GUID_d8820afb_ada1_45db_bd57_cf29047ee2bf
0x180075d2f  mov     rax, [rcx]
0x180075d32  mov     rax, [rax]
0x180075d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d3a  mov     ebx, eax
0x180075d3c  test    eax, eax
0x180075d3e  js      short loc_180075D8D
0x180075d40  mov     rcx, [rbp+punkSite]
0x180075d44  lea     rdx, [rbp+arg_8]
0x180075d48  mov     [rbp+arg_8], r14
0x180075d4c  mov     rax, [rcx]
0x180075d4f  mov     rax, [rax+20h]
0x180075d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d58  mov     ebx, eax
0x180075d5a  test    eax, eax
0x180075d5c  js      short loc_180075D74
0x180075d5e  mov     rcx, [rbp+ppvOut]
0x180075d62  mov     rdx, [rbp+arg_8]
0x180075d66  mov     rax, [rcx]
0x180075d69  mov     rax, [rax+18h]
0x180075d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d72  mov     ebx, eax
0x180075d74  mov     rcx, [rbp+arg_8]
0x180075d78  test    rcx, rcx
0x180075d7b  jz      short loc_180075D8D
0x180075d7d  mov     [rbp+arg_8], r14
0x180075d81  mov     rax, [rcx]
0x180075d84  mov     rax, [rax+10h]
0x180075d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d8d  mov     rcx, [rbp+punkSite]
0x180075d91  test    rcx, rcx
0x180075d94  jz      short loc_180075DA6
0x180075d96  mov     [rbp+punkSite], r14
0x180075d9a  mov     rax, [rcx]
0x180075d9d  mov     rax, [rax+10h]
0x180075da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075da6  test    ebx, ebx
0x180075da8  jns     short loc_180075DC3
0x180075daa  mov     rcx, [rbp+punk]
0x180075dae  mov     [rbp+punk], r14
0x180075db2  test    rcx, rcx
0x180075db5  jz      short loc_180075DC3
0x180075db7  mov     rax, [rcx]
0x180075dba  mov     rax, [rax+10h]
0x180075dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075dc3  mov     rcx, [rbp+ppvOut]
0x180075dc7  test    rcx, rcx
0x180075dca  jz      short loc_180075DDC
0x180075dcc  mov     [rbp+ppvOut], r14
0x180075dd0  mov     rax, [rcx]
0x180075dd3  mov     rax, [rax+10h]
0x180075dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ddc  mov     rcx, [rbp+ppbc]
0x180075de0  test    rcx, rcx
0x180075de3  jz      short loc_180075DF5
0x180075de5  mov     [rbp+ppbc], r14
0x180075de9  mov     rax, [rcx]
0x180075dec  mov     rax, [rax+10h]
0x180075df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075df5  test    ebx, ebx
0x180075df7  js      loc_180075FC8
0x180075dfd  call    cs:__imp_CreatePopupMenu
0x180075e03  mov     rdi, rax
0x180075e06  test    rax, rax
0x180075e09  jnz     short loc_180075E15
0x180075e0b  mov     ebx, 8007000Eh
0x180075e10  jmp     loc_180075FB3
0x180075e15  mov     rcx, [rsi+10h]; psz
0x180075e19  mov     r15d, 1
0x180075e1f  mov     [rbp+ppbc], r14
0x180075e23  test    rcx, rcx
0x180075e26  jz      short loc_180075E90
0x180075e28  lea     rdx, [rbp+ppbc]; ppwsz
0x180075e2c  call    cs:__imp_SHStrDupA
0x180075e32  test    eax, eax
0x180075e34  js      short loc_180075E90
0x180075e36  mov     rcx, [rbp+punk]
0x180075e3a  lea     r8, [rbp+arg_8]
0x180075e3e  mov     [rbp+arg_8], r14
0x180075e42  lea     rdx, _GUID_649e2263_dc09_466f_9d66_3eb133ee8f81
0x180075e49  mov     rax, [rcx]
0x180075e4c  mov     rax, [rax]
0x180075e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e54  test    eax, eax
0x180075e56  js      short loc_180075E77
0x180075e58  mov     rax, [rbp+ppbc]
0x180075e5c  lea     rdx, [rbp+ppvOut]
0x180075e60  mov     rcx, [rbp+arg_8]
0x180075e64  mov     r8d, r15d
0x180075e67  mov     [rbp+ppvOut], rax
0x180075e6b  mov     rax, [rcx]
0x180075e6e  mov     rax, [rax+18h]
0x180075e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e77  mov     rcx, [rbp+arg_8]
0x180075e7b  test    rcx, rcx
0x180075e7e  jz      short loc_180075E90
0x180075e80  mov     [rbp+arg_8], r14
0x180075e84  mov     rax, [rcx]
0x180075e87  mov     rax, [rax+10h]
0x180075e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e90  mov     rcx, [rsi+0B0h]
0x180075e97  lea     r8, [rbp+punkSite]
0x180075e9b  mov     [rbp+punkSite], r14
0x180075e9f  call    ServiceProviderImpl__Make__lambda_c0828ba839c9b98e640d08a0c85a758f___
0x180075ea4  mov     ebx, eax
0x180075ea6  test    eax, eax
0x180075ea8  js      loc_180075F83
0x180075eae  mov     rdx, [rbp+punkSite]; punkSite
0x180075eb2  mov     rcx, [rbp+punk]; punk
0x180075eb6  call    cs:__imp_IUnknown_SetSite
0x180075ebc  mov     al, [rsi+0D0h]
0x180075ec2  mov     r9d, r15d
0x180075ec5  mov     rcx, [rbp+punk]
0x180075ec9  neg     al
0x180075ecb  mov     rax, [rsi+10h]
0x180075ecf  sbb     r8d, r8d
0x180075ed2  not     r8d
0x180075ed5  mov     r10, [rcx]
0x180075ed8  and     r8d, 2
0x180075edc  neg     rax
0x180075edf  sbb     edx, edx
0x180075ee1  mov     rax, [r10+18h]
0x180075ee5  and     edx, 7FFh
0x180075eeb  add     edx, r15d
0x180075eee  or      r8d, edx
0x180075ef1  mov     rdx, rdi
0x180075ef4  mov     [rsp+68h+var_40], r8d
0x180075ef9  xor     r8d, r8d
0x180075efc  mov     [rsp+68h+var_48], 0FFh
0x180075f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f09  mov     ebx, eax
0x180075f0b  test    eax, eax
0x180075f0d  js      short loc_180075F77
0x180075f0f  or      ebx, 0FFFFFFFFh
0x180075f12  mov     eax, ebx
0x180075f14  cmp     [rsi+10h], r14
0x180075f18  jnz     short loc_180075F4B
0x180075f1a  xor     r8d, r8d; gmdiFlags
0x180075f1d  xor     edx, edx; fByPos
0x180075f1f  mov     rcx, rdi; hMenu
0x180075f22  call    cs:__imp_GetMenuDefaultItem
0x180075f28  cmp     eax, ebx
0x180075f2a  jz      short loc_180075F3A
0x180075f2c  movzx   ecx, ax
0x180075f2f  sub     cx, r15w
0x180075f33  movzx   ecx, cx
0x180075f36  mov     [rsi+10h], rcx
0x180075f3a  cmp     [rsi+10h], r14
0x180075f3e  jnz     short loc_180075F4B
0x180075f40  cmp     eax, ebx
0x180075f42  jnz     short loc_180075F62
0x180075f44  mov     ebx, 80004005h
0x180075f49  jmp     short loc_180075F77
0x180075f4b  cmp     qword ptr [rsi+10h], 10000h
0x180075f53  jb      short loc_180075F62
0x180075f55  mov     rax, [rbp+ppbc]
0x180075f59  bts     dword ptr [rsi+4], 0Eh
0x180075f5e  mov     [rsi+40h], rax
0x180075f62  mov     rcx, [rbp+punk]
0x180075f66  mov     rdx, rsi
0x180075f69  mov     rax, [rcx]
0x180075f6c  mov     rax, [rax+20h]
0x180075f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f75  mov     ebx, eax
0x180075f77  mov     rcx, [rbp+punk]; punk
0x180075f7b  xor     edx, edx; punkSite
0x180075f7d  call    cs:__imp_IUnknown_SetSite
0x180075f83  mov     rcx, rdi; hMenu
0x180075f86  call    cs:__imp_DestroyMenu
0x180075f8c  mov     rcx, [rbp+punkSite]
0x180075f90  test    rcx, rcx
0x180075f93  jz      short loc_180075FA5
0x180075f95  mov     [rbp+punkSite], r14
0x180075f99  mov     rax, [rcx]
0x180075f9c  mov     rax, [rax+10h]
0x180075fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075fa5  mov     rcx, [rbp+ppbc]; pv
0x180075fa9  mov     [rbp+ppbc], r14
0x180075fad  call    cs:__imp_CoTaskMemFree
0x180075fb3  mov     rcx, [rbp+punk]
0x180075fb7  mov     rax, [rcx]
0x180075fba  mov     rax, [rax+10h]
0x180075fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075fc3  jmp     loc_180075C78
0x180075fc8  cmp     ebx, 8007007Fh
0x180075fce  jnz     loc_180075C78
0x180075fd4  mov     rcx, [rsi+10h]; psz
0x180075fd8  mov     [rbp+punkSite], r14
0x180075fdc  test    rcx, rcx
0x180075fdf  jz      short loc_180075FEB
0x180075fe1  lea     rdx, [rbp+punkSite]; ppwsz
0x180075fe5  call    cs:__imp_SHStrDupA
0x180075feb  mov     rdi, [rsi+0B8h]
0x180075ff2  lea     rcx, [rbp+arg_8]
0x180075ff6  mov     [rbp+arg_8], r14
0x180075ffa  test    rdi, rdi
0x180075ffd  jz      short loc_18007606D
0x180075fff  mov     rax, [rdi]
0x180076002  mov     rbx, [rax]
0x180076005  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWICImagingFactory>>)
0x18007600a  mov     r8, rax
0x18007600d  lea     rdx, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x180076014  mov     rax, rbx
0x180076017  mov     rcx, rdi
0x18007601a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007601f  mov     ebx, eax
0x180076021  test    eax, eax
0x180076023  jns     loc_1800760AD
0x180076029  mov     edx, 17Bh; void *
0x18007602e  mov     rcx, [rbp+30h]; this
0x180076032  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\executeitem\\ex"...
0x180076039  mov     r9d, ebx; char *
0x18007603c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076041  mov     rcx, [rbp+arg_8]
0x180076045  test    rcx, rcx
0x180076048  jz      short loc_18007605A
0x18007604a  mov     [rbp+arg_8], r14
0x18007604e  mov     rax, [rcx]
0x180076051  mov     rax, [rax+10h]
0x180076055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007605a  mov     rcx, [rbp+punkSite]; pv
0x18007605e  mov     [rbp+punkSite], r14
0x180076062  call    cs:__imp_CoTaskMemFree
0x180076068  jmp     loc_180075C78
0x18007606d  mov     rdi, [rsi+0A8h]
0x180076074  mov     rax, [rdi]
0x180076077  mov     rbx, [rax+18h]
0x18007607b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWICImagingFactory>>)
0x180076080  mov     qword ptr [rsp+68h+var_48], rax
0x180076085  lea     r9, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x18007608c  mov     rax, rbx
0x18007608f  lea     r8, BHID_AssociationArray
0x180076096  xor     edx, edx
0x180076098  mov     rcx, rdi
0x18007609b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760a0  mov     ebx, eax
0x1800760a2  test    eax, eax
0x1800760a4  jns     short loc_1800760AD
0x1800760a6  mov     edx, 17Fh
0x1800760ab  jmp     short loc_18007602E
0x1800760ad  mov     rcx, [rbp+arg_8]
0x1800760b1  lea     rdx, [rbp+ppbc]
  ... truncated ...
```
