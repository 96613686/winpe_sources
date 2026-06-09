# GetCurrentContextParameters(AppInfo *,ushort * *,IMrtResourceManager * *,ushort * *,ushort * *)

- ea: `0x1802e118c`
- end: `0x1802e1555`
- name: `?GetCurrentContextParameters@@YAJPEAVAppInfo@@PEAPEAGPEAPEAUIMrtResourceManager@@11@Z`
- size: `969`
- prototype: `__int64 __fastcall(struct AppInfo *, unsigned __int16 **, struct IMrtResourceManager **, unsigned __int16 **, DWORD dwProcessId)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1802e0df0`
- `0x1802e1690`

## callees

- `0x18000b7e8`
- `0x180027ee4`
- `0x180036428`
- `0x180047224`
- `0x180047dd4`
- `0x18008e9d4`
- `0x18009f240`
- `0x1800ae2cc`
- `0x180127288`
- `0x180265edc`
- `0x1802e118c`
- `0x18036de98`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802e1245`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802e1245`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802e13b4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802e13e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802e13b4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802e13e9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1802e1234`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1802e1234`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x1802e132b`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x1802e136c`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x1802e132b`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x1802e136c`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageId` at `0x1802e12a8`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageId` at `0x1802e1301`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageId` at `0x1802e12a8`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageId` at `0x1802e1301`

## pseudocode

