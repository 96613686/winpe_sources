# GrepLineTo(XDCOBJ &,int,int)

- ea: `0x14005c5f0`
- end: `0x14005cffe`
- name: `?GrepLineTo@@YAHAEAVXDCOBJ@@HH@Z`
- size: `2574`
- prototype: `__int64 __fastcall(struct XDCOBJ *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14018b7b0`

## callees

- `0x14003de60`
- `0x140056bc8`
- `0x14005c5f0`
- `0x14005d010`
- `0x140067498`
- `0x1400697e4`
- `0x14006be04`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005c718`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005cb14`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005c718`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005cb14`
- `win32kbase!PopThreadGuardedObject` at `0x14005c840`
- `win32kbase!PopThreadGuardedObject` at `0x14005c840`
- `win32kbase!PushThreadGuardedObject` at `0x14005c74d`
- `win32kbase!PushThreadGuardedObject` at `0x14005c773`
- `win32kbase!PushThreadGuardedObject` at `0x14005c74d`
- `win32kbase!PushThreadGuardedObject` at `0x14005c773`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14005ce79`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14005ce79`
- `win32kbase!EngSetLastError` at `0x14005c80b`
- `win32kbase!EngSetLastError` at `0x14005ced8`
- `win32kbase!EngSetLastError` at `0x14005cef7`
- `win32kbase!EngSetLastError` at `0x14005cfd3`
- `win32kbase!EngSetLastError` at `0x14005c80b`
- `win32kbase!EngSetLastError` at `0x14005ced8`
- `win32kbase!EngSetLastError` at `0x14005cef7`
- `win32kbase!EngSetLastError` at `0x14005cfd3`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14005c65e`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14005c65e`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14005c7ae`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14005c7ae`
- `win32kbase!?vUnlock@EPATHOBJ@@QEAAXXZ` at `0x14005c81b`
- `win32kbase!?vUnlock@EPATHOBJ@@QEAAXXZ` at `0x14005c81b`
- `win32kbase!??1PATH_CORE@@QEAA@XZ` at `0x14005c82b`
- `win32kbase!??1PATH_CORE@@QEAA@XZ` at `0x14005c82b`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x14005cbe1`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x14005cbe1`
- `win32kbase!GreDCSelectBrush` at `0x14005c6a3`
- `win32kbase!GreDCSelectBrush` at `0x14005c6a3`
- `win32kbase!GreDCSelectPen` at `0x14005c6c6`
- `win32kbase!GreDCSelectPen` at `0x14005c6c6`
- `win32kbase!?bPolyLineTo@EPATHOBJ@@QEAA_NPEBVEXFORMOBJR@@AEBV?$umptr_r@U_POINTL@@@@K@Z` at `0x14005cce4`
- `win32kbase!?bPolyLineTo@EPATHOBJ@@QEAA_NPEBVEXFORMOBJR@@AEBV?$umptr_r@U_POINTL@@@@K@Z` at `0x14005cce4`

## pseudocode

