# EngFillPath

- ea: `0x14006d850`
- end: `0x14006dd2b`
- name: `EngFillPath`
- size: `1243`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, BRUSHOBJ *pbo, POINTL *pptlBrushOrg, MIX mix, FLONG flOptions)`
- caller_count: `9`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006c818`
- `0x14006d4c8`
- `0x14006ff90`
- `0x1400f97f0`
- `0x1401d4be0`
- `0x1402a38d0`
- `0x1402a50d0`
- `0x14031ad00`
- `0x14032d118`

## callees

- `0x140069bc8`
- `0x14006d850`
- `0x14006dd34`
- `0x140077348`
- `0x14008cfa0`
- `0x140163094`
- `0x1401d5250`
- `0x140204768`
- `0x14022d39c`
- `0x140342fa0`

## import_xrefs

- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006da42`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006dac6`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006da42`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006dac6`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14006dab5`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14006dab5`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006db18`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006db45`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006dbfa`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006dcf3`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006db18`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006db45`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006dbfa`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14006dcf3`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006db07`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006db34`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006dbe9`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006dce2`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006db07`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006db34`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006dbe9`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14006dce2`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14006db83`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14006dc87`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14006db83`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14006dc87`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14006daee`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14006daee`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x14006d8dc`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x14006d8dc`
- `win32kbase!EngSetLastError` at `0x14006da67`
- `win32kbase!EngSetLastError` at `0x14006dc1a`
- `win32kbase!EngSetLastError` at `0x14006da67`
- `win32kbase!EngSetLastError` at `0x14006dc1a`
- `win32kbase!?bFlatten@EPATHOBJ@@QEAA_NXZ` at `0x14006d99b`
- `win32kbase!?bFlatten@EPATHOBJ@@QEAA_NXZ` at `0x14006d99b`
- `win32kbase!?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z` at `0x14006da27`
- `win32kbase!?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z` at `0x14006da27`

## pseudocode

