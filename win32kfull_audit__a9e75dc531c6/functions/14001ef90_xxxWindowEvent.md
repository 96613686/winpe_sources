# xxxWindowEvent

- ea: `0x14001ef90`
- end: `0x14001fdf2`
- name: `xxxWindowEvent`
- size: `3682`
- prototype: `void __fastcall(unsigned int, struct tagWND *, int, int, int)`
- caller_count: `51`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004380`
- `0x1400082e8`
- `0x140008a0c`
- `0x14000a6dc`
- `0x14000aa2c`
- `0x14000ab10`
- `0x14000add0`
- `0x14000b128`
- `0x14000ba54`
- `0x14001ee40`
- `0x140020230`
- `0x140023ef8`
- `0x140035ec0`
- `0x14003636c`
- `0x140038550`
- `0x140094974`
- `0x1400bc9a4`
- `0x1400be164`
- `0x1400ebc3c`
- `0x14010e028`
- `0x14013f4b4`
- `0x14016e684`
- `0x140173778`
- `0x140183674`
- `0x140183eb4`
- `0x14018597c`
- `0x1401a8c50`
- `0x1401c0f48`
- `0x1401ca020`
- `0x1401f7318`
- `0x1401f8064`
- `0x1401f81cc`
- `0x14020b284`
- `0x14020b6e0`
- `0x1402139d4`
- `0x14021c534`
- `0x140227c80`
- `0x14022c0e8`
- `0x14024d548`
- `0x1402595e8`
- `0x14026d770`
- `0x14026dd2c`
- `0x14027d004`
- `0x140290eac`
- `0x1402dcb54`
- `0x1402ed19c`
- `0x1402eee78`
- `0x1402ef59c`
- `0x1402effd8`
- `0x1402f2af8`

## callees

- `0x14001ef90`
- `0x14001fdf8`
- `0x1400c5cf8`
- `0x1400c7cd8`
- `0x1402665f0`
- `0x14029345c`
- `0x140343080`

## import_xrefs

- `ntoskrnl!PsGetThreadProcessId` at `0x14001f1b6`
- `ntoskrnl!PsGetThreadProcessId` at `0x14001f1b6`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14001f2a8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14001f7f6`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14001f2a8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14001f7f6`
- `ntoskrnl!PsGetThreadId` at `0x14001f197`
- `ntoskrnl!PsGetThreadId` at `0x14001f893`
- `ntoskrnl!PsGetThreadId` at `0x14001f197`
- `ntoskrnl!PsGetThreadId` at `0x14001f893`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f2ba`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f2ba`
- `ntoskrnl!KeBugCheckEx` at `0x14001f9a5`
- `ntoskrnl!KeBugCheckEx` at `0x14001fbbf`
- `ntoskrnl!KeBugCheckEx` at `0x14001f9a5`
- `ntoskrnl!KeBugCheckEx` at `0x14001fbbf`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f114`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f133`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f23c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f39c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f3dd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f91c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f95d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001fb43`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f114`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f133`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f23c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f39c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f3dd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f91c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001f95d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001fb43`
- `win32kbase!?getDLT@DLT_WINEVENT@@SA?AW4DomainLockType@@XZ` at `0x14001efb8`
- `win32kbase!?getDLT@DLT_WINEVENT@@SA?AW4DomainLockType@@XZ` at `0x14001efb8`
- `win32kbase!?getDLT@DLT_HANDLEMANAGER@@SA?AW4DomainLockType@@XZ` at `0x14001f73e`
- `win32kbase!?getDLT@DLT_HANDLEMANAGER@@SA?AW4DomainLockType@@XZ` at `0x14001f73e`
- `win32kbase!ReferenceW32Thread` at `0x14001f280`
- `win32kbase!ReferenceW32Thread` at `0x14001f280`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x14001efc6`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x14001f74c`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x14001efc6`
- `win32kbase!?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z` at `0x14001f74c`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x14001f795`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x14001fcce`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x14001f795`
- `win32kbase!?LockShared@tagDomLock@@QEBAXXZ` at `0x14001fcce`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x14001f00f`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x14001fd02`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x14001f00f`
- `win32kbase!?LockExclusive@tagDomLock@@QEBAXXZ` at `0x14001fd02`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x14001f4cc`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x14001f8ef`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x14001fc37`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x14001f4cc`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x14001f8ef`
- `win32kbase!?UnLockShared@tagDomLock@@QEBAXXZ` at `0x14001fc37`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x14001f442`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x14001f7d7`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x14001fc26`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x14001f442`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x14001f7d7`
- `win32kbase!?UnLockExclusive@tagDomLock@@QEBAXXZ` at `0x14001fc26`
- `win32kbase!_HMPheFromObject` at `0x14001f7a8`
- `win32kbase!_HMPheFromObject` at `0x14001f7a8`
- `win32kbase!HMLockObject` at `0x14001f230`
- `win32kbase!HMLockObject` at `0x14001f230`
- `win32kbase!HMUnlockObject` at `0x14001f41d`
- `win32kbase!HMUnlockObject` at `0x14001f41d`
- `win32kbase!HMAssignmentLock` at `0x14001f85f`
- `win32kbase!HMAssignmentLock` at `0x14001f85f`
- `win32kbase!Win32AllocPoolZInit` at `0x14001f82e`
- `win32kbase!Win32AllocPoolZInit` at `0x14001f82e`
- `WIN32K!W32GetUserSessionState` at `0x14001efda`
- `WIN32K!W32GetUserSessionState` at `0x14001f0da`
- `WIN32K!W32GetUserSessionState` at `0x14001f1c6`
- `WIN32K!W32GetUserSessionState` at `0x14001f295`
- `WIN32K!W32GetUserSessionState` at `0x14001f2c9`
- `WIN32K!W32GetUserSessionState` at `0x14001f317`
- `WIN32K!W32GetUserSessionState` at `0x14001f361`
- `WIN32K!W32GetUserSessionState` at `0x14001f760`
- `WIN32K!W32GetUserSessionState` at `0x14001f7e3`
- `WIN32K!W32GetUserSessionState` at `0x14001f808`
- `WIN32K!W32GetUserSessionState` at `0x14001efda`
- `WIN32K!W32GetUserSessionState` at `0x14001f0da`
- `WIN32K!W32GetUserSessionState` at `0x14001f1c6`
- `WIN32K!W32GetUserSessionState` at `0x14001f295`
- `WIN32K!W32GetUserSessionState` at `0x14001f2c9`
- `WIN32K!W32GetUserSessionState` at `0x14001f317`
- `WIN32K!W32GetUserSessionState` at `0x14001f361`
- `WIN32K!W32GetUserSessionState` at `0x14001f760`
- `WIN32K!W32GetUserSessionState` at `0x14001f7e3`
- `WIN32K!W32GetUserSessionState` at `0x14001f808`

