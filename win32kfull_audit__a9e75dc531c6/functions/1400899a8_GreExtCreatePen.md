# GreExtCreatePen

- ea: `0x1400899a8`
- end: `0x14008a18b`
- name: `GreExtCreatePen`
- size: `2019`
- prototype: `__int64 __fastcall(Gre::Base *, int, int, unsigned int, HBITMAP, unsigned __int16 *, unsigned int, __int64 *, unsigned int, int, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140089340`
- `0x140089890`
- `0x140089924`

## callees

- `0x140089784`
- `0x1400899a8`
- `0x14008a194`
- `0x14008a21c`
- `0x14008a30c`
- `0x14028be70`

## import_xrefs

- `win32kbase!Win32AllocPool` at `0x140089dba`
- `win32kbase!Win32AllocPool` at `0x140089dba`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400899fa`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140089b34`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140089c7e`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400899fa`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140089b34`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140089c7e`
- `win32kbase!HmgShareLock` at `0x140089b4f`
- `win32kbase!HmgShareLock` at `0x140089b4f`
- `win32kbase!PopThreadGuardedObject` at `0x140089ca1`
- `win32kbase!PopThreadGuardedObject` at `0x140089ca1`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140089c91`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14008a156`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140089c91`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14008a156`
- `win32kbase!PushThreadGuardedObject` at `0x140089b28`
- `win32kbase!PushThreadGuardedObject` at `0x140089b28`
- `win32kbase!EngSetLastError` at `0x140089e4b`
- `win32kbase!EngSetLastError` at `0x14008a126`
- `win32kbase!EngSetLastError` at `0x140089e4b`
- `win32kbase!EngSetLastError` at `0x14008a126`
- `win32kbase!HmgModifyHandleType` at `0x140089c62`
- `win32kbase!HmgModifyHandleType` at `0x140089c62`
- `win32kbase!hCreateSolidBrushInternal` at `0x140089aef`
- `win32kbase!hCreateSolidBrushInternal` at `0x140089aef`
- `win32kbase!GreCreatePatternBrushInternal` at `0x14008a13e`
- `win32kbase!GreCreatePatternBrushInternal` at `0x14008a13e`
- `win32kbase!Win32FreePool` at `0x140089d7a`
- `win32kbase!Win32FreePool` at `0x140089e3a`
- `win32kbase!Win32FreePool` at `0x140089ecf`
- `win32kbase!Win32FreePool` at `0x14008a17a`
- `win32kbase!Win32FreePool` at `0x140089d7a`
- `win32kbase!Win32FreePool` at `0x140089e3a`
- `win32kbase!Win32FreePool` at `0x140089ecf`
- `win32kbase!Win32FreePool` at `0x14008a17a`

## pseudocode

