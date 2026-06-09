# ScheduledToasts::Add(NotificationPlatform *,ushort *,ushort const *,_WPN_SCHEDULED_TOAST *,_GUID *)

- ea: `0x1800200b4`
- end: `0x180020c84`
- name: `?Add@ScheduledToasts@@QEAAJPEAVNotificationPlatform@@PEAGPEBGPEAU_WPN_SCHEDULED_TOAST@@PEAU_GUID@@@Z`
- size: `3024`
- prototype: `__int64 __fastcall(ScheduledToasts *__hidden this, struct NotificationPlatform *, unsigned __int16 *, const unsigned __int16 *, struct _WPN_SCHEDULED_TOAST *, struct _GUID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001fb78`

## callees

- `0x18001f180`
- `0x1800200b4`
- `0x180024640`
- `0x1800264a4`
- `0x18002ee38`
- `0x1800325c8`
- `0x180061800`
- `0x1800622ac`
- `0x18006ae88`
- `0x1800734c0`
- `0x18008a97c`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800ba574`
- `0x1800d7bac`
- `0x180107150`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800209ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800209ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800209fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800209fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002050b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002050b`
- `ntdll!RtlNtStatusToDosError` at `0x18002077a`
- `ntdll!RtlNtStatusToDosError` at `0x180020b69`
- `ntdll!RtlNtStatusToDosError` at `0x18002077a`
- `ntdll!RtlNtStatusToDosError` at `0x180020b69`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180020501`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180020501`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x18002029f`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x18002029f`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtCreateEventForPackageName` at `0x180020b59`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtCreateEventForPackageName` at `0x180020b59`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateActivationProxy` at `0x18002076e`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateActivationProxy` at `0x18002076e`
- `TimeBrokerClient!TbCreateEvent` at `0x180020698`
- `TimeBrokerClient!TbCreateEvent` at `0x180020698`
- `TimeBrokerClient!TbDeleteEvent` at `0x18002028d`
- `TimeBrokerClient!TbDeleteEvent` at `0x18002028d`

## string_xrefs

- `0x18002017c`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800202d5`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180020324`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180020389`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800203da`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180020447`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180020527`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800206af`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800206f5`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x18002079a`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800207f2`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800208e0`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180020940`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x18002099e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180020a2c`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180020a8e`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180020af2`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180020b89`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x180020c1f`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\scheduledtoasts.cpp`
- `0x1800201dc`: `SetScheduledToastUpdate`

## pseudocode

