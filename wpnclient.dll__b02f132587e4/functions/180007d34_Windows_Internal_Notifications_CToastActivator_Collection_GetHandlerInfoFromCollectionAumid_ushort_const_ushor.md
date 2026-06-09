# Windows::Internal::Notifications::CToastActivator_Collection::GetHandlerInfoFromCollectionAumid(ushort const *,ushort * *,ushort * *)

- ea: `0x180007d34`
- end: `0x1800082b0`
- name: `?GetHandlerInfoFromCollectionAumid@CToastActivator_Collection@Notifications@Internal@Windows@@AEAAJPEBGPEAPEAG1@Z`
- size: `1404`
- prototype: `int(Windows::Internal::Notifications::CToastActivator_Collection *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007760`
- `0x180007b40`

## callees

- `0x180005670`
- `0x1800070e8`
- `0x18000710c`
- `0x1800074d0`
- `0x180007d34`
- `0x180014010`
- `0x18001bdec`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007f91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008101`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007f91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008101`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007d9e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007d9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_Collection::GetHandlerInfoFromCollectionAumid(
        Windows::Internal::Notifications::CToastActivator_Collection *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  __int64 v7; // rbx
  LPVOID *v8; // rax
  HRESULT Instance; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, const unsigned __int16 *, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, LPCWCH *); // rbx
  int v22; // eax
  unsigned __int16 *v23; // rcx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, const unsigned __int16 *, __int64 *); // rbx
  int v26; // eax
  __int64 v27; // rdx
  unsigned int i; // r14d
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, LPCWCH *); // rbx
  int v34; // eax
  __int64 v35; // rdx
  const WCHAR *v36; // rcx
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, unsigned __int16 **); // rbx
  __int64 v39; // rdx
  unsigned __int16 *v40; // rax
  int ppv; // [rsp+20h] [rbp-59h]
  int ppva; // [rsp+20h] [rbp-59h]
  __int64 v43; // [rsp+30h] [rbp-49h] BYREF
  __int64 v44; // [rsp+38h] [rbp-41h] BYREF
  __int64 v45; // [rsp+40h] [rbp-39h] BYREF
  LPCWCH lpString1; // [rsp+48h] [rbp-31h] BYREF
  __int64 v47; // [rsp+50h] [rbp-29h]
  __int64 v48; // [rsp+58h] [rbp-21h]
  unsigned __int16 *v49; // [rsp+60h] [rbp-19h] BYREF
  __int64 v50; // [rsp+68h] [rbp-11h]
  __int64 v51; // [rsp+70h] [rbp-9h]
  __int64 v52; // [rsp+78h] [rbp-1h] BYREF
  LPCWCH v53; // [rsp+80h] [rbp+7h] BYREF
  __int64 v54; // [rsp+88h] [rbp+Fh]
  __int64 v55; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 v57; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v58; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v59; // [rsp+F8h] [rbp+7Fh] BYREF

  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v43 = 0;
  v7 = *((_QWORD *)this + 9);
  if ( v7 )
  {
    v57 = *((_QWORD *)this + 9);
    Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::InternalAddRef(&v57);
    v57 = v43;
    v43 = v7;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  }
  else
  {
    v45 = 0;
    v8 = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWpnPlatform>>(&v45);
    Instance = CoCreateInstance(
                 &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
                 0,
                 0x15u,
                 &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                 v8);
    v10 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      v11 = v45;
      if ( v45 )
      {
        v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      return v10;
    }
    v52 = 0;
    v13 = v45;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 40LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
    v15 = v14(v13, &v52);
    v10 = v15;
    if ( v15 < 0 )
    {
      v16 = 183;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
        (const char *)(unsigned int)v15,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      goto LABEL_59;
    }
    v15 = Microsoft::WRL::ComPtr<IWpnRegistrationEndpoint>::As<IWpnRegistrationEndpoint2>(&v52, &v43);
    v10 = v15;
    if ( v15 < 0 )
    {
      v16 = 185;
      goto LABEL_12;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  }
  v58 = 0;
  v17 = v43;
  v18 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v43 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  v19 = v18(v17, a2, &v58);
  v10 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
      (const char *)(unsigned int)v19,
      ppv);
LABEL_17:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
    goto LABEL_59;
  }
  lpString1 = 0;
  v47 = 0;
  v48 = 0;
  v20 = v58;
  v21 = *(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v58 + 40LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
  v47 = -1;
  v48 = -1;
  v22 = v21(v20, &lpString1);
  v10 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
      (const char *)(unsigned int)v22,
      ppv);
