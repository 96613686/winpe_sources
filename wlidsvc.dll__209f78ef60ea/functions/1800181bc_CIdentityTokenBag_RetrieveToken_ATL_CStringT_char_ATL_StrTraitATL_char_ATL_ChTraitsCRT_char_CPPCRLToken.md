# CIdentityTokenBag::RetrieveToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CPPCRLToken &)

- ea: `0x1800181bc`
- end: `0x180018dda`
- name: `?RetrieveToken@CIdentityTokenBag@@QEAAHV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAVCPPCRLToken@@@Z`
- size: `3102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800122b0`
- `0x1800272b0`
- `0x18002795c`
- `0x1800287f0`
- `0x180028cd4`
- `0x180041ae8`
- `0x180052ca8`
- `0x180075bd0`
- `0x1800903c4`
- `0x1800921bc`
- `0x1800b67b0`
- `0x1800bfd30`
- `0x1800ce0f0`
- `0x1800ce730`
- `0x1800d97b0`
- `0x1800f8070`
- `0x1800fa368`

## callees

- `0x180014490`
- `0x1800151c4`
- `0x180015860`
- `0x180017868`
- `0x180017e38`
- `0x1800181bc`
- `0x180018f80`
- `0x180019130`
- `0x1800191c0`
- `0x18001921c`
- `0x18001b050`
- `0x18001b760`
- `0x180036adc`
- `0x180037288`
- `0x18007c408`
- `0x180084374`
- `0x18008b65c`
- `0x1800a3b60`
- `0x1800a4784`
- `0x180116c40`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__mbscmp` at `0x1800183dd`
- `api-ms-win-crt-private-l1-1-0!_o__mbscmp` at `0x1800183dd`
- `api-ms-win-crt-private-l1-1-0!_o__mbsicmp` at `0x180018a3d`
- `api-ms-win-crt-private-l1-1-0!_o__mbsicmp` at `0x180018a3d`
- `api-ms-win-crt-private-l1-1-0!_o__mbslwr_s` at `0x180018359`
- `api-ms-win-crt-private-l1-1-0!_o__mbslwr_s` at `0x180018359`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018251`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018ab0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018bb3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018c0f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018c6b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018cc7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018d23`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018251`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018ab0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018bb3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018c0f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018c6b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018cc7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180018d23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018849`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018849`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001888e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001888e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018319`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018319`
- `CRYPTSP!CryptContextAddRef` at `0x1800189bf`
- `CRYPTSP!CryptContextAddRef` at `0x1800189bf`

## string_xrefs

