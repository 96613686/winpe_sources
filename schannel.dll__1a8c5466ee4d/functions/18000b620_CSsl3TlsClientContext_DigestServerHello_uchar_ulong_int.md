# CSsl3TlsClientContext::DigestServerHello(uchar *,ulong,int *)

- ea: `0x18000b620`
- end: `0x18000c605`
- name: `?DigestServerHello@CSsl3TlsClientContext@@AEAAKPEAEKPEAH@Z`
- size: `4069`
- prototype: `__int64 __fastcall(CSsl3TlsClientContext *this, unsigned __int8 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f510`

## callees

- `0x180005fa0`
- `0x180005fe0`
- `0x1800093c0`
- `0x18000b620`
- `0x18000cb90`
- `0x1800165a4`
- `0x180019650`
- `0x18001e7e0`
- `0x1800214f0`
- `0x180021e64`
- `0x180041600`
- `0x180041f00`
- `0x18004bca4`
- `0x180056c68`
- `0x180057c8c`
- `0x1800597b0`
- `0x18005a160`
- `0x18005f1e4`
- `0x180088a48`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c153`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c153`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000c05b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000c1ea`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000c05b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000c1ea`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b812`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b829`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000c34c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b812`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b829`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000c34c`
- `ntdll!RtlReleaseResource` at `0x18000b8c6`
- `ntdll!RtlReleaseResource` at `0x18000b911`
- `ntdll!RtlReleaseResource` at `0x18000bac4`
- `ntdll!RtlReleaseResource` at `0x18000bb39`
- `ntdll!RtlReleaseResource` at `0x18000c095`
- `ntdll!RtlReleaseResource` at `0x18000c33c`
- `ntdll!RtlReleaseResource` at `0x18000c421`
- `ntdll!RtlReleaseResource` at `0x18000b8c6`
- `ntdll!RtlReleaseResource` at `0x18000b911`
- `ntdll!RtlReleaseResource` at `0x18000bac4`
- `ntdll!RtlReleaseResource` at `0x18000bb39`
- `ntdll!RtlReleaseResource` at `0x18000c095`
- `ntdll!RtlReleaseResource` at `0x18000c33c`
- `ntdll!RtlReleaseResource` at `0x18000c421`
- `ntdll!RtlAcquireResourceShared` at `0x18000b943`
- `ntdll!RtlAcquireResourceShared` at `0x18000ba81`
- `ntdll!RtlAcquireResourceShared` at `0x18000b943`
- `ntdll!RtlAcquireResourceShared` at `0x18000ba81`
- `ntdll!RtlInitUnicodeString` at `0x180089d00`
- `ntdll!RtlInitUnicodeString` at `0x180089d0d`
- `ntdll!RtlInitUnicodeString` at `0x180089d00`
- `ntdll!RtlInitUnicodeString` at `0x180089d0d`
- `ncrypt!SslLookupCipherLengths` at `0x18000baff`
- `ncrypt!SslLookupCipherLengths` at `0x18000baff`

## pseudocode

```c
__int64 __fastcall CSsl3TlsClientContext::DigestServerHello(
        CSsl3TlsClientContext *this,
        unsigned __int8 *a2,
        unsigned int a3,
        int *a4)
{
  int v5; // r10d
  __int64 v6; // rcx
  unsigned int v7; // esi
  int v8; // r13d
  bool v9; // zf
  __int64 v10; // r11
  unsigned __int8 *v11; // r12
  __int64 v12; // rcx
  int v13; // edi
  __int64 v14; // r9
  unsigned int v15; // edi
  int v16; // edx
  int v17; // edx
  __int16 v18; // ax
  unsigned int v19; // esi
  __int64 v20; // r14
  __int64 v21; // r15
  unsigned int v22; // eax
  unsigned __int8 *v23; // r8
  __int64 v24; // rcx
  struct CSessionCacheClientItem *v25; // rdi
  int v26; // esi
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  unsigned int v30; // eax
  unsigned __int8 *v31; // r8
  __int64 v32; // rcx
  __int64 v33; // r14
  unsigned int v34; // r15d
  __int64 v35; // r12
  unsigned int v36; // r13d
  CMasterCipherInfo *v37; // rax
  __int64 v38; // r9
  unsigned int v39; // r8d
  unsigned int i; // edx
  __int64 *v41; // rdi
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // r14
  __int64 v45; // rsi
  CSslServerKey *v46; // rcx
  __int64 v47; // r15
  unsigned int j; // r8d
  __int64 v49; // rdx
  __int64 v50; // rcx
  unsigned int v51; // esi
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 result; // rax
  __int64 v56; // r9
  __int64 v57; // r8
  __int64 v58; // rdx
  unsigned int v59; // edi
  _DWORD *v60; // rcx
  int v61; // eax
  int v62; // r8d
  __int64 v63; // r8
  unsigned int v64; // eax
  unsigned int v65; // edi
  __int64 v66; // r10
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // r10
  __int64 v70; // r10
  __int64 v71; // r10
  __int64 v72; // r10
  __int64 v73; // rax
  __int64 v74; // rcx
  const WCHAR *v75; // rdx
  const WCHAR *v76; // rdi
  __int64 v77; // rax
  unsigned int v78; // r14d
  __int64 v79; // rdx
  int v80; // edi
  int v81; // r14d
  __int64 v82; // r15
  __int64 v83; // rax
  __int64 v84; // r10
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // rax
  __int64 v88; // r10
  __int64 v89; // r10
  __int64 v90; // r10
  __int64 v91; // r10
  int v92; // eax
  const unsigned __int8 near *const *v93; // rdx
  unsigned int v94; // ecx
  int v95; // eax
  __int64 v96; // rdx
  __int64 v97; // rcx
  size_t v98; // rsi
  __int64 v99; // rax
  CSessionCacheManager *v100; // rcx
  __int64 v101; // rsi
  CCipherMill *v102; // rcx
  __int64 v103; // rdx
  __int64 v104; // r8
  __int64 v105; // [rsp+20h] [rbp-E0h]
  __int64 v106; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v107; // [rsp+70h] [rbp-90h]
  unsigned __int8 v108; // [rsp+71h] [rbp-8Fh]
  struct CSessionCacheClientItem *v109; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  void **v111; // [rsp+90h] [rbp-70h] BYREF
  int v112; // [rsp+98h] [rbp-68h]
  CSsl3TlsClientContext *v113; // [rsp+A0h] [rbp-60h]
  char v114; // [rsp+A8h] [rbp-58h]
  __int64 v115; // [rsp+ACh] [rbp-54h]
  char v116; // [rsp+B8h] [rbp-48h]
  HLOCAL hMem; // [rsp+C0h] [rbp-40h]
  int v118; // [rsp+C8h] [rbp-38h]
  char v119; // [rsp+CCh] [rbp-34h]
  CSsl3TlsClientContext *v120; // [rsp+D0h] [rbp-30h]
  char v121[8]; // [rsp+E0h] [rbp-20h] BYREF
  int v122; // [rsp+E8h] [rbp-18h]
  int v123; // [rsp+ECh] [rbp-14h]
  _BYTE Size[20]; // [rsp+760h] [rbp+660h] BYREF
  _BYTE Buf1[32]; // [rsp+778h] [rbp+678h] BYREF

  *(_QWORD *)&DestinationString.Length = a4;
  *((_BYTE *)this + 2274) = 0;
  if ( a3 < 0x23 )
    goto LABEL_158;
  a4 = (int *)*a2;
  v5 = a2[1];
  *(_OWORD *)((char *)this + 2024) = *(_OWORD *)(a2 + 2);
  *(_OWORD *)((char *)this + 2040) = *(_OWORD *)(a2 + 18);
  v6 = a2[34];
  if ( (unsigned __int8)v6 > 0x20u )
  {
    v96 = 103;
    goto LABEL_159;
  }
  v7 = a3 - 35;
  v8 = a2[34];
  if ( a3 - 35 < (int)v6 + 3 )
  {
LABEL_158:
    v96 = 100;
LABEL_159:
    LOBYTE(a4) = 50;
    CSslContext::SetErrorAndFatalAlert(this, v96, 2148074278LL, a4);
    return 2148074278LL;
  }
  v9 = a2[v6 + 37] == 0;
  v10 = a2[34];
  v11 = a2 + 35;
  *(_QWORD *)Size = v10;
  if ( !v9 )
  {
    LOBYTE(a4) = 30;
    CSslContext::SetErrorAndFatalAlert(this, 104, 2148074278LL, a4);
    return 2148074278LL;
  }
  v12 = *((_QWORD *)this + 13);
  if ( !v12 )
    return 2148074244LL;
  v13 = (_DWORD)a4 << 8;
  v14 = 772;
  v15 = v5 | v13;
  if ( v15 == 771 )
  {
    v16 = 2048;
    goto LABEL_8;
  }
  if ( v15 > 0x302 )
  {
    switch ( v15 )
    {
      case 0x304u:
        v16 = 0x2000;
        goto LABEL_8;
      case 0xFEFDu:
        v16 = 0x80000;
        goto LABEL_8;
      case 0xFEFFu:
        v16 = 0x20000;
        goto LABEL_8;
    }
LABEL_143:
    v16 = 0;
    goto LABEL_8;
  }
  if ( v15 == 770 )
  {
    v16 = 512;
    goto LABEL_8;
  }
  if ( v15 == 2 )
    goto LABEL_143;
  if ( v15 != 768 )
  {
    if ( v15 == 769 )
    {
      v16 = 128;
      goto LABEL_8;
    }
    goto LABEL_143;
  }
  v16 = 32;
LABEL_8:
  v17 = *(_DWORD *)(v12 + 216) & v16;
  if ( !v17 )
  {
    LOBYTE(v14) = 70;
    CSslContext::SetErrorAndFatalAlert(this, 105, 2148074289LL, v14);
    return 2148074289LL;
  }
  v107 = v11[v10];
  v108 = v11[v10 + 1];
  *((_DWORD *)this + 22) = v17;
  if ( (v17 & 0xF0000) != 0 && (v17 & 0x3FFC) != 0 )
  {
    v18 = 0;
  }
  else if ( (v17 & 0xC0000) != 0 )
  {
    v18 = -259;
  }
  else if ( (v17 & 0x30000) != 0 )
  {
    v18 = -257;
  }
  else if ( (v17 & 0x3000) != 0 )
  {
    v18 = 772;
  }
  else if ( (v17 & 0xC00) != 0 )
  {
    v18 = 771;
  }
  else if ( (v17 & 0x300) != 0 )
  {
    v18 = 770;
  }
  else if ( (v17 & 0xC0) != 0 )
  {
    v18 = 769;
  }
  else
  {
    v18 = 0;
    if ( (v17 & 0x30) != 0 )
      v18 = 768;
  }
  v9 = *((_BYTE *)this + 1953) == 0;
  *((_WORD *)this + 17) = v18;
  if ( v9 )
  {
    if ( *((_DWORD *)this + 9) <= v15 || *((_DWORD *)this + 9) < 0x303u )
      goto LABEL_17;
  }
  else if ( *((_DWORD *)this + 9) > 0xFEFDu || *((_DWORD *)this + 9) >= v15 )
  {
    goto LABEL_17;
  }
  v92 = v17;
  if ( (v17 & 0x2000) == 0 )
  {
    v93 = &CSsl3TlsContext::m_rgbTls12Downgrade;
    if ( (v92 & 0x80800) == 0 )
      v93 = &CSsl3TlsContext::m_rgbTls11OrBelowDowngrade;
    if ( RtlCompareMemory((char *)this + 2048, v93, 8u) == 8 )
    {
      LOBYTE(v14) = 47;
      CSslContext::SetErrorAndFatalAlert(this, 105, 2148074248LL, v14);
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids,
          *((unsigned int *)this + 9),
          v15);
      return 2148074248LL;
    }
    v10 = *(_QWORD *)Size;
  }
