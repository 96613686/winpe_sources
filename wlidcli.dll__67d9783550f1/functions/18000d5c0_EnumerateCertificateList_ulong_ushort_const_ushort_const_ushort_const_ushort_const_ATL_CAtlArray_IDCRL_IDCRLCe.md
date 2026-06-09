# EnumerateCertificateList(ulong,ushort const *,ushort const *,ushort const *,ushort const *,ATL::CAtlArray<IDCRL::_IDCRLCertInfo,ATL::CElementTraits<IDCRL::_IDCRLCertInfo>> &)

- ea: `0x18000d5c0`
- end: `0x18000ddc7`
- name: `?EnumerateCertificateList@@YAJKPEBG000AEAV?$CAtlArray@U_IDCRLCertInfo@IDCRL@@V?$CElementTraits@U_IDCRLCertInfo@IDCRL@@@ATL@@@ATL@@@Z`
- size: `2055`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x18002adb0`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x18000a870`
- `0x18000a914`
- `0x18000af40`
- `0x18000ba8c`
- `0x18000bdf0`
- `0x18000be18`
- `0x18000cb6c`
- `0x18000cc48`
- `0x18000cc9c`
- `0x18000cd80`
- `0x18000cdd8`
- `0x18000ce04`
- `0x18000cfdc`
- `0x18000d094`
- `0x18000d194`
- `0x18000d554`
- `0x18000d5c0`
- `0x18000e784`
- `0x18000ecc4`
- `0x18000edec`
- `0x1800530e4`
- `0x180054b78`
- `0x180054f6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000d6d9`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000d6eb`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000d6d9`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000d6eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da1c`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000da9e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000dbca`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000da9e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000dbca`
- `CRYPT32!CertOpenStore` at `0x18000d9f9`
- `CRYPT32!CertOpenStore` at `0x18000d9f9`

## string_xrefs

- `0x18000d6ad`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000d70d`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000d99d`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000da43`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000db1c`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000dd86`: `clientcore\ds\ext\live\identity\api\classic\certtokenwlidcli.cpp`
- `0x18000da36`: `CertOpenStore failed with hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall EnumerateCertificateList(int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  int v9; // ebx
  int v10; // eax
  __int64 v11; // rdx
  volatile signed __int32 *v12; // rcx
  int *v13; // rbx
  volatile signed __int32 *v14; // rdi
  __int64 v15; // rdx
  volatile signed __int32 *v16; // rcx
  int *v17; // rbx
  volatile signed __int32 *v18; // rdi
  _QWORD *CurrentUserKey; // rax
  _WORD *v20; // rbx
  bool v21; // di
  char v22; // r15
  HCERTSTORE v23; // rax
  signed int LastError; // eax
  const CERT_CONTEXT *v25; // rax
  char v26; // r12
  const CERT_CONTEXT *v27; // rsi
  int v28; // eax
  unsigned __int64 v29; // r14
  unsigned __int64 i; // rdi
  __int64 v31; // rax
  char *v32; // r8
  int v33; // ecx
  int v34; // edx
  unsigned int v35; // ebx
  _QWORD *v37; // rax
  __int64 v38; // rdx
  _QWORD *v39; // rax
  __int64 v40; // rdx
  void *pvPara; // [rsp+20h] [rbp-298h]
  void *pvParaa; // [rsp+20h] [rbp-298h]
  int pCertContext; // [rsp+28h] [rbp-290h]
  int v44; // [rsp+30h] [rbp-288h]
  int v45; // [rsp+50h] [rbp-268h] BYREF
  int v46; // [rsp+54h] [rbp-264h] BYREF
  volatile signed __int32 *v47; // [rsp+58h] [rbp-260h] BYREF
  char v48[8]; // [rsp+60h] [rbp-258h]
  _QWORD v49[2]; // [rsp+68h] [rbp-250h] BYREF
  __int64 v50; // [rsp+78h] [rbp-240h] BYREF
  int v51; // [rsp+80h] [rbp-238h] BYREF
  _WORD *v52; // [rsp+88h] [rbp-230h] BYREF
  __int64 v53; // [rsp+90h] [rbp-228h] BYREF
  void **v54; // [rsp+98h] [rbp-220h] BYREF
  HCERTSTORE hCertStore; // [rsp+A0h] [rbp-218h]
  int v56; // [rsp+A8h] [rbp-210h]
  int v57; // [rsp+B0h] [rbp-208h] BYREF
  _QWORD v58[3]; // [rsp+B8h] [rbp-200h] BYREF
  int v59; // [rsp+D0h] [rbp-1E8h]
  _QWORD v60[3]; // [rsp+D8h] [rbp-1E0h] BYREF
  int v61; // [rsp+F0h] [rbp-1C8h]
  char *v62[4]; // [rsp+F8h] [rbp-1C0h] BYREF
  _QWORD v63[3]; // [rsp+118h] [rbp-1A0h] BYREF
  const wil::ResultException *v64; // [rsp+130h] [rbp-188h] BYREF
  ATL::CAtlException *v65; // [rsp+138h] [rbp-180h] BYREF
  CPassportException *v66; // [rsp+140h] [rbp-178h] BYREF
  _BYTE v67[24]; // [rsp+148h] [rbp-170h] BYREF
  unsigned __int16 v68[136]; // [rsp+160h] [rbp-158h] BYREF

  v46 = 0;
  v45 = 0;
  memset(v60, 0, sizeof(v60));
  v61 = 0;
  memset(v58, 0, sizeof(v58));
  v59 = 0;
  hCertStore = 0;
  v54 = &SmartHCERTSTORE::`vftable';
  v56 = 1;
  memset_0(v68, 0, 0x108u);
  v44 = a1;
  CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
    v62,
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
    0x16Eu,
    (char *)&v45,
    "EnumerateCertificateList",
    L"dwFlags=0x%x, CSPs=%s, Thumbprints=%s");
  if ( a4 && a5 )
  {
    v9 = _o__wtol(a4);
    v48[0] = v9 != 0;
    v10 = _o__wtol(a5);
    v48[1] = v10 != 0;
    if ( v9 && v10 )
    {
      TracePrintW(
        3u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
        0x184u,
        L"fDisableEID && fDisableSSC");
      v45 = 0;
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v62);
    }
    else
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v47);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v52);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v50);
      try
      {
        v46 = 0;
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v52);
        v11 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                           &v52,
                           v49,
                           L"|",
                           &v46);
        v12 = (volatile signed __int32 *)(v11 - 24);
        v13 = (int *)(v47 - 6);
        if ( (volatile signed __int32 *)(v11 - 24) != v47 - 6 )
        {
          if ( v13[4] < 0 || *(_QWORD *)v12 != *(_QWORD *)v13 )
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v47, v11, *(unsigned int *)(v11 - 16));
            goto LABEL_12;
          }
