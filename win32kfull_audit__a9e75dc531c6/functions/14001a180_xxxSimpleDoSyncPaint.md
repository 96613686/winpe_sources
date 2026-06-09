# xxxSimpleDoSyncPaint

- ea: `0x14001a180`
- end: `0x14001a89d`
- name: `xxxSimpleDoSyncPaint`
- size: `1821`
- prototype: `char __fastcall(struct tagWND *, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140019de0`
- `0x14001bfcc`
- `0x1400bf7ec`
- `0x1400e177c`
- `0x1401af970`

## callees

- `0x1400190d8`
- `0x14001a180`
- `0x14001af00`
- `0x14001b0e0`
- `0x14002323c`
- `0x14002479c`
- `0x140026790`
- `0x14008dabc`
- `0x1400e491c`
- `0x1401f56c0`

## import_xrefs

- `ntoskrnl!LpcRequestPort` at `0x14001a46d`
- `ntoskrnl!LpcRequestPort` at `0x14001a46d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001a298`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001a298`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a47c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001a47c`
- `win32kbase!CreateEmptyRgnPublic` at `0x14001a4d5`
- `win32kbase!CreateEmptyRgnPublic` at `0x14001a671`
- `win32kbase!CreateEmptyRgnPublic` at `0x14001a4d5`
- `win32kbase!CreateEmptyRgnPublic` at `0x14001a671`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x14001a3df`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x14001a5e1`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x14001a3df`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x14001a5e1`
- `win32kbase!GreCombineRgn` at `0x14001a504`
- `win32kbase!GreCombineRgn` at `0x14001a560`
- `win32kbase!GreCombineRgn` at `0x14001a6a0`
- `win32kbase!GreCombineRgn` at `0x14001a504`
- `win32kbase!GreCombineRgn` at `0x14001a560`
- `win32kbase!GreCombineRgn` at `0x14001a6a0`
- `win32kbase!IsWindowDesktopComposed` at `0x14001a1f1`
- `win32kbase!IsWindowDesktopComposed` at `0x14001a2dd`
- `win32kbase!IsWindowDesktopComposed` at `0x14001a351`
- `win32kbase!IsWindowDesktopComposed` at `0x14001a1f1`
- `win32kbase!IsWindowDesktopComposed` at `0x14001a2dd`
- `win32kbase!IsWindowDesktopComposed` at `0x14001a351`
- `win32kbase!GreDeleteObject` at `0x14001a588`
- `win32kbase!GreDeleteObject` at `0x14001a843`
- `win32kbase!GreDeleteObject` at `0x14001a864`
- `win32kbase!GreDeleteObject` at `0x14001a887`
- `win32kbase!GreDeleteObject` at `0x14001a588`
- `win32kbase!GreDeleteObject` at `0x14001a843`
- `win32kbase!GreDeleteObject` at `0x14001a864`
- `win32kbase!GreDeleteObject` at `0x14001a887`
- `win32kbase!ReferenceDwmApiPort` at `0x14001a40b`
- `win32kbase!ReferenceDwmApiPort` at `0x14001a6e1`
- `win32kbase!ReferenceDwmApiPort` at `0x14001a76e`
- `win32kbase!ReferenceDwmApiPort` at `0x14001a40b`
- `win32kbase!ReferenceDwmApiPort` at `0x14001a6e1`
- `win32kbase!ReferenceDwmApiPort` at `0x14001a76e`
- `WIN32K!W32GetUserSessionState` at `0x14001a518`
- `WIN32K!W32GetUserSessionState` at `0x14001a539`
- `WIN32K!W32GetUserSessionState` at `0x14001a518`
- `WIN32K!W32GetUserSessionState` at `0x14001a539`

## pseudocode

