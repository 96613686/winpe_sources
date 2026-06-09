# StaticWndProcWorker(tagWND *,uint,unsigned __int64,__int64,ulong)

- ea: `0x180051d40`
- end: `0x1800521db`
- name: `?StaticWndProcWorker@@YA_JPEAUtagWND@@I_K_JK@Z`
- size: `1179`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, void *, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180051c80`
- `0x180051ce0`

## callees

- `0x18000d9f0`
- `0x180010950`
- `0x180016320`
- `0x18003024c`
- `0x180038560`
- `0x1800385c8`
- `0x1800386b8`
- `0x18003b448`
- `0x18003b4a0`
- `0x18003bfac`
- `0x18003c588`
- `0x18004cc10`
- `0x180051d40`
- `0x1800521e4`
- `0x180052258`
- `0x1800526a0`
- `0x18008f04c`
- `0x18008f094`
- `0x18008f150`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserAlterWindowStyle` at `0x18005212f`
- `win32u!NtUserAlterWindowStyle` at `0x18005212f`
- `win32u!NtUserSetWindowFNID` at `0x180052003`
- `win32u!NtUserSetWindowFNID` at `0x180052041`
- `win32u!NtUserSetWindowFNID` at `0x18009eb50`
- `win32u!NtUserSetWindowFNID` at `0x180052003`
- `win32u!NtUserSetWindowFNID` at `0x180052041`
- `win32u!NtUserSetWindowFNID` at `0x18009eb50`
- `win32u!NtUserDestroyCursor` at `0x18009ea1f`
- `win32u!NtUserDestroyCursor` at `0x18009ea1f`
- `win32u!NtUserSetWindowPos` at `0x18009eb3c`
- `win32u!NtUserSetWindowPos` at `0x18009eb3c`
- `win32u!NtUserKillTimer` at `0x18009ea0c`
- `win32u!NtUserKillTimer` at `0x18009ea0c`
- `win32u!NtUserInvalidateRect` at `0x180051f69`
- `win32u!NtUserInvalidateRect` at `0x180051f69`
- `win32u!NtUserEndPaint` at `0x180052087`
- `win32u!NtUserEndPaint` at `0x180052087`
- `win32u!NtUserDestroyWindow` at `0x18005204a`
- `win32u!NtUserDestroyWindow` at `0x18005204a`
- `win32u!NtUserBeginPaint` at `0x180051fd3`
- `win32u!NtUserBeginPaint` at `0x180051fd3`
- `ntdll!RtlFreeHeap` at `0x18009eada`
- `ntdll!RtlFreeHeap` at `0x18009eada`
- `GDI32!DeleteObject` at `0x1800520f1`
- `GDI32!DeleteObject` at `0x1800520f1`

## pseudocode

