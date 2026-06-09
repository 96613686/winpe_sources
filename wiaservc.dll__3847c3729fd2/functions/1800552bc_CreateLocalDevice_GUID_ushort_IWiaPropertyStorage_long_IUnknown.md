# CreateLocalDevice(_GUID,ushort *,IWiaPropertyStorage *,long,IUnknown * *)

- ea: `0x1800552bc`
- end: `0x180056a9e`
- name: `?CreateLocalDevice@@YAJU_GUID@@PEAGPEAUIWiaPropertyStorage@@JPEAPEAUIUnknown@@@Z`
- size: `6114`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int16 *, struct IWiaPropertyStorage *, int, struct IUnknown **)`
- caller_count: `1`
- callee_count: `49`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002d6e4`

## callees

- `0x180004a7c`
- `0x18000a974`
- `0x18000a9e0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x18000f808`
- `0x18000fbec`
- `0x180010d78`
- `0x180011a64`
- `0x180011a94`
- `0x1800174c4`
- `0x18001750c`
- `0x18001901c`
- `0x180019eac`
- `0x180023288`
- `0x180027590`
- `0x1800284dc`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180032764`
- `0x180033884`
- `0x180033cc0`
- `0x180039b40`
- `0x18004ba9c`
- `0x180055200`
- `0x1800552bc`
- `0x18005de14`
- `0x18005eb7c`
- `0x180060520`
- `0x180060e70`
- `0x180063434`
- `0x180063688`
- `0x1800649a0`
- `0x180064a6c`
- `0x180064fc0`
- `0x1800655b0`
- `0x1800656e0`
- `0x180076b8c`
- `0x180076bc8`
- `0x180077040`
- `0x1800775fc`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800554e9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800554e9`
- `OLEAUT32!__imp_SysAllocString` at `0x180055535`
- `OLEAUT32!__imp_SysAllocString` at `0x18005643d`
- `OLEAUT32!__imp_SysAllocString` at `0x180055535`
- `OLEAUT32!__imp_SysAllocString` at `0x18005643d`
- `OLEAUT32!__imp_SysFreeString` at `0x180055d52`
- `OLEAUT32!__imp_SysFreeString` at `0x18005642d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800567b3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800567be`
- `OLEAUT32!__imp_SysFreeString` at `0x180055d52`
- `OLEAUT32!__imp_SysFreeString` at `0x18005642d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800567b3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800567be`
- `OLEAUT32!__imp_SysStringLen` at `0x1800553e8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800553e8`
- `ole32!PropVariantClear` at `0x180055f7a`
- `ole32!PropVariantClear` at `0x180056006`
- `ole32!PropVariantClear` at `0x180056071`
- `ole32!PropVariantClear` at `0x180055f7a`
- `ole32!PropVariantClear` at `0x180056006`
- `ole32!PropVariantClear` at `0x180056071`

## string_xrefs

- `0x180055327`: `CreateLocalDevice`
- `0x180055b8c`: `CreateLocalDevice`
- `0x180055bb9`: `CreateLocalDevice`
- `0x180055bd1`: `CreateLocalDevice`
- `0x180055316`: `::CreateLocalDevice`
- `0x180055de4`: `unable to initialize D-AIT  (0x%X), compatibility mode disabled`
- `0x180055e08`: `unable to initialize D-AIT  (0x%X), compatibility mode disabled`
- `0x180055c51`: `CreateLocalDevice driver provided optional inner component`
- `0x180055c77`: `CreateLocalDevice driver provided optional inner component`
- `0x18005611c`: `Compatibility Mode: detected LH D-AIT feeder = %u, flatbed = %u`
- `0x18005614d`: `Compatibility Mode: detected LH D-AIT feeder = %u, flatbed = %u`
- `0x18005617f`: `Cannot detect compatible LH D-AIT items (0x%X), compatibility mode disabled`
- `0x1800561a3`: `Cannot detect compatible LH D-AIT items (0x%X), compatibility mode disabled`
- `0x180055e7f`: `detected an incompatible number of XP D-AIT child item(s) (%u), compatibility mode disabled`
- `0x180055ea4`: `detected an incompatible number of XP D-AIT child item(s) (%u), compatibility mode disabled`
- `0x180055ec4`: `cannot detect compatible XP D-AIT item(s) (0x%X), compatibility mode disabled`
- `0x180055ee8`: `cannot detect compatible XP D-AIT item(s) (0x%X), compatibility mode disabled`
- `0x180056347`: `cannot initialize A-AIT root item (0x%X), compatibility mode disabled`
- `0x18005636b`: `cannot initialize A-AIT root item (0x%X), compatibility mode disabled`
- `0x1800563d4`: `read item name from root D-AIT item failed (0x%X)`
- `0x1800563f8`: `read item name from root D-AIT item failed (0x%X)`
- `0x1800561f0`: `Incompatible D-AIT items, compatibility mode disabled`
- `0x180056212`: `Incompatible D-AIT items, compatibility mode disabled`
- `0x1800562b1`: `cannot get the IWiaPropertyStorage interface for A-AIT, compatibility mode disabled`
- `0x1800562d3`: `cannot get the IWiaPropertyStorage interface for A-AIT, compatibility mode disabled`
- `0x180056534`: `read item flags from root D-AIT failed (0x%X)`
- `0x180056558`: `read item flags from root D-AIT failed (0x%X)`
- `0x18005658a`: `unable to get a valid CWiaDrvItem* for the root D-AIT to copy item name and flags (0x%X)`
- `0x1800565ae`: `unable to get a valid CWiaDrvItem* for the root D-AIT to copy item name and flags (0x%X)`
- `0x180056461`: `copy full item name for root A-AIT failed (0x%X)`
- `0x180056485`: `copy full item name for root A-AIT failed (0x%X)`
- `0x1800564cc`: `read full item name from root D-AIT item failed (0x%X)`
- `0x1800564f0`: `read full item name from root D-AIT item failed (0x%X)`
- `0x18005674a`: `cannot initialize A-AIT root item properties (0x%X), compatibility mode disabled`
- `0x18005676e`: `cannot initialize A-AIT root item properties (0x%X), compatibility mode disabled`
- `0x1800565f3`: `InitManagedItemProperties on A-AIT root failed (0x%X)`
- `0x180056617`: `InitManagedItemProperties on A-AIT root failed (0x%X)`
- `0x180056653`: `cannot initialize WIA_DIP_ props for the A-AIT root (0x%X), compatibility mode disabled`
- `0x180056677`: `cannot initialize WIA_DIP_ props for the A-AIT root (0x%X), compatibility mode disabled`
- `0x180056970`: `CreateLocalDevice failed, cannot enter compatibility mode`
- `0x180056992`: `CreateLocalDevice failed, cannot enter compatibility mode`
- `0x1800567c6`: `cannot allocate memory for A-AIT, compatibility mode disabled`
- `0x1800567e8`: `cannot allocate memory for A-AIT, compatibility mode disabled`
- `0x1800568c2`: `failed to create one A-AIT child item, compatibility mode disabled`
- `0x1800568e4`: `failed to create one A-AIT child item, compatibility mode disabled`

## pseudocode

