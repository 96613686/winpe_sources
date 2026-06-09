# CEEAppXHandler::GetPackageInstallStatus(tagDSGlobalUpdateId const &,void *,AppxPackage const *,tagSusRuleContext const &,wchar_t * *,ApplicabilityResultContext *,ulong *)

- ea: `0x180204e18`
- end: `0x1802053f6`
- name: `?GetPackageInstallStatus@CEEAppXHandler@@AEAAJAEBUtagDSGlobalUpdateId@@PEAXPEBVAppxPackage@@AEBUtagSusRuleContext@@PEAPEA_WPEAW4ApplicabilityResultContext@@PEAK@Z`
- size: `1502`
- prototype: `int(CEEAppXHandler *__hidden this, const struct tagDSGlobalUpdateId *, void *, const struct AppxPackage *, const struct tagSusRuleContext *, wchar_t **, enum ApplicabilityResultContext *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802053fc`

## callees

- `0x18012b618`
- `0x18012bf80`
- `0x18012d9d4`
- `0x18013618c`
- `0x180204e18`
- `0x18020587c`
- `0x180218d20`
- `0x180219b90`
- `0x18021a948`
- `0x18021aa40`
- `0x18021ac04`
- `0x18021ad10`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180204ec4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180204ec4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180204f53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180204f53`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180204f1a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180204f1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18020507a`
- `OLEAUT32!__imp_SysFreeString` at `0x180205180`
- `OLEAUT32!__imp_SysFreeString` at `0x1802052b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18020507a`
- `OLEAUT32!__imp_SysFreeString` at `0x180205180`
- `OLEAUT32!__imp_SysFreeString` at `0x1802052b0`

## string_xrefs