```c
__int64 __fastcall ScheduledToasts::Add(
        ScheduledToasts *this,
        struct NotificationPlatform *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _WPN_SCHEDULED_TOAST *a5,
        struct _GUID *a6)
{
  int v8; // r14d
  signed int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  ScheduledToasts *v13; // rdi
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  void *v18; // rcx
  __int64 v19; // xmm0_8
  int v20; // eax
  DWORD v21; // eax
  signed int LastError; // eax
  unsigned __int64 v23; // rdx
  int v24; // eax
  NTSTATUS v25; // eax
  unsigned int v26; // edx
  signed int v27; // eax
  int UserSid; // eax
  unsigned __int16 *v29; // rax
  char *v30; // rcx
  __int64 v31; // rdx
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  int v40; // eax
  int v41; // eax
  int v42; // eax
  void *v43; // r14
  _QWORD *v44; // rcx
  __int64 v45; // rdx
  HANDLE ProcessHeap; // rax
  int v47; // eax
  const unsigned __int16 *v48; // r8
  unsigned __int64 v49; // r11
  int v50; // eax
  const unsigned __int16 *v51; // r8
  int v52; // eax
  NTSTATUS v53; // eax
  signed int v54; // eax
  int v55; // eax
  int v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+20h] [rbp-E0h]
  ScheduledToasts *v58; // [rsp+40h] [rbp-C0h] BYREF
  int v59; // [rsp+48h] [rbp-B8h] BYREF
  FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  int v61; // [rsp+58h] [rbp-A8h]
  LPVOID lpMem[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v63; // [rsp+70h] [rbp-90h] BYREF
  __m256i v64; // [rsp+80h] [rbp-80h] BYREF
  __int128 v65; // [rsp+A0h] [rbp-60h]
  __int128 v66; // [rsp+B0h] [rbp-50h]
  __int128 v67; // [rsp+C0h] [rbp-40h]
  __int128 v68; // [rsp+D0h] [rbp-30h]
  __int128 v69; // [rsp+E0h] [rbp-20h]
  __int128 v70; // [rsp+F0h] [rbp-10h]
  __int128 v71; // [rsp+100h] [rbp+0h]
  __int128 v72; // [rsp+110h] [rbp+10h]
  __int128 v73; // [rsp+120h] [rbp+20h]
  __int128 v74; // [rsp+130h] [rbp+30h]
  __int128 v75; // [rsp+140h] [rbp+40h]
  __int128 v76; // [rsp+150h] [rbp+50h]
  __int128 v77; // [rsp+160h] [rbp+60h]
  __int64 v78; // [rsp+170h] [rbp+70h]
  __m256i v79; // [rsp+180h] [rbp+80h] BYREF
  __int128 v80; // [rsp+1A0h] [rbp+A0h]
  __int128 v81; // [rsp+1B0h] [rbp+B0h]
  __int128 v82; // [rsp+1C0h] [rbp+C0h]
  __int128 v83; // [rsp+1D0h] [rbp+D0h]
  __int128 v84; // [rsp+1E0h] [rbp+E0h]
  __int128 v85; // [rsp+1F0h] [rbp+F0h]
  __int128 v86; // [rsp+200h] [rbp+100h]
  __int128 v87; // [rsp+210h] [rbp+110h]
  __int128 v88; // [rsp+220h] [rbp+120h]
  __int128 v89; // [rsp+230h] [rbp+130h]
  __int128 v90; // [rsp+240h] [rbp+140h]
  __int128 v91; // [rsp+250h] [rbp+150h]
  __int128 v92; // [rsp+260h] [rbp+160h]
  __int64 v93; // [rsp+270h] [rbp+170h]
  _WNF_STATE_NAME v94; // [rsp+280h] [rbp+180h] BYREF
  struct _GUID v95; // [rsp+290h] [rbp+190h] BYREF
  struct _GUID v96; // [rsp+2A0h] [rbp+1A0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v98; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v99; // [rsp+2D0h] [rbp+1D0h] BYREF
  struct _GUID v100; // [rsp+2D4h] [rbp+1D4h] BYREF
  _WNF_STATE_NAME v101; // [rsp+2E4h] [rbp+1E4h]
  void *v102; // [rsp+2F0h] [rbp+1F0h]
  __int64 v103; // [rsp+2F8h] [rbp+1F8h]
  int v104; // [rsp+300h] [rbp+200h]
  int v105; // [rsp+304h] [rbp+204h]
  int v106; // [rsp+308h] [rbp+208h]
  unsigned __int16 v107[16]; // [rsp+30Ch] [rbp+20Ch] BYREF
  unsigned __int16 v108[130]; // [rsp+32Ch] [rbp+22Ch] BYREF
  char v109; // [rsp+430h] [rbp+330h] BYREF
  char v110[5120]; // [rsp+530h] [rbp+430h] BYREF
  int v111; // [rsp+1930h] [rbp+1830h]
  unsigned __int16 v112[65]; // [rsp+19BCh] [rbp+18BCh] BYREF
  unsigned __int16 v113[65]; // [rsp+1A3Eh] [rbp+193Eh] BYREF
  __int64 v114; // [rsp+1AC0h] [rbp+19C0h]
  int v115; // [rsp+1AC8h] [rbp+19C8h]
  int v116; // [rsp+1ACCh] [rbp+19CCh]
  _BYTE v117[80]; // [rsp+1AD0h] [rbp+19D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B68h] [rbp+1A68h]

  v58 = this;
  v64.m256i_i32[1] = 0;
  memset_0(&v64.m256i_u64[1], 0, 0xF0u);
  FileTime = 0;
  v94 = 0;
  v95 = 0;
  v98 = 0;
  v96 = 0;
  memset_0(&v99, 0, 0x1800u);
  v61 = 0;
  v59 = 0;
  v8 = 0;
  lpMem[0] = 0;
  SystemTime = 0;
  if ( !a4 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)0x80070057LL,
      v56);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 18;
    goto LABEL_5;
  }
  if ( !a5 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)0x80070057LL,
      v56);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 19;
    goto LABEL_5;
  }
  if ( !a6 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)0x80070057LL,
      v56);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 20;
    goto LABEL_5;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SFI663>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SFI663>::GetImpl'::`2'::impl) )
  {
    if ( !*((_QWORD *)a5 + 1) )
    {
      v9 = -2147024809;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)0x80070057LL,
        v56);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_7;
      v11 = 21;
      goto LABEL_5;
    }
    if ( !*(_QWORD *)a5 )
    {
      v9 = -2147024809;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)0x80070057LL,
        v56);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_7;
      v11 = 22;
      goto LABEL_5;
    }
  }
  if ( *((_DWORD *)a5 + 12) )
  {
    FileTime = *(FILETIME *)((char *)a5 + 52);
    if ( (unsigned int)WpnCheckTimeIsExpired(FileTime) )
    {
      v9 = -2147024809;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)0x80070057LL,
        v56);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_7;
      v11 = 23;
