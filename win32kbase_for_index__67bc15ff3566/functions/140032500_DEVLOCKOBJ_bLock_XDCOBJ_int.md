# DEVLOCKOBJ::bLock(XDCOBJ &,int)

- ea: `0x140032500`
- end: `0x14003337f`
- name: `?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z`
- size: `3711`
- prototype: `__int64 __fastcall(DEVLOCKOBJ *__hidden this, struct XDCOBJ *, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140022740`

## callees

- `0x1400182b4`
- `0x14001a3a0`
- `0x14001e034`
- `0x14002006c`
- `0x140020bcc`
- `0x140025858`
- `0x140031fa0`
- `0x140032300`
- `0x140032500`
- `0x140033390`
- `0x140033a6c`
- `0x140033ea4`
- `0x140033f80`
- `0x1400341ac`
- `0x140034238`
- `0x140036794`
- `0x140079330`
- `0x140111520`
- `0x140120e30`
- `0x14012e228`
- `0x140192b70`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140033076`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400330bb`
- `ntoskrnl!PsGetCurrentProcess` at `0x140033151`
- `ntoskrnl!PsGetCurrentProcess` at `0x140033076`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400330bb`
- `ntoskrnl!PsGetCurrentProcess` at `0x140033151`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032c90`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032feb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032c90`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140032feb`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400329ec`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140032a56`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400329ec`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140032a56`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140033085`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400330a2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400330ca`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400330e7`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140033160`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003317d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140033085`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400330a2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400330ca`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400330e7`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140033160`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14003317d`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400331c2`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400331c2`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140033093`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400330d8`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003316e`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140033093`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400330d8`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14003316e`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400329d5`
- `ntoskrnl!KeIsAttachedProcess` at `0x140032a3f`
- `ntoskrnl!KeIsAttachedProcess` at `0x140032b61`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400329d5`
- `ntoskrnl!KeIsAttachedProcess` at `0x140032a3f`
- `ntoskrnl!KeIsAttachedProcess` at `0x140032b61`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032ee3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032ee3`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14003267a`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14003267a`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x1400331ae`
- `ntoskrnl!PsIsWin32KFilterAuditEnabled` at `0x1400331ae`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140032b52`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140032b52`
- `ntoskrnl!KeReleaseMutex` at `0x140032f10`
- `ntoskrnl!KeReleaseMutex` at `0x140032f10`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140032648`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400327a9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400327d8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140032805`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003293a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140032e0f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140032e42`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140032648`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400327a9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400327d8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140032805`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003293a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140032e0f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140032e42`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140032555`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003257a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140032a98`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140032ac5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140032d14`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140032d39`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140032555`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003257a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140032a98`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140032ac5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140032d14`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140032d39`
- `WIN32K!W32GetSessionState` at `0x140032750`
- `WIN32K!W32GetSessionState` at `0x140032750`

## pseudocode

```c
__int64 __fastcall DEVLOCKOBJ::bLock(DEVLOCKOBJ *this, struct _ERESOURCE ***a2, int a3)
{
  __int64 v6; // rcx
  int v7; // r8d
  int (*v8)(void); // rax
  void (__fastcall *v9)(DEVLOCKOBJ *, _QWORD); // rax
  int v10; // r12d
  struct _ERESOURCE **v11; // r14
  bool v12; // zf
  struct _GRETHREAD *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  struct _GRETHREAD *v17; // rdi
  int v18; // ebp
  unsigned __int64 v19; // r9
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // ecx
  int v24; // r8d
  struct _GRETHREAD *v25; // rax
  __int64 v26; // r9
  struct _GRETHREAD *v27; // rdi
  __int64 v28; // rdx
  char v29; // cl
  struct _ERESOURCE **v30; // rdx
  struct _ERESOURCE *v31; // rdi
  int ExclusiveWaiters; // ecx
  __int64 v33; // rcx
  __int64 v34; // rbp
  __int64 SessionState; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  struct _ERESOURCE **v43; // r8
  __int64 v44; // r9
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 *v54; // rax
  int v55; // ecx
  int v56; // r8d
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rcx
  struct _ERESOURCE **v60; // rdi
  _DWORD *v61; // rdx
  __int64 v62; // rax
  __int64 v63; // rbp
  struct _ERESOURCE *v64; // rdi
  __int64 v65; // rcx
  struct _ERESOURCE *v66; // r15
  struct _KTHREAD *CurrentThread; // rbp
  __int64 ThreadWin32Thread; // rax
  _QWORD *v69; // rdx
  struct _ERESOURCE *v70; // r14
  struct _KTHREAD *v71; // rbp
  __int64 v72; // rax
  _QWORD *v73; // rdx
  int (*v74)(void); // rax
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 (__fastcall *v77)(DEVLOCKOBJ *, struct XDCOBJ *); // rax
  int v78; // ecx
  int v79; // eax
  __int64 v80; // rax
  DCOBJ *v81; // r14
  int *v82; // rax
  __int64 v83; // rbp
  __int64 v84; // r13
  int v85; // r15d
  unsigned int v86; // edi
  __int64 *CurrentThreadWin32ThreadAndEnterCriticalRegion; // rsi
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // rax
  __int64 v91; // rbx
  __int64 v92; // rcx
  int v93; // r12d
  __int64 v94; // rax
  unsigned int *v95; // rsi
  unsigned int v96; // ecx
  struct _KTHREAD *v97; // rbx
  __int64 v98; // rax
  __int64 *v99; // rdi
  __int64 v100; // rbx
  __int64 v101; // rax
  int v102; // eax
  __int64 v103; // rcx
  int (*v105)(void); // rax
  __int64 (__fastcall *v106)(struct XDCOBJ *, char *, char *, char *); // rax
  int v107; // eax
  struct _ERESOURCE *v108; // r8
  __int64 *v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 *v112; // rax
  __int64 v113; // rax
  __int64 v114; // rax
  unsigned __int64 i; // rcx
  int v116; // eax
  int v117; // eax
  __int64 v118; // rax
  int v119; // edi
  __int64 v120; // rax
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  ThreadRestrictNewHandlesRegion *v124; // rcx
  __int64 v125; // rax
  int v126; // ebx
  __int64 v127; // rax
  unsigned __int64 j; // rcx
  int v129; // eax
  unsigned int *v130; // [rsp+30h] [rbp-58h] BYREF
  int v131; // [rsp+38h] [rbp-50h]
  __int16 v132; // [rsp+3Ch] [rbp-4Ch]
  __int64 v133; // [rsp+40h] [rbp-48h]
  __int64 v134; // [rsp+90h] [rbp+8h] BYREF
  __int64 v135; // [rsp+98h] [rbp+10h]
  unsigned int v136; // [rsp+A0h] [rbp+18h]

  *((_DWORD *)this + 6) = 1;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 19) = **a2;
  if ( !a3 )
  {
    if ( (v105 = *(int (**)(void))(*(_QWORD *)(((__int64 (*)(void))W32GetWin32kBaseApiSetTable)() + 24) + 2032LL)) == 0
      || v105() < 0
      || ((v106 = *(__int64 (__fastcall **)(struct XDCOBJ *, char *, char *, char *))(*(_QWORD *)(((__int64 (*)(void))W32GetWin32kBaseApiSetTable)()
                                                                                                + 24)
                                                                                    + 2040LL)) == 0
        ? (v107 = 0)
        : (v107 = v106((struct XDCOBJ *)a2, (char *)this + 144, (char *)this + 136, (char *)this + 28)),
          v107 != 1) )
    {
      *((_DWORD *)this + 6) &= ~1u;
      return 0;
    }
  }
  v6 = *(_QWORD *)(((__int64 (*)(void))W32GetWin32kBaseApiSetTable)() + 24);
  v8 = *(int (**)(void))(v6 + 768);
  if ( v8 )
  {
    if ( v8() >= 0 )
    {
      v6 = *(_QWORD *)(((__int64 (*)(void))W32GetWin32kBaseApiSetTable)() + 24);
      v9 = *(void (__fastcall **)(DEVLOCKOBJ *, _QWORD))(v6 + 776);
      if ( v9 )
        v9(this, 0);
    }
  }
  if ( a3 == 1 )
    *((_DWORD *)this + 6) |= 0x20000u;
  v10 = 0;
  v11 = a2[2];
  if ( (*((_DWORD *)*a2 + 9) & 0x200) == 0 )
  {
    v109 = (__int64 *)((__int64 (*)(void))PsGetCurrentThreadWin32Thread)();
    if ( !v109 || (v110 = *v109) == 0 || (v111 = v110 + 8) == 0 || !*(_DWORD *)(v111 + 340) )
    {
      *((_DWORD *)this + 6) |= 0x80000u;
      v112 = (__int64 *)((__int64 (*)(void))PsGetCurrentThreadWin32Thread)();
      if ( v112 )
      {
        v113 = *v112;
        if ( v113 )
        {
          v114 = v113 + 8;
          if ( v114 )
            ++*(_DWORD *)(v114 + 340);
        }
      }
    }
    goto LABEL_51;
  }
  v12 = LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) == 0;
  *((_QWORD *)this + 1) = *v11 + 6;
  if ( !v12 && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
    McTemplateK0pz_EtwWriteTransfer(
      v6,
      (unsigned int)LockAcquireShared,
      v7,
      *(_DWORD *)v11 + 624,
      (__int64)L"DynamicModeChange");
  EngAcquireSemaphoreShared((HSEMAPHORE)&(*v11)[6]);
  v13 = GreGetCurrentThreadCrossSessionCheck();
  v17 = v13;
  v18 = 38;
  v19 = 0xFFFFFFDFFFFFFFFFuLL;
  if ( v13 )
  {
    v16 = *(_QWORD *)v13;
    LOBYTE(v14) = (*(_QWORD *)v13 & 0xFFFFFFDFFFFFFFFEuLL) != 0;
    if ( ((unsigned __int8)v14 & ((*(_QWORD *)v13 & 2) == 0)) != 0 )
    {
      LODWORD(v14) = 38;
      for ( i = 0; i < 0x40; ++i )
      {
        v116 = i;
        if ( ((1LL << i) & 0xFFFFFFDFFFFFFFFFuLL & v16) == 0 )
          v116 = v14;
        v14 = (unsigned int)v116;
      }
      if ( v116 > 1 && v116 != 38 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(i, (unsigned int)v116, v16, 0xFFFFFFDFFFFFFFFFuLL);
    }
    v15 = *((unsigned __int8 *)v17 + 9);
    *((_BYTE *)v17 + 9) = v15 + 1;
    if ( !(_BYTE)v15 )
      *(_QWORD *)v17 |= 2uLL;
  }
  *((_DWORD *)this + 6) |= 8u;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v15, v14, v16, v19);
  if ( (!CurrentThreadWin32Thread
     || (v21 = *CurrentThreadWin32Thread) == 0
     || (v22 = v21 + 8) == 0
     || !*(_DWORD *)(v22 + 340))
    && !ExIsResourceAcquiredSharedLite(*v11 + 11) )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        v23,
        (unsigned int)LockAcquireShared,
        v24,
        *(_DWORD *)v11 + 1144,
        (__int64)L"GreLock");
    EngAcquireSemaphoreShared((HSEMAPHORE)&(*v11)[11]);
    v25 = GreGetCurrentThreadCrossSessionCheck();
    v27 = v25;
    if ( v25 )
    {
      v28 = *(_QWORD *)v25;
      if ( (*(_QWORD *)v25 & 0xFFFFFFDFFFFFFFFCuLL) != 0 && (v28 & 4) == 0 )
      {
        for ( j = 0; j < 0x40; ++j )
        {
          v129 = j;
          if ( ((1LL << j) & 0xFFFFFFDFFFFFFFFFuLL & v28) == 0 )
            v129 = v18;
          v18 = v129;
        }
        if ( v129 > 2 && v129 != 38 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(j, v28, 0xFFFFFFDFFFFFFFFFuLL, v26);
      }
      v29 = *((_BYTE *)v27 + 10);
      *((_BYTE *)v27 + 10) = v29 + 1;
      if ( !v29 )
        *(_QWORD *)v27 |= 4uLL;
    }
    v10 = 1;
  }
  v30 = *a2;
  if ( ((__int64)(*a2)[122]->SystemResourcesList.Flink & 1) != 0 || (*((_DWORD *)v30 + 9) & 0x8000) != 0 )
  {
    v31 = v30[6];
    ExclusiveWaiters = (int)v31->ExclusiveWaiters;
    if ( (ExclusiveWaiters & 0x1000001) == 1 )
    {
      if ( HIDWORD(v31[25].SystemResourcesList.Flink) == 5
        || (ExclusiveWaiters & 0x20000) != 0
        || (v33 = *(_QWORD *)&v31[24].NumberOfSharedWaiters, ((v33 + 4) & 0xFFFFFFFFFFFFFFFBuLL) != 0)
        && (*(_DWORD *)(v33 + 160) & 0x800000) != 0 )
      {
        v34 = *(_QWORD *)&v31->ActiveCount;
        SessionState = W32GetSessionState();
        if ( ((__int64)v31[20].SharedWaiters & 0x400) == 0 )
        {
          LOBYTE(v36) = ((__int64)v31->ExclusiveWaiters & 0x48000000) == 0;
          LOBYTE(v37) = ((__int64)v31[17].ExclusiveWaiters & 0x8000000) == 0;
          if ( ((unsigned __int8)v36 & (unsigned __int8)v37) != 0
            && (*(_DWORD *)(v34 + 40) & 0x1000000) == 0
            && *(_DWORD *)(*(_QWORD *)(SessionState + 88) + 4232LL) )
          {
            goto LABEL_36;
          }
        }
      }
    }
    v30 = *a2;
  }
  v108 = v30[8];
  *(_QWORD *)this = v108;
  *((_QWORD *)this + 2) = (*a2)[6];
  if ( v10 == 1 && v108 == &(*v11)[11] )
  {
    GreReleaseSemaphoreShared<2,>(v11);
    v10 = 0;
  }
  if ( *(struct _ERESOURCE **)this == &(*v11)[11] )
  {
    *((_DWORD *)this + 6) |= 0x100000u;
    GreAcquireSemaphore<2,>(v11);
  }
  else
  {
    GreAcquireSemaphore<8,PDEVOBJ>(*((_QWORD *)this + 2));
  }
  v36 = *((unsigned int *)this + 6);
  if ( (v36 & 0x200) == 0 && (*((_DWORD *)*a2 + 9) & 0x4000) != 0 )
  {
    LODWORD(v36) = v36 | 0x200;
    *((_DWORD *)this + 6) = v36;
  }