```c
__int64 __fastcall GetCurrentContextParameters(
        struct AppInfo *a1,
        unsigned __int16 **a2,
        struct IMrtResourceManager **a3,
        unsigned __int16 **a4,
        PWSTR *dwProcessId)
{
  PWSTR *v8; // r14
  PWSTR v9; // r15
  CDefaultUILangugageCache *v10; // rcx
  int CachedDefaultUILanguage; // edi
  HWND v12; // rcx
  HANDLE v13; // rsi
  unsigned __int16 **v14; // r8
  LONG PackageId; // eax
  void *v16; // rcx
  BYTE *v17; // rbx
  LONG v18; // eax
  LONG PackagePath; // eax
  int v20; // eax
  LONG v21; // eax
  HRESULT Instance; // eax
  unsigned __int16 *v23; // rsi
  struct IMrtResourceManager *v24; // rbx
  struct IPropertyStore *v25; // r8
  unsigned __int16 *v26; // rax
  BYTE *buffer; // [rsp+30h] [rbp-51h] BYREF
  HANDLE v29; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int16 *v30; // [rsp+40h] [rbp-41h] BYREF
  __int64 v31; // [rsp+48h] [rbp-39h]
  __int64 v32; // [rsp+50h] [rbp-31h]
  unsigned __int16 *v33; // [rsp+58h] [rbp-29h] BYREF
  __int64 v34; // [rsp+60h] [rbp-21h]
  __int64 v35; // [rsp+68h] [rbp-19h]
  PWSTR path; // [rsp+70h] [rbp-11h] BYREF
  __int64 v37; // [rsp+78h] [rbp-9h]
  __int64 v38; // [rsp+80h] [rbp-1h]
  __int16 v39; // [rsp+88h] [rbp+7h] BYREF
  PWSTR v40; // [rsp+90h] [rbp+Fh]
  BYTE *pathLength; // [rsp+F0h] [rbp+6Fh] BYREF
  TileUtils *ppv; // [rsp+F8h] [rbp+77h] BYREF

  *a2 = 0;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = dwProcessId;
  if ( dwProcessId )
    *dwProcessId = 0;
  v33 = 0;
  v34 = 0;
  v9 = 0;
  v35 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  path = 0;
  v37 = 0;
  v38 = 0;
  ppv = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
  v34 = -1;
  v35 = -1;
  v29 = 0;
  CachedDefaultUILanguage = CDefaultUILangugageCache::GetCachedDefaultUILanguage(v10, &v33);
  if ( CachedDefaultUILanguage >= 0 )
  {
    v12 = (HWND)*((_QWORD *)a1 + 3);
    LODWORD(dwProcessId) = 0;
    GetWindowThreadProcessId(v12, (LPDWORD)&dwProcessId);
    v13 = OpenProcess(0x1000u, 0, (DWORD)dwProcessId);
    CAutoHandle<void *>::~CAutoHandle<void *>(&v29);
    v29 = v13;
    if ( v13 || (CachedDefaultUILanguage = ResultFromKnownLastError(), CachedDefaultUILanguage >= 0) )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
      v31 = -1;
      v32 = -1;
      CachedDefaultUILanguage = CallerIdentity::GetPackageFullNameFromProcess(v13, &v30, v14);
      if ( CachedDefaultUILanguage >= 0 )
      {
        LODWORD(dwProcessId) = 0;
        PackageId = GetPackageId(v13, (UINT32 *)&dwProcessId, 0);
        CachedDefaultUILanguage = PackageId;
        if ( PackageId > 0 )
          CachedDefaultUILanguage = (unsigned __int16)PackageId | 0x80070000;
        if ( CachedDefaultUILanguage == -2147024774 )
        {
          if ( !(_DWORD)dwProcessId )
            goto LABEL_39;
          buffer = 0;
          CachedDefaultUILanguage = CTCoAllocPolicy::Alloc(v16, 1u, (unsigned int)dwProcessId, (void **)&buffer);
          if ( CachedDefaultUILanguage >= 0 )
          {
            v17 = buffer;
            v18 = GetPackageId(v13, (UINT32 *)&dwProcessId, buffer);
            CachedDefaultUILanguage = v18;
            if ( v18 > 0 )
              CachedDefaultUILanguage = (unsigned __int16)v18 | 0x80070000;
            if ( CachedDefaultUILanguage >= 0 )
            {
              LODWORD(pathLength) = 0;
              PackagePath = GetPackagePath((const PACKAGE_ID *)v17, 0, (UINT32 *)&pathLength, 0);
              CachedDefaultUILanguage = PackagePath;
              if ( PackagePath > 0 )
                CachedDefaultUILanguage = (unsigned __int16)PackagePath | 0x80070000;
              if ( CachedDefaultUILanguage == -2147024774 )
              {
                if ( (_DWORD)pathLength )
                {
                  v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                          &path,
                          (unsigned int)pathLength);
                  v9 = path;
                  CachedDefaultUILanguage = v20;
                  if ( v20 >= 0 )
                  {
                    v21 = GetPackagePath((const PACKAGE_ID *)v17, 0, (UINT32 *)&pathLength, path);
                    CachedDefaultUILanguage = v21;
                    if ( v21 > 0 )
                      CachedDefaultUILanguage = (unsigned __int16)v21 | 0x80070000;
                  }
                }
              }
            }
          }
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&buffer);
        }
        if ( CachedDefaultUILanguage >= 0 )
        {
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
          CachedDefaultUILanguage = CoCreateInstance(
                                      &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
                                      0,
                                      1u,
                                      &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
                                      (LPVOID *)&ppv);
          if ( CachedDefaultUILanguage >= 0 )
          {
            pathLength = 0;
            Instance = CoCreateInstance(
                         &CLSID_InMemoryPropertyStore,
                         0,
                         3u,
                         &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                         (LPVOID *)&pathLength);
            v23 = v30;
            CachedDefaultUILanguage = Instance;
            if ( Instance >= 0 )
            {
              v24 = (struct IMrtResourceManager *)pathLength;
              buffer = pathLength;
              if ( pathLength )
                (*(void (__fastcall **)(BYTE *))(*(_QWORD *)pathLength + 8LL))(pathLength);
              v40 = v9;
              v39 = 31;
              CachedDefaultUILanguage = (*(__int64 (__fastcall **)(struct IMrtResourceManager *, __int128 *, __int16 *))(*(_QWORD *)v24 + 48LL))(
                                          v24,
                                          &PKEY_AppUserModel_PackageInstallPath,
                                          &v39);
              if ( CachedDefaultUILanguage >= 0 )
              {
                v40 = v23;
                v39 = 31;
                CachedDefaultUILanguage = (*(__int64 (__fastcall **)(struct IMrtResourceManager *, __int128 *, __int16 *))(*(_QWORD *)v24 + 48LL))(
                                            v24,
                                            &PKEY_AppUserModel_PackageFullName,
                                            &v39);
                if ( CachedDefaultUILanguage >= 0 )
                  CachedDefaultUILanguage = TileUtils::InitializeMRTResourceManager(ppv, v24, v25);
              }
              DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)&buffer);
            }
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pathLength);
            if ( CachedDefaultUILanguage >= 0 )
            {
              v26 = v33;
              v33 = 0;
              v35 = 0;
              v34 = 0;
              *a2 = v26;
              *a3 = ppv;
              ppv = 0;
              if ( a4 )
              {
                v30 = 0;
                v32 = 0;
                v31 = 0;
                *a4 = v23;
              }
              if ( v8 )
              {
                path = 0;
                v38 = 0;
                v37 = 0;
                *v8 = v9;
              }
            }
          }
        }
      }
    }
  }
LABEL_39:
  CAutoHandle<void *>::~CAutoHandle<void *>(&v29);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&path);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
  return (unsigned int)CachedDefaultUILanguage;
}

```

