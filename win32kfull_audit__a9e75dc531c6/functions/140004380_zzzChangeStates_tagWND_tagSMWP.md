# zzzChangeStates(tagWND *,tagSMWP *)

- ea: `0x140004380`
- end: `0x140005118`
- name: `?zzzChangeStates@@YAJPEAUtagWND@@PEAUtagSMWP@@@Z`
- size: `3480`
- prototype: `__int64 __fastcall(struct tagWND *, struct tagSMWP *)`
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140096770`

## callees

- `0x140004380`
- `0x140005120`
- `0x1400051a0`
- `0x140005204`
- `0x1400054ec`
- `0x140005a18`
- `0x140010aac`
- `0x140011fec`
- `0x14001242c`
- `0x140012790`
- `0x1400138bc`
- `0x140015940`
- `0x14001af00`
- `0x14001b230`
- `0x14001ba04`
- `0x14001ef90`
- `0x140023570`
- `0x1400240e0`
- `0x140026888`
- `0x140026ce0`
- `0x14002767c`
- `0x1400281b8`
- `0x1400285bc`
- `0x140029014`
- `0x140029248`
- `0x14002953c`
- `0x14008f430`
- `0x1400915f4`
- `0x140095914`
- `0x140096200`
- `0x1400979ec`
- `0x1400990a4`
- `0x1400d0e30`
- `0x1400db6d4`
- `0x1400e2cb0`
- `0x1400e759c`
- `0x140110d58`
- `0x140112528`
- `0x14017e680`
- `0x1401dd704`
- `0x1401dd800`
- `0x140220cd8`
- `0x14029b250`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140004d1c`
- `ntoskrnl!KeBugCheckEx` at `0x140004d1c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140004cce`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140004cce`
- `win32kbase!GreOffsetRgn` at `0x140004ea5`
- `win32kbase!GreOffsetRgn` at `0x140004eba`
- `win32kbase!GreOffsetRgn` at `0x140004ea5`
- `win32kbase!GreOffsetRgn` at `0x140004eba`
- `win32kbase!?ComputeDominantState@tagWND@@QEAAXXZ` at `0x140004e32`
- `win32kbase!?ComputeDominantState@tagWND@@QEAAXXZ` at `0x140004e32`
- `win32kbase!IsWindowDesktopComposed` at `0x140004b10`
- `win32kbase!IsWindowDesktopComposed` at `0x140004f5e`
- `win32kbase!IsWindowDesktopComposed` at `0x140004b10`
- `win32kbase!IsWindowDesktopComposed` at `0x140004f5e`
- `win32kbase!ValidateHmonitorNoRip` at `0x14000450a`
- `win32kbase!ValidateHmonitorNoRip` at `0x14000450a`
- `win32kbase!GreDeleteObject` at `0x1400046ae`
- `win32kbase!GreDeleteObject` at `0x1400046ae`
- `win32kbase!ValidateHmonitor` at `0x140004539`
- `win32kbase!ValidateHmonitor` at `0x140004539`
- `WIN32K!W32GetUserSessionState` at `0x140004730`
- `WIN32K!W32GetUserSessionState` at `0x140004ab8`
- `WIN32K!W32GetUserSessionState` at `0x140004b41`
- `WIN32K!W32GetUserSessionState` at `0x140004bba`
- `WIN32K!W32GetUserSessionState` at `0x140004cb3`
- `WIN32K!W32GetUserSessionState` at `0x140005082`
- `WIN32K!W32GetUserSessionState` at `0x1400050e4`
- `WIN32K!W32GetUserSessionState` at `0x140004730`
- `WIN32K!W32GetUserSessionState` at `0x140004ab8`
- `WIN32K!W32GetUserSessionState` at `0x140004b41`
- `WIN32K!W32GetUserSessionState` at `0x140004bba`
- `WIN32K!W32GetUserSessionState` at `0x140004cb3`
- `WIN32K!W32GetUserSessionState` at `0x140005082`
- `WIN32K!W32GetUserSessionState` at `0x1400050e4`

## pseudocode

```c
__int64 __fastcall zzzChangeStates(struct tagWND *a1, struct tagSMWP *a2)
{
  __int64 *v2; // r15
  __int64 v3; // rbx
  int v4; // r13d
  struct tagSMWP *v5; // r14
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rdi
  int v10; // r12d
  __int64 v11; // rcx
  __int64 v12; // rsi
  int v13; // eax
  int v14; // edx
  int v15; // eax
  __int64 NewMonitor; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v22; // r9
  __int16 v23; // cx
  __int16 v24; // dx
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // rcx
  char v28; // bl
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rax
  int v34; // ecx
  char v35; // al
  __int64 v36; // rcx
  char v37; // dl
  struct tagWND *v38; // rax
  __int64 v39; // rax
  unsigned int v40; // ecx
  __int64 v41; // rcx
  int v42; // r13d
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 DesktopWindow; // rax
  int v47; // r8d
  int v48; // r9d
  int v49; // ebx
  int v50; // r14d
  _DWORD *v51; // rdx
  int v52; // r15d
  int v53; // ecx
  unsigned int v54; // r15d
  int v55; // r12d
  unsigned int v56; // r12d
  __int64 v57; // rax
  int v58; // ecx
  __int64 v59; // rax
  int v60; // ecx
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // rcx
  __int128 v64; // xmm0
  __int64 v65; // rcx
  int v66; // eax
  __int64 v67; // rax
  __int64 v68; // r10
  __int64 v69; // rdx
  __int64 v70; // rcx
  int v71; // ebx
  BOOL v72; // r14d
  __int64 v73; // r8
  __int64 v74; // r9
  __int64 v75; // rdx
  unsigned __int64 v76; // rcx
  __int64 v77; // rcx
  int v78; // ebx
  __int64 v79; // rdx
  char v80; // bl
  _DWORD *v81; // rdx
  __int64 UserSessionState; // rax
  __int64 v83; // r8
  __int64 v84; // rax
  __int64 v85; // r8
  int v86; // edx
  char v87; // bl
  int v88; // eax
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // rbx
  __int64 v92; // rdx
  __int64 v93; // rcx
  __int64 v94; // rax
  __int64 v95; // r9
  HRGN ExplicitClipRgn; // rax
  int v97; // r15d
  int v98; // r12d
  int v99; // ecx
  char v100; // al
  __int64 v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // r8
  __int64 v104; // r9
  __int64 v105; // rax
  int v106; // ecx
  __int64 v107; // rax
  int updated; // [rsp+60h] [rbp-A0h]
  __int128 v109; // [rsp+68h] [rbp-98h] BYREF
  int v110; // [rsp+78h] [rbp-88h]
  int v111; // [rsp+7Ch] [rbp-84h]
  int v112; // [rsp+80h] [rbp-80h]
  int v113; // [rsp+84h] [rbp-7Ch]
  __int64 v114; // [rsp+88h] [rbp-78h]
  struct tagWND *v115; // [rsp+90h] [rbp-70h]
  struct tagSMWP *v116; // [rsp+98h] [rbp-68h]
  struct tagPOINT v117; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v118; // [rsp+A8h] [rbp-58h] BYREF
  int v119; // [rsp+B0h] [rbp-50h]
  int v120; // [rsp+B4h] [rbp-4Ch]
  _BYTE v121[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v122; // [rsp+C0h] [rbp-40h]
  char v123[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 CurrentThreadWin32Thread; // [rsp+D0h] [rbp-30h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+D8h] [rbp-28h] BYREF
  ULONG_PTR v126[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v127; // [rsp+F8h] [rbp-8h] BYREF

  v115 = a1;
  v2 = (__int64 *)a1;
  updated = 0;
  v110 = 0;
  v3 = 0;
  v113 = 0;
  v4 = 0;
  v121[0] = 0;
  v122 = 0;
  v5 = a2;
  v116 = a2;
  AtomicExecutionCheck::Arm((AtomicExecutionCheck *)v121);
  Win32HMThreadLockBase<tagWND,0,0>::Win32HMThreadLockBase<tagWND,0,0>(v126, v2);
  v9 = (__int64 *)*((_QWORD *)v5 + 5);
  v10 = *((_DWORD *)v5 + 7) - 1;
  v111 = v10;
  if ( v10 < 0 )
    goto LABEL_32;
  while ( 1 )
  {
    v11 = *v9;
    *(_QWORD *)&v109 = 0;
    if ( !v11 )
      goto LABEL_17;
    LOBYTE(v6) = 1;
    v12 = HMValidateHandleNoSecure(v11, v6);
    if ( !v12 || !(unsigned int)IsStillWindowC((HWND)v9[1]) )
    {
      *((_DWORD *)v9 + 8) = 6159;
      *v9 = 0;
    }
    v13 = *((_DWORD *)v9 + 8);
    v11 = v13 & 0x18E7;
    if ( (v13 & 0x80000) == 0 && (_DWORD)v11 == 6151 )
    {
      *((_DWORD *)v9 + 8) = v13 | 8;
      goto LABEL_17;
    }
    if ( (_DWORD)v11 == 6147
      && (*(_BYTE *)(*(_QWORD *)(v12 + 40) + 19LL) & 4) == 0
      && (unsigned int)ValidateZorder((struct tagCVR *)v9) )
    {
      *((_DWORD *)v9 + 8) |= 0xCu;
      v11 = v9[12];
      if ( v11 )
      {
        GreDeleteObject(v11);
        v9[12] = 0;
      }
      goto LABEL_17;
    }
    if ( (v9[4] & 0x1803) != 0x1803 )
    {
      v41 = *(_QWORD *)(v12 + 40);
      v112 = 0;
      if ( (*(_BYTE *)(v41 + 27) & 0x20) == 0 && (*(_BYTE *)(v41 + 26) & 8) == 0
        || (v86 = *(_DWORD *)(v41 + 100) - *(_DWORD *)(v41 + 92),
            LODWORD(v114) = *(_DWORD *)(v41 + 96) - *(_DWORD *)(v41 + 88),
            HIDWORD(v114) = v86,
            (_DWORD)v114 == *((_DWORD *)v9 + 6))
        && v86 == *((_DWORD *)v9 + 7) )
      {
        v114 = v109;
      }
      else
      {
        v112 = 1;
      }
      if ( *(_DWORD *)(v41 + 88) != *((_DWORD *)v9 + 4) || (v42 = 0, *(_DWORD *)(v41 + 92) != *((_DWORD *)v9 + 5)) )
        v42 = 1;
      v109 = *(_OWORD *)(v2[5] + 104);
      if ( IsChildWindowDpiBoundary((const struct tagWND *)v12) )
      {
        if ( (*((_DWORD *)v9 + 39) & 0x100) == 0 )
        {
          v3 = v12 + 224;
          *(_DWORD *)(v12 + 224) = 0;
          *(_DWORD *)(v12 + 228) = 0;
        }
        LogicalToPhysicalInPlaceRectWithSubpixel(v2, &v109, v3);
        PhysicalToLogicalInPlaceRectWithSubpixel(v12, &v109, v3);
        v113 = 1;
      }
      v44 = *(_QWORD *)(v12 + 40);
      v45 = *(unsigned int *)(v44 + 88);
      *(_DWORD *)(v44 + 88) = *((_DWORD *)v9 + 4);
      *(_DWORD *)(*(_QWORD *)(v12 + 40) + 92LL) = *((_DWORD *)v9 + 5);
      DesktopWindow = GetDesktopWindow(v12, v43, v45);
      v49 = DWORD1(v109);
      v50 = v109;
      if ( v2 != (__int64 *)DesktopWindow )
      {
        *(_DWORD *)(*(_QWORD *)(v12 + 40) + 88LL) += v109;
        *(_DWORD *)(*(_QWORD *)(v12 + 40) + 92LL) += v49;
      }
      v51 = *(_DWORD **)(v12 + 40);
      v52 = v51[22];
      v53 = *((_DWORD *)v9 + 6) + v52;
      v54 = v52 - v47;
      v55 = v51[23];
      v51[24] = v53;
      v56 = v55 - v48;
      *(_DWORD *)(*(_QWORD *)(v12 + 40) + 100LL) = *((_DWORD *)v9 + 7) + *(_DWORD *)(*(_QWORD *)(v12 + 40) + 92LL);
      v57 = *(_QWORD *)(v12 + 40);
      v58 = *(_DWORD *)(v57 + 88);
      if ( *(_DWORD *)(v57 + 96) < v58 )
        *(_DWORD *)(v57 + 96) = v58;
      v59 = *(_QWORD *)(v12 + 40);
      v60 = *(_DWORD *)(v59 + 92);
      if ( *(_DWORD *)(v59 + 100) < v60 )
        *(_DWORD *)(v59 + 100) = v60;
      if ( v12 == *(_QWORD *)(*((_QWORD *)PtiCurrent() + 58) + 416LL) )
      {
        v94 = GetDesktopWindow(
                v12,
                (unsigned int)(*((_DWORD *)v9 + 19) + *(_DWORD *)(*(_QWORD *)(v12 + 40) + 108LL) - *((_DWORD *)v9 + 11)),
                (unsigned int)(*((_DWORD *)v9 + 18) + *(_DWORD *)(*(_QWORD *)(v12 + 40) + 104LL) - *((_DWORD *)v9 + 10)));
        if ( v115 != (struct tagWND *)v94 )
        {
          v62 = (unsigned int)(v62 - v50);
          v61 = (unsigned int)(v61 - v49);
        }
        if ( (unsigned int)v62 | (unsigned int)v61 )
        {
          *(_DWORD *)(v95 + 436) += v62;
          *(_DWORD *)(v95 + 440) += v61;
        }
      }
      v63 = *(_QWORD *)(v12 + 40);
      v64 = *(_OWORD *)(v63 + 104);
      *(_DWORD *)(v63 + 104) = *((_DWORD *)v9 + 10);
      v65 = *(_QWORD *)(v12 + 40);
      v66 = *((_DWORD *)v9 + 11);
      v109 = v64;
      *(_DWORD *)(v65 + 108) = v66;
      v67 = GetDesktopWindow(v12, v61, v62);
      if ( v68 != v67 )
      {
        *(_DWORD *)(*(_QWORD *)(v12 + 40) + 104LL) += v50;
        *(_DWORD *)(*(_QWORD *)(v12 + 40) + 108LL) += v49;
      }
      *(_DWORD *)(*(_QWORD *)(v12 + 40) + 112LL) = *((_DWORD *)v9 + 12) + *(_DWORD *)(*(_QWORD *)(v12 + 40) + 104LL);
      *(_DWORD *)(*(_QWORD *)(v12 + 40) + 116LL) = *((_DWORD *)v9 + 13) + *(_DWORD *)(*(_QWORD *)(v12 + 40) + 108LL);
      v69 = *(_QWORD *)(v12 + 40);
      v70 = v109 - *(_QWORD *)(v69 + 104);
      if ( (_QWORD)v109 == *(_QWORD *)(v69 + 104) )
        v70 = *((_QWORD *)&v109 + 1) - *(_QWORD *)(v69 + 112);
      v71 = 0;
      v72 = v70 == 0;
      FixupMonitorRgn((struct tagWND *)v12, (v9[4] & 8) == 0);
      if ( !v112 )
        goto LABEL_86;
      *((_DWORD *)v9 + 39) |= 1u;
      if ( (*((_DWORD *)v9 + 39) & 0x1000) != 0 )
        tagWND::ComputeDominantState((tagWND *)v12);
      v79 = *(_QWORD *)(v12 + 40);
      if ( (*(_BYTE *)(v79 + 27) & 0x20) != 0 )
      {
        v80 = *(_BYTE *)(v79 + 26);
        if ( (v80 & 0x20) == 0 )
        {
          v87 = v80 & 8;
          *(_QWORD *)&v109 = 0;
          v88 = RecreateRedirectionBitmap((struct tagWND *)v12, 0, (unsigned __int64)&v109 & -(__int64)(v87 != 0));
          updated = v88;
          if ( v87 && v88 >= 0 )
          {
            v91 = v109;
            if ( (_QWORD)v109 )
            {
              if ( (unsigned int)SetOldRedirectionBitmap(v12, v109) )
                v91 = 0;
            }
            else
            {
              if ( !*(_QWORD *)W32GetUserSessionState(v90, v89, v73, v74) || !IS_USERCRIT_OWNED_AT_ALL() )
                KeBugCheckEx(0x164u, 0x2Au, 0, 0, 0);
              CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v93, v92);
              v123[0] = 1;
              ++*(_DWORD *)(CurrentThreadWin32Thread + 28);
              xxxInternalInvalidate((struct tagWND *)v12, (HRGN)1, 0x401u);
              AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v123);
            }
          }
          else
          {
            v91 = v109;
          }
          if ( v91 )
            DeleteOrSetRedirectionBitmap(v12, v91, 1);
          v71 = 0;
          goto LABEL_86;
        }
        v71 = 0;
      }
      if ( (unsigned int)IsWindowDesktopComposed(v12, v79, v73, v74) )
      {
        v81 = *(_DWORD **)(v12 + 40);
        *(_QWORD *)&v109 = 0;
        LODWORD(v109) = v81[24] - v81[22];
        DWORD1(v109) = v81[25] - v81[23];
        UserSessionState = W32GetUserSessionState(DWORD1(v109), v81, v73, v74);
        updated = UpdateSprite(
                    *(HDEV *)(*(_QWORD *)(UserSessionState + 56744) + 40LL),
                    (struct tagWND *)v12,
                    v83,
                    0,
                    0,
                    (struct tagSIZE *)&v109,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0);
      }
LABEL_86:
      if ( v54 || v56 )
      {
        ExplicitClipRgn = tagWND::GetExplicitClipRgn((tagWND *)v12);
        if ( ExplicitClipRgn )
          GreOffsetRgn(ExplicitClipRgn, v54, v56);
      }
      v75 = *((unsigned int *)v9 + 18);
      if ( v9[9] || v113 )
      {
        v76 = *(_QWORD *)(*(_QWORD *)(v12 + 40) + 136LL);
        if ( v76 > 1 )
          GreOffsetRgn(v76, v75, *((unsigned int *)v9 + 19));
        OffsetChildren((struct tagWND *)v12);
      }
      if ( v42 || !v72 || v54 || v56 )
      {
        v77 = *(_QWORD *)(v12 + 40);
        v117 = *(struct tagPOINT *)(v77 + 88);
        v127 = 0;
        if ( v42 )
        {
          if ( (*(_DWORD *)(v12 + 380) & 0x400) != 0 )
            RemoveWindowFullScreen(v12);
          v75 = *(_QWORD *)(v12 + 40);
          if ( (*(_BYTE *)(v75 + 26) & 8) != 0 )
          {
            v78 = v112;
            if ( v112 )
            {
              v97 = -v54;
              v98 = -v56;
              v119 = *(_DWORD *)(v75 + 96) - *(_DWORD *)(v75 + 88);
              v99 = *(_DWORD *)(v75 + 100) - *(_DWORD *)(v75 + 92);
              DWORD2(v127) = v97 + v114;
              v120 = v99;
              HIDWORD(v127) = v98 + HIDWORD(v114);
              v118 = 0;
              *(_QWORD *)&v127 = __PAIR64__(v98, v97);
              IntersectRect(&v127, &v127, &v118);
            }
            if ( *(_DWORD *)(W32GetUserSessionState(v77, v75, v73, v74) + 43048) )
            {
              InvalidateGDIWindows(v12);
              GreClientRgnUpdated(1);
            }
            if ( !v78 || (v71 = 1, (unsigned int)IsWindowDesktopComposed(v12, v75, v73, v74)) )
              v71 = 0;
          }
        }
        if ( (*(_BYTE *)(*(_QWORD *)(v12 + 40) + 26LL) & 8) != 0 )
        {
          v84 = W32GetUserSessionState(v77, v75, v73, v74);
          updated = UpdateSprite(
                      *(HDEV *)(*(_QWORD *)(v84 + 56744) + 40LL),
                      (struct tagWND *)v12,
                      v85,
                      0,
                      &v117,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      (struct tagRECT *)((unsigned __int64)&v127 & -(__int64)(v71 != 0)));
        }
      }
      v5 = v116;
      v2 = (__int64 *)v115;
      v10 = v111;
      v4 = v110;
    }
    if ( (v9[4] & 4) == 0 )
    {
      if ( (unsigned int)ReValidateZorder((struct tagCVR *)v9)
        && (unsigned int)ValidateWindowPos((struct tagCVR *)v9, (struct tagWND *)v2) )
      {
        UnlinkWindow((struct tagWND *)v12);
        v38 = (struct tagWND *)PWInsertAfter(v9[1]);
        LinkWindow((struct tagWND **)v12, v38, v2);
        v39 = *(_QWORD *)(v12 + 40);
        v110 = ++v4;
        if ( (*(_BYTE *)(v39 + 19) & 4) == 0 )
          goto LABEL_9;
        SetOrClrWF(0, v12, 772, 1);
        v25 = 2056;
        LOBYTE(v40) = ~*(_BYTE *)(*(_QWORD *)(v12 + 40) + 24LL);
        v26 = (v40 >> 3) & 1;
      }
      else
      {
        *((_DWORD *)v9 + 8) |= 4u;
        v25 = 772;
        v26 = 0;
      }
      SetOrClrWF(v26, v12, v25, 1);
    }
LABEL_9:
    v14 = *((_DWORD *)v9 + 39);
    if ( (v14 & 0x20) != 0 && (*(_BYTE *)(*(_QWORD *)(v12 + 40) + 31LL) & 0x20) == 0 )
    {
      if ( (v14 & 0x200) != 0 )
      {
        NewMonitor = ValidateHmonitorNoRip(v9[16]);
      }
      else
      {
        v109 = 0;
        if ( (v14 & 0x80u) != 0 )
          v109 = *(_OWORD *)(v9 + 17);
        NewMonitor = GetNewMonitor((struct tagWND *)v12);
      }
      v19 = NewMonitor;
      if ( NewMonitor )
      {
        v20 = (*((_DWORD *)v9 + 39) & 0x200) != 0 ? *(_QWORD *)(*(_QWORD *)(v12 + 40) + 256LL) : v9[16];
        if ( ValidateHmonitor(v20, v17, v18) != NewMonitor
          || (v22 = *(_QWORD *)(v12 + 40), (v23 = *(_WORD *)(v22 + 286)) != 0)
          && *(_WORD *)(*(_QWORD *)(v19 + 40) + 60LL) != v23
          && (*(_DWORD *)(v22 + 288) & 0xF) == 2
          && (*(_DWORD *)(*(_QWORD *)(v12 + 16) + 680LL) & 0x2000000) == 0
          && (unsigned int)IsTopLevelWindow(v12)
          || (*(_BYTE *)(v22 + 288) & 0xF) == 3
          && (v24 = *(_WORD *)(*(_QWORD *)(v19 + 40) + 84LL), v24 != ((*(_DWORD *)(v22 + 288) >> 8) & 0x1FF))
          && v24 != *(_WORD *)(v12 + 304) )
        {
          *((_DWORD *)v9 + 39) ^= ((unsigned __int8)*((_DWORD *)v9 + 39)
                                 ^ (unsigned __int8)((unsigned __int8)UpdateMonitorForWindowAndChildren((struct tagWND *)v12) << 6))
                                & 0x40;
        }
      }
    }
    Win32HMThreadLockBase<tagWND,0,0>::Win32HMThreadLockBase<tagWND,0,0>(BugCheckParameter3, v12);
    v15 = *((_DWORD *)v9 + 8);
    if ( (v15 & 0x40) == 0 )
    {
      if ( (v15 & 0x80u) != 0 )
      {
        v100 = IsTrayWindow(v12, 1);
        v3 = 0;
        if ( (v9[4] & 0x1F) != 0x1F && v100 && (*(_WORD *)(*(_QWORD *)(v12 + 40) + 42LL) & 0x2FFF) != 0x2AA )
        {
          *((_DWORD *)v5 + 6) |= 1u;
          *((_DWORD *)v9 + 8) |= 0x20000000u;
        }
        SetRedrawProp(v12, 0);
        if ( (unsigned __int8)SetVisible(v12, 10) )
          DecomposeWindowIfNeeded((struct tagWND *)v12);
        v105 = W32GetUserSessionState(v102, v101, v103, v104);
        v106 = 3;
        if ( !*(_DWORD *)(v105 + 70592) )
          v106 = 1;
        xxxWindowEvent(0x8003u, v106);
      }
      else
      {
        v3 = 0;
      }
      goto LABEL_13;
    }
    v27 = *(_QWORD *)(*(_QWORD *)(v12 + 16) + 456LL);
    if ( (*(_DWORD *)(v27 + 12) & 0x40) != 0 )
      zzzCalcStartCursorHide(v27, 5000);
    SetRedrawProp(v12, 0);
    v28 = SetVisible(v12, 9);
    v33 = W32GetUserSessionState(v30, v29, v31, v32);
    v34 = 3;
    if ( !*(_DWORD *)(v33 + 70592) )
      v34 = 1;
    xxxWindowEvent(0x8002u, v34);
    if ( v28 )
    {
      *((_DWORD *)v9 + 39) |= 2u;
      if ( (*(_BYTE *)(*(_QWORD *)(v12 + 40) + 26LL) & 8) == 0 )
        updated = ComposeWindowIfNeeded((struct tagWND *)v12, 0);
    }
    v35 = IsTrayWindow(v12, 1);
    v36 = *(_QWORD *)(v12 + 40);
    v3 = 0;
    v37 = *(_BYTE *)(v36 + 16) & 0x40;
    if ( (*(_WORD *)(v36 + 42) & 0x2FFF) == 0x2AA )
    {
      if ( v37 )
      {
        *((_DWORD *)v5 + 6) |= 1u;
        *((_DWORD *)v9 + 8) |= 0x40000000u;
      }
      if ( v35 )
        goto LABEL_13;
LABEL_63:
      if ( !*(_QWORD *)(v12 + 120) )
        goto LABEL_64;
      goto LABEL_13;
    }
    if ( v37 )
    {
      *((_DWORD *)v5 + 6) |= 1u;
      *((_DWORD *)v9 + 8) |= 0x40000000u;
    }
    if ( !v35 && !*(_QWORD *)(v12 + 120) )
    {
LABEL_64:
      if ( (v9[4] & 0x40000000) != 0 )
        *((_DWORD *)v9 + 39) |= 0x10u;
      goto LABEL_13;
    }
    *((_DWORD *)v5 + 6) |= 1u;
    *((_DWORD *)v9 + 8) |= 0x10000000u;
    if ( !v35 )
    {
      *((_DWORD *)v9 + 39) |= 8u;
      goto LABEL_63;
    }
LABEL_13:
    if ( (*(_BYTE *)(*(_QWORD *)(v12 + 40) + 31LL) & 0x10) != 0 && (v9[4] & 0x8000) != 0 )
      SetOrClrWF(1, v12, 264, 1);
    if ( v9[14] )
      SelectWindowRgn((struct tagWND *)v12);
    Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
LABEL_17:
    v111 = --v10;
    if ( v10 < 0 )
      break;
    v9 += 21;
  }
  if ( v4 )
  {
    v107 = W32GetUserSessionState(v11, v6, v7, v8);
    xxxWindowEvent(0x8004u, *(_DWORD *)(v107 + 70592) != 0 ? 2 : 0);
  }
  LODWORD(v3) = updated;
LABEL_32:
  Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v126);
  if ( v121[0] )
    --*(_DWORD *)(v122 + 28);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140004380  mov     [rsp-8+arg_10], rbx
0x140004385  push    rbp
0x140004386  push    rsi
0x140004387  push    rdi
0x140004388  push    r12
0x14000438a  push    r13
0x14000438c  push    r14
0x14000438e  push    r15
0x140004390  lea     rbp, [rsp-10h]
0x140004395  sub     rsp, 110h
0x14000439c  mov     rax, cs:__security_cookie
0x1400043a3  xor     rax, rsp
0x1400043a6  mov     [rbp+40h+var_38], rax
0x1400043aa  xor     eax, eax
0x1400043ac  mov     [rbp+40h+var_B0], rcx
0x1400043b0  mov     r15, rcx
0x1400043b3  mov     [rsp+140h+var_E0], eax
0x1400043b7  lea     rcx, [rbp+40h+var_88]; this
0x1400043bb  mov     [rsp+140h+var_C8], eax
0x1400043bf  mov     ebx, eax
0x1400043c1  mov     [rbp+40h+var_BC], eax
0x1400043c4  mov     r13d, eax
0x1400043c7  mov     [rbp+40h+var_88], al
0x1400043ca  mov     [rbp+40h+var_80], rax
0x1400043ce  mov     r14, rdx
0x1400043d1  mov     [rbp+40h+var_A8], rdx
0x1400043d5  call    ?Arm@AtomicExecutionCheck@@QEAAXXZ
0x1400043da  mov     rdx, r15
0x1400043dd  lea     rcx, [rbp+40h+var_58]
0x1400043e1  call    ??0?$Win32HMThreadLockBase@UtagWND@@$0A@$0A@@@QEAA@PEAUtagWND@@@Z
0x1400043e6  mov     r12d, [r14+1Ch]
0x1400043ea  mov     rdi, [r14+28h]
0x1400043ee  sub     r12d, 1
0x1400043f2  mov     [rsp+140h+var_C4], r12d
0x1400043f7  js      loc_14000458B
0x1400043fd  mov     rcx, [rdi]
0x140004400  mov     qword ptr [rsp+140h+var_D8], rbx
0x140004405  test    rcx, rcx
0x140004408  jz      loc_1400044C0
0x14000440e  mov     dl, 1
0x140004410  call    HMValidateHandleNoSecure
0x140004415  mov     rsi, rax
0x140004418  test    rax, rax
0x14000441b  jz      loc_140004D61
0x140004421  mov     rcx, [rdi+8]; HWND
0x140004425  call    ?IsStillWindowC@@YAHPEAUHWND__@@@Z
0x14000442a  test    eax, eax
0x14000442c  jz      loc_140004D61
0x140004432  mov     eax, [rdi+20h]
0x140004435  mov     ecx, eax
0x140004437  and     ecx, 18E7h
0x14000443d  bt      eax, 13h
0x140004441  jnb     loc_1400044DB
0x140004447  cmp     ecx, 1803h
0x14000444d  jz      loc_14000467F
0x140004453  mov     eax, [rdi+20h]
0x140004456  mov     ecx, 1803h
0x14000445b  and     eax, ecx
0x14000445d  cmp     eax, ecx
0x14000445f  jnz     loc_140004875
0x140004465  mov     eax, [rdi+20h]
0x140004468  test    al, 4
0x14000446a  jz      loc_1400046C3
0x140004470  mov     edx, [rdi+9Ch]
0x140004476  test    dl, 20h
0x140004479  jnz     short loc_1400044EF
0x14000447b  mov     rdx, rsi
0x14000447e  lea     rcx, [rbp+40h+BugCheckParameter3]
0x140004482  call    ??0?$Win32HMThreadLockBase@UtagWND@@$0A@$0A@@@QEAA@PEAUtagWND@@@Z
0x140004487  mov     eax, [rdi+20h]
0x14000448a  test    al, 40h
0x14000448c  jnz     loc_140004701
0x140004492  test    al, al
0x140004494  js      loc_14000503D
0x14000449a  xor     ebx, ebx
0x14000449c  mov     rax, [rsi+28h]
0x1400044a0  test    byte ptr [rax+1Fh], 10h
0x1400044a4  jnz     loc_1400050BB
0x1400044aa  mov     rdx, [rdi+70h]
0x1400044ae  test    rdx, rdx
0x1400044b1  jnz     loc_1400047EA
0x1400044b7  lea     rcx, [rbp+40h+BugCheckParameter3]; BugCheckParameter3
0x1400044bb  call    ??1?$Win32HMThreadLockAlways@UtagWND@@@@QEAA@XZ
0x1400044c0  sub     r12d, 1
0x1400044c4  mov     [rsp+140h+var_C4], r12d
0x1400044c9  js      loc_14000457E
0x1400044cf  add     rdi, 0A8h
0x1400044d6  jmp     loc_1400043FD
0x1400044db  cmp     ecx, 1807h
0x1400044e1  jnz     loc_140004447
0x1400044e7  or      eax, 8
0x1400044ea  mov     [rdi+20h], eax
0x1400044ed  jmp     short loc_1400044C0
0x1400044ef  mov     rax, [rsi+28h]
0x1400044f3  test    byte ptr [rax+1Fh], 20h
0x1400044f7  jnz     short loc_14000447B
0x1400044f9  bt      edx, 9
0x1400044fd  jnb     loc_1400045CB
0x140004503  mov     rcx, [rdi+80h]
0x14000450a  call    cs:__imp_ValidateHmonitorNoRip
0x140004511  nop     dword ptr [rax+rax+00h]
0x140004516  mov     rbx, rax
0x140004519  test    rax, rax
0x14000451c  jz      loc_14000447B
0x140004522  test    dword ptr [rdi+9Ch], 200h
0x14000452c  jnz     loc_140004F8E
0x140004532  mov     rcx, [rdi+80h]
0x140004539  call    cs:__imp_ValidateHmonitor
0x140004540  nop     dword ptr [rax+rax+00h]
0x140004545  cmp     rax, rbx
0x140004548  jz      loc_14000461E
0x14000454e  lea     r8, [rdi+0A0h]
0x140004555  xor     r9d, r9d
0x140004558  mov     rdx, rbx
0x14000455b  mov     rcx, rsi; struct tagWND *
0x14000455e  call    UpdateMonitorForWindowAndChildren
0x140004563  mov     ecx, [rdi+9Ch]
0x140004569  shl     eax, 6
0x14000456c  xor     eax, ecx
0x14000456e  and     eax, 40h
0x140004571  xor     eax, ecx
0x140004573  mov     [rdi+9Ch], eax
0x140004579  jmp     loc_14000447B
0x14000457e  test    r13d, r13d
0x140004581  jnz     loc_1400050E4
0x140004587  mov     ebx, [rsp+140h+var_E0]
0x14000458b  lea     rcx, [rbp+40h+var_58]; BugCheckParameter3
0x14000458f  call    ??1?$Win32HMThreadLockAlways@UtagWND@@@@QEAA@XZ
0x140004594  cmp     [rbp+40h+var_88], 0
0x140004598  jz      short loc_1400045A1
0x14000459a  mov     rax, [rbp+40h+var_80]
0x14000459e  dec     dword ptr [rax+1Ch]
0x1400045a1  mov     eax, ebx
0x1400045a3  mov     rcx, [rbp+40h+var_38]
0x1400045a7  xor     rcx, rsp; StackCookie
0x1400045aa  call    __security_check_cookie
0x1400045af  mov     rbx, [rsp+140h+arg_10]
0x1400045b7  add     rsp, 110h
0x1400045be  pop     r15
0x1400045c0  pop     r14
0x1400045c2  pop     r13
0x1400045c4  pop     r12
0x1400045c6  pop     rdi
0x1400045c7  pop     rsi
0x1400045c8  pop     rbp
0x1400045c9  retn
0x1400045cb  xorps   xmm0, xmm0
0x1400045ce  movups  [rsp+140h+var_D8], xmm0
0x1400045d3  test    dl, dl
0x1400045d5  js      loc_140004F7C
0x1400045db  mov     rax, qword ptr [rsp+140h+var_D8]
0x1400045e0  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x1400045e5  cmp     eax, ecx
0x1400045e7  jge     loc_1400047E0
0x1400045ed  shr     rcx, 20h
0x1400045f1  shr     rax, 20h
0x1400045f5  cmp     eax, ecx
0x1400045f7  mov     ecx, ebx
0x1400045f9  jge     loc_1400047E0
0x1400045ff  test    ecx, ecx
0x140004601  lea     rdx, [rsp+140h+var_D8]
0x140004606  lea     r8, [rdi+88h]
0x14000460d  mov     rcx, rsi; struct tagWND *
0x140004610  cmovnz  rdx, rbx
0x140004614  call    GetNewMonitor
0x140004619  jmp     loc_140004516
0x14000461e  mov     r9, [rsi+28h]
0x140004622  movzx   ecx, word ptr [r9+11Eh]
0x14000462a  test    cx, cx
0x14000462d  jz      short loc_14000463D
0x14000462f  mov     rax, [rbx+28h]
0x140004633  cmp     [rax+3Ch], cx
0x140004637  jnz     loc_140004F9E
0x14000463d  mov     ecx, [r9+120h]
0x140004644  mov     eax, ecx
0x140004646  and     eax, 0Fh
0x140004649  cmp     al, 3
0x14000464b  jnz     loc_14000447B
0x140004651  mov     rax, [rbx+28h]
0x140004655  shr     ecx, 8
0x140004658  movzx   edx, word ptr [rax+54h]
0x14000465c  mov     eax, 1FFh
0x140004661  and     cx, ax
0x140004664  cmp     dx, cx
0x140004667  jz      loc_14000447B
0x14000466d  cmp     dx, [rsi+130h]
0x140004674  jz      loc_14000447B
0x14000467a  jmp     loc_14000454E
0x14000467f  mov     rax, [rsi+28h]
0x140004683  test    byte ptr [rax+13h], 4
0x140004687  jnz     loc_140004453
0x14000468d  mov     rcx, rdi; struct tagCVR *
0x140004690  call    ?ValidateZorder@@YAHPEAUtagCVR@@@Z
0x140004695  test    eax, eax
0x140004697  jz      loc_140004453
0x14000469d  or      dword ptr [rdi+20h], 0Ch
0x1400046a1  mov     rcx, [rdi+60h]
0x1400046a5  test    rcx, rcx
0x1400046a8  jz      loc_1400044C0
0x1400046ae  call    cs:__imp_GreDeleteObject
0x1400046b5  nop     dword ptr [rax+rax+00h]
0x1400046ba  mov     [rdi+60h], rbx
0x1400046be  jmp     loc_1400044C0
0x1400046c3  mov     rcx, rdi; struct tagCVR *
0x1400046c6  call    ?ReValidateZorder@@YAHPEAUtagCVR@@@Z
0x1400046cb  test    eax, eax
0x1400046cd  jz      short loc_1400046E2
0x1400046cf  mov     rdx, r15; struct tagWND *
0x1400046d2  mov     rcx, rdi; struct tagCVR *
0x1400046d5  call    ?ValidateWindowPos@@YAHPEAUtagCVR@@PEAUtagWND@@@Z
0x1400046da  test    eax, eax
0x1400046dc  jnz     loc_140004806
0x1400046e2  or      dword ptr [rdi+20h], 4
0x1400046e6  mov     r8d, 304h
0x1400046ec  xor     ecx, ecx
0x1400046ee  mov     r9d, 1
0x1400046f4  mov     rdx, rsi
0x1400046f7  call    SetOrClrWF
0x1400046fc  jmp     loc_140004470
0x140004701  mov     rax, [rsi+10h]
0x140004705  mov     rcx, [rax+1C8h]
0x14000470c  mov     eax, [rcx+0Ch]
0x14000470f  test    al, 40h
0x140004711  jnz     loc_140004FD8
0x140004717  xor     edx, edx
0x140004719  mov     rcx, rsi
0x14000471c  call    SetRedrawProp
0x140004721  mov     edx, 9
0x140004726  mov     rcx, rsi
0x140004729  call    ?SetVisible@@YA_NPEAUtagWND@@W4SetVisibleOptions@@@Z
0x14000472e  mov     bl, al
0x140004730  call    cs:__imp_W32GetUserSessionState
0x140004737  nop     dword ptr [rax+rax+00h]
0x14000473c  mov     ecx, 3
0x140004741  mov     rdx, rsi
0x140004744  cmp     dword ptr [rax+113C0h], 0
0x14000474b  lea     eax, [rcx-2]
0x14000474e  cmovbe  ecx, eax
0x140004751  xor     r9d, r9d
0x140004754  mov     dword ptr [rsp+140h+BugCheckParameter4], ecx
0x140004758  xor     r8d, r8d
0x14000475b  mov     ecx, 8002h
0x140004760  call    xxxWindowEvent
0x140004765  test    bl, bl
0x140004767  jz      short loc_14000477E
0x140004769  or      dword ptr [rdi+9Ch], 2
0x140004770  mov     rax, [rsi+28h]
0x140004774  test    byte ptr [rax+1Ah], 8
0x140004778  jz      loc_140004FE7
0x14000477e  mov     edx, 1
0x140004783  mov     rcx, rsi
0x140004786  call    ?IsTrayWindow@@YA_NPEBUtagWND@@W4TrayCheckOption@@@Z
0x14000478b  mov     rcx, [rsi+28h]
0x14000478f  xor     ebx, ebx
0x140004791  mov     dl, [rcx+10h]
0x140004794  movzx   ecx, word ptr [rcx+2Ah]
0x140004798  and     dl, 40h
0x14000479b  and     ecx, 0FFFF2FFFh
0x1400047a1  cmp     ecx, 2AAh
0x1400047a7  jnz     loc_140005009
0x1400047ad  test    dl, dl
0x1400047af  jnz     loc_140004FFA
0x1400047b5  test    al, al
0x1400047b7  jnz     loc_14000449C
0x1400047bd  cmp     [rsi+78h], rbx
0x1400047c1  jnz     loc_14000449C
0x1400047c7  test    dword ptr [rdi+20h], 40000000h
0x1400047ce  jz      loc_14000449C
0x1400047d4  or      dword ptr [rdi+9Ch], 10h
0x1400047db  jmp     loc_14000449C
0x1400047e0  mov     ecx, 1
0x1400047e5  jmp     loc_1400045FF
0x1400047ea  mov     r8d, [rdi+20h]
0x1400047ee  mov     rcx, rsi; struct tagWND *
0x1400047f1  shr     r8d, 3
0x1400047f5  not     r8d
0x1400047f8  and     r8d, 1
0x1400047fc  call    SelectWindowRgn
0x140004801  jmp     loc_1400044B7
0x140004806  mov     rdx, r15
0x140004809  mov     rcx, rsi; struct tagWND *
0x14000480c  call    UnlinkWindow
0x140004811  mov     rcx, [rdi+8]
0x140004815  call    PWInsertAfter
0x14000481a  mov     rdx, rax
0x14000481d  mov     r8, r15
0x140004820  mov     rcx, rsi; struct tagWND *
0x140004823  call    LinkWindow
0x140004828  mov     rax, [rsi+28h]
0x14000482c  inc     r13d
0x14000482f  mov     [rsp+140h+var_C8], r13d
0x140004834  test    byte ptr [rax+13h], 4
0x140004838  jz      loc_140004470
0x14000483e  mov     r8d, 304h
0x140004844  mov     r9d, 1
0x14000484a  mov     rdx, rsi
0x14000484d  xor     ecx, ecx
0x14000484f  call    SetOrClrWF
0x140004854  mov     rax, [rsi+28h]
0x140004858  mov     r8d, 808h
  ... truncated ...
```
