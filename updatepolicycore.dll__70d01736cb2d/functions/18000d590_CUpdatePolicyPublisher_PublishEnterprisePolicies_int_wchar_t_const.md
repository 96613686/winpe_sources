# CUpdatePolicyPublisher::PublishEnterprisePolicies(int,wchar_t const *)

- ea: `0x18000d590`
- end: `0x18000e0d6`
- name: `?PublishEnterprisePolicies@CUpdatePolicyPublisher@@UEAAJHPEB_W@Z`
- size: `2886`
- prototype: `__int64 __fastcall(CUpdatePolicyPublisher *this, unsigned int, const wchar_t *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000aac0`
- `0x18000d1f0`
- `0x18000d590`
- `0x18000e310`
- `0x18000e388`
- `0x18000e4cc`
- `0x18000e588`
- `0x18000e620`
- `0x18000e6a0`
- `0x18000e710`
- `0x18000e7e4`
- `0x18000e978`
- `0x18000ea40`
- `0x18000ec2c`
- `0x18000edf0`
- `0x18000f8a8`
- `0x18000fcc4`
- `0x18000fd94`
- `0x180010260`
- `0x18002d3fc`
- `0x18002d730`
- `0x18002ffd0`
- `0x180030cb4`
- `0x180036a10`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000da67`
- `OLEAUT32!__imp_SysAllocString` at `0x18000da67`
- `OLEAUT32!__imp_VariantInit` at `0x18000d836`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9bb`
- `OLEAUT32!__imp_VariantInit` at `0x18000d836`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9bb`
- `OLEAUT32!__imp_VariantClear` at `0x18000db4c`
- `OLEAUT32!__imp_VariantClear` at `0x18000db4c`
- `OLEAUT32!__imp_VariantCopy` at `0x18000dadd`
- `OLEAUT32!__imp_VariantCopy` at `0x18000dadd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000da5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d86b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000db74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dc9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dd37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d86b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000db74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dc9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dd37`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d645`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d645`

## string_xrefs

- `0x18000d6b9`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000d6f8`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000dc8f`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000dcc1`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000dd01`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000dd22`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000dd4d`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000df9f`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000e00a`: `C:\__w\1\s\src\Client\policy\src\ComApi\UpdatePolicyApi.cpp`
- `0x18000d621`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
__int64 __fastcall CUpdatePolicyPublisher::PublishEnterprisePolicies(
        CUpdatePolicyPublisher *this,
        unsigned int a2,
        const wchar_t *a3)
{
  _QWORD *v3; // rax
  HRESULT StringReference; // eax
  int v5; // edx
  unsigned int v6; // r8d
  HRESULT ActivationFactory; // ebx
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rdi
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdx
  unsigned __int64 i; // rbx
  wchar_t *v16; // rdx
  __int64 v17; // r8
  __m128i si128; // xmm7
  int v19; // eax
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rdi
  int v22; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rbx
  size_t v27; // rdi
  const wchar_t *v28; // rdx
  const wchar_t *v29; // rcx
  size_t v30; // rsi
  size_t v31; // r8
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 (__fastcall *v35)(__int64, HSTRING *); // rdi
  const OLECHAR *v36; // rax
  VARTYPE v37; // ax
  LONG v38; // eax
  __int64 v39; // rbx
  __int64 v40; // rcx
  _QWORD *v41; // rdi
  __int64 v42; // rax
  _QWORD *v43; // rbx
  _QWORD *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rdx
  double v48; // rax
  __int64 v49; // rdx
  _OWORD *v50; // r8
  int v51; // r14d
  __int64 v52; // r15
  __int64 v53; // rdi
  unsigned int v54; // r12d
  int WUSystemInterface; // eax
  unsigned int v56; // edx
  __int64 v57; // rdx
  int v58; // eax
  int v59; // eax
  wchar_t **v61; // [rsp+28h] [rbp-E0h]
  int v62[4]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v63; // [rsp+58h] [rbp-B0h]
  __int128 v64; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v65[3]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v66; // [rsp+88h] [rbp-80h]
  char v67[32]; // [rsp+98h] [rbp-70h] BYREF
  double v68[2]; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG pvargSrc; // [rsp+C8h] [rbp-40h] BYREF
  char v70; // [rsp+E0h] [rbp-28h] BYREF
  char v71[7]; // [rsp+E1h] [rbp-27h] BYREF
  __int64 v72; // [rsp+E8h] [rbp-20h] BYREF
  unsigned int v73; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v74; // [rsp+F8h] [rbp-10h] BYREF
  HSTRING v75; // [rsp+100h] [rbp-8h] BYREF
  HSTRING v76; // [rsp+108h] [rbp+0h] BYREF
  int v77; // [rsp+110h] [rbp+8h] BYREF
  __int64 v78; // [rsp+118h] [rbp+10h] BYREF
  __int128 hstringHeader; // [rsp+120h] [rbp+18h] BYREF
  __int128 hstringHeader_16; // [rsp+130h] [rbp+28h] BYREF
  __int128 v81; // [rsp+140h] [rbp+38h] BYREF
  __int64 v82; // [rsp+150h] [rbp+48h]
  __int64 *v83; // [rsp+158h] [rbp+50h] BYREF
  __int64 v84; // [rsp+160h] [rbp+58h] BYREF
  __int64 v85; // [rsp+168h] [rbp+60h] BYREF
  __int64 v86; // [rsp+170h] [rbp+68h] BYREF
  _QWORD v87[2]; // [rsp+178h] [rbp+70h] BYREF
  __int128 v88; // [rsp+188h] [rbp+80h] BYREF
  __int64 v89; // [rsp+198h] [rbp+90h]
  _OWORD v90[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  wchar_t *S1[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  size_t v92; // [rsp+1D8h] [rbp+D0h]
  unsigned __int64 v93; // [rsp+1E0h] [rbp+D8h]
  VARIANTARG pvarg; // [rsp+1E8h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  v73 = a2;
  *(_QWORD *)&v68[0] = a3;
  v86 = 0;
  v85 = 0;
  v84 = 0;
  v81 = 0;
  v82 = 0;
  v87[1] = 0;
  v3 = operator new(0x40u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  v87[0] = v3;
  *((_QWORD *)&hstringHeader_16 + 1) = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Data.Json.JsonValue",
                      0x1Bu,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16 + 1);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v5, v6);
    JUMPOUT(0x18000E0D5LL);
  }
  ActivationFactory = RoGetActivationFactory(
                        *((_QWORD *)&hstringHeader_16 + 1),
                        &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c,
                        &v86);
  if ( ActivationFactory < 0 )
  {
    v8 = 392;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v61);
    goto LABEL_131;
  }
  v9 = v86;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v86 + 48LL);
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v68);
  ActivationFactory = v10(v9, *(_QWORD *)(v11 + 24), &v85);
  if ( ActivationFactory < 0 )
  {
    v8 = 393;
    goto LABEL_8;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v85 + 96LL))(v85, &v84);
  if ( ActivationFactory < 0 )
  {
    v8 = 394;
    goto LABEL_8;
  }
  v83 = 0;
  v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v84)(
          v84,
          &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099,
          &v83);
  ActivationFactory = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
      (const char *)(unsigned int)v12,
      (int)v61);
    goto LABEL_129;
  }
  v13 = *v83;
  v78 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v13 + 48))(v83, &v78);
  if ( ActivationFactory < 0 )
  {
    v14 = 400;
LABEL_126:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v61);
    goto LABEL_127;
  }
  v70 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v78 + 56LL))(v78, &v70);
  if ( ActivationFactory < 0 )
  {
    v14 = 403;
    goto LABEL_126;
  }
  for ( i = 1; i <= 0x55; ++i )
  {
    v16 = off_18004B4F0[15 * (int)i];
    if ( v16 )
    {
      hstringHeader = 0;
      hstringHeader_16 = 0;
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      std::wstring::_Construct<1,wchar_t const *>(&hstringHeader);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
        v87,
        v68,
        &hstringHeader);
      std::wstring::~wstring(&hstringHeader);
    }
  }
  if ( !v70 )
  {
LABEL_65:
    v64 = 0;
    v40 = 0;
    v65[0] = 0;
    *(_OWORD *)v62 = 0;
    v63 = 0;
    v88 = 0;
    v89 = 0;
    v41 = (_QWORD *)*((_QWORD *)&v81 + 1);
    v42 = v81;
    if ( (_QWORD)v81 != *((_QWORD *)&v81 + 1) )
    {
      v43 = (_QWORD *)(v81 + 32);
      while ( 1 )
      {
        v44 = v43 - 4;
        if ( *(v43 - 1) > 7u )
          v44 = (_QWORD *)*v44;
        *(_QWORD *)&v68[0] = v44;
        if ( *((_QWORD *)&v64 + 1) == v40 )
        {
          std::vector<void *>::_Emplace_reallocate<void *>(&v64, *((_QWORD *)&v64 + 1), v68);
        }
        else
        {
          **((_QWORD **)&v64 + 1) = v44;
          *((_QWORD *)&v64 + 1) += 8LL;
        }
        v48 = *(double *)&v43;
        if ( v43[3] > 7u )
          v48 = *(double *)v43;
        v68[0] = v48;
        if ( *(_QWORD *)&v62[2] == v63 )
        {
          std::vector<void *>::_Emplace_reallocate<void *>(v62, *(_QWORD *)&v62[2], v68);
        }
        else
        {
          **(double **)&v62[2] = v48;
          *(_QWORD *)&v62[2] += 8LL;
        }
        if ( v73 )
        {
          v49 = *((_QWORD *)&v88 + 1);
          v50 = v43 + 4;
          if ( *((_QWORD *)&v88 + 1) == v89 )
          {
            std::vector<tagVARIANT>::_Emplace_reallocate<tagVARIANT const &>(&v88, *((_QWORD *)&v88 + 1), v50);
          }
          else
          {
            **((_OWORD **)&v88 + 1) = *v50;
            *(_QWORD *)(v49 + 16) = v43[6];
            *((_QWORD *)&v88 + 1) += 24LL;
          }
        }
        v43 += 11;
        if ( v43 - 4 == v41 )
          break;
        v40 = v65[0];
      }
      v41 = (_QWORD *)*((_QWORD *)&v81 + 1);
      v42 = v81;
    }
    *(_QWORD *)&hstringHeader = &v81;
    *((_QWORD *)&hstringHeader + 1) = &v73;
    *(_QWORD *)&hstringHeader_16 = &v88;
    BYTE8(hstringHeader_16) = 1;
    v51 = v62[0];
    v52 = v64;
    v53 = 0x2E8BA2E8BA2E8BA3LL * (((__int64)v41 - v42) >> 3);
    v54 = v73;
    WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface((WUSystemInterfaceHelper *)&v88);
    ActivationFactory = WUSystemInterface;
    if ( WUSystemInterface >= 0 )
    {
      WUSystemInterface = WUSystemInterfaceHelper::IsCapabilitySupported((WUSystemInterfaceHelper *)5, v56);
      ActivationFactory = WUSystemInterface;
      if ( WUSystemInterface >= 0 )
      {
        v72 = 0;
        v58 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))g_WUSystemInterface)(
                g_WUSystemInterface,
                &GUID_8fd9dcdc_f120_4fe5_95ce_75542fe86b18,
                &v72);
        ActivationFactory = v58;
        if ( v58 >= 0 )
        {
          v59 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v72 + 528LL))(
                  v72,
                  v54,
                  (unsigned int)v53,
                  v52);
          ActivationFactory = v59;
          if ( v59 >= 0 )
          {
            if ( v72 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
            ActivationFactory = 0;
            goto LABEL_125;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x357,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
            (const char *)(unsigned int)v59,
            v51);
          if ( v72 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x352,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
            (const char *)(unsigned int)v58,
            (int)v61);
          if ( v72 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
        }
LABEL_121:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x200,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
          (const char *)(unsigned int)ActivationFactory,
          (int)v61);
LABEL_125:
        wil::details::lambda_call__lambda_d4daf6b2210cb606e8a2819f8424c7cd___::_lambda_call__lambda_d4daf6b2210cb606e8a2819f8424c7cd___(&hstringHeader);
        std::vector<tagVARIANT>::~vector<tagVARIANT>(&v88);
        std::vector<void *>::~vector<void *>(v62);
        std::vector<void *>::~vector<void *>(&v64);
        goto LABEL_127;
      }
      if ( WUSystemInterface == -2147467262 || WUSystemInterface == -2147024846 )
        goto LABEL_121;
      v57 = 847;
    }
    else
    {
      v57 = 843;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v57,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
      (const char *)(unsigned int)WUSystemInterface,
      (int)v61);
    goto LABEL_121;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v90[0] = 0;
    v90[1] = si128;
    LOWORD(v90[0]) = 0;
    *(_OWORD *)S1 = 0;
    v92 = 0;
    v93 = 7;
    LOWORD(S1[0]) = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v72 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v78 + 48LL))(v78, &v72);
    ActivationFactory = v19;
    if ( v19 < 0 )
      break;
    v20 = v72;
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v72 + 48LL);
    WindowsDeleteString(0);
    v76 = 0;
    v22 = v21(v20, &v76);
    ActivationFactory = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AC,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
        (const char *)(unsigned int)v22,
        (int)v61);
      goto LABEL_89;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v76, 0);
    hstringHeader = 0;
    hstringHeader_16 = 0;
    v24 = -1;
    do
      ++v24;
    while ( StringRawBuffer[v24] );
    std::wstring::_Construct<1,wchar_t const *>(&hstringHeader);
    *(_OWORD *)&v65[1] = 0;
    v66 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v65[1]);
    v25 = std::wstring::wstring(v67, &hstringHeader);
    v61 = S1;
    ActivationFactory = CUpdatePolicyPublisher::GetPolicyNodeAndName(S1, v25, &v65[1], v90);
    if ( ActivationFactory < 0 )
    {
      v47 = 434;
LABEL_86:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v47,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)S1);
      goto LABEL_87;
    }
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
      v87,
      &v65[1],
      S1);
    v26 = v66;
    if ( *(_BYTE *)(v66 + 25) )
      goto LABEL_41;
    v27 = *(_QWORD *)(v66 + 48);
    v28 = (const wchar_t *)(v66 + 32);
    if ( *(_QWORD *)(v66 + 56) > 7u )
      v28 = *(const wchar_t **)v28;
    v29 = (const wchar_t *)S1;
    if ( v93 > 7 )
      v29 = S1[0];
    v30 = v92;
    v31 = v92;
    if ( v27 < v92 )
      v31 = *(_QWORD *)(v66 + 48);
    v32 = wmemcmp(v29, v28, v31);
    if ( !v32 )
    {
      if ( v30 >= v27 )
        v32 = v30 > v27;
      else
        v32 = -1;
    }
    if ( v32 < 0 )
    {
LABEL_41:
      v33 = v87[0];
      v26 = v87[0];
    }
    else
    {
      v33 = v87[0];
    }
    if ( v26 == v33 )
    {
      ActivationFactory = -2147024809;
      v47 = 438;
      goto LABEL_86;
    }
    memset(&pvargSrc, 0, sizeof(pvargSrc));
    VariantInit(&pvargSrc);
    v74 = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v72 + 56LL))(v72, &v74);
    if ( ActivationFactory < 0 )
    {
      v46 = 444;
LABEL_80:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v46,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)S1);
LABEL_81:
      if ( v74 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
LABEL_87:
      std::wstring::~wstring(&hstringHeader);
LABEL_89:
      WindowsDeleteString(v76);
      v76 = 0;
      goto LABEL_91;
    }
    v77 = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v74 + 48LL))(v74, &v77);
    if ( ActivationFactory < 0 )
    {
      v46 = 447;
      goto LABEL_80;
    }
    v71[0] = 0;
    v75 = 0;
    v68[0] = 0.0;
    if ( v77 == 1 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v74 + 80LL))(v74, v71);
      if ( ActivationFactory < 0 )
      {
        v45 = 455;
        goto LABEL_77;
      }
      v38 = v71[0] != 0;
LABEL_54:
      pvargSrc.lVal = v38;
      v37 = 3;
      goto LABEL_55;
    }
    if ( v77 == 2 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, double *))(*(_QWORD *)v74 + 72LL))(v74, v68);
      if ( ActivationFactory < 0 )
      {
        v45 = 465;
        goto LABEL_77;
      }
      v38 = (int)v68[0];
      goto LABEL_54;
    }
    if ( v77 != 3 )
    {
      ActivationFactory = -2147024809;
      v45 = 470;
      goto LABEL_77;
    }
    v34 = v74;
    v35 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v74 + 64LL);
    WindowsDeleteString(0);
    ActivationFactory = v35(v34, &v75);
    if ( ActivationFactory < 0 )
    {
      v45 = 460;
LABEL_77:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v45,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)S1);
      WindowsDeleteString(v75);
      v75 = 0;
      goto LABEL_81;
    }
    v36 = WindowsGetStringRawBuffer(v75, 0);
    pvargSrc.llVal = (LONGLONG)SysAllocString(v36);
    v37 = 8;
LABEL_55:
    pvargSrc.vt = v37;
    ActivationFactory = VariantCopy(&pvarg, &pvargSrc);
    if ( ActivationFactory < 0 )
    {
      v45 = 473;
      goto LABEL_77;
    }
    v39 = *((_QWORD *)&v81 + 1);
    if ( *((_QWORD *)&v81 + 1) == v82 )
    {
      std::vector<tagPolicyPublisherInformation>::_Emplace_reallocate<tagPolicyPublisherInformation const &>(
        &v81,
        *((_QWORD *)&v81 + 1),
        v90);
    }
    else
    {
      std::wstring::wstring(*((_QWORD *)&v81 + 1), v90);
      std::wstring::wstring(v39 + 32, S1);
      *(VARIANTARG *)(v39 + 64) = pvarg;
      *((_QWORD *)&v81 + 1) += 88LL;
    }
    VariantClear(&pvargSrc);
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v78 + 64LL))(v78, &v70);
    if ( ActivationFactory < 0 )
    {
      v45 = 477;
      goto LABEL_77;
    }
    WindowsDeleteString(v75);
    v75 = 0;
    if ( v74 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    std::wstring::~wstring(&hstringHeader);
    WindowsDeleteString(v76);
    v76 = 0;
    if ( v72 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    std::wstring::~wstring(S1);
    std::wstring::~wstring(v90);
    if ( !v70 )
      goto LABEL_65;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A9,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\ComApi\\UpdatePolicyApi.cpp",
    (const char *)(unsigned int)v19,
    (int)v61);
LABEL_91:
  if ( v72 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
  std::wstring::~wstring(S1);
  std::wstring::~wstring(v90);
LABEL_127:
  if ( v78 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
LABEL_129:
  if ( v83 )
    (*(void (__fastcall **)(__int64 *))(*v83 + 16))(v83);
LABEL_131:
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v87);
  std::vector<tagPolicyPublisherInformation>::~vector<tagPolicyPublisherInformation>(&v81);
  if ( v84 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
  if ( v85 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
  if ( v86 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000d590  mov     rax, rsp
0x18000d593  mov     [rax+8], rbx
0x18000d597  push    rbp
0x18000d598  push    rsi
0x18000d599  push    rdi
0x18000d59a  push    r12
0x18000d59c  push    r13
0x18000d59e  push    r14
0x18000d5a0  push    r15
0x18000d5a2  lea     rbp, [rax-168h]
0x18000d5a9  sub     rsp, 230h
0x18000d5b0  movaps  xmmword ptr [rax-48h], xmm6
0x18000d5b4  movaps  xmmword ptr [rax-58h], xmm7
0x18000d5b8  mov     rax, cs:__security_cookie
0x18000d5bf  xor     rax, rsp
0x18000d5c2  mov     [rbp+160h+var_60], rax
0x18000d5c9  mov     [rbp+160h+var_178], edx
0x18000d5cc  mov     [rbp+160h+var_1B0], r8
0x18000d5d0  xor     r13d, r13d
0x18000d5d3  mov     [rbp+160h+var_F8], r13
0x18000d5d7  mov     [rbp+160h+var_100], r13
0x18000d5db  mov     [rbp+160h+var_108], r13
0x18000d5df  xorps   xmm0, xmm0
0x18000d5e2  movdqu  [rbp+160h+var_128], xmm0
0x18000d5e7  mov     [rbp+160h+var_118], r13
0x18000d5eb  mov     [rbp+160h+var_E8], r13
0x18000d5ef  lea     ecx, [r13+40h]; Size
0x18000d5f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d5f8  mov     [rax], rax
0x18000d5fb  mov     [rax+8], rax
0x18000d5ff  mov     [rax+10h], rax
0x18000d603  lea     r15d, [r13+1]
0x18000d607  mov     word ptr [rax+18h], 101h
0x18000d60d  mov     [rbp+160h+var_F0], rax
0x18000d611  mov     [rbp+160h+string], r13
0x18000d615  lea     r9, [rbp+160h+string]; string
0x18000d619  lea     r8, [rbp+160h+hstringHeader]; hstringHeader
0x18000d61d  lea     edx, [r13+1Bh]; length
0x18000d621  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x18000d628  call    cs:__imp_WindowsCreateStringReference
0x18000d62e  test    eax, eax
0x18000d630  js      loc_18000E0CE
0x18000d636  lea     r8, [rbp+160h+var_F8]
0x18000d63a  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18000d641  mov     rcx, [rbp+160h+string]
0x18000d645  call    cs:__imp_RoGetActivationFactory
0x18000d64b  mov     ebx, eax
0x18000d64d  test    eax, eax
0x18000d64f  jns     short loc_18000D658
0x18000d651  mov     edx, 188h
0x18000d656  jmp     short loc_18000D6AF
0x18000d658  mov     rbx, [rbp+160h+var_F8]
0x18000d65c  mov     rax, [rbx]
0x18000d65f  mov     rdi, [rax+30h]
0x18000d663  lea     rdx, [rbp+160h+var_1B0]
0x18000d667  lea     rcx, [rbp+160h+hstringHeader]
0x18000d66b  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18000d670  lea     r8, [rbp+160h+var_100]
0x18000d674  mov     rdx, [rax+18h]
0x18000d678  mov     rcx, rbx
0x18000d67b  mov     rax, rdi
0x18000d67e  call    _guard_dispatch_icall
0x18000d683  mov     ebx, eax
0x18000d685  test    eax, eax
0x18000d687  jns     short loc_18000D690
0x18000d689  mov     edx, 189h
0x18000d68e  jmp     short loc_18000D6AF
0x18000d690  mov     rcx, [rbp+160h+var_100]
0x18000d694  mov     rax, [rcx]
0x18000d697  lea     rdx, [rbp+160h+var_108]
0x18000d69b  mov     rax, [rax+60h]
0x18000d69f  call    _guard_dispatch_icall
0x18000d6a4  mov     ebx, eax
0x18000d6a6  test    eax, eax
0x18000d6a8  jns     short loc_18000D6CA
0x18000d6aa  mov     edx, 18Ah; void *
0x18000d6af  mov     rcx, [rbp+168h]; this
0x18000d6b6  mov     r9d, ebx; char *
0x18000d6b9  lea     r8, aCW1SSrcClientP_7; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18000d6c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d6c5  jmp     loc_18000E043
0x18000d6ca  mov     [rbp+160h+var_110], r13
0x18000d6ce  mov     rcx, [rbp+160h+var_108]
0x18000d6d2  mov     rax, [rcx]
0x18000d6d5  lea     r8, [rbp+160h+var_110]
0x18000d6d9  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x18000d6e0  mov     rax, [rax]
0x18000d6e3  call    _guard_dispatch_icall
0x18000d6e8  mov     ebx, eax
0x18000d6ea  test    eax, eax
0x18000d6ec  jns     short loc_18000D70E
0x18000d6ee  mov     rcx, [rbp+168h]; this
0x18000d6f5  mov     r9d, eax; char *
0x18000d6f8  lea     r8, aCW1SSrcClientP_7; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18000d6ff  mov     edx, 18Dh; void *
0x18000d704  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d709  jmp     loc_18000E02D
0x18000d70e  mov     rcx, [rbp+160h+var_110]
0x18000d712  mov     rax, [rcx]
0x18000d715  mov     [rbp+160h+var_150], r13
0x18000d719  lea     rdx, [rbp+160h+var_150]
0x18000d71d  mov     rax, [rax+30h]
0x18000d721  call    _guard_dispatch_icall
0x18000d726  mov     ebx, eax
0x18000d728  test    eax, eax
0x18000d72a  jns     short loc_18000D736
0x18000d72c  mov     edx, 190h
0x18000d731  jmp     loc_18000E000
0x18000d736  mov     [rbp+160h+var_188], r13b
0x18000d73a  mov     rcx, [rbp+160h+var_150]
0x18000d73e  mov     rax, [rcx]
0x18000d741  lea     rdx, [rbp+160h+var_188]
0x18000d745  mov     rax, [rax+38h]
0x18000d749  call    _guard_dispatch_icall
0x18000d74e  mov     ebx, eax
0x18000d750  test    eax, eax
0x18000d752  jns     short loc_18000D75E
0x18000d754  mov     edx, 193h
0x18000d759  jmp     loc_18000E000
0x18000d75e  mov     rbx, r15
0x18000d761  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000d765  cmp     ebx, 55h ; 'U'
0x18000d768  ja      loc_18000DFF6
0x18000d76e  movsxd  rax, ebx
0x18000d771  imul    rcx, rax, 78h ; 'x'
0x18000d775  lea     rdx, off_18004B4F0; "None"
0x18000d77c  mov     rdx, [rcx+rdx]
0x18000d780  test    rdx, rdx
0x18000d783  jz      short loc_18000D7C4
0x18000d785  xorps   xmm0, xmm0
0x18000d788  movups  xmmword ptr [rbp+160h+hstringHeader.Reserved], xmm0
0x18000d78c  xorps   xmm1, xmm1
0x18000d78f  movdqu  xmmword ptr [rbp+160h+hstringHeader.Reserved+10h], xmm1
0x18000d794  mov     r8, r12
0x18000d797  inc     r8
0x18000d79a  cmp     [rdx+r8*2], r13w
0x18000d79f  jnz     short loc_18000D797
0x18000d7a1  lea     rcx, [rbp+160h+hstringHeader]
0x18000d7a5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d7aa  lea     r8, [rbp+160h+hstringHeader]
0x18000d7ae  lea     rdx, [rbp+160h+var_1B0]
0x18000d7b2  lea     rcx, [rbp+160h+var_F0]
0x18000d7b6  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18000d7bb  lea     rcx, [rbp+160h+hstringHeader]; void *
0x18000d7bf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d7c4  add     rbx, r15
0x18000d7c7  cmp     rbx, 55h ; 'U'
0x18000d7cb  jbe     short loc_18000D765
0x18000d7cd  mov     r14d, 7
0x18000d7d3  cmp     [rbp+160h+var_188], r13b
0x18000d7d7  jz      loc_18000DBE3
0x18000d7dd  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x18000d7e5  xorps   xmm6, xmm6
0x18000d7e8  xorps   xmm0, xmm0
0x18000d7eb  movups  [rbp+160h+var_C0], xmm0
0x18000d7f2  movdqa  [rbp+160h+var_B0], xmm7
0x18000d7fa  mov     word ptr [rbp+160h+var_C0], r13w
0x18000d802  movups  xmmword ptr [rbp+160h+S1], xmm0
0x18000d809  mov     [rbp+160h+var_90], r13
0x18000d810  mov     [rbp+160h+var_88], r14
0x18000d817  mov     word ptr [rbp+160h+S1], r13w
0x18000d81f  xor     eax, eax
0x18000d821  movups  xmmword ptr [rbp+160h+pvarg], xmm0
0x18000d828  mov     qword ptr [rbp+160h+pvarg+10h], rax
0x18000d82f  lea     rcx, [rbp+160h+pvarg]; pvarg
0x18000d836  call    cs:__imp_VariantInit
0x18000d83c  mov     [rbp+160h+var_180], r13
0x18000d840  mov     rcx, [rbp+160h+var_150]
0x18000d844  mov     rax, [rcx]
0x18000d847  lea     rdx, [rbp+160h+var_180]
0x18000d84b  mov     rax, [rax+30h]
0x18000d84f  call    _guard_dispatch_icall
0x18000d854  mov     ebx, eax
0x18000d856  test    eax, eax
0x18000d858  js      loc_18000DD43
0x18000d85e  mov     rbx, [rbp+160h+var_180]
0x18000d862  mov     rax, [rbx]
0x18000d865  mov     rdi, [rax+30h]
0x18000d869  xor     ecx, ecx; string
0x18000d86b  call    cs:__imp_WindowsDeleteString
0x18000d871  mov     [rbp+160h+var_160], r13
0x18000d875  lea     rdx, [rbp+160h+var_160]
0x18000d879  mov     rcx, rbx
0x18000d87c  mov     rax, rdi
0x18000d87f  call    _guard_dispatch_icall
0x18000d884  mov     ebx, eax
0x18000d886  test    eax, eax
0x18000d888  js      loc_18000DD18
0x18000d88e  xor     edx, edx; length
0x18000d890  mov     rcx, [rbp+160h+var_160]; string
0x18000d894  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d89a  xorps   xmm0, xmm0
0x18000d89d  movups  xmmword ptr [rbp+160h+hstringHeader.Reserved], xmm0
0x18000d8a1  xorps   xmm1, xmm1
0x18000d8a4  movdqu  xmmword ptr [rbp+160h+hstringHeader.Reserved+10h], xmm1
0x18000d8a9  mov     r8, r12
0x18000d8ac  inc     r8
0x18000d8af  cmp     [rax+r8*2], r13w
0x18000d8b4  jnz     short loc_18000D8AC
0x18000d8b6  mov     rdx, rax
0x18000d8b9  lea     rcx, [rbp+160h+hstringHeader]
0x18000d8bd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d8c2  xorps   xmm0, xmm0
0x18000d8c5  movups  xmmword ptr [rsp+260h+var_1F8+8], xmm0
0x18000d8ca  xorps   xmm1, xmm1
0x18000d8cd  movdqu  [rbp+160h+var_1E0], xmm1
0x18000d8d2  mov     r8, r15
0x18000d8d5  lea     rdx, asc_18003C64C; "/"
0x18000d8dc  lea     rcx, [rsp+260h+var_1F8+8]
0x18000d8e1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000d8e6  lea     rdx, [rbp+160h+hstringHeader]
0x18000d8ea  lea     rcx, [rbp+160h+var_1D0]
0x18000d8ee  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d8f3  lea     rcx, [rbp+160h+S1]
0x18000d8fa  mov     qword ptr [rsp+260h+var_240], rcx; int
0x18000d8ff  lea     r9, [rbp+160h+var_C0]
0x18000d906  lea     r8, [rsp+260h+var_1F8+8]
0x18000d90b  mov     rdx, rax
0x18000d90e  call    ?GetPolicyNodeAndName@CUpdatePolicyPublisher@@AEAAJV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@1@Z; CUpdatePolicyPublisher::GetPolicyNodeAndName(std::wstring,std::wstring,std::wstring &,std::wstring &)
0x18000d913  mov     ebx, eax
0x18000d915  test    eax, eax
0x18000d917  js      loc_18000DCF2
0x18000d91d  lea     r8, [rbp+160h+S1]
0x18000d924  lea     rdx, [rsp+260h+var_1F8+8]
0x18000d929  lea     rcx, [rbp+160h+var_F0]
0x18000d92d  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000d932  mov     rbx, qword ptr [rbp+160h+var_1E0]
0x18000d936  cmp     [rbx+19h], r13b
0x18000d93a  jnz     short loc_18000D99A
0x18000d93c  mov     rdi, [rbx+30h]
0x18000d940  lea     rdx, [rbx+20h]
0x18000d944  cmp     [rbx+38h], r14
0x18000d948  jbe     short loc_18000D94D
0x18000d94a  mov     rdx, [rdx]; S2
0x18000d94d  lea     rcx, [rbp+160h+S1]
0x18000d954  cmp     [rbp+160h+var_88], r14
0x18000d95b  cmova   rcx, [rbp+160h+S1]; S1
0x18000d963  mov     rsi, [rbp+160h+var_90]
0x18000d96a  mov     r8, rsi
0x18000d96d  cmp     rdi, rsi
0x18000d970  cmovb   r8, rdi; N
0x18000d974  call    wmemcmp
0x18000d979  test    eax, eax
0x18000d97b  jnz     short loc_18000D98D
0x18000d97d  cmp     rsi, rdi
0x18000d980  jnb     short loc_18000D987
0x18000d982  mov     eax, r12d
0x18000d985  jmp     short loc_18000D98D
0x18000d987  mov     eax, r13d
0x18000d98a  setnbe  al
0x18000d98d  shr     eax, 1Fh
0x18000d990  test    al, al
0x18000d992  jnz     short loc_18000D99A
0x18000d994  mov     rax, [rbp+160h+var_F0]
0x18000d998  jmp     short loc_18000D9A1
0x18000d99a  mov     rax, [rbp+160h+var_F0]
0x18000d99e  mov     rbx, rax
0x18000d9a1  cmp     rbx, rax
0x18000d9a4  jz      loc_18000DCE6
0x18000d9aa  xorps   xmm0, xmm0
0x18000d9ad  xor     eax, eax
0x18000d9af  movups  xmmword ptr [rbp+160h+pvargSrc], xmm0
0x18000d9b3  mov     qword ptr [rbp+160h+pvargSrc+10h], rax
0x18000d9b7  lea     rcx, [rbp+160h+pvargSrc]; pvarg
0x18000d9bb  call    cs:__imp_VariantInit
0x18000d9c1  mov     [rbp+160h+var_170], r13
0x18000d9c5  mov     rcx, [rbp+160h+var_180]
0x18000d9c9  mov     rax, [rcx]
0x18000d9cc  lea     rdx, [rbp+160h+var_170]
0x18000d9d0  mov     rax, [rax+38h]
0x18000d9d4  call    _guard_dispatch_icall
0x18000d9d9  mov     ebx, eax
0x18000d9db  test    eax, eax
0x18000d9dd  js      loc_18000DCB2
0x18000d9e3  mov     [rbp+160h+var_158], r13d
0x18000d9e7  mov     rcx, [rbp+160h+var_170]
0x18000d9eb  mov     rax, [rcx]
0x18000d9ee  lea     rdx, [rbp+160h+var_158]
0x18000d9f2  mov     rax, [rax+30h]
0x18000d9f6  call    _guard_dispatch_icall
0x18000d9fb  mov     ebx, eax
0x18000d9fd  test    eax, eax
0x18000d9ff  js      loc_18000DCAB
0x18000da05  mov     [rbp+160h+var_187], r13b
0x18000da09  mov     [rbp+160h+var_168], r13
0x18000da0d  movsd   [rbp+160h+var_1B0], xmm6
0x18000da12  mov     ecx, [rbp+160h+var_158]
0x18000da15  sub     ecx, 1
0x18000da18  jz      loc_18000DA9E
0x18000da1e  sub     ecx, 1
0x18000da21  jz      short loc_18000DA78
0x18000da23  cmp     ecx, 1
0x18000da26  jnz     loc_18000DC5F
0x18000da2c  mov     rbx, [rbp+160h+var_170]
0x18000da30  mov     rax, [rbx]
0x18000da33  mov     rdi, [rax+40h]
0x18000da37  xor     ecx, ecx; string
0x18000da39  call    cs:__imp_WindowsDeleteString
0x18000da3f  lea     rdx, [rbp+160h+var_168]
0x18000da43  mov     rcx, rbx
  ... truncated ...
```
