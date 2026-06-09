# BlbBackupThreadFunc(void *)

- ea: `0x140019fd0`
- end: `0x14001d2ca`
- name: `?BlbBackupThreadFunc@@YAKPEAX@Z`
- size: `13050`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `143`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140001008`
- `0x1400010b8`
- `0x140006ca8`
- `0x140006d94`
- `0x140007ad3`
- `0x14000aee8`
- `0x14000b0bc`
- `0x14000b25c`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be7c`
- `0x14000bfb8`
- `0x14000c318`
- `0x14000ce1c`
- `0x14000e4fc`
- `0x14000ed24`
- `0x14000f27c`
- `0x1400101b4`
- `0x140010470`
- `0x14001218c`
- `0x140013008`
- `0x1400130fc`
- `0x140013ed0`
- `0x140014200`
- `0x140014260`
- `0x140014384`
- `0x140014784`
- `0x14001480c`
- `0x140014860`
- `0x140014894`
- `0x140014bc0`
- `0x140014eec`
- `0x140014fd8`
- `0x140015010`
- `0x140015244`
- `0x14001526c`
- `0x1400154f0`
- `0x140015558`
- `0x140015e48`
- `0x14001706c`
- `0x140019fd0`
- `0x14001d750`
- `0x14001e86c`
- `0x14001ec78`
- `0x14001eca4`
- `0x14001f488`
- `0x140020034`
- `0x1400204e8`
- `0x140021120`
- `0x140021210`

## import_xrefs

- `KERNEL32!SetThreadExecutionState` at `0x14001a170`
- `KERNEL32!SetThreadExecutionState` at `0x14001d214`
- `KERNEL32!SetThreadExecutionState` at `0x14001a170`
- `KERNEL32!SetThreadExecutionState` at `0x14001d214`
- `KERNEL32!Sleep` at `0x14001bc9b`
- `KERNEL32!Sleep` at `0x14001bc9b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001a165`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001a911`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001b6a9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001c407`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001c436`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001c5c4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001a165`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001a911`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001b6a9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001c407`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001c436`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14001c5c4`
- `KERNEL32!GetLastError` at `0x14001a987`
- `KERNEL32!GetLastError` at `0x14001a987`
- `USER32!LoadStringW` at `0x14001a97d`
- `USER32!LoadStringW` at `0x14001a97d`
- `ntdll!WinSqmAddToStream` at `0x14001d0ff`
- `ntdll!WinSqmAddToStream` at `0x14001d0ff`
- `ole32!CoTaskMemAlloc` at `0x14001a301`
- `ole32!CoTaskMemAlloc` at `0x14001a72c`
- `ole32!CoTaskMemAlloc` at `0x14001b381`
- `ole32!CoTaskMemAlloc` at `0x14001a301`
- `ole32!CoTaskMemAlloc` at `0x14001a72c`
- `ole32!CoTaskMemAlloc` at `0x14001b381`
- `ole32!CoTaskMemFree` at `0x14001b08e`
- `ole32!CoTaskMemFree` at `0x14001be31`
- `ole32!CoTaskMemFree` at `0x14001cc99`
- `ole32!CoTaskMemFree` at `0x14001ccb7`
- `ole32!CoTaskMemFree` at `0x14001ccc8`
- `ole32!CoTaskMemFree` at `0x14001ccec`
- `ole32!CoTaskMemFree` at `0x14001cd00`
- `ole32!CoTaskMemFree` at `0x14001cd0f`
- `ole32!CoTaskMemFree` at `0x14001cd1e`
- `ole32!CoTaskMemFree` at `0x14001cd31`
- `ole32!CoTaskMemFree` at `0x14001d11c`
- `ole32!CoTaskMemFree` at `0x14001b08e`
- `ole32!CoTaskMemFree` at `0x14001be31`
- `ole32!CoTaskMemFree` at `0x14001cc99`
- `ole32!CoTaskMemFree` at `0x14001ccb7`
- `ole32!CoTaskMemFree` at `0x14001ccc8`
- `ole32!CoTaskMemFree` at `0x14001ccec`
- `ole32!CoTaskMemFree` at `0x14001cd00`
- `ole32!CoTaskMemFree` at `0x14001cd0f`
- `ole32!CoTaskMemFree` at `0x14001cd1e`
- `ole32!CoTaskMemFree` at `0x14001cd31`
- `ole32!CoTaskMemFree` at `0x14001d11c`
- `ole32!CoCreateInstance` at `0x14001a6a5`
- `ole32!CoCreateInstance` at `0x14001b0f1`
- `ole32!CoCreateInstance` at `0x14001a6a5`
- `ole32!CoCreateInstance` at `0x14001b0f1`
- `ole32!CoInitializeEx` at `0x14001a2b3`
- `ole32!CoInitializeEx` at `0x14001a2b3`
- `ole32!CoUninitialize` at `0x14001cd56`
- `ole32!CoUninitialize` at `0x14001cd56`
- `SPP!SppFreeBadWritersArray` at `0x14001cc6e`
- `SPP!SppFreeBadWritersArray` at `0x14001cc6e`

## string_xrefs

