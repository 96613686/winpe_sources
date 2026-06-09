# DEVLOCKOBJ::~DEVLOCKOBJ(void)

- ea: `0x14005d010`
- end: `0x14005d6d2`
- name: `??1DEVLOCKOBJ@@QEAA@XZ`
- size: `1730`
- prototype: `void __fastcall(HDC *this)`
- caller_count: `78`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003baf8`
- `0x14003e810`
- `0x1400502c4`
- `0x140052954`
- `0x140052fe0`
- `0x140054a74`
- `0x14005ba50`
- `0x14005c5f0`
- `0x14005f820`
- `0x14006487c`
- `0x140065f80`
- `0x14006651c`
- `0x140066cd0`
- `0x140069c70`
- `0x14006a108`
- `0x14006a4c0`
- `0x14006aa18`
- `0x14006b5c4`
- `0x14006be04`
- `0x14006d0d0`
- `0x14008826c`
- `0x140088bd4`
- `0x14008aafc`
- `0x14009b770`
- `0x1400a55dc`
- `0x1400a9c94`
- `0x140110a10`
- `0x14011b718`
- `0x14011bb64`
- `0x140120928`
- `0x140120b84`
- `0x140156120`
- `0x14019e020`
- `0x1401aa4a0`
- `0x1401aaa50`
- `0x1401d7888`
- `0x1401d8ce0`
- `0x1401fa730`
- `0x14020c690`
- `0x140215554`
- `0x140219b90`
- `0x140219e20`
- `0x14021f99c`
- `0x14022dc10`
- `0x1402357c0`
- `0x14023f360`
- `0x140284380`
- `0x14028d380`
- `0x140298ca8`
- `0x14029dcf4`

## callees

- `0x14005d010`
- `0x14005d6e0`
- `0x14005db98`
- `0x140067320`
- `0x140099c84`
- `0x14009a40c`
- `0x14009b35c`
- `0x1400ac68c`
- `0x1400ae480`
- `0x14011e794`
- `0x14011e9a0`
- `0x14011ea9c`
- `0x14011eb74`
- `0x14011ec90`
- `0x1401cfb8c`
- `0x140343080`

## import_xrefs

- `ntoskrnl!KeIsAttachedProcess` at `0x14005d0c8`
- `ntoskrnl!KeIsAttachedProcess` at `0x14005d0c8`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14005d5fa`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14005d5fa`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005d16f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005d242`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005d16f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005d242`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005d5ec`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005d609`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005d5ec`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005d609`
- `ntoskrnl!PsGetCurrentProcess` at `0x14005d5dd`
- `ntoskrnl!PsGetCurrentProcess` at `0x14005d5dd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005d055`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005d055`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14005d0df`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14005d0df`
- `win32kbase!GreDereferenceObject` at `0x14005d480`
- `win32kbase!GreDereferenceObject` at `0x14005d480`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d3bf`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d3f1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d42f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d452`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d4a8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d4f2`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d3bf`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d3f1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d42f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d452`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d4a8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d4f2`
- `win32kbase!HmgPentryFromPobj` at `0x14005d194`
- `win32kbase!HmgPentryFromPobj` at `0x14005d267`
- `win32kbase!HmgPentryFromPobj` at `0x14005d194`
- `win32kbase!HmgPentryFromPobj` at `0x14005d267`
- `win32kbase!HmgShareLock` at `0x14005d3da`
- `win32kbase!HmgShareLock` at `0x14005d40c`
- `win32kbase!HmgShareLock` at `0x14005d3da`
- `win32kbase!HmgShareLock` at `0x14005d40c`
- `win32kbase!PopThreadGuardedObject` at `0x14005d14a`
- `win32kbase!PopThreadGuardedObject` at `0x14005d1ee`
- `win32kbase!PopThreadGuardedObject` at `0x14005d14a`
- `win32kbase!PopThreadGuardedObject` at `0x14005d1ee`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14005d442`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14005d465`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14005d442`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14005d465`
- `win32kbase!PushThreadGuardedObject` at `0x14005d37e`
- `win32kbase!PushThreadGuardedObject` at `0x14005d3a8`
- `win32kbase!PushThreadGuardedObject` at `0x14005d37e`
- `win32kbase!PushThreadGuardedObject` at `0x14005d3a8`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14005d119`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14005d54b`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14005d10d`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14005d593`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14005d10d`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14005d593`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005d0b3`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005d2ff`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005d0b3`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005d2ff`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14005d631`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14005d651`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14005d631`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14005d651`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14005d32b`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14005d1c8`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14005d29b`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14005d1c8`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14005d29b`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005d1b1`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005d284`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005d1b1`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005d284`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005d682`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005d6ba`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005d682`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005d6ba`
- `win32kbase!GreDecLockCount` at `0x14005d042`
- `win32kbase!GreDecLockCount` at `0x14005d2cc`
- `win32kbase!GreDecLockCount` at `0x14005d042`
- `win32kbase!GreDecLockCount` at `0x14005d2cc`
- `win32kbase!GreGetLockCount` at `0x14005d4cb`
- `win32kbase!GreGetLockCount` at `0x14005d4cb`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14005d51e`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14005d5b8`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14005d51e`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14005d5b8`

## pseudocode

```c
void __fastcall DEVLOCKOBJ::~DEVLOCKOBJ(HDC *this)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // eax
  HDC v9; // rsi
  struct _KTHREAD *CurrentThread; // r14
  __int64 ThreadWin32Thread; // rax
  _QWORD *v12; // rdx
  bool v13; // zf
  HDC v14; // rax
  DCOBJ *v15; // rbx
  unsigned int v16; // eax
  DC *v17; // rsi
  unsigned int v18; // edi
  __int64 v19; // r14
  struct _DC_ATTR *v20; // rax
  unsigned int CurrentProcessId; // eax
  __int64 v22; // rsi
  unsigned int v23; // edi
  __int64 v24; // r14
  struct _DC_ATTR *UserAttr; // rax
  __int64 v26; // rbx
  struct _GRETHREAD *v27; // rax
  HDC v28; // rbx
  Gre::Base *v29; // rcx
  struct Gre::Base::SESSION_GLOBALS *v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  HDC v33; // rbx
  Gre::Base *v34; // rcx
  struct Gre::Base::SESSION_GLOBALS *v35; // rax
  __int64 v36; // r8
  __int64 v37; // rbx
  Gre::Base *v38; // rcx
  struct Gre::Base::SESSION_GLOBALS *v39; // rax
  Gre::Base *v40; // rcx
  struct Gre::Base::SESSION_GLOBALS *v41; // rax
  __int64 v42; // rdx
  Gre::Base *v43; // rcx
  struct Gre::Base::SESSION_GLOBALS *v44; // rbx
  char v45; // si
  Gre::Base *v46; // rcx
  struct Gre::Base::SESSION_GLOBALS *v47; // rax
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  _OWORD v54[2]; // [rsp+30h] [rbp-49h] BYREF
  __int64 *v55; // [rsp+50h] [rbp-29h]
  _OWORD v56[2]; // [rsp+58h] [rbp-21h] BYREF
  struct SURFACE *v57; // [rsp+78h] [rbp-1h]
  DC *v58[8]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v59; // [rsp+E0h] [rbp+67h] BYREF

  DEVLOCKOBJ::bDisposeTrgDcoWorker((DEVLOCKOBJ *)this);
  v2 = *((_DWORD *)this + 6);
  if ( (v2 & 0x1000) != 0 )
  {
    GreDecLockCount();
    *((_DWORD *)this + 6) &= ~0x1000u;
    CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v4, v3);
    if ( CurrentThreadWin32Thread )
    {
      v6 = *CurrentThreadWin32Thread;
      if ( v6 )
      {
        v7 = v6 + 8;
        if ( v7 )
        {
          *(_QWORD *)(v7 + 304) = 0;
          *(_QWORD *)(v7 + 296) = 0;
        }
      }
    }
  }
  else if ( (v2 & 0x80000) != 0 )
  {
    GreDecLockCount();
    *((_DWORD *)this + 6) &= ~0x80000u;
  }
  if ( *this )
  {
    if ( ((_DWORD)this[3] & 0x100000) != 0 )
    {
      GreReleaseSemaphoreExclusive<2>();
      *((_DWORD *)this + 6) &= ~0x100000u;
    }
    else
    {
      v26 = *((_QWORD *)this[2] + 6);
      EtwTraceGreLockReleaseSemaphore(L"DevLock", v26);
      v27 = GreGetCurrentThreadCrossSessionCheck();
      if ( v27 )
      {
        v13 = (*((_BYTE *)v27 + 16))-- == 1;
        if ( v13 )
          *(_QWORD *)v27 &= ~0x100uLL;
        if ( !*(_QWORD *)v27 )
          GrepOnAllLocksReleased();
      }
      ((void (__fastcall *)(__int64))GreReleaseSemaphoreExclusiveInternal)(v26);
    }
  }
  v8 = *((_DWORD *)this + 6);
  if ( (v8 & 8) != 0 )
    *((_DWORD *)this + 6) = v8 & 0xFFFFFFF7;
  v9 = this[1];
  if ( v9 )
  {
    EtwTraceGreLockReleaseSemaphore(L"DynamicModeChange", v9);
    CurrentThread = KeGetCurrentThread();
    if ( !(unsigned __int8)KeIsAttachedProcess()
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
          v12 = (_QWORD *)(*(_QWORD *)ThreadWin32Thread + 8LL);
          if ( *(_QWORD *)ThreadWin32Thread != -8 )
          {
            v13 = (*(_BYTE *)(*(_QWORD *)ThreadWin32Thread + 17LL))-- == 1;
            if ( v13 )
              *v12 &= ~2uLL;
            if ( !*v12 )
              GrepOnAllLocksReleased();
          }
        }
      }
    }
    ((void (__fastcall *)(HDC))GreReleaseSemaphoreSharedInternal)(v9);
  }
  if ( this[18] )
  {
    DCOBJ::DCOBJ((DCOBJ *)v58, this[19]);
    memset(v54, 0, sizeof(v54));
    PushThreadGuardedObject(
      v54,
      v54,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    v55 = 0;
    memset(v56, 0, sizeof(v56));
    PushThreadGuardedObject(
      v56,
      v56,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    v28 = this[17];
    v57 = 0;
    v30 = Gre::Base::Globals(v29);
    LOBYTE(v31) = 5;
    v32 = HmgShareLock(v30, v28, v31, 1);
    v33 = this[18];
    v55 = (__int64 *)v32;
    v35 = Gre::Base::Globals(v34);
    LOBYTE(v36) = 5;
    v57 = (struct SURFACE *)HmgShareLock(v35, v33, v36, 1);
    v37 = *v55;
    DC::pSurface(v58[0], v57);
    v39 = Gre::Base::Globals(v38);
    DEC_SHARE_REF_CNT(v39, v55);
    v55 = 0;
    v41 = Gre::Base::Globals(v40);
    DEC_SHARE_REF_CNT(v41, v57);
    v57 = 0;
    LOBYTE(v42) = 5;
    GreDereferenceObject(v37, v42, 1);
    this[19] = 0;
    this[17] = 0;
    if ( this != (HDC *)-28LL )
    {
      v43 = v58[0];
      *((_DWORD *)v58[0] + 9) |= *((_DWORD *)this + 7);
    }
    v44 = Gre::Base::Globals(v43);
    if ( (*((_DWORD *)v58[0] + 9) & 0x200) != 0 )
    {
      v45 = 0;
      if ( !(unsigned int)GreGetLockCount()
        && !(unsigned __int8)GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(v44) )
      {
        GreAcquireSemaphoreShared<2,>(v44);
        v45 = 1;
      }
      v47 = Gre::Base::Globals(v46);
      SEMOBJSHARED<3>::SEMOBJSHARED<3>(&v59, v47);
      v48 = HmgShareUnlockRemoveObject(this[18], 0, 0, 0, 5);
      if ( v48 )
        SURFACE::bDeleteSurface(v48, v44, 0, 1);
      *((_QWORD *)v58[0] + 63) = 0;
      DC::vClearRendering(v58[0]);
      v49 = v59;
      this[18] = 0;
      GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v49);
      if ( v45 )
        GreReleaseSemaphoreShared<2,>(v44);
    }
    else
    {
      v50 = HmgShareUnlockRemoveObject(this[18], 0, 0, 0, 5);
      if ( v50 )
        SURFACE::bDeleteSurface(v50, v44, 0, 1);
      *((_QWORD *)v58[0] + 63) = 0;
      this[18] = 0;
    }
    GreReleaseSemaphoreShared<1,>(v44);
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v56);
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v54);
    DCOBJ::~DCOBJ((DCOBJ *)v58);
  }
  v14 = this[4];
  v15 = (DCOBJ *)(this + 4);
  if ( v14 )
  {
    if ( *((_BYTE *)this + 128) )
    {
      *((_DWORD *)v14 + 10) &= ~2u;
      *((_BYTE *)this + 128) = 0;
    }
    if ( *(_QWORD *)v15 )
    {
      if ( *((_DWORD *)this + 10) && (*(_DWORD *)(*(_QWORD *)v15 + 44LL) & 2) != 0 )
      {
        CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
        v22 = *(_QWORD *)v15;
        v23 = CurrentProcessId & 0xFFFFFFFC;
        if ( **(_QWORD **)v15 )
        {
          v24 = HmgPentryFromPobj(*((_QWORD *)v15 + 2), *(_QWORD *)v15);
        }
        else
        {
          v24 = v22 + 2152;
          *(_OWORD *)(v22 + 2152) = 0;
          *(_QWORD *)(v22 + 2168) = 0;
          *(_DWORD *)(v22 + 2160) = -2147483630;
          *(_QWORD *)(v22 + 2168) = GreEncodeUserModePointer(0);
        }
        if ( v23 == (*(_DWORD *)(v24 + 8) & 0xFFFFFFFE) )
        {
          UserAttr = DCOBJ::GetUserAttr(v15);
          if ( UserAttr )
            DC::RestoreAttributes(*(DC **)v15, UserAttr);
        }
        *(_DWORD *)(*(_QWORD *)v15 + 44LL) &= ~2u;
        *((_DWORD *)v15 + 2) = 0;
      }
      _InterlockedDecrement16((volatile signed __int16 *)(*(_QWORD *)v15 + 12LL));
      *(_QWORD *)v15 = 0;
    }
  }
  PopThreadGuardedObject((char *)v15 + 64);
  if ( *(_QWORD *)v15 )
  {
    if ( *((_DWORD *)v15 + 2) && (*(_DWORD *)(*(_QWORD *)v15 + 44LL) & 2) != 0 )
    {
      v16 = (unsigned int)PsGetCurrentProcessId();
      v17 = *(DC **)v15;
      v18 = v16 & 0xFFFFFFFC;
      if ( **(_QWORD **)v15 )
      {
        v19 = HmgPentryFromPobj(*((_QWORD *)v15 + 2), *(_QWORD *)v15);
      }
      else
      {
        v19 = (__int64)v17 + 2152;
        *(_OWORD *)((char *)v17 + 2152) = 0;
        *((_QWORD *)v17 + 271) = 0;
        *((_DWORD *)v17 + 540) = -2147483630;
        *((_QWORD *)v17 + 271) = GreEncodeUserModePointer(0);
      }
      if ( v18 == (*(_DWORD *)(v19 + 8) & 0xFFFFFFFE) )
      {
        v20 = DCOBJ::GetUserAttr(v15);
        if ( v20 )
          DC::RestoreAttributes(*(DC **)v15, v20);
      }
      *(_DWORD *)(*(_QWORD *)v15 + 44LL) &= ~2u;
      *((_DWORD *)v15 + 2) = 0;
    }
    _InterlockedDecrement16((volatile signed __int16 *)(*(_QWORD *)v15 + 12LL));
    *(_QWORD *)v15 = 0;
  }
  PopThreadGuardedObject((char *)v15 + 32);
}