LABEL_10:
          v14 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v12);
          ATL::CStringData::Release((ATL::CStringData *)v13);
          v47 = v14 + 6;
        }
LABEL_12:
        while ( 1 )
        {
          ATL::CStringData::Release((ATL::CStringData *)(v49[0] - 24LL));
          if ( !*((_DWORD *)v47 - 4) )
            break;
          v39 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&v47);
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
            v60,
            *v39);
          v40 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                             &v52,
                             v49,
                             L"|",
                             &v46);
          v12 = (volatile signed __int32 *)(v40 - 24);
          v13 = (int *)(v47 - 6);
          if ( (volatile signed __int32 *)(v40 - 24) != v47 - 6 )
          {
            if ( v13[4] >= 0 && *(_QWORD *)v12 == *(_QWORD *)v13 )
              goto LABEL_10;
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v47, v40, *(unsigned int *)(v40 - 16));
          }
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v50);
        v46 = 0;
        v15 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                           &v50,
                           v49,
                           L"|",
                           &v46);
        v16 = (volatile signed __int32 *)(v15 - 24);
        v17 = (int *)(v47 - 6);
        if ( (volatile signed __int32 *)(v15 - 24) == v47 - 6 )
          goto LABEL_18;
        if ( v17[4] >= 0 && *(_QWORD *)v16 == *(_QWORD *)v17 )
        {
LABEL_16:
          v18 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v16);
          ATL::CStringData::Release((ATL::CStringData *)v17);
          v47 = v18 + 6;
          goto LABEL_18;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v47, v15, *(unsigned int *)(v15 - 16));
