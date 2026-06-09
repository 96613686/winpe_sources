# EngStrokeAndFillPath

- ea: `0x1401d4be0`
- end: `0x1401d5247`
- name: `EngStrokeAndFillPath`
- size: `1639`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, XFORMOBJ *pxo, BRUSHOBJ *pboStroke, LINEATTRS *plineattrs, BRUSHOBJ *pboFill, POINTL *pptlBrushOrg, MIX mixFill, FLONG flOptions)`
- caller_count: `7`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140146f40`
- `0x140147764`
- `0x1401d4798`
- `0x1402a3370`
- `0x1402a53d0`
- `0x140315900`
- `0x1403220c0`

## callees

- `0x140069bc8`
- `0x14006cdb4`
- `0x14006d850`
- `0x14006e244`
- `0x14006ff90`
- `0x14007021c`
- `0x140077348`
- `0x14008cfa0`
- `0x1401d4be0`
- `0x1401d5250`
- `0x14022d39c`
- `0x140342fa0`

## import_xrefs

- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x1401d4c9f`
- `win32kbase!??0PATHMEMOBJ@@QEAA@XZ` at `0x1401d4c9f`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x1401d4cdb`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x1401d4f3a`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x1401d4cdb`
- `win32kbase!??1PATHMEMOBJ@@QEAA@XZ` at `0x1401d4f3a`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4e23`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4e7f`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4ead`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4fc7`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4e23`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4e7f`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4ead`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4fc7`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x1401d4e9c`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x1401d4fb6`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x1401d4e9c`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x1401d4fb6`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d4eda`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d4f02`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d4f2a`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d5002`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d501d`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d5208`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d4eda`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d4f02`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d4f2a`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d5002`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d501d`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401d5208`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4ec9`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4ef1`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4f19`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4ff1`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4ec9`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4ef1`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4f19`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401d4ff1`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1401d50f7`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1401d51ab`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1401d50f7`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1401d51ab`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401d4f76`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401d50ac`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401d5160`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401d4f76`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401d50ac`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401d5160`
- `win32kbase!EngSetLastError` at `0x1401d4ccb`
- `win32kbase!EngSetLastError` at `0x1401d4ccb`
- `win32kbase!?bFlatten@EPATHOBJ@@QEAA_NXZ` at `0x1401d51e0`
- `win32kbase!?bFlatten@EPATHOBJ@@QEAA_NXZ` at `0x1401d51e0`
- `win32kbase!?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z` at `0x1401d4e08`
- `win32kbase!?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z` at `0x1401d4e64`
- `win32kbase!?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z` at `0x1401d4e08`
- `win32kbase!?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z` at `0x1401d4e64`

## pseudocode

