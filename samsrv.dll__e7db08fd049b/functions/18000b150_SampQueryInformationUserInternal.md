# SampQueryInformationUserInternal

- ea: `0x18000b150`
- end: `0x18000e174`
- name: `SampQueryInformationUserInternal`
- size: `12324`
- prototype: `__int64 __usercall@<rax>(struct _SAMP_OBJECT *@<rcx>, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `47`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001760`
- `0x18001ff20`
- `0x180021d20`

## callees

- `0x1800028e0`
- `0x180008590`
- `0x1800096c0`
- `0x18000ae10`
- `0x18000b150`
- `0x18000e180`
- `0x18000e8c0`
- `0x18000ed50`
- `0x180012a28`
- `0x180013e00`
- `0x180016240`
- `0x180016a80`
- `0x180016d50`
- `0x180018620`
- `0x1800198a0`
- `0x18001b4e0`
- `0x18001c1d0`
- `0x18001f160`
- `0x1800202d0`
- `0x180020c74`
- `0x180021ad0`
- `0x180022188`
- `0x1800225f0`
- `0x180022b30`
- `0x180024dc0`
- `0x180024ee8`
- `0x180025fe4`
- `0x1800270b4`
- `0x180027250`
- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x180037284`
- `0x1800372ac`
- `0x18003c010`
- `0x18003c920`
- `0x180059a74`
- `0x1800904e8`
- `0x180090664`
- `0x18009d3cc`
- `0x18009d488`
- `0x18009d554`
- `0x18009fd08`
- `0x1800a0f44`
- `0x1800a82c8`
- `0x1800bb788`
- `0x1800bc010`

## import_xrefs

- `ntdll!RtlAreAllAccessesGranted` at `0x18000b707`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000b720`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000b73c`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000b75b`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000b707`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000b720`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000b73c`
- `ntdll!RtlAreAllAccessesGranted` at `0x18000b75b`
- `ntdll!NtQuerySystemTime` at `0x18000d346`
- `ntdll!NtQuerySystemTime` at `0x18000d346`
- `ntdll!RtlEnterCriticalSection` at `0x18000b42e`
- `ntdll!RtlEnterCriticalSection` at `0x18000b42e`
- `ntdll!RtlInitUnicodeString` at `0x18000d617`
- `ntdll!RtlInitUnicodeString` at `0x18000d626`
- `ntdll!RtlInitUnicodeString` at `0x18000d617`
- `ntdll!RtlInitUnicodeString` at `0x18000d626`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b307`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b34a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c8ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c960`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cf6a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d4f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d63d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d694`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b307`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b34a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c8ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c960`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cf6a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d4f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d63d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d694`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b852`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b9aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b852`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b9aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000b418`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000b43b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000b418`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000b43b`
- `ext-ms-win-laps-l1-1-0!LAPSExtIsLocalAccountManaged` at `0x18000b5ce`
- `ext-ms-win-laps-l1-1-0!LAPSExtIsLocalAccountManaged` at `0x18000b5ce`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtDowngradeSecurityDescriptor` at `0x18000d79f`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtDowngradeSecurityDescriptor` at `0x18000d79f`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x18000b4a4`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x18000b4a4`

## pseudocode

