# MSMSecPerformPreAssociateSecurityEx

- ea: `0x180039810`
- end: `0x18003a3ce`
- name: `MSMSecPerformPreAssociateSecurityEx`
- size: `3006`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct DOT11_MSMSEC_CONNECTION_PROFILE *, __int64, struct _DOT11_BSS_LIST *, __int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `47`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800397a0`

## callees

- `0x180001008`
- `0x180001710`
- `0x18000372c`
- `0x1800045b8`
- `0x180006b34`
- `0x18000892c`
- `0x180008998`
- `0x180009e70`
- `0x18000a26c`
- `0x18000b6dc`
- `0x18000e020`
- `0x18000e140`
- `0x180012224`
- `0x1800125b0`
- `0x180013bc0`
- `0x1800148d0`
- `0x180014998`
- `0x1800163e0`
- `0x1800169c0`
- `0x180016a08`
- `0x18001d690`
- `0x18001e594`
- `0x18001eb3c`
- `0x18001ece4`
- `0x18001edd4`
- `0x180025e20`
- `0x180028574`
- `0x18002dba8`
- `0x18002dc9c`
- `0x180030b00`
- `0x180030fec`
- `0x18003161c`
- `0x1800328b0`
- `0x18003455c`
- `0x1800347d0`
- `0x180034ac0`
- `0x1800353d8`
- `0x1800354e0`
- `0x180039810`
- `0x180040f44`
- `0x180041578`
- `0x180043a30`
- `0x18004456c`
- `0x180051ff4`
- `0x1800558c0`
- `0x18005ca3c`
- `0x180078be8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18003a336`
- `MobileNetworking!ReleaseWriteLock` at `0x18003a336`

## string_xrefs

- `0x1800398f7`: `MSMSecPerformPreAssociateSecurityEx`
- `0x18003a32c`: `MSMSecPerformPreAssociateSecurityEx`
- `0x18003a357`: `MSMSecPerformPreAssociateSecurityEx`
- `0x18003a36b`: `MSMSecPerformPreAssociateSecurityEx`

## pseudocode

```c
__int64 __fastcall MSMSecPerformPreAssociateSecurityEx(
        void ***a1,
        void *a2,
        struct MSMSEC_NW_DESC *a3,
        struct MSMSEC_HOST_DESC *a4,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a5,
        __int64 a6,
        struct _DOT11_BSS_LIST *a7,
        void *a8,
        unsigned int a9,
        __int64 a10,
        unsigned int *a11)
{
  struct MSMSEC_INTF_CONTEXT *v13; // rsi
  unsigned int v14; // edi
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v17; // r15
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  int v21; // edx
  int v22; // r8d
  PVOID *v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rax
  unsigned int v28; // r10d
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // r11
  __int64 v32; // r8
  char v33; // r10
  struct MSMSEC_HOST_DESC *v34; // r12
  unsigned int matched; // eax
  __int64 v36; // rax
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v37; // r14
  _DWORD *v38; // rbx
  int v39; // ecx
  int v40; // ecx
  char *v41; // rax
  char *v42; // rax
  _QWORD *v43; // rax
  int v44; // r8d
  int v45; // r9d
  unsigned int v46; // ecx
  int v47; // eax
  int v48; // ecx
  void *v49; // rbx
  struct API_CONTEXT_BASE *v50; // r15
  __int128 v51; // xmm0
  _QWORD *v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rax
  void *v55; // rdx
  struct DOT11_MSMSEC_RUNTIME_STATE *v56; // rdx
  __int64 v57; // rcx
  int v59; // [rsp+60h] [rbp-A0h] BYREF
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v60; // [rsp+68h] [rbp-98h]
  int v61; // [rsp+70h] [rbp-90h]
  int v62; // [rsp+74h] [rbp-8Ch]
  int v63; // [rsp+78h] [rbp-88h]
  int v64; // [rsp+7Ch] [rbp-84h]
  int v65; // [rsp+80h] [rbp-80h]
  struct MSMSEC_INTF_CONTEXT *v66; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v67; // [rsp+90h] [rbp-70h] BYREF
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v68; // [rsp+98h] [rbp-68h] BYREF
  struct DOT11_MSMSEC_RUNTIME_STATE *v69; // [rsp+A0h] [rbp-60h] BYREF
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v70; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v71; // [rsp+B0h] [rbp-50h] BYREF
  struct MSMSEC_HOST_DESC *v72; // [rsp+B8h] [rbp-48h] BYREF
  void *v73; // [rsp+C0h] [rbp-40h]
  unsigned int *v74; // [rsp+C8h] [rbp-38h]
  struct API_CONTEXT_BASE *v75; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v76; // [rsp+D8h] [rbp-28h] BYREF
  char *v77; // [rsp+E0h] [rbp-20h] BYREF
  void *v78; // [rsp+E8h] [rbp-18h]
  __int64 v79; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v80; // [rsp+F8h] [rbp-8h]
  _BYTE v81[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v82[64]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v83; // [rsp+160h] [rbp+60h]

  v78 = a8;
  v13 = 0;
  v74 = a11;
  v73 = a2;
  v60 = 0;
  v68 = 0;
  v72 = a4;
  v66 = 0;
  v59 = 0;
  v62 = 0;
  v63 = 0;
  v61 = 0;
  v64 = 0;
  v65 = 0;
  v75 = 0;
  v70 = 0;
  v71 = 0;
  v67 = 327679;
  memset_0(v82, 0, 0x42u);
  v69 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 46, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v14 = IncThreadCountAndCheckInitializedEx("MSMSecPerformPreAssociateSecurityEx", 305);
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 47, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v14);
    goto LABEL_137;
  }
  if ( !a1 || !a3 || !v72 || !(unsigned int)IsNwDescValid(a3) || !a5 || !v74 )
  {
    v14 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 48, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
LABEL_137:
    if ( !v74 )
      goto LABEL_139;
    goto LABEL_138;
  }
  if ( !a7 || (unsigned int)IsBSSListValid(a7) )
  {
    v14 = MSMSecDuplicateRuntimeState(a6, &v69);
    if ( v14 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_129;
      v16 = 50;
LABEL_23:
      WPP_SF_d(v15[7], v16, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v14);
LABEL_129:
      v17 = v60;
      goto LABEL_130;
    }
    v14 = MSMSecCheckConnectFlags(a9, a5);
    if ( v14 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_129;
      v16 = 51;
      goto LABEL_23;
    }
    v14 = CopyMSMSecConfig(a5, &v68);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 52, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v14);
      v17 = v68;
      goto LABEL_130;
    }
    v17 = v68;
    v60 = v68;
    v14 = StripUndecryptableKeys(v68);
    if ( v14 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_130;
      v19 = 53;
      goto LABEL_37;
    }
    v14 = CheckProfileValidForConnect(v17);
    if ( v14 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_130;
      v19 = 54;
      goto LABEL_37;
    }
    v14 = SecMgrValidateRefAndLockAdapter(a1, &v66);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v14);
      v13 = v66;
      goto LABEL_130;
    }
    v59 = 33;
    WlanSsidToWideString(a3, v82, &v59);
    v59 = 1;
    v83 = 0;
    v23 = (PVOID *)WPP_GLOBAL_Control;
    v13 = v66;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      {
        WPP_SF_LSqq(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          v21,
          v22,
          *((_DWORD *)v66 + 624),
          (__int64)v82,
          (char)a1,
          (char)v73);
        v23 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 68) & 2) != 0 )
        WPP_SF_LqDDDDDD(
          v23[7],
          57,
          &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          *((unsigned int *)v13 + 624),
          v13,
          *((unsigned __int8 *)v13 + 2360),
          *((unsigned __int8 *)v13 + 2361),
          *((unsigned __int8 *)v13 + 2362),
          *((unsigned __int8 *)v13 + 2363),
          *((unsigned __int8 *)v13 + 2364),
          *((unsigned __int8 *)v13 + 2365));
    }
    if ( (byte_1800AED45 & 1) != 0 )
      McTemplateU0qjb6z_EventWriteTransfer(
        (unsigned int)v82,
        v21,
        *((_DWORD *)v13 + 624),
        (_DWORD)v13 + 32,
        (__int64)v13 + 2360,
        (__int64)v82);
    MSMSecLogProfile(v17, a3);
    if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v13 + 681), 1) )
    {
      v14 = 5023;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v27 = IntfActionStr(1, v24, v25, v26);
        v30 = IntfSecStateStr(v28, v29, v27);
        WPP_SF_SLSL(
          *(_QWORD *)(v31 + 56),
          60,
          (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          v30,
          v33,
          v32,
          1);
      }
      goto LABEL_130;
    }
    v34 = v72;
    matched = PerformCapabilityMatchInternal(v13, a3, v72, v17, a7, &v70, &v67);
    v14 = matched;
    if ( matched )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_130;
      v19 = 61;
      v20 = matched;
      goto LABEL_38;
    }
    v62 = 1;
    v36 = wil::details::static_lazy<WlanTriageProvider>::get();
    v37 = v70;
    v38 = *(_DWORD **)(v36 + 8);
    if ( *v38 > 4u && (unsigned __int8)tlgKeywordOn(v38) )
    {
      if ( (*(_DWORD *)v37 & 0x1000) != 0 )
      {
        v39 = *((_DWORD *)v37 + 35);
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( v40 )
          {
            if ( v40 == 1 )
              v41 = "Hardware";
            else
              v41 = "Unknown";
          }
          else
          {
            v41 = "Software";
          }
        }
        else
        {
          v41 = "Unspecified";
        }
      }
      else
      {
        v41 = "No";
      }
      v72 = (struct MSMSEC_HOST_DESC *)v41;
      if ( (unsigned int)RawDataIsEmpty((char *)v37 + 64) )
      {
        v42 = "Absent";
      }
      else
      {
        v42 = "Passphrase";
        if ( (*(_BYTE *)v37 & 2) == 0 )
          v42 = "MasterKey";
      }
      v66 = (struct MSMSEC_INTF_CONTEXT *)v42;
      v43 = (_QWORD *)stringify::ToLogString(v81, (char *)v37 + 16);
      if ( v43[3] > 0xFu )
        v43 = (_QWORD *)*v43;
      v46 = *(_DWORD *)a3;
      v76 = v43;
      if ( v46 > 0xFFFF )
        LOWORD(v46) = -1;
      v80 = v46;
      v79 = (__int64)a3 + 4;
      v77 = (char *)v13 + 32;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v38,
        (unsigned int)byte_1800A25A1,
        v44,
        v45,
        (__int64)&v77,
        (__int64)&v79,
        (__int64)&v76,
        (__int64)&v66,
        (__int64)&v72);
      std::string::~string(v81);
    }
    v14 = CopyMSMSecConfig(v17, &v71);
    if ( v14 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_130;
      v19 = 62;
      goto LABEL_37;
    }
    v63 = 1;
    v14 = PmkCacheInitializeProfile((struct MSMSEC_INTF_CONTEXT *)((char *)v13 + 3000), v37);
    if ( v14 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_130;
      v19 = 63;
      goto LABEL_37;
    }
    v64 = 1;
    v14 = PreAuthInitializeProfile((struct MSMSEC_INTF_CONTEXT *)((char *)v13 + 2912), v37);
    if ( v14 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_130;
      v19 = 64;
      goto LABEL_37;
    }
    v65 = 1;
    if ( v37 && (*(_DWORD *)v37 & 0x100) != 0 )
    {
      v47 = *((_DWORD *)v37 + 31);
      *((_DWORD *)v13 + 830) = v47;
      v48 = 1000 * v47;
    }
    else
    {
      v48 = -1;
    }
    v49 = v73;
    *((_DWORD *)v13 + 830) = v48;
    v14 = AllocateAndInitializeAPIContextPreAssociateSecurity(v13, v49, &v75);
    if ( v14 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_130;
      v19 = 66;
LABEL_37:
      v20 = v14;
LABEL_38:
      WPP_SF_d(v18[7], v19, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v20);
LABEL_130:
      if ( v69 )
        MSMSecFreeRuntimeState(v69);
      if ( v17 )
        FreeMSMSecConfig(&v68);
      goto LABEL_138;
    }
    v50 = v75;
    v14 = QueueIntfWorkerThread(v13, v75);
    if ( v14 )
    {
      v61 = 1;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_129;
      v16 = 67;
      goto LABEL_23;
    }
    v51 = *(_OWORD *)a3;
    v61 = 0;
    *(_OWORD *)((char *)v13 + 2728) = v51;
    *(_OWORD *)((char *)v13 + 2744) = *((_OWORD *)a3 + 1);
    *(_OWORD *)((char *)v13 + 2760) = *((_OWORD *)a3 + 2);
    *((_QWORD *)v13 + 347) = *(_QWORD *)v34;
    if ( a10 )
    {
      if ( *(_BYTE *)a10
        || *(_BYTE *)(a10 + 1)
        || *(_BYTE *)(a10 + 2)
        || *(_BYTE *)(a10 + 3)
        || *(_BYTE *)(a10 + 4)
        || *(_BYTE *)(a10 + 5) )
      {
        *((_DWORD *)v13 + 590) = *(_DWORD *)a10;
        *((_WORD *)v13 + 1182) = *(_WORD *)(a10 + 4);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
        {
          WPP_SF_DDDDDD(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            68,
            &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            *((unsigned __int8 *)v13 + 2360),
            *((unsigned __int8 *)v13 + 2361),
            *((unsigned __int8 *)v13 + 2362),
            *((unsigned __int8 *)v13 + 2363));
          v49 = v73;
        }
        goto LABEL_125;
      }
      v52 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      {
LABEL_125:
        v54 = v71;
        *((_QWORD *)v13 + 348) = v37;
        v70 = 0;
        v62 = 0;
        *((_QWORD *)v13 + 349) = v54;
        v71 = 0;
        v63 = 0;
        v64 = 0;
        v65 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
          WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 71, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
        v55 = v78;
        *((_QWORD *)v13 + 328) = v49;
        SecMgrSetNotificationSession(v13, v55);
        v56 = v69;
        *((_DWORD *)v13 + 660) = a9;
        SecMgrSetRTStateIntf(v13, v56);
        v57 = *((_QWORD *)v50 + 1);
        v69 = 0;
        SecMgrIntfStateTransition(v57, 2, 327679);
        goto LABEL_129;
      }
      v53 = 69;
    }
    else
    {
      v52 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
        goto LABEL_125;
      v53 = 70;
    }
    WPP_SF_(v52[7], v53, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_125;
  }
  v14 = 87;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
