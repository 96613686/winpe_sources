# BlbRestoreComponentThreadFunc(void *)

- ea: `0x14006a120`
- end: `0x14006afb0`
- name: `?BlbRestoreComponentThreadFunc@@YAKPEAX@Z`
- size: `3728`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `33`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000aee8`
- `0x14000b0bc`
- `0x14000b25c`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000bb8c`
- `0x14000bfd8`
- `0x140013008`
- `0x140014260`
- `0x140026c8c`
- `0x14002cbe8`
- `0x14003c480`
- `0x14006a120`
- `0x14006c324`
- `0x14006d778`
- `0x14006ec50`
- `0x14006ee04`
- `0x1400889f0`
- `0x140088d0c`
- `0x14008ba2c`
- `0x14008fed0`
- `0x1400d740c`
- `0x1400f007c`
- `0x1400f07dc`
- `0x140106f84`
- `0x140107278`
- `0x14011cf98`
- `0x14011d420`
- `0x140134cc6`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14006a380`
- `ole32!CoTaskMemAlloc` at `0x14006a380`
- `ole32!CoTaskMemFree` at `0x14006a5d5`
- `ole32!CoTaskMemFree` at `0x14006a5e7`
- `ole32!CoTaskMemFree` at `0x14006a834`
- `ole32!CoTaskMemFree` at `0x14006abd9`
- `ole32!CoTaskMemFree` at `0x14006ac77`
- `ole32!CoTaskMemFree` at `0x14006ac87`
- `ole32!CoTaskMemFree` at `0x14006ac96`
- `ole32!CoTaskMemFree` at `0x14006acbe`
- `ole32!CoTaskMemFree` at `0x14006acce`
- `ole32!CoTaskMemFree` at `0x14006ace0`
- `ole32!CoTaskMemFree` at `0x14006acf2`
- `ole32!CoTaskMemFree` at `0x14006ad04`
- `ole32!CoTaskMemFree` at `0x14006a5d5`
- `ole32!CoTaskMemFree` at `0x14006a5e7`
- `ole32!CoTaskMemFree` at `0x14006a834`
- `ole32!CoTaskMemFree` at `0x14006abd9`
- `ole32!CoTaskMemFree` at `0x14006ac77`
- `ole32!CoTaskMemFree` at `0x14006ac87`
- `ole32!CoTaskMemFree` at `0x14006ac96`
- `ole32!CoTaskMemFree` at `0x14006acbe`
- `ole32!CoTaskMemFree` at `0x14006acce`
- `ole32!CoTaskMemFree` at `0x14006ace0`
- `ole32!CoTaskMemFree` at `0x14006acf2`
- `ole32!CoTaskMemFree` at `0x14006ad04`
- `ole32!CoInitializeEx` at `0x14006a3b2`
- `ole32!CoInitializeEx` at `0x14006a3b2`
- `ole32!CoUninitialize` at `0x14006ad10`
- `ole32!CoUninitialize` at `0x14006ad10`

## string_xrefs

- `0x14006a367`: `base\stor\blb\engine\service\component.cpp`
- `0x14006a70e`: `base\stor\blb\engine\service\component.cpp`

## pseudocode

```c
__int64 __fastcall BlbRestoreComponentThreadFunc(_QWORD *Parameter)
{
  unsigned int v1; // esi
  _QWORD *v2; // r12
  unsigned int v3; // ebx
  unsigned __int16 *v4; // r13
  struct IBLBCatalogSystem *Catalog; // r14
  PVOID *v6; // r15
  int Data1; // r15d
  struct _FILETIME v8; // r9
  unsigned int v9; // r8d
  unsigned int i; // edx
  unsigned int v11; // eax
  SIZE_T v12; // rbx
  void *v13; // rax
  void *v14; // rdi
  unsigned int v15; // edi
  struct _GUID *v16; // r13
  void *ImpersonationToken; // rax
  struct _GUID v18; // xmm1
  __int64 v19; // rcx
  const unsigned __int16 *v20; // rcx
  signed int VolumeName; // eax
  LPVOID *v22; // rbx
  const unsigned __int16 *v23; // rcx
  unsigned __int16 *v24; // rcx
  void *v25; // r14
  unsigned int v26; // eax
  __int64 v27; // rbx
  int v28; // eax
  __int64 v29; // rcx
  unsigned __int16 *v30; // rcx
  struct _GUID v31; // xmm1
  signed int v32; // edi
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  unsigned int v35; // r8d
  unsigned int v36; // edx
  CBlbImpersonationHelper *v37; // r14
  __int64 v38; // r14
  _QWORD *v39; // r12
  __int64 v40; // rdi
  int v41; // eax
  char v42; // r8
  __int64 v43; // rcx
  int v44; // eax
  void *v45; // rcx
  void *v46; // rcx
  void *v47; // rcx
  CBlbAsync *v48; // rsi
  int v49; // r8d
  int v50; // ebx
  unsigned int v51; // edi
  __int64 v53; // [rsp+20h] [rbp-E0h]
  char v54; // [rsp+80h] [rbp-80h]
  unsigned __int8 v55[15]; // [rsp+81h] [rbp-7Fh] BYREF
  struct _GUID v56; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v57[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID Buf1; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v59; // [rsp+C0h] [rbp-40h]
  LPVOID pv[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v61; // [rsp+E0h] [rbp-20h] BYREF
  int v62; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v63; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 **v64; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD *v65; // [rsp+100h] [rbp+0h]
  _QWORD *v66; // [rsp+108h] [rbp+8h]
  unsigned __int16 v67[264]; // [rsp+110h] [rbp+10h] BYREF

  v1 = 0;
  v66 = Parameter;
  v2 = Parameter;
  *(_QWORD *)&v56.Data1 = 0;
  v3 = 0;
  v65 = (_QWORD *)Parameter[8];
  v4 = 0;
  v59 = 0;
  v57[0] = 0;
  Catalog = CBlbAsync::GetCatalog((CBlbAsync *)(Parameter + 1));
  *(_QWORD *)&Buf1.Data1 = Catalog;
  v62 = 0;
  v63 = 0;
  v61 = 0;
  v54 = 0;
  LODWORD(pv[0]) = 0;
  v64 = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    {
      WPP_SF_DDDDDDDDDDD(
        (unsigned int)v6[2],
        130,
        (unsigned int)&WPP_40d550336cac3d55f04e301f30980d6d_Traceguids,
        *((_DWORD *)v2 + 52),
        *((_WORD *)v2 + 106),
        *((_WORD *)v2 + 107),
        *((_BYTE *)v2 + 216),
        *((_BYTE *)v2 + 217),
        *((_BYTE *)v2 + 218),
        *((_BYTE *)v2 + 219),
        *((_BYTE *)v2 + 220),
        *((_BYTE *)v2 + 221),
        *((_BYTE *)v2 + 222),
        *((_BYTE *)v2 + 223));
      Catalog = *(struct IBLBCatalogSystem **)&Buf1.Data1;
      v1 = 0;
      v3 = 0;
    }
  }
  Buf1.Data1 = CBlbRestoreComponentAsync::GetComponentNameList(
                 (CBlbRestoreComponentAsync *)v2,
                 (unsigned int *)pv,
                 &v64);
  Data1 = Buf1.Data1;
  if ( (Buf1.Data1 & 0x80000000) != 0 )
  {
    v14 = 0;
    goto LABEL_127;
  }
  v8 = (struct _FILETIME)v2[65];
  v56 = (struct _GUID)*((_OWORD *)v2 + 13);
  if ( PublishRestoreStartedEvent(&v56, v64, (unsigned int)pv[0], v8) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
  }
  v9 = *((_DWORD *)v2 + 94);
  if ( !v9 )
    goto LABEL_21;
  for ( i = 0; i < v9; ++i )
  {
    v11 = v3 + 1;
    if ( (*(_BYTE *)(120LL * i + v2[48] + 16) & 1) != 0 )
      v11 = v3;
    v3 = v11;
  }
  v59 = v11;
  if ( !v11 )
LABEL_21:
    BlbAssert("base\\stor\\blb\\engine\\service\\component.cpp", 0xD5Bu, "cVolumeMap > 0");
  v12 = 24LL * v3;
  v13 = CoTaskMemAlloc(v12);
  *(_QWORD *)&v56.Data1 = v13;
  v14 = v13;
  if ( !v13 )
  {
    Data1 = -2147024882;
    Buf1.Data1 = -2147024882;
    goto LABEL_127;
  }
  memset_0(v13, 0, v12);
  Buf1.Data1 = CoInitializeEx(0, 0);
  Data1 = Buf1.Data1;
  if ( (Buf1.Data1 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
    }
    goto LABEL_127;
  }
  v15 = 0;
  v54 = 1;
  while ( v1 < *((_DWORD *)v2 + 94) )
  {
    v67[0] = 0;
    v16 = (struct _GUID *)(v2[48] + 120LL * v1);
    if ( (v16[1].Data1 & 1) != 0 )
    {
      v4 = v57[0];
    }
    else
    {
      ImpersonationToken = CBlbImpersonationHelper::GetImpersonationToken((CBlbImpersonationHelper *)(v2 + 3));
      v18 = (struct _GUID)*((_OWORD *)v2 + 13);
      v19 = *v65;
      *(struct _GUID *)pv = *v16;
      Buf1 = v18;
      Buf1.Data1 = (*(__int64 (__fastcall **)(_QWORD *, struct _GUID *, LPVOID *, _QWORD, _QWORD, _QWORD, void *, int, struct IBLBCatalogSystem *, int *, unsigned __int16 *, _DWORD))(v19 + 344))(
                     v65,
                     &Buf1,
                     pv,
                     0,
                     v2[34],
                     0,
                     ImpersonationToken,
                     260,
                     Catalog,
                     &v62,
                     v67,
                     0);
      Data1 = Buf1.Data1;
      if ( (Buf1.Data1 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DDDDDDDDDDDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            133,
            (unsigned int)&WPP_40d550336cac3d55f04e301f30980d6d_Traceguids,
            v16->Data1,
            v16->Data2,
            v16->Data3,
            v16->Data4[0],
            v16->Data4[1],
            v16->Data4[2],
            v16->Data4[3],
            v16->Data4[4],
            v16->Data4[5],
            v16->Data4[6],
            v16->Data4[7],
            Buf1.Data1);
        }
LABEL_55:
        v4 = v57[0];
LABEL_56:
        v14 = *(void **)&v56.Data1;
        v1 = 0;
        goto LABEL_127;
      }
      v20 = *(const unsigned __int16 **)v16[1].Data4;
      if ( v20 )
        VolumeName = BlbutilDuplicateString(v20, v57, 0);
      else
        VolumeName = BlbutilQueryVolumeName(v16, v16[1].Data1, v57, 0);
      Buf1.Data1 = VolumeName;
      Data1 = VolumeName;
      if ( VolumeName < 0 )
        goto LABEL_55;
      v4 = v57[0];
      v22 = (LPVOID *)(*(_QWORD *)&v56.Data1 + 24LL * v15);
      Data1 = BlbutilSlashTerminatePath(v57[0], v22);
      Buf1.Data1 = Data1;
      if ( Data1 < 0 )
        goto LABEL_56;
      v23 = (const unsigned __int16 *)v2[35];
      if ( v23 )
      {
        pv[0] = 0;
        Buf1.Data1 = BlbutilDuplicateString(v23, (unsigned __int16 **)pv, 0);
        Data1 = Buf1.Data1;
        if ( (Buf1.Data1 & 0x80000000) != 0 )
          goto LABEL_56;
        Data1 = BlbutilSlashTerminatePath((unsigned __int16 *)pv[0], v22 + 1);
        Buf1.Data1 = Data1;
        CoTaskMemFree(pv[0]);
        if ( Data1 < 0 )
          goto LABEL_56;
      }
      else
      {
        Buf1.Data1 = BlbutilDuplicateString((const unsigned __int16 *)*v22, (unsigned __int16 **)v22 + 1, 0);
        Data1 = Buf1.Data1;
        if ( (Buf1.Data1 & 0x80000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
          }
          goto LABEL_56;
        }
      }
      CoTaskMemFree(v4);
      v57[0] = 0;
      Buf1.Data1 = BlbutilDuplicateString(v67, v57, 0);
      Data1 = Buf1.Data1;
      if ( (Buf1.Data1 & 0x80000000) != 0 )
        goto LABEL_55;
      v4 = v57[0];
      Buf1.Data1 = BlbutilSlashTerminatePath(v57[0], v22 + 2);
      Data1 = Buf1.Data1;
      if ( (Buf1.Data1 & 0x80000000) != 0 )
        goto LABEL_56;
      ++v15;
    }
    ++v1;
  }
  if ( v15 != v59 )
    BlbAssert("base\\stor\\blb\\engine\\service\\component.cpp", 0xDD6u, "iVolumeMap == cVolumeMap");
  v1 = 0;
  Buf1.Data1 = CBlbImpersonationHelper::ImpersonateCaller((CBlbImpersonationHelper *)(v2 + 3), 0);
  Data1 = Buf1.Data1;
  if ( (Buf1.Data1 & 0x80000000) != 0 )
  {
LABEL_65:
    v14 = *(void **)&v56.Data1;
    goto LABEL_127;
  }
  v24 = (unsigned __int16 *)v2[38];
  *(_OWORD *)pv = *((_OWORD *)v2 + 13);
  Buf1.Data1 = BlbReadBackupComponentsFromTarget(v24, (UUID *)pv, &v63);
  Data1 = Buf1.Data1;
  if ( (Buf1.Data1 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
    }
    goto LABEL_65;
  }
  CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)(v2 + 3));
  v25 = *(void **)&v56.Data1;
  *((_DWORD *)v2 + 50) = 0;
  while ( 1 )
  {
    v26 = *((_DWORD *)v2 + 50);
    if ( v26 >= *((_DWORD *)v2 + 66) )
    {
      v35 = *((_DWORD *)v2 + 67);
      Data1 = 0;
      Buf1.Data1 = 0;
      v36 = 0;
      if ( v35 )
      {
        while ( *(_DWORD *)(232LL * v36 + v2[28] + 64) != 6 )
        {
          if ( ++v36 >= v35 )
            goto LABEL_118;
        }
      }
      else
      {
LABEL_118:
        if ( v36 == v35 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
          }
          Data1 = -2139619239;
          Buf1.Data1 = -2139619239;
          goto LABEL_124;
        }
      }
      CBlbRestoreComponentAsync::SetState(v2, 6);
      goto LABEL_124;
    }
    v27 = *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                       v2 + 29,
                       v26);
    v28 = *((_DWORD *)v2 + 50);
    if ( v28 )
    {
      v29 = *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                         v2 + 29,
                         (unsigned int)(v28 - 1));
      Buf1 = *(struct _GUID *)(v27 + 20);
      *(_OWORD *)pv = *(_OWORD *)(v29 + 20);
      v1 = 0;
      if ( !memcmp_0(&Buf1, pv, 0x10u) )
        goto LABEL_75;
    }
    if ( v61 )
    {
      CoTaskMemFree(v61);
      v61 = 0;
    }
    v1 = 0;
    Buf1.Data1 = CBlbImpersonationHelper::ImpersonateCaller((CBlbImpersonationHelper *)(v2 + 3), 0);
    Data1 = Buf1.Data1;
    if ( (Buf1.Data1 & 0x80000000) != 0 )
      break;
    v30 = (unsigned __int16 *)v2[38];
    v31 = (struct _GUID)*((_OWORD *)v2 + 13);
    *(_OWORD *)pv = *(_OWORD *)(v27 + 20);
    Buf1 = v31;
    Buf1.Data1 = BlbReadWriterMetadataFromTarget(v30, &Buf1, (struct _GUID *)pv, (LPVOID *)&v61);
    Data1 = Buf1.Data1;
    if ( (Buf1.Data1 & 0x80000000) != 0 )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v34 = 137;
