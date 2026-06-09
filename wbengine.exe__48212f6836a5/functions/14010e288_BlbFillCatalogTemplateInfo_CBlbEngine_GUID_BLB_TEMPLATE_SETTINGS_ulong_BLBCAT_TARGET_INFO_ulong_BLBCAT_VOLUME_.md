# BlbFillCatalogTemplateInfo(CBlbEngine *,_GUID *,_BLB_TEMPLATE_SETTINGS *,ulong,_BLBCAT_TARGET_INFO *,ulong,_BLBCAT_VOLUME_INFO *,CBlbImpersonationHelper *,_BLBCAT_TEMPLATE_INFO *)

- ea: `0x14010e288`
- end: `0x14010fc56`
- name: `?BlbFillCatalogTemplateInfo@@YAJPEAVCBlbEngine@@PEAU_GUID@@PEAU_BLB_TEMPLATE_SETTINGS@@KPEAU_BLBCAT_TARGET_INFO@@KPEAU_BLBCAT_VOLUME_INFO@@PEAVCBlbImpersonationHelper@@PEAU_BLBCAT_TEMPLATE_INFO@@@Z`
- size: `6606`
- prototype: `int(struct CBlbEngine *, struct _GUID *, struct _BLB_TEMPLATE_SETTINGS *, unsigned int, struct _BLBCAT_TARGET_INFO *, unsigned int, struct _BLBCAT_VOLUME_INFO *, struct CBlbImpersonationHelper *, struct _BLBCAT_TEMPLATE_INFO *)`
- caller_count: `2`
- callee_count: `65`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140042ca0`
- `0x140049e40`

## callees

- `0x140006ca8`
- `0x140006d94`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be04`
- `0x14000cbcc`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x140014624`
- `0x140015148`
- `0x140027760`
- `0x140027d4c`
- `0x140034134`
- `0x14003d4ec`
- `0x1400877b0`
- `0x1400881ac`
- `0x14008863c`
- `0x1400889f0`
- `0x14008aa6c`
- `0x14008ae5c`
- `0x14008b58c`
- `0x14008ba2c`
- `0x14008f1b8`
- `0x14008f45c`
- `0x14008fed0`
- `0x14009257c`
- `0x140093604`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f4964`
- `0x1400f5164`
- `0x1400f5228`
- `0x1400f7208`
- `0x1400f85a0`
- `0x1400fad0c`
- `0x1400fb0c8`
- `0x1400fbfc0`
- `0x1400fcc68`
- `0x1400fd358`
- `0x1400fdb78`
- `0x1400ffe98`
- `0x1401003b8`
- `0x14010158c`
- `0x140104e24`
- `0x140108ccc`
- `0x140109be8`
- `0x14010e004`
- `0x14010e288`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14010f77a`
- `msvcrt!_wcsicmp` at `0x14010f77a`
- `ole32!CoTaskMemAlloc` at `0x14010ed5f`
- `ole32!CoTaskMemAlloc` at `0x14010f4b2`
- `ole32!CoTaskMemAlloc` at `0x14010ed5f`
- `ole32!CoTaskMemAlloc` at `0x14010f4b2`
- `ole32!CoTaskMemFree` at `0x14010e48b`
- `ole32!CoTaskMemFree` at `0x14010e4a0`
- `ole32!CoTaskMemFree` at `0x14010e4b2`
- `ole32!CoTaskMemFree` at `0x14010e4c1`
- `ole32!CoTaskMemFree` at `0x14010e4d3`
- `ole32!CoTaskMemFree` at `0x14010e512`
- `ole32!CoTaskMemFree` at `0x14010edfa`
- `ole32!CoTaskMemFree` at `0x14010ef58`
- `ole32!CoTaskMemFree` at `0x14010efd7`
- `ole32!CoTaskMemFree` at `0x14010f17b`
- `ole32!CoTaskMemFree` at `0x14010f381`
- `ole32!CoTaskMemFree` at `0x14010f8b6`
- `ole32!CoTaskMemFree` at `0x14010fbc7`
- `ole32!CoTaskMemFree` at `0x14010e48b`
- `ole32!CoTaskMemFree` at `0x14010e4a0`
- `ole32!CoTaskMemFree` at `0x14010e4b2`
- `ole32!CoTaskMemFree` at `0x14010e4c1`
- `ole32!CoTaskMemFree` at `0x14010e4d3`
- `ole32!CoTaskMemFree` at `0x14010e512`
- `ole32!CoTaskMemFree` at `0x14010edfa`
- `ole32!CoTaskMemFree` at `0x14010ef58`
- `ole32!CoTaskMemFree` at `0x14010efd7`
- `ole32!CoTaskMemFree` at `0x14010f17b`
- `ole32!CoTaskMemFree` at `0x14010f381`
- `ole32!CoTaskMemFree` at `0x14010f8b6`
- `ole32!CoTaskMemFree` at `0x14010fbc7`
- `OLEAUT32!__imp_SysFreeString` at `0x14010e7db`
- `OLEAUT32!__imp_SysFreeString` at `0x14010e914`
- `OLEAUT32!__imp_SysFreeString` at `0x14010e7db`
- `OLEAUT32!__imp_SysFreeString` at `0x14010e914`

## string_xrefs

- `0x14010e683`: `pTemplate->m_rgFileSpecs == NULL`
- `0x14010e6a7`: `pTemplate->m_cFileSpecs == 0`
- `0x14010f57d`: `pTemplate->m_cTarget == 1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BlbFillCatalogTemplateInfo(
        struct CBlbEngine *a1,
        struct _GUID *a2,
        struct _BLB_TEMPLATE_SETTINGS *a3,
        unsigned int a4,
        OLECHAR *a5,
        unsigned int a6,
        struct _BLBCAT_VOLUME_INFO *a7,
        struct CBlbImpersonationHelper *a8,
        struct _BLBCAT_TEMPLATE_INFO *a9)
{
  struct _BLBCAT_TEMPLATE_INFO *v11; // r13
  int v12; // r14d
  void *v13; // r12
  struct _BLB_TEMPLATE_SETTINGS *v14; // rdi
  int IsClientSKU; // ebx
  const unsigned __int16 *v16; // rcx
  struct _BLBCAT_TEMPLATE_INFO *v17; // r14
  unsigned __int16 *v18; // r15
  CBlbBackupItemsHelper *v19; // r12
  unsigned int v20; // edx
  struct _BLB_VOLUME_VHD_INFO *v21; // rsi
  CBlbBackupItemsHelper *v23; // rax
  _QWORD *v24; // rsi
  PVOID *v25; // rcx
  unsigned int v26; // ecx
  unsigned int v27; // edx
  unsigned int i; // r15d
  bool v29; // zf
  __int64 v30; // r13
  const struct _GUID *v31; // r8
  unsigned __int64 v32; // r12
  __int64 v33; // rax
  char v34; // bl
  ATL::CComBSTR *v35; // rax
  char *v36; // rsi
  char v37; // cl
  unsigned __int8 v38; // bl
  ATL::CComBSTR *v39; // rax
  unsigned int j; // edx
  __int64 v41; // rdx
  struct CBlbEngine *v42; // r15
  int VolumesToBackup; // eax
  unsigned int v44; // r10d
  unsigned __int64 v45; // r8
  unsigned int k; // r8d
  int v47; // esi
  int v48; // r14d
  unsigned int v49; // ebx
  unsigned __int64 v50; // rcx
  unsigned __int8 IsFileSystemCSVFS; // al
  unsigned int m; // ecx
  unsigned __int64 v53; // rax
  void *v54; // rcx
  int v55; // ebx
  unsigned int v56; // ecx
  __int64 v57; // rsi
  __int64 v58; // r12
  struct _GUID *v59; // r13
  __int64 v60; // r14
  unsigned int v61; // r15d
  __int64 v62; // rbx
  unsigned __int8 v63; // si
  BSTR v64; // r13
  __int64 v65; // rbx
  unsigned int VolumeIndexInOldVolumeList; // eax
  __int64 v67; // r14
  unsigned int v68; // edx
  __int64 v69; // rdx
  unsigned __int16 *v70; // rsi
  int v71; // edx
  int v72; // r8d
  unsigned __int64 v73; // rbx
  struct _BLB_VOLUME_INFO *v74; // rsi
  BSTR v75; // r14
  int v76; // r9d
  unsigned int kk; // r14d
  __int64 v78; // rbx
  __int64 v79; // rax
  unsigned int v80; // esi
  int IsVolumeVirtual; // eax
  PVOID *v82; // rcx
  unsigned __int8 v83; // al
  unsigned int n; // r14d
  const struct _GUID *v85; // rsi
  struct _BLB_VOLUME_VHD_INFO *v86; // rbx
  int VolumeVHDInfo; // eax
  char v88; // r15
  unsigned int v89; // eax
  __int64 StartPosition; // rax
  __int64 Next; // rax
  __int64 v92; // rbx
  BlbGuidStr *v93; // rbx
  unsigned int v94; // eax
  void *v95; // rcx
  CBlbImpersonationHelper *v96; // rsi
  int VolumeMediaType; // eax
  _QWORD *v98; // rcx
  int v99; // edx
  __int64 v100; // r9
  __int64 v101; // rdx
  int v102; // esi
  char v103; // r13
  unsigned int ii; // r12d
  unsigned int jj; // ebx
  __int64 v106; // rsi
  PVOID *v107; // rbx
  _QWORD *v108; // rcx
  __int64 v109; // rax
  BSTR v110; // rbx
  unsigned int TargetIndexInOldTargetList; // eax
  unsigned __int16 *v112; // rsi
  __int64 v113; // rdx
  void *v114; // rcx
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  CBlbBackupItemsHelper *v116; // [rsp+70h] [rbp-90h]
  unsigned __int8 IsSSBToAnyVolumeAllowed; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v118[3]; // [rsp+79h] [rbp-87h] BYREF
  OLECHAR v119[2]; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int8 v120[8]; // [rsp+80h] [rbp-80h] BYREF
  char v121[8]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v122; // [rsp+90h] [rbp-70h]
  unsigned int v123; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v124; // [rsp+98h] [rbp-68h] BYREF
  struct _BLB_VOLUME_INFO *v125; // [rsp+A0h] [rbp-60h] BYREF
  int v126; // [rsp+A8h] [rbp-58h] BYREF
  struct _BLB_VOLUME_INFO *v127; // [rsp+B0h] [rbp-50h] BYREF
  struct _BLB_TEMPLATE_SETTINGS *v128; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v129; // [rsp+C0h] [rbp-40h] BYREF
  BSTR bstrString[2]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v131; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v132; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v133; // [rsp+E8h] [rbp-18h]
  __int64 v134; // [rsp+F0h] [rbp-10h]
  struct CBlbEngine *v135; // [rsp+F8h] [rbp-8h]
  struct _BLB_VOLUME_INFO *v136; // [rsp+100h] [rbp+0h] BYREF
  BSTR v137; // [rsp+108h] [rbp+8h] BYREF
  CBlbImpersonationHelper *v138; // [rsp+110h] [rbp+10h]
  unsigned __int64 v139; // [rsp+118h] [rbp+18h] BYREF
  struct _GUID v140; // [rsp+120h] [rbp+20h] BYREF
  struct _GUID Buf1; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v142[80]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v143[112]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v144[112]; // [rsp+200h] [rbp+100h] BYREF