```c
__int64 __fastcall CreateLocalDevice(
        struct _GUID *a1,
        unsigned __int16 *a2,
        struct IWiaPropertyStorage *a3,
        unsigned int a4,
        struct IUnknown **a5)
{
  struct tagWiaTraceData_Type *v6; // rax
  char *v7; // rdx
  unsigned int v8; // r8d
  struct USDWrapper *USDWrapperFromDeviceList; // r13
  CWiaItem *v10; // r12
  signed int inited; // esi
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  char *v23; // rbx
  void *v24; // rdx
  void **v25; // rax
  void *v26; // rdx
  __int64 v27; // rcx
  BSTR v28; // rbx
  wchar_t *v29; // rax
  const unsigned __int16 *v30; // rax
  unsigned int v31; // r11d
  char *v32; // rbx
  void *v33; // rdx
  void **v34; // rax
  void *v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rcx
  char *v38; // rbx
  void *v39; // rdx
  void **v40; // rax
  void *v41; // rdx
  __int64 v42; // rcx
  _QWORD *v43; // rbx
  _DWORD *v44; // rbx
  char *v45; // rbx
  void *v46; // rdx
  void **v47; // rax
  void *v48; // rdx
  __int64 v49; // rcx
  CWiaItem *v50; // rax
  char *v51; // rbx
  void *v52; // rdx
  void **v53; // rax
  void *v54; // rdx
  __int64 v55; // rcx
  StiLockMgr *v56; // rbx
  char *v57; // rbx
  void *v58; // rdx
  void **v59; // rax
  void *v60; // rdx
  __int64 v61; // rcx
  StiLockMgr *v62; // rcx
  int v63; // r9d
  unsigned int v64; // r8d
  char *v65; // rbx
  void *v66; // rdx
  void **v67; // rax
  void *v68; // rdx
  __int64 v69; // rcx
  char *v70; // rbx
  void *v71; // rdx
  void **v72; // rax
  void *v73; // rdx
  __int64 v74; // rcx
  int v75; // r8d
  char *v76; // rbx
  void *v77; // rdx
  void **v78; // rax
  void *v79; // rdx
  __int64 v80; // rcx
  char *v81; // rbx
  void *v82; // rdx
  void **v83; // rax
  void *v84; // rdx
  __int64 v85; // rcx
  char *v86; // rbx
  void *v87; // rdx
  StiLockMgr *v88; // rbx
  char *v89; // rcx
  struct IUnknown *v90; // rax
  char *v91; // rbx
  void *v92; // rdx
  void **v93; // rax
  void *v94; // rdx
  __int64 v95; // rcx
  char *v96; // rbx
  void *v97; // rdx
  void **v98; // rax
  void *v99; // rdx
  __int64 v100; // rcx
  unsigned int v101; // edx
  unsigned int v102; // ebx
  char *v103; // rbx
  void *v104; // rdx
  void **v105; // rax
  void *v106; // rdx
  __int64 v107; // rcx
  int v108; // r13d
  char *v109; // rbx
  void *v110; // rdx
  void **v111; // rax
  void *v112; // rdx
  __int64 v113; // rcx
  char *v114; // rbx
  void *v115; // rdx
  void **v116; // rax
  void *v117; // rdx
  __int64 v118; // rcx
  char v119; // r13
  int v120; // ebx
  int v121; // r13d
  int v122; // ebx
  struct tagPROPVARIANT *v123; // r9
  bool Property; // bl
  int *v125; // r9
  char v126; // cl
  int v127; // r13d
  char *v128; // rbx
  void *v129; // rdx
  void **v130; // rax
  void *v131; // rdx
  __int64 v132; // rcx
  int v133; // eax
  int v134; // edx
  char *v135; // rbx
  void *v136; // rdx
  void **v137; // rax
  void *v138; // rdx
  __int64 v139; // rcx
  char *v140; // rbx
  void *v141; // rdx
  void **v142; // rax
  void *v143; // rdx
  __int64 v144; // rcx
  CWiaItem *v145; // r13
  CWiaItem *v146; // rax
  char *v147; // rbx
  void *v148; // rdx
  void **v149; // rax
  void *v150; // rdx
  __int64 v151; // rcx
  char *v152; // rbx
  void *v153; // rdx
  void **v154; // rax
  void *v155; // rdx
  __int64 v156; // rcx
  int v157; // edx
  char *v158; // rbx
  void *v159; // rdx
  void **v160; // rax
  void *v161; // rdx
  __int64 v162; // rcx
  const OLECHAR *v163; // rbx
  OLECHAR *v164; // rcx
  BSTR v165; // rax
  char *v166; // rbx
  void *v167; // rdx
  void **v168; // rax
  void *v169; // rdx
  __int64 v170; // rcx
  void *v171; // rbx
  char *v172; // rbx
  void *v173; // rdx
  void **v174; // rax
  void *v175; // rdx
  __int64 v176; // rcx
  char *v177; // rbx
  void *v178; // rdx
  void **v179; // rax
  void *v180; // rdx
  __int64 v181; // rcx
  char *v182; // rbx
  void *v183; // rdx
  void **v184; // rax
  void *v185; // rdx
  __int64 v186; // rcx
  char *v187; // rbx
  void *v188; // rdx
  void **v189; // rax
  void *v190; // rdx
  __int64 v191; // rcx
  char *v192; // rbx
  void *v193; // rdx
  void **v194; // rax
  void *v195; // rdx
  __int64 v196; // rcx
  int v197; // ebx
  char *v198; // rbx
  void *v199; // rdx
  void **v200; // rax
  void *v201; // rdx
  __int64 v202; // rcx
  int v203; // eax
  char *v204; // rbx
  void *v205; // rdx
  void **v206; // rax
  void *v207; // rdx
  __int64 v208; // rcx
  char *v209; // rbx
  void *v210; // rdx
  void **v211; // rax
  void *v212; // rdx
  __int64 v213; // rcx
  signed int v214; // eax
  char *v215; // rbx
  void *v216; // rdx
  void **v217; // rax
  void *v218; // rdx
  __int64 v219; // rcx
  unsigned int v220; // edx
  char *v221; // rbx
  void *v222; // rdx
  void **v223; // rax
  void *v224; // rdx
  __int64 v225; // rcx
  int v226; // r15d
  int IsLegacyDriver; // eax
  int v228; // ebx
  unsigned int lpMem; // [rsp+20h] [rbp-428h]
  int v231; // [rsp+60h] [rbp-3E8h] BYREF
  unsigned int v232; // [rsp+64h] [rbp-3E4h] BYREF
  BSTR v233; // [rsp+68h] [rbp-3E0h] BYREF
  __int64 v234; // [rsp+70h] [rbp-3D8h] BYREF
  BSTR pbstr; // [rsp+78h] [rbp-3D0h]
  BSTR bstrString; // [rsp+80h] [rbp-3C8h] BYREF
  BSTR v237; // [rsp+88h] [rbp-3C0h] BYREF
  int v238; // [rsp+90h] [rbp-3B8h]
  void *Buf1[2]; // [rsp+98h] [rbp-3B0h] BYREF
  __int64 v240; // [rsp+A8h] [rbp-3A0h]
  struct IUnknown **v241; // [rsp+B0h] [rbp-398h]
  struct CWiaDrvItem *v242; // [rsp+B8h] [rbp-390h] BYREF
  struct USDWrapper *v243; // [rsp+C0h] [rbp-388h]
  struct IWiaPropertyStorage *v244; // [rsp+C8h] [rbp-380h] BYREF
  __int64 v245; // [rsp+D0h] [rbp-378h]
  struct IUnknown *v246; // [rsp+D8h] [rbp-370h] BYREF
  __int64 (__fastcall ***v247)(_QWORD, GUID *, __int64 *); // [rsp+E0h] [rbp-368h] BYREF
  StiLockMgr *v248; // [rsp+E8h] [rbp-360h]
  struct IWiaPropertyStorage *v249; // [rsp+F0h] [rbp-358h]
  PROPVARIANT pvar[2]; // [rsp+F8h] [rbp-350h] BYREF
  __int64 v251; // [rsp+108h] [rbp-340h]
  _BYTE v252[80]; // [rsp+110h] [rbp-338h] BYREF
  struct IUnknown v253; // [rsp+160h] [rbp-2E8h] BYREF
  __int64 v254; // [rsp+270h] [rbp-1D8h]
  _QWORD v255[38]; // [rsp+290h] [rbp-1B8h] BYREF
  OLECHAR psz[32]; // [rsp+3C0h] [rbp-88h] BYREF

  v232 = a4;
  v249 = a3;
  pbstr = a2;
  Buf1[0] = a1;
  v244 = a3;
  v241 = a5;
  v6 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::CreateLocalDevice");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v252, v7, v8, "CreateLocalDevice", lpMem, v6);
  USDWrapperFromDeviceList = 0;
  v243 = 0;
  v247 = 0;
  v10 = 0;
  v237 = 0;
  v246 = 0;
  v242 = 0;
  v248 = 0;
  v231 = 0;
  LODWORD(v233) = 0;
  bstrString = 0;
  if ( !a3 || (inited = 0, !a5) )
  {
    v12 = (char *)WiaTrace_TraceLog("Invalid argument");
    WriteDbgTraceErrorWI("CreateLocalDevice", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_Trace("Invalid argument");
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"CreateLocalDevice", 1, v14);
    inited = -2147024809;
  }
  if ( !SysStringLen(pbstr) )
  {
    v17 = (char *)WiaTrace_TraceLog("Invalid argument");
    WriteDbgTraceErrorWI("CreateLocalDevice", v17);
    WiaTrcLib::Free((WiaTrcLib *)v17, v18);
    v19 = (void **)WiaTrace_Trace("Invalid argument");
    WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"CreateLocalDevice", 1, v19);
    inited = -2147024809;
  }
  if ( inited >= 0 )
  {
    *v241 = 0;
    v22 = memcmp_0(Buf1[0], &CLSID_WiaDevMgr, 0x10u);
    v231 = v22 == 0;
    LODWORD(v233) = v231;
    if ( v22 && memcmp_0(Buf1[0], &CLSID_WiaDevMgr2, 0x10u) )
    {
      v23 = (char *)WiaTrace_TraceLog("bad GUID");
      WriteDbgTraceErrorWI("CreateLocalDevice", v23);
      WiaTrcLib::Free((WiaTrcLib *)v23, v24);
      v25 = (void **)WiaTrace_Trace("bad GUID");
      WiaTrace_ProcessTrace_Ex(v27, v26, (void *)"CreateLocalDevice", 1, v25);
      inited = -2147024809;
    }
    if ( inited >= 0 )
    {
      v28 = pbstr;
      v29 = wcsstr(pbstr, L"}\\");
      if ( v29 )
        v30 = v29 + 2;
      else
        v30 = pbstr;
      StringCchCopyW(psz, 0x20u, v30);
      StringCchCatW(psz, v31, L"\\Root");
      bstrString = SysAllocString(psz);
      if ( bstrString )
        goto LABEL_17;
      v32 = (char *)WiaTrace_TraceLog("unable to allocate property stream device name");
      WriteDbgTraceErrorWI("CreateLocalDevice", v32);
      WiaTrcLib::Free((WiaTrcLib *)v32, v33);
      v34 = (void **)WiaTrace_Trace("unable to allocate property stream device name");
      WiaTrace_ProcessTrace_Ex(v36, v35, (void *)"CreateLocalDevice", 1, v34);
      inited = -2147024882;
    }
  }
  v28 = pbstr;
LABEL_17:
  if ( inited < 0 )
    goto LABEL_28;
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v255, v28);
  USDWrapperFromDeviceList = (struct USDWrapper *)GetUSDWrapperFromDeviceList(v37, v255);
  v243 = USDWrapperFromDeviceList;
  v255[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v255);
  v255[34] = 0;
  if ( !USDWrapperFromDeviceList )
  {
    v38 = (char *)WiaTrace_TraceLog("unable to find active STI USD device object");
    WriteDbgTraceErrorWI("CreateLocalDevice", v38);
    WiaTrcLib::Free((WiaTrcLib *)v38, v39);
    v40 = (void **)WiaTrace_Trace("unable to find active STI USD device object");
    WiaTrace_ProcessTrace_Ex(v42, v41, (void *)"CreateLocalDevice", 1, v40);
    inited = -2145320939;
  }
  if ( inited < 0 )
  {
LABEL_28:
    v43 = 0;
  }
  else
  {
    (*(void (__fastcall **)(struct USDWrapper *, __int64))(*(_QWORD *)USDWrapperFromDeviceList + 104LL))(
      USDWrapperFromDeviceList,
      2);
    v43 = (_QWORD *)(*(__int64 (__fastcall **)(struct USDWrapper *))(*(_QWORD *)USDWrapperFromDeviceList + 200LL))(USDWrapperFromDeviceList);
    Buf1[0] = v43;
    if ( !v43 )
    {
      Buf1[0] = *(void **)(*(_QWORD *)USDWrapperFromDeviceList + 192LL);
      v44 = operator new(0x18u);
      if ( v44 )
      {
        *(_QWORD *)v44 = &FakeStiDevice::`vftable';
        v44[2] = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl);
        *((_QWORD *)v44 + 2) = 0;
      }
      else
      {
        v44 = 0;
      }
      ((void (__fastcall *)(struct USDWrapper *, _DWORD *))Buf1[0])(USDWrapperFromDeviceList, v44);
      v43 = (_QWORD *)(*(__int64 (__fastcall **)(struct USDWrapper *))(*(_QWORD *)USDWrapperFromDeviceList + 200LL))(USDWrapperFromDeviceList);
      Buf1[0] = v43;
    }
    if ( !v43 )
    {
      v45 = (char *)WiaTrace_TraceLog("unable to allocate fake device");
      WriteDbgTraceErrorWI("CreateLocalDevice", v45);
      WiaTrcLib::Free((WiaTrcLib *)v45, v46);
      v47 = (void **)WiaTrace_Trace("unable to allocate fake device");
      WiaTrace_ProcessTrace_Ex(v49, v48, (void *)"CreateLocalDevice", 1, v47);
      inited = -2147024882;
      v43 = Buf1[0];
    }
  }
  if ( inited >= 0 )
  {
    v43[2] = USDWrapperFromDeviceList;
    if ( USDWrapperFromDeviceList
      && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl) )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v43[2] + 8LL))(v43[2]);
    }
    inited = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD))*v43)(v43, &IID_IStiDevice, &v247);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl) )
      (*(void (__fastcall **)(_QWORD *))(*v43 + 16LL))(v43);
    if ( inited >= 0 )
    {
      v50 = (CWiaItem *)operator new(0x130u);
      if ( v50 )
        v10 = CWiaItem::CWiaItem(v50);
      v237 = (BSTR)v10;
      if ( !v10 )
      {
        v51 = (char *)WiaTrace_TraceLog("unable to allocate root item");
        WriteDbgTraceErrorWI("CreateLocalDevice", v51);
        WiaTrcLib::Free((WiaTrcLib *)v51, v52);
        v53 = (void **)WiaTrace_Trace("unable to allocate root item");
        WiaTrace_ProcessTrace_Ex(v55, v54, (void *)"CreateLocalDevice", 1, v53);
        inited = -2147024882;
      }
      if ( inited >= 0 )
      {
        inited = (**(__int64 (__fastcall ***)(CWiaItem *, GUID *, struct IUnknown **))v10)(v10, &IID_IUnknown, v241);
        if ( inited >= 0 )
        {
          ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)Buf1);
          CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v253, L"StiLockMgr");
          v56 = (StiLockMgr *)ServiceComponentHolder::Get<StiLockMgr>(Buf1, &v253);
          v248 = v56;
          v253.lpVtbl = (struct IUnknownVtbl *)&CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(&v253);
          v254 = 0;
          if ( !v56 )
          {
            v57 = (char *)WiaTrace_TraceLog("The Lock Manager is NULL - we cannot call IWiaMiniDrv::drvInitializeWia on (%ws)");
            WriteDbgTraceErrorWI("CreateLocalDevice", v57);
            WiaTrcLib::Free((WiaTrcLib *)v57, v58);
            v59 = (void **)WiaTrace_Trace(
                             "The Lock Manager is NULL - we cannot call IWiaMiniDrv::drvInitializeWia on (%ws)",
                             pbstr);
            WiaTrace_ProcessTrace_Ex(v61, v60, (void *)"CreateLocalDevice", 1, v59);
            inited = -2147418113;
          }
          ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)Buf1);
          if ( inited >= 0 )
          {
            v64 = *((_DWORD *)USDWrapperFromDeviceList + 1014) ? -1 : 100;
            inited = StiLockMgr::RequestLock(v62, USDWrapperFromDeviceList, v64, v63, 0);
            if ( inited >= 0 )
            {
              v234 = 0;
              inited = (**v247)(v247, &IID_IUnknown, &v234);
              v238 = inited;
              if ( inited < 0 )
              {
                v86 = (char *)WiaTrace_TraceLog("Unable to get IID_IUnknown from fake sti device, WIA_drvInitializeWia wi"
                                                "ll not be called");
                WriteDbgTraceErrorWI("CreateLocalDevice", v86);
                WiaTrcLib::Free((WiaTrcLib *)v86, v87);
                v78 = (void **)WiaTrace_Trace(
                                 "Unable to get IID_IUnknown from fake sti device, WIA_drvInitializeWia will not be called");
              }
              else
              {
                *((_DWORD *)v10 + 32) = 1;
                v65 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "=> drvInitializeWia <=");
                WriteDbgTraceInfoWI("CreateLocalDevice", v65);
                WiaTrcLib::Free((WiaTrcLib *)v65, v66);
                v67 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "=> drvInitializeWia <=");
                WiaTrace_ProcessTrace_Ex(v69, v68, (void *)"CreateLocalDevice", 4, v67);
                inited = (*(__int64 (__fastcall **)(struct USDWrapper *, struct IUnknown *, _QWORD, BSTR, BSTR, __int64, struct IUnknown *, struct CWiaDrvItem **, struct IUnknown **, __int64))(*(_QWORD *)USDWrapperFromDeviceList + 344LL))(
                           USDWrapperFromDeviceList,
                           *v241,
                           v232,
                           pbstr,
                           bstrString,
                           v234,
                           *v241,
                           &v242,
                           &v246,
                           (__int64)v10 + 160);
                v238 = inited;
                v70 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "=> Returned from drvInitializeWia <=");
                WriteDbgTraceInfoWI("CreateLocalDevice", v70);
                WiaTrcLib::Free((WiaTrcLib *)v70, v71);
                v72 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "=> Returned from drvInitializeWia <=");
                WiaTrace_ProcessTrace_Ex(v74, v73, (void *)"CreateLocalDevice", 4, v72);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v234 + 16LL))(v234);
                v234 = 0;
                if ( inited >= 0 )
                {
                  if ( !v242 )
                  {
                    v81 = (char *)WiaTrace_TraceLog("WIA_drvInitializeWia succeeded but driver root item is null!");
                    WriteDbgTraceErrorWI("CreateLocalDevice", v81);
                    WiaTrcLib::Free((WiaTrcLib *)v81, v82);
                    v83 = (void **)WiaTrace_Trace("WIA_drvInitializeWia succeeded but driver root item is null!");
                    WiaTrace_ProcessTrace_Ex(v85, v84, (void *)"CreateLocalDevice", 1, v83);
                    inited = -2147467259;
                    v238 = -2147467259;
                  }
                  goto LABEL_56;
                }
                v76 = (char *)WiaTrace_TraceLog("WIA_drvInitializeWia failed with hr (0x%08X)");
                WriteDbgTraceErrorWI("CreateLocalDevice", v76);
                WiaTrcLib::Free((WiaTrcLib *)v76, v77);
                v78 = (void **)WiaTrace_Trace("WIA_drvInitializeWia failed with hr (0x%08X)", inited);
              }
              WiaTrace_ProcessTrace_Ex(v80, v79, (void *)"CreateLocalDevice", 1, v78);
