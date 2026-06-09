# CIconListControl::LoadImagelists(void)

- ea: `0x1800452dc`
- end: `0x180045a58`
- name: `?LoadImagelists@CIconListControl@@AEAAJXZ`
- size: `1916`
- prototype: `__int64 __fastcall(CIconListControl *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180044fb0`
- `0x1803c2230`

## callees

- `0x18000d4b0`
- `0x18000d4c0`
- `0x18000f05c`
- `0x180025cd8`
- `0x18003cd64`
- `0x1800452dc`
- `0x180045ed4`
- `0x180045fd4`
- `0x1800471b4`
- `0x180047948`
- `0x180047d00`
- `0x18009bed0`
- `0x18009c8b0`
- `0x1800b4154`
- `0x180233280`
- `0x1802342d8`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180045579`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180045579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800454ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800455ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045721`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800457b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800457f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800458b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800459f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800454ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800455ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045623`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045721`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800457b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800457f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800458b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800459f9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004562e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004568e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800456f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045760`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045836`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800458f3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045950`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045a04`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045a38`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004562e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004568e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800456f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045760`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045836`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800458f3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045950`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045a04`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045a38`
- `PROPSYS!PropVariantToUInt32` at `0x18004536a`
- `PROPSYS!PropVariantToUInt32` at `0x18004536a`
- `Windows.Storage!SHGetImageList` at `0x1800453da`
- `Windows.Storage!SHGetImageList` at `0x1800453da`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CIconListControl::LoadImagelists(CIconListControl *this)
{
  HRESULT v2; // eax
  int v3; // ebx
  CIconListControl *v4; // rcx
  int PropertyDescriptionListFromStore; // eax
  int v6; // eax
  HRESULT v7; // eax
  unsigned int i; // r14d
  struct IPropertyDescriptionList *v9; // rdi
  HRESULT (__stdcall *GetAt)(IPropertyDescriptionList *, UINT, const IID *const, void **); // rbx
  int v11; // eax
  int v12; // eax
  struct IPropertyDescription *v13; // rdi
  __int64 v14; // r8
  __int64 v15; // r8
  void *v16; // rcx
  int v17; // eax
  struct IPropertyDescription *v18; // rcx
  struct IPropertyDescriptionList *v19; // rcx
  struct IPropertyStore *v20; // rcx
  struct IPropertyDescription *v22; // rcx
  void *v23; // rcx
  struct IPropertyDescriptionList *v24; // rcx
  struct IPropertyStore *v25; // rcx
  LPVOID v26; // rax
  void *v27; // rcx
  void *v28; // rcx
  struct IPropertyDescriptionList *v29; // rcx
  struct IPropertyStore *v30; // rcx
  struct IPropertyDescription *v31; // rcx
  void *v32; // rcx
  struct IPropertyDescriptionList *v33; // rcx
  struct IPropertyStore *v34; // rcx
  struct IPropertyDescriptionList *v35; // rcx
  struct IPropertyStore *v36; // rcx
  __int64 v37; // rdx
  unsigned __int64 v38; // r9
  __int64 v39; // rdx
  int v40; // [rsp+20h] [rbp-99h]
  LPVOID v41[3]; // [rsp+30h] [rbp-89h] BYREF
  LPVOID v42; // [rsp+48h] [rbp-71h] BYREF
  struct IPropertyStore *v43; // [rsp+50h] [rbp-69h] BYREF
  struct IPropertyDescriptionList *v44; // [rsp+58h] [rbp-61h] BYREF
  void *ppvObj; // [rsp+60h] [rbp-59h] BYREF
  struct IPropertyDescription *v46; // [rsp+68h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-49h] BYREF
  unsigned int v48; // [rsp+78h] [rbp-41h] BYREF
  __int64 v49; // [rsp+80h] [rbp-39h] BYREF
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v51; // [rsp+98h] [rbp-21h]
  PROPVARIANT propvarIn[2]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-9h]
  __int128 Buf1; // [rsp+B8h] [rbp-1h] BYREF
  int v55; // [rsp+C8h] [rbp+Fh]
  WCHAR Buffer[12]; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v43 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  if ( (int)CIconListControl::_GetPropertyStoreFromValue(this, &v43) >= 0 )
  {
    *(_OWORD *)propvarIn = 0;
    v53 = 0;
    if ( ((int (__fastcall *)(struct IPropertyStore *, void *, PROPVARIANT *))v43->lpVtbl->GetValue)(
           v43,
           &PKEY_PropList_StatusIconsDisplayFlag,
           propvarIn) < 0 )
    {
      v3 = 0;
    }
    else
    {
      v2 = PropVariantToUInt32(propvarIn, (ULONG *)this + 98);
      v3 = v2;
      if ( v2 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC42,
          (unsigned int)"shell\\shell32\\docpropcontrols.cpp",
          (const char *)(unsigned int)v2,
          v40);
      }
      else
      {
        v44 = 0;
        v48 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
        PropertyDescriptionListFromStore = CIconListControl::_GetPropertyDescriptionListFromStore(v4, v43, &v44, &v48);
        v3 = PropertyDescriptionListFromStore;
        if ( PropertyDescriptionListFromStore < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC47,
            (unsigned int)"shell\\shell32\\docpropcontrols.cpp",
            (const char *)(unsigned int)PropertyDescriptionListFromStore,
            v40);
          v19 = v44;
          if ( v44 )
          {
            v44 = 0;
            ((void (__fastcall *)(struct IPropertyDescriptionList *))v19->lpVtbl->Release)(v19);
          }
          PropVariantClear(propvarIn);
          v20 = v43;
          if ( v43 )
          {
            v43 = 0;
            ((void (__fastcall *)(struct IPropertyStore *))v20->lpVtbl->Release)(v20);
          }
          return (unsigned int)v3;
        }
        v6 = CIconListControl::_InitializeLists(this, v48);
        v3 = v6;
        if ( v6 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC48,
            (unsigned int)"shell\\shell32\\docpropcontrols.cpp",
            (const char *)(unsigned int)v6,
            v40);
          v35 = v44;
          if ( v44 )
          {
            v44 = 0;
            ((void (__fastcall *)(struct IPropertyDescriptionList *))v35->lpVtbl->Release)(v35);
          }
          PropVariantClear(propvarIn);
          v36 = v43;
          if ( v43 )
          {
            v43 = 0;
            ((void (__fastcall *)(struct IPropertyStore *))v36->lpVtbl->Release)(v36);
          }
          return (unsigned int)v3;
        }
        ppvObj = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObj);
        v7 = SHGetImageList(-1, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppvObj);
        v3 = v7;
        if ( v7 < 0 )
        {
          v37 = 3148;
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppvObj + 256LL))(
                 ppvObj,
                 *((unsigned int *)this + 95),
                 *((unsigned int *)this + 96));
          v3 = v7;
          if ( v7 >= 0 )
          {
            memset(v41, 0, sizeof(v41));
            for ( i = 0; i < v48; ++i )
            {
              v46 = 0;
              v9 = v44;
              GetAt = v44->lpVtbl->GetAt;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
              v11 = ((__int64 (__fastcall *)(struct IPropertyDescriptionList *, _QWORD, GUID *, struct IPropertyDescription **))GetAt)(
                      v9,
                      i,
                      &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
                      &v46);
              v3 = v11;
              if ( v11 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xC55,
                  (unsigned int)"shell\\shell32\\docpropcontrols.cpp",
                  (const char *)(unsigned int)v11,
                  v40);
                v31 = v46;
                if ( v46 )
                {
                  v46 = 0;
                  ((void (__fastcall *)(struct IPropertyDescription *))v31->lpVtbl->Release)(v31);
                }
                if ( v41[0] )
                  CoTaskMemFree(v41[0]);
                v32 = ppvObj;
                if ( ppvObj )
                {
                  ppvObj = 0;
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
                }
                v33 = v44;
                if ( v44 )
                {
                  v44 = 0;
                  ((void (__fastcall *)(struct IPropertyDescriptionList *))v33->lpVtbl->Release)(v33);
                }
                PropVariantClear(propvarIn);
                v34 = v43;
                if ( v43 )
                {
                  v43 = 0;
                  ((void (__fastcall *)(struct IPropertyStore *))v34->lpVtbl->Release)(v34);
                }
                return (unsigned int)v3;
              }
              Buf1 = 0;
              v55 = 0;
              ((void (__fastcall *)(struct IPropertyDescription *, __int128 *))v46->lpVtbl->GetPropertyKey)(v46, &Buf1);
              *(_OWORD *)pvar = 0;
              v51 = 0;
              v12 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int128 *, PROPVARIANT *))v43->lpVtbl->GetValue)(
                      v43,
                      &Buf1,
                      pvar);
              v3 = v12;
              if ( v12 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xC5A,
                  (unsigned int)"shell\\shell32\\docpropcontrols.cpp",
                  (const char *)(unsigned int)v12,
                  v40);
                PropVariantClear(pvar);
                v22 = v46;
                if ( v46 )
                {
                  v46 = 0;
                  ((void (__fastcall *)(struct IPropertyDescription *))v22->lpVtbl->Release)(v22);
                }
                if ( v41[0] )
                  CoTaskMemFree(v41[0]);
                v23 = ppvObj;
                if ( ppvObj )
                {
                  ppvObj = 0;
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
                }
                v24 = v44;
                if ( v44 )
                {
                  v44 = 0;
                  ((void (__fastcall *)(struct IPropertyDescriptionList *))v24->lpVtbl->Release)(v24);
                }
                PropVariantClear(propvarIn);
                v25 = v43;
                if ( v43 )
                {
                  v43 = 0;
                  ((void (__fastcall *)(struct IPropertyStore *))v25->lpVtbl->Release)(v25);
                }
                return (unsigned int)v3;
              }
              if ( LOWORD(pvar[0]) || !memcmp_0(&Buf1, &GUID_0e6b2b12_2ee4_43eb_ba9d_7cedfe743e6f, 0x10u) )
              {
                pv = 0;
                CoTaskMemFree(0);
                v13 = v46;
                pv = 0;
                ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(&v49);
                v3 = ((__int64 (__fastcall *)(struct IPropertyDescription *, GUID *, __int64 *))v13->lpVtbl->QueryInterface)(
                       v13,
                       &GUID_57d2eded_5062_400e_b107_5dae79fe57a6,
                       &v49);
                if ( v3 >= 0
                  && (*(int (__fastcall **)(__int64, PROPVARIANT *, LPVOID *))(*(_QWORD *)v49 + 192LL))(v49, pvar, &pv) >= 0 )
                {
                  v42 = 0;
                  v3 = ((__int64 (__fastcall *)(struct IPropertyDescription *, PROPVARIANT *, _QWORD, LPVOID *))v13->lpVtbl->FormatForDisplay)(
                         v13,
                         pvar,
                         0,
                         &v42);
                  if ( v3 < 0 )
                    goto LABEL_16;
                  if ( ImageList_GetImageCount(*((HIMAGELIST *)this + 43)) <= 0 )
                    goto LABEL_19;
                  LoadStringW(g_hinst, 0x1076u, Buffer, 10);
                  v14 = -1;
                  do
                    ++v14;
                  while ( Buffer[v14] );
                  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                         v41,
                         Buffer);
                  if ( v3 >= 0 )
                  {
LABEL_19:
                    if ( v42 )
                    {
                      v15 = -1;
                      do
                        ++v15;
                      while ( *((_WORD *)v42 + v15) );
                    }
                    v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                           v41,
                           v42);
                  }
                  CoTaskMemFree(v42);
                  if ( v3 < 0 )
                  {
LABEL_16:
                    CoTaskMemFree(pv);
                    pv = 0;
                  }
                }
                ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(&v49);
                if ( v3 < 0 )
                {
                  v38 = (unsigned int)v3;
                  v39 = 3169;
                  goto LABEL_90;
                }
                v16 = pv;
                if ( pv )
                {
                  v17 = CIconListControl::_AddIconToList(this, (struct IImageList *)ppvObj, (unsigned __int16 *)pv);
                  v3 = v17;
                  if ( v17 < 0 )
                  {
                    v38 = (unsigned int)v17;
                    v39 = 3172;
LABEL_90:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v39,
                      (unsigned int)"shell\\shell32\\docpropcontrols.cpp",
                      (const char *)v38,
                      v40);
                    CoTaskMemFree(pv);
                    PropVariantClear(pvar);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v41);
                    goto LABEL_91;
                  }
                  CIconListControl::_AddToolTipToList(this, v46, v43);
                  v16 = pv;
                }
                CoTaskMemFree(v16);
              }
              PropVariantClear(pvar);
              v18 = v46;
              if ( v46 )
              {
                v46 = 0;
                ((void (__fastcall *)(struct IPropertyDescription *))v18->lpVtbl->Release)(v18);
              }
            }
            CoTaskMemFree(*((LPVOID *)this + 45));
            *((_QWORD *)this + 45) = 0;
            v26 = v41[0];
            if ( !v41[0] )
            {
              if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                          v41,
                          &pszStart,
                          -1) < 0 )
              {
                v27 = v41[0];
                goto LABEL_54;
              }
              v26 = v41[0];
            }
            v27 = 0;
            *((_QWORD *)this + 45) = v26;
