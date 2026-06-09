# CBlbBackupAsync::DeleteNonExistingBackupSetsOnTarget(void)

- ea: `0x140021210`
- end: `0x140021aa9`
- name: `?DeleteNonExistingBackupSetsOnTarget@CBlbBackupAsync@@AEAAJXZ`
- size: `2201`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x140006ca8`
- `0x140006d94`
- `0x140007ad3`
- `0x140008ac8`
- `0x14000b25c`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000fe94`
- `0x140014200`
- `0x140014260`
- `0x14001d660`
- `0x140021210`
- `0x1400227f8`
- `0x140028f5c`
- `0x14008bd48`
- `0x140098c04`
- `0x140098dbc`
- `0x1400d70c4`
- `0x1400f007c`
- `0x1400f07dc`
- `0x140101b64`
- `0x140104908`
- `0x140104e8c`
- `0x140134cc6`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140021678`
- `ole32!CoTaskMemFree` at `0x14002168c`
- `ole32!CoTaskMemFree` at `0x1400216a0`
- `ole32!CoTaskMemFree` at `0x1400219e1`
- `ole32!CoTaskMemFree` at `0x140021a12`
- `ole32!CoTaskMemFree` at `0x140021a21`
- `ole32!CoTaskMemFree` at `0x140021a31`
- `ole32!CoTaskMemFree` at `0x140021a3f`
- `ole32!CoTaskMemFree` at `0x140021a51`
- `ole32!CoTaskMemFree` at `0x140021678`
- `ole32!CoTaskMemFree` at `0x14002168c`
- `ole32!CoTaskMemFree` at `0x1400216a0`
- `ole32!CoTaskMemFree` at `0x1400219e1`
- `ole32!CoTaskMemFree` at `0x140021a12`
- `ole32!CoTaskMemFree` at `0x140021a21`
- `ole32!CoTaskMemFree` at `0x140021a31`
- `ole32!CoTaskMemFree` at `0x140021a3f`
- `ole32!CoTaskMemFree` at `0x140021a51`

## string_xrefs

- `0x1400212f5`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400213a2`: `base\stor\blb\engine\service\backup.cpp`
- `0x140021585`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400215ad`: `base\stor\blb\engine\service\backup.cpp`
- `0x14002163a`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400212e9`: `OVERWRITE(m_ulFeatures) || SNAPSHOT(m_ulFeatures)`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::DeleteNonExistingBackupSetsOnTarget(CBlbBackupAsync *this)
{
  unsigned int v2; // r13d
  struct IBLBCatalogSystem *Catalog; // rdi
  char v4; // r12
  unsigned __int16 *v5; // r14
  int v6; // ebx
  int MediaIdInTarget; // eax
  int v8; // eax
  int v9; // eax
  unsigned int v10; // eax
  PVOID *v11; // rcx
  int v12; // r15d
  unsigned int v13; // r12d
  __int64 v14; // r14
  __int64 v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // rax
  int TargetPathForBackupSet; // eax
  unsigned __int8 v21; // r8
  __int64 v22; // rax
  int VolumeFriendlyNameForPublisher; // eax
  int v24; // eax
  CBlbImpersonationHelper *v25; // r14
  CblbCatalogVerifier *v26; // rdi
  _QWORD *v27; // rsi
  unsigned __int64 v28; // r14
  char v30; // [rsp+40h] [rbp-C0h]
  char v31; // [rsp+41h] [rbp-BFh]
  unsigned __int16 *v32; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v33[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v34; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v35; // [rsp+58h] [rbp-A8h] BYREF
  struct _BLBCAT_MEDIA_INFO *v36; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v37; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v38; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v40; // [rsp+80h] [rbp-80h] BYREF
  CblbCatalogVerifier *v41; // [rsp+88h] [rbp-78h]
  unsigned __int8 *v42; // [rsp+90h] [rbp-70h] BYREF
  CBlbImpersonationHelper *v43; // [rsp+98h] [rbp-68h]
  __int128 v44; // [rsp+A0h] [rbp-60h] BYREF
  GUID Buf1; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v46[40]; // [rsp+C0h] [rbp-40h] BYREF
  int v47; // [rsp+E8h] [rbp-18h]
  __int64 v48; // [rsp+F0h] [rbp-10h]

  v2 = 0;
  v35 = 0;
  v37 = 0;
  Catalog = CBlbAsync::GetCatalog((CBlbBackupAsync *)((char *)this + 24));
  memset_0(v46, 0, 0xD0u);
  v4 = 0;
  v30 = 0;
  v34 = 0;
  v5 = 0;
  Buf1 = GUID_NULL;
  v36 = 0;
  pv = 0;
  v40 = 0;
  v38 = 0;
  v32 = 0;
  LODWORD(v41) = 0;
  v33[0] = 0;
  v42 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 631, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  if ( (*((_BYTE *)this + 340) & 0xC) == 0 )
    BlbAssert(
      "base\\stor\\blb\\engine\\service\\backup.cpp",
      0x3B68u,
      "OVERWRITE(m_ulFeatures) || SNAPSHOT(m_ulFeatures)");
  v43 = (CBlbBackupAsync *)((char *)this + 40);
  v6 = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)this + 40), 0);
  if ( v6 < 0 )
    goto LABEL_109;
  MediaIdInTarget = BlbGetMediaIdInTarget(*((unsigned __int16 **)this + 73), &Buf1);
  v6 = MediaIdInTarget;
  if ( MediaIdInTarget < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        632,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        *((_QWORD *)this + 73),
        MediaIdInTarget);
    }
    goto LABEL_109;
  }
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x3B79u, "guidTargetMediaId != GUID_NULL");
  v8 = *((_DWORD *)this + 84);
  if ( v8 == 2 || (v31 = 0, v8 == 3) )
  {
    v31 = 1;
    v9 = BlbutilQueryVolumeUniqueId(*((unsigned __int16 **)this + 43), &v42, v33);
    v6 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          633,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          *((_QWORD *)this + 43),
          v9);
      }
      goto LABEL_109;
    }
    LODWORD(v41) = v33[0];
  }
  CBlbImpersonationHelper::Revert((CBlbBackupAsync *)((char *)this + 40));
  v6 = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, unsigned int *, LPVOID *))(*(_QWORD *)Catalog + 80LL))(
         Catalog,
         &v35,
         &v37);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 634, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
