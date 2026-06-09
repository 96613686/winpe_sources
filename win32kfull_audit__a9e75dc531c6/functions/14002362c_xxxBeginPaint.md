# xxxBeginPaint

- ea: `0x14002362c`
- end: `0x140023e69`
- name: `xxxBeginPaint`
- size: `2109`
- prototype: `__int64 __fastcall(unsigned int **, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140023460`
- `0x1400381cc`
- `0x140084578`
- `0x1402db660`

## callees

- `0x14001af00`
- `0x14001b0e0`
- `0x14002323c`
- `0x14002362c`
- `0x140023e70`
- `0x140023ef8`
- `0x140023f84`
- `0x1400240e0`
- `0x14002479c`
- `0x140026790`
- `0x14008c314`
- `0x14008dabc`
- `0x1400e491c`
- `0x1401f56c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002378a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002378a`
- `win32kbase!_GetDCEx` at `0x140023923`
- `win32kbase!_GetDCEx` at `0x140023923`
- `win32kbase!CreateEmptyRgnPublic` at `0x140023d4b`
- `win32kbase!CreateEmptyRgnPublic` at `0x140023d4b`
- `win32kbase!GreGetClipBox` at `0x14002394d`
- `win32kbase!GreGetClipBox` at `0x14002394d`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x140023a1d`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x140023a1d`
- `win32kbase!GreCombineRgn` at `0x140023e53`
- `win32kbase!GreCombineRgn` at `0x140023e53`
- `win32kbase!IsWindowDesktopComposed` at `0x14002367a`
- `win32kbase!IsWindowDesktopComposed` at `0x1400236d8`
- `win32kbase!IsWindowDesktopComposed` at `0x140023744`
- `win32kbase!IsWindowDesktopComposed` at `0x1400237e2`
- `win32kbase!IsWindowDesktopComposed` at `0x140023838`
- `win32kbase!IsWindowDesktopComposed` at `0x1400238a6`
- `win32kbase!IsWindowDesktopComposed` at `0x14002367a`
- `win32kbase!IsWindowDesktopComposed` at `0x1400236d8`
- `win32kbase!IsWindowDesktopComposed` at `0x140023744`
- `win32kbase!IsWindowDesktopComposed` at `0x1400237e2`
- `win32kbase!IsWindowDesktopComposed` at `0x140023838`
- `win32kbase!IsWindowDesktopComposed` at `0x1400238a6`
- `win32kbase!ReferenceDwmApiPort` at `0x140023a4f`
- `win32kbase!ReferenceDwmApiPort` at `0x140023aca`
- `win32kbase!ReferenceDwmApiPort` at `0x140023b49`
- `win32kbase!ReferenceDwmApiPort` at `0x140023bc8`
- `win32kbase!ReferenceDwmApiPort` at `0x140023c47`
- `win32kbase!ReferenceDwmApiPort` at `0x140023cc5`
- `win32kbase!ReferenceDwmApiPort` at `0x140023a4f`
- `win32kbase!ReferenceDwmApiPort` at `0x140023aca`
- `win32kbase!ReferenceDwmApiPort` at `0x140023b49`
- `win32kbase!ReferenceDwmApiPort` at `0x140023bc8`
- `win32kbase!ReferenceDwmApiPort` at `0x140023c47`
- `win32kbase!ReferenceDwmApiPort` at `0x140023cc5`
- `WIN32K!W32GetUserSessionState` at `0x140023644`
- `WIN32K!W32GetUserSessionState` at `0x140023d35`
- `WIN32K!W32GetUserSessionState` at `0x140023d5a`
- `WIN32K!W32GetUserSessionState` at `0x140023d6d`
- `WIN32K!W32GetUserSessionState` at `0x140023d87`
- `WIN32K!W32GetUserSessionState` at `0x140023daa`
- `WIN32K!W32GetUserSessionState` at `0x140023dc8`
- `WIN32K!W32GetUserSessionState` at `0x140023e34`
- `WIN32K!W32GetUserSessionState` at `0x140023644`
- `WIN32K!W32GetUserSessionState` at `0x140023d35`
- `WIN32K!W32GetUserSessionState` at `0x140023d5a`
- `WIN32K!W32GetUserSessionState` at `0x140023d6d`
- `WIN32K!W32GetUserSessionState` at `0x140023d87`
- `WIN32K!W32GetUserSessionState` at `0x140023daa`
- `WIN32K!W32GetUserSessionState` at `0x140023dc8`
- `WIN32K!W32GetUserSessionState` at `0x140023e34`