LABEL_17:
  v19 = v7 - v8 - 3;
  if ( v19 <= 2 )
  {
    *((_BYTE *)this + 2642) = 0;
    goto LABEL_19;
  }
  v62 = v11[v10 + 3] << 8;
  v111 = &CTlsExtClient::`vftable';
  v112 = 0;
  v113 = this;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  hMem = 0;
  v118 = 0;
  v120 = this;
  v119 = *((_BYTE *)this + 2642);
  v63 = v11[v10 + 4] | (unsigned int)v62;
  if ( v19 - 2 < (unsigned int)v63 )
  {
    *((_BYTE *)this + 2642) = 0;
    v111 = &CTlsExt::`vftable';
    goto LABEL_19;
  }
  LOBYTE(v14) = 2;
  v64 = CTlsExt::ParseTlsExtensions(&v111, &v11[v10 + 5], v63, v14);
  v65 = v64;
  if ( !v64 )
  {
    v111 = &CTlsExtClient::`vftable';
    if ( hMem )
    {
      if ( LsaTable )
        (*(void (**)(void))(LsaTable + 48))();
      else
        LocalFree(hMem);
    }
    v111 = &CTlsExt::`vftable';
LABEL_19:
    if ( *((_BYTE *)this + 2274) )
      goto LABEL_20;
    if ( *((_BYTE *)this + 2273) )
    {
      v102 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_221;
      v103 = 52;
    }
    else
    {
      if ( g_fAllowInsecureRenegoServers )
      {
LABEL_20:
        v20 = 314159;
        v21 = -1;
        if ( !CSessionCacheManager::m_pSessionCacheManager )
          goto LABEL_24;
        v22 = 0;
        v23 = *(unsigned __int8 **)(*(_QWORD *)(*((_QWORD *)this + 380) + 160LL) + 264LL);
        if ( !v23 )
        {
LABEL_22:
          v24 = *((_QWORD *)CSessionCacheManager::m_pSessionCacheManager + 4)
              + 152LL * (v22 / *((_DWORD *)CSessionCacheManager::m_pSessionCacheManager + 11));
          if ( v24 )
            RtlAcquireResourceExclusive((PRTL_RESOURCE)(v24 + 48), 1u);
LABEL_24:
          RtlAcquireResourceExclusive((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 380) + 40LL) + 80LL), 1u);
          v25 = (struct CSessionCacheClientItem *)*((_QWORD *)this + 380);
          if ( *((unsigned __int16 *)v25 + 39) > 0x20u )
          {
            v26 = 32;
          }
          else
          {
            v26 = *((unsigned __int16 *)v25 + 39);
            memcpy_0(Buf1, (char *)v25 + 80, *((unsigned __int16 *)v25 + 39));
          }
          if ( !*((_QWORD *)v25 + 4) )
          {
LABEL_27:
            v27 = *((_QWORD *)v25 + 5);
            v28 = *((_DWORD *)this + 22);
            LODWORD(v109) = 0;
            *(_DWORD *)(v27 + 176) = v28;
            if ( v8 )
            {
              v29 = *((_QWORD *)this + 380);
              *(_WORD *)(v29 + 78) = v8;
              if ( v11 )
                memcpy_0((void *)(v29 + 80), v11, *(size_t *)Size);
            }
            goto LABEL_30;
          }
          if ( v26 )
          {
            v9 = v26 == v8;
            v98 = *(_QWORD *)Size;
            if ( v9 && !memcmp_0(Buf1, v11, *(size_t *)Size) )
            {
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids);
              }
              LODWORD(v109) = 1;
              if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
              {
                *((_WORD *)this + 110) |= 1u;
                *((_DWORD *)this + 44) = 1;
              }
              goto LABEL_30;
            }
          }
          else
          {
            v98 = *(_QWORD *)Size;
          }
          v99 = *((_QWORD *)this + 232);
          if ( (v99 & 0x400000) == 0 && (v99 & 0x800000) == 0 )
          {
            v100 = CSessionCacheManager::m_pSessionCacheManager;
            *((_BYTE *)v25 + 76) = 0;
            v101 = *((_QWORD *)this + 380);
            v109 = 0;
            v59 = CSessionCacheManager::CacheRetrieveNewClientItem(
                    v100,
                    *(const unsigned __int16 **)(*(_QWORD *)(v101 + 160) + 264LL),
                    &v109,
                    0);
            if ( v59 )
            {
              RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 380) + 40LL) + 80LL));
              CSessionCacheManager::ReleaseCacheTableLock(
                *((_QWORD *)this + 380),
                *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 380) + 160LL) + 264LL),
                0);
              return v59;
            }
            v25 = v109;
            *(_DWORD *)(*((_QWORD *)v109 + 5) + 176LL) = *(_DWORD *)(*(_QWORD *)(v101 + 160) + 176LL);
            *(_QWORD *)(*((_QWORD *)v25 + 5) + 196LL) = *(_QWORD *)(*(_QWORD *)(v101 + 160) + 196LL);
            *((_QWORD *)v25 + 24) = v101;
            RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 380) + 40LL) + 80LL));
            RtlAcquireResourceExclusive((PRTL_RESOURCE)(*((_QWORD *)v25 + 5) + 80LL), 1u);
            *((_QWORD *)this + 380) = v25;
            *((_QWORD *)this + 14) = v25;
            goto LABEL_27;
          }
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids);
          }
          *((_QWORD *)this + 232) |= 0x1000000uLL;
          LODWORD(v109) = 1;
          if ( v8 )
          {
            *((_WORD *)this + 1350) = v8;
            if ( v11 )
              memcpy_0((char *)this + 2702, v11, v98);
          }
          if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
          {
            *((_WORD *)this + 110) |= 2u;
            *((_DWORD *)this + 44) = 1;
          }
