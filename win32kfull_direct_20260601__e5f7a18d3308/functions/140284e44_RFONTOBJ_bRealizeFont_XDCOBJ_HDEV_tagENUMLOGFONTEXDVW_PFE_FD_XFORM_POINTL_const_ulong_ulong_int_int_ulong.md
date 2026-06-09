# RFONTOBJ::bRealizeFont(XDCOBJ &,HDEV__ *,tagENUMLOGFONTEXDVW *,PFE *,_FD_XFORM *,_POINTL * const,ulong,ulong,int,int,ulong)

- ea: `0x140284e44`
- end: `0x140285a58`
- name: `?bRealizeFont@RFONTOBJ@@QEAAHAEAVXDCOBJ@@PEAUHDEV__@@PEAUtagENUMLOGFONTEXDVW@@PEAVPFE@@PEAU_FD_XFORM@@QEAU_POINTL@@KKHHK@Z`
- size: `3092`
- prototype: `__int64 __usercall@<rax>(RFONTOBJ *__hidden this@<rcx>, struct XDCOBJ *@<rdx>, HDEV@<r8>, struct tagENUMLOGFONTEXDVW *@<r9>, struct PFE *, struct _FD_XFORM *, struct _POINTL *const, unsigned int, unsigned int, int, int, unsigned int)`
- caller_count: `3`
- callee_count: `31`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140047d64`
- `0x1400abcb8`
- `0x1400ace68`

## callees

- `0x140001d04`
- `0x140043c58`
- `0x140043e10`
- `0x140045ec8`
- `0x140048f4c`
- `0x1400abaf4`
- `0x140108d40`
- `0x14010b150`
- `0x14010c2b8`
- `0x14010cea0`
- `0x140132580`
- `0x1401325d0`
- `0x140136e78`
- `0x140137198`
- `0x140137284`
- `0x1401376f8`
- `0x140181590`
- `0x14018d034`
- `0x14019f4f8`
- `0x1401eb5ec`
- `0x1402002e0`
- `0x14020038c`
- `0x14020365c`
- `0x140233c50`
- `0x1402425cc`
- `0x14026db38`
- `0x140284e44`
- `0x140342f7a`
- `0x140342fa0`
- `0x140343080`
- `0x140343500`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x1402858cf`
- `ntoskrnl!_wcsicmp` at `0x1402858ed`
- `ntoskrnl!_wcsicmp` at `0x140285907`
- `ntoskrnl!_wcsicmp` at `0x140285921`
- `ntoskrnl!_wcsicmp` at `0x14028593b`
- `ntoskrnl!_wcsicmp` at `0x140285955`
- `ntoskrnl!_wcsicmp` at `0x1402858cf`
- `ntoskrnl!_wcsicmp` at `0x1402858ed`
- `ntoskrnl!_wcsicmp` at `0x140285907`
- `ntoskrnl!_wcsicmp` at `0x140285921`
- `ntoskrnl!_wcsicmp` at `0x14028593b`
- `ntoskrnl!_wcsicmp` at `0x140285955`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140284e9c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140284e9c`
- `win32kbase!PopThreadGuardedObject` at `0x14028513a`
- `win32kbase!PopThreadGuardedObject` at `0x1402854b3`
- `win32kbase!PopThreadGuardedObject` at `0x1402856b0`
- `win32kbase!PopThreadGuardedObject` at `0x140285738`
- `win32kbase!PopThreadGuardedObject` at `0x14028513a`
- `win32kbase!PopThreadGuardedObject` at `0x1402854b3`
- `win32kbase!PopThreadGuardedObject` at `0x1402856b0`
- `win32kbase!PopThreadGuardedObject` at `0x140285738`
- `win32kbase!PushThreadGuardedObject` at `0x14028511d`
- `win32kbase!PushThreadGuardedObject` at `0x140285487`
- `win32kbase!PushThreadGuardedObject` at `0x140285693`
- `win32kbase!PushThreadGuardedObject` at `0x14028571b`
- `win32kbase!PushThreadGuardedObject` at `0x14028511d`
- `win32kbase!PushThreadGuardedObject` at `0x140285487`
- `win32kbase!PushThreadGuardedObject` at `0x140285693`
- `win32kbase!PushThreadGuardedObject` at `0x14028571b`
- `win32kbase!lNormAngle` at `0x140285358`
- `win32kbase!lNormAngle` at `0x140285358`
- `win32kbase!?vGetCoefficient@EXFORMOBJ@@QEBAXPEAUtagFLOATOBJ_XFORM@@@Z` at `0x140285999`
- `win32kbase!?vGetCoefficient@EXFORMOBJ@@QEBAXPEAUtagFLOATOBJ_XFORM@@@Z` at `0x140285999`
- `win32kbase!Win32FreePool` at `0x140285107`
- `win32kbase!Win32FreePool` at `0x14028567a`
- `win32kbase!Win32FreePool` at `0x140285702`
- `WIN32K!W32GetSessionState` at `0x140285383`
- `WIN32K!W32GetSessionState` at `0x14028564d`
- `WIN32K!W32GetSessionState` at `0x14028575b`
- `WIN32K!W32GetSessionState` at `0x140285383`
- `WIN32K!W32GetSessionState` at `0x14028564d`
- `WIN32K!W32GetSessionState` at `0x14028575b`

## string_xrefs

- `0x1402858c2`: `Courier New`

## pseudocode

```c
__int64 __fastcall RFONTOBJ::bRealizeFont(
        RFONTOBJ *this,
        struct XDCOBJ *a2,
        _QWORD *a3,
        struct tagENUMLOGFONTEXDVW *a4,
        struct PFE *a5,
        struct _FD_XFORM *a6,
        struct _POINTL *const a7,
        unsigned int a8,
        unsigned int a9,
        int a10,
        int a11,
        unsigned int a12)
{
  Gre::Base *v16; // rcx
  struct _FD_GLYPHSET *v17; // rsi
  __int64 v18; // rax
  __int64 v19; // r15
  __int64 v20; // rax
  __int64 v21; // rax
  char v22; // r14
  __int64 v23; // rcx
  __int64 v24; // r15
  __int64 v25; // rdx
  int v26; // ecx
  __int128 v27; // xmm1
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r11
  __int64 v31; // rcx
  __int64 v32; // r11
  __int64 v33; // rcx
  __int64 v34; // r11
  __int64 v35; // rcx
  __int64 v36; // r11
  int v37; // eax
  __int64 v38; // rcx
  unsigned int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rcx
  int v44; // esi
  __int64 v45; // rdi
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  unsigned int (__fastcall *v49)(__int64, _BYTE *); // rax
  __int64 v50; // rcx
  int v51; // eax
  unsigned int v52; // edi
  __int64 v53; // rsi
  __int64 v54; // rsi
  __int64 v55; // rdx
  unsigned int v56; // ecx
  _DWORD *v57; // rsi
  const wchar_t *v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // r14
  _DWORD *v62; // rax
  __int64 v63; // rdx
  int v64; // ecx
  int inited; // eax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // rcx
  __int64 v70; // rdi
  bool v71; // zf
  int v72; // ecx
  struct _LIST_ENTRY *v73; // rax
  struct _LIST_ENTRY *Flink; // rdx
  __int64 v75; // rdi
  struct _LIST_ENTRY *v76; // rcx
  _QWORD *v77; // rcx
  __int64 v78; // rdx
  _QWORD *v79; // rax
  unsigned int v80; // edx
  BOOL v81; // ecx
  __int64 v82; // rcx
  char v83; // dl
  __int64 v84; // rcx
  const wchar_t *v85; // rdi
  __int64 v86; // rcx
  _BYTE *v87; // r9
  float v88; // xmm1_4
  int v89; // edx
  unsigned __int8 *v90; // r8
  __int64 v91; // rdx
  unsigned int v93; // [rsp+50h] [rbp-B0h] BYREF
  struct PFE *v94; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v95[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v96; // [rsp+68h] [rbp-98h]
  int v97; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v98[4]; // [rsp+78h] [rbp-88h] BYREF
  int v99; // [rsp+7Ch] [rbp-84h]
  _QWORD *v100; // [rsp+80h] [rbp-80h] BYREF
  __int64 v101; // [rsp+88h] [rbp-78h] BYREF
  __int64 v102; // [rsp+90h] [rbp-70h] BYREF
  _FD_DEVICEMETRICS v103; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE Str2[32]; // [rsp+120h] [rbp+20h] BYREF

  v94 = a5;
  v17 = PFEOBJ::pfdg((PFEOBJ *)&v94);
  if ( !v17 )
    goto LABEL_105;
  if ( !*(_QWORD *)(*((_QWORD *)Gre::Base::Globals(v16) + 548) + 40LL) )
  {
    *(_QWORD *)this = 0;
    goto LABEL_104;
  }
  v18 = NSInstrumentation::CTypeIsolation<237568,928>::Allocate();
  *(_QWORD *)this = v18;
  if ( !v18 )
  {
LABEL_104:
    PFEOBJ::vFreepfdg((PFEOBJ *)&v94);
LABEL_105:
    *(_QWORD *)this = 0;
    goto LABEL_106;
  }
  v96 = *(_QWORD *)a5;
  v19 = v96;
  v100 = a3;
  *(_DWORD *)(*(_QWORD *)this + 32LL) = PDEVOBJ::ulLogPixelsX((PDEVOBJ *)&v100);
  *(_DWORD *)(*(_QWORD *)this + 36LL) = PDEVOBJ::ulLogPixelsY((PDEVOBJ *)&v100);
  *(_DWORD *)(*(_QWORD *)this + 40LL) = a9;
  *(_DWORD *)(*(_QWORD *)this + 12LL) = a8 | PFEOBJ::flFontType((PFEOBJ *)&v94);
  *(_QWORD *)(*(_QWORD *)this + 48LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 56LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 4LL) = *((_DWORD *)a5 + 2);
  *(_QWORD *)(*(_QWORD *)this + 24LL) = *(_QWORD *)(v19 + 88);
  if ( (*(_DWORD *)(*(_QWORD *)this + 12LL) & 4) != 0 )
    v20 = *((unsigned int *)a5 + 20);
  else
    v20 = 0;
  *(_QWORD *)(*(_QWORD *)this + 16LL) = v20;
  *(struct _FD_XFORM *)(*(_QWORD *)this + 136LL) = *a6;
  *(struct _FD_XFORM *)(*(_QWORD *)this + 152LL) = *a6;
  *(struct _FD_XFORM *)(*(_QWORD *)this + 356LL) = *a6;
  *(struct _POINTL *)(*(_QWORD *)this + 656LL) = *a7;
  EXFORMOBJ::vInit((EXFORMOBJ *)(*(_QWORD *)this + 224LL), (struct MATRIX *)(*(_QWORD *)this + 232LL), 0);
  RFONTOBJ::vSetNotionalToDevice(this, (struct EXFORMOBJ *)(*(_QWORD *)this + 224LL));
  *(_QWORD *)(*(_QWORD *)this + 120LL) = a5;
  *(_QWORD *)(*(_QWORD *)this + 128LL) = *(_QWORD *)a5;
  *(_QWORD *)(*(_QWORD *)this + 728LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 736LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 744LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 752LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 840LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 720LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 848LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 844LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 852LL) = *((_DWORD *)a5 + 3) & 0x100;
  *(_QWORD *)(*(_QWORD *)this + 104LL) = a3;
  v21 = a3[223];
  v22 = 0;
  v23 = *(_QWORD *)this;
  v93 = 0;
  *(_QWORD *)(v23 + 112) = v21;
  *(_DWORD *)(*(_QWORD *)this + 168LL) = 1;
  *(_DWORD *)(*(_QWORD *)this + 724LL) = *(_DWORD *)(*((_QWORD *)a5 + 4) + 48LL);
  *(_QWORD *)(*(_QWORD *)this + 472LL) = v17;
  v24 = *((_QWORD *)a5 + 4);
  v95[0] = *(_WORD *)(v24 + 116);
  RFONTOBJ::vXlatGlyphArray(this, v95, 1u, &v93, 2u, 0);
  *(_DWORD *)(*(_QWORD *)this + 456LL) = v93;
  *(_DWORD *)(*(_QWORD *)this + 720LL) &= ~0x40u;
  memset_0(&v103, 0, sizeof(v103));
  *(_QWORD *)(*(_QWORD *)this + 96LL) = *(_QWORD *)(v96 + 96);
  if ( !(unsigned int)RFONTOBJ::bGetDEVICEMETRICS(this, &v103) )
  {
    v25 = *(_QWORD *)this;
LABEL_9:
    memset(Str2, 0, sizeof(Str2));
    PushThreadGuardedObject(Str2, v25, Win32FreePool);
    RFONTOBJ::vDestroyFont(this, 1);
    PopThreadGuardedObject(Str2);
    FreeIsolatedType<NSInstrumentation::CTypeIsolation<237568,928>>(*(_QWORD *)this);
    *(_QWORD *)this = 0;
LABEL_106:
    v91 = 0;
    return *(unsigned int *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v94, v91);
  }
  *(POINTE *)(*(_QWORD *)this + 392LL) = v103.pteBase;
  *(POINTE *)(*(_QWORD *)this + 412LL) = v103.pteSide;
  v26 = *(_DWORD *)(*(_QWORD *)a2 + 352LL);
  v27 = *(_OWORD *)(*(_QWORD *)a2 + 336LL);
  v28 = *(_QWORD *)this;
  *(_OWORD *)(v28 + 172) = *(_OWORD *)(*(_QWORD *)a2 + 320LL);
  *(_OWORD *)(v28 + 188) = v27;
  *(_DWORD *)(v28 + 204) = v26;
  if ( !(unsigned int)RFONTOBJ::bCalcLayoutUnits(this, a2)
    || !(unsigned int)bGetNtoWScales(
                        (struct EPOINTFL *)(*(_QWORD *)this + 212LL),
                        a2,
                        (struct _FD_XFORM *)(*(_QWORD *)this + 356LL),
                        (struct PFEOBJ *)&v94,
                        (int *)(*(_QWORD *)this + 220LL)) )
  {
    v25 = *(_QWORD *)this;
    goto LABEL_9;
  }
  v93 = 0;
  bFToL(v29, &v93, 0);
  *(_DWORD *)(v30 + 320) = v93;
  v93 = 0;
  bFToL(v31, &v93, 0);
  *(_DWORD *)(v32 + 324) = v93;
  v93 = 0;
  bFToL(v33, &v93, 0);
  *(_DWORD *)(v34 + 328) = v93;
  v93 = 0;
  bFToL(v35, &v93, 0);
  *(_DWORD *)(v36 + 332) = v93;
  *(_DWORD *)(*(_QWORD *)this + 428LL) = -1;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 208LL) == 1 )
  {
    v37 = *(_DWORD *)(v24 + 48);
    if ( (v37 & 4) == 0 )
    {
      if ( (v37 & 0x10) == 0 )
      {
        v39 = ulSimpleDeviceOrientation(this);
LABEL_21:
        v43 = *(_QWORD *)this;
        *(_DWORD *)(*(_QWORD *)this + 388LL) = v39;
        goto LABEL_22;
      }
      v38 = (unsigned int)(3600 - a4->elfEnumLogfontEx.elfLogFont.lfEscapement);
LABEL_20:
      v39 = lNormAngle(v38);
      goto LABEL_21;
    }
LABEL_19:
    v38 = (unsigned int)(3600 - a4->elfEnumLogfontEx.elfLogFont.lfOrientation);
    goto LABEL_20;
  }
  *(_DWORD *)(*(_QWORD *)this + 388LL) = RFONTOBJ::ulSimpleOrientation(this, a2);
  v43 = 3600;
  if ( *(_DWORD *)(*(_QWORD *)this + 388LL) >= 0xE10u && (*(_DWORD *)(*(_QWORD *)this + 724LL) & 0x10) != 0 )
    goto LABEL_19;