LABEL_36:
  v40 = (__int64 *)PsGetCurrentThreadWin32Thread(v37, v36, v38, v39);
  if ( !v40 || (v45 = *v40) == 0 || (v46 = v45 + 8) == 0 || !*(_DWORD *)(v46 + 340) )
  {
    *((_DWORD *)this + 6) |= 0x1000u;
    v47 = (__int64 *)PsGetCurrentThreadWin32Thread(v42, v41, v43, v44);
    if ( v47 )
    {
      v52 = *v47;
      if ( v52 )
      {
        v53 = v52 + 8;
        if ( v53 )
        {
          *(_QWORD *)(v53 + 304) = 0;
          *(_QWORD *)(v53 + 296) = 0;
        }
      }
    }
    v54 = (__int64 *)PsGetCurrentThreadWin32Thread(v49, v48, v50, v51);
    if ( v54 )
    {
      v57 = *v54;
      if ( v57 )
      {
        v58 = v57 + 8;
        if ( v58 )
          ++*(_DWORD *)(v58 + 340);
      }
    }
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        v55,
        (unsigned int)LockAcquireShared,
        v56,
        *(_DWORD *)v11 + 728,
        (__int64)L"DCVisRgn");
    EngAcquireSemaphoreShared((HSEMAPHORE)&(*v11)[7]);
    GrepAcquireLockValidate<3>();
  }
  v59 = *((unsigned int *)*a2 + 9);
  if ( (v59 & 0x1000) != 0 && (v59 & 0x4000) == 0 )
  {
    if ( (*((_DWORD *)this + 6) & 0x1000) != 0 )
      GreReleaseSemaphoreShared<3,>(v11);
    if ( v10 )
    {
LABEL_159:
      GreReleaseSemaphoreShared<2,>(v11);
      *((_DWORD *)this + 6) &= ~1u;
      return 0;
    }
LABEL_155:
    *((_DWORD *)this + 6) &= ~1u;
    return 0;
  }
