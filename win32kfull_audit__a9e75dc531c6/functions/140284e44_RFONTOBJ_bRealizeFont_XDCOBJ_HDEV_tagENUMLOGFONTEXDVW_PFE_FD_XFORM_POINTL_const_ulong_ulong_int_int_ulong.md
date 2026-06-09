# RFONTOBJ::bRealizeFont(XDCOBJ &,HDEV__ *,tagENUMLOGFONTEXDVW *,PFE *,_FD_XFORM *,_POINTL * const,ulong,ulong,int,int,ulong)

- ea: `0x140284e44`
- end: `0x140285a58`
- name: `?bRealizeFont@RFONTOBJ@@QEAAHAEAVXDCOBJ@@PEAUHDEV__@@PEAUtagENUMLOGFONTEXDVW@@PEAVPFE@@PEAU_FD_XFORM@@QEAU_POINTL@@KKHHK@Z`
- size: `3092`
- prototype: `__int64 __fastcall(RFONTOBJ *this, struct XDCOBJ *, _QWORD *, struct tagENUMLOGFONTEXDVW *, struct PFE *, struct _FD_XFORM *, struct _POINTL *const, unsigned int, unsigned int, int, int, unsigned int)`
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
  __int64 *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r15
  __int64 v21; // rax
  __int64 v22; // rax
  char v23; // r14
  __int64 v24; // rcx
  __int64 v25; // r15
  __int64 v26; // rdx
  int v27; // ecx
  __int128 v28; // xmm1
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r11
  __int64 v32; // rcx
  __int64 v33; // r11
  __int64 v34; // rcx
  __int64 v35; // r11
  __int64 v36; // rcx
  __int64 v37; // r11
  int v38; // eax
  __int64 v39; // rcx
  unsigned int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rcx
  int v45; // esi
  __int64 v46; // rdi
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  unsigned int (__fastcall *v50)(__int64, _BYTE *); // rax
  __int64 v51; // rcx
  int v52; // eax
  unsigned int v53; // edi
  __int64 v54; // rsi
  __int64 v55; // rsi
  __int64 v56; // rdx
  unsigned int v57; // ecx
  _DWORD *v58; // rsi
  const wchar_t *v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // r14
  _DWORD *v63; // rax
  __int64 v64; // rdx
  int v65; // ecx
  int inited; // eax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // rcx
  __int64 v71; // rdi
  bool v72; // zf
  int v73; // ecx
  struct _LIST_ENTRY *v74; // rax
  struct _LIST_ENTRY *Flink; // rdx
  __int64 v76; // rdi
  struct _LIST_ENTRY *v77; // rcx
  _QWORD *v78; // rcx
  __int64 v79; // rdx
  _QWORD *v80; // rax
  unsigned int v81; // edx
  BOOL v82; // ecx
  __int64 v83; // rcx
  char v84; // dl
  __int64 v85; // rcx
  const wchar_t *v86; // rdi
  __int64 v87; // rcx
  _BYTE *v88; // r9
  float v89; // xmm1_4
  int v90; // edx
  unsigned __int8 *v91; // r8
  __int64 v92; // rdx
  unsigned int v94; // [rsp+50h] [rbp-B0h] BYREF
  struct PFE *v95; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v96[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v97; // [rsp+68h] [rbp-98h]
  int v98; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v99[4]; // [rsp+78h] [rbp-88h] BYREF
  int v100; // [rsp+7Ch] [rbp-84h]
  _QWORD *v101; // [rsp+80h] [rbp-80h] BYREF
  __int64 v102; // [rsp+88h] [rbp-78h] BYREF
  __int64 v103; // [rsp+90h] [rbp-70h] BYREF
  _FD_DEVICEMETRICS v104; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE Str2[32]; // [rsp+120h] [rbp+20h] BYREF

  v95 = a5;
  v17 = PFEOBJ::pfdg((PFEOBJ *)&v95);
  if ( !v17 )
    goto LABEL_105;
  v18 = *(__int64 **)(*((_QWORD *)Gre::Base::Globals(v16) + 548) + 40LL);
  if ( !v18 )
  {
    *(_QWORD *)this = 0;
    goto LABEL_104;
  }
  v19 = NSInstrumentation::CTypeIsolation<237568,928>::Allocate(v18);
  *(_QWORD *)this = v19;
  if ( !v19 )
  {
LABEL_104:
    PFEOBJ::vFreepfdg((PFEOBJ *)&v95);
LABEL_105:
    *(_QWORD *)this = 0;
    goto LABEL_106;
  }
  v97 = *(_QWORD *)a5;
  v20 = v97;
  v101 = a3;
  *(_DWORD *)(*(_QWORD *)this + 32LL) = PDEVOBJ::ulLogPixelsX((PDEVOBJ *)&v101);
  *(_DWORD *)(*(_QWORD *)this + 36LL) = PDEVOBJ::ulLogPixelsY((PDEVOBJ *)&v101);
  *(_DWORD *)(*(_QWORD *)this + 40LL) = a9;
  *(_DWORD *)(*(_QWORD *)this + 12LL) = a8 | PFEOBJ::flFontType((PFEOBJ *)&v95);
  *(_QWORD *)(*(_QWORD *)this + 48LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 56LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 4LL) = *((_DWORD *)a5 + 2);
  *(_QWORD *)(*(_QWORD *)this + 24LL) = *(_QWORD *)(v20 + 88);
  if ( (*(_DWORD *)(*(_QWORD *)this + 12LL) & 4) != 0 )
    v21 = *((unsigned int *)a5 + 20);
  else
    v21 = 0;
  *(_QWORD *)(*(_QWORD *)this + 16LL) = v21;
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
  v22 = a3[223];
  v23 = 0;
  v24 = *(_QWORD *)this;
  v94 = 0;
  *(_QWORD *)(v24 + 112) = v22;
  *(_DWORD *)(*(_QWORD *)this + 168LL) = 1;
  *(_DWORD *)(*(_QWORD *)this + 724LL) = *(_DWORD *)(*((_QWORD *)a5 + 4) + 48LL);
  *(_QWORD *)(*(_QWORD *)this + 472LL) = v17;
  v25 = *((_QWORD *)a5 + 4);
  v96[0] = *(_WORD *)(v25 + 116);
  RFONTOBJ::vXlatGlyphArray(this, v96, 1u, &v94, 2u, 0);
  *(_DWORD *)(*(_QWORD *)this + 456LL) = v94;
  *(_DWORD *)(*(_QWORD *)this + 720LL) &= ~0x40u;
  memset_0(&v104, 0, sizeof(v104));
  *(_QWORD *)(*(_QWORD *)this + 96LL) = *(_QWORD *)(v97 + 96);
  if ( !(unsigned int)RFONTOBJ::bGetDEVICEMETRICS(this, &v104) )
  {
    v26 = *(_QWORD *)this;
LABEL_9:
    memset(Str2, 0, sizeof(Str2));
    PushThreadGuardedObject(Str2, v26, Win32FreePool);
    RFONTOBJ::vDestroyFont(this, 1);
    PopThreadGuardedObject(Str2);
    FreeIsolatedType<NSInstrumentation::CTypeIsolation<237568,928>>(*(_QWORD *)this);
    *(_QWORD *)this = 0;
LABEL_106:
    v92 = 0;
    return *(unsigned int *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v95, v92);
  }
  *(POINTE *)(*(_QWORD *)this + 392LL) = v104.pteBase;
  *(POINTE *)(*(_QWORD *)this + 412LL) = v104.pteSide;
  v27 = *(_DWORD *)(*(_QWORD *)a2 + 352LL);
  v28 = *(_OWORD *)(*(_QWORD *)a2 + 336LL);
  v29 = *(_QWORD *)this;
  *(_OWORD *)(v29 + 172) = *(_OWORD *)(*(_QWORD *)a2 + 320LL);
  *(_OWORD *)(v29 + 188) = v28;
  *(_DWORD *)(v29 + 204) = v27;
  if ( !(unsigned int)RFONTOBJ::bCalcLayoutUnits(this, a2)
    || !(unsigned int)bGetNtoWScales(
                        (struct EPOINTFL *)(*(_QWORD *)this + 212LL),
                        a2,
                        (struct _FD_XFORM *)(*(_QWORD *)this + 356LL),
                        (struct PFEOBJ *)&v95,
                        (int *)(*(_QWORD *)this + 220LL)) )
  {
    v26 = *(_QWORD *)this;
    goto LABEL_9;
  }
  v94 = 0;
  bFToL(v30, &v94, 0);
  *(_DWORD *)(v31 + 320) = v94;
  v94 = 0;
  bFToL(v32, &v94, 0);
  *(_DWORD *)(v33 + 324) = v94;
  v94 = 0;
  bFToL(v34, &v94, 0);
  *(_DWORD *)(v35 + 328) = v94;
  v94 = 0;
  bFToL(v36, &v94, 0);
  *(_DWORD *)(v37 + 332) = v94;
  *(_DWORD *)(*(_QWORD *)this + 428LL) = -1;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 208LL) == 1 )
  {
    v38 = *(_DWORD *)(v25 + 48);
    if ( (v38 & 4) == 0 )
    {
      if ( (v38 & 0x10) == 0 )
      {
        v40 = ulSimpleDeviceOrientation(this);
LABEL_21:
        v44 = *(_QWORD *)this;
        *(_DWORD *)(*(_QWORD *)this + 388LL) = v40;
        goto LABEL_22;
      }
      v39 = (unsigned int)(3600 - a4->elfEnumLogfontEx.elfLogFont.lfEscapement);
LABEL_20:
      v40 = lNormAngle(v39);
      goto LABEL_21;
    }
LABEL_19:
    v39 = (unsigned int)(3600 - a4->elfEnumLogfontEx.elfLogFont.lfOrientation);
    goto LABEL_20;
  }
  *(_DWORD *)(*(_QWORD *)this + 388LL) = RFONTOBJ::ulSimpleOrientation(this, a2);
  v44 = 3600;
  if ( *(_DWORD *)(*(_QWORD *)this + 388LL) >= 0xE10u && (*(_DWORD *)(*(_QWORD *)this + 724LL) & 0x10) != 0 )
    goto LABEL_19;