- `0x18020531e`: `Installed`
- `0x180205327`: `Installable`
- `0x1802050e2`: `SupportsAppProvisionAfterInstall`
- `0x1802050e9`: `SOFTWARE\Microsoft\WindowsUpdate\Client`
- `0x1802052db`: `installable`
- `0x180205373`: `AppX update %ws (PFN: %ws; evaldata: %ws) has applicability state %ws evaluated as %ws`
- `0x1802053bd`: `AppX update %ws (PFN: %ws) evaluation failed.`
- `0x1802052d2`: `installed`
- `0x180205330`: `NotInstallable`
- `0x180205315`: `RequiresReinstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CEEAppXHandler::GetPackageInstallStatus(
        CEEAppXHandler *this,
        const struct tagDSGlobalUpdateId *a2,
        void *a3,
        AppXDeliveryProperties **a4,
        const struct tagSusRuleContext *a5,
        wchar_t **a6,
        enum ApplicabilityResultContext *a7,
        unsigned int *a8)
{
  enum ApplicabilityResultContext *v9; // r14
  unsigned int v10; // esi
  AppXDeliveryProperties *v11; // rax
  int IsInstalledChannelIdEqual; // edi
  struct tagDSGlobalUpdateId *v13; // r14
  AppXDeliveryProperties *v14; // rbx
  __int64 v15; // r8
  const wchar_t *v16; // rdx
  wchar_t *v17; // rbx
  __int64 v18; // rcx
  bool *v19; // r9
  PSID v20; // r13
  char v21; // dl
  __int64 v22; // r14
  const wchar_t *v23; // rdx
  bool *v24; // r9
  unsigned int v25; // edi
  OLECHAR *v26; // rcx
  unsigned int v27; // ecx
  int v28; // edi
  unsigned int v29; // r14d
  struct CPackageManagerWrapper *v30; // rcx
  struct CPackageManagerWrapper *v31; // rcx
  int v32; // ecx
  struct CPackageManagerWrapper *v33; // rcx
  const enum ApplicabilityResultContext *v34; // r8
  wchar_t *v35; // rax
  const wchar_t *v36; // r15
  unsigned int v37; // esi
  unsigned int v38; // esi
  unsigned int v39; // esi
  const wchar_t *v40; // rbx
  const wchar_t *v41; // rsi
  __int64 v42; // rax
  __int64 updated; // rax
  const wchar_t *v45; // [rsp+48h] [rbp-B8h]
  wchar_t v46; // [rsp+60h] [rbp-A0h] BYREF
  char v47; // [rsp+62h] [rbp-9Eh]
  char v48; // [rsp+63h] [rbp-9Dh]
  struct tagDSGlobalUpdateId *v49; // [rsp+68h] [rbp-98h]
  AppXDeliveryProperties *v50; // [rsp+70h] [rbp-90h]
  unsigned int v51; // [rsp+78h] [rbp-88h]
  enum ApplicabilityResultContext *v52; // [rsp+80h] [rbp-80h]
  struct CPackageManagerWrapper *v53; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v54; // [rsp+90h] [rbp-70h]
  unsigned int v55; // [rsp+94h] [rbp-6Ch] BYREF
  OLECHAR *v56; // [rsp+98h] [rbp-68h] BYREF
  int v57; // [rsp+A0h] [rbp-60h]
  PSID pSid2; // [rsp+A8h] [rbp-58h]
  CEEAppXHandler *v59; // [rsp+B0h] [rbp-50h]
  const struct AppxPackage *v60; // [rsp+B8h] [rbp-48h]
  CAppxApplicabilityResultsCache *v61; // [rsp+C0h] [rbp-40h]
  _BYTE v62[176]; // [rsp+D0h] [rbp-30h] BYREF

  v60 = (const struct AppxPackage *)a4;
  pSid2 = a3;
  v49 = a2;
  v59 = this;
  v9 = a7;
  v52 = a7;
  v10 = 1;
  v55 = 1;
  v51 = 5;
  v11 = a4[2];
  v50 = v11;
  if ( !a7 )
  {
    IsInstalledChannelIdEqual = -2147467261;
    v13 = a2;
    v14 = v11;
LABEL_103:
    updated = Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v62, v13);
    WUTrace(
      0,
      0,
      0x100000,
      3,
      IsInstalledChannelIdEqual,
      L"AppX update %ws (PFN: %ws) evaluation failed.",
      updated,
      v14);
    return (unsigned int)IsInstalledChannelIdEqual;
  }
  *(_DWORD *)a7 = 0;
  if ( a6 )
    *a6 = 0;
  *a8 = 0;
  v61 = (CEEAppXHandler *)((char *)this + 208);
  IsInstalledChannelIdEqual = -2145124344;
  if ( a6 )
    *a6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( *(_OWORD *)((char *)this + 264) == *(_OWORD *)v49 && *((_DWORD *)this + 70) == *((_DWORD *)v49 + 4) )
  {
    v15 = *((_QWORD *)this + 32);
    if ( (v15 == 0) == (pSid2 == 0) && (!v15 || EqualSid(*((PSID *)this + 32), pSid2)) )
    {
      *a8 = *((_DWORD *)this + 75);
      *(_DWORD *)a7 = *((_DWORD *)this + 74);
      if ( a6 )
        IsInstalledChannelIdEqual = SusSysAllocString(*((const wchar_t **)this + 36), a6);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( IsInstalledChannelIdEqual != -2145124344 )
  {
    v13 = v49;
    if ( IsInstalledChannelIdEqual < 0 )
    {
      v14 = v50;
      goto LABEL_103;
    }
    goto LABEL_80;
  }
  v17 = 0;
  v56 = 0;
  if ( !AppXPolicy::IsPackageFamilyNameOnDoNotUpdateList(v50, v16) )
  {
    v21 = 0;
    if ( !*((_DWORD *)a5 + 42) )
      goto LABEL_43;
    v22 = *((_QWORD *)a5 + 24);
    v54 = *((_DWORD *)a5 + 46);
    v57 = *((_DWORD *)a5 + 40);
    v46 = 0;
    v47 = 0;
    v48 = 0;
    IsInstalledChannelIdEqual = AppXDeliveryProperties::IsInstalledChannelIdEqual(
                                  v50,
                                  *((const wchar_t **)a5 + 22),
                                  &v46,
                                  v19);
    if ( IsInstalledChannelIdEqual < 0 )
      goto LABEL_33;
    if ( !(_BYTE)v46 )
    {
      v48 = 1;
LABEL_21:
      v21 = 1;
LABEL_37:
      v27 = *(_DWORD *)v52 | 1;
      if ( !v48 )
        v27 = *(_DWORD *)v52 & 0xFFFFFFFE;
      if ( HIBYTE(v46) )
        v18 = v27 | 2;
      else
        v18 = v27 & 0xFFFFFFFD;
      *(_DWORD *)v52 = v18;
LABEL_43:
      v28 = (*((_DWORD *)a5 + 40) != 0) | 4;
      if ( !v21 )
        v28 = *((_DWORD *)a5 + 40) != 0;
      if ( (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                           v18,
                           L"SOFTWARE\\Microsoft\\WindowsUpdate\\Client",
                           L"SupportsAppProvisionAfterInstall",
                           0,
                           0,
                           -1) )
      {
        if ( *((_DWORD *)a5 + 2) == 1 )
        {
          v29 = v28 | 2;
        }
        else if ( *((_DWORD *)a5 + 41) || (v29 = v28, !*((_DWORD *)a5 + 50)) )
        {
          v29 = v28 | 8;
        }
      }
      else if ( *((_DWORD *)a5 + 41) || (v29 = v28, *((_DWORD *)a5 + 2) == 1) )
      {
        v29 = v28 | 2;
      }
      v53 = 0;
      IsInstalledChannelIdEqual = CEEAppXHandler::GetPackageManagerWrapper(v59, &v53);
      if ( IsInstalledChannelIdEqual < 0 )
      {
        v30 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*(void (__fastcall **)(struct CPackageManagerWrapper *))(*(_QWORD *)v30 + 16LL))(v30);
        }
        v26 = 0;
        goto LABEL_35;
      }
      SysFreeString(0);
      v56 = 0;
      v20 = pSid2;
      IsInstalledChannelIdEqual = CPackageManagerWrapper::GetApplicability(
                                    (__int64)&v56,
                                    (__int64)v60,
                                    v29,
                                    *((_DWORD *)a5 + 40) != 0,
                                    pSid2,
                                    *((wchar_t **)a5 + 19),
                                    (wchar_t **)a5 + 2,
                                    &v56,
                                    &v55);
      if ( IsInstalledChannelIdEqual < 0 )
      {
        v31 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*(void (__fastcall **)(struct CPackageManagerWrapper *))(*(_QWORD *)v31 + 16LL))(v31);
        }
        v26 = v56;
        goto LABEL_35;
      }
      v10 = v55;
      if ( v55 )
      {
        if ( v55 == 1 )
        {
          *a8 = 56;
        }
        else
        {
          if ( v55 != 2 )
          {
            v32 = v55 - 3;
            v9 = v52;
            if ( v55 == 3 )
            {
              *a8 = 56;
              v51 = 4;
              *(_DWORD *)v9 |= 4u;
            }
            else
            {
              *a8 = 57;
              if ( v32 != 1 )
                v51 = 3;
            }
            goto LABEL_73;
          }
          *a8 = 57;
        }
      }
      else
      {
        *a8 = 0;
      }
      v9 = v52;
LABEL_73:
      v33 = v53;
      if ( v53 )
      {
        v53 = 0;
        (*(void (__fastcall **)(struct CPackageManagerWrapper *))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v17 = v56;
      goto LABEL_76;
    }
    if ( AppXPolicy::IsPackageFamilyManagedByRelease(v50, v23) )
    {
      HIBYTE(v46) = 1;
      goto LABEL_21;
    }
    if ( v57 )
    {
      if ( v54 && v22 )
      {
        v25 = 0;
        while ( 1 )
        {
          LOBYTE(v46) = 0;
          if ( (int)AppXPolicy::IsAnyPackageFamiliesManagedByRelease(
                      (AppXPolicy *)*(unsigned int *)(*(_QWORD *)v22 + 608LL),
                      *(struct tagDSDataBlob **)(*(_QWORD *)v22 + 616LL),
                      (const struct tagDSDataBlob *const)&v46,
                      v24) >= 0 )
            break;
          ++v25;
          v22 += 8;
          if ( v25 >= v54 )
          {
            v21 = 0;
            goto LABEL_37;
          }
        }
        HIBYTE(v46) = v46;
        v21 = v46;
        goto LABEL_37;
      }
      IsInstalledChannelIdEqual = -2145062913;
    }
    else
    {
LABEL_33:
      if ( IsInstalledChannelIdEqual >= 0 )
      {
        v21 = v47;
        goto LABEL_37;
      }
    }
    v26 = 0;
LABEL_35:
    SysFreeString(v26);
    v13 = v49;
    v14 = v50;
    goto LABEL_100;
  }
  *a8 = 0;
  v20 = pSid2;
LABEL_76:
  v34 = v9;
  v13 = v49;
  CAppxApplicabilityResultsCache::CacheApplicabilityResult(v61, v49, v34, v20, v17, *a8);
  if ( a6 )
  {
    v35 = v17;
    v17 = 0;
    *a6 = v35;
  }
  IsInstalledChannelIdEqual = 0;
  SysFreeString(v17);
LABEL_80:
  if ( *a8 == 56 )
  {
    v36 = L"installable";
  }
  else if ( *a8 == 57 )
  {
    v36 = L"installed";
  }
  else
  {
    v36 = L"not applicable";
  }
  if ( v10 )
  {
    v37 = v10 - 1;
    if ( v37 )
    {
      v38 = v37 - 1;
      if ( v38 )
      {
        v39 = v38 - 1;
        if ( v39 )
        {
          if ( v39 == 1 )
            v40 = L"Offline";
          else
            v40 = L"Unknown";
        }
        else
        {
          v40 = L"RequiresReinstall";
        }
      }
      else
      {
        v40 = L"Installed";
      }
    }
    else
    {
      v40 = L"Installable";
    }
  }
  else
  {
    v40 = L"NotInstallable";
  }
  if ( a6 )
    v41 = *a6;
  else
    v41 = L"n/a";
  v42 = Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v62, v13);
  v45 = v40;
  v14 = v50;
  WUTrace(
    0,
    0,
    0x100000,
    v51,
    0,
    L"AppX update %ws (PFN: %ws; evaldata: %ws) has applicability state %ws evaluated as %ws",
    v42,
    v50,
    v41,
    v45,
    v36);
LABEL_100:
  if ( IsInstalledChannelIdEqual < 0 )
    goto LABEL_103;
  return (unsigned int)IsInstalledChannelIdEqual;
}

```