- `0x14001a62f`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001b3ce`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001b3ef`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001b997`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001bdb7`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001c895`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001cdd9`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001ce65`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001cf20`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001cf90`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001acea`: `CreateGroup`
- `0x14001acf1`: `CreateGroupEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall BlbBackupThreadFunc(_QWORD **Parameter)
{
  struct IBLBCatalogSystem *Catalog; // rbx
  unsigned __int16 **v3; // rsi
  struct _SPP_METADATA_PROP *v4; // r13
  struct CBlbMediaBackupContext *v5; // r14
  struct CBlbMediaBackupContext *v6; // r15
  __int64 v7; // r12
  struct CBlbMediaBackupContext *v8; // rbx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  SIZE_T v11; // r13
  unsigned __int16 **v12; // rax
  __int64 v13; // r12
  unsigned int v14; // ebx
  __int64 v15; // r14
  unsigned __int16 **v16; // rsi
  int IsVolumeValid; // ebx
  int v18; // eax
  unsigned int v19; // edx
  _QWORD *v20; // rcx
  int v21; // edx
  int IsVolumeBitlocked; // eax
  void *v23; // rax
  int v24; // r12d
  __int64 v25; // r14
  unsigned __int16 **v26; // r13
  __int64 v27; // rbx
  _QWORD *v28; // rsi
  int v29; // eax
  unsigned int v30; // r14d
  PVOID *v31; // rcx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rdx
  signed int LastError; // eax
  unsigned int v36; // esi
  unsigned int v37; // ebx
  PVOID *v38; // rcx
  CBlbApplicationBackupAsync *v39; // r14
  unsigned __int16 **v40; // rax
  int v41; // eax
  _QWORD *v42; // rcx
  __int64 v43; // rdx
  char *v44; // r12
  int v45; // eax
  char *v46; // rax
  const wchar_t *v47; // r9
  unsigned int v48; // edx
  PVOID *v49; // rcx
  __int64 *v50; // r14
  int v51; // eax
  unsigned int i; // ebx
  __int64 v53; // rsi
  __int64 v54; // r15
  __int64 v55; // r15
  unsigned int j; // ebx
  __int64 v57; // rsi
  __int64 v58; // r14
  int IsClusterSharedVolume; // eax
  LPVOID *v60; // rax
  _QWORD *v61; // rcx
  __int64 v62; // rdx
  __int64 (__fastcall *v63)(_QWORD **, GUID *, _QWORD *); // rbx
  _QWORD *v64; // rax
  __int64 v65; // rax
  int v66; // eax
  struct _GUID **v67; // rbx
  struct _SPP_METADATA_PROP *v68; // rax
  _QWORD *v69; // rcx
  __int64 v70; // rdx
  int v71; // eax
  CBlbApplicationBackupAsync *v72; // r13
  _QWORD *v73; // rcx
  __int64 v74; // rdx
  unsigned __int64 v75; // rax
  __int64 (__fastcall *v76)(_QWORD **, GUID *, _QWORD *); // rbx
  _QWORD *v77; // rax
  CBlbFileAsync *v78; // rsi
  int v79; // ebx
  CBlbMediaBackupContext *v80; // rax
  CBlbMediaBackupContext *v81; // rax
  int v82; // r14d
  _BYTE *v83; // rbx
  unsigned int v84; // eax
  _BYTE *v85; // rsi
  CBlbSuppressAutoPlay *v86; // rax
  int v87; // r8d
  const wchar_t *v88; // rax
  int v89; // edx
  signed int v90; // eax
  _QWORD *v91; // rcx
  signed int BackupSetDirectory; // eax
  unsigned int v93; // ebx
  int v94; // eax
  int v95; // eax
  struct _GUID *v96; // rax
  int v97; // eax
  unsigned __int64 v98; // rax
  unsigned __int64 v99; // rax
  char v100; // bl
  int v101; // eax
  _QWORD *v102; // rcx
  __int64 v103; // rdx
  unsigned int k; // ebx
  unsigned __int16 *v105; // rcx
  _QWORD *v106; // rdx
  unsigned int v107; // ebx
  unsigned int m; // esi
  void *v109; // rcx
  char v110; // al
  int v111; // r8d
  unsigned int n; // edx
  int v113; // r8d
  unsigned int v114; // edx
  unsigned int v115; // ebx
  CBlbVolumeBackupContext *v116; // rcx
  int v117; // edx
  int v118; // ecx
  unsigned int ii; // ebx
  CBlbFileAsync *v120; // rcx
  PVOID *v121; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  unsigned int v124; // [rsp+70h] [rbp-90h] BYREF
  unsigned int IsClientSKU; // [rsp+74h] [rbp-8Ch] BYREF
  struct CBlbMediaBackupContext *v126; // [rsp+78h] [rbp-88h] BYREF
  struct CBlbMediaBackupContext *v127; // [rsp+80h] [rbp-80h]
  unsigned __int16 **v128; // [rsp+88h] [rbp-78h]
  struct _SPP_METADATA_PROP *v129; // [rsp+90h] [rbp-70h]
  struct CBlbMediaBackupContext *v130; // [rsp+98h] [rbp-68h]
  unsigned __int8 v131; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v132; // [rsp+A1h] [rbp-5Fh] BYREF
  unsigned __int8 v133; // [rsp+A2h] [rbp-5Eh] BYREF
  unsigned __int8 v134; // [rsp+A3h] [rbp-5Dh] BYREF
  _BYTE v135[4]; // [rsp+A4h] [rbp-5Ch] BYREF
  int Data1; // [rsp+A8h] [rbp-58h] BYREF
  char v137; // [rsp+ACh] [rbp-54h]
  char v138; // [rsp+ADh] [rbp-53h]
  char v139; // [rsp+AEh] [rbp-52h]
  unsigned __int8 v140; // [rsp+AFh] [rbp-51h]
  unsigned __int8 v141[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v142; // [rsp+B4h] [rbp-4Ch] BYREF
  struct _GUID *v143; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v144[4]; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v145; // [rsp+D0h] [rbp-30h] BYREF
  struct ISharedProtectionPoints *v146; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v147; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int v148; // [rsp+ECh] [rbp-14h] BYREF
  struct _SPP_WRITER_ERROR_INFO *v149; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+F8h] [rbp-8h]
  struct IBlbsrvReclaimSpaceCallback *v151; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v152; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v153[2]; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID v154; // [rsp+120h] [rbp+20h] BYREF
  struct _SPP_WRITER_COMPONENT_INFO *v155; // [rsp+130h] [rbp+30h] BYREF
  struct _BLB_COMPONENT *v156; // [rsp+138h] [rbp+38h] BYREF
  struct IVssBackupComponents *v157; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v158; // [rsp+148h] [rbp+48h] BYREF
  __int64 v159; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 *v160; // [rsp+158h] [rbp+58h] BYREF
  struct _FILETIME v161; // [rsp+160h] [rbp+60h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+168h] [rbp+68h] BYREF
  CBlbFileAsync *v163; // [rsp+170h] [rbp+70h]
  __int128 v164; // [rsp+178h] [rbp+78h] BYREF
  struct _GUID v165; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v166[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v167; // [rsp+1B0h] [rbp+B0h]
  struct _GUID v168; // [rsp+1C0h] [rbp+C0h] BYREF
  int v169; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v170; // [rsp+1D8h] [rbp+D8h]
  int v171; // [rsp+1E0h] [rbp+E0h]
  __int64 v172; // [rsp+1E8h] [rbp+E8h]
  int v173; // [rsp+1F0h] [rbp+F0h]
  __int64 v174; // [rsp+1F8h] [rbp+F8h]
  int v175; // [rsp+200h] [rbp+100h]
  __int64 v176; // [rsp+208h] [rbp+108h]
  WCHAR Buffer[104]; // [rsp+210h] [rbp+110h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 925, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  IsClientSKU = 0;
  Data1 = 0;
  v133 = 0;
  Catalog = CBlbAsync::GetCatalog((CBlbAsync *)(Parameter + 3));
  *(_QWORD *)&v165.Data1 = Catalog;
  v139 = 0;
  v146 = 0;
  v3 = 0;
  pv = 0;
  v142 = 0;
  v4 = 0;
  v164 = 0;
  v137 = 0;
  v138 = 0;
  v141[0] = 0;
  v168 = 0;
  v5 = 0;
  v130 = 0;
  v157 = 0;
  v140 = 0;
  v152 = 0;
  v143 = 0;
  v163 = 0;
  SystemTimeAsFileTime = 0;
  v161 = 0;
  v131 = 0;
  v169 = 1;
  v170 = 0;
  v171 = 1;
  v172 = 0;
  v173 = 1;
  v174 = 0;
  v175 = 1;
  v176 = 0;
  v158 = 0;
  v159 = 0;
  v166[0] = &CBlbObjectLock<CBlbBackupAsync>::`vftable';
  v166[1] = Parameter;
  v167 = 0;
  ATL::CComPtrBase<IBlbsrvReclaimSpaceCallback>::CComPtrBase<IBlbsrvReclaimSpaceCallback>(&v151);
  v6 = 0;
  v127 = 0;
  v135[0] = 0;
  v149 = 0;
  v144[0] = 0;
  v156 = 0;
  v148 = 0;
  v7 = *((unsigned int *)Parameter + 92);
  v124 = *((_DWORD *)Parameter + 92);
  v147 = 0;
  v155 = 0;
  v153[0] = 0;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_14015E050, 0, 0);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( !SetThreadExecutionState(0x80000001)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 926, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v154 = *(struct _GUID *)(Parameter + 37);
  if ( (int)PublishBackupStartEvent(&v154, *((unsigned __int8 *)Parameter + 390)) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 927, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  IsClientSKU = BlbutilIsClientSKU(&v131);
  if ( (IsClientSKU & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 928, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    goto LABEL_20;
  }
  IsClientSKU = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, char *))(*(_QWORD *)Catalog + 136LL))(
                  Catalog,
                  (char *)Parameter + 400);
  if ( (IsClientSKU & 0x80000000) != 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v10 = 929;
LABEL_26:
    WPP_SF_d(v9[2], v10, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_20:
    v8 = 0;
    goto LABEL_577;
  }
  IsClientSKU = CoInitializeEx(0, 0);
  if ( (IsClientSKU & 0x80000000) != 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v10 = 930;
    goto LABEL_26;
  }
  v139 = 1;
  v11 = 8 * v7;
  v12 = (unsigned __int16 **)CoTaskMemAlloc(8 * v7);
  v3 = v12;
  v128 = v12;
  if ( !v12 )
  {
    IsClientSKU = -2147024882;
    v8 = 0;
    v4 = 0;
    goto LABEL_577;
  }
  memset_0(v12, 0, 8 * v7);
  v13 = 0;
  while ( 1 )
  {
    v14 = v124;
    if ( (unsigned int)v13 >= v124 )
      break;
    v15 = (__int64)&Parameter[27][46 * (unsigned int)v13];
    v16 = &v3[v13];
    IsClientSKU = BlbutilQueryVolumeName((struct _GUID *)(v15 + 68), *(_DWORD *)(v15 + 84), v16, 1u);
    if ( (IsClientSKU & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 931, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      v8 = 0;
      goto LABEL_92;
    }
    v132 = 0;
    IsVolumeValid = BlbIsVolumeValid(*v16, *(_DWORD *)(v15 + 84), &v132);
    if ( IsVolumeValid < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        932,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (unsigned int)*v16,
        IsVolumeValid);
      v145.Data1 = 0;
LABEL_42:
      if ( IsVolumeValid == -2147024894
        && (int)GetVolumeFriendlyNameForPublisher(v15 + 68, *(unsigned int *)(v15 + 84), 2, &v152) >= 0 )
      {
        v18 = PublishProtectedVolumeMissingEvent(v152, *v16);
        if ( v18 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            936,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            (_DWORD)v152,
            (__int64)*v16,
            v18);
        }
      }
      goto LABEL_49;
    }
    v145.Data1 = 0;
    if ( IsVolumeValid < 0 )
      goto LABEL_42;
    v19 = *(_DWORD *)(v15 + 84);
    if ( (v19 & 8) != 0 && (IsVolumeValid = BlbCheckVolumeSize(*v16, v19, (int *)&v145), IsVolumeValid < 0) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 933;
LABEL_73:
        WPP_SF_Sd(
          v20[2],
          v21,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (unsigned int)*v16,
          IsVolumeValid);
      }
    }
    else
    {
      v134 = 0;
      IsVolumeBitlocked = BlbIsVolumeBitlocked(*v16, &v134);
      if ( IsVolumeBitlocked >= 0 )
      {
        if ( v134 )
        {
          IsVolumeValid = -2139619151;
          goto LABEL_74;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          934,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (unsigned int)*v16,
          IsVolumeBitlocked);
      }
      if ( v132 )
      {
        if ( v145.Data1 <= 1 )
        {
          IsVolumeValid = BlbQueryVolumeSectorSize(*v16, (unsigned int *)(v15 + 64));
          if ( IsVolumeValid < 0 )
          {
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v21 = 935;
              goto LABEL_73;
            }
          }
        }
      }
    }
LABEL_74:
    if ( (int)v145.Data1 > 0 )
      PublishTwoTBSqmDataPoint(*v16);
    if ( IsVolumeValid < 0 )
      goto LABEL_42;
    if ( v132 )
    {
      if ( v145.Data1 != -1 && v145.Data1 != 2 )
        goto LABEL_53;
      if ( (v145.Data1 & 0x80000000) == 0 )
        IsVolumeValid = -2139619148;
      else
        IsVolumeValid = -2139619231;
    }
    else
    {
      IsVolumeValid = -2139619043;
    }
LABEL_49:
    CBlbVolumeBackupContext::SetAborted((CBlbVolumeBackupContext *)v15, IsVolumeValid, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        937,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (unsigned int)*v16,
        IsVolumeValid);
    }
LABEL_53:
    v13 = (unsigned int)(v13 + 1);
    v3 = v128;
  }
  IsClientSKU = CoCreateInstance(&CLSID_SPP, 0, 1u, &IID_ISharedProtectionPoints, (LPVOID *)&v146);
  if ( (IsClientSKU & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 938, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
LABEL_98:
    v8 = 0;
LABEL_99:
    v5 = v8;
    v6 = v8;
    v4 = v8;
    goto LABEL_576;
  }
  *(_QWORD *)&v154.Data1 = 0;
  if ( (unsigned __int8)operator==(Parameter + 35, &GUID_NULL) )
  {
    CBlbBackupAsync::SetState(Parameter, 2);
    v23 = CoTaskMemAlloc(v11);
    pv = v23;
    if ( !v23 )
    {
      IsClientSKU = -2147024882;
      goto LABEL_98;
    }
    v24 = 0;
    memset_0(v23, 0, v11);
    v25 = 0;
    v26 = v128;
    while ( (unsigned int)v25 < v14 )
    {
      v27 = 46LL * (unsigned int)v25;
      v28 = Parameter[27];
      if ( !BlbutilIsEspVolume(HIDWORD(v28[v27 + 10])) && SLODWORD(v28[v27 + 4]) >= 0 )
      {
        if ( v131 || (v29 = HIDWORD(v28[v27 + 10]), (v29 & 0x20) == 0) || (v29 & 0x40) != 0 || (v29 & 8) != 0 )
        {
          IsClientSKU = BlbutilDuplicateString(v26[v25], (unsigned __int16 **)pv + (unsigned int)v142, 0);
          if ( (IsClientSKU & 0x80000000) != 0 )
            goto LABEL_280;
          ++v142;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              939,
              &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              v28[v27 + 11]);
          }
          ++v24;
        }
        LOBYTE(v28[v27 + 17]) = 1;
      }
      v25 = (unsigned int)(v25 + 1);
      v14 = v124;
    }
    v30 = v142;
    if ( v142 )
      goto LABEL_130;
    if ( !v131 && v24 )
      goto LABEL_131;
    if ( !*((_BYTE *)Parameter + 391) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 940, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      IsClientSKU = -2139618958;
      goto LABEL_129;
    }
LABEL_130:
    if ( !v131 )
    {
LABEL_131:
      if ( ((*((_DWORD *)Parameter + 84) - 1) & 0xFFFFFFFB) != 0 )
      {
        CBlbBackupAsync::GetPreSnapshotUSNInfo((CBlbBackupAsync *)Parameter);
        goto LABEL_137;
      }
    }
    v31 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 941, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_137:
        v31 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 1) != 0 && *((_BYTE *)v31 + 25) >= 4u )
        WPP_SF_(v31[2], 942, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    GetSystemTimeAsFileTime((LPFILETIME)Parameter + 77);
    IsClientSKU = CBlbBackupAsync::SetSourceDiffAreasIfNeeded((CBlbBackupAsync *)Parameter, 1u);
    if ( (IsClientSKU & 0x80000000) != 0 )
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_129;
      }
      v33 = 943;
      goto LABEL_154;
    }
    if ( !LoadStringW(0, 0x6Au, Buffer, 100) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      IsClientSKU = LastError;
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v33 = 944;
        goto LABEL_154;
      }
LABEL_129:
      v8 = 0;
LABEL_92:
      v5 = v8;
      v6 = v8;
      v4 = v8;
      goto LABEL_575;
    }
    v36 = 1;
    v37 = 8 * ((_DWORD)Parameter[48] & 1);
    if ( *((_DWORD *)Parameter + 80) == 1 )
    {
LABEL_160:
      v38 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_161;
    }
    v37 |= 1u;
    v38 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 945, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        goto LABEL_160;
      }
