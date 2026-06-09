# CVssHardwareProviderWrapper::OnVolumeArrivalForBreak(ushort *,int,_VSS_VOLUME_DISK_ID_MAPPING *,ulong *)

- ea: `0x14007a974`
- end: `0x14007b2de`
- name: `?OnVolumeArrivalForBreak@CVssHardwareProviderWrapper@@QEAAXPEAGHPEAU_VSS_VOLUME_DISK_ID_MAPPING@@PEAK@Z`
- size: `2410`
- prototype: `void __fastcall(CVssHardwareProviderWrapper *__hidden this, unsigned __int16 *, int, struct _VSS_VOLUME_DISK_ID_MAPPING *, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400c46e0`

## callees

- `0x140008450`
- `0x140009444`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140024ef8`
- `0x140025110`
- `0x14003a8f0`
- `0x140065a90`
- `0x14007a974`
- `0x14007b2e4`
- `0x14007b340`
- `0x14007b4d0`
- `0x140089348`
- `0x140091560`
- `0x1400916f0`
- `0x1400921dc`
- `0x1400c36fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007ae4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007af15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007ae4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007af15`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14007ae3e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14007af07`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14007ae3e`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14007af07`

## string_xrefs

- `0x14007a9c3`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14007ac50`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x14007aebd`: `GetVolumeNameForVolumeMountPoint(%s) fails with 0x%08lx. We cannot accept this volume`
- `0x14007af89`: `GetVolumeNameForVolumeMountPoint(%s) fail on second time. with 0x%08lx. We cannot accept this volume`
- `0x14007b268`: `Fail to open handle to arrived volume hr 0x%08lx `
- `0x14007adc4`: `Found new volume with matching disk id at path %s on local disk no %d. Ending wait.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CVssHardwareProviderWrapper::OnVolumeArrivalForBreak(
        CVssHardwareProviderWrapper *this,
        unsigned __int16 *a2,
        __int64 a3,
        struct _VSS_DISK_ID **a4,
        unsigned int *a5)
{
  _DWORD *v5; // rbx
  unsigned int v6; // ecx
  __int64 v7; // rcx
  struct _VSS_DISK_ID *v8; // rcx
  __int64 v9; // rcx
  signed int v10; // eax
  WCHAR *v11; // r9
  const wchar_t *v12; // r8
  __int64 v13; // rdx
  signed int LastError; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rax
  LPCWSTR v17; // rax
  struct _VSS_VOLUME_DISK_ID_MAPPING *v18; // rcx
  unsigned int v19; // edi
  CVssDiskSignatureManager *v20; // rcx
  unsigned int v21; // r8d
  __int64 v22; // [rsp+20h] [rbp-758h]
  __int64 v23; // [rsp+20h] [rbp-758h]
  __int64 v24; // [rsp+20h] [rbp-758h]
  int v25; // [rsp+28h] [rbp-750h]
  unsigned int v26; // [rsp+50h] [rbp-728h]
  unsigned int v27; // [rsp+50h] [rbp-728h]
  unsigned __int16 *v28; // [rsp+58h] [rbp-720h]
  struct _VSS_DISK_ID *const *v29; // [rsp+68h] [rbp-710h] BYREF
  LPCWSTR lpszVolumeMountPoint; // [rsp+70h] [rbp-708h]
  struct _VSS_DISK_ID *v31; // [rsp+78h] [rbp-700h]
  const unsigned __int16 *v32; // [rsp+80h] [rbp-6F8h] BYREF
  const unsigned __int16 *v33; // [rsp+88h] [rbp-6F0h]
  const unsigned __int16 *v34; // [rsp+90h] [rbp-6E8h]
  int v35; // [rsp+98h] [rbp-6E0h]
  int v36; // [rsp+9Ch] [rbp-6DCh]
  int v37; // [rsp+A0h] [rbp-6D8h]
  _BYTE v38[120]; // [rsp+A8h] [rbp-6D0h] BYREF
  int v39; // [rsp+120h] [rbp-658h]
  unsigned __int16 *v40; // [rsp+128h] [rbp-650h]
  _DWORD *v41; // [rsp+130h] [rbp-648h]
  _DWORD *v42; // [rsp+138h] [rbp-640h]
  struct _VSS_VOLUME_DISK_ID_MAPPING *v43; // [rsp+140h] [rbp-638h]
  LPVOID v44; // [rsp+150h] [rbp-628h] BYREF
  int v45; // [rsp+158h] [rbp-620h]
  unsigned int v46; // [rsp+174h] [rbp-604h]
  __int128 v47; // [rsp+1C0h] [rbp-5B8h] BYREF
  __int64 v48; // [rsp+1D0h] [rbp-5A8h]
  __int64 v49; // [rsp+1D8h] [rbp-5A0h]
  int v50; // [rsp+1E0h] [rbp-598h] BYREF
  __int64 v51; // [rsp+1F0h] [rbp-588h] BYREF
  __int128 v52; // [rsp+1F8h] [rbp-580h]
  __int128 v53; // [rsp+208h] [rbp-570h]
  __int16 v54; // [rsp+218h] [rbp-560h]
  __int64 v55; // [rsp+21Ch] [rbp-55Ch]
  __int64 v56; // [rsp+228h] [rbp-550h]
  __int64 v57; // [rsp+230h] [rbp-548h]
  int v58; // [rsp+238h] [rbp-540h]
  _DWORD *v59; // [rsp+240h] [rbp-538h]
  __int16 v60; // [rsp+248h] [rbp-530h]
  void **v61; // [rsp+250h] [rbp-528h]
  __int64 v62; // [rsp+258h] [rbp-520h]
  _com_error *v63; // [rsp+260h] [rbp-518h] BYREF
  const std::exception *v64; // [rsp+268h] [rbp-510h] BYREF
  _BYTE v65[32]; // [rsp+270h] [rbp-508h] BYREF
  struct _VSS_DISK_ID *v66; // [rsp+290h] [rbp-4E8h]
  WCHAR v68[264]; // [rsp+320h] [rbp-458h] BYREF
  WCHAR szVolumeName[264]; // [rsp+530h] [rbp-248h] BYREF

  v28 = a2;
  v29 = a4;
  v40 = a2;
  v43 = (struct _VSS_VOLUME_DISK_ID_MAPPING *)a4;
  v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
  v34 = L"CORHDELC";
  v35 = 1280;
  v36 = 1;
  v37 = 255;
  v39 = 0x1000000;
  memset_0(v38, 0, sizeof(v38));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v44, (__int64)&v32, 0);
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(v68, 0, 0x208u);
  CVssHwSnapshotInfo::CVssHwSnapshotInfo((CVssHwSnapshotInfo *)v65);
  v51 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v62 = 0;
  v61 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
  v52 = 0;
  v53 = 0;
  v45 = CVssIOCTLChannel::Open((CVssIOCTLChannel *)&v51, (__int64)&v44, v28, 0, 0, 0, 0xC0000000, 3u, 0x80u);
  if ( v45 >= 0 )
  {
    LOBYTE(v25) = 0;
    v45 = CVssIOCTLChannel::Call(&v51, &v44, 5636096, 0, 0, v25, 0);
    if ( v45 < 0 )
    {
      v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
      v34 = L"CORHDELC";
      v35 = 1316;
      v36 = 1;
      v37 = 255;
      v39 = 0x1000000;
      memset_0(v38, 0, sizeof(v38));
      CVssFunctionTracer::Trace(
        &v44,
        &v32,
        L"Fail to get extents for the volume device. [0x%08lx]. Assume check fails, continuing wait",
        (unsigned int)v45);
      goto LABEL_38;
    }
    v31 = 0;
    v5 = v59;
    v41 = v59;
    v6 = *v59;
    v26 = v6;
    v42 = v59 + 2;
    if ( v6 != 1 )
    {
      v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
      v34 = L"CORHDELC";
      v35 = 1328;
      v36 = 1;
      v37 = 255;
      v39 = 0x1000000;
      memset_0(v38, 0, sizeof(v38));
      CVssFunctionTracer::Trace(&v44, &v32, L"Arrival of dynamic volume of %d extents. Ignoring.", v26);
      goto LABEL_38;
    }
    try
    {
      CVssHwSnapshotInfo::Initialize((CVssHwSnapshotInfo *)v65, v59[2]);
      v31 = v66;
    }
    catch ( long v50 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v44,
        v50,
        L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx",
        L"CORHDELC",
        L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak",
        0x544u,
        v46);
      v5 = v41;
      v28 = v40;
    }
    catch ( _com_error *v63 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v44,
        v63,
        L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx",
        L"CORHDELC",
        L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak",
        0x544u,
        v46);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v44,
        L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx",
        L"CORHDELC",
        L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak",
        0x544u,
        v46);
      v5 = v41;
      v28 = v40;
    }
    catch ( const std::exception *v64 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v44,
        v64,
        L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx",
        L"CORHDELC",
        L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak",
        0x544u,
        v46);
    }
    if ( v45 < 0 )
    {
      v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
      v34 = L"CORHDELC";
      v35 = 1353;
      v36 = 1;
      v37 = 255;
      v39 = 0x1000000;
      memset_0(v38, 0, sizeof(v38));
      LODWORD(v22) = *v42;
      CVssFunctionTracer::Trace(&v44, &v32, L"Fail to find HwSnapshotInfo for volume %s, disk no %d", v28, v22);
      goto LABEL_38;
    }
    v47 = 0;
    v48 = 0;
    v49 = 0;
    if ( !CVssDiskSignatureManager::IsMatchingDiskSignature(v20, *v29, v21, v31, v22) )
    {
      v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
      v34 = L"CORHDELC";
      v35 = 1366;
      v36 = 1;
      v37 = 255;
      v39 = 0x1000000;
      memset_0(v38, 0, sizeof(v38));
      CVssFunctionTracer::Trace(
        &v44,
        &v32,
        L"Arrived volume %s disk id not matched with pre-reverted disk id. Continuing wait.",
        v28);
LABEL_8:
      CVssDiskSignatureManager::~CVssDiskSignatureManager((CVssDiskSignatureManager *)&v47);
      goto LABEL_38;
    }
    v7 = *((_QWORD *)v43 + 2);
    v29 = *(struct _VSS_DISK_ID *const **)(v7 + 8);
    v8 = (struct _VSS_DISK_ID *)(v7 + 16);
    v31 = v8;
    if ( v29 == *((struct _VSS_DISK_ID *const **)v5 + 2) )
    {
      if ( *(_QWORD *)v8 == *((_QWORD *)v5 + 3) )
      {
        v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
        v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
        v34 = L"CORHDELC";
        v35 = 1388;
        v36 = 1;
        v37 = 255;
        v39 = 0x1000000;
        memset_0(v38, 0, sizeof(v38));
        LODWORD(v23) = *v42;
        CVssFunctionTracer::Trace(
          &v44,
          &v32,
          L"Found new volume with matching disk id at path %s on local disk no %d. Ending wait.",
          v28,
          v23);
        lpszVolumeMountPoint = 0;
        v29 = (struct _VSS_DISK_ID *const *)&CVssAutoLocalPtr<unsigned short *>::`vftable';
        CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::CopyFrom(&v29, v28);
        v9 = -1;
        do
          ++v9;
        while ( v28[v9] );
        if ( v28[v9 - 1] != 92 )
          CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::Append(&v29, L"\\");
        if ( GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, szVolumeName, 0x104u) )
        {
          if ( GetVolumeNameForVolumeMountPointW(szVolumeName, v68, 0x104u) )
          {
            v15 = -1;
            do
              ++v15;
            while ( v68[v15] );
            if ( v68[v15 - 1] == 92 )
            {
              v16 = 2 * v15 - 2;
              if ( v16 >= 0x208 )
                _report_rangecheckfailure(v68, v13);
              *(WCHAR *)((char *)v68 + v16) = 0;
            }
            CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::CopyFrom(&v29, v68);
            v17 = lpszVolumeMountPoint;
            lpszVolumeMountPoint = 0;
            v18 = v43;
            *((_QWORD *)v43 + 3) = v17;
            *((_DWORD *)v18 + 8) = *v42;
            v19 = (*a5)--;
            v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
            v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
            v34 = L"CORHDELC";
            v35 = 1424;
            v36 = 1;
            v37 = 255;
            v39 = 0x1000000;
            memset_0(v38, 0, sizeof(v38));
            LODWORD(v24) = v19 - 1;
            CVssFunctionTracer::Trace(&v44, &v32, L"Decremented expected device count %d --> %d", v19, v24);
            goto LABEL_20;
          }
          LastError = GetLastError();
          v27 = LastError;
          if ( LastError > 0 )
            v27 = (unsigned __int16)LastError | 0x80070000;
          v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
          v34 = L"CORHDELC";
          v35 = 1408;
          v36 = 6;
          v37 = 255;
          v39 = 0x1000000;
          memset_0(v38, 0, sizeof(v38));
          v11 = szVolumeName;
          v12 = L"GetVolumeNameForVolumeMountPoint(%s) fail on second time. with 0x%08lx. We cannot accept this volume";
        }
        else
        {
          v10 = GetLastError();
          v27 = v10;
          if ( v10 > 0 )
            v27 = (unsigned __int16)v10 | 0x80070000;
          v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
          v34 = L"CORHDELC";
          v35 = 1404;
          v36 = 6;
          v37 = 255;
          v39 = 0x1000000;
          memset_0(v38, 0, sizeof(v38));
          v11 = v28;
          v12 = L"GetVolumeNameForVolumeMountPoint(%s) fails with 0x%08lx. We cannot accept this volume";
        }
        LODWORD(v24) = v27;
        CVssFunctionTracer::Trace(&v44, &v32, v12, v11, v24);