LABEL_28:
    v5 = v32;
    goto LABEL_109;
  }
  v10 = v35;
  if ( !v35 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 635, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    goto LABEL_28;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  v12 = 0;
  *(_DWORD *)v33 = 0;
  v13 = 0;
  while ( v2 < v10 )
  {
    if ( v36 )
    {
      FreeMediaArray(v36, v34);
      v36 = 0;
      v34 = 0;
    }
    v14 = 16LL * v2;
    v15 = *(_QWORD *)Catalog;
    v44 = *(_OWORD *)((char *)v37 + v14);
    v6 = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, __int128 *, unsigned int *, struct _BLBCAT_MEDIA_INFO **))(v15 + 112))(
           Catalog,
           &v44,
           &v34,
           &v36);
    if ( v6 < 0 )
      goto LABEL_107;
    v16 = (_QWORD *)((char *)v36 + 32 * v34 - 32);
    v17 = *v16 - *(_QWORD *)&Buf1.Data1;
    if ( *v16 == *(_QWORD *)&Buf1.Data1 )
      v17 = v16[1] - *(_QWORD *)Buf1.Data4;
    if ( v17 )
      goto LABEL_78;
    if ( v34 != 1 )
      BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x3BB6u, "cMedia == 1");
    if ( v13 && v13 != *((_DWORD *)v36 + 4) )
      BlbAssert(
        "base\\stor\\blb\\engine\\service\\backup.cpp",
        0x3BB8u,
        "eMediaType == BLB_MT_UNDEFINED || eMediaType == rgMediaCat[0].m_eMediaType");
    v13 = *((_DWORD *)v36 + 4);
    if ( v30 )
    {
      FreeBackupSetContents((struct _BLBCAT_BACKUP_SET_INFO *)v46);
      v30 = 0;
    }
    memset_0(v46, 0, 0xD0u);
    LOBYTE(v18) = 1;
    v19 = *(_QWORD *)Catalog;
    v44 = *(_OWORD *)((char *)v37 + v14);
    v6 = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, __int128 *, _BYTE *, __int64))(v19 + 88))(
           Catalog,
           &v44,
           v46,
           v18);
    if ( v6 < 0 )
      goto LABEL_107;
    v30 = 1;
    if ( v31 )
    {
      if ( v47 != 1 )
        BlbAssert("base\\stor\\blb\\engine\\service\\backup.cpp", 0x3BCAu, "bsiCat.m_cTarget == 1");
      if ( !BlbutilCompareUniqueIds(
              *(_WORD *)(v48 + 24),
              *(const unsigned __int8 **)(v48 + 32),
              (unsigned __int16)v41,
              v42) )
        goto LABEL_78;
    }
    ++*(_DWORD *)v33;
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v40 )
    {
      CoTaskMemFree(v40);
      v40 = 0;
    }
    if ( v38 )
    {
      CoTaskMemFree(v38);
      v38 = 0;
    }
    TargetPathForBackupSet = BlbGetTargetPathForBackupSet(
                               *((unsigned __int16 **)this + 43),
                               0,
                               (struct _BLBCAT_BACKUP_SET_INFO *)v46,
                               (CBlbBackupAsync *)((char *)this + 40),
                               (unsigned __int16 **)&pv,
                               &v40,
                               &v38);
    v6 = TargetPathForBackupSet;
    if ( TargetPathForBackupSet == -2139619289 || TargetPathForBackupSet == -2139619271 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 636, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v38);
      }
      if ( (int)CBlbBackupAsync::DeleteSppMetadataFile(this, (struct _GUID *)((char *)v37 + v14), v21) < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 637, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
      }
      v22 = *(_QWORD *)Catalog;
      v44 = *(_OWORD *)((char *)v37 + v14);
      v6 = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, __int128 *))(v22 + 48))(Catalog, &v44);
      if ( v6 < 0 )
        goto LABEL_107;
      ++v12;
      goto LABEL_78;
    }
    if ( TargetPathForBackupSet < 0 )
      goto LABEL_107;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 638, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
