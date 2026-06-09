# CViewStatePropertyBag::s_GetMRUSlots(_ITEMIDLIST_ABSOLUTE const *,ulong,HKEY__ *,ulong * const,ulong,ulong *,int *)

- ea: `0x180005598`
- end: `0x18000594d`
- name: `?s_GetMRUSlots@CViewStatePropertyBag@@CAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAUHKEY__@@QEAKKPEAKPEAH@Z`
- size: `949`
- prototype: `__int64 __usercall@<rax>(LPCITEMIDLIST pidl1@<rcx>, unsigned int@<edx>, HKEY@<r8>, unsigned int *const@<r9>, unsigned int, unsigned int *, int *)`
- caller_count: `3`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000492c`
- `0x180004d10`
- `0x180004ef0`

## callees

- `0x180005598`
- `0x18000d280`
- `0x180012550`
- `0x1800291dc`
- `0x1800292a4`
- `0x180029338`
- `0x1800294d4`
- `0x180029758`
- `0x180029fb0`
- `0x18002a108`
- `0x18002a52c`
- `0x18002b180`
- `0x18002bba4`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800055f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800055f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000591e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000591e`
- `SHELL32!__imp_ILClone` at `0x1800056c6`
- `SHELL32!__imp_ILClone` at `0x180005758`
- `SHELL32!__imp_ILClone` at `0x180005772`
- `SHELL32!__imp_ILClone` at `0x18000581d`
- `SHELL32!__imp_ILClone` at `0x1800056c6`
- `SHELL32!__imp_ILClone` at `0x180005758`
- `SHELL32!__imp_ILClone` at `0x180005772`
- `SHELL32!__imp_ILClone` at `0x18000581d`
- `SHELL32!__imp_ILIsEqual` at `0x18000578b`
- `SHELL32!__imp_ILIsEqual` at `0x18000580b`
- `SHELL32!__imp_ILIsEqual` at `0x18000578b`
- `SHELL32!__imp_ILIsEqual` at `0x18000580b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000561d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000561d`

## pseudocode

```c
__int64 __fastcall CViewStatePropertyBag::s_GetMRUSlots(
        LPCITEMIDLIST pidl1,
        int a2,
        HKEY a3,
        unsigned int *const a4,
        unsigned int a5,
        unsigned int *a6,
        int *a7)
{
  unsigned int *v8; // r13
  char v10; // r12
  HRESULT v11; // edi
  __int64 (__fastcall *v12)(LPVOID, _QWORD, HKEY, const wchar_t *); // rbx
  unsigned int MRUSize; // eax
  void **v14; // rax
  LPCITEMIDLIST v15; // rbx
  bool v16; // zf
  __int64 v17; // r13
  const ITEMIDLIST *v18; // rdx
  char v19; // al
  int v20; // r12d
  LPITEMIDLIST v21; // rax
  LPITEMIDLIST v22; // rax
  BOOL v23; // eax
  const ITEMIDLIST *v24; // rax
  LPITEMIDLIST v25; // rax
  _QWORD *v26; // rax
  unsigned int *v28; // [rsp+38h] [rbp-59h] BYREF
  void *v29; // [rsp+40h] [rbp-51h] BYREF
  int v30; // [rsp+48h] [rbp-49h]
  unsigned int *v31; // [rsp+50h] [rbp-41h]
  int *v32; // [rsp+58h] [rbp-39h]
  LPCITEMIDLIST *p_pidl; // [rsp+60h] [rbp-31h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v34; // [rsp+68h] [rbp-29h] BYREF
  char v35; // [rsp+70h] [rbp-21h]
  LPVOID ppv; // [rsp+78h] [rbp-19h] BYREF
  LPCITEMIDLIST pidl; // [rsp+80h] [rbp-11h] BYREF
  void *v38[2]; // [rsp+88h] [rbp-9h] BYREF

  v8 = a4;
  v31 = a4;
  v30 = a2;
  *a7 = 0;
  v10 = a2;
  v28 = a6;
  v32 = a7;
  AcquireSRWLockExclusive(&g_srwBags);
  ppv = 0;
  v11 = CoCreateInstance(&CLSID_MruPidlList, 0, 1u, &GUID_2fb499a3_cfce_480f_a5f3_2453db7a2b7a, &ppv);
  if ( v11 >= 0 )
  {
    v12 = *(__int64 (__fastcall **)(LPVOID, _QWORD, HKEY, const wchar_t *))(*(_QWORD *)ppv + 24LL);
    MRUSize = CViewStatePropertyBag::s_GetMRUSize(a3);
    v11 = v12(ppv, MRUSize, a3, L"BagMRU");
    if ( v11 < 0 )
    {
LABEL_32:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      goto LABEL_33;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, LPCITEMIDLIST, _QWORD, unsigned int *, unsigned int *))(*(_QWORD *)ppv + 40LL))(
            ppv,
            pidl1,
            a5,
            v8,
            a6);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::GetImpl'::`2'::impl) )
    {
      if ( !v11 || (v10 & 3) != 0 )
      {
        v11 = (*(__int64 (__fastcall **)(LPVOID, LPCITEMIDLIST, unsigned int *, int *))(*(_QWORD *)ppv + 32LL))(
                ppv,
                pidl1,
                v8,
                v32);
      }
      else if ( a5 == 1 )
      {
        v11 = -2147467259;
      }
      goto LABEL_32;
    }
    v29 = 0;
    v14 = tip2::tip_test<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::ensure_data(&v29);
    tip2::details::shared_data<0,0,0>::start((char *)*v14 + 8, v38);
    pidl = 0;
    v38[0] = ILClone(pidl1);
    v15 = (LPCITEMIDLIST)v38[0];
    v16 = v11 == 0;
    if ( v11 >= 0 )
    {
LABEL_21:
      if ( v16 || (v10 & 3) != 0 )
      {
        v11 = (*(__int64 (__fastcall **)(LPVOID, LPCITEMIDLIST, unsigned int *, int *))(*(_QWORD *)ppv + 32LL))(
                ppv,
                v15,
                v8,
                v32);
LABEL_26:
        v26 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::operator->(
                          &v29,
                          &v28);
        tip2::details::shared_data<0,0,0>::complete(*v26 + 8LL);
        tip2::test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::~test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>(&v28);
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          v38,
          0);
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          (void **)&pidl,
          0);
        wil::com_ptr_t<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>,wil::err_returncode_policy>(&v29);
        goto LABEL_32;
      }
