# VssVolumeHasParentVolume(ushort const *,bool *,ushort *,int)

- ea: `0x180040cb0`
- end: `0x180041410`
- name: `?VssVolumeHasParentVolume@@YA_NPEBGPEA_NPEAGH@Z`
- size: `1888`
- prototype: `bool __fastcall(const unsigned __int16 *, bool *, unsigned __int16 *, int)`
- caller_count: `6`
- callee_count: `19`
- tags: `loader_planting, service_task`

## callers

- `0x180012740`
- `0x1800200c0`
- `0x180021bc4`
- `0x180027ca0`
- `0x18002d1f0`
- `0x180040cb0`

## callees

- `0x180001580`
- `0x18000212c`
- `0x1800039d8`
- `0x18000610c`
- `0x18001c208`
- `0x18001febc`
- `0x18002a774`
- `0x180033a8c`
- `0x180033c2c`
- `0x180033c78`
- `0x180033e60`
- `0x180033f90`
- `0x1800348b4`
- `0x1800358f4`
- `0x1800367b8`
- `0x180037080`
- `0x180037db8`
- `0x180037ecc`
- `0x180040cb0`

## import_xrefs

- `VirtDisk!GetStorageDependencyInformation` at `0x180040e94`
- `VirtDisk!GetStorageDependencyInformation` at `0x180040e94`

## string_xrefs