- `0x180018201`: `CIdentityTokenBag::RetrieveToken`
- `0x18001828f`: `CIdentityTokenBag::RetrieveToken`
- `0x180018917`: `CIdentityTokenBag::RetrieveToken`
- `0x180018247`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`
- `0x180018aa6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`
- `0x180018ba9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`
- `0x180018c05`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`
- `0x180018c61`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`
- `0x180018cbd`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`
- `0x180018d19`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\tokenbag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CIdentityTokenBag::RetrieveToken(__int64 a1, const unsigned __int8 **a2, __int64 a3)
{
  unsigned int v6; // r14d
  const char *v7; // rbx
  char *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rax
  int v12; // eax
  __int64 *v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // rsi
  int v16; // eax
  const unsigned __int8 *v17; // r15
  signed __int8 v18; // al
  const unsigned __int8 *v19; // rcx
  __int64 v20; // rsi
  __int64 i; // rsi
  _QWORD *v22; // rcx
  volatile signed __int32 *v23; // rsi
  __int64 v24; // r14
  _QWORD *v25; // rcx
  volatile signed __int32 *v26; // rsi
  __int64 v27; // r15
  _QWORD *v28; // rcx
  volatile signed __int32 *v29; // rsi
  __int64 v30; // r15
  _QWORD *v31; // rcx
  volatile signed __int32 *v32; // rsi
  __int64 v33; // r15
  _QWORD *v34; // r15
  _QWORD *v35; // rcx
  volatile signed __int32 *v36; // rsi
  __int64 v37; // r14
  _QWORD *v38; // rcx
  volatile signed __int32 *v39; // rsi
  __int64 v40; // r12
  _QWORD *v41; // rcx
  volatile signed __int32 *v42; // rsi
  __int64 v43; // r12
  _QWORD *v44; // rcx
  volatile signed __int32 *v45; // rsi
  __int64 v46; // r12
  const void *v47; // r12
  size_t v48; // rsi
  HLOCAL v49; // rax
  unsigned int v50; // edi
  int v51; // r8d
  volatile signed __int32 *v52; // rdx
  HCRYPTPROV v54; // rcx
  int v55; // esi
  int v56; // r14d
  _QWORD *v57; // rcx
  volatile signed __int32 *v58; // rdi
  __int64 v59; // rbx
  char *v60; // rax
  __int64 v61; // rax
  char *v62; // rax
  __int64 v63; // rax
  char *v64; // rax
  __int64 v65; // rax
  char *v66; // rax
  __int64 v67; // rax
  char *v68; // rax
  __int64 v69; // rax
  char *v70; // rax
  __int64 v71; // rax
  __int64 pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  char *v73; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v74; // [rsp+40h] [rbp-C0h] BYREF
  int v75; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v76; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v77; // [rsp+60h] [rbp-A0h] BYREF
  int v78; // [rsp+68h] [rbp-98h]
  __int64 v79; // [rsp+70h] [rbp-90h]
  int v80; // [rsp+78h] [rbp-88h]
  __int64 v81; // [rsp+80h] [rbp-80h]
  __int64 v82; // [rsp+88h] [rbp-78h]
  __int64 v83; // [rsp+90h] [rbp-70h]
  __int64 v84; // [rsp+98h] [rbp-68h]
  __int64 v85; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v86; // [rsp+A8h] [rbp-58h] BYREF
  int v87; // [rsp+B0h] [rbp-50h]
  int v88; // [rsp+B4h] [rbp-4Ch]
  __int64 v89; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v90; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v91; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v92; // [rsp+D0h] [rbp-30h] BYREF
  SIZE_T uBytes[3]; // [rsp+D8h] [rbp-28h] BYREF
  HCRYPTPROV hProv; // [rsp+F0h] [rbp-10h] BYREF
  char v95; // [rsp+F8h] [rbp-8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+100h] [rbp+0h]
  char v97; // [rsp+108h] [rbp+8h]
  const unsigned __int8 **v98; // [rsp+110h] [rbp+10h]
  const char *v99; // [rsp+118h] [rbp+18h]
  char **v100; // [rsp+120h] [rbp+20h]
  __int64 v101; // [rsp+128h] [rbp+28h]
  __int64 v102; // [rsp+130h] [rbp+30h]
  char v103[16]; // [rsp+140h] [rbp+40h] BYREF
  const char *v104; // [rsp+150h] [rbp+50h]
  int v105; // [rsp+158h] [rbp+58h]
  int v106; // [rsp+15Ch] [rbp+5Ch]
  const char *v107; // [rsp+160h] [rbp+60h]
  __int64 v108; // [rsp+168h] [rbp+68h]
  __int64 *p_pExceptionObject; // [rsp+170h] [rbp+70h]
  __int64 v110; // [rsp+178h] [rbp+78h]
  const wchar_t *v111; // [rsp+180h] [rbp+80h]
  __int64 v112; // [rsp+188h] [rbp+88h]

  v98 = a2;
  LODWORD(v73) = 1;
  v99 = "CIdentityTokenBag::RetrieveToken";
  v100 = &v73;
  v6 = 0;
  v101 = 0;
  v102 = 0;
  if ( dword_1801C3ABC != 4 )
  {
    switch ( dword_1801C3ABC )
    {
      case 5:
        if ( byte_1801C36C5 >= 0 )
          goto LABEL_11;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp";
        v70 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp", 92);
        if ( v70 )
          v7 = v70 + 1;
        LODWORD(pExceptionObject) = 230;
        if ( v7 )
        {
          v71 = -1;
          do
            ++v71;
          while ( v7[v71] );
          v12 = v71 + 1;
        }
        else
        {
          v7 = "NULL";
          v12 = 5;
        }
        v13 = WlidModern_TraceFunction_Enter;
        break;
      case 6:
        if ( (byte_1801C36C7 & 8) == 0 )
          goto LABEL_11;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp";
        v68 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp", 92);
        if ( v68 )
          v7 = v68 + 1;
        LODWORD(pExceptionObject) = 230;
        if ( v7 )
        {
          v69 = -1;
          do
            ++v69;
          while ( v7[v69] );
          v12 = v69 + 1;
        }
        else
        {
          v7 = "NULL";
          v12 = 5;
        }
        v13 = WlidCli_TraceFunction_Enter;
        break;
      case 7:
        if ( (byte_1801C36C8 & 8) == 0 )
          goto LABEL_11;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp";
        v66 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp", 92);
        if ( v66 )
          v7 = v66 + 1;
        LODWORD(pExceptionObject) = 230;
        if ( v7 )
        {
          v67 = -1;
          do
            ++v67;
          while ( v7[v67] );
          v12 = v67 + 1;
        }
        else
        {
          v7 = "NULL";
          v12 = 5;
        }
        v13 = WlidProv_TraceFunction_Enter;
        break;
      case 8:
        if ( (byte_1801C36C9 & 0x10) == 0 )
          goto LABEL_11;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp";
        v64 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp", 92);
        if ( v64 )
          v7 = v64 + 1;
        LODWORD(pExceptionObject) = 230;
        if ( v7 )
        {
          v65 = -1;
          do
            ++v65;
          while ( v7[v65] );
          v12 = v65 + 1;
        }
        else
        {
          v7 = "NULL";
          v12 = 5;
        }
        v13 = WlidBho_TraceFunction_Enter;
        break;
      case 9:
        if ( (byte_1801C36CA & 0x10) == 0 )
          goto LABEL_11;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp";
        v60 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp", 92);
        if ( v60 )
          v7 = v60 + 1;
        LODWORD(pExceptionObject) = 230;
        if ( v7 )
        {
          v61 = -1;
          do
            ++v61;
          while ( v7[v61] );
          v12 = v61 + 1;
        }
        else
        {
          v7 = "NULL";
          v12 = 5;
        }
        v13 = TokenProvider_TraceFunction_Enter;
        break;
      default:
        if ( dword_1801C3ABC != 10 || (byte_1801C36CB & 0x10) == 0 )
          goto LABEL_11;
        v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp";
        v62 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp", 92);
        if ( v62 )
          v7 = v62 + 1;
        LODWORD(pExceptionObject) = 230;
        if ( v7 )
        {
          v63 = -1;
          do
            ++v63;
          while ( v7[v63] );
          v12 = v63 + 1;
        }
        else
        {
          v7 = "NULL";
          v12 = 5;
        }
        v13 = Extension_TraceFunction_Enter;
        break;
    }
    goto LABEL_10;
  }
  if ( (byte_1801C36C4 & 4) != 0 )
  {
    v7 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp";
    v8 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\tokenbag.cpp", 92);
    if ( v8 )
      v7 = v8 + 1;
    LODWORD(pExceptionObject) = 230;
    if ( v7 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v7[v11] );
      v12 = v11 + 1;
    }
    else
    {
      v7 = "NULL";
      v12 = 5;
    }
    v13 = WlidSvc_TraceFunction_Enter;
LABEL_10:
    v105 = v12;
    v107 = "CIdentityTokenBag::RetrieveToken";
    p_pExceptionObject = &pExceptionObject;
    v111 = L"NULL";
    v104 = v7;
    v106 = 0;
    v108 = 33;
    v110 = 4;
    v112 = 10;
    McGenEventWrite_EventWriteTransfer(v9, v13, v10, 5, v103);
  }
