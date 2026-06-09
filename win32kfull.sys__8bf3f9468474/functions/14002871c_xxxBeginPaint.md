# xxxBeginPaint

- ea: `0x14002871c`
- end: `0x140028f59`
- name: `xxxBeginPaint`
- size: `2109`
- prototype: `__int64 __fastcall(struct tagWND *)`
- caller_count: `4`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140028550`
- `0x1400d6234`
- `0x14010bbb8`
- `0x1402d97a0`

## callees

- `0x14001593c`
- `0x1400209c0`
- `0x140020ba0`
- `0x14002832c`
- `0x14002871c`
- `0x140028f60`
- `0x140028fe8`
- `0x140029074`
- `0x1400291d0`
- `0x14002988c`
- `0x14002b844`
- `0x1400be70c`
- `0x1401e32d0`
- `0x1401f11e0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002887a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002887a`
- `win32kbase!_GetDCEx` at `0x140028a13`
- `win32kbase!_GetDCEx` at `0x140028a13`
- `win32kbase!CreateEmptyRgnPublic` at `0x140028e3b`
- `win32kbase!CreateEmptyRgnPublic` at `0x140028e3b`
- `win32kbase!GreGetClipBox` at `0x140028a3d`
- `win32kbase!GreGetClipBox` at `0x140028a3d`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x140028b0d`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x140028b0d`
- `win32kbase!GreCombineRgn` at `0x140028f43`
- `win32kbase!GreCombineRgn` at `0x140028f43`
- `win32kbase!IsWindowDesktopComposed` at `0x14002876a`
- `win32kbase!IsWindowDesktopComposed` at `0x1400287c8`
- `win32kbase!IsWindowDesktopComposed` at `0x140028834`
- `win32kbase!IsWindowDesktopComposed` at `0x1400288d2`
- `win32kbase!IsWindowDesktopComposed` at `0x140028928`
- `win32kbase!IsWindowDesktopComposed` at `0x140028996`
- `win32kbase!IsWindowDesktopComposed` at `0x14002876a`
- `win32kbase!IsWindowDesktopComposed` at `0x1400287c8`
- `win32kbase!IsWindowDesktopComposed` at `0x140028834`
- `win32kbase!IsWindowDesktopComposed` at `0x1400288d2`
- `win32kbase!IsWindowDesktopComposed` at `0x140028928`
- `win32kbase!IsWindowDesktopComposed` at `0x140028996`
- `win32kbase!ReferenceDwmApiPort` at `0x140028b3f`
- `win32kbase!ReferenceDwmApiPort` at `0x140028bba`
- `win32kbase!ReferenceDwmApiPort` at `0x140028c39`
- `win32kbase!ReferenceDwmApiPort` at `0x140028cb8`
- `win32kbase!ReferenceDwmApiPort` at `0x140028d37`
- `win32kbase!ReferenceDwmApiPort` at `0x140028db5`
- `win32kbase!ReferenceDwmApiPort` at `0x140028b3f`
- `win32kbase!ReferenceDwmApiPort` at `0x140028bba`
- `win32kbase!ReferenceDwmApiPort` at `0x140028c39`
- `win32kbase!ReferenceDwmApiPort` at `0x140028cb8`
- `win32kbase!ReferenceDwmApiPort` at `0x140028d37`
- `win32kbase!ReferenceDwmApiPort` at `0x140028db5`
- `WIN32K!W32GetUserSessionState` at `0x140028734`
- `WIN32K!W32GetUserSessionState` at `0x140028e25`
- `WIN32K!W32GetUserSessionState` at `0x140028e4a`
- `WIN32K!W32GetUserSessionState` at `0x140028e5d`
- `WIN32K!W32GetUserSessionState` at `0x140028e77`
- `WIN32K!W32GetUserSessionState` at `0x140028e9a`
- `WIN32K!W32GetUserSessionState` at `0x140028eb8`
- `WIN32K!W32GetUserSessionState` at `0x140028f24`
- `WIN32K!W32GetUserSessionState` at `0x140028734`
- `WIN32K!W32GetUserSessionState` at `0x140028e25`
- `WIN32K!W32GetUserSessionState` at `0x140028e4a`
- `WIN32K!W32GetUserSessionState` at `0x140028e5d`
- `WIN32K!W32GetUserSessionState` at `0x140028e77`
- `WIN32K!W32GetUserSessionState` at `0x140028e9a`
- `WIN32K!W32GetUserSessionState` at `0x140028eb8`
- `WIN32K!W32GetUserSessionState` at `0x140028f24`

## pseudocode

```c
__int64 __fastcall xxxBeginPaint(struct tagWND *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rax
  int v6; // ebx
  int v7; // esi
  int v8; // r12d
  _DWORD *v9; // rax
  int v10; // r15d
  int v11; // ebp
  int v12; // eax
  int v13; // r15d
  __int64 v14; // rax
  int v15; // ebx
  int v16; // esi
  int v17; // r12d
  _DWORD *v18; // rax
  int v19; // r15d
  int v20; // ebp
  int v21; // eax
  int v22; // r15d
  __int64 v23; // rax
  char v24; // cl
  int v25; // ebx
  int v26; // esi
  int v27; // r12d
  __int64 v28; // rcx
  unsigned int *v29; // rax
  unsigned int v30; // r15d
  int v31; // ebp
  int v32; // eax
  int v33; // r15d
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v35; // rax
  int v36; // r12d
  int v37; // r15d
  int v38; // ebp
  int v39; // ebx
  _DWORD *v40; // rax
  int v41; // ebp
  int v42; // ebx
  int v43; // r15d
  __int64 v44; // rax
  int v45; // r15d
  int v46; // ebp
  int v47; // ebx
  _DWORD *v48; // rax
  int v49; // ebp
  int v50; // ebx
  int v51; // r15d
  __int64 v52; // rcx
  int v53; // r14d
  int v54; // esi
  int v55; // ebx
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // r9
  unsigned int *v60; // rax
  int v61; // esi
  int v62; // ebx
  int v63; // r14d
  __int64 v64; // rax
  __int64 v65; // rsi
  __int64 DCEx; // rax
  __int64 v67; // rbx
  __int64 result; // rax
  HRGN NCUpdateRgn; // rbx
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  void *v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // r8
  void *v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  void *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r8
  void *v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r8
  void *v89; // rax
  __int64 v90; // rdx
  __int64 v91; // rcx
  __int64 v92; // r8
  void *v93; // rax
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // r8
  __int64 v97; // r9
  __int64 EmptyRgnPublic; // rbx
  __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // r8
  __int64 v102; // r9
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // r8
  __int64 v106; // r9
  __int64 UserSessionState; // rax
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // r8
  __int64 v111; // r9
  BOOL v112; // ebx
  __int64 v113; // rax
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // r8
  __int64 v117; // r9
  __int64 v118; // rax
  __int64 v119; // rbx
  __int64 v120; // rax
  _OWORD v121[5]; // [rsp+20h] [rbp-58h] BYREF

  if ( (*(_DWORD *)(W32GetUserSessionState(a1, a2, a3, a4) + 66784) & 0x10000000) == 0 )
    goto LABEL_6;
  v5 = *((_QWORD *)a1 + 5);
  v6 = *(_DWORD *)(v5 + 28);
  v7 = *(_DWORD *)(v5 + 24);
  v8 = *(_DWORD *)(v5 + 232);
  *(_BYTE *)(v5 + 20) |= 4u;
  if ( !(unsigned int)IsWindowDesktopComposed(a1) )
    goto LABEL_6;
  v9 = (_DWORD *)*((_QWORD *)a1 + 5);
  v10 = v9[7];
  v11 = v7 ^ v9[6];
  v12 = v8 ^ v9[58];
  v13 = v6 ^ v10;
  if ( !v13 )
  {
    if ( v11 )
      goto LABEL_76;
    if ( !v12 )
      goto LABEL_6;
  }
  if ( (v13 & 0xB9CF0000) != 0 )
  {
LABEL_73:
    DirtyVisRgnTrackers(a1);
    v89 = (void *)ReferenceDwmApiPort(v87, v86, v88);
    DwmAsyncChildStyleChange(v89);
    goto LABEL_74;
  }
LABEL_76:
  if ( (v11 & 0x4E27A9) != 0 || (v12 & 0x372C0) != 0 )
    goto LABEL_73;
LABEL_74:
  if ( (v13 & 0x1C40000) != 0 || (v11 & 0x200A0381) != 0 )
    WindowMargins::CheckForChanges(a1, 1);
LABEL_6:
  v14 = *((_QWORD *)a1 + 5);
  v15 = *(_DWORD *)(v14 + 28);
  v16 = *(_DWORD *)(v14 + 24);
  v17 = *(_DWORD *)(v14 + 232);
  *(_BYTE *)(v14 + 18) &= ~0x40u;
  if ( !(unsigned int)IsWindowDesktopComposed(a1) )
    goto LABEL_10;
  v18 = (_DWORD *)*((_QWORD *)a1 + 5);
  v19 = v18[7];
  v20 = v16 ^ v18[6];
  v21 = v17 ^ v18[58];
  v22 = v15 ^ v19;
  if ( !v22 )
  {
    if ( v20 )
      goto LABEL_48;
    if ( !v21 )
      goto LABEL_10;
  }
  if ( (v22 & 0xB9CF0000) != 0 )
  {
LABEL_45:
    DirtyVisRgnTrackers(a1);
    v73 = (void *)ReferenceDwmApiPort(v71, v70, v72);
    DwmAsyncChildStyleChange(v73);
    goto LABEL_46;
  }
LABEL_48:
  if ( (v20 & 0x4E27A9) != 0 || (v21 & 0x372C0) != 0 )
    goto LABEL_45;
LABEL_46:
  if ( (v22 & 0x1C40000) != 0 || (v20 & 0x200A0381) != 0 )
    WindowMargins::CheckForChanges(a1, 1);
LABEL_10:
  v23 = *((_QWORD *)a1 + 5);
  v24 = *(_BYTE *)(v23 + 17);
  if ( (v24 & 8) != 0 )
  {
    do
    {
      SetOrClrWF(0, a1, 288, 1);
      NCUpdateRgn = GetNCUpdateRgn(a1, 0);
      xxxSendNCPaint(a1, NCUpdateRgn);
      DeleteMaybeSpecialRgn(NCUpdateRgn);
    }
    while ( (*(_BYTE *)(*((_QWORD *)a1 + 5) + 17LL) & 0x20) != 0 );
    goto LABEL_15;
  }
  v25 = *(_DWORD *)(v23 + 28);
  v26 = *(_DWORD *)(v23 + 24);
  v27 = *(_DWORD *)(v23 + 232);
  *(_BYTE *)(v23 + 17) = v24 & 0xDF;
  if ( !(unsigned int)IsWindowDesktopComposed(a1) )
    goto LABEL_15;
  v29 = (unsigned int *)*((_QWORD *)a1 + 5);
  v30 = v29[7];
  v28 = v29[6];
  v31 = v26 ^ v29[6];
  v32 = v27 ^ v29[58];
  v33 = v25 ^ v30;
  if ( !v33 )
  {
    if ( v31 )
      goto LABEL_83;
    if ( !v32 )
      goto LABEL_15;
  }
  if ( (v33 & 0xB9CF0000) != 0 )
  {
LABEL_80:
    DirtyVisRgnTrackers(a1);
    v93 = (void *)ReferenceDwmApiPort(v91, v90, v92);
    DwmAsyncChildStyleChange(v93);
    goto LABEL_81;
  }
LABEL_83:
  if ( (v31 & 0x4E27A9) != 0 || (v32 & 0x372C0) != 0 )
    goto LABEL_80;
LABEL_81:
  LOBYTE(v28) = (v33 & 0x1C40000) == 0;
  if ( ((unsigned __int8)v28 & ((v31 & 0x200A0381) == 0)) == 0 )
    WindowMargins::CheckForChanges(a1, 1);
LABEL_15:
  CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread(v28);
  if ( CurrentThreadWin32Thread )
    CurrentThreadWin32Thread = (_QWORD *)*CurrentThreadWin32Thread;
  if ( a1 == *(struct tagWND **)(CurrentThreadWin32Thread[58] + 416LL) )
    zzzInternalHideCaret();
  v35 = *((_QWORD *)a1 + 5);
  v36 = *(_BYTE *)(v35 + 17) & 2;
  if ( (*(_BYTE *)(v35 + 17) & 2) != 0 )
  {
    v37 = *(_DWORD *)(v35 + 28);
    v38 = *(_DWORD *)(v35 + 24);
    v39 = *(_DWORD *)(v35 + 232);
    *(_BYTE *)(v35 + 17) &= ~4u;
    if ( !(unsigned int)IsWindowDesktopComposed(a1) )
      goto LABEL_24;
    v40 = (_DWORD *)*((_QWORD *)a1 + 5);
    v41 = v40[6] ^ v38;
    v42 = v40[58] ^ v39;
    v43 = v40[7] ^ v37;
    if ( !v43 )
    {
      if ( v41 )
      {
LABEL_62:
        if ( (v41 & 0x4E27A9) == 0 && (v42 & 0x372C0) == 0 )
        {
LABEL_60:
          if ( (v43 & 0x1C40000) != 0 || (v41 & 0x200A0381) != 0 )
            WindowMargins::CheckForChanges(a1, 1);
LABEL_24:
          v44 = *((_QWORD *)a1 + 5);
          v45 = *(_DWORD *)(v44 + 28);
          v46 = *(_DWORD *)(v44 + 24);
          v47 = *(_DWORD *)(v44 + 232);
          *(_BYTE *)(v44 + 17) &= ~2u;
          if ( !(unsigned int)IsWindowDesktopComposed(a1) )
            goto LABEL_28;
          v48 = (_DWORD *)*((_QWORD *)a1 + 5);
          v49 = v48[6] ^ v46;
          v50 = v48[58] ^ v47;
          v51 = v48[7] ^ v45;
          if ( !v51 )
          {
            if ( v49 )
            {
LABEL_69:
              if ( (v49 & 0x4E27A9) == 0 && (v50 & 0x372C0) == 0 )
              {
LABEL_67:
                if ( (v51 & 0x1C40000) != 0 || (v49 & 0x200A0381) != 0 )
                  WindowMargins::CheckForChanges(a1, 1);
                goto LABEL_28;
              }
LABEL_66:
              DirtyVisRgnTrackers(a1);
              v85 = (void *)ReferenceDwmApiPort(v83, v82, v84);
              DwmAsyncChildStyleChange(v85);
              goto LABEL_67;
            }
            if ( !v50 )
              goto LABEL_28;
          }
          if ( (v51 & 0xB9CF0000) != 0 )
            goto LABEL_66;
          goto LABEL_69;
        }
LABEL_59:
        DirtyVisRgnTrackers(a1);
        v81 = (void *)ReferenceDwmApiPort(v79, v78, v80);
        DwmAsyncChildStyleChange(v81);
        goto LABEL_60;
      }
      if ( !v42 )
        goto LABEL_24;
    }
    if ( (v43 & 0xB9CF0000) != 0 )
      goto LABEL_59;
    goto LABEL_62;
  }
LABEL_28:
  v52 = *((_QWORD *)a1 + 5);
  if ( *(_QWORD *)(v52 + 136) || (*(_BYTE *)(v52 + 17) & 0x10) != 0 )
  {
    DecPaintCount(a1);
    v52 = *((_QWORD *)a1 + 5);
  }
  v53 = *(_DWORD *)(v52 + 28);
  v54 = *(_DWORD *)(v52 + 24);
  v55 = *(_DWORD *)(v52 + 232);
  *(_BYTE *)(v52 + 17) &= ~0x10u;
  if ( (unsigned int)IsWindowDesktopComposed(a1) )
  {
    v60 = (unsigned int *)*((_QWORD *)a1 + 5);
    v57 = v60[6];
    v61 = v57 ^ v54;
    v56 = v60[58];
    v62 = v56 ^ v55;
    v63 = v60[7] ^ v53;
    if ( !v63 )
    {
      if ( v61 )
      {
LABEL_55:
        if ( (v61 & 0x4E27A9) == 0 && (v62 & 0x372C0) == 0 )
        {
LABEL_53:
          LOBYTE(v57) = (v61 & 0x200A0381) == 0;
          if ( ((unsigned __int8)v57 & ((v63 & 0x1C40000) == 0)) == 0 )
            WindowMargins::CheckForChanges(a1, 1);
          goto LABEL_34;
        }
LABEL_52:
        DirtyVisRgnTrackers(a1);
        v77 = (void *)ReferenceDwmApiPort(v75, v74, v76);
        DwmAsyncChildStyleChange(v77);
        goto LABEL_53;
      }
      if ( !v62 )
        goto LABEL_34;
    }
    if ( (v63 & 0xB9CF0000) != 0 )
      goto LABEL_52;
    goto LABEL_55;
  }
LABEL_34:
  v64 = *((_QWORD *)a1 + 5);
  v65 = *(_QWORD *)(v64 + 136);
  *(_QWORD *)(v64 + 136) = 0;
  if ( (*(_BYTE *)(*((_QWORD *)a1 + 5) + 20LL) & 2) != 0 && v65 )
  {
    if ( !*(_QWORD *)(W32GetUserSessionState(v57, v56, v58, v59) + 42872) )
    {
      EmptyRgnPublic = CreateEmptyRgnPublic();
      *(_QWORD *)(W32GetUserSessionState(v100, v99, v101, v102) + 42872) = EmptyRgnPublic;
    }
    if ( *(_QWORD *)(W32GetUserSessionState(v95, v94, v96, v97) + 42872) )
    {
      UserSessionState = W32GetUserSessionState(v104, v103, v105, v106);
      if ( v65 == 1 )
      {
        v112 = ((*(_DWORD *)(UserSessionState + 63180) >> 10) & 1) == 0;
        v113 = W32GetUserSessionState(v109, v108, v110, v111);
        CalcWindowRgn(a1, *(_QWORD *)(v113 + 42872), v112);
      }
      else
      {
        v119 = *(_QWORD *)(UserSessionState + 42872);
        v120 = W32GetUserSessionState(v109, v108, v110, v111);
        GreCombineRgn(*(_QWORD *)(v120 + 42872), v119, v65, 2);
      }
      v118 = W32GetUserSessionState(v115, v114, v116, v117);
      ++*(_DWORD *)(v118 + 43044);
    }
  }
  *(_QWORD *)(a2 + 28) = 0;
  DCEx = _GetDCEx(a1, v65, 65664);
  *(_QWORD *)a2 = DCEx;
  v121[0] = 0;
  v67 = DCEx;
  if ( (unsigned int)GreGetClipBox(DCEx, a2 + 12, 1) != 1 )
  {
    if ( *(char *)(*(_QWORD *)(*((_QWORD *)a1 + 17) + 8LL) + 8LL) >= 0
      || (GetRect(a1, v121, 17), (unsigned int)IntersectRect(a2 + 12, a2 + 12, v121)) )
    {
      if ( v36 )
        xxxSendEraseBkgnd(a1);
    }
  }
  xxxSendChildNCPaint(a1);
  result = v67;
  *(_DWORD *)(a2 + 8) = (*(unsigned __int8 *)(*((_QWORD *)a1 + 5) + 17LL) >> 2) & 1;
  return result;
}

