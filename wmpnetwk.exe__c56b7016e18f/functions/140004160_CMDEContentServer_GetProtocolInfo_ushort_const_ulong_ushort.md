# CMDEContentServer::GetProtocolInfo(ushort const *,ulong,ushort * *)

- ea: `0x140004160`
- end: `0x140004ad7`
- name: `?GetProtocolInfo@CMDEContentServer@@UEAAJPEBGKPEAPEAG@Z`
- size: `2423`
- prototype: `__int64 __fastcall(CMDEContentServer *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `32`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002fd8`
- `0x140003610`
- `0x140003690`
- `0x140004160`
- `0x1400065e0`
- `0x140006d70`
- `0x140007388`
- `0x140009a40`
- `0x14000b3f0`
- `0x14000c780`
- `0x14000c920`
- `0x14000dc4c`
- `0x140013a20`
- `0x140015100`
- `0x140015230`
- `0x140018df0`
- `0x140019af8`
- `0x14001b560`
- `0x14001b620`
- `0x14001d520`
- `0x140023eb0`
- `0x1400396dc`
- `0x14003b610`
- `0x14003e5f4`
- `0x140046c32`
- `0x140046d00`
- `0x140047798`
- `0x140054490`
- `0x140054534`
- `0x140063700`
- `0x14009ad10`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400041ac`
- `KERNEL32!EnterCriticalSection` at `0x1400041ac`
- `KERNEL32!LeaveCriticalSection` at `0x140004ab4`
- `KERNEL32!LeaveCriticalSection` at `0x140004ab4`
- `KERNEL32!CompareStringW` at `0x14000439c`
- `KERNEL32!CompareStringW` at `0x140004469`
- `KERNEL32!CompareStringW` at `0x1400044ef`
- `KERNEL32!CompareStringW` at `0x140004517`
- `KERNEL32!CompareStringW` at `0x14000439c`
- `KERNEL32!CompareStringW` at `0x140004469`
- `KERNEL32!CompareStringW` at `0x1400044ef`
- `KERNEL32!CompareStringW` at `0x140004517`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004917`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004917`
- `OLEAUT32!__imp_SysAllocString` at `0x1400049dc`
- `OLEAUT32!__imp_SysAllocString` at `0x1400049dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMDEContentServer::GetProtocolInfo(
        CMDEContentServer *this,
        char *a2,
        char a3,
        unsigned __int16 **a4)
{
  const wchar_t **v4; // rdi
  CMDEContentServer *v7; // r15
  unsigned __int64 v8; // rsi
  PVOID *v9; // r10
  int v10; // ebx
  PVOID *v11; // r10
  int v12; // esi
  const WCHAR *v13; // r14
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  __int64 v16; // r13
  _DWORD *v17; // rdi
  __int64 v18; // rbx
  const wchar_t *v19; // rdx
  PCNZWCH *v20; // r15
  __int64 v21; // r8
  _QWORD *v22; // rax
  __int64 v23; // rdi
  ATL::CStringData *v24; // r13
  __int64 v25; // rdi
  int *v26; // rcx
  __int64 v27; // rdi
  __int64 v28; // r8
  __int64 v29; // rdi
  _QWORD *v30; // rax
  const OLECHAR *v31; // rdi
  unsigned int i; // eax
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // r15
  __int64 v36; // rdx
  const OLECHAR *v37; // rbx
  int v38; // r8d
  const OLECHAR *v39; // rdx
  unsigned __int64 v40; // r13
  int v41; // r12d
  size_t v42; // r8
  OLECHAR *v43; // rcx
  unsigned __int16 *v44; // rax
  const wchar_t *v45; // rax
  const OLECHAR *v47; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v49; // [rsp+48h] [rbp-C0h]
  int v50; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v51; // [rsp+50h] [rbp-B8h] BYREF
  PCNZWCH lpString1; // [rsp+58h] [rbp-B0h] BYREF
  char *v53; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+68h] [rbp-A0h] BYREF
  const OLECHAR *v55; // [rsp+70h] [rbp-98h] BYREF
  __int64 v56; // [rsp+78h] [rbp-90h] BYREF
  __int64 v57; // [rsp+80h] [rbp-88h]
  unsigned int v58; // [rsp+88h] [rbp-80h]
  int v59; // [rsp+8Ch] [rbp-7Ch]
  int v60; // [rsp+90h] [rbp-78h]
  int v61; // [rsp+94h] [rbp-74h]
  __int64 v62; // [rsp+98h] [rbp-70h]
  __int64 v63; // [rsp+A0h] [rbp-68h]
  int v64; // [rsp+A8h] [rbp-60h]
  int v65; // [rsp+ACh] [rbp-5Ch]
  __int64 v66; // [rsp+B0h] [rbp-58h]
  __int64 v67; // [rsp+B8h] [rbp-50h]
  __int64 v68; // [rsp+C8h] [rbp-40h] BYREF
  ATL::CStringData *v69; // [rsp+D0h] [rbp-38h]
  _QWORD *v70; // [rsp+D8h] [rbp-30h]
  char v71[8]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v72[13]; // [rsp+F0h] [rbp-18h] BYREF
  int v74; // [rsp+168h] [rbp+60h]

  v4 = (const wchar_t **)a4;
  v7 = this;
  v8 = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
  v55 = (const OLECHAR *)v8;
  if ( v8 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SDq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      109,
      (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (_DWORD)a2,
      a3,
      (char)v4);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v4 )
  {
    v10 = -2147024809;
    goto LABEL_104;
  }
  v56 = 0;
  v57 = 0;
  v58 = 17;
  v62 = 0xFFFFFFFFLL;
  v63 = 0;
  v64 = 0;
  v65 = 10;
  v66 = 0;
  v67 = 0;
  v59 = 1061158912;
  v60 = 1048576000;
  v61 = 1074790400;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(&v56);
  v50 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)&v53,
    a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Tokenize(
    &v53,
    &lpString1,
    L",",
    &v50);
  LODWORD(v48) = a3 & 4;
  v49 = a3 & 0x10;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  v12 = v48;
  while ( 1 )
  {
    v13 = lpString1;
    if ( !*lpString1 )
      break;
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      WPP_SF_S(v11[2], 111, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, lpString1);
    v14 = (_QWORD *)*((_QWORD *)v7 + 19);
    if ( v14 )
    {
      do
      {
        v15 = (_QWORD *)*v14;
        v70 = (_QWORD *)*v14;
        v16 = v14[2];
        v17 = (_DWORD *)(v16 + 56);
        if ( !*((_DWORD *)v7 + 112) && *v17 == 1 )
          goto LABEL_65;
        if ( *v17 )
        {
          if ( *v17 != 1
            || (a3 & 2) != 0
            && ((a3 & 0x40) == 0 || CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v16 + 32), 6, L"video/", -1) != 2) )
          {
            goto LABEL_65;
          }
        }
        else if ( (a3 & 1) != 0 )
        {
          goto LABEL_65;
        }
        if ( (unsigned int)CMDEContentServer::ProfileMatchesMIME((const struct MDEProfile *)v16, v13) )
        {
          v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
          v47 = (const OLECHAR *)v18;
          if ( *v17 )
          {
            if ( *v17 == 1 )
            {
              v19 = L"rtsp-rtp-udp";
              goto LABEL_34;
            }
          }
          else
          {
            v19 = (const wchar_t *)L"http-get";
LABEL_34:
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v47, v19);
            v18 = (__int64)v47;
          }
          v69 = (ATL::CStringData *)ATL::CSimpleStringT<unsigned short,0>::CloneData(v13 - 12);
          v48 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
          CDlnaContentFeaturesWriter::CDlnaContentFeaturesWriter(
            (CDlnaContentFeaturesWriter *)v71,
            (const struct MDEProfile *)v16,
            0);
          v20 = (PCNZWCH *)(v16 + 32);
          if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v16 + 32), -1, L"application/octet-stream", -1) == 2
            || !*((_DWORD *)*v20 - 4) )
          {
            v26 = (int *)(*(_QWORD *)v71 - 24LL);
            if ( *(_DWORD *)(*(_QWORD *)v71 - 24LL + 8) )
            {
              if ( v26[4] >= 0 )
              {
                v27 = *(_QWORD *)v26;
                ATL::CStringData::Release((ATL::CStringData *)v26);
                *(_QWORD *)v71 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27) + 24;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetLength(v71, 0);
              }
            }
            ATL::CSimpleStringT<unsigned short,0>::operator=(v72, &lpString1);
            LOBYTE(v28) = 1;
            CDlnaContentFeaturesWriter::ToString((size_t)v71, &v48, v28, v12 != 0, (a3 & 8) != 0);
            v47 = (const OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
              &v47,
              L"%ls:*:%ls:%ls",
              v18,
              v13,
              v48);
            v29 = (__int64)v47;
            ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::SetAt(
              &v56,
              v47);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, v29);
            }
            if ( !v12 )
              CMDEContentServer::AddDLNAProtocolInfoForGetProtocolInfo(v13, v71, a3, v18, (__int64)&v56);
            v24 = (ATL::CStringData *)(v29 - 24);
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::operator=(v71, (_QWORD *)(v16 + 40));
            LOBYTE(v21) = 1;
            CDlnaContentFeaturesWriter::ToString((size_t)v71, &v48, v21, v12 != 0, (a3 & 8) != 0);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
              &v51,
              (const void **)(v16 + 32));
            if ( v49
              && (CompareStringW(0x7Fu, 1u, *v20, 10, L"audio/L16;", -1) == 2
               || CompareStringW(0x7Fu, 1u, *v20, 9, L"audio/L8;", -1) == 2)
              && (v22 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
                                    v20,
                                    &v68,
                                    L";"),
                  ATL::CSimpleStringT<unsigned short,0>::operator=(&v51, v22),
                  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v68),
                  WPP_GLOBAL_Control != &WPP_GLOBAL_Control)
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v23 = v51;
              WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v51);
            }
            else
            {
              v23 = v51;
            }
            v24 = (ATL::CStringData *)(v23 - 24);
            if ( *(_DWORD *)(v23 - 24 + 8) )
            {
              v47 = (const OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
                &v47,
                L"%ls:*:%ls:%ls",
                v18,
                v23,
                v48);
              v25 = (__int64)v47;
              ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::SetAt(
                &v56,
                v47);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  114,
                  &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
                  v25);
              }
              ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
            }
            if ( !v12 )
              CMDEContentServer::AddDLNAProtocolInfoForGetProtocolInfo(*v20, v71, a3, v18, (__int64)&v56);
          }
          ATL::CStringData::Release(v24);
          CDlnaContentFeaturesWriter::~CDlnaContentFeaturesWriter((CDlnaContentFeaturesWriter *)v71);
          ATL::CStringData::Release((ATL::CStringData *)(v48 - 24));
          ATL::CStringData::Release(v69);
          ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
          v7 = this;
          v15 = v70;
        }
