# SetHiddenPropertyStore(IShellItem *,IDLHID,IUnknown *)

- ea: `0x180066980`
- end: `0x180067231`
- name: `?SetHiddenPropertyStore@@YAJPEAUIShellItem@@W4IDLHID@@PEAUIUnknown@@@Z`
- size: `2225`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000eeb0`
- `0x180288d58`

## callees

- `0x18000d6cc`
- `0x1800144c4`
- `0x1800432f0`
- `0x18004e520`
- `0x180065950`
- `0x180066980`
- `0x180067cb8`
- `0x180097ff0`
- `0x1800db130`
- `0x1803a4cb0`
- `0x1803a570a`
- `0x1803a57e0`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180066bfc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180066c20`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180066e23`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180067205`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180066bfc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180066c20`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180066e23`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180067205`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066a8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066cc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066cd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066db0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066dce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ed1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066f56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067056`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006711e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006719b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800671b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800671c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066a8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066cc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066cd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066db0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066dce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066ed1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066f56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066f84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067056`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006711e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006719b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800671b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800671c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall SetHiddenPropertyStore(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64))
{
  __int64 (__fastcall *v5)(_QWORD, GUID *, __int64); // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *, struct _ITEMIDLIST_RELATIVE **); // rbx
  struct _ITEMIDLIST_RELATIVE *v13; // rcx
  void *v14; // rcx
  __int64 (__fastcall *v15)(_QWORD, GUID *, _QWORD **); // rbx
  int v16; // eax
  __int64 v17; // rax
  void *v18; // rcx
  __int64 v19; // rax
  unsigned __int16 v20; // di
  unsigned __int16 v21; // si
  char v22; // r9
  __int64 v23; // r14
  struct _HIDDENITEMID *v24; // r10
  struct _HIDDENITEMID *v25; // rax
  struct _HIDDENITEMID *v26; // rcx
  char *v27; // rcx
  void *v28; // rcx
  int v29; // eax
  void *v30; // rcx
  struct _HIDDENITEMID *v31; // rcx
  void *v32; // rcx
  _QWORD *v33; // rcx
  struct _ITEMIDLIST_RELATIVE *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  void *v39; // rcx
  bool v40; // zf
  struct _ITEMIDLIST_RELATIVE *v41; // rcx
  LPVOID v42; // rsi
  unsigned __int64 v43; // rbx
  __int64 v44; // rcx
  struct _ITEMIDLIST_RELATIVE *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  void *v49; // rcx
  _QWORD *v50; // rcx
  struct _ITEMIDLIST_RELATIVE *v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  void *v57; // rcx
  _QWORD *v58; // rcx
  struct _ITEMIDLIST_RELATIVE *v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  _QWORD *v63; // rcx
  struct _ITEMIDLIST_RELATIVE *v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  void *v68; // rcx
  struct _HIDDENITEMID *v69; // rcx
  unsigned __int64 v70; // r9
  __int64 v71; // rdx
  int v72; // [rsp+20h] [rbp-49h]
  struct _ITEMIDLIST_RELATIVE *v73; // [rsp+38h] [rbp-31h] BYREF
  char v74; // [rsp+40h] [rbp-29h]
  struct _ITEMIDLIST_RELATIVE *v75; // [rsp+48h] [rbp-21h]
  __int64 v76; // [rsp+50h] [rbp-19h] BYREF
  __int64 v77; // [rsp+58h] [rbp-11h] BYREF
  LPVOID Src; // [rsp+60h] [rbp-9h]
  _QWORD *v79; // [rsp+68h] [rbp-1h] BYREF
  __int64 v80; // [rsp+70h] [rbp+7h] BYREF
  struct _HIDDENITEMID *v81; // [rsp+78h] [rbp+Fh] BYREF
  LPVOID pv; // [rsp+80h] [rbp+17h]
  unsigned int v83[4]; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v76 = 0;
  v5 = **a3;
  v6 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&v76);
  v7 = v5(a3, &GUID_00000109_0000_0000_c000_000000000046, v6);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)(unsigned int)v7,
      v72);
    v44 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    return v8;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v76 + 32LL))(v76) )
  {
    v77 = 0;
    v9 = **a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
    v10 = v9(a1, &GUID_b3a4b685_b685_4805_99d9_5dead2873236, &v77);
    v8 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
        (const char *)(unsigned int)v10,
        v72);
      v55 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      v56 = v76;
      if ( v76 )
      {
        v76 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      return v8;
    }
    v80 = 0;
    v75 = 0;
    v11 = v77;
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, struct _ITEMIDLIST_RELATIVE **))(*(_QWORD *)v77 + 32LL);
    v73 = 0;
    v74 = 1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
    v8 = v12(v11, 0, &v80, &v73);
    if ( v74 )
    {
      v13 = v75;
      v75 = v73;
      if ( v13 )
        CoTaskMemFree(v13);
    }
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
        (const char *)v8,
        v72);
      v45 = v75;
      v75 = 0;
      if ( v45 )
        CoTaskMemFree(v45);
      v46 = v80;
      if ( v80 )
      {
        v80 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      v47 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      }
      v48 = v76;
      if ( v76 )
      {
        v76 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      }
      return v8;
    }
    if ( (unsigned int)ILIsEmpty(v75) )
    {
      v75 = 0;
      if ( v14 )
        CoTaskMemFree(v14);
      v8 = 0;
      goto LABEL_58;
    }
    v79 = 0;
    v15 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD **))**a3;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
    v16 = v15(a3, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v79);
    v8 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
        (const char *)(unsigned int)v16,
        v72);
      v63 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v63 + 16LL))(v63);
      }
      v64 = v75;
      v75 = 0;
      if ( v64 )
        CoTaskMemFree(v64);
      v65 = v80;
      if ( v80 )
      {
        v80 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      }
      v66 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
      }
      v67 = v76;
      if ( v76 )
      {
        v76 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      }
      return v8;
    }
    v83[0] = 0;
    Src = 0;
    v17 = *v79;
    v73 = 0;
    v74 = 1;
    v8 = (*(__int64 (__fastcall **)(_QWORD *, struct _ITEMIDLIST_RELATIVE **, unsigned int *))(v17 + 40))(
           v79,
           &v73,
           v83);
    if ( v74 )
    {
      v18 = Src;
      Src = v73;
      if ( v18 )
        CoTaskMemFree(v18);
    }
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
        (const char *)v8,
        v72);
      v57 = Src;
      Src = 0;
      if ( v57 )
        CoTaskMemFree(v57);
      v58 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v58 + 16LL))(v58);
      }
      v59 = v75;
      v75 = 0;
      if ( v59 )
        CoTaskMemFree(v59);
      v60 = v80;
      if ( v80 )
      {
        v80 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      }
      v61 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      }
      v62 = v76;
      if ( v76 )
      {
        v76 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      }
      return v8;
    }
    v19 = ILFindHiddenIDOn(v75, 3203334183LL, 1);
    if ( v19 )
      *(_DWORD *)(v19 + 4) = -1091633152;
    ILExpungeRemovedHiddenIDs(v75);
    v20 = v83[0];
    if ( v83[0] > 0xFFFF )
    {
      v8 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
        (const char *)0x80070216LL,
        v72);
LABEL_54:
      v39 = Src;
      v40 = Src == 0;
      Src = 0;
      if ( !v40 )
        CoTaskMemFree(v39);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
      v41 = v75;
      v40 = v75 == 0;
      v75 = 0;
      if ( !v40 )
        CoTaskMemFree(v41);
LABEL_58:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
      return v8;
    }
    v21 = LOWORD(v83[0]) + 8;
    if ( LOWORD(v83[0]) >= 0xFFF8u )
    {
      v8 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
        (const char *)0x80070216LL,
        v72);
      v49 = Src;
      Src = 0;
      if ( v49 )
        CoTaskMemFree(v49);
      v50 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v50 + 16LL))(v50);
      }
      v51 = v75;
      v75 = 0;
      if ( v51 )
        CoTaskMemFree(v51);
      v52 = v80;
      if ( v80 )
      {
        v80 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      v53 = v77;
      if ( v77 )
      {
        v77 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      }
      v54 = v76;
      if ( v76 )
      {
        v76 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      return v8;
    }
    v81 = 0;
    v22 = 1;
    v74 = 1;
    v23 = v21;
    v24 = 0;
    v73 = 0;
    if ( is_mul_ok(v21, 1u) )
    {
      v8 = CTCoAllocPolicy::Alloc(&v81, 1u, v21, (void **)&v73);
      v22 = v74;
      v24 = v73;
    }
    else
    {
      v8 = -2147024362;
    }
    if ( v22 )
    {
      v25 = v81;
      v81 = v24;
      if ( v25 )
        CoTaskMemFree(v25);
    }
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
        (const char *)v8,
        v72);
LABEL_125:
      v69 = v81;
      v81 = 0;
      if ( v69 )
        CoTaskMemFree(v69);
      goto LABEL_54;
    }
    v26 = v81;
    if ( v81 )
    {
      if ( v21 >= 8uLL )
      {
        *(_WORD *)v81 = v21;
        *((_WORD *)v26 + 1) = 0;
        *((_DWORD *)v26 + 1) = -1091633113;
LABEL_27:
        if ( !v20 )
          goto LABEL_31;
        v27 = (char *)v81 + 8;
        if ( v81 == (struct _HIDDENITEMID *)-8LL )
          goto LABEL_29;
        v42 = Src;
        v43 = v23 - 8;
        if ( Src && v43 >= v20 )
        {
          memcpy_0(v27, Src, v20);
        }
        else
        {
          memset_0(v27, 0, v23 - 8);
          if ( !v42 )
          {
LABEL_29:
            *(_DWORD *)_o__errno(v27) = 22;
LABEL_30:
            invalid_parameter_noinfo();
            goto LABEL_31;
          }
          if ( v43 < v20 )
          {
            *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
            goto LABEL_30;
          }
        }
LABEL_31:
        pv = 0;
        v73 = 0;
        v74 = 1;
        v8 = ILCloneWithHiddenID(v75, v81, &v73);
        if ( v74 )
        {
          v28 = pv;
          pv = v73;
          if ( v28 )
            CoTaskMemFree(v28);
        }
        if ( (v8 & 0x80000000) != 0 )
        {
          v70 = v8;
          v71 = 228;
        }
        else
        {
          v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPVOID))(*(_QWORD *)v77 + 24LL))(v77, 0, v80, pv);
          v8 = v29;
          if ( v29 >= 0 )
          {
            v30 = pv;
            pv = 0;
            if ( v30 )
              CoTaskMemFree(v30);
            v31 = v81;
            v81 = 0;
            if ( v31 )
              CoTaskMemFree(v31);
            v32 = Src;
            Src = 0;
            if ( v32 )
              CoTaskMemFree(v32);
            v33 = v79;
            if ( v79 )
            {
              v79 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
            }
            v34 = v75;
            v75 = 0;
            if ( v34 )
              CoTaskMemFree(v34);
            v35 = v80;
            if ( v80 )
            {
              v80 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            }
            v36 = v77;
            if ( v77 )
            {
              v77 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            }
            goto LABEL_50;
          }
          v70 = (unsigned int)v29;
          v71 = 229;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v71,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
          (const char *)v70,
          v72);
        v68 = pv;
        pv = 0;
        if ( v68 )
          CoTaskMemFree(v68);
        goto LABEL_125;
      }
      memset_0(v81, 0, v21);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_27;
  }
LABEL_50:
  v37 = v76;
  if ( v76 )
  {
    v76 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  return 0;
}

```

