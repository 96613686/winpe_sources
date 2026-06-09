# NtGdiFastPolyPolyline

- ea: `0x140283260`
- end: `0x140283d22`
- name: `NtGdiFastPolyPolyline`
- size: `2754`
- prototype: `__int64 __fastcall(Gre::Base *, struct _POINTL *, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x140063ee0`
- `0x14006c84c`
- `0x14006d5e4`
- `0x14006ec10`
- `0x14007eef8`
- `0x140080590`
- `0x140155c24`
- `0x14015ba5c`
- `0x1401b1e94`
- `0x1401d8c44`
- `0x1401e4828`
- `0x140256df8`
- `0x140283260`
- `0x140287538`
- `0x140303af4`
- `0x140341ff0`
- `0x1403420d0`
- `0x140342540`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402832bd`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1402832bd`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140283433`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1402837ef`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140283433`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1402837ef`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14028331d`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14028331d`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14028367b`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14028367b`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x140283458`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x1402834c7`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x140283458`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x1402834c7`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140283b72`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140283b72`
- `win32kbase!GreDCSelectBrush` at `0x14028337a`
- `win32kbase!GreDCSelectBrush` at `0x14028337a`
- `win32kbase!AllocFreeTmpBuffer` at `0x1402833f7`
- `win32kbase!AllocFreeTmpBuffer` at `0x14028362b`
- `win32kbase!AllocFreeTmpBuffer` at `0x1402833f7`
- `win32kbase!AllocFreeTmpBuffer` at `0x14028362b`
- `win32kbase!FreeTmpBuffer` at `0x1402834e8`
- `win32kbase!FreeTmpBuffer` at `0x140283a1e`
- `win32kbase!FreeTmpBuffer` at `0x140283cbf`
- `win32kbase!FreeTmpBuffer` at `0x140348e1c`
- `win32kbase!FreeTmpBuffer` at `0x1402834e8`
- `win32kbase!FreeTmpBuffer` at `0x140283a1e`
- `win32kbase!FreeTmpBuffer` at `0x140283cbf`
- `win32kbase!FreeTmpBuffer` at `0x140348e1c`
- `win32kbase!GreDCSelectPen` at `0x1402833a2`
- `win32kbase!GreDCSelectPen` at `0x1402833a2`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_VECTORL@@PEAU_VECTORFX@@_K_N@Z` at `0x140283786`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_VECTORL@@PEAU_VECTORFX@@_K_N@Z` at `0x140283786`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU2@_K@Z` at `0x14028380c`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU2@_K@Z` at `0x14028380c`

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
  __int64 v21; // r8
  __int64 v22; // r14
  struct PATHRECORD *v23; // rbx
  __int64 v24; // rax
  int v25; // r8d
  int v26; // r9d
  BOOL v27; // esi
  int v28; // r13d
  struct Gre::Base::SESSION_GLOBALS *v29; // r14
  int v30; // r8d
  int v31; // r9d
  const unsigned int *v32; // rdx
  int v33; // esi
  int v34; // r14d
  int v35; // edx
  int v36; // ecx
  struct ECLIPOBJ *v38; // rdx
  __int64 v39; // rsi
  __int64 v40; // r10
  __int64 v41; // r9
  char *v42; // r15
  __int64 v43; // r8
  char v44; // r12
  struct REGION *v45; // rax
  struct ECLIPOBJ *v46; // rdx
  __int64 v47; // rcx
  unsigned int v48; // eax
  char *v49; // [rsp+70h] [rbp-488h]
  int *v50; // [rsp+80h] [rbp-478h] BYREF
  unsigned int v51; // [rsp+88h] [rbp-470h]
  int v52; // [rsp+8Ch] [rbp-46Ch]
  int v53; // [rsp+90h] [rbp-468h]
  int v54; // [rsp+94h] [rbp-464h]
  unsigned int *v55; // [rsp+98h] [rbp-460h]
  unsigned int *v56; // [rsp+A0h] [rbp-458h]
  unsigned int *v57; // [rsp+A8h] [rbp-450h]
  unsigned int *v58; // [rsp+B0h] [rbp-448h]
  int *v59; // [rsp+B8h] [rbp-440h] BYREF
  bool v60; // [rsp+C0h] [rbp-438h]
  struct Gre::Base::SESSION_GLOBALS *v61[3]; // [rsp+C8h] [rbp-430h] BYREF
  struct ECLIPOBJ *v62[14]; // [rsp+E0h] [rbp-418h] BYREF
  _DWORD v63[2]; // [rsp+150h] [rbp-3A8h] BYREF
  _BYTE *v64; // [rsp+158h] [rbp-3A0h]
  __int128 v65; // [rsp+160h] [rbp-398h]
  __int128 v66; // [rsp+170h] [rbp-388h]
  __int64 v67; // [rsp+180h] [rbp-378h]
  __int64 v68; // [rsp+188h] [rbp-370h]
  __int64 v69; // [rsp+190h] [rbp-368h]
  __int64 v70; // [rsp+198h] [rbp-360h]
  _BYTE v71[176]; // [rsp+1A0h] [rbp-358h] BYREF
  _BYTE v72[32]; // [rsp+250h] [rbp-2A8h] BYREF
  struct PATHRECORD *v73; // [rsp+270h] [rbp-288h]
  struct PATHRECORD *v74; // [rsp+278h] [rbp-280h] BYREF
  struct _POINTL *plResult; // [rsp+280h] [rbp-278h] BYREF
  int v76; // [rsp+288h] [rbp-270h]
  int v77; // [rsp+28Ch] [rbp-26Ch]
  int v78; // [rsp+298h] [rbp-260h]
  __int64 v79; // [rsp+2A0h] [rbp-258h]
  struct _POINTL *v80; // [rsp+390h] [rbp-168h] BYREF
  int v81; // [rsp+398h] [rbp-160h]
  int v82; // [rsp+39Ch] [rbp-15Ch]
  _BYTE v83[112]; // [rsp+3A0h] [rbp-158h] BYREF
  _BYTE v84[4]; // [rsp+410h] [rbp-E8h] BYREF
  _QWORD v85[19]; // [rsp+414h] [rbp-E4h] BYREF

  v4 = a4;
  v57 = a3;
  v80 = a2;
  v58 = a3;
  v7 = 0;
  v8 = 0;
  v61[0] = Gre::Base::Globals(a1);
  APIDCOBJ::APIDCOBJ((APIDCOBJ *)v62, (HDC)a1, v61[0]);
  if ( !v62[0] || (*((_DWORD *)v62[0] + 9) & 0x10000) != 0 )
    goto LABEL_81;
  v9 = *(_DWORD *)(*((_QWORD *)v62[0] + 122) + 208LL);
  DC::QuickInitXform(v62[0], &v50, 516);
  v59 = v50;
  v60 = v9 != 2;
  v10 = (int *)((char *)v62[0] + 208);
  v49 = (char *)v62[0] + 208;
  v50 = (int *)((char *)v62[0] + 208);
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
  v55 = 0;
  v52 = 0;
  v56 = 0;
  v51 = 0;
  if ( (unsigned int)v4 <= 0x3FFFFFFF )
  {
    v14 = 4 * v4;
    if ( (unsigned int)Feature_GdiUMA__private_IsEnabledNoReportingNoInline() )
    {
      v15 = (unsigned int *)AllocFreeTmpBuffer(v14);
      v13 = v15;
      v55 = v15;
      if ( !v15 )
      {
        v8 = 0;
LABEL_18:
        v10 = (int *)v49;
        goto LABEL_19;
      }
      GreProbeAndReadFromUntrustedVa(v15, v14, a3, v14, 1u);
      v16 = v13;
      v56 = v13;
    }
    else
    {
      GreProbeForReadFromUntrustedVa(a3, 4 * v4, 1u);
      v16 = a3;
      v56 = a3;
    }
    v17 = 0;
    v51 = 0;
    v18 = v4;
    v52 = v4;
    do
    {
      v19 = *v16++;
      v56 = v16;
      v17 += v19;
      v51 = v17;
      v20 = v18-- == 1;
      v52 = v18;
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
    v55 = 0;
  }
  if ( !v7 )
    goto LABEL_81;
  if ( (unsigned int)v4 >= 0x8000000 )
    goto LABEL_81;
  if ( v7 >= 0x8000000 )
    goto LABEL_81;
  if ( (*((_DWORD *)v62[0] + 62) & 1) != 0 )
    goto LABEL_81;
  v50 = v10;
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
  v22 = 8 * ((unsigned int)v4 + v7 + 2 * (_DWORD)v4);
  if ( (unsigned int)v22 <= 0x64 )
  {
    v23 = (struct PATHRECORD *)v83;
  }
  else
  {
    v23 = 0;
    if ( (unsigned int)v22 <= 0x2710000 )
      v23 = (struct PATHRECORD *)AllocFreeTmpBuffer((unsigned int)v22);
    if ( !v23 )
      goto LABEL_79;
  }
  DEVLOCKOBJ::DEVLOCKOBJ(v71, 2, v21);
  if ( !DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v71, (struct XDCOBJ *)v62, 0) )
  {
    v48 = XDCOBJ::bFullScreen((XDCOBJ *)v62);
    goto LABEL_75;
  }
  v24 = *((_DWORD *)v62[0] + 10) & 1;
  v25 = *((_DWORD *)v62[0] + 2 * v24 + 254);
  v53 = v25;
  v26 = *((_DWORD *)v62[0] + 2 * v24 + 255);
  v54 = v26;
  v27 = 1;
  v28 = 1;
  if ( (v59[8] & 2) != 0
    && (*(_DWORD *)(*((_QWORD *)v62[0] + 122) + 208LL) == 1 || ((*((_BYTE *)v59 + 24) | *((_BYTE *)v59 + 28)) & 0xF) == 0) )
  {
    v29 = (struct Gre::Base::SESSION_GLOBALS *)v80;
    v30 = v25 + (v59[6] >> 4);
    v31 = v26 + (v59[7] >> 4);
    v32 = v57;
  }
  else
  {
    v29 = (struct PATHRECORD *)((char *)v23 + v22 - 8LL * v7);
    v61[2] = v29;
    if ( *(_DWORD *)(*((_QWORD *)v62[0] + 122) + 208LL) == 2 )
    {
      v28 = 0;
      v27 = EXFORMOBJ::bXform((EXFORMOBJ *)&v59, (const struct _VECTORL *)v80, v29, v7, 0);
      v30 = v59[6] + 16 * v53;
      v31 = v59[7] + 16 * v54;
    }
    else
    {
      v28 = 1;
      GreProbeAndReadFromUntrustedVa(v29, 8LL * v7, v80, 8LL * v7, 1u);
      v27 = EXFORMOBJ::bXform((EXFORMOBJ *)&v59, (const struct _POINTL *)v29, (struct _POINTL *)v29, v7);
      v30 = v53;
      v31 = v54;
    }
    v32 = v57;
  }
  v63[0] = v28 != 0 ? 4 : 0;
  v33 = bMakePathRecords(v23, v32, v7, (struct _POINTL *)v29, v4, v30, v31, (LONG *)&plResult, &v74) & v27;
  v34 = 0;
  if ( v28 )
  {
    v80 = plResult;
    v35 = v76;
    v81 = v76;
    v36 = v77;
    v82 = v77;
    if ( ((unsigned int)plResult & 0xF8000000) != 0 || ((v77 | v76 | HIDWORD(plResult)) & 0xF8000000) != 0 )
      v34 = 1;
    LODWORD(plResult) = 16 * (_DWORD)plResult;
    v76 *= 16;
    HIDWORD(plResult) *= 16;
    v77 *= 16;
  }
  else
  {
    LODWORD(v80) = (int)plResult >> 4;
    HIDWORD(v80) = SHIDWORD(plResult) >> 4;
    v35 = (v76 + 15) >> 4;
    v81 = v35;
    v36 = (v77 + 15) >> 4;
    v82 = v36;
    if ( (v35 ^ v76) < 0 || (v36 ^ v77) < 0 )
      v34 = 1;
  }
  if ( v36 == 0x7FFFFFFF || v35 == 0x7FFFFFFF )
  {
    v34 = 1;
  }
  else
  {
    v82 = v36 + 1;
    v81 = v35 + 1;
  }
  if ( v33 )
  {
    v73 = v23;
    v78 = 0;
    v79 = 0;
    v63[1] = v7 - v4;
    v64 = v72;
    v38 = v62[0];
    if ( (*((_DWORD *)v62[0] + 9) & 0xE0) != 0 )
    {
      XDCOBJ::vAccumulate((XDCOBJ *)v62, v62[0], (struct ERECTL *)&v80);
      v38 = v62[0];
    }
    if ( *((_QWORD *)v38 + 18) == *((_QWORD *)v61[0] + 22) )
      goto LABEL_73;
    v39 = *((_QWORD *)v38 + 62);
    if ( !v39 )
      goto LABEL_73;
    v40 = *(_QWORD *)(v39 + 176);
    v41 = *((_QWORD *)v38 + 11);
    v42 = (char *)v38 + 1336;
    if ( *((_DWORD *)v38 + 334) == -1 )
    {
      *(_DWORD *)(*((_QWORD *)v38 + 122) + 152LL) |= 2u;
      v38 = v62[0];
    }
    v43 = *((_QWORD *)v38 + 122);
    if ( ((*((_BYTE *)v38 + 316) | *(_BYTE *)(v43 + 152)) & 2) != 0 )
    {
      *(_DWORD *)(v43 + 152) &= ~2u;
      *((_DWORD *)v62[0] + 79) &= ~2u;
      EBRUSHOBJ::vInitBrush(v42, v62[0], *((_QWORD *)v62[0] + 18), v41, v40);
      v38 = v62[0];
    }
    v44 = *(_BYTE *)(*((_QWORD *)v38 + 122) + 212LL);
    v45 = XDCOBJ::prgnEffRao((XDCOBJ *)v62);
    ECLIPOBJ::ECLIPOBJ((ECLIPOBJ *)v84, v45, (struct ERECTL *)&v80, v34);
    if ( (unsigned int)ERECTL::bEmpty((ERECTL *)v85) )
    {
LABEL_73:
      v8 = 1;
LABEL_76:
      if ( v23 != (struct PATHRECORD *)v83 )
        FreeTmpBuffer(v23);
      DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v71);
LABEL_79:
      PATH::~PATH((PATH *)v72);
LABEL_81:
      APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v62);
      return v8;
    }
    if ( (*((_DWORD *)v62[0] + 9) & 0xE0) != 0 && (*((_DWORD *)v42 + 30) & 0x100) == 0 )
    {
      v61[0] = (struct Gre::Base::SESSION_GLOBALS *)v85[0];
      v61[1] = (struct Gre::Base::SESSION_GLOBALS *)v85[1];
      XDCOBJ::vAccumulateTight((XDCOBJ *)v62, v46, (struct ERECTL *)v61);
    }
    v47 = v39 + 24;
    ++*(_DWORD *)(v39 + 92);
    if ( (*(_DWORD *)(v39 + 160) & 0x20) != 0 )
      v48 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _BYTE *, _QWORD, char *, _QWORD, char *, unsigned int))(*(_QWORD *)(v39 + 48) + 2792LL))(
              v47,
              v63,
              v84,
              0,
              v42,
              0,
              v49,
              (((v44 - 1) & 0xF) + 1) | ((((v44 - 1) & 0xFu) + 1) << 8));
    else
      v48 = ((__int64 (__fastcall *)(__int64, _DWORD *, _BYTE *, _QWORD, char *, _QWORD, char *, unsigned int))EngStrokePath)(
              v47,
              v63,
              v84,
              0,
              v42,
              0,
              v49,
              (((v44 - 1) & 0xF) + 1) | ((((v44 - 1) & 0xFu) + 1) << 8));
