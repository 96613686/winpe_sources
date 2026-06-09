# RIMRegisterForInputWithCallbacks

- ea: `0x140162810`
- end: `0x140163860`
- name: `RIMRegisterForInputWithCallbacks`
- size: `4176`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x1401627a0`
- `0x1401b3304`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x140065730`
- `0x1400729c8`
- `0x140072a90`
- `0x1400775c0`
- `0x1400951c0`
- `0x140096d00`
- `0x1400b1d40`
- `0x1400e0370`
- `0x140117e20`
- `0x140162810`
- `0x140163870`
- `0x140165268`
- `0x14016c4a0`
- `0x1401721a0`
- `0x1401744dc`
- `0x14017a458`
- `0x1401a9f9c`
- `0x1401aa51c`
- `0x1401b3a54`
- `0x1401b5398`
- `0x1401bf8f0`
- `0x1401c6028`
- `0x1401ff110`
- `0x1402026ec`
- `0x140238160`
- `0x1402bb164`
- `0x1402bb1a0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14016338a`
- `ntoskrnl!ProbeForRead` at `0x14016338a`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14016345a`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14016345a`
- `ntoskrnl!ZwClose` at `0x140163753`
- `ntoskrnl!ZwClose` at `0x14016376c`
- `ntoskrnl!ZwClose` at `0x140163785`
- `ntoskrnl!ZwClose` at `0x140163753`
- `ntoskrnl!ZwClose` at `0x14016376c`
- `ntoskrnl!ZwClose` at `0x140163785`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140162e02`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140162e02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140162e2a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140162e2a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401633fc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401633fc`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14016310a`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14016310a`
- `ntoskrnl!ObCloseHandle` at `0x1401637a1`
- `ntoskrnl!ObCloseHandle` at `0x1401637a1`
- `ntoskrnl!ObfDereferenceObject` at `0x1401635ea`
- `ntoskrnl!ObfDereferenceObject` at `0x1401635ea`
- `WIN32K!W32GetUserSessionState` at `0x14016291b`
- `WIN32K!W32GetUserSessionState` at `0x1401629c0`
- `WIN32K!W32GetUserSessionState` at `0x140162a54`
- `WIN32K!W32GetUserSessionState` at `0x140162ac9`
- `WIN32K!W32GetUserSessionState` at `0x140162b44`
- `WIN32K!W32GetUserSessionState` at `0x140162bca`
- `WIN32K!W32GetUserSessionState` at `0x140162c5f`
- `WIN32K!W32GetUserSessionState` at `0x140163244`
- `WIN32K!W32GetUserSessionState` at `0x1401634a8`
- `WIN32K!W32GetUserSessionState` at `0x1401637f6`
- `WIN32K!W32GetUserSessionState` at `0x14016291b`
- `WIN32K!W32GetUserSessionState` at `0x1401629c0`
- `WIN32K!W32GetUserSessionState` at `0x140162a54`
- `WIN32K!W32GetUserSessionState` at `0x140162ac9`
- `WIN32K!W32GetUserSessionState` at `0x140162b44`
- `WIN32K!W32GetUserSessionState` at `0x140162bca`
- `WIN32K!W32GetUserSessionState` at `0x140162c5f`
- `WIN32K!W32GetUserSessionState` at `0x140163244`
- `WIN32K!W32GetUserSessionState` at `0x1401634a8`
- `WIN32K!W32GetUserSessionState` at `0x1401637f6`

## pseudocode

