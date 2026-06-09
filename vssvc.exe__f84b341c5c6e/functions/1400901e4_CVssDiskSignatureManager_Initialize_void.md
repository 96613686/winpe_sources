# CVssDiskSignatureManager::Initialize(void)

- ea: `0x1400901e4`
- end: `0x140090b17`
- name: `?Initialize@CVssDiskSignatureManager@@QEAAXXZ`
- size: `2355`
- prototype: `void __fastcall(CVssDiskSignatureManager *__hidden this)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140052640`
- `0x140063f60`
- `0x1400b32f4`

## callees

- `0x140008450`
- `0x140009444`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x140028b48`
- `0x140040a40`
- `0x140065a90`
- `0x14007b37c`
- `0x1400901e4`
- `0x140090b20`
- `0x140091560`
- `0x1400919a0`
- `0x1400921dc`
- `0x1400b2030`
- `0x1400b22f8`
- `0x1400c20e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009051c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009051c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090a1a`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400904ad`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400904ad`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400903ec`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400903ec`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x140090516`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x140090577`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x140090516`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x140090577`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140090352`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140090352`

## string_xrefs

- `0x1400905e6`: `Device path: %s`
- `0x1400903b6`: `DevObjCreateDeviceInfoList(NULL, NULL, NULL, NULL, NULL)`
- `0x1400906ef`: `Unable to open the disk handle of %s. `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CVssDiskSignatureManager::Initialize(CVssDiskSignatureManager *this)
{
  void *v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 DeviceInfoList; // rsi
  int ClassDevs; // eax
  unsigned int i; // edi
  DWORD LastError; // r14d
  _DWORD *v9; // r14
  unsigned __int16 *v10; // r14
  CVssDiskSignatureManager *v11; // rcx
  DWORD v12; // ebx
  DWORD v13; // ebx
  __int64 v14; // [rsp+20h] [rbp-E0h]
  struct _VSS_DISK_ID *v15; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v16; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v17; // [rsp+5Ch] [rbp-A4h] BYREF
  const unsigned __int16 *v18; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+68h] [rbp-98h]
  __int128 v20; // [rsp+78h] [rbp-88h]
  _WORD v21[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v22; // [rsp+8Ch] [rbp-74h]
  __int64 v23; // [rsp+98h] [rbp-68h]
  __int64 v24; // [rsp+A0h] [rbp-60h]
  int v25; // [rsp+A8h] [rbp-58h]
  struct _DRIVE_LAYOUT_INFORMATION_EX *v26; // [rsp+B0h] [rbp-50h]
  __int16 v27; // [rsp+B8h] [rbp-48h]
  void **v28; // [rsp+C0h] [rbp-40h]
  __int64 v29; // [rsp+C8h] [rbp-38h]
  int v30; // [rsp+100h] [rbp+0h]
  const unsigned __int16 *v31; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v32; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v33; // [rsp+120h] [rbp+20h]
  int v34; // [rsp+128h] [rbp+28h]
  int v35; // [rsp+12Ch] [rbp+2Ch]
  int v36; // [rsp+130h] [rbp+30h]
  _BYTE v37[120]; // [rsp+138h] [rbp+38h] BYREF
  int v38; // [rsp+1B0h] [rbp+B0h]
  void **v39; // [rsp+1B8h] [rbp+B8h] BYREF
  _DWORD *v40; // [rsp+1C0h] [rbp+C0h]
  LPVOID v41; // [rsp+1D0h] [rbp+D0h] BYREF
  int v42; // [rsp+1D8h] [rbp+D8h]
  _QWORD v43[2]; // [rsp+240h] [rbp+140h] BYREF
  const unsigned __int16 *v44; // [rsp+250h] [rbp+150h] BYREF
  const wchar_t *v45; // [rsp+258h] [rbp+158h]
  const unsigned __int16 *v46; // [rsp+260h] [rbp+160h]
  int v47; // [rsp+268h] [rbp+168h]
  int v48; // [rsp+26Ch] [rbp+16Ch]
  int v49; // [rsp+270h] [rbp+170h]
  _BYTE v50[120]; // [rsp+278h] [rbp+178h] BYREF
  int v51; // [rsp+2F0h] [rbp+1F0h]
  _QWORD v52[3]; // [rsp+2F8h] [rbp+1F8h] BYREF
  int v53; // [rsp+310h] [rbp+210h]
  int v54; // [rsp+314h] [rbp+214h]
  int v55; // [rsp+318h] [rbp+218h]
  _BYTE v56[120]; // [rsp+320h] [rbp+220h] BYREF
  int v57; // [rsp+398h] [rbp+298h]
  _QWORD v58[3]; // [rsp+3A0h] [rbp+2A0h] BYREF
  int v59; // [rsp+3B8h] [rbp+2B8h]
  int v60; // [rsp+3BCh] [rbp+2BCh]
  int v61; // [rsp+3C0h] [rbp+2C0h]
  _BYTE v62[120]; // [rsp+3C8h] [rbp+2C8h] BYREF
  int v63; // [rsp+440h] [rbp+340h]
  unsigned int v64[2]; // [rsp+448h] [rbp+348h] BYREF
  int v65; // [rsp+450h] [rbp+350h]
  _OWORD v66[2]; // [rsp+458h] [rbp+358h] BYREF
  _OWORD v67[3]; // [rsp+478h] [rbp+378h] BYREF

  v18 = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
  *(_QWORD *)&v19 = L"CVssDiskSignatureManager::Initialize";
  *((_QWORD *)&v19 + 1) = L"HWDVOBJC";
  *(_QWORD *)&v20 = 0x10000022CLL;
  DWORD2(v20) = 255;
  v30 = 0x1000000;
  memset_0(v21, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v41, (__int64)&v18, 0);
  if ( *((_DWORD *)this + 7) )
    goto LABEL_2;
  *(_QWORD *)this = operator new[](0x50u, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 1) = operator new[](0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v2 = operator new[](0x28u, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 2) = v2;
  if ( !*(_QWORD *)this || !*((_QWORD *)this + 1) || !v2 )
  {
    v31 = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
    v32 = L"CVssDiskSignatureManager::Initialize";
    v33 = L"HWDVOBJC";
    v34 = 572;
    v35 = 1;
    v36 = 255;
    v38 = 0x1000000;
    memset_0(v37, 0, sizeof(v37));
    CVssFunctionTracer::Throw(
      &v41,
      &v31,
      2147942414LL,
      L"Fail to alloc array of PVSS_DISK_SIGNATUREs or sizes or local disk numbers");
  }
  memset_0(*(void **)this, 0, 0x50u);
  v3 = *((_QWORD *)this + 1);
  *(_OWORD *)v3 = 0;
  *(_OWORD *)(v3 + 16) = 0;
  *(_QWORD *)(v3 + 32) = 0;
  v4 = *((_QWORD *)this + 2);
  *(_OWORD *)v4 = 0;
  *(_OWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 32) = 0;
  *((_DWORD *)this + 7) = 10;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v43[0] = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v43[1] = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    v18 = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
    *(_QWORD *)&v19 = L"CVssDiskSignatureManager::Initialize";
    *((_QWORD *)&v19 + 1) = L"HWDVOBJC";
    *(_QWORD *)&v20 = 0x10000024DLL;
    DWORD2(v20) = 255;
    v30 = 0x1000000;
    memset_0(v21, 0, 0x78u);
    CVssFunctionTracer::TranslateWin32Error(&v41, &v18, L"DevObjCreateDeviceInfoList(NULL, NULL, NULL, NULL, NULL)");
  }
  ClassDevs = DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0);
  v18 = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
  *(_QWORD *)&v19 = L"CVssDiskSignatureManager::Initialize";
  *(_QWORD *)((char *)&v20 + 4) = 0xFF00000001LL;
  v30 = 0x1000000;
  *((_QWORD *)&v19 + 1) = L"HWDVOBJC";
  if ( !ClassDevs )
  {
    LODWORD(v20) = 599;
    memset_0(v21, 0, 0x78u);
    CVssFunctionTracer::TranslateWin32Error(
      &v41,
      &v18,
      L"DevObjGetClassDevs(&, NULL, NULL, DOGCF_DEVICEINTERFACE | DOGCF_PRESENT, NULL, NULL)");
  }
  memset(v66, 0, sizeof(v66));
  LODWORD(v66[0]) = 32;
  LODWORD(v20) = 609;
  memset_0(v21, 0, 0x78u);
  CVssFunctionTracer::Trace(&v41, &v18, L"Enumerating all disks in system for disk signatures: ");
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_DEVINTERFACE_DISK, i, v66); ++i )
  {
    v40 = 0;
    v39 = &CVssAuto<unsigned short * *,CVssAutoCppPtr_Storage<unsigned short * *>>::`vftable';
    memset(v67, 0, sizeof(v67));
    LODWORD(v67[0]) = 48;
    v16 = 0;
    DevObjGetDeviceInterfaceDetail(DeviceInfoList, v66, 0, 0, &v16, 0);
    LastError = GetLastError();
    if ( LastError != 122 || !v16 )
    {
      v31 = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
      v32 = L"CVssDiskSignatureManager::Initialize";
      v33 = L"HWDVOBJC";
      v34 = 655;
      v35 = 1;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::TranslateWin32Error(
        &v41,
        &v31,
        L"DevObjGetDeviceInterfaceDetail(devInfo, &, NULL, 0, &, NULL) fails winerror %d",
        LastError);
    }
    CVssAutoCppPtr_Storage<unsigned char *>::AllocateBytes(&v39);
    v9 = v40;
    *v40 = 8;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v66, v9, v16, 0, v67) )
    {
      v12 = GetLastError();
      v31 = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
      v32 = L"CVssDiskSignatureManager::Initialize";
      v33 = L"HWDVOBJC";
      v34 = 672;
      v35 = 1;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::TranslateWin32Error(
        &v41,
        &v31,
        L"DevObjGetDeviceInterfaceDetail(devInfo, &, detail, dwBytes, NULL, &) fails winerror %d",
        v12);
    }
    v10 = (unsigned __int16 *)(v9 + 1);
    v44 = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
    v45 = L"CVssDiskSignatureManager::Initialize";
    v46 = L"HWDVOBJC";
    v47 = 674;
    v48 = 1;
    v49 = 255;
    v51 = 0x1000000;
    memset_0(v50, 0, sizeof(v50));
    CVssFunctionTracer::Trace(&v41, &v44, L"Device path: %s", v10);
    v18 = 0;
    v21[0] = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v29 = 0;
    v28 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    v19 = 0;
    v20 = 0;
    *(_QWORD *)v64 = 0;
    v65 = 0;
    v42 = CVssIOCTLChannel::Open((CVssIOCTLChannel *)&v18, (__int64)&v41, v10, 0, 0, 0, 0x80000000, 3u, 0x80u);
    if ( v42 < 0 )
    {
      v52[0] = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
      v52[1] = L"CVssDiskSignatureManager::Initialize";
      v52[2] = L"HWDVOBJC";
      v53 = 692;
      v54 = 1;
      v55 = 255;
      v57 = 0x1000000;
      memset_0(v56, 0, sizeof(v56));
      CVssFunctionTracer::Trace(&v41, v52, L"Unable to open the disk handle of %s. ", v10);
      goto LABEL_17;
    }
    v42 = CVssIOCTLChannel::Call(&v18, (__int64)&v41, 0x2D1080u, 0, 0, 0, 0);
    if ( v42 < 0 )
    {
      v58[0] = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
      v58[1] = L"CVssDiskSignatureManager::Initialize";
      v58[2] = L"HWDVOBJC";
      v59 = 705;
      v60 = 1;
      v61 = 255;
      v63 = 0x1000000;
      memset_0(v62, 0, sizeof(v62));
      CVssFunctionTracer::Trace(&v41, v58, L"Unable to get the disk number of %s", v10);
      goto LABEL_17;
    }
    CVssIOCTLChannel::Unpack<_STORAGE_DEVICE_NUMBER>((__int64)&v18, (struct CVssFunctionTracer *)&v41, (__int64)v64);
    LODWORD(v22) = 0;
    LODWORD(v24) = 0;
    v42 = CVssIOCTLChannel::Call(&v18, (__int64)&v41, 0x70050u, 0, 0, 0, 0);
    if ( v42 < 0 )
    {
      v31 = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
      v32 = L"CVssDiskSignatureManager::Initialize";
      v33 = L"HWDVOBJC";
      v34 = 718;
      v35 = 1;
      v36 = 255;
      v38 = 0x1000000;
      memset_0(v37, 0, sizeof(v37));
      CVssFunctionTracer::Trace(
        &v41,
        &v31,
        L"Unable to get the drive layout of %s. Could be a USB drive or other media",
        v10);
LABEL_17:
      v42 = 0;
LABEL_18:
      CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v18);
      goto LABEL_27;
    }
    v17 = 0;
    v15 = 0;
    CVssDiskSignatureManager::DriveLayoutToDiskId(v11, v26, &v15, &v17);
    if ( v17 && v15 )
    {
      CVssDiskSignatureManager::AddToInternalSet(this, v15, v17, v64[1]);
      goto LABEL_18;
    }
    v44 = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
    v45 = L"CVssDiskSignatureManager::Initialize";
    v46 = L"HWDVOBJC";
    v47 = 733;
    v48 = 1;
    v49 = 255;
    v51 = 0x1000000;
    memset_0(v50, 0, sizeof(v50));
    CVssFunctionTracer::Trace(&v41, &v44, L"No disk id found for disk %d", v64[1]);
    CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v18);