  v123 = a4;
  v135 = a1;
  v11 = a9;
  v137 = a5;
  *(_QWORD *)&v140.Data1 = a7;
  v138 = a8;
  v12 = 0;
  v126 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_f64988f85895305c69b26f06d2565e84_Traceguids);
  }
  v129 = 0;
  v132 = 0;
  Buf1 = 0;
  v126 = 0;
  v13 = 0;
  pv = 0;
  v131 = 0;
  v127 = 0;
  v124 = 0;
  v125 = 0;
  *(_DWORD *)v119 = 0;
  v14 = 0;
  v128 = 0;
  v116 = 0;
  ATL::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>(
    (unsigned int)v142,
    (_DWORD)a2,
    (_DWORD)a3,
    a4,
    LODWORD(FLOAT_2_25));
  v118[0] = 0;
  v120[0] = 0;
  IsClientSKU = BlbutilIsClientSKU(v120);
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  BlbCleanupCatalogTemplateInfo(a9);
  *(struct _GUID *)a9 = *a2;
  IsClientSKU = BlbutilMemalloc((void **)&v128, 1u, 0xA8u);
  v14 = v128;
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  IsClientSKU = CopyTemplateSettings(a3, v128);
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  IsClientSKU = BlbutilDuplicateString(*(const unsigned __int16 **)v14, (unsigned __int16 **)a9 + 2, 0);
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  *((_DWORD *)a9 + 7) = *((_DWORD *)v14 + 2);
  *((_BYTE *)a9 + 115) = *((_BYTE *)v14 + 107);
  *((_DWORD *)a9 + 29) = *((_DWORD *)v14 + 28);
  *((_BYTE *)a9 + 120) = *((_BYTE *)v14 + 116);
  *((_DWORD *)a9 + 34) = *((_DWORD *)v14 + 40);
  v16 = (const unsigned __int16 *)*((_QWORD *)v14 + 2);
  if ( !v16 )
  {
LABEL_10:
    IsClientSKU = -2139619316;
    goto LABEL_11;
  }
  IsClientSKU = BlbutilDuplicateString(v16, (unsigned __int16 **)a9 + 4, 0);
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  v23 = (CBlbBackupItemsHelper *)operator new(0x20u);
  v116 = v23;
  bstrString[0] = (BSTR)v23;
  if ( !v23 )
  {
    v19 = 0;
    IsClientSKU = -2147024882;
    goto LABEL_387;
  }
  *((_QWORD *)v23 + 1) = 0;
  *(_QWORD *)v23 = 0;
  v24 = (_QWORD *)((char *)v14 + 80);
  if ( *((_QWORD *)v14 + 10) && *((_QWORD *)v14 + 11) && *((_QWORD *)v14 + 12) )
  {
    v25 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_f64988f85895305c69b26f06d2565e84_Traceguids);
      v25 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *v24 && *((_QWORD *)v14 + 11) && *((_QWORD *)v14 + 12) )
    {
      if ( *((_QWORD *)v14 + 16) )
      {
        BlbAssert(
          "base\\stor\\blb\\engine\\blbengutils\\blbcatalogutils.cpp",
          0x357u,
          "pTemplate->m_rgFileSpecs == NULL");
        v25 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( *((_DWORD *)v14 + 30) )
      {
        BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbcatalogutils.cpp", 0x358u, "pTemplate->m_cFileSpecs == 0");
        v25 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !*((_QWORD *)v14 + 16) && !*((_DWORD *)v14 + 30) )
      {
        IsClientSKU = (*(__int64 (__fastcall **)(struct CBlbEngine *, unsigned int *, struct _BLB_VOLUME_INFO **))(*(_QWORD *)v135 + 64LL))(
                        v135,
                        &v124,
                        &v127);
        if ( IsClientSKU < 0 )
          goto LABEL_92;
        *(_DWORD *)v119 = *((_DWORD *)v14 + 18);
        IsClientSKU = BlbutilMemalloc((void **)&v125, *(unsigned int *)v119, 0x80u);
        if ( IsClientSKU < 0 )
          goto LABEL_92;
        v26 = 0;
        v27 = v124;
        while ( 2 )
        {
          v122 = v26;
          if ( v26 < *((_DWORD *)v14 + 18) )
          {
            for ( i = 0; ; ++i )
            {
              v29 = i == v27;
              if ( i >= v27 )
                break;
              v30 = v26;
              v31 = (const struct _GUID *)(*v24 + 16LL * v26);
              v32 = (unsigned __int64)i << 7;
              v33 = *(_QWORD *)((char *)v127 + v32) - *(_QWORD *)&v31->Data1;
              if ( !v33 )
                v33 = *(_QWORD *)((char *)v127 + v32 + 8) - *(_QWORD *)v31->Data4;
              if ( !v33 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  v34 = *(_BYTE *)(*((_QWORD *)v14 + 12) + v26);
                  v35 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, v31);
                  v12 |= 1u;
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    45,
                    (unsigned int)&WPP_f64988f85895305c69b26f06d2565e84_Traceguids,
                    *(_QWORD *)v35,
                    v34);
                }
                if ( (v12 & 1) != 0 )
                {
                  v12 &= ~1u;
                  SysFreeString(bstrString[0]);
                }
                IsClientSKU = CopyVolumeInfo(
                                (struct _BLB_VOLUME_INFO *)((char *)v127 + v32),
                                (struct _BLB_VOLUME_INFO *)((char *)v125 + 128 * v30));
                if ( IsClientSKU < 0 )
                  goto LABEL_11;
                v36 = (char *)v125 + 128 * v30;
                v136 = (struct _BLB_VOLUME_INFO *)v36;
                v37 = *(_BYTE *)(*((_QWORD *)v14 + 12) + v30);
                v36[84] = v37;
                if ( v37 )
                {
                  *(_DWORD *)v121 = 0;
                  v38 = v36[88] & 1;
                  v118[0] = BlbutilIsFileSystemCSVFS(*((unsigned __int16 **)v36 + 6));
                  IsClientSKU = CBlbBackupItemsHelper::GetVolumeBackupFlags(
                                  *((_BYTE *)v14 + 108),
                                  *((_BYTE *)v14 + 116),
                                  (*((_DWORD *)v36 + 22) & 0x200) != 0,
                                  v38,
                                  v118[0],
                                  *((struct _BLB_FILESPEC_INFO **)v36 + 14),
                                  *((_DWORD *)v36 + 26),
                                  (unsigned int *)v121);
                  if ( IsClientSKU < 0 )
                    goto LABEL_11;
                  *((_DWORD *)v36 + 22) |= *(_DWORD *)v121;
                  *(_DWORD *)(*((_QWORD *)v14 + 11) + 4 * v30) = *((_DWORD *)v36 + 22);
                  IsClientSKU = CBlbBackupItemsHelper::UpdateVolumeSpecsIfRequired(&v136);
                  if ( IsClientSKU < 0 )
                    goto LABEL_11;
                }
                v27 = v124;
                v26 = v122;
                v24 = (_QWORD *)((char *)v14 + 80);
                v29 = i == v124;
                break;
              }
              v26 = v122;
            }
            if ( !v29 )
            {
              ++v26;
              continue;
            }
            IsClientSKU = -2139619191;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v39 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v137, (const struct _GUID *)(*v24 + 16LL * v26));
              LOBYTE(v12) = v12 | 2;
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                46,
                &WPP_f64988f85895305c69b26f06d2565e84_Traceguids,
                *(_QWORD *)v39);
            }
            if ( (v12 & 2) != 0 )
              SysFreeString(v137);
            goto LABEL_92;
          }
          break;
        }
        j = *(_DWORD *)v119;
        v11 = a9;
        v13 = pv;
        goto LABEL_117;
      }
      IsClientSKU = -2147024809;
      if ( v25 == &WPP_GLOBAL_Control || (*((_BYTE *)v25 + 28) & 1) == 0 || *((_BYTE *)v25 + 25) < 2u )
        goto LABEL_92;
      v41 = 44;
    }
    else
    {
      IsClientSKU = -2147467261;
      if ( v25 == &WPP_GLOBAL_Control || (*((_BYTE *)v25 + 28) & 1) == 0 || *((_BYTE *)v25 + 25) < 2u )
        goto LABEL_92;
      v41 = 43;
    }
