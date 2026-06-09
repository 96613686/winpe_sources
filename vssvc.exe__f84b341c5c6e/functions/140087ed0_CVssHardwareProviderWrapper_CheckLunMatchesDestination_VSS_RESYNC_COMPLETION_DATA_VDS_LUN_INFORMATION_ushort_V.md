# CVssHardwareProviderWrapper::CheckLunMatchesDestination(_VSS_RESYNC_COMPLETION_DATA *,_VDS_LUN_INFORMATION *,ushort *,_VOLUME_DISK_EXTENTS *)

- ea: `0x140087ed0`
- end: `0x14008838f`
- name: `?CheckLunMatchesDestination@CVssHardwareProviderWrapper@@AEAA_NPEAU_VSS_RESYNC_COMPLETION_DATA@@PEAU_VDS_LUN_INFORMATION@@PEAGPEAU_VOLUME_DISK_EXTENTS@@@Z`
- size: `1215`
- prototype: `bool __fastcall(CVssHardwareProviderWrapper *__hidden this, struct _VSS_RESYNC_COMPLETION_DATA *, struct _VDS_LUN_INFORMATION *, unsigned __int16 *, struct _VOLUME_DISK_EXTENTS *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400c9d34`

## callees

- `0x140011a90`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140024ef8`
- `0x140025110`
- `0x14003a8f0`
- `0x140087ed0`
- `0x140091560`
- `0x1400921dc`
- `0x1400b8c3c`
- `0x1400b9058`
- `0x1400bfe60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008818d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140088231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008818d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140088231`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14008817f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140088227`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14008817f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140088227`

## string_xrefs

- `0x1400881f8`: `GetVolumeNameForVolumeMountPoint(%s) fails with 0x%08lx after matching. We cannot accept this volume`
- `0x1400882a0`: `GetVolumeNameForVolumeMountPoint(%s) fail on second time. with 0x%08lx after matching. We cannot accept this volume`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CVssHardwareProviderWrapper::CheckLunMatchesDestination(
        CVssHardwareProviderWrapper *this,
        struct _VSS_RESYNC_COMPLETION_DATA *a2,
        struct _VDS_LUN_INFORMATION *a3,
        unsigned __int16 *a4,
        struct _VOLUME_DISK_EXTENTS *a5)
{
  CVssHardwareProviderWrapper *v8; // rcx
  unsigned int i; // edi
  bool v10; // dl
  unsigned int v11; // edi
  __int64 v12; // r14
  const struct _VDS_LUN_INFORMATION *v13; // r15
  CVssHardwareProviderWrapper *v14; // rcx
  __int64 v15; // rax
  signed int v16; // eax
  unsigned int v17; // ebx
  WCHAR *v18; // r9
  const wchar_t *v19; // r8
  CVssHardwareProviderWrapper *v20; // rcx
  signed int LastError; // eax
  LPCWSTR v22; // rbx
  bool v23; // bl
  void **v25; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpszVolumeMountPoint; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v27; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v28; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  int v32; // [rsp+68h] [rbp-98h]
  _BYTE v33[120]; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+E8h] [rbp-18h]
  LPVOID v35[14]; // [rsp+F0h] [rbp-10h] BYREF
  _VOLUME_DISK_EXTENTS v36; // [rsp+160h] [rbp+60h] BYREF
  WCHAR szVolumeName[264]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR v38[264]; // [rsp+390h] [rbp+290h] BYREF

  v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
  v28 = L"CVssHardwareProviderWrapper::CheckLunMatchesDestination";
  v29 = L"CORHRSNC";
  v30 = 2192;
  v31 = 1;
  v32 = 255;
  v34 = 0x1000000;
  memset_0(v33, 0, sizeof(v33));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v35, (__int64)&v27, 0);
  memset(&v36, 0, sizeof(v36));
  memset_0(szVolumeName, 0, 0x208u);
  memset_0(v38, 0, 0x208u);
  lpszVolumeMountPoint = 0;
  v25 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  for ( i = 0; i < *((_DWORD *)a2 + 8); ++i )
  {
    if ( CVssHardwareProviderWrapper::IsMatchLun(
           v8,
           a3,
           (const struct _VDS_LUN_INFORMATION *)(*((_QWORD *)a2 + 3) + 96LL * i),
           0) )
    {
      break;
    }
  }
  if ( i == *((_DWORD *)a2 + 8) )
  {
    v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
    v28 = L"CVssHardwareProviderWrapper::CheckLunMatchesDestination";
    v29 = L"CORHRSNC";
    v30 = 2214;
    v31 = 1;
    v32 = 255;
    v34 = 0x1000000;
    memset_0(v33, 0, sizeof(v33));
    CVssFunctionTracer::Trace(v35, &v27, L"Lun info of volume %s not expected. Ignoring.", a4);
  }
  else
  {
    v11 = 0;
    if ( *((_DWORD *)a2 + 4) )
    {
      do
      {
        v12 = *(_QWORD *)(*(_QWORD *)a2 + 8LL * v11);
        if ( !*(_QWORD *)(v12 + 48) )
        {
          v13 = *(const struct _VDS_LUN_INFORMATION **)(*((_QWORD *)a2 + 1) + 8LL * v11);
          v36.NumberOfDiskExtents = 1;
          v36.Extents[0] = *(DISK_EXTENT *)*(_QWORD *)(v12 + 8);
          if ( CVssHardwareProviderWrapper::IsMatchingDiskExtents((CVssHardwareProviderWrapper *)v11, a5, &v36)
            && CVssHardwareProviderWrapper::IsMatchLun(v14, a3, v13 + 1, 0) )
          {
            break;
          }
        }
        ++v11;
      }
      while ( v11 < *((_DWORD *)a2 + 4) );
    }
    else
    {
      v12 = 0;
    }
    if ( v11 == *((_DWORD *)a2 + 4) )
    {
      v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
      v28 = L"CVssHardwareProviderWrapper::CheckLunMatchesDestination";
      v29 = L"CORHRSNC";
      v30 = 2247;
      v31 = 1;
      v32 = 255;
      v34 = 0x1000000;
      memset_0(v33, 0, sizeof(v33));
      CVssFunctionTracer::Trace(v35, &v27, L"Extents for volume %s not found. Ignoring.", a4);
    }
    else
    {
      CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::CopyFrom(&v25, a4);
      v15 = -1;
      do
        ++v15;
      while ( a4[v15] );
      if ( a4[v15 - 1] != 92 )
        CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::Append(&v25, L"\\");
      if ( GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, szVolumeName, 0x104u) )
      {
        if ( GetVolumeNameForVolumeMountPointW(szVolumeName, v38, 0x104u) )
        {
          CVssHardwareProviderWrapper::RemoveTrailingSlashFromPath(v20, v38);
          CVssAutoString<CVssAutoLocalPtr<unsigned short *>>::CopyFrom(&v25, v38);
          v22 = lpszVolumeMountPoint;
          lpszVolumeMountPoint = 0;
          *(_QWORD *)(v12 + 48) = v22;
          v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
          v28 = L"CVssHardwareProviderWrapper::CheckLunMatchesDestination";
          v29 = L"CORHRSNC";
          v30 = 2277;
          v31 = 1;
          v32 = 255;
          v34 = 0x1000000;
          memset_0(v33, 0, sizeof(v33));
          CVssFunctionTracer::Trace(v35, &v27, L"Found volume name %s for arrived volume", v22);
          v10 = 1;
          goto LABEL_30;
        }
        LastError = GetLastError();
        v17 = LastError;
        if ( LastError > 0 )
          v17 = (unsigned __int16)LastError | 0x80070000;
        v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
        v28 = L"CVssHardwareProviderWrapper::CheckLunMatchesDestination";
        v29 = L"CORHRSNC";
        v30 = 2265;
        v31 = 1;
        v32 = 255;
        v34 = 0x1000000;
        memset_0(v33, 0, sizeof(v33));
        v18 = szVolumeName;
        v19 = L"GetVolumeNameForVolumeMountPoint(%s) fail on second time. with 0x%08lx after matching. We cannot accept this volume";
      }
      else
      {
        v16 = GetLastError();
        v17 = v16;
        if ( v16 > 0 )
          v17 = (unsigned __int16)v16 | 0x80070000;
        v27 = L"base\\stor\\vss\\modules\\coord\\src\\hwresync.cxx";
        v28 = L"CVssHardwareProviderWrapper::CheckLunMatchesDestination";
        v29 = L"CORHRSNC";
        v30 = 2261;
        v31 = 1;
        v32 = 255;
        v34 = 0x1000000;
        memset_0(v33, 0, sizeof(v33));
        v18 = a4;
        v19 = L"GetVolumeNameForVolumeMountPoint(%s) fails with 0x%08lx after matching. We cannot accept this volume";
      }
      CVssFunctionTracer::Trace(v35, &v27, v19, v18, v17);
    }
  }
  v10 = 0;
LABEL_30:
  v23 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v35, v10);
  CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v25);
  CVssFunctionTracer::~CVssFunctionTracer(v35);
  return v23;
}

```

