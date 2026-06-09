# EngFillPath

- ea: `0x14011d640`
- end: `0x14011db1b`
- name: `EngFillPath`
- size: `1243`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, BRUSHOBJ *pbo, POINTL *pptlBrushOrg, MIX mix, FLONG flOptions)`
- caller_count: `9`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14011afe0`
- `0x14011bfb4`
- `0x14011cd0c`
- `0x140128240`
- `0x14016b910`
- `0x1402a1400`
- `0x1402a2c30`
- `0x1403197a0`
- `0x14032bd08`

## callees

- `0x1400620a8`
- `0x14006ec10`
- `0x1400f8e58`
- `0x14011d640`
- `0x14011db24`
- `0x14013d844`
- `0x14016c040`
- `0x1402037e8`
- `0x14022c3ac`
- `0x140341ff0`

## import_xrefs

- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011d832`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011d8b6`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011d832`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011d8b6`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14011d8a5`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x14011d8a5`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14011d908`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14011d935`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14011d9ea`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14011dae3`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14011d908`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14011d935`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14011d9ea`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14011dae3`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011d8f7`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011d924`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011d9d9`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011dad2`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011d8f7`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011d924`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011d9d9`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x14011dad2`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14011d973`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14011da77`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14011d973`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14011da77`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14011d8de`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14011d8de`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x14011d6cc`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x14011d6cc`
- `win32kbase!EngSetLastError` at `0x14011d857`
- `win32kbase!EngSetLastError` at `0x14011da0a`
- `win32kbase!EngSetLastError` at `0x14011d857`
- `win32kbase!EngSetLastError` at `0x14011da0a`
- `win32kbase!?bFlatten@EPATHOBJ@@QEAA_NXZ` at `0x14011d78b`
- `win32kbase!?bFlatten@EPATHOBJ@@QEAA_NXZ` at `0x14011d78b`
- `win32kbase!?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z` at `0x14011d817`
- `win32kbase!?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z` at `0x14011d817`

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
  __int64 v21; // r8
  __int64 v22; // r9
  POINTL *v23; // r9
  BRUSHOBJ *v24; // r8
  BYTE v25; // dl
  __int64 v26; // rax
  struct REGION *v27; // r11
  POINTL *v28; // r9
  BRUSHOBJ *v29; // r8
  BYTE iDComplexity; // cl
  __int64 p_iUniq; // rax
  struct REGION *v32; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h]
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  struct REGION *v35; // [rsp+58h] [rbp-A8h] BYREF
  POINTL *v36; // [rsp+60h] [rbp-A0h]
  BRUSHOBJ *pboa; // [rsp+68h] [rbp-98h]
  __int128 v38; // [rsp+70h] [rbp-90h] BYREF
  __int128 v39; // [rsp+80h] [rbp-80h] BYREF
  RECTL v40; // [rsp+90h] [rbp-70h] BYREF
  CLIPOBJ pcoa; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+D8h] [rbp-28h]
  __int64 v43; // [rsp+F0h] [rbp-10h]
  int v44; // [rsp+F8h] [rbp-8h]
  int v45; // [rsp+120h] [rbp+20h]
  __int64 v46; // [rsp+130h] [rbp+30h]
  CLIPOBJ v47; // [rsp+140h] [rbp+40h] BYREF
  __int64 v48; // [rsp+178h] [rbp+78h]
  __int64 v49; // [rsp+190h] [rbp+90h]
  int v50; // [rsp+198h] [rbp+98h]
  int v51; // [rsp+1C0h] [rbp+C0h]
  __int64 v52; // [rsp+1D0h] [rbp+D0h]

  v7 = 1;
  v36 = pptlBrushOrg;
  fl = ppo->fl;
  pboa = pbo;
  if ( (fl & 1) != 0 && !EPATHOBJ::bFlatten((EPATHOBJ *)ppo) )
    return 0;
  p_hdev = (__int64)&pso->hdev;
  p_rclBounds = &pco->rclBounds;
  if ( !pso )
    p_hdev = 48;
  v35 = *(struct REGION **)p_hdev;
  if ( v35 )
    PDEVOBJ::vSync((PDEVOBJ *)&v35, pso, &pco->rclBounds, 0);
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
  result = EngFastFill(pso, ppo, v15, pboa, v36, mix, flOptions);
  if ( result < 0 )
  {
LABEL_18:
    v17 = pco->iDComplexity == 0;
    v38 = 0;
    if ( v17 )
    {
      v18 = 0;
    }
    else
    {
      v18 = (struct _RECTL *)&v38;
      DWORD1(v38) = 16 * pco->rclBounds.top;
      HIDWORD(v38) = 16 * pco->rclBounds.bottom;
    }
    v19 = ppo->fl;
    v33 = 0;
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
    v32 = v20;
    if ( v20
      || (v33 = 1,
          v35 = 0,
          RGNMEMOBJ::vCreate((RGNMEMOBJ *)&v35, (struct EPATHOBJ *)ppo, flOptions, v18),
          v32 = v35,
          RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v32),
          v32) )
    {
      if ( (unsigned int)RGNOBJ::iComplexity((RGNOBJ *)&v32) != 1 )
      {
        v40 = *p_rclBounds;
        if ( (unsigned int)EPATHOBJ::bPreComputedFill((EPATHOBJ *)ppo) || pco->iDComplexity )
        {
          v34 = 0;
          RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v34, 0x70u);
          RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v34);
          if ( !v34 )
          {
            EngSetLastError(8u);
            RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v34);
            goto LABEL_44;
          }
          if ( !RGNOBJ::bMerge((RGNOBJ *)&v34, (struct RGNOBJ *)&v32, (struct RGNOBJ *)&pco[2].rclBounds.top, 8u) )
          {
            RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v34);
            RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v34);
            if ( v33 )
            {
              RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v32);
              RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v32);
            }
            return 0;
          }
          v39 = *(_OWORD *)(v34 + 52);
          ERECTL::operator*=(&v39, &pco->rclBounds, v21, v22);
          v48 = 0;
          v49 = 0;
          v50 = 0;
          v51 = 1;
          v52 = 0;
          XCLIPOBJ::vSetup((XCLIPOBJ *)&v47, v27, (const struct ERECTL *)&v39, 0);
          if ( (unsigned int)ERECTL::bEmpty((ERECTL *)&v47.rclBounds) )
          {
            RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v34);
            goto LABEL_45;
          }
          v28 = v36;
          v29 = pboa;
          iDComplexity = v47.iDComplexity;
          if ( !v47.iDComplexity )
            iDComplexity = 1;
          v47.iDComplexity = iDComplexity;
          p_iUniq = (__int64)&pso->iUniq;
          if ( !pso )
            p_iUniq = 92;
          ++*(_DWORD *)p_iUniq;
          v7 = EngPaint(pso, &v47, v29, v28, mix);
          RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v34);
          RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v34);
        }
        else
        {
          v42 = 0;
          v43 = 0;
          v44 = 0;
          v45 = 1;
          v46 = 0;
          XCLIPOBJ::vSetup((XCLIPOBJ *)&pcoa, v32, (const struct ERECTL *)&v40, 0);
          if ( (unsigned int)ERECTL::bEmpty((ERECTL *)&pcoa.rclBounds) )
          {
LABEL_45:
            RGNMEMOBJTMPIFNEEDED::~RGNMEMOBJTMPIFNEEDED((RGNMEMOBJTMPIFNEEDED *)&v32);
            return v7;
          }
          v23 = v36;
          v24 = pboa;
          v25 = pcoa.iDComplexity;
          if ( !pcoa.iDComplexity )
            v25 = 1;
          pcoa.iDComplexity = v25;
          v26 = (__int64)&pso->iUniq;
          if ( !pso )
            v26 = 92;
          ++*(_DWORD *)v26;
          v7 = EngPaint(pso, &pcoa, v24, v23, mix);
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
    if ( v33 )
    {
      RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v32);
      RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v32);
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x14011d640  push    rbp
0x14011d642  push    rbx
0x14011d643  push    rsi
0x14011d644  push    rdi
0x14011d645  push    r12
0x14011d647  push    r13
0x14011d649  push    r14
0x14011d64b  push    r15
0x14011d64d  lea     rbp, [rsp-0F8h]
0x14011d655  sub     rsp, 1F8h
0x14011d65c  mov     rax, cs:__security_cookie
0x14011d663  xor     rax, rsp
0x14011d666  mov     [rbp+130h+var_50], rax
0x14011d66d  mov     rax, [rbp+130h+pptlBrushOrg]
0x14011d674  mov     ebx, 1
0x14011d679  mov     r12d, [rbp+130h+flOptions]
0x14011d680  mov     rsi, r8
0x14011d683  mov     [rsp+230h+var_1D0], rax
0x14011d688  mov     rdi, rdx
0x14011d68b  mov     eax, [rdx]
0x14011d68d  mov     r15, rcx
0x14011d690  mov     [rsp+230h+pbo], r9
0x14011d695  test    bl, al
0x14011d697  jnz     loc_14011D788
0x14011d69d  test    r15, r15
0x14011d6a0  lea     rax, [r15+18h]
0x14011d6a4  mov     ecx, 30h ; '0'
0x14011d6a9  lea     r14, [rsi+4]
0x14011d6ad  cmovz   rax, rcx
0x14011d6b1  mov     rax, [rax]
0x14011d6b4  mov     [rsp+230h+var_1D8], rax
0x14011d6b9  test    rax, rax
0x14011d6bc  jz      short loc_14011D6D8
0x14011d6be  xor     r9d, r9d
0x14011d6c1  lea     rcx, [rsp+230h+var_1D8]
0x14011d6c6  mov     r8, r14
0x14011d6c9  mov     rdx, r15
0x14011d6cc  call    cs:__imp_?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z; PDEVOBJ::vSync(_SURFOBJ *,_RECTL *,ulong)
0x14011d6d3  nop     dword ptr [rax+rax+00h]
0x14011d6d8  test    dword ptr [rdi], 4000h
0x14011d6de  mov     r13d, [rbp+130h+mix]
0x14011d6e5  jnz     loc_14011D7A8
0x14011d6eb  cmp     byte ptr [rsi+14h], 3
0x14011d6ef  jz      loc_14011D7B8
0x14011d6f5  mov     rcx, [rdi+8]
0x14011d6f9  mov     eax, [rcx+30h]
0x14011d6fc  sar     eax, 4
0x14011d6ff  cmp     [r14], eax
0x14011d702  jg      loc_14011D7A3
0x14011d708  movsxd  rax, dword ptr [rcx+38h]
0x14011d70c  add     rax, 0Fh
0x14011d710  sar     rax, 4
0x14011d714  cmp     [rsi+0Ch], eax
0x14011d717  jl      loc_14011D7A3
0x14011d71d  mov     eax, [rcx+34h]
0x14011d720  sar     eax, 4
0x14011d723  cmp     [rsi+8], eax
0x14011d726  jg      short loc_14011D7A3
0x14011d728  movsxd  rax, dword ptr [rcx+3Ch]
0x14011d72c  xor     r8d, r8d; struct _RECTL *
0x14011d72f  add     rax, 0Fh
0x14011d733  sar     rax, 4
0x14011d737  cmp     [rsi+10h], eax
0x14011d73a  jl      short loc_14011D7A3
0x14011d73c  mov     rax, [rsp+230h+var_1D0]
0x14011d741  mov     rdx, rdi; struct _PATHOBJ *
0x14011d744  mov     r9, [rsp+230h+pbo]; struct _BRUSHOBJ *
0x14011d749  mov     rcx, r15; struct _SURFOBJ *
0x14011d74c  mov     [rsp+230h+var_200], r12d; unsigned int
0x14011d751  mov     [rsp+230h+var_208], r13d; unsigned int
0x14011d756  mov     qword ptr [rsp+230h+var_210], rax; struct _POINTL *
0x14011d75b  call    ?EngFastFill@@YAJPEAU_SURFOBJ@@PEAU_PATHOBJ@@PEAU_RECTL@@PEAU_BRUSHOBJ@@PEAU_POINTL@@KK@Z; EngFastFill(_SURFOBJ *,_PATHOBJ *,_RECTL *,_BRUSHOBJ *,_POINTL *,ulong,ulong)
0x14011d760  test    eax, eax
0x14011d762  js      short loc_14011D7B8
0x14011d764  mov     rcx, [rbp+130h+var_50]
0x14011d76b  xor     rcx, rsp; StackCookie
0x14011d76e  call    __security_check_cookie
0x14011d773  add     rsp, 1F8h
0x14011d77a  pop     r15
0x14011d77c  pop     r14
0x14011d77e  pop     r13
0x14011d780  pop     r12
0x14011d782  pop     rdi
0x14011d783  pop     rsi
0x14011d784  pop     rbx
0x14011d785  pop     rbp
0x14011d786  retn
0x14011d788  mov     rcx, rdi
0x14011d78b  call    cs:__imp_?bFlatten@EPATHOBJ@@QEAA_NXZ; EPATHOBJ::bFlatten(void)
0x14011d792  nop     dword ptr [rax+rax+00h]
0x14011d797  test    al, al
0x14011d799  jnz     loc_14011D69D
0x14011d79f  xor     eax, eax
0x14011d7a1  jmp     short loc_14011D764
0x14011d7a3  mov     r8, r14
0x14011d7a6  jmp     short loc_14011D73C
0x14011d7a8  mov     rcx, rdi; this
0x14011d7ab  call    ?bPreComputedFill@EPATHOBJ@@QEBAHXZ; EPATHOBJ::bPreComputedFill(void)
0x14011d7b0  test    eax, eax
0x14011d7b2  jz      loc_14011D6EB
0x14011d7b8  cmp     byte ptr [rsi+14h], 0
0x14011d7bc  xorps   xmm0, xmm0
0x14011d7bf  movups  [rsp+230h+var_1C0], xmm0
0x14011d7c4  jz      loc_14011D9FD
0x14011d7ca  mov     eax, [rsi+8]
0x14011d7cd  lea     r9, [rsp+230h+var_1C0]
0x14011d7d2  shl     eax, 4
0x14011d7d5  mov     dword ptr [rsp+230h+var_1C0+4], eax
0x14011d7d9  mov     eax, [rsi+10h]
0x14011d7dc  shl     eax, 4
0x14011d7df  mov     dword ptr [rsp+230h+var_1C0+0Ch], eax
0x14011d7e3  mov     eax, [rdi]
0x14011d7e5  mov     [rsp+230h+var_1E8], 0
0x14011d7ed  test    al, 10h
0x14011d7ef  jnz     loc_14011DAF4
0x14011d7f5  mov     rax, [rdi+10h]
0x14011d7f9  mov     [rsp+230h+var_1F0], rax
0x14011d7fe  test    rax, rax
0x14011d801  jnz     short loc_14011D868
0x14011d803  mov     r8d, r12d
0x14011d806  mov     [rsp+230h+var_1E8], ebx
0x14011d80a  mov     rdx, rdi
0x14011d80d  mov     [rsp+230h+var_1D8], rax
0x14011d812  lea     rcx, [rsp+230h+var_1D8]
0x14011d817  call    cs:__imp_?vCreate@RGNMEMOBJ@@QEAAXAEAVEPATHOBJ@@KPEAU_RECTL@@@Z; RGNMEMOBJ::vCreate(EPATHOBJ &,ulong,_RECTL *)
0x14011d81e  nop     dword ptr [rax+rax+00h]
0x14011d823  mov     rax, [rsp+230h+var_1D8]
0x14011d828  lea     rcx, [rsp+230h+var_1F0]
0x14011d82d  mov     [rsp+230h+var_1F0], rax
0x14011d832  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x14011d839  nop     dword ptr [rax+rax+00h]
0x14011d83e  xor     r12d, r12d
0x14011d841  cmp     [rsp+230h+var_1F0], r12
0x14011d846  jnz     short loc_14011D86B
0x14011d848  cmp     dword ptr [rdi+4], 2
0x14011d84c  jb      loc_14011D9CD
0x14011d852  lea     ecx, [r12+8]; iError
0x14011d857  call    cs:__imp_EngSetLastError
0x14011d85e  nop     dword ptr [rax+rax+00h]
0x14011d863  jmp     loc_14011DA20
0x14011d868  xor     r12d, r12d
0x14011d86b  lea     rcx, [rsp+230h+var_1F0]; this
0x14011d870  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x14011d875  cmp     eax, ebx
0x14011d877  jz      loc_14011D9CD
0x14011d87d  movups  xmm0, xmmword ptr [r14]
0x14011d881  mov     rcx, rdi; this
0x14011d884  movdqu  [rbp+130h+var_1A0], xmm0
0x14011d889  call    ?bPreComputedFill@EPATHOBJ@@QEBAHXZ; EPATHOBJ::bPreComputedFill(void)
0x14011d88e  test    eax, eax
0x14011d890  jz      loc_14011D946
0x14011d896  mov     edx, 70h ; 'p'
0x14011d89b  mov     [rsp+230h+var_1E0], r12
0x14011d8a0  lea     rcx, [rsp+230h+var_1E0]
0x14011d8a5  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x14011d8ac  nop     dword ptr [rax+rax+00h]
0x14011d8b1  lea     rcx, [rsp+230h+var_1E0]
0x14011d8b6  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x14011d8bd  nop     dword ptr [rax+rax+00h]
0x14011d8c2  cmp     [rsp+230h+var_1E0], r12
0x14011d8c7  jz      loc_14011DA05
0x14011d8cd  lea     r8, [rsi+38h]
0x14011d8d1  mov     r9b, 8
0x14011d8d4  lea     rdx, [rsp+230h+var_1F0]
0x14011d8d9  lea     rcx, [rsp+230h+var_1E0]
0x14011d8de  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x14011d8e5  nop     dword ptr [rax+rax+00h]
0x14011d8ea  test    eax, eax
0x14011d8ec  jnz     loc_14011DA2F
0x14011d8f2  lea     rcx, [rsp+230h+var_1E0]
0x14011d8f7  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14011d8fe  nop     dword ptr [rax+rax+00h]
0x14011d903  lea     rcx, [rsp+230h+var_1E0]
0x14011d908  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14011d90f  nop     dword ptr [rax+rax+00h]
0x14011d914  cmp     [rsp+230h+var_1E8], r12d
0x14011d919  jz      loc_14011D79F
0x14011d91f  lea     rcx, [rsp+230h+var_1F0]
0x14011d924  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14011d92b  nop     dword ptr [rax+rax+00h]
0x14011d930  lea     rcx, [rsp+230h+var_1F0]
0x14011d935  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14011d93c  nop     dword ptr [rax+rax+00h]
0x14011d941  jmp     loc_14011D79F
0x14011d946  cmp     [rsi+14h], r12b
0x14011d94a  jnz     loc_14011D896
0x14011d950  mov     rdx, [rsp+230h+var_1F0]
0x14011d955  lea     r8, [rbp+130h+var_1A0]
0x14011d959  xor     r9d, r9d
0x14011d95c  mov     [rbp+130h+var_158], r12
0x14011d960  lea     rcx, [rbp+130h+pco]
0x14011d964  mov     [rbp+130h+var_140], r12
0x14011d968  mov     [rbp+130h+var_138], r12d
0x14011d96c  mov     [rbp+130h+var_110], ebx
0x14011d96f  mov     [rbp+130h+var_100], r12
0x14011d973  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x14011d97a  nop     dword ptr [rax+rax+00h]
0x14011d97f  lea     rcx, [rbp+130h+pco.rclBounds]; this
0x14011d983  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x14011d988  test    eax, eax
0x14011d98a  jnz     loc_14011DA23
0x14011d990  movzx   eax, [rbp+130h+pco.iDComplexity]
0x14011d994  mov     ecx, 5Ch ; '\'
0x14011d999  mov     r9, [rsp+230h+var_1D0]; pptlBrushOrg
0x14011d99e  test    al, al
0x14011d9a0  mov     r8, [rsp+230h+pbo]; pbo
0x14011d9a5  mov     edx, eax
0x14011d9a7  cmovz   edx, ebx
0x14011d9aa  mov     [rsp+230h+var_210], r13d; mix
0x14011d9af  test    r15, r15
0x14011d9b2  mov     [rbp+130h+pco.iDComplexity], dl
0x14011d9b5  lea     rax, [r15+44h]
0x14011d9b9  cmovz   rax, rcx
0x14011d9bd  lea     rdx, [rbp+130h+pco]; pco
0x14011d9c1  mov     rcx, r15; pso
0x14011d9c4  add     [rax], ebx
0x14011d9c6  call    EngPaint
0x14011d9cb  mov     ebx, eax
0x14011d9cd  cmp     [rsp+230h+var_1E8], r12d
0x14011d9d2  jz      short loc_14011D9F6
0x14011d9d4  lea     rcx, [rsp+230h+var_1F0]
0x14011d9d9  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14011d9e0  nop     dword ptr [rax+rax+00h]
0x14011d9e5  lea     rcx, [rsp+230h+var_1F0]
0x14011d9ea  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14011d9f1  nop     dword ptr [rax+rax+00h]
0x14011d9f6  mov     eax, ebx
0x14011d9f8  jmp     loc_14011D764
0x14011d9fd  xor     r9d, r9d
0x14011da00  jmp     loc_14011D7E3
0x14011da05  mov     ecx, 8; iError
0x14011da0a  call    cs:__imp_EngSetLastError
0x14011da11  nop     dword ptr [rax+rax+00h]
0x14011da16  lea     rcx, [rsp+230h+var_1E0]; this
0x14011da1b  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14011da20  mov     ebx, r12d
0x14011da23  lea     rcx, [rsp+230h+var_1F0]; this
0x14011da28  call    ??1RGNMEMOBJTMPIFNEEDED@@QEAA@XZ; RGNMEMOBJTMPIFNEEDED::~RGNMEMOBJTMPIFNEEDED(void)
0x14011da2d  jmp     short loc_14011D9F6
0x14011da2f  mov     r11, [rsp+230h+var_1E0]
0x14011da34  lea     rcx, [rbp+130h+var_1B0]
0x14011da38  mov     rdx, r14
0x14011da3b  movups  xmm0, xmmword ptr [r11+34h]
0x14011da40  movdqu  [rbp+130h+var_1B0], xmm0
0x14011da45  call    ??XERECTL@@QEAAAEAV0@AEBU_RECTL@@@Z; ERECTL::operator*=(_RECTL const &)
0x14011da4a  xor     r9d, r9d
0x14011da4d  mov     [rbp+130h+var_B8], r12
0x14011da51  lea     r8, [rbp+130h+var_1B0]
0x14011da55  mov     [rbp+130h+var_A0], r12
0x14011da5c  mov     rdx, r11
0x14011da5f  mov     [rbp+130h+var_98], r12d
0x14011da66  lea     rcx, [rbp+130h+var_F0]
0x14011da6a  mov     [rbp+130h+var_70], ebx
0x14011da70  mov     [rbp+130h+var_60], r12
0x14011da77  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x14011da7e  nop     dword ptr [rax+rax+00h]
0x14011da83  lea     rcx, [rbp+130h+var_F0.rclBounds]; this
0x14011da87  call    ?bEmpty@ERECTL@@QEBAHXZ; ERECTL::bEmpty(void)
0x14011da8c  test    eax, eax
0x14011da8e  jnz     short loc_14011DB0C
0x14011da90  movzx   eax, [rbp+130h+var_F0.iDComplexity]
0x14011da94  lea     rdx, [rbp+130h+var_F0]; pco
0x14011da98  mov     r9, [rsp+230h+var_1D0]; pptlBrushOrg
0x14011da9d  test    al, al
0x14011da9f  mov     r8, [rsp+230h+pbo]; pbo
0x14011daa4  mov     ecx, eax
0x14011daa6  cmovz   ecx, ebx
0x14011daa9  mov     [rsp+230h+var_210], r13d; mix
0x14011daae  mov     [rbp+130h+var_F0.iDComplexity], cl
0x14011dab1  lea     rax, [r15+44h]
0x14011dab5  mov     ecx, 5Ch ; '\'
0x14011daba  test    r15, r15
0x14011dabd  cmovz   rax, rcx
0x14011dac1  mov     rcx, r15; pso
0x14011dac4  add     [rax], ebx
0x14011dac6  call    EngPaint
0x14011dacb  lea     rcx, [rsp+230h+var_1E0]
0x14011dad0  mov     ebx, eax
0x14011dad2  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14011dad9  nop     dword ptr [rax+rax+00h]
0x14011dade  lea     rcx, [rsp+230h+var_1E0]
0x14011dae3  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14011daea  nop     dword ptr [rax+rax+00h]
0x14011daef  jmp     loc_14011D9CD
0x14011daf4  cmp     r12d, 2
0x14011daf8  jnz     short loc_14011DB03
0x14011dafa  mov     rax, [rdi+20h]
0x14011dafe  jmp     loc_14011D7F9
0x14011db03  mov     rax, [rdi+18h]
0x14011db07  jmp     loc_14011D7F9
0x14011db0c  lea     rcx, [rsp+230h+var_1E0]; this
0x14011db11  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14011db16  jmp     loc_14011DA23
```