LABEL_54:
            if ( v27 )
              CoTaskMemFree(v27);
            v28 = ppvObj;
            if ( ppvObj )
            {
              ppvObj = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
            }
            v29 = v44;
            if ( v44 )
            {
              v44 = 0;
              ((void (__fastcall *)(struct IPropertyDescriptionList *))v29->lpVtbl->Release)(v29);
            }
            PropVariantClear(propvarIn);
            v30 = v43;
            if ( v43 )
            {
              v43 = 0;
              ((void (__fastcall *)(struct IPropertyStore *))v30->lpVtbl->Release)(v30);
            }
            return 0;
          }
          v37 = 3150;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"shell\\shell32\\docpropcontrols.cpp",
          (const char *)(unsigned int)v7,
          v40);
LABEL_91:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvObj);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      }
    }
    PropVariantClear(propvarIn);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    return (unsigned int)v3;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  return 0;
}

```

## disassembly

```asm
0x1800452dc  mov     [rsp-8+arg_8], rbx
0x1800452e1  mov     [rsp-8+arg_10], rsi
0x1800452e6  push    rbp
0x1800452e7  push    rdi
0x1800452e8  push    r12
0x1800452ea  push    r14
0x1800452ec  push    r15
0x1800452ee  lea     rbp, [rsp-37h]
0x1800452f3  sub     rsp, 0F0h
0x1800452fa  mov     rax, cs:__security_cookie
0x180045301  xor     rax, rsp
0x180045304  mov     [rbp+57h+var_28], rax
0x180045308  mov     rsi, rcx
0x18004530b  xor     r15d, r15d
0x18004530e  mov     [rbp+57h+var_C0], r15
0x180045312  lea     rcx, [rbp+57h+var_C0]
0x180045316  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004531b  lea     rdx, [rbp+57h+var_C0]; struct IPropertyStore **
0x18004531f  mov     rcx, rsi; this
0x180045322  call    ?_GetPropertyStoreFromValue@CIconListControl@@AEAAJPEAPEAUIPropertyStore@@@Z; CIconListControl::_GetPropertyStoreFromValue(IPropertyStore * *)
0x180045327  test    eax, eax
0x180045329  js      loc_18004597E
0x18004532f  xorps   xmm0, xmm0
0x180045332  xor     eax, eax
0x180045334  movups  xmmword ptr [rbp+57h+propvarIn], xmm0
0x180045338  mov     [rbp+57h+var_60], rax
0x18004533c  mov     rcx, [rbp+57h+var_C0]
0x180045340  mov     rax, [rcx]
0x180045343  lea     r8, [rbp+57h+propvarIn]
0x180045347  lea     rdx, PKEY_PropList_StatusIconsDisplayFlag
0x18004534e  mov     rax, [rax+28h]
0x180045352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045357  test    eax, eax
0x180045359  js      loc_18004598C
0x18004535f  lea     rdx, [rsi+188h]; pulRet
0x180045366  lea     rcx, [rbp+57h+propvarIn]; propvarIn
0x18004536a  call    cs:__imp_PropVariantToUInt32
0x180045370  mov     ebx, eax
0x180045372  test    eax, eax
0x180045374  js      loc_180045994
0x18004537a  mov     [rbp+57h+var_B8], r15
0x18004537e  mov     [rbp+57h+var_98], r15d
0x180045382  lea     rcx, [rbp+57h+var_B8]
0x180045386  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004538b  lea     r9, [rbp+57h+var_98]; unsigned int *
0x18004538f  lea     r8, [rbp+57h+var_B8]; struct IPropertyDescriptionList **
0x180045393  mov     rdx, [rbp+57h+var_C0]; struct IPropertyStore *
0x180045397  call    ?_GetPropertyDescriptionListFromStore@CIconListControl@@AEAAJPEAUIPropertyStore@@PEAPEAUIPropertyDescriptionList@@PEAI@Z; CIconListControl::_GetPropertyDescriptionListFromStore(IPropertyStore *,IPropertyDescriptionList * *,uint *)
0x18004539c  mov     ebx, eax
0x18004539e  test    eax, eax
0x1800453a0  js      loc_180045657
0x1800453a6  mov     edx, [rbp+57h+var_98]; unsigned int
0x1800453a9  mov     rcx, rsi; this
0x1800453ac  call    ?_InitializeLists@CIconListControl@@AEAAJI@Z; CIconListControl::_InitializeLists(uint)
0x1800453b1  mov     ebx, eax
0x1800453b3  test    eax, eax
0x1800453b5  js      loc_180045919
0x1800453bb  mov     [rbp+57h+ppvObj], r15
0x1800453bf  lea     rcx, [rbp+57h+ppvObj]
0x1800453c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800453c8  lea     r8, [rbp+57h+ppvObj]; ppvObj
0x1800453cc  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x1800453d3  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800453d7  mov     ecx, r12d; iImageList
0x1800453da  call    cs:__imp_SHGetImageList
0x1800453e0  mov     ebx, eax
0x1800453e2  test    eax, eax
0x1800453e4  js      loc_1800459B1
0x1800453ea  mov     rcx, [rbp+57h+ppvObj]
0x1800453ee  mov     rax, [rcx]
0x1800453f1  mov     r8d, [rsi+180h]
0x1800453f8  mov     edx, [rsi+17Ch]
0x1800453fe  mov     rax, [rax+100h]
0x180045405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004540a  mov     ebx, eax
0x18004540c  test    eax, eax
0x18004540e  js      loc_1800459B8
0x180045414  mov     [rsp+110h+var_E0], r15
0x180045419  mov     [rsp+110h+var_D8], r15
0x18004541e  mov     [rbp+57h+var_D0], r15
0x180045422  mov     r14d, r15d
0x180045425  cmp     r14d, [rbp+57h+var_98]
0x180045429  jnb     loc_1800457A9
0x18004542f  mov     [rbp+57h+var_A8], r15
0x180045433  mov     rdi, [rbp+57h+var_B8]
0x180045437  mov     rax, [rdi]
0x18004543a  mov     rbx, [rax+20h]
0x18004543e  lea     rcx, [rbp+57h+var_A8]
0x180045442  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180045447  lea     r9, [rbp+57h+var_A8]
0x18004544b  lea     r8, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814
0x180045452  mov     edx, r14d
0x180045455  mov     rcx, rdi
0x180045458  mov     rax, rbx
0x18004545b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045460  mov     ebx, eax
0x180045462  test    eax, eax
0x180045464  js      loc_180045877
0x18004546a  xorps   xmm0, xmm0
0x18004546d  xor     eax, eax
0x18004546f  movups  [rbp+57h+Buf1], xmm0
0x180045473  mov     [rbp+57h+var_48], eax
0x180045476  mov     rcx, [rbp+57h+var_A8]
0x18004547a  mov     rax, [rcx]
0x18004547d  lea     rdx, [rbp+57h+Buf1]
0x180045481  mov     rax, [rax+18h]
0x180045485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004548a  xorps   xmm0, xmm0
0x18004548d  xor     eax, eax
0x18004548f  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180045493  mov     [rbp+57h+var_78], rax
0x180045497  mov     rcx, [rbp+57h+var_C0]
0x18004549b  mov     rax, [rcx]
0x18004549e  lea     r8, [rbp+57h+pvar]
0x1800454a2  lea     rdx, [rbp+57h+Buf1]
0x1800454a6  mov     rax, [rax+28h]
0x1800454aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454af  mov     ebx, eax
0x1800454b1  test    eax, eax
0x1800454b3  js      loc_1800456D9
0x1800454b9  cmp     word ptr [rbp+57h+pvar], r15w
0x1800454be  jz      loc_180045786
0x1800454c4  mov     [rbp+57h+pv], r15
0x1800454c8  xor     ecx, ecx; pv
0x1800454ca  call    cs:__imp_CoTaskMemFree
0x1800454d0  mov     rdi, [rbp+57h+var_A8]
0x1800454d4  mov     [rbp+57h+pv], r15
0x1800454d8  lea     rcx, [rbp+57h+var_90]; void *
0x1800454dc  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x1800454e1  nop
0x1800454e2  mov     rax, [rdi]
0x1800454e5  lea     r8, [rbp+57h+var_90]
0x1800454e9  lea     rdx, _GUID_57d2eded_5062_400e_b107_5dae79fe57a6
0x1800454f0  mov     rcx, rdi
0x1800454f3  mov     rax, [rax]
0x1800454f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454fb  mov     ebx, eax
0x1800454fd  test    eax, eax
0x1800454ff  js      loc_1800455DC
0x180045505  mov     rcx, [rbp+57h+var_90]
0x180045509  mov     rax, [rcx]
0x18004550c  lea     r8, [rbp+57h+pv]
0x180045510  lea     rdx, [rbp+57h+pvar]
0x180045514  mov     rax, [rax+0C0h]
0x18004551b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045520  test    eax, eax
0x180045522  js      loc_1800455DC
0x180045528  mov     [rbp+57h+var_C8], r15
0x18004552c  mov     rax, [rdi]
0x18004552f  lea     r9, [rbp+57h+var_C8]
0x180045533  xor     r8d, r8d
0x180045536  lea     rdx, [rbp+57h+pvar]
0x18004553a  mov     rcx, rdi
0x18004553d  mov     rax, [rax+0B0h]
0x180045544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045549  mov     ebx, eax
0x18004554b  test    eax, eax
0x18004554d  jns     loc_18004585E
0x180045553  mov     rcx, [rbp+57h+pv]; pv
0x180045557  call    cs:__imp_CoTaskMemFree
0x18004555d  mov     [rbp+57h+pv], r15
0x180045561  jmp     short loc_1800455DC
0x180045563  mov     r9d, 0Ah; cchBufferMax
0x180045569  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18004556d  mov     edx, 1076h; uID
0x180045572  mov     rcx, cs:g_hinst; hInstance
0x180045579  call    cs:__imp_LoadStringW
0x18004557f  lea     rax, [rbp+57h+Buffer]
0x180045583  mov     r8, r12
0x180045586  inc     r8
0x180045589  cmp     [rax+r8*2], r15w
0x18004558e  jnz     short loc_180045586
0x180045590  lea     rdx, [rbp+57h+Buffer]
0x180045594  lea     rcx, [rsp+110h+var_E0]
0x180045599  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18004559e  mov     ebx, eax
0x1800455a0  test    eax, eax
0x1800455a2  js      short loc_1800455CA
0x1800455a4  mov     rdx, [rbp+57h+var_C8]
0x1800455a8  test    rdx, rdx
0x1800455ab  jz      loc_180045976
0x1800455b1  mov     r8, r12
0x1800455b4  inc     r8
0x1800455b7  cmp     [rdx+r8*2], r15w
0x1800455bc  jnz     short loc_1800455B4
0x1800455be  lea     rcx, [rsp+110h+var_E0]
0x1800455c3  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800455c8  mov     ebx, eax
0x1800455ca  mov     rcx, [rbp+57h+var_C8]; pv
0x1800455ce  call    cs:__imp_CoTaskMemFree
0x1800455d4  test    ebx, ebx
0x1800455d6  js      loc_180045553
0x1800455dc  lea     rcx, [rbp+57h+var_90]; void *
0x1800455e0  call    ??1?$CComPtr@UIUICommandWithBackgroundColor@@@ATL@@QEAA@XZ; ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(void)
0x1800455e5  test    ebx, ebx
0x1800455e7  js      loc_1800459DC
0x1800455ed  mov     rcx, [rbp+57h+pv]
0x1800455f1  test    rcx, rcx
0x1800455f4  jz      short loc_180045623
0x1800455f6  mov     r8, rcx; unsigned __int16 *
0x1800455f9  mov     rdx, [rbp+57h+ppvObj]; struct IImageList *
0x1800455fd  mov     rcx, rsi; this
0x180045600  call    ?_AddIconToList@CIconListControl@@AEAAJPEAUIImageList@@PEAG@Z; CIconListControl::_AddIconToList(IImageList *,ushort *)
0x180045605  mov     ebx, eax
0x180045607  test    eax, eax
0x180045609  js      loc_1800459D2
0x18004560f  mov     r8, [rbp+57h+var_C0]; struct IPropertyStore *
0x180045613  mov     rdx, [rbp+57h+var_A8]; struct IPropertyDescription *
0x180045617  mov     rcx, rsi; this
0x18004561a  call    ?_AddToolTipToList@CIconListControl@@AEAAXPEAUIPropertyDescription@@PEAUIPropertyStore@@@Z; CIconListControl::_AddToolTipToList(IPropertyDescription *,IPropertyStore *)
0x18004561f  mov     rcx, [rbp+57h+pv]; pv
0x180045623  call    cs:__imp_CoTaskMemFree
0x180045629  nop
0x18004562a  lea     rcx, [rbp+57h+pvar]; pvar
0x18004562e  call    cs:__imp_PropVariantClear
0x180045634  nop
0x180045635  mov     rcx, [rbp+57h+var_A8]
0x180045639  test    rcx, rcx
0x18004563c  jz      short loc_18004564F
0x18004563e  mov     [rbp+57h+var_A8], r15
0x180045642  mov     rax, [rcx]
0x180045645  mov     rax, [rax+10h]
0x180045649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004564e  nop
0x18004564f  inc     r14d
0x180045652  jmp     loc_180045425
0x180045657  mov     rcx, [rbp+5Fh]; this
0x18004565b  mov     r9d, ebx; char *
0x18004565e  lea     r8, aShellShell32Do_0; "shell\\shell32\\docpropcontrols.cpp"
0x180045665  mov     edx, 0C47h; void *
0x18004566a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004566f  nop
0x180045670  mov     rcx, [rbp+57h+var_B8]
0x180045674  test    rcx, rcx
0x180045677  jz      short loc_18004568A
0x180045679  mov     [rbp+57h+var_B8], r15
0x18004567d  mov     rax, [rcx]
0x180045680  mov     rax, [rax+10h]
0x180045684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045689  nop
0x18004568a  lea     rcx, [rbp+57h+propvarIn]; pvar
0x18004568e  call    cs:__imp_PropVariantClear
0x180045694  nop
0x180045695  mov     rcx, [rbp+57h+var_C0]
0x180045699  test    rcx, rcx
0x18004569c  jz      short loc_1800456AF
0x18004569e  mov     [rbp+57h+var_C0], r15
0x1800456a2  mov     rax, [rcx]
0x1800456a5  mov     rax, [rax+10h]
0x1800456a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800456ae  nop
0x1800456af  mov     eax, ebx
0x1800456b1  mov     rcx, [rbp+57h+var_28]
0x1800456b5  xor     rcx, rsp; StackCookie
0x1800456b8  call    __security_check_cookie
0x1800456bd  lea     r11, [rsp+110h+var_20]
0x1800456c5  mov     rbx, [r11+38h]
0x1800456c9  mov     rsi, [r11+40h]
0x1800456cd  mov     rsp, r11
0x1800456d0  pop     r15
0x1800456d2  pop     r14
0x1800456d4  pop     r12
0x1800456d6  pop     rdi
0x1800456d7  pop     rbp
0x1800456d8  retn
0x1800456d9  mov     rcx, [rbp+5Fh]; this
0x1800456dd  mov     r9d, ebx; char *
0x1800456e0  lea     r8, aShellShell32Do_0; "shell\\shell32\\docpropcontrols.cpp"
0x1800456e7  mov     edx, 0C5Ah; void *
0x1800456ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800456f1  nop
0x1800456f2  lea     rcx, [rbp+57h+pvar]; pvar
0x1800456f6  call    cs:__imp_PropVariantClear
0x1800456fc  nop
0x1800456fd  mov     rcx, [rbp+57h+var_A8]
0x180045701  test    rcx, rcx
0x180045704  jz      short loc_180045717
0x180045706  mov     [rbp+57h+var_A8], r15
0x18004570a  mov     rax, [rcx]
0x18004570d  mov     rax, [rax+10h]
0x180045711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045716  nop
0x180045717  mov     rcx, [rsp+110h+var_E0]; pv
0x18004571c  test    rcx, rcx
0x18004571f  jz      short loc_180045728
0x180045721  call    cs:__imp_CoTaskMemFree
0x180045727  nop
0x180045728  mov     rcx, [rbp+57h+ppvObj]
0x18004572c  test    rcx, rcx
0x18004572f  jz      short loc_180045742
0x180045731  mov     [rbp+57h+ppvObj], r15
0x180045735  mov     rax, [rcx]
0x180045738  mov     rax, [rax+10h]
0x18004573c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045741  nop
0x180045742  mov     rcx, [rbp+57h+var_B8]
0x180045746  test    rcx, rcx
0x180045749  jz      short loc_18004575C
0x18004574b  mov     [rbp+57h+var_B8], r15
0x18004574f  mov     rax, [rcx]
  ... truncated ...
```