LABEL_78:
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = v35;
    ++v2;
  }
  if ( v12 )
  {
    if ( v12 != *(_DWORD *)v33 )
    {
      v5 = v32;
      goto LABEL_90;
    }
    VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(*((_QWORD *)this + 43), v13, &v32);
    v5 = v32;
    v6 = VolumeFriendlyNameForPublisher;
    if ( VolumeFriendlyNameForPublisher < 0 )
      goto LABEL_108;
    v24 = PublishNoBackupAvailableEvent(v32);
    if ( v24 >= 0 )
    {
LABEL_88:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_90;
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          639,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          *((_QWORD *)this + 43),
          v24);
        goto LABEL_88;
      }
LABEL_90:
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 3u )
        WPP_SF_d(v11[2], 640, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    v6 = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *))(*(_QWORD *)Catalog + 216LL))(Catalog);
    if ( v6 < 0 )
      goto LABEL_108;
    v25 = (CBlbBackupAsync *)((char *)this + 40);
    v6 = CBlbImpersonationHelper::ImpersonateCaller((CBlbBackupAsync *)((char *)this + 40), 0);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, _QWORD, bool))(*(_QWORD *)Catalog + 208LL))(
             Catalog,
             *((_QWORD *)this + 71),
             *((_DWORD *)this + 84) != 4);
      if ( *((char *)this + 340) >= 0 || !*((_BYTE *)this + 276) )
        goto LABEL_106;
      v41 = (CblbCatalogVerifier *)operator new(0x20u);
      v26 = v41;
      if ( v41 )
      {
        *((_BYTE *)v41 + 8) = 1;
        *(_QWORD *)v26 = &CblbCatalogVerifier::`vftable';
        *((_QWORD *)v26 + 3) = 0;
        *((_QWORD *)v26 + 2) = 0;
      }
      else
      {
        v26 = 0;
      }
      v6 = CblbCatalogVerifier::Init(v26, *((unsigned __int16 **)this + 71));
      if ( v6 >= 0 )
      {
        v27 = (_QWORD *)((char *)this + 776);
        v28 = v27[1];
        if ( v28 >= v27[2]
          && !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                                 v27,
                                 v28 + 1) )
        {
          ATL::AtlThrowImpl(-2147024882);
        }
        *(_QWORD *)(*v27 + 8 * v28) = v26;
        ++v27[1];
        v25 = v43;
LABEL_106:
        CBlbImpersonationHelper::Revert(v25);
      }
    }
  }
LABEL_107:
  v5 = v32;
LABEL_108:
  v4 = v30;
LABEL_109:
  CBlbImpersonationHelper::Revert(v43);
  if ( v37 )
    CoTaskMemFree(v37);
  if ( v36 )
    FreeMediaArray(v36, v34);
  if ( v4 )
    FreeBackupSetContents((struct _BLBCAT_BACKUP_SET_INFO *)v46);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v40 )
    CoTaskMemFree(v40);
  if ( v38 )
    CoTaskMemFree(v38);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v42 )
    CoTaskMemFree(v42);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 641, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140021210  push    rbp
0x140021212  push    rbx
0x140021213  push    rsi
0x140021214  push    rdi
0x140021215  push    r12
0x140021217  push    r13
0x140021219  push    r14
0x14002121b  push    r15
0x14002121d  lea     rbp, [rsp-0A8h]
0x140021225  sub     rsp, 1A8h
0x14002122c  mov     rax, cs:__security_cookie
0x140021233  xor     rax, rsp
0x140021236  mov     [rbp+0E0h+var_50], rax
0x14002123d  mov     rsi, rcx
0x140021240  add     rcx, 18h; this
0x140021244  call    ?GetCatalog@CBlbAsync@@QEAAPEAUIBLBCatalogSystem@@XZ; CBlbAsync::GetCatalog(void)
0x140021249  xor     r13d, r13d
0x14002124c  lea     rcx, [rbp+0E0h+var_120]; void *
0x140021250  xor     edx, edx; Val
0x140021252  mov     [rsp+1E0h+var_188], r13d
0x140021257  mov     r8d, 0D0h; Size
0x14002125d  mov     [rsp+1E0h+var_178], r13
0x140021262  mov     rdi, rax
0x140021265  call    memset_0
0x14002126a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140021271  mov     r12b, r13b
0x140021274  mov     [rsp+1E0h+var_1A0], r13b
0x140021279  mov     [rsp+1E0h+var_18C], r13d
0x14002127e  mov     r14d, r13d
0x140021281  movdqu  [rbp+0E0h+Buf1], xmm0
0x140021286  mov     [rsp+1E0h+var_180], r13
0x14002128b  mov     [rsp+1E0h+pv], r13
0x140021290  mov     [rbp+0E0h+var_160], r13
0x140021294  mov     [rsp+1E0h+var_170], r13
0x140021299  mov     [rsp+1E0h+var_198], r13
0x14002129e  mov     dword ptr [rbp+0E0h+var_158], r13d
0x1400212a2  mov     [rsp+1E0h+var_190], r13w
0x1400212a8  mov     [rbp+0E0h+var_150], r13
0x1400212ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212b3  lea     r15, WPP_GLOBAL_Control
0x1400212ba  cmp     rcx, r15
0x1400212bd  jz      short loc_1400212E0
0x1400212bf  test    byte ptr [rcx+1Ch], 1
0x1400212c3  jz      short loc_1400212E0
0x1400212c5  cmp     byte ptr [rcx+19h], 4
0x1400212c9  jb      short loc_1400212E0
0x1400212cb  mov     rcx, [rcx+10h]
0x1400212cf  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400212d6  mov     edx, 277h
0x1400212db  call    WPP_SF_
0x1400212e0  test    byte ptr [rsi+154h], 0Ch
0x1400212e7  jnz     short loc_140021301
0x1400212e9  lea     r8, aOverwriteMUlfe_0; "OVERWRITE(m_ulFeatures) || SNAPSHOT(m_u"...
0x1400212f0  mov     edx, 3B68h; unsigned int
0x1400212f5  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400212fc  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140021301  lea     rax, [rsi+28h]
0x140021305  xor     edx, edx; unsigned __int8
0x140021307  mov     rcx, rax; this
0x14002130a  mov     [rbp+0E0h+var_148], rax
0x14002130e  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x140021313  mov     ebx, eax
0x140021315  test    eax, eax
0x140021317  js      loc_1400219CE
0x14002131d  mov     rcx, [rsi+248h]; unsigned __int16 *
0x140021324  lea     rdx, [rbp+0E0h+Buf1]; struct _GUID *
0x140021328  call    ?BlbGetMediaIdInTarget@@YAJPEAGPEAU_GUID@@@Z; BlbGetMediaIdInTarget(ushort *,_GUID *)
0x14002132d  mov     ebx, eax
0x14002132f  test    eax, eax
0x140021331  jns     short loc_14002137C
0x140021333  mov     rcx, cs:WPP_GLOBAL_Control
0x14002133a  cmp     rcx, r15
0x14002133d  jz      loc_1400219CE
0x140021343  test    byte ptr [rcx+1Ch], 1
0x140021347  jz      loc_1400219CE
0x14002134d  cmp     byte ptr [rcx+19h], 2
0x140021351  jb      loc_1400219CE
0x140021357  mov     r9, [rsi+248h]
0x14002135e  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140021365  mov     rcx, [rcx+10h]
0x140021369  mov     edx, 278h
0x14002136e  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x140021372  call    WPP_SF_Sd
0x140021377  jmp     loc_1400219CE
0x14002137c  mov     r8d, 10h; Size
0x140021382  lea     rdx, GUID_NULL; Buf2
0x140021389  lea     rcx, [rbp+0E0h+Buf1]; Buf1
0x14002138d  call    memcmp_0
0x140021392  test    eax, eax
0x140021394  jnz     short loc_1400213AE
0x140021396  lea     r8, aGuidtargetmedi; "guidTargetMediaId != GUID_NULL"
0x14002139d  mov     edx, 3B79h; unsigned int
0x1400213a2  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400213a9  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400213ae  mov     eax, [rsi+150h]
0x1400213b4  cmp     eax, 2
0x1400213b7  jz      short loc_1400213C3
0x1400213b9  mov     [rsp+1E0h+var_19F], r13b
0x1400213be  cmp     eax, 3
0x1400213c1  jnz     short loc_140021434
0x1400213c3  mov     rcx, [rsi+158h]; unsigned __int16 *
0x1400213ca  lea     r8, [rsp+1E0h+var_190]; unsigned __int16 *
0x1400213cf  lea     rdx, [rbp+0E0h+var_150]; unsigned __int8 **
0x1400213d3  mov     [rsp+1E0h+var_19F], 1
0x1400213d8  call    ?BlbutilQueryVolumeUniqueId@@YAJPEAGPEAPEAEAEAG@Z; BlbutilQueryVolumeUniqueId(ushort *,uchar * *,ushort &)
0x1400213dd  mov     ebx, eax
0x1400213df  test    eax, eax
0x1400213e1  jns     short loc_14002142C
0x1400213e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400213ea  cmp     rcx, r15
0x1400213ed  jz      loc_1400219CE
0x1400213f3  test    byte ptr [rcx+1Ch], 1
0x1400213f7  jz      loc_1400219CE
0x1400213fd  cmp     byte ptr [rcx+19h], 2
0x140021401  jb      loc_1400219CE
0x140021407  mov     r9, [rsi+158h]
0x14002140e  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140021415  mov     rcx, [rcx+10h]
0x140021419  mov     edx, 279h
0x14002141e  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x140021422  call    WPP_SF_Sd
0x140021427  jmp     loc_1400219CE
0x14002142c  movzx   eax, [rsp+1E0h+var_190]
0x140021431  mov     dword ptr [rbp+0E0h+var_158], eax
0x140021434  lea     rcx, [rsi+28h]; this
0x140021438  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x14002143d  mov     rax, [rdi]
0x140021440  lea     r8, [rsp+1E0h+var_178]
0x140021445  lea     rdx, [rsp+1E0h+var_188]
0x14002144a  mov     rcx, rdi
0x14002144d  mov     rax, [rax+50h]
0x140021451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021456  mov     ebx, eax
0x140021458  test    eax, eax
0x14002145a  jns     short loc_140021496
0x14002145c  mov     rcx, cs:WPP_GLOBAL_Control
0x140021463  cmp     rcx, r15
0x140021466  jz      short loc_14002148C
0x140021468  test    byte ptr [rcx+1Ch], 1
0x14002146c  jz      short loc_14002148C
0x14002146e  cmp     byte ptr [rcx+19h], 2
0x140021472  jb      short loc_14002148C
0x140021474  mov     rcx, [rcx+10h]
0x140021478  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002147f  mov     edx, 27Ah
0x140021484  mov     r9d, eax
0x140021487  call    WPP_SF_d
0x14002148c  mov     r14, [rsp+1E0h+var_198]
0x140021491  jmp     loc_1400219CE
0x140021496  mov     eax, [rsp+1E0h+var_188]
0x14002149a  test    eax, eax
0x14002149c  jnz     short loc_1400214CD
0x14002149e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400214a5  cmp     rcx, r15
0x1400214a8  jz      short loc_14002148C
0x1400214aa  test    byte ptr [rcx+1Ch], 1
0x1400214ae  jz      short loc_14002148C
0x1400214b0  cmp     byte ptr [rcx+19h], 4
0x1400214b4  jb      short loc_14002148C
0x1400214b6  mov     rcx, [rcx+10h]
0x1400214ba  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400214c1  mov     edx, 27Bh
0x1400214c6  call    WPP_SF_
0x1400214cb  jmp     short loc_14002148C
0x1400214cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400214d4  mov     r15d, r13d
0x1400214d7  mov     dword ptr [rsp+1E0h+var_190], r13d
0x1400214dc  mov     r12d, r13d
0x1400214df  cmp     r13d, eax
0x1400214e2  jnb     loc_1400217FE
0x1400214e8  mov     rcx, [rsp+1E0h+var_180]; pv
0x1400214ed  test    rcx, rcx
0x1400214f0  jz      short loc_14002150C
0x1400214f2  mov     edx, [rsp+1E0h+var_18C]; unsigned int
0x1400214f6  call    ?FreeMediaArray@@YAXPEAU_BLBCAT_MEDIA_INFO@@K@Z; FreeMediaArray(_BLBCAT_MEDIA_INFO *,ulong)
0x1400214fb  mov     [rsp+1E0h+var_180], 0
0x140021504  mov     [rsp+1E0h+var_18C], 0
0x14002150c  mov     rax, [rsp+1E0h+var_178]
0x140021511  lea     r9, [rsp+1E0h+var_180]
0x140021516  mov     r14d, r13d
0x140021519  lea     r8, [rsp+1E0h+var_18C]
0x14002151e  shl     r14, 4
0x140021522  lea     rdx, [rbp+0E0h+var_140]
0x140021526  mov     rcx, rdi
0x140021529  movups  xmm0, xmmword ptr [r14+rax]
0x14002152e  mov     rax, [rdi]
0x140021531  movdqu  [rbp+0E0h+var_140], xmm0
0x140021536  mov     rax, [rax+70h]
0x14002153a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002153f  mov     ebx, eax
0x140021541  test    eax, eax
0x140021543  js      loc_1400219BD
0x140021549  mov     ecx, [rsp+1E0h+var_18C]
0x14002154d  dec     ecx
0x14002154f  shl     rcx, 5
0x140021553  add     rcx, [rsp+1E0h+var_180]
0x140021558  mov     rax, [rcx]
0x14002155b  sub     rax, qword ptr [rbp+0E0h+Buf1]
0x14002155f  jnz     short loc_140021569
0x140021561  mov     rax, [rcx+8]
0x140021565  sub     rax, qword ptr [rbp+0E0h+Buf1+8]
0x140021569  test    rax, rax
0x14002156c  jnz     loc_1400217EB
0x140021572  cmp     [rsp+1E0h+var_18C], 1
0x140021577  jz      short loc_140021591
0x140021579  lea     r8, aCmedia1; "cMedia == 1"
0x140021580  mov     edx, 3BB6h; unsigned int
0x140021585  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14002158c  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140021591  test    r12d, r12d
0x140021594  jz      short loc_1400215B9
0x140021596  mov     rax, [rsp+1E0h+var_180]
0x14002159b  cmp     r12d, [rax+10h]
0x14002159f  jz      short loc_1400215B9
0x1400215a1  lea     r8, aEmediatypeBlbM; "eMediaType == BLB_MT_UNDEFINED || eMedi"...
0x1400215a8  mov     edx, 3BB8h; unsigned int
0x1400215ad  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x1400215b4  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400215b9  cmp     [rsp+1E0h+var_1A0], 0
0x1400215be  mov     rax, [rsp+1E0h+var_180]
0x1400215c3  mov     r12d, [rax+10h]
0x1400215c7  jz      short loc_1400215D8
0x1400215c9  lea     rcx, [rbp+0E0h+var_120]; struct _BLBCAT_BACKUP_SET_INFO *
0x1400215cd  call    ?FreeBackupSetContents@@YAXPEAU_BLBCAT_BACKUP_SET_INFO@@@Z; FreeBackupSetContents(_BLBCAT_BACKUP_SET_INFO *)
0x1400215d2  xor     al, al
0x1400215d4  mov     [rsp+1E0h+var_1A0], al
0x1400215d8  xor     edx, edx; Val
0x1400215da  lea     rcx, [rbp+0E0h+var_120]; void *
0x1400215de  mov     r8d, 0D0h; Size
0x1400215e4  call    memset_0
0x1400215e9  mov     rax, [rsp+1E0h+var_178]
0x1400215ee  lea     r8, [rbp+0E0h+var_120]
0x1400215f2  mov     r9b, 1
0x1400215f5  lea     rdx, [rbp+0E0h+var_140]
0x1400215f9  mov     rcx, rdi
0x1400215fc  movups  xmm0, xmmword ptr [r14+rax]
0x140021601  mov     rax, [rdi]
0x140021604  movdqu  [rbp+0E0h+var_140], xmm0
0x140021609  mov     rax, [rax+58h]
0x14002160d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021612  mov     ebx, eax
0x140021614  test    eax, eax
0x140021616  js      loc_1400219BD
0x14002161c  cmp     [rsp+1E0h+var_19F], 0
0x140021621  mov     [rsp+1E0h+var_1A0], 1
0x140021626  jz      short loc_140021668
0x140021628  cmp     [rbp+0E0h+var_F8], 1
0x14002162c  jz      short loc_140021646
0x14002162e  lea     r8, aBsicatMCtarget; "bsiCat.m_cTarget == 1"
0x140021635  mov     edx, 3BCAh; unsigned int
0x14002163a  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x140021641  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140021646  mov     rcx, [rbp+0E0h+var_F0]
0x14002164a  mov     r9, [rbp+0E0h+var_150]; unsigned __int8 *
0x14002164e  movzx   r8d, word ptr [rbp+0E0h+var_158]; unsigned __int16
0x140021653  mov     rdx, [rcx+20h]; unsigned __int8 *
0x140021657  movzx   ecx, word ptr [rcx+18h]; unsigned __int16
0x14002165b  call    ?BlbutilCompareUniqueIds@@YAEGPEBEG0@Z; BlbutilCompareUniqueIds(ushort,uchar const *,ushort,uchar const *)
0x140021660  test    al, al
0x140021662  jz      loc_1400217EB
0x140021668  inc     dword ptr [rsp+1E0h+var_190]
0x14002166c  xor     ebx, ebx
0x14002166e  mov     rcx, [rsp+1E0h+pv]; pv
0x140021673  test    rcx, rcx
0x140021676  jz      short loc_140021683
0x140021678  call    cs:__imp_CoTaskMemFree
0x14002167e  mov     [rsp+1E0h+pv], rbx
0x140021683  mov     rcx, [rbp+0E0h+var_160]; pv
0x140021687  test    rcx, rcx
0x14002168a  jz      short loc_140021696
0x14002168c  call    cs:__imp_CoTaskMemFree
0x140021692  mov     [rbp+0E0h+var_160], rbx
0x140021696  mov     rcx, [rsp+1E0h+var_170]; pv
0x14002169b  test    rcx, rcx
0x14002169e  jz      short loc_1400216AB
0x1400216a0  call    cs:__imp_CoTaskMemFree
0x1400216a6  mov     [rsp+1E0h+var_170], rbx
0x1400216ab  mov     rcx, [rsi+158h]; unsigned __int16 *
0x1400216b2  lea     rax, [rsp+1E0h+var_170]
0x1400216b7  mov     [rsp+1E0h+var_1B0], rax; unsigned __int16 **
0x1400216bc  lea     r9, [rsi+28h]; struct CBlbImpersonationHelper *
0x1400216c0  lea     rax, [rbp+0E0h+var_160]
0x1400216c4  xor     edx, edx; unsigned __int8
0x1400216c6  mov     [rsp+1E0h+var_1B8], rax; unsigned __int16 **
0x1400216cb  lea     r8, [rbp+0E0h+var_120]; struct _BLBCAT_BACKUP_SET_INFO *
0x1400216cf  lea     rax, [rsp+1E0h+pv]
0x1400216d4  mov     [rsp+1E0h+var_1C0], rax; unsigned __int16 **
0x1400216d9  call    ?BlbGetTargetPathForBackupSet@@YAJPEAGEPEAU_BLBCAT_BACKUP_SET_INFO@@PEAVCBlbImpersonationHelper@@PEAPEAG33@Z; BlbGetTargetPathForBackupSet(ushort *,uchar,_BLBCAT_BACKUP_SET_INFO *,CBlbImpersonationHelper *,ushort * *,ushort * *,ushort * *)
0x1400216de  mov     ebx, eax
0x1400216e0  cmp     eax, 80780027h
0x1400216e5  jz      short loc_14002173F
0x1400216e7  cmp     eax, 80780039h
0x1400216ec  jz      short loc_14002173F
0x1400216ee  test    eax, eax
0x1400216f0  js      loc_1400219BD
0x1400216f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400216fd  lea     rax, WPP_GLOBAL_Control
0x140021704  cmp     rcx, rax
0x140021707  jz      loc_1400217F2
0x14002170d  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
