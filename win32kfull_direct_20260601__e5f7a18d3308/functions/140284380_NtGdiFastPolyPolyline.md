# NtGdiFastPolyPolyline

- ea: `0x140284380`
- end: `0x140284e3d`
- name: `NtGdiFastPolyPolyline`
- size: `2749`
- prototype: `__int64 __fastcall(HDC)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x14003e7dc`
- `0x140056bc8`
- `0x14005b820`
- `0x14005d010`
- `0x1400697e4`
- `0x14006bd2c`
- `0x14008cfa0`
- `0x14009be70`
- `0x1400a4eb4`
- `0x1401acf04`
- `0x1401d567c`
- `0x1401e22a8`
- `0x140258608`
- `0x140284380`
- `0x140288ef8`
- `0x140342fa0`
- `0x140343080`
- `0x140343500`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402843dd`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402843dd`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140284553`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14028490a`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140284553`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14028490a`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14028443d`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14028443d`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140284796`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140284796`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x140284578`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x1402845e7`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x140284578`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x1402845e7`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140284c8d`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140284c8d`
- `win32kbase!GreDCSelectBrush` at `0x14028449a`
- `win32kbase!GreDCSelectBrush` at `0x14028449a`
- `win32kbase!AllocFreeTmpBuffer` at `0x140284517`
- `win32kbase!AllocFreeTmpBuffer` at `0x14028474b`
- `win32kbase!AllocFreeTmpBuffer` at `0x140284517`
- `win32kbase!AllocFreeTmpBuffer` at `0x14028474b`
- `win32kbase!FreeTmpBuffer` at `0x140284608`
- `win32kbase!FreeTmpBuffer` at `0x140284b39`
- `win32kbase!FreeTmpBuffer` at `0x140284dda`
- `win32kbase!FreeTmpBuffer` at `0x140349dc8`
- `win32kbase!FreeTmpBuffer` at `0x140284608`
- `win32kbase!FreeTmpBuffer` at `0x140284b39`
- `win32kbase!FreeTmpBuffer` at `0x140284dda`
- `win32kbase!FreeTmpBuffer` at `0x140349dc8`
- `win32kbase!GreDCSelectPen` at `0x1402844c2`
- `win32kbase!GreDCSelectPen` at `0x1402844c2`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_VECTORL@@PEAU_VECTORFX@@_K_N@Z` at `0x1402848a1`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_VECTORL@@PEAU_VECTORFX@@_K_N@Z` at `0x1402848a1`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU2@_K@Z` at `0x140284927`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU2@_K@Z` at `0x140284927`

## pseudocode