LABEL_23:
      if ( a5 == 1 )
        v11 = -2147467259;
      goto LABEL_26;
    }
    if ( (v10 & 3) == 0 )
      goto LABEL_23;
    v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v18 = *(const ITEMIDLIST **)(v17 + 328);
    if ( v18 && *(_QWORD *)(v17 + 320) && ILIsEqual(pidl1, v18) )
    {
      v25 = ILClone(*(LPCITEMIDLIST *)(v17 + 320));
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        (void **)&pidl,
        v25);
      v19 = 1;
    }
    else
    {
      v19 = 0;
    }
    v20 = 0;
    if ( !v19 )
    {
      v34 = 0;
      p_pidl = &pidl;
      v35 = 1;
      v20 = NormalizePidlForViewState(pidl1, &v34);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl);
      if ( v20 < 0 )
      {
        v8 = v31;
LABEL_20:
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::operator->(
                                 &v29,
                                 &v28)
                  + 272LL) = v20;
        tip2::test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::~test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>(&v28);
        v10 = v30;
        v16 = v11 == 0;
        goto LABEL_21;
      }
      if ( pidl )
      {
        v21 = ILClone(pidl1);
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          (void **)(v17 + 328),
          v21);
        v22 = ILClone(pidl);
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          (void **)(v17 + 320),
          v22);
      }
    }
    v23 = ILIsEqual(pidl1, pidl);
    v8 = v31;
    if ( !v23 )
    {
      v11 = (*(__int64 (__fastcall **)(LPVOID, LPCITEMIDLIST, _QWORD, unsigned int *, unsigned int *))(*(_QWORD *)ppv + 40LL))(
              ppv,
              pidl,
              a5,
              v31,
              v28);
      if ( v11 >= 0 )
      {
        v24 = v15;
        v15 = pidl;
        v38[0] = (void *)pidl;
        pidl = v24;
      }
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::operator->(
                               &v29,
                               &v28)
                + 276LL) = v11;
      tip2::test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::~test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>(&v28);
    }
    goto LABEL_20;
  }
LABEL_33:
  ReleaseSRWLockExclusive(&g_srwBags);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005598  mov     [rsp-8+arg_8], rbx
