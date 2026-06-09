# InternalInvalidate3

- ea: `0x1400916d4`
- end: `0x140091ee0`
- name: `InternalInvalidate3`
- size: `2060`
- prototype: `__int64 __fastcall(struct tagWND *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14003824c`
- `0x140090ac0`

## callees

- `0x14001af00`
- `0x14001b0e0`
- `0x14002479c`
- `0x140026790`
- `0x14008dabc`
- `0x1400916d4`
- `0x1400922c0`
- `0x1400e2cb0`
- `0x1400e491c`
- `0x1402e7a1c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14009182d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14009182d`
- `win32kbase!CreateEmptyRgnPublic` at `0x140091a23`
- `win32kbase!CreateEmptyRgnPublic` at `0x140091de5`
- `win32kbase!CreateEmptyRgnPublic` at `0x140091a23`
- `win32kbase!CreateEmptyRgnPublic` at `0x140091de5`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x140091a75`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x140091b21`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x140091a75`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x140091b21`
- `win32kbase!GreCombineRgn` at `0x14009193a`
- `win32kbase!GreCombineRgn` at `0x140091a56`
- `win32kbase!GreCombineRgn` at `0x140091af9`
- `win32kbase!GreCombineRgn` at `0x14009193a`
- `win32kbase!GreCombineRgn` at `0x140091a56`
- `win32kbase!GreCombineRgn` at `0x140091af9`
- `win32kbase!IsWindowDesktopComposed` at `0x140091779`
- `win32kbase!IsWindowDesktopComposed` at `0x1400917ed`
- `win32kbase!IsWindowDesktopComposed` at `0x14009186e`
- `win32kbase!IsWindowDesktopComposed` at `0x1400918cc`
- `win32kbase!IsWindowDesktopComposed` at `0x140091981`
- `win32kbase!IsWindowDesktopComposed` at `0x140091779`
- `win32kbase!IsWindowDesktopComposed` at `0x1400917ed`
- `win32kbase!IsWindowDesktopComposed` at `0x14009186e`
- `win32kbase!IsWindowDesktopComposed` at `0x1400918cc`
- `win32kbase!IsWindowDesktopComposed` at `0x140091981`
- `win32kbase!ReferenceDwmApiPort` at `0x140091bc0`
- `win32kbase!ReferenceDwmApiPort` at `0x140091c3e`
- `win32kbase!ReferenceDwmApiPort` at `0x140091cc1`
- `win32kbase!ReferenceDwmApiPort` at `0x140091d3f`
- `win32kbase!ReferenceDwmApiPort` at `0x140091bc0`
- `win32kbase!ReferenceDwmApiPort` at `0x140091c3e`
- `win32kbase!ReferenceDwmApiPort` at `0x140091cc1`
- `win32kbase!ReferenceDwmApiPort` at `0x140091d3f`
- `WIN32K!W32GetUserSessionState` at `0x140091b90`
- `WIN32K!W32GetUserSessionState` at `0x140091dbc`
- `WIN32K!W32GetUserSessionState` at `0x140091b90`
- `WIN32K!W32GetUserSessionState` at `0x140091dbc`

## pseudocode

