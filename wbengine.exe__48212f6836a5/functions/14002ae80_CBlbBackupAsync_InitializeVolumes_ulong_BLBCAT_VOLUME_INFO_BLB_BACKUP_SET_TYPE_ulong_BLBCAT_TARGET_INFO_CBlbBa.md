# CBlbBackupAsync::InitializeVolumes(ulong,_BLBCAT_VOLUME_INFO *,_BLB_BACKUP_SET_TYPE,ulong,_BLBCAT_TARGET_INFO *,CBlbBackupItemsHelper *)

- ea: `0x14002ae80`
- end: `0x14002bce2`
- name: `?InitializeVolumes@CBlbBackupAsync@@AEAAJKPEAU_BLBCAT_VOLUME_INFO@@W4_BLB_BACKUP_SET_TYPE@@KPEAU_BLBCAT_TARGET_INFO@@PEAVCBlbBackupItemsHelper@@@Z`
- size: `3682`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400290e4`

## callees

- `0x140006ca8`
- `0x140006dd4`
- `0x140007654`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be04`
- `0x140014260`
- `0x140014624`
- `0x140014a10`
- `0x140016028`
- `0x14001d3dc`
- `0x140027760`
- `0x140027d4c`
- `0x140029cf4`
- `0x14002ae80`
- `0x14002d004`
- `0x140034134`
- `0x14003440c`
- `0x140034474`
- `0x1400351ec`
- `0x14003c434`
- `0x14008b940`
- `0x14008fed0`
- `0x1400d6fd8`
- `0x1400fe6e0`
- `0x140101c50`
- `0x14012e834`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14002b298`
- `ole32!CoTaskMemAlloc` at `0x14002b298`
- `ole32!CoTaskMemFree` at `0x14002b9f0`
- `ole32!CoTaskMemFree` at `0x14002bc5d`
- `ole32!CoTaskMemFree` at `0x14002bc72`
- `ole32!CoTaskMemFree` at `0x14002b9f0`
- `ole32!CoTaskMemFree` at `0x14002bc5d`
- `ole32!CoTaskMemFree` at `0x14002bc72`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b3ab`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b424`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b3ab`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b424`

## string_xrefs

- `0x14002af86`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002b121`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002b1c2`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002b461`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002b577`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002b8e7`: `base\stor\blb\engine\service\backup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CBlbBackupAsync::InitializeVolumes(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        OLECHAR *a7)
{
  unsigned int v11; // edi
  int IsClientSKU; // ebx
  PVOID *v13; // rcx
  unsigned int v14; // edx
  unsigned int v15; // r14d
  __int64 v16; // r9
  unsigned int v17; // r8d
  unsigned __int64 v18; // rcx
  unsigned int i; // edi
  unsigned __int64 v20; // r8
  unsigned int j; // ecx
  __int64 v22; // r9
  __int64 v23; // rax
  int v24; // r8d
  unsigned int v25; // edi
  unsigned int v26; // esi
  unsigned int v27; // edx
  int v28; // r13d
  __int64 v29; // rcx
  unsigned int v30; // eax
  char *v31; // rdi
  SIZE_T v32; // rbx
  char *v33; // rax
  unsigned int v34; // r9d
  unsigned int k; // esi
  unsigned int v36; // ebx
  __int64 v37; // rbx
  int v38; // ebx
  ATL::CComBSTR *v39; // rax
  int v40; // ebx
  ATL::CComBSTR *v41; // rax
  _BYTE *v42; // r13
  __int64 v43; // rax
  struct _BLB_VOLUME_INFO *v44; // rax
  unsigned int m; // edi
  __int64 v46; // rbx
  unsigned int v47; // esi
  unsigned int v48; // r9d
  unsigned int v49; // r14d
  int v50; // r12d
  struct _GUID *v51; // r10
  __int64 v52; // r8
  unsigned int v53; // ecx
  __int64 v54; // rdx
  __int64 v55; // rax
  unsigned __int64 v56; // rdi
  __int64 v57; // rax
  bool v58; // cf
  size_t v59; // rax
  OLECHAR *v60; // rax
  OLECHAR *v61; // rbx
  unsigned int v62; // edi
  unsigned int v63; // r9d
  unsigned int v64; // r11d
  __int64 v65; // r10
  char *v66; // rdx
  _OWORD *v67; // r8
  __int64 v68; // rax
  unsigned int v69; // ecx
  __int64 v70; // r8
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // r14
  unsigned __int16 *v75; // rcx
  __int64 v76; // rdx
  int VolumeId; // eax
  void *v78; // rsi
  __int64 Next; // rbx
  int VolumeFriendlyNameForPublisher; // eax
  PVOID *v81; // rcx
  int v82; // edi
  unsigned __int8 v84; // [rsp+30h] [rbp-D0h] BYREF
  char v85; // [rsp+31h] [rbp-CFh]
  LPVOID v86; // [rsp+38h] [rbp-C8h]
  unsigned int v87; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v89; // [rsp+50h] [rbp-B0h]
  int v90; // [rsp+54h] [rbp-ACh]
  unsigned int v91; // [rsp+58h] [rbp-A8h] BYREF
  int v92; // [rsp+5Ch] [rbp-A4h]
  unsigned int v93; // [rsp+60h] [rbp-A0h] BYREF
  struct _BLB_VOLUME_INFO *v94; // [rsp+68h] [rbp-98h] BYREF
  char *v95; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID *v97; // [rsp+80h] [rbp-80h] BYREF
  __int64 v98; // [rsp+88h] [rbp-78h]
  __int64 v99; // [rsp+90h] [rbp-70h]
  __int128 v100; // [rsp+98h] [rbp-68h] BYREF
  __int64 v101; // [rsp+A8h] [rbp-58h]
  __int128 v102; // [rsp+B0h] [rbp-50h]
  int v103; // [rsp+C0h] [rbp-40h]
  _BYTE v104[80]; // [rsp+D0h] [rbp-30h] BYREF
  BSTR v105[2]; // [rsp+120h] [rbp+20h] BYREF

  v90 = a4;
  v98 = a3;
  v89 = a2;
  v99 = a6;
  v105[0] = a7;
  v11 = 0;
  LODWORD(bstrString) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v97 = 0;
  v93 = 0;
  v84 = 0;
  ATL::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>(
    (unsigned int)v104,
    a2,
    a3,
    a4,
    LODWORD(FLOAT_2_25));
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v103 = 10;
  v91 = 0;
  v94 = 0;
  pv = 0;
  v86 = 0;
  if ( !a7 )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x128Cu, "pBackupSpecs");
  IsClientSKU = BlbutilIsClientSKU(&v84);
  if ( IsClientSKU < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_217:
      v31 = (char *)v86;
      goto LABEL_218;
    }
LABEL_58:
    v31 = (char *)v86;
    goto LABEL_219;
  }
  IsClientSKU = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, struct _BLB_VOLUME_INFO **))(**(_QWORD **)(a1 + 80)
                                                                                              + 64LL))(
                  *(_QWORD *)(a1 + 80),
                  &v91,
                  &v94);
  if ( IsClientSKU < 0 )
    goto LABEL_217;
  v85 = 0;
  v14 = v91;
  if ( v91 )
  {
    do
    {
      v95 = (char *)v94 + 128 * (unsigned __int64)v11;
      ATL::CAtlMap<_GUID,_BLB_VOLUME_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::SetAt(
        v104,
        v95,
        &v95);
      ++v11;
      v14 = v91;
    }
    while ( v11 < v91 );
  }
  if ( a4 == 1 )
  {
    v15 = 0;
    v16 = 0;
    v87 = 0;
    for ( i = 0; i < v14; ++i )
    {
      v20 = (unsigned __int64)i << 7;
      if ( (*(_DWORD *)((_BYTE *)v94 + v20 + 88) & 0x200) != 0 )
      {
        v16 = (unsigned int)(v16 + 1);
        v87 = v16;
        if ( *(_BYTE *)(a1 + 388) )
        {
          for ( j = 0; j < a2; ++j )
          {
            v22 = 120LL * j;
            v23 = *(_QWORD *)((char *)v94 + v20) - *(_QWORD *)(v22 + a3);
            if ( !v23 )
              v23 = *(_QWORD *)((char *)v94 + v20 + 8) - *(_QWORD *)(v22 + a3 + 8);
            if ( !v23 && *(_BYTE *)(v22 + a3 + 40) )
            {
              if ( (*(_DWORD *)(v22 + a3 + 16) & 0x200) != 0 )
                goto LABEL_37;
              BlbAssert(
                "base\\stor\\blb\\engine\\service\\backup.cpp",
                0x12B1u,
                "VOLUME_IS_BACKUP_CRITICAL(rgVolume[j].m_dwVolumeFlags)");
              goto LABEL_36;
            }
          }
          if ( j != a2 )
            goto LABEL_37;
          v95 = (char *)v94 + v20;
          ATL::CAtlList<_BLB_VOLUME_INFO *,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::AddTail(&v100, &v95);
LABEL_36:
          v14 = v91;
LABEL_37:
          v16 = v87;
        }
      }
    }
  }
  else
  {
    v15 = 0;
    v16 = 0;
    v87 = 0;
    v17 = 0;
    if ( v14 )
    {
      do
      {
        v18 = (unsigned __int64)v17 << 7;
        if ( (*(_DWORD *)((_BYTE *)v94 + v18 + 88) & 0x200) != 0 && (*((_BYTE *)v94 + v18 + 88) & 1) == 0 )
          v16 = (unsigned int)(v16 + 1);
        ++v17;
      }
      while ( v17 < v14 );
      v87 = v16;
    }
  }
  LODWORD(v95) = v101;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = v89;
  if ( !v89 )
    goto LABEL_216;
  v28 = 0;
  do
  {
    v29 = 120LL * v26;
    if ( *(_BYTE *)(v29 + a3 + 40) )
    {
      v92 = ++v24;
      v30 = v25 + 1;
      if ( (*(_DWORD *)(v29 + a3 + 16) & 0x200) == 0 )
        v30 = v25;
      v25 = v30;
      if ( (*(_BYTE *)(v29 + a3 + 16) & 1) != 0 )
      {
        v85 = 1;
        if ( v15 )
        {
          BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x12D3u, "j == 0");
          v27 = v89;
          v24 = v92;
        }
        v15 = 1;
      }
    }
    ++v26;
  }
  while ( v26 < v27 );
  if ( !v24 )
  {
LABEL_216:
    IsClientSKU = -2139619312;
    goto LABEL_217;
  }
  if ( *(_BYTE *)(a1 + 390) && *(_BYTE *)(a1 + 388) && v90 != 1 && v25 < v87 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(a1 + 824) + 64LL))(
      *(_QWORD *)(a1 + 824),
      2155347992LL,
      0,
      v16);
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_58;
    }
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    v31 = 0;
LABEL_218:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_219;
  }
  v92 = v101 + v24;
  v32 = 368LL * (unsigned int)(v101 + v24);
  v33 = (char *)CoTaskMemAlloc(v32);
  v31 = v33;
  v86 = v33;
  if ( !v33 )
  {
    IsClientSKU = -2147024882;
    goto LABEL_218;
  }
  memset_0(v33, 0, v32);
  for ( k = 0; ; ++k )
  {
    v36 = v89;
    if ( k >= v89 )
    {
      v42 = v86;
      if ( v85 && (*((_BYTE *)v86 + 84) & 1) == 0 )
        BlbAssert(
          "base\\stor\\blb\\engine\\service\\backup.cpp",
          0x1330u,
          "BlbutilIsEspVolume(rgVolumesInBackup[0].m_dwVolumeFlags)");
      v43 = v101;
      if ( v101 )
      {
        while ( v43 )
        {
          v44 = (struct _BLB_VOLUME_INFO *)ATL::CAtlList<_BLB_VOLUME_INFO *,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::RemoveHead(&v100);
          IsClientSKU = CBlbVolumeBackupContext::MarkCriticalVolumeNotInBackupAsAborted(
                          (CBlbVolumeBackupContext *)&v42[368 * v15],
                          (struct CBlbBackupAsync *)a1,
                          v44);
          if ( IsClientSKU < 0 )
            goto LABEL_217;
          ++v15;
          v43 = v101;
        }
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 824) + 64LL))(
          *(_QWORD *)(a1 + 824),
          2155347992LL,
          0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
        }
        v36 = v89;
      }
      for ( m = 0; m < v36; ++m )
      {
        v46 = v98 + 120LL * m;
        if ( (*(_DWORD *)(v46 + 16) & 0x200) == 0 )
        {
          ATL::CAtlMap<_GUID,_BLB_VOLUME_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::RemoveKey(
            v104,
            v98 + 120LL * m);
          if ( *(_BYTE *)(v46 + 40) )
          {
            IsClientSKU = CBlbVolumeBackupContext::Initialize(
                            (CBlbVolumeBackupContext *)&v42[368 * v15],
                            (struct _BLBCAT_VOLUME_INFO *)v46,
                            (struct CBlbBackupAsync *)a1,
                            (struct CBlbBackupItemsHelper *)v105[0]);
            if ( IsClientSKU < 0 )
              goto LABEL_217;
            ++v15;
          }
        }
        v36 = v89;
      }
      v47 = v92;
      if ( v15 != v92 )
        BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x1366u, "j == cVolumesInBackup");
      if ( *(_BYTE *)(a1 + 390) )
      {
        if ( v90 != 1 )
        {
          IsClientSKU = BlbGetCriticalVolumesEx(&v93, &v97, (const unsigned int **)v105, v34);
          if ( IsClientSKU < 0 )
            goto LABEL_217;
        }
      }
      *(_DWORD *)(a1 + 368) = 0;
      v48 = 0;
      v49 = v93;
      if ( v47 )
      {
        v50 = v90;
        v51 = v97;
        do
        {
          v52 = 368LL * v48;
          if ( (v42[v52 + 84] & 8) != 0 || (v42[v52 + 84] & 0x40) != 0 )
            goto LABEL_122;
          if ( v42[v52 + 104] )
          {
            if ( v50 == 1 )
              goto LABEL_122;
            v53 = 0;
            if ( v49 )
            {
              do
              {
                v54 = v53;
                v55 = *(_QWORD *)&v42[v52 + 68] - *(_QWORD *)&v51[v54].Data1;
                if ( !v55 )
                  v55 = *(_QWORD *)&v42[v52 + 76] - *(_QWORD *)v51[v54].Data4;
                if ( !v55 )
                  break;
                ++v53;
              }
              while ( v53 < v49 );
              if ( v53 < v49 )
LABEL_122:
                ++*(_DWORD *)(a1 + 368);
            }
          }
          ++v48;
        }
        while ( v48 < v47 );
      }
      v56 = *(unsigned int *)(a1 + 368);
      v57 = 368 * v56;
      if ( !is_mul_ok(v56, 0x170u) )
        v57 = -1;
      v58 = __CFADD__(v57, 8);
      v59 = v57 + 8;
      if ( v58 )
        v59 = -1;
      v60 = (OLECHAR *)operator new[](v59);
      v105[0] = v60;
      if ( v60 )
      {
        *(_QWORD *)v60 = v56;
        v61 = v60 + 4;
        `eh vector constructor iterator'(
          v60 + 4,
          0x170u,
          (unsigned int)v56,
          (void (*)(void *))CBlbVolumeBackupContext::CBlbVolumeBackupContext,
          (void (*)(void *))CBlbVolumeBackupContext::~CBlbVolumeBackupContext);
        v62 = 0;
      }
      else
      {
        v62 = 0;
        v61 = 0;
      }
      *(_QWORD *)(a1 + 216) = v61;
      if ( !v61 )
      {
        IsClientSKU = -2147024882;
        goto LABEL_217;
      }
      v63 = 0;
      v64 = 0;
      if ( v47 )
      {
        v65 = 0;
        while ( 1 )
        {
          v66 = &v42[368 * v65];
          if ( (v66[84] & 8) != 0 || (v66[84] & 0x40) != 0 )
            break;
          if ( v66[104] )
          {
            if ( v90 == 1 )
            {
              v67 = (_OWORD *)(*(_QWORD *)(a1 + 216) + 368LL * v63);
              v68 = 2;
              do
              {
                *v67 = *(_OWORD *)v66;
                v67[1] = *((_OWORD *)v66 + 1);
                v67[2] = *((_OWORD *)v66 + 2);
                v67[3] = *((_OWORD *)v66 + 3);
                v67[4] = *((_OWORD *)v66 + 4);
                v67[5] = *((_OWORD *)v66 + 5);
                v67[6] = *((_OWORD *)v66 + 6);
                v67[7] = *((_OWORD *)v66 + 7);
                v67 += 8;
                v66 += 128;
                --v68;
              }
              while ( v68 );
            }
            else
            {
              v69 = 0;
              if ( !v49 )
                goto LABEL_154;
              do
              {
                v70 = v69;
                v71 = *(_QWORD *)(v66 + 68) - *(_QWORD *)&v97[v70].Data1;
                if ( !v71 )
                  v71 = *(_QWORD *)(v66 + 76) - *(_QWORD *)v97[v70].Data4;
                if ( !v71 )
                  break;
                ++v69;
              }
              while ( v69 < v49 );
              v42 = v86;
              if ( v69 >= v49 )
                goto LABEL_154;
              v67 = (_OWORD *)(*(_QWORD *)(a1 + 216) + 368LL * v63);
              v72 = 2;
              do
              {
                *v67 = *(_OWORD *)v66;
                v67[1] = *((_OWORD *)v66 + 1);
                v67[2] = *((_OWORD *)v66 + 2);
                v67[3] = *((_OWORD *)v66 + 3);
                v67[4] = *((_OWORD *)v66 + 4);
                v67[5] = *((_OWORD *)v66 + 5);
                v67[6] = *((_OWORD *)v66 + 6);
                v67[7] = *((_OWORD *)v66 + 7);
                v67 += 8;
                v66 += 128;
                --v72;
              }
              while ( v72 );
            }
            goto LABEL_153;
          }
LABEL_154:
          ++v64;
          ++v65;
          if ( v64 >= v47 )
            goto LABEL_155;
        }
        v67 = (_OWORD *)(*(_QWORD *)(a1 + 216) + 368LL * v63);
        v73 = 2;
        do
        {
          *v67 = *(_OWORD *)v66;
          v67[1] = *((_OWORD *)v66 + 1);
          v67[2] = *((_OWORD *)v66 + 2);
          v67[3] = *((_OWORD *)v66 + 3);
          v67[4] = *((_OWORD *)v66 + 4);
          v67[5] = *((_OWORD *)v66 + 5);
          v67[6] = *((_OWORD *)v66 + 6);
          v67[7] = *((_OWORD *)v66 + 7);
          v67 += 8;
          v66 += 128;
          --v73;
        }
        while ( v73 );
LABEL_153:
        *v67 = *(_OWORD *)v66;
        v67[1] = *((_OWORD *)v66 + 1);
        v67[2] = *((_OWORD *)v66 + 2);
        v67[3] = *((_OWORD *)v66 + 3);
        v67[4] = *((_OWORD *)v66 + 4);
        v67[5] = *((_OWORD *)v66 + 5);
        v67[6] = *((_OWORD *)v66 + 6);
        ++v63;
        goto LABEL_154;
      }
