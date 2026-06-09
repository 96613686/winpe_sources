# RFONTOBJ::bRealizeFont(XDCOBJ &,HDEV__ *,tagENUMLOGFONTEXDVW *,PFE *,_FD_XFORM *,_POINTL * const,ulong,ulong,int,int,ulong)

- ea: `0x140283d28`
- end: `0x14028493c`
- name: `?bRealizeFont@RFONTOBJ@@QEAAHAEAVXDCOBJ@@PEAUHDEV__@@PEAUtagENUMLOGFONTEXDVW@@PEAVPFE@@PEAU_FD_XFORM@@QEAU_POINTL@@KKHHK@Z`
- size: `3092`
- prototype: `__int64 __usercall@<rax>(RFONTOBJ *__hidden this@<rcx>, struct XDCOBJ *@<rdx>, HDEV@<r8>, struct tagENUMLOGFONTEXDVW *@<r9>, struct PFE *, struct _FD_XFORM *, struct _POINTL *const, unsigned int, unsigned int, int, int, unsigned int)`
- caller_count: `3`
- callee_count: `31`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003e3f0`
- `0x1400956b8`
- `0x140096868`

## callees

- `0x140001d04`
- `0x14003e1cc`
- `0x140043560`
- `0x1400435b0`
- `0x140048018`
- `0x140048338`
- `0x14005426c`
- `0x140056680`
- `0x1400577e8`
- `0x1400583d0`
- `0x1400954e4`
- `0x1400a03b8`
- `0x1400a0570`
- `0x1400a26ac`
- `0x140118550`
- `0x14017fd54`
- `0x14019da3c`
- `0x1401a7170`
- `0x1401ec328`
- `0x1401ff8e0`
- `0x1401ff98c`
- `0x140202bcc`
- `0x140233970`
- `0x1402416dc`
- `0x140250910`
- `0x14026a7c8`
- `0x140283d28`
- `0x140341fca`
- `0x140341ff0`
- `0x1403420d0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x1402847b3`
- `ntoskrnl!_wcsicmp` at `0x1402847d1`
- `ntoskrnl!_wcsicmp` at `0x1402847eb`
- `ntoskrnl!_wcsicmp` at `0x140284805`
- `ntoskrnl!_wcsicmp` at `0x14028481f`
- `ntoskrnl!_wcsicmp` at `0x140284839`
- `ntoskrnl!_wcsicmp` at `0x1402847b3`
- `ntoskrnl!_wcsicmp` at `0x1402847d1`
- `ntoskrnl!_wcsicmp` at `0x1402847eb`
- `ntoskrnl!_wcsicmp` at `0x140284805`
- `ntoskrnl!_wcsicmp` at `0x14028481f`
- `ntoskrnl!_wcsicmp` at `0x140284839`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140283d80`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140283d80`
- `win32kbase!PopThreadGuardedObject` at `0x14028401e`
- `win32kbase!PopThreadGuardedObject` at `0x140284397`
- `win32kbase!PopThreadGuardedObject` at `0x140284594`
- `win32kbase!PopThreadGuardedObject` at `0x14028461c`
- `win32kbase!PopThreadGuardedObject` at `0x14028401e`
- `win32kbase!PopThreadGuardedObject` at `0x140284397`
- `win32kbase!PopThreadGuardedObject` at `0x140284594`
- `win32kbase!PopThreadGuardedObject` at `0x14028461c`
- `win32kbase!PushThreadGuardedObject` at `0x140284001`
- `win32kbase!PushThreadGuardedObject` at `0x14028436b`
- `win32kbase!PushThreadGuardedObject` at `0x140284577`
- `win32kbase!PushThreadGuardedObject` at `0x1402845ff`
- `win32kbase!PushThreadGuardedObject` at `0x140284001`
- `win32kbase!PushThreadGuardedObject` at `0x14028436b`
- `win32kbase!PushThreadGuardedObject` at `0x140284577`
- `win32kbase!PushThreadGuardedObject` at `0x1402845ff`
- `win32kbase!lNormAngle` at `0x14028423c`
- `win32kbase!lNormAngle` at `0x14028423c`
- `win32kbase!?vGetCoefficient@EXFORMOBJ@@QEBAXPEAUtagFLOATOBJ_XFORM@@@Z` at `0x14028487d`
- `win32kbase!?vGetCoefficient@EXFORMOBJ@@QEBAXPEAUtagFLOATOBJ_XFORM@@@Z` at `0x14028487d`
- `win32kbase!Win32FreePool` at `0x140283feb`
- `win32kbase!Win32FreePool` at `0x14028455e`
- `win32kbase!Win32FreePool` at `0x1402845e6`
- `WIN32K!W32GetSessionState` at `0x140284267`
- `WIN32K!W32GetSessionState` at `0x140284531`
- `WIN32K!W32GetSessionState` at `0x14028463f`
- `WIN32K!W32GetSessionState` at `0x140284267`
- `WIN32K!W32GetSessionState` at `0x140284531`
- `WIN32K!W32GetSessionState` at `0x14028463f`

## string_xrefs

- `0x1402847a6`: `Courier New`

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
  __int64 v40; // rcx
  int v41; // esi
  __int64 v42; // rdi
  __int64 v43; // rdx
  unsigned int (__fastcall *v44)(__int64, _BYTE *); // rax
  __int64 v45; // rcx
  int v46; // eax
  unsigned int v47; // edi
  __int64 v48; // rsi
  __int64 v49; // rsi
  __int64 v50; // rdx
  unsigned int v51; // ecx
  _DWORD *v52; // rsi
  unsigned int v53; // edx
  const wchar_t *v54; // rcx
  int v55; // r8d
  int v56; // r9d
  __int64 v57; // rcx
  __int64 v58; // rax
  __int64 v59; // r14
  _DWORD *v60; // rax
  __int64 v61; // rdx
  int v62; // ecx
  int inited; // eax
  __int64 v64; // rcx
  __int64 v65; // rdi
  bool v66; // zf
  int v67; // ecx
  struct _LIST_ENTRY *v68; // rax
  struct _LIST_ENTRY *Flink; // rdx
  __int64 v70; // rdi
  struct _LIST_ENTRY *v71; // rcx
  _QWORD *v72; // rcx
  __int64 v73; // rdx
  _QWORD *v74; // rax
  unsigned int v75; // edx
  BOOL v76; // ecx
  __int64 v77; // rcx
  char v78; // dl
  __int64 v79; // rcx
  const wchar_t *v80; // rdi
  __int64 v81; // rcx
  _BYTE *v82; // r9
  float v83; // xmm1_4
  int v84; // edx
  unsigned __int8 *v85; // r8
  __int64 v86; // rdx
  unsigned int v88; // [rsp+50h] [rbp-B0h] BYREF
  struct PFE *v89; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v90[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v91; // [rsp+68h] [rbp-98h]
  int v92; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v93[4]; // [rsp+78h] [rbp-88h] BYREF
  int v94; // [rsp+7Ch] [rbp-84h]
  _QWORD *v95; // [rsp+80h] [rbp-80h] BYREF
  __int64 v96; // [rsp+88h] [rbp-78h] BYREF
  __int64 v97; // [rsp+90h] [rbp-70h] BYREF
  _FD_DEVICEMETRICS v98; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE Str2[32]; // [rsp+120h] [rbp+20h] BYREF

  v89 = a5;
  v17 = PFEOBJ::pfdg((PFEOBJ *)&v89);
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
    PFEOBJ::vFreepfdg((PFEOBJ *)&v89);
LABEL_105:
    *(_QWORD *)this = 0;
    goto LABEL_106;
  }
  v91 = *(_QWORD *)a5;
  v19 = v91;
  v95 = a3;
  *(_DWORD *)(*(_QWORD *)this + 32LL) = PDEVOBJ::ulLogPixelsX((PDEVOBJ *)&v95);
  *(_DWORD *)(*(_QWORD *)this + 36LL) = PDEVOBJ::ulLogPixelsY((PDEVOBJ *)&v95);
  *(_DWORD *)(*(_QWORD *)this + 40LL) = a9;
  *(_DWORD *)(*(_QWORD *)this + 12LL) = a8 | PFEOBJ::flFontType((PFEOBJ *)&v89);
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
  v88 = 0;
  *(_QWORD *)(v23 + 112) = v21;
  *(_DWORD *)(*(_QWORD *)this + 168LL) = 1;
  *(_DWORD *)(*(_QWORD *)this + 724LL) = *(_DWORD *)(*((_QWORD *)a5 + 4) + 48LL);
  *(_QWORD *)(*(_QWORD *)this + 472LL) = v17;
  v24 = *((_QWORD *)a5 + 4);
  v90[0] = *(_WORD *)(v24 + 116);
  RFONTOBJ::vXlatGlyphArray(this, v90, 1u, &v88, 2u, 0);
  *(_DWORD *)(*(_QWORD *)this + 456LL) = v88;
  *(_DWORD *)(*(_QWORD *)this + 720LL) &= ~0x40u;
  memset_0(&v98, 0, sizeof(v98));
  *(_QWORD *)(*(_QWORD *)this + 96LL) = *(_QWORD *)(v91 + 96);
  if ( !(unsigned int)RFONTOBJ::bGetDEVICEMETRICS(this, &v98) )
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
    v86 = 0;
    return *(unsigned int *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v89, v86);
  }
  *(POINTE *)(*(_QWORD *)this + 392LL) = v98.pteBase;
  *(POINTE *)(*(_QWORD *)this + 412LL) = v98.pteSide;
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
                        (struct PFEOBJ *)&v89,
                        (int *)(*(_QWORD *)this + 220LL)) )
  {
    v25 = *(_QWORD *)this;
    goto LABEL_9;
  }
  v88 = 0;
  bFToL(v29, &v88, 0);
  *(_DWORD *)(v30 + 320) = v88;
  v88 = 0;
  bFToL(v31, &v88, 0);
  *(_DWORD *)(v32 + 324) = v88;
  v88 = 0;
  bFToL(v33, &v88, 0);
  *(_DWORD *)(v34 + 328) = v88;
  v88 = 0;
  bFToL(v35, &v88, 0);
  *(_DWORD *)(v36 + 332) = v88;
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
        v40 = *(_QWORD *)this;
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
  v40 = 3600;
  if ( *(_DWORD *)(*(_QWORD *)this + 388LL) >= 0xE10u && (*(_DWORD *)(*(_QWORD *)this + 724LL) & 0x10) != 0 )
    goto LABEL_19;
LABEL_22:
  v41 = a10;
  *(_DWORD *)(*(_QWORD *)this + 664LL) = a10;
  v42 = *(_QWORD *)(*(_QWORD *)this + 96LL);
  v43 = *(_QWORD *)(*(_QWORD *)(W32GetSessionState(v40) + 96) + 24136LL);
  if ( *(_QWORD *)(*(_QWORD *)this + 96LL) == v43 )
  {
    if ( (unsigned int)UmfdQueryFontCapsEx(*(_QWORD *)(*(_QWORD *)this + 24LL), v43, v93) != -1 )
      v22 = v94;
  }
  else
  {
    v44 = *(unsigned int (__fastcall **)(__int64, _BYTE *))(v42 + 3032);
    if ( v44 && v44(2, v93) != -1 )
      v22 = v94;
  }
  v45 = *(_QWORD *)this;
  if ( (*(_DWORD *)(v42 + 40) & 0x2000) != 0 )
  {
    v46 = *(_DWORD *)(v45 + 12) & 0x10010000;
    *(_DWORD *)(v45 + 92) = 0;
    v47 = v46 != 0 ? 400 : 800;
    *(_DWORD *)(*(_QWORD *)this + 88LL) = 1;
    v48 = *(_QWORD *)this;
    if ( a10 )
    {
      *(_DWORD *)(v48 + 88) = 2;
    }
    else
    {
      v49 = *(_QWORD *)(v48 + 104);
      if ( v49 )
      {
        v89 = (struct PFE *)v49;
        if ( (unsigned int)PDEVOBJ::bAllowDDICall((PDEVOBJ *)&v89) && *(_QWORD *)(v49 + 2976) )
        {
          v50 = *(_QWORD *)this;
          memset(Str2, 0, sizeof(Str2));
          PushThreadGuardedObject(Str2, v50, vRestartbRealizeFont);
          *(_DWORD *)(*(_QWORD *)this + 88LL) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v49 + 2976))(
                                                  *(_QWORD *)(*(_QWORD *)this + 112LL),
                                                  *(_QWORD *)this);
          PopThreadGuardedObject(Str2);
        }
        if ( (*(_DWORD *)(v49 + 1808) & 0x40000000) != 0 )
        {
          v51 = 3 * PDEVOBJ::ulLogPixelsY((PDEVOBJ *)&v89);
          if ( v51 <= 0x320 )
            v51 = v47;
          v47 = v51;
          if ( v51 > 0x960 )
            v47 = 2400;
        }
      }
    }
    v52 = *(_DWORD **)this;
    v45 = (unsigned int)(*(_DWORD *)(*(_QWORD *)this + 88LL) - 1);
    if ( *(_DWORD *)(*(_QWORD *)this + 88LL) == 1 )
    {
      v53 = v52[85];
      if ( *(char *)(v24 + 52) < 0 )
      {
        v45 = (unsigned int)v52[88];
        if ( v53 > 3 * (int)v45 )
        {
          v88 = v52[88];
          v54 = (const wchar_t *)(v24 + *(int *)(v24 + 16));
          wcscpy((wchar_t *)Str2, L"Cambria Math");
          if ( wcsncmp_0(v54, (const wchar_t *)Str2, 0xDu) )
          {
            if ( (unsigned int)dword_14039AA20 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14039AA20, 0x400000000000LL) )
            {
              v57 = *(_QWORD *)this;
              *(_DWORD *)v90 = *(_DWORD *)(*(_QWORD *)this + 352LL);
              v92 = *(_DWORD *)(v57 + 340);
              v58 = *(int *)(v24 + 16);
              LODWORD(v89) = v47;
              v97 = v24 + v58;
              v96 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v57,
                (unsigned int)byte_14036CD6B,
                v55,
                v56,
                (__int64)&v96,
                (__int64)&v97,
                (__int64)&v89,
                (__int64)&v92,
                (__int64)v90);
            }
            v52 = *(_DWORD **)this;
          }
          v53 = v88;
        }
      }
      if ( (v22 & 2) == 0 || (v52[181] & 0x8000) != 0 && (v52[84] > 2 * v47 || v53 > v47) )
        v52[22] = 2;
    }
    else if ( *(_DWORD *)(*(_QWORD *)this + 88LL) == 2 && (v22 & 1) == 0 )
    {
      v52[22] = 1;
    }
    v41 = a10;
  }
  else
  {
    *(_DWORD *)(v45 + 92) = 1;
    *(_DWORD *)(*(_QWORD *)this + 88LL) = 0;
  }
  v59 = *(_QWORD *)(W32GetSessionState(v45) + 96);
  if ( *(_DWORD *)(*(_QWORD *)this + 88LL) == 2 )
    *(_DWORD *)(*(_QWORD *)this + 12LL) &= 0x8FFEFFFF;
  v60 = *(_DWORD **)this;
  if ( v41 && v60[22] != 2 )
    goto LABEL_63;
  if ( !a11 || (v62 = 1, v60[97]) )
    v62 = 0;
  v60[162] = v62;
  inited = RFONTOBJ::bInitCache(this, a12);
  v64 = *(_QWORD *)this;
  if ( !inited )
  {
LABEL_63:
    v61 = *(_QWORD *)this;
    memset(Str2, 0, sizeof(Str2));
    PushThreadGuardedObject(Str2, v61, Win32FreePool);
    RFONTOBJ::vDestroyFont(this, 1);
    PopThreadGuardedObject(Str2);
    FreeIsolatedType<NSInstrumentation::CTypeIsolation<237568,928>>(*(_QWORD *)this);
    *(_QWORD *)this = 0;
    goto LABEL_106;
  }
  *(_QWORD *)(v64 + 696) = 0;
  v65 = *(_QWORD *)(W32GetSessionState(v64) + 96);
  SEMOBJ<18>::SEMOBJ<18>(&v96, v65 + 4864);
  v66 = (*(_DWORD *)(v65 + 24024))++ == -1;
  v67 = *(_DWORD *)(v65 + 24024);
  if ( v66 )
  {
    *(_DWORD *)(v65 + 24024) = 1;
    v67 = 1;
  }
  **(_DWORD **)this = v67;
  *(_DWORD *)(*(_QWORD *)this + 668LL) = 1;
  v68 = PDEVOBJ::prfntActive((PDEVOBJ *)&v95);
  Flink = v68->Flink;
  if ( v68->Flink->Blink != v68 )
    goto LABEL_101;
  v70 = v91;
  v71 = (struct _LIST_ENTRY *)(*(_QWORD *)this + 672LL);
  v71->Flink = Flink;
  v71->Blink = v68;
  Flink->Blink = v71;
  v68->Flink = v71;
  v72 = (_QWORD *)(v70 + 72);
  v73 = *(_QWORD *)(v70 + 72);
  if ( *(_QWORD *)(v73 + 8) != v70 + 72 )
LABEL_101:
    __fastfail(3u);
  v74 = (_QWORD *)(*(_QWORD *)this + 488LL);
  v74[1] = v72;
  *v74 = v73;
  *(_QWORD *)(v73 + 8) = v74;
  *v72 = v74;
  SEMOBJ<18>::vUnlock(&v96);
  v75 = *(_DWORD *)(*(_QWORD *)this + 12LL) | 1;
  if ( *(_DWORD *)(*(_QWORD *)this + 88LL) != 1 )
    v75 = *(_DWORD *)(*(_QWORD *)this + 12LL) & 0xFFFFFFFE;
  *(_DWORD *)(*(_QWORD *)this + 12LL) = v75;
  *(_DWORD *)(*(_QWORD *)this + 208LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 976LL) + 208LL);
  v76 = *(_DWORD *)(v59 + 19552) && (*((_DWORD *)a5 + 3) & 0x10) != 0;
  *(_DWORD *)(*(_QWORD *)this + 716LL) = v76;
  v77 = *(_QWORD *)this;
  if ( (*(_DWORD *)(*(_QWORD *)this + 12LL) & 0x10000000) != 0 )
  {
    if ( (*(_BYTE *)(v77 + 204) & 1) == 0 || (v78 = 1, *(_DWORD *)(v77 + 320)) )
      v78 = 0;
    v79 = *(_QWORD *)(*(_QWORD *)(v77 + 120) + 32LL);
    if ( (*(_DWORD *)(v79 + 48) & 0x401000) != 0 && v78 && *(_WORD *)(v79 + 46) <= 0x190u )
    {
      v80 = (const wchar_t *)(v79 + *(int *)(v79 + 8));
      if ( !_wcsicmp(v80, L"Courier New")
        || !_wcsicmp(v80, L"Rod")
        || !_wcsicmp(v80, L"Rod Transparent")
        || !_wcsicmp(v80, L"Fixed Miriam Transparent")
        || !_wcsicmp(v80, L"Miriam Fixed")
        || !_wcsicmp(v80, L"Simplified Arabic Fixed") )
      {
        *(_DWORD *)(*(_QWORD *)this + 64LL) = 1;
      }
      v70 = v91;
    }
    v81 = *(_QWORD *)this;
    if ( (*(_DWORD *)(*(_QWORD *)this + 12LL) & 0x20000000) != 0 )
    {
      memset(Str2, 0, 24);
      EXFORMOBJ::vGetCoefficient((EXFORMOBJ *)(v81 + 224), (struct tagFLOATOBJ_XFORM *)Str2);
      v82 = *(_BYTE **)(v70 + 200);
      v83 = *(float *)&Str2[12] * (float)*(__int16 *)(v24 + 56);
      *(float *)&Str2[12] = v83;
      if ( v82 && (v84 = 0, *v82) )
      {
        while ( 1 )
        {
          v85 = &v82[80 * v84 + 4];
          if ( *v85 == (int)v83 )
            break;
          if ( ++v84 >= (unsigned int)(unsigned __int8)*v82 )
            goto LABEL_98;
        }
      }
      else
      {
LABEL_98:
        v85 = 0;
      }
      *(_QWORD *)(*(_QWORD *)this + 72LL) = v85;
    }
  }
  v86 = 1;
  return *(unsigned int *)ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v89, v86);
}

```