```c
__int64 __fastcall GrepLineTo(struct XDCOBJ *a1, unsigned int a2, unsigned int a3)
{
  __int64 v4; // rcx
  unsigned int v5; // r12d
  unsigned int v6; // r14d
  unsigned int v7; // esi
  int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rdx
  LINEATTRS *v11; // r15
  int v12; // edi
  int v13; // edi
  Gre::Base *v14; // rcx
  struct Gre::Base::SESSION_GLOBALS *v15; // rax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r15
  int v19; // eax
  int v21; // eax
  int v22; // r8d
  int *v23; // rcx
  int v24; // r8d
  int v25; // r9d
  __int32 v26; // r10d
  __int32 v27; // r11d
  int v28; // r12d
  int v29; // r13d
  __int64 v30; // rdx
  _DWORD *v31; // rcx
  __int64 v32; // rdx
  int v33; // r8d
  int v34; // edx
  int v35; // r14d
  __int32 v36; // r9d
  int v37; // r12d
  __int32 v38; // r8d
  __int32 v39; // r10d
  __int32 v40; // edx
  __int32 v41; // r9d
  int v42; // r11d
  _DWORD *v43; // r14
  __int32 v44; // r8d
  __int32 v45; // r10d
  int v46; // eax
  int v47; // edx
  int v48; // r9d
  struct Gre::Base::SESSION_GLOBALS *v49; // rax
  _DWORD *v50; // rcx
  XCLIPOBJ *v51; // r13
  _DWORD *v52; // r14
  __int64 v53; // r8
  struct ECLIPOBJ *v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rdx
  __int64 *v57; // r9
  __int64 v58; // r9
  char v59; // r8
  __int64 v60; // r9
  struct REGION *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rcx
  int v64; // [rsp+50h] [rbp-B0h]
  int v65; // [rsp+54h] [rbp-ACh]
  __int32 v66; // [rsp+58h] [rbp-A8h]
  unsigned int v68; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v69; // [rsp+64h] [rbp-9Ch]
  LINEATTRS *v70; // [rsp+68h] [rbp-98h] BYREF
  __m128i v71; // [rsp+70h] [rbp-90h] BYREF
  __int64 v72; // [rsp+80h] [rbp-80h]
  __int16 v73; // [rsp+88h] [rbp-78h]
  int v74; // [rsp+90h] [rbp-70h]
  int v75; // [rsp+94h] [rbp-6Ch]
  unsigned int v76; // [rsp+98h] [rbp-68h]
  BOOL (__stdcall *v77)(SURFOBJ *, CLIPOBJ *, BRUSHOBJ *, LONG, LONG, LONG, LONG, RECTL *, MIX); // [rsp+A0h] [rbp-60h]
  struct _RECTFX v78; // [rsp+A8h] [rbp-58h] BYREF
  __m128i v79; // [rsp+C0h] [rbp-40h] BYREF
  struct _PATHOBJ v80[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v81; // [rsp+E0h] [rbp-20h]
  int v82; // [rsp+E8h] [rbp-18h]
  __int64 v83; // [rsp+F0h] [rbp-10h] BYREF
  int v84; // [rsp+F8h] [rbp-8h]
  struct Gre::Base::SESSION_GLOBALS *v85; // [rsp+100h] [rbp+0h]
  __int64 v86; // [rsp+108h] [rbp+8h]
  __int128 v87; // [rsp+110h] [rbp+10h] BYREF
  __int128 v88; // [rsp+120h] [rbp+20h] BYREF
  __int128 v89; // [rsp+130h] [rbp+30h] BYREF
  __int128 v90; // [rsp+140h] [rbp+40h]
  __int16 v91; // [rsp+150h] [rbp+50h]
  __int64 v92; // [rsp+158h] [rbp+58h]
  _QWORD v93[70]; // [rsp+160h] [rbp+60h] BYREF

  v4 = *(_QWORD *)a1;
  v5 = a3;
  v6 = a2;
  v76 = a2;
  if ( (*(_DWORD *)(v4 + 36) & 0x10000) != 0 )
  {
    EngSetLastError(6u);
    return 0;
  }
  v7 = 1;
  v8 = *(_DWORD *)(*(_QWORD *)(v4 + 976) + 208LL);
  DC::QuickInitXform(v4, &v70, 516);
  v9 = *(_QWORD *)a1;
  LOBYTE(v78.xRight) = v8 != 2;
  *(_QWORD *)&v78.xLeft = v70;
  v10 = *(_QWORD *)(v9 + 976);
  v11 = (LINEATTRS *)(v9 + 208);
  v70 = (LINEATTRS *)(v9 + 208);
  v12 = *(_DWORD *)(v10 + 152);
  if ( (v12 & 0x1000) != 0 )
    GreDCSelectBrush(v9, *(_QWORD *)(v10 + 160));
  if ( (v12 & 0x2000) != 0 )
    GreDCSelectPen(*(_QWORD *)a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 976LL) + 168LL));
  v13 = 0;
  if ( (v11->fl & 0xB) != 0 )
    goto LABEL_14;
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 248LL) & 1) != 0 )
    goto LABEL_14;
  v14 = (Gre::Base *)*(unsigned int *)(*(_QWORD *)&v78.xLeft + 32LL);
  if ( ((unsigned __int8)v14 & 2) == 0 && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 976LL) + 208LL) == 2 )
    goto LABEL_14;
  v83 = 0;
  v84 = 0;
  v15 = Gre::Base::Globals(v14);
  v86 = 0;
  v85 = v15;
  v83 = 0;
  v84 = 0;
  v87 = 0;
  v88 = 0;
  PushThreadGuardedObject(
    &v87,
    &v83,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  v89 = 0;
  v90 = 0;
  PushThreadGuardedObject(&v89, &v83, UnexpectedThreadTerminationHandler<DLODCOBJ>::OnUnexpectedThreadTerminationStatic);
  v91 = 256;
  *(_OWORD *)&v80[0].fl = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v93[1] = 0;
  v93[0] = 0;
  v92 = 0;
  v16 = DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v80, a1, 0);
  v17 = *(_QWORD *)a1;
  v18 = *(_QWORD *)(*(_QWORD *)a1 + 496LL);
  if ( !v16 )
  {
    if ( !v18 || (v19 = *(_DWORD *)(v17 + 36), (v19 & 0x1000) != 0) && (v19 & 0x4000) == 0 )
      v13 = 1;
    v7 = v13;
LABEL_20:
    DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v80);
    return v7;
  }
  if ( !v18 )
  {
LABEL_12:
    DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v80);
LABEL_13:
    v11 = v70;
LABEL_14:
    v68 = v6;
    v69 = v5;
    PATHSTACKOBJ::PATHSTACKOBJ((PATHSTACKOBJ *)v80, (DC **)a1, 1);
    if ( v80[1] )
    {
      v71.m128i_i64[1] = 1;
      v71.m128i_i64[0] = (__int64)&v68;
      v72 = 0;
      v73 = 0;
      if ( (unsigned __int8)EPATHOBJ::bPolyLineTo(v80, &v78, &v71) )
      {
        v56 = *(_QWORD *)a1;
        if ( (*(_DWORD *)(*(_QWORD *)&v80[1] + 72LL) & 1) != 0 )
          v57 = (__int64 *)(*(_QWORD *)&v80[1] + 64LL);
        else
          v57 = (__int64 *)(*(_QWORD *)(*(_QWORD *)&v80[1] + 40LL)
                          + 8 * ((unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v80[1] + 40LL) + 20LL) - 1) + 3LL));
        v58 = *v57;
        *(_DWORD *)(*(_QWORD *)(v56 + 976) + 152LL) &= 0xFFFFFCFF;
        *(_DWORD *)(*(_QWORD *)(v56 + 976) + 216LL) = v68;
        *(_DWORD *)(*(_QWORD *)(v56 + 976) + 220LL) = v69;
        *(_QWORD *)(*(_QWORD *)(v56 + 976) + 8LL) = v58;
        if ( (*(_DWORD *)(*(_QWORD *)a1 + 248LL) & 1) == 0
          && !(unsigned int)EPATHOBJ_bStrokeAndOrFill(v80, a1, v11, &v78, 1u) )
        {
          v7 = 0;
        }
      }
    }
    else
    {
      EngSetLastError(8u);
    }
    EPATHOBJ::vUnlock((EPATHOBJ *)v80);
    PATH_CORE::~PATH_CORE((PATH_CORE *)v93);
    if ( (_DWORD)v90 )
      PopThreadGuardedObject(&v88);
    return v7;
  }
  v21 = *(_DWORD *)(v18 + 144);
  if ( (v21 & 0x100) != 0 )
  {
    v77 = *(BOOL (__stdcall **)(SURFOBJ *, CLIPOBJ *, BRUSHOBJ *, LONG, LONG, LONG, LONG, RECTL *, MIX))(*(_QWORD *)(v17 + 48) + 2928LL);
    if ( !v77 )
      goto LABEL_12;
  }
  else
  {
    if ( *(_WORD *)(v18 + 100) || (v21 & 0x20) != 0 )
      goto LABEL_12;
    v77 = EngLineTo;
  }
  v22 = *(_DWORD *)(*(_QWORD *)&v78.xLeft + 32LL);
  if ( (v22 & 2) == 0 )
  {
    v71.m128i_i64[0] = __PAIR64__(v5, v6);
    v59 = v22 & 0x43;
    v60 = *(_QWORD *)(v17 + 976);
    if ( (*(_DWORD *)(v60 + 152) & 0x200) != 0 )
    {
      v28 = *(_DWORD *)(v60 + 216);
      v71.m128i_i32[2] = v28;
      v64 = v28;
      v29 = *(_DWORD *)(*(_QWORD *)(v17 + 976) + 220LL);
      v65 = v29;
      v71.m128i_i32[3] = v29;
      if ( v59 == 67 )
      {
LABEL_84:
        v26 = v71.m128i_i32[0];
        v27 = v71.m128i_i32[1];
        goto LABEL_31;
      }
      bCvtPts1(*(_QWORD *)&v78.xLeft, &v71, 2);
      v29 = v71.m128i_i32[3];
      v28 = v71.m128i_i32[2];
    }
    else
    {
      if ( v59 != 67 )
        bCvtPts1(*(_QWORD *)&v78.xLeft, &v71, 1);
      v63 = *(_QWORD *)(*(_QWORD *)a1 + 976LL);
      v28 = *(int *)(v63 + 8) >> 4;
      v29 = *(int *)(v63 + 12) >> 4;
    }
    v65 = v29;
    v64 = v28;
    goto LABEL_84;
  }
  v23 = *(int **)(v17 + 976);
  v24 = *(int *)(*(_QWORD *)&v78.xLeft + 24LL) >> 4;
  v25 = *(int *)(*(_QWORD *)&v78.xLeft + 28LL) >> 4;
  v26 = v6 + v24;
  v27 = v5 + v25;
  if ( (v23[38] & 0x100) != 0 )
  {
    v28 = v23[2] >> 4;
    v29 = v23[3] >> 4;
    v65 = v29;
    v64 = v28;
  }
  else
  {
    v28 = v24 + v23[54];
    v29 = v25 + v23[55];
    v64 = v28;
    v65 = v29;
  }
LABEL_31:
  if ( (unsigned int)(v26 + 134217726) > 0xFFFFFFC || (unsigned int)(v27 + 134217726) > 0xFFFFFFC )
  {
    EngSetLastError(0x57u);
    DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v80);
    return 0;
  }
  else
  {
    v30 = *(_QWORD *)a1;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 976LL) + 152LL) &= 0xFFFFFCFF;
    *(_DWORD *)(*(_QWORD *)(v30 + 976) + 216LL) = v6;
    *(_DWORD *)(*(_QWORD *)(v30 + 976) + 220LL) = a3;
    *(_DWORD *)(*(_QWORD *)(v30 + 976) + 8LL) = 16 * v26;
    *(_DWORD *)(*(_QWORD *)(v30 + 976) + 12LL) = 16 * v27;
    v31 = *(_DWORD **)a1;
    v32 = 2LL * (*(_DWORD *)(*(_QWORD *)a1 + 40LL) & 1);
    v33 = *(_DWORD *)(v32 * 4 + *(_QWORD *)a1 + 1016);
    v66 = v33 + v28;
    if ( (unsigned int)(v33 + v28 + 134217726) <= 0xFFFFFFC )
    {
      v34 = v31[v32 + 255];
      v35 = v34 + v29;
      v75 = v34 + v29;
      if ( (unsigned int)(v34 + v29 + 134217726) <= 0xFFFFFFC )
      {
        v36 = v33 + v26;
        v74 = v33 + v26;
        if ( (unsigned int)(v33 + v26 + 134217726) <= 0xFFFFFFC )
        {
          v37 = v34 + v27;
          if ( (unsigned int)(v34 + v27 + 134217726) <= 0xFFFFFFC )
          {
            if ( v66 > v36 )
            {
              v38 = v33 + v26;
              v79.m128i_i32[0] = v36;
              v39 = v66 + 1;
            }
            else
            {
              v38 = v66;
              v79.m128i_i32[0] = v66;
              v39 = v36 + 1;
            }
            v79.m128i_i32[2] = v39;
            if ( v35 > v37 )
            {
              v40 = v34 + v27;
              v41 = v35 + 1;
            }
            else
            {
              v40 = v34 + v29;
              v41 = v37 + 1;
            }
            v79.m128i_i32[3] = v41;
            v79.m128i_i32[1] = v40;
            v42 = v31[9];
            if ( (v42 & 0xE0) != 0 )
            {
              v43 = v31 + 256;
              if ( (v31[10] & 1) == 0 )
                v43 = v31 + 254;
              v44 = v38 - *v43;
              v45 = v39 - *v43;
              v46 = v43[1];
              v47 = v40 - v46;
              v48 = v41 - v46;
              if ( (v42 & 0x20) != 0 )
              {
                if ( v44 < v31[266] )
                  v31[266] = v44;
                if ( v47 < v31[267] )
                  v31[267] = v47;
                if ( v45 > v31[268] )
                  v31[268] = v45;
                if ( v48 > v31[269] )
                  v31[269] = v48;
              }
              v31 = *(_DWORD **)a1;
              if ( (*(_DWORD *)(*(_QWORD *)a1 + 36LL) & 0x80u) != 0 )
              {
                if ( v44 < v31[274] )
                  v31[274] = v44;
                if ( v47 < v31[275] )
                  v31[275] = v47;
                if ( v45 > v31[276] )
                  v31[276] = v45;
                if ( v48 > v31[277] )
                  v31[277] = v48;
              }
            }
            v49 = Gre::Base::Globals((Gre::Base *)v31);
            v50 = *(_DWORD **)a1;
            if ( *(_QWORD *)(*(_QWORD *)a1 + 144LL) != *((_QWORD *)v49 + 22) )
            {
              if ( v79.m128i_i32[0] >= v50[250]
                && v79.m128i_i32[2] <= v50[252]
                && v79.m128i_i32[1] >= v50[251]
                && (v51 = 0, v79.m128i_i32[3] <= v50[253])
                || (v51 = (XCLIPOBJ *)(v50 + 442),
                    v61 = XDCOBJ::prgnEffRao(a1),
                    XCLIPOBJ::vSetup(v51, v61, (const struct ERECTL *)&v79, 0),
                    *((_DWORD *)v51 + 1) != *((_DWORD *)v51 + 3))
                && *((_DWORD *)v51 + 2) != *((_DWORD *)v51 + 4) )
              {
                v52 = (_DWORD *)(*(_QWORD *)a1 + 1336LL);
                if ( *v52 == -1 )
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 976LL) + 152LL) |= 2u;
                v53 = *(_QWORD *)(*(_QWORD *)a1 + 976LL);
                v54 = (struct ECLIPOBJ *)*(unsigned int *)(v53 + 152);
                if ( ((*(_BYTE *)(*(_QWORD *)a1 + 316LL) | *(_BYTE *)(v53 + 152)) & 2) != 0 )
                {
                  *(_DWORD *)(v53 + 152) = (unsigned int)v54 & 0xFFFFFFFD;
                  *(_DWORD *)(*(_QWORD *)a1 + 316LL) &= ~2u;
                  EBRUSHOBJ::vInitBrush(
                    v52,
                    *(_QWORD *)a1,
                    *(_QWORD *)(*(_QWORD *)a1 + 144LL),
                    *(_QWORD *)(*(_QWORD *)a1 + 88LL),
                    *(_QWORD *)(v18 + 160),
                    v18,
                    0);
                }
                if ( (*(_DWORD *)(*(_QWORD *)a1 + 36LL) & 0xE0) != 0 && (v52[30] & 0x100) == 0 )
                {
                  v71 = v79;
                  XDCOBJ::vAccumulateTight(a1, v54, &v71);
                }
                ++*(_DWORD *)(v18 + 92);
                if ( !((unsigned int (__fastcall *)(__int64, XCLIPOBJ *, _DWORD *, _QWORD, int, int, int, __m128i *, int))v77)(
                        v18 + 24,
                        v51,
                        v52,
                        (unsigned int)v66,
                        v75,
                        v74,
                        v37,
                        &v79,
                        (((*(_BYTE *)(*(_QWORD *)(*(_QWORD *)a1 + 976LL) + 212LL) - 1) & 0xF) + 1)
                      | ((((*(_BYTE *)(*(_QWORD *)(*(_QWORD *)a1 + 976LL) + 212LL) - 1) & 0xF) + 1) << 8)) )
                {
                  v55 = *(_QWORD *)a1;
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 976LL) + 152LL) &= ~0x200u;
                  *(_DWORD *)(*(_QWORD *)(v55 + 976) + 152LL) |= 0x100u;
                  *(_DWORD *)(*(_QWORD *)(v55 + 976) + 8LL) = 16 * v64;
                  *(_DWORD *)(*(_QWORD *)(v55 + 976) + 12LL) = 16 * v65;
                  DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v80);
                  v6 = v76;
                  v5 = a3;
                  goto LABEL_13;
                }
              }
            }
            goto LABEL_20;
          }
          v28 = v64;
        }
      }
    }
    EngSetLastError(0x57u);
    v62 = *(_QWORD *)a1;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 976LL) + 152LL) &= ~0x200u;
    *(_DWORD *)(*(_QWORD *)(v62 + 976) + 152LL) |= 0x100u;
    *(_DWORD *)(*(_QWORD *)(v62 + 976) + 8LL) = 16 * v28;
    *(_DWORD *)(*(_QWORD *)(v62 + 976) + 12LL) = 16 * v29;
    DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v80);
    return 0;
  }
}

```