LABEL_155:
      if ( v63 != *(_DWORD *)(a1 + 368) )
        BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x13C2u, "j == m_cVolume");
      if ( *(_BYTE *)(a1 + 388) )
      {
        *(_OWORD *)v105 = 0;
        if ( *(_DWORD *)(a1 + 336) != 4 )
        {
          v74 = v99;
          while ( 1 )
          {
            if ( v62 >= a5 )
              goto LABEL_169;
            v75 = *(unsigned __int16 **)(v74 + 40LL * v62);
            v76 = -1;
            do
              ++v76;
            while ( v75[v76] );
            VolumeId = BlbutilQueryVolumeId(v75, v76, (struct _GUID *)v105);
            IsClientSKU = VolumeId;
            if ( VolumeId < 0 )
              break;
            ATL::CAtlMap<_GUID,_BLB_VOLUME_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::RemoveKey(
              v104,
              v105);
            ++v62;
          }
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              206,
              (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
              *(_QWORD *)(v74 + 40LL * v62),
              VolumeId);
            v13 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_85;
          }
          v78 = pv;
          goto LABEL_210;
        }
LABEL_169:
        v105[0] = (BSTR)ATL::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>::GetStartPosition(v104);
        if ( v105[0] )
        {
          v78 = pv;
          while ( 1 )
          {
            Next = ATL::CAtlMap<unsigned long,_GUID,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<_GUID>>::GetNext(
                     v104,
                     v105);
            if ( v78 )
            {
              CoTaskMemFree(v78);
              pv = 0;
            }
            VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                               *(_QWORD *)(Next + 16),
                                               *(unsigned int *)(*(_QWORD *)(Next + 16) + 88LL),
                                               2,
                                               &pv);
            v78 = pv;
            if ( VolumeFriendlyNameForPublisher < 0
              || (VolumeFriendlyNameForPublisher = PublishNewVolumeAvailableEvent(
                                                     (unsigned __int16 *)pv,
                                                     *(unsigned __int16 **)(*(_QWORD *)(Next + 16) + 16LL)),
                  VolumeFriendlyNameForPublisher < 0) )
            {
              v81 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_180;
              }
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                207,
                (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                (_DWORD)v78,
                VolumeFriendlyNameForPublisher);
            }
            v81 = (PVOID *)WPP_GLOBAL_Control;