## pseudocode

```c
void __fastcall xxxWindowEvent(unsigned int a1, struct tagWND *a2, int a3, int a4, int a5)
{
  unsigned int DLT; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 UserSessionState; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  tagDomLock *v16; // rcx
  int v17; // eax
  unsigned int v18; // r12d
  int v19; // r14d
  BOOL v20; // esi
  __int64 v21; // rdx
  int v22; // eax
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  unsigned __int64 *v26; // rax
  unsigned __int64 v27; // rdi
  int v28; // ecx
  unsigned __int64 v29; // r13
  HANDLE ThreadId; // rax
  struct _KTHREAD *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rax
  __int64 v37; // rdx
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // rbx
  __int64 *v40; // rax
  __int64 v41; // rcx
  __int64 i; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rax
  unsigned int CurrentThreadId; // edi
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 *v52; // rbx
  int v53; // edx
  unsigned int v54; // r12d
  __int64 v55; // rdi
  unsigned __int64 v56; // rcx
  __int64 v57; // rdx
  int v58; // eax
  __int64 *v59; // rax
  __int64 v60; // rcx
  ULONG_PTR *v61; // rax
  ULONG_PTR v62; // rdx
  ULONG_PTR *v63; // rcx
  ULONG_PTR v64; // rcx
  struct tagTHREADINFO *v65; // rbx
  bool v66; // zf
  __int64 k; // rbx
  __int64 v68; // rdi
  HANDLE v69; // rax
  int v70; // eax
  unsigned int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // rdx
  tagDomLock *v77; // rcx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // rax
  __int64 v86; // r14
  __int64 v87; // rsi
  struct tagWND *v88; // rax
  unsigned int v89; // eax
  __int64 *v90; // rax
  __int64 *v91; // rax
  __int64 v92; // rcx
  ULONG_PTR *v93; // rax
  unsigned __int64 v94; // kr00_8
  struct tagWND *v95; // rax
  _QWORD *v96; // rax
  int v97; // eax
  int v98; // [rsp+40h] [rbp-C0h]
  unsigned int v99; // [rsp+44h] [rbp-BCh]
  unsigned int v102; // [rsp+50h] [rbp-B0h]
  struct tagWND *v103; // [rsp+58h] [rbp-A8h]
  __int64 v104; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v105; // [rsp+68h] [rbp-98h]
  __int64 v106; // [rsp+70h] [rbp-90h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+78h] [rbp-88h] BYREF
  tagDomLock *DomainLockRef; // [rsp+88h] [rbp-78h] BYREF
  char v109; // [rsp+90h] [rbp-70h]
  __int64 v110; // [rsp+98h] [rbp-68h]
  char v111; // [rsp+A0h] [rbp-60h]
  __int64 v112; // [rsp+A8h] [rbp-58h]
  char v113; // [rsp+B0h] [rbp-50h]
  __int64 j; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v115; // [rsp+C0h] [rbp-40h]
  _QWORD v116[2]; // [rsp+D0h] [rbp-30h] BYREF
  tagDomLock *v117; // [rsp+E0h] [rbp-20h] BYREF
  char v118; // [rsp+E8h] [rbp-18h]
  __int64 v119; // [rsp+F0h] [rbp-10h]
  char v120; // [rsp+F8h] [rbp-8h]
  __int64 v121; // [rsp+100h] [rbp+0h]
  char v122; // [rsp+108h] [rbp+8h]
  HANDLE ThreadProcessId; // [rsp+110h] [rbp+10h]
  __int64 v124; // [rsp+118h] [rbp+18h]
  HANDLE v125; // [rsp+120h] [rbp+20h]

  v103 = a2;
  DLT = DLT_WINEVENT::getDLT();
  DomainLockRef = (tagDomLock *)GetDomainLockRef(DLT);
  v109 = 1;
  UserSessionState = W32GetUserSessionState(v9, v8, v10, v11);
  v16 = DomainLockRef;
  v110 = UserSessionState + 42184;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  if ( DomainLockRef )
    tagDomLock::LockExclusive(DomainLockRef);
  v113 = 1;
  if ( a1 == 2147483408 )
  {
    v17 = 1;
    v98 = 1;
    goto LABEL_16;
  }
  if ( a1 - 2147483409 < 2 )
    v17 = 2;
  else
    v17 = 0;
  v98 = v17;
  if ( a1 <= 0x80000002 )
  {
    v98 = v17;
    if ( a1 != -2147483646 )
    {
      if ( a1 != 2147483393 && a1 != 2147483392 )
      {
        if ( a1 == 0x80000000 )
        {
          v98 = v17;
          goto LABEL_12;
        }
        if ( a1 == -2147483647 )
        {
LABEL_12:
          v18 = 256;
          v19 = 1;
          goto LABEL_17;
        }
        goto LABEL_16;
      }
      v98 = v17;
      v18 = 1024;
      goto LABEL_179;
    }
    v98 = v17;
LABEL_226:
    v18 = 512;
LABEL_179:
    v19 = 1;
    goto LABEL_17;
  }
  if ( a1 == -2147483645 )
    goto LABEL_226;
  if ( a1 != -2147483643 && a1 != -2147483644 )
  {
LABEL_16:
    v18 = 0;
    v19 = 0;
    goto LABEL_17;
  }
  v18 = 4096;
  v19 = 1;
LABEL_17:
  v20 = v17 != 0;
  v21 = *(unsigned int *)(*(_QWORD *)(W32GetUserSessionState(v16, v13, v14, v15) + 19704) + 1892LL);
  if ( a1 != 32779 )
  {
    if ( a1 <= 0x800A )
    {
      if ( a1 == 32778 )
      {
        v22 = 32;
        goto LABEL_19;
      }
      if ( a1 > 0x4001 )
      {
        if ( a1 == 32773 )
        {
          v22 = 4;
          goto LABEL_19;
        }
        if ( a1 <= 0x8005 )
        {
          switch ( a1 )
          {
            case 0x4002u:
            case 0x4003u:
            case 0x4004u:
            case 0x4005u:
            case 0x4006u:
            case 0x4007u:
              goto LABEL_169;
            default:
              goto LABEL_82;
          }
        }
      }
      else
      {
        if ( a1 == 16385 )
        {
LABEL_169:
          v22 = 2;
          goto LABEL_19;
        }
        if ( a1 == 4 || a1 == 5 || a1 - 6 < 2 )
        {
          v22 = 1;
          goto LABEL_19;
        }
      }
      goto LABEL_82;
    }
    if ( a1 <= 0x7FFFFF10 )
    {
      if ( a1 != 2147483408 )
      {
        if ( a1 == 32780 )
        {
          v22 = 8;
          goto LABEL_19;
        }
        if ( a1 == 32782 )
        {
          v22 = 16;
          goto LABEL_19;
        }
        goto LABEL_82;
      }
    }
    else
    {
      if ( a1 > 0x80000002 )
      {
        switch ( a1 )
        {
          case 0x80000003:
            goto LABEL_98;
          case 0x80000005:
          case 0x80000004:
            v22 = 512;
            goto LABEL_19;
          case 0x80000006:
          case 0x80000007:
            goto LABEL_98;
        }
LABEL_82:
        v22 = 0x8000;
        goto LABEL_19;
      }
      if ( a1 != -2147483646 )
      {
        if ( a1 > 0x7FFFFF30 )
        {
          if ( a1 != 0x80000000 && a1 != -2147483647 )
            goto LABEL_82;
        }
        else if ( a1 != 2147483440 && a1 != 2147483409 && a1 != 2147483410 && a1 != 2147483424 )
        {
          goto LABEL_82;
        }
      }
    }
LABEL_98:
    v22 = 256;
    goto LABEL_19;
  }
  v22 = 64;
LABEL_19:
  if ( ((unsigned int)v21 & v22) == 0 && !v20 && !v19 )
  {
LABEL_74:
    DomainShared<>::DomainExclusive<DLT_HOOK>::ObjectLock<>::~ObjectLock<>(&DomainLockRef);
    return;
  }
  CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread(0x140000000uLL, v21);
  if ( !CurrentThreadWin32Thread || !*CurrentThreadWin32Thread )
  {
    if ( DomainLockRef )
      tagDomLock::UnLockExclusive(DomainLockRef);
    return;
  }
  v26 = (unsigned __int64 *)PsGetCurrentThreadWin32Thread(v25, v24);
  if ( v26 )
    v27 = *v26;
  else
    v27 = 0;
  v115 = v27;
  if ( (a5 & 0x11) != 0x11 && a2 && *(char *)(*((_QWORD *)a2 + 5) + 19LL) < 0 )
    goto LABEL_74;
  v28 = a5 | 2;
  if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v27 + 520), 0, 0) & 0x10000001) == 0 )
    v28 = a5;
  v99 = v28;
  if ( (v28 & 1) != 0 && a2 )
  {
    v29 = *((_QWORD *)a2 + 2);
    v95 = 0;
    if ( (v28 & 0x10) == 0 )
      v95 = a2;
    v103 = v95;
  }
  else
  {
    v29 = v27;
  }
  ThreadId = PsGetThreadId(*(PETHREAD *)v29);
  v31 = *(struct _KTHREAD **)v29;
  v125 = ThreadId;
  v124 = *(_QWORD *)(v29 + 456);
  ThreadProcessId = PsGetThreadProcessId(v31);
  v36 = W32GetUserSessionState(v33, v32, v34, v35);
  v116[0] = v36;
  if ( (v99 & 0x20) != 0 )
  {
    LODWORD(v39) = _InterlockedIncrement((volatile signed __int32 *)(v36 + 70576));
  }
  else
  {
    v38 = 0xFFFFF78000000004uLL;
    v39 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
  }
  BugCheckParameter3[0] = *(_QWORD *)(v27 + 448);
  *(_QWORD *)(v27 + 448) = BugCheckParameter3;
  v102 = v39;
  BugCheckParameter3[1] = (ULONG_PTR)v103;
  if ( v103 )
    HMLockObject(v103);
  v40 = (__int64 *)PsGetCurrentThreadWin32Thread(v38, v37);
  if ( v40 )
    v41 = *v40;
  else
    v41 = 0;
  v104 = *(_QWORD *)(v41 + 376);
  *(_QWORD *)(v41 + 376) = &v104;
  v106 = (__int64)Win32RawLockedW32Thread::Deref;
  v105 = v29;
  ReferenceW32Thread(v29);
  v45 = v99;
  if ( (v99 & 2) == 0 )
  {
    v46 = W32GetUserSessionState(i, v99, v43, v44);
    if ( ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v46 + 42144)) != 1 )
      __int2c();
    CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
    v52 = (__int64 *)(W32GetUserSessionState(v49, v48, v50, v51) + 70600);
    for ( i = *v52; (__int64 *)i != v52; i = *(_QWORD *)i )
    {
      v53 = *(_DWORD *)(i + 56);
      if ( (v53 & 2) != 0 && *(_DWORD *)(i + 48) == CurrentThreadId )
      {
        v66 = *(_DWORD *)(i + 24) == 0;
        *(_DWORD *)(i + 56) = v53 & 0xFFFFFFFD;
        if ( v66 )
          xxxProcessNotifyWinEvent(i);
        else
          xxxProcessTSFEvent((struct tagNOTIFY *)i);
        i = (__int64)v52;
      }
    }
    v45 = v99;
    LODWORD(v39) = v102;
  }
  if ( v19 )
  {
    i = *(unsigned int *)(*(_QWORD *)(v29 + 456) + 808LL);
    if ( (i & 0x1000000) != 0 )
      xxxDoLocalTSFWork(a1, v103, a3, a4, v45, v18, (struct tagTHREADINFO *)v29, v39);
  }
  if ( v20 )
  {
    v54 = v102;
    v55 = *(_QWORD *)(W32GetUserSessionState(i, v45, v43, v44) + 36200);
    for ( j = v55; v55; j = v55 )
    {
      if ( (*(_DWORD *)(v55 + 808) & 0x1000000) != 0 )
      {
        v65 = *(struct tagTHREADINFO **)(v55 + 328);
        if ( v65 )
        {
          do
          {
            if ( (v98 & *(_DWORD *)(*((_QWORD *)v65 + 60) + 24LL)) != 0 )
              CreateAndPostTSFNotify(a1, v103, a3, a4, v65, (struct tagTHREADINFO *)v29, v102);
            v65 = (struct tagTHREADINFO *)*((_QWORD *)v65 + 87);
          }
          while ( v65 );
          v55 = j;
        }
      }
      v55 = *(_QWORD *)(v55 + 368);
    }
  }
  else
  {
    v54 = v102;
  }
  v56 = *(_QWORD *)(W32GetUserSessionState(i, v45, v43, v44) + 19704);
  v57 = *(unsigned int *)(v56 + 1892);
  if ( a1 != 32779 )
  {
    if ( a1 <= 0x800A )
    {
      if ( a1 == 32778 )
      {
        v58 = 32;
        goto LABEL_49;
      }
      if ( a1 > 0x4001 )
      {
        if ( a1 == 32773 )
        {
          v58 = 4;
          goto LABEL_49;
        }
        if ( a1 <= 0x8005 )
        {
          v94 = v56;
          v56 = 0x140000000uLL;
          switch ( a1 )
          {
            case 0x4002u:
            case 0x4003u:
            case 0x4004u:
            case 0x4005u:
            case 0x4006u:
            case 0x4007u:
              goto LABEL_173;
            default:
              v56 = v94;
              goto LABEL_90;
          }
        }
      }
      else
      {
        if ( a1 == 16385 )
        {
LABEL_173:
          v58 = 2;
          goto LABEL_49;
        }
        if ( a1 == 4 || a1 == 5 || a1 - 6 < 2 )
        {
          v58 = 1;
          goto LABEL_49;
        }
      }
      goto LABEL_90;
    }
    if ( a1 <= 0x7FFFFF10 )
    {
      if ( a1 != 2147483408 )
      {
        if ( a1 == 32780 )
        {
          v58 = 8;
          goto LABEL_49;
        }
        if ( a1 == 32782 )
        {
          v58 = 16;
          goto LABEL_49;
        }
        goto LABEL_90;
      }
    }
    else
    {
      if ( a1 > 0x80000002 )
      {
        switch ( a1 )
        {
          case 0x80000003:
            goto LABEL_106;
          case 0x80000005:
          case 0x80000004:
            v58 = 512;
            goto LABEL_49;
          case 0x80000006:
          case 0x80000007:
            goto LABEL_106;
        }
LABEL_90:
        v58 = 0x8000;
        goto LABEL_49;
      }
      if ( a1 != -2147483646 )
      {
        if ( a1 > 0x7FFFFF30 )
        {
          if ( a1 != 0x80000000 && a1 != -2147483647 )
            goto LABEL_90;
        }
        else if ( a1 != 2147483440 && a1 != 2147483409 && a1 != 2147483410 && a1 != 2147483424 )
        {
          goto LABEL_90;
        }
      }
    }
LABEL_106:
    v58 = 256;
    goto LABEL_49;
  }
  v58 = 64;
LABEL_49:
  if ( ((unsigned int)v57 & v58) != 0 )
  {
    for ( k = *(_QWORD *)(v116[0] + 70584LL); k; k = v68 )
    {
      v56 = *(unsigned int *)(k + 40);
      v68 = *(_QWORD *)(k + 24);
      if ( (v56 & 1) == 0 && *(_DWORD *)(k + 32) <= a1 && a1 <= *(_DWORD *)(k + 36) )
      {
        v69 = *(HANDLE *)(k + 48);
        if ( !v69 || v69 == ThreadProcessId )
        {
          if ( (v56 & 4) == 0 || (v57 = v124, v124 != *(_QWORD *)(*(_QWORD *)(k + 16) + 456LL)) )
          {
            v70 = *(_DWORD *)(k + 56);
            if ( (!v70 || v70 == (_DWORD)v125) && ((v56 & 2) == 0 || v29 != *(_QWORD *)(k + 16)) )
            {
              v56 = *(_QWORD *)(*(_QWORD *)(k + 16) + 488LL);
              if ( v56 == *(_QWORD *)(v115 + 488) || a1 == 32 || v56 == *(_QWORD *)(v29 + 488) && a1 + 2147483646 <= 1 )
              {
                v71 = DLT_HANDLEMANAGER::getDLT();
                v117 = (tagDomLock *)GetDomainLockRef(v71);
                v118 = 0;
                v119 = W32GetUserSessionState(v73, v72, v74, v75) + 42184;
                v120 = 0;
                v121 = 0;
                v122 = 0;
                if ( v117 )
                {
                  if ( v118 )
                    tagDomLock::LockExclusive(v117);
                  else
                    tagDomLock::LockShared(v117);
                }
                v122 = 1;
                if ( (*(_BYTE *)(_HMPheFromObject(k) + 25) & 1) != 0 )
                {
                  DomainShared<>::DomainExclusive<DLT_HOOK>::ObjectLock<>::~ObjectLock<>(&v117);
                  break;
                }
                if ( v122 )
                {
                  v77 = v117;
                  if ( v117 )
                  {
                    if ( v118 )
                      tagDomLock::UnLockExclusive(v117);
                    else
                      tagDomLock::UnLockShared(v117);
                  }
                }
                v80 = W32GetUserSessionState(v77, v76, v78, v79);
                if ( ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v80 + 42144)) != 1 )
                  __int2c();
                v85 = W32GetUserSessionState(v82, v81, v83, v84);
                v86 = v85;
                if ( *(_DWORD *)(v85 + 70688) )
                {
                  v87 = Win32AllocPoolZInit(72, 2037281621);
                  if ( !v87 )
                    break;
                }
                else
                {
                  *(_DWORD *)(v85 + 70688) = 1;
                  v87 = v85 + 70616;
                }
                *(_QWORD *)(v87 + 16) = 0;
                v116[0] = v87 + 16;
                v116[1] = k;
                HMAssignmentLock(v116, 0);
                v88 = v103;
                if ( v103 )
                  v88 = *(struct tagWND **)v103;
                *(_QWORD *)(v87 + 32) = v88;
                *(_DWORD *)(v87 + 40) = a3;
                *(_DWORD *)(v87 + 44) = a4;
                *(_DWORD *)(v87 + 28) = a1;
                v89 = (unsigned int)PsGetThreadId(*(PETHREAD *)v29);
                *(_DWORD *)(v87 + 52) = v54;
                *(_DWORD *)(v87 + 48) = v89;
                *(_DWORD *)(v87 + 56) = 0;
                *(_DWORD *)(v87 + 24) = 0;
                *(_DWORD *)(v87 + 56) = ~(unsigned __int8)(*(_DWORD *)(k + 40) >> 1) & 4;
                *(_QWORD *)(v87 + 8) = v87;
                *(_QWORD *)v87 = v87;
                *(_QWORD *)(v87 + 64) = 0;
                if ( (*(_DWORD *)(k + 40) & 8) != 0 && a1 + 2147483646 <= 3 )
                {
                  v96 = (_QWORD *)PsGetCurrentThreadWin32Thread(0, v57);
                  if ( v96 )
                    v96 = (_QWORD *)*v96;
                  if ( *(_QWORD **)(k + 16) != v96 )
                    *(_DWORD *)(v87 + 56) |= 4u;
                }
                v90 = *(__int64 **)(v86 + 70608);
                v56 = v86 + 70600;
                if ( *v90 != v86 + 70600 )
                  __fastfail(3u);
                *(_QWORD *)(v87 + 8) = v90;
                *(_QWORD *)v87 = v56;
                *v90 = v87;
                *(_QWORD *)(v86 + 70608) = v87;
                *(_DWORD *)(v87 + 56) |= v99;
                v97 = *(_DWORD *)(v87 + 56);
                if ( (v97 & 4) != 0 )
                {
                  v97 &= ~2u;
                  *(_DWORD *)(v87 + 56) = v97;
                }
                if ( (v97 & 2) == 0 )
                  v68 = xxxProcessNotifyWinEvent(v87);
              }
            }
          }
        }
      }
    }
    if ( v106 != -1 )
    {
      v91 = (__int64 *)PsGetCurrentThreadWin32Thread(v56, v57);
      if ( v91 )
        v92 = *v91;
      else
        v92 = 0;
      *(_QWORD *)(v92 + 376) = v104;
      v56 = v105;
      if ( v105 )
        ((void (*)(void))v106)();
      v106 = -1;
    }
    v93 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v56, v57);
    if ( v93 )
      v62 = *v93;
    else
      v62 = 0;
    v63 = *(ULONG_PTR **)(v62 + 448);
    if ( v63 != BugCheckParameter3 )
      KeBugCheckEx(0x164u, 0x3Bu, v62, (ULONG_PTR)BugCheckParameter3, 0);
  }
  else
  {
    if ( v106 != -1 )
    {
      v59 = (__int64 *)PsGetCurrentThreadWin32Thread(v56, v57);
      if ( v59 )
        v60 = *v59;
      else
        v60 = 0;
      *(_QWORD *)(v60 + 376) = v104;
      v56 = v105;
      if ( v105 )
        ((void (*)(void))v106)();
      v106 = -1;
    }
    v61 = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v56, v57);
    if ( v61 )
      v62 = *v61;
    else
      v62 = 0;
    v63 = *(ULONG_PTR **)(v62 + 448);
    if ( v63 != BugCheckParameter3 )
      KeBugCheckEx(0x164u, 0x3Bu, v62, (ULONG_PTR)BugCheckParameter3, 0);
  }
  *(_QWORD *)(v62 + 448) = *v63;
  v64 = v63[1];
  if ( v64 )
    HMUnlockObject(v64);
  if ( v113 && DomainLockRef )
  {
    if ( v109 )
      tagDomLock::UnLockExclusive(DomainLockRef);
    else
      tagDomLock::UnLockShared(DomainLockRef);
  }
}

```

