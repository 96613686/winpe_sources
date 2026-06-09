# SHGetViewStatePropertyBag

- ea: `0x18000f430`
- end: `0x18000f9c0`
- name: `SHGetViewStatePropertyBag`
- size: `1424`
- prototype: `HRESULT __stdcall(LPCITEMIDLIST pidl, PCWSTR pszBagName, DWORD dwFlags, const IID *const riid, void **ppv)`
- caller_count: `0`
- callee_count: `24`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180008730`
- `0x180009db8`
- `0x18000bd64`
- `0x18000e624`
- `0x18000f430`
- `0x180010a18`
- `0x180012550`
- `0x180012940`
- `0x180012a04`
- `0x180029080`
- `0x18002919c`
- `0x1800291f8`
- `0x1800292a4`
- `0x180029370`
- `0x180029510`
- `0x180029758`
- `0x180029a38`
- `0x180029ad4`
- `0x180029fb0`
- `0x18002a108`
- `0x18002a58c`
- `0x18002b180`
- `0x18002bba4`
- `0x180037010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x18000f4eb`
- `SHELL32!SHCreateItemFromIDList` at `0x18000f894`
- `SHELL32!SHCreateItemFromIDList` at `0x18000f4eb`
- `SHELL32!SHCreateItemFromIDList` at `0x18000f894`
- `SHELL32!__imp_ILClone` at `0x18000f48b`
- `SHELL32!__imp_ILClone` at `0x18000f5ec`
- `SHELL32!__imp_ILClone` at `0x18000f64c`
- `SHELL32!__imp_ILClone` at `0x18000f48b`
- `SHELL32!__imp_ILClone` at `0x18000f5ec`
- `SHELL32!__imp_ILClone` at `0x18000f64c`
- `SHELL32!__imp_ILIsEqual` at `0x18000f5de`
- `SHELL32!__imp_ILIsEqual` at `0x18000f5de`
- `SHELL32!__imp_ILFree` at `0x18000f998`
- `SHELL32!__imp_ILFree` at `0x18000f998`

## pseudocode

```c
HRESULT __stdcall SHGetViewStatePropertyBag(
        LPCITEMIDLIST pidl,
        PCWSTR pszBagName,
        DWORD dwFlags,
        const IID *const riid,
        void **ppv)
{
  const ITEMIDLIST *v9; // rcx
  LPITEMIDLIST v10; // rax
  HRESULT CachedViewStatePropertyBag; // ebx
  __int64 v12; // rax
  __int64 v13; // rbx
  const ITEMIDLIST *v14; // rdx
  LPITEMIDLIST v15; // rax
  const struct _ITEMIDLIST_ABSOLUTE *v16; // rcx
  _QWORD *v17; // rax
  const ITEMIDLIST *v18; // rbx
  int v19; // edi
  const ITEMIDLIST *v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  _QWORD *v23; // rax
  CViewStatePropertyBag *v24; // rax
  CViewStatePropertyBag *v25; // rax
  struct CViewStatePropertyBag *v26; // rdi
  int v27; // eax
  __int64 v28; // r9
  __int64 v29; // rdx
  int v30; // eax
  CViewStatePropertyBag *v31; // rax
  CViewStatePropertyBag *v32; // rax
  struct CViewStatePropertyBag *v33; // rdi
  void **v35; // [rsp+20h] [rbp-51h]
  LPCITEMIDLIST *p_pidl1; // [rsp+30h] [rbp-41h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v37; // [rsp+38h] [rbp-39h] BYREF
  char v38; // [rsp+40h] [rbp-31h]
  LPITEMIDLIST pidla; // [rsp+48h] [rbp-29h] BYREF
  void *v40; // [rsp+50h] [rbp-21h] BYREF
  void *v41; // [rsp+58h] [rbp-19h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+60h] [rbp-11h] BYREF
  LPCITEMIDLIST v43; // [rsp+68h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::GetImpl'::`2'::impl) )
  {
    v9 = 0;
    pidl1 = 0;
    if ( pidl )
    {
      v10 = ILClone(pidl);
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &pidl1,
        v10);
      v9 = pidl1;
      if ( !pidl1 )
      {
        CachedViewStatePropertyBag = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x51B,
          (unsigned int)"shell\\shlwapi\\propbagadv.cpp",
          (const char *)0x8007000ELL,
          (int)v35);
LABEL_5:
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &pidl1,
          0);
        return CachedViewStatePropertyBag;
      }
    }
    v40 = 0;
    if ( v9 )
    {
      if ( SHCreateItemFromIDList(v9, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v40) >= 0 )
      {
        v41 = 0;
        v35 = &v41;
        if ( (*(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)v40 + 24LL))(
               v40,
               0,
               &BHID_SFObject,
               &GUID_9d264146_a94f_4195_9f9f_3bb12ce0c955) >= 0 )
        {
          v12 = *(_QWORD *)v41;
          p_pidl1 = &pidl1;
          v37 = 0;
          v38 = 1;
          (*(void (__fastcall **)(void *, struct _ITEMIDLIST_ABSOLUTE **))(v12 + 24))(v41, &v37);
          wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl1);
        }
        wil::com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>::~com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>(&v41);
      }
      if ( pidl1 )
      {
        if ( (int)_GetCachedViewStatePropertyBag(
                    (const struct _ITEMIDLIST_ABSOLUTE *)pidl1,
                    pszBagName,
                    dwFlags,
                    riid,
                    ppv) >= 0 )
          goto LABEL_34;
        if ( pidl1 )
        {
          v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
          if ( !*(_BYTE *)(v13 + 16) )
            _dyn_tls_on_demand_init();
          if ( !*(_BYTE *)(v13 + 16) )
            _dyn_tls_on_demand_init();
          v14 = *(const ITEMIDLIST **)(v13 + 312);
          if ( !v14
            || !*(_QWORD *)(v13 + 304)
            || !ILIsEqual(pidl1, v14)
            || (v15 = ILClone(*(LPCITEMIDLIST *)(v13 + 304)),
                wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
                  &pidl1,
                  v15),
                (v16 = (const struct _ITEMIDLIST_ABSOLUTE *)pidl1) == 0) )
          {
            pidla = 0;
            v17 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::ensure_data(&pidla);
            tip2::details::shared_data<0,0,0>::start(*v17 + 8LL, &p_pidl1);
            *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::operator->(
                                    &pidla,
                                    &v41)
                     + 272LL) = 1;
            tip2::test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::~test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>(&v41);
            v41 = ILClone(pidl1);
            v18 = (const ITEMIDLIST *)v41;
            if ( !v41 )
            {
              CachedViewStatePropertyBag = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x543,
                (unsigned int)"shell\\shlwapi\\propbagadv.cpp",
                (const char *)0x8007000ELL,
                (int)v35);
LABEL_31:
              wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
                &v41,
                0);
              wil::com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>(&pidla);
