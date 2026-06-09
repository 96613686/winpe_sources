# CSdBackupImpl::_RefreshBackupSpaceUsed(void)

- ea: `0x18001f128`
- end: `0x18001f780`
- name: `?_RefreshBackupSpaceUsed@CSdBackupImpl@@AEAAJXZ`
- size: `1624`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003f5f0`

## callees

- `0x180003520`
- `0x180003534`
- `0x18001f128`
- `0x180072e08`
- `0x180072f14`
- `0x180073a94`
- `0x1800892c4`
- `0x18008c0c4`
- `0x1800935fc`
- `0x180097104`
- `0x1800994b8`
- `0x18009b340`
- `0x18009ea34`
- `0x18009f560`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001f2f9`
- `msvcrt!_wcsicmp` at `0x18001f2f9`
- `KERNEL32!CreateFileW` at `0x18001f37e`
- `KERNEL32!CreateFileW` at `0x18001f37e`
- `KERNEL32!CloseHandle` at `0x18001f6e8`
- `KERNEL32!CloseHandle` at `0x18001f6e8`
- `KERNEL32!GetComputerNameW` at `0x18001f1e7`
- `KERNEL32!GetComputerNameW` at `0x18001f1e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f47f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f5b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f70e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f72e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f47f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f5b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f70e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f72e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f5e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f5e4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f4c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f4c9`
- `ole32!CoTaskMemFree` at `0x18001f6c2`
- `ole32!CoTaskMemFree` at `0x18001f6c2`
- `ole32!CoCreateInstance` at `0x18001f23d`
- `ole32!CoCreateInstance` at `0x18001f23d`

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
  _BYTE v53[8]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v54; // [rsp+100h] [rbp+0h]
  WCHAR Buffer[16]; // [rsp+108h] [rbp+8h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v41, "CSdBackupImpl::_RefreshBackupSpaceUsed", 0x149Eu, 1u);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&ppv);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(v53);
  hKey = 0;
  KeyHandle = 0;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  FileW = -1;
  v54 = -1;
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
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, _BYTE *))(*(_QWORD *)ppv + 24LL))(
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
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(v53);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(&ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v41);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001f128  push    rbp
0x18001f12a  push    rbx
0x18001f12b  push    rsi
0x18001f12c  push    rdi
0x18001f12d  push    r12
0x18001f12f  push    r13
0x18001f131  push    r14
0x18001f133  push    r15
0x18001f135  lea     rbp, [rsp-38h]
0x18001f13a  sub     rsp, 138h
0x18001f141  mov     rax, cs:__security_cookie
0x18001f148  xor     rax, rsp
0x18001f14b  mov     [rbp+70h+var_48], rax
0x18001f14f  mov     r13, rcx
0x18001f152  mov     r9d, 1; unsigned __int16
0x18001f158  mov     r8d, 149Eh; unsigned __int16
0x18001f15e  lea     rdx, aCsdbackupimplR_0; "CSdBackupImpl::_RefreshBackupSpaceUsed"
0x18001f165  lea     rcx, [rsp+170h+var_F8]; this
0x18001f16a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001f16f  nop
0x18001f170  lea     rcx, [rbp+70h+var_B0]; void *
0x18001f174  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18001f179  nop
0x18001f17a  lea     rcx, [rbp+70h+var_78]; void *
0x18001f17e  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18001f183  nop
0x18001f184  xor     r14d, r14d
0x18001f187  mov     [rsp+170h+hKey], r14
0x18001f18c  mov     [rsp+170h+KeyHandle], r14
0x18001f191  lea     rax, qword_1800EE510
0x18001f198  mov     [rbp+70h+lpFileName], rax
0x18001f19c  mov     [rbp+70h+var_98], r14
0x18001f1a0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001f1a4  mov     [rbp+70h+var_70], rbx
0x18001f1a8  mov     [rbp+70h+dwDisposition], r14d
0x18001f1ac  mov     [rbp+70h+Buffer], r14w
0x18001f1b1  xorps   xmm0, xmm0
0x18001f1b4  movups  xmmword ptr [rbp+70h+var_66], xmm0
0x18001f1b8  movups  xmmword ptr [rbp+70h+var_66+0Eh], xmm0
0x18001f1bc  mov     [rbp+70h+nSize], 10h
0x18001f1c3  mov     r12d, r14d
0x18001f1c6  mov     [rbp+70h+var_90], r14
0x18001f1ca  mov     [rbp+70h+var_B8], r14
0x18001f1ce  mov     [rsp+170h+var_110], r14d
0x18001f1d3  mov     [rbp+70h+pv], r14
0x18001f1d7  mov     [rbp+70h+var_88], r14
0x18001f1db  mov     [rbp+70h+var_80], r14
0x18001f1df  lea     rdx, [rbp+70h+nSize]; nSize
0x18001f1e3  lea     rcx, [rbp+70h+Buffer]; lpBuffer
0x18001f1e7  call    cs:__imp_GetComputerNameW
0x18001f1ee  nop     dword ptr [rax+rax+00h]
0x18001f1f3  test    eax, eax
0x18001f1f5  jnz     short loc_18001F211
0x18001f1f7  call    GetLastFailureAsHRESULT
0x18001f1fc  mov     edi, eax
0x18001f1fe  mov     [rsp+170h+var_F8], eax
0x18001f202  mov     eax, 14B7h
0x18001f207  mov     [rsp+170h+var_F2], ax
0x18001f20c  jmp     loc_18001F68E
0x18001f211  mov     [rsp+170h+var_F8], r14d
0x18001f216  mov     eax, 14B7h
0x18001f21b  mov     [rsp+170h+var_F4], ax
0x18001f220  lea     rax, [rbp+70h+var_B0]
0x18001f224  mov     [rsp+170h+ppv], rax; ppv
0x18001f229  lea     r9, IID_ISdCommon2; riid
0x18001f230  xor     edx, edx; pUnkOuter
0x18001f232  lea     r8d, [rdx+1]; dwClsContext
0x18001f236  lea     rcx, CLSID_SdEngine2; rclsid
0x18001f23d  call    cs:__imp_CoCreateInstance
0x18001f244  nop     dword ptr [rax+rax+00h]
0x18001f249  mov     edi, eax
0x18001f24b  mov     [rsp+170h+var_F8], eax
0x18001f24f  test    eax, eax
0x18001f251  mov     eax, 14B9h
0x18001f256  js      short loc_18001F207
0x18001f258  mov     [rsp+170h+var_F4], ax
0x18001f25d  mov     rcx, [rbp+70h+var_B0]
0x18001f261  mov     rax, [rcx]
0x18001f264  lea     r9, [rbp+70h+var_78]
0x18001f268  lea     r8, IID_IUnknown
0x18001f26f  mov     edx, 9
0x18001f274  mov     rax, [rax+18h]
0x18001f278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f27d  mov     edi, eax
0x18001f27f  mov     [rsp+170h+var_F8], eax
0x18001f283  test    eax, eax
0x18001f285  mov     eax, 14BAh
0x18001f28a  js      loc_18001F207
0x18001f290  mov     [rsp+170h+var_F4], ax
0x18001f295  mov     rcx, [rbp+70h+var_B0]
0x18001f299  mov     rax, [rcx]
0x18001f29c  lea     r9, [rbp+70h+pv]
0x18001f2a0  lea     r8, [rsp+170h+var_110]
0x18001f2a5  mov     rdx, [r13+180h]
0x18001f2ac  mov     rax, [rax+28h]
0x18001f2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2b5  mov     edi, eax
0x18001f2b7  mov     [rsp+170h+var_F8], eax
0x18001f2bb  test    eax, eax
0x18001f2bd  mov     eax, 14BCh
0x18001f2c2  js      loc_18001F207
0x18001f2c8  mov     r15, r14
0x18001f2cb  mov     rsi, r14
0x18001f2ce  mov     [rsp+170h+var_F4], ax
0x18001f2d3  mov     edi, r14d
0x18001f2d6  cmp     [rsp+170h+var_110], r14d
0x18001f2db  jbe     short loc_18001F31D
0x18001f2dd  mov     rcx, [rbp+70h+pv]
0x18001f2e1  mov     eax, edi
0x18001f2e3  lea     r14, [rax+rax*2]
0x18001f2e7  shl     r14, 4
0x18001f2eb  add     r15, [r14+rcx+28h]
0x18001f2f0  lea     rdx, [rbp+70h+Buffer]; String2
0x18001f2f4  mov     rcx, [r14+rcx+8]; String1
0x18001f2f9  call    cs:__imp__wcsicmp
0x18001f300  nop     dword ptr [rax+rax+00h]
0x18001f305  mov     rcx, [rbp+70h+pv]
0x18001f309  test    eax, eax
0x18001f30b  jnz     short loc_18001F312
0x18001f30d  add     rsi, [r14+rcx+28h]
0x18001f312  inc     edi
0x18001f314  cmp     edi, [rsp+170h+var_110]
0x18001f318  jb      short loc_18001F2E1
0x18001f31a  xor     r14d, r14d
0x18001f31d  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], r14; unsigned __int16 *
0x18001f322  mov     [rsp+170h+ppv], r14; unsigned __int16 *
0x18001f327  lea     r9, [rbp+70h+Buffer]; unsigned __int16 *
0x18001f32b  lea     r8, aWindowsimageba; "WindowsImageBackup"
0x18001f332  mov     rdx, [r13+180h]; unsigned __int16 *
0x18001f339  lea     rcx, [rbp+70h+lpFileName]; this
0x18001f33d  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001f342  mov     edi, eax
0x18001f344  mov     [rsp+170h+var_F8], eax
0x18001f348  test    eax, eax
0x18001f34a  mov     eax, 14CBh
0x18001f34f  js      loc_18001F207
0x18001f355  mov     [rsp+170h+var_F4], ax
0x18001f35a  mov     [rsp+170h+hTemplateFile], r14; unsigned __int16 *
0x18001f35f  mov     [rsp+170h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18001f367  mov     r8d, 3; dwShareMode
0x18001f36d  mov     dword ptr [rsp+170h+ppv], r8d; dwCreationDisposition
0x18001f372  xor     r9d, r9d; lpSecurityAttributes
0x18001f375  mov     edx, 1000A0h; dwDesiredAccess
0x18001f37a  mov     rcx, [rbp+70h+lpFileName]; lpFileName
0x18001f37e  call    cs:__imp_CreateFileW
0x18001f385  nop     dword ptr [rax+rax+00h]
0x18001f38a  mov     rbx, rax
0x18001f38d  dec     rax
0x18001f390  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f394  ja      loc_18001F470
0x18001f39a  cmp     dword ptr [r13+1B0h], 7
0x18001f3a2  jz      short loc_18001F3D0
0x18001f3a4  lea     rdx, [rbp+70h+var_90]; unsigned __int64 *
0x18001f3a8  mov     rcx, [r13+180h]; unsigned __int16 *
0x18001f3af  call    ?SdGetSnapshotDiffArea@@YAJPEBGPEA_K11@Z; SdGetSnapshotDiffArea(ushort const *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x18001f3b4  mov     edi, eax
0x18001f3b6  mov     [rsp+170h+var_F8], eax
0x18001f3ba  test    eax, eax
0x18001f3bc  mov     eax, 14D8h
0x18001f3c1  js      loc_18001F207
0x18001f3c7  mov     [rsp+170h+var_F4], ax
0x18001f3cc  mov     r12, [rbp+70h+var_90]
0x18001f3d0  lea     rdx, [rbp+70h+var_B8]; unsigned __int64 *
0x18001f3d4  mov     rcx, [rbp+70h+lpFileName]; unsigned __int16 *
0x18001f3d8  call    ?SxFindDirSizeRecursive@@YAJPEBGPEA_K@Z; SxFindDirSizeRecursive(ushort const *,unsigned __int64 *)
0x18001f3dd  mov     edi, eax
0x18001f3df  mov     [rsp+170h+var_F8], eax
0x18001f3e3  test    eax, eax
0x18001f3e5  mov     eax, 14DBh
0x18001f3ea  js      loc_18001F207
0x18001f3f0  mov     [rsp+170h+var_F4], ax
0x18001f3f5  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], r14; unsigned __int16 *
0x18001f3fa  mov     [rsp+170h+ppv], r14; unsigned __int16 *
0x18001f3ff  xor     r9d, r9d; unsigned __int16 *
0x18001f402  lea     r8, aWindowsimageba; "WindowsImageBackup"
0x18001f409  mov     rdx, [r13+180h]; unsigned __int16 *
0x18001f410  lea     rcx, [rbp+70h+lpFileName]; this
0x18001f414  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001f419  mov     edi, eax
0x18001f41b  mov     [rsp+170h+var_F8], eax
0x18001f41f  test    eax, eax
0x18001f421  mov     eax, 14E1h
0x18001f426  js      loc_18001F207
0x18001f42c  mov     r14, [rbp+70h+var_B8]
0x18001f430  add     r14, r12
0x18001f433  mov     [rsp+170h+var_F4], ax
0x18001f438  lea     rdx, [rbp+70h+var_B8]; unsigned __int64 *
0x18001f43c  mov     rcx, [rbp+70h+lpFileName]; unsigned __int16 *
0x18001f440  call    ?SxFindDirSizeRecursive@@YAJPEBGPEA_K@Z; SxFindDirSizeRecursive(ushort const *,unsigned __int64 *)
0x18001f445  mov     edi, eax
0x18001f447  mov     [rsp+170h+var_F8], eax
0x18001f44b  test    eax, eax
0x18001f44d  mov     eax, 14E2h
0x18001f452  jns     short loc_18001F461
0x18001f454  mov     [rsp+170h+var_F2], ax
0x18001f459  xor     r14d, r14d
0x18001f45c  jmp     loc_18001F68E
0x18001f461  add     rsi, r14
0x18001f464  mov     [rsp+170h+var_F4], ax
0x18001f469  add     r15, [rbp+70h+var_B8]
0x18001f46d  xor     r14d, r14d
0x18001f470  mov     rcx, [rsp+170h+hKey]; hKey
0x18001f475  lea     rax, [rcx-1]
0x18001f479  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f47d  ja      short loc_18001F490
0x18001f47f  call    cs:__imp_RegCloseKey
0x18001f486  nop     dword ptr [rax+rax+00h]
0x18001f48b  mov     [rsp+170h+hKey], r14
0x18001f490  lea     rax, [rbp+70h+dwDisposition]
0x18001f494  mov     [rsp+170h+lpdwDisposition], rax; lpdwDisposition
0x18001f499  lea     rax, [rsp+170h+hKey]
0x18001f49e  mov     [rsp+170h+phkResult], rax; phkResult
0x18001f4a3  mov     [rsp+170h+hTemplateFile], r14; lpSecurityAttributes
0x18001f4a8  mov     [rsp+170h+dwFlagsAndAttributes], 2001Fh; samDesired
0x18001f4b0  mov     dword ptr [rsp+170h+ppv], r14d; dwOptions
0x18001f4b5  xor     r9d, r9d; lpClass
0x18001f4b8  xor     r8d, r8d; Reserved
0x18001f4bb  lea     rdx, c_wszSafedocsStatusKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001f4c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f4c9  call    cs:__imp_RegCreateKeyExW
0x18001f4d0  nop     dword ptr [rax+rax+00h]
0x18001f4d5  mov     edi, eax
0x18001f4d7  mov     r12d, 80070000h
0x18001f4dd  test    eax, eax
0x18001f4df  jle     short loc_18001F4E7
0x18001f4e1  movzx   edi, ax
0x18001f4e4  or      edi, r12d
0x18001f4e7  mov     [rsp+170h+var_F8], edi
0x18001f4eb  mov     eax, 14EFh
0x18001f4f0  test    edi, edi
0x18001f4f2  js      loc_18001F207
0x18001f4f8  mov     [rsp+170h+var_F4], ax
0x18001f4fd  mov     rcx, [rsp+170h+hKey]; KeyHandle
0x18001f502  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18001f507  mov     edi, eax
0x18001f509  mov     [rsp+170h+var_F8], eax
0x18001f50d  test    eax, eax
0x18001f50f  mov     eax, 14F0h
0x18001f514  js      loc_18001F207
0x18001f51a  mov     [rsp+170h+var_F4], ax
0x18001f51f  mov     r8, r15; unsigned __int64
0x18001f522  lea     rdx, c_wszSafedocsScheduleTotalBackupSpaceUsed; "BackupSpaceUsed"
0x18001f529  mov     rcx, [rsp+170h+hKey]; hKey
0x18001f52e  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x18001f533  mov     edi, eax
0x18001f535  mov     [rsp+170h+var_F8], eax
0x18001f539  test    eax, eax
0x18001f53b  mov     eax, 14F2h
0x18001f540  js      loc_18001F207
0x18001f546  mov     [rsp+170h+var_F4], ax
0x18001f54b  mov     r8, rsi; unsigned __int64
0x18001f54e  lea     rdx, c_wszSafedocsScheduleLocalBackupSpaceUsed; "LocalBackupSpaceUsed"
0x18001f555  mov     rcx, [rsp+170h+hKey]; hKey
0x18001f55a  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x18001f55f  mov     edi, eax
0x18001f561  mov     [rsp+170h+var_F8], eax
0x18001f565  test    eax, eax
0x18001f567  mov     eax, 14F3h
0x18001f56c  js      loc_18001F207
0x18001f572  mov     [rsp+170h+var_F4], ax
0x18001f577  lea     r8, [rbp+70h+var_88]; unsigned __int64 *
0x18001f57b  lea     rdx, [rbp+70h+var_80]; unsigned __int64 *
0x18001f57f  mov     rcx, [r13+180h]; unsigned __int16 *
0x18001f586  call    ?SxQueryVolumeSpace@@YAJPEBGPEA_K11@Z; SxQueryVolumeSpace(ushort const *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x18001f58b  mov     edi, eax
0x18001f58d  mov     [rsp+170h+var_F8], eax
0x18001f591  test    eax, eax
0x18001f593  mov     eax, 14F6h
0x18001f598  js      loc_18001F207
0x18001f59e  mov     [rsp+170h+var_F4], ax
0x18001f5a3  mov     rcx, [rsp+170h+KeyHandle]; hKey
0x18001f5a8  lea     rax, [rcx-1]
0x18001f5ac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f5b0  ja      short loc_18001F5C3
0x18001f5b2  call    cs:__imp_RegCloseKey
0x18001f5b9  nop     dword ptr [rax+rax+00h]
0x18001f5be  mov     [rsp+170h+KeyHandle], r14
0x18001f5c3  lea     rax, [rsp+170h+KeyHandle]
0x18001f5c8  mov     [rsp+170h+ppv], rax; phkResult
0x18001f5cd  mov     r9d, 2001Fh; samDesired
0x18001f5d3  xor     r8d, r8d; ulOptions
0x18001f5d6  lea     rdx, c_wszSafedocsDeviceTargetKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001f5dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f5e4  call    cs:__imp_RegOpenKeyExW
0x18001f5eb  nop     dword ptr [rax+rax+00h]
0x18001f5f0  mov     edi, eax
0x18001f5f2  test    eax, eax
0x18001f5f4  jle     short loc_18001F5FC
0x18001f5f6  movzx   edi, ax
0x18001f5f9  or      edi, r12d
0x18001f5fc  mov     [rsp+170h+var_F8], edi
0x18001f600  mov     eax, 14F8h
0x18001f605  test    edi, edi
0x18001f607  js      loc_18001F207
0x18001f60d  mov     [rsp+170h+var_F4], ax
0x18001f612  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18001f617  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18001f61c  mov     edi, eax
0x18001f61e  mov     [rsp+170h+var_F8], eax
0x18001f622  test    eax, eax
  ... truncated ...
```