## pseudocode

```c
__int64 __fastcall xxxBeginPaint(unsigned int **a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int *v8; // rax
  unsigned int v9; // ebx
  unsigned int v10; // esi
  unsigned int v11; // r12d
  unsigned int *v12; // rax
  unsigned int v13; // r15d
  int v14; // ebp
  int v15; // eax
  int v16; // r15d
  unsigned int *v17; // rax
  unsigned int v18; // ebx
  unsigned int v19; // esi
  unsigned int v20; // r12d
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int *v24; // rax
  unsigned int v25; // r15d
  int v26; // ebp
  int v27; // eax
  int v28; // r15d
  unsigned int *v29; // rax
  char v30; // cl
  unsigned int v31; // ebx
  unsigned int v32; // esi
  unsigned int v33; // r12d
  __int64 v34; // rdx
  __int64 v35; // rcx
  unsigned int *v36; // rax
  unsigned int v37; // r15d
  int v38; // ebp
  int v39; // eax
  int v40; // r15d
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  unsigned int *v45; // rax
  int v46; // r12d
  unsigned int v47; // r15d
  unsigned int v48; // ebp
  unsigned int v49; // ebx
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  unsigned int *v53; // rax
  int v54; // ebp
  int v55; // ebx
  int v56; // r15d
  unsigned int *v57; // rax
  unsigned int v58; // r15d
  unsigned int v59; // ebp
  unsigned int v60; // ebx
  unsigned int *v61; // rax
  int v62; // ebp
  int v63; // ebx
  int v64; // r15d
  unsigned int *v65; // rcx
  unsigned int v66; // r14d
  unsigned int v67; // esi
  unsigned int v68; // ebx
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // r9
  unsigned int *v73; // rax
  int v74; // esi
  int v75; // ebx
  int v76; // r14d
  unsigned int *v77; // rax
  __int64 v78; // rsi
  __int64 DCEx; // rax
  __int64 v80; // rbx
  __int64 result; // rax
  HRGN NCUpdateRgn; // rbx
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  void *v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // r8
  void *v90; // rax
  __int64 v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // r8
  void *v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // r8
  void *v98; // rax
  __int64 v99; // rdx
  __int64 v100; // rcx
  __int64 v101; // r8
  void *v102; // rax
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // r8
  void *v106; // rax
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // r9
  __int64 EmptyRgnPublic; // rbx
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  __int64 v115; // r9
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // r9
  __int64 UserSessionState; // rax
  __int64 v121; // rdx
  __int64 v122; // rcx
  __int64 v123; // r8
  __int64 v124; // r9
  BOOL v125; // ebx
  __int64 v126; // rax
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // r8
  __int64 v130; // r9
  __int64 v131; // rax
  __int64 v132; // rbx
  __int64 v133; // rax
  _OWORD v134[5]; // [rsp+20h] [rbp-58h] BYREF

  if ( (*(_DWORD *)(W32GetUserSessionState(a1, a2, a3, a4) + 66784) & 0x10000000) == 0 )
    goto LABEL_6;
  v8 = a1[5];
  v9 = v8[7];
  v10 = v8[6];
  v11 = v8[58];
  *((_BYTE *)v8 + 20) |= 4u;
  if ( !(unsigned int)IsWindowDesktopComposed(a1, v5, v6, v7) )
    goto LABEL_6;
  v12 = a1[5];
  v13 = v12[7];
  v5 = v12[58];
  v14 = v10 ^ v12[6];
  v15 = v11 ^ v12[58];
  v16 = v9 ^ v13;
  if ( !v16 )
  {
    if ( v14 )
      goto LABEL_76;
    if ( !v15 )
      goto LABEL_6;
  }
  if ( (v16 & 0xB9CF0000) != 0 )
  {
LABEL_73:
    DirtyVisRgnTrackers((struct tagWND *)a1, v5);
    v102 = (void *)ReferenceDwmApiPort(v100, v99, v101);
    DwmAsyncChildStyleChange(v102);
    goto LABEL_74;
  }
LABEL_76:
  if ( (v14 & 0x4E27A9) != 0 || (v15 & 0x372C0) != 0 )
    goto LABEL_73;
LABEL_74:
  if ( (v16 & 0x1C40000) != 0 || (v14 & 0x200A0381) != 0 )
    WindowMargins::CheckForChanges(a1, 1);
LABEL_6:
  v17 = a1[5];
  v18 = v17[7];
  v19 = v17[6];
  v20 = v17[58];
  *((_BYTE *)v17 + 18) &= ~0x40u;
  if ( !(unsigned int)IsWindowDesktopComposed(a1, v5, v6, v7) )
    goto LABEL_10;
  v24 = a1[5];
  v25 = v24[7];
  v21 = v24[58];
  v26 = v19 ^ v24[6];
  v27 = v20 ^ v24[58];
  v28 = v18 ^ v25;
  if ( !v28 )
  {
    if ( v26 )
      goto LABEL_48;
    if ( !v27 )
      goto LABEL_10;
  }
  if ( (v28 & 0xB9CF0000) != 0 )
  {
LABEL_45:
    DirtyVisRgnTrackers((struct tagWND *)a1, v21);
    v86 = (void *)ReferenceDwmApiPort(v84, v83, v85);
    DwmAsyncChildStyleChange(v86);
    goto LABEL_46;
  }
LABEL_48:
  if ( (v26 & 0x4E27A9) != 0 || (v27 & 0x372C0) != 0 )
    goto LABEL_45;
LABEL_46:
  if ( (v28 & 0x1C40000) != 0 || (v26 & 0x200A0381) != 0 )
    WindowMargins::CheckForChanges(a1, 1);
LABEL_10:
  v29 = a1[5];
  v30 = *((_BYTE *)v29 + 17);
  if ( (v30 & 8) != 0 )
  {
    do
    {
      SetOrClrWF(0, (struct tagWND *)a1, 288, 1);
      NCUpdateRgn = GetNCUpdateRgn((struct tagWND *)a1, 0);
      xxxSendNCPaint((struct tagWND *)a1, NCUpdateRgn);
      DeleteMaybeSpecialRgn(NCUpdateRgn);
    }
    while ( (*((_BYTE *)a1[5] + 17) & 0x20) != 0 );
    goto LABEL_15;
  }
  v31 = v29[7];
  v32 = v29[6];
  v33 = v29[58];
  *((_BYTE *)v29 + 17) = v30 & 0xDF;
  if ( !(unsigned int)IsWindowDesktopComposed(a1, v21, v22, v23) )
    goto LABEL_15;
  v36 = a1[5];
  v37 = v36[7];
  v35 = v36[6];
  v34 = v36[58];
  v38 = v32 ^ v36[6];
  v39 = v33 ^ v36[58];
  v40 = v31 ^ v37;
  if ( !v40 )
  {
    if ( v38 )
      goto LABEL_83;
    if ( !v39 )
      goto LABEL_15;
  }
  if ( (v40 & 0xB9CF0000) != 0 )
  {
LABEL_80:
    DirtyVisRgnTrackers((struct tagWND *)a1, v34);
    v106 = (void *)ReferenceDwmApiPort(v104, v103, v105);
    DwmAsyncChildStyleChange(v106);
    goto LABEL_81;
  }
LABEL_83:
  if ( (v38 & 0x4E27A9) != 0 || (v39 & 0x372C0) != 0 )
    goto LABEL_80;
LABEL_81:
  LOBYTE(v35) = (v40 & 0x1C40000) == 0;
  if ( ((unsigned __int8)v35 & ((v38 & 0x200A0381) == 0)) == 0 )
    WindowMargins::CheckForChanges(a1, 1);
LABEL_15:
  CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread(v35, v34);
  if ( CurrentThreadWin32Thread )
    CurrentThreadWin32Thread = (_QWORD *)*CurrentThreadWin32Thread;
  if ( a1 == *(unsigned int ***)(CurrentThreadWin32Thread[58] + 416LL) )
    zzzInternalHideCaret();
  v45 = a1[5];
  v46 = *((_BYTE *)v45 + 17) & 2;
  if ( (*((_BYTE *)v45 + 17) & 2) != 0 )
  {
    v47 = v45[7];
    v48 = v45[6];
    v49 = v45[58];
    *((_BYTE *)v45 + 17) &= ~4u;
    if ( !(unsigned int)IsWindowDesktopComposed(a1, v42, v43, v44) )
      goto LABEL_24;
    v53 = a1[5];
    v54 = v53[6] ^ v48;
    v50 = v53[58];
    v55 = v50 ^ v49;
    v56 = v53[7] ^ v47;
    if ( !v56 )
    {
      if ( v54 )
      {
LABEL_62:
        if ( (v54 & 0x4E27A9) == 0 && (v55 & 0x372C0) == 0 )
        {
LABEL_60:
          if ( (v56 & 0x1C40000) != 0 || (v54 & 0x200A0381) != 0 )
            WindowMargins::CheckForChanges(a1, 1);
LABEL_24:
          v57 = a1[5];
          v58 = v57[7];
          v59 = v57[6];
          v60 = v57[58];
          *((_BYTE *)v57 + 17) &= ~2u;
          if ( !(unsigned int)IsWindowDesktopComposed(a1, v50, v51, v52) )
            goto LABEL_28;
          v61 = a1[5];
          v62 = v61[6] ^ v59;
          v42 = v61[58];
          v63 = v42 ^ v60;
          v64 = v61[7] ^ v58;
          if ( !v64 )
          {
            if ( v62 )
            {
LABEL_69:
              if ( (v62 & 0x4E27A9) == 0 && (v63 & 0x372C0) == 0 )
              {
LABEL_67:
                if ( (v64 & 0x1C40000) != 0 || (v62 & 0x200A0381) != 0 )
                  WindowMargins::CheckForChanges(a1, 1);
                goto LABEL_28;
              }
LABEL_66:
              DirtyVisRgnTrackers((struct tagWND *)a1, v42);
              v98 = (void *)ReferenceDwmApiPort(v96, v95, v97);
              DwmAsyncChildStyleChange(v98);
              goto LABEL_67;
            }
            if ( !v63 )
              goto LABEL_28;
          }
          if ( (v64 & 0xB9CF0000) != 0 )
            goto LABEL_66;
          goto LABEL_69;
        }
LABEL_59:
        DirtyVisRgnTrackers((struct tagWND *)a1, v50);
        v94 = (void *)ReferenceDwmApiPort(v92, v91, v93);
        DwmAsyncChildStyleChange(v94);
        goto LABEL_60;
      }
      if ( !v55 )
        goto LABEL_24;
    }
    if ( (v56 & 0xB9CF0000) != 0 )
      goto LABEL_59;
    goto LABEL_62;
  }
LABEL_28:
  v65 = a1[5];
  if ( *((_QWORD *)v65 + 17) || (*((_BYTE *)v65 + 17) & 0x10) != 0 )
  {
    DecPaintCount(a1);
    v65 = a1[5];
  }
  v66 = v65[7];
  v67 = v65[6];
  v68 = v65[58];
  *((_BYTE *)v65 + 17) &= ~0x10u;
  if ( (unsigned int)IsWindowDesktopComposed(a1, v42, v43, v44) )
  {
    v73 = a1[5];
    v70 = v73[6];
    v74 = v70 ^ v67;
    v69 = v73[58];
    v75 = v69 ^ v68;
    v76 = v73[7] ^ v66;
    if ( !v76 )
    {
      if ( v74 )
      {
LABEL_55:
        if ( (v74 & 0x4E27A9) == 0 && (v75 & 0x372C0) == 0 )
        {
LABEL_53:
          LOBYTE(v70) = (v74 & 0x200A0381) == 0;
          if ( ((unsigned __int8)v70 & ((v76 & 0x1C40000) == 0)) == 0 )
            WindowMargins::CheckForChanges(a1, 1);
          goto LABEL_34;
        }
LABEL_52:
        DirtyVisRgnTrackers((struct tagWND *)a1, v69);
        v90 = (void *)ReferenceDwmApiPort(v88, v87, v89);
        DwmAsyncChildStyleChange(v90);
        goto LABEL_53;
      }
      if ( !v75 )
        goto LABEL_34;
    }
    if ( (v76 & 0xB9CF0000) != 0 )
      goto LABEL_52;
    goto LABEL_55;
  }
LABEL_34:
  v77 = a1[5];
  v78 = *((_QWORD *)v77 + 17);
  *((_QWORD *)v77 + 17) = 0;
  if ( (a1[5][5] & 2) != 0 && v78 )
  {
    if ( !*(_QWORD *)(W32GetUserSessionState(v70, v69, v71, v72) + 42872) )
    {
      EmptyRgnPublic = CreateEmptyRgnPublic();
      *(_QWORD *)(W32GetUserSessionState(v113, v112, v114, v115) + 42872) = EmptyRgnPublic;
    }
    if ( *(_QWORD *)(W32GetUserSessionState(v108, v107, v109, v110) + 42872) )
    {
      UserSessionState = W32GetUserSessionState(v117, v116, v118, v119);
      if ( v78 == 1 )
      {
        v125 = ((*(_DWORD *)(UserSessionState + 63180) >> 10) & 1) == 0;
        v126 = W32GetUserSessionState(v122, v121, v123, v124);
        CalcWindowRgn(a1, *(_QWORD *)(v126 + 42872), v125);
      }
      else
      {
        v132 = *(_QWORD *)(UserSessionState + 42872);
        v133 = W32GetUserSessionState(v122, v121, v123, v124);
        GreCombineRgn(*(_QWORD *)(v133 + 42872), v132, v78, 2);
      }
      v131 = W32GetUserSessionState(v128, v127, v129, v130);
      ++*(_DWORD *)(v131 + 43044);
    }
  }
  *(_QWORD *)(a2 + 28) = 0;
  DCEx = _GetDCEx(a1, v78, 65664);
  *(_QWORD *)a2 = DCEx;
  v134[0] = 0;
  v80 = DCEx;
  if ( (unsigned int)GreGetClipBox(DCEx, a2 + 12, 1) != 1 )
  {
    if ( *(char *)(*((_QWORD *)a1[17] + 1) + 8LL) >= 0
      || (GetRect(a1, v134, 17), (unsigned int)IntersectRect(a2 + 12, a2 + 12, v134)) )
    {
      if ( v46 )
        xxxSendEraseBkgnd((struct tagWND *)a1, v80, v78);
    }
  }
  xxxSendChildNCPaint((struct tagWND *)a1);
  result = v80;
  *(_DWORD *)(a2 + 8) = (*((unsigned __int8 *)a1[5] + 17) >> 2) & 1;
  return result;
}

```

