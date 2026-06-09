# WDiagConnectCompletion(_WD_INTERFACE_CONTEXT *,void *,DOT11_SSID_LIST *,_PM_PROFILE *,_WLAN_CONNECTION_MODE *,PasspointFlag,ulong,ulong,ulong,int,int,unsigned __int64,bool)

- ea: `0x18001ff4c`
- end: `0x180020d11`
- name: `?WDiagConnectCompletion@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXPEAUDOT11_SSID_LIST@@PEAU_PM_PROFILE@@PEAW4_WLAN_CONNECTION_MODE@@W4PasspointFlag@@KKKHH_K_N@Z`
- size: `3525`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001fde8`

## callees

- `0x18000aa0c`
- `0x18000c5a0`
- `0x180011530`
- `0x18001b22c`
- `0x18001cd38`
- `0x18001e950`
- `0x18001ea10`
- `0x18001eacc`
- `0x18001fd00`
- `0x18001ff4c`
- `0x180029ed4`
- `0x18002aeb4`
- `0x18002bde8`
- `0x18002c96c`
- `0x18002d18c`
- `0x180075bfc`
- `0x18009ae14`
- `0x1800afe28`
- `0x1800b4990`
- `0x1800cc4a4`
- `0x1800de33c`
- `0x1800e09c0`
- `0x1800f7798`
- `0x18010051c`
- `0x180106340`
- `0x18010730c`
- `0x180107330`
- `0x1801c5dcc`
- `0x1801c73dc`
- `0x1801c7570`
- `0x1801c77f4`
- `0x18021e380`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020017`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020017`
- `npmproxy!NlmDiagSendWlanConnectionAttemptDiagnostics` at `0x1800209cc`
- `npmproxy!NlmDiagSendWlanConnectionAttemptDiagnostics` at `0x180020ca4`
- `npmproxy!NlmDiagSendWlanConnectionAttemptDiagnostics` at `0x1800209cc`
- `npmproxy!NlmDiagSendWlanConnectionAttemptDiagnostics` at `0x180020ca4`

## string_xrefs

- `0x18002012f`: `WDiagConnectCompletion`
- `0x180020168`: `WDiagConnectCompletion`
- `0x180020206`: `WDiagConnectCompletion`
- `0x1800202db`: `WDiagConnectCompletion`
- `0x1800202f7`: `WDiagConnectCompletion`
- `0x1800209e4`: `WDiagConnectCompletion`
- `0x180020a00`: `WDiagConnectCompletion`
- `0x180020cb7`: `WDiagConnectCompletion`
- `0x180020cd3`: `WDiagConnectCompletion`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WDiagConnectCompletion(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        unsigned int a9,
        int a10,
        int a11,
        __int64 a12,
        char a13)
{
  struct _WLAN_CONNECTION_ATTRIBUTES *v16; // r12
  __int64 v17; // rdx
  ULONGLONG TickCount64; // r15
  struct DOT11_CONNECTION_INFO *v19; // rsi
  struct DOT11_CONNECTION_INFO **ConnectionInfo; // rax
  __int64 v21; // rcx
  __int64 ConnectionAttributes; // rax
  struct _WLAN_CONNECTION_ATTRIBUTES *v23; // rcx
  int v24; // eax
  struct _PM_PROFILE *v25; // r8
  struct _DOT11_SSID *v26; // r9
  struct _WD_CONNECTION_CONTEXT *MatchingConnection; // rdi
  unsigned int v28; // r13d
  char *v29; // rbx
  _WORD *v30; // r9
  unsigned __int16 *v31; // rax
  int v32; // ecx
  int v33; // edx
  struct _WLAN_CONNECTION_ATTRIBUTES *v34; // rcx
  _OWORD *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // r8
  int v40; // ecx
  __int64 v41; // rdx
  __int64 v42; // r8
  PVOID *v43; // r10
  PVOID *v44; // r11
  int v45; // r12d
  int v46; // eax
  unsigned int v47; // eax
  char *v48; // r8
  int *v49; // r9
  __int64 v50; // rdx
  unsigned int v51; // eax
  unsigned int v52; // eax
  struct _WLAN_CONNECTION_ATTRIBUTES *v53; // rbx
  char *v54; // rax
  __int64 v55; // rcx
  _OWORD *v56; // rax
  _OWORD *v57; // rcx
  __int64 v58; // rdx
  unsigned int updated; // eax
  char *v60; // rax
  int *p_Buf1; // [rsp+20h] [rbp-E0h]
  unsigned int v62; // [rsp+20h] [rbp-E0h]
  int *v63; // [rsp+38h] [rbp-C8h]
  __int64 v64; // [rsp+40h] [rbp-C0h]
  __int64 v65; // [rsp+48h] [rbp-B8h]
  char v66; // [rsp+50h] [rbp-B0h]
  unsigned int v67; // [rsp+54h] [rbp-ACh] BYREF
  int v68; // [rsp+58h] [rbp-A8h]
  struct DOT11_CONNECTION_INFO *v69; // [rsp+60h] [rbp-A0h]
  struct _WLAN_CONNECTION_ATTRIBUTES *v70; // [rsp+68h] [rbp-98h] BYREF
  __int64 v71; // [rsp+70h] [rbp-90h] BYREF
  int v72; // [rsp+78h] [rbp-88h] BYREF
  int v73; // [rsp+7Ch] [rbp-84h]
  int Buf1; // [rsp+80h] [rbp-80h] BYREF
  __int16 v75; // [rsp+84h] [rbp-7Ch]
  struct _WLAN_CONNECTION_ATTRIBUTES *v76; // [rsp+88h] [rbp-78h] BYREF
  __int128 v77; // [rsp+90h] [rbp-70h] BYREF
  struct DOT11_CONNECTION_INFO *v78; // [rsp+A0h] [rbp-60h]
  int v79; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v80[156]; // [rsp+B4h] [rbp-4Ch] BYREF
  _DWORD v81[911]; // [rsp+150h] [rbp+50h] BYREF
  int v82; // [rsp+F8Ch] [rbp+E8Ch]
  int v83; // [rsp+FBCh] [rbp+EBCh]
  int v84; // [rsp+1078h] [rbp+F78h]
  unsigned int v85; // [rsp+1090h] [rbp+F90h]
  unsigned int v86; // [rsp+109Ch] [rbp+F9Ch]

  v16 = 0;
  v73 = 0;
  v72 = 0;
  Buf1 = 0;
  v75 = 0;
  v79 = 0;
  memset_0(v80, 0, sizeof(v80));
  memset_0(v81, 0, 0xF68u);
  v67 = 0;
  v68 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 121, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  StopWlanDbgTracing(a9);
  TickCount64 = GetTickCount64();
  *(_QWORD *)&v77 = TickCount64;
  v19 = 0;
  v69 = 0;
  v78 = 0;
  v70 = 0;
  v76 = 0;
  if ( !a11 )
  {
    v65 = 0;
    v64 = 0;
    v63 = &v72;
    p_Buf1 = &Buf1;
    WDiagQueryDot11DataEx(a1, v17, &v79, 0);
    ConnectionInfo = (struct DOT11_CONNECTION_INFO **)WDiagGetConnectionInfo(&v71, a1);
    v69 = *ConnectionInfo;
    v19 = v69;
    *ConnectionInfo = 0;
    v78 = v19;
    v21 = v71;
    v71 = 0;
    if ( v21 )
      FreeWLMem(v21);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_57825957>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_57825957>::GetImpl'::`2'::impl) )
    {
      ConnectionAttributes = WDiagGetConnectionAttributes(&v70, a1);
      wistd::unique_ptr<_WLAN_CONNECTION_ATTRIBUTES,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>::operator=(
        &v76,
        ConnectionAttributes);
      v23 = v70;
      v70 = 0;
      if ( v23 )
        FreeWLMem(v23);
      v16 = v76;
      v70 = v76;
    }
  }
  if ( !WDiagQueryIntfOpmode((struct _WD_INTERFACE_CONTEXT *)a1, &v67) )
  {
    v24 = v68;
    if ( v67 == 4 )
      v24 = 1;
    v68 = v24;
  }
  WDiagAcquireExLock((void *)a1, (struct _WDIAG_RW_LOCK *)(a1 + 3352), "WDiagConnectCompletion", 0xAF9u);
  MatchingConnection = FindMatchingConnection(
                         (struct _WD_INTERFACE_CONTEXT *)a1,
                         a2,
                         v25,
                         v26,
                         (enum _DOT11_BSS_TYPE)p_Buf1,
                         1u,
                         1u);
  if ( !MatchingConnection )
  {
    WDiagReleaseExLock((void *)a1, (struct _WDIAG_RW_LOCK *)(a1 + 3352), "WDiagConnectCompletion", 0xB03u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 122, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
    }
    v28 = 1168;
LABEL_21:
    if ( v16 )
      FreeWLMem(v16);
    if ( v19 )
      FreeWLMem(v19);
    goto LABEL_41;
  }
  v67 = 1168;
  WdiagInitSqmRecord((struct WDIAG_SQM_RECORD *)v81);
  WDiagAcquireExLock(
    MatchingConnection,
    (struct _WD_CONNECTION_CONTEXT *)((char *)MatchingConnection + 3920),
    "WDiagConnectCompletion",
    0xB0Du);
  *((_DWORD *)MatchingConnection + 301) = 1;
  *((_QWORD *)MatchingConnection + 151) = TickCount64;
  *((_DWORD *)MatchingConnection + 1018) = a12;
  *((_DWORD *)MatchingConnection + 1017) = HIDWORD(a12);
  *((_BYTE *)MatchingConnection + 4076) = a13;
  if ( !a4 )
    goto LABEL_52;
  v29 = (char *)(a4 + 24);
  v30 = (_WORD *)((char *)MatchingConnection + 88);
  v31 = (unsigned __int16 *)((char *)MatchingConnection + 88);
  do
  {
    v32 = *(unsigned __int16 *)((char *)v31 + v29 - ((char *)MatchingConnection + 88));
    v33 = *v31 - v32;
    if ( v33 )
      break;
    ++v31;
  }
  while ( v32 );
  if ( !v33 )
  {
LABEL_52:
    v66 = 0;
    goto LABEL_53;
  }
  if ( !*v30 )
  {
    v66 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        124,
        (unsigned int)&WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids,
        (_DWORD)v30,
        (__int64)v29);
    }
    v36 = (_OWORD *)((char *)MatchingConnection + 3404);
    v37 = 4;
    do
    {
      *v36 = *(_OWORD *)v29;
      v36[1] = *((_OWORD *)v29 + 1);
      v36[2] = *((_OWORD *)v29 + 2);
      v36[3] = *((_OWORD *)v29 + 3);
      v36[4] = *((_OWORD *)v29 + 4);
      v36[5] = *((_OWORD *)v29 + 5);
      v36[6] = *((_OWORD *)v29 + 6);
      v36[7] = *((_OWORD *)v29 + 7);
      v36 += 8;
      v29 += 128;
      --v37;
    }
    while ( v37 );