LABEL_138:
  *v74 = v67;
LABEL_139:
  if ( v61 )
    FreeAPIContextPreAssociateSecurity(&v75);
  if ( v62 )
    FreeMSMSecConfig(&v70);
  if ( v63 )
    FreeMSMSecConfig(&v71);
  if ( v64 )
    PmkCacheDeinitializeProfile((struct MSMSEC_INTF_CONTEXT *)((char *)v13 + 3000));
  if ( v65 )
    PreAuthDeinitializeProfile((struct MSMSEC_INTF_CONTEXT *)((char *)v13 + 2912));
  if ( v59 )
  {
    TraceAdapterId(*((_DWORD *)v13 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(v13, (char *)v13 + 2512, "MSMSecPerformPreAssociateSecurityEx", 553);
    TraceAdapterId(*((_DWORD *)v13 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v13, "MSMSecPerformPreAssociateSecurityEx", 553);
  }
  DecThreadCountEx("MSMSecPerformPreAssociateSecurityEx", 555);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 72, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180039810  push    rbp
0x180039812  push    rbx
0x180039813  push    rsi
0x180039814  push    rdi
0x180039815  push    r12
0x180039817  push    r13
0x180039819  push    r14
0x18003981b  push    r15
0x18003981d  lea     rbp, [rsp-88h]
0x180039825  sub     rsp, 188h
0x18003982c  mov     rax, cs:__security_cookie
0x180039833  xor     rax, rsp
0x180039836  mov     [rbp+0C0h+var_50], rax
0x18003983a  mov     rax, [rbp+0C0h+arg_38]
0x180039841  xor     edi, edi
0x180039843  mov     rbx, [rbp+0C0h+arg_20]
0x18003984a  mov     r13, r8
0x18003984d  mov     r15, [rbp+0C0h+arg_28]
0x180039854  mov     r14, rcx
0x180039857  mov     r12, [rbp+0C0h+arg_30]
0x18003985e  lea     rcx, [rbp+0C0h+var_A0]; void *
0x180039862  mov     [rbp+0C0h+var_D8], rax
0x180039866  lea     r8d, [rdi+42h]; Size
0x18003986a  mov     rax, [rbp+0C0h+arg_50]
0x180039871  mov     esi, edi
0x180039873  mov     [rbp+0C0h+var_F8], rax
0x180039877  mov     eax, edi
0x180039879  mov     [rbp+0C0h+var_100], rdx
0x18003987d  xor     edx, edx; Val
0x18003987f  mov     [rsp+1C0h+var_158], rax
0x180039884  mov     [rbp+0C0h+var_128], rax
0x180039888  mov     [rbp+0C0h+var_108], r9
0x18003988c  mov     [rbp+0C0h+var_138], rdi
0x180039890  mov     [rsp+1C0h+var_160], edi
0x180039894  mov     [rsp+1C0h+var_14C], edi
0x180039898  mov     [rsp+1C0h+var_148], edi
0x18003989c  mov     [rsp+1C0h+var_150], edi
0x1800398a0  mov     [rsp+1C0h+var_144], edi
0x1800398a4  mov     [rbp+0C0h+var_140], edi
0x1800398a7  mov     [rbp+0C0h+var_F0], rdi
0x1800398ab  mov     [rbp+0C0h+var_118], rdi
0x1800398af  mov     [rbp+0C0h+var_110], rdi
0x1800398b3  mov     [rbp+0C0h+var_130], 4FFFFh
0x1800398ba  call    memset_0
0x1800398bf  mov     [rbp+0C0h+var_120], rdi
0x1800398c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398ca  lea     rax, WPP_GLOBAL_Control
0x1800398d1  cmp     rcx, rax
0x1800398d4  jz      short loc_1800398F2
0x1800398d6  test    dword ptr [rcx+44h], 100h
0x1800398dd  jz      short loc_1800398F2
0x1800398df  mov     rcx, [rcx+38h]
0x1800398e3  lea     edx, [rdi+2Eh]
0x1800398e6  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800398ed  call    WPP_SF_
0x1800398f2  mov     edx, 131h; int
0x1800398f7  lea     rcx, aMsmsecperformp_2; "MSMSecPerformPreAssociateSecurityEx"
0x1800398fe  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x180039903  mov     edi, eax
0x180039905  test    eax, eax
0x180039907  jz      short loc_180039947
0x180039909  mov     rcx, cs:WPP_GLOBAL_Control
0x180039910  lea     rax, WPP_GLOBAL_Control
0x180039917  cmp     rcx, rax
0x18003991a  jz      loc_18003A2A0
0x180039920  test    byte ptr [rcx+44h], 1
0x180039924  jz      loc_18003A2A0
0x18003992a  mov     rcx, [rcx+38h]
0x18003992e  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180039935  mov     edx, 2Fh ; '/'
0x18003993a  mov     r9d, edi
0x18003993d  call    WPP_SF_d
0x180039942  jmp     loc_18003A2A0
0x180039947  test    r14, r14
0x18003994a  jz      loc_18003A26F
0x180039950  test    r13, r13
0x180039953  jz      loc_18003A26F
0x180039959  cmp     [rbp+0C0h+var_108], rsi
0x18003995d  jz      loc_18003A26F
0x180039963  mov     rcx, r13
0x180039966  call    IsNwDescValid
0x18003996b  test    eax, eax
0x18003996d  jz      loc_18003A26F
0x180039973  test    rbx, rbx
0x180039976  jz      loc_18003A26F
0x18003997c  cmp     [rbp+0C0h+var_F8], rsi
0x180039980  jz      loc_18003A26F
0x180039986  test    r12, r12
0x180039989  jz      short loc_1800399D3
0x18003998b  mov     rcx, r12; struct _DOT11_BSS_LIST *
0x18003998e  call    ?IsBSSListValid@@YAHPEAU_DOT11_BSS_LIST@@@Z; IsBSSListValid(_DOT11_BSS_LIST *)
0x180039993  test    eax, eax
0x180039995  jnz     short loc_1800399D3
0x180039997  lea     edi, [rax+57h]
0x18003999a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800399a1  lea     r14, WPP_GLOBAL_Control
0x1800399a8  cmp     rcx, r14
0x1800399ab  jz      loc_18003A2A6
0x1800399b1  test    byte ptr [rcx+44h], 1
0x1800399b5  jz      loc_18003A2A6
0x1800399bb  mov     rcx, [rcx+38h]
0x1800399bf  lea     edx, [rax+31h]
0x1800399c2  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800399c9  call    WPP_SF_
0x1800399ce  jmp     loc_18003A2A6
0x1800399d3  lea     rdx, [rbp+0C0h+var_120]
0x1800399d7  mov     rcx, r15
0x1800399da  call    MSMSecDuplicateRuntimeState
0x1800399df  mov     edi, eax
0x1800399e1  test    eax, eax
0x1800399e3  jz      short loc_180039A23
0x1800399e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800399ec  lea     rax, WPP_GLOBAL_Control
0x1800399f3  cmp     rcx, rax
0x1800399f6  jz      loc_18003A24C
0x1800399fc  test    byte ptr [rcx+44h], 1
0x180039a00  jz      loc_18003A24C
0x180039a06  mov     edx, 32h ; '2'
0x180039a0b  mov     rcx, [rcx+38h]
0x180039a0f  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180039a16  mov     r9d, edi
0x180039a19  call    WPP_SF_d
0x180039a1e  jmp     loc_18003A24C
0x180039a23  mov     ecx, [rbp+0C0h+arg_40]; unsigned int
0x180039a29  mov     rdx, rbx; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x180039a2c  call    ?MSMSecCheckConnectFlags@@YAKKPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z; MSMSecCheckConnectFlags(ulong,DOT11_MSMSEC_CONNECTION_PROFILE *)
0x180039a31  mov     edi, eax
0x180039a33  test    eax, eax
0x180039a35  jz      short loc_180039A5F
0x180039a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a3e  lea     rax, WPP_GLOBAL_Control
0x180039a45  cmp     rcx, rax
0x180039a48  jz      loc_18003A24C
0x180039a4e  test    byte ptr [rcx+44h], 1
0x180039a52  jz      loc_18003A24C
0x180039a58  mov     edx, 33h ; '3'
0x180039a5d  jmp     short loc_180039A0B
0x180039a5f  lea     rdx, [rbp+0C0h+var_128]
0x180039a63  mov     rcx, rbx
0x180039a66  call    CopyMSMSecConfig
0x180039a6b  mov     edi, eax
0x180039a6d  test    eax, eax
0x180039a6f  jz      short loc_180039AAB
0x180039a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a78  lea     rax, WPP_GLOBAL_Control
0x180039a7f  cmp     rcx, rax
0x180039a82  jz      short loc_180039AA2
0x180039a84  test    byte ptr [rcx+44h], 1
0x180039a88  jz      short loc_180039AA2
0x180039a8a  mov     rcx, [rcx+38h]
0x180039a8e  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180039a95  mov     edx, 34h ; '4'
0x180039a9a  mov     r9d, edi
0x180039a9d  call    WPP_SF_d
0x180039aa2  mov     r15, [rbp+0C0h+var_128]
0x180039aa6  jmp     loc_18003A251
0x180039aab  mov     r15, [rbp+0C0h+var_128]
0x180039aaf  mov     rcx, r15
0x180039ab2  mov     [rsp+1C0h+var_158], r15
0x180039ab7  call    StripUndecryptableKeys
0x180039abc  mov     edi, eax
0x180039abe  test    eax, eax
0x180039ac0  jz      short loc_180039B00
0x180039ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ac9  lea     rax, WPP_GLOBAL_Control
0x180039ad0  cmp     rcx, rax
0x180039ad3  jz      loc_18003A251
0x180039ad9  test    byte ptr [rcx+44h], 1
0x180039add  jz      loc_18003A251
0x180039ae3  mov     edx, 35h ; '5'
0x180039ae8  mov     r9d, edi
0x180039aeb  mov     rcx, [rcx+38h]
0x180039aef  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180039af6  call    WPP_SF_d
0x180039afb  jmp     loc_18003A251
0x180039b00  mov     rcx, r15; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x180039b03  call    ?CheckProfileValidForConnect@@YAKPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z; CheckProfileValidForConnect(DOT11_MSMSEC_CONNECTION_PROFILE *)
0x180039b08  mov     edi, eax
0x180039b0a  test    eax, eax
0x180039b0c  jz      short loc_180039B36
0x180039b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b15  lea     rax, WPP_GLOBAL_Control
0x180039b1c  cmp     rcx, rax
0x180039b1f  jz      loc_18003A251
0x180039b25  test    byte ptr [rcx+44h], 1
0x180039b29  jz      loc_18003A251
0x180039b2f  mov     edx, 36h ; '6'
0x180039b34  jmp     short loc_180039AE8
0x180039b36  lea     rdx, [rbp+0C0h+var_138]; struct MSMSEC_INTF_CONTEXT **
0x180039b3a  mov     rcx, r14; void *
0x180039b3d  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180039b42  mov     edi, eax
0x180039b44  test    eax, eax
0x180039b46  jz      short loc_180039B82
0x180039b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b4f  lea     rax, WPP_GLOBAL_Control
0x180039b56  cmp     rcx, rax
0x180039b59  jz      short loc_180039B79
0x180039b5b  test    byte ptr [rcx+44h], 1
0x180039b5f  jz      short loc_180039B79
0x180039b61  mov     rcx, [rcx+38h]
0x180039b65  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180039b6c  mov     edx, 37h ; '7'
0x180039b71  mov     r9d, edi
0x180039b74  call    WPP_SF_d
0x180039b79  mov     rsi, [rbp+0C0h+var_138]
0x180039b7d  jmp     loc_18003A251
0x180039b82  lea     r8, [rsp+1C0h+var_160]
0x180039b87  mov     [rsp+1C0h+var_160], 21h ; '!'
0x180039b8f  lea     rdx, [rbp+0C0h+var_A0]
0x180039b93  mov     rcx, r13
0x180039b96  call    WlanSsidToWideString
0x180039b9b  xor     eax, eax
0x180039b9d  mov     [rsp+1C0h+var_160], 1
0x180039ba5  mov     [rbp+0C0h+var_60], ax
0x180039ba9  mov     rbx, cs:WPP_GLOBAL_Control
0x180039bb0  lea     rax, WPP_GLOBAL_Control
0x180039bb7  mov     rsi, [rbp+0C0h+var_138]
0x180039bbb  cmp     rbx, rax
0x180039bbe  jz      loc_180039C77
0x180039bc4  test    byte ptr [rbx+44h], 20h
0x180039bc8  jz      short loc_180039BF8
0x180039bca  mov     rax, [rbp+0C0h+var_100]
0x180039bce  mov     r9d, [rsi+9C0h]
0x180039bd5  mov     rcx, [rbx+38h]
0x180039bd9  mov     [rsp+1C0h+var_190], rax
0x180039bde  lea     rax, [rbp+0C0h+var_A0]
0x180039be2  mov     [rsp+1C0h+var_198], r14
0x180039be7  mov     [rsp+1C0h+var_1A0], rax
0x180039bec  call    WPP_SF_LSqq
0x180039bf1  mov     rbx, cs:WPP_GLOBAL_Control
0x180039bf8  lea     r14, WPP_GLOBAL_Control
0x180039bff  cmp     rbx, r14
0x180039c02  jz      short loc_180039C7E
0x180039c04  test    byte ptr [rbx+44h], 2
0x180039c08  jz      short loc_180039C7E
0x180039c0a  movzx   ecx, byte ptr [rsi+93Ch]
0x180039c11  mov     edx, 39h ; '9'
0x180039c16  movzx   r8d, byte ptr [rsi+93Bh]
0x180039c1e  movzx   r9d, byte ptr [rsi+93Ah]
0x180039c26  movzx   eax, byte ptr [rsi+93Dh]
0x180039c2d  movzx   r10d, byte ptr [rsi+939h]
0x180039c35  movzx   r11d, byte ptr [rsi+938h]
0x180039c3d  mov     [rsp+1C0h+var_170], eax
0x180039c41  mov     [rsp+1C0h+var_178], ecx
0x180039c45  mov     rcx, [rbx+38h]
0x180039c49  mov     dword ptr [rsp+1C0h+var_180], r8d
0x180039c4e  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180039c55  mov     dword ptr [rsp+1C0h+var_188], r9d
0x180039c5a  mov     r9d, [rsi+9C0h]
0x180039c61  mov     dword ptr [rsp+1C0h+var_190], r10d
0x180039c66  mov     dword ptr [rsp+1C0h+var_198], r11d
0x180039c6b  mov     [rsp+1C0h+var_1A0], rsi
0x180039c70  call    WPP_SF_LqDDDDDD
0x180039c75  jmp     short loc_180039C7E
0x180039c77  lea     r14, WPP_GLOBAL_Control
0x180039c7e  test    cs:byte_1800AED45, 1
0x180039c85  jz      short loc_180039CAC
0x180039c87  mov     r8d, [rsi+9C0h]
0x180039c8e  lea     rcx, [rbp+0C0h+var_A0]
0x180039c92  lea     rax, [rsi+938h]
0x180039c99  mov     [rsp+1C0h+var_198], rcx
0x180039c9e  lea     r9, [rsi+20h]
0x180039ca2  mov     [rsp+1C0h+var_1A0], rax
0x180039ca7  call    McTemplateU0qjb6z_EventWriteTransfer
0x180039cac  mov     rdx, r13; struct MSMSEC_NW_DESC *
0x180039caf  mov     rcx, r15; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x180039cb2  call    ?MSMSecLogProfile@@YAXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAUMSMSEC_NW_DESC@@@Z; MSMSecLogProfile(DOT11_MSMSEC_CONNECTION_PROFILE *,MSMSEC_NW_DESC *)
0x180039cb7  mov     ecx, [rsi+0AA4h]
0x180039cbd  mov     edx, 1
0x180039cc2  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180039cc7  test    eax, eax
0x180039cc9  jnz     short loc_180039D34
0x180039ccb  mov     edi, 139Fh
0x180039cd0  mov     r11, cs:WPP_GLOBAL_Control
0x180039cd7  cmp     r11, r14
0x180039cda  jz      loc_18003A251
0x180039ce0  test    byte ptr [r11+44h], 1
0x180039ce5  jz      loc_18003A251
0x180039ceb  mov     r10d, [rsi+0AA4h]
0x180039cf2  lea     ecx, [rax+1]
0x180039cf5  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x180039cfa  mov     ecx, r10d
0x180039cfd  mov     r8, rax
0x180039d00  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x180039d05  mov     rcx, [r11+38h]
0x180039d09  mov     r9, rax
0x180039d0c  mov     dword ptr [rsp+1C0h+var_190], 1
0x180039d14  mov     edx, 3Ch ; '<'
0x180039d19  mov     [rsp+1C0h+var_198], r8
0x180039d1e  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180039d25  mov     dword ptr [rsp+1C0h+var_1A0], r10d
0x180039d2a  call    WPP_SF_SLSL
0x180039d2f  jmp     loc_18003A251
0x180039d34  lea     rax, [rbp+0C0h+var_130]
0x180039d38  mov     r9, r15; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x180039d3b  mov     [rsp+1C0h+var_190], rax; unsigned int *
0x180039d40  mov     rdx, r13; struct MSMSEC_NW_DESC *
0x180039d43  lea     rax, [rbp+0C0h+var_118]
0x180039d47  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
  ... truncated ...
```