## disassembly

```asm
0x14001ef90  push    rbp
0x14001ef92  push    rbx
0x14001ef93  push    rsi
0x14001ef94  push    rdi
0x14001ef95  push    r15
0x14001ef97  lea     rbp, [rsp-50h]
0x14001ef9c  sub     rsp, 150h
0x14001efa3  mov     [rsp+170h+var_124], r9d
0x14001efa8  mov     rbx, rdx
0x14001efab  mov     [rsp+170h+var_128], r8d
0x14001efb0  mov     r15d, ecx
0x14001efb3  mov     [rsp+170h+var_118], rdx
0x14001efb8  call    cs:__imp_?getDLT@DLT_WINEVENT@@SA?AW4DomainLockType@@XZ; DLT_WINEVENT::getDLT(void)
0x14001efbf  nop     dword ptr [rax+rax+00h]
0x14001efc4  mov     ecx, eax
0x14001efc6  call    cs:__imp_?GetDomainLockRef@@YAAEAUtagDomLock@@W4DomainLockType@@@Z; GetDomainLockRef(DomainLockType)
0x14001efcd  nop     dword ptr [rax+rax+00h]
0x14001efd2  mov     [rbp+70h+var_E8], rax
0x14001efd6  mov     [rbp+70h+var_E0], 1
0x14001efda  call    cs:__imp_W32GetUserSessionState
0x14001efe1  nop     dword ptr [rax+rax+00h]
0x14001efe6  mov     rcx, [rbp+70h+var_E8]
0x14001efea  add     rax, 0A4C8h
0x14001eff0  mov     [rbp+70h+var_D8], rax
0x14001eff4  xor     eax, eax
0x14001eff6  mov     [rbp+70h+var_D0], 0
0x14001effa  mov     [rbp+70h+var_C8], rax
0x14001effe  mov     [rbp+70h+var_C0], al
0x14001f001  test    rcx, rcx
0x14001f004  jz      short loc_14001F01B
0x14001f006  cmp     [rbp+70h+var_E0], al
0x14001f009  jz      loc_14001FCCE
0x14001f00f  call    cs:__imp_?LockExclusive@tagDomLock@@QEBAXXZ; tagDomLock::LockExclusive(void)
0x14001f016  nop     dword ptr [rax+rax+00h]
0x14001f01b  mov     eax, r15d
0x14001f01e  mov     [rsp+170h+var_28], r12
0x14001f026  mov     [rsp+170h+var_38], r14
0x14001f02e  mov     edi, 1
0x14001f033  mov     [rbp+70h+var_C0], 1
0x14001f037  sub     eax, 7FFFFF10h
0x14001f03c  jz      loc_14001FC52
0x14001f042  sub     eax, edi
0x14001f044  jz      loc_14001FCC4
0x14001f04a  cmp     eax, edi
0x14001f04c  jz      loc_14001FCC4
0x14001f052  xor     eax, eax
0x14001f054  mov     [rsp+170h+var_130], eax
0x14001f058  cmp     r15d, 80000002h
0x14001f05f  ja      short loc_14001F0A6
0x14001f061  mov     [rsp+170h+var_130], eax
0x14001f065  jz      loc_14001FD23
0x14001f06b  cmp     r15d, 7FFFFF01h
0x14001f072  jz      loc_14001FABE
0x14001f078  cmp     r15d, 7FFFFF00h
0x14001f07f  jz      loc_14001FABE
0x14001f085  cmp     r15d, 80000000h
0x14001f08c  jz      loc_14001FD1A
0x14001f092  cmp     r15d, 80000001h
0x14001f099  jnz     short loc_14001F0CD
0x14001f09b  mov     r12d, 100h
0x14001f0a1  mov     r14d, edi
0x14001f0a4  jmp     short loc_14001F0D3
0x14001f0a6  cmp     r15d, 80000003h
0x14001f0ad  jz      loc_14001FD27
0x14001f0b3  cmp     r15d, 80000005h
0x14001f0ba  jz      loc_14001FB96
0x14001f0c0  cmp     r15d, 80000004h
0x14001f0c7  jz      loc_14001FB96
0x14001f0cd  xor     r12d, r12d
0x14001f0d0  xor     r14d, r14d
0x14001f0d3  xor     esi, esi
0x14001f0d5  test    eax, eax
0x14001f0d7  cmovnz  esi, edi
0x14001f0da  call    cs:__imp_W32GetUserSessionState
0x14001f0e1  nop     dword ptr [rax+rax+00h]
0x14001f0e6  mov     rcx, [rax+4CF8h]
0x14001f0ed  mov     edx, [rcx+764h]
0x14001f0f3  lea     rcx, cs:140000000h
0x14001f0fa  cmp     r15d, 800Bh
0x14001f101  jnz     loc_14001F4FC
0x14001f107  mov     eax, 40h ; '@'
0x14001f10c  test    eax, edx
0x14001f10e  jz      loc_14001F4DD
0x14001f114  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001f11b  nop     dword ptr [rax+rax+00h]
0x14001f120  test    rax, rax
0x14001f123  jz      loc_14001FC09
0x14001f129  cmp     qword ptr [rax], 0
0x14001f12d  jz      loc_14001FC09
0x14001f133  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001f13a  nop     dword ptr [rax+rax+00h]
0x14001f13f  test    rax, rax
0x14001f142  jz      loc_14001FCE6
0x14001f148  mov     rdi, [rax]
0x14001f14b  mov     edx, [rbp+70h+arg_20]
0x14001f151  mov     eax, edx
0x14001f153  and     eax, 11h
0x14001f156  mov     [rbp+70h+var_B0], rdi
0x14001f15a  cmp     al, 11h
0x14001f15c  jnz     loc_14001F9E4
0x14001f162  xor     ecx, ecx
0x14001f164  mov     [rsp+170h+var_30], r13
0x14001f16c  xor     eax, eax
0x14001f16e  lock cmpxchg [rdi+208h], ecx
0x14001f176  mov     ecx, edx
0x14001f178  or      ecx, 2
0x14001f17b  test    eax, 10000001h
0x14001f180  cmovz   ecx, edx
0x14001f183  mov     [rsp+170h+var_12C], ecx
0x14001f187  test    cl, 1
0x14001f18a  jnz     loc_14001FA9B
0x14001f190  mov     r13, rdi
0x14001f193  mov     rcx, [r13+0]; Thread
0x14001f197  call    cs:__imp_PsGetThreadId
0x14001f19e  nop     dword ptr [rax+rax+00h]
0x14001f1a3  mov     rcx, [r13+0]; Thread
0x14001f1a7  mov     [rbp+70h+var_50], rax
0x14001f1ab  mov     rax, [r13+1C8h]
0x14001f1b2  mov     [rbp+70h+var_58], rax
0x14001f1b6  call    cs:__imp_PsGetThreadProcessId
0x14001f1bd  nop     dword ptr [rax+rax+00h]
0x14001f1c2  mov     [rbp+70h+var_60], rax
0x14001f1c6  call    cs:__imp_W32GetUserSessionState
0x14001f1cd  nop     dword ptr [rax+rax+00h]
0x14001f1d2  test    byte ptr [rsp+170h+var_12C], 20h
0x14001f1d7  mov     [rbp+70h+var_A0], rax
0x14001f1db  jnz     loc_14001F9B2
0x14001f1e1  mov     rax, 0FFFFF78000000320h
0x14001f1eb  mov     rcx, 0FFFFF78000000004h
0x14001f1f5  mov     rax, [rax]
0x14001f1f8  mov     ebx, [rcx]
0x14001f1fa  imul    rbx, rax
0x14001f1fe  shr     rbx, 18h
0x14001f202  mov     rax, [rdi+1C0h]
0x14001f209  mov     [rsp+170h+BugCheckParameter3], rax
0x14001f20e  lea     rax, [rsp+170h+BugCheckParameter3]
0x14001f213  mov     [rdi+1C0h], rax
0x14001f21a  mov     rax, [rsp+170h+var_118]
0x14001f21f  mov     qword ptr [rsp+170h+var_120], rbx
0x14001f224  mov     [rbp+70h+var_F0], rax
0x14001f228  test    rax, rax
0x14001f22b  jz      short loc_14001F23C
0x14001f22d  mov     rcx, rax
0x14001f230  call    cs:__imp_HMLockObject
0x14001f237  nop     dword ptr [rax+rax+00h]
0x14001f23c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001f243  nop     dword ptr [rax+rax+00h]
0x14001f248  test    rax, rax
0x14001f24b  jz      loc_14001FCDF
0x14001f251  mov     rcx, [rax]
0x14001f254  mov     rax, [rcx+178h]
0x14001f25b  mov     [rsp+170h+var_110], rax
0x14001f260  lea     rax, [rsp+170h+var_110]
0x14001f265  mov     [rcx+178h], rax
0x14001f26c  lea     rax, ?Deref@Win32RawLockedW32Thread@@CAXPEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::Deref(_W32THREAD *)
0x14001f273  mov     rcx, r13
0x14001f276  mov     [rsp+170h+var_100], rax
0x14001f27b  mov     [rsp+170h+var_108], r13
0x14001f280  call    cs:__imp_ReferenceW32Thread
0x14001f287  nop     dword ptr [rax+rax+00h]
0x14001f28c  mov     edx, [rsp+170h+var_12C]
0x14001f290  test    dl, 2
0x14001f293  jnz     short loc_14001F301
0x14001f295  call    cs:__imp_W32GetUserSessionState
0x14001f29c  nop     dword ptr [rax+rax+00h]
0x14001f2a1  mov     rcx, [rax+0A4A0h]; Resource
0x14001f2a8  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14001f2af  nop     dword ptr [rax+rax+00h]
0x14001f2b4  cmp     al, 1
0x14001f2b6  jz      short loc_14001F2BA
0x14001f2b8  int     2Ch; Windows NT - assertion failure
0x14001f2ba  call    cs:__imp_PsGetCurrentThreadId
0x14001f2c1  nop     dword ptr [rax+rax+00h]
0x14001f2c6  mov     rdi, rax
0x14001f2c9  call    cs:__imp_W32GetUserSessionState
0x14001f2d0  nop     dword ptr [rax+rax+00h]
0x14001f2d5  lea     rbx, [rax+113C8h]
0x14001f2dc  mov     rcx, [rbx]; struct tagNOTIFY *
0x14001f2df  cmp     rcx, rbx
0x14001f2e2  jz      short loc_14001F2F8
0x14001f2e4  mov     edx, [rcx+38h]
0x14001f2e7  test    dl, 2
0x14001f2ea  jnz     loc_14001F664
0x14001f2f0  mov     rcx, [rcx]
0x14001f2f3  cmp     rcx, rbx
0x14001f2f6  jnz     short loc_14001F2E4
0x14001f2f8  mov     edx, [rsp+170h+var_12C]
0x14001f2fc  mov     rbx, qword ptr [rsp+170h+var_120]
0x14001f301  test    r14d, r14d
0x14001f304  mov     r14, [rsp+170h+var_118]
0x14001f309  jnz     loc_14001FC5D
0x14001f30f  test    esi, esi
0x14001f311  jz      loc_14001FAF5
0x14001f317  call    cs:__imp_W32GetUserSessionState
0x14001f31e  nop     dword ptr [rax+rax+00h]
0x14001f323  mov     r12, qword ptr [rsp+170h+var_120]
0x14001f328  mov     rdi, [rax+8D68h]
0x14001f32f  mov     [rbp+70h+var_B8], rdi
0x14001f333  test    rdi, rdi
0x14001f336  jz      short loc_14001F361
0x14001f338  mov     esi, [rsp+170h+var_130]
0x14001f33c  nop     dword ptr [rax+00h]
0x14001f340  mov     eax, [rdi+328h]
0x14001f346  bt      rax, 18h
0x14001f34b  jb      loc_14001F475
0x14001f351  mov     rdi, [rdi+170h]
0x14001f358  mov     [rbp+70h+var_B8], rdi
0x14001f35c  test    rdi, rdi
0x14001f35f  jnz     short loc_14001F340
0x14001f361  call    cs:__imp_W32GetUserSessionState
0x14001f368  nop     dword ptr [rax+rax+00h]
0x14001f36d  mov     rcx, [rax+4CF8h]
0x14001f374  mov     edx, [rcx+764h]
0x14001f37a  cmp     r15d, 800Bh
0x14001f381  jnz     loc_14001F553
0x14001f387  mov     eax, 40h ; '@'
0x14001f38c  test    eax, edx
0x14001f38e  jnz     loc_14001F6C2
0x14001f394  cmp     [rsp+170h+var_100], 0FFFFFFFFFFFFFFFFh
0x14001f39a  jz      short loc_14001F3DD
0x14001f39c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001f3a3  nop     dword ptr [rax+rax+00h]
0x14001f3a8  test    rax, rax
0x14001f3ab  jz      loc_14001FCF4
0x14001f3b1  mov     rcx, [rax]
0x14001f3b4  mov     rax, [rsp+170h+var_110]
0x14001f3b9  mov     [rcx+178h], rax
0x14001f3c0  mov     rcx, [rsp+170h+var_108]
0x14001f3c5  test    rcx, rcx
0x14001f3c8  jz      short loc_14001F3D4
0x14001f3ca  mov     rax, [rsp+170h+var_100]
0x14001f3cf  call    _guard_dispatch_icall
0x14001f3d4  mov     [rsp+170h+var_100], 0FFFFFFFFFFFFFFFFh
0x14001f3dd  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001f3e4  nop     dword ptr [rax+rax+00h]
0x14001f3e9  test    rax, rax
0x14001f3ec  jz      loc_14001FCED
0x14001f3f2  mov     rdx, [rax]
0x14001f3f5  mov     rcx, [rdx+1C0h]
0x14001f3fc  lea     rax, [rsp+170h+BugCheckParameter3]
0x14001f401  cmp     rcx, rax
0x14001f404  jnz     loc_14001FBA4
0x14001f40a  mov     rax, [rcx]
0x14001f40d  mov     [rdx+1C0h], rax
0x14001f414  mov     rcx, [rcx+8]
0x14001f418  test    rcx, rcx
0x14001f41b  jz      short loc_14001F429
0x14001f41d  call    cs:__imp_HMUnlockObject
0x14001f424  nop     dword ptr [rax+rax+00h]
0x14001f429  cmp     [rbp+70h+var_C0], 0
0x14001f42d  jz      short loc_14001F44E
0x14001f42f  mov     rcx, [rbp+70h+var_E8]
0x14001f433  test    rcx, rcx
0x14001f436  jz      short loc_14001F44E
0x14001f438  cmp     [rbp+70h+var_E0], 0
0x14001f43c  jz      loc_14001F4CC
0x14001f442  call    cs:__imp_?UnLockExclusive@tagDomLock@@QEBAXXZ; tagDomLock::UnLockExclusive(void)
0x14001f449  nop     dword ptr [rax+rax+00h]
0x14001f44e  mov     r13, [rsp+170h+var_30]
0x14001f456  mov     r14, [rsp+170h+var_38]
0x14001f45e  mov     r12, [rsp+170h+var_28]
0x14001f466  add     rsp, 150h
0x14001f46d  pop     r15
0x14001f46f  pop     rdi
0x14001f470  pop     rsi
0x14001f471  pop     rbx
0x14001f472  pop     rbp
0x14001f473  retn
0x14001f475  mov     rbx, [rdi+148h]
0x14001f47c  test    rbx, rbx
0x14001f47f  jz      loc_14001F351
0x14001f485  mov     edi, [rsp+170h+var_128]
0x14001f489  mov     rax, [rbx+1E0h]
0x14001f490  test    [rax+18h], esi
0x14001f493  jz      short loc_14001F4B7
0x14001f495  mov     r9d, [rsp+170h+var_124]; int
0x14001f49a  mov     r8d, edi; int
0x14001f49d  mov     dword ptr [rsp+170h+var_140], r12d; unsigned int
0x14001f4a2  mov     rdx, r14; struct tagWND *
0x14001f4a5  mov     [rsp+170h+var_148], r13; struct tagTHREADINFO *
0x14001f4aa  mov     ecx, r15d; unsigned int
0x14001f4ad  mov     [rsp+170h+BugCheckParameter4], rbx; struct tagTHREADINFO *
0x14001f4b2  call    ?CreateAndPostTSFNotify@@YAXKPEAUtagWND@@JJPEAUtagTHREADINFO@@1K@Z; CreateAndPostTSFNotify(ulong,tagWND *,long,long,tagTHREADINFO *,tagTHREADINFO *,ulong)
0x14001f4b7  mov     rbx, [rbx+2B8h]
0x14001f4be  test    rbx, rbx
0x14001f4c1  jnz     short loc_14001F489
0x14001f4c3  mov     rdi, [rbp+70h+var_B8]
0x14001f4c7  jmp     loc_14001F351
0x14001f4cc  call    cs:__imp_?UnLockShared@tagDomLock@@QEBAXXZ; tagDomLock::UnLockShared(void)
0x14001f4d3  nop     dword ptr [rax+rax+00h]
0x14001f4d8  jmp     loc_14001F44E
0x14001f4dd  test    esi, esi
0x14001f4df  jnz     loc_14001F114
0x14001f4e5  test    r14d, r14d
0x14001f4e8  jnz     loc_14001F114
0x14001f4ee  lea     rcx, [rbp+70h+var_E8]
0x14001f4f2  call    ??1?$ObjectLock@$$V@?$DomainExclusive@VDLT_HOOK@@@?$DomainShared@$$V@@QEAA@XZ; DomainShared<>::DomainExclusive<DLT_HOOK>::ObjectLock<>::~ObjectLock<>(void)
0x14001f4f7  jmp     loc_14001F456
0x14001f4fc  cmp     r15d, 800Ah
0x14001f503  ja      loc_14001F5AA
  ... truncated ...
```
