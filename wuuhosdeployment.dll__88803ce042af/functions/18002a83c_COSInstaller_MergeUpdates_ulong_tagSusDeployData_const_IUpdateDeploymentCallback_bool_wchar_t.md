# COSInstaller::MergeUpdates(ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,bool *,wchar_t * *)

- ea: `0x18002a83c`
- end: `0x18002b2ce`
- name: `?MergeUpdates@COSInstaller@@AEAAJKQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@PEA_NPEAPEA_W@Z`
- size: `2706`
- prototype: `__int64 __fastcall(COSInstaller *__hidden this, unsigned int, struct tagSusDeployData *const, struct IUpdateDeploymentCallback *, bool *, wchar_t **)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800276d0`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000a448`
- `0x18000a4f4`
- `0x18000aecc`
- `0x18000b3ac`
- `0x18000b480`
- `0x18000b658`
- `0x18000c634`
- `0x18000d904`
- `0x18000e05c`
- `0x180018f18`
- `0x18001952c`
- `0x180019cc4`
- `0x180019e00`
- `0x18001a8b8`
- `0x1800230c0`
- `0x180026964`
- `0x18002a83c`
- `0x18002b2d4`
- `0x18002b4fc`
- `0x180031890`
- `0x180042630`
- `0x180042a24`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18002aa0f`
- `RPCRT4!UuidFromStringW` at `0x18002aa0f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ad3d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ad3d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b20c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b20c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002b020`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002b020`

## string_xrefs

- `0x18002a959`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002aeb7`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002aefe`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002b05e`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002b102`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002b142`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002b187`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002b116`: `ParseHandlerXml`
- `0x18002aa5a`: `Skipping merging UUP on Prem language specific update ID: %ws`
- `0x18002a922`: `CreateMergedSandboxDir`
- `0x18002ac77`: `Merge failed for update ID: %ws.%d`
- `0x18002b245`: `No updates were merged`

## pseudocode

