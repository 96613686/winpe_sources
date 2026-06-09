# xxxSimpleDoSyncPaint

- ea: `0x14001a180`
- end: `0x14001a89d`
- name: `xxxSimpleDoSyncPaint`
- size: `1821`
- prototype: `__int64 __fastcall(struct tagWND *)`
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
char __fastcall xxxSimpleDoSyncPaint(struct tagWND *a1)
{
  struct tagWND *v2; // rax
  __int64 v3; // rax
  int v4; // ebx
  int v5; // esi
  int v6; // ebp
  _DWORD *v7; // rax
  int v8; // r15d
  int v9; // edx
  int v10; // r14d
  int v11; // ecx
  int v12; // ebx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // esi
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v17; // rbp
  int v18; // ecx
  int v19; // ebx
  int v20; // r13d
  _DWORD *v21; // rax
  int v22; // r14d
  int v23; // eax
  int v24; // r15d
  __int64 v25; // rax
  int v26; // ecx
  int v27; // ebx
  int v28; // r13d
  int v29; // r14d
  int v30; // r15d
  unsigned __int64 v31; // rbx
  int v32; // esi
  __int64 v33; // r13
  void *v34; // rbp
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 UserSessionState; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  __int64 v41; // rcx
  __int64 EmptyRgnPublic; // rax
  void *v43; // rax
  void *v44; // rax
  int v46; // [rsp+20h] [rbp-78h] BYREF
  __int16 v47; // [rsp+24h] [rbp-74h]
  __int128 v48; // [rsp+26h] [rbp-72h]
  __int128 v49; // [rsp+36h] [rbp-62h]
  __int16 v50; // [rsp+46h] [rbp-52h]
  int v51; // [rsp+48h] [rbp-50h]
  __int64 v52; // [rsp+4Ch] [rbp-4Ch]
  int v53; // [rsp+54h] [rbp-44h]
  int v54; // [rsp+58h] [rbp-40h]
  int v55; // [rsp+A0h] [rbp+8h]
  int v56; // [rsp+A0h] [rbp+8h]
  int v57; // [rsp+A8h] [rbp+10h]
  int v58; // [rsp+A8h] [rbp+10h]

  v2 = a1;
  if ( !a1 )
  {
LABEL_4:
    v3 = *((_QWORD *)a1 + 5);
    v4 = *(_DWORD *)(v3 + 28);
    v5 = *(_DWORD *)(v3 + 24);
    v6 = *(_DWORD *)(v3 + 232);
    *(_BYTE *)(v3 + 18) &= ~0x40u;
    if ( !(unsigned int)IsWindowDesktopComposed(a1) )
      goto LABEL_8;
    v7 = (_DWORD *)*((_QWORD *)a1 + 5);
    v8 = v7[7];
    v9 = v7[6];
    v10 = v4 ^ v8;
    v11 = v7[58];
    v12 = v5 ^ v9;
    v13 = v6 ^ v11;
    if ( !v10 )
    {
      if ( v12 )
        goto LABEL_36;
      if ( !v13 )
        goto LABEL_8;
    }
    if ( (v10 & 0xB9CF0000) != 0 )
    {
      v32 = -16;
      goto LABEL_32;
    }
LABEL_36:
    if ( (v12 & 0x4E27A9) != 0 )
    {
      v32 = -20;
      v8 = v9;
    }
    else
    {
      if ( (v13 & 0x372C0) == 0 )
      {
LABEL_34:
        if ( (v12 & 0x200A0381) != 0 || (v10 & 0x1C40000) != 0 )
          WindowMargins::CheckForChanges(a1, 1);
LABEL_8:
        v14 = *((_QWORD *)a1 + 5);
        LOBYTE(v2) = *(_BYTE *)(v14 + 17);
        v15 = ((unsigned __int8)v2 >> 2) & 2 | 1;
        if ( ((unsigned __int8)v2 & 2) == 0 )
          v15 = (*(unsigned __int8 *)(v14 + 17) >> 2) & 2;
        if ( !v15 )
          return (char)v2;
        if ( (*(_BYTE *)(v14 + 31) & 0x10) == 0 )
        {
          SetOrClrWF(0, a1, 264, 1);
          SetOrClrWF(0, a1, 258, 1);
          LOBYTE(v2) = SetOrClrWF(0, a1, 260, 1);
          return (char)v2;
        }
        CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
        if ( CurrentThreadWin32Thread )
          v17 = *CurrentThreadWin32Thread;
        else
          v17 = 0;
        v2 = (struct tagWND *)*((_QWORD *)a1 + 5);
        if ( *((_QWORD *)v2 + 17) )
        {
LABEL_25:
          if ( *((_QWORD *)a1 + 2) != v17 )
            return (char)v2;
          v31 = *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL);
          if ( v31 <= 1 )
          {
LABEL_27:
            if ( (v15 & 2) != 0 && (*(_BYTE *)(*((_QWORD *)a1 + 5) + 17LL) & 8) != 0 )
              xxxSendNCPaint(a1, (HRGN)v31);
            if ( (v15 & 1) == 0 )
              goto LABEL_29;
            v41 = *((_QWORD *)a1 + 5);
            if ( (*(_BYTE *)(v41 + 17) & 8) == 0
              || (DeleteMaybeSpecialRgn(v31), v41 = *((_QWORD *)a1 + 5), v31 = *(_QWORD *)(v41 + 136), v31 <= 1) )
            {
LABEL_47:
              if ( (*(_BYTE *)(v41 + 17) & 2) != 0 )
              {
                SetOrClrWF(0, a1, 258, 1);
                SetOrClrWF(0, a1, 260, 1);
                xxxSendEraseBkgnd(a1);
              }
LABEL_29:
              LOBYTE(v2) = DeleteMaybeSpecialRgn(v31);
              return (char)v2;
            }
            EmptyRgnPublic = CreateEmptyRgnPublic();
            v31 = EmptyRgnPublic;
            if ( EmptyRgnPublic )
            {
              if ( (unsigned int)GreCombineRgn(EmptyRgnPublic, *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL), 0, 5) )
              {
LABEL_54:
                v41 = *((_QWORD *)a1 + 5);
                goto LABEL_47;
              }
              GreDeleteObject(v31);
            }
            v31 = 1;
            goto LABEL_54;
          }
          v35 = CreateEmptyRgnPublic();
          v31 = v35;
          if ( v35 )
          {
            if ( (unsigned int)GreCombineRgn(v35, *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL), 0, 5) )
              goto LABEL_41;
            GreDeleteObject(v31);
          }
          v31 = 1;
LABEL_41:
          UserSessionState = W32GetUserSessionState(v36);
          CalcWindowRgn(a1, *(_QWORD *)(UserSessionState + 63136), 1);
          v39 = W32GetUserSessionState(v38);
          v40 = GreCombineRgn(
                  *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL),
                  *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL),
                  *(_QWORD *)(v39 + 63136),
                  1);
          if ( v40 )
          {
            if ( v40 == 1 )
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
        v18 = *((_DWORD *)v2 + 58);
        v19 = *((_DWORD *)v2 + 7);
        v20 = *((_DWORD *)v2 + 6);
        *((_BYTE *)v2 + 17) &= ~2u;
        v55 = v18;
        if ( !(unsigned int)IsWindowDesktopComposed(a1) )
        {
LABEL_20:
          v25 = *((_QWORD *)a1 + 5);
          v26 = *(_DWORD *)(v25 + 232);
          v27 = *(_DWORD *)(v25 + 28);
          v28 = *(_DWORD *)(v25 + 24);
          *(_BYTE *)(v25 + 17) &= ~4u;
          v56 = v26;
          LODWORD(v2) = IsWindowDesktopComposed(a1);
          if ( !(_DWORD)v2 )
          {
LABEL_24:
            LOBYTE(v15) = v15 & 0xFE;
            goto LABEL_25;
          }
          v2 = (struct tagWND *)*((_QWORD *)a1 + 5);
          v58 = *((_DWORD *)v2 + 7);
          v29 = v28 ^ *((_DWORD *)v2 + 6);
          LODWORD(v2) = v56 ^ *((_DWORD *)v2 + 58);
          v30 = v27 ^ v58;
          if ( v27 == v58 )
          {
            if ( v29 )
            {
LABEL_66:
              if ( (v29 & 0x4E27A9) == 0 && ((unsigned int)v2 & 0x372C0) == 0 )
              {
LABEL_64:
                LOBYTE(v2) = (v30 & 0x1C40000) == 0;
                if ( (((v29 & 0x200A0381) == 0) & (unsigned __int8)v2) == 0 )
                  LOBYTE(v2) = WindowMargins::CheckForChanges(a1, 1);
                goto LABEL_24;
              }
LABEL_63:
              DirtyVisRgnTrackers(a1);
              v44 = (void *)ReferenceDwmApiPort();
              DwmAsyncChildStyleChange(v44);
              goto LABEL_64;
            }
            if ( !(_DWORD)v2 )
              goto LABEL_24;
          }
          if ( (v30 & 0xB9CF0000) != 0 )
            goto LABEL_63;
          goto LABEL_66;
        }
        v21 = (_DWORD *)*((_QWORD *)a1 + 5);
        v57 = v21[7];
        v22 = v20 ^ v21[6];
        v23 = v55 ^ v21[58];
        v24 = v19 ^ v57;
        if ( v19 == v57 )
        {
          if ( v22 )
          {
LABEL_59:
            if ( (v22 & 0x4E27A9) == 0 && (v23 & 0x372C0) == 0 )
            {
LABEL_57:
              if ( (v22 & 0x200A0381) != 0 || (v24 & 0x1C40000) != 0 )
                WindowMargins::CheckForChanges(a1, 1);
              goto LABEL_20;
            }
LABEL_56:
            DirtyVisRgnTrackers(a1);
            v43 = (void *)ReferenceDwmApiPort();
            DwmAsyncChildStyleChange(v43);
            goto LABEL_57;
          }
          if ( !v23 )
            goto LABEL_20;
        }
        if ( (v24 & 0xB9CF0000) != 0 )
          goto LABEL_56;
        goto LABEL_59;
      }
      v32 = -268435456;
      v8 = v11;
    }
LABEL_32:
    DirtyVisRgnTrackers(a1);
    v33 = *(_QWORD *)a1;
    v34 = (void *)ReferenceDwmApiPort();
    IncrementDWMWindowUniqueness();
    if ( v34 )
    {
      v46 = 3932180;
      v50 = 0;
      v51 = 1073741846;
      v52 = v33;
      v53 = v32;
      v47 = 0x8000;
      v48 = 0;
      v54 = v8;
      v49 = 0;
      LpcRequestPort(v34, &v46);
      ObfDereferenceObject(v34);
    }
    goto LABEL_34;
  }
  while ( (*(_BYTE *)(*((_QWORD *)v2 + 5) + 27LL) & 2) == 0 )
  {
    v2 = (struct tagWND *)*((_QWORD *)v2 + 13);
    if ( !v2 )
      goto LABEL_4;
  }
  return (char)v2;
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