LABEL_56:
              *((_DWORD *)v10 + 32) = 0;
              v88 = v248;
              StiLockMgr::RequestUnlock(v248, USDWrapperFromDeviceList, v75);
              v89 = (char *)v88 + *(int *)(*((_QWORD *)v88 + 1) + 4LL) + 8;
              (*(void (__fastcall **)(char *))(*(_QWORD *)v89 + 16LL))(v89);
              if ( inited >= 0 )
              {
                v90 = v246;
                if ( v246 )
                {
                  v91 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                                  0,
                                  0,
                                  "CreateLocalDevice driver provided optional inner component");
                  WriteDbgTraceInfoWI("CreateLocalDevice", v91);
                  WiaTrcLib::Free((WiaTrcLib *)v91, v92);
                  v93 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                                   0,
                                   0,
                                   "CreateLocalDevice driver provided optional inner component");
                  WiaTrace_ProcessTrace_Ex(v95, v94, (void *)"CreateLocalDevice", 4, v93);
                  v90 = v246;
                }
                inited = CWiaItem::InitializeWiaItem(v10, 0, v231 == 0, v10, v249, USDWrapperFromDeviceList, v242, v90);
                if ( inited < 0 )
                {
                  v96 = (char *)WiaTrace_TraceLog("Initialize of root item failed (%#x)");
                  WriteDbgTraceErrorWI("CreateLocalDevice", v96);
                  WiaTrcLib::Free((WiaTrcLib *)v96, v97);
                  v98 = (void **)WiaTrace_Trace("Initialize of root item failed (%#x)", inited);
                  WiaTrace_ProcessTrace_Ex(v100, v99, (void *)"CreateLocalDevice", 1, v98);
                  if ( v10 )
                    CWiaItem::`scalar deleting destructor'(v10, v101);
                  v10 = 0;
                }
                if ( inited >= 0 )
                  (*(void (__fastcall **)(struct USDWrapper *))(*(_QWORD *)USDWrapperFromDeviceList + 8LL))(USDWrapperFromDeviceList);
              }
            }
          }
        }
      }
    }
  }
  SysFreeString(bstrString);
  if ( inited < 0 )
    goto LABEL_190;
  if ( v10 )
  {
    if ( *((_DWORD *)v10 + 56) == 1 || !(unsigned int)CWiaItem::IsLegacyDriver(v10) )
    {
      v102 = 0;
      LODWORD(v234) = 0;
      if ( *((_DWORD *)v10 + 56) == 1 )
      {
        if ( !(unsigned int)CWiaItem::IsLegacyDriver(v10) )
          v102 = 2;
        LODWORD(v234) = v102;
      }
    }
    else
    {
      v102 = 1;
      LODWORD(v234) = 1;
    }
    CWiaItem::SetCompatMode(v10, v102);
    if ( v102 )
    {
      inited = CWiaItem::InitLazyProps(v10);
      if ( inited < 0 )
      {
        v103 = (char *)WiaTrace_TraceLog("unable to initialize D-AIT  (0x%X), compatibility mode disabled");
        WriteDbgTraceErrorWI("CreateLocalDevice", v103);
        WiaTrcLib::Free((WiaTrcLib *)v103, v104);
        v105 = (void **)WiaTrace_Trace("unable to initialize D-AIT  (0x%X), compatibility mode disabled", inited);
        WiaTrace_ProcessTrace_Ex(v107, v106, (void *)"CreateLocalDevice", 1, v105);
        v102 = 0;
        LODWORD(v234) = 0;
        CWiaItem::SetCompatMode(v10, 0);
      }
      else
      {
        inited = CWiaItem::ChildrenInitLazyProps(v10);
      }
    }
    v232 = 0;
    v231 = 0;
    LODWORD(pbstr) = 0;
    LODWORD(v233) = 0;
    if ( v102 )
    {
      if ( v102 == 1 )
      {
        LODWORD(v233) = 0;
        inited = CWiaItem::DetectCompatXPChild(v10, (unsigned int *)&v233);
        if ( inited < 0 )
        {
          v114 = (char *)WiaTrace_TraceLog("cannot detect compatible XP D-AIT item(s) (0x%X), compatibility mode disabled");
          WriteDbgTraceErrorWI("CreateLocalDevice", v114);
          WiaTrcLib::Free((WiaTrcLib *)v114, v115);
          v116 = (void **)WiaTrace_Trace(
                            "cannot detect compatible XP D-AIT item(s) (0x%X), compatibility mode disabled",
                            inited);
          WiaTrace_ProcessTrace_Ex(v118, v117, (void *)"CreateLocalDevice", 1, v116);
          LODWORD(v234) = 0;
        }
        else
        {
          v108 = (int)v233;
          if ( (_DWORD)v233 == 1 )
            goto LABEL_85;
          v109 = (char *)WiaTrace_TraceLog("detected an incompatible number of XP D-AIT child item(s) (%u), compatibility mode disabled");
          WriteDbgTraceErrorWI("CreateLocalDevice", v109);
          WiaTrcLib::Free((WiaTrcLib *)v109, v110);
          v111 = (void **)WiaTrace_Trace(
                            "detected an incompatible number of XP D-AIT child item(s) (%u), compatibility mode disabled",
                            v108);
          WiaTrace_ProcessTrace_Ex(v113, v112, (void *)"CreateLocalDevice", 1, v111);
        }
        CWiaItem::SetCompatMode(v10, 0);
LABEL_85:
        *(_OWORD *)Buf1 = 0;
        v240 = 0;
        LODWORD(v244) = 1;
        v245 = 3086;
        if ( (*(int (__fastcall **)(__int64, __int64, struct IWiaPropertyStorage **, void **))(*((_QWORD *)v10 + 1)
                                                                                             + 24LL))(
               (__int64)v10 + 8,
               1,
               &v244,
               Buf1) < 0 )
        {
          v120 = 0;
          LODWORD(pbstr) = 0;
        }
        else
        {
          v119 = (char)Buf1[1];
          PropVariantClear(Buf1);
          v120 = v119 & 1;
          LODWORD(pbstr) = v120;
          if ( (v119 & 1) != 0 )
          {
            v121 = v119 & 2;
LABEL_90:
            if ( v120 )
            {
              *(_OWORD *)Buf1 = 0;
              v240 = 0;
              LODWORD(v244) = 1;
              LODWORD(v245) = 3088;
              if ( (*(int (__fastcall **)(__int64, __int64, struct IWiaPropertyStorage **, void **))(*((_QWORD *)v10 + 1) + 24LL))(
                     (__int64)v10 + 8,
                     1,
                     &v244,
                     Buf1) >= 0 )
              {
                v122 = v121;
              }
              else
              {
                LODWORD(pbstr) = 0;
                v121 = 1;
                v122 = 1;
              }
              PropVariantClear(Buf1);
            }
            else
            {
              v122 = v121;
            }
            if ( !v122 )
            {
              *(_OWORD *)pvar = 0;
              v251 = 0;
              PropStorageHelpers::CPropertyId::CPropertyId((PropStorageHelpers::CPropertyId *)&v253, 0xC03u);
              Property = PropStorageHelpers::GetProperty(
                           v10,
                           &v253,
                           (const struct PropStorageHelpers::CPropertyId *)pvar,
                           v123);
              PropStorageHelpers::CPropertyId::~CPropertyId((PropStorageHelpers::CPropertyId *)&v253);
              if ( Property )
                v121 = 1;
              PropVariantClear(pvar);
            }
            LODWORD(v233) = 0;
            PropStorageHelpers::CPropertyId::CPropertyId((PropStorageHelpers::CPropertyId *)&v253, 0xC10u);
            PropStorageHelpers::GetPropertyFlags(
              v10,
              &v253,
              (const struct PropStorageHelpers::CPropertyId *)&v233,
              v125);
            PropStorageHelpers::CPropertyId::~CPropertyId((PropStorageHelpers::CPropertyId *)&v253);
            v126 = (char)v233;
            if ( !(_DWORD)v233 )
              v126 = 2;
            v232 = (v126 & 2) != 0 ? v121 : 0;
            v102 = v234;
            if ( (v126 & 1) == 0 )
              LODWORD(pbstr) = 0;
            goto LABEL_111;
          }
        }
        v121 = 1;
        goto LABEL_90;
      }
      inited = CWiaItem::DetectCompatLHChildren(v10, &v231, (int *)&v233);
      if ( inited < 0 )
      {
        v135 = (char *)WiaTrace_TraceLog("Cannot detect compatible LH D-AIT items (0x%X), compatibility mode disabled");
        WriteDbgTraceErrorWI("CreateLocalDevice", v135);
        WiaTrcLib::Free((WiaTrcLib *)v135, v136);
        v137 = (void **)WiaTrace_Trace(
                          "Cannot detect compatible LH D-AIT items (0x%X), compatibility mode disabled",
                          inited);
        WiaTrace_ProcessTrace_Ex(v139, v138, (void *)"CreateLocalDevice", 1, v137);
        v102 = 0;
        LODWORD(v234) = 0;
        CWiaItem::SetCompatMode(v10, 0);
        inited = -2145320959;
        v134 = v231;
        v232 = v231;
        v133 = (int)v233;
        LODWORD(pbstr) = (_DWORD)v233;
      }
      else
      {
        v232 = v231;
        v127 = (int)v233;
        LODWORD(pbstr) = (_DWORD)v233;
        v128 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                         0,
                         0,
                         "Compatibility Mode: detected LH D-AIT feeder = %u, flatbed = %u",
                         (_DWORD)v233,
                         v231);
        WriteDbgTraceInfoWI("CreateLocalDevice", v128);
        WiaTrcLib::Free((WiaTrcLib *)v128, v129);
        v130 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                          0,
                          0,
                          "Compatibility Mode: detected LH D-AIT feeder = %u, flatbed = %u",
                          v127,
                          v232);
        WiaTrace_ProcessTrace_Ex(v132, v131, (void *)"CreateLocalDevice", 4, v130);
        v102 = v234;
        v133 = v127;
        v134 = v232;
      }
      if ( inited >= 0 && !v134 && !v133 )
      {
        v140 = (char *)WiaTrace_TraceLog("Incompatible D-AIT items, compatibility mode disabled");
        WriteDbgTraceErrorWI("CreateLocalDevice", v140);
        WiaTrcLib::Free((WiaTrcLib *)v140, v141);
        v142 = (void **)WiaTrace_Trace("Incompatible D-AIT items, compatibility mode disabled");
        WiaTrace_ProcessTrace_Ex(v144, v143, (void *)"CreateLocalDevice", 1, v142);
        v102 = 0;
        LODWORD(v234) = 0;
        CWiaItem::SetCompatMode(v10, 0);
        inited = -2145320959;
      }
    }
LABEL_111:
    v145 = 0;
    if ( !v102 )
      goto LABEL_174;
    v146 = (CWiaItem *)operator new(0x130u);
    if ( v146 )
      v145 = CWiaItem::CWiaItem(v146);
    if ( !v145 )
    {
      v209 = (char *)WiaTrace_TraceLog("cannot allocate memory for A-AIT, compatibility mode disabled");
      WriteDbgTraceErrorWI("CreateLocalDevice", v209);
      WiaTrcLib::Free((WiaTrcLib *)v209, v210);
      v211 = (void **)WiaTrace_Trace("cannot allocate memory for A-AIT, compatibility mode disabled");
      WiaTrace_ProcessTrace_Ex(v213, v212, (void *)"CreateLocalDevice", 1, v211);
      v102 = 0;
      CWiaItem::SetCompatMode(v10, 0);
LABEL_157:
      switch ( v102 )
      {
        case 0u:
          goto LABEL_174;
        case 1u:
          if ( v232 )
          {
            inited = CWiaItem::CreateCompatLayerChild(v145, 0, 0);
            if ( inited >= 0 )
            {
              CWiaItem::SetCompatMode(v10, 1);
              CWiaItem::SetCompatMode(v145, 1);
              inited = CWiaItem::InitChildItemLHProps(v145, 0);
            }
          }
          if ( inited < 0 )
          {
LABEL_171:
            v215 = (char *)WiaTrace_TraceLog("failed to create one A-AIT child item, compatibility mode disabled");
            WriteDbgTraceErrorWI("CreateLocalDevice", v215);
            WiaTrcLib::Free((WiaTrcLib *)v215, v216);
            v217 = (void **)WiaTrace_Trace("failed to create one A-AIT child item, compatibility mode disabled");
            WiaTrace_ProcessTrace_Ex(v219, v218, (void *)"CreateLocalDevice", 1, v217);
            v102 = 0;
            CWiaItem::SetCompatMode(v10, 0);
            if ( v145 )
              CWiaItem::`scalar deleting destructor'(v145, v220);
            v145 = 0;
LABEL_174:
            if ( inited < 0 )
            {
LABEL_181:
              v221 = (char *)WiaTrace_TraceLog("CreateLocalDevice failed, cannot enter compatibility mode");
              WriteDbgTraceErrorWI("CreateLocalDevice", v221);
              WiaTrcLib::Free((WiaTrcLib *)v221, v222);
              v223 = (void **)WiaTrace_Trace("CreateLocalDevice failed, cannot enter compatibility mode");
              WiaTrace_ProcessTrace_Ex(v225, v224, (void *)"CreateLocalDevice", 1, v223);
LABEL_182:
              USDWrapperFromDeviceList = v243;
              goto LABEL_183;
            }
LABEL_175:
            if ( v102 )
            {
              CWiaItem::SetCompatMode(v10, v102);
              if ( *((_DWORD *)v145 + 26) )
                *((_DWORD *)v145 + 27) = 1;
              inited = (**(__int64 (__fastcall ***)(CWiaItem *, GUID *, struct IUnknown **))v145)(
                         v145,
                         &IID_IUnknown,
                         v241);
              if ( inited >= 0 )
                (*(void (__fastcall **)(CWiaItem *))(*(_QWORD *)v145 + 16LL))(v145);
            }
            if ( inited >= 0 )
              goto LABEL_182;
            goto LABEL_181;
          }
          if ( (_DWORD)pbstr )
          {
            inited = CWiaItem::CreateCompatLayerChild(v145, 0, 1);
            if ( inited >= 0 )
            {
              CWiaItem::SetCompatMode(v10, 1);
              CWiaItem::SetCompatMode(v145, 1);
              v214 = CWiaItem::InitChildItemLHProps(v145, 1);
LABEL_169:
              inited = v214;
            }
          }
          break;
        case 2u:
          inited = CWiaItem::CreateCompatLayerChild(v145, 1, 0);
          if ( inited >= 0 )
          {
            v214 = CWiaItem::InitChildItemXPProps(v145, 0);
            goto LABEL_169;
          }
          break;
      }
      if ( inited >= 0 )
        goto LABEL_175;
      goto LABEL_171;
    }
    bstrString = 0;
    inited = (**(__int64 (__fastcall ***)(CWiaItem *, GUID *, BSTR *))v145)(v145, &IID_IWiaPropertyStorage, &bstrString);
    if ( inited >= 0 && !bstrString )
      inited = -2147024882;
    if ( inited >= 0 )
    {
      inited = CWiaItem::InitializeWiaItem(
                 v145,
                 1,
                 v102 == 1,
                 v145,
                 (struct IWiaPropertyStorage *)bstrString,
                 v243,
                 v242,
                 0);
      if ( inited < 0 )
      {
        v152 = (char *)WiaTrace_TraceLog("cannot initialize A-AIT root item (0x%X), compatibility mode disabled");
        WriteDbgTraceErrorWI("CreateLocalDevice", v152);
        WiaTrcLib::Free((WiaTrcLib *)v152, v153);
        v154 = (void **)WiaTrace_Trace("cannot initialize A-AIT root item (0x%X), compatibility mode disabled", inited);
        WiaTrace_ProcessTrace_Ex(v156, v155, (void *)"CreateLocalDevice", 1, v154);
      }
    }
    else
    {
      v147 = (char *)WiaTrace_TraceLog("cannot get the IWiaPropertyStorage interface for A-AIT, compatibility mode disabled");
      WriteDbgTraceErrorWI("CreateLocalDevice", v147);
      WiaTrcLib::Free((WiaTrcLib *)v147, v148);
      v149 = (void **)WiaTrace_Trace("cannot get the IWiaPropertyStorage interface for A-AIT, compatibility mode disabled");
      WiaTrace_ProcessTrace_Ex(v151, v150, (void *)"CreateLocalDevice", 1, v149);
    }
    v233 = 0;
    v237 = 0;
    v157 = 0;
    v231 = 0;
    if ( inited < 0 )
      goto LABEL_146;
    Buf1[0] = v242;
    if ( !v242 )
    {
      inited = -2147024809;
      v182 = (char *)WiaTrace_TraceLog("unable to get a valid CWiaDrvItem* for the root D-AIT to copy item name and flags (0x%X)");
      WriteDbgTraceErrorWI("CreateLocalDevice", v182);
      WiaTrcLib::Free((WiaTrcLib *)v182, v183);
      v184 = (void **)WiaTrace_Trace(
                        "unable to get a valid CWiaDrvItem* for the root D-AIT to copy item name and flags (0x%X)",
                        -2147024809);
      WiaTrace_ProcessTrace_Ex(v186, v185, (void *)"CreateLocalDevice", 1, v184);
      v157 = v231;
      goto LABEL_139;
    }
    inited = (*(__int64 (__fastcall **)(struct CWiaDrvItem *, BSTR *))(*(_QWORD *)v242 + 48LL))(v242, &v233);
    if ( inited >= 0 )
    {
      v163 = v233;
      v164 = (OLECHAR *)*((_QWORD *)v145 + 24);
      if ( v164 )
      {
        SysFreeString(v164);
        *((_QWORD *)v145 + 24) = 0;
      }
      v165 = SysAllocString(v163);
      *((_QWORD *)v145 + 24) = v165;
      inited = v165 == 0 ? 0x8007000E : 0;
      if ( !v165 )
      {
        v166 = (char *)WiaTrace_TraceLog("copy full item name for root A-AIT failed (0x%X)");
        WriteDbgTraceErrorWI("CreateLocalDevice", v166);
        WiaTrcLib::Free((WiaTrcLib *)v166, v167);
        v168 = (void **)WiaTrace_Trace("copy full item name for root A-AIT failed (0x%X)", inited);
        WiaTrace_ProcessTrace_Ex(v170, v169, (void *)"CreateLocalDevice", 1, v168);
      }
      if ( inited >= 0 )
      {
        v171 = Buf1[0];
        inited = (*(__int64 (__fastcall **)(void *, BSTR *))(*(_QWORD *)Buf1[0] + 40LL))(Buf1[0], &v237);
        if ( inited >= 0 )
          goto LABEL_134;
        v172 = (char *)WiaTrace_TraceLog("read full item name from root D-AIT item failed (0x%X)");
        WriteDbgTraceErrorWI("CreateLocalDevice", v172);
        WiaTrcLib::Free((WiaTrcLib *)v172, v173);
        v174 = (void **)WiaTrace_Trace("read full item name from root D-AIT item failed (0x%X)", inited);
        WiaTrace_ProcessTrace_Ex(v176, v175, (void *)"CreateLocalDevice", 1, v174);
      }
    }
    else
    {
      v158 = (char *)WiaTrace_TraceLog("read item name from root D-AIT item failed (0x%X)");
      WriteDbgTraceErrorWI("CreateLocalDevice", v158);
      WiaTrcLib::Free((WiaTrcLib *)v158, v159);
      v160 = (void **)WiaTrace_Trace("read item name from root D-AIT item failed (0x%X)", inited);
      WiaTrace_ProcessTrace_Ex(v162, v161, (void *)"CreateLocalDevice", 1, v160);
    }
    v171 = Buf1[0];
