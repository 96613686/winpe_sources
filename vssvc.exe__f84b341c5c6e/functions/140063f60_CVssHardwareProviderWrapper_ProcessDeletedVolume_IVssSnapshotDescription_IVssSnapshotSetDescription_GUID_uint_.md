# CVssHardwareProviderWrapper::ProcessDeletedVolume(IVssSnapshotDescription *,IVssSnapshotSetDescription *,_GUID *,uint,bool *,CVssHardwareProviderWrapper::EDeviceOperation,int,CVssSimpleArray<ulong> *)

- ea: `0x140063f60`
- end: `0x140065a88`
- name: `?ProcessDeletedVolume@CVssHardwareProviderWrapper@@AEAAXPEAVIVssSnapshotDescription@@PEAVIVssSnapshotSetDescription@@PEAU_GUID@@IPEA_NW4EDeviceOperation@1@HPEAV?$CVssSimpleArray@K@@@Z`
- size: `6952`
- prototype: ``
- caller_count: `3`
- callee_count: `57`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140087148`
- `0x14008d224`
- `0x1400b5264`

## callees

- `0x140006020`
- `0x140008450`
- `0x1400084c4`
- `0x140008908`
- `0x140009444`
- `0x14000a834`
- `0x14000e640`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x140019760`
- `0x140019990`
- `0x140028b48`
- `0x1400326c0`
- `0x140032fcc`
- `0x1400330fc`
- `0x14003a8f0`
- `0x14003d54c`
- `0x14003eedc`
- `0x14003fc04`
- `0x140040a40`
- `0x14004b248`
- `0x14004ce80`
- `0x14005e024`
- `0x14005eaf8`
- `0x140063f60`
- `0x140065a90`
- `0x1400679e8`
- `0x140069108`
- `0x140069dbc`
- `0x140077018`
- `0x140077a2c`
- `0x14007b2e4`
- `0x14007bd10`
- `0x14007cf8c`
- `0x14007dda4`
- `0x14007f78c`
- `0x1400901e4`
- `0x140091560`
- `0x14009197c`
- `0x1400921dc`
- `0x1400b1ff4`
- `0x1400b2030`
- `0x1400b3120`
- `0x1400b3618`
- `0x1400b3648`
- `0x1400b3e84`
- `0x1400b4284`
- `0x1400b4754`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400647ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400647ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064fba`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x140064fac`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x140064fac`
- `OLEAUT32!__imp_SysFreeString` at `0x140065a52`
- `OLEAUT32!__imp_SysFreeString` at `0x140065a52`

## string_xrefs

- `0x140063fc5`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14006466c`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x1400648ce`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140064a36`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140064c07`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140064cce`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140064d8a`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140064e53`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140064ef6`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140064f85`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14006506e`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14006527d`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140065377`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x1400654b5`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140065577`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14006561e`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140063fd3`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140064360`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x1400643d7`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x14006467a`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x14006490b`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140064974`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140064a44`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140064c15`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140064cdc`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140064d98`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140064e61`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140064f04`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140064f8c`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x14006507c`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x14006528b`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140065385`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x1400654c0`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140065582`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140065629`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x140065731`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x1400657d0`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x14006586c`: `CVssHardwareProviderWrapper::ProcessDeletedVolume`
- `0x1400646d5`: `Attempting to dismount/delete the volume device and then revert disk signature`
- `0x1400649ab`: `Failed to open the volume: %s [0%08lx]`
- `0x1400649e0`: `Failed to open the volume: %s [0%08lx]`
- `0x140064df1`: `Failed to to dismount the volume: %s [0%08lx]`
- `0x140064f59`: `Removing mount points from volume device %s`
- `0x1400650d7`: `Uninstalling volume device: %s`
- `0x140065021`: `Fail to delete mount point %s for volume %s, winerror %d`
- `0x140065559`: `Fail to get all volume arrivals for reinstalled disks on Break`
- `0x140065779`: `CreateFile(%s) failed: [0x%08lx]`
- `0x140065984`: `CreateSymbolicLink(%s,%s) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall CVssHardwareProviderWrapper::ProcessDeletedVolume(
        CVssHardwareProviderWrapper *this,
        __int64 a2,
        struct IVssSnapshotSetDescription *a3,
        struct _GUID *a4,
        unsigned int a5,
        _BYTE *a6,
        int a7,
        int a8,
        void **a9)
{
  CVssHardwareProviderWrapper *v10; // r12
  const WCHAR *v11; // r13
  BSTR v12; // r14
  const wchar_t *v13; // rax
  int v14; // r15d
  const wchar_t *v15; // r9
  char v16; // di
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  struct _VSS_DISK_ID *v20; // rsi
  int v21; // ebx
  CVssDebugInfo *v22; // rax
  int v23; // ebx
  unsigned int *v24; // rax
  CVssDiskSignatureManager *v25; // rcx
  unsigned int *v26; // rax
  bool DiskPreviousId; // al
  __int64 v28; // rcx
  int v29; // ebx
  signed int v30; // ebx
  CVssDebugInfo *v31; // rax
  int v32; // ebx
  int v33; // ebx
  unsigned int v34; // ebx
  const WCHAR *v35; // rdi
  __int64 v36; // rax
  DWORD LastError; // ebx
  __int64 v38; // rax
  CVssHardwareProviderWrapper *v39; // rcx
  unsigned int v40; // r15d
  unsigned int *v41; // rsi
  __int64 v42; // rdx
  int v43; // ebx
  bool v44; // si
  struct IVssSnapshotSetDescription *v45; // r15
  struct _GUID *v46; // r13
  int v47; // eax
  unsigned int *v48; // rax
  bool IsDiskUnused; // al
  unsigned int v50; // ebx
  void **v51; // rdi
  unsigned int *v52; // rax
  __int64 v53; // rax
  void ***v54; // rcx
  unsigned int v55; // ebx
  _DWORD *v56; // rax
  struct CVssDiskSignatureManager *v57; // rdx
  _DWORD *v58; // rdi
  CVssHardwareProviderWrapper *v59; // rcx
  CVssDebugInfo *v60; // rax
  CVssDebugInfo *v61; // rax
  __int64 v62; // rbx
  int v63; // ebx
  int v64; // ebx
  CVssHardwareProviderWrapper *v65; // rcx
  CVssHardwareProviderWrapper *v66; // rcx
  __int64 v67; // rcx
  int *v68; // [rsp+20h] [rbp-E0h]
  int v69; // [rsp+20h] [rbp-E0h]
  int *v70; // [rsp+20h] [rbp-E0h]
  int *v71; // [rsp+20h] [rbp-E0h]
  int *v72; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+20h] [rbp-E0h]
  int *v74; // [rsp+20h] [rbp-E0h]
  int *v75; // [rsp+20h] [rbp-E0h]
  bool v76[8]; // [rsp+28h] [rbp-D8h]
  int v77; // [rsp+28h] [rbp-D8h]
  int v78; // [rsp+28h] [rbp-D8h]
  int v79; // [rsp+28h] [rbp-D8h]
  int v80; // [rsp+28h] [rbp-D8h]
  bool v81[8]; // [rsp+28h] [rbp-D8h]
  int v82; // [rsp+28h] [rbp-D8h]
  char v83; // [rsp+80h] [rbp-80h]
  bool v84; // [rsp+81h] [rbp-7Fh] BYREF
  bool v85; // [rsp+82h] [rbp-7Eh]
  __int64 v86; // [rsp+88h] [rbp-78h]
  const WCHAR *v87; // [rsp+90h] [rbp-70h]
  int v88; // [rsp+98h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-60h] BYREF
  const WCHAR *v90; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int *v91; // [rsp+B0h] [rbp-50h] BYREF
  struct _VSS_DISK_ID *v92; // [rsp+B8h] [rbp-48h] BYREF
  void **v93; // [rsp+C0h] [rbp-40h] BYREF
  void *v94; // [rsp+C8h] [rbp-38h]
  void **v95; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD *v96; // [rsp+D8h] [rbp-28h]
  int v97; // [rsp+E0h] [rbp-20h]
  void **v98; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v99; // [rsp+F0h] [rbp-10h]
  int v100; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v101; // [rsp+FCh] [rbp-4h] BYREF
  int v102; // [rsp+100h] [rbp+0h]
  const unsigned __int16 *v103; // [rsp+108h] [rbp+8h] BYREF
  const wchar_t *v104; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v105; // [rsp+118h] [rbp+18h]
  int v106; // [rsp+120h] [rbp+20h]
  int v107; // [rsp+124h] [rbp+24h]
  int v108; // [rsp+128h] [rbp+28h]
  _BYTE v109[120]; // [rsp+130h] [rbp+30h] BYREF
  int v110; // [rsp+1A8h] [rbp+A8h]
  LPVOID v111; // [rsp+1B0h] [rbp+B0h] BYREF
  int v112; // [rsp+1B8h] [rbp+B8h]
  void **v113; // [rsp+220h] [rbp+120h] BYREF
  struct _VSS_DISK_ID *v114; // [rsp+228h] [rbp+128h]
  void **v115; // [rsp+230h] [rbp+130h] BYREF
  const WCHAR *v116; // [rsp+238h] [rbp+138h]
  _BYTE v117[16]; // [rsp+240h] [rbp+140h] BYREF
  void **v118; // [rsp+250h] [rbp+150h] BYREF
  __int64 v119; // [rsp+258h] [rbp+158h]
  int v120; // [rsp+260h] [rbp+160h]
  unsigned int *v121; // [rsp+268h] [rbp+168h]
  struct _VSS_DISK_ID *v122; // [rsp+270h] [rbp+170h]
  _QWORD v123[2]; // [rsp+278h] [rbp+178h] BYREF
  __int128 v124; // [rsp+288h] [rbp+188h] BYREF
  __int64 v125; // [rsp+298h] [rbp+198h]
  __int64 v126; // [rsp+2A0h] [rbp+1A0h]
  struct _GUID *v127; // [rsp+2A8h] [rbp+1A8h]
  _BYTE *v128; // [rsp+2B0h] [rbp+1B0h]
  struct IVssSnapshotSetDescription *v129; // [rsp+2B8h] [rbp+1B8h]
  __int64 v130; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v131; // [rsp+2C8h] [rbp+1C8h]
  __int128 v132; // [rsp+2D8h] [rbp+1D8h]
  __int16 v133; // [rsp+2E8h] [rbp+1E8h]
  __int64 v134; // [rsp+2ECh] [rbp+1ECh]
  __int64 v135; // [rsp+2F8h] [rbp+1F8h]
  __int64 v136; // [rsp+300h] [rbp+200h]
  int v137; // [rsp+308h] [rbp+208h]
  unsigned int *v138; // [rsp+310h] [rbp+210h]
  __int16 v139; // [rsp+318h] [rbp+218h]
  void **v140; // [rsp+320h] [rbp+220h]
  __int64 v141; // [rsp+328h] [rbp+228h]
  __int64 v142; // [rsp+330h] [rbp+230h] BYREF
  __int128 v143; // [rsp+338h] [rbp+238h]
  __int128 v144; // [rsp+348h] [rbp+248h]
  __int16 v145; // [rsp+358h] [rbp+258h]
  __int64 v146; // [rsp+35Ch] [rbp+25Ch]
  __int64 v147; // [rsp+368h] [rbp+268h]
  __int64 v148; // [rsp+370h] [rbp+270h]
  int v149; // [rsp+378h] [rbp+278h]
  __int64 v150; // [rsp+380h] [rbp+280h]
  __int16 v151; // [rsp+388h] [rbp+288h]
  void **v152; // [rsp+390h] [rbp+290h]
  __int64 v153; // [rsp+398h] [rbp+298h]
  _BYTE v154[168]; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int128 v155; // [rsp+448h] [rbp+348h] BYREF
  _OWORD v156[3]; // [rsp+458h] [rbp+358h] BYREF
  unsigned __int16 v157[4]; // [rsp+490h] [rbp+390h] BYREF
  const wchar_t *v158; // [rsp+498h] [rbp+398h]
  const unsigned __int16 *v159; // [rsp+4A0h] [rbp+3A0h]
  int v160; // [rsp+4A8h] [rbp+3A8h]
  int v161; // [rsp+4ACh] [rbp+3ACh]
  int v162; // [rsp+4B0h] [rbp+3B0h]
  _BYTE v163[120]; // [rsp+4B8h] [rbp+3B8h] BYREF
  int v164; // [rsp+530h] [rbp+430h]
  unsigned __int16 v165[264]; // [rsp+540h] [rbp+440h] BYREF

  v127 = a4;
  v129 = a3;
  v86 = a2;
  v10 = this;
  v95 = (void **)this;
  v128 = a6;
  v118 = a9;
  *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
  v159 = L"CORHDELC";
  v160 = 518;
  v161 = 6;
  v162 = 255;
  v11 = 0;
  v164 = 0x1000000;
  memset_0(v163, 0, sizeof(v163));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v111, (__int64)v157, 0);
  bstrString = 0;
  v112 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a2 + 128LL))(a2, &bstrString);
  *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
  v159 = L"CORHDELC";
  v160 = 522;
  v161 = 1;
  v162 = 255;
  v164 = 0x1000000;
  memset_0(v163, 0, sizeof(v163));
  CVssFunctionTracer::CheckForErrorInternal(&v111, v157, L"IVssSnapshotDescription::GetDeviceName");
  v84 = 0;
  v112 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)a2 + 96LL))(a2, &v84);
  *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
  v159 = L"CORHDELC";
  v160 = 526;
  v161 = 1;
  v162 = 255;
  v164 = 0x1000000;
  memset_0(v163, 0, sizeof(v163));
  CVssFunctionTracer::CheckForErrorInternal(&v111, v157, L"IVssSnapshotDescription::IsDynamicVolume");
  v100 = 0;
  v112 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 64LL))(a2, &v100);
  *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
  v159 = L"CORHDELC";
  v160 = 530;
  v161 = 1;
  v162 = 255;
  v164 = 0x1000000;
  memset_0(v163, 0, sizeof(v163));
  CVssFunctionTracer::CheckForErrorInternal(&v111, v157, L"IVssSnapshotDescription::GetAttributes");
  v155 = 0;
  v112 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 24LL))(a2, &v155);
  *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
  v159 = L"CORHDELC";
  v160 = 534;
  v161 = 1;
  v162 = 255;
  v164 = 0x1000000;
  memset_0(v163, 0, sizeof(v163));
  CVssFunctionTracer::CheckForErrorInternal(&v111, v157, L"IVssSnapshotDescription::GetSnapshotId");
  v102 = v100 & 1;
  v12 = bstrString;
  v124 = 0;
  v125 = 0;
  v126 = 0;
  *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
  v159 = L"CORHDELC";
  v160 = 546;
  v161 = 6;
  v162 = 255;
  v164 = 0x1000000;
  memset_0(v163, 0, sizeof(v163));
  v13 = L"Mask Flag given";
  if ( !a8 )
    v13 = L"No Mask Flag";
  v14 = a7;
  v15 = L"Breaking";
  if ( a7 )
    v15 = L"Deleting";
  CVssFunctionTracer::Trace(&v111, v157, L"%s snapshot %s, %s", v15, v12, v13);
  if ( a7
    || (CVssDiskSignatureManager::Initialize((CVssDiskSignatureManager *)&v124),
        CVssDiskSignatureManager::IsIdSafeToRevertOnVolumeDisks((CVssDiskSignatureManager *)&v124, v12, v84)) )
  {
    if ( a8 )
    {
      *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
      v159 = L"CORHDELC";
      v160 = 565;
      v161 = 1;
      v162 = 255;
      v164 = 0x1000000;
      memset_0(v163, 0, sizeof(v163));
      CVssFunctionTracer::AddOperation((__int64)&v111, (__int64)v157, 0x1780u);
    }
    else if ( a7 == 1 )
    {
      *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
      v159 = L"CORHDELC";
      v160 = 567;
      v161 = 1;
      v162 = 255;
      v164 = 0x1000000;
      memset_0(v163, 0, sizeof(v163));
      CVssFunctionTracer::AddOperation((__int64)&v111, (__int64)v157, 0x1782u);
    }
    else if ( !a7 )
    {
      *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
      v159 = L"CORHDELC";
      v160 = 569;
      v161 = 1;
      v162 = 255;
      v164 = 0x1000000;
      memset_0(v163, 0, sizeof(v163));
      CVssFunctionTracer::AddOperation((__int64)&v111, (__int64)v157, 0x1781u);
    }
    *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
    v159 = L"CORHDELC";
    v160 = 571;
    v161 = 1;
    v162 = 255;
    v164 = 0x1000000;
    memset_0(v163, 0, sizeof(v163));
    CVssFunctionTracer::AddContext((__int64)&v111, (__int64)v157, 5010, (__int64)v12);
    *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
    v159 = L"CORHDELC";
    v160 = 572;
    v161 = 1;
    v162 = 255;
    v164 = 0x1000000;
    memset_0(v163, 0, sizeof(v163));
    *(_DWORD *)v76 = WORD2(v155);
    LODWORD(v68) = v155;
    CVssFunctionTracer::AddContextEx(
      (__int64)&v111,
      (__int64)v157,
      0x1396u,
      L"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
      v68,
      *(_QWORD *)v76,
      WORD3(v155),
      BYTE8(v155),
      BYTE9(v155),
      BYTE10(v155),
      BYTE11(v155),
      BYTE12(v155),
      BYTE13(v155),
      BYTE14(v155),
      HIBYTE(v155));
    *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
    v159 = L"CORHDELC";
    v160 = 574;
    v161 = 6;
    v162 = 255;
    v164 = 0x1000000;
    v16 = 1;
    memset_0(v163, 0, sizeof(v163));
    CVssFunctionTracer::Trace(
      &v111,
      v157,
      L"Attempting to dismount/delete the volume device and then revert disk signature");
    v85 = a7 == 1;
    v94 = (void *)-1LL;
    v93 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
    v99 = 0;
    v98 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    memset(v156, 0, sizeof(v156));
    if ( (unsigned __int8)CVssHardwareProviderWrapper::GetVolumeDevinfo(v17, v12, &v93, &v98, v156)
      || (unsigned __int8)CVssHardwareProviderWrapper::GetHiddenVolumeDevinfo(v18, v12, &v93, &v98, v156) )
    {
      v83 = 1;
    }
    else
    {
      v83 = 0;
      *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
      v159 = L"CORHDELC";
      v160 = 603;
      v161 = 1;
      v162 = 255;
      v164 = 0x1000000;
      memset_0(v163, 0, sizeof(v163));
      GetLastError();
      v19 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)v157, (CVssDebugInfo *)&v103);
      CVssFunctionTracer::LogError(&v111, 12329, v19, 2);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v157);
    }
    v101 = 0;
    v20 = 0;
    v122 = 0;
    v92 = 0;
    v130 = 0;
    v133 = 0;
    v134 = 0;
    v135 = 0;
    v136 = 0;
    v137 = 0;
    v138 = 0;
    v139 = 0;
    v141 = 0;
    v140 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    v131 = 0;
    v132 = 0;
    LOBYTE(v69) = 0;
    v21 = CVssIOCTLChannel::Open(&v130, &v111, v12, 0, v69, 0, -1073741824, 3, 128);
    v112 = v21;
    if ( v21 < 0 )
    {
      v161 = 1;
      v162 = 255;
      v164 = 0x1000000;
      *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      if ( v21 == -2147212536 )
      {
        v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
        v159 = L"CORHDELC";
        v160 = 636;
        memset_0(v163, 0, sizeof(v163));
        v22 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)v157, (CVssDebugInfo *)&v103, v12);
        CVssFunctionTracer::LogError(&v111, 12330, v22, 2);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v157);
      }
      else
      {
        v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
        v159 = L"CORHDELC";
        if ( a7 != 1 )
        {
          v160 = 646;
          memset_0(v163, 0, sizeof(v163));
          LODWORD(v70) = v21;
          CVssFunctionTracer::TranslateWin32Error(&v111, v157, L"Failed to open the volume: %s [0%08lx]", v12, v70);
        }
        v160 = 642;
        memset_0(v163, 0, sizeof(v163));
        LODWORD(v70) = v21;
        CVssFunctionTracer::LogGenericWarning(&v111, v157, L"Failed to open the volume: %s [0%08lx]", v12, v70);
      }
      goto LABEL_97;
    }
    LOBYTE(v77) = 0;
    v23 = CVssIOCTLChannel::Call(&v130, &v111, 5636096, 0, 0, v77, 0);
    v112 = v23;
    if ( v23 < 0 )
    {
      *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
      v159 = L"CORHDELC";
      v160 = 657;
      v161 = 1;
      v162 = 255;
      v164 = 0x1000000;
      memset_0(v163, 0, sizeof(v163));
      LODWORD(v71) = v23;
      CVssFunctionTracer::TranslateWin32Error(&v111, v157, L"Failed to get the volume extents: %s [0%08lx]", v12, v71);
    }
    v24 = v138;
    v138 = 0;
    v136 = 0;
    v137 = 0;
    v91 = v24;
    v25 = (CVssDiskSignatureManager *)*v24;
    v88 = *v24;
    v26 = v24 + 2;
    v121 = v26;
    if ( a7
      || (DiskPreviousId = CVssDiskSignatureManager::GetDiskPreviousId(v25, *v26, &v92, &v101),
          v20 = v92,
          v122 = v92,
          !DiskPreviousId) )
    {
      v16 = 0;
    }
    v123[1] = v20;
    v123[0] = &CVssAuto<unsigned short * *,CVssAutoCppPtr_Storage<unsigned short * *>>::`vftable';
    v87 = 0;
    v90 = 0;
    v92 = 0;
    ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>(v117);
    v114 = 0;
    v113 = &CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>::`vftable';
    v116 = 0;
    v115 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
    if ( v102 && v16 )
    {
      CVssHardwareProviderWrapper::CollectSharesAndMountPointsOnVolume(v28, v12, v117, &v92, &v90);
      CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::Close(&v113);
      v114 = v92;
      CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v115);
      v11 = v90;
      v87 = v90;
      v116 = v90;
    }
    LODWORD(v134) = 0;
    LODWORD(v136) = 0;
    LOBYTE(v78) = 0;
    v29 = CVssIOCTLChannel::Call(&v130, &v111, 589848, 0, 0, v78, 0);
    v112 = v29;
    if ( v29 < 0 )
    {
      *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
      v159 = L"CORHDELC";
      v160 = 705;
      v161 = 1;
      v162 = 255;
      v164 = 0x1000000;
      memset_0(v163, 0, sizeof(v163));
      CVssFunctionTracer::Trace(&v111, v157, L"Failed to lock the volume [0x%08lx].", (unsigned int)v29);
    }
    LODWORD(v134) = 0;
    LODWORD(v136) = 0;
    LOBYTE(v79) = 0;
    v30 = CVssIOCTLChannel::Call(&v130, &v111, 589856, 0, 0, v79, 0);
    v112 = v30;
    if ( v30 < 0 )
    {
      *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
      v159 = L"CORHDELC";
      v160 = 715;
      v161 = 1;
      v162 = 255;
      v164 = 0x1000000;
      memset_0(v163, 0, sizeof(v163));
      v31 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)v157, (CVssDebugInfo *)&v103, v30);
      CVssFunctionTracer::LogError(&v111, 12331, v31, (unsigned __int16)((a7 == 1) + 1));
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v157);
      if ( a7 != 1 )
      {
        v32 = v112;
        *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
        v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
        v159 = L"CORHDELC";
        v160 = 718;
        v161 = 1;
        v162 = 255;
        v164 = 0x1000000;
        memset_0(v163, 0, sizeof(v163));
        LODWORD(v72) = v32;
        CVssFunctionTracer::TranslateWin32Error(&v111, v157, L"Failed to to dismount the volume: %s [0%08lx]", v12, v72);
      }
    }
    LODWORD(v134) = 0;
    LODWORD(v136) = 0;
    LOBYTE(v80) = 0;
    v33 = CVssIOCTLChannel::Call(&v130, &v111, 5685260, 0, 0, v80, 0);
    v112 = v33;
    if ( v33 < 0 )
    {
      *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
      v159 = L"CORHDELC";
      v160 = 729;
      v161 = 1;
      v162 = 255;
      v164 = 0x1000000;
      memset_0(v163, 0, sizeof(v163));
      CVssFunctionTracer::Trace(&v111, v157, L"Failed to take the volume offline [0x%08lx].", (unsigned int)v33);
    }
    CVssIOCTLChannel::Close((CVssIOCTLChannel *)&v130);
    v34 = 0;
    if ( a7 == 1 || v16 )
    {
      *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
      v159 = L"CORHDELC";
      v160 = 752;
      v161 = 1;
      v162 = 255;
      v164 = 0x1000000;
      memset_0(v163, 0, sizeof(v163));
      CVssFunctionTracer::Trace(&v111, v157, L"Removing mount points from volume device %s", v12);
      v35 = v11;
      if ( v11 )
      {
        do
        {
          v36 = -1;
          do
            ++v36;
          while ( v35[v36] );
          if ( !v36 )
            break;
          if ( !DeleteVolumeMountPointW(v35) )
          {
            LastError = GetLastError();
            *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
            v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
            v159 = L"CORHDELC";
            v160 = 759;
            v161 = 1;
            v162 = 255;
            v164 = 0x1000000;
            memset_0(v163, 0, sizeof(v163));
            *(_DWORD *)v81 = LastError;
            CVssFunctionTracer::Trace(
              &v111,
              v157,
              L"Fail to delete mount point %s for volume %s, winerror %d",
              v35,
              v12,
              *(_QWORD *)v81);
            v34 = 0;
          }
          v38 = -1;
          do
            ++v38;
          while ( v35[v38] );
          v35 += v38 + 1;
        }
        while ( v35 );
        v14 = a7;
        v10 = (CVssHardwareProviderWrapper *)v95;
        v20 = v122;
        v11 = v87;
      }
    }
    *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
    v159 = L"CORHDELC";
    v160 = 768;
    v161 = 1;
    v162 = 255;
    v164 = 0x1000000;
    memset_0(v163, 0, sizeof(v163));
    CVssFunctionTracer::Trace(&v111, v157, L"Uninstalling volume device: %s", v99);
    if ( v83 )
    {
      CVssHardwareProviderWrapper::UninstallDevice(v39, v94, (struct _DO_DEVINFO_DATA *)v156);
      CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(&v93);
    }
    if ( v84 )
    {
      ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>(&v95);
      v97 = a8;
      v40 = v88;
      if ( v88 )
      {
        v41 = v121;
        do
        {
          if ( !(unsigned __int8)CVssHardwareProviderWrapper::IdArrayContainsId(v41[6 * v34], &v95) )
            CVssSimpleArray<unsigned long>::Add(&v95, &v41[6 * v34]);
          ++v34;
        }
        while ( v34 < v40 );
      }
      CVssHardwareProviderWrapper::BuildClosure(v10, &v95);
      v42 = 0;
      v43 = 0;
      v44 = v85;
      v45 = v129;
      v46 = v127;
      while ( 1 )
      {
        v47 = (int)v96;
        if ( v43 >= (int)v96 )
          break;
        v48 = (unsigned int *)ATL::CSimpleArray<unsigned long,ATL::CSimpleArrayEqualHelper<unsigned long>>::operator[](
                                &v95,
                                (unsigned int)v43);
        IsDiskUnused = CVssHardwareProviderWrapper::IsDiskUnused(v10, *v48, v45, v46, a5, v44);
        v42 = 0;
        if ( !IsDiskUnused )
          goto LABEL_69;
        ++v43;
      }
      *v128 = 1;
      if ( a8 )
      {
        v50 = 0;
        if ( v47 > 0 )
        {
          v51 = v118;
          do
          {
            v52 = (unsigned int *)ATL::CSimpleArray<unsigned long,ATL::CSimpleArrayEqualHelper<unsigned long>>::operator[](
                                    &v95,
                                    v50);
            if ( !(unsigned __int8)CVssHardwareProviderWrapper::IdArrayContainsId(*v52, v51) )
            {
              v53 = ATL::CSimpleArray<unsigned long,ATL::CSimpleArrayEqualHelper<unsigned long>>::operator[](&v95, v50);
              CVssSimpleArray<unsigned long>::Add(v51, v53);
            }
            ++v50;
          }
          while ( (int)v50 < (int)v96 );
        }
      }
      else
      {
        CVssHardwareProviderWrapper::OfflineDynamicDisks(v10, (struct _VSS_DISK_UNINSTALL_DATA *)&v95);
        CVssHardwareProviderWrapper::UninstallDisks(v10, (struct _VSS_DISK_UNINSTALL_DATA *)&v95);
      }
LABEL_69:
      v54 = &v95;
    }
    else
    {
      v55 = *v121;
      v88 = v55;
      if ( !CVssHardwareProviderWrapper::IsDiskUnused(v10, v55, v129, v127, a5, v85) )
      {
        *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
        v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
        v159 = L"CORHDELC";
        v160 = 861;
        v161 = 1;
        v162 = 255;
        v164 = 0x1000000;
        memset_0(v163, 0, sizeof(v163));
        CVssFunctionTracer::Trace(&v111, v157, L"Disk %d still has snapshots on it", v55);
        goto LABEL_96;
      }
      if ( v14 != 1 )
      {
        v88 = 0;
        v56 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
        v58 = v56;
        if ( !v56 )
        {
          *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
          v159 = L"CORHDELC";
          v160 = 896;
          v161 = 1;
          v162 = 255;
          v164 = 0x1000000;
          memset_0(v163, 0, sizeof(v163));
          CVssFunctionTracer::Throw(&v111, v157, 2147942414LL, L"can't allocate VSS_VOLUME_DISK_ID_MAPPING");
        }
        v56[3] = 0;
        *((_QWORD *)v56 + 3) = 0;
        *((_QWORD *)v56 + 4) = 0;
        *((_QWORD *)v56 + 2) = v121;
        *(_QWORD *)v56 = v20;
        v56[2] = v101;
        v119 = 0;
        v118 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
        v96 = v56;
        v95 = &CVssAuto<unsigned short * *,CVssAutoCppPtr_Storage<unsigned short * *>>::`vftable';
        if ( CVssHardwareProviderWrapper::ReOnlineDiskAndWaitForVolumeOnBreak(
               v10,
               v57,
               v55,
               (struct _VSS_VOLUME_DISK_ID_MAPPING *)v56,
               &v88) )
        {
          v62 = *((_QWORD *)v58 + 3);
          CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v118);
          v119 = v62;
          v112 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v86 + 136LL))(v86, *((_QWORD *)v58 + 3));
          v103 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          v104 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
          v105 = L"CORHDELC";
          v106 = 936;
          v107 = 1;
          v108 = 255;
          v110 = 0x1000000;
          memset_0(v109, 0, sizeof(v109));
          CVssFunctionTracer::CheckForErrorInternal(&v111, &v103, L"IVssSnapshotSetDescription::SetDeviceName");
          v142 = 0;
          v145 = 0;
          v146 = 0;
          v147 = 0;
          v148 = 0;
          v149 = 0;
          v150 = 0;
          v151 = 0;
          v153 = 0;
          v152 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
          v143 = 0;
          v144 = 0;
          LOBYTE(v73) = 0;
          v63 = CVssIOCTLChannel::Open(&v142, &v111, *((_QWORD *)v58 + 3), 0, v73, 0, -1073741824, 3, 128);
          v112 = v63;
          if ( v63 >= 0 )
          {
            LOBYTE(v82) = 0;
            v64 = CVssIOCTLChannel::Call(&v142, &v111, 5685256, 0, 0, v82, 0);
            v112 = v64;
            if ( v64 < 0 )
            {
              v103 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
              v104 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
              v105 = L"CORHDELC";
              v106 = 953;
              v107 = 1;
              v108 = 255;
              v110 = 0x1000000;
              memset_0(v109, 0, sizeof(v109));
              LODWORD(v75) = v64;
              CVssFunctionTracer::Trace(
                &v111,
                &v103,
                L"DeviceIoControl(%s, IOCTL_VOLUME_ONLINE) fails: [0x%08lx]",
                *((_QWORD *)v58 + 3),
                v75);
              v112 = 0;
            }
            CVssIOCTLChannel::Close((CVssIOCTLChannel *)&v142);
          }
          else
          {
            v103 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
            v104 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
            v105 = L"CORHDELC";
            v106 = 945;
            v107 = 1;
            v108 = 255;
            v110 = 0x1000000;
            memset_0(v109, 0, sizeof(v109));
            LODWORD(v74) = v63;
            CVssFunctionTracer::Trace(&v111, &v103, L"CreateFile(%s) failed: [0x%08lx]", *((_QWORD *)v58 + 3), v74);
          }
          memset_0(v165, 0, 0x208u);
          if ( !CVssHardwareProviderWrapper::GetDosDevice(v65, *((const unsigned __int16 **)v58 + 3), v165, 0x104u) )
          {
            v103 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
            v104 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
            v105 = L"CORHDELC";
            v106 = 965;
            v107 = 6;
            v108 = 255;
            v110 = 0x1000000;
            memset_0(v109, 0, sizeof(v109));
            CVssFunctionTracer::Trace(&v111, &v103, L"GetDosDevice(%s) fails ", *((_QWORD *)v58 + 3));
          }
          if ( v102 )
          {
            if ( !CVssHardwareProviderWrapper::SetDosDevice(v66, v12, v165) )
            {
              v103 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
              v104 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
              v105 = L"CORHDELC";
              v106 = 971;
              v107 = 6;
              v108 = 255;
              v110 = 0x1000000;
              memset_0(v109, 0, sizeof(v109));
              CVssFunctionTracer::Trace(&v111, &v103, L"SetDosDevice(%s, %s) failed", v12, v165);
            }
          }
          else if ( !CVssHardwareProviderWrapper::CreateSymbolicLinkW(v66, v12, v165) )
          {
            v103 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
            v104 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
            v105 = L"CORHDELC";
            v106 = 979;
            v107 = 6;
            v108 = 255;
            v110 = 0x1000000;
            memset_0(v109, 0, sizeof(v109));
            CVssFunctionTracer::Trace(&v111, &v103, L"CreateSymbolicLink(%s,%s) failed", v12, v165);
          }
          CVssHardwareProviderWrapper::RestoreSharesAndMountPointsOnVolume(v67, *((_QWORD *)v58 + 3), v117, v11);
          CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v142);
        }
        else
        {
          memset_0(v157, 0, 0x80u);
          CVssHardwareProviderWrapper::DisknoToPhysicalDrive(v59, (struct CVssFunctionTracer *)&v111, v55, v157, 0x40u);
          v107 = 6;
          v110 = 0x1000000;
          if ( v88 )
          {
            v103 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
            v104 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
            v105 = L"CORHDELC";
            v106 = 923;
            v108 = 255;
            memset_0(v109, 0, sizeof(v109));
            v60 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v103, (CVssDebugInfo *)v154, v12);
            CVssFunctionTracer::LogError(&v111, 12350, v60, 1);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v103);
            v103 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
            v104 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
            v105 = L"CORHDELC";
            v106 = 924;
            v107 = 6;
            v108 = 255;
            v110 = 0x1000000;
            memset_0(v109, 0, sizeof(v109));
            CVssFunctionTracer::Throw(
              &v111,
              &v103,
              2147754754LL,
              L"Fail to get all volume arrivals for reinstalled disks on Break");
          }
          v103 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          v104 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
          v105 = L"CORHDELC";
          v106 = 927;
          v108 = 255;
          memset_0(v109, 0, sizeof(v109));
          v61 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v103, (CVssDebugInfo *)v154, v157);
          CVssFunctionTracer::LogError(&v111, 12352, v61, 1);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v103);
        }
        CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>::~CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>(&v95);
        CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v118);
        goto LABEL_96;
      }
      ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>(&v118);
      CVssSimpleArray<unsigned long>::Add(&v118, &v88);
      v120 = a8;
      CVssHardwareProviderWrapper::UninstallDisks(v10, (struct _VSS_DISK_UNINSTALL_DATA *)&v118);
      *v128 = 1;
      v54 = &v118;
    }
    ATL::CSimpleArray<_HRESOURCE *,ATL::CSimpleArrayEqualHelper<_HRESOURCE *>>::~CSimpleArray<_HRESOURCE *,ATL::CSimpleArrayEqualHelper<_HRESOURCE *>>(
      v54,
      v42);
