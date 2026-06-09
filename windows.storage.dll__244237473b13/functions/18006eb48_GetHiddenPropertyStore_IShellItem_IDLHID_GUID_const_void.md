# GetHiddenPropertyStore(IShellItem *,IDLHID,_GUID const &,void * *)

- ea: `0x18006eb48`
- end: `0x18006f245`
- name: `?GetHiddenPropertyStore@@YAJPEAUIShellItem@@W4IDLHID@@AEBU_GUID@@PEAPEAX@Z`
- size: `1789`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007c810`
- `0x1802513f0`
- `0x1804885c0`

## callees

- `0x180009fc0`
- `0x1800304e0`
- `0x180038f50`
- `0x180049110`
- `0x18006eb48`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ec07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006eccf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ed76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ef2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006efcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f0f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f1b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ec07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006eccf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ed76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ef2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006efcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f0f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f1b9`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006ec52`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006ede3`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006ec52`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006ede3`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall GetHiddenPropertyStore(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *, void **); // rbx
  void *v11; // rcx
  _WORD *v12; // rax
  _WORD *v13; // rsi
  void **v14; // rax
  HRESULT v15; // eax
  int v16; // eax
  int v17; // eax
  void *v18; // rcx
  void *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  void *v23; // rcx
  void *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int16 v27; // di
  HRESULT v28; // eax
  void *v29; // rbx
  __int64 (__fastcall *v30)(void *, GUID *, __int64 *); // rdi
  int v31; // eax
  int v32; // eax
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  void *v45; // rcx
  void *v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  void *v50; // rcx
  void *v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  void *v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  void *v57; // rcx
  bool v58; // zf
  __int64 v59; // rdx
  int v60; // [rsp+20h] [rbp-60h]
  void *v61; // [rsp+38h] [rbp-48h] BYREF
  char v62; // [rsp+40h] [rbp-40h]
  void *ppv; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-30h]
  __int64 v65; // [rsp+58h] [rbp-28h] BYREF
  __int64 v66; // [rsp+60h] [rbp-20h] BYREF
  __int64 v67; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a4 = 0;
  v65 = 0;
  v6 = **a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  v7 = v6(a1, &GUID_b3a4b685_b685_4805_99d9_5dead2873236, &v65);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)(unsigned int)v7,
      v60);
    v35 = v65;
    if ( v65 )
    {
      v65 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    return v8;
  }
  v66 = 0;
  pv = 0;
  v9 = v65;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, void **))(*(_QWORD *)v65 + 32LL);
  v61 = 0;
  v62 = 1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  v8 = v10(v9, 0, &v66, &v61);
  if ( v62 )
  {
    v11 = pv;
    pv = v61;
    if ( v11 )
      CoTaskMemFree(v11);
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)v8,
      v60);
LABEL_87:
    v57 = pv;
    v58 = pv == 0;
    pv = 0;
    if ( !v58 )
      CoTaskMemFree(v57);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    return v8;
  }
  v12 = (_WORD *)ILFindHiddenIDOn(pv, 3203334183LL, 1);
  v13 = v12;
  if ( v12 )
  {
    v27 = *v12;
    if ( *v12 < 8u )
    {
      v8 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
        (const char *)0x80070216LL,
        v60);
      v54 = pv;
      pv = 0;
      if ( v54 )
        CoTaskMemFree(v54);
      v55 = v66;
      if ( v66 )
      {
        v66 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      v56 = v65;
      if ( v65 )
      {
        v65 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      return v8;
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v28 = PSCreateMemoryPropertyStore(&GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &ppv);
    v8 = v28;
    if ( v28 < 0 )
    {
      v59 = 160;
    }
    else
    {
      v28 = (*(__int64 (__fastcall **)(void *, _WORD *, _QWORD))(*(_QWORD *)ppv + 32LL))(
              ppv,
              v13 + 4,
              (unsigned __int16)(v27 - 8));
      v8 = v28;
      if ( v28 >= 0 )
      {
        v67 = 0;
        v29 = ppv;
        v30 = **(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
        v31 = v30(v29, &GUID_8e6433f3_db66_457e_a54c_351e9a83f7c5, &v67);
        v8 = v31;
        if ( v31 >= 0 )
        {
          v32 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 24LL))(v67, 2);
          v8 = v32;
          if ( v32 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA7,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
              (const char *)(unsigned int)v32,
              v60);
            v49 = v67;
            if ( v67 )
            {
              v67 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
            }
            v50 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v50 + 16LL))(v50);
            }
            v51 = pv;
            pv = 0;
            if ( v51 )
              CoTaskMemFree(v51);
            v52 = v66;
            if ( v66 )
            {
              v66 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
            }
            v53 = v65;
            if ( v65 )
            {
              v65 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
            }
          }
          else
          {
            v33 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))ppv)(
                    ppv,
                    &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                    a4);
            v8 = v33;
            if ( v33 >= 0 )
            {
              v34 = v67;
              if ( v67 )
              {
                v67 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              }
              goto LABEL_10;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA9,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
              (const char *)(unsigned int)v33,
              v60);
            v40 = v67;
            if ( v67 )
            {
              v67 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
            }
            v41 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
            }
            v42 = pv;
            pv = 0;
            if ( v42 )
              CoTaskMemFree(v42);
            v43 = v66;
            if ( v66 )
            {
              v66 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            }
            v44 = v65;
            if ( v65 )
            {
              v65 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            }
          }
          return v8;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA6,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
          (const char *)(unsigned int)v31,
          v60);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
        goto LABEL_95;
      }
      v59 = 163;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v59,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)(unsigned int)v28,
      v60);
