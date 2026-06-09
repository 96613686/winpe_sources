# CVssHardwareProviderWrapper::RestartDiskIfResyncTarget(CVssFunctionTracer &,void *,_SP_DEVINFO_DATA *,ushort *,_VSS_RESYNC_COMPLETION_DATA *)

- ea: `0x1400cb0f0`
- end: `0x1400cb90b`
- name: `?RestartDiskIfResyncTarget@CVssHardwareProviderWrapper@@AEAA_NAEAVCVssFunctionTracer@@PEAXPEAU_SP_DEVINFO_DATA@@PEAGPEAU_VSS_RESYNC_COMPLETION_DATA@@@Z`
- size: `2075`
- prototype: `bool __usercall@<al>(CVssHardwareProviderWrapper *__hidden this@<rcx>, struct CVssFunctionTracer *@<rdx>, void *@<r8>, struct _SP_DEVINFO_DATA *@<r9>, unsigned __int16 *, struct _VSS_RESYNC_COMPLETION_DATA *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140053bcc`

## callees

- `0x140008450`
- `0x140009444`
- `0x140011a90`
- `0x1400139c0`
- `0x140015e38`
- `0x140019760`
- `0x14004d404`
- `0x140065a90`
- `0x14008de40`
- `0x140090b20`
- `0x140091560`
- `0x1400921dc`
- `0x1400b4d94`
- `0x1400b8c3c`
- `0x1400cb0f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb3d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb42c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb50d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb3d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb42c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cb50d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400cb1b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400cb1b7`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiCallClassInstaller` at `0x1400cb4aa`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiCallClassInstaller` at `0x1400cb4aa`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiSetClassInstallParamsW` at `0x1400cb3c9`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiSetClassInstallParamsW` at `0x1400cb3c9`

## string_xrefs

