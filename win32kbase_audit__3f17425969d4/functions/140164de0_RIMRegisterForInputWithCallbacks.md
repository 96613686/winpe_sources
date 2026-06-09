# RIMRegisterForInputWithCallbacks

- ea: `0x140164de0`
- end: `0x140165e30`
- name: `RIMRegisterForInputWithCallbacks`
- size: `4176`
- prototype: `__int64 __fastcall(unsigned int, __int64, unsigned int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, int, HANDLE *)`
- caller_count: `2`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x140164d70`
- `0x1401b4514`

## callees

- `0x140049df8`
- `0x140049ec0`
- `0x14004e9f0`
- `0x140062ff0`
- `0x1400682c0`
- `0x140069e00`
- `0x14007b930`
- `0x14007efd0`
- `0x140092750`
- `0x1400a5ba0`
- `0x14011aa7c`
- `0x140164de0`
- `0x140165e40`
- `0x140167774`
- `0x14016e35c`
- `0x140173ac0`
- `0x1401760fc`
- `0x14017c468`
- `0x1401aab9c`
- `0x1401ab11c`
- `0x1401b4c64`
- `0x1401b6518`
- `0x1401c0a20`
- `0x1401c7158`
- `0x1401ff970`
- `0x140202f4c`
- `0x1402388e0`
- `0x1402bb164`
- `0x1402bb1a0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14016595a`
- `ntoskrnl!ProbeForRead` at `0x14016595a`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140165a2a`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140165a2a`
- `ntoskrnl!ZwClose` at `0x140165d23`
- `ntoskrnl!ZwClose` at `0x140165d3c`
- `ntoskrnl!ZwClose` at `0x140165d55`
- `ntoskrnl!ZwClose` at `0x140165d23`
- `ntoskrnl!ZwClose` at `0x140165d3c`
- `ntoskrnl!ZwClose` at `0x140165d55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401653d2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401653d2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401653fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401653fa`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401659cc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401659cc`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1401656da`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1401656da`
- `ntoskrnl!ObCloseHandle` at `0x140165d71`
- `ntoskrnl!ObCloseHandle` at `0x140165d71`
- `ntoskrnl!ObfDereferenceObject` at `0x140165bba`
- `ntoskrnl!ObfDereferenceObject` at `0x140165bba`
- `WIN32K!W32GetUserSessionState` at `0x140164eeb`
- `WIN32K!W32GetUserSessionState` at `0x140164f90`
- `WIN32K!W32GetUserSessionState` at `0x140165024`
- `WIN32K!W32GetUserSessionState` at `0x140165099`
- `WIN32K!W32GetUserSessionState` at `0x140165114`
- `WIN32K!W32GetUserSessionState` at `0x14016519a`
- `WIN32K!W32GetUserSessionState` at `0x14016522f`
- `WIN32K!W32GetUserSessionState` at `0x140165814`
- `WIN32K!W32GetUserSessionState` at `0x140165a78`
- `WIN32K!W32GetUserSessionState` at `0x140165dc6`
- `WIN32K!W32GetUserSessionState` at `0x140164eeb`
- `WIN32K!W32GetUserSessionState` at `0x140164f90`
- `WIN32K!W32GetUserSessionState` at `0x140165024`
- `WIN32K!W32GetUserSessionState` at `0x140165099`
- `WIN32K!W32GetUserSessionState` at `0x140165114`
- `WIN32K!W32GetUserSessionState` at `0x14016519a`
- `WIN32K!W32GetUserSessionState` at `0x14016522f`
- `WIN32K!W32GetUserSessionState` at `0x140165814`
- `WIN32K!W32GetUserSessionState` at `0x140165a78`
- `WIN32K!W32GetUserSessionState` at `0x140165dc6`

## pseudocode

