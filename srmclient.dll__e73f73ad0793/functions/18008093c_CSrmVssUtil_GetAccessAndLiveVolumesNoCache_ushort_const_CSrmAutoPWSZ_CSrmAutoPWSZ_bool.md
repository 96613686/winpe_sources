# CSrmVssUtil::GetAccessAndLiveVolumesNoCache(ushort const *,CSrmAutoPWSZ &,CSrmAutoPWSZ &,bool &)

- ea: `0x18008093c`
- end: `0x180081125`
- name: `?GetAccessAndLiveVolumesNoCache@CSrmVssUtil@@SAXPEBGAEAVCSrmAutoPWSZ@@1AEA_N@Z`
- size: `2025`
- prototype: `void __fastcall(const unsigned __int16 *, struct CSrmAutoPWSZ *this, struct CSrmAutoPWSZ *, bool *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x180080580`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18000ad14`
- `0x18000af40`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180070bd8`
- `0x180073a80`
- `0x180073f54`
- `0x180074d00`
- `0x18008093c`
- `0x18008112c`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180080b9d`
- `msvcrt!_wcsicmp` at `0x180080bb6`
- `msvcrt!_wcsicmp` at `0x180080b9d`
- `msvcrt!_wcsicmp` at `0x180080bb6`
- `msvcrt!_wcsnicmp` at `0x1800809ec`
- `msvcrt!_wcsnicmp` at `0x180080ce7`
- `msvcrt!_wcsnicmp` at `0x1800809ec`
- `msvcrt!_wcsnicmp` at `0x180080ce7`
- `ole32!CoTaskMemFree` at `0x180080bc3`
- `ole32!CoTaskMemFree` at `0x180080c49`
- `ole32!CoTaskMemFree` at `0x180080c82`
- `ole32!CoTaskMemFree` at `0x180080d9b`
- `ole32!CoTaskMemFree` at `0x180080dae`
- `ole32!CoTaskMemFree` at `0x180080bc3`
- `ole32!CoTaskMemFree` at `0x180080c49`
- `ole32!CoTaskMemFree` at `0x180080c82`
- `ole32!CoTaskMemFree` at `0x180080d9b`
- `ole32!CoTaskMemFree` at `0x180080dae`
- `KERNEL32!GetLastError` at `0x180080df5`
- `KERNEL32!GetLastError` at `0x180080e6d`
- `KERNEL32!GetLastError` at `0x180080ee4`
- `KERNEL32!GetLastError` at `0x180080f8d`
- `KERNEL32!GetLastError` at `0x180080df5`
- `KERNEL32!GetLastError` at `0x180080e6d`
- `KERNEL32!GetLastError` at `0x180080ee4`
- `KERNEL32!GetLastError` at `0x180080f8d`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180080bf7`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180080c24`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180080cfe`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180080d24`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180080bf7`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180080c24`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180080cfe`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180080d24`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180080a65`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180080a65`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x180080bda`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x180080c99`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x180080bda`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x180080c99`

## string_xrefs

- `0x180080e56`: `GetVolumeNameForVolumeMountPoint`
- `0x180080ecd`: `GetVolumeNameForVolumeMountPoint`
- `0x180080f44`: `GetVolumeNameForVolumeMountPoint`
- `0x180080fed`: `GetVolumeNameForVolumeMountPoint`
- `0x180080989`: `CSrmVssUtil::GetAccessAndLiveVolumesNoCache`
- `0x180080e37`: `CSrmVssUtil::GetAccessAndLiveVolumesNoCache`
- `0x180080eae`: `CSrmVssUtil::GetAccessAndLiveVolumesNoCache`
- `0x180080f25`: `CSrmVssUtil::GetAccessAndLiveVolumesNoCache`
- `0x180080fce`: `CSrmVssUtil::GetAccessAndLiveVolumesNoCache`
- `0x180080c64`: `Shadow copy volume '%s' found; originating volume = '%s'`
- `0x180080d7a`: `Volume '%s': shadow copy = '%s', volume canonical access name = '%s', originating volume GUID name = '%s'`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall CSrmVssUtil::GetAccessAndLiveVolumesNoCache(
        const unsigned __int16 *a1,
        LPVOID *this,
        struct CSrmAutoPWSZ *a3,
        bool *a4)
{
  unsigned __int16 *v8; // rbx
  __int64 v9; // rax
  bool IsShadowCopyVolume; // al
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  wchar_t *v17; // rdi
  const wchar_t *v18; // rcx
  signed int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rax
  signed int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rax
  signed int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rax
  int v28; // eax
  char v29; // al
  signed int LastError; // eax
  unsigned int Hr; // ebx
  __int64 v32; // rax
  int v33; // eax
  char v34; // al
  int v35; // eax
  char v36; // al
  int v37; // eax
  char v38; // al
  int v39; // eax
  char v40; // al
  int v41; // eax
  char v42; // al
  wchar_t *v43; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR lpszVolumeName; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-A8h] BYREF
  GUID v47; // [rsp+60h] [rbp-A0h] BYREF
  int v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h]
  _QWORD v50[4]; // [rsp+80h] [rbp-80h] BYREF
  int v51; // [rsp+A0h] [rbp-60h]
  _BYTE v52[96]; // [rsp+A8h] [rbp-58h] BYREF
  int v53; // [rsp+108h] [rbp+8h]
  void **v54; // [rsp+110h] [rbp+10h] BYREF
  int v55; // [rsp+118h] [rbp+18h]
  _BYTE v56[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v57[40]; // [rsp+1C8h] [rbp+C8h] BYREF
  wchar_t *String2; // [rsp+1F0h] [rbp+F0h]
  unsigned __int16 *v59; // [rsp+1F8h] [rbp+F8h]
  WCHAR szVolumeName[256]; // [rsp+250h] [rbp+150h] BYREF

  *(_QWORD *)&v47.Data1 = v50;
  v50[0] = L"base\\fs\\fsrm\\utilities\\vss\\srmvss.cpp";
  v50[1] = L"CSrmVssUtil::GetAccessAndLiveVolumesNoCache";
  v50[2] = L"SRMVSSUC";
  v50[3] = 158;
  v51 = 255;
  v53 = 0x1000000;
  memset_0(v52, 0, sizeof(v52));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v54, (const struct CSrmDebugInfo *)v50, 0);
  lpszVolumeName = 0;
  if ( _wcsnicmp(a1, L"\\\\?\\GLOBALROOT", 0xEu) )
  {
    if ( !GetVolumeNameForVolumeMountPointW(a1, szVolumeName, 0x100u) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v54, LastError);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
      *(_QWORD *)&v47.Data1 = v50;
      v32 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v50,
              (__int64)L"base\\fs\\fsrm\\utilities\\vss\\srmvss.cpp",
              (__int64)L"SRMVSSUC",
              (__int64)L"CSrmVssUtil::GetAccessAndLiveVolumesNoCache",
              184,
              17);
      CSrmFunctionTracer::TranslatePathError(&v54, v32, Hr, L"GetVolumeNameForVolumeMountPoint");
    }
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumeName, 0x100u);
    v8 = lpszVolumeName;
    if ( !GetVolumeNameForVolumeMountPointW(szVolumeName, lpszVolumeName, 0x100u) )
    {
      v22 = GetLastError();
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v54, v22);
      v23 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
      *(_QWORD *)&v47.Data1 = v50;
      v24 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v50,
              (__int64)L"base\\fs\\fsrm\\utilities\\vss\\srmvss.cpp",
              (__int64)L"SRMVSSUC",
              (__int64)L"CSrmVssUtil::GetAccessAndLiveVolumesNoCache",
              197,
              17);
      CSrmFunctionTracer::TranslatePathError(&v54, v24, v23, L"GetVolumeNameForVolumeMountPoint");
    }
  }
  else
  {
    CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&lpszVolumeName, a1);
    v8 = lpszVolumeName;
  }
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  if ( v8[v9 - 1] != 92 )
  {
    CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&lpszVolumeName, L"\\");
    v8 = lpszVolumeName;
  }
  String1 = 0;
  IsShadowCopyVolume = CSrmVssUtil::IsShadowCopyVolume(v8, (struct CSrmAutoPWSZ *)&String1);
  *a4 = IsShadowCopyVolume;
  if ( IsShadowCopyVolume )
  {
    v45 = 0;
    v11 = CreateVssBackupComponentsInternal(&v45);
    v55 = v11;
    if ( v11 < 0 )
    {
      v28 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v54, v28);
      v29 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v54, 0xDEu, v29, 0);
    }
    v55 = v11;
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v45 + 40LL))(v45, 0);
    v55 = v12;
    if ( v12 < 0 )
    {
      v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v54, v33);
      v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v54, 0xE0u, v34, 0);
    }
    v55 = v12;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 280LL))(v45, 0xFFFFFFFFLL);
    v55 = v13;
    if ( v13 < 0 )
    {
      v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v54, v35);
      v36 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v54, 0xE2u, v36, 0);
    }
    v55 = v13;
    v49 = 0;
    v47 = GUID_NULL;
    v14 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v45 + 344LL))(v45, &v47, 1);
    v55 = v14;
    if ( v14 < 0 )
    {
      v37 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v54, v37);
      v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v54, 0xE8u, v38, 0);
    }
    v55 = v14;
    v48 = 0;
    memset_0(v56, 0, 0x88u);
    while ( 1 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, int *))(*(_QWORD *)v49 + 24LL))(v49, 1, v56, &v48);
      v55 = v15;
      if ( v15 < 0 )
      {
        v41 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v54, v41);
        v42 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v54, 0xF2u, v42, 0);
      }
      v55 = v15;
      if ( v15 == 1 )
      {
        CSrmFunctionTracer::Trace(
          (CSrmFunctionTracer *)&v54,
          0x28u,
          0x129u,
          L"Could not find originating volume for '%s'",
          a1);
        v55 = -2147200234;
        v39 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v54, v39);
        v40 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v54, 0x12Au, v40, 0);
      }
      *(_QWORD *)&v47.Data1 = v57;
      v43 = 0;
      CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v43, String2);
      CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&v43, L"\\");
      v16 = _wcsicmp(String1, String2);
      v17 = v43;
      if ( !v16 || !_wcsicmp(v8, v43) )
        break;
      CoTaskMemFree(v17);
      v43 = 0;
      VssFreeSnapshotPropertiesInternal(v57);
      *(_QWORD *)&v47.Data1 = 0;
    }
    CSrmAutoPWSZ::CopyFrom(a3, v59);
    CoTaskMemFree(*this);
    v43 = 0;
    *this = v17;
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)&v54,
      0x8Cu,
      0x11Du,
      L"Shadow copy volume '%s' found; originating volume = '%s'",
      v17,
      *(_QWORD *)a3);
    CoTaskMemFree(0);
    v43 = 0;
    VssFreeSnapshotPropertiesInternal(v57);
    *(_QWORD *)&v47.Data1 = 0;
    if ( v49 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  else
  {
    if ( _wcsnicmp(a1, L"\\\\?\\GLOBALROOT", 0xEu) )
    {
      CSrmAutoPWSZ::CopyFrom(a3, v8);
    }
    else
    {
      if ( !GetVolumeNameForVolumeMountPointW(a1, szVolumeName, 0x100u) )
      {
        v19 = GetLastError();
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v54, v19);
        v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
        *(_QWORD *)&v47.Data1 = v50;
        v21 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v50,
                (__int64)L"base\\fs\\fsrm\\utilities\\vss\\srmvss.cpp",
                (__int64)L"SRMVSSUC",
                (__int64)L"CSrmVssUtil::GetAccessAndLiveVolumesNoCache",
                319,
                17);
        CSrmFunctionTracer::TranslatePathError(&v54, v21, v20, L"GetVolumeNameForVolumeMountPoint");
      }
      CSrmAutoPWSZ::Allocate(a3, 0x100u);
      if ( !GetVolumeNameForVolumeMountPointW(szVolumeName, *(LPWSTR *)a3, 0x100u) )
      {
        v25 = GetLastError();
        if ( v25 > 0 )
          v25 = (unsigned __int16)v25 | 0x80070000;
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v54, v25);
        v26 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v54);
        *(_QWORD *)&v47.Data1 = v50;
        v27 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v50,
                (__int64)L"base\\fs\\fsrm\\utilities\\vss\\srmvss.cpp",
                (__int64)L"SRMVSSUC",
                (__int64)L"CSrmVssUtil::GetAccessAndLiveVolumesNoCache",
                332,
                17);
        CSrmFunctionTracer::TranslatePathError(&v54, v27, v26, L"GetVolumeNameForVolumeMountPoint");
      }
    }
    CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)this, *(const unsigned __int16 **)a3);
  }
  v18 = L"TRUE";
  if ( !*a4 )
    v18 = L"FALSE";
  CSrmFunctionTracer::Trace(
    (CSrmFunctionTracer *)&v54,
    0x8Cu,
    0x162u,
    L"Volume '%s': shadow copy = '%s', volume canonical access name = '%s', originating volume GUID name = '%s'",
    a1,
    v18,
    *this,
    *(_QWORD *)a3);
  CoTaskMemFree(String1);
  String1 = 0;
  CoTaskMemFree(v8);
  lpszVolumeName = 0;
  v54 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v54);
}

```