```c
void __fastcall InternalInvalidate3(struct tagWND *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // esi
  __int64 v5; // r13
  int v7; // r14d
  __int64 v8; // rcx
  struct tagWND *v9; // rax
  __int64 v10; // rdx
  _BYTE *v11; // rcx
  BOOL v12; // ebx
  int v13; // eax
  int v14; // ebp
  int v15; // ebx
  _DWORD *v16; // rax
  int v17; // ebx
  int v18; // r12d
  int v19; // r13d
  __int64 v20; // rax
  int v21; // r12d
  int v22; // r14d
  int v23; // ebx
  __int64 v24; // rcx
  unsigned int *v25; // rax
  int v26; // r14d
  int v27; // ebx
  int v28; // r12d
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rax
  int v34; // r12d
  int v35; // r14d
  int v36; // ebx
  _DWORD *v37; // rax
  int v38; // r14d
  int v39; // ebx
  int v40; // r12d
  __int64 v41; // rax
  int v42; // r15d
  int v43; // ebp
  int v44; // ebx
  _DWORD *v45; // rax
  int v46; // ebp
  int v47; // ebx
  int v48; // r15d
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 UserSessionState; // rax
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  void *v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // r8
  void *v66; // rax
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // r8
  void *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // r8
  void *v74; // rax
  __int64 v75; // r8
  __int64 v76; // rdx
  struct tagTHREADINFO *v77; // rbx
  int v78; // [rsp+20h] [rbp-48h]
  __int64 v79; // [rsp+78h] [rbp+10h]
  BOOL v80; // [rsp+88h] [rbp+20h]

  v79 = a2;
  v4 = a3;
  v5 = a2;
  v7 = a3 & 1;
  if ( (a3 & 1) == 0 )
    goto LABEL_6;
  v8 = *((_QWORD *)a1 + 3);
  v9 = 0;
  if ( v8 )
  {
    a2 = *(_QWORD *)(v8 + 8);
    if ( a2 )
      v9 = *(struct tagWND **)(a2 + 24);
  }
  if ( a1 != v9 || !(unsigned int)IsWindowDesktopComposed(a1, a2, a3, a4) )
  {
LABEL_6:
    v10 = *((_QWORD *)a1 + 5);
    v11 = (_BYTE *)(v10 + 17);
    v12 = *(_QWORD *)(v10 + 136) || (*v11 & 0x10) != 0;
    v80 = v12;
    if ( (v4 & 0x407) != 0 )
    {
      if ( (v4 & 2) == 0
        || (v13 = *(_DWORD *)(v10 + 24),
            v14 = *(_DWORD *)(v10 + 28),
            v15 = *(_DWORD *)(v10 + 232),
            *v11 |= 0x10u,
            v78 = v13,
            !(unsigned int)IsWindowDesktopComposed(a1, v10, a3, a4)) )
      {
LABEL_15:
        if ( !v7 )
          goto LABEL_37;
        v20 = *((_QWORD *)a1 + 5);
        v21 = *(_DWORD *)(v20 + 28);
        v22 = *(_DWORD *)(v20 + 24);
        v23 = *(_DWORD *)(v20 + 232);
        *(_BYTE *)(v20 + 17) &= ~1u;
        if ( !(unsigned int)IsWindowDesktopComposed(a1, v10, a3, a4) )
        {
LABEL_20:
          CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread(v24);
          if ( CurrentThreadWin32Thread )
            CurrentThreadWin32Thread = (_QWORD *)*CurrentThreadWin32Thread;
          if ( *((_QWORD **)a1 + 2) != CurrentThreadWin32Thread )
          {
            SetOrClrWF(1, a1, 288, 1);
            if ( (*(_BYTE *)(*((_QWORD *)a1 + 5) + 20LL) & 1) != 0 )
            {
              SetOrClrWF(1, a1, 1026, 1);
              UserSessionState = W32GetUserSessionState(v57, v56);
              *(_DWORD *)(UserSessionState + 63180) |= v4;
            }
          }
          if ( (v4 & 4) == 0
            || (v33 = *((_QWORD *)a1 + 5),
                v34 = *(_DWORD *)(v33 + 28),
                v35 = *(_DWORD *)(v33 + 24),
                v36 = *(_DWORD *)(v33 + 232),
                *(_BYTE *)(v33 + 17) |= 2u,
                !(unsigned int)IsWindowDesktopComposed(a1, v30, v31, v32)) )
          {
LABEL_28:
            if ( (v4 & 0x400) == 0 )
              goto LABEL_33;
            v41 = *((_QWORD *)a1 + 5);
            v42 = *(_DWORD *)(v41 + 28);
            v43 = *(_DWORD *)(v41 + 24);
            v44 = *(_DWORD *)(v41 + 232);
            *(_BYTE *)(v41 + 17) |= 8u;
            if ( !(unsigned int)IsWindowDesktopComposed(a1, v30, v31, v32) )
              goto LABEL_33;
            v45 = (_DWORD *)*((_QWORD *)a1 + 5);
            v46 = v45[6] ^ v43;
            v47 = v45[58] ^ v44;
            v48 = v45[7] ^ v42;
            if ( !v48 )
            {
              if ( v46 )
              {
LABEL_98:
                if ( (v46 & 0x4E27A9) == 0 && (v47 & 0x372C0) == 0 )
                {
LABEL_96:
                  if ( (v46 & 0x200A0381) != 0 || (v48 & 0x1C40000) != 0 )
                    WindowMargins::CheckForChanges(a1, 1);
LABEL_33:
                  v49 = *((_QWORD *)a1 + 5);
                  v50 = *(_QWORD *)(v49 + 136);
                  if ( v50 != 1 )
                  {
                    if ( v5 == 1 )
                      goto LABEL_59;
                    if ( v50 )
                    {
                      if ( (unsigned int)GreCombineRgn(v50, *(_QWORD *)(v49 + 136), v5, 2) )
                        goto LABEL_37;
LABEL_59:
                      DeleteMaybeSpecialRgn(*(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL));
                      *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL) = 1;
                      goto LABEL_37;
                    }
                    *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL) = CreateEmptyRgnPublic();
                    v53 = *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL);
                    if ( !v53 || !(unsigned int)GreCombineRgn(v53, v5, 0, 5) )
                      goto LABEL_59;
                  }
LABEL_37:
                  if ( !v80 )
                  {
                    v51 = *((_QWORD *)a1 + 5);
                    if ( *(_QWORD *)(v51 + 136) || (*(_BYTE *)(v51 + 17) & 0x10) != 0 )
                    {
                      if ( (v4 & 0x20000) == 0
                        || (v77 = (struct tagTHREADINFO *)*((_QWORD *)a1 + 2), v77 == PtiCurrent()) )
                      {
                        IncPaintCount(a1);
                      }
                      else
                      {
                        IncPaintCountInterMoveSize(a1);
                      }
                    }
                  }
                  return;
                }
LABEL_95:
                DirtyVisRgnTrackers(a1);
                v74 = (void *)ReferenceDwmApiPort(v72, v71, v73);
                DwmAsyncChildStyleChange(v74);
                goto LABEL_96;
              }
              if ( !v47 )
                goto LABEL_33;
            }
            if ( (v48 & 0xB9CF0000) != 0 )
              goto LABEL_95;
            goto LABEL_98;
          }
          v37 = (_DWORD *)*((_QWORD *)a1 + 5);
          v38 = v37[6] ^ v35;
          v30 = (unsigned int)v37[58];
          v39 = v30 ^ v36;
          v40 = v37[7] ^ v34;
          if ( !v40 )
          {
            if ( v38 )
            {
LABEL_91:
              if ( (v38 & 0x4E27A9) == 0 && (v39 & 0x372C0) == 0 )
              {
LABEL_89:
                if ( (v38 & 0x200A0381) != 0 || (v40 & 0x1C40000) != 0 )
                  WindowMargins::CheckForChanges(a1, 1);
                goto LABEL_28;
              }
LABEL_88:
              DirtyVisRgnTrackers(a1);
              v70 = (void *)ReferenceDwmApiPort(v68, v67, v69);
              DwmAsyncChildStyleChange(v70);
              goto LABEL_89;
            }
            if ( !v39 )
              goto LABEL_28;
          }
          if ( (v40 & 0xB9CF0000) != 0 )
            goto LABEL_88;
          goto LABEL_91;
        }
        v25 = (unsigned int *)*((_QWORD *)a1 + 5);
        v24 = v25[6];
        v26 = v24 ^ v22;
        v27 = v25[58] ^ v23;
        v28 = v25[7] ^ v21;
        if ( !v28 )
        {
          if ( v26 )
          {
LABEL_84:
            if ( (v26 & 0x4E27A9) == 0 && (v27 & 0x372C0) == 0 )
            {
LABEL_82:
              LOBYTE(v24) = (v26 & 0x200A0381) == 0;
              if ( ((unsigned __int8)v24 & ((v28 & 0x1C40000) == 0)) == 0 )
                WindowMargins::CheckForChanges(a1, 1);
              goto LABEL_20;
            }
LABEL_81:
            DirtyVisRgnTrackers(a1);
            v66 = (void *)ReferenceDwmApiPort(v64, v63, v65);
            DwmAsyncChildStyleChange(v66);
            goto LABEL_82;
          }
          if ( !v27 )
            goto LABEL_20;
        }
        if ( (v28 & 0xB9CF0000) != 0 )
          goto LABEL_81;
        goto LABEL_84;
      }
      v16 = (_DWORD *)*((_QWORD *)a1 + 5);
      v10 = (unsigned int)v16[58];
      v17 = v10 ^ v15;
      v18 = v78 ^ v16[6];
      v19 = v14 ^ v16[7];
      if ( !v19 )
      {
        if ( v18 )
        {
LABEL_77:
          if ( (v18 & 0x4E27A9) == 0 && (v17 & 0x372C0) == 0 )
          {
LABEL_75:
            if ( (v18 & 0x200A0381) != 0 || (v19 & 0x1C40000) != 0 )
              WindowMargins::CheckForChanges(a1, 1);
            goto LABEL_14;
          }
LABEL_74:
          DirtyVisRgnTrackers(a1);
          v62 = (void *)ReferenceDwmApiPort(v60, v59, v61);
          DwmAsyncChildStyleChange(v62);
          goto LABEL_75;
        }
        if ( !v17 )
        {
LABEL_14:
          v5 = v79;
          goto LABEL_15;
        }
      }
      if ( (v19 & 0xB9CF0000) != 0 )
        goto LABEL_74;
      goto LABEL_77;
    }
    if ( (v4 & 0x838) == 0 )
      return;
    LOBYTE(v11) = ((v4 & 0x8000) == 0) & (*v11 >> 5);
    if ( ((unsigned __int8)v11 & 1) != 0 )
      return;
    if ( (v4 & 0x10) != 0 )
      SetOrClrWF(0, a1, 272, 1);
    if ( (v4 & 8) == 0 )
      goto LABEL_53;
    if ( (v4 & 0x20) != 0 )
      SetOrClrWF(0, a1, 258, 1);
    if ( (v4 & 0x800) != 0 )
      SetOrClrWF(0, a1, 264, 1);
    v54 = *((_QWORD *)a1 + 5);
    if ( !*(_QWORD *)(v54 + 136) )
      goto LABEL_53;
    if ( (*(_BYTE *)(v54 + 17) & 8) != 0 )
    {
      if ( v5 != 1 )
        goto LABEL_67;
      v5 = *(_QWORD *)(W32GetUserSessionState(v11, v10) + 63136);
      CalcWindowRgn(a1, v5, 1);
    }
    if ( v5 == 1 )
    {
LABEL_70:
      DeleteMaybeSpecialRgn(*(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL));
      *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL) = 0;
      SetOrClrWF(0, a1, 258, 1);
LABEL_53:
      if ( v12 )
      {
        v52 = *((_QWORD *)a1 + 5);
        if ( !*(_QWORD *)(v52 + 136) && (*(_BYTE *)(v52 + 17) & 0x10) == 0 )
          DecPaintCount(a1);
      }
      return;
    }
LABEL_67:
    if ( *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL) == 1 )
    {
      *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL) = CreateEmptyRgnPublic();
      v75 = *((_QWORD *)a1 + 5);
      v76 = *(_QWORD *)(v75 + 136);
      if ( !v76 )
        goto LABEL_59;
      LOBYTE(v75) = ~*(_BYTE *)(v75 + 17);
      if ( !(unsigned int)CalcWindowRgn(a1, v76, ((unsigned int)v75 >> 3) & 1) )
        goto LABEL_59;
    }
    v55 = GreCombineRgn(*(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL), *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL), v5, 4);
    if ( !v55 )
      goto LABEL_59;
    if ( v55 != 1 )
      goto LABEL_53;
    goto LABEL_70;
  }
}

```

