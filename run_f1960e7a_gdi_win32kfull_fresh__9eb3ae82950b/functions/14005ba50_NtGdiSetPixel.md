# NtGdiSetPixel

- ea: `0x14005ba50`
- end: `0x14005c5e6`
- name: `NtGdiSetPixel`
- size: `2966`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400539b0`
- `0x14005b820`
- `0x14005ba50`
- `0x14005d010`
- `0x140067498`
- `0x14006b59c`
- `0x1400a4e80`
- `0x140154d18`
- `0x1401ad190`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14005bb28`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005bb28`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005ba9b`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005bd68`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005c074`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005c4df`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005ba9b`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005bd68`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005c074`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005c4df`
- `win32kbase!HmgPentryFromPobj` at `0x14005bb4e`
- `win32kbase!HmgPentryFromPobj` at `0x14005bb4e`
- `win32kbase!PushThreadGuardedObject` at `0x14005bad0`
- `win32kbase!PushThreadGuardedObject` at `0x14005bbd8`
- `win32kbase!PushThreadGuardedObject` at `0x14005bdb5`
- `win32kbase!PushThreadGuardedObject` at `0x14005bde7`
- `win32kbase!PushThreadGuardedObject` at `0x14005bad0`
- `win32kbase!PushThreadGuardedObject` at `0x14005bbd8`
- `win32kbase!PushThreadGuardedObject` at `0x14005bdb5`
- `win32kbase!PushThreadGuardedObject` at `0x14005bde7`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x14005c092`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x14005c092`
- `win32kbase!rgbFromColorref` at `0x14005c5d0`
- `win32kbase!rgbFromColorref` at `0x14005c5d0`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14005c1c5`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14005c1ee`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14005c1c5`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14005c1ee`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14005c1b4`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14005c1dd`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14005c1b4`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14005c1dd`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14005c27e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14005c2a0`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14005c27e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14005c2a0`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14005c26d`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14005c28f`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14005c26d`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14005c28f`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14005c214`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14005c214`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14005c3a2`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14005c3a2`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14005c232`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14005c232`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14005c24c`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14005c24c`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005bb6f`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005bb6f`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005c53c`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005c53c`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14005bb89`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14005bb89`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14005beee`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14005beee`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14005bedc`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14005bedc`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005baec`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005baec`
- `win32kbase!EngSetLastError` at `0x14005be83`
- `win32kbase!EngSetLastError` at `0x14005be83`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14005bc45`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14005bc45`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14005be3e`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14005be3e`
- `win32kbase!?vDelete@EBRUSHOBJ@@QEAAXXZ` at `0x14005c17e`
- `win32kbase!?vDelete@EBRUSHOBJ@@QEAAXXZ` at `0x14005c17e`
- `win32kbase!ulIndexToRGB` at `0x14005c16b`
- `win32kbase!ulIndexToRGB` at `0x14005c16b`
- `win32kbase!UserSurfaceAccessCheck` at `0x14005c41f`
- `win32kbase!UserSurfaceAccessCheck` at `0x14005c41f`
- `win32kbase!UserScreenAccessCheck` at `0x14005bf0d`
- `win32kbase!UserScreenAccessCheck` at `0x14005bf0d`

## pseudocode

```c
__int64 __fastcall NtGdiSetPixel(Gre::Base *a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  int v4; // esi
  unsigned int v9; // r14d
  __int64 v10; // r8
  __int64 v11; // rax
  DC *v12; // rcx
  unsigned int CurrentProcessId; // eax
  DC *v14; // rbx
  unsigned int v15; // edi
  char *v16; // rsi
  struct _DC_ATTR *UserAttr; // rax
  DC *v18; // rcx
  int v19; // eax
  struct Gre::Base::SESSION_GLOBALS *v20; // rax
  DC *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rdi
  ULONG v24; // ecx
  int v26; // eax
  LONG left; // edx
  int v28; // r10d
  __int64 v29; // rax
  LONG v30; // edx
  int right; // r8d
  int top; // r9d
  LONG v33; // esi
  int *v34; // r11
  int v35; // r10d
  LONG *v36; // rdi
  LONG v37; // ebx
  int *v38; // rax
  __int64 v39; // rdi
  __int64 v40; // rbx
  int v41; // edx
  struct Gre::Base::SESSION_GLOBALS *v42; // r12
  int v43; // edx
  int (*v44)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // rax
  int v45; // edx
  __int64 v46; // r9
  __int64 v47; // r10
  __int64 v48; // r15
  int v49; // r9d
  int v50; // r11d
  int v51; // r10d
  __int64 v52; // rdx
  XCLIPOBJ *v53; // rbx
  struct REGION *v54; // rdx
  int v55; // eax
  __int64 v56; // rbx
  struct Gre::Base::SESSION_GLOBALS *v57; // rax
  int v58; // eax
  __int64 v59; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v61; // [rsp+70h] [rbp-90h] BYREF
  __int64 v62; // [rsp+78h] [rbp-88h] BYREF
  DC *v63; // [rsp+80h] [rbp-80h] BYREF
  int v64; // [rsp+88h] [rbp-78h]
  struct Gre::Base::SESSION_GLOBALS *v65; // [rsp+90h] [rbp-70h]
  __int64 v66; // [rsp+98h] [rbp-68h]
  _OWORD v67[2]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v68[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v69; // [rsp+E0h] [rbp-20h]
  __int64 v70; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int NearestIndexFromColorref; // [rsp+100h] [rbp+0h] BYREF
  __int64 v72; // [rsp+108h] [rbp+8h]
  int v73; // [rsp+110h] [rbp+10h]
  unsigned int v74; // [rsp+118h] [rbp+18h]
  int v75; // [rsp+11Ch] [rbp+1Ch]
  __int64 v76; // [rsp+120h] [rbp+20h]
  __int64 v77; // [rsp+128h] [rbp+28h]
  __int64 v78; // [rsp+158h] [rbp+58h]
  __int128 v79; // [rsp+160h] [rbp+60h]
  int v80; // [rsp+178h] [rbp+78h]
  __int128 v81; // [rsp+190h] [rbp+90h] BYREF
  __int64 v82; // [rsp+1A0h] [rbp+A0h]
  int v83; // [rsp+1A8h] [rbp+A8h]
  __int64 v84; // [rsp+1B0h] [rbp+B0h] BYREF
  int v85; // [rsp+1B8h] [rbp+B8h]
  struct Gre::Base::SESSION_GLOBALS *v86; // [rsp+1C0h] [rbp+C0h]
  __int64 v87; // [rsp+1C8h] [rbp+C8h]
  _OWORD v88[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v89[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int16 v90; // [rsp+210h] [rbp+110h]
  __int64 v91; // [rsp+218h] [rbp+118h]
  __int64 v92; // [rsp+220h] [rbp+120h]
  __int64 v93; // [rsp+228h] [rbp+128h]
  struct _RECTL v94; // [rsp+230h] [rbp+130h] BYREF
  struct _RECTL v95; // [rsp+240h] [rbp+140h] BYREF

  v4 = 0;
  v9 = -1;
  v66 = 0;
  v65 = Gre::Base::Globals(a1);
  v63 = 0;
  v64 = 0;
  memset(v67, 0, sizeof(v67));
  PushThreadGuardedObject(
    v67,
    &v63,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  LOBYTE(v10) = 1;
  v11 = HmgLock(v65, a1, v10);
  v63 = (DC *)v11;
  v12 = (DC *)v11;
  if ( v11 )
  {
    if ( *(_DWORD *)(v11 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v11 + 12));
      v12 = 0;
      v63 = 0;
    }
  }
  else
  {
    if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction(0) != 1 )
      GrepAuditBehaviorRestrictionViolations(1);
    v12 = v63;
  }
  if ( v12 )
  {
    if ( (*((_DWORD *)v12 + 11) & 2) == 0 )
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v14 = v63;
      v15 = CurrentProcessId & 0xFFFFFFFC;
      if ( *(_QWORD *)v63 )
      {
        v16 = (char *)HmgPentryFromPobj(v65, v63);
      }
      else
      {
        v16 = (char *)v63 + 2152;
        *(_OWORD *)((char *)v63 + 2152) = 0;
        *((_QWORD *)v14 + 271) = 0;
        *((_DWORD *)v14 + 540) = -2147483630;
        *((_QWORD *)v14 + 271) = GreEncodeUserModePointer(0);
      }
      if ( v15 == (*((_DWORD *)v16 + 2) & 0xFFFFFFFE) )
      {
        UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v63);
        v4 = 0;
        if ( UserAttr && !DC::SaveAttributes(v63, UserAttr) )
        {
          _InterlockedDecrement16((volatile signed __int16 *)v63 + 6);
          v63 = 0;
          goto LABEL_14;
        }
      }
      else
      {
        v4 = 0;
      }
      *((_DWORD *)v63 + 11) |= 2u;
      v12 = v63;
      v64 = 1;
    }
    if ( (*((_DWORD *)v12 + 130) & 4) != 0 )
      DC::vMarkTransformDirty(v12);
  }
LABEL_14:
  memset(v68, 0, sizeof(v68));
  PushThreadGuardedObject(v68, &v63, UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v69 = 1;
  if ( v63 )
  {
    if ( *((_WORD *)v63 + 6) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( *((_WORD *)v63 + 6) != 1 )
      DCOBJ::vUnlock((DCOBJ *)&v63);
    if ( v63 && (*((_DWORD *)v63 + 9) & 0x10000) == 0 )
    {
      v61 = __PAIR64__(a3, a2);
      DC::QuickInitXform(v63, &v70, 516);
      if ( (*(_BYTE *)(v70 + 32) & 0x43) != 0x43 )
        bCvtPts1(v70, &v61, 1);
      *(_QWORD *)&v94.left = v61;
      v94.right = v61 + 1;
      v18 = v63;
      v94.bottom = HIDWORD(v61) + 1;
      v19 = *((_DWORD *)v63 + 9);
      if ( (v19 & 0xE0) != 0 )
      {
        if ( (v19 & 0x20) != 0 )
        {
          if ( (int)v61 < *((_DWORD *)v63 + 266) )
            *((_DWORD *)v63 + 266) = v61;
          if ( v94.top < *((_DWORD *)v18 + 267) )
            *((_DWORD *)v18 + 267) = v94.top;
          if ( v94.right > *((_DWORD *)v18 + 268) )
            *((_DWORD *)v18 + 268) = v94.right;
          if ( v94.bottom > *((_DWORD *)v18 + 269) )
            *((_DWORD *)v18 + 269) = v94.bottom;
        }
        v18 = v63;
        if ( (*((_DWORD *)v63 + 9) & 0x80u) != 0 )
        {
          if ( v94.left < *((_DWORD *)v63 + 274) )
            *((_DWORD *)v63 + 274) = v94.left;
          if ( v94.top < *((_DWORD *)v18 + 275) )
            *((_DWORD *)v18 + 275) = v94.top;
          if ( v94.right > *((_DWORD *)v18 + 276) )
            *((_DWORD *)v18 + 276) = v94.right;
          if ( v94.bottom > *((_DWORD *)v18 + 277) )
            *((_DWORD *)v18 + 277) = v94.bottom;
        }
      }
      if ( *((_QWORD *)v63 + 62) )
      {
        v84 = 0;
        v85 = 0;
        v20 = Gre::Base::Globals(v18);
        v87 = 0;
        v86 = v20;
        v84 = 0;
        v85 = 0;
        memset(v88, 0, sizeof(v88));
        PushThreadGuardedObject(
          v88,
          &v84,
          UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
        memset(v89, 0, sizeof(v89));
        PushThreadGuardedObject(
          v89,
          &v84,
          UnexpectedThreadTerminationHandler<DLODCOBJ>::OnUnexpectedThreadTerminationStatic);
        v90 = 256;
        v81 = 0;
        v82 = 0;
        v83 = 0;
        v84 = 0;
        v93 = 0;
        v92 = 0;
        v91 = 0;
        if ( !DEVLOCKOBJ::bLock((DEVLOCKOBJ *)&v81, (struct XDCOBJ *)&v63, 0) )
        {
LABEL_47:
          DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)&v81);
          goto LABEL_48;
        }
        v21 = v63;
        v22 = *((_DWORD *)v63 + 10) & 1LL;
        v23 = *((int *)v63 + 2 * v22 + 254);
        if ( (unsigned __int64)(v23 + v94.left + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_45;
        if ( (unsigned __int64)(v23 + v94.right + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_45;
        v56 = *((int *)v63 + 2 * v22 + 255);
        if ( (unsigned __int64)(v56 + v94.top + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_45;
        if ( (unsigned __int64)(v56 + v94.bottom + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_45;
        v48 = *((_QWORD *)v63 + 62);
        left = v23 + v94.left;
        v94.left = left;
        v49 = *((_DWORD *)v63 + 2 * v22 + 254) + v94.right;
        v50 = *((_DWORD *)v63 + 2 * v22 + 255) + v94.top;
        *(_QWORD *)&v94.top = __PAIR64__(v49, v50);
        v51 = *((_DWORD *)v63 + 2 * v22 + 255) + v94.bottom;
        v94.bottom = v51;
        if ( (unsigned int)(left + 134217726) > 0xFFFFFFC
          || (unsigned int)(v49 + 134217726) > 0xFFFFFFC
          || (unsigned int)(v50 + 134217726) > 0xFFFFFFC
          || (unsigned int)(v51 + 134217726) > 0xFFFFFFC )
        {
LABEL_45:
          v24 = 87;
LABEL_46:
          EngSetLastError(v24);
          goto LABEL_47;
        }
        if ( left >= *((_DWORD *)v63 + 250)
          && v49 <= *((_DWORD *)v63 + 252)
          && v50 >= *((_DWORD *)v63 + 251)
          && v51 <= *((_DWORD *)v63 + 253) )
        {
LABEL_99:
          if ( ((*(_DWORD *)(v48 + 148) & 8) != 0 || *(_QWORD *)(v48 + 256))
            && _bittest16((const signed __int16 *)(v48 + 102), 9u) )
          {
            goto LABEL_108;
          }
          v55 = *(_DWORD *)(v48 + 144);
          if ( (v55 & 0x800) != 0 )
          {
            v26 = UserSurfaceAccessCheck(*(_QWORD *)(v48 + 680));
          }
          else
          {
            if ( (v55 & 0x10000000) == 0 )
              goto LABEL_54;
            v26 = UserScreenAccessCheck();
          }
          if ( !v26 )
          {
LABEL_108:
            v24 = 5;
            goto LABEL_46;
          }
          v21 = v63;
          left = v94.left;
LABEL_54:
          v28 = *((_DWORD *)v21 + 9);
          if ( (v28 & 0xE0) == 0 )
            goto LABEL_68;
          v95 = v94;
          v29 = *((_DWORD *)v21 + 10) & 1LL;
          v30 = left - *((_DWORD *)v21 + 2 * v29 + 254);
          v95.left = v30;
          right = v94.right - *((_DWORD *)v21 + 2 * v29 + 254);
          v95.right = right;
          top = v94.top - *((_DWORD *)v21 + 2 * v29 + 255);
          v95.top = top;
          v95.bottom = v94.bottom - *((_DWORD *)v21 + 2 * v29 + 255);
          if ( (v28 & 0x40) == 0 )
          {
LABEL_68:
            v39 = *((_QWORD *)v21 + 11);
            v40 = *(_QWORD *)(v48 + 160);
            v79 = 0;
            v78 = 0;
            v72 = 0;
            v73 = 0;
            v75 = -1;
            v76 = 0;
            v77 = 0;
            v80 = 0;
            v41 = *((_DWORD *)v21 + 30);
            if ( (v41 & 1) != 0 && *(_QWORD *)(*((_QWORD *)v21 + 122) + 248LL) && (v41 & 0x10000000) != 0 )
            {
              v57 = Gre::Base::Globals(v21);
              NearestIndexFromColorref = a4;
              v73 = 6;
              if ( *((_DWORD *)v57 + 788) )
              {
                v74 = a4;
                v75 = a4;
              }
              v4 = 1;
            }
            else
            {
              v42 = Gre::Base::Globals(v21);
              NearestIndexFromColorref = ulGetNearestIndexFromColorref(v40, v39, a4, 1);
              v43 = *((_DWORD *)v63 + 30);
              if ( (v43 & 5) != 0 )
              {
                v73 = 2;
              }
              else
              {
                v58 = v73;
                if ( (v43 & 2) != 0 )
                  v58 = 1;
                v73 = v58;
              }
              if ( *((_DWORD *)v42 + 788) )
              {
                v74 = a4;
                v75 = rgbFromColorref(v40, v39, a4);
                v4 = 0;
              }
            }
            ++*(_DWORD *)(v48 + 92);
            v44 = SURFACE::pfnBitBlt((SURFACE *)v48);
            if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, struct _RECTL *, _QWORD, _QWORD, unsigned int *, __int64, int))v44)(
                   v47 & -(__int64)(v48 != 0),
                   0,
                   0,
                   0,
                   0,
                   &v94,
                   0,
                   0,
                   &NearestIndexFromColorref,
                   v46 + 1192,
                   v45 | (v45 << 8)) )
            {
              if ( v4 )
                v9 = NearestIndexFromColorref;
              else
                v9 = ulIndexToRGB(v40, v39, NearestIndexFromColorref);
            }
            EBRUSHOBJ::vDelete((EBRUSHOBJ *)&NearestIndexFromColorref);
            goto LABEL_47;
          }
          v33 = *((_DWORD *)v21 + 270);
          v34 = (int *)((char *)v21 + 1088);
          v35 = *((_DWORD *)v21 + 272);
          if ( v33 == v35
            || (v36 = (LONG *)((char *)v21 + 1092),
                v37 = *((_DWORD *)v21 + 273),
                v38 = (int *)((char *)v21 + 1084),
                *((_DWORD *)v21 + 271) == v37) )
          {
            *(struct _RECTL *)((char *)v21 + 1080) = v95;
          }
          else
          {
            if ( v30 < v33 )
            {
              v35 = *v34;
              v37 = *v36;
              *((_DWORD *)v21 + 270) = v30;
              v21 = v63;
              right = v95.right;
              top = v95.top;
            }
            if ( top < *v38 )
            {
              *v38 = top;
              v21 = v63;
              right = v95.right;
            }
            if ( right > v35 )
            {
              *v34 = right;
              v21 = v63;
            }
            if ( v95.bottom <= v37 )
              goto LABEL_67;
            *v36 = v95.bottom;
          }
          v21 = v63;
LABEL_67:
          v4 = 0;
          v62 = *((_QWORD *)v21 + 148);
          if ( v62 )
          {
            v60 = 0;
            RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v60, 0x70u);
            RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v60);
            v59 = 0;
            RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v59, 0x70u);
            RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v59);
            if ( v60 )
            {
              if ( v59 )
              {
                RGNOBJ::vSet((RGNOBJ *)&v59, &v95);
                if ( RGNOBJ::bMerge((RGNOBJ *)&v60, (struct RGNOBJ *)&v62, (struct RGNOBJ *)&v59, 0xEu) )
                {
                  RGNOBJ::vSwap((RGNOBJ *)&v62, (struct RGNOBJ *)&v60);
                  *((_QWORD *)v63 + 148) = v62;
                }
              }
            }
            RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v59);
            RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v59);
            RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v60);
            RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v60);
            v21 = v63;
          }
          goto LABEL_68;
        }
        v52 = *((_QWORD *)v63 + 146);
        v53 = (DC *)((char *)v63 + 1768);
        if ( !v52 || (*((_DWORD *)v63 + 10) & 2) == 0 || !(unsigned int)DC::bDpiScaledSurface(v63) )
        {
          if ( !*((_QWORD *)v21 + 144) )
          {
            if ( !*((_QWORD *)v21 + 145)
              || (*((_DWORD *)v21 + 10) & 2) == 0
              || !(unsigned int)DC::bDpiScaledSurface(v21) )
            {
              v54 = (struct REGION *)*((_QWORD *)v21 + 143);
            }
            goto LABEL_96;
          }
          if ( !v52 )
            goto LABEL_95;
        }
        if ( (*((_DWORD *)v21 + 10) & 2) == 0 || !(unsigned int)DC::bDpiScaledSurface(v21) )
LABEL_95:
          v54 = (struct REGION *)*((_QWORD *)v21 + 144);
LABEL_96:
        XCLIPOBJ::vSetup(v53, v54, (const struct ERECTL *)&v94, 2);
        if ( *((_DWORD *)v53 + 1) == *((_DWORD *)v53 + 3) || *((_DWORD *)v53 + 2) == *((_DWORD *)v53 + 4) )
          goto LABEL_47;
        v21 = v63;
        left = v94.left;
        goto LABEL_99;
      }
    }
  }