LABEL_180:
            if ( !v105[0] )
              goto LABEL_183;
          }
        }
      }
      v81 = (PVOID *)WPP_GLOBAL_Control;
      v78 = pv;
LABEL_183:
      if ( v81 == &WPP_GLOBAL_Control || (*((_BYTE *)v81 + 28) & 1) == 0 )
      {
        v82 = v90;
      }
      else
      {
        v82 = v90;
        if ( *((_BYTE *)v81 + 25) >= 4u )
          WPP_SF_d(v81[2], 208, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      IsClientSKU = CBlbBackupAsync::BlbSetBackupType((CBlbBackupAsync *)a1);
      if ( IsClientSKU >= 0 )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            v13 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
          {
            WPP_SF_dd(v13[2], 211, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
            v13 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        if ( *(_DWORD *)(a1 + 320) == v82 )
          goto LABEL_194;
        if ( v82 != 1 )
        {
          if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
            WPP_SF_(v13[2], 213, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          *(_DWORD *)(a1 + 320) = 1;
          goto LABEL_193;
        }
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
        {
          WPP_SF_(v13[2], 212, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
          goto LABEL_193;
        }
      }
      else
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_193:
          v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_194:
          v31 = (char *)v86;
          goto LABEL_220;
        }
      }
LABEL_210:
      v31 = (char *)v86;
      goto LABEL_220;
    }
    v37 = v98 + 120LL * k;
    if ( (*(_DWORD *)(v37 + 16) & 0x200) != 0 )
    {
      ATL::CAtlMap<_GUID,_BLB_VOLUME_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::RemoveKey(
        v104,
        v98 + 120LL * k);
      if ( *(_BYTE *)(v37 + 40) )
        break;
    }
LABEL_77:
    ;
  }
  if ( (*(_BYTE *)(v37 + 16) & 1) == 0 )
    v31 = (char *)v86 + 368 * v15++;
  IsClientSKU = CBlbVolumeBackupContext::Initialize(
                  (CBlbVolumeBackupContext *)v31,
                  (struct _BLBCAT_VOLUME_INFO *)v37,
                  (struct CBlbBackupAsync *)a1,
                  (struct CBlbBackupItemsHelper *)v105[0]);
  if ( IsClientSKU < 0 )
    goto LABEL_217;
  if ( *((_DWORD *)v31 + 5) != 12 )
    goto LABEL_76;
  if ( !v84 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v38 = *((_DWORD *)v31 + 8);
      v39 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct _GUID *)(v31 + 68));
      v28 |= 2u;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        204,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        *(_QWORD *)v39,
        v38);
    }
    if ( (v28 & 2) != 0 )
    {
      v28 &= ~2u;
      SysFreeString(bstrString);
    }