LABEL_11:
  v14 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v74 = v14;
  CPPCRLToken::CPPCRLToken((CPPCRLToken *)&v75);
  v95 = 1;
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v97 = 1;
  v15 = *((int *)*a2 - 4);
  if ( !(_DWORD)v15 )
    goto LABEL_80;
  if ( (int)((*((_DWORD *)*a2 - 3) - v15) | (1 - *((_DWORD *)*a2 - 2))) < 0 )
    ATL::CSimpleStringT<char,0>::PrepareWrite2(a2, (unsigned int)v15);
  v16 = _o__mbslwr_s(*a2, (int)v15 + 1);
  ATL::AtlCrtErrorCheck(v16);
  if ( (int)v15 < 0 || (int)v15 > *((_DWORD *)*a2 - 3) )
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a2 - 4) = v15;
  (*a2)[v15] = 0;
  v17 = *a2;
  if ( !*a2 )
    ATL::AtlThrowImpl(-2147467259);
  v18 = *v17;
  if ( *v17 )
  {
    v19 = *a2;
    do
    {
      v6 = v18 + 33 * v6;
      v18 = *++v19;
    }
    while ( *v19 );
  }
  v20 = *(_QWORD *)(a1 + 56);
  if ( v20 )
  {
    for ( i = *(_QWORD *)(v20 + 8LL * (v6 % *(_DWORD *)(a1 + 72))); i; i = *(_QWORD *)(i + 184) )
    {
      if ( *(_DWORD *)(i + 192) == v6 && !(unsigned int)_o__mbscmp(*(_QWORD *)i, v17) )
        goto LABEL_27;
    }
  }
  i = 0;