LABEL_65:
        v14 = v15;
      }
      while ( v15 );
    }
    v30 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Tokenize(
                      &v53,
                      &v54,
                      L",",
                      &v50);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&lpString1, v30);
    ATL::CStringData::Release((ATL::CStringData *)(v54 - 24));
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  v31 = (const OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v47 = v31;
  v8 = (unsigned __int64)v55;
  if ( v57 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= v58 )
        goto LABEL_98;
      if ( *(_QWORD *)(v56 + 8LL * i) )
        break;
    }
    _mm_lfence();
    v33 = v56;
    v34 = *(_QWORD *)(v56 + 8LL * i);
    if ( v34 )
    {
      while ( 1 )
      {
        v35 = *(_QWORD *)(v34 + 16);
        if ( !v35 )
        {
          LODWORD(v36) = *(_DWORD *)(v34 + 24) % v58;
          do
          {
            v36 = (unsigned int)(v36 + 1);
            v35 = 0;
            if ( (unsigned int)v36 >= v58 )
              break;
            v35 = *(_QWORD *)(v33 + 8 * v36);
          }
          while ( !v35 );
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
          &v55,
          (const void **)v34);
        v37 = v55;
        v38 = *((_DWORD *)v55 - 4);
        v74 = v38;
        v39 = v55;
        v40 = v55 - v31;
        v49 = *((_DWORD *)v31 - 4);
        v41 = v49 + v38;
        if ( (((*((_DWORD *)v31 - 3) - (v49 + v38)) | (1 - *((_DWORD *)v31 - 2))) & 0x80000000) != 0 )
        {
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v47, (unsigned int)v41);
          v31 = v47;
          v39 = v37;
          v38 = v74;
        }
        if ( v40 <= v49 )
          v39 = &v31[v40];
        v42 = 2LL * v38;
        if ( v42 )
        {
          v43 = (OLECHAR *)&v31[v49];
          if ( v43 )
          {
            if ( v39 )
            {
              memcpy_0(v43, v39, v42);
              goto LABEL_87;
            }
            memset_0(v43, 0, v42);
          }
          *(_DWORD *)_o__errno(v43, v39, v42) = 22;
          invalid_parameter_noinfo();
        }
LABEL_87:
        if ( v41 < 0 || v41 > *((_DWORD *)v31 - 3) )
          ATL::AtlThrowImpl(-2147024809);
        *((_DWORD *)v31 - 4) = v41;
        v31[v41] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, v37);
        }
        if ( v35 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&v47, L",");
          v31 = v47;
        }
        ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
        if ( !v35 )
          break;
        v34 = v35;
        v33 = v56;
      }
    }
  }