LABEL_98:
    WPP_SF_d(v25[2], v41, &WPP_f64988f85895305c69b26f06d2565e84_Traceguids);
    goto LABEL_92;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_f64988f85895305c69b26f06d2565e84_Traceguids);
  }
  v42 = v135;
  IsClientSKU = (*(__int64 (__fastcall **)(struct CBlbEngine *, unsigned int *, struct _BLB_VOLUME_INFO **))(*(_QWORD *)v135 + 64LL))(
                  v135,
                  &v124,
                  &v127);
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  *(_DWORD *)v121 = 0;
  IsClientSKU = (*(__int64 (__fastcall **)(struct CBlbEngine *, char *))(*(_QWORD *)v42 + 400LL))(v42, v121);
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  VolumesToBackup = CBlbBackupItemsHelper::GetVolumesToBackup(
                      v124,
                      v127,
                      *((_DWORD *)v14 + 30),
                      *((struct _BLB_FILESPEC_INFO **)v14 + 16),
                      0,
                      *((_BYTE *)v14 + 108),
                      *((_BYTE *)v14 + 116),
                      v121[0],
                      0,
                      0,
                      v119,
                      &v125);
  IsClientSKU = VolumesToBackup;
  if ( VolumesToBackup < 0 && (VolumesToBackup != -2139619008 || !*((_DWORD *)v14 + 34)) )
    goto LABEL_11;
  *((_DWORD *)v14 + 18) = *(_DWORD *)v119;
  IsClientSKU = BlbutilMemalloc((void **)v14 + 10, *(unsigned int *)v119, 0x10u);
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  IsClientSKU = BlbutilMemalloc((void **)v14 + 11, *((_DWORD *)v14 + 18), 4u);
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  IsClientSKU = BlbutilMemalloc((void **)v14 + 12, *((_DWORD *)v14 + 18), 1u);
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  v44 = 0;
  for ( j = *(_DWORD *)v119; v44 < *(_DWORD *)v119; j = *(_DWORD *)v119 )
  {
    v45 = (unsigned __int64)v44 << 7;
    *(_BYTE *)(v44 + *((_QWORD *)v14 + 12)) = *((_BYTE *)v125 + v45 + 84);
    *(_OWORD *)(*((_QWORD *)v14 + 10) + 16LL * v44) = *(_OWORD *)((char *)v125 + v45);
    *(_DWORD *)(*((_QWORD *)v14 + 11) + 4LL * v44++) = *(_DWORD *)((char *)v125 + v45 + 88);
  }
LABEL_117:
  for ( k = 0; k < j; ++k )
  {
    if ( *((_BYTE *)v125 + 128 * (unsigned __int64)k + 84) )
      break;
  }
  if ( k == j && !*((_DWORD *)v14 + 34) )
  {
    IsClientSKU = -2139618958;
    v25 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_92;
    }
    v41 = 48;
    goto LABEL_98;
  }
  v47 = 0;
  v48 = 0;
  v49 = 0;
  if ( j )
  {
    do
    {
      v50 = (unsigned __int64)v49 << 7;
      if ( *((_BYTE *)v125 + v50 + 84) )
      {
        IsFileSystemCSVFS = BlbutilIsFileSystemCSVFS(*(unsigned __int16 **)((char *)v125 + v50 + 48));
        j = *(_DWORD *)v119;
        if ( IsFileSystemCSVFS )
          ++v47;
        else
          ++v48;
      }
      ++v49;
    }
    while ( v49 < j );
    if ( v47 )
    {
      if ( v48 )
      {
        IsClientSKU = -2139618936;
        v25 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_92;
        }
        v41 = 49;
        goto LABEL_98;
      }
      *(_DWORD *)v121 = 0;
      IsClientSKU = BlbutilGetTestHookValue(L"CsvSupportSettings", L"CsvSourceSupported", 1u, (unsigned int *)v121);
      if ( IsClientSKU < 0 )
        goto LABEL_11;
      if ( !*(_DWORD *)v121 )
      {
        IsClientSKU = -2139618977;
        v25 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_92;
        }
        v41 = 50;
        goto LABEL_98;
      }
    }
  }
  IsClientSKU = BlbutilDuplicateString(*((const unsigned __int16 **)v14 + 8), (unsigned __int16 **)v11 + 9, 0);
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  *((_DWORD *)v11 + 20) = *((_DWORD *)v14 + 18);
  if ( ((*((_DWORD *)v14 + 2) - 1) & 0xFFFFFFFB) == 0 )
  {
    for ( m = 0; m < *(_DWORD *)v119; ++m )
    {
      v53 = (unsigned __int64)m << 7;
      if ( *((_BYTE *)v125 + v53 + 84) && (*((_BYTE *)v125 + v53 + 88) & 8) == 0 )
        goto LABEL_152;
    }
    if ( *((_DWORD *)v14 + 34) )
    {
LABEL_152:
      IsClientSKU = -2139619007;
      v25 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_92;
      }
      v41 = 51;
      goto LABEL_98;
    }
  }
  v133 = 0;
  v128 = 0;
  v134 = 0;
  if ( !*((_DWORD *)v14 + 18) )
    goto LABEL_390;
  v54 = CoTaskMemAlloc(120LL * *((unsigned int *)v14 + 18));
  *((_QWORD *)v11 + 11) = v54;
  if ( !v54 )
    goto LABEL_158;
  v55 = 0;
  v122 = 0;
  memset_0(v54, 0, 120LL * *((unsigned int *)v14 + 18));
  v56 = 0;
  while ( 2 )
  {
    *(_DWORD *)v121 = v56;
    if ( v56 < *((_DWORD *)v14 + 18) )
    {
      v57 = *((_QWORD *)v14 + 10);
      v58 = v56;
      bstrString[0] = (BSTR)(16LL * v56);
      v59 = (struct _GUID *)((char *)bstrString[0] + v57);
      v60 = *((_QWORD *)v14 + 11);
      v61 = *(_DWORD *)(v60 + 4LL * v56);
      v62 = 0;
      while ( (unsigned int)v62 < v56 )
      {
        if ( BlbutilIsVolumeMatch(
               (struct _GUID *)(v57 + 16LL * (unsigned int)v62),
               *(_DWORD *)(v60 + 4 * v62),
               v59,
               v61) )
        {
          IsClientSKU = -2139619309;
          goto LABEL_11;
        }
        v62 = (unsigned int)(v62 + 1);
        v56 = *(_DWORD *)v121;
      }
      v63 = *(_BYTE *)(v58 + *((_QWORD *)v14 + 12));
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      IsClientSKU = BlbutilQueryVolumeName(v59, v61, (unsigned __int16 **)&pv, 1u);
      if ( IsClientSKU >= 0 )
      {
        v64 = bstrString[0];
        v65 = *(_QWORD *)&v140.Data1;
        VolumeIndexInOldVolumeList = BlbGetVolumeIndexInOldVolumeList(
                                       (struct _GUID *)((char *)bstrString[0] + *((_QWORD *)v14 + 10)),
                                       *(_DWORD *)(*((_QWORD *)v14 + 11) + 4 * v58),
                                       a6,
                                       *(struct _BLBCAT_VOLUME_INFO **)&v140.Data1);
        v67 = 120 * v58;
        if ( VolumeIndexInOldVolumeList == -1 )
        {
          v68 = v61;
          v18 = (unsigned __int16 *)pv;
          IsClientSKU = BlbFillCatalogVolumeInfo(
                          (unsigned __int16 *)pv,
                          v68,
                          v63,
                          (struct _BLBCAT_VOLUME_INFO *)(120 * v58 + *((_QWORD *)a9 + 11)));
          if ( IsClientSKU < 0 )
          {
            if ( v63 )
              goto LABEL_201;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                52,
                (unsigned int)&WPP_f64988f85895305c69b26f06d2565e84_Traceguids,
                (_DWORD)v18,
                IsClientSKU);
            }
            *(_OWORD *)(v67 + *((_QWORD *)a9 + 11)) = *(_OWORD *)((char *)v64 + *((_QWORD *)v14 + 10));
            v69 = 0;
            v11 = a9;
            do
              *(_BYTE *)(v67 + *((_QWORD *)a9 + 11) + v69++ + 40) = 0;
            while ( v69 != 2 );
            goto LABEL_198;
          }
          v11 = a9;
        }
        else
        {
          IsClientSKU = BlbCopyCatalogVolumeInfo(
                          (struct _BLBCAT_VOLUME_INFO *)(v65 + 120LL * VolumeIndexInOldVolumeList),
                          (struct _BLBCAT_VOLUME_INFO *)(120 * v58 + *((_QWORD *)a9 + 11)));
          if ( IsClientSKU < 0 )
            goto LABEL_11;
          v11 = a9;
          *(_BYTE *)(v67 + *((_QWORD *)a9 + 11) + 40) = v63;
          *(_DWORD *)(v67 + *((_QWORD *)a9 + 11) + 16) = v61;
          v18 = (unsigned __int16 *)pv;
        }
        if ( v63 )
        {
          if ( v132 )
          {
            CoTaskMemFree(v132);
            v132 = 0;
          }
          IsClientSKU = BlbutilAppendString(v18, L"\\", &v132);
          if ( IsClientSKU >= 0 )
          {
            if ( (*(_BYTE *)(*((_QWORD *)v14 + 11) + 4 * v58) & 8) == 0 )
            {
LABEL_197:
              v55 = ++v122;
LABEL_199:
              v56 = *(_DWORD *)v121 + 1;
              continue;
            }
            v139 = 0;
            v136 = 0;
            bstrString[0] = 0;
            v70 = v132;
            IsClientSKU = BlbQueryFileSystemSpace(v132, &v139, (unsigned __int64 *)&v136);
            if ( IsClientSKU >= 0 )
            {
              IsClientSKU = BlbQueryExcludedFileSize(v70, (unsigned __int64 *)bstrString);
              if ( IsClientSKU >= 0 )
              {
                if ( v131 )
                {
                  CoTaskMemFree(v131);
                  v131 = 0;
                }
                BlbQueryVolumeAccessPath(v18, &v131);
                v73 = v139;
                v74 = v136;
                v75 = bstrString[0];
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  v76 = (int)v18;
                  if ( v131 )
                    v76 = (int)v131;
                  WPP_SF_SIII(*((_QWORD *)WPP_GLOBAL_Control + 2), v71, v72, v76, v139, (char)v136, (char)bstrString[0]);
                }
                v128 = (struct _BLB_TEMPLATE_SETTINGS *)((char *)v128 + v73);
                v134 += (__int64)v74;
                v133 += (__int64)v75;
                goto LABEL_197;
              }
            }
          }
LABEL_201:
          v17 = a9;
          goto LABEL_13;
        }
