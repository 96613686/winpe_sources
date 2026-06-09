# CBlbEngine::LoadGlobalCatalogFromTarget(ushort *,_GUID,ushort * *,void *,_GUID *,IBLBCatalogSystem * *)

- ea: `0x140048e00`
- end: `0x1400496f7`
- name: `?LoadGlobalCatalogFromTarget@CBlbEngine@@UEAAJPEAGU_GUID@@PEAPEAGPEAXPEAU2@PEAPEAUIBLBCatalogSystem@@@Z`
- size: `2295`
- prototype: `__int64 __fastcall(CBlbEngine *this, unsigned __int16 *, struct _GUID *Buf1, const wchar_t **, void *, struct _GUID *, struct IBLBCatalogSystem **)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140054720`

## callees

- `0x140006a64`
- `0x14000ae38`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000bfd8`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x140048394`
- `0x140048e00`
- `0x1400877b0`
- `0x14008863c`
- `0x1400889f0`
- `0x14009257c`
- `0x1400a0f00`
- `0x1400d6e64`
- `0x1400f007c`
- `0x1400f07dc`
- `0x14010158c`
- `0x140102ec0`
- `0x140103238`
- `0x140103590`
- `0x140103b10`
- `0x140104908`
- `0x1401218b8`
- `0x140134cc6`
- `0x140137010`

## import_xrefs

- `KERNEL32!FindClose` at `0x140048f60`
- `KERNEL32!FindClose` at `0x140048f60`
- `msvcrt!_wcsicmp` at `0x140049128`
- `msvcrt!_wcsicmp` at `0x140049128`
- `ole32!CoTaskMemFree` at `0x140048f22`
- `ole32!CoTaskMemFree` at `0x140048f34`
- `ole32!CoTaskMemFree` at `0x140048f43`
- `ole32!CoTaskMemFree` at `0x140048f51`
- `ole32!CoTaskMemFree` at `0x140048f92`
- `ole32!CoTaskMemFree` at `0x140049592`
- `ole32!CoTaskMemFree` at `0x140048f22`
- `ole32!CoTaskMemFree` at `0x140048f34`
- `ole32!CoTaskMemFree` at `0x140048f43`
- `ole32!CoTaskMemFree` at `0x140048f51`
- `ole32!CoTaskMemFree` at `0x140048f92`
- `ole32!CoTaskMemFree` at `0x140049592`

## pseudocode