```c
__int64 __fastcall NtGdiFastPolyPolyline(Gre::Base *a1, struct _POINTL *a2, unsigned int *a3, unsigned int a4)
{
  __int64 v4; // r12
  unsigned int v7; // r15d
  unsigned int v8; // esi
  int v9; // ebx
  int *v10; // r14
  __int64 v11; // rdx
  int v12; // ebx
  unsigned int *v13; // rbx
  unsigned int v14; // r14d
  unsigned int *v15; // rax
  unsigned int *v16; // rcx
  unsigned int v17; // r14d
  int v18; // edx
  int v19; // eax
  bool v20; // zf
  __int64 v21; // r14
  struct PATHRECORD *v22; // rbx
  __int64 v23; // rax
  int v24; // r8d
  int v25; // r9d
  BOOL v26; // esi
  int v27; // r13d
  struct _POINTL *v28; // r14
  int v29; // r8d
  int v30; // r9d
  const unsigned int *v31; // rdx
  int v32; // esi
  int v33; // r14d
  int v34; // edx
  int v35; // ecx
  struct ECLIPOBJ *v37; // rdx
  __int64 v38; // rsi
  __int64 v39; // r10
  __int64 v40; // r9
  char *v41; // r15
  __int64 v42; // r8
  char v43; // r12
  struct REGION *v44; // rax
  struct ECLIPOBJ *v45; // rdx
  __int64 v46; // rcx
  unsigned int v47; // eax
  char *v48; // [rsp+70h] [rbp-478h]
  int *v49; // [rsp+80h] [rbp-468h] BYREF
  unsigned int v50; // [rsp+88h] [rbp-460h]
  int v51; // [rsp+8Ch] [rbp-45Ch]
  int v52; // [rsp+90h] [rbp-458h]
  int v53; // [rsp+94h] [rbp-454h]
  unsigned int *v54; // [rsp+98h] [rbp-450h]
  unsigned int *v55; // [rsp+A0h] [rbp-448h]
  unsigned int *v56; // [rsp+A8h] [rbp-440h]
  unsigned int *v57; // [rsp+B0h] [rbp-438h]
  int *v58; // [rsp+B8h] [rbp-430h] BYREF
  bool v59; // [rsp+C0h] [rbp-428h]
  __m128i v60; // [rsp+C8h] [rbp-420h] BYREF
  struct _POINTL *v61; // [rsp+D8h] [rbp-410h]
  struct ECLIPOBJ *v62[14]; // [rsp+E0h] [rbp-408h] BYREF
  _DWORD v63[2]; // [rsp+150h] [rbp-398h] BYREF
  _BYTE *v64; // [rsp+158h] [rbp-390h]
  __int128 v65; // [rsp+160h] [rbp-388h]
  __int128 v66; // [rsp+170h] [rbp-378h]
  __int64 v67; // [rsp+180h] [rbp-368h]
  __int64 v68; // [rsp+188h] [rbp-360h]
  __int64 v69; // [rsp+190h] [rbp-358h]
  __int64 v70; // [rsp+198h] [rbp-350h]
  HDC v71[20]; // [rsp+1A0h] [rbp-348h] BYREF
  _BYTE v72[32]; // [rsp+240h] [rbp-2A8h] BYREF
  struct PATHRECORD *v73; // [rsp+260h] [rbp-288h]
  struct PATHRECORD *v74; // [rsp+268h] [rbp-280h] BYREF
  struct _POINTL *plResult; // [rsp+270h] [rbp-278h] BYREF
  int v76; // [rsp+278h] [rbp-270h]
  int v77; // [rsp+27Ch] [rbp-26Ch]
  int v78; // [rsp+288h] [rbp-260h]
  __int64 v79; // [rsp+290h] [rbp-258h]
  struct _POINTL *v80; // [rsp+380h] [rbp-168h] BYREF
  int v81; // [rsp+388h] [rbp-160h]
  int v82; // [rsp+38Ch] [rbp-15Ch]
  _BYTE v83[112]; // [rsp+390h] [rbp-158h] BYREF
  _BYTE v84[4]; // [rsp+400h] [rbp-E8h] BYREF
  __m128i v85; // [rsp+404h] [rbp-E4h] BYREF

  v4 = a4;
  v56 = a3;
  v80 = a2;
  v57 = a3;
  v7 = 0;
  v8 = 0;
  v60.m128i_i64[0] = (__int64)Gre::Base::Globals(a1);
  APIDCOBJ::APIDCOBJ((APIDCOBJ *)v62, (HDC)a1, (struct Gre::Base::SESSION_GLOBALS *)v60.m128i_i64[0]);
  if ( !v62[0] || (*((_DWORD *)v62[0] + 9) & 0x10000) != 0 )
    goto LABEL_81;
  v9 = *(_DWORD *)(*((_QWORD *)v62[0] + 122) + 208LL);
  DC::QuickInitXform(v62[0], &v49, 516);
  v58 = v49;
  v59 = v9 != 2;
  v10 = (int *)((char *)v62[0] + 208);
  v48 = (char *)v62[0] + 208;
  v49 = (int *)((char *)v62[0] + 208);
  v11 = *((_QWORD *)v62[0] + 122);
  v12 = *(_DWORD *)(v11 + 152);
  if ( (v12 & 0x1000) != 0 )
    GreDCSelectBrush(v62[0], *(_QWORD *)(v11 + 160));
  if ( (v12 & 0x2000) != 0 )
    GreDCSelectPen(v62[0], *(_QWORD *)(*((_QWORD *)v62[0] + 122) + 168LL));
  if ( !(_DWORD)v4 )
  {
    v8 = 1;
    goto LABEL_81;
  }
  v13 = 0;
  v54 = 0;
  v51 = 0;
  v55 = 0;
  v50 = 0;
  if ( (unsigned int)v4 <= 0x3FFFFFFF )
  {
    v14 = 4 * v4;
    if ( (unsigned int)Feature_GdiUMA__private_IsEnabledNoReportingNoInline() )
    {
      v15 = (unsigned int *)AllocFreeTmpBuffer(v14);
      v13 = v15;
      v54 = v15;
      if ( !v15 )
      {
        v8 = 0;
LABEL_18:
        v10 = (int *)v48;
        goto LABEL_19;
      }
      GreProbeAndReadFromUntrustedVa(v15, v14, a3, v14, 1u);
      v16 = v13;
      v55 = v13;
    }
    else
    {
      GreProbeForReadFromUntrustedVa(a3, 4 * v4, 1u);
      v16 = a3;
      v55 = a3;
    }
    v17 = 0;
    v50 = 0;
    v18 = v4;
    v51 = v4;
    do
    {
      v19 = *v16++;
      v55 = v16;
      v17 += v19;
      v50 = v17;
      v20 = v18-- == 1;
      v51 = v18;
    }
    while ( !v20 );
    if ( v17 <= 0x1FFFFFFF )
    {
      GreProbeForReadFromUntrustedVa(v80, 8LL * v17, 1u);
      v7 = v17;
    }
    goto LABEL_18;
  }
LABEL_19:
  if ( v13 )
  {
    FreeTmpBuffer(v13);
    v54 = 0;
  }
  if ( !v7 )
    goto LABEL_81;
  if ( (unsigned int)v4 >= 0x8000000 )
    goto LABEL_81;
  if ( v7 >= 0x8000000 )
    goto LABEL_81;
  if ( (*((_DWORD *)v62[0] + 62) & 1) != 0 )
    goto LABEL_81;
  v49 = v10;
  if ( (*v10 & 3) != 0 || *((_QWORD *)v10 + 3) )
    goto LABEL_81;
  v70 = 0;
  v65 = 0;
  v66 = 0;
  v68 = 0;
  v69 = 0;
  v67 = 0;
  PATH::PATH((PATH *)v72);
  memset_0(v83, 0, 0x68u);
  v21 = 8 * ((unsigned int)v4 + v7 + 2 * (_DWORD)v4);
  if ( (unsigned int)v21 <= 0x64 )
  {
    v22 = (struct PATHRECORD *)v83;
  }
  else
  {
    v22 = 0;
    if ( (unsigned int)v21 <= 0x2710000 )
      v22 = (struct PATHRECORD *)AllocFreeTmpBuffer((unsigned int)v21);
    if ( !v22 )
      goto LABEL_79;
  }
  DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v71);
  if ( !DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v71, (struct XDCOBJ *)v62, 0) )
  {
    v47 = XDCOBJ::bFullScreen((XDCOBJ *)v62);
    goto LABEL_75;
  }
  v23 = *((_DWORD *)v62[0] + 10) & 1;
  v24 = *((_DWORD *)v62[0] + 2 * v23 + 254);
  v52 = v24;
  v25 = *((_DWORD *)v62[0] + 2 * v23 + 255);
  v53 = v25;
  v26 = 1;
  v27 = 1;
  if ( (v58[8] & 2) != 0
    && (*(_DWORD *)(*((_QWORD *)v62[0] + 122) + 208LL) == 1 || ((*((_BYTE *)v58 + 24) | *((_BYTE *)v58 + 28)) & 0xF) == 0) )
  {
    v28 = v80;
    v29 = v24 + (v58[6] >> 4);
    v30 = v25 + (v58[7] >> 4);
    v31 = v56;
  }
  else
  {
    v28 = (struct _POINTL *)((char *)v22 + v21 - 8LL * v7);
    v61 = v28;
    if ( *(_DWORD *)(*((_QWORD *)v62[0] + 122) + 208LL) == 2 )
    {
      v27 = 0;
      v26 = EXFORMOBJ::bXform((EXFORMOBJ *)&v58, (const struct _VECTORL *)v80, (struct _VECTORFX *)v28, v7, 0);
      v29 = v58[6] + 16 * v52;
      v30 = v58[7] + 16 * v53;
    }
    else
    {
      v27 = 1;
      GreProbeAndReadFromUntrustedVa(v28, 8LL * v7, v80, 8LL * v7, 1u);
      v26 = EXFORMOBJ::bXform((EXFORMOBJ *)&v58, v28, v28, v7);
      v29 = v52;
      v30 = v53;
    }
    v31 = v56;
  }
  v63[0] = v27 != 0 ? 4 : 0;
  v32 = bMakePathRecords(v22, v31, v7, v28, v4, v29, v30, (LONG *)&plResult, &v74) & v26;
  v33 = 0;
  if ( v27 )
  {
    v80 = plResult;
    v34 = v76;
    v81 = v76;
    v35 = v77;
    v82 = v77;
    if ( ((unsigned int)plResult & 0xF8000000) != 0 || ((v77 | v76 | HIDWORD(plResult)) & 0xF8000000) != 0 )
      v33 = 1;
    LODWORD(plResult) = 16 * (_DWORD)plResult;
    v76 *= 16;
    HIDWORD(plResult) *= 16;
    v77 *= 16;
  }
  else
  {
    LODWORD(v80) = (int)plResult >> 4;
    HIDWORD(v80) = SHIDWORD(plResult) >> 4;
    v34 = (v76 + 15) >> 4;
    v81 = v34;
    v35 = (v77 + 15) >> 4;
    v82 = v35;
    if ( (v34 ^ v76) < 0 || (v35 ^ v77) < 0 )
      v33 = 1;
  }
  if ( v35 == 0x7FFFFFFF || v34 == 0x7FFFFFFF )
  {
    v33 = 1;
  }
  else
  {
    v82 = v35 + 1;
    v81 = v34 + 1;
  }
  if ( v32 )
  {
    v73 = v22;
    v78 = 0;
    v79 = 0;
    v63[1] = v7 - v4;
    v64 = v72;
    v37 = v62[0];
    if ( (*((_DWORD *)v62[0] + 9) & 0xE0) != 0 )
    {
      XDCOBJ::vAccumulate((XDCOBJ *)v62, v62[0], (struct ERECTL *)&v80);
      v37 = v62[0];
    }
    if ( *((_QWORD *)v37 + 18) == *(_QWORD *)(v60.m128i_i64[0] + 176) )
      goto LABEL_73;
    v38 = *((_QWORD *)v37 + 62);
    if ( !v38 )
      goto LABEL_73;
    v39 = *(_QWORD *)(v38 + 160);
    v40 = *((_QWORD *)v37 + 11);
    v41 = (char *)v37 + 1336;
    if ( *((_DWORD *)v37 + 334) == -1 )
    {
      *(_DWORD *)(*((_QWORD *)v37 + 122) + 152LL) |= 2u;
      v37 = v62[0];
    }
    v42 = *((_QWORD *)v37 + 122);
    if ( ((*((_BYTE *)v37 + 316) | *(_BYTE *)(v42 + 152)) & 2) != 0 )
    {
      *(_DWORD *)(v42 + 152) &= ~2u;
      *((_DWORD *)v62[0] + 79) &= ~2u;
      EBRUSHOBJ::vInitBrush(v41, v62[0], *((_QWORD *)v62[0] + 18), v40, v39, v38, 0);
      v37 = v62[0];
    }
    v43 = *(_BYTE *)(*((_QWORD *)v37 + 122) + 212LL);
    v44 = XDCOBJ::prgnEffRao((XDCOBJ *)v62);
    ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v84, v44, (struct ERECTL *)&v80, v33);
    if ( (unsigned int)ERECTL::bEmpty((ERECTL *)&v85) )
    {
LABEL_73:
      v8 = 1;
LABEL_76:
      if ( v22 != (struct PATHRECORD *)v83 )
        FreeTmpBuffer(v22);
      DEVLOCKOBJ::~DEVLOCKOBJ(v71);
LABEL_79:
      PATH::~PATH((PATH *)v72);
LABEL_81:
      APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v62);
      return v8;
    }
    if ( (*((_DWORD *)v62[0] + 9) & 0xE0) != 0 && (*((_DWORD *)v41 + 30) & 0x100) == 0 )
    {
      v60 = v85;
      XDCOBJ::vAccumulateTight((XDCOBJ *)v62, v45, &v60);
    }
    v46 = v38 + 24;
    ++*(_DWORD *)(v38 + 92);
    if ( (*(_DWORD *)(v38 + 144) & 0x20) != 0 )
      v47 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _BYTE *, _QWORD, char *, _QWORD, char *, unsigned int))(*(_QWORD *)(v38 + 48) + 2792LL))(
              v46,
              v63,
              v84,
              0,
              v41,
              0,
              v48,
              (((v43 - 1) & 0xF) + 1) | ((((v43 - 1) & 0xFu) + 1) << 8));
    else
      v47 = ((__int64 (__fastcall *)(__int64, _DWORD *, _BYTE *, _QWORD, char *, _QWORD, char *, unsigned int))EngStrokePath)(
              v46,
              v63,
              v84,
              0,
              v41,
              0,
              v48,
              (((v43 - 1) & 0xF) + 1) | ((((v43 - 1) & 0xFu) + 1) << 8));
LABEL_75:
    v8 = v47;
    goto LABEL_76;
  }
  if ( v22 != (struct PATHRECORD *)v83 )
    FreeTmpBuffer(v22);
  DEVLOCKOBJ::~DEVLOCKOBJ(v71);
  PATH::~PATH((PATH *)v72);
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v62);
  return 0;
}

```