```c
char __fastcall xxxSimpleDoSyncPaint(struct tagWND *a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct tagWND *v5; // rax
  __int64 v6; // rax
  int v7; // ebx
  int v8; // esi
  int v9; // ebp
  _DWORD *v10; // rax
  int v11; // r15d
  int v12; // edx
  int v13; // r14d
  int v14; // ecx
  int v15; // ebx
  int v16; // eax
  __int64 v17; // rdx
  int v18; // esi
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rbp
  int v24; // ecx
  int v25; // ebx
  int v26; // r13d
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  _DWORD *v30; // rax
  int v31; // r14d
  int v32; // eax
  int v33; // r15d
  __int64 v34; // rax
  int v35; // ecx
  int v36; // ebx
  int v37; // r13d
  int v38; // r14d
  int v39; // r15d
  unsigned __int64 v40; // rbx
  int v41; // esi
  __int64 v42; // r13
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  void *v46; // rbp
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 UserSessionState; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // rax
  int v62; // eax
  __int64 v63; // rcx
  __int64 EmptyRgnPublic; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  void *v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  void *v72; // rax
  int v74; // [rsp+20h] [rbp-78h] BYREF
  __int16 v75; // [rsp+24h] [rbp-74h]
  __int128 v76; // [rsp+26h] [rbp-72h]
  __int128 v77; // [rsp+36h] [rbp-62h]
  __int16 v78; // [rsp+46h] [rbp-52h]
  int v79; // [rsp+48h] [rbp-50h]
  __int64 v80; // [rsp+4Ch] [rbp-4Ch]
  int v81; // [rsp+54h] [rbp-44h]
  int v82; // [rsp+58h] [rbp-40h]
  int v83; // [rsp+A0h] [rbp+8h]
  int v84; // [rsp+A0h] [rbp+8h]
  int v85; // [rsp+A8h] [rbp+10h]
  int v86; // [rsp+A8h] [rbp+10h]

  v5 = a1;
  if ( !a1 )
  {
LABEL_4:
    v6 = *((_QWORD *)a1 + 5);
    v7 = *(_DWORD *)(v6 + 28);
    v8 = *(_DWORD *)(v6 + 24);
    v9 = *(_DWORD *)(v6 + 232);
    *(_BYTE *)(v6 + 18) &= ~0x40u;
    if ( !(unsigned int)IsWindowDesktopComposed(a1, a2, a3, a4) )
      goto LABEL_8;
    v10 = (_DWORD *)*((_QWORD *)a1 + 5);
    v11 = v10[7];
    v12 = v10[6];
    v13 = v7 ^ v11;
    v14 = v10[58];
    v15 = v8 ^ v12;
    v16 = v9 ^ v14;
    if ( !v13 )
    {
      if ( v15 )
        goto LABEL_36;
      if ( !v16 )
        goto LABEL_8;
    }
    if ( (v13 & 0xB9CF0000) != 0 )
    {
      v41 = -16;
      goto LABEL_32;
    }
LABEL_36:
    if ( (v15 & 0x4E27A9) != 0 )
    {
      v41 = -20;
      v11 = v12;
    }
    else
    {
      if ( (v16 & 0x372C0) == 0 )
      {
LABEL_34:
        if ( (v15 & 0x200A0381) != 0 || (v13 & 0x1C40000) != 0 )
          WindowMargins::CheckForChanges(a1, 1);
LABEL_8:
        v17 = *((_QWORD *)a1 + 5);
        LOBYTE(v5) = *(_BYTE *)(v17 + 17);
        v18 = ((unsigned __int8)v5 >> 2) & 2 | 1;
        if ( ((unsigned __int8)v5 & 2) == 0 )
          v18 = ((unsigned __int8)v5 >> 2) & 2;
        if ( !v18 )
          return (char)v5;
        if ( (*(_BYTE *)(v17 + 31) & 0x10) == 0 )
        {
          SetOrClrWF(0, a1, 264, 1);
          SetOrClrWF(0, a1, 258, 1);
          LOBYTE(v5) = SetOrClrWF(0, a1, 260, 1);
          return (char)v5;
        }
        CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(((unsigned __int8)v5 >> 2) & 2, v17);
        if ( CurrentThreadWin32Thread )
          v23 = *CurrentThreadWin32Thread;
        else
          v23 = 0;
        v5 = (struct tagWND *)*((_QWORD *)a1 + 5);
        if ( *((_QWORD *)v5 + 17) )
        {
LABEL_25:
          if ( *((_QWORD *)a1 + 2) != v23 )
            return (char)v5;
          v40 = *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL);
          if ( v40 <= 1 )
          {
LABEL_27:
            if ( (v18 & 2) != 0 && (*(_BYTE *)(*((_QWORD *)a1 + 5) + 17LL) & 8) != 0 )
              xxxSendNCPaint(a1, (HRGN)v40);
            if ( (v18 & 1) == 0 )
              goto LABEL_29;
            v63 = *((_QWORD *)a1 + 5);
            if ( (*(_BYTE *)(v63 + 17) & 8) == 0
              || (DeleteMaybeSpecialRgn(v40), v63 = *((_QWORD *)a1 + 5), v40 = *(_QWORD *)(v63 + 136), v40 <= 1) )
            {
LABEL_47:
              if ( (*(_BYTE *)(v63 + 17) & 2) != 0 )
              {
                SetOrClrWF(0, a1, 258, 1);
                SetOrClrWF(0, a1, 260, 1);
                xxxSendEraseBkgnd(a1);
              }
LABEL_29:
              LOBYTE(v5) = DeleteMaybeSpecialRgn(v40);
              return (char)v5;
            }
            EmptyRgnPublic = CreateEmptyRgnPublic();
            v40 = EmptyRgnPublic;
            if ( EmptyRgnPublic )
            {
              if ( (unsigned int)GreCombineRgn(EmptyRgnPublic, *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL), 0, 5) )
              {
LABEL_54:
                v63 = *((_QWORD *)a1 + 5);
                goto LABEL_47;
              }
              GreDeleteObject(v40);
            }
            v40 = 1;
            goto LABEL_54;
          }
          v51 = CreateEmptyRgnPublic();
          v40 = v51;
          if ( v51 )
          {
            if ( (unsigned int)GreCombineRgn(v51, *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL), 0, 5) )
              goto LABEL_41;
            GreDeleteObject(v40);
          }
          v40 = 1;
LABEL_41:
          UserSessionState = W32GetUserSessionState(v53, v52, v54, v55);
          CalcWindowRgn(a1, *(_QWORD *)(UserSessionState + 63136), 1);
          v61 = W32GetUserSessionState(v58, v57, v59, v60);
          v62 = GreCombineRgn(
                  *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL),
                  *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL),
                  *(_QWORD *)(v61 + 63136),
                  1);
          if ( v62 )
          {
            if ( v62 == 1 )
            {
              GreDeleteObject(*(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL));
              *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL) = 0;
              SetOrClrWF(0, a1, 288, 1);
              if ( (*(_BYTE *)(*((_QWORD *)a1 + 5) + 17LL) & 0x10) == 0 )
                DecPaintCount(a1);
            }
          }
          else
          {
            GreDeleteObject(*(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL));
            *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL) = 1;
          }
          goto LABEL_27;
        }
        v24 = *((_DWORD *)v5 + 58);
        v25 = *((_DWORD *)v5 + 7);
        v26 = *((_DWORD *)v5 + 6);
        *((_BYTE *)v5 + 17) &= ~2u;
        v83 = v24;
        if ( !(unsigned int)IsWindowDesktopComposed(a1, v20, v21, v22) )
        {
LABEL_20:
          v34 = *((_QWORD *)a1 + 5);
          v35 = *(_DWORD *)(v34 + 232);
          v36 = *(_DWORD *)(v34 + 28);
          v37 = *(_DWORD *)(v34 + 24);
          *(_BYTE *)(v34 + 17) &= ~4u;
          v84 = v35;
          LODWORD(v5) = IsWindowDesktopComposed(a1, v27, v28, v29);
          if ( !(_DWORD)v5 )
          {
LABEL_24:
            LOBYTE(v18) = v18 & 0xFE;
            goto LABEL_25;
          }
          v5 = (struct tagWND *)*((_QWORD *)a1 + 5);
          v86 = *((_DWORD *)v5 + 7);
          v38 = v37 ^ *((_DWORD *)v5 + 6);
          LODWORD(v5) = v84 ^ *((_DWORD *)v5 + 58);
          v39 = v36 ^ v86;
          if ( v36 == v86 )
          {
            if ( v38 )
            {
LABEL_66:
              if ( (v38 & 0x4E27A9) == 0 && ((unsigned int)v5 & 0x372C0) == 0 )
              {
LABEL_64:
                LOBYTE(v5) = (v39 & 0x1C40000) == 0;
                if ( (((v38 & 0x200A0381) == 0) & (unsigned __int8)v5) == 0 )
                  LOBYTE(v5) = WindowMargins::CheckForChanges(a1, 1);
                goto LABEL_24;
              }
LABEL_63:
              DirtyVisRgnTrackers(a1);
              v72 = (void *)ReferenceDwmApiPort(v70, v69, v71);
              DwmAsyncChildStyleChange(v72);
              goto LABEL_64;
            }
            if ( !(_DWORD)v5 )
              goto LABEL_24;
          }
          if ( (v39 & 0xB9CF0000) != 0 )
            goto LABEL_63;
          goto LABEL_66;
        }
        v30 = (_DWORD *)*((_QWORD *)a1 + 5);
        v85 = v30[7];
        v31 = v26 ^ v30[6];
        v32 = v83 ^ v30[58];
        v33 = v25 ^ v85;
        if ( v25 == v85 )
        {
          if ( v31 )
          {
LABEL_59:
            if ( (v31 & 0x4E27A9) == 0 && (v32 & 0x372C0) == 0 )
            {
LABEL_57:
              if ( (v31 & 0x200A0381) != 0 || (v33 & 0x1C40000) != 0 )
                WindowMargins::CheckForChanges(a1, 1);
              goto LABEL_20;
            }
LABEL_56:
            DirtyVisRgnTrackers(a1);
            v68 = (void *)ReferenceDwmApiPort(v66, v65, v67);
            DwmAsyncChildStyleChange(v68);
            goto LABEL_57;
          }
          if ( !v32 )
            goto LABEL_20;
        }
        if ( (v33 & 0xB9CF0000) != 0 )
          goto LABEL_56;
        goto LABEL_59;
      }
      v41 = -268435456;
      v11 = v14;
    }
LABEL_32:
    DirtyVisRgnTrackers(a1);
    v42 = *(_QWORD *)a1;
    v46 = (void *)ReferenceDwmApiPort(v44, v43, v45);
    IncrementDWMWindowUniqueness(v48, v47, v49, v50);
    if ( v46 )
    {
      v74 = 3932180;
      v78 = 0;
      v79 = 1073741846;
      v80 = v42;
      v81 = v41;
      v75 = 0x8000;
      v76 = 0;
      v82 = v11;
      v77 = 0;
      LpcRequestPort(v46, &v74);
      ObfDereferenceObject(v46);
    }
    goto LABEL_34;
  }
  while ( 1 )
  {
    a2 = *((_QWORD *)v5 + 5);
    if ( (*(_BYTE *)(a2 + 27) & 2) != 0 )
      return (char)v5;
    v5 = (struct tagWND *)*((_QWORD *)v5 + 13);
    if ( !v5 )
      goto LABEL_4;
  }
}

```

