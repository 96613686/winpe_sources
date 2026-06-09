# FinalPolicyInternal_

- ea: `0x180040d58`
- end: `0x18004179a`
- name: `FinalPolicyInternal_`
- size: `2626`
- prototype: `__int64 __fastcall(__int64, struct _CRYPT_PROVIDER_DATA *, void *, void *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042ca0`

## callees

- `0x180018c00`
- `0x1800246f0`
- `0x180025304`
- `0x180025a7c`
- `0x180025b44`
- `0x18002627c`
- `0x180026320`
- `0x180026494`
- `0x18002737c`
- `0x180027dac`
- `0x18002b22c`
- `0x18002c090`
- `0x18002c34c`
- `0x18002d060`
- `0x18002e5d0`
- `0x180030224`
- `0x180040d58`
- `0x1800421dc`
- `0x180042718`
- `0x180042b94`
- `0x180042bcc`
- `0x180043a30`
- `0x180048924`
- `0x180048eec`
- `0x180049568`
- `0x18004994c`
- `0x18004c230`
- `0x18004de52`
- `0x18004de6a`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004163a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004163a`
- `ntdll!RtlFreeUnicodeString` at `0x180041600`
- `ntdll!RtlFreeUnicodeString` at `0x180041600`

## string_xrefs

- `0x180041080`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x1800412c0`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall FinalPolicyInternal_(
        __int64 a1,
        struct _CRYPT_PROVIDER_DATA *a2,
        void *a3,
        void *a4,
        unsigned int a5,
        __int64 a6)
{
  unsigned __int64 v9; // r15
  __int64 v10; // rbx
  int v11; // eax
  bool v12; // r14
  unsigned __int8 v13; // r11
  unsigned __int8 v14; // r9
  __int64 i; // r10
  __int64 v16; // rcx
  int v17; // ebx
  void *v18; // r12
  char v19; // al
  int OriginalFilenameAndVersionFromImageBase; // eax
  unsigned int v21; // r8d
  _OWORD *v22; // rax
  unsigned int v23; // r14d
  HCRYPTMSG hMsg; // rcx
  int ResourcesFromMsg; // eax
  BOOL v26; // ecx
  WINTRUST_DATA *pWintrustData; // rax
  _DWORD *pPolicyCallbackData; // rdx
  unsigned __int64 v29; // rax
  void *v30; // rax
  int v31; // edx
  char *v32; // rbx
  __int64 v33; // r10
  int v34; // edi
  __int64 v35; // r11
  char *v36; // r14
  __int64 v37; // rcx
  unsigned __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r9
  HLOCAL v42; // r12
  size_t v43; // rdi
  __int64 unique_hlocal; // rax
  HLOCAL v45; // rcx
  void *v46; // r14
  unsigned int v48; // edi
  int v49; // r8d
  unsigned int v50; // edx
  char *v51; // r14
  __int64 v52; // r13
  unsigned __int64 v53; // rax
  int v54; // r11d
  __int64 v55; // r10
  char v56; // dl
  int v57; // eax
  unsigned int v58; // eax
  bool v59; // cl
  bool v60; // zf
  __int128 v61; // xmm1
  __int64 v62; // r12
  unsigned int v63; // edi
  __int64 v64; // rdi
  int PolicyString; // eax
  unsigned int v66; // r8d
  int v67; // eax
  unsigned int v68; // r8d
  __int64 j; // rdi
  unsigned int v70; // edi
  __int128 v71; // xmm1
  __int128 v72; // xmm0
  int v73; // eax
  __int128 v74; // xmm0
  int v75; // eax
  __int128 v76; // xmm1
  __int64 v77; // rax
  __int128 v78; // xmm0
  int v79; // [rsp+20h] [rbp-E0h]
  int v80; // [rsp+20h] [rbp-E0h]
  int v81; // [rsp+20h] [rbp-E0h]
  int v82; // [rsp+30h] [rbp-D0h]
  __int64 v83; // [rsp+58h] [rbp-A8h] BYREF
  void *v84; // [rsp+60h] [rbp-A0h]
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL hMem[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v87; // [rsp+80h] [rbp-80h] BYREF
  __int128 v88; // [rsp+90h] [rbp-70h]
  _QWORD v89[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v90; // [rsp+B0h] [rbp-50h]
  void *v91[2]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v92[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v93[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v94[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v95[2]; // [rsp+F8h] [rbp-8h] BYREF
  PVOID BaseAddress[2]; // [rsp+108h] [rbp+8h] BYREF
  ULONGLONG v97; // [rsp+118h] [rbp+18h]
  _OWORD v98[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v99; // [rsp+140h] [rbp+40h]
  __int64 v100; // [rsp+150h] [rbp+50h]
  __int64 v101; // [rsp+158h] [rbp+58h]
  _QWORD v102[2]; // [rsp+160h] [rbp+60h] BYREF
  int v103; // [rsp+170h] [rbp+70h]
  _QWORD *v104; // [rsp+178h] [rbp+78h]
  __int64 *v105; // [rsp+180h] [rbp+80h]
  __int64 *v106; // [rsp+188h] [rbp+88h]
  __int64 *v107; // [rsp+190h] [rbp+90h]
  void *v108; // [rsp+198h] [rbp+98h]
  char *v109; // [rsp+1C8h] [rbp+C8h]
  int v110; // [rsp+1D0h] [rbp+D0h]
  BOOL v111; // [rsp+1F0h] [rbp+F0h] BYREF
  int v112; // [rsp+1F4h] [rbp+F4h]
  _QWORD *v113; // [rsp+1F8h] [rbp+F8h]
  unsigned int (__fastcall *v114)(void *, void *); // [rsp+200h] [rbp+100h]
  _QWORD *v115; // [rsp+208h] [rbp+108h]
  void (__fastcall *v116)(void *, void *, const struct _UNICODE_STRING ***, unsigned int *); // [rsp+210h] [rbp+110h]
  __int128 v117; // [rsp+218h] [rbp+118h]
  _QWORD v118[15]; // [rsp+230h] [rbp+130h] BYREF
  char v119; // [rsp+2A8h] [rbp+1A8h] BYREF
  int v120; // [rsp+2D8h] [rbp+1D8h]
  int v121; // [rsp+2E0h] [rbp+1E0h]
  HLOCAL v122[4]; // [rsp+2E8h] [rbp+1E8h] BYREF
  int v123; // [rsp+308h] [rbp+208h]
  __int64 v124; // [rsp+330h] [rbp+230h]
  __int128 v125; // [rsp+338h] [rbp+238h]
  __int128 v126; // [rsp+348h] [rbp+248h]
  __int128 v127; // [rsp+358h] [rbp+258h]
  __int128 v128; // [rsp+368h] [rbp+268h]
  __int128 v129; // [rsp+378h] [rbp+278h]
  __int64 v130; // [rsp+388h] [rbp+288h]
  int v131; // [rsp+3B8h] [rbp+2B8h]
  wil::details::in1diag3 *retaddr; // [rsp+428h] [rbp+328h]

  *(_QWORD *)&v87 = a1;
  v100 = 0;
  memset(v98, 0, sizeof(v98));
  v101 = 0;
  v97 = 0;
  hMem[0] = a4;
  LODWORD(v98[0]) = 56;
  v99 = 0;
  *(_OWORD *)BaseAddress = 0;
  memset_0(v118, 0, 0x1A0u);
  v9 = *(unsigned int *)(a1 + 36);
  v10 = *(_QWORD *)(a1 + 40);
  v84 = 0;
  v91[0] = 0;
  v90 = v10;
  v11 = SoftpubAuthenticode(a2);
  v12 = (int)(v11 + 0x80000000) >= 0
     && v11 != -2146762487
     && (v11 != -2146762495 || a2->pWintrustData->dwUnionChoice != 5);
  v13 = 0;
  v14 = 0;
  for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
  {
    v16 = 8 * i;
    if ( v13 || (*(_BYTE *)(*(_QWORD *)(v16 + v10) + 672LL) & 1) != 0 )
      v13 = 1;
    v14 = v14 || (unsigned __int8)SIPolicyIsPolicyAuthRootAuthorized(*(_QWORD *)(v16 + v10));
  }
  if ( !v12 )
  {
    v17 = SiChainInfo::ConvertFromProvData((SiChainInfo *)v98, a2, v13, v14);
    if ( v17 < 0 )
    {
LABEL_61:
      WTConfigCiFreePrivateData(v122);
      FileMapping::cleanup((FileMapping *)BaseAddress);
      SiChainInfo::~SiChainInfo((SiChainInfo *)v98);
      return (unsigned int)v17;
    }
    v123 = DWORD1(v99);
  }
  v92[0] = 0x20000;
  v18 = 0;
  v92[1] = &qword_180056E08;
  v93[0] = 0x20000;
  v93[1] = (__int64)&qword_180056E08;
  v94[0] = 0x20000;
  v94[1] = (__int64)&qword_180056E08;
  v95[0] = 0x20000;
  v95[1] = (__int64)&qword_180056E08;
  Block = 0;
  v112 = 0;
  v83 = 0;
  v117 = 0;
  if ( a3 && FileMapping::reset((FileMapping *)BaseAddress, a3) >= 0 )
  {
    v19 = IsScriptFile(&a2->pPDSip->gSubject, BaseAddress);
    LOBYTE(v112) = 4 * v19;
    if ( v19 )
    {
      hMsg = a2->hMsg;
      if ( hMsg )
      {
        ResourcesFromMsg = GetResourcesFromMsg(hMsg);
        v17 = ResourcesFromMsg;
        if ( ResourcesFromMsg < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x998,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
            (const char *)(unsigned int)ResourcesFromMsg,
            v79);
          goto LABEL_28;
        }
      }
    }
    else
    {
      OriginalFilenameAndVersionFromImageBase = SIPolicyGetOriginalFilenameAndVersionFromImageBase(
                                                  BaseAddress[1],
                                                  (unsigned int)v97,
                                                  (__int64)&Block,
                                                  (__int64)v95,
                                                  v82,
                                                  (__int64)v93,
                                                  (__int64)v94);
      if ( (unsigned int)(OriginalFilenameAndVersionFromImageBase + 1073741687) > 2
        && OriginalFilenameAndVersionFromImageBase != -1073741308
        && OriginalFilenameAndVersionFromImageBase != -1073741793
        && OriginalFilenameAndVersionFromImageBase < 0
        && OriginalFilenameAndVersionFromImageBase != -1073741275 )
      {
        v17 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x991,
                v21,
                (const char *)(unsigned int)OriginalFilenameAndVersionFromImageBase,
                v79);
LABEL_28:
        SIPolicyFreeResources(&v83);
        goto LABEL_61;
      }
      v18 = Block;
    }
  }
  memset_0(v102, 0, 0x88u);
  v60 = !v12;
  v22 = v98;
  v23 = a5;
  if ( !v60 )
    v22 = (_OWORD *)v102[0];
  v102[0] = v22;
  v103 = (unsigned __int8)a5;
  v102[1] = hMem[0];
  v104 = v92;
  v105 = v93;
  v106 = v94;
  v107 = v95;
  v108 = v18;
  v118[0] = a3;
  v109 = &v119;
  v26 = 1;
  v110 = v120;
  pWintrustData = a2->pWintrustData;
  v118[1] = a2;
  pPolicyCallbackData = pWintrustData->pPolicyCallbackData;
  if ( pPolicyCallbackData && *pPolicyCallbackData > 0x20u )
    v26 = pPolicyCallbackData[8] != 131;
  v111 = v26;
  v113 = v118;
  Block = 0;
  v114 = CIProviderExternalAuthorizationCallback;
  v115 = v118;
  v116 = WinTrustPerPolicyFilePathsCallback;
  v29 = 24 * v9;
  if ( !is_mul_ok(v9, 0x18u) )
    v29 = -1;
  v30 = operator new[](v29, (const struct std::nothrow_t *)std::nothrow);
  std::unique_ptr<_SIPOLICY_EXEC_STATUS [0]>::reset(&Block, v30);
  v32 = (char *)Block;
  if ( Block )
  {
    v89[0] = 0;
    if ( (_DWORD)v9 )
    {
      LOBYTE(v31) = 0;
      memset_0(Block, v31, 24 * v9);
    }
    SIPolicyObjectValidationEngine(v87, &v111, v102, v32);
    v33 = 0x48F222A00D2EB091LL;
    v34 = 0;
    v35 = SiPolicyIDEndpointSec;
    if ( (_DWORD)v9 )
    {
      while ( 1 )
      {
        v36 = &v32[24 * v34];
        v37 = *(_QWORD *)v36;
        v38 = -(__int64)(*(_DWORD *)(*(_QWORD *)v36 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
        if ( *(_QWORD *)(v38 + *(_QWORD *)v36 + 720) == v35
          && *(_QWORD *)(v38 + v37 + 728) == v33
          && (unsigned __int8)SIPolicyIsBasePolicy(v37, 6)
          && *(_QWORD *)(v41 + v40 + 720) == v35
          && *(_QWORD *)(v41 + v40 + 728) == v33
          && (unsigned __int8)SIPolicyIsBasePolicy(v40, v39) )
        {
          break;
        }
        if ( ++v34 >= (unsigned int)v9 )
          goto LABEL_54;
      }
      v89[0] = &v32[24 * v34];
      v36[8] = (int)SIPolicyAggregatePolicyValidationResult(v89[0], v32, (unsigned int)v9) >= 0;
      v33 = 0x48F222A00D2EB091LL;
      v35 = SiPolicyIDEndpointSec;
LABEL_54:
      v23 = a5;
    }
    v42 = hMem[0];
    if ( hMem[0] )
    {
      v43 = v23;
      unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned char [0]>(hMem, v23);
      wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
        v91,
        unique_hlocal);
      v45 = hMem[0];
      hMem[0] = 0;
      if ( v45 )
        LocalFree(v45);
      v46 = v91[0];
      v84 = v91[0];
      if ( !v91[0] )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9FC,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
          (const char *)0x8007000ELL,
          v79);
        operator delete(v32);
        SIPolicyFreeResources(&v83);
        v17 = -2147024882;
        goto LABEL_61;
      }
      memcpy_0(v91[0], v42, v43);
      v33 = 0x48F222A00D2EB091LL;
      v35 = SiPolicyIDEndpointSec;
    }
    else
    {
      v46 = 0;
    }
    v48 = 0;
    if ( (_DWORD)v9 )
    {
      v49 = v121;
      while ( 1 )
      {
        DWORD1(v88) = a5;
        v87 = 0u;
        LODWORD(v88) = 0;
        *((_QWORD *)&v88 + 1) = v46;
        if ( v49 < 0 )
        {
          *(_DWORD *)(a6 + 4) = v49;
          goto LABEL_103;
        }
        v50 = 0;
        do
        {
          if ( *(_QWORD *)&v32[24 * v50] == *(_QWORD *)(v90 + 8LL * v48) )
            break;
          ++v50;
        }
        while ( v50 < (unsigned int)v9 );
        v51 = &v32[24 * v50];
        v52 = *(_QWORD *)v51;
        v53 = -(__int64)(*(_DWORD *)(*(_QWORD *)v51 + 40LL) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
        if ( *(_QWORD *)(v53 + *(_QWORD *)v51 + 720) != v35 || *(_QWORD *)(v53 + v52 + 728) != v33 )
          break;
LABEL_93:
        v46 = v84;
        if ( ++v48 >= (unsigned int)v9 )
          goto LABEL_94;
      }
      v54 = SIPolicyAggregatePolicyValidationResult(v51, v32, (unsigned int)v9);
      if ( v54 < 0
        && v89[0]
        && *(_BYTE *)(v89[0] + 8LL)
        && !(unsigned __int8)SIPolicyIsSystemPolicy(
                               *(_QWORD *)&v32[24 * v48]
                             + 704LL
                             + (-(__int64)(*(_DWORD *)(*(_QWORD *)&v32[24 * v48] + 40LL) < 6u) & 0xFFFFFFFFFFFFFD50uLL)) )
      {
        v54 = 0;
        *(_WORD *)&v32[8 * v55 + 8] = 1;
        *(_DWORD *)&v32[8 * v55 + 12] = 0;
        *(_DWORD *)&v32[8 * v55 + 20] |= 0x10000000u;
      }
      v56 = v51[9];
      LOBYTE(v88) = v56;
      if ( v54 >= 0 )
      {
        v58 = 1;
      }
      else
      {
        v57 = *(_DWORD *)(v52 + 44) & 0x10000;
        DWORD1(v87) = v54 | 0x10000000;
        HIDWORD(v87) = v48;
        v58 = (v57 | 0x20000u) >> 16;
      }
      DWORD2(v87) = v58;
      if ( v48 )
      {
        if ( v58 == *(_DWORD *)(a6 + 8) )
        {
          v59 = v56;
          goto LABEL_88;
        }
        if ( v58 != 2 )
        {
          if ( *(_DWORD *)(a6 + 8) == 2 )
            goto LABEL_90;
          v60 = v58 == 3;
          if ( v58 == 3 )
            goto LABEL_87;
          if ( *(_DWORD *)(a6 + 8) == 3 )
          {
            v60 = v58 == 3;
LABEL_87:
            v59 = v60;
LABEL_88:
            if ( !v59 )
              goto LABEL_90;
          }
        }
      }
      v61 = v88;
      *(_OWORD *)a6 = v87;
      *(_OWORD *)(a6 + 16) = v61;
LABEL_90:
      if ( v58 == 2 && v56 )
        goto LABEL_94;
      v49 = v121;
      v33 = 0x48F222A00D2EB091LL;
      v35 = SiPolicyIDEndpointSec;
      goto LABEL_93;
    }
LABEL_94:
    v46 = 0;
    v62 = v90;
    v63 = 0;
    *(_DWORD *)(a6 + 20) = a5;
    *(_QWORD *)(a6 + 24) = v84;
    if ( (_DWORD)v9 )
    {
      while ( !(unsigned __int8)SIPolicyNightsWatchEnabled(*(_QWORD *)(v62 + 8LL * v63)) )
      {
        if ( ++v63 >= (unsigned int)v9 )
        {
          v46 = 0;
          goto LABEL_98;
        }
      }
      v71 = v126;
      *(_OWORD *)(a6 + 36) = *(_OWORD *)((-(__int64)(*(_DWORD *)(*(_QWORD *)&v32[24 * v63] + 40LL) < 6u)
                                        & 0xFFFFFFFFFFFFFD50uLL)
                                       + *(_QWORD *)&v32[24 * v63]
                                       + 704);
      v72 = v125;
      *(_BYTE *)(a6 + 56) = v32[24 * v63 + 8];
      *(_BYTE *)(a6 + 57) = v32[24 * v63 + 9];
      *(_DWORD *)(a6 + 60) = *(_DWORD *)&v32[24 * v63 + 12];
      *(_DWORD *)(a6 + 64) = *(_DWORD *)&v32[24 * v63 + 16];
      v73 = *(_DWORD *)&v32[24 * v63 + 20];
      *(_OWORD *)(a6 + 80) = v72;
      *(_DWORD *)(a6 + 68) = v73;
      v74 = v127;
      v75 = v123;
      *(_OWORD *)(a6 + 96) = v71;
      *(_DWORD *)(a6 + 32) = v75;
      v76 = v128;
      v77 = v124;
      *(_OWORD *)(a6 + 112) = v74;
      *(_QWORD *)(a6 + 72) = v77;
      v78 = v129;
      *(_OWORD *)(a6 + 128) = v76;
      *(_QWORD *)&v76 = v130;
      *(_OWORD *)(a6 + 144) = v78;
      *(_QWORD *)(a6 + 160) = v76;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SAC_LocalLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SAC_LocalLogging>::GetImpl'::`2'::impl) )
        *(_DWORD *)(a6 + 208) = v131;
      memset_0(v122, 0, 0xE8u);
      v46 = 0;
    }
LABEL_98:
    if ( *(_DWORD *)(a6 + 8) != 1 )
    {
      v89[0] = 1441812;
      v89[1] = L"PolicyInfo";
      v91[0] = (void *)1572886;
      v91[1] = L"Information";
      *(_QWORD *)&v87 = 655368;
      *((_QWORD *)&v87 + 1) = L"Name";
      hMem[0] = (HLOCAL)393220;
      hMem[1] = L"ID";
      v64 = *(_QWORD *)(v62 + 8LL * *(unsigned int *)(a6 + 12));
      *(_OWORD *)(a6 + 168) = *(_OWORD *)((-(__int64)(*(_DWORD *)(v64 + 40) < 6u) & 0xFFFFFFFFFFFFFD50uLL) + v64 + 704);
      *(_QWORD *)(a6 + 184) = *(_QWORD *)(v64 + 32);
      PolicyString = QueryPolicyString(v64, (unsigned int)v89, (unsigned int)v91, (unsigned int)&v87, a6 + 192);
      if ( PolicyString < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xA84, v66, (const char *)(unsigned int)PolicyString, v80);
      v67 = QueryPolicyString(v64, (unsigned int)v89, (unsigned int)&v87, (unsigned int)hMem, a6 + 200);
      if ( v67 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xA8A, v68, (const char *)(unsigned int)v67, v81);
    }
LABEL_103:
    for ( j = 1; j != 6; ++j )
    {
      if ( v118[2 * j + 4] )
        RtlFreeUnicodeString((PUNICODE_STRING)&v118[2 * j + 3]);
    }
    v70 = *(_DWORD *)(a6 + 4);
    operator delete(Block);
    SIPolicyFreeResources(&v83);
    WTConfigCiFreePrivateData(v122);
    if ( v46 )
      LocalFree(v46);
    FileMapping::cleanup((FileMapping *)BaseAddress);
    SiChainInfo::~SiChainInfo((SiChainInfo *)v98);
    return v70;
  }
  else
  {
    operator delete(0);
    SIPolicyFreeResources(&v83);
    WTConfigCiFreePrivateData(v122);
    FileMapping::cleanup((FileMapping *)BaseAddress);
    SiChainInfo::~SiChainInfo((SiChainInfo *)v98);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180040d58  push    rbp
0x180040d5a  push    rbx
0x180040d5b  push    rsi
0x180040d5c  push    rdi
0x180040d5d  push    r12
0x180040d5f  push    r13
0x180040d61  push    r14
0x180040d63  push    r15
0x180040d65  lea     rbp, [rsp-2E8h]
0x180040d6d  sub     rsp, 3E8h
0x180040d74  mov     rax, cs:__security_cookie
0x180040d7b  xor     rax, rsp
0x180040d7e  mov     [rbp+320h+var_50], rax
0x180040d85  mov     eax, [rbp+320h+arg_20]
0x180040d8b  xorps   xmm0, xmm0
0x180040d8e  mov     rsi, [rbp+320h+arg_28]
0x180040d95  mov     r13, r8
0x180040d98  mov     dword ptr [rsp+420h+Size], eax
0x180040d9c  mov     rdi, rdx
0x180040d9f  xor     eax, eax
0x180040da1  mov     qword ptr [rbp+320h+var_3A0], rcx
0x180040da5  mov     rbx, rcx
0x180040da8  mov     [rbp+320h+var_2D0], rax
0x180040dac  movups  [rbp+320h+var_300], xmm0
0x180040db0  xor     edx, edx; Val
0x180040db2  mov     [rbp+320h+var_2C8], rax
0x180040db6  mov     r8d, 1A0h; Size
0x180040dbc  mov     [rbp+320h+var_308], rax
0x180040dc0  lea     rcx, [rbp+320h+var_1F0]; void *
0x180040dc7  mov     [rsp+420h+hMem], r9
0x180040dcc  movups  [rbp+320h+var_2F0], xmm0
0x180040dd0  mov     dword ptr [rbp+320h+var_300], 38h ; '8'
0x180040dd7  movups  [rbp+320h+var_2E0], xmm0
0x180040ddb  movdqu  xmmword ptr [rbp+320h+BaseAddress], xmm0
0x180040de0  call    memset_0
0x180040de5  mov     r15d, [rbx+24h]
0x180040de9  xor     eax, eax
0x180040deb  mov     rbx, [rbx+28h]
0x180040def  mov     rcx, rdi; struct _CRYPT_PROVIDER_DATA *
0x180040df2  mov     [rsp+420h+var_3C0], rax
0x180040df7  mov     [rbp+320h+var_368], rax
0x180040dfb  mov     [rbp+320h+var_370], rbx
0x180040dff  call    SoftpubAuthenticode
0x180040e04  mov     edx, 80000000h
0x180040e09  lea     ecx, [rax+rdx]
0x180040e0c  test    edx, ecx
0x180040e0e  jnz     short loc_180040E2D
0x180040e10  cmp     eax, 800B0109h
0x180040e15  jz      short loc_180040E2D
0x180040e17  cmp     eax, 800B0101h
0x180040e1c  jnz     short loc_180040E28
0x180040e1e  mov     rax, [rdi+8]
0x180040e22  cmp     dword ptr [rax+20h], 5
0x180040e26  jz      short loc_180040E2D
0x180040e28  mov     r14b, 1
0x180040e2b  jmp     short loc_180040E30
0x180040e2d  xor     r14b, r14b
0x180040e30  xor     r11b, r11b
0x180040e33  xor     r9b, r9b
0x180040e36  xor     r10d, r10d
0x180040e39  test    r15d, r15d
0x180040e3c  jz      short loc_180040E7D
0x180040e3e  lea     rcx, ds:0[r10*8]
0x180040e46  test    r11b, r11b
0x180040e49  jnz     short loc_180040E58
0x180040e4b  mov     rax, [rcx+rbx]
0x180040e4f  test    byte ptr [rax+2A0h], 1
0x180040e56  jz      short loc_180040E5B
0x180040e58  mov     r11b, 1
0x180040e5b  test    r9b, r9b
0x180040e5e  jnz     short loc_180040E72
0x180040e60  mov     rcx, [rcx+rbx]
0x180040e64  call    SIPolicyIsPolicyAuthRootAuthorized
0x180040e69  test    al, al
0x180040e6b  jnz     short loc_180040E72
0x180040e6d  xor     r9b, r9b
0x180040e70  jmp     short loc_180040E75
0x180040e72  mov     r9b, 1; unsigned __int8
0x180040e75  inc     r10d
0x180040e78  cmp     r10d, r15d
0x180040e7b  jb      short loc_180040E3E
0x180040e7d  test    r14b, r14b
0x180040e80  jnz     short loc_180040EA4
0x180040e82  mov     r8b, r11b; unsigned __int8
0x180040e85  lea     rcx, [rbp+320h+var_300]; this
0x180040e89  mov     rdx, rdi; struct _CRYPT_PROVIDER_DATA *
0x180040e8c  call    ?ConvertFromProvData@SiChainInfo@@QEAAJPEBU_CRYPT_PROVIDER_DATA@@EE@Z; SiChainInfo::ConvertFromProvData(_CRYPT_PROVIDER_DATA const *,uchar,uchar)
0x180040e91  mov     ebx, eax
0x180040e93  test    eax, eax
0x180040e95  js      loc_1800412EE
0x180040e9b  mov     eax, dword ptr [rbp+320h+var_2E0+4]
0x180040e9e  mov     [rbp+320h+var_118], eax
0x180040ea4  lea     rcx, qword_180056E08
0x180040eab  mov     [rbp+320h+var_358], 20000h
0x180040eb3  xor     r12d, r12d
0x180040eb6  mov     [rbp+320h+var_350], rcx
0x180040eba  xor     ebx, ebx
0x180040ebc  mov     [rbp+320h+var_348], 20000h
0x180040ec4  mov     [rbp+320h+var_340], rcx
0x180040ec8  xorps   xmm0, xmm0
0x180040ecb  mov     [rbp+320h+var_338], 20000h
0x180040ed3  mov     [rbp+320h+var_330], rcx
0x180040ed7  mov     [rbp+320h+var_328], 20000h
0x180040edf  mov     [rbp+320h+var_320], rcx
0x180040ee3  mov     [rsp+420h+Block], r12
0x180040ee8  mov     [rbp+320h+var_22C], r12d
0x180040eef  mov     [rsp+420h+var_3C8], rbx
0x180040ef4  movdqu  [rbp+320h+var_208], xmm0
0x180040efc  test    r13, r13
0x180040eff  jz      loc_180040FC8
0x180040f05  mov     rdx, r13; void *
0x180040f08  lea     rcx, [rbp+320h+BaseAddress]; this
0x180040f0c  call    ?reset@FileMapping@@QEAAJPEAX@Z; FileMapping::reset(void *)
0x180040f11  test    eax, eax
0x180040f13  js      loc_180040FC3
0x180040f19  mov     rcx, [rdi+0A0h]
0x180040f20  lea     rdx, [rbp+320h+BaseAddress]
0x180040f24  add     rcx, 4
0x180040f28  call    IsScriptFile
0x180040f2d  mov     cl, al
0x180040f2f  shl     cl, 2
0x180040f32  mov     byte ptr [rbp+320h+var_22C], cl
0x180040f38  test    al, al
0x180040f3a  jnz     loc_180041058
0x180040f40  mov     edx, dword ptr [rbp+320h+var_308]; Size
0x180040f43  lea     rax, [rbp+320h+var_338]
0x180040f47  mov     rcx, [rbp+320h+BaseAddress+8]; BaseAddress
0x180040f4b  lea     r9, [rbp+320h+var_358]
0x180040f4f  mov     [rsp+420h+var_3E0], rax; __int64
0x180040f54  lea     rax, [rbp+320h+var_348]
0x180040f58  mov     [rsp+420h+var_3E8], rax; __int64
0x180040f5d  lea     rax, [rbp+320h+var_328]
0x180040f61  mov     [rsp+420h+var_3F8], rax; __int64
0x180040f66  lea     rax, [rsp+420h+Block]
0x180040f6b  mov     [rsp+420h+var_400], rax; int
0x180040f70  call    SIPolicyGetOriginalFilenameAndVersionFromImageBase
0x180040f75  lea     ecx, [rax+3FFFFF77h]
0x180040f7b  cmp     ecx, 2
0x180040f7e  jbe     short loc_180040FBE
0x180040f80  cmp     eax, 0C0000204h
0x180040f85  jz      short loc_180040FBE
0x180040f87  cmp     eax, 0C000001Fh
0x180040f8c  jz      short loc_180040FBE
0x180040f8e  test    eax, eax
0x180040f90  jns     short loc_180040FBE
0x180040f92  cmp     eax, 0C0000225h
0x180040f97  jz      short loc_180040FBE
0x180040f99  mov     rcx, [rbp+328h]; this
0x180040fa0  mov     r9d, eax; char *
0x180040fa3  mov     edx, 991h; void *
0x180040fa8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180040fad  mov     ebx, eax
0x180040faf  lea     rcx, [rsp+420h+var_3C8]
0x180040fb4  call    SIPolicyFreeResources
0x180040fb9  jmp     loc_1800412EE
0x180040fbe  mov     r12, [rsp+420h+Block]
0x180040fc3  mov     rbx, [rsp+420h+var_3C8]
0x180040fc8  xor     edx, edx; Val
0x180040fca  lea     rcx, [rbp+320h+var_2C0]; void *
0x180040fce  mov     r8d, 88h; Size
0x180040fd4  call    memset_0
0x180040fd9  test    r14b, r14b
0x180040fdc  lea     rax, [rbp+320h+var_300]
0x180040fe0  mov     r14d, dword ptr [rsp+420h+Size]
0x180040fe5  cmovnz  rax, [rbp+320h+var_2C0]
0x180040fea  test    rbx, rbx
0x180040fed  mov     [rbp+320h+var_2C0], rax
0x180040ff1  movzx   eax, r14b
0x180040ff5  mov     [rbp+320h+var_2B0], eax
0x180040ff8  mov     rax, [rsp+420h+hMem]
0x180040ffd  mov     [rbp+320h+var_2B8], rax
0x180041001  lea     rax, [rbp+320h+var_358]
0x180041005  cmovnz  rax, rbx
0x180041009  mov     [rbp+320h+var_2A8], rax
0x18004100d  lea     rax, [rbx+10h]
0x180041011  jnz     short loc_180041017
0x180041013  lea     rax, [rbp+320h+var_348]
0x180041017  mov     [rbp+320h+var_2A0], rax
0x18004101e  lea     rax, [rbx+20h]
0x180041022  test    rbx, rbx
0x180041025  jnz     short loc_18004102B
0x180041027  lea     rax, [rbp+320h+var_338]
0x18004102b  mov     [rbp+320h+var_298], rax
0x180041032  lea     rax, [rbx+30h]
0x180041036  test    rbx, rbx
0x180041039  jnz     short loc_18004103F
0x18004103b  lea     rax, [rbp+320h+var_328]
0x18004103f  mov     [rbp+320h+var_290], rax
0x180041046  test    rbx, rbx
0x180041049  jz      short loc_180041099
0x18004104b  mov     rax, [rbx+40h]
0x18004104f  mov     [rbp+320h+var_288], rax
0x180041056  jmp     short loc_1800410A0
0x180041058  mov     rcx, [rdi+70h]; hCryptMsg
0x18004105c  test    rcx, rcx
0x18004105f  jz      loc_180040FC3
0x180041065  lea     rdx, [rsp+420h+var_3C8]
0x18004106a  call    GetResourcesFromMsg
0x18004106f  mov     ebx, eax
0x180041071  test    eax, eax
0x180041073  jns     loc_180040FC3
0x180041079  mov     rcx, [rbp+328h]; this
0x180041080  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180041087  mov     r9d, eax; char *
0x18004108a  mov     edx, 998h; void *
0x18004108f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041094  jmp     loc_180040FAF
0x180041099  mov     [rbp+320h+var_288], r12
0x1800410a0  lea     rax, [rbp+320h+var_178]
0x1800410a7  mov     [rbp+320h+var_1F0], r13
0x1800410ae  mov     [rbp+320h+var_258], rax
0x1800410b5  xor     r13d, r13d
0x1800410b8  mov     eax, [rbp+320h+var_148]
0x1800410be  mov     ecx, 1
0x1800410c3  mov     [rbp+320h+var_250], eax
0x1800410c9  mov     rax, [rdi+8]
0x1800410cd  mov     [rbp+320h+var_1E8], rdi
0x1800410d4  mov     rdx, [rax+8]
0x1800410d8  test    rdx, rdx
0x1800410db  jz      short loc_1800410ED
0x1800410dd  cmp     dword ptr [rdx], 20h ; ' '
0x1800410e0  jbe     short loc_1800410ED
0x1800410e2  cmp     dword ptr [rdx+20h], 83h
0x1800410e9  cmovz   ecx, r13d
0x1800410ed  mov     [rbp+320h+var_230], ecx
0x1800410f3  lea     rax, [rbp+320h+var_1F0]
0x1800410fa  mov     [rbp+320h+var_228], rax
0x180041101  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180041108  lea     rax, ?CIProviderExternalAuthorizationCallback@@YAKPEAX0@Z; CIProviderExternalAuthorizationCallback(void *,void *)
0x18004110f  mov     [rsp+420h+Block], r13
0x180041114  mov     [rbp+320h+var_220], rax
0x18004111b  lea     rax, [rbp+320h+var_1F0]
0x180041122  mov     [rbp+320h+var_218], rax
0x180041129  lea     rax, ?WinTrustPerPolicyFilePathsCallback@@YAXPEAX0PEAPEAPEBU_UNICODE_STRING@@PEAK@Z; WinTrustPerPolicyFilePathsCallback(void *,void *,_UNICODE_STRING const * * *,ulong *)
0x180041130  mov     [rbp+320h+var_210], rax
0x180041137  mov     eax, 18h
0x18004113c  mul     r15
0x18004113f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180041146  cmovb   rax, rcx
0x18004114a  mov     rcx, rax; unsigned __int64
0x18004114d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180041152  mov     rdx, rax
0x180041155  lea     rcx, [rsp+420h+Block]
0x18004115a  call    ?reset@?$unique_ptr@$$BY0A@U_SIPOLICY_EXEC_STATUS@@U?$default_delete@$$BY0A@U_SIPOLICY_EXEC_STATUS@@@std@@@std@@QEAAXPEAU_SIPOLICY_EXEC_STATUS@@@Z; std::unique_ptr<_SIPOLICY_EXEC_STATUS [0]>::reset(_SIPOLICY_EXEC_STATUS *)
0x18004115f  mov     rbx, [rsp+420h+Block]
0x180041164  test    rbx, rbx
0x180041167  jz      loc_180041743
0x18004116d  mov     [rbp+320h+var_380], r13
0x180041171  test    r15d, r15d
0x180041174  jz      short loc_180041188
0x180041176  lea     r8, [r15+r15*2]
0x18004117a  xor     dl, dl; Val
0x18004117c  shl     r8, 3; Size
0x180041180  mov     rcx, rbx; void *
0x180041183  call    memset_0
0x180041188  mov     rcx, qword ptr [rbp+320h+var_3A0]
0x18004118c  lea     r8, [rbp+320h+var_2C0]
0x180041190  mov     r9, rbx
0x180041193  lea     rdx, [rbp+320h+var_230]
0x18004119a  call    SIPolicyObjectValidationEngine
0x18004119f  mov     r10, cs:qword_180058D98
0x1800411a6  mov     edi, r13d
0x1800411a9  mov     r11, cs:SiPolicyIDEndpointSec
0x1800411b0  mov     edx, 6
0x1800411b5  test    r15d, r15d
0x1800411b8  jz      loc_18004124E
0x1800411be  mov     eax, edi
0x1800411c0  lea     rcx, [rax+rax*2]
0x1800411c4  lea     r14, [rbx+rcx*8]
0x1800411c8  mov     rcx, [r14]
0x1800411cb  cmp     [rcx+28h], edx
0x1800411ce  sbb     r9, r9
0x1800411d1  and     r9, 0FFFFFFFFFFFFFD40h
0x1800411d8  cmp     [r9+rcx+2D0h], r11
0x1800411e0  jnz     short loc_180041217
0x1800411e2  cmp     [r9+rcx+2D8h], r10
0x1800411ea  jnz     short loc_180041217
0x1800411ec  call    SIPolicyIsBasePolicy
0x1800411f1  test    al, al
0x1800411f3  jz      short loc_180041212
0x1800411f5  cmp     [r9+rcx+2D0h], r11
0x1800411fd  jnz     short loc_180041212
0x1800411ff  cmp     [r9+rcx+2D8h], r10
0x180041207  jnz     short loc_180041212
0x180041209  call    SIPolicyIsBasePolicy
0x18004120e  test    al, al
0x180041210  jnz     short loc_180041220
0x180041212  mov     edx, 6
0x180041217  inc     edi
0x180041219  cmp     edi, r15d
0x18004121c  jb      short loc_1800411BE
0x18004121e  jmp     short loc_180041249
0x180041220  mov     r8d, r15d
0x180041223  mov     [rbp+320h+var_380], r14
0x180041227  mov     rdx, rbx
0x18004122a  mov     rcx, r14
0x18004122d  call    SIPolicyAggregatePolicyValidationResult
0x180041232  shr     eax, 1Fh
0x180041235  xor     al, 1
0x180041237  mov     [r14+8], al
  ... truncated ...
```