```c
__int64 __fastcall RIMRegisterForInputWithCallbacks(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        int a12,
        HANDLE *a13)
{
  int v13; // r15d
  bool v15; // r12
  __int64 UserSessionState; // rax
  int v17; // r8d
  int v18; // edx
  bool v19; // r15
  __int64 v20; // rax
  int v21; // r8d
  int v22; // edx
  char v23; // bl
  bool v24; // si
  __int64 v25; // rax
  int v26; // edx
  int v27; // r8d
  char v28; // r12
  bool v29; // r13
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  bool v33; // r13
  __int64 v34; // rax
  int v35; // r8d
  int v36; // edx
  int v38; // eax
  void *KernelSemaphore; // rsi
  __int64 v40; // r15
  void *v41; // rcx
  unsigned int i; // edx
  void *v43; // rax
  __int64 j; // rbx
  PVOID v45; // rcx
  int v46; // r15d
  int v47; // ecx
  __int64 v48; // r8
  bool v49; // sf
  int v50; // edx
  int v51; // r8d
  int v52; // r9d
  char *v53; // rsi
  unsigned int v54; // edx
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rdx
  void *v59; // rax
  int v60; // ecx
  unsigned int v61; // r8d
  __int64 v62; // r9
  unsigned int k; // ebx
  __int64 v64; // rax
  int ULongFromUser; // ebx
  void *v66; // rcx
  void *v67; // rbx
  __int64 n; // r13
  __int64 m; // r12
  PVOID v70; // rcx
  char v71; // bl
  bool v72; // r12
  __int64 v73; // rax
  int v74; // r8d
  int v75; // edx
  int TableContext; // [rsp+20h] [rbp-158h]
  int v77; // [rsp+28h] [rbp-150h]
  int v78; // [rsp+30h] [rbp-148h]
  __int16 v79; // [rsp+30h] [rbp-148h]
  int v80; // [rsp+38h] [rbp-140h]
  bool v81; // [rsp+60h] [rbp-118h]
  bool v82; // [rsp+60h] [rbp-118h]
  bool v83; // [rsp+60h] [rbp-118h]
  int v84; // [rsp+68h] [rbp-110h]
  unsigned int v85; // [rsp+70h] [rbp-108h]
  unsigned int v86; // [rsp+74h] [rbp-104h]
  __int64 v87; // [rsp+78h] [rbp-100h]
  bool v88; // [rsp+80h] [rbp-F8h]
  HANDLE v89; // [rsp+88h] [rbp-F0h] BYREF
  PVOID Object; // [rsp+90h] [rbp-E8h] BYREF
  UNICODE_STRING SourceString; // [rsp+98h] [rbp-E0h] BYREF
  void *v92; // [rsp+A8h] [rbp-D0h]
  HANDLE *v93; // [rsp+B0h] [rbp-C8h]
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-C0h] BYREF
  unsigned int v95; // [rsp+C8h] [rbp-B0h]
  int v96; // [rsp+CCh] [rbp-ACh]
  HANDLE Handle; // [rsp+D0h] [rbp-A8h] BYREF
  HANDLE v98; // [rsp+D8h] [rbp-A0h] BYREF
  HANDLE v99; // [rsp+E0h] [rbp-98h] BYREF
  __int64 v100; // [rsp+E8h] [rbp-90h]
  __int64 v101; // [rsp+F0h] [rbp-88h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+F8h] [rbp-80h]
  __int128 v103; // [rsp+100h] [rbp-78h]
  __int64 v104; // [rsp+110h] [rbp-68h]
  PVOID Buffer[3]; // [rsp+118h] [rbp-60h] BYREF

  v100 = a4;
  v13 = a3;
  v85 = a3;
  v87 = a2;
  v101 = a2;
  *(_QWORD *)&SourceString.Length = a4;
  v104 = a7;
  *(_QWORD *)&v103 = a8;
  v93 = a13;
  Handle = (HANDLE)-1LL;
  v98 = (HANDLE)-1LL;
  v99 = (HANDLE)-1LL;
  v89 = (HANDLE)-1LL;
  memset(Buffer, 0, sizeof(Buffer));
  v15 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v81 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, a2, a3);
    LOBYTE(v17) = v81;
    LOBYTE(v18) = v15;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v18,
      v17,
      *(_QWORD *)(UserSessionState + 19408),
      4,
      1,
      11,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    a2 = v87;
  }
  if ( (a1 & 0xFFFFFFC0) != 0 )
  {
    v19 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u;
    v82 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control, a3);
      LOBYTE(v21) = v82;
      LOBYTE(v22) = v19;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v22,
        v21,
        *(_QWORD *)(v20 + 19408),
        2,
        1,
        12,
        (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
        a1);
    }
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v23 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v23 = 0;
    }
    v24 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v23 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 3221225485LL;
    v25 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control, a3);
    v79 = 13;
LABEL_60:
    LOBYTE(v27) = v24;
    LOBYTE(v26) = v23;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v26,
      v27,
      *(_QWORD *)(v25 + 19408),
      4,
      1,
      v79,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    return 3221225485LL;
  }
  if ( a2 && (!a1 || ((a1 - 1) & a1) != 0 || v13) )
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v28 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u) )
    {
      v28 = 0;
    }
    v29 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v30 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control, a3);
      LOBYTE(v31) = v29;
      LOBYTE(v32) = v28;
      WPP_RECORDER_AND_TRACE_SF_qDd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v32,
        v31,
        *(_QWORD *)(v30 + 19408),
        TableContext,
        v77,
        v78,
        v80,
        v87,
        a1,
        v13);
    }
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v23 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v23 = 0;
    }
    v24 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v23 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return 3221225485LL;
    v25 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control, a3);
    v79 = 15;
    goto LABEL_60;
  }
  v88 = 0;
  if ( v13 )
  {
    if ( (a1 & 0x20) == 0 )
    {
      v33 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u;
      v83 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v34 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control, a3);
        LOBYTE(v35) = v83;
        LOBYTE(v36) = v33;
        WPP_RECORDER_AND_TRACE_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v36,
          v35,
          *(_QWORD *)(v34 + 19408),
          2,
          1,
          16,
          (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
          a1,
          v13);
      }
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v23 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
      {
        v23 = 0;
      }
      v24 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v23 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 3221225485LL;
      v25 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control, a3);
      v79 = 17;
      goto LABEL_60;
    }
    if ( a12 )
    {
      v38 = rimCheckForRegistrationConflicts(a1);
      if ( v38 == 1 )
        return 3221225506LL;
      v88 = v38 == 0;
    }
  }
  KernelSemaphore = (void *)CreateKernelSemaphore(0, -1);
  *(_QWORD *)&DestinationString.Length = KernelSemaphore;
  if ( !KernelSemaphore )
    return 3221225495LL;
  v40 = CreateKernelSemaphore(0, 0x7FFFFFFF);
  v92 = (void *)v40;
  if ( !v40 )
  {
    v41 = KernelSemaphore;
LABEL_70:
    GreDeleteFastMutex(v41);
    return 3221225495LL;
  }
  for ( i = 0; ; i = v86 + 1 )
  {
    v86 = i;
    if ( i > 2 )
      break;
    v43 = Win32AllocPoolZInitImpl(0x40u, 0x68u, 0x63704152u);
    Buffer[v86] = v43;
    if ( !v43 )
    {
      for ( j = 0; j != 3; ++j )
      {
        v45 = Buffer[j];
        if ( v45 )
          GreDeleteFastMutex(v45);
      }
      GreDeleteFastMutex(KernelSemaphore);
      v41 = (void *)v40;
      goto LABEL_70;
    }
  }
  LODWORD(Object) = a12 != 0;
  v46 = rimConvertUserToKernelEventHandle(a6, &Handle);
  v84 = rimConvertUserToKernelTimerHandle(v104, &v98);
  v47 = rimConvertUserToKernelSemaphoreHandle(v103, &v99);
  v49 = v46 < 0;
  if ( v46 < 0 )
    goto LABEL_131;
  if ( v84 < 0 || v47 < 0 )
  {
    v49 = v46 < 0;
LABEL_131:
    if ( !v49 )
      v46 = v84;
    goto LABEL_133;
  }
  KeEnterCriticalRegion();
  v46 = RawInputManagerObjectCreate((int)Object, v50, v51, v52, &v89);
  KeLeaveCriticalRegion();
  if ( v46 >= 0 )
  {
    Object = 0;
    v46 = RawInputManagerObjectResolveHandle(v89, 3, 1, &Object);
    if ( v46 >= 0 )
    {
      v53 = (char *)Object;
      *((_QWORD *)Object + 8) = v89;
      *((_WORD *)v53 + 36) = 0;
      v53[74] = 0;
      *((_DWORD *)v53 + 19) = a1;
      *((_QWORD *)v53 + 14) = a5;
      *((_QWORD *)v53 + 12) = 0;
      *((_QWORD *)v53 + 13) = 0;
      *((_QWORD *)v53 + 94) = 0;
      *((_QWORD *)v53 + 95) = 0;
      *((_QWORD *)v53 + 52) = 0;
      *((_DWORD *)v53 + 100) = 0;
      *((_QWORD *)v53 + 51) = 0;
      *((_QWORD *)v53 + 54) = v53 + 424;
      *((_QWORD *)v53 + 53) = v53 + 424;
      *((_QWORD *)v53 + 56) = v53 + 440;
      *((_QWORD *)v53 + 55) = v53 + 440;
      RIMCheckPressureDefaultSetting(v53);
      *((_DWORD *)v53 + 262) = a12 == 0;
      *((_QWORD *)v53 + 132) = *(_QWORD *)&DestinationString.Length;
      *((_DWORD *)v53 + 266) = 0;
      *((_QWORD *)v53 + 136) = v92;
      *((_DWORD *)v53 + 274) = 0;
      v54 = 0;
      v55 = 0;
      do
      {
        v56 = 32 * v55;
        *(_OWORD *)&v53[v56 + 120] = *(_OWORD *)&(&off_14024FF60)[4 * v55];
        *(_OWORD *)&v53[v56 + 136] = *((_OWORD *)&off_14024FF60 + 2 * v55 + 1);
        *(_QWORD *)&v53[8 * v55 + 216] = 0;
        *(_QWORD *)&v53[8 * v55 + 304] = Buffer[v55];
        *(_DWORD *)&v53[4 * v55 + 288] = 0;
        Buffer[v55] = 0;
        *(_DWORD *)&v53[16 * v55 + 248] = v54;
        *(_QWORD *)&v53[16 * v55 + 240] = v53;
        ++v54;
        ++v55;
      }
      while ( v54 <= 2 );
      *((_QWORD *)v53 + 41) = v98;
      *((_QWORD *)v53 + 49) = a9;
      *((_QWORD *)v53 + 42) = Handle;
      v53[384] = v88;
      v53[385] = 0;
      *((_QWORD *)v53 + 43) = 0;
      *((_QWORD *)v53 + 44) = 0;
      *((_QWORD *)v53 + 45) = v99;
      *((_QWORD *)v53 + 47) = v53 + 368;
      *((_QWORD *)v53 + 46) = v53 + 368;
      v53[768] = 0;
      *((_QWORD *)v53 + 112) = 0;
      v57 = ((unsigned __int64)(500 * gliQpcFreq.QuadPart) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      *((_QWORD *)v53 + 111) = (v57 + ((unsigned __int64)(500 * gliQpcFreq.QuadPart - v57) >> 1)) >> 9;
      v58 = ((unsigned __int64)(5000 * gliQpcFreq.QuadPart) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      *((_QWORD *)v53 + 115) = (v58 + ((unsigned __int64)(5000 * gliQpcFreq.QuadPart - v58) >> 1)) >> 9;
      *((_QWORD *)v53 + 102) = a10;
      *((_QWORD *)v53 + 103) = a11;
      *((_WORD *)v53 + 352) = 0;
      *(_QWORD *)(v53 + 708) = 1;
      *((_QWORD *)v53 + 99) = 0;
      *((_QWORD *)v53 + 91) = v53 + 720;
      *((_QWORD *)v53 + 90) = v53 + 720;
      *((_QWORD *)v53 + 93) = v53 + 736;
      *((_QWORD *)v53 + 92) = v53 + 736;
      *((_QWORD *)v53 + 98) = v53 + 776;
      *((_QWORD *)v53 + 97) = v53 + 776;
      *((_QWORD *)v53 + 101) = v53 + 800;
      *((_QWORD *)v53 + 100) = v53 + 800;
      *((_QWORD *)v53 + 135) = v53 + 1072;
      *((_QWORD *)v53 + 134) = v53 + 1072;
      RtlInitializeGenericTableAvl(
        (PRTL_AVL_TABLE)(v53 + 928),
        rimUserMemAllocNodeCompare,
        rimUserMemAllocNodeAlloc,
        (PRTL_AVL_FREE_ROUTINE)rimUserMemAllocNodeFree,
        0);
      *((_DWORD *)v53 + 20) = v85;
      if ( v85 )
      {
        if ( v87 )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 458);
        if ( 4 * (unsigned __int64)v85 > 0xFFFFFFFF )
        {
          v46 = -1073741811;
        }
        else
        {
          v59 = Win32AllocPoolZInitImpl(0x100u, 4 * v85, 0x70617552u);
          *((_QWORD *)v53 + 11) = v59;
          v60 = a12;
          if ( !v59 )
          {
            v46 = -1073741801;
LABEL_103:
            v64 = v87;
LABEL_104:
            if ( v64 )
            {
              SourceString = 0;
              p_DestinationString = 0;
              DestinationString = 0;
              if ( v60 )
              {
                v103 = 0;
                ULongFromUser = RtlReadULongFromUser(v87);
                LODWORD(v103) = ULongFromUser;
                *((_QWORD *)&v103 + 1) = RtlReadULong64FromUser(v87 + 8);
                *(_DWORD *)&SourceString.Length = ULongFromUser;
                *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v103);
                SourceString.Buffer = (PWSTR)*((_QWORD *)&v103 + 1);
                ProbeForRead(*((volatile void **)&v103 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
                if ( SourceString.Length > SourceString.MaximumLength || (SourceString.Length & 1) != 0 )
                {
                  if ( (SourceString.Length & 1) != 0 )
                    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 521);
                  ExRaiseAccessViolation();
                }
                if ( SourceString.Length )
                {
                  DestinationString.MaximumLength = SourceString.Length;
                  DestinationString.Length = SourceString.Length;
                  DestinationString.Buffer = (PWSTR)Win32AllocPoolZInitImpl(0x100u, SourceString.Length, 0x706D7452u);
                  if ( DestinationString.Buffer )
                  {
                    RtlCopyUnicodeString(&DestinationString, &SourceString);
                    p_DestinationString = &DestinationString;
                  }
                }
                else
                {
                  v46 = -1073741801;
                  v96 = -1073741801;
                }
              }
              if ( v46 >= 0 )
              {
                RIMLockExclusive(v53 + 96);
                v46 = RIMDiscoverSpecificDevice((struct RawInputManagerObject *)v53);
                RIMUnlockExclusive(v53 + 96);
                if ( v46 < 0 )
                {
                  if ( *((_QWORD *)v53 + 11) )
                    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 558);
                  v66 = (void *)*((_QWORD *)v53 + 51);
                  if ( v66 )
                  {
                    GreDeleteFastMutex(v66);
                    *((_QWORD *)v53 + 51) = 0;
                  }
                  *((_QWORD *)v53 + 41) = -1;
                  *((_QWORD *)v53 + 42) = -1;
                  *((_QWORD *)v53 + 45) = -1;
                }
              }
              if ( DestinationString.Buffer )
                GreDeleteFastMutex(DestinationString.Buffer);
            }
            else
            {
              if ( v46 >= 0 && !v53[384] )
                RIMDiscoverDevicesOfInputType(v53);
              RIMIDEAdoptOrphanedRimDevs(v53);
            }
            v67 = 0;
            InputTraceLogging::RIM::RawInputManagerObjectUsed((const struct RawInputManagerObject *)v53);
            ObfDereferenceObject(v53);
            KernelSemaphore = 0;
            goto LABEL_134;
          }
          if ( a12 )
          {
            for ( k = 0; ; ++k )
            {
              v95 = k;
              if ( k >= v85 )
                break;
              RtlCopyFromUser((void *)(*((_QWORD *)v53 + 11) + 4LL * k), (void *)(v100 + 4LL * k), 4u);
            }
            v64 = v87;
            v60 = a12;
            goto LABEL_104;
          }
          v61 = 0;
          v62 = v100;
          do
          {
            *(_DWORD *)(*((_QWORD *)v53 + 11) + 4LL * v61) = *(_DWORD *)(v62 + 4LL * v61);
            ++v61;
          }
          while ( v61 < v85 );
        }
      }
      v60 = a12;
      goto LABEL_103;
    }
  }
LABEL_133:
  v67 = v92;
LABEL_134:
  if ( v46 < 0 )
  {
    for ( m = 0; m != 3; ++m )
    {
      v70 = Buffer[m];
      if ( v70 )
        GreDeleteFastMutex(v70);
    }
    if ( KernelSemaphore )
      GreDeleteFastMutex(KernelSemaphore);
    if ( v67 )
      GreDeleteFastMutex(v67);
    if ( Handle != (HANDLE)-1LL )
      ZwClose(Handle);
    if ( v98 != (HANDLE)-1LL )
      ZwClose(v98);
    if ( v99 != (HANDLE)-1LL )
      ZwClose(v99);
    if ( v89 != (HANDLE)-1LL )
      ObCloseHandle(v89, 1);
  }
  else
  {
    for ( n = 0; n != 3; ++n )
    {
      if ( Buffer[n] )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 609);
    }
    if ( KernelSemaphore )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 612);
    if ( v67 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 613);
    if ( a12 )
      RtlWriteULong64ToUser(v93, v89);
    else
      *v93 = v89;
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v71 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v71 = 0;
  }
  v72 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v71 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v73 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control, v48);
    LOBYTE(v74) = v72;
    LOBYTE(v75) = v71;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v75,
      v74,
      *(_QWORD *)(v73 + 19408),
      4,
      1,
      20,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      v46);
  }
  return (unsigned int)v46;
}

```