LABEL_20:
        CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v29);
        goto LABEL_8;
      }
    }
    else
    {
      v31 = v8;
    }
    v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
    v34 = L"CORHDELC";
    v35 = 1378;
    v36 = 1;
    v37 = 255;
    v39 = 0x1000000;
    memset_0(v38, 0, sizeof(v38));
    CVssFunctionTracer::Trace(
      &v44,
      &v32,
      L"Fail to match disk extent for arrived volume, continuing wait. Expected: offset 0x%016I64x length 0x%016I64x, Arri"
       "ved: offset 0x%016I64x length 0x%016I64x",
      v29,
      *(_QWORD *)v31,
      *((_QWORD *)v5 + 2),
      *((_QWORD *)v5 + 3));
    goto LABEL_8;
  }
  v32 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v33 = L"CVssHardwareProviderWrapper::OnVolumeArrivalForBreak";
  v34 = L"CORHDELC";
  v35 = 1305;
  v36 = 1;
  v37 = 255;
  v39 = 0x1000000;
  memset_0(v38, 0, sizeof(v38));
  CVssFunctionTracer::Trace(&v44, &v32, L"Fail to open handle to arrived volume hr 0x%08lx ", (unsigned int)v45);
LABEL_38:
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v51);
  CVssHwSnapshotInfo::~CVssHwSnapshotInfo((CVssHwSnapshotInfo *)v65);
  CVssFunctionTracer::~CVssFunctionTracer(&v44);
}

