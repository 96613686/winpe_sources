# CVssHardwareProviderWrapper::BuildLunInfoFromVolume(ushort const *,uchar * &,uint &,ushort * * &,_VDS_LUN_INFORMATION * &,_GUID * &,bool *)

- ea: `0x140074528`
- end: `0x14007528e`
- name: `?BuildLunInfoFromVolume@CVssHardwareProviderWrapper@@AEAA_NPEBGAEAPEAEAEAIAEAPEAPEAGAEAPEAU_VDS_LUN_INFORMATION@@AEAPEAU_GUID@@PEA_N@Z`
- size: `3430`
- prototype: `bool __fastcall(CVssHardwareProviderWrapper *__hidden this, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int16 ***, struct _VDS_LUN_INFORMATION **, struct _GUID **, bool *)`
- caller_count: `7`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14004c618`
- `0x14004ca84`
- `0x140051a40`
- `0x1400bac8c`
- `0x1400bb520`
- `0x1400c9d34`
- `0x1400ca888`

## callees

- `0x140008450`
- `0x140008908`
- `0x140009444`
- `0x14000a834`
- `0x140011a90`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x140025b00`
- `0x14003fc04`
- `0x14004ce80`
- `0x140065a90`
- `0x140074528`
- `0x140075294`
- `0x14007dda4`
- `0x14008de40`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140074f7c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14007500c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400750ba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140074f7c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14007500c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400750ba`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x140074a92`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x140074a92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140074ade`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140074bac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140074c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140074dbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140074ade`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140074bac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140074c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140074dbf`

## string_xrefs

- `0x14007484c`: `Fail to open handle to volume hr 0x%08lx `
- `0x140074f03`: `StringCchCopy fail to copy device path.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
bool __fastcall CVssHardwareProviderWrapper::BuildLunInfoFromVolume(
        CVssHardwareProviderWrapper *this,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int16 ***a5,
        struct _VDS_LUN_INFORMATION **a6,
        struct _GUID **a7,
        bool *a8)
{
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // rax
  CVssHardwareProviderWrapper *v12; // rcx
  int v13; // esi
  __int64 v14; // r9
  bool v15; // bl
  int v17; // esi
  unsigned int *v18; // r12
  size_t v19; // rsi
  unsigned int v20; // ebx
  unsigned int v21; // r15d
  unsigned int i; // r8d
  unsigned int v23; // edx
  unsigned int v24; // ecx
  unsigned int v25; // eax
  struct _VDS_LUN_INFORMATION *v26; // rax
  unsigned __int16 **v27; // rax
  GUID *v28; // rax
  struct _GUID *v29; // r13
  unsigned int j; // ecx
  unsigned int v31; // ebx
  __int64 v32; // rsi
  unsigned int k; // r14d
  unsigned int v34; // eax
  __int64 v35; // rcx
  unsigned __int16 *v36; // rax
  __int64 v37; // rdx
  bool v38; // bl
  void *v39; // rcx
  bool v40; // dl
  bool v41; // bl
  int v42; // [rsp+28h] [rbp-360h]
  struct _VDS_LUN_INFORMATION *v43; // [rsp+50h] [rbp-338h]
  unsigned int v45; // [rsp+60h] [rbp-328h] BYREF
  int v46; // [rsp+64h] [rbp-324h]
  void *Block; // [rsp+68h] [rbp-320h] BYREF
  void *v48; // [rsp+70h] [rbp-318h] BYREF
  unsigned int v49; // [rsp+78h] [rbp-310h]
  unsigned int v50; // [rsp+7Ch] [rbp-30Ch]
  unsigned __int16 **v51; // [rsp+80h] [rbp-308h]
  void **v52; // [rsp+90h] [rbp-2F8h] BYREF
  GUID *v53; // [rsp+98h] [rbp-2F0h]
  void **v54; // [rsp+A0h] [rbp-2E8h] BYREF
  unsigned __int16 **v55; // [rsp+A8h] [rbp-2E0h]
  void **v56; // [rsp+B0h] [rbp-2D8h] BYREF
  struct _VDS_LUN_INFORMATION *v57; // [rsp+B8h] [rbp-2D0h]
  LPVOID v58; // [rsp+C0h] [rbp-2C8h] BYREF
  int v59; // [rsp+C8h] [rbp-2C0h]
  const unsigned __int16 *v60; // [rsp+130h] [rbp-258h] BYREF
  const unsigned __int16 *v61; // [rsp+138h] [rbp-250h]
  const unsigned __int16 *v62; // [rsp+140h] [rbp-248h]
  int v63; // [rsp+148h] [rbp-240h]
  int v64; // [rsp+14Ch] [rbp-23Ch]
  int v65; // [rsp+150h] [rbp-238h]
  _BYTE v66[120]; // [rsp+158h] [rbp-230h] BYREF
  int v67; // [rsp+1D0h] [rbp-1B8h]
  bool *v68; // [rsp+1E0h] [rbp-1A8h]
  CVssHardwareProviderWrapper *v69; // [rsp+1E8h] [rbp-1A0h]
  unsigned __int8 **v70; // [rsp+1F0h] [rbp-198h]
  unsigned __int16 ***v71; // [rsp+1F8h] [rbp-190h]
  struct _VDS_LUN_INFORMATION **v72; // [rsp+200h] [rbp-188h]
  struct _GUID **v73; // [rsp+208h] [rbp-180h]
  __int64 v74; // [rsp+210h] [rbp-178h] BYREF
  __int128 v75; // [rsp+218h] [rbp-170h]
  __int128 v76; // [rsp+228h] [rbp-160h]
  __int16 v77; // [rsp+238h] [rbp-150h]
  __int64 v78; // [rsp+23Ch] [rbp-14Ch]
  __int64 v79; // [rsp+248h] [rbp-140h]
  __int64 v80; // [rsp+250h] [rbp-138h]
  int v81; // [rsp+258h] [rbp-130h]
  unsigned int *v82; // [rsp+260h] [rbp-128h]
  __int16 v83; // [rsp+268h] [rbp-120h]
  void **v84; // [rsp+270h] [rbp-118h]
  __int64 v85; // [rsp+278h] [rbp-110h]
  unsigned __int16 v86[4]; // [rsp+290h] [rbp-F8h] BYREF
  const unsigned __int16 *v87; // [rsp+298h] [rbp-F0h]
  const unsigned __int16 *v88; // [rsp+2A0h] [rbp-E8h]
  int v89; // [rsp+2A8h] [rbp-E0h]
  int v90; // [rsp+2ACh] [rbp-DCh]
  int v91; // [rsp+2B0h] [rbp-D8h]
  _BYTE v92[120]; // [rsp+2B8h] [rbp-D0h] BYREF
  int v93; // [rsp+330h] [rbp-58h]

  v70 = a3;
  v69 = this;
  v71 = a5;
  v72 = a6;
  v73 = a7;
  v68 = a8;
  *(_QWORD *)v86 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v87 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
  v88 = L"CORHWUTC";
  v89 = 106;
  v90 = 1;
  v91 = 255;
  v93 = 0x1000000;
  memset_0(v92, 0, sizeof(v92));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v58, (__int64)v86, 0);
  *(_QWORD *)v86 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v87 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
  v88 = L"CORHWUTC";
  v89 = 108;
  v90 = 1;
  v91 = 255;
  v93 = 0x1000000;
  memset_0(v92, 0, sizeof(v92));
  CVssFunctionTracer::AddContext((__int64)&v58, (__int64)v86, 6006, (__int64)a2);
  *(_QWORD *)v86 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v87 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
  v88 = L"CORHWUTC";
  v89 = 109;
  v90 = 6;
  v91 = 255;
  v93 = 0x1000000;
  memset_0(v92, 0, sizeof(v92));
  CVssFunctionTracer::Trace(&v58, v86, L"Build LUN info for volume %s ...", a2);
  if ( !a2 )
    goto LABEL_50;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  if ( v10 )
  {
    v74 = 0;
    v77 = 0;
    v78 = 0;
    v79 = 0;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    v83 = 0;
    v85 = 0;
    v84 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    v75 = 0;
    v76 = 0;
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    LOBYTE(v9) = a2[v11 - 1] == 92;
    v13 = CVssIOCTLChannel::Open(&v74, &v58, a2, v9, 1, 2, -1073741824, 3, 128);
    v59 = v13;
    if ( v13 < 0 )
    {
      *(_QWORD *)v86 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v87 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
      v88 = L"CORHWUTC";
      v89 = 135;
      v90 = 1;
      v91 = 255;
      v93 = 0x1000000;
      memset_0(v92, 0, sizeof(v92));
      CVssFunctionTracer::Trace(&v58, v86, L"Fail to open handle to volume hr 0x%08lx ", (unsigned int)v13);
    }
    if ( CVssHardwareProviderWrapper::IsDeviceCDRom(v12, (struct CVssIOCTLChannel *)&v74) )
    {
      *(_QWORD *)v86 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v87 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
      v88 = L"CORHWUTC";
      v89 = 140;
      v90 = 1;
      v91 = 255;
      v93 = 0x1000000;
      memset_0(v92, 0, sizeof(v92));
      CVssFunctionTracer::Trace(&v58, v86, L"Device %s is a CD-ROM and therefore is not supported.  Skipping.", a2);
      v15 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v58, 0);
      CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v74);
      CVssFunctionTracer::~CVssFunctionTracer(&v58);
      return v15;
    }
    LOBYTE(v42) = 0;
    LOBYTE(v14) = 1;
    v17 = CVssIOCTLChannel::Call(&v74, &v58, 5636096, v14, 2, v42, 0);
    v59 = v17;
    if ( v17 < 0 )
    {
      *(_QWORD *)v86 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v87 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
      v88 = L"CORHWUTC";
      v89 = 147;
      v90 = 1;
      v91 = 255;
      v93 = 0x1000000;
      memset_0(v92, 0, sizeof(v92));
      CVssFunctionTracer::Trace(
        &v58,
        v86,
        L"Fail to get extents for the volume device. [0x%08lx]. Assume check fails, continuing wait",
        (unsigned int)v17);
    }
    v18 = v82;
    v82 = 0;
    v80 = 0;
    v81 = 0;
    v48 = v18;
    v19 = *v18;
    v49 = v19;
    if ( !(_DWORD)v19 )
    {
      *(_QWORD *)v86 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v87 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
      v88 = L"CORHWUTC";
      v89 = 162;
      v90 = 1;
      v91 = 255;
      v93 = 0x1000000;
      memset_0(v92, 0, sizeof(v92));
      CVssFunctionTracer::Trace(&v58, v86, L"IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS(%s) returned zero extents", a2);
    }
    qsort(v18 + 2, v19, 0x18u, CVssHardwareProviderWrapper::cmpDiskExtents);
    v20 = v18[2];
    v21 = 1;
    for ( i = 1; i < (unsigned int)v19; v20 = v24 )
    {
      v23 = v18[6 * i + 2];
      v24 = v23;
      if ( v23 == v20 )
        v24 = v20;
      v25 = v21 + 1;
      if ( v23 == v20 )
        v25 = v21;
      v21 = v25;
      ++i;
    }
    v26 = (struct _VDS_LUN_INFORMATION *)CoTaskMemAlloc(96LL * v21);
    v43 = v26;
    if ( !v26 )
    {
      *(_QWORD *)v86 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v87 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
      v88 = L"CORHWUTC";
      v89 = 189;
      v90 = 1;
      v91 = 255;
      v93 = 0x1000000;
      memset_0(v92, 0, sizeof(v92));
      CVssFunctionTracer::Throw(&v58, v86, 2147942414LL, L"Cannot allocate LUN information array");
    }
    v57 = v26;
    v56 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    memset_0(v26, 0, 96LL * v21);
    v27 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v21);
    v51 = v27;
    if ( !v27 )
    {
      *(_QWORD *)v86 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v87 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
      v88 = L"CORHWUTC";
      v89 = 198;
      v90 = 1;
      v91 = 255;
      v93 = 0x1000000;
      memset_0(v92, 0, sizeof(v92));
      CVssFunctionTracer::Throw(&v58, v86, 2147942414LL, L"Cannot allocate device name array");
    }
    v55 = v27;
    v54 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    memset_0(v27, 0, 8LL * v21);
    v28 = (GUID *)CoTaskMemAlloc(16LL * v21);
    v29 = v28;
    if ( !v28 )
    {
      *(_QWORD *)v86 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v87 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
      v88 = L"CORHWUTC";
      v89 = 207;
      v90 = 1;
      v91 = 255;
      v93 = 0x1000000;
      memset_0(v92, 0, sizeof(v92));
      CVssFunctionTracer::Throw(&v58, v86, 2147942414LL, L"Cannot allocate lun id array");
    }
    v53 = v28;
    v52 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
    for ( j = 0; j < v21; ++j )
      v28[j] = GUID_NULL;
    v31 = v20 + 1;
    v32 = 0;
    v46 = 0;
    for ( k = 0; k < v49; ++k )
    {
      v34 = v18[6 * k + 2];
      v50 = v34;
      if ( v34 != v31 )
      {
        CVssHardwareProviderWrapper::DisknoToPhysicalDrive(
          (CVssHardwareProviderWrapper *)(3LL * k),
          (struct CVssFunctionTracer *)&v58,
          v34,
          v86,
          0x40u);
        v35 = -1;
        do
          ++v35;
        while ( v86[v35] );
        v36 = (unsigned __int16 *)CoTaskMemAlloc(2 * v35 + 2);
        v51[v32] = v36;
        if ( !v36 )
        {
          v60 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
          v61 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
          v62 = L"CORHWUTC";
          v63 = 235;
          v64 = 1;
          v65 = 255;
          v67 = 0x1000000;
          memset_0(v66, 0, sizeof(v66));
          CVssFunctionTracer::Throw(&v58, &v60, 2147942414LL, L"Cannot allocate device name");
        }
        v37 = -1;
        do
          ++v37;
        while ( v86[v37] );
        v59 = StringCchCopyW(v36, v37 + 1, v86);
        v60 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
        v61 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
        v62 = L"CORHWUTC";
        v63 = 238;
        v64 = 1;
        v65 = 255;
        v67 = 0x1000000;
        memset_0(v66, 0, sizeof(v66));
        CVssFunctionTracer::CheckForErrorInternal(&v58, &v60, L"StringCchCopy fail to copy device path.");
        Block = 0;
        v45 = 0;
        if ( !CVssHardwareProviderWrapper::BuildLunInfoForDrive(
                v69,
                v86,
                &v43[v32],
                0,
                v68,
                (struct _DISK_SNAPSHOT_INFO **)&Block,
                &v45) )
        {
          if ( Block )
            free(Block);
LABEL_41:
          v38 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v58, 0);
          CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v52);
          CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v54);
          CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v56);
          CVssMallocAutoPtr<_VM_GET_CLOSURE_OUTPUT>::~CVssMallocAutoPtr<_VM_GET_CLOSURE_OUTPUT>(&v48);
          CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v74);
          CVssFunctionTracer::~CVssFunctionTracer(&v58);
          return v38;
        }
        if ( !v45 || (v39 = Block) == 0 )
        {
          v60 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
          v61 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
          v62 = L"CORHWUTC";
          v63 = 254;
          v64 = 1;
          v65 = 255;
          v67 = 0x1000000;
          memset_0(v66, 0, sizeof(v66));
          CVssFunctionTracer::Trace(
            &v58,
            &v60,
            L"Fail to find snapshot info for disk %s for this volume, returning false",
            v86);
          if ( Block )
            free(Block);
          goto LABEL_41;
        }
        v31 = v50;
        v29[v32] = *(struct _GUID *)((char *)Block + 40);
        free(v39);
        v32 = (unsigned int)++v46;
      }
    }
    v48 = 0;
    *v70 = (unsigned __int8 *)v18;
    v55 = 0;
    *v71 = v51;
    v57 = 0;
    *v72 = v43;
    v53 = 0;
    *v73 = v29;
    *a4 = v21;
    CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v52);
    CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v54);
    CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v56);
    CVssMallocAutoPtr<_VM_GET_CLOSURE_OUTPUT>::~CVssMallocAutoPtr<_VM_GET_CLOSURE_OUTPUT>(&v48);
    CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v74);
    v40 = v59 >= 0;
  }
  else
  {
LABEL_50:
    v60 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v61 = L"CVssHardwareProviderWrapper::BuildLunInfoFromVolume";
    v62 = L"CORHWUTC";
    v63 = 121;
    v64 = 1;
    v65 = 255;
    v67 = 0x1000000;
    memset_0(v66, 0, sizeof(v66));
    CVssFunctionTracer::Trace(&v58, &v60, L"Invalid arg: NULL or empty volume name.");
    v40 = 0;
  }
  v41 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v58, v40);
  CVssFunctionTracer::~CVssFunctionTracer(&v58);
  return v41;
}