LABEL_27:
    CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>::~CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>(&v39);
  }
  v13 = GetLastError();
  v31 = L"base\\stor\\vss\\modules\\coord\\src\\hwdeviceobj.cxx";
  v32 = L"CVssDiskSignatureManager::Initialize";
  v35 = 1;
  v36 = 255;
  v38 = 0x1000000;
  v33 = L"HWDVOBJC";
  if ( v13 != 259 )
  {
    v34 = 628;
    memset_0(v37, 0, sizeof(v37));
    LODWORD(v14) = v13;
    CVssFunctionTracer::TranslateWin32Error(
      &v41,
      &v31,
      L"DevObjEnumDeviceInterfaces(devInfo, NULL, &, [%d], &) fails winerror %d",
      i,
      v14);
  }
  v34 = 741;
  memset_0(v37, 0, sizeof(v37));
  CVssFunctionTracer::Trace(&v41, &v31, L"End disk enumeration for disk signatures");
  CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(v43);
LABEL_2:
  CVssFunctionTracer::~CVssFunctionTracer(&v41);
}

```

## disassembly

```asm
0x1400901e4  push    rbp
0x1400901e6  push    rbx
0x1400901e7  push    rsi
0x1400901e8  push    rdi
0x1400901e9  push    r12
0x1400901eb  push    r13
0x1400901ed  push    r14
0x1400901ef  push    r15
0x1400901f1  lea     rbp, [rsp-3B8h]
0x1400901f9  sub     rsp, 4B8h
0x140090200  mov     rax, cs:__security_cookie
0x140090207  xor     rax, rsp
0x14009020a  mov     [rbp+3F0h+var_48], rax
0x140090211  mov     rbx, rcx
0x140090214  lea     r13, aBaseStorVssMod_29; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14009021b  mov     [rsp+4F0h+var_490], r13
0x140090220  lea     r14, aCvssdisksignat_13; "CVssDiskSignatureManager::Initialize"
0x140090227  mov     qword ptr [rsp+4F0h+var_488], r14
0x14009022c  lea     rax, aHwdvobjc; "HWDVOBJC"
0x140090233  mov     qword ptr [rsp+4F0h+var_488+8], rax
0x140090238  mov     dword ptr [rsp+4F0h+var_478], 22Ch
0x140090240  mov     r12d, 1
0x140090246  mov     dword ptr [rsp+4F0h+var_478+4], r12d
0x14009024b  mov     dword ptr [rbp+3F0h+var_478+8], 0FFh
0x140090252  xor     r15d, r15d
0x140090255  mov     [rbp+3F0h+var_3F0], 1000000h
0x14009025c  xor     edx, edx; Val
0x14009025e  lea     r8d, [r12+77h]; Size
0x140090263  lea     rcx, [rbp+3F0h+var_468]; void *
0x140090267  call    memset_0
0x14009026c  xor     r8d, r8d
0x14009026f  lea     rdx, [rsp+4F0h+var_490]
0x140090274  lea     rcx, [rbp+3F0h+var_320]
0x14009027b  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140090280  nop
0x140090281  cmp     [rbx+1Ch], r15d
0x140090285  jz      short loc_1400902B6
0x140090287  lea     rcx, [rbp+3F0h+var_320]; this
0x14009028e  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140090293  mov     rcx, [rbp+3F0h+var_48]
0x14009029a  xor     rcx, rsp; StackCookie
0x14009029d  call    __security_check_cookie
0x1400902a2  add     rsp, 4B8h
0x1400902a9  pop     r15
0x1400902ab  pop     r14
0x1400902ad  pop     r13
0x1400902af  pop     r12
0x1400902b1  pop     rdi
0x1400902b2  pop     rsi
0x1400902b3  pop     rbx
0x1400902b4  pop     rbp
0x1400902b5  retn
0x1400902b6  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1400902bd  mov     rdx, rsi; struct std::nothrow_t *
0x1400902c0  mov     ecx, 50h ; 'P'; unsigned __int64
0x1400902c5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400902ca  mov     [rbx], rax
0x1400902cd  mov     rdx, rsi; struct std::nothrow_t *
0x1400902d0  mov     edi, 28h ; '('
0x1400902d5  mov     ecx, edi; unsigned __int64
0x1400902d7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400902dc  mov     [rbx+8], rax
0x1400902e0  mov     rdx, rsi; struct std::nothrow_t *
0x1400902e3  mov     ecx, edi; unsigned __int64
0x1400902e5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400902ea  mov     [rbx+10h], rax
0x1400902ee  mov     rcx, [rbx]; void *
0x1400902f1  test    rcx, rcx
0x1400902f4  jz      loc_140090ABB
0x1400902fa  cmp     [rbx+8], r15
0x1400902fe  jz      loc_140090ABB
0x140090304  test    rax, rax
0x140090307  jz      loc_140090ABB
0x14009030d  xor     edx, edx; Val
0x14009030f  lea     r8d, [rdi+28h]; Size
0x140090313  call    memset_0
0x140090318  xorps   xmm0, xmm0
0x14009031b  xor     ecx, ecx
0x14009031d  mov     rax, [rbx+8]
0x140090321  movups  xmmword ptr [rax], xmm0
0x140090324  movups  xmmword ptr [rax+10h], xmm0
0x140090328  mov     [rax+20h], rcx
0x14009032c  xorps   xmm1, xmm1
0x14009032f  mov     rax, [rbx+10h]
0x140090333  movups  xmmword ptr [rax], xmm1
0x140090336  movups  xmmword ptr [rax+10h], xmm1
0x14009033a  mov     [rax+20h], rcx
0x14009033e  mov     dword ptr [rbx+1Ch], 0Ah
0x140090345  mov     [rsp+4F0h+var_4D0], r15
0x14009034a  xor     r9d, r9d
0x14009034d  xor     r8d, r8d
0x140090350  xor     edx, edx
0x140090352  call    cs:__imp_DevObjCreateDeviceInfoList
0x140090358  mov     rsi, rax
0x14009035b  lea     rax, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x140090362  mov     [rbp+3F0h+var_2B0], rax
0x140090369  mov     [rbp+3F0h+var_2A8], rsi
0x140090370  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140090374  jnz     short loc_1400903CF
0x140090376  mov     [rsp+4F0h+var_490], r13
0x14009037b  mov     qword ptr [rsp+4F0h+var_488], r14
0x140090380  lea     rax, aHwdvobjc; "HWDVOBJC"
0x140090387  mov     qword ptr [rsp+4F0h+var_488+8], rax
0x14009038c  mov     dword ptr [rsp+4F0h+var_478], 24Dh
0x140090394  mov     dword ptr [rsp+4F0h+var_478+4], r12d
0x140090399  mov     dword ptr [rbp+3F0h+var_478+8], 0FFh
0x1400903a0  mov     [rbp+3F0h+var_3F0], 1000000h
0x1400903a7  xor     edx, edx; Val
0x1400903a9  lea     r8d, [rdi+50h]; Size
0x1400903ad  lea     rcx, [rbp+3F0h+var_468]; void *
0x1400903b1  call    memset_0
0x1400903b6  lea     r8, aDevobjcreatede_0; "DevObjCreateDeviceInfoList(NULL, NULL, "...
0x1400903bd  lea     rdx, [rsp+4F0h+var_490]
0x1400903c2  lea     rcx, [rbp+3F0h+var_320]
0x1400903c9  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400903cf  mov     [rsp+4F0h+var_4C8], r15
0x1400903d4  mov     [rsp+4F0h+var_4D0], r15
0x1400903d9  mov     r9d, 12h
0x1400903df  xor     r8d, r8d
0x1400903e2  lea     rdx, GUID_DEVINTERFACE_DISK
0x1400903e9  mov     rcx, rsi
0x1400903ec  call    cs:__imp_DevObjGetClassDevs
0x1400903f2  mov     [rsp+4F0h+var_490], r13
0x1400903f7  mov     qword ptr [rsp+4F0h+var_488], r14
0x1400903fc  mov     dword ptr [rsp+4F0h+var_478+4], r12d
0x140090401  mov     dword ptr [rbp+3F0h+var_478+8], 0FFh
0x140090408  mov     [rbp+3F0h+var_3F0], 1000000h
0x14009040f  xor     edx, edx; Val
0x140090411  lea     r8d, [rdx+78h]; Size
0x140090415  lea     rcx, [rbp+3F0h+var_468]; void *
0x140090419  test    eax, eax
0x14009041b  lea     rax, aHwdvobjc; "HWDVOBJC"
0x140090422  mov     qword ptr [rsp+4F0h+var_488+8], rax
0x140090427  jnz     short loc_14009044F
0x140090429  mov     dword ptr [rsp+4F0h+var_478], 257h
0x140090431  call    memset_0
0x140090436  lea     r8, aDevobjgetclass_3; "DevObjGetClassDevs(&, NULL, NULL, DOGCF"...
0x14009043d  lea     rdx, [rsp+4F0h+var_490]
0x140090442  lea     rcx, [rbp+3F0h+var_320]
0x140090449  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x14009044f  xorps   xmm0, xmm0
0x140090452  movups  [rbp+3F0h+var_98], xmm0
0x140090459  movups  [rbp+3F0h+var_88], xmm0
0x140090460  mov     dword ptr [rbp+3F0h+var_98], 20h ; ' '
0x14009046a  mov     dword ptr [rsp+4F0h+var_478], 261h
0x140090472  call    memset_0
0x140090477  lea     r8, aEnumeratingAll_0; "Enumerating all disks in system for dis"...
0x14009047e  lea     rdx, [rsp+4F0h+var_490]
0x140090483  lea     rcx, [rbp+3F0h+var_320]
0x14009048a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14009048f  mov     edi, r15d
0x140090492  lea     rax, [rbp+3F0h+var_98]
0x140090499  mov     [rsp+4F0h+var_4D0], rax
0x14009049e  mov     r9d, edi
0x1400904a1  lea     r8, GUID_DEVINTERFACE_DISK
0x1400904a8  xor     edx, edx
0x1400904aa  mov     rcx, rsi
0x1400904ad  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1400904b3  test    eax, eax
0x1400904b5  jz      loc_140090A1A
0x1400904bb  mov     [rbp+3F0h+var_330], r15
0x1400904c2  lea     rax, ??_7?$CVssAuto@PEAPEAGV?$CVssAutoCppPtr_Storage@PEAPEAG@@@@6B@; const CVssAuto<ushort * *,CVssAutoCppPtr_Storage<ushort * *>>::`vftable'
0x1400904c9  mov     [rbp+3F0h+var_338], rax
0x1400904d0  xorps   xmm0, xmm0
0x1400904d3  movups  [rbp+3F0h+var_78], xmm0
0x1400904da  movups  [rbp+3F0h+var_68], xmm0
0x1400904e1  movups  [rbp+3F0h+var_58], xmm0
0x1400904e8  mov     dword ptr [rbp+3F0h+var_78], 30h ; '0'
0x1400904f2  mov     [rsp+4F0h+var_498], r15d
0x1400904f7  mov     [rsp+4F0h+var_4C8], r15
0x1400904fc  lea     rax, [rsp+4F0h+var_498]
0x140090501  mov     [rsp+4F0h+var_4D0], rax
0x140090506  xor     r9d, r9d
0x140090509  xor     r8d, r8d
0x14009050c  lea     rdx, [rbp+3F0h+var_98]
0x140090513  mov     rcx, rsi
0x140090516  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x14009051c  call    cs:__imp_GetLastError
0x140090522  mov     r14d, eax
0x140090525  cmp     eax, 7Ah ; 'z'
0x140090528  jnz     loc_1400909BA
0x14009052e  mov     edx, [rsp+4F0h+var_498]
0x140090532  test    edx, edx
0x140090534  jz      loc_1400909BA
0x14009053a  lea     rcx, [rbp+3F0h+var_338]
0x140090541  call    ?AllocateBytes@?$CVssAutoCppPtr_Storage@PEAE@@QEAAXK@Z; CVssAutoCppPtr_Storage<uchar *>::AllocateBytes(ulong)
0x140090546  mov     r14, [rbp+3F0h+var_330]
0x14009054d  mov     dword ptr [r14], 8
0x140090554  lea     rax, [rbp+3F0h+var_78]
0x14009055b  mov     [rsp+4F0h+var_4C8], rax
0x140090560  mov     [rsp+4F0h+var_4D0], r15
0x140090565  mov     r9d, [rsp+4F0h+var_498]
0x14009056a  mov     r8, r14
0x14009056d  lea     rdx, [rbp+3F0h+var_98]
0x140090574  mov     rcx, rsi
0x140090577  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x14009057d  test    eax, eax
0x14009057f  jz      loc_140090952
0x140090585  add     r14, 4
0x140090589  mov     [rbp+3F0h+var_2A0], r13
0x140090590  lea     rax, aCvssdisksignat_13; "CVssDiskSignatureManager::Initialize"
0x140090597  mov     [rbp+3F0h+var_298], rax
0x14009059e  lea     rax, aHwdvobjc; "HWDVOBJC"
0x1400905a5  mov     [rbp+3F0h+var_290], rax
0x1400905ac  mov     [rbp+3F0h+var_288], 2A2h
0x1400905b6  mov     [rbp+3F0h+var_284], r12d
0x1400905bd  mov     [rbp+3F0h+var_280], 0FFh
0x1400905c7  mov     [rbp+3F0h+var_200], 1000000h
0x1400905d1  xor     edx, edx; Val
0x1400905d3  lea     r8d, [rdx+78h]; Size
0x1400905d7  lea     rcx, [rbp+3F0h+var_278]; void *
0x1400905de  call    memset_0
0x1400905e3  mov     r9, r14
0x1400905e6  lea     r8, aDevicePathS; "Device path: %s"
0x1400905ed  lea     rdx, [rbp+3F0h+var_2A0]
0x1400905f4  lea     rcx, [rbp+3F0h+var_320]
0x1400905fb  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140090600  mov     [rsp+4F0h+var_490], r15
0x140090605  mov     [rbp+3F0h+var_468], r15w
0x14009060a  mov     [rbp+3F0h+var_464], r15
0x14009060e  mov     [rbp+3F0h+var_458], r15
0x140090612  mov     [rbp+3F0h+var_450], r15
0x140090616  mov     [rbp+3F0h+var_448], r15d
0x14009061a  mov     [rbp+3F0h+var_440], r15
0x14009061e  mov     [rbp+3F0h+var_438], r15w
0x140090623  mov     [rbp+3F0h+var_428], r15
0x140090627  lea     rax, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x14009062e  mov     [rbp+3F0h+var_430], rax
0x140090632  xorps   xmm0, xmm0
0x140090635  movups  [rsp+4F0h+var_488], xmm0
0x14009063a  movups  [rsp+4F0h+var_478], xmm0
0x14009063f  xor     eax, eax
0x140090641  mov     qword ptr [rbp+3F0h+var_A8], rax
0x140090648  mov     [rbp+3F0h+var_A0], eax
0x14009064e  mov     [rsp+4F0h+var_4B0], 80h
0x140090656  mov     [rsp+4F0h+var_4B8], 3
0x14009065e  mov     dword ptr [rsp+4F0h+var_4C0], 80000000h
0x140090666  mov     dword ptr [rsp+4F0h+var_4C8], r15d
0x14009066b  mov     byte ptr [rsp+4F0h+var_4D0], r15b
0x140090670  xor     r9d, r9d
0x140090673  mov     r8, r14
0x140090676  lea     rdx, [rbp+3F0h+var_320]
0x14009067d  lea     rcx, [rsp+4F0h+var_490]
0x140090682  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x140090687  mov     [rbp+3F0h+var_318], eax
0x14009068d  test    eax, eax
0x14009068f  jns     loc_14009072A
0x140090695  mov     [rbp+3F0h+var_1F8], r13
0x14009069c  lea     rax, aCvssdisksignat_13; "CVssDiskSignatureManager::Initialize"
0x1400906a3  mov     [rbp+3F0h+var_1F0], rax
0x1400906aa  lea     rax, aHwdvobjc; "HWDVOBJC"
0x1400906b1  mov     [rbp+3F0h+var_1E8], rax
0x1400906b8  mov     [rbp+3F0h+var_1E0], 2B4h
0x1400906c2  mov     [rbp+3F0h+var_1DC], r12d
0x1400906c9  mov     [rbp+3F0h+var_1D8], 0FFh
0x1400906d3  mov     [rbp+3F0h+var_158], 1000000h
0x1400906dd  xor     edx, edx; Val
0x1400906df  lea     r8d, [rdx+78h]; Size
0x1400906e3  lea     rcx, [rbp+3F0h+var_1D0]; void *
0x1400906ea  call    memset_0
0x1400906ef  lea     r8, aUnableToOpenTh; "Unable to open the disk handle of %s. "
0x1400906f6  lea     rdx, [rbp+3F0h+var_1F8]
0x1400906fd  mov     r9, r14
0x140090700  lea     rcx, [rbp+3F0h+var_320]
0x140090707  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14009070c  mov     [rbp+3F0h+var_318], r15d
0x140090713  lea     rcx, [rsp+4F0h+var_490]; this
0x140090718  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x14009071d  nop
0x14009071e  lea     r14, aCvssdisksignat_13; "CVssDiskSignatureManager::Initialize"
0x140090725  jmp     loc_14009093E
0x14009072a  mov     [rsp+4F0h+var_4C0], r15
0x14009072f  mov     byte ptr [rsp+4F0h+var_4C8], r15b
0x140090734  mov     dword ptr [rsp+4F0h+var_4D0], r15d
0x140090739  xor     r9d, r9d
0x14009073c  mov     r8d, 2D1080h
0x140090742  lea     rdx, [rbp+3F0h+var_320]
0x140090749  lea     rcx, [rsp+4F0h+var_490]
0x14009074e  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x140090753  mov     [rbp+3F0h+var_318], eax
0x140090759  test    eax, eax
0x14009075b  jns     short loc_1400907CA
0x14009075d  mov     [rbp+3F0h+var_150], r13
0x140090764  lea     rax, aCvssdisksignat_13; "CVssDiskSignatureManager::Initialize"
0x14009076b  mov     [rbp+3F0h+var_148], rax
0x140090772  lea     rax, aHwdvobjc; "HWDVOBJC"
0x140090779  mov     [rbp+3F0h+var_140], rax
0x140090780  mov     [rbp+3F0h+var_138], 2C1h
0x14009078a  mov     [rbp+3F0h+var_134], r12d
0x140090791  mov     [rbp+3F0h+var_130], 0FFh
0x14009079b  mov     [rbp+3F0h+var_B0], 1000000h
0x1400907a5  xor     edx, edx; Val
0x1400907a7  lea     r8d, [rdx+78h]; Size
0x1400907ab  lea     rcx, [rbp+3F0h+var_128]; void *
0x1400907b2  call    memset_0
0x1400907b7  lea     r8, aUnableToGetThe_0; "Unable to get the disk number of %s"
0x1400907be  lea     rdx, [rbp+3F0h+var_150]
0x1400907c5  jmp     loc_1400906FD
0x1400907ca  lea     r8, [rbp+3F0h+var_A8]
0x1400907d1  lea     rdx, [rbp+3F0h+var_320]
  ... truncated ...
```