LABEL_198:
        v55 = v122;
        goto LABEL_199;
      }
      goto LABEL_11;
    }
    break;
  }
  v13 = pv;
  if ( !v55 )
  {
LABEL_390:
    if ( !*((_DWORD *)v14 + 34) )
    {
      IsClientSKU = -2139618958;
      goto LABEL_11;
    }
  }
  IsClientSKU = BlbFillCriticalVolumesInfo<_BLBCAT_VOLUME_INFO>(*((_QWORD *)v11 + 11), *((unsigned int *)v11 + 20));
  if ( IsClientSKU < 0 )
    goto LABEL_11;
  if ( *((_BYTE *)v14 + 108) )
  {
    if ( !memcmp_0(&g_guidSystemVolumeId, &GUID_NULL, 0x10u) && (g_dwSystemVolumeFlags & 1) == 0 )
    {
      IsClientSKU = -2139618968;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_f64988f85895305c69b26f06d2565e84_Traceguids);
      }
      goto LABEL_92;
    }
    goto LABEL_214;
  }
  if ( !*((_BYTE *)v14 + 116) )
  {
LABEL_245:
    for ( n = 0; n < *(_DWORD *)v119; ++n )
    {
      v85 = (const struct _GUID *)((char *)v125 + 128 * (unsigned __int64)n);
      if ( LOBYTE(v85[5].Data2) && (v85[5].Data4[0] & 1) == 0 )
      {
        bstrString[0] = 0;
        IsClientSKU = BlbutilMemalloc((void **)bstrString, 1u, 0x20u);
        if ( IsClientSKU < 0 )
          goto LABEL_11;
        v140 = *v85;
        v86 = (struct _BLB_VOLUME_VHD_INFO *)bstrString[0];
        VolumeVHDInfo = CBlbVhdHelper::GetVolumeVHDInfo(&v140, (struct _BLB_VOLUME_VHD_INFO *)bstrString[0]);
        v88 = VolumeVHDInfo;
        if ( VolumeVHDInfo >= 0 )
        {
          *(_QWORD *)ATL::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>::operator[](
                       v142,
                       v85) = v86;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v89 = (unsigned int)BlbGuidStr::BlbGuidStr((BlbGuidStr *)v143, v85);
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              58,
              (unsigned int)&WPP_f64988f85895305c69b26f06d2565e84_Traceguids,
              v89,
              v88);
          }
          FreeVolumeVHDInfo(v86);
          if ( v86 )
            CoTaskMemFree(v86);
        }
      }
    }
    StartPosition = ATL::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>::GetStartPosition(v142);
    *(_QWORD *)v121 = StartPosition;
    while ( StartPosition )
    {
      Next = ATL::CAtlMap<unsigned long,_GUID,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<_GUID>>::GetNext(
               v142,
               v121);
      *(_OWORD *)bstrString = *(_OWORD *)Next;
      v92 = *(_QWORD *)(Next + 16);
      if ( *(_BYTE *)v92
        && (unsigned __int8)ATL::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>::Lookup(
                              v142,
                              v92 + 4,
                              &v140) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v93 = BlbGuidStr::BlbGuidStr((BlbGuidStr *)v143, (const struct _GUID *)(v92 + 4));
          v94 = (unsigned int)BlbGuidStr::BlbGuidStr((BlbGuidStr *)v144, (const struct _GUID *)bstrString);
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            (unsigned int)&WPP_f64988f85895305c69b26f06d2565e84_Traceguids,
            v94,
            (__int64)v93);
        }
        IsClientSKU = -2139618983;
        goto LABEL_92;
      }
      StartPosition = *(_QWORD *)v121;
    }
    if ( !*((_DWORD *)v14 + 6) )
    {
      IsClientSKU = -2139619234;
      goto LABEL_11;
    }
    if ( (BlbutilGetBackupFeatures(*((unsigned int *)v14 + 2)) & 0x100) == 0 && *((_DWORD *)v14 + 6) > 1u )
    {
      IsClientSKU = -2139619232;
      goto LABEL_11;
    }
    *((_DWORD *)v11 + 10) = *((_DWORD *)v14 + 6);
    if ( !*((_QWORD *)v14 + 4) )
    {
      IsClientSKU = -2147467261;
      goto LABEL_11;
    }
    v95 = CoTaskMemAlloc(40LL * *((unsigned int *)v14 + 6));
    *((_QWORD *)v11 + 6) = v95;
    if ( !v95 )
    {
LABEL_158:
      IsClientSKU = -2147024882;
      goto LABEL_11;
    }
    memset_0(v95, 0, 40LL * *((unsigned int *)v14 + 6));
    if ( *((_DWORD *)v14 + 2) == 4 )
    {
      v96 = v138;
      IsClientSKU = CBlbImpersonationHelper::ImpersonateCaller(v138, 1);
      if ( IsClientSKU < 0 )
        goto LABEL_11;
      v118[0] = 0;
      VolumeMediaType = BlbutilCheckNetworkShare(*((const unsigned __int16 **)v14 + 2), 1u, v118);
      IsClientSKU = VolumeMediaType;
      if ( VolumeMediaType < 0 )
      {
        v98 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_92;
        }
        v99 = 60;
        v100 = *((_QWORD *)v14 + 2);
        goto LABEL_284;
      }
      CBlbImpersonationHelper::Revert(v96);
      if ( !v118[0] )
        goto LABEL_10;
      if ( *((_DWORD *)v14 + 6) != 1 )
        BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbcatalogutils.cpp", 0x5BEu, "pTemplate->m_cTarget == 1");
      IsClientSKU = BlbutilDuplicateString(**((const unsigned __int16 ***)v14 + 4), *((unsigned __int16 ***)v11 + 6), 0);
      if ( IsClientSKU < 0
        || (IsClientSKU = BlbutilDuplicateString(
                            *(const unsigned __int16 **)(*((_QWORD *)v14 + 4) + 8LL),
                            (unsigned __int16 **)(*((_QWORD *)v11 + 6) + 8LL),
                            0),
            IsClientSKU < 0)
        || (*(_QWORD *)(*((_QWORD *)v11 + 6) + 16LL) = 0,
            *(_WORD *)(*((_QWORD *)v11 + 6) + 24LL) = 0,
            *(_QWORD *)(*((_QWORD *)v11 + 6) + 32LL) = 0,
            IsClientSKU = BlbutilDuplicateString(*((const unsigned __int16 **)v14 + 5), (unsigned __int16 **)v11 + 7, 0),
            IsClientSKU < 0)
        || (IsClientSKU = BlbutilDuplicateString(*((const unsigned __int16 **)v14 + 6), (unsigned __int16 **)v11 + 8, 0),
            IsClientSKU < 0) )
      {
LABEL_11:
        v17 = a9;
LABEL_12:
        v18 = (unsigned __int16 *)pv;
        goto LABEL_13;
      }
      IsClientSKU = BlbValidateTargetFreeSpace(v135, v101, v96, v14, *((_QWORD *)v14 + 2));
      if ( IsClientSKU < 0 )
      {
        v25 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_92;
        }
        v41 = 61;
        goto LABEL_98;
      }
