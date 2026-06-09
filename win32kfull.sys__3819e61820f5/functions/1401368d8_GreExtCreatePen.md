# GreExtCreatePen

- ea: `0x1401368d8`
- end: `0x1401370bb`
- name: `GreExtCreatePen`
- size: `2019`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140136270`
- `0x1401367c0`
- `0x140136854`

## callees

- `0x1401366b4`
- `0x1401368d8`
- `0x1401370c4`
- `0x14013714c`
- `0x14013723c`
- `0x140289980`

## import_xrefs

- `win32kbase!Win32AllocPool` at `0x140136cea`
- `win32kbase!Win32AllocPool` at `0x140136cea`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14013692a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140136a64`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140136bae`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14013692a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140136a64`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140136bae`
- `win32kbase!HmgShareLock` at `0x140136a7f`
- `win32kbase!HmgShareLock` at `0x140136a7f`
- `win32kbase!PopThreadGuardedObject` at `0x140136bd1`
- `win32kbase!PopThreadGuardedObject` at `0x140136bd1`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140136bc1`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140137086`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140136bc1`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140137086`
- `win32kbase!PushThreadGuardedObject` at `0x140136a58`
- `win32kbase!PushThreadGuardedObject` at `0x140136a58`
- `win32kbase!EngSetLastError` at `0x140136d7b`
- `win32kbase!EngSetLastError` at `0x140137056`
- `win32kbase!EngSetLastError` at `0x140136d7b`
- `win32kbase!EngSetLastError` at `0x140137056`
- `win32kbase!HmgModifyHandleType` at `0x140136b92`
- `win32kbase!HmgModifyHandleType` at `0x140136b92`
- `win32kbase!hCreateSolidBrushInternal` at `0x140136a1f`
- `win32kbase!hCreateSolidBrushInternal` at `0x140136a1f`
- `win32kbase!GreCreatePatternBrushInternal` at `0x14013706e`
- `win32kbase!GreCreatePatternBrushInternal` at `0x14013706e`
- `win32kbase!Win32FreePool` at `0x140136caa`
- `win32kbase!Win32FreePool` at `0x140136d6a`
- `win32kbase!Win32FreePool` at `0x140136dff`
- `win32kbase!Win32FreePool` at `0x1401370aa`
- `win32kbase!Win32FreePool` at `0x140136caa`
- `win32kbase!Win32FreePool` at `0x140136d6a`
- `win32kbase!Win32FreePool` at `0x140136dff`
- `win32kbase!Win32FreePool` at `0x1401370aa`

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
        a8 = &qword_1403539B0;
        goto LABEL_18;
      case 2:
        v21 = 2;
        a8 = &qword_1403539B8;
        goto LABEL_18;
      case 3:
        v21 = 4;
        a8 = qword_140353988;
        goto LABEL_18;
      case 4:
        v21 = 6;
        a8 = qword_140353998;
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
        v17 = qword_140362AC0;
        goto LABEL_98;
      case 2:
        v21 = 8;
        v17 = qword_140353968;
LABEL_98:
        v50 = 1;
        goto LABEL_18;
      case 3:
        v21 = 4;
        v17 = qword_140362AB0;
        goto LABEL_98;
      case 4:
        v21 = 6;
        v17 = qword_140362A98;
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
0x1401368d8  mov     rax, rsp
0x1401368db  mov     [rax+10h], rbx
0x1401368df  mov     [rax+20h], r9d
0x1401368e3  mov     [rax+18h], r8d
0x1401368e7  mov     [rax+8], ecx
0x1401368ea  push    rbp
0x1401368eb  push    rsi
0x1401368ec  push    rdi
0x1401368ed  push    r12
0x1401368ef  push    r13
0x1401368f1  push    r14
0x1401368f3  push    r15
0x1401368f5  mov     rbp, rsp
0x1401368f8  sub     rsp, 80h
0x1401368ff  mov     r12d, ecx
0x140136902  mov     r13d, edx
0x140136905  and     r12d, 0Fh
0x140136909  mov     r14d, r8d
0x14013690c  neg     r13d
0x14013690f  mov     esi, ecx
0x140136911  mov     r9d, 1
0x140136917  cmovs   r13d, edx
0x14013691b  test    ecx, 0FFF000F0h
0x140136921  jz      loc_140136BFC
0x140136927  mov     ebx, r9d
0x14013692a  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140136931  nop     dword ptr [rax+rax+00h]
0x140136936  mov     [rbp+var_40], rax
0x14013693a  cmp     r12d, 5
0x14013693e  jz      loc_140136CBA
0x140136944  xor     edi, edi
0x140136946  mov     [rbp+var_4C], 0
0x14013694d  mov     r15d, esi
0x140136950  mov     r10d, 10000h
0x140136956  and     r15d, 0F0000h
0x14013695d  mov     [rbp+var_44], r15d
0x140136961  lea     r8d, [rdi+2]
0x140136965  jnz     loc_140136C1D
0x14013696b  test    r14d, r14d
0x14013696e  jnz     loc_140136F2A
0x140136974  mov     edx, 1
0x140136979  mov     ecx, [rbp+arg_48]
0x14013697f  cmp     r13d, edx
0x140136982  jnz     loc_140136E10
0x140136988  mov     eax, esi
0x14013698a  and     eax, 0F000h
0x14013698f  jnz     loc_140136E4C
0x140136995  mov     [rbp+var_50], dil
0x140136999  mov     eax, esi
0x14013699b  and     eax, 0F00h
0x1401369a0  jnz     loc_140136E23
0x1401369a6  mov     [rbp+var_48], edi
0x1401369a9  mov     r14d, [rbp+arg_30]
0x1401369ad  cmp     r12d, 7
0x1401369b1  jz      loc_140136FD4
0x1401369b7  test    r14d, r14d
0x1401369ba  jnz     loc_140136FDD
0x1401369c0  cmp     r14d, 10h
0x1401369c4  ja      loc_140136FDD
0x1401369ca  mov     r9d, 6
0x1401369d0  mov     eax, r12d
0x1401369d3  cmp     r15d, r10d
0x1401369d6  jz      loc_140136D9F
0x1401369dc  test    r12d, r12d
0x1401369df  jnz     loc_140136E73
0x1401369e5  mov     rsi, [rbp+arg_38]
0x1401369e9  test    ebx, ebx
0x1401369eb  jnz     loc_140136D76
0x1401369f1  test    r14d, r14d
0x1401369f4  jnz     loc_140136CCA
0x1401369fa  mov     eax, [rbp+arg_10]
0x1401369fd  mov     r15, [rbp+arg_20]
0x140136a01  test    eax, eax
0x140136a03  jnz     loc_140136C4F
0x140136a09  test    r13d, r13d
0x140136a0c  jz      loc_140136EF0
0x140136a12  xor     r9d, r9d
0x140136a15  mov     r8, [rbp+arg_50]
0x140136a1c  mov     ecx, [rbp+arg_18]
0x140136a1f  call    cs:__imp_hCreateSolidBrushInternal
0x140136a26  nop     dword ptr [rax+rax+00h]
0x140136a2b  mov     rbx, rax
0x140136a2e  test    rax, rax
0x140136a31  jz      loc_140136DE9
0x140136a37  xorps   xmm0, xmm0
0x140136a3a  mov     [rbp+var_30], 0
0x140136a41  lea     r8, ??1EPALOBJ@@QEAA@XZ; EPALOBJ::~EPALOBJ(void)
0x140136a48  lea     rdx, [rbp+var_38]
0x140136a4c  lea     rcx, [rbp+var_28]
0x140136a50  movups  [rbp+var_28], xmm0
0x140136a54  movups  [rbp+var_18], xmm0
0x140136a58  call    cs:__imp_PushThreadGuardedObject
0x140136a5f  nop     dword ptr [rax+rax+00h]
0x140136a64  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140136a6b  nop     dword ptr [rax+rax+00h]
0x140136a70  xor     r9d, r9d
0x140136a73  mov     r8b, 10h
0x140136a76  mov     rcx, rax
0x140136a79  mov     rdx, rbx
0x140136a7c  mov     rsi, rax
0x140136a7f  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140136a86  nop     dword ptr [rax+rax+00h]
0x140136a8b  mov     [rbp+var_38], rax
0x140136a8f  test    rax, rax
0x140136a92  jz      loc_140136C07
0x140136a98  lea     rcx, [rbp+var_38]; this
0x140136a9c  call    ?bSaveAttributes@XEBRUSHOBJ@@IEAAHXZ; XEBRUSHOBJ::bSaveAttributes(void)
0x140136aa1  test    eax, eax
0x140136aa3  jz      loc_14013707F
0x140136aa9  mov     rax, [rbp+var_38]
0x140136aad  test    rax, rax
0x140136ab0  jz      loc_140136C07
0x140136ab6  bts     dword ptr [rax+28h], 0Ah
0x140136abb  cmp     [rbp+var_4C], 0
0x140136abf  mov     rax, [rbp+var_38]
0x140136ac3  mov     ecx, [rbp+arg_0]
0x140136ac6  mov     [rax+0B0h], ecx
0x140136acc  mov     rax, [rbp+var_38]
0x140136ad0  mov     ecx, [rbp+var_48]
0x140136ad3  mov     [rax+0B9h], cl
0x140136ad9  mov     rax, [rbp+var_38]
0x140136add  mov     cl, [rbp+var_50]
0x140136ae0  mov     [rax+0B8h], cl
0x140136ae6  mov     rax, [rbp+var_38]
0x140136aea  mov     [rax+98h], rdi
0x140136af1  mov     rax, [rbp+var_38]
0x140136af5  mov     [rax+0B4h], r14d
0x140136afc  mov     rax, [rbp+var_38]
0x140136b00  mov     [rax+0A8h], r13d
0x140136b07  jz      short loc_140136B12
0x140136b09  mov     rax, [rbp+var_38]
0x140136b0d  bts     dword ptr [rax+28h], 0Eh
0x140136b12  cmp     [rbp+arg_48], 0
0x140136b19  mov     edx, 10000h
0x140136b1e  mov     rax, [rbp+var_38]
0x140136b22  mov     ecx, [rbp+arg_10]
0x140136b25  mov     [rax+0BCh], ecx
0x140136b2b  mov     rax, [rbp+var_38]
0x140136b2f  mov     ecx, [rbp+var_44]
0x140136b32  mov     [rax+0A0h], r15
0x140136b39  jz      loc_140136C2B
0x140136b3f  cmp     [rbp+arg_48], 0
0x140136b46  mov     rax, [rbp+var_38]
0x140136b4a  movd    xmm0, r13d
0x140136b4f  cvtdq2ps xmm0, xmm0
0x140136b52  movss   dword ptr [rax+0ACh], xmm0
0x140136b5a  jz      loc_140136C33
0x140136b60  mov     rax, [rbp+var_38]
0x140136b64  or      dword ptr [rax+28h], 0C00h
0x140136b6b  mov     rax, [rbp+var_38]
0x140136b6f  and     dword ptr [rax+28h], 0FFFFFFFBh
0x140136b73  cmp     r12d, 6
0x140136b77  jnz     short loc_140136B88
0x140136b79  mov     rax, [rbp+var_38]
0x140136b7d  or      dword ptr [rax+28h], 4
0x140136b81  mov     rax, [rbp+var_38]
0x140136b85  or      [rax+28h], edx
0x140136b88  or      rbx, 300000h
0x140136b8f  mov     rcx, rbx
0x140136b92  call    cs:__imp_HmgModifyHandleType
0x140136b99  nop     dword ptr [rax+rax+00h]
0x140136b9e  cmp     [rbp+var_38], 0
0x140136ba3  jz      short loc_140136BCD
0x140136ba5  lea     rcx, [rbp+var_38]; this
0x140136ba9  call    ?RestoreAttributes@XEBRUSHOBJ@@IEAAXXZ; XEBRUSHOBJ::RestoreAttributes(void)
0x140136bae  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140136bb5  nop     dword ptr [rax+rax+00h]
0x140136bba  mov     rdx, [rbp+var_38]
0x140136bbe  mov     rcx, rax
0x140136bc1  call    cs:__imp_DEC_SHARE_REF_CNT
0x140136bc8  nop     dword ptr [rax+rax+00h]
0x140136bcd  lea     rcx, [rbp+var_28]
0x140136bd1  call    cs:__imp_PopThreadGuardedObject
0x140136bd8  nop     dword ptr [rax+rax+00h]
0x140136bdd  mov     rax, rbx
0x140136be0  mov     rbx, [rsp+80h+arg_8]
0x140136be8  add     rsp, 80h
0x140136bef  pop     r15
0x140136bf1  pop     r14
0x140136bf3  pop     r13
0x140136bf5  pop     r12
0x140136bf7  pop     rdi
0x140136bf8  pop     rsi
0x140136bf9  pop     rbp
0x140136bfa  retn
0x140136bfc  mov     ebx, r13d
0x140136bff  shr     ebx, 1Fh
0x140136c02  jmp     loc_14013692A
0x140136c07  test    rdi, rdi
0x140136c0a  jnz     loc_14013709D
0x140136c10  lea     rcx, [rbp+var_38]; this
0x140136c14  call    ??1BRUSHSELOBJ@@QEAA@XZ; BRUSHSELOBJ::~BRUSHSELOBJ(void)
0x140136c19  xor     eax, eax
0x140136c1b  jmp     short loc_140136BE0
0x140136c1d  cmp     r15d, r10d
0x140136c20  jz      loc_140136974
0x140136c26  jmp     loc_140136F43
0x140136c2b  cmp     ecx, edx
0x140136c2d  jz      loc_140136B3F
0x140136c33  or      rbx, 500000h
0x140136c3a  test    ecx, ecx
0x140136c3c  jnz     loc_140136DD3
0x140136c42  mov     rax, [rbp+var_38]
0x140136c46  and     dword ptr [rax+28h], 0FFFFFFFBh
0x140136c4a  jmp     loc_140136B8F
0x140136c4f  sub     eax, 1
0x140136c52  jz      short loc_140136C9C
0x140136c54  sub     eax, 1
0x140136c57  jz      loc_140136D8C
0x140136c5d  sub     eax, 1
0x140136c60  jz      loc_140137067
0x140136c66  sub     eax, r8d
0x140136c69  jz      loc_140137051
0x140136c6f  cmp     eax, 1
0x140136c72  jnz     loc_140137051
0x140136c78  mov     r8d, [rbp+arg_40]; unsigned int
0x140136c7f  xor     r9d, r9d; int
0x140136c82  mov     rcx, [rbp+arg_28]; void *
0x140136c86  mov     [rsp+80h+var_58], r15; void *
0x140136c8b  mov     [rsp+80h+var_60], edx; int
0x140136c8f  mov     edx, [rbp+arg_18]; unsigned int
0x140136c92  call    ?GreCreateDIBBrush@@YAPEAUHBRUSH__@@PEAXKIHH0@Z; GreCreateDIBBrush(void *,ulong,uint,int,int,void *)
0x140136c97  jmp     loc_140136A2B
0x140136c9c  test    rdi, rdi
0x140136c9f  jz      short loc_140136CB6
0x140136ca1  cmp     [rbp+var_4C], 0
0x140136ca5  jnz     short loc_140136CB6
0x140136ca7  mov     rcx, rdi
0x140136caa  call    cs:__imp_Win32FreePool
0x140136cb1  nop     dword ptr [rax+rax+00h]
0x140136cb6  mov     rax, [rbp+var_40]
0x140136cba  mov     rax, [rax+0C10h]
0x140136cc1  mov     rax, [rax+40h]
0x140136cc5  jmp     loc_140136BE0
0x140136cca  test    rdi, rdi
0x140136ccd  jnz     loc_1401369FA
0x140136cd3  lea     eax, ds:0[r14*4]
0x140136cdb  test    eax, eax
0x140136cdd  jz      loc_140136E98
0x140136ce3  mov     ecx, eax
0x140136ce5  mov     edx, 79747347h
0x140136cea  call    cs:__imp_Win32AllocPool
0x140136cf1  nop     dword ptr [rax+rax+00h]
0x140136cf6  mov     rdi, rax
0x140136cf9  test    rax, rax
0x140136cfc  jz      loc_140136E98
0x140136d02  mov     r10, rax
0x140136d05  mov     eax, r14d
0x140136d08  lea     rbx, [r10+rax*4]
0x140136d0c  test    r15d, r15d
0x140136d0f  jz      loc_140136E33
0x140136d15  cmp     [rbp+arg_48], 0
0x140136d1c  jnz     loc_140136E33
0x140136d22  xor     r11d, r11d
0x140136d25  xor     r9d, r9d
0x140136d28  mov     rdx, r10
0x140136d2b  test    rsi, rsi
0x140136d2e  jz      short loc_140136D67
0x140136d30  cmp     r10, rbx
0x140136d33  jnb     loc_140136FB3
0x140136d39  mov     r8d, [rsi]
0x140136d3c  cmp     r12d, 7
0x140136d40  jnz     loc_140136F08
0x140136d46  cmp     r9d, r8d
0x140136d49  movd    xmm0, r8d
0x140136d4e  cvtdq2ps xmm0, xmm0
0x140136d51  cmovge  r9d, r8d
0x140136d55  add     r11d, r8d
0x140136d58  movss   dword ptr [r10], xmm0
0x140136d5d  add     r10, 4
0x140136d61  add     rsi, 4
0x140136d65  jnz     short loc_140136D30
0x140136d67  mov     rcx, rdx
0x140136d6a  call    cs:__imp_Win32FreePool
0x140136d71  nop     dword ptr [rax+rax+00h]
0x140136d76  mov     ecx, 57h ; 'W'; iError
0x140136d7b  call    cs:__imp_EngSetLastError
0x140136d82  nop     dword ptr [rax+rax+00h]
0x140136d87  jmp     loc_140136C19
0x140136d8c  mov     ecx, dword ptr [rbp+arg_28]; unsigned int
0x140136d8f  mov     r8d, edx; int
0x140136d92  mov     edx, [rbp+arg_18]; unsigned int
0x140136d95  call    ?hCreateHatchBrushInternal@@YAPEAUHBRUSH__@@KKH@Z; hCreateHatchBrushInternal(ulong,ulong,int)
0x140136d9a  jmp     loc_140136A2B
0x140136d9f  test    r12d, r12d
0x140136da2  jz      loc_1401369E5
0x140136da8  sub     eax, 1
0x140136dab  jz      loc_140136F7E
0x140136db1  sub     eax, 1
0x140136db4  jz      loc_140136F6F
0x140136dba  sub     eax, 1
0x140136dbd  jnz     loc_140136F57
0x140136dc3  lea     r14d, [rax+4]
0x140136dc7  lea     rsi, qword_140353988
0x140136dce  jmp     loc_1401369E9
0x140136dd3  cmp     r12d, 6
0x140136dd7  jnz     loc_140136B8F
0x140136ddd  mov     rax, [rbp+var_38]
0x140136de1  or      [rax+28h], edx
0x140136de4  jmp     loc_140136B8F
  ... truncated ...
```