LABEL_22:
  v44 = a10;
  *(_DWORD *)(*(_QWORD *)this + 664LL) = a10;
  v45 = *(_QWORD *)(*(_QWORD *)this + 96LL);
  v46 = *(_QWORD *)(*(_QWORD *)(W32GetSessionState(v43, v40, v41, v42) + 96) + 24136LL);
  if ( *(_QWORD *)(*(_QWORD *)this + 96LL) == v46 )
  {
    if ( (unsigned int)UmfdQueryFontCapsEx(*(_QWORD *)(*(_QWORD *)this + 24LL), v46, v98) != -1 )
      v22 = v99;
  }
  else
  {
    v49 = *(unsigned int (__fastcall **)(__int64, _BYTE *))(v45 + 3032);
    if ( v49 && v49(2, v98) != -1 )
      v22 = v99;
  }
  v50 = *(_QWORD *)this;
  if ( (*(_DWORD *)(v45 + 40) & 0x2000) != 0 )
  {
    v51 = *(_DWORD *)(v50 + 12) & 0x10010000;
    *(_DWORD *)(v50 + 92) = 0;
    v52 = v51 != 0 ? 400 : 800;
    *(_DWORD *)(*(_QWORD *)this + 88LL) = 1;
    v53 = *(_QWORD *)this;
    if ( a10 )
    {
      *(_DWORD *)(v53 + 88) = 2;
    }
    else
    {
      v54 = *(_QWORD *)(v53 + 104);
      if ( v54 )
      {
        v94 = (struct PFE *)v54;
        if ( (unsigned int)PDEVOBJ::bAllowDDICall((PDEVOBJ *)&v94) && *(_QWORD *)(v54 + 2976) )
        {
          v55 = *(_QWORD *)this;
          memset(Str2, 0, sizeof(Str2));
          PushThreadGuardedObject(Str2, v55, vRestartbRealizeFont);
          *(_DWORD *)(*(_QWORD *)this + 88LL) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v54 + 2976))(
                                                  *(_QWORD *)(*(_QWORD *)this + 112LL),
                                                  *(_QWORD *)this);
          PopThreadGuardedObject(Str2);
        }
        if ( (*(_DWORD *)(v54 + 1808) & 0x40000000) != 0 )
        {
          v56 = 3 * PDEVOBJ::ulLogPixelsY((PDEVOBJ *)&v94);
          if ( v56 <= 0x320 )
            v56 = v52;
          v52 = v56;
          if ( v56 > 0x960 )
            v52 = 2400;
        }
      }
    }
    v57 = *(_DWORD **)this;
    v50 = (unsigned int)(*(_DWORD *)(*(_QWORD *)this + 88LL) - 1);
    if ( *(_DWORD *)(*(_QWORD *)this + 88LL) == 1 )
    {
      v46 = (unsigned int)v57[85];
      if ( *(char *)(v24 + 52) < 0 )
      {
        v50 = (unsigned int)v57[88];
        if ( (unsigned int)v46 > 3 * (int)v50 )
        {
          v93 = v57[88];
          v58 = (const wchar_t *)(v24 + *(int *)(v24 + 16));
          wcscpy((wchar_t *)Str2, L"Cambria Math");
          if ( wcsncmp_0(v58, (const wchar_t *)Str2, 0xDu) )
          {
            if ( (unsigned int)dword_14039BA20 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14039BA20, 0x400000000000LL) )
            {
              v59 = *(_QWORD *)this;
              *(_DWORD *)v95 = *(_DWORD *)(*(_QWORD *)this + 352LL);
              v97 = *(_DWORD *)(v59 + 340);
              v60 = *(int *)(v24 + 16);
              LODWORD(v94) = v52;
              v102 = v24 + v60;
              v101 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v59,
                (unsigned int)byte_14036DCEB,
                v47,
                v48,
                (__int64)&v101,
                (__int64)&v102,
                (__int64)&v94,
                (__int64)&v97,
                (__int64)v95);
            }
            v57 = *(_DWORD **)this;
          }
          v46 = v93;
        }
      }
      if ( (v22 & 2) == 0 || (v57[181] & 0x8000) != 0 && (v57[84] > 2 * v52 || (unsigned int)v46 > v52) )
        v57[22] = 2;
    }
    else if ( *(_DWORD *)(*(_QWORD *)this + 88LL) == 2 && (v22 & 1) == 0 )
    {
      v57[22] = 1;
    }
    v44 = a10;
  }
  else
  {
    *(_DWORD *)(v50 + 92) = 1;
    *(_DWORD *)(*(_QWORD *)this + 88LL) = 0;
  }
  v61 = *(_QWORD *)(W32GetSessionState(v50, v46, v47, v48) + 96);
  if ( *(_DWORD *)(*(_QWORD *)this + 88LL) == 2 )
    *(_DWORD *)(*(_QWORD *)this + 12LL) &= 0x8FFEFFFF;
  v62 = *(_DWORD **)this;
  if ( v44 && v62[22] != 2 )
    goto LABEL_63;
  if ( !a11 || (v64 = 1, v62[97]) )
    v64 = 0;
  v62[162] = v64;
  inited = RFONTOBJ::bInitCache(this, a12);
  v69 = *(_QWORD *)this;
  if ( !inited )
  {
LABEL_63:
    v63 = *(_QWORD *)this;
    memset(Str2, 0, sizeof(Str2));
    PushThreadGuardedObject(Str2, v63, Win32FreePool);
    RFONTOBJ::vDestroyFont(this, 1);
    PopThreadGuardedObject(Str2);
    FreeIsolatedType<NSInstrumentation::CTypeIsolation<237568,928>>(*(_QWORD *)this);
    *(_QWORD *)this = 0;
    goto LABEL_106;
  }
  *(_QWORD *)(v69 + 696) = 0;
  v70 = *(_QWORD *)(W32GetSessionState(v69, v66, v67, v68) + 96);
  SEMOBJ<18>::SEMOBJ<18>(&v101, v70 + 4864);
  v71 = (*(_DWORD *)(v70 + 24024))++ == -1;
  v72 = *(_DWORD *)(v70 + 24024);
  if ( v71 )
  {
    *(_DWORD *)(v70 + 24024) = 1;
    v72 = 1;
  }
  **(_DWORD **)this = v72;
  *(_DWORD *)(*(_QWORD *)this + 668LL) = 1;
  v73 = PDEVOBJ::prfntActive((PDEVOBJ *)&v100);
  Flink = v73->Flink;
  if ( v73->Flink->Blink != v73 )
    goto LABEL_101;
  v75 = v96;
  v76 = (struct _LIST_ENTRY *)(*(_QWORD *)this + 672LL);
  v76->Flink = Flink;
  v76->Blink = v73;
  Flink->Blink = v76;
  v73->Flink = v76;
  v77 = (_QWORD *)(v75 + 72);
  v78 = *(_QWORD *)(v75 + 72);
  if ( *(_QWORD *)(v78 + 8) != v75 + 72 )
