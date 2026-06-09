# CSdBackupImpl::_RefreshBackupSpaceUsed(void)

- ea: `0x18001e604`
- end: `0x18001ec0f`
- name: `?_RefreshBackupSpaceUsed@CSdBackupImpl@@AEAAJXZ`
- size: `1547`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003dee0`

## callees

- `0x180003430`
- `0x180003444`
- `0x18001e604`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180070a7c`
- `0x180085a30`
- `0x180088640`
- `0x18008f5d0`
- `0x180092ebc`
- `0x180095164`
- `0x180096f00`
- `0x18009a378`
- `0x18009ae34`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001e7c5`
- `msvcrt!_wcsicmp` at `0x18001e7c5`
- `KERNEL32!CreateFileW` at `0x18001e844`
- `KERNEL32!CreateFileW` at `0x18001e844`
- `KERNEL32!CloseHandle` at `0x18001eb8a`
- `KERNEL32!CloseHandle` at `0x18001eb8a`
- `KERNEL32!GetComputerNameW` at `0x18001e6c3`
- `KERNEL32!GetComputerNameW` at `0x18001e6c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e93f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ea66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ebaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ebc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e93f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ea66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ebaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ebc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ea92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ea92`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e983`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e983`
- `ole32!CoTaskMemFree` at `0x18001eb6a`
- `ole32!CoTaskMemFree` at `0x18001eb6a`
- `ole32!CoCreateInstance` at `0x18001e713`
- `ole32!CoCreateInstance` at `0x18001e713`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSdBackupImpl::_RefreshBackupSpaceUsed(CSdBackupImpl *this)
{
  __int64 FileW; // rbx
  unsigned __int64 v3; // r12
  __int64 v4; // rcx
  int LastFailureAsHRESULT; // edi
  __int16 v6; // ax
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // rsi
  unsigned int v9; // edi
  char *v10; // rcx
  __int64 v11; // r14
  int v12; // eax
  unsigned __int64 *v13; // r8
  unsigned __int64 *v14; // r9
  unsigned __int64 v15; // r14
  LSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // r9d
  unsigned __int64 *v20; // r9
  LSTATUS v21; // eax
  int v22; // edx
  int v23; // r8d
  int v24; // r9d
  char *v25; // rdx
  unsigned int i; // edi
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *hTemplateFilea; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *phkResult; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *phkResulta; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *lpdwDisposition; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *lpdwDispositiona; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v34; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v35; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v36; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v37; // [rsp+50h] [rbp-B0h]
  unsigned int v38; // [rsp+60h] [rbp-A0h] BYREF
  HKEY KeyHandle; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+78h] [rbp-88h] BYREF
  __int16 v42; // [rsp+7Ch] [rbp-84h]
  __int16 v43; // [rsp+7Eh] [rbp-82h]
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp-40h] BYREF
  DWORD nSize; // [rsp+C8h] [rbp-38h] BYREF
  DWORD dwDisposition; // [rsp+CCh] [rbp-34h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v50; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v51; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v52; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v53[2]; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR Buffer[16]; // [rsp+108h] [rbp+8h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v41, "CSdBackupImpl::_RefreshBackupSpaceUsed", 5278, 1);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&ppv);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(v53);
  hKey = 0;
  KeyHandle = 0;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  FileW = -1;
  v53[1] = -1;
  dwDisposition = 0;
  memset(Buffer, 0, sizeof(Buffer));
  nSize = 16;
  v3 = 0;
  v50 = 0;
  v45 = 0;
  v38 = 0;
  pv = 0;
  v51 = 0;
  v52 = 0;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v4);
    v41 = LastFailureAsHRESULT;
    v6 = 5303;
LABEL_3:
    v43 = v6;
    goto LABEL_40;
  }
  v41 = 0;
  v42 = 5303;
  LastFailureAsHRESULT = CoCreateInstance(&CLSID_SdEngine2, 0, 1u, &IID_ISdCommon2, &ppv);
  v41 = LastFailureAsHRESULT;
  v6 = 5305;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5305;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, _QWORD *))(*(_QWORD *)ppv + 24LL))(
                           ppv,
                           9,
                           &IID_IUnknown,
                           v53);
  v41 = LastFailureAsHRESULT;
  v6 = 5306;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5306;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned int *, LPVOID *))(*(_QWORD *)ppv + 40LL))(
                           ppv,
                           *((_QWORD *)this + 48),
                           &v38,
                           &pv);
  v41 = LastFailureAsHRESULT;
  v6 = 5308;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v7 = 0;
  v8 = 0;
  v42 = 5308;
  v9 = 0;
  if ( v38 )
  {
    v10 = (char *)pv;
    do
    {
      v11 = 48LL * v9;
      v7 += *(_QWORD *)&v10[v11 + 40];
      v12 = _wcsicmp(*(const wchar_t **)&v10[v11 + 8], Buffer);
      v10 = (char *)pv;
      if ( !v12 )
        v8 += *(_QWORD *)((char *)pv + v11 + 40);
      ++v9;
    }
    while ( v9 < v38 );
  }
  LastFailureAsHRESULT = CBsString::SetPath(
                           (CBsString *)lpFileName,
                           *((const unsigned __int16 **)this + 48),
                           L"WindowsImageBackup",
                           Buffer,
                           0,
                           0,
                           hTemplateFile,
                           phkResult,
                           lpdwDisposition,
                           v34,
                           v36);
  v41 = LastFailureAsHRESULT;
  v6 = 5323;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5323;
  FileW = (__int64)CreateFileW(lpFileName[0], 0x1000A0u, 3u, 0, 3u, 0x2000000u, 0);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( *((_DWORD *)this + 108) != 7 )
    {
      LastFailureAsHRESULT = SdGetSnapshotDiffArea(*((const unsigned __int16 **)this + 48), &v50, v13, v14);
      v41 = LastFailureAsHRESULT;
      v6 = 5336;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_3;
      v42 = 5336;
      v3 = v50;
    }
    LastFailureAsHRESULT = SxFindDirSizeRecursive(lpFileName[0], &v45);
    v41 = LastFailureAsHRESULT;
    v6 = 5339;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v42 = 5339;
    LastFailureAsHRESULT = CBsString::SetPath(
                             (CBsString *)lpFileName,
                             *((const unsigned __int16 **)this + 48),
                             L"WindowsImageBackup",
                             0,
                             0,
                             0,
                             hTemplateFilea,
                             phkResulta,
                             lpdwDispositiona,
                             v35,
                             v37);
    v41 = LastFailureAsHRESULT;
    v6 = 5345;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v15 = v3 + v45;
    v42 = 5345;
    LastFailureAsHRESULT = SxFindDirSizeRecursive(lpFileName[0], &v45);
    v41 = LastFailureAsHRESULT;
    if ( LastFailureAsHRESULT < 0 )
    {
      v43 = 5346;
      goto LABEL_40;
    }
    v8 += v15;
    v42 = 5346;
    v7 += v45;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v16 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\Status",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &hKey,
          &dwDisposition);
  LastFailureAsHRESULT = v16;
  if ( v16 > 0 )
    LastFailureAsHRESULT = (unsigned __int16)v16 | 0x80070000;
  v41 = LastFailureAsHRESULT;
  v6 = 5359;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5359;
  LastFailureAsHRESULT = SetRegKeyVirtualization(hKey, v17, v18, v19);
  v41 = LastFailureAsHRESULT;
  v6 = 5360;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5360;
  LastFailureAsHRESULT = SxRegWriteULONGLONG(hKey, L"BackupSpaceUsed", v7);
  v41 = LastFailureAsHRESULT;
  v6 = 5362;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5362;
  LastFailureAsHRESULT = SxRegWriteULONGLONG(hKey, L"LocalBackupSpaceUsed", v8);
  v41 = LastFailureAsHRESULT;
  v6 = 5363;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5363;
  LastFailureAsHRESULT = SxQueryVolumeSpace(*((const unsigned __int16 **)this + 48), &v52, &v51, v20);
  v41 = LastFailureAsHRESULT;
  v6 = 5366;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5366;
  if ( (unsigned __int64)KeyHandle - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(KeyHandle);
    KeyHandle = 0;
  }
  v21 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\ScheduleParams\\TargetDevice",
          0,
          0x2001Fu,
          &KeyHandle);
  LastFailureAsHRESULT = v21;
  if ( v21 > 0 )
    LastFailureAsHRESULT = (unsigned __int16)v21 | 0x80070000;
  v41 = LastFailureAsHRESULT;
  v6 = 5368;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5368;
  LastFailureAsHRESULT = SetRegKeyVirtualization(KeyHandle, v22, v23, v24);
  v41 = LastFailureAsHRESULT;
  v6 = 5369;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5369;
  LastFailureAsHRESULT = SxRegWriteULONGLONG(KeyHandle, L"TotalSize", v51);
  v41 = LastFailureAsHRESULT;
  v6 = 5371;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5371;
  LastFailureAsHRESULT = SxRegWriteULONGLONG(KeyHandle, L"Freespace", v52);
  v41 = LastFailureAsHRESULT;
  v6 = 5372;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v42 = 5372;
LABEL_40:
  v25 = (char *)pv;
  if ( pv )
  {
    for ( i = 0; i < v38; v25 = (char *)pv )
      CleanupBackupsetLocationProp((struct _SD_BACKUPSET_LOCATION_PROP *)&v25[48 * i++]);
    CoTaskMemFree(v25);
    pv = 0;
    LastFailureAsHRESULT = v41;
  }
  v38 = 0;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)KeyHandle - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(KeyHandle);
    KeyHandle = 0;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)v53);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v41);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001e604  push    rbp
0x18001e606  push    rbx
0x18001e607  push    rsi
0x18001e608  push    rdi
0x18001e609  push    r12
0x18001e60b  push    r13
0x18001e60d  push    r14
0x18001e60f  push    r15
0x18001e611  lea     rbp, [rsp-38h]
0x18001e616  sub     rsp, 138h
0x18001e61d  mov     rax, cs:__security_cookie
0x18001e624  xor     rax, rsp
0x18001e627  mov     [rbp+70h+var_48], rax
0x18001e62b  mov     r13, rcx
0x18001e62e  mov     r9d, 1; unsigned __int16
0x18001e634  mov     r8d, 149Eh; unsigned __int16
0x18001e63a  lea     rdx, aCsdbackupimplR_0; "CSdBackupImpl::_RefreshBackupSpaceUsed"
0x18001e641  lea     rcx, [rsp+170h+var_F8]; this
0x18001e646  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e64b  nop
0x18001e64c  lea     rcx, [rbp+70h+var_B0]; void *
0x18001e650  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18001e655  nop
0x18001e656  lea     rcx, [rbp+70h+var_78]; void *
0x18001e65a  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18001e65f  nop
0x18001e660  xor     r14d, r14d
0x18001e663  mov     [rsp+170h+hKey], r14
0x18001e668  mov     [rsp+170h+KeyHandle], r14
0x18001e66d  lea     rax, qword_1800E8530
0x18001e674  mov     [rbp+70h+lpFileName], rax
0x18001e678  mov     [rbp+70h+var_98], r14
0x18001e67c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001e680  mov     [rbp+70h+var_70], rbx
0x18001e684  mov     [rbp+70h+dwDisposition], r14d
0x18001e688  mov     [rbp+70h+Buffer], r14w
0x18001e68d  xorps   xmm0, xmm0
0x18001e690  movups  xmmword ptr [rbp+70h+var_66], xmm0
0x18001e694  movups  xmmword ptr [rbp+70h+var_66+0Eh], xmm0
0x18001e698  mov     [rbp+70h+nSize], 10h
0x18001e69f  mov     r12d, r14d
0x18001e6a2  mov     [rbp+70h+var_90], r14
0x18001e6a6  mov     [rbp+70h+var_B8], r14
0x18001e6aa  mov     [rsp+170h+var_110], r14d
0x18001e6af  mov     [rbp+70h+pv], r14
0x18001e6b3  mov     [rbp+70h+var_88], r14
0x18001e6b7  mov     [rbp+70h+var_80], r14
0x18001e6bb  lea     rdx, [rbp+70h+nSize]; nSize
0x18001e6bf  lea     rcx, [rbp+70h+Buffer]; lpBuffer
0x18001e6c3  call    cs:__imp_GetComputerNameW
0x18001e6c9  test    eax, eax
0x18001e6cb  jnz     short loc_18001E6E7
0x18001e6cd  call    GetLastFailureAsHRESULT
0x18001e6d2  mov     edi, eax
0x18001e6d4  mov     [rsp+170h+var_F8], eax
0x18001e6d8  mov     eax, 14B7h
0x18001e6dd  mov     [rsp+170h+var_F2], ax
0x18001e6e2  jmp     loc_18001EB36
0x18001e6e7  mov     [rsp+170h+var_F8], r14d
0x18001e6ec  mov     eax, 14B7h
0x18001e6f1  mov     [rsp+170h+var_F4], ax
0x18001e6f6  lea     rax, [rbp+70h+var_B0]
0x18001e6fa  mov     [rsp+170h+ppv], rax; ppv
0x18001e6ff  lea     r9, IID_ISdCommon2; riid
0x18001e706  xor     edx, edx; pUnkOuter
0x18001e708  lea     r8d, [rdx+1]; dwClsContext
0x18001e70c  lea     rcx, CLSID_SdEngine2; rclsid
0x18001e713  call    cs:__imp_CoCreateInstance
0x18001e719  mov     edi, eax
0x18001e71b  mov     [rsp+170h+var_F8], eax
0x18001e71f  test    eax, eax
0x18001e721  mov     eax, 14B9h
0x18001e726  js      short loc_18001E6DD
0x18001e728  mov     [rsp+170h+var_F4], ax
0x18001e72d  mov     rcx, [rbp+70h+var_B0]
0x18001e731  mov     rax, [rcx]
0x18001e734  lea     r9, [rbp+70h+var_78]
0x18001e738  lea     r8, IID_IUnknown
0x18001e73f  mov     edx, 9
0x18001e744  mov     rax, [rax+18h]
0x18001e748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e74d  mov     edi, eax
0x18001e74f  mov     [rsp+170h+var_F8], eax
0x18001e753  test    eax, eax
0x18001e755  mov     eax, 14BAh
0x18001e75a  js      short loc_18001E6DD
0x18001e75c  mov     [rsp+170h+var_F4], ax
0x18001e761  mov     rcx, [rbp+70h+var_B0]
0x18001e765  mov     rax, [rcx]
0x18001e768  lea     r9, [rbp+70h+pv]
0x18001e76c  lea     r8, [rsp+170h+var_110]
0x18001e771  mov     rdx, [r13+180h]
0x18001e778  mov     rax, [rax+28h]
0x18001e77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e781  mov     edi, eax
0x18001e783  mov     [rsp+170h+var_F8], eax
0x18001e787  test    eax, eax
0x18001e789  mov     eax, 14BCh
0x18001e78e  js      loc_18001E6DD
0x18001e794  mov     r15, r14
0x18001e797  mov     rsi, r14
0x18001e79a  mov     [rsp+170h+var_F4], ax
0x18001e79f  mov     edi, r14d
0x18001e7a2  cmp     [rsp+170h+var_110], r14d
0x18001e7a7  jbe     short loc_18001E7E3
0x18001e7a9  mov     rcx, [rbp+70h+pv]
0x18001e7ad  mov     eax, edi
0x18001e7af  lea     r14, [rax+rax*2]
0x18001e7b3  shl     r14, 4
0x18001e7b7  add     r15, [r14+rcx+28h]
0x18001e7bc  lea     rdx, [rbp+70h+Buffer]; String2
0x18001e7c0  mov     rcx, [r14+rcx+8]; String1
0x18001e7c5  call    cs:__imp__wcsicmp
0x18001e7cb  mov     rcx, [rbp+70h+pv]
0x18001e7cf  test    eax, eax
0x18001e7d1  jnz     short loc_18001E7D8
0x18001e7d3  add     rsi, [r14+rcx+28h]
0x18001e7d8  inc     edi
0x18001e7da  cmp     edi, [rsp+170h+var_110]
0x18001e7de  jb      short loc_18001E7AD
0x18001e7e0  xor     r14d, r14d
0x18001e7e3  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], r14; unsigned __int16 *
0x18001e7e8  mov     [rsp+170h+ppv], r14; unsigned __int16 *
0x18001e7ed  lea     r9, [rbp+70h+Buffer]; unsigned __int16 *
0x18001e7f1  lea     r8, aWindowsimageba; "WindowsImageBackup"
0x18001e7f8  mov     rdx, [r13+180h]; unsigned __int16 *
0x18001e7ff  lea     rcx, [rbp+70h+lpFileName]; this
0x18001e803  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001e808  mov     edi, eax
0x18001e80a  mov     [rsp+170h+var_F8], eax
0x18001e80e  test    eax, eax
0x18001e810  mov     eax, 14CBh
0x18001e815  js      loc_18001E6DD
0x18001e81b  mov     [rsp+170h+var_F4], ax
0x18001e820  mov     [rsp+170h+hTemplateFile], r14; unsigned __int16 *
0x18001e825  mov     [rsp+170h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18001e82d  mov     r8d, 3; dwShareMode
0x18001e833  mov     dword ptr [rsp+170h+ppv], r8d; dwCreationDisposition
0x18001e838  xor     r9d, r9d; lpSecurityAttributes
0x18001e83b  mov     edx, 1000A0h; dwDesiredAccess
0x18001e840  mov     rcx, [rbp+70h+lpFileName]; lpFileName
0x18001e844  call    cs:__imp_CreateFileW
0x18001e84a  mov     rbx, rax
0x18001e84d  dec     rax
0x18001e850  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e854  ja      loc_18001E930
0x18001e85a  cmp     dword ptr [r13+1B0h], 7
0x18001e862  jz      short loc_18001E890
0x18001e864  lea     rdx, [rbp+70h+var_90]; unsigned __int64 *
0x18001e868  mov     rcx, [r13+180h]; unsigned __int16 *
0x18001e86f  call    ?SdGetSnapshotDiffArea@@YAJPEBGPEA_K11@Z; SdGetSnapshotDiffArea(ushort const *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x18001e874  mov     edi, eax
0x18001e876  mov     [rsp+170h+var_F8], eax
0x18001e87a  test    eax, eax
0x18001e87c  mov     eax, 14D8h
0x18001e881  js      loc_18001E6DD
0x18001e887  mov     [rsp+170h+var_F4], ax
0x18001e88c  mov     r12, [rbp+70h+var_90]
0x18001e890  lea     rdx, [rbp+70h+var_B8]; unsigned __int64 *
0x18001e894  mov     rcx, [rbp+70h+lpFileName]; unsigned __int16 *
0x18001e898  call    ?SxFindDirSizeRecursive@@YAJPEBGPEA_K@Z; SxFindDirSizeRecursive(ushort const *,unsigned __int64 *)
0x18001e89d  mov     edi, eax
0x18001e89f  mov     [rsp+170h+var_F8], eax
0x18001e8a3  test    eax, eax
0x18001e8a5  mov     eax, 14DBh
0x18001e8aa  js      loc_18001E6DD
0x18001e8b0  mov     [rsp+170h+var_F4], ax
0x18001e8b5  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], r14; unsigned __int16 *
0x18001e8ba  mov     [rsp+170h+ppv], r14; unsigned __int16 *
0x18001e8bf  xor     r9d, r9d; unsigned __int16 *
0x18001e8c2  lea     r8, aWindowsimageba; "WindowsImageBackup"
0x18001e8c9  mov     rdx, [r13+180h]; unsigned __int16 *
0x18001e8d0  lea     rcx, [rbp+70h+lpFileName]; this
0x18001e8d4  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001e8d9  mov     edi, eax
0x18001e8db  mov     [rsp+170h+var_F8], eax
0x18001e8df  test    eax, eax
0x18001e8e1  mov     eax, 14E1h
0x18001e8e6  js      loc_18001E6DD
0x18001e8ec  mov     r14, [rbp+70h+var_B8]
0x18001e8f0  add     r14, r12
0x18001e8f3  mov     [rsp+170h+var_F4], ax
0x18001e8f8  lea     rdx, [rbp+70h+var_B8]; unsigned __int64 *
0x18001e8fc  mov     rcx, [rbp+70h+lpFileName]; unsigned __int16 *
0x18001e900  call    ?SxFindDirSizeRecursive@@YAJPEBGPEA_K@Z; SxFindDirSizeRecursive(ushort const *,unsigned __int64 *)
0x18001e905  mov     edi, eax
0x18001e907  mov     [rsp+170h+var_F8], eax
0x18001e90b  test    eax, eax
0x18001e90d  mov     eax, 14E2h
0x18001e912  jns     short loc_18001E921
0x18001e914  mov     [rsp+170h+var_F2], ax
0x18001e919  xor     r14d, r14d
0x18001e91c  jmp     loc_18001EB36
0x18001e921  add     rsi, r14
0x18001e924  mov     [rsp+170h+var_F4], ax
0x18001e929  add     r15, [rbp+70h+var_B8]
0x18001e92d  xor     r14d, r14d
0x18001e930  mov     rcx, [rsp+170h+hKey]; hKey
0x18001e935  lea     rax, [rcx-1]
0x18001e939  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e93d  ja      short loc_18001E94A
0x18001e93f  call    cs:__imp_RegCloseKey
0x18001e945  mov     [rsp+170h+hKey], r14
0x18001e94a  lea     rax, [rbp+70h+dwDisposition]
0x18001e94e  mov     [rsp+170h+lpdwDisposition], rax; lpdwDisposition
0x18001e953  lea     rax, [rsp+170h+hKey]
0x18001e958  mov     [rsp+170h+phkResult], rax; phkResult
0x18001e95d  mov     [rsp+170h+hTemplateFile], r14; lpSecurityAttributes
0x18001e962  mov     [rsp+170h+dwFlagsAndAttributes], 2001Fh; samDesired
0x18001e96a  mov     dword ptr [rsp+170h+ppv], r14d; dwOptions
0x18001e96f  xor     r9d, r9d; lpClass
0x18001e972  xor     r8d, r8d; Reserved
0x18001e975  lea     rdx, c_wszSafedocsStatusKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001e97c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e983  call    cs:__imp_RegCreateKeyExW
0x18001e989  mov     edi, eax
0x18001e98b  mov     r12d, 80070000h
0x18001e991  test    eax, eax
0x18001e993  jle     short loc_18001E99B
0x18001e995  movzx   edi, ax
0x18001e998  or      edi, r12d
0x18001e99b  mov     [rsp+170h+var_F8], edi
0x18001e99f  mov     eax, 14EFh
0x18001e9a4  test    edi, edi
0x18001e9a6  js      loc_18001E6DD
0x18001e9ac  mov     [rsp+170h+var_F4], ax
0x18001e9b1  mov     rcx, [rsp+170h+hKey]; KeyHandle
0x18001e9b6  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18001e9bb  mov     edi, eax
0x18001e9bd  mov     [rsp+170h+var_F8], eax
0x18001e9c1  test    eax, eax
0x18001e9c3  mov     eax, 14F0h
0x18001e9c8  js      loc_18001E6DD
0x18001e9ce  mov     [rsp+170h+var_F4], ax
0x18001e9d3  mov     r8, r15; unsigned __int64
0x18001e9d6  lea     rdx, c_wszSafedocsScheduleTotalBackupSpaceUsed; "BackupSpaceUsed"
0x18001e9dd  mov     rcx, [rsp+170h+hKey]; hKey
0x18001e9e2  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x18001e9e7  mov     edi, eax
0x18001e9e9  mov     [rsp+170h+var_F8], eax
0x18001e9ed  test    eax, eax
0x18001e9ef  mov     eax, 14F2h
0x18001e9f4  js      loc_18001E6DD
0x18001e9fa  mov     [rsp+170h+var_F4], ax
0x18001e9ff  mov     r8, rsi; unsigned __int64
0x18001ea02  lea     rdx, c_wszSafedocsScheduleLocalBackupSpaceUsed; "LocalBackupSpaceUsed"
0x18001ea09  mov     rcx, [rsp+170h+hKey]; hKey
0x18001ea0e  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x18001ea13  mov     edi, eax
0x18001ea15  mov     [rsp+170h+var_F8], eax
0x18001ea19  test    eax, eax
0x18001ea1b  mov     eax, 14F3h
0x18001ea20  js      loc_18001E6DD
0x18001ea26  mov     [rsp+170h+var_F4], ax
0x18001ea2b  lea     r8, [rbp+70h+var_88]; unsigned __int64 *
0x18001ea2f  lea     rdx, [rbp+70h+var_80]; unsigned __int64 *
0x18001ea33  mov     rcx, [r13+180h]; unsigned __int16 *
0x18001ea3a  call    ?SxQueryVolumeSpace@@YAJPEBGPEA_K11@Z; SxQueryVolumeSpace(ushort const *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x18001ea3f  mov     edi, eax
0x18001ea41  mov     [rsp+170h+var_F8], eax
0x18001ea45  test    eax, eax
0x18001ea47  mov     eax, 14F6h
0x18001ea4c  js      loc_18001E6DD
0x18001ea52  mov     [rsp+170h+var_F4], ax
0x18001ea57  mov     rcx, [rsp+170h+KeyHandle]; hKey
0x18001ea5c  lea     rax, [rcx-1]
0x18001ea60  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ea64  ja      short loc_18001EA71
0x18001ea66  call    cs:__imp_RegCloseKey
0x18001ea6c  mov     [rsp+170h+KeyHandle], r14
0x18001ea71  lea     rax, [rsp+170h+KeyHandle]
0x18001ea76  mov     [rsp+170h+ppv], rax; phkResult
0x18001ea7b  mov     r9d, 2001Fh; samDesired
0x18001ea81  xor     r8d, r8d; ulOptions
0x18001ea84  lea     rdx, c_wszSafedocsDeviceTargetKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001ea8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ea92  call    cs:__imp_RegOpenKeyExW
0x18001ea98  mov     edi, eax
0x18001ea9a  test    eax, eax
0x18001ea9c  jle     short loc_18001EAA4
0x18001ea9e  movzx   edi, ax
0x18001eaa1  or      edi, r12d
0x18001eaa4  mov     [rsp+170h+var_F8], edi
0x18001eaa8  mov     eax, 14F8h
0x18001eaad  test    edi, edi
0x18001eaaf  js      loc_18001E6DD
0x18001eab5  mov     [rsp+170h+var_F4], ax
0x18001eaba  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18001eabf  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18001eac4  mov     edi, eax
0x18001eac6  mov     [rsp+170h+var_F8], eax
0x18001eaca  test    eax, eax
0x18001eacc  mov     eax, 14F9h
0x18001ead1  js      loc_18001E6DD
0x18001ead7  mov     [rsp+170h+var_F4], ax
0x18001eadc  mov     r8, [rbp+70h+var_88]; unsigned __int64
0x18001eae0  lea     rdx, c_wszSafedocsDeviceSize; "TotalSize"
0x18001eae7  mov     rcx, [rsp+170h+KeyHandle]; hKey
0x18001eaec  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x18001eaf1  mov     edi, eax
  ... truncated ...
```