## disassembly

```asm
0x140283d28  push    rbp
0x140283d2a  push    rbx
0x140283d2b  push    rsi
0x140283d2c  push    rdi
0x140283d2d  push    r12
0x140283d2f  push    r13
0x140283d31  push    r14
0x140283d33  push    r15
0x140283d35  lea     rbp, [rsp-58h]
0x140283d3a  sub     rsp, 158h
0x140283d41  mov     rax, cs:__security_cookie
0x140283d48  xor     rax, rsp
0x140283d4b  mov     [rbp+90h+var_50], rax
0x140283d4f  mov     r12, [rbp+90h+arg_20]
0x140283d56  mov     rbx, rcx
0x140283d59  lea     rcx, [rsp+190h+var_138]; this
0x140283d5e  mov     [rsp+190h+var_138], r12
0x140283d63  mov     rdi, r9
0x140283d66  mov     r14, r8
0x140283d69  mov     r13, rdx
0x140283d6c  call    ?pfdg@PFEOBJ@@QEAAPEAU_FD_GLYPHSET@@XZ; PFEOBJ::pfdg(void)
0x140283d71  xor     r15d, r15d
0x140283d74  mov     rsi, rax
0x140283d77  test    rax, rax
0x140283d7a  jz      loc_14028490A
0x140283d80  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140283d87  nop     dword ptr [rax+rax+00h]
0x140283d8c  mov     rcx, [rax+1120h]
0x140283d93  mov     rcx, [rcx+28h]
0x140283d97  test    rcx, rcx
0x140283d9a  jz      loc_1402848FD
0x140283da0  call    ?Allocate@?$CTypeIsolation@$0DKAAA@$0DKA@@NSInstrumentation@@IEAAPEAXXZ; NSInstrumentation::CTypeIsolation<237568,928>::Allocate(void)
0x140283da5  mov     [rbx], rax
0x140283da8  test    rax, rax
0x140283dab  jz      loc_140284900
0x140283db1  mov     r15, [r12]
0x140283db5  lea     rcx, [rbp+90h+var_110]; this
0x140283db9  mov     [rsp+190h+var_128], r15
0x140283dbe  mov     [rbp+90h+var_110], r14
0x140283dc2  call    ?ulLogPixelsX@PDEVOBJ@@QEBAKXZ; PDEVOBJ::ulLogPixelsX(void)
0x140283dc7  mov     rcx, [rbx]
0x140283dca  mov     [rcx+20h], eax
0x140283dcd  lea     rcx, [rbp+90h+var_110]; this
0x140283dd1  call    ?ulLogPixelsY@PDEVOBJ@@QEBAKXZ; PDEVOBJ::ulLogPixelsY(void)
0x140283dd6  mov     rcx, [rbx]
0x140283dd9  mov     [rcx+24h], eax
0x140283ddc  mov     rcx, [rbx]
0x140283ddf  mov     eax, [rbp+90h+arg_40]
0x140283de5  mov     [rcx+28h], eax
0x140283de8  lea     rcx, [rsp+190h+var_138]; this
0x140283ded  call    ?flFontType@PFEOBJ@@QEAAKXZ; PFEOBJ::flFontType(void)
0x140283df2  or      eax, [rbp+90h+arg_38]
0x140283df8  mov     rcx, [rbx]
0x140283dfb  mov     [rcx+0Ch], eax
0x140283dfe  mov     rax, [rbx]
0x140283e01  mov     qword ptr [rax+30h], 0
0x140283e09  mov     rax, [rbx]
0x140283e0c  mov     qword ptr [rax+38h], 0
0x140283e14  mov     rcx, [rbx]
0x140283e17  mov     eax, [r12+8]
0x140283e1c  mov     [rcx+4], eax
0x140283e1f  mov     rcx, [rbx]
0x140283e22  mov     rax, [r15+58h]
0x140283e26  mov     [rcx+18h], rax
0x140283e2a  mov     rcx, [rbx]
0x140283e2d  mov     eax, [rcx+0Ch]
0x140283e30  test    al, 4
0x140283e32  jz      short loc_140283E3B
0x140283e34  mov     eax, [r12+50h]
0x140283e39  jmp     short loc_140283E3D
0x140283e3b  xor     eax, eax
0x140283e3d  mov     [rcx+10h], rax
0x140283e41  xor     r8d, r8d; unsigned int
0x140283e44  mov     rax, [rbx]
0x140283e47  mov     rcx, [rbp+90h+arg_28]
0x140283e4e  movups  xmm0, xmmword ptr [rcx]
0x140283e51  movdqu  xmmword ptr [rax+88h], xmm0
0x140283e59  mov     rax, [rbx]
0x140283e5c  movups  xmm1, xmmword ptr [rcx]
0x140283e5f  movdqu  xmmword ptr [rax+98h], xmm1
0x140283e67  mov     rax, [rbx]
0x140283e6a  movups  xmm0, xmmword ptr [rcx]
0x140283e6d  movdqu  xmmword ptr [rax+164h], xmm0
0x140283e75  mov     rdx, [rbx]
0x140283e78  mov     rax, [rbp+90h+arg_30]
0x140283e7f  mov     rcx, [rax]
0x140283e82  mov     [rdx+290h], rcx
0x140283e89  mov     rcx, [rbx]
0x140283e8c  lea     rdx, [rcx+0E8h]; struct MATRIX *
0x140283e93  add     rcx, 0E0h; this
0x140283e9a  call    ?vInit@EXFORMOBJ@@QEAAXPEAUMATRIX@@K@Z; EXFORMOBJ::vInit(MATRIX *,ulong)
0x140283e9f  mov     rdx, [rbx]
0x140283ea2  mov     rcx, rbx; this
0x140283ea5  add     rdx, 0E0h; struct EXFORMOBJ *
0x140283eac  call    ?vSetNotionalToDevice@RFONTOBJ@@QEAAXAEAVEXFORMOBJ@@@Z; RFONTOBJ::vSetNotionalToDevice(EXFORMOBJ &)
0x140283eb1  mov     rax, [rbx]
0x140283eb4  lea     r9, [rsp+190h+var_140]; unsigned int *
0x140283eb9  mov     edx, 1
0x140283ebe  mov     r8d, edx; unsigned int
0x140283ec1  mov     [rax+78h], r12
0x140283ec5  mov     rcx, [rbx]
0x140283ec8  mov     rax, [r12]
0x140283ecc  mov     [rcx+80h], rax
0x140283ed3  xor     ecx, ecx
0x140283ed5  mov     rax, [rbx]
0x140283ed8  mov     [rax+2D8h], rcx
0x140283edf  mov     rax, [rbx]
0x140283ee2  mov     [rax+2E0h], rcx
0x140283ee9  mov     rax, [rbx]
0x140283eec  mov     [rax+2E8h], rcx
0x140283ef3  mov     rax, [rbx]
0x140283ef6  mov     [rax+2F0h], rcx
0x140283efd  mov     rax, [rbx]
0x140283f00  mov     [rax+348h], ecx
0x140283f06  mov     rax, [rbx]
0x140283f09  mov     [rax+2D0h], ecx
0x140283f0f  mov     rax, [rbx]
0x140283f12  mov     [rax+350h], ecx
0x140283f18  mov     rax, [rbx]
0x140283f1b  mov     [rax+34Ch], ecx
0x140283f21  mov     ecx, [r12+0Ch]
0x140283f26  mov     rax, [rbx]
0x140283f29  and     ecx, 100h
0x140283f2f  mov     [rax+354h], ecx
0x140283f35  mov     rax, [rbx]
0x140283f38  mov     [rax+68h], r14
0x140283f3c  mov     rax, [r14+6F8h]
0x140283f43  xor     r14d, r14d
0x140283f46  mov     rcx, [rbx]
0x140283f49  mov     [rsp+190h+var_168], r14d; int
0x140283f4e  mov     [rsp+190h+var_140], r14d
0x140283f53  mov     dword ptr [rsp+190h+var_170], 2; unsigned int
0x140283f5b  mov     [rcx+70h], rax
0x140283f5f  mov     rax, [rbx]
0x140283f62  mov     [rax+0A8h], edx
0x140283f68  lea     rdx, [rsp+190h+var_130]; unsigned __int16 *
0x140283f6d  mov     rax, [r12+20h]
0x140283f72  mov     rcx, [rbx]
0x140283f75  mov     eax, [rax+30h]
0x140283f78  mov     [rcx+2D4h], eax
0x140283f7e  mov     rcx, rbx; this
0x140283f81  mov     rax, [rbx]
0x140283f84  mov     [rax+1D8h], rsi
0x140283f8b  mov     r15, [r12+20h]
0x140283f90  movzx   eax, word ptr [r15+74h]
0x140283f95  mov     [rsp+190h+var_130], ax
0x140283f9a  call    ?vXlatGlyphArray@RFONTOBJ@@QEAAXPEBGIPEAKKH@Z; RFONTOBJ::vXlatGlyphArray(ushort const *,uint,ulong *,ulong,int)
0x140283f9f  mov     rcx, [rbx]
0x140283fa2  mov     eax, [rsp+190h+var_140]
0x140283fa6  mov     [rcx+1C8h], eax
0x140283fac  mov     rax, [rbx]
0x140283faf  and     dword ptr [rax+2D0h], 0FFFFFFBFh
0x140283fb6  xor     edx, edx; Val
0x140283fb8  lea     r8d, [r14+7Ch]; Size
0x140283fbc  lea     rcx, [rbp+90h+var_F0]; void *
0x140283fc0  call    memset_0
0x140283fc5  mov     rcx, [rbx]
0x140283fc8  lea     rdx, [rbp+90h+var_F0]; struct _FD_DEVICEMETRICS *
0x140283fcc  mov     rax, [rsp+190h+var_128]
0x140283fd1  mov     rax, [rax+60h]
0x140283fd5  mov     [rcx+60h], rax
0x140283fd9  mov     rcx, rbx; this
0x140283fdc  call    ?bGetDEVICEMETRICS@RFONTOBJ@@QEAAHPEAU_FD_DEVICEMETRICS@@@Z; RFONTOBJ::bGetDEVICEMETRICS(_FD_DEVICEMETRICS *)
0x140283fe1  mov     rcx, [rbx]
0x140283fe4  test    eax, eax
0x140283fe6  jnz     short loc_14028403A
0x140283fe8  mov     rdx, rcx
0x140283feb  mov     r8, cs:__imp_Win32FreePool
0x140283ff2  lea     rcx, [rbp+90h+Str2]
0x140283ff6  xorps   xmm0, xmm0
0x140283ff9  movups  [rbp+90h+var_60], xmm0
0x140283ffd  movups  xmmword ptr [rbp+90h+Str2], xmm0
0x140284001  call    cs:__imp_PushThreadGuardedObject
0x140284008  nop     dword ptr [rax+rax+00h]
0x14028400d  mov     edx, 1; int
0x140284012  mov     rcx, rbx; this
0x140284015  call    ?vDestroyFont@RFONTOBJ@@QEAAXH@Z; RFONTOBJ::vDestroyFont(int)
0x14028401a  lea     rcx, [rbp+90h+Str2]
0x14028401e  call    cs:__imp_PopThreadGuardedObject
0x140284025  nop     dword ptr [rax+rax+00h]
0x14028402a  mov     rcx, [rbx]
0x14028402d  call    ??$FreeIsolatedType@V?$CTypeIsolation@$0DKAAA@$0DKA@@NSInstrumentation@@@@YAXPEAX@Z; FreeIsolatedType<NSInstrumentation::CTypeIsolation<237568,928>>(void *)
0x140284032  mov     [rbx], r14
0x140284035  jmp     loc_14028490D
0x14028403a  movss   xmm0, [rbp+90h+var_F0.pteBase.x]
0x14028403f  mov     rdx, r13; struct XDCOBJ *
0x140284042  movss   dword ptr [rcx+188h], xmm0
0x14028404a  mov     rax, [rbx]
0x14028404d  movss   xmm1, [rbp+90h+var_F0.pteBase.y]
0x140284052  movss   dword ptr [rax+18Ch], xmm1
0x14028405a  mov     rax, [rbx]
0x14028405d  movss   xmm0, [rbp+90h+var_F0.pteSide.x]
0x140284062  movss   dword ptr [rax+19Ch], xmm0
0x14028406a  mov     rax, [rbx]
0x14028406d  movss   xmm1, [rbp+90h+var_F0.pteSide.y]
0x140284072  movss   dword ptr [rax+1A0h], xmm1
0x14028407a  mov     rax, [r13+0]
0x14028407e  mov     ecx, [rax+160h]
0x140284084  movups  xmm0, xmmword ptr [rax+140h]
0x14028408b  movups  xmm1, xmmword ptr [rax+150h]
0x140284092  mov     rax, [rbx]
0x140284095  movups  xmmword ptr [rax+0ACh], xmm0
0x14028409c  movups  xmmword ptr [rax+0BCh], xmm1
0x1402840a3  mov     [rax+0CCh], ecx
0x1402840a9  mov     rcx, rbx; this
0x1402840ac  call    ?bCalcLayoutUnits@RFONTOBJ@@QEAAHAEAVXDCOBJ@@@Z; RFONTOBJ::bCalcLayoutUnits(XDCOBJ &)
0x1402840b1  test    eax, eax
0x1402840b3  jz      loc_1402848F5
0x1402840b9  mov     rcx, [rbx]
0x1402840bc  lea     r9, [rsp+190h+var_138]; struct PFEOBJ *
0x1402840c1  mov     rdx, r13; struct XDCOBJ *
0x1402840c4  lea     rax, [rcx+0DCh]
0x1402840cb  lea     r8, [rcx+164h]; struct _FD_XFORM *
0x1402840d2  mov     [rsp+190h+var_170], rax; int *
0x1402840d7  add     rcx, 0D4h; struct EPOINTFL *
0x1402840de  call    ?bGetNtoWScales@@YAHPEAVEPOINTFL@@AEAVXDCOBJ@@PEAU_FD_XFORM@@AEAVPFEOBJ@@PEAH@Z; bGetNtoWScales(EPOINTFL *,XDCOBJ &,_FD_XFORM *,PFEOBJ &,int *)
0x1402840e3  test    eax, eax
0x1402840e5  jz      loc_1402848F5
0x1402840eb  mov     r11, [rbx]
0x1402840ee  lea     rdx, [rsp+190h+var_140]
0x1402840f3  xor     r8d, r8d
0x1402840f6  mov     [rsp+190h+var_140], r14d
0x1402840fb  movd    xmm0, dword ptr [r11+134h]
0x140284104  cvtdq2ps xmm0, xmm0
0x140284107  mulss   xmm0, dword ptr [r11+19Ch]
0x140284110  call    bFToL
0x140284115  mov     r8d, [rsp+190h+var_140]
0x14028411a  lea     rdx, [rsp+190h+var_140]
0x14028411f  mov     [r11+140h], r8d
0x140284126  xor     r8d, r8d
0x140284129  mov     r11, [rbx]
0x14028412c  mov     [rsp+190h+var_140], r14d
0x140284131  movd    xmm0, dword ptr [r11+134h]
0x14028413a  cvtdq2ps xmm0, xmm0
0x14028413d  mulss   xmm0, dword ptr [r11+1A0h]
0x140284146  call    bFToL
0x14028414b  mov     r8d, [rsp+190h+var_140]
0x140284150  lea     rdx, [rsp+190h+var_140]
0x140284155  mov     [r11+144h], r8d
0x14028415c  xor     r8d, r8d
0x14028415f  mov     r11, [rbx]
0x140284162  mov     [rsp+190h+var_140], r14d
0x140284167  movd    xmm0, dword ptr [r11+138h]
0x140284170  cvtdq2ps xmm0, xmm0
0x140284173  mulss   xmm0, dword ptr [r11+19Ch]
0x14028417c  call    bFToL
0x140284181  mov     r8d, [rsp+190h+var_140]
0x140284186  lea     rdx, [rsp+190h+var_140]
0x14028418b  mov     [r11+148h], r8d
0x140284192  xor     r8d, r8d
0x140284195  mov     r11, [rbx]
0x140284198  mov     [rsp+190h+var_140], r14d
0x14028419d  movd    xmm0, dword ptr [r11+138h]
0x1402841a6  cvtdq2ps xmm0, xmm0
0x1402841a9  mulss   xmm0, dword ptr [r11+1A0h]
0x1402841b2  call    bFToL
0x1402841b7  mov     r8d, [rsp+190h+var_140]
0x1402841bc  mov     [r11+14Ch], r8d
0x1402841c3  mov     rax, [rbx]
0x1402841c6  mov     dword ptr [rax+1ACh], 0FFFFFFFFh
0x1402841d0  mov     rax, [r13+0]
0x1402841d4  mov     rcx, [rax+3D0h]
0x1402841db  cmp     dword ptr [rcx+0D0h], 1
0x1402841e2  jnz     short loc_14028420B
0x1402841e4  mov     eax, [r15+30h]
0x1402841e8  test    al, 4
0x1402841ea  jz      short loc_1402841F3
0x1402841ec  mov     ecx, 0E10h
0x1402841f1  jmp     short loc_140284239
0x1402841f3  test    al, 10h
0x1402841f5  jz      short loc_140284201
0x1402841f7  mov     ecx, 0E10h
0x1402841fc  sub     ecx, [rdi+8]
0x1402841ff  jmp     short loc_14028423C
0x140284201  mov     rcx, rbx; struct RFONTOBJ *
0x140284204  call    ?ulSimpleDeviceOrientation@@YAKAEAVRFONTOBJ@@@Z; ulSimpleDeviceOrientation(RFONTOBJ &)
0x140284209  jmp     short loc_140284248
0x14028420b  mov     rdx, r13; struct XDCOBJ *
0x14028420e  mov     rcx, rbx; this
0x140284211  call    ?ulSimpleOrientation@RFONTOBJ@@QEAAKAEAVXDCOBJ@@@Z; RFONTOBJ::ulSimpleOrientation(XDCOBJ &)
0x140284216  mov     rcx, [rbx]
0x140284219  mov     [rcx+184h], eax
0x14028421f  mov     ecx, 0E10h
0x140284224  mov     rax, [rbx]
0x140284227  cmp     [rax+184h], ecx
0x14028422d  jb      short loc_140284251
0x14028422f  mov     eax, [rax+2D4h]
0x140284235  test    al, 10h
0x140284237  jz      short loc_140284251
0x140284239  sub     ecx, [rdi+0Ch]
0x14028423c  call    cs:__imp_lNormAngle
0x140284243  nop     dword ptr [rax+rax+00h]
0x140284248  mov     rcx, [rbx]
0x14028424b  mov     [rcx+184h], eax
0x140284251  mov     rax, [rbx]
0x140284254  mov     esi, [rbp+90h+arg_48]
0x14028425a  mov     [rax+298h], esi
0x140284260  mov     rax, [rbx]
0x140284263  mov     rdi, [rax+60h]
0x140284267  call    cs:__imp_W32GetSessionState
  ... truncated ...
```