```c
__int64 __fastcall COSInstaller::MergeUpdates(
        COSInstaller *this,
        unsigned int a2,
        struct tagSusDeployData *const a3,
        struct IUpdateDeploymentCallback *a4,
        bool *a5,
        wchar_t **a6)
{
  struct tagSusDeployData *v6; // rbx
  wchar_t *v8; // rsi
  OLECHAR *v9; // r12
  WCHAR *v10; // r13
  __int64 v11; // rdx
  int FilesPerPatchType; // r15d
  COSInstaller *v13; // rcx
  unsigned __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // r15
  struct tagDSUpdateMetadata *v17; // rdi
  wchar_t *v18; // r14
  __int64 v19; // rbx
  struct tagSusDeployData *v20; // rax
  unsigned __int16 *v21; // rcx
  unsigned int v22; // eax
  struct tagDSUpdateMetadata *v23; // r15
  wchar_t **v24; // r8
  __int64 v25; // r15
  char *v26; // rax
  char IsEnabled; // al
  struct tagDSFile **v28; // rax
  __int64 v29; // r15
  __int64 v30; // rdx
  const struct std::nothrow_t *v31; // rdx
  BSTR v32; // rax
  int v33; // eax
  int CombinedPath; // eax
  int v35; // eax
  GUID *v36; // r15
  const wchar_t **v37; // rax
  const struct std::nothrow_t *v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  unsigned int v41; // edi
  unsigned int v42; // ebx
  unsigned int v43; // esi
  __int64 v44; // r14
  __int64 v45; // r13
  __int64 v46; // r15
  const WCHAR *v47; // rbx
  LPWSTR v48; // rcx
  WCHAR i; // ax
  const wchar_t *v50; // rdi
  int v51; // eax
  int v52; // eax
  __int64 v53; // rdi
  BSTR *v54; // rbx
  int v55; // eax
  unsigned int *v57; // [rsp+20h] [rbp-E0h]
  struct tagDSFile ***v58; // [rsp+38h] [rbp-C8h]
  int v59; // [rsp+38h] [rbp-C8h]
  int v60; // [rsp+50h] [rbp-B0h]
  int v61; // [rsp+50h] [rbp-B0h]
  GUID *rguid; // [rsp+60h] [rbp-A0h] BYREF
  const struct tagDSFile *v64; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v65; // [rsp+70h] [rbp-90h]
  void *v66; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t **v67; // [rsp+80h] [rbp-80h] BYREF
  __int64 v68; // [rsp+88h] [rbp-78h]
  LPCWSTR lpNewFileName; // [rsp+90h] [rbp-70h] BYREF
  void *lpMem; // [rsp+98h] [rbp-68h] BYREF
  void *v71; // [rsp+A0h] [rbp-60h] BYREF
  struct tagDSUpdateMetadata *v72; // [rsp+A8h] [rbp-58h] BYREF
  struct tagDSFile **v73; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR *psz; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *v75; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v76; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *v77; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v78; // [rsp+D8h] [rbp-28h] BYREF
  GUID v79; // [rsp+E0h] [rbp-20h]
  __int64 v80; // [rsp+F0h] [rbp-10h]
  const struct tagDSGlobalUpdateId *v81; // [rsp+F8h] [rbp-8h]
  bool *v82; // [rsp+100h] [rbp+0h]
  wchar_t **v83; // [rsp+108h] [rbp+8h]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int128 v85; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v86[112]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v87[14]; // [rsp+1A0h] [rbp+A0h] BYREF
  struct tagDSFile ***v88; // [rsp+210h] [rbp+110h] BYREF
  COSInstaller *v89; // [rsp+218h] [rbp+118h] BYREF
  void **v90; // [rsp+220h] [rbp+120h] BYREF
  __int64 v91; // [rsp+228h] [rbp+128h]
  __int64 v92; // [rsp+230h] [rbp+130h]
  void **v93; // [rsp+238h] [rbp+138h] BYREF
  __int64 v94; // [rsp+240h] [rbp+140h]
  __int64 v95; // [rsp+248h] [rbp+148h]
  UUID Uuid; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v97[112]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v6 = a3;
  v65 = a2;
  v89 = this;
  v82 = a5;
  v83 = a6;
  v8 = 0;
  v9 = 0;
  psz = 0;
  v84 = 0;
  v10 = 0;
  lpNewFileName = 0;
  v93 = &CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable';
  v94 = 0;
  v95 = 0;
  v90 = &CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable';
  v91 = 0;
  v92 = 0;
  if ( !a5 )
  {
    v11 = 1664;
LABEL_5:
    FilesPerPatchType = -2147467261;
    goto LABEL_8;
  }
  if ( !a6 )
  {
    v11 = 1665;
    goto LABEL_5;
  }
  *a5 = 0;
  FilesPerPatchType = COSInstaller::CreateMergedSandboxDir((COSInstaller *)a6, &psz);
  v60 = FilesPerPatchType;
  if ( FilesPerPatchType < 0 )
  {
    LODWORD(v57) = FilesPerPatchType;
    WUTrace(0, 0, 4096, 2);
    v11 = 1674;
    v9 = psz;
    goto LABEL_8;
  }
  v15 = 0;
  HIDWORD(v64) = 0;
  v9 = psz;
  if ( a2 )
  {
    while ( 1 )
    {
      v16 = 296 * v15;
      v68 = 296 * v15;
      v72 = (struct tagDSUpdateMetadata *)*((_QWORD *)v6 + 37 * v15 + 7);
      v88 = 0;
      memset(v87, 0, 0x68u);
      rguid = (GUID *)&CONTAINING_RECORD(v72, GUID, Data4)->Data4[4];
      Trace::UpdateIdToString::UpdateIdToString(
        (Trace::UpdateIdToString *)v97,
        (struct tagDSUpdateMetadata *)((char *)v72 + 4));
      LODWORD(v64) = 0;
      v66 = 0;
      LODWORD(v73) = 0;
      v71 = 0;
      v17 = 0;
      v77 = 0;
      v18 = 0;
      v75 = 0;
      lpMem = 0;
      v19 = 0;
      v76 = 0;
      Uuid = 0;
      v20 = a3;
      v21 = *(unsigned __int16 **)((char *)a3 + v16);
      if ( v21 && *v21 )
      {
        v22 = UuidFromStringW(v21, &Uuid);
        if ( v22 )
        {
          FilesPerPatchType = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x6A0,
                                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
                                (const char *)v22,
                                (unsigned int)v57);
          goto LABEL_101;
        }
        v20 = a3;
      }
      v81 = (struct tagSusDeployData *)((char *)v20 + v16 + 32);
      v23 = v72;
      if ( IsUUPOnPremLangSpecificChildUpdate(v72, v81, &Uuid) )
      {
        Trace::UpdateIdToString::UpdateIdToString(
          (Trace::UpdateIdToString *)v86,
          (const struct tagDSGlobalUpdateId *)rguid);
        v8 = 0;
        v57 = 0;
        WUTrace(0, 0, 4096, 4);
      }
      else
      {
        FilesPerPatchType = OSDeploymentHelper::GetFilesPerPatchType(
                              (OSDeploymentHelper *)*((unsigned int *)v23 + 116),
                              *((_QWORD *)v23 + 59),
                              (struct tagDSFile *const)&v88,
                              &v64,
                              (unsigned int *)&v66,
                              &v73,
                              (unsigned int *)&v71,
                              v58);
        if ( FilesPerPatchType < 0 )
        {
          WUTrace(0, 0, 4096, 2);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6BA,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
            (const char *)(unsigned int)FilesPerPatchType,
            FilesPerPatchType);
          goto LABEL_101;
        }
        FilesPerPatchType = OSDeploymentHelper::ParseHandlerXml(
                              (struct tagDSUpdateMetadata *)((char *)v72 + 544),
                              (const struct tagDSDataBlob *)&v77,
                              v24);
        if ( FilesPerPatchType < 0 )
        {
          WUTrace(0, 0, 4096, 2);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6C2,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
            (const char *)(unsigned int)FilesPerPatchType,
            FilesPerPatchType);
          v17 = (struct tagDSUpdateMetadata *)v77;
          goto LABEL_101;
        }
        v87[1] = v97;
        v25 = v68;
        v87[2] = *(_QWORD *)((char *)a3 + v68 + 104);
        v87[3] = *(_QWORD *)((char *)a3 + v68 + 248);
        v87[0] = *(_QWORD *)((char *)a3 + v68 + 256);
        v26 = (char *)v87[4];
        if ( *((_BYTE *)a3 + v68 + 112) )
          v26 = (char *)a3 + v68 + 112;
        v87[4] = v26;
        v78 = 0;
        v79 = GUID_NULL;
        v80 = 0;
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl'::`2'::impl);
        v17 = (struct tagDSUpdateMetadata *)v77;
        if ( IsEnabled )
        {
          FilesPerPatchType = OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(
                                (struct _GUID *)&v78,
                                rguid,
                                (void **)0x493E0);
          if ( FilesPerPatchType < 0 )
          {
            v39 = 1748;
            goto LABEL_98;
          }
          v25 = v68;
        }
        rguid = (GUID *)v87;
        v85 = xmmword_180076898;
        v72 = v17;
        if ( v88 )
          v28 = v88[9];
        else
          v28 = 0;
        v73 = v28;
        v67 = (const wchar_t **)((char *)a3 + v25 + 16);
        FilesPerPatchType = Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,OSDeploymentHelper::CDeploymentSessionWrapper,wchar_t * const &,wchar_t * const &,wchar_t * const &,int,std::nullptr_t,_GUID,unsigned long const &,tagOptionalSessionInfo5 *>(
                              (unsigned int)&v76,
                              (int)v25 + (int)a3 + 16,
                              (unsigned int)&v73,
                              (unsigned int)&v72,
                              (__int64)&v64,
                              (__int64)&v66,
                              (__int64)&v85,
                              v59,
                              (__int64)&rguid);
        v19 = v76;
        if ( FilesPerPatchType < 0 )
        {
          v39 = 1760;
LABEL_98:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v39,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
            (const char *)(unsigned int)FilesPerPatchType,
            (int)v57);