LABEL_366:
      v123 = 1;
      IsClientSKU = CBlbEngine::GetBackupSetInfo<_BLB_VOLUME_INFO>(
                      v124,
                      (__int64)v127,
                      *(unsigned int *)v119,
                      (__int64)v125,
                      &v123);
      if ( IsClientSKU < 0 )
      {
        v25 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_92;
        }
        v41 = 68;
        goto LABEL_98;
      }
      *((_DWORD *)v11 + 6) = v123;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_f64988f85895305c69b26f06d2565e84_Traceguids);
      }
      if ( (BlbutilGetBackupFeatures(*((unsigned int *)v14 + 2)) & 0x10) == 0
        && (*((_BYTE *)v14 + 104) || *((_BYTE *)v14 + 105)) )
      {
        IsClientSKU = -2139619273;
        goto LABEL_11;
      }
      *((_WORD *)v11 + 48) = *((_WORD *)v14 + 52);
      *((_BYTE *)v11 + 98) = v120[0];
      IsClientSKU = BlbutilGetComputerName((unsigned __int16 **)v11 + 13);
      if ( IsClientSKU < 0 )
        goto LABEL_11;
      BlbutilGetProcessorArchitecture((unsigned __int16 *)v11 + 56);
      *((_BYTE *)v11 + 114) = *((_BYTE *)v14 + 106);
      v114 = (void *)*((_QWORD *)v11 + 16);
      if ( v114 )
      {
        CoTaskMemFree(v114);
        *((_QWORD *)v11 + 16) = 0;
      }
      v19 = v116;
      IsClientSKU = CBlbBackupItemsHelper::Initialize(
                      v116,
                      *(unsigned int *)v119,
                      v125,
                      *((_DWORD *)v14 + 34),
                      *((struct _BLB_COMPONENT **)v14 + 18),
                      *((_BYTE *)v14 + 116),
                      *((_BYTE *)v14 + 108));
      if ( IsClientSKU >= 0 )
      {
        IsClientSKU = CBlbBackupItemsHelper::GetBackupSpecsXML(v19, (unsigned __int16 **)v11 + 16);
        v17 = a9;
        v18 = (unsigned __int16 *)pv;
        if ( IsClientSKU >= 0 )
          *((_BYTE *)v11 + 121) = *((_DWORD *)v14 + 34) != 0;
        goto LABEL_14;
      }
LABEL_387:
      v17 = a9;
      v18 = (unsigned __int16 *)pv;
      goto LABEL_14;
    }
    if ( BlbGetTargetIndexInOldTargetList(*((wchar_t **)v14 + 2), v123, (struct _BLBCAT_TARGET_INFO *)v137) == -1 )
    {
      IsClientSKU = BlbutilAppendString(*((const unsigned __int16 **)v14 + 2), L"\\", &v129);
      if ( IsClientSKU < 0 )
        goto LABEL_11;
      v102 = (int)v129;
      VolumeMediaType = BlbQueryVolumeMediaType(v129, (enum _BLB_MEDIA_TYPE *)&v126);
      IsClientSKU = VolumeMediaType;
      if ( VolumeMediaType < 0 )
      {
        v98 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_92;
        }
        v99 = 62;
        LODWORD(v100) = v102;
LABEL_284:
        WPP_SF_Sd(v98[2], v99, (unsigned int)&WPP_f64988f85895305c69b26f06d2565e84_Traceguids, v100, VolumeMediaType);
        goto LABEL_92;
      }
      if ( v126 != *((_DWORD *)v14 + 2) )
      {
        IsClientSKU = -2139619311;
        goto LABEL_11;
      }
    }
    v103 = 0;
    IsSSBToAnyVolumeAllowed = 0;
    if ( *((_BYTE *)v14 + 116) && !*((_DWORD *)v14 + 30) && !*((_BYTE *)v14 + 108) )
      IsSSBToAnyVolumeAllowed = BlbIsSSBToAnyVolumeAllowed();
    for ( ii = 0; ii < *((_DWORD *)v14 + 6); ++ii )
    {
      for ( jj = 0; jj < ii; ++jj )
      {
        if ( !_wcsicmp(
                *(const wchar_t **)(*((_QWORD *)v14 + 4) + 24LL * jj),
                *(const wchar_t **)(*((_QWORD *)v14 + 4) + 24LL * ii)) )
        {
          IsClientSKU = -2139619233;
          goto LABEL_11;
        }
      }
      if ( (int)BlbutilGetVolumeIdFromName(*(unsigned __int16 **)(*((_QWORD *)v14 + 4) + 24LL * ii), &Buf1) < 0 )
        goto LABEL_10;
      v106 = 0;
      v107 = (PVOID *)WPP_GLOBAL_Control;
      while ( (unsigned int)v106 < *((_DWORD *)v14 + 18) )
      {
        if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
        {
          BlbAssert(
            "base\\stor\\blb\\engine\\blbengutils\\blbcatalogutils.cpp",
            0x62Bu,
            "guidTargetVolumeId != GUID_NULL");
          v107 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( *(_BYTE *)(v106 + *((_QWORD *)v14 + 12)) == 1 )
        {
          v108 = (_QWORD *)(*((_QWORD *)v14 + 10) + 16LL * (unsigned int)v106);
          v109 = *(_QWORD *)&Buf1.Data1 - *v108;
          if ( *(_QWORD *)&Buf1.Data1 == *v108 )
            v109 = *(_QWORD *)Buf1.Data4 - v108[1];
          if ( !v109 )
          {
            if ( !IsSSBToAnyVolumeAllowed )
            {
              IsClientSKU = -2139619264;
              goto LABEL_11;
            }
            if ( v107 != &WPP_GLOBAL_Control && (*((_BYTE *)v107 + 28) & 1) != 0 && *((_BYTE *)v107 + 25) >= 4u )
            {
              WPP_SF_(v107[2], 63, &WPP_f64988f85895305c69b26f06d2565e84_Traceguids);
              v107 = (PVOID *)WPP_GLOBAL_Control;
            }
          }
        }
        v106 = (unsigned int)(v106 + 1);
      }
      v110 = v137;
      TargetIndexInOldTargetList = BlbGetTargetIndexInOldTargetList(
                                     *(wchar_t **)(*((_QWORD *)v14 + 4) + 24LL * ii),
                                     v123,
                                     (struct _BLBCAT_TARGET_INFO *)v137);
      if ( TargetIndexInOldTargetList == -1 )
      {
        if ( v129 )
        {
          CoTaskMemFree(v129);
          v129 = 0;
        }
        IsClientSKU = BlbutilAppendString(*(const unsigned __int16 **)(*((_QWORD *)v14 + 4) + 24LL * ii), L"\\", &v129);
        if ( IsClientSKU < 0 )
          goto LABEL_11;
        v112 = v129;
        IsClientSKU = BlbFillCatalogTargetInfo(
                        v129,
                        *(unsigned __int16 **)(*((_QWORD *)v14 + 4) + 24LL * ii + 8),
                        (unsigned __int16 **)(*((_QWORD *)a9 + 6) + 40LL * ii));
        if ( IsClientSKU < 0 )
          goto LABEL_11;
        if ( (unsigned int)(v126 - 2) <= 1 )
        {
          IsClientSKU = BlbIsClusterSharedVolume(v112, v118);
          if ( IsClientSKU < 0 )
          {
            v25 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v41 = 64;
              goto LABEL_98;
            }
            goto LABEL_92;
          }
          v103 |= v118[0];
          if ( !v118[0] )
          {
            IsClientSKU = BlbValidateTargetFreeSpace(v135, v113, v138, v14, v112);
            if ( IsClientSKU < 0 )
            {
              v25 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v41 = 65;
                goto LABEL_98;
              }
              goto LABEL_92;
            }
          }
        }
      }
      else
      {
        v17 = a9;
        IsClientSKU = BlbCopyCatalogTargetInfo(
                        (struct _BLBCAT_TARGET_INFO *)&v110[20 * TargetIndexInOldTargetList],
                        (struct _BLBCAT_TARGET_INFO *)(*((_QWORD *)a9 + 6) + 40LL * ii));
        if ( IsClientSKU < 0 )
          goto LABEL_12;
      }
    }
    if ( v103 )
    {
      if ( *((_BYTE *)v14 + 108) )
      {
        IsClientSKU = -2139618927;
        v25 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v41 = 66;
          goto LABEL_98;
        }
LABEL_92:
        v17 = a9;
        goto LABEL_12;
      }
      v123 = 0;
      IsClientSKU = BlbutilGetTestHookValue(L"CsvSupportSettings", L"CsvTargetSupported", 1u, &v123);
      if ( IsClientSKU < 0 )
        goto LABEL_11;
      if ( !v123 )
      {
        IsClientSKU = -2139618975;
        v25 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v41 = 67;
          goto LABEL_98;
        }
        goto LABEL_92;
      }
    }
    v11 = a9;
    goto LABEL_366;
  }