LABEL_98:
  v10 = 0;
  v44 = SysAllocString(v31);
  *a4 = v44;
  if ( !v44 )
  {
    v10 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, v31);
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v31 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v53 - 24));
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::RemoveAll(&v56);
  v9 = (PVOID *)WPP_GLOBAL_Control;
  v4 = (const wchar_t **)a4;
LABEL_104:
  if ( v9 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v9 + 28) & 1) != 0
    && *((unsigned __int8 *)v9 + 25) >= ((v10 >> 31) & 0xFFFFFFFD) + 5 )
  {
    if ( v4 )
      v45 = *v4;
    else
      v45 = L"<NULL>";
    WPP_SF_dS(
      (unsigned int)v9[2],
      117,
      (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      v10,
      (__int64)v45);
  }
  if ( v8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140004160  mov     rax, rsp
0x140004163  mov     [rax+10h], rbx
0x140004167  mov     [rax+20h], r9
0x14000416b  mov     [rax+8], rcx
0x14000416f  push    rbp
0x140004170  push    rsi
0x140004171  push    rdi
0x140004172  push    r12
0x140004174  push    r13
0x140004176  push    r14
0x140004178  push    r15
0x14000417a  lea     rbp, [rax-58h]
0x14000417e  sub     rsp, 120h
0x140004185  mov     rdi, r9
0x140004188  mov     r12d, r8d
0x14000418b  mov     rbx, rdx
0x14000418e  mov     r15, rcx
0x140004191  mov     rax, rcx
0x140004194  lea     r10, [rcx+8]
0x140004198  neg     rax
0x14000419b  sbb     rsi, rsi
0x14000419e  and     rsi, r10
0x1400041a1  mov     [rsp+150h+var_E8], rsi
0x1400041a6  jz      short loc_1400041B2
0x1400041a8  lea     rcx, [rsi+8]; lpCriticalSection
0x1400041ac  call    cs:__imp_EnterCriticalSection
0x1400041b2  lea     r14, WPP_GLOBAL_Control
0x1400041b9  mov     r10, cs:WPP_GLOBAL_Control
0x1400041c0  cmp     r10, r14
0x1400041c3  jz      short loc_1400041FC
0x1400041c5  test    byte ptr [r10+1Ch], 1
0x1400041ca  jz      short loc_1400041FC
0x1400041cc  cmp     byte ptr [r10+19h], 5
0x1400041d1  jb      short loc_1400041FC
0x1400041d3  mov     edx, 6Dh ; 'm'
0x1400041d8  mov     qword ptr [rsp+150h+cchCount2], rdi
0x1400041dd  mov     dword ptr [rsp+150h+lpString2], r12d
0x1400041e2  mov     r9, rbx
0x1400041e5  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x1400041ec  mov     rcx, [r10+10h]
0x1400041f0  call    WPP_SF_SDq
0x1400041f5  mov     r10, cs:WPP_GLOBAL_Control
0x1400041fc  xor     r13d, r13d
0x1400041ff  test    rdi, rdi
0x140004202  jnz     short loc_14000420E
0x140004204  mov     ebx, 80070057h
0x140004209  jmp     loc_140004A5D
0x14000420e  mov     [rsp+150h+var_E0], r13
0x140004213  mov     [rsp+150h+var_D8], r13
0x140004218  mov     [rbp+50h+var_D0], 11h
0x14000421f  mov     eax, 0FFFFFFFFh
0x140004224  mov     [rbp+50h+var_C0], rax
0x140004228  mov     [rbp+50h+var_B8], r13
0x14000422c  mov     [rbp+50h+var_B0], r13d
0x140004230  mov     [rbp+50h+var_AC], 0Ah
0x140004237  mov     [rbp+50h+var_A8], r13
0x14000423b  mov     [rbp+50h+var_A0], r13
0x14000423f  mov     [rbp+50h+var_CC], 3F400000h
0x140004246  mov     [rbp+50h+var_C8], 3E800000h
0x14000424d  mov     [rbp+50h+var_C4], 40100000h
0x140004254  lea     rcx, [rsp+150h+var_E0]
0x140004259  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CComPtr@UIWMCContentProvider@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CComPtr@UIWMCContentProvider@@@ATL@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(void)
0x14000425e  nop
0x14000425f  mov     dword ptr [rsp+150h+var_110+4], r13d
0x140004264  mov     rdx, rbx
0x140004267  lea     rcx, [rsp+150h+var_F8]
0x14000426c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140004271  lea     r9, [rsp+150h+var_110+4]
0x140004276  lea     r8, asc_1400A3E98; ","
0x14000427d  lea     rdx, [rsp+150h+lpString1]
0x140004282  lea     rcx, [rsp+150h+var_F8]
0x140004287  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Tokenize(ushort const *,int &)
0x14000428c  mov     eax, r12d
0x14000428f  and     eax, 4
0x140004292  mov     [rsp+150h+var_118], eax
0x140004296  mov     eax, r12d
0x140004299  and     eax, 10h
0x14000429c  mov     dword ptr [rsp+150h+var_110], eax
0x1400042a0  mov     r10, cs:WPP_GLOBAL_Control
0x1400042a7  cmp     r10, r14
0x1400042aa  jz      short loc_1400042D6
0x1400042ac  test    byte ptr [r10+1Ch], 2
0x1400042b1  jz      short loc_1400042D6
0x1400042b3  cmp     byte ptr [r10+19h], 5
0x1400042b8  jb      short loc_1400042D6
0x1400042ba  mov     edx, 6Eh ; 'n'
0x1400042bf  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x1400042c6  mov     rcx, [r10+10h]
0x1400042ca  call    WPP_SF_
0x1400042cf  mov     r10, cs:WPP_GLOBAL_Control
0x1400042d6  mov     esi, [rsp+150h+var_118]
0x1400042da  lea     rbx, WPP_GLOBAL_Control
0x1400042e1  mov     r14, [rsp+150h+lpString1]
0x1400042e6  cmp     [r14], r13w
0x1400042ea  jz      loc_140004814
0x1400042f0  cmp     r10, rbx
0x1400042f3  jz      short loc_14000431B
0x1400042f5  test    byte ptr [r10+1Ch], 2
0x1400042fa  jz      short loc_14000431B
0x1400042fc  cmp     byte ptr [r10+19h], 5
0x140004301  jb      short loc_14000431B
0x140004303  mov     edx, 6Fh ; 'o'
0x140004308  mov     r9, r14
0x14000430b  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x140004312  mov     rcx, [r10+10h]
0x140004316  call    WPP_SF_S
0x14000431b  mov     rax, [r15+98h]
0x140004322  test    rax, rax
0x140004325  jz      loc_1400047D2
0x14000432b  mov     rbx, [rax]
0x14000432e  mov     [rbp+50h+var_80], rbx
0x140004332  mov     r13, [rax+10h]
0x140004336  lea     rdi, [r13+38h]
0x14000433a  cmp     dword ptr [r15+1C0h], 0
0x140004342  jnz     short loc_14000434D
0x140004344  cmp     dword ptr [rdi], 1
0x140004347  jz      loc_1400047BC
0x14000434d  cmp     dword ptr [rdi], 0
0x140004350  jnz     short loc_14000435E
0x140004352  test    r12b, 1
0x140004356  jnz     loc_1400047BC
0x14000435c  jmp     short loc_1400043AB
0x14000435e  cmp     dword ptr [rdi], 1
0x140004361  jnz     loc_1400047BC
0x140004367  test    r12b, 2
0x14000436b  jz      short loc_1400043AB
0x14000436d  test    r12b, 40h
0x140004371  jz      loc_1400047BC
0x140004377  mov     [rsp+150h+cchCount2], 0FFFFFFFFh; cchCount2
0x14000437f  lea     rax, aVideo; "video/"
0x140004386  mov     [rsp+150h+lpString2], rax; lpString2
0x14000438b  mov     r9d, 6; cchCount1
0x140004391  mov     r8, [r13+20h]; lpString1
0x140004395  lea     edx, [r9-5]; dwCmpFlags
0x140004399  lea     ecx, [rdx+7Eh]; Locale
0x14000439c  call    cs:__imp_CompareStringW
0x1400043a2  cmp     eax, 2
0x1400043a5  jnz     loc_1400047BC
0x1400043ab  mov     rdx, r14; unsigned __int16 *
0x1400043ae  mov     rcx, r13; struct MDEProfile *
0x1400043b1  call    ?ProfileMatchesMIME@CMDEContentServer@@CAHPEBUMDEProfile@@PEBG@Z; CMDEContentServer::ProfileMatchesMIME(MDEProfile const *,ushort const *)
0x1400043b6  test    eax, eax
0x1400043b8  jz      loc_1400047BC
0x1400043be  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400043c5  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400043cc  mov     rax, [rax+18h]
0x1400043d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043d5  lea     rbx, [rax+18h]
0x1400043d9  mov     [rsp+150h+var_120], rbx
0x1400043de  mov     ecx, [rdi]
0x1400043e0  test    ecx, ecx
0x1400043e2  jz      short loc_1400043F2
0x1400043e4  cmp     ecx, 1
0x1400043e7  jnz     short loc_140004408
0x1400043e9  lea     rdx, aRtspRtpUdp; "rtsp-rtp-udp"
0x1400043f0  jmp     short loc_1400043F9
0x1400043f2  lea     rdx, aHttpGet_1; "http-get"
0x1400043f9  lea     rcx, [rsp+150h+var_120]
0x1400043fe  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140004403  mov     rbx, [rsp+150h+var_120]
0x140004408  lea     rcx, [r14-18h]
0x14000440c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140004411  mov     [rbp+50h+var_88], rax
0x140004415  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000441c  mov     rax, [rcx+18h]
0x140004420  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140004427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000442c  add     rax, 18h
0x140004430  mov     qword ptr [rsp+150h+var_118], rax
0x140004435  xor     r8d, r8d; bool
0x140004438  mov     rdx, r13; struct MDEProfile *
0x14000443b  lea     rcx, [rbp+50h+var_70]; this
0x14000443f  call    ??0CDlnaContentFeaturesWriter@@QEAA@PEBUMDEProfile@@_N1@Z; CDlnaContentFeaturesWriter::CDlnaContentFeaturesWriter(MDEProfile const *,bool,bool)
0x140004444  lea     r15, [r13+20h]
0x140004448  or      ecx, 0FFFFFFFFh
0x14000444b  mov     [rsp+150h+cchCount2], ecx; cchCount2
0x14000444f  lea     rax, aApplicationOct; "application/octet-stream"
0x140004456  mov     [rsp+150h+lpString2], rax; lpString2
0x14000445b  mov     r9d, ecx; cchCount1
0x14000445e  mov     r8, [r15]; lpString1
0x140004461  lea     edi, [rcx+2]
0x140004464  mov     edx, edi; dwCmpFlags
0x140004466  lea     ecx, [rdi+7Eh]; Locale
0x140004469  call    cs:__imp_CompareStringW
0x14000446f  cmp     eax, 2
0x140004472  jz      loc_14000465E
0x140004478  mov     rax, [r15]
0x14000447b  cmp     dword ptr [rax-10h], 0
0x14000447f  jz      loc_14000465E
0x140004485  lea     rdx, [r13+28h]
0x140004489  lea     rcx, [rbp+50h+var_70]
0x14000448d  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140004492  mov     eax, r12d
0x140004495  shr     eax, 3
0x140004498  and     al, dil
0x14000449b  test    esi, esi
0x14000449d  setnz   r9b
0x1400044a1  mov     byte ptr [rsp+150h+lpString2], al
0x1400044a5  mov     r8b, dil
0x1400044a8  lea     rdx, [rsp+150h+var_118]
0x1400044ad  lea     rcx, [rbp+50h+var_70]
0x1400044b1  call    ?ToString@CDlnaContentFeaturesWriter@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_N11@Z; CDlnaContentFeaturesWriter::ToString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,bool,bool,bool)
0x1400044b6  mov     rdx, r15
0x1400044b9  lea     rcx, [rsp+150h+var_108]
0x1400044be  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x1400044c3  cmp     dword ptr [rsp+150h+var_110], 0
0x1400044c8  jz      loc_14000458E
0x1400044ce  or      r13d, 0FFFFFFFFh
0x1400044d2  mov     [rsp+150h+cchCount2], r13d; cchCount2
0x1400044d7  lea     rax, aAudioL16_0; "audio/L16;"
0x1400044de  mov     [rsp+150h+lpString2], rax; lpString2
0x1400044e3  lea     r9d, [rdi+9]; cchCount1
0x1400044e7  mov     r8, [r15]; lpString1
0x1400044ea  mov     edx, edi; dwCmpFlags
0x1400044ec  lea     ecx, [rdi+7Eh]; Locale
0x1400044ef  call    cs:__imp_CompareStringW
0x1400044f5  cmp     eax, 2
0x1400044f8  jz      short loc_140004522
0x1400044fa  mov     [rsp+150h+cchCount2], r13d; cchCount2
0x1400044ff  lea     rax, aAudioL8_0; "audio/L8;"
0x140004506  mov     [rsp+150h+lpString2], rax; lpString2
0x14000450b  lea     r9d, [rdi+8]; cchCount1
0x14000450f  mov     r8, [r15]; lpString1
0x140004512  mov     edx, edi; dwCmpFlags
0x140004514  lea     ecx, [rdi+7Eh]; Locale
0x140004517  call    cs:__imp_CompareStringW
0x14000451d  cmp     eax, 2
0x140004520  jnz     short loc_14000458E
0x140004522  lea     r8, asc_1400A3EB0; ";"
0x140004529  lea     rdx, [rbp+50h+var_90]
0x14000452d  mov     rcx, r15
0x140004530  call    ?SpanExcluding@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::SpanExcluding(ushort const *)
0x140004535  mov     rdx, rax
0x140004538  lea     rcx, [rsp+150h+var_108]
0x14000453d  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140004542  lea     rcx, [rbp+50h+var_90]
0x140004546  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14000454b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004552  lea     rax, WPP_GLOBAL_Control
0x140004559  cmp     rcx, rax
0x14000455c  jz      short loc_14000458E
0x14000455e  test    byte ptr [rcx+1Ch], 2
0x140004562  jz      short loc_14000458E
0x140004564  cmp     byte ptr [rcx+19h], 5
0x140004568  jb      short loc_14000458E
0x14000456a  mov     edx, 71h ; 'q'
0x14000456f  mov     rdi, [rsp+150h+var_108]
0x140004574  mov     [rsp+150h+lpString2], rdi; __int64
0x140004579  mov     r9, [r15]
0x14000457c  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x140004583  mov     rcx, [rcx+10h]; LoggerHandle
0x140004587  call    WPP_SF_SS
0x14000458c  jmp     short loc_140004593
0x14000458e  mov     rdi, [rsp+150h+var_108]
0x140004593  lea     r13, [rdi-18h]
0x140004597  cmp     dword ptr [r13+8], 0
0x14000459c  jz      loc_140004635
0x1400045a2  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400045a9  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400045b0  mov     rax, [rax+18h]
0x1400045b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045b9  add     rax, 18h
0x1400045bd  mov     [rsp+150h+var_120], rax
0x1400045c2  mov     rax, qword ptr [rsp+150h+var_118]
0x1400045c7  mov     [rsp+150h+lpString2], rax
0x1400045cc  mov     r9, rdi
0x1400045cf  mov     r8, rbx
0x1400045d2  lea     rdx, aLsLsLs; "%ls:*:%ls:%ls"
0x1400045d9  lea     rcx, [rsp+150h+var_120]
0x1400045de  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x1400045e3  mov     rdi, [rsp+150h+var_120]
0x1400045e8  mov     rdx, rdi
0x1400045eb  lea     rcx, [rsp+150h+var_E0]
0x1400045f0  call    ?SetAt@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@EV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@E@2@@ATL@@QEAAPEAU__POSITION@@PEBGE@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,uchar,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<uchar>>::SetAt(ushort const *,uchar)
0x1400045f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045fc  lea     rax, WPP_GLOBAL_Control
0x140004603  cmp     rcx, rax
0x140004606  jz      short loc_14000462C
0x140004608  test    byte ptr [rcx+1Ch], 2
0x14000460c  jz      short loc_14000462C
0x14000460e  cmp     byte ptr [rcx+19h], 5
0x140004612  jb      short loc_14000462C
0x140004614  mov     edx, 72h ; 'r'
0x140004619  mov     r9, rdi
0x14000461c  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x140004623  mov     rcx, [rcx+10h]
0x140004627  call    WPP_SF_S
0x14000462c  lea     rcx, [rdi-18h]; this
0x140004630  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140004635  test    esi, esi
0x140004637  jnz     loc_140004783
0x14000463d  lea     rax, [rsp+150h+var_E0]
0x140004642  mov     [rsp+150h+lpString2], rax; __int64
0x140004647  mov     r9, rbx
0x14000464a  mov     r8d, r12d
0x14000464d  lea     rdx, [rbp+50h+var_70]; char
0x140004651  mov     rcx, [r15]; lpString1
0x140004654  call    ?AddDLNAProtocolInfoForGetProtocolInfo@CMDEContentServer@@CAXPEBGPEAVCDlnaContentFeaturesWriter@@K0AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@EV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@E@2@@ATL@@@Z; CMDEContentServer::AddDLNAProtocolInfoForGetProtocolInfo(ushort const *,CDlnaContentFeaturesWriter *,ulong,ushort const *,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,uchar,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<uchar>> &)
0x140004659  jmp     loc_140004783
0x14000465e  mov     rcx, qword ptr [rbp+50h+var_70]
  ... truncated ...
```
