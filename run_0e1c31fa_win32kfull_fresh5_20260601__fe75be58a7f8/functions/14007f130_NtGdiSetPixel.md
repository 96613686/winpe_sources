# NtGdiSetPixel

- ea: `0x14007f130`
- end: `0x14007fc03`
- name: `NtGdiSetPixel`
- size: `2771`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400604f0`
- `0x14006a090`
- `0x14006ba5c`
- `0x1400781e8`
- `0x14007eef8`
- `0x14007f130`
- `0x140080590`
- `0x140164228`
- `0x14016cabc`
- `0x140303af4`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14007f208`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007f208`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007f17b`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007f694`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007fafc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007f17b`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007f694`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14007fafc`
- `win32kbase!HmgPentryFromPobj` at `0x14007f22e`
- `win32kbase!HmgPentryFromPobj` at `0x14007f22e`
- `win32kbase!PushThreadGuardedObject` at `0x14007f1b0`
- `win32kbase!PushThreadGuardedObject` at `0x14007f2b8`
- `win32kbase!PushThreadGuardedObject` at `0x14007f1b0`
- `win32kbase!PushThreadGuardedObject` at `0x14007f2b8`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x14007f6b2`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x14007f6b2`
- `win32kbase!rgbFromColorref` at `0x14007fbed`
- `win32kbase!rgbFromColorref` at `0x14007fbed`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14007f7e5`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14007f80e`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14007f7e5`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14007f80e`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14007f7d4`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14007f7fd`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14007f7d4`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14007f7fd`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14007f89e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14007f8c0`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14007f89e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14007f8c0`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14007f88d`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14007f8af`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14007f88d`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14007f8af`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14007f834`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14007f834`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14007f9bf`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14007f9bf`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14007f852`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14007f852`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14007f86c`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14007f86c`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14007f24f`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14007f24f`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14007fb59`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14007fb59`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14007f269`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14007f269`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14007f50e`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14007f50e`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14007f4fc`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14007f4fc`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14007f1cc`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14007f1cc`
- `win32kbase!EngSetLastError` at `0x14007f4a3`
- `win32kbase!EngSetLastError` at `0x14007f4a3`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14007f325`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14007f325`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14007f45e`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14007f45e`
- `win32kbase!?vDelete@EBRUSHOBJ@@QEAAXXZ` at `0x14007f79e`
- `win32kbase!?vDelete@EBRUSHOBJ@@QEAAXXZ` at `0x14007f79e`
- `win32kbase!ulIndexToRGB` at `0x14007f78b`
- `win32kbase!ulIndexToRGB` at `0x14007f78b`
- `win32kbase!UserSurfaceAccessCheck` at `0x14007fa39`
- `win32kbase!UserSurfaceAccessCheck` at `0x14007fa39`
- `win32kbase!UserScreenAccessCheck` at `0x14007f52d`
- `win32kbase!UserScreenAccessCheck` at `0x14007f52d`

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
  DC *v20; // rcx
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
  _BYTE v81[176]; // [rsp+190h] [rbp+90h] BYREF
  struct _RECTL v82; // [rsp+240h] [rbp+140h] BYREF
  struct _RECTL v83; // [rsp+250h] [rbp+150h] BYREF

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
      *(_QWORD *)&v82.left = v61;
      v82.right = v61 + 1;
      v18 = v63;
      v82.bottom = HIDWORD(v61) + 1;
      v19 = *((_DWORD *)v63 + 9);
      if ( (v19 & 0xE0) != 0 )
      {
        if ( (v19 & 0x20) != 0 )
        {
          if ( (int)v61 < *((_DWORD *)v63 + 266) )
            *((_DWORD *)v63 + 266) = v61;
          if ( v82.top < *((_DWORD *)v18 + 267) )
            *((_DWORD *)v18 + 267) = v82.top;
          if ( v82.right > *((_DWORD *)v18 + 268) )
            *((_DWORD *)v18 + 268) = v82.right;
          if ( v82.bottom > *((_DWORD *)v18 + 269) )
            *((_DWORD *)v18 + 269) = v82.bottom;
        }
        v20 = v63;
        if ( (*((_DWORD *)v63 + 9) & 0x80u) != 0 )
        {
          if ( v82.left < *((_DWORD *)v63 + 274) )
            *((_DWORD *)v63 + 274) = v82.left;
          if ( v82.top < *((_DWORD *)v20 + 275) )
            *((_DWORD *)v20 + 275) = v82.top;
          if ( v82.right > *((_DWORD *)v20 + 276) )
            *((_DWORD *)v20 + 276) = v82.right;
          if ( v82.bottom > *((_DWORD *)v20 + 277) )
            *((_DWORD *)v20 + 277) = v82.bottom;
        }
      }
      if ( *((_QWORD *)v63 + 62) )
      {
        DEVLOCKOBJ::DEVLOCKOBJ(v81, 2);
        if ( !DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v81, (struct XDCOBJ *)&v63, 0) )
        {
LABEL_47:
          DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v81);
          goto LABEL_48;
        }
        v21 = v63;
        v22 = *((_DWORD *)v63 + 10) & 1LL;
        v23 = *((int *)v63 + 2 * v22 + 254);
        if ( (unsigned __int64)(v23 + v82.left + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_45;
        if ( (unsigned __int64)(v23 + v82.right + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_45;
        v56 = *((int *)v63 + 2 * v22 + 255);
        if ( (unsigned __int64)(v56 + v82.top + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_45;
        if ( (unsigned __int64)(v56 + v82.bottom + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_45;
        v48 = *((_QWORD *)v63 + 62);
        left = v23 + v82.left;
        v82.left = left;
        v49 = *((_DWORD *)v63 + 2 * v22 + 254) + v82.right;
        v50 = *((_DWORD *)v63 + 2 * v22 + 255) + v82.top;
        *(_QWORD *)&v82.top = __PAIR64__(v49, v50);
        v51 = *((_DWORD *)v63 + 2 * v22 + 255) + v82.bottom;
        v82.bottom = v51;
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
          if ( ((*(_DWORD *)(v48 + 164) & 8) != 0 || *(_QWORD *)(v48 + 272))
            && _bittest16((const signed __int16 *)(v48 + 102), 9u) )
          {
            goto LABEL_108;
          }
          v55 = *(_DWORD *)(v48 + 160);
          if ( (v55 & 0x800) != 0 )
          {
            v26 = UserSurfaceAccessCheck(*(_QWORD *)(v48 + 696));
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
          left = v82.left;
LABEL_54:
          v28 = *((_DWORD *)v21 + 9);
          if ( (v28 & 0xE0) == 0 )
            goto LABEL_68;
          v83 = v82;
          v29 = *((_DWORD *)v21 + 10) & 1LL;
          v30 = left - *((_DWORD *)v21 + 2 * v29 + 254);
          v83.left = v30;
          right = v82.right - *((_DWORD *)v21 + 2 * v29 + 254);
          v83.right = right;
          top = v82.top - *((_DWORD *)v21 + 2 * v29 + 255);
          v83.top = top;
          v83.bottom = v82.bottom - *((_DWORD *)v21 + 2 * v29 + 255);
          if ( (v28 & 0x40) == 0 )
          {
LABEL_68:
            v39 = *((_QWORD *)v21 + 11);
            v40 = *(_QWORD *)(v48 + 176);
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
                   &v82,
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
            *(struct _RECTL *)((char *)v21 + 1080) = v83;
          }
          else
          {
            if ( v30 < v33 )
            {
              v35 = *v34;
              v37 = *v36;
              *((_DWORD *)v21 + 270) = v30;
              v21 = v63;
              right = v83.right;
              top = v83.top;
            }
            if ( top < *v38 )
            {
              *v38 = top;
              v21 = v63;
              right = v83.right;
            }
            if ( right > v35 )
            {
              *v34 = right;
              v21 = v63;
            }
            if ( v83.bottom <= v37 )
              goto LABEL_67;
            *v36 = v83.bottom;
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
                RGNOBJ::vSet((RGNOBJ *)&v59, &v83);
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
        XCLIPOBJ::vSetup(v53, v54, (const struct ERECTL *)&v82, 2);
        if ( *((_DWORD *)v53 + 1) == *((_DWORD *)v53 + 3) || *((_DWORD *)v53 + 2) == *((_DWORD *)v53 + 4) )
          goto LABEL_47;
        v21 = v63;
        left = v82.left;
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
0x14007f130  mov     [rsp-8+arg_10], rbx
0x14007f135  push    rbp
0x14007f136  push    rsi
0x14007f137  push    rdi
0x14007f138  push    r12
0x14007f13a  push    r13
0x14007f13c  push    r14
0x14007f13e  push    r15
0x14007f140  lea     rbp, [rsp-170h]
0x14007f148  sub     rsp, 270h
0x14007f14f  mov     rax, cs:__security_cookie
0x14007f156  xor     rax, rsp
0x14007f159  mov     [rbp+1A0h+var_40], rax
0x14007f160  xor     esi, esi
0x14007f162  mov     r13d, r9d
0x14007f165  mov     [rbp+1A0h+var_220], rsi
0x14007f169  mov     r15d, r8d
0x14007f16c  mov     [rbp+1A0h+var_218], esi
0x14007f16f  mov     r12d, edx
0x14007f172  mov     rbx, rcx
0x14007f175  mov     r14d, 0FFFFFFFFh
0x14007f17b  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14007f182  nop     dword ptr [rax+rax+00h]
0x14007f187  xorps   xmm0, xmm0
0x14007f18a  mov     [rbp+1A0h+var_208], rsi
0x14007f18e  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14007f195  mov     [rbp+1A0h+var_210], rax
0x14007f199  lea     rdx, [rbp+1A0h+var_220]
0x14007f19d  mov     [rbp+1A0h+var_220], rsi
0x14007f1a1  lea     rcx, [rbp+1A0h+var_200]
0x14007f1a5  mov     [rbp+1A0h+var_218], esi
0x14007f1a8  movups  [rbp+1A0h+var_200], xmm0
0x14007f1ac  movups  [rbp+1A0h+var_1F0], xmm0
0x14007f1b0  call    cs:__imp_PushThreadGuardedObject
0x14007f1b7  nop     dword ptr [rax+rax+00h]
0x14007f1bc  mov     rcx, [rbp+1A0h+var_210]
0x14007f1c0  lea     edi, [rsi+1]
0x14007f1c3  mov     r8b, dil
0x14007f1c6  xor     r9d, r9d
0x14007f1c9  mov     rdx, rbx
0x14007f1cc  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14007f1d3  nop     dword ptr [rax+rax+00h]
0x14007f1d8  mov     [rbp+1A0h+var_220], rax
0x14007f1dc  mov     rcx, rax
0x14007f1df  test    rax, rax
0x14007f1e2  jz      loc_14007F4FC
0x14007f1e8  cmp     [rax+858h], esi
0x14007f1ee  jnz     loc_14007FB29
0x14007f1f4  test    rcx, rcx
0x14007f1f7  jz      loc_14007F29E
0x14007f1fd  mov     eax, [rcx+2Ch]
0x14007f200  test    al, 2
0x14007f202  jnz     loc_14007F290
0x14007f208  call    cs:__imp_PsGetCurrentProcessId
0x14007f20f  nop     dword ptr [rax+rax+00h]
0x14007f214  mov     rbx, [rbp+1A0h+var_220]
0x14007f218  mov     rdi, rax
0x14007f21b  and     edi, 0FFFFFFFCh
0x14007f21e  cmp     [rbx], rsi
0x14007f221  jz      loc_14007FB3A
0x14007f227  mov     rcx, [rbp+1A0h+var_210]
0x14007f22b  mov     rdx, rbx
0x14007f22e  call    cs:__imp_HmgPentryFromPobj
0x14007f235  nop     dword ptr [rax+rax+00h]
0x14007f23a  mov     rsi, rax
0x14007f23d  mov     eax, [rsi+8]
0x14007f240  and     eax, 0FFFFFFFEh
0x14007f243  cmp     edi, eax
0x14007f245  jnz     loc_14007FB83
0x14007f24b  lea     rcx, [rbp+1A0h+var_220]
0x14007f24f  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14007f256  nop     dword ptr [rax+rax+00h]
0x14007f25b  xor     esi, esi
0x14007f25d  test    rax, rax
0x14007f260  jz      short loc_14007F27D
0x14007f262  mov     rcx, [rbp+1A0h+var_220]
0x14007f266  mov     rdx, rax
0x14007f269  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x14007f270  nop     dword ptr [rax+rax+00h]
0x14007f275  test    eax, eax
0x14007f277  jz      loc_14007FB71
0x14007f27d  mov     rax, [rbp+1A0h+var_220]
0x14007f281  or      dword ptr [rax+2Ch], 2
0x14007f285  mov     rcx, [rbp+1A0h+var_220]; this
0x14007f289  mov     [rbp+1A0h+var_218], 1
0x14007f290  mov     eax, [rcx+208h]
0x14007f296  test    al, 4
0x14007f298  jnz     loc_14007F4F2
0x14007f29e  xorps   xmm0, xmm0
0x14007f2a1  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14007f2a8  lea     rdx, [rbp+1A0h+var_220]
0x14007f2ac  lea     rcx, [rbp+1A0h+var_1E0]
0x14007f2b0  movups  [rbp+1A0h+var_1E0], xmm0
0x14007f2b4  movups  [rbp+1A0h+var_1D0], xmm0
0x14007f2b8  call    cs:__imp_PushThreadGuardedObject
0x14007f2bf  nop     dword ptr [rax+rax+00h]
0x14007f2c4  mov     rax, [rbp+1A0h+var_220]
0x14007f2c8  mov     ebx, 1
0x14007f2cd  mov     [rbp+1A0h+var_1C0], bl
0x14007f2d0  test    rax, rax
0x14007f2d3  jz      loc_14007F4BB
0x14007f2d9  movzx   eax, word ptr [rax+0Ch]
0x14007f2dd  cmp     ax, bx
0x14007f2e0  jnz     loc_14007F523
0x14007f2e6  mov     rax, [rbp+1A0h+var_220]
0x14007f2ea  movzx   ecx, word ptr [rax+0Ch]
0x14007f2ee  cmp     cx, bx
0x14007f2f1  jnz     loc_14007FB8A
0x14007f2f7  mov     rcx, [rbp+1A0h+var_220]
0x14007f2fb  test    rcx, rcx
0x14007f2fe  jz      loc_14007F4BB
0x14007f304  test    dword ptr [rcx+24h], 10000h
0x14007f30b  jnz     loc_14007F4BB
0x14007f311  mov     r8d, 204h
0x14007f317  mov     dword ptr [rsp+2A0h+var_230], r12d
0x14007f31c  lea     rdx, [rbp+1A0h+var_1B0]
0x14007f320  mov     dword ptr [rsp+2A0h+var_230+4], r15d
0x14007f325  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x14007f32c  nop     dword ptr [rax+rax+00h]
0x14007f331  mov     rcx, [rbp+1A0h+var_1B0]
0x14007f335  mov     eax, [rcx+20h]
0x14007f338  and     eax, 43h
0x14007f33b  cmp     al, 43h ; 'C'
0x14007f33d  jz      short loc_14007F34C
0x14007f33f  mov     r8, rbx
0x14007f342  lea     rdx, [rsp+2A0h+var_230]
0x14007f347  call    bCvtPts1
0x14007f34c  mov     ecx, dword ptr [rsp+2A0h+var_230+4]
0x14007f350  mov     edx, dword ptr [rsp+2A0h+var_230]
0x14007f354  mov     dword ptr [rbp+1A0h+var_60+4], ecx
0x14007f35a  mov     dword ptr [rbp+1A0h+var_60], edx
0x14007f360  lea     eax, [rdx+1]
0x14007f363  mov     dword ptr [rbp+1A0h+var_60+8], eax
0x14007f369  lea     eax, [rcx+1]
0x14007f36c  mov     rcx, [rbp+1A0h+var_220]
0x14007f370  mov     dword ptr [rbp+1A0h+var_60+0Ch], eax
0x14007f376  mov     eax, [rcx+24h]
0x14007f379  test    al, 0E0h
0x14007f37b  jz      loc_14007F42A
0x14007f381  test    al, 20h
0x14007f383  jz      short loc_14007F3CF
0x14007f385  cmp     edx, [rcx+428h]
0x14007f38b  jge     short loc_14007F393
0x14007f38d  mov     [rcx+428h], edx
0x14007f393  mov     eax, dword ptr [rbp+1A0h+var_60+4]
0x14007f399  cmp     eax, [rcx+42Ch]
0x14007f39f  jge     short loc_14007F3A7
0x14007f3a1  mov     [rcx+42Ch], eax
0x14007f3a7  mov     eax, dword ptr [rbp+1A0h+var_60+8]
0x14007f3ad  cmp     eax, [rcx+430h]
0x14007f3b3  jle     short loc_14007F3BB
0x14007f3b5  mov     [rcx+430h], eax
0x14007f3bb  mov     eax, dword ptr [rbp+1A0h+var_60+0Ch]
0x14007f3c1  cmp     eax, [rcx+434h]
0x14007f3c7  jle     short loc_14007F3CF
0x14007f3c9  mov     [rcx+434h], eax
0x14007f3cf  mov     rcx, [rbp+1A0h+var_220]
0x14007f3d3  mov     eax, [rcx+24h]
0x14007f3d6  test    al, al
0x14007f3d8  jns     short loc_14007F42A
0x14007f3da  mov     eax, dword ptr [rbp+1A0h+var_60]
0x14007f3e0  cmp     eax, [rcx+448h]
0x14007f3e6  jge     short loc_14007F3EE
0x14007f3e8  mov     [rcx+448h], eax
0x14007f3ee  mov     eax, dword ptr [rbp+1A0h+var_60+4]
0x14007f3f4  cmp     eax, [rcx+44Ch]
0x14007f3fa  jge     short loc_14007F402
0x14007f3fc  mov     [rcx+44Ch], eax
0x14007f402  mov     eax, dword ptr [rbp+1A0h+var_60+8]
0x14007f408  cmp     eax, [rcx+450h]
0x14007f40e  jle     short loc_14007F416
0x14007f410  mov     [rcx+450h], eax
0x14007f416  mov     eax, dword ptr [rbp+1A0h+var_60+0Ch]
0x14007f41c  cmp     eax, [rcx+454h]
0x14007f422  jle     short loc_14007F42A
0x14007f424  mov     [rcx+454h], eax
0x14007f42a  mov     rax, [rbp+1A0h+var_220]
0x14007f42e  cmp     [rax+1F0h], rsi
0x14007f435  jz      loc_14007F4BB
0x14007f43b  mov     r12d, 2
0x14007f441  lea     rcx, [rbp+1A0h+var_110]
0x14007f448  mov     edx, r12d
0x14007f44b  call    ??0DEVLOCKOBJ@@QEAA@W4U2KMMAPStatus@@@Z; DEVLOCKOBJ::DEVLOCKOBJ(U2KMMAPStatus)
0x14007f450  xor     r8d, r8d
0x14007f453  lea     rdx, [rbp+1A0h+var_220]
0x14007f457  lea     rcx, [rbp+1A0h+var_110]
0x14007f45e  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x14007f465  nop     dword ptr [rax+rax+00h]
0x14007f46a  test    eax, eax
0x14007f46c  jz      short loc_14007F4AF
0x14007f46e  mov     rcx, [rbp+1A0h+var_220]; this
0x14007f472  mov     r15d, 80000000h
0x14007f478  movsxd  rdx, dword ptr [rbp+1A0h+var_60]
0x14007f47f  mov     r8d, [rcx+28h]
0x14007f483  and     r8, rbx
0x14007f486  movsxd  rdi, dword ptr [rcx+r8*8+3F8h]
0x14007f48e  lea     rax, [rdi+rdx]
0x14007f492  add     rax, r15
0x14007f495  cmp     rax, r14
0x14007f498  jbe     loc_14007FAAA
0x14007f49e  mov     ecx, 57h ; 'W'; iError
0x14007f4a3  call    cs:__imp_EngSetLastError
0x14007f4aa  nop     dword ptr [rax+rax+00h]
0x14007f4af  lea     rcx, [rbp+1A0h+var_110]; this
0x14007f4b6  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x14007f4bb  lea     rcx, [rbp+1A0h+var_220]; this
0x14007f4bf  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x14007f4c4  mov     eax, r14d
0x14007f4c7  mov     rcx, [rbp+1A0h+var_40]
0x14007f4ce  xor     rcx, rsp; StackCookie
0x14007f4d1  call    __security_check_cookie
0x14007f4d6  mov     rbx, [rsp+2A0h+arg_10]
0x14007f4de  add     rsp, 270h
0x14007f4e5  pop     r15
0x14007f4e7  pop     r14
0x14007f4e9  pop     r13
0x14007f4eb  pop     r12
0x14007f4ed  pop     rdi
0x14007f4ee  pop     rsi
0x14007f4ef  pop     rbp
0x14007f4f0  retn
0x14007f4f2  call    ?vMarkTransformDirty@DC@@QEAAXXZ; DC::vMarkTransformDirty(void)
0x14007f4f7  jmp     loc_14007F29E
0x14007f4fc  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x14007f503  nop     dword ptr [rax+rax+00h]
0x14007f508  cmp     eax, edi
0x14007f50a  jz      short loc_14007F51A
0x14007f50c  mov     ecx, edi
0x14007f50e  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x14007f515  nop     dword ptr [rax+rax+00h]
0x14007f51a  mov     rcx, [rbp+1A0h+var_220]
0x14007f51e  jmp     loc_14007F1F4
0x14007f523  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14007f528  jmp     loc_14007F2E6
0x14007f52d  call    cs:__imp_UserScreenAccessCheck
0x14007f534  nop     dword ptr [rax+rax+00h]
0x14007f539  test    eax, eax
0x14007f53b  jz      loc_14007FA53
0x14007f541  mov     rcx, [rbp+1A0h+var_220]
0x14007f545  mov     edx, dword ptr [rbp+1A0h+var_60]
0x14007f54b  mov     r10d, [rcx+24h]
0x14007f54f  test    r10b, 0E0h
0x14007f553  jz      loc_14007F657
0x14007f559  movaps  xmm0, [rbp+1A0h+var_60]
0x14007f560  movdqa  [rbp+1A0h+var_50], xmm0
0x14007f568  mov     eax, [rcx+28h]
0x14007f56b  mov     r8d, dword ptr [rbp+1A0h+var_50+8]
0x14007f572  and     rax, 1
0x14007f576  mov     r9d, dword ptr [rbp+1A0h+var_50+4]
0x14007f57d  sub     edx, [rcx+rax*8+3F8h]
0x14007f584  mov     dword ptr [rbp+1A0h+var_50], edx
0x14007f58a  sub     r8d, [rcx+rax*8+3F8h]
0x14007f592  mov     dword ptr [rbp+1A0h+var_50+8], r8d
0x14007f599  sub     r9d, [rcx+rax*8+3FCh]
0x14007f5a1  mov     dword ptr [rbp+1A0h+var_50+4], r9d
0x14007f5a8  mov     eax, [rcx+rax*8+3FCh]
0x14007f5af  sub     dword ptr [rbp+1A0h+var_50+0Ch], eax
0x14007f5b5  test    r10b, 40h
0x14007f5b9  jz      loc_14007F657
0x14007f5bf  mov     esi, [rcx+438h]
0x14007f5c5  lea     r11, [rcx+440h]
0x14007f5cc  mov     r10d, [r11]
0x14007f5cf  cmp     esi, r10d
0x14007f5d2  jz      loc_14007F7AF
0x14007f5d8  lea     rdi, [rcx+444h]
0x14007f5df  mov     ebx, [rdi]
0x14007f5e1  lea     rax, [rcx+43Ch]
0x14007f5e8  cmp     [rax], ebx
0x14007f5ea  jz      loc_14007F7AF
0x14007f5f0  cmp     edx, esi
0x14007f5f2  jge     short loc_14007F611
0x14007f5f4  mov     r10d, [r11]
0x14007f5f7  mov     ebx, [rdi]
0x14007f5f9  mov     [rcx+438h], edx
0x14007f5ff  mov     rcx, [rbp+1A0h+var_220]
0x14007f603  mov     r8d, dword ptr [rbp+1A0h+var_50+8]
0x14007f60a  mov     r9d, dword ptr [rbp+1A0h+var_50+4]
0x14007f611  cmp     r9d, [rax]
0x14007f614  jge     short loc_14007F624
0x14007f616  mov     [rax], r9d
0x14007f619  mov     rcx, [rbp+1A0h+var_220]
0x14007f61d  mov     r8d, dword ptr [rbp+1A0h+var_50+8]
0x14007f624  cmp     r8d, r10d
0x14007f627  jle     short loc_14007F630
0x14007f629  mov     [r11], r8d
0x14007f62c  mov     rcx, [rbp+1A0h+var_220]
0x14007f630  mov     eax, dword ptr [rbp+1A0h+var_50+0Ch]
0x14007f636  cmp     eax, ebx
0x14007f638  jle     short loc_14007F640
0x14007f63a  mov     [rdi], eax
0x14007f63c  mov     rcx, [rbp+1A0h+var_220]
0x14007f640  mov     rax, [rcx+4A0h]
0x14007f647  xor     esi, esi
0x14007f649  mov     [rsp+2A0h+var_228], rax
0x14007f64e  test    rax, rax
0x14007f651  jnz     loc_14007F7C3
0x14007f657  mov     rdi, [rcx+58h]
0x14007f65b  xorps   xmm0, xmm0
0x14007f65e  mov     rbx, [r15+0B0h]
0x14007f665  movdqa  [rbp+1A0h+var_140], xmm0
  ... truncated ...
```