## disassembly

```asm
0x14002362c  mov     [rsp+arg_8], rdx
0x140023631  push    rbx
0x140023632  push    rbp
0x140023633  push    rsi
0x140023634  push    rdi
0x140023635  push    r12
0x140023637  push    r13
0x140023639  push    r14
0x14002363b  push    r15
0x14002363d  sub     rsp, 38h
0x140023641  mov     rdi, rcx
0x140023644  call    cs:__imp_W32GetUserSessionState
0x14002364b  nop     dword ptr [rax+rax+00h]
0x140023650  mov     r13d, 0FFFFFFF0h
0x140023656  test    dword ptr [rax+104E0h], 10000000h
0x140023660  jz      short loc_1400236C0
0x140023662  mov     rax, [rdi+28h]
0x140023666  mov     rcx, rdi
0x140023669  mov     ebx, [rax+1Ch]
0x14002366c  mov     esi, [rax+18h]
0x14002366f  mov     r12d, [rax+0E8h]
0x140023676  or      byte ptr [rax+14h], 4
0x14002367a  call    cs:__imp_IsWindowDesktopComposed
0x140023681  nop     dword ptr [rax+rax+00h]
0x140023686  test    eax, eax
0x140023688  jz      short loc_1400236C0
0x14002368a  mov     rax, [rdi+28h]
0x14002368e  mov     r14d, [rax+1Ch]
0x140023692  mov     r15d, r14d
0x140023695  mov     ecx, [rax+18h]
0x140023698  mov     ebp, ecx
0x14002369a  mov     edx, [rax+0E8h]
0x1400236a0  xor     ebp, esi
0x1400236a2  mov     eax, edx
0x1400236a4  xor     eax, r12d
0x1400236a7  xor     r15d, ebx
0x1400236aa  jnz     loc_140023C30
0x1400236b0  test    ebp, ebp
0x1400236b2  jnz     loc_140023C91
0x1400236b8  test    eax, eax
0x1400236ba  jnz     loc_140023C30
0x1400236c0  mov     rax, [rdi+28h]
0x1400236c4  mov     rcx, rdi
0x1400236c7  mov     ebx, [rax+1Ch]
0x1400236ca  mov     esi, [rax+18h]
0x1400236cd  mov     r12d, [rax+0E8h]
0x1400236d4  and     byte ptr [rax+12h], 0BFh
0x1400236d8  call    cs:__imp_IsWindowDesktopComposed
0x1400236df  nop     dword ptr [rax+rax+00h]
0x1400236e4  test    eax, eax
0x1400236e6  jz      short loc_14002371E
0x1400236e8  mov     rax, [rdi+28h]
0x1400236ec  mov     r14d, [rax+1Ch]
0x1400236f0  mov     r15d, r14d
0x1400236f3  mov     ecx, [rax+18h]
0x1400236f6  mov     ebp, ecx
0x1400236f8  mov     edx, [rax+0E8h]
0x1400236fe  xor     ebp, esi
0x140023700  mov     eax, edx
0x140023702  xor     eax, r12d
0x140023705  xor     r15d, ebx
0x140023708  jnz     loc_140023A38
0x14002370e  test    ebp, ebp
0x140023710  jnz     loc_140023A99
0x140023716  test    eax, eax
0x140023718  jnz     loc_140023A38
0x14002371e  mov     rax, [rdi+28h]
0x140023722  mov     cl, [rax+11h]
0x140023725  test    cl, 8
0x140023728  jnz     loc_1400239EC
0x14002372e  mov     ebx, [rax+1Ch]
0x140023731  and     cl, 0DFh
0x140023734  mov     esi, [rax+18h]
0x140023737  mov     r12d, [rax+0E8h]
0x14002373e  mov     [rax+11h], cl
0x140023741  mov     rcx, rdi
0x140023744  call    cs:__imp_IsWindowDesktopComposed
0x14002374b  nop     dword ptr [rax+rax+00h]
0x140023750  test    eax, eax
0x140023752  jz      short loc_14002378A
0x140023754  mov     rax, [rdi+28h]
0x140023758  mov     r14d, [rax+1Ch]
0x14002375c  mov     r15d, r14d
0x14002375f  mov     ecx, [rax+18h]
0x140023762  mov     ebp, ecx
0x140023764  mov     edx, [rax+0E8h]
0x14002376a  xor     ebp, esi
0x14002376c  mov     eax, edx
0x14002376e  xor     eax, r12d
0x140023771  xor     r15d, ebx
0x140023774  jnz     loc_140023CAE
0x14002377a  test    ebp, ebp
0x14002377c  jnz     loc_140023D0F
0x140023782  test    eax, eax
0x140023784  jnz     loc_140023CAE
0x14002378a  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140023791  nop     dword ptr [rax+rax+00h]
0x140023796  test    rax, rax
0x140023799  jz      loc_140023E64
0x14002379f  mov     rax, [rax]
0x1400237a2  mov     rax, [rax+1D0h]
0x1400237a9  cmp     rdi, [rax+1A0h]
0x1400237b0  jnz     short loc_1400237B7
0x1400237b2  call    zzzInternalHideCaret
0x1400237b7  mov     rax, [rdi+28h]
0x1400237bb  movzx   ecx, byte ptr [rax+11h]
0x1400237bf  mov     r12d, ecx
0x1400237c2  and     r12d, 2
0x1400237c6  jz      loc_140023876
0x1400237cc  mov     r15d, [rax+1Ch]
0x1400237d0  and     cl, 0FBh
0x1400237d3  mov     ebp, [rax+18h]
0x1400237d6  mov     ebx, [rax+0E8h]
0x1400237dc  mov     [rax+11h], cl
0x1400237df  mov     rcx, rdi
0x1400237e2  call    cs:__imp_IsWindowDesktopComposed
0x1400237e9  nop     dword ptr [rax+rax+00h]
0x1400237ee  test    eax, eax
0x1400237f0  jz      short loc_140023820
0x1400237f2  mov     rax, [rdi+28h]
0x1400237f6  mov     ecx, [rax+18h]
0x1400237f9  xor     ebp, ecx
0x1400237fb  mov     edx, [rax+0E8h]
0x140023801  xor     ebx, edx
0x140023803  mov     r14d, [rax+1Ch]
0x140023807  xor     r15d, r14d
0x14002380a  jnz     loc_140023B32
0x140023810  test    ebp, ebp
0x140023812  jnz     loc_140023B93
0x140023818  test    ebx, ebx
0x14002381a  jnz     loc_140023B32
0x140023820  mov     rax, [rdi+28h]
0x140023824  mov     rcx, rdi
0x140023827  mov     r15d, [rax+1Ch]
0x14002382b  mov     ebp, [rax+18h]
0x14002382e  mov     ebx, [rax+0E8h]
0x140023834  and     byte ptr [rax+11h], 0FDh
0x140023838  call    cs:__imp_IsWindowDesktopComposed
0x14002383f  nop     dword ptr [rax+rax+00h]
0x140023844  test    eax, eax
0x140023846  jz      short loc_140023876
0x140023848  mov     rax, [rdi+28h]
0x14002384c  mov     ecx, [rax+18h]
0x14002384f  xor     ebp, ecx
0x140023851  mov     edx, [rax+0E8h]
0x140023857  xor     ebx, edx
0x140023859  mov     r14d, [rax+1Ch]
0x14002385d  xor     r15d, r14d
0x140023860  jnz     loc_140023BB1
0x140023866  test    ebp, ebp
0x140023868  jnz     loc_140023C12
0x14002386e  test    ebx, ebx
0x140023870  jnz     loc_140023BB1
0x140023876  mov     rcx, [rdi+28h]
0x14002387a  cmp     qword ptr [rcx+88h], 0
0x140023882  jnz     loc_1400239DB
0x140023888  test    byte ptr [rcx+11h], 10h
0x14002388c  jnz     loc_1400239DB
0x140023892  mov     r14d, [rcx+1Ch]
0x140023896  mov     esi, [rcx+18h]
0x140023899  mov     ebx, [rcx+0E8h]
0x14002389f  and     byte ptr [rcx+11h], 0EFh
0x1400238a3  mov     rcx, rdi
0x1400238a6  call    cs:__imp_IsWindowDesktopComposed
0x1400238ad  nop     dword ptr [rax+rax+00h]
0x1400238b2  test    eax, eax
0x1400238b4  jz      short loc_1400238E3
0x1400238b6  mov     rax, [rdi+28h]
0x1400238ba  mov     ecx, [rax+18h]
0x1400238bd  xor     esi, ecx
0x1400238bf  mov     edx, [rax+0E8h]
0x1400238c5  xor     ebx, edx
0x1400238c7  mov     ebp, [rax+1Ch]
0x1400238ca  xor     r14d, ebp
0x1400238cd  jnz     loc_140023AB6
0x1400238d3  test    esi, esi
0x1400238d5  jnz     loc_140023B14
0x1400238db  test    ebx, ebx
0x1400238dd  jnz     loc_140023AB6
0x1400238e3  mov     rax, [rdi+28h]
0x1400238e7  mov     rsi, [rax+88h]
0x1400238ee  mov     qword ptr [rax+88h], 0
0x1400238f9  mov     rax, [rdi+28h]
0x1400238fd  test    byte ptr [rax+14h], 2
0x140023901  jnz     loc_140023D2C
0x140023907  mov     r14, [rsp+78h+arg_8]
0x14002390f  mov     r8d, 10080h
0x140023915  mov     rdx, rsi
0x140023918  mov     rcx, rdi
0x14002391b  mov     qword ptr [r14+1Ch], 0
0x140023923  call    cs:__imp__GetDCEx
0x14002392a  nop     dword ptr [rax+rax+00h]
0x14002392f  xorps   xmm0, xmm0
0x140023932  lea     rbp, [r14+0Ch]
0x140023936  mov     rdx, rbp
0x140023939  mov     [r14], rax
0x14002393c  mov     rcx, rax
0x14002393f  mov     r8d, 1
0x140023945  movups  [rsp+78h+var_58], xmm0
0x14002394a  mov     rbx, rax
0x14002394d  call    cs:__imp_GreGetClipBox
0x140023954  nop     dword ptr [rax+rax+00h]
0x140023959  cmp     eax, 1
0x14002395c  jz      short loc_1400239AC
0x14002395e  mov     rdx, [rdi+88h]
0x140023965  mov     r8, [rdx+8]
0x140023969  cmp     byte ptr [r8+8], 0
0x14002396e  jl      short loc_140023985
0x140023970  test    r12d, r12d
0x140023973  jz      short loc_1400239AC
0x140023975  mov     r8, rsi
0x140023978  mov     rdx, rbx
0x14002397b  mov     rcx, rdi; struct tagWND *
0x14002397e  call    xxxSendEraseBkgnd
0x140023983  jmp     short loc_1400239AC
0x140023985  mov     r8d, 11h
0x14002398b  lea     rdx, [rsp+78h+var_58]
0x140023990  mov     rcx, rdi
0x140023993  call    GetRect
0x140023998  lea     r8, [rsp+78h+var_58]
0x14002399d  mov     rdx, rbp
0x1400239a0  mov     rcx, rbp
0x1400239a3  call    IntersectRect
0x1400239a8  test    eax, eax
0x1400239aa  jnz     short loc_140023970
0x1400239ac  mov     rcx, rdi; struct tagWND *
0x1400239af  call    ?xxxSendChildNCPaint@@YAXPEAUtagWND@@@Z; xxxSendChildNCPaint(tagWND *)
0x1400239b4  mov     rax, [rdi+28h]
0x1400239b8  movzx   ecx, byte ptr [rax+11h]
0x1400239bc  mov     rax, rbx
0x1400239bf  shr     ecx, 2
0x1400239c2  and     ecx, 1
0x1400239c5  mov     [r14+8], ecx
0x1400239c9  add     rsp, 38h
0x1400239cd  pop     r15
0x1400239cf  pop     r14
0x1400239d1  pop     r13
0x1400239d3  pop     r12
0x1400239d5  pop     rdi
0x1400239d6  pop     rsi
0x1400239d7  pop     rbp
0x1400239d8  pop     rbx
0x1400239d9  retn
0x1400239db  mov     rcx, rdi
0x1400239de  call    DecPaintCount
0x1400239e3  mov     rcx, [rdi+28h]
0x1400239e7  jmp     loc_140023892
0x1400239ec  mov     r8d, 120h
0x1400239f2  mov     r9d, 1
0x1400239f8  mov     rdx, rdi
0x1400239fb  xor     ecx, ecx
0x1400239fd  call    SetOrClrWF
0x140023a02  xor     edx, edx; int
0x140023a04  mov     rcx, rdi; struct tagWND *
0x140023a07  call    ?GetNCUpdateRgn@@YAPEAUHRGN__@@PEAUtagWND@@H@Z; GetNCUpdateRgn(tagWND *,int)
0x140023a0c  mov     rdx, rax; HRGN
0x140023a0f  mov     rcx, rdi; struct tagWND *
0x140023a12  mov     rbx, rax
0x140023a15  call    ?xxxSendNCPaint@@YAXPEAUtagWND@@PEAUHRGN__@@@Z; xxxSendNCPaint(tagWND *,HRGN__ *)
0x140023a1a  mov     rcx, rbx
0x140023a1d  call    cs:__imp_DeleteMaybeSpecialRgn
0x140023a24  nop     dword ptr [rax+rax+00h]
0x140023a29  mov     rax, [rdi+28h]
0x140023a2d  test    byte ptr [rax+11h], 20h
0x140023a31  jnz     short loc_1400239EC
0x140023a33  jmp     loc_14002378A
0x140023a38  test    r15d, 0B9CF0000h
0x140023a3f  jz      short loc_140023A99
0x140023a41  mov     esi, r13d
0x140023a44  mov     rcx, rdi; struct tagWND *
0x140023a47  call    DirtyVisRgnTrackers
0x140023a4c  mov     rbx, [rdi]
0x140023a4f  call    cs:__imp_ReferenceDwmApiPort
0x140023a56  nop     dword ptr [rax+rax+00h]
0x140023a5b  mov     r9d, r14d
0x140023a5e  mov     r8d, esi
0x140023a61  mov     rcx, rax; Object
0x140023a64  mov     rdx, rbx
0x140023a67  call    DwmAsyncChildStyleChange
0x140023a6c  test    r15d, 1C40000h
0x140023a73  setz    cl
0x140023a76  test    ebp, 200A0381h
0x140023a7c  setz    al
0x140023a7f  test    al, cl
0x140023a81  jnz     loc_14002371E
0x140023a87  mov     edx, 1
0x140023a8c  mov     rcx, rdi
0x140023a8f  call    ?CheckForChanges@WindowMargins@@YAXPEAUtagWND@@W4ChangeReason@1@@Z; WindowMargins::CheckForChanges(tagWND *,WindowMargins::ChangeReason)
0x140023a94  jmp     loc_14002371E
0x140023a99  test    ebp, 4E27A9h
0x140023a9f  jnz     loc_140023DDF
0x140023aa5  test    eax, 372C0h
0x140023aaa  jz      short loc_140023A6C
0x140023aac  mov     esi, 0F0000000h
0x140023ab1  mov     r14d, edx
0x140023ab4  jmp     short loc_140023A44
0x140023ab6  test    r14d, 0B9CF0000h
0x140023abd  jz      short loc_140023B14
0x140023abf  mov     rcx, rdi; struct tagWND *
0x140023ac2  call    DirtyVisRgnTrackers
  ... truncated ...
```