LABEL_5:
      v12 = 2147942487LL;
LABEL_6:
      WPP_SF_d(v10[2], v11, WPP_7a7099aae5df3fa656003ab1196d31fe_Traceguids, v12);
LABEL_7:
      v13 = v58;
      goto LABEL_8;
    }
  }
  v18 = (void *)*((_QWORD *)a5 + 5);
  v19 = *((_QWORD *)a5 + 6);
  v104 = *((_DWORD *)a5 + 18);
  v103 = *((_QWORD *)a5 + 8);
  v106 = *((_DWORD *)a5 + 19);
  v111 = *((_DWORD *)a5 + 20);
  v20 = *((_DWORD *)a5 + 14);
  v102 = v18;
  v115 = v20;
  v116 = *((_DWORD *)a5 + 26);
  v21 = *((_DWORD *)a5 + 10);
  FileTime.dwHighDateTime = HIDWORD(v18);
  FileTime.dwLowDateTime = v21;
  v99 = 6;
  v114 = v19;
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)(unsigned int)v9,
      v56);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 24;
LABEL_48:
    v12 = (unsigned int)v9;
    goto LABEL_6;
  }
  v64.m256i_i32[0] = 0;
  v64.m256i_i64[3] = 0x100000000LL;
  *(_SYSTEMTIME *)&v64.m256i_u64[1] = SystemTime;
  LODWORD(v65) = 5;
  DWORD2(v67) = 0;
  DWORD2(v68) = 0;
  BYTE5(v66) = 1;
  if ( *((_DWORD *)a5 + 18) )
  {
    v23 = *((_QWORD *)a5 + 8) / 10000000LL;
    *((_QWORD *)a5 + 8) = v23;
    if ( v23 > 0xFFFFFFFF )
    {
      v9 = -2147024362;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)0x80070216LL,
        v56);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_7;
      v11 = 25;
      v12 = 2147942934LL;
      goto LABEL_6;
    }
    v64.m256i_i32[6] = v23;
  }
  v79 = v64;
  v93 = v78;
  v80 = v65;
  v82 = v67;
  v81 = v66;
  v84 = v69;
  v83 = v68;
  v86 = v71;
  v85 = v70;
  v88 = v73;
  v87 = v72;
  v90 = v75;
  v89 = v74;
  v92 = v77;
  v91 = v76;
  v24 = TbCreateEvent(a3, &v79, &v95);
  v9 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)(unsigned int)v24,
      v56);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 26;
    goto LABEL_48;
  }
  v9 = 0;
  v61 = 1;
  v25 = BiPtAssociateActivationProxy(&v98, &v94, &v95, 0);
  if ( v25 < 0 )
  {
    v27 = RtlNtStatusToDosError(v25);
    v9 = v27;
    if ( v27 > 0 )
      v9 = (unsigned __int16)v27 | 0x80070000;
  }
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)(unsigned int)v9,
      0);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 27;
    goto LABEL_48;
  }
  UserSid = WpnGetUserSid(v117, v26);
  v9 = UserSid;
  if ( UserSid < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)(unsigned int)UserSid,
      0);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 28;
    goto LABEL_48;
  }
  v101 = v94;
  v100 = v95;
  if ( a3 )
  {
    v29 = a3;
    v30 = &v109;
    v31 = 2;
    do
    {
      v32 = *(_OWORD *)v29;
      v33 = *((_OWORD *)v29 + 1);
      v29 += 64;
      *(_OWORD *)v30 = v32;
      v34 = *((_OWORD *)v29 - 6);
      *((_OWORD *)v30 + 1) = v33;
      v35 = *((_OWORD *)v29 - 5);
      *((_OWORD *)v30 + 2) = v34;
      v36 = *((_OWORD *)v29 - 4);
      *((_OWORD *)v30 + 3) = v35;
      v37 = *((_OWORD *)v29 - 3);
      *((_OWORD *)v30 + 4) = v36;
      v38 = *((_OWORD *)v29 - 2);
      *((_OWORD *)v30 + 5) = v37;
      v39 = *((_OWORD *)v29 - 1);
      *((_OWORD *)v30 + 6) = v38;
      *((_OWORD *)v30 + 7) = v39;
      v30 += 128;
      --v31;
    }
    while ( v31 );
    v105 = 1;
  }
  v40 = StringCchCopyW(v107, 0x10u, *((const unsigned __int16 **)a5 + 1));
  v9 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)(unsigned int)v40,
      0);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 29;
    goto LABEL_48;
  }
  v41 = StringCchCopyW(v108, 0x82u, a4);
  v9 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)(unsigned int)v41,
      0);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_7;
    v11 = 30;
    goto LABEL_48;
  }
  v42 = WpnUtf16ToUtf8(*(LPCWCH *)a5, (char **)lpMem);
  v43 = lpMem[0];
  v9 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)(unsigned int)v42,
      0);
    v44 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_87;
    v45 = 31;
    goto LABEL_86;
  }
  v47 = StringCchCopyA(v110, 0x1400u, (const char *)lpMem[0]);
  v9 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
      (const char *)(unsigned int)v47,
      0);
    v44 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_87;
    v45 = 32;
    goto LABEL_86;
  }
  v48 = (const unsigned __int16 *)*((_QWORD *)a5 + 2);
  v49 = 64;
  if ( v48 )
  {
    v50 = StringCchCopyW(v112, 0x40u, v48);
    v9 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v50,
        0);
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_87;
      v45 = 33;
      goto LABEL_86;
    }
  }
  v51 = (const unsigned __int16 *)*((_QWORD *)a5 + 3);
  if ( v51 )
  {
    v52 = StringCchCopyW(v113, v49, v51);
    v9 = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v52,
        0);
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_87;
      v45 = 34;
      goto LABEL_86;
    }
  }
  v53 = BiPtCreateEventForPackageName(&v96, qword_1801278D0, 0, 0);
  if ( v53 < 0 )
  {
    v54 = RtlNtStatusToDosError(v53);
    v9 = v54;
    if ( v54 > 0 )
      v9 = (unsigned __int16)v54 | 0x80070000;
  }
  else
  {
    v9 = 0;
  }
  if ( v9 >= 0 )
  {
    v13 = v58;
    v59 = 1;
    v63 = v96;
    *(struct _GUID *)lpMem = v95;
    v55 = ScheduledToasts::SubscribeAndAddToList(v58, v94, (struct _GUID *)lpMem, &v63, a4, a3);
    v9 = v55;
    if ( v55 >= 0 )
    {
      v9 = 0;
      *a6 = v95;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x176,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
        (const char *)(unsigned int)v55,
        v57);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          WPP_7a7099aae5df3fa656003ab1196d31fe_Traceguids,
          (unsigned int)v9);
    }
    goto LABEL_88;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x169,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\scheduledtoasts.cpp",
    (const char *)(unsigned int)v9,
    (int)&v99);
  v44 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v45 = 35;