```c
BOOL __stdcall EngFillPath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        BRUSHOBJ *pbo,
        POINTL *pptlBrushOrg,
        MIX mix,
        FLONG flOptions)
{
  BOOL v7; // ebx
  FLONG fl; // eax
  __int64 p_hdev; // rax
  RECTL *p_rclBounds; // r14
  int *v14; // rcx
  RECTL *v15; // r8
  BOOL result; // eax
  bool v17; // zf
  struct _RECTL *v18; // r9
  FLONG v19; // eax
  struct REGION *v20; // rax
  POINTL *v21; // r9
  BRUSHOBJ *v22; // r8
  BYTE v23; // dl
  __int64 v24; // rax
  struct REGION *v25; // r11
  POINTL *v26; // r9
  BRUSHOBJ *v27; // r8
  BYTE iDComplexity; // cl
  __int64 p_iUniq; // rax
  struct REGION *v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+48h] [rbp-B8h]
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  struct REGION *v33; // [rsp+58h] [rbp-A8h] BYREF
  POINTL *v34; // [rsp+60h] [rbp-A0h]
  BRUSHOBJ *pboa; // [rsp+68h] [rbp-98h]
  __int128 v36; // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+80h] [rbp-80h] BYREF
  RECTL v38; // [rsp+90h] [rbp-70h] BYREF
  CLIPOBJ pcoa; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+D8h] [rbp-28h]
  __int64 v41; // [rsp+F0h] [rbp-10h]
  int v42; // [rsp+F8h] [rbp-8h]
  int v43; // [rsp+120h] [rbp+20h]
  __int64 v44; // [rsp+130h] [rbp+30h]
  CLIPOBJ v45; // [rsp+140h] [rbp+40h] BYREF
  __int64 v46; // [rsp+178h] [rbp+78h]
  __int64 v47; // [rsp+190h] [rbp+90h]
  int v48; // [rsp+198h] [rbp+98h]
  int v49; // [rsp+1C0h] [rbp+C0h]
  __int64 v50; // [rsp+1D0h] [rbp+D0h]

  v7 = 1;
  v34 = pptlBrushOrg;
  fl = ppo->fl;
  pboa = pbo;
  if ( (fl & 1) != 0 && !EPATHOBJ::bFlatten((EPATHOBJ *)ppo) )
    return 0;
  p_hdev = (__int64)&pso->hdev;
  p_rclBounds = &pco->rclBounds;
  if ( !pso )
    p_hdev = 48;
  v33 = *(struct REGION **)p_hdev;
  if ( v33 )
    PDEVOBJ::vSync((PDEVOBJ *)&v33, pso, &pco->rclBounds, 0);
  if ( (ppo->fl & 0x4000) != 0 && (unsigned int)EPATHOBJ::bPreComputedFill((EPATHOBJ *)ppo) || pco->iDComplexity == 3 )
    goto LABEL_18;
  v14 = (int *)ppo[1];
  if ( p_rclBounds->left > v14[12] >> 4
    || pco->rclBounds.right < (int)((v14[14] + 15LL) >> 4)
    || pco->rclBounds.top > v14[13] >> 4
    || (v15 = 0, pco->rclBounds.bottom < (int)((v14[15] + 15LL) >> 4)) )
  {
    v15 = &pco->rclBounds;
  }
  result = EngFastFill(pso, ppo, v15, pboa, v34, mix, flOptions);
  if ( result < 0 )
  {
LABEL_18:
    v17 = pco->iDComplexity == 0;
    v36 = 0;
    if ( v17 )
    {
      v18 = 0;
    }
    else
    {
      v18 = (struct _RECTL *)&v36;
      DWORD1(v36) = 16 * pco->rclBounds.top;
      HIDWORD(v36) = 16 * pco->rclBounds.bottom;
    }
    v19 = ppo->fl;
    v31 = 0;
    if ( (v19 & 0x10) != 0 )
    {
      if ( flOptions == 2 )
        v20 = (struct REGION *)ppo[4];
      else
        v20 = (struct REGION *)ppo[3];
    }
    else
    {
      v20 = (struct REGION *)ppo[2];
    }
    v30 = v20;
    if ( v20
      || (v31 = 1,
          v33 = 0,
          RGNMEMOBJ::vCreate((RGNMEMOBJ *)&v33, (struct EPATHOBJ *)ppo, flOptions, v18),
          v30 = v33,
          RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v30),
          v30) )
    {
      if ( (unsigned int)RGNOBJ::iComplexity((RGNOBJ *)&v30) != 1 )
      {
        v38 = *p_rclBounds;
        if ( (unsigned int)EPATHOBJ::bPreComputedFill((EPATHOBJ *)ppo) || pco->iDComplexity )
        {
          v32 = 0;
          RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v32, 0x70u);
          RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v32);
          if ( !v32 )
          {
            EngSetLastError(8u);
            RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v32);
            goto LABEL_44;
          }
          if ( !RGNOBJ::bMerge((RGNOBJ *)&v32, (struct RGNOBJ *)&v30, (struct RGNOBJ *)&pco[2].rclBounds.top, 8u) )
          {
            RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v32);
            RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v32);
            if ( v31 )
            {
              RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v30);
              RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v30);
            }
            return 0;
          }
          v37 = *(_OWORD *)(v32 + 52);
          ERECTL::operator*=(&v37, &pco->rclBounds);
          v46 = 0;
          v47 = 0;
          v48 = 0;
          v49 = 1;
          v50 = 0;
          XCLIPOBJ::vSetup((XCLIPOBJ *)&v45, v25, (const struct ERECTL *)&v37, 0);
          if ( (unsigned int)ERECTL::bEmpty((ERECTL *)&v45.rclBounds) )
          {
            RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v32);
            goto LABEL_45;
          }
          v26 = v34;
          v27 = pboa;
          iDComplexity = v45.iDComplexity;
          if ( !v45.iDComplexity )
            iDComplexity = 1;
          v45.iDComplexity = iDComplexity;
          p_iUniq = (__int64)&pso->iUniq;
          if ( !pso )
            p_iUniq = 92;
          ++*(_DWORD *)p_iUniq;
          v7 = EngPaint(pso, &v45, v27, v26, mix);
          RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v32);
          RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v32);
        }
        else
        {
          v40 = 0;
          v41 = 0;
          v42 = 0;
          v43 = 1;
          v44 = 0;
          XCLIPOBJ::vSetup((XCLIPOBJ *)&pcoa, v30, (const struct ERECTL *)&v38, 0);
          if ( (unsigned int)ERECTL::bEmpty((ERECTL *)&pcoa.rclBounds) )
          {
LABEL_45:
            RGNMEMOBJTMPIFNEEDED::~RGNMEMOBJTMPIFNEEDED((RGNMEMOBJTMPIFNEEDED *)&v30);
            return v7;
          }
          v21 = v34;
          v22 = pboa;
          v23 = pcoa.iDComplexity;
          if ( !pcoa.iDComplexity )
            v23 = 1;
          pcoa.iDComplexity = v23;
          v24 = (__int64)&pso->iUniq;
          if ( !pso )
            v24 = 92;
          ++*(_DWORD *)v24;
          v7 = EngPaint(pso, &pcoa, v22, v21, mix);
        }
      }
    }
    else if ( ppo->cCurves >= 2 )
    {
      EngSetLastError(8u);
LABEL_44:
      v7 = 0;
      goto LABEL_45;
    }
    if ( v31 )
    {
      RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v30);
      RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v30);
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x14006d850  push    rbp
0x14006d852  push    rbx
0x14006d853  push    rsi
0x14006d854  push    rdi
0x14006d855  push    r12
0x14006d857  push    r13
0x14006d859  push    r14
0x14006d85b  push    r15
0x14006d85d  lea     rbp, [rsp-0F8h]
0x14006d865  sub     rsp, 1F8h
0x14006d86c  mov     rax, cs:__security_cookie
0x14006d873  xor     rax, rsp
0x14006d876  mov     [rbp+130h+var_50], rax
0x14006d87d  mov     rax, [rbp+130h+pptlBrushOrg]
0x14006d884  mov     ebx, 1
0x14006d889  mov     r12d, [rbp+130h+flOptions]
0x14006d890  mov     rsi, r8
0x14006d893  mov     [rsp+230h+var_1D0], rax
0x14006d898  mov     rdi, rdx
0x14006d89b  mov     eax, [rdx]
0x14006d89d  mov     r15, rcx
0x14006d8a0  mov     [rsp+230h+pbo], r9
0x14006d8a5  test    bl, al
0x14006d8a7  jnz     loc_14006D998
0x14006d8ad  test    r15, r15
0x14006d8b0  lea     rax, [r15+18h]
0x14006d8b4  mov     ecx, 30h ; '0'
0x14006d8b9  lea     r14, [rsi+4]
0x14006d8bd  cmovz   rax, rcx
0x14006d8c1  mov     rax, [rax]
0x14006d8c4  mov     [rsp+230h+var_1D8], rax
0x14006d8c9  test    rax, rax
0x14006d8cc  jz      short loc_14006D8E8
0x14006d8ce  xor     r9d, r9d
0x14006d8d1  lea     rcx, [rsp+230h+var_1D8]
0x14006d8d6  mov     r8, r14
0x14006d8d9  mov     rdx, r15
0x14006d8dc  call    cs:__imp_?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z; PDEVOBJ::vSync(_SURFOBJ *,_RECTL *,ulong)
0x14006d8e3  nop     dword ptr [rax+rax+00h]
0x14006d8e8  test    dword ptr [rdi], 4000h
0x14006d8ee  mov     r13d, [rbp+130h+mix]
0x14006d8f5  jnz     loc_14006D9B8
0x14006d8fb  cmp     byte ptr [rsi+14h], 3
0x14006d8ff  jz      loc_14006D9C8
0x14006d905  mov     rcx, [rdi+8]
0x14006d909  mov     eax, [rcx+30h]
0x14006d90c  sar     eax, 4
0x14006d90f  cmp     [r14], eax
0x14006d912  jg      loc_14006D9B3
0x14006d918  movsxd  rax, dword ptr [rcx+38h]
0x14006d91c  add     rax, 0Fh
0x14006d920  sar     rax, 4
0x14006d924  cmp     [rsi+0Ch], eax
0x14006d927  jl      loc_14006D9B3
0x14006d92d  mov     eax, [rcx+34h]
0x14006d930  sar     eax, 4
0x14006d933  cmp     [rsi+8], eax
0x14006d936  jg      short loc_14006D9B3
0x14006d938  movsxd  rax, dword ptr [rcx+3Ch]
0x14006d93c  xor     r8d, r8d; struct _RECTL *
0x14006d93f  add     rax, 0Fh
0x14006d943  sar     rax, 4
0x14006d947  cmp     [rsi+10h], eax
0x14006d94a  jl      short loc_14006D9B3
0x14006d94c  mov     rax, [rsp+230h+var_1D0]
0x14006d951  mov     rdx, rdi; struct _PATHOBJ *
0x14006d954  mov     r9, [rsp+230h+pbo]; struct _BRUSHOBJ *
0x14006d959  mov     rcx, r15; struct _SURFOBJ *
0x14006d95c  mov     [rsp+230h+var_200], r12d; unsigned int
0x14006d961  mov     [rsp+230h+var_208], r13d; unsigned int
0x14006d966  mov     qword ptr [rsp+230h+var_210], rax; struct _POINTL *
0x14006d96b  call    ?EngFastFill@@YAJPEAU_SURFOBJ@@PEAU_PATHOBJ@@PEAU_RECTL@@PEAU_BRUSHOBJ@@PEAU_POINTL@@KK@Z; EngFastFill(_SURFOBJ *,_PATHOBJ *,_RECTL *,_BRUSHOBJ *,_POINTL *,ulong,ulong)
0x14006d970  test    eax, eax
0x14006d972  js      short loc_14006D9C8
0x14006d974  mov     rcx, [rbp+130h+var_50]
0x14006d97b  xor     rcx, rsp; StackCookie
0x14006d97e  call    __security_check_cookie
0x14006d983  add     rsp, 1F8h
0x14006d98a  pop     r15
0x14006d98c  pop     r14
0x14006d98e  pop     r13
0x14006d990  pop     r12
0x14006d992  pop     rdi
0x14006d993  pop     rsi
0x14006d994  pop     rbx
0x14006d995  pop     rbp
0x14006d996  retn
0x14006d998  mov     rcx, rdi
0x14006d99b  call    cs:__imp_?bFlatten@EPATHOBJ@@QEAA_NXZ; EPATHOBJ::bFlatten(void)
0x14006d9a2  nop     dword ptr [rax+rax+00h]
0x14006d9a7  test    al, al
0x14006d9a9  jnz     loc_14006D8AD
0x14006d9af  xor     eax, eax
0x14006d9b1  jmp     short loc_14006D974
0x14006d9b3  mov     r8, r14
0x14006d9b6  jmp     short loc_14006D94C
0x14006d9b8  mov     rcx, rdi; this
0x14006d9bb  call    ?bPreComputedFill@EPATHOBJ@@QEBAHXZ; EPATHOBJ::bPreComputedFill(void)
0x14006d9c0  test    eax, eax
0x14006d9c2  jz      loc_14006D8FB
0x14006d9c8  cmp     byte ptr [rsi+14h], 0
0x14006d9cc  xorps   xmm0, xmm0
0x14006d9cf  movups  [rsp+230h+var_1C0], xmm0
0x14006d9d4  jz      loc_14006DC0D
0x14006d9da  mov     eax, [rsi+8]
0x14006d9dd  lea     r9, [rsp+230h+var_1C0]
0x14006d9e2  shl     eax, 4
0x14006d9e5  mov     dword ptr [rsp+230h+var_1C0+4], eax
0x14006d9e9  mov     eax, [rsi+10h]
0x14006d9ec  shl     eax, 4
0x14006d9ef  mov     dword ptr [rsp+230h+var_1C0+0Ch], eax
0x14006d9f3  mov     eax, [rdi]
0x14006d9f5  mov     [rsp+230h+var_1E8], 0
0x14006d9fd  test    al, 10h
0x14006d9ff  jnz     loc_14006DD04
0x14006da05  mov     rax, [rdi+10h]
0x14006da09  mov     [rsp+230h+var_1F0], rax
0x14006da0e  test    rax, rax
0x14006da11  jnz     short loc_14006DA78
0x14006da13  mov     r8d, r12d
0x14006da16  mov     [rsp+230h+var_1E8], ebx
0x14006da1a  mov     rdx, rdi
0x14006da1d  mov     [rsp+230h+var_1D8], rax
0x14006da22  lea     rcx, [rsp+230h+var_1D8]
0x14006da27  call    cs:__imp_?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z; RGNMEMOBJ::vCreate(EPATHOBJ &,ulong,_RECTL *)
0x14006da2e  nop     dword ptr [rax+rax+00h]
0x14006da33  mov     rax, [rsp+230h+var_1D8]
0x14006da38  lea     rcx, [rsp+230h+var_1F0]
0x14006da3d  mov     [rsp+230h+var_1F0], rax
0x14006da42  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x14006da49  nop     dword ptr [rax+rax+00h]
0x14006da4e  xor     r12d, r12d
0x14006da51  cmp     [rsp+230h+var_1F0], r12
0x14006da56  jnz     short loc_14006DA7B
0x14006da58  cmp     dword ptr [rdi+4], 2
0x14006da5c  jb      loc_14006DBDD
0x14006da62  lea     ecx, [r12+8]; iError
0x14006da67  call    cs:__imp_EngSetLastError
0x14006da6e  nop     dword ptr [rax+rax+00h]
0x14006da73  jmp     loc_14006DC30
0x14006da78  xor     r12d, r12d
0x14006da7b  lea     rcx, [rsp+230h+var_1F0]; this
0x14006da80  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x14006da85  cmp     eax, ebx
0x14006da87  jz      loc_14006DBDD
0x14006da8d  movups  xmm0, xmmword ptr [r14]
0x14006da91  mov     rcx, rdi; this
0x14006da94  movdqu  [rbp+130h+var_1A0], xmm0
0x14006da99  call    ?bPreComputedFill@EPATHOBJ@@QEBAHXZ; EPATHOBJ::bPreComputedFill(void)
0x14006da9e  test    eax, eax
0x14006daa0  jz      loc_14006DB56
0x14006daa6  mov     edx, 70h ; 'p'
0x14006daab  mov     [rsp+230h+var_1E0], r12
0x14006dab0  lea     rcx, [rsp+230h+var_1E0]
0x14006dab5  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x14006dabc  nop     dword ptr [rax+rax+00h]
0x14006dac1  lea     rcx, [rsp+230h+var_1E0]
0x14006dac6  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x14006dacd  nop     dword ptr [rax+rax+00h]
0x14006dad2  cmp     [rsp+230h+var_1E0], r12
0x14006dad7  jz      loc_14006DC15
0x14006dadd  lea     r8, [rsi+38h]
0x14006dae1  mov     r9b, 8
0x14006dae4  lea     rdx, [rsp+230h+var_1F0]
0x14006dae9  lea     rcx, [rsp+230h+var_1E0]
0x14006daee  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x14006daf5  nop     dword ptr [rax+rax+00h]
0x14006dafa  test    eax, eax
0x14006dafc  jnz     loc_14006DC3F
0x14006db02  lea     rcx, [rsp+230h+var_1E0]
0x14006db07  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14006db0e  nop     dword ptr [rax+rax+00h]
0x14006db13  lea     rcx, [rsp+230h+var_1E0]
0x14006db18  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14006db1f  nop     dword ptr [rax+rax+00h]
0x14006db24  cmp     [rsp+230h+var_1E8], r12d
0x14006db29  jz      loc_14006D9AF
0x14006db2f  lea     rcx, [rsp+230h+var_1F0]
0x14006db34  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14006db3b  nop     dword ptr [rax+rax+00h]
0x14006db40  lea     rcx, [rsp+230h+var_1F0]
0x14006db45  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14006db4c  nop     dword ptr [rax+rax+00h]
0x14006db51  jmp     loc_14006D9AF
0x14006db56  cmp     [rsi+14h], r12b
0x14006db5a  jnz     loc_14006DAA6
0x14006db60  mov     rdx, [rsp+230h+var_1F0]
0x14006db65  lea     r8, [rbp+130h+var_1A0]
0x14006db69  xor     r9d, r9d
0x14006db6c  mov     [rbp+130h+var_158], r12
0x14006db70  lea     rcx, [rbp+130h+pco]
0x14006db74  mov     [rbp+130h+var_140], r12
0x14006db78  mov     [rbp+130h+var_138], r12d
0x14006db7c  mov     [rbp+130h+var_110], ebx
0x14006db7f  mov     [rbp+130h+var_100], r12
0x14006db83  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x14006db8a  nop     dword ptr [rax+rax+00h]
0x14006db8f  lea     rcx, [rbp+130h+pco.rclBounds]; this
0x14006db93  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x14006db98  test    eax, eax
0x14006db9a  jnz     loc_14006DC33
0x14006dba0  movzx   eax, [rbp+130h+pco.iDComplexity]
0x14006dba4  mov     ecx, 5Ch ; '\'
0x14006dba9  mov     r9, [rsp+230h+var_1D0]; pptlBrushOrg
0x14006dbae  test    al, al
0x14006dbb0  mov     r8, [rsp+230h+pbo]; pbo
0x14006dbb5  mov     edx, eax
0x14006dbb7  cmovz   edx, ebx
0x14006dbba  mov     [rsp+230h+var_210], r13d; mix
0x14006dbbf  test    r15, r15
0x14006dbc2  mov     [rbp+130h+pco.iDComplexity], dl
0x14006dbc5  lea     rax, [r15+44h]
0x14006dbc9  cmovz   rax, rcx
0x14006dbcd  lea     rdx, [rbp+130h+pco]; pco
0x14006dbd1  mov     rcx, r15; pso
0x14006dbd4  add     [rax], ebx
0x14006dbd6  call    EngPaint
0x14006dbdb  mov     ebx, eax
0x14006dbdd  cmp     [rsp+230h+var_1E8], r12d
0x14006dbe2  jz      short loc_14006DC06
0x14006dbe4  lea     rcx, [rsp+230h+var_1F0]
0x14006dbe9  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14006dbf0  nop     dword ptr [rax+rax+00h]
0x14006dbf5  lea     rcx, [rsp+230h+var_1F0]
0x14006dbfa  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14006dc01  nop     dword ptr [rax+rax+00h]
0x14006dc06  mov     eax, ebx
0x14006dc08  jmp     loc_14006D974
0x14006dc0d  xor     r9d, r9d
0x14006dc10  jmp     loc_14006D9F3
0x14006dc15  mov     ecx, 8; iError
0x14006dc1a  call    cs:__imp_EngSetLastError
0x14006dc21  nop     dword ptr [rax+rax+00h]
0x14006dc26  lea     rcx, [rsp+230h+var_1E0]; this
0x14006dc2b  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14006dc30  mov     ebx, r12d
0x14006dc33  lea     rcx, [rsp+230h+var_1F0]; this
0x14006dc38  call    ??1RGNMEMOBJTMPIFNEEDED@@QEAA@XZ; RGNMEMOBJTMPIFNEEDED::~RGNMEMOBJTMPIFNEEDED(void)
0x14006dc3d  jmp     short loc_14006DC06
0x14006dc3f  mov     r11, [rsp+230h+var_1E0]
0x14006dc44  lea     rcx, [rbp+130h+var_1B0]
0x14006dc48  mov     rdx, r14
0x14006dc4b  movups  xmm0, xmmword ptr [r11+34h]
0x14006dc50  movdqu  [rbp+130h+var_1B0], xmm0
0x14006dc55  call    ??XERECTL@@QEAAAEAV0@AEBU_RECTL@@@Z; ERECTL::operator*=(_RECTL const &)
0x14006dc5a  xor     r9d, r9d
0x14006dc5d  mov     [rbp+130h+var_B8], r12
0x14006dc61  lea     r8, [rbp+130h+var_1B0]
0x14006dc65  mov     [rbp+130h+var_A0], r12
0x14006dc6c  mov     rdx, r11
0x14006dc6f  mov     [rbp+130h+var_98], r12d
0x14006dc76  lea     rcx, [rbp+130h+var_F0]
0x14006dc7a  mov     [rbp+130h+var_70], ebx
0x14006dc80  mov     [rbp+130h+var_60], r12
0x14006dc87  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x14006dc8e  nop     dword ptr [rax+rax+00h]
0x14006dc93  lea     rcx, [rbp+130h+var_F0.rclBounds]; this
0x14006dc97  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x14006dc9c  test    eax, eax
0x14006dc9e  jnz     short loc_14006DD1C
0x14006dca0  movzx   eax, [rbp+130h+var_F0.iDComplexity]
0x14006dca4  lea     rdx, [rbp+130h+var_F0]; pco
0x14006dca8  mov     r9, [rsp+230h+var_1D0]; pptlBrushOrg
0x14006dcad  test    al, al
0x14006dcaf  mov     r8, [rsp+230h+pbo]; pbo
0x14006dcb4  mov     ecx, eax
0x14006dcb6  cmovz   ecx, ebx
0x14006dcb9  mov     [rsp+230h+var_210], r13d; mix
0x14006dcbe  mov     [rbp+130h+var_F0.iDComplexity], cl
0x14006dcc1  lea     rax, [r15+44h]
0x14006dcc5  mov     ecx, 5Ch ; '\'
0x14006dcca  test    r15, r15
0x14006dccd  cmovz   rax, rcx
0x14006dcd1  mov     rcx, r15; pso
0x14006dcd4  add     [rax], ebx
0x14006dcd6  call    EngPaint
0x14006dcdb  lea     rcx, [rsp+230h+var_1E0]
0x14006dce0  mov     ebx, eax
0x14006dce2  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14006dce9  nop     dword ptr [rax+rax+00h]
0x14006dcee  lea     rcx, [rsp+230h+var_1E0]
0x14006dcf3  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14006dcfa  nop     dword ptr [rax+rax+00h]
0x14006dcff  jmp     loc_14006DBDD
0x14006dd04  cmp     r12d, 2
0x14006dd08  jnz     short loc_14006DD13
0x14006dd0a  mov     rax, [rdi+20h]
0x14006dd0e  jmp     loc_14006DA09
0x14006dd13  mov     rax, [rdi+18h]
0x14006dd17  jmp     loc_14006DA09
0x14006dd1c  lea     rcx, [rsp+230h+var_1E0]; this
0x14006dd21  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14006dd26  jmp     loc_14006DC33
```