LABEL_30:
          RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 380) + 40LL) + 80LL));
          if ( !CSessionCacheManager::m_pSessionCacheManager )
          {
LABEL_34:
            v33 = *((_QWORD *)this + 13);
            v34 = *((_DWORD *)this + 22);
            v35 = *(_QWORD *)(v33 + 248);
            v36 = *(_DWORD *)(v33 + 240);
            *(_DWORD *)Size = *(_DWORD *)(v33 + 256);
            RtlAcquireResourceShared(&Resource, 1u);
            v37 = xmmword_1800AE5B0;
            if ( (*((_DWORD *)this + 464) & 0x20000000) != 0 )
              v37 = *(&xmmword_1800AE5B0 + 1);
            if ( v37 )
            {
              v38 = *(_QWORD *)v37;
              v39 = *((_DWORD *)v37 + 2);
            }
            else
            {
              v38 = 0;
              v39 = 0;
            }
            for ( i = 0; ; ++i )
            {
              if ( i >= v39 )
                goto LABEL_136;
              v41 = (__int64 *)(v38 + 864LL * i);
              if ( *((_DWORD *)v41 + 7) == (v108 | (v107 << 8)) )
                break;
            }
            if ( !(unsigned __int8)CCipherMill::IsCipherSuiteAllowed(
                                     &g_cCipherMill,
                                     v35,
                                     v36,
                                     *(unsigned int *)Size,
                                     (*(_DWORD *)(v33 + 220) >> 12) & 1,
                                     *(_DWORD *)(v33 + 220) & 0x800,
                                     *(_DWORD *)(v33 + 232),
                                     *(_DWORD *)(v33 + 228),
                                     v34,
                                     v41,
                                     0,
                                     0,
                                     0,
                                     1) )
            {
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_09dceeee5ffe36f0dedb0b1d6c80af61_Traceguids);
              }