LABEL_48:
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v63);
  return v9;
}

```

## disassembly

```asm
0x14005ba50  mov     [rsp-8+arg_10], rbx
0x14005ba55  push    rbp
0x14005ba56  push    rsi
0x14005ba57  push    rdi
0x14005ba58  push    r12
0x14005ba5a  push    r13
0x14005ba5c  push    r14
0x14005ba5e  push    r15
0x14005ba60  lea     rbp, [rsp-160h]
0x14005ba68  sub     rsp, 260h
0x14005ba6f  mov     rax, cs:__security_cookie
0x14005ba76  xor     rax, rsp
0x14005ba79  mov     [rbp+190h+var_40], rax
0x14005ba80  xor     esi, esi
0x14005ba82  mov     r13d, r9d
0x14005ba85  mov     [rbp+190h+var_210], rsi
0x14005ba89  mov     r15d, r8d
0x14005ba8c  mov     [rbp+190h+var_208], esi
0x14005ba8f  mov     r12d, edx
0x14005ba92  mov     rbx, rcx
0x14005ba95  mov     r14d, 0FFFFFFFFh
0x14005ba9b  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005baa2  nop     dword ptr [rax+rax+00h]
0x14005baa7  xorps   xmm0, xmm0
0x14005baaa  mov     [rbp+190h+var_1F8], rsi
0x14005baae  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14005bab5  mov     [rbp+190h+var_200], rax
0x14005bab9  lea     rdx, [rbp+190h+var_210]
0x14005babd  mov     [rbp+190h+var_210], rsi
0x14005bac1  lea     rcx, [rbp+190h+var_1F0]
0x14005bac5  mov     [rbp+190h+var_208], esi
0x14005bac8  movups  [rbp+190h+var_1F0], xmm0
0x14005bacc  movups  [rbp+190h+var_1E0], xmm0
0x14005bad0  call    cs:__imp_PushThreadGuardedObject
0x14005bad7  nop     dword ptr [rax+rax+00h]
0x14005badc  mov     rcx, [rbp+190h+var_200]
0x14005bae0  lea     edi, [rsi+1]
0x14005bae3  mov     r8b, dil
0x14005bae6  xor     r9d, r9d
0x14005bae9  mov     rdx, rbx
0x14005baec  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14005baf3  nop     dword ptr [rax+rax+00h]
0x14005baf8  mov     [rbp+190h+var_210], rax
0x14005bafc  mov     rcx, rax
0x14005baff  test    rax, rax
0x14005bb02  jz      loc_14005BEDC
0x14005bb08  cmp     [rax+858h], esi
0x14005bb0e  jnz     loc_14005C50C
0x14005bb14  test    rcx, rcx
0x14005bb17  jz      loc_14005BBBE
0x14005bb1d  mov     eax, [rcx+2Ch]
0x14005bb20  test    al, 2
0x14005bb22  jnz     loc_14005BBB0
0x14005bb28  call    cs:__imp_PsGetCurrentProcessId
0x14005bb2f  nop     dword ptr [rax+rax+00h]
0x14005bb34  mov     rbx, [rbp+190h+var_210]
0x14005bb38  mov     rdi, rax
0x14005bb3b  and     edi, 0FFFFFFFCh
0x14005bb3e  cmp     [rbx], rsi
0x14005bb41  jz      loc_14005C51D
0x14005bb47  mov     rcx, [rbp+190h+var_200]
0x14005bb4b  mov     rdx, rbx
0x14005bb4e  call    cs:__imp_HmgPentryFromPobj
0x14005bb55  nop     dword ptr [rax+rax+00h]
0x14005bb5a  mov     rsi, rax
0x14005bb5d  mov     eax, [rsi+8]
0x14005bb60  and     eax, 0FFFFFFFEh
0x14005bb63  cmp     edi, eax
0x14005bb65  jnz     loc_14005C566
0x14005bb6b  lea     rcx, [rbp+190h+var_210]
0x14005bb6f  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14005bb76  nop     dword ptr [rax+rax+00h]
0x14005bb7b  xor     esi, esi
0x14005bb7d  test    rax, rax
0x14005bb80  jz      short loc_14005BB9D
0x14005bb82  mov     rcx, [rbp+190h+var_210]
0x14005bb86  mov     rdx, rax
0x14005bb89  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x14005bb90  nop     dword ptr [rax+rax+00h]
0x14005bb95  test    eax, eax
0x14005bb97  jz      loc_14005C554
0x14005bb9d  mov     rax, [rbp+190h+var_210]
0x14005bba1  or      dword ptr [rax+2Ch], 2
0x14005bba5  mov     rcx, [rbp+190h+var_210]; this
0x14005bba9  mov     [rbp+190h+var_208], 1
0x14005bbb0  mov     eax, [rcx+208h]
0x14005bbb6  test    al, 4
0x14005bbb8  jnz     loc_14005BED2
0x14005bbbe  xorps   xmm0, xmm0
0x14005bbc1  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14005bbc8  lea     rdx, [rbp+190h+var_210]
0x14005bbcc  lea     rcx, [rbp+190h+var_1D0]
0x14005bbd0  movups  [rbp+190h+var_1D0], xmm0
0x14005bbd4  movups  [rbp+190h+var_1C0], xmm0
0x14005bbd8  call    cs:__imp_PushThreadGuardedObject
0x14005bbdf  nop     dword ptr [rax+rax+00h]
0x14005bbe4  mov     rax, [rbp+190h+var_210]
0x14005bbe8  mov     ebx, 1
0x14005bbed  mov     [rbp+190h+var_1B0], bl
0x14005bbf0  test    rax, rax
0x14005bbf3  jz      loc_14005BE9B
0x14005bbf9  movzx   eax, word ptr [rax+0Ch]
0x14005bbfd  cmp     ax, bx
0x14005bc00  jnz     loc_14005BF03
0x14005bc06  mov     rax, [rbp+190h+var_210]
0x14005bc0a  movzx   ecx, word ptr [rax+0Ch]
0x14005bc0e  cmp     cx, bx
0x14005bc11  jnz     loc_14005C56D
0x14005bc17  mov     rcx, [rbp+190h+var_210]
0x14005bc1b  test    rcx, rcx
0x14005bc1e  jz      loc_14005BE9B
0x14005bc24  test    dword ptr [rcx+24h], 10000h
0x14005bc2b  jnz     loc_14005BE9B
0x14005bc31  mov     r8d, 204h
0x14005bc37  mov     dword ptr [rsp+290h+var_220], r12d
0x14005bc3c  lea     rdx, [rbp+190h+var_1A0]
0x14005bc40  mov     dword ptr [rsp+290h+var_220+4], r15d
0x14005bc45  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x14005bc4c  nop     dword ptr [rax+rax+00h]
0x14005bc51  mov     rcx, [rbp+190h+var_1A0]
0x14005bc55  mov     eax, [rcx+20h]
0x14005bc58  and     eax, 43h
0x14005bc5b  cmp     al, 43h ; 'C'
0x14005bc5d  jz      short loc_14005BC6C
0x14005bc5f  mov     r8, rbx
0x14005bc62  lea     rdx, [rsp+290h+var_220]
0x14005bc67  call    bCvtPts1
0x14005bc6c  mov     ecx, dword ptr [rsp+290h+var_220+4]
0x14005bc70  mov     edx, dword ptr [rsp+290h+var_220]
0x14005bc74  mov     dword ptr [rbp+190h+var_60+4], ecx
0x14005bc7a  mov     dword ptr [rbp+190h+var_60], edx
0x14005bc80  lea     eax, [rdx+1]
0x14005bc83  mov     dword ptr [rbp+190h+var_60+8], eax
0x14005bc89  lea     eax, [rcx+1]
0x14005bc8c  mov     rcx, [rbp+190h+var_210]
0x14005bc90  mov     dword ptr [rbp+190h+var_60+0Ch], eax
0x14005bc96  mov     eax, [rcx+24h]
0x14005bc99  test    al, 0E0h
0x14005bc9b  jz      loc_14005BD4A
0x14005bca1  test    al, 20h
0x14005bca3  jz      short loc_14005BCEF
0x14005bca5  cmp     edx, [rcx+428h]
0x14005bcab  jge     short loc_14005BCB3
0x14005bcad  mov     [rcx+428h], edx
0x14005bcb3  mov     eax, dword ptr [rbp+190h+var_60+4]
0x14005bcb9  cmp     eax, [rcx+42Ch]
0x14005bcbf  jge     short loc_14005BCC7
0x14005bcc1  mov     [rcx+42Ch], eax
0x14005bcc7  mov     eax, dword ptr [rbp+190h+var_60+8]
0x14005bccd  cmp     eax, [rcx+430h]
0x14005bcd3  jle     short loc_14005BCDB
0x14005bcd5  mov     [rcx+430h], eax
0x14005bcdb  mov     eax, dword ptr [rbp+190h+var_60+0Ch]
0x14005bce1  cmp     eax, [rcx+434h]
0x14005bce7  jle     short loc_14005BCEF
0x14005bce9  mov     [rcx+434h], eax
0x14005bcef  mov     rcx, [rbp+190h+var_210]
0x14005bcf3  mov     eax, [rcx+24h]
0x14005bcf6  test    al, al
0x14005bcf8  jns     short loc_14005BD4A
0x14005bcfa  mov     eax, dword ptr [rbp+190h+var_60]
0x14005bd00  cmp     eax, [rcx+448h]
0x14005bd06  jge     short loc_14005BD0E
0x14005bd08  mov     [rcx+448h], eax
0x14005bd0e  mov     eax, dword ptr [rbp+190h+var_60+4]
0x14005bd14  cmp     eax, [rcx+44Ch]
0x14005bd1a  jge     short loc_14005BD22
0x14005bd1c  mov     [rcx+44Ch], eax
0x14005bd22  mov     eax, dword ptr [rbp+190h+var_60+8]
0x14005bd28  cmp     eax, [rcx+450h]
0x14005bd2e  jle     short loc_14005BD36
0x14005bd30  mov     [rcx+450h], eax
0x14005bd36  mov     eax, dword ptr [rbp+190h+var_60+0Ch]
0x14005bd3c  cmp     eax, [rcx+454h]
0x14005bd42  jle     short loc_14005BD4A
0x14005bd44  mov     [rcx+454h], eax
0x14005bd4a  mov     rax, [rbp+190h+var_210]
0x14005bd4e  cmp     [rax+1F0h], rsi
0x14005bd55  jz      loc_14005BE9B
0x14005bd5b  mov     [rbp+190h+var_E0], rsi
0x14005bd62  mov     [rbp+190h+var_D8], esi
0x14005bd68  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005bd6f  nop     dword ptr [rax+rax+00h]
0x14005bd74  xorps   xmm0, xmm0
0x14005bd77  mov     [rbp+190h+var_C8], rsi
0x14005bd7e  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14005bd85  mov     [rbp+190h+var_D0], rax
0x14005bd8c  lea     rdx, [rbp+190h+var_E0]
0x14005bd93  mov     [rbp+190h+var_E0], rsi
0x14005bd9a  lea     rcx, [rbp+190h+var_C0]
0x14005bda1  mov     [rbp+190h+var_D8], esi
0x14005bda7  movups  [rbp+190h+var_C0], xmm0
0x14005bdae  movups  [rbp+190h+var_B0], xmm0
0x14005bdb5  call    cs:__imp_PushThreadGuardedObject
0x14005bdbc  nop     dword ptr [rax+rax+00h]
0x14005bdc1  xorps   xmm0, xmm0
0x14005bdc4  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDLODCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DLODCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14005bdcb  lea     rdx, [rbp+190h+var_E0]
0x14005bdd2  lea     rcx, [rbp+190h+var_A0]
0x14005bdd9  movups  [rbp+190h+var_A0], xmm0
0x14005bde0  movups  [rbp+190h+var_90], xmm0
0x14005bde7  call    cs:__imp_PushThreadGuardedObject
0x14005bdee  nop     dword ptr [rax+rax+00h]
0x14005bdf3  xorps   xmm0, xmm0
0x14005bdf6  mov     [rbp+190h+var_80], 100h
0x14005bdff  xor     r8d, r8d
0x14005be02  movdqa  [rbp+190h+var_100], xmm0
0x14005be0a  lea     rdx, [rbp+190h+var_210]
0x14005be0e  mov     [rbp+190h+var_F0], rsi
0x14005be15  lea     rcx, [rbp+190h+var_100]
0x14005be1c  mov     [rbp+190h+var_E8], esi
0x14005be22  mov     [rbp+190h+var_E0], rsi
0x14005be29  mov     [rbp+190h+var_68], rsi
0x14005be30  mov     [rbp+190h+var_70], rsi
0x14005be37  mov     [rbp+190h+var_78], rsi
0x14005be3e  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x14005be45  nop     dword ptr [rax+rax+00h]
0x14005be4a  test    eax, eax
0x14005be4c  jz      short loc_14005BE8F
0x14005be4e  mov     rcx, [rbp+190h+var_210]; this
0x14005be52  mov     r15d, 80000000h
0x14005be58  movsxd  rdx, dword ptr [rbp+190h+var_60]
0x14005be5f  mov     r8d, [rcx+28h]
0x14005be63  and     r8, rbx
0x14005be66  movsxd  rdi, dword ptr [rcx+r8*8+3F8h]
0x14005be6e  lea     rax, [rdi+rdx]
0x14005be72  add     rax, r15
0x14005be75  cmp     rax, r14
0x14005be78  jbe     loc_14005C48D
0x14005be7e  mov     ecx, 57h ; 'W'; iError
0x14005be83  call    cs:__imp_EngSetLastError
0x14005be8a  nop     dword ptr [rax+rax+00h]
0x14005be8f  lea     rcx, [rbp+190h+var_100]; this
0x14005be96  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x14005be9b  lea     rcx, [rbp+190h+var_210]; this
0x14005be9f  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x14005bea4  mov     eax, r14d
0x14005bea7  mov     rcx, [rbp+190h+var_40]
0x14005beae  xor     rcx, rsp; StackCookie
0x14005beb1  call    __security_check_cookie
0x14005beb6  mov     rbx, [rsp+290h+arg_10]
0x14005bebe  add     rsp, 260h
0x14005bec5  pop     r15
0x14005bec7  pop     r14
0x14005bec9  pop     r13
0x14005becb  pop     r12
0x14005becd  pop     rdi
0x14005bece  pop     rsi
0x14005becf  pop     rbp
0x14005bed0  retn
0x14005bed2  call    ?vMarkTransformDirty@DC@@QEAAXXZ; DC::vMarkTransformDirty(void)
0x14005bed7  jmp     loc_14005BBBE
0x14005bedc  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x14005bee3  nop     dword ptr [rax+rax+00h]
0x14005bee8  cmp     eax, edi
0x14005beea  jz      short loc_14005BEFA
0x14005beec  mov     ecx, edi
0x14005beee  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x14005bef5  nop     dword ptr [rax+rax+00h]
0x14005befa  mov     rcx, [rbp+190h+var_210]
0x14005befe  jmp     loc_14005BB14
0x14005bf03  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14005bf08  jmp     loc_14005BC06
0x14005bf0d  call    cs:__imp_UserScreenAccessCheck
0x14005bf14  nop     dword ptr [rax+rax+00h]
0x14005bf19  test    eax, eax
0x14005bf1b  jz      loc_14005C439
0x14005bf21  mov     rcx, [rbp+190h+var_210]
0x14005bf25  mov     edx, dword ptr [rbp+190h+var_60]
0x14005bf2b  mov     r10d, [rcx+24h]
0x14005bf2f  test    r10b, 0E0h
0x14005bf33  jz      loc_14005C037
0x14005bf39  movaps  xmm0, [rbp+190h+var_60]
0x14005bf40  movdqa  [rbp+190h+var_50], xmm0
0x14005bf48  mov     eax, [rcx+28h]
0x14005bf4b  mov     r8d, dword ptr [rbp+190h+var_50+8]
0x14005bf52  and     rax, 1
0x14005bf56  mov     r9d, dword ptr [rbp+190h+var_50+4]
0x14005bf5d  sub     edx, [rcx+rax*8+3F8h]
0x14005bf64  mov     dword ptr [rbp+190h+var_50], edx
0x14005bf6a  sub     r8d, [rcx+rax*8+3F8h]
0x14005bf72  mov     dword ptr [rbp+190h+var_50+8], r8d
0x14005bf79  sub     r9d, [rcx+rax*8+3FCh]
0x14005bf81  mov     dword ptr [rbp+190h+var_50+4], r9d
0x14005bf88  mov     eax, [rcx+rax*8+3FCh]
0x14005bf8f  sub     dword ptr [rbp+190h+var_50+0Ch], eax
0x14005bf95  test    r10b, 40h
0x14005bf99  jz      loc_14005C037
0x14005bf9f  mov     esi, [rcx+438h]
0x14005bfa5  lea     r11, [rcx+440h]
0x14005bfac  mov     r10d, [r11]
0x14005bfaf  cmp     esi, r10d
0x14005bfb2  jz      loc_14005C18F
0x14005bfb8  lea     rdi, [rcx+444h]
0x14005bfbf  mov     ebx, [rdi]
0x14005bfc1  lea     rax, [rcx+43Ch]
0x14005bfc8  cmp     [rax], ebx
0x14005bfca  jz      loc_14005C18F
0x14005bfd0  cmp     edx, esi
0x14005bfd2  jge     short loc_14005BFF1
  ... truncated ...
```