0x18000559d  push    rbp
0x18000559e  push    rsi
0x18000559f  push    rdi
0x1800055a0  push    r12
0x1800055a2  push    r13
0x1800055a4  push    r14
0x1800055a6  push    r15
0x1800055a8  lea     rbp, [rsp-0Fh]
0x1800055ad  sub     rsp, 0A0h
0x1800055b4  mov     rax, cs:__security_cookie
0x1800055bb  xor     rax, rsp
0x1800055be  mov     [rbp+3Fh+var_38], rax
0x1800055c2  mov     rax, [rbp+3Fh+arg_30]
0x1800055c6  mov     r14, rcx
0x1800055c9  mov     r15, [rbp+3Fh+arg_28]
0x1800055cd  lea     rcx, ?g_srwBags@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800055d4  mov     r13, r9
0x1800055d7  mov     [rbp+3Fh+var_80], r9
0x1800055db  mov     rsi, r8
0x1800055de  mov     [rbp+3Fh+var_88], edx
0x1800055e1  mov     dword ptr [rax], 0
0x1800055e7  mov     r12d, edx
0x1800055ea  mov     [rbp+3Fh+var_98], r15
0x1800055ee  mov     [rbp+3Fh+var_78], rax
0x1800055f2  call    cs:__imp_AcquireSRWLockExclusive
0x1800055f8  xor     edx, edx; pUnkOuter
0x1800055fa  mov     [rbp+3Fh+var_58], 0
0x180005602  lea     rax, [rbp+3Fh+var_58]
0x180005606  lea     r9, _GUID_2fb499a3_cfce_480f_a5f3_2453db7a2b7a; riid
0x18000560d  mov     [rsp+0D0h+ppv], rax; ppv
0x180005612  lea     rcx, CLSID_MruPidlList; rclsid
0x180005619  lea     r8d, [rdx+1]; dwClsContext
0x18000561d  call    cs:__imp_CoCreateInstance
0x180005623  mov     edi, eax
0x180005625  test    eax, eax
0x180005627  js      loc_180005917
0x18000562d  mov     rax, [rbp+3Fh+var_58]
0x180005631  mov     rcx, [rax]
0x180005634  mov     rbx, [rcx+18h]
0x180005638  mov     rcx, rsi; HKEY
0x18000563b  call    ?s_GetMRUSize@CViewStatePropertyBag@@SAKPEAUHKEY__@@@Z; CViewStatePropertyBag::s_GetMRUSize(HKEY__ *)
0x180005640  mov     rcx, [rbp+3Fh+var_58]
0x180005644  lea     r9, aBagmru; "BagMRU"
0x18000564b  mov     edx, eax
0x18000564d  mov     r8, rsi
0x180005650  mov     rax, rbx
0x180005653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005658  mov     edi, eax
0x18000565a  test    eax, eax
0x18000565c  js      loc_180005907
0x180005662  mov     rcx, [rbp+3Fh+var_58]
0x180005666  mov     r9, r13
0x180005669  mov     [rsp+0D0h+ppv], r15
0x18000566e  mov     rdx, r14
0x180005671  mov     r15d, [rbp+3Fh+arg_20]
0x180005675  mov     r8d, r15d
0x180005678  mov     rax, [rcx]
0x18000567b  mov     rax, [rax+28h]
0x18000567f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005684  mov     edi, eax
0x180005686  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784> `wil::Feature<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::GetImpl(void)'::`2'::impl
0x18000568d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableViewStatePidlNormalization_55063784>::__private_IsEnabled(void)
0x180005692  test    al, al
0x180005694  jz      loc_1800058D4
0x18000569a  lea     rcx, [rbp+3Fh+var_90]
0x18000569e  mov     [rbp+3Fh+var_90], 0
0x1800056a6  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::ensure_data(void)
0x1800056ab  lea     rdx, [rbp+3Fh+var_48]
0x1800056af  mov     rcx, [rax]
0x1800056b2  add     rcx, 8
0x1800056b6  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800056bb  mov     rcx, r14; pidl
0x1800056be  mov     [rbp+3Fh+pidl], 0
0x1800056c6  call    cs:__imp_ILClone
0x1800056cc  mov     [rbp+3Fh+var_48], rax
0x1800056d0  mov     rbx, rax
0x1800056d3  test    edi, edi
0x1800056d5  jns     loc_180005860
0x1800056db  test    r12b, 3
0x1800056df  jz      loc_180005868
0x1800056e5  mov     rax, gs:58h
0x1800056ee  mov     ecx, cs:_tls_index
0x1800056f4  mov     [rbp+3Fh+var_A0], 0
0x1800056f8  mov     r13, [rax+rcx*8]
0x1800056fc  mov     eax, 148h
0x180005701  mov     rdx, [rax+r13]; pidl2
0x180005705  test    rdx, rdx
0x180005708  jnz     loc_1800057F6
0x18000570e  mov     esi, 140h
0x180005713  mov     al, [rbp+3Fh+var_A0]
0x180005716  xor     r12d, r12d
0x180005719  test    al, al
0x18000571b  jnz     short loc_180005784
0x18000571d  lea     rax, [rbp+3Fh+pidl]
0x180005721  mov     [rbp+3Fh+var_68], r12
0x180005725  lea     rdx, [rbp+3Fh+var_68]; struct _ITEMIDLIST_ABSOLUTE **
0x180005729  mov     [rbp+3Fh+var_70], rax
0x18000572d  mov     rcx, r14; pidl
0x180005730  mov     [rbp+3Fh+var_60], 1
0x180005734  call    ?NormalizePidlForViewState@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU1@@Z; NormalizePidlForViewState(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x180005739  lea     rcx, [rbp+3Fh+var_70]
0x18000573d  mov     r12d, eax
0x180005740  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180005745  test    r12d, r12d
0x180005748  js      loc_180005836
0x18000574e  cmp     [rbp+3Fh+pidl], 0
0x180005753  jz      short loc_180005784
0x180005755  mov     rcx, r14; pidl
0x180005758  call    cs:__imp_ILClone
0x18000575e  mov     ecx, 148h
0x180005763  mov     rdx, rax
0x180005766  add     rcx, r13
0x180005769  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18000576e  mov     rcx, [rbp+3Fh+pidl]; pidl
0x180005772  call    cs:__imp_ILClone
0x180005778  mov     rdx, rax
0x18000577b  lea     rcx, [rsi+r13]
0x18000577f  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x180005784  mov     rdx, [rbp+3Fh+pidl]; pidl2
0x180005788  mov     rcx, r14; pidl1
0x18000578b  call    cs:__imp_ILIsEqual
0x180005791  mov     r13, [rbp+3Fh+var_80]
0x180005795  test    eax, eax
0x180005797  jnz     loc_18000583A
0x18000579d  mov     rcx, [rbp+3Fh+var_58]
0x1800057a1  mov     r9, r13
0x1800057a4  mov     rdx, [rbp+3Fh+var_98]
0x1800057a8  mov     r8d, r15d
0x1800057ab  mov     [rsp+0D0h+ppv], rdx
0x1800057b0  mov     rdx, [rbp+3Fh+pidl]
0x1800057b4  mov     rax, [rcx]
0x1800057b7  mov     rax, [rax+28h]
0x1800057bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c0  mov     edi, eax
0x1800057c2  test    eax, eax
0x1800057c4  js      short loc_1800057D5
0x1800057c6  mov     rax, rbx
0x1800057c9  mov     rbx, [rbp+3Fh+pidl]
0x1800057cd  mov     [rbp+3Fh+var_48], rbx
0x1800057d1  mov     [rbp+3Fh+pidl], rax
0x1800057d5  lea     rdx, [rbp+3Fh+var_98]
0x1800057d9  lea     rcx, [rbp+3Fh+var_90]
0x1800057dd  call    ??C?$tip_test@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::operator->(void)
0x1800057e2  mov     rcx, [rax]
0x1800057e5  mov     [rcx+114h], edi
0x1800057eb  lea     rcx, [rbp+3Fh+var_98]
0x1800057ef  call    ??1?$test_data_control@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::~test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>(void)
0x1800057f4  jmp     short loc_18000583A
0x1800057f6  mov     eax, 140h
0x1800057fb  mov     esi, eax
0x1800057fd  cmp     qword ptr [rax+r13], 0
0x180005802  jz      loc_180005713
0x180005808  mov     rcx, r14; pidl1
0x18000580b  call    cs:__imp_ILIsEqual
0x180005811  test    eax, eax
0x180005813  jz      loc_180005713
0x180005819  mov     rcx, [rsi+r13]; pidl
0x18000581d  call    cs:__imp_ILClone
0x180005823  mov     rdx, rax
0x180005826  lea     rcx, [rbp+3Fh+pidl]
0x18000582a  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x18000582f  mov     al, 1
0x180005831  jmp     loc_180005716
0x180005836  mov     r13, [rbp+3Fh+var_80]
0x18000583a  lea     rdx, [rbp+3Fh+var_98]
0x18000583e  lea     rcx, [rbp+3Fh+var_90]
0x180005842  call    ??C?$tip_test@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::operator->(void)
0x180005847  mov     rcx, [rax]
0x18000584a  mov     [rcx+110h], r12d
0x180005851  lea     rcx, [rbp+3Fh+var_98]
0x180005855  call    ??1?$test_data_control@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::~test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>(void)
0x18000585a  mov     r12d, [rbp+3Fh+var_88]
0x18000585e  test    edi, edi
0x180005860  jz      short loc_180005875
0x180005862  test    r12b, 3
0x180005866  jnz     short loc_180005875
0x180005868  cmp     r15d, 1
0x18000586c  jnz     short loc_180005891
0x18000586e  mov     edi, 80004005h
0x180005873  jmp     short loc_180005891
0x180005875  mov     rcx, [rbp+3Fh+var_58]
0x180005879  mov     r8, r13
0x18000587c  mov     r9, [rbp+3Fh+var_78]
0x180005880  mov     rdx, rbx
0x180005883  mov     rax, [rcx]
0x180005886  mov     rax, [rax+20h]
0x18000588a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000588f  mov     edi, eax
0x180005891  lea     rdx, [rbp+3Fh+var_98]
0x180005895  lea     rcx, [rbp+3Fh+var_90]
0x180005899  call    ??C?$tip_test@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::operator->(void)
0x18000589e  mov     rcx, [rax]
0x1800058a1  add     rcx, 8
0x1800058a5  call    ?complete@?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAAXXZ; tip2::details::shared_data<0,0,0>::complete(void)
0x1800058aa  lea     rcx, [rbp+3Fh+var_98]
0x1800058ae  call    ??1?$test_data_control@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>::~test_data_control<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>>(void)
0x1800058b3  xor     edx, edx
0x1800058b5  lea     rcx, [rbp+3Fh+var_48]
0x1800058b9  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x1800058be  xor     edx, edx
0x1800058c0  lea     rcx, [rbp+3Fh+pidl]
0x1800058c4  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x1800058c9  lea     rcx, [rbp+3Fh+var_90]
0x1800058cd  call    ??1?$com_ptr_t@V?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>,wil::err_returncode_policy>(void)
0x1800058d2  jmp     short loc_180005907
0x1800058d4  test    edi, edi
0x1800058d6  jz      short loc_1800058EB
0x1800058d8  test    r12b, 3
0x1800058dc  jnz     short loc_1800058EB
0x1800058de  cmp     r15d, 1
0x1800058e2  jnz     short loc_180005907
0x1800058e4  mov     edi, 80004005h
0x1800058e9  jmp     short loc_180005907
0x1800058eb  mov     rcx, [rbp+3Fh+var_58]
0x1800058ef  mov     r8, r13
0x1800058f2  mov     r9, [rbp+3Fh+var_78]
0x1800058f6  mov     rdx, r14
0x1800058f9  mov     rax, [rcx]
0x1800058fc  mov     rax, [rax+20h]
0x180005900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005905  mov     edi, eax
0x180005907  mov     rcx, [rbp+3Fh+var_58]
0x18000590b  mov     rax, [rcx]
0x18000590e  mov     rax, [rax+10h]
0x180005912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005917  lea     rcx, ?g_srwBags@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000591e  call    cs:__imp_ReleaseSRWLockExclusive
0x180005924  mov     eax, edi
0x180005926  mov     rcx, [rbp+3Fh+var_38]
0x18000592a  xor     rcx, rsp; StackCookie
0x18000592d  call    __security_check_cookie
0x180005932  mov     rbx, [rsp+0D0h+arg_8]
0x18000593a  add     rsp, 0A0h
0x180005941  pop     r15
0x180005943  pop     r14
0x180005945  pop     r13
0x180005947  pop     r12
0x180005949  pop     rdi
0x18000594a  pop     rsi
0x18000594b  pop     rbp
0x18000594c  retn
```