LABEL_95:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    goto LABEL_87;
  }
  ppv = 0;
  v14 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&ppv);
  v15 = PSCreateMemoryPropertyStore(&GUID_8e6433f3_db66_457e_a54c_351e9a83f7c5, v14);
  v8 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)(unsigned int)v15,
      v60);
    v36 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
    }
    v37 = pv;
    pv = 0;
    if ( v37 )
      CoTaskMemFree(v37);
    v38 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v65;
    if ( v65 )
    {
      v65 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    return v8;
  }
  v16 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 2);
  v8 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)(unsigned int)v16,
      v60);
    v45 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v45 + 16LL))(v45);
    }
    v46 = pv;
    pv = 0;
    if ( v46 )
      CoTaskMemFree(v46);
    v47 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v48 = v65;
    if ( v65 )
    {
      v65 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    return v8;
  }
  v17 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))ppv)(ppv, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, a4);
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)(unsigned int)v17,
      v60);
    v23 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = pv;
    pv = 0;
    if ( v24 )
      CoTaskMemFree(v24);
    v25 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v65;
    if ( v65 )
    {
      v65 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    return v8;
  }
LABEL_10:
  v18 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = pv;
  pv = 0;
  if ( v19 )
    CoTaskMemFree(v19);
  v20 = v66;
  if ( v66 )
  {
    v66 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  v21 = v65;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x18006eb48  mov     [rsp-28h+arg_8], rbx
0x18006eb4d  push    rbp
0x18006eb4e  push    rsi
0x18006eb4f  push    rdi
0x18006eb50  push    r14
0x18006eb52  push    r15
0x18006eb54  mov     rbp, rsp
0x18006eb57  sub     rsp, 80h
0x18006eb5e  mov     rax, cs:__security_cookie
0x18006eb65  xor     rax, rsp
0x18006eb68  mov     [rbp+var_10], rax
0x18006eb6c  mov     r14, r9
0x18006eb6f  mov     rdi, rcx
0x18006eb72  xor     r15d, r15d
0x18006eb75  mov     [r9], r15
0x18006eb78  mov     [rbp+var_28], r15
0x18006eb7c  mov     rax, [rcx]
0x18006eb7f  mov     rbx, [rax]
0x18006eb82  lea     rcx, [rbp+var_28]
0x18006eb86  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006eb8b  lea     r8, [rbp+var_28]
0x18006eb8f  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x18006eb96  mov     rcx, rdi
0x18006eb99  mov     rax, rbx
0x18006eb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eba1  mov     ebx, eax
0x18006eba3  test    eax, eax
0x18006eba5  js      loc_18006EEB7
0x18006ebab  mov     [rbp+var_20], r15
0x18006ebaf  mov     [rbp+pv], r15
0x18006ebb3  mov     rdi, [rbp+var_28]
0x18006ebb7  mov     rax, [rdi]
0x18006ebba  mov     rbx, [rax+20h]
0x18006ebbe  lea     rax, [rbp+pv]
0x18006ebc2  mov     [rbp+var_50], rax
0x18006ebc6  mov     [rbp+var_48], r15
0x18006ebca  mov     [rbp+var_40], 1
0x18006ebce  lea     rcx, [rbp+var_20]
0x18006ebd2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ebd7  lea     r9, [rbp+var_48]
0x18006ebdb  lea     r8, [rbp+var_20]
0x18006ebdf  xor     edx, edx
0x18006ebe1  mov     rcx, rdi
0x18006ebe4  mov     rax, rbx
0x18006ebe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ebec  mov     ebx, eax
0x18006ebee  cmp     [rbp+var_40], r15b
0x18006ebf2  jz      short loc_18006EC13
0x18006ebf4  mov     r8, [rbp+var_50]
0x18006ebf8  mov     rcx, [r8]; pv
0x18006ebfb  mov     rdx, [rbp+var_48]
0x18006ebff  mov     [r8], rdx
0x18006ec02  test    rcx, rcx
0x18006ec05  jz      short loc_18006EC13
0x18006ec07  call    cs:__imp_CoTaskMemFree
0x18006ec0e  nop     dword ptr [rax+rax+00h]
0x18006ec13  test    ebx, ebx
0x18006ec15  js      loc_18006F1DE
0x18006ec1b  mov     edx, 0BEEF0027h
0x18006ec20  mov     r8d, 1
0x18006ec26  mov     rcx, [rbp+pv]
0x18006ec2a  call    ?ILFindHiddenIDOn@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@H@Z; ILFindHiddenIDOn(_ITEMIDLIST_RELATIVE const *,IDLHID,int)
0x18006ec2f  mov     rsi, rax
0x18006ec32  test    rax, rax
0x18006ec35  jnz     loc_18006EDBE
0x18006ec3b  mov     [rbp+ppv], r15
0x18006ec3f  lea     rcx, [rbp+ppv]
0x18006ec43  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>)
0x18006ec48  mov     rdx, rax; ppv
0x18006ec4b  lea     rcx, _GUID_8e6433f3_db66_457e_a54c_351e9a83f7c5; riid
0x18006ec52  call    cs:__imp_PSCreateMemoryPropertyStore
0x18006ec59  nop     dword ptr [rax+rax+00h]
0x18006ec5e  mov     ebx, eax
0x18006ec60  test    eax, eax
0x18006ec62  js      loc_18006EEEF
0x18006ec68  mov     rcx, [rbp+ppv]
0x18006ec6c  mov     rax, [rcx]
0x18006ec6f  lea     edx, [rsi+2]
0x18006ec72  mov     rax, [rax+18h]
0x18006ec76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ec7b  mov     ebx, eax
0x18006ec7d  test    eax, eax
0x18006ec7f  js      loc_18006F015
0x18006ec85  mov     rcx, [rbp+ppv]
0x18006ec89  mov     rax, [rcx]
0x18006ec8c  mov     r8, r14
0x18006ec8f  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18006ec96  mov     rax, [rax]
0x18006ec99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ec9e  mov     ebx, eax
0x18006eca0  test    eax, eax
0x18006eca2  js      loc_18006ED36
0x18006eca8  mov     rcx, [rbp+ppv]
0x18006ecac  test    rcx, rcx
0x18006ecaf  jz      short loc_18006ECC2
0x18006ecb1  mov     [rbp+ppv], r15
0x18006ecb5  mov     rax, [rcx]
0x18006ecb8  mov     rax, [rax+10h]
0x18006ecbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ecc1  nop
0x18006ecc2  mov     rcx, [rbp+pv]; pv
0x18006ecc6  mov     [rbp+pv], r15
0x18006ecca  test    rcx, rcx
0x18006eccd  jz      short loc_18006ECDC
0x18006eccf  call    cs:__imp_CoTaskMemFree
0x18006ecd6  nop     dword ptr [rax+rax+00h]
0x18006ecdb  nop
0x18006ecdc  mov     rcx, [rbp+var_20]
0x18006ece0  test    rcx, rcx
0x18006ece3  jz      short loc_18006ECF6
0x18006ece5  mov     [rbp+var_20], r15
0x18006ece9  mov     rax, [rcx]
0x18006ecec  mov     rax, [rax+10h]
0x18006ecf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ecf5  nop
0x18006ecf6  mov     rcx, [rbp+var_28]
0x18006ecfa  test    rcx, rcx
0x18006ecfd  jz      short loc_18006ED10
0x18006ecff  mov     [rbp+var_28], r15
0x18006ed03  mov     rax, [rcx]
0x18006ed06  mov     rax, [rax+10h]
0x18006ed0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed0f  nop
0x18006ed10  xor     eax, eax
0x18006ed12  mov     rcx, [rbp+var_10]
0x18006ed16  xor     rcx, rsp; StackCookie
0x18006ed19  call    __security_check_cookie
0x18006ed1e  mov     rbx, [rsp+80h+arg_8]
0x18006ed26  add     rsp, 80h
0x18006ed2d  pop     r15
0x18006ed2f  pop     r14
0x18006ed31  pop     rdi
0x18006ed32  pop     rsi
0x18006ed33  pop     rbp
0x18006ed34  retn
0x18006ed36  mov     rcx, [rbp+28h]; this
0x18006ed3a  mov     r9d, ebx; char *
0x18006ed3d  lea     r8, aOnecoreuapInte_36; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18006ed44  mov     edx, 95h; void *
0x18006ed49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ed4e  nop
0x18006ed4f  mov     rcx, [rbp+ppv]
0x18006ed53  test    rcx, rcx
0x18006ed56  jz      short loc_18006ED69
0x18006ed58  mov     [rbp+ppv], r15
0x18006ed5c  mov     rax, [rcx]
0x18006ed5f  mov     rax, [rax+10h]
0x18006ed63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed68  nop
0x18006ed69  mov     rcx, [rbp+pv]; pv
0x18006ed6d  mov     [rbp+pv], r15
0x18006ed71  test    rcx, rcx
0x18006ed74  jz      short loc_18006ED83
0x18006ed76  call    cs:__imp_CoTaskMemFree
0x18006ed7d  nop     dword ptr [rax+rax+00h]
0x18006ed82  nop
0x18006ed83  mov     rcx, [rbp+var_20]
0x18006ed87  test    rcx, rcx
0x18006ed8a  jz      short loc_18006ED9D
0x18006ed8c  mov     [rbp+var_20], r15
0x18006ed90  mov     rax, [rcx]
0x18006ed93  mov     rax, [rax+10h]
0x18006ed97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed9c  nop
0x18006ed9d  mov     rcx, [rbp+var_28]
0x18006eda1  test    rcx, rcx
0x18006eda4  jz      short loc_18006EDB7
0x18006eda6  mov     [rbp+var_28], r15
0x18006edaa  mov     rax, [rcx]
0x18006edad  mov     rax, [rax+10h]
0x18006edb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006edb6  nop
0x18006edb7  mov     eax, ebx
0x18006edb9  jmp     loc_18006ED12
0x18006edbe  movzx   edi, word ptr [rax]
0x18006edc1  cmp     di, 8
0x18006edc5  jb      loc_18006F13B
0x18006edcb  mov     [rbp+ppv], r15
0x18006edcf  lea     rcx, [rbp+ppv]
0x18006edd3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006edd8  lea     rdx, [rbp+ppv]; ppv
0x18006eddc  lea     rcx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917; riid
0x18006ede3  call    cs:__imp_PSCreateMemoryPropertyStore
0x18006edea  nop     dword ptr [rax+rax+00h]
0x18006edef  mov     ebx, eax
0x18006edf1  test    eax, eax
0x18006edf3  js      loc_18006F1F8
0x18006edf9  mov     rcx, [rbp+ppv]
0x18006edfd  mov     rax, [rcx]
0x18006ee00  sub     di, 8
0x18006ee04  movzx   r8d, di
0x18006ee08  lea     rdx, [rsi+8]
0x18006ee0c  mov     rax, [rax+20h]
0x18006ee10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee15  mov     ebx, eax
0x18006ee17  test    eax, eax
0x18006ee19  js      loc_18006F1FF
0x18006ee1f  mov     [rbp+var_18], r15
0x18006ee23  mov     rbx, [rbp+ppv]
0x18006ee27  mov     rax, [rbx]
0x18006ee2a  mov     rdi, [rax]
0x18006ee2d  lea     rcx, [rbp+var_18]
0x18006ee31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ee36  lea     r8, [rbp+var_18]
0x18006ee3a  lea     rdx, _GUID_8e6433f3_db66_457e_a54c_351e9a83f7c5
0x18006ee41  mov     rcx, rbx
0x18006ee44  mov     rax, rdi
0x18006ee47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee4c  mov     ebx, eax
0x18006ee4e  test    eax, eax
0x18006ee50  js      loc_18006F21D
0x18006ee56  mov     rcx, [rbp+var_18]
0x18006ee5a  mov     rax, [rcx]
0x18006ee5d  mov     edx, 2
0x18006ee62  mov     rax, [rax+18h]
0x18006ee66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee6b  mov     ebx, eax
0x18006ee6d  test    eax, eax
0x18006ee6f  js      loc_18006F09B
0x18006ee75  mov     rcx, [rbp+ppv]
0x18006ee79  mov     rax, [rcx]
0x18006ee7c  mov     r8, r14
0x18006ee7f  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18006ee86  mov     rax, [rax]
0x18006ee89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee8e  mov     ebx, eax
0x18006ee90  test    eax, eax
0x18006ee92  js      loc_18006EF75
0x18006ee98  mov     rcx, [rbp+var_18]
0x18006ee9c  test    rcx, rcx
0x18006ee9f  jz      short loc_18006EEB2
0x18006eea1  mov     [rbp+var_18], r15
0x18006eea5  mov     rax, [rcx]
0x18006eea8  mov     rax, [rax+10h]
0x18006eeac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eeb1  nop
0x18006eeb2  jmp     loc_18006ECA8
0x18006eeb7  mov     rcx, [rbp+28h]; this
0x18006eebb  mov     r9d, ebx; char *
0x18006eebe  lea     r8, aOnecoreuapInte_36; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18006eec5  mov     edx, 89h; void *
0x18006eeca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006eecf  nop
0x18006eed0  mov     rcx, [rbp+var_28]
0x18006eed4  test    rcx, rcx
0x18006eed7  jz      short loc_18006EEEA
0x18006eed9  mov     [rbp+var_28], r15
0x18006eedd  mov     rax, [rcx]
0x18006eee0  mov     rax, [rax+10h]
0x18006eee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eee9  nop
0x18006eeea  jmp     loc_18006EDB7
0x18006eeef  mov     rcx, [rbp+28h]; this
0x18006eef3  mov     r9d, ebx; char *
0x18006eef6  lea     r8, aOnecoreuapInte_36; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18006eefd  mov     edx, 93h; void *
0x18006ef02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ef07  nop
0x18006ef08  mov     rcx, [rbp+ppv]
0x18006ef0c  test    rcx, rcx
0x18006ef0f  jz      short loc_18006EF22
0x18006ef11  mov     [rbp+ppv], r15
0x18006ef15  mov     rax, [rcx]
0x18006ef18  mov     rax, [rax+10h]
0x18006ef1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef21  nop
0x18006ef22  mov     rcx, [rbp+pv]; pv
0x18006ef26  mov     [rbp+pv], r15
0x18006ef2a  test    rcx, rcx
0x18006ef2d  jz      short loc_18006EF3C
0x18006ef2f  call    cs:__imp_CoTaskMemFree
0x18006ef36  nop     dword ptr [rax+rax+00h]
0x18006ef3b  nop
0x18006ef3c  mov     rcx, [rbp+var_20]
0x18006ef40  test    rcx, rcx
0x18006ef43  jz      short loc_18006EF56
0x18006ef45  mov     [rbp+var_20], r15
0x18006ef49  mov     rax, [rcx]
0x18006ef4c  mov     rax, [rax+10h]
0x18006ef50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef55  nop
0x18006ef56  mov     rcx, [rbp+var_28]
0x18006ef5a  test    rcx, rcx
0x18006ef5d  jz      short loc_18006EF70
0x18006ef5f  mov     [rbp+var_28], r15
0x18006ef63  mov     rax, [rcx]
0x18006ef66  mov     rax, [rax+10h]
0x18006ef6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef6f  nop
0x18006ef70  jmp     loc_18006EDB7
0x18006ef75  mov     rcx, [rbp+28h]; this
0x18006ef79  mov     r9d, ebx; char *
0x18006ef7c  lea     r8, aOnecoreuapInte_36; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18006ef83  mov     edx, 0A9h; void *
0x18006ef88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ef8d  nop
0x18006ef8e  mov     rcx, [rbp+var_18]
0x18006ef92  test    rcx, rcx
0x18006ef95  jz      short loc_18006EFA8
0x18006ef97  mov     [rbp+var_18], r15
  ... truncated ...
```
