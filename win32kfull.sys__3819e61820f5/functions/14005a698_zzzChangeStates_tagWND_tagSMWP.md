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
  __int64 v38; // rax
  unsigned int v39; // ecx
  __int64 v40; // rcx
  int v41; // r13d
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
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
  __int64 v63; // r9
  __int64 v64; // rcx
  __int128 v65; // xmm0
  __int64 v66; // rcx
  int v67; // eax
  __int64 v68; // rax
  __int64 v69; // r10
  __int64 v70; // rdx
  __int64 v71; // rcx
  int v72; // ebx
  BOOL v73; // r14d
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // rdx
  unsigned __int64 v77; // rcx
  __int64 v78; // rcx
  int v79; // ebx
  __int64 v80; // rdx
  char v81; // bl
  _DWORD *v82; // rdx
  __int64 UserSessionState; // rax
  __int64 v84; // rax
  int v85; // edx
  char v86; // bl
  int v87; // eax
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // rbx
  __int64 v91; // rcx
  __int64 v92; // rax
  HRGN ExplicitClipRgn; // rax
  int v94; // r15d
  int v95; // r12d
  int v96; // ecx
  char v97; // al
  __int64 v98; // rdx
  __int64 v99; // rcx
  __int64 v100; // r8
  __int64 v101; // r9
  __int64 v102; // rax
  int v103; // ecx
  __int64 v104; // rax
  int updated; // [rsp+60h] [rbp-A0h]
  __int128 v106; // [rsp+68h] [rbp-98h] BYREF
  int v107; // [rsp+78h] [rbp-88h]
  int v108; // [rsp+7Ch] [rbp-84h]
  int v109; // [rsp+80h] [rbp-80h]
  int v110; // [rsp+84h] [rbp-7Ch]
  __int64 v111; // [rsp+88h] [rbp-78h]
  struct tagWND *v112; // [rsp+90h] [rbp-70h]
  struct tagSMWP *v113; // [rsp+98h] [rbp-68h]
  struct tagPOINT v114; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v115; // [rsp+A8h] [rbp-58h] BYREF
  int v116; // [rsp+B0h] [rbp-50h]
  int v117; // [rsp+B4h] [rbp-4Ch]
  _BYTE v118[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v119; // [rsp+C0h] [rbp-40h]
  char v120[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 CurrentThreadWin32Thread; // [rsp+D0h] [rbp-30h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+D8h] [rbp-28h] BYREF
  ULONG_PTR v123[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v124; // [rsp+F8h] [rbp-8h] BYREF

  v112 = a1;
  v2 = a1;
  updated = 0;
  v107 = 0;
  v3 = 0;
  v110 = 0;
  v4 = 0;
  v118[0] = 0;
  v119 = 0;
  v5 = a2;
  v113 = a2;
  AtomicExecutionCheck::Arm((AtomicExecutionCheck *)v118);
  Win32HMThreadLockBase<tagWND,0,0>::Win32HMThreadLockBase<tagWND,0,0>(v123, v2);
  v9 = (__int64 *)*((_QWORD *)v5 + 5);
  v10 = *((_DWORD *)v5 + 7) - 1;
  v108 = v10;
  if ( v10 < 0 )
    goto LABEL_32;
  while ( 1 )
  {
    v11 = *v9;
    *(_QWORD *)&v106 = 0;
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
      v40 = *(_QWORD *)(v12 + 40);
      v109 = 0;
      if ( (*(_BYTE *)(v40 + 27) & 0x20) == 0 && (*(_BYTE *)(v40 + 26) & 8) == 0
        || (v85 = *(_DWORD *)(v40 + 100) - *(_DWORD *)(v40 + 92),
            LODWORD(v111) = *(_DWORD *)(v40 + 96) - *(_DWORD *)(v40 + 88),
            HIDWORD(v111) = v85,
            (_DWORD)v111 == *((_DWORD *)v9 + 6))
        && v85 == *((_DWORD *)v9 + 7) )
      {
        v111 = v106;
      }
      else
      {
        v109 = 1;
      }
      if ( *(_DWORD *)(v40 + 88) != *((_DWORD *)v9 + 4) || (v41 = 0, *(_DWORD *)(v40 + 92) != *((_DWORD *)v9 + 5)) )
        v41 = 1;
      v106 = *(_OWORD *)(*((_QWORD *)v2 + 5) + 104LL);
      if ( IsChildWindowDpiBoundary((const struct tagWND *)v12) )
      {
        if ( (*((_DWORD *)v9 + 39) & 0x100) == 0 )
        {
          v3 = v12 + 224;
          *(_DWORD *)(v12 + 224) = 0;
          *(_DWORD *)(v12 + 228) = 0;
        }
        LogicalToPhysicalInPlaceRectWithSubpixel(v2, &v106, v3);
        PhysicalToLogicalInPlaceRectWithSubpixel(v12, &v106, v3);
        v110 = 1;
      }
      v43 = *(_QWORD *)(v12 + 40);
      v44 = *(unsigned int *)(v43 + 88);
      v45 = *(unsigned int *)(v43 + 92);
      *(_DWORD *)(v43 + 88) = *((_DWORD *)v9 + 4);
      *(_DWORD *)(*(_QWORD *)(v12 + 40) + 92LL) = *((_DWORD *)v9 + 5);
      DesktopWindow = GetDesktopWindow(v12, v42, v44, v45);
      v49 = DWORD1(v106);
      v50 = v106;
      if ( v2 != (struct tagWND *)DesktopWindow )
      {
        *(_DWORD *)(*(_QWORD *)(v12 + 40) + 88LL) += v106;
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
      v63 = *((_QWORD *)PtiCurrent() + 58);
      if ( v12 == *(_QWORD *)(v63 + 416) )
      {
        v92 = GetDesktopWindow(
                v12,
                (unsigned int)(*((_DWORD *)v9 + 19) + *(_DWORD *)(*(_QWORD *)(v12 + 40) + 108LL) - *((_DWORD *)v9 + 11)),
                (unsigned int)(*((_DWORD *)v9 + 18) + *(_DWORD *)(*(_QWORD *)(v12 + 40) + 104LL) - *((_DWORD *)v9 + 10)),
                v63);
        if ( v112 != (struct tagWND *)v92 )
        {
          v62 = (unsigned int)(v62 - v50);
          v61 = (unsigned int)(v61 - v49);
        }
        if ( (unsigned int)v62 | (unsigned int)v61 )
        {
          *(_DWORD *)(v63 + 436) += v62;
          *(_DWORD *)(v63 + 440) += v61;
        }
      }
      v64 = *(_QWORD *)(v12 + 40);
      v65 = *(_OWORD *)(v64 + 104);
      *(_DWORD *)(v64 + 104) = *((_DWORD *)v9 + 10);
      v66 = *(_QWORD *)(v12 + 40);
      v67 = *((_DWORD *)v9 + 11);
      v106 = v65;
      *(_DWORD *)(v66 + 108) = v67;
      v68 = GetDesktopWindow(v12, v61, v62, v63);
      if ( v69 != v68 )
      {
        *(_DWORD *)(*(_QWORD *)(v12 + 40) + 104LL) += v50;
        *(_DWORD *)(*(_QWORD *)(v12 + 40) + 108LL) += v49;
      }
      *(_DWORD *)(*(_QWORD *)(v12 + 40) + 112LL) = *((_DWORD *)v9 + 12) + *(_DWORD *)(*(_QWORD *)(v12 + 40) + 104LL);
      *(_DWORD *)(*(_QWORD *)(v12 + 40) + 116LL) = *((_DWORD *)v9 + 13) + *(_DWORD *)(*(_QWORD *)(v12 + 40) + 108LL);
      v70 = *(_QWORD *)(v12 + 40);
      v71 = v106 - *(_QWORD *)(v70 + 104);
      if ( (_QWORD)v106 == *(_QWORD *)(v70 + 104) )
        v71 = *((_QWORD *)&v106 + 1) - *(_QWORD *)(v70 + 112);
      v72 = 0;
      v73 = v71 == 0;
      FixupMonitorRgn((struct tagWND *)v12, (v9[4] & 8) == 0);
      if ( !v109 )
        goto LABEL_86;
      *((_DWORD *)v9 + 39) |= 1u;
      if ( (*((_DWORD *)v9 + 39) & 0x1000) != 0 )
        tagWND::ComputeDominantState((tagWND *)v12);
      v80 = *(_QWORD *)(v12 + 40);
      if ( (*(_BYTE *)(v80 + 27) & 0x20) != 0 )
      {
        v81 = *(_BYTE *)(v80 + 26);
        if ( (v81 & 0x20) == 0 )
        {
          v86 = v81 & 8;
          *(_QWORD *)&v106 = 0;
          v87 = RecreateRedirectionBitmap((struct tagWND *)v12, 0, (unsigned __int64)&v106 & -(__int64)(v86 != 0));
          updated = v87;
          if ( v86 && v87 >= 0 )
          {
            v90 = v106;
            if ( (_QWORD)v106 )
            {
              if ( (unsigned int)SetOldRedirectionBitmap(v12, v106) )
                v90 = 0;
            }
            else
            {
              if ( !*(_QWORD *)W32GetUserSessionState(v89, v88, v74, v75) || !IS_USERCRIT_OWNED_AT_ALL() )
                KeBugCheckEx(0x164u, 0x2Au, 0, 0, 0);
              CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v91);
              v120[0] = 1;
              ++*(_DWORD *)(CurrentThreadWin32Thread + 28);
              xxxInternalInvalidate((struct tagWND *)v12, (HRGN)1, 0x401u);
              AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v120);
            }
          }
          else
          {
            v90 = v106;
          }
          if ( v90 )
            DeleteOrSetRedirectionBitmap(v12, v90, 1);
          v72 = 0;
          goto LABEL_86;
        }
        v72 = 0;
      }
      if ( (unsigned int)IsWindowDesktopComposed(v12) )
      {
        v82 = *(_DWORD **)(v12 + 40);
        *(_QWORD *)&v106 = 0;
        LODWORD(v106) = v82[24] - v82[22];
        DWORD1(v106) = v82[25] - v82[23];
        UserSessionState = W32GetUserSessionState(DWORD1(v106), v82, v74, v75);
        updated = UpdateSprite(
                    *(HDEV *)(*(_QWORD *)(UserSessionState + 56744) + 40LL),
                    (struct tagWND *)v12,
                    0,
                    (__int64)&v106,
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
      v76 = *((unsigned int *)v9 + 18);
      if ( v9[9] || v110 )
      {
        v77 = *(_QWORD *)(*(_QWORD *)(v12 + 40) + 136LL);
        if ( v77 > 1 )
          GreOffsetRgn(v77, v76, *((unsigned int *)v9 + 19));
        OffsetChildren((struct tagWND *)v12);
      }
      if ( v41 || !v73 || v54 || v56 )
      {
        v78 = *(_QWORD *)(v12 + 40);
        v114 = *(struct tagPOINT *)(v78 + 88);
        v124 = 0;
        if ( v41 )
        {
          if ( (*(_DWORD *)(v12 + 380) & 0x400) != 0 )
            RemoveWindowFullScreen(v12);
          v76 = *(_QWORD *)(v12 + 40);
          if ( (*(_BYTE *)(v76 + 26) & 8) != 0 )
          {
            v79 = v109;
            if ( v109 )
            {
              v94 = -v54;
              v95 = -v56;
              v116 = *(_DWORD *)(v76 + 96) - *(_DWORD *)(v76 + 88);
              v96 = *(_DWORD *)(v76 + 100) - *(_DWORD *)(v76 + 92);
              DWORD2(v124) = v94 + v111;
              v117 = v96;
              HIDWORD(v124) = v95 + HIDWORD(v111);
              v115 = 0;
              *(_QWORD *)&v124 = __PAIR64__(v95, v94);
              IntersectRect(&v124, &v124, &v115);
            }
            if ( *(_DWORD *)(W32GetUserSessionState(v78, v76, v74, v75) + 43048) )
            {
              InvalidateGDIWindows(v12);
              GreClientRgnUpdated(1);
            }
            if ( !v79 || (v72 = 1, (unsigned int)IsWindowDesktopComposed(v12)) )
              v72 = 0;
          }
        }
        if ( (*(_BYTE *)(*(_QWORD *)(v12 + 40) + 26LL) & 8) != 0 )
        {
          v84 = W32GetUserSessionState(v78, v76, v74, v75);
          updated = UpdateSprite(
                      *(HDEV *)(*(_QWORD *)(v84 + 56744) + 40LL),
                      (struct tagWND *)v12,
                      &v114,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      (unsigned __int64)&v124 & -(__int64)(v72 != 0));
        }
      }
      v5 = v113;
      v2 = v112;
      v10 = v108;
      v4 = v107;
    }
    if ( (v9[4] & 4) == 0 )
    {
      if ( (unsigned int)ReValidateZorder((struct tagCVR *)v9)
        && (unsigned int)ValidateWindowPos((struct tagCVR *)v9, v2) )
      {
        UnlinkWindow((struct tagWND *)v12);
        PWInsertAfter(v9[1]);
        LinkWindow((struct tagWND *)v12);
        v38 = *(_QWORD *)(v12 + 40);
        v107 = ++v4;
        if ( (*(_BYTE *)(v38 + 19) & 4) == 0 )
          goto LABEL_9;
        SetOrClrWF(0, v12, 772, 1);
        v25 = 2056;
        LOBYTE(v39) = ~*(_BYTE *)(*(_QWORD *)(v12 + 40) + 24LL);
        v26 = (v39 >> 3) & 1;
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
        v106 = 0;
        if ( (v14 & 0x80u) != 0 )
          v106 = *(_OWORD *)(v9 + 17);
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
                                 ^ (unsigned __int8)((unsigned __int8)UpdateMonitorForWindowAndChildren(
                                                                        (struct tagWND *)v12,
                                                                        (struct tagMONITOR *)v19) << 6))
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
        v97 = IsTrayWindow(v12, 1);
        v3 = 0;
        if ( (v9[4] & 0x1F) != 0x1F && v97 && (*(_WORD *)(*(_QWORD *)(v12 + 40) + 42LL) & 0x2FFF) != 0x2AA )
        {
          *((_DWORD *)v5 + 6) |= 1u;
          *((_DWORD *)v9 + 8) |= 0x20000000u;
        }
        SetRedrawProp(v12, 0);
        if ( (unsigned __int8)SetVisible(v12, 10) )
          DecomposeWindowIfNeeded((struct tagWND *)v12);
        v102 = W32GetUserSessionState(v99, v98, v100, v101);
        v103 = 3;
        if ( !*(_DWORD *)(v102 + 70592) )
          v103 = 1;
        xxxWindowEvent(0x8003u, (struct tagWND *)v12, 0, 0, v103);
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
    xxxWindowEvent(0x8002u, (struct tagWND *)v12, 0, 0, v34);
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
    v108 = --v10;
    if ( v10 < 0 )
      break;
    v9 += 21;
  }
  if ( v4 )
  {
    v104 = W32GetUserSessionState(v11, v6, v7, v8);
    xxxWindowEvent(0x8004u, v2, -4, 0, *(_DWORD *)(v104 + 70592) != 0 ? 2 : 0);
  }
  LODWORD(v3) = updated;
LABEL_32:
  Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v123);
  if ( v118[0] )
    --*(_DWORD *)(v119 + 28);
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
