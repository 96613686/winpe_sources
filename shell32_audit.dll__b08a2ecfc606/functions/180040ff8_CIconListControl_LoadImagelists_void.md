# CIconListControl::LoadImagelists(void)

- ea: `0x180040ff8`
- end: `0x1800417f6`
- name: `?LoadImagelists@CIconListControl@@AEAAJXZ`
- size: `2046`
- prototype: `__int64 __fastcall(CIconListControl *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180040c40`
- `0x1803eb260`

## callees

- `0x18000d220`
- `0x18000d240`
- `0x18000f6cc`
- `0x180038608`
- `0x180040ff8`
- `0x180041ca8`
- `0x180041d1c`
- `0x180042f30`
- `0x1800436e8`
- `0x180043ac0`
- `0x1800667f8`
- `0x1800b04d0`
- `0x1800b0f28`
- `0x1800b83a8`
- `0x180249490`
- `0x18024a518`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800412b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800412b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004130b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041366`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004147d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041518`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041565`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004162e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041785`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004130b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041366`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004147d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041518`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041565`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004162e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041785`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041377`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800413dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004144c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800414c2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800415aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041673`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800416d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041796`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800417d0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041377`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800413dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004144c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800414c2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800415aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041673`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800416d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180041796`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800417d0`
- `PROPSYS!PropVariantToUInt32` at `0x180041086`
- `PROPSYS!PropVariantToUInt32` at `0x180041086`
- `Windows.Storage!SHGetImageList` at `0x1800410fc`
- `Windows.Storage!SHGetImageList` at `0x1800410fc`

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
0x180040ff8  mov     [rsp-8+arg_8], rbx
0x180040ffd  mov     [rsp-8+arg_10], rsi
0x180041002  push    rbp
0x180041003  push    rdi
0x180041004  push    r12
0x180041006  push    r14
0x180041008  push    r15
0x18004100a  lea     rbp, [rsp-37h]
0x18004100f  sub     rsp, 0F0h
0x180041016  mov     rax, cs:__security_cookie
0x18004101d  xor     rax, rsp
0x180041020  mov     [rbp+57h+var_28], rax
0x180041024  mov     rsi, rcx
0x180041027  xor     r15d, r15d
0x18004102a  mov     [rbp+57h+var_C0], r15
0x18004102e  lea     rcx, [rbp+57h+var_C0]
0x180041032  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041037  lea     rdx, [rbp+57h+var_C0]; struct IPropertyStore **
0x18004103b  mov     rcx, rsi; this
0x18004103e  call    ?_GetPropertyStoreFromValue@CIconListControl@@AEAAJPEAPEAUIPropertyStore@@@Z; CIconListControl::_GetPropertyStoreFromValue(IPropertyStore * *)
0x180041043  test    eax, eax
0x180041045  js      loc_18004170A
0x18004104b  xorps   xmm0, xmm0
0x18004104e  xor     eax, eax
0x180041050  movups  xmmword ptr [rbp+57h+propvarIn], xmm0
0x180041054  mov     [rbp+57h+var_60], rax
0x180041058  mov     rcx, [rbp+57h+var_C0]
0x18004105c  mov     rax, [rcx]
0x18004105f  lea     r8, [rbp+57h+propvarIn]
0x180041063  lea     rdx, PKEY_PropList_StatusIconsDisplayFlag
0x18004106a  mov     rax, [rax+28h]
0x18004106e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041073  test    eax, eax
0x180041075  js      loc_180041718
0x18004107b  lea     rdx, [rsi+188h]; pulRet
0x180041082  lea     rcx, [rbp+57h+propvarIn]; propvarIn
0x180041086  call    cs:__imp_PropVariantToUInt32
0x18004108d  nop     dword ptr [rax+rax+00h]
0x180041092  mov     ebx, eax
0x180041094  test    eax, eax
0x180041096  js      loc_180041720
0x18004109c  mov     [rbp+57h+var_B8], r15
0x1800410a0  mov     [rbp+57h+var_98], r15d
0x1800410a4  lea     rcx, [rbp+57h+var_B8]
0x1800410a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800410ad  lea     r9, [rbp+57h+var_98]; unsigned int *
0x1800410b1  lea     r8, [rbp+57h+var_B8]; struct IPropertyDescriptionList **
0x1800410b5  mov     rdx, [rbp+57h+var_C0]; struct IPropertyStore *
0x1800410b9  call    ?_GetPropertyDescriptionListFromStore@CIconListControl@@AEAAJPEAUIPropertyStore@@PEAPEAUIPropertyDescriptionList@@PEAI@Z; CIconListControl::_GetPropertyDescriptionListFromStore(IPropertyStore *,IPropertyDescriptionList * *,uint *)
0x1800410be  mov     ebx, eax
0x1800410c0  test    eax, eax
0x1800410c2  js      loc_1800413A6
0x1800410c8  mov     edx, [rbp+57h+var_98]; unsigned int
0x1800410cb  mov     rcx, rsi; this
0x1800410ce  call    ?_InitializeLists@CIconListControl@@AEAAJI@Z; CIconListControl::_InitializeLists(uint)
0x1800410d3  mov     ebx, eax
0x1800410d5  test    eax, eax
0x1800410d7  js      loc_18004169F
0x1800410dd  mov     [rbp+57h+ppvObj], r15
0x1800410e1  lea     rcx, [rbp+57h+ppvObj]
0x1800410e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800410ea  lea     r8, [rbp+57h+ppvObj]; ppvObj
0x1800410ee  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x1800410f5  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800410f9  mov     ecx, r12d; iImageList
0x1800410fc  call    cs:__imp_SHGetImageList
0x180041103  nop     dword ptr [rax+rax+00h]
0x180041108  mov     ebx, eax
0x18004110a  test    eax, eax
0x18004110c  js      loc_18004173D
0x180041112  mov     rcx, [rbp+57h+ppvObj]
0x180041116  mov     rax, [rcx]
0x180041119  mov     r8d, [rsi+180h]
0x180041120  mov     edx, [rsi+17Ch]
0x180041126  mov     rax, [rax+100h]
0x18004112d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041132  mov     ebx, eax
0x180041134  test    eax, eax
0x180041136  js      loc_180041744
0x18004113c  mov     [rsp+110h+var_E0], r15
0x180041141  mov     [rsp+110h+var_D8], r15
0x180041146  mov     [rbp+57h+var_D0], r15
0x18004114a  mov     r14d, r15d
0x18004114d  cmp     r14d, [rbp+57h+var_98]
0x180041151  jnb     loc_180041511
0x180041157  mov     [rbp+57h+var_A8], r15
0x18004115b  mov     rdi, [rbp+57h+var_B8]
0x18004115f  mov     rax, [rdi]
0x180041162  mov     rbx, [rax+20h]
0x180041166  lea     rcx, [rbp+57h+var_A8]
0x18004116a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004116f  lea     r9, [rbp+57h+var_A8]
0x180041173  lea     r8, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814
0x18004117a  mov     edx, r14d
0x18004117d  mov     rcx, rdi
0x180041180  mov     rax, rbx
0x180041183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041188  mov     ebx, eax
0x18004118a  test    eax, eax
0x18004118c  js      loc_1800415F1
0x180041192  xorps   xmm0, xmm0
0x180041195  xor     eax, eax
0x180041197  movups  [rbp+57h+Buf1], xmm0
0x18004119b  mov     [rbp+57h+var_48], eax
0x18004119e  mov     rcx, [rbp+57h+var_A8]
0x1800411a2  mov     rax, [rcx]
0x1800411a5  lea     rdx, [rbp+57h+Buf1]
0x1800411a9  mov     rax, [rax+18h]
0x1800411ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411b2  xorps   xmm0, xmm0
0x1800411b5  xor     eax, eax
0x1800411b7  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800411bb  mov     [rbp+57h+var_78], rax
0x1800411bf  mov     rcx, [rbp+57h+var_C0]
0x1800411c3  mov     rax, [rcx]
0x1800411c6  lea     r8, [rbp+57h+pvar]
0x1800411ca  lea     rdx, [rbp+57h+Buf1]
0x1800411ce  mov     rax, [rax+28h]
0x1800411d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411d7  mov     ebx, eax
0x1800411d9  test    eax, eax
0x1800411db  js      loc_18004142F
0x1800411e1  cmp     word ptr [rbp+57h+pvar], r15w
0x1800411e6  jz      loc_1800414EE
0x1800411ec  mov     [rbp+57h+pv], r15
0x1800411f0  xor     ecx, ecx; pv
0x1800411f2  call    cs:__imp_CoTaskMemFree
0x1800411f9  nop     dword ptr [rax+rax+00h]
0x1800411fe  mov     rdi, [rbp+57h+var_A8]
0x180041202  mov     [rbp+57h+pv], r15
0x180041206  lea     rcx, [rbp+57h+var_90]; void *
0x18004120a  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x18004120f  nop
0x180041210  mov     rax, [rdi]
0x180041213  lea     r8, [rbp+57h+var_90]
0x180041217  lea     rdx, _GUID_57d2eded_5062_400e_b107_5dae79fe57a6
0x18004121e  mov     rcx, rdi
0x180041221  mov     rax, [rax]
0x180041224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041229  mov     ebx, eax
0x18004122b  test    eax, eax
0x18004122d  js      loc_18004131F
0x180041233  mov     rcx, [rbp+57h+var_90]
0x180041237  mov     rax, [rcx]
0x18004123a  lea     r8, [rbp+57h+pv]
0x18004123e  lea     rdx, [rbp+57h+pvar]
0x180041242  mov     rax, [rax+0C0h]
0x180041249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004124e  test    eax, eax
0x180041250  js      loc_18004131F
0x180041256  mov     [rbp+57h+var_C8], r15
0x18004125a  mov     rax, [rdi]
0x18004125d  lea     r9, [rbp+57h+var_C8]
0x180041261  xor     r8d, r8d
0x180041264  lea     rdx, [rbp+57h+pvar]
0x180041268  mov     rcx, rdi
0x18004126b  mov     rax, [rax+0B0h]
0x180041272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041277  mov     ebx, eax
0x180041279  test    eax, eax
0x18004127b  jns     loc_1800415D8
0x180041281  mov     rcx, [rbp+57h+pv]; pv
0x180041285  call    cs:__imp_CoTaskMemFree
0x18004128c  nop     dword ptr [rax+rax+00h]
0x180041291  mov     [rbp+57h+pv], r15
0x180041295  jmp     loc_18004131F
0x18004129a  mov     r9d, 0Ah; cchBufferMax
0x1800412a0  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800412a4  mov     edx, 1076h; uID
0x1800412a9  mov     rcx, cs:g_hinst; hInstance
0x1800412b0  call    cs:__imp_LoadStringW
0x1800412b7  nop     dword ptr [rax+rax+00h]
0x1800412bc  lea     rax, [rbp+57h+Buffer]
0x1800412c0  mov     r8, r12
0x1800412c3  inc     r8
0x1800412c6  cmp     [rax+r8*2], r15w
0x1800412cb  jnz     short loc_1800412C3
0x1800412cd  lea     rdx, [rbp+57h+Buffer]
0x1800412d1  lea     rcx, [rsp+110h+var_E0]
0x1800412d6  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800412db  mov     ebx, eax
0x1800412dd  test    eax, eax
0x1800412df  js      short loc_180041307
0x1800412e1  mov     rdx, [rbp+57h+var_C8]
0x1800412e5  test    rdx, rdx
0x1800412e8  jz      loc_180041702
0x1800412ee  mov     r8, r12
0x1800412f1  inc     r8
0x1800412f4  cmp     [rdx+r8*2], r15w
0x1800412f9  jnz     short loc_1800412F1
0x1800412fb  lea     rcx, [rsp+110h+var_E0]
0x180041300  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180041305  mov     ebx, eax
0x180041307  mov     rcx, [rbp+57h+var_C8]; pv
0x18004130b  call    cs:__imp_CoTaskMemFree
0x180041312  nop     dword ptr [rax+rax+00h]
0x180041317  test    ebx, ebx
0x180041319  js      loc_180041281
0x18004131f  lea     rcx, [rbp+57h+var_90]; void *
0x180041323  call    ??1?$CComPtr@UIUICommandWithBackgroundColor@@@ATL@@QEAA@XZ; ATL::CComPtr<IUICommandWithBackgroundColor>::~CComPtr<IUICommandWithBackgroundColor>(void)
0x180041328  test    ebx, ebx
0x18004132a  js      loc_180041768
0x180041330  mov     rcx, [rbp+57h+pv]
0x180041334  test    rcx, rcx
0x180041337  jz      short loc_180041366
0x180041339  mov     r8, rcx; unsigned __int16 *
0x18004133c  mov     rdx, [rbp+57h+ppvObj]; struct IImageList *
0x180041340  mov     rcx, rsi; this
0x180041343  call    ?_AddIconToList@CIconListControl@@AEAAJPEAUIImageList@@PEAG@Z; CIconListControl::_AddIconToList(IImageList *,ushort *)
0x180041348  mov     ebx, eax
0x18004134a  test    eax, eax
0x18004134c  js      loc_18004175E
0x180041352  mov     r8, [rbp+57h+var_C0]; struct IPropertyStore *
0x180041356  mov     rdx, [rbp+57h+var_A8]; struct IPropertyDescription *
0x18004135a  mov     rcx, rsi; this
0x18004135d  call    ?_AddToolTipToList@CIconListControl@@AEAAXPEAUIPropertyDescription@@PEAUIPropertyStore@@@Z; CIconListControl::_AddToolTipToList(IPropertyDescription *,IPropertyStore *)
0x180041362  mov     rcx, [rbp+57h+pv]; pv
0x180041366  call    cs:__imp_CoTaskMemFree
0x18004136d  nop     dword ptr [rax+rax+00h]
0x180041372  nop
0x180041373  lea     rcx, [rbp+57h+pvar]; pvar
0x180041377  call    cs:__imp_PropVariantClear
0x18004137e  nop     dword ptr [rax+rax+00h]
0x180041383  nop
0x180041384  mov     rcx, [rbp+57h+var_A8]
0x180041388  test    rcx, rcx
0x18004138b  jz      short loc_18004139E
0x18004138d  mov     [rbp+57h+var_A8], r15
0x180041391  mov     rax, [rcx]
0x180041394  mov     rax, [rax+10h]
0x180041398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004139d  nop
0x18004139e  inc     r14d
0x1800413a1  jmp     loc_18004114D
0x1800413a6  mov     rcx, [rbp+5Fh]; this
0x1800413aa  mov     r9d, ebx; char *
0x1800413ad  lea     r8, aShellShell32Do_0; "shell\\shell32\\docpropcontrols.cpp"
0x1800413b4  mov     edx, 0C47h; void *
0x1800413b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800413be  nop
0x1800413bf  mov     rcx, [rbp+57h+var_B8]
0x1800413c3  test    rcx, rcx
0x1800413c6  jz      short loc_1800413D9
0x1800413c8  mov     [rbp+57h+var_B8], r15
0x1800413cc  mov     rax, [rcx]
0x1800413cf  mov     rax, [rax+10h]
0x1800413d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413d8  nop
0x1800413d9  lea     rcx, [rbp+57h+propvarIn]; pvar
0x1800413dd  call    cs:__imp_PropVariantClear
0x1800413e4  nop     dword ptr [rax+rax+00h]
0x1800413e9  nop
0x1800413ea  mov     rcx, [rbp+57h+var_C0]
0x1800413ee  test    rcx, rcx
0x1800413f1  jz      short loc_180041404
0x1800413f3  mov     [rbp+57h+var_C0], r15
0x1800413f7  mov     rax, [rcx]
0x1800413fa  mov     rax, [rax+10h]
0x1800413fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041403  nop
0x180041404  mov     eax, ebx
0x180041406  mov     rcx, [rbp+57h+var_28]
0x18004140a  xor     rcx, rsp; StackCookie
0x18004140d  call    __security_check_cookie
0x180041412  lea     r11, [rsp+110h+var_20]
0x18004141a  mov     rbx, [r11+38h]
0x18004141e  mov     rsi, [r11+40h]
0x180041422  mov     rsp, r11
0x180041425  pop     r15
0x180041427  pop     r14
0x180041429  pop     r12
0x18004142b  pop     rdi
0x18004142c  pop     rbp
0x18004142d  retn
0x18004142f  mov     rcx, [rbp+5Fh]; this
0x180041433  mov     r9d, ebx; char *
0x180041436  lea     r8, aShellShell32Do_0; "shell\\shell32\\docpropcontrols.cpp"
0x18004143d  mov     edx, 0C5Ah; void *
0x180041442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041447  nop
0x180041448  lea     rcx, [rbp+57h+pvar]; pvar
0x18004144c  call    cs:__imp_PropVariantClear
0x180041453  nop     dword ptr [rax+rax+00h]
0x180041458  nop
0x180041459  mov     rcx, [rbp+57h+var_A8]
0x18004145d  test    rcx, rcx
0x180041460  jz      short loc_180041473
0x180041462  mov     [rbp+57h+var_A8], r15
0x180041466  mov     rax, [rcx]
0x180041469  mov     rax, [rax+10h]
0x18004146d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041472  nop
0x180041473  mov     rcx, [rsp+110h+var_E0]; pv
0x180041478  test    rcx, rcx
0x18004147b  jz      short loc_18004148A
0x18004147d  call    cs:__imp_CoTaskMemFree
0x180041484  nop     dword ptr [rax+rax+00h]
0x180041489  nop
0x18004148a  mov     rcx, [rbp+57h+ppvObj]
0x18004148e  test    rcx, rcx
  ... truncated ...
```
