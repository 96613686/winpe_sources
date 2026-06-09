# CBlbBackupAsync::PrepareTargetVolumesForSSB(_BLBSRV_VOLUME_MAP *,ulong)

- ea: `0x140030ea8`
- end: `0x1400318d0`
- name: `?PrepareTargetVolumesForSSB@CBlbBackupAsync@@AEAAJPEAU_BLBSRV_VOLUME_MAP@@K@Z`
- size: `2600`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this, struct _BLBSRV_VOLUME_MAP *, unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, service_task`

## callers

- `0x140019620`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bfd8`
- `0x14000cbcc`
- `0x140013008`
- `0x14001358c`
- `0x140014384`
- `0x140020bf0`
- `0x1400278a4`
- `0x14002d79c`
- `0x140030ea8`
- `0x14003c69c`
- `0x14008863c`
- `0x1400889f0`
- `0x140088d0c`
- `0x14008ba2c`
- `0x14008bb44`
- `0x14008e8e8`
- `0x1400f007c`
- `0x1400f07dc`
- `0x14011b8a0`
- `0x14012365c`
- `0x1401244c0`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!SetVolumeLabelW` at `0x14003149e`
- `KERNEL32!SetVolumeLabelW` at `0x14003149e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140030fae`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14003185d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140030fae`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14003185d`
- `KERNEL32!GetLastError` at `0x1400314a8`
- `KERNEL32!GetLastError` at `0x1400314a8`
- `msvcrt!_wcsnicmp` at `0x14003177d`
- `msvcrt!_wcsnicmp` at `0x140031809`
- `msvcrt!_wcsnicmp` at `0x14003177d`
- `msvcrt!_wcsnicmp` at `0x140031809`
- `ole32!CoTaskMemAlloc` at `0x140031007`
- `ole32!CoTaskMemAlloc` at `0x14003103a`
- `ole32!CoTaskMemAlloc` at `0x140031007`
- `ole32!CoTaskMemAlloc` at `0x14003103a`
- `ole32!CoTaskMemFree` at `0x1400310b3`
- `ole32!CoTaskMemFree` at `0x1400311ee`
- `ole32!CoTaskMemFree` at `0x14003128c`
- `ole32!CoTaskMemFree` at `0x1400313cc`
- `ole32!CoTaskMemFree` at `0x140031577`
- `ole32!CoTaskMemFree` at `0x140031589`
- `ole32!CoTaskMemFree` at `0x140031597`
- `ole32!CoTaskMemFree` at `0x1400315ab`
- `ole32!CoTaskMemFree` at `0x1400315c6`
- `ole32!CoTaskMemFree` at `0x1400315e0`
- `ole32!CoTaskMemFree` at `0x140031601`
- `ole32!CoTaskMemFree` at `0x14003161b`
- `ole32!CoTaskMemFree` at `0x14003163b`
- `ole32!CoTaskMemFree` at `0x14003164f`
- `ole32!CoTaskMemFree` at `0x14003165d`
- `ole32!CoTaskMemFree` at `0x1400310b3`
- `ole32!CoTaskMemFree` at `0x1400311ee`
- `ole32!CoTaskMemFree` at `0x14003128c`
- `ole32!CoTaskMemFree` at `0x1400313cc`
- `ole32!CoTaskMemFree` at `0x140031577`
- `ole32!CoTaskMemFree` at `0x140031589`
- `ole32!CoTaskMemFree` at `0x140031597`
- `ole32!CoTaskMemFree` at `0x1400315ab`
- `ole32!CoTaskMemFree` at `0x1400315c6`
- `ole32!CoTaskMemFree` at `0x1400315e0`
- `ole32!CoTaskMemFree` at `0x140031601`
- `ole32!CoTaskMemFree` at `0x14003161b`
- `ole32!CoTaskMemFree` at `0x14003163b`
- `ole32!CoTaskMemFree` at `0x14003164f`
- `ole32!CoTaskMemFree` at `0x14003165d`
- `RPCRT4!UuidToStringW` at `0x140031255`
- `RPCRT4!UuidToStringW` at `0x140031255`
- `RPCRT4!RpcStringFreeW` at `0x140031241`
- `RPCRT4!RpcStringFreeW` at `0x140031564`
- `RPCRT4!RpcStringFreeW` at `0x140031241`
- `RPCRT4!RpcStringFreeW` at `0x140031564`

## string_xrefs

- `0x140030f6a`: `base\stor\blb\engine\service\backup.cpp`
- `0x140030f8a`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400313a0`: `base\stor\blb\engine\service\backup.cpp`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::PrepareTargetVolumesForSSB(
        CBlbBackupAsync *this,
        struct _BLBSRV_VOLUME_MAP *a2,
        unsigned int a3)
{
  bool v4; // zf
  unsigned int v5; // r12d
  unsigned __int16 *v6; // rsi
  char *v7; // r14
  void *v8; // r13
  __int64 v9; // r10
  unsigned int v10; // r8d
  unsigned __int8 IsVolumeIncludedForSSB; // al
  int v12; // r8d
  unsigned int v13; // r9d
  unsigned int v14; // ecx
  unsigned __int16 **v15; // r15
  int appended; // ebx
  void *v17; // rax
  unsigned int v18; // r15d
  __int64 v19; // r14
  int OriginalAccessPath; // eax
  __int64 v21; // rcx
  unsigned int v22; // r14d
  char *v23; // r15
  unsigned int v24; // r13d
  __int64 i; // rax
  __int64 v26; // rsi
  unsigned __int16 *v27; // rcx
  unsigned __int16 **v28; // r14
  bool v29; // bl
  int VHD; // eax
  unsigned __int16 *v31; // r12
  LPVOID *v32; // r14
  char LastError; // al
  unsigned int v34; // edi
  unsigned __int16 *v35; // rcx
  _QWORD *v36; // r15
  unsigned int m; // edi
  void *v38; // rcx
  unsigned int n; // edi
  void *v40; // rcx
  __int64 j; // r13
  __int64 v43; // rcx
  unsigned int v44; // r15d
  unsigned __int64 v45; // rax
  unsigned int v46; // esi
  unsigned __int64 v47; // rdx
  __int64 v48; // r12
  size_t v49; // r8
  const wchar_t *v50; // rcx
  unsigned __int16 *v51; // rcx
  struct _BLBSRV_VOLUME_MAP *v52; // r12
  unsigned int k; // esi
  size_t v54; // r8
  const wchar_t *v55; // rcx
  unsigned __int16 *v56; // rcx
  LPVOID *v57; // rdx
  unsigned int v58; // [rsp+40h] [rbp-C0h]
  void *v59; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v61; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 **v62; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v63; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v64; // [rsp+70h] [rbp-90h] BYREF
  RPC_WSTR String; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v66; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v67; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v68; // [rsp+90h] [rbp-70h]
  __int64 v69; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v71; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v72; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v73; // [rsp+B8h] [rbp-48h]
  struct _BLBSRV_VOLUME_MAP *v74; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v75[264]; // [rsp+D0h] [rbp-30h] BYREF

  v68 = a3;
  v74 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 448, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v4 = *((_DWORD *)this + 84) == 1;
  v5 = 0;
  v58 = 0;
  v6 = 0;
  String = 0;
  v7 = 0;
  v64 = 0;
  v8 = 0;
  v61 = 0;
  v59 = 0;
  v66 = 0;
  v71 = 0;
  pv = 0;
  v69 = 0;
  v70 = 0;
  v72 = 0;
  if ( v4 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x27E7u, "m_eMediaType != BLB_MT_SHINY");
  if ( !*((_BYTE *)this + 390) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x27E8u, "m_bSystemState");
  memset_0(v75, 0, 0x208u);
  GetSystemTimeAsFileTime((LPFILETIME)this + 89);
  if ( *((_DWORD *)this + 92) )
  {
    v9 = *((_QWORD *)this + 27);
    v10 = 0;
    do
    {
      IsVolumeIncludedForSSB = BlbIsVolumeIncludedForSSB(
                                 *(_DWORD *)(368LL * v10 + v9 + 84),
                                 *(_BYTE *)(368LL * v10 + v9 + 104));
      v14 = v5 + 1;
      if ( !IsVolumeIncludedForSSB )
        v14 = v5;
      v10 = v12 + 1;
      v5 = v14;
    }
    while ( v10 < v13 );
    v58 = v14;
  }
  v15 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v5);
  v62 = v15;
  if ( !v15 )
  {
    v73 = 0;
LABEL_17:
    appended = -2147024882;
    goto LABEL_82;
  }
  memset_0(v15, 0, 8LL * v5);
  v17 = CoTaskMemAlloc(8LL * v5);
  v73 = v17;
  if ( !v17 )
    goto LABEL_17;
  memset_0(v17, 0, 8LL * v5);
  appended = BlbutilMemalloc(&v59, v5, 8u);
  if ( appended < 0 )
  {
    v7 = (char *)v59;
    goto LABEL_82;
  }
  v18 = 0;
  while ( (unsigned int)v6 < *((_DWORD *)this + 92) )
  {
    v19 = 368LL * (unsigned int)v6;
    if ( BlbIsVolumeIncludedForSSB(
           *(_DWORD *)(*((_QWORD *)this + 27) + v19 + 84),
           *(_BYTE *)(*((_QWORD *)this + 27) + v19 + 104)) )
    {
      if ( v8 )
      {
        CoTaskMemFree(v8);
        pv = 0;
      }
      OriginalAccessPath = CBlbVolumeBackupContext::GetOriginalAccessPath(
                             (CBlbVolumeBackupContext *)(v19 + *((_QWORD *)this + 27)),
                             (unsigned __int16 **)&pv);
      v8 = pv;
      appended = OriginalAccessPath;
      if ( OriginalAccessPath < 0 )
        goto LABEL_30;
      v21 = *((_QWORD *)this + 103);
      v69 = 0;
      v70 = 0;
      (*(void (__fastcall **)(__int64, LPVOID, __int64 *, __int64 *))(*(_QWORD *)v21 + 80LL))(v21, pv, &v69, &v70);
      if ( v18 >= v5 )
      {
        appended = -2147418113;
LABEL_30:
        v7 = (char *)v59;
        goto LABEL_81;
      }
      ++v18;
      *(_QWORD *)(*((_QWORD *)this + 27) + v19 + 48) = v69;
      *(_QWORD *)(*((_QWORD *)this + 27) + v19 + 56) = v70;
    }
    LODWORD(v6) = (_DWORD)v6 + 1;
  }
  v22 = 0;
  appended = BlbutilAppendString(*((const unsigned __int16 **)this + 43), L"\\", &v71);
  if ( appended < 0 )
    goto LABEL_30;
  appended = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)this + 40), 0);
  if ( appended < 0 )
    goto LABEL_30;
  appended = BlbQueryFileSystemSpace(v71, &v63, &v67);
  if ( appended < 0 )
    goto LABEL_30;
  CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)this + 40));
  v23 = (char *)v59;
  v24 = 0;
  for ( i = 0; ; i = (unsigned int)(v63 + 1) )
  {
    LODWORD(v63) = i;
    if ( (unsigned int)i >= *((_DWORD *)this + 92) )
      break;
    v26 = 368 * i + *((_QWORD *)this + 27);
    v67 = 368 * i;
    if ( !BlbIsVolumeIncludedForSSB(*(_DWORD *)(v26 + 84), *(_BYTE *)(v26 + 104)) )
      continue;
    if ( v24 >= v5 )
    {
      appended = -2147418113;
      goto LABEL_79;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    appended = CBlbVolumeBackupContext::GetOriginalAccessPath((CBlbVolumeBackupContext *)v26, (unsigned __int16 **)&pv);
    if ( appended < 0 )
      goto LABEL_79;
    appended = BlbutilDuplicateString((const unsigned __int16 *)pv, &v62[v24], 0);
    if ( appended < 0 )
      goto LABEL_79;
    if ( String )
    {
      RpcStringFreeW(&String);
      String = 0;
    }
    if ( UuidToStringW((const UUID *)(v26 + 68), &String) )
    {
      appended = -2147024882;
      goto LABEL_78;
    }
    appended = StringCchPrintfW(v75, 0x104u, L"%s.vhdx", String);
    if ( appended < 0
      || (CoTaskMemFree(v64),
          v27 = (unsigned __int16 *)*((_QWORD *)this + 59),
          v64 = 0,
          appended = BlbutilSlashTerminatePath(v27, (LPVOID *)&v64),
          appended < 0)
      || (v28 = (unsigned __int16 **)((char *)v73 + 8 * v24), appended = BlbutilAppendString(v64, v75, v28),
                                                              appended < 0)
      || (appended = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)this + 40), 0), appended < 0) )
    {
LABEL_78:
      v5 = v58;
      goto LABEL_79;
    }
    v29 = FileExists(*v28);
    CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)this + 40));
    if ( !v29 )
    {
      if ( v61 )
      {
        CoTaskMemFree(v61);
        v61 = 0;
      }
      appended = BlbutilQueryVolumeName((struct _GUID *)(v26 + 68), *(_DWORD *)(v26 + 84), &v61, 0);
      if ( appended < 0 )
        goto LABEL_78;
      v31 = v61;
      appended = BlbutilQueryVolumeSpace(v61, &v66);
      if ( appended < 0 )
        goto LABEL_78;
      appended = BlbQueryVolumeFileSystem(v31, &v72);
      if ( appended < 0 )
        goto LABEL_78;
      VHD = CBlbBackupAsync::CreateVHD(
              this,
              *v28,
              v66,
              *(unsigned __int16 **)(v26 + 96),
              0,
              *(_DWORD *)(v26 + 64),
              v72,
              (unsigned __int16 **)(v26 + 224));
      goto LABEL_67;
    }
    if ( !*(_QWORD *)(v26 + 224) )
    {
      if ( (*(_BYTE *)(v26 + 84) & 8) == 0 && (*(_BYTE *)(v26 + 84) & 0x10) == 0 )
        BlbAssert(
          "base\\stor\\blb\\engine\\service\\backup.cpp",
          0x28C3u,
          "VOLUME_IS_BLOCKLEVEL(pVolCtxt->m_dwVolumeFlags) || VOLUME_IS_INCREMENTAL(pVolCtxt->m_dwVolumeFlags)");
      VHD = CBlbBackupAsync::MountVHD(this, *v28, (unsigned __int16 **)(v26 + 224));
LABEL_67:
      appended = VHD;
      if ( VHD < 0 )
        goto LABEL_78;
      v32 = (LPVOID *)&v23[8 * v24];
      appended = BlbutilSlashTerminatePath(*(unsigned __int16 **)(*((_QWORD *)this + 27) + v67 + 224), v32);
      if ( appended < 0 )
        goto LABEL_78;
      if ( SetVolumeLabelW((LPCWSTR)*v32, *(LPCWSTR *)(v26 + 96)) )
      {
        v22 = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            450,
            (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
            *(_QWORD *)(v26 + 96),
            (__int64)*v32,
            LastError);
        }
        v22 = 0;
        appended = 0;
      }
      v5 = v58;
      ++v24;
      continue;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 449, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    v7 = (char *)v59;
    v5 = v58;
    appended = BlbutilDuplicateString(*(const unsigned __int16 **)(v26 + 224), (unsigned __int16 **)v59 + v24, 0);
    if ( appended < 0 )
      goto LABEL_80;
    ++v24;
    v23 = v7;
    v22 = 0;
  }
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    LODWORD(v63) = j;
    if ( (unsigned int)j >= v5 )
      break;
    while ( 1 )
    {
      v43 = *((_QWORD *)this + 103);
      if ( v22 >= *(_DWORD *)(v43 + 216) )
        break;
      v44 = 0;
      v45 = *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                         (_QWORD *)(v43 + 184),
                         v22);
      v66 = v45;