LABEL_53:
    LODWORD(v71) = 0;
    WDiagUpdatePasspointInfo(MatchingConnection, a6);
    *((_DWORD *)MatchingConnection + 432) = v73;
    *((_DWORD *)MatchingConnection + 433) = v72;
    if ( memcmp_0(&Buf1, &zeroMac, 6u) )
    {
      *(_DWORD *)((char *)MatchingConnection + 1478) = Buf1;
      *((_WORD *)MatchingConnection + 741) = v75;
    }
    if ( a5 )
      v40 = *a5;
    else
      v40 = 5;
    *((_DWORD *)MatchingConnection + 304) = v40;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      LODWORD(v63) = v72;
      WPP_SF_DDDdd(*((_QWORD *)WPP_GLOBAL_Control + 27), v38, v39, a9, a8, a7, v73, v63, v64, v65);
    }
    if ( !a9 )
    {
      WDiagGetTime((LPFILETIME)MatchingConnection + 252);
      v55 = 624LL * ((*((_DWORD *)MatchingConnection + 294) - 1) % 5u);
      *(_DWORD *)(v55 + a1 + 772) = 1;
      v56 = (_OWORD *)(v55 + a1 + 200);
      v57 = (_OWORD *)((char *)MatchingConnection + 624);
      v58 = 4;
      do
      {
        *v56 = *v57;
        v56[1] = v57[1];
        v56[2] = v57[2];
        v56[3] = v57[3];
        v56[4] = v57[4];
        v56[5] = v57[5];
        v56[6] = v57[6];
        v56[7] = v57[7];
        v56 += 8;
        v57 += 8;
        --v58;
      }
      while ( v58 );
      *v56 = *v57;
      v56[1] = v57[1];
      v56[2] = v57[2];
      *(_OWORD *)((char *)v56 + 44) = *(_OWORD *)((char *)v57 + 44);
      if ( (*((_DWORD *)MatchingConnection + 299) & 0x18) == 8 )
      {
        WDiagGetTime((LPFILETIME)MatchingConnection + 211);
        *((_QWORD *)MatchingConnection + 213) = v77;
        *((_DWORD *)MatchingConnection + 299) |= 0x10u;
        WDiagGetTime((LPFILETIME)MatchingConnection + 211);
      }
      *((_DWORD *)MatchingConnection + 299) |= 0x60u;
      updated = UpdateConnectivityStatistics(MatchingConnection, (struct WDIAG_PACKET_STATISTICS *)&v79);
      if ( updated
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 137, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids, updated);
      }
      *(_DWORD *)(a1 + 24) |= 2u;
      v28 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          138,
          &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids,
          *((unsigned int *)MatchingConnection + 1015));
      }
      if ( *((_DWORD *)MatchingConnection + 1015) || a10 || !v68 )
      {
        v19 = v69;
      }
      else
      {
        v19 = v69;
        WdiagPopulateSqmRecord(MatchingConnection, v69, v16, 0, a8, (struct WDIAG_SQM_RECORD *)v81);
        LODWORD(v71) = 1;
        *((_DWORD *)MatchingConnection + 1015) = 1;
        if ( v86 != 229377 )
        {
          WDiagLogConnectDiagnosticEvent(
            (struct _WD_INTERFACE_CONTEXT *)a1,
            MatchingConnection,
            (struct WDIAG_SQM_RECORD *)v81);
          v60 = (char *)MatchingConnection + 3404;
          if ( !v66 )
            v60 = (char *)MatchingConnection + 88;
          v77 = *(_OWORD *)(a1 + 3488);
          LODWORD(v63) = v83;
          NlmDiagSendWlanConnectionAttemptDiagnostics(&v77, v81[0], v86, v85, v82, v84, v60, v63);
        }
      }
      WDiagReleaseExLock(
        MatchingConnection,
        (struct _WD_CONNECTION_CONTEXT *)((char *)MatchingConnection + 3920),
        "WDiagConnectCompletion",
        0xC4Fu);
      WDiagReleaseExLock((void *)a1, (struct _WDIAG_RW_LOCK *)(a1 + 3352), "WDiagConnectCompletion", 0xC50u);
      if ( (_DWORD)v71 && v86 != 229377 )
        WdiagAddSqmRecord((struct WDIAG_SQM_RECORD *)v81);
      goto LABEL_21;
    }
    v45 = WDiagComponentFromReasonCode(a8, *(unsigned int *)(a1 + 4036));
    if ( v43 != v44 && *((_BYTE *)v43 + 225) >= 3u && (*((_BYTE *)v43 + 228) & 0x10) != 0 )
    {
      WPP_SF_LLLd(
        v43[27],
        v41,
        v42,
        *((unsigned int *)MatchingConnection + 375),
        *((_DWORD *)MatchingConnection + 376),
        *((_DWORD *)MatchingConnection + 377),
        *((_DWORD *)MatchingConnection + 378),
        v63);
      v43 = (PVOID *)WPP_GLOBAL_Control;
      v44 = &WPP_GLOBAL_Control;
    }
    v46 = *((_DWORD *)MatchingConnection + 299);
    if ( (v46 & 2) == 0 )
    {
      if ( v43 != v44 && *((_BYTE *)v43 + 225) && (*((_BYTE *)v43 + 228) & 0x10) != 0 )
        WPP_SF_lll(v43[27], 127, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids, a9);
      if ( a7 )
        *((_DWORD *)MatchingConnection + 372) = a7;
      if ( !*((_DWORD *)MatchingConnection + 312) )
        *((_DWORD *)MatchingConnection + 312) = a8;
      if ( !a8 )
        goto LABEL_130;
      *((_DWORD *)MatchingConnection + 311) = v45;
      if ( v45 == 4 && !*((_DWORD *)MatchingConnection + 434) )
        *((_DWORD *)MatchingConnection + 434) = a8;
LABEL_127:
      if ( a8 == 229377 )
      {
        if ( !*((_DWORD *)MatchingConnection + 431) )
          *((_DWORD *)MatchingConnection + 299) |= 0x80000000;
        goto LABEL_132;
      }
LABEL_130:
      if ( a8 == 229393 )
        *((_DWORD *)MatchingConnection + 299) |= 0x40000000u;
LABEL_132:
      *((_DWORD *)MatchingConnection + 299) |= 0x80u;
      *(_DWORD *)(a1 + 24) &= ~2u;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          136,
          &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids,
          *((unsigned int *)MatchingConnection + 1015));
      }
      if ( *((_DWORD *)MatchingConnection + 1015) || a10 )
      {
        v53 = v70;
      }
      else
      {
        v53 = v70;
        if ( v68 )
        {
          v19 = v69;
          WdiagPopulateSqmRecord(MatchingConnection, v69, v70, 0, a8, (struct WDIAG_SQM_RECORD *)v81);
          *((_DWORD *)MatchingConnection + 1015) = 1;
          LODWORD(v71) = 1;
          if ( v86 != 229377 )
          {
            WDiagLogConnectDiagnosticEvent(
              (struct _WD_INTERFACE_CONTEXT *)a1,
              MatchingConnection,
              (struct WDIAG_SQM_RECORD *)v81);
            v54 = (char *)MatchingConnection + 3404;
            if ( !v66 )
              v54 = (char *)MatchingConnection + 88;
            v77 = *(_OWORD *)(a1 + 3488);
            LODWORD(v63) = v83;
            NlmDiagSendWlanConnectionAttemptDiagnostics(&v77, v81[0], v86, v85, v82, v84, v54, v63);
          }
          goto LABEL_145;
        }
      }
      v19 = v69;
