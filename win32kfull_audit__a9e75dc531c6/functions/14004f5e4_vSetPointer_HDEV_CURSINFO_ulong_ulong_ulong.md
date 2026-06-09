# vSetPointer(HDEV__ *,_CURSINFO *,ulong,ulong,ulong)

- ea: `0x14004f5e4`
- end: `0x1400500c2`
- name: `?vSetPointer@@YAXPEAUHDEV__@@PEAU_CURSINFO@@KKK@Z`
- size: `2782`
- prototype: `void __fastcall(HDEV, struct _CURSINFO *, char, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004e8d8`

## callees

- `0x14004de48`
- `0x14004e750`
- `0x14004f5e4`
- `0x1400500c8`
- `0x140050c78`
- `0x140050d10`
- `0x14009a40c`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004f61f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004f750`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004f8b6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004fb86`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004fbbc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004fbfb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004f61f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004f750`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004f8b6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004fb86`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004fbbc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14004fbfb`
- `win32kbase!HmgShareLock` at `0x14004f67d`
- `win32kbase!HmgShareLock` at `0x14004f771`
- `win32kbase!HmgShareLock` at `0x14004f8cf`
- `win32kbase!HmgShareLock` at `0x14004fced`
- `win32kbase!HmgShareLock` at `0x14004f67d`
- `win32kbase!HmgShareLock` at `0x14004f771`
- `win32kbase!HmgShareLock` at `0x14004f8cf`
- `win32kbase!HmgShareLock` at `0x14004fced`
- `win32kbase!PopThreadGuardedObject` at `0x14004fba9`
- `win32kbase!PopThreadGuardedObject` at `0x14004fbdf`
- `win32kbase!PopThreadGuardedObject` at `0x14004fc1e`
- `win32kbase!PopThreadGuardedObject` at `0x14004fba9`
- `win32kbase!PopThreadGuardedObject` at `0x14004fbdf`
- `win32kbase!PopThreadGuardedObject` at `0x14004fc1e`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14004fb99`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14004fbcf`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14004fc0e`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14004fb99`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14004fbcf`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14004fc0e`
- `win32kbase!PushThreadGuardedObject` at `0x14004f665`
- `win32kbase!PushThreadGuardedObject` at `0x14004f6e1`
- `win32kbase!PushThreadGuardedObject` at `0x14004f70b`
- `win32kbase!PushThreadGuardedObject` at `0x14004f665`
- `win32kbase!PushThreadGuardedObject` at `0x14004f6e1`
- `win32kbase!PushThreadGuardedObject` at `0x14004f70b`
- `win32kbase!bIsCompatible` at `0x14004f7cd`
- `win32kbase!bIsCompatible` at `0x14004f7cd`

## pseudocode

```c
void __fastcall vSetPointer(HDEV a1, struct _CURSINFO *a2, char a3, unsigned int a4, unsigned int a5)
{
  struct Gre::Base::SESSION_GLOBALS *v7; // rax
  int v8; // ecx
  struct Gre::Base::SESSION_GLOBALS *v9; // r15
  __int64 v10; // rbx
  __int64 v11; // r8
  __int64 v12; // rax
  int v13; // r14d
  __int64 v14; // rbx
  int v15; // r13d
  __int64 v16; // rax
  __int64 v17; // r12
  __int64 v18; // r15
  struct Gre::Base::SESSION_GLOBALS *v19; // rax
  __int64 v20; // r8
  __int64 v21; // rax
  struct PALETTE *v22; // rdx
  Gre::Base *v23; // rcx
  int *v24; // rbx
  int v25; // r8d
  int v26; // r13d
  int v27; // r12d
  int v28; // ebx
  __int64 v29; // rax
  struct Gre::Base::SESSION_GLOBALS *v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // r11
  LONG v34; // r11d
  LONG v35; // r10d
  LONG v36; // r9d
  LONG v37; // r8d
  unsigned __int64 v38; // rcx
  LONG v39; // edx
  bool v40; // cc
  unsigned int v41; // r12d
  int v42; // r9d
  bool v43; // zf
  int v44; // ebx
  int v45; // eax
  int v46; // r13d
  unsigned int v47; // r8d
  int v48; // ecx
  int v49; // eax
  __int64 (__fastcall *v50)(SURFOBJ *, __int64, __int64, XLATEOBJ *, int, int, LONG, LONG, RECTL *, FLONG); // r10
  int v51; // edx
  int v52; // ecx
  unsigned int v53; // eax
  char v54; // cl
  BOOL v55; // eax
  SURFOBJ *v56; // rsi
  signed __int32 v57; // eax
  signed __int32 v58; // edx
  signed __int32 v59; // eax
  signed __int32 v60; // edx
  signed __int32 v61; // eax
  signed __int32 v62; // edx
  signed __int32 v63; // eax
  signed __int32 v64; // edx
  struct Gre::Base::SESSION_GLOBALS *v65; // rax
  Gre::Base *v66; // rcx
  struct Gre::Base::SESSION_GLOBALS *v67; // rax
  Gre::Base *v68; // rcx
  struct Gre::Base::SESSION_GLOBALS *v69; // rax
  int v70; // edx
  struct _SURFOBJ *v71; // r8
  int v72; // eax
  unsigned int v73; // eax
  Gre::Base *v74; // r8
  int v75; // eax
  int v76; // r9d
  int v77; // eax
  void (__fastcall *v78)(__int64, __int64, __int64, _QWORD); // rax
  signed __int32 v79; // ett
  signed __int32 v80; // ett
  signed __int32 v81; // ett
  void (__fastcall *v82)(SURFOBJ *, __int64, __int64, _QWORD); // rax
  unsigned __int8 v83; // al
  int v84; // ecx
  char v85; // al
  int v86; // ecx
  int v87; // ecx
  void (__fastcall *v88)(SURFOBJ *, __int64, __int64, _QWORD); // rax
  SURFOBJ *v89; // r8
  XLATEOBJ *v90; // r9
  SURFOBJ *v91; // rdx
  HDEV v92; // rdx
  LONG xHot; // [rsp+20h] [rbp-E0h]
  LONG yHot; // [rsp+28h] [rbp-D8h]
  LONG x; // [rsp+30h] [rbp-D0h]
  LONG y; // [rsp+38h] [rbp-C8h]
  RECTL *prcl; // [rsp+40h] [rbp-C0h]
  FLONG fla; // [rsp+48h] [rbp-B8h]
  int fl; // [rsp+48h] [rbp-B8h]
  int v100; // [rsp+60h] [rbp-A0h]
  LONG v101; // [rsp+64h] [rbp-9Ch]
  LONG v102; // [rsp+68h] [rbp-98h]
  int v103; // [rsp+70h] [rbp-90h]
  int v104; // [rsp+70h] [rbp-90h]
  Gre::Base *v106; // [rsp+88h] [rbp-78h]
  SURFOBJ *pso; // [rsp+90h] [rbp-70h]
  struct PALETTE *v108; // [rsp+98h] [rbp-68h] BYREF
  __int64 v109; // [rsp+A0h] [rbp-60h]
  RECTL v110; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v111[2]; // [rsp+C0h] [rbp-40h] BYREF
  RECTL v112; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v113; // [rsp+E0h] [rbp-20h]
  int v114; // [rsp+E4h] [rbp-1Ch]
  XLATEOBJ *v115; // [rsp+E8h] [rbp-18h]
  _OWORD v116[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v117; // [rsp+110h] [rbp+10h]
  _OWORD v118[2]; // [rsp+118h] [rbp+18h] BYREF
  Gre::Base *v119; // [rsp+138h] [rbp+38h]
  _OWORD v120[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v121; // [rsp+160h] [rbp+60h]
  RECTL v122; // [rsp+170h] [rbp+70h] BYREF

  v113 = a4;
  v7 = Gre::Base::Globals((Gre::Base *)a1);
  v8 = *((_DWORD *)a1 + 10);
  v9 = v7;
  if ( (v8 & 0x400) != 0 )
    return;
  if ( a2 )
  {
    v10 = *((_QWORD *)a2 + 1);
    memset(v116, 0, sizeof(v116));
    PushThreadGuardedObject(
      v116,
      v116,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    LOBYTE(v11) = 5;
    v12 = HmgShareLock(v9, v10, v11, 0);
    v117 = v12;
    if ( !v12 )
      goto LABEL_81;
    v13 = 1;
    if ( *(_DWORD *)(v12 + 96) != 1 || (*(_DWORD *)(v12 + 60) & 1) != 0 )
      goto LABEL_81;
    v14 = *((_QWORD *)v9 + 484);
    v106 = 0;
    v115 = 0;
    v111[0] = 0;
    memset(v118, 0, sizeof(v118));
    v15 = 0;
    PushThreadGuardedObject(
      v118,
      v118,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    v119 = 0;
    memset(v120, 0, sizeof(v120));
    PushThreadGuardedObject(
      v120,
      v120,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    v16 = *((_QWORD *)a1 + 318);
    v121 = 0;
    v108 = 0;
    v17 = *((_QWORD *)a2 + 2);
    v112 = 0;
    pso = (SURFOBJ *)((v16 + 24) & -(__int64)(v16 != 0));
    if ( v17 || *((_QWORD *)a2 + 6) )
    {
      v18 = *((_QWORD *)a2 + 6);
      v19 = Gre::Base::Globals((Gre::Base *)(v16 + 24));
      LOBYTE(v20) = 5;
      if ( v18 )
      {
        v21 = HmgShareLock(v19, v18, v20, 0);
        v15 = 1;
      }
      else
      {
        v21 = HmgShareLock(v19, v17, v20, 0);
      }
      v119 = (Gre::Base *)v21;
      if ( !v21 )
        goto LABEL_95;
      if ( *(_DWORD *)(v21 + 60) != *(int *)(v117 + 60) >> 1 || *(_DWORD *)(v21 + 56) < *(_DWORD *)(v117 + 56) )
        goto LABEL_80;
      v22 = *(struct PALETTE **)(v21 + 160);
      v108 = v22;
      if ( !v22 )
      {
        v92 = (HDEV)*((_QWORD *)a1 + 3);
        if ( v92 == a1 )
        {
          v22 = 0;
        }
        else
        {
          v22 = (struct PALETTE *)*((_QWORD *)v92 + 224);
          v108 = v22;
        }
      }
      if ( !(unsigned int)bIsCompatible(&v108, v22, v119, a1) )
      {
LABEL_80:
        SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v120);
        SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v118);
        EXLATEOBJ::vAltUnlock((EXLATEOBJ *)v111);
LABEL_81:
        SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v116);
        return;
      }
      if ( (unsigned int)EXLATEOBJ::bInitXlateObj(v111, 0, 0, v108, *((_QWORD *)a1 + 224), v14, v14, 0, 0xFFFFFF, 0, 0) )
      {
        v23 = v119;
        v115 = (XLATEOBJ *)v111[0];
        v106 = v119;
      }
      else
      {
LABEL_95:
        v23 = 0;
      }
    }
    else
    {
      v23 = 0;
    }
    v24 = (int *)((char *)a2 + 32);
    if ( *((_DWORD *)a2 + 11) )
    {
      if ( (*(_DWORD *)a2 & 0x400) != 0 )
      {
        if ( (a3 & 0x10) != 0 )
          goto LABEL_19;
      }
      else if ( (a3 & 0x10) == 0 )
      {
        goto LABEL_19;
      }
    }
    if ( v23 )
      v71 = (struct _SURFOBJ *)((char *)v23 + 24);
    else
      v71 = 0;
    vProcessCursorShape(
      (Gre::Base *)-v117,
      a3 & 0x10,
      v15,
      (struct _SURFOBJ *)((v117 + 24) & -(__int64)(v117 != 0)),
      v71,
      v108,
      (struct _RECTL *)a2 + 2,
      (HBITMAP *)a2 + 3);
    v72 = *(_DWORD *)a2;
    if ( (a3 & 0x10) != 0 )
      v73 = v72 | 0x400;
    else
      v73 = v72 & 0xFFFFFBFF;
    *(_DWORD *)a2 = v73;
LABEL_19:
    v25 = *v24;
    v26 = *((_DWORD *)a2 + 10);
    v103 = *v24;
    if ( *v24 <= v26 )
    {
      v27 = *((_DWORD *)a2 + 11);
      v28 = *((_DWORD *)a2 + 9);
      if ( v28 <= v27 )
      {
        v29 = *((_QWORD *)a2 + 3);
        *(_QWORD *)&v110.left = __PAIR64__(v28, v25);
        *(_QWORD *)&v110.right = __PAIR64__(v27, v26);
        v109 = v29;
        if ( v29 && *((_DWORD *)a1 + 523) > 3u )
        {
          v30 = Gre::Base::Globals(v23);
          LOBYTE(v31) = 5;
          v32 = HmgShareLock(v30, v109, v31, 0);
          v25 = v103;
          v121 = v32;
        }
        v33 = v117;
        v109 = v121;
        if ( v121 )
        {
          v34 = *((_DWORD *)a2 + 8);
          v35 = *((_DWORD *)a2 + 9);
          v36 = *((_DWORD *)a2 + 10);
          v37 = *((_DWORD *)a2 + 11);
          if ( (a3 & 0x10) != 0 )
          {
            ++v34;
            v36 += 8;
            ++v35;
            v37 += 6;
          }
          v38 = *(unsigned int *)(v121 + 56);
          v39 = *(_DWORD *)(v121 + 60);
          if ( v34 < 0 )
            v34 = 0;
          v112.left = v34;
          if ( v35 < 0 )
            v35 = 0;
          v112.top = v35;
          if ( (int)v38 < v36 )
            v36 = v38;
          v112.right = v36;
          if ( v39 < v37 )
            v37 = v39;
          v40 = v36 < v34;
          v33 = v117;
          v112.bottom = v37;
          if ( v40 )
          {
            v112.left = v36;
          }
          else if ( v37 < v35 )
          {
            v112.top = v37;
          }
        }
        else
        {
          v70 = *(_DWORD *)(v117 + 56);
          v109 = 0;
          if ( v119 && v70 >= *((_DWORD *)v119 + 14) )
            v70 = *((_DWORD *)v119 + 14);
          v38 = (unsigned int)(*(int *)(v117 + 60) >> 1);
          if ( v25 < 0 )
            v25 = 0;
          v110.left = v25;
          if ( v28 < 0 )
            v28 = 0;
          v110.top = v28;
          if ( v70 < v26 )
            v26 = v70;
          v110.right = v26;
          if ( (int)v38 < v27 )
            v27 = v38;
          v110.bottom = v27;
          if ( v26 < v25 )
          {
            v110.left = v26;
          }
          else
          {
            if ( v27 < v28 )
              v28 = v27;
            v110.top = v28;
          }
        }
        v41 = 3;
        v42 = (a3 & 0x10) != 0 ? 3 : 0;
        v43 = ((_DWORD)a1[10] & 0x400) == 0;
        v122 = 0;
        v114 = v42;
        if ( !v43 )
          goto LABEL_72;
        v44 = 0;
        v45 = *((__int16 *)a2 + 2);
        v46 = 0;
        v47 = v113;
        *((_DWORD *)a1 + 19) = *((__int16 *)a2 + 3);
        *((_DWORD *)a1 + 18) = v45;
        v48 = a3 & 0xC | 1;
        v102 = *((_DWORD *)a1 + 16);
        v101 = *((_DWORD *)a1 + 17);
        v49 = 0;
        v100 = v48;
        v104 = 0;
        if ( v47 )
        {
          if ( a5 )
          {
            v83 = -1;
            if ( a5 < 0xFF )
              v83 = a5;
            v84 = v83;
            v85 = 16;
            v86 = 16 * v84;
            if ( v47 < 0x10 )
              v85 = v47;
            v87 = v85 & 0xF | v86;
            v49 = 1;
            v48 = v100 | (v87 << 8);
            v100 = v48;
            v104 = 1;
          }
          else
          {
            v48 = a3 & 0xC | 1;
          }
        }
        if ( (a3 & 0x20) != 0 )
        {
          v41 = 1;
          goto LABEL_51;
        }
        v50 = (__int64 (__fastcall *)(SURFOBJ *, __int64, __int64, XLATEOBJ *, int, int, LONG, LONG, RECTL *, FLONG))*((_QWORD *)a1 + 364);
        if ( !v50 )
        {
          v41 = 2;
          goto LABEL_51;
        }
        if ( v49 && ((_DWORD)a1[528] & 0x200) == 0 )
          goto LABEL_51;
        if ( v109 )
        {
          if ( ((_DWORD)a1[528] & 0x20) == 0 )
            goto LABEL_131;
          v51 = v42 + *((__int16 *)a2 + 3);
          fla = v48 | 0x10;
          v52 = v42 + *((__int16 *)a2 + 2);
          v122 = v112;
          v53 = v50(pso, 0, v109 + 24, 0, v52, v51, v102, v101, &v122, fla);
          v54 = v53;
          if ( v53 == 3 )
          {
            v55 = 1;
          }
          else
          {
            v44 = (v53 >> 1) & 1;
            v55 = (v53 & 2) == 0;
            if ( (v54 & 4) != 0 )
              v46 = 1;
          }
          v13 = v55;
LABEL_49:
          if ( !v13 )
          {
            v41 = 0;
LABEL_51:
            InputTraceLogging::GreCursor::CursorTypeUsage(v41);
            if ( v13 )
            {
              if ( v109 )
              {
                v89 = (SURFOBJ *)(v109 + 24);
                fl = v100 | a3 & 0x40 | 0x10;
                prcl = &v112;
                y = v101;
                v90 = 0;
                x = v102;
                v91 = 0;
                yHot = *((__int16 *)a2 + 3) + v114;
                xHot = *((__int16 *)a2 + 2) + v114;
              }
              else
              {
                if ( v106 )
                  v89 = (SURFOBJ *)((char *)v106 + 24);
                else
                  v89 = 0;
                fl = v100 | a3 & 0x40;
                prcl = &v110;
                v91 = (SURFOBJ *)((v117 + 24) & -(__int64)(v117 != 0));
                y = v101;
                x = v102;
                yHot = *((__int16 *)a2 + 3);
                v90 = v115;
                xHot = *((__int16 *)a2 + 2);
              }
              v56 = pso;
              EngSetPointerShape(pso, v91, v89, v90, xHot, yHot, x, y, prcl, fl);
            }
            else
            {
              if ( ((_DWORD)a1[10] & 4) != 0 )
                EngSetPointerShape(
                  (SURFOBJ *)((*((_QWORD *)a1 + 318) + 24LL) & -(__int64)(*((_QWORD *)a1 + 318) != 0)),
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0);
              v56 = pso;
            }
            if ( !v44 && ((_DWORD)a1[10] & 2) != 0 )
            {
              v82 = (void (__fastcall *)(SURFOBJ *, __int64, __int64, _QWORD))*((_QWORD *)a1 + 365);
              if ( v82 )
                v82(v56, 0xFFFFFFFFLL, 0xFFFFFFFFLL, 0);
            }
            _m_prefetchw(a1 + 10);
            do
            {
              v58 = *((_DWORD *)a1 + 10) | 4;
              if ( !v13 )
                v58 = (_DWORD)a1[10] & 0xFFFFFFFB;
              v57 = *((_DWORD *)a1 + 10);
            }
            while ( v57 != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 10, v58, v57) );
            _m_prefetchw(a1 + 10);
            do
            {
              v60 = *((_DWORD *)a1 + 10) | 2;
              if ( !v44 )
                v60 = (_DWORD)a1[10] & 0xFFFFFFFD;
              v59 = *((_DWORD *)a1 + 10);
            }
            while ( v59 != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 10, v60, v59) );
            _m_prefetchw(a1 + 10);
            do
            {
              v62 = *((_DWORD *)a1 + 10) | 0x100000;
              if ( !v104 )
                v62 = (_DWORD)a1[10] & 0xFFEFFFFF;
              v61 = *((_DWORD *)a1 + 10);
            }
            while ( v61 != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 10, v62, v61) );
            _m_prefetchw(a1 + 10);
            do
            {
              v38 = *((unsigned int *)a1 + 10);
              LODWORD(v38) = v38 & 0xFFDFFFFF;
              v64 = *((_DWORD *)a1 + 10) | 0x200000;
              if ( !v46 )
                v64 = v38;
              v63 = *((_DWORD *)a1 + 10);
            }
            while ( v63 != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 10, v64, v63) );
LABEL_72:
            if ( v121 )
            {
              v65 = Gre::Base::Globals((Gre::Base *)v38);
              DEC_SHARE_REF_CNT(v65, v121);
            }
            PopThreadGuardedObject(v120);
            if ( v119 )
            {
              v67 = Gre::Base::Globals(v66);
              DEC_SHARE_REF_CNT(v67, v119);
            }
            PopThreadGuardedObject(v118);
            EXLATEOBJ::vAltUnlock((EXLATEOBJ *)v111);
            if ( v117 )
            {
              v69 = Gre::Base::Globals(v68);
              DEC_SHARE_REF_CNT(v69, v117);
            }
            PopThreadGuardedObject(v116);
            return;
          }
LABEL_131:
          v41 = 4;
          goto LABEL_51;
        }
        v74 = v106;
        v75 = *((__int16 *)a2 + 3);
        v76 = *((__int16 *)a2 + 2);
        v122 = v110;
        if ( v106 )
          v74 = (Gre::Base *)((char *)v106 + 24);
        v77 = v50(pso, (v33 + 24) & -(__int64)(v33 != 0), (__int64)v74, v115, v76, v75, v102, v101, &v122, v100);
        if ( v77 == 3 )
        {
          v88 = (void (__fastcall *)(SURFOBJ *, __int64, __int64, _QWORD))*((_QWORD *)a1 + 365);
          if ( v88 )
            v88(pso, 0xFFFFFFFFLL, 0xFFFFFFFFLL, 0);
          LOBYTE(v77) = 1;
        }
        else if ( (v77 & 2) != 0 )
        {
          v44 = 1;
LABEL_110:
          if ( (v77 & 4) != 0 )
            v46 = 1;
          v13 = v44 ^ 1;
          goto LABEL_49;
        }
        v44 = 0;
        goto LABEL_110;
      }
    }
    goto LABEL_80;
  }
  if ( (v8 & 4) != 0 )
    EngSetPointerShape(
      (SURFOBJ *)((*((_QWORD *)a1 + 318) + 24LL) & -(__int64)(*((_QWORD *)a1 + 318) != 0)),
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      0,
      0);
  if ( ((_DWORD)a1[10] & 2) != 0 )
  {
    v78 = (void (__fastcall *)(__int64, __int64, __int64, _QWORD))*((_QWORD *)a1 + 365);
    if ( v78 )
      v78((*((_QWORD *)a1 + 318) + 24LL) & -(__int64)(*((_QWORD *)a1 + 318) != 0), 0xFFFFFFFFLL, 0xFFFFFFFFLL, 0);
  }
  _m_prefetchw(a1 + 10);
  do
    v79 = *((_DWORD *)a1 + 10);
  while ( v79 != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 10, v79 & 0xFFFFFFFD, v79) );
  _m_prefetchw(a1 + 10);
  do
    v80 = *((_DWORD *)a1 + 10);
  while ( v80 != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 10, v80 & 0xFFFFFFFB, v80) );
  _m_prefetchw(a1 + 10);
  do
    v81 = *((_DWORD *)a1 + 10);
  while ( v81 != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 10, v81 & 0xFFEFFFFF, v81) );
}