LABEL_75:
    v8 = v48;
    goto LABEL_76;
  }
  if ( v23 != (struct PATHRECORD *)v83 )
    FreeTmpBuffer(v23);
  DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v71);
  PATH::~PATH((PATH *)v72);
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v62);
  return 0;
}

```

## disassembly

```asm
0x140283260  push    rbx
0x140283262  push    rsi
0x140283263  push    r12
0x140283265  push    r13
0x140283267  push    r14
0x140283269  push    r15
0x14028326b  sub     rsp, 4C8h
0x140283272  mov     rax, cs:__security_cookie
0x140283279  xor     rax, rsp
0x14028327c  mov     [rsp+4F8h+var_48], rax
0x140283284  mov     r12d, r9d
0x140283287  mov     r13, r8
0x14028328a  mov     [rsp+4F8h+var_450], r8
0x140283292  mov     [rsp+4F8h+var_168], rdx
0x14028329a  mov     rbx, rcx
0x14028329d  mov     [rsp+4F8h+var_480], rdx
0x1402832a2  mov     [rsp+4F8h+var_448], r8
0x1402832aa  mov     [rsp+4F8h+var_490], r12d
0x1402832af  xor     r15d, r15d
0x1402832b2  mov     [rsp+4F8h+var_49C], r15d
0x1402832b7  xor     esi, esi
0x1402832b9  mov     [rsp+4F8h+var_4A8], esi
0x1402832bd  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1402832c4  nop     dword ptr [rax+rax+00h]
0x1402832c9  mov     [rsp+4F8h+var_430], rax
0x1402832d1  mov     r8, rax; struct Gre::Base::SESSION_GLOBALS *
0x1402832d4  mov     rdx, rbx; HDC
0x1402832d7  lea     rcx, [rsp+4F8h+var_418]; this
0x1402832df  call    ??0APIDCOBJ@@QEAA@PEAUHDC__@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; APIDCOBJ::APIDCOBJ(HDC__ *,Gre::Base::SESSION_GLOBALS &)
0x1402832e4  mov     rcx, [rsp+4F8h+var_418]
0x1402832ec  test    rcx, rcx
0x1402832ef  jz      loc_140283CF0
0x1402832f5  test    dword ptr [rcx+24h], 10000h
0x1402832fc  jnz     loc_140283CF0
0x140283302  mov     rax, [rcx+3D0h]
0x140283309  mov     ebx, [rax+0D0h]
0x14028330f  mov     r8d, 204h
0x140283315  lea     rdx, [rsp+4F8h+var_478]
0x14028331d  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x140283324  nop     dword ptr [rax+rax+00h]
0x140283329  mov     rax, [rsp+4F8h+var_478]
0x140283331  mov     [rsp+4F8h+var_440], rax
0x140283339  cmp     ebx, 2
0x14028333c  setnz   [rsp+4F8h+var_438]
0x140283344  mov     rcx, [rsp+4F8h+var_418]
0x14028334c  lea     r14, [rcx+0D0h]
0x140283353  mov     [rsp+4F8h+var_488], r14
0x140283358  mov     [rsp+4F8h+var_478], r14
0x140283360  mov     rdx, [rcx+3D0h]
0x140283367  mov     ebx, [rdx+98h]
0x14028336d  bt      ebx, 0Ch
0x140283371  jnb     short loc_140283386
0x140283373  mov     rdx, [rdx+0A0h]
0x14028337a  call    cs:__imp_GreDCSelectBrush
0x140283381  nop     dword ptr [rax+rax+00h]
0x140283386  bt      ebx, 0Dh
0x14028338a  jnb     short loc_1402833AE
0x14028338c  mov     rcx, [rsp+4F8h+var_418]
0x140283394  mov     rdx, [rcx+3D0h]
0x14028339b  mov     rdx, [rdx+0A8h]
0x1402833a2  call    cs:__imp_GreDCSelectPen
0x1402833a9  nop     dword ptr [rax+rax+00h]
0x1402833ae  test    r12d, r12d
0x1402833b1  jz      loc_140283CE7
0x1402833b7  xor     ebx, ebx
0x1402833b9  mov     [rsp+4F8h+var_460], rbx
0x1402833c1  mov     [rsp+4F8h+var_46C], ebx
0x1402833c8  mov     [rsp+4F8h+var_458], rbx
0x1402833d0  mov     [rsp+4F8h+var_470], ebx
0x1402833d7  cmp     r12d, 3FFFFFFFh
0x1402833de  ja      loc_1402834E0
0x1402833e4  mov     r14, r12
0x1402833e7  shl     r14, 2
0x1402833eb  call    Feature_GdiUMA__private_IsEnabledNoReportingNoInline
0x1402833f0  test    eax, eax
0x1402833f2  jz      short loc_14028344C
0x1402833f4  mov     ecx, r14d
0x1402833f7  call    cs:__imp_AllocFreeTmpBuffer
0x1402833fe  nop     dword ptr [rax+rax+00h]
0x140283403  mov     rbx, rax
0x140283406  mov     [rsp+4F8h+var_460], rax
0x14028340e  test    rax, rax
0x140283411  jnz     short loc_14028341E
0x140283413  xor     esi, esi
0x140283415  mov     [rsp+4F8h+var_4A8], esi
0x140283419  jmp     loc_1402834DB
0x14028341e  mov     edx, r14d
0x140283421  mov     qword ptr [rsp+4F8h+var_4D8], 1
0x14028342a  mov     r9d, r14d
0x14028342d  mov     r8, r13
0x140283430  mov     rcx, rbx
0x140283433  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14028343a  nop     dword ptr [rax+rax+00h]
0x14028343f  mov     rcx, rbx
0x140283442  mov     [rsp+4F8h+var_458], rbx
0x14028344a  jmp     short loc_14028346F
0x14028344c  mov     r8d, 1
0x140283452  mov     rdx, r14
0x140283455  mov     rcx, r13
0x140283458  call    cs:__imp_?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z; GreProbeForReadFromUntrustedVa(void const *,unsigned __int64,unsigned __int64)
0x14028345f  nop     dword ptr [rax+rax+00h]
0x140283464  mov     rcx, r13
0x140283467  mov     [rsp+4F8h+var_458], rcx
0x14028346f  xor     r14d, r14d
0x140283472  mov     [rsp+4F8h+var_470], r14d
0x14028347a  mov     edx, r12d
0x14028347d  mov     [rsp+4F8h+var_46C], edx
0x140283484  mov     eax, [rcx]
0x140283486  add     rcx, 4
0x14028348a  mov     [rsp+4F8h+var_458], rcx
0x140283492  add     r14d, eax
0x140283495  mov     [rsp+4F8h+var_470], r14d
0x14028349d  add     edx, 0FFFFFFFFh
0x1402834a0  mov     [rsp+4F8h+var_46C], edx
0x1402834a7  jnz     short loc_140283484
0x1402834a9  cmp     r14d, 1FFFFFFFh
0x1402834b0  ja      short loc_1402834DB
0x1402834b2  mov     edx, r14d
0x1402834b5  shl     rdx, 3
0x1402834b9  mov     r8d, 1
0x1402834bf  mov     rcx, [rsp+4F8h+var_168]
0x1402834c7  call    cs:__imp_?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z; GreProbeForReadFromUntrustedVa(void const *,unsigned __int64,unsigned __int64)
0x1402834ce  nop     dword ptr [rax+rax+00h]
0x1402834d3  mov     r15d, r14d
0x1402834d6  mov     [rsp+4F8h+var_49C], r14d
0x1402834db  mov     r14, [rsp+4F8h+var_488]
0x1402834e0  test    rbx, rbx
0x1402834e3  jz      short loc_140283500
0x1402834e5  mov     rcx, rbx
0x1402834e8  call    cs:__imp_FreeTmpBuffer
0x1402834ef  nop     dword ptr [rax+rax+00h]
0x1402834f4  mov     [rsp+4F8h+var_460], 0
0x140283500  jmp     short loc_14028353A
0x140283502  mov     r15d, [rsp+4F8h+var_49C]
0x140283507  mov     esi, [rsp+4F8h+var_4A8]
0x14028350b  mov     rax, [rsp+4F8h+var_480]
0x140283510  mov     [rsp+4F8h+var_168], rax
0x140283518  mov     rax, [rsp+4F8h+var_448]
0x140283520  mov     [rsp+4F8h+var_450], rax
0x140283528  mov     r12d, [rsp+4F8h+var_490]
0x14028352d  mov     r14, [rsp+4F8h+var_478]
0x140283535  mov     [rsp+4F8h+var_488], r14
0x14028353a  test    r15d, r15d
0x14028353d  jz      loc_140283CF0
0x140283543  mov     eax, 8000000h
0x140283548  cmp     r12d, eax
0x14028354b  jnb     loc_140283CF0
0x140283551  cmp     r15d, eax
0x140283554  jnb     loc_140283CF0
0x14028355a  mov     rax, [rsp+4F8h+var_418]
0x140283562  mov     ecx, [rax+0F8h]
0x140283568  test    cl, 1
0x14028356b  jnz     loc_140283CF0
0x140283571  mov     [rsp+4F8h+var_478], r14
0x140283579  mov     eax, [r14]
0x14028357c  test    al, 3
0x14028357e  jnz     loc_140283CF0
0x140283584  cmp     qword ptr [r14+18h], 0
0x140283589  jnz     loc_140283CF0
0x14028358f  mov     [rsp+4F8h+var_4A4], 0
0x140283597  mov     [rsp+4F8h+var_4A0], 0
0x14028359f  mov     [rsp+4F8h+var_360], 0
0x1402835ab  xorps   xmm0, xmm0
0x1402835ae  movdqa  [rsp+4F8h+var_398], xmm0
0x1402835b7  xorps   xmm1, xmm1
0x1402835ba  movdqa  [rsp+4F8h+var_388], xmm1
0x1402835c3  mov     [rsp+4F8h+var_370], 0
0x1402835cf  mov     [rsp+4F8h+var_368], 0
0x1402835db  mov     [rsp+4F8h+var_378], 0
0x1402835e7  lea     rcx, [rsp+4F8h+var_2A8]; this
0x1402835ef  call    ??0PATH@@QEAA@XZ; PATH::PATH(void)
0x1402835f4  xor     edx, edx; Val
0x1402835f6  lea     r8d, [rdx+68h]; Size
0x1402835fa  lea     rcx, [rsp+4F8h+var_158]; void *
0x140283602  call    memset_0
0x140283607  lea     r14d, [r15+r12*2]
0x14028360b  add     r14d, r12d
0x14028360e  shl     r14d, 3
0x140283612  cmp     r14d, 64h ; 'd'
0x140283616  jbe     short loc_140283649
0x140283618  xor     ebx, ebx
0x14028361a  mov     [rsp+4F8h+var_480], rbx
0x14028361f  cmp     r14d, 2710000h
0x140283626  ja      short loc_14028363F
0x140283628  mov     ecx, r14d
0x14028362b  call    cs:__imp_AllocFreeTmpBuffer
0x140283632  nop     dword ptr [rax+rax+00h]
0x140283637  mov     rbx, rax
0x14028363a  mov     [rsp+4F8h+var_480], rax
0x14028363f  test    rbx, rbx
0x140283642  jnz     short loc_140283656
0x140283644  jmp     loc_140283CD8
0x140283649  lea     rbx, [rsp+4F8h+var_158]
0x140283651  mov     [rsp+4F8h+var_480], rbx
0x140283656  mov     edx, 2
0x14028365b  lea     rcx, [rsp+4F8h+var_358]
0x140283663  call    ??0DEVLOCKOBJ@@QEAA@W4U2KMMAPStatus@@@Z; DEVLOCKOBJ::DEVLOCKOBJ(U2KMMAPStatus)
0x140283668  xor     r8d, r8d
0x14028366b  lea     rdx, [rsp+4F8h+var_418]
0x140283673  lea     rcx, [rsp+4F8h+var_358]
0x14028367b  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x140283682  nop     dword ptr [rax+rax+00h]
0x140283687  test    eax, eax
0x140283689  jz      loc_140283C9C
0x14028368f  mov     r10, [rsp+4F8h+var_418]
0x140283697  mov     eax, [r10+28h]
0x14028369b  and     eax, 1
0x14028369e  mov     r8d, [r10+rax*8+3F8h]
0x1402836a6  mov     [rsp+4F8h+var_468], r8d
0x1402836ae  mov     [rsp+4F8h+var_4A4], r8d
0x1402836b3  mov     r9d, [r10+rax*8+3FCh]
0x1402836bb  mov     [rsp+4F8h+var_464], r9d
0x1402836c3  mov     [rsp+4F8h+var_4A0], r9d
0x1402836c8  mov     esi, 1
0x1402836cd  mov     [rsp+4F8h+var_4A8], esi
0x1402836d1  mov     r13d, esi
0x1402836d4  mov     [rsp+4F8h+var_498], esi
0x1402836d8  mov     rax, [rsp+4F8h+var_440]
0x1402836e0  mov     ecx, [rax+20h]
0x1402836e3  test    cl, 2
0x1402836e6  jz      short loc_140283737
0x1402836e8  mov     rcx, [r10+3D0h]
0x1402836ef  cmp     [rcx+0D0h], esi
0x1402836f5  jz      short loc_140283702
0x1402836f7  mov     edx, [rax+1Ch]
0x1402836fa  or      edx, [rax+18h]
0x1402836fd  test    dl, 0Fh
0x140283700  jnz     short loc_140283737
0x140283702  mov     r14, [rsp+4F8h+var_168]
0x14028370a  mov     ecx, [rax+18h]
0x14028370d  sar     ecx, 4
0x140283710  add     ecx, r8d
0x140283713  mov     r8d, ecx
0x140283716  mov     [rsp+4F8h+var_4A4], ecx
0x14028371a  mov     ecx, [rax+1Ch]
0x14028371d  sar     ecx, 4
0x140283720  add     ecx, r9d
0x140283723  mov     r9d, ecx
0x140283726  mov     [rsp+4F8h+var_4A0], ecx
0x14028372a  mov     rdx, [rsp+4F8h+var_450]
0x140283732  jmp     loc_14028387A
0x140283737  mov     esi, r15d
0x14028373a  lea     rax, ds:0[rsi*8]
0x140283742  sub     r14, rax
0x140283745  add     r14, rbx
0x140283748  mov     [rsp+4F8h+var_420], r14
0x140283750  mov     edx, r15d
0x140283753  mov     rax, [r10+3D0h]
0x14028375a  cmp     dword ptr [rax+0D0h], 2
0x140283761  jnz     short loc_1402837CD
0x140283763  xor     r13d, r13d
0x140283766  mov     [rsp+4F8h+var_498], r13d
0x14028376b  mov     byte ptr [rsp+4F8h+var_4D8], r13b
0x140283770  mov     r9d, edx
0x140283773  mov     r8, r14
0x140283776  mov     rdx, [rsp+4F8h+var_168]
0x14028377e  lea     rcx, [rsp+4F8h+var_440]
0x140283786  call    cs:__imp_?bXform@EXFORMOBJ@@QEBA_NPEBU_VECTORL@@PEAU_VECTORFX@@_K_N@Z; EXFORMOBJ::bXform(_VECTORL const *,_VECTORFX *,unsigned __int64,bool)
0x14028378d  nop     dword ptr [rax+rax+00h]
0x140283792  movzx   esi, al
0x140283795  mov     [rsp+4F8h+var_4A8], esi
0x140283799  mov     r8d, [rsp+4F8h+var_468]
0x1402837a1  shl     r8d, 4
0x1402837a5  mov     rax, [rsp+4F8h+var_440]
0x1402837ad  add     r8d, [rax+18h]
0x1402837b1  mov     [rsp+4F8h+var_4A4], r8d
0x1402837b6  mov     r9d, [rsp+4F8h+var_464]
0x1402837be  shl     r9d, 4
0x1402837c2  add     r9d, [rax+1Ch]
0x1402837c6  mov     [rsp+4F8h+var_4A0], r9d
0x1402837cb  jmp     short loc_14028382F
0x1402837cd  mov     r13d, 1
0x1402837d3  mov     [rsp+4F8h+var_498], r13d
0x1402837d8  shl     rdx, 3
0x1402837dc  mov     qword ptr [rsp+4F8h+var_4D8], r13
0x1402837e1  mov     r9, rdx
0x1402837e4  mov     r8, [rsp+4F8h+var_168]
0x1402837ec  mov     rcx, r14
0x1402837ef  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x1402837f6  nop     dword ptr [rax+rax+00h]
0x1402837fb  mov     r9, rsi
0x1402837fe  mov     r8, r14
0x140283801  mov     rdx, r14
0x140283804  lea     rcx, [rsp+4F8h+var_440]
0x14028380c  call    cs:__imp_?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTL@@PEAU2@_K@Z; EXFORMOBJ::bXform(_POINTL const *,_POINTL *,unsigned __int64)
0x140283813  nop     dword ptr [rax+rax+00h]
0x140283818  movzx   esi, al
0x14028381b  mov     [rsp+4F8h+var_4A8], esi
0x14028381f  mov     r8d, [rsp+4F8h+var_468]
0x140283827  mov     r9d, [rsp+4F8h+var_464]
0x14028382f  mov     rdx, [rsp+4F8h+var_450]
0x140283837  jmp     short loc_14028387A
0x140283839  xor     esi, esi
0x14028383b  mov     [rsp+4F8h+var_4A8], esi
0x14028383f  mov     r15d, [rsp+4F8h+var_49C]
0x140283844  mov     r8d, [rsp+4F8h+var_4A4]
0x140283849  mov     r9d, [rsp+4F8h+var_4A0]
0x14028384e  mov     r13d, [rsp+4F8h+var_498]
0x140283853  mov     rbx, [rsp+4F8h+var_480]
0x140283858  mov     r14, [rsp+4F8h+var_420]
  ... truncated ...
```