## disassembly

```asm
0x14005c5f0  mov     [rsp-8+arg_18], rbx
0x14005c5f5  push    rbp
0x14005c5f6  push    rsi
0x14005c5f7  push    rdi
0x14005c5f8  push    r12
0x14005c5fa  push    r13
0x14005c5fc  push    r14
0x14005c5fe  push    r15
0x14005c600  lea     rbp, [rsp-2A0h]
0x14005c608  sub     rsp, 3A0h
0x14005c60f  mov     rax, cs:__security_cookie
0x14005c616  xor     rax, rsp
0x14005c619  mov     [rbp+2D0h+var_40], rax
0x14005c620  mov     rbx, rcx
0x14005c623  mov     [rsp+3D0h+var_374], r8d
0x14005c628  mov     rcx, [rcx]
0x14005c62b  mov     r12d, r8d
0x14005c62e  mov     r14d, edx
0x14005c631  mov     [rbp+2D0h+var_338], edx
0x14005c634  test    dword ptr [rcx+24h], 10000h
0x14005c63b  jnz     loc_14005CED3
0x14005c641  mov     rax, [rcx+3D0h]
0x14005c648  lea     rdx, [rsp+3D0h+var_368]
0x14005c64d  mov     r8d, 204h
0x14005c653  mov     esi, 1
0x14005c658  mov     edi, [rax+0D0h]
0x14005c65e  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x14005c665  nop     dword ptr [rax+rax+00h]
0x14005c66a  mov     rcx, [rbx]
0x14005c66d  cmp     edi, 2
0x14005c670  mov     rax, [rsp+3D0h+var_368]
0x14005c675  setnz   byte ptr [rbp+2D0h+var_328.xRight]
0x14005c679  mov     qword ptr [rbp+2D0h+var_328.xLeft], rax
0x14005c67d  mov     rdx, [rcx+3D0h]
0x14005c684  lea     r15, [rcx+0D0h]
0x14005c68b  mov     [rsp+3D0h+var_368], r15
0x14005c690  mov     edi, [rdx+98h]
0x14005c696  bt      edi, 0Ch
0x14005c69a  jnb     short loc_14005C6AF
0x14005c69c  mov     rdx, [rdx+0A0h]
0x14005c6a3  call    cs:__imp_GreDCSelectBrush
0x14005c6aa  nop     dword ptr [rax+rax+00h]
0x14005c6af  bt      edi, 0Dh
0x14005c6b3  jnb     short loc_14005C6D2
0x14005c6b5  mov     rcx, [rbx]
0x14005c6b8  mov     rdx, [rcx+3D0h]
0x14005c6bf  mov     rdx, [rdx+0A8h]
0x14005c6c6  call    cs:__imp_GreDCSelectPen
0x14005c6cd  nop     dword ptr [rax+rax+00h]
0x14005c6d2  mov     eax, [r15]
0x14005c6d5  xor     edi, edi
0x14005c6d7  test    al, 0Bh
0x14005c6d9  jnz     loc_14005C7E3
0x14005c6df  mov     rdx, [rbx]
0x14005c6e2  mov     eax, [rdx+0F8h]
0x14005c6e8  test    sil, al
0x14005c6eb  jnz     loc_14005C7E3
0x14005c6f1  mov     rax, qword ptr [rbp+2D0h+var_328.xLeft]
0x14005c6f5  mov     ecx, [rax+20h]
0x14005c6f8  test    cl, 2
0x14005c6fb  jnz     short loc_14005C711
0x14005c6fd  mov     rax, [rdx+3D0h]
0x14005c704  cmp     dword ptr [rax+0D0h], 2
0x14005c70b  jz      loc_14005C7E3
0x14005c711  mov     [rbp+2D0h+var_2E0], rdi
0x14005c715  mov     [rbp+2D0h+var_2D8], edi
0x14005c718  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005c71f  nop     dword ptr [rax+rax+00h]
0x14005c724  xorps   xmm0, xmm0
0x14005c727  mov     [rbp+2D0h+var_2C8], rdi
0x14005c72b  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14005c732  mov     [rbp+2D0h+var_2D0], rax
0x14005c736  lea     rdx, [rbp+2D0h+var_2E0]
0x14005c73a  mov     [rbp+2D0h+var_2E0], rdi
0x14005c73e  lea     rcx, [rbp+2D0h+var_2C0]
0x14005c742  mov     [rbp+2D0h+var_2D8], edi
0x14005c745  movups  [rbp+2D0h+var_2C0], xmm0
0x14005c749  movups  [rbp+2D0h+var_2B0], xmm0
0x14005c74d  call    cs:__imp_PushThreadGuardedObject
0x14005c754  nop     dword ptr [rax+rax+00h]
0x14005c759  xorps   xmm0, xmm0
0x14005c75c  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDLODCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DLODCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14005c763  lea     rdx, [rbp+2D0h+var_2E0]
0x14005c767  lea     rcx, [rbp+2D0h+var_2A0]
0x14005c76b  movups  [rbp+2D0h+var_2A0], xmm0
0x14005c76f  movups  [rbp+2D0h+var_290], xmm0
0x14005c773  call    cs:__imp_PushThreadGuardedObject
0x14005c77a  nop     dword ptr [rax+rax+00h]
0x14005c77f  xorps   xmm0, xmm0
0x14005c782  mov     [rbp+2D0h+var_280], 100h
0x14005c788  xor     r8d, r8d
0x14005c78b  movdqa  xmmword ptr [rbp+2D0h+var_300.fl], xmm0
0x14005c790  mov     rdx, rbx
0x14005c793  mov     [rbp+2D0h+var_2F0], rdi
0x14005c797  lea     rcx, [rbp+2D0h+var_300]
0x14005c79b  mov     [rbp+2D0h+var_2E8], edi
0x14005c79e  mov     [rbp+2D0h+var_2E0], rdi
0x14005c7a2  mov     [rbp+2D0h+var_268], rdi
0x14005c7a6  mov     [rbp+2D0h+var_270], rdi
0x14005c7aa  mov     [rbp+2D0h+var_278], rdi
0x14005c7ae  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x14005c7b5  nop     dword ptr [rax+rax+00h]
0x14005c7ba  mov     rdx, [rbx]
0x14005c7bd  mov     r15, [rdx+1F0h]
0x14005c7c4  test    eax, eax
0x14005c7c6  jz      loc_14005C893
0x14005c7cc  test    r15, r15
0x14005c7cf  jnz     loc_14005C89C
0x14005c7d5  lea     rcx, [rbp+2D0h+var_300]; this
0x14005c7d9  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x14005c7de  mov     r15, [rsp+3D0h+var_368]
0x14005c7e3  mov     r8d, esi; int
0x14005c7e6  mov     [rsp+3D0h+var_370], r14d
0x14005c7eb  mov     rdx, rbx; struct XDCOBJ *
0x14005c7ee  mov     [rsp+3D0h+var_36C], r12d
0x14005c7f3  lea     rcx, [rbp+2D0h+var_300]; this
0x14005c7f7  call    ??0PATHSTACKOBJ@@QEAA@AEAVXDCOBJ@@H@Z; PATHSTACKOBJ::PATHSTACKOBJ(XDCOBJ &,int)
0x14005c7fc  cmp     qword ptr [rbp+2D0h+var_300.fl+8], rdi
0x14005c800  jnz     loc_14005CCBD
0x14005c806  mov     ecx, 8; iError
0x14005c80b  call    cs:__imp_EngSetLastError
0x14005c812  nop     dword ptr [rax+rax+00h]
0x14005c817  lea     rcx, [rbp+2D0h+var_300]
0x14005c81b  call    cs:__imp_?vUnlock@EPATHOBJ@@QEAAXXZ; EPATHOBJ::vUnlock(void)
0x14005c822  nop     dword ptr [rax+rax+00h]
0x14005c827  lea     rcx, [rbp+2D0h+var_270]
0x14005c82b  call    cs:__imp_??1PATH_CORE@@QEAA@XZ; PATH_CORE::~PATH_CORE(void)
0x14005c832  nop     dword ptr [rax+rax+00h]
0x14005c837  cmp     dword ptr [rbp+2D0h+var_290], edi
0x14005c83a  jz      short loc_14005C866
0x14005c83c  lea     rcx, [rbp+2D0h+var_2B0]
0x14005c840  call    cs:__imp_PopThreadGuardedObject
0x14005c847  nop     dword ptr [rax+rax+00h]
0x14005c84c  jmp     short loc_14005C866
0x14005c84e  mov     eax, [rdx+24h]
0x14005c851  bt      eax, 0Ch
0x14005c855  jb      loc_14005CFEF
0x14005c85b  mov     esi, edi
0x14005c85d  lea     rcx, [rbp+2D0h+var_300]; this
0x14005c861  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x14005c866  mov     eax, esi
0x14005c868  mov     rcx, [rbp+2D0h+var_40]
0x14005c86f  xor     rcx, rsp; StackCookie
0x14005c872  call    __security_check_cookie
0x14005c877  mov     rbx, [rsp+3D0h+arg_18]
0x14005c87f  add     rsp, 3A0h
0x14005c886  pop     r15
0x14005c888  pop     r14
0x14005c88a  pop     r13
0x14005c88c  pop     r12
0x14005c88e  pop     rdi
0x14005c88f  pop     rsi
0x14005c890  pop     rbp
0x14005c891  retn
0x14005c893  test    r15, r15
0x14005c896  jnz     short loc_14005C84E
0x14005c898  mov     edi, esi
0x14005c89a  jmp     short loc_14005C85B
0x14005c89c  mov     eax, [r15+90h]
0x14005c8a3  bt      eax, 8
0x14005c8a7  jb      loc_14005CEA6
0x14005c8ad  cmp     [r15+64h], di
0x14005c8b2  jnz     loc_14005C7D5
0x14005c8b8  test    al, 20h
0x14005c8ba  jnz     loc_14005C7D5
0x14005c8c0  lea     rax, EngLineTo
0x14005c8c7  mov     [rbp+2D0h+var_330], rax
0x14005c8cb  mov     rcx, qword ptr [rbp+2D0h+var_328.xLeft]
0x14005c8cf  mov     r8d, [rcx+20h]
0x14005c8d3  test    r8b, 2
0x14005c8d7  jz      loc_14005CDA6
0x14005c8dd  mov     r8d, [rcx+18h]
0x14005c8e1  mov     r9d, [rcx+1Ch]
0x14005c8e5  mov     rcx, [rdx+3D0h]
0x14005c8ec  sar     r8d, 4
0x14005c8f0  sar     r9d, 4
0x14005c8f4  test    dword ptr [rcx+98h], 100h
0x14005c8fe  lea     r10d, [r14+r8]
0x14005c902  lea     r11d, [r12+r9]
0x14005c906  jz      loc_14005CE2E
0x14005c90c  mov     r12d, [rcx+8]
0x14005c910  mov     r13d, [rcx+0Ch]
0x14005c914  sar     r12d, 4
0x14005c918  sar     r13d, 4
0x14005c91c  mov     [rsp+3D0h+var_37C], r13d
0x14005c921  mov     [rsp+3D0h+var_380], r12d
0x14005c926  lea     eax, [r10+7FFFFFEh]
0x14005c92d  cmp     eax, 0FFFFFFCh
0x14005c932  ja      loc_14005CFCE
0x14005c938  lea     eax, [r11+7FFFFFEh]
0x14005c93f  cmp     eax, 0FFFFFFCh
0x14005c944  ja      loc_14005CFCE
0x14005c94a  mov     rdx, [rbx]
0x14005c94d  mov     ecx, [rsp+3D0h+var_374]
0x14005c951  mov     rax, [rdx+3D0h]
0x14005c958  and     dword ptr [rax+98h], 0FFFFFCFFh
0x14005c962  mov     rax, [rdx+3D0h]
0x14005c969  mov     [rax+0D8h], r14d
0x14005c970  mov     rax, [rdx+3D0h]
0x14005c977  mov     [rax+0DCh], ecx
0x14005c97d  mov     ecx, r10d
0x14005c980  mov     rax, [rdx+3D0h]
0x14005c987  shl     ecx, 4
0x14005c98a  mov     [rax+8], ecx
0x14005c98d  mov     ecx, r11d
0x14005c990  mov     rax, [rdx+3D0h]
0x14005c997  shl     ecx, 4
0x14005c99a  mov     [rax+0Ch], ecx
0x14005c99d  mov     rcx, [rbx]
0x14005c9a0  mov     eax, [rcx+28h]
0x14005c9a3  and     eax, esi
0x14005c9a5  lea     rdx, ds:0[rax*8]
0x14005c9ad  mov     r8d, [rdx+rcx+3F8h]
0x14005c9b5  lea     eax, [r8+r12]
0x14005c9b9  mov     [rsp+3D0h+var_378], eax
0x14005c9bd  add     eax, 7FFFFFEh
0x14005c9c2  cmp     eax, 0FFFFFFCh
0x14005c9c7  ja      loc_14005CEF2
0x14005c9cd  mov     edx, [rdx+rcx+3FCh]
0x14005c9d4  lea     r14d, [rdx+r13]
0x14005c9d8  lea     eax, [r14+7FFFFFEh]
0x14005c9df  mov     [rbp+2D0h+var_33C], r14d
0x14005c9e3  cmp     eax, 0FFFFFFCh
0x14005c9e8  ja      loc_14005CEF2
0x14005c9ee  lea     r9d, [r8+r10]
0x14005c9f2  lea     eax, [r9+7FFFFFEh]
0x14005c9f9  mov     [rbp+2D0h+var_340], r9d
0x14005c9fd  cmp     eax, 0FFFFFFCh
0x14005ca02  ja      loc_14005CEF2
0x14005ca08  lea     r12d, [rdx+r11]
0x14005ca0c  lea     eax, [r12+7FFFFFEh]
0x14005ca14  cmp     eax, 0FFFFFFCh
0x14005ca19  ja      loc_14005CEED
0x14005ca1f  mov     eax, [rsp+3D0h+var_378]
0x14005ca23  cmp     eax, r9d
0x14005ca26  jg      loc_14005CEC3
0x14005ca2c  mov     r8d, eax
0x14005ca2f  mov     dword ptr [rbp+2D0h+var_310], eax
0x14005ca32  lea     r10d, [r9+1]
0x14005ca36  mov     dword ptr [rbp+2D0h+var_310+8], r10d
0x14005ca3a  cmp     r14d, r12d
0x14005ca3d  jg      loc_14005CE51
0x14005ca43  mov     edx, r14d
0x14005ca46  lea     r9d, [r12+1]
0x14005ca4b  mov     dword ptr [rbp+2D0h+var_310+0Ch], r9d
0x14005ca4f  mov     dword ptr [rbp+2D0h+var_310+4], edx
0x14005ca52  mov     r11d, [rcx+24h]
0x14005ca56  test    r11b, 0E0h
0x14005ca5a  jz      loc_14005CB14
0x14005ca60  mov     eax, [rcx+28h]
0x14005ca63  lea     r14, [rcx+400h]
0x14005ca6a  test    sil, al
0x14005ca6d  jnz     short loc_14005CA76
0x14005ca6f  lea     r14, [rcx+3F8h]
0x14005ca76  mov     eax, [r14]
0x14005ca79  sub     r8d, eax
0x14005ca7c  sub     r10d, eax
0x14005ca7f  mov     eax, [r14+4]
0x14005ca83  sub     edx, eax
0x14005ca85  sub     r9d, eax
0x14005ca88  test    r11b, 20h
0x14005ca8c  jz      short loc_14005CACC
0x14005ca8e  cmp     r8d, [rcx+428h]
0x14005ca95  jge     short loc_14005CA9E
0x14005ca97  mov     [rcx+428h], r8d
0x14005ca9e  cmp     edx, [rcx+42Ch]
0x14005caa4  jge     short loc_14005CAAC
0x14005caa6  mov     [rcx+42Ch], edx
0x14005caac  cmp     r10d, [rcx+430h]
0x14005cab3  jle     short loc_14005CABC
0x14005cab5  mov     [rcx+430h], r10d
0x14005cabc  cmp     r9d, [rcx+434h]
0x14005cac3  jle     short loc_14005CACC
0x14005cac5  mov     [rcx+434h], r9d
0x14005cacc  mov     rcx, [rbx]
0x14005cacf  mov     eax, [rcx+24h]
0x14005cad2  test    al, al
0x14005cad4  jns     short loc_14005CB14
0x14005cad6  cmp     r8d, [rcx+448h]
0x14005cadd  jge     short loc_14005CAE6
0x14005cadf  mov     [rcx+448h], r8d
0x14005cae6  cmp     edx, [rcx+44Ch]
0x14005caec  jge     short loc_14005CAF4
0x14005caee  mov     [rcx+44Ch], edx
0x14005caf4  cmp     r10d, [rcx+450h]
0x14005cafb  jle     short loc_14005CB04
0x14005cafd  mov     [rcx+450h], r10d
0x14005cb04  cmp     r9d, [rcx+454h]
0x14005cb0b  jle     short loc_14005CB14
0x14005cb0d  mov     [rcx+454h], r9d
0x14005cb14  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005cb1b  nop     dword ptr [rax+rax+00h]
0x14005cb20  mov     rcx, [rbx]
0x14005cb23  mov     rax, [rax+0B0h]
0x14005cb2a  cmp     [rcx+90h], rax
0x14005cb31  jz      loc_14005C85D
0x14005cb37  mov     eax, [rcx+3E8h]
0x14005cb3d  cmp     dword ptr [rbp+2D0h+var_310], eax
0x14005cb40  jl      loc_14005CE5D
0x14005cb46  mov     eax, [rcx+3F0h]
  ... truncated ...
```