LABEL_126:
      if ( v44 < *(_DWORD *)(v45 + 92) )
      {
        v46 = 0;
        v47 = *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                           (_QWORD *)(v45 + 96),
                           v44);
        v67 = v47;
        while ( 1 )
        {
          if ( v46 >= *(_DWORD *)(v47 + 104) )
            goto LABEL_139;
          v48 = *(_QWORD *)(56LL * v46 + *(_QWORD *)(v47 + 96));
          if ( v48 )
          {
            v49 = -1;
            v50 = v62[j];
            do
              ++v49;
            while ( v50[v49] );
            if ( !_wcsnicmp(v50, *(const wchar_t **)v48, v49) )
            {
              v51 = (unsigned __int16 *)*((_QWORD *)v59 + j);
              if ( !v51
                || *(_QWORD *)(v48 + 8)
                || (appended = BlbutilSlashTerminatePath(v51, (LPVOID *)(v48 + 8)), appended >= 0) )
              {
                j = (unsigned int)v63;
LABEL_139:
                v45 = v66;
                ++v44;
                goto LABEL_126;
              }
              goto LABEL_78;
            }
            v47 = v67;
            j = (unsigned int)v63;
          }
          ++v46;
        }
      }
      ++v22;
    }
    v52 = v74;
    v22 = 0;
    for ( k = 0; k < v68; ++k )
    {
      v54 = -1;
      v55 = v62[j];
      do
        ++v54;
      while ( v55[v54] );
      v22 = 0;
      if ( !_wcsnicmp(v55, *((const wchar_t **)v52 + 3 * k), v54) )
      {
        v56 = (unsigned __int16 *)*((_QWORD *)v59 + j);
        if ( v56 )
        {
          v57 = (LPVOID *)((char *)v52 + 24 * k + 8);
          if ( !*v57 )
          {
            appended = BlbutilSlashTerminatePath(v56, v57);
            if ( appended < 0 )
              goto LABEL_78;
          }
          break;
        }
      }
    }
    v5 = v58;
  }
  GetSystemTimeAsFileTime((LPFILETIME)this + 90);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      451,
      &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
      (*((_QWORD *)this + 90) - *((_QWORD *)this + 89)) / 0x2710uLL);
  }