LABEL_136:
              RtlReleaseResource(&Resource);
              LogCipherMismatchEvent(*(_DWORD *)(v33 + 276), (const unsigned __int16 *)(v33 + 280), v34);
              v54 = *(_QWORD *)this;
              v51 = -2146893007;
              goto LABEL_93;
            }
            v42 = v41[106];
            if ( v42 )
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v42 + 16) + 12LL));
            _InterlockedIncrement((volatile signed __int32 *)(v41[107] + 12));
            v43 = (*(__int64 (__fastcall **)(CSsl3TlsClientContext *))(*(_QWORD *)this + 264LL))(this);
            v44 = *((_QWORD *)this + 1);
            v45 = v43;
            memset(Size, 0, sizeof(Size));
            if ( v44 )
            {
              v97 = *(_QWORD *)(v44 + 848);
              if ( v97 )
                CMasterEccCurveInfo::Dereference(*(CMasterEccCurveInfo **)(v97 + 16));
              CMasterCipherInfo::Dereference(*(CMasterCipherInfo **)(v44 + 856));
            }
            v46 = (CSslServerKey *)*((_QWORD *)this + 3);
            if ( v46 )
            {
              CSslServerKey::Dereference(v46);
              *((_QWORD *)this + 3) = 0;
            }
            if ( v45 )
            {
              v47 = *v41;
              RtlAcquireResourceShared((PRTL_RESOURCE)(v45 + 552), 1u);
              for ( j = 0; j < *(_DWORD *)(v45 + 96); ++j )
              {
                v49 = 8LL * j;
                v50 = *(_QWORD *)(v49 + *(_QWORD *)(v45 + 88));
                if ( *(_QWORD *)(v50 + 16) == v47 )
                {
                  _InterlockedIncrement((volatile signed __int32 *)(v50 + 24));
                  *((_QWORD *)this + 3) = *(_QWORD *)(v49 + *(_QWORD *)(v45 + 88));
                  break;
                }
              }
              RtlReleaseResource((PRTL_RESOURCE)(v45 + 552));
            }
            if ( (*((_DWORD *)this + 22) & 0xF3F00) != 0 )
            {
              v51 = SslLookupCipherLengths(
                      *v41,
                      *((unsigned __int16 *)this + 17),
                      *((unsigned int *)v41 + 7),
                      *((unsigned int *)this + 4),
                      Size,
                      20,
                      0);
              if ( v51 )
                goto LABEL_58;
            }
            else
            {
              v94 = *((_DWORD *)v41 + 3);
              v51 = 0;
              v95 = *((_DWORD *)v41 + 4);
              *(_QWORD *)Size = 20;
              *(_QWORD *)&Size[12] = 0;
              *(_DWORD *)&Size[8] = v95;
              if ( v94 > 1 )
              {
                *(_DWORD *)&Size[12] = v94;
                *(_DWORD *)&Size[16] = 1;
              }
            }
            if ( (*((_BYTE *)this + 32) & 1) == 0 || RtlCompareMemory(Size, (char *)this + 40, 0x14u) == 20 )
            {
              v52 = *(_DWORD *)&Size[16];
              *(_OWORD *)((char *)this + 40) = *(_OWORD *)Size;
              *((_DWORD *)this + 14) = v52;
            }
            else
            {
              v51 = -2146893007;
            }
LABEL_58:
            *((_WORD *)this + 16) |= 1u;
            *((_QWORD *)this + 1) = v41;
            RtlReleaseResource(&Resource);
            v54 = *(_QWORD *)this;
            if ( !v51 )
            {
              LOBYTE(v53) = (*((_DWORD *)this + 22) & 0x80800) != 0;
              result = (*(__int64 (__fastcall **)(CSsl3TlsClientContext *, __int64))(v54 + 560))(this, v53);
              if ( (_DWORD)result )
                return result;
              v57 = *((unsigned int *)this + 648);
              LOBYTE(v56) = 1;
              v58 = *((_QWORD *)this + 325);
              *((_BYTE *)this + 2060) = 0;
              v59 = (*(__int64 (__fastcall **)(CSsl3TlsClientContext *, __int64, __int64, __int64))(*(_QWORD *)this
                                                                                                  + 568LL))(
                      this,
                      v58,
                      v57,
                      v56);
              if ( *((_QWORD *)this + 325) )
              {
                (*(void (__fastcall **)(CSsl3TlsClientContext *))(*(_QWORD *)this + 16LL))(this);
                *((_QWORD *)this + 325) = 0;
              }
              v60 = *(_DWORD **)&DestinationString.Length;
              v61 = (int)v109;
              *((_DWORD *)this + 648) = 0;
              *v60 = v61;
              return v59;
            }