```c
BOOL __stdcall EngStrokeAndFillPath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        XFORMOBJ *pxo,
        BRUSHOBJ *pboStroke,
        LINEATTRS *plineattrs,
        BRUSHOBJ *pboFill,
        POINTL *pptlBrushOrg,
        MIX mixFill,
        FLONG flOptions)
{
  MIX v13; // r15d
  MIX mix; // r12d
  BOOL v15; // edi
  struct _RECTFX *v17; // rdx
  LINEATTRS *v18; // r9
  bool v19; // zf
  PATHOBJ *v20; // rdx
  BOOL v21; // r14d
  FLONG fl; // eax
  PATHOBJ v23; // rax
  BRUSHOBJ *v24; // r8
  POINTL *v25; // r15
  __int64 v26; // rax
  POINTL *v27; // r9
  __int128 v28; // xmm0
  BRUSHOBJ *v29; // r8
  __int64 p_iUniq; // rsi
  __int128 v31; // xmm0
  MIX v32; // [rsp+20h] [rbp-E0h]
  struct REGION *v33; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  LINEATTRS *v35; // [rsp+50h] [rbp-B0h] BYREF
  LINEATTRS *v36; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+60h] [rbp-A0h]
  LINEATTRS *v38; // [rsp+68h] [rbp-98h] BYREF
  int v39; // [rsp+70h] [rbp-90h]
  struct _CLIPOBJ *v40; // [rsp+78h] [rbp-88h] BYREF
  BRUSHOBJ *pbo; // [rsp+80h] [rbp-80h] BYREF
  POINTL *v42; // [rsp+88h] [rbp-78h]
  BRUSHOBJ *v43; // [rsp+90h] [rbp-70h] BYREF
  CLIPOBJ *pcoa[2]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v45[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-48h]
  __int128 v47; // [rsp+130h] [rbp+30h] BYREF
  CLIPOBJ v48; // [rsp+140h] [rbp+40h] BYREF
  __int64 v49; // [rsp+178h] [rbp+78h]
  __int64 v50; // [rsp+190h] [rbp+90h]
  int v51; // [rsp+198h] [rbp+98h]
  int v52; // [rsp+1C0h] [rbp+C0h]
  __int64 v53; // [rsp+1D0h] [rbp+D0h]
  _BYTE v54[152]; // [rsp+1E0h] [rbp+E0h] BYREF
  BRUSHOBJ *v55; // [rsp+278h] [rbp+178h]
  int v56; // [rsp+280h] [rbp+180h]

  v13 = mixFill;
  pcoa[0] = pco;
  v35 = plineattrs;
  v40 = pco;
  pbo = pboStroke;
  v43 = pboFill;
  v42 = pptlBrushOrg;
  LODWORD(v33) = flOptions;
  if ( _bittest((const signed __int32 *)&pboFill[5], 0xFu) )
    mix = mixFill;
  else
    mix = (unsigned __int8)mixFill | ((unsigned __int8)mixFill << 8);
  if ( !_bittest((const signed __int32 *)&pboStroke[5], 0xFu) )
    v13 = (unsigned __int8)mixFill | ((unsigned __int8)mixFill << 8);
  v15 = 1;
  if ( (plineattrs->fl & 1) != 0 && (unsigned __int8)mixFill != 13 )
  {
    PATHMEMOBJ::PATHMEMOBJ((PATHMEMOBJ *)v45);
    if ( !*(_QWORD *)&ppo[5] )
    {
      if ( !pxo )
        goto LABEL_11;
      if ( !v46
        || (v17 = (struct _RECTFX *)(*(_QWORD *)&ppo[1] + 48LL),
            *(_OWORD *)pcoa = 0,
            !pathwide::bComputeWidenedBounds(
               (pathwide *)pcoa,
               v17,
               (struct _RECTFX *)pxo,
               (const struct EXFORMOBJ *)v35))
        || (v18 = v35,
            *(_OWORD *)(v46 + 48) = *(_OWORD *)pcoa,
            !pathwide::bWiden((pathwide *)v45, (struct EPATHOBJ *)ppo, (struct EPATHOBJ *)pxo, v18)) )
      {
        EngSetLastError(8u);
        goto LABEL_11;
      }
    }
    if ( (ppo->fl & 1) == 0 || EPATHOBJ::bFlatten((EPATHOBJ *)ppo) )
    {
      v19 = *(_QWORD *)&ppo[5] == 0;
      v20 = (PATHOBJ *)v45;
      v21 = 0;
      v39 = 0;
      if ( !v19 )
        v20 = ppo;
      v38 = (LINEATTRS *)v20[5];
      if ( !v38 )
      {
        v39 = 1;
        v35 = 0;
        RGNMEMOBJ::vCreate((RGNMEMOBJ *)&v35, (struct EPATHOBJ *)v20, 2u, 0);
        v38 = v35;
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v38);
      }
      fl = ppo->fl;
      v37 = 0;
      if ( (fl & 0x10) != 0 )
      {
        if ( (_DWORD)v33 == 2 )
          v23 = ppo[4];
        else
          v23 = ppo[3];
      }
      else
      {
        v23 = ppo[2];
      }
      v36 = (LINEATTRS *)v23;
      if ( !*(_QWORD *)&v23 )
      {
        v37 = 1;
        v35 = 0;
        RGNMEMOBJ::vCreate((RGNMEMOBJ *)&v35, (struct EPATHOBJ *)ppo, (unsigned int)v33, 0);
        v36 = v35;
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v36);
      }
      v34 = 0;
      RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v34, 0x70u);
      RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v34);
      if ( !v36 || !v38 || !v34 || !RGNOBJ::bMerge((RGNOBJ *)&v34, (struct RGNOBJ *)&v36, (struct RGNOBJ *)&v38, 4u) )
        goto LABEL_27;
      BOUNDCLIPRGNTOSURFACE::BOUNDCLIPRGNTOSURFACE((BOUNDCLIPRGNTOSURFACE *)v54, pso, &v40);
      if ( v56 )
      {
        v33 = 0;
        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v33, 0x70u);
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v33);
        if ( v33 )
        {
          if ( (unsigned int)RGNOBJ::iComplexity((RGNOBJ *)&v38) != 1 )
          {
            v40 = (struct _CLIPOBJ *)((char *)v40 + 56);
            if ( RGNOBJ::bMerge((RGNOBJ *)&v33, (struct RGNOBJ *)&v38, (struct RGNOBJ *)v40, 8u) )
            {
              v31 = *(_OWORD *)((char *)v33 + 52);
              v49 = 0;
              v50 = 0;
              v47 = v31;
              v51 = 0;
              v52 = 1;
              v53 = 0;
              XCLIPOBJ::vSetup((XCLIPOBJ *)&v48, v33, (const struct ERECTL *)&v47, 0);
              p_iUniq = (__int64)&pso->iUniq;
              if ( ERECTL::bEmpty((ERECTL *)&v48.rclBounds) )
              {
                v25 = v42;
                v21 = 1;
              }
              else
              {
                v24 = pbo;
                v32 = v13;
                v25 = v42;
                v26 = (__int64)&pso->iUniq;
                if ( !pso )
                  v26 = 92;
                v27 = v42;
                ++*(_DWORD *)v26;
                v21 = EngPaint(pso, &v48, v24, v27, v32);
                if ( !v21 )
                  goto LABEL_38;
              }
              if ( (unsigned int)RGNOBJ::iComplexity((RGNOBJ *)&v34) != 1 )
              {
                if ( RGNOBJ::bMerge((RGNOBJ *)&v33, (struct RGNOBJ *)&v34, (struct RGNOBJ *)v40, 8u) )
                {
                  v28 = *(_OWORD *)((char *)v33 + 52);
                  v49 = 0;
                  v50 = 0;
                  v47 = v28;
                  v51 = 0;
                  v52 = 1;
                  v53 = 0;
                  XCLIPOBJ::vSetup((XCLIPOBJ *)&v48, v33, (const struct ERECTL *)&v47, 0);
                  if ( ERECTL::bEmpty((ERECTL *)&v48.rclBounds) )
                  {
                    v21 = 1;
                  }
                  else
                  {
                    v29 = v43;
                    if ( !pso )
                      p_iUniq = 92;
                    ++*(_DWORD *)p_iUniq;
                    v21 = EngPaint(pso, &v48, v29, v25, mix);
                  }
                }
                else
                {
                  v21 = 0;
                }
              }
            }
          }
        }
LABEL_38:
        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v33);
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v33);
        v43 = v55;
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v43);
LABEL_27:
        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v34);
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v34);
        if ( v37 )
        {
          RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v36);
          RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v36);
        }
        if ( v39 )
        {
          RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v38);
          RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v38);
        }
        PATHMEMOBJ::~PATHMEMOBJ((PATHMEMOBJ *)v45);
        return v21;
      }
      pbo = v55;
      RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&pbo);
      RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v34);
      RGNMEMOBJTMPIFNEEDED::~RGNMEMOBJTMPIFNEEDED((RGNMEMOBJTMPIFNEEDED *)&v36);
      RGNMEMOBJTMPIFNEEDED::~RGNMEMOBJTMPIFNEEDED((RGNMEMOBJTMPIFNEEDED *)&v38);
    }
LABEL_11:
    PATHMEMOBJ::~PATHMEMOBJ((PATHMEMOBJ *)v45);
    return 0;
  }
  if ( !EngFillPath(pso, ppo, pco, pboFill, pptlBrushOrg, mix, flOptions)
    || !EngStrokePath(pso, ppo, pcoa[0], pxo, pbo, v42, v35, v13) )
  {
    return 0;
  }
  return v15;
}

```

