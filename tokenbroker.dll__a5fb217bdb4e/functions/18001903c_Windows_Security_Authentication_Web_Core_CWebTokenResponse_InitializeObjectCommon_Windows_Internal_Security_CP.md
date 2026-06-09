# Windows::Security::Authentication::Web::Core::CWebTokenResponse::InitializeObjectCommon(Windows::Internal::Security::CPropertiesSerializer &)

- ea: `0x18001903c`
- end: `0x180019890`
- name: `?InitializeObjectCommon@CWebTokenResponse@Core@Web@Authentication@Security@Windows@@AEAAJAEAVCPropertiesSerializer@5Internal@6@@Z`
- size: `2132`
- prototype: `int(Windows::Security::Authentication::Web::Core::CWebTokenResponse *__hidden this, struct Windows::Internal::Security::CPropertiesSerializer *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018f90`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180016f44`
- `0x1800175c0`
- `0x180018224`
- `0x180018674`
- `0x180018720`
- `0x18001903c`
- `0x180025c60`
- `0x18003fa60`
- `0x180049430`
- `0x18008e690`
- `0x1800f34e4`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019621`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001972a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019742`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001975f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019779`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019621`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001972a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019742`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001975f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800190d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019262`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800192fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800190d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019262`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800192fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800195e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800196b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800197a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800195e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800196b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800197a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180019797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180019797`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180019102`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180019102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019231`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001987c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019231`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001987c`

## string_xrefs

- `0x1800193d1`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x18001949f`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800197c4`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800197e1`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800197f9`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x18001907d`: `WTRes_Token`
- `0x1800190d2`: `Windows.Internal.Security.Credentials.WebAccountInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Security::Authentication::Web::Core::CWebTokenResponse::InitializeObjectCommon(
        Windows::Security::Authentication::Web::Core::CWebTokenResponse *this,
        __int64 **a2)
{
  int StringProperty; // eax
  int EmptyPropertyBag; // ebx
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  void *v8; // r14
  unsigned int v9; // r12d
  int v10; // esi
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, void *, __int64 *); // rbx
  int HStringPropertyBagProperty; // eax
  char *v17; // rax
  _QWORD *v18; // rdi
  void *v19; // rcx
  void *v20; // rbx
  unsigned int v21; // r14d
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  HSTRING v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, __int64 *); // rbx
  __int64 v49; // rdx
  HSTRING *v50; // r14
  HSTRING v51; // rbx
  int v52; // [rsp+20h] [rbp-99h]
  unsigned int v53; // [rsp+30h] [rbp-89h] BYREF
  __int64 v54; // [rsp+38h] [rbp-81h] BYREF
  __int64 v55; // [rsp+40h] [rbp-79h] BYREF
  __int64 v56; // [rsp+48h] [rbp-71h] BYREF
  __int64 v57; // [rsp+50h] [rbp-69h] BYREF
  HSTRING v58; // [rsp+58h] [rbp-61h] BYREF
  void *v59; // [rsp+60h] [rbp-59h] BYREF
  __int64 v60; // [rsp+68h] [rbp-51h] BYREF
  HSTRING v61; // [rsp+70h] [rbp-49h] BYREF
  __int64 v62; // [rsp+78h] [rbp-41h] BYREF
  HSTRING v63; // [rsp+80h] [rbp-39h] BYREF
  int v64; // [rsp+88h] [rbp-31h]
  char v65; // [rsp+90h] [rbp-29h] BYREF
  HSTRING string; // [rsp+98h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-19h] BYREF
  HSTRING v68; // [rsp+B8h] [rbp-1h] BYREF
  HSTRING_HEADER v69; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v58 = 0;
  if ( WindowsCreateStringReference(L"WTRes_Token", 0xBu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  StringProperty = Windows::Internal::Security::CPropertiesSerializer::GetStringProperty(
                     (Windows::Internal::Security::CPropertiesSerializer *)a2,
                     string,
                     &v58);
  EmptyPropertyBag = 0;
  if ( StringProperty != -2147483637 )
    EmptyPropertyBag = StringProperty;
  if ( EmptyPropertyBag < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x528,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)EmptyPropertyBag,
      v52);
LABEL_61:
    if ( v58 )
      WindowsDeleteString(v58);
    return (unsigned int)EmptyPropertyBag;
  }
  v57 = 0;
  v56 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Security.Credentials.WebAccountInternal",
         0x38u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_067cd3b2_1f07_4710_8ae5_5cd2e71efc11, &v56);
  EmptyPropertyBag = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x534,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v52);
LABEL_102:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
    goto LABEL_61;
  }
  v55 = 0;
  v8 = 0;
  v9 = 0;
  if ( WindowsCreateStringReference(L"WTRes_Account", 0xDu, &v69, &v68) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v59 = 0;
  v53 = 0;
  v63 = 0;
  v64 = 0;
  v10 = -2147024809;
  if ( v68 )
  {
    v11 = a2[1];
    v12 = *v11;
    v61 = (HSTRING)&v63;
    v62 = 0;
    EmptyPropertyBag = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v12 + 48))(v11, v68, &v62);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v61);
    if ( EmptyPropertyBag >= 0 )
    {
      string = v63;
      LODWORD(hstringHeader.Reserved.Reserved1) = v64;
      v53 = 0;
      v59 = 0;
      EmptyPropertyBag = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&string);
      if ( EmptyPropertyBag >= 0 )
      {
        EmptyPropertyBag = (*(__int64 (__fastcall **)(__int64, unsigned int *, void **))(*(_QWORD *)v13 + 208LL))(
                             v13,
                             &v53,
                             &v59);
        if ( EmptyPropertyBag >= 0 )
        {
          v8 = v59;
          v9 = v53;
        }
      }
    }
  }
  else
  {
    EmptyPropertyBag = -2147024809;
  }
  RoVariant::~RoVariant((RoVariant *)&v63);
  if ( EmptyPropertyBag < 0 )
  {
    if ( EmptyPropertyBag == -2147483637 )
      goto LABEL_22;
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x550,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)EmptyPropertyBag,
      v52);
    v31 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    goto LABEL_61;
  }
  v14 = v56;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, void *, __int64 *))(*(_QWORD *)v56 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  EmptyPropertyBag = v15(v14, v9, v8, &v57);
  if ( EmptyPropertyBag >= 0 )
  {
    v47 = v57;
    v48 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v57 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
    EmptyPropertyBag = v48(v47, &v55);
  }
  if ( v8 )
    CoTaskMemFree(v8);
  if ( EmptyPropertyBag < 0 )
    goto LABEL_55;
LABEL_22:
  v54 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  if ( WindowsCreateStringReference(L"WTRes_PropertyBag", 0x11u, &v69, &v68) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  HStringPropertyBagProperty = Windows::Internal::Security::CPropertiesSerializer::GetHStringPropertyBagProperty(
                                 a2,
                                 v68,
                                 &v54);
  EmptyPropertyBag = 0;
  if ( HStringPropertyBagProperty != -2147483637 )
    EmptyPropertyBag = HStringPropertyBagProperty;
  if ( EmptyPropertyBag < 0 )
  {
    v49 = 1369;
    goto LABEL_101;
  }
  if ( !v54 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
    EmptyPropertyBag = MakeEmptyPropertyBag(&v54);
    if ( EmptyPropertyBag < 0 )
    {
      v49 = 1374;
LABEL_101:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v49,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
        (const char *)(unsigned int)EmptyPropertyBag,
        v52);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
      goto LABEL_102;
    }
  }
  v60 = 0;
  v17 = (char *)Microsoft::WRL::Details::Make<Windows::Security::Authentication::Web::Core::CWebProviderError,>(&v59);
  v18 = 0;
  if ( &v65 != v17 )
  {
    v18 = *(_QWORD **)v17;
    *(_QWORD *)v17 = 0;
  }
  v63 = (HSTRING)v18;
  v19 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( v18 )
  {
    v20 = 0;
    v21 = 0;
    if ( WindowsCreateStringReference(L"WTRes_Error", 0xBu, &v69, &v68) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v59 = 0;
    v53 = 0;
    v61 = 0;
    LODWORD(v62) = 0;
    if ( v68 )
    {
      v22 = a2[1];
      v23 = *v22;
      string = (HSTRING)&v61;
      hstringHeader.Reserved.Reserved1 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING_HEADER *))(v23 + 48))(v22, v68, &hstringHeader);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&string);
      if ( v10 >= 0 )
      {
        string = v61;
        LODWORD(hstringHeader.Reserved.Reserved1) = v62;
        v53 = 0;
        v59 = 0;
        v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&string);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *, void **))(*(_QWORD *)v24 + 208LL))(v24, &v53, &v59);
          if ( v10 >= 0 )
          {
            v20 = v59;
            v21 = v53;
          }
        }
      }
    }
    RoVariant::~RoVariant((RoVariant *)&v61);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD *, void *, _QWORD))(v18[3] + 24LL))(v18 + 3, v20, v21);
      if ( v10 >= 0 )
        v10 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::CWebProviderError>::As<Windows::Security::Authentication::Web::Core::IWebProviderError>(
                &v63,
                &v60);
      if ( v20 )
        CoTaskMemFree(v20);
      if ( v10 < 0 )
      {
LABEL_42:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x587,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
          (const char *)(unsigned int)v10,
          v52);
        v25 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
        v26 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        v27 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v28 = v56;
        if ( v56 )
        {
          v56 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        v29 = v57;
        if ( v57 )
        {
          v57 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        v30 = v58;
        if ( !v58 )
          return (unsigned int)v10;
        goto LABEL_77;
      }
    }
    else
    {
      if ( v10 != -2147483637 )
        goto LABEL_42;
      v10 = 0;
    }
    v50 = (HSTRING *)((char *)this + 96);
    v51 = v58;
    if ( WindowsIsStringEmpty(v58) )
    {
      Windows::Internal::String::Release((Windows::Security::Authentication::Web::Core::CWebTokenResponse *)((char *)this + 96));
    }
    else
    {
      WindowsDeleteString(*v50);
      *v50 = v51;
      v51 = 0;
      v58 = 0;
    }
    v35 = *((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = v55;
    v55 = v35;
    v36 = *((_QWORD *)this + 14);
    *((_QWORD *)this + 14) = v54;
    v54 = v36;
    v37 = *((_QWORD *)this + 15);
    *((_QWORD *)this + 15) = v60;
    v60 = v37;
    if ( v37 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
    v38 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v41 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    if ( !v51 )
      return (unsigned int)v10;
    v30 = v51;
LABEL_77:
    WindowsDeleteString(v30);
    return (unsigned int)v10;
  }
  v42 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  if ( v58 )
    WindowsDeleteString(v58);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001903c  mov     [rsp-8+arg_10], rbx
0x180019041  push    rbp
0x180019042  push    rsi
0x180019043  push    rdi
0x180019044  push    r12
0x180019046  push    r13
0x180019048  push    r14
0x18001904a  push    r15
0x18001904c  lea     rbp, [rsp-27h]
0x180019051  sub     rsp, 0E0h
0x180019058  mov     rax, cs:__security_cookie
0x18001905f  xor     rax, rsp
0x180019062  mov     [rbp+57h+var_38], rax
0x180019066  mov     r13, rdx
0x180019069  mov     r15, rcx
0x18001906c  xor     edi, edi
0x18001906e  mov     [rbp+57h+var_B8], rdi
0x180019072  lea     r9, [rbp+57h+string]; string
0x180019076  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001907a  lea     edx, [rdi+0Bh]; length
0x18001907d  lea     rcx, aWtresToken; "WTRes_Token"
0x180019084  call    cs:__imp_WindowsCreateStringReference
0x18001908a  lea     esi, [rdi+1]
0x18001908d  mov     r14d, 0C000000Dh
0x180019093  test    eax, eax
0x180019095  js      loc_180019754
0x18001909b  lea     r8, [rbp+57h+var_B8]; HSTRING *
0x18001909f  mov     rdx, [rbp+57h+string]; HSTRING
0x1800190a3  mov     rcx, r13; this
0x1800190a6  call    ?GetStringProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAPEAU5@@Z; Windows::Internal::Security::CPropertiesSerializer::GetStringProperty(HSTRING__ *,HSTRING__ * *)
0x1800190ab  mov     ebx, edi
0x1800190ad  cmp     eax, 8000000Bh
0x1800190b2  cmovnz  ebx, eax
0x1800190b5  test    ebx, ebx
0x1800190b7  js      loc_1800197BD
0x1800190bd  mov     [rbp+57h+var_C0], rdi
0x1800190c1  mov     [rbp+57h+var_C8], rdi
0x1800190c5  lea     r9, [rbp+57h+string]; string
0x1800190c9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800190cd  mov     edx, 38h ; '8'; length
0x1800190d2  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Credentials_WebAccountInternal@@3QBGB; "Windows.Internal.Security.Credentials.W"...
0x1800190d9  call    cs:__imp_WindowsCreateStringReference
0x1800190df  test    eax, eax
0x1800190e1  js      loc_180019616
0x1800190e7  mov     rbx, [rbp+57h+string]
0x1800190eb  lea     rcx, [rbp+57h+var_C8]
0x1800190ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800190f4  lea     r8, [rbp+57h+var_C8]
0x1800190f8  lea     rdx, _GUID_067cd3b2_1f07_4710_8ae5_5cd2e71efc11
0x1800190ff  mov     rcx, rbx
0x180019102  call    cs:__imp_RoGetActivationFactory
0x180019108  mov     ebx, eax
0x18001910a  test    eax, eax
0x18001910c  js      loc_1800197DA
0x180019112  mov     [rbp+57h+var_D0], rdi
0x180019116  mov     r14, rdi
0x180019119  mov     r12d, edi
0x18001911c  lea     r9, [rbp+57h+var_58]; string
0x180019120  lea     r8, [rbp+57h+var_50]; hstringHeader
0x180019124  mov     edx, 0Dh; length
0x180019129  lea     rcx, aWtresAccount; "WTRes_Account"
0x180019130  call    cs:__imp_WindowsCreateStringReference
0x180019136  test    eax, eax
0x180019138  js      loc_180019735
0x18001913e  mov     rdx, [rbp+57h+var_58]
0x180019142  mov     [rbp+57h+var_B0], rdi
0x180019146  mov     [rsp+110h+var_E0], edi
0x18001914a  mov     [rbp+57h+var_90], rdi
0x18001914e  mov     [rbp+57h+var_88], edi
0x180019151  mov     esi, 80070057h
0x180019156  test    rdx, rdx
0x180019159  jz      loc_18001974D
0x18001915f  mov     rcx, [r13+8]
0x180019163  mov     rax, [rcx]
0x180019166  lea     r8, [rbp+57h+var_90]
0x18001916a  mov     [rbp+57h+var_A0], r8
0x18001916e  mov     [rbp+57h+var_98], rdi
0x180019172  lea     r8, [rbp+57h+var_98]
0x180019176  mov     rax, [rax+30h]
0x18001917a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001917f  mov     ebx, eax
0x180019181  lea     rcx, [rbp+57h+var_A0]; this
0x180019185  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x18001918a  mov     eax, ebx
0x18001918c  shr     eax, 1Fh
0x18001918f  xor     al, 1
0x180019191  jz      short loc_1800191E2
0x180019193  mov     r9, [rbp+57h+var_90]
0x180019197  mov     [rbp+57h+string], r9
0x18001919b  mov     eax, [rbp+57h+var_88]
0x18001919e  mov     dword ptr [rbp+57h+hstringHeader.Reserved], eax
0x1800191a1  mov     [rsp+110h+var_E0], edi
0x1800191a5  mov     [rbp+57h+var_B0], rdi
0x1800191a9  lea     rcx, [rbp+57h+string]; this
0x1800191ad  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x1800191b2  mov     ebx, eax
0x1800191b4  test    eax, eax
0x1800191b6  js      short loc_1800191E2
0x1800191b8  mov     rax, [r9]
0x1800191bb  lea     r8, [rbp+57h+var_B0]
0x1800191bf  lea     rdx, [rsp+110h+var_E0]
0x1800191c4  mov     rcx, r9
0x1800191c7  mov     rax, [rax+0D0h]
0x1800191ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191d3  mov     ebx, eax
0x1800191d5  test    eax, eax
0x1800191d7  js      short loc_1800191E2
0x1800191d9  mov     r14, [rbp+57h+var_B0]
0x1800191dd  mov     r12d, [rsp+110h+var_E0]
0x1800191e2  lea     rcx, [rbp+57h+var_90]; this
0x1800191e6  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800191eb  test    ebx, ebx
0x1800191ed  js      loc_180019489
0x1800191f3  mov     rdi, [rbp+57h+var_C8]
0x1800191f7  mov     rax, [rdi]
0x1800191fa  mov     rbx, [rax+38h]
0x1800191fe  lea     rcx, [rbp+57h+var_C0]
0x180019202  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180019207  lea     r9, [rbp+57h+var_C0]
0x18001920b  mov     r8, r14
0x18001920e  mov     edx, r12d
0x180019211  mov     rcx, rdi
0x180019214  mov     rax, rbx
0x180019217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001921c  mov     ebx, eax
0x18001921e  xor     r12d, r12d
0x180019221  test    eax, eax
0x180019223  jns     loc_1800196C9
0x180019229  test    r14, r14
0x18001922c  jz      short loc_180019237
0x18001922e  mov     rcx, r14; pv
0x180019231  call    cs:__imp_CoTaskMemFree
0x180019237  test    ebx, ebx
0x180019239  js      loc_180019498
0x18001923f  mov     [rsp+110h+var_D8], r12
0x180019244  lea     rcx, [rsp+110h+var_D8]
0x180019249  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001924e  lea     r9, [rbp+57h+var_58]; string
0x180019252  lea     r8, [rbp+57h+var_50]; hstringHeader
0x180019256  mov     edx, 11h; length
0x18001925b  lea     rcx, aWtresPropertyb; "WTRes_PropertyBag"
0x180019262  call    cs:__imp_WindowsCreateStringReference
0x180019268  test    eax, eax
0x18001926a  js      loc_18001971B
0x180019270  lea     r8, [rsp+110h+var_D8]
0x180019275  mov     rdx, [rbp+57h+var_58]
0x180019279  mov     rcx, r13
0x18001927c  call    ?GetHStringPropertyBagProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@4@@Z; Windows::Internal::Security::CPropertiesSerializer::GetHStringPropertyBagProperty(HSTRING__ *,Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> * *)
0x180019281  mov     ebx, r12d
0x180019284  cmp     eax, 8000000Bh
0x180019289  cmovnz  ebx, eax
0x18001928c  test    ebx, ebx
0x18001928e  js      loc_1800197F4
0x180019294  cmp     [rsp+110h+var_D8], r12
0x180019299  jz      loc_1800196F3
0x18001929f  mov     [rbp+57h+var_A8], r12
0x1800192a3  lea     rcx, [rbp+57h+var_B0]
0x1800192a7  call    ??$Make@VCWebProviderError@Core@Web@Authentication@Security@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCWebProviderError@Core@Web@Authentication@Security@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::Security::Authentication::Web::Core::CWebProviderError,>(void)
0x1800192ac  mov     rdi, r12
0x1800192af  lea     rcx, [rbp+57h+var_80]
0x1800192b3  cmp     rcx, rax
0x1800192b6  jnz     loc_18001983A
0x1800192bc  mov     [rbp+57h+var_90], rdi
0x1800192c0  mov     rcx, [rbp+57h+var_B0]
0x1800192c4  test    rcx, rcx
0x1800192c7  jz      short loc_1800192DA
0x1800192c9  mov     [rbp+57h+var_B0], r12
0x1800192cd  mov     rax, [rcx]
0x1800192d0  mov     rax, [rax+10h]
0x1800192d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192d9  nop
0x1800192da  test    rdi, rdi
0x1800192dd  jz      loc_18001962C
0x1800192e3  mov     rbx, r12
0x1800192e6  mov     r14d, r12d
0x1800192e9  lea     r9, [rbp+57h+var_58]; string
0x1800192ed  lea     r8, [rbp+57h+var_50]; hstringHeader
0x1800192f1  mov     edx, 0Bh; length
0x1800192f6  lea     rcx, aWtresError; "WTRes_Error"
0x1800192fd  call    cs:__imp_WindowsCreateStringReference
0x180019303  test    eax, eax
0x180019305  js      loc_18001976A
0x18001930b  mov     rdx, [rbp+57h+var_58]
0x18001930f  mov     [rbp+57h+var_B0], r12
0x180019313  mov     [rsp+110h+var_E0], r12d
0x180019318  mov     [rbp+57h+var_A0], r12
0x18001931c  mov     dword ptr [rbp+57h+var_98], r12d
0x180019320  test    rdx, rdx
0x180019323  jz      loc_1800193AD
0x180019329  mov     rcx, [r13+8]
0x18001932d  mov     rax, [rcx]
0x180019330  lea     r8, [rbp+57h+var_A0]
0x180019334  mov     [rbp+57h+string], r8
0x180019338  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r12
0x18001933c  lea     r8, [rbp+57h+hstringHeader]
0x180019340  mov     rax, [rax+30h]
0x180019344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019349  mov     esi, eax
0x18001934b  lea     rcx, [rbp+57h+string]; this
0x18001934f  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180019354  mov     eax, esi
0x180019356  shr     eax, 1Fh
0x180019359  xor     al, 1
0x18001935b  jz      short loc_1800193AD
0x18001935d  mov     r9, [rbp+57h+var_A0]
0x180019361  mov     [rbp+57h+string], r9
0x180019365  mov     eax, dword ptr [rbp+57h+var_98]
0x180019368  mov     dword ptr [rbp+57h+hstringHeader.Reserved], eax
0x18001936b  mov     [rsp+110h+var_E0], r12d
0x180019370  mov     [rbp+57h+var_B0], r12
0x180019374  lea     rcx, [rbp+57h+string]; this
0x180019378  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x18001937d  mov     esi, eax
0x18001937f  test    eax, eax
0x180019381  js      short loc_1800193AD
0x180019383  mov     rax, [r9]
0x180019386  lea     r8, [rbp+57h+var_B0]
0x18001938a  lea     rdx, [rsp+110h+var_E0]
0x18001938f  mov     rcx, r9
0x180019392  mov     rax, [rax+0D0h]
0x180019399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001939e  mov     esi, eax
0x1800193a0  test    eax, eax
0x1800193a2  js      short loc_1800193AD
0x1800193a4  mov     rbx, [rbp+57h+var_B0]
0x1800193a8  mov     r14d, [rsp+110h+var_E0]
0x1800193ad  lea     rcx, [rbp+57h+var_A0]; this
0x1800193b1  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x1800193b6  test    esi, esi
0x1800193b8  jns     loc_180019845
0x1800193be  cmp     esi, 8000000Bh
0x1800193c4  jz      loc_180019887
0x1800193ca  mov     rcx, [rbp+5Fh]; this
0x1800193ce  mov     r9d, esi; char *
0x1800193d1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800193d8  mov     edx, 587h; void *
0x1800193dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800193e2  nop
0x1800193e3  mov     rcx, [rbp+57h+var_A8]
0x1800193e7  test    rcx, rcx
0x1800193ea  jz      short loc_1800193FD
0x1800193ec  mov     [rbp+57h+var_A8], r12
0x1800193f0  mov     rax, [rcx]
0x1800193f3  mov     rax, [rax+10h]
0x1800193f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193fc  nop
0x1800193fd  mov     rax, [rdi]
0x180019400  mov     rcx, rdi
0x180019403  mov     rax, [rax+10h]
0x180019407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001940c  nop
0x18001940d  mov     rcx, [rsp+110h+var_D8]
0x180019412  test    rcx, rcx
0x180019415  jz      short loc_180019429
0x180019417  mov     [rsp+110h+var_D8], r12
0x18001941c  mov     rax, [rcx]
0x18001941f  mov     rax, [rax+10h]
0x180019423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019428  nop
0x180019429  mov     rcx, [rbp+57h+var_D0]
0x18001942d  test    rcx, rcx
0x180019430  jz      short loc_180019443
0x180019432  mov     [rbp+57h+var_D0], r12
0x180019436  mov     rax, [rcx]
0x180019439  mov     rax, [rax+10h]
0x18001943d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019442  nop
0x180019443  mov     rcx, [rbp+57h+var_C8]
0x180019447  test    rcx, rcx
0x18001944a  jz      short loc_18001945D
0x18001944c  mov     [rbp+57h+var_C8], r12
0x180019450  mov     rax, [rcx]
0x180019453  mov     rax, [rax+10h]
0x180019457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001945c  nop
0x18001945d  mov     rcx, [rbp+57h+var_C0]
0x180019461  test    rcx, rcx
0x180019464  jz      short loc_180019477
0x180019466  mov     [rbp+57h+var_C0], r12
0x18001946a  mov     rax, [rcx]
0x18001946d  mov     rax, [rax+10h]
0x180019471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019476  nop
0x180019477  mov     rcx, [rbp+57h+var_B8]
0x18001947b  test    rcx, rcx
0x18001947e  jz      loc_1800195ED
0x180019484  jmp     loc_1800195E7
0x180019489  xor     r12d, r12d
0x18001948c  cmp     ebx, 8000000Bh
0x180019492  jz      loc_18001923F
0x180019498  mov     rcx, [rbp+5Fh]; this
0x18001949c  mov     r9d, ebx; char *
0x18001949f  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800194a6  mov     edx, 550h; void *
0x1800194ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194b0  nop
0x1800194b1  mov     rcx, [rbp+57h+var_D0]
0x1800194b5  test    rcx, rcx
0x1800194b8  jz      short loc_1800194CB
0x1800194ba  mov     [rbp+57h+var_D0], r12
  ... truncated ...
```