## disassembly

```asm
0x140162810  mov     r11, rsp
0x140162813  push    rbx
0x140162814  push    rsi
0x140162815  push    rdi
0x140162816  push    r12
0x140162818  push    r13
0x14016281a  push    r14
0x14016281c  push    r15
0x14016281e  sub     rsp, 140h
0x140162825  mov     rax, cs:__security_cookie
0x14016282c  xor     rax, rsp
0x14016282f  mov     [rsp+178h+var_48], rax
0x140162837  mov     rax, r9
0x14016283a  mov     [rsp+178h+var_90], rax
0x140162842  mov     r15d, r8d
0x140162845  mov     [rsp+178h+var_108], r8d
0x14016284a  mov     [rsp+178h+var_100], rdx
0x14016284f  mov     ebx, ecx
0x140162851  mov     [rsp+178h+var_88], rdx
0x140162859  mov     qword ptr [rsp+178h+SourceString.Length], rax
0x140162861  mov     rax, [rsp+178h+arg_28]
0x140162869  mov     [rsp+178h+var_110], rax
0x14016286e  mov     rax, [rsp+178h+arg_30]
0x140162876  mov     [rsp+178h+var_68], rax
0x14016287e  mov     rax, [rsp+178h+arg_38]
0x140162886  mov     qword ptr [rsp+178h+var_78], rax
0x14016288e  mov     rax, [rsp+178h+arg_60]
0x140162896  mov     [rsp+178h+var_C8], rax
0x14016289e  or      r13, 0FFFFFFFFFFFFFFFFh
0x1401628a2  mov     [r11-0A8h], r13
0x1401628a9  mov     [r11-0A0h], r13
0x1401628b0  mov     [r11-98h], r13
0x1401628b7  mov     [r11-0F0h], r13
0x1401628be  xorps   xmm0, xmm0
0x1401628c1  xor     eax, eax
0x1401628c3  movups  xmmword ptr [r11-60h], xmm0
0x1401628c8  mov     [r11-50h], rax
0x1401628cc  lea     rsi, WPP_GLOBAL_Control
0x1401628d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1401628da  lea     r14d, [r13+2]
0x1401628de  cmp     rcx, rsi
0x1401628e1  jz      short loc_1401628F8
0x1401628e3  mov     eax, [rcx+2Ch]
0x1401628e6  test    r14b, al
0x1401628e9  jz      short loc_1401628F8
0x1401628eb  cmp     byte ptr [rcx+29h], 4
0x1401628ef  jb      short loc_1401628F8
0x1401628f1  mov     r12b, r14b
0x1401628f4  xor     edi, edi
0x1401628f6  jmp     short loc_1401628FD
0x1401628f8  xor     edi, edi
0x1401628fa  mov     r12b, dil
0x1401628fd  lea     rcx, WPP_RECORDER_INITIALIZED
0x140162904  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14016290b  setnz   al
0x14016290e  mov     [rsp+178h+var_118], al
0x140162912  test    r12b, r12b
0x140162915  jnz     short loc_14016291B
0x140162917  test    al, al
0x140162919  jz      short loc_14016296F
0x14016291b  call    cs:__imp_W32GetUserSessionState
0x140162922  nop     dword ptr [rax+rax+00h]
0x140162927  mov     r9, [rax+4BD0h]
0x14016292e  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140162935  mov     [rsp+178h+var_140], rax
0x14016293a  mov     [rsp+178h+var_148], 0Bh
0x140162941  mov     [rsp+178h+var_150], r14d
0x140162946  mov     byte ptr [rsp+178h+TableContext], 4
0x14016294b  mov     r8b, [rsp+178h+var_118]
0x140162950  mov     dl, r12b
0x140162953  mov     rcx, cs:WPP_GLOBAL_Control
0x14016295a  mov     rcx, [rcx+18h]
0x14016295e  call    WPP_RECORDER_AND_TRACE_SF_
0x140162963  lea     rcx, WPP_RECORDER_INITIALIZED
0x14016296a  mov     rdx, [rsp+178h+var_100]
0x14016296f  test    ebx, 0FFFFFFC0h
0x140162975  jz      loc_140162A71
0x14016297b  mov     rdx, cs:WPP_GLOBAL_Control
0x140162982  cmp     rdx, rsi
0x140162985  jz      short loc_1401629A0
0x140162987  mov     eax, [rdx+2Ch]
0x14016298a  test    r14b, al
0x14016298d  jz      short loc_1401629A0
0x14016298f  mov     r12d, 2
0x140162995  cmp     [rdx+29h], r12b
0x140162999  jb      short loc_1401629A6
0x14016299b  mov     r15b, r14b
0x14016299e  jmp     short loc_1401629A9
0x1401629a0  mov     r12d, 2
0x1401629a6  mov     r15b, dil
0x1401629a9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1401629b0  setnz   al
0x1401629b3  mov     [rsp+178h+var_118], al
0x1401629b7  test    r15b, r15b
0x1401629ba  jnz     short loc_1401629C0
0x1401629bc  test    al, al
0x1401629be  jz      short loc_140162A15
0x1401629c0  call    cs:__imp_W32GetUserSessionState
0x1401629c7  nop     dword ptr [rax+rax+00h]
0x1401629cc  mov     r9, [rax+4BD0h]
0x1401629d3  mov     dword ptr [rsp+178h+var_138], ebx
0x1401629d7  lea     r13, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401629de  mov     [rsp+178h+var_140], r13
0x1401629e3  mov     [rsp+178h+var_148], 0Ch
0x1401629ea  mov     [rsp+178h+var_150], r14d
0x1401629ef  mov     byte ptr [rsp+178h+TableContext], r12b
0x1401629f4  mov     r8b, [rsp+178h+var_118]
0x1401629f9  mov     dl, r15b
0x1401629fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140162a03  mov     rcx, [rcx+18h]
0x140162a07  call    WPP_RECORDER_AND_TRACE_SF_D
0x140162a0c  lea     rcx, WPP_RECORDER_INITIALIZED
0x140162a13  jmp     short loc_140162A1C
0x140162a15  lea     r13, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140162a1c  mov     rdx, cs:WPP_GLOBAL_Control
0x140162a23  cmp     rdx, rsi
0x140162a26  jz      short loc_140162A39
0x140162a28  mov     eax, [rdx+2Ch]
0x140162a2b  test    r14b, al
0x140162a2e  jz      short loc_140162A39
0x140162a30  cmp     byte ptr [rdx+29h], 4
0x140162a34  mov     bl, r14b
0x140162a37  jnb     short loc_140162A3C
0x140162a39  mov     bl, dil
0x140162a3c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140162a43  setnz   sil
0x140162a47  test    bl, bl
0x140162a49  jnz     short loc_140162A54
0x140162a4b  test    sil, sil
0x140162a4e  jz      loc_140162C9D
0x140162a54  call    cs:__imp_W32GetUserSessionState
0x140162a5b  nop     dword ptr [rax+rax+00h]
0x140162a60  mov     [rsp+178h+var_140], r13
0x140162a65  mov     [rsp+178h+var_148], 0Dh
0x140162a6c  jmp     loc_140162C77
0x140162a71  test    rdx, rdx
0x140162a74  jz      loc_140162B68
0x140162a7a  test    ebx, ebx
0x140162a7c  jz      short loc_140162A8E
0x140162a7e  lea     eax, [rbx-1]
0x140162a81  test    ebx, eax
0x140162a83  jnz     short loc_140162A8E
0x140162a85  test    r15d, r15d
0x140162a88  jz      loc_140162B68
0x140162a8e  mov     rdx, cs:WPP_GLOBAL_Control
0x140162a95  cmp     rdx, rsi
0x140162a98  jz      short loc_140162AB1
0x140162a9a  mov     eax, [rdx+2Ch]
0x140162a9d  test    r14b, al
0x140162aa0  jz      short loc_140162AB1
0x140162aa2  mov     r12d, 2
0x140162aa8  cmp     [rdx+29h], r12b
0x140162aac  mov     r12b, r14b
0x140162aaf  jnb     short loc_140162AB4
0x140162ab1  mov     r12b, dil
0x140162ab4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140162abb  setnz   r13b
0x140162abf  test    r12b, r12b
0x140162ac2  jnz     short loc_140162AC9
0x140162ac4  test    r13b, r13b
0x140162ac7  jz      short loc_140162B0C
0x140162ac9  call    cs:__imp_W32GetUserSessionState
0x140162ad0  nop     dword ptr [rax+rax+00h]
0x140162ad5  mov     r9, [rax+4BD0h]
0x140162adc  mov     [rsp+178h+var_128], r15d
0x140162ae1  mov     [rsp+178h+var_130], ebx
0x140162ae5  mov     rax, [rsp+178h+var_100]
0x140162aea  mov     [rsp+178h+var_138], rax
0x140162aef  mov     r8b, r13b
0x140162af2  mov     dl, r12b
0x140162af5  mov     rcx, cs:WPP_GLOBAL_Control
0x140162afc  mov     rcx, [rcx+18h]
0x140162b00  call    WPP_RECORDER_AND_TRACE_SF_qDd
0x140162b05  lea     rcx, WPP_RECORDER_INITIALIZED
0x140162b0c  mov     rdx, cs:WPP_GLOBAL_Control
0x140162b13  cmp     rdx, rsi
0x140162b16  jz      short loc_140162B29
0x140162b18  mov     eax, [rdx+2Ch]
0x140162b1b  test    r14b, al
0x140162b1e  jz      short loc_140162B29
0x140162b20  cmp     byte ptr [rdx+29h], 4
0x140162b24  mov     bl, r14b
0x140162b27  jnb     short loc_140162B2C
0x140162b29  mov     bl, dil
0x140162b2c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140162b33  setnz   sil
0x140162b37  test    bl, bl
0x140162b39  jnz     short loc_140162B44
0x140162b3b  test    sil, sil
0x140162b3e  jz      loc_140162C9D
0x140162b44  call    cs:__imp_W32GetUserSessionState
0x140162b4b  nop     dword ptr [rax+rax+00h]
0x140162b50  lea     r13, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140162b57  mov     [rsp+178h+var_140], r13
0x140162b5c  mov     [rsp+178h+var_148], 0Fh
0x140162b63  jmp     loc_140162C77
0x140162b68  mov     r12b, dil
0x140162b6b  mov     dword ptr [rsp+178h+var_F8], r12d
0x140162b73  test    r15d, r15d
0x140162b76  jz      loc_140162CD8
0x140162b7c  test    bl, 20h
0x140162b7f  jnz     loc_140162CA7
0x140162b85  mov     rdx, cs:WPP_GLOBAL_Control
0x140162b8c  cmp     rdx, rsi
0x140162b8f  jz      short loc_140162BAA
0x140162b91  mov     eax, [rdx+2Ch]
0x140162b94  test    r14b, al
0x140162b97  jz      short loc_140162BAA
0x140162b99  mov     r12d, 2
0x140162b9f  cmp     [rdx+29h], r12b
0x140162ba3  jb      short loc_140162BB0
0x140162ba5  mov     r13b, r14b
0x140162ba8  jmp     short loc_140162BB3
0x140162baa  mov     r12d, 2
0x140162bb0  mov     r13b, dil
0x140162bb3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140162bba  setnz   al
0x140162bbd  mov     [rsp+178h+var_118], al
0x140162bc1  test    r13b, r13b
0x140162bc4  jnz     short loc_140162BCA
0x140162bc6  test    al, al
0x140162bc8  jz      short loc_140162C24
0x140162bca  call    cs:__imp_W32GetUserSessionState
0x140162bd1  nop     dword ptr [rax+rax+00h]
0x140162bd6  mov     r9, [rax+4BD0h]
0x140162bdd  mov     [rsp+178h+var_130], r15d
0x140162be2  mov     dword ptr [rsp+178h+var_138], ebx
0x140162be6  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140162bed  mov     [rsp+178h+var_140], r15
0x140162bf2  mov     [rsp+178h+var_148], 10h
0x140162bf9  mov     [rsp+178h+var_150], r14d
0x140162bfe  mov     byte ptr [rsp+178h+TableContext], r12b
0x140162c03  mov     r8b, [rsp+178h+var_118]
0x140162c08  mov     dl, r13b
0x140162c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140162c12  mov     rcx, [rcx+18h]
0x140162c16  call    WPP_RECORDER_AND_TRACE_SF_DD
0x140162c1b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140162c22  jmp     short loc_140162C2B
0x140162c24  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140162c2b  mov     rdx, cs:WPP_GLOBAL_Control
0x140162c32  cmp     rdx, rsi
0x140162c35  jz      short loc_140162C48
0x140162c37  mov     eax, [rdx+2Ch]
0x140162c3a  test    r14b, al
0x140162c3d  jz      short loc_140162C48
0x140162c3f  cmp     byte ptr [rdx+29h], 4
0x140162c43  mov     bl, r14b
0x140162c46  jnb     short loc_140162C4B
0x140162c48  mov     bl, dil
0x140162c4b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140162c52  setnz   sil
0x140162c56  test    bl, bl
0x140162c58  jnz     short loc_140162C5F
0x140162c5a  test    sil, sil
0x140162c5d  jz      short loc_140162C9D
0x140162c5f  call    cs:__imp_W32GetUserSessionState
0x140162c66  nop     dword ptr [rax+rax+00h]
0x140162c6b  mov     [rsp+178h+var_140], r15
0x140162c70  mov     [rsp+178h+var_148], 11h
0x140162c77  mov     [rsp+178h+var_150], r14d
0x140162c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140162c83  mov     byte ptr [rsp+178h+TableContext], 4
0x140162c88  mov     r9, [rax+4BD0h]
0x140162c8f  mov     r8b, sil
0x140162c92  mov     dl, bl
0x140162c94  mov     rcx, [rcx+18h]
0x140162c98  call    WPP_RECORDER_AND_TRACE_SF_
0x140162c9d  mov     eax, 0C000000Dh
0x140162ca2  jmp     loc_14016383C
0x140162ca7  cmp     [rsp+178h+arg_58], edi
0x140162cae  jz      short loc_140162CD8
0x140162cb0  mov     ecx, ebx
0x140162cb2  call    rimCheckForRegistrationConflicts
0x140162cb7  cmp     eax, r14d
0x140162cba  jnz     short loc_140162CC6
0x140162cbc  mov     eax, 0C0000022h
0x140162cc1  jmp     loc_14016383C
0x140162cc6  movzx   r12d, r12b
0x140162cca  test    eax, eax
0x140162ccc  cmovz   r12d, r14d
0x140162cd0  mov     dword ptr [rsp+178h+var_F8], r12d
0x140162cd8  mov     edx, r13d; Limit
0x140162cdb  xor     ecx, ecx; Count
0x140162cdd  call    CreateKernelSemaphore
0x140162ce2  mov     rsi, rax
0x140162ce5  mov     qword ptr [rsp+178h+DestinationString.Length], rax
0x140162ced  test    rax, rax
0x140162cf0  jnz     short loc_140162CFC
0x140162cf2  mov     eax, 0C0000017h
0x140162cf7  jmp     loc_14016383C
0x140162cfc  mov     edx, 7FFFFFFFh; Limit
0x140162d01  xor     ecx, ecx; Count
0x140162d03  call    CreateKernelSemaphore
0x140162d08  mov     r15, rax
0x140162d0b  mov     [rsp+178h+var_D0], rax
0x140162d13  test    rax, rax
0x140162d16  jnz     short loc_140162D22
0x140162d18  mov     rcx, rsi; Buffer
0x140162d1b  call    GreDeleteFastMutex
  ... truncated ...
```