```

## disassembly

```asm
0x14002871c  mov     [rsp+arg_8], rdx
0x140028721  push    rbx
0x140028722  push    rbp
0x140028723  push    rsi
0x140028724  push    rdi
0x140028725  push    r12
0x140028727  push    r13
0x140028729  push    r14
0x14002872b  push    r15
0x14002872d  sub     rsp, 38h
0x140028731  mov     rdi, rcx
0x140028734  call    cs:__imp_W32GetUserSessionState
0x14002873b  nop     dword ptr [rax+rax+00h]
0x140028740  mov     r13d, 0FFFFFFF0h
0x140028746  test    dword ptr [rax+104E0h], 10000000h
0x140028750  jz      short loc_1400287B0
0x140028752  mov     rax, [rdi+28h]
0x140028756  mov     rcx, rdi
0x140028759  mov     ebx, [rax+1Ch]
0x14002875c  mov     esi, [rax+18h]
0x14002875f  mov     r12d, [rax+0E8h]
0x140028766  or      byte ptr [rax+14h], 4
0x14002876a  call    cs:__imp_IsWindowDesktopComposed
0x140028771  nop     dword ptr [rax+rax+00h]
0x140028776  test    eax, eax
0x140028778  jz      short loc_1400287B0
0x14002877a  mov     rax, [rdi+28h]
0x14002877e  mov     r14d, [rax+1Ch]
0x140028782  mov     r15d, r14d
0x140028785  mov     ecx, [rax+18h]
0x140028788  mov     ebp, ecx
0x14002878a  mov     edx, [rax+0E8h]
0x140028790  xor     ebp, esi
0x140028792  mov     eax, edx
0x140028794  xor     eax, r12d
0x140028797  xor     r15d, ebx
0x14002879a  jnz     loc_140028D20
0x1400287a0  test    ebp, ebp
0x1400287a2  jnz     loc_140028D81
0x1400287a8  test    eax, eax
0x1400287aa  jnz     loc_140028D20
0x1400287b0  mov     rax, [rdi+28h]
0x1400287b4  mov     rcx, rdi
0x1400287b7  mov     ebx, [rax+1Ch]
0x1400287ba  mov     esi, [rax+18h]
0x1400287bd  mov     r12d, [rax+0E8h]
0x1400287c4  and     byte ptr [rax+12h], 0BFh
0x1400287c8  call    cs:__imp_IsWindowDesktopComposed
0x1400287cf  nop     dword ptr [rax+rax+00h]
0x1400287d4  test    eax, eax
0x1400287d6  jz      short loc_14002880E
0x1400287d8  mov     rax, [rdi+28h]
0x1400287dc  mov     r14d, [rax+1Ch]
0x1400287e0  mov     r15d, r14d
0x1400287e3  mov     ecx, [rax+18h]
0x1400287e6  mov     ebp, ecx
0x1400287e8  mov     edx, [rax+0E8h]
0x1400287ee  xor     ebp, esi
0x1400287f0  mov     eax, edx
0x1400287f2  xor     eax, r12d
0x1400287f5  xor     r15d, ebx
0x1400287f8  jnz     loc_140028B28
0x1400287fe  test    ebp, ebp
0x140028800  jnz     loc_140028B89
0x140028806  test    eax, eax
0x140028808  jnz     loc_140028B28
0x14002880e  mov     rax, [rdi+28h]
0x140028812  mov     cl, [rax+11h]
0x140028815  test    cl, 8
0x140028818  jnz     loc_140028ADC
0x14002881e  mov     ebx, [rax+1Ch]
0x140028821  and     cl, 0DFh
0x140028824  mov     esi, [rax+18h]
0x140028827  mov     r12d, [rax+0E8h]
0x14002882e  mov     [rax+11h], cl
0x140028831  mov     rcx, rdi
0x140028834  call    cs:__imp_IsWindowDesktopComposed
0x14002883b  nop     dword ptr [rax+rax+00h]
0x140028840  test    eax, eax
0x140028842  jz      short loc_14002887A
0x140028844  mov     rax, [rdi+28h]
0x140028848  mov     r14d, [rax+1Ch]
0x14002884c  mov     r15d, r14d
0x14002884f  mov     ecx, [rax+18h]
0x140028852  mov     ebp, ecx
0x140028854  mov     edx, [rax+0E8h]
0x14002885a  xor     ebp, esi
0x14002885c  mov     eax, edx
0x14002885e  xor     eax, r12d
0x140028861  xor     r15d, ebx
0x140028864  jnz     loc_140028D9E
0x14002886a  test    ebp, ebp
0x14002886c  jnz     loc_140028DFF
0x140028872  test    eax, eax
0x140028874  jnz     loc_140028D9E
0x14002887a  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140028881  nop     dword ptr [rax+rax+00h]
0x140028886  test    rax, rax
0x140028889  jz      loc_140028F54
0x14002888f  mov     rax, [rax]
0x140028892  mov     rax, [rax+1D0h]
0x140028899  cmp     rdi, [rax+1A0h]
0x1400288a0  jnz     short loc_1400288A7
0x1400288a2  call    zzzInternalHideCaret
0x1400288a7  mov     rax, [rdi+28h]
0x1400288ab  movzx   ecx, byte ptr [rax+11h]
0x1400288af  mov     r12d, ecx
0x1400288b2  and     r12d, 2
0x1400288b6  jz      loc_140028966
0x1400288bc  mov     r15d, [rax+1Ch]
0x1400288c0  and     cl, 0FBh
0x1400288c3  mov     ebp, [rax+18h]
0x1400288c6  mov     ebx, [rax+0E8h]
0x1400288cc  mov     [rax+11h], cl
0x1400288cf  mov     rcx, rdi
0x1400288d2  call    cs:__imp_IsWindowDesktopComposed
0x1400288d9  nop     dword ptr [rax+rax+00h]
0x1400288de  test    eax, eax
0x1400288e0  jz      short loc_140028910
0x1400288e2  mov     rax, [rdi+28h]
0x1400288e6  mov     ecx, [rax+18h]
0x1400288e9  xor     ebp, ecx
0x1400288eb  mov     edx, [rax+0E8h]
0x1400288f1  xor     ebx, edx
0x1400288f3  mov     r14d, [rax+1Ch]
0x1400288f7  xor     r15d, r14d
0x1400288fa  jnz     loc_140028C22
0x140028900  test    ebp, ebp
0x140028902  jnz     loc_140028C83
0x140028908  test    ebx, ebx
0x14002890a  jnz     loc_140028C22
0x140028910  mov     rax, [rdi+28h]
0x140028914  mov     rcx, rdi
0x140028917  mov     r15d, [rax+1Ch]
0x14002891b  mov     ebp, [rax+18h]
0x14002891e  mov     ebx, [rax+0E8h]
0x140028924  and     byte ptr [rax+11h], 0FDh
0x140028928  call    cs:__imp_IsWindowDesktopComposed
0x14002892f  nop     dword ptr [rax+rax+00h]
0x140028934  test    eax, eax
0x140028936  jz      short loc_140028966
0x140028938  mov     rax, [rdi+28h]
0x14002893c  mov     ecx, [rax+18h]
0x14002893f  xor     ebp, ecx
0x140028941  mov     edx, [rax+0E8h]
0x140028947  xor     ebx, edx
0x140028949  mov     r14d, [rax+1Ch]
0x14002894d  xor     r15d, r14d
0x140028950  jnz     loc_140028CA1
0x140028956  test    ebp, ebp
0x140028958  jnz     loc_140028D02
0x14002895e  test    ebx, ebx
0x140028960  jnz     loc_140028CA1
0x140028966  mov     rcx, [rdi+28h]
0x14002896a  cmp     qword ptr [rcx+88h], 0
0x140028972  jnz     loc_140028ACB
0x140028978  test    byte ptr [rcx+11h], 10h
0x14002897c  jnz     loc_140028ACB
0x140028982  mov     r14d, [rcx+1Ch]
0x140028986  mov     esi, [rcx+18h]
0x140028989  mov     ebx, [rcx+0E8h]
0x14002898f  and     byte ptr [rcx+11h], 0EFh
0x140028993  mov     rcx, rdi
0x140028996  call    cs:__imp_IsWindowDesktopComposed
0x14002899d  nop     dword ptr [rax+rax+00h]
0x1400289a2  test    eax, eax
0x1400289a4  jz      short loc_1400289D3
0x1400289a6  mov     rax, [rdi+28h]
0x1400289aa  mov     ecx, [rax+18h]
0x1400289ad  xor     esi, ecx
0x1400289af  mov     edx, [rax+0E8h]
0x1400289b5  xor     ebx, edx
0x1400289b7  mov     ebp, [rax+1Ch]
0x1400289ba  xor     r14d, ebp
0x1400289bd  jnz     loc_140028BA6
0x1400289c3  test    esi, esi
0x1400289c5  jnz     loc_140028C04
0x1400289cb  test    ebx, ebx
0x1400289cd  jnz     loc_140028BA6
0x1400289d3  mov     rax, [rdi+28h]
0x1400289d7  mov     rsi, [rax+88h]
0x1400289de  mov     qword ptr [rax+88h], 0
0x1400289e9  mov     rax, [rdi+28h]
0x1400289ed  test    byte ptr [rax+14h], 2
0x1400289f1  jnz     loc_140028E1C
0x1400289f7  mov     r14, [rsp+78h+arg_8]
0x1400289ff  mov     r8d, 10080h
0x140028a05  mov     rdx, rsi
0x140028a08  mov     rcx, rdi
0x140028a0b  mov     qword ptr [r14+1Ch], 0
0x140028a13  call    cs:__imp__GetDCEx
0x140028a1a  nop     dword ptr [rax+rax+00h]
0x140028a1f  xorps   xmm0, xmm0
0x140028a22  lea     rbp, [r14+0Ch]
0x140028a26  mov     rdx, rbp
0x140028a29  mov     [r14], rax
0x140028a2c  mov     rcx, rax
0x140028a2f  mov     r8d, 1
0x140028a35  movups  [rsp+78h+var_58], xmm0
0x140028a3a  mov     rbx, rax
0x140028a3d  call    cs:__imp_GreGetClipBox
0x140028a44  nop     dword ptr [rax+rax+00h]
0x140028a49  cmp     eax, 1
0x140028a4c  jz      short loc_140028A9C
0x140028a4e  mov     rdx, [rdi+88h]
0x140028a55  mov     r8, [rdx+8]
0x140028a59  cmp     byte ptr [r8+8], 0
0x140028a5e  jl      short loc_140028A75
0x140028a60  test    r12d, r12d
0x140028a63  jz      short loc_140028A9C
0x140028a65  mov     r8, rsi
0x140028a68  mov     rdx, rbx
0x140028a6b  mov     rcx, rdi; struct tagWND *
0x140028a6e  call    xxxSendEraseBkgnd
0x140028a73  jmp     short loc_140028A9C
0x140028a75  mov     r8d, 11h
0x140028a7b  lea     rdx, [rsp+78h+var_58]
0x140028a80  mov     rcx, rdi
0x140028a83  call    GetRect
0x140028a88  lea     r8, [rsp+78h+var_58]
0x140028a8d  mov     rdx, rbp
0x140028a90  mov     rcx, rbp
0x140028a93  call    IntersectRect
0x140028a98  test    eax, eax
0x140028a9a  jnz     short loc_140028A60
0x140028a9c  mov     rcx, rdi; struct tagWND *
0x140028a9f  call    ?xxxSendChildNCPaint@@YAXPEAUtagWND@@@Z; xxxSendChildNCPaint(tagWND *)
0x140028aa4  mov     rax, [rdi+28h]
0x140028aa8  movzx   ecx, byte ptr [rax+11h]
0x140028aac  mov     rax, rbx
0x140028aaf  shr     ecx, 2
0x140028ab2  and     ecx, 1
0x140028ab5  mov     [r14+8], ecx
0x140028ab9  add     rsp, 38h
0x140028abd  pop     r15
0x140028abf  pop     r14
0x140028ac1  pop     r13
0x140028ac3  pop     r12
0x140028ac5  pop     rdi
0x140028ac6  pop     rsi
0x140028ac7  pop     rbp
0x140028ac8  pop     rbx
0x140028ac9  retn
0x140028acb  mov     rcx, rdi
0x140028ace  call    DecPaintCount
0x140028ad3  mov     rcx, [rdi+28h]
0x140028ad7  jmp     loc_140028982
0x140028adc  mov     r8d, 120h
0x140028ae2  mov     r9d, 1
0x140028ae8  mov     rdx, rdi
0x140028aeb  xor     ecx, ecx
0x140028aed  call    SetOrClrWF
0x140028af2  xor     edx, edx; int
0x140028af4  mov     rcx, rdi; struct tagWND *
0x140028af7  call    ?GetNCUpdateRgn@@YAPEAUHRGN__@@PEAUtagWND@@H@Z; GetNCUpdateRgn(tagWND *,int)
0x140028afc  mov     rdx, rax; HRGN
0x140028aff  mov     rcx, rdi; struct tagWND *
0x140028b02  mov     rbx, rax
0x140028b05  call    ?xxxSendNCPaint@@YAXPEAUtagWND@@PEAUHRGN__@@@Z; xxxSendNCPaint(tagWND *,HRGN__ *)
0x140028b0a  mov     rcx, rbx
0x140028b0d  call    cs:__imp_DeleteMaybeSpecialRgn
0x140028b14  nop     dword ptr [rax+rax+00h]
0x140028b19  mov     rax, [rdi+28h]
0x140028b1d  test    byte ptr [rax+11h], 20h
0x140028b21  jnz     short loc_140028ADC
0x140028b23  jmp     loc_14002887A
0x140028b28  test    r15d, 0B9CF0000h
0x140028b2f  jz      short loc_140028B89
0x140028b31  mov     esi, r13d
0x140028b34  mov     rcx, rdi; struct tagWND *
0x140028b37  call    DirtyVisRgnTrackers
0x140028b3c  mov     rbx, [rdi]
0x140028b3f  call    cs:__imp_ReferenceDwmApiPort
0x140028b46  nop     dword ptr [rax+rax+00h]
0x140028b4b  mov     r9d, r14d
0x140028b4e  mov     r8d, esi
0x140028b51  mov     rcx, rax; Object
0x140028b54  mov     rdx, rbx
0x140028b57  call    DwmAsyncChildStyleChange
0x140028b5c  test    r15d, 1C40000h
0x140028b63  setz    cl
0x140028b66  test    ebp, 200A0381h
0x140028b6c  setz    al
0x140028b6f  test    al, cl
0x140028b71  jnz     loc_14002880E
0x140028b77  mov     edx, 1
0x140028b7c  mov     rcx, rdi
0x140028b7f  call    ?CheckForChanges@WindowMargins@@YAXPEAUtagWND@@W4ChangeReason@1@@Z; WindowMargins::CheckForChanges(tagWND *,WindowMargins::ChangeReason)
0x140028b84  jmp     loc_14002880E
0x140028b89  test    ebp, 4E27A9h
0x140028b8f  jnz     loc_140028ECF
0x140028b95  test    eax, 372C0h
0x140028b9a  jz      short loc_140028B5C
0x140028b9c  mov     esi, 0F0000000h
0x140028ba1  mov     r14d, edx
0x140028ba4  jmp     short loc_140028B34
0x140028ba6  test    r14d, 0B9CF0000h
0x140028bad  jz      short loc_140028C04
0x140028baf  mov     rcx, rdi; struct tagWND *
0x140028bb2  call    DirtyVisRgnTrackers
  ... truncated ...
```