```c
__int64 __fastcall StaticWndProcWorker(
        struct tagWND *a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  HWND v5; // r12
  HTOUCHINPUT v7; // r15
  unsigned __int64 v8; // r13
  __int64 v10; // r9
  HDC v12; // r9
  __int64 v13; // rdx
  unsigned __int8 v14; // r14
  __int64 v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  int v18; // r8d
  void *v19; // rcx
  void *v20; // rdx
  __int64 v21; // rax
  char *v22; // r10
  __int64 v23; // rcx
  char *v24; // rcx
  unsigned __int16 *v25; // rdi
  unsigned __int16 *v26; // rdx
  int v27; // eax
  int v28; // r15d
  int v29; // [rsp+40h] [rbp-71h] BYREF
  __int64 v30[2]; // [rsp+48h] [rbp-69h] BYREF
  _BYTE v31[80]; // [rsp+60h] [rbp-51h] BYREF

  v5 = *(HWND *)a1;
  v30[0] = a4;
  v7 = (HTOUCHINPUT)a4;
  v8 = a2;
  if ( *((_WORD *)a1 + 21) )
  {
    if ( *((_WORD *)a1 + 21) != 680 )
      return 0;
  }
  else
  {
    if ( *((_DWORD *)a1 + 50) < (int)*(unsigned __int16 *)(gpsi + 356) )
      return 0;
    NtUserSetWindowFNID(v5, 680);
  }
  if ( !**((_QWORD **)a1 + 37) )
  {
    if ( dword_1800C8944 )
    {
      if ( (int)InitLookaside((struct _LOOKASIDE *)&StaticLookaside, 0x28u, 8u) < 0 )
        goto LABEL_47;
      dword_1800C8944 = 0;
    }
    v16 = AllocLookasideEntry((struct _LOOKASIDE *)&StaticLookaside);
    v17 = v16;
    if ( v16 )
    {
      _SetWindowLongPtr(v5, 0, (__int64)v16, 0);
      *v17 = a1;
      goto LABEL_4;
    }
LABEL_47:
    NtUserSetWindowFNID(v5, 0x4000);
    NtUserDestroyWindow(v5);
    return 0;
  }
LABEL_4:
  if ( (unsigned int)v8 > dword_1800C9478
    || ((unsigned __int8)(1 << (v8 & 7)) & *(_BYTE *)((v8 >> 3) + qword_1800C9480)) == 0 )
  {
    v10 = (__int64)v7;
    return DefWindowProcWorker(a1, v8, a3, v10, a5);
  }
  v13 = 31;
  v14 = *((_BYTE *)a1 + 28) & 0x1F;
  v15 = **((_QWORD **)a1 + 37);
  if ( (unsigned int)v8 > 0x84 )
  {
    if ( (unsigned int)v8 > 0x171 )
    {
      if ( (_DWORD)v8 == 370 )
      {
        if ( a3 >= 4 )
          return 0;
LABEL_127:
        if ( *((_BYTE *)&qword_1800AC8D8 + a3) != v14 )
          return 0;
        return (__int64)xxxSetStaticImage(**((struct tagSTAT ***)a1 + 37), v7, 0);
      }
      if ( (_DWORD)v8 != 371 )
      {
        if ( (_DWORD)v8 != 513 )
        {
          if ( (_DWORD)v8 != 515 )
          {
            if ( (_DWORD)v8 == 792 )
            {
              xxxStaticPaint(**((struct tagSTAT ***)a1 + 37), (HDC)a3, 0);
              return 0;
            }
            goto LABEL_42;
          }
          goto LABEL_118;
        }
LABEL_120:
        if ( (*((_BYTE *)a1 + 29) & 1) == 0 )
          return 0;
        v18 = 0;
        goto LABEL_122;
      }
      if ( a3 >= 4 )
        return 0;
    }
    else
    {
      if ( (_DWORD)v8 != 369 )
      {
        if ( (_DWORD)v8 == 135 )
          return 256;
        if ( (_DWORD)v8 != 161 )
        {
          if ( (_DWORD)v8 != 163 )
          {
            if ( (_DWORD)v8 == 275 )
            {
              if ( a3 == 65533 )
                xxxNextAniIconStep(**((struct tagSTAT ***)a1 + 37));
              return 0;
            }
            if ( (_DWORD)v8 == 296 )
            {
              DefWindowProcWorker(a1, 0x128u, a3, v30[0], a5);
              if ( (a3 & 0x20000) != 0 && (v14 <= 2u || (unsigned __int8)(v14 - 11) <= 2u) )
              {
                *(_DWORD *)(v15 + 32) |= 1u;
                StaticRepaint((struct tagSTAT *)v15);
                *(_DWORD *)(v15 + 32) &= ~1u;
              }
              return 0;
            }
            if ( (_DWORD)v8 != 368 )
              goto LABEL_42;
            v7 = (HTOUCHINPUT)a3;
            a3 = 1;
            goto LABEL_127;
          }
LABEL_118:
          if ( (*((_BYTE *)a1 + 29) & 1) == 0 )
            return 0;
          v18 = 1;
          goto LABEL_122;
        }
        goto LABEL_120;
      }
      a3 = 1;
    }
    if ( *((_BYTE *)&qword_1800AC8D8 + a3) != v14 )
      return 0;
    return *(_QWORD *)(v15 + 16);
  }
  if ( (_DWORD)v8 == 132 )
    return 2LL * (*((_BYTE *)a1 + 29) & 1) - 1;
  if ( (_DWORD)v8 == 48 )
  {
    if ( (*((_BYTE *)qword_1800AA410 + v14) & 8) != 0 )
    {
      *(_QWORD *)(v15 + 8) = a3;
      if ( v7 )
      {
        if ( (*((_BYTE *)a1 + 31) & 0x10) != 0 )
        {
          NtUserInvalidateRect(v5, 0, 1);
          UpdateWindow(v5);
        }
      }
    }
    return 0;
  }
  if ( (unsigned int)v8 <= 0x30 )
  {
    if ( (_DWORD)v8 == 1 )
    {
      if ( (*((_BYTE *)qword_1800AA410 + v14) & 3) == 1 )
      {
        v25 = 0;
        v26 = (unsigned __int16 *)*((_QWORD *)v7 + 7);
        v30[0] = 0;
        v29 = 0;
        if ( a5 )
        {
          if ( v26 )
          {
            if ( *(_BYTE *)v26 == 0xFF )
            {
              v25 = (unsigned __int16 *)&v29;
              LOWORD(v29) = -1;
              HIWORD(v29) = *(unsigned __int16 *)((char *)v26 + 1);
            }
            else
            {
              MBToWCSEx(0, v26, 0xFFFFFFFFLL, v30, -1, 1);
              v25 = (unsigned __int16 *)v30[0];
            }
          }
        }
        else
        {
          v25 = v26;
        }
        xxxStaticLoadImage((struct tagSTAT *)v15, v25);
        if ( a5 && v25 && v25 != (unsigned __int16 *)&v29 )
          RtlFreeHeap(pUserHeap, 0, v25);
      }
      else if ( (unsigned __int8)(v14 - 16) <= 1u )
      {
        *(_OWORD *)v30 = 0;
        GetClientRect(a1, v30);
        if ( v14 == 16 )
        {
          v27 = v30[1];
          v28 = 2;
        }
        else
        {
          v28 = HIDWORD(v30[1]);
          v27 = 2;
        }
        NtUserSetWindowPos(v5, 0, 0, 0, v27, v28, 22);
      }
      return 0;
    }
    if ( (_DWORD)v8 == 2 )
    {
      if ( (*((_BYTE *)qword_1800AA410 + v14) & 3) == 1 )
      {
        v19 = *(void **)(v15 + 16);
        if ( v19 )
        {
          if ( *(_DWORD *)(v15 + 8) )
          {
            if ( v14 == 14 )
            {
              DeleteObject(v19);
            }
            else if ( v14 == 3 )
            {
              if ( *(_DWORD *)(v15 + 24) > 1u )
                NtUserKillTimer(v5, 65533);
              NtUserDestroyCursor(*(_QWORD *)(v15 + 16), 1);
            }
          }
        }
      }
      return 0;
    }
    if ( (_DWORD)v8 != 10 )
    {
      switch ( (_DWORD)v8 )
      {
        case 0xC:
          if ( (*((_BYTE *)qword_1800AA410 + v14) & 0x10) != 0
            && (unsigned int)_DefSetText(v5, (const unsigned __int16 *)v7, a5) )
          {
            StaticRepaint((struct tagSTAT *)v15);
            return 1;
          }
          return 0;
        case 0xF:
          memset_0(v31, 0, 0x48u);
          if ( !a3 )
            NtUserBeginPaint(v5, v31);
          if ( (unsigned int)IsVisible(a1) )
            xxxStaticPaint((struct tagSTAT *)v15, v12, a3 == 0);
          if ( !a3 )
            NtUserEndPaint(v5, v31);
          return 0;
        case 0x14:
          return 1;
      }
      goto LABEL_42;
    }
    StaticRepaint(**((struct tagSTAT ***)a1 + 37));
    if ( (*((_BYTE *)a1 + 29) & 1) == 0 )
      return 0;
    v18 = 3 - (a3 != 0);
LABEL_122:
    StaticNotifyParent(a1, (struct tagWND *)v13, v18);
    return 0;
  }
  switch ( (_DWORD)v8 )
  {
    case 0x31:
      if ( (*((_BYTE *)qword_1800AA410 + v14) & 8) == 0 )
        return 0;
      return *(_QWORD *)(v15 + 8);
    case 0x50:
      if ( (*(_BYTE *)gpsi & 0xC) == 0 )
        goto LABEL_42;
      if ( (*((_BYTE *)a1 + 31) & 0xC0) != 0x40 )
        goto LABEL_42;
      v21 = *((_QWORD *)a1 + 6);
      if ( !v21 )
        goto LABEL_42;
      v22 = (char *)a1 + v21 - *((_QWORD *)a1 + 1);
      if ( !v22 )
        goto LABEL_42;
      v23 = *((_QWORD *)v22 + 16);
      v24 = v23 ? &v22[v23 - *((_QWORD *)v22 + 1)] : 0LL;
      if ( *(_WORD *)v24 != *(_WORD *)(gpsi + 904) )
        goto LABEL_42;
      return SendMessageWorker((struct tagWND *)v22, 0x50u, a3, v7, 0);
    case 0x70:
      goto LABEL_58;
    case 0x81:
      if ( (*((_BYTE *)a1 + 25) & 0x10) != 0 )
        NtUserAlterWindowStyle(v5, 31, 2);
      if ( (*((_BYTE *)a1 + 29) & 0x10) != 0 || (unsigned __int8)(v14 - 16) <= 1u )
        SetWindowState(a1, 0xA02u);
      goto LABEL_42;
    case 0x82:
LABEL_58:
      if ( v15 )
      {
        v20 = (void *)**((_QWORD **)a1 + 37);
        *(_QWORD *)v15 = 0;
        FreeLookasideEntry((struct _LOOKASIDE *)&StaticLookaside, v20);
      }
      NtUserSetWindowFNID(v5, 0x4000);
      return 0;
    default:
LABEL_42:
      v10 = v30[0];
      return DefWindowProcWorker(a1, v8, a3, v10, a5);
  }
}

```