LABEL_214:
  for ( kk = 0; ; ++kk )
  {
    if ( kk >= *((_DWORD *)v11 + 20) )
      goto LABEL_245;
    IsSSBToAnyVolumeAllowed = 0;
    v78 = 120LL * kk;
    v79 = *((_QWORD *)v11 + 11);
    if ( *(_BYTE *)(v79 + v78 + 40) )
    {
      v80 = *(_DWORD *)(v79 + v78 + 16);
      if ( (v80 & 0x200) != 0 && (v80 & 1) == 0 )
        break;
    }
LABEL_235:
    ;
  }
  if ( v13 )
  {
    CoTaskMemFree(v13);
    pv = 0;
  }
  IsClientSKU = BlbutilQueryVolumeName((struct _GUID *)(v78 + *((_QWORD *)v11 + 11)), v80, (unsigned __int16 **)&pv, 0);
  v18 = (unsigned __int16 *)pv;
  if ( IsClientSKU < 0 )
    goto LABEL_201;
  IsVolumeVirtual = CBlbVhdHelper::IsVolumeVirtual((const unsigned __int16 *)pv, &IsSSBToAnyVolumeAllowed);
  if ( IsVolumeVirtual >= 0 )
  {
    v82 = (PVOID *)WPP_GLOBAL_Control;
    v83 = IsSSBToAnyVolumeAllowed;
  }
  else
  {
    v82 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        (unsigned int)&WPP_f64988f85895305c69b26f06d2565e84_Traceguids,
        (_DWORD)v18,
        IsVolumeVirtual);
      v82 = (PVOID *)WPP_GLOBAL_Control;
    }
    v83 = 0;
    IsSSBToAnyVolumeAllowed = 0;
  }
  if ( !v83 )
  {
LABEL_234:
    v13 = pv;
    goto LABEL_235;
  }
  if ( !*((_BYTE *)v14 + 108) )
  {
    if ( *((_BYTE *)v14 + 116) && (v80 & 2) == 0 && (v80 & 0x400) == 0 )
    {
      IsClientSKU = -2139618982;
      if ( v82 != &WPP_GLOBAL_Control && (*((_BYTE *)v82 + 28) & 1) != 0 && *((_BYTE *)v82 + 25) >= 2u )
        WPP_SF_Sd(
          (unsigned int)v82[2],
          57,
          (unsigned int)&WPP_f64988f85895305c69b26f06d2565e84_Traceguids,
          (_DWORD)v18,
          90);
      goto LABEL_240;
    }
    goto LABEL_234;
  }
  IsClientSKU = -2139618993;
  if ( v82 != &WPP_GLOBAL_Control && (*((_BYTE *)v82 + 28) & 1) != 0 && *((_BYTE *)v82 + 25) >= 2u )
    WPP_SF_Sd((unsigned int)v82[2], 56, (unsigned int)&WPP_f64988f85895305c69b26f06d2565e84_Traceguids, (_DWORD)v18, 79);
LABEL_240:
  v17 = a9;
LABEL_13:
  v19 = v116;
LABEL_14:
  CBlbImpersonationHelper::Revert(v138);
  *(_QWORD *)v121 = ATL::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>::GetStartPosition(v142);
  while ( *(_QWORD *)v121 )
  {
    v21 = *(struct _BLB_VOLUME_VHD_INFO **)(ATL::CAtlMap<unsigned long,_GUID,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<_GUID>>::GetNext(
                                              v142,
                                              v121)
                                          + 16);
    FreeVolumeVHDInfo(v21);
    if ( v21 )
      CoTaskMemFree(v21);
  }
  if ( v18 )
    CoTaskMemFree(v18);
  if ( v131 )
    CoTaskMemFree(v131);
  if ( v129 )
    CoTaskMemFree(v129);
  if ( v132 )
    CoTaskMemFree(v132);
  if ( v127 )
    FreeVolumes(&v127, &v124);
  if ( v125 )
    FreeVolumes(&v125, (unsigned int *)v119);
  if ( v14 )
  {
    FreeTemplateSettings(v14);
    CoTaskMemFree(v14);
  }
  if ( v19 )
    CBlbBackupItemsHelper::`scalar deleting destructor'(v19, v20);
  if ( IsClientSKU < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_f64988f85895305c69b26f06d2565e84_Traceguids);
    }
    BlbCleanupCatalogTemplateInfo(v17);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_f64988f85895305c69b26f06d2565e84_Traceguids);
  }
  ATL::CAtlMap<unsigned long,_GUID,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<_GUID>>::RemoveAll(v142);
  return (unsigned int)IsClientSKU;
}

```

## disassembly