LABEL_51:
  if ( (*((_DWORD *)this + 6) & 0x1000) != 0 )
  {
    if ( (*((_DWORD *)*a2 + 9) & 0x80000) != 0 )
    {
      if ( *((_QWORD *)this + 1) )
        GreReleaseSemaphoreShared<3,>(v11);
      if ( v10 )
        goto LABEL_159;
      goto LABEL_155;
    }
  }
  else if ( *((_QWORD *)this + 1) )
  {
    goto LABEL_56;
  }
  v59 = (__int64)*a2;
  if ( (*((_DWORD *)*a2 + 9) & 0x10) != 0 && !(unsigned int)DC::bCompute((DC *)v59) )
  {
    if ( *((_QWORD *)this + 1) )
      GreReleaseSemaphoreShared<3,>(v11);
    if ( v10 )
      GreReleaseSemaphoreShared<2,>(v11);
    goto LABEL_155;
  }
LABEL_56:
  v60 = *a2;
  if ( !(*a2)[146] || ((_DWORD)v60[5] & 2) == 0 || !(unsigned int)DC::bDpiScaledSurface((DC *)*a2) )
  {
    v61 = v60 + 5;
    if ( !v60[144] && (!v60[145] || (*v61 & 2) == 0 || !(unsigned int)DC::bDpiScaledSurface((DC *)v60)) && !v60[143] )
      goto LABEL_155;
  }
  if ( (*((_DWORD *)this + 6) & 0x20000) == 0 )
  {
    LOBYTE(v59) = (*((_DWORD *)this + 6) & 0x1000) != 0;
    if ( ((unsigned __int8)v59 & ((*((_DWORD *)v60 + 9) & 0x200) != 0)) != 0 )
    {
      if ( !*((_QWORD *)this + 17) )
      {
        v59 = (__int64)((*v61 & 1) != 0 ? v60 + 128 : v60 + 127);
        v43 = v60 + 128;
        *((_DWORD *)v60 + 256) = *(_DWORD *)v59;
        *((_DWORD *)v60 + 257) = *(_DWORD *)(v59 + 4);
        *((_DWORD *)v60 + 262) = *((_DWORD *)v60 + 258);
        *((_DWORD *)v60 + 263) = *((_DWORD *)v60 + 259);
        *((_DWORD *)v60 + 264) = *((_DWORD *)v60 + 260);
        *((_DWORD *)v60 + 265) = *((_DWORD *)v60 + 261);
        *v61 |= 1u;
        if ( (*((_DWORD *)v60 + 9) & 0x4000) != 0 )
        {
          v59 = (__int64)v60[62];
          if ( *(_QWORD *)(v59 + 280) || (*(_DWORD *)(v59 + 148) & 1) != 0 )
          {
            KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(v59 + 344) + 64LL), UserRequest, 0, 0, 0);
            ++HIDWORD(v60[62][3].ExclusiveWaiters);
            KeReleaseMutex(*((PRKMUTEX *)v60[62][3].SharedWaiters + 8), 0);
          }
        }
      }
      v62 = PsGetCurrentThreadWin32Thread(v59, v61, v43, v44);
      if ( v62 )
      {
        if ( *(_QWORD *)v62 )
        {
          v63 = *(_QWORD *)v62 + 8LL;
          if ( *(_QWORD *)v62 != -8 )
          {
            *(_QWORD *)(*(_QWORD *)v62 + 304LL) = *a2;
            if ( (*((_DWORD *)*a2 + 9) & 0x4000) == 0 )
            {
              *(_DWORD *)(v63 + 336) |= 1u;
              (*a2)[247] = 0;
              v64 = *v11;
              EngAcquireSemaphoreShared((HSEMAPHORE)&(*v11)[8]);
              GrepAcquireLockValidate<14>();
              *(_DWORD *)(v63 + 348) = *((_DWORD *)v11 + 1098);
              GreReleaseSemaphoreCommon<14,void (*)(HSEMAPHORE__ *)>(v65, &v64[8]);
            }
          }
        }
      }
    }
  }
  if ( *((_QWORD *)this + 1) && (*((_DWORD *)this + 6) & 0x1000) != 0 )
  {
    v66 = *v11;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        v59,
        (unsigned int)LockRelease,
        (_DWORD)v43,
        (_DWORD)v66 + 728,
        (__int64)L"DCVisRgn");
    CurrentThread = KeGetCurrentThread();
    if ( !(unsigned __int8)KeIsAttachedProcess(v59, v61)
      || (CurrentProcess = PsGetCurrentProcess(),
          ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = PsGetThreadWin32Thread(CurrentThread);
      if ( ThreadWin32Thread )
      {
        if ( *(_QWORD *)ThreadWin32Thread )
        {
          v69 = (_QWORD *)(*(_QWORD *)ThreadWin32Thread + 8LL);
          if ( *(_QWORD *)ThreadWin32Thread != -8 )
          {
            v12 = (*(_BYTE *)(*(_QWORD *)ThreadWin32Thread + 19LL))-- == 1;
            if ( v12 )
              *v69 &= ~8uLL;
          }
        }
      }
    }
    GreReleaseSemaphoreSharedInternal((HSEMAPHORE)&v66[7]);
  }
  if ( v10 )
  {
    v70 = *v11;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        v59,
        (unsigned int)LockRelease,
        (_DWORD)v43,
        (_DWORD)v70 + 1144,
        (__int64)L"GreLock");
    v71 = KeGetCurrentThread();
    if ( !(unsigned __int8)KeIsAttachedProcess(v59, v61)
      || (v118 = PsGetCurrentProcess(),
          v119 = PsGetProcessSessionIdEx(v118),
          v120 = PsGetCurrentThreadProcess(),
          v119 == (unsigned int)PsGetProcessSessionIdEx(v120)) )
    {
      v72 = PsGetThreadWin32Thread(v71);
      if ( v72 )
      {
        if ( *(_QWORD *)v72 )
        {
          v73 = (_QWORD *)(*(_QWORD *)v72 + 8LL);
          if ( *(_QWORD *)v72 != -8 )
          {
            v12 = (*(_BYTE *)(*(_QWORD *)v72 + 18LL))-- == 1;
            if ( v12 )
              *v73 &= ~4uLL;
          }
        }
      }
    }
    GreReleaseSemaphoreSharedInternal((HSEMAPHORE)&v70[11]);
  }
  if ( (*((_DWORD *)this + 6) & 0x20000) != 0 )
    return 1;
  v74 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v59, v61) + 24) + 768LL);
  if ( v74 && v74() >= 0 )
  {
    v77 = *(__int64 (__fastcall **)(DEVLOCKOBJ *, struct XDCOBJ *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v76, v75)
                                                                              + 24)
                                                                  + 776LL);
    if ( v77 )
      v78 = v77(this, (struct XDCOBJ *)a2);
    else
      v78 = 0;
    v79 = *((_DWORD *)this + 6);
    if ( v78 )
    {
      if ( (v79 & 0x81000) == 0 )
        return 1;
      v80 = *((_QWORD *)this + 4);
      v81 = (DEVLOCKOBJ *)((char *)this + 32);
      if ( v80 )
      {
LABEL_118:
        *(_DWORD *)(v80 + 40) |= 2u;
        *((_BYTE *)v81 + 96) = 1;
        return 1;
      }
      v82 = (int *)*a2;
      v83 = 0;
      v84 = *((_QWORD *)this + 6);
      v132 = 0;
      v133 = v84;
      v85 = *v82;
      v86 = (unsigned __int16)*v82 | ((unsigned int)*v82 >> 8) & 0xFF0000;
      v134 = 0;
      CurrentThreadWin32ThreadAndEnterCriticalRegion = (__int64 *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v134);
      if ( (!(unsigned __int8)KeIsAttachedProcess(v89, v88)
         || (v125 = PsGetCurrentProcess(),
             v126 = PsGetProcessSessionIdEx(v125),
             v127 = PsGetCurrentThreadProcess(),
             v126 == (unsigned int)PsGetProcessSessionIdEx(v127)))
        && CurrentThreadWin32ThreadAndEnterCriticalRegion
        && (v90 = *CurrentThreadWin32ThreadAndEnterCriticalRegion) != 0 )
      {
        v91 = v90 + 8;
        if ( v90 != -8 )
        {
          v135 = *(_QWORD *)(v90 + 72);
          goto LABEL_101;
        }
      }
      else
      {
        v91 = 0;
      }
      v135 = 0;
LABEL_101:
      v92 = *(_QWORD *)(v84 + 8);
      v93 = 1;
      v131 = 1;
      v94 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v92 + 40LL))(v92, v86);
      v130 = (unsigned int *)v94;
      v95 = (unsigned int *)v94;
      if ( !v94 )
      {
        v93 = 0;
        KeLeaveCriticalRegion();
        goto LABEL_104;
      }
      _m_prefetchw((const void *)(v94 + 8));
      v96 = *(_DWORD *)(v94 + 8) & 0xFFFFFFFE;
      v136 = v96;
      if ( v96 == (v134 & 0xFFFFFFFC) || !v96 || v135 && (v117 = UMPDGetThreadClientPID(v91), v136 == v117) )
      {
        if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v84 + 8) + 96LL))(
                           *(_QWORD *)(v84 + 8),
                           *v95)
                       + 14)
            & 0x20) == 0
          || v91
          && (v124 = *(ThreadRestrictNewHandlesRegion **)(v91 + 328)) != 0
          && *((_BYTE *)v124 + 80)
          && ThreadRestrictNewHandlesRegion::InRegion(v124, v86) )
        {
LABEL_104:
          if ( v93 )
          {
            if ( *((_BYTE *)v95 + 14) == 1 && *((_WORD *)v95 + 6) == HIWORD(v85) )
            {
              v97 = KeGetCurrentThread();
              v98 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v84 + 8) + 96LL))(
                      *(_QWORD *)(v84 + 8),
                      *v95);
              v83 = v98;
              if ( !*(_WORD *)(v98 + 12) || *(struct _KTHREAD **)(v98 + 16) == v97 )
              {
                _InterlockedIncrement16((volatile signed __int16 *)(v98 + 12));
                *(_QWORD *)(v98 + 16) = v97;
              }
              else
              {
                v83 = 0;
              }
            }
            v99 = *(__int64 **)(v84 + 8);
            v100 = *v99;
            v101 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v99 + 96))(v99, *v95);
            (*(void (__fastcall **)(__int64 *, __int64))(v100 + 48))(v99, v101);
            KeLeaveCriticalRegion();
          }
          *(_QWORD *)v81 = v83;
          if ( v83 )
          {
            if ( *(_DWORD *)(v83 + 2136) )
            {
              _InterlockedDecrement16((volatile signed __int16 *)(v83 + 12));
              *(_QWORD *)v81 = 0;
              goto LABEL_116;
            }
          }
          else if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction() != 1
                 && (unsigned __int8)PsIsWin32KFilterAuditEnabled() )
          {
            PsGetWin32KFilterSet();
          }
          if ( *(_QWORD *)v81 )
          {
            v102 = DCOBJ::SaveAttributes(v81);
            v103 = *(_QWORD *)v81;
            if ( v102 )
            {
              if ( (*(_DWORD *)(v103 + 520) & 4) != 0 )
                DC::vMarkTransformDirty((DC *)v103);
            }
            else
            {
              _InterlockedDecrement16((volatile signed __int16 *)(v103 + 12));
              *(_QWORD *)v81 = 0;
            }
          }