- `0x1400cb46c`: `SetupDiSetClassInstallParams(%s) fails for Disk %d winerror %d`
- `0x1400cb418`: `SetupDiSetClassInstallParams(%s) fails winerror %d`
- `0x1400cb54d`: `SetupDiCallClassInstaller(DIF_PROPERTYCHANGE, %s) fails for Disk %d winerror %d`
- `0x1400cb4f9`: `SetupDiCallClassInstaller(DIF_PROPERTYCHANGE, %s) fails to restart winerror %d`
- `0x1400cb6db`: `Cannot open handle for disk %s`
- `0x1400cb698`: `Error - Cannot open handle to post-resync disk %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CVssHardwareProviderWrapper::RestartDiskIfResyncTarget(
        CVssHardwareProviderWrapper *this,
        struct CVssFunctionTracer *a2,
        void *a3,
        struct _SP_DEVINFO_DATA *a4,
        unsigned __int16 *a5,
        struct _VSS_RESYNC_COMPLETION_DATA *a6)
{
  struct _VDS_LUN_INFORMATION *v8; // rax
  struct _VDS_LUN_INFORMATION *v9; // r12
  CVssHardwareProviderWrapper *v10; // rcx
  unsigned int i; // r15d
  bool v12; // zf
  DWORD LastError; // ebx
  DWORD v14; // ebx
  unsigned int v15; // edi
  const wchar_t *v16; // r9
  CVssHardwareProviderWrapper *v17; // rcx
  DWORD v18; // ebx
  unsigned int v19; // ebx
  int v20; // eax
  int v21; // eax
  bool v22; // dl
  unsigned int v23; // eax
  unsigned int v24; // r8d
  __int64 j; // rdx
  bool v26; // bl
  bool *v28; // [rsp+20h] [rbp-E0h]
  bool *v29; // [rsp+20h] [rbp-E0h]
  struct _DISK_SNAPSHOT_INFO **v30; // [rsp+28h] [rbp-D8h]
  int v31; // [rsp+28h] [rbp-D8h]
  struct _DISK_SNAPSHOT_INFO **v32; // [rsp+28h] [rbp-D8h]
  unsigned int *v33; // [rsp+30h] [rbp-D0h]
  CVssHardwareProviderWrapper *v34; // [rsp+50h] [rbp-B0h]
  bool v35; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v36; // [rsp+60h] [rbp-A0h]
  unsigned int v37; // [rsp+68h] [rbp-98h] BYREF
  struct _VDS_LUN_INFORMATION *pv; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v39; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v40; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v41; // [rsp+88h] [rbp-78h]
  int v42; // [rsp+90h] [rbp-70h]
  int v43; // [rsp+94h] [rbp-6Ch]
  int v44; // [rsp+98h] [rbp-68h]
  _BYTE v45[120]; // [rsp+A0h] [rbp-60h] BYREF
  int v46; // [rsp+118h] [rbp+18h]
  HDEVINFO DeviceInfoSet; // [rsp+120h] [rbp+20h]
  PSP_DEVINFO_DATA DeviceInfoData; // [rsp+128h] [rbp+28h]
  __int64 v49; // [rsp+130h] [rbp+30h] BYREF
  __int128 v50; // [rsp+138h] [rbp+38h]
  __int128 v51; // [rsp+148h] [rbp+48h]
  __int16 v52; // [rsp+158h] [rbp+58h]
  __int64 v53; // [rsp+15Ch] [rbp+5Ch]
  __int64 v54; // [rsp+168h] [rbp+68h]
  __int64 v55; // [rsp+170h] [rbp+70h]
  int v56; // [rsp+178h] [rbp+78h]
  __int64 v57; // [rsp+180h] [rbp+80h]
  __int16 v58; // [rsp+188h] [rbp+88h]
  void **v59; // [rsp+190h] [rbp+90h]
  __int64 v60; // [rsp+198h] [rbp+98h]
  __int64 v61; // [rsp+1A8h] [rbp+A8h] BYREF
  int v62; // [rsp+1B0h] [rbp+B0h]
  struct _SP_CLASSINSTALL_HEADER ClassInstallParams[3]; // [rsp+1B8h] [rbp+B8h] BYREF

  DeviceInfoData = a4;
  DeviceInfoSet = a3;
  v36 = a5;
  v35 = 0;
  v37 = 0;
  memset(ClassInstallParams, 0, 20);
  v61 = 0;
  v62 = 0;
  v49 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v60 = 0;
  v59 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
  v50 = 0;
  v51 = 0;
  v8 = (struct _VDS_LUN_INFORMATION *)CoTaskMemAlloc(0x60u);
  v9 = v8;
  pv = v8;
  if ( !v8 )
  {
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1494;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::Throw(a2, &v39, 2147942414LL, L"Cannot allocate VDS_LUN_INFORMATION");
  }
  memset_0(v8, 0, sizeof(struct _VDS_LUN_INFORMATION));
  if ( !CVssHardwareProviderWrapper::BuildLunInfoForDrive(this, a5, v9, &v37, &v35, 0, 0) )
  {
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1501;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::Trace(a2, &v39, L"Can't to build Lun info for drive %s . Ignoring", a5);
LABEL_21:
    CVssHardwareProviderWrapper::FreeLunInfo(pv, 0, 0, 1u);
    v22 = 0;
    goto LABEL_33;
  }
  for ( i = 0; i < *((_DWORD *)a6 + 8); ++i )
  {
    if ( CVssHardwareProviderWrapper::IsMatchLun(
           v10,
           v9,
           (const struct _VDS_LUN_INFORMATION *)(*((_QWORD *)a6 + 3) + 96LL * i),
           0) )
    {
      break;
    }
  }
  v43 = 1;
  v46 = 0x1000000;
  v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
  v41 = L"CORHRSNC";
  v12 = i == *((_DWORD *)a6 + 8);
  v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
  if ( v12 )
  {
    v42 = 1518;
    v44 = 255;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::Trace(a2, &v39, L"Lun info of disk %s not expected. Ignoring.", a5);
    goto LABEL_21;
  }
  v42 = 1527;
  v44 = 255;
  memset_0(v45, 0, sizeof(v45));
  CVssFunctionTracer::Trace(a2, &v39, L"Restarting disk device %s", v36);
  ClassInstallParams[0].cbSize = 8;
  *(_QWORD *)&ClassInstallParams[0].InstallFunction = 0x300000012LL;
  *(_QWORD *)&ClassInstallParams[1].InstallFunction = 2;
  if ( !SetupDiSetClassInstallParamsW(DeviceInfoSet, DeviceInfoData, ClassInstallParams, 0x14u) )
  {
    LastError = GetLastError();
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1540;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    LODWORD(v28) = LastError;
    CVssFunctionTracer::Trace(a2, &v39, L"SetupDiSetClassInstallParams(%s) fails winerror %d", v36, v28);
    v14 = GetLastError();
    v15 = v37;
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1541;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    v16 = L"SetupDiSetClassInstallParams(%s) fails for Disk %d winerror %d";
LABEL_12:
    LODWORD(v33) = v14;
    LODWORD(v30) = v15;
    CVssFunctionTracer::AddContextEx((__int64)a2, (__int64)&v39, 0x1B67u, v16, v36, v30, v33);
    goto LABEL_21;
  }
  if ( !SetupDiCallClassInstaller(0x12u, DeviceInfoSet, DeviceInfoData) )
  {
    v18 = GetLastError();
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1548;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    LODWORD(v28) = v18;
    CVssFunctionTracer::Trace(
      a2,
      &v39,
      L"SetupDiCallClassInstaller(DIF_PROPERTYCHANGE, %s) fails to restart winerror %d",
      v36,
      v28);
    v14 = GetLastError();
    v15 = v37;
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1549;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    v16 = L"SetupDiCallClassInstaller(DIF_PROPERTYCHANGE, %s) fails for Disk %d winerror %d";
    goto LABEL_12;
  }
  if ( CVssHardwareProviderWrapper::IsRebootRequired(v17, DeviceInfoSet, DeviceInfoData, v36) )
  {
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1558;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::Trace(
      a2,
      &v39,
      L"Disk %d requires a reboot in order to continue, resync cannot continue with this disk",
      v37);
    v19 = v37;
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1559;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    LODWORD(v30) = v19;
    CVssFunctionTracer::AddContextEx(
      (__int64)a2,
      (__int64)&v39,
      0x1B67u,
      L"IsRebootRequired(%s) returned true for Disk %d",
      v36,
      v30);
    goto LABEL_21;
  }
  v20 = CVssIOCTLChannel::Open((CVssIOCTLChannel *)&v49, (__int64)a2, v36, 0, 0, 0, 0xC0000000, 3u, 0x80u);
  *((_DWORD *)a2 + 2) = v20;
  if ( v20 < 0 )
  {
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1574;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::Trace(a2, &v39, L"Error - Cannot open handle to post-resync disk %s", v36);
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1575;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::AddContextEx((__int64)a2, (__int64)&v39, 0x1B67u, L"Cannot open handle for disk %s", v36);
    goto LABEL_21;
  }
  LOBYTE(v31) = 0;
  v21 = CVssIOCTLChannel::Call(&v49, a2, 2953344, 0, 0, v31, 0);
  *((_DWORD *)a2 + 2) = v21;
  if ( v21 < 0 )
  {
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1584;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::Trace(a2, &v39, L"Error - Cannot find post-resync disk number for %s", v36);
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
    v41 = L"CORHRSNC";
    v42 = 1585;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::AddContextEx((__int64)a2, (__int64)&v39, 0x1B67u, L"Cannot find new disk number for %s", v36);
    goto LABEL_21;
  }
  CVssIOCTLChannel::Unpack<_STORAGE_DEVICE_NUMBER>((__int64)&v49, a2, (__int64)&v61);
  v23 = 0;
  LODWORD(DeviceInfoSet) = 0;
  if ( *((_DWORD *)a6 + 4) )
  {
    do
    {
      v34 = *(CVssHardwareProviderWrapper **)(*(_QWORD *)a6 + 8LL * v23);
      if ( CVssHardwareProviderWrapper::IsMatchLun(
             v34,
             pv,
             (const struct _VDS_LUN_INFORMATION *)(*(_QWORD *)(*((_QWORD *)a6 + 1) + 8LL * v23) + 96LL),
             0) )
      {
        *((_DWORD *)v34 + 10) = 1;
        LODWORD(DeviceInfoData) = *((_DWORD *)v34 + 7);
        if ( (_DWORD)DeviceInfoData != HIDWORD(v61) )
        {
          v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
          v40 = L"CVssHardwareProviderWrapper::RestartDiskIfResyncTarget";
          v41 = L"CORHRSNC";
          v42 = 1605;
          v43 = 1;
          v44 = 255;
          v46 = 0x1000000;
          memset_0(v45, 0, sizeof(v45));
          LODWORD(v32) = HIDWORD(v61);
          LODWORD(v29) = (_DWORD)DeviceInfoData;
          CVssFunctionTracer::Trace(
            a2,
            &v39,
            L"Disk number for %s has changed post restart from %d to %d",
            v36,
            v29,
            v32);
          *((_DWORD *)v34 + 7) = HIDWORD(v61);
        }
      }
      v23 = (_DWORD)DeviceInfoSet + 1;
      LODWORD(DeviceInfoSet) = v23;
      v24 = *((_DWORD *)a6 + 4);
    }
    while ( v23 < v24 );
    for ( j = 0; (unsigned int)j < v24; j = (unsigned int)(j + 1) )
    {
      if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)a6 + 8 * j) + 40LL) )
        break;
    }
  }
  else
  {
    LODWORD(j) = 0;
  }
  v22 = (_DWORD)j == *((_DWORD *)a6 + 4);
LABEL_33:
  v26 = CVssFunctionTracer::Exit(a2, v22);
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v49);
  return v26;
}

```