## disassembly

```asm
0x180051d40  push    rbp
0x180051d42  push    rbx
0x180051d43  push    rsi
0x180051d44  push    rdi
0x180051d45  push    r12
0x180051d47  push    r13
0x180051d49  push    r14
0x180051d4b  push    r15
0x180051d4d  lea     rbp, [rsp-17h]
0x180051d52  sub     rsp, 0C8h
0x180051d59  mov     rax, cs:__security_cookie
0x180051d60  xor     rax, rsp
0x180051d63  mov     [rbp+4Fh+var_50], rax
0x180051d67  mov     r12, [rcx]
0x180051d6a  mov     rsi, r8
0x180051d6d  xor     r8d, r8d
0x180051d70  mov     [rbp+4Fh+var_B8], r9
0x180051d74  mov     r15, r9
0x180051d77  mov     r13d, edx
0x180051d7a  mov     rdi, rcx
0x180051d7d  cmp     [rcx+2Ah], r8w
0x180051d82  jz      loc_180051FE1
0x180051d88  mov     edx, 2A8h
0x180051d8d  cmp     [rcx+2Ah], dx
0x180051d91  jnz     loc_180051E25
0x180051d97  mov     rax, [rdi+128h]
0x180051d9e  cmp     [rax], r8
0x180051da1  jz      loc_180051EF1
0x180051da7  cmp     r13d, cs:dword_1800C9478
0x180051dae  jbe     short loc_180051E29
0x180051db0  mov     r9, r15; __int64
0x180051db3  mov     eax, [rbp+4Fh+arg_20]
0x180051db6  mov     r8, rsi; unsigned __int64
0x180051db9  mov     edx, r13d; unsigned int
0x180051dbc  mov     [rsp+100h+var_E0], eax; unsigned int
0x180051dc0  mov     rcx, rdi; struct tagWND *
0x180051dc3  call    ?DefWindowProcWorker@@YA_JPEAUtagWND@@I_K_JK@Z; DefWindowProcWorker(tagWND *,uint,unsigned __int64,__int64,ulong)
0x180051dc8  mov     rcx, [rbp+4Fh+var_50]
0x180051dcc  xor     rcx, rsp; StackCookie
0x180051dcf  call    __security_check_cookie
0x180051dd4  add     rsp, 0C8h
0x180051ddb  pop     r15
0x180051ddd  pop     r14
0x180051ddf  pop     r13
0x180051de1  pop     r12
0x180051de3  pop     rdi
0x180051de4  pop     rsi
0x180051de5  pop     rbx
0x180051de6  pop     rbp
0x180051de7  retn
0x180051de8  sub     ecx, 3
0x180051deb  jnz     loc_180052055
0x180051df1  lea     r8d, [rcx+48h]; Size
0x180051df5  xor     edx, edx; Val
0x180051df7  lea     rcx, [rbp+4Fh+var_A0]; void *
0x180051dfb  call    memset_0
0x180051e00  test    rsi, rsi
0x180051e03  jz      loc_180051FCC
0x180051e09  mov     r9, rsi
0x180051e0c  mov     rcx, rdi
0x180051e0f  call    IsVisible
0x180051e14  test    eax, eax
0x180051e16  jnz     loc_180052066
0x180051e1c  test    rsi, rsi
0x180051e1f  jz      loc_180052080
0x180051e25  xor     eax, eax
0x180051e27  jmp     short loc_180051DC8
0x180051e29  mov     rax, cs:qword_1800C9480
0x180051e30  mov     ecx, r13d
0x180051e33  and     ecx, 7
0x180051e36  mov     r9d, 1
0x180051e3c  mov     edx, r9d
0x180051e3f  shl     edx, cl
0x180051e41  mov     rcx, r13
0x180051e44  shr     rcx, 3
0x180051e48  test    [rcx+rax], dl
0x180051e4b  jz      loc_180051DB0
0x180051e51  mov     rax, [rdi+128h]
0x180051e58  lea     edx, [r9+1Eh]; struct tagWND *
0x180051e5c  mov     r14b, [rdi+1Ch]
0x180051e60  and     r14b, dl
0x180051e63  mov     rbx, [rax]
0x180051e66  lea     eax, [rdx+65h]
0x180051e69  cmp     r13d, eax
0x180051e6c  ja      loc_18009EB91
0x180051e72  jz      loc_1800521C7
0x180051e78  cmp     r13d, 30h ; '0'
0x180051e7c  jz      loc_180051F31
0x180051e82  ja      loc_180051F7C
0x180051e88  mov     ecx, r13d
0x180051e8b  sub     ecx, r9d
0x180051e8e  jz      loc_18009EA2B
0x180051e94  sub     ecx, r9d
0x180051e97  jz      loc_1800520B3
0x180051e9d  sub     ecx, 8
0x180051ea0  jz      loc_180052092
0x180051ea6  sub     ecx, 2
0x180051ea9  jnz     loc_180051DE8
0x180051eaf  movzx   eax, r14b
0x180051eb3  lea     rcx, __ImageBase
0x180051eba  test    byte ptr [rax+rcx+0AA410h], 10h
0x180051ec2  jz      loc_180051E25
0x180051ec8  mov     r8d, [rbp+4Fh+arg_20]; int
0x180051ecc  mov     rdx, r15; unsigned __int16 *
0x180051ecf  mov     rcx, r12; HWND
0x180051ed2  call    ?_DefSetText@@YAHPEAUHWND__@@PEBGH@Z; _DefSetText(HWND__ *,ushort const *,int)
0x180051ed7  test    eax, eax
0x180051ed9  jz      loc_180051E25
0x180051edf  mov     rcx, rbx; struct tagSTAT *
0x180051ee2  call    ?StaticRepaint@@YAXPEAUtagSTAT@@@Z; StaticRepaint(tagSTAT *)
0x180051ee7  mov     eax, 1
0x180051eec  jmp     loc_180051DC8
0x180051ef1  cmp     cs:dword_1800C8944, r8d
0x180051ef8  jnz     loc_180052011
0x180051efe  lea     rcx, ?StaticLookaside@@3U_LOOKASIDE@@A; struct _LOOKASIDE *
0x180051f05  call    ?AllocLookasideEntry@@YAPEAXPEAU_LOOKASIDE@@@Z; AllocLookasideEntry(_LOOKASIDE *)
0x180051f0a  mov     rbx, rax
0x180051f0d  test    rax, rax
0x180051f10  jz      loc_180052039
0x180051f16  xor     r9d, r9d; int
0x180051f19  mov     r8, rax; __int64
0x180051f1c  xor     edx, edx; int
0x180051f1e  mov     rcx, r12; HWND
0x180051f21  call    ?_SetWindowLongPtr@@YA_JPEAUHWND__@@H_JH@Z; _SetWindowLongPtr(HWND__ *,int,__int64,int)
0x180051f26  xor     r8d, r8d
0x180051f29  mov     [rbx], rdi
0x180051f2c  jmp     loc_180051DA7
0x180051f31  movzx   eax, r14b
0x180051f35  lea     rcx, __ImageBase
0x180051f3c  test    byte ptr [rax+rcx+0AA410h], 8
0x180051f44  jz      loc_180051E25
0x180051f4a  mov     [rbx+8], rsi
0x180051f4e  test    r15, r15
0x180051f51  jz      loc_180051E25
0x180051f57  test    byte ptr [rdi+1Fh], 10h
0x180051f5b  jz      loc_180051E25
0x180051f61  mov     r8d, r9d
0x180051f64  xor     edx, edx
0x180051f66  mov     rcx, r12
0x180051f69  call    cs:__imp_NtUserInvalidateRect
0x180051f6f  mov     rcx, r12; hWnd
0x180051f72  call    UpdateWindow
0x180051f77  jmp     loc_180051E25
0x180051f7c  mov     eax, r13d
0x180051f7f  sub     eax, 31h ; '1'
0x180051f82  jz      loc_1800521A5
0x180051f88  sub     eax, edx
0x180051f8a  jz      loc_180052152
0x180051f90  sub     eax, 20h ; ' '
0x180051f93  jz      loc_180052105
0x180051f99  sub     eax, 11h
0x180051f9c  jnz     loc_1800520FC
0x180051fa2  test    byte ptr [rdi+19h], 10h
0x180051fa6  jnz     loc_180052126
0x180051fac  test    byte ptr [rdi+1Dh], 10h
0x180051fb0  jz      loc_180052140
0x180051fb6  mov     edx, 0A02h; unsigned int
0x180051fbb  mov     rcx, rdi; struct tagWND *
0x180051fbe  call    ?SetWindowState@@YAXPEAUtagWND@@I@Z; SetWindowState(tagWND *,uint)
0x180051fc3  mov     r9, [rbp+4Fh+var_B8]
0x180051fc7  jmp     loc_180051DB3
0x180051fcc  lea     rdx, [rbp+4Fh+var_A0]
0x180051fd0  mov     rcx, r12
0x180051fd3  call    cs:__imp_NtUserBeginPaint
0x180051fd9  mov     r9, rax
0x180051fdc  jmp     loc_180051E0C
0x180051fe1  mov     rax, cs:gpsi
0x180051fe8  movzx   ecx, word ptr [rax+164h]
0x180051fef  cmp     [rdi+0C8h], ecx
0x180051ff5  jl      loc_180051E25
0x180051ffb  mov     edx, 2A8h
0x180052000  mov     rcx, r12
0x180052003  call    cs:__imp_NtUserSetWindowFNID
0x180052009  xor     r8d, r8d
0x18005200c  jmp     loc_180051D97
0x180052011  mov     edx, 28h ; '('; unsigned int
0x180052016  lea     rcx, ?StaticLookaside@@3U_LOOKASIDE@@A; struct _LOOKASIDE *
0x18005201d  lea     r8d, [rdx-20h]; unsigned int
0x180052021  call    ?InitLookaside@@YAJPEAU_LOOKASIDE@@KK@Z; InitLookaside(_LOOKASIDE *,ulong,ulong)
0x180052026  test    eax, eax
0x180052028  js      short loc_180052039
0x18005202a  mov     cs:dword_1800C8944, 0
0x180052034  jmp     loc_180051EFE
0x180052039  mov     edx, 4000h
0x18005203e  mov     rcx, r12
0x180052041  call    cs:__imp_NtUserSetWindowFNID
0x180052047  mov     rcx, r12
0x18005204a  call    cs:__imp_NtUserDestroyWindow
0x180052050  jmp     loc_180051E25
0x180052055  cmp     ecx, 5
0x180052058  jnz     loc_180051FC3
0x18005205e  mov     rax, r9
0x180052061  jmp     loc_180051DC8
0x180052066  xor     r8d, r8d
0x180052069  mov     rdx, r9; HDC
0x18005206c  test    rsi, rsi
0x18005206f  mov     rcx, rbx; struct tagSTAT *
0x180052072  setz    r8b; int
0x180052076  call    ?xxxStaticPaint@@YAXPEAUtagSTAT@@PEAUHDC__@@H@Z; xxxStaticPaint(tagSTAT *,HDC__ *,int)
0x18005207b  jmp     loc_180051E1C
0x180052080  lea     rdx, [rbp+4Fh+var_A0]
0x180052084  mov     rcx, r12
0x180052087  call    cs:__imp_NtUserEndPaint
0x18005208d  jmp     loc_180051E25
0x180052092  mov     rcx, rbx; struct tagSTAT *
0x180052095  call    ?StaticRepaint@@YAXPEAUtagSTAT@@@Z; StaticRepaint(tagSTAT *)
0x18005209a  test    byte ptr [rdi+1Dh], 1
0x18005209e  jz      loc_180051E25
0x1800520a4  neg     rsi
0x1800520a7  sbb     r8d, r8d
0x1800520aa  add     r8d, 3
0x1800520ae  jmp     loc_18009ECBC
0x1800520b3  movzx   eax, r14b
0x1800520b7  lea     rcx, __ImageBase
0x1800520be  mov     al, [rax+rcx+0AA410h]
0x1800520c5  and     al, 3
0x1800520c7  cmp     al, r9b
0x1800520ca  jnz     loc_180051E25
0x1800520d0  mov     rcx, [rbx+10h]; ho
0x1800520d4  test    rcx, rcx
0x1800520d7  jz      loc_180051E25
0x1800520dd  cmp     [rbx+8], r8d
0x1800520e1  jz      loc_180051E25
0x1800520e7  cmp     r14b, 0Eh
0x1800520eb  jnz     loc_18009E9F4
0x1800520f1  call    cs:__imp_DeleteObject
0x1800520f7  jmp     loc_180051E25
0x1800520fc  cmp     eax, r9d
0x1800520ff  jnz     loc_180051FC3
0x180052105  test    rbx, rbx
0x180052108  jz      loc_18009EB48
0x18005210e  mov     rdx, rbx; void *
0x180052111  mov     [rbx], r8
0x180052114  lea     rcx, ?StaticLookaside@@3U_LOOKASIDE@@A; struct _LOOKASIDE *
0x18005211b  call    ?FreeLookasideEntry@@YAXPEAU_LOOKASIDE@@PEAX@Z; FreeLookasideEntry(_LOOKASIDE *,void *)
0x180052120  nop
0x180052121  jmp     loc_18009EB48
0x180052126  mov     r8d, 2
0x18005212c  mov     rcx, r12
0x18005212f  call    cs:__imp_NtUserAlterWindowStyle
0x180052135  mov     r9d, 1
0x18005213b  jmp     loc_180051FAC
0x180052140  sub     r14b, 10h
0x180052144  cmp     r14b, r9b
0x180052147  ja      loc_180051FC3
0x18005214d  jmp     loc_180051FB6
0x180052152  mov     rdx, cs:gpsi
0x180052159  test    byte ptr [rdx], 0Ch
0x18005215c  jz      loc_180051FC3
0x180052162  mov     al, [rdi+1Fh]
0x180052165  and     al, 0C0h
0x180052167  cmp     al, 40h ; '@'
0x180052169  jnz     loc_180051FC3
0x18005216f  mov     rax, [rdi+30h]
0x180052173  test    rax, rax
0x180052176  jz      loc_180051FC3
0x18005217c  sub     rax, [rdi+8]
0x180052180  lea     r10, [rax+rdi]
0x180052184  test    r10, r10
0x180052187  jz      loc_180051FC3
0x18005218d  mov     rcx, [r10+80h]
0x180052194  test    rcx, rcx
0x180052197  jnz     loc_18009EB5C
0x18005219d  mov     rcx, r8
0x1800521a0  jmp     loc_18009EB63
0x1800521a5  movzx   eax, r14b
0x1800521a9  lea     rcx, __ImageBase
0x1800521b0  test    byte ptr [rax+rcx+0AA410h], 8
0x1800521b8  jz      loc_180051E25
0x1800521be  mov     rax, [rbx+8]
0x1800521c2  jmp     loc_180051DC8
0x1800521c7  movzx   eax, byte ptr [rdi+1Dh]
0x1800521cb  and     rax, r9
0x1800521ce  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rax*2]
0x1800521d6  jmp     loc_180051DC8
0x18009e9f4  cmp     r14b, 3
0x18009e9f8  jnz     loc_180051E25
0x18009e9fe  cmp     [rbx+18h], r9d
0x18009ea02  jbe     short loc_18009EA18
0x18009ea04  mov     edx, 0FFFDh
0x18009ea09  mov     rcx, r12
0x18009ea0c  call    cs:__imp_NtUserKillTimer
0x18009ea12  mov     r9d, 1
0x18009ea18  mov     rcx, [rbx+10h]
0x18009ea1c  mov     edx, r9d
0x18009ea1f  call    cs:__imp_NtUserDestroyCursor
0x18009ea25  nop
0x18009ea26  jmp     loc_180051E25
0x18009ea2b  movzx   eax, r14b
0x18009ea2f  lea     rcx, __ImageBase
0x18009ea36  mov     al, [rax+rcx+0AA410h]
0x18009ea3d  and     al, 3
0x18009ea3f  cmp     al, r9b
0x18009ea42  jnz     loc_18009EAE6
0x18009ea48  mov     esi, [rbp+4Fh+arg_20]
0x18009ea4b  mov     rdi, r8
0x18009ea4e  mov     rdx, [r15+38h]
0x18009ea52  mov     [rbp+4Fh+var_B8], r8
0x18009ea56  mov     [rbp+4Fh+var_C0], r8d
0x18009ea5a  test    esi, esi
  ... truncated ...
```