## disassembly

```asm
0x14001a180  push    rdi
0x14001a182  sub     rsp, 90h
0x14001a189  mov     rdi, rcx
0x14001a18c  mov     rax, rcx
0x14001a18f  test    rcx, rcx
0x14001a192  jz      short loc_14001A1B1
0x14001a194  mov     rdx, [rax+28h]
0x14001a198  test    byte ptr [rdx+1Bh], 2
0x14001a19c  jz      short loc_14001A1A8
0x14001a19e  add     rsp, 90h
0x14001a1a5  pop     rdi
0x14001a1a6  retn
0x14001a1a8  mov     rax, [rax+68h]
0x14001a1ac  test    rax, rax
0x14001a1af  jnz     short loc_14001A194
0x14001a1b1  mov     rax, [rcx+28h]
0x14001a1b5  mov     [rsp+98h+arg_10], rbx
0x14001a1bd  mov     [rsp+98h+var_10], rbp
0x14001a1c5  mov     [rsp+98h+var_18], rsi
0x14001a1cd  mov     ebx, [rax+1Ch]
0x14001a1d0  mov     esi, [rax+18h]
0x14001a1d3  mov     ebp, [rax+0E8h]
0x14001a1d9  and     byte ptr [rax+12h], 0BFh
0x14001a1dd  mov     [rsp+98h+var_20], r12
0x14001a1e2  mov     [rsp+98h+var_28], r13
0x14001a1e7  mov     [rsp+98h+var_30], r14
0x14001a1ec  mov     [rsp+98h+var_38], r15
0x14001a1f1  call    cs:__imp_IsWindowDesktopComposed
0x14001a1f8  nop     dword ptr [rax+rax+00h]
0x14001a1fd  mov     r12d, 0FFFFFFF0h
0x14001a203  test    eax, eax
0x14001a205  jz      short loc_14001A23F
0x14001a207  mov     rax, [rdi+28h]
0x14001a20b  mov     r15d, [rax+1Ch]
0x14001a20f  mov     r14d, r15d
0x14001a212  mov     edx, [rax+18h]
0x14001a215  xor     r14d, ebx
0x14001a218  mov     ecx, [rax+0E8h]
0x14001a21e  mov     ebx, edx
0x14001a220  mov     eax, ecx
0x14001a222  xor     ebx, esi
0x14001a224  xor     eax, ebp
0x14001a226  test    r14d, r14d
0x14001a229  jnz     loc_14001A3F0
0x14001a22f  test    ebx, ebx
0x14001a231  jnz     loc_14001A4B5
0x14001a237  test    eax, eax
0x14001a239  jnz     loc_14001A3F0
0x14001a23f  mov     rdx, [rdi+28h]
0x14001a243  movzx   eax, byte ptr [rdx+11h]
0x14001a247  mov     ecx, eax
0x14001a249  shr     ecx, 2
0x14001a24c  and     ecx, 2
0x14001a24f  mov     esi, ecx
0x14001a251  or      esi, 1
0x14001a254  test    al, 2
0x14001a256  cmovz   esi, ecx
0x14001a259  test    esi, esi
0x14001a25b  jnz     short loc_14001A28E
0x14001a25d  mov     r14, [rsp+98h+var_30]
0x14001a262  mov     r13, [rsp+98h+var_28]
0x14001a267  mov     r12, [rsp+98h+var_20]
0x14001a26c  mov     rsi, [rsp+98h+var_18]
0x14001a274  mov     rbp, [rsp+98h+var_10]
0x14001a27c  mov     rbx, [rsp+98h+arg_10]
0x14001a284  mov     r15, [rsp+98h+var_38]
0x14001a289  jmp     loc_14001A19E
0x14001a28e  test    byte ptr [rdx+1Fh], 10h
0x14001a292  jz      loc_14001A7D1
0x14001a298  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001a29f  nop     dword ptr [rax+rax+00h]
0x14001a2a4  test    rax, rax
0x14001a2a7  jz      loc_14001A839
0x14001a2ad  mov     rbp, [rax]
0x14001a2b0  mov     rax, [rdi+28h]
0x14001a2b4  cmp     qword ptr [rax+88h], 0
0x14001a2bc  jnz     loc_14001A3A9
0x14001a2c2  mov     ecx, [rax+0E8h]
0x14001a2c8  mov     ebx, [rax+1Ch]
0x14001a2cb  mov     r13d, [rax+18h]
0x14001a2cf  and     byte ptr [rax+11h], 0FDh
0x14001a2d3  mov     [rsp+98h+arg_0], ecx
0x14001a2da  mov     rcx, rdi
0x14001a2dd  call    cs:__imp_IsWindowDesktopComposed
0x14001a2e4  nop     dword ptr [rax+rax+00h]
0x14001a2e9  test    eax, eax
0x14001a2eb  jz      short loc_14001A332
0x14001a2ed  mov     rax, [rdi+28h]
0x14001a2f1  mov     ecx, [rax+1Ch]
0x14001a2f4  mov     r15d, ecx
0x14001a2f7  mov     [rsp+98h+arg_8], ecx
0x14001a2fe  mov     ecx, [rax+18h]
0x14001a301  mov     r14d, ecx
0x14001a304  xor     r14d, r13d
0x14001a307  mov     r13d, [rax+0E8h]
0x14001a30e  mov     eax, r13d
0x14001a311  xor     eax, [rsp+98h+arg_0]
0x14001a318  xor     r15d, ebx
0x14001a31b  jnz     loc_14001A6BD
0x14001a321  test    r14d, r14d
0x14001a324  jnz     loc_14001A731
0x14001a32a  test    eax, eax
0x14001a32c  jnz     loc_14001A6BD
0x14001a332  mov     rax, [rdi+28h]
0x14001a336  mov     ecx, [rax+0E8h]
0x14001a33c  mov     ebx, [rax+1Ch]
0x14001a33f  mov     r13d, [rax+18h]
0x14001a343  and     byte ptr [rax+11h], 0FBh
0x14001a347  mov     [rsp+98h+arg_0], ecx
0x14001a34e  mov     rcx, rdi
0x14001a351  call    cs:__imp_IsWindowDesktopComposed
0x14001a358  nop     dword ptr [rax+rax+00h]
0x14001a35d  test    eax, eax
0x14001a35f  jz      short loc_14001A3A6
0x14001a361  mov     rax, [rdi+28h]
0x14001a365  mov     ecx, [rax+1Ch]
0x14001a368  mov     r15d, ecx
0x14001a36b  mov     [rsp+98h+arg_8], ecx
0x14001a372  mov     ecx, [rax+18h]
0x14001a375  mov     r14d, ecx
0x14001a378  xor     r14d, r13d
0x14001a37b  mov     r13d, [rax+0E8h]
0x14001a382  mov     eax, r13d
0x14001a385  xor     eax, [rsp+98h+arg_0]
0x14001a38c  xor     r15d, ebx
0x14001a38f  jnz     loc_14001A752
0x14001a395  test    r14d, r14d
0x14001a398  jnz     loc_14001A7B9
0x14001a39e  test    eax, eax
0x14001a3a0  jnz     loc_14001A752
0x14001a3a6  and     esi, 0FFFFFFFEh
0x14001a3a9  cmp     [rdi+10h], rbp
0x14001a3ad  jnz     loc_14001A25D
0x14001a3b3  mov     rax, [rdi+28h]
0x14001a3b7  mov     rbx, [rax+88h]
0x14001a3be  cmp     rbx, 1
0x14001a3c2  ja      loc_14001A4D5
0x14001a3c8  test    sil, 2
0x14001a3cc  jnz     loc_14001A646
0x14001a3d2  test    sil, 1
0x14001a3d6  jnz     loc_14001A5D4
0x14001a3dc  mov     rcx, rbx
0x14001a3df  call    cs:__imp_DeleteMaybeSpecialRgn
0x14001a3e6  nop     dword ptr [rax+rax+00h]
0x14001a3eb  jmp     loc_14001A25D
0x14001a3f0  test    r14d, 0B9CF0000h
0x14001a3f7  jz      loc_14001A4B5
0x14001a3fd  mov     esi, r12d
0x14001a400  mov     rcx, rdi; struct tagWND *
0x14001a403  call    DirtyVisRgnTrackers
0x14001a408  mov     r13, [rdi]
0x14001a40b  call    cs:__imp_ReferenceDwmApiPort
0x14001a412  nop     dword ptr [rax+rax+00h]
0x14001a417  mov     rbp, rax
0x14001a41a  call    ?IncrementDWMWindowUniqueness@@YA_JXZ; IncrementDWMWindowUniqueness(void)
0x14001a41f  test    rbp, rbp
0x14001a422  jz      short loc_14001A488
0x14001a424  xor     ecx, ecx
0x14001a426  mov     [rsp+98h+var_78], 3C0014h
0x14001a42e  mov     [rsp+98h+var_52], cx
0x14001a433  lea     rdx, [rsp+98h+var_78]
0x14001a438  xorps   xmm0, xmm0
0x14001a43b  mov     [rsp+98h+var_50], 40000016h
0x14001a443  xorps   xmm1, xmm1
0x14001a446  mov     [rsp+98h+var_4C], r13
0x14001a44b  mov     eax, 0FFFF8000h
0x14001a450  mov     [rsp+98h+var_44], esi
0x14001a454  mov     rcx, rbp
0x14001a457  mov     [rsp+98h+var_74], ax
0x14001a45c  movdqu  [rsp+98h+var_72], xmm0
0x14001a462  mov     [rsp+98h+var_40], r15d
0x14001a467  movdqu  [rsp+98h+var_62], xmm1
0x14001a46d  call    cs:__imp_LpcRequestPort
0x14001a474  nop     dword ptr [rax+rax+00h]
0x14001a479  mov     rcx, rbp; Object
0x14001a47c  call    cs:__imp_ObfDereferenceObject
0x14001a483  nop     dword ptr [rax+rax+00h]
0x14001a488  test    ebx, 200A0381h
0x14001a48e  setz    cl
0x14001a491  test    r14d, 1C40000h
0x14001a498  setz    al
0x14001a49b  test    al, cl
0x14001a49d  jnz     loc_14001A23F
0x14001a4a3  mov     edx, 1
0x14001a4a8  mov     rcx, rdi
0x14001a4ab  call    ?CheckForChanges@WindowMargins@@YAXPEAUtagWND@@W4ChangeReason@1@@Z; WindowMargins::CheckForChanges(tagWND *,WindowMargins::ChangeReason)
0x14001a4b0  jmp     loc_14001A23F
0x14001a4b5  test    ebx, 4E27A9h
0x14001a4bb  jnz     loc_14001A664
0x14001a4c1  test    eax, 372C0h
0x14001a4c6  jz      short loc_14001A488
0x14001a4c8  mov     esi, 0F0000000h
0x14001a4cd  mov     r15d, ecx
0x14001a4d0  jmp     loc_14001A400
0x14001a4d5  call    cs:__imp_CreateEmptyRgnPublic
0x14001a4dc  nop     dword ptr [rax+rax+00h]
0x14001a4e1  mov     rbx, rax
0x14001a4e4  test    rax, rax
0x14001a4e7  jz      loc_14001A84F
0x14001a4ed  mov     rdx, [rdi+28h]
0x14001a4f1  mov     r9d, 5
0x14001a4f7  xor     r8d, r8d
0x14001a4fa  mov     rcx, rax
0x14001a4fd  mov     rdx, [rdx+88h]
0x14001a504  call    cs:__imp_GreCombineRgn
0x14001a50b  nop     dword ptr [rax+rax+00h]
0x14001a510  test    eax, eax
0x14001a512  jz      loc_14001A840
0x14001a518  call    cs:__imp_W32GetUserSessionState
0x14001a51f  nop     dword ptr [rax+rax+00h]
0x14001a524  mov     r8d, 1
0x14001a52a  mov     rcx, rdi
0x14001a52d  mov     rdx, [rax+0F6A0h]
0x14001a534  call    CalcWindowRgn
0x14001a539  call    cs:__imp_W32GetUserSessionState
0x14001a540  nop     dword ptr [rax+rax+00h]
0x14001a545  mov     r9d, 1
0x14001a54b  mov     r8, [rax+0F6A0h]
0x14001a552  mov     rax, [rdi+28h]
0x14001a556  mov     rcx, [rax+88h]
0x14001a55d  mov     rdx, rcx
0x14001a560  call    cs:__imp_GreCombineRgn
0x14001a567  nop     dword ptr [rax+rax+00h]
0x14001a56c  test    eax, eax
0x14001a56e  jz      loc_14001A859
0x14001a574  cmp     eax, 1
0x14001a577  jnz     loc_14001A3C8
0x14001a57d  mov     rcx, [rdi+28h]
0x14001a581  mov     rcx, [rcx+88h]
0x14001a588  call    cs:__imp_GreDeleteObject
0x14001a58f  nop     dword ptr [rax+rax+00h]
0x14001a594  mov     rax, [rdi+28h]
0x14001a598  mov     r8d, 120h
0x14001a59e  mov     r9d, 1
0x14001a5a4  mov     rdx, rdi
0x14001a5a7  xor     ecx, ecx
0x14001a5a9  mov     qword ptr [rax+88h], 0
0x14001a5b4  call    SetOrClrWF
0x14001a5b9  mov     rax, [rdi+28h]
0x14001a5bd  test    byte ptr [rax+11h], 10h
0x14001a5c1  jnz     loc_14001A3C8
0x14001a5c7  mov     rcx, rdi
0x14001a5ca  call    DecPaintCount
0x14001a5cf  jmp     loc_14001A3C8
0x14001a5d4  mov     rcx, [rdi+28h]
0x14001a5d8  test    byte ptr [rcx+11h], 8
0x14001a5dc  jz      short loc_14001A5FE
0x14001a5de  mov     rcx, rbx
0x14001a5e1  call    cs:__imp_DeleteMaybeSpecialRgn
0x14001a5e8  nop     dword ptr [rax+rax+00h]
0x14001a5ed  mov     rcx, [rdi+28h]
0x14001a5f1  mov     rbx, [rcx+88h]
0x14001a5f8  cmp     rbx, 1
0x14001a5fc  ja      short loc_14001A671
0x14001a5fe  test    byte ptr [rcx+11h], 2
0x14001a602  jz      loc_14001A3DC
0x14001a608  mov     r8d, 102h
0x14001a60e  mov     r9d, 1
0x14001a614  mov     rdx, rdi
0x14001a617  xor     ecx, ecx
0x14001a619  call    SetOrClrWF
0x14001a61e  mov     r8d, 104h
0x14001a624  mov     r9d, 1
0x14001a62a  mov     rdx, rdi
0x14001a62d  xor     ecx, ecx
0x14001a62f  call    SetOrClrWF
0x14001a634  mov     r8, rbx
0x14001a637  xor     edx, edx
0x14001a639  mov     rcx, rdi; struct tagWND *
0x14001a63c  call    xxxSendEraseBkgnd
0x14001a641  jmp     loc_14001A3DC
0x14001a646  mov     rax, [rdi+28h]
0x14001a64a  test    byte ptr [rax+11h], 8
0x14001a64e  jz      loc_14001A3D2
0x14001a654  mov     rdx, rbx; HRGN
0x14001a657  mov     rcx, rdi; struct tagWND *
0x14001a65a  call    ?xxxSendNCPaint@@YAXPEAUtagWND@@PEAUHRGN__@@@Z; xxxSendNCPaint(tagWND *,HRGN__ *)
0x14001a65f  jmp     loc_14001A3D2
0x14001a664  mov     esi, 0FFFFFFECh
0x14001a669  mov     r15d, edx
0x14001a66c  jmp     loc_14001A400
0x14001a671  call    cs:__imp_CreateEmptyRgnPublic
0x14001a678  nop     dword ptr [rax+rax+00h]
0x14001a67d  mov     rbx, rax
0x14001a680  test    rax, rax
0x14001a683  jz      loc_14001A893
0x14001a689  mov     rdx, [rdi+28h]
0x14001a68d  mov     r9d, 5
0x14001a693  xor     r8d, r8d
0x14001a696  mov     rcx, rax
0x14001a699  mov     rdx, [rdx+88h]
0x14001a6a0  call    cs:__imp_GreCombineRgn
0x14001a6a7  nop     dword ptr [rax+rax+00h]
0x14001a6ac  test    eax, eax
0x14001a6ae  jz      loc_14001A884
0x14001a6b4  mov     rcx, [rdi+28h]
0x14001a6b8  jmp     loc_14001A5FE
0x14001a6bd  test    r15d, 0B9CF0000h
0x14001a6c4  jz      short loc_14001A731
0x14001a6c6  mov     r13d, [rsp+98h+arg_8]
  ... truncated ...
```
