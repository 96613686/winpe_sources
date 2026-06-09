# vSetPointer(HDEV__ *,_CURSINFO *,ulong,ulong,ulong)

- ea: `0x14007870c`
- end: `0x1400791ea`
- name: `?vSetPointer@@YAXPEAUHDEV__@@PEAU_CURSINFO@@KKK@Z`
- size: `2782`
- prototype: `void __fastcall(HDEV, struct _CURSINFO *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140091b5c`

## callees

- `0x14005fb0c`
- `0x140078480`
- `0x14007870c`
- `0x1400791f0`
- `0x14007a824`
- `0x14007a930`
- `0x1401269c8`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140078747`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140078878`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400789de`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140078cae`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140078ce4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140078d23`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140078747`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140078878`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400789de`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140078cae`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140078ce4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140078d23`
- `win32kbase!HmgShareLock` at `0x1400787a5`
- `win32kbase!HmgShareLock` at `0x140078899`
- `win32kbase!HmgShareLock` at `0x1400789f7`
- `win32kbase!HmgShareLock` at `0x140078e15`
- `win32kbase!HmgShareLock` at `0x1400787a5`
- `win32kbase!HmgShareLock` at `0x140078899`
- `win32kbase!HmgShareLock` at `0x1400789f7`
- `win32kbase!HmgShareLock` at `0x140078e15`
- `win32kbase!PopThreadGuardedObject` at `0x140078cd1`
- `win32kbase!PopThreadGuardedObject` at `0x140078d07`
- `win32kbase!PopThreadGuardedObject` at `0x140078d46`
- `win32kbase!PopThreadGuardedObject` at `0x140078cd1`
- `win32kbase!PopThreadGuardedObject` at `0x140078d07`
- `win32kbase!PopThreadGuardedObject` at `0x140078d46`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140078cc1`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140078cf7`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140078d36`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140078cc1`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140078cf7`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140078d36`
- `win32kbase!PushThreadGuardedObject` at `0x14007878d`
- `win32kbase!PushThreadGuardedObject` at `0x140078809`
- `win32kbase!PushThreadGuardedObject` at `0x140078833`
- `win32kbase!PushThreadGuardedObject` at `0x14007878d`
- `win32kbase!PushThreadGuardedObject` at `0x140078809`
- `win32kbase!PushThreadGuardedObject` at `0x140078833`
- `win32kbase!bIsCompatible` at `0x1400788f5`
- `win32kbase!bIsCompatible` at `0x1400788f5`

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
      v22 = *(struct PALETTE **)(v21 + 176);
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
      (HDEV)-v117,
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
0x14007870c  push    rbp
0x14007870e  push    rbx
0x14007870f  push    rsi
0x140078710  push    rdi
0x140078711  push    r12
0x140078713  push    r13
0x140078715  push    r14
0x140078717  push    r15
0x140078719  lea     rbp, [rsp-98h]
0x140078721  sub     rsp, 198h
0x140078728  mov     rax, cs:__security_cookie
0x14007872f  xor     rax, rsp
0x140078732  mov     [rbp+0D0h+var_50], rax
0x140078739  mov     [rbp+0D0h+var_F0], r9d
0x14007873d  mov     rsi, rdx
0x140078740  mov     [rbp+0D0h+var_150], r8d
0x140078744  mov     rdi, rcx
0x140078747  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14007874e  nop     dword ptr [rax+rax+00h]
0x140078753  mov     ecx, [rdi+28h]
0x140078756  mov     r15, rax
0x140078759  bt      ecx, 0Ah
0x14007875d  jb      loc_140078D52
0x140078763  xor     r12d, r12d
0x140078766  test    rsi, rsi
0x140078769  jz      loc_140078F3F
0x14007876f  mov     rbx, [rsi+8]
0x140078773  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14007877a  xorps   xmm0, xmm0
0x14007877d  lea     rdx, [rbp+0D0h+var_E0]
0x140078781  lea     rcx, [rbp+0D0h+var_E0]
0x140078785  movups  [rbp+0D0h+var_E0], xmm0
0x140078789  movups  [rbp+0D0h+var_D0], xmm0
0x14007878d  call    cs:__imp_PushThreadGuardedObject
0x140078794  nop     dword ptr [rax+rax+00h]
0x140078799  xor     r9d, r9d
0x14007879c  mov     r8b, 5
0x14007879f  mov     rdx, rbx
0x1400787a2  mov     rcx, r15
0x1400787a5  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400787ac  nop     dword ptr [rax+rax+00h]
0x1400787b1  mov     [rbp+0D0h+var_C0], rax
0x1400787b5  test    rax, rax
0x1400787b8  jz      loc_140078D91
0x1400787be  lea     r14d, [r12+1]
0x1400787c3  cmp     [rax+60h], r14d
0x1400787c7  jnz     loc_140078D91
0x1400787cd  mov     eax, [rax+3Ch]
0x1400787d0  test    r14b, al
0x1400787d3  jnz     loc_140078D91
0x1400787d9  mov     rbx, [r15+0F20h]
0x1400787e0  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1400787e7  xorps   xmm0, xmm0
0x1400787ea  mov     [rbp+0D0h+var_148], r12
0x1400787ee  lea     rdx, [rbp+0D0h+var_B8]
0x1400787f2  mov     [rbp+0D0h+var_E8], r12
0x1400787f6  lea     rcx, [rbp+0D0h+var_B8]
0x1400787fa  mov     [rbp+0D0h+var_110], r12
0x1400787fe  movups  [rbp+0D0h+var_B8], xmm0
0x140078802  mov     r13d, r12d
0x140078805  movups  [rbp+0D0h+var_A8], xmm0
0x140078809  call    cs:__imp_PushThreadGuardedObject
0x140078810  nop     dword ptr [rax+rax+00h]
0x140078815  xorps   xmm0, xmm0
0x140078818  mov     [rbp+0D0h+var_98], r12
0x14007881c  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140078823  lea     rdx, [rbp+0D0h+var_90]
0x140078827  lea     rcx, [rbp+0D0h+var_90]
0x14007882b  movups  [rbp+0D0h+var_90], xmm0
0x14007882f  movups  [rbp+0D0h+var_80], xmm0
0x140078833  call    cs:__imp_PushThreadGuardedObject
0x14007883a  nop     dword ptr [rax+rax+00h]
0x14007883f  mov     rax, [rdi+9F0h]
0x140078846  xorps   xmm0, xmm0
0x140078849  mov     [rbp+0D0h+var_70], r12
0x14007884d  mov     [rbp+0D0h+var_138], r12
0x140078851  mov     r12, [rsi+10h]
0x140078855  lea     rcx, [rax+18h]
0x140078859  movdqa  xmmword ptr [rbp+0D0h+var_100.left], xmm0
0x14007885e  neg     rax
0x140078861  sbb     rax, rax
0x140078864  and     rax, rcx
0x140078867  mov     [rbp+0D0h+pso], rax
0x14007886b  test    r12, r12
0x14007886e  jz      loc_140078E26
0x140078874  mov     r15, [rsi+30h]
0x140078878  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14007887f  nop     dword ptr [rax+rax+00h]
0x140078884  xor     r9d, r9d
0x140078887  mov     r8b, 5
0x14007888a  mov     rcx, rax
0x14007888d  test    r15, r15
0x140078890  jz      loc_140078E12
0x140078896  mov     rdx, r15
0x140078899  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400788a0  nop     dword ptr [rax+rax+00h]
0x1400788a5  mov     r13d, r14d
0x1400788a8  mov     [rbp+0D0h+var_98], rax
0x1400788ac  mov     rdx, rax
0x1400788af  test    rax, rax
0x1400788b2  jz      loc_140078DFE
0x1400788b8  mov     rcx, [rbp+0D0h+var_C0]
0x1400788bc  mov     eax, [rcx+3Ch]
0x1400788bf  sar     eax, 1
0x1400788c1  cmp     [rdx+3Ch], eax
0x1400788c4  jnz     loc_140078D76
0x1400788ca  mov     eax, [rcx+38h]
0x1400788cd  cmp     [rdx+38h], eax
0x1400788d0  jl      loc_140078D76
0x1400788d6  mov     rdx, [rdx+0B0h]
0x1400788dd  mov     [rbp+0D0h+var_138], rdx
0x1400788e1  test    rdx, rdx
0x1400788e4  jz      loc_1400791A4
0x1400788ea  mov     r8, [rbp+0D0h+var_98]
0x1400788ee  lea     rcx, [rbp+0D0h+var_138]
0x1400788f2  mov     r9, rdi
0x1400788f5  call    cs:__imp_bIsCompatible
0x1400788fc  nop     dword ptr [rax+rax+00h]
0x140078901  test    eax, eax
0x140078903  jz      loc_140078D76
0x140078909  mov     rax, [rdi+700h]
0x140078910  lea     rcx, [rbp+0D0h+var_110]
0x140078914  mov     r9, [rbp+0D0h+var_138]
0x140078918  xor     r8d, r8d
0x14007891b  mov     [rsp+1D0h+var_180], 0
0x140078923  xor     edx, edx
0x140078925  mov     [rsp+1D0h+fl], 0
0x14007892d  mov     dword ptr [rsp+1D0h+prcl], 0FFFFFFh
0x140078935  mov     [rsp+1D0h+y], 0
0x14007893d  mov     qword ptr [rsp+1D0h+x], rbx
0x140078942  mov     qword ptr [rsp+1D0h+yHot], rbx
0x140078947  mov     qword ptr [rsp+1D0h+xHot], rax
0x14007894c  call    ?bInitXlateObj@EXLATEOBJ@@QEAAHPEAXJVXEPALOBJ@@111KKKK@Z; EXLATEOBJ::bInitXlateObj(void *,long,XEPALOBJ,XEPALOBJ,XEPALOBJ,XEPALOBJ,ulong,ulong,ulong,ulong)
0x140078951  test    eax, eax
0x140078953  jz      loc_140078DFE
0x140078959  mov     rax, [rbp+0D0h+var_110]
0x14007895d  mov     rcx, [rbp+0D0h+var_98]
0x140078961  mov     [rbp+0D0h+var_E8], rax
0x140078965  mov     [rbp+0D0h+var_148], rcx
0x140078969  mov     r15d, [rbp+0D0h+var_150]
0x14007896d  lea     rbx, [rsi+20h]
0x140078971  and     r15d, 10h
0x140078975  cmp     dword ptr [rbx+0Ch], 0
0x140078979  jz      loc_140078E38
0x14007897f  test    dword ptr [rsi], 400h
0x140078985  jnz     loc_1400790D7
0x14007898b  test    r15d, r15d
0x14007898e  jnz     loc_140078E38
0x140078994  mov     r8d, [rbx]
0x140078997  mov     r13d, [rsi+28h]
0x14007899b  mov     [rsp+1D0h+var_160], r8d
0x1400789a0  cmp     r8d, r13d
0x1400789a3  jg      loc_140078D76
0x1400789a9  mov     r12d, [rsi+2Ch]
0x1400789ad  mov     ebx, [rsi+24h]
0x1400789b0  cmp     ebx, r12d
0x1400789b3  jg      loc_140078D76
0x1400789b9  mov     rax, [rsi+18h]
0x1400789bd  mov     dword ptr [rbp+0D0h+var_120], r8d
0x1400789c1  mov     dword ptr [rbp+0D0h+var_120+4], ebx
0x1400789c4  mov     dword ptr [rbp+0D0h+var_120+8], r13d
0x1400789c8  mov     dword ptr [rbp+0D0h+var_120+0Ch], r12d
0x1400789cc  mov     [rbp+0D0h+var_130], rax
0x1400789d0  test    rax, rax
0x1400789d3  jz      short loc_140078A0C
0x1400789d5  cmp     dword ptr [rdi+82Ch], 3
0x1400789dc  jbe     short loc_140078A0C
0x1400789de  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400789e5  nop     dword ptr [rax+rax+00h]
0x1400789ea  mov     rdx, [rbp+0D0h+var_130]
0x1400789ee  xor     r9d, r9d
0x1400789f1  mov     rcx, rax
0x1400789f4  mov     r8b, 5
0x1400789f7  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400789fe  nop     dword ptr [rax+rax+00h]
0x140078a03  mov     r8d, [rsp+1D0h+var_160]
0x140078a08  mov     [rbp+0D0h+var_70], rax
0x140078a0c  mov     rax, [rbp+0D0h+var_70]
0x140078a10  mov     r11, [rbp+0D0h+var_C0]
0x140078a14  mov     [rbp+0D0h+var_130], rax
0x140078a18  test    rax, rax
0x140078a1b  jz      loc_140078D9C
0x140078a21  mov     r11d, [rsi+20h]
0x140078a25  mov     r10d, [rsi+24h]
0x140078a29  mov     r9d, [rsi+28h]
0x140078a2d  mov     r8d, [rsi+2Ch]
0x140078a31  test    r15d, r15d
0x140078a34  jz      short loc_140078A44
0x140078a36  inc     r11d
0x140078a39  add     r9d, 8
0x140078a3d  inc     r10d
0x140078a40  add     r8d, 6
0x140078a44  mov     ecx, [rax+38h]
0x140078a47  mov     edx, [rax+3Ch]
0x140078a4a  xor     eax, eax
0x140078a4c  test    r11d, r11d
0x140078a4f  cmovs   r11d, eax
0x140078a53  test    r10d, r10d
0x140078a56  mov     [rbp+0D0h+var_100.left], r11d
0x140078a5a  cmovs   r10d, eax
0x140078a5e  cmp     ecx, r9d
0x140078a61  mov     [rbp+0D0h+var_100.top], r10d
0x140078a65  cmovl   r9d, ecx
0x140078a69  cmp     edx, r8d
0x140078a6c  mov     [rbp+0D0h+var_100.right], r9d
0x140078a70  cmovl   r8d, edx
0x140078a74  cmp     r9d, r11d
0x140078a77  mov     r11, [rbp+0D0h+var_C0]
0x140078a7b  mov     [rbp+0D0h+var_100.bottom], r8d
0x140078a7f  jl      loc_140078F25
0x140078a85  cmp     r8d, r10d
0x140078a88  jge     short loc_140078A8E
0x140078a8a  mov     [rbp+0D0h+var_100.top], r8d
0x140078a8e  neg     r15d
0x140078a91  mov     r12d, 3
0x140078a97  xorps   xmm0, xmm0
0x140078a9a  sbb     r9d, r9d
0x140078a9d  and     r9d, r12d
0x140078aa0  test    dword ptr [rdi+28h], 400h
0x140078aa7  movups  [rbp+0D0h+var_60], xmm0
0x140078aab  mov     [rbp+0D0h+var_EC], r9d
0x140078aaf  jnz     loc_140078CA7
0x140078ab5  movsx   ecx, word ptr [rsi+6]
0x140078ab9  xor     ebx, ebx
0x140078abb  movsx   eax, word ptr [rsi+4]
0x140078abf  xor     r13d, r13d
0x140078ac2  mov     edx, [rbp+0D0h+var_150]
0x140078ac5  mov     r8d, [rbp+0D0h+var_F0]
0x140078ac9  and     edx, 20h
0x140078acc  mov     [rdi+4Ch], ecx
0x140078acf  mov     ecx, [rbp+0D0h+var_150]
0x140078ad2  mov     [rdi+48h], eax
0x140078ad5  and     ecx, 0Ch
0x140078ad8  mov     eax, [rdi+40h]
0x140078adb  or      ecx, r14d
0x140078ade  mov     [rsp+1D0h+var_168], eax
0x140078ae2  mov     eax, [rdi+44h]
0x140078ae5  mov     [rsp+1D0h+var_16C], eax
0x140078ae9  xor     eax, eax
0x140078aeb  mov     [rsp+1D0h+var_170], ecx
0x140078aef  mov     [rsp+1D0h+var_160], eax
0x140078af3  test    r8d, r8d
0x140078af6  jnz     loc_140079062
0x140078afc  or      r15d, 0FFFFFFFFh
0x140078b00  test    edx, edx
0x140078b02  jnz     loc_1400790BE
0x140078b08  mov     r10, [rdi+0B60h]
0x140078b0f  test    r10, r10
0x140078b12  jz      loc_140078E07
0x140078b18  test    eax, eax
0x140078b1a  jnz     loc_14007904D
0x140078b20  mov     r8, [rbp+0D0h+var_130]
0x140078b24  test    r8, r8
0x140078b27  jz      loc_140078E93
0x140078b2d  mov     eax, [rdi+840h]
0x140078b33  test    al, 20h
0x140078b35  jz      loc_14007902C
0x140078b3b  movsx   edx, word ptr [rsi+6]
0x140078b3f  mov     eax, ecx
0x140078b41  movsx   ecx, word ptr [rsi+4]
0x140078b45  or      eax, 10h
0x140078b48  movaps  xmm0, xmmword ptr [rbp+0D0h+var_100.left]
0x140078b4c  add     edx, r9d
0x140078b4f  mov     [rsp+1D0h+fl], eax
0x140078b53  add     ecx, r9d
0x140078b56  lea     rax, [rbp+0D0h+var_60]
0x140078b5a  movdqa  [rbp+0D0h+var_60], xmm0
0x140078b5f  mov     [rsp+1D0h+prcl], rax
0x140078b64  add     r8, 18h
0x140078b68  mov     eax, [rsp+1D0h+var_16C]
0x140078b6c  xor     r9d, r9d
0x140078b6f  mov     [rsp+1D0h+y], eax
0x140078b73  mov     eax, [rsp+1D0h+var_168]
0x140078b77  mov     [rsp+1D0h+x], eax
0x140078b7b  mov     rax, r10
0x140078b7e  mov     [rsp+1D0h+yHot], edx
0x140078b82  xor     edx, edx
0x140078b84  mov     [rsp+1D0h+xHot], ecx
0x140078b88  mov     rcx, [rbp+0D0h+pso]
0x140078b8c  call    _guard_dispatch_icall
0x140078b91  mov     ecx, eax
0x140078b93  cmp     eax, r12d
0x140078b96  jz      loc_1400791C4
0x140078b9c  mov     ebx, eax
0x140078b9e  shr     ebx, 1
0x140078ba0  and     ebx, r14d
0x140078ba3  mov     eax, ebx
0x140078ba5  xor     eax, r14d
0x140078ba8  test    cl, 4
0x140078bab  jnz     loc_1400791CC
0x140078bb1  mov     r14d, eax
0x140078bb4  test    r14d, r14d
0x140078bb7  jnz     loc_14007902C
0x140078bbd  xor     r12d, r12d
0x140078bc0  mov     ecx, r12d
0x140078bc3  call    ?CursorTypeUsage@GreCursor@InputTraceLogging@@SAXW4_TRACING_CURSOR_USAGE_TYPE@@@Z; InputTraceLogging::GreCursor::CursorTypeUsage(_TRACING_CURSOR_USAGE_TYPE)
0x140078bc8  test    r14d, r14d
0x140078bcb  jnz     loc_1400790E5
0x140078bd1  mov     eax, [rdi+28h]
0x140078bd4  test    al, 4
  ... truncated ...
```