LABEL_27:
  if ( i )
  {
    v75 = *(_DWORD *)(i + 8);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v76, i + 16);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v77, i + 24);
    v78 = *(_DWORD *)(i + 32);
    v79 = *(_QWORD *)(i + 40);
    v80 = *(_DWORD *)(i + 48);
    v81 = *(_QWORD *)(i + 56);
    v82 = *(_QWORD *)(i + 64);
    v83 = *(_QWORD *)(i + 72);
    v84 = *(_QWORD *)(i + 80);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v85, i + 88);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v86, i + 96);
    v87 = *(_DWORD *)(i + 104);
    v88 = *(_DWORD *)(i + 108);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v89, i + 112);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v90, i + 120);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v91, i + 128);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v92, i + 136);
    CBytePtr::Attach((CBytePtr *)uBytes, *(unsigned __int8 **)(i + 152), *(_DWORD *)(i + 144), 0);
    ATL::CCryptProv::operator=(&hProv, i + 168);
    v95 = *(_BYTE *)(i + 176);
    *(_DWORD *)a3 = v75;
    pExceptionObject = a3 + 8;
    v22 = (_QWORD *)(v76 - 24);
    v23 = (volatile signed __int32 *)(*(_QWORD *)(a3 + 8) - 24LL);
    if ( (volatile signed __int32 *)(v76 - 24) != v23 )
    {
      if ( *((int *)v23 + 4) >= 0 && *v22 == *(_QWORD *)v23 )
      {
        v24 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v22);
        if ( _InterlockedExchangeAdd(v23 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23, v23);
        *(_QWORD *)(a3 + 8) = v24 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3 + 8, v76, *(unsigned int *)(v76 - 16));
      }
    }
    v25 = (_QWORD *)(v77 - 24);
    v26 = (volatile signed __int32 *)(*(_QWORD *)(a3 + 16) - 24LL);
    if ( (volatile signed __int32 *)(v77 - 24) != v26 )
    {
      if ( *((int *)v26 + 4) >= 0 && *v25 == *(_QWORD *)v26 )
      {
        v27 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v25);
        if ( _InterlockedExchangeAdd(v26 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26, v26);
        *(_QWORD *)(a3 + 16) = v27 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3 + 16, v77, *(unsigned int *)(v77 - 16));
      }
    }
    *(_DWORD *)(a3 + 24) = v78;
    *(_QWORD *)(a3 + 32) = v79;
    *(_DWORD *)(a3 + 40) = v80;
    *(_QWORD *)(a3 + 48) = v81;
    *(_QWORD *)(a3 + 56) = v82;
    *(_QWORD *)(a3 + 64) = v83;
    *(_QWORD *)(a3 + 72) = v84;
    v28 = (_QWORD *)(v85 - 24);
    v29 = (volatile signed __int32 *)(*(_QWORD *)(a3 + 80) - 24LL);
    if ( (volatile signed __int32 *)(v85 - 24) != v29 )
    {
      if ( *((int *)v29 + 4) >= 0 && *v28 == *(_QWORD *)v29 )
      {
        v30 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v28);
        if ( _InterlockedExchangeAdd(v29 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29, v29);
        *(_QWORD *)(a3 + 80) = v30 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3 + 80, v85, *(unsigned int *)(v85 - 16));
      }
    }
    v31 = (_QWORD *)(v86 - 24);
    v32 = (volatile signed __int32 *)(*(_QWORD *)(a3 + 88) - 24LL);
    if ( (volatile signed __int32 *)(v86 - 24) != v32 )
    {
      if ( *((int *)v32 + 4) >= 0 && *v31 == *(_QWORD *)v32 )
      {
        v33 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v31);
        if ( _InterlockedExchangeAdd(v32 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v32 + 8LL))(*(_QWORD *)v32, v32);
        *(_QWORD *)(a3 + 88) = v33 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3 + 88, v86, *(unsigned int *)(v86 - 16));
      }
    }
    *(_DWORD *)(a3 + 96) = v87;
    *(_DWORD *)(a3 + 100) = v88;
    v34 = (_QWORD *)(a3 + 104);
    v35 = (_QWORD *)(v89 - 24);
    v36 = (volatile signed __int32 *)(*(_QWORD *)(a3 + 104) - 24LL);
    if ( (volatile signed __int32 *)(v89 - 24) != v36 )
    {
      if ( *((int *)v36 + 4) >= 0 && *v35 == *(_QWORD *)v36 )
      {
        v37 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v35);
        if ( _InterlockedExchangeAdd(v36 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v36 + 8LL))(*(_QWORD *)v36, v36);
        *v34 = v37 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3 + 104, v89, *(unsigned int *)(v89 - 16));
      }
    }
    v38 = (_QWORD *)(v90 - 24);
    v39 = (volatile signed __int32 *)(*(_QWORD *)(a3 + 112) - 24LL);
    if ( (volatile signed __int32 *)(v90 - 24) != v39 )
    {
      if ( *((int *)v39 + 4) >= 0 && *v38 == *(_QWORD *)v39 )
      {
        v40 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v38);
        if ( _InterlockedExchangeAdd(v39 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v39 + 8LL))(*(_QWORD *)v39, v39);
        *(_QWORD *)(a3 + 112) = v40 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3 + 112, v90, *(unsigned int *)(v90 - 16));
      }
    }
    v41 = (_QWORD *)(v91 - 24);
    v42 = (volatile signed __int32 *)(*(_QWORD *)(a3 + 120) - 24LL);
    if ( (volatile signed __int32 *)(v91 - 24) != v42 )
    {
      if ( *((int *)v42 + 4) >= 0 && *v41 == *(_QWORD *)v42 )
      {
        v43 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v41);
        if ( _InterlockedExchangeAdd(v42 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v42 + 8LL))(*(_QWORD *)v42, v42);
        *(_QWORD *)(a3 + 120) = v43 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3 + 120, v91, *(unsigned int *)(v91 - 16));
      }
    }
    v44 = (_QWORD *)(v92 - 24);
    v45 = (volatile signed __int32 *)(*(_QWORD *)(a3 + 128) - 24LL);
    if ( (volatile signed __int32 *)(v92 - 24) != v45 )
    {
      if ( *((int *)v45 + 4) >= 0 && *v44 == *(_QWORD *)v45 )
      {
        v46 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v44);
        if ( _InterlockedExchangeAdd(v45 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v45 + 8LL))(*(_QWORD *)v45, v45);
        *(_QWORD *)(a3 + 128) = v46 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3 + 128, v92, *(unsigned int *)(v92 - 16));
      }
    }
    v47 = (const void *)uBytes[1];
    CBytePtr::Empty((CBytePtr *)(a3 + 136));
    if ( v47 )
    {
      v48 = LODWORD(uBytes[0]);
      v49 = LocalAlloc(0, LODWORD(uBytes[0]));
      *(_QWORD *)(a3 + 144) = v49;
      if ( !v49 )
      {
        LODWORD(pExceptionObject) = -2147024882;
        throw (long *)&pExceptionObject;
      }
      if ( v48 )
        memcpy_0(v49, v47, v48);
      *(_DWORD *)(a3 + 136) = v48;
      *(_DWORD *)(a3 + 152) = v48;
    }
    if ( (HCRYPTPROV *)(a3 + 160) != &hProv )
    {
      ATL::CCryptProv::Release((ATL::CCryptProv *)(a3 + 160));
      v54 = hProv;
      *(_QWORD *)(a3 + 160) = hProv;
      if ( v54 )
      {
        if ( !CryptContextAddRef(v54, 0, 0) )
          ATL::AtlHresultFromLastError();
      }
    }
    LODWORD(v73) = 1;
    v55 = *(_DWORD *)(a3 + 96);
    v56 = *(_DWORD *)(a3 + 100);
    v57 = (_QWORD *)(*v34 - 24LL);
    v58 = (volatile signed __int32 *)(v14 - 24);
    if ( v57 != (_QWORD *)(v14 - 24) )
    {
      if ( *((int *)v58 + 4) >= 0 && *v57 == *(_QWORD *)v58 )
      {
        v59 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v57);
        if ( _InterlockedExchangeAdd(v58 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v58 + 8LL))(*(_QWORD *)v58, v58);
        v14 = v59 + 24;
        v74 = v14;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v74, *v34, *(unsigned int *)(*v34 - 16LL));
        v14 = v74;
      }
    }
    if ( _mbsicmp(*a2, "http://Passport.NET/tb") && (v55 < 0 || v56 < 0) )
      ATL::CSimpleStringT<unsigned short,0>::SetString(pExceptionObject, 0);
  }
  else
  {
LABEL_80:
    LODWORD(v73) = 0;
  }
  v50 = (unsigned int)v73;
  LeaveCriticalSection(lpCriticalSection);
  ATL::CCryptProv::Release((ATL::CCryptProv *)&hProv);
  CBytePtr::Empty((CBytePtr *)uBytes);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v92);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v91);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v90);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v89);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v85);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v77);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v14 - 24) + 8LL))(*(_QWORD *)(v14 - 24));
  MsaTracingInternal::TraceFunctionExit(
    (MsaTracingInternal *)"CIdentityTokenBag::RetrieveToken",
    (const char *)(unsigned int)v73,
    v51);
  v52 = (volatile signed __int32 *)(*a2 - 24);
  if ( _InterlockedExchangeAdd(v52 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v52 + 8LL))(*(_QWORD *)v52);
  return v50;
}