LABEL_86:
    WPP_SF_d(v44[2], v45, WPP_7a7099aae5df3fa656003ab1196d31fe_Traceguids, (unsigned int)v9);
  }
LABEL_87:
  v13 = v58;
LABEL_88:
  if ( v43 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v43);
  }
  v8 = v59;
LABEL_8:
  if ( WpnTelemetryAggregator::AddEventCount(
         *(WpnTelemetryAggregator **)(*((_QWORD *)v13 + 5) + 344LL),
         L"SetScheduledToastUpdate",
         a4,
         L"Toast")
    && (unsigned int)dword_18015C038 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x400000000000LL) )
  {
    lpMem[0] = v102;
    v58 = (ScheduledToasts *)&v100;
    *(_QWORD *)&v63.Data1 = a4;
    v59 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
      v14,
      (unsigned int)&dword_180138AE4,
      v15,
      v16,
      (__int64)&v59,
      (__int64)&v63,
      (__int64)&v58,
      (__int64)lpMem);
  }
  if ( v9 < 0 )
  {
    if ( v61 )
    {
      v63 = v95;
      TbDeleteEvent(a3, &v63);
    }
    if ( v8 )
      BiPtDeleteEvent(&v96);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800200b4  push    rbp
0x1800200b6  push    rbx
0x1800200b7  push    rdi
0x1800200b8  push    r12
0x1800200ba  push    r13
0x1800200bc  push    r14
0x1800200be  push    r15
0x1800200c0  lea     rbp, [rsp-1A30h]
0x1800200c8  mov     eax, 1B30h
0x1800200cd  call    _alloca_probe
0x1800200d2  sub     rsp, rax
0x1800200d5  mov     rax, cs:__security_cookie
0x1800200dc  xor     rax, rsp
0x1800200df  mov     [rbp+1A60h+var_40], rax
0x1800200e6  mov     rdi, [rbp+1A60h+arg_20]
0x1800200ed  mov     r12, r8
0x1800200f0  mov     r15, [rbp+1A60h+arg_28]
0x1800200f7  xor     eax, eax
0x1800200f9  mov     [rsp+1B60h+var_1B20], rcx
0x1800200fe  mov     r8d, 0F0h; Size
0x180020104  lea     rcx, [rbp+1A60h+var_1AE0+8]; void *
0x180020108  mov     dword ptr [rbp+1A60h+var_1AE0+4], eax
0x18002010b  xor     edx, edx; Val
0x18002010d  mov     r13, r9
0x180020110  call    memset_0
0x180020115  xorps   xmm0, xmm0
0x180020118  lea     rcx, [rbp+1A60h+var_1890]; void *
0x18002011f  xorps   xmm1, xmm1
0x180020122  xor     ebx, ebx
0x180020124  xor     edx, edx; Val
0x180020126  mov     qword ptr [rsp+1B60h+FileTime.dwLowDateTime], rbx
0x18002012b  mov     r8d, 1800h; Size
0x180020131  mov     qword ptr [rbp+1A60h+var_18E0.Data], rbx
0x180020138  movups  [rbp+1A60h+var_18D0], xmm0
0x18002013f  movups  [rbp+1A60h+var_18A0], xmm0
0x180020146  movups  [rbp+1A60h+var_18C0], xmm1
0x18002014d  call    memset_0
0x180020152  mov     [rsp+1B60h+var_1B08], ebx
0x180020156  xorps   xmm0, xmm0
0x180020159  mov     [rsp+1B60h+var_1B18], ebx
0x18002015d  mov     r14d, ebx
0x180020160  mov     [rsp+1B60h+lpMem], rbx
0x180020165  movups  xmmword ptr [rbp+1A60h+SystemTime.wYear], xmm0
0x18002016c  test    r13, r13
0x18002016f  jnz     loc_1800202C9
0x180020175  mov     rcx, [rbp+1A68h]; this
0x18002017c  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180020183  mov     r9d, 80070057h; char *
0x180020189  mov     edx, 0D7h; void *
0x18002018e  mov     ebx, r9d
0x180020191  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020196  mov     rcx, cs:WPP_GLOBAL_Control
0x18002019d  lea     rax, WPP_GLOBAL_Control
0x1800201a4  cmp     rcx, rax
0x1800201a7  jz      short loc_1800201C9
0x1800201a9  test    byte ptr [rcx+1Ch], 80h
0x1800201ad  jz      short loc_1800201C9
0x1800201af  lea     edx, [r13+12h]
0x1800201b3  mov     r9d, 80070057h
0x1800201b9  mov     rcx, [rcx+10h]
0x1800201bd  lea     r8, WPP_7a7099aae5df3fa656003ab1196d31fe_Traceguids
0x1800201c4  call    WPP_SF_d
0x1800201c9  mov     rdi, [rsp+1B60h+var_1B20]
0x1800201ce  mov     rcx, [rdi+28h]
0x1800201d2  lea     r9, aToast; "Toast"
0x1800201d9  mov     r8, r13; unsigned __int16 *
0x1800201dc  lea     rdx, aSetscheduledto; "SetScheduledToastUpdate"
0x1800201e3  mov     rcx, [rcx+158h]; this
0x1800201ea  call    ?AddEventCount@WpnTelemetryAggregator@@QEAA_NPEBG00@Z; WpnTelemetryAggregator::AddEventCount(ushort const *,ushort const *,ushort const *)
0x1800201ef  test    al, al
0x1800201f1  jz      short loc_18002026D
0x1800201f3  mov     eax, cs:dword_18015C038
0x1800201f9  cmp     eax, 5
0x1800201fc  jbe     short loc_18002026D
0x1800201fe  mov     rdx, 400000000000h
0x180020208  lea     rcx, dword_18015C038
0x18002020f  call    _tlgKeywordOn
0x180020214  test    al, al
0x180020216  jz      short loc_18002026D
0x180020218  mov     rax, [rbp+1A60h+var_1870]
0x18002021f  lea     rdx, dword_180138AE4
0x180020226  mov     [rsp+1B60h+lpMem], rax
0x18002022b  lea     rax, [rbp+1A60h+var_188C]
0x180020232  mov     [rsp+1B60h+var_1B20], rax
0x180020237  lea     rax, [rsp+1B60h+lpMem]
0x18002023c  mov     [rsp+1B60h+var_1B28], rax
0x180020241  lea     rax, [rsp+1B60h+var_1B20]
0x180020246  mov     [rsp+1B60h+var_1B30], rax
0x18002024b  lea     rax, [rsp+1B60h+var_1AF0]
0x180020250  mov     [rsp+1B60h+var_1B38], rax
0x180020255  lea     rax, [rsp+1B60h+var_1B18]
0x18002025a  mov     [rsp+1B60h+var_1B40], rax
0x18002025f  mov     qword ptr [rsp+1B60h+var_1AF0.Data1], r13
0x180020264  mov     [rsp+1B60h+var_1B18], ebx
0x180020268  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x18002026d  test    ebx, ebx
0x18002026f  jns     short loc_1800202A5
0x180020271  cmp     [rsp+1B60h+var_1B08], 0
0x180020276  jz      short loc_180020293
0x180020278  movaps  xmm0, [rbp+1A60h+var_18D0]
0x18002027f  lea     rdx, [rsp+1B60h+var_1AF0]
0x180020284  mov     rcx, r12
0x180020287  movdqa  xmmword ptr [rsp+1B60h+var_1AF0.Data1], xmm0
0x18002028d  call    cs:__imp_TbDeleteEvent
0x180020293  test    r14d, r14d
0x180020296  jz      short loc_1800202A5
0x180020298  lea     rcx, [rbp+1A60h+var_18C0]
0x18002029f  call    cs:__imp_BiPtDeleteEvent
0x1800202a5  mov     eax, ebx
0x1800202a7  mov     rcx, [rbp+1A60h+var_40]
0x1800202ae  xor     rcx, rsp; StackCookie
0x1800202b1  call    __security_check_cookie
0x1800202b6  add     rsp, 1B30h
0x1800202bd  pop     r15
0x1800202bf  pop     r14
0x1800202c1  pop     r13
0x1800202c3  pop     r12
0x1800202c5  pop     rdi
0x1800202c6  pop     rbx
0x1800202c7  pop     rbp
0x1800202c8  retn
0x1800202c9  test    rdi, rdi
0x1800202cc  jnz     short loc_180020318
0x1800202ce  mov     rcx, [rbp+1A68h]; this
0x1800202d5  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800202dc  mov     r9d, 80070057h; char *
0x1800202e2  mov     edx, 0D8h; void *
0x1800202e7  mov     ebx, r9d
0x1800202ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800202ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202f6  lea     rax, WPP_GLOBAL_Control
0x1800202fd  cmp     rcx, rax
0x180020300  jz      loc_1800201C9
0x180020306  test    byte ptr [rcx+1Ch], 80h
0x18002030a  jz      loc_1800201C9
0x180020310  lea     edx, [rdi+13h]
0x180020313  jmp     loc_1800201B3
0x180020318  test    r15, r15
0x18002031b  jnz     short loc_180020368
0x18002031d  mov     rcx, [rbp+1A68h]; this
0x180020324  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002032b  mov     r9d, 80070057h; char *
0x180020331  mov     edx, 0D9h; void *
0x180020336  mov     ebx, r9d
0x180020339  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002033e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020345  lea     rax, WPP_GLOBAL_Control
0x18002034c  cmp     rcx, rax
0x18002034f  jz      loc_1800201C9
0x180020355  test    byte ptr [rcx+1Ch], 80h
0x180020359  jz      loc_1800201C9
0x18002035f  lea     edx, [r15+14h]
0x180020363  jmp     loc_1800201B3
0x180020368  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SFI663@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SFI663@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SFI663> `wil::Feature<__WilFeatureTraits_Feature_SFI663>::GetImpl(void)'::`2'::impl
0x18002036f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SFI663@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SFI663>::__private_IsEnabled(void)
0x180020374  test    al, al
0x180020376  jz      loc_18002041F
0x18002037c  cmp     [rdi+8], rbx
0x180020380  jnz     short loc_1800203CE
0x180020382  mov     rcx, [rbp+1A68h]; this
0x180020389  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180020390  mov     r9d, 80070057h; char *
0x180020396  mov     edx, 0DDh; void *
0x18002039b  mov     ebx, r9d
0x18002039e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800203a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203aa  lea     rax, WPP_GLOBAL_Control
0x1800203b1  cmp     rcx, rax
0x1800203b4  jz      loc_1800201C9
0x1800203ba  test    byte ptr [rcx+1Ch], 80h
0x1800203be  jz      loc_1800201C9
0x1800203c4  mov     edx, 15h
0x1800203c9  jmp     loc_1800201B3
0x1800203ce  cmp     [rdi], rbx
0x1800203d1  jnz     short loc_18002041F
0x1800203d3  mov     rcx, [rbp+1A68h]; this
0x1800203da  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800203e1  mov     r9d, 80070057h; char *
0x1800203e7  mov     edx, 0DEh; void *
0x1800203ec  mov     ebx, r9d
0x1800203ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800203f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203fb  lea     rax, WPP_GLOBAL_Control
0x180020402  cmp     rcx, rax
0x180020405  jz      loc_1800201C9
0x18002040b  test    byte ptr [rcx+1Ch], 80h
0x18002040f  jz      loc_1800201C9
0x180020415  mov     edx, 16h
0x18002041a  jmp     loc_1800201B3
0x18002041f  cmp     [rdi+30h], ebx
0x180020422  jz      short loc_18002048C
0x180020424  mov     eax, [rdi+34h]
0x180020427  mov     [rsp+1B60h+FileTime.dwLowDateTime], eax
0x18002042b  mov     eax, [rdi+38h]
0x18002042e  mov     [rsp+1B60h+FileTime.dwHighDateTime], eax
0x180020432  mov     rcx, qword ptr [rsp+1B60h+FileTime.dwLowDateTime]; struct _FILETIME
0x180020437  call    ?WpnCheckTimeIsExpired@@YAHU_FILETIME@@@Z; WpnCheckTimeIsExpired(_FILETIME)
0x18002043c  test    eax, eax
0x18002043e  jz      short loc_18002048C
0x180020440  mov     rcx, [rbp+1A68h]; this
0x180020447  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002044e  mov     r9d, 80070057h; char *
0x180020454  mov     edx, 0E7h; void *
0x180020459  mov     ebx, r9d
0x18002045c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020461  mov     rcx, cs:WPP_GLOBAL_Control
0x180020468  lea     rax, WPP_GLOBAL_Control
0x18002046f  cmp     rcx, rax
0x180020472  jz      loc_1800201C9
0x180020478  test    byte ptr [rcx+1Ch], 80h
0x18002047c  jz      loc_1800201C9
0x180020482  mov     edx, 17h
0x180020487  jmp     loc_1800201B3
0x18002048c  mov     eax, [rdi+48h]
0x18002048f  lea     rdx, [rbp+1A60h+SystemTime]; lpSystemTime
0x180020496  mov     rcx, [rdi+28h]
0x18002049a  movsd   xmm0, qword ptr [rdi+30h]
0x18002049f  mov     [rbp+1A60h+var_1860], eax
0x1800204a5  mov     rax, [rdi+40h]
0x1800204a9  mov     [rbp+1A60h+var_1868], rax
0x1800204b0  mov     eax, [rdi+4Ch]
0x1800204b3  mov     [rbp+1A60h+var_1858], eax
0x1800204b9  mov     eax, [rdi+50h]
0x1800204bc  mov     [rbp+1A60h+var_230], eax
0x1800204c2  mov     eax, [rdi+38h]
0x1800204c5  mov     [rbp+1A60h+var_1870], rcx
0x1800204cc  mov     [rbp+1A60h+var_98], eax
0x1800204d2  mov     eax, [rdi+68h]
0x1800204d5  sar     rcx, 20h
0x1800204d9  mov     [rbp+1A60h+var_94], eax
0x1800204df  mov     eax, [rdi+28h]
0x1800204e2  mov     [rsp+1B60h+FileTime.dwHighDateTime], ecx
0x1800204e6  lea     rcx, [rsp+1B60h+FileTime]; lpFileTime
0x1800204eb  mov     [rsp+1B60h+FileTime.dwLowDateTime], eax
0x1800204ef  mov     [rbp+1A60h+var_1890], 6
0x1800204f9  movsd   [rbp+1A60h+var_A0], xmm0
0x180020501  call    cs:__imp_FileTimeToSystemTime
0x180020507  test    eax, eax
0x180020509  jnz     short loc_180020573
0x18002050b  call    cs:__imp_GetLastError
0x180020511  mov     ebx, eax
0x180020513  test    eax, eax
0x180020515  jle     short loc_180020520
0x180020517  movzx   ebx, ax
0x18002051a  or      ebx, 80070000h
0x180020520  mov     rcx, [rbp+1A68h]; this
0x180020527  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002052e  test    ebx, ebx
0x180020530  mov     eax, 80004005h
0x180020535  mov     edx, 0FBh; void *
0x18002053a  cmovns  ebx, eax
0x18002053d  mov     r9d, ebx; char *
0x180020540  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020545  mov     rcx, cs:WPP_GLOBAL_Control
0x18002054c  lea     rax, WPP_GLOBAL_Control
0x180020553  cmp     rcx, rax
0x180020556  jz      loc_1800201C9
0x18002055c  test    byte ptr [rcx+1Ch], 80h
0x180020560  jz      loc_1800201C9
0x180020566  mov     edx, 18h
0x18002056b  mov     r9d, ebx
0x18002056e  jmp     loc_1800201B9
0x180020573  movups  xmm0, xmmword ptr [rbp+1A60h+SystemTime.wYear]
0x18002057a  mov     dword ptr [rbp+1A60h+var_1AE0], ebx
0x18002057d  mov     [rbp+1A60h+var_1AC8], ebx
0x180020580  movdqu  [rbp+1A60h+var_1AE0+8], xmm0
0x180020585  mov     [rbp+1A60h+var_1AC4], 1
0x18002058c  mov     dword ptr [rbp+1A60h+var_1AC0], 5
0x180020593  mov     [rbp+1A60h+var_1A98], ebx
0x180020596  mov     [rbp+1A60h+var_1A88], ebx
0x180020599  mov     [rbp+1A60h+var_1AAB], 1
0x18002059d  cmp     [rdi+48h], ebx
0x1800205a0  jz      short loc_1800205D7
0x1800205a2  mov     rax, 0D6BF94D5E57A42BDh
0x1800205ac  imul    qword ptr [rdi+40h]
0x1800205b0  add     rdx, [rdi+40h]
0x1800205b4  sar     rdx, 17h
0x1800205b8  mov     rax, rdx
0x1800205bb  shr     rax, 3Fh
0x1800205bf  add     rdx, rax
0x1800205c2  mov     eax, 0FFFFFFFFh
0x1800205c7  mov     [rdi+40h], rdx
0x1800205cb  cmp     rdx, rax
0x1800205ce  ja      loc_1800206EE
0x1800205d4  mov     [rbp+1A60h+var_1AC8], edx
0x1800205d7  movaps  xmm0, [rbp+1A60h+var_1AE0]
0x1800205db  lea     r8, [rbp+1A60h+var_18D0]
0x1800205e2  movaps  xmm1, xmmword ptr [rbp-70h]
0x1800205e6  lea     rdx, [rbp+1A60h+var_19E0]
0x1800205ed  mov     rax, [rbp+1A60h+var_19F0]
0x1800205f1  mov     rcx, r12
0x1800205f4  movups  [rbp+1A60h+var_19E0], xmm0
0x1800205fb  mov     [rbp+1A60h+var_18F0], rax
0x180020602  movaps  xmm0, [rbp+1A60h+var_1AC0]
0x180020606  movups  [rbp+1A60h+var_19C0], xmm0
0x18002060d  movaps  xmm0, xmmword ptr [rbp-40h]
0x180020611  movups  [rbp+1A60h+var_19D0], xmm1
0x180020618  movaps  xmm1, xmmword ptr [rbp-50h]
0x18002061c  movups  [rbp+1A60h+var_19A0], xmm0
0x180020623  movaps  xmm0, [rbp+1A60h+var_1A80]
  ... truncated ...
```