LABEL_161:
      if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 1) != 0 && *((_BYTE *)v38 + 25) >= 4u )
      {
        ppv = v37;
        WPP_SF_dd(v38[2], 946, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
    }
    if ( !v131 && *((_BYTE *)Parameter + 390) && !v30 && !v147 && BlbIsSSBToAnyVolumeAllowed() )
      v36 = 0;
    if ( *((_BYTE *)Parameter + 391) )
    {
      v39 = (CBlbApplicationBackupAsync *)Parameter[104];
      *(_QWORD *)&v154.Data1 = v39;
      IsClientSKU = CBlbApplicationBackupAsync::InitializeComponentContexts(v39, (unsigned __int16 *)Parameter[107]);
      if ( (IsClientSKU & 0x80000000) != 0 )
        goto LABEL_129;
      IsClientSKU = CBlbApplicationBackupAsync::GetSPPWriterInfoFromComponents(v39, &v147, &v155);
      if ( (IsClientSKU & 0x80000000) != 0 )
        goto LABEL_129;
      if ( v36 )
      {
        IsClientSKU = BlbutilSlashTerminatePath((unsigned __int16 *)Parameter[43], (LPVOID *)v153);
        if ( (IsClientSKU & 0x80000000) != 0 )
          goto LABEL_129;
        v40 = v153;
      }
      else
      {
        v40 = 0;
      }
      IsClientSKU = CBlbApplicationBackupAsync::InitializeVolumeContexts(
                      v39,
                      v147,
                      v155,
                      *((_DWORD *)Parameter + 92),
                      (struct CBlbVolumeBackupContext *)Parameter[27],
                      v36,
                      (const unsigned __int16 *const *)v40);
      if ( (IsClientSKU & 0x80000000) != 0 )
        goto LABEL_129;
      v30 = v142;
    }
    if ( v131 )
    {
      v145 = (struct _GUID)xmmword_14013EA70;
      v41 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *, struct _GUID *, __int64, _QWORD, LPVOID))(*(_QWORD *)v146 + 88LL))(
              v146,
              &v145,
              1,
              v30,
              pv);
      IsClientSKU = v41;
      if ( v41 < 0 )
      {
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v43 = 947;
          goto LABEL_186;
        }
        goto LABEL_187;
      }
      v145 = (struct _GUID)xmmword_14013EA70;
      v41 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *, struct _GUID *, __int64))(*(_QWORD *)v146
                                                                                                 + 248LL))(
              v146,
              &v145,
              86400000);
      IsClientSKU = v41;
      if ( v41 < 0 )
      {
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v43 = 948;
LABEL_186:
          WPP_SF_d(v42[2], v43, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          v41 = IsClientSKU;
        }
LABEL_187:
        IsClientSKU = BlbTranslateSppError(v41, &Data1);
        goto LABEL_129;
      }
      v44 = (char *)(Parameter + 35);
      v45 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *, __int64, WCHAR *, _QWORD, int, _QWORD, _DWORD, char *))(*(_QWORD *)v146 + 24LL))(
              v146,
              15,
              Buffer,
              v37,
              5,
              0,
              0,
              (char *)Parameter + 280);
    }
    else
    {
      v46 = (char *)(Parameter + 43);
      if ( !v36 )
        v46 = 0;
      v44 = (char *)(Parameter + 35);
      LOBYTE(v34) = *((_BYTE *)Parameter + 390);
      v45 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *, __int64, _QWORD, LPVOID, unsigned int, struct _SPP_WRITER_COMPONENT_INFO *, unsigned int, char *, WCHAR *, unsigned int, int, _BYTE *, char *))(*(_QWORD *)v146 + 32LL))(
              v146,
              v34,
              v30,
              pv,
              v147,
              v155,
              v36,
              v46,
              Buffer,
              v37,
              5,
              v135,
              (char *)Parameter + 280);
    }
    IsClientSKU = v45;
    if ( v45 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v47 = L"CreateGroup";
        if ( !v131 )
          v47 = L"CreateGroupEx";
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          949,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (_DWORD)v47,
          v45);
        v45 = IsClientSKU;
      }
      if ( v45 == -2147024891 )
      {
        v48 = -2139619190;
        IsClientSKU = -2139619190;
        Data1 = -2147024891;
        goto LABEL_223;
      }
      IsClientSKU = BlbTranslateSppError(v45, &Data1);
      if ( CBlbBackupAsync::InitializeFileLogging((CBlbBackupAsync *)Parameter, (struct _FILETIME)Parameter[49]) < 0 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_129;
        }
        v33 = 950;
        goto LABEL_154;
      }
      if ( !v135[0] )
        goto LABEL_222;
      if ( (*(int (__fastcall **)(struct ISharedProtectionPoints *, unsigned int *, struct _SPP_WRITER_ERROR_INFO **))(*(_QWORD *)v146 + 40LL))(
             v146,
             v144,
             &v149) < 0 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_129;
        }
        v33 = 951;
        goto LABEL_154;
      }
      if ( (int)CBlbBackupAsync::LogFailedSnapshotComponents((CBlbBackupAsync *)Parameter, v144[0], v149) >= 0 )
      {
LABEL_222:
        v48 = IsClientSKU;
LABEL_223:
        v165 = *(struct _GUID *)(Parameter + 37);
        if ( (int)PublishBackupSppFailureEvent(&v165, v48, (struct _FILETIME)Parameter[49]) < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 953, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
        v140 = 1;
        goto LABEL_129;
      }
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_129;
      }
      v33 = 952;
LABEL_154:
      WPP_SF_d(v32[2], v33, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      goto LABEL_129;
    }
    if ( v135[0] )
    {
      IsClientSKU = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *, unsigned int *, struct _SPP_WRITER_ERROR_INFO **))(*(_QWORD *)v146 + 40LL))(
                      v146,
                      v144,
                      &v149);
      if ( (IsClientSKU & 0x80000000) != 0 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_129;
        }
        v33 = 954;
        goto LABEL_154;
      }
    }
    v49 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 955, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      v49 = (PVOID *)WPP_GLOBAL_Control;
    }
    v137 = 1;
    v3 = v128;
  }
  else
  {
    v49 = (PVOID *)WPP_GLOBAL_Control;
    v44 = (char *)(Parameter + 35);
  }
  if ( v49 != &WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 1) != 0 && *((_BYTE *)v49 + 25) >= 4u )
    WPP_SF_(v49[2], 956, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  v50 = (__int64 *)(Parameter + 53);
  v51 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *, char *, char *))(*(_QWORD *)v146 + 64LL))(
          v146,
          (char *)Parameter + 416,
          (char *)Parameter + 424);
  IsClientSKU = v51;
  if ( v51 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 957, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      v51 = IsClientSKU;
    }
    IsClientSKU = BlbTranslateSppError(v51, &Data1);
    v8 = v130;
    goto LABEL_99;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 958, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)Parameter + 104) )
      goto LABEL_685;
    v53 = 144LL * i;
    if ( (unsigned __int8)operator==(v53 + *v50, v44) )
      break;
  }
  v54 = *v50;
  v5 = 0;
  v55 = v53 + v54;
  if ( !v55 )
  {
LABEL_685:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 959, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    IsClientSKU = -2139619297;
LABEL_280:
    v8 = v130;
    goto LABEL_92;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= *(_DWORD *)(v55 + 80) )
      goto LABEL_266;
    v134 = 0;
    v57 = 56LL * j;
    v58 = *(_QWORD *)(v55 + 88);
    IsClusterSharedVolume = BlbIsClusterSharedVolume(*(const unsigned __int16 **)(v57 + v58 + 24), &v134);
    IsClientSKU = IsClusterSharedVolume;
    if ( IsClusterSharedVolume < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          960,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          *(_QWORD *)(v57 + v58 + 24),
          IsClusterSharedVolume);
      }
      goto LABEL_280;
    }
    v5 = 0;
    if ( v134 )
      break;
  }
  *((_BYTE *)Parameter + 1065) = 1;
LABEL_266:
  CoTaskMemFree(Parameter[55]);
  Parameter[55] = 0;
  *((_DWORD *)Parameter + 112) = 0;
  if ( v131
    && (BlbutilGetBackupFeatures(*((unsigned int *)Parameter + 84)) & 0x40) != 0
    && *((_DWORD *)Parameter + 80) == 1 )
  {
    *(_QWORD *)&v145.Data1 = 0;
    v60 = (LPVOID *)ATL::CComPtrBase<IRegisteredTask>::operator&(&v145);
    IsClientSKU = CoCreateInstance(&CLSID_SrDrvWuHelper, 0, 1u, &IID_ISrDrvWuHelper, v60);
    if ( (IsClientSKU & 0x80000000) != 0 )
    {
      v61 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v62 = 961;
        goto LABEL_274;
      }
      goto LABEL_275;
    }
    v63 = (__int64 (__fastcall *)(_QWORD **, GUID *, _QWORD *))**Parameter;
    v64 = ATL::CComPtrBase<IRegisteredTask>::operator&(&v159);
    IsClientSKU = v63(Parameter, &IID_ISrDriversWUStatusCallback, v64);
    if ( (IsClientSKU & 0x80000000) != 0 )
    {
      v61 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v62 = 962;
LABEL_274:
        WPP_SF_d(v61[2], v62, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
LABEL_275:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v145);
      goto LABEL_280;
    }
    v65 = ATL::CComPtrBase<IRegistrationInfo>::operator->((__int64)&v145);
    v66 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v65 + 24LL))(
            v65,
            v55,
            v159,
            &v164);
    IsClientSKU = v66;
    if ( v66 == -2147467260 )
    {
      if ( ((unsigned __int8 (__fastcall *)(char *))Parameter[3][2])((char *)Parameter + 24) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 963, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
        IsClientSKU = -2139619299;
        goto LABEL_275;
      }
      v66 = IsClientSKU;
    }
    if ( v66 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 964, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      IsClientSKU = 0;
    }
    Parameter[55] = (_QWORD *)*((_QWORD *)&v164 + 1);
    *((_DWORD *)Parameter + 112) = v164;
    *((_QWORD *)&v164 + 1) = 0;
    LODWORD(v164) = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v145);
  }
  Parameter[49] = *(_QWORD **)(v55 + 16);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 965, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v67 = (struct _GUID **)(Parameter + 54);
  IsClientSKU = BlbCloneSppGroup((struct _SPP_GROUP_PROP *)v55, (struct _SPP_GROUP_PROP **)Parameter + 54);
  if ( (IsClientSKU & 0x80000000) != 0 )
    goto LABEL_280;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 966, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v138 = 1;
  v68 = (struct _SPP_METADATA_PROP *)CoTaskMemAlloc(0x28u);
  v4 = v68;
  if ( !v68 )
  {
    IsClientSKU = -2147024882;
LABEL_312:
    v8 = v130;
    v5 = v130;
    v6 = v130;
    goto LABEL_575;
  }
  *(_OWORD *)v68 = 0;
  *((_OWORD *)v68 + 1) = 0;
  *((_QWORD *)v68 + 4) = 0;
  if ( !*(_QWORD *)(*v67)[5].Data4 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x5825u, "pContext->m_pGroup->rgVolumes");
  if ( !(*v67)[5].Data1 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x5826u, "pContext->m_pGroup->cVolumes > 0");
  v160 = 0;
  IsClientSKU = BlbGetValidSnapshotPathFromSppGroup(*v67, &v160);
  if ( (IsClientSKU & 0x80000000) != 0 )
  {
    v69 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_312;
    }
    v70 = 967;
    goto LABEL_322;
  }
  v71 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *, unsigned __int16 *, struct _SPP_METADATA_PROP *))(*(_QWORD *)v146 + 72LL))(
          v146,
          v160,
          v4);
  IsClientSKU = v71;
  if ( v71 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 968, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      v71 = IsClientSKU;
    }
    IsClientSKU = BlbTranslateSppError(v71, &Data1);
    goto LABEL_312;
  }
  Parameter[57] = v4;
  v4 = 0;
  v129 = 0;
  IsClientSKU = CBlbBackupAsync::InitializeFileLogging((CBlbBackupAsync *)Parameter, (struct _FILETIME)Parameter[49]);
  if ( (IsClientSKU & 0x80000000) != 0 )
  {
    v69 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_312;
    }
    v70 = 969;