```

## disassembly

```asm
0x14005d010  mov     [rsp-8+arg_10], rbx
0x14005d015  mov     [rsp-8+arg_18], rsi
0x14005d01a  push    rbp
0x14005d01b  push    rdi
0x14005d01c  push    r15
0x14005d01e  lea     rbp, [rsp-47h]
0x14005d023  sub     rsp, 0C0h
0x14005d02a  mov     rdi, rcx
0x14005d02d  call    ?bDisposeTrgDcoWorker@DEVLOCKOBJ@@QEAAHXZ; DEVLOCKOBJ::bDisposeTrgDcoWorker(void)
0x14005d032  mov     eax, [rdi+18h]
0x14005d035  xor     r15d, r15d
0x14005d038  bt      eax, 0Ch
0x14005d03c  jnb     loc_14005D2C2
0x14005d042  call    cs:__imp_GreDecLockCount
0x14005d049  nop     dword ptr [rax+rax+00h]
0x14005d04e  and     dword ptr [rdi+18h], 0FFFFEFFFh
0x14005d055  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14005d05c  nop     dword ptr [rax+rax+00h]
0x14005d061  test    rax, rax
0x14005d064  jz      short loc_14005D082
0x14005d066  mov     rax, [rax]
0x14005d069  test    rax, rax
0x14005d06c  jz      short loc_14005D082
0x14005d06e  add     rax, 8
0x14005d072  jz      short loc_14005D082
0x14005d074  mov     [rax+130h], r15
0x14005d07b  mov     [rax+128h], r15
0x14005d082  cmp     [rdi], r15
0x14005d085  jnz     loc_14005D2E4
0x14005d08b  mov     eax, [rdi+18h]
0x14005d08e  test    al, 8
0x14005d090  jz      short loc_14005D098
0x14005d092  and     eax, 0FFFFFFF7h
0x14005d095  mov     [rdi+18h], eax
0x14005d098  mov     rsi, [rdi+8]
0x14005d09c  mov     [rsp+0D0h+arg_8], r14
0x14005d0a4  test    rsi, rsi
0x14005d0a7  jz      short loc_14005D128
0x14005d0a9  mov     rdx, rsi
0x14005d0ac  lea     rcx, aDynamicmodecha; "DynamicModeChange"
0x14005d0b3  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14005d0ba  nop     dword ptr [rax+rax+00h]
0x14005d0bf  mov     r14, gs:188h
0x14005d0c8  call    cs:__imp_KeIsAttachedProcess
0x14005d0cf  nop     dword ptr [rax+rax+00h]
0x14005d0d4  test    al, al
0x14005d0d6  jnz     loc_14005D5DD
0x14005d0dc  mov     rcx, r14
0x14005d0df  call    cs:__imp_PsGetThreadWin32Thread
0x14005d0e6  nop     dword ptr [rax+rax+00h]
0x14005d0eb  test    rax, rax
0x14005d0ee  jz      short loc_14005D119
0x14005d0f0  mov     rdx, [rax]
0x14005d0f3  test    rdx, rdx
0x14005d0f6  jz      short loc_14005D119
0x14005d0f8  add     rdx, 8
0x14005d0fc  jz      short loc_14005D119
0x14005d0fe  add     byte ptr [rdx+9], 0FFh
0x14005d102  jnz     short loc_14005D108
0x14005d104  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x14005d108  cmp     [rdx], r15
0x14005d10b  jnz     short loc_14005D119
0x14005d10d  call    cs:__imp_?GrepOnAllLocksReleased@@YAXXZ; GrepOnAllLocksReleased(void)
0x14005d114  nop     dword ptr [rax+rax+00h]
0x14005d119  mov     rax, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14005d120  mov     rcx, rsi
0x14005d123  call    _guard_dispatch_icall
0x14005d128  cmp     [rdi+90h], r15
0x14005d12f  jnz     loc_14005D350
0x14005d135  mov     rax, [rdi+20h]
0x14005d139  lea     rbx, [rdi+20h]
0x14005d13d  test    rax, rax
0x14005d140  jnz     loc_14005D21B
0x14005d146  lea     rcx, [rbx+40h]
0x14005d14a  call    cs:__imp_PopThreadGuardedObject
0x14005d151  nop     dword ptr [rax+rax+00h]
0x14005d156  mov     rax, [rbx]
0x14005d159  test    rax, rax
0x14005d15c  jz      loc_14005D1EA
0x14005d162  cmp     [rbx+8], r15d
0x14005d166  jz      short loc_14005D1DF
0x14005d168  mov     eax, [rax+2Ch]
0x14005d16b  test    al, 2
0x14005d16d  jz      short loc_14005D1DF
0x14005d16f  call    cs:__imp_PsGetCurrentProcessId
0x14005d176  nop     dword ptr [rax+rax+00h]
0x14005d17b  mov     rsi, [rbx]
0x14005d17e  mov     rdi, rax
0x14005d181  and     edi, 0FFFFFFFCh
0x14005d184  cmp     [rsi], r15
0x14005d187  jz      loc_14005D69A
0x14005d18d  mov     rcx, [rbx+10h]
0x14005d191  mov     rdx, rsi
0x14005d194  call    cs:__imp_HmgPentryFromPobj
0x14005d19b  nop     dword ptr [rax+rax+00h]
0x14005d1a0  mov     r14, rax
0x14005d1a3  mov     eax, [r14+8]
0x14005d1a7  and     eax, 0FFFFFFFEh
0x14005d1aa  cmp     edi, eax
0x14005d1ac  jnz     short loc_14005D1D4
0x14005d1ae  mov     rcx, rbx
0x14005d1b1  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14005d1b8  nop     dword ptr [rax+rax+00h]
0x14005d1bd  test    rax, rax
0x14005d1c0  jz      short loc_14005D1D4
0x14005d1c2  mov     rcx, [rbx]
0x14005d1c5  mov     rdx, rax
0x14005d1c8  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x14005d1cf  nop     dword ptr [rax+rax+00h]
0x14005d1d4  mov     rax, [rbx]
0x14005d1d7  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14005d1db  mov     [rbx+8], r15d
0x14005d1df  mov     rax, [rbx]
0x14005d1e2  lock dec word ptr [rax+0Ch]
0x14005d1e7  mov     [rbx], r15
0x14005d1ea  lea     rcx, [rbx+20h]
0x14005d1ee  call    cs:__imp_PopThreadGuardedObject
0x14005d1f5  nop     dword ptr [rax+rax+00h]
0x14005d1fa  mov     r14, [rsp+0D0h+arg_8]
0x14005d202  lea     r11, [rsp+0D0h+var_10]
0x14005d20a  mov     rbx, [r11+30h]
0x14005d20e  mov     rsi, [r11+38h]
0x14005d212  mov     rsp, r11
0x14005d215  pop     r15
0x14005d217  pop     rdi
0x14005d218  pop     rbp
0x14005d219  retn
0x14005d21b  cmp     [rbx+60h], r15b
0x14005d21f  jz      short loc_14005D229
0x14005d221  and     dword ptr [rax+28h], 0FFFFFFFDh
0x14005d225  mov     [rbx+60h], r15b
0x14005d229  mov     rax, [rbx]
0x14005d22c  test    rax, rax
0x14005d22f  jz      loc_14005D146
0x14005d235  cmp     [rbx+8], r15d
0x14005d239  jz      short loc_14005D2B2
0x14005d23b  mov     eax, [rax+2Ch]
0x14005d23e  test    al, 2
0x14005d240  jz      short loc_14005D2B2
0x14005d242  call    cs:__imp_PsGetCurrentProcessId
0x14005d249  nop     dword ptr [rax+rax+00h]
0x14005d24e  mov     rsi, [rbx]
0x14005d251  mov     rdi, rax
0x14005d254  and     edi, 0FFFFFFFCh
0x14005d257  cmp     [rsi], r15
0x14005d25a  jz      loc_14005D662
0x14005d260  mov     rcx, [rbx+10h]
0x14005d264  mov     rdx, rsi
0x14005d267  call    cs:__imp_HmgPentryFromPobj
0x14005d26e  nop     dword ptr [rax+rax+00h]
0x14005d273  mov     r14, rax
0x14005d276  mov     eax, [r14+8]
0x14005d27a  and     eax, 0FFFFFFFEh
0x14005d27d  cmp     edi, eax
0x14005d27f  jnz     short loc_14005D2A7
0x14005d281  mov     rcx, rbx
0x14005d284  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14005d28b  nop     dword ptr [rax+rax+00h]
0x14005d290  test    rax, rax
0x14005d293  jz      short loc_14005D2A7
0x14005d295  mov     rcx, [rbx]
0x14005d298  mov     rdx, rax
0x14005d29b  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x14005d2a2  nop     dword ptr [rax+rax+00h]
0x14005d2a7  mov     rax, [rbx]
0x14005d2aa  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14005d2ae  mov     [rbx+8], r15d
0x14005d2b2  mov     rax, [rbx]
0x14005d2b5  lock dec word ptr [rax+0Ch]
0x14005d2ba  mov     [rbx], r15
0x14005d2bd  jmp     loc_14005D146
0x14005d2c2  bt      eax, 13h
0x14005d2c6  jnb     loc_14005D082
0x14005d2cc  call    cs:__imp_GreDecLockCount
0x14005d2d3  nop     dword ptr [rax+rax+00h]
0x14005d2d8  and     dword ptr [rdi+18h], 0FFF7FFFFh
0x14005d2df  jmp     loc_14005D082
0x14005d2e4  test    dword ptr [rdi+18h], 100000h
0x14005d2eb  jnz     short loc_14005D33F
0x14005d2ed  mov     rax, [rdi+10h]
0x14005d2f1  lea     rcx, aDevlock; "DevLock"
0x14005d2f8  mov     rbx, [rax+30h]
0x14005d2fc  mov     rdx, rbx
0x14005d2ff  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14005d306  nop     dword ptr [rax+rax+00h]
0x14005d30b  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14005d310  test    rax, rax
0x14005d313  jz      short loc_14005D32B
0x14005d315  add     byte ptr [rax+10h], 0FFh
0x14005d319  jnz     short loc_14005D322
0x14005d31b  and     qword ptr [rax], 0FFFFFFFFFFFFFEFFh
0x14005d322  cmp     [rax], r15
0x14005d325  jz      loc_14005D593
0x14005d32b  mov     rax, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x14005d332  mov     rcx, rbx
0x14005d335  call    _guard_dispatch_icall
0x14005d33a  jmp     loc_14005D08B
0x14005d33f  call    ??$GreReleaseSemaphoreExclusive@$01@@YAXXZ; GreReleaseSemaphoreExclusive<2>(void)
0x14005d344  and     dword ptr [rdi+18h], 0FFEFFFFFh
0x14005d34b  jmp     loc_14005D08B
0x14005d350  mov     rdx, [rdi+98h]; HDC
0x14005d357  lea     rcx, [rbp+57h+var_50]; this
0x14005d35b  lea     rsi, [rdi+1Ch]
0x14005d35f  call    ??0DCOBJ@@QEAA@PEAUHDC__@@@Z; DCOBJ::DCOBJ(HDC__ *)
0x14005d364  xorps   xmm0, xmm0
0x14005d367  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14005d36e  lea     rdx, [rbp+57h+var_A0]
0x14005d372  lea     rcx, [rbp+57h+var_A0]
0x14005d376  movups  [rbp+57h+var_A0], xmm0
0x14005d37a  movups  [rbp+57h+var_90], xmm0
0x14005d37e  call    cs:__imp_PushThreadGuardedObject
0x14005d385  nop     dword ptr [rax+rax+00h]
0x14005d38a  xorps   xmm0, xmm0
0x14005d38d  mov     [rbp+57h+var_80], r15
0x14005d391  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14005d398  lea     rdx, [rbp+57h+var_78]
0x14005d39c  lea     rcx, [rbp+57h+var_78]
0x14005d3a0  movups  [rbp+57h+var_78], xmm0
0x14005d3a4  movups  [rbp+57h+var_68], xmm0
0x14005d3a8  call    cs:__imp_PushThreadGuardedObject
0x14005d3af  nop     dword ptr [rax+rax+00h]
0x14005d3b4  mov     rbx, [rdi+88h]
0x14005d3bb  mov     [rbp+57h+var_58], r15
0x14005d3bf  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005d3c6  nop     dword ptr [rax+rax+00h]
0x14005d3cb  mov     r9d, 1
0x14005d3d1  mov     r8b, 5
0x14005d3d4  mov     rcx, rax
0x14005d3d7  mov     rdx, rbx
0x14005d3da  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14005d3e1  nop     dword ptr [rax+rax+00h]
0x14005d3e6  mov     rbx, [rdi+90h]
0x14005d3ed  mov     [rbp+57h+var_80], rax
0x14005d3f1  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005d3f8  nop     dword ptr [rax+rax+00h]
0x14005d3fd  mov     r9d, 1
0x14005d403  mov     r8b, 5
0x14005d406  mov     rcx, rax
0x14005d409  mov     rdx, rbx
0x14005d40c  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14005d413  nop     dword ptr [rax+rax+00h]
0x14005d418  mov     rcx, [rbp+57h+var_80]
0x14005d41c  mov     rdx, rax; struct SURFACE *
0x14005d41f  mov     [rbp+57h+var_58], rax
0x14005d423  mov     rbx, [rcx]
0x14005d426  mov     rcx, [rbp+57h+var_50]; this
0x14005d42a  call    ?pSurface@DC@@QEAAXPEAVSURFACE@@@Z; DC::pSurface(SURFACE *)
0x14005d42f  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005d436  nop     dword ptr [rax+rax+00h]
0x14005d43b  mov     rdx, [rbp+57h+var_80]
0x14005d43f  mov     rcx, rax
0x14005d442  call    cs:__imp_DEC_SHARE_REF_CNT
0x14005d449  nop     dword ptr [rax+rax+00h]
0x14005d44e  mov     [rbp+57h+var_80], r15
0x14005d452  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005d459  nop     dword ptr [rax+rax+00h]
0x14005d45e  mov     rdx, [rbp+57h+var_58]
0x14005d462  mov     rcx, rax
0x14005d465  call    cs:__imp_DEC_SHARE_REF_CNT
0x14005d46c  nop     dword ptr [rax+rax+00h]
0x14005d471  mov     r8d, 1
0x14005d477  mov     [rbp+57h+var_58], r15
0x14005d47b  mov     dl, 5
0x14005d47d  mov     rcx, rbx
0x14005d480  call    cs:__imp_GreDereferenceObject
0x14005d487  nop     dword ptr [rax+rax+00h]
0x14005d48c  mov     [rdi+98h], r15
0x14005d493  mov     [rdi+88h], r15
0x14005d49a  test    rsi, rsi
0x14005d49d  jz      short loc_14005D4A8
0x14005d49f  mov     rcx, [rbp+57h+var_50]
0x14005d4a3  mov     eax, [rsi]
0x14005d4a5  or      [rcx+24h], eax
0x14005d4a8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005d4af  nop     dword ptr [rax+rax+00h]
0x14005d4b4  mov     rcx, [rbp+57h+var_50]
0x14005d4b8  mov     rbx, rax
0x14005d4bb  test    dword ptr [rcx+24h], 200h
0x14005d4c2  jz      loc_14005D5A4
0x14005d4c8  xor     sil, sil
0x14005d4cb  call    cs:__imp_GreGetLockCount
0x14005d4d2  nop     dword ptr [rax+rax+00h]
0x14005d4d7  test    eax, eax
0x14005d4d9  jnz     short loc_14005D4F2
0x14005d4db  mov     rcx, rbx
0x14005d4de  call    ??$GrepIsLockOwnedByCurrentThread@$01USESSION_GLOBALS@Base@Gre@@@@YA_NAEBUSESSION_GLOBALS@Base@Gre@@@Z; GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(Gre::Base::SESSION_GLOBALS const &)
0x14005d4e3  test    al, al
0x14005d4e5  jnz     short loc_14005D4F2
0x14005d4e7  mov     rcx, rbx
0x14005d4ea  call    ??$GreAcquireSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x14005d4ef  mov     sil, 1
0x14005d4f2  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005d4f9  nop     dword ptr [rax+rax+00h]
0x14005d4fe  mov     rdx, rax
0x14005d501  lea     rcx, [rbp+57h+arg_0]
0x14005d505  call    ??0?$SEMOBJSHARED@$02@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<3>::SEMOBJSHARED<3>(Gre::Base::SESSION_GLOBALS &)
0x14005d50a  mov     rcx, [rdi+90h]
0x14005d511  xor     r9d, r9d
0x14005d514  xor     r8d, r8d
0x14005d517  mov     [rsp+0D0h+var_B0], 5
  ... truncated ...
```