```c
__int64 __fastcall CBlbEngine::LoadGlobalCatalogFromTarget(
        CBlbEngine *this,
        unsigned __int16 *a2,
        struct _GUID *Buf1,
        const wchar_t **a4,
        void *a5,
        struct _GUID *a6,
        struct IBLBCatalogSystem **a7)
{
  unsigned int v11; // esi
  unsigned __int16 *v12; // r14
  unsigned __int16 *v13; // r12
  int IsInitialized; // ebx
  struct IBLBCatalogSystem *v15; // rsi
  HANDLE v16; // r15
  unsigned __int64 v17; // rsi
  unsigned __int64 i; // rdi
  LPVOID *v19; // rax
  PVOID *v20; // rcx
  GUID *v22; // rax
  unsigned __int64 v23; // rdx
  unsigned int v24; // ebx
  __int64 v25; // rax
  unsigned __int64 v26; // r14
  const wchar_t **v27; // rax
  const unsigned __int16 *v28; // rcx
  const unsigned __int16 **v29; // rax
  const unsigned __int16 **v30; // rax
  unsigned __int16 **p_pv; // rdx
  int BackupRootDirectory; // eax
  unsigned __int16 *v33; // rdi
  int VolumeMediaType; // eax
  _QWORD *v35; // rcx
  int v36; // edx
  int v37; // r9d
  char BackupFeatures; // al
  char v39; // di
  int v40; // eax
  PVOID *v41; // rcx
  int FirstLocalCatalogInTarget; // eax
  PVOID *v43; // rcx
  char v44; // di
  int v45; // eax
  int NextLocalCatalogInTarget; // eax
  struct _GUID v47; // xmm0
  HANDLE hFindFile; // [rsp+30h] [rbp-A1h] BYREF
  struct IBLBCatalogSystem *v49; // [rsp+38h] [rbp-99h]
  unsigned __int16 *v50; // [rsp+40h] [rbp-91h] BYREF
  int v51; // [rsp+48h] [rbp-89h] BYREF
  __int64 v52; // [rsp+50h] [rbp-81h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-79h] BYREF
  struct IBLBCatalogSystem *v54; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int16 *v55; // [rsp+68h] [rbp-69h] BYREF
  wchar_t *String2; // [rsp+70h] [rbp-61h] BYREF
  __int64 v57; // [rsp+78h] [rbp-59h] BYREF
  unsigned __int64 v58; // [rsp+80h] [rbp-51h]
  __int64 v59; // [rsp+88h] [rbp-49h]
  int v60; // [rsp+90h] [rbp-41h]
  _QWORD v61[2]; // [rsp+98h] [rbp-39h] BYREF
  int v62; // [rsp+A8h] [rbp-29h]
  __int64 v63; // [rsp+B0h] [rbp-21h] BYREF
  struct _GUID Buf2[5]; // [rsp+B8h] [rbp-19h] BYREF
  unsigned __int8 v65; // [rsp+128h] [rbp+57h] BYREF

  v61[0] = a5;
  String2 = 0;
  v63 = 0;
  hFindFile = (HANDLE)-1LL;
  v61[1] = -1;
  Buf2[0] = GUID_NULL;
  v65 = 0;
  v11 = 0;
  v51 = 0;
  v12 = 0;
  v49 = 0;
  v13 = 0;
  v54 = 0;
  v50 = 0;
  v52 = 0;
  v55 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  pv = 0;
  v62 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
  }
  if ( !a2 || !a7 || (v22 = a6) == 0 || !a4 )
  {
    IsInitialized = -2147467261;
LABEL_7:
    v15 = v49;
LABEL_8:
    v16 = hFindFile;
    goto LABEL_9;
  }
  *a7 = 0;
  *v22 = GUID_NULL;
  IsInitialized = CBlbEngine::IsInitialized(this);
  if ( IsInitialized < 0 )
    goto LABEL_7;
  IsInitialized = CBlbImpersonationHelper::ImpersonateCaller((CBlbImpersonationHelper *)v61, 1);
  if ( IsInitialized < 0 )
    goto LABEL_7;
  IsInitialized = BlbutilCheckNetworkShare(a2, 0, &v65);
  if ( IsInitialized < 0 )
    goto LABEL_7;
  if ( v65 )
  {
    v11 = 4;
    v51 = 4;
  }
  else
  {
    CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)v61);
  }
  IsInitialized = BlbFindAllBackupMachineNames(a2);
  if ( IsInitialized < 0 )
    goto LABEL_7;
  v23 = v58;
  if ( *a4 )
  {
    v24 = 0;
    if ( v58 )
    {
      v25 = 0;
      v26 = v58;
      do
      {
        v27 = (const wchar_t **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                  &v57,
                                  v25);
        if ( !_wcsicmp(*a4, *v27) )
          break;
        v25 = ++v24;
      }
      while ( v24 < v26 );
      v12 = v50;
      v23 = v58;
    }
    if ( v24 == v23 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          119,
          (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
          (unsigned int)*a4,
          (__int64)a2);
      }
      IsInitialized = -2139619175;
      goto LABEL_7;
    }
  }
  v28 = *a4;
  if ( *a4 )
  {
    p_pv = (unsigned __int16 **)&pv;
  }
  else
  {
    if ( v23 > 1 )
    {
      IsInitialized = -2139619206;
      goto LABEL_7;
    }
    if ( !v23 )
    {
LABEL_68:
      IsInitialized = -2147024894;
      goto LABEL_7;
    }
    v29 = (const unsigned __int16 **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                       &v57,
                                       0);
    IsInitialized = BlbutilDuplicateString(*v29, (unsigned __int16 **)&pv, 0);
    if ( IsInitialized < 0 )
      goto LABEL_7;
    v30 = (const unsigned __int16 **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                       &v57,
                                       0);
    p_pv = (unsigned __int16 **)a4;
    v28 = *v30;
  }
  IsInitialized = BlbutilDuplicateString(v28, p_pv, 0);
  if ( IsInitialized < 0 )
    goto LABEL_7;
  BackupRootDirectory = BlbFindBackupRootDirectory(a2, (unsigned __int16 *)pv, &v55);
  v13 = v55;
  IsInitialized = BackupRootDirectory;
  if ( BackupRootDirectory < 0 )
    goto LABEL_7;
  if ( !v55 )
    goto LABEL_68;
  IsInitialized = BlbutilAppendString(a2, L"\\", &String2);
  if ( IsInitialized < 0 )
    goto LABEL_7;
  if ( v11 != 4 )
  {
    v33 = String2;
    IsInitialized = BlbIsVolumeNameValid(String2, 0, &v65);
    if ( IsInitialized < 0 )
      goto LABEL_7;
    if ( !v65 )
    {
      IsInitialized = -2139619316;
      goto LABEL_7;
    }
    VolumeMediaType = BlbQueryVolumeMediaType(v33, (enum _BLB_MEDIA_TYPE *)&v51);
    IsInitialized = VolumeMediaType;
    if ( VolumeMediaType < 0 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_86;
      }
      v36 = 120;
      v37 = (int)v33;
LABEL_85:
      WPP_SF_Sd(v35[2], v36, (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids, v37, VolumeMediaType);
LABEL_86:
      v15 = v49;
LABEL_87:
      v16 = hFindFile;
      goto LABEL_9;
    }
    v11 = v51;
  }
  VolumeMediaType = BlbGetMediaIdInTarget(v13, Buf2);
  IsInitialized = VolumeMediaType;
  if ( VolumeMediaType < 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_86;
    }
    v36 = 121;
    v37 = (int)v13;
    goto LABEL_85;
  }
  if ( !memcmp_0(Buf1, Buf2, 0x10u) )
  {
    IsInitialized = 7864323;
    goto LABEL_7;
  }
  IsInitialized = CreateCatalogSystem(&v54);
  if ( IsInitialized < 0 )
  {
    v15 = v54;
    goto LABEL_8;
  }
  BackupFeatures = BlbutilGetBackupFeatures(v11);
  v15 = v54;
  v39 = BackupFeatures;
  v40 = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, unsigned __int16 *, __int64, __int64 *))(*(_QWORD *)v54 + 168LL))(
          v54,
          v13,
          1,
          &v63);
  IsInitialized = v40;
  if ( v40 < 0 )
  {
    if ( v40 == -2139619327 && (int)PublishLocalCatalogFailureEvent(a2) < 0 )
    {
      v41 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_105:
        if ( v41 != &WPP_GLOBAL_Control && (*((_BYTE *)v41 + 28) & 1) != 0 && *((_BYTE *)v41 + 25) >= 2u )
          WPP_SF_Sd(
            (unsigned int)v41[2],
            123,
            (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
            (_DWORD)v13,
            IsInitialized);
        goto LABEL_87;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    v41 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_105;
  }
  if ( (v39 & 1) != 0 )
  {
    FirstLocalCatalogInTarget = BlbFindFirstLocalCatalogInTarget(v13, &v50, &hFindFile);
    v16 = hFindFile;
    IsInitialized = FirstLocalCatalogInTarget;
    if ( FirstLocalCatalogInTarget >= 0 )
    {
      v43 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_124;
    }
    if ( FirstLocalCatalogInTarget == -2147024894 )
    {
      if ( hFindFile != (HANDLE)-1LL )
      {
        v43 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids, v13);
          v43 = (PVOID *)WPP_GLOBAL_Control;
        }
        IsInitialized = 0;
LABEL_124:
        v44 = 0;
LABEL_125:
        v12 = v50;
        while ( 1 )
        {
          while ( 1 )
          {
            if ( v44 )
              goto LABEL_158;
            if ( v12 )
            {
              if ( v43 != &WPP_GLOBAL_Control && (*((_BYTE *)v43 + 28) & 1) != 0 && *((_BYTE *)v43 + 25) >= 4u )
                WPP_SF_S(v43[2], 126, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids, v12);
              if ( v52 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 144LL))(v52);
                v52 = 0;
              }
              v45 = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, unsigned __int16 *, __int64 *))(*(_QWORD *)v15 + 144LL))(
                      v15,
                      v12,
                      &v52);
              IsInitialized = v45;
              if ( v45 < 0 )
              {
                if ( v45 == -2139619326
                  && (int)PublishLocalCatalogFailureEvent(a2) < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
                }
                goto LABEL_9;
              }
              IsInitialized = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, __int64))(*(_QWORD *)v15 + 192LL))(
                                v15,
                                v52);
              if ( IsInitialized < 0 )
                goto LABEL_9;
              CoTaskMemFree(v12);
              v50 = 0;
            }
            NextLocalCatalogInTarget = BlbFindNextLocalCatalogInTarget(v13, v16, &v50);
            IsInitialized = NextLocalCatalogInTarget;
            if ( NextLocalCatalogInTarget < 0 )
            {
              if ( NextLocalCatalogInTarget != -2147024894 )
                goto LABEL_122;
              v43 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  128,
                  &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
                  v13);
                v43 = (PVOID *)WPP_GLOBAL_Control;
              }
              IsInitialized = 0;
              goto LABEL_125;
            }
            v12 = v50;
            if ( !v50 )
              break;
LABEL_149:
            v43 = (PVOID *)WPP_GLOBAL_Control;
          }
          v44 = 1;
          v43 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
            goto LABEL_149;
          }
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      }
    }
LABEL_122:
    v12 = v50;
  }
  else
  {
    v16 = hFindFile;
LABEL_158:
    v47 = Buf2[0];
    *a7 = v15;
    v15 = 0;
    *a6 = v47;
  }
LABEL_9:
  CBlbImpersonationHelper::Revert((CBlbImpersonationHelper *)v61);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 144LL))(v52);
  if ( v15 )
    (*(void (__fastcall **)(struct IBLBCatalogSystem *))(*(_QWORD *)v15 + 240LL))(v15);
  if ( v13 )
    CoTaskMemFree(v13);
  if ( pv )
    CoTaskMemFree(pv);
  if ( String2 )
    CoTaskMemFree(String2);
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v16 != (HANDLE)-1LL )
    FindClose(v16);
  v17 = v58;
  for ( i = 0; i < v17; ++i )
  {
    if ( *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                      &v57,
                      i) )
    {
      v19 = (LPVOID *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                        &v57,
                        i);
      CoTaskMemFree(*v19);
    }
  }
  if ( IsInitialized >= 0 )
    goto LABEL_36;
  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v20 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v20 + 28) & 1) == 0 || *((_BYTE *)v20 + 25) < 2u )
      {
LABEL_37:
        if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 4u )
          WPP_SF_(v20[2], 133, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
        goto LABEL_41;
      }
      WPP_SF_d(v20[2], 132, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
LABEL_36:
      v20 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_37;
    }
  }
LABEL_41:
  CBlbImpersonationHelper::~CBlbImpersonationHelper((CBlbImpersonationHelper *)v61);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(&v57);
  return (unsigned int)IsInitialized;
}

```