LABEL_45:
              wil::com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>::~com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>(&v40);
              goto LABEL_5;
            }
            p_pidl1 = &v43;
            v43 = 0;
            v37 = 0;
            v38 = 1;
            v19 = NormalizePidlForViewState(pidl1, &v37);
            wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl1);
            if ( v19 >= 0 )
            {
              v20 = v43;
              if ( v43 )
              {
                v43 = pidl1;
                pidl1 = v20;
                wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
                  &v43,
                  0);
                v21 = CViewStatePropertyBag::SetViewStateCachedOriginal(v18);
                CachedViewStatePropertyBag = v21;
                if ( v21 < 0 )
                {
                  v22 = 1355;
LABEL_30:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v22,
                    (unsigned int)"shell\\shlwapi\\propbagadv.cpp",
                    (const char *)(unsigned int)v21,
                    (int)v35);
                  wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
                    &v43,
                    0);
                  goto LABEL_31;
                }
                v21 = CViewStatePropertyBag::SetViewStateCachedNormalized(pidl1);
                CachedViewStatePropertyBag = v21;
                if ( v21 < 0 )
                {
                  v22 = 1356;
                  goto LABEL_30;
                }
              }
            }
            *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::operator->(
                                     &pidla,
                                     &p_pidl1)
                      + 276LL) = v19;
            tip2::test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::~test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>(&p_pidl1);
            v23 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::operator->(
                              &pidla,
                              &p_pidl1);
            tip2::details::shared_data<0,0,0>::complete(*v23 + 8LL);
            tip2::test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::~test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>(&p_pidl1);
            wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
              &v43,
              0);
            wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
              &v41,
              0);
            wil::com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>(&pidla);
            v16 = (const struct _ITEMIDLIST_ABSOLUTE *)pidl1;
          }
          if ( (int)_GetCachedViewStatePropertyBag(v16, pszBagName, dwFlags, riid, ppv) >= 0 )
          {
LABEL_34:
            CachedViewStatePropertyBag = 0;
            goto LABEL_45;
          }
        }
      }
    }
    v24 = (CViewStatePropertyBag *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v24 )
    {
      v25 = CViewStatePropertyBag::CViewStatePropertyBag(v24);
      v41 = v25;
      v26 = v25;
      if ( v25 )
      {
        v27 = CViewStatePropertyBag::Init(v25, (const struct _ITEMIDLIST_ABSOLUTE *)pidl1, pszBagName, dwFlags);
        CachedViewStatePropertyBag = v27;
        if ( v27 >= 0 )
        {
          v30 = (**(__int64 (__fastcall ***)(struct CViewStatePropertyBag *, const IID *const, void **))v26)(
                  v26,
                  riid,
                  ppv);
          CachedViewStatePropertyBag = v30;
          if ( v30 >= 0 )
          {
            _AddCachedViewStatePropertyBag(v26);
            wil::com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>::~com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>(&v41);
            CachedViewStatePropertyBag = 0;
            goto LABEL_45;
          }
          v28 = (unsigned int)v30;
          v29 = 1375;
        }
        else
        {
          v28 = (unsigned int)v27;
          v29 = 1374;
        }
LABEL_44:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"shell\\shlwapi\\propbagadv.cpp",
          (const char *)v28,
          (int)v35);
        wil::com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>::~com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>(&v41);
        goto LABEL_45;
      }
    }
    else
    {
      v41 = 0;
    }
    CachedViewStatePropertyBag = -2147024882;
    v29 = 1373;
    v28 = 2147942414LL;
    goto LABEL_44;
  }
  pidla = 0;
  v41 = 0;
  if ( pidl && SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v41) >= 0 )
  {
    v40 = 0;
    if ( (*(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *, void **))(*(_QWORD *)v41 + 24LL))(
           v41,
           0,
           &BHID_SFObject,
           &GUID_9d264146_a94f_4195_9f9f_3bb12ce0c955,
           &v40) >= 0 )
    {
      if ( (*(int (__fastcall **)(void *, LPITEMIDLIST *))(*(_QWORD *)v40 + 24LL))(v40, &pidla) >= 0 )
        pidl = pidla;
      (*(void (**)(void))(*(_QWORD *)v40 + 16LL))();
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
  }
  CachedViewStatePropertyBag = _GetCachedViewStatePropertyBag(
                                 (const struct _ITEMIDLIST_ABSOLUTE *)pidl,
                                 pszBagName,
                                 dwFlags,
                                 riid,
                                 ppv);
  if ( CachedViewStatePropertyBag < 0 )
  {
    v31 = (CViewStatePropertyBag *)operator new(0xA8u);
    if ( v31 && (v32 = CViewStatePropertyBag::CViewStatePropertyBag(v31), (v33 = v32) != 0) )
    {
      CachedViewStatePropertyBag = CViewStatePropertyBag::Init(
                                     v32,
                                     (const struct _ITEMIDLIST_ABSOLUTE *)pidl,
                                     pszBagName,
                                     dwFlags);
      if ( CachedViewStatePropertyBag >= 0 )
      {
        CachedViewStatePropertyBag = (**(__int64 (__fastcall ***)(struct CViewStatePropertyBag *, const IID *const, void **))v33)(
                                       v33,
                                       riid,
                                       ppv);
        if ( CachedViewStatePropertyBag >= 0 )
          _AddCachedViewStatePropertyBag(v33);
      }
      (*(void (__fastcall **)(struct CViewStatePropertyBag *))(*(_QWORD *)v33 + 16LL))(v33);
    }
    else
    {
      CachedViewStatePropertyBag = -2147024882;
    }
  }
  ILFree(pidla);
  return CachedViewStatePropertyBag;
}

