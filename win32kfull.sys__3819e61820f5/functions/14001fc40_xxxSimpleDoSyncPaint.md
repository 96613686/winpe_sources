# xxxSimpleDoSyncPaint

- ea: `0x14001fc40`
- end: `0x14002035d`
- name: `xxxSimpleDoSyncPaint`
- size: `1821`
- prototype: `__int64 __fastcall(struct tagWND *)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400152e8`
- `0x14001f8a0`
- `0x140021198`
- `0x1400bb574`
- `0x1400dfc44`

## callees

- `0x14001593c`
- `0x14001fc40`
- `0x1400209c0`
- `0x140020ba0`
- `0x14002832c`
- `0x14002988c`
- `0x14002b844`
- `0x1400858a8`
- `0x1400be70c`
- `0x1401f11e0`

## import_xrefs

- `ntoskrnl!LpcRequestPort` at `0x14001ff2d`
- `ntoskrnl!LpcRequestPort` at `0x14001ff2d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001fd58`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001fd58`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ff3c`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ff3c`
- `win32kbase!CreateEmptyRgnPublic` at `0x14001ff95`
- `win32kbase!CreateEmptyRgnPublic` at `0x140020131`
- `win32kbase!CreateEmptyRgnPublic` at `0x14001ff95`
- `win32kbase!CreateEmptyRgnPublic` at `0x140020131`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x14001fe9f`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x1400200a1`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x14001fe9f`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x1400200a1`
- `win32kbase!GreCombineRgn` at `0x14001ffc4`
- `win32kbase!GreCombineRgn` at `0x140020020`
- `win32kbase!GreCombineRgn` at `0x140020160`
- `win32kbase!GreCombineRgn` at `0x14001ffc4`
- `win32kbase!GreCombineRgn` at `0x140020020`
- `win32kbase!GreCombineRgn` at `0x140020160`
- `win32kbase!IsWindowDesktopComposed` at `0x14001fcb1`
- `win32kbase!IsWindowDesktopComposed` at `0x14001fd9d`
- `win32kbase!IsWindowDesktopComposed` at `0x14001fe11`
- `win32kbase!IsWindowDesktopComposed` at `0x14001fcb1`
- `win32kbase!IsWindowDesktopComposed` at `0x14001fd9d`
- `win32kbase!IsWindowDesktopComposed` at `0x14001fe11`
- `win32kbase!GreDeleteObject` at `0x140020048`
- `win32kbase!GreDeleteObject` at `0x140020303`
- `win32kbase!GreDeleteObject` at `0x140020324`
- `win32kbase!GreDeleteObject` at `0x140020347`
- `win32kbase!GreDeleteObject` at `0x140020048`
- `win32kbase!GreDeleteObject` at `0x140020303`
- `win32kbase!GreDeleteObject` at `0x140020324`
- `win32kbase!GreDeleteObject` at `0x140020347`
- `win32kbase!ReferenceDwmApiPort` at `0x14001fecb`
- `win32kbase!ReferenceDwmApiPort` at `0x1400201a1`
- `win32kbase!ReferenceDwmApiPort` at `0x14002022e`
- `win32kbase!ReferenceDwmApiPort` at `0x14001fecb`
- `win32kbase!ReferenceDwmApiPort` at `0x1400201a1`
- `win32kbase!ReferenceDwmApiPort` at `0x14002022e`
- `WIN32K!W32GetUserSessionState` at `0x14001ffd8`
- `WIN32K!W32GetUserSessionState` at `0x14001fff9`
- `WIN32K!W32GetUserSessionState` at `0x14001ffd8`
- `WIN32K!W32GetUserSessionState` at `0x14001fff9`

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
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  void *v37; // rbp
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 UserSessionState; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rcx
  __int64 EmptyRgnPublic; // rax
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  void *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  void *v59; // rax
  int v61; // [rsp+20h] [rbp-78h] BYREF
  __int16 v62; // [rsp+24h] [rbp-74h]
  __int128 v63; // [rsp+26h] [rbp-72h]
  __int128 v64; // [rsp+36h] [rbp-62h]
  __int16 v65; // [rsp+46h] [rbp-52h]
  int v66; // [rsp+48h] [rbp-50h]
  __int64 v67; // [rsp+4Ch] [rbp-4Ch]
  int v68; // [rsp+54h] [rbp-44h]
  int v69; // [rsp+58h] [rbp-40h]
  int v70; // [rsp+A0h] [rbp+8h]
  int v71; // [rsp+A0h] [rbp+8h]
  int v72; // [rsp+A8h] [rbp+10h]
  int v73; // [rsp+A8h] [rbp+10h]

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
            v50 = *((_QWORD *)a1 + 5);
            if ( (*(_BYTE *)(v50 + 17) & 8) == 0
              || (DeleteMaybeSpecialRgn(v31), v50 = *((_QWORD *)a1 + 5), v31 = *(_QWORD *)(v50 + 136), v31 <= 1) )
            {
LABEL_47:
              if ( (*(_BYTE *)(v50 + 17) & 2) != 0 )
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
                v50 = *((_QWORD *)a1 + 5);
                goto LABEL_47;
              }
              GreDeleteObject(v31);
            }
            v31 = 1;
            goto LABEL_54;
          }
          v38 = CreateEmptyRgnPublic();
          v31 = v38;
          if ( v38 )
          {
            if ( (unsigned int)GreCombineRgn(v38, *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL), 0, 5) )
              goto LABEL_41;
            GreDeleteObject(v31);
          }
          v31 = 1;
LABEL_41:
          UserSessionState = W32GetUserSessionState(v40, v39, v41, v42);
          CalcWindowRgn(a1, *(_QWORD *)(UserSessionState + 63136), 1);
          v48 = W32GetUserSessionState(v45, v44, v46, v47);
          v49 = GreCombineRgn(
                  *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL),
                  *(_QWORD *)(*((_QWORD *)a1 + 5) + 136LL),
                  *(_QWORD *)(v48 + 63136),
                  1);
          if ( v49 )
          {
            if ( v49 == 1 )
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
        v70 = v18;
        if ( !(unsigned int)IsWindowDesktopComposed(a1) )
        {
LABEL_20:
          v25 = *((_QWORD *)a1 + 5);
          v26 = *(_DWORD *)(v25 + 232);
          v27 = *(_DWORD *)(v25 + 28);
          v28 = *(_DWORD *)(v25 + 24);
          *(_BYTE *)(v25 + 17) &= ~4u;
          v71 = v26;
          LODWORD(v2) = IsWindowDesktopComposed(a1);
          if ( !(_DWORD)v2 )
          {
LABEL_24:
            LOBYTE(v15) = v15 & 0xFE;
            goto LABEL_25;
          }
          v2 = (struct tagWND *)*((_QWORD *)a1 + 5);
          v73 = *((_DWORD *)v2 + 7);
          v29 = v28 ^ *((_DWORD *)v2 + 6);
          LODWORD(v2) = v71 ^ *((_DWORD *)v2 + 58);
          v30 = v27 ^ v73;
          if ( v27 == v73 )
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
              v59 = (void *)ReferenceDwmApiPort(v57, v56, v58);
              DwmAsyncChildStyleChange(v59);
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
        v72 = v21[7];
        v22 = v20 ^ v21[6];
        v23 = v70 ^ v21[58];
        v24 = v19 ^ v72;
        if ( v19 == v72 )
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
            v55 = (void *)ReferenceDwmApiPort(v53, v52, v54);
            DwmAsyncChildStyleChange(v55);
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
    v37 = (void *)ReferenceDwmApiPort(v35, v34, v36);
    IncrementDWMWindowUniqueness();
    if ( v37 )
    {
      v61 = 3932180;
      v65 = 0;
      v66 = 1073741846;
      v67 = v33;
      v68 = v32;
      v62 = 0x8000;
      v63 = 0;
      v69 = v8;
      v64 = 0;
      LpcRequestPort(v37, &v61);
      ObfDereferenceObject(v37);
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
0x14001fc40  push    rdi
0x14001fc42  sub     rsp, 90h
0x14001fc49  mov     rdi, rcx
0x14001fc4c  mov     rax, rcx
0x14001fc4f  test    rcx, rcx
0x14001fc52  jz      short loc_14001FC71
0x14001fc54  mov     rdx, [rax+28h]
0x14001fc58  test    byte ptr [rdx+1Bh], 2
0x14001fc5c  jz      short loc_14001FC68
0x14001fc5e  add     rsp, 90h
0x14001fc65  pop     rdi
0x14001fc66  retn
0x14001fc68  mov     rax, [rax+68h]
0x14001fc6c  test    rax, rax
0x14001fc6f  jnz     short loc_14001FC54
0x14001fc71  mov     rax, [rcx+28h]
0x14001fc75  mov     [rsp+98h+arg_10], rbx
0x14001fc7d  mov     [rsp+98h+var_10], rbp
0x14001fc85  mov     [rsp+98h+var_18], rsi
0x14001fc8d  mov     ebx, [rax+1Ch]
0x14001fc90  mov     esi, [rax+18h]
0x14001fc93  mov     ebp, [rax+0E8h]
0x14001fc99  and     byte ptr [rax+12h], 0BFh
0x14001fc9d  mov     [rsp+98h+var_20], r12
0x14001fca2  mov     [rsp+98h+var_28], r13
0x14001fca7  mov     [rsp+98h+var_30], r14
0x14001fcac  mov     [rsp+98h+var_38], r15
0x14001fcb1  call    cs:__imp_IsWindowDesktopComposed
0x14001fcb8  nop     dword ptr [rax+rax+00h]
0x14001fcbd  mov     r12d, 0FFFFFFF0h
0x14001fcc3  test    eax, eax
0x14001fcc5  jz      short loc_14001FCFF
0x14001fcc7  mov     rax, [rdi+28h]
0x14001fccb  mov     r15d, [rax+1Ch]
0x14001fccf  mov     r14d, r15d
0x14001fcd2  mov     edx, [rax+18h]
0x14001fcd5  xor     r14d, ebx
0x14001fcd8  mov     ecx, [rax+0E8h]
0x14001fcde  mov     ebx, edx
0x14001fce0  mov     eax, ecx
0x14001fce2  xor     ebx, esi
0x14001fce4  xor     eax, ebp
0x14001fce6  test    r14d, r14d
0x14001fce9  jnz     loc_14001FEB0
0x14001fcef  test    ebx, ebx
0x14001fcf1  jnz     loc_14001FF75
0x14001fcf7  test    eax, eax
0x14001fcf9  jnz     loc_14001FEB0
0x14001fcff  mov     rdx, [rdi+28h]
0x14001fd03  movzx   eax, byte ptr [rdx+11h]
0x14001fd07  mov     ecx, eax
0x14001fd09  shr     ecx, 2
0x14001fd0c  and     ecx, 2
0x14001fd0f  mov     esi, ecx
0x14001fd11  or      esi, 1
0x14001fd14  test    al, 2
0x14001fd16  cmovz   esi, ecx
0x14001fd19  test    esi, esi
0x14001fd1b  jnz     short loc_14001FD4E
0x14001fd1d  mov     r14, [rsp+98h+var_30]
0x14001fd22  mov     r13, [rsp+98h+var_28]
0x14001fd27  mov     r12, [rsp+98h+var_20]
0x14001fd2c  mov     rsi, [rsp+98h+var_18]
0x14001fd34  mov     rbp, [rsp+98h+var_10]
0x14001fd3c  mov     rbx, [rsp+98h+arg_10]
0x14001fd44  mov     r15, [rsp+98h+var_38]
0x14001fd49  jmp     loc_14001FC5E
0x14001fd4e  test    byte ptr [rdx+1Fh], 10h
0x14001fd52  jz      loc_140020291
0x14001fd58  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14001fd5f  nop     dword ptr [rax+rax+00h]
0x14001fd64  test    rax, rax
0x14001fd67  jz      loc_1400202F9
0x14001fd6d  mov     rbp, [rax]
0x14001fd70  mov     rax, [rdi+28h]
0x14001fd74  cmp     qword ptr [rax+88h], 0
0x14001fd7c  jnz     loc_14001FE69
0x14001fd82  mov     ecx, [rax+0E8h]
0x14001fd88  mov     ebx, [rax+1Ch]
0x14001fd8b  mov     r13d, [rax+18h]
0x14001fd8f  and     byte ptr [rax+11h], 0FDh
0x14001fd93  mov     [rsp+98h+arg_0], ecx
0x14001fd9a  mov     rcx, rdi
0x14001fd9d  call    cs:__imp_IsWindowDesktopComposed
0x14001fda4  nop     dword ptr [rax+rax+00h]
0x14001fda9  test    eax, eax
0x14001fdab  jz      short loc_14001FDF2
0x14001fdad  mov     rax, [rdi+28h]
0x14001fdb1  mov     ecx, [rax+1Ch]
0x14001fdb4  mov     r15d, ecx
0x14001fdb7  mov     [rsp+98h+arg_8], ecx
0x14001fdbe  mov     ecx, [rax+18h]
0x14001fdc1  mov     r14d, ecx
0x14001fdc4  xor     r14d, r13d
0x14001fdc7  mov     r13d, [rax+0E8h]
0x14001fdce  mov     eax, r13d
0x14001fdd1  xor     eax, [rsp+98h+arg_0]
0x14001fdd8  xor     r15d, ebx
0x14001fddb  jnz     loc_14002017D
0x14001fde1  test    r14d, r14d
0x14001fde4  jnz     loc_1400201F1
0x14001fdea  test    eax, eax
0x14001fdec  jnz     loc_14002017D
0x14001fdf2  mov     rax, [rdi+28h]
0x14001fdf6  mov     ecx, [rax+0E8h]
0x14001fdfc  mov     ebx, [rax+1Ch]
0x14001fdff  mov     r13d, [rax+18h]
0x14001fe03  and     byte ptr [rax+11h], 0FBh
0x14001fe07  mov     [rsp+98h+arg_0], ecx
0x14001fe0e  mov     rcx, rdi
0x14001fe11  call    cs:__imp_IsWindowDesktopComposed
0x14001fe18  nop     dword ptr [rax+rax+00h]
0x14001fe1d  test    eax, eax
0x14001fe1f  jz      short loc_14001FE66
0x14001fe21  mov     rax, [rdi+28h]
0x14001fe25  mov     ecx, [rax+1Ch]
0x14001fe28  mov     r15d, ecx
0x14001fe2b  mov     [rsp+98h+arg_8], ecx
0x14001fe32  mov     ecx, [rax+18h]
0x14001fe35  mov     r14d, ecx
0x14001fe38  xor     r14d, r13d
0x14001fe3b  mov     r13d, [rax+0E8h]
0x14001fe42  mov     eax, r13d
0x14001fe45  xor     eax, [rsp+98h+arg_0]
0x14001fe4c  xor     r15d, ebx
0x14001fe4f  jnz     loc_140020212
0x14001fe55  test    r14d, r14d
0x14001fe58  jnz     loc_140020279
0x14001fe5e  test    eax, eax
0x14001fe60  jnz     loc_140020212
0x14001fe66  and     esi, 0FFFFFFFEh
0x14001fe69  cmp     [rdi+10h], rbp
0x14001fe6d  jnz     loc_14001FD1D
0x14001fe73  mov     rax, [rdi+28h]
0x14001fe77  mov     rbx, [rax+88h]
0x14001fe7e  cmp     rbx, 1
0x14001fe82  ja      loc_14001FF95
0x14001fe88  test    sil, 2
0x14001fe8c  jnz     loc_140020106
0x14001fe92  test    sil, 1
0x14001fe96  jnz     loc_140020094
0x14001fe9c  mov     rcx, rbx
0x14001fe9f  call    cs:__imp_DeleteMaybeSpecialRgn
0x14001fea6  nop     dword ptr [rax+rax+00h]
0x14001feab  jmp     loc_14001FD1D
0x14001feb0  test    r14d, 0B9CF0000h
0x14001feb7  jz      loc_14001FF75
0x14001febd  mov     esi, r12d
0x14001fec0  mov     rcx, rdi; struct tagWND *
0x14001fec3  call    DirtyVisRgnTrackers
0x14001fec8  mov     r13, [rdi]
0x14001fecb  call    cs:__imp_ReferenceDwmApiPort
0x14001fed2  nop     dword ptr [rax+rax+00h]
0x14001fed7  mov     rbp, rax
0x14001feda  call    ?IncrementDWMWindowUniqueness@@YA_JXZ; IncrementDWMWindowUniqueness(void)
0x14001fedf  test    rbp, rbp
0x14001fee2  jz      short loc_14001FF48
0x14001fee4  xor     ecx, ecx
0x14001fee6  mov     [rsp+98h+var_78], 3C0014h
0x14001feee  mov     [rsp+98h+var_52], cx
0x14001fef3  lea     rdx, [rsp+98h+var_78]
0x14001fef8  xorps   xmm0, xmm0
0x14001fefb  mov     [rsp+98h+var_50], 40000016h
0x14001ff03  xorps   xmm1, xmm1
0x14001ff06  mov     [rsp+98h+var_4C], r13
0x14001ff0b  mov     eax, 0FFFF8000h
0x14001ff10  mov     [rsp+98h+var_44], esi
0x14001ff14  mov     rcx, rbp
0x14001ff17  mov     [rsp+98h+var_74], ax
0x14001ff1c  movdqu  [rsp+98h+var_72], xmm0
0x14001ff22  mov     [rsp+98h+var_40], r15d
0x14001ff27  movdqu  [rsp+98h+var_62], xmm1
0x14001ff2d  call    cs:__imp_LpcRequestPort
0x14001ff34  nop     dword ptr [rax+rax+00h]
0x14001ff39  mov     rcx, rbp; Object
0x14001ff3c  call    cs:__imp_ObfDereferenceObject
0x14001ff43  nop     dword ptr [rax+rax+00h]
0x14001ff48  test    ebx, 200A0381h
0x14001ff4e  setz    cl
0x14001ff51  test    r14d, 1C40000h
0x14001ff58  setz    al
0x14001ff5b  test    al, cl
0x14001ff5d  jnz     loc_14001FCFF
0x14001ff63  mov     edx, 1
0x14001ff68  mov     rcx, rdi
0x14001ff6b  call    ?CheckForChanges@WindowMargins@@YAXPEAUtagWND@@W4ChangeReason@1@@Z; WindowMargins::CheckForChanges(tagWND *,WindowMargins::ChangeReason)
0x14001ff70  jmp     loc_14001FCFF
0x14001ff75  test    ebx, 4E27A9h
0x14001ff7b  jnz     loc_140020124
0x14001ff81  test    eax, 372C0h
0x14001ff86  jz      short loc_14001FF48
0x14001ff88  mov     esi, 0F0000000h
0x14001ff8d  mov     r15d, ecx
0x14001ff90  jmp     loc_14001FEC0
0x14001ff95  call    cs:__imp_CreateEmptyRgnPublic
0x14001ff9c  nop     dword ptr [rax+rax+00h]
0x14001ffa1  mov     rbx, rax
0x14001ffa4  test    rax, rax
0x14001ffa7  jz      loc_14002030F
0x14001ffad  mov     rdx, [rdi+28h]
0x14001ffb1  mov     r9d, 5
0x14001ffb7  xor     r8d, r8d
0x14001ffba  mov     rcx, rax
0x14001ffbd  mov     rdx, [rdx+88h]
0x14001ffc4  call    cs:__imp_GreCombineRgn
0x14001ffcb  nop     dword ptr [rax+rax+00h]
0x14001ffd0  test    eax, eax
0x14001ffd2  jz      loc_140020300
0x14001ffd8  call    cs:__imp_W32GetUserSessionState
0x14001ffdf  nop     dword ptr [rax+rax+00h]
0x14001ffe4  mov     r8d, 1
0x14001ffea  mov     rcx, rdi
0x14001ffed  mov     rdx, [rax+0F6A0h]
0x14001fff4  call    CalcWindowRgn
0x14001fff9  call    cs:__imp_W32GetUserSessionState
0x140020000  nop     dword ptr [rax+rax+00h]
0x140020005  mov     r9d, 1
0x14002000b  mov     r8, [rax+0F6A0h]
0x140020012  mov     rax, [rdi+28h]
0x140020016  mov     rcx, [rax+88h]
0x14002001d  mov     rdx, rcx
0x140020020  call    cs:__imp_GreCombineRgn
0x140020027  nop     dword ptr [rax+rax+00h]
0x14002002c  test    eax, eax
0x14002002e  jz      loc_140020319
0x140020034  cmp     eax, 1
0x140020037  jnz     loc_14001FE88
0x14002003d  mov     rcx, [rdi+28h]
0x140020041  mov     rcx, [rcx+88h]
0x140020048  call    cs:__imp_GreDeleteObject
0x14002004f  nop     dword ptr [rax+rax+00h]
0x140020054  mov     rax, [rdi+28h]
0x140020058  mov     r8d, 120h
0x14002005e  mov     r9d, 1
0x140020064  mov     rdx, rdi
0x140020067  xor     ecx, ecx
0x140020069  mov     qword ptr [rax+88h], 0
0x140020074  call    SetOrClrWF
0x140020079  mov     rax, [rdi+28h]
0x14002007d  test    byte ptr [rax+11h], 10h
0x140020081  jnz     loc_14001FE88
0x140020087  mov     rcx, rdi
0x14002008a  call    DecPaintCount
0x14002008f  jmp     loc_14001FE88
0x140020094  mov     rcx, [rdi+28h]
0x140020098  test    byte ptr [rcx+11h], 8
0x14002009c  jz      short loc_1400200BE
0x14002009e  mov     rcx, rbx
0x1400200a1  call    cs:__imp_DeleteMaybeSpecialRgn
0x1400200a8  nop     dword ptr [rax+rax+00h]
0x1400200ad  mov     rcx, [rdi+28h]
0x1400200b1  mov     rbx, [rcx+88h]
0x1400200b8  cmp     rbx, 1
0x1400200bc  ja      short loc_140020131
0x1400200be  test    byte ptr [rcx+11h], 2
0x1400200c2  jz      loc_14001FE9C
0x1400200c8  mov     r8d, 102h
0x1400200ce  mov     r9d, 1
0x1400200d4  mov     rdx, rdi
0x1400200d7  xor     ecx, ecx
0x1400200d9  call    SetOrClrWF
0x1400200de  mov     r8d, 104h
0x1400200e4  mov     r9d, 1
0x1400200ea  mov     rdx, rdi
0x1400200ed  xor     ecx, ecx
0x1400200ef  call    SetOrClrWF
0x1400200f4  mov     r8, rbx
0x1400200f7  xor     edx, edx
0x1400200f9  mov     rcx, rdi; struct tagWND *
0x1400200fc  call    xxxSendEraseBkgnd
0x140020101  jmp     loc_14001FE9C
0x140020106  mov     rax, [rdi+28h]
0x14002010a  test    byte ptr [rax+11h], 8
0x14002010e  jz      loc_14001FE92
0x140020114  mov     rdx, rbx; HRGN
0x140020117  mov     rcx, rdi; struct tagWND *
0x14002011a  call    ?xxxSendNCPaint@@YAXPEAUtagWND@@PEAUHRGN__@@@Z; xxxSendNCPaint(tagWND *,HRGN__ *)
0x14002011f  jmp     loc_14001FE92
0x140020124  mov     esi, 0FFFFFFECh
0x140020129  mov     r15d, edx
0x14002012c  jmp     loc_14001FEC0
0x140020131  call    cs:__imp_CreateEmptyRgnPublic
0x140020138  nop     dword ptr [rax+rax+00h]
0x14002013d  mov     rbx, rax
0x140020140  test    rax, rax
0x140020143  jz      loc_140020353
0x140020149  mov     rdx, [rdi+28h]
0x14002014d  mov     r9d, 5
0x140020153  xor     r8d, r8d
0x140020156  mov     rcx, rax
0x140020159  mov     rdx, [rdx+88h]
0x140020160  call    cs:__imp_GreCombineRgn
0x140020167  nop     dword ptr [rax+rax+00h]
0x14002016c  test    eax, eax
0x14002016e  jz      loc_140020344
0x140020174  mov     rcx, [rdi+28h]
0x140020178  jmp     loc_1400200BE
0x14002017d  test    r15d, 0B9CF0000h
0x140020184  jz      short loc_1400201F1
0x140020186  mov     r13d, [rsp+98h+arg_8]
  ... truncated ...
```