## disassembly

```asm
0x180066980  mov     [rsp-8+arg_8], rbx
0x180066985  mov     [rsp-8+arg_18], rsi
0x18006698a  push    rbp
0x18006698b  push    rdi
0x18006698c  push    r13
0x18006698e  push    r14
0x180066990  push    r15
0x180066992  lea     rbp, [rsp-37h]
0x180066997  sub     rsp, 0A0h
0x18006699e  mov     rax, cs:__security_cookie
0x1800669a5  xor     rax, rsp
0x1800669a8  mov     [rbp+57h+var_28], rax
0x1800669ac  mov     rsi, r8
0x1800669af  mov     rdi, rcx
0x1800669b2  xor     r15d, r15d
0x1800669b5  mov     [rbp+57h+var_70], r15
0x1800669b9  mov     rax, [r8]
0x1800669bc  mov     rbx, [rax]
0x1800669bf  lea     rcx, [rbp+57h+var_70]
0x1800669c3  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>)
0x1800669c8  mov     r8, rax
0x1800669cb  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x1800669d2  mov     rcx, rsi
0x1800669d5  mov     rax, rbx
0x1800669d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669dd  mov     ebx, eax
0x1800669df  test    eax, eax
0x1800669e1  js      loc_180066E71
0x1800669e7  mov     rcx, [rbp+57h+var_70]
0x1800669eb  mov     rax, [rcx]
0x1800669ee  mov     rax, [rax+20h]
0x1800669f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669f7  test    eax, eax
0x1800669f9  jnz     loc_180067178
0x1800669ff  mov     [rbp+57h+var_68], r15
0x180066a03  mov     rax, [rdi]
0x180066a06  mov     rbx, [rax]
0x180066a09  lea     rcx, [rbp+57h+var_68]
0x180066a0d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180066a12  lea     r8, [rbp+57h+var_68]
0x180066a16  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x180066a1d  mov     rcx, rdi
0x180066a20  mov     rax, rbx
0x180066a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a28  mov     ebx, eax
0x180066a2a  test    eax, eax
0x180066a2c  js      loc_180066FDE
0x180066a32  mov     [rbp+57h+var_50], r15
0x180066a36  mov     [rbp+57h+var_78], r15
0x180066a3a  mov     rdi, [rbp+57h+var_68]
0x180066a3e  mov     rax, [rdi]
0x180066a41  mov     rbx, [rax+20h]
0x180066a45  lea     rax, [rbp+57h+var_78]
0x180066a49  mov     [rbp+57h+var_90], rax
0x180066a4d  mov     [rbp+57h+var_88], r15
0x180066a51  mov     [rbp+57h+var_80], 1
0x180066a55  lea     rcx, [rbp+57h+var_50]
0x180066a59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180066a5e  lea     r9, [rbp+57h+var_88]
0x180066a62  lea     r8, [rbp+57h+var_50]
0x180066a66  xor     edx, edx
0x180066a68  mov     rcx, rdi
0x180066a6b  mov     rax, rbx
0x180066a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a73  mov     ebx, eax
0x180066a75  cmp     [rbp+57h+var_80], r15b
0x180066a79  jz      short loc_180066A94
0x180066a7b  mov     r8, [rbp+57h+var_90]
0x180066a7f  mov     rcx, [r8]; pv
0x180066a82  mov     rdx, [rbp+57h+var_88]
0x180066a86  mov     [r8], rdx
0x180066a89  test    rcx, rcx
0x180066a8c  jz      short loc_180066A94
0x180066a8e  call    cs:__imp_CoTaskMemFree
0x180066a94  test    ebx, ebx
0x180066a96  js      loc_180066EAB
0x180066a9c  mov     rcx, [rbp+57h+var_78]; struct _ITEMIDLIST_RELATIVE *
0x180066aa0  call    ?ILIsEmpty@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsEmpty(_ITEMIDLIST_RELATIVE const *)
0x180066aa5  test    eax, eax
0x180066aa7  jnz     loc_1800671BE
0x180066aad  mov     [rbp+57h+var_58], r15
0x180066ab1  mov     rax, [rsi]
0x180066ab4  mov     rbx, [rax]
0x180066ab7  lea     rcx, [rbp+57h+var_58]
0x180066abb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180066ac0  lea     r8, [rbp+57h+var_58]
0x180066ac4  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x180066acb  mov     rcx, rsi
0x180066ace  mov     rax, rbx
0x180066ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ad6  mov     ebx, eax
0x180066ad8  test    eax, eax
0x180066ada  js      loc_1800670DE
0x180066ae0  mov     [rbp+57h+var_38], r15d
0x180066ae4  mov     [rbp+57h+Src], r15
0x180066ae8  mov     rcx, [rbp+57h+var_58]
0x180066aec  mov     rax, [rcx]
0x180066aef  lea     rdx, [rbp+57h+Src]
0x180066af3  mov     [rbp+57h+var_90], rdx
0x180066af7  mov     [rbp+57h+var_88], r15
0x180066afb  mov     [rbp+57h+var_80], 1
0x180066aff  lea     r8, [rbp+57h+var_38]
0x180066b03  lea     rdx, [rbp+57h+var_88]
0x180066b07  mov     rax, [rax+28h]
0x180066b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b10  mov     ebx, eax
0x180066b12  cmp     [rbp+57h+var_80], r15b
0x180066b16  jz      short loc_180066B31
0x180066b18  mov     r8, [rbp+57h+var_90]
0x180066b1c  mov     rcx, [r8]; pv
0x180066b1f  mov     rdx, [rbp+57h+var_88]
0x180066b23  mov     [r8], rdx
0x180066b26  test    rcx, rcx
0x180066b29  jz      short loc_180066B31
0x180066b2b  call    cs:__imp_CoTaskMemFree
0x180066b31  test    ebx, ebx
0x180066b33  js      loc_180067030
0x180066b39  mov     edx, 0BEEF0027h
0x180066b3e  mov     r8d, 1
0x180066b44  mov     rcx, [rbp+57h+var_78]
0x180066b48  call    ?ILFindHiddenIDOn@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@H@Z; ILFindHiddenIDOn(_ITEMIDLIST_RELATIVE const *,IDLHID,int)
0x180066b4d  test    rax, rax
0x180066b50  jnz     loc_1800671D5
0x180066b56  mov     rcx, [rbp+57h+var_78]
0x180066b5a  call    ILExpungeRemovedHiddenIDs
0x180066b5f  mov     edi, [rbp+57h+var_38]
0x180066b62  cmp     edi, 0FFFFh
0x180066b68  ja      loc_180066D85
0x180066b6e  mov     r13d, 8
0x180066b74  lea     esi, [rdi+r13]
0x180066b78  cmp     si, r13w
0x180066b7c  jb      loc_180066F2B
0x180066b82  mov     [rbp+57h+var_48], r15
0x180066b86  lea     rcx, [rbp+57h+var_48]; void *
0x180066b8a  mov     [rbp+57h+var_90], rcx
0x180066b8e  mov     r9b, 1
0x180066b91  mov     [rbp+57h+var_80], r9b
0x180066b95  movzx   r14d, si
0x180066b99  mov     r10, r15
0x180066b9c  mov     [rbp+57h+var_88], r15
0x180066ba0  lea     eax, [r13-7]
0x180066ba4  mul     r14
0x180066ba7  test    rdx, rdx
0x180066baa  jnz     loc_180066E51
0x180066bb0  lea     r9, [rbp+57h+var_88]; void **
0x180066bb4  mov     r8, rax; unsigned __int64
0x180066bb7  lea     edx, [r13-7]; unsigned int
0x180066bbb  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180066bc0  mov     ebx, eax
0x180066bc2  mov     r9b, [rbp+57h+var_80]
0x180066bc6  mov     r10, [rbp+57h+var_88]
0x180066bca  mov     rcx, [rbp+57h+var_90]
0x180066bce  test    r9b, r9b
0x180066bd1  jz      short loc_180066BE7
0x180066bd3  mov     rax, [rcx]
0x180066bd6  mov     [rcx], r10
0x180066bd9  test    rax, rax
0x180066bdc  jz      short loc_180066BE7
0x180066bde  mov     rcx, rax; pv
0x180066be1  call    cs:__imp_CoTaskMemFree
0x180066be7  test    ebx, ebx
0x180066be9  js      loc_1800671E1
0x180066bef  mov     rcx, [rbp+57h+var_48]; void *
0x180066bf3  test    rcx, rcx
0x180066bf6  jnz     loc_180066E34
0x180066bfc  call    cs:__imp__o__errno
0x180066c02  mov     dword ptr [rax], 16h
0x180066c08  call    _invalid_parameter_noinfo
0x180066c0d  test    di, di
0x180066c10  jz      short loc_180066C31
0x180066c12  mov     rcx, [rbp+57h+var_48]
0x180066c16  add     rcx, 8; void *
0x180066c1a  jnz     loc_180066DF7
0x180066c20  call    cs:__imp__o__errno
0x180066c26  mov     dword ptr [rax], 16h
0x180066c2c  call    _invalid_parameter_noinfo
0x180066c31  mov     [rbp+57h+pv], r15
0x180066c35  lea     rax, [rbp+57h+pv]
0x180066c39  mov     [rbp+57h+var_90], rax
0x180066c3d  mov     [rbp+57h+var_88], r15
0x180066c41  mov     [rbp+57h+var_80], 1
0x180066c45  lea     r8, [rbp+57h+var_88]; struct _ITEMIDLIST_RELATIVE **
0x180066c49  mov     rdx, [rbp+57h+var_48]; struct _HIDDENITEMID *
0x180066c4d  mov     rcx, [rbp+57h+var_78]; Src
0x180066c51  call    ?ILCloneWithHiddenID@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEFBU_HIDDENITEMID@@PEAPEAU1@@Z; ILCloneWithHiddenID(_ITEMIDLIST_RELATIVE const *,_HIDDENITEMID const *,_ITEMIDLIST_RELATIVE * *)
0x180066c56  mov     ebx, eax
0x180066c58  cmp     [rbp+57h+var_80], r15b
0x180066c5c  jz      short loc_180066C77
0x180066c5e  mov     rdx, [rbp+57h+var_90]
0x180066c62  mov     rcx, [rdx]; pv
0x180066c65  mov     rax, [rbp+57h+var_88]
0x180066c69  mov     [rdx], rax
0x180066c6c  test    rcx, rcx
0x180066c6f  jz      short loc_180066C77
0x180066c71  call    cs:__imp_CoTaskMemFree
0x180066c77  test    ebx, ebx
0x180066c79  js      loc_180067216
0x180066c7f  mov     rcx, [rbp+57h+var_68]
0x180066c83  mov     rax, [rcx]
0x180066c86  mov     r9, [rbp+57h+pv]
0x180066c8a  mov     r8, [rbp+57h+var_50]
0x180066c8e  xor     edx, edx
0x180066c90  mov     rax, [rax+18h]
0x180066c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c99  mov     ebx, eax
0x180066c9b  test    eax, eax
0x180066c9d  js      loc_180067223
0x180066ca3  mov     rcx, [rbp+57h+pv]; pv
0x180066ca7  mov     [rbp+57h+pv], r15
0x180066cab  test    rcx, rcx
0x180066cae  jz      short loc_180066CB7
0x180066cb0  call    cs:__imp_CoTaskMemFree
0x180066cb6  nop
0x180066cb7  mov     rcx, [rbp+57h+var_48]; pv
0x180066cbb  mov     [rbp+57h+var_48], r15
0x180066cbf  test    rcx, rcx
0x180066cc2  jz      short loc_180066CCB
0x180066cc4  call    cs:__imp_CoTaskMemFree
0x180066cca  nop
0x180066ccb  mov     rcx, [rbp+57h+Src]; pv
0x180066ccf  mov     [rbp+57h+Src], r15
0x180066cd3  test    rcx, rcx
0x180066cd6  jz      short loc_180066CDF
0x180066cd8  call    cs:__imp_CoTaskMemFree
0x180066cde  nop
0x180066cdf  mov     rcx, [rbp+57h+var_58]
0x180066ce3  test    rcx, rcx
0x180066ce6  jz      short loc_180066CF9
0x180066ce8  mov     [rbp+57h+var_58], r15
0x180066cec  mov     rax, [rcx]
0x180066cef  mov     rax, [rax+10h]
0x180066cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066cf8  nop
0x180066cf9  mov     rcx, [rbp+57h+var_78]; pv
0x180066cfd  mov     [rbp+57h+var_78], r15
0x180066d01  test    rcx, rcx
0x180066d04  jz      short loc_180066D0D
0x180066d06  call    cs:__imp_CoTaskMemFree
0x180066d0c  nop
0x180066d0d  mov     rcx, [rbp+57h+var_50]
0x180066d11  test    rcx, rcx
0x180066d14  jz      short loc_180066D27
0x180066d16  mov     [rbp+57h+var_50], r15
0x180066d1a  mov     rax, [rcx]
0x180066d1d  mov     rax, [rax+10h]
0x180066d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d26  nop
0x180066d27  mov     rcx, [rbp+57h+var_68]
0x180066d2b  test    rcx, rcx
0x180066d2e  jz      short loc_180066D41
0x180066d30  mov     [rbp+57h+var_68], r15
0x180066d34  mov     rax, [rcx]
0x180066d37  mov     rax, [rax+10h]
0x180066d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d40  nop
0x180066d41  mov     rcx, [rbp+57h+var_70]
0x180066d45  test    rcx, rcx
0x180066d48  jz      short loc_180066D5B
0x180066d4a  mov     [rbp+57h+var_70], r15
0x180066d4e  mov     rax, [rcx]
0x180066d51  mov     rax, [rax+10h]
0x180066d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d5a  nop
0x180066d5b  xor     eax, eax
0x180066d5d  mov     rcx, [rbp+57h+var_28]
0x180066d61  xor     rcx, rsp; StackCookie
0x180066d64  call    __security_check_cookie
0x180066d69  lea     r11, [rsp+0C0h+var_20]
0x180066d71  mov     rbx, [r11+38h]
0x180066d75  mov     rsi, [r11+48h]
0x180066d79  mov     rsp, r11
0x180066d7c  pop     r15
0x180066d7e  pop     r14
0x180066d80  pop     r13
0x180066d82  pop     rdi
0x180066d83  pop     rbp
0x180066d84  retn
0x180066d85  mov     rcx, [rbp+5Fh]; this
0x180066d89  mov     ebx, 80070216h
0x180066d8e  mov     r9d, ebx; char *
0x180066d91  lea     r8, aOnecoreuapInte_37; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180066d98  mov     edx, 0D5h; void *
0x180066d9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066da2  nop
0x180066da3  mov     rcx, [rbp+57h+Src]; pv
0x180066da7  test    rcx, rcx
0x180066daa  mov     [rbp+57h+Src], r15
0x180066dae  jz      short loc_180066DB7
0x180066db0  call    cs:__imp_CoTaskMemFree
0x180066db6  nop
0x180066db7  lea     rcx, [rbp+57h+var_58]
0x180066dbb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180066dc0  nop
0x180066dc1  mov     rcx, [rbp+57h+var_78]; pv
0x180066dc5  test    rcx, rcx
0x180066dc8  mov     [rbp+57h+var_78], r15
0x180066dcc  jz      short loc_180066DD5
0x180066dce  call    cs:__imp_CoTaskMemFree
0x180066dd4  nop
0x180066dd5  lea     rcx, [rbp+57h+var_50]
  ... truncated ...
```