## disassembly

```asm
0x140087ed0  mov     [rsp-8+arg_0], rbx
0x140087ed5  push    rbp
0x140087ed6  push    rsi
0x140087ed7  push    rdi
0x140087ed8  push    r12
0x140087eda  push    r13
0x140087edc  push    r14
0x140087ede  push    r15
0x140087ee0  lea     rbp, [rsp-4B0h]
0x140087ee8  sub     rsp, 5B0h
0x140087eef  mov     rax, cs:__security_cookie
0x140087ef6  xor     rax, rsp
0x140087ef9  mov     [rbp+4E0h+var_40], rax
0x140087f00  mov     rsi, r9
0x140087f03  mov     r12, r8
0x140087f06  mov     rbx, rdx
0x140087f09  mov     r13, [rbp+4E0h+arg_20]
0x140087f10  lea     rax, aBaseStorVssMod_28; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140087f17  mov     [rsp+5E0h+var_598], rax
0x140087f1c  lea     rax, aCvsshardwarepr_173; "CVssHardwareProviderWrapper::CheckLunMa"...
0x140087f23  mov     [rsp+5E0h+var_590], rax
0x140087f28  lea     rax, aCorhrsnc; "CORHRSNC"
0x140087f2f  mov     [rsp+5E0h+var_588], rax
0x140087f34  mov     [rsp+5E0h+var_580], 890h
0x140087f3c  mov     r14d, 1
0x140087f42  mov     [rsp+5E0h+var_57C], r14d
0x140087f47  mov     [rsp+5E0h+var_578], 0FFh
0x140087f4f  xor     r15d, r15d
0x140087f52  mov     [rbp+4E0h+var_4F8], 1000000h
0x140087f59  xor     edx, edx; Val
0x140087f5b  lea     r8d, [r14+77h]; Size
0x140087f5f  lea     rcx, [rsp+5E0h+var_570]; void *
0x140087f64  call    memset_0
0x140087f69  xor     r8d, r8d
0x140087f6c  lea     rdx, [rsp+5E0h+var_598]
0x140087f71  lea     rcx, [rbp+4E0h+var_4F0]
0x140087f75  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140087f7a  nop
0x140087f7b  xorps   xmm0, xmm0
0x140087f7e  movups  xmmword ptr [rbp+4E0h+var_480.NumberOfDiskExtents], xmm0
0x140087f82  movups  xmmword ptr [rbp+4E0h+var_480.Extents.StartingOffset], xmm0
0x140087f86  mov     edi, 208h
0x140087f8b  mov     r8d, edi; Size
0x140087f8e  xor     edx, edx; Val
0x140087f90  lea     rcx, [rbp+4E0h+szVolumeName]; void *
0x140087f97  call    memset_0
0x140087f9c  mov     r8d, edi; Size
0x140087f9f  xor     edx, edx; Val
0x140087fa1  lea     rcx, [rbp+4E0h+var_250]; void *
0x140087fa8  call    memset_0
0x140087fad  mov     [rsp+5E0h+lpszVolumeMountPoint], r15
0x140087fb2  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140087fb9  mov     [rsp+5E0h+var_5A8], rax
0x140087fbe  mov     edi, r15d
0x140087fc1  cmp     [rbx+20h], r15d
0x140087fc5  jbe     short loc_140087FEC
0x140087fc7  mov     eax, edi
0x140087fc9  lea     r8, [rax+rax*2]
0x140087fcd  shl     r8, 5
0x140087fd1  add     r8, [rbx+18h]; struct _VDS_LUN_INFORMATION *
0x140087fd5  xor     r9d, r9d; bool
0x140087fd8  mov     rdx, r12; struct _VDS_LUN_INFORMATION *
0x140087fdb  call    ?IsMatchLun@CVssHardwareProviderWrapper@@AEAA_NAEBU_VDS_LUN_INFORMATION@@0_N@Z; CVssHardwareProviderWrapper::IsMatchLun(_VDS_LUN_INFORMATION const &,_VDS_LUN_INFORMATION const &,bool)
0x140087fe0  test    al, al
0x140087fe2  jnz     short loc_140087FEC
0x140087fe4  add     edi, r14d
0x140087fe7  cmp     edi, [rbx+20h]
0x140087fea  jb      short loc_140087FC7
0x140087fec  cmp     edi, [rbx+20h]
0x140087fef  jnz     short loc_140088060
0x140087ff1  lea     rax, aBaseStorVssMod_28; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140087ff8  mov     [rsp+5E0h+var_598], rax
0x140087ffd  lea     rax, aCvsshardwarepr_173; "CVssHardwareProviderWrapper::CheckLunMa"...
0x140088004  mov     [rsp+5E0h+var_590], rax
0x140088009  lea     rax, aCorhrsnc; "CORHRSNC"
0x140088010  mov     [rsp+5E0h+var_588], rax
0x140088015  mov     [rsp+5E0h+var_580], 8A6h
0x14008801d  mov     [rsp+5E0h+var_57C], r14d
0x140088022  mov     [rsp+5E0h+var_578], 0FFh
0x14008802a  mov     [rbp+4E0h+var_4F8], 1000000h
0x140088031  xor     edx, edx; Val
0x140088033  lea     r8d, [rdx+78h]; Size
0x140088037  lea     rcx, [rsp+5E0h+var_570]; void *
0x14008803c  call    memset_0
0x140088041  lea     r8, aLunInfoOfVolum; "Lun info of volume %s not expected. Ign"...
0x140088048  mov     r9, rsi
0x14008804b  lea     rdx, [rsp+5E0h+var_598]
0x140088050  lea     rcx, [rbp+4E0h+var_4F0]
0x140088054  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140088059  xor     edx, edx
0x14008805b  jmp     loc_140088344
0x140088060  mov     edi, r15d
0x140088063  cmp     [rbx+10h], r15d
0x140088067  jbe     short loc_1400880D0
0x140088069  mov     ecx, edi; this
0x14008806b  mov     rax, [rbx]
0x14008806e  mov     r14, [rax+rcx*8]
0x140088072  cmp     [r14+30h], r15
0x140088076  jnz     short loc_1400880C7
0x140088078  mov     rax, [rbx+8]
0x14008807c  mov     r15, [rax+rcx*8]
0x140088080  mov     [rbp+4E0h+var_480.NumberOfDiskExtents], 1
0x140088087  mov     rax, [r14+8]
0x14008808b  movups  xmm0, xmmword ptr [rax]
0x14008808e  movups  xmmword ptr [rbp+4E0h+var_480.Extents.DiskNumber], xmm0
0x140088092  movsd   xmm1, qword ptr [rax+10h]
0x140088097  movsd   qword ptr [rbp+4E0h+var_480.Extents.ExtentLength], xmm1
0x14008809c  lea     r8, [rbp+4E0h+var_480]; struct _VOLUME_DISK_EXTENTS *
0x1400880a0  mov     rdx, r13; struct _VOLUME_DISK_EXTENTS *
0x1400880a3  call    ?IsMatchingDiskExtents@CVssHardwareProviderWrapper@@AEAA_NPEBU_VOLUME_DISK_EXTENTS@@0@Z; CVssHardwareProviderWrapper::IsMatchingDiskExtents(_VOLUME_DISK_EXTENTS const *,_VOLUME_DISK_EXTENTS const *)
0x1400880a8  test    al, al
0x1400880aa  jz      short loc_1400880C4
0x1400880ac  lea     r8, [r15+60h]; struct _VDS_LUN_INFORMATION *
0x1400880b0  xor     r9d, r9d; bool
0x1400880b3  mov     rdx, r12; struct _VDS_LUN_INFORMATION *
0x1400880b6  call    ?IsMatchLun@CVssHardwareProviderWrapper@@AEAA_NAEBU_VDS_LUN_INFORMATION@@0_N@Z; CVssHardwareProviderWrapper::IsMatchLun(_VDS_LUN_INFORMATION const &,_VDS_LUN_INFORMATION const &,bool)
0x1400880bb  xor     r15d, r15d
0x1400880be  test    al, al
0x1400880c0  jnz     short loc_1400880D3
0x1400880c2  jmp     short loc_1400880C7
0x1400880c4  xor     r15d, r15d
0x1400880c7  inc     edi
0x1400880c9  cmp     edi, [rbx+10h]
0x1400880cc  jb      short loc_140088069
0x1400880ce  jmp     short loc_1400880D3
0x1400880d0  mov     r14, r15
0x1400880d3  cmp     edi, [rbx+10h]
0x1400880d6  jnz     short loc_140088137
0x1400880d8  lea     rax, aBaseStorVssMod_28; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400880df  mov     [rsp+5E0h+var_598], rax
0x1400880e4  lea     rax, aCvsshardwarepr_173; "CVssHardwareProviderWrapper::CheckLunMa"...
0x1400880eb  mov     [rsp+5E0h+var_590], rax
0x1400880f0  lea     rax, aCorhrsnc; "CORHRSNC"
0x1400880f7  mov     [rsp+5E0h+var_588], rax
0x1400880fc  mov     [rsp+5E0h+var_580], 8C7h
0x140088104  mov     [rsp+5E0h+var_57C], 1
0x14008810c  mov     [rsp+5E0h+var_578], 0FFh
0x140088114  mov     [rbp+4E0h+var_4F8], 1000000h
0x14008811b  xor     edx, edx; Val
0x14008811d  lea     r8d, [rdx+78h]; Size
0x140088121  lea     rcx, [rsp+5E0h+var_570]; void *
0x140088126  call    memset_0
0x14008812b  lea     r8, aExtentsForVolu; "Extents for volume %s not found. Ignori"...
0x140088132  jmp     loc_140088048
0x140088137  mov     rdx, rsi
0x14008813a  lea     rcx, [rsp+5E0h+var_5A8]
0x14008813f  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::CopyFrom(ushort const *)
0x140088144  or      rax, 0FFFFFFFFFFFFFFFFh
0x140088148  inc     rax
0x14008814b  cmp     [rsi+rax*2], r15w
0x140088150  jnz     short loc_140088148
0x140088152  cmp     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x140088158  jz      short loc_14008816B
0x14008815a  lea     rdx, pszSrc; "\\"
0x140088161  lea     rcx, [rsp+5E0h+var_5A8]
0x140088166  call    ?Append@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::Append(ushort const *)
0x14008816b  mov     ebx, 104h
0x140088170  mov     r8d, ebx; cchBufferLength
0x140088173  lea     rdx, [rbp+4E0h+szVolumeName]; lpszVolumeName
0x14008817a  mov     rcx, [rsp+5E0h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x14008817f  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140088185  test    eax, eax
0x140088187  jnz     loc_140088216
0x14008818d  call    cs:__imp_GetLastError
0x140088193  mov     ebx, eax
0x140088195  test    eax, eax
0x140088197  jle     short loc_1400881A2
0x140088199  movzx   ebx, ax
0x14008819c  or      ebx, 80070000h
0x1400881a2  lea     rax, aBaseStorVssMod_28; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400881a9  mov     [rsp+5E0h+var_598], rax
0x1400881ae  lea     rax, aCvsshardwarepr_173; "CVssHardwareProviderWrapper::CheckLunMa"...
0x1400881b5  mov     [rsp+5E0h+var_590], rax
0x1400881ba  lea     rax, aCorhrsnc; "CORHRSNC"
0x1400881c1  mov     [rsp+5E0h+var_588], rax
0x1400881c6  mov     [rsp+5E0h+var_580], 8D5h
0x1400881ce  mov     [rsp+5E0h+var_57C], 1
0x1400881d6  mov     [rsp+5E0h+var_578], 0FFh
0x1400881de  mov     [rbp+4E0h+var_4F8], 1000000h
0x1400881e5  xor     edx, edx; Val
0x1400881e7  lea     r8d, [rdx+78h]; Size
0x1400881eb  lea     rcx, [rsp+5E0h+var_570]; void *
0x1400881f0  call    memset_0
0x1400881f5  mov     r9, rsi
0x1400881f8  lea     r8, aGetvolumenamef_11; "GetVolumeNameForVolumeMountPoint(%s) fa"...
0x1400881ff  mov     [rsp+5E0h+var_5C0], ebx
0x140088203  lea     rdx, [rsp+5E0h+var_598]
0x140088208  lea     rcx, [rbp+4E0h+var_4F0]
0x14008820c  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140088211  jmp     loc_140088059
0x140088216  mov     r8d, ebx; cchBufferLength
0x140088219  lea     rdx, [rbp+4E0h+var_250]; lpszVolumeName
0x140088220  lea     rcx, [rbp+4E0h+szVolumeName]; lpszVolumeMountPoint
0x140088227  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14008822d  test    eax, eax
0x14008822f  jnz     short loc_1400882AC
0x140088231  call    cs:__imp_GetLastError
0x140088237  mov     ebx, eax
0x140088239  test    eax, eax
0x14008823b  jle     short loc_140088246
0x14008823d  movzx   ebx, ax
0x140088240  or      ebx, 80070000h
0x140088246  lea     rax, aBaseStorVssMod_28; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14008824d  mov     [rsp+5E0h+var_598], rax
0x140088252  lea     rax, aCvsshardwarepr_173; "CVssHardwareProviderWrapper::CheckLunMa"...
0x140088259  mov     [rsp+5E0h+var_590], rax
0x14008825e  lea     rax, aCorhrsnc; "CORHRSNC"
0x140088265  mov     [rsp+5E0h+var_588], rax
0x14008826a  mov     [rsp+5E0h+var_580], 8D9h
0x140088272  mov     [rsp+5E0h+var_57C], 1
0x14008827a  mov     [rsp+5E0h+var_578], 0FFh
0x140088282  mov     [rbp+4E0h+var_4F8], 1000000h
0x140088289  xor     edx, edx; Val
0x14008828b  lea     r8d, [rdx+78h]; Size
0x14008828f  lea     rcx, [rsp+5E0h+var_570]; void *
0x140088294  call    memset_0
0x140088299  lea     r9, [rbp+4E0h+szVolumeName]
0x1400882a0  lea     r8, aGetvolumenamef_2; "GetVolumeNameForVolumeMountPoint(%s) fa"...
0x1400882a7  jmp     loc_1400881FF
0x1400882ac  lea     rdx, [rbp+4E0h+var_250]; unsigned __int16 *
0x1400882b3  call    ?RemoveTrailingSlashFromPath@CVssHardwareProviderWrapper@@AEAAXPEAG@Z; CVssHardwareProviderWrapper::RemoveTrailingSlashFromPath(ushort *)
0x1400882b8  lea     rdx, [rbp+4E0h+var_250]
0x1400882bf  lea     rcx, [rsp+5E0h+var_5A8]
0x1400882c4  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoLocalPtr<ushort *>>::CopyFrom(ushort const *)
0x1400882c9  mov     rbx, [rsp+5E0h+lpszVolumeMountPoint]
0x1400882ce  mov     [rsp+5E0h+lpszVolumeMountPoint], r15
0x1400882d3  mov     [r14+30h], rbx
0x1400882d7  lea     rax, aBaseStorVssMod_28; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400882de  mov     [rsp+5E0h+var_598], rax
0x1400882e3  lea     rax, aCvsshardwarepr_173; "CVssHardwareProviderWrapper::CheckLunMa"...
0x1400882ea  mov     [rsp+5E0h+var_590], rax
0x1400882ef  lea     rax, aCorhrsnc; "CORHRSNC"
0x1400882f6  mov     [rsp+5E0h+var_588], rax
0x1400882fb  mov     [rsp+5E0h+var_580], 8E5h
0x140088303  mov     [rsp+5E0h+var_57C], 1
0x14008830b  mov     [rsp+5E0h+var_578], 0FFh
0x140088313  mov     [rbp+4E0h+var_4F8], 1000000h
0x14008831a  xor     edx, edx; Val
0x14008831c  lea     r8d, [rdx+78h]; Size
0x140088320  lea     rcx, [rsp+5E0h+var_570]; void *
0x140088325  call    memset_0
0x14008832a  mov     r9, rbx
0x14008832d  lea     r8, aFoundVolumeNam_0; "Found volume name %s for arrived volume"
0x140088334  lea     rdx, [rsp+5E0h+var_598]
0x140088339  lea     rcx, [rbp+4E0h+var_4F0]
0x14008833d  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140088342  mov     dl, 1; bool
0x140088344  lea     rcx, [rbp+4E0h+var_4F0]; this
0x140088348  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x14008834d  mov     bl, al
0x14008834f  lea     rcx, [rsp+5E0h+var_5A8]
0x140088354  call    ??1?$CVssAutoLocalPtr@PEAX@@UEAA@XZ; CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(void)
0x140088359  nop
0x14008835a  lea     rcx, [rbp+4E0h+var_4F0]; this
0x14008835e  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140088363  mov     al, bl
0x140088365  mov     rcx, [rbp+4E0h+var_40]
0x14008836c  xor     rcx, rsp; StackCookie
0x14008836f  call    __security_check_cookie
0x140088374  mov     rbx, [rsp+5E0h+arg_0]
0x14008837c  add     rsp, 5B0h
0x140088383  pop     r15
0x140088385  pop     r14
0x140088387  pop     r13
0x140088389  pop     r12
0x14008838b  pop     rdi
0x14008838c  pop     rsi
0x14008838d  pop     rbp
0x14008838e  retn
```