```

## disassembly

```asm
0x18000f430  push    rbp
0x18000f432  push    rbx
0x18000f433  push    rsi
0x18000f434  push    rdi
0x18000f435  push    r12
0x18000f437  push    r13
0x18000f439  push    r14
0x18000f43b  push    r15
0x18000f43d  lea     rbp, [rsp-17h]
0x18000f442  sub     rsp, 88h
0x18000f449  mov     rax, cs:__security_cookie
0x18000f450  xor     rax, rsp
0x18000f453  mov     [rbp+4Fh+var_50], rax
0x18000f457  mov     r13, [rbp+4Fh+ppv]
0x18000f45b  mov     r12, r9
0x18000f45e  mov     r15d, r8d
0x18000f461  mov     r14, rdx
0x18000f464  mov     rsi, rcx
0x18000f467  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784> `wil::Feature<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::GetImpl(void)'::`2'::impl
0x18000f46e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::__private_IsEnabled(void)
0x18000f473  xor     edi, edi
0x18000f475  test    al, al
0x18000f477  jz      loc_18000F875
0x18000f47d  mov     ecx, edi; pidl
0x18000f47f  mov     [rbp+4Fh+pidl1], rcx
0x18000f483  test    rsi, rsi
0x18000f486  jz      short loc_18000F4D3
0x18000f488  mov     rcx, rsi; pidl
0x18000f48b  call    cs:__imp_ILClone
0x18000f491  mov     rdx, rax
0x18000f494  lea     rcx, [rbp+4Fh+pidl1]
0x18000f498  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18000f49d  mov     rcx, [rbp+4Fh+pidl1]
0x18000f4a1  test    rcx, rcx
0x18000f4a4  jnz     short loc_18000F4D3
0x18000f4a6  mov     rcx, [rbp+57h]; this
0x18000f4aa  lea     r8, aShellShlwapiPr; "shell\\shlwapi\\propbagadv.cpp"
0x18000f4b1  mov     ebx, 8007000Eh
0x18000f4b6  mov     edx, 51Bh; void *
0x18000f4bb  mov     r9d, ebx; char *
0x18000f4be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f4c3  xor     edx, edx
0x18000f4c5  lea     rcx, [rbp+4Fh+pidl1]
0x18000f4c9  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18000f4ce  jmp     loc_18000F99E
0x18000f4d3  mov     [rbp+4Fh+var_70], rdi
0x18000f4d7  test    rcx, rcx
0x18000f4da  jz      loc_18000F7B8
0x18000f4e0  lea     r8, [rbp+4Fh+var_70]; ppv
0x18000f4e4  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000f4eb  call    cs:__imp_SHCreateItemFromIDList
0x18000f4f1  test    eax, eax
0x18000f4f3  js      short loc_18000F55C
0x18000f4f5  mov     rcx, [rbp+4Fh+var_70]
0x18000f4f9  lea     rdx, [rbp+4Fh+var_68]
0x18000f4fd  mov     [rbp+4Fh+var_68], rdi
0x18000f501  lea     r9, _GUID_9d264146_a94f_4195_9f9f_3bb12ce0c955
0x18000f508  mov     [rsp+0C0h+var_A0], rdx
0x18000f50d  lea     r8, BHID_SFObject
0x18000f514  xor     edx, edx
0x18000f516  mov     rax, [rcx]
0x18000f519  mov     rax, [rax+18h]
0x18000f51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f522  test    eax, eax
0x18000f524  js      short loc_18000F553
0x18000f526  mov     rcx, [rbp+4Fh+var_68]
0x18000f52a  lea     rdx, [rbp+4Fh+pidl1]
0x18000f52e  mov     rax, [rcx]
0x18000f531  mov     [rbp+4Fh+var_90], rdx
0x18000f535  lea     rdx, [rbp+4Fh+var_88]
0x18000f539  mov     [rbp+4Fh+var_88], rdi
0x18000f53d  mov     [rbp+4Fh+var_80], 1
0x18000f541  mov     rax, [rax+18h]
0x18000f545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f54a  lea     rcx, [rbp+4Fh+var_90]
0x18000f54e  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18000f553  lea     rcx, [rbp+4Fh+var_68]
0x18000f557  call    ??1?$com_ptr_t@UIViewStateIdentityItem@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>::~com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>(void)
0x18000f55c  mov     rcx, [rbp+4Fh+pidl1]; struct _ITEMIDLIST_ABSOLUTE *
0x18000f560  test    rcx, rcx
0x18000f563  jz      loc_18000F7B8
0x18000f569  mov     r9, r12; struct _GUID *
0x18000f56c  mov     [rsp+0C0h+var_A0], r13; int
0x18000f571  mov     r8d, r15d; unsigned int
0x18000f574  mov     rdx, r14; unsigned __int16 *
0x18000f577  call    ?_GetCachedViewStatePropertyBag@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGKAEBU_GUID@@PEAPEAX@Z; _GetCachedViewStatePropertyBag(_ITEMIDLIST_ABSOLUTE const *,ushort const *,ulong,_GUID const &,void * *)
0x18000f57c  test    eax, eax
0x18000f57e  jns     loc_18000F7B1
0x18000f584  cmp     [rbp+4Fh+pidl1], rdi
0x18000f588  jz      loc_18000F7B8
0x18000f58e  mov     ecx, cs:_tls_index
0x18000f594  mov     rax, gs:58h
0x18000f59d  mov     esi, 10h
0x18000f5a2  mov     rbx, [rax+rcx*8]
0x18000f5a6  cmp     [rsi+rbx], dil
0x18000f5aa  jnz     short loc_18000F5B1
0x18000f5ac  call    __dyn_tls_on_demand_init
0x18000f5b1  mov     eax, 138h
0x18000f5b6  cmp     [rsi+rbx], dil
0x18000f5ba  jnz     short loc_18000F5C6
0x18000f5bc  call    __dyn_tls_on_demand_init
0x18000f5c1  mov     eax, 138h
0x18000f5c6  mov     rdx, [rax+rbx]; pidl2
0x18000f5ca  test    rdx, rdx
0x18000f5cd  jz      short loc_18000F60B
0x18000f5cf  mov     esi, 130h
0x18000f5d4  cmp     [rsi+rbx], rdi
0x18000f5d8  jz      short loc_18000F60B
0x18000f5da  mov     rcx, [rbp+4Fh+pidl1]; pidl1
0x18000f5de  call    cs:__imp_ILIsEqual
0x18000f5e4  test    eax, eax
0x18000f5e6  jz      short loc_18000F60B
0x18000f5e8  mov     rcx, [rsi+rbx]; pidl
0x18000f5ec  call    cs:__imp_ILClone
0x18000f5f2  mov     rdx, rax
0x18000f5f5  lea     rcx, [rbp+4Fh+pidl1]
0x18000f5f9  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18000f5fe  mov     rcx, [rbp+4Fh+pidl1]
0x18000f602  test    rcx, rcx
0x18000f605  jnz     loc_18000F79A
0x18000f60b  lea     rcx, [rbp+4Fh+pidl]
0x18000f60f  mov     [rbp+4Fh+pidl], rdi
0x18000f613  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::ensure_data(void)
0x18000f618  lea     rdx, [rbp+4Fh+var_90]
0x18000f61c  mov     rcx, [rax]
0x18000f61f  add     rcx, 8
0x18000f623  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18000f628  lea     rdx, [rbp+4Fh+var_68]
0x18000f62c  lea     rcx, [rbp+4Fh+pidl]
0x18000f630  call    ??C?$tip_test@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::operator->(void)
0x18000f635  mov     rcx, [rax]
0x18000f638  mov     byte ptr [rcx+110h], 1
0x18000f63f  lea     rcx, [rbp+4Fh+var_68]
0x18000f643  call    ??1?$test_data_control@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::~test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>(void)
0x18000f648  mov     rcx, [rbp+4Fh+pidl1]; pidl
0x18000f64c  call    cs:__imp_ILClone
0x18000f652  mov     [rbp+4Fh+var_68], rax
0x18000f656  mov     rbx, rax
0x18000f659  test    rax, rax
0x18000f65c  jnz     short loc_18000F680
0x18000f65e  mov     rcx, [rbp+57h]; this
0x18000f662  lea     r8, aShellShlwapiPr; "shell\\shlwapi\\propbagadv.cpp"
0x18000f669  mov     ebx, 8007000Eh
0x18000f66e  mov     edx, 543h; void *
0x18000f673  mov     r9d, ebx; char *
0x18000f676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f67b  jmp     loc_18000F71B
0x18000f680  mov     rcx, [rbp+4Fh+pidl1]; pidl
0x18000f684  lea     rax, [rbp+4Fh+var_58]
0x18000f688  lea     rdx, [rbp+4Fh+var_88]; struct _ITEMIDLIST_ABSOLUTE **
0x18000f68c  mov     [rbp+4Fh+var_90], rax
0x18000f690  mov     [rbp+4Fh+var_58], rdi
0x18000f694  mov     [rbp+4Fh+var_88], rdi
0x18000f698  mov     [rbp+4Fh+var_80], 1
0x18000f69c  call    ?NormalizePidlForViewState@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU1@@Z; NormalizePidlForViewState(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x18000f6a1  lea     rcx, [rbp+4Fh+var_90]
0x18000f6a5  mov     edi, eax
0x18000f6a7  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18000f6ac  test    edi, edi
0x18000f6ae  js      loc_18000F734
0x18000f6b4  mov     rdx, [rbp+4Fh+var_58]
0x18000f6b8  test    rdx, rdx
0x18000f6bb  jz      short loc_18000F734
0x18000f6bd  mov     rcx, [rbp+4Fh+pidl1]
0x18000f6c1  mov     [rbp+4Fh+var_58], rcx
0x18000f6c5  lea     rcx, [rbp+4Fh+var_58]
0x18000f6c9  mov     [rbp+4Fh+pidl1], rdx
0x18000f6cd  xor     edx, edx
0x18000f6cf  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18000f6d4  mov     rcx, rbx; pidl
0x18000f6d7  call    ?SetViewStateCachedOriginal@CViewStatePropertyBag@@SAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CViewStatePropertyBag::SetViewStateCachedOriginal(_ITEMIDLIST_ABSOLUTE const *)
0x18000f6dc  mov     ebx, eax
0x18000f6de  test    eax, eax
0x18000f6e0  jns     short loc_18000F6E9
0x18000f6e2  mov     edx, 54Bh
0x18000f6e7  jmp     short loc_18000F6FD
0x18000f6e9  mov     rcx, [rbp+4Fh+pidl1]; pidl
0x18000f6ed  call    ?SetViewStateCachedNormalized@CViewStatePropertyBag@@SAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CViewStatePropertyBag::SetViewStateCachedNormalized(_ITEMIDLIST_ABSOLUTE const *)
0x18000f6f2  mov     ebx, eax
0x18000f6f4  test    eax, eax
0x18000f6f6  jns     short loc_18000F734
0x18000f6f8  mov     edx, 54Ch; void *
0x18000f6fd  mov     rcx, [rbp+57h]; this
0x18000f701  lea     r8, aShellShlwapiPr; "shell\\shlwapi\\propbagadv.cpp"
0x18000f708  mov     r9d, eax; char *
0x18000f70b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f710  xor     edx, edx
0x18000f712  lea     rcx, [rbp+4Fh+var_58]
0x18000f716  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18000f71b  xor     edx, edx
0x18000f71d  lea     rcx, [rbp+4Fh+var_68]
0x18000f721  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18000f726  lea     rcx, [rbp+4Fh+pidl]
0x18000f72a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>(void)
0x18000f72f  jmp     loc_18000F867
0x18000f734  lea     rdx, [rbp+4Fh+var_90]
0x18000f738  lea     rcx, [rbp+4Fh+pidl]
0x18000f73c  call    ??C?$tip_test@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::operator->(void)
0x18000f741  mov     rcx, [rax]
0x18000f744  mov     [rcx+114h], edi
0x18000f74a  lea     rcx, [rbp+4Fh+var_90]
0x18000f74e  call    ??1?$test_data_control@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::~test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>(void)
0x18000f753  lea     rdx, [rbp+4Fh+var_90]
0x18000f757  lea     rcx, [rbp+4Fh+pidl]
0x18000f75b  call    ??C?$tip_test@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::operator->(void)
0x18000f760  mov     rcx, [rax]
0x18000f763  add     rcx, 8
0x18000f767  call    ?complete@?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAAXXZ; tip2::details::shared_data<0,0,0>::complete(void)
0x18000f76c  lea     rcx, [rbp+4Fh+var_90]
0x18000f770  call    ??1?$test_data_control@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>::~test_data_control<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>>(void)
0x18000f775  xor     edx, edx
0x18000f777  lea     rcx, [rbp+4Fh+var_58]
0x18000f77b  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18000f780  xor     edx, edx
0x18000f782  lea     rcx, [rbp+4Fh+var_68]
0x18000f786  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18000f78b  lea     rcx, [rbp+4Fh+pidl]
0x18000f78f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>,wil::err_returncode_policy>(void)
0x18000f794  mov     rcx, [rbp+4Fh+pidl1]; struct _ITEMIDLIST_ABSOLUTE *
0x18000f798  xor     edi, edi
0x18000f79a  mov     r9, r12; struct _GUID *
0x18000f79d  mov     [rsp+0C0h+var_A0], r13; void **
0x18000f7a2  mov     r8d, r15d; unsigned int
0x18000f7a5  mov     rdx, r14; unsigned __int16 *
0x18000f7a8  call    ?_GetCachedViewStatePropertyBag@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGKAEBU_GUID@@PEAPEAX@Z; _GetCachedViewStatePropertyBag(_ITEMIDLIST_ABSOLUTE const *,ushort const *,ulong,_GUID const &,void * *)
0x18000f7ad  test    eax, eax
0x18000f7af  js      short loc_18000F7B8
0x18000f7b1  mov     ebx, edi
0x18000f7b3  jmp     loc_18000F867
0x18000f7b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f7bf  mov     ecx, 0A8h; unsigned __int64
0x18000f7c4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f7c9  test    rax, rax
0x18000f7cc  jz      short loc_18000F83D
0x18000f7ce  mov     rcx, rax; this
0x18000f7d1  call    ??0CViewStatePropertyBag@@QEAA@XZ; CViewStatePropertyBag::CViewStatePropertyBag(void)
0x18000f7d6  mov     [rbp+4Fh+var_68], rax
0x18000f7da  mov     rdi, rax
0x18000f7dd  test    rax, rax
0x18000f7e0  jz      short loc_18000F841
0x18000f7e2  mov     rdx, [rbp+4Fh+pidl1]; struct _ITEMIDLIST_ABSOLUTE *
0x18000f7e6  mov     r9d, r15d; unsigned int
0x18000f7e9  mov     r8, r14; unsigned __int16 *
0x18000f7ec  mov     rcx, rax; this
0x18000f7ef  call    ?Init@CViewStatePropertyBag@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGK@Z; CViewStatePropertyBag::Init(_ITEMIDLIST_ABSOLUTE const *,ushort const *,ulong)
0x18000f7f4  mov     ebx, eax
0x18000f7f6  test    eax, eax
0x18000f7f8  jns     short loc_18000F804
0x18000f7fa  mov     r9d, eax
0x18000f7fd  mov     edx, 55Eh
0x18000f802  jmp     short loc_18000F84E
0x18000f804  mov     rax, [rdi]
0x18000f807  mov     r8, r13
0x18000f80a  mov     rdx, r12
0x18000f80d  mov     rcx, rdi
0x18000f810  mov     rax, [rax]
0x18000f813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f818  mov     ebx, eax
0x18000f81a  test    eax, eax
0x18000f81c  jns     short loc_18000F828
0x18000f81e  mov     r9d, eax
0x18000f821  mov     edx, 55Fh
0x18000f826  jmp     short loc_18000F84E
0x18000f828  mov     rcx, rdi; p
0x18000f82b  call    ?_AddCachedViewStatePropertyBag@@YAXPEAVCViewStatePropertyBag@@@Z; _AddCachedViewStatePropertyBag(CViewStatePropertyBag *)
0x18000f830  lea     rcx, [rbp+4Fh+var_68]
0x18000f834  call    ??1?$com_ptr_t@UIViewStateIdentityItem@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>::~com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>(void)
0x18000f839  xor     ebx, ebx
0x18000f83b  jmp     short loc_18000F867
0x18000f83d  mov     [rbp+4Fh+var_68], rdi
0x18000f841  mov     ebx, 8007000Eh
0x18000f846  mov     edx, 55Dh; void *
0x18000f84b  mov     r9d, ebx; char *
0x18000f84e  mov     rcx, [rbp+57h]; this
0x18000f852  lea     r8, aShellShlwapiPr; "shell\\shlwapi\\propbagadv.cpp"
0x18000f859  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f85e  lea     rcx, [rbp+4Fh+var_68]
0x18000f862  call    ??1?$com_ptr_t@UIViewStateIdentityItem@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>::~com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>(void)
0x18000f867  lea     rcx, [rbp+4Fh+var_70]
0x18000f86b  call    ??1?$com_ptr_t@UIViewStateIdentityItem@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>::~com_ptr_t<IViewStateIdentityItem,wil::err_returncode_policy>(void)
0x18000f870  jmp     loc_18000F4C3
0x18000f875  mov     [rbp+4Fh+pidl], rdi
0x18000f879  mov     [rbp+4Fh+var_68], rdi
0x18000f87d  test    rsi, rsi
0x18000f880  jz      loc_18000F90A
0x18000f886  lea     r8, [rbp+4Fh+var_68]; ppv
0x18000f88a  mov     rcx, rsi; pidl
0x18000f88d  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000f894  call    cs:__imp_SHCreateItemFromIDList
0x18000f89a  test    eax, eax
0x18000f89c  js      short loc_18000F90A
0x18000f89e  mov     rcx, [rbp+4Fh+var_68]
0x18000f8a2  lea     rdx, [rbp+4Fh+var_70]
0x18000f8a6  mov     [rbp+4Fh+var_70], rdi
0x18000f8aa  lea     r9, _GUID_9d264146_a94f_4195_9f9f_3bb12ce0c955
0x18000f8b1  mov     [rsp+0C0h+var_A0], rdx
0x18000f8b6  lea     r8, BHID_SFObject
0x18000f8bd  xor     edx, edx
0x18000f8bf  mov     rax, [rcx]
0x18000f8c2  mov     rax, [rax+18h]
  ... truncated ...
```