LABEL_145:
      WDiagReleaseExLock(
        MatchingConnection,
        (struct _WD_CONNECTION_CONTEXT *)((char *)MatchingConnection + 3920),
        "WDiagConnectCompletion",
        0xC0Du);
      WDiagReleaseExLock((void *)a1, (struct _WDIAG_RW_LOCK *)(a1 + 3352), "WDiagConnectCompletion", 0xC0Eu);
      if ( (_DWORD)v71 && v86 != 229377 )
        WdiagAddSqmRecord((struct WDIAG_SQM_RECORD *)v81);
      if ( !v53 )
        goto LABEL_38;
      v34 = v53;
      goto LABEL_37;
    }
    if ( (v46 & 4) != 0 )
    {
      if ( (v46 & 0x18) != 8 )
      {
        if ( v45 == 5 )
        {
          if ( v43 != v44 && *((_BYTE *)v43 + 225) && (*((_BYTE *)v43 + 228) & 0x10) != 0 )
            WPP_SF_DD(v43[27], 134, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids, a9);
          *((_DWORD *)MatchingConnection + 299) |= 8u;
          *((_DWORD *)MatchingConnection + 430) |= 0x2000u;
          if ( !*((_DWORD *)MatchingConnection + 437) )
            *((_DWORD *)MatchingConnection + 437) = a8;
          if ( !*((_DWORD *)MatchingConnection + 435) )
            *((_DWORD *)MatchingConnection + 435) = a8;
          WDiagGetTime((LPFILETIME)MatchingConnection + 211);
          *((_QWORD *)MatchingConnection + 213) = v77;
        }
        else if ( v43 != v44 && *((_BYTE *)v43 + 225) && (*((_BYTE *)v43 + 228) & 0x10) != 0 )
        {
          WPP_SF_DD(v43[27], 135, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids, a9);
        }
        goto LABEL_127;
      }
      if ( v43 != v44 && *((_BYTE *)v43 + 225) && (*((_BYTE *)v43 + 228) & 0x10) != 0 )
      {
        v62 = a8;
        WPP_SF_DD(v43[27], 130, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids, a9);
      }
      *((_DWORD *)MatchingConnection + 430) |= 0x2000u;
      if ( !*((_DWORD *)MatchingConnection + 437) )
      {
        v51 = a8;
        if ( !a8 )
          v51 = a9;
        *((_DWORD *)MatchingConnection + 437) = v51;
      }
      if ( !*((_DWORD *)MatchingConnection + 435) )
      {
        v52 = a8;
        if ( !a8 )
          v52 = a9;
        *((_DWORD *)MatchingConnection + 435) = v52;
      }
      WDiagGetTime((LPFILETIME)MatchingConnection + 211);
      *((_QWORD *)MatchingConnection + 213) = v77;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 131, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
      }
      v49 = (int *)((char *)MatchingConnection + 1840);
      v48 = (char *)MatchingConnection + 1520;
      v50 = 3;
    }
    else
    {
      if ( v43 != v44 && *((_BYTE *)v43 + 225) && (*((_BYTE *)v43 + 228) & 0x10) != 0 )
      {
        v62 = a8;
        WPP_SF_DD(v43[27], 128, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids, a9);
        v44 = &WPP_GLOBAL_Control;
      }
      if ( a7 )
        *((_DWORD *)MatchingConnection + 372) = a7;
      v47 = a8;
      if ( !a8 )
        v47 = a9;
      *((_DWORD *)MatchingConnection + 374) = v47;
      if ( WPP_GLOBAL_Control != v44
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 129, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
      }
      v48 = (char *)MatchingConnection + 1280;
      v49 = &v79;
      v50 = 2;
    }
    WDiagLogStatisticsDifference(a1, v50, v48, v49, v62);
    goto LABEL_127;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      123,
      (unsigned int)&WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids,
      (_DWORD)v30,
      (__int64)v29);
  }
  WDiagReleaseExLock(
    MatchingConnection,
    (struct _WD_CONNECTION_CONTEXT *)((char *)MatchingConnection + 3920),
    "WDiagConnectCompletion",
    0xB23u);
  WDiagReleaseExLock((void *)a1, (struct _WDIAG_RW_LOCK *)(a1 + 3352), "WDiagConnectCompletion", 0xB24u);
  if ( !v16 )
    goto LABEL_38;
  v34 = v16;