LABEL_134:
    if ( inited >= 0 )
    {
      inited = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v171 + 24LL))(v171, &v231);
      if ( inited < 0 )
      {
        v177 = (char *)WiaTrace_TraceLog("read item flags from root D-AIT failed (0x%X)");
        WriteDbgTraceErrorWI("CreateLocalDevice", v177);
        WiaTrcLib::Free((WiaTrcLib *)v177, v178);
        v179 = (void **)WiaTrace_Trace("read item flags from root D-AIT failed (0x%X)", inited);
        WiaTrace_ProcessTrace_Ex(v181, v180, (void *)"CreateLocalDevice", 1, v179);
      }
    }
    v157 = v231 | 0xC;
    v231 |= 0xCu;
LABEL_139:
    if ( inited >= 0 )
    {
      inited = CWiaItem::InitManagedItemProperties(v145, v157, v233, v237);
      if ( inited >= 0 )
      {
        inited = CWiaItem::InitRootProperties(v145, (struct IWiaPropertyStorage *)bstrString);
        if ( inited >= 0 )
        {
          CWiaItem::SetAITLink(v10, v145, 0);
          CWiaItem::SetAITLink(v145, v10, 1);
          v197 = v234;
          CWiaItem::SetCompatMode(v145, (unsigned int)v234);
          inited = CWiaItem::InitAAITItemTree(v145, v231, v233, v237);
          if ( inited >= 0 )
            goto LABEL_147;
          v198 = (char *)WiaTrace_TraceLog("InitAAITItemTree for the A-AIT root failed (0x%X)");
          WriteDbgTraceErrorWI("CreateLocalDevice", v198);
          WiaTrcLib::Free((WiaTrcLib *)v198, v199);
          v200 = (void **)WiaTrace_Trace("InitAAITItemTree for the A-AIT root failed (0x%X)", inited);
          WiaTrace_ProcessTrace_Ex(v202, v201, (void *)"CreateLocalDevice", 1, v200);
        }
        else
        {
          v192 = (char *)WiaTrace_TraceLog("cannot initialize WIA_DIP_ props for the A-AIT root (0x%X), compatibility mode disabled");
          WriteDbgTraceErrorWI("CreateLocalDevice", v192);
          WiaTrcLib::Free((WiaTrcLib *)v192, v193);
          v194 = (void **)WiaTrace_Trace(
                            "cannot initialize WIA_DIP_ props for the A-AIT root (0x%X), compatibility mode disabled",
                            inited);
          WiaTrace_ProcessTrace_Ex(v196, v195, (void *)"CreateLocalDevice", 1, v194);
        }
      }
      else
      {
        v187 = (char *)WiaTrace_TraceLog("InitManagedItemProperties on A-AIT root failed (0x%X)");
        WriteDbgTraceErrorWI("CreateLocalDevice", v187);
        WiaTrcLib::Free((WiaTrcLib *)v187, v188);
        v189 = (void **)WiaTrace_Trace("InitManagedItemProperties on A-AIT root failed (0x%X)", inited);
        WiaTrace_ProcessTrace_Ex(v191, v190, (void *)"CreateLocalDevice", 1, v189);
      }
    }
