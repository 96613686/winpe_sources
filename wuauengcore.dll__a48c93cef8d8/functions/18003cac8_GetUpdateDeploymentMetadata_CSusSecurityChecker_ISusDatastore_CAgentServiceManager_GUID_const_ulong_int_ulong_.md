# GetUpdateDeploymentMetadata(CSusSecurityChecker *,ISusDatastore *,CAgentServiceManager *,_GUID const &,ulong,int,ulong,uchar const *,ulong,tagMatchingUpdate const * const,ulong,tagDSUpdateMetadata * const)

- ea: `0x18003cac8`
- end: `0x18003d661`
- name: `?GetUpdateDeploymentMetadata@@YAJPEAVCSusSecurityChecker@@PEAUISusDatastore@@PEAVCAgentServiceManager@@AEBU_GUID@@KHKPEBEKQEBUtagMatchingUpdate@@KQEAUtagDSUpdateMetadata@@@Z`
- size: `2969`
- prototype: `__int64 __fastcall(struct CSusSecurityChecker *, struct ISusDatastore *, struct CAgentServiceManager *, const struct _GUID *, unsigned int, int, unsigned int, unsigned __int8 *, unsigned int, const struct tagMatchingUpdate *, unsigned int, struct tagDSUpdateMetadata *const)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180042f20`
- `0x1800d1c60`

## callees