## disassembly

```asm
0x1401d4be0  push    rbp
0x1401d4be2  push    rbx
0x1401d4be3  push    rsi
0x1401d4be4  push    rdi
0x1401d4be5  push    r12
0x1401d4be7  push    r13
0x1401d4be9  push    r14
0x1401d4beb  push    r15
0x1401d4bed  lea     rbp, [rsp-1A8h]
0x1401d4bf5  sub     rsp, 2A8h
0x1401d4bfc  mov     rax, cs:__security_cookie
0x1401d4c03  xor     rax, rsp
0x1401d4c06  mov     [rbp+1E0h+var_50], rax
0x1401d4c0d  mov     rbx, [rbp+1E0h+pboFill]
0x1401d4c14  mov     rsi, rdx
0x1401d4c17  mov     rdx, [rbp+1E0h+plineattrs]
0x1401d4c1e  mov     r14, r9
0x1401d4c21  mov     r11, [rbp+1E0h+pboStroke]
0x1401d4c28  mov     r13, rcx
0x1401d4c2b  mov     r10, [rbp+1E0h+pptlBrushOrg]
0x1401d4c32  bt      dword ptr [rbx+78h], 0Fh
0x1401d4c37  mov     r9d, [rbp+1E0h+flOptions]
0x1401d4c3e  mov     r15d, [rbp+1E0h+mixFill]
0x1401d4c45  mov     [rbp+1E0h+pco], r8
0x1401d4c49  mov     [rsp+2E0h+var_290], rdx
0x1401d4c4e  mov     [rsp+2E0h+var_268], r8
0x1401d4c53  mov     [rbp+1E0h+pbo], r11
0x1401d4c57  mov     [rbp+1E0h+var_250], rbx
0x1401d4c5b  mov     [rbp+1E0h+var_258], r10
0x1401d4c5f  mov     dword ptr [rsp+2E0h+var_2A0], r9d
0x1401d4c64  movzx   ecx, r15b
0x1401d4c68  jb      loc_1401D504D
0x1401d4c6e  mov     r12d, ecx
0x1401d4c71  shl     r12d, 8
0x1401d4c75  or      r12d, ecx
0x1401d4c78  bt      dword ptr [r11+78h], 0Fh
0x1401d4c7e  jb      short loc_1401D4C8A
0x1401d4c80  mov     r15d, ecx
0x1401d4c83  shl     r15d, 8
0x1401d4c87  or      r15d, ecx
0x1401d4c8a  mov     eax, [rdx]
0x1401d4c8c  mov     edi, 1
0x1401d4c91  test    dil, al
0x1401d4c94  jz      short loc_1401D4D0D
0x1401d4c96  cmp     ecx, 0Dh
0x1401d4c99  jz      short loc_1401D4D0D
0x1401d4c9b  lea     rcx, [rbp+1E0h+var_230]
0x1401d4c9f  call    cs:__imp_??0PATHMEMOBJ@@QEAA@XZ; PATHMEMOBJ::PATHMEMOBJ(void)
0x1401d4ca6  nop     dword ptr [rax+rax+00h]
0x1401d4cab  xor     ebx, ebx
0x1401d4cad  cmp     [rsi+28h], rbx
0x1401d4cb1  jnz     loc_1401D4DC7
0x1401d4cb7  test    r14, r14
0x1401d4cba  jz      short loc_1401D4CD7
0x1401d4cbc  cmp     [rbp+1E0h+var_228], rbx
0x1401d4cc0  jnz     loc_1401D4D76
0x1401d4cc6  mov     ecx, 8; iError
0x1401d4ccb  call    cs:__imp_EngSetLastError
0x1401d4cd2  nop     dword ptr [rax+rax+00h]
0x1401d4cd7  lea     rcx, [rbp+1E0h+var_230]
0x1401d4cdb  call    cs:__imp_??1PATHMEMOBJ@@QEAA@XZ; PATHMEMOBJ::~PATHMEMOBJ(void)
0x1401d4ce2  nop     dword ptr [rax+rax+00h]
0x1401d4ce7  xor     eax, eax
0x1401d4ce9  mov     rcx, [rbp+1E0h+var_50]
0x1401d4cf0  xor     rcx, rsp; StackCookie
0x1401d4cf3  call    __security_check_cookie
0x1401d4cf8  add     rsp, 2A8h
0x1401d4cff  pop     r15
0x1401d4d01  pop     r14
0x1401d4d03  pop     r13
0x1401d4d05  pop     r12
0x1401d4d07  pop     rdi
0x1401d4d08  pop     rsi
0x1401d4d09  pop     rbx
0x1401d4d0a  pop     rbp
0x1401d4d0b  retn
0x1401d4d0d  mov     [rsp+2E0h+var_2B0], r9d; flOptions
0x1401d4d12  mov     rdx, rsi; ppo
0x1401d4d15  mov     [rsp+2E0h+mix], r12d; mix
0x1401d4d1a  mov     r9, rbx; pbo
0x1401d4d1d  mov     rcx, r13; pso
0x1401d4d20  mov     qword ptr [rsp+2E0h+var_2C0], r10; pptlBrushOrg
0x1401d4d25  call    EngFillPath
0x1401d4d2a  xor     ebx, ebx
0x1401d4d2c  test    eax, eax
0x1401d4d2e  jz      loc_1401D5046
0x1401d4d34  mov     rax, [rsp+2E0h+var_290]
0x1401d4d39  mov     r9, r14; pxo
0x1401d4d3c  mov     r8, [rbp+1E0h+pco]; pco
0x1401d4d40  mov     rdx, rsi; ppo
0x1401d4d43  mov     [rsp+2E0h+var_2A8], r15d; mix
0x1401d4d48  mov     rcx, r13; pso
0x1401d4d4b  mov     r15, [rbp+1E0h+var_258]
0x1401d4d4f  mov     qword ptr [rsp+2E0h+var_2B0], rax; plineattrs
0x1401d4d54  mov     rax, [rbp+1E0h+pbo]
0x1401d4d58  mov     qword ptr [rsp+2E0h+mix], r15; pptlBrushOrg
0x1401d4d5d  mov     qword ptr [rsp+2E0h+var_2C0], rax; pbo
0x1401d4d62  call    EngStrokePath
0x1401d4d67  test    eax, eax
0x1401d4d69  jz      loc_1401D5046
0x1401d4d6f  mov     eax, edi
0x1401d4d71  jmp     loc_1401D4CE9
0x1401d4d76  mov     rdx, [rsi+8]
0x1401d4d7a  lea     rcx, [rbp+1E0h+pco]; this
0x1401d4d7e  mov     r9, [rsp+2E0h+var_290]; struct EXFORMOBJ *
0x1401d4d83  xorps   xmm0, xmm0
0x1401d4d86  add     rdx, 30h ; '0'; struct _RECTFX *
0x1401d4d8a  mov     r8, r14; struct _RECTFX *
0x1401d4d8d  movups  xmmword ptr [rbp+1E0h+pco], xmm0
0x1401d4d91  call    ?bComputeWidenedBounds@pathwide@@YA_NAEAU_RECTFX@@AEBU2@AEBVEXFORMOBJ@@AEBU_LINEATTRS@@@Z; pathwide::bComputeWidenedBounds(_RECTFX &,_RECTFX const &,EXFORMOBJ const &,_LINEATTRS const &)
0x1401d4d96  test    al, al
0x1401d4d98  jz      loc_1401D4CC6
0x1401d4d9e  mov     rax, [rbp+1E0h+var_228]
0x1401d4da2  lea     rcx, [rbp+1E0h+var_230]; this
0x1401d4da6  movups  xmm0, xmmword ptr [rbp+1E0h+pco]
0x1401d4daa  mov     r9, [rsp+2E0h+var_290]; struct EXFORMOBJ *
0x1401d4daf  mov     r8, r14; struct EPATHOBJ *
0x1401d4db2  mov     rdx, rsi; struct EPATHOBJ *
0x1401d4db5  movdqu  xmmword ptr [rax+30h], xmm0
0x1401d4dba  call    ?bWiden@pathwide@@YA_NAEAVEPATHOBJ@@0AEBVEXFORMOBJ@@AEBU_LINEATTRS@@@Z; pathwide::bWiden(EPATHOBJ &,EPATHOBJ &,EXFORMOBJ const &,_LINEATTRS const &)
0x1401d4dbf  test    al, al
0x1401d4dc1  jz      loc_1401D4CC6
0x1401d4dc7  mov     eax, [rsi]
0x1401d4dc9  test    dil, al
0x1401d4dcc  jnz     loc_1401D51DD
0x1401d4dd2  cmp     [rsi+28h], rbx
0x1401d4dd6  lea     rdx, [rbp+1E0h+var_230]
0x1401d4dda  mov     r14d, ebx
0x1401d4ddd  mov     [rsp+2E0h+var_270], ebx
0x1401d4de1  cmovnz  rdx, rsi
0x1401d4de5  mov     rax, [rdx+28h]
0x1401d4de9  mov     [rsp+2E0h+var_278], rax
0x1401d4dee  test    rax, rax
0x1401d4df1  jnz     short loc_1401D4E2F
0x1401d4df3  xor     r9d, r9d
0x1401d4df6  mov     [rsp+2E0h+var_270], edi
0x1401d4dfa  lea     r8d, [rax+2]
0x1401d4dfe  mov     [rsp+2E0h+var_290], rbx
0x1401d4e03  lea     rcx, [rsp+2E0h+var_290]
0x1401d4e08  call    cs:__imp_?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z; RGNMEMOBJ::vCreate(EPATHOBJ &,ulong,_RECTL *)
0x1401d4e0f  nop     dword ptr [rax+rax+00h]
0x1401d4e14  mov     rax, [rsp+2E0h+var_290]
0x1401d4e19  lea     rcx, [rsp+2E0h+var_278]
0x1401d4e1e  mov     [rsp+2E0h+var_278], rax
0x1401d4e23  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x1401d4e2a  nop     dword ptr [rax+rax+00h]
0x1401d4e2f  mov     eax, [rsi]
0x1401d4e31  mov     r8d, dword ptr [rsp+2E0h+var_2A0]
0x1401d4e36  mov     [rsp+2E0h+var_280], ebx
0x1401d4e3a  test    al, 10h
0x1401d4e3c  jnz     loc_1401D502E
0x1401d4e42  mov     rax, [rsi+10h]
0x1401d4e46  mov     [rsp+2E0h+var_288], rax
0x1401d4e4b  test    rax, rax
0x1401d4e4e  jnz     short loc_1401D4E8B
0x1401d4e50  xor     r9d, r9d
0x1401d4e53  mov     [rsp+2E0h+var_280], edi
0x1401d4e57  mov     rdx, rsi
0x1401d4e5a  mov     [rsp+2E0h+var_290], rbx
0x1401d4e5f  lea     rcx, [rsp+2E0h+var_290]
0x1401d4e64  call    cs:__imp_?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z; RGNMEMOBJ::vCreate(EPATHOBJ &,ulong,_RECTL *)
0x1401d4e6b  nop     dword ptr [rax+rax+00h]
0x1401d4e70  mov     rax, [rsp+2E0h+var_290]
0x1401d4e75  lea     rcx, [rsp+2E0h+var_288]
0x1401d4e7a  mov     [rsp+2E0h+var_288], rax
0x1401d4e7f  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x1401d4e86  nop     dword ptr [rax+rax+00h]
0x1401d4e8b  mov     esi, 70h ; 'p'
0x1401d4e90  mov     [rsp+2E0h+var_298], rbx
0x1401d4e95  mov     edx, esi
0x1401d4e97  lea     rcx, [rsp+2E0h+var_298]
0x1401d4e9c  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x1401d4ea3  nop     dword ptr [rax+rax+00h]
0x1401d4ea8  lea     rcx, [rsp+2E0h+var_298]
0x1401d4ead  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x1401d4eb4  nop     dword ptr [rax+rax+00h]
0x1401d4eb9  cmp     [rsp+2E0h+var_288], rbx
0x1401d4ebe  jnz     loc_1401D4F4E
0x1401d4ec4  lea     rcx, [rsp+2E0h+var_298]
0x1401d4ec9  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x1401d4ed0  nop     dword ptr [rax+rax+00h]
0x1401d4ed5  lea     rcx, [rsp+2E0h+var_298]
0x1401d4eda  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401d4ee1  nop     dword ptr [rax+rax+00h]
0x1401d4ee6  cmp     [rsp+2E0h+var_280], ebx
0x1401d4eea  jz      short loc_1401D4F0E
0x1401d4eec  lea     rcx, [rsp+2E0h+var_288]
0x1401d4ef1  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x1401d4ef8  nop     dword ptr [rax+rax+00h]
0x1401d4efd  lea     rcx, [rsp+2E0h+var_288]
0x1401d4f02  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401d4f09  nop     dword ptr [rax+rax+00h]
0x1401d4f0e  cmp     [rsp+2E0h+var_270], ebx
0x1401d4f12  jz      short loc_1401D4F36
0x1401d4f14  lea     rcx, [rsp+2E0h+var_278]
0x1401d4f19  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x1401d4f20  nop     dword ptr [rax+rax+00h]
0x1401d4f25  lea     rcx, [rsp+2E0h+var_278]
0x1401d4f2a  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401d4f31  nop     dword ptr [rax+rax+00h]
0x1401d4f36  lea     rcx, [rbp+1E0h+var_230]
0x1401d4f3a  call    cs:__imp_??1PATHMEMOBJ@@QEAA@XZ; PATHMEMOBJ::~PATHMEMOBJ(void)
0x1401d4f41  nop     dword ptr [rax+rax+00h]
0x1401d4f46  mov     eax, r14d
0x1401d4f49  jmp     loc_1401D4CE9
0x1401d4f4e  cmp     [rsp+2E0h+var_278], rbx
0x1401d4f53  jz      loc_1401D4EC4
0x1401d4f59  cmp     [rsp+2E0h+var_298], rbx
0x1401d4f5e  jz      loc_1401D4EC4
0x1401d4f64  mov     r9b, 4
0x1401d4f67  lea     r8, [rsp+2E0h+var_278]
0x1401d4f6c  lea     rdx, [rsp+2E0h+var_288]
0x1401d4f71  lea     rcx, [rsp+2E0h+var_298]
0x1401d4f76  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x1401d4f7d  nop     dword ptr [rax+rax+00h]
0x1401d4f82  test    eax, eax
0x1401d4f84  jz      loc_1401D4EC4
0x1401d4f8a  lea     r8, [rsp+2E0h+var_268]; struct _CLIPOBJ **
0x1401d4f8f  mov     rdx, r13; struct _SURFOBJ *
0x1401d4f92  lea     rcx, [rbp+1E0h+var_100]; this
0x1401d4f99  call    ??0BOUNDCLIPRGNTOSURFACE@@QEAA@PEAU_SURFOBJ@@PEAPEAU_CLIPOBJ@@@Z; BOUNDCLIPRGNTOSURFACE::BOUNDCLIPRGNTOSURFACE(_SURFOBJ *,_CLIPOBJ * *)
0x1401d4f9e  cmp     [rbp+1E0h+var_60], ebx
0x1401d4fa4  jz      loc_1401D51F9
0x1401d4faa  mov     edx, esi
0x1401d4fac  mov     [rsp+2E0h+var_2A0], rbx
0x1401d4fb1  lea     rcx, [rsp+2E0h+var_2A0]
0x1401d4fb6  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x1401d4fbd  nop     dword ptr [rax+rax+00h]
0x1401d4fc2  lea     rcx, [rsp+2E0h+var_2A0]
0x1401d4fc7  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x1401d4fce  nop     dword ptr [rax+rax+00h]
0x1401d4fd3  cmp     [rsp+2E0h+var_2A0], rbx
0x1401d4fd8  jz      short loc_1401D4FEC
0x1401d4fda  lea     rcx, [rsp+2E0h+var_278]; this
0x1401d4fdf  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x1401d4fe4  cmp     eax, edi
0x1401d4fe6  jnz     loc_1401D5142
0x1401d4fec  lea     rcx, [rsp+2E0h+var_2A0]
0x1401d4ff1  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x1401d4ff8  nop     dword ptr [rax+rax+00h]
0x1401d4ffd  lea     rcx, [rsp+2E0h+var_2A0]
0x1401d5002  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401d5009  nop     dword ptr [rax+rax+00h]
0x1401d500e  mov     rax, [rbp+1E0h+var_68]
0x1401d5015  lea     rcx, [rbp+1E0h+var_250]
0x1401d5019  mov     [rbp+1E0h+var_250], rax
0x1401d501d  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401d5024  nop     dword ptr [rax+rax+00h]
0x1401d5029  jmp     loc_1401D4EC4
0x1401d502e  cmp     r8d, 2
0x1401d5032  jnz     short loc_1401D503D
0x1401d5034  mov     rax, [rsi+20h]
0x1401d5038  jmp     loc_1401D4E46
0x1401d503d  mov     rax, [rsi+18h]
0x1401d5041  jmp     loc_1401D4E46
0x1401d5046  mov     edi, ebx
0x1401d5048  jmp     loc_1401D4D6F
0x1401d504d  mov     r12d, r15d
0x1401d5050  jmp     loc_1401D4C78
0x1401d5055  mov     r8, [rbp+1E0h+pbo]; pbo
0x1401d5059  lea     rdx, [rbp+1E0h+var_1A0]; pco
0x1401d505d  test    r13, r13
0x1401d5060  mov     [rsp+2E0h+var_2C0], r15d; mix
0x1401d5065  mov     r15, [rbp+1E0h+var_258]
0x1401d5069  mov     rax, rsi
0x1401d506c  cmovz   rax, rcx
0x1401d5070  mov     r9, r15; pptlBrushOrg
0x1401d5073  mov     rcx, r13; pso
0x1401d5076  add     [rax], edi
0x1401d5078  call    EngPaint
0x1401d507d  mov     r14d, eax
0x1401d5080  cmp     eax, edi
0x1401d5082  jnz     loc_1401D4FEC
0x1401d5088  lea     rcx, [rsp+2E0h+var_298]; this
0x1401d508d  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x1401d5092  cmp     eax, edi
0x1401d5094  jz      loc_1401D4FEC
0x1401d509a  mov     r8, [rsp+2E0h+var_268]
0x1401d509f  lea     rdx, [rsp+2E0h+var_298]
0x1401d50a4  mov     r9b, 8
0x1401d50a7  lea     rcx, [rsp+2E0h+var_2A0]
0x1401d50ac  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x1401d50b3  nop     dword ptr [rax+rax+00h]
0x1401d50b8  test    eax, eax
0x1401d50ba  jz      loc_1401D5237
0x1401d50c0  mov     rdx, [rsp+2E0h+var_2A0]
0x1401d50c5  lea     r8, [rbp+1E0h+var_1B0]
0x1401d50c9  xor     r9d, r9d
0x1401d50cc  lea     rcx, [rbp+1E0h+var_1A0]
0x1401d50d0  movups  xmm0, xmmword ptr [rdx+34h]
0x1401d50d4  mov     [rbp+1E0h+var_168], rbx
0x1401d50d8  mov     [rbp+1E0h+var_150], rbx
0x1401d50df  movdqu  [rbp+1E0h+var_1B0], xmm0
0x1401d50e4  mov     [rbp+1E0h+var_148], ebx
0x1401d50ea  mov     [rbp+1E0h+var_120], edi
0x1401d50f0  mov     [rbp+1E0h+var_110], rbx
0x1401d50f7  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x1401d50fe  nop     dword ptr [rax+rax+00h]
0x1401d5103  lea     rcx, [rbp+1E0h+var_1A0.rclBounds]; this
0x1401d5107  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
  ... truncated ...
```