## disassembly

```asm
0x1400916d4  mov     [rsp+arg_0], rbx
0x1400916d9  mov     [rsp+arg_8], rdx
0x1400916de  push    rbp
0x1400916df  push    rsi
0x1400916e0  push    rdi
0x1400916e1  push    r12
0x1400916e3  push    r13
0x1400916e5  push    r14
0x1400916e7  push    r15
0x1400916e9  sub     rsp, 30h
0x1400916ed  mov     r14d, r8d
0x1400916f0  mov     esi, r8d
0x1400916f3  mov     r13, rdx
0x1400916f6  mov     rdi, rcx
0x1400916f9  and     r14d, 1
0x1400916fd  jz      short loc_140091720
0x1400916ff  mov     rcx, [rcx+18h]
0x140091703  xor     eax, eax
0x140091705  test    rcx, rcx
0x140091708  jz      short loc_140091717
0x14009170a  mov     rdx, [rcx+8]
0x14009170e  test    rdx, rdx
0x140091711  jz      short loc_140091717
0x140091713  mov     rax, [rdx+18h]
0x140091717  cmp     rdi, rax
0x14009171a  jz      loc_14009197E
0x140091720  mov     rdx, [rdi+28h]
0x140091724  mov     r15b, 10h
0x140091727  cmp     qword ptr [rdx+88h], 0
0x14009172f  lea     rcx, [rdx+11h]
0x140091733  jz      loc_14009196E
0x140091739  mov     ebx, 1
0x14009173e  mov     [rsp+68h+arg_18], ebx
0x140091745  test    esi, 407h
0x14009174b  jz      loc_1400919C0
0x140091751  mov     ebp, 0FFFFFFF0h
0x140091756  mov     [rsp+68h+arg_10], ebp
0x14009175d  test    sil, 2
0x140091761  jz      short loc_1400917CB
0x140091763  mov     eax, [rdx+18h]
0x140091766  mov     ebp, [rdx+1Ch]
0x140091769  mov     ebx, [rdx+0E8h]
0x14009176f  or      [rcx], r15b
0x140091772  mov     rcx, rdi
0x140091775  mov     [rsp+68h+var_48], eax
0x140091779  call    cs:__imp_IsWindowDesktopComposed
0x140091780  nop     dword ptr [rax+rax+00h]
0x140091785  test    eax, eax
0x140091787  jz      short loc_1400917C6
0x140091789  mov     rax, [rdi+28h]
0x14009178d  mov     ecx, [rax+18h]
0x140091790  mov     r12d, ecx
0x140091793  mov     r15d, [rax+1Ch]
0x140091797  mov     r13d, r15d
0x14009179a  mov     edx, [rax+0E8h]
0x1400917a0  xor     ebx, edx
0x1400917a2  xor     r12d, [rsp+68h+var_48]
0x1400917a7  xor     r13d, ebp
0x1400917aa  jnz     loc_140091BA7
0x1400917b0  test    r12d, r12d
0x1400917b3  jnz     loc_140091C0B
0x1400917b9  test    ebx, ebx
0x1400917bb  jnz     loc_140091BA7
0x1400917c1  mov     r13, [rsp+68h+arg_8]
0x1400917c6  mov     ebp, 0FFFFFFF0h
0x1400917cb  test    r14d, r14d
0x1400917ce  jz      loc_14009194E
0x1400917d4  mov     rax, [rdi+28h]
0x1400917d8  mov     rcx, rdi
0x1400917db  mov     r12d, [rax+1Ch]
0x1400917df  mov     r14d, [rax+18h]
0x1400917e3  mov     ebx, [rax+0E8h]
0x1400917e9  and     byte ptr [rax+11h], 0FEh
0x1400917ed  call    cs:__imp_IsWindowDesktopComposed
0x1400917f4  nop     dword ptr [rax+rax+00h]
0x1400917f9  test    eax, eax
0x1400917fb  jz      short loc_14009182D
0x1400917fd  mov     rax, [rdi+28h]
0x140091801  mov     ecx, [rax+18h]
0x140091804  xor     r14d, ecx
0x140091807  mov     edx, [rax+0E8h]
0x14009180d  xor     ebx, edx
0x14009180f  mov     r15d, [rax+1Ch]
0x140091813  xor     r12d, r15d
0x140091816  jnz     loc_140091C2A
0x14009181c  test    r14d, r14d
0x14009181f  jnz     loc_140091C89
0x140091825  test    ebx, ebx
0x140091827  jnz     loc_140091C2A
0x14009182d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140091834  nop     dword ptr [rax+rax+00h]
0x140091839  test    rax, rax
0x14009183c  jz      loc_140091E6E
0x140091842  mov     rax, [rax]
0x140091845  cmp     [rdi+10h], rax
0x140091849  jnz     loc_140091B54
0x14009184f  test    sil, 4
0x140091853  jz      short loc_1400918AE
0x140091855  mov     rax, [rdi+28h]
0x140091859  mov     rcx, rdi
0x14009185c  mov     r12d, [rax+1Ch]
0x140091860  mov     r14d, [rax+18h]
0x140091864  mov     ebx, [rax+0E8h]
0x14009186a  or      byte ptr [rax+11h], 2
0x14009186e  call    cs:__imp_IsWindowDesktopComposed
0x140091875  nop     dword ptr [rax+rax+00h]
0x14009187a  test    eax, eax
0x14009187c  jz      short loc_1400918AE
0x14009187e  mov     rax, [rdi+28h]
0x140091882  mov     ecx, [rax+18h]
0x140091885  xor     r14d, ecx
0x140091888  mov     edx, [rax+0E8h]
0x14009188e  xor     ebx, edx
0x140091890  mov     r15d, [rax+1Ch]
0x140091894  xor     r12d, r15d
0x140091897  jnz     loc_140091CA8
0x14009189d  test    r14d, r14d
0x1400918a0  jnz     loc_140091D0C
0x1400918a6  test    ebx, ebx
0x1400918a8  jnz     loc_140091CA8
0x1400918ae  bt      esi, 0Ah
0x1400918b2  jnb     short loc_14009190A
0x1400918b4  mov     rax, [rdi+28h]
0x1400918b8  mov     rcx, rdi
0x1400918bb  mov     r15d, [rax+1Ch]
0x1400918bf  mov     ebp, [rax+18h]
0x1400918c2  mov     ebx, [rax+0E8h]
0x1400918c8  or      byte ptr [rax+11h], 8
0x1400918cc  call    cs:__imp_IsWindowDesktopComposed
0x1400918d3  nop     dword ptr [rax+rax+00h]
0x1400918d8  test    eax, eax
0x1400918da  jz      short loc_14009190A
0x1400918dc  mov     rax, [rdi+28h]
0x1400918e0  mov     ecx, [rax+18h]
0x1400918e3  xor     ebp, ecx
0x1400918e5  mov     edx, [rax+0E8h]
0x1400918eb  xor     ebx, edx
0x1400918ed  mov     r14d, [rax+1Ch]
0x1400918f1  xor     r15d, r14d
0x1400918f4  jnz     loc_140091D2B
0x1400918fa  test    ebp, ebp
0x1400918fc  jnz     loc_140091D8E
0x140091902  test    ebx, ebx
0x140091904  jnz     loc_140091D2B
0x14009190a  mov     rax, [rdi+28h]
0x14009190e  mov     rcx, [rax+88h]
0x140091915  cmp     rcx, 1
0x140091919  jz      short loc_14009194E
0x14009191b  cmp     r13, 1
0x14009191f  jz      loc_140091A6A
0x140091925  test    rcx, rcx
0x140091928  jz      loc_140091A23
0x14009192e  mov     r9d, 2
0x140091934  mov     r8, r13
0x140091937  mov     rdx, rcx
0x14009193a  call    cs:__imp_GreCombineRgn
0x140091941  nop     dword ptr [rax+rax+00h]
0x140091946  test    eax, eax
0x140091948  jz      loc_140091A6A
0x14009194e  cmp     [rsp+68h+arg_18], 0
0x140091956  jz      short loc_140091996
0x140091958  mov     rbx, [rsp+68h+arg_0]
0x14009195d  add     rsp, 30h
0x140091961  pop     r15
0x140091963  pop     r14
0x140091965  pop     r13
0x140091967  pop     r12
0x140091969  pop     rdi
0x14009196a  pop     rsi
0x14009196b  pop     rbp
0x14009196c  retn
0x14009196e  test    [rcx], r15b
0x140091971  jnz     loc_140091739
0x140091977  xor     ebx, ebx
0x140091979  jmp     loc_14009173E
0x14009197e  mov     rcx, rdi
0x140091981  call    cs:__imp_IsWindowDesktopComposed
0x140091988  nop     dword ptr [rax+rax+00h]
0x14009198d  test    eax, eax
0x14009198f  jnz     short loc_140091958
0x140091991  jmp     loc_140091720
0x140091996  mov     rax, [rdi+28h]
0x14009199a  cmp     qword ptr [rax+88h], 0
0x1400919a2  jz      short loc_1400919B8
0x1400919a4  bt      esi, 11h
0x1400919a8  jb      loc_140091EC1
0x1400919ae  mov     rcx, rdi
0x1400919b1  call    IncPaintCount
0x1400919b6  jmp     short loc_140091958
0x1400919b8  test    byte ptr [rax+11h], 10h
0x1400919bc  jnz     short loc_1400919A4
0x1400919be  jmp     short loc_140091958
0x1400919c0  test    esi, 838h
0x1400919c6  jz      short loc_140091958
0x1400919c8  mov     cl, [rcx]
0x1400919ca  shr     cl, 5
0x1400919cd  bt      esi, 0Fh
0x1400919d1  setnb   al
0x1400919d4  and     cl, al
0x1400919d6  test    cl, 1
0x1400919d9  jnz     loc_140091958
0x1400919df  test    r15b, sil
0x1400919e2  jnz     loc_140091E73
0x1400919e8  test    sil, 8
0x1400919ec  jnz     loc_140091A95
0x1400919f2  test    ebx, ebx
0x1400919f4  jz      loc_140091958
0x1400919fa  mov     rax, [rdi+28h]
0x1400919fe  cmp     qword ptr [rax+88h], 0
0x140091a06  jnz     loc_140091958
0x140091a0c  test    [rax+11h], r15b
0x140091a10  jnz     loc_140091958
0x140091a16  mov     rcx, rdi
0x140091a19  call    DecPaintCount
0x140091a1e  jmp     loc_140091958
0x140091a23  call    cs:__imp_CreateEmptyRgnPublic
0x140091a2a  nop     dword ptr [rax+rax+00h]
0x140091a2f  mov     rcx, [rdi+28h]
0x140091a33  mov     [rcx+88h], rax
0x140091a3a  mov     rax, [rdi+28h]
0x140091a3e  mov     rcx, [rax+88h]
0x140091a45  test    rcx, rcx
0x140091a48  jz      short loc_140091A6A
0x140091a4a  mov     r9d, 5
0x140091a50  xor     r8d, r8d
0x140091a53  mov     rdx, r13
0x140091a56  call    cs:__imp_GreCombineRgn
0x140091a5d  nop     dword ptr [rax+rax+00h]
0x140091a62  test    eax, eax
0x140091a64  jnz     loc_14009194E
0x140091a6a  mov     rcx, [rdi+28h]
0x140091a6e  mov     rcx, [rcx+88h]
0x140091a75  call    cs:__imp_DeleteMaybeSpecialRgn
0x140091a7c  nop     dword ptr [rax+rax+00h]
0x140091a81  mov     rax, [rdi+28h]
0x140091a85  mov     qword ptr [rax+88h], 1
0x140091a90  jmp     loc_14009194E
0x140091a95  mov     ebp, 102h
0x140091a9a  test    sil, 20h
0x140091a9e  jnz     loc_140091E8E
0x140091aa4  bt      esi, 0Bh
0x140091aa8  jb      loc_140091EA6
0x140091aae  mov     rax, [rdi+28h]
0x140091ab2  cmp     qword ptr [rax+88h], 0
0x140091aba  jz      loc_1400919F2
0x140091ac0  test    byte ptr [rax+11h], 8
0x140091ac4  jnz     loc_140091DB2
0x140091aca  cmp     r13, 1
0x140091ace  jz      short loc_140091B16
0x140091ad0  mov     rax, [rdi+28h]
0x140091ad4  cmp     qword ptr [rax+88h], 1
0x140091adc  jz      loc_140091DE5
0x140091ae2  mov     rax, [rdi+28h]
0x140091ae6  mov     r9d, 4
0x140091aec  mov     r8, r13
0x140091aef  mov     rcx, [rax+88h]
0x140091af6  mov     rdx, rcx
0x140091af9  call    cs:__imp_GreCombineRgn
0x140091b00  nop     dword ptr [rax+rax+00h]
0x140091b05  test    eax, eax
0x140091b07  jz      loc_140091A6A
0x140091b0d  cmp     eax, 1
0x140091b10  jnz     loc_1400919F2
0x140091b16  mov     rcx, [rdi+28h]
0x140091b1a  mov     rcx, [rcx+88h]
0x140091b21  call    cs:__imp_DeleteMaybeSpecialRgn
0x140091b28  nop     dword ptr [rax+rax+00h]
0x140091b2d  mov     rax, [rdi+28h]
0x140091b31  mov     r8d, ebp
0x140091b34  mov     r9d, 1
0x140091b3a  mov     rdx, rdi
0x140091b3d  xor     ecx, ecx
0x140091b3f  mov     qword ptr [rax+88h], 0
0x140091b4a  call    SetOrClrWF
0x140091b4f  jmp     loc_1400919F2
0x140091b54  mov     r9d, 1
0x140091b5a  mov     r8d, 120h
0x140091b60  mov     ecx, r9d
0x140091b63  mov     rdx, rdi
0x140091b66  call    SetOrClrWF
0x140091b6b  mov     rax, [rdi+28h]
0x140091b6f  test    byte ptr [rax+14h], 1
0x140091b73  jz      loc_14009184F
0x140091b79  mov     r9d, 1
0x140091b7f  mov     r8d, 402h
0x140091b85  mov     ecx, r9d
0x140091b88  mov     rdx, rdi
0x140091b8b  call    SetOrClrWF
0x140091b90  call    cs:__imp_W32GetUserSessionState
0x140091b97  nop     dword ptr [rax+rax+00h]
0x140091b9c  or      [rax+0F6CCh], esi
0x140091ba2  jmp     loc_14009184F
0x140091ba7  test    r13d, 0B9CF0000h
0x140091bae  jz      short loc_140091C0B
0x140091bb0  mov     ebp, 0FFFFFFF0h
0x140091bb5  mov     rcx, rdi; struct tagWND *
0x140091bb8  call    DirtyVisRgnTrackers
0x140091bbd  mov     rbx, [rdi]
0x140091bc0  call    cs:__imp_ReferenceDwmApiPort
0x140091bc7  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