- `0x18000def4`
- `0x18003baf4`
- `0x18003bc54`
- `0x18003c710`
- `0x18003cac8`
- `0x18005c79c`
- `0x180060988`
- `0x1800634f8`
- `0x180105194`
- `0x18010bc10`
- `0x18010fc44`
- `0x180113a3c`
- `0x180113ae8`
- `0x180113b9c`
- `0x180113c50`
- `0x180119e48`
- `0x18011b100`
- `0x1801335f4`
- `0x180133a10`
- `0x180134e3c`
- `0x180238960`
- `0x180238984`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003cd24`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003cd24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003cd8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003cd8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d387`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d3b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d387`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d3b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d583`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d592`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003d2d1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003d2d1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d34d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d522`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d34d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003d522`

## string_xrefs

- `0x18003cb42`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003cb86`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003d048`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003d111`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003d361`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003d4e8`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003d50a`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003d536`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003d55f`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18003d5b4`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetUpdateDeploymentMetadata(
        struct CSusSecurityChecker *a1,
        struct ISusDatastore *a2,
        struct CAgentServiceManager *a3,
        const struct _GUID *a4,
        unsigned int a5,
        int a6,
        unsigned int a7,
        unsigned __int8 *a8,
        unsigned int a9,
        const struct tagMatchingUpdate *a10,
        unsigned int a11,
        struct tagDSUpdateMetadata *const a12)
{
  const struct tagMatchingUpdate *v15; // rdx
  __int64 v16; // rdx
  signed int ServiceObject; // r15d
  _DWORD *v19; // rdi
  CCallerIdentity *v20; // rsi
  unsigned int i; // ebx
  __int64 v22; // rdx
  __int64 v23; // rax
  double *v24; // rbx
  RTL_SRWLOCK *v25; // rsi
  signed int v26; // eax
  __int64 (__fastcall *v27)(struct ISusDatastore *, __int64 *); // rbx
  const struct tagMatchingUpdate *v28; // r12
  _DWORD *v29; // rcx
  __int64 v30; // r8
  unsigned int v31; // edx
  unsigned __int64 v32; // rbx
  char *v33; // r8
  __int64 v34; // rbx
  unsigned int v35; // r9d
  int v36; // r15d
  int v37; // eax
  __int64 v38; // rax
  int v39; // ecx
  void *v40; // rbx
  unsigned __int64 v41; // r9
  __int64 v42; // rdx
  int v43; // eax
  __int64 j; // r8
  __int64 v45; // rdx
  int v46; // eax
  signed int v47; // ebx
  __int64 v48; // r14
  unsigned int v49; // ebx
  unsigned int v50; // eax
  char *v51; // rcx
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // r15
  __int64 v55; // r12
  wchar_t *v56; // rbx
  void *v57; // r14
  __int64 v58; // rax
  int v59; // edx
  int v60; // r8d
  int v61; // eax
  int StringAllocW; // eax
  HRESULT v63; // eax
  __int64 v64; // rax
  void *v65; // rcx
  __int64 v66; // rax
  void *v67; // rcx
  _OWORD *v68; // rcx
  char *v69; // r8
  _OWORD *v70; // rax
  _OWORD *v71; // rdx
  __int64 v72; // r9
  unsigned __int64 v73; // r9
  HRESULT v74; // eax
  __int64 v75; // rdx
  void **v76; // [rsp+20h] [rbp-E0h]
  int v77; // [rsp+20h] [rbp-E0h]
  int v78; // [rsp+20h] [rbp-E0h]
  unsigned int v79; // [rsp+70h] [rbp-90h] BYREF
  int v80; // [rsp+74h] [rbp-8Ch]
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v82; // [rsp+80h] [rbp-80h]
  CCallerIdentity *v83; // [rsp+88h] [rbp-78h] BYREF
  const struct tagMatchingUpdate *v84; // [rsp+90h] [rbp-70h]
  unsigned __int8 *v85; // [rsp+98h] [rbp-68h] BYREF
  __int64 BooleanPropertyFromServerConfig; // [rsp+A0h] [rbp-60h]
  struct tagDSUpdateMetadata *v87; // [rsp+A8h] [rbp-58h]
  struct _GUID v88; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v89; // [rsp+C0h] [rbp-40h]
  wchar_t *v90; // [rsp+C8h] [rbp-38h]
  __int64 v91; // [rsp+D0h] [rbp-30h]
  __int64 v92; // [rsp+D8h] [rbp-28h]
  bool *v93; // [rsp+E0h] [rbp-20h]
  char v94; // [rsp+E8h] [rbp-18h]
  void **v95; // [rsp+F0h] [rbp-10h]
  unsigned int *v96; // [rsp+F8h] [rbp-8h]
  unsigned int *v97; // [rsp+100h] [rbp+0h]
  char v98; // [rsp+108h] [rbp+8h]
  bool v99; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v100[3]; // [rsp+114h] [rbp+14h] BYREF
  __int64 v101; // [rsp+120h] [rbp+20h] BYREF
  struct _FILETIME v102; // [rsp+128h] [rbp+28h] BYREF
  int v103; // [rsp+130h] [rbp+30h]
  int v104; // [rsp+134h] [rbp+34h]
  void *lpMem[2]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v106[24]; // [rsp+148h] [rbp+48h] BYREF
  int v107[44]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v102 = (struct _FILETIME)a1;
  v82 = a8;
  v15 = a10;
  v84 = a10;
  v87 = a12;
  if ( !a1 )
  {
    v16 = 643;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)0x80004003LL,
      (int)v76);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    v16 = 644;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v16 = 645;
    goto LABEL_3;
  }
  if ( !a9 )
  {
    ServiceObject = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x286,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)0x80070057LL,
      (int)v76);
    return (unsigned int)ServiceObject;
  }
  if ( !a10 )
  {
    v16 = 647;
    goto LABEL_3;
  }
  if ( !a12 )
  {
    v16 = 648;
    goto LABEL_3;
  }
  v101 = 0;
  *(_OWORD *)lpMem = 0;
  v19 = 0;
  v89 = 0;
  memset(v100, 0, sizeof(v100));
  v80 = 0;
  v20 = 0;
  v83 = 0;
  v79 = 0;
  v85 = 0;
  pv = 0;
  v95 = lpMem;
  v96 = &v100[1];
  v97 = v100;
  v98 = 1;
  for ( i = 0; i < a9; ++i )
  {
    if ( !(unsigned int)IsValidMatchingUpdate((const struct tagMatchingUpdate *)((char *)v15 + 232 * i), 1u) )
    {
      ServiceObject = -2147024809;
      v22 = 670;
      goto LABEL_125;
    }
    memset((char *)v87 + 640 * i, 0, 0x280u);
    v15 = v84;
  }
  v88 = *a4;
  ServiceObject = PrepareCallSecurity(*(struct CSusSecurityChecker **)&v102, a2, 5, &v88, a3, &v83, 0, 0, 0, 0, 0, 0, 0);
  if ( ServiceObject < 0 )
  {
    v22 = 687;
    goto LABEL_19;
  }
  v23 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&c_idSrvNone.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&c_idSrvNone.Data1 )
    v23 = *(_QWORD *)a4->Data4 - *(_QWORD *)c_idSrvNone.Data4;
  BooleanPropertyFromServerConfig = 0;
  if ( v23 )
  {
    ServiceObject = CAgentServiceManager::GetServiceObject(a3, a4, (struct CSusService **)&pv);
    if ( ServiceObject < 0 )
    {
      v22 = 694;
      goto LABEL_19;
    }
    v24 = (double *)pv;
    v25 = (RTL_SRWLOCK *)((char *)pv + 40);
    AcquireSRWLockShared((PSRWLOCK)pv + 5);
    v26 = CSusService::ValidateServerConfigState((CSusService *)v24);
    ServiceObject = 0;
    if ( v26 != -2145123267 )
      ServiceObject = v26;
    BooleanPropertyFromServerConfig = 0;
    if ( ServiceObject >= 0 )
    {
      if ( v24[48] >= 4.0 )
        BooleanPropertyFromServerConfig = CSusService::GetBooleanPropertyFromServerConfig(
                                            (CSusService *)v24,
                                            L"AutoAcceptEula",
                                            0);
      else
        BooleanPropertyFromServerConfig = (*(unsigned __int8 (__fastcall **)(double *))(*(_QWORD *)v24 + 24LL))(v24);
    }
    ReleaseSRWLockShared(v25);
    if ( ServiceObject < 0 )
    {
      v22 = 695;
LABEL_19:
      v20 = v83;
LABEL_125:
      v73 = (unsigned int)ServiceObject;
LABEL_126:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
        (const char *)v73,
        (int)v76);
      goto LABEL_127;
    }
  }
  v20 = v83;
  if ( v82 )
  {
    v79 = a7;
  }
  else
  {
    ServiceObject = GetSizeAndPtrFromSID(*((PSID *)v83 + 11), &v79, &v85);
    if ( ServiceObject < 0 )
    {
      v22 = 700;
      goto LABEL_125;
    }
    v82 = v85;
  }
  v27 = *(__int64 (__fastcall **)(struct ISusDatastore *, __int64 *))(*(_QWORD *)a2 + 24LL);
  if ( v101 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
    v101 = 0;
  }
  ServiceObject = v27(a2, &v101);
  if ( ServiceObject < 0 )
  {
    v22 = 708;
    goto LABEL_125;
  }
  v28 = v84;
  v29 = (_DWORD *)((char *)v84 + 40);
  v30 = a9;
  v31 = v100[0];
  do
  {
    v31 += *v29 + 1;
    v29 += 58;
    --v30;
  }
  while ( v30 );
  v100[0] = v31;
  if ( v31 )
  {
    v19 = SafeSusAllocArray(v31, 0x18u);
    v89 = v19;
    ServiceObject = v19 == 0 ? 0x8007000E : 0;
    if ( !v19 )
    {
      v22 = 715;
      goto LABEL_125;
    }
    v31 = v100[0];
  }
  v32 = v31;
  if ( *(_QWORD *)&v100[1] )
  {
    SusFree(*(void **)&v100[1]);
    *(_QWORD *)&v100[1] = 0;
  }
  if ( v32 )
  {
    *(_QWORD *)&v100[1] = SafeSusAllocArray(v32, 0x280u);
    ServiceObject = *(_QWORD *)&v100[1] == 0 ? 0x8007000E : 0;
    if ( !*(_QWORD *)&v100[1] )
    {
      v22 = 716;
      goto LABEL_125;
    }
  }
  ServiceObject = GetLangStrings(a11, (unsigned int *)lpMem + 1, (wchar_t ***)&lpMem[1], 4u);
  if ( ServiceObject < 0 )
  {
    v22 = 717;
    goto LABEL_125;
  }
  LODWORD(lpMem[0]) = 0;
  v33 = (char *)v28 + 40;
  v34 = a9;
  do
  {
    v35 = 0;
    if ( *(_DWORD *)v33 != -1 )
    {
      v36 = v80;
      do
      {
        v19[6 * v36] = a6 != 0 ? 3 : 0;
        if ( v35 )
        {
          v38 = *((_QWORD *)v33 + 1);
          v39 = *(_DWORD *)(v38 + 40LL * (v35 - 1) + 16);
          *(_OWORD *)&v19[6 * v36 + 1] = *(_OWORD *)(v38 + 40LL * (v35 - 1));
          v19[6 * v36 + 5] = v39;
        }
        else
        {
          v37 = *((_DWORD *)v33 - 6);
          *(_OWORD *)&v19[6 * v36 + 1] = *(_OWORD *)(v33 - 40);
          v19[6 * v36 + 5] = v37;
        }
        ++v36;
        ++v35;
      }
      while ( v35 < *(_DWORD *)v33 + 1 );
      v80 = v36;
    }
    v33 += 232;
    --v34;
  }
  while ( v34 );
  if ( a6
    && (*(_QWORD *)&c_idSrvNone.Data1 != *(_QWORD *)&a4->Data1 || *(_QWORD *)c_idSrvNone.Data4 != *(_QWORD *)a4->Data4) )
  {
    v40 = 0;
    v102 = 0;
    if ( v100[0] )
    {
      v40 = SafeSusAllocArray(v100[0], 0x2Cu);
      v102 = (struct _FILETIME)v40;
      ServiceObject = v40 == 0 ? 0x8007000E : 0;
      if ( !v40 )
      {
        v41 = (unsigned int)ServiceObject;
        v42 = 749;
        goto LABEL_72;
      }
    }
    LODWORD(v76) = (_DWORD)v19;
    v43 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, __int64))(*(_QWORD *)v101 + 376LL))(v101, a4, 2);
    ServiceObject = v43;
    if ( v43 < 0 )
    {
      v41 = (unsigned int)v43;
      v42 = 750;
LABEL_72:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
        (const char *)v41,
        (int)v76);
      if ( v40 )
        SusFree(v40);
      goto LABEL_127;
    }
    for ( j = 0; (unsigned int)j < v100[0]; j = (unsigned int)(j + 1) )
    {
      v45 = 3 * j;
      v19[2 * v45 + 5] = *((_DWORD *)v40 + 11 * (unsigned int)j + 4);
      v19[2 * v45] = 0;
    }
    if ( v40 )
      SusFree(v40);
  }
  v76 = lpMem;
  v46 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 *, _QWORD))(*(_QWORD *)v101 + 208LL))(
          v101,
          v79,
          v82,
          a5);
  v47 = v46;
  if ( v46 < 0 )
  {
    ServiceObject = -2145091577;
    if ( v46 != -2145091577 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FF,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
        (const char *)(unsigned int)v46,
        (int)lpMem);
      ServiceObject = v47;
    }
    goto LABEL_127;
  }
  v48 = 0;
  v80 = 0;
  v49 = 0;
  v79 = 0;
  v50 = a5 & 0xE03;
  LODWORD(v82) = v50;
  while ( 1 )
  {
    if ( v50 )
    {
      v51 = (char *)v28 + 232 * v49;
      if ( *((_DWORD *)v51 + 10) )
      {
        v52 = CombineBundleInformation(v51, *(_QWORD *)&v100[1] + 640 * v48);
        ServiceObject = v52;
        if ( v52 < 0 )
        {
          v73 = (unsigned int)v52;
          v22 = 776;
          goto LABEL_126;
        }
      }
    }
    v53 = v49;
    v92 = v49;
    v54 = 232LL * v49;
    v91 = v54;
    if ( *(_DWORD *)((char *)v28 + v54 + 112) == 1
      && (*(_QWORD *)&a4->Data1 != *(_QWORD *)&c_idSrvNone.Data1 || *(_QWORD *)a4->Data4 != *(_QWORD *)c_idSrvNone.Data4)
      && *(_DWORD *)((char *)v28 + v54 + 40)
      && (a5 & 0x100) != 0 )
    {
      break;
    }
LABEL_104:
    v68 = (_OWORD *)(*(_QWORD *)&v100[1] + 640LL * (unsigned int)v48);
    v69 = (char *)v87 + 640 * v53;
    v70 = v69;
    v71 = v68;
    v72 = 5;
    do
    {
      *v70 = *v71;
      v70[1] = v71[1];
      v70[2] = v71[2];
      v70[3] = v71[3];
      v70[4] = v71[4];
      v70[5] = v71[5];
      v70[6] = v71[6];
      v70 += 8;
      *(v70 - 1) = v71[7];
      v71 += 8;
      --v72;
    }
    while ( v72 );
    if ( BooleanPropertyFromServerConfig )
    {
      *((_DWORD *)v69 + 37) = 1;
      *((_DWORD *)v69 + 51) = 0;
    }
    memset(v68, 0, 0x280u);
    v48 = (unsigned int)(*(_DWORD *)((char *)v28 + v54 + 40) + v48 + 1);
    v80 = v48;
    v79 = ++v49;
    if ( v49 >= a9 )
    {
      ServiceObject = 0;
      goto LABEL_127;
    }
    v50 = (unsigned int)v82;
  }
  v55 = 640 * v48;
  if ( !*(_QWORD *)(640 * v48 + *(_QWORD *)&v100[1] + 440) )
  {
LABEL_103:
    v28 = v84;
    goto LABEL_104;
  }
  v56 = 0;
  v90 = 0;
  v57 = 0;
  pv = 0;
  memset(v106, 0, sizeof(v106));
  memset(v107, 0, 0xA8u);
  v102 = 0;
  v104 = 0;
  v103 = 0;
  *(_QWORD *)&v88.Data1 = v107;
  v88.Data4[0] = 1;
  v58 = *(_QWORD *)((char *)v84 + v54 + 48);
  *(_OWORD *)&v106[4] = *(_OWORD *)v58;
  *(_DWORD *)&v106[20] = *(_DWORD *)(v58 + 16);
  ServiceObject = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, __int64, _BYTE *))(*(_QWORD *)v101 + 384LL))(
                    v101,
                    a4,
                    1,
                    v106);
  if ( ServiceObject < 0 )
  {
    v75 = 799;
    goto LABEL_118;
  }
  v102 = *(struct _FILETIME *)&v107[4];
  LODWORD(v85) = *(_DWORD *)(v55 + *(_QWORD *)&v100[1] + 184) & 0xC0;
  v56 = (wchar_t *)SafeSusComAllocArray(0x1F4u, 2u);
  v90 = v56;
  ServiceObject = v56 == 0 ? 0x8007000E : 0;
  if ( !v56 )
  {
    v75 = 808;
LABEL_118:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v75,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)(unsigned int)ServiceObject,
      (int)v107);
    goto LABEL_119;
  }
  v99 = CoImpersonateClient() >= 0;
  v93 = &v99;
  v94 = 1;
  v61 = ConstructTitleForIDPParent(g_hInstance, v59, v60, &v102, (int)v85, v56, 0x1F4u);
  ServiceObject = v61;
  if ( v61 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33C,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)(unsigned int)v61,
      (int)v76);
    goto LABEL_113;
  }
  StringAllocW = LoadStringAllocW(g_hInstance, 388, LoadStringAllocator_CoTaskMemAlloc, (wchar_t **)&pv);
  ServiceObject = StringAllocW;
  if ( StringAllocW >= 0 )
  {
    v94 = 0;
    if ( v99 )
    {
      v63 = CoRevertToSelf();
      if ( v63 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x332,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
          (const char *)(unsigned int)v63,
          (int)v76);
    }
    v64 = *(_QWORD *)&v100[1];
    v65 = *(void **)(*(_QWORD *)(v55 + *(_QWORD *)&v100[1] + 440) + 8LL);
    if ( v65 )
    {
      CoTaskMemFree(v65);
      v64 = *(_QWORD *)&v100[1];
    }
    *(_QWORD *)(*(_QWORD *)(v55 + v64 + 440) + 8LL) = v56;
    v66 = *(_QWORD *)&v100[1];
    v67 = *(void **)(*(_QWORD *)(v55 + *(_QWORD *)&v100[1] + 440) + 16LL);
    if ( v67 )
    {
      CoTaskMemFree(v67);
      v66 = *(_QWORD *)&v100[1];
    }
    *(_QWORD *)(*(_QWORD *)(v55 + v66 + 440) + 16LL) = pv;
    v88.Data4[0] = 0;
    DsqFreeObject((struct tagDSDeployment *)v107, 1u);
    v49 = v79;
    LODWORD(v48) = v80;
    v54 = v91;
    v53 = v92;
    goto LABEL_103;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x93,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\LoadString.cpp",
    (const char *)(unsigned int)StringAllocW,
    (int)v76);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x340,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
    (const char *)(unsigned int)ServiceObject,
    v77);
  v57 = pv;