LABEL_37:
  FreeWLMem(v34);
LABEL_38:
  if ( v19 )
    FreeWLMem(v19);
  v28 = v67;
LABEL_41:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 139, &WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids);
  return v28;
}

```

## disassembly

```asm
0x18001ff4c  mov     [rsp-8+arg_10], rbx
0x18001ff51  push    rbp
0x18001ff52  push    rsi
0x18001ff53  push    rdi
0x18001ff54  push    r12
0x18001ff56  push    r13
0x18001ff58  push    r14
0x18001ff5a  push    r15
0x18001ff5c  lea     rbp, [rsp-0FD0h]
0x18001ff64  mov     eax, 10D0h
0x18001ff69  call    _alloca_probe
0x18001ff6e  sub     rsp, rax
0x18001ff71  mov     rax, cs:__security_cookie
0x18001ff78  xor     rax, rsp
0x18001ff7b  mov     [rbp+1000h+var_40], rax
0x18001ff82  mov     rbx, r9
0x18001ff85  mov     rdi, rdx
0x18001ff88  mov     r14, rcx
0x18001ff8b  xor     r12d, r12d
0x18001ff8e  mov     [rsp+1100h+var_1084], r12d
0x18001ff93  mov     [rsp+1100h+var_1088], r12d
0x18001ff98  xor     eax, eax
0x18001ff9a  mov     [rbp+1000h+Buf1], eax
0x18001ff9d  mov     [rbp+1000h+var_107C], ax
0x18001ffa1  mov     [rbp+1000h+var_1050], r12d
0x18001ffa5  xor     edx, edx; Val
0x18001ffa7  mov     r8d, 9Ch; Size
0x18001ffad  lea     rcx, [rbp+1000h+var_104C]; void *
0x18001ffb1  call    memset_0
0x18001ffb6  xor     edx, edx; Val
0x18001ffb8  mov     r8d, 0F68h; Size
0x18001ffbe  lea     rcx, [rbp+1000h+var_FB0]; void *
0x18001ffc2  call    memset_0
0x18001ffc7  mov     [rsp+1100h+var_10AC], r12d
0x18001ffcc  mov     [rsp+1100h+var_10A8], r12d
0x18001ffd1  lea     rax, WPP_GLOBAL_Control
0x18001ffd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffdf  cmp     rcx, rax
0x18001ffe2  jz      short loc_180020008
0x18001ffe4  test    dword ptr [rcx+0E4h], 200h
0x18001ffee  jz      short loc_180020008
0x18001fff0  lea     edx, [r12+79h]
0x18001fff5  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x18001fffc  mov     rcx, [rcx+0D8h]
0x180020003  call    WPP_SF_
0x180020008  mov     r13d, [rbp+1000h+arg_40]
0x18002000f  mov     ecx, r13d; unsigned int
0x180020012  call    ?StopWlanDbgTracing@@YAXK@Z; StopWlanDbgTracing(ulong)
0x180020017  call    cs:__imp_GetTickCount64
0x18002001d  mov     r15, rax
0x180020020  mov     qword ptr [rbp+1000h+var_1070], rax
0x180020024  mov     rsi, r12
0x180020027  mov     [rsp+1100h+var_10A0], r12
0x18002002c  mov     [rbp+1000h+var_1060], r12
0x180020030  mov     [rsp+1100h+var_1098], r12
0x180020035  mov     [rbp+1000h+var_1078], r12
0x180020039  xor     ecx, ecx
0x18002003b  cmp     [rbp+1000h+arg_50], ecx
0x180020041  jnz     loc_1800200FC
0x180020047  mov     [rsp+1100h+var_10B8], rcx
0x18002004c  mov     [rsp+1100h+var_10C0], rcx
0x180020051  lea     rax, [rsp+1100h+var_1088]
0x180020056  mov     [rsp+1100h+var_10C8], rax
0x18002005b  lea     rax, [rsp+1100h+var_1084]
0x180020060  mov     qword ptr [rsp+1100h+var_10D0], rax
0x180020065  mov     [rsp+1100h+var_10D8], rcx
0x18002006a  lea     rax, [rbp+1000h+Buf1]
0x18002006e  mov     qword ptr [rsp+1100h+var_10E0], rax; enum _DOT11_BSS_TYPE
0x180020073  xor     r9d, r9d
0x180020076  lea     r8, [rbp+1000h+var_1050]
0x18002007a  mov     rcx, r14
0x18002007d  call    ?WDiagQueryDot11DataEx@@YAKPEAU_WD_INTERFACE_CONTEXT@@W4WDIAG_STATISTICS_QUERY_REASON@@PEAUWDIAG_PACKET_STATISTICS@@PEAU_DOT11_SSID@@PEAY05EPEAUWDIAG_SIGNAL_QUALITY@@PEAK666@Z; WDiagQueryDot11DataEx(_WD_INTERFACE_CONTEXT *,WDIAG_STATISTICS_QUERY_REASON,WDIAG_PACKET_STATISTICS *,_DOT11_SSID *,uchar (*)[6],WDIAG_SIGNAL_QUALITY *,ulong *,ulong *,ulong *,ulong *)
0x180020082  mov     rdx, r14
0x180020085  lea     rcx, [rsp+1100h+var_1090]
0x18002008a  call    ?WDiagGetConnectionInfo@@YA?AV?$unique_ptr@UDOT11_CONNECTION_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@PEAU_WD_INTERFACE_CONTEXT@@@Z; WDiagGetConnectionInfo(_WD_INTERFACE_CONTEXT *)
0x18002008f  mov     rsi, [rax]
0x180020092  mov     [rsp+1100h+var_10A0], rsi
0x180020097  xor     edx, edx
0x180020099  mov     [rax], rdx
0x18002009c  mov     [rbp+1000h+var_1060], rsi
0x1800200a0  mov     rcx, [rsp+1100h+var_1090]
0x1800200a5  mov     [rsp+1100h+var_1090], rdx
0x1800200aa  test    rcx, rcx
0x1800200ad  jz      short loc_1800200B4
0x1800200af  call    FreeWLMem
0x1800200b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_57825957@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_57825957@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_57825957> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_57825957>::GetImpl(void)'::`2'::impl
0x1800200bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_57825957@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_57825957>::__private_IsEnabled(void)
0x1800200c0  test    al, al
0x1800200c2  jz      short loc_1800200FC
0x1800200c4  mov     rdx, r14
0x1800200c7  lea     rcx, [rsp+1100h+var_1098]
0x1800200cc  call    ?WDiagGetConnectionAttributes@@YA?AV?$unique_ptr@U_WLAN_CONNECTION_ATTRIBUTES@@U?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@PEBU_WD_INTERFACE_CONTEXT@@@Z; WDiagGetConnectionAttributes(_WD_INTERFACE_CONTEXT const *)
0x1800200d1  mov     rdx, rax
0x1800200d4  lea     rcx, [rbp+1000h+var_1078]
0x1800200d8  call    ??4?$unique_ptr@U_WLAN_CONNECTION_ATTRIBUTES@@U?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_WLAN_CONNECTION_ATTRIBUTES,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>::operator=(wistd::unique_ptr<_WLAN_CONNECTION_ATTRIBUTES,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>> &&)
0x1800200dd  mov     rcx, [rsp+1100h+var_1098]
0x1800200e2  xor     eax, eax
0x1800200e4  mov     [rsp+1100h+var_1098], rax
0x1800200e9  test    rcx, rcx
0x1800200ec  jz      short loc_1800200F3
0x1800200ee  call    FreeWLMem
0x1800200f3  mov     r12, [rbp+1000h+var_1078]
0x1800200f7  mov     [rsp+1100h+var_1098], r12
0x1800200fc  lea     rdx, [rsp+1100h+var_10AC]; unsigned int *
0x180020101  mov     rcx, r14; struct _WD_INTERFACE_CONTEXT *
0x180020104  call    ?WDiagQueryIntfOpmode@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAK@Z; WDiagQueryIntfOpmode(_WD_INTERFACE_CONTEXT *,ulong *)
0x180020109  mov     ecx, 1
0x18002010e  test    eax, eax
0x180020110  jnz     short loc_180020122
0x180020112  mov     eax, [rsp+1100h+var_10A8]
0x180020116  cmp     [rsp+1100h+var_10AC], 4
0x18002011b  cmovz   eax, ecx
0x18002011e  mov     [rsp+1100h+var_10A8], eax
0x180020122  lea     rdx, [r14+0D18h]; struct _WDIAG_RW_LOCK *
0x180020129  mov     r9d, 0AF9h; unsigned int
0x18002012f  lea     r8, aWdiagconnectco; "WDiagConnectCompletion"
0x180020136  mov     rcx, r14; void *
0x180020139  call    ?WDiagAcquireExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagAcquireExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18002013e  mov     eax, 1
0x180020143  mov     [rsp+1100h+var_10D0], eax; unsigned int
0x180020147  mov     dword ptr [rsp+1100h+var_10D8], eax; unsigned int
0x18002014b  mov     rdx, rdi; void *
0x18002014e  mov     rcx, r14; struct _WD_INTERFACE_CONTEXT *
0x180020151  call    ?FindMatchingConnection@@YAPEAU_WD_CONNECTION_CONTEXT@@PEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_PM_PROFILE@@PEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@KK@Z; FindMatchingConnection(_WD_INTERFACE_CONTEXT *,void *,_PM_PROFILE *,_DOT11_SSID *,_DOT11_BSS_TYPE,ulong,ulong)
0x180020156  mov     rdi, rax
0x180020159  test    rax, rax
0x18002015c  jnz     loc_1800201E7
0x180020162  mov     r9d, 0B03h; unsigned int
0x180020168  lea     r8, aWdiagconnectco; "WDiagConnectCompletion"
0x18002016f  lea     rdx, [r14+0D18h]; struct _WDIAG_RW_LOCK *
0x180020176  mov     rcx, r14; void *
0x180020179  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18002017e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020185  lea     rax, WPP_GLOBAL_Control
0x18002018c  cmp     rcx, rax
0x18002018f  jz      short loc_1800201BD
0x180020191  cmp     byte ptr [rcx+0E1h], 1
0x180020198  jb      short loc_1800201BD
0x18002019a  lea     r15d, [rdi+10h]
0x18002019e  test    [rcx+0E4h], r15b
0x1800201a5  jz      short loc_1800201BD
0x1800201a7  lea     edx, [rdi+7Ah]
0x1800201aa  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x1800201b1  mov     rcx, [rcx+0D8h]
0x1800201b8  call    WPP_SF_
0x1800201bd  mov     r13d, 490h
0x1800201c3  test    r12, r12
0x1800201c6  jz      short loc_1800201D1
0x1800201c8  mov     rcx, r12
0x1800201cb  call    FreeWLMem
0x1800201d0  nop
0x1800201d1  test    rsi, rsi
0x1800201d4  jz      loc_18002032E
0x1800201da  mov     rcx, rsi
0x1800201dd  call    FreeWLMem
0x1800201e2  jmp     loc_18002032E
0x1800201e7  mov     eax, 490h
0x1800201ec  mov     [rsp+1100h+var_10AC], eax
0x1800201f0  lea     rcx, [rbp+1000h+var_FB0]; struct WDIAG_SQM_RECORD *
0x1800201f4  call    ?WdiagInitSqmRecord@@YAXPEAUWDIAG_SQM_RECORD@@@Z; WdiagInitSqmRecord(WDIAG_SQM_RECORD *)
0x1800201f9  lea     rdx, [rdi+0F50h]; struct _WDIAG_RW_LOCK *
0x180020200  mov     r9d, 0B0Dh; unsigned int
0x180020206  lea     r8, aWdiagconnectco; "WDiagConnectCompletion"
0x18002020d  mov     rcx, rdi; void *
0x180020210  call    ?WDiagAcquireExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagAcquireExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x180020215  mov     dword ptr [rdi+4B4h], 1
0x18002021f  mov     [rdi+4B8h], r15
0x180020226  mov     eax, [rbp+1000h+arg_58]
0x18002022c  mov     [rdi+0FE8h], eax
0x180020232  mov     eax, [rbp+1000h+arg_5C]
0x180020238  mov     [rdi+0FE4h], eax
0x18002023e  mov     al, [rbp+1000h+arg_60]
0x180020244  mov     [rdi+0FECh], al
0x18002024a  mov     r15d, 10h
0x180020250  xor     r10d, r10d
0x180020253  test    rbx, rbx
0x180020256  jz      loc_18002043C
0x18002025c  add     rbx, 18h
0x180020260  lea     r9, [rdi+58h]
0x180020264  mov     rax, r9
0x180020267  mov     r8, rbx
0x18002026a  sub     r8, r9
0x18002026d  movzx   edx, word ptr [rax]
0x180020270  movzx   ecx, word ptr [rax+r8]
0x180020275  sub     edx, ecx
0x180020277  jnz     short loc_180020281
0x180020279  add     rax, 2
0x18002027d  test    ecx, ecx
0x18002027f  jnz     short loc_18002026D
0x180020281  test    edx, edx
0x180020283  jz      loc_18002043C
0x180020289  cmp     [r9], r10w
0x18002028d  jz      loc_180020392
0x180020293  mov     rcx, cs:WPP_GLOBAL_Control
0x18002029a  lea     rax, WPP_GLOBAL_Control
0x1800202a1  cmp     rcx, rax
0x1800202a4  jz      short loc_1800202D5
0x1800202a6  cmp     byte ptr [rcx+0E1h], 1
0x1800202ad  jb      short loc_1800202D5
0x1800202af  test    [rcx+0E4h], r15b
0x1800202b6  jz      short loc_1800202D5
0x1800202b8  mov     edx, 7Bh ; '{'
0x1800202bd  mov     qword ptr [rsp+1100h+var_10E0], rbx
0x1800202c2  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x1800202c9  mov     rcx, [rcx+0D8h]
0x1800202d0  call    WPP_SF_SS
0x1800202d5  mov     r9d, 0B23h; unsigned int
0x1800202db  lea     r8, aWdiagconnectco; "WDiagConnectCompletion"
0x1800202e2  lea     rdx, [rdi+0F50h]; struct _WDIAG_RW_LOCK *
0x1800202e9  mov     rcx, rdi; void *
0x1800202ec  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x1800202f1  mov     r9d, 0B24h; unsigned int
0x1800202f7  lea     r8, aWdiagconnectco; "WDiagConnectCompletion"
0x1800202fe  lea     rdx, [r14+0D18h]; struct _WDIAG_RW_LOCK *
0x180020305  mov     rcx, r14; void *
0x180020308  call    ?WDiagReleaseExLock@@YAXPEAXPEAU_WDIAG_RW_LOCK@@PEADK@Z; WDiagReleaseExLock(void *,_WDIAG_RW_LOCK *,char *,ulong)
0x18002030d  nop
0x18002030e  test    r12, r12
0x180020311  jz      short loc_18002031C
0x180020313  mov     rcx, r12
0x180020316  call    FreeWLMem
0x18002031b  nop
0x18002031c  test    rsi, rsi
0x18002031f  jz      short loc_180020329
0x180020321  mov     rcx, rsi
0x180020324  call    FreeWLMem
0x180020329  mov     r13d, [rsp+1100h+var_10AC]
0x18002032e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020335  lea     rax, WPP_GLOBAL_Control
0x18002033c  cmp     rcx, rax
0x18002033f  jz      short loc_180020365
0x180020341  test    dword ptr [rcx+0E4h], 200h
0x18002034b  jz      short loc_180020365
0x18002034d  mov     edx, 8Bh
0x180020352  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x180020359  mov     rcx, [rcx+0D8h]
0x180020360  call    WPP_SF_
0x180020365  mov     eax, r13d
0x180020368  mov     rcx, [rbp+1000h+var_40]
0x18002036f  xor     rcx, rsp; StackCookie
0x180020372  call    __security_check_cookie
0x180020377  mov     rbx, [rsp+1100h+arg_10]
0x18002037f  add     rsp, 10D0h
0x180020386  pop     r15
0x180020388  pop     r14
0x18002038a  pop     r13
0x18002038c  pop     r12
0x18002038e  pop     rdi
0x18002038f  pop     rsi
0x180020390  pop     rbp
0x180020391  retn
0x180020392  mov     [rsp+1100h+var_10B0], 1
0x180020397  mov     rcx, cs:WPP_GLOBAL_Control
0x18002039e  lea     rax, WPP_GLOBAL_Control
0x1800203a5  cmp     rcx, rax
0x1800203a8  jz      short loc_1800203DC
0x1800203aa  cmp     byte ptr [rcx+0E1h], 3
0x1800203b1  jb      short loc_1800203DC
0x1800203b3  test    [rcx+0E4h], r15b
0x1800203ba  jz      short loc_1800203DC
0x1800203bc  mov     edx, 7Ch ; '|'
0x1800203c1  mov     qword ptr [rsp+1100h+var_10E0], rbx
0x1800203c6  lea     r8, WPP_bcd32bcee69034a4b765a1a21c01e351_Traceguids
0x1800203cd  mov     rcx, [rcx+0D8h]
0x1800203d4  call    WPP_SF_SS
0x1800203d9  xor     r10d, r10d
0x1800203dc  lea     rax, [rdi+0D4Ch]
0x1800203e3  mov     ecx, 4
0x1800203e8  movups  xmm0, xmmword ptr [rbx]
0x1800203eb  movups  xmmword ptr [rax], xmm0
0x1800203ee  movups  xmm1, xmmword ptr [rbx+10h]
0x1800203f2  movups  xmmword ptr [rax+10h], xmm1
0x1800203f6  movups  xmm0, xmmword ptr [rbx+20h]
0x1800203fa  movups  xmmword ptr [rax+20h], xmm0
0x1800203fe  movups  xmm1, xmmword ptr [rbx+30h]
0x180020402  movups  xmmword ptr [rax+30h], xmm1
0x180020406  movups  xmm0, xmmword ptr [rbx+40h]
0x18002040a  movups  xmmword ptr [rax+40h], xmm0
0x18002040e  movups  xmm1, xmmword ptr [rbx+50h]
0x180020412  movups  xmmword ptr [rax+50h], xmm1
0x180020416  movups  xmm0, xmmword ptr [rbx+60h]
0x18002041a  movups  xmmword ptr [rax+60h], xmm0
0x18002041e  movups  xmm1, xmmword ptr [rbx+70h]
0x180020422  movups  xmmword ptr [rax+70h], xmm1
0x180020426  lea     rax, [rax+80h]
0x18002042d  lea     rbx, [rbx+80h]
0x180020434  sub     rcx, 1
0x180020438  jnz     short loc_1800203E8
0x18002043a  jmp     short loc_180020441
0x18002043c  mov     [rsp+1100h+var_10B0], r10b
0x180020441  mov     dword ptr [rsp+1100h+var_1090], r10d
0x180020446  mov     edx, [rbp+1000h+arg_28]
0x18002044c  mov     rcx, rdi
0x18002044f  call    ?WDiagUpdatePasspointInfo@@YAXPEAU_WD_CONNECTION_CONTEXT@@W4PasspointFlag@@@Z; WDiagUpdatePasspointInfo(_WD_CONNECTION_CONTEXT *,PasspointFlag)
0x180020454  mov     ecx, [rsp+1100h+var_1084]
0x180020458  mov     [rdi+6C0h], ecx
0x18002045e  mov     eax, [rsp+1100h+var_1088]
0x180020462  mov     [rdi+6C4h], eax
0x180020468  mov     r8d, 6; Size
0x18002046e  lea     rdx, ?zeroMac@@3QBEB; Buf2
  ... truncated ...
```