## disassembly

```asm
0x180204e18  push    rbp
0x180204e1a  push    rbx
0x180204e1b  push    rsi
0x180204e1c  push    rdi
0x180204e1d  push    r12
0x180204e1f  push    r13
0x180204e21  push    r14
0x180204e23  push    r15
0x180204e25  lea     rbp, [rsp-48h]
0x180204e2a  sub     rsp, 148h
0x180204e31  mov     [rbp+80h+var_C8], r9
0x180204e35  mov     [rbp+80h+pSid2], r8
0x180204e39  mov     [rsp+180h+var_118], rdx
0x180204e3e  mov     rbx, rcx
0x180204e41  mov     [rbp+80h+var_D0], rcx
0x180204e45  mov     r14, [rbp+80h+arg_30]
0x180204e4c  mov     [rbp+80h+var_100], r14
0x180204e50  mov     r13, [rbp+80h+arg_20]
0x180204e57  mov     r12, [rbp+80h+arg_28]
0x180204e5e  mov     r15, [rbp+80h+arg_38]
0x180204e65  mov     esi, 1
0x180204e6a  mov     [rbp+80h+var_EC], esi
0x180204e6d  mov     [rsp+180h+var_108], 5
0x180204e75  mov     rax, [r9+10h]
0x180204e79  mov     [rsp+180h+var_110], rax
0x180204e7e  xor     ecx, ecx
0x180204e80  test    r14, r14
0x180204e83  jnz     short loc_180204E95
0x180204e85  mov     edi, 80004003h
0x180204e8a  mov     r14, rdx
0x180204e8d  mov     rbx, rax
0x180204e90  jmp     loc_1802053A7
0x180204e95  mov     [r14], ecx
0x180204e98  test    r12, r12
0x180204e9b  jz      short loc_180204EA1
0x180204e9d  mov     [r12], rcx
0x180204ea1  mov     [r15], ecx
0x180204ea4  lea     rax, [rbx+0D0h]
0x180204eab  mov     [rbp+80h+var_C0], rax
0x180204eaf  mov     edi, 80240008h
0x180204eb4  test    r12, r12
0x180204eb7  jz      short loc_180204EBD
0x180204eb9  mov     [r12], rcx
0x180204ebd  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x180204ec4  call    cs:__imp_EnterCriticalSection
0x180204eca  mov     rax, [rbx+108h]
0x180204ed1  mov     rcx, [rsp+180h+var_118]
0x180204ed6  cmp     rax, [rcx]
0x180204ed9  jnz     short loc_180204F4C
0x180204edb  mov     rax, [rbx+110h]
0x180204ee2  cmp     rax, [rcx+8]
0x180204ee6  jnz     short loc_180204F4C
0x180204ee8  mov     eax, [rcx+10h]
0x180204eeb  cmp     [rbx+118h], eax
0x180204ef1  jnz     short loc_180204F4C
0x180204ef3  mov     r8, [rbx+100h]
0x180204efa  xor     ecx, ecx
0x180204efc  test    r8, r8
0x180204eff  setz    cl
0x180204f02  xor     eax, eax
0x180204f04  mov     rdx, [rbp+80h+pSid2]; pSid2
0x180204f08  test    rdx, rdx
0x180204f0b  setz    al
0x180204f0e  cmp     ecx, eax
0x180204f10  jnz     short loc_180204F4C
0x180204f12  test    r8, r8
0x180204f15  jz      short loc_180204F24
0x180204f17  mov     rcx, r8; pSid1
0x180204f1a  call    cs:__imp_EqualSid
0x180204f20  test    eax, eax
0x180204f22  jz      short loc_180204F4C
0x180204f24  mov     eax, [rbx+12Ch]
0x180204f2a  mov     [r15], eax
0x180204f2d  mov     eax, [rbx+128h]
0x180204f33  mov     [r14], eax
0x180204f36  test    r12, r12
0x180204f39  jz      short loc_180204F4C
0x180204f3b  mov     rdx, r12; wchar_t **
0x180204f3e  mov     rcx, [rbx+120h]; wchar_t *
0x180204f45  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x180204f4a  mov     edi, eax
0x180204f4c  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x180204f53  call    cs:__imp_LeaveCriticalSection
0x180204f59  cmp     edi, 80240008h
0x180204f5f  jnz     loc_1802052B8
0x180204f65  xor     ebx, ebx
0x180204f67  mov     [rbp+80h+var_E8], rbx
0x180204f6b  mov     rdi, [rsp+180h+var_110]
0x180204f70  mov     rcx, rdi; this
0x180204f73  call    ?IsPackageFamilyNameOnDoNotUpdateList@AppXPolicy@@YA_NPEB_W@Z; AppXPolicy::IsPackageFamilyNameOnDoNotUpdateList(wchar_t const *)
0x180204f78  xor     r8d, r8d
0x180204f7b  test    al, al
0x180204f7d  jz      short loc_180204F8B
0x180204f7f  mov     [r15], r8d
0x180204f82  mov     r13, [rbp+80h+pSid2]
0x180204f86  jmp     loc_18020527A
0x180204f8b  mov     dl, r8b
0x180204f8e  cmp     [r13+0A8h], r8d
0x180204f95  jz      loc_1802050BB
0x180204f9b  mov     r14, [r13+0C0h]
0x180204fa2  mov     eax, [r13+0B8h]
0x180204fa9  mov     [rbp+80h+var_F0], eax
0x180204fac  mov     eax, [r13+0A0h]
0x180204fb3  mov     [rbp+80h+var_E0], eax
0x180204fb6  mov     byte ptr [rsp+180h+var_120], r8b
0x180204fbb  mov     [rsp+180h+var_11E], r8b
0x180204fc0  mov     [rsp+180h+var_11D], r8b
0x180204fc5  mov     byte ptr [rsp+180h+var_120+1], r8b
0x180204fca  lea     r8, [rsp+180h+var_120]; wchar_t *
0x180204fcf  mov     rdx, [r13+0B0h]; wchar_t *
0x180204fd6  mov     rcx, rdi; this
0x180204fd9  call    ?IsInstalledChannelIdEqual@AppXDeliveryProperties@@YAJPEB_W0PEA_N@Z; AppXDeliveryProperties::IsInstalledChannelIdEqual(wchar_t const *,wchar_t const *,bool *)
0x180204fde  mov     edi, eax
0x180204fe0  xor     r8d, r8d
0x180204fe3  test    eax, eax
0x180204fe5  js      loc_180205074
0x180204feb  cmp     byte ptr [rsp+180h+var_120], r8b
0x180204ff0  jnz     short loc_180204FFF
0x180204ff2  mov     [rsp+180h+var_11D], sil
0x180204ff7  mov     dl, sil
0x180204ffa  jmp     loc_180205093
0x180204fff  mov     rcx, [rsp+180h+var_110]; this
0x180205004  call    ?IsPackageFamilyManagedByRelease@AppXPolicy@@YA_NPEB_W@Z; AppXPolicy::IsPackageFamilyManagedByRelease(wchar_t const *)
0x180205009  xor     r8d, r8d
0x18020500c  test    al, al
0x18020500e  jz      short loc_180205017
0x180205010  mov     byte ptr [rsp+180h+var_120+1], sil
0x180205015  jmp     short loc_180204FF7
0x180205017  cmp     [rbp+80h+var_E0], r8d
0x18020501b  jz      short loc_180205074
0x18020501d  cmp     [rbp+80h+var_F0], r8d
0x180205021  ja      short loc_18020502A
0x180205023  mov     edi, 8024EFFFh
0x180205028  jmp     short loc_180205078
0x18020502a  test    r14, r14
0x18020502d  jz      short loc_180205023
0x18020502f  mov     edi, r8d
0x180205032  mov     byte ptr [rsp+180h+var_120], r8b
0x180205037  mov     rcx, [r14]
0x18020503a  lea     r8, [rsp+180h+var_120]; struct tagDSDataBlob *
0x18020503f  mov     rdx, [rcx+268h]; struct tagDSDataBlob *
0x180205046  mov     ecx, [rcx+260h]; this
0x18020504c  call    ?IsAnyPackageFamiliesManagedByRelease@AppXPolicy@@YAJKQEBUtagDSDataBlob@@PEA_N@Z; AppXPolicy::IsAnyPackageFamiliesManagedByRelease(ulong,tagDSDataBlob const * const,bool *)
0x180205051  xor     r8d, r8d
0x180205054  test    eax, eax
0x180205056  jns     short loc_180205068
0x180205058  add     edi, esi
0x18020505a  add     r14, 8
0x18020505e  cmp     edi, [rbp+80h+var_F0]
0x180205061  jb      short loc_180205032
0x180205063  mov     dl, r8b
0x180205066  jmp     short loc_180205093
0x180205068  mov     al, byte ptr [rsp+180h+var_120]
0x18020506c  mov     byte ptr [rsp+180h+var_120+1], al
0x180205070  mov     dl, al
0x180205072  jmp     short loc_180205093
0x180205074  test    edi, edi
0x180205076  jns     short loc_18020508F
0x180205078  xor     ecx, ecx; bstrString
0x18020507a  call    cs:__imp_SysFreeString
0x180205080  mov     r14, [rsp+180h+var_118]
0x180205085  mov     rbx, [rsp+180h+var_110]
0x18020508a  jmp     loc_18020539C
0x18020508f  mov     dl, [rsp+180h+var_11E]
0x180205093  mov     r14, [rbp+80h+var_100]
0x180205097  mov     ecx, [r14]
0x18020509a  mov     eax, ecx
0x18020509c  and     eax, 0FFFFFFFEh
0x18020509f  or      ecx, esi
0x1802050a1  cmp     [rsp+180h+var_11D], r8b
0x1802050a6  cmovz   ecx, eax
0x1802050a9  cmp     byte ptr [rsp+180h+var_120+1], r8b
0x1802050ae  jz      short loc_1802050B5
0x1802050b0  or      ecx, 2
0x1802050b3  jmp     short loc_1802050B8
0x1802050b5  and     ecx, 0FFFFFFFDh
0x1802050b8  mov     [r14], ecx
0x1802050bb  mov     eax, r8d
0x1802050be  cmp     [r13+0A0h], r8d
0x1802050c5  setnz   al
0x1802050c8  mov     edi, eax
0x1802050ca  or      edi, 4
0x1802050cd  test    dl, dl
0x1802050cf  cmovz   edi, eax
0x1802050d2  mov     [rsp+180h+var_158], 0FFFFFFFFh
0x1802050da  mov     dword ptr [rsp+180h+var_160], r8d
0x1802050df  xor     r9d, r9d
0x1802050e2  lea     r8, ?c_szAppProvisionAfterInstall@@3QB_WB; "SupportsAppProvisionAfterInstall"
0x1802050e9  lea     rdx, ?c_szClientKey@@3QB_WB; "SOFTWARE\\Microsoft\\WindowsUpdate\\Cli"...
0x1802050f0  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1802050f5  xor     ecx, ecx
0x1802050f7  test    eax, eax
0x1802050f9  jz      short loc_180205127
0x1802050fb  cmp     [r13+8], esi
0x1802050ff  jnz     short loc_180205109
0x180205101  or      edi, 2
0x180205104  mov     r14d, edi
0x180205107  jmp     short loc_180205140
0x180205109  cmp     [r13+0A4h], ecx
0x180205110  jnz     short loc_18020511E
0x180205112  mov     r14d, edi
0x180205115  cmp     [r13+0C8h], ecx
0x18020511c  jnz     short loc_180205140
0x18020511e  mov     r14d, edi
0x180205121  or      r14d, 8
0x180205125  jmp     short loc_180205140
0x180205127  cmp     [r13+0A4h], ecx
0x18020512e  jnz     short loc_180205139
0x180205130  mov     r14d, edi
0x180205133  cmp     [r13+8], esi
0x180205137  jnz     short loc_180205140
0x180205139  mov     r14d, edi
0x18020513c  or      r14d, 2
0x180205140  mov     [rbp+80h+var_F8], rcx
0x180205144  lea     rdx, [rbp+80h+var_F8]; struct CPackageManagerWrapper **
0x180205148  mov     rcx, [rbp+80h+var_D0]; this
0x18020514c  call    ?GetPackageManagerWrapper@CEEAppXHandler@@AEAAJPEAPEAVCPackageManagerWrapper@@@Z; CEEAppXHandler::GetPackageManagerWrapper(CPackageManagerWrapper * *)
0x180205151  mov     edi, eax
0x180205153  test    eax, eax
0x180205155  jns     short loc_18020517D
0x180205157  mov     rcx, [rbp+80h+var_F8]
0x18020515b  test    rcx, rcx
0x18020515e  jz      short loc_180205175
0x180205160  mov     [rbp+80h+var_F8], 0
0x180205168  mov     rdx, [rcx]
0x18020516b  mov     rax, [rdx+10h]
0x18020516f  call    _guard_dispatch_icall
0x180205174  nop
0x180205175  mov     rcx, rbx
0x180205178  jmp     loc_18020507A
0x18020517d  mov     rcx, rbx; bstrString
0x180205180  call    cs:__imp_SysFreeString
0x180205186  xor     ebx, ebx
0x180205188  mov     [rbp+80h+var_E8], rbx
0x18020518c  lea     rax, [r13+10h]
0x180205190  cmp     [r13+0A0h], ebx
0x180205197  setnz   r9b
0x18020519b  lea     rcx, [rbp+80h+var_EC]
0x18020519f  mov     [rsp+180h+var_140], rcx
0x1802051a4  lea     rcx, [rbp+80h+var_E8]
0x1802051a8  mov     [rsp+180h+var_148], rcx
0x1802051ad  mov     [rsp+180h+var_150], rax
0x1802051b2  mov     rax, [r13+98h]
0x1802051b9  mov     qword ptr [rsp+180h+var_158], rax
0x1802051be  mov     r13, [rbp+80h+pSid2]
0x1802051c2  mov     [rsp+180h+var_160], r13
0x1802051c7  mov     r8d, r14d
0x1802051ca  mov     rdx, [rbp+80h+var_C8]
0x1802051ce  call    ?GetApplicability@CPackageManagerWrapper@@QEAAJPEBVAppxPackage@@W4GetApplicabilityFlags@@_NQEAXPEB_WPEBDPEAPEA_WPEAW4ApplicabilityState@@@Z; CPackageManagerWrapper::GetApplicability(AppxPackage const *,GetApplicabilityFlags,bool,void * const,wchar_t const *,char const *,wchar_t * *,ApplicabilityState *)
0x1802051d3  mov     edi, eax
0x1802051d5  test    eax, eax
0x1802051d7  jns     short loc_1802051FC
0x1802051d9  mov     rcx, [rbp+80h+var_F8]
0x1802051dd  test    rcx, rcx
0x1802051e0  jz      short loc_1802051F3
0x1802051e2  mov     [rbp+80h+var_F8], rbx
0x1802051e6  mov     rax, [rcx]
0x1802051e9  mov     rax, [rax+10h]
0x1802051ed  call    _guard_dispatch_icall
0x1802051f2  nop
0x1802051f3  mov     rcx, [rbp+80h+var_E8]
0x1802051f7  jmp     loc_18020507A
0x1802051fc  mov     esi, [rbp+80h+var_EC]
0x1802051ff  mov     ecx, esi
0x180205201  test    esi, esi
0x180205203  jz      short loc_180205255
0x180205205  sub     ecx, 1
0x180205208  jz      short loc_18020524C
0x18020520a  sub     ecx, 1
0x18020520d  jz      short loc_180205243
0x18020520f  sub     ecx, 1
0x180205212  mov     r14, [rbp+80h+var_100]
0x180205216  jz      short loc_18020522E
0x180205218  mov     dword ptr [r15], 39h ; '9'
0x18020521f  cmp     ecx, 1
0x180205222  jz      short loc_18020525C
0x180205224  mov     [rsp+180h+var_108], 3
0x18020522c  jmp     short loc_18020525C
0x18020522e  mov     dword ptr [r15], 38h ; '8'
0x180205235  mov     [rsp+180h+var_108], 4
0x18020523d  or      dword ptr [r14], 4
0x180205241  jmp     short loc_18020525C
0x180205243  mov     dword ptr [r15], 39h ; '9'
0x18020524a  jmp     short loc_180205258
0x18020524c  mov     dword ptr [r15], 38h ; '8'
0x180205253  jmp     short loc_180205258
0x180205255  mov     [r15], ebx
0x180205258  mov     r14, [rbp+80h+var_100]
0x18020525c  mov     rcx, [rbp+80h+var_F8]
0x180205260  test    rcx, rcx
0x180205263  jz      short loc_180205276
0x180205265  mov     [rbp+80h+var_F8], rbx
0x180205269  mov     rax, [rcx]
0x18020526c  mov     rax, [rax+10h]
0x180205270  call    _guard_dispatch_icall
0x180205275  nop
0x180205276  mov     rbx, [rbp+80h+var_E8]
0x18020527a  mov     eax, [r15]
0x18020527d  mov     [rsp+180h+var_158], eax; unsigned int
0x180205281  mov     [rsp+180h+var_160], rbx; wchar_t *
  ... truncated ...
```
