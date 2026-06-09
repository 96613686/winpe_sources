# InternalInvalidate3

- ea: `0x140019554`
- end: `0x140019d60`
- name: `InternalInvalidate3`
- size: `2060`
- prototype: `__int64 __fastcall(struct tagWND *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140018940`
- `0x1400d62b4`

## callees

- `0x14001593c`
- `0x140019554`
- `0x14001a140`
- `0x1400209c0`
- `0x140020ba0`
- `0x14002988c`
- `0x14002b844`
- `0x1400bcaa0`
- `0x1400be70c`
- `0x1402e5b5c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400196ad`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400196ad`
- `win32kbase!CreateEmptyRgnPublic` at `0x1400198a3`
- `win32kbase!CreateEmptyRgnPublic` at `0x140019c65`
- `win32kbase!CreateEmptyRgnPublic` at `0x1400198a3`
- `win32kbase!CreateEmptyRgnPublic` at `0x140019c65`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x1400198f5`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x1400199a1`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x1400198f5`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x1400199a1`
- `win32kbase!GreCombineRgn` at `0x1400197ba`
- `win32kbase!GreCombineRgn` at `0x1400198d6`
- `win32kbase!GreCombineRgn` at `0x140019979`
- `win32kbase!GreCombineRgn` at `0x1400197ba`
- `win32kbase!GreCombineRgn` at `0x1400198d6`
- `win32kbase!GreCombineRgn` at `0x140019979`
- `win32kbase!IsWindowDesktopComposed` at `0x1400195f9`
- `win32kbase!IsWindowDesktopComposed` at `0x14001966d`
- `win32kbase!IsWindowDesktopComposed` at `0x1400196ee`
- `win32kbase!IsWindowDesktopComposed` at `0x14001974c`
- `win32kbase!IsWindowDesktopComposed` at `0x140019801`
- `win32kbase!IsWindowDesktopComposed` at `0x1400195f9`
- `win32kbase!IsWindowDesktopComposed` at `0x14001966d`
- `win32kbase!IsWindowDesktopComposed` at `0x1400196ee`
- `win32kbase!IsWindowDesktopComposed` at `0x14001974c`
- `win32kbase!IsWindowDesktopComposed` at `0x140019801`
- `win32kbase!ReferenceDwmApiPort` at `0x140019a40`
- `win32kbase!ReferenceDwmApiPort` at `0x140019abe`
- `win32kbase!ReferenceDwmApiPort` at `0x140019b41`
- `win32kbase!ReferenceDwmApiPort` at `0x140019bbf`
- `win32kbase!ReferenceDwmApiPort` at `0x140019a40`
- `win32kbase!ReferenceDwmApiPort` at `0x140019abe`
- `win32kbase!ReferenceDwmApiPort` at `0x140019b41`
- `win32kbase!ReferenceDwmApiPort` at `0x140019bbf`
- `WIN32K!W32GetUserSessionState` at `0x140019a10`
- `WIN32K!W32GetUserSessionState` at `0x140019c3c`
- `WIN32K!W32GetUserSessionState` at `0x140019a10`
- `WIN32K!W32GetUserSessionState` at `0x140019c3c`

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
  __int64 v11; // rdx
  _BYTE *v12; // rcx
  BOOL v13; // ebx
  int v14; // eax
  int v15; // ebp
  int v16; // ebx
  _DWORD *v17; // rax
  int v18; // ebx
  int v19; // r12d
  int v20; // r13d
  __int64 v21; // rax
  int v22; // r12d
  int v23; // r14d
  int v24; // ebx
  __int64 v25; // rcx
  unsigned int *v26; // rax
  int v27; // r14d
  int v28; // ebx
  int v29; // r12d
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v31; // rax
  int v32; // r12d
  int v33; // r14d
  int v34; // ebx
  _DWORD *v35; // rax
  int v36; // r14d
  int v37; // ebx
  int v38; // r12d
  __int64 v39; // rax
  int v40; // r15d
  int v41; // ebp
  int v42; // ebx
  _DWORD *v43; // rax
  int v44; // ebp
  int v45; // ebx
  int v46; // r15d
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  int v53; // eax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  __int64 v57; // r9
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
  BOOL v80; // [rsp+88h] [rbp+20h]

  v4 = a3;
  v5 = a2;
  v7 = a3 & 1;
  if ( (a3 & 1) == 0 )
    goto LABEL_6;
  v8 = *((_QWORD *)a1 + 3);
  v9 = 0;
  if ( v8 )
  {
    v10 = *(_QWORD *)(v8 + 8);
    if ( v10 )
      v9 = *(struct tagWND **)(v10 + 24);
  }
  if ( a1 != v9 || !(unsigned int)IsWindowDesktopComposed(a1) )
  {
LABEL_6:
    v11 = *((_QWORD *)a1 + 5);
    v12 = (_BYTE *)(v11 + 17);
    v13 = *(_QWORD *)(v11 + 136) || (*v12 & 0x10) != 0;
    v80 = v13;
    if ( (v4 & 0x407) != 0 )
    {
      if ( (v4 & 2) == 0
        || (v14 = *(_DWORD *)(v11 + 24),
            v15 = *(_DWORD *)(v11 + 28),
            v16 = *(_DWORD *)(v11 + 232),
            *v12 |= 0x10u,
            v78 = v14,
            !(unsigned int)IsWindowDesktopComposed(a1)) )
      {
LABEL_15:
        if ( !v7 )
          goto LABEL_37;
        v21 = *((_QWORD *)a1 + 5);
        v22 = *(_DWORD *)(v21 + 28);
        v23 = *(_DWORD *)(v21 + 24);
        v24 = *(_DWORD *)(v21 + 232);
        *(_BYTE *)(v21 + 17) &= ~1u;
        if ( !(unsigned int)IsWindowDesktopComposed(a1) )
        {
LABEL_20:
          CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread(v25);
          if ( CurrentThreadWin32Thread )
            CurrentThreadWin32Thread = (_QWORD *)*CurrentThreadWin32Thread;
          if ( *((_QWORD **)a1 + 2) != CurrentThreadWin32Thread )
          {
            SetOrClrWF(1, a1, 288, 1);
            if ( (*(_BYTE *)(*((_QWORD *)a1 + 5) + 20LL) & 1) != 0 )
            {
              SetOrClrWF(1, a1, 1026, 1);
              UserSessionState = W32GetUserSessionState(v55, v54, v56, v57);
              *(_DWORD *)(UserSessionState + 63180) |= v4;
            }
          }
          if ( (v4 & 4) == 0
            || (v31 = *((_QWORD *)a1 + 5),
                v32 = *(_DWORD *)(v31 + 28),
                v33 = *(_DWORD *)(v31 + 24),
                v34 = *(_DWORD *)(v31 + 232),
                *(_BYTE *)(v31 + 17) |= 2u,
                !(unsigned int)IsWindowDesktopComposed(a1)) )
          {
LABEL_28:
            if ( (v4 & 0x400) == 0 )
              goto LABEL_33;
            v39 = *((_QWORD *)a1 + 5);
            v40 = *(_DWORD *)(v39 + 28);
            v41 = *(_DWORD *)(v39 + 24);
            v42 = *(_DWORD *)(v39 + 232);
            *(_BYTE *)(v39 + 17) |= 8u;
            if ( !(unsigned int)IsWindowDesktopComposed(a1) )
              goto LABEL_33;
            v43 = (_DWORD *)*((_QWORD *)a1 + 5);
            v44 = v43[6] ^ v41;
            v45 = v43[58] ^ v42;
            v46 = v43[7] ^ v40;
            if ( !v46 )
            {
              if ( v44 )
              {
LABEL_98:
                if ( (v44 & 0x4E27A9) == 0 && (v45 & 0x372C0) == 0 )
                {
LABEL_96:
                  if ( (v44 & 0x200A0381) != 0 || (v46 & 0x1C40000) != 0 )
                    WindowMargins::CheckForChanges(a1, 1);
LABEL_33:
                  v47 = *((_QWORD *)a1 + 5);
                  v48 = *(_QWORD *)(v47 + 136);
                  if ( v48 != 1 )
                  {
                    if ( v5 == 1 )
                      goto LABEL_59;
                    if ( v48 )
                    {
                      if ( (unsigned int)GreCombineRgn(v48, *(_QWORD *)(v47 + 136), v5, 2) )
                        goto LABEL_37;
LABEL_59:
                      DeleteMaybeSpecialRgn(*(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL));
                      *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL) = 1;
                      goto LABEL_37;
                    }
                    *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL) = CreateEmptyRgnPublic();
                    v51 = *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL);
                    if ( !v51 || !(unsigned int)GreCombineRgn(v51, v5, 0, 5) )
                      goto LABEL_59;
                  }
LABEL_37:
                  if ( !v80 )
                  {
                    v49 = *((_QWORD *)a1 + 5);
                    if ( *(_QWORD *)(v49 + 136) || (*(_BYTE *)(v49 + 17) & 0x10) != 0 )
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
              if ( !v45 )
                goto LABEL_33;
            }
            if ( (v46 & 0xB9CF0000) != 0 )
              goto LABEL_95;
            goto LABEL_98;
          }
          v35 = (_DWORD *)*((_QWORD *)a1 + 5);
          v36 = v35[6] ^ v33;
          v37 = v35[58] ^ v34;
          v38 = v35[7] ^ v32;
          if ( !v38 )
          {
            if ( v36 )
            {
LABEL_91:
              if ( (v36 & 0x4E27A9) == 0 && (v37 & 0x372C0) == 0 )
              {
LABEL_89:
                if ( (v36 & 0x200A0381) != 0 || (v38 & 0x1C40000) != 0 )
                  WindowMargins::CheckForChanges(a1, 1);
                goto LABEL_28;
              }
LABEL_88:
              DirtyVisRgnTrackers(a1);
              v70 = (void *)ReferenceDwmApiPort(v68, v67, v69);
              DwmAsyncChildStyleChange(v70);
              goto LABEL_89;
            }
            if ( !v37 )
              goto LABEL_28;
          }
          if ( (v38 & 0xB9CF0000) != 0 )
            goto LABEL_88;
          goto LABEL_91;
        }
        v26 = (unsigned int *)*((_QWORD *)a1 + 5);
        v25 = v26[6];
        v27 = v25 ^ v23;
        v28 = v26[58] ^ v24;
        v29 = v26[7] ^ v22;
        if ( !v29 )
        {
          if ( v27 )
          {
LABEL_84:
            if ( (v27 & 0x4E27A9) == 0 && (v28 & 0x372C0) == 0 )
            {
LABEL_82:
              LOBYTE(v25) = (v27 & 0x200A0381) == 0;
              if ( ((unsigned __int8)v25 & ((v29 & 0x1C40000) == 0)) == 0 )
                WindowMargins::CheckForChanges(a1, 1);
              goto LABEL_20;
            }
LABEL_81:
            DirtyVisRgnTrackers(a1);
            v66 = (void *)ReferenceDwmApiPort(v64, v63, v65);
            DwmAsyncChildStyleChange(v66);
            goto LABEL_82;
          }
          if ( !v28 )
            goto LABEL_20;
        }
        if ( (v29 & 0xB9CF0000) != 0 )
          goto LABEL_81;
        goto LABEL_84;
      }
      v17 = (_DWORD *)*((_QWORD *)a1 + 5);
      v18 = v17[58] ^ v16;
      v19 = v78 ^ v17[6];
      v20 = v15 ^ v17[7];
      if ( !v20 )
      {
        if ( v19 )
        {
LABEL_77:
          if ( (v19 & 0x4E27A9) == 0 && (v18 & 0x372C0) == 0 )
          {
LABEL_75:
            if ( (v19 & 0x200A0381) != 0 || (v20 & 0x1C40000) != 0 )
              WindowMargins::CheckForChanges(a1, 1);
            goto LABEL_14;
          }
LABEL_74:
          DirtyVisRgnTrackers(a1);
          v62 = (void *)ReferenceDwmApiPort(v60, v59, v61);
          DwmAsyncChildStyleChange(v62);
          goto LABEL_75;
        }
        if ( !v18 )
        {
LABEL_14:
          v5 = a2;
          goto LABEL_15;
        }
      }
      if ( (v20 & 0xB9CF0000) != 0 )
        goto LABEL_74;
      goto LABEL_77;
    }
    if ( (v4 & 0x838) == 0 )
      return;
    LOBYTE(v12) = ((v4 & 0x8000) == 0) & (*v12 >> 5);
    if ( ((unsigned __int8)v12 & 1) != 0 )
      return;
    if ( (v4 & 0x10) != 0 )
      SetOrClrWF(0, a1, 272, 1);
    if ( (v4 & 8) == 0 )
      goto LABEL_53;
    if ( (v4 & 0x20) != 0 )
      SetOrClrWF(0, a1, 258, 1);
    if ( (v4 & 0x800) != 0 )
      SetOrClrWF(0, a1, 264, 1);
    v52 = *((_QWORD *)a1 + 5);
    if ( !*(_QWORD *)(v52 + 136) )
      goto LABEL_53;
    if ( (*(_BYTE *)(v52 + 17) & 8) != 0 )
    {
      if ( v5 != 1 )
        goto LABEL_67;
      v5 = *(_QWORD *)(W32GetUserSessionState(v12, v11, a3, a4) + 63136);
      CalcWindowRgn(a1, v5, 1);
    }
    if ( v5 == 1 )
    {
LABEL_70:
      DeleteMaybeSpecialRgn(*(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL));
      *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL) = 0;
      SetOrClrWF(0, a1, 258, 1);
LABEL_53:
      if ( v13 )
      {
        v50 = *((_QWORD *)a1 + 5);
        if ( !*(_QWORD *)(v50 + 136) && (*(_BYTE *)(v50 + 17) & 0x10) == 0 )
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
    v53 = GreCombineRgn(*(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL), *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL), v5, 4);
    if ( !v53 )
      goto LABEL_59;
    if ( v53 != 1 )
      goto LABEL_53;
    goto LABEL_70;
  }
}

```