LABEL_93:
            v73 = (*(__int64 (__fastcall **)(CSsl3TlsClientContext *))(v54 + 352))(this);
            v74 = *((_QWORD *)this + 231);
            if ( !*(_WORD *)(v74 + 34) )
            {
              *(_WORD *)(v74 + 34) = 107;
              *(_DWORD *)(v74 + 36) = v51;
            }
            *((_WORD *)this + 60) = 10242;
            v75 = &Class;
            v76 = &Class;
            if ( v73 )
              v76 = (const WCHAR *)v73;
            v77 = *((_QWORD *)this + 13);
            if ( v77 )
            {
              v78 = *(_DWORD *)(v77 + 276);
              v75 = (const WCHAR *)(v77 + 280);
            }
            else
            {
              v78 = 0;
            }
            if ( (g_dwEventLogging & 4) != 0 )
            {
              *(_OWORD *)Size = 0;
              DestinationString = 0;
              RtlInitUnicodeString((PUNICODE_STRING)Size, v75);
              RtlInitUnicodeString(&DestinationString, v76);
              LODWORD(v106) = 107;
              LODWORD(v105) = 40;
              SchEventWrite(&SSLEVENT_GENERATE_FATAL_ALERT, L"duddu", v78, Size, v105, v106, &DestinationString);
            }
            memset_0(v121, 0, 0x680u);
            v79 = *((_QWORD *)this + 1);
            if ( v79 )
            {
              v80 = *(_DWORD *)(v79 + 28);
              v122 = v80;
            }
            else
            {
              v80 = 0;
              v122 = 0;
            }
            v81 = *((unsigned __int16 *)this + 17);
            v82 = *((_QWORD *)this + 232);
            v123 = *((_DWORD *)this + 4);
            if ( v79 )
            {
              v104 = *((_QWORD *)this + 14);
              if ( v104 )
                CSchannelTelemetryContext::LogKeyExchange(
                  (CSsl3TlsClientContext *)((char *)this + 144),
                  *(_DWORD *)(v79 + 32),
                  *(_DWORD *)(*(_QWORD *)(v104 + 40) + 8LL));
            }
            if ( CTelemetryContext::s_IsTelemetryGloballyInitialized )
            {
              *((_DWORD *)this + 47) = v123;
              *((_BYTE *)this + 260) = 40;
              *((_DWORD *)this + 64) = v51;
              *((_DWORD *)this + 66) = 107;
              *((_DWORD *)this + 46) = v80;
              *((_DWORD *)this + 48) = v81;
              *((_QWORD *)this + 35) = v82;
              *((_BYTE *)this + 169) = 1;
            }
            CSchannelTelemetryContext::LogDebugTraceHandshakeInfo(
              (CSsl3TlsClientContext *)((char *)this + 144),
              L"Fatal Error");
            return v51;
          }
          v30 = 0;
          v31 = *(unsigned __int8 **)(*(_QWORD *)(*((_QWORD *)this + 380) + 160LL) + 264LL);
          if ( !v31 )
          {
LABEL_32:
            v32 = *((_QWORD *)CSessionCacheManager::m_pSessionCacheManager + 4)
                + 152LL * (v30 / *((_DWORD *)CSessionCacheManager::m_pSessionCacheManager + 11));
            if ( v32 )
              RtlReleaseResource((PRTL_RESOURCE)(v32 + 48));
            goto LABEL_34;
          }
          do
            v9 = *(_WORD *)&v31[2 * v21++ + 2] == 0;
          while ( !v9 );
          v66 = (unsigned int)(2 * v21);
          if ( (unsigned __int64)v66 >= 8 )
          {
            do
            {
              v66 -= 8;
              v67 = v31[6]
                  + 37
                  * (v31[5] + 37 * (v31[4] + 37 * (v31[3] + 37 * (v31[2] + 37 * (v31[1] + 37 * (*v31 + 37 * v20))))));
              v68 = v31[7];
              v31 += 8;
              v20 = v68 + 37 * v67;
            }
            while ( v66 >= 8 );
          }
          if ( v66 != 6 )
          {
            if ( v66 == 4 )
            {
LABEL_88:
              LODWORD(v20) = *v31++ + 37 * v20;
              goto LABEL_89;
            }
            v69 = v66 - 1;
            if ( !v69 )
            {
LABEL_91:
              LODWORD(v20) = *v31 + 37 * v20;
              goto LABEL_92;
            }
            v70 = v69 - 1;
            if ( !v70 )
            {
LABEL_90:
              LODWORD(v20) = *v31++ + 37 * v20;
              goto LABEL_91;
            }
            v71 = v70 - 1;
            if ( !v71 )
            {
LABEL_89:
              LODWORD(v20) = *v31++ + 37 * v20;
              goto LABEL_90;
            }
            v72 = v71 - 2;
            if ( !v72 )
            {
LABEL_87:
              LODWORD(v20) = *v31++ + 37 * v20;
              goto LABEL_88;
            }
            if ( v72 != 2 )
            {
LABEL_92:
              v30 = (unsigned int)v20 % *((_DWORD *)CSessionCacheManager::m_pSessionCacheManager + 4);
              goto LABEL_32;
            }
            LODWORD(v20) = *v31++ + 37 * v20;
          }
          LODWORD(v20) = *v31++ + 37 * v20;
          goto LABEL_87;
        }
        v83 = -1;
        do
          v9 = *(_WORD *)&v23[2 * v83++ + 2] == 0;
        while ( !v9 );
        v84 = (unsigned int)(2 * v83);
        v85 = 314159;
        if ( (unsigned __int64)v84 >= 8 )
        {
          do
          {
            v84 -= 8;
            v86 = v23[6]
                + 37 * (v23[5] + 37 * (v23[4] + 37 * (v23[3] + 37 * (v23[2] + 37 * (v23[1] + 37 * (*v23 + 37 * v85))))));
            v87 = v23[7];
            v23 += 8;
            v85 = v87 + 37 * v86;
          }
          while ( v84 >= 8 );
        }
        if ( v84 != 6 )
        {
          if ( v84 == 4 )
          {
LABEL_121:
            LODWORD(v85) = *v23++ + 37 * v85;
            goto LABEL_122;
          }
          v88 = v84 - 1;
          if ( !v88 )
          {
LABEL_124:
            LODWORD(v85) = *v23 + 37 * v85;
            goto LABEL_125;
          }
          v89 = v88 - 1;
          if ( !v89 )
          {
LABEL_123:
            LODWORD(v85) = *v23++ + 37 * v85;
            goto LABEL_124;
          }
          v90 = v89 - 1;
          if ( !v90 )
          {
LABEL_122:
            LODWORD(v85) = *v23++ + 37 * v85;
            goto LABEL_123;
          }
          v91 = v90 - 2;
          if ( !v91 )
          {
LABEL_120:
            LODWORD(v85) = *v23++ + 37 * v85;
            goto LABEL_121;
          }
          if ( v91 != 2 )
          {
LABEL_125:
            v22 = (unsigned int)v85 % *((_DWORD *)CSessionCacheManager::m_pSessionCacheManager + 4);
            goto LABEL_22;
          }
          LODWORD(v85) = *v23++ + 37 * v85;
        }
        LODWORD(v85) = *v23++ + 37 * v85;
        goto LABEL_120;
      }
      v102 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_221:
        LOBYTE(v14) = 40;
        CSslContext::SetErrorAndFatalAlert(this, 1207, 2148074310LL, v14);
        result = 2148074310LL;
        *((_DWORD *)this + 23) = 96;
        *((_WORD *)this + 60) = 10242;
        return result;
      }
      v103 = 53;
    }
    WPP_SF_(*((_QWORD *)v102 + 2), v103, WPP_5383be3bbf5b3806aa9fb4bb82cdd1d5_Traceguids);
    goto LABEL_221;
  }
  if ( v64 != -2146892986 )
  {
    LOBYTE(v14) = 10;
    CSslContext::SetErrorAndFatalAlert(this, 106, v64, v14);
  }
  CTlsExtClient::~CTlsExtClient((CTlsExtClient *)&v111);
  return v65;
}