LABEL_18:
        while ( 1 )
        {
          ATL::CStringData::Release((ATL::CStringData *)(v49[0] - 24LL));
          if ( !*((_DWORD *)v47 - 4) )
            break;
          v37 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&v47);
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
            v58,
            *v37);
          v38 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                             &v50,
                             v49,
                             L"|",
                             &v46);
          v16 = (volatile signed __int32 *)(v38 - 24);
          v17 = (int *)(v47 - 6);
          if ( (volatile signed __int32 *)(v38 - 24) != v47 - 6 )
          {
            if ( v17[4] >= 0 && *(_QWORD *)v16 == *(_QWORD *)v17 )
              goto LABEL_16;
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v47, v38, *(unsigned int *)(v38 - 16));
          }
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)v49,
          (__int64)L"BypassCSP");
        v46 = 1;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v53,
          (__int64)L"Software\\Microsoft\\IdentityCRL\\Certificate");
        v46 = 3;
        CurrentUserKey = (_QWORD *)GetCurrentUserKey(v67);
        v46 = 7;
        v51 = 0;
        v63[0] = &ExecutionContext::`vftable';
        v63[1] = &ComFunctions::`vftable';
        v63[2] = &StringSrvPassthrough::`vftable';
        RegQueryDWORD(
          (unsigned int)v63,
          *CurrentUserKey,
          (unsigned int)&v53,
          (unsigned int)v49,
          (__int64)&v51,
          pCertContext);
        v20 = v52;
        v21 = v51 || *v52 == 42 && !v52[1];
        ATL::CRegKey::Close((ATL::CRegKey *)v67);
        ATL::CStringData::Release((ATL::CStringData *)(v53 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v49[0] - 24LL));
        if ( v21 )
        {
          v22 = 1;
          TracePrintW(
            3u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
            0x1A5u,
            L"Bypass CSP certificate enumerate filter.");
        }
        else
        {
          v22 = 0;
          TracePrintW(
            3u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
            0x1AAu,
            L"Use CSP certificate enumerate filter '%s'. ",
            a2);
        }
        v23 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x1C000u, L"MY");
        SmartPtr<void *>::Attach(&v54, v23);
        if ( hCertStore )
        {
          v49[0] = &SmartPCCERT_CONTEXT::`vftable';
          v25 = CertEnumCertificatesInStore(hCertStore, 0);
          v26 = v48[0];
          while ( 1 )
          {
            v49[1] = v25;
            v27 = v25;
            if ( !v25 )
              break;
            v28 = ValidateCertificate((__int64)v60, (__int64)v58, v22, v26, v48[1], v25, v44, v68);
            v45 = v28;
            if ( v28 == -2146435028 )
            {
              v45 = 0;
            }
            else
            {
              if ( v28 < 0 )
              {
                LODWORD(pvParaa) = v28;
                TracePrintW(
                  3u,
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
                  0x1CAu,
                  L"ValidateCertificate failed with hr=0x%x",
                  pvParaa);
                SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)v49);
                ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
                ATL::CStringData::Release((ATL::CStringData *)(v20 - 12));
                ATL::CStringData::Release((ATL::CStringData *)(v47 - 6));
                CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v62);
                goto LABEL_73;
              }
              v29 = *(_QWORD *)(a6 + 8);
              for ( i = 0; i < v29; ++i )
              {
                v31 = ATL::CAtlArray<IDCRL::_IDCRLCertInfo,ATL::CElementTraits<IDCRL::_IDCRLCertInfo>>::operator[](
                        a6,
                        i);
                v32 = (char *)v68 - v31;
                do
                {
                  v33 = *(unsigned __int16 *)&v32[v31];
                  v34 = *(unsigned __int16 *)v31 - v33;
                  if ( v34 )
                    break;
                  v31 += 2;
                }
                while ( v33 );
                if ( !v34 )
                  goto LABEL_45;
              }
              ATL::CAtlArray<IDCRL::_IDCRLCertInfo,ATL::CElementTraits<IDCRL::_IDCRLCertInfo>>::Add(a6, v68);
            }