## disassembly

```asm
0x140019554  mov     [rsp+arg_0], rbx
0x140019559  mov     [rsp+arg_8], rdx
0x14001955e  push    rbp
0x14001955f  push    rsi
0x140019560  push    rdi
0x140019561  push    r12
0x140019563  push    r13
0x140019565  push    r14
0x140019567  push    r15
0x140019569  sub     rsp, 30h
0x14001956d  mov     r14d, r8d
0x140019570  mov     esi, r8d
0x140019573  mov     r13, rdx
0x140019576  mov     rdi, rcx
0x140019579  and     r14d, 1
0x14001957d  jz      short loc_1400195A0
0x14001957f  mov     rcx, [rcx+18h]
0x140019583  xor     eax, eax
0x140019585  test    rcx, rcx
0x140019588  jz      short loc_140019597
0x14001958a  mov     rdx, [rcx+8]
0x14001958e  test    rdx, rdx
0x140019591  jz      short loc_140019597
0x140019593  mov     rax, [rdx+18h]
0x140019597  cmp     rdi, rax
0x14001959a  jz      loc_1400197FE
0x1400195a0  mov     rdx, [rdi+28h]
0x1400195a4  mov     r15b, 10h
0x1400195a7  cmp     qword ptr [rdx+88h], 0
0x1400195af  lea     rcx, [rdx+11h]
0x1400195b3  jz      loc_1400197EE
0x1400195b9  mov     ebx, 1
0x1400195be  mov     [rsp+68h+arg_18], ebx
0x1400195c5  test    esi, 407h
0x1400195cb  jz      loc_140019840
0x1400195d1  mov     ebp, 0FFFFFFF0h
0x1400195d6  mov     [rsp+68h+arg_10], ebp
0x1400195dd  test    sil, 2
0x1400195e1  jz      short loc_14001964B
0x1400195e3  mov     eax, [rdx+18h]
0x1400195e6  mov     ebp, [rdx+1Ch]
0x1400195e9  mov     ebx, [rdx+0E8h]
0x1400195ef  or      [rcx], r15b
0x1400195f2  mov     rcx, rdi
0x1400195f5  mov     [rsp+68h+var_48], eax
0x1400195f9  call    cs:__imp_IsWindowDesktopComposed
0x140019600  nop     dword ptr [rax+rax+00h]
0x140019605  test    eax, eax
0x140019607  jz      short loc_140019646
0x140019609  mov     rax, [rdi+28h]
0x14001960d  mov     ecx, [rax+18h]
0x140019610  mov     r12d, ecx
0x140019613  mov     r15d, [rax+1Ch]
0x140019617  mov     r13d, r15d
0x14001961a  mov     edx, [rax+0E8h]
0x140019620  xor     ebx, edx
0x140019622  xor     r12d, [rsp+68h+var_48]
0x140019627  xor     r13d, ebp
0x14001962a  jnz     loc_140019A27
0x140019630  test    r12d, r12d
0x140019633  jnz     loc_140019A8B
0x140019639  test    ebx, ebx
0x14001963b  jnz     loc_140019A27
0x140019641  mov     r13, [rsp+68h+arg_8]
0x140019646  mov     ebp, 0FFFFFFF0h
0x14001964b  test    r14d, r14d
0x14001964e  jz      loc_1400197CE
0x140019654  mov     rax, [rdi+28h]
0x140019658  mov     rcx, rdi
0x14001965b  mov     r12d, [rax+1Ch]
0x14001965f  mov     r14d, [rax+18h]
0x140019663  mov     ebx, [rax+0E8h]
0x140019669  and     byte ptr [rax+11h], 0FEh
0x14001966d  call    cs:__imp_IsWindowDesktopComposed
0x140019674  nop     dword ptr [rax+rax+00h]
0x140019679  test    eax, eax
0x14001967b  jz      short loc_1400196AD
0x14001967d  mov     rax, [rdi+28h]
0x140019681  mov     ecx, [rax+18h]
0x140019684  xor     r14d, ecx
0x140019687  mov     edx, [rax+0E8h]
0x14001968d  xor     ebx, edx
0x14001968f  mov     r15d, [rax+1Ch]
0x140019693  xor     r12d, r15d
0x140019696  jnz     loc_140019AAA
0x14001969c  test    r14d, r14d
0x14001969f  jnz     loc_140019B09
0x1400196a5  test    ebx, ebx
0x1400196a7  jnz     loc_140019AAA
0x1400196ad  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400196b4  nop     dword ptr [rax+rax+00h]
0x1400196b9  test    rax, rax
0x1400196bc  jz      loc_140019CEE
0x1400196c2  mov     rax, [rax]
0x1400196c5  cmp     [rdi+10h], rax
0x1400196c9  jnz     loc_1400199D4
0x1400196cf  test    sil, 4
0x1400196d3  jz      short loc_14001972E
0x1400196d5  mov     rax, [rdi+28h]
0x1400196d9  mov     rcx, rdi
0x1400196dc  mov     r12d, [rax+1Ch]
0x1400196e0  mov     r14d, [rax+18h]
0x1400196e4  mov     ebx, [rax+0E8h]
0x1400196ea  or      byte ptr [rax+11h], 2
0x1400196ee  call    cs:__imp_IsWindowDesktopComposed
0x1400196f5  nop     dword ptr [rax+rax+00h]
0x1400196fa  test    eax, eax
0x1400196fc  jz      short loc_14001972E
0x1400196fe  mov     rax, [rdi+28h]
0x140019702  mov     ecx, [rax+18h]
0x140019705  xor     r14d, ecx
0x140019708  mov     edx, [rax+0E8h]
0x14001970e  xor     ebx, edx
0x140019710  mov     r15d, [rax+1Ch]
0x140019714  xor     r12d, r15d
0x140019717  jnz     loc_140019B28
0x14001971d  test    r14d, r14d
0x140019720  jnz     loc_140019B8C
0x140019726  test    ebx, ebx
0x140019728  jnz     loc_140019B28
0x14001972e  bt      esi, 0Ah
0x140019732  jnb     short loc_14001978A
0x140019734  mov     rax, [rdi+28h]
0x140019738  mov     rcx, rdi
0x14001973b  mov     r15d, [rax+1Ch]
0x14001973f  mov     ebp, [rax+18h]
0x140019742  mov     ebx, [rax+0E8h]
0x140019748  or      byte ptr [rax+11h], 8
0x14001974c  call    cs:__imp_IsWindowDesktopComposed
0x140019753  nop     dword ptr [rax+rax+00h]
0x140019758  test    eax, eax
0x14001975a  jz      short loc_14001978A
0x14001975c  mov     rax, [rdi+28h]
0x140019760  mov     ecx, [rax+18h]
0x140019763  xor     ebp, ecx
0x140019765  mov     edx, [rax+0E8h]
0x14001976b  xor     ebx, edx
0x14001976d  mov     r14d, [rax+1Ch]
0x140019771  xor     r15d, r14d
0x140019774  jnz     loc_140019BAB
0x14001977a  test    ebp, ebp
0x14001977c  jnz     loc_140019C0E
0x140019782  test    ebx, ebx
0x140019784  jnz     loc_140019BAB
0x14001978a  mov     rax, [rdi+28h]
0x14001978e  mov     rcx, [rax+88h]
0x140019795  cmp     rcx, 1
0x140019799  jz      short loc_1400197CE
0x14001979b  cmp     r13, 1
0x14001979f  jz      loc_1400198EA
0x1400197a5  test    rcx, rcx
0x1400197a8  jz      loc_1400198A3
0x1400197ae  mov     r9d, 2
0x1400197b4  mov     r8, r13
0x1400197b7  mov     rdx, rcx
0x1400197ba  call    cs:__imp_GreCombineRgn
0x1400197c1  nop     dword ptr [rax+rax+00h]
0x1400197c6  test    eax, eax
0x1400197c8  jz      loc_1400198EA
0x1400197ce  cmp     [rsp+68h+arg_18], 0
0x1400197d6  jz      short loc_140019816
0x1400197d8  mov     rbx, [rsp+68h+arg_0]
0x1400197dd  add     rsp, 30h
0x1400197e1  pop     r15
0x1400197e3  pop     r14
0x1400197e5  pop     r13
0x1400197e7  pop     r12
0x1400197e9  pop     rdi
0x1400197ea  pop     rsi
0x1400197eb  pop     rbp
0x1400197ec  retn
0x1400197ee  test    [rcx], r15b
0x1400197f1  jnz     loc_1400195B9
0x1400197f7  xor     ebx, ebx
0x1400197f9  jmp     loc_1400195BE
0x1400197fe  mov     rcx, rdi
0x140019801  call    cs:__imp_IsWindowDesktopComposed
0x140019808  nop     dword ptr [rax+rax+00h]
0x14001980d  test    eax, eax
0x14001980f  jnz     short loc_1400197D8
0x140019811  jmp     loc_1400195A0
0x140019816  mov     rax, [rdi+28h]
0x14001981a  cmp     qword ptr [rax+88h], 0
0x140019822  jz      short loc_140019838
0x140019824  bt      esi, 11h
0x140019828  jb      loc_140019D41
0x14001982e  mov     rcx, rdi
0x140019831  call    IncPaintCount
0x140019836  jmp     short loc_1400197D8
0x140019838  test    byte ptr [rax+11h], 10h
0x14001983c  jnz     short loc_140019824
0x14001983e  jmp     short loc_1400197D8
0x140019840  test    esi, 838h
0x140019846  jz      short loc_1400197D8
0x140019848  mov     cl, [rcx]
0x14001984a  shr     cl, 5
0x14001984d  bt      esi, 0Fh
0x140019851  setnb   al
0x140019854  and     cl, al
0x140019856  test    cl, 1
0x140019859  jnz     loc_1400197D8
0x14001985f  test    r15b, sil
0x140019862  jnz     loc_140019CF3
0x140019868  test    sil, 8
0x14001986c  jnz     loc_140019915
0x140019872  test    ebx, ebx
0x140019874  jz      loc_1400197D8
0x14001987a  mov     rax, [rdi+28h]
0x14001987e  cmp     qword ptr [rax+88h], 0
0x140019886  jnz     loc_1400197D8
0x14001988c  test    [rax+11h], r15b
0x140019890  jnz     loc_1400197D8
0x140019896  mov     rcx, rdi
0x140019899  call    DecPaintCount
0x14001989e  jmp     loc_1400197D8
0x1400198a3  call    cs:__imp_CreateEmptyRgnPublic
0x1400198aa  nop     dword ptr [rax+rax+00h]
0x1400198af  mov     rcx, [rdi+28h]
0x1400198b3  mov     [rcx+88h], rax
0x1400198ba  mov     rax, [rdi+28h]
0x1400198be  mov     rcx, [rax+88h]
0x1400198c5  test    rcx, rcx
0x1400198c8  jz      short loc_1400198EA
0x1400198ca  mov     r9d, 5
0x1400198d0  xor     r8d, r8d
0x1400198d3  mov     rdx, r13
0x1400198d6  call    cs:__imp_GreCombineRgn
0x1400198dd  nop     dword ptr [rax+rax+00h]
0x1400198e2  test    eax, eax
0x1400198e4  jnz     loc_1400197CE
0x1400198ea  mov     rcx, [rdi+28h]
0x1400198ee  mov     rcx, [rcx+88h]
0x1400198f5  call    cs:__imp_DeleteMaybeSpecialRgn
0x1400198fc  nop     dword ptr [rax+rax+00h]
0x140019901  mov     rax, [rdi+28h]
0x140019905  mov     qword ptr [rax+88h], 1
0x140019910  jmp     loc_1400197CE
0x140019915  mov     ebp, 102h
0x14001991a  test    sil, 20h
0x14001991e  jnz     loc_140019D0E
0x140019924  bt      esi, 0Bh
0x140019928  jb      loc_140019D26
0x14001992e  mov     rax, [rdi+28h]
0x140019932  cmp     qword ptr [rax+88h], 0
0x14001993a  jz      loc_140019872
0x140019940  test    byte ptr [rax+11h], 8
0x140019944  jnz     loc_140019C32
0x14001994a  cmp     r13, 1
0x14001994e  jz      short loc_140019996
0x140019950  mov     rax, [rdi+28h]
0x140019954  cmp     qword ptr [rax+88h], 1
0x14001995c  jz      loc_140019C65
0x140019962  mov     rax, [rdi+28h]
0x140019966  mov     r9d, 4
0x14001996c  mov     r8, r13
0x14001996f  mov     rcx, [rax+88h]
0x140019976  mov     rdx, rcx
0x140019979  call    cs:__imp_GreCombineRgn
0x140019980  nop     dword ptr [rax+rax+00h]
0x140019985  test    eax, eax
0x140019987  jz      loc_1400198EA
0x14001998d  cmp     eax, 1
0x140019990  jnz     loc_140019872
0x140019996  mov     rcx, [rdi+28h]
0x14001999a  mov     rcx, [rcx+88h]
0x1400199a1  call    cs:__imp_DeleteMaybeSpecialRgn
0x1400199a8  nop     dword ptr [rax+rax+00h]
0x1400199ad  mov     rax, [rdi+28h]
0x1400199b1  mov     r8d, ebp
0x1400199b4  mov     r9d, 1
0x1400199ba  mov     rdx, rdi
0x1400199bd  xor     ecx, ecx
0x1400199bf  mov     qword ptr [rax+88h], 0
0x1400199ca  call    SetOrClrWF
0x1400199cf  jmp     loc_140019872
0x1400199d4  mov     r9d, 1
0x1400199da  mov     r8d, 120h
0x1400199e0  mov     ecx, r9d
0x1400199e3  mov     rdx, rdi
0x1400199e6  call    SetOrClrWF
0x1400199eb  mov     rax, [rdi+28h]
0x1400199ef  test    byte ptr [rax+14h], 1
0x1400199f3  jz      loc_1400196CF
0x1400199f9  mov     r9d, 1
0x1400199ff  mov     r8d, 402h
0x140019a05  mov     ecx, r9d
0x140019a08  mov     rdx, rdi
0x140019a0b  call    SetOrClrWF
0x140019a10  call    cs:__imp_W32GetUserSessionState
0x140019a17  nop     dword ptr [rax+rax+00h]
0x140019a1c  or      [rax+0F6CCh], esi
0x140019a22  jmp     loc_1400196CF
0x140019a27  test    r13d, 0B9CF0000h
0x140019a2e  jz      short loc_140019A8B
0x140019a30  mov     ebp, 0FFFFFFF0h
0x140019a35  mov     rcx, rdi; struct tagWND *
0x140019a38  call    DirtyVisRgnTrackers
0x140019a3d  mov     rbx, [rdi]
0x140019a40  call    cs:__imp_ReferenceDwmApiPort
0x140019a47  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