LABEL_322:
    WPP_SF_d(v69[2], v70, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    goto LABEL_312;
  }
  IsClientSKU = CBlbBackupAsync::HandleSkippedComponentsInSppGroup((CBlbBackupAsync *)Parameter, v144[0], v149);
  if ( (IsClientSKU & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 970, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    goto LABEL_312;
  }
  v72 = *(CBlbApplicationBackupAsync **)&v154.Data1;
  if ( *((_BYTE *)Parameter + 391) )
  {
    IsClientSKU = CBlbApplicationBackupAsync::UpdateContextPostSnapshot(
                    *(CBlbApplicationBackupAsync **)&v154.Data1,
                    (struct _SPP_METADATA_PROP *)Parameter[57],
                    v144[0],
                    v149,
                    (struct _SPP_GROUP_PROP *)*v67);
    if ( (IsClientSKU & 0x80000000) != 0 )
      goto LABEL_356;
    IsClientSKU = CBlbApplicationBackupAsync::GetAppBackupComponents(v72, &v148, &v156);
    if ( (IsClientSKU & 0x80000000) != 0 )
      goto LABEL_356;
  }
  if ( !v131 )
  {
    IsClientSKU = CBlbApplicationBackupAsync::ComputePrevBackupCompSpecs((CBlbApplicationBackupAsync *)Parameter[104]);
    if ( (IsClientSKU & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 971, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      IsClientSKU = 0;
    }
  }
  IsClientSKU = BlbutilDuplicateString((const unsigned __int16 *)*Parameter[57], (unsigned __int16 **)Parameter + 58, 0);
  if ( (IsClientSKU & 0x80000000) != 0 )
    goto LABEL_356;
  IsClientSKU = CBlbComponentBackupHelper::Initialize(
                  (CBlbComponentBackupHelper *)Parameter[101],
                  (const struct _SPP_METADATA_PROP *)Parameter[57],
                  v146,
                  (const struct _SPP_GROUP_PROP *)*v67);
  if ( (IsClientSKU & 0x80000000) != 0 )
  {
    v73 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v74 = 972;
      goto LABEL_355;
    }
    goto LABEL_356;
  }
  CBlbComponentBackupHelper::MarkExplicitlyIncludedComponents((CBlbComponentBackupHelper *)Parameter[101], v148, v156);
  GetSystemTimeAsFileTime((LPFILETIME)Parameter + 78);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v75 = BLB_TIME_DIFF((struct _FILETIME *)Parameter + 77, (struct _FILETIME *)Parameter + 78);
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 973, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v75);
  }
  if ( v135[0] )
  {
    IsClientSKU = CBlbBackupAsync::LogFailedSnapshotComponents((CBlbBackupAsync *)Parameter, v144[0], v149);
    if ( (IsClientSKU & 0x80000000) != 0 )
    {
      v73 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_356;
      }
      v74 = 974;
      goto LABEL_355;
    }
  }
  IsClientSKU = CBlbBackupAsync::SetVolumeSnapshotIds((CBlbBackupAsync *)Parameter);
  if ( (IsClientSKU & 0x80000000) != 0 )
    goto LABEL_356;
  if ( v131 || ((*((_DWORD *)Parameter + 84) - 1) & 0xFFFFFFFB) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 975, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
  }
  else
  {
    CBlbBackupAsync::GetPostSnapshotUSNInfo((CBlbBackupAsync *)Parameter);
  }
  if ( !v131 )
  {
    IsClientSKU = CBlbComponentBackupHelper::IsAnyComponentRequiresConsistencyCheck(
                    (CBlbComponentBackupHelper *)Parameter[101],
                    v141);
    if ( (IsClientSKU & 0x80000000) != 0 )
    {
      v73 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_356;
      }
      v74 = 976;
      goto LABEL_355;
    }
    if ( v141[0] )
      CBlbBackupAsync::SetState(Parameter, 3);
    IsClientSKU = CBlbComponentBackupHelper::CheckAppConsistency((CBlbComponentBackupHelper *)Parameter[101]);
    if ( (IsClientSKU & 0x80000000) != 0 )
    {
      v73 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_356;
      }
      v74 = 977;
      goto LABEL_355;
    }
    IsClientSKU = CBlbBackupAsync::PublishAppConsistencyEvents((CBlbBackupAsync *)Parameter);
    if ( (IsClientSKU & 0x80000000) != 0 )
    {
      v73 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_356;
      }
      v74 = 978;
      goto LABEL_355;
    }
    if ( !v131 && (unsigned int)(*((_DWORD *)Parameter + 84) - 2) <= 2 )
    {
      v76 = (__int64 (__fastcall *)(_QWORD **, GUID *, _QWORD *))**Parameter;
      v77 = ATL::CComPtrBase<IRegisteredTask>::operator&(&v151);
      IsClientSKU = v76(Parameter, &IID_IBlbsrvReclaimSpaceCallback, v77);
      if ( (IsClientSKU & 0x80000000) != 0 )
      {
        v73 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_356;
        }
        v74 = 979;
LABEL_355:
        WPP_SF_d(v73[2], v74, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        goto LABEL_356;
      }
    }
  }
  IsClientSKU = CBlbBackupAsync::AddBackupSetToLocalCatalog(
                  (CBlbBackupAsync *)Parameter,
                  (struct _BLBCAT_BACKUP_SET_INFO **)&v143);
  if ( (IsClientSKU & 0x80000000) != 0 )
    goto LABEL_356;
  IsClientSKU = CBlbBackupAsync::GetComponentsList(
                  (CBlbBackupAsync *)Parameter,
                  (struct _BLBCAT_COMPONENT_INFO **)v143[5].Data4,
                  &v143[5].Data1);
  if ( (IsClientSKU & 0x80000000) != 0 )
    goto LABEL_356;
  if ( *((_DWORD *)Parameter + 92) )
  {
    IsClientSKU = CBlbBackupAsync::PostInitializeVolumes(
                    (CBlbBackupAsync *)Parameter,
                    (struct _BLBCAT_BACKUP_SET_INFO *)v143,
                    (unsigned __int16 *)Parameter[43],
                    v151);
    if ( (IsClientSKU & 0x80000000) != 0 )
      goto LABEL_356;
    IsClientSKU = CBlbBackupAsync::GetVolumesList(
                    (CBlbBackupAsync *)Parameter,
                    (struct _BLBCAT_VOLUME_INFO **)v143[4].Data4,
                    &v143[4].Data1);
    if ( (IsClientSKU & 0x80000000) != 0 )
      goto LABEL_356;
  }
  if ( *((_BYTE *)Parameter + 390) )
  {
    if ( !Parameter[103] )
      BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x5913u, "pContext->m_pSSBContext");
    v78 = (CBlbFileAsync *)Parameter[103];
    v163 = v78;
    if ( !(*(unsigned __int8 (__fastcall **)(CBlbFileAsync *))(*(_QWORD *)v78 + 96LL))(v78) )
    {
      v79 = BlbutilCheckTestHook(L"ExcludeSystemFiles");
      IsClientSKU = BlbCheckVolumesHavingSystemState(
                      (struct CBlbEngine *)Parameter[10],
                      (struct _BLBCAT_BACKUP_SET_INFO *)v143,
                      1,
                      1u,
                      0,
                      &v158);
      if ( (IsClientSKU & 0x80000000) != 0 )
        goto LABEL_356;
      IsClientSKU = CBlbSystemStateBackupAsync::PostInitialize(
                      v78,
                      (unsigned __int16 *)Parameter[43],
                      (struct _SPP_METADATA_PROP *)Parameter[57],
                      v79,
                      (struct _BLBCAT_BACKUP_SET_INFO *)v143,
                      (struct _FILETIME)Parameter[49],
                      v151);
      if ( (IsClientSKU & 0x80000000) != 0 )
      {
        CBlbSystemStateBackupAsync::SetState(v78, 5);
        (*(void (__fastcall **)(CBlbFileAsync *, __int64, _QWORD))(*(_QWORD *)v78 + 64LL))(
          v78,
          2155347997LL,
          IsClientSKU);
        goto LABEL_356;
      }
    }
  }
  if ( *((_DWORD *)Parameter + 92)
    && (IsClientSKU = CBlbBackupAsync::PopulateVolumeMap(
                        (CBlbBackupAsync *)Parameter,
                        v143[4].Data1,
                        *(struct _BLBCAT_VOLUME_INFO **)v143[4].Data4,
                        (struct _BLBSRV_VOLUME_MAP **)Parameter + 105,
                        (BSTR)Parameter + 424),
        (IsClientSKU & 0x80000000) != 0)
    || !v131
    && ((IsClientSKU = CBlbBackupAsync::CheckIfVolumeSpecsChanged((CBlbBackupAsync *)Parameter),
         (IsClientSKU & 0x80000000) != 0)
     || (IsClientSKU = CBlbBackupAsync::InitializePredefinedExclusions((CBlbBackupAsync *)Parameter),
         (IsClientSKU & 0x80000000) != 0))
    || (IsClientSKU = CBlbImpersonationHelper::ImpersonateCaller((CBlbImpersonationHelper *)(Parameter + 5), 0),
        (IsClientSKU & 0x80000000) != 0) )
  {
LABEL_356:
    v8 = v130;
    v5 = v130;
LABEL_357:
    v6 = v8;
    goto LABEL_574;
  }
  v80 = (CBlbMediaBackupContext *)operator new(0x48u);
  *(_QWORD *)&v154.Data1 = v80;
  if ( v80 )
    v5 = CBlbMediaBackupContext::CBlbMediaBackupContext(v80, (struct CBlbBackupAsync *)Parameter);
  v126 = v5;
  if ( !v5 )
  {
    IsClientSKU = -2147024882;
    v8 = v130;
    goto LABEL_357;
  }
  v81 = (CBlbMediaBackupContext *)operator new(0x48u);
  *(_QWORD *)&v154.Data1 = v81;
  if ( v81 )
    v8 = CBlbMediaBackupContext::CBlbMediaBackupContext(v81, v5);
  else
    v8 = 0;
  v130 = v8;
  if ( !v8 )
  {
    IsClientSKU = -2147024882;
    goto LABEL_573;
  }
  v82 = 0;
  v83 = (char *)Parameter + 340;
  while ( 2 )
  {
    v84 = v124;
LABEL_430:
    if ( *((_DWORD *)v126 + 2) >= v84 )
    {
      if ( !*((_BYTE *)Parameter + 391) || (v83 = (char *)Parameter + 340, v82) )
      {
        if ( !CBlbBackupAsync::HasOverallBackupSucceeded((CBlbBackupAsync *)Parameter) )
        {
          IsClientSKU = *((_DWORD *)Parameter + 8);
          goto LABEL_523;
        }
        CBlbAsync::SetResult((CBlbAsync *)(Parameter + 3), 0, 0, 0);
        if ( (*v83 & 8) != 0 )
        {
          IsClientSKU = CBlbBackupAsync::PrepareForTargetSnapshot((CBlbBackupAsync *)Parameter, &v157, &Data1);
          if ( (IsClientSKU & 0x80000000) != 0 )
            goto LABEL_523;
        }
        v96 = v143;
        if ( *(_DWORD *)v143[11].Data4 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 993, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            v96 = v143;
          }
          IsClientSKU = CSPPMetadataManager::SaveMetadataToSystemVolume(v96);
          if ( (IsClientSKU & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 994, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            }
            goto LABEL_523;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 995, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
        IsClientSKU = CBlbImpersonationHelper::ImpersonateCaller((CBlbImpersonationHelper *)(Parameter + 5), 0);
        if ( (IsClientSKU & 0x80000000) != 0 )
        {
LABEL_523:
          v8 = v130;
          v5 = v126;
          goto LABEL_573;
        }
        IsClientSKU = CBlbBackupAsync::MergeLocalCatalog((CBlbBackupAsync *)Parameter);
        if ( (IsClientSKU & 0x80000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 996, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          }
          goto LABEL_523;
        }
        CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)(Parameter + 5));
        v97 = *(_DWORD *)v83;
        if ( (*(_DWORD *)v83 & 2) == 0 )
        {
          IsClientSKU = CBlbBackupAsync::DismountAllVHDs((CBlbBackupAsync *)Parameter);
          if ( (IsClientSKU & 0x80000000) != 0 )
            goto LABEL_523;
          v97 = *(_DWORD *)v83;
        }
        if ( (v97 & 8) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 997, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          }
          GetSystemTimeAsFileTime((LPFILETIME)Parameter + 79);
          LODWORD(v7) = v124;
          IsClientSKU = CBlbBackupAsync::DoTargetSnapshot((CBlbBackupAsync *)Parameter, v157, v128, v124, &Data1);
          GetSystemTimeAsFileTime((LPFILETIME)Parameter + 80);
          if ( (IsClientSKU & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 998, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            }
            CBlbBackupAsync::DeleteSppMetadataFile((CBlbBackupAsync *)Parameter, (struct _GUID *)(Parameter + 37), 1u);
            CBlbBackupAsync::DeleteBackupSetFromGlobalCatalog((CBlbBackupAsync *)Parameter);
            goto LABEL_560;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v98 = BLB_TIME_DIFF((struct _FILETIME *)Parameter + 79, (struct _FILETIME *)Parameter + 80);
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 999, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v98);
          }
        }
        else
        {
          LODWORD(v7) = v124;
        }
        IsClientSKU = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&v165.Data1 + 216LL))(*(_QWORD *)&v165.Data1);
        if ( (IsClientSKU & 0x80000000) == 0 )
        {
          v8 = v130;
          v5 = v126;
          goto LABEL_692;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1000, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
LABEL_560:
        v8 = v130;
        v5 = v126;
        v6 = v127;
        v4 = v129;
        v3 = v128;
        goto LABEL_577;
      }
    }
    v85 = (char *)Parameter + 340;
    v8 = v130;
    if ( (*((_BYTE *)Parameter + 340) & 2) != 0 )
    {
      CBlbBackupAsync::RevertBackupToMedia((CBlbBackupAsync *)Parameter, v126, v130);
      if ( (int)PublishWaitingForShiningMediaEvent() < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 980, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
    }
    CBlbMediaBackupContext::operator=(v130, v126);
    if ( (*v85 & 2) == 0 )
    {
LABEL_453:
      if ( (*v85 & 0x20) != 0 && *((_BYTE *)Parameter + 496) )
      {
        CBlbBackupAsync::SetState(Parameter, 6);
        v87 = CBlbBackupAsync::FormatMedia(
                (CBlbBackupAsync *)Parameter,
                (unsigned __int16 *)Parameter[43],
                1u,
                0,
                &v133);
        IsClientSKU = v87;
        if ( v87 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v88 = L"TRUE";
            if ( !v133 )
              v88 = (const wchar_t *)L"FALSE";
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              982,
              (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              v87,
              (__int64)v88);
            v87 = IsClientSKU;
          }
          if ( !v133 || (*v85 & 2) == 0 )
            goto LABEL_572;
          v89 = -2139619258;
LABEL_465:
          CBlbAsync::SetResult((CBlbAsync *)(Parameter + 3), v89, v87, 0);
          v83 = (char *)Parameter + 340;
          continue;
        }
        if ( v133 )
          BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x59E5u, "!bTargetFailure");
      }
      CBlbBackupAsync::SetState(Parameter, 7);
      v90 = CBlbBackupAsync::PrepareMedia((CBlbBackupAsync *)Parameter, &v168, &Data1);
      IsClientSKU = v90;
      if ( v90 < 0 )
      {
        if ( v90 == -2147024882 )
          goto LABEL_641;
        if ( Data1 != -2147024882 && (*v85 & 2) != 0 )
        {
          v87 = 0;
          v89 = v90;
          goto LABEL_465;
        }
        if ( v90 == -2147024891 )
        {
          IsClientSKU = -2139619257;
        }
        else if ( v90 != -2139619225 )
        {
LABEL_641:
          if ( Data1 != -2147024891 )
          {
            IsClientSKU = -2139618951;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              ppv = Data1;
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 984, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            }
            goto LABEL_572;
          }
        }
        if ( (int)CBlbBackupAsync::PublishBackupTargetNotWritableEvent((CBlbBackupAsync *)Parameter) >= 0 )
          goto LABEL_572;
        v102 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_572;
        }
        v103 = 983;
        goto LABEL_652;
      }
      v91 = Parameter[59];
      if ( v91 )
      {
        CoTaskMemFree(v91);
        Parameter[59] = 0;
      }
      BackupSetDirectory = CBlbBackupAsync::CreateBackupSetDirectory((CBlbBackupAsync *)Parameter);
      IsClientSKU = BackupSetDirectory;
      if ( BackupSetDirectory < 0 )
      {
        if ( BackupSetDirectory == -2147024882 || (*v85 & 2) == 0 )
          goto LABEL_572;
        v87 = BackupSetDirectory;
        v89 = -2139619219;
        goto LABEL_465;
      }
      IsClientSKU = CBlbBackupAsync::FixVHDFileNamesIfNeeded((CBlbBackupAsync *)Parameter);
      if ( (IsClientSKU & 0x80000000) != 0 )
      {
        v102 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_572;
        }
        v103 = 985;
      }
      else
      {
        if ( (*v85 & 4) != 0
          && (int)CBlbBackupAsync::CleanupPreviousBackups((CBlbBackupAsync *)Parameter) < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 986, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
        CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)(Parameter + 5));
        IsClientSKU = CBlbBackupAsync::BackupLocalCatalog((CBlbBackupAsync *)Parameter);
        if ( (IsClientSKU & 0x80000000) == 0 )
        {
          if ( (*v85 & 2) == 0 && !v131 )
          {
            IsClientSKU = CBlbBackupAsync::DeleteVhdsIfRequired((CBlbBackupAsync *)Parameter);
            if ( (IsClientSKU & 0x80000000) != 0 )
              goto LABEL_572;
            IsClientSKU = CBlbBackupAsync::SetIncrementalBackupStatus((CBlbBackupAsync *)Parameter);
            if ( (IsClientSKU & 0x80000000) != 0 )
              goto LABEL_572;
            v93 = *((_DWORD *)Parameter + 58);
            CBlbBackupAsync::SetState(Parameter, 16);
            IsClientSKU = CBlbBackupAsync::PerformVHDPruning(
                            (CBlbBackupAsync *)Parameter,
                            (struct _BLBCAT_BACKUP_SET_INFO *)v143);
            if ( (IsClientSKU & 0x80000000) != 0 )
              goto LABEL_663;
            CBlbBackupAsync::SetState(Parameter, v93);
            v8 = v130;
          }
          if ( !CBlbAsync::CheckPoint((CBlbAsync *)(Parameter + 3)) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 988, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            }
            goto LABEL_638;
          }
          v132 = 0;
          if ( *((_DWORD *)Parameter + 92) )
          {
            IsClientSKU = CBlbBackupAsync::PerformVolumeBackup(
                            (CBlbBackupAsync *)Parameter,
                            &v168,
                            v128,
                            v124,
                            v126,
                            v8,
                            &v132,
                            &Data1);
            if ( (IsClientSKU & 0x80000000) != 0 )
              goto LABEL_572;
            v83 = (char *)Parameter + 340;
            if ( v132 )
              continue;
          }
          if ( *((_BYTE *)Parameter + 391) )
          {
            CBlbBackupAsync::SetState(Parameter, 19);
            IsClientSKU = CBlbApplicationBackupAsync::PrepareTarget(
                            v72,
                            *((_DWORD *)Parameter + 92),
                            (struct CBlbVolumeBackupContext *)Parameter[27],
                            (unsigned __int16 *)Parameter[59],
                            (struct CBlbImpersonationHelper *)(Parameter + 5));
            if ( (IsClientSKU & 0x80000000) != 0 )
              goto LABEL_663;
            v94 = CBlbBackupAsync::PerformApplicationBackup(
                    (CBlbBackupAsync *)Parameter,
                    (struct _BLBCAT_BACKUP_SET_INFO *)v143,
                    (struct _FILETIME)Parameter[49],
                    v151);
            IsClientSKU = v94;
            if ( v94 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 989, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
                v94 = IsClientSKU;
              }
              if ( v94 == -2139618978
                && (int)CBlbBackupAsync::OverrideErrorIfSourceDedup(Parameter, &IsClientSKU, 1) < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 990, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
              }
LABEL_663:
              v8 = v130;
              goto LABEL_572;
            }
            IsClientSKU = CBlbBackupAsync::WriteBackupMetadata((CBlbBackupAsync *)Parameter, &v133);
            if ( (IsClientSKU & 0x80000000) != 0 )
              goto LABEL_663;
            v145 = v168;
            IsClientSKU = CBlbApplicationBackupAsync::AddBagsToCatalog(
                            v72,
                            *((_DWORD *)Parameter + 92),
                            (struct CBlbVolumeBackupContext *)Parameter[27],
                            &v145,
                            (struct _FILETIME)Parameter[49]);
            if ( (IsClientSKU & 0x80000000) != 0 )
              goto LABEL_663;
            v82 = 1;
          }
          if ( *((_BYTE *)Parameter + 390) )
          {
            IsClientSKU = CBlbBackupAsync::PerformSystemStateBackup((CBlbBackupAsync *)Parameter, &v168);
            if ( (IsClientSKU & 0x80000000) != 0 )
              goto LABEL_663;
          }
          CBlbBackupAsync::UpdateBackupInfoIfRequired((CBlbBackupAsync *)Parameter, v143[12].Data4);
          v145 = *(struct _GUID *)(Parameter + 37);
          IsClientSKU = CBlbBackupAsync::AddMediaToLocalCatalog((CBlbBackupAsync *)Parameter, &v168, &v145);
          v8 = v130;
          if ( (IsClientSKU & 0x80000000) != 0 )
            goto LABEL_572;
          if ( *((_DWORD *)v130 + 2) == v124 && !v131 )
          {
            v95 = CBlbComponentBackupHelper::BackupComplete((CBlbComponentBackupHelper *)Parameter[101], 0);
            IsClientSKU = v95;
            if ( v95 < 0 )
            {
              Data1 = v95;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 991, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
              }
              IsClientSKU = -2139619153;
              goto LABEL_572;
            }
          }
          IsClientSKU = CBlbBackupAsync::WriteBackupComponents((CBlbBackupAsync *)Parameter, v146);
          if ( (IsClientSKU & 0x80000000) != 0 )
          {
            v102 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
            {
              goto LABEL_572;
            }
            v103 = 992;
            goto LABEL_652;
          }
          if ( *((_DWORD *)v130 + 2) != v124 )
          {
LABEL_514:
            IsClientSKU = CBlbBackupAsync::CloseMedia((CBlbBackupAsync *)Parameter, &v132);
            if ( (IsClientSKU & 0x80000000) != 0 )
              goto LABEL_572;
            v83 = (char *)Parameter + 340;
            v84 = v124;
            if ( !v132 )
            {
              IsClientSKU = CBlbBackupAsync::DoVerification((CBlbBackupAsync *)Parameter, &v132);
              if ( (IsClientSKU & 0x80000000) != 0 )
                goto LABEL_663;
              v84 = v124;
              if ( !v132 )
              {
                CBlbMediaBackupContext::operator=(v126, v130);
                ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(Parameter + 63, &v168);
                v84 = v124;
                if ( *((_DWORD *)v126 + 2) < v124 )
                {
                  CBlbAsync::SetResult((CBlbAsync *)(Parameter + 3), -2139619280, 0, 0);
                  v84 = v124;
                }
                v83 = (char *)Parameter + 340;
              }
            }
            goto LABEL_430;
          }
          IsClientSKU = CBlbBackupAsync::UpdateLocalCatalogAfterbackup(
                          (CBlbBackupAsync *)Parameter,
                          (struct _BLBCAT_BACKUP_SET_INFO *)v143,
                          &v132);
          if ( (IsClientSKU & 0x80000000) == 0 )
          {
            v83 = (char *)Parameter + 340;
            v84 = v124;
            if ( v132 )
              goto LABEL_430;
            v8 = v130;
            goto LABEL_514;
          }
          v5 = v126;
          LODWORD(v7) = v124;