## disassembly

```asm
0x1400cb0f0  push    rbp
0x1400cb0f2  push    rbx
0x1400cb0f3  push    rsi
0x1400cb0f4  push    rdi
0x1400cb0f5  push    r12
0x1400cb0f7  push    r13
0x1400cb0f9  push    r14
0x1400cb0fb  push    r15
0x1400cb0fd  lea     rbp, [rsp-0E8h]
0x1400cb105  sub     rsp, 1E8h
0x1400cb10c  mov     rax, cs:__security_cookie
0x1400cb113  xor     rax, rsp
0x1400cb116  mov     [rbp+120h+var_50], rax
0x1400cb11d  mov     [rbp+120h+DeviceInfoData], r9
0x1400cb121  mov     [rbp+120h+DeviceInfoSet], r8
0x1400cb125  mov     r14, rdx
0x1400cb128  mov     rsi, rcx
0x1400cb12b  mov     rdi, [rbp+120h+arg_20]
0x1400cb132  mov     [rsp+220h+var_1C0], rdi
0x1400cb137  mov     rbx, [rbp+120h+arg_28]
0x1400cb13e  xor     r13d, r13d
0x1400cb141  mov     [rsp+220h+var_1C8], r13b
0x1400cb146  mov     [rsp+220h+var_1B8], r13d
0x1400cb14b  mov     dword ptr [rbp+120h+ClassInstallParams], r13d
0x1400cb152  xorps   xmm0, xmm0
0x1400cb155  movups  xmmword ptr [rbp+120h+ClassInstallParams+4], xmm0
0x1400cb15c  xor     eax, eax
0x1400cb15e  mov     [rbp+120h+var_78], rax
0x1400cb165  mov     [rbp+120h+var_70], eax
0x1400cb16b  mov     [rbp+120h+var_F0], r13
0x1400cb16f  mov     [rbp+120h+var_C8], r13w
0x1400cb174  mov     [rbp+120h+var_C4], r13
0x1400cb178  mov     [rbp+120h+var_B8], r13
0x1400cb17c  mov     [rbp+120h+var_B0], r13
0x1400cb180  mov     [rbp+120h+var_A8], r13d
0x1400cb184  mov     [rbp+120h+var_A0], r13
0x1400cb18b  mov     [rbp+120h+var_98], r13w
0x1400cb193  mov     [rbp+120h+var_88], r13
0x1400cb19a  lea     rax, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x1400cb1a1  mov     [rbp+120h+var_90], rax
0x1400cb1a8  movups  [rbp+120h+var_E8], xmm0
0x1400cb1ac  movups  [rbp+120h+var_D8], xmm0
0x1400cb1b0  lea     r15d, [r13+60h]
0x1400cb1b4  mov     ecx, r15d; cb
0x1400cb1b7  call    cs:__imp_CoTaskMemAlloc
0x1400cb1bd  mov     r12, rax
0x1400cb1c0  mov     [rsp+220h+pv], rax
0x1400cb1c5  test    rax, rax
0x1400cb1c8  jnz     short loc_1400CB231
0x1400cb1ca  lea     r15, aBaseStorVssMod_28; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400cb1d1  mov     [rsp+220h+var_1A8], r15
0x1400cb1d6  lea     r12, aCvsshardwarepr_33; "CVssHardwareProviderWrapper::RestartDis"...
0x1400cb1dd  mov     [rbp+120h+var_1A0], r12
0x1400cb1e1  lea     r13, aCorhrsnc; "CORHRSNC"
0x1400cb1e8  mov     [rbp+120h+var_198], r13
0x1400cb1ec  mov     [rbp+120h+var_190], 5D6h
0x1400cb1f3  lea     esi, [rax+1]
0x1400cb1f6  mov     [rbp+120h+var_18C], esi
0x1400cb1f9  mov     [rbp+120h+var_188], 0FFh
0x1400cb200  mov     [rbp+120h+var_108], 1000000h
0x1400cb207  xor     edx, edx; Val
0x1400cb209  lea     r8d, [rax+78h]; Size
0x1400cb20d  lea     rcx, [rbp+120h+var_180]; void *
0x1400cb211  call    memset_0
0x1400cb216  lea     r9, aCannotAllocate_19; "Cannot allocate VDS_LUN_INFORMATION"
0x1400cb21d  mov     r8d, 8007000Eh
0x1400cb223  lea     rdx, [rsp+220h+var_1A8]
0x1400cb228  mov     rcx, r14
0x1400cb22b  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400cb231  mov     r8, r15; Size
0x1400cb234  xor     edx, edx; Val
0x1400cb236  mov     rcx, r12; void *
0x1400cb239  call    memset_0
0x1400cb23e  mov     [rsp+220h+var_1F0], r13; unsigned int *
0x1400cb243  mov     [rsp+220h+var_1F8], r13; struct _DISK_SNAPSHOT_INFO **
0x1400cb248  lea     rax, [rsp+220h+var_1C8]
0x1400cb24d  mov     [rsp+220h+var_200], rax; bool *
0x1400cb252  lea     r9, [rsp+220h+var_1B8]; unsigned int *
0x1400cb257  mov     r8, r12; struct _VDS_LUN_INFORMATION *
0x1400cb25a  mov     rdx, rdi; unsigned __int16 *
0x1400cb25d  mov     rcx, rsi; this
0x1400cb260  call    ?BuildLunInfoForDrive@CVssHardwareProviderWrapper@@AEAA_NPEBGPEAU_VDS_LUN_INFORMATION@@PEAKPEA_NPEAPEAU_DISK_SNAPSHOT_INFO@@2@Z; CVssHardwareProviderWrapper::BuildLunInfoForDrive(ushort const *,_VDS_LUN_INFORMATION *,ulong *,bool *,_DISK_SNAPSHOT_INFO * *,ulong *)
0x1400cb265  mov     esi, 1
0x1400cb26a  test    al, al
0x1400cb26c  jnz     short loc_1400CB2D3
0x1400cb26e  lea     r15, aBaseStorVssMod_28; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400cb275  mov     [rsp+220h+var_1A8], r15
0x1400cb27a  lea     r12, aCvsshardwarepr_33; "CVssHardwareProviderWrapper::RestartDis"...
0x1400cb281  mov     [rbp+120h+var_1A0], r12
0x1400cb285  lea     r13, aCorhrsnc; "CORHRSNC"
0x1400cb28c  mov     [rbp+120h+var_198], r13
0x1400cb290  mov     [rbp+120h+var_190], 5DDh
0x1400cb297  mov     [rbp+120h+var_18C], esi
0x1400cb29a  mov     [rbp+120h+var_188], 0FFh
0x1400cb2a1  mov     [rbp+120h+var_108], 1000000h
0x1400cb2a8  xor     edx, edx; Val
0x1400cb2aa  lea     r8d, [rsi+77h]; Size
0x1400cb2ae  lea     rcx, [rbp+120h+var_180]; void *
0x1400cb2b2  call    memset_0
0x1400cb2b7  lea     r8, aCanTToBuildLun; "Can't to build Lun info for drive %s . "...
0x1400cb2be  mov     r9, rdi
0x1400cb2c1  lea     rdx, [rsp+220h+var_1A8]
0x1400cb2c6  mov     rcx, r14
0x1400cb2c9  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400cb2ce  jmp     loc_1400CB7B5
0x1400cb2d3  mov     r15d, r13d
0x1400cb2d6  cmp     [rbx+20h], r13d
0x1400cb2da  jbe     short loc_1400CB303
0x1400cb2dc  mov     eax, r15d
0x1400cb2df  lea     r8, [rax+rax*2]
0x1400cb2e3  shl     r8, 5
0x1400cb2e7  add     r8, [rbx+18h]; struct _VDS_LUN_INFORMATION *
0x1400cb2eb  xor     r9d, r9d; bool
0x1400cb2ee  mov     rdx, r12; struct _VDS_LUN_INFORMATION *
0x1400cb2f1  call    ?IsMatchLun@CVssHardwareProviderWrapper@@AEAA_NAEBU_VDS_LUN_INFORMATION@@0_N@Z; CVssHardwareProviderWrapper::IsMatchLun(_VDS_LUN_INFORMATION const &,_VDS_LUN_INFORMATION const &,bool)
0x1400cb2f6  test    al, al
0x1400cb2f8  jnz     short loc_1400CB303
0x1400cb2fa  add     r15d, esi
0x1400cb2fd  cmp     r15d, [rbx+20h]
0x1400cb301  jb      short loc_1400CB2DC
0x1400cb303  lea     r12, aCvsshardwarepr_33; "CVssHardwareProviderWrapper::RestartDis"...
0x1400cb30a  lea     r13, aCorhrsnc; "CORHRSNC"
0x1400cb311  mov     [rbp+120h+var_18C], esi
0x1400cb314  mov     [rbp+120h+var_108], 1000000h
0x1400cb31b  xor     edx, edx; Val
0x1400cb31d  lea     r8d, [rdx+78h]; Size
0x1400cb321  lea     rcx, [rbp+120h+var_180]; void *
0x1400cb325  mov     [rbp+120h+var_1A0], r12
0x1400cb329  mov     [rbp+120h+var_198], r13
0x1400cb32d  cmp     r15d, [rbx+20h]
0x1400cb331  lea     r15, aBaseStorVssMod_28; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400cb338  mov     [rsp+220h+var_1A8], r15
0x1400cb33d  jnz     short loc_1400CB35E
0x1400cb33f  mov     [rbp+120h+var_190], 5EEh
0x1400cb346  mov     [rbp+120h+var_188], 0FFh
0x1400cb34d  call    memset_0
0x1400cb352  lea     r8, aLunInfoOfDiskS; "Lun info of disk %s not expected. Ignor"...
0x1400cb359  jmp     loc_1400CB2BE
0x1400cb35e  mov     [rbp+120h+var_190], 5F7h
0x1400cb365  mov     edi, 0FFh
0x1400cb36a  mov     [rbp+120h+var_188], edi
0x1400cb36d  call    memset_0
0x1400cb372  mov     r9, [rsp+220h+var_1C0]
0x1400cb377  lea     r8, aRestartingDisk; "Restarting disk device %s"
0x1400cb37e  lea     rdx, [rsp+220h+var_1A8]
0x1400cb383  mov     rcx, r14
0x1400cb386  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400cb38b  mov     dword ptr [rbp+120h+ClassInstallParams], 8
0x1400cb395  mov     dword ptr [rbp+120h+ClassInstallParams+4], 12h
0x1400cb39f  mov     dword ptr [rbp+120h+ClassInstallParams+8], 3
0x1400cb3a9  mov     qword ptr [rbp+120h+ClassInstallParams+0Ch], 2
0x1400cb3b4  mov     r9d, 14h; ClassInstallParamsSize
0x1400cb3ba  lea     r8, [rbp+120h+ClassInstallParams]; ClassInstallParams
0x1400cb3c1  mov     rdx, [rbp+120h+DeviceInfoData]; DeviceInfoData
0x1400cb3c5  mov     rcx, [rbp+120h+DeviceInfoSet]; DeviceInfoSet
0x1400cb3c9  call    cs:__imp_SetupDiSetClassInstallParamsW
0x1400cb3cf  test    eax, eax
0x1400cb3d1  jnz     loc_1400CB49D
0x1400cb3d7  call    cs:__imp_GetLastError
0x1400cb3dd  mov     ebx, eax
0x1400cb3df  mov     [rsp+220h+var_1A8], r15
0x1400cb3e4  mov     [rbp+120h+var_1A0], r12
0x1400cb3e8  mov     [rbp+120h+var_198], r13
0x1400cb3ec  mov     [rbp+120h+var_190], 604h
0x1400cb3f3  mov     [rbp+120h+var_18C], esi
0x1400cb3f6  mov     [rbp+120h+var_188], edi
0x1400cb3f9  mov     [rbp+120h+var_108], 1000000h
0x1400cb400  xor     edx, edx; Val
0x1400cb402  lea     r8d, [rdx+78h]; Size
0x1400cb406  lea     rcx, [rbp+120h+var_180]; void *
0x1400cb40a  call    memset_0
0x1400cb40f  mov     dword ptr [rsp+220h+var_200], ebx
0x1400cb413  mov     r9, [rsp+220h+var_1C0]
0x1400cb418  lea     r8, aSetupdisetclas_1; "SetupDiSetClassInstallParams(%s) fails "...
0x1400cb41f  lea     rdx, [rsp+220h+var_1A8]
0x1400cb424  mov     rcx, r14
0x1400cb427  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400cb42c  call    cs:__imp_GetLastError
0x1400cb432  mov     ebx, eax
0x1400cb434  mov     edi, [rsp+220h+var_1B8]
0x1400cb438  mov     [rsp+220h+var_1A8], r15
0x1400cb43d  mov     [rbp+120h+var_1A0], r12
0x1400cb441  mov     [rbp+120h+var_198], r13
0x1400cb445  mov     [rbp+120h+var_190], 605h
0x1400cb44c  mov     [rbp+120h+var_18C], esi
0x1400cb44f  mov     [rbp+120h+var_188], 0FFh
0x1400cb456  mov     [rbp+120h+var_108], 1000000h
0x1400cb45d  xor     edx, edx; Val
0x1400cb45f  lea     r8d, [rdx+78h]; Size
0x1400cb463  lea     rcx, [rbp+120h+var_180]; void *
0x1400cb467  call    memset_0
0x1400cb46c  lea     r9, aSetupdisetclas_0; "SetupDiSetClassInstallParams(%s) fails "...
0x1400cb473  mov     dword ptr [rsp+220h+var_1F0], ebx
0x1400cb477  mov     dword ptr [rsp+220h+var_1F8], edi
0x1400cb47b  mov     rax, [rsp+220h+var_1C0]
0x1400cb480  mov     [rsp+220h+var_200], rax
0x1400cb485  mov     r8d, 1B67h
0x1400cb48b  lea     rdx, [rsp+220h+var_1A8]
0x1400cb490  mov     rcx, r14
0x1400cb493  call    ?AddContextEx@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBGZZ; CVssFunctionTracer::AddContextEx(CVssDebugInfo,uint,ushort const *,...)
0x1400cb498  jmp     loc_1400CB7B5
0x1400cb49d  mov     r8, [rbp+120h+DeviceInfoData]; DeviceInfoData
0x1400cb4a1  mov     rdx, [rbp+120h+DeviceInfoSet]; DeviceInfoSet
0x1400cb4a5  mov     ecx, 12h; InstallFunction
0x1400cb4aa  call    cs:__imp_SetupDiCallClassInstaller
0x1400cb4b0  test    eax, eax
0x1400cb4b2  jnz     loc_1400CB559
0x1400cb4b8  call    cs:__imp_GetLastError
0x1400cb4be  mov     ebx, eax
0x1400cb4c0  mov     [rsp+220h+var_1A8], r15
0x1400cb4c5  mov     [rbp+120h+var_1A0], r12
0x1400cb4c9  mov     [rbp+120h+var_198], r13
0x1400cb4cd  mov     [rbp+120h+var_190], 60Ch
0x1400cb4d4  mov     [rbp+120h+var_18C], esi
0x1400cb4d7  mov     [rbp+120h+var_188], edi
0x1400cb4da  mov     [rbp+120h+var_108], 1000000h
0x1400cb4e1  xor     edx, edx; Val
0x1400cb4e3  lea     r8d, [rdx+78h]; Size
0x1400cb4e7  lea     rcx, [rbp+120h+var_180]; void *
0x1400cb4eb  call    memset_0
0x1400cb4f0  mov     dword ptr [rsp+220h+var_200], ebx
0x1400cb4f4  mov     r9, [rsp+220h+var_1C0]
0x1400cb4f9  lea     r8, aSetupdicallcla_1; "SetupDiCallClassInstaller(DIF_PROPERTYC"...
0x1400cb500  lea     rdx, [rsp+220h+var_1A8]
0x1400cb505  mov     rcx, r14
0x1400cb508  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400cb50d  call    cs:__imp_GetLastError
0x1400cb513  mov     ebx, eax
0x1400cb515  mov     edi, [rsp+220h+var_1B8]
0x1400cb519  mov     [rsp+220h+var_1A8], r15
0x1400cb51e  mov     [rbp+120h+var_1A0], r12
0x1400cb522  mov     [rbp+120h+var_198], r13
0x1400cb526  mov     [rbp+120h+var_190], 60Dh
0x1400cb52d  mov     [rbp+120h+var_18C], esi
0x1400cb530  mov     [rbp+120h+var_188], 0FFh
0x1400cb537  mov     [rbp+120h+var_108], 1000000h
0x1400cb53e  xor     edx, edx; Val
0x1400cb540  lea     r8d, [rdx+78h]; Size
0x1400cb544  lea     rcx, [rbp+120h+var_180]; void *
0x1400cb548  call    memset_0
0x1400cb54d  lea     r9, aSetupdicallcla_0; "SetupDiCallClassInstaller(DIF_PROPERTYC"...
0x1400cb554  jmp     loc_1400CB473
0x1400cb559  mov     r9, [rsp+220h+var_1C0]; unsigned __int16 *
0x1400cb55e  mov     r8, [rbp+120h+DeviceInfoData]; struct _SP_DEVINFO_DATA *
0x1400cb562  mov     rdx, [rbp+120h+DeviceInfoSet]; void *
0x1400cb566  call    ?IsRebootRequired@CVssHardwareProviderWrapper@@AEAA_NPEAXPEAU_SP_DEVINFO_DATA@@PEBG@Z; CVssHardwareProviderWrapper::IsRebootRequired(void *,_SP_DEVINFO_DATA *,ushort const *)
0x1400cb56b  xor     ecx, ecx
0x1400cb56d  test    al, al
0x1400cb56f  jz      loc_1400CB61F
0x1400cb575  mov     [rsp+220h+var_1A8], r15
0x1400cb57a  mov     [rbp+120h+var_1A0], r12
0x1400cb57e  mov     [rbp+120h+var_198], r13
0x1400cb582  mov     [rbp+120h+var_190], 616h
0x1400cb589  mov     [rbp+120h+var_18C], esi
0x1400cb58c  mov     [rbp+120h+var_188], edi
0x1400cb58f  mov     [rbp+120h+var_108], 1000000h
0x1400cb596  xor     edx, edx; Val
0x1400cb598  lea     r8d, [rcx+78h]; Size
0x1400cb59c  lea     rcx, [rbp+120h+var_180]; void *
0x1400cb5a0  call    memset_0
0x1400cb5a5  mov     r9d, [rsp+220h+var_1B8]
0x1400cb5aa  lea     r8, aDiskDRequiresA; "Disk %d requires a reboot in order to c"...
0x1400cb5b1  lea     rdx, [rsp+220h+var_1A8]
0x1400cb5b6  mov     rcx, r14
0x1400cb5b9  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400cb5be  mov     ebx, [rsp+220h+var_1B8]
0x1400cb5c2  mov     [rsp+220h+var_1A8], r15
0x1400cb5c7  mov     [rbp+120h+var_1A0], r12
0x1400cb5cb  mov     [rbp+120h+var_198], r13
0x1400cb5cf  mov     [rbp+120h+var_190], 617h
0x1400cb5d6  mov     [rbp+120h+var_18C], esi
0x1400cb5d9  mov     [rbp+120h+var_188], edi
0x1400cb5dc  mov     [rbp+120h+var_108], 1000000h
0x1400cb5e3  xor     edx, edx; Val
0x1400cb5e5  lea     r8d, [rdx+78h]; Size
0x1400cb5e9  lea     rcx, [rbp+120h+var_180]; void *
0x1400cb5ed  call    memset_0
0x1400cb5f2  mov     dword ptr [rsp+220h+var_1F8], ebx
0x1400cb5f6  mov     rax, [rsp+220h+var_1C0]
0x1400cb5fb  mov     [rsp+220h+var_200], rax
0x1400cb600  lea     r9, aIsrebootrequir; "IsRebootRequired(%s) returned true for "...
0x1400cb607  mov     r8d, 1B67h
0x1400cb60d  lea     rdx, [rsp+220h+var_1A8]
0x1400cb612  mov     rcx, r14
0x1400cb615  call    ?AddContextEx@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBGZZ; CVssFunctionTracer::AddContextEx(CVssDebugInfo,uint,ushort const *,...)
0x1400cb61a  jmp     loc_1400CB7B5
0x1400cb61f  mov     [rsp+220h+var_1E0], 80h
0x1400cb627  mov     [rsp+220h+var_1E8], 3
0x1400cb62f  mov     dword ptr [rsp+220h+var_1F0], 0C0000000h
0x1400cb637  mov     dword ptr [rsp+220h+var_1F8], ecx
0x1400cb63b  mov     byte ptr [rsp+220h+var_200], cl
0x1400cb63f  xor     r9d, r9d
0x1400cb642  mov     r8, [rsp+220h+var_1C0]
0x1400cb647  mov     rdx, r14
0x1400cb64a  lea     rcx, [rbp+120h+var_F0]
0x1400cb64e  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x1400cb653  mov     [r14+8], eax
0x1400cb657  xor     ecx, ecx
0x1400cb659  test    eax, eax
0x1400cb65b  jns     loc_1400CB6E7
  ... truncated ...
```