LABEL_116:
          v80 = *(_QWORD *)v81;
          if ( *(_QWORD *)v81 )
          {
            *((_BYTE *)v81 + 97) = 0;
            goto LABEL_118;
          }
          return 1;
        }
        LOBYTE(v132) = 1;
      }
      HANDLELOCK::vUnlock((HANDLELOCK *)&v130);
      v95 = v130;
      v93 = v131;
      v84 = v133;
      goto LABEL_104;
    }
  }
  else
  {
    v79 = *((_DWORD *)this + 6);
  }
  *((_DWORD *)this + 6) = v79 & 0xFFFFFFFE;
  return 0;
}

```

## disassembly

```asm
0x140032500  push    rbx
0x140032502  push    rsi
0x140032503  push    rdi
0x140032504  push    r13
0x140032506  push    r14
0x140032508  push    r15
0x14003250a  sub     rsp, 58h
0x14003250e  xor     r13d, r13d
0x140032511  mov     dword ptr [rcx+18h], 1
0x140032518  mov     [rcx], r13
0x14003251b  mov     rbx, rcx
0x14003251e  mov     [rcx+8], r13
0x140032522  mov     edi, r8d
0x140032525  mov     [rcx+10h], r13
0x140032529  mov     rsi, rdx
0x14003252c  mov     [rcx+90h], r13
0x140032533  mov     [rcx+88h], r13
0x14003253a  mov     rax, [rdx]
0x14003253d  mov     rcx, [rax]
0x140032540  mov     [rbx+98h], rcx
0x140032547  test    r8d, r8d
0x14003254a  jz      loc_140032D14
0x140032550  mov     [rsp+88h+var_38], r12
0x140032555  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003255c  nop     dword ptr [rax+rax+00h]
0x140032561  mov     rcx, [rax+18h]
0x140032565  mov     rax, [rcx+300h]
0x14003256c  test    rax, rax
0x14003256f  jz      short loc_1400325A0
0x140032571  call    _guard_dispatch_icall
0x140032576  test    eax, eax
0x140032578  js      short loc_1400325A0
0x14003257a  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140032581  nop     dword ptr [rax+rax+00h]
0x140032586  mov     rcx, [rax+18h]
0x14003258a  mov     rax, [rcx+308h]
0x140032591  test    rax, rax
0x140032594  jz      short loc_1400325A0
0x140032596  xor     edx, edx
0x140032598  mov     rcx, rbx
0x14003259b  call    _guard_dispatch_icall
0x1400325a0  cmp     edi, 1
0x1400325a3  jnz     short loc_1400325AC
0x1400325a5  or      dword ptr [rbx+18h], 20000h
0x1400325ac  mov     rax, [rsi]
0x1400325af  mov     r12d, r13d
0x1400325b2  mov     r14, [rsi+10h]
0x1400325b6  mov     [rsp+88h+arg_18], rbp
0x1400325be  test    dword ptr [rax+24h], 200h
0x1400325c5  jz      loc_140032E0F
0x1400325cb  mov     rax, [r14]
0x1400325ce  add     rax, 270h
0x1400325d4  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, r13d
0x1400325db  mov     [rbx+8], rax
0x1400325df  jnz     loc_140033200
0x1400325e5  mov     rcx, [r14]
0x1400325e8  add     rcx, 270h; hsem
0x1400325ef  call    EngAcquireSemaphoreShared
0x1400325f4  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x1400325f9  mov     rdi, rax
0x1400325fc  mov     ebp, 26h ; '&'
0x140032601  mov     r9, 0FFFFFFDFFFFFFFFFh
0x14003260b  test    rax, rax
0x14003260e  jz      short loc_140032644
0x140032610  mov     r8, [rax]
0x140032613  mov     rax, 0FFFFFFDFFFFFFFFEh
0x14003261d  test    rax, r8
0x140032620  setnz   dl
0x140032623  test    r8b, 2
0x140032627  setz    cl
0x14003262a  test    cl, dl
0x14003262c  jnz     loc_140032F7A
0x140032632  movzx   ecx, byte ptr [rdi+9]
0x140032636  lea     eax, [rcx+1]
0x140032639  mov     [rdi+9], al
0x14003263c  test    cl, cl
0x14003263e  jnz     short loc_140032644
0x140032640  or      qword ptr [rdi], 2
0x140032644  or      dword ptr [rbx+18h], 8
0x140032648  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14003264f  nop     dword ptr [rax+rax+00h]
0x140032654  test    rax, rax
0x140032657  jz      short loc_140032670
0x140032659  mov     rax, [rax]
0x14003265c  test    rax, rax
0x14003265f  jz      short loc_140032670
0x140032661  add     rax, 8
0x140032665  jz      short loc_140032670
0x140032667  cmp     [rax+154h], r13d
0x14003266e  jnz     short loc_1400326E1
0x140032670  mov     rcx, [r14]
0x140032673  add     rcx, 478h; Resource
0x14003267a  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140032681  nop     dword ptr [rax+rax+00h]
0x140032686  test    eax, eax
0x140032688  jnz     short loc_1400326E1
0x14003268a  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, r13d
0x140032691  jnz     loc_140033234
0x140032697  mov     rcx, [r14]
0x14003269a  add     rcx, 478h; hsem
0x1400326a1  call    EngAcquireSemaphoreShared
0x1400326a6  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x1400326ab  mov     rdi, rax
0x1400326ae  test    rax, rax
0x1400326b1  jz      short loc_1400326DB
0x1400326b3  mov     rdx, [rax]
0x1400326b6  mov     rax, 0FFFFFFDFFFFFFFFCh
0x1400326c0  test    rax, rdx
0x1400326c3  jnz     loc_140033268
0x1400326c9  movzx   ecx, byte ptr [rdi+0Ah]
0x1400326cd  lea     eax, [rcx+1]
0x1400326d0  mov     [rdi+0Ah], al
0x1400326d3  test    cl, cl
0x1400326d5  jnz     short loc_1400326DB
0x1400326d7  or      qword ptr [rdi], 4
0x1400326db  mov     r12d, 1
0x1400326e1  mov     rdx, [rsi]
0x1400326e4  mov     rax, [rdx+3D0h]
0x1400326eb  mov     ecx, [rax]
0x1400326ed  test    cl, 1
0x1400326f0  jnz     short loc_1400326FF
0x1400326f2  test    dword ptr [rdx+24h], 8000h
0x1400326f9  jz      loc_140032D94
0x1400326ff  mov     rdi, [rdx+30h]
0x140032703  mov     ecx, [rdi+28h]
0x140032706  mov     eax, ecx
0x140032708  and     eax, 1000001h
0x14003270d  cmp     eax, 1
0x140032710  jnz     loc_140032D91
0x140032716  cmp     dword ptr [rdi+0A2Ch], 5
0x14003271d  jz      short loc_14003274C
0x14003271f  bt      ecx, 11h
0x140032723  jb      short loc_14003274C
0x140032725  mov     rcx, [rdi+0A08h]
0x14003272c  lea     rax, [rcx+4]
0x140032730  test    rax, 0FFFFFFFFFFFFFFFBh
0x140032736  jz      loc_140032D91
0x14003273c  mov     eax, [rcx+0A0h]
0x140032742  bt      eax, 17h
0x140032746  jnb     loc_140032D91
0x14003274c  mov     rbp, [rdi+18h]
0x140032750  call    cs:__imp_W32GetSessionState
0x140032757  nop     dword ptr [rax+rax+00h]
0x14003275c  test    dword ptr [rdi+840h], 400h
0x140032766  jnz     loc_140032D91
0x14003276c  test    dword ptr [rdi+28h], 48000000h
0x140032773  setz    dl
0x140032776  test    dword ptr [rdi+710h], 8000000h
0x140032780  setz    cl
0x140032783  test    cl, dl
0x140032785  jz      loc_140032D91
0x14003278b  test    dword ptr [rbp+28h], 1000000h
0x140032792  jnz     loc_140032D91
0x140032798  mov     rax, [rax+58h]
0x14003279c  cmp     [rax+1088h], r13d
0x1400327a3  jz      loc_140032D91
0x1400327a9  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400327b0  nop     dword ptr [rax+rax+00h]
0x1400327b5  test    rax, rax
0x1400327b8  jz      short loc_1400327D1
0x1400327ba  mov     rax, [rax]
0x1400327bd  test    rax, rax
0x1400327c0  jz      short loc_1400327D1
0x1400327c2  add     rax, 8
0x1400327c6  jz      short loc_1400327D1
0x1400327c8  cmp     [rax+154h], r13d
0x1400327cf  jnz     short loc_14003284B
0x1400327d1  or      dword ptr [rbx+18h], 1000h
0x1400327d8  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400327df  nop     dword ptr [rax+rax+00h]
0x1400327e4  test    rax, rax
0x1400327e7  jz      short loc_140032805
0x1400327e9  mov     rax, [rax]
0x1400327ec  test    rax, rax
0x1400327ef  jz      short loc_140032805
0x1400327f1  add     rax, 8
0x1400327f5  jz      short loc_140032805
0x1400327f7  mov     [rax+130h], r13
0x1400327fe  mov     [rax+128h], r13
0x140032805  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14003280c  nop     dword ptr [rax+rax+00h]
0x140032811  test    rax, rax
0x140032814  jz      short loc_14003282A
0x140032816  mov     rax, [rax]
0x140032819  test    rax, rax
0x14003281c  jz      short loc_14003282A
0x14003281e  add     rax, 8
0x140032822  jz      short loc_14003282A
0x140032824  inc     dword ptr [rax+154h]
0x14003282a  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, r13d
0x140032831  jnz     loc_1400332B8
0x140032837  mov     rcx, [r14]
0x14003283a  add     rcx, 2D8h; hsem
0x140032841  call    EngAcquireSemaphoreShared
0x140032846  call    ??$GrepAcquireLockValidate@$02@@YAXXZ; GrepAcquireLockValidate<3>(void)
0x14003284b  mov     rax, [rsi]
0x14003284e  mov     ecx, [rax+24h]
0x140032851  bt      ecx, 0Ch
0x140032855  jb      loc_1400332EC
0x14003285b  test    dword ptr [rbx+18h], 1000h
0x140032862  jnz     short loc_14003286C
0x140032864  cmp     [rbx+8], r13
0x140032868  jnz     short loc_14003288A
0x14003286a  jmp     short loc_14003287C
0x14003286c  mov     rax, [rsi]
0x14003286f  test    dword ptr [rax+24h], 80000h
0x140032876  jnz     loc_140032F54
0x14003287c  mov     rcx, [rsi]; this
0x14003287f  mov     eax, [rcx+24h]
0x140032882  test    al, 10h
0x140032884  jnz     loc_140032F21
0x14003288a  mov     rdi, [rsi]
0x14003288d  cmp     [rdi+490h], r13
0x140032894  jnz     loc_140032FFC
0x14003289a  lea     rdx, [rdi+28h]
0x14003289e  cmp     [rdi+480h], r13
0x1400328a5  jz      loc_140032E78
0x1400328ab  mov     eax, [rbx+18h]
0x1400328ae  bt      eax, 11h
0x1400328b2  jb      loc_1400329AD
0x1400328b8  bt      eax, 0Ch
0x1400328bc  setb    cl
0x1400328bf  test    dword ptr [rdi+24h], 200h
0x1400328c6  setnz   al
0x1400328c9  test    al, cl
0x1400328cb  jz      loc_1400329AD
0x1400328d1  cmp     [rbx+88h], r13
0x1400328d8  jnz     short loc_14003293A
0x1400328da  mov     eax, [rdx]
0x1400328dc  test    al, 1
0x1400328de  jz      loc_140032E97
0x1400328e4  lea     rcx, [rdi+400h]
0x1400328eb  mov     r8, rcx
0x1400328ee  mov     eax, [rcx]
0x1400328f0  mov     [r8], eax
0x1400328f3  mov     eax, [rcx+4]
0x1400328f6  mov     [r8+4], eax
0x1400328fa  mov     eax, [rdi+408h]
0x140032900  mov     [rdi+418h], eax
0x140032906  mov     eax, [rdi+40Ch]
0x14003290c  mov     [rdi+41Ch], eax
0x140032912  mov     eax, [rdi+410h]
0x140032918  mov     [rdi+420h], eax
0x14003291e  mov     eax, [rdi+414h]
0x140032924  mov     [rdi+424h], eax
0x14003292a  or      dword ptr [rdx], 1
0x14003292d  test    dword ptr [rdi+24h], 4000h
0x140032934  jnz     loc_140032EAA
0x14003293a  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140032941  nop     dword ptr [rax+rax+00h]
0x140032946  test    rax, rax
0x140032949  jz      short loc_1400329AD
0x14003294b  mov     rbp, [rax]
0x14003294e  test    rbp, rbp
0x140032951  jz      short loc_1400329AD
0x140032953  add     rbp, 8
0x140032957  jz      short loc_1400329AD
0x140032959  mov     rax, [rsi]
0x14003295c  mov     [rbp+128h], rax
0x140032963  mov     rax, [rsi]
0x140032966  test    dword ptr [rax+24h], 4000h
0x14003296d  jnz     short loc_1400329AD
0x14003296f  or      dword ptr [rbp+150h], 1
0x140032976  mov     rax, [rsi]
0x140032979  mov     [rax+7B8h], r13
0x140032980  mov     rdi, [r14]
0x140032983  lea     rcx, [rdi+340h]; hsem
0x14003298a  call    EngAcquireSemaphoreShared
0x14003298f  call    ??$GrepAcquireLockValidate@$0O@@@YAXXZ; GrepAcquireLockValidate<14>(void)
0x140032994  mov     eax, [r14+1128h]
0x14003299b  lea     rdx, [rdi+340h]
0x1400329a2  mov     [rbp+15Ch], eax
0x1400329a8  call    ??$GreReleaseSemaphoreCommon@$0O@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<14,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x1400329ad  cmp     [rbx+8], r13
0x1400329b1  jz      short loc_140032A21
0x1400329b3  test    dword ptr [rbx+18h], 1000h
0x1400329ba  jz      short loc_140032A21
0x1400329bc  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, r13d
0x1400329c3  mov     r15, [r14]
0x1400329c6  jnz     loc_1400332FB
0x1400329cc  mov     rbp, gs:188h
0x1400329d5  call    cs:__imp_KeIsAttachedProcess
0x1400329dc  nop     dword ptr [rax+rax+00h]
0x1400329e1  test    al, al
0x1400329e3  jnz     loc_1400330BB
0x1400329e9  mov     rcx, rbp
0x1400329ec  call    cs:__imp_PsGetThreadWin32Thread
0x1400329f3  nop     dword ptr [rax+rax+00h]
0x1400329f8  test    rax, rax
0x1400329fb  jz      short loc_140032A15
0x1400329fd  mov     rdx, [rax]
0x140032a00  test    rdx, rdx
0x140032a03  jz      short loc_140032A15
0x140032a05  add     rdx, 8
0x140032a09  jz      short loc_140032A15
0x140032a0b  add     byte ptr [rdx+0Bh], 0FFh
0x140032a0f  jnz     short loc_140032A15
0x140032a11  and     qword ptr [rdx], 0FFFFFFFFFFFFFFF7h
0x140032a15  lea     rcx, [r15+2D8h]; HSEMAPHORE
0x140032a1c  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
  ... truncated ...
```