LABEL_146:
    v197 = v234;
LABEL_147:
    if ( inited >= 0 )
    {
      if ( v197 == 1 )
        v203 = CWiaItem::InitRootItemLHProps(v145);
      else
        v203 = CWiaItem::InitRootItemXPProps(v145);
      inited = v203;
      if ( v203 >= 0 )
      {
        v102 = v234;
        goto LABEL_155;
      }
      v204 = (char *)WiaTrace_TraceLog("cannot initialize A-AIT root item properties (0x%X), compatibility mode disabled");
      WriteDbgTraceErrorWI("CreateLocalDevice", v204);
      WiaTrcLib::Free((WiaTrcLib *)v204, v205);
      v206 = (void **)WiaTrace_Trace(
                        "cannot initialize A-AIT root item properties (0x%X), compatibility mode disabled",
                        inited);
      WiaTrace_ProcessTrace_Ex(v208, v207, (void *)"CreateLocalDevice", 1, v206);
    }
    CWiaItem::`scalar deleting destructor'(v145, v157);
    v145 = 0;
    v102 = 0;
    CWiaItem::SetCompatMode(v10, 0);
LABEL_155:
    SysFreeString(v237);
    SysFreeString(v233);
    goto LABEL_157;
  }
LABEL_183:
  if ( inited >= 0 )
  {
    if ( v10 )
    {
      v226 = *((_DWORD *)v10 + 56);
      IsLegacyDriver = CWiaItem::IsLegacyDriver(v10);
      v228 = IsLegacyDriver;
      LODWORD(v233) = 0;
      if ( v226 == 1 && IsLegacyDriver )
        LODWORD(v233) = *(_WORD *)((*(__int64 (__fastcall **)(struct USDWrapper *))(*(_QWORD *)USDWrapperFromDeviceList
                                                                                  + 152LL))(USDWrapperFromDeviceList)
                                 + 42) == 1;
      v231 = (v226 != 1) + 1;
      v232 = 2 - (v228 != 0);
      WiaServiceTelemetry::WiaScanSessionCreated<int,int,int &>(&v232, &v231, &v233);
    }
    goto LABEL_194;
  }
LABEL_190:
  if ( v241 )
    *v241 = 0;
  if ( v10 )
    (*(void (__fastcall **)(CWiaItem *))(*(_QWORD *)v10 + 16LL))(v10);
LABEL_194:
  if ( USDWrapperFromDeviceList )
    (*(void (__fastcall **)(struct USDWrapper *))(*(_QWORD *)USDWrapperFromDeviceList + 16LL))(USDWrapperFromDeviceList);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v252);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800552bc  push    rbx
0x1800552be  push    rsi
0x1800552bf  push    rdi
0x1800552c0  push    r12
0x1800552c2  push    r13
0x1800552c4  push    r14
0x1800552c6  push    r15
0x1800552c8  sub     rsp, 410h
0x1800552cf  mov     rax, cs:__security_cookie
0x1800552d6  xor     rax, rsp
0x1800552d9  mov     [rsp+448h+var_48], rax
0x1800552e1  mov     [rsp+448h+var_3E4], r9d
0x1800552e6  mov     rbx, r8
0x1800552e9  mov     [rsp+448h+var_358], rbx
0x1800552f1  mov     [rsp+448h+pbstr], rdx
0x1800552f6  mov     [rsp+448h+Buf1], rcx
0x1800552fe  mov     [rsp+448h+var_380], rbx
0x180055306  mov     r14, [rsp+448h+arg_20]
0x18005530e  mov     [rsp+448h+var_398], r14
0x180055316  lea     rcx, aCreatelocaldev_1; "::CreateLocalDevice"
0x18005531d  call    WiaTrace_Trace
0x180055322  mov     [rsp+448h+var_420], rax; struct tagWiaTraceData_Type *
0x180055327  lea     r15, aCreatelocaldev; "CreateLocalDevice"
0x18005532e  mov     r9, r15; char *
0x180055331  lea     rcx, [rsp+448h+var_338]; this
0x180055339  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18005533e  xor     edi, edi
0x180055340  mov     r13d, edi
0x180055343  mov     [rsp+448h+var_388], rdi
0x18005534b  mov     [rsp+448h+var_368], rdi
0x180055353  mov     r12d, edi
0x180055356  mov     [rsp+448h+var_3C0], rdi
0x18005535e  mov     [rsp+448h+var_370], rdi
0x180055366  mov     [rsp+448h+var_390], rdi
0x18005536e  mov     [rsp+448h+var_360], rdi
0x180055376  mov     eax, edi
0x180055378  mov     [rsp+448h+var_3E8], eax
0x18005537c  mov     dword ptr [rsp+448h+var_3E0], eax
0x180055380  mov     [rsp+448h+bstrString], rdi
0x180055388  test    rbx, rbx
0x18005538b  jz      short loc_18005539A
0x18005538d  mov     esi, edi
0x18005538f  test    r14, r14
0x180055392  jz      short loc_18005539A
0x180055394  lea     r14d, [rdi+1]
0x180055398  jmp     short loc_1800553E3
0x18005539a  lea     rcx, aInvalidArgumen; "Invalid argument"
0x1800553a1  call    WiaTrace_TraceLog
0x1800553a6  mov     rbx, rax
0x1800553a9  mov     rdx, rax; char *
0x1800553ac  mov     rcx, r15; char *
0x1800553af  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800553b4  mov     rcx, rbx; this
0x1800553b7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800553bc  lea     rcx, aInvalidArgumen; "Invalid argument"
0x1800553c3  call    WiaTrace_Trace
0x1800553c8  mov     [rsp+448h+lpMem], rax; lpMem
0x1800553cd  mov     r14d, 1
0x1800553d3  mov     r9d, r14d; int
0x1800553d6  mov     r8, r15; int
0x1800553d9  call    WiaTrace_ProcessTrace_Ex
0x1800553de  mov     esi, 80070057h
0x1800553e3  mov     rcx, [rsp+448h+pbstr]; pbstr
0x1800553e8  call    cs:__imp_SysStringLen
0x1800553ee  test    eax, eax
0x1800553f0  jnz     short loc_180055435
0x1800553f2  lea     rcx, aInvalidArgumen; "Invalid argument"
0x1800553f9  call    WiaTrace_TraceLog
0x1800553fe  mov     rbx, rax
0x180055401  mov     rdx, rax; char *
0x180055404  mov     rcx, r15; char *
0x180055407  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005540c  mov     rcx, rbx; this
0x18005540f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180055414  lea     rcx, aInvalidArgumen; "Invalid argument"
0x18005541b  call    WiaTrace_Trace
0x180055420  mov     [rsp+448h+lpMem], rax; lpMem
0x180055425  mov     r9d, r14d; int
0x180055428  mov     r8, r15; int
0x18005542b  call    WiaTrace_ProcessTrace_Ex
0x180055430  mov     esi, 80070057h
0x180055435  test    esi, esi
0x180055437  js      loc_18005558B
0x18005543d  mov     rax, [rsp+448h+var_398]
0x180055445  mov     [rax], rdi
0x180055448  mov     r8d, 10h; Size
0x18005544e  lea     rdx, CLSID_WiaDevMgr; Buf2
0x180055455  mov     rbx, [rsp+448h+Buf1]
0x18005545d  mov     rcx, rbx; Buf1
0x180055460  call    memcmp_0
0x180055465  mov     ecx, edi
0x180055467  test    eax, eax
0x180055469  setz    cl
0x18005546c  mov     [rsp+448h+var_3E8], ecx
0x180055470  mov     dword ptr [rsp+448h+var_3E0], ecx
0x180055474  test    ecx, ecx
0x180055476  jnz     short loc_1800554D2
0x180055478  lea     r8d, [rcx+10h]; Size
0x18005547c  lea     rdx, CLSID_WiaDevMgr2; Buf2
0x180055483  mov     rcx, rbx; Buf1
0x180055486  call    memcmp_0
0x18005548b  test    eax, eax
0x18005548d  jz      short loc_1800554D2
0x18005548f  lea     rcx, aBadGuid; "bad GUID"
0x180055496  call    WiaTrace_TraceLog
0x18005549b  mov     rbx, rax
0x18005549e  mov     rdx, rax; char *
0x1800554a1  mov     rcx, r15; char *
0x1800554a4  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800554a9  mov     rcx, rbx; this
0x1800554ac  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800554b1  lea     rcx, aBadGuid; "bad GUID"
0x1800554b8  call    WiaTrace_Trace
0x1800554bd  mov     [rsp+448h+lpMem], rax; lpMem
0x1800554c2  mov     r9d, r14d; int
0x1800554c5  mov     r8, r15; int
0x1800554c8  call    WiaTrace_ProcessTrace_Ex
0x1800554cd  mov     esi, 80070057h
0x1800554d2  test    esi, esi
0x1800554d4  js      loc_18005558B
0x1800554da  lea     rdx, asc_180095304; "}\\"
0x1800554e1  mov     rbx, [rsp+448h+pbstr]
0x1800554e6  mov     rcx, rbx; Str
0x1800554e9  call    cs:__imp_wcsstr
0x1800554ef  test    rax, rax
0x1800554f2  jnz     short loc_1800554F9
0x1800554f4  mov     rax, rbx
0x1800554f7  jmp     short loc_1800554FD
0x1800554f9  add     rax, 4
0x1800554fd  mov     r8, rax; unsigned __int16 *
0x180055500  mov     r11d, 20h ; ' '
0x180055506  mov     edx, r11d; unsigned __int64
0x180055509  lea     rcx, [rsp+448h+psz]; unsigned __int16 *
0x180055511  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180055516  lea     r8, aRoot_0; "\\Root"
0x18005551d  mov     edx, r11d; unsigned __int64
0x180055520  lea     rcx, [rsp+448h+psz]; unsigned __int16 *
0x180055528  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005552d  lea     rcx, [rsp+448h+psz]; psz
0x180055535  call    cs:__imp_SysAllocString
0x18005553b  mov     [rsp+448h+bstrString], rax
0x180055543  test    rax, rax
0x180055546  jnz     short loc_180055590
0x180055548  lea     rcx, aUnableToAlloca; "unable to allocate property stream devi"...
0x18005554f  call    WiaTrace_TraceLog
0x180055554  mov     rbx, rax
0x180055557  mov     rdx, rax; char *
0x18005555a  mov     rcx, r15; char *
0x18005555d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180055562  mov     rcx, rbx; this
0x180055565  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005556a  lea     rcx, aUnableToAlloca; "unable to allocate property stream devi"...
0x180055571  call    WiaTrace_Trace
0x180055576  mov     [rsp+448h+lpMem], rax; lpMem
0x18005557b  mov     r9d, r14d; int
0x18005557e  mov     r8, r15; int
0x180055581  call    WiaTrace_ProcessTrace_Ex
0x180055586  mov     esi, 8007000Eh
0x18005558b  mov     rbx, [rsp+448h+pbstr]
0x180055590  test    esi, esi
0x180055592  js      loc_180055737
0x180055598  mov     rdx, rbx
0x18005559b  lea     rcx, [rsp+448h+var_1B8]
0x1800555a3  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800555a8  lea     rdx, [rsp+448h+var_1B8]
0x1800555b0  call    ?GetUSDWrapperFromDeviceList@@YAPEAVUSDWrapper@@JAEBV?$CSimpleStringBase@G@@@Z; GetUSDWrapperFromDeviceList(long,CSimpleStringBase<ushort> const &)
0x1800555b5  mov     r13, rax
0x1800555b8  mov     [rsp+448h+var_388], rax
0x1800555c0  lea     rbx, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800555c7  mov     [rsp+448h+var_1B8], rbx
0x1800555cf  lea     rcx, [rsp+448h+var_1B8]
0x1800555d7  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800555dc  mov     [rsp+448h+var_A8], rdi
0x1800555e4  test    r13, r13
0x1800555e7  jnz     short loc_18005562C
0x1800555e9  lea     rcx, aUnableToFindAc; "unable to find active STI USD device ob"...
0x1800555f0  call    WiaTrace_TraceLog
0x1800555f5  mov     rbx, rax
0x1800555f8  mov     rdx, rax; char *
0x1800555fb  mov     rcx, r15; char *
0x1800555fe  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180055603  mov     rcx, rbx; this
0x180055606  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005560b  lea     rcx, aUnableToFindAc; "unable to find active STI USD device ob"...
0x180055612  call    WiaTrace_Trace
0x180055617  mov     [rsp+448h+lpMem], rax; lpMem
0x18005561c  mov     r9d, r14d; int
0x18005561f  mov     r8, r15; int
0x180055622  call    WiaTrace_ProcessTrace_Ex
0x180055627  mov     esi, 80210015h
0x18005562c  test    esi, esi
0x18005562e  js      loc_180055737
0x180055634  mov     rax, [r13+0]
0x180055638  mov     edx, 2
0x18005563d  mov     rcx, r13
0x180055640  mov     rax, [rax+68h]
0x180055644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055649  mov     rax, [r13+0]
0x18005564d  mov     rcx, r13
0x180055650  mov     rax, [rax+0C8h]
0x180055657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005565c  mov     rbx, rax
0x18005565f  mov     [rsp+448h+Buf1], rax
0x180055667  test    rax, rax
0x18005566a  jnz     short loc_1800556E5
0x18005566c  mov     rax, [r13+0]
0x180055670  mov     rax, [rax+0C0h]
0x180055677  mov     [rsp+448h+Buf1], rax
0x18005567f  lea     ecx, [rbx+18h]; Size
0x180055682  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180055687  mov     rbx, rax
0x18005568a  test    rax, rax
0x18005568d  jz      short loc_1800556B1
0x18005568f  lea     rax, ??_7FakeStiDevice@@6B@; const FakeStiDevice::`vftable'
0x180055696  mov     [rbx], rax
0x180055699  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x1800556a0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(void)
0x1800556a5  movzx   ecx, al
0x1800556a8  mov     [rbx+8], ecx
0x1800556ab  mov     [rbx+10h], rdi
0x1800556af  jmp     short loc_1800556B4
0x1800556b1  mov     rbx, rdi
0x1800556b4  mov     rdx, rbx
0x1800556b7  mov     rcx, r13
0x1800556ba  mov     rax, [rsp+448h+Buf1]
0x1800556c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556c7  mov     rax, [r13+0]
0x1800556cb  mov     rcx, r13
0x1800556ce  mov     rax, [rax+0C8h]
0x1800556d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556da  mov     rbx, rax
0x1800556dd  mov     [rsp+448h+Buf1], rax
0x1800556e5  test    rbx, rbx
0x1800556e8  jnz     short loc_18005573A
0x1800556ea  lea     rcx, aUnableToAlloca_0; "unable to allocate fake device"
0x1800556f1  call    WiaTrace_TraceLog
0x1800556f6  mov     rbx, rax
0x1800556f9  mov     rdx, rax; char *
0x1800556fc  mov     rcx, r15; char *
0x1800556ff  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180055704  mov     rcx, rbx; this
0x180055707  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005570c  lea     rcx, aUnableToAlloca_0; "unable to allocate fake device"
0x180055713  call    WiaTrace_Trace
0x180055718  mov     [rsp+448h+lpMem], rax; lpMem
0x18005571d  mov     r9d, r14d; int
0x180055720  mov     r8, r15; int
0x180055723  call    WiaTrace_ProcessTrace_Ex
0x180055728  mov     esi, 8007000Eh
0x18005572d  mov     rbx, [rsp+448h+Buf1]
0x180055735  jmp     short loc_18005573A
0x180055737  mov     rbx, rdi
0x18005573a  test    esi, esi
0x18005573c  js      loc_180055D4A
0x180055742  mov     [rbx+10h], r13
0x180055746  test    r13, r13
0x180055749  jz      short loc_18005576B
0x18005574b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x180055752  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(void)
0x180055757  test    al, al
0x180055759  jz      short loc_18005576B
0x18005575b  mov     rcx, [rbx+10h]
0x18005575f  mov     rax, [rcx]
0x180055762  mov     rax, [rax+8]
0x180055766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005576b  mov     rax, [rbx]
0x18005576e  lea     r8, [rsp+448h+var_368]
0x180055776  lea     rdx, IID_IStiDevice
0x18005577d  mov     rcx, rbx
0x180055780  mov     rax, [rax]
0x180055783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055788  mov     esi, eax
0x18005578a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x180055791  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(void)
0x180055796  test    al, al
0x180055798  jz      short loc_1800557A9
0x18005579a  mov     rcx, [rbx]
0x18005579d  mov     rax, [rcx+10h]
0x1800557a1  mov     rcx, rbx
0x1800557a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800557a9  test    esi, esi
0x1800557ab  js      loc_180055D4A
0x1800557b1  mov     ecx, 130h; Size
0x1800557b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800557bb  test    rax, rax
0x1800557be  jz      short loc_1800557CB
0x1800557c0  mov     rcx, rax; this
0x1800557c3  call    ??0CWiaItem@@QEAA@XZ; CWiaItem::CWiaItem(void)
0x1800557c8  mov     r12, rax
0x1800557cb  mov     [rsp+448h+var_3C0], r12
0x1800557d3  test    r12, r12
0x1800557d6  jnz     short loc_18005581B
0x1800557d8  lea     rcx, aUnableToAlloca_2; "unable to allocate root item"
0x1800557df  call    WiaTrace_TraceLog
0x1800557e4  mov     rbx, rax
0x1800557e7  mov     rdx, rax; char *
0x1800557ea  mov     rcx, r15; char *
0x1800557ed  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800557f2  mov     rcx, rbx; this
0x1800557f5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
  ... truncated ...
```