LABEL_692:
          v3 = v128;
          v4 = v129;
          v6 = v127;
          goto LABEL_577;
        }
        v102 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_572;
        }
        v103 = 987;
      }
LABEL_652:
      WPP_SF_d(v102[2], v103, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      goto LABEL_572;
    }
    break;
  }
  if ( v127 )
    goto LABEL_450;
  v86 = (CBlbSuppressAutoPlay *)operator new(0x10u);
  *(_QWORD *)&v154.Data1 = v86;
  if ( v86 )
    v86 = CBlbSuppressAutoPlay::CBlbSuppressAutoPlay(v86);
  v127 = v86;
  if ( v86 )
  {
    IsClientSKU = CBlbSuppressAutoPlay::Initialize((struct IUnknown **)v86, (const unsigned __int16 *)Parameter[43]);
    if ( (IsClientSKU & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 981, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      IsClientSKU = 0;
    }
LABEL_450:
    while ( 1 )
    {
      Sleep(0x3E8u);
      if ( !CBlbAsync::CheckPoint((CBlbAsync *)(Parameter + 3)) )
        break;
      if ( CBlbBackupAsync::HasMediaArrived((CBlbBackupAsync *)Parameter) )
      {
        CBlbAsync::SetResult((CBlbAsync *)(Parameter + 3), 0, 0, 1u);
        goto LABEL_453;
      }
    }
    if ( !((unsigned __int8 (__fastcall *)(char *))Parameter[3][2])((char *)Parameter + 24) )
      BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x59BDu, "pContext->IsAborted()");
LABEL_638:
    IsClientSKU = -2139618969;
  }
  else
  {
    IsClientSKU = -2147024882;
  }