LABEL_101:
    __fastfail(3u);
  v79 = (_QWORD *)(*(_QWORD *)this + 488LL);
  v79[1] = v77;
  *v79 = v78;
  *(_QWORD *)(v78 + 8) = v79;
  *v77 = v79;
  SEMOBJ<18>::vUnlock(&v101);
  v80 = *(_DWORD *)(*(_QWORD *)this + 12LL) | 1;
  if ( *(_DWORD *)(*(_QWORD *)this + 88LL) != 1 )
    v80 = *(_DWORD *)(*(_QWORD *)this + 12LL) & 0xFFFFFFFE;
  *(_DWORD *)(*(_QWORD *)this + 12LL) = v80;
  *(_DWORD *)(*(_QWORD *)this + 208LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 208LL);
  v81 = *(_DWORD *)(v61 + 19552) && (*((_DWORD *)a5 + 3) & 0x10) != 0;
  *(_DWORD *)(*(_QWORD *)this + 716LL) = v81;
  v82 = *(_QWORD *)this;
  if ( (*(_DWORD *)(*(_QWORD *)this + 12LL) & 0x10000000) != 0 )
  {
    if ( (*(_BYTE *)(v82 + 204) & 1) == 0 || (v83 = 1, *(_DWORD *)(v82 + 320)) )
      v83 = 0;
    v84 = *(_QWORD *)(*(_QWORD *)(v82 + 120) + 32LL);
    if ( (*(_DWORD *)(v84 + 48) & 0x401000) != 0 && v83 && *(_WORD *)(v84 + 46) <= 0x190u )
    {
      v85 = (const wchar_t *)(v84 + *(int *)(v84 + 8));
      if ( !_wcsicmp(v85, L"Courier New")
        || !_wcsicmp(v85, L"Rod")
        || !_wcsicmp(v85, L"Rod Transparent")
        || !_wcsicmp(v85, L"Fixed Miriam Transparent")
        || !_wcsicmp(v85, L"Miriam Fixed")
        || !_wcsicmp(v85, L"Simplified Arabic Fixed") )
      {
        *(_DWORD *)(*(_QWORD *)this + 64LL) = 1;
      }
      v75 = v96;
    }
    v86 = *(_QWORD *)this;
    if ( (*(_DWORD *)(*(_QWORD *)this + 12LL) & 0x20000000) != 0 )
    {
      memset(Str2, 0, 24);
      EXFORMOBJ::vGetCoefficient((EXFORMOBJ *)(v86 + 224), (struct tagFLOATOBJ_XFORM *)Str2);
      v87 = *(_BYTE **)(v75 + 200);
      v88 = *(float *)&Str2[12] * (float)*(__int16 *)(v24 + 56);
      *(float *)&Str2[12] = v88;
      if ( v87 && (v89 = 0, *v87) )
      {
        while ( 1 )
        {
          v90 = &v87[80 * v89 + 4];
          if ( *v90 == (int)v88 )
            break;
          if ( ++v89 >= (unsigned int)(unsigned __int8)*v87 )
            goto LABEL_98;
        }
      }
      else
      {
LABEL_98:
        v90 = 0;
      }
      *(_QWORD *)(*(_QWORD *)this + 72LL) = v90;
    }
  }
  v91 = 1;
  return *(unsigned int *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v94, v91);
}