```c
__int64 __fastcall SampQueryInformationUserInternal(
        struct _SAMP_OBJECT *a1,
        unsigned int a2,
        char a3,
        int a4,
        int a5,
        union _LARGE_INTEGER **a6)
{
  union _LARGE_INTEGER **v6; // r12
  struct _SAMP_OBJECT *v7; // r13
  unsigned int v9; // r14d
  int updated; // ebx
  ACCESS_MASK v11; // esi
  __int64 v12; // rbx
  union _LARGE_INTEGER *v13; // rax
  __int64 v14; // rbx
  union _LARGE_INTEGER *v15; // rax
  unsigned __int8 v16; // di
  DWORD TickCount; // ebx
  DWORD v18; // eax
  unsigned int v19; // ecx
  DWORD v20; // eax
  unsigned int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  PUNICODE_STRING v24; // rcx
  __int64 v25; // rsi
  int v26; // eax
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  unsigned int IsLocalAccountManaged; // eax
  int v30; // r15d
  unsigned int v31; // r14d
  __int64 v32; // r8
  struct _USER_STRING_LIST *LogonHours; // rcx
  bool v34; // di
  int v35; // ebx
  int v36; // edi
  int v37; // ebx
  PUNICODE_STRING v38; // rsi
  unsigned int v39; // edi
  bool v40; // zf
  _OWORD *v41; // rax
  int UserPasswords; // eax
  __int64 v43; // rcx
  struct _LM_OWF_PASSWORD *v44; // rax
  struct _LM_OWF_PASSWORD *v45; // rax
  __int64 j; // rdi
  struct _LOGON_HOURS *v47; // rcx
  void *v48; // rcx
  void *v49; // rcx
  __int64 v50; // rax
  void *v51; // rcx
  __int64 v52; // rax
  void *v53; // rcx
  __int64 v54; // rax
  void *v55; // rcx
  __int64 v56; // rax
  void *v57; // rcx
  __int64 v58; // rax
  void *v59; // rcx
  __int64 v60; // rax
  struct _LOGON_HOURS *v61; // rdx
  void *v62; // rcx
  __int64 v63; // rax
  void *v64; // rcx
  void *QuadPart; // rcx
  void *v66; // rcx
  __int64 v67; // rax
  void *v68; // rcx
  __int64 v69; // rax
  void *v70; // rcx
  int UserLogonHours; // eax
  void *v72; // rcx
  union _LARGE_INTEGER *v73; // rdx
  void *v74; // rcx
  union _LARGE_INTEGER *v75; // rbx
  void *v76; // rcx
  void *v77; // rcx
  __int64 v78; // rax
  void *v79; // rcx
  __int64 v80; // rax
  void *v81; // rcx
  __int64 v82; // rax
  void *v83; // rcx
  __int64 v84; // rax
  void *v85; // rcx
  __int64 v86; // rax
  struct _LOGON_HOURS *v87; // rdx
  void *v88; // rcx
  __int64 v89; // rax
  void *v90; // rcx
  struct _LOGON_HOURS *v91; // rdi
  int v92; // esi
  __int64 v93; // rax
  __int64 v94; // rax
  union _LARGE_INTEGER v95; // rdx
  union _LARGE_INTEGER v96; // r8
  int v97; // r9d
  __int64 v98; // rax
  __int64 v99; // rax
  void *v100; // rcx
  __int64 v101; // rax
  void *v102; // rcx
  __int64 v103; // rax
  PUCHAR v104; // rcx
  __int64 v105; // rax
  __int64 v106; // rax
  _BYTE *v107; // rax
  int v108; // eax
  unsigned int v109; // eax
  HLOCAL v110; // rax
  void *v111; // rcx
  __int64 v112; // rax
  unsigned int v113; // eax
  HLOCAL v114; // rax
  void *v115; // rcx
  __int64 v116; // rax
  __int64 v117; // rax
  unsigned int v118; // esi
  struct _SAMP_MAPPING_INFORMATION *v119; // rdx
  int v120; // eax
  struct _LOGON_HOURS *v121; // rdi
  struct _LOGON_HOURS *v122; // rsi
  void *v123; // rcx
  __int64 v124; // rax
  int v125; // eax
  PUNICODE_STRING v126; // rcx
  __int64 v127; // rdx
  __int64 v128; // r9
  __int64 v129; // rcx
  __int64 v130; // rax
  unsigned int v131; // eax
  size_t v132; // rbx
  UCHAR *v133; // rax
  UCHAR *v134; // r9
  __int64 v135; // rcx
  __int64 v136; // rdx
  unsigned int v137; // eax
  __int64 v138; // rax
  void *v139; // rcx
  __int64 v140; // rax
  int v141; // eax
  __int64 v142; // rcx
  __int64 v143; // rax
  unsigned int v144; // eax
  size_t v145; // rbx
  UCHAR *v146; // rax
  UCHAR *v147; // r9
  __int64 v148; // rcx
  __int64 v149; // rdx
  unsigned int v150; // eax
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // rax
  unsigned __int16 BadPasswordCount; // ax
  unsigned int v161; // esi
  char v162; // cl
  char v163; // dl
  __int64 v164; // rax
  union _LARGE_INTEGER v165; // rax
  unsigned int v166; // eax
  void *v167; // rcx
  __int64 v168; // rax
  int v169; // eax
  __int64 v170; // rcx
  __int64 v171; // rax
  unsigned int v172; // eax
  size_t v173; // rbx
  UCHAR *v174; // rax
  UCHAR *v175; // r9
  __int64 v176; // rcx
  __int64 v177; // rdx
  unsigned int v178; // eax
  PUCHAR v179; // rcx
  __int64 v180; // rax
  struct _LM_OWF_PASSWORD *v181; // rax
  struct _LM_OWF_PASSWORD *v182; // rcx
  __int64 v183; // rax
  struct _LM_OWF_PASSWORD *v184; // rax
  struct _LM_OWF_PASSWORD *v185; // rcx
  __int64 v186; // rax
  PUCHAR v187; // rcx
  __int64 v188; // rax
  int v189; // eax
  PUCHAR v190; // rcx
  __int64 v191; // rax
  PUCHAR v192; // rcx
  __int64 v193; // rax
  _BYTE *v194; // rax
  __int64 v195; // rax
  __int64 v196; // rcx
  __int64 v197; // rax
  __int64 v198; // rcx
  __int64 v199; // rax
  __int64 v200; // rcx
  __int64 v201; // rax
  __int64 v202; // rcx
  __int64 v203; // rax
  __int64 v204; // rcx
  __int64 v205; // rax
  __int64 v206; // rcx
  __int64 v207; // rax
  __int64 v208; // rcx
  __int64 v209; // rax
  __int64 v210; // rcx
  __int64 v211; // rax
  __int64 v212; // rcx
  __int64 v213; // rax
  __int64 v214; // rcx
  __int64 v215; // r14
  __int64 v216; // rax
  __int64 (__fastcall *v217)(struct _SAMP_OBJECT *, unsigned int *, _QWORD); // r13
  struct _SAMP_OBJECT *v218; // r15
  int v219; // eax
  __int64 v220; // r12
  __int64 v221; // rbx
  unsigned int *v222; // r8
  int v223; // r15d
  int v224; // eax
  __int64 i; // r14
  __int64 v226; // r13
  char v227; // r12
  __int64 v228; // rdx
  __int64 v229; // r8
  __int64 v230; // rax
  int *v231; // rcx
  _BYTE *v232; // r15
  unsigned int v233; // eax
  union _LARGE_INTEGER *v234; // rdx
  void *v235; // rcx
  void *v236; // rcx
  __int64 v237; // rax
  void *v238; // rcx
  __int64 v239; // rax
  void *v240; // r8
  unsigned int HighPart; // [rsp+40h] [rbp-C8h]
  unsigned int v243; // [rsp+58h] [rbp-B0h] BYREF
  int v244; // [rsp+5Ch] [rbp-ACh] BYREF
  _BYTE v245[4]; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v246; // [rsp+64h] [rbp-A4h] BYREF
  char v247; // [rsp+68h] [rbp-A0h]
  char v248; // [rsp+69h] [rbp-9Fh]
  char v249; // [rsp+6Ah] [rbp-9Eh]
  unsigned int v250[2]; // [rsp+70h] [rbp-98h] BYREF
  struct _SAMP_OBJECT *v251; // [rsp+78h] [rbp-90h]
  _LARGE_INTEGER SystemTime; // [rsp+80h] [rbp-88h] BYREF
  int v253; // [rsp+88h] [rbp-80h] BYREF
  int *v254; // [rsp+90h] [rbp-78h]
  __int128 v255; // [rsp+98h] [rbp-70h] BYREF
  union _LARGE_INTEGER v256[2]; // [rsp+A8h] [rbp-60h]
  __int128 v257; // [rsp+B8h] [rbp-50h]
  unsigned int v258[4]; // [rsp+C8h] [rbp-40h]
  __int128 v259; // [rsp+D8h] [rbp-30h]
  __int128 v260; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v261; // [rsp+F8h] [rbp-10h]
  struct _LM_OWF_PASSWORD v262; // [rsp+108h] [rbp+0h] BYREF
  struct _LM_OWF_PASSWORD v263; // [rsp+118h] [rbp+10h] BYREF
  struct _DOMAIN_PASSWORD_INFORMATION v264[2]; // [rsp+128h] [rbp+20h] BYREF
  _DWORD v265[44]; // [rsp+158h] [rbp+50h] BYREF
  HLOCAL hMem[64]; // [rsp+208h] [rbp+100h] BYREF
  _DWORD Src[32]; // [rsp+408h] [rbp+300h] BYREF
  unsigned int v268[24]; // [rsp+488h] [rbp+380h] BYREF

  v6 = a6;
  v7 = a1;
  v249 = a3;
  v246 = a2;
  v251 = a1;
  LODWORD(v254) = a4;
  SystemTime.QuadPart = (LONGLONG)a6;
  v253 = 0;
  v255 = 0;
  *(_OWORD *)&v256[0].LowPart = 0;
  v257 = 0;
  v244 = 0;
  *(_OWORD *)v258 = 0;
  v259 = 0;
  v248 = 0;
  v262 = 0;
  v245[0] = 0;
  v263 = 0;
  memset_0(hMem, 0, sizeof(hMem));
  v9 = 0;
  v243 = 0;
  v250[0] = 0;
  memset(v264, 0, sizeof(v264));
  SampTraceEvent(1);
  if ( !a6 || *a6 )
  {
    updated = -1073741811;
    goto LABEL_683;
  }
  if ( a2 != 27 )
  {
    if ( a2 == 5 )
    {
LABEL_16:
      v11 = 27;
    }
    else
    {
      switch ( a2 )
      {
        case 1u:
        case 6u:
        case 7u:
        case 8u:
        case 9u:
        case 0xDu:
          v11 = 1;
          goto LABEL_18;
        case 2u:
          v11 = 3;
          goto LABEL_18;
        case 3u:
          goto LABEL_16;
        case 4u:
        case 0xAu:
        case 0xBu:
        case 0xCu:
        case 0xEu:
          v11 = 8;
          goto LABEL_18;
        case 0x10u:
        case 0x11u:
        case 0x14u:
        case 0x21u:
        case 0x22u:
          v11 = 16;
          goto LABEL_18;
        case 0x12u:
        case 0x13u:
          goto LABEL_7;
        case 0x15u:
        case 0x16u:
          goto LABEL_17;
        case 0x1Cu:
          updated = SampCheckAccessToExtendedInformation(v7, 0, a5);
          if ( updated < 0 )
            goto LABEL_683;
LABEL_7:
          v11 = 0;
          break;
        case 0x1Du:
          updated = SampCheckAccessToLogonUIInformation(v7);
          if ( updated < 0 )
            goto LABEL_683;
          v11 = 0;
          break;
        case 0x1Eu:
          v11 = 128;
          goto LABEL_18;
        default:
          updated = -1073741821;
          goto LABEL_683;
      }
    }
    goto LABEL_18;
  }
LABEL_17:
  v11 = 0;
  if ( a2 != 27 )
  {
LABEL_18:
    v12 = 848;
    v13 = (union _LARGE_INTEGER *)LocalAlloc(0x40u, 0x350u);
    *a6 = v13;
    if ( v13 )
    {
      v9 = 1;
      hMem[0] = v13;
      v243 = 1;
      v250[0] = 1;
      do
      {
        LOBYTE(v13->LowPart) = 0;
        v13 = (union _LARGE_INTEGER *)((char *)v13 + 1);
        --v12;
      }
      while ( v12 );
    }
    goto LABEL_25;
  }
  v14 = 768;
  v15 = (union _LARGE_INTEGER *)LocalAlloc(0x40u, 0x300u);
  *a6 = v15;
  if ( v15 )
  {
    v9 = 1;
    hMem[0] = v15;
    v243 = 1;
    v250[0] = 1;
    do
    {
      LOBYTE(v15->LowPart) = 0;
      v15 = (union _LARGE_INTEGER *)((char *)v15 + 1);
      --v14;
    }
    while ( v14 );
  }
LABEL_25:
  if ( !*a6 )
  {
    updated = -1073741670;
    goto LABEL_683;
  }
  v16 = 0;
  v247 = 0;
  if ( !v249 )
  {
    if ( !v7 )
      goto LABEL_33;
    v247 = 0;
    if ( (int)SampValidateContext(v7) < 0 )
      goto LABEL_46;
    if ( (*((_BYTE *)v7 + 192) & 2) != 0 && (*((_BYTE *)v7 + 28) & 1) != 0 )
    {
      SampIncrementActiveThreads();
    }
    else
    {
LABEL_33:
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
      if ( !SampUseDsData || !(unsigned int)SampExtIsWriteLockHeldByDs() )
      {
        TickCount = GetTickCount();
        _InterlockedIncrement((volatile signed __int32 *)&SamLockQueueLength);
        RtlEnterCriticalSection(&SampLock);
        _InterlockedDecrement((volatile signed __int32 *)&SamLockQueueLength);
        v18 = GetTickCount();
        v19 = SamLockTotalAquisitions + 1;
        SamLockCurrentHoldStartTime = v18;
        ++SamLockTotalAquisitions;
        v20 = v18 - TickCount;
        if ( v20 && v19 )
          SamCumulativeWaitTime += v20;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
        if ( SampUseDsData && (int)SampShouldCallNtdsaApiSet() >= 0 )
          NtdsaExtSetGlobalTransactionType(0);
      }
      v16 = 1;
      v247 = 1;
    }
  }
LABEL_46:
  v21 = SampLookupContextEx((__int64)v7, v11, 0, 4, &v253);
  updated = v21;
  v24 = WPP_GLOBAL_Control;
  v25 = 16;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v21, v21);
    v24 = WPP_GLOBAL_Control;
  }
  if ( updated == -1073741790 )
  {
    if ( a2 != 20 || (*((_BYTE *)v7 + 192) & 2) == 0 || !*((_BYTE *)v7 + 327) )
      goto LABEL_120;
    v26 = SampLookupContext(v7, 0, 4, &v253);
    v24 = WPP_GLOBAL_Control;
    updated = v26;
  }
  if ( updated >= 0 )
  {
    if ( (*((_BYTE *)v7 + 192) & 2) == 0 )
    {
      if ( gfLapsExtInitialized )
      {
        v28 = *((_DWORD *)v7 + 62);
        if ( (*(_BYTE *)(&v24[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v24[4].Length) >= 4u )
          WPP_SF_Dd(v24[3].Buffer, 55, WPP_98e4cdad5db13c057b28971bf7933a81_Traceguids, v28, *((_DWORD *)v7 + 62));
        IsLocalAccountManaged = LAPSExtIsLocalAccountManaged(v28);
        v27 = IsLocalAccountManaged;
        v24 = WPP_GLOBAL_Control;
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[3].Buffer,
            56,
            WPP_98e4cdad5db13c057b28971bf7933a81_Traceguids,
            IsLocalAccountManaged);
          v24 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        if ( (*(_BYTE *)(&v24[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v24[4].Length) >= 4u )
        {
          WPP_SF_(v24[3].Buffer, 54, WPP_98e4cdad5db13c057b28971bf7933a81_Traceguids);
          v24 = WPP_GLOBAL_Control;
        }
        v27 = 0;
      }
      if ( (*(_DWORD *)(&v24[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_d(v24[3].Buffer, 57, WPP_98e4cdad5db13c057b28971bf7933a81_Traceguids, v27);
      *((_DWORD *)v7 + 212) = v27;
    }
    v30 = 0;
    v31 = v246 - 1;
    switch ( v246 )
    {
      case 1u:
      case 2u:
      case 3u:
      case 5u:
      case 9u:
      case 0x10u:
      case 0x11u:
      case 0x13u:
      case 0x1Du:
        goto LABEL_76;
      case 0x15u:
        if ( (*((_BYTE *)v7 + 20) & 0x20) != 0 )
          goto LABEL_74;
        v35 = RtlAreAllAccessesGranted(*((_DWORD *)v7 + 37), 1u) != 0 ? 0x3F : 0;
        v36 = v35 | 0x3FFC0;
        if ( !RtlAreAllAccessesGranted(*((_DWORD *)v7 + 37), 8u) )
          v36 = v35;
        v37 = v36 | 0x3C0000;
        if ( !RtlAreAllAccessesGranted(*((_DWORD *)v7 + 37), 0x10u) )
          v37 = v36;
        v30 = v37 | 0xC00000;
        if ( !RtlAreAllAccessesGranted(*((_DWORD *)v7 + 37), 2u) )
          v30 = v37;
        if ( v30 )
          goto LABEL_76;
        v9 = v243;
        updated = -1073741790;
        goto LABEL_119;
      case 0x16u:
      case 0x1Bu:
        if ( (*((_BYTE *)v7 + 20) & 0x20) == 0 )
        {
          updated = -1073741821;
          goto LABEL_72;
        }
LABEL_74:
        v30 = 0x1FFFFFFF;
        if ( (_DWORD)v254 )
          v30 = (int)v254;
LABEL_76:
        updated = SampRetrieveUserV1aFixed(v7, &v255, v22, v23);
        if ( updated < 0 )
          goto LABEL_72;
LABEL_77:
        updated = SampUpdateAccountDisabledFlag(v7);
        if ( updated < 0 )
        {
LABEL_72:
          v9 = v243;
          goto LABEL_119;
        }
        LogonHours = (struct _USER_STRING_LIST *)v246;
        switch ( v246 )
        {
          case 0x10u:
            goto LABEL_97;
          case 3u:
          case 5u:
            goto LABEL_96;
          case 0x15u:
          case 0x16u:
            goto LABEL_94;
        }
        if ( v246 != 27 )
        {
          LogonHours = (struct _USER_STRING_LIST *)v246;
          v34 = 0;
          goto LABEL_98;
        }
        if ( (a5 & 0x10) != 0 )
        {
LABEL_96:
          LogonHours = (struct _USER_STRING_LIST *)v246;
        }
        else
        {
LABEL_94:
          LogonHours = (struct _USER_STRING_LIST *)v246;
          if ( v30 )
          {
            v34 = (v30 & 0xC134000) != 0;
            goto LABEL_98;
          }
        }
LABEL_97:
        v34 = 1;
LABEL_98:
        v38 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 25, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v34);
          LogonHours = (struct _USER_STRING_LIST *)v246;
          v38 = WPP_GLOBAL_Control;
        }
        if ( v34 )
        {
          v39 = 0;
          LOBYTE(v32) = 1;
          updated = SampGetReverseMembershipTransitive(v7, 1, v32, 0, 0, 0);
          if ( updated < 0
            || (v40 = (*((_BYTE *)v7 + 192) & 2) == 0,
                v41 = (_OWORD *)*((_QWORD *)v7 + 90),
                *(_OWORD *)&v264[0].MinPasswordLength = *v41,
                *(_OWORD *)&v264[0].MinPasswordAge.LowPart = v41[1],
                *(_OWORD *)&v264[1].MaxPasswordAge.LowPart = v41[2],
                v40)
            && (updated = EasMergeUserPasswordSettings(v7, v264), updated < 0) )
          {
            LocalFree(*((HLOCAL *)v7 + 90));
            *((_QWORD *)v7 + 90) = 0;
            memset(v264, 0, sizeof(v264));
          }
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_Dd(
              WPP_GLOBAL_Control[3].Buffer,
              13,
              WPP_88ec5fb48460398ff276a1700e0df4bf_Traceguids,
              (unsigned int)updated,
              updated);
          if ( updated < 0 )
            goto LABEL_117;
          SampUpdateComputedUserAccountControlBits(v7);
          LogonHours = (struct _USER_STRING_LIST *)v246;
          v38 = WPP_GLOBAL_Control;
        }
        else
        {
          v39 = 0;
        }
        if ( (_DWORD)LogonHours != 28 )
        {
          if ( (_DWORD)LogonHours == 29 )
          {
            v9 = v243;
            updated = SampRetrieveUserPasswords(v7, &v262, (_BYTE *)&v244 + 3, &v263, v245, (bool *)&v244 + 2);
            if ( updated >= 0 )
            {
              v194 = *a6;
              LOBYTE(v244) = HIBYTE(v244);
              BYTE1(v244) = BYTE2(v244);
              *v194 = BYTE2(v244) == 0;
              BYTE1((*a6)->LowPart) = v258[2] & 1;
              goto LABEL_118;
            }
            goto LABEL_590;
          }
          if ( (_DWORD)LogonHours != 27 )
          {
            if ( (_DWORD)LogonHours != 21 )
            {
              switch ( v31 )
              {
                case 0u:
                  (*a6)[4].LowPart = v258[1];
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_117;
                  QuadPart = (void *)(*a6)[1].QuadPart;
                  if ( QuadPart )
                  {
                    v9 = v243;
                    if ( v243 < 0x40 )
                    {
                      hMem[v243] = QuadPart;
                      ++v9;
                    }
                  }
                  else
                  {
                    v9 = v243;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v66 = (void *)(*a6)[3].QuadPart;
                  if ( v66 && v9 < 0x40 )
                  {
                    v67 = v9++;
                    hMem[v67] = v66;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v68 = (void *)(*a6)[6].QuadPart;
                  if ( v68 && v9 < 0x40 )
                  {
                    v69 = v9++;
                    hMem[v69] = v68;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v64 = (void *)(*a6)[8].QuadPart;
                  goto LABEL_167;
                case 1u:
                  (*a6)[4].LowPart = v258[3];
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_117;
                  v73 = *a6;
                  v74 = (void *)(*a6)[1].QuadPart;
                  if ( v74 )
                  {
                    v9 = v243;
                    if ( v243 < 0x40 )
                    {
                      hMem[v243] = v74;
                      ++v9;
                    }
                  }
                  else
                  {
                    v9 = v243;
                  }
                  LOWORD(v73[2].LowPart) = 0;
                  HIWORD((*a6)[2].u.LowPart) = 0;
                  (*a6)[3].QuadPart = 0;
                  goto LABEL_118;
                case 2u:
                  v75 = (union _LARGE_INTEGER *)((char *)SampDefinedDomains + 1360 * *((unsigned int *)v7 + 50));
                  (*a6)[4].LowPart = v258[0];
                  (*a6)[4].HighPart = v258[1];
                  (*a6)[15] = *(union _LARGE_INTEGER *)((char *)&v255 + 8);
                  (*a6)[16] = v256[0];
                  LOWORD((*a6)[22].LowPart) = v259;
                  (*a6)[17] = v256[1];
                  (*a6)[18].QuadPart = ((__int64 (__fastcall *)(_QWORD, _QWORD))SampAddDeltaTime)(
                                         (union _LARGE_INTEGER)v256[1].QuadPart,
                                         (union _LARGE_INTEGER)v75[66].QuadPart);
                  (*a6)[19] = SampGetPasswordMustChange(v7, v258[2], v256[1], v75[65]);
                  HIWORD((*a6)[22].u.LowPart) = WORD1(v259);
                  (*a6)[22].HighPart = v258[2];
                  updated = SampRetrieveUserPasswords(v7, &v262, (_BYTE *)&v244 + 3, &v263, v245, (bool *)&v244 + 2);
                  if ( updated < 0 )
                  {
                    v9 = v243;
                    goto LABEL_590;
                  }
                  LOBYTE(v244) = HIBYTE(v244);
                  BYTE1(v244) = BYTE2(v244);
                  if ( !HIWORD(v244) )
                    (*a6)[18] = SampHasNeverTime;
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_117;
                  v76 = (void *)(*a6)[1].QuadPart;
                  if ( v76 )
                  {
                    v9 = v243;
                    if ( v243 < 0x40 )
                    {
                      hMem[v243] = v76;
                      ++v9;
                    }
                  }
                  else
                  {
                    v9 = v243;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v77 = (void *)(*a6)[3].QuadPart;
                  if ( v77 && v9 < 0x40 )
                  {
                    v78 = v9++;
                    hMem[v78] = v77;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v79 = (void *)(*a6)[6].QuadPart;
                  if ( v79 && v9 < 0x40 )
                  {
                    v80 = v9++;
                    hMem[v80] = v79;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v81 = (void *)(*a6)[8].QuadPart;
                  if ( v81 && v9 < 0x40 )
                  {
                    v82 = v9++;
                    hMem[v82] = v81;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v83 = (void *)(*a6)[10].QuadPart;
                  if ( v83 && v9 < 0x40 )
                  {
                    v84 = v9++;
                    hMem[v84] = v83;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v85 = (void *)(*a6)[12].QuadPart;
                  if ( v85 && v9 < 0x40 )
                  {
                    v86 = v9++;
                    hMem[v86] = v85;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v87 = (struct _LOGON_HOURS *)*a6;
                  v88 = (void *)(*a6)[14].QuadPart;
                  if ( v88 && v9 < 0x40 )
                  {
                    v89 = v9++;
                    hMem[v89] = v88;
                  }
                  updated = SampRetrieveUserLogonHours(v7, v87 + 10);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v64 = (void *)(*a6)[21].QuadPart;
LABEL_167:
                  if ( !v64 )
                    goto LABEL_118;
                  v25 = 16;
                  if ( v9 >= 0x40 )
                    goto LABEL_119;
                  hMem[v9] = v64;
                  break;
                case 3u:
                  UserLogonHours = SampRetrieveUserLogonHours(v7, (struct _LOGON_HOURS *)*a6);
                  goto LABEL_194;
                case 4u:
                  (*a6)[4].LowPart = v258[0];
                  (*a6)[4].HighPart = v258[1];
                  (*a6)[17] = *(union _LARGE_INTEGER *)((char *)&v255 + 8);
                  v47 = (struct _LOGON_HOURS *)*a6;
                  *(union _LARGE_INTEGER *)&v47[9].UnitsPerWeek = v256[0];
                  LOWORD((*a6)[21].LowPart) = SampQueryBadPasswordCount(
                                                (struct _SAMP_OBJECT *)v47,
                                                (struct _SAMP_V1_0A_FIXED_LENGTH_USER *)&v255,
                                                (struct _DOMAIN_LOCKOUT_INFORMATION *)&v264[1]);
                  HIWORD((*a6)[21].u.LowPart) = WORD1(v259);
                  *(union _LARGE_INTEGER *)((char *)*a6 + 172) = v256[1];
                  *(LONGLONG *)((char *)&(*a6)[22].QuadPart + 4) = v257;
                  (*a6)[23].HighPart = v258[2];
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_117;
                  v48 = (void *)(*a6)[1].QuadPart;
                  if ( v48 )
                  {
                    v9 = v243;
                    if ( v243 < 0x40 )
                    {
                      hMem[v243] = v48;
                      ++v9;
                    }
                  }
                  else
                  {
                    v9 = v243;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v49 = (void *)(*a6)[3].QuadPart;
                  if ( v49 && v9 < 0x40 )
                  {
                    v50 = v9++;
                    hMem[v50] = v49;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v51 = (void *)(*a6)[6].QuadPart;
                  if ( v51 && v9 < 0x40 )
                  {
                    v52 = v9++;
                    hMem[v52] = v51;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v53 = (void *)(*a6)[8].QuadPart;
                  if ( v53 && v9 < 0x40 )
                  {
                    v54 = v9++;
                    hMem[v54] = v53;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v55 = (void *)(*a6)[10].QuadPart;
                  if ( v55 && v9 < 0x40 )
                  {
                    v56 = v9++;
                    hMem[v56] = v55;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v57 = (void *)(*a6)[12].QuadPart;
                  if ( v57 && v9 < 0x40 )
                  {
                    v58 = v9++;
                    hMem[v58] = v57;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v59 = (void *)(*a6)[14].QuadPart;
                  if ( v59 && v9 < 0x40 )
                  {
                    v60 = v9++;
                    hMem[v60] = v59;
                  }
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v61 = (struct _LOGON_HOURS *)*a6;
                  v62 = (void *)(*a6)[16].QuadPart;
                  if ( v62 && v9 < 0x40 )
                  {
                    v63 = v9++;
                    hMem[v63] = v62;
                  }
                  updated = SampRetrieveUserLogonHours(v7, (struct _LOGON_HOURS *)((char *)v61 + 152));
                  if ( updated < 0 )
                    goto LABEL_118;
                  v64 = (void *)(*a6)[20].QuadPart;
                  goto LABEL_167;
                case 5u:
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_117;
                  v70 = (void *)(*a6)[1].QuadPart;
                  if ( v70 )
                  {
                    v9 = v243;
                    if ( v243 < 0x40 )
                    {
                      hMem[v243] = v70;
                      ++v9;
                    }
                  }
                  else
                  {
                    v9 = v243;
                  }
                  goto LABEL_191;
                case 6u:
                case 7u:
                case 0xAu:
                case 0xBu:
                case 0xCu:
                case 0xDu:
                case 0x13u:
                  UserLogonHours = SampGetUnicodeStringAttribute(v7);
LABEL_194:
                  updated = UserLogonHours;
                  if ( UserLogonHours < 0 )
                    goto LABEL_117;
                  v72 = (void *)(*a6)[1].QuadPart;
                  if ( !v72 )
                    goto LABEL_117;
                  v9 = v243;
                  v25 = 16;
                  if ( v243 >= 0x40 )
                    goto LABEL_119;
                  hMem[v243] = v72;
                  break;
                case 8u:
                  (*a6)->LowPart = v258[1];
                  goto LABEL_117;
                case 9u:
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_117;
                  v90 = (void *)(*a6)[1].QuadPart;
                  if ( v90 )
                  {
                    v9 = v243;
                    if ( v243 < 0x40 )
                    {
                      hMem[v243] = v90;
                      ++v9;
                    }
                  }
                  else
                  {
                    v9 = v243;
                  }
LABEL_191:
                  updated = SampGetUnicodeStringAttribute(v7);
                  if ( updated < 0 )
                    goto LABEL_118;
                  v64 = (void *)(*a6)[3].QuadPart;
                  goto LABEL_167;
                case 0xFu:
                  (*a6)->LowPart = v258[2];
                  goto LABEL_117;
                case 0x10u:
                  (*a6)->QuadPart = v257;
                  goto LABEL_117;
                case 0x11u:
                  if ( (*((_BYTE *)v7 + 20) & 0x20) != 0 )
                  {
                    BYTE2((*a6)[4].u.LowPart) = 0;
                    UserPasswords = SampRetrieveUserPasswords(
                                      v7,
                                      (struct _LM_OWF_PASSWORD *)&(*a6)[2],
                                      (_BYTE *)&(*a6)[4] + 1,
                                      (struct _LM_OWF_PASSWORD *)*a6,
                                      v245,
                                      (bool *)&(*a6)[4]);
LABEL_116:
                    updated = UserPasswords;
                  }
                  else
                  {
                    updated = -1073741821;
                  }
                  goto LABEL_117;
                case 0x12u:
                  v25 = 16;
                  v9 = v243;
                  if ( (*((_BYTE *)v7 + 20) & 0x20) != 0 )
                  {
                    *(LONGLONG *)((char *)&(*a6)->QuadPart + 4) = *(_QWORD *)((LONGLONG)&v255 + 8);
                    *(union _LARGE_INTEGER *)((char *)*a6 + 12) = v256[0];
                    (*a6)[2].HighPart = v259;
                  }
                  else
                  {
                    updated = -1073741821;
                  }
                  goto LABEL_119;
                case 0x15u:
                  goto LABEL_373;
                case 0x1Du:
                  (*a6)->LowPart = 0x4000000;
                  UserPasswords = SampQueryObjectExtendedAttributesEx(
                                    v7,
                                    0x4000000u,
                                    1u,
                                    (const struct _SAMP_ATTRIBUTES_INFORMATION *)&UserExtendedAttributesResetData,
                                    0,
                                    *a6);
                  goto LABEL_116;
                case 0x20u:
                  if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                    goto LABEL_261;
                  UserPasswords = SampQueryShadowAccountLinks(v7, (void **)*a6, (void **)&(*a6)[1]);
                  goto LABEL_116;
                case 0x21u:
                  if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                    goto LABEL_261;
                  UserPasswords = SampQueryShadowAccountExternalInfo(
                                    v7,
                                    (struct _SAMPR_USER_SHADOWACCOUNT_EXTERNAL_INFORMATION *)*a6);
                  goto LABEL_116;
                default:
                  goto LABEL_117;
              }
LABEL_170:
              ++v9;
LABEL_119:
              SampDeReferenceContext(v7, 0);
              v16 = v247;
              break;
            }
            goto LABEL_373;
          }
          v91 = (struct _LOGON_HOURS *)*a6;
          v92 = a5;
          *(_OWORD *)&(*a6)[94].LowPart = *(_OWORD *)((char *)v7 + 252);
          if ( (a5 & 2) != 0 && (LogonHours = (struct _USER_STRING_LIST *)*((_QWORD *)v7 + 66)) != 0 )
          {
            if ( !*((_BYTE *)v7 + 536) )
            {
LABEL_261:
              updated = -1073741811;
              goto LABEL_117;
            }
            updated = SampCopyStringListAttribute(LogonHours, (struct _USER_STRING_LIST **)&v91[22]);
            if ( updated < 0 )
            {
LABEL_373:
              v9 = v243;
              goto LABEL_374;
            }
            LogonHours = *(struct _USER_STRING_LIST **)&v91[22].UnitsPerWeek;
            if ( LogonHours )
            {
              v9 = v243;
              if ( v243 < 0x40 )
              {
                hMem[v243] = LogonHours;
                v250[0] = ++v9;
              }
            }
            else
            {
              v9 = v243;
            }
            LODWORD(v91[20].LogonHours) |= 2u;
            v92 = a5;
          }
          else
          {
            v9 = v243;
          }
          if ( (v92 & 4) != 0 )
          {
            LogonHours = (struct _USER_STRING_LIST *)*((_QWORD *)v7 + 68);
            if ( LogonHours )
            {
              if ( !*((_BYTE *)v7 + 552) )
              {
                updated = -1073741811;
                goto LABEL_118;
              }
              updated = SampCopyStringListAttribute(LogonHours, (struct _USER_STRING_LIST **)&v91[22].LogonHours);
              if ( updated < 0 )
                goto LABEL_374;
              LogonHours = (struct _USER_STRING_LIST *)v91[22].LogonHours;
              if ( LogonHours && v9 < 0x40 )
              {
                v93 = v9++;
                v250[0] = v9;
                hMem[v93] = LogonHours;
              }
              LODWORD(v91[20].LogonHours) |= 4u;
              v92 = a5;
            }
          }
          if ( (v92 & 1) != 0 )
          {
            updated = SampDuplicateUnicodeString((PUNICODE_STRING)&v91[21], (PCUNICODE_STRING)v7 + 21);
            if ( updated < 0 )
              goto LABEL_374;
            LogonHours = (struct _USER_STRING_LIST *)v91[21].LogonHours;
            if ( LogonHours && v9 < 0x40 )
            {
              v94 = v9++;
              v250[0] = v9;
              hMem[v94] = LogonHours;
            }
            LODWORD(v91[20].LogonHours) |= 1u;
            BYTE4(v91[20].LogonHours) = *((_BYTE *)v7 + 352);
          }
          if ( (v92 & 8) != 0 )
          {
            if ( !*((_BYTE *)v7 + 560) )
            {
              updated = -1073741811;
              goto LABEL_118;
            }
            LODWORD(v91[20].LogonHours) |= 8u;
            *(_DWORD *)&v91[23].UnitsPerWeek = *((_DWORD *)v7 + 139);
          }
          if ( (v92 & 0x10) != 0 )
          {
            LODWORD(v91[20].LogonHours) |= 0x10u;
            *((_DWORD *)&v91[23].UnitsPerWeek + 1) = LOWORD(v264[1].MinPasswordAge.LowPart);
          }
          if ( (v92 & 0x20) != 0 )
          {
            if ( !*((_BYTE *)v7 + 568) && *((_DWORD *)v7 + 62) != 502 )
            {
              updated = -1073741811;
              goto LABEL_118;
            }
            LODWORD(v91[20].LogonHours) |= 0x20u;
            LODWORD(v91[23].LogonHours) = *((_DWORD *)v7 + 141);
          }
          if ( (v92 & 0x40) != 0 )
          {
            if ( !*((_BYTE *)v7 + 576) )
            {
              updated = -1073741811;
              goto LABEL_118;
            }
            LODWORD(v91[20].LogonHours) |= 0x40u;
            HIDWORD(v91[23].LogonHours) = *((_DWORD *)v7 + 143);
          }
          if ( (v92 & 0x200) != 0 )
          {
            v260 = 0;
            v261 = 0;
            updated = SampQueryObjectExtendedAttributesEx(
                        v7,
                        0x200u,
                        4u,
                        (const struct _SAMP_ATTRIBUTES_INFORMATION *)qword_1800D3230,
                        0,
                        &v260);
            if ( updated < 0 )
              goto LABEL_374;
            v95 = *(union _LARGE_INTEGER *)((char *)&v260 + 8);
            v96.QuadPart = v261;
            LODWORD(v91[20].LogonHours) |= v260;
            v97 = DWORD2(v261);
            if ( v95.QuadPart == SampHasNeverTime.QuadPart )
              v95 = SampWillNeverTime;
            v91[24].LogonHours = (PUCHAR)v95.QuadPart;
            if ( v96.QuadPart == SampHasNeverTime.QuadPart )
              v96 = SampWillNeverTime;
            LODWORD(v91[25].LogonHours) = v97 - HIDWORD(v261);
            *(union _LARGE_INTEGER *)&v91[25].UnitsPerWeek = v96;
            if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x1000) != 0
              && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
            {
              HighPart = v96.HighPart;
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))WPP_SF_dDDDDd)(
                WPP_GLOBAL_Control[3].Buffer,
                (union _LARGE_INTEGER)v95.QuadPart,
                (union _LARGE_INTEGER)v96.QuadPart,
                v258[0],
                v95.LowPart,
                v95.HighPart,
                v96.LowPart);
            }
          }
          if ( (v92 & 0x80u) != 0 )
          {
            LogonHours = (struct _USER_STRING_LIST *)*((_QWORD *)v7 + 73);
            if ( LogonHours )
            {
              if ( !*((_BYTE *)v7 + 592) )
              {
                updated = -1073741811;
                goto LABEL_118;
              }
              updated = SampCopyStringListAttribute(LogonHours, (struct _USER_STRING_LIST **)&v91[24]);
              if ( updated < 0 )
                goto LABEL_374;
              LogonHours = *(struct _USER_STRING_LIST **)&v91[24].UnitsPerWeek;
              if ( LogonHours && v9 < 0x40 )
              {
                v98 = v9++;
                v250[0] = v9;
                hMem[v98] = LogonHours;
              }
              LODWORD(v91[20].LogonHours) |= 0x80u;
              v92 = a5;
            }
          }
          if ( (v92 & 0x800) != 0 )
          {
            LogonHours = (struct _USER_STRING_LIST *)*((_QWORD *)v7 + 75);
            if ( LogonHours )
            {
              updated = SampCopyA2DFAttribute(
                          (struct _SECURITY_DESCRIPTOR_RELATIVE *)LogonHours,
                          *((unsigned int *)v7 + 149),
                          (struct _SECURITY_DESCRIPTOR_RELATIVE **)&v91[32].LogonHours);
              if ( updated < 0 )
                goto LABEL_374;
              LogonHours = (struct _USER_STRING_LIST *)v91[32].LogonHours;
              if ( LogonHours && v9 < 0x40 )
              {
                v99 = v9++;
                v250[0] = v9;
                hMem[v99] = LogonHours;
              }
              LODWORD(v91[20].LogonHours) |= 0x800u;
              v92 = a5;
            }
          }
          if ( (v92 & 0x2000000) != 0 )
          {
            updated = SampDuplicateUnicodeString(
                        (PUNICODE_STRING)&v91[33].LogonHours,
                        (PCUNICODE_STRING)((char *)v7 + 616));
            if ( updated < 0 )
              goto LABEL_374;
            v100 = *(void **)&v91[34].UnitsPerWeek;
            if ( v100 && v9 < 0x40 )
            {
              v101 = v9++;
              v250[0] = v9;
              hMem[v101] = v100;
            }
            updated = SampDuplicateUnicodeString((PUNICODE_STRING)&v91[34].LogonHours, (PCUNICODE_STRING)v7 + 40);
            if ( updated < 0 )
              goto LABEL_374;
            v102 = *(void **)&v91[35].UnitsPerWeek;
            if ( v102 && v9 < 0x40 )
            {
              v103 = v9++;
              v250[0] = v9;
              hMem[v103] = v102;
            }
            updated = SampCopySecurityDescriptor(
                        *((struct _SECURITY_DESCRIPTOR_RELATIVE **)v7 + 83),
                        (struct _SECURITY_DESCRIPTOR_RELATIVE **)&v91[36].LogonHours);
            if ( updated < 0 )
              goto LABEL_374;
            v104 = v91[36].LogonHours;
            if ( v104 && v9 < 0x40 )
            {
              v105 = v9++;
              v250[0] = v9;
              hMem[v105] = v104;
            }
            updated = SampCopySecurityDescriptor(
                        *((struct _SECURITY_DESCRIPTOR_RELATIVE **)v7 + 84),
                        (struct _SECURITY_DESCRIPTOR_RELATIVE **)&v91[37]);
            if ( updated < 0 )
              goto LABEL_374;
            LogonHours = *(struct _USER_STRING_LIST **)&v91[37].UnitsPerWeek;
            if ( LogonHours && v9 < 0x40 )
            {
              v106 = v9++;
              v250[0] = v9;
              hMem[v106] = LogonHours;
            }
            *(_QWORD *)&v91[36].UnitsPerWeek = *((_QWORD *)v7 + 82);
            v107 = (char *)v7 + 609;
            if ( !*((_BYTE *)v7 + 608) )
              v107 = (char *)v7 + 632;
            v92 = a5;
            LOBYTE(v91[35].LogonHours) = *v107;
            LOBYTE(v91[37].LogonHours) = *((_BYTE *)v7 + 680);
            v108 = *((_DWORD *)v7 + 171);
            LODWORD(v91[20].LogonHours) |= 0x2000000u;
            HIDWORD(v91[37].LogonHours) = v108;
          }
          if ( (v92 & 0x8000000) != 0 )
            *(struct _LOGON_HOURS *)((char *)v91 + 628) = *((struct _LOGON_HOURS *)v7 + 43);
          if ( (v92 & 0x10000000) != 0 )
            v91[40].LogonHours = (PUCHAR)*((_QWORD *)v7 + 93);
          if ( (v92 & 0x20000000) != 0 )
          {
            if ( *((_QWORD *)v7 + 104) )
            {
              v109 = *((_DWORD *)v7 + 210);
              if ( v109 )
              {
                v110 = LocalAlloc(0x40u, v109);
                *(_QWORD *)&v91[46].UnitsPerWeek = v110;
                v111 = v110;
                if ( !v110 )
                {
                  updated = -1073741670;
                  goto LABEL_118;
                }
                if ( v9 < 0x40 )
                {
                  v112 = v9++;
                  v250[0] = v9;
                  hMem[v112] = v111;
                }
                memcpy_0(v111, *((const void **)v7 + 104), *((unsigned int *)v7 + 210));
                LODWORD(v91[46].LogonHours) = *((_DWORD *)v7 + 210);
              }
            }
            if ( *((_QWORD *)v7 + 102) )
            {
              v113 = *((_DWORD *)v7 + 206);
              if ( v113 )
              {
                v114 = LocalAlloc(0x40u, v113);
                *(_QWORD *)&v91[45].UnitsPerWeek = v114;
                v115 = v114;
                if ( !v114 )
                {
                  updated = -1073741670;
                  goto LABEL_118;
                }
                if ( v9 < 0x40 )
                {
                  v116 = v9++;
                  v250[0] = v9;
                  hMem[v116] = v115;
                }
                memcpy_0(v115, *((const void **)v7 + 102), *((unsigned int *)v7 + 206));
                LODWORD(v91[45].LogonHours) = *((_DWORD *)v7 + 206);
              }
            }
            LODWORD(v91[44].LogonHours) = *((_DWORD *)v7 + 202);
            BYTE4(v91[44].LogonHours) = *((_BYTE *)v7 + 812);
            LOBYTE(v91[41].UnitsPerWeek) = *((_BYTE *)v7 + 752);
            *(struct _LOGON_HOURS *)((char *)v91 + 660) = *(struct _LOGON_HOURS *)((char *)v7 + 756);
            *((_DWORD *)&v91[42].UnitsPerWeek + 1) = *((_DWORD *)v7 + 193);
            LOBYTE(v91[42].LogonHours) = *((_BYTE *)v7 + 776);
            *(struct _LOGON_HOURS *)((char *)v91 + 684) = *(struct _LOGON_HOURS *)((char *)v7 + 780);
            HIDWORD(v91[43].LogonHours) = *((_DWORD *)v7 + 199);
            LOBYTE(v91[44].UnitsPerWeek) = *((_BYTE *)v7 + 800);
          }
          if ( (v92 & 0x400) != 0 )
          {
            v260 = 0;
            v261 = 0;
            updated = SampQueryObjectExtendedAttributesEx(
                        v7,
                        0x400u,
                        2u,
                        (const struct _SAMP_ATTRIBUTES_INFORMATION *)L"\b",
                        0,
                        &v260);
            if ( updated < 0 )
              goto LABEL_374;
            LODWORD(v91[20].LogonHours) |= v260;
            LogonHours = (struct _USER_STRING_LIST *)v261;
            v91[31].LogonHours = (PUCHAR)*((_QWORD *)&v260 + 1);
            *(_QWORD *)&v91[32].UnitsPerWeek = LogonHours;
            if ( LogonHours && v9 < 0x40 )
            {
              v117 = v9++;
              v250[0] = v9;
              hMem[v117] = LogonHours;
            }
          }
          v118 = v92 & 0xFFF000;
          if ( v118 )
          {
            memset_0(v265, 0, 0xA8u);
            updated = SampQueryObjectExtendedAttributesEx(
                        v7,
                        v118,
                        0xBu,
                        (const struct _SAMP_ATTRIBUTES_INFORMATION *)&UserExtendedAttributesInformation,
                        0,
                        v265);
            if ( updated >= 0 )
            {
              v243 = 0;
              v120 = SampMapInformationLevel((unsigned int)LogonHours, v119, v265, v91, a5, &v243, v250, HighPart, hMem);
              v9 = v250[0];
              updated = v120;
              if ( v120 >= 0 )
              {
                LODWORD(v91[20].LogonHours) |= v243;
LABEL_375:
                v121 = (struct _LOGON_HOURS *)*a6;
                if ( (v30 & 0x1020000) == 0 )
                  goto LABEL_378;
                updated = SampRetrieveUserPasswords(v7, &v262, (_BYTE *)&v244 + 3, &v263, v245, (bool *)&v244 + 2);
                if ( updated >= 0 )
                {
                  BYTE1(v244) = BYTE2(v244);
                  v248 = v245[0];
                  LOBYTE(v244) = HIBYTE(v244);
LABEL_378:
                  if ( (v30 & 1) == 0 )
                    goto LABEL_413;
                  v122 = (struct _LOGON_HOURS *)*a6;
                  if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                  {
                    if ( *((_QWORD *)v7 + 14) )
                    {
                      if ( _bittest64(*((const signed __int64 **)v7 + 8), 1u) )
                      {
                        v123 = (void *)*((_QWORD *)v7 + 17);
                        if ( v123 )
                          LocalFree(v123);
                        v124 = *((_QWORD *)v7 + 14);
                        *((_BYTE *)v7 + 20) &= 0xF0u;
                        *((_QWORD *)v7 + 17) = v124;
                        *((_QWORD *)v7 + 14) = 0;
                        *((_QWORD *)v7 + 15) = 0;
                        *((_DWORD *)v7 + 32) = 0;
                        updated = SampValidateDsAttributes(v7, 0);
                        if ( updated >= 0 )
                        {
                          updated = SampValidateDsAttributes(v7, 1u);
                          if ( updated >= 0 )
                          {
                            SampMarkPerAttributeInvalidFromWhichFields(v7, 0);
                            *((_BYTE *)v7 + 29) &= ~1u;
                          }
                        }
                        goto LABEL_391;
                      }
                    }
                    else
                    {
                      updated = SampValidateDsAttributes(v7, 0);
                      if ( updated < 0 )
                      {
LABEL_391:
                        v126 = WPP_GLOBAL_Control;
                        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                        {
                          WPP_SF_Dd(
                            WPP_GLOBAL_Control[3].Buffer,
                            110,
                            WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
                            (unsigned int)updated,
                            updated);
                          v126 = WPP_GLOBAL_Control;
                        }
                        if ( updated < 0 )
                        {
LABEL_394:
                          if ( (*(_DWORD *)(&v126[4].MaximumLength + 1) & 0x20000) != 0 )
                          {
                            v127 = 29;
                            v128 = (unsigned int)updated;
LABEL_396:
                            WPP_SF_Dd(
                              v126[3].Buffer,
                              v127,
                              WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
                              v128,
                              updated);
                          }
LABEL_118:
                          v25 = 16;
                          goto LABEL_119;
                        }
                        v129 = 22LL * *((int *)v7 + 4);
                        if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                          v130 = (unsigned int)dword_1800EEC4C[v129];
                        else
                          v130 = (unsigned int)dword_1800EEC34[v129];
                        v131 = *(_DWORD *)(*((_QWORD *)v7 + 14) + v130 + 16);
                        *(&v122[3].UnitsPerWeek + 1) = v131;
                        v122[3].UnitsPerWeek = v131;
                        v132 = v131;
                        v133 = (UCHAR *)LocalAlloc(0x40u, v131);
                        v122[3].LogonHours = v133;
                        v134 = v133;
                        if ( !v133 )
                        {
                          *(_DWORD *)&v122[3].UnitsPerWeek = 0;
LABEL_402:
                          v126 = WPP_GLOBAL_Control;
                          updated = -1073741801;
                          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
                            goto LABEL_118;
                          v127 = 31;
                          v128 = 3221225495LL;
                          goto LABEL_396;
                        }
                        v135 = *((_QWORD *)v7 + 14);
                        v136 = 22LL * *((int *)v7 + 4);
                        if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                          v137 = dword_1800EEC48[v136] + *(_DWORD *)((unsigned int)dword_1800EEC4C[v136] + v135 + 12);
                        else
                          v137 = dword_1800EEC38[v136] + *(_DWORD *)((unsigned int)dword_1800EEC34[v136] + v135 + 12);
                        memcpy_0(v134, (const void *)(v135 + v137), v132);
                        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                          WPP_SF_Dd(
                            WPP_GLOBAL_Control[3].Buffer,
                            32,
                            WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
                            0,
                            0);
                        LogonHours = (struct _USER_STRING_LIST *)v121[3].LogonHours;
                        if ( LogonHours && v9 < 0x40 )
                        {
                          v138 = v9++;
                          hMem[v138] = LogonHours;
                        }
                        updated = 0;
LABEL_413:
                        if ( (v30 & 2) == 0 )
                          goto LABEL_443;
                        if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                        {
                          if ( *((_QWORD *)v7 + 14) )
                          {
                            if ( _bittest64(*((const signed __int64 **)v7 + 8), 2u) )
                            {
                              v139 = (void *)*((_QWORD *)v7 + 17);
                              if ( v139 )
                                LocalFree(v139);
                              v140 = *((_QWORD *)v7 + 14);
                              *((_BYTE *)v7 + 20) &= 0xF0u;
                              *((_QWORD *)v7 + 17) = v140;
                              *((_QWORD *)v7 + 14) = 0;
                              *((_QWORD *)v7 + 15) = 0;
                              *((_DWORD *)v7 + 32) = 0;
                              updated = SampValidateDsAttributes(v7, 0);
                              if ( updated >= 0 )
                              {
                                updated = SampValidateDsAttributes(v7, 1u);
                                if ( updated >= 0 )
                                {
                                  SampMarkPerAttributeInvalidFromWhichFields(v7, 0);
                                  *((_BYTE *)v7 + 29) &= ~1u;
                                }
                              }
                              goto LABEL_426;
                            }
                          }
                          else
                          {
                            updated = SampValidateDsAttributes(v7, 0);
                            if ( updated < 0 )
                            {
LABEL_426:
                              v126 = WPP_GLOBAL_Control;
                              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                              {
                                WPP_SF_Dd(
                                  WPP_GLOBAL_Control[3].Buffer,
                                  110,
                                  WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
                                  (unsigned int)updated,
                                  updated);
                                v126 = WPP_GLOBAL_Control;
                              }
                              if ( updated < 0 )
                                goto LABEL_394;
                              v142 = 22LL * *((int *)v7 + 4);
                              if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                                v143 = (unsigned int)dword_1800EEC4C[v142];
                              else
                                v143 = (unsigned int)dword_1800EEC34[v142];
                              v144 = *(_DWORD *)(*((_QWORD *)v7 + 14) + v143 + 28);
                              *(&v121[4].UnitsPerWeek + 1) = v144;
                              v121[4].UnitsPerWeek = v144;
                              v145 = v144;
                              v146 = (UCHAR *)LocalAlloc(0x40u, v144);
                              v121[4].LogonHours = v146;
                              v147 = v146;
                              if ( !v146 )
                              {
                                *(_DWORD *)&v121[4].UnitsPerWeek = 0;
                                goto LABEL_402;
                              }
                              v148 = *((_QWORD *)v7 + 14);
                              v149 = 22LL * *((int *)v7 + 4);
                              if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                                v150 = dword_1800EEC48[v149]
                                     + *(_DWORD *)((unsigned int)dword_1800EEC4C[v149] + v148 + 24);
                              else
                                v150 = dword_1800EEC38[v149]
                                     + *(_DWORD *)((unsigned int)dword_1800EEC34[v149] + v148 + 24);
                              memcpy_0(v147, (const void *)(v148 + v150), v145);
                              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                                WPP_SF_Dd(
                                  WPP_GLOBAL_Control[3].Buffer,
                                  32,
                                  WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
                                  0,
                                  0);
                              LogonHours = (struct _USER_STRING_LIST *)v121[4].LogonHours;
                              if ( LogonHours && v9 < 0x40 )
                              {
                                v151 = v9++;
                                hMem[v151] = LogonHours;
                              }
                              updated = 0;
LABEL_443:
                              if ( (v30 & 4) != 0 )
                                *(_DWORD *)&v121[17].UnitsPerWeek = v258[0];
                              if ( (v30 & 8) != 0 )
                                *((_DWORD *)&v121[17].UnitsPerWeek + 1) = v258[1];
                              if ( (v30 & 0x10) != 0 )
                              {
                                updated = SampGetUnicodeStringAttribute(v7);
                                if ( updated < 0 )
                                  goto LABEL_118;
                                LogonHours = (struct _USER_STRING_LIST *)v121[9].LogonHours;
                                if ( LogonHours && v9 < 0x40 )
                                {
                                  v152 = v9++;
                                  hMem[v152] = LogonHours;
                                }
                              }
                              if ( (v30 & 0x20) != 0 )
                              {
                                updated = SampGetUnicodeStringAttribute(v7);
                                if ( updated < 0 )
                                  goto LABEL_118;
                                LogonHours = (struct _USER_STRING_LIST *)v121[11].LogonHours;
                                if ( LogonHours && v9 < 0x40 )
                                {
                                  v153 = v9++;
                                  hMem[v153] = LogonHours;
                                }
                              }
                              if ( (v30 & 0x40) != 0 )
                              {
                                updated = SampGetUnicodeStringAttribute(v7);
                                if ( updated < 0 )
                                  goto LABEL_118;
                                LogonHours = (struct _USER_STRING_LIST *)v121[5].LogonHours;
                                if ( LogonHours && v9 < 0x40 )
                                {
                                  v154 = v9++;
                                  hMem[v154] = LogonHours;
                                }
                              }
                              if ( (v30 & 0x80u) != 0 )
                              {
                                updated = SampGetUnicodeStringAttribute(v7);
                                if ( updated < 0 )
                                  goto LABEL_118;
                                LogonHours = (struct _USER_STRING_LIST *)v121[6].LogonHours;
                                if ( LogonHours && v9 < 0x40 )
                                {
                                  v155 = v9++;
                                  hMem[v155] = LogonHours;
                                }
                              }
                              if ( (v30 & 0x100) != 0 )
                              {
                                updated = SampGetUnicodeStringAttribute(v7);
                                if ( updated < 0 )
                                  goto LABEL_118;
                                LogonHours = (struct _USER_STRING_LIST *)v121[7].LogonHours;
                                if ( LogonHours && v9 < 0x40 )
                                {
                                  v156 = v9++;
                                  hMem[v156] = LogonHours;
                                }
                              }
                              if ( (v30 & 0x200) != 0 )
                              {
                                updated = SampGetUnicodeStringAttribute(v7);
                                if ( updated < 0 )
                                  goto LABEL_118;
                                LogonHours = (struct _USER_STRING_LIST *)v121[8].LogonHours;
                                if ( LogonHours && v9 < 0x40 )
                                {
                                  v157 = v9++;
                                  hMem[v157] = LogonHours;
                                }
                              }
                              if ( (v30 & 0x400) != 0 )
                              {
                                updated = SampGetUnicodeStringAttribute(v7);
                                if ( updated < 0 )
                                  goto LABEL_118;
                                LogonHours = (struct _USER_STRING_LIST *)v121[10].LogonHours;
                                if ( LogonHours && v9 < 0x40 )
                                {
                                  v158 = v9++;
                                  hMem[v158] = LogonHours;
                                }
                              }
                              if ( (v30 & 0x800) != 0 )
                                *(_QWORD *)&v121->UnitsPerWeek = *((_QWORD *)&v255 + 1);
                              if ( (v30 & 0x1000) != 0 )
                                v121->LogonHours = (PUCHAR)v256[0];
                              if ( (v30 & 0x2000) != 0 )
                              {
                                updated = SampRetrieveUserLogonHours(v7, v121 + 18);
                                if ( updated < 0 )
                                  goto LABEL_118;
                                LogonHours = (struct _USER_STRING_LIST *)v121[18].LogonHours;
                                if ( LogonHours && v9 < 0x40 )
                                {
                                  v159 = v9++;
                                  hMem[v159] = LogonHours;
                                }
                              }
                              if ( (v30 & 0x4000) != 0 )
                              {
                                BadPasswordCount = SampQueryBadPasswordCount(
                                                     LogonHours,
                                                     (struct _SAMP_V1_0A_FIXED_LENGTH_USER *)&v255,
                                                     (struct _DOMAIN_LOCKOUT_INFORMATION *)&v264[1]);
                                v161 = v246;
                                v121[19].UnitsPerWeek = BadPasswordCount;
                                if ( v161 == 22 )
                                  *(union _LARGE_INTEGER *)((char *)*a6 + 316) = *(union _LARGE_INTEGER *)((char *)&v257 + 8);
                              }
                              else
                              {
                                v161 = v246;
                              }
                              if ( (v30 & 0x8000) != 0 )
                                *(&v121[19].UnitsPerWeek + 1) = WORD1(v259);
                              v162 = BYTE1(v244);
                              if ( (v30 & 0x10000) != 0 )
                              {
                                if ( !BYTE1(v244) )
                                {
                                  v163 = v244;
                                  if ( !(_BYTE)v244 )
                                  {
                                    *(union _LARGE_INTEGER *)&v121[2].UnitsPerWeek = SampHasNeverTime;
                                    goto LABEL_503;
                                  }
                                }
                                v164 = ((__int64 (__fastcall *)(_QWORD, _QWORD))SampAddDeltaTime)(
                                         (union _LARGE_INTEGER)v256[1].QuadPart,
                                         (LARGE_INTEGER)v264[0].MinPasswordAge.QuadPart);
                                v162 = BYTE1(v244);
                                *(_QWORD *)&v121[2].UnitsPerWeek = v164;
                              }
                              v163 = v244;
LABEL_503:
                              if ( (v30 & 0x8020000) != 0 )
                              {
                                v165 = SampGetPasswordMustChange(v7, v258[2], v256[1], v264[0].MaxPasswordAge);
                                v162 = BYTE1(v244);
                                v163 = v244;
                                v121[2].LogonHours = (PUCHAR)v165.QuadPart;
                              }
                              if ( (v30 & 0x8000000) != 0 )
                              {
                                SystemTime.QuadPart = 0;
                                updated = NtQuerySystemTime(&SystemTime);
                                if ( updated < 0 )
                                  goto LABEL_118;
                                v162 = BYTE1(v244);
                                v163 = v244;
                                BYTE2(v121[19].LogonHours) = SystemTime.QuadPart >= (__int64)v121[2].LogonHours;
                              }
                              if ( (v30 & 0x40000) != 0 )
                                *(union _LARGE_INTEGER *)&v121[1].UnitsPerWeek = v256[1];
                              if ( (v30 & 0x80000) != 0 )
                                v121[1].LogonHours = (PUCHAR)v257;
                              if ( (v30 & 0x100000) != 0 )
                              {
                                v166 = v258[2];
                                LODWORD(v121[17].LogonHours) = v258[2];
                                if ( v161 == 22 )
                                  LODWORD(v121[17].LogonHours) = v166 & 0xFFFDFFFF;
                              }
                              if ( (v30 & 0x200000) == 0 )
                              {
                                if ( updated < 0 )
                                  goto LABEL_118;
                                goto LABEL_546;
                              }
                              if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                              {
                                if ( *((_QWORD *)v7 + 14) )
                                {
                                  if ( _bittest64(*((const signed __int64 **)v7 + 8), 5u) )
                                  {
                                    v167 = (void *)*((_QWORD *)v7 + 17);
                                    if ( v167 )
                                      LocalFree(v167);
                                    v168 = *((_QWORD *)v7 + 14);
                                    *((_BYTE *)v7 + 20) &= 0xF0u;
                                    *((_QWORD *)v7 + 17) = v168;
                                    *((_QWORD *)v7 + 14) = 0;
                                    *((_QWORD *)v7 + 15) = 0;
                                    *((_DWORD *)v7 + 32) = 0;
                                    updated = SampValidateDsAttributes(v7, 0);
                                    if ( updated >= 0 )
                                    {
                                      updated = SampValidateDsAttributes(v7, 1u);
                                      if ( updated >= 0 )
                                      {
                                        SampMarkPerAttributeInvalidFromWhichFields(v7, 0);
                                        *((_BYTE *)v7 + 29) &= ~1u;
                                      }
                                    }
                                    goto LABEL_528;
                                  }
                                }
                                else
                                {
                                  updated = SampValidateDsAttributes(v7, 0);
                                  if ( updated < 0 )
                                  {
LABEL_528:
                                    v126 = WPP_GLOBAL_Control;
                                    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                                    {
                                      WPP_SF_Dd(
                                        WPP_GLOBAL_Control[3].Buffer,
                                        110,
                                        WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
                                        (unsigned int)updated,
                                        updated);
                                      v126 = WPP_GLOBAL_Control;
                                    }
                                    if ( updated < 0 )
                                      goto LABEL_394;
                                    v170 = 22LL * *((int *)v7 + 4);
                                    if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                                      v171 = (unsigned int)dword_1800EEC4C[v170];
                                    else
                                      v171 = (unsigned int)dword_1800EEC34[v170];
                                    v172 = *(_DWORD *)(*((_QWORD *)v7 + 14) + v171 + 64);
                                    *(&v121[12].UnitsPerWeek + 1) = v172;
                                    v121[12].UnitsPerWeek = v172;
                                    v173 = v172;
                                    v174 = (UCHAR *)LocalAlloc(0x40u, v172);
                                    v121[12].LogonHours = v174;
                                    v175 = v174;
                                    if ( !v174 )
                                    {
                                      *(_DWORD *)&v121[12].UnitsPerWeek = 0;
                                      goto LABEL_402;
                                    }
                                    v176 = *((_QWORD *)v7 + 14);
                                    v177 = 22LL * *((int *)v7 + 4);
                                    if ( (*((_BYTE *)v7 + 192) & 2) != 0 )
                                      v178 = dword_1800EEC48[v177]
                                           + *(_DWORD *)((unsigned int)dword_1800EEC4C[v177] + v176 + 60);
                                    else
                                      v178 = dword_1800EEC38[v177]
                                           + *(_DWORD *)((unsigned int)dword_1800EEC34[v177] + v176 + 60);
                                    memcpy_0(v175, (const void *)(v176 + v178), v173);
                                    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                                      WPP_SF_Dd(
                                        WPP_GLOBAL_Control[3].Buffer,
                                        32,
                                        WPP_ec9974b3367635591c8fff3dd01cd200_Traceguids,
                                        0,
                                        0);
                                    v179 = v121[12].LogonHours;
                                    v163 = v244;
                                    if ( v179 && v9 < 0x40 )
                                    {
                                      v180 = v9++;
                                      hMem[v180] = v179;
                                    }
                                    v162 = BYTE1(v244);
                                    updated = 0;
LABEL_546:
                                    if ( (v30 & 0x400000) != 0 )
                                      *(&v121[19].UnitsPerWeek + 2) = v258[3];
                                    if ( (v30 & 0x800000) != 0 )
                                      *(&v121[19].UnitsPerWeek + 3) = HIWORD(v258[3]);
                                    if ( (v30 & 0x1000000) != 0 )
                                    {
                                      LOBYTE(v121[19].LogonHours) = v163;
                                      BYTE1(v121[19].LogonHours) = v162;
                                      RtlInitUnicodeString((PUNICODE_STRING)&v121[13], 0);
                                      RtlInitUnicodeString((PUNICODE_STRING)&v121[14], 0);
                                      if ( (_BYTE)v244 )
                                      {
                                        v181 = (struct _LM_OWF_PASSWORD *)LocalAlloc(0x40u, 0x10u);
                                        v121[13].LogonHours = (PUCHAR)v181;
                                        v182 = v181;
                                        if ( !v181 )
                                        {
                                          updated = -1073741670;
                                          goto LABEL_118;
                                        }
                                        if ( v9 < 0x40 )
                                        {
                                          v183 = v9++;
                                          hMem[v183] = v182;
                                        }
                                        *(_DWORD *)&v121[13].UnitsPerWeek = 1048592;
                                        *v182 = v262;
                                      }
                                      v25 = 16;
                                      if ( v248 )
                                      {
                                        v184 = (struct _LM_OWF_PASSWORD *)LocalAlloc(0x40u, 0x10u);
                                        v121[14].LogonHours = (PUCHAR)v184;
                                        v185 = v184;
                                        if ( !v184 )
                                        {
                                          updated = -1073741670;
                                          goto LABEL_119;
                                        }
                                        if ( v9 < 0x40 )
                                        {
                                          v186 = v9++;
                                          hMem[v186] = v185;
                                        }
                                        *(_DWORD *)&v121[14].UnitsPerWeek = 1048592;
                                        *v185 = v263;
                                      }
                                      v161 = v246;
                                    }
                                    if ( (v30 & 0x4000000) != 0 )
                                    {
                                      BYTE3(v121[19].LogonHours) = 1;
                                      updated = SampGetPrivateUserData(
                                                  v7,
                                                  v264,
                                                  (unsigned int *)&v121[15].UnitsPerWeek,
                                                  (void **)&v121[15].LogonHours);
                                      if ( updated < 0 )
                                        goto LABEL_118;
                                      v187 = v121[15].LogonHours;
                                      v161 = v246;
                                      *(&v121[15].UnitsPerWeek + 1) = v121[15].UnitsPerWeek;
                                      if ( v187 && v9 < 0x40 )
                                      {
                                        v188 = v9++;
                                        hMem[v188] = v187;
                                      }
                                    }
                                    if ( (v30 & 0x10000000) != 0 )
                                    {
                                      updated = SampGetObjectSD(v7);
                                      if ( updated < 0 )
                                        goto LABEL_118;
                                      if ( (*((_BYTE *)v7 + 192) & 2) == 0
                                        || (*((_BYTE *)v7 + 20) & 0x20) != 0 && (v161 == 21 || v161 == 27) )
                                      {
                                        v192 = v121[16].LogonHours;
                                        if ( v192 && v9 < 0x40 )
                                        {
                                          v193 = v9++;
                                          hMem[v193] = v192;
                                        }
                                      }
                                      else
                                      {
                                        v189 = SampShouldCallNtdsaApiSet();
                                        updated = v189;
                                        if ( v189 == -1073741637 )
                                        {
                                          updated = 0;
                                        }
                                        else
                                        {
                                          if ( v189 >= 0 )
                                            updated = NtdsaExtDowngradeSecurityDescriptor(v7, v121);
                                          if ( updated < 0 )
                                            goto LABEL_118;
                                        }
                                        v190 = v121[16].LogonHours;
                                        if ( v190 && v9 < 0x40 )
                                        {
                                          v191 = v9++;
                                          hMem[v191] = v190;
                                        }
                                      }
                                    }
                                    HIDWORD(v121[17].LogonHours) = v30;
                                    goto LABEL_118;
                                  }
                                }
                                v169 = SampValidateDsAttributes(v7, 1u);
                              }
                              else
                              {
                                v169 = SampValidateRegAttributes(v7, 1u);
                              }
                              updated = v169;
                              goto LABEL_528;
                            }
                          }
                          v141 = SampValidateDsAttributes(v7, 1u);
                        }
                        else
                        {
                          v141 = SampValidateRegAttributes(v7, 1u);
                        }
                        updated = v141;
                        goto LABEL_426;
                      }
                    }
                    v125 = SampValidateDsAttributes(v7, 1u);
                  }
                  else
                  {
                    v125 = SampValidateRegAttributes(v7, 1u);
                  }
                  updated = v125;
                  goto LABEL_391;
                }
LABEL_590:
                LOBYTE(v244) = HIBYTE(v244);
                BYTE1(v244) = BYTE2(v244);
                goto LABEL_118;
              }
            }
          }
LABEL_374:
          if ( updated < 0 )
            goto LABEL_118;
          goto LABEL_375;
        }
        if ( (dword_1800EE478 & 0xFFF000) != 0 )
        {
          Src[0] = dword_1800EE474;
          v265[0] = 0;
        }
        LOBYTE(v39) = (dword_1800EE478 & 0xFFF000) != 0;
        if ( (dword_1800EE484 & 0xFFF000) != 0 )
        {
          v195 = v39++;
          v196 = v195;
          LODWORD(v195) = dword_1800EE480;
          v265[v196] = 1;
          Src[v196] = v195;
        }
        if ( (dword_1800EE490 & 0xFFF000) != 0 )
        {
          v197 = v39++;
          v198 = v197;
          LODWORD(v197) = dword_1800EE48C;
          v265[v198] = 2;
          Src[v198] = v197;
        }
        if ( (dword_1800EE49C & 0xFFF000) != 0 )
        {
          v199 = v39++;
          v200 = v199;
          LODWORD(v199) = dword_1800EE498;
          v265[v200] = 3;
          Src[v200] = v199;
        }
        if ( (dword_1800EE4A8 & 0xFFF000) != 0 )
        {
          v201 = v39++;
          v202 = v201;
          LODWORD(v201) = dword_1800EE4A4;
          v265[v202] = 4;
          Src[v202] = v201;
        }
        if ( (dword_1800EE4B4 & 0xFFF000) != 0 )
        {
          v203 = v39++;
          v204 = v203;
          LODWORD(v203) = dword_1800EE4B0;
          v265[v204] = 5;
          Src[v204] = v203;
        }
        if ( (dword_1800EE4C0 & 0xFFF000) != 0 )
        {
          v205 = v39++;
          v206 = v205;
          LODWORD(v205) = dword_1800EE4BC;
          v265[v206] = 6;
          Src[v206] = v205;
        }
        if ( (dword_1800EE4CC & 0xFFF000) != 0 )
        {
          v207 = v39++;
          v208 = v207;
          LODWORD(v207) = dword_1800EE4C8;
          v265[v208] = 7;
          Src[v208] = v207;
        }
        if ( (dword_1800EE4D8 & 0xFFF000) != 0 )
        {
          v209 = v39++;
          v210 = v209;
          LODWORD(v209) = dword_1800EE4D4;
          v265[v210] = 8;
          Src[v210] = v209;
        }
        if ( (dword_1800EE4E4 & 0xFFF000) != 0 )
        {
          v211 = v39++;
          v212 = v211;
          LODWORD(v211) = dword_1800EE4E0;
          v265[v212] = 9;
          Src[v212] = v211;
        }
        if ( (dword_1800EE4F0 & 0xFFF000) != 0 )
        {
          v213 = v39++;
          v214 = v213;
          LODWORD(v213) = dword_1800EE4EC;
          v265[v214] = 10;
          Src[v214] = v213;
        }
        if ( !v39 )
        {
          updated = 0;
          goto LABEL_666;
        }
        *(_QWORD *)v250 = *a6;
        LODWORD(v215) = v39;
        v216 = 2LL * (*((_DWORD *)v7 + 48) & 2);
        v246 = v39;
        v217 = (__int64 (__fastcall *)(struct _SAMP_OBJECT *, unsigned int *, _QWORD))*(&funcs_180001EF0 + v216);
        memcpy_0(v268, Src, 4LL * v39);
        v218 = v251;
        if ( (*((_BYTE *)v251 + 20) & 0x20) != 0 )
          goto LABEL_618;
        v219 = SampCheckExtendedAttributesForReadAccess(
                 (__int64)v251 + 864,
                 *((_DWORD *)v251 + 4),
                 1,
                 (__int64)v268,
                 &v246);
        v38 = WPP_GLOBAL_Control;
        updated = v219;
        if ( v219 >= 0 )
        {
          LODWORD(v215) = v246;
LABEL_618:
          v220 = *((int *)v218 + 4);
          v221 = 0;
          while ( (unsigned int)v221 < (unsigned int)v215 )
          {
            v222 = &v268[v221];
            if ( (*((_BYTE *)v218 + 24 * (*v222 - dword_1800BD00C[4 * v220]) + 864) & 1) != 0 )
            {
              v215 = (unsigned int)(v215 - 1);
              v221 = (unsigned int)v221;
              *v222 = v268[v215];
            }
            else
            {
              v223 = *(_DWORD *)(*((_QWORD *)&SampObjectExtendedAttributesProperties + 2 * *((int *)v218 + 4))
                               + 32LL * (v268[v221] - dword_1800BD00C[4 * v220])
                               + 4)
                   & (((*((_BYTE *)v218 + 192) & 2) != 0) + 1);
              if ( (*(_DWORD *)(&v38[4].MaximumLength + 1) & 0x20000) != 0 )
              {
                WPP_SF_d(v38[3].Buffer, 40, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v223 != 0);
                v38 = WPP_GLOBAL_Control;
              }
              if ( !v223 )
              {
                updated = -1073741149;
                if ( (*(_DWORD *)(&v38[4].MaximumLength + 1) & 0x20000) != 0 )
                {
                  WPP_SF_Dd(
                    v38[3].Buffer,
                    82,
                    WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
                    3221226147LL,
                    -1073741149);
                  v38 = WPP_GLOBAL_Control;
                }
                v6 = (union _LARGE_INTEGER **)SystemTime.QuadPart;
                v218 = v251;
                goto LABEL_635;
              }
              v218 = v251;
              v221 = (unsigned int)(v221 + 1);
            }
          }
          if ( (*(_DWORD *)(&v38[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_Dd(v38[3].Buffer, 83, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 0, 0);
            v38 = WPP_GLOBAL_Control;
          }
          if ( (_DWORD)v215 )
          {
            v224 = v217(v218, v268, (unsigned int)v215);
            v38 = WPP_GLOBAL_Control;
            updated = v224;
          }
          else
          {
            updated = 0;
          }
          v6 = (union _LARGE_INTEGER **)SystemTime.QuadPart;
        }
LABEL_635:
        if ( (*(_BYTE *)(&v38[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v38[4].Length) >= 5u )
        {
          WPP_SF_Dd(v38[3].Buffer, 86, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v39, updated);
          v38 = WPP_GLOBAL_Control;
        }
        if ( (*(_DWORD *)(&v38[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          WPP_SF_Dd(v38[3].Buffer, 87, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, (unsigned int)updated, updated);
          v38 = WPP_GLOBAL_Control;
        }
        if ( updated >= 0 )
        {
          for ( i = 0; (unsigned int)i < v39; i = (unsigned int)(i + 1) )
          {
            v226 = (unsigned int)v265[i];
            v227 = 0;
            v228 = 4LL * *((int *)v218 + 4);
            v229 = *((unsigned int *)&UserExtendedAttributesInformation + 3 * v226);
            v230 = (unsigned int)(Src[i] - dword_1800BD00C[v228]) + 36LL;
            v231 = (int *)(*(char **)((char *)&SampObjectExtendedAttributesProperties + v228 * 4)
                         + 32 * (unsigned int)(Src[i] - dword_1800BD00C[v228]));
            v254 = v231;
            v232 = (char *)v218 + 24 * v230;
            if ( (*((_BYTE *)v251 + 20) & 0x20) != 0 )
            {
              v227 = *v232 >> 2;
              *v232 |= 4u;
              v38 = WPP_GLOBAL_Control;
            }
            if ( (*v232 & 4) != 0 )
            {
              v233 = ((__int64 (__fastcall *)(_BYTE *, __int64))qword_1800BD430[2 * *v231])(
                       v232 + 8,
                       *(_QWORD *)v250 + v229);
              updated = v233;
              v38 = WPP_GLOBAL_Control;
              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
              {
                WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 66, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v233, v233);
                v38 = WPP_GLOBAL_Control;
              }
              LODWORD(v231) = (_DWORD)v254;
            }
            else
            {
              if ( (*(_DWORD *)(&v38[4].MaximumLength + 1) & 0x20000) != 0 )
              {
                WPP_SF_Dd(v38[3].Buffer, 65, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 3221225506LL, -1073741790);
                LODWORD(v231) = (_DWORD)v254;
                v38 = WPP_GLOBAL_Control;
              }
              updated = -1073741790;
            }
            if ( (*((_BYTE *)v251 + 20) & 0x20) != 0 )
            {
              *v232 ^= (*v232 ^ (4 * v227)) & 4;
              v38 = WPP_GLOBAL_Control;
            }
            if ( (*(_BYTE *)(&v38[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v38[4].Length) >= 4u )
            {
              WPP_SF_ZD(
                v38[3].Buffer,
                67,
                (unsigned int)WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
                (_DWORD)v231 + 8,
                updated);
              v38 = WPP_GLOBAL_Control;
            }
            if ( (*(_DWORD *)(&v38[4].MaximumLength + 1) & 0x20000) != 0 )
            {
              WPP_SF_Dd(
                v38[3].Buffer,
                68,
                WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
                (unsigned int)updated,
                updated);
              v38 = WPP_GLOBAL_Control;
            }
            if ( updated >= 0 )
            {
              **(_DWORD **)v250 |= *((_DWORD *)&UserExtendedAttributesInformation + 3 * v226 + 2);
              v38 = WPP_GLOBAL_Control;
            }
            else
            {
              if ( updated != -1073741790 )
                break;
              updated = 0;
            }
            v218 = v251;
          }
          v6 = (union _LARGE_INTEGER **)SystemTime.QuadPart;
        }
        v7 = v251;
LABEL_666:
        if ( (*(_DWORD *)(&v38[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(v38[3].Buffer, 202, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)updated, updated);
        if ( updated >= 0 )
        {
          v234 = *v6;
          v235 = (void *)(*v6)[2].QuadPart;
          if ( v235 )
          {
            v9 = v243;
            if ( v243 < 0x40 )
            {
              hMem[v243] = v235;
              ++v9;
            }
          }
          else
          {
            v9 = v243;
          }
          v236 = (void *)v234[7].QuadPart;
          if ( v236 && v9 < 0x40 )
          {
            v237 = v9++;
            hMem[v237] = v236;
          }
          v238 = (void *)v234[17].QuadPart;
          if ( v238 && v9 < 0x40 )
          {
            v239 = v9++;
            hMem[v239] = v238;
          }
          v240 = (void *)v234[19].QuadPart;
          if ( v240 )
          {
            v25 = 16;
            if ( v9 >= 0x40 )
              goto LABEL_119;
            hMem[v9] = v240;
            goto LABEL_170;
          }
          goto LABEL_118;
        }
LABEL_117:
        v9 = v243;
        goto LABEL_118;
      default:
        goto LABEL_77;
    }
  }
LABEL_120:
  if ( !v249 )
    SampMaybeReleaseReadLock(v16);
  if ( updated < 0 )
  {
    if ( (_BYTE)v244 )
    {
      v43 = 16;
      v44 = &v262;
      do
      {
        v44->data[0].data[0] = 0;
        v44 = (struct _LM_OWF_PASSWORD *)((char *)v44 + 1);
        --v43;
      }
      while ( v43 );
    }
    if ( BYTE1(v244) )
    {
      v45 = &v263;
      do
      {
        v45->data[0].data[0] = 0;
        v45 = (struct _LM_OWF_PASSWORD *)((char *)v45 + 1);
        --v25;
      }
      while ( v25 );
    }
    for ( j = 0; (unsigned int)j < v9; j = (unsigned int)(j + 1) )
      LocalFree(hMem[j]);
    *v6 = 0;
  }
LABEL_683:
  SampTraceEvent(2);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      27,
      WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
      (unsigned int)updated,
      updated);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000b150  mov     r11, rsp
0x18000b153  push    rbp
0x18000b154  push    rbx
0x18000b155  lea     rbp, [r11-418h]
0x18000b15c  sub     rsp, 508h
0x18000b163  mov     rax, cs:__security_cookie
0x18000b16a  xor     rax, rsp
0x18000b16d  mov     [rbp+410h+var_30], rax
0x18000b174  xorps   xmm0, xmm0
0x18000b177  mov     [r11+10h], rsi
0x18000b17b  xor     al, al
0x18000b17d  mov     [r11+18h], rdi
0x18000b181  mov     [r11+20h], r12
0x18000b185  xorps   xmm1, xmm1
0x18000b188  mov     r12, [rbp+410h+arg_28]
0x18000b18f  mov     [r11-18h], r13
0x18000b193  mov     r13, rcx
0x18000b196  mov     [r11-20h], r14
0x18000b19a  mov     [r11-28h], r15
0x18000b19e  mov     r15d, edx
0x18000b1a1  mov     byte ptr [rsp+510h+var_4B0+2], r8b
0x18000b1a6  mov     r8d, 200h; Size
0x18000b1ac  mov     [rsp+510h+var_4B4], edx
0x18000b1b0  xor     edx, edx; Val
0x18000b1b2  mov     [rsp+510h+var_4A0], rcx
0x18000b1b7  lea     rcx, [rbp+410h+hMem]; void *
0x18000b1be  mov     dword ptr [rbp+410h+var_488], r9d
0x18000b1c2  mov     qword ptr [rsp+510h+SystemTime], r12
0x18000b1c7  mov     [rbp+410h+var_490], 0
0x18000b1ce  movups  [rbp+410h+var_480], xmm0
0x18000b1d2  mov     byte ptr [rsp+510h+var_4BC+1], al
0x18000b1d6  movups  xmmword ptr [rbp+410h+var_470], xmm0
0x18000b1da  mov     byte ptr [rsp+510h+var_4BC+2], al
0x18000b1de  movups  [rbp+410h+var_460], xmm0
0x18000b1e2  mov     byte ptr [rsp+510h+var_4BC], al
0x18000b1e6  movups  xmmword ptr [rbp+410h+var_450], xmm0
0x18000b1ea  mov     byte ptr [rsp+510h+var_4BC+3], al
0x18000b1ee  movups  [rbp+410h+var_440], xmm0
0x18000b1f2  mov     byte ptr [rsp+510h+var_4B0+1], al
0x18000b1f6  movdqu  [rbp+410h+var_410], xmm0
0x18000b1fb  mov     byte ptr [rsp+510h+var_4BC+4], al
0x18000b1ff  movdqu  [rbp+410h+var_400], xmm1
0x18000b204  call    memset_0
0x18000b209  xorps   xmm0, xmm0
0x18000b20c  xor     r14d, r14d
0x18000b20f  xor     eax, eax
0x18000b211  mov     [rsp+510h+var_4C0], r14d
0x18000b216  movups  xmmword ptr [rbp+410h+var_3F0.MinPasswordAge+2], xmm0
0x18000b21a  xor     r8d, r8d
0x18000b21d  mov     [rsp+510h+var_4A8], r14d
0x18000b222  mov     edx, 25h ; '%'
0x18000b227  mov     [rbp+410h+var_3F0.MinPasswordLength], ax
0x18000b22b  mov     ecx, 1
0x18000b230  movups  xmmword ptr [rbp+40h], xmm0
0x18000b234  movups  xmmword ptr [rbp+410h+var_3F0.PasswordHistoryLength], xmm0
0x18000b238  call    SampTraceEvent
0x18000b23d  test    r12, r12
0x18000b240  jz      loc_18000DFD9
0x18000b246  cmp     [r12], r14
0x18000b24a  jnz     loc_18000DFD9
0x18000b250  lea     rdx, __ImageBase
0x18000b257  cmp     r15d, 1Bh
0x18000b25b  jz      loc_18000B2F3; jumptable 000000018000B288 cases 21,22
0x18000b261  cmp     r15d, 5
0x18000b265  jz      loc_18000B2EC; jumptable 000000018000B288 case 3
0x18000b26b  lea     eax, [r15-1]; switch 34 cases
0x18000b26f  cmp     eax, 21h
0x18000b272  ja      short def_18000B288; jumptable 000000018000B288 default case, cases 5,15,23-27,31,32
0x18000b274  cdqe
0x18000b276  movzx   eax, ds:(byte_18000E098 - 180000000h)[rdx+rax]
0x18000b27e  mov     ecx, ds:(jpt_18000B288 - 180000000h)[rdx+rax*4]
0x18000b285  add     rcx, rdx
0x18000b288  jmp     rcx; switch jump
0x18000b28a  mov     r8d, [rbp+410h+arg_20]; jumptable 000000018000B288 case 28
0x18000b291  xor     edx, edx; unsigned __int8
0x18000b293  mov     rcx, r13; struct _SAMP_OBJECT *
0x18000b296  call    ?SampCheckAccessToExtendedInformation@@YAJPEAU_SAMP_OBJECT@@EK@Z; SampCheckAccessToExtendedInformation(_SAMP_OBJECT *,uchar,ulong)
0x18000b29b  mov     ebx, eax
0x18000b29d  test    eax, eax
0x18000b29f  js      loc_18000DFDE
0x18000b2a5  xor     esi, esi; jumptable 000000018000B288 cases 18,19
0x18000b2a7  jmp     short loc_18000B2FB
0x18000b2a9  mov     esi, 80h; jumptable 000000018000B288 case 30
0x18000b2ae  jmp     short loc_18000B2FB
0x18000b2b0  mov     rcx, r13; jumptable 000000018000B288 case 29
0x18000b2b3  call    ?SampCheckAccessToLogonUIInformation@@YAJPEAU_SAMP_OBJECT@@@Z; SampCheckAccessToLogonUIInformation(_SAMP_OBJECT *)
0x18000b2b8  mov     ebx, eax
0x18000b2ba  test    eax, eax
0x18000b2bc  js      loc_18000DFDE
0x18000b2c2  xor     esi, esi
0x18000b2c4  jmp     short loc_18000B2FB
0x18000b2c6  mov     esi, 1; jumptable 000000018000B288 cases 1,6-9,13
0x18000b2cb  jmp     short loc_18000B2FB
0x18000b2cd  mov     esi, 3; jumptable 000000018000B288 case 2
0x18000b2d2  jmp     short loc_18000B2FB
0x18000b2d4  mov     esi, 8; jumptable 000000018000B288 cases 4,10-12,14
0x18000b2d9  jmp     short loc_18000B2FB
0x18000b2db  mov     esi, 10h; jumptable 000000018000B288 cases 16,17,20,33,34
0x18000b2e0  jmp     short loc_18000B2FB
0x18000b2e2  mov     ebx, 0C0000003h; jumptable 000000018000B288 default case, cases 5,15,23-27,31,32
0x18000b2e7  jmp     loc_18000DFDE
0x18000b2ec  mov     esi, 1Bh; jumptable 000000018000B288 case 3
0x18000b2f1  jmp     short loc_18000B2FB
0x18000b2f3  xor     esi, esi; jumptable 000000018000B288 cases 21,22
0x18000b2f5  cmp     r15d, 1Bh
0x18000b2f9  jz      short loc_18000B33E
0x18000b2fb  mov     ebx, 350h
0x18000b300  mov     ecx, 40h ; '@'; uFlags
0x18000b305  mov     edx, ebx; uBytes
0x18000b307  call    cs:__imp_LocalAlloc
0x18000b30d  mov     [r12], rax
0x18000b311  test    rax, rax
0x18000b314  jz      short loc_18000B37C
0x18000b316  mov     r14d, 1
0x18000b31c  mov     [rbp+410h+hMem], rax
0x18000b323  mov     [rsp+510h+var_4C0], r14d
0x18000b328  mov     [rsp+510h+var_4A8], r14d
0x18000b32d  nop     dword ptr [rax]
0x18000b330  mov     byte ptr [rax], 0
0x18000b333  lea     rax, [rax+1]
0x18000b337  sub     rbx, r14
0x18000b33a  jnz     short loc_18000B330
0x18000b33c  jmp     short loc_18000B37C
0x18000b33e  mov     ebx, 300h
0x18000b343  mov     ecx, 40h ; '@'; uFlags
0x18000b348  mov     edx, ebx; uBytes
0x18000b34a  call    cs:__imp_LocalAlloc
0x18000b350  mov     [r12], rax
0x18000b354  test    rax, rax
0x18000b357  jz      short loc_18000B37C
0x18000b359  mov     r14d, 1
0x18000b35f  mov     [rbp+410h+hMem], rax
0x18000b366  mov     [rsp+510h+var_4C0], r14d
0x18000b36b  mov     [rsp+510h+var_4A8], r14d
0x18000b370  mov     [rax], sil
0x18000b373  lea     rax, [rax+1]
0x18000b377  sub     rbx, r14
0x18000b37a  jnz     short loc_18000B370
0x18000b37c  cmp     qword ptr [r12], 0
0x18000b381  jnz     short loc_18000B38D
0x18000b383  mov     ebx, 0C000009Ah
0x18000b388  jmp     loc_18000DFDE
0x18000b38d  xor     dil, dil
0x18000b390  mov     byte ptr [rsp+510h+var_4B0], dil
0x18000b395  cmp     byte ptr [rsp+510h+var_4B0+2], dil
0x18000b39a  jnz     loc_18000B4B2
0x18000b3a0  test    r13, r13
0x18000b3a3  jz      short loc_18000B3D5
0x18000b3a5  mov     rcx, r13; struct _SAMP_OBJECT *
0x18000b3a8  mov     byte ptr [rsp+510h+var_4B0], dil
0x18000b3ad  call    ?SampValidateContext@@YAJPEAU_SAMP_OBJECT@@@Z; SampValidateContext(_SAMP_OBJECT *)
0x18000b3b2  test    eax, eax
0x18000b3b4  js      loc_18000B4B2
0x18000b3ba  test    byte ptr [r13+0C0h], 2
0x18000b3c2  jz      short loc_18000B3D5
0x18000b3c4  test    byte ptr [r13+1Ch], 1
0x18000b3c9  jz      short loc_18000B3D5
0x18000b3cb  call    SampIncrementActiveThreads
0x18000b3d0  jmp     loc_18000B4B2
0x18000b3d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3dc  test    dword ptr [rcx+44h], 20000h
0x18000b3e3  jz      short loc_18000B402
0x18000b3e5  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x18000b3ed  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18000b3f4  mov     rcx, [rcx+38h]
0x18000b3f8  mov     edx, 49h ; 'I'
0x18000b3fd  call    WPP_SF_d
0x18000b402  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x18000b409  jz      short loc_18000B418
0x18000b40b  call    ?SampExtIsWriteLockHeldByDs@@YAHXZ; SampExtIsWriteLockHeldByDs(void)
0x18000b410  test    eax, eax
0x18000b412  jnz     loc_18000B4AA
0x18000b418  call    cs:__imp_GetTickCount
0x18000b41e  mov     ebx, eax
0x18000b420  lock inc cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x18000b427  lea     rcx, ?SampLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000b42e  call    cs:__imp_RtlEnterCriticalSection
0x18000b434  lock dec cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x18000b43b  call    cs:__imp_GetTickCount
0x18000b441  mov     ecx, cs:?SamLockTotalAquisitions@@3KA; ulong SamLockTotalAquisitions
0x18000b447  inc     ecx
0x18000b449  mov     cs:?SamLockCurrentHoldStartTime@@3KA, eax; ulong SamLockCurrentHoldStartTime
0x18000b44f  mov     cs:?SamLockTotalAquisitions@@3KA, ecx; ulong SamLockTotalAquisitions
0x18000b455  sub     eax, ebx
0x18000b457  jz      short loc_18000B463
0x18000b459  test    ecx, ecx
0x18000b45b  jz      short loc_18000B463
0x18000b45d  add     cs:?SamCumulativeWaitTime@@3KA, eax; ulong SamCumulativeWaitTime
0x18000b463  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b46a  test    dword ptr [rcx+44h], 20000h
0x18000b471  jz      short loc_18000B490
0x18000b473  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x18000b47b  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18000b482  mov     rcx, [rcx+38h]
0x18000b486  mov     edx, 49h ; 'I'
0x18000b48b  call    WPP_SF_d
0x18000b490  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x18000b497  jz      short loc_18000B4AA
0x18000b499  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18000b49e  test    eax, eax
0x18000b4a0  js      short loc_18000B4AA
0x18000b4a2  xor     ecx, ecx
0x18000b4a4  call    cs:__imp_NtdsaExtSetGlobalTransactionType
0x18000b4aa  mov     dil, 1
0x18000b4ad  mov     byte ptr [rsp+510h+var_4B0], dil
0x18000b4b2  lea     rax, [rbp+410h+var_490]
0x18000b4b6  mov     r9d, 4
0x18000b4bc  xor     r8d, r8d
0x18000b4bf  mov     qword ptr [rsp+510h+var_4F0], rax
0x18000b4c4  mov     edx, esi
0x18000b4c6  mov     rcx, r13
0x18000b4c9  call    ?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z; SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)
0x18000b4ce  mov     ebx, eax
0x18000b4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4d7  mov     esi, 10h
0x18000b4dc  test    dword ptr [rcx+44h], 20000h
0x18000b4e3  jz      short loc_18000B505
0x18000b4e5  mov     rcx, [rcx+38h]
0x18000b4e9  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x18000b4f0  mov     edx, esi
0x18000b4f2  mov     [rsp+510h+var_4F0], eax
0x18000b4f6  mov     r9d, eax
0x18000b4f9  call    WPP_SF_Dd
0x18000b4fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b505  cmp     ebx, 0C0000022h
0x18000b50b  jnz     short loc_18000B550
0x18000b50d  cmp     r15d, 14h
0x18000b511  jnz     loc_18000B950
0x18000b517  test    byte ptr [r13+0C0h], 2
0x18000b51f  jz      loc_18000B950
0x18000b525  cmp     byte ptr [r13+147h], 0
0x18000b52d  jz      loc_18000B950
0x18000b533  lea     r9, [rbp+410h+var_490]
0x18000b537  xor     edx, edx
0x18000b539  mov     r8d, 4
0x18000b53f  mov     rcx, r13
0x18000b542  call    SampLookupContext
0x18000b547  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b54e  mov     ebx, eax
0x18000b550  test    ebx, ebx
0x18000b552  js      loc_18000B950
0x18000b558  test    byte ptr [r13+0C0h], 2
0x18000b560  jnz     loc_18000B634
0x18000b566  cmp     cs:?gfLapsExtInitialized@@3HA, 0; int gfLapsExtInitialized
0x18000b56d  jnz     short loc_18000B59D
0x18000b56f  test    byte ptr [rcx+44h], 1
0x18000b573  jz      short loc_18000B597
0x18000b575  cmp     byte ptr [rcx+41h], 4
0x18000b579  jb      short loc_18000B597
0x18000b57b  mov     rcx, [rcx+38h]
0x18000b57f  lea     r8, WPP_98e4cdad5db13c057b28971bf7933a81_Traceguids
0x18000b586  mov     edx, 36h ; '6'
0x18000b58b  call    WPP_SF_
0x18000b590  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b597  xor     edi, edi
0x18000b599  mov     ebx, edi
0x18000b59b  jmp     short loc_18000B60A
0x18000b59d  test    byte ptr [rcx+44h], 1
0x18000b5a1  mov     ebx, [r13+0F8h]
0x18000b5a8  jz      short loc_18000B5CC
0x18000b5aa  cmp     byte ptr [rcx+41h], 4
0x18000b5ae  jb      short loc_18000B5CC
0x18000b5b0  mov     rcx, [rcx+38h]
0x18000b5b4  lea     r8, WPP_98e4cdad5db13c057b28971bf7933a81_Traceguids
0x18000b5bb  mov     edx, 37h ; '7'
0x18000b5c0  mov     [rsp+510h+var_4F0], ebx
0x18000b5c4  mov     r9d, ebx
0x18000b5c7  call    WPP_SF_Dd
0x18000b5cc  mov     ecx, ebx
0x18000b5ce  call    cs:__imp_LAPSExtIsLocalAccountManaged
0x18000b5d4  mov     ebx, eax
0x18000b5d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5dd  test    byte ptr [rcx+44h], 1
0x18000b5e1  jz      short loc_18000B608
0x18000b5e3  cmp     byte ptr [rcx+41h], 4
0x18000b5e7  jb      short loc_18000B608
0x18000b5e9  mov     rcx, [rcx+38h]
0x18000b5ed  lea     r8, WPP_98e4cdad5db13c057b28971bf7933a81_Traceguids
0x18000b5f4  mov     edx, 38h ; '8'
0x18000b5f9  mov     r9d, eax
0x18000b5fc  call    WPP_SF_d
0x18000b601  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b608  xor     edi, edi
0x18000b60a  test    dword ptr [rcx+44h], 20000h
0x18000b611  jz      short loc_18000B62B
0x18000b613  mov     rcx, [rcx+38h]
0x18000b617  lea     r8, WPP_98e4cdad5db13c057b28971bf7933a81_Traceguids
0x18000b61e  mov     edx, 39h ; '9'
0x18000b623  mov     r9d, ebx
0x18000b626  call    WPP_SF_d
0x18000b62b  mov     [r13+350h], ebx
0x18000b632  jmp     short loc_18000B636
0x18000b634  xor     edi, edi
0x18000b636  mov     r14d, [rsp+510h+var_4B4]
0x18000b63b  mov     r15d, edi
0x18000b63e  dec     r14d; switch 29 cases
0x18000b641  cmp     r14d, 1Ch
0x18000b645  ja      short def_18000B663; jumptable 000000018000B663 default case, cases 4,6-8,10-15,18,20,23-26,28
0x18000b647  lea     rdx, __ImageBase
0x18000b64e  movsxd  rax, r14d
  ... truncated ...
```