LABEL_572:
  v5 = v126;
LABEL_573:
  v6 = v127;
LABEL_574:
  v4 = v129;
LABEL_575:
  v3 = v128;
LABEL_576:
  LODWORD(v7) = v124;
LABEL_577:
  FreeComponents(&v156, &v148);
  if ( (int)CBlbBackupAsync::CopySkippedLogFileToTarget((CBlbBackupAsync *)Parameter) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1001, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  GetSystemTimeAsFileTime(&v161);
  if ( v6 )
    CBlbSuppressAutoPlay::`scalar deleting destructor'(v6, 1u);
  if ( v8 )
  {
    if ( v5 )
    {
      if ( *((_QWORD *)v8 + 6) == *((_QWORD *)v5 + 6) )
        *((_QWORD *)v8 + 6) = 0;
      if ( *((_QWORD *)v8 + 7) == *((_QWORD *)v5 + 7) )
        *((_QWORD *)v8 + 7) = 0;
    }
    CBlbMediaBackupContext::`scalar deleting destructor'(v8, 1u);
  }
  if ( v5 )
    CBlbMediaBackupContext::`scalar deleting destructor'(v5, 1u);
  CBlbBackupAsync::RemoveESPCache((CBlbBackupAsync *)Parameter);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v99 = BLB_TIME_DIFF(&SystemTimeAsFileTime, &v161);
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 1002, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v99);
  }
  if ( (*((_BYTE *)Parameter + 340) & 2) == 0
    && (int)CBlbBackupAsync::DismountAllVHDs((CBlbBackupAsync *)Parameter) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1003, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( (int)BlbDeleteOldBackupLogFiles() < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1004, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)(Parameter + 5));
  if ( (IsClientSKU & 0x80000000) != 0
    && !v131
    && (int)CBlbComponentBackupHelper::BackupComplete((CBlbComponentBackupHelper *)Parameter[101], 1u) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1005, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v100 = v137;
  if ( v137
    && v131
    && (*(int (__fastcall **)(struct ISharedProtectionPoints *))(*(_QWORD *)v146 + 120LL))(v146) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1006, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( (IsClientSKU & 0x80000000) == 0 && (*((_BYTE *)Parameter + 340) & 0xC) != 0 )
  {
    v101 = CBlbBackupAsync::DeleteNonExistingBackupSetsOnTarget((CBlbBackupAsync *)Parameter);
    if ( v101 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        1007,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (unsigned int)Parameter[43],
        v101);
    }
  }
  if ( v100
    && v138
    && (int)CBlbBackupAsync::DeleteSourceSnapshotsIfNeeded((CBlbBackupAsync *)Parameter, IsClientSKU) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1008, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( (int)CBlbBackupAsync::SetSourceDiffAreasIfNeeded((CBlbBackupAsync *)Parameter, 0) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1009, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( *((_BYTE *)Parameter + 388)
    && (int)CBlbBackupAsync::CheckForLowSpaceOnTarget((CBlbBackupAsync *)Parameter) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1010, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( !*((_BYTE *)Parameter + 1064)
    && (int)CBlbBackupAsync::ResetTargetDiffAreaSize((CBlbBackupAsync *)Parameter) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1011, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  SppFreeBadWritersArray(v144[0], &v149);
  if ( v157 )
    (*(void (__fastcall **)(struct IVssBackupComponents *))(*(_QWORD *)v157 + 16LL))(v157);
  if ( v4 )
  {
    BlbCleanupSppMetadata(v4);
    CoTaskMemFree(v4);
  }
  if ( v3 )
  {
    for ( k = 0; k < (unsigned int)v7; ++k )
    {
      v105 = v3[k];
      if ( v105 )
        CoTaskMemFree(v105);
    }
    CoTaskMemFree(v3);
  }
  v106 = pv;
  if ( pv )
  {
    v107 = 0;
    for ( m = v142; v107 < m; ++v107 )
    {
      v109 = (void *)v106[v107];
      if ( v109 )
      {
        CoTaskMemFree(v109);
        v106 = pv;
      }
    }
    CoTaskMemFree(v106);
  }
  if ( v152 )
    CoTaskMemFree(v152);
  if ( v158 )
  {
    CoTaskMemFree(v158);
    v158 = 0;
  }
  if ( v153[0] )
  {
    CoTaskMemFree(v153[0]);
    v153[0] = 0;
  }
  if ( v146 )
    (*(void (__fastcall **)(struct ISharedProtectionPoints *))(*(_QWORD *)v146 + 16LL))(v146);
  if ( v139 )
    CoUninitialize();
  if ( (IsClientSKU & 0x80000000) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 1013, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    CBlbBackupAsync::SetState(Parameter, 14);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 1014, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, Parameter);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1012, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    v142 = 0;
    v124 = 0;
    v145.Data1 = 0;
    LODWORD(v126) = 0;
    v110 = *((_BYTE *)Parameter + 391);
    if ( *((int *)Parameter + 8) < 0 )
    {
      if ( v110 )
      {
        if ( !Parameter[104] )
          BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x5CD8u, "pContext->m_pAppBackupContext");
        CBlbApplicationBackupAsync::GetError((CBlbApplicationBackupAsync *)Parameter[104], &v142, (int *)&v124);
        CBlbApplicationBackupAsync::SetState(Parameter[104], 5);
        if ( v142 >= 0 )
          (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*Parameter[104] + 64LL))(
            Parameter[104],
            *((unsigned int *)Parameter + 8),
            *((unsigned int *)Parameter + 9));
      }
      if ( *((_BYTE *)Parameter + 390) )
      {
        if ( !Parameter[103] )
          BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x5CE5u, "pContext->m_pSSBContext");
        CBlbSystemStateBackupAsync::GetError((CBlbSystemStateBackupAsync *)Parameter[103], (int *)&v145, (int *)&v126);
        CBlbSystemStateBackupAsync::SetState(Parameter[103], 5);
        if ( (v145.Data1 & 0x80000000) == 0 )
          (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*Parameter[103] + 64LL))(
            Parameter[103],
            *((unsigned int *)Parameter + 8),
            *((unsigned int *)Parameter + 9));
      }
      v113 = *((_DWORD *)Parameter + 9);
      v114 = *((_DWORD *)Parameter + 8);
    }
    else
    {
      if ( !v110 )
        goto LABEL_749;
      if ( !Parameter[104] )
        BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x5C9Eu, "pContext->m_pAppBackupContext");
      CBlbApplicationBackupAsync::SetState(Parameter[104], 5);
      (*(void (__fastcall **)(_QWORD *, __int64, _QWORD))(*Parameter[104] + 64LL))(
        Parameter[104],
        2155347997LL,
        (unsigned int)Data1);
      if ( *((_BYTE *)Parameter + 390) )
        goto LABEL_827;
      if ( !*((_DWORD *)Parameter + 92) )
      {
        CBlbApplicationBackupAsync::GetError((CBlbApplicationBackupAsync *)Parameter[104], &v142, (int *)&v124);
        if ( v142 < 0 )
          Data1 = v142;
      }
LABEL_749:
      if ( *((_BYTE *)Parameter + 390) )
      {
LABEL_827:
        if ( !Parameter[103] )
          BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x5CB3u, "pContext->m_pSSBContext");
        CBlbSystemStateBackupAsync::SetState(Parameter[103], 5);
        (*(void (__fastcall **)(_QWORD *, __int64, _QWORD))(*Parameter[103] + 64LL))(
          Parameter[103],
          2155347997LL,
          (unsigned int)Data1);
        v111 = 0;
        for ( n = 0; n < *((_DWORD *)Parameter + 92); ++n )
        {
          if ( (Parameter[27][46 * n + 10] & 0x2000000000LL) == 0 )
          {
            v111 = 1;
            break;
          }
        }
        if ( !*((_BYTE *)Parameter + 391) && !v111 )
        {
          CBlbSystemStateBackupAsync::GetError((CBlbSystemStateBackupAsync *)Parameter[103], (int *)&v145, (int *)&v126);
          if ( (v145.Data1 & 0x80000000) != 0 )
            Data1 = v145.Data1;
        }
      }
      v113 = Data1;
      v114 = IsClientSKU;
    }
    CBlbBackupAsync::SetAborted((CBlbBackupAsync *)Parameter, v114, v113);
    CBlbBackupAsync::CleanupAbort((CBlbBackupAsync *)Parameter);
    v115 = 0;
    if ( (_DWORD)v7 )
    {
      while ( 2 )
      {
        v116 = (CBlbVolumeBackupContext *)&Parameter[27][46 * v115];
        if ( *((_DWORD *)v116 + 5) == 15 )
        {
          v117 = -2139619228;
          goto LABEL_780;
        }
        if ( *((_DWORD *)v116 + 5) != 14 && *((int *)v116 + 8) >= 0 )
        {
          v117 = *((_DWORD *)Parameter + 8);
          if ( v117 >= 0 )
            v117 = -2139619299;
LABEL_780:
          CBlbVolumeBackupContext::SetResult(v116, v117, 0);
        }
        if ( ++v115 >= (unsigned int)v7 )
          break;
        continue;
      }
    }
  }
  if ( v131 )
  {
    v118 = *((_DWORD *)Parameter + 8);
    LODWORD(v170) = v118 >= 0;
    LODWORD(v172) = 1;
    LODWORD(v174) = *((_DWORD *)Parameter + 9);
    LODWORD(v176) = v118;
    WinSqmAddToStream(0, 4248, 4, &v169, ppv);
  }
  if ( v143 )
  {
    FreeBackupSetContents((struct _BLBCAT_BACKUP_SET_INFO *)v143);
    if ( v143 )
    {
      CoTaskMemFree(v143);
      v143 = 0;
    }
  }
  if ( (int)CBlbBackupAsync::PublishAllBackupStopEvents((CBlbBackupAsync *)Parameter, IsClientSKU, v140) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1015, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( !v131 )
    CBlbBackupAsync::GenerateWERIfRequired((CBlbBackupAsync *)Parameter);
  if ( (int)CBlbBackupAsync::UpdateBackupStatInRegistry((CBlbBackupAsync *)Parameter) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1016, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( v163 )
    CBlbFileAsync::Uninitialize(v163);
  for ( ii = 0; ii < (unsigned int)v7; ++ii )
  {
    v120 = (CBlbFileAsync *)Parameter[27][46 * ii + 27];
    if ( v120 )
      CBlbFileAsync::Uninitialize(v120);
  }
  CBlbAsync::Done((CBlbAsync *)(Parameter + 3));
  ((void (__fastcall *)(_QWORD **))(*Parameter)[2])(Parameter);
  if ( SetThreadExecutionState(0x80000000) )
  {
LABEL_819:
    v121 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_820;
  }
  v121 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 1017, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      goto LABEL_819;
    }
LABEL_820:
    if ( v121 != &WPP_GLOBAL_Control && (*((_BYTE *)v121 + 28) & 1) != 0 && *((_BYTE *)v121 + 25) >= 4u )
      WPP_SF_(v121[2], 1018, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  TraceLoggingUnregister_EventUnregister(&dword_14015E050);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v151);
  CBlbObjectLock<CBlbBackupAsync>::~CBlbObjectLock<CBlbBackupAsync>(v166);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v159);
  return 0;
}

```