LABEL_79:
  v7 = (char *)v59;
LABEL_80:
  v8 = pv;
LABEL_81:
  v15 = v62;
  v6 = v61;
LABEL_82:
  CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)this + 40));
  if ( appended < 0 )
    CBlbAsync::SetResult((CBlbBackupAsync *)((char *)this + 24), -2139619131, appended, 0);
  v34 = 0;
  if ( String )
    RpcStringFreeW(&String);
  if ( v64 )
    CoTaskMemFree(v64);
  if ( v71 )
    CoTaskMemFree(v71);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v72 )
    CoTaskMemFree(v72);
  if ( v15 )
  {
    if ( v5 )
    {
      do
      {
        v35 = v15[v34];
        if ( v35 )
        {
          CoTaskMemFree(v35);
          v15[v34] = 0;
        }
        ++v34;
      }
      while ( v34 < v5 );
    }
    CoTaskMemFree(v15);
  }
  v36 = v73;
  if ( v73 )
  {
    for ( m = 0; m < v5; ++m )
    {
      v38 = (void *)v36[m];
      if ( v38 )
      {
        CoTaskMemFree(v38);
        v36[m] = 0;
      }
    }
    CoTaskMemFree(v36);
  }
  if ( v7 )
  {
    for ( n = 0; n < v5; ++n )
    {
      v40 = *(void **)&v7[8 * n];
      if ( v40 )
      {
        CoTaskMemFree(v40);
        *(_QWORD *)&v7[8 * n] = 0;
      }
    }
    CoTaskMemFree(v7);
  }
  if ( v8 )
    CoTaskMemFree(v8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 452, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140030ea8  mov     [rsp-8+arg_10], rbx
0x140030ead  push    rbp
0x140030eae  push    rsi
0x140030eaf  push    rdi
0x140030eb0  push    r12
0x140030eb2  push    r13
0x140030eb4  push    r14
0x140030eb6  push    r15
0x140030eb8  lea     rbp, [rsp-1F0h]
0x140030ec0  sub     rsp, 2F0h
0x140030ec7  mov     rax, cs:__security_cookie
0x140030ece  xor     rax, rsp
0x140030ed1  mov     [rbp+220h+var_40], rax
0x140030ed8  mov     [rbp+220h+var_290], r8d
0x140030edc  mov     rdi, rcx
0x140030edf  mov     [rbp+220h+var_260], rdx
0x140030ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x140030eea  lea     rax, WPP_GLOBAL_Control
0x140030ef1  cmp     rcx, rax
0x140030ef4  jz      short loc_140030F17
0x140030ef6  test    byte ptr [rcx+1Ch], 1
0x140030efa  jz      short loc_140030F17
0x140030efc  cmp     byte ptr [rcx+19h], 4
0x140030f00  jb      short loc_140030F17
0x140030f02  mov     rcx, [rcx+10h]
0x140030f06  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140030f0d  mov     edx, 1C0h
0x140030f12  call    WPP_SF_
0x140030f17  xor     ebx, ebx
0x140030f19  cmp     dword ptr [rdi+150h], 1
0x140030f20  mov     r12d, ebx
0x140030f23  mov     [rsp+320h+var_2E0], ebx
0x140030f27  mov     esi, ebx
0x140030f29  mov     [rsp+320h+String], rbx
0x140030f2e  mov     r14d, ebx
0x140030f31  mov     [rsp+320h+var_2B0], rbx
0x140030f36  mov     r13d, ebx
0x140030f39  mov     [rsp+320h+var_2C8], rbx
0x140030f3e  mov     [rsp+320h+var_2D8], rbx
0x140030f43  mov     [rbp+220h+var_2A0], rbx
0x140030f47  mov     [rbp+220h+var_278], rbx
0x140030f4b  mov     [rsp+320h+pv], rbx
0x140030f50  mov     [rbp+220h+var_288], rbx
0x140030f54  mov     [rbp+220h+var_280], rbx
0x140030f58  mov     [rbp+220h+var_270], rbx
0x140030f5c  jnz     short loc_140030F76
0x140030f5e  lea     r8, aMEmediatypeBlb; "m_eMediaType != BLB_MT_SHINY"
0x140030f65  mov     edx, 27E7h; unsigned int
0x140030f6a  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140030f71  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140030f76  cmp     [rdi+186h], bl
0x140030f7c  jnz     short loc_140030F96
0x140030f7e  lea     r8, aMBsystemstate; "m_bSystemState"
0x140030f85  mov     edx, 27E8h; unsigned int
0x140030f8a  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140030f91  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140030f96  xor     edx, edx; Val
0x140030f98  lea     rcx, [rbp+220h+var_250]; void *
0x140030f9c  mov     r8d, 208h; Size
0x140030fa2  call    memset_0
0x140030fa7  lea     rcx, [rdi+2C8h]; lpSystemTimeAsFileTime
0x140030fae  call    cs:__imp_GetSystemTimeAsFileTime
0x140030fb4  mov     r9d, [rdi+170h]
0x140030fbb  test    r9d, r9d
0x140030fbe  jz      short loc_140030FFD
0x140030fc0  mov     r10, [rdi+0D8h]
0x140030fc7  mov     r8d, ebx
0x140030fca  mov     eax, r8d
0x140030fcd  imul    rcx, rax, 170h
0x140030fd4  mov     dl, [rcx+r10+68h]; unsigned __int8
0x140030fd9  mov     ecx, [rcx+r10+54h]; unsigned int
0x140030fde  call    ?BlbIsVolumeIncludedForSSB@@YAEKE@Z; BlbIsVolumeIncludedForSSB(ulong,uchar)
0x140030fe3  test    al, al
0x140030fe5  lea     ecx, [r12+1]
0x140030fea  cmovz   ecx, r12d
0x140030fee  inc     r8d
0x140030ff1  mov     r12d, ecx
0x140030ff4  cmp     r8d, r9d
0x140030ff7  jb      short loc_140030FCA
0x140030ff9  mov     [rsp+320h+var_2E0], ecx
0x140030ffd  mov     ebx, r12d
0x140031000  shl     rbx, 3
0x140031004  mov     rcx, rbx; cb
0x140031007  call    cs:__imp_CoTaskMemAlloc
0x14003100d  mov     r15, rax
0x140031010  mov     [rsp+320h+var_2C0], rax
0x140031015  xor     eax, eax
0x140031017  test    r15, r15
0x14003101a  jnz     short loc_14003102A
0x14003101c  mov     [rbp+220h+var_268], rax
0x140031020  mov     ebx, 8007000Eh
0x140031025  jmp     loc_140031535
0x14003102a  mov     r8, rbx; Size
0x14003102d  xor     edx, edx; Val
0x14003102f  mov     rcx, r15; void *
0x140031032  call    memset_0
0x140031037  mov     rcx, rbx; cb
0x14003103a  call    cs:__imp_CoTaskMemAlloc
0x140031040  mov     [rbp+220h+var_268], rax
0x140031044  test    rax, rax
0x140031047  jz      short loc_140031020
0x140031049  mov     r8, rbx; Size
0x14003104c  xor     edx, edx; Val
0x14003104e  mov     rcx, rax; void *
0x140031051  call    memset_0
0x140031056  mov     r8d, 8; unsigned int
0x14003105c  lea     rcx, [rsp+320h+var_2D8]; void **
0x140031061  mov     edx, r12d; unsigned int
0x140031064  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x140031069  mov     ebx, eax
0x14003106b  test    eax, eax
0x14003106d  js      loc_1400318C6
0x140031073  mov     r15d, r14d
0x140031076  cmp     esi, [rdi+170h]
0x14003107c  jnb     loc_140031143
0x140031082  mov     rcx, [rdi+0D8h]
0x140031089  mov     eax, esi
0x14003108b  imul    r14, rax, 170h
0x140031092  mov     dl, [rcx+r14+68h]; unsigned __int8
0x140031097  mov     ecx, [rcx+r14+54h]; unsigned int
0x14003109c  call    ?BlbIsVolumeIncludedForSSB@@YAEKE@Z; BlbIsVolumeIncludedForSSB(ulong,uchar)
0x1400310a1  xor     ebx, ebx
0x1400310a3  test    al, al
0x1400310a5  jz      loc_14003112D
0x1400310ab  test    r13, r13
0x1400310ae  jz      short loc_1400310BE
0x1400310b0  mov     rcx, r13; pv
0x1400310b3  call    cs:__imp_CoTaskMemFree
0x1400310b9  mov     [rsp+320h+pv], rbx
0x1400310be  mov     rcx, [rdi+0D8h]
0x1400310c5  lea     rdx, [rsp+320h+pv]; unsigned __int16 **
0x1400310ca  add     rcx, r14; this
0x1400310cd  call    ?GetOriginalAccessPath@CBlbVolumeBackupContext@@QEAAJPEAPEAG@Z; CBlbVolumeBackupContext::GetOriginalAccessPath(ushort * *)
0x1400310d2  mov     r13, [rsp+320h+pv]
0x1400310d7  mov     ebx, eax
0x1400310d9  test    eax, eax
0x1400310db  js      short loc_140031139
0x1400310dd  mov     rcx, [rdi+338h]
0x1400310e4  lea     r9, [rbp+220h+var_280]
0x1400310e8  xor     ebx, ebx
0x1400310ea  lea     r8, [rbp+220h+var_288]
0x1400310ee  mov     [rbp+220h+var_288], rbx
0x1400310f2  mov     rdx, r13
0x1400310f5  mov     [rbp+220h+var_280], rbx
0x1400310f9  mov     rax, [rcx]
0x1400310fc  mov     rax, [rax+50h]
0x140031100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031105  cmp     r15d, r12d
0x140031108  jnb     short loc_140031134
0x14003110a  mov     rcx, [rdi+0D8h]
0x140031111  inc     r15d
0x140031114  mov     rax, [rbp+220h+var_288]
0x140031118  mov     [rcx+r14+30h], rax
0x14003111d  mov     rcx, [rdi+0D8h]
0x140031124  mov     rax, [rbp+220h+var_280]
0x140031128  mov     [rcx+r14+38h], rax
0x14003112d  inc     esi
0x14003112f  jmp     loc_140031076
0x140031134  mov     ebx, 8000FFFFh
0x140031139  mov     r14, [rsp+320h+var_2D8]
0x14003113e  jmp     loc_14003152B
0x140031143  mov     rcx, [rdi+158h]; unsigned __int16 *
0x14003114a  lea     r8, [rbp+220h+var_278]; unsigned __int16 **
0x14003114e  lea     rdx, asc_14013C090; "\\"
0x140031155  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14003115a  xor     r14d, r14d
0x14003115d  mov     ebx, eax
0x14003115f  test    eax, eax
0x140031161  js      short loc_140031139
0x140031163  xor     edx, edx; unsigned __int8
0x140031165  lea     rcx, [rdi+28h]; this
0x140031169  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x14003116e  mov     ebx, eax
0x140031170  test    eax, eax
0x140031172  js      short loc_140031139
0x140031174  mov     rcx, [rbp+220h+var_278]; unsigned __int16 *
0x140031178  lea     r8, [rbp+220h+var_298]; unsigned __int64 *
0x14003117c  lea     rdx, [rsp+320h+var_2B8]; unsigned __int64 *
0x140031181  call    ?BlbQueryFileSystemSpace@@YAJPEAGPEA_K1@Z; BlbQueryFileSystemSpace(ushort *,unsigned __int64 *,unsigned __int64 *)
0x140031186  mov     ebx, eax
0x140031188  test    eax, eax
0x14003118a  js      short loc_140031139
0x14003118c  lea     rcx, [rdi+28h]; this
0x140031190  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140031195  mov     r15, [rsp+320h+var_2D8]
0x14003119a  mov     r13d, r14d
0x14003119d  mov     eax, r14d
0x1400311a0  mov     dword ptr [rsp+320h+var_2B8], eax
0x1400311a4  cmp     eax, [rdi+170h]
0x1400311aa  jnb     loc_1400316E6
0x1400311b0  mov     rsi, [rdi+0D8h]
0x1400311b7  imul    rcx, rax, 170h
0x1400311be  add     rsi, rcx
0x1400311c1  mov     [rbp+220h+var_298], rcx
0x1400311c5  mov     dl, [rsi+68h]; unsigned __int8
0x1400311c8  mov     ecx, [rsi+54h]; unsigned int
0x1400311cb  call    ?BlbIsVolumeIncludedForSSB@@YAEKE@Z; BlbIsVolumeIncludedForSSB(ulong,uchar)
0x1400311d0  test    al, al
0x1400311d2  jz      loc_140031511
0x1400311d8  cmp     r13d, r12d
0x1400311db  jnb     loc_1400316DC
0x1400311e1  mov     rax, [rsp+320h+pv]
0x1400311e6  test    rax, rax
0x1400311e9  jz      short loc_1400311F9
0x1400311eb  mov     rcx, rax; pv
0x1400311ee  call    cs:__imp_CoTaskMemFree
0x1400311f4  mov     [rsp+320h+pv], r14
0x1400311f9  lea     rdx, [rsp+320h+pv]; unsigned __int16 **
0x1400311fe  mov     rcx, rsi; this
0x140031201  call    ?GetOriginalAccessPath@CBlbVolumeBackupContext@@QEAAJPEAPEAG@Z; CBlbVolumeBackupContext::GetOriginalAccessPath(ushort * *)
0x140031206  mov     ebx, eax
0x140031208  test    eax, eax
0x14003120a  js      loc_140031521
0x140031210  mov     rax, [rsp+320h+var_2C0]
0x140031215  xor     r8d, r8d; unsigned __int64
0x140031218  mov     rcx, [rsp+320h+pv]; unsigned __int16 *
0x14003121d  mov     r14d, r13d
0x140031220  lea     rdx, [rax+r14*8]; unsigned __int16 **
0x140031224  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140031229  mov     ebx, eax
0x14003122b  test    eax, eax
0x14003122d  js      loc_140031521
0x140031233  xor     ebx, ebx
0x140031235  cmp     [rsp+320h+String], rbx
0x14003123a  jz      short loc_14003124C
0x14003123c  lea     rcx, [rsp+320h+String]; String
0x140031241  call    cs:__imp_RpcStringFreeW
0x140031247  mov     [rsp+320h+String], rbx
0x14003124c  lea     rdx, [rsp+320h+String]; StringUuid
0x140031251  lea     rcx, [rsi+44h]; Uuid
0x140031255  call    cs:__imp_UuidToStringW
0x14003125b  test    eax, eax
0x14003125d  jnz     loc_1400316D2
0x140031263  mov     r9, [rsp+320h+String]
0x140031268  lea     r8, aSVhdx; "%s.vhdx"
0x14003126f  mov     edx, 104h; unsigned __int64
0x140031274  lea     rcx, [rbp+220h+var_250]; unsigned __int16 *
0x140031278  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003127d  mov     ebx, eax
0x14003127f  test    eax, eax
0x140031281  js      loc_14003151C
0x140031287  mov     rcx, [rsp+320h+var_2B0]; pv
0x14003128c  call    cs:__imp_CoTaskMemFree
0x140031292  mov     rcx, [rdi+1D8h]; unsigned __int16 *
0x140031299  lea     rdx, [rsp+320h+var_2B0]; unsigned __int16 **
0x14003129e  mov     [rsp+320h+var_2B0], 0
0x1400312a7  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x1400312ac  mov     ebx, eax
0x1400312ae  test    eax, eax
0x1400312b0  js      loc_1400316C3
0x1400312b6  mov     rax, [rbp+220h+var_268]
0x1400312ba  lea     rdx, [rbp+220h+var_250]; unsigned __int16 *
0x1400312be  lea     r14, [rax+r14*8]
0x1400312c2  mov     rax, [rsp+320h+var_2B0]
0x1400312c7  mov     rcx, rax; unsigned __int16 *
0x1400312ca  mov     [rsp+320h+var_2B0], rax
0x1400312cf  mov     r8, r14; unsigned __int16 **
0x1400312d2  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1400312d7  mov     ebx, eax
0x1400312d9  test    eax, eax
0x1400312db  js      loc_14003151C
0x1400312e1  xor     edx, edx; unsigned __int8
0x1400312e3  lea     rcx, [rdi+28h]; this
0x1400312e7  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x1400312ec  mov     ebx, eax
0x1400312ee  test    eax, eax
0x1400312f0  js      loc_14003151C
0x1400312f6  mov     rcx, [r14]; unsigned __int16 *
0x1400312f9  call    ?FileExists@@YA_NPEAG@Z; FileExists(ushort *)
0x1400312fe  lea     rcx, [rdi+28h]; this
0x140031302  mov     bl, al
0x140031304  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140031309  test    bl, bl
0x14003130b  jz      loc_1400313BF
0x140031311  lea     rbx, [rsi+0E0h]
0x140031318  xor     r12d, r12d
0x14003131b  cmp     [rbx], r12
0x14003131e  jz      short loc_140031388
0x140031320  mov     rcx, cs:WPP_GLOBAL_Control
0x140031327  lea     rax, WPP_GLOBAL_Control
0x14003132e  cmp     rcx, rax
0x140031331  jz      short loc_140031354
0x140031333  test    byte ptr [rcx+1Ch], 1
0x140031337  jz      short loc_140031354
0x140031339  cmp     byte ptr [rcx+19h], 4
0x14003133d  jb      short loc_140031354
0x14003133f  mov     rcx, [rcx+10h]
0x140031343  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14003134a  mov     edx, 1C1h
0x14003134f  call    WPP_SF_
0x140031354  mov     r14, [rsp+320h+var_2D8]
0x140031359  xor     r8d, r8d; unsigned __int64
0x14003135c  mov     rcx, [rbx]; unsigned __int16 *
0x14003135f  mov     eax, r13d
0x140031362  lea     rdx, [r14+rax*8]; unsigned __int16 **
0x140031366  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14003136b  mov     r12d, [rsp+320h+var_2E0]
0x140031370  mov     ebx, eax
0x140031372  test    eax, eax
0x140031374  js      loc_140031526
  ... truncated ...
```