LABEL_63:
          OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v78);
LABEL_101:
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v8 )
            CSusBaseAllocTag<942762101>::operator delete(v8);
          if ( v18 )
            CSusBaseAllocTag<942762101>::operator delete(v18);
          if ( v17 )
            CSusBaseAllocTag<942762101>::operator delete(v17);
          if ( v71 )
            operator delete(v71, v38);
          if ( v66 )
            operator delete(v66, v38);
          goto LABEL_121;
        }
        v60 = (*(__int64 (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)(v76 + 8) + 72LL))(v76 + 8, v9);
        v29 = v68;
        v30 = *(_QWORD *)((char *)a3 + v68 + 56);
        if ( v60 >= 0 )
        {
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*((_QWORD *)v89 + 15) + 8LL))(
            (__int64)v89 + 120,
            v30 + 4,
            0);
          (*(void (__fastcall **)(__int64, const struct tagDSGlobalUpdateId *, _QWORD))(*((_QWORD *)v89 + 18) + 8LL))(
            (__int64)v89 + 144,
            v81,
            0);
          v32 = SysAllocString(v9);
          *(_QWORD *)((char *)a3 + v29 + 24) = v32;
          if ( !v32 )
          {
            FilesPerPatchType = -2147024882;
            v39 = 1793;
            goto LABEL_98;
          }
          v33 = CreateCombinedPath(*v67, L"Metadata", &v75);
          v18 = v75;
          if ( v33 < 0 )
          {
            FilesPerPatchType = v33;
            v39 = 1798;
            goto LABEL_98;
          }
          CombinedPath = CreateCombinedPath(v75, (const wchar_t *)v17, (wchar_t **)&lpMem);
          v8 = (wchar_t *)lpMem;
          if ( CombinedPath < 0 )
          {
            FilesPerPatchType = CombinedPath;
            v39 = 1802;
            goto LABEL_98;
          }
          if ( (int)CheckIfFileExists((const wchar_t *)lpMem) >= 0 && v88 )
          {
            rguid = 0;
            v35 = CreateCombinedPath(
                    *(const wchar_t **)((char *)a3 + v29 + 16),
                    (const wchar_t *)v88[9],
                    (wchar_t **)&rguid);
            v36 = rguid;
            if ( v35 < 0 )
            {
              v40 = 1811;
              goto LABEL_60;
            }
            v35 = CheckIfFileExists((const wchar_t *)rguid);
            if ( v35 < 0 )
            {
              v40 = 1813;
LABEL_60:
              v61 = v35;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v40,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
                (const char *)(unsigned int)v35,
                (int)v57);
              if ( v36 )
                CSusBaseAllocTag<942762101>::operator delete(v36);
              FilesPerPatchType = v61;
              goto LABEL_63;
            }
            v37 = (const wchar_t **)v8;
            v8 = 0;
            lpMem = 0;
            v67 = v37;
            CSusArrayList<tagSusFileRequest *,CFileListOps>::Add(&v93, &v67, 0);
            v67 = (const wchar_t **)v36;
            CSusArrayList<tagSusFileRequest *,CFileListOps>::Add(&v90, &v67, 0);
          }
          OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v78);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v8 )
            CSusBaseAllocTag<942762101>::operator delete(v8);
          v8 = 0;
          if ( v18 )
            CSusBaseAllocTag<942762101>::operator delete(v18);
        }
        else
        {
          LODWORD(v58) = *(_DWORD *)(v30 + 20);
          Trace::GuidToString::GuidToString((Trace::GuidToString *)v86, (const struct _GUID *)(v30 + 4));
          FilesPerPatchType = v60;
          LODWORD(v57) = v60;
          WUTrace(0, 0, 4096, 3);
          if ( v60 != -2145079036 )
          {
            v39 = 1783;
            goto LABEL_98;
          }
          v8 = 0;
          v57 = 0;
          WUTrace(0, 0, 4096, 4);
          v60 = 0;
          OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v78);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        if ( v17 )
          CSusBaseAllocTag<942762101>::operator delete(v17);
        if ( v71 )
          operator delete(v71, v31);
        v13 = (COSInstaller *)v66;
        if ( v66 )
          operator delete(v66, v31);
      }
      v15 = (unsigned int)(HIDWORD(v64) + 1);
      HIDWORD(v64) = v15;
      if ( (unsigned int)v15 >= v65 )
      {
        v41 = HIDWORD(v95);
        if ( HIDWORD(v95) < 2 )
        {
          v53 = v65;
          if ( v65 )
          {
            v54 = (BSTR *)((char *)a3 + 24);
            do
            {
              SysFreeString(*v54);
              *v54 = 0;
              v54 += 37;
              --v53;
            }
            while ( v53 );
          }
          break;
        }
        *v82 = 1;
        v42 = 0;
        if ( v41 )
        {
          v43 = 1;
          v44 = v41;
          v45 = v94;
          do
          {
            v88 = 0;
            v89 = 0;
            if ( v42 < v41 )
            {
              v46 = *(_QWORD *)(v45 + 8LL * v42);
              if ( (int)GetFileVersion(v46, &v88) >= 0
                && v43 < v41
                && (int)GetFileVersion(v46, &v89) >= 0
                && v88 != (struct tagDSFile ***)v89
                && v88 < (struct tagDSFile ***)v89 )
              {
                v42 = v43;
              }
            }
            ++v43;
            --v44;
          }
          while ( v44 );
          v10 = (WCHAR *)lpNewFileName;
          v8 = 0;
        }
        if ( v42 >= HIDWORD(v92) )
        {
          FilesPerPatchType = -2145124345;
          v11 = 1868;
          goto LABEL_8;
        }
        _mm_lfence();
        v47 = *(const WCHAR **)(v91 + 8LL * v42);
        if ( !v47 )
        {
          FilesPerPatchType = -2147467261;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3E7,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
            (const char *)0x80004003LL,
            (int)v57);
          v11 = 1871;
          goto LABEL_8;
        }
        v48 = (LPWSTR)v47;
        for ( i = *v47; i; i = *v48 )
        {
          if ( i == 92 || i == 47 )
            v8 = v48;
          v48 = CharNextW(v48);
        }
        v50 = v8 + 1;
        if ( !v8 )
          v50 = v47;
        v51 = CreateCombinedPath(v9, v50, (wchar_t **)&lpNewFileName);
        FilesPerPatchType = v51;
        if ( v51 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x753,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
            (const char *)(unsigned int)v51,
            (int)v57);
          v10 = (WCHAR *)lpNewFileName;
          goto LABEL_121;
        }
        v10 = (WCHAR *)lpNewFileName;
        SusCopyFileRetryIfSharingViolation(v47, lpNewFileName, 0, 0, v57);
        v52 = DuplicateString<wchar_t const *,wchar_t *>(v50, v83);
        FilesPerPatchType = v52;
        if ( v52 < 0 )
        {
          v14 = (unsigned int)v52;
          v11 = 1883;
          goto LABEL_9;
        }
        FilesPerPatchType = v60;
        if ( v60 < 0 )
        {
          v11 = 1885;
          goto LABEL_8;
        }