## disassembly

```asm
0x18008093c  push    rbp
0x18008093e  push    rbx
0x18008093f  push    rsi
0x180080940  push    rdi
0x180080941  push    r12
0x180080943  push    r13
0x180080945  push    r14
0x180080947  push    r15
0x180080949  lea     rbp, [rsp-368h]
0x180080951  sub     rsp, 468h
0x180080958  mov     rax, cs:__security_cookie
0x18008095f  xor     rax, rsp
0x180080962  mov     [rbp+3A0h+var_50], rax
0x180080969  mov     r12, r9
0x18008096c  mov     rsi, r8
0x18008096f  mov     r15, rdx
0x180080972  mov     r14, rcx
0x180080975  lea     rax, [rbp+3A0h+var_420]
0x180080979  mov     qword ptr [rsp+4A0h+var_440], rax
0x18008097e  lea     rax, aBaseFsFsrmUtil_15; "base\\fs\\fsrm\\utilities\\vss\\srmvss."...
0x180080985  mov     [rbp+3A0h+var_420], rax
0x180080989  lea     rax, aCsrmvssutilGet_0; "CSrmVssUtil::GetAccessAndLiveVolumesNoC"...
0x180080990  mov     [rbp+3A0h+var_418], rax
0x180080994  lea     rax, aSrmvssuc; "SRMVSSUC"
0x18008099b  mov     [rbp+3A0h+var_410], rax
0x18008099f  mov     [rbp+3A0h+var_408], 9Eh
0x1800809a7  xor     r13d, r13d
0x1800809aa  mov     [rbp+3A0h+var_400], 0FFh
0x1800809b1  mov     [rbp+3A0h+var_398], 1000000h
0x1800809b8  xor     edx, edx; Val
0x1800809ba  lea     r8d, [r13+60h]; Size
0x1800809be  lea     rcx, [rbp+3A0h+var_3F8]; void *
0x1800809c2  call    memset_0
0x1800809c7  nop
0x1800809c8  xor     r8d, r8d
0x1800809cb  lea     rdx, [rbp+3A0h+var_420]
0x1800809cf  lea     rcx, [rbp+3A0h+var_390]
0x1800809d3  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800809d8  nop
0x1800809d9  mov     [rsp+4A0h+lpszVolumeName], r13
0x1800809de  lea     r8d, [r13+0Eh]; MaxCount
0x1800809e2  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x1800809e9  mov     rcx, r14; String1
0x1800809ec  call    cs:__imp__wcsnicmp
0x1800809f2  mov     edi, 100h
0x1800809f7  test    eax, eax
0x1800809f9  jnz     loc_180080BEA
0x1800809ff  mov     rdx, r14; unsigned __int16 *
0x180080a02  lea     rcx, [rsp+4A0h+lpszVolumeName]; this
0x180080a07  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180080a0c  mov     rbx, [rsp+4A0h+lpszVolumeName]
0x180080a11  or      rax, 0FFFFFFFFFFFFFFFFh
0x180080a15  inc     rax
0x180080a18  cmp     [rbx+rax*2], r13w
0x180080a1d  jnz     short loc_180080A15
0x180080a1f  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x180080a25  jz      short loc_180080A3D
0x180080a27  lea     rdx, psz; "\\"
0x180080a2e  lea     rcx, [rsp+4A0h+lpszVolumeName]; this
0x180080a33  call    ?Append@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::Append(ushort const *)
0x180080a38  mov     rbx, [rsp+4A0h+lpszVolumeName]
0x180080a3d  mov     [rsp+4A0h+String1], r13
0x180080a42  lea     rdx, [rsp+4A0h+String1]; this
0x180080a47  mov     rcx, rbx; unsigned __int16 *
0x180080a4a  call    ?IsShadowCopyVolume@CSrmVssUtil@@SA_NPEBGAEAVCSrmAutoPWSZ@@@Z; CSrmVssUtil::IsShadowCopyVolume(ushort const *,CSrmAutoPWSZ &)
0x180080a4f  mov     [r12], al
0x180080a53  test    al, al
0x180080a55  jz      loc_180080CD7
0x180080a5b  mov     [rsp+4A0h+var_450], r13
0x180080a60  lea     rcx, [rsp+4A0h+var_450]
0x180080a65  call    cs:__imp_CreateVssBackupComponentsInternal
0x180080a6b  mov     [rbp+3A0h+var_388], eax
0x180080a6e  test    eax, eax
0x180080a70  js      loc_180080F5B
0x180080a76  mov     [rbp+3A0h+var_388], eax
0x180080a79  mov     rcx, [rsp+4A0h+var_450]
0x180080a7e  mov     rax, [rcx]
0x180080a81  xor     edx, edx
0x180080a83  mov     rax, [rax+28h]
0x180080a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080a8c  mov     [rbp+3A0h+var_388], eax
0x180080a8f  test    eax, eax
0x180080a91  js      loc_180081004
0x180080a97  mov     [rbp+3A0h+var_388], eax
0x180080a9a  mov     rcx, [rsp+4A0h+var_450]
0x180080a9f  mov     rax, [rcx]
0x180080aa2  or      edx, 0FFFFFFFFh
0x180080aa5  mov     rax, [rax+118h]
0x180080aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080ab1  mov     [rbp+3A0h+var_388], eax
0x180080ab4  test    eax, eax
0x180080ab6  js      loc_180081036
0x180080abc  mov     [rbp+3A0h+var_388], eax
0x180080abf  mov     [rsp+4A0h+var_428], r13
0x180080ac4  mov     rcx, [rsp+4A0h+var_450]
0x180080ac9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180080ad0  movdqu  [rsp+4A0h+var_440], xmm0
0x180080ad6  mov     rax, [rcx]
0x180080ad9  lea     rdx, [rsp+4A0h+var_428]
0x180080ade  mov     [rsp+4A0h+var_480], rdx
0x180080ae3  mov     r9d, 3
0x180080ae9  lea     r8d, [r9-2]
0x180080aed  lea     rdx, [rsp+4A0h+var_440]
0x180080af2  mov     rax, [rax+158h]
0x180080af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080afe  mov     [rbp+3A0h+var_388], eax
0x180080b01  test    eax, eax
0x180080b03  js      loc_180081068
0x180080b09  mov     [rbp+3A0h+var_388], eax
0x180080b0c  mov     [rsp+4A0h+var_430], r13d
0x180080b11  xor     edx, edx; Val
0x180080b13  mov     r8d, 88h; Size
0x180080b19  lea     rcx, [rbp+3A0h+var_2E0]; void *
0x180080b20  call    memset_0
0x180080b25  mov     rcx, [rsp+4A0h+var_428]
0x180080b2a  mov     rax, [rcx]
0x180080b2d  lea     r9, [rsp+4A0h+var_430]
0x180080b32  lea     r8, [rbp+3A0h+var_2E0]
0x180080b39  mov     edx, 1
0x180080b3e  mov     rax, [rax+18h]
0x180080b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080b47  mov     [rbp+3A0h+var_388], eax
0x180080b4a  test    eax, eax
0x180080b4c  js      loc_1800810F3
0x180080b52  mov     [rbp+3A0h+var_388], eax
0x180080b55  cmp     eax, 1
0x180080b58  jz      loc_18008109A
0x180080b5e  lea     rax, [rbp+3A0h+var_2D8]
0x180080b65  mov     qword ptr [rsp+4A0h+var_440], rax
0x180080b6a  mov     [rsp+4A0h+var_460], r13
0x180080b6f  mov     rdx, [rbp+3A0h+String2]; unsigned __int16 *
0x180080b76  lea     rcx, [rsp+4A0h+var_460]; this
0x180080b7b  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180080b80  lea     rdx, psz; "\\"
0x180080b87  lea     rcx, [rsp+4A0h+var_460]; this
0x180080b8c  call    ?Append@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::Append(ushort const *)
0x180080b91  mov     rdx, [rbp+3A0h+String2]; String2
0x180080b98  mov     rcx, [rsp+4A0h+String1]; String1
0x180080b9d  call    cs:__imp__wcsicmp
0x180080ba3  mov     rdi, [rsp+4A0h+var_460]
0x180080ba8  test    eax, eax
0x180080baa  jz      loc_180080C37
0x180080bb0  mov     rdx, rdi; String2
0x180080bb3  mov     rcx, rbx; String1
0x180080bb6  call    cs:__imp__wcsicmp
0x180080bbc  test    eax, eax
0x180080bbe  jz      short loc_180080C37
0x180080bc0  mov     rcx, rdi; pv
0x180080bc3  call    cs:__imp_CoTaskMemFree
0x180080bc9  mov     [rsp+4A0h+var_460], r13
0x180080bce  mov     [rsp+4A0h+var_460], r13
0x180080bd3  lea     rcx, [rbp+3A0h+var_2D8]
0x180080bda  call    cs:__imp_VssFreeSnapshotPropertiesInternal
0x180080be0  mov     qword ptr [rsp+4A0h+var_440], r13
0x180080be5  jmp     loc_180080B25
0x180080bea  mov     r8d, edi; cchBufferLength
0x180080bed  lea     rdx, [rbp+3A0h+szVolumeName]; lpszVolumeName
0x180080bf4  mov     rcx, r14; lpszVolumeMountPoint
0x180080bf7  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180080bfd  test    eax, eax
0x180080bff  jz      loc_180080F8D
0x180080c05  mov     rdx, rdi; unsigned __int64
0x180080c08  lea     rcx, [rsp+4A0h+lpszVolumeName]; this
0x180080c0d  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x180080c12  mov     r8d, edi; cchBufferLength
0x180080c15  mov     rbx, [rsp+4A0h+lpszVolumeName]
0x180080c1a  mov     rdx, rbx; lpszVolumeName
0x180080c1d  lea     rcx, [rbp+3A0h+szVolumeName]; lpszVolumeMountPoint
0x180080c24  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180080c2a  test    eax, eax
0x180080c2c  jz      loc_180080E6D
0x180080c32  jmp     loc_180080A11
0x180080c37  mov     rdx, [rbp+3A0h+var_2A8]; unsigned __int16 *
0x180080c3e  mov     rcx, rsi; this
0x180080c41  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180080c46  mov     rcx, [r15]; pv
0x180080c49  call    cs:__imp_CoTaskMemFree
0x180080c4f  mov     [rsp+4A0h+var_460], r13
0x180080c54  mov     [r15], rdi
0x180080c57  mov     rax, [rsi]
0x180080c5a  mov     [rsp+4A0h+var_478], rax
0x180080c5f  mov     [rsp+4A0h+var_480], rdi
0x180080c64  lea     r9, aShadowCopyVolu; "Shadow copy volume '%s' found; originat"...
0x180080c6b  mov     edx, 8Ch; unsigned int
0x180080c70  mov     r8d, 11Dh; unsigned int
0x180080c76  lea     rcx, [rbp+3A0h+var_390]; this
0x180080c7a  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x180080c7f  nop
0x180080c80  xor     ecx, ecx; pv
0x180080c82  call    cs:__imp_CoTaskMemFree
0x180080c88  mov     [rsp+4A0h+var_460], r13
0x180080c8d  mov     [rsp+4A0h+var_460], r13
0x180080c92  lea     rcx, [rbp+3A0h+var_2D8]
0x180080c99  call    cs:__imp_VssFreeSnapshotPropertiesInternal
0x180080c9f  mov     qword ptr [rsp+4A0h+var_440], r13
0x180080ca4  mov     rcx, [rsp+4A0h+var_428]
0x180080ca9  test    rcx, rcx
0x180080cac  jz      short loc_180080CBB
0x180080cae  mov     rax, [rcx]
0x180080cb1  mov     rax, [rax+10h]
0x180080cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080cba  nop
0x180080cbb  mov     rcx, [rsp+4A0h+var_450]
0x180080cc0  test    rcx, rcx
0x180080cc3  jz      loc_180080D4A
0x180080cc9  mov     rax, [rcx]
0x180080ccc  mov     rax, [rax+10h]
0x180080cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080cd5  jmp     short loc_180080D4A
0x180080cd7  mov     r8d, 0Eh; MaxCount
0x180080cdd  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x180080ce4  mov     rcx, r14; String1
0x180080ce7  call    cs:__imp__wcsnicmp
0x180080ced  test    eax, eax
0x180080cef  jnz     short loc_180080D34
0x180080cf1  mov     r8d, edi; cchBufferLength
0x180080cf4  lea     rdx, [rbp+3A0h+szVolumeName]; lpszVolumeName
0x180080cfb  mov     rcx, r14; lpszVolumeMountPoint
0x180080cfe  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180080d04  test    eax, eax
0x180080d06  jz      loc_180080DF5
0x180080d0c  mov     rdx, rdi; unsigned __int64
0x180080d0f  mov     rcx, rsi; this
0x180080d12  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x180080d17  mov     r8d, edi; cchBufferLength
0x180080d1a  mov     rdx, [rsi]; lpszVolumeName
0x180080d1d  lea     rcx, [rbp+3A0h+szVolumeName]; lpszVolumeMountPoint
0x180080d24  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180080d2a  test    eax, eax
0x180080d2c  jz      loc_180080EE4
0x180080d32  jmp     short loc_180080D3F
0x180080d34  mov     rdx, rbx; unsigned __int16 *
0x180080d37  mov     rcx, rsi; this
0x180080d3a  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180080d3f  mov     rdx, [rsi]; unsigned __int16 *
0x180080d42  mov     rcx, r15; this
0x180080d45  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180080d4a  lea     rax, aFalse; "FALSE"
0x180080d51  lea     rcx, aTrue_0; "TRUE"
0x180080d58  cmp     [r12], r13b
0x180080d5c  cmovz   rcx, rax
0x180080d60  mov     rax, [rsi]
0x180080d63  mov     [rsp+4A0h+var_468], rax
0x180080d68  mov     rax, [r15]
0x180080d6b  mov     [rsp+4A0h+var_470], rax
0x180080d70  mov     [rsp+4A0h+var_478], rcx
0x180080d75  mov     [rsp+4A0h+var_480], r14
0x180080d7a  lea     r9, aVolumeSShadowC; "Volume '%s': shadow copy = '%s', volume"...
0x180080d81  mov     edx, 8Ch; unsigned int
0x180080d86  mov     r8d, 162h; unsigned int
0x180080d8c  lea     rcx, [rbp+3A0h+var_390]; this
0x180080d90  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x180080d95  nop
0x180080d96  mov     rcx, [rsp+4A0h+String1]; pv
0x180080d9b  call    cs:__imp_CoTaskMemFree
0x180080da1  mov     [rsp+4A0h+String1], r13
0x180080da6  mov     [rsp+4A0h+String1], r13
0x180080dab  mov     rcx, rbx; pv
0x180080dae  call    cs:__imp_CoTaskMemFree
0x180080db4  mov     [rsp+4A0h+lpszVolumeName], r13
0x180080db9  mov     [rsp+4A0h+lpszVolumeName], r13
0x180080dbe  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180080dc5  mov     [rbp+3A0h+var_390], rax
0x180080dc9  lea     rcx, [rbp+3A0h+var_390]; this
0x180080dcd  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180080dd2  mov     rcx, [rbp+3A0h+var_50]
0x180080dd9  xor     rcx, rsp; StackCookie
0x180080ddc  call    __security_check_cookie
0x180080de1  add     rsp, 468h
0x180080de8  pop     r15
0x180080dea  pop     r14
0x180080dec  pop     r13
0x180080dee  pop     r12
0x180080df0  pop     rdi
0x180080df1  pop     rsi
0x180080df2  pop     rbx
0x180080df3  pop     rbp
0x180080df4  retn
0x180080df5  call    cs:__imp_GetLastError
0x180080dfb  nop
0x180080dfc  test    eax, eax
0x180080dfe  jle     short loc_180080E08
0x180080e00  movzx   eax, ax
0x180080e03  or      eax, 80070000h
0x180080e08  mov     edx, eax; int
0x180080e0a  lea     rcx, [rbp+3A0h+var_390]; this
0x180080e0e  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180080e13  lea     rcx, [rbp+3A0h+var_390]; this
0x180080e17  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180080e1c  mov     ebx, eax
0x180080e1e  lea     rax, [rbp+3A0h+var_420]
0x180080e22  mov     qword ptr [rsp+4A0h+var_440], rax
0x180080e27  mov     dword ptr [rsp+4A0h+var_478], 11h
0x180080e2f  mov     dword ptr [rsp+4A0h+var_480], 13Fh
0x180080e37  lea     r9, aCsrmvssutilGet_0; "CSrmVssUtil::GetAccessAndLiveVolumesNoC"...
0x180080e3e  lea     r8, aSrmvssuc; "SRMVSSUC"
0x180080e45  lea     rdx, aBaseFsFsrmUtil_15; "base\\fs\\fsrm\\utilities\\vss\\srmvss."...
0x180080e4c  lea     rcx, [rbp+3A0h+var_420]
0x180080e50  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180080e55  nop
  ... truncated ...
```