- `0x180040e0d`: `Opening volume %s`
- `0x180041144`: `VHD volume %s is surfaced from a remote machine.  Parent volume path: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall VssVolumeHasParentVolume(unsigned __int16 *a1, bool *a2, unsigned __int16 *a3)
{
  ULONG v5; // ebx
  PSTORAGE_DEPENDENCY_INFO v6; // rdi
  signed int StorageDependencyInformation; // eax
  DWORD v8; // ebx
  DWORD v9; // ebx
  struct CVssDebugInfo *v10; // rax
  CVssDebugInfo *v11; // rax
  char v12; // r15
  const wchar_t *HostVolumeName; // rbx
  char v14; // dl
  unsigned __int16 *v15; // rbx
  __int64 v16; // rax
  signed int v17; // edi
  const wchar_t *v18; // r9
  char v19; // bl
  PULONG SizeUsed; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  ULONG v23; // [rsp+58h] [rbp-A8h] BYREF
  void **v24; // [rsp+60h] [rbp-A0h] BYREF
  PSTORAGE_DEPENDENCY_INFO StorageDependencyInfo; // [rsp+68h] [rbp-98h]
  const wchar_t *v26; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v27; // [rsp+78h] [rbp-88h]
  const wchar_t *v28; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+88h] [rbp-78h]
  int v30; // [rsp+8Ch] [rbp-74h]
  int v31; // [rsp+90h] [rbp-70h]
  _BYTE v32[120]; // [rsp+98h] [rbp-68h] BYREF
  int v33; // [rsp+110h] [rbp+10h]
  HANDLE ObjectHandle; // [rsp+120h] [rbp+20h] BYREF
  __int128 v35; // [rsp+128h] [rbp+28h]
  __int128 v36; // [rsp+138h] [rbp+38h]
  _WORD v37[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v38; // [rsp+14Ch] [rbp+4Ch]
  __int64 v39; // [rsp+158h] [rbp+58h]
  __int64 v40; // [rsp+160h] [rbp+60h]
  int v41; // [rsp+168h] [rbp+68h]
  __int64 v42; // [rsp+170h] [rbp+70h]
  __int16 v43; // [rsp+178h] [rbp+78h]
  void **v44; // [rsp+180h] [rbp+80h]
  __int64 v45; // [rsp+188h] [rbp+88h]
  int v46; // [rsp+1C0h] [rbp+C0h]
  LPVOID v47; // [rsp+1D0h] [rbp+D0h] BYREF
  DWORD dwMessageId; // [rsp+1D8h] [rbp+D8h]
  unsigned __int16 v49[4]; // [rsp+240h] [rbp+140h] BYREF
  const wchar_t *v50; // [rsp+248h] [rbp+148h]
  const wchar_t *v51; // [rsp+250h] [rbp+150h]
  int v52; // [rsp+258h] [rbp+158h]
  int v53; // [rsp+25Ch] [rbp+15Ch]
  int v54; // [rsp+260h] [rbp+160h]
  _BYTE v55[120]; // [rsp+268h] [rbp+168h] BYREF
  int v56; // [rsp+2E0h] [rbp+1E0h]
  unsigned __int16 v57[88]; // [rsp+2F0h] [rbp+1F0h] BYREF

  ObjectHandle = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
  *(_QWORD *)&v35 = L"VssVolumeHasParentVolume";
  *((_QWORD *)&v35 + 1) = L"VOLUMEC";
  *(_QWORD *)&v36 = 0xB0000002DLL;
  DWORD2(v36) = 255;
  v46 = 0x1000000;
  memset_0(v37, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v47, (__int64)&ObjectHandle, 0);
  ObjectHandle = 0;
  v37[0] = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v45 = 0;
  v44 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v35 = 0;
  v36 = 0;
  v5 = 1024;
  v23 = 0;
  StorageDependencyInfo = 0;
  v24 = &CVssAutoCppPtr<unsigned char *>::`vftable';
  if ( a2 )
    *a2 = 0;
  *(_QWORD *)v49 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
  v50 = L"VssVolumeHasParentVolume";
  v51 = L"VOLUMEC";
  v52 = 68;
  v53 = 11;
  v54 = 255;
  v56 = 0x1000000;
  memset_0(v55, 0, sizeof(v55));
  CVssFunctionTracer::Trace(&v47, v49, L"Opening volume %s", a1);
  CVssIOCTLChannel::Open((CVssIOCTLChannel *)&ObjectHandle, (__int64)&v47, a1, 1, 1, 0, 0x80000000, v22, 0x80u);
  while ( 1 )
  {
    CVssAutoCppPtr_Storage<unsigned char *>::AllocateBytes(&v24, v5);
    v6 = StorageDependencyInfo;
    memset_0(StorageDependencyInfo, 0, v5);
    v6->Version = STORAGE_DEPENDENCY_INFO_VERSION_2;
    StorageDependencyInformation = GetStorageDependencyInformation(
                                     ObjectHandle,
                                     GET_STORAGE_DEPENDENCY_FLAG_HOST_VOLUMES,
                                     v5,
                                     v6,
                                     &v23);
    v8 = StorageDependencyInformation;
    if ( !StorageDependencyInformation )
      break;
    if ( StorageDependencyInformation != 122 )
    {
      if ( StorageDependencyInformation == 1 || StorageDependencyInformation == -1069940715 )
      {
        *(_QWORD *)v49 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
        v50 = L"VssVolumeHasParentVolume";
        v51 = L"VOLUMEC";
        v52 = 110;
        v53 = 11;
        v54 = 255;
        v56 = 0x1000000;
        memset_0(v55, 0, sizeof(v55));
        CVssFunctionTracer::Trace(&v47, v49, L"No VHDs are presently surfaced");
        v14 = 0;
        goto LABEL_34;
      }
      if ( StorageDependencyInformation > 0 )
        v8 = (unsigned __int16)StorageDependencyInformation | 0x80070000;
      dwMessageId = v8;
      *(_QWORD *)v49 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
      v50 = L"VssVolumeHasParentVolume";
      v51 = L"VOLUMEC";
      v52 = 115;
      v53 = 11;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      CVssFunctionTracer::AddGenericErrorContext((__int64)&v47, (const struct CVssDebugInfo *)v49, v8);
      v9 = dwMessageId;
      *(_QWORD *)v49 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
      v50 = L"VssVolumeHasParentVolume";
      v51 = L"VOLUMEC";
      v52 = 116;
      v53 = 11;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      LODWORD(SizeUsed) = v9;
      CVssFunctionTracer::Trace(
        &v47,
        v49,
        L"GetStorageDependencyInformation(%s, NULL) failed to get required buffer size, %#x",
        a1,
        SizeUsed);
      *(_QWORD *)v49 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
      v50 = L"VssVolumeHasParentVolume";
      v51 = L"VOLUMEC";
      v52 = 118;
      v53 = 11;
      v54 = 255;
      v56 = 0x1000000;
      memset_0(v55, 0, sizeof(v55));
      v10 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)v49, (CVssDebugInfo *)v57);
      v11 = CVssDebugInfo::operator<<(v10, (CVssDebugInfo *)&v26, dwMessageId);
      CVssFunctionTracer::LogError((__int64)&v47, 0x3001u, (__int64)v11, 1u);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v57);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v49);
      break;
    }
    v5 = v23;
  }
  v12 = 0;
  if ( !v23 || !v6->NumberEntries || v6->Version2Entries[0].VirtualStorageType.DeviceId - 2 > 1 )
    goto LABEL_29;
  v12 = 1;
  memset_0(v57, 0, 0x64u);
  memset_0(v49, 0, 0x64u);
  if ( (v6->Version1Entries[0].DependencyTypeFlags & 8) != 0 )
  {
    HostVolumeName = L"<null>";
    if ( v6->Version2Entries[0].HostVolumeName )
      HostVolumeName = v6->Version2Entries[0].HostVolumeName;
    v26 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
    v27 = L"VssVolumeHasParentVolume";
    v28 = L"VOLUMEC";
    v29 = 145;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    CVssFunctionTracer::Trace(
      &v47,
      &v26,
      L"VHD volume %s is surfaced from a remote machine.  Parent volume path: %s",
      a1,
      HostVolumeName);
    if ( !a2 )
      goto LABEL_33;
    *a2 = 1;
    goto LABEL_29;
  }
  if ( a2 )
  {
    v15 = v6->Version2Entries[0].HostVolumeName;
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    if ( v15[v16 - 1] != 92 )
    {
      v17 = StringCchPrintfW(v57, 0x32u, L"%s\\", v6->Version2Entries[0].HostVolumeName);
      dwMessageId = v17;
      if ( v17 < 0 )
      {
        v26 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
        v27 = L"VssVolumeHasParentVolume";
        v28 = L"VOLUMEC";
        v29 = 180;
        v30 = 2;
        v31 = 255;
        v33 = 0x1000000;
        memset_0(v32, 0, sizeof(v32));
        CVssFunctionTracer::TranslateGenericError(
          &v47,
          &v26,
          (unsigned int)v17,
          L"StringCchPrintf - volume name: %s",
          v15);
      }
      v15 = v57;
    }
    v26 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
    v27 = L"VssVolumeHasParentVolume";
    v28 = L"VOLUMEC";
    v29 = 191;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(v32, 0, sizeof(v32));
    GetVolumeNameWithCheck((const struct CVssDebugInfo *)&v26, 0x80070057, v15, v49);
    *a2 = !VssVolumeHasParentVolume(v49, 0, 0, 0);
LABEL_29:
    if ( a2 )
    {
      v26 = L"base\\stor\\vss\\modules\\volume\\volume.cxx";
      v27 = L"VssVolumeHasParentVolume";
      v28 = L"VOLUMEC";
      v29 = 218;
      v30 = 11;
      v31 = 255;
      v33 = 0x1000000;
      memset_0(v32, 0, sizeof(v32));
      v18 = L"TRUE";
      if ( !*a2 )
        v18 = L"FALSE";
      CVssFunctionTracer::Trace(&v47, &v26, L"ParentIsPhysical: %s", v18);
    }
  }