LABEL_22:
  v45 = a10;
  *(_DWORD *)(*(_QWORD *)this + 664LL) = a10;
  v46 = *(_QWORD *)(*(_QWORD *)this + 96LL);
  v47 = *(_QWORD *)(*(_QWORD *)(W32GetSessionState(v44, v41, v42, v43) + 96) + 24136LL);
  if ( *(_QWORD *)(*(_QWORD *)this + 96LL) == v47 )
  {
    if ( (unsigned int)UmfdQueryFontCapsEx(*(_QWORD *)(*(_QWORD *)this + 24LL), v47, v99) != -1 )
      v23 = v100;
  }
  else
  {
    v50 = *(unsigned int (__fastcall **)(__int64, _BYTE *))(v46 + 3032);
    if ( v50 && v50(2, v99) != -1 )
      v23 = v100;
  }
  v51 = *(_QWORD *)this;
  if ( (*(_DWORD *)(v46 + 40) & 0x2000) != 0 )
  {
    v52 = *(_DWORD *)(v51 + 12) & 0x10010000;
    *(_DWORD *)(v51 + 92) = 0;
    v53 = v52 != 0 ? 400 : 800;
    *(_DWORD *)(*(_QWORD *)this + 88LL) = 1;
    v54 = *(_QWORD *)this;
    if ( a10 )
    {
      *(_DWORD *)(v54 + 88) = 2;
    }
    else
    {
      v55 = *(_QWORD *)(v54 + 104);
      if ( v55 )
      {
        v95 = (struct PFE *)v55;
        if ( (unsigned int)PDEVOBJ::bAllowDDICall((PDEVOBJ *)&v95) && *(_QWORD *)(v55 + 2976) )
        {
          v56 = *(_QWORD *)this;
          memset(Str2, 0, sizeof(Str2));
          PushThreadGuardedObject(Str2, v56, vRestartbRealizeFont);
          *(_DWORD *)(*(_QWORD *)this + 88LL) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v55 + 2976))(
                                                  *(_QWORD *)(*(_QWORD *)this + 112LL),
                                                  *(_QWORD *)this);
          PopThreadGuardedObject(Str2);
        }
        if ( (*(_DWORD *)(v55 + 1808) & 0x40000000) != 0 )
        {
          v57 = 3 * PDEVOBJ::ulLogPixelsY((PDEVOBJ *)&v95);
          if ( v57 <= 0x320 )
            v57 = v53;
          v53 = v57;
          if ( v57 > 0x960 )
            v53 = 2400;
        }
      }
    }
    v58 = *(_DWORD **)this;
    v51 = (unsigned int)(*(_DWORD *)(*(_QWORD *)this + 88LL) - 1);
    if ( *(_DWORD *)(*(_QWORD *)this + 88LL) == 1 )
    {
      v47 = (unsigned int)v58[85];
      if ( *(char *)(v25 + 52) < 0 )
      {
        v51 = (unsigned int)v58[88];
        if ( (unsigned int)v47 > 3 * (int)v51 )
        {
          v94 = v58[88];
          v59 = (const wchar_t *)(v25 + *(int *)(v25 + 16));
          wcscpy((wchar_t *)Str2, L"Cambria Math");
          if ( wcsncmp_0(v59, (const wchar_t *)Str2, 0xDu) )
          {
            if ( (unsigned int)dword_14039BA20 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14039BA20, 0x400000000000LL) )
            {
              v60 = *(_QWORD *)this;
              *(_DWORD *)v96 = *(_DWORD *)(*(_QWORD *)this + 352LL);
              v98 = *(_DWORD *)(v60 + 340);
              v61 = *(int *)(v25 + 16);
              LODWORD(v95) = v53;
              v103 = v25 + v61;
              v102 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v60,
                (unsigned int)byte_14036DCEB,
                v48,
                v49,
                (__int64)&v102,
                (__int64)&v103,
                (__int64)&v95,
                (__int64)&v98,
                (__int64)v96);
            }
            v58 = *(_DWORD **)this;
          }
          v47 = v94;
        }
      }
      if ( (v23 & 2) == 0 || (v58[181] & 0x8000) != 0 && (v58[84] > 2 * v53 || (unsigned int)v47 > v53) )
        v58[22] = 2;
    }
    else if ( *(_DWORD *)(*(_QWORD *)this + 88LL) == 2 && (v23 & 1) == 0 )
    {
      v58[22] = 1;
    }
    v45 = a10;
  }
  else
  {
    *(_DWORD *)(v51 + 92) = 1;
    *(_DWORD *)(*(_QWORD *)this + 88LL) = 0;
  }
  v62 = *(_QWORD *)(W32GetSessionState(v51, v47, v48, v49) + 96);
  if ( *(_DWORD *)(*(_QWORD *)this + 88LL) == 2 )
    *(_DWORD *)(*(_QWORD *)this + 12LL) &= 0x8FFEFFFF;
  v63 = *(_DWORD **)this;
  if ( v45 && v63[22] != 2 )
    goto LABEL_63;
  if ( !a11 || (v65 = 1, v63[97]) )
    v65 = 0;
  v63[162] = v65;
  inited = RFONTOBJ::bInitCache(this, a12);
  v70 = *(_QWORD *)this;
  if ( !inited )
  {
LABEL_63:
    v64 = *(_QWORD *)this;
    memset(Str2, 0, sizeof(Str2));
    PushThreadGuardedObject(Str2, v64, Win32FreePool);
    RFONTOBJ::vDestroyFont(this, 1);
    PopThreadGuardedObject(Str2);
    FreeIsolatedType<NSInstrumentation::CTypeIsolation<237568,928>>(*(_QWORD *)this);
    *(_QWORD *)this = 0;
    goto LABEL_106;
  }
  *(_QWORD *)(v70 + 696) = 0;
  v71 = *(_QWORD *)(W32GetSessionState(v70, v67, v68, v69) + 96);
  SEMOBJ<18>::SEMOBJ<18>(&v102, v71 + 4864);
  v72 = (*(_DWORD *)(v71 + 24024))++ == -1;
  v73 = *(_DWORD *)(v71 + 24024);
  if ( v72 )
  {
    *(_DWORD *)(v71 + 24024) = 1;
    v73 = 1;
  }
  **(_DWORD **)this = v73;
  *(_DWORD *)(*(_QWORD *)this + 668LL) = 1;
  v74 = PDEVOBJ::prfntActive((PDEVOBJ *)&v101);
  Flink = v74->Flink;
  if ( v74->Flink->Blink != v74 )
    goto LABEL_101;
  v76 = v97;
  v77 = (struct _LIST_ENTRY *)(*(_QWORD *)this + 672LL);
  v77->Flink = Flink;
  v77->Blink = v74;
  Flink->Blink = v77;
  v74->Flink = v77;
  v78 = (_QWORD *)(v76 + 72);
  v79 = *(_QWORD *)(v76 + 72);
  if ( *(_QWORD *)(v79 + 8) != v76 + 72 )
