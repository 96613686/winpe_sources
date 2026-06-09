# CVssHardwareProviderWrapper::WriteDeviceNames(IVssSnapshotSetDescription *,_LUN_MAPPING_STRUCTURE *,bool)

- ea: `0x140073d84`
- end: `0x1400744e1`
- name: `?WriteDeviceNames@CVssHardwareProviderWrapper@@AEAAXPEAVIVssSnapshotSetDescription@@PEAU_LUN_MAPPING_STRUCTURE@@_N@Z`
- size: `1885`
- prototype: `void __fastcall(CVssHardwareProviderWrapper *__hidden this, struct IVssSnapshotSetDescription *, struct _LUN_MAPPING_STRUCTURE *, bool)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14004d814`
- `0x1400b7dd0`

## callees

- `0x1400088fc`
- `0x140010170`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x140019990`
- `0x140025b00`
- `0x14003c160`
- `0x14003fc04`
- `0x140049ec4`
- `0x140073d84`
- `0x1400744e8`
- `0x140091560`
- `0x140091584`
- `0x1400916f0`
- `0x1400919a0`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400743bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400743bc`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140073f8d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140073f8d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400740d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1400740d7`

## string_xrefs

- `0x140074429`: `GetVolumeNameForVolumeMountPoint(%s)`
- `0x140073dcc`: `CVssHardwareProviderWrapper::WriteDeviceNames`
- `0x140073eaf`: `CVssHardwareProviderWrapper::WriteDeviceNames`
- `0x140073fde`: `CVssHardwareProviderWrapper::WriteDeviceNames`
- `0x140074117`: `CVssHardwareProviderWrapper::WriteDeviceNames`
- `0x140074190`: `CVssHardwareProviderWrapper::WriteDeviceNames`
- `0x1400742f4`: `CVssHardwareProviderWrapper::WriteDeviceNames`
- `0x140074359`: `CVssHardwareProviderWrapper::WriteDeviceNames`
- `0x1400743dd`: `CVssHardwareProviderWrapper::WriteDeviceNames`
- `0x14007444e`: `CVssHardwareProviderWrapper::WriteDeviceNames`
- `0x140073ef9`: `INFO: Attempting to create a Volume Name for hidden volume device %s...`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssHardwareProviderWrapper::WriteDeviceNames(
        CVssHardwareProviderWrapper *this,
        struct IVssSnapshotSetDescription *a2,
        struct _LUN_MAPPING_STRUCTURE *a3,
        char a4)
{
  unsigned int i; // r12d
  __int64 v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rdx
  WCHAR *v10; // rbx
  int v11; // r14d
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rax
  unsigned __int16 *v17; // r15
  __int64 v18; // rdx
  int v19; // r14d
  signed int LastError; // eax
  unsigned int v21; // edi
  int v23; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v24; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v25; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v26; // [rsp+50h] [rbp-B0h]
  int v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+5Ch] [rbp-A4h]
  int v29; // [rsp+60h] [rbp-A0h]
  _BYTE v30[120]; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+E0h] [rbp-20h]
  _QWORD v32[2]; // [rsp+E8h] [rbp-18h] BYREF
  LPCWSTR lpszVolumeMountPoint; // [rsp+F8h] [rbp-8h] BYREF
  struct IVssSnapshotSetDescription *v34; // [rsp+100h] [rbp+0h]
  LPVOID v35; // [rsp+110h] [rbp+10h] BYREF
  int v36; // [rsp+118h] [rbp+18h]
  WCHAR szVolumeName[64]; // [rsp+180h] [rbp+80h] BYREF

  v34 = a2;
  v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
  v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
  v26 = L"CORHIMPC";
  v27 = 2097;
  v28 = 1;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(v30, 0, sizeof(v30));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v35, (__int64)&v24, 0);
  v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
  v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
  v26 = L"CORHIMPC";
  v27 = 2101;
  v28 = 1;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(v30, 0, sizeof(v30));
  CVssFunctionTracer::AddOperation((__int64)&v35, (__int64)&v24, 0x1A3u);
  for ( i = 0; i < *(_DWORD *)a3; ++i )
  {
    v6 = *((_QWORD *)a3 + 1);
    v7 = *(_QWORD *)(v6 + 80LL * i + 56);
    if ( v7 )
    {
      v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
      v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
      v26 = L"CORHIMPC";
      v27 = 2111;
      v28 = 6;
      v29 = 255;
      v31 = 0x1000000;
      memset_0(v30, 0, sizeof(v30));
      CVssFunctionTracer::Trace(
        &v35,
        &v24,
        L"INFO: Attempting to create a Volume Name for hidden volume device %s...",
        v7);
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(*(_QWORD *)(v6 + 80LL * i + 56) + 2 * v8) );
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&lpszVolumeMountPoint, v8 + 2);
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(*(_QWORD *)(v6 + 80LL * i + 56) + 2 * v9) );
      v10 = (WCHAR *)lpszVolumeMountPoint;
      v11 = StringCchPrintfW((unsigned __int16 *)lpszVolumeMountPoint, v9 + 2, L"%s\\");
      v36 = v11;
      if ( v11 < 0 )
      {
        v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
        v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
        v26 = L"CORHIMPC";
        v27 = 2121;
        v28 = 1;
        v29 = 255;
        v31 = 0x1000000;
        memset_0(v30, 0, sizeof(v30));
        CVssFunctionTracer::TranslateGenericError(&v35, &v24, (unsigned int)v11, L"StringCchPrintf");
      }
      memset_0(szVolumeName, 0, sizeof(szVolumeName));
      if ( !GetVolumeNameForVolumeMountPointW(v10, szVolumeName, 0x40u) )
      {
        LastError = GetLastError();
        v21 = LastError;
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
        v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
        v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
        v26 = L"CORHIMPC";
        v27 = 2128;
        v28 = 1;
        v29 = 255;
        v31 = 0x1000000;
        memset_0(v30, 0, sizeof(v30));
        CVssFunctionTracer::TranslateGenericError(&v35, &v24, v21, L"GetVolumeNameForVolumeMountPoint(%s)", v10);
      }
      v12 = -1;
      do
        ++v12;
      while ( szVolumeName[v12] );
      if ( szVolumeName[v12 - 1] == 92 )
      {
        v13 = 2 * v12 - 2;
        if ( v13 >= 0x80 )
          _report_rangecheckfailure();
        *(WCHAR *)((char *)szVolumeName + v13) = 0;
      }
      v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
      v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
      v26 = L"CORHIMPC";
      v27 = 2135;
      v28 = 6;
      v29 = 255;
      v31 = 0x1000000;
      memset_0(v30, 0, sizeof(v30));
      CVssFunctionTracer::Trace(
        &v35,
        &v24,
        L"Found volume name %s for device %s",
        szVolumeName,
        *(_QWORD *)(v6 + 80LL * i + 56));
      v14 = -1;
      do
        ++v14;
      while ( szVolumeName[v14] );
      v15 = v14 + 1;
      v16 = 2 * v15;
      if ( !is_mul_ok(v15, 2u) )
        v16 = -1;
      v17 = (unsigned __int16 *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v17 )
      {
        v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
        v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
        v26 = L"CORHIMPC";
        v27 = 2140;
        v28 = 1;
        v29 = 255;
        v31 = 0x1000000;
        memset_0(v30, 0, sizeof(v30));
        CVssFunctionTracer::Throw(&v35, &v24, 2147942414LL, L"can't allocate device name");
      }
      v18 = -1;
      do
        ++v18;
      while ( szVolumeName[v18] );
      v19 = StringCchCopyW(v17, v18 + 1, szVolumeName);
      v36 = v19;
      if ( v19 < 0 )
      {
        v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
        v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
        v26 = L"CORHIMPC";
        v27 = 2146;
        v28 = 1;
        v29 = 255;
        v31 = 0x1000000;
        memset_0(v30, 0, sizeof(v30));
        CVssFunctionTracer::TranslateGenericError(&v35, &v24, (unsigned int)v19, L"StringCchPrintf");
      }
      operator delete(*(void **)(v6 + 80LL * i + 56));
      *(_QWORD *)(v6 + 80LL * i + 56) = v17;
      SysFreeString(v10);
    }
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(v32);
    v36 = (*(__int64 (__fastcall **)(struct IVssSnapshotSetDescription *, _QWORD, _QWORD *))(*(_QWORD *)v34 + 112LL))(
            v34,
            i,
            v32);
    v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
    v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
    v26 = L"CORHIMPC";
    v27 = 2156;
    v28 = 1;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(v30, 0, sizeof(v30));
    CVssFunctionTracer::CheckForErrorInternal(&v35, &v24, L"IVssSnapshotSetDescription::GetSnasphotDescription");
    v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v32[0] + 136LL))(
            v32[0],
            *(_QWORD *)(v6 + 80LL * i + 56));
    v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
    v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
    v26 = L"CORHIMPC";
    v27 = 2158;
    v28 = 1;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(v30, 0, sizeof(v30));
    CVssFunctionTracer::CheckForErrorInternal(&v35, &v24, L"IVssSnapshotSetDescription::SetDeviceName");
    if ( a4 )
    {
      v23 = 0;
      v36 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v32[0] + 64LL))(v32[0], &v23);
      v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
      v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
      v26 = L"CORHIMPC";
      v27 = 2164;
      v28 = 1;
      v29 = 255;
      v31 = 0x1000000;
      memset_0(v30, 0, sizeof(v30));
      CVssFunctionTracer::CheckForErrorInternal(&v35, &v24, L"IVssSnapshotDescription::GetAttributes");
      v23 |= 0x80000u;
      v36 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v32[0] + 72LL))(v32[0]);
      v24 = L"base\\stor\\vss\\modules\\coord\\src\\hwimport.cxx";
      v25 = L"CVssHardwareProviderWrapper::WriteDeviceNames";
      v26 = L"CORHIMPC";
      v27 = 2167;
      v28 = 1;
      v29 = 255;
      v31 = 0x1000000;
      memset_0(v30, 0, sizeof(v30));
      CVssFunctionTracer::CheckForErrorInternal(&v35, &v24, L"IVssSnapshotDescription::SetAttributes");
    }
    ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)v32);
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v35);
}

```