```c
__int64 __fastcall GreExtCreatePen(
        Gre::Base *a1,
        int a2,
        int a3,
        unsigned int a4,
        HBITMAP a5,
        unsigned __int16 *a6,
        unsigned int a7,
        __int64 *a8,
        unsigned int a9,
        int a10,
        __int64 a11)
{
  int v11; // r12d
  int v13; // r13d
  int v14; // esi
  int v15; // ebx
  struct Gre::Base::SESSION_GLOBALS *v16; // rax
  __int64 *v17; // rdi
  int v18; // r15d
  int v19; // eax
  int v20; // eax
  unsigned int v21; // r14d
  __int64 v22; // r9
  _BOOL8 v24; // r9
  HBRUSH SolidBrushInternal; // rax
  HBRUSH v26; // rbx
  Gre::Base *v27; // rcx
  struct Gre::Base::SESSION_GLOBALS *v28; // rax
  __int64 v29; // r8
  struct Gre::Base::SESSION_GLOBALS *v30; // rsi
  __int64 v31; // rax
  __int64 v32; // rbx
  Gre::Base *v33; // rcx
  struct Gre::Base::SESSION_GLOBALS *v34; // rax
  __int64 v36; // rax
  float *v37; // r10
  unsigned __int64 v38; // rbx
  int v39; // r11d
  void *v40; // rdx
  int v41; // r8d
  ULONG v42; // ecx
  int v43; // r11d
  int v44; // r8d
  int v45; // ecx
  int v46; // eax
  bool v47; // zf
  int v48; // eax
  char v49; // [rsp+30h] [rbp-50h]
  int v50; // [rsp+34h] [rbp-4Ch]
  int v51; // [rsp+38h] [rbp-48h]
  int v52; // [rsp+3Ch] [rbp-44h]
  struct Gre::Base::SESSION_GLOBALS *v53; // [rsp+40h] [rbp-40h]
  __int64 v54; // [rsp+48h] [rbp-38h] BYREF
  int v55; // [rsp+50h] [rbp-30h]
  _OWORD v56[2]; // [rsp+58h] [rbp-28h] BYREF
  int v57; // [rsp+C0h] [rbp+40h]

  v57 = (int)a1;
  v11 = (unsigned __int8)a1 & 0xF;
  v13 = -a2;
  v14 = (int)a1;
  if ( a2 > 0 )
    v13 = a2;
  if ( ((unsigned int)a1 & 0xFFF000F0) != 0 )
    v15 = 1;
  else
    v15 = (unsigned int)v13 >> 31;
  v16 = Gre::Base::Globals(a1);
  v53 = v16;
  if ( v11 == 5 )
    return *(_QWORD *)(*((_QWORD *)v16 + 386) + 64LL);
  v17 = 0;
  v50 = 0;
  v18 = v14 & 0xF0000;
  v52 = v14 & 0xF0000;
  if ( (v14 & 0xF0000) != 0 )
  {
    if ( v18 != 0x10000 )
LABEL_117:
      v15 = 1;
  }
  else if ( a3 && (a3 != 2 || ((unsigned __int64)(a6 - 4) & 0xFFFFFFFFFFFFFFFDuLL) != 0) )
  {
    goto LABEL_117;
  }
  if ( v13 != 1 && !v18 && !a10 )
    v15 = 1;
  v19 = v14 & 0xF000;
  if ( (v14 & 0xF000) == 0 )
    goto LABEL_10;
  if ( v19 == 0x2000 )
  {
    v49 = 2;
  }
  else
  {
    if ( v19 != 4096 )
    {
      v15 = 1;
LABEL_10:
      v49 = 0;
      goto LABEL_11;
    }
    v49 = 1;
  }
LABEL_11:
  v20 = v14 & 0xF00;
  if ( (v14 & 0xF00) == 0 )
  {
LABEL_12:
    v51 = 0;
    goto LABEL_13;
  }
  if ( v20 == 512 )
  {
    v51 = 2;
  }
  else
  {
    if ( v20 != 256 )
    {
      v15 = 1;
      goto LABEL_12;
    }
    v51 = 1;
  }
LABEL_13:
  v21 = a7;
  if ( v11 == 7 )
  {
    if ( a7 )
    {
LABEL_15:
      if ( a7 <= 0x10 )
        goto LABEL_16;
    }
  }
  else if ( !a7 )
  {
    goto LABEL_15;
  }
  v15 = 1;
LABEL_16:
  v22 = 6;
  if ( v18 == 0x10000 )
  {
    switch ( v11 )
    {
      case 0:
        goto LABEL_18;
      case 1:
        v21 = 2;
        a8 = &qword_140352A98;
        goto LABEL_18;
      case 2:
        v21 = 2;
        a8 = qword_140352AA0;
        goto LABEL_18;
      case 3:
        v21 = 4;
        a8 = qword_140352A70;
        goto LABEL_18;
      case 4:
        v21 = 6;
        a8 = qword_140352A80;
        goto LABEL_18;
    }
    v48 = v11 - 6;
    v47 = v11 == 6;
  }
  else
  {
    switch ( v11 )
    {
      case 0:
        goto LABEL_18;
      case 1:
        v21 = 2;
        v17 = &qword_140363A20;
        goto LABEL_98;
      case 2:
        v21 = 8;
        v17 = qword_140352650;
LABEL_98:
        v50 = 1;
        goto LABEL_18;
      case 3:
        v21 = 4;
        v17 = qword_140363A40;
        goto LABEL_98;
      case 4:
        v21 = 6;
        v17 = qword_140363A28;
        goto LABEL_98;
      case 6:
        if ( !a10 )
          v15 = 1;
        goto LABEL_18;
    }
    v48 = v11 - 7;
    v47 = v11 == 7;
  }
  if ( !v47 && v48 != 1 )
    goto LABEL_70;
LABEL_18:
  if ( v15 )
  {
LABEL_70:
    v42 = 87;
LABEL_71:
    EngSetLastError(v42);
    return 0;
  }
  if ( !v21 || v17 )
    goto LABEL_20;
  if ( !(4 * v21) || (v36 = Win32AllocPool(4 * v21, 2037674823, 2), (v17 = (__int64 *)v36) == 0) )
  {
    v42 = 8;
    goto LABEL_71;
  }
  v37 = (float *)v36;
  v38 = v36 + 4LL * v21;
  if ( v18 && !a10 )
  {
    v39 = 0;
    v22 = 0;
    v40 = (void *)v36;
    if ( a8 )
    {
      while ( (unsigned __int64)v37 < v38 )
      {
        v41 = *(_DWORD *)a8;
        if ( v11 != 7 )
        {
          if ( v51 != 2 )
            v41 += (((_BYTE)v37 - (_BYTE)v36) & 4) != 0 ? 1 : -1;
          v41 *= v13;
        }
        if ( (int)v22 >= v41 )
          v22 = (unsigned int)v41;
        v39 += v41;
        *v37++ = (float)v41;
        a8 = (__int64 *)((char *)a8 + 4);
        if ( !a8 )
          goto LABEL_69;
      }
      if ( (int)v22 >= 0 && v39 > 0 )
        goto LABEL_20;
    }
    goto LABEL_69;
  }
  v43 = 0;
  v22 = 1;
  v44 = 1;
  if ( !a8 )
  {
    v40 = (void *)v36;
LABEL_69:
    Win32FreePool(v40);
    goto LABEL_70;
  }
  while ( 1 )
  {
    v40 = (void *)v36;
    if ( (unsigned __int64)v37 >= v38 )
      break;
    v45 = *(_DWORD *)a8;
    v43 += *(_DWORD *)a8;
    v46 = *(_DWORD *)a8;
    *v37++ = *(float *)a8;
    if ( v44 < v45 )
      v46 = v44;
    v44 = v46;
    v36 = (__int64)v40;
    if ( (int)v22 > v45 )
      v45 = v22;
    v22 = (unsigned int)v45;
    a8 = (__int64 *)((char *)a8 + 4);
    if ( !a8 )
      goto LABEL_69;
  }
  if ( v44 <= 0 || (int)v22 > 0x3FFF || v43 > 0x3FFF )
    goto LABEL_69;
LABEL_20:
  switch ( a3 )
  {
    case 0:
      v24 = !v13 && !v11;
      SolidBrushInternal = (HBRUSH)hCreateSolidBrushInternal(a4, 1, a11, v24);
      break;
    case 1:
      if ( v17 && !v50 )
        Win32FreePool(v17);
      v16 = v53;
      return *(_QWORD *)(*((_QWORD *)v16 + 386) + 64LL);
    case 2:
      SolidBrushInternal = hCreateHatchBrushInternal((unsigned int)a6, a4, 1);
      break;
    case 3:
      SolidBrushInternal = (HBRUSH)GreCreatePatternBrushInternal(a6, 1, 0, v22);
      break;
    case 6:
      SolidBrushInternal = (HBRUSH)GreCreateDIBBrush(a6, a4, a9, 0, 1, a5);
      break;
    default:
      EngSetLastError(0x57u);
      goto LABEL_80;
  }
  v26 = SolidBrushInternal;
  if ( !SolidBrushInternal )
  {
LABEL_80:
    if ( v17 && !v50 )
      Win32FreePool(v17);
    return 0;
  }
  v55 = 0;
  memset(v56, 0, sizeof(v56));
  PushThreadGuardedObject(v56, &v54, EPALOBJ::~EPALOBJ);
  v28 = Gre::Base::Globals(v27);
  LOBYTE(v29) = 16;
  v30 = v28;
  v54 = HmgShareLock(v28, v26, v29, 0);
  if ( !v54
    || (!(unsigned int)XEBRUSHOBJ::bSaveAttributes((XEBRUSHOBJ *)&v54)
      ? (DEC_SHARE_REF_CNT(v30, v54), v31 = 0, v54 = 0)
      : (v31 = v54),
        !v31) )
  {
    if ( v17 && !v50 )
      Win32FreePool(v17);
    BRUSHSELOBJ::~BRUSHSELOBJ((BRUSHSELOBJ *)&v54);
    return 0;
  }
  *(_DWORD *)(v31 + 40) |= 0x400u;
  *(_DWORD *)(v54 + 176) = v57;
  *(_BYTE *)(v54 + 185) = v51;
  *(_BYTE *)(v54 + 184) = v49;
  *(_QWORD *)(v54 + 152) = v17;
  *(_DWORD *)(v54 + 180) = v21;
  *(_DWORD *)(v54 + 168) = v13;
  if ( v50 )
    *(_DWORD *)(v54 + 40) |= 0x4000u;
  *(_DWORD *)(v54 + 188) = a3;
  *(_QWORD *)(v54 + 160) = a5;
  if ( (a10 || v52 == 0x10000) && (*(float *)(v54 + 172) = (float)v13, a10) )
  {
    *(_DWORD *)(v54 + 40) |= 0xC00u;
    *(_DWORD *)(v54 + 40) &= ~4u;
    if ( v11 == 6 )
    {
      *(_DWORD *)(v54 + 40) |= 4u;
      *(_DWORD *)(v54 + 40) |= 0x10000u;
    }
    v32 = (unsigned __int64)v26 | 0x300000;
  }
  else
  {
    v32 = (unsigned __int64)v26 | 0x500000;
    if ( v52 )
    {
      if ( v11 == 6 )
        *(_DWORD *)(v54 + 40) |= 0x10000u;
    }
    else
    {
      *(_DWORD *)(v54 + 40) &= ~4u;
    }
  }
  HmgModifyHandleType(v32, 0x10000);
  if ( v54 )
  {
    XEBRUSHOBJ::RestoreAttributes((XEBRUSHOBJ *)&v54);
    v34 = Gre::Base::Globals(v33);
    DEC_SHARE_REF_CNT(v34, v54);
  }
  PopThreadGuardedObject(v56);
  return v32;
}

```