LABEL_45:
            v25 = CertEnumCertificatesInStore(hCertStore, v27);
          }
          SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)v49);
          ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v20 - 12));
          ATL::CStringData::Release((ATL::CStringData *)(v47 - 6));
          CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v62);
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v45 = LastError;
          LODWORD(pvPara) = LastError;
          TracePrintW(
            3u,
            "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
            0x1B8u,
            L"CertOpenStore failed with hr=0x%x",
            pvPara);
          ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v20 - 12));
          ATL::CStringData::Release((ATL::CStringData *)(v47 - 6));
          CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v62);
        }
      }
      catch ( CPassportException *v66 )
      {
        v45 = *((_DWORD *)v66 + 2);
        if ( v45 >= 0 )
          v45 = -2147418113;
        goto LABEL_47;
      }
      catch ( ATL::CAtlException *v65 )
      {
        v45 = *(_DWORD *)v65;
        if ( v45 >= 0 )
          v45 = -2147418113;
        goto LABEL_47;
      }
      catch ( std::bad_alloc )
      {
        v45 = -2147024882;
        goto LABEL_47;
      }
      catch ( long v57 )
      {
        v45 = v57;
        if ( v57 >= 0 )
          v45 = -2147418113;
        goto LABEL_47;
      }
      catch ( const wil::ResultException *v64 )
      {
        v45 = *((_DWORD *)v64 + 8);
        if ( v45 >= 0 )
          v45 = -2147418113;
        goto LABEL_47;
      }
LABEL_73:
      ;
    }
  }
  else
  {
    TracePrintW(
      3u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\certtokenwlidcli.cpp",
      0x179u,
      L"Invalid parameter");
    v45 = -2147024809;
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v62);
  }
LABEL_47:
  v35 = v45;
  SmartHCERTSTORE::~SmartHCERTSTORE((SmartHCERTSTORE *)&v54);
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(v58);
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>(v60);
  return v35;
}

