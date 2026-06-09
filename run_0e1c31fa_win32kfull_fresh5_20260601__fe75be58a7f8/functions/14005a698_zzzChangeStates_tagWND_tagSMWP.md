# zzzChangeStates(tagWND *,tagSMWP *)

- ea: `0x14005a698`
- end: `0x14005b430`
- name: `?zzzChangeStates@@YAJPEAUtagWND@@PEAUtagSMWP@@@Z`
- size: `3480`
- prototype: `__int64 __fastcall(struct tagWND *, struct tagSMWP *)`
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14005b5c0`

## callees

- `0x14000cd90`
- `0x140015750`
- `0x14001584c`
- `0x1400172b0`
- `0x140019474`
- `0x14001e034`
- `0x14001ec90`
- `0x14001eeb4`
- `0x1400209c0`
- `0x140020cf0`
- `0x140024100`
- `0x140028660`
- `0x1400291d0`
- `0x14002b948`
- `0x14002bda0`
- `0x14002c73c`
- `0x14002d278`
- `0x14002d67c`
- `0x140059f84`
- `0x14005a1b8`
- `0x14005a4ac`
- `0x14005a638`
- `0x14005a698`
- `0x14005c83c`
- `0x14005def4`
- `0x140061354`
- `0x1400911b0`
- `0x1400b5444`
- `0x1400bcaa0`
- `0x1400c138c`
- `0x1400c8768`
- `0x1400dd858`
- `0x1400ded9c`
- `0x1400df1dc`
- `0x1400df540`
- `0x1400ecb50`
- `0x1401339d8`
- `0x14016af50`
- `0x140198928`
- `0x1401bbcec`
- `0x1401fc80c`
- `0x14026a380`
- `0x140298d80`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14005b034`
- `ntoskrnl!KeBugCheckEx` at `0x14005b034`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005afe6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005afe6`
- `win32kbase!GreOffsetRgn` at `0x14005b1bd`
- `win32kbase!GreOffsetRgn` at `0x14005b1d2`
- `win32kbase!GreOffsetRgn` at `0x14005b1bd`
- `win32kbase!GreOffsetRgn` at `0x14005b1d2`
- `win32kbase!?ComputeDominantState@tagWND@@QEAAXXZ` at `0x14005b14a`
- `win32kbase!?ComputeDominantState@tagWND@@QEAAXXZ` at `0x14005b14a`
- `win32kbase!IsWindowDesktopComposed` at `0x14005ae28`
- `win32kbase!IsWindowDesktopComposed` at `0x14005b276`
- `win32kbase!IsWindowDesktopComposed` at `0x14005ae28`
- `win32kbase!IsWindowDesktopComposed` at `0x14005b276`
- `win32kbase!ValidateHmonitorNoRip` at `0x14005a822`
- `win32kbase!ValidateHmonitorNoRip` at `0x14005a822`
- `win32kbase!GreDeleteObject` at `0x14005a9c6`
- `win32kbase!GreDeleteObject` at `0x14005a9c6`
- `win32kbase!ValidateHmonitor` at `0x14005a851`
- `win32kbase!ValidateHmonitor` at `0x14005a851`
- `WIN32K!W32GetUserSessionState` at `0x14005aa48`
- `WIN32K!W32GetUserSessionState` at `0x14005add0`
- `WIN32K!W32GetUserSessionState` at `0x14005ae59`
- `WIN32K!W32GetUserSessionState` at `0x14005aed2`
- `WIN32K!W32GetUserSessionState` at `0x14005afcb`
- `WIN32K!W32GetUserSessionState` at `0x14005b39a`
- `WIN32K!W32GetUserSessionState` at `0x14005b3fc`
- `WIN32K!W32GetUserSessionState` at `0x14005aa48`
- `WIN32K!W32GetUserSessionState` at `0x14005add0`
- `WIN32K!W32GetUserSessionState` at `0x14005ae59`
- `WIN32K!W32GetUserSessionState` at `0x14005aed2`
- `WIN32K!W32GetUserSessionState` at `0x14005afcb`
- `WIN32K!W32GetUserSessionState` at `0x14005b39a`
- `WIN32K!W32GetUserSessionState` at `0x14005b3fc`

## pseudocode

```c
__int64 __fastcall zzzChangeStates(struct tagWND *a1, struct tagSMWP *a2)
{
  struct tagWND *v2; // r15
  __int64 v3; // rbx
  int v4; // r13d
  struct tagSMWP *v5; // r14
  __int64 v6; // rdx
  __int64 *v7; // rdi
  int v8; // r12d
  __int64 v9; // rcx
  __int64 v10; // rsi
  int v11; // eax
  int v12; // edx
  int v13; // eax
  __int64 NewMonitor; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v20; // r9
  __int16 v21; // cx
  __int16 v22; // dx
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rcx
  char v26; // bl
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // ecx
  char v30; // al
  __int64 v31; // rcx
  char v32; // dl
  __int64 v33; // rax
  unsigned int v34; // ecx
  __int64 v35; // rcx
  int v36; // r13d
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 DesktopWindow; // rax
  int v42; // r8d
  int v43; // r9d
  int v44; // ebx
  int v45; // r14d
  _DWORD *v46; // rdx
  int v47; // r15d
  int v48; // ecx
  unsigned int v49; // r15d
  int v50; // r12d
  unsigned int v51; // r12d
  __int64 v52; // rax
  int v53; // ecx
  __int64 v54; // rax
  int v55; // ecx
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rcx
  __int128 v60; // xmm0
  __int64 v61; // rcx
  int v62; // eax
  __int64 v63; // rax
  __int64 v64; // r10
  __int64 v65; // rdx
  __int64 v66; // rcx
  int v67; // ebx
  BOOL v68; // r14d
  unsigned __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rdx
  int v72; // ebx
  __int64 v73; // rdx
  char v74; // bl
  _DWORD *v75; // rdx
  __int64 UserSessionState; // rax
  __int64 v77; // rax
  int v78; // edx
  char v79; // bl
  int v80; // eax
  __int64 v81; // rcx
  __int64 v82; // rbx
  __int64 v83; // rcx
  __int64 v84; // rax
  HRGN ExplicitClipRgn; // rax
  int v86; // r15d
  int v87; // r12d
  int v88; // ecx
  char v89; // al
  __int64 v90; // rcx
  __int64 v91; // rax
  int v92; // ecx
  __int64 v93; // rax
  int updated; // [rsp+60h] [rbp-A0h]
  __int128 v95; // [rsp+68h] [rbp-98h] BYREF
  int v96; // [rsp+78h] [rbp-88h]
  int v97; // [rsp+7Ch] [rbp-84h]
  int v98; // [rsp+80h] [rbp-80h]
  int v99; // [rsp+84h] [rbp-7Ch]
  __int64 v100; // [rsp+88h] [rbp-78h]
  struct tagWND *v101; // [rsp+90h] [rbp-70h]
  struct tagSMWP *v102; // [rsp+98h] [rbp-68h]
  struct tagPOINT v103; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v104; // [rsp+A8h] [rbp-58h] BYREF
  int v105; // [rsp+B0h] [rbp-50h]
  int v106; // [rsp+B4h] [rbp-4Ch]
  _BYTE v107[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v108; // [rsp+C0h] [rbp-40h]
  char v109[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 CurrentThreadWin32Thread; // [rsp+D0h] [rbp-30h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+D8h] [rbp-28h] BYREF
  ULONG_PTR v112[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v113; // [rsp+F8h] [rbp-8h] BYREF

  v101 = a1;
  v2 = a1;
  updated = 0;
  v96 = 0;
  v3 = 0;
  v99 = 0;
  v4 = 0;
  v107[0] = 0;
  v108 = 0;
  v5 = a2;
  v102 = a2;
  AtomicExecutionCheck::Arm((AtomicExecutionCheck *)v107);
  Win32HMThreadLockBase<tagWND,0,0>::Win32HMThreadLockBase<tagWND,0,0>(v112, v2);
  v7 = (__int64 *)*((_QWORD *)v5 + 5);
  v8 = *((_DWORD *)v5 + 7) - 1;
  v97 = v8;
  if ( v8 < 0 )
    goto LABEL_32;
  while ( 1 )
  {
    v9 = *v7;
    *(_QWORD *)&v95 = 0;
    if ( !v9 )
      goto LABEL_17;
    LOBYTE(v6) = 1;
    v10 = HMValidateHandleNoSecure(v9, v6);
    if ( !v10 || !(unsigned int)IsStillWindowC((HWND)v7[1]) )
    {
      *((_DWORD *)v7 + 8) = 6159;
      *v7 = 0;
    }
    v11 = *((_DWORD *)v7 + 8);
    v9 = v11 & 0x18E7;
    if ( (v11 & 0x80000) == 0 && (_DWORD)v9 == 6151 )
    {
      *((_DWORD *)v7 + 8) = v11 | 8;
      goto LABEL_17;
    }
    if ( (_DWORD)v9 == 6147
      && (*(_BYTE *)(*(_QWORD *)(v10 + 40) + 19LL) & 4) == 0
      && (unsigned int)ValidateZorder((struct tagCVR *)v7) )
    {
      *((_DWORD *)v7 + 8) |= 0xCu;
      v9 = v7[12];
      if ( v9 )
      {
        GreDeleteObject(v9);
        v7[12] = 0;
      }
      goto LABEL_17;
    }
    if ( (v7[4] & 0x1803) != 0x1803 )
    {
      v35 = *(_QWORD *)(v10 + 40);
      v98 = 0;
      if ( (*(_BYTE *)(v35 + 27) & 0x20) == 0 && (*(_BYTE *)(v35 + 26) & 8) == 0
        || (v78 = *(_DWORD *)(v35 + 100) - *(_DWORD *)(v35 + 92),
            LODWORD(v100) = *(_DWORD *)(v35 + 96) - *(_DWORD *)(v35 + 88),
            HIDWORD(v100) = v78,
            (_DWORD)v100 == *((_DWORD *)v7 + 6))
        && v78 == *((_DWORD *)v7 + 7) )
      {
        v100 = v95;
      }
      else
      {
        v98 = 1;
      }
      if ( *(_DWORD *)(v35 + 88) != *((_DWORD *)v7 + 4) || (v36 = 0, *(_DWORD *)(v35 + 92) != *((_DWORD *)v7 + 5)) )
        v36 = 1;
      v95 = *(_OWORD *)(*((_QWORD *)v2 + 5) + 104LL);
      if ( IsChildWindowDpiBoundary((const struct tagWND *)v10) )
      {
        if ( (*((_DWORD *)v7 + 39) & 0x100) == 0 )
        {
          v3 = v10 + 224;
          *(_DWORD *)(v10 + 224) = 0;
          *(_DWORD *)(v10 + 228) = 0;
        }
        LogicalToPhysicalInPlaceRectWithSubpixel(v2, &v95, v3);
        PhysicalToLogicalInPlaceRectWithSubpixel(v10, &v95, v3);
        v99 = 1;
      }
      v38 = *(_QWORD *)(v10 + 40);
      v39 = *(unsigned int *)(v38 + 88);
      v40 = *(unsigned int *)(v38 + 92);
      *(_DWORD *)(v38 + 88) = *((_DWORD *)v7 + 4);
      *(_DWORD *)(*(_QWORD *)(v10 + 40) + 92LL) = *((_DWORD *)v7 + 5);
      DesktopWindow = GetDesktopWindow(v10, v37, v39, v40);
      v44 = DWORD1(v95);
      v45 = v95;
      if ( v2 != (struct tagWND *)DesktopWindow )
      {
        *(_DWORD *)(*(_QWORD *)(v10 + 40) + 88LL) += v95;
        *(_DWORD *)(*(_QWORD *)(v10 + 40) + 92LL) += v44;
      }
      v46 = *(_DWORD **)(v10 + 40);
      v47 = v46[22];
      v48 = *((_DWORD *)v7 + 6) + v47;
      v49 = v47 - v42;
      v50 = v46[23];
      v46[24] = v48;
      v51 = v50 - v43;
      *(_DWORD *)(*(_QWORD *)(v10 + 40) + 100LL) = *((_DWORD *)v7 + 7) + *(_DWORD *)(*(_QWORD *)(v10 + 40) + 92LL);
      v52 = *(_QWORD *)(v10 + 40);
      v53 = *(_DWORD *)(v52 + 88);
      if ( *(_DWORD *)(v52 + 96) < v53 )
        *(_DWORD *)(v52 + 96) = v53;
      v54 = *(_QWORD *)(v10 + 40);
      v55 = *(_DWORD *)(v54 + 92);
      if ( *(_DWORD *)(v54 + 100) < v55 )
        *(_DWORD *)(v54 + 100) = v55;
      v58 = *((_QWORD *)PtiCurrent() + 58);
      if ( v10 == *(_QWORD *)(v58 + 416) )
      {
        v84 = GetDesktopWindow(
                v10,
                (unsigned int)(*((_DWORD *)v7 + 19) + *(_DWORD *)(*(_QWORD *)(v10 + 40) + 108LL) - *((_DWORD *)v7 + 11)),
                (unsigned int)(*((_DWORD *)v7 + 18) + *(_DWORD *)(*(_QWORD *)(v10 + 40) + 104LL) - *((_DWORD *)v7 + 10)),
                v58);
        if ( v101 != (struct tagWND *)v84 )
        {
          v57 = (unsigned int)(v57 - v45);
          v56 = (unsigned int)(v56 - v44);
        }
        if ( (unsigned int)v57 | (unsigned int)v56 )
        {
          *(_DWORD *)(v58 + 436) += v57;
          *(_DWORD *)(v58 + 440) += v56;
        }
      }
      v59 = *(_QWORD *)(v10 + 40);
      v60 = *(_OWORD *)(v59 + 104);
      *(_DWORD *)(v59 + 104) = *((_DWORD *)v7 + 10);
      v61 = *(_QWORD *)(v10 + 40);
      v62 = *((_DWORD *)v7 + 11);
      v95 = v60;
      *(_DWORD *)(v61 + 108) = v62;
      v63 = GetDesktopWindow(v10, v56, v57, v58);
      if ( v64 != v63 )
      {
        *(_DWORD *)(*(_QWORD *)(v10 + 40) + 104LL) += v45;
        *(_DWORD *)(*(_QWORD *)(v10 + 40) + 108LL) += v44;
      }
      *(_DWORD *)(*(_QWORD *)(v10 + 40) + 112LL) = *((_DWORD *)v7 + 12) + *(_DWORD *)(*(_QWORD *)(v10 + 40) + 104LL);
      *(_DWORD *)(*(_QWORD *)(v10 + 40) + 116LL) = *((_DWORD *)v7 + 13) + *(_DWORD *)(*(_QWORD *)(v10 + 40) + 108LL);
      v65 = *(_QWORD *)(v10 + 40);
      v66 = v95 - *(_QWORD *)(v65 + 104);
      if ( (_QWORD)v95 == *(_QWORD *)(v65 + 104) )
        v66 = *((_QWORD *)&v95 + 1) - *(_QWORD *)(v65 + 112);
      v67 = 0;
      v68 = v66 == 0;
      FixupMonitorRgn((struct tagWND *)v10, (v7[4] & 8) == 0);
      if ( !v98 )
        goto LABEL_86;
      *((_DWORD *)v7 + 39) |= 1u;
      if ( (*((_DWORD *)v7 + 39) & 0x1000) != 0 )
        tagWND::ComputeDominantState((tagWND *)v10);
      v73 = *(_QWORD *)(v10 + 40);
      if ( (*(_BYTE *)(v73 + 27) & 0x20) != 0 )
      {
        v74 = *(_BYTE *)(v73 + 26);
        if ( (v74 & 0x20) == 0 )
        {
          v79 = v74 & 8;
          *(_QWORD *)&v95 = 0;
          v80 = RecreateRedirectionBitmap((struct tagWND *)v10, 0, (unsigned __int64)&v95 & -(__int64)(v79 != 0));
          updated = v80;
          if ( v79 && v80 >= 0 )
          {
            v82 = v95;
            if ( (_QWORD)v95 )
            {
              if ( (unsigned int)SetOldRedirectionBitmap(v10, v95) )
                v82 = 0;
            }
            else
            {
              if ( !*(_QWORD *)W32GetUserSessionState(v81) || !IS_USERCRIT_OWNED_AT_ALL() )
                KeBugCheckEx(0x164u, 0x2Au, 0, 0, 0);
              CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v83);
              v109[0] = 1;
              ++*(_DWORD *)(CurrentThreadWin32Thread + 28);
              xxxInternalInvalidate((struct tagWND *)v10, (HRGN)1, 0x401u);
              AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v109);
            }
          }
          else
          {
            v82 = v95;
          }
          if ( v82 )
            DeleteOrSetRedirectionBitmap(v10, v82, 1);
          v67 = 0;
          goto LABEL_86;
        }
        v67 = 0;
      }
      if ( (unsigned int)IsWindowDesktopComposed(v10) )
      {
        v75 = *(_DWORD **)(v10 + 40);
        *(_QWORD *)&v95 = 0;
        LODWORD(v95) = v75[24] - v75[22];
        DWORD1(v95) = v75[25] - v75[23];
        UserSessionState = W32GetUserSessionState(DWORD1(v95));
        updated = UpdateSprite(
                    *(HDEV *)(*(_QWORD *)(UserSessionState + 56744) + 40LL),
                    (struct tagWND *)v10,
                    0,
                    (__int64)&v95,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0);
      }
LABEL_86:
      if ( v49 || v51 )
      {
        ExplicitClipRgn = tagWND::GetExplicitClipRgn((tagWND *)v10);
        if ( ExplicitClipRgn )
          GreOffsetRgn(ExplicitClipRgn, v49, v51);
      }
      if ( v7[9] || v99 )
      {
        v69 = *(_QWORD *)(*(_QWORD *)(v10 + 40) + 136LL);
        if ( v69 > 1 )
          GreOffsetRgn(v69, *((unsigned int *)v7 + 18), *((unsigned int *)v7 + 19));
        OffsetChildren((struct tagWND *)v10);
      }
      if ( v36 || !v68 || v49 || v51 )
      {
        v70 = *(_QWORD *)(v10 + 40);
        v103 = *(struct tagPOINT *)(v70 + 88);
        v113 = 0;
        if ( v36 )
        {
          if ( (*(_DWORD *)(v10 + 380) & 0x400) != 0 )
            RemoveWindowFullScreen(v10);
          v71 = *(_QWORD *)(v10 + 40);
          if ( (*(_BYTE *)(v71 + 26) & 8) != 0 )
          {
            v72 = v98;
            if ( v98 )
            {
              v86 = -v49;
              v87 = -v51;
              v105 = *(_DWORD *)(v71 + 96) - *(_DWORD *)(v71 + 88);
              v88 = *(_DWORD *)(v71 + 100) - *(_DWORD *)(v71 + 92);
              DWORD2(v113) = v86 + v100;
              v106 = v88;
              HIDWORD(v113) = v87 + HIDWORD(v100);
              v104 = 0;
              *(_QWORD *)&v113 = __PAIR64__(v87, v86);
              IntersectRect(&v113, &v113, &v104);
            }
            if ( *(_DWORD *)(W32GetUserSessionState(v70) + 43048) )
            {
              InvalidateGDIWindows(v10);
              GreClientRgnUpdated(1);
            }
            if ( !v72 || (v67 = 1, (unsigned int)IsWindowDesktopComposed(v10)) )
              v67 = 0;
          }
        }
        if ( (*(_BYTE *)(*(_QWORD *)(v10 + 40) + 26LL) & 8) != 0 )
        {
          v77 = W32GetUserSessionState(v70);
          updated = UpdateSprite(
                      *(HDEV *)(*(_QWORD *)(v77 + 56744) + 40LL),
                      (struct tagWND *)v10,
                      &v103,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      (unsigned __int64)&v113 & -(__int64)(v67 != 0));
        }
      }
      v5 = v102;
      v2 = v101;
      v8 = v97;
      v4 = v96;
    }
    if ( (v7[4] & 4) == 0 )
    {
      if ( (unsigned int)ReValidateZorder((struct tagCVR *)v7)
        && (unsigned int)ValidateWindowPos((struct tagCVR *)v7, v2) )
      {
        UnlinkWindow((struct tagWND *)v10);
        PWInsertAfter(v7[1]);
        LinkWindow((struct tagWND *)v10);
        v33 = *(_QWORD *)(v10 + 40);
        v96 = ++v4;
        if ( (*(_BYTE *)(v33 + 19) & 4) == 0 )
          goto LABEL_9;
        SetOrClrWF(0, v10, 772, 1);
        v23 = 2056;
        LOBYTE(v34) = ~*(_BYTE *)(*(_QWORD *)(v10 + 40) + 24LL);
        v24 = (v34 >> 3) & 1;
      }
      else
      {
        *((_DWORD *)v7 + 8) |= 4u;
        v23 = 772;
        v24 = 0;
      }
      SetOrClrWF(v24, v10, v23, 1);
    }
LABEL_9:
    v12 = *((_DWORD *)v7 + 39);
    if ( (v12 & 0x20) != 0 && (*(_BYTE *)(*(_QWORD *)(v10 + 40) + 31LL) & 0x20) == 0 )
    {
      if ( (v12 & 0x200) != 0 )
      {
        NewMonitor = ValidateHmonitorNoRip(v7[16]);
      }
      else
      {
        v95 = 0;
        if ( (v12 & 0x80u) != 0 )
          v95 = *(_OWORD *)(v7 + 17);
        NewMonitor = GetNewMonitor((struct tagWND *)v10);
      }
      v17 = NewMonitor;
      if ( NewMonitor )
      {
        v18 = (*((_DWORD *)v7 + 39) & 0x200) != 0 ? *(_QWORD *)(*(_QWORD *)(v10 + 40) + 256LL) : v7[16];
        if ( ValidateHmonitor(v18, v15, v16) != NewMonitor
          || (v20 = *(_QWORD *)(v10 + 40), (v21 = *(_WORD *)(v20 + 286)) != 0)
          && *(_WORD *)(*(_QWORD *)(v17 + 40) + 60LL) != v21
          && (*(_DWORD *)(v20 + 288) & 0xF) == 2
          && (*(_DWORD *)(*(_QWORD *)(v10 + 16) + 680LL) & 0x2000000) == 0
          && (unsigned int)IsTopLevelWindow(v10)
          || (*(_BYTE *)(v20 + 288) & 0xF) == 3
          && (v22 = *(_WORD *)(*(_QWORD *)(v17 + 40) + 84LL), v22 != ((*(_DWORD *)(v20 + 288) >> 8) & 0x1FF))
          && v22 != *(_WORD *)(v10 + 304) )
        {
          *((_DWORD *)v7 + 39) ^= ((unsigned __int8)*((_DWORD *)v7 + 39)
                                 ^ (unsigned __int8)((unsigned __int8)UpdateMonitorForWindowAndChildren(
                                                                        (struct tagWND *)v10,
                                                                        (struct tagMONITOR *)v17) << 6))
                                & 0x40;
        }
      }
    }
    Win32HMThreadLockBase<tagWND,0,0>::Win32HMThreadLockBase<tagWND,0,0>(BugCheckParameter3, v10);
    v13 = *((_DWORD *)v7 + 8);
    if ( (v13 & 0x40) == 0 )
    {
      if ( (v13 & 0x80u) != 0 )
      {
        v89 = IsTrayWindow(v10, 1);
        v3 = 0;
        if ( (v7[4] & 0x1F) != 0x1F && v89 && (*(_WORD *)(*(_QWORD *)(v10 + 40) + 42LL) & 0x2FFF) != 0x2AA )
        {
          *((_DWORD *)v5 + 6) |= 1u;
          *((_DWORD *)v7 + 8) |= 0x20000000u;
        }
        SetRedrawProp(v10, 0);
        if ( (unsigned __int8)SetVisible(v10, 10) )
          DecomposeWindowIfNeeded((struct tagWND *)v10);
        v91 = W32GetUserSessionState(v90);
        v92 = 3;
        if ( !*(_DWORD *)(v91 + 70592) )
          v92 = 1;
        xxxWindowEvent(0x8003u, (struct tagWND *)v10, 0, 0, v92);
      }
      else
      {
        v3 = 0;
      }
      goto LABEL_13;
    }
    v25 = *(_QWORD *)(*(_QWORD *)(v10 + 16) + 456LL);
    if ( (*(_DWORD *)(v25 + 12) & 0x40) != 0 )
      zzzCalcStartCursorHide(v25, 5000);
    SetRedrawProp(v10, 0);
    v26 = SetVisible(v10, 9);
    v28 = W32GetUserSessionState(v27);
    v29 = 3;
    if ( !*(_DWORD *)(v28 + 70592) )
      v29 = 1;
    xxxWindowEvent(0x8002u, (struct tagWND *)v10, 0, 0, v29);
    if ( v26 )
    {
      *((_DWORD *)v7 + 39) |= 2u;
      if ( (*(_BYTE *)(*(_QWORD *)(v10 + 40) + 26LL) & 8) == 0 )
        updated = ComposeWindowIfNeeded((struct tagWND *)v10, 0);
    }
    v30 = IsTrayWindow(v10, 1);
    v31 = *(_QWORD *)(v10 + 40);
    v3 = 0;
    v32 = *(_BYTE *)(v31 + 16) & 0x40;
    if ( (*(_WORD *)(v31 + 42) & 0x2FFF) == 0x2AA )
    {
      if ( v32 )
      {
        *((_DWORD *)v5 + 6) |= 1u;
        *((_DWORD *)v7 + 8) |= 0x40000000u;
      }
      if ( v30 )
        goto LABEL_13;
LABEL_63:
      if ( !*(_QWORD *)(v10 + 120) )
        goto LABEL_64;
      goto LABEL_13;
    }
    if ( v32 )
    {
      *((_DWORD *)v5 + 6) |= 1u;
      *((_DWORD *)v7 + 8) |= 0x40000000u;
    }
    if ( !v30 && !*(_QWORD *)(v10 + 120) )
    {
LABEL_64:
      if ( (v7[4] & 0x40000000) != 0 )
        *((_DWORD *)v7 + 39) |= 0x10u;
      goto LABEL_13;
    }
    *((_DWORD *)v5 + 6) |= 1u;
    *((_DWORD *)v7 + 8) |= 0x10000000u;
    if ( !v30 )
    {
      *((_DWORD *)v7 + 39) |= 8u;
      goto LABEL_63;
    }
LABEL_13:
    if ( (*(_BYTE *)(*(_QWORD *)(v10 + 40) + 31LL) & 0x10) != 0 && (v7[4] & 0x8000) != 0 )
      SetOrClrWF(1, v10, 264, 1);
    if ( v7[14] )
      SelectWindowRgn((struct tagWND *)v10);
    Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
LABEL_17:
    v97 = --v8;
    if ( v8 < 0 )
      break;
    v7 += 21;
  }
  if ( v4 )
  {
    v93 = W32GetUserSessionState(v9);
    xxxWindowEvent(0x8004u, v2, -4, 0, *(_DWORD *)(v93 + 70592) != 0 ? 2 : 0);
  }
  LODWORD(v3) = updated;
LABEL_32:
  Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v112);
  if ( v107[0] )
    --*(_DWORD *)(v108 + 28);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14005a698  mov     [rsp-8+arg_10], rbx
0x14005a69d  push    rbp
0x14005a69e  push    rsi
0x14005a69f  push    rdi
0x14005a6a0  push    r12
0x14005a6a2  push    r13
0x14005a6a4  push    r14
0x14005a6a6  push    r15
0x14005a6a8  lea     rbp, [rsp-10h]
0x14005a6ad  sub     rsp, 110h
0x14005a6b4  mov     rax, cs:__security_cookie
0x14005a6bb  xor     rax, rsp
0x14005a6be  mov     [rbp+40h+var_38], rax
0x14005a6c2  xor     eax, eax
0x14005a6c4  mov     [rbp+40h+var_B0], rcx
0x14005a6c8  mov     r15, rcx
0x14005a6cb  mov     [rsp+140h+var_E0], eax
0x14005a6cf  lea     rcx, [rbp+40h+var_88]; this
0x14005a6d3  mov     [rsp+140h+var_C8], eax
0x14005a6d7  mov     ebx, eax
0x14005a6d9  mov     [rbp+40h+var_BC], eax
0x14005a6dc  mov     r13d, eax
0x14005a6df  mov     [rbp+40h+var_88], al
0x14005a6e2  mov     [rbp+40h+var_80], rax
0x14005a6e6  mov     r14, rdx
0x14005a6e9  mov     [rbp+40h+var_A8], rdx
0x14005a6ed  call    ?Arm@AtomicExecutionCheck@@QEAAXXZ
0x14005a6f2  mov     rdx, r15
0x14005a6f5  lea     rcx, [rbp+40h+var_58]
0x14005a6f9  call    ??0?$Win32HMThreadLockBase@UtagWND@@$0A@$0A@@@QEAA@PEAUtagWND@@@Z
0x14005a6fe  mov     r12d, [r14+1Ch]
0x14005a702  mov     rdi, [r14+28h]
0x14005a706  sub     r12d, 1
0x14005a70a  mov     [rsp+140h+var_C4], r12d
0x14005a70f  js      loc_14005A8A3
0x14005a715  mov     rcx, [rdi]
0x14005a718  mov     qword ptr [rsp+140h+var_D8], rbx
0x14005a71d  test    rcx, rcx
0x14005a720  jz      loc_14005A7D8
0x14005a726  mov     dl, 1
0x14005a728  call    HMValidateHandleNoSecure
0x14005a72d  mov     rsi, rax
0x14005a730  test    rax, rax
0x14005a733  jz      loc_14005B079
0x14005a739  mov     rcx, [rdi+8]; HWND
0x14005a73d  call    ?IsStillWindowC@@YAHPEAUHWND__@@@Z
0x14005a742  test    eax, eax
0x14005a744  jz      loc_14005B079
0x14005a74a  mov     eax, [rdi+20h]
0x14005a74d  mov     ecx, eax
0x14005a74f  and     ecx, 18E7h
0x14005a755  bt      eax, 13h
0x14005a759  jnb     loc_14005A7F3
0x14005a75f  cmp     ecx, 1803h
0x14005a765  jz      loc_14005A997
0x14005a76b  mov     eax, [rdi+20h]
0x14005a76e  mov     ecx, 1803h
0x14005a773  and     eax, ecx
0x14005a775  cmp     eax, ecx
0x14005a777  jnz     loc_14005AB8D
0x14005a77d  mov     eax, [rdi+20h]
0x14005a780  test    al, 4
0x14005a782  jz      loc_14005A9DB
0x14005a788  mov     edx, [rdi+9Ch]
0x14005a78e  test    dl, 20h
0x14005a791  jnz     short loc_14005A807
0x14005a793  mov     rdx, rsi
0x14005a796  lea     rcx, [rbp+40h+BugCheckParameter3]
0x14005a79a  call    ??0?$Win32HMThreadLockBase@UtagWND@@$0A@$0A@@@QEAA@PEAUtagWND@@@Z
0x14005a79f  mov     eax, [rdi+20h]
0x14005a7a2  test    al, 40h
0x14005a7a4  jnz     loc_14005AA19
0x14005a7aa  test    al, al
0x14005a7ac  js      loc_14005B355
0x14005a7b2  xor     ebx, ebx
0x14005a7b4  mov     rax, [rsi+28h]
0x14005a7b8  test    byte ptr [rax+1Fh], 10h
0x14005a7bc  jnz     loc_14005B3D3
0x14005a7c2  mov     rdx, [rdi+70h]
0x14005a7c6  test    rdx, rdx
0x14005a7c9  jnz     loc_14005AB02
0x14005a7cf  lea     rcx, [rbp+40h+BugCheckParameter3]; BugCheckParameter3
0x14005a7d3  call    ??1?$Win32HMThreadLockAlways@UtagWND@@@@QEAA@XZ
0x14005a7d8  sub     r12d, 1
0x14005a7dc  mov     [rsp+140h+var_C4], r12d
0x14005a7e1  js      loc_14005A896
0x14005a7e7  add     rdi, 0A8h
0x14005a7ee  jmp     loc_14005A715
0x14005a7f3  cmp     ecx, 1807h
0x14005a7f9  jnz     loc_14005A75F
0x14005a7ff  or      eax, 8
0x14005a802  mov     [rdi+20h], eax
0x14005a805  jmp     short loc_14005A7D8
0x14005a807  mov     rax, [rsi+28h]
0x14005a80b  test    byte ptr [rax+1Fh], 20h
0x14005a80f  jnz     short loc_14005A793
0x14005a811  bt      edx, 9
0x14005a815  jnb     loc_14005A8E3
0x14005a81b  mov     rcx, [rdi+80h]
0x14005a822  call    cs:__imp_ValidateHmonitorNoRip
0x14005a829  nop     dword ptr [rax+rax+00h]
0x14005a82e  mov     rbx, rax
0x14005a831  test    rax, rax
0x14005a834  jz      loc_14005A793
0x14005a83a  test    dword ptr [rdi+9Ch], 200h
0x14005a844  jnz     loc_14005B2A6
0x14005a84a  mov     rcx, [rdi+80h]
0x14005a851  call    cs:__imp_ValidateHmonitor
0x14005a858  nop     dword ptr [rax+rax+00h]
0x14005a85d  cmp     rax, rbx
0x14005a860  jz      loc_14005A936
0x14005a866  lea     r8, [rdi+0A0h]
0x14005a86d  xor     r9d, r9d
0x14005a870  mov     rdx, rbx
0x14005a873  mov     rcx, rsi
0x14005a876  call    UpdateMonitorForWindowAndChildren
0x14005a87b  mov     ecx, [rdi+9Ch]
0x14005a881  shl     eax, 6
0x14005a884  xor     eax, ecx
0x14005a886  and     eax, 40h
0x14005a889  xor     eax, ecx
0x14005a88b  mov     [rdi+9Ch], eax
0x14005a891  jmp     loc_14005A793
0x14005a896  test    r13d, r13d
0x14005a899  jnz     loc_14005B3FC
0x14005a89f  mov     ebx, [rsp+140h+var_E0]
0x14005a8a3  lea     rcx, [rbp+40h+var_58]; BugCheckParameter3
0x14005a8a7  call    ??1?$Win32HMThreadLockAlways@UtagWND@@@@QEAA@XZ
0x14005a8ac  cmp     [rbp+40h+var_88], 0
0x14005a8b0  jz      short loc_14005A8B9
0x14005a8b2  mov     rax, [rbp+40h+var_80]
0x14005a8b6  dec     dword ptr [rax+1Ch]
0x14005a8b9  mov     eax, ebx
0x14005a8bb  mov     rcx, [rbp+40h+var_38]
0x14005a8bf  xor     rcx, rsp; StackCookie
0x14005a8c2  call    __security_check_cookie
0x14005a8c7  mov     rbx, [rsp+140h+arg_10]
0x14005a8cf  add     rsp, 110h
0x14005a8d6  pop     r15
0x14005a8d8  pop     r14
0x14005a8da  pop     r13
0x14005a8dc  pop     r12
0x14005a8de  pop     rdi
0x14005a8df  pop     rsi
0x14005a8e0  pop     rbp
0x14005a8e1  retn
0x14005a8e3  xorps   xmm0, xmm0
0x14005a8e6  movups  [rsp+140h+var_D8], xmm0
0x14005a8eb  test    dl, dl
0x14005a8ed  js      loc_14005B294
0x14005a8f3  mov     rax, qword ptr [rsp+140h+var_D8]
0x14005a8f8  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x14005a8fd  cmp     eax, ecx
0x14005a8ff  jge     loc_14005AAF8
0x14005a905  shr     rcx, 20h
0x14005a909  shr     rax, 20h
0x14005a90d  cmp     eax, ecx
0x14005a90f  mov     ecx, ebx
0x14005a911  jge     loc_14005AAF8
0x14005a917  test    ecx, ecx
0x14005a919  lea     rdx, [rsp+140h+var_D8]
0x14005a91e  lea     r8, [rdi+88h]
0x14005a925  mov     rcx, rsi; struct tagWND *
0x14005a928  cmovnz  rdx, rbx
0x14005a92c  call    GetNewMonitor
0x14005a931  jmp     loc_14005A82E
0x14005a936  mov     r9, [rsi+28h]
0x14005a93a  movzx   ecx, word ptr [r9+11Eh]
0x14005a942  test    cx, cx
0x14005a945  jz      short loc_14005A955
0x14005a947  mov     rax, [rbx+28h]
0x14005a94b  cmp     [rax+3Ch], cx
0x14005a94f  jnz     loc_14005B2B6
0x14005a955  mov     ecx, [r9+120h]
0x14005a95c  mov     eax, ecx
0x14005a95e  and     eax, 0Fh
0x14005a961  cmp     al, 3
0x14005a963  jnz     loc_14005A793
0x14005a969  mov     rax, [rbx+28h]
0x14005a96d  shr     ecx, 8
0x14005a970  movzx   edx, word ptr [rax+54h]
0x14005a974  mov     eax, 1FFh
0x14005a979  and     cx, ax
0x14005a97c  cmp     dx, cx
0x14005a97f  jz      loc_14005A793
0x14005a985  cmp     dx, [rsi+130h]
0x14005a98c  jz      loc_14005A793
0x14005a992  jmp     loc_14005A866
0x14005a997  mov     rax, [rsi+28h]
0x14005a99b  test    byte ptr [rax+13h], 4
0x14005a99f  jnz     loc_14005A76B
0x14005a9a5  mov     rcx, rdi; struct tagCVR *
0x14005a9a8  call    ?ValidateZorder@@YAHPEAUtagCVR@@@Z
0x14005a9ad  test    eax, eax
0x14005a9af  jz      loc_14005A76B
0x14005a9b5  or      dword ptr [rdi+20h], 0Ch
0x14005a9b9  mov     rcx, [rdi+60h]
0x14005a9bd  test    rcx, rcx
0x14005a9c0  jz      loc_14005A7D8
0x14005a9c6  call    cs:__imp_GreDeleteObject
0x14005a9cd  nop     dword ptr [rax+rax+00h]
0x14005a9d2  mov     [rdi+60h], rbx
0x14005a9d6  jmp     loc_14005A7D8
0x14005a9db  mov     rcx, rdi; struct tagCVR *
0x14005a9de  call    ?ReValidateZorder@@YAHPEAUtagCVR@@@Z
0x14005a9e3  test    eax, eax
0x14005a9e5  jz      short loc_14005A9FA
0x14005a9e7  mov     rdx, r15; struct tagWND *
0x14005a9ea  mov     rcx, rdi; struct tagCVR *
0x14005a9ed  call    ?ValidateWindowPos@@YAHPEAUtagCVR@@PEAUtagWND@@@Z
0x14005a9f2  test    eax, eax
0x14005a9f4  jnz     loc_14005AB1E
0x14005a9fa  or      dword ptr [rdi+20h], 4
0x14005a9fe  mov     r8d, 304h
0x14005aa04  xor     ecx, ecx
0x14005aa06  mov     r9d, 1
0x14005aa0c  mov     rdx, rsi
0x14005aa0f  call    SetOrClrWF
0x14005aa14  jmp     loc_14005A788
0x14005aa19  mov     rax, [rsi+10h]
0x14005aa1d  mov     rcx, [rax+1C8h]
0x14005aa24  mov     eax, [rcx+0Ch]
0x14005aa27  test    al, 40h
0x14005aa29  jnz     loc_14005B2F0
0x14005aa2f  xor     edx, edx
0x14005aa31  mov     rcx, rsi
0x14005aa34  call    SetRedrawProp
0x14005aa39  mov     edx, 9
0x14005aa3e  mov     rcx, rsi
0x14005aa41  call    ?SetVisible@@YA_NPEAUtagWND@@W4SetVisibleOptions@@@Z
0x14005aa46  mov     bl, al
0x14005aa48  call    cs:__imp_W32GetUserSessionState
0x14005aa4f  nop     dword ptr [rax+rax+00h]
0x14005aa54  mov     ecx, 3
0x14005aa59  mov     rdx, rsi
0x14005aa5c  cmp     dword ptr [rax+113C0h], 0
0x14005aa63  lea     eax, [rcx-2]
0x14005aa66  cmovbe  ecx, eax
0x14005aa69  xor     r9d, r9d
0x14005aa6c  mov     dword ptr [rsp+140h+BugCheckParameter4], ecx
0x14005aa70  xor     r8d, r8d
0x14005aa73  mov     ecx, 8002h
0x14005aa78  call    xxxWindowEvent
0x14005aa7d  test    bl, bl
0x14005aa7f  jz      short loc_14005AA96
0x14005aa81  or      dword ptr [rdi+9Ch], 2
0x14005aa88  mov     rax, [rsi+28h]
0x14005aa8c  test    byte ptr [rax+1Ah], 8
0x14005aa90  jz      loc_14005B2FF
0x14005aa96  mov     edx, 1
0x14005aa9b  mov     rcx, rsi
0x14005aa9e  call    ?IsTrayWindow@@YA_NPEBUtagWND@@W4TrayCheckOption@@@Z
0x14005aaa3  mov     rcx, [rsi+28h]
0x14005aaa7  xor     ebx, ebx
0x14005aaa9  mov     dl, [rcx+10h]
0x14005aaac  movzx   ecx, word ptr [rcx+2Ah]
0x14005aab0  and     dl, 40h
0x14005aab3  and     ecx, 0FFFF2FFFh
0x14005aab9  cmp     ecx, 2AAh
0x14005aabf  jnz     loc_14005B321
0x14005aac5  test    dl, dl
0x14005aac7  jnz     loc_14005B312
0x14005aacd  test    al, al
0x14005aacf  jnz     loc_14005A7B4
0x14005aad5  cmp     [rsi+78h], rbx
0x14005aad9  jnz     loc_14005A7B4
0x14005aadf  test    dword ptr [rdi+20h], 40000000h
0x14005aae6  jz      loc_14005A7B4
0x14005aaec  or      dword ptr [rdi+9Ch], 10h
0x14005aaf3  jmp     loc_14005A7B4
0x14005aaf8  mov     ecx, 1
0x14005aafd  jmp     loc_14005A917
0x14005ab02  mov     r8d, [rdi+20h]
0x14005ab06  mov     rcx, rsi; struct tagWND *
0x14005ab09  shr     r8d, 3
0x14005ab0d  not     r8d
0x14005ab10  and     r8d, 1
0x14005ab14  call    SelectWindowRgn
0x14005ab19  jmp     loc_14005A7CF
0x14005ab1e  mov     rdx, r15
0x14005ab21  mov     rcx, rsi; struct tagWND *
0x14005ab24  call    UnlinkWindow
0x14005ab29  mov     rcx, [rdi+8]
0x14005ab2d  call    PWInsertAfter
0x14005ab32  mov     rdx, rax
0x14005ab35  mov     r8, r15
0x14005ab38  mov     rcx, rsi; struct tagWND *
0x14005ab3b  call    LinkWindow
0x14005ab40  mov     rax, [rsi+28h]
0x14005ab44  inc     r13d
0x14005ab47  mov     [rsp+140h+var_C8], r13d
0x14005ab4c  test    byte ptr [rax+13h], 4
0x14005ab50  jz      loc_14005A788
0x14005ab56  mov     r8d, 304h
0x14005ab5c  mov     r9d, 1
0x14005ab62  mov     rdx, rsi
0x14005ab65  xor     ecx, ecx
0x14005ab67  call    SetOrClrWF
0x14005ab6c  mov     rax, [rsi+28h]
0x14005ab70  mov     r8d, 808h
  ... truncated ...
```