## disassembly

```asm
0x140073d84  mov     [rsp-8+arg_0], rbx
0x140073d89  push    rbp
0x140073d8a  push    rsi
0x140073d8b  push    rdi
0x140073d8c  push    r12
0x140073d8e  push    r13
0x140073d90  push    r14
0x140073d92  push    r15
0x140073d94  lea     rbp, [rsp-110h]
0x140073d9c  sub     rsp, 210h
0x140073da3  mov     rax, cs:__security_cookie
0x140073daa  xor     rax, rsp
0x140073dad  mov     [rbp+140h+var_40], rax
0x140073db4  mov     [rsp+240h+var_210], r9b
0x140073db9  mov     r13, r8
0x140073dbc  mov     [rbp+140h+var_140], rdx
0x140073dc0  lea     rbx, aBaseStorVssMod_1; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140073dc7  mov     [rsp+240h+var_200], rbx
0x140073dcc  lea     rdi, aCvsshardwarepr_157; "CVssHardwareProviderWrapper::WriteDevic"...
0x140073dd3  mov     [rsp+240h+var_1F8], rdi
0x140073dd8  lea     rsi, aCorhimpc; "CORHIMPC"
0x140073ddf  mov     [rsp+240h+var_1F0], rsi
0x140073de4  mov     [rsp+240h+var_1E8], 831h
0x140073dec  mov     r14d, 1
0x140073df2  mov     [rsp+240h+var_1E4], r14d
0x140073df7  mov     r12d, 0FFh
0x140073dfd  mov     [rsp+240h+var_1E0], r12d
0x140073e02  xor     r15d, r15d
0x140073e05  mov     [rbp+140h+var_160], 1000000h
0x140073e0c  xor     edx, edx; Val
0x140073e0e  lea     r8d, [r14+77h]; Size
0x140073e12  lea     rcx, [rsp+240h+var_1D8]; void *
0x140073e17  call    memset_0
0x140073e1c  xor     r8d, r8d
0x140073e1f  lea     rdx, [rsp+240h+var_200]
0x140073e24  lea     rcx, [rbp+140h+var_130]
0x140073e28  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140073e2d  nop
0x140073e2e  mov     [rsp+240h+var_200], rbx
0x140073e33  mov     [rsp+240h+var_1F8], rdi
0x140073e38  mov     [rsp+240h+var_1F0], rsi
0x140073e3d  mov     [rsp+240h+var_1E8], 835h
0x140073e45  mov     [rsp+240h+var_1E4], r14d
0x140073e4a  mov     [rsp+240h+var_1E0], r12d
0x140073e4f  mov     [rbp+140h+var_160], 1000000h
0x140073e56  xor     edx, edx; Val
0x140073e58  lea     r8d, [r14+77h]; Size
0x140073e5c  lea     rcx, [rsp+240h+var_1D8]; void *
0x140073e61  call    memset_0
0x140073e66  mov     r8d, 1A3h
0x140073e6c  lea     rdx, [rsp+240h+var_200]
0x140073e71  lea     rcx, [rbp+140h+var_130]
0x140073e75  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x140073e7a  mov     r12d, r15d
0x140073e7d  cmp     r12d, [r13+0]
0x140073e81  jnb     loc_1400744AE
0x140073e87  mov     eax, r12d
0x140073e8a  lea     rdi, [rax+rax*4]
0x140073e8e  add     rdi, rdi
0x140073e91  mov     rsi, [r13+8]
0x140073e95  mov     rbx, [rsi+rdi*8+38h]
0x140073e9a  test    rbx, rbx
0x140073e9d  jz      loc_1400740E4
0x140073ea3  lea     rax, aBaseStorVssMod_1; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140073eaa  mov     [rsp+240h+var_200], rax
0x140073eaf  lea     rax, aCvsshardwarepr_157; "CVssHardwareProviderWrapper::WriteDevic"...
0x140073eb6  mov     [rsp+240h+var_1F8], rax
0x140073ebb  lea     rax, aCorhimpc; "CORHIMPC"
0x140073ec2  mov     [rsp+240h+var_1F0], rax
0x140073ec7  mov     [rsp+240h+var_1E8], 83Fh
0x140073ecf  mov     [rsp+240h+var_1E4], 6
0x140073ed7  mov     [rsp+240h+var_1E0], 0FFh
0x140073edf  mov     [rbp+140h+var_160], 1000000h
0x140073ee6  xor     edx, edx; Val
0x140073ee8  lea     r8d, [rdx+78h]; Size
0x140073eec  lea     rcx, [rsp+240h+var_1D8]; void *
0x140073ef1  call    memset_0
0x140073ef6  mov     r9, rbx
0x140073ef9  lea     r8, aInfoAttempting; "INFO: Attempting to create a Volume Nam"...
0x140073f00  lea     rdx, [rsp+240h+var_200]
0x140073f05  lea     rcx, [rbp+140h+var_130]
0x140073f09  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140073f0e  mov     rax, [rsi+rdi*8+38h]
0x140073f13  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140073f17  mov     rdx, rbx
0x140073f1a  inc     rdx
0x140073f1d  cmp     [rax+rdx*2], r15w
0x140073f22  jnz     short loc_140073F1A
0x140073f24  add     edx, 2; int
0x140073f27  lea     rcx, [rbp+140h+lpszVolumeMountPoint]; this
0x140073f2b  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x140073f30  nop
0x140073f31  mov     r9, [rsi+rdi*8+38h]
0x140073f36  mov     rdx, rbx
0x140073f39  inc     rdx
0x140073f3c  cmp     [r9+rdx*2], r15w
0x140073f41  jnz     short loc_140073F39
0x140073f43  add     rdx, 2; unsigned __int64
0x140073f47  lea     r8, aS_2; "%s\\"
0x140073f4e  mov     rbx, [rbp+140h+lpszVolumeMountPoint]
0x140073f52  mov     rcx, rbx; unsigned __int16 *
0x140073f55  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140073f5a  mov     r14d, eax
0x140073f5d  mov     [rbp+140h+var_128], eax
0x140073f60  test    eax, eax
0x140073f62  js      loc_140074442
0x140073f68  mov     r14d, 80h
0x140073f6e  mov     r8d, r14d; Size
0x140073f71  xor     edx, edx; Val
0x140073f73  lea     rcx, [rbp+140h+szVolumeName]; void *
0x140073f7a  call    memset_0
0x140073f7f  lea     r8d, [r14-40h]; cchBufferLength
0x140073f83  lea     rdx, [rbp+140h+szVolumeName]; lpszVolumeName
0x140073f8a  mov     rcx, rbx; lpszVolumeMountPoint
0x140073f8d  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140073f93  test    eax, eax
0x140073f95  jz      loc_1400743BC
0x140073f9b  lea     rcx, [rbp+140h+szVolumeName]
0x140073fa2  or      rax, 0FFFFFFFFFFFFFFFFh
0x140073fa6  inc     rax
0x140073fa9  cmp     [rcx+rax*2], r15w
0x140073fae  jnz     short loc_140073FA6
0x140073fb0  cmp     [rbp+rax*2+140h+var_C2], 5Ch ; '\'
0x140073fb6  jnz     short loc_140073FD2
0x140073fb8  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140073fc0  cmp     rcx, r14
0x140073fc3  jnb     loc_1400742E2
0x140073fc9  mov     [rbp+rcx+140h+szVolumeName], r15w
0x140073fd2  lea     r14, aBaseStorVssMod_1; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140073fd9  mov     [rsp+240h+var_200], r14
0x140073fde  lea     rax, aCvsshardwarepr_157; "CVssHardwareProviderWrapper::WriteDevic"...
0x140073fe5  mov     [rsp+240h+var_1F8], rax
0x140073fea  lea     rax, aCorhimpc; "CORHIMPC"
0x140073ff1  mov     [rsp+240h+var_1F0], rax
0x140073ff6  mov     [rsp+240h+var_1E8], 857h
0x140073ffe  mov     [rsp+240h+var_1E4], 6
0x140074006  mov     [rsp+240h+var_1E0], 0FFh
0x14007400e  mov     [rbp+140h+var_160], 1000000h
0x140074015  xor     edx, edx; Val
0x140074017  lea     r8d, [rdx+78h]; Size
0x14007401b  lea     rcx, [rsp+240h+var_1D8]; void *
0x140074020  call    memset_0
0x140074025  mov     rax, [rsi+rdi*8+38h]
0x14007402a  mov     [rsp+240h+var_220], rax
0x14007402f  lea     r9, [rbp+140h+szVolumeName]
0x140074036  lea     r8, aFoundVolumeNam; "Found volume name %s for device %s"
0x14007403d  lea     rdx, [rsp+240h+var_200]
0x140074042  lea     rcx, [rbp+140h+var_130]
0x140074046  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14007404b  lea     rax, [rbp+140h+szVolumeName]
0x140074052  or      r8, 0FFFFFFFFFFFFFFFFh
0x140074056  mov     rcx, r8
0x140074059  inc     rcx
0x14007405c  cmp     [rax+rcx*2], r15w
0x140074061  jnz     short loc_140074059
0x140074063  inc     rcx
0x140074066  mov     eax, 2
0x14007406b  mul     rcx
0x14007406e  cmovb   rax, r8
0x140074072  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140074079  mov     rcx, rax; unsigned __int64
0x14007407c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140074081  mov     r15, rax
0x140074084  xor     r10d, r10d
0x140074087  test    rax, rax
0x14007408a  jz      loc_140074354
0x140074090  lea     rax, [rbp+140h+szVolumeName]
0x140074097  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14007409b  inc     rdx
0x14007409e  cmp     [rax+rdx*2], r10w
0x1400740a3  jnz     short loc_14007409B
0x1400740a5  inc     rdx; unsigned __int64
0x1400740a8  lea     r8, [rbp+140h+szVolumeName]; unsigned __int16 *
0x1400740af  mov     rcx, r15; unsigned __int16 *
0x1400740b2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400740b7  mov     r14d, eax
0x1400740ba  mov     [rbp+140h+var_128], eax
0x1400740bd  test    eax, eax
0x1400740bf  js      loc_1400742E8
0x1400740c5  mov     rcx, [rsi+rdi*8+38h]; Block
0x1400740ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400740cf  mov     [rsi+rdi*8+38h], r15
0x1400740d4  mov     rcx, rbx; bstrString
0x1400740d7  call    cs:__imp_SysFreeString
0x1400740dd  xor     r15d, r15d
0x1400740e0  lea     r14d, [r15+1]
0x1400740e4  lea     rcx, [rbp+140h+var_158]
0x1400740e8  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x1400740ed  nop
0x1400740ee  mov     rbx, [rbp+140h+var_140]
0x1400740f2  mov     rax, [rbx]
0x1400740f5  lea     r8, [rbp+140h+var_158]
0x1400740f9  mov     edx, r12d
0x1400740fc  mov     rcx, rbx
0x1400740ff  mov     rax, [rax+70h]
0x140074103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140074108  mov     [rbp+140h+var_128], eax
0x14007410b  lea     rbx, aBaseStorVssMod_1; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140074112  mov     [rsp+240h+var_200], rbx
0x140074117  lea     rax, aCvsshardwarepr_157; "CVssHardwareProviderWrapper::WriteDevic"...
0x14007411e  mov     [rsp+240h+var_1F8], rax
0x140074123  lea     rax, aCorhimpc; "CORHIMPC"
0x14007412a  mov     [rsp+240h+var_1F0], rax
0x14007412f  mov     [rsp+240h+var_1E8], 86Ch
0x140074137  mov     [rsp+240h+var_1E4], r14d
0x14007413c  mov     [rsp+240h+var_1E0], 0FFh
0x140074144  mov     [rbp+140h+var_160], 1000000h
0x14007414b  xor     edx, edx; Val
0x14007414d  lea     r8d, [rdx+78h]; Size
0x140074151  lea     rcx, [rsp+240h+var_1D8]; void *
0x140074156  call    memset_0
0x14007415b  lea     r8, aIvsssnapshotse_6; "IVssSnapshotSetDescription::GetSnasphot"...
0x140074162  lea     rdx, [rsp+240h+var_200]
0x140074167  lea     rcx, [rbp+140h+var_130]
0x14007416b  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x140074170  mov     rcx, [rbp+140h+var_158]
0x140074174  mov     rax, [rcx]
0x140074177  mov     rdx, [rsi+rdi*8+38h]
0x14007417c  mov     rax, [rax+88h]
0x140074183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140074188  mov     [rbp+140h+var_128], eax
0x14007418b  mov     [rsp+240h+var_200], rbx
0x140074190  lea     rdi, aCvsshardwarepr_157; "CVssHardwareProviderWrapper::WriteDevic"...
0x140074197  mov     [rsp+240h+var_1F8], rdi
0x14007419c  lea     rsi, aCorhimpc; "CORHIMPC"
0x1400741a3  mov     [rsp+240h+var_1F0], rsi
0x1400741a8  mov     [rsp+240h+var_1E8], 86Eh
0x1400741b0  mov     [rsp+240h+var_1E4], r14d
0x1400741b5  mov     [rsp+240h+var_1E0], 0FFh
0x1400741bd  mov     [rbp+140h+var_160], 1000000h
0x1400741c4  xor     edx, edx; Val
0x1400741c6  lea     r8d, [rdx+78h]; Size
0x1400741ca  lea     rcx, [rsp+240h+var_1D8]; void *
0x1400741cf  call    memset_0
0x1400741d4  lea     r8, aIvsssnapshotse_10; "IVssSnapshotSetDescription::SetDeviceNa"...
0x1400741db  lea     rdx, [rsp+240h+var_200]
0x1400741e0  lea     rcx, [rbp+140h+var_130]
0x1400741e4  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400741e9  cmp     [rsp+240h+var_210], r15b
0x1400741ee  jz      loc_1400742D1
0x1400741f4  mov     [rsp+240h+var_208], r15d
0x1400741f9  mov     rcx, [rbp+140h+var_158]
0x1400741fd  mov     rax, [rcx]
0x140074200  lea     rdx, [rsp+240h+var_208]
0x140074205  mov     rax, [rax+40h]
0x140074209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007420e  mov     [rbp+140h+var_128], eax
0x140074211  mov     [rsp+240h+var_200], rbx
0x140074216  mov     [rsp+240h+var_1F8], rdi
0x14007421b  mov     [rsp+240h+var_1F0], rsi
0x140074220  mov     [rsp+240h+var_1E8], 874h
0x140074228  mov     [rsp+240h+var_1E4], r14d
0x14007422d  mov     [rsp+240h+var_1E0], 0FFh
0x140074235  mov     [rbp+140h+var_160], 1000000h
0x14007423c  xor     edx, edx; Val
0x14007423e  lea     r8d, [rdx+78h]; Size
0x140074242  lea     rcx, [rsp+240h+var_1D8]; void *
0x140074247  call    memset_0
0x14007424c  lea     r8, aIvsssnapshotde; "IVssSnapshotDescription::GetAttributes"
0x140074253  lea     rdx, [rsp+240h+var_200]
0x140074258  lea     rcx, [rbp+140h+var_130]
0x14007425c  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x140074261  mov     edx, [rsp+240h+var_208]
0x140074265  bts     edx, 13h
0x140074269  mov     [rsp+240h+var_208], edx
0x14007426d  mov     rcx, [rbp+140h+var_158]
0x140074271  mov     rax, [rcx]
0x140074274  mov     rax, [rax+48h]
0x140074278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007427d  mov     [rbp+140h+var_128], eax
0x140074280  mov     [rsp+240h+var_200], rbx
0x140074285  mov     [rsp+240h+var_1F8], rdi
0x14007428a  mov     [rsp+240h+var_1F0], rsi
0x14007428f  mov     [rsp+240h+var_1E8], 877h
0x140074297  mov     [rsp+240h+var_1E4], r14d
0x14007429c  mov     [rsp+240h+var_1E0], 0FFh
0x1400742a4  mov     [rbp+140h+var_160], 1000000h
0x1400742ab  xor     edx, edx; Val
0x1400742ad  lea     r8d, [rdx+78h]; Size
0x1400742b1  lea     rcx, [rsp+240h+var_1D8]; void *
0x1400742b6  call    memset_0
0x1400742bb  lea     r8, aIvsssnapshotde_0; "IVssSnapshotDescription::SetAttributes"
0x1400742c2  lea     rdx, [rsp+240h+var_200]
0x1400742c7  lea     rcx, [rbp+140h+var_130]
0x1400742cb  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400742d0  nop
0x1400742d1  lea     rcx, [rbp+140h+var_158]
0x1400742d5  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x1400742da  add     r12d, r14d
0x1400742dd  jmp     loc_140073E7D
0x1400742e2  call    __report_rangecheckfailure
0x1400742e8  lea     rax, aBaseStorVssMod_1; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400742ef  mov     [rsp+240h+var_200], rax
0x1400742f4  lea     rax, aCvsshardwarepr_157; "CVssHardwareProviderWrapper::WriteDevic"...
0x1400742fb  mov     [rsp+240h+var_1F8], rax
0x140074300  lea     rax, aCorhimpc; "CORHIMPC"
0x140074307  mov     [rsp+240h+var_1F0], rax
0x14007430c  mov     [rsp+240h+var_1E8], 862h
0x140074314  mov     [rsp+240h+var_1E4], 1
0x14007431c  mov     [rsp+240h+var_1E0], 0FFh
  ... truncated ...
```