```

## disassembly

```asm
0x18000d5c0  mov     r11, rsp
0x18000d5c3  push    rbx
0x18000d5c4  push    rsi
0x18000d5c5  push    rdi
0x18000d5c6  push    r12
0x18000d5c8  push    r13
0x18000d5ca  push    r14
0x18000d5cc  push    r15
0x18000d5ce  sub     rsp, 280h
0x18000d5d5  mov     rax, cs:__security_cookie
0x18000d5dc  xor     rax, rsp
0x18000d5df  mov     [rsp+2B8h+var_48], rax
0x18000d5e7  mov     rbx, r9
0x18000d5ea  mov     r15, r8
0x18000d5ed  mov     r12, rdx
0x18000d5f0  mov     esi, ecx
0x18000d5f2  mov     rdi, [rsp+2B8h+arg_20]
0x18000d5fa  mov     r13, [rsp+2B8h+arg_28]
0x18000d602  xor     ecx, ecx
0x18000d604  mov     r14d, ecx
0x18000d607  mov     [rsp+2B8h+var_264], ecx
0x18000d60b  mov     [rsp+2B8h+var_268], ecx
0x18000d60f  mov     [r11-1E0h], rcx
0x18000d616  mov     [r11-1D8h], rcx
0x18000d61d  mov     [r11-1D0h], rcx
0x18000d624  mov     [rsp+2B8h+var_1C8], ecx
0x18000d62b  mov     [r11-200h], rcx
0x18000d632  mov     [r11-1F8h], rcx
0x18000d639  mov     [r11-1F0h], rcx
0x18000d640  mov     [rsp+2B8h+var_1E8], ecx
0x18000d647  mov     [r11-218h], rcx
0x18000d64e  lea     rax, ??_7SmartHCERTSTORE@@6B@; const SmartHCERTSTORE::`vftable'
0x18000d655  mov     [r11-220h], rax
0x18000d65c  mov     [rsp+2B8h+var_210], 1
0x18000d667  xor     edx, edx; Val
0x18000d669  mov     r8d, 108h; Size
0x18000d66f  lea     rcx, [r11-158h]; void *
0x18000d676  call    memset_0
0x18000d67b  nop
0x18000d67c  mov     [rsp+2B8h+var_278], r15
0x18000d681  mov     [rsp+2B8h+var_280], r12
0x18000d686  mov     [rsp+2B8h+var_288], esi; int
0x18000d68a  lea     rax, aDwflags0xXCsps_0; "dwFlags=0x%x, CSPs=%s, Thumbprints=%s"
0x18000d691  mov     [rsp+2B8h+pCertContext], rax
0x18000d696  lea     rax, aEnumeratecerti_0; "EnumerateCertificateList"
0x18000d69d  mov     [rsp+2B8h+pvPara], rax
0x18000d6a2  lea     r9, [rsp+2B8h+var_268]
0x18000d6a7  mov     r8d, 16Eh
0x18000d6ad  lea     rdx, aClientcoreDsEx_16; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18000d6b4  lea     rcx, [rsp+2B8h+var_1C0]
0x18000d6bc  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x18000d6c1  nop
0x18000d6c2  xor     esi, esi
0x18000d6c4  test    rbx, rbx
0x18000d6c7  jz      loc_18000DD79
0x18000d6cd  test    rdi, rdi
0x18000d6d0  jz      loc_18000DD79
0x18000d6d6  mov     rcx, rbx
0x18000d6d9  call    cs:__imp__o__wtol
0x18000d6df  mov     ebx, eax
0x18000d6e1  test    eax, eax
0x18000d6e3  setnz   [rsp+2B8h+var_258]
0x18000d6e8  mov     rcx, rdi
0x18000d6eb  call    cs:__imp__o__wtol
0x18000d6f1  test    eax, eax
0x18000d6f3  setnz   [rsp+2B8h+var_258+1]
0x18000d6f8  test    ebx, ebx
0x18000d6fa  jz      short loc_18000D733
0x18000d6fc  test    eax, eax
0x18000d6fe  jz      short loc_18000D733
0x18000d700  lea     r9, aFdisableeidFdi; "fDisableEID && fDisableSSC"
0x18000d707  mov     r8d, 184h; unsigned int
0x18000d70d  lea     rdx, aClientcoreDsEx_16; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18000d714  lea     ecx, [rsi+3]; unsigned __int8
0x18000d717  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d71c  mov     [rsp+2B8h+var_268], esi
0x18000d720  lea     rcx, [rsp+2B8h+var_1C0]
0x18000d728  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000d72d  nop
0x18000d72e  jmp     loc_18000DC16
0x18000d733  lea     rcx, [rsp+2B8h+var_260]
0x18000d738  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d73d  nop
0x18000d73e  lea     rcx, [rsp+2B8h+var_230]
0x18000d746  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d74b  nop
0x18000d74c  lea     rcx, [rsp+2B8h+var_240]
0x18000d751  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d756  nop
0x18000d757  mov     [rsp+2B8h+var_264], esi
0x18000d75b  mov     rdx, r12
0x18000d75e  lea     rcx, [rsp+2B8h+var_230]
0x18000d766  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18000d76b  lea     r9, [rsp+2B8h+var_264]
0x18000d770  lea     r8, asc_18006E2D8; "|"
0x18000d777  lea     rdx, [rsp+2B8h+var_250]
0x18000d77c  lea     rcx, [rsp+2B8h+var_230]
0x18000d784  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x18000d789  nop
0x18000d78a  mov     rdx, [rax]
0x18000d78d  lea     rcx, [rdx-18h]
0x18000d791  mov     rbx, [rsp+2B8h+var_260]
0x18000d796  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18000d79a  cmp     rcx, rbx
0x18000d79d  jz      short loc_18000D7D6
0x18000d79f  cmp     [rbx+10h], esi
0x18000d7a2  jl      short loc_18000D7C7
0x18000d7a4  mov     rax, [rbx]
0x18000d7a7  cmp     [rcx], rax
0x18000d7aa  jnz     short loc_18000D7C7
0x18000d7ac  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000d7b1  mov     rdi, rax
0x18000d7b4  mov     rcx, rbx; this
0x18000d7b7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000d7bc  lea     rax, [rdi+18h]
0x18000d7c0  mov     [rsp+2B8h+var_260], rax
0x18000d7c5  jmp     short loc_18000D7D6
0x18000d7c7  mov     r8d, [rdx-10h]
0x18000d7cb  lea     rcx, [rsp+2B8h+var_260]
0x18000d7d0  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000d7d5  nop
0x18000d7d6  mov     rcx, [rsp+2B8h+var_250]
0x18000d7db  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000d7df  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000d7e4  mov     rax, [rsp+2B8h+var_260]
0x18000d7e9  cmp     [rax-10h], esi
0x18000d7ec  jnz     loc_18000DCEF
0x18000d7f2  mov     rdx, r15
0x18000d7f5  lea     rcx, [rsp+2B8h+var_240]
0x18000d7fa  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18000d7ff  mov     [rsp+2B8h+var_264], esi
0x18000d803  lea     r9, [rsp+2B8h+var_264]
0x18000d808  lea     r8, asc_18006E2D8; "|"
0x18000d80f  lea     rdx, [rsp+2B8h+var_250]
0x18000d814  lea     rcx, [rsp+2B8h+var_240]
0x18000d819  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x18000d81e  nop
0x18000d81f  mov     rdx, [rax]
0x18000d822  lea     rcx, [rdx-18h]
0x18000d826  mov     rbx, [rsp+2B8h+var_260]
0x18000d82b  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18000d82f  cmp     rcx, rbx
0x18000d832  jz      short loc_18000D86B
0x18000d834  cmp     [rbx+10h], esi
0x18000d837  jl      short loc_18000D85C
0x18000d839  mov     rax, [rbx]
0x18000d83c  cmp     [rcx], rax
0x18000d83f  jnz     short loc_18000D85C
0x18000d841  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000d846  mov     rdi, rax
0x18000d849  mov     rcx, rbx; this
0x18000d84c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000d851  lea     rax, [rdi+18h]
0x18000d855  mov     [rsp+2B8h+var_260], rax
0x18000d85a  jmp     short loc_18000D86B
0x18000d85c  mov     r8d, [rdx-10h]
0x18000d860  lea     rcx, [rsp+2B8h+var_260]
0x18000d865  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000d86a  nop
0x18000d86b  mov     rcx, [rsp+2B8h+var_250]
0x18000d870  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000d874  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000d879  mov     rax, [rsp+2B8h+var_260]
0x18000d87e  cmp     [rax-10h], esi
0x18000d881  jnz     loc_18000DC68
0x18000d887  lea     rdx, aBypasscsp; "BypassCSP"
0x18000d88e  lea     rcx, [rsp+2B8h+var_250]
0x18000d893  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000d898  nop
0x18000d899  or      r14d, 1
0x18000d89d  mov     [rsp+2B8h+var_264], r14d
0x18000d8a2  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\IdentityCRL\\Certi"...
0x18000d8a9  lea     rcx, [rsp+2B8h+var_228]
0x18000d8b1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000d8b6  nop
0x18000d8b7  or      r14d, 2
0x18000d8bb  mov     [rsp+2B8h+var_264], r14d
0x18000d8c0  lea     rcx, [rsp+2B8h+var_170]
0x18000d8c8  call    ?GetCurrentUserKey@@YA?AVCRegKey@ATL@@XZ; GetCurrentUserKey(void)
0x18000d8cd  nop
0x18000d8ce  or      r14d, 4
0x18000d8d2  mov     [rsp+2B8h+var_264], r14d
0x18000d8d7  mov     [rsp+2B8h+var_238], esi
0x18000d8de  lea     rcx, ??_7ExecutionContext@@6B@; const ExecutionContext::`vftable'
0x18000d8e5  mov     [rsp+2B8h+var_1A0], rcx
0x18000d8ed  lea     rcx, ??_7ComFunctions@@6B@; const ComFunctions::`vftable'
0x18000d8f4  mov     [rsp+2B8h+var_198], rcx
0x18000d8fc  lea     rcx, ??_7StringSrvPassthrough@@6B@; const StringSrvPassthrough::`vftable'
0x18000d903  mov     [rsp+2B8h+var_190], rcx
0x18000d90b  lea     rcx, [rsp+2B8h+var_238]
0x18000d913  mov     [rsp+2B8h+pvPara], rcx
0x18000d918  lea     r9, [rsp+2B8h+var_250]
0x18000d91d  lea     r8, [rsp+2B8h+var_228]
0x18000d925  mov     rdx, [rax]
0x18000d928  lea     rcx, [rsp+2B8h+var_1A0]
0x18000d930  call    ?RegQueryDWORD@@YAJPEAVIExecutionContext@@PEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@2PEAKH@Z; RegQueryDWORD(IExecutionContext *,HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong *,int)
0x18000d935  nop
0x18000d936  mov     rbx, [rsp+2B8h+var_230]
0x18000d93e  cmp     [rsp+2B8h+var_238], esi
0x18000d945  ja      short loc_18000D958
0x18000d947  cmp     word ptr [rbx], 2Ah ; '*'
0x18000d94b  jnz     short loc_18000D953
0x18000d94d  cmp     [rbx+2], si
0x18000d951  jz      short loc_18000D958
0x18000d953  mov     dil, sil
0x18000d956  jmp     short loc_18000D95B
0x18000d958  mov     dil, 1
0x18000d95b  and     r14d, 0FFFFFFFBh
0x18000d95f  lea     rcx, [rsp+2B8h+var_170]; this
0x18000d967  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d96c  nop
0x18000d96d  test    r14b, 2
0x18000d971  jz      short loc_18000D989
0x18000d973  and     r14d, 0FFFFFFFDh
0x18000d977  mov     rcx, [rsp+2B8h+var_228]
0x18000d97f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000d983  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000d988  nop
0x18000d989  test    r14b, 1
0x18000d98d  jz      short loc_18000D99D
0x18000d98f  mov     rcx, [rsp+2B8h+var_250]
0x18000d994  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000d998  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000d99d  lea     rdx, aClientcoreDsEx_16; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18000d9a4  mov     ecx, 3; unsigned __int8
0x18000d9a9  test    dil, dil
0x18000d9ac  jz      short loc_18000D9C5
0x18000d9ae  mov     r15b, 1
0x18000d9b1  lea     r9, aBypassCspCerti; "Bypass CSP certificate enumerate filter"...
0x18000d9b8  mov     r8d, 1A5h; unsigned int
0x18000d9be  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d9c3  jmp     short loc_18000D9DF
0x18000d9c5  mov     r15b, sil
0x18000d9c8  mov     [rsp+2B8h+pvPara], r12
0x18000d9cd  lea     r9, aUseCspCertific; "Use CSP certificate enumerate filter '%"...
0x18000d9d4  mov     r8d, 1AAh; unsigned int
0x18000d9da  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d9df  lea     rax, aMy; "MY"
0x18000d9e6  mov     [rsp+2B8h+pvPara], rax; pvPara
0x18000d9eb  mov     r9d, 1C000h; dwFlags
0x18000d9f1  xor     r8d, r8d; hCryptProv
0x18000d9f4  xor     edx, edx; dwEncodingType
0x18000d9f6  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18000d9f9  call    cs:__imp_CertOpenStore
0x18000d9ff  mov     rdx, rax
0x18000da02  lea     rcx, [rsp+2B8h+var_220]
0x18000da0a  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x18000da0f  mov     rcx, [rsp+2B8h+hCertStore]; hCertStore
0x18000da17  test    rcx, rcx
0x18000da1a  jnz     short loc_18000DA90
0x18000da1c  call    cs:__imp_GetLastError
0x18000da22  test    eax, eax
0x18000da24  jle     short loc_18000DA2E
0x18000da26  movzx   eax, ax
0x18000da29  or      eax, 80070000h
0x18000da2e  mov     [rsp+2B8h+var_268], eax
0x18000da32  mov     dword ptr [rsp+2B8h+pvPara], eax
0x18000da36  lea     r9, aCertopenstoreF; "CertOpenStore failed with hr=0x%x"
0x18000da3d  mov     r8d, 1B8h; unsigned int
0x18000da43  lea     rdx, aClientcoreDsEx_16; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18000da4a  mov     ecx, 3; unsigned __int8
0x18000da4f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000da54  nop
0x18000da55  mov     rcx, [rsp+2B8h+var_240]
0x18000da5a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000da5e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000da63  nop
0x18000da64  lea     rcx, [rbx-18h]; this
0x18000da68  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000da6d  nop
0x18000da6e  mov     rcx, [rsp+2B8h+var_260]
0x18000da73  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000da77  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000da7c  nop
0x18000da7d  lea     rcx, [rsp+2B8h+var_1C0]
0x18000da85  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000da8a  nop
0x18000da8b  jmp     loc_18000DC16
0x18000da90  lea     rax, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x18000da97  mov     [rsp+2B8h+var_250], rax
0x18000da9c  xor     edx, edx; pPrevCertContext
0x18000da9e  call    cs:__imp_CertEnumCertificatesInStore
0x18000daa4  mov     r12b, [rsp+2B8h+var_258]
0x18000daa9  mov     [rsp+2B8h+var_248], rax
0x18000daae  mov     rsi, rax
0x18000dab1  test    rax, rax
0x18000dab4  jz      loc_18000DBD5
0x18000daba  lea     rax, [rsp+2B8h+var_158]
0x18000dac2  mov     [rsp+2B8h+var_280], rax; void *
0x18000dac7  mov     [rsp+2B8h+pCertContext], rsi; pCertContext
0x18000dacc  mov     al, [rsp+2B8h+var_258+1]
0x18000dad0  mov     byte ptr [rsp+2B8h+pvPara], al; char
0x18000dad4  mov     r9b, r12b; int
0x18000dad7  mov     r8b, r15b; int
0x18000dada  lea     rdx, [rsp+2B8h+var_200]; int
0x18000dae2  lea     rcx, [rsp+2B8h+var_1E0]; int
0x18000daea  call    ?ValidateCertificate@@YAJPEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@0_N11PEBU_CERT_CONTEXT@@HPEAU_IDCRLCertInfo@IDCRL@@@Z; ValidateCertificate(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,bool,bool,bool,_CERT_CONTEXT const *,int,IDCRL::_IDCRLCertInfo *)
0x18000daef  mov     [rsp+2B8h+var_268], eax
0x18000daf3  cmp     eax, 8010002Ch
0x18000daf8  jnz     short loc_18000DB07
  ... truncated ...
```