## disassembly

```asm
0x1802e118c  mov     [rsp-8+arg_0], rbx
0x1802e1191  mov     [rsp-8+arg_8], rdx
0x1802e1196  push    rbp
0x1802e1197  push    rsi
0x1802e1198  push    rdi
0x1802e1199  push    r12
0x1802e119b  push    r13
0x1802e119d  push    r14
0x1802e119f  push    r15
0x1802e11a1  lea     rbp, [rsp-1Fh]
0x1802e11a6  sub     rsp, 0A0h
0x1802e11ad  xor     esi, esi
0x1802e11af  mov     r12, r9
0x1802e11b2  mov     [rdx], rsi
0x1802e11b5  mov     r13, r8
0x1802e11b8  mov     [r8], rsi
0x1802e11bb  mov     rbx, rcx
0x1802e11be  test    r9, r9
0x1802e11c1  jz      short loc_1802E11C6
0x1802e11c3  mov     [r9], rsi
0x1802e11c6  mov     r14, [rbp+4Fh+dwProcessId]
0x1802e11ca  test    r14, r14
0x1802e11cd  jz      short loc_1802E11D2
0x1802e11cf  mov     [r14], rsi
0x1802e11d2  lea     rcx, [rbp+4Fh+var_78]
0x1802e11d6  mov     [rbp+4Fh+var_78], rsi
0x1802e11da  mov     [rbp+4Fh+var_70], rsi
0x1802e11de  mov     r15, rsi
0x1802e11e1  mov     [rbp+4Fh+var_68], rsi
0x1802e11e5  mov     [rbp+4Fh+var_90], rsi
0x1802e11e9  mov     [rbp+4Fh+var_88], rsi
0x1802e11ed  mov     [rbp+4Fh+var_80], rsi
0x1802e11f1  mov     [rbp+4Fh+path], rsi
0x1802e11f5  mov     [rbp+4Fh+var_58], rsi
0x1802e11f9  mov     [rbp+4Fh+var_50], rsi
0x1802e11fd  mov     [rbp+4Fh+arg_18], rsi
0x1802e1201  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802e1206  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802e120a  lea     rdx, [rbp+4Fh+var_78]; unsigned __int16 **
0x1802e120e  mov     [rbp+4Fh+var_70], rax
0x1802e1212  mov     [rbp+4Fh+var_68], rax
0x1802e1216  call    ?GetCachedDefaultUILanguage@CDefaultUILangugageCache@@QEAAJPEAPEAG@Z; CDefaultUILangugageCache::GetCachedDefaultUILanguage(ushort * *)
0x1802e121b  mov     [rbp+4Fh+var_98], rsi
0x1802e121f  mov     edi, eax
0x1802e1221  test    eax, eax
0x1802e1223  js      loc_1802E150B
0x1802e1229  mov     rcx, [rbx+18h]; hWnd
0x1802e122d  lea     rdx, [rbp+4Fh+dwProcessId]; lpdwProcessId
0x1802e1231  mov     dword ptr [rbp+4Fh+dwProcessId], esi
0x1802e1234  call    cs:__imp_GetWindowThreadProcessId
0x1802e123a  mov     r8d, dword ptr [rbp+4Fh+dwProcessId]; dwProcessId
0x1802e123e  xor     edx, edx; bInheritHandle
0x1802e1240  mov     ecx, 1000h; dwDesiredAccess
0x1802e1245  call    cs:__imp_OpenProcess
0x1802e124b  lea     rcx, [rbp+4Fh+var_98]
0x1802e124f  mov     rsi, rax
0x1802e1252  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802e1257  mov     [rbp+4Fh+var_98], rsi
0x1802e125b  test    rsi, rsi
0x1802e125e  jnz     short loc_1802E126F
0x1802e1260  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802e1265  mov     edi, eax
0x1802e1267  test    eax, eax
0x1802e1269  js      loc_1802E150B
0x1802e126f  lea     rcx, [rbp+4Fh+var_90]
0x1802e1273  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802e1278  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802e127c  lea     rdx, [rbp+4Fh+var_90]; void *
0x1802e1280  mov     rcx, rsi; hProcess
0x1802e1283  mov     [rbp+4Fh+var_88], rax
0x1802e1287  mov     [rbp+4Fh+var_80], rax
0x1802e128b  call    ?GetPackageFullNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromProcess(void *,ushort * *)
0x1802e1290  mov     edi, eax
0x1802e1292  test    eax, eax
0x1802e1294  js      loc_1802E150B
0x1802e129a  xor     r8d, r8d; buffer
0x1802e129d  mov     dword ptr [rbp+4Fh+dwProcessId], r15d
0x1802e12a1  lea     rdx, [rbp+4Fh+dwProcessId]; bufferLength
0x1802e12a5  mov     rcx, rsi; hProcess
0x1802e12a8  call    cs:__imp_GetPackageId
0x1802e12ae  mov     edi, eax
0x1802e12b0  test    eax, eax
0x1802e12b2  jle     short loc_1802E12BD
0x1802e12b4  movzx   edi, ax
0x1802e12b7  or      edi, 80070000h
0x1802e12bd  cmp     edi, 8007007Ah
0x1802e12c3  jnz     loc_1802E1386
0x1802e12c9  mov     eax, dword ptr [rbp+4Fh+dwProcessId]
0x1802e12cc  test    eax, eax
0x1802e12ce  jz      loc_1802E150B
0x1802e12d4  mov     r8d, eax; unsigned __int64
0x1802e12d7  mov     [rbp+4Fh+buffer], r15
0x1802e12db  lea     r9, [rbp+4Fh+buffer]; void **
0x1802e12df  mov     edx, 1; unsigned int
0x1802e12e4  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1802e12e9  mov     edi, eax
0x1802e12eb  test    eax, eax
0x1802e12ed  js      loc_1802E137D
0x1802e12f3  mov     rbx, [rbp+4Fh+buffer]
0x1802e12f7  lea     rdx, [rbp+4Fh+dwProcessId]; bufferLength
0x1802e12fb  mov     r8, rbx; buffer
0x1802e12fe  mov     rcx, rsi; hProcess
0x1802e1301  call    cs:__imp_GetPackageId
0x1802e1307  mov     edi, eax
0x1802e1309  mov     esi, 80070000h
0x1802e130e  test    eax, eax
0x1802e1310  jle     short loc_1802E1317
0x1802e1312  movzx   edi, ax
0x1802e1315  or      edi, esi
0x1802e1317  test    edi, edi
0x1802e1319  js      short loc_1802E137D
0x1802e131b  xor     r9d, r9d; path
0x1802e131e  mov     dword ptr [rbp+4Fh+pathLength], r15d
0x1802e1322  lea     r8, [rbp+4Fh+pathLength]; pathLength
0x1802e1326  xor     edx, edx; reserved
0x1802e1328  mov     rcx, rbx; packageId
0x1802e132b  call    cs:__imp_GetPackagePath
0x1802e1331  mov     edi, eax
0x1802e1333  test    eax, eax
0x1802e1335  jle     short loc_1802E133C
0x1802e1337  movzx   edi, ax
0x1802e133a  or      edi, esi
0x1802e133c  cmp     edi, 8007007Ah
0x1802e1342  jnz     short loc_1802E137D
0x1802e1344  mov     eax, dword ptr [rbp+4Fh+pathLength]
0x1802e1347  test    eax, eax
0x1802e1349  jz      short loc_1802E137D
0x1802e134b  mov     edx, eax
0x1802e134d  lea     rcx, [rbp+4Fh+path]
0x1802e1351  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1802e1356  mov     r15, [rbp+4Fh+path]
0x1802e135a  mov     edi, eax
0x1802e135c  test    eax, eax
0x1802e135e  js      short loc_1802E137D
0x1802e1360  mov     r9, r15; path
0x1802e1363  lea     r8, [rbp+4Fh+pathLength]; pathLength
0x1802e1367  xor     edx, edx; reserved
0x1802e1369  mov     rcx, rbx; packageId
0x1802e136c  call    cs:__imp_GetPackagePath
0x1802e1372  mov     edi, eax
0x1802e1374  test    eax, eax
0x1802e1376  jle     short loc_1802E137D
0x1802e1378  movzx   edi, ax
0x1802e137b  or      edi, esi
0x1802e137d  lea     rcx, [rbp+4Fh+buffer]
0x1802e1381  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1802e1386  test    edi, edi
0x1802e1388  js      loc_1802E150B
0x1802e138e  lea     rcx, [rbp+4Fh+arg_18]
0x1802e1392  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e1397  xor     edx, edx; pUnkOuter
0x1802e1399  lea     rax, [rbp+4Fh+arg_18]
0x1802e139d  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x1802e13a4  mov     [rsp+0D0h+ppv], rax; ppv
0x1802e13a9  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x1802e13b0  lea     r8d, [rdx+1]; dwClsContext
0x1802e13b4  call    cs:__imp_CoCreateInstance
0x1802e13ba  mov     edi, eax
0x1802e13bc  test    eax, eax
0x1802e13be  js      loc_1802E150B
0x1802e13c4  xor     edx, edx; pUnkOuter
0x1802e13c6  mov     [rbp+4Fh+pathLength], 0
0x1802e13ce  lea     rax, [rbp+4Fh+pathLength]
0x1802e13d2  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1802e13d9  mov     [rsp+0D0h+ppv], rax; ppv
0x1802e13de  lea     rcx, CLSID_InMemoryPropertyStore; rclsid
0x1802e13e5  lea     r8d, [rdx+3]; dwClsContext
0x1802e13e9  call    cs:__imp_CoCreateInstance
0x1802e13ef  mov     rsi, [rbp+4Fh+var_90]
0x1802e13f3  mov     edi, eax
0x1802e13f5  test    eax, eax
0x1802e13f7  js      loc_1802E148A
0x1802e13fd  mov     rbx, [rbp+4Fh+pathLength]
0x1802e1401  mov     [rbp+4Fh+buffer], rbx
0x1802e1405  test    rbx, rbx
0x1802e1408  jz      short loc_1802E1419
0x1802e140a  mov     rax, [rbx]
0x1802e140d  mov     rcx, rbx
0x1802e1410  mov     rax, [rax+8]
0x1802e1414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e1419  mov     eax, 1Fh
0x1802e141e  mov     [rbp+4Fh+var_40], r15
0x1802e1422  mov     [rbp+4Fh+var_48], ax
0x1802e1426  lea     r8, [rbp+4Fh+var_48]
0x1802e142a  mov     rax, [rbx]
0x1802e142d  lea     rdx, PKEY_AppUserModel_PackageInstallPath
0x1802e1434  mov     rcx, rbx
0x1802e1437  mov     rax, [rax+30h]
0x1802e143b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e1440  mov     edi, eax
0x1802e1442  test    eax, eax
0x1802e1444  js      short loc_1802E1481
0x1802e1446  mov     eax, 1Fh
0x1802e144b  mov     [rbp+4Fh+var_40], rsi
0x1802e144f  mov     [rbp+4Fh+var_48], ax
0x1802e1453  lea     r8, [rbp+4Fh+var_48]
0x1802e1457  mov     rax, [rbx]
0x1802e145a  lea     rdx, PKEY_AppUserModel_PackageFullName
0x1802e1461  mov     rcx, rbx
0x1802e1464  mov     rax, [rax+30h]
0x1802e1468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e146d  mov     edi, eax
0x1802e146f  test    eax, eax
0x1802e1471  js      short loc_1802E1481
0x1802e1473  mov     rcx, [rbp+4Fh+arg_18]; this
0x1802e1477  mov     rdx, rbx; struct IMrtResourceManager *
0x1802e147a  call    ?InitializeMRTResourceManager@TileUtils@@YAJPEAUIMrtResourceManager@@PEAUIPropertyStore@@@Z; TileUtils::InitializeMRTResourceManager(IMrtResourceManager *,IPropertyStore *)
0x1802e147f  mov     edi, eax
0x1802e1481  lea     rcx, [rbp+4Fh+buffer]; this
0x1802e1485  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x1802e148a  lea     rcx, [rbp+4Fh+pathLength]
0x1802e148e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e1493  test    edi, edi
0x1802e1495  js      short loc_1802E150B
0x1802e1497  mov     rax, [rbp+4Fh+var_78]
0x1802e149b  mov     rcx, [rbp+4Fh+arg_8]
0x1802e149f  mov     [rbp+4Fh+var_78], 0
0x1802e14a7  mov     [rbp+4Fh+var_68], 0
0x1802e14af  mov     [rbp+4Fh+var_70], 0
0x1802e14b7  mov     [rcx], rax
0x1802e14ba  mov     rax, [rbp+4Fh+arg_18]
0x1802e14be  mov     [r13+0], rax
0x1802e14c2  mov     [rbp+4Fh+arg_18], 0
0x1802e14ca  test    r12, r12
0x1802e14cd  jz      short loc_1802E14EB
0x1802e14cf  mov     [rbp+4Fh+var_90], 0
0x1802e14d7  mov     [rbp+4Fh+var_80], 0
0x1802e14df  mov     [rbp+4Fh+var_88], 0
0x1802e14e7  mov     [r12], rsi
0x1802e14eb  test    r14, r14
0x1802e14ee  jz      short loc_1802E150B
0x1802e14f0  mov     [rbp+4Fh+path], 0
0x1802e14f8  mov     [rbp+4Fh+var_50], 0
0x1802e1500  mov     [rbp+4Fh+var_58], 0
0x1802e1508  mov     [r14], r15
0x1802e150b  lea     rcx, [rbp+4Fh+var_98]
0x1802e150f  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802e1514  lea     rcx, [rbp+4Fh+arg_18]
0x1802e1518  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802e151d  lea     rcx, [rbp+4Fh+path]
0x1802e1521  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802e1526  lea     rcx, [rbp+4Fh+var_90]
0x1802e152a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802e152f  lea     rcx, [rbp+4Fh+var_78]
0x1802e1533  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802e1538  mov     rbx, [rsp+0D0h+arg_0]
0x1802e1540  mov     eax, edi
0x1802e1542  add     rsp, 0A0h
0x1802e1549  pop     r15
0x1802e154b  pop     r14
0x1802e154d  pop     r13
0x1802e154f  pop     r12
0x1802e1551  pop     rdi
0x1802e1552  pop     rsi
0x1802e1553  pop     rbp
0x1802e1554  retn
```