```

## disassembly

```asm
0x14007a974  mov     r11, rsp
0x14007a977  mov     [r11+8], rbx
0x14007a97b  push    rsi
0x14007a97c  push    rdi
0x14007a97d  push    r12
0x14007a97f  push    r13
0x14007a981  push    r15
0x14007a983  sub     rsp, 750h
0x14007a98a  mov     rax, cs:__security_cookie
0x14007a991  xor     rax, rsp
0x14007a994  mov     [rsp+778h+var_38], rax
0x14007a99c  mov     [rsp+778h+var_720], rdx
0x14007a9a1  mov     [rsp+778h+var_710], r9
0x14007a9a6  mov     [rsp+778h+var_650], rdx
0x14007a9ae  mov     [rsp+778h+var_638], r9
0x14007a9b6  mov     rax, [rsp+778h+arg_20]
0x14007a9be  mov     [rsp+778h+var_718], rax
0x14007a9c3  lea     r15, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14007a9ca  mov     [r11-6F8h], r15
0x14007a9d1  lea     r12, aCvsshardwarepr_40; "CVssHardwareProviderWrapper::OnVolumeAr"...
0x14007a9d8  mov     [r11-6F0h], r12
0x14007a9df  lea     r13, aCorhdelc; "CORHDELC"
0x14007a9e6  mov     [r11-6E8h], r13
0x14007a9ed  mov     [rsp+778h+var_6E0], 500h
0x14007a9f8  mov     [rsp+778h+var_6DC], 1
0x14007aa03  mov     edi, 0FFh
0x14007aa08  mov     [rsp+778h+var_6D8], edi
0x14007aa0f  xor     esi, esi
0x14007aa11  mov     [rsp+778h+var_658], 1000000h
0x14007aa1c  lea     ebx, [rsi+78h]
0x14007aa1f  mov     r8d, ebx; Size
0x14007aa22  xor     edx, edx; Val
0x14007aa24  lea     rcx, [r11-6D0h]; void *
0x14007aa2b  call    memset_0
0x14007aa30  xor     r8d, r8d
0x14007aa33  lea     rdx, [rsp+778h+var_6F8]
0x14007aa3b  lea     rcx, [rsp+778h+var_628]
0x14007aa43  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14007aa48  nop
0x14007aa49  xor     edx, edx; Val
0x14007aa4b  mov     r8d, 208h; Size
0x14007aa51  lea     rcx, [rsp+778h+szVolumeName]; void *
0x14007aa59  call    memset_0
0x14007aa5e  xor     edx, edx; Val
0x14007aa60  mov     r8d, 208h; Size
0x14007aa66  lea     rcx, [rsp+778h+var_458]; void *
0x14007aa6e  call    memset_0
0x14007aa73  lea     rcx, [rsp+778h+var_508]; this
0x14007aa7b  call    ??0CVssHwSnapshotInfo@@QEAA@XZ; CVssHwSnapshotInfo::CVssHwSnapshotInfo(void)
0x14007aa80  nop
0x14007aa81  mov     [rsp+778h+var_588], rsi
0x14007aa89  mov     [rsp+778h+var_560], si
0x14007aa91  mov     [rsp+778h+var_55C], rsi
0x14007aa99  mov     [rsp+778h+var_550], rsi
0x14007aaa1  mov     [rsp+778h+var_548], rsi
0x14007aaa9  mov     [rsp+778h+var_540], esi
0x14007aab0  mov     [rsp+778h+var_538], rsi
0x14007aab8  mov     [rsp+778h+var_530], si
0x14007aac0  mov     [rsp+778h+var_520], rsi
0x14007aac8  lea     rax, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x14007aacf  mov     [rsp+778h+var_528], rax
0x14007aad7  xorps   xmm0, xmm0
0x14007aada  movups  [rsp+778h+var_580], xmm0
0x14007aae2  movups  [rsp+778h+var_570], xmm0
0x14007aaea  mov     [rsp+778h+var_738], 80h
0x14007aaf2  mov     [rsp+778h+var_740], 3
0x14007aafa  mov     dword ptr [rsp+778h+var_748], 0C0000000h
0x14007ab02  mov     dword ptr [rsp+778h+var_750], esi
0x14007ab06  mov     byte ptr [rsp+778h+var_758], sil
0x14007ab0b  xor     r9d, r9d
0x14007ab0e  mov     r8, [rsp+778h+var_720]
0x14007ab13  lea     rdx, [rsp+778h+var_628]
0x14007ab1b  lea     rcx, [rsp+778h+var_588]
0x14007ab23  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x14007ab28  mov     [rsp+778h+var_620], eax
0x14007ab2f  test    eax, eax
0x14007ab31  js      loc_14007B216
0x14007ab37  mov     [rsp+778h+var_748], rsi
0x14007ab3c  mov     byte ptr [rsp+778h+var_750], sil
0x14007ab41  mov     dword ptr [rsp+778h+var_758], esi
0x14007ab45  xor     r9d, r9d
0x14007ab48  mov     r8d, 560000h
0x14007ab4e  lea     rdx, [rsp+778h+var_628]
0x14007ab56  lea     rcx, [rsp+778h+var_588]
0x14007ab5e  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x14007ab63  mov     [rsp+778h+var_620], eax
0x14007ab6a  test    eax, eax
0x14007ab6c  js      loc_14007B1BB
0x14007ab72  mov     [rsp+778h+var_700], rsi
0x14007ab77  mov     rbx, [rsp+778h+var_538]
0x14007ab7f  mov     [rsp+778h+var_648], rbx
0x14007ab87  mov     ecx, [rbx]
0x14007ab89  mov     [rsp+778h+var_728], ecx
0x14007ab8d  lea     rax, [rbx+8]
0x14007ab91  mov     [rsp+778h+var_640], rax
0x14007ab99  cmp     ecx, 1
0x14007ab9c  jz      short loc_14007AC02
0x14007ab9e  mov     [rsp+778h+var_6F8], r15
0x14007aba6  mov     [rsp+778h+var_6F0], r12
0x14007abae  mov     [rsp+778h+var_6E8], r13
0x14007abb6  mov     [rsp+778h+var_6E0], 530h
0x14007abc1  mov     [rsp+778h+var_6DC], 1
0x14007abcc  mov     [rsp+778h+var_6D8], edi
0x14007abd3  mov     [rsp+778h+var_658], 1000000h
0x14007abde  xor     edx, edx; Val
0x14007abe0  lea     r8d, [rsi+78h]; Size
0x14007abe4  lea     rcx, [rsp+778h+var_6D0]; void *
0x14007abec  call    memset_0
0x14007abf1  mov     r9d, [rsp+778h+var_728]
0x14007abf6  lea     r8, aArrivalOfDynam; "Arrival of dynamic volume of %d extents"...
0x14007abfd  jmp     loc_14007B277
0x14007ac02  mov     edx, [rax]; unsigned int
0x14007ac04  lea     rcx, [rsp+778h+var_508]; this
0x14007ac0c  call    ?Initialize@CVssHwSnapshotInfo@@QEAAXK@Z; CVssHwSnapshotInfo::Initialize(ulong)
0x14007ac11  mov     rax, [rsp+778h+var_4E8]
0x14007ac19  mov     [rsp+778h+var_700], rax
0x14007ac1e  jmp     short loc_14007AC57
0x14007ac20  jmp     short loc_14007AC26
0x14007ac22  jmp     short loc_14007AC26
0x14007ac24  jmp     short $+2
0x14007ac26  mov     rax, [rsp+778h+var_650]
0x14007ac2e  mov     rbx, [rsp+778h+var_648]
0x14007ac36  mov     [rsp+778h+var_720], rax
0x14007ac3b  xor     esi, esi
0x14007ac3d  mov     edi, 0FFh
0x14007ac42  lea     r13, aCorhdelc; "CORHDELC"
0x14007ac49  lea     r12, aCvsshardwarepr_40; "CVssHardwareProviderWrapper::OnVolumeAr"...
0x14007ac50  lea     r15, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14007ac57  cmp     [rsp+778h+var_620], esi
0x14007ac5e  jl      loc_14007B134
0x14007ac64  xorps   xmm0, xmm0
0x14007ac67  movdqu  [rsp+778h+var_5B8], xmm0
0x14007ac70  mov     [rsp+778h+var_5A8], rsi
0x14007ac78  mov     [rsp+778h+var_5A0], 0
0x14007ac84  mov     r9, [rsp+778h+var_700]; struct _VSS_DISK_ID *
0x14007ac89  mov     rdx, [rsp+778h+var_710]
0x14007ac8e  mov     rdx, [rdx]; struct _VSS_DISK_ID *
0x14007ac91  call    ?IsMatchingDiskSignature@CVssDiskSignatureManager@@QEAA_NQEAU_VSS_DISK_ID@@K0K@Z; CVssDiskSignatureManager::IsMatchingDiskSignature(_VSS_DISK_ID * const,ulong,_VSS_DISK_ID * const,ulong)
0x14007ac96  test    al, al
0x14007ac98  jnz     loc_14007AD25
0x14007ac9e  mov     [rsp+778h+var_6F8], r15
0x14007aca6  mov     [rsp+778h+var_6F0], r12
0x14007acae  mov     [rsp+778h+var_6E8], r13
0x14007acb6  mov     [rsp+778h+var_6E0], 556h
0x14007acc1  mov     [rsp+778h+var_6DC], 1
0x14007accc  mov     [rsp+778h+var_6D8], edi
0x14007acd3  mov     [rsp+778h+var_658], 1000000h
0x14007acde  xor     edx, edx; Val
0x14007ace0  lea     r8d, [rdx+78h]; Size
0x14007ace4  lea     rcx, [rsp+778h+var_6D0]; void *
0x14007acec  call    memset_0
0x14007acf1  mov     r9, [rsp+778h+var_720]
0x14007acf6  lea     r8, aArrivedVolumeS; "Arrived volume %s disk id not matched w"...
0x14007acfd  lea     rdx, [rsp+778h+var_6F8]
0x14007ad05  lea     rcx, [rsp+778h+var_628]
0x14007ad0d  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14007ad12  nop
0x14007ad13  lea     rcx, [rsp+778h+var_5B8]; this
0x14007ad1b  call    ??1CVssDiskSignatureManager@@QEAA@XZ; CVssDiskSignatureManager::~CVssDiskSignatureManager(void)
0x14007ad20  jmp     loc_14007B28D
0x14007ad25  mov     rax, [rsp+778h+var_638]
0x14007ad2d  mov     rcx, [rax+10h]
0x14007ad31  mov     rax, [rcx+8]
0x14007ad35  mov     [rsp+778h+var_710], rax
0x14007ad3a  add     rcx, 10h
0x14007ad3e  mov     [rsp+778h+var_700], rcx
0x14007ad43  cmp     rax, [rbx+10h]
0x14007ad47  jnz     loc_14007B097
0x14007ad4d  mov     rax, [rbx+18h]
0x14007ad51  cmp     [rcx], rax
0x14007ad54  jnz     loc_14007B09C
0x14007ad5a  mov     [rsp+778h+var_6F8], r15
0x14007ad62  mov     [rsp+778h+var_6F0], r12
0x14007ad6a  mov     [rsp+778h+var_6E8], r13
0x14007ad72  mov     [rsp+778h+var_6E0], 56Ch
0x14007ad7d  mov     [rsp+778h+var_6DC], 1
0x14007ad88  mov     [rsp+778h+var_6D8], edi
0x14007ad8f  mov     [rsp+778h+var_658], 1000000h
0x14007ad9a  mov     ebx, 78h ; 'x'
0x14007ad9f  mov     r8d, ebx; Size
0x14007ada2  xor     edx, edx; Val
0x14007ada4  lea     rcx, [rsp+778h+var_6D0]; void *
0x14007adac  call    memset_0
0x14007adb1  mov     rcx, [rsp+778h+var_640]
0x14007adb9  mov     eax, [rcx]
0x14007adbb  mov     dword ptr [rsp+778h+var_758], eax
0x14007adbf  mov     r9, [rsp+778h+var_720]
0x14007adc4  lea     r8, aFoundNewVolume; "Found new volume with matching disk id "...
0x14007adcb  lea     rdx, [rsp+778h+var_6F8]
0x14007add3  lea     rcx, [rsp+778h+var_628]
0x14007addb  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14007ade0  mov     [rsp+778h+lpszVolumeMountPoint], rsi
0x14007ade5  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x14007adec  mov     [rsp+778h+var_710], rax
0x14007adf1  mov     rdx, [rsp+778h+var_720]
0x14007adf6  lea     rcx, [rsp+778h+var_710]
0x14007adfb  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::CopyFrom(ushort const *)
0x14007ae00  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14007ae04  mov     rax, [rsp+778h+var_720]
0x14007ae09  inc     rcx
0x14007ae0c  cmp     [rax+rcx*2], si
0x14007ae10  jnz     short loc_14007AE09
0x14007ae12  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14007ae18  jz      short loc_14007AE2B
0x14007ae1a  lea     rdx, pszSrc; "\\"
0x14007ae21  lea     rcx, [rsp+778h+var_710]
0x14007ae26  call    ?Append@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::Append(ushort const *)
0x14007ae2b  mov     r8d, 104h; cchBufferLength
0x14007ae31  lea     rdx, [rsp+778h+szVolumeName]; lpszVolumeName
0x14007ae39  mov     rcx, [rsp+778h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x14007ae3e  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14007ae44  test    eax, eax
0x14007ae46  jnz     loc_14007AEF1
0x14007ae4c  call    cs:__imp_GetLastError
0x14007ae52  mov     [rsp+778h+var_728], eax
0x14007ae56  test    eax, eax
0x14007ae58  jle     short loc_14007AE66
0x14007ae5a  movzx   eax, ax
0x14007ae5d  or      eax, 80070000h
0x14007ae62  mov     [rsp+778h+var_728], eax
0x14007ae66  mov     [rsp+778h+var_6F8], r15
0x14007ae6e  mov     [rsp+778h+var_6F0], r12
0x14007ae76  mov     [rsp+778h+var_6E8], r13
0x14007ae7e  mov     [rsp+778h+var_6E0], 57Ch
0x14007ae89  mov     [rsp+778h+var_6DC], 6
0x14007ae94  mov     [rsp+778h+var_6D8], edi
0x14007ae9b  mov     [rsp+778h+var_658], 1000000h
0x14007aea6  mov     r8, rbx; Size
0x14007aea9  xor     edx, edx; Val
0x14007aeab  lea     rcx, [rsp+778h+var_6D0]; void *
0x14007aeb3  call    memset_0
0x14007aeb8  mov     r9, [rsp+778h+var_720]
0x14007aebd  lea     r8, aGetvolumenamef_1; "GetVolumeNameForVolumeMountPoint(%s) fa"...
0x14007aec4  mov     eax, [rsp+778h+var_728]
0x14007aec8  mov     dword ptr [rsp+778h+var_758], eax
0x14007aecc  lea     rdx, [rsp+778h+var_6F8]
0x14007aed4  lea     rcx, [rsp+778h+var_628]
0x14007aedc  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14007aee1  nop
0x14007aee2  lea     rcx, [rsp+778h+var_710]
0x14007aee7  call    ??1?$CVssAutoLocalPtr@PEAX@@UEAA@XZ; CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(void)
0x14007aeec  jmp     loc_14007AD13
0x14007aef1  mov     r8d, 104h; cchBufferLength
0x14007aef7  lea     rdx, [rsp+778h+var_458]; lpszVolumeName
0x14007aeff  lea     rcx, [rsp+778h+szVolumeName]; lpszVolumeMountPoint
0x14007af07  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14007af0d  test    eax, eax
0x14007af0f  jnz     loc_14007AF95
0x14007af15  call    cs:__imp_GetLastError
0x14007af1b  mov     [rsp+778h+var_728], eax
0x14007af1f  test    eax, eax
0x14007af21  jle     short loc_14007AF2F
0x14007af23  movzx   eax, ax
0x14007af26  or      eax, 80070000h
0x14007af2b  mov     [rsp+778h+var_728], eax
0x14007af2f  mov     [rsp+778h+var_6F8], r15
0x14007af37  mov     [rsp+778h+var_6F0], r12
0x14007af3f  mov     [rsp+778h+var_6E8], r13
0x14007af47  mov     [rsp+778h+var_6E0], 580h
0x14007af52  mov     [rsp+778h+var_6DC], 6
0x14007af5d  mov     [rsp+778h+var_6D8], edi
0x14007af64  mov     [rsp+778h+var_658], 1000000h
0x14007af6f  mov     r8, rbx; Size
0x14007af72  xor     edx, edx; Val
0x14007af74  lea     rcx, [rsp+778h+var_6D0]; void *
0x14007af7c  call    memset_0
0x14007af81  lea     r9, [rsp+778h+szVolumeName]
0x14007af89  lea     r8, aGetvolumenamef_16; "GetVolumeNameForVolumeMountPoint(%s) fa"...
0x14007af90  jmp     loc_14007AEC4
0x14007af95  lea     rcx, [rsp+778h+var_458]
0x14007af9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14007afa1  inc     rax
0x14007afa4  cmp     [rcx+rax*2], si
0x14007afa8  jnz     short loc_14007AFA1
0x14007afaa  cmp     [rsp+rax*2+778h+var_45A], 5Ch ; '\'
0x14007afb3  jnz     short loc_14007AFD1
0x14007afb5  lea     rax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x14007afbd  cmp     rax, 208h
0x14007afc3  jnb     loc_14007B091
0x14007afc9  mov     [rsp+rax+778h+var_458], si
0x14007afd1  lea     rdx, [rsp+778h+var_458]
0x14007afd9  lea     rcx, [rsp+778h+var_710]
0x14007afde  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::CopyFrom(ushort const *)
0x14007afe3  mov     rax, [rsp+778h+lpszVolumeMountPoint]
0x14007afe8  mov     [rsp+778h+lpszVolumeMountPoint], rsi
0x14007afed  mov     rcx, [rsp+778h+var_638]
0x14007aff5  mov     [rcx+18h], rax
0x14007aff9  mov     rax, [rsp+778h+var_640]
0x14007b001  mov     eax, [rax]
0x14007b003  mov     [rcx+20h], eax
0x14007b006  mov     rax, [rsp+778h+var_718]
0x14007b00b  mov     edi, [rax]
0x14007b00d  lea     ebx, [rdi-1]
0x14007b010  mov     [rax], ebx
0x14007b012  mov     [rsp+778h+var_6F8], r15
0x14007b01a  mov     [rsp+778h+var_6F0], r12
0x14007b022  mov     [rsp+778h+var_6E8], r13
0x14007b02a  mov     [rsp+778h+var_6E0], 590h
0x14007b035  mov     [rsp+778h+var_6DC], 1
0x14007b040  mov     [rsp+778h+var_6D8], 0FFh
  ... truncated ...
```