LABEL_33:
  v14 = v12;
LABEL_34:
  v19 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v47, v14);
  CVssAuto<unsigned char *,CVssAutoCppPtr_Storage<unsigned char *>>::~CVssAuto<unsigned char *,CVssAutoCppPtr_Storage<unsigned char *>>(&v24);
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&ObjectHandle);
  CVssFunctionTracer::~CVssFunctionTracer(&v47);
  return v19;
}

```

## disassembly

```asm
0x180040cb0  mov     [rsp-8+arg_10], rbx
0x180040cb5  mov     [rsp-8+arg_18], rsi
0x180040cba  push    rbp
0x180040cbb  push    rdi
0x180040cbc  push    r12
0x180040cbe  push    r14
0x180040cc0  push    r15
0x180040cc2  lea     rbp, [rsp-2B0h]
0x180040cca  sub     rsp, 3B0h
0x180040cd1  mov     rax, cs:__security_cookie
0x180040cd8  xor     rax, rsp
0x180040cdb  mov     [rbp+2D0h+var_30], rax
0x180040ce2  mov     rsi, rdx
0x180040ce5  mov     r14, rcx
0x180040ce8  lea     r15, aBaseStorVssMod_1; "base\\stor\\vss\\modules\\volume\\volum"...
0x180040cef  mov     [rbp+2D0h+ObjectHandle], r15
0x180040cf3  lea     rdi, aVssvolumehaspa; "VssVolumeHasParentVolume"
0x180040cfa  mov     qword ptr [rbp+2D0h+var_2A8], rdi
0x180040cfe  lea     rax, aVolumec; "VOLUMEC"
0x180040d05  mov     qword ptr [rbp+2D0h+var_2A8+8], rax
0x180040d09  mov     dword ptr [rbp+2D0h+var_298], 2Dh ; '-'
0x180040d10  mov     dword ptr [rbp+2D0h+var_298+4], 0Bh
0x180040d17  mov     dword ptr [rbp+2D0h+var_298+8], 0FFh
0x180040d1e  xor     r12d, r12d
0x180040d21  mov     [rbp+2D0h+var_210], 1000000h
0x180040d2b  xor     edx, edx; Val
0x180040d2d  lea     r8d, [r12+78h]; Size
0x180040d32  lea     rcx, [rbp+2D0h+var_288]; void *
0x180040d36  call    memset_0
0x180040d3b  xor     r8d, r8d
0x180040d3e  lea     rdx, [rbp+2D0h+ObjectHandle]
0x180040d42  lea     rcx, [rbp+2D0h+var_200]
0x180040d49  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180040d4e  nop
0x180040d4f  mov     [rbp+2D0h+ObjectHandle], r12
0x180040d53  mov     [rbp+2D0h+var_288], r12w
0x180040d58  mov     [rbp+2D0h+var_284], r12
0x180040d5c  mov     [rbp+2D0h+var_278], r12
0x180040d60  mov     [rbp+2D0h+var_270], r12
0x180040d64  mov     [rbp+2D0h+var_268], r12d
0x180040d68  mov     [rbp+2D0h+var_260], r12
0x180040d6c  mov     [rbp+2D0h+var_258], r12w
0x180040d71  mov     [rbp+2D0h+var_248], r12
0x180040d78  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180040d7f  mov     [rbp+2D0h+var_250], rax
0x180040d86  xorps   xmm0, xmm0
0x180040d89  movups  [rbp+2D0h+var_2A8], xmm0
0x180040d8d  movups  [rbp+2D0h+var_298], xmm0
0x180040d91  mov     ebx, 400h
0x180040d96  mov     [rsp+3D0h+var_378], r12d
0x180040d9b  mov     [rsp+3D0h+StorageDependencyInfo], r12
0x180040da0  lea     rax, ??_7?$CVssAutoCppPtr@PEAE@@6B@; const CVssAutoCppPtr<uchar *>::`vftable'
0x180040da7  mov     [rsp+3D0h+var_370], rax
0x180040dac  test    rsi, rsi
0x180040daf  jz      short loc_180040DB4
0x180040db1  mov     [rsi], r12b
0x180040db4  mov     qword ptr [rbp+2D0h+var_190], r15
0x180040dbb  mov     [rbp+2D0h+var_188], rdi
0x180040dc2  lea     rax, aVolumec; "VOLUMEC"
0x180040dc9  mov     [rbp+2D0h+var_180], rax
0x180040dd0  mov     [rbp+2D0h+var_178], 44h ; 'D'
0x180040dda  mov     [rbp+2D0h+var_174], 0Bh
0x180040de4  mov     [rbp+2D0h+var_170], 0FFh
0x180040dee  mov     [rbp+2D0h+var_F0], 1000000h
0x180040df8  xor     edx, edx; Val
0x180040dfa  lea     r8d, [rdx+78h]; Size
0x180040dfe  lea     rcx, [rbp+2D0h+var_168]; void *
0x180040e05  call    memset_0
0x180040e0a  mov     r9, r14
0x180040e0d  lea     r8, aOpeningVolumeS; "Opening volume %s"
0x180040e14  lea     rdx, [rbp+2D0h+var_190]
0x180040e1b  lea     rcx, [rbp+2D0h+var_200]
0x180040e22  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180040e27  mov     [rsp+3D0h+var_390], 80h
0x180040e2f  mov     [rsp+3D0h+var_3A0], 80000000h
0x180040e37  mov     [rsp+3D0h+var_3A8], r12d
0x180040e3c  mov     byte ptr [rsp+3D0h+SizeUsed], 1
0x180040e41  mov     r9b, 1
0x180040e44  mov     r8, r14
0x180040e47  lea     rdx, [rbp+2D0h+var_200]
0x180040e4e  lea     rcx, [rbp+2D0h+ObjectHandle]
0x180040e52  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x180040e57  mov     edx, ebx
0x180040e59  lea     rcx, [rsp+3D0h+var_370]
0x180040e5e  call    ?AllocateBytes@?$CVssAutoCppPtr_Storage@PEAE@@QEAAXK@Z; CVssAutoCppPtr_Storage<uchar *>::AllocateBytes(ulong)
0x180040e63  mov     rdi, [rsp+3D0h+StorageDependencyInfo]
0x180040e68  mov     r8d, ebx; Size
0x180040e6b  xor     edx, edx; Val
0x180040e6d  mov     rcx, rdi; void *
0x180040e70  call    memset_0
0x180040e75  mov     dword ptr [rdi], 2
0x180040e7b  lea     rax, [rsp+3D0h+var_378]
0x180040e80  mov     [rsp+3D0h+SizeUsed], rax; SizeUsed
0x180040e85  mov     r9, rdi; StorageDependencyInfo
0x180040e88  mov     r8d, ebx; StorageDependencyInfoSize
0x180040e8b  mov     edx, 1; Flags
0x180040e90  mov     rcx, [rbp+2D0h+ObjectHandle]; ObjectHandle
0x180040e94  call    cs:__imp_GetStorageDependencyInformation
0x180040e9a  mov     ebx, eax
0x180040e9c  test    eax, eax
0x180040e9e  jz      loc_180041083
0x180040ea4  cmp     eax, 7Ah ; 'z'
0x180040ea7  jnz     short loc_180040EAF
0x180040ea9  mov     ebx, [rsp+3D0h+var_378]
0x180040ead  jmp     short loc_180040E57
0x180040eaf  cmp     eax, 1
0x180040eb2  jz      loc_18004116D
0x180040eb8  cmp     eax, 0C03A0015h
0x180040ebd  jz      loc_18004116D
0x180040ec3  test    eax, eax
0x180040ec5  jle     short loc_180040ED0
0x180040ec7  movzx   ebx, ax
0x180040eca  or      ebx, 80070000h
0x180040ed0  mov     [rbp+2D0h+dwMessageId], ebx
0x180040ed6  mov     qword ptr [rbp+2D0h+var_190], r15
0x180040edd  lea     rax, aVssvolumehaspa; "VssVolumeHasParentVolume"
0x180040ee4  mov     [rbp+2D0h+var_188], rax
0x180040eeb  lea     rax, aVolumec; "VOLUMEC"
0x180040ef2  mov     [rbp+2D0h+var_180], rax
0x180040ef9  mov     [rbp+2D0h+var_178], 73h ; 's'
0x180040f03  mov     [rbp+2D0h+var_174], 0Bh
0x180040f0d  mov     [rbp+2D0h+var_170], 0FFh
0x180040f17  mov     [rbp+2D0h+var_F0], 1000000h
0x180040f21  xor     edx, edx; Val
0x180040f23  lea     r8d, [rdx+78h]; Size
0x180040f27  lea     rcx, [rbp+2D0h+var_168]; void *
0x180040f2e  call    memset_0
0x180040f33  mov     r8d, ebx
0x180040f36  lea     rdx, [rbp+2D0h+var_190]
0x180040f3d  lea     rcx, [rbp+2D0h+var_200]
0x180040f44  call    ?AddGenericErrorContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@J@Z; CVssFunctionTracer::AddGenericErrorContext(CVssDebugInfo,long)
0x180040f49  mov     ebx, [rbp+2D0h+dwMessageId]
0x180040f4f  mov     qword ptr [rbp+2D0h+var_190], r15
0x180040f56  lea     rax, aVssvolumehaspa; "VssVolumeHasParentVolume"
0x180040f5d  mov     [rbp+2D0h+var_188], rax
0x180040f64  lea     rax, aVolumec; "VOLUMEC"
0x180040f6b  mov     [rbp+2D0h+var_180], rax
0x180040f72  mov     [rbp+2D0h+var_178], 74h ; 't'
0x180040f7c  mov     [rbp+2D0h+var_174], 0Bh
0x180040f86  mov     [rbp+2D0h+var_170], 0FFh
0x180040f90  mov     [rbp+2D0h+var_F0], 1000000h
0x180040f9a  xor     edx, edx; Val
0x180040f9c  lea     r8d, [rdx+78h]; Size
0x180040fa0  lea     rcx, [rbp+2D0h+var_168]; void *
0x180040fa7  call    memset_0
0x180040fac  mov     dword ptr [rsp+3D0h+SizeUsed], ebx
0x180040fb0  mov     r9, r14
0x180040fb3  lea     r8, aGetstoragedepe; "GetStorageDependencyInformation(%s, NUL"...
0x180040fba  lea     rdx, [rbp+2D0h+var_190]
0x180040fc1  lea     rcx, [rbp+2D0h+var_200]
0x180040fc8  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180040fcd  mov     qword ptr [rbp+2D0h+var_190], r15
0x180040fd4  lea     rax, aVssvolumehaspa; "VssVolumeHasParentVolume"
0x180040fdb  mov     [rbp+2D0h+var_188], rax
0x180040fe2  lea     rax, aVolumec; "VOLUMEC"
0x180040fe9  mov     [rbp+2D0h+var_180], rax
0x180040ff0  mov     [rbp+2D0h+var_178], 76h ; 'v'
0x180040ffa  mov     [rbp+2D0h+var_174], 0Bh
0x180041004  mov     [rbp+2D0h+var_170], 0FFh
0x18004100e  mov     [rbp+2D0h+var_F0], 1000000h
0x180041018  xor     edx, edx; Val
0x18004101a  lea     r8d, [rdx+78h]; Size
0x18004101e  lea     rcx, [rbp+2D0h+var_168]; void *
0x180041025  call    memset_0
0x18004102a  lea     rdx, [rbp+2D0h+var_E0]; this
0x180041031  lea     rcx, [rbp+2D0h+var_190]; struct CVssDebugInfo *
0x180041038  call    ??6CVssDebugInfo@@QEAA?AU0@PEAD@Z; CVssDebugInfo::operator<<(char *)
0x18004103d  mov     r8d, [rbp+2D0h+dwMessageId]; dwMessageId
0x180041044  lea     rdx, [rsp+3D0h+var_360]; this
0x180041049  mov     rcx, rax; struct CVssDebugInfo *
0x18004104c  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x180041051  mov     r9d, 1
0x180041057  mov     r8, rax
0x18004105a  mov     edx, 3001h
0x18004105f  lea     rcx, [rbp+2D0h+var_200]
0x180041066  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x18004106b  lea     rcx, [rbp+2D0h+var_E0]; this
0x180041072  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180041077  lea     rcx, [rbp+2D0h+var_190]; this
0x18004107e  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180041083  mov     r15b, r12b
0x180041086  cmp     [rsp+3D0h+var_378], r12d
0x18004108b  jbe     loc_180041331
0x180041091  cmp     [rdi+4], r12d
0x180041095  jbe     loc_180041331
0x18004109b  mov     eax, [rdi+10h]
0x18004109e  sub     eax, 2
0x1800410a1  cmp     eax, 1
0x1800410a4  ja      loc_180041331
0x1800410aa  mov     r15b, 1
0x1800410ad  mov     ebx, 64h ; 'd'
0x1800410b2  mov     r8d, ebx; Size
0x1800410b5  xor     edx, edx; Val
0x1800410b7  lea     rcx, [rbp+2D0h+var_E0]; void *
0x1800410be  call    memset_0
0x1800410c3  mov     r8d, ebx; Size
0x1800410c6  xor     edx, edx; Val
0x1800410c8  lea     rcx, [rbp+2D0h+var_190]; void *
0x1800410cf  call    memset_0
0x1800410d4  test    byte ptr [rdi+8], 8
0x1800410d8  jz      loc_1800411EB
0x1800410de  lea     rbx, aNull; "<null>"
0x1800410e5  cmp     [rdi+30h], r12
0x1800410e9  cmovnz  rbx, [rdi+30h]
0x1800410ee  lea     rdi, aBaseStorVssMod_1; "base\\stor\\vss\\modules\\volume\\volum"...
0x1800410f5  mov     [rsp+3D0h+var_360], rdi
0x1800410fa  lea     rax, aVssvolumehaspa; "VssVolumeHasParentVolume"
0x180041101  mov     [rsp+3D0h+var_358], rax
0x180041106  lea     rax, aVolumec; "VOLUMEC"
0x18004110d  mov     [rbp+2D0h+var_350], rax
0x180041111  mov     [rbp+2D0h+var_348], 91h
0x180041118  mov     [rbp+2D0h+var_344], 0Bh
0x18004111f  mov     [rbp+2D0h+var_340], 0FFh
0x180041126  mov     [rbp+2D0h+var_2C0], 1000000h
0x18004112d  xor     edx, edx; Val
0x18004112f  lea     r8d, [rdx+78h]; Size
0x180041133  lea     rcx, [rbp+2D0h+var_338]; void *
0x180041137  call    memset_0
0x18004113c  mov     [rsp+3D0h+SizeUsed], rbx
0x180041141  mov     r9, r14
0x180041144  lea     r8, aVhdVolumeSIsSu; "VHD volume %s is surfaced from a remote"...
0x18004114b  lea     rdx, [rsp+3D0h+var_360]
0x180041150  lea     rcx, [rbp+2D0h+var_200]
0x180041157  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18004115c  test    rsi, rsi
0x18004115f  jz      loc_1800413B1
0x180041165  mov     [rsi], r15b
0x180041168  jmp     loc_180041338
0x18004116d  mov     qword ptr [rbp+2D0h+var_190], r15
0x180041174  lea     rax, aVssvolumehaspa; "VssVolumeHasParentVolume"
0x18004117b  mov     [rbp+2D0h+var_188], rax
0x180041182  lea     rax, aVolumec; "VOLUMEC"
0x180041189  mov     [rbp+2D0h+var_180], rax
0x180041190  mov     [rbp+2D0h+var_178], 6Eh ; 'n'
0x18004119a  mov     [rbp+2D0h+var_174], 0Bh
0x1800411a4  mov     [rbp+2D0h+var_170], 0FFh
0x1800411ae  mov     [rbp+2D0h+var_F0], 1000000h
0x1800411b8  xor     edx, edx; Val
0x1800411ba  lea     r8d, [rdx+78h]; Size
0x1800411be  lea     rcx, [rbp+2D0h+var_168]; void *
0x1800411c5  call    memset_0
0x1800411ca  lea     r8, aNoVhdsArePrese; "No VHDs are presently surfaced"
0x1800411d1  lea     rdx, [rbp+2D0h+var_190]
0x1800411d8  lea     rcx, [rbp+2D0h+var_200]
0x1800411df  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800411e4  xor     edx, edx
0x1800411e6  jmp     loc_1800413B4
0x1800411eb  test    rsi, rsi
0x1800411ee  jz      loc_1800413B1
0x1800411f4  mov     rbx, [rdi+30h]
0x1800411f8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800411fc  inc     rax
0x1800411ff  cmp     [rbx+rax*2], r12w
0x180041204  jnz     short loc_1800411FC
0x180041206  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x18004120c  jz      loc_1800412AF
0x180041212  mov     r9, rbx
0x180041215  lea     r8, aS_0; "%s\\"
0x18004121c  mov     edx, 32h ; '2'; unsigned __int64
0x180041221  lea     rcx, [rbp+2D0h+var_E0]; unsigned __int16 *
0x180041228  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004122d  mov     edi, eax
0x18004122f  mov     [rbp+2D0h+dwMessageId], eax
0x180041235  test    eax, eax
0x180041237  jns     short loc_1800412A8
0x180041239  lea     rax, aBaseStorVssMod_1; "base\\stor\\vss\\modules\\volume\\volum"...
0x180041240  mov     [rsp+3D0h+var_360], rax
0x180041245  lea     rax, aVssvolumehaspa; "VssVolumeHasParentVolume"
0x18004124c  mov     [rsp+3D0h+var_358], rax
0x180041251  lea     rax, aVolumec; "VOLUMEC"
0x180041258  mov     [rbp+2D0h+var_350], rax
0x18004125c  mov     [rbp+2D0h+var_348], 0B4h
0x180041263  mov     [rbp+2D0h+var_344], 2
0x18004126a  mov     [rbp+2D0h+var_340], 0FFh
0x180041271  mov     [rbp+2D0h+var_2C0], 1000000h
0x180041278  xor     edx, edx; Val
0x18004127a  lea     r8d, [rdx+78h]; Size
0x18004127e  lea     rcx, [rbp+2D0h+var_338]; void *
0x180041282  call    memset_0
0x180041287  mov     [rsp+3D0h+SizeUsed], rbx
0x18004128c  lea     r9, aStringcchprint; "StringCchPrintf - volume name: %s"
0x180041293  mov     r8d, edi
0x180041296  lea     rdx, [rsp+3D0h+var_360]
0x18004129b  lea     rcx, [rbp+2D0h+var_200]
0x1800412a2  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1800412a8  lea     rbx, [rbp+2D0h+var_E0]
0x1800412af  lea     rdi, aBaseStorVssMod_1; "base\\stor\\vss\\modules\\volume\\volum"...
0x1800412b6  mov     [rsp+3D0h+var_360], rdi
0x1800412bb  lea     r14, aVssvolumehaspa; "VssVolumeHasParentVolume"
0x1800412c2  mov     [rsp+3D0h+var_358], r14
0x1800412c7  lea     rax, aVolumec; "VOLUMEC"
0x1800412ce  mov     [rbp+2D0h+var_350], rax
0x1800412d2  mov     [rbp+2D0h+var_348], 0BFh
0x1800412d9  mov     [rbp+2D0h+var_344], 0Bh
0x1800412e0  mov     [rbp+2D0h+var_340], 0FFh
0x1800412e7  mov     [rbp+2D0h+var_2C0], 1000000h
0x1800412ee  xor     edx, edx; Val
0x1800412f0  lea     r8d, [rdx+78h]; Size
0x1800412f4  lea     rcx, [rbp+2D0h+var_338]; void *
0x1800412f8  call    memset_0
  ... truncated ...
```