```

## disassembly

```asm
0x140074528  mov     r11, rsp
0x14007452b  push    rbx
0x14007452c  push    rsi
0x14007452d  push    rdi
0x14007452e  push    r12
0x140074530  push    r13
0x140074532  push    r14
0x140074534  push    r15
0x140074536  sub     rsp, 350h
0x14007453d  mov     rax, cs:__security_cookie
0x140074544  xor     rax, rsp
0x140074547  mov     [rsp+388h+var_48], rax
0x14007454f  mov     [rsp+388h+var_330], r9
0x140074554  mov     [rsp+388h+var_198], r8
0x14007455c  mov     rbx, rdx
0x14007455f  mov     [rsp+388h+var_1A0], rcx
0x140074567  mov     rax, [rsp+388h+arg_20]
0x14007456f  mov     [rsp+388h+var_190], rax
0x140074577  mov     rax, [rsp+388h+arg_28]
0x14007457f  mov     [rsp+388h+var_188], rax
0x140074587  mov     rax, [rsp+388h+arg_30]
0x14007458f  mov     [rsp+388h+var_180], rax
0x140074597  mov     rax, [rsp+388h+arg_38]
0x14007459f  mov     [rsp+388h+var_1A8], rax
0x1400745a7  lea     r14, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400745ae  mov     [r11-0F8h], r14
0x1400745b5  lea     r15, aCvsshardwarepr_209; "CVssHardwareProviderWrapper::BuildLunIn"...
0x1400745bc  mov     [r11-0F0h], r15
0x1400745c3  lea     r12, aCorhwutc; "CORHWUTC"
0x1400745ca  mov     [r11-0E8h], r12
0x1400745d1  mov     [rsp+388h+var_E0], 6Ah ; 'j'
0x1400745dc  mov     r13d, 1
0x1400745e2  mov     [r11-0DCh], r13d
0x1400745e9  mov     esi, 0FFh
0x1400745ee  mov     [rsp+388h+var_D8], esi
0x1400745f5  xor     edi, edi
0x1400745f7  mov     dword ptr [r11-58h], 1000000h
0x1400745ff  xor     edx, edx; Val
0x140074601  lea     r8d, [r13+77h]; Size
0x140074605  lea     rcx, [r11-0D0h]; void *
0x14007460c  call    memset_0
0x140074611  xor     r8d, r8d
0x140074614  lea     rdx, [rsp+388h+var_F8]
0x14007461c  lea     rcx, [rsp+388h+var_2C8]
0x140074624  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140074629  nop
0x14007462a  mov     qword ptr [rsp+388h+var_F8], r14
0x140074632  mov     [rsp+388h+var_F0], r15
0x14007463a  mov     [rsp+388h+var_E8], r12
0x140074642  mov     [rsp+388h+var_E0], 6Ch ; 'l'
0x14007464d  mov     [rsp+388h+var_DC], r13d
0x140074655  mov     [rsp+388h+var_D8], esi
0x14007465c  mov     [rsp+388h+var_58], 1000000h
0x140074667  xor     edx, edx; Val
0x140074669  lea     r8d, [r13+77h]; Size
0x14007466d  lea     rcx, [rsp+388h+var_D0]; void *
0x140074675  call    memset_0
0x14007467a  mov     r9, rbx
0x14007467d  mov     r8d, 1776h
0x140074683  lea     rdx, [rsp+388h+var_F8]
0x14007468b  lea     rcx, [rsp+388h+var_2C8]
0x140074693  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x140074698  mov     qword ptr [rsp+388h+var_F8], r14
0x1400746a0  mov     [rsp+388h+var_F0], r15
0x1400746a8  mov     [rsp+388h+var_E8], r12
0x1400746b0  mov     [rsp+388h+var_E0], 6Dh ; 'm'
0x1400746bb  mov     [rsp+388h+var_DC], 6
0x1400746c6  mov     [rsp+388h+var_D8], esi
0x1400746cd  mov     [rsp+388h+var_58], 1000000h
0x1400746d8  xor     edx, edx; Val
0x1400746da  lea     r8d, [r13+77h]; Size
0x1400746de  lea     rcx, [rsp+388h+var_D0]; void *
0x1400746e6  call    memset_0
0x1400746eb  mov     r9, rbx
0x1400746ee  lea     r8, aBuildLunInfoFo; "Build LUN info for volume %s ..."
0x1400746f5  lea     rdx, [rsp+388h+var_F8]
0x1400746fd  lea     rcx, [rsp+388h+var_2C8]
0x140074705  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14007470a  test    rbx, rbx
0x14007470d  jz      loc_1400751DF
0x140074713  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140074717  mov     rax, rcx
0x14007471a  inc     rax
0x14007471d  cmp     [rbx+rax*2], di
0x140074721  jnz     short loc_14007471A
0x140074723  test    rax, rax
0x140074726  jz      loc_1400751DF
0x14007472c  mov     [rsp+388h+var_178], rdi
0x140074734  mov     [rsp+388h+var_150], di
0x14007473c  mov     [rsp+388h+var_14C], rdi
0x140074744  mov     [rsp+388h+var_140], rdi
0x14007474c  mov     [rsp+388h+var_138], rdi
0x140074754  mov     [rsp+388h+var_130], edi
0x14007475b  mov     [rsp+388h+var_128], rdi
0x140074763  mov     [rsp+388h+var_120], di
0x14007476b  mov     [rsp+388h+var_110], rdi
0x140074773  lea     rax, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x14007477a  mov     [rsp+388h+var_118], rax
0x140074782  xorps   xmm0, xmm0
0x140074785  movups  [rsp+388h+var_170], xmm0
0x14007478d  movups  [rsp+388h+var_160], xmm0
0x140074795  mov     rax, rcx
0x140074798  inc     rax
0x14007479b  cmp     [rbx+rax*2], di
0x14007479f  jnz     short loc_140074798
0x1400747a1  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x1400747a7  setz    r9b
0x1400747ab  mov     [rsp+388h+var_348], 80h
0x1400747b3  mov     [rsp+388h+var_350], 3
0x1400747bb  mov     dword ptr [rsp+388h+var_358], 0C0000000h
0x1400747c3  mov     dword ptr [rsp+388h+var_360], 2
0x1400747cb  mov     byte ptr [rsp+388h+var_368], r13b
0x1400747d0  mov     r8, rbx
0x1400747d3  lea     rdx, [rsp+388h+var_2C8]
0x1400747db  lea     rcx, [rsp+388h+var_178]
0x1400747e3  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x1400747e8  mov     esi, eax
0x1400747ea  mov     [rsp+388h+var_2C0], eax
0x1400747f1  test    eax, eax
0x1400747f3  jns     short loc_140074868
0x1400747f5  mov     qword ptr [rsp+388h+var_F8], r14
0x1400747fd  mov     [rsp+388h+var_F0], r15
0x140074805  mov     [rsp+388h+var_E8], r12
0x14007480d  mov     [rsp+388h+var_E0], 87h
0x140074818  mov     [rsp+388h+var_DC], r13d
0x140074820  mov     [rsp+388h+var_D8], 0FFh
0x14007482b  mov     [rsp+388h+var_58], 1000000h
0x140074836  xor     edx, edx; Val
0x140074838  lea     r8d, [rdx+78h]; Size
0x14007483c  lea     rcx, [rsp+388h+var_D0]; void *
0x140074844  call    memset_0
0x140074849  mov     r9d, esi
0x14007484c  lea     r8, aFailToOpenHand_2; "Fail to open handle to volume hr 0x%08l"...
0x140074853  lea     rdx, [rsp+388h+var_F8]
0x14007485b  lea     rcx, [rsp+388h+var_2C8]
0x140074863  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140074868  lea     rdx, [rsp+388h+var_178]; struct CVssIOCTLChannel *
0x140074870  call    ?IsDeviceCDRom@CVssHardwareProviderWrapper@@AEAA_NPEAVCVssIOCTLChannel@@@Z; CVssHardwareProviderWrapper::IsDeviceCDRom(CVssIOCTLChannel *)
0x140074875  test    al, al
0x140074877  jz      loc_140074923
0x14007487d  mov     qword ptr [rsp+388h+var_F8], r14
0x140074885  mov     [rsp+388h+var_F0], r15
0x14007488d  mov     [rsp+388h+var_E8], r12
0x140074895  mov     [rsp+388h+var_E0], 8Ch
0x1400748a0  mov     [rsp+388h+var_DC], r13d
0x1400748a8  mov     [rsp+388h+var_D8], 0FFh
0x1400748b3  mov     [rsp+388h+var_58], 1000000h
0x1400748be  xor     edx, edx; Val
0x1400748c0  lea     r8d, [rdx+78h]; Size
0x1400748c4  lea     rcx, [rsp+388h+var_D0]; void *
0x1400748cc  call    memset_0
0x1400748d1  mov     r9, rbx
0x1400748d4  lea     r8, aDeviceSIsACdRo_0; "Device %s is a CD-ROM and therefore is "...
0x1400748db  lea     rdx, [rsp+388h+var_F8]
0x1400748e3  lea     rcx, [rsp+388h+var_2C8]
0x1400748eb  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400748f0  xor     edx, edx; bool
0x1400748f2  lea     rcx, [rsp+388h+var_2C8]; this
0x1400748fa  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x1400748ff  mov     bl, al
0x140074901  lea     rcx, [rsp+388h+var_178]; this
0x140074909  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x14007490e  nop
0x14007490f  lea     rcx, [rsp+388h+var_2C8]; this
0x140074917  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14007491c  mov     al, bl
0x14007491e  jmp     loc_14007526B
0x140074923  mov     [rsp+388h+var_358], rdi
0x140074928  mov     byte ptr [rsp+388h+var_360], dil
0x14007492d  mov     dword ptr [rsp+388h+var_368], 2
0x140074935  mov     r9b, r13b
0x140074938  mov     r8d, 560000h
0x14007493e  lea     rdx, [rsp+388h+var_2C8]
0x140074946  lea     rcx, [rsp+388h+var_178]
0x14007494e  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x140074953  mov     esi, eax
0x140074955  mov     [rsp+388h+var_2C0], eax
0x14007495c  test    eax, eax
0x14007495e  jns     short loc_1400749D3
0x140074960  mov     qword ptr [rsp+388h+var_F8], r14
0x140074968  mov     [rsp+388h+var_F0], r15
0x140074970  mov     [rsp+388h+var_E8], r12
0x140074978  mov     [rsp+388h+var_E0], 93h
0x140074983  mov     [rsp+388h+var_DC], r13d
0x14007498b  mov     [rsp+388h+var_D8], 0FFh
0x140074996  mov     [rsp+388h+var_58], 1000000h
0x1400749a1  xor     edx, edx; Val
0x1400749a3  lea     r8d, [rdx+78h]; Size
0x1400749a7  lea     rcx, [rsp+388h+var_D0]; void *
0x1400749af  call    memset_0
0x1400749b4  mov     r9d, esi
0x1400749b7  lea     r8, aFailToGetExten_0; "Fail to get extents for the volume devi"...
0x1400749be  lea     rdx, [rsp+388h+var_F8]
0x1400749c6  lea     rcx, [rsp+388h+var_2C8]
0x1400749ce  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400749d3  mov     r12, [rsp+388h+var_128]
0x1400749db  mov     [rsp+388h+var_128], rdi
0x1400749e3  mov     [rsp+388h+var_138], rdi
0x1400749eb  mov     [rsp+388h+var_130], edi
0x1400749f2  mov     [rsp+388h+var_318], r12
0x1400749f7  mov     esi, [r12]
0x1400749fb  mov     [rsp+388h+var_310], esi
0x1400749ff  test    esi, esi
0x140074a01  jnz     short loc_140074A7D
0x140074a03  mov     qword ptr [rsp+388h+var_F8], r14
0x140074a0b  mov     [rsp+388h+var_F0], r15
0x140074a13  lea     rax, aCorhwutc; "CORHWUTC"
0x140074a1a  mov     [rsp+388h+var_E8], rax
0x140074a22  mov     [rsp+388h+var_E0], 0A2h
0x140074a2d  mov     [rsp+388h+var_DC], r13d
0x140074a35  mov     [rsp+388h+var_D8], 0FFh
0x140074a40  mov     [rsp+388h+var_58], 1000000h
0x140074a4b  xor     edx, edx; Val
0x140074a4d  lea     r8d, [rsi+78h]; Size
0x140074a51  lea     rcx, [rsp+388h+var_D0]; void *
0x140074a59  call    memset_0
0x140074a5e  mov     r9, rbx
0x140074a61  lea     r8, aIoctlVolumeGet; "IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS(%s"...
0x140074a68  lea     rdx, [rsp+388h+var_F8]
0x140074a70  lea     rcx, [rsp+388h+var_2C8]
0x140074a78  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140074a7d  mov     rdx, rsi; NumOfElements
0x140074a80  lea     r9, ?cmpDiskExtents@CVssHardwareProviderWrapper@@SAHPEBX0@Z; CompareFunction
0x140074a87  mov     r8d, 18h; SizeOfElements
0x140074a8d  lea     rcx, [r12+8]; Base
0x140074a92  call    cs:__imp_qsort
0x140074a98  mov     ebx, [r12+8]
0x140074a9d  mov     r15d, r13d
0x140074aa0  mov     r8d, r13d
0x140074aa3  cmp     esi, r13d
0x140074aa6  jbe     short loc_140074AD0
0x140074aa8  mov     eax, r8d
0x140074aab  lea     rcx, [rax+rax*2]
0x140074aaf  mov     edx, [r12+rcx*8+8]
0x140074ab4  mov     ecx, edx
0x140074ab6  cmp     edx, ebx
0x140074ab8  cmovz   ecx, ebx
0x140074abb  lea     eax, [r15+1]
0x140074abf  cmovz   eax, r15d
0x140074ac3  mov     r15d, eax
0x140074ac6  add     r8d, r13d
0x140074ac9  mov     ebx, ecx
0x140074acb  cmp     r8d, esi
0x140074ace  jb      short loc_140074AA8
0x140074ad0  mov     esi, r15d
0x140074ad3  lea     r14, [rsi+rsi*2]
0x140074ad7  shl     r14, 5
0x140074adb  mov     rcx, r14; cb
0x140074ade  call    cs:__imp_CoTaskMemAlloc
0x140074ae4  mov     [rsp+388h+var_338], rax
0x140074ae9  test    rax, rax
0x140074aec  jnz     loc_140074B7D
0x140074af2  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140074af9  mov     qword ptr [rsp+388h+var_F8], rax
0x140074b01  lea     rax, aCvsshardwarepr_209; "CVssHardwareProviderWrapper::BuildLunIn"...
0x140074b08  mov     [rsp+388h+var_F0], rax
0x140074b10  lea     rax, aCorhwutc; "CORHWUTC"
0x140074b17  mov     [rsp+388h+var_E8], rax
0x140074b1f  mov     [rsp+388h+var_E0], 0BDh
0x140074b2a  mov     [rsp+388h+var_DC], r13d
0x140074b32  mov     [rsp+388h+var_D8], 0FFh
0x140074b3d  mov     [rsp+388h+var_58], 1000000h
0x140074b48  xor     edx, edx; Val
0x140074b4a  lea     r8d, [rdx+78h]; Size
0x140074b4e  lea     rcx, [rsp+388h+var_D0]; void *
0x140074b56  call    memset_0
0x140074b5b  lea     r9, aCannotAllocate_2; "Cannot allocate LUN information array"
0x140074b62  mov     r8d, 8007000Eh
0x140074b68  lea     rdx, [rsp+388h+var_F8]
0x140074b70  lea     rcx, [rsp+388h+var_2C8]
0x140074b78  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140074b7d  mov     [rsp+388h+var_2D0], rax
0x140074b85  lea     rcx, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x140074b8c  mov     [rsp+388h+var_2D8], rcx
0x140074b94  mov     r8, r14; Size
0x140074b97  xor     edx, edx; Val
0x140074b99  mov     rcx, rax; void *
0x140074b9c  call    memset_0
0x140074ba1  lea     r14, ds:0[rsi*8]
0x140074ba9  mov     rcx, r14; cb
0x140074bac  call    cs:__imp_CoTaskMemAlloc
0x140074bb2  mov     [rsp+388h+var_308], rax
0x140074bba  test    rax, rax
0x140074bbd  jnz     loc_140074C4E
0x140074bc3  lea     rax, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140074bca  mov     qword ptr [rsp+388h+var_F8], rax
0x140074bd2  lea     rax, aCvsshardwarepr_209; "CVssHardwareProviderWrapper::BuildLunIn"...
0x140074bd9  mov     [rsp+388h+var_F0], rax
0x140074be1  lea     rax, aCorhwutc; "CORHWUTC"
0x140074be8  mov     [rsp+388h+var_E8], rax
0x140074bf0  mov     [rsp+388h+var_E0], 0C6h
0x140074bfb  mov     [rsp+388h+var_DC], r13d
0x140074c03  mov     [rsp+388h+var_D8], 0FFh
0x140074c0e  mov     [rsp+388h+var_58], 1000000h
0x140074c19  xor     edx, edx; Val
0x140074c1b  lea     r8d, [rdx+78h]; Size
0x140074c1f  lea     rcx, [rsp+388h+var_D0]; void *
0x140074c27  call    memset_0
0x140074c2c  lea     r9, aCannotAllocate_12; "Cannot allocate device name array"
0x140074c33  mov     r8d, 8007000Eh
  ... truncated ...
```