LABEL_114:
        WPP_SF_d(v33[2], v34, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
        goto LABEL_124;
      }
      goto LABEL_124;
    }
    CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)(v2 + 3));
LABEL_75:
    if ( (*(int (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, _QWORD, void *))(*(_QWORD *)v27 + 8LL))(
           v27,
           v63,
           v61,
           v59,
           v25) >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27) >= 0 )
      {
        v32 = 0;
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27) < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
          }
          v32 = -2139619243;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
        }
        v32 = -2139619045;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
      }
      v32 = -2139619245;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 56LL))(v27);
    if ( v32 < 0 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(v2[1] + 16LL))(v2 + 1) )
      {
        Data1 = -2139619299;
        Buf1.Data1 = -2139619299;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
        }
        goto LABEL_124;
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v27 + 32LL))(v27) )
      {
        Data1 = v32;
        Buf1.Data1 = v32;
        goto LABEL_124;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
      }
    }
    CBlbAsync::LockedIncrement((CBlbAsync *)(v2 + 1), (unsigned int *)v2 + 50);
  }
  v33 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v34 = 136;
    goto LABEL_114;
  }
LABEL_124:
  v14 = v25;
LABEL_127:
  v37 = (CBlbImpersonationHelper *)(v2 + 3);
  while ( 1 )
  {
    CBlbImpersonationHelper::Revert(v37);
    if ( v14 )
    {
      if ( v59 )
      {
        v38 = *(_QWORD *)&v56.Data1;
        v39 = v65;
        v40 = 0;
        do
        {
          if ( *(_QWORD *)(v38 + 24 * v40 + 16) )
          {
            if ( v4 )
            {
              CoTaskMemFree(v4);
              v57[0] = 0;
            }
            v41 = BlbutilDuplicateString(*(const unsigned __int16 **)(v38 + 24 * v40 + 16), v57, 0);
            v4 = v57[0];
            v42 = v41;
            v43 = -1;
            do
              ++v43;
            while ( v57[0][v43] );
            v57[0][v43 - 1] = 0;
            if ( v41 < 0
              || (v44 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int16 *, _QWORD))(*v39 + 360LL))(
                          v39,
                          v4,
                          (unsigned int)v41),
                  v42 = v44,
                  v44 < 0) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  144,
                  (unsigned int)&WPP_40d550336cac3d55f04e301f30980d6d_Traceguids,
                  (_DWORD)v4,
                  v42);
              }
            }
          }
          v45 = *(void **)(v38 + 24 * v40 + 16);
          if ( v45 )
            CoTaskMemFree(v45);
          v46 = *(void **)(v38 + 24 * v40 + 8);
          if ( v46 )
            CoTaskMemFree(v46);
          v47 = *(void **)(v38 + 24 * v40);
          if ( v47 )
            CoTaskMemFree(v47);
          ++v1;
          ++v40;
        }
        while ( v1 < v59 );
        v2 = v66;
        Data1 = Buf1.Data1;
        v14 = *(void **)&v56.Data1;
        v37 = (CBlbImpersonationHelper *)(v66 + 3);
      }
      CoTaskMemFree(v14);
    }
    if ( v4 )
      CoTaskMemFree(v4);
    if ( v61 )
      CoTaskMemFree(v61);
    if ( v63 )
      CoTaskMemFree(v63);
    if ( v64 )
      CoTaskMemFree(v64);
    if ( v54 )
      CoUninitialize();
    if ( Data1 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
      }
      CBlbRestoreComponentAsync::SetState(v2, 6);
      v48 = (CBlbAsync *)(v2 + 1);
    }
    else
    {
      v48 = (CBlbAsync *)(v2 + 1);
      if ( !CBlbAsync::CheckPoint((CBlbAsync *)(v2 + 1)) )
      {
        Data1 = -2139618969;
        CBlbAsync::SetResult((CBlbAsync *)(v2 + 1), -2139618969, 0, 0);
      }
      CBlbRestoreComponentAsync::SetAborted((CBlbRestoreComponentAsync *)v2, Data1, v49);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
      }
    }
    v50 = *((_DWORD *)v2 + 4);
    v51 = *((_DWORD *)v2 + 5);
    v55[0] = 0;
    Buf1.Data1 = BlbutilIsClientSKU(v55);
    Data1 = Buf1.Data1;
    if ( (Buf1.Data1 & 0x80000000) == 0 )
      break;
    v14 = *(void **)&v56.Data1;
    v1 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
    }
  }
  if ( v50 < 0 && !v55[0] )
  {
    if ( IsWERRequiredForError(v50) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
      }
      LODWORD(v53) = 0;
      BlbGenerateErrorReport(*((unsigned int *)v2 + 132), 4, (unsigned int)v50, v51, v53, 0, 0, 0);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
    }
  }
  if ( (int)CBlbRestoreComponentAsync::PublishComponentRestoreStopEvent((CBlbRestoreComponentAsync *)v2) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
  }
  CBlbAsync::Done(v48);
  (*(void (__fastcall **)(_QWORD *))(*v2 + 16LL))(v2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_40d550336cac3d55f04e301f30980d6d_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14006a120  push    rbp
0x14006a122  push    rbx
0x14006a123  push    rsi
0x14006a124  push    rdi
0x14006a125  push    r12
0x14006a127  push    r13
0x14006a129  push    r14
0x14006a12b  push    r15
0x14006a12d  lea     rbp, [rsp-238h]
0x14006a135  sub     rsp, 338h
0x14006a13c  mov     rax, cs:__security_cookie
0x14006a143  xor     rax, rsp
0x14006a146  mov     [rbp+270h+var_50], rax
0x14006a14d  xor     esi, esi
0x14006a14f  mov     [rbp+270h+var_268], rcx
0x14006a153  mov     r12, rcx
0x14006a156  mov     qword ptr [rbp+270h+var_2E0.Data1], rsi
0x14006a15a  mov     rcx, [rcx+40h]
0x14006a15e  mov     ebx, esi
0x14006a160  mov     [rbp+270h+var_270], rcx
0x14006a164  mov     r13d, esi
0x14006a167  mov     [rbp+270h+var_2B0], ebx
0x14006a16a  lea     rcx, [r12+8]; this
0x14006a16f  mov     [rbp+270h+var_2D0], rsi
0x14006a173  call    ?GetCatalog@CBlbAsync@@QEAAPEAUIBLBCatalogSystem@@XZ; CBlbAsync::GetCatalog(void)
0x14006a178  mov     r14, rax
0x14006a17b  mov     qword ptr [rbp+270h+Buf1], rax
0x14006a17f  mov     [rbp+270h+var_288], esi
0x14006a182  mov     [rbp+270h+var_280], rsi
0x14006a186  mov     [rbp+270h+var_290], rsi
0x14006a18a  mov     [rbp+270h+var_2F0], sil
0x14006a18e  mov     dword ptr [rbp+270h+pv], esi
0x14006a191  mov     [rbp+270h+var_278], rsi
0x14006a195  mov     r15, cs:WPP_GLOBAL_Control
0x14006a19c  lea     rdi, WPP_GLOBAL_Control
0x14006a1a3  cmp     r15, rdi
0x14006a1a6  jz      loc_14006A2A9
0x14006a1ac  test    byte ptr [r15+1Ch], 1
0x14006a1b1  jz      short loc_14006A1D6
0x14006a1b3  cmp     byte ptr [r15+19h], 4
0x14006a1b8  jb      short loc_14006A1D6
0x14006a1ba  mov     rcx, [r15+10h]
0x14006a1be  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006a1c5  mov     edx, 81h
0x14006a1ca  call    WPP_SF_
0x14006a1cf  mov     r15, cs:WPP_GLOBAL_Control
0x14006a1d6  cmp     r15, rdi
0x14006a1d9  jz      loc_14006A2A9
0x14006a1df  test    byte ptr [r15+1Ch], 1
0x14006a1e4  jz      loc_14006A2A9
0x14006a1ea  cmp     byte ptr [r15+19h], 4
0x14006a1ef  jb      loc_14006A2A9
0x14006a1f5  movzx   ecx, byte ptr [r12+0DEh]
0x14006a1fe  mov     edx, 82h
0x14006a203  movzx   r8d, byte ptr [r12+0DDh]
0x14006a20c  movzx   r9d, byte ptr [r12+0DCh]
0x14006a215  movzx   eax, byte ptr [r12+0DFh]
0x14006a21e  movzx   r10d, byte ptr [r12+0DBh]
0x14006a227  movzx   r11d, byte ptr [r12+0DAh]
0x14006a230  movzx   ebx, byte ptr [r12+0D9h]
0x14006a239  movzx   edi, byte ptr [r12+0D8h]
0x14006a242  movzx   esi, word ptr [r12+0D6h]
0x14006a24b  movzx   r14d, word ptr [r12+0D4h]
0x14006a254  mov     [rsp+370h+var_308], eax
0x14006a258  mov     [rsp+370h+var_310], ecx
0x14006a25c  mov     rcx, [r15+10h]
0x14006a260  mov     [rsp+370h+var_318], r8d
0x14006a265  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006a26c  mov     dword ptr [rsp+370h+var_320], r9d
0x14006a271  mov     r9d, [r12+0D0h]
0x14006a279  mov     dword ptr [rsp+370h+var_328], r10d
0x14006a27e  mov     dword ptr [rsp+370h+var_330], r11d
0x14006a283  mov     [rsp+370h+var_338], ebx
0x14006a287  mov     dword ptr [rsp+370h+var_340], edi
0x14006a28b  mov     dword ptr [rsp+370h+var_348], esi
0x14006a28f  mov     dword ptr [rsp+370h+var_350], r14d
0x14006a294  call    WPP_SF_DDDDDDDDDDD
0x14006a299  mov     r14, qword ptr [rbp+270h+Buf1]
0x14006a29d  lea     rdi, WPP_GLOBAL_Control
0x14006a2a4  xor     esi, esi
0x14006a2a6  mov     ebx, r13d
0x14006a2a9  lea     r8, [rbp+270h+var_278]; unsigned __int16 ***
0x14006a2ad  mov     rcx, r12; this
0x14006a2b0  lea     rdx, [rbp+270h+pv]; unsigned int *
0x14006a2b4  call    ?GetComponentNameList@CBlbRestoreComponentAsync@@AEAAJPEAKPEAPEAPEAG@Z; CBlbRestoreComponentAsync::GetComponentNameList(ulong *,ushort * * *)
0x14006a2b9  mov     dword ptr [rbp+270h+Buf1], eax
0x14006a2bc  mov     r15d, eax
0x14006a2bf  test    eax, eax
0x14006a2c1  js      loc_14006AB91
0x14006a2c7  movups  xmm0, xmmword ptr [r12+0D0h]
0x14006a2d0  mov     r9, [r12+208h]; struct _FILETIME
0x14006a2d8  lea     rcx, [rbp+270h+var_2E0]; struct _GUID
0x14006a2dc  mov     r8d, dword ptr [rbp+270h+pv]; unsigned int
0x14006a2e0  mov     rdx, [rbp+270h+var_278]; unsigned __int16 **
0x14006a2e4  movdqu  xmmword ptr [rbp+270h+var_2E0.Data1], xmm0
0x14006a2e9  call    ?PublishRestoreStartedEvent@@YAJU_GUID@@PEAPEAGIU_FILETIME@@@Z; PublishRestoreStartedEvent(_GUID,ushort * *,uint,_FILETIME)
0x14006a2ee  test    eax, eax
0x14006a2f0  jns     short loc_14006A322
0x14006a2f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a2f9  cmp     rcx, rdi
0x14006a2fc  jz      short loc_14006A322
0x14006a2fe  test    byte ptr [rcx+1Ch], 1
0x14006a302  jz      short loc_14006A322
0x14006a304  cmp     byte ptr [rcx+19h], 2
0x14006a308  jb      short loc_14006A322
0x14006a30a  mov     rcx, [rcx+10h]
0x14006a30e  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006a315  mov     edx, 83h
0x14006a31a  mov     r9d, eax
0x14006a31d  call    WPP_SF_d
0x14006a322  mov     r8d, [r12+178h]
0x14006a32a  test    r8d, r8d
0x14006a32d  jz      short loc_14006A35B
0x14006a32f  mov     r9, [r12+180h]
0x14006a337  mov     edx, esi
0x14006a339  mov     eax, edx
0x14006a33b  imul    rcx, rax, 78h ; 'x'
0x14006a33f  lea     eax, [rbx+1]
0x14006a342  test    byte ptr [rcx+r9+10h], 1
0x14006a348  cmovnz  eax, ebx
0x14006a34b  inc     edx
0x14006a34d  mov     ebx, eax
0x14006a34f  cmp     edx, r8d
0x14006a352  jb      short loc_14006A339
0x14006a354  mov     [rbp+270h+var_2B0], eax
0x14006a357  test    eax, eax
0x14006a359  jnz     short loc_14006A373
0x14006a35b  lea     r8, aCvolumemap0; "cVolumeMap > 0"
0x14006a362  mov     edx, 0D5Bh; unsigned int
0x14006a367  lea     rcx, aBaseStorBlbEng_18; "base\\stor\\blb\\engine\\service\\compo"...
0x14006a36e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14006a373  mov     eax, ebx
0x14006a375  lea     rbx, [rax+rax*2]
0x14006a379  shl     rbx, 3
0x14006a37d  mov     rcx, rbx; cb
0x14006a380  call    cs:__imp_CoTaskMemAlloc
0x14006a386  mov     qword ptr [rbp+270h+var_2E0.Data1], rax
0x14006a38a  mov     rdi, rax
0x14006a38d  test    rax, rax
0x14006a390  jnz     short loc_14006A3A1
0x14006a392  mov     r15d, 8007000Eh
0x14006a398  mov     dword ptr [rbp+270h+Buf1], r15d
0x14006a39c  jmp     loc_14006AB94
0x14006a3a1  mov     r8, rbx; Size
0x14006a3a4  xor     edx, edx; Val
0x14006a3a6  mov     rcx, rax; void *
0x14006a3a9  call    memset_0
0x14006a3ae  xor     edx, edx; dwCoInit
0x14006a3b0  xor     ecx, ecx; pvReserved
0x14006a3b2  call    cs:__imp_CoInitializeEx
0x14006a3b8  mov     dword ptr [rbp+270h+Buf1], eax
0x14006a3bb  mov     r15d, eax
0x14006a3be  test    eax, eax
0x14006a3c0  jns     short loc_14006A40A
0x14006a3c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a3c9  lea     rax, WPP_GLOBAL_Control
0x14006a3d0  cmp     rcx, rax
0x14006a3d3  jz      loc_14006AB94
0x14006a3d9  test    byte ptr [rcx+1Ch], 1
0x14006a3dd  jz      loc_14006AB94
0x14006a3e3  cmp     byte ptr [rcx+19h], 2
0x14006a3e7  jb      loc_14006AB94
0x14006a3ed  mov     rcx, [rcx+10h]
0x14006a3f1  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006a3f8  mov     edx, 84h
0x14006a3fd  mov     r9d, r15d
0x14006a400  call    WPP_SF_d
0x14006a405  jmp     loc_14006AB94
0x14006a40a  mov     edi, esi
0x14006a40c  mov     [rbp+270h+var_2F0], 1
0x14006a410  cmp     esi, [r12+178h]
0x14006a418  jnb     loc_14006A6FD
0x14006a41e  xor     ebx, ebx
0x14006a420  mov     eax, esi
0x14006a422  imul    r13, rax, 78h ; 'x'
0x14006a426  mov     [rbp+270h+var_260], bx
0x14006a42a  add     r13, [r12+180h]
0x14006a432  test    byte ptr [r13+10h], 1
0x14006a437  jnz     loc_14006A634
0x14006a43d  lea     rcx, [r12+18h]; this
0x14006a442  call    ?GetImpersonationToken@CBlbImpersonationHelper@@QEAAPEAXXZ; CBlbImpersonationHelper::GetImpersonationToken(void)
0x14006a447  mov     r11, [rbp+270h+var_270]
0x14006a44b  lea     r8, [rbp+270h+pv]
0x14006a44f  movups  xmm0, xmmword ptr [r13+0]
0x14006a454  mov     [rsp+370h+var_318], ebx
0x14006a458  xor     r9d, r9d
0x14006a45b  movups  xmm1, xmmword ptr [r12+0D0h]
0x14006a464  mov     rcx, [r11]
0x14006a467  lea     rdx, [rbp+270h+Buf1]
0x14006a46b  movdqu  xmmword ptr [rbp+270h+pv], xmm0
0x14006a470  movdqu  [rbp+270h+Buf1], xmm1
0x14006a475  mov     r10, [rcx+158h]
0x14006a47c  lea     rcx, [rbp+270h+var_260]
0x14006a480  mov     [rsp+370h+var_320], rcx
0x14006a485  lea     rcx, [rbp+270h+var_288]
0x14006a489  mov     [rsp+370h+var_328], rcx
0x14006a48e  mov     rcx, [r12+110h]
0x14006a496  mov     [rsp+370h+var_330], r14
0x14006a49b  mov     [rsp+370h+var_338], 104h
0x14006a4a3  mov     [rsp+370h+var_340], rax
0x14006a4a8  mov     rax, r10
0x14006a4ab  mov     [rsp+370h+var_348], rbx
0x14006a4b0  mov     [rsp+370h+var_350], rcx
0x14006a4b5  mov     rcx, r11
0x14006a4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a4bd  mov     dword ptr [rbp+270h+Buf1], eax
0x14006a4c0  mov     r15d, eax
0x14006a4c3  test    eax, eax
0x14006a4c5  js      loc_14006A63F
0x14006a4cb  mov     rcx, [r13+18h]; unsigned __int16 *
0x14006a4cf  test    rcx, rcx
0x14006a4d2  jz      short loc_14006A4E2
0x14006a4d4  xor     r8d, r8d; unsigned __int64
0x14006a4d7  lea     rdx, [rbp+270h+var_2D0]; unsigned __int16 **
0x14006a4db  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14006a4e0  jmp     short loc_14006A4F5
0x14006a4e2  mov     edx, [r13+10h]; unsigned int
0x14006a4e6  lea     r8, [rbp+270h+var_2D0]; unsigned __int16 **
0x14006a4ea  xor     r9d, r9d; unsigned __int8
0x14006a4ed  mov     rcx, r13; struct _GUID *
0x14006a4f0  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x14006a4f5  mov     dword ptr [rbp+270h+Buf1], eax
0x14006a4f8  mov     r15d, eax
0x14006a4fb  test    eax, eax
0x14006a4fd  js      loc_14006A6EE
0x14006a503  mov     r13, [rbp+270h+var_2D0]
0x14006a507  mov     eax, edi
0x14006a509  lea     rcx, [rax+rax*2]
0x14006a50d  mov     rax, qword ptr [rbp+270h+var_2E0.Data1]
0x14006a511  lea     rbx, [rax+rcx*8]
0x14006a515  mov     rcx, r13; unsigned __int16 *
0x14006a518  mov     rdx, rbx; unsigned __int16 **
0x14006a51b  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14006a520  mov     r15d, eax
0x14006a523  mov     dword ptr [rbp+270h+Buf1], eax
0x14006a526  xor     eax, eax
0x14006a528  test    r15d, r15d
0x14006a52b  js      loc_14006A6F2
0x14006a531  mov     rcx, [r12+118h]; unsigned __int16 *
0x14006a539  xor     r8d, r8d; unsigned __int64
0x14006a53c  test    rcx, rcx
0x14006a53f  jnz     short loc_14006A5A3
0x14006a541  mov     rcx, [rbx]; unsigned __int16 *
0x14006a544  lea     rdx, [rbx+8]; unsigned __int16 **
0x14006a548  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14006a54d  mov     dword ptr [rbp+270h+Buf1], eax
0x14006a550  mov     r15d, eax
0x14006a553  test    eax, eax
0x14006a555  jns     loc_14006A5E4
0x14006a55b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a562  lea     rax, WPP_GLOBAL_Control
0x14006a569  cmp     rcx, rax
0x14006a56c  jz      loc_14006A6F2
0x14006a572  test    byte ptr [rcx+1Ch], 1
0x14006a576  jz      loc_14006A6F2
0x14006a57c  cmp     byte ptr [rcx+19h], 2
0x14006a580  jb      loc_14006A6F2
0x14006a586  mov     rcx, [rcx+10h]
0x14006a58a  lea     r8, WPP_40d550336cac3d55f04e301f30980d6d_Traceguids
0x14006a591  mov     edx, 86h
0x14006a596  mov     r9d, r15d
0x14006a599  call    WPP_SF_d
0x14006a59e  jmp     loc_14006A6F2
0x14006a5a3  lea     rdx, [rbp+270h+pv]; unsigned __int16 **
0x14006a5a7  mov     [rbp+270h+pv], rax
0x14006a5ab  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14006a5b0  mov     dword ptr [rbp+270h+Buf1], eax
0x14006a5b3  mov     r15d, eax
0x14006a5b6  test    eax, eax
0x14006a5b8  js      loc_14006A6F2
0x14006a5be  mov     rcx, [rbp+270h+pv]; unsigned __int16 *
0x14006a5c2  lea     rdx, [rbx+8]; unsigned __int16 **
0x14006a5c6  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14006a5cb  mov     rcx, [rbp+270h+pv]; pv
0x14006a5cf  mov     r15d, eax
0x14006a5d2  mov     dword ptr [rbp+270h+Buf1], eax
0x14006a5d5  call    cs:__imp_CoTaskMemFree
0x14006a5db  test    r15d, r15d
0x14006a5de  js      loc_14006A6F2
0x14006a5e4  mov     rcx, r13; pv
0x14006a5e7  call    cs:__imp_CoTaskMemFree
0x14006a5ed  xor     r13d, r13d
0x14006a5f0  lea     rdx, [rbp+270h+var_2D0]; unsigned __int16 **
0x14006a5f4  xor     r8d, r8d; unsigned __int64
0x14006a5f7  mov     [rbp+270h+var_2D0], r13
0x14006a5fb  lea     rcx, [rbp+270h+var_260]; unsigned __int16 *
0x14006a5ff  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14006a604  mov     dword ptr [rbp+270h+Buf1], eax
0x14006a607  mov     r15d, eax
0x14006a60a  test    eax, eax
0x14006a60c  js      loc_14006A6EE
0x14006a612  mov     r13, [rbp+270h+var_2D0]
0x14006a616  lea     rdx, [rbx+10h]; unsigned __int16 **
0x14006a61a  mov     rcx, r13; unsigned __int16 *
0x14006a61d  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14006a622  mov     dword ptr [rbp+270h+Buf1], eax
0x14006a625  mov     r15d, eax
0x14006a628  test    eax, eax
0x14006a62a  js      loc_14006A6F2
0x14006a630  inc     edi
  ... truncated ...
```