LABEL_76:
    v31 = (char *)v86;
    goto LABEL_77;
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v40 = *((_DWORD *)v31 + 8);
    v41 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v105, (const struct _GUID *)(v31 + 68));
    LOBYTE(v28) = v28 | 1;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      203,
      (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
      *(_QWORD *)v41,
      v40);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (v28 & 1) != 0 )
  {
    SysFreeString(v105[0]);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  IsClientSKU = -2139619303;
LABEL_85:
  v31 = (char *)v86;
LABEL_219:
  v78 = pv;
LABEL_220:
  if ( v94 )
  {
    FreeVolumes(&v94, &v91);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v78 )
  {
    CoTaskMemFree(v78);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v31 )
  {
    CoTaskMemFree(v31);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
    WPP_SF_(v13[2], 214, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  ATL::CAtlList<unsigned short *,ATL::CElementTraits<unsigned short *>>::~CAtlList<unsigned short *,ATL::CElementTraits<unsigned short *>>(&v100);
  ATL::CAtlMap<unsigned long,_GUID,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<_GUID>>::RemoveAll(v104);
  return (unsigned int)IsClientSKU;
}

```

## disassembly

```asm
0x14002ae80  mov     [rsp-8+arg_8], rbx
0x14002ae85  push    rbp
0x14002ae86  push    rsi
0x14002ae87  push    rdi
0x14002ae88  push    r12
0x14002ae8a  push    r13
0x14002ae8c  push    r14
0x14002ae8e  push    r15
0x14002ae90  lea     rbp, [rsp-40h]
0x14002ae95  sub     rsp, 140h
0x14002ae9c  mov     rax, cs:__security_cookie
0x14002aea3  xor     rax, rsp
0x14002aea6  mov     [rbp+70h+var_40], rax
0x14002aeaa  mov     r14d, r9d
0x14002aead  mov     [rsp+170h+var_11C], r9d
0x14002aeb2  mov     r12, r8
0x14002aeb5  mov     [rbp+70h+var_E8], r8
0x14002aeb9  mov     esi, edx
0x14002aebb  mov     [rsp+170h+var_120], edx
0x14002aebf  mov     r15, rcx
0x14002aec2  mov     rax, [rbp+70h+arg_28]
0x14002aec9  mov     [rbp+70h+var_E0], rax
0x14002aecd  mov     rbx, [rbp+70h+arg_30]
0x14002aed4  mov     [rbp+70h+var_50], rbx
0x14002aed8  xor     edi, edi
0x14002aeda  mov     dword ptr [rsp+170h+bstrString], edi
0x14002aede  lea     rax, WPP_GLOBAL_Control
0x14002aee5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aeec  cmp     rcx, rax
0x14002aeef  jz      short loc_14002AF12
0x14002aef1  test    byte ptr [rcx+1Ch], 1
0x14002aef5  jz      short loc_14002AF12
0x14002aef7  cmp     byte ptr [rcx+19h], 4
0x14002aefb  jb      short loc_14002AF12
0x14002aefd  mov     edx, 0C8h
0x14002af02  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002af09  mov     rcx, [rcx+10h]
0x14002af0d  call    WPP_SF_
0x14002af12  mov     [rbp+70h+var_F0], rdi
0x14002af16  mov     [rsp+170h+var_110], edi
0x14002af1a  mov     [rsp+170h+var_140], dil
0x14002af1f  movss   xmm0, cs:__real@40100000
0x14002af27  movss   dword ptr [rsp+170h+var_150], xmm0
0x14002af2d  movss   xmm3, cs:__real@3e800000
0x14002af35  movss   xmm2, cs:__real@3f400000
0x14002af3d  lea     rcx, [rbp+70h+var_A0]
0x14002af41  call    ??0?$CAtlMap@U_GUID@@PEAU_BLB_VOLUME_VHD_INFO@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAU_BLB_VOLUME_VHD_INFO@@@4@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>(uint,float,float,float,uint)
0x14002af46  nop
0x14002af47  xorps   xmm0, xmm0
0x14002af4a  movdqu  [rbp+70h+var_D8], xmm0
0x14002af4f  mov     [rbp+70h+var_C8], rdi
0x14002af53  xorps   xmm1, xmm1
0x14002af56  movdqu  [rbp+70h+var_C0], xmm1
0x14002af5b  mov     [rbp+70h+var_B0], 0Ah
0x14002af62  mov     [rsp+170h+var_118], edi
0x14002af66  mov     [rsp+170h+var_108], rdi
0x14002af6b  mov     [rsp+170h+pv], rdi
0x14002af70  mov     [rsp+170h+var_138], rdi
0x14002af75  test    rbx, rbx
0x14002af78  jnz     short loc_14002AF92
0x14002af7a  lea     r8, aPbackupspecs; "pBackupSpecs"
0x14002af81  mov     edx, 128Ch; unsigned int
0x14002af86  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002af8d  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002af92  lea     rcx, [rsp+170h+var_140]; unsigned __int8 *
0x14002af97  call    ?BlbutilIsClientSKU@@YAJPEAE@Z; BlbutilIsClientSKU(uchar *)
0x14002af9c  mov     ebx, eax
0x14002af9e  test    eax, eax
0x14002afa0  jns     short loc_14002AFF0
0x14002afa2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002afa9  lea     rax, WPP_GLOBAL_Control
0x14002afb0  cmp     rcx, rax
0x14002afb3  jz      loc_14002B278
0x14002afb9  test    byte ptr [rcx+1Ch], 1
0x14002afbd  jz      loc_14002B278
0x14002afc3  mov     r12d, 2
0x14002afc9  cmp     [rcx+19h], r12b
0x14002afcd  jb      loc_14002B278
0x14002afd3  mov     edx, 0C9h
0x14002afd8  mov     r9d, ebx
0x14002afdb  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002afe2  mov     rcx, [rcx+10h]
0x14002afe6  call    WPP_SF_d
0x14002afeb  jmp     loc_14002BC1D
0x14002aff0  mov     rcx, [r15+50h]
0x14002aff4  mov     rax, [rcx]
0x14002aff7  lea     r8, [rsp+170h+var_108]
0x14002affc  lea     rdx, [rsp+170h+var_118]
0x14002b001  mov     rax, [rax+40h]
0x14002b005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b00a  mov     ebx, eax
0x14002b00c  test    eax, eax
0x14002b00e  js      loc_14002BC1D
0x14002b014  mov     [rsp+170h+var_13F], dil
0x14002b019  mov     edx, [rsp+170h+var_118]
0x14002b01d  test    edx, edx
0x14002b01f  jz      short loc_14002B049
0x14002b021  mov     edx, edi
0x14002b023  shl     rdx, 7
0x14002b027  add     rdx, [rsp+170h+var_108]
0x14002b02c  mov     [rsp+170h+var_100], rdx
0x14002b031  lea     r8, [rsp+170h+var_100]
0x14002b036  lea     rcx, [rbp+70h+var_A0]
0x14002b03a  call    ?SetAt@?$CAtlMap@U_GUID@@PEAU_BLB_VOLUME_INFO@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAU_BLB_VOLUME_INFO@@@4@@ATL@@QEAAPEAU__POSITION@@AEBU_GUID@@AEBQEAU_BLB_VOLUME_INFO@@@Z; ATL::CAtlMap<_GUID,_BLB_VOLUME_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::SetAt(_GUID const &,_BLB_VOLUME_INFO * const &)
0x14002b03f  inc     edi
0x14002b041  mov     edx, [rsp+170h+var_118]
0x14002b045  cmp     edi, edx
0x14002b047  jb      short loc_14002B021
0x14002b049  cmp     r14d, 1
0x14002b04d  jz      short loc_14002B097
0x14002b04f  xor     r14d, r14d
0x14002b052  mov     r9d, r14d
0x14002b055  mov     [rsp+170h+var_130], r14d
0x14002b05a  mov     r8d, r14d
0x14002b05d  test    edx, edx
0x14002b05f  jz      loc_14002B15F
0x14002b065  mov     ecx, r8d
0x14002b068  shl     rcx, 7
0x14002b06c  mov     rax, [rsp+170h+var_108]
0x14002b071  test    dword ptr [rcx+rax+58h], 200h
0x14002b079  jz      short loc_14002B085
0x14002b07b  test    byte ptr [rcx+rax+58h], 1
0x14002b080  jnz     short loc_14002B085
0x14002b082  inc     r9d
0x14002b085  inc     r8d
0x14002b088  cmp     r8d, edx
0x14002b08b  jb      short loc_14002B065
0x14002b08d  mov     [rsp+170h+var_130], r9d
0x14002b092  jmp     loc_14002B15F
0x14002b097  xor     r14d, r14d
0x14002b09a  mov     r9d, r14d
0x14002b09d  mov     [rsp+170h+var_130], r14d
0x14002b0a2  mov     edi, r14d
0x14002b0a5  test    edx, edx
0x14002b0a7  jz      loc_14002B15F
0x14002b0ad  mov     r8d, edi
0x14002b0b0  shl     r8, 7
0x14002b0b4  mov     r10, [rsp+170h+var_108]
0x14002b0b9  test    dword ptr [r8+r10+58h], 200h
0x14002b0c2  jz      loc_14002B155
0x14002b0c8  inc     r9d
0x14002b0cb  mov     [rsp+170h+var_130], r9d
0x14002b0d0  cmp     [r15+184h], r14b
0x14002b0d7  jz      short loc_14002B155
0x14002b0d9  mov     ecx, r14d
0x14002b0dc  cmp     ecx, esi
0x14002b0de  jnb     short loc_14002B12F
0x14002b0e0  mov     eax, ecx
0x14002b0e2  imul    r9, rax, 78h ; 'x'
0x14002b0e6  mov     rax, [r8+r10]
0x14002b0ea  sub     rax, [r9+r12]
0x14002b0ee  jnz     short loc_14002B0FA
0x14002b0f0  mov     rax, [r8+r10+8]
0x14002b0f5  sub     rax, [r9+r12+8]
0x14002b0fa  test    rax, rax
0x14002b0fd  jnz     short loc_14002B106
0x14002b0ff  cmp     [r9+r12+28h], r14b
0x14002b104  jnz     short loc_14002B10A
0x14002b106  inc     ecx
0x14002b108  jmp     short loc_14002B0DC
0x14002b10a  test    dword ptr [r9+r12+10h], 200h
0x14002b113  jnz     short loc_14002B150
0x14002b115  lea     r8, aVolumeIsBackup; "VOLUME_IS_BACKUP_CRITICAL(rgVolume[j].m"...
0x14002b11c  mov     edx, 12B1h; unsigned int
0x14002b121  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002b128  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002b12d  jmp     short loc_14002B14C
0x14002b12f  jnz     short loc_14002B150
0x14002b131  mov     rcx, [rsp+170h+var_108]
0x14002b136  add     rcx, r8
0x14002b139  mov     [rsp+170h+var_100], rcx
0x14002b13e  lea     rdx, [rsp+170h+var_100]
0x14002b143  lea     rcx, [rbp+70h+var_D8]
0x14002b147  call    ?AddTail@?$CAtlList@PEAU_BLB_VOLUME_INFO@@V?$CElementTraits@PEAU_BLB_VOLUME_INFO@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBQEAU_BLB_VOLUME_INFO@@@Z; ATL::CAtlList<_BLB_VOLUME_INFO *,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::AddTail(_BLB_VOLUME_INFO * const &)
0x14002b14c  mov     edx, [rsp+170h+var_118]
0x14002b150  mov     r9d, [rsp+170h+var_130]
0x14002b155  inc     edi
0x14002b157  cmp     edi, edx
0x14002b159  jb      loc_14002B0AD
0x14002b15f  mov     eax, dword ptr [rbp+70h+var_C8]
0x14002b162  mov     dword ptr [rsp+170h+var_100], eax
0x14002b166  mov     r8d, r14d
0x14002b169  xor     eax, eax
0x14002b16b  mov     edi, eax
0x14002b16d  mov     esi, eax
0x14002b16f  mov     edx, [rsp+170h+var_120]
0x14002b173  test    edx, edx
0x14002b175  jz      loc_14002BC18
0x14002b17b  xor     r13d, r13d
0x14002b17e  mov     eax, esi
0x14002b180  imul    rcx, rax, 78h ; 'x'
0x14002b184  cmp     [rcx+r12+28h], r13b
0x14002b189  jz      short loc_14002B1DD
0x14002b18b  inc     r8d
0x14002b18e  mov     [rsp+170h+var_114], r8d
0x14002b193  test    dword ptr [rcx+r12+10h], 200h
0x14002b19c  lea     eax, [rdi+1]
0x14002b19f  cmovz   eax, edi
0x14002b1a2  mov     edi, eax
0x14002b1a4  test    byte ptr [rcx+r12+10h], 1
0x14002b1aa  jz      short loc_14002B1DD
0x14002b1ac  mov     [rsp+170h+var_13F], 1
0x14002b1b1  test    r14d, r14d
0x14002b1b4  jz      short loc_14002B1D7
0x14002b1b6  lea     r8, aJ0; "j == 0"
0x14002b1bd  mov     edx, 12D3h; unsigned int
0x14002b1c2  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002b1c9  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14002b1ce  mov     edx, [rsp+170h+var_120]
0x14002b1d2  mov     r8d, [rsp+170h+var_114]
0x14002b1d7  mov     r14d, 1
0x14002b1dd  inc     esi
0x14002b1df  cmp     esi, edx
0x14002b1e1  jb      short loc_14002B17E
0x14002b1e3  test    r8d, r8d
0x14002b1e6  jz      loc_14002BC18
0x14002b1ec  xor     r12d, r12d
0x14002b1ef  cmp     [r15+186h], r12b
0x14002b1f6  jz      loc_14002B282
0x14002b1fc  cmp     [r15+184h], r12b
0x14002b203  jz      short loc_14002B282
0x14002b205  cmp     [rsp+170h+var_11C], 1
0x14002b20a  jz      short loc_14002B282
0x14002b20c  mov     esi, [rsp+170h+var_130]
0x14002b210  cmp     edi, esi
0x14002b212  jnb     short loc_14002B282
0x14002b214  mov     rcx, [r15+338h]
0x14002b21b  mov     rax, [rcx]
0x14002b21e  xor     r8d, r8d
0x14002b221  mov     edx, 80780018h
0x14002b226  mov     rax, [rax+40h]
0x14002b22a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b22f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b236  lea     rax, WPP_GLOBAL_Control
0x14002b23d  cmp     rcx, rax
0x14002b240  jz      short loc_14002B278
0x14002b242  test    byte ptr [rcx+1Ch], 1
0x14002b246  jz      short loc_14002B278
0x14002b248  mov     r12d, 2
0x14002b24e  cmp     [rcx+19h], r12b
0x14002b252  jb      short loc_14002B278
0x14002b254  mov     edx, 0CAh
0x14002b259  mov     dword ptr [rsp+170h+var_150], esi
0x14002b25d  mov     r9d, edi
0x14002b260  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002b267  mov     rcx, [rcx+10h]
0x14002b26b  call    WPP_SF_dd
0x14002b270  mov     rdi, r13
0x14002b273  jmp     loc_14002BC22
0x14002b278  mov     rdi, [rsp+170h+var_138]
0x14002b27d  jmp     loc_14002BC29
0x14002b282  add     r8d, dword ptr [rbp+70h+var_C8]
0x14002b286  mov     [rsp+170h+var_114], r8d
0x14002b28b  mov     eax, r8d
0x14002b28e  imul    rbx, rax, 170h
0x14002b295  mov     rcx, rbx; cb
0x14002b298  call    cs:__imp_CoTaskMemAlloc
0x14002b29e  mov     rdi, rax
0x14002b2a1  mov     [rsp+170h+var_138], rax
0x14002b2a6  test    rax, rax
0x14002b2a9  jnz     short loc_14002B2B5
0x14002b2ab  mov     ebx, 8007000Eh
0x14002b2b0  jmp     loc_14002BC22
0x14002b2b5  mov     r8, rbx; Size
0x14002b2b8  xor     edx, edx; Val
0x14002b2ba  mov     rcx, rax; void *
0x14002b2bd  call    memset_0
0x14002b2c2  mov     esi, r12d
0x14002b2c5  mov     r12d, 2
0x14002b2cb  mov     ebx, [rsp+170h+var_120]
0x14002b2cf  cmp     esi, ebx
0x14002b2d1  jnb     loc_14002B440
0x14002b2d7  mov     eax, esi
0x14002b2d9  imul    rbx, rax, 78h ; 'x'
0x14002b2dd  add     rbx, [rbp+70h+var_E8]
0x14002b2e1  test    dword ptr [rbx+10h], 200h
0x14002b2e8  jz      loc_14002B3B6
0x14002b2ee  mov     rdx, rbx
0x14002b2f1  lea     rcx, [rbp+70h+var_A0]
0x14002b2f5  call    ?RemoveKey@?$CAtlMap@U_GUID@@PEAU_BLB_VOLUME_INFO@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAU_BLB_VOLUME_INFO@@@4@@ATL@@QEAA_NAEBU_GUID@@@Z; ATL::CAtlMap<_GUID,_BLB_VOLUME_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_INFO *>>::RemoveKey(_GUID const &)
0x14002b2fa  xor     eax, eax
0x14002b2fc  cmp     [rbx+28h], al
0x14002b2ff  jz      loc_14002B3B6
0x14002b305  test    byte ptr [rbx+10h], 1
0x14002b309  jnz     short loc_14002B31D
0x14002b30b  mov     eax, r14d
0x14002b30e  imul    rdi, rax, 170h
0x14002b315  add     rdi, [rsp+170h+var_138]
0x14002b31a  inc     r14d
0x14002b31d  mov     r9, [rbp+70h+var_50]; struct CBlbBackupItemsHelper *
0x14002b321  mov     r8, r15; struct CBlbBackupAsync *
0x14002b324  mov     rdx, rbx; struct _BLBCAT_VOLUME_INFO *
0x14002b327  mov     rcx, rdi; this
0x14002b32a  call    ?Initialize@CBlbVolumeBackupContext@@QEAAJPEAU_BLBCAT_VOLUME_INFO@@PEAVCBlbBackupAsync@@PEAVCBlbBackupItemsHelper@@@Z; CBlbVolumeBackupContext::Initialize(_BLBCAT_VOLUME_INFO *,CBlbBackupAsync *,CBlbBackupItemsHelper *)
0x14002b32f  mov     ebx, eax
0x14002b331  xor     eax, eax
0x14002b333  test    ebx, ebx
0x14002b335  js      loc_14002BC1D
0x14002b33b  cmp     dword ptr [rdi+14h], 0Ch
0x14002b33f  jnz     short loc_14002B3B1
  ... truncated ...
```