```

## disassembly

```asm
0x14004f5e4  push    rbp
0x14004f5e6  push    rbx
0x14004f5e7  push    rsi
0x14004f5e8  push    rdi
0x14004f5e9  push    r12
0x14004f5eb  push    r13
0x14004f5ed  push    r14
0x14004f5ef  push    r15
0x14004f5f1  lea     rbp, [rsp-98h]
0x14004f5f9  sub     rsp, 198h
0x14004f600  mov     rax, cs:__security_cookie
0x14004f607  xor     rax, rsp
0x14004f60a  mov     [rbp+0D0h+var_50], rax
0x14004f611  mov     [rbp+0D0h+var_F0], r9d
0x14004f615  mov     rsi, rdx
0x14004f618  mov     [rbp+0D0h+var_150], r8d
0x14004f61c  mov     rdi, rcx
0x14004f61f  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14004f626  nop     dword ptr [rax+rax+00h]
0x14004f62b  mov     ecx, [rdi+28h]
0x14004f62e  mov     r15, rax
0x14004f631  bt      ecx, 0Ah
0x14004f635  jb      loc_14004FC2A
0x14004f63b  xor     r12d, r12d
0x14004f63e  test    rsi, rsi
0x14004f641  jz      loc_14004FE17
0x14004f647  mov     rbx, [rsi+8]
0x14004f64b  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14004f652  xorps   xmm0, xmm0
0x14004f655  lea     rdx, [rbp+0D0h+var_E0]
0x14004f659  lea     rcx, [rbp+0D0h+var_E0]
0x14004f65d  movups  [rbp+0D0h+var_E0], xmm0
0x14004f661  movups  [rbp+0D0h+var_D0], xmm0
0x14004f665  call    cs:__imp_PushThreadGuardedObject
0x14004f66c  nop     dword ptr [rax+rax+00h]
0x14004f671  xor     r9d, r9d
0x14004f674  mov     r8b, 5
0x14004f677  mov     rdx, rbx
0x14004f67a  mov     rcx, r15
0x14004f67d  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14004f684  nop     dword ptr [rax+rax+00h]
0x14004f689  mov     [rbp+0D0h+var_C0], rax
0x14004f68d  test    rax, rax
0x14004f690  jz      loc_14004FC69
0x14004f696  lea     r14d, [r12+1]
0x14004f69b  cmp     [rax+60h], r14d
0x14004f69f  jnz     loc_14004FC69
0x14004f6a5  mov     eax, [rax+3Ch]
0x14004f6a8  test    r14b, al
0x14004f6ab  jnz     loc_14004FC69
0x14004f6b1  mov     rbx, [r15+0F20h]
0x14004f6b8  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14004f6bf  xorps   xmm0, xmm0
0x14004f6c2  mov     [rbp+0D0h+var_148], r12
0x14004f6c6  lea     rdx, [rbp+0D0h+var_B8]
0x14004f6ca  mov     [rbp+0D0h+var_E8], r12
0x14004f6ce  lea     rcx, [rbp+0D0h+var_B8]
0x14004f6d2  mov     [rbp+0D0h+var_110], r12
0x14004f6d6  movups  [rbp+0D0h+var_B8], xmm0
0x14004f6da  mov     r13d, r12d
0x14004f6dd  movups  [rbp+0D0h+var_A8], xmm0
0x14004f6e1  call    cs:__imp_PushThreadGuardedObject
0x14004f6e8  nop     dword ptr [rax+rax+00h]
0x14004f6ed  xorps   xmm0, xmm0
0x14004f6f0  mov     [rbp+0D0h+var_98], r12
0x14004f6f4  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14004f6fb  lea     rdx, [rbp+0D0h+var_90]
0x14004f6ff  lea     rcx, [rbp+0D0h+var_90]
0x14004f703  movups  [rbp+0D0h+var_90], xmm0
0x14004f707  movups  [rbp+0D0h+var_80], xmm0
0x14004f70b  call    cs:__imp_PushThreadGuardedObject
0x14004f712  nop     dword ptr [rax+rax+00h]
0x14004f717  mov     rax, [rdi+9F0h]
0x14004f71e  xorps   xmm0, xmm0
0x14004f721  mov     [rbp+0D0h+var_70], r12
0x14004f725  mov     [rbp+0D0h+var_138], r12
0x14004f729  mov     r12, [rsi+10h]
0x14004f72d  lea     rcx, [rax+18h]
0x14004f731  movdqa  xmmword ptr [rbp+0D0h+var_100.left], xmm0
0x14004f736  neg     rax
0x14004f739  sbb     rax, rax
0x14004f73c  and     rax, rcx
0x14004f73f  mov     [rbp+0D0h+pso], rax
0x14004f743  test    r12, r12
0x14004f746  jz      loc_14004FCFE
0x14004f74c  mov     r15, [rsi+30h]
0x14004f750  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14004f757  nop     dword ptr [rax+rax+00h]
0x14004f75c  xor     r9d, r9d
0x14004f75f  mov     r8b, 5
0x14004f762  mov     rcx, rax
0x14004f765  test    r15, r15
0x14004f768  jz      loc_14004FCEA
0x14004f76e  mov     rdx, r15
0x14004f771  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14004f778  nop     dword ptr [rax+rax+00h]
0x14004f77d  mov     r13d, r14d
0x14004f780  mov     [rbp+0D0h+var_98], rax
0x14004f784  mov     rdx, rax
0x14004f787  test    rax, rax
0x14004f78a  jz      loc_14004FCD6
0x14004f790  mov     rcx, [rbp+0D0h+var_C0]
0x14004f794  mov     eax, [rcx+3Ch]
0x14004f797  sar     eax, 1
0x14004f799  cmp     [rdx+3Ch], eax
0x14004f79c  jnz     loc_14004FC4E
0x14004f7a2  mov     eax, [rcx+38h]
0x14004f7a5  cmp     [rdx+38h], eax
0x14004f7a8  jl      loc_14004FC4E
0x14004f7ae  mov     rdx, [rdx+0A0h]
0x14004f7b5  mov     [rbp+0D0h+var_138], rdx
0x14004f7b9  test    rdx, rdx
0x14004f7bc  jz      loc_14005007C
0x14004f7c2  mov     r8, [rbp+0D0h+var_98]
0x14004f7c6  lea     rcx, [rbp+0D0h+var_138]
0x14004f7ca  mov     r9, rdi
0x14004f7cd  call    cs:__imp_bIsCompatible
0x14004f7d4  nop     dword ptr [rax+rax+00h]
0x14004f7d9  test    eax, eax
0x14004f7db  jz      loc_14004FC4E
0x14004f7e1  mov     rax, [rdi+700h]
0x14004f7e8  lea     rcx, [rbp+0D0h+var_110]
0x14004f7ec  mov     r9, [rbp+0D0h+var_138]
0x14004f7f0  xor     r8d, r8d
0x14004f7f3  mov     [rsp+1D0h+var_180], 0
0x14004f7fb  xor     edx, edx
0x14004f7fd  mov     [rsp+1D0h+fl], 0
0x14004f805  mov     dword ptr [rsp+1D0h+prcl], 0FFFFFFh
0x14004f80d  mov     [rsp+1D0h+y], 0
0x14004f815  mov     qword ptr [rsp+1D0h+x], rbx
0x14004f81a  mov     qword ptr [rsp+1D0h+yHot], rbx
0x14004f81f  mov     qword ptr [rsp+1D0h+xHot], rax
0x14004f824  call    ?bInitXlateObj@EXLATEOBJ@@QEAAHPEAXJVXEPALOBJ@@111KKKK@Z; EXLATEOBJ::bInitXlateObj(void *,long,XEPALOBJ,XEPALOBJ,XEPALOBJ,XEPALOBJ,ulong,ulong,ulong,ulong)
0x14004f829  test    eax, eax
0x14004f82b  jz      loc_14004FCD6
0x14004f831  mov     rax, [rbp+0D0h+var_110]
0x14004f835  mov     rcx, [rbp+0D0h+var_98]
0x14004f839  mov     [rbp+0D0h+var_E8], rax
0x14004f83d  mov     [rbp+0D0h+var_148], rcx
0x14004f841  mov     r15d, [rbp+0D0h+var_150]
0x14004f845  lea     rbx, [rsi+20h]
0x14004f849  and     r15d, 10h
0x14004f84d  cmp     dword ptr [rbx+0Ch], 0
0x14004f851  jz      loc_14004FD10
0x14004f857  test    dword ptr [rsi], 400h
0x14004f85d  jnz     loc_14004FFAF
0x14004f863  test    r15d, r15d
0x14004f866  jnz     loc_14004FD10
0x14004f86c  mov     r8d, [rbx]
0x14004f86f  mov     r13d, [rsi+28h]
0x14004f873  mov     [rsp+1D0h+var_160], r8d
0x14004f878  cmp     r8d, r13d
0x14004f87b  jg      loc_14004FC4E
0x14004f881  mov     r12d, [rsi+2Ch]
0x14004f885  mov     ebx, [rsi+24h]
0x14004f888  cmp     ebx, r12d
0x14004f88b  jg      loc_14004FC4E
0x14004f891  mov     rax, [rsi+18h]
0x14004f895  mov     dword ptr [rbp+0D0h+var_120], r8d
0x14004f899  mov     dword ptr [rbp+0D0h+var_120+4], ebx
0x14004f89c  mov     dword ptr [rbp+0D0h+var_120+8], r13d
0x14004f8a0  mov     dword ptr [rbp+0D0h+var_120+0Ch], r12d
0x14004f8a4  mov     [rbp+0D0h+var_130], rax
0x14004f8a8  test    rax, rax
0x14004f8ab  jz      short loc_14004F8E4
0x14004f8ad  cmp     dword ptr [rdi+82Ch], 3
0x14004f8b4  jbe     short loc_14004F8E4
0x14004f8b6  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14004f8bd  nop     dword ptr [rax+rax+00h]
0x14004f8c2  mov     rdx, [rbp+0D0h+var_130]
0x14004f8c6  xor     r9d, r9d
0x14004f8c9  mov     rcx, rax
0x14004f8cc  mov     r8b, 5
0x14004f8cf  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14004f8d6  nop     dword ptr [rax+rax+00h]
0x14004f8db  mov     r8d, [rsp+1D0h+var_160]
0x14004f8e0  mov     [rbp+0D0h+var_70], rax
0x14004f8e4  mov     rax, [rbp+0D0h+var_70]
0x14004f8e8  mov     r11, [rbp+0D0h+var_C0]
0x14004f8ec  mov     [rbp+0D0h+var_130], rax
0x14004f8f0  test    rax, rax
0x14004f8f3  jz      loc_14004FC74
0x14004f8f9  mov     r11d, [rsi+20h]
0x14004f8fd  mov     r10d, [rsi+24h]
0x14004f901  mov     r9d, [rsi+28h]
0x14004f905  mov     r8d, [rsi+2Ch]
0x14004f909  test    r15d, r15d
0x14004f90c  jz      short loc_14004F91C
0x14004f90e  inc     r11d
0x14004f911  add     r9d, 8
0x14004f915  inc     r10d
0x14004f918  add     r8d, 6
0x14004f91c  mov     ecx, [rax+38h]
0x14004f91f  mov     edx, [rax+3Ch]
0x14004f922  xor     eax, eax
0x14004f924  test    r11d, r11d
0x14004f927  cmovs   r11d, eax
0x14004f92b  test    r10d, r10d
0x14004f92e  mov     [rbp+0D0h+var_100.left], r11d
0x14004f932  cmovs   r10d, eax
0x14004f936  cmp     ecx, r9d
0x14004f939  mov     [rbp+0D0h+var_100.top], r10d
0x14004f93d  cmovl   r9d, ecx
0x14004f941  cmp     edx, r8d
0x14004f944  mov     [rbp+0D0h+var_100.right], r9d
0x14004f948  cmovl   r8d, edx
0x14004f94c  cmp     r9d, r11d
0x14004f94f  mov     r11, [rbp+0D0h+var_C0]
0x14004f953  mov     [rbp+0D0h+var_100.bottom], r8d
0x14004f957  jl      loc_14004FDFD
0x14004f95d  cmp     r8d, r10d
0x14004f960  jge     short loc_14004F966
0x14004f962  mov     [rbp+0D0h+var_100.top], r8d
0x14004f966  neg     r15d
0x14004f969  mov     r12d, 3
0x14004f96f  xorps   xmm0, xmm0
0x14004f972  sbb     r9d, r9d
0x14004f975  and     r9d, r12d
0x14004f978  test    dword ptr [rdi+28h], 400h
0x14004f97f  movups  [rbp+0D0h+var_60], xmm0
0x14004f983  mov     [rbp+0D0h+var_EC], r9d
0x14004f987  jnz     loc_14004FB7F
0x14004f98d  movsx   ecx, word ptr [rsi+6]
0x14004f991  xor     ebx, ebx
0x14004f993  movsx   eax, word ptr [rsi+4]
0x14004f997  xor     r13d, r13d
0x14004f99a  mov     edx, [rbp+0D0h+var_150]
0x14004f99d  mov     r8d, [rbp+0D0h+var_F0]
0x14004f9a1  and     edx, 20h
0x14004f9a4  mov     [rdi+4Ch], ecx
0x14004f9a7  mov     ecx, [rbp+0D0h+var_150]
0x14004f9aa  mov     [rdi+48h], eax
0x14004f9ad  and     ecx, 0Ch
0x14004f9b0  mov     eax, [rdi+40h]
0x14004f9b3  or      ecx, r14d
0x14004f9b6  mov     [rsp+1D0h+var_168], eax
0x14004f9ba  mov     eax, [rdi+44h]
0x14004f9bd  mov     [rsp+1D0h+var_16C], eax
0x14004f9c1  xor     eax, eax
0x14004f9c3  mov     [rsp+1D0h+var_170], ecx
0x14004f9c7  mov     [rsp+1D0h+var_160], eax
0x14004f9cb  test    r8d, r8d
0x14004f9ce  jnz     loc_14004FF3A
0x14004f9d4  or      r15d, 0FFFFFFFFh
0x14004f9d8  test    edx, edx
0x14004f9da  jnz     loc_14004FF96
0x14004f9e0  mov     r10, [rdi+0B60h]
0x14004f9e7  test    r10, r10
0x14004f9ea  jz      loc_14004FCDF
0x14004f9f0  test    eax, eax
0x14004f9f2  jnz     loc_14004FF25
0x14004f9f8  mov     r8, [rbp+0D0h+var_130]
0x14004f9fc  test    r8, r8
0x14004f9ff  jz      loc_14004FD6B
0x14004fa05  mov     eax, [rdi+840h]
0x14004fa0b  test    al, 20h
0x14004fa0d  jz      loc_14004FF04
0x14004fa13  movsx   edx, word ptr [rsi+6]
0x14004fa17  mov     eax, ecx
0x14004fa19  movsx   ecx, word ptr [rsi+4]
0x14004fa1d  or      eax, 10h
0x14004fa20  movaps  xmm0, xmmword ptr [rbp+0D0h+var_100.left]
0x14004fa24  add     edx, r9d
0x14004fa27  mov     [rsp+1D0h+fl], eax
0x14004fa2b  add     ecx, r9d
0x14004fa2e  lea     rax, [rbp+0D0h+var_60]
0x14004fa32  movdqa  [rbp+0D0h+var_60], xmm0
0x14004fa37  mov     [rsp+1D0h+prcl], rax
0x14004fa3c  add     r8, 18h
0x14004fa40  mov     eax, [rsp+1D0h+var_16C]
0x14004fa44  xor     r9d, r9d
0x14004fa47  mov     [rsp+1D0h+y], eax
0x14004fa4b  mov     eax, [rsp+1D0h+var_168]
0x14004fa4f  mov     [rsp+1D0h+x], eax
0x14004fa53  mov     rax, r10
0x14004fa56  mov     [rsp+1D0h+yHot], edx
0x14004fa5a  xor     edx, edx
0x14004fa5c  mov     [rsp+1D0h+xHot], ecx
0x14004fa60  mov     rcx, [rbp+0D0h+pso]
0x14004fa64  call    _guard_dispatch_icall
0x14004fa69  mov     ecx, eax
0x14004fa6b  cmp     eax, r12d
0x14004fa6e  jz      loc_14005009C
0x14004fa74  mov     ebx, eax
0x14004fa76  shr     ebx, 1
0x14004fa78  and     ebx, r14d
0x14004fa7b  mov     eax, ebx
0x14004fa7d  xor     eax, r14d
0x14004fa80  test    cl, 4
0x14004fa83  jnz     loc_1400500A4
0x14004fa89  mov     r14d, eax
0x14004fa8c  test    r14d, r14d
0x14004fa8f  jnz     loc_14004FF04
0x14004fa95  xor     r12d, r12d
0x14004fa98  mov     ecx, r12d
0x14004fa9b  call    ?CursorTypeUsage@GreCursor@InputTraceLogging@@SAXW4_TRACING_CURSOR_USAGE_TYPE@@@Z; InputTraceLogging::GreCursor::CursorTypeUsage(_TRACING_CURSOR_USAGE_TYPE)
0x14004faa0  test    r14d, r14d
0x14004faa3  jnz     loc_14004FFBD
0x14004faa9  mov     eax, [rdi+28h]
0x14004faac  test    al, 4
  ... truncated ...
```