## disassembly

```asm
0x140048e00  push    rbp
0x140048e02  push    rbx
0x140048e03  push    rsi
0x140048e04  push    rdi
0x140048e05  push    r12
0x140048e07  push    r13
0x140048e09  push    r14
0x140048e0b  push    r15
0x140048e0d  lea     rbp, [rsp-7]
0x140048e12  sub     rsp, 0D8h
0x140048e19  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140048e20  mov     rax, [rbp+3Fh+arg_20]
0x140048e24  mov     r13, rdx
0x140048e27  xor     edx, edx
0x140048e29  mov     [rbp+3Fh+var_78], rax
0x140048e2d  mov     rbx, rcx
0x140048e30  mov     [rbp+3Fh+String2], rdx
0x140048e34  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140048e38  mov     [rbp+3Fh+var_60], rdx
0x140048e3c  mov     [rsp+110h+hFindFile], rcx
0x140048e41  mov     rdi, r9
0x140048e44  mov     [rbp+3Fh+var_70], rcx
0x140048e48  mov     r15, r8
0x140048e4b  movdqu  [rbp+3Fh+Buf2], xmm0
0x140048e50  mov     [rbp+3Fh+arg_8], dl
0x140048e53  mov     esi, edx
0x140048e55  mov     [rsp+110h+var_C8], edx
0x140048e59  mov     r14d, edx
0x140048e5c  mov     [rsp+110h+var_D8], rdx
0x140048e61  mov     r12d, edx
0x140048e64  mov     [rbp+3Fh+var_B0], rdx
0x140048e68  mov     [rsp+110h+var_D0], rdx
0x140048e6d  mov     [rsp+110h+var_C0], rdx
0x140048e72  mov     [rbp+3Fh+var_A8], rdx
0x140048e76  mov     [rbp+3Fh+var_98], rdx
0x140048e7a  mov     [rbp+3Fh+var_90], rdx
0x140048e7e  mov     [rbp+3Fh+var_88], rdx
0x140048e82  mov     [rbp+3Fh+var_80], edx
0x140048e85  mov     [rbp+3Fh+pv], rdx
0x140048e89  mov     [rbp+3Fh+var_68], edx
0x140048e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140048e93  lea     rax, WPP_GLOBAL_Control
0x140048e9a  cmp     rcx, rax
0x140048e9d  jz      short loc_140048EC2
0x140048e9f  test    byte ptr [rcx+1Ch], 1
0x140048ea3  jz      short loc_140048EC2
0x140048ea5  cmp     byte ptr [rcx+19h], 4
0x140048ea9  jb      short loc_140048EC2
0x140048eab  mov     rcx, [rcx+10h]
0x140048eaf  lea     edx, [r12+75h]
0x140048eb4  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x140048ebb  call    WPP_SF_
0x140048ec0  xor     edx, edx
0x140048ec2  test    r13, r13
0x140048ec5  jnz     loc_14004905D
0x140048ecb  mov     ebx, 80004003h
0x140048ed0  mov     rsi, [rsp+110h+var_D8]
0x140048ed5  mov     r15, [rsp+110h+hFindFile]
0x140048eda  lea     r13, WPP_GLOBAL_Control
0x140048ee1  lea     rcx, [rbp+3Fh+var_78]; this
0x140048ee5  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140048eea  mov     rcx, [rsp+110h+var_C0]
0x140048eef  test    rcx, rcx
0x140048ef2  jz      short loc_140048F03
0x140048ef4  mov     rax, [rcx]
0x140048ef7  mov     rax, [rax+90h]
0x140048efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048f03  test    rsi, rsi
0x140048f06  jz      short loc_140048F1A
0x140048f08  mov     rax, [rsi]
0x140048f0b  mov     rcx, rsi
0x140048f0e  mov     rax, [rax+0F0h]
0x140048f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048f1a  test    r12, r12
0x140048f1d  jz      short loc_140048F28
0x140048f1f  mov     rcx, r12; pv
0x140048f22  call    cs:__imp_CoTaskMemFree
0x140048f28  mov     rax, [rbp+3Fh+pv]
0x140048f2c  test    rax, rax
0x140048f2f  jz      short loc_140048F3A
0x140048f31  mov     rcx, rax; pv
0x140048f34  call    cs:__imp_CoTaskMemFree
0x140048f3a  mov     rcx, [rbp+3Fh+String2]; pv
0x140048f3e  test    rcx, rcx
0x140048f41  jz      short loc_140048F49
0x140048f43  call    cs:__imp_CoTaskMemFree
0x140048f49  test    r14, r14
0x140048f4c  jz      short loc_140048F57
0x140048f4e  mov     rcx, r14; pv
0x140048f51  call    cs:__imp_CoTaskMemFree
0x140048f57  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140048f5b  jz      short loc_140048F66
0x140048f5d  mov     rcx, r15; hFindFile
0x140048f60  call    cs:__imp_FindClose
0x140048f66  mov     rsi, [rbp+3Fh+var_90]
0x140048f6a  xor     edi, edi
0x140048f6c  test    rsi, rsi
0x140048f6f  jz      short loc_140048FA0
0x140048f71  mov     rdx, rdi
0x140048f74  lea     rcx, [rbp+3Fh+var_98]
0x140048f78  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140048f7d  cmp     qword ptr [rax], 0
0x140048f81  jz      short loc_140048F98
0x140048f83  mov     rdx, rdi
0x140048f86  lea     rcx, [rbp+3Fh+var_98]
0x140048f8a  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140048f8f  mov     rcx, [rax]; pv
0x140048f92  call    cs:__imp_CoTaskMemFree
0x140048f98  inc     rdi
0x140048f9b  cmp     rdi, rsi
0x140048f9e  jb      short loc_140048F71
0x140048fa0  test    ebx, ebx
0x140048fa2  jns     short loc_140049008
0x140048fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140048fab  cmp     rcx, r13
0x140048fae  jz      loc_140049035
0x140048fb4  test    byte ptr [rcx+1Ch], 1
0x140048fb8  jz      short loc_140048FDF
0x140048fba  cmp     byte ptr [rcx+19h], 2
0x140048fbe  jb      short loc_140048FDF
0x140048fc0  mov     rcx, [rcx+10h]
0x140048fc4  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x140048fcb  mov     edx, 82h
0x140048fd0  mov     r9d, ebx
0x140048fd3  call    WPP_SF_d
0x140048fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140048fdf  cmp     rcx, r13
0x140048fe2  jz      short loc_140049035
0x140048fe4  test    byte ptr [rcx+1Ch], 1
0x140048fe8  jz      short loc_14004900F
0x140048fea  cmp     byte ptr [rcx+19h], 2
0x140048fee  jb      short loc_14004900F
0x140048ff0  mov     rcx, [rcx+10h]
0x140048ff4  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x140048ffb  mov     edx, 84h
0x140049000  mov     r9d, ebx
0x140049003  call    WPP_SF_d
0x140049008  mov     rcx, cs:WPP_GLOBAL_Control
0x14004900f  cmp     rcx, r13
0x140049012  jz      short loc_140049035
0x140049014  test    byte ptr [rcx+1Ch], 1
0x140049018  jz      short loc_140049035
0x14004901a  cmp     byte ptr [rcx+19h], 4
0x14004901e  jb      short loc_140049035
0x140049020  mov     rcx, [rcx+10h]
0x140049024  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004902b  mov     edx, 85h
0x140049030  call    WPP_SF_
0x140049035  lea     rcx, [rbp+3Fh+var_78]; this
0x140049039  call    ??1CBlbImpersonationHelper@@QEAA@XZ; CBlbImpersonationHelper::~CBlbImpersonationHelper(void)
0x14004903e  lea     rcx, [rbp+3Fh+var_98]
0x140049042  call    ??1?$CAtlArray@U_BLB_COMPONENT@@V?$CElementTraits@U_BLB_COMPONENT@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(void)
0x140049047  mov     eax, ebx
0x140049049  add     rsp, 0D8h
0x140049050  pop     r15
0x140049052  pop     r14
0x140049054  pop     r13
0x140049056  pop     r12
0x140049058  pop     rdi
0x140049059  pop     rsi
0x14004905a  pop     rbx
0x14004905b  pop     rbp
0x14004905c  retn
0x14004905d  mov     rcx, [rbp+3Fh+arg_30]
0x140049061  test    rcx, rcx
0x140049064  jz      loc_140048ECB
0x14004906a  mov     rax, [rbp+3Fh+arg_28]
0x14004906e  test    rax, rax
0x140049071  jz      loc_140048ECB
0x140049077  test    rdi, rdi
0x14004907a  jz      loc_140048ECB
0x140049080  mov     [rcx], rdx
0x140049083  mov     rcx, rbx; this
0x140049086  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14004908d  movdqu  xmmword ptr [rax], xmm0
0x140049091  call    ?IsInitialized@CBlbEngine@@QEAAJXZ; CBlbEngine::IsInitialized(void)
0x140049096  mov     ebx, eax
0x140049098  test    eax, eax
0x14004909a  js      loc_140048ED0
0x1400490a0  mov     dl, 1; unsigned __int8
0x1400490a2  lea     rcx, [rbp+3Fh+var_78]; this
0x1400490a6  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x1400490ab  mov     ebx, eax
0x1400490ad  test    eax, eax
0x1400490af  js      loc_140048ED0
0x1400490b5  lea     r8, [rbp+3Fh+arg_8]; unsigned __int8 *
0x1400490b9  xor     edx, edx; unsigned __int8
0x1400490bb  mov     rcx, r13; unsigned __int16 *
0x1400490be  call    ?BlbutilCheckNetworkShare@@YAJPEBGEPEAE@Z; BlbutilCheckNetworkShare(ushort const *,uchar,uchar *)
0x1400490c3  mov     ebx, eax
0x1400490c5  test    eax, eax
0x1400490c7  js      loc_140048ED0
0x1400490cd  cmp     [rbp+3Fh+arg_8], sil
0x1400490d1  jz      short loc_1400490DE
0x1400490d3  mov     esi, 4
0x1400490d8  mov     [rsp+110h+var_C8], esi
0x1400490dc  jmp     short loc_1400490E7
0x1400490de  lea     rcx, [rbp+3Fh+var_78]; this
0x1400490e2  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x1400490e7  lea     rdx, [rbp+3Fh+var_98]
0x1400490eb  mov     rcx, r13; unsigned __int16 *
0x1400490ee  call    ?BlbFindAllBackupMachineNames@@YAJPEAGPEAV?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@@Z; BlbFindAllBackupMachineNames(ushort *,ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>> *)
0x1400490f3  mov     ebx, eax
0x1400490f5  test    eax, eax
0x1400490f7  js      loc_140048ED0
0x1400490fd  mov     rdx, [rbp+3Fh+var_90]
0x140049101  cmp     [rdi], r12
0x140049104  jz      loc_140049191
0x14004910a  xor     ebx, ebx
0x14004910c  test    rdx, rdx
0x14004910f  jz      short loc_140049144
0x140049111  xor     eax, eax
0x140049113  mov     r14, rdx
0x140049116  mov     rdx, rax
0x140049119  lea     rcx, [rbp+3Fh+var_98]
0x14004911d  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140049122  mov     rcx, [rdi]; String1
0x140049125  mov     rdx, [rax]; String2
0x140049128  call    cs:__imp__wcsicmp
0x14004912e  test    eax, eax
0x140049130  jz      short loc_14004913B
0x140049132  inc     ebx
0x140049134  mov     eax, ebx
0x140049136  cmp     rax, r14
0x140049139  jb      short loc_140049116
0x14004913b  mov     r14, [rsp+110h+var_D0]
0x140049140  mov     rdx, [rbp+3Fh+var_90]
0x140049144  mov     eax, ebx
0x140049146  cmp     rax, rdx
0x140049149  jnz     short loc_140049191
0x14004914b  mov     rcx, cs:WPP_GLOBAL_Control
0x140049152  lea     rax, WPP_GLOBAL_Control
0x140049159  cmp     rcx, rax
0x14004915c  jz      short loc_140049187
0x14004915e  test    byte ptr [rcx+1Ch], 1
0x140049162  jz      short loc_140049187
0x140049164  cmp     byte ptr [rcx+19h], 2
0x140049168  jb      short loc_140049187
0x14004916a  mov     r9, [rdi]
0x14004916d  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x140049174  mov     rcx, [rcx+10h]
0x140049178  mov     edx, 77h ; 'w'
0x14004917d  mov     [rsp+110h+var_F0], r13
0x140049182  call    WPP_SF_SS
0x140049187  mov     ebx, 80780099h
0x14004918c  jmp     loc_140048ED0
0x140049191  mov     rcx, [rdi]; unsigned __int16 *
0x140049194  test    rcx, rcx
0x140049197  jnz     short loc_1400491EF
0x140049199  cmp     rdx, 1
0x14004919d  jbe     short loc_1400491A9
0x14004919f  mov     ebx, 8078007Ah
0x1400491a4  jmp     loc_140048ED0
0x1400491a9  test    rdx, rdx
0x1400491ac  jnz     short loc_1400491B8
0x1400491ae  mov     ebx, 80070002h
0x1400491b3  jmp     loc_140048ED0
0x1400491b8  xor     edx, edx
0x1400491ba  lea     rcx, [rbp+3Fh+var_98]
0x1400491be  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400491c3  xor     r8d, r8d; unsigned __int64
0x1400491c6  lea     rdx, [rbp+3Fh+pv]; unsigned __int16 **
0x1400491ca  mov     rcx, [rax]; unsigned __int16 *
0x1400491cd  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400491d2  mov     ebx, eax
0x1400491d4  test    eax, eax
0x1400491d6  js      loc_140048ED0
0x1400491dc  xor     edx, edx
0x1400491de  lea     rcx, [rbp+3Fh+var_98]
0x1400491e2  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400491e7  mov     rdx, rdi
0x1400491ea  mov     rcx, [rax]
0x1400491ed  jmp     short loc_1400491F3
0x1400491ef  lea     rdx, [rbp+3Fh+pv]; unsigned __int16 **
0x1400491f3  xor     r8d, r8d; unsigned __int64
0x1400491f6  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400491fb  mov     ebx, eax
0x1400491fd  test    eax, eax
0x1400491ff  js      loc_140048ED0
0x140049205  mov     rdx, [rbp+3Fh+pv]; unsigned __int16 *
0x140049209  lea     r8, [rbp+3Fh+var_A8]; unsigned __int16 **
0x14004920d  mov     rcx, r13; unsigned __int16 *
0x140049210  call    ?BlbFindBackupRootDirectory@@YAJPEAG0PEAPEAG@Z; BlbFindBackupRootDirectory(ushort *,ushort *,ushort * *)
0x140049215  mov     r12, [rbp+3Fh+var_A8]
0x140049219  mov     ebx, eax
0x14004921b  test    eax, eax
0x14004921d  js      loc_140048ED0
0x140049223  test    r12, r12
0x140049226  jz      short loc_1400491AE
0x140049228  lea     r8, [rbp+3Fh+String2]; unsigned __int16 **
0x14004922c  mov     rcx, r13; unsigned __int16 *
0x14004922f  lea     rdx, asc_14013C090; "\\"
0x140049236  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14004923b  mov     ebx, eax
0x14004923d  test    eax, eax
0x14004923f  js      loc_140048ED0
0x140049245  cmp     esi, 4
0x140049248  jz      loc_1400492DB
0x14004924e  mov     rdi, [rbp+3Fh+String2]
0x140049252  lea     r8, [rbp+3Fh+arg_8]; unsigned __int8 *
  ... truncated ...
```