```asm
0x14010e288  mov     [rsp-8+arg_8], rbx
0x14010e28d  push    rbp
0x14010e28e  push    rsi
0x14010e28f  push    rdi
0x14010e290  push    r12
0x14010e292  push    r13
0x14010e294  push    r14
0x14010e296  push    r15
0x14010e298  lea     rbp, [rsp-180h]
0x14010e2a0  sub     rsp, 280h
0x14010e2a7  mov     rax, cs:__security_cookie
0x14010e2ae  xor     rax, rsp
0x14010e2b1  mov     [rbp+1B0h+var_40], rax
0x14010e2b8  mov     [rbp+1B0h+var_21C], r9d
0x14010e2bc  mov     rsi, r8
0x14010e2bf  mov     r15, rdx
0x14010e2c2  mov     [rbp+1B0h+var_1B8], rcx
0x14010e2c6  mov     r13, [rbp+1B0h+arg_40]
0x14010e2cd  mov     [rsp+2B0h+var_250], r13
0x14010e2d2  mov     rax, [rbp+1B0h+arg_20]
0x14010e2d9  mov     [rbp+1B0h+var_1A8], rax
0x14010e2dd  mov     rax, [rbp+1B0h+arg_30]
0x14010e2e4  mov     qword ptr [rbp+1B0h+var_190.Data1], rax
0x14010e2e8  mov     rax, [rbp+1B0h+arg_38]
0x14010e2ef  mov     [rbp+1B0h+var_1A0], rax
0x14010e2f3  xor     ebx, ebx
0x14010e2f5  mov     r14d, ebx
0x14010e2f8  mov     [rbp+1B0h+var_208], ebx
0x14010e2fb  lea     rax, WPP_GLOBAL_Control
0x14010e302  mov     rcx, cs:WPP_GLOBAL_Control
0x14010e309  cmp     rcx, rax
0x14010e30c  jz      short loc_14010E32D
0x14010e30e  test    byte ptr [rcx+1Ch], 1
0x14010e312  jz      short loc_14010E32D
0x14010e314  cmp     byte ptr [rcx+19h], 4
0x14010e318  jb      short loc_14010E32D
0x14010e31a  lea     edx, [rbx+29h]
0x14010e31d  lea     r8, WPP_f64988f85895305c69b26f06d2565e84_Traceguids
0x14010e324  mov     rcx, [rcx+10h]
0x14010e328  call    WPP_SF_
0x14010e32d  mov     [rbp+1B0h+var_1F0], rbx
0x14010e331  mov     [rbp+1B0h+var_1D0], rbx
0x14010e335  xorps   xmm0, xmm0
0x14010e338  movups  [rbp+1B0h+Buf1], xmm0
0x14010e33c  mov     [rbp+1B0h+var_208], ebx
0x14010e33f  mov     r12, rbx
0x14010e342  mov     [rsp+2B0h+pv], rbx
0x14010e347  mov     [rbp+1B0h+var_1D8], rbx
0x14010e34b  mov     [rbp+1B0h+var_200], rbx
0x14010e34f  mov     [rbp+1B0h+var_218], ebx
0x14010e352  mov     [rbp+1B0h+var_210], rbx
0x14010e356  mov     dword ptr [rsp+2B0h+var_234], ebx
0x14010e35a  mov     rdi, rbx
0x14010e35d  mov     [rbp+1B0h+var_1F8], rbx
0x14010e361  mov     [rsp+2B0h+var_240], rbx
0x14010e366  movss   xmm0, cs:__real@40100000
0x14010e36e  movss   dword ptr [rsp+2B0h+lpszFileName], xmm0
0x14010e374  movss   xmm3, cs:__real@3e800000
0x14010e37c  movss   xmm2, cs:__real@3f400000
0x14010e384  lea     rcx, [rbp+1B0h+var_170]
0x14010e388  call    ??0?$CAtlMap@U_GUID@@PEAU_BLB_VOLUME_VHD_INFO@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAU_BLB_VOLUME_VHD_INFO@@@4@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>(uint,float,float,float,uint)
0x14010e38d  nop
0x14010e38e  mov     [rsp+2B0h+var_237], bl
0x14010e392  mov     [rbp+1B0h+var_230], bl
0x14010e395  lea     rcx, [rbp+1B0h+var_230]; unsigned __int8 *
0x14010e399  call    ?BlbutilIsClientSKU@@YAJPEAE@Z; BlbutilIsClientSKU(uchar *)
0x14010e39e  mov     ebx, eax
0x14010e3a0  test    eax, eax
0x14010e3a2  js      loc_14010E439
0x14010e3a8  mov     rcx, r13; struct _BLBCAT_TEMPLATE_INFO *
0x14010e3ab  call    ?BlbCleanupCatalogTemplateInfo@@YAXPEAU_BLBCAT_TEMPLATE_INFO@@@Z; BlbCleanupCatalogTemplateInfo(_BLBCAT_TEMPLATE_INFO *)
0x14010e3b0  movups  xmm0, xmmword ptr [r15]
0x14010e3b4  movdqu  xmmword ptr [r13+0], xmm0
0x14010e3ba  mov     edx, 1; unsigned int
0x14010e3bf  mov     r8d, 0A8h; unsigned int
0x14010e3c5  lea     rcx, [rbp+1B0h+var_1F8]; void **
0x14010e3c9  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14010e3ce  mov     ebx, eax
0x14010e3d0  mov     rdi, [rbp+1B0h+var_1F8]
0x14010e3d4  test    eax, eax
0x14010e3d6  js      short loc_14010E439
0x14010e3d8  mov     rdx, rdi; struct _BLB_TEMPLATE_SETTINGS *
0x14010e3db  mov     rcx, rsi; struct _BLB_TEMPLATE_SETTINGS *
0x14010e3de  call    ?CopyTemplateSettings@@YAJAEAU_BLB_TEMPLATE_SETTINGS@@0@Z; CopyTemplateSettings(_BLB_TEMPLATE_SETTINGS &,_BLB_TEMPLATE_SETTINGS &)
0x14010e3e3  mov     ebx, eax
0x14010e3e5  test    eax, eax
0x14010e3e7  js      short loc_14010E439
0x14010e3e9  lea     rdx, [r13+10h]; unsigned __int16 **
0x14010e3ed  xor     r8d, r8d; unsigned __int64
0x14010e3f0  mov     rcx, [rdi]; unsigned __int16 *
0x14010e3f3  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14010e3f8  mov     ebx, eax
0x14010e3fa  test    eax, eax
0x14010e3fc  js      short loc_14010E439
0x14010e3fe  mov     eax, [rdi+8]
0x14010e401  mov     [r13+1Ch], eax
0x14010e405  mov     al, [rdi+6Bh]
0x14010e408  mov     [r13+73h], al
0x14010e40c  mov     eax, [rdi+70h]
0x14010e40f  mov     [r13+74h], eax
0x14010e413  mov     al, [rdi+74h]
0x14010e416  mov     [r13+78h], al
0x14010e41a  mov     eax, [rdi+0A0h]
0x14010e420  mov     [r13+88h], eax
0x14010e427  mov     rcx, [rdi+10h]; unsigned __int16 *
0x14010e42b  test    rcx, rcx
0x14010e42e  jnz     loc_14010E5C4
0x14010e434  mov     ebx, 8078000Ch
0x14010e439  mov     r14, [rsp+2B0h+var_250]
0x14010e43e  lea     r13, WPP_GLOBAL_Control
0x14010e445  mov     r15, [rsp+2B0h+pv]
0x14010e44a  mov     r12, [rsp+2B0h+var_240]
0x14010e44f  mov     rcx, [rbp+1B0h+var_1A0]; this
0x14010e453  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x14010e458  lea     rcx, [rbp+1B0h+var_170]
0x14010e45c  call    ?GetStartPosition@?$CAtlMap@U_GUID@@PEAU_BLB_VOLUME_VHD_INFO@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAU_BLB_VOLUME_VHD_INFO@@@4@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<_GUID,_BLB_VOLUME_VHD_INFO *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<_BLB_VOLUME_VHD_INFO *>>::GetStartPosition(void)
0x14010e461  mov     qword ptr [rbp+1B0h+var_228], rax
0x14010e465  test    rax, rax
0x14010e468  jz      short loc_14010E498
0x14010e46a  lea     rdx, [rbp+1B0h+var_228]
0x14010e46e  lea     rcx, [rbp+1B0h+var_170]
0x14010e472  call    ?GetNext@?$CAtlMap@KU_GUID@@V?$CElementTraits@K@ATL@@V?$CElementTraits@U_GUID@@@3@@ATL@@QEAAPEAVCPair@12@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ulong,_GUID,ATL::CElementTraits<ulong>,ATL::CElementTraits<_GUID>>::GetNext(__POSITION * &)
0x14010e477  mov     rsi, [rax+10h]
0x14010e47b  mov     rcx, rsi; struct _BLB_VOLUME_VHD_INFO *
0x14010e47e  call    ?FreeVolumeVHDInfo@@YAXAEAU_BLB_VOLUME_VHD_INFO@@@Z; FreeVolumeVHDInfo(_BLB_VOLUME_VHD_INFO &)
0x14010e483  test    rsi, rsi
0x14010e486  jz      short loc_14010E491
0x14010e488  mov     rcx, rsi; pv
0x14010e48b  call    cs:__imp_CoTaskMemFree
0x14010e491  cmp     qword ptr [rbp+1B0h+var_228], 0
0x14010e496  jnz     short loc_14010E46A
0x14010e498  test    r15, r15
0x14010e49b  jz      short loc_14010E4A6
0x14010e49d  mov     rcx, r15; pv
0x14010e4a0  call    cs:__imp_CoTaskMemFree
0x14010e4a6  mov     rax, [rbp+1B0h+var_1D8]
0x14010e4aa  test    rax, rax
0x14010e4ad  jz      short loc_14010E4B8
0x14010e4af  mov     rcx, rax; pv
0x14010e4b2  call    cs:__imp_CoTaskMemFree
0x14010e4b8  mov     rcx, [rbp+1B0h+var_1F0]; pv
0x14010e4bc  test    rcx, rcx
0x14010e4bf  jz      short loc_14010E4C7
0x14010e4c1  call    cs:__imp_CoTaskMemFree
0x14010e4c7  mov     rax, [rbp+1B0h+var_1D0]
0x14010e4cb  test    rax, rax
0x14010e4ce  jz      short loc_14010E4D9
0x14010e4d0  mov     rcx, rax; pv
0x14010e4d3  call    cs:__imp_CoTaskMemFree
0x14010e4d9  cmp     [rbp+1B0h+var_200], 0
0x14010e4de  jz      short loc_14010E4ED
0x14010e4e0  lea     rdx, [rbp+1B0h+var_218]; unsigned int *
0x14010e4e4  lea     rcx, [rbp+1B0h+var_200]; struct _BLB_VOLUME_INFO **
0x14010e4e8  call    ?FreeVolumes@@YAXAEAPEAU_BLB_VOLUME_INFO@@AEAK@Z; FreeVolumes(_BLB_VOLUME_INFO * &,ulong &)
0x14010e4ed  cmp     [rbp+1B0h+var_210], 0
0x14010e4f2  jz      short loc_14010E502
0x14010e4f4  lea     rdx, [rsp+2B0h+var_234]; unsigned int *
0x14010e4f9  lea     rcx, [rbp+1B0h+var_210]; struct _BLB_VOLUME_INFO **
0x14010e4fd  call    ?FreeVolumes@@YAXAEAPEAU_BLB_VOLUME_INFO@@AEAK@Z; FreeVolumes(_BLB_VOLUME_INFO * &,ulong &)
0x14010e502  test    rdi, rdi
0x14010e505  jz      short loc_14010E518
0x14010e507  mov     rcx, rdi; struct _BLB_TEMPLATE_SETTINGS *
0x14010e50a  call    ?FreeTemplateSettings@@YAXAEAU_BLB_TEMPLATE_SETTINGS@@@Z; FreeTemplateSettings(_BLB_TEMPLATE_SETTINGS &)
0x14010e50f  mov     rcx, rdi; pv
0x14010e512  call    cs:__imp_CoTaskMemFree
0x14010e518  test    r12, r12
0x14010e51b  jz      short loc_14010E525
0x14010e51d  mov     rcx, r12; this
0x14010e520  call    ??_GCBlbBackupItemsHelper@@QEAAPEAXI@Z; CBlbBackupItemsHelper::`scalar deleting destructor'(uint)
0x14010e525  test    ebx, ebx
0x14010e527  jns     short loc_14010E561
0x14010e529  mov     rcx, cs:WPP_GLOBAL_Control
0x14010e530  cmp     rcx, r13
0x14010e533  jz      short loc_14010E559
0x14010e535  test    byte ptr [rcx+1Ch], 1
0x14010e539  jz      short loc_14010E559
0x14010e53b  cmp     byte ptr [rcx+19h], 2
0x14010e53f  jb      short loc_14010E559
0x14010e541  mov     edx, 46h ; 'F'
0x14010e546  mov     r9d, ebx
0x14010e549  lea     r8, WPP_f64988f85895305c69b26f06d2565e84_Traceguids
0x14010e550  mov     rcx, [rcx+10h]
0x14010e554  call    WPP_SF_d
0x14010e559  mov     rcx, r14; struct _BLBCAT_TEMPLATE_INFO *
0x14010e55c  call    ?BlbCleanupCatalogTemplateInfo@@YAXPEAU_BLBCAT_TEMPLATE_INFO@@@Z; BlbCleanupCatalogTemplateInfo(_BLBCAT_TEMPLATE_INFO *)
0x14010e561  mov     rcx, cs:WPP_GLOBAL_Control
0x14010e568  cmp     rcx, r13
0x14010e56b  jz      short loc_14010E58F
0x14010e56d  test    byte ptr [rcx+1Ch], 1
0x14010e571  jz      short loc_14010E58F
0x14010e573  cmp     byte ptr [rcx+19h], 4
0x14010e577  jb      short loc_14010E58F
0x14010e579  mov     edx, 47h ; 'G'
0x14010e57e  lea     r8, WPP_f64988f85895305c69b26f06d2565e84_Traceguids
0x14010e585  mov     rcx, [rcx+10h]
0x14010e589  call    WPP_SF_
0x14010e58e  nop
0x14010e58f  lea     rcx, [rbp+1B0h+var_170]
0x14010e593  call    ?RemoveAll@?$CAtlMap@KU_GUID@@V?$CElementTraits@K@ATL@@V?$CElementTraits@U_GUID@@@3@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,_GUID,ATL::CElementTraits<ulong>,ATL::CElementTraits<_GUID>>::RemoveAll(void)
0x14010e598  mov     eax, ebx
0x14010e59a  mov     rcx, [rbp+1B0h+var_40]
0x14010e5a1  xor     rcx, rsp; StackCookie
0x14010e5a4  call    __security_check_cookie
0x14010e5a9  mov     rbx, [rsp+2B0h+arg_8]
0x14010e5b1  add     rsp, 280h
0x14010e5b8  pop     r15
0x14010e5ba  pop     r14
0x14010e5bc  pop     r13
0x14010e5be  pop     r12
0x14010e5c0  pop     rdi
0x14010e5c1  pop     rsi
0x14010e5c2  pop     rbp
0x14010e5c3  retn
0x14010e5c4  lea     rdx, [r13+20h]; unsigned __int16 **
0x14010e5c8  xor     r8d, r8d; unsigned __int64
0x14010e5cb  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14010e5d0  mov     ebx, eax
0x14010e5d2  test    eax, eax
0x14010e5d4  js      loc_14010E439
0x14010e5da  mov     ecx, 20h ; ' '; Size
0x14010e5df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14010e5e4  mov     [rsp+2B0h+var_240], rax
0x14010e5e9  mov     [rbp+1B0h+bstrString], rax
0x14010e5ed  xor     ebx, ebx
0x14010e5ef  test    rax, rax
0x14010e5f2  jz      loc_14010FC41
0x14010e5f8  mov     [rax+8], rbx
0x14010e5fc  mov     [rax], rbx
0x14010e5ff  lea     rsi, [rdi+50h]
0x14010e603  cmp     [rsi], rbx
0x14010e606  jz      loc_14010E990
0x14010e60c  cmp     [rdi+58h], rbx
0x14010e610  jz      loc_14010E990
0x14010e616  cmp     [rdi+60h], rbx
0x14010e61a  jz      loc_14010E990
0x14010e620  mov     rcx, cs:WPP_GLOBAL_Control
0x14010e627  lea     r13, WPP_GLOBAL_Control
0x14010e62e  cmp     rcx, r13
0x14010e631  jz      short loc_14010E65D
0x14010e633  test    byte ptr [rcx+1Ch], 1
0x14010e637  jz      short loc_14010E65D
0x14010e639  cmp     byte ptr [rcx+19h], 4
0x14010e63d  jb      short loc_14010E65D
0x14010e63f  lea     edx, [rbx+2Ah]
0x14010e642  mov     r9d, [rdi+48h]
0x14010e646  lea     r8, WPP_f64988f85895305c69b26f06d2565e84_Traceguids
0x14010e64d  mov     rcx, [rcx+10h]
0x14010e651  call    WPP_SF_d
0x14010e656  mov     rcx, cs:WPP_GLOBAL_Control
0x14010e65d  cmp     [rsi], rbx
0x14010e660  jz      loc_14010E96D
0x14010e666  cmp     [rdi+58h], rbx
0x14010e66a  jz      loc_14010E96D
0x14010e670  cmp     [rdi+60h], rbx
0x14010e674  jz      loc_14010E96D
0x14010e67a  cmp     [rdi+80h], rbx
0x14010e681  jz      short loc_14010E6A2
0x14010e683  lea     r8, aPtemplateMRgfi; "pTemplate->m_rgFileSpecs == NULL"
0x14010e68a  mov     edx, 357h; unsigned int
0x14010e68f  lea     rcx, aBaseStorBlbEng_44; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14010e696  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14010e69b  mov     rcx, cs:WPP_GLOBAL_Control
0x14010e6a2  cmp     [rdi+78h], ebx
0x14010e6a5  jz      short loc_14010E6C6
0x14010e6a7  lea     r8, aPtemplateMCfil; "pTemplate->m_cFileSpecs == 0"
0x14010e6ae  mov     edx, 358h; unsigned int
0x14010e6b3  lea     rcx, aBaseStorBlbEng_44; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14010e6ba  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14010e6bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14010e6c6  cmp     [rdi+80h], rbx
0x14010e6cd  jnz     loc_14010E93A
0x14010e6d3  cmp     [rdi+78h], ebx
0x14010e6d6  jnz     loc_14010E93A
0x14010e6dc  mov     rcx, [rbp+1B0h+var_1B8]
0x14010e6e0  mov     rax, [rcx]
0x14010e6e3  lea     r8, [rbp+1B0h+var_200]
0x14010e6e7  lea     rdx, [rbp+1B0h+var_218]
0x14010e6eb  mov     rax, [rax+40h]
0x14010e6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010e6f4  mov     ebx, eax
0x14010e6f6  test    eax, eax
0x14010e6f8  js      loc_14010E91A
0x14010e6fe  mov     edx, [rdi+48h]; unsigned int
0x14010e701  mov     dword ptr [rsp+2B0h+var_234], edx
0x14010e705  mov     r8d, 80h; unsigned int
0x14010e70b  lea     rcx, [rbp+1B0h+var_210]; void **
0x14010e70f  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14010e714  mov     ebx, eax
0x14010e716  test    eax, eax
0x14010e718  js      loc_14010E91A
0x14010e71e  xor     ecx, ecx
0x14010e720  mov     edx, [rbp+1B0h+var_218]
0x14010e723  mov     [rbp+1B0h+var_220], ecx
0x14010e726  cmp     ecx, [rdi+48h]
0x14010e729  jnb     loc_14010E924
0x14010e72f  xor     r15d, r15d
0x14010e732  cmp     r15d, edx
0x14010e735  jnb     loc_14010E8A8
0x14010e73b  mov     r13d, ecx
0x14010e73e  mov     r8d, ecx
  ... truncated ...
```