```c
__int64 __fastcall RIMRegisterForInputWithCallbacks(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
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
  bool v48; // sf
  int v49; // edx
  int v50; // r8d
  int v51; // r9d
  char *v52; // rsi
  unsigned int v53; // edx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rdx
  void *v58; // rax
  int v59; // ecx
  unsigned int v60; // r8d
  __int64 v61; // r9
  unsigned int k; // ebx
  __int64 v63; // rax
  int ULongFromUser; // ebx
  void *v65; // rcx
  void *v66; // rbx
  __int64 n; // r13
  __int64 m; // r12
  PVOID v69; // rcx
  char v70; // bl
  bool v71; // r12
  __int64 v72; // rax
  int v73; // r8d
  int v74; // edx
  int TableContext; // [rsp+20h] [rbp-158h]
  int v76; // [rsp+28h] [rbp-150h]
  int v77; // [rsp+30h] [rbp-148h]
  __int16 v78; // [rsp+30h] [rbp-148h]
  int v79; // [rsp+38h] [rbp-140h]
  bool v80; // [rsp+60h] [rbp-118h]
  bool v81; // [rsp+60h] [rbp-118h]
  bool v82; // [rsp+60h] [rbp-118h]
  int v83; // [rsp+68h] [rbp-110h]
  unsigned int v85; // [rsp+74h] [rbp-104h]
  __int64 v86; // [rsp+78h] [rbp-100h]
  bool v87; // [rsp+80h] [rbp-F8h]
  HANDLE v88; // [rsp+88h] [rbp-F0h] BYREF
  PVOID Object; // [rsp+90h] [rbp-E8h] BYREF
  UNICODE_STRING SourceString; // [rsp+98h] [rbp-E0h] BYREF
  void *v91; // [rsp+A8h] [rbp-D0h]
  HANDLE *v92; // [rsp+B0h] [rbp-C8h]
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-C0h] BYREF
  unsigned int v94; // [rsp+C8h] [rbp-B0h]
  int v95; // [rsp+CCh] [rbp-ACh]
  HANDLE Handle; // [rsp+D0h] [rbp-A8h] BYREF
  HANDLE v97; // [rsp+D8h] [rbp-A0h] BYREF
  HANDLE v98; // [rsp+E0h] [rbp-98h] BYREF
  __int64 v99; // [rsp+E8h] [rbp-90h]
  __int64 v100; // [rsp+F0h] [rbp-88h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+F8h] [rbp-80h]
  __int128 v102; // [rsp+100h] [rbp-78h]
  __int64 v103; // [rsp+110h] [rbp-68h]
  PVOID Buffer[3]; // [rsp+118h] [rbp-60h] BYREF

  v99 = a4;
  v86 = a2;
  v100 = a2;
  *(_QWORD *)&SourceString.Length = a4;
  v103 = a7;
  *(_QWORD *)&v102 = a8;
  v92 = a13;
  Handle = (HANDLE)-1LL;
  v97 = (HANDLE)-1LL;
  v98 = (HANDLE)-1LL;
  v88 = (HANDLE)-1LL;
  memset(Buffer, 0, sizeof(Buffer));
  v15 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v80 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, a2);
    LOBYTE(v17) = v80;
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
    a2 = v86;
  }
  if ( (a1 & 0xFFFFFFC0) != 0 )
  {
    v19 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u;
    v81 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control);
      LOBYTE(v21) = v81;
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
    v25 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control);
    v78 = 13;
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
      v78,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    return 3221225485LL;
  }
  if ( a2 && (!a1 || ((a1 - 1) & a1) != 0 || a3) )
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
      v30 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control);
      LOBYTE(v31) = v29;
      LOBYTE(v32) = v28;
      WPP_RECORDER_AND_TRACE_SF_qDd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v32,
        v31,
        *(_QWORD *)(v30 + 19408),
        TableContext,
        v76,
        v77,
        v79,
        v86,
        a1,
        a3);
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
    v25 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control);
    v78 = 15;
    goto LABEL_60;
  }
  v87 = 0;
  if ( a3 )
  {
    if ( (a1 & 0x20) == 0 )
    {
      v33 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u;
      v82 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v33 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v34 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control);
        LOBYTE(v35) = v82;
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
          a3);
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
      v25 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control);
      v78 = 17;
      goto LABEL_60;
    }
    if ( a12 )
    {
      v38 = rimCheckForRegistrationConflicts(a1);
      if ( v38 == 1 )
        return 3221225506LL;
      v87 = v38 == 0;
    }
  }
  KernelSemaphore = (void *)CreateKernelSemaphore(0, -1);
  *(_QWORD *)&DestinationString.Length = KernelSemaphore;
  if ( !KernelSemaphore )
    return 3221225495LL;
  v40 = CreateKernelSemaphore(0, 0x7FFFFFFF);
  v91 = (void *)v40;
  if ( !v40 )
  {
    v41 = KernelSemaphore;
LABEL_70:
    GreDeleteFastMutex(v41);
    return 3221225495LL;
  }
  for ( i = 0; ; i = v85 + 1 )
  {
    v85 = i;
    if ( i > 2 )
      break;
    v43 = Win32AllocPoolZInitImpl(0x40u, 0x68u, 0x63704152u);
    Buffer[v85] = v43;
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
  v83 = rimConvertUserToKernelTimerHandle(v103, &v97);
  v47 = rimConvertUserToKernelSemaphoreHandle(v102, &v98);
  v48 = v46 < 0;
  if ( v46 < 0 )
    goto LABEL_131;
  if ( v83 < 0 || v47 < 0 )
  {
    v48 = v46 < 0;
LABEL_131:
    if ( !v48 )
      v46 = v83;
    goto LABEL_133;
  }
  KeEnterCriticalRegion();
  v46 = RawInputManagerObjectCreate((int)Object, v49, v50, v51, &v88);
  KeLeaveCriticalRegion();
  if ( v46 >= 0 )
  {
    Object = 0;
    v46 = RawInputManagerObjectResolveHandle(v88, 3, 1, &Object);
    if ( v46 >= 0 )
    {
      v52 = (char *)Object;
      *((_QWORD *)Object + 8) = v88;
      *((_WORD *)v52 + 36) = 0;
      v52[74] = 0;
      *((_DWORD *)v52 + 19) = a1;
      *((_QWORD *)v52 + 14) = a5;
      *((_QWORD *)v52 + 12) = 0;
      *((_QWORD *)v52 + 13) = 0;
      *((_QWORD *)v52 + 94) = 0;
      *((_QWORD *)v52 + 95) = 0;
      *((_QWORD *)v52 + 52) = 0;
      *((_DWORD *)v52 + 100) = 0;
      *((_QWORD *)v52 + 51) = 0;
      *((_QWORD *)v52 + 54) = v52 + 424;
      *((_QWORD *)v52 + 53) = v52 + 424;
      *((_QWORD *)v52 + 56) = v52 + 440;
      *((_QWORD *)v52 + 55) = v52 + 440;
      RIMCheckPressureDefaultSetting(v52);
      *((_DWORD *)v52 + 262) = a12 == 0;
      *((_QWORD *)v52 + 132) = *(_QWORD *)&DestinationString.Length;
      *((_DWORD *)v52 + 266) = 0;
      *((_QWORD *)v52 + 136) = v91;
      *((_DWORD *)v52 + 274) = 0;
      v53 = 0;
      v54 = 0;
      do
      {
        v55 = 32 * v54;
        *(_OWORD *)&v52[v55 + 120] = *(_OWORD *)&(&off_140250EF0)[4 * v54];
        *(_OWORD *)&v52[v55 + 136] = *((_OWORD *)&off_140250EF0 + 2 * v54 + 1);
        *(_QWORD *)&v52[8 * v54 + 216] = 0;
        *(_QWORD *)&v52[8 * v54 + 304] = Buffer[v54];
        *(_DWORD *)&v52[4 * v54 + 288] = 0;
        Buffer[v54] = 0;
        *(_DWORD *)&v52[16 * v54 + 248] = v53;
        *(_QWORD *)&v52[16 * v54 + 240] = v52;
        ++v53;
        ++v54;
      }
      while ( v53 <= 2 );
      *((_QWORD *)v52 + 41) = v97;
      *((_QWORD *)v52 + 49) = a9;
      *((_QWORD *)v52 + 42) = Handle;
      v52[384] = v87;
      v52[385] = 0;
      *((_QWORD *)v52 + 43) = 0;
      *((_QWORD *)v52 + 44) = 0;
      *((_QWORD *)v52 + 45) = v98;
      *((_QWORD *)v52 + 47) = v52 + 368;
      *((_QWORD *)v52 + 46) = v52 + 368;
      v52[768] = 0;
      *((_QWORD *)v52 + 112) = 0;
      v56 = ((unsigned __int64)(500 * gliQpcFreq.QuadPart) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      *((_QWORD *)v52 + 111) = (v56 + ((unsigned __int64)(500 * gliQpcFreq.QuadPart - v56) >> 1)) >> 9;
      v57 = ((unsigned __int64)(5000 * gliQpcFreq.QuadPart) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
      *((_QWORD *)v52 + 115) = (v57 + ((unsigned __int64)(5000 * gliQpcFreq.QuadPart - v57) >> 1)) >> 9;
      *((_QWORD *)v52 + 102) = a10;
      *((_QWORD *)v52 + 103) = a11;
      *((_WORD *)v52 + 352) = 0;
      *(_QWORD *)(v52 + 708) = 1;
      *((_QWORD *)v52 + 99) = 0;
      *((_QWORD *)v52 + 91) = v52 + 720;
      *((_QWORD *)v52 + 90) = v52 + 720;
      *((_QWORD *)v52 + 93) = v52 + 736;
      *((_QWORD *)v52 + 92) = v52 + 736;
      *((_QWORD *)v52 + 98) = v52 + 776;
      *((_QWORD *)v52 + 97) = v52 + 776;
      *((_QWORD *)v52 + 101) = v52 + 800;
      *((_QWORD *)v52 + 100) = v52 + 800;
      *((_QWORD *)v52 + 135) = v52 + 1072;
      *((_QWORD *)v52 + 134) = v52 + 1072;
      RtlInitializeGenericTableAvl(
        (PRTL_AVL_TABLE)(v52 + 928),
        rimUserMemAllocNodeCompare,
        rimUserMemAllocNodeAlloc,
        rimUserMemAllocNodeFree,
        0);
      *((_DWORD *)v52 + 20) = a3;
      if ( a3 )
      {
        if ( v86 )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 458);
        if ( 4 * (unsigned __int64)a3 > 0xFFFFFFFF )
        {
          v46 = -1073741811;
        }
        else
        {
          v58 = Win32AllocPoolZInitImpl(0x100u, 4 * a3, 0x70617552u);
          *((_QWORD *)v52 + 11) = v58;
          v59 = a12;
          if ( !v58 )
          {
            v46 = -1073741801;
LABEL_103:
            v63 = v86;
LABEL_104:
            if ( v63 )
            {
              SourceString = 0;
              p_DestinationString = 0;
              DestinationString = 0;
              if ( v59 )
              {
                v102 = 0;
                ULongFromUser = RtlReadULongFromUser(v86);
                LODWORD(v102) = ULongFromUser;
                *((_QWORD *)&v102 + 1) = RtlReadULong64FromUser(v86 + 8);
                *(_DWORD *)&SourceString.Length = ULongFromUser;
                *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v102);
                SourceString.Buffer = (PWSTR)*((_QWORD *)&v102 + 1);
                ProbeForRead(*((volatile void **)&v102 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
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
                  v95 = -1073741801;
                }
              }
              if ( v46 >= 0 )
              {
                RIMLockExclusive(v52 + 96);
                v46 = RIMDiscoverSpecificDevice((struct RawInputManagerObject *)v52);
                RIMUnlockExclusive(v52 + 96);
                if ( v46 < 0 )
                {
                  if ( *((_QWORD *)v52 + 11) )
                    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 558);
                  v65 = (void *)*((_QWORD *)v52 + 51);
                  if ( v65 )
                  {
                    GreDeleteFastMutex(v65);
                    *((_QWORD *)v52 + 51) = 0;
                  }
                  *((_QWORD *)v52 + 41) = -1;
                  *((_QWORD *)v52 + 42) = -1;
                  *((_QWORD *)v52 + 45) = -1;
                }
              }
              if ( DestinationString.Buffer )
                GreDeleteFastMutex(DestinationString.Buffer);
            }
            else
            {
              if ( v46 >= 0 && !v52[384] )
                RIMDiscoverDevicesOfInputType(v52);
              RIMIDEAdoptOrphanedRimDevs(v52);
            }
            v66 = 0;
            InputTraceLogging::RIM::RawInputManagerObjectUsed((const struct RawInputManagerObject *)v52);
            ObfDereferenceObject(v52);
            KernelSemaphore = 0;
            goto LABEL_134;
          }
          if ( a12 )
          {
            for ( k = 0; ; ++k )
            {
              v94 = k;
              if ( k >= a3 )
                break;
              RtlCopyFromUser((void *)(*((_QWORD *)v52 + 11) + 4LL * k), (void *)(v99 + 4LL * k), 4u);
            }
            v63 = v86;
            v59 = a12;
            goto LABEL_104;
          }
          v60 = 0;
          v61 = v99;
          do
          {
            *(_DWORD *)(*((_QWORD *)v52 + 11) + 4LL * v60) = *(_DWORD *)(v61 + 4LL * v60);
            ++v60;
          }
          while ( v60 < a3 );
        }
      }
      v59 = a12;
      goto LABEL_103;
    }
  }
LABEL_133:
  v66 = v91;
LABEL_134:
  if ( v46 < 0 )
  {
    for ( m = 0; m != 3; ++m )
    {
      v69 = Buffer[m];
      if ( v69 )
        GreDeleteFastMutex(v69);
    }
    if ( KernelSemaphore )
      GreDeleteFastMutex(KernelSemaphore);
    if ( v66 )
      GreDeleteFastMutex(v66);
    if ( Handle != (HANDLE)-1LL )
      ZwClose(Handle);
    if ( v97 != (HANDLE)-1LL )
      ZwClose(v97);
    if ( v98 != (HANDLE)-1LL )
      ZwClose(v98);
    if ( v88 != (HANDLE)-1LL )
      ObCloseHandle(v88, 1);
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
    if ( v66 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 613);
    if ( a12 )
      RtlWriteULong64ToUser(v92, v88);
    else
      *v92 = v88;
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v70 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v70 = 0;
  }
  v71 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v70 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v72 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, WPP_GLOBAL_Control);
    LOBYTE(v73) = v71;
    LOBYTE(v74) = v70;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v74,
      v73,
      *(_QWORD *)(v72 + 19408),
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
0x140164de0  mov     r11, rsp
0x140164de3  push    rbx
0x140164de4  push    rsi
0x140164de5  push    rdi
0x140164de6  push    r12
0x140164de8  push    r13
0x140164dea  push    r14
0x140164dec  push    r15
0x140164dee  sub     rsp, 140h
0x140164df5  mov     rax, cs:__security_cookie
0x140164dfc  xor     rax, rsp
0x140164dff  mov     [rsp+178h+var_48], rax
0x140164e07  mov     rax, r9
0x140164e0a  mov     [rsp+178h+var_90], rax
0x140164e12  mov     r15d, r8d
0x140164e15  mov     [rsp+178h+var_108], r8d
0x140164e1a  mov     [rsp+178h+var_100], rdx
0x140164e1f  mov     ebx, ecx
0x140164e21  mov     [rsp+178h+var_88], rdx
0x140164e29  mov     qword ptr [rsp+178h+SourceString.Length], rax
0x140164e31  mov     rax, [rsp+178h+arg_28]
0x140164e39  mov     [rsp+178h+var_110], rax
0x140164e3e  mov     rax, [rsp+178h+arg_30]
0x140164e46  mov     [rsp+178h+var_68], rax
0x140164e4e  mov     rax, [rsp+178h+arg_38]
0x140164e56  mov     qword ptr [rsp+178h+var_78], rax
0x140164e5e  mov     rax, [rsp+178h+arg_60]
0x140164e66  mov     [rsp+178h+var_C8], rax
0x140164e6e  or      r13, 0FFFFFFFFFFFFFFFFh
0x140164e72  mov     [r11-0A8h], r13
0x140164e79  mov     [r11-0A0h], r13
0x140164e80  mov     [r11-98h], r13
0x140164e87  mov     [r11-0F0h], r13
0x140164e8e  xorps   xmm0, xmm0
0x140164e91  xor     eax, eax
0x140164e93  movups  xmmword ptr [r11-60h], xmm0
0x140164e98  mov     [r11-50h], rax
0x140164e9c  lea     rsi, WPP_GLOBAL_Control
0x140164ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x140164eaa  lea     r14d, [r13+2]
0x140164eae  cmp     rcx, rsi
0x140164eb1  jz      short loc_140164EC8
0x140164eb3  mov     eax, [rcx+2Ch]
0x140164eb6  test    r14b, al
0x140164eb9  jz      short loc_140164EC8
0x140164ebb  cmp     byte ptr [rcx+29h], 4
0x140164ebf  jb      short loc_140164EC8
0x140164ec1  mov     r12b, r14b
0x140164ec4  xor     edi, edi
0x140164ec6  jmp     short loc_140164ECD
0x140164ec8  xor     edi, edi
0x140164eca  mov     r12b, dil
0x140164ecd  lea     rcx, WPP_RECORDER_INITIALIZED
0x140164ed4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140164edb  setnz   al
0x140164ede  mov     [rsp+178h+var_118], al
0x140164ee2  test    r12b, r12b
0x140164ee5  jnz     short loc_140164EEB
0x140164ee7  test    al, al
0x140164ee9  jz      short loc_140164F3F
0x140164eeb  call    cs:__imp_W32GetUserSessionState
0x140164ef2  nop     dword ptr [rax+rax+00h]
0x140164ef7  mov     r9, [rax+4BD0h]
0x140164efe  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140164f05  mov     [rsp+178h+var_140], rax
0x140164f0a  mov     [rsp+178h+var_148], 0Bh
0x140164f11  mov     [rsp+178h+var_150], r14d
0x140164f16  mov     byte ptr [rsp+178h+TableContext], 4
0x140164f1b  mov     r8b, [rsp+178h+var_118]
0x140164f20  mov     dl, r12b
0x140164f23  mov     rcx, cs:WPP_GLOBAL_Control
0x140164f2a  mov     rcx, [rcx+18h]
0x140164f2e  call    WPP_RECORDER_AND_TRACE_SF_
0x140164f33  lea     rcx, WPP_RECORDER_INITIALIZED
0x140164f3a  mov     rdx, [rsp+178h+var_100]
0x140164f3f  test    ebx, 0FFFFFFC0h
0x140164f45  jz      loc_140165041
0x140164f4b  mov     rdx, cs:WPP_GLOBAL_Control
0x140164f52  cmp     rdx, rsi
0x140164f55  jz      short loc_140164F70
0x140164f57  mov     eax, [rdx+2Ch]
0x140164f5a  test    r14b, al
0x140164f5d  jz      short loc_140164F70
0x140164f5f  mov     r12d, 2
0x140164f65  cmp     [rdx+29h], r12b
0x140164f69  jb      short loc_140164F76
0x140164f6b  mov     r15b, r14b
0x140164f6e  jmp     short loc_140164F79
0x140164f70  mov     r12d, 2
0x140164f76  mov     r15b, dil
0x140164f79  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140164f80  setnz   al
0x140164f83  mov     [rsp+178h+var_118], al
0x140164f87  test    r15b, r15b
0x140164f8a  jnz     short loc_140164F90
0x140164f8c  test    al, al
0x140164f8e  jz      short loc_140164FE5
0x140164f90  call    cs:__imp_W32GetUserSessionState
0x140164f97  nop     dword ptr [rax+rax+00h]
0x140164f9c  mov     r9, [rax+4BD0h]
0x140164fa3  mov     dword ptr [rsp+178h+var_138], ebx
0x140164fa7  lea     r13, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140164fae  mov     [rsp+178h+var_140], r13
0x140164fb3  mov     [rsp+178h+var_148], 0Ch
0x140164fba  mov     [rsp+178h+var_150], r14d
0x140164fbf  mov     byte ptr [rsp+178h+TableContext], r12b
0x140164fc4  mov     r8b, [rsp+178h+var_118]
0x140164fc9  mov     dl, r15b
0x140164fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x140164fd3  mov     rcx, [rcx+18h]
0x140164fd7  call    WPP_RECORDER_AND_TRACE_SF_D
0x140164fdc  lea     rcx, WPP_RECORDER_INITIALIZED
0x140164fe3  jmp     short loc_140164FEC
0x140164fe5  lea     r13, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140164fec  mov     rdx, cs:WPP_GLOBAL_Control
0x140164ff3  cmp     rdx, rsi
0x140164ff6  jz      short loc_140165009
0x140164ff8  mov     eax, [rdx+2Ch]
0x140164ffb  test    r14b, al
0x140164ffe  jz      short loc_140165009
0x140165000  cmp     byte ptr [rdx+29h], 4
0x140165004  mov     bl, r14b
0x140165007  jnb     short loc_14016500C
0x140165009  mov     bl, dil
0x14016500c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140165013  setnz   sil
0x140165017  test    bl, bl
0x140165019  jnz     short loc_140165024
0x14016501b  test    sil, sil
0x14016501e  jz      loc_14016526D
0x140165024  call    cs:__imp_W32GetUserSessionState
0x14016502b  nop     dword ptr [rax+rax+00h]
0x140165030  mov     [rsp+178h+var_140], r13
0x140165035  mov     [rsp+178h+var_148], 0Dh
0x14016503c  jmp     loc_140165247
0x140165041  test    rdx, rdx
0x140165044  jz      loc_140165138
0x14016504a  test    ebx, ebx
0x14016504c  jz      short loc_14016505E
0x14016504e  lea     eax, [rbx-1]
0x140165051  test    ebx, eax
0x140165053  jnz     short loc_14016505E
0x140165055  test    r15d, r15d
0x140165058  jz      loc_140165138
0x14016505e  mov     rdx, cs:WPP_GLOBAL_Control
0x140165065  cmp     rdx, rsi
0x140165068  jz      short loc_140165081
0x14016506a  mov     eax, [rdx+2Ch]
0x14016506d  test    r14b, al
0x140165070  jz      short loc_140165081
0x140165072  mov     r12d, 2
0x140165078  cmp     [rdx+29h], r12b
0x14016507c  mov     r12b, r14b
0x14016507f  jnb     short loc_140165084
0x140165081  mov     r12b, dil
0x140165084  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14016508b  setnz   r13b
0x14016508f  test    r12b, r12b
0x140165092  jnz     short loc_140165099
0x140165094  test    r13b, r13b
0x140165097  jz      short loc_1401650DC
0x140165099  call    cs:__imp_W32GetUserSessionState
0x1401650a0  nop     dword ptr [rax+rax+00h]
0x1401650a5  mov     r9, [rax+4BD0h]
0x1401650ac  mov     [rsp+178h+var_128], r15d
0x1401650b1  mov     [rsp+178h+var_130], ebx
0x1401650b5  mov     rax, [rsp+178h+var_100]
0x1401650ba  mov     [rsp+178h+var_138], rax
0x1401650bf  mov     r8b, r13b
0x1401650c2  mov     dl, r12b
0x1401650c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1401650cc  mov     rcx, [rcx+18h]
0x1401650d0  call    WPP_RECORDER_AND_TRACE_SF_qDd
0x1401650d5  lea     rcx, WPP_RECORDER_INITIALIZED
0x1401650dc  mov     rdx, cs:WPP_GLOBAL_Control
0x1401650e3  cmp     rdx, rsi
0x1401650e6  jz      short loc_1401650F9
0x1401650e8  mov     eax, [rdx+2Ch]
0x1401650eb  test    r14b, al
0x1401650ee  jz      short loc_1401650F9
0x1401650f0  cmp     byte ptr [rdx+29h], 4
0x1401650f4  mov     bl, r14b
0x1401650f7  jnb     short loc_1401650FC
0x1401650f9  mov     bl, dil
0x1401650fc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140165103  setnz   sil
0x140165107  test    bl, bl
0x140165109  jnz     short loc_140165114
0x14016510b  test    sil, sil
0x14016510e  jz      loc_14016526D
0x140165114  call    cs:__imp_W32GetUserSessionState
0x14016511b  nop     dword ptr [rax+rax+00h]
0x140165120  lea     r13, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140165127  mov     [rsp+178h+var_140], r13
0x14016512c  mov     [rsp+178h+var_148], 0Fh
0x140165133  jmp     loc_140165247
0x140165138  mov     r12b, dil
0x14016513b  mov     dword ptr [rsp+178h+var_F8], r12d
0x140165143  test    r15d, r15d
0x140165146  jz      loc_1401652A8
0x14016514c  test    bl, 20h
0x14016514f  jnz     loc_140165277
0x140165155  mov     rdx, cs:WPP_GLOBAL_Control
0x14016515c  cmp     rdx, rsi
0x14016515f  jz      short loc_14016517A
0x140165161  mov     eax, [rdx+2Ch]
0x140165164  test    r14b, al
0x140165167  jz      short loc_14016517A
0x140165169  mov     r12d, 2
0x14016516f  cmp     [rdx+29h], r12b
0x140165173  jb      short loc_140165180
0x140165175  mov     r13b, r14b
0x140165178  jmp     short loc_140165183
0x14016517a  mov     r12d, 2
0x140165180  mov     r13b, dil
0x140165183  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14016518a  setnz   al
0x14016518d  mov     [rsp+178h+var_118], al
0x140165191  test    r13b, r13b
0x140165194  jnz     short loc_14016519A
0x140165196  test    al, al
0x140165198  jz      short loc_1401651F4
0x14016519a  call    cs:__imp_W32GetUserSessionState
0x1401651a1  nop     dword ptr [rax+rax+00h]
0x1401651a6  mov     r9, [rax+4BD0h]
0x1401651ad  mov     [rsp+178h+var_130], r15d
0x1401651b2  mov     dword ptr [rsp+178h+var_138], ebx
0x1401651b6  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401651bd  mov     [rsp+178h+var_140], r15
0x1401651c2  mov     [rsp+178h+var_148], 10h
0x1401651c9  mov     [rsp+178h+var_150], r14d
0x1401651ce  mov     byte ptr [rsp+178h+TableContext], r12b
0x1401651d3  mov     r8b, [rsp+178h+var_118]
0x1401651d8  mov     dl, r13b
0x1401651db  mov     rcx, cs:WPP_GLOBAL_Control
0x1401651e2  mov     rcx, [rcx+18h]
0x1401651e6  call    WPP_RECORDER_AND_TRACE_SF_DD
0x1401651eb  lea     rcx, WPP_RECORDER_INITIALIZED
0x1401651f2  jmp     short loc_1401651FB
0x1401651f4  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401651fb  mov     rdx, cs:WPP_GLOBAL_Control
0x140165202  cmp     rdx, rsi
0x140165205  jz      short loc_140165218
0x140165207  mov     eax, [rdx+2Ch]
0x14016520a  test    r14b, al
0x14016520d  jz      short loc_140165218
0x14016520f  cmp     byte ptr [rdx+29h], 4
0x140165213  mov     bl, r14b
0x140165216  jnb     short loc_14016521B
0x140165218  mov     bl, dil
0x14016521b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140165222  setnz   sil
0x140165226  test    bl, bl
0x140165228  jnz     short loc_14016522F
0x14016522a  test    sil, sil
0x14016522d  jz      short loc_14016526D
0x14016522f  call    cs:__imp_W32GetUserSessionState
0x140165236  nop     dword ptr [rax+rax+00h]
0x14016523b  mov     [rsp+178h+var_140], r15
0x140165240  mov     [rsp+178h+var_148], 11h
0x140165247  mov     [rsp+178h+var_150], r14d
0x14016524c  mov     rcx, cs:WPP_GLOBAL_Control
0x140165253  mov     byte ptr [rsp+178h+TableContext], 4
0x140165258  mov     r9, [rax+4BD0h]
0x14016525f  mov     r8b, sil
0x140165262  mov     dl, bl
0x140165264  mov     rcx, [rcx+18h]
0x140165268  call    WPP_RECORDER_AND_TRACE_SF_
0x14016526d  mov     eax, 0C000000Dh
0x140165272  jmp     loc_140165E0C
0x140165277  cmp     [rsp+178h+arg_58], edi
0x14016527e  jz      short loc_1401652A8
0x140165280  mov     ecx, ebx
0x140165282  call    rimCheckForRegistrationConflicts
0x140165287  cmp     eax, r14d
0x14016528a  jnz     short loc_140165296
0x14016528c  mov     eax, 0C0000022h
0x140165291  jmp     loc_140165E0C
0x140165296  movzx   r12d, r12b
0x14016529a  test    eax, eax
0x14016529c  cmovz   r12d, r14d
0x1401652a0  mov     dword ptr [rsp+178h+var_F8], r12d
0x1401652a8  mov     edx, r13d; Limit
0x1401652ab  xor     ecx, ecx; Count
0x1401652ad  call    CreateKernelSemaphore
0x1401652b2  mov     rsi, rax
0x1401652b5  mov     qword ptr [rsp+178h+DestinationString.Length], rax
0x1401652bd  test    rax, rax
0x1401652c0  jnz     short loc_1401652CC
0x1401652c2  mov     eax, 0C0000017h
0x1401652c7  jmp     loc_140165E0C
0x1401652cc  mov     edx, 7FFFFFFFh; Limit
0x1401652d1  xor     ecx, ecx; Count
0x1401652d3  call    CreateKernelSemaphore
0x1401652d8  mov     r15, rax
0x1401652db  mov     [rsp+178h+var_D0], rax
0x1401652e3  test    rax, rax
0x1401652e6  jnz     short loc_1401652F2
0x1401652e8  mov     rcx, rsi; Buffer
0x1401652eb  call    GreDeleteFastMutex
  ... truncated ...
```