LABEL_120:
        FilesPerPatchType = 0;
        goto LABEL_121;
      }
      v6 = a3;
    }
  }
  v55 = COSInstaller::DeleteMergedSandboxDir(v13, v9);
  FilesPerPatchType = v55;
  if ( v55 >= 0 )
  {
    WUTrace(0, 0, 4096, 4);
    goto LABEL_120;
  }
  if ( (unsigned int)(v55 + 2147024894) > 1 )
  {
    v11 = 1833;
LABEL_8:
    v14 = (unsigned int)FilesPerPatchType;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v14,
      (int)v57);
  }
LABEL_121:
  CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>(&v90);
  CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>(&v93);
  if ( v10 )
    CSusBaseAllocTag<942762101>::operator delete(v10);
  if ( v9 )
    CSusBaseAllocTag<942762101>::operator delete(v9);
  return (unsigned int)FilesPerPatchType;
}

```

## disassembly

```asm
0x18002a83c  mov     [rsp-8+arg_8], rbx
0x18002a841  push    rbp
0x18002a842  push    rsi
0x18002a843  push    rdi
0x18002a844  push    r12
0x18002a846  push    r13
0x18002a848  push    r14
0x18002a84a  push    r15
0x18002a84c  lea     rbp, [rsp-1E0h]
0x18002a854  sub     rsp, 2E0h
0x18002a85b  mov     rax, cs:__security_cookie
0x18002a862  xor     rax, rsp
0x18002a865  mov     [rbp+210h+var_40], rax
0x18002a86c  mov     rbx, r8
0x18002a86f  mov     [rsp+310h+var_2B8], rbx
0x18002a874  mov     edi, edx
0x18002a876  mov     [rsp+310h+var_2A0], edi
0x18002a87a  mov     [rbp+210h+var_F8], rcx
0x18002a881  mov     rax, [rbp+210h+arg_20]
0x18002a888  mov     [rbp+210h+var_210], rax
0x18002a88c  mov     rcx, [rbp+210h+arg_28]; this
0x18002a893  mov     [rbp+210h+var_208], rcx
0x18002a897  xor     esi, esi
0x18002a899  mov     r12d, esi
0x18002a89c  mov     [rbp+210h+psz], rsi
0x18002a8a0  mov     [rbp+210h+var_200], rsi
0x18002a8a4  mov     r13d, esi
0x18002a8a7  mov     [rbp+210h+lpNewFileName], rsi
0x18002a8ab  xorps   xmm0, xmm0
0x18002a8ae  movups  [rbp+210h+var_D8], xmm0
0x18002a8b5  lea     r8, ??_7?$CSusArrayList@PEA_WV?$CSusArrayListItemOpSusFree@PEA_W@@@@6B@; const CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable'
0x18002a8bc  mov     qword ptr [rbp+210h+var_D8], r8
0x18002a8c3  mov     qword ptr [rbp+210h+var_D8+8], rsi
0x18002a8ca  mov     [rbp+210h+var_C8], rsi
0x18002a8d1  movups  [rbp+210h+var_F0], xmm0
0x18002a8d8  mov     qword ptr [rbp+210h+var_F0], r8
0x18002a8df  mov     qword ptr [rbp+210h+var_F0+8], rsi
0x18002a8e6  mov     [rbp+210h+var_E0], rsi
0x18002a8ed  test    rax, rax
0x18002a8f0  jnz     short loc_18002A8F9
0x18002a8f2  mov     edx, 680h
0x18002a8f7  jmp     short loc_18002A903
0x18002a8f9  test    rcx, rcx
0x18002a8fc  jnz     short loc_18002A90B
0x18002a8fe  mov     edx, 681h
0x18002a903  mov     r15d, 80004003h
0x18002a909  jmp     short loc_18002A94F
0x18002a90b  mov     [rax], sil
0x18002a90e  lea     rdx, [rbp+210h+psz]; wchar_t **
0x18002a912  call    ?CreateMergedSandboxDir@COSInstaller@@AEAAJPEAPEA_W@Z; COSInstaller::CreateMergedSandboxDir(wchar_t * *)
0x18002a917  mov     r15d, eax
0x18002a91a  mov     [rsp+310h+var_2C0], eax
0x18002a91e  test    eax, eax
0x18002a920  jns     short loc_18002A96A
0x18002a922  lea     rax, aCreatemergedsa; "CreateMergedSandboxDir"
0x18002a929  mov     [rsp+310h+var_2E8], rax
0x18002a92e  mov     dword ptr [rsp+310h+var_2F0], r15d; int
0x18002a933  xor     edx, edx
0x18002a935  xor     ecx, ecx
0x18002a937  lea     r9d, [rdx+2]
0x18002a93b  mov     r8d, 1000h
0x18002a941  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002a946  mov     edx, 68Ah; void *
0x18002a94b  mov     r12, [rbp+210h+psz]
0x18002a94f  mov     r9d, r15d; char *
0x18002a952  mov     rcx, [rbp+218h]; this
0x18002a959  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002a960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a965  jmp     loc_18002B26C
0x18002a96a  mov     eax, esi
0x18002a96c  mov     dword ptr [rsp+310h+var_2A8+4], eax
0x18002a970  mov     r12, [rbp+210h+psz]
0x18002a974  test    edi, edi
0x18002a976  jz      loc_18002B222
0x18002a97c  imul    r15, rax, 128h
0x18002a983  mov     [rbp+210h+var_288], r15
0x18002a987  mov     rbx, [r15+rbx+38h]
0x18002a98c  mov     [rbp+210h+var_268], rbx
0x18002a990  mov     [rbp+210h+var_100], rsi
0x18002a997  xor     edx, edx; Val
0x18002a999  lea     r8d, [rdx+68h]; Size
0x18002a99d  lea     rcx, [rbp+210h+var_170]; void *
0x18002a9a4  call    memset
0x18002a9a9  lea     rax, [rbx+4]
0x18002a9ad  mov     [rsp+310h+rguid], rax
0x18002a9b2  mov     rdx, rax; struct tagDSGlobalUpdateId *
0x18002a9b5  lea     rcx, [rbp+210h+var_B0]; this
0x18002a9bc  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18002a9c1  mov     dword ptr [rsp+310h+var_2A8], esi
0x18002a9c5  mov     [rsp+310h+var_298], rsi
0x18002a9ca  mov     dword ptr [rbp+210h+var_260], esi
0x18002a9cd  mov     [rbp+210h+var_270], rsi
0x18002a9d1  mov     rdi, rsi
0x18002a9d4  mov     [rbp+210h+var_240], rsi
0x18002a9d8  mov     r14, rsi
0x18002a9db  mov     [rbp+210h+var_250], rsi
0x18002a9df  mov     [rbp+210h+lpMem], rsi
0x18002a9e3  xor     edx, edx
0x18002a9e5  mov     ebx, edx
0x18002a9e7  mov     [rbp+210h+var_248], rdx
0x18002a9eb  xorps   xmm0, xmm0
0x18002a9ee  movups  xmmword ptr [rbp+210h+Uuid.Data1], xmm0
0x18002a9f5  mov     rax, [rsp+310h+var_2B8]
0x18002a9fa  mov     rcx, [r15+rax]; StringUuid
0x18002a9fe  test    rcx, rcx
0x18002aa01  jz      short loc_18002AA22
0x18002aa03  cmp     [rcx], dx
0x18002aa06  jz      short loc_18002AA22
0x18002aa08  lea     rdx, [rbp+210h+Uuid]; Uuid
0x18002aa0f  call    cs:__imp_UuidFromStringW
0x18002aa15  test    eax, eax
0x18002aa17  jnz     loc_18002AEAD
0x18002aa1d  mov     rax, [rsp+310h+var_2B8]
0x18002aa22  add     r15, 20h ; ' '
0x18002aa26  add     rax, r15
0x18002aa29  mov     [rbp+210h+var_218], rax
0x18002aa2d  lea     r8, [rbp+210h+Uuid]; struct _GUID *
0x18002aa34  mov     rdx, rax; struct tagDSGlobalUpdateId *
0x18002aa37  mov     r15, [rbp+210h+var_268]
0x18002aa3b  mov     rcx, r15; struct tagDSUpdateMetadata *
0x18002aa3e  call    ?IsUUPOnPremLangSpecificChildUpdate@@YA_NAEBUtagDSUpdateMetadata@@AEBUtagDSGlobalUpdateId@@AEBU_GUID@@@Z; IsUUPOnPremLangSpecificChildUpdate(tagDSUpdateMetadata const &,tagDSGlobalUpdateId const &,_GUID const &)
0x18002aa43  test    al, al
0x18002aa45  jz      short loc_18002AA86
0x18002aa47  mov     rdx, [rsp+310h+rguid]; struct tagDSGlobalUpdateId *
0x18002aa4c  lea     rcx, [rbp+210h+var_1E0]; this
0x18002aa50  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18002aa55  mov     [rsp+310h+var_2E0], rax
0x18002aa5a  lea     rax, aSkippingMergin; "Skipping merging UUP on Prem language s"...
0x18002aa61  mov     [rsp+310h+var_2E8], rax
0x18002aa66  xor     esi, esi
0x18002aa68  mov     [rsp+310h+var_2F0], rsi
0x18002aa6d  xor     edx, edx
0x18002aa6f  xor     ecx, ecx
0x18002aa71  lea     r9d, [rsi+4]
0x18002aa75  mov     r8d, 1000h
0x18002aa7b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002aa80  nop
0x18002aa81  jmp     loc_18002AE8F
0x18002aa86  lea     rax, [rbp+210h+var_270]
0x18002aa8a  mov     [rsp+310h+var_2E0], rax; unsigned int *
0x18002aa8f  lea     rax, [rbp+210h+var_260]
0x18002aa93  mov     [rsp+310h+var_2E8], rax; struct tagDSFile ***
0x18002aa98  lea     rax, [rsp+310h+var_298]
0x18002aa9d  mov     [rsp+310h+var_2F0], rax; unsigned int *
0x18002aaa2  lea     r9, [rsp+310h+var_2A8]; struct tagDSFile **
0x18002aaa7  lea     r8, [rbp+210h+var_100]; struct tagDSFile *
0x18002aaae  mov     rdx, [r15+1D8h]; unsigned int
0x18002aab5  mov     ecx, [r15+1D0h]; this
0x18002aabc  call    ?GetFilesPerPatchType@OSDeploymentHelper@@YAJKQEAUtagDSFile@@PEAPEBU2@PEAKPEAPEAPEAU2@23@Z; OSDeploymentHelper::GetFilesPerPatchType(ulong,tagDSFile * const,tagDSFile const * *,ulong *,tagDSFile * * *,ulong *,tagDSFile * * *)
0x18002aac1  mov     r15d, eax
0x18002aac4  test    eax, eax
0x18002aac6  js      loc_18002B159
0x18002aacc  mov     rcx, [rbp+210h+var_268]
0x18002aad0  add     rcx, 220h; this
0x18002aad7  lea     rdx, [rbp+210h+var_240]; struct tagDSDataBlob *
0x18002aadb  call    ?ParseHandlerXml@OSDeploymentHelper@@YAJAEBUtagDSDataBlob@@PEAPEA_W@Z; OSDeploymentHelper::ParseHandlerXml(tagDSDataBlob const &,wchar_t * *)
0x18002aae0  mov     r15d, eax
0x18002aae3  xor     edx, edx
0x18002aae5  test    eax, eax
0x18002aae7  js      loc_18002B116
0x18002aaed  lea     rax, [rbp+210h+var_B0]
0x18002aaf4  mov     [rbp+210h+var_168], rax
0x18002aafb  mov     r15, [rbp+210h+var_288]
0x18002aaff  mov     rcx, [rsp+310h+var_2B8]
0x18002ab04  mov     rax, [r15+rcx+68h]
0x18002ab09  mov     [rbp+210h+var_160], rax
0x18002ab10  mov     rax, [r15+rcx+0F8h]
0x18002ab18  mov     [rbp+210h+var_158], rax
0x18002ab1f  mov     rax, [r15+rcx+100h]
0x18002ab27  mov     [rbp+210h+var_170], rax
0x18002ab2e  add     rcx, 70h ; 'p'
0x18002ab32  add     rcx, r15
0x18002ab35  mov     rax, [rbp+210h+var_150]
0x18002ab3c  cmp     [rcx], dl
0x18002ab3e  cmovnz  rax, rcx
0x18002ab42  mov     [rbp+210h+var_150], rax
0x18002ab49  xorps   xmm0, xmm0
0x18002ab4c  movups  xmmword ptr [rbp+210h+var_238.Data1], xmm0
0x18002ab50  movups  [rbp+210h+var_228], xmm0
0x18002ab54  mov     qword ptr [rbp+210h+var_238.Data1], rdx
0x18002ab58  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18002ab5f  movdqu  xmmword ptr [rbp+210h+var_238.Data4], xmm1
0x18002ab64  mov     qword ptr [rbp+210h+var_228+8], rdx
0x18002ab68  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl(void)'::`2'::impl
0x18002ab6f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(void)
0x18002ab74  mov     rdi, [rbp+210h+var_240]
0x18002ab78  test    al, al
0x18002ab7a  jz      short loc_18002AB9F
0x18002ab7c  mov     r8d, 493E0h; void **
0x18002ab82  mov     rdx, [rsp+310h+rguid]; rguid
0x18002ab87  lea     rcx, [rbp+210h+var_238]; this
0x18002ab8b  call    ?Acquire@SandboxAccessMutexGuard@OSDeploymentHelper@@QEAAJAEBU_GUID@@K@Z; OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(_GUID const &,ulong)
0x18002ab90  mov     r15d, eax
0x18002ab93  test    eax, eax
0x18002ab95  js      loc_18002AED0
0x18002ab9b  mov     r15, [rbp+210h+var_288]
0x18002ab9f  lea     rax, [rbp+210h+var_170]
0x18002aba6  mov     [rsp+310h+rguid], rax
0x18002abab  movups  xmm0, cs:xmmword_180076898
0x18002abb2  movdqu  [rbp+210h+var_1F8], xmm0
0x18002abb7  mov     [rbp+210h+var_268], rdi
0x18002abbb  mov     rax, [rbp+210h+var_100]
0x18002abc2  xor     ebx, ebx
0x18002abc4  test    rax, rax
0x18002abc7  jnz     short loc_18002ABCD
0x18002abc9  mov     eax, ebx
0x18002abcb  jmp     short loc_18002ABD1
0x18002abcd  mov     rax, [rax+48h]
0x18002abd1  mov     [rbp+210h+var_260], rax
0x18002abd5  mov     rax, [rsp+310h+var_2B8]
0x18002abda  add     rax, 10h
0x18002abde  add     rax, r15
0x18002abe1  mov     [rbp+210h+var_290], rax
0x18002abe5  lea     rcx, [rsp+310h+rguid]
0x18002abea  mov     [rsp+310h+var_2D0], rcx
0x18002abef  lea     rcx, [rbp+210h+var_1F8]
0x18002abf3  mov     [rsp+310h+var_2E0], rcx
0x18002abf8  lea     rcx, [rsp+310h+var_298]
0x18002abfd  mov     [rsp+310h+var_2E8], rcx
0x18002ac02  lea     rcx, [rsp+310h+var_2A8]
0x18002ac07  mov     [rsp+310h+var_2F0], rcx; int
0x18002ac0c  lea     r9, [rbp+210h+var_268]
0x18002ac10  lea     r8, [rbp+210h+var_260]
0x18002ac14  mov     rdx, rax
0x18002ac17  lea     rcx, [rbp+210h+var_248]
0x18002ac1b  call    ??$MakeAndInitialize@VCDeploymentSessionWrapper@OSDeploymentHelper@@V12@AEBQEA_WAEBQEA_WAEBQEA_WH$$TU_GUID@@AEBKPEAUtagOptionalSessionInfo5@@@Details@WRL@Microsoft@@YAJPEAPEAVCDeploymentSessionWrapper@OSDeploymentHelper@@AEBQEA_W11$$QEAH$$QEA$$T$$QEAU_GUID@@AEBK$$QEAPEAUtagOptionalSessionInfo5@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,OSDeploymentHelper::CDeploymentSessionWrapper,wchar_t * const &,wchar_t * const &,wchar_t * const &,int,std::nullptr_t,_GUID,ulong const &,tagOptionalSessionInfo5 *>(OSDeploymentHelper::CDeploymentSessionWrapper * *,wchar_t * const &,wchar_t * const &,wchar_t * const &,int &&,$$T$$QEAU_GUID &&,ulong const &,tagOptionalSessionInfo5 * &&)
0x18002ac20  mov     r15d, eax
0x18002ac23  mov     rbx, [rbp+210h+var_248]
0x18002ac27  test    eax, eax
0x18002ac29  js      loc_18002B0F6
0x18002ac2f  lea     rcx, [rbx+8]
0x18002ac33  mov     rax, [rcx]
0x18002ac36  mov     rdx, r12
0x18002ac39  mov     rax, [rax+48h]
0x18002ac3d  call    _guard_dispatch_icall
0x18002ac42  mov     [rsp+310h+var_2C0], eax
0x18002ac46  mov     r15, [rbp+210h+var_288]
0x18002ac4a  test    eax, eax
0x18002ac4c  mov     rax, [rsp+310h+var_2B8]
0x18002ac51  mov     rdx, [r15+rax+38h]
0x18002ac56  jns     loc_18002ACFB
0x18002ac5c  mov     r15d, [rdx+14h]
0x18002ac60  add     rdx, 4; struct _GUID *
0x18002ac64  lea     rcx, [rbp+210h+var_1E0]; this
0x18002ac68  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002ac6d  mov     dword ptr [rsp+310h+var_2D8], r15d
0x18002ac72  mov     [rsp+310h+var_2E0], rax
0x18002ac77  lea     rax, aMergeFailedFor; "Merge failed for update ID: %ws.%d"
0x18002ac7e  mov     [rsp+310h+var_2E8], rax
0x18002ac83  mov     r15d, [rsp+310h+var_2C0]
0x18002ac88  mov     dword ptr [rsp+310h+var_2F0], r15d
0x18002ac8d  xor     edx, edx
0x18002ac8f  xor     ecx, ecx
0x18002ac91  lea     r9d, [rdx+3]
0x18002ac95  mov     r8d, 1000h
0x18002ac9b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002aca0  cmp     r15d, 8024B104h
0x18002aca7  jnz     loc_18002AEDA
0x18002acad  lea     rax, aContinuingTheM; "Continuing the merge operation"
0x18002acb4  mov     [rsp+310h+var_2E8], rax
0x18002acb9  xor     esi, esi
0x18002acbb  mov     [rsp+310h+var_2F0], rsi
0x18002acc0  xor     edx, edx
0x18002acc2  xor     ecx, ecx
0x18002acc4  lea     r9d, [rsi+4]
0x18002acc8  mov     r8d, 1000h
0x18002acce  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002acd3  mov     [rsp+310h+var_2C0], esi
0x18002acd7  lea     rcx, [rbp+210h+var_238]; this
0x18002acdb  call    ??1SandboxAccessMutexGuard@OSDeploymentHelper@@QEAA@XZ; OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard(void)
0x18002ace0  nop
0x18002ace1  test    rbx, rbx
0x18002ace4  jz      short loc_18002ACF6
0x18002ace6  mov     rax, [rbx]
0x18002ace9  mov     rcx, rbx
0x18002acec  mov     rax, [rax+10h]
0x18002acf0  call    _guard_dispatch_icall
0x18002acf5  nop
0x18002acf6  jmp     loc_18002AE63
0x18002acfb  mov     rcx, [rbp+210h+var_F8]
0x18002ad02  add     rcx, 78h ; 'x'
0x18002ad06  add     rdx, 4
0x18002ad0a  mov     rax, [rcx]
0x18002ad0d  xor     r8d, r8d
0x18002ad10  mov     rax, [rax+8]
0x18002ad14  call    _guard_dispatch_icall
0x18002ad19  mov     rcx, [rbp+210h+var_F8]
0x18002ad20  add     rcx, 90h
0x18002ad27  mov     rax, [rcx]
0x18002ad2a  xor     r8d, r8d
0x18002ad2d  mov     rdx, [rbp+210h+var_218]
0x18002ad31  mov     rax, [rax+8]
0x18002ad35  call    _guard_dispatch_icall
0x18002ad3a  mov     rcx, r12; psz
0x18002ad3d  call    cs:__imp_SysAllocString
0x18002ad43  mov     rdx, [rsp+310h+var_2B8]
0x18002ad48  mov     [r15+rdx+18h], rax
0x18002ad4d  test    rax, rax
0x18002ad50  jz      loc_18002B0E9
0x18002ad56  lea     r8, [rbp+210h+var_250]; wchar_t **
  ... truncated ...
```