LABEL_96:
    CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v115);
    CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>::~CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>(&v113);
    ATL::CSimpleArray<_GUID,ATL::CSimpleArrayEqualHelper<_GUID>>::RemoveAll(v117);
    CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>::~CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>(v123);
    CVssMallocAutoPtr<_VM_GET_CLOSURE_OUTPUT>::~CVssMallocAutoPtr<_VM_GET_CLOSURE_OUTPUT>((void **)&v91);
LABEL_97:
    CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v130);
    CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v98);
    CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(&v93);
    goto LABEL_98;
  }
  *(_QWORD *)v157 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v158 = L"CVssHardwareProviderWrapper::ProcessDeletedVolume";
  v159 = L"CORHDELC";
  v160 = 559;
  v161 = 6;
  v162 = 255;
  v164 = 0x1000000;
  memset_0(v163, 0, sizeof(v163));
  CVssFunctionTracer::Trace(&v111, v157, L"It is not safe to revert signature on one of the disks of this volume");
LABEL_98:
  CVssDiskSignatureManager::~CVssDiskSignatureManager((CVssDiskSignatureManager *)&v124);
  SysFreeString(bstrString);
  CVssFunctionTracer::~CVssFunctionTracer(&v111);
}

```

## disassembly

```asm
0x140063f60  push    rbp
0x140063f62  push    rbx
0x140063f63  push    rsi
0x140063f64  push    rdi
0x140063f65  push    r12
0x140063f67  push    r13
0x140063f69  push    r14
0x140063f6b  push    r15
0x140063f6d  lea     rbp, [rsp-668h]
0x140063f75  sub     rsp, 768h
0x140063f7c  mov     rax, cs:__security_cookie
0x140063f83  xor     rax, rsp
0x140063f86  mov     [rbp+6A0h+var_50], rax
0x140063f8d  mov     [rbp+6A0h+var_4F8], r9
0x140063f94  mov     [rbp+6A0h+var_4E8], r8
0x140063f9b  mov     rbx, rdx
0x140063f9e  mov     [rbp+6A0h+var_718], rdx
0x140063fa2  mov     r12, rcx
0x140063fa5  mov     [rbp+6A0h+var_6D0], rcx
0x140063fa9  mov     rax, [rbp+6A0h+arg_28]
0x140063fb0  mov     [rbp+6A0h+var_4F0], rax
0x140063fb7  mov     rax, [rbp+6A0h+arg_40]
0x140063fbe  mov     [rbp+6A0h+var_550], rax
0x140063fc5  lea     rsi, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140063fcc  mov     qword ptr [rbp+6A0h+var_310], rsi
0x140063fd3  lea     r15, aCvsshardwarepr_162; "CVssHardwareProviderWrapper::ProcessDel"...
0x140063fda  mov     [rbp+6A0h+var_308], r15
0x140063fe1  lea     r14, aCorhdelc; "CORHDELC"
0x140063fe8  mov     [rbp+6A0h+var_300], r14
0x140063fef  mov     [rbp+6A0h+var_2F8], 206h
0x140063ff9  mov     [rbp+6A0h+var_2F4], 6
0x140064003  mov     [rbp+6A0h+var_2F0], 0FFh
0x14006400d  xor     r13d, r13d
0x140064010  mov     [rbp+6A0h+var_270], 1000000h
0x14006401a  lea     edi, [r13+1]
0x14006401e  xor     edx, edx; Val
0x140064020  lea     r8d, [r13+78h]; Size
0x140064024  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x14006402b  call    memset_0
0x140064030  xor     r8d, r8d
0x140064033  lea     rdx, [rbp+6A0h+var_310]
0x14006403a  lea     rcx, [rbp+6A0h+var_5F0]
0x140064041  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140064046  nop
0x140064047  mov     [rbp+6A0h+bstrString], r13
0x14006404b  mov     rax, [rbx]
0x14006404e  lea     rdx, [rbp+6A0h+bstrString]
0x140064052  mov     rcx, rbx
0x140064055  mov     rax, [rax+80h]
0x14006405c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064061  mov     [rbp+6A0h+var_5E8], eax
0x140064067  mov     qword ptr [rbp+6A0h+var_310], rsi
0x14006406e  mov     [rbp+6A0h+var_308], r15
0x140064075  mov     [rbp+6A0h+var_300], r14
0x14006407c  mov     [rbp+6A0h+var_2F8], 20Ah
0x140064086  mov     [rbp+6A0h+var_2F4], edi
0x14006408c  mov     [rbp+6A0h+var_2F0], 0FFh
0x140064096  mov     [rbp+6A0h+var_270], 1000000h
0x1400640a0  xor     edx, edx; Val
0x1400640a2  lea     r8d, [r13+78h]; Size
0x1400640a6  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x1400640ad  call    memset_0
0x1400640b2  lea     r8, aIvsssnapshotde_10; "IVssSnapshotDescription::GetDeviceName"
0x1400640b9  lea     rdx, [rbp+6A0h+var_310]
0x1400640c0  lea     rcx, [rbp+6A0h+var_5F0]
0x1400640c7  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400640cc  mov     [rbp+6A0h+var_71F], r13b
0x1400640d0  mov     rax, [rbx]
0x1400640d3  lea     rdx, [rbp+6A0h+var_71F]
0x1400640d7  mov     rcx, rbx
0x1400640da  mov     rax, [rax+60h]
0x1400640de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400640e3  mov     [rbp+6A0h+var_5E8], eax
0x1400640e9  mov     qword ptr [rbp+6A0h+var_310], rsi
0x1400640f0  mov     [rbp+6A0h+var_308], r15
0x1400640f7  mov     [rbp+6A0h+var_300], r14
0x1400640fe  mov     [rbp+6A0h+var_2F8], 20Eh
0x140064108  mov     [rbp+6A0h+var_2F4], edi
0x14006410e  mov     [rbp+6A0h+var_2F0], 0FFh
0x140064118  mov     [rbp+6A0h+var_270], 1000000h
0x140064122  xor     edx, edx; Val
0x140064124  lea     r8d, [r13+78h]; Size
0x140064128  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x14006412f  call    memset_0
0x140064134  lea     r8, aIvsssnapshotde_15; "IVssSnapshotDescription::IsDynamicVolum"...
0x14006413b  lea     rdx, [rbp+6A0h+var_310]
0x140064142  lea     rcx, [rbp+6A0h+var_5F0]
0x140064149  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14006414e  mov     [rbp+6A0h+var_6A8], r13d
0x140064152  mov     rax, [rbx]
0x140064155  lea     rdx, [rbp+6A0h+var_6A8]
0x140064159  mov     rcx, rbx
0x14006415c  mov     rax, [rax+40h]
0x140064160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064165  mov     [rbp+6A0h+var_5E8], eax
0x14006416b  mov     qword ptr [rbp+6A0h+var_310], rsi
0x140064172  mov     [rbp+6A0h+var_308], r15
0x140064179  mov     [rbp+6A0h+var_300], r14
0x140064180  mov     [rbp+6A0h+var_2F8], 212h
0x14006418a  mov     [rbp+6A0h+var_2F4], edi
0x140064190  mov     [rbp+6A0h+var_2F0], 0FFh
0x14006419a  mov     [rbp+6A0h+var_270], 1000000h
0x1400641a4  xor     edx, edx; Val
0x1400641a6  lea     r8d, [r13+78h]; Size
0x1400641aa  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x1400641b1  call    memset_0
0x1400641b6  lea     r8, aIvsssnapshotde; "IVssSnapshotDescription::GetAttributes"
0x1400641bd  lea     rdx, [rbp+6A0h+var_310]
0x1400641c4  lea     rcx, [rbp+6A0h+var_5F0]
0x1400641cb  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400641d0  xorps   xmm0, xmm0
0x1400641d3  movups  [rbp+6A0h+var_358], xmm0
0x1400641da  mov     rax, [rbx]
0x1400641dd  lea     rdx, [rbp+6A0h+var_358]
0x1400641e4  mov     rcx, rbx
0x1400641e7  mov     rax, [rax+18h]
0x1400641eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400641f0  mov     [rbp+6A0h+var_5E8], eax
0x1400641f6  mov     qword ptr [rbp+6A0h+var_310], rsi
0x1400641fd  mov     [rbp+6A0h+var_308], r15
0x140064204  mov     [rbp+6A0h+var_300], r14
0x14006420b  mov     [rbp+6A0h+var_2F8], 216h
0x140064215  mov     [rbp+6A0h+var_2F4], edi
0x14006421b  mov     ebx, 0FFh
0x140064220  mov     [rbp+6A0h+var_2F0], ebx
0x140064226  mov     [rbp+6A0h+var_270], 1000000h
0x140064230  xor     edx, edx; Val
0x140064232  lea     r8d, [r13+78h]; Size
0x140064236  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x14006423d  call    memset_0
0x140064242  lea     r8, aIvsssnapshotde_17; "IVssSnapshotDescription::GetSnapshotId"
0x140064249  lea     rdx, [rbp+6A0h+var_310]
0x140064250  lea     rcx, [rbp+6A0h+var_5F0]
0x140064257  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14006425c  mov     eax, [rbp+6A0h+var_6A8]
0x14006425f  and     eax, edi
0x140064261  mov     [rbp+6A0h+var_6A0], eax
0x140064264  mov     r14, [rbp+6A0h+bstrString]
0x140064268  xorps   xmm0, xmm0
0x14006426b  movdqu  [rbp+6A0h+var_518], xmm0
0x140064273  mov     [rbp+6A0h+var_508], r13
0x14006427a  mov     [rbp+6A0h+var_500], r13
0x140064281  mov     qword ptr [rbp+6A0h+var_310], rsi
0x140064288  mov     [rbp+6A0h+var_308], r15
0x14006428f  lea     rax, aCorhdelc; "CORHDELC"
0x140064296  mov     [rbp+6A0h+var_300], rax
0x14006429d  mov     [rbp+6A0h+var_2F8], 222h
0x1400642a7  mov     [rbp+6A0h+var_2F4], 6
0x1400642b1  mov     [rbp+6A0h+var_2F0], ebx
0x1400642b7  mov     [rbp+6A0h+var_270], 1000000h
0x1400642c1  xor     edx, edx; Val
0x1400642c3  lea     r8d, [r13+78h]; Size
0x1400642c7  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x1400642ce  call    memset_0
0x1400642d3  lea     rcx, aNoMaskFlag; "No Mask Flag"
0x1400642da  lea     rax, aMaskFlagGiven; "Mask Flag given"
0x1400642e1  mov     ebx, [rbp+6A0h+arg_38]
0x1400642e7  test    ebx, ebx
0x1400642e9  cmovz   rax, rcx
0x1400642ed  mov     r15d, [rbp+6A0h+arg_30]
0x1400642f4  lea     rcx, aDeleting; "Deleting"
0x1400642fb  lea     r9, aBreaking; "Breaking"
0x140064302  test    r15d, r15d
0x140064305  cmovnz  r9, rcx
0x140064309  mov     qword ptr [rsp+7A0h+var_778], rax
0x14006430e  mov     [rsp+7A0h+var_780], r14
0x140064313  lea     r8, aSSnapshotSS; "%s snapshot %s, %s"
0x14006431a  lea     rdx, [rbp+6A0h+var_310]
0x140064321  lea     rcx, [rbp+6A0h+var_5F0]
0x140064328  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14006432d  test    r15d, r15d
0x140064330  jnz     loc_1400643D5
0x140064336  lea     rcx, [rbp+6A0h+var_518]; this
0x14006433d  call    ?Initialize@CVssDiskSignatureManager@@QEAAXXZ; CVssDiskSignatureManager::Initialize(void)
0x140064342  mov     r8b, [rbp+6A0h+var_71F]; bool
0x140064346  mov     rdx, r14; unsigned __int16 *
0x140064349  lea     rcx, [rbp+6A0h+var_518]; this
0x140064350  call    ?IsIdSafeToRevertOnVolumeDisks@CVssDiskSignatureManager@@QEAA_NPEBG_N@Z; CVssDiskSignatureManager::IsIdSafeToRevertOnVolumeDisks(ushort const *,bool)
0x140064355  test    al, al
0x140064357  jnz     short loc_1400643D5
0x140064359  mov     qword ptr [rbp+6A0h+var_310], rsi
0x140064360  lea     rbx, aCvsshardwarepr_162; "CVssHardwareProviderWrapper::ProcessDel"...
0x140064367  mov     [rbp+6A0h+var_308], rbx
0x14006436e  lea     rax, aCorhdelc; "CORHDELC"
0x140064375  mov     [rbp+6A0h+var_300], rax
0x14006437c  mov     [rbp+6A0h+var_2F8], 22Fh
0x140064386  mov     [rbp+6A0h+var_2F4], 6
0x140064390  mov     [rbp+6A0h+var_2F0], 0FFh
0x14006439a  mov     [rbp+6A0h+var_270], 1000000h
0x1400643a4  xor     edx, edx; Val
0x1400643a6  lea     r8d, [r13+78h]; Size
0x1400643aa  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x1400643b1  call    memset_0
0x1400643b6  lea     r8, aItIsNotSafeToR; "It is not safe to revert signature on o"...
0x1400643bd  lea     rdx, [rbp+6A0h+var_310]
0x1400643c4  lea     rcx, [rbp+6A0h+var_5F0]
0x1400643cb  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400643d0  jmp     loc_140065A41
0x1400643d5  test    ebx, ebx
0x1400643d7  lea     rbx, aCvsshardwarepr_162; "CVssHardwareProviderWrapper::ProcessDel"...
0x1400643de  jz      short loc_14006443D
0x1400643e0  mov     qword ptr [rbp+6A0h+var_310], rsi
0x1400643e7  mov     [rbp+6A0h+var_308], rbx
0x1400643ee  lea     rax, aCorhdelc; "CORHDELC"
0x1400643f5  mov     [rbp+6A0h+var_300], rax
0x1400643fc  mov     [rbp+6A0h+var_2F8], 235h
0x140064406  mov     [rbp+6A0h+var_2F4], edi
0x14006440c  mov     [rbp+6A0h+var_2F0], 0FFh
0x140064416  mov     [rbp+6A0h+var_270], 1000000h
0x140064420  xor     edx, edx; Val
0x140064422  lea     r8d, [rdx+78h]; Size
0x140064426  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x14006442d  call    memset_0
0x140064432  mov     r8d, 1780h
0x140064438  jmp     loc_1400644F9
0x14006443d  cmp     r15d, edi
0x140064440  jnz     short loc_14006449C
0x140064442  mov     qword ptr [rbp+6A0h+var_310], rsi
0x140064449  mov     [rbp+6A0h+var_308], rbx
0x140064450  lea     rax, aCorhdelc; "CORHDELC"
0x140064457  mov     [rbp+6A0h+var_300], rax
0x14006445e  mov     [rbp+6A0h+var_2F8], 237h
0x140064468  mov     [rbp+6A0h+var_2F4], edi
0x14006446e  mov     [rbp+6A0h+var_2F0], 0FFh
0x140064478  mov     [rbp+6A0h+var_270], 1000000h
0x140064482  xor     edx, edx; Val
0x140064484  lea     r8d, [rdx+78h]; Size
0x140064488  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x14006448f  call    memset_0
0x140064494  mov     r8d, 1782h
0x14006449a  jmp     short loc_1400644F9
0x14006449c  test    r15d, r15d
0x14006449f  jnz     short loc_14006450C
0x1400644a1  mov     qword ptr [rbp+6A0h+var_310], rsi
0x1400644a8  mov     [rbp+6A0h+var_308], rbx
0x1400644af  lea     rax, aCorhdelc; "CORHDELC"
0x1400644b6  mov     [rbp+6A0h+var_300], rax
0x1400644bd  mov     [rbp+6A0h+var_2F8], 239h
0x1400644c7  mov     [rbp+6A0h+var_2F4], edi
0x1400644cd  mov     [rbp+6A0h+var_2F0], 0FFh
0x1400644d7  mov     [rbp+6A0h+var_270], 1000000h
0x1400644e1  xor     edx, edx; Val
0x1400644e3  lea     r8d, [r15+78h]; Size
0x1400644e7  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x1400644ee  call    memset_0
0x1400644f3  mov     r8d, 1781h
0x1400644f9  lea     rdx, [rbp+6A0h+var_310]
0x140064500  lea     rcx, [rbp+6A0h+var_5F0]
0x140064507  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x14006450c  mov     qword ptr [rbp+6A0h+var_310], rsi
0x140064513  mov     [rbp+6A0h+var_308], rbx
0x14006451a  lea     rax, aCorhdelc; "CORHDELC"
0x140064521  mov     [rbp+6A0h+var_300], rax
0x140064528  mov     [rbp+6A0h+var_2F8], 23Bh
0x140064532  mov     [rbp+6A0h+var_2F4], edi
0x140064538  mov     [rbp+6A0h+var_2F0], 0FFh
0x140064542  mov     [rbp+6A0h+var_270], 1000000h
0x14006454c  xor     edx, edx; Val
0x14006454e  lea     r8d, [rdx+78h]; Size
0x140064552  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x140064559  call    memset_0
0x14006455e  mov     r9, r14
0x140064561  mov     r8d, 1392h
0x140064567  lea     rdx, [rbp+6A0h+var_310]
0x14006456e  lea     rcx, [rbp+6A0h+var_5F0]
0x140064575  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x14006457a  mov     qword ptr [rbp+6A0h+var_310], rsi
0x140064581  mov     [rbp+6A0h+var_308], rbx
0x140064588  lea     rax, aCorhdelc; "CORHDELC"
0x14006458f  mov     [rbp+6A0h+var_300], rax
0x140064596  mov     [rbp+6A0h+var_2F8], 23Ch
0x1400645a0  mov     [rbp+6A0h+var_2F4], edi
0x1400645a6  mov     [rbp+6A0h+var_2F0], 0FFh
0x1400645b0  mov     [rbp+6A0h+var_270], 1000000h
0x1400645ba  xor     edx, edx; Val
0x1400645bc  lea     r8d, [rdx+78h]; Size
0x1400645c0  lea     rcx, [rbp+6A0h+var_2E8]; void *
0x1400645c7  call    memset_0
0x1400645cc  movzx   eax, byte ptr [rbp+6A0h+var_358+0Fh]
0x1400645d3  movzx   ecx, byte ptr [rbp+6A0h+var_358+0Eh]
0x1400645da  movzx   edx, byte ptr [rbp+6A0h+var_358+0Dh]
0x1400645e1  movzx   r8d, byte ptr [rbp+6A0h+var_358+0Ch]
0x1400645e9  movzx   r9d, byte ptr [rbp+6A0h+var_358+0Bh]
0x1400645f1  movzx   r10d, byte ptr [rbp+6A0h+var_358+0Ah]
0x1400645f9  movzx   r11d, byte ptr [rbp+6A0h+var_358+9]
0x140064601  movzx   ebx, byte ptr [rbp+6A0h+var_358+8]
0x140064608  movzx   edi, word ptr [rbp+6A0h+var_358+6]
0x14006460f  movzx   esi, word ptr [rbp+6A0h+var_358+4]
0x140064616  mov     [rsp+7A0h+var_730], eax
0x14006461a  mov     [rsp+7A0h+var_738], ecx
0x14006461e  mov     [rsp+7A0h+var_740], edx
0x140064622  mov     [rsp+7A0h+var_748], r8d
0x140064627  mov     [rsp+7A0h+var_750], r9d
0x14006462c  mov     [rsp+7A0h+var_758], r10d
0x140064631  mov     [rsp+7A0h+var_760], r11d
0x140064636  mov     [rsp+7A0h+var_768], ebx
0x14006463a  mov     dword ptr [rsp+7A0h+var_770], edi
0x14006463e  mov     dword ptr [rsp+7A0h+var_778], esi
0x140064642  mov     eax, dword ptr [rbp+6A0h+var_358]
0x140064648  mov     dword ptr [rsp+7A0h+var_780], eax
  ... truncated ...
```