LABEL_113:
  if ( v99 )
  {
    v74 = CoRevertToSelf();
    if ( v74 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x332,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
        (const char *)(unsigned int)v74,
        v78);
  }
LABEL_119:
  DsqFreeObject((struct tagDSDeployment *)v107, 1u);
  if ( v57 )
    CoTaskMemFree(v57);
  if ( v56 )
    CoTaskMemFree(v56);
LABEL_127:
  SusFreePtrArray(lpMem[1], HIDWORD(lpMem[0]));
  DsqFreeObject(*(struct tagDSUpdateMetadata **)&v100[1], v100[0], 0x2FAFu, 1);
  if ( v20 )
  {
    CCallerIdentity::~CCallerIdentity(v20);
    operator delete(v20, (const struct std::nothrow_t *)0xA8);
  }
  if ( *(_QWORD *)&v100[1] )
  {
    SusFree(*(void **)&v100[1]);
    *(_QWORD *)&v100[1] = 0;
  }
  if ( v19 )
    SusFree(v19);
  if ( v101 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
  return (unsigned int)ServiceObject;
}

```

## disassembly

```asm
0x18003cac8  push    rbp
0x18003caca  push    rbx
0x18003cacb  push    rsi
0x18003cacc  push    rdi
0x18003cacd  push    r12
0x18003cacf  push    r13
0x18003cad1  push    r14
0x18003cad3  push    r15
0x18003cad5  lea     rbp, [rsp-128h]
0x18003cadd  sub     rsp, 228h
0x18003cae4  mov     rax, cs:__security_cookie
0x18003caeb  xor     rax, rsp
0x18003caee  mov     [rbp+160h+var_50], rax
0x18003caf5  mov     r13, r9
0x18003caf8  mov     r12, r8
0x18003cafb  mov     r14, rdx
0x18003cafe  mov     rax, rcx
0x18003cb01  mov     qword ptr [rbp+160h+var_138.dwLowDateTime], rcx
0x18003cb05  mov     rcx, [rbp+160h+arg_38]
0x18003cb0c  mov     [rbp+160h+var_1E0], rcx
0x18003cb10  mov     rdx, [rbp+160h+arg_48]
0x18003cb17  mov     [rbp+160h+var_1D0], rdx
0x18003cb1b  mov     rcx, [rbp+160h+arg_58]
0x18003cb22  mov     [rbp+160h+var_1B8], rcx
0x18003cb26  xor     r8d, r8d
0x18003cb29  test    rax, rax
0x18003cb2c  jnz     short loc_18003CB55
0x18003cb2e  mov     edx, 283h; void *
0x18003cb33  mov     ebx, 80004003h
0x18003cb38  mov     rcx, [rbp+168h]; this
0x18003cb3f  mov     r9d, ebx; char *
0x18003cb42  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18003cb49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb4e  mov     eax, ebx
0x18003cb50  jmp     loc_18003D63E
0x18003cb55  test    r14, r14
0x18003cb58  jnz     short loc_18003CB61
0x18003cb5a  mov     edx, 284h
0x18003cb5f  jmp     short loc_18003CB33
0x18003cb61  test    r12, r12
0x18003cb64  jnz     short loc_18003CB6D
0x18003cb66  mov     edx, 285h
0x18003cb6b  jmp     short loc_18003CB33
0x18003cb6d  cmp     [rbp+160h+arg_40], 1
0x18003cb74  jnb     short loc_18003CB9C
0x18003cb76  mov     rcx, [rbp+168h]; this
0x18003cb7d  mov     r15d, 80070057h
0x18003cb83  mov     r9d, r15d; char *
0x18003cb86  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18003cb8d  mov     edx, 286h; void *
0x18003cb92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb97  jmp     loc_18003D63B
0x18003cb9c  test    rdx, rdx
0x18003cb9f  jnz     short loc_18003CBA8
0x18003cba1  mov     edx, 287h
0x18003cba6  jmp     short loc_18003CB33
0x18003cba8  test    rcx, rcx
0x18003cbab  jnz     short loc_18003CBB7
0x18003cbad  mov     edx, 288h
0x18003cbb2  jmp     loc_18003CB33
0x18003cbb7  mov     [rbp+160h+var_140], r8
0x18003cbbb  xorps   xmm0, xmm0
0x18003cbbe  movups  xmmword ptr [rbp+160h+lpMem], xmm0
0x18003cbc2  mov     rdi, r8
0x18003cbc5  mov     [rbp+160h+var_1A0], r8
0x18003cbc9  mov     qword ptr [rbp+160h+var_14C+4], r8
0x18003cbcd  mov     dword ptr [rbp+160h+var_14C], r8d
0x18003cbd1  mov     [rsp+260h+var_1EC], r8d
0x18003cbd6  mov     rsi, r8
0x18003cbd9  mov     [rbp+160h+var_1D8], r8
0x18003cbdd  mov     [rsp+260h+var_1F0], r8d
0x18003cbe2  mov     [rbp+160h+var_1C8], r8
0x18003cbe6  mov     [rsp+260h+pv], r8
0x18003cbeb  lea     rax, [rbp+160h+lpMem]
0x18003cbef  mov     [rbp+160h+var_170], rax
0x18003cbf3  lea     rax, [rbp+160h+var_14C+4]
0x18003cbf7  mov     [rbp+160h+var_168], rax
0x18003cbfb  lea     rax, [rbp+160h+var_14C]
0x18003cbff  mov     [rbp+160h+var_160], rax
0x18003cc03  mov     [rbp+160h+var_158], 1
0x18003cc07  mov     ebx, r8d
0x18003cc0a  mov     r15d, ebx
0x18003cc0d  imul    rcx, r15, 0E8h
0x18003cc14  add     rcx, rdx; struct tagMatchingUpdate *
0x18003cc17  mov     edx, 1; unsigned int
0x18003cc1c  call    ?IsValidMatchingUpdate@@YAHAEBUtagMatchingUpdate@@K@Z; IsValidMatchingUpdate(tagMatchingUpdate const &,ulong)
0x18003cc21  test    eax, eax
0x18003cc23  jz      loc_18003D59F
0x18003cc29  lea     rcx, [r15+r15*4]
0x18003cc2d  shl     rcx, 7
0x18003cc31  add     rcx, [rbp+160h+var_1B8]; void *
0x18003cc35  xor     edx, edx; Val
0x18003cc37  mov     r8d, 280h; Size
0x18003cc3d  call    memset
0x18003cc42  inc     ebx
0x18003cc44  cmp     ebx, [rbp+160h+arg_40]
0x18003cc4a  mov     rdx, [rbp+160h+var_1D0]
0x18003cc4e  jb      short loc_18003CC0A
0x18003cc50  movups  xmm0, xmmword ptr [r13+0]
0x18003cc55  movdqu  xmmword ptr [rbp+160h+var_1B0.Data1], xmm0
0x18003cc5a  mov     [rsp+260h+var_200], 0; int *
0x18003cc63  mov     [rsp+260h+var_208], 0; int *
0x18003cc6c  mov     [rsp+260h+var_210], 0; struct tagMatchingUpdate *
0x18003cc75  mov     [rsp+260h+var_218], 0; unsigned int
0x18003cc7d  mov     [rsp+260h+var_220], 0; void **
0x18003cc86  mov     [rsp+260h+var_228], 0; int *
0x18003cc8f  mov     [rsp+260h+var_230], 0; struct IUnknown *
0x18003cc98  lea     rax, [rbp+160h+var_1D8]
0x18003cc9c  mov     [rsp+260h+var_238], rax; struct CCallerIdentity **
0x18003cca1  mov     [rsp+260h+var_240], r12; struct CAgentServiceManager *
0x18003cca6  lea     r9, [rbp+160h+var_1B0]; struct _GUID *
0x18003ccaa  mov     r8d, 5; unsigned int
0x18003ccb0  mov     rdx, r14; struct ISusDatastore *
0x18003ccb3  mov     rcx, qword ptr [rbp+160h+var_138.dwLowDateTime]; struct CSusSecurityChecker *
0x18003ccb7  call    ?PrepareCallSecurity@@YAJPEAVCSusSecurityChecker@@PEAUISusDatastore@@KU_GUID@@PEAVCAgentServiceManager@@PEAPEAVCCallerIdentity@@PEAUIUnknown@@PEAHPEAPEAXKQEBUtagMatchingUpdate@@66@Z; PrepareCallSecurity(CSusSecurityChecker *,ISusDatastore *,ulong,_GUID,CAgentServiceManager *,CCallerIdentity * *,IUnknown *,int *,void * *,ulong,tagMatchingUpdate const * const,int *,int *)
0x18003ccbc  mov     r15d, eax
0x18003ccbf  test    eax, eax
0x18003ccc1  jns     short loc_18003CCD1
0x18003ccc3  mov     edx, 2AFh
0x18003ccc8  mov     rsi, [rbp+160h+var_1D8]
0x18003cccc  jmp     loc_18003D5AA
0x18003ccd1  mov     rax, [r13+0]
0x18003ccd5  sub     rax, qword ptr cs:c_idSrvNone.Data1
0x18003ccdc  jnz     short loc_18003CCE9
0x18003ccde  mov     rax, [r13+8]
0x18003cce2  sub     rax, qword ptr cs:c_idSrvNone.Data4
0x18003cce9  mov     [rbp+160h+var_1C0], 0
0x18003ccf1  test    rax, rax
0x18003ccf4  jz      loc_18003CDA3
0x18003ccfa  lea     r8, [rsp+260h+pv]; struct CSusService **
0x18003ccff  mov     rdx, r13; struct _GUID *
0x18003cd02  mov     rcx, r12; this
0x18003cd05  call    ?GetServiceObject@CAgentServiceManager@@QEAAJAEBU_GUID@@PEAPEAVCSusService@@@Z; CAgentServiceManager::GetServiceObject(_GUID const &,CSusService * *)
0x18003cd0a  mov     r15d, eax
0x18003cd0d  test    eax, eax
0x18003cd0f  jns     short loc_18003CD18
0x18003cd11  mov     edx, 2B6h
0x18003cd16  jmp     short loc_18003CCC8
0x18003cd18  mov     rbx, [rsp+260h+pv]
0x18003cd1d  lea     rsi, [rbx+28h]
0x18003cd21  mov     rcx, rsi; SRWLock
0x18003cd24  call    cs:__imp_AcquireSRWLockShared
0x18003cd2a  mov     rcx, rbx; this
0x18003cd2d  call    ?ValidateServerConfigState@CSusService@@AEAAJXZ; CSusService::ValidateServerConfigState(void)
0x18003cd32  xor     r15d, r15d
0x18003cd35  cmp     eax, 8024043Dh
0x18003cd3a  cmovnz  r15d, eax
0x18003cd3e  mov     [rbp+160h+var_1C0], 0
0x18003cd46  test    r15d, r15d
0x18003cd49  js      short loc_18003CD8B
0x18003cd4b  movsd   xmm0, cs:__real@4010000000000000
0x18003cd53  mov     rcx, rbx; this
0x18003cd56  comisd  xmm0, qword ptr [rbx+180h]
0x18003cd5e  jbe     short loc_18003CD75
0x18003cd60  mov     rax, [rbx]
0x18003cd63  mov     rax, [rax+18h]
0x18003cd67  call    _guard_dispatch_icall
0x18003cd6c  movzx   ebx, al
0x18003cd6f  mov     [rbp+160h+var_1C0], rbx
0x18003cd73  jmp     short loc_18003CD8B
0x18003cd75  xor     r8d, r8d; bool
0x18003cd78  lea     rdx, aAutoaccepteula; "AutoAcceptEula"
0x18003cd7f  call    ?GetBooleanPropertyFromServerConfig@CSusService@@AEAA_NPEB_W_N@Z; CSusService::GetBooleanPropertyFromServerConfig(wchar_t const *,bool)
0x18003cd84  movzx   eax, al
0x18003cd87  mov     [rbp+160h+var_1C0], rax
0x18003cd8b  mov     rcx, rsi; SRWLock
0x18003cd8e  call    cs:__imp_ReleaseSRWLockShared
0x18003cd94  test    r15d, r15d
0x18003cd97  jns     short loc_18003CDA3
0x18003cd99  mov     edx, 2B7h
0x18003cd9e  jmp     loc_18003CCC8
0x18003cda3  mov     rsi, [rbp+160h+var_1D8]
0x18003cda7  cmp     [rbp+160h+var_1E0], 0
0x18003cdac  jnz     short loc_18003CDE3
0x18003cdae  lea     r8, [rbp+160h+var_1C8]; unsigned __int8 **
0x18003cdb2  lea     rdx, [rsp+260h+var_1F0]; unsigned int *
0x18003cdb7  mov     rcx, [rsi+58h]; pSid
0x18003cdbb  call    ?GetSizeAndPtrFromSID@@YAJQEAXPEAKPEAPEAE@Z; GetSizeAndPtrFromSID(void * const,ulong *,uchar * *)
0x18003cdc0  mov     r15d, eax
0x18003cdc3  test    eax, eax
0x18003cdc5  jns     short loc_18003CDD1
0x18003cdc7  mov     edx, 2BCh
0x18003cdcc  jmp     loc_18003D5AA
0x18003cdd1  mov     edx, [rsp+260h+var_1F0]
0x18003cdd5  mov     [rsp+260h+var_1F0], edx
0x18003cdd9  mov     rax, [rbp+160h+var_1C8]
0x18003cddd  mov     [rbp+160h+var_1E0], rax
0x18003cde1  jmp     short loc_18003CDED
0x18003cde3  mov     eax, [rbp+160h+arg_30]
0x18003cde9  mov     [rsp+260h+var_1F0], eax
0x18003cded  mov     rax, [r14]
0x18003cdf0  mov     rbx, [rax+18h]
0x18003cdf4  mov     rcx, [rbp+160h+var_140]
0x18003cdf8  test    rcx, rcx
0x18003cdfb  jz      short loc_18003CE11
0x18003cdfd  mov     rdx, [rcx]
0x18003ce00  mov     rax, [rdx+10h]
0x18003ce04  call    _guard_dispatch_icall
0x18003ce09  mov     [rbp+160h+var_140], 0
0x18003ce11  lea     rdx, [rbp+160h+var_140]
0x18003ce15  mov     rcx, r14
0x18003ce18  mov     rax, rbx
0x18003ce1b  call    _guard_dispatch_icall
0x18003ce20  mov     r15d, eax
0x18003ce23  test    eax, eax
0x18003ce25  jns     short loc_18003CE31
0x18003ce27  mov     edx, 2C4h
0x18003ce2c  jmp     loc_18003D5AA
0x18003ce31  mov     r12, [rbp+160h+var_1D0]
0x18003ce35  lea     rcx, [r12+28h]
0x18003ce3a  mov     r8d, [rbp+160h+arg_40]
0x18003ce41  mov     edx, dword ptr [rbp+160h+var_14C]
0x18003ce44  inc     edx
0x18003ce46  add     edx, [rcx]
0x18003ce48  lea     rcx, [rcx+0E8h]
0x18003ce4f  sub     r8, 1
0x18003ce53  jnz     short loc_18003CE44
0x18003ce55  mov     dword ptr [rbp+160h+var_14C], edx
0x18003ce58  mov     ecx, edx; unsigned __int64
0x18003ce5a  mov     r14d, 8007000Eh
0x18003ce60  test    edx, edx
0x18003ce62  jz      short loc_18003CE92
0x18003ce64  lea     edx, [r8+18h]; unsigned __int64
0x18003ce68  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18003ce6d  mov     rdi, rax
0x18003ce70  mov     [rbp+160h+var_1A0], rax
0x18003ce74  neg     rax
0x18003ce77  sbb     r15d, r15d
0x18003ce7a  not     r15d
0x18003ce7d  and     r15d, r14d
0x18003ce80  test    rdi, rdi
0x18003ce83  jnz     short loc_18003CE8F
0x18003ce85  mov     edx, 2CBh
0x18003ce8a  jmp     loc_18003D5AA
0x18003ce8f  mov     edx, dword ptr [rbp+160h+var_14C]
0x18003ce92  mov     ebx, edx
0x18003ce94  mov     rcx, qword ptr [rbp+160h+var_14C+4]; lpMem
0x18003ce98  test    rcx, rcx
0x18003ce9b  jz      short loc_18003CEAA
0x18003ce9d  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003cea2  mov     qword ptr [rbp+160h+var_14C+4], 0
0x18003ceaa  test    rbx, rbx
0x18003cead  jz      short loc_18003CEDE
0x18003ceaf  mov     edx, 280h; unsigned __int64
0x18003ceb4  mov     rcx, rbx; unsigned __int64
0x18003ceb7  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18003cebc  mov     qword ptr [rbp+160h+var_14C+4], rax
0x18003cec0  mov     rcx, rax
0x18003cec3  neg     rcx
0x18003cec6  sbb     r15d, r15d
0x18003cec9  not     r15d
0x18003cecc  and     r15d, r14d
0x18003cecf  test    rax, rax
0x18003ced2  jnz     short loc_18003CEDE
0x18003ced4  mov     edx, 2CCh
0x18003ced9  jmp     loc_18003D5AA
0x18003cede  mov     r9d, 4; unsigned int
0x18003cee4  lea     r8, [rbp+160h+lpMem+8]; wchar_t ***
0x18003cee8  lea     rdx, [rbp+160h+lpMem+4]; unsigned int *
0x18003ceec  mov     ecx, [rbp+160h+arg_50]; unsigned int
0x18003cef2  call    ?GetLangStrings@@YAJKPEAKPEAPEAPEA_WK@Z; GetLangStrings(ulong,ulong *,wchar_t * * *,ulong)
0x18003cef7  mov     r15d, eax
0x18003cefa  test    eax, eax
0x18003cefc  jns     short loc_18003CF08
0x18003cefe  mov     edx, 2CDh
0x18003cf03  jmp     loc_18003D5AA
0x18003cf08  mov     dword ptr [rbp+160h+lpMem], 0
0x18003cf0f  lea     r8, [r12+28h]
0x18003cf14  mov     ebx, [rbp+160h+arg_40]
0x18003cf1a  mov     r14d, [rbp+160h+arg_28]
0x18003cf21  xor     r9d, r9d
0x18003cf24  mov     eax, [r8]
0x18003cf27  add     eax, 1
0x18003cf2a  jz      short loc_18003CF97
0x18003cf2c  mov     eax, r14d
0x18003cf2f  neg     eax
0x18003cf31  sbb     r11d, r11d
0x18003cf34  and     r11d, 3
0x18003cf38  mov     r15d, [rsp+260h+var_1EC]
0x18003cf3d  mov     eax, r15d
0x18003cf40  lea     r10, [rax+rax*2]
0x18003cf44  mov     [rdi+r10*8], r11d
0x18003cf48  test    r9d, r9d
0x18003cf4b  jnz     short loc_18003CF63
0x18003cf4d  movups  xmm0, xmmword ptr [r8-28h]
0x18003cf52  mov     eax, [r8-18h]
0x18003cf56  movups  xmmword ptr [rdi+r10*8+4], xmm0
0x18003cf5c  mov     [rdi+r10*8+14h], eax
0x18003cf61  jmp     short loc_18003CF82
0x18003cf63  lea     eax, [r9-1]
0x18003cf67  lea     rdx, [rax+rax*4]
0x18003cf6b  mov     rax, [r8+8]
0x18003cf6f  movups  xmm0, xmmword ptr [rax+rdx*8]
0x18003cf73  mov     ecx, [rax+rdx*8+10h]
0x18003cf77  movups  xmmword ptr [rdi+r10*8+4], xmm0
0x18003cf7d  mov     [rdi+r10*8+14h], ecx
0x18003cf82  inc     r15d
0x18003cf85  inc     r9d
0x18003cf88  mov     eax, [r8]
0x18003cf8b  inc     eax
  ... truncated ...
```
