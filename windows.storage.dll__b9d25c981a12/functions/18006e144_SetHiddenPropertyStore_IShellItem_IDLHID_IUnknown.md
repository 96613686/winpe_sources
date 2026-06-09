# SetHiddenPropertyStore(IShellItem *,IDLHID,IUnknown *)

- ea: `0x18006e144`
- end: `0x18006ea80`
- name: `?SetHiddenPropertyStore@@YAJPEAUIShellItem@@W4IDLHID@@PEAUIUnknown@@@Z`
- size: `2364`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007c810`
- `0x1802513f0`

## callees

- `0x180009fc0`
- `0x1800143b0`
- `0x1800304e0`
- `0x180038f50`
- `0x180049110`
- `0x18005d130`
- `0x18006cff0`
- `0x18006e144`
- `0x18006f56c`
- `0x1803b1f60`
- `0x1803b29ea`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006e3d2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006e3fc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006e630`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006ea4e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006e3d2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006e3fc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006e630`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18006ea4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e2f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e3b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e4b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e4cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e500`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e5b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e5d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e6e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e76f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e7a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e87b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e8af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e94f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e9d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e9f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ea0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e2f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e3b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e4b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e4cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e500`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e5b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e5d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e6e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e76f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e7a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e87b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e8af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e94f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e9d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e9f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ea0a`

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
0x18006e144  mov     [rsp-8+arg_8], rbx
0x18006e149  mov     [rsp-8+arg_18], rsi
0x18006e14e  push    rbp
0x18006e14f  push    rdi
0x18006e150  push    r13
0x18006e152  push    r14
0x18006e154  push    r15
0x18006e156  lea     rbp, [rsp-37h]
0x18006e15b  sub     rsp, 0A0h
0x18006e162  mov     rax, cs:__security_cookie
0x18006e169  xor     rax, rsp
0x18006e16c  mov     [rbp+57h+var_28], rax
0x18006e170  mov     rsi, r8
0x18006e173  mov     rdi, rcx
0x18006e176  xor     r15d, r15d
0x18006e179  mov     [rbp+57h+var_70], r15
0x18006e17d  mov     rax, [r8]
0x18006e180  mov     rbx, [rax]
0x18006e183  lea     rcx, [rbp+57h+var_70]
0x18006e187  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>)
0x18006e18c  mov     r8, rax
0x18006e18f  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18006e196  mov     rcx, rsi
0x18006e199  mov     rax, rbx
0x18006e19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1a1  mov     ebx, eax
0x18006e1a3  test    eax, eax
0x18006e1a5  js      loc_18006E684
0x18006e1ab  mov     rcx, [rbp+57h+var_70]
0x18006e1af  mov     rax, [rcx]
0x18006e1b2  mov     rax, [rax+20h]
0x18006e1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1bb  test    eax, eax
0x18006e1bd  jnz     loc_18006E9AF
0x18006e1c3  mov     [rbp+57h+var_68], r15
0x18006e1c7  mov     rax, [rdi]
0x18006e1ca  mov     rbx, [rax]
0x18006e1cd  lea     rcx, [rbp+57h+var_68]
0x18006e1d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e1d6  lea     r8, [rbp+57h+var_68]
0x18006e1da  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x18006e1e1  mov     rcx, rdi
0x18006e1e4  mov     rax, rbx
0x18006e1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1ec  mov     ebx, eax
0x18006e1ee  test    eax, eax
0x18006e1f0  js      loc_18006E803
0x18006e1f6  mov     [rbp+57h+var_50], r15
0x18006e1fa  mov     [rbp+57h+var_78], r15
0x18006e1fe  mov     rdi, [rbp+57h+var_68]
0x18006e202  mov     rax, [rdi]
0x18006e205  mov     rbx, [rax+20h]
0x18006e209  lea     rax, [rbp+57h+var_78]
0x18006e20d  mov     [rbp+57h+var_90], rax
0x18006e211  mov     [rbp+57h+var_88], r15
0x18006e215  mov     [rbp+57h+var_80], 1
0x18006e219  lea     rcx, [rbp+57h+var_50]
0x18006e21d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e222  lea     r9, [rbp+57h+var_88]
0x18006e226  lea     r8, [rbp+57h+var_50]
0x18006e22a  xor     edx, edx
0x18006e22c  mov     rcx, rdi
0x18006e22f  mov     rax, rbx
0x18006e232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e237  mov     ebx, eax
0x18006e239  cmp     [rbp+57h+var_80], r15b
0x18006e23d  jz      short loc_18006E25E
0x18006e23f  mov     r8, [rbp+57h+var_90]
0x18006e243  mov     rcx, [r8]; pv
0x18006e246  mov     rdx, [rbp+57h+var_88]
0x18006e24a  mov     [r8], rdx
0x18006e24d  test    rcx, rcx
0x18006e250  jz      short loc_18006E25E
0x18006e252  call    cs:__imp_CoTaskMemFree
0x18006e259  nop     dword ptr [rax+rax+00h]
0x18006e25e  test    ebx, ebx
0x18006e260  js      loc_18006E6BE
0x18006e266  mov     rcx, [rbp+57h+var_78]; struct _ITEMIDLIST_RELATIVE *
0x18006e26a  call    ?ILIsEmpty@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsEmpty(_ITEMIDLIST_RELATIVE const *)
0x18006e26f  test    eax, eax
0x18006e271  jnz     loc_18006EA01
0x18006e277  mov     [rbp+57h+var_58], r15
0x18006e27b  mov     rax, [rsi]
0x18006e27e  mov     rbx, [rax]
0x18006e281  lea     rcx, [rbp+57h+var_58]
0x18006e285  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006e28a  lea     r8, [rbp+57h+var_58]
0x18006e28e  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x18006e295  mov     rcx, rsi
0x18006e298  mov     rax, rbx
0x18006e29b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2a0  mov     ebx, eax
0x18006e2a2  test    eax, eax
0x18006e2a4  js      loc_18006E90F
0x18006e2aa  mov     [rbp+57h+var_38], r15d
0x18006e2ae  mov     [rbp+57h+Src], r15
0x18006e2b2  mov     rcx, [rbp+57h+var_58]
0x18006e2b6  mov     rax, [rcx]
0x18006e2b9  lea     rdx, [rbp+57h+Src]
0x18006e2bd  mov     [rbp+57h+var_90], rdx
0x18006e2c1  mov     [rbp+57h+var_88], r15
0x18006e2c5  mov     [rbp+57h+var_80], 1
0x18006e2c9  lea     r8, [rbp+57h+var_38]
0x18006e2cd  lea     rdx, [rbp+57h+var_88]
0x18006e2d1  mov     rax, [rax+28h]
0x18006e2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2da  mov     ebx, eax
0x18006e2dc  cmp     [rbp+57h+var_80], r15b
0x18006e2e0  jz      short loc_18006E301
0x18006e2e2  mov     r8, [rbp+57h+var_90]
0x18006e2e6  mov     rcx, [r8]; pv
0x18006e2e9  mov     rdx, [rbp+57h+var_88]
0x18006e2ed  mov     [r8], rdx
0x18006e2f0  test    rcx, rcx
0x18006e2f3  jz      short loc_18006E301
0x18006e2f5  call    cs:__imp_CoTaskMemFree
0x18006e2fc  nop     dword ptr [rax+rax+00h]
0x18006e301  test    ebx, ebx
0x18006e303  js      loc_18006E855
0x18006e309  mov     edx, 0BEEF0027h
0x18006e30e  mov     r8d, 1
0x18006e314  mov     rcx, [rbp+57h+var_78]
0x18006e318  call    ?ILFindHiddenIDOn@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@H@Z; ILFindHiddenIDOn(_ITEMIDLIST_RELATIVE const *,IDLHID,int)
0x18006e31d  test    rax, rax
0x18006e320  jnz     loc_18006EA1E
0x18006e326  mov     rcx, [rbp+57h+var_78]
0x18006e32a  call    ILExpungeRemovedHiddenIDs
0x18006e32f  mov     edi, [rbp+57h+var_38]
0x18006e332  cmp     edi, 0FFFFh
0x18006e338  ja      loc_18006E586
0x18006e33e  mov     r13d, 8
0x18006e344  lea     esi, [rdi+r13]
0x18006e348  cmp     si, r13w
0x18006e34c  jb      loc_18006E744
0x18006e352  mov     [rbp+57h+var_48], r15
0x18006e356  lea     rcx, [rbp+57h+var_48]; void *
0x18006e35a  mov     [rbp+57h+var_90], rcx
0x18006e35e  mov     r9b, 1
0x18006e361  mov     [rbp+57h+var_80], r9b
0x18006e365  movzx   r14d, si
0x18006e369  mov     r10, r15
0x18006e36c  mov     [rbp+57h+var_88], r15
0x18006e370  lea     eax, [r13-7]
0x18006e374  mul     r14
0x18006e377  test    rdx, rdx
0x18006e37a  jnz     loc_18006E664
0x18006e380  lea     r9, [rbp+57h+var_88]; void **
0x18006e384  mov     r8, rax; unsigned __int64
0x18006e387  lea     edx, [r13-7]; unsigned int
0x18006e38b  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18006e390  mov     ebx, eax
0x18006e392  mov     r9b, [rbp+57h+var_80]
0x18006e396  mov     r10, [rbp+57h+var_88]
0x18006e39a  mov     rcx, [rbp+57h+var_90]
0x18006e39e  test    r9b, r9b
0x18006e3a1  jz      short loc_18006E3BD
0x18006e3a3  mov     rax, [rcx]
0x18006e3a6  mov     [rcx], r10
0x18006e3a9  test    rax, rax
0x18006e3ac  jz      short loc_18006E3BD
0x18006e3ae  mov     rcx, rax; pv
0x18006e3b1  call    cs:__imp_CoTaskMemFree
0x18006e3b8  nop     dword ptr [rax+rax+00h]
0x18006e3bd  test    ebx, ebx
0x18006e3bf  js      loc_18006EA2A
0x18006e3c5  mov     rcx, [rbp+57h+var_48]; void *
0x18006e3c9  test    rcx, rcx
0x18006e3cc  jnz     loc_18006E647
0x18006e3d2  call    cs:__imp__o__errno
0x18006e3d9  nop     dword ptr [rax+rax+00h]
0x18006e3de  mov     dword ptr [rax], 16h
0x18006e3e4  call    _invalid_parameter_noinfo
0x18006e3e9  test    di, di
0x18006e3ec  jz      short loc_18006E413
0x18006e3ee  mov     rcx, [rbp+57h+var_48]
0x18006e3f2  add     rcx, 8; void *
0x18006e3f6  jnz     loc_18006E604
0x18006e3fc  call    cs:__imp__o__errno
0x18006e403  nop     dword ptr [rax+rax+00h]
0x18006e408  mov     dword ptr [rax], 16h
0x18006e40e  call    _invalid_parameter_noinfo
0x18006e413  mov     [rbp+57h+pv], r15
0x18006e417  lea     rax, [rbp+57h+pv]
0x18006e41b  mov     [rbp+57h+var_90], rax
0x18006e41f  mov     [rbp+57h+var_88], r15
0x18006e423  mov     [rbp+57h+var_80], 1
0x18006e427  lea     r8, [rbp+57h+var_88]; struct _ITEMIDLIST_RELATIVE **
0x18006e42b  mov     rdx, [rbp+57h+var_48]; struct _HIDDENITEMID *
0x18006e42f  mov     rcx, [rbp+57h+var_78]; Src
0x18006e433  call    ?ILCloneWithHiddenID@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEFBU_HIDDENITEMID@@PEAPEAU1@@Z; ILCloneWithHiddenID(_ITEMIDLIST_RELATIVE const *,_HIDDENITEMID const *,_ITEMIDLIST_RELATIVE * *)
0x18006e438  mov     ebx, eax
0x18006e43a  cmp     [rbp+57h+var_80], r15b
0x18006e43e  jz      short loc_18006E45F
0x18006e440  mov     rdx, [rbp+57h+var_90]
0x18006e444  mov     rcx, [rdx]; pv
0x18006e447  mov     rax, [rbp+57h+var_88]
0x18006e44b  mov     [rdx], rax
0x18006e44e  test    rcx, rcx
0x18006e451  jz      short loc_18006E45F
0x18006e453  call    cs:__imp_CoTaskMemFree
0x18006e45a  nop     dword ptr [rax+rax+00h]
0x18006e45f  test    ebx, ebx
0x18006e461  js      loc_18006EA65
0x18006e467  mov     rcx, [rbp+57h+var_68]
0x18006e46b  mov     rax, [rcx]
0x18006e46e  mov     r9, [rbp+57h+pv]
0x18006e472  mov     r8, [rbp+57h+var_50]
0x18006e476  xor     edx, edx
0x18006e478  mov     rax, [rax+18h]
0x18006e47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e481  mov     ebx, eax
0x18006e483  test    eax, eax
0x18006e485  js      loc_18006EA72
0x18006e48b  mov     rcx, [rbp+57h+pv]; pv
0x18006e48f  mov     [rbp+57h+pv], r15
0x18006e493  test    rcx, rcx
0x18006e496  jz      short loc_18006E4A5
0x18006e498  call    cs:__imp_CoTaskMemFree
0x18006e49f  nop     dword ptr [rax+rax+00h]
0x18006e4a4  nop
0x18006e4a5  mov     rcx, [rbp+57h+var_48]; pv
0x18006e4a9  mov     [rbp+57h+var_48], r15
0x18006e4ad  test    rcx, rcx
0x18006e4b0  jz      short loc_18006E4BF
0x18006e4b2  call    cs:__imp_CoTaskMemFree
0x18006e4b9  nop     dword ptr [rax+rax+00h]
0x18006e4be  nop
0x18006e4bf  mov     rcx, [rbp+57h+Src]; pv
0x18006e4c3  mov     [rbp+57h+Src], r15
0x18006e4c7  test    rcx, rcx
0x18006e4ca  jz      short loc_18006E4D9
0x18006e4cc  call    cs:__imp_CoTaskMemFree
0x18006e4d3  nop     dword ptr [rax+rax+00h]
0x18006e4d8  nop
0x18006e4d9  mov     rcx, [rbp+57h+var_58]
0x18006e4dd  test    rcx, rcx
0x18006e4e0  jz      short loc_18006E4F3
0x18006e4e2  mov     [rbp+57h+var_58], r15
0x18006e4e6  mov     rax, [rcx]
0x18006e4e9  mov     rax, [rax+10h]
0x18006e4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4f2  nop
0x18006e4f3  mov     rcx, [rbp+57h+var_78]; pv
0x18006e4f7  mov     [rbp+57h+var_78], r15
0x18006e4fb  test    rcx, rcx
0x18006e4fe  jz      short loc_18006E50D
0x18006e500  call    cs:__imp_CoTaskMemFree
0x18006e507  nop     dword ptr [rax+rax+00h]
0x18006e50c  nop
0x18006e50d  mov     rcx, [rbp+57h+var_50]
0x18006e511  test    rcx, rcx
0x18006e514  jz      short loc_18006E527
0x18006e516  mov     [rbp+57h+var_50], r15
0x18006e51a  mov     rax, [rcx]
0x18006e51d  mov     rax, [rax+10h]
0x18006e521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e526  nop
0x18006e527  mov     rcx, [rbp+57h+var_68]
0x18006e52b  test    rcx, rcx
0x18006e52e  jz      short loc_18006E541
0x18006e530  mov     [rbp+57h+var_68], r15
0x18006e534  mov     rax, [rcx]
0x18006e537  mov     rax, [rax+10h]
0x18006e53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e540  nop
0x18006e541  mov     rcx, [rbp+57h+var_70]
0x18006e545  test    rcx, rcx
0x18006e548  jz      short loc_18006E55B
0x18006e54a  mov     [rbp+57h+var_70], r15
0x18006e54e  mov     rax, [rcx]
0x18006e551  mov     rax, [rax+10h]
0x18006e555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e55a  nop
0x18006e55b  xor     eax, eax
0x18006e55d  mov     rcx, [rbp+57h+var_28]
0x18006e561  xor     rcx, rsp; StackCookie
0x18006e564  call    __security_check_cookie
0x18006e569  lea     r11, [rsp+0C0h+var_20]
0x18006e571  mov     rbx, [r11+38h]
0x18006e575  mov     rsi, [r11+48h]
0x18006e579  mov     rsp, r11
0x18006e57c  pop     r15
0x18006e57e  pop     r14
0x18006e580  pop     r13
0x18006e582  pop     rdi
0x18006e583  pop     rbp
0x18006e584  retn
0x18006e586  mov     rcx, [rbp+5Fh]; this
0x18006e58a  mov     ebx, 80070216h
0x18006e58f  mov     r9d, ebx; char *
0x18006e592  lea     r8, aOnecoreuapInte_36; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18006e599  mov     edx, 0D5h; void *
0x18006e59e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e5a3  nop
0x18006e5a4  mov     rcx, [rbp+57h+Src]; pv
0x18006e5a8  test    rcx, rcx
0x18006e5ab  mov     [rbp+57h+Src], r15
0x18006e5af  jz      short loc_18006E5BE
0x18006e5b1  call    cs:__imp_CoTaskMemFree
0x18006e5b8  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