```

## disassembly

```asm
0x18000b620  push    rbp
0x18000b622  push    rbx
0x18000b623  push    rsi
0x18000b624  push    r13
0x18000b626  lea     rbp, [rsp-6B8h]
0x18000b62e  sub     rsp, 7B8h
0x18000b635  mov     rax, cs:__security_cookie
0x18000b63c  xor     rax, rsp
0x18000b63f  mov     [rbp+6D0h+var_38], rax
0x18000b646  mov     qword ptr [rbp+6D0h+DestinationString.Length], r9
0x18000b64a  mov     rbx, rcx
0x18000b64d  mov     byte ptr [rcx+8E2h], 0
0x18000b654  cmp     r8d, 23h ; '#'
0x18000b658  jb      loc_18000C1B9
0x18000b65e  movups  xmm0, xmmword ptr [rdx+2]
0x18000b662  movzx   r9d, byte ptr [rdx]
0x18000b666  movzx   r10d, byte ptr [rdx+1]
0x18000b66b  movups  xmmword ptr [rcx+7E8h], xmm0
0x18000b672  movups  xmm1, xmmword ptr [rdx+12h]
0x18000b676  movups  xmmword ptr [rcx+7F8h], xmm1
0x18000b67d  movzx   ecx, byte ptr [rdx+22h]
0x18000b681  cmp     cl, 20h ; ' '
0x18000b684  ja      loc_18000C491
0x18000b68a  lea     esi, [r8-23h]
0x18000b68e  mov     r13d, ecx
0x18000b691  lea     eax, [rcx+3]
0x18000b694  cmp     esi, eax
0x18000b696  jb      loc_18000C1B9
0x18000b69c  cmp     byte ptr [rdx+rcx+25h], 0
0x18000b6a1  mov     r11d, ecx
0x18000b6a4  mov     [rsp+7D0h+var_20], r12
0x18000b6ac  lea     r12, [rdx+23h]
0x18000b6b0  mov     [rbp+6D0h+Size], rcx
0x18000b6b7  jnz     loc_18000C49B
0x18000b6bd  mov     rcx, [rbx+68h]
0x18000b6c1  mov     [rsp+7D0h+arg_10], rdi
0x18000b6c9  test    rcx, rcx
0x18000b6cc  jz      loc_18000C4BB
0x18000b6d2  mov     edi, r9d
0x18000b6d5  mov     r8d, 303h
0x18000b6db  shl     edi, 8
0x18000b6de  mov     r9d, 304h
0x18000b6e4  or      edi, r10d
0x18000b6e7  mov     r10d, 302h
0x18000b6ed  cmp     edi, r8d
0x18000b6f0  jnz     loc_18000BCC2
0x18000b6f6  mov     edx, 800h
0x18000b6fb  and     edx, [rcx+0D8h]
0x18000b701  jz      loc_18000C4CF
0x18000b707  movzx   eax, byte ptr [r12+r11]
0x18000b70c  test    edx, 0F0000h
0x18000b712  mov     [rsp+7D0h+var_760], al
0x18000b716  movzx   eax, byte ptr [r12+r11+1]
0x18000b71c  setnz   cl
0x18000b71f  test    edx, 3FFCh
0x18000b725  mov     [rsp+7D0h+var_75F], al
0x18000b729  mov     [rsp+7D0h+var_28], r14
0x18000b731  mov     r14d, 0FEFDh
0x18000b737  setnz   al
0x18000b73a  mov     [rbx+58h], edx
0x18000b73d  test    al, cl
0x18000b73f  jnz     loc_18000C20E
0x18000b745  test    edx, 0C0000h
0x18000b74b  jnz     loc_18000C215
0x18000b751  test    edx, 30000h
0x18000b757  jnz     loc_18000C204
0x18000b75d  test    edx, 3000h
0x18000b763  jnz     loc_18000BCB9
0x18000b769  test    edx, 0C00h
0x18000b76f  jz      loc_18000C133
0x18000b775  movzx   eax, r8w
0x18000b779  cmp     byte ptr [rbx+7A1h], 0
0x18000b780  mov     [rbx+22h], ax
0x18000b784  jnz     loc_18000C4FD
0x18000b78a  cmp     [rbx+24h], edi
0x18000b78d  ja      loc_18000C021
0x18000b793  sub     esi, r13d
0x18000b796  add     esi, 0FFFFFFFDh
0x18000b799  cmp     esi, 2
0x18000b79c  ja      loc_18000BC03
0x18000b7a2  mov     byte ptr [rbx+0A52h], 0
0x18000b7a9  cmp     byte ptr [rbx+8E2h], 0
0x18000b7b0  jz      loc_18000C52D
0x18000b7b6  mov     r9, cs:?m_pSessionCacheManager@CSessionCacheManager@@0PEAV1@EA; CSessionCacheManager * CSessionCacheManager::m_pSessionCacheManager
0x18000b7bd  mov     r14d, 4CB2Fh
0x18000b7c3  mov     [rsp+7D0h+var_30], r15
0x18000b7cb  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000b7d2  test    r9, r9
0x18000b7d5  jz      short loc_18000B818
0x18000b7d7  mov     rax, [rbx+0BE0h]
0x18000b7de  mov     rcx, [rax+0A0h]
0x18000b7e5  xor     eax, eax
0x18000b7e7  mov     r8, [rcx+108h]
0x18000b7ee  test    r8, r8
0x18000b7f1  jnz     loc_18000BED6
0x18000b7f7  xor     edx, edx
0x18000b7f9  div     dword ptr [r9+2Ch]
0x18000b7fd  mov     ecx, eax
0x18000b7ff  imul    rcx, 98h
0x18000b806  add     rcx, [r9+20h]
0x18000b80a  jz      short loc_18000B818
0x18000b80c  add     rcx, 30h ; '0'; Resource
0x18000b810  mov     dl, 1; Wait
0x18000b812  call    cs:__imp_RtlAcquireResourceExclusive
0x18000b818  mov     rax, [rbx+0BE0h]
0x18000b81f  mov     dl, 1; Wait
0x18000b821  mov     rcx, [rax+28h]
0x18000b825  add     rcx, 50h ; 'P'; Resource
0x18000b829  call    cs:__imp_RtlAcquireResourceExclusive
0x18000b82f  mov     rdi, [rbx+0BE0h]
0x18000b836  movzx   eax, word ptr [rdi+4Eh]
0x18000b83a  cmp     eax, 20h ; ' '
0x18000b83d  ja      loc_18000C24C
0x18000b843  mov     r8d, eax; Size
0x18000b846  lea     rdx, [rdi+50h]; Src
0x18000b84a  lea     rcx, [rbp+6D0h+Buf1]; void *
0x18000b851  mov     esi, eax
0x18000b853  call    memcpy_0
0x18000b858  cmp     qword ptr [rdi+20h], 0
0x18000b85d  lea     rdx, WPP_GLOBAL_Control
0x18000b864  jnz     loc_18000C25F
0x18000b86a  mov     rcx, [rdi+28h]
0x18000b86e  mov     eax, [rbx+58h]
0x18000b871  mov     dword ptr [rsp+7D0h+var_758], 0
0x18000b879  mov     [rcx+0B0h], eax
0x18000b87f  test    r13d, r13d
0x18000b882  jz      short loc_18000B8A8
0x18000b884  mov     rcx, [rbx+0BE0h]
0x18000b88b  mov     [rcx+4Eh], r13w
0x18000b890  test    r12, r12
0x18000b893  jz      short loc_18000B8A8
0x18000b895  mov     r8, [rbp+6D0h+Size]; Size
0x18000b89c  add     rcx, 50h ; 'P'; void *
0x18000b8a0  mov     rdx, r12; Src
0x18000b8a3  call    memcpy_0
0x18000b8a8  movzx   eax, [rsp+7D0h+var_75F]
0x18000b8ad  movzx   esi, [rsp+7D0h+var_760]
0x18000b8b2  shl     esi, 8
0x18000b8b5  or      esi, eax
0x18000b8b7  mov     rax, [rbx+0BE0h]
0x18000b8be  mov     rcx, [rax+28h]
0x18000b8c2  add     rcx, 50h ; 'P'; Resource
0x18000b8c6  call    cs:__imp_RtlReleaseResource
0x18000b8cc  mov     r9, cs:?m_pSessionCacheManager@CSessionCacheManager@@0PEAV1@EA; CSessionCacheManager * CSessionCacheManager::m_pSessionCacheManager
0x18000b8d3  test    r9, r9
0x18000b8d6  jz      short loc_18000B917
0x18000b8d8  mov     rax, [rbx+0BE0h]
0x18000b8df  mov     rcx, [rax+0A0h]
0x18000b8e6  xor     eax, eax
0x18000b8e8  mov     r8, [rcx+108h]
0x18000b8ef  test    r8, r8
0x18000b8f2  jnz     loc_18000BCE0
0x18000b8f8  xor     edx, edx
0x18000b8fa  div     dword ptr [r9+2Ch]
0x18000b8fe  mov     ecx, eax
0x18000b900  imul    rcx, 98h
0x18000b907  add     rcx, [r9+20h]
0x18000b90b  jz      short loc_18000B917
0x18000b90d  add     rcx, 30h ; '0'; Resource
0x18000b911  call    cs:__imp_RtlReleaseResource
0x18000b917  mov     r14, [rbx+68h]
0x18000b91b  lea     rcx, Resource; Resource
0x18000b922  mov     r15d, [rbx+58h]
0x18000b926  mov     dl, 1; Wait
0x18000b928  mov     eax, [r14+100h]
0x18000b92f  mov     r12, [r14+0F8h]
0x18000b936  mov     r13d, [r14+0F0h]
0x18000b93d  mov     dword ptr [rbp+6D0h+Size], eax
0x18000b943  call    cs:__imp_RtlAcquireResourceShared
0x18000b949  mov     eax, [rbx+740h]
0x18000b94f  bt      rax, 1Dh
0x18000b954  mov     rax, qword ptr cs:xmmword_1800AE5B0
0x18000b95b  cmovb   rax, qword ptr cs:xmmword_1800AE5B0+8
0x18000b963  xor     r11d, r11d
0x18000b966  test    rax, rax
0x18000b969  jz      loc_18000C128
0x18000b96f  mov     r9, [rax]
0x18000b972  mov     r8d, [rax+8]
0x18000b976  mov     edx, r11d
0x18000b979  cmp     edx, r8d
0x18000b97c  jnb     loc_18000C08E
0x18000b982  mov     eax, edx
0x18000b984  imul    rdi, rax, 360h
0x18000b98b  add     rdi, r9
0x18000b98e  cmp     [rdi+1Ch], esi
0x18000b991  jz      short loc_18000B997
0x18000b993  inc     edx
0x18000b995  jmp     short loc_18000B979
0x18000b997  mov     r10d, [r14+0DCh]
0x18000b99e  mov     r8d, r13d
0x18000b9a1  mov     eax, [r14+0E4h]
0x18000b9a8  mov     ecx, r10d
0x18000b9ab  mov     r9d, dword ptr [rbp+6D0h+Size]
0x18000b9b2  and     ecx, 800h
0x18000b9b8  mov     [rsp+7D0h+var_768], 1
0x18000b9bd  mov     rdx, r12
0x18000b9c0  mov     [rsp+7D0h+var_770], r11d
0x18000b9c5  mov     [rsp+7D0h+var_778], r11
0x18000b9ca  mov     [rsp+7D0h+var_780], r11
0x18000b9cf  mov     [rsp+7D0h+var_788], rdi
0x18000b9d4  mov     [rsp+7D0h+var_790], r15d
0x18000b9d9  mov     [rsp+7D0h+var_798], eax
0x18000b9dd  mov     eax, [r14+0E8h]
0x18000b9e4  mov     dword ptr [rsp+7D0h+var_7A0], eax
0x18000b9e8  mov     dword ptr [rsp+7D0h+var_7A8], ecx
0x18000b9ec  lea     rcx, ?g_cCipherMill@@3VCCipherMill@@A; CCipherMill g_cCipherMill
0x18000b9f3  shr     r10d, 0Ch
0x18000b9f7  and     r10d, 1
0x18000b9fb  mov     dword ptr [rsp+7D0h+var_7B0], r10d
0x18000ba00  call    ?IsCipherSuiteAllowed@CCipherMill@@QEAAEPEAIKW4efAlgFlags@@HHKKKPEAVCCipherSuiteInfo@@PEAU_UNICODE_STRING@@PEAU_TLS_PARAMETERS@@KE@Z; CCipherMill::IsCipherSuiteAllowed(uint *,ulong,efAlgFlags,int,int,ulong,ulong,ulong,CCipherSuiteInfo *,_UNICODE_STRING *,_TLS_PARAMETERS *,ulong,uchar)
0x18000ba05  test    al, al
0x18000ba07  jz      loc_18000C077
0x18000ba0d  mov     rax, [rdi+350h]
0x18000ba14  test    rax, rax
0x18000ba17  jz      short loc_18000BA21
0x18000ba19  mov     rax, [rax+10h]
0x18000ba1d  lock inc dword ptr [rax+0Ch]
0x18000ba21  mov     rax, [rdi+358h]
0x18000ba28  lock inc dword ptr [rax+0Ch]
0x18000ba2c  mov     rax, [rbx]
0x18000ba2f  mov     rcx, rbx
0x18000ba32  mov     rax, [rax+108h]
0x18000ba39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba3e  mov     r14, [rbx+8]
0x18000ba42  mov     rsi, rax
0x18000ba45  xor     eax, eax
0x18000ba47  xorps   xmm0, xmm0
0x18000ba4a  mov     [rbp+6D0h+var_60], eax
0x18000ba50  movups  xmmword ptr [rbp+6D0h+Size], xmm0
0x18000ba57  test    r14, r14
0x18000ba5a  jnz     loc_18000C226
0x18000ba60  mov     rcx, [rbx+18h]; this
0x18000ba64  test    rcx, rcx
0x18000ba67  jnz     loc_18000C589
0x18000ba6d  xor     r12d, r12d
0x18000ba70  test    rsi, rsi
0x18000ba73  jz      short loc_18000BACA
0x18000ba75  mov     r15, [rdi]
0x18000ba78  lea     rcx, [rsi+228h]; Resource
0x18000ba7f  mov     dl, 1; Wait
0x18000ba81  call    cs:__imp_RtlAcquireResourceShared
0x18000ba87  mov     r8d, r12d
0x18000ba8a  cmp     r8d, [rsi+60h]
0x18000ba8e  jnb     short loc_18000BABD
0x18000ba90  mov     eax, r8d
0x18000ba93  lea     rdx, ds:0[rax*8]
0x18000ba9b  mov     rax, [rsi+58h]
0x18000ba9f  mov     rcx, [rdx+rax]
0x18000baa3  cmp     [rcx+10h], r15
0x18000baa7  jnz     loc_18000C21E
0x18000baad  lock inc dword ptr [rcx+18h]
0x18000bab1  mov     rax, [rsi+58h]
0x18000bab5  mov     rdx, [rdx+rax]
0x18000bab9  mov     [rbx+18h], rdx
0x18000babd  lea     rcx, [rsi+228h]; Resource
0x18000bac4  call    cs:__imp_RtlReleaseResource
0x18000baca  test    dword ptr [rbx+58h], 0F3F00h
0x18000bad1  jz      loc_18000C15E
0x18000bad7  movzx   edx, word ptr [rbx+22h]
0x18000badb  lea     rax, [rbp+6D0h+Size]
0x18000bae2  mov     r9d, [rbx+10h]
0x18000bae6  mov     r8d, [rdi+1Ch]
0x18000baea  mov     rcx, [rdi]
0x18000baed  mov     dword ptr [rsp+7D0h+var_7A0], r12d
0x18000baf2  mov     dword ptr [rsp+7D0h+var_7A8], 14h
0x18000bafa  mov     [rsp+7D0h+var_7B0], rax
0x18000baff  call    cs:__imp_SslLookupCipherLengths
0x18000bb05  mov     esi, eax
0x18000bb07  test    eax, eax
0x18000bb09  jnz     short loc_18000BB29
0x18000bb0b  test    byte ptr [rbx+20h], 1
0x18000bb0f  jnz     loc_18000C1D9
0x18000bb15  movups  xmm0, xmmword ptr [rbp+6D0h+Size]
0x18000bb1c  mov     eax, [rbp+6D0h+var_60]
0x18000bb22  movups  xmmword ptr [rbx+28h], xmm0
0x18000bb26  mov     [rbx+38h], eax
0x18000bb29  or      word ptr [rbx+20h], 1
0x18000bb2e  lea     rcx, Resource; Resource
0x18000bb35  mov     [rbx+8], rdi
0x18000bb39  call    cs:__imp_RtlReleaseResource
0x18000bb3f  mov     rax, [rbx]
0x18000bb42  test    esi, esi
0x18000bb44  jnz     loc_18000BE06
0x18000bb4a  test    dword ptr [rbx+58h], 80800h
0x18000bb51  mov     rcx, rbx
0x18000bb54  mov     rax, [rax+230h]
0x18000bb5b  setnz   dl
0x18000bb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb63  test    eax, eax
0x18000bb65  jnz     short loc_18000BBC7
0x18000bb67  mov     r8d, [rbx+0A20h]
0x18000bb6e  mov     r9b, 1
0x18000bb71  mov     rdx, [rbx+0A28h]
0x18000bb78  mov     rcx, rbx
0x18000bb7b  mov     [rbx+80Ch], al
0x18000bb81  mov     rax, [rbx]
0x18000bb84  mov     rax, [rax+238h]
0x18000bb8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb90  mov     rdx, [rbx+0A28h]
0x18000bb97  mov     edi, eax
  ... truncated ...
```
