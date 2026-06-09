# GetHiddenPropertyStore(IShellItem *,IDLHID,_GUID const &,void * *)

- ea: `0x1800672f8`
- end: `0x1800679b2`
- name: `?GetHiddenPropertyStore@@YAJPEAUIShellItem@@W4IDLHID@@AEBU_GUID@@PEAPEAX@Z`
- size: `1722`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000eeb0`
- `0x180288d58`
- `0x1804760f0`

## callees

- `0x18000d6cc`
- `0x1800144c4`
- `0x1800432f0`
- `0x1800672f8`
- `0x180097ff0`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800673b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067473`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800676c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006775a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800677da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800678df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006792c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800673b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067473`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800676c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006775a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800677da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800678df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006792c`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800673fc`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006757a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800673fc`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18006757a`

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
0x1800672f8  mov     [rsp-28h+arg_8], rbx
0x1800672fd  push    rbp
0x1800672fe  push    rsi
0x1800672ff  push    rdi
0x180067300  push    r14
0x180067302  push    r15
0x180067304  mov     rbp, rsp
0x180067307  sub     rsp, 80h
0x18006730e  mov     rax, cs:__security_cookie
0x180067315  xor     rax, rsp
0x180067318  mov     [rbp+var_10], rax
0x18006731c  mov     r14, r9
0x18006731f  mov     rdi, rcx
0x180067322  xor     r15d, r15d
0x180067325  mov     [r9], r15
0x180067328  mov     [rbp+var_28], r15
0x18006732c  mov     rax, [rcx]
0x18006732f  mov     rbx, [rax]
0x180067332  lea     rcx, [rbp+var_28]
0x180067336  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006733b  lea     r8, [rbp+var_28]
0x18006733f  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x180067346  mov     rcx, rdi
0x180067349  mov     rax, rbx
0x18006734c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067351  mov     ebx, eax
0x180067353  test    eax, eax
0x180067355  js      loc_180067648
0x18006735b  mov     [rbp+var_20], r15
0x18006735f  mov     [rbp+pv], r15
0x180067363  mov     rdi, [rbp+var_28]
0x180067367  mov     rax, [rdi]
0x18006736a  mov     rbx, [rax+20h]
0x18006736e  lea     rax, [rbp+pv]
0x180067372  mov     [rbp+var_50], rax
0x180067376  mov     [rbp+var_48], r15
0x18006737a  mov     [rbp+var_40], 1
0x18006737e  lea     rcx, [rbp+var_20]
0x180067382  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067387  lea     r9, [rbp+var_48]
0x18006738b  lea     r8, [rbp+var_20]
0x18006738f  xor     edx, edx
0x180067391  mov     rcx, rdi
0x180067394  mov     rax, rbx
0x180067397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006739c  mov     ebx, eax
0x18006739e  cmp     [rbp+var_40], r15b
0x1800673a2  jz      short loc_1800673BD
0x1800673a4  mov     r8, [rbp+var_50]
0x1800673a8  mov     rcx, [r8]; pv
0x1800673ab  mov     rdx, [rbp+var_48]
0x1800673af  mov     [r8], rdx
0x1800673b2  test    rcx, rcx
0x1800673b5  jz      short loc_1800673BD
0x1800673b7  call    cs:__imp_CoTaskMemFree
0x1800673bd  test    ebx, ebx
0x1800673bf  js      loc_18006794B
0x1800673c5  mov     edx, 0BEEF0027h
0x1800673ca  mov     r8d, 1
0x1800673d0  mov     rcx, [rbp+pv]
0x1800673d4  call    ?ILFindHiddenIDOn@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@H@Z; ILFindHiddenIDOn(_ITEMIDLIST_RELATIVE const *,IDLHID,int)
0x1800673d9  mov     rsi, rax
0x1800673dc  test    rax, rax
0x1800673df  jnz     loc_180067555
0x1800673e5  mov     [rbp+ppv], r15
0x1800673e9  lea     rcx, [rbp+ppv]
0x1800673ed  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>)
0x1800673f2  mov     rdx, rax; ppv
0x1800673f5  lea     rcx, _GUID_8e6433f3_db66_457e_a54c_351e9a83f7c5; riid
0x1800673fc  call    cs:__imp_PSCreateMemoryPropertyStore
0x180067402  mov     ebx, eax
0x180067404  test    eax, eax
0x180067406  js      loc_180067680
0x18006740c  mov     rcx, [rbp+ppv]
0x180067410  mov     rax, [rcx]
0x180067413  lea     edx, [rsi+2]
0x180067416  mov     rax, [rax+18h]
0x18006741a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006741f  mov     ebx, eax
0x180067421  test    eax, eax
0x180067423  js      loc_18006779A
0x180067429  mov     rcx, [rbp+ppv]
0x18006742d  mov     rax, [rcx]
0x180067430  mov     r8, r14
0x180067433  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18006743a  mov     rax, [rax]
0x18006743d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067442  mov     ebx, eax
0x180067444  test    eax, eax
0x180067446  js      loc_1800674D3
0x18006744c  mov     rcx, [rbp+ppv]
0x180067450  test    rcx, rcx
0x180067453  jz      short loc_180067466
0x180067455  mov     [rbp+ppv], r15
0x180067459  mov     rax, [rcx]
0x18006745c  mov     rax, [rax+10h]
0x180067460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067465  nop
0x180067466  mov     rcx, [rbp+pv]; pv
0x18006746a  mov     [rbp+pv], r15
0x18006746e  test    rcx, rcx
0x180067471  jz      short loc_18006747A
0x180067473  call    cs:__imp_CoTaskMemFree
0x180067479  nop
0x18006747a  mov     rcx, [rbp+var_20]
0x18006747e  test    rcx, rcx
0x180067481  jz      short loc_180067494
0x180067483  mov     [rbp+var_20], r15
0x180067487  mov     rax, [rcx]
0x18006748a  mov     rax, [rax+10h]
0x18006748e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067493  nop
0x180067494  mov     rcx, [rbp+var_28]
0x180067498  test    rcx, rcx
0x18006749b  jz      short loc_1800674AE
0x18006749d  mov     [rbp+var_28], r15
0x1800674a1  mov     rax, [rcx]
0x1800674a4  mov     rax, [rax+10h]
0x1800674a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674ad  nop
0x1800674ae  xor     eax, eax
0x1800674b0  mov     rcx, [rbp+var_10]
0x1800674b4  xor     rcx, rsp; StackCookie
0x1800674b7  call    __security_check_cookie
0x1800674bc  mov     rbx, [rsp+80h+arg_8]
0x1800674c4  add     rsp, 80h
0x1800674cb  pop     r15
0x1800674cd  pop     r14
0x1800674cf  pop     rdi
0x1800674d0  pop     rsi
0x1800674d1  pop     rbp
0x1800674d2  retn
0x1800674d3  mov     rcx, [rbp+28h]; this
0x1800674d7  mov     r9d, ebx; char *
0x1800674da  lea     r8, aOnecoreuapInte_37; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800674e1  mov     edx, 95h; void *
0x1800674e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800674eb  nop
0x1800674ec  mov     rcx, [rbp+ppv]
0x1800674f0  test    rcx, rcx
0x1800674f3  jz      short loc_180067506
0x1800674f5  mov     [rbp+ppv], r15
0x1800674f9  mov     rax, [rcx]
0x1800674fc  mov     rax, [rax+10h]
0x180067500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067505  nop
0x180067506  mov     rcx, [rbp+pv]; pv
0x18006750a  mov     [rbp+pv], r15
0x18006750e  test    rcx, rcx
0x180067511  jz      short loc_18006751A
0x180067513  call    cs:__imp_CoTaskMemFree
0x180067519  nop
0x18006751a  mov     rcx, [rbp+var_20]
0x18006751e  test    rcx, rcx
0x180067521  jz      short loc_180067534
0x180067523  mov     [rbp+var_20], r15
0x180067527  mov     rax, [rcx]
0x18006752a  mov     rax, [rax+10h]
0x18006752e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067533  nop
0x180067534  mov     rcx, [rbp+var_28]
0x180067538  test    rcx, rcx
0x18006753b  jz      short loc_18006754E
0x18006753d  mov     [rbp+var_28], r15
0x180067541  mov     rax, [rcx]
0x180067544  mov     rax, [rax+10h]
0x180067548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006754d  nop
0x18006754e  mov     eax, ebx
0x180067550  jmp     loc_1800674B0
0x180067555  movzx   edi, word ptr [rax]
0x180067558  cmp     di, 8
0x18006755c  jb      loc_1800678B4
0x180067562  mov     [rbp+ppv], r15
0x180067566  lea     rcx, [rbp+ppv]
0x18006756a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006756f  lea     rdx, [rbp+ppv]; ppv
0x180067573  lea     rcx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917; riid
0x18006757a  call    cs:__imp_PSCreateMemoryPropertyStore
0x180067580  mov     ebx, eax
0x180067582  test    eax, eax
0x180067584  js      loc_180067965
0x18006758a  mov     rcx, [rbp+ppv]
0x18006758e  mov     rax, [rcx]
0x180067591  sub     di, 8
0x180067595  movzx   r8d, di
0x180067599  lea     rdx, [rsi+8]
0x18006759d  mov     rax, [rax+20h]
0x1800675a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675a6  mov     ebx, eax
0x1800675a8  test    eax, eax
0x1800675aa  js      loc_18006796C
0x1800675b0  mov     [rbp+var_18], r15
0x1800675b4  mov     rbx, [rbp+ppv]
0x1800675b8  mov     rax, [rbx]
0x1800675bb  mov     rdi, [rax]
0x1800675be  lea     rcx, [rbp+var_18]
0x1800675c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800675c7  lea     r8, [rbp+var_18]
0x1800675cb  lea     rdx, _GUID_8e6433f3_db66_457e_a54c_351e9a83f7c5
0x1800675d2  mov     rcx, rbx
0x1800675d5  mov     rax, rdi
0x1800675d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675dd  mov     ebx, eax
0x1800675df  test    eax, eax
0x1800675e1  js      loc_18006798A
0x1800675e7  mov     rcx, [rbp+var_18]
0x1800675eb  mov     rax, [rcx]
0x1800675ee  mov     edx, 2
0x1800675f3  mov     rax, [rax+18h]
0x1800675f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675fc  mov     ebx, eax
0x1800675fe  test    eax, eax
0x180067600  js      loc_18006781A
0x180067606  mov     rcx, [rbp+ppv]
0x18006760a  mov     rax, [rcx]
0x18006760d  mov     r8, r14
0x180067610  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180067617  mov     rax, [rax]
0x18006761a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006761f  mov     ebx, eax
0x180067621  test    eax, eax
0x180067623  js      loc_180067700
0x180067629  mov     rcx, [rbp+var_18]
0x18006762d  test    rcx, rcx
0x180067630  jz      short loc_180067643
0x180067632  mov     [rbp+var_18], r15
0x180067636  mov     rax, [rcx]
0x180067639  mov     rax, [rax+10h]
0x18006763d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067642  nop
0x180067643  jmp     loc_18006744C
0x180067648  mov     rcx, [rbp+28h]; this
0x18006764c  mov     r9d, ebx; char *
0x18006764f  lea     r8, aOnecoreuapInte_37; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180067656  mov     edx, 89h; void *
0x18006765b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067660  nop
0x180067661  mov     rcx, [rbp+var_28]
0x180067665  test    rcx, rcx
0x180067668  jz      short loc_18006767B
0x18006766a  mov     [rbp+var_28], r15
0x18006766e  mov     rax, [rcx]
0x180067671  mov     rax, [rax+10h]
0x180067675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006767a  nop
0x18006767b  jmp     loc_18006754E
0x180067680  mov     rcx, [rbp+28h]; this
0x180067684  mov     r9d, ebx; char *
0x180067687  lea     r8, aOnecoreuapInte_37; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18006768e  mov     edx, 93h; void *
0x180067693  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067698  nop
0x180067699  mov     rcx, [rbp+ppv]
0x18006769d  test    rcx, rcx
0x1800676a0  jz      short loc_1800676B3
0x1800676a2  mov     [rbp+ppv], r15
0x1800676a6  mov     rax, [rcx]
0x1800676a9  mov     rax, [rax+10h]
0x1800676ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676b2  nop
0x1800676b3  mov     rcx, [rbp+pv]; pv
0x1800676b7  mov     [rbp+pv], r15
0x1800676bb  test    rcx, rcx
0x1800676be  jz      short loc_1800676C7
0x1800676c0  call    cs:__imp_CoTaskMemFree
0x1800676c6  nop
0x1800676c7  mov     rcx, [rbp+var_20]
0x1800676cb  test    rcx, rcx
0x1800676ce  jz      short loc_1800676E1
0x1800676d0  mov     [rbp+var_20], r15
0x1800676d4  mov     rax, [rcx]
0x1800676d7  mov     rax, [rax+10h]
0x1800676db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676e0  nop
0x1800676e1  mov     rcx, [rbp+var_28]
0x1800676e5  test    rcx, rcx
0x1800676e8  jz      short loc_1800676FB
0x1800676ea  mov     [rbp+var_28], r15
0x1800676ee  mov     rax, [rcx]
0x1800676f1  mov     rax, [rax+10h]
0x1800676f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676fa  nop
0x1800676fb  jmp     loc_18006754E
0x180067700  mov     rcx, [rbp+28h]; this
0x180067704  mov     r9d, ebx; char *
0x180067707  lea     r8, aOnecoreuapInte_37; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18006770e  mov     edx, 0A9h; void *
0x180067713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067718  nop
0x180067719  mov     rcx, [rbp+var_18]
0x18006771d  test    rcx, rcx
0x180067720  jz      short loc_180067733
0x180067722  mov     [rbp+var_18], r15
0x180067726  mov     rax, [rcx]
0x180067729  mov     rax, [rax+10h]
0x18006772d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067732  nop
0x180067733  mov     rcx, [rbp+ppv]
0x180067737  test    rcx, rcx
  ... truncated ...
```