## disassembly

```asm
0x140284380  push    rbx
0x140284382  push    rsi
0x140284383  push    r12
0x140284385  push    r13
0x140284387  push    r14
0x140284389  push    r15
0x14028438b  sub     rsp, 4B8h
0x140284392  mov     rax, cs:__security_cookie
0x140284399  xor     rax, rsp
0x14028439c  mov     [rsp+4E8h+var_48], rax
0x1402843a4  mov     r12d, r9d
0x1402843a7  mov     r13, r8
0x1402843aa  mov     [rsp+4E8h+var_440], r8
0x1402843b2  mov     [rsp+4E8h+var_168], rdx
0x1402843ba  mov     rbx, rcx
0x1402843bd  mov     [rsp+4E8h+var_470], rdx
0x1402843c2  mov     [rsp+4E8h+var_438], r8
0x1402843ca  mov     [rsp+4E8h+var_480], r12d
0x1402843cf  xor     r15d, r15d
0x1402843d2  mov     [rsp+4E8h+var_48C], r15d
0x1402843d7  xor     esi, esi
0x1402843d9  mov     [rsp+4E8h+var_498], esi
0x1402843dd  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1402843e4  nop     dword ptr [rax+rax+00h]
0x1402843e9  mov     [rsp+4E8h+var_420], rax
0x1402843f1  mov     r8, rax; struct Gre::Base::SESSION_GLOBALS *
0x1402843f4  mov     rdx, rbx; HDC
0x1402843f7  lea     rcx, [rsp+4E8h+var_408]; this
0x1402843ff  call    ??0APIDCOBJ@@QEAA@PEAUHDC__@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; APIDCOBJ::APIDCOBJ(HDC__ *,Gre::Base::SESSION_GLOBALS &)
0x140284404  mov     rcx, [rsp+4E8h+var_408]
0x14028440c  test    rcx, rcx
0x14028440f  jz      loc_140284E0B
0x140284415  test    dword ptr [rcx+24h], 10000h
0x14028441c  jnz     loc_140284E0B
0x140284422  mov     rax, [rcx+3D0h]
0x140284429  mov     ebx, [rax+0D0h]
0x14028442f  mov     r8d, 204h
0x140284435  lea     rdx, [rsp+4E8h+var_468]
0x14028443d  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x140284444  nop     dword ptr [rax+rax+00h]
0x140284449  mov     rax, [rsp+4E8h+var_468]
0x140284451  mov     [rsp+4E8h+var_430], rax
0x140284459  cmp     ebx, 2
0x14028445c  setnz   [rsp+4E8h+var_428]
0x140284464  mov     rcx, [rsp+4E8h+var_408]
0x14028446c  lea     r14, [rcx+0D0h]
0x140284473  mov     [rsp+4E8h+var_478], r14
0x140284478  mov     [rsp+4E8h+var_468], r14
0x140284480  mov     rdx, [rcx+3D0h]
0x140284487  mov     ebx, [rdx+98h]
0x14028448d  bt      ebx, 0Ch
0x140284491  jnb     short loc_1402844A6
0x140284493  mov     rdx, [rdx+0A0h]
0x14028449a  call    cs:__imp_GreDCSelectBrush
0x1402844a1  nop     dword ptr [rax+rax+00h]
0x1402844a6  bt      ebx, 0Dh
0x1402844aa  jnb     short loc_1402844CE
0x1402844ac  mov     rcx, [rsp+4E8h+var_408]
0x1402844b4  mov     rdx, [rcx+3D0h]
0x1402844bb  mov     rdx, [rdx+0A8h]
0x1402844c2  call    cs:__imp_GreDCSelectPen
0x1402844c9  nop     dword ptr [rax+rax+00h]
0x1402844ce  test    r12d, r12d
0x1402844d1  jz      loc_140284E02
0x1402844d7  xor     ebx, ebx
0x1402844d9  mov     [rsp+4E8h+var_450], rbx
0x1402844e1  mov     [rsp+4E8h+var_45C], ebx
0x1402844e8  mov     [rsp+4E8h+var_448], rbx
0x1402844f0  mov     [rsp+4E8h+var_460], ebx
0x1402844f7  cmp     r12d, 3FFFFFFFh
0x1402844fe  ja      loc_140284600
0x140284504  mov     r14, r12
0x140284507  shl     r14, 2
0x14028450b  call    Feature_GdiUMA__private_IsEnabledNoReportingNoInline
0x140284510  test    eax, eax
0x140284512  jz      short loc_14028456C
0x140284514  mov     ecx, r14d
0x140284517  call    cs:__imp_AllocFreeTmpBuffer
0x14028451e  nop     dword ptr [rax+rax+00h]
0x140284523  mov     rbx, rax
0x140284526  mov     [rsp+4E8h+var_450], rax
0x14028452e  test    rax, rax
0x140284531  jnz     short loc_14028453E
0x140284533  xor     esi, esi
0x140284535  mov     [rsp+4E8h+var_498], esi
0x140284539  jmp     loc_1402845FB
0x14028453e  mov     edx, r14d
0x140284541  mov     qword ptr [rsp+4E8h+var_4C8], 1
0x14028454a  mov     r9d, r14d
0x14028454d  mov     r8, r13
0x140284550  mov     rcx, rbx
0x140284553  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14028455a  nop     dword ptr [rax+rax+00h]
0x14028455f  mov     rcx, rbx
0x140284562  mov     [rsp+4E8h+var_448], rbx
0x14028456a  jmp     short loc_14028458F
0x14028456c  mov     r8d, 1
0x140284572  mov     rdx, r14
0x140284575  mov     rcx, r13
0x140284578  call    cs:__imp_?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z; GreProbeForReadFromUntrustedVa(void const *,unsigned __int64,unsigned __int64)
0x14028457f  nop     dword ptr [rax+rax+00h]
0x140284584  mov     rcx, r13
0x140284587  mov     [rsp+4E8h+var_448], rcx
0x14028458f  xor     r14d, r14d
0x140284592  mov     [rsp+4E8h+var_460], r14d
0x14028459a  mov     edx, r12d
0x14028459d  mov     [rsp+4E8h+var_45C], edx
0x1402845a4  mov     eax, [rcx]
0x1402845a6  add     rcx, 4
0x1402845aa  mov     [rsp+4E8h+var_448], rcx
0x1402845b2  add     r14d, eax
0x1402845b5  mov     [rsp+4E8h+var_460], r14d
0x1402845bd  add     edx, 0FFFFFFFFh
0x1402845c0  mov     [rsp+4E8h+var_45C], edx
0x1402845c7  jnz     short loc_1402845A4
0x1402845c9  cmp     r14d, 1FFFFFFFh
0x1402845d0  ja      short loc_1402845FB
0x1402845d2  mov     edx, r14d
0x1402845d5  shl     rdx, 3
0x1402845d9  mov     r8d, 1
0x1402845df  mov     rcx, [rsp+4E8h+var_168]
0x1402845e7  call    cs:__imp_?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z; GreProbeForReadFromUntrustedVa(void const *,unsigned __int64,unsigned __int64)
0x1402845ee  nop     dword ptr [rax+rax+00h]
0x1402845f3  mov     r15d, r14d
0x1402845f6  mov     [rsp+4E8h+var_48C], r14d
0x1402845fb  mov     r14, [rsp+4E8h+var_478]
0x140284600  test    rbx, rbx
0x140284603  jz      short loc_140284620
0x140284605  mov     rcx, rbx
0x140284608  call    cs:__imp_FreeTmpBuffer
0x14028460f  nop     dword ptr [rax+rax+00h]
0x140284614  mov     [rsp+4E8h+var_450], 0
0x140284620  jmp     short loc_14028465A
0x140284622  mov     r15d, [rsp+4E8h+var_48C]
0x140284627  mov     esi, [rsp+4E8h+var_498]
0x14028462b  mov     rax, [rsp+4E8h+var_470]
0x140284630  mov     [rsp+4E8h+var_168], rax
0x140284638  mov     rax, [rsp+4E8h+var_438]
0x140284640  mov     [rsp+4E8h+var_440], rax
0x140284648  mov     r12d, [rsp+4E8h+var_480]
0x14028464d  mov     r14, [rsp+4E8h+var_468]
0x140284655  mov     [rsp+4E8h+var_478], r14
0x14028465a  test    r15d, r15d
0x14028465d  jz      loc_140284E0B
0x140284663  mov     eax, 8000000h
0x140284668  cmp     r12d, eax
0x14028466b  jnb     loc_140284E0B
0x140284671  cmp     r15d, eax
0x140284674  jnb     loc_140284E0B
0x14028467a  mov     rax, [rsp+4E8h+var_408]
0x140284682  mov     ecx, [rax+0F8h]
0x140284688  test    cl, 1
0x14028468b  jnz     loc_140284E0B
0x140284691  mov     [rsp+4E8h+var_468], r14
0x140284699  mov     eax, [r14]
0x14028469c  test    al, 3
0x14028469e  jnz     loc_140284E0B
0x1402846a4  cmp     qword ptr [r14+18h], 0
0x1402846a9  jnz     loc_140284E0B
0x1402846af  mov     [rsp+4E8h+var_494], 0
0x1402846b7  mov     [rsp+4E8h+var_490], 0
0x1402846bf  mov     [rsp+4E8h+var_350], 0
0x1402846cb  xorps   xmm0, xmm0
0x1402846ce  movdqa  [rsp+4E8h+var_388], xmm0
0x1402846d7  xorps   xmm1, xmm1
0x1402846da  movdqa  [rsp+4E8h+var_378], xmm1
0x1402846e3  mov     [rsp+4E8h+var_360], 0
0x1402846ef  mov     [rsp+4E8h+var_358], 0
0x1402846fb  mov     [rsp+4E8h+var_368], 0
0x140284707  lea     rcx, [rsp+4E8h+var_2A8]; this
0x14028470f  call    ??0PATH@@QEAA@XZ; PATH::PATH(void)
0x140284714  xor     edx, edx; Val
0x140284716  lea     r8d, [rdx+68h]; Size
0x14028471a  lea     rcx, [rsp+4E8h+var_158]; void *
0x140284722  call    memset_0
0x140284727  lea     r14d, [r15+r12*2]
0x14028472b  add     r14d, r12d
0x14028472e  shl     r14d, 3
0x140284732  cmp     r14d, 64h ; 'd'
0x140284736  jbe     short loc_140284769
0x140284738  xor     ebx, ebx
0x14028473a  mov     [rsp+4E8h+var_470], rbx
0x14028473f  cmp     r14d, 2710000h
0x140284746  ja      short loc_14028475F
0x140284748  mov     ecx, r14d
0x14028474b  call    cs:__imp_AllocFreeTmpBuffer
0x140284752  nop     dword ptr [rax+rax+00h]
0x140284757  mov     rbx, rax
0x14028475a  mov     [rsp+4E8h+var_470], rax
0x14028475f  test    rbx, rbx
0x140284762  jnz     short loc_140284776
0x140284764  jmp     loc_140284DF3
0x140284769  lea     rbx, [rsp+4E8h+var_158]
0x140284771  mov     [rsp+4E8h+var_470], rbx
0x140284776  lea     rcx, [rsp+4E8h+var_348]; this
0x14028477e  call    ??0DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::DEVLOCKOBJ(void)
0x140284783  xor     r8d, r8d
0x140284786  lea     rdx, [rsp+4E8h+var_408]
0x14028478e  lea     rcx, [rsp+4E8h+var_348]
0x140284796  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x14028479d  nop     dword ptr [rax+rax+00h]
0x1402847a2  test    eax, eax
0x1402847a4  jz      loc_140284DB7
0x1402847aa  mov     r10, [rsp+4E8h+var_408]
0x1402847b2  mov     eax, [r10+28h]
0x1402847b6  and     eax, 1
0x1402847b9  mov     r8d, [r10+rax*8+3F8h]
0x1402847c1  mov     [rsp+4E8h+var_458], r8d
0x1402847c9  mov     [rsp+4E8h+var_494], r8d
0x1402847ce  mov     r9d, [r10+rax*8+3FCh]
0x1402847d6  mov     [rsp+4E8h+var_454], r9d
0x1402847de  mov     [rsp+4E8h+var_490], r9d
0x1402847e3  mov     esi, 1
0x1402847e8  mov     [rsp+4E8h+var_498], esi
0x1402847ec  mov     r13d, esi
0x1402847ef  mov     [rsp+4E8h+var_488], esi
0x1402847f3  mov     rax, [rsp+4E8h+var_430]
0x1402847fb  mov     ecx, [rax+20h]
0x1402847fe  test    cl, 2
0x140284801  jz      short loc_140284852
0x140284803  mov     rcx, [r10+3D0h]
0x14028480a  cmp     [rcx+0D0h], esi
0x140284810  jz      short loc_14028481D
0x140284812  mov     edx, [rax+1Ch]
0x140284815  or      edx, [rax+18h]
0x140284818  test    dl, 0Fh
0x14028481b  jnz     short loc_140284852
0x14028481d  mov     r14, [rsp+4E8h+var_168]
0x140284825  mov     ecx, [rax+18h]
0x140284828  sar     ecx, 4
0x14028482b  add     ecx, r8d
0x14028482e  mov     r8d, ecx
0x140284831  mov     [rsp+4E8h+var_494], ecx
0x140284835  mov     ecx, [rax+1Ch]
0x140284838  sar     ecx, 4
0x14028483b  add     ecx, r9d
0x14028483e  mov     r9d, ecx
0x140284841  mov     [rsp+4E8h+var_490], ecx
0x140284845  mov     rdx, [rsp+4E8h+var_440]
0x14028484d  jmp     loc_140284995
0x140284852  mov     esi, r15d
0x140284855  lea     rax, ds:0[rsi*8]
0x14028485d  sub     r14, rax
0x140284860  add     r14, rbx
0x140284863  mov     [rsp+4E8h+var_410], r14
0x14028486b  mov     edx, r15d
0x14028486e  mov     rax, [r10+3D0h]
0x140284875  cmp     dword ptr [rax+0D0h], 2
0x14028487c  jnz     short loc_1402848E8
0x14028487e  xor     r13d, r13d
0x140284881  mov     [rsp+4E8h+var_488], r13d
0x140284886  mov     byte ptr [rsp+4E8h+var_4C8], r13b
0x14028488b  mov     r9d, edx
0x14028488e  mov     r8, r14
0x140284891  mov     rdx, [rsp+4E8h+var_168]
0x140284899  lea     rcx, [rsp+4E8h+var_430]
0x1402848a1  call    cs:__imp_?bXform@EXFORMOBJ@@QEBA_NPEBU_VECTORL@@PEAU_VECTORFX@@_K_N@Z; EXFORMOBJ::bXform(_VECTORL const *,_VECTORFX *,unsigned __int64,bool)
0x1402848a8  nop     dword ptr [rax+rax+00h]
0x1402848ad  movzx   esi, al
0x1402848b0  mov     [rsp+4E8h+var_498], esi
0x1402848b4  mov     r8d, [rsp+4E8h+var_458]
0x1402848bc  shl     r8d, 4
0x1402848c0  mov     rax, [rsp+4E8h+var_430]
0x1402848c8  add     r8d, [rax+18h]
0x1402848cc  mov     [rsp+4E8h+var_494], r8d
0x1402848d1  mov     r9d, [rsp+4E8h+var_454]
0x1402848d9  shl     r9d, 4
0x1402848dd  add     r9d, [rax+1Ch]
0x1402848e1  mov     [rsp+4E8h+var_490], r9d
0x1402848e6  jmp     short loc_14028494A
0x1402848e8  mov     r13d, 1
0x1402848ee  mov     [rsp+4E8h+var_488], r13d
0x1402848f3  shl     rdx, 3
0x1402848f7  mov     qword ptr [rsp+4E8h+var_4C8], r13
0x1402848fc  mov     r9, rdx
0x1402848ff  mov     r8, [rsp+4E8h+var_168]
0x140284907  mov     rcx, r14
0x14028490a  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140284911  nop     dword ptr [rax+rax+00h]
0x140284916  mov     r9, rsi
0x140284919  mov     r8, r14
0x14028491c  mov     rdx, r14
0x14028491f  lea     rcx, [rsp+4E8h+var_430]
0x140284927  call    cs:__imp_?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU2@_K@Z; EXFORMOBJ::bXform(_POINTL const *,_POINTL *,unsigned __int64)
0x14028492e  nop     dword ptr [rax+rax+00h]
0x140284933  movzx   esi, al
0x140284936  mov     [rsp+4E8h+var_498], esi
0x14028493a  mov     r8d, [rsp+4E8h+var_458]
0x140284942  mov     r9d, [rsp+4E8h+var_454]
0x14028494a  mov     rdx, [rsp+4E8h+var_440]
0x140284952  jmp     short loc_140284995
0x140284954  xor     esi, esi
0x140284956  mov     [rsp+4E8h+var_498], esi
0x14028495a  mov     r15d, [rsp+4E8h+var_48C]
0x14028495f  mov     r8d, [rsp+4E8h+var_494]
0x140284964  mov     r9d, [rsp+4E8h+var_490]
0x140284969  mov     r13d, [rsp+4E8h+var_488]
0x14028496e  mov     rbx, [rsp+4E8h+var_470]
0x140284973  mov     r14, [rsp+4E8h+var_410]
0x14028497b  mov     rax, [rsp+4E8h+var_468]
  ... truncated ...
```