## disassembly

```asm
0x140019fd0  push    rbp
0x140019fd2  push    rbx
0x140019fd3  push    rsi
0x140019fd4  push    rdi
0x140019fd5  push    r12
0x140019fd7  push    r13
0x140019fd9  push    r14
0x140019fdb  push    r15
0x140019fdd  lea     rbp, [rsp-1F8h]
0x140019fe5  sub     rsp, 2F8h
0x140019fec  mov     rax, cs:__security_cookie
0x140019ff3  xor     rax, rsp
0x140019ff6  mov     [rbp+230h+var_50], rax
0x140019ffd  mov     rdi, rcx
0x14001a000  lea     rax, WPP_GLOBAL_Control
0x14001a007  mov     r15d, 1
0x14001a00d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a014  cmp     rcx, rax
0x14001a017  jz      short loc_14001A03A
0x14001a019  test    [rcx+1Ch], r15b
0x14001a01d  jz      short loc_14001A03A
0x14001a01f  cmp     byte ptr [rcx+19h], 4
0x14001a023  jb      short loc_14001A03A
0x14001a025  mov     edx, 39Dh
0x14001a02a  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001a031  mov     rcx, [rcx+10h]
0x14001a035  call    WPP_SF_
0x14001a03a  xor     r12d, r12d
0x14001a03d  mov     [rsp+330h+var_2BC], r12d
0x14001a042  mov     [rbp+230h+var_288], r12d
0x14001a046  mov     [rbp+230h+var_28E], r12b
0x14001a04a  lea     rcx, [rdi+18h]; this
0x14001a04e  call    ?GetCatalog@CBlbAsync@@QEAAPEAUIBLBCatalogSystem@@XZ; CBlbAsync::GetCatalog(void)
0x14001a053  mov     rbx, rax
0x14001a056  mov     qword ptr [rbp+230h+var_1A0.Data1], rax
0x14001a05d  mov     [rbp+230h+var_282], r12b
0x14001a061  mov     [rbp+230h+var_250], r12
0x14001a065  mov     esi, r12d
0x14001a068  mov     [rbp+230h+pv], r12
0x14001a06c  mov     [rbp+230h+var_27C], r12d
0x14001a070  mov     r13d, r12d
0x14001a073  xorps   xmm0, xmm0
0x14001a076  movups  [rbp+230h+var_1B8], xmm0
0x14001a07a  mov     [rbp+230h+var_284], r12b
0x14001a07e  mov     [rbp+230h+var_283], r12b
0x14001a082  mov     [rbp+230h+var_280], r12b
0x14001a086  movups  xmmword ptr [rbp+230h+var_170.Data1], xmm0
0x14001a08d  mov     r14d, r12d
0x14001a090  mov     [rbp+230h+var_298], r12
0x14001a094  mov     [rbp+230h+var_1F0], r12
0x14001a098  mov     [rbp+230h+var_281], r12b
0x14001a09c  mov     [rbp+230h+var_228], r12
0x14001a0a0  mov     [rbp+230h+var_278], r12
0x14001a0a4  mov     [rbp+230h+var_1C0], r12
0x14001a0a8  mov     qword ptr [rbp+230h+SystemTimeAsFileTime.dwLowDateTime], r12
0x14001a0ac  mov     qword ptr [rbp+230h+var_1D0.dwLowDateTime], r12
0x14001a0b0  mov     [rbp+230h+var_290], r12b
0x14001a0b4  mov     [rbp+230h+var_160], r15d
0x14001a0bb  mov     [rbp+230h+var_158], r12
0x14001a0c2  mov     [rbp+230h+var_150], r15d
0x14001a0c9  mov     [rbp+230h+var_148], r12
0x14001a0d0  mov     [rbp+230h+var_140], r15d
0x14001a0d7  mov     [rbp+230h+var_138], r12
0x14001a0de  mov     [rbp+230h+var_130], r15d
0x14001a0e5  mov     [rbp+230h+var_128], r12
0x14001a0ec  mov     [rbp+230h+var_1E8], r12
0x14001a0f0  mov     [rbp+230h+var_1E0], r12
0x14001a0f4  lea     rax, ??_7?$CBlbObjectLock@VCBlbBackupAsync@@@@6B@; const CBlbObjectLock<CBlbBackupAsync>::`vftable'
0x14001a0fb  mov     [rbp+230h+var_190], rax
0x14001a102  mov     [rbp+230h+var_188], rdi
0x14001a109  mov     [rbp+230h+var_180], r12b
0x14001a110  xor     edx, edx
0x14001a112  lea     rcx, [rbp+230h+var_230]
0x14001a116  call    ??0?$CComPtrBase@UIBlbsrvReclaimSpaceCallback@@@ATL@@IEAA@H@Z; ATL::CComPtrBase<IBlbsrvReclaimSpaceCallback>::CComPtrBase<IBlbsrvReclaimSpaceCallback>(int)
0x14001a11b  nop
0x14001a11c  mov     r15d, r12d
0x14001a11f  mov     [rbp+230h+var_2B0], r12
0x14001a123  mov     [rbp+230h+var_28C], r12b
0x14001a127  mov     [rbp+230h+var_240], r12
0x14001a12b  mov     [rbp+230h+var_270], r12d
0x14001a12f  mov     [rbp+230h+var_1F8], r12
0x14001a133  mov     [rbp+230h+var_244], r12d
0x14001a137  mov     r12d, [rdi+170h]
0x14001a13e  mov     [rsp+330h+var_2C0], r12d
0x14001a143  xor     eax, eax
0x14001a145  mov     [rbp+230h+var_248], eax
0x14001a148  mov     [rbp+230h+var_200], rax
0x14001a14c  mov     [rbp+230h+var_220], rax
0x14001a150  xor     r8d, r8d
0x14001a153  xor     edx, edx
0x14001a155  lea     rcx, dword_14015E050
0x14001a15c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14001a161  lea     rcx, [rbp+230h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14001a165  call    cs:__imp_GetSystemTimeAsFileTime
0x14001a16b  mov     ecx, 80000001h; esFlags
0x14001a170  call    cs:__imp_SetThreadExecutionState
0x14001a176  test    eax, eax
0x14001a178  jnz     short loc_14001A1AE
0x14001a17a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a181  lea     rax, WPP_GLOBAL_Control
0x14001a188  cmp     rcx, rax
0x14001a18b  jz      short loc_14001A1AE
0x14001a18d  test    byte ptr [rcx+1Ch], 1
0x14001a191  jz      short loc_14001A1AE
0x14001a193  cmp     byte ptr [rcx+19h], 3
0x14001a197  jb      short loc_14001A1AE
0x14001a199  mov     edx, 39Eh
0x14001a19e  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001a1a5  mov     rcx, [rcx+10h]
0x14001a1a9  call    WPP_SF_
0x14001a1ae  movups  xmm0, xmmword ptr [rdi+128h]
0x14001a1b5  movdqu  xmmword ptr [rbp+230h+var_210.Data1], xmm0
0x14001a1ba  movzx   edx, byte ptr [rdi+186h]; int
0x14001a1c1  lea     rcx, [rbp+230h+var_210]; struct _GUID
0x14001a1c5  call    ?PublishBackupStartEvent@@YAJU_GUID@@H@Z; PublishBackupStartEvent(_GUID,int)
0x14001a1ca  test    eax, eax
0x14001a1cc  jns     short loc_14001A205
0x14001a1ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a1d5  lea     rdx, WPP_GLOBAL_Control
0x14001a1dc  cmp     rcx, rdx
0x14001a1df  jz      short loc_14001A205
0x14001a1e1  test    byte ptr [rcx+1Ch], 1
0x14001a1e5  jz      short loc_14001A205
0x14001a1e7  cmp     byte ptr [rcx+19h], 2
0x14001a1eb  jb      short loc_14001A205
0x14001a1ed  mov     edx, 39Fh
0x14001a1f2  mov     r9d, eax
0x14001a1f5  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001a1fc  mov     rcx, [rcx+10h]
0x14001a200  call    WPP_SF_d
0x14001a205  lea     rcx, [rbp+230h+var_290]; unsigned __int8 *
0x14001a209  call    ?BlbutilIsClientSKU@@YAJPEAE@Z; BlbutilIsClientSKU(uchar *)
0x14001a20e  mov     [rsp+330h+var_2BC], eax
0x14001a212  test    eax, eax
0x14001a214  jns     short loc_14001A255
0x14001a216  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a21d  lea     rdx, WPP_GLOBAL_Control
0x14001a224  cmp     rcx, rdx
0x14001a227  jz      short loc_14001A24D
0x14001a229  test    byte ptr [rcx+1Ch], 1
0x14001a22d  jz      short loc_14001A24D
0x14001a22f  cmp     byte ptr [rcx+19h], 2
0x14001a233  jb      short loc_14001A24D
0x14001a235  mov     edx, 3A0h
0x14001a23a  mov     r9d, eax
0x14001a23d  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001a244  mov     rcx, [rcx+10h]
0x14001a248  call    WPP_SF_d
0x14001a24d  mov     rbx, r15
0x14001a250  jmp     loc_14001C570
0x14001a255  mov     rax, [rbx]
0x14001a258  lea     rdx, [rdi+190h]
0x14001a25f  mov     rcx, rbx
0x14001a262  mov     rax, [rax+88h]
0x14001a269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a26e  mov     [rsp+330h+var_2BC], eax
0x14001a272  test    eax, eax
0x14001a274  jns     short loc_14001A2AF
0x14001a276  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a27d  lea     rdx, WPP_GLOBAL_Control
0x14001a284  cmp     rcx, rdx
0x14001a287  jz      short loc_14001A24D
0x14001a289  test    byte ptr [rcx+1Ch], 1
0x14001a28d  jz      short loc_14001A24D
0x14001a28f  cmp     byte ptr [rcx+19h], 2
0x14001a293  jb      short loc_14001A24D
0x14001a295  mov     edx, 3A1h
0x14001a29a  mov     r9d, eax
0x14001a29d  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001a2a4  mov     rcx, [rcx+10h]
0x14001a2a8  call    WPP_SF_d
0x14001a2ad  jmp     short loc_14001A24D
0x14001a2af  xor     edx, edx; dwCoInit
0x14001a2b1  xor     ecx, ecx; pvReserved
0x14001a2b3  call    cs:__imp_CoInitializeEx
0x14001a2b9  mov     [rsp+330h+var_2BC], eax
0x14001a2bd  test    eax, eax
0x14001a2bf  jns     short loc_14001A2F3
0x14001a2c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a2c8  lea     rdx, WPP_GLOBAL_Control
0x14001a2cf  cmp     rcx, rdx
0x14001a2d2  jz      loc_14001A24D
0x14001a2d8  test    byte ptr [rcx+1Ch], 1
0x14001a2dc  jz      loc_14001A24D
0x14001a2e2  cmp     byte ptr [rcx+19h], 2
0x14001a2e6  jb      loc_14001A24D
0x14001a2ec  mov     edx, 3A2h
0x14001a2f1  jmp     short loc_14001A29A
0x14001a2f3  mov     [rbp+230h+var_282], 1
0x14001a2f7  mov     r13, r12
0x14001a2fa  shl     r13, 3
0x14001a2fe  mov     rcx, r13; cb
0x14001a301  call    cs:__imp_CoTaskMemAlloc
0x14001a307  mov     rsi, rax
0x14001a30a  mov     [rbp+230h+var_2A8], rax
0x14001a30e  test    rax, rax
0x14001a311  jnz     short loc_14001A326
0x14001a313  mov     [rsp+330h+var_2BC], 8007000Eh
0x14001a31b  mov     rbx, r15
0x14001a31e  mov     r13, rbx
0x14001a321  jmp     loc_14001C570
0x14001a326  mov     r8, r13; Size
0x14001a329  xor     edx, edx; Val
0x14001a32b  mov     rcx, rax; void *
0x14001a32e  call    memset_0
0x14001a333  xor     r12d, r12d
0x14001a336  mov     ebx, [rsp+330h+var_2C0]
0x14001a33a  cmp     r12d, ebx
0x14001a33d  jnb     loc_14001A688
0x14001a343  mov     edx, r12d
0x14001a346  imul    rcx, rdx, 170h
0x14001a34d  mov     r14, [rdi+0D8h]
0x14001a354  add     r14, rcx
0x14001a357  lea     rsi, [rsi+r12*8]
0x14001a35b  mov     r9b, 1; unsigned __int8
0x14001a35e  mov     r8, rsi; unsigned __int16 **
0x14001a361  mov     edx, [r14+54h]; unsigned int
0x14001a365  lea     rcx, [r14+44h]; struct _GUID *
0x14001a369  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x14001a36e  mov     [rsp+330h+var_2BC], eax
0x14001a372  test    eax, eax
0x14001a374  js      loc_14001A640
0x14001a37a  mov     [rbp+230h+var_28F], r15b
0x14001a37e  lea     r8, [rbp+230h+var_28F]; unsigned __int8 *
0x14001a382  mov     edx, [r14+54h]; unsigned int
0x14001a386  mov     rcx, [rsi]; unsigned __int16 *
0x14001a389  call    ?BlbIsVolumeValid@@YAJPEAGKPEAE@Z; BlbIsVolumeValid(ushort *,ulong,uchar *)
0x14001a38e  mov     ebx, eax
0x14001a390  test    eax, eax
0x14001a392  jns     loc_14001A4AE
0x14001a398  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a39f  lea     rax, WPP_GLOBAL_Control
0x14001a3a6  cmp     rcx, rax
0x14001a3a9  jz      loc_14001A4AE
0x14001a3af  test    byte ptr [rcx+1Ch], 1
0x14001a3b3  jz      loc_14001A4AE
0x14001a3b9  cmp     byte ptr [rcx+19h], 2
0x14001a3bd  jb      loc_14001A4AE
0x14001a3c3  mov     edx, 3A4h
0x14001a3c8  mov     dword ptr [rsp+330h+ppv], ebx
0x14001a3cc  mov     r9, [rsi]
0x14001a3cf  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001a3d6  mov     rcx, [rcx+10h]
0x14001a3da  call    WPP_SF_Sd
0x14001a3df  mov     [rbp+230h+var_260.Data1], r15d
0x14001a3e3  cmp     ebx, 80070002h
0x14001a3e9  jnz     short loc_14001A45A
0x14001a3eb  lea     r9, [rbp+230h+var_228]
0x14001a3ef  mov     r8d, 2
0x14001a3f5  mov     edx, [r14+54h]
0x14001a3f9  lea     rcx, [r14+44h]
0x14001a3fd  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAU_GUID@@KW4_BLB_MEDIA_TYPE@@PEAPEAG@Z; GetVolumeFriendlyNameForPublisher(_GUID *,ulong,_BLB_MEDIA_TYPE,ushort * *)
0x14001a402  test    eax, eax
0x14001a404  js      short loc_14001A45A
0x14001a406  mov     rdx, [rsi]; unsigned __int16 *
0x14001a409  mov     rcx, [rbp+230h+var_228]; unsigned __int16 *
0x14001a40d  call    ?PublishProtectedVolumeMissingEvent@@YAJPEAG0@Z; PublishProtectedVolumeMissingEvent(ushort *,ushort *)
0x14001a412  test    eax, eax
0x14001a414  jns     short loc_14001A45A
0x14001a416  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a41d  lea     rdx, WPP_GLOBAL_Control
0x14001a424  cmp     rcx, rdx
0x14001a427  jz      short loc_14001A45A
0x14001a429  test    byte ptr [rcx+1Ch], 1
0x14001a42d  jz      short loc_14001A45A
0x14001a42f  cmp     byte ptr [rcx+19h], 2
0x14001a433  jb      short loc_14001A45A
0x14001a435  mov     edx, 3A8h
0x14001a43a  mov     [rsp+330h+var_308.dwLowDateTime], eax
0x14001a43e  mov     rax, [rsi]
0x14001a441  mov     [rsp+330h+ppv], rax
0x14001a446  mov     r9, [rbp+230h+var_228]
0x14001a44a  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001a451  mov     rcx, [rcx+10h]
0x14001a455  call    WPP_SF_SSD
0x14001a45a  xor     r8d, r8d; int
0x14001a45d  mov     edx, ebx; int
0x14001a45f  mov     rcx, r14; this
0x14001a462  call    ?SetAborted@CBlbVolumeBackupContext@@QEAAXJJ@Z; CBlbVolumeBackupContext::SetAborted(long,long)
0x14001a467  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a46e  lea     rax, WPP_GLOBAL_Control
0x14001a475  cmp     rcx, rax
0x14001a478  jz      short loc_14001A4A2
0x14001a47a  test    byte ptr [rcx+1Ch], 1
0x14001a47e  jz      short loc_14001A4A2
0x14001a480  cmp     byte ptr [rcx+19h], 3
0x14001a484  jb      short loc_14001A4A2
0x14001a486  mov     edx, 3A9h
0x14001a48b  mov     dword ptr [rsp+330h+ppv], ebx
0x14001a48f  mov     r9, [rsi]
0x14001a492  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001a499  mov     rcx, [rcx+10h]
0x14001a49d  call    WPP_SF_Sd
0x14001a4a2  inc     r12d
0x14001a4a5  mov     rsi, [rbp+230h+var_2A8]
0x14001a4a9  jmp     loc_14001A336
0x14001a4ae  mov     [rbp+230h+var_260.Data1], r15d
0x14001a4b2  test    ebx, ebx
0x14001a4b4  js      loc_14001A3E3
0x14001a4ba  mov     edx, [r14+54h]; unsigned int
  ... truncated ...
```