```

## disassembly

```asm
0x140284e44  push    rbp
0x140284e46  push    rbx
0x140284e47  push    rsi
0x140284e48  push    rdi
0x140284e49  push    r12
0x140284e4b  push    r13
0x140284e4d  push    r14
0x140284e4f  push    r15
0x140284e51  lea     rbp, [rsp-58h]
0x140284e56  sub     rsp, 158h
0x140284e5d  mov     rax, cs:__security_cookie
0x140284e64  xor     rax, rsp
0x140284e67  mov     [rbp+90h+var_50], rax
0x140284e6b  mov     r12, [rbp+90h+arg_20]
0x140284e72  mov     rbx, rcx
0x140284e75  lea     rcx, [rsp+190h+var_138]; this
0x140284e7a  mov     [rsp+190h+var_138], r12
0x140284e7f  mov     rdi, r9
0x140284e82  mov     r14, r8
0x140284e85  mov     r13, rdx
0x140284e88  call    ?pfdg@PFEOBJ@@QEAAPEAU_FD_GLYPHSET@@XZ; PFEOBJ::pfdg(void)
0x140284e8d  xor     r15d, r15d
0x140284e90  mov     rsi, rax
0x140284e93  test    rax, rax
0x140284e96  jz      loc_140285A26
0x140284e9c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140284ea3  nop     dword ptr [rax+rax+00h]
0x140284ea8  mov     rcx, [rax+1120h]
0x140284eaf  mov     rcx, [rcx+28h]
0x140284eb3  test    rcx, rcx
0x140284eb6  jz      loc_140285A19
0x140284ebc  call    ?Allocate@?$CTypeIsolation@$0DKAAA@$0DKA@@NSInstrumentation@@IEAAPEAXXZ; NSInstrumentation::CTypeIsolation<237568,928>::Allocate(void)
0x140284ec1  mov     [rbx], rax
0x140284ec4  test    rax, rax
0x140284ec7  jz      loc_140285A1C
0x140284ecd  mov     r15, [r12]
0x140284ed1  lea     rcx, [rbp+90h+var_110]; this
0x140284ed5  mov     [rsp+190h+var_128], r15
0x140284eda  mov     [rbp+90h+var_110], r14
0x140284ede  call    ?ulLogPixelsX@PDEVOBJ@@QEBAKXZ; PDEVOBJ::ulLogPixelsX(void)
0x140284ee3  mov     rcx, [rbx]
0x140284ee6  mov     [rcx+20h], eax
0x140284ee9  lea     rcx, [rbp+90h+var_110]; this
0x140284eed  call    ?ulLogPixelsY@PDEVOBJ@@QEBAKXZ; PDEVOBJ::ulLogPixelsY(void)
0x140284ef2  mov     rcx, [rbx]
0x140284ef5  mov     [rcx+24h], eax
0x140284ef8  mov     rcx, [rbx]
0x140284efb  mov     eax, [rbp+90h+arg_40]
0x140284f01  mov     [rcx+28h], eax
0x140284f04  lea     rcx, [rsp+190h+var_138]; this
0x140284f09  call    ?flFontType@PFEOBJ@@QEAAKXZ; PFEOBJ::flFontType(void)
0x140284f0e  or      eax, [rbp+90h+arg_38]
0x140284f14  mov     rcx, [rbx]
0x140284f17  mov     [rcx+0Ch], eax
0x140284f1a  mov     rax, [rbx]
0x140284f1d  mov     qword ptr [rax+30h], 0
0x140284f25  mov     rax, [rbx]
0x140284f28  mov     qword ptr [rax+38h], 0
0x140284f30  mov     rcx, [rbx]
0x140284f33  mov     eax, [r12+8]
0x140284f38  mov     [rcx+4], eax
0x140284f3b  mov     rcx, [rbx]
0x140284f3e  mov     rax, [r15+58h]
0x140284f42  mov     [rcx+18h], rax
0x140284f46  mov     rcx, [rbx]
0x140284f49  mov     eax, [rcx+0Ch]
0x140284f4c  test    al, 4
0x140284f4e  jz      short loc_140284F57
0x140284f50  mov     eax, [r12+50h]
0x140284f55  jmp     short loc_140284F59
0x140284f57  xor     eax, eax
0x140284f59  mov     [rcx+10h], rax
0x140284f5d  xor     r8d, r8d; unsigned int
0x140284f60  mov     rax, [rbx]
0x140284f63  mov     rcx, [rbp+90h+arg_28]
0x140284f6a  movups  xmm0, xmmword ptr [rcx]
0x140284f6d  movdqu  xmmword ptr [rax+88h], xmm0
0x140284f75  mov     rax, [rbx]
0x140284f78  movups  xmm1, xmmword ptr [rcx]
0x140284f7b  movdqu  xmmword ptr [rax+98h], xmm1
0x140284f83  mov     rax, [rbx]
0x140284f86  movups  xmm0, xmmword ptr [rcx]
0x140284f89  movdqu  xmmword ptr [rax+164h], xmm0
0x140284f91  mov     rdx, [rbx]
0x140284f94  mov     rax, [rbp+90h+arg_30]
0x140284f9b  mov     rcx, [rax]
0x140284f9e  mov     [rdx+290h], rcx
0x140284fa5  mov     rcx, [rbx]
0x140284fa8  lea     rdx, [rcx+0E8h]; struct MATRIX *
0x140284faf  add     rcx, 0E0h; this
0x140284fb6  call    ?vInit@EXFORMOBJ@@QEAAXPEAUMATRIX@@K@Z; EXFORMOBJ::vInit(MATRIX *,ulong)
0x140284fbb  mov     rdx, [rbx]
0x140284fbe  mov     rcx, rbx; this
0x140284fc1  add     rdx, 0E0h; struct EXFORMOBJ *
0x140284fc8  call    ?vSetNotionalToDevice@RFONTOBJ@@QEAAXAEAVEXFORMOBJ@@@Z; RFONTOBJ::vSetNotionalToDevice(EXFORMOBJ &)
0x140284fcd  mov     rax, [rbx]
0x140284fd0  lea     r9, [rsp+190h+var_140]; unsigned int *
0x140284fd5  mov     edx, 1
0x140284fda  mov     r8d, edx; unsigned int
0x140284fdd  mov     [rax+78h], r12
0x140284fe1  mov     rcx, [rbx]
0x140284fe4  mov     rax, [r12]
0x140284fe8  mov     [rcx+80h], rax
0x140284fef  xor     ecx, ecx
0x140284ff1  mov     rax, [rbx]
0x140284ff4  mov     [rax+2D8h], rcx
0x140284ffb  mov     rax, [rbx]
0x140284ffe  mov     [rax+2E0h], rcx
0x140285005  mov     rax, [rbx]
0x140285008  mov     [rax+2E8h], rcx
0x14028500f  mov     rax, [rbx]
0x140285012  mov     [rax+2F0h], rcx
0x140285019  mov     rax, [rbx]
0x14028501c  mov     [rax+348h], ecx
0x140285022  mov     rax, [rbx]
0x140285025  mov     [rax+2D0h], ecx
0x14028502b  mov     rax, [rbx]
0x14028502e  mov     [rax+350h], ecx
0x140285034  mov     rax, [rbx]
0x140285037  mov     [rax+34Ch], ecx
0x14028503d  mov     ecx, [r12+0Ch]
0x140285042  mov     rax, [rbx]
0x140285045  and     ecx, 100h
0x14028504b  mov     [rax+354h], ecx
0x140285051  mov     rax, [rbx]
0x140285054  mov     [rax+68h], r14
0x140285058  mov     rax, [r14+6F8h]
0x14028505f  xor     r14d, r14d
0x140285062  mov     rcx, [rbx]
0x140285065  mov     [rsp+190h+var_168], r14d; int
0x14028506a  mov     [rsp+190h+var_140], r14d
0x14028506f  mov     dword ptr [rsp+190h+var_170], 2; unsigned int
0x140285077  mov     [rcx+70h], rax
0x14028507b  mov     rax, [rbx]
0x14028507e  mov     [rax+0A8h], edx
0x140285084  lea     rdx, [rsp+190h+var_130]; unsigned __int16 *
0x140285089  mov     rax, [r12+20h]
0x14028508e  mov     rcx, [rbx]
0x140285091  mov     eax, [rax+30h]
0x140285094  mov     [rcx+2D4h], eax
0x14028509a  mov     rcx, rbx; this
0x14028509d  mov     rax, [rbx]
0x1402850a0  mov     [rax+1D8h], rsi
0x1402850a7  mov     r15, [r12+20h]
0x1402850ac  movzx   eax, word ptr [r15+74h]
0x1402850b1  mov     [rsp+190h+var_130], ax
0x1402850b6  call    ?vXlatGlyphArray@RFONTOBJ@@QEAAXPEBGIPEAKKH@Z; RFONTOBJ::vXlatGlyphArray(ushort const *,uint,ulong *,ulong,int)
0x1402850bb  mov     rcx, [rbx]
0x1402850be  mov     eax, [rsp+190h+var_140]
0x1402850c2  mov     [rcx+1C8h], eax
0x1402850c8  mov     rax, [rbx]
0x1402850cb  and     dword ptr [rax+2D0h], 0FFFFFFBFh
0x1402850d2  xor     edx, edx; Val
0x1402850d4  lea     r8d, [r14+7Ch]; Size
0x1402850d8  lea     rcx, [rbp+90h+var_F0]; void *
0x1402850dc  call    memset_0
0x1402850e1  mov     rcx, [rbx]
0x1402850e4  lea     rdx, [rbp+90h+var_F0]; struct _FD_DEVICEMETRICS *
0x1402850e8  mov     rax, [rsp+190h+var_128]
0x1402850ed  mov     rax, [rax+60h]
0x1402850f1  mov     [rcx+60h], rax
0x1402850f5  mov     rcx, rbx; this
0x1402850f8  call    ?bGetDEVICEMETRICS@RFONTOBJ@@QEAAHPEAU_FD_DEVICEMETRICS@@@Z; RFONTOBJ::bGetDEVICEMETRICS(_FD_DEVICEMETRICS *)
0x1402850fd  mov     rcx, [rbx]
0x140285100  test    eax, eax
0x140285102  jnz     short loc_140285156
0x140285104  mov     rdx, rcx
0x140285107  mov     r8, cs:__imp_Win32FreePool
0x14028510e  lea     rcx, [rbp+90h+Str2]
0x140285112  xorps   xmm0, xmm0
0x140285115  movups  [rbp+90h+var_60], xmm0
0x140285119  movups  xmmword ptr [rbp+90h+Str2], xmm0
0x14028511d  call    cs:__imp_PushThreadGuardedObject
0x140285124  nop     dword ptr [rax+rax+00h]
0x140285129  mov     edx, 1; int
0x14028512e  mov     rcx, rbx; this
0x140285131  call    ?vDestroyFont@RFONTOBJ@@QEAAXH@Z; RFONTOBJ::vDestroyFont(int)
0x140285136  lea     rcx, [rbp+90h+Str2]
0x14028513a  call    cs:__imp_PopThreadGuardedObject
0x140285141  nop     dword ptr [rax+rax+00h]
0x140285146  mov     rcx, [rbx]
0x140285149  call    ??$FreeIsolatedType@V?$CTypeIsolation@$0DKAAA@$0DKA@@NSInstrumentation@@@@YAXPEAX@Z; FreeIsolatedType<NSInstrumentation::CTypeIsolation<237568,928>>(void *)
0x14028514e  mov     [rbx], r14
0x140285151  jmp     loc_140285A29
0x140285156  movss   xmm0, [rbp+90h+var_F0.pteBase.x]
0x14028515b  mov     rdx, r13; struct XDCOBJ *
0x14028515e  movss   dword ptr [rcx+188h], xmm0
0x140285166  mov     rax, [rbx]
0x140285169  movss   xmm1, [rbp+90h+var_F0.pteBase.y]
0x14028516e  movss   dword ptr [rax+18Ch], xmm1
0x140285176  mov     rax, [rbx]
0x140285179  movss   xmm0, [rbp+90h+var_F0.pteSide.x]
0x14028517e  movss   dword ptr [rax+19Ch], xmm0
0x140285186  mov     rax, [rbx]
0x140285189  movss   xmm1, [rbp+90h+var_F0.pteSide.y]
0x14028518e  movss   dword ptr [rax+1A0h], xmm1
0x140285196  mov     rax, [r13+0]
0x14028519a  mov     ecx, [rax+160h]
0x1402851a0  movups  xmm0, xmmword ptr [rax+140h]
0x1402851a7  movups  xmm1, xmmword ptr [rax+150h]
0x1402851ae  mov     rax, [rbx]
0x1402851b1  movups  xmmword ptr [rax+0ACh], xmm0
0x1402851b8  movups  xmmword ptr [rax+0BCh], xmm1
0x1402851bf  mov     [rax+0CCh], ecx
0x1402851c5  mov     rcx, rbx; this
0x1402851c8  call    ?bCalcLayoutUnits@RFONTOBJ@@QEAAHAEAVXDCOBJ@@@Z; RFONTOBJ::bCalcLayoutUnits(XDCOBJ &)
0x1402851cd  test    eax, eax
0x1402851cf  jz      loc_140285A11
0x1402851d5  mov     rcx, [rbx]
0x1402851d8  lea     r9, [rsp+190h+var_138]; struct PFEOBJ *
0x1402851dd  mov     rdx, r13; struct XDCOBJ *
0x1402851e0  lea     rax, [rcx+0DCh]
0x1402851e7  lea     r8, [rcx+164h]; struct _FD_XFORM *
0x1402851ee  mov     [rsp+190h+var_170], rax; int *
0x1402851f3  add     rcx, 0D4h; struct EPOINTFL *
0x1402851fa  call    ?bGetNtoWScales@@YAHPEAVEPOINTFL@@AEAVXDCOBJ@@PEAU_FD_XFORM@@AEAVPFEOBJ@@PEAH@Z; bGetNtoWScales(EPOINTFL *,XDCOBJ &,_FD_XFORM *,PFEOBJ &,int *)
0x1402851ff  test    eax, eax
0x140285201  jz      loc_140285A11
0x140285207  mov     r11, [rbx]
0x14028520a  lea     rdx, [rsp+190h+var_140]
0x14028520f  xor     r8d, r8d
0x140285212  mov     [rsp+190h+var_140], r14d
0x140285217  movd    xmm0, dword ptr [r11+134h]
0x140285220  cvtdq2ps xmm0, xmm0
0x140285223  mulss   xmm0, dword ptr [r11+19Ch]
0x14028522c  call    bFToL
0x140285231  mov     r8d, [rsp+190h+var_140]
0x140285236  lea     rdx, [rsp+190h+var_140]
0x14028523b  mov     [r11+140h], r8d
0x140285242  xor     r8d, r8d
0x140285245  mov     r11, [rbx]
0x140285248  mov     [rsp+190h+var_140], r14d
0x14028524d  movd    xmm0, dword ptr [r11+134h]
0x140285256  cvtdq2ps xmm0, xmm0
0x140285259  mulss   xmm0, dword ptr [r11+1A0h]
0x140285262  call    bFToL
0x140285267  mov     r8d, [rsp+190h+var_140]
0x14028526c  lea     rdx, [rsp+190h+var_140]
0x140285271  mov     [r11+144h], r8d
0x140285278  xor     r8d, r8d
0x14028527b  mov     r11, [rbx]
0x14028527e  mov     [rsp+190h+var_140], r14d
0x140285283  movd    xmm0, dword ptr [r11+138h]
0x14028528c  cvtdq2ps xmm0, xmm0
0x14028528f  mulss   xmm0, dword ptr [r11+19Ch]
0x140285298  call    bFToL
0x14028529d  mov     r8d, [rsp+190h+var_140]
0x1402852a2  lea     rdx, [rsp+190h+var_140]
0x1402852a7  mov     [r11+148h], r8d
0x1402852ae  xor     r8d, r8d
0x1402852b1  mov     r11, [rbx]
0x1402852b4  mov     [rsp+190h+var_140], r14d
0x1402852b9  movd    xmm0, dword ptr [r11+138h]
0x1402852c2  cvtdq2ps xmm0, xmm0
0x1402852c5  mulss   xmm0, dword ptr [r11+1A0h]
0x1402852ce  call    bFToL
0x1402852d3  mov     r8d, [rsp+190h+var_140]
0x1402852d8  mov     [r11+14Ch], r8d
0x1402852df  mov     rax, [rbx]
0x1402852e2  mov     dword ptr [rax+1ACh], 0FFFFFFFFh
0x1402852ec  mov     rax, [r13+0]
0x1402852f0  mov     rcx, [rax+3D0h]
0x1402852f7  cmp     dword ptr [rcx+0D0h], 1
0x1402852fe  jnz     short loc_140285327
0x140285300  mov     eax, [r15+30h]
0x140285304  test    al, 4
0x140285306  jz      short loc_14028530F
0x140285308  mov     ecx, 0E10h
0x14028530d  jmp     short loc_140285355
0x14028530f  test    al, 10h
0x140285311  jz      short loc_14028531D
0x140285313  mov     ecx, 0E10h
0x140285318  sub     ecx, [rdi+8]
0x14028531b  jmp     short loc_140285358
0x14028531d  mov     rcx, rbx; struct RFONTOBJ *
0x140285320  call    ?ulSimpleDeviceOrientation@@YAKAEAVRFONTOBJ@@@Z; ulSimpleDeviceOrientation(RFONTOBJ &)
0x140285325  jmp     short loc_140285364
0x140285327  mov     rdx, r13; struct XDCOBJ *
0x14028532a  mov     rcx, rbx; this
0x14028532d  call    ?ulSimpleOrientation@RFONTOBJ@@QEAAKAEAVXDCOBJ@@@Z; RFONTOBJ::ulSimpleOrientation(XDCOBJ &)
0x140285332  mov     rcx, [rbx]
0x140285335  mov     [rcx+184h], eax
0x14028533b  mov     ecx, 0E10h
0x140285340  mov     rax, [rbx]
0x140285343  cmp     [rax+184h], ecx
0x140285349  jb      short loc_14028536D
0x14028534b  mov     eax, [rax+2D4h]
0x140285351  test    al, 10h
0x140285353  jz      short loc_14028536D
0x140285355  sub     ecx, [rdi+0Ch]
0x140285358  call    cs:__imp_lNormAngle
0x14028535f  nop     dword ptr [rax+rax+00h]
0x140285364  mov     rcx, [rbx]
0x140285367  mov     [rcx+184h], eax
0x14028536d  mov     rax, [rbx]
0x140285370  mov     esi, [rbp+90h+arg_48]
0x140285376  mov     [rax+298h], esi
0x14028537c  mov     rax, [rbx]
0x14028537f  mov     rdi, [rax+60h]
0x140285383  call    cs:__imp_W32GetSessionState
  ... truncated ...
```