## disassembly

```asm
0x1400899a8  mov     rax, rsp
0x1400899ab  mov     [rax+10h], rbx
0x1400899af  mov     [rax+20h], r9d
0x1400899b3  mov     [rax+18h], r8d
0x1400899b7  mov     [rax+8], ecx
0x1400899ba  push    rbp
0x1400899bb  push    rsi
0x1400899bc  push    rdi
0x1400899bd  push    r12
0x1400899bf  push    r13
0x1400899c1  push    r14
0x1400899c3  push    r15
0x1400899c5  mov     rbp, rsp
0x1400899c8  sub     rsp, 80h
0x1400899cf  mov     r12d, ecx
0x1400899d2  mov     r13d, edx
0x1400899d5  and     r12d, 0Fh
0x1400899d9  mov     r14d, r8d
0x1400899dc  neg     r13d
0x1400899df  mov     esi, ecx
0x1400899e1  mov     r9d, 1
0x1400899e7  cmovs   r13d, edx
0x1400899eb  test    ecx, 0FFF000F0h
0x1400899f1  jz      loc_140089CCC
0x1400899f7  mov     ebx, r9d
0x1400899fa  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140089a01  nop     dword ptr [rax+rax+00h]
0x140089a06  mov     [rbp+var_40], rax
0x140089a0a  cmp     r12d, 5
0x140089a0e  jz      loc_140089D8A
0x140089a14  xor     edi, edi
0x140089a16  mov     [rbp+var_4C], 0
0x140089a1d  mov     r15d, esi
0x140089a20  mov     r10d, 10000h
0x140089a26  and     r15d, 0F0000h
0x140089a2d  mov     [rbp+var_44], r15d
0x140089a31  lea     r8d, [rdi+2]
0x140089a35  jnz     loc_140089CED
0x140089a3b  test    r14d, r14d
0x140089a3e  jnz     loc_140089FFA
0x140089a44  mov     edx, 1
0x140089a49  mov     ecx, [rbp+arg_48]
0x140089a4f  cmp     r13d, edx
0x140089a52  jnz     loc_140089EE0
0x140089a58  mov     eax, esi
0x140089a5a  and     eax, 0F000h
0x140089a5f  jnz     loc_140089F1C
0x140089a65  mov     [rbp+var_50], dil
0x140089a69  mov     eax, esi
0x140089a6b  and     eax, 0F00h
0x140089a70  jnz     loc_140089EF3
0x140089a76  mov     [rbp+var_48], edi
0x140089a79  mov     r14d, [rbp+arg_30]
0x140089a7d  cmp     r12d, 7
0x140089a81  jz      loc_14008A0A4
0x140089a87  test    r14d, r14d
0x140089a8a  jnz     loc_14008A0AD
0x140089a90  cmp     r14d, 10h
0x140089a94  ja      loc_14008A0AD
0x140089a9a  mov     r9d, 6
0x140089aa0  mov     eax, r12d
0x140089aa3  cmp     r15d, r10d
0x140089aa6  jz      loc_140089E6F
0x140089aac  test    r12d, r12d
0x140089aaf  jnz     loc_140089F43
0x140089ab5  mov     rsi, [rbp+arg_38]
0x140089ab9  test    ebx, ebx
0x140089abb  jnz     loc_140089E46
0x140089ac1  test    r14d, r14d
0x140089ac4  jnz     loc_140089D9A
0x140089aca  mov     eax, [rbp+arg_10]
0x140089acd  mov     r15, [rbp+arg_20]
0x140089ad1  test    eax, eax
0x140089ad3  jnz     loc_140089D1F
0x140089ad9  test    r13d, r13d
0x140089adc  jz      loc_140089FC0
0x140089ae2  xor     r9d, r9d
0x140089ae5  mov     r8, [rbp+arg_50]
0x140089aec  mov     ecx, [rbp+arg_18]
0x140089aef  call    cs:__imp_hCreateSolidBrushInternal
0x140089af6  nop     dword ptr [rax+rax+00h]
0x140089afb  mov     rbx, rax
0x140089afe  test    rax, rax
0x140089b01  jz      loc_140089EB9
0x140089b07  xorps   xmm0, xmm0
0x140089b0a  mov     [rbp+var_30], 0
0x140089b11  lea     r8, ??1EPALOBJ@@QEAA@XZ; EPALOBJ::~EPALOBJ(void)
0x140089b18  lea     rdx, [rbp+var_38]
0x140089b1c  lea     rcx, [rbp+var_28]
0x140089b20  movups  [rbp+var_28], xmm0
0x140089b24  movups  [rbp+var_18], xmm0
0x140089b28  call    cs:__imp_PushThreadGuardedObject
0x140089b2f  nop     dword ptr [rax+rax+00h]
0x140089b34  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140089b3b  nop     dword ptr [rax+rax+00h]
0x140089b40  xor     r9d, r9d
0x140089b43  mov     r8b, 10h
0x140089b46  mov     rcx, rax
0x140089b49  mov     rdx, rbx
0x140089b4c  mov     rsi, rax
0x140089b4f  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140089b56  nop     dword ptr [rax+rax+00h]
0x140089b5b  mov     [rbp+var_38], rax
0x140089b5f  test    rax, rax
0x140089b62  jz      loc_140089CD7
0x140089b68  lea     rcx, [rbp+var_38]; this
0x140089b6c  call    ?bSaveAttributes@XEBRUSHOBJ@@IEAAHXZ; XEBRUSHOBJ::bSaveAttributes(void)
0x140089b71  test    eax, eax
0x140089b73  jz      loc_14008A14F
0x140089b79  mov     rax, [rbp+var_38]
0x140089b7d  test    rax, rax
0x140089b80  jz      loc_140089CD7
0x140089b86  bts     dword ptr [rax+28h], 0Ah
0x140089b8b  cmp     [rbp+var_4C], 0
0x140089b8f  mov     rax, [rbp+var_38]
0x140089b93  mov     ecx, [rbp+arg_0]
0x140089b96  mov     [rax+0B0h], ecx
0x140089b9c  mov     rax, [rbp+var_38]
0x140089ba0  mov     ecx, [rbp+var_48]
0x140089ba3  mov     [rax+0B9h], cl
0x140089ba9  mov     rax, [rbp+var_38]
0x140089bad  mov     cl, [rbp+var_50]
0x140089bb0  mov     [rax+0B8h], cl
0x140089bb6  mov     rax, [rbp+var_38]
0x140089bba  mov     [rax+98h], rdi
0x140089bc1  mov     rax, [rbp+var_38]
0x140089bc5  mov     [rax+0B4h], r14d
0x140089bcc  mov     rax, [rbp+var_38]
0x140089bd0  mov     [rax+0A8h], r13d
0x140089bd7  jz      short loc_140089BE2
0x140089bd9  mov     rax, [rbp+var_38]
0x140089bdd  bts     dword ptr [rax+28h], 0Eh
0x140089be2  cmp     [rbp+arg_48], 0
0x140089be9  mov     edx, 10000h
0x140089bee  mov     rax, [rbp+var_38]
0x140089bf2  mov     ecx, [rbp+arg_10]
0x140089bf5  mov     [rax+0BCh], ecx
0x140089bfb  mov     rax, [rbp+var_38]
0x140089bff  mov     ecx, [rbp+var_44]
0x140089c02  mov     [rax+0A0h], r15
0x140089c09  jz      loc_140089CFB
0x140089c0f  cmp     [rbp+arg_48], 0
0x140089c16  mov     rax, [rbp+var_38]
0x140089c1a  movd    xmm0, r13d
0x140089c1f  cvtdq2ps xmm0, xmm0
0x140089c22  movss   dword ptr [rax+0ACh], xmm0
0x140089c2a  jz      loc_140089D03
0x140089c30  mov     rax, [rbp+var_38]
0x140089c34  or      dword ptr [rax+28h], 0C00h
0x140089c3b  mov     rax, [rbp+var_38]
0x140089c3f  and     dword ptr [rax+28h], 0FFFFFFFBh
0x140089c43  cmp     r12d, 6
0x140089c47  jnz     short loc_140089C58
0x140089c49  mov     rax, [rbp+var_38]
0x140089c4d  or      dword ptr [rax+28h], 4
0x140089c51  mov     rax, [rbp+var_38]
0x140089c55  or      [rax+28h], edx
0x140089c58  or      rbx, 300000h
0x140089c5f  mov     rcx, rbx
0x140089c62  call    cs:__imp_HmgModifyHandleType
0x140089c69  nop     dword ptr [rax+rax+00h]
0x140089c6e  cmp     [rbp+var_38], 0
0x140089c73  jz      short loc_140089C9D
0x140089c75  lea     rcx, [rbp+var_38]; this
0x140089c79  call    ?RestoreAttributes@XEBRUSHOBJ@@IEAAXXZ; XEBRUSHOBJ::RestoreAttributes(void)
0x140089c7e  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140089c85  nop     dword ptr [rax+rax+00h]
0x140089c8a  mov     rdx, [rbp+var_38]
0x140089c8e  mov     rcx, rax
0x140089c91  call    cs:__imp_DEC_SHARE_REF_CNT
0x140089c98  nop     dword ptr [rax+rax+00h]
0x140089c9d  lea     rcx, [rbp+var_28]
0x140089ca1  call    cs:__imp_PopThreadGuardedObject
0x140089ca8  nop     dword ptr [rax+rax+00h]
0x140089cad  mov     rax, rbx
0x140089cb0  mov     rbx, [rsp+80h+arg_8]
0x140089cb8  add     rsp, 80h
0x140089cbf  pop     r15
0x140089cc1  pop     r14
0x140089cc3  pop     r13
0x140089cc5  pop     r12
0x140089cc7  pop     rdi
0x140089cc8  pop     rsi
0x140089cc9  pop     rbp
0x140089cca  retn
0x140089ccc  mov     ebx, r13d
0x140089ccf  shr     ebx, 1Fh
0x140089cd2  jmp     loc_1400899FA
0x140089cd7  test    rdi, rdi
0x140089cda  jnz     loc_14008A16D
0x140089ce0  lea     rcx, [rbp+var_38]; this
0x140089ce4  call    ??1BRUSHSELOBJ@@QEAA@XZ; BRUSHSELOBJ::~BRUSHSELOBJ(void)
0x140089ce9  xor     eax, eax
0x140089ceb  jmp     short loc_140089CB0
0x140089ced  cmp     r15d, r10d
0x140089cf0  jz      loc_140089A44
0x140089cf6  jmp     loc_14008A013
0x140089cfb  cmp     ecx, edx
0x140089cfd  jz      loc_140089C0F
0x140089d03  or      rbx, 500000h
0x140089d0a  test    ecx, ecx
0x140089d0c  jnz     loc_140089EA3
0x140089d12  mov     rax, [rbp+var_38]
0x140089d16  and     dword ptr [rax+28h], 0FFFFFFFBh
0x140089d1a  jmp     loc_140089C5F
0x140089d1f  sub     eax, 1
0x140089d22  jz      short loc_140089D6C
0x140089d24  sub     eax, 1
0x140089d27  jz      loc_140089E5C
0x140089d2d  sub     eax, 1
0x140089d30  jz      loc_14008A137
0x140089d36  sub     eax, r8d
0x140089d39  jz      loc_14008A121
0x140089d3f  cmp     eax, 1
0x140089d42  jnz     loc_14008A121
0x140089d48  mov     r8d, [rbp+arg_40]; unsigned int
0x140089d4f  xor     r9d, r9d; int
0x140089d52  mov     rcx, [rbp+arg_28]; void *
0x140089d56  mov     [rsp+80h+var_58], r15; void *
0x140089d5b  mov     [rsp+80h+var_60], edx; int
0x140089d5f  mov     edx, [rbp+arg_18]; unsigned int
0x140089d62  call    ?GreCreateDIBBrush@@YAPEAUHBRUSH__@@PEAXKIHH0@Z; GreCreateDIBBrush(void *,ulong,uint,int,int,void *)
0x140089d67  jmp     loc_140089AFB
0x140089d6c  test    rdi, rdi
0x140089d6f  jz      short loc_140089D86
0x140089d71  cmp     [rbp+var_4C], 0
0x140089d75  jnz     short loc_140089D86
0x140089d77  mov     rcx, rdi
0x140089d7a  call    cs:__imp_Win32FreePool
0x140089d81  nop     dword ptr [rax+rax+00h]
0x140089d86  mov     rax, [rbp+var_40]
0x140089d8a  mov     rax, [rax+0C10h]
0x140089d91  mov     rax, [rax+40h]
0x140089d95  jmp     loc_140089CB0
0x140089d9a  test    rdi, rdi
0x140089d9d  jnz     loc_140089ACA
0x140089da3  lea     eax, ds:0[r14*4]
0x140089dab  test    eax, eax
0x140089dad  jz      loc_140089F68
0x140089db3  mov     ecx, eax
0x140089db5  mov     edx, 79747347h
0x140089dba  call    cs:__imp_Win32AllocPool
0x140089dc1  nop     dword ptr [rax+rax+00h]
0x140089dc6  mov     rdi, rax
0x140089dc9  test    rax, rax
0x140089dcc  jz      loc_140089F68
0x140089dd2  mov     r10, rax
0x140089dd5  mov     eax, r14d
0x140089dd8  lea     rbx, [r10+rax*4]
0x140089ddc  test    r15d, r15d
0x140089ddf  jz      loc_140089F03
0x140089de5  cmp     [rbp+arg_48], 0
0x140089dec  jnz     loc_140089F03
0x140089df2  xor     r11d, r11d
0x140089df5  xor     r9d, r9d
0x140089df8  mov     rdx, r10
0x140089dfb  test    rsi, rsi
0x140089dfe  jz      short loc_140089E37
0x140089e00  cmp     r10, rbx
0x140089e03  jnb     loc_14008A083
0x140089e09  mov     r8d, [rsi]
0x140089e0c  cmp     r12d, 7
0x140089e10  jnz     loc_140089FD8
0x140089e16  cmp     r9d, r8d
0x140089e19  movd    xmm0, r8d
0x140089e1e  cvtdq2ps xmm0, xmm0
0x140089e21  cmovge  r9d, r8d
0x140089e25  add     r11d, r8d
0x140089e28  movss   dword ptr [r10], xmm0
0x140089e2d  add     r10, 4
0x140089e31  add     rsi, 4
0x140089e35  jnz     short loc_140089E00
0x140089e37  mov     rcx, rdx
0x140089e3a  call    cs:__imp_Win32FreePool
0x140089e41  nop     dword ptr [rax+rax+00h]
0x140089e46  mov     ecx, 57h ; 'W'; iError
0x140089e4b  call    cs:__imp_EngSetLastError
0x140089e52  nop     dword ptr [rax+rax+00h]
0x140089e57  jmp     loc_140089CE9
0x140089e5c  mov     ecx, dword ptr [rbp+arg_28]; unsigned int
0x140089e5f  mov     r8d, edx; int
0x140089e62  mov     edx, [rbp+arg_18]; unsigned int
0x140089e65  call    ?hCreateHatchBrushInternal@@YAPEAUHBRUSH__@@KKH@Z; hCreateHatchBrushInternal(ulong,ulong,int)
0x140089e6a  jmp     loc_140089AFB
0x140089e6f  test    r12d, r12d
0x140089e72  jz      loc_140089AB5
0x140089e78  sub     eax, 1
0x140089e7b  jz      loc_14008A04E
0x140089e81  sub     eax, 1
0x140089e84  jz      loc_14008A03F
0x140089e8a  sub     eax, 1
0x140089e8d  jnz     loc_14008A027
0x140089e93  lea     r14d, [rax+4]
0x140089e97  lea     rsi, qword_140352A70
0x140089e9e  jmp     loc_140089AB9
0x140089ea3  cmp     r12d, 6
0x140089ea7  jnz     loc_140089C5F
0x140089ead  mov     rax, [rbp+var_38]
0x140089eb1  or      [rax+28h], edx
0x140089eb4  jmp     loc_140089C5F
  ... truncated ...
```