```

## disassembly

```asm
0x1800181bc  mov     [rsp-8+arg_18], rbx
0x1800181c1  push    rbp
0x1800181c2  push    rsi
0x1800181c3  push    rdi
0x1800181c4  push    r12
0x1800181c6  push    r13
0x1800181c8  push    r14
0x1800181ca  push    r15
0x1800181cc  lea     rbp, [rsp-0A0h]
0x1800181d4  sub     rsp, 1A0h
0x1800181db  mov     rax, cs:__security_cookie
0x1800181e2  xor     rax, rsp
0x1800181e5  mov     [rbp+0D0h+var_40], rax
0x1800181ec  mov     rdi, r8
0x1800181ef  mov     r13, rdx
0x1800181f2  mov     r12, rcx
0x1800181f5  mov     [rbp+0D0h+var_C0], rdx
0x1800181f9  mov     dword ptr [rsp+1D0h+var_198], 1
0x180018201  lea     rax, aCidentitytoken_11; "CIdentityTokenBag::RetrieveToken"
0x180018208  mov     [rbp+0D0h+var_B8], rax
0x18001820c  lea     rax, [rsp+1D0h+var_198]
0x180018211  mov     [rbp+0D0h+var_B0], rax
0x180018215  xor     r14d, r14d
0x180018218  mov     [rbp+0D0h+var_A8], r14
0x18001821c  mov     [rbp+0D0h+var_A0], r14
0x180018220  mov     ecx, cs:dword_1801C3ABC
0x180018226  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001822a  lea     r15d, [r14+4]
0x18001822e  sub     ecx, r15d
0x180018231  jnz     loc_180018A69
0x180018237  test    cs:byte_1801C36C4, r15b
0x18001823e  jz      loc_1800182DF
0x180018244  lea     edx, [rsi+5Dh]; Ch
0x180018247  lea     rbx, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001824e  mov     rcx, rbx; Str
0x180018251  call    cs:__imp_strrchr
0x180018257  test    rax, rax
0x18001825a  jz      short loc_180018260
0x18001825c  lea     rbx, [rax+1]
0x180018260  mov     dword ptr [rsp+1D0h+pExceptionObject], 0E6h
0x180018268  mov     r9d, 5
0x18001826e  test    rbx, rbx
0x180018271  jz      loc_180018DB6
0x180018277  mov     rax, rsi
0x18001827a  inc     rax
0x18001827d  cmp     [rbx+rax], r14b
0x180018281  jnz     short loc_18001827A
0x180018283  inc     eax
0x180018285  lea     rdx, WlidSvc_TraceFunction_Enter
0x18001828c  mov     [rbp+0D0h+var_78], eax
0x18001828f  lea     rax, aCidentitytoken_11; "CIdentityTokenBag::RetrieveToken"
0x180018296  mov     [rbp+0D0h+var_70], rax
0x18001829a  lea     rax, [rsp+1D0h+pExceptionObject]
0x18001829f  mov     [rbp+0D0h+var_60], rax
0x1800182a3  lea     rax, aNull_2; "NULL"
0x1800182aa  mov     [rbp+0D0h+var_50], rax
0x1800182b1  lea     rax, [rbp+0D0h+var_90]
0x1800182b5  mov     [rsp+1D0h+var_1B0], rax
0x1800182ba  mov     [rbp+0D0h+var_80], rbx
0x1800182be  mov     [rbp+0D0h+var_74], r14d
0x1800182c2  mov     [rbp+0D0h+var_68], 21h ; '!'
0x1800182ca  mov     [rbp+0D0h+var_58], r15
0x1800182ce  mov     [rbp+0D0h+var_48], 0Ah
0x1800182d9  call    McGenEventWrite_EventWriteTransfer
0x1800182de  nop
0x1800182df  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800182e6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800182ed  mov     rax, [rax+18h]
0x1800182f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182f6  lea     rbx, [rax+18h]
0x1800182fa  mov     [rsp+1D0h+var_190], rbx
0x1800182ff  lea     rcx, [rsp+1D0h+var_180]; this
0x180018304  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x180018309  mov     [rbp+0D0h+var_D8], 1
0x18001830d  lea     rax, [r12+10h]
0x180018312  mov     [rbp+0D0h+lpCriticalSection], rax
0x180018316  mov     rcx, rax; lpCriticalSection
0x180018319  call    cs:__imp_EnterCriticalSection
0x18001831f  mov     [rbp+0D0h+var_C8], 1
0x180018323  mov     rax, [r13+0]
0x180018327  movsxd  rsi, dword ptr [rax-10h]
0x18001832b  test    esi, esi
0x18001832d  jz      loc_180018881
0x180018333  mov     ecx, 1
0x180018338  sub     ecx, [rax-8]
0x18001833b  mov     eax, [rax-0Ch]
0x18001833e  sub     eax, esi
0x180018340  or      ecx, eax
0x180018342  jge     short loc_18001834F
0x180018344  mov     edx, esi
0x180018346  mov     rcx, r13
0x180018349  call    ?PrepareWrite2@?$CSimpleStringT@D$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite2(int)
0x18001834e  nop
0x18001834f  lea     eax, [rsi+1]
0x180018352  movsxd  rdx, eax
0x180018355  mov     rcx, [r13+0]
0x180018359  call    cs:__imp__o__mbslwr_s
0x18001835f  mov     ecx, eax; int
0x180018361  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180018366  nop
0x180018367  test    esi, esi
0x180018369  js      loc_180018DCF
0x18001836f  mov     rax, [r13+0]
0x180018373  cmp     esi, [rax-0Ch]
0x180018376  jg      loc_180018DCF
0x18001837c  mov     [rax-10h], esi
0x18001837f  mov     rax, [r13+0]
0x180018383  mov     [rsi+rax], r14b
0x180018387  mov     r15, [r13+0]
0x18001838b  test    r15, r15
0x18001838e  jz      loc_180018876
0x180018394  mov     al, [r15]
0x180018397  test    al, al
0x180018399  jz      short loc_1800183B1
0x18001839b  mov     rcx, r15
0x18001839e  imul    r14d, 21h ; '!'
0x1800183a2  movsx   eax, al
0x1800183a5  add     r14d, eax
0x1800183a8  inc     rcx
0x1800183ab  mov     al, [rcx]
0x1800183ad  test    al, al
0x1800183af  jnz     short loc_18001839E
0x1800183b1  mov     rsi, [r12+38h]
0x1800183b6  test    rsi, rsi
0x1800183b9  jz      short loc_1800183F4
0x1800183bb  xor     edx, edx
0x1800183bd  mov     eax, r14d
0x1800183c0  div     dword ptr [r12+48h]
0x1800183c5  mov     rsi, [rsi+rdx*8]
0x1800183c9  test    rsi, rsi
0x1800183cc  jz      short loc_1800183F4
0x1800183ce  cmp     [rsi+0C0h], r14d
0x1800183d5  jnz     short loc_1800183EB
0x1800183d7  mov     rdx, r15
0x1800183da  mov     rcx, [rsi]
0x1800183dd  call    cs:__imp__o__mbscmp
0x1800183e3  test    eax, eax
0x1800183e5  jz      loc_180018974
0x1800183eb  mov     rsi, [rsi+0B8h]
0x1800183f2  jmp     short loc_1800183C9
0x1800183f4  xor     r14d, r14d
0x1800183f7  mov     esi, r14d
0x1800183fa  test    rsi, rsi
0x1800183fd  jz      loc_180018881
0x180018403  mov     eax, [rsi+8]
0x180018406  mov     [rsp+1D0h+var_180], eax
0x18001840a  lea     rdx, [rsi+10h]
0x18001840e  lea     rcx, [rsp+1D0h+var_178]
0x180018413  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180018418  lea     rdx, [rsi+18h]
0x18001841c  lea     rcx, [rsp+1D0h+var_170]
0x180018421  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180018426  mov     eax, [rsi+20h]
0x180018429  mov     [rsp+1D0h+var_168], eax
0x18001842d  mov     rax, [rsi+28h]
0x180018431  mov     [rsp+1D0h+var_160], rax
0x180018436  mov     eax, [rsi+30h]
0x180018439  mov     [rsp+1D0h+var_158], eax
0x18001843d  mov     rax, [rsi+38h]
0x180018441  mov     [rbp+0D0h+var_150], rax
0x180018445  mov     rax, [rsi+40h]
0x180018449  mov     [rbp+0D0h+var_148], rax
0x18001844d  mov     rax, [rsi+48h]
0x180018451  mov     [rbp+0D0h+var_140], rax
0x180018455  mov     rax, [rsi+50h]
0x180018459  mov     [rbp+0D0h+var_138], rax
0x18001845d  lea     rdx, [rsi+58h]
0x180018461  lea     rcx, [rbp+0D0h+var_130]
0x180018465  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18001846a  lea     rdx, [rsi+60h]
0x18001846e  lea     rcx, [rbp+0D0h+var_128]
0x180018472  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180018477  mov     eax, [rsi+68h]
0x18001847a  mov     [rbp+0D0h+var_120], eax
0x18001847d  mov     eax, [rsi+6Ch]
0x180018480  mov     [rbp+0D0h+var_11C], eax
0x180018483  lea     rdx, [rsi+70h]
0x180018487  lea     rcx, [rbp+0D0h+var_118]
0x18001848b  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180018490  lea     rdx, [rsi+78h]
0x180018494  lea     rcx, [rbp+0D0h+var_110]
0x180018498  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18001849d  lea     rdx, [rsi+80h]
0x1800184a4  lea     rcx, [rbp+0D0h+var_108]
0x1800184a8  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800184ad  lea     rdx, [rsi+88h]
0x1800184b4  lea     rcx, [rbp+0D0h+var_100]
0x1800184b8  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800184bd  xor     r9d, r9d; bool
0x1800184c0  mov     r8d, [rsi+90h]; unsigned int
0x1800184c7  mov     rdx, [rsi+98h]; unsigned __int8 *
0x1800184ce  lea     rcx, [rbp+0D0h+uBytes]; this
0x1800184d2  call    ?Attach@CBytePtr@@QEAAXPEAEK_N@Z; CBytePtr::Attach(uchar *,ulong,bool)
0x1800184d7  lea     rdx, [rsi+0A8h]
0x1800184de  lea     rcx, [rbp+0D0h+hProv]
0x1800184e2  call    ??4CCryptProv@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CCryptProv::operator=(ATL::CCryptProv const &)
0x1800184e7  mov     al, [rsi+0B0h]
0x1800184ed  mov     [rbp+0D0h+var_D8], al
0x1800184f0  mov     eax, [rsp+1D0h+var_180]
0x1800184f4  mov     [rdi], eax
0x1800184f6  lea     r15, [rdi+8]
0x1800184fa  mov     [rsp+1D0h+pExceptionObject], r15
0x1800184ff  mov     rdx, [rsp+1D0h+var_178]
0x180018504  lea     rcx, [rdx-18h]
0x180018508  mov     rsi, [r15]
0x18001850b  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001850f  cmp     rcx, rsi
0x180018512  jz      short loc_180018558
0x180018514  cmp     [rsi+10h], r14d
0x180018518  jl      loc_180018AF0
0x18001851e  mov     rax, [rsi]
0x180018521  cmp     [rcx], rax
0x180018524  jnz     loc_180018AF0
0x18001852a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001852f  mov     r14, rax
0x180018532  or      ecx, 0FFFFFFFFh
0x180018535  lock xadd [rsi+10h], ecx
0x18001853a  sub     ecx, 1
0x18001853d  jg      short loc_180018551
0x18001853f  mov     rcx, [rsi]
0x180018542  mov     r8, [rcx]
0x180018545  mov     rdx, rsi
0x180018548  mov     rax, [r8+8]
0x18001854c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018551  lea     rax, [r14+18h]
0x180018555  mov     [r15], rax
0x180018558  lea     r14, [rdi+10h]
0x18001855c  mov     rdx, [rsp+1D0h+var_170]
0x180018561  lea     rcx, [rdx-18h]
0x180018565  mov     rsi, [r14]
0x180018568  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001856c  cmp     rcx, rsi
0x18001856f  jz      short loc_1800185B5
0x180018571  cmp     dword ptr [rsi+10h], 0
0x180018575  jl      loc_180018B01
0x18001857b  mov     rax, [rsi]
0x18001857e  cmp     [rcx], rax
0x180018581  jnz     loc_180018B01
0x180018587  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001858c  mov     r15, rax
0x18001858f  or      ecx, 0FFFFFFFFh
0x180018592  lock xadd [rsi+10h], ecx
0x180018597  sub     ecx, 1
0x18001859a  jg      short loc_1800185AE
0x18001859c  mov     rcx, [rsi]
0x18001859f  mov     r8, [rcx]
0x1800185a2  mov     rdx, rsi
0x1800185a5  mov     rax, [r8+8]
0x1800185a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185ae  lea     rax, [r15+18h]
0x1800185b2  mov     [r14], rax
0x1800185b5  mov     eax, [rsp+1D0h+var_168]
0x1800185b9  mov     [rdi+18h], eax
0x1800185bc  mov     rax, [rsp+1D0h+var_160]
0x1800185c1  mov     [rdi+20h], rax
0x1800185c5  mov     eax, [rsp+1D0h+var_158]
0x1800185c9  mov     [rdi+28h], eax
0x1800185cc  mov     rax, [rbp+0D0h+var_150]
0x1800185d0  mov     [rdi+30h], rax
0x1800185d4  mov     rax, [rbp+0D0h+var_148]
0x1800185d8  mov     [rdi+38h], rax
0x1800185dc  mov     rax, [rbp+0D0h+var_140]
0x1800185e0  mov     [rdi+40h], rax
0x1800185e4  mov     rax, [rbp+0D0h+var_138]
0x1800185e8  mov     [rdi+48h], rax
0x1800185ec  lea     r14, [rdi+50h]
0x1800185f0  mov     rdx, [rbp+0D0h+var_130]
0x1800185f4  lea     rcx, [rdx-18h]
0x1800185f8  mov     rsi, [r14]
0x1800185fb  add     rsi, 0FFFFFFFFFFFFFFE8h
0x1800185ff  cmp     rcx, rsi
0x180018602  jz      short loc_180018648
0x180018604  cmp     dword ptr [rsi+10h], 0
0x180018608  jl      loc_180018B12
0x18001860e  mov     rax, [rsi]
0x180018611  cmp     [rcx], rax
0x180018614  jnz     loc_180018B12
0x18001861a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001861f  mov     r15, rax
0x180018622  or      ecx, 0FFFFFFFFh
0x180018625  lock xadd [rsi+10h], ecx
0x18001862a  sub     ecx, 1
0x18001862d  jg      short loc_180018641
0x18001862f  mov     rcx, [rsi]
0x180018632  mov     r8, [rcx]
0x180018635  mov     rdx, rsi
0x180018638  mov     rax, [r8+8]
0x18001863c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018641  lea     rax, [r15+18h]
0x180018645  mov     [r14], rax
0x180018648  lea     r14, [rdi+58h]
0x18001864c  mov     rdx, [rbp+0D0h+var_128]
0x180018650  lea     rcx, [rdx-18h]
0x180018654  mov     rsi, [r14]
0x180018657  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001865b  cmp     rcx, rsi
0x18001865e  jz      short loc_1800186A4
0x180018660  cmp     dword ptr [rsi+10h], 0
0x180018664  jl      loc_180018B23
0x18001866a  mov     rax, [rsi]
  ... truncated ...
```