LABEL_101:
    __fastfail(3u);
  v80 = (_QWORD *)(*(_QWORD *)this + 488LL);
  v80[1] = v78;
  *v80 = v79;
  *(_QWORD *)(v79 + 8) = v80;
  *v78 = v80;
  SEMOBJ<18>::vUnlock(&v102);
  v81 = *(_DWORD *)(*(_QWORD *)this + 12LL) | 1;
  if ( *(_DWORD *)(*(_QWORD *)this + 88LL) != 1 )
    v81 = *(_DWORD *)(*(_QWORD *)this + 12LL) & 0xFFFFFFFE;
  *(_DWORD *)(*(_QWORD *)this + 12LL) = v81;
  *(_DWORD *)(*(_QWORD *)this + 208LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 208LL);
  v82 = *(_DWORD *)(v62 + 19552) && (*((_DWORD *)a5 + 3) & 0x10) != 0;
  *(_DWORD *)(*(_QWORD *)this + 716LL) = v82;
  v83 = *(_QWORD *)this;
  if ( (*(_DWORD *)(*(_QWORD *)this + 12LL) & 0x10000000) != 0 )
  {
    if ( (*(_BYTE *)(v83 + 204) & 1) == 0 || (v84 = 1, *(_DWORD *)(v83 + 320)) )
      v84 = 0;
    v85 = *(_QWORD *)(*(_QWORD *)(v83 + 120) + 32LL);
    if ( (*(_DWORD *)(v85 + 48) & 0x401000) != 0 && v84 && *(_WORD *)(v85 + 46) <= 0x190u )
    {
      v86 = (const wchar_t *)(v85 + *(int *)(v85 + 8));
      if ( !_wcsicmp(v86, L"Courier New")
        || !_wcsicmp(v86, L"Rod")
        || !_wcsicmp(v86, L"Rod Transparent")
        || !_wcsicmp(v86, L"Fixed Miriam Transparent")
        || !_wcsicmp(v86, L"Miriam Fixed")
        || !_wcsicmp(v86, L"Simplified Arabic Fixed") )
      {
        *(_DWORD *)(*(_QWORD *)this + 64LL) = 1;
      }
      v76 = v97;
    }
    v87 = *(_QWORD *)this;
    if ( (*(_DWORD *)(*(_QWORD *)this + 12LL) & 0x20000000) != 0 )
    {
      memset(Str2, 0, 24);
      EXFORMOBJ::vGetCoefficient((EXFORMOBJ *)(v87 + 224), (struct tagFLOATOBJ_XFORM *)Str2);
      v88 = *(_BYTE **)(v76 + 200);
      v89 = *(float *)&Str2[12] * (float)*(__int16 *)(v25 + 56);
      *(float *)&Str2[12] = v89;
      if ( v88 && (v90 = 0, *v88) )
      {
        while ( 1 )
        {
          v91 = &v88[80 * v90 + 4];
          if ( *v91 == (int)v89 )
            break;
          if ( ++v90 >= (unsigned int)(unsigned __int8)*v88 )
            goto LABEL_98;
        }
      }
      else
      {
LABEL_98:
        v91 = 0;
      }
      *(_QWORD *)(*(_QWORD *)this + 72LL) = v91;
    }
  }
  v92 = 1;
  return *(unsigned int *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v95, v92);
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