LABEL_20:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    goto LABEL_17;
  }
  if ( !lpString1 || !*lpString1 || CompareStringOrdinal(lpString1, -1, a2, -1, 1) == 2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    return 2147942450LL;
  }
  v23 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  if ( !a4 )
  {
LABEL_51:
    v40 = (unsigned __int16 *)lpString1;
    lpString1 = 0;
    v48 = 0;
    v47 = 0;
    *a3 = v40;
    if ( a4 )
    {
      v49 = 0;
      v51 = 0;
      v50 = 0;
      *a4 = v23;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    return 0;
  }
  v59 = 0;
  v24 = v43;
  v25 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v43 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  v26 = v25(v24, a2, &v59);
  v10 = v26;
  if ( v26 < 0 )
  {
    v27 = 209;
    goto LABEL_27;
  }
  LODWORD(v57) = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 32LL))(v59, &v57);
  v10 = v26;
  if ( v26 < 0 )
  {
    v27 = 212;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
      (const char *)(unsigned int)v26,
      ppva);
LABEL_28:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
    goto LABEL_20;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned int)v57 )
      goto LABEL_48;
    v44 = 0;
    v29 = v59;
    v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v59 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    v31 = v30(v29, i, &v44);
    v10 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
        (const char *)(unsigned int)v31,
        ppva);
      goto LABEL_57;
    }
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v32 = v44;
    v33 = *(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v44 + 24LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v53);
    v54 = -1;
    v55 = -1;
    v34 = v33(v32, &v53);
    v10 = v34;
    if ( v34 < 0 )
    {
      v39 = 219;
LABEL_55:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v39,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_collection.cpp",
        (const char *)(unsigned int)v34,
        ppva);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v53);
LABEL_57:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
      goto LABEL_28;
    }
    LODWORD(v35) = v54;
    if ( v54 == -1 )
    {
      if ( v53 )
      {
        v35 = -1;
        do
          ++v35;
        while ( v53[v35] );
      }
      else
      {
        LODWORD(v35) = 0;
      }
    }
    v36 = &pwzBaseUrl;
    if ( v53 )
      v36 = v53;
    if ( CompareStringOrdinal(v36, v35, L"LaunchArgs", -1, 0) == 2 )
      break;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v53);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  }
  v37 = v44;
  v38 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v44 + 32LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
  v50 = -1;
  v51 = -1;
  v34 = v38(v37, &v49);
  v10 = v34;
  if ( v34 < 0 )
  {
    v39 = 222;
    goto LABEL_55;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v53);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
LABEL_48:
  if ( v49 && *v49 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    v23 = v49;
    goto LABEL_51;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v49);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  v10 = -2147024846;
LABEL_59:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
  return v10;
}

```

## disassembly

```asm
0x180007d34  mov     [rsp-8+arg_8], rbx
0x180007d39  push    rbp
0x180007d3a  push    rsi
0x180007d3b  push    rdi
0x180007d3c  push    r12
0x180007d3e  push    r13
0x180007d40  push    r14
0x180007d42  push    r15
0x180007d44  lea     rbp, [rsp-27h]
0x180007d49  sub     rsp, 0A0h
0x180007d50  mov     rsi, r9
0x180007d53  mov     r15, r8
0x180007d56  mov     r14, rdx
0x180007d59  xor     r12d, r12d
0x180007d5c  mov     [r8], r12
0x180007d5f  test    r9, r9
0x180007d62  jz      short loc_180007D67
0x180007d64  mov     [r9], r12
0x180007d67  mov     [rbp+57h+var_A0], r12
0x180007d6b  mov     rbx, [rcx+48h]
0x180007d6f  test    rbx, rbx
0x180007d72  jnz     loc_180007E8B
0x180007d78  mov     [rbp+57h+var_90], r12
0x180007d7c  lea     rcx, [rbp+57h+var_90]
0x180007d80  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWpnPlatform>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnPlatform>>)
0x180007d85  mov     qword ptr [rsp+0D0h+ppv], rax; int
0x180007d8a  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x180007d91  xor     edx, edx; pUnkOuter
0x180007d93  lea     r8d, [rbx+15h]; dwClsContext
0x180007d97  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x180007d9e  call    cs:__imp_CoCreateInstance
0x180007da4  mov     ebx, eax
0x180007da6  test    eax, eax
0x180007da8  jns     short loc_180007DFE
0x180007daa  mov     rcx, [rbp+5Fh]; this
0x180007dae  mov     r9d, eax; char *
0x180007db1  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007db8  mov     edx, 0B4h; void *
0x180007dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007dc2  nop
0x180007dc3  mov     rcx, [rbp+57h+var_90]
0x180007dc7  test    rcx, rcx
0x180007dca  jz      short loc_180007DDD
0x180007dcc  mov     [rbp+57h+var_90], r12
0x180007dd0  mov     rax, [rcx]
0x180007dd3  mov     rax, [rax+10h]
0x180007dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ddc  nop
0x180007ddd  mov     rcx, [rbp+57h+var_A0]
0x180007de1  test    rcx, rcx
0x180007de4  jz      short loc_180007DF7
0x180007de6  mov     [rbp+57h+var_A0], r12
0x180007dea  mov     rax, [rcx]
0x180007ded  mov     rax, [rax+10h]
0x180007df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007df6  nop
0x180007df7  mov     eax, ebx
0x180007df9  jmp     loc_180008295
0x180007dfe  mov     [rbp+57h+var_58], r12
0x180007e02  mov     rdi, [rbp+57h+var_90]
0x180007e06  mov     rax, [rdi]
0x180007e09  mov     rbx, [rax+28h]
0x180007e0d  lea     rcx, [rbp+57h+var_58]
0x180007e11  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007e16  lea     rdx, [rbp+57h+var_58]
0x180007e1a  mov     rcx, rdi
0x180007e1d  mov     rax, rbx
0x180007e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e25  mov     ebx, eax
0x180007e27  test    eax, eax
0x180007e29  jns     short loc_180007E32
0x180007e2b  mov     edx, 0B7h
0x180007e30  jmp     short loc_180007E4A
0x180007e32  lea     rdx, [rbp+57h+var_A0]
0x180007e36  lea     rcx, [rbp+57h+var_58]
0x180007e3a  call    ??$As@UIWpnRegistrationEndpoint2@@@?$ComPtr@UIWpnRegistrationEndpoint@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWpnRegistrationEndpoint2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IWpnRegistrationEndpoint>::As<IWpnRegistrationEndpoint2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnRegistrationEndpoint2>>)
0x180007e3f  mov     ebx, eax
0x180007e41  test    eax, eax
0x180007e43  jns     short loc_180007E76
0x180007e45  mov     edx, 0B9h; void *
0x180007e4a  mov     r9d, eax; char *
0x180007e4d  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007e54  mov     rcx, [rbp+5Fh]; this
0x180007e58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e5d  nop
0x180007e5e  lea     rcx, [rbp+57h+var_58]
0x180007e62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007e67  nop
0x180007e68  lea     rcx, [rbp+57h+var_90]
0x180007e6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007e71  jmp     loc_180008265
0x180007e76  lea     rcx, [rbp+57h+var_58]
0x180007e7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007e7f  nop
0x180007e80  lea     rcx, [rbp+57h+var_90]
0x180007e84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007e89  jmp     short loc_180007EAD
0x180007e8b  mov     [rbp+57h+arg_0], rbx
0x180007e8f  lea     rcx, [rbp+57h+arg_0]
0x180007e93  call    ?InternalAddRef@?$ComPtr@UIWpnPresentationEndpoint@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWpnPresentationEndpoint>::InternalAddRef(void)
0x180007e98  mov     rax, [rbp+57h+var_A0]
0x180007e9c  mov     [rbp+57h+arg_0], rax
0x180007ea0  mov     [rbp+57h+var_A0], rbx
0x180007ea4  lea     rcx, [rbp+57h+arg_0]
0x180007ea8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007ead  mov     [rbp+57h+arg_10], r12
0x180007eb1  mov     rdi, [rbp+57h+var_A0]
0x180007eb5  mov     rax, [rdi]
0x180007eb8  mov     rbx, [rax+38h]
0x180007ebc  lea     rcx, [rbp+57h+arg_10]
0x180007ec0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007ec5  lea     r8, [rbp+57h+arg_10]
0x180007ec9  mov     rdx, r14
0x180007ecc  mov     rcx, rdi
0x180007ecf  mov     rax, rbx
0x180007ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ed7  mov     ebx, eax
0x180007ed9  test    eax, eax
0x180007edb  jns     short loc_180007F04
0x180007edd  mov     rcx, [rbp+5Fh]; this
0x180007ee1  mov     r9d, eax; char *
0x180007ee4  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007eeb  mov     edx, 0C1h; void *
0x180007ef0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ef5  nop
0x180007ef6  lea     rcx, [rbp+57h+arg_10]
0x180007efa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007eff  jmp     loc_180008265
0x180007f04  mov     [rbp+57h+lpString1], r12
0x180007f08  mov     [rbp+57h+var_80], r12
0x180007f0c  mov     [rbp+57h+var_78], r12
0x180007f10  mov     rdi, [rbp+57h+arg_10]
0x180007f14  mov     rax, [rdi]
0x180007f17  mov     rbx, [rax+28h]
0x180007f1b  lea     rcx, [rbp+57h+lpString1]
0x180007f1f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180007f24  or      r13, 0FFFFFFFFFFFFFFFFh
0x180007f28  mov     [rbp+57h+var_80], r13
0x180007f2c  mov     [rbp+57h+var_78], r13
0x180007f30  lea     rdx, [rbp+57h+lpString1]
0x180007f34  mov     rcx, rdi
0x180007f37  mov     rax, rbx
0x180007f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f3f  mov     ebx, eax
0x180007f41  test    eax, eax
0x180007f43  jns     short loc_180007F69
0x180007f45  mov     rcx, [rbp+5Fh]; this
0x180007f49  mov     r9d, eax; char *
0x180007f4c  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007f53  mov     edx, 0C4h; void *
0x180007f58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f5d  nop
0x180007f5e  lea     rcx, [rbp+57h+lpString1]
0x180007f62  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180007f67  jmp     short loc_180007EF6
0x180007f69  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180007f6d  test    rcx, rcx
0x180007f70  jz      loc_180008273
0x180007f76  cmp     [rcx], r12w
0x180007f7a  jz      loc_180008273
0x180007f80  mov     [rsp+0D0h+ppv], 1; int
0x180007f88  mov     r9d, r13d; cchCount2
0x180007f8b  mov     r8, r14; lpString2
0x180007f8e  mov     edx, r13d; cchCount1
0x180007f91  call    cs:__imp_CompareStringOrdinal
0x180007f97  cmp     eax, 2
0x180007f9a  jz      loc_180008273
0x180007fa0  mov     rcx, r12
0x180007fa3  mov     [rbp+57h+var_70], rcx
0x180007fa7  mov     [rbp+57h+var_68], r12
0x180007fab  mov     [rbp+57h+var_60], r12
0x180007faf  test    rsi, rsi
0x180007fb2  jz      loc_180008199
0x180007fb8  mov     [rbp+57h+arg_18], r12
0x180007fbc  mov     rdi, [rbp+57h+var_A0]
0x180007fc0  mov     rax, [rdi]
0x180007fc3  mov     rbx, [rax+40h]
0x180007fc7  lea     rcx, [rbp+57h+arg_18]
0x180007fcb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007fd0  lea     r8, [rbp+57h+arg_18]
0x180007fd4  mov     rdx, r14
0x180007fd7  mov     rcx, rdi
0x180007fda  mov     rax, rbx
0x180007fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fe2  mov     ebx, eax
0x180007fe4  test    eax, eax
0x180007fe6  jns     short loc_180008019
0x180007fe8  mov     edx, 0D1h; void *
0x180007fed  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007ff4  mov     r9d, eax; char *
0x180007ff7  mov     rcx, [rbp+5Fh]; this
0x180007ffb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008000  nop
0x180008001  lea     rcx, [rbp+57h+arg_18]
0x180008005  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000800a  nop
0x18000800b  lea     rcx, [rbp+57h+var_70]
0x18000800f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180008014  jmp     loc_180007F5E
0x180008019  mov     dword ptr [rbp+57h+arg_0], r12d
0x18000801d  mov     rcx, [rbp+57h+arg_18]
0x180008021  mov     rax, [rcx]
0x180008024  lea     rdx, [rbp+57h+arg_0]
0x180008028  mov     rax, [rax+20h]
0x18000802c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008031  mov     ebx, eax
0x180008033  test    eax, eax
0x180008035  jns     short loc_18000803E
0x180008037  mov     edx, 0D4h
0x18000803c  jmp     short loc_180007FED
0x18000803e  mov     r14d, r12d
0x180008041  cmp     r14d, dword ptr [rbp+57h+arg_0]
0x180008045  jnb     loc_180008175
0x18000804b  mov     [rbp+57h+var_98], r12
0x18000804f  mov     rdi, [rbp+57h+arg_18]
0x180008053  mov     rax, [rdi]
0x180008056  mov     rbx, [rax+18h]
0x18000805a  lea     rcx, [rbp+57h+var_98]
0x18000805e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008063  lea     r8, [rbp+57h+var_98]
0x180008067  mov     edx, r14d
0x18000806a  mov     rcx, rdi
0x18000806d  mov     rax, rbx
0x180008070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008075  mov     ebx, eax
0x180008077  test    eax, eax
0x180008079  js      loc_180008212
0x18000807f  mov     [rbp+57h+var_50], r12
0x180008083  mov     [rbp+57h+var_48], r12
0x180008087  mov     [rbp+57h+var_40], r12
0x18000808b  mov     rdi, [rbp+57h+var_98]
0x18000808f  mov     rax, [rdi]
0x180008092  mov     rbx, [rax+18h]
0x180008096  lea     rcx, [rbp+57h+var_50]
0x18000809a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000809f  mov     [rbp+57h+var_48], r13
0x1800080a3  mov     [rbp+57h+var_40], r13
0x1800080a7  lea     rdx, [rbp+57h+var_50]
0x1800080ab  mov     rcx, rdi
0x1800080ae  mov     rax, rbx
0x1800080b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b6  mov     ebx, eax
0x1800080b8  test    eax, eax
0x1800080ba  js      loc_1800081EE
0x1800080c0  mov     rdx, [rbp+57h+var_48]
0x1800080c4  mov     rax, [rbp+57h+var_50]
0x1800080c8  cmp     rdx, r13
0x1800080cb  jnz     short loc_1800080E4
0x1800080cd  test    rax, rax
0x1800080d0  jz      short loc_1800080E1
0x1800080d2  mov     rdx, r13
0x1800080d5  inc     rdx
0x1800080d8  cmp     [rax+rdx*2], r12w
0x1800080dd  jnz     short loc_1800080D5
0x1800080df  jmp     short loc_1800080E4
0x1800080e1  mov     rdx, r12; cchCount1
0x1800080e4  lea     rcx, pwzBaseUrl
0x1800080eb  test    rax, rax
0x1800080ee  cmovnz  rcx, rax; lpString1
0x1800080f2  mov     [rsp+0D0h+ppv], r12d; bIgnoreCase
0x1800080f7  mov     r9d, r13d; cchCount2
0x1800080fa  lea     r8, String2; "LaunchArgs"
0x180008101  call    cs:__imp_CompareStringOrdinal
0x180008107  cmp     eax, 2
0x18000810a  jz      short loc_180008127
0x18000810c  lea     rcx, [rbp+57h+var_50]
0x180008110  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180008115  nop
0x180008116  lea     rcx, [rbp+57h+var_98]
0x18000811a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000811f  inc     r14d
0x180008122  jmp     loc_180008041
0x180008127  mov     rdi, [rbp+57h+var_98]
0x18000812b  mov     rax, [rdi]
0x18000812e  mov     rbx, [rax+20h]
0x180008132  lea     rcx, [rbp+57h+var_70]
0x180008136  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000813b  mov     [rbp+57h+var_68], r13
0x18000813f  mov     [rbp+57h+var_60], r13
0x180008143  lea     rdx, [rbp+57h+var_70]
0x180008147  mov     rcx, rdi
0x18000814a  mov     rax, rbx
0x18000814d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008152  mov     ebx, eax
0x180008154  test    eax, eax
0x180008156  jns     short loc_180008162
0x180008158  mov     edx, 0DEh
0x18000815d  jmp     loc_1800081F3
0x180008162  lea     rcx, [rbp+57h+var_50]
0x180008166  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000816b  nop
0x18000816c  lea     rcx, [rbp+57h+var_98]
0x180008170  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008175  mov     rax, [rbp+57h+var_70]
0x180008179  test    rax, rax
0x18000817c  jz      loc_180008239
0x180008182  cmp     [rax], r12w
0x180008186  jz      loc_180008239
0x18000818c  lea     rcx, [rbp+57h+arg_18]
0x180008190  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
  ... truncated ...
```
