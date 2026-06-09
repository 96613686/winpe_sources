# VolumeTrackerVolume::GetPartitionInformation(void)

- ea: `0x180075240`
- end: `0x18007560a`
- name: `?GetPartitionInformation@VolumeTrackerVolume@@AEAAJXZ`
- size: `970`
- prototype: `__int64 __fastcall(VolumeTrackerVolume *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800756d0`

## callees

- `0x18000d400`
- `0x18000d5a4`
- `0x180012c9c`
- `0x180019210`
- `0x180072288`
- `0x180072688`
- `0x180072720`
- `0x180073034`
- `0x18007318c`
- `0x1800732e0`
- `0x18007342c`
- `0x180074bd4`
- `0x180074cd4`
- `0x180074d94`
- `0x180074e6c`
- `0x180075240`
- `0x180076bcc`
- `0x180076f58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007559a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007559a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007532f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007532f`

## string_xrefs

- `0x1800755c0`: `CreateFile`
- `0x1800754f5`: `StringCchCopy`
- `0x1800752a5`: `disk path buffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VolumeTrackerVolume::GetPartitionInformation(VolumeTrackerVolume *this)
{
  wchar_t *v2; // rax
  __int64 v3; // rcx
  signed int DiskLayoutInternal; // edi
  int v5; // eax
  int v6; // edx
  int v7; // ecx
  HANDLE FileW; // rax
  unsigned int *v9; // r8
  HANDLE v10; // rbx
  unsigned int *v11; // r8
  struct _DISK_GEOMETRY_EX *v12; // r14
  __int64 i; // rcx
  __int64 v14; // r15
  _OWORD *v15; // rcx
  int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  int v18; // eax
  DWORD LowPart; // eax
  wchar_t *v20; // rax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // edx
  int v24; // ecx
  wchar_t *v25; // rax
  unsigned int v26; // r9d
  signed int LastError; // eax
  int v28; // edx
  int v29; // ecx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  struct _DISK_GEOMETRY_EX *v33; // [rsp+70h] [rbp+30h] BYREF
  struct _DISK_GEOMETRY_EX *v34; // [rsp+78h] [rbp+38h] BYREF
  HANDLE hDevice; // [rsp+80h] [rbp+40h] BYREF

  v33 = 0;
  v34 = 0;
  hDevice = 0;
  if ( !*((_QWORD *)this + 9) )
  {
    v2 = (wchar_t *)operator new[](0x208u, (const struct std::nothrow_t *)std::nothrow);
    *((_QWORD *)this + 9) = v2;
    if ( !v2 )
    {
      DiskLayoutInternal = -2147024882;
      if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 1) != 0 )
        McTemplateU0zz_EventWriteTransfer(
          v3,
          AllocationFailure,
          L"VolumeTrackerVolume::GetPartitionInformation",
          L"disk path buffer");
      goto LABEL_53;
    }
    v5 = StringCchPrintfW(v2, 0x104u, L"\\\\.\\PhysicalDrive%d", *((unsigned int *)this + 28));
    DiskLayoutInternal = v5;
    if ( v5 < 0 )
    {
      if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
        McTemplateU0zzzq_EventWriteTransfer(
          v7,
          v6,
          (unsigned int)L"VolumeTrackerVolume::GetPartitionInformation",
          (unsigned int)L"StringCchPrintf",
          (__int64)L"\\\\.\\PhysicalDrive",
          v5);
      goto LABEL_53;
    }
  }
  FileW = CreateFileW(*((LPCWSTR *)this + 9), 0x80000000, 7u, 0, 3u, 0x80u, 0);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &hDevice,
    FileW);
  v10 = hDevice;
  if ( (char *)hDevice - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    DiskLayoutInternal = LastError;
    if ( LastError > 0 )
      DiskLayoutInternal = (unsigned __int16)LastError | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
      McTemplateU0zzzq_EventWriteTransfer(
        v29,
        v28,
        (unsigned int)L"VolumeTrackerVolume::GetPartitionInformation",
        (unsigned int)L"CreateFile",
        *((_QWORD *)this + 9),
        DiskLayoutInternal);
  }
  else
  {
    DiskLayoutInternal = GetDiskLayoutInternal(hDevice, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&v33, v9);
    if ( DiskLayoutInternal < 0 )
      goto LABEL_53;
    DiskLayoutInternal = GetDiskNumber(v10, (unsigned int *)this + 28);
    if ( DiskLayoutInternal < 0 )
      goto LABEL_53;
    v12 = v33;
    *((_DWORD *)this + 6) = v33->Geometry.Cylinders.LowPart;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v12->Geometry.Cylinders.HighPart )
        goto LABEL_46;
      v14 = 144 * i;
      if ( *((_QWORD *)&v12[1].Geometry.SectorsPerTrack + 18 * i) == *((_QWORD *)this + 15) )
        break;
    }
    if ( v12->Geometry.Cylinders.LowPart >= 2 )
    {
LABEL_16:
      DiskLayoutInternal = -2147024846;
      if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(i, InvalidPartitionStyle, L"VolumeTrackerVolume::GetPartitionInformation");
      goto LABEL_53;
    }
    *((_DWORD *)this + 29) = *(_DWORD *)&v12[1].Data[v14];
    v15 = (_OWORD *)((char *)this + 44);
    if ( this != (VolumeTrackerVolume *)-44LL )
    {
      v16 = *(MEDIA_TYPE *)((char *)&v12[1].Geometry.MediaType + v14);
      if ( v16 )
      {
        if ( v16 == 1 )
          *v15 = *(_OWORD *)((char *)&v12[2].Geometry.Cylinders.LowPart + v14);
      }
      else
      {
        *(_BYTE *)v15 = *((_BYTE *)&v12[2].Geometry.Cylinders.LowPart + v14);
      }
    }
    v17 = (VolumeTrackerVolume *)((char *)this + 64);
    if ( this != (VolumeTrackerVolume *)-64LL )
    {
      v18 = *(MEDIA_TYPE *)((char *)&v12[1].Geometry.MediaType + v14);
      if ( v18 )
      {
        if ( v18 == 1 )
          *(_QWORD *)v17 = *(_QWORD *)&v12[2].Data[v14];
      }
      else
      {
        *(_BYTE *)v17 = *((_BYTE *)&v12[2].Geometry.Cylinders.LowPart + v14 + 1) != 0 ? 0x80 : 0;
      }
    }
    LowPart = v12->Geometry.Cylinders.LowPart;
    *((_DWORD *)this + 6) = v12->Geometry.Cylinders.LowPart;
    if ( LowPart )
    {
      if ( LowPart == 1 )
        *(_OWORD *)((char *)this + 28) = *(_OWORD *)&v12->Geometry.MediaType;
      else
        wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x7A,
          (unsigned int)"onecore\\base\\wcp\\storage\\storagehelper\\diskfunctions.cpp",
          (const char *)0x571,
          dwCreationDisposition);
    }
    else
    {
      *((_DWORD *)this + 7) = v12->Geometry.MediaType;
    }
    i = *((unsigned int *)this + 6);
    if ( (_DWORD)i )
    {
      if ( (_DWORD)i != 1 )
        goto LABEL_16;
      *((_OWORD *)this + 6) = *(_OWORD *)((char *)&v12[2].Geometry.SectorsPerTrack + v14);
      operator delete(*((void **)this + 11), v17);
      *((_QWORD *)this + 11) = 0;
      v20 = (wchar_t *)operator new[](0x48u, (const struct std::nothrow_t *)std::nothrow);
      *((_QWORD *)this + 11) = v20;
      if ( v20 )
      {
        v22 = StringCchCopyW(v20, 0x24u, (const wchar_t *)((char *)&v12[3] + v14));
        DiskLayoutInternal = v22;
        if ( v22 < 0 && (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
          McTemplateU0zzq_EventWriteTransfer(
            v24,
            v23,
            (unsigned int)L"VolumeTrackerVolume::GetPartitionInformation",
            (unsigned int)L"StringCchCopy",
            v22);
        goto LABEL_46;
      }
    }
    else
    {
      if ( *((_QWORD *)this + 11) || !ValidMbrMetadataPartitionExists(v10, (__int64)v17, v11) )
      {
LABEL_46:
        if ( !*((_DWORD *)this + 20) )
        {
          DiskLayoutInternal = GetDiskGeometry(v10, &v34, v11);
          if ( DiskLayoutInternal >= 0 )
            *((_DWORD *)this + 20) = v34->Geometry.BytesPerSector;
        }
        goto LABEL_53;
      }
      v25 = (wchar_t *)operator new[](0x48u, (const struct std::nothrow_t *)std::nothrow);
      *((_QWORD *)this + 11) = v25;
      if ( v25 )
      {
        DiskLayoutInternal = MbrMetaGetPartitionName(v10, *((_QWORD *)this + 15), v25, v26);
        if ( DiskLayoutInternal < 0 )
          goto LABEL_53;
        goto LABEL_46;
      }
    }
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 1) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v21,
        AllocationFailure,
        L"VolumeTrackerVolume::GetPartitionInformation",
        L"_strPartitionName");
    DiskLayoutInternal = -2147024882;
  }
LABEL_53:
  SafeFreeDiskGeometry(&v33);
  SafeFreeDiskGeometry(&v34);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hDevice);
  return (unsigned int)DiskLayoutInternal;
}

```

## disassembly

```asm
0x180075240  mov     [rsp-28h+arg_18], rbx
0x180075245  push    rbp
0x180075246  push    rsi
0x180075247  push    rdi
0x180075248  push    r14
0x18007524a  push    r15
0x18007524c  mov     rbp, rsp
0x18007524f  sub     rsp, 40h
0x180075253  mov     rsi, rcx
0x180075256  mov     [rbp+arg_0], 0
0x18007525e  mov     [rbp+arg_8], 0
0x180075266  mov     [rbp+hDevice], 0
0x18007526e  cmp     qword ptr [rcx+48h], 0
0x180075273  jnz     loc_180075306
0x180075279  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180075280  mov     ecx, 208h; unsigned __int64
0x180075285  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007528a  mov     [rsi+48h], rax
0x18007528e  test    rax, rax
0x180075291  jnz     short loc_1800752C4
0x180075293  mov     edi, 8007000Eh
0x180075298  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 1
0x18007529f  jz      loc_1800755D8
0x1800752a5  lea     r9, aDiskPathBuffer; "disk path buffer"
0x1800752ac  lea     r8, aVolumetrackerv_1; "VolumeTrackerVolume::GetPartitionInform"...
0x1800752b3  lea     rdx, AllocationFailure
0x1800752ba  call    McTemplateU0zz_EventWriteTransfer
0x1800752bf  jmp     loc_1800755D8
0x1800752c4  mov     r9d, [rsi+70h]
0x1800752c8  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x1800752cf  mov     edx, 104h; unsigned __int64
0x1800752d4  mov     rcx, rax; wchar_t *
0x1800752d7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800752dc  mov     edi, eax
0x1800752de  test    eax, eax
0x1800752e0  jns     short loc_180075306
0x1800752e2  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x1800752e9  jz      loc_1800755D8
0x1800752ef  mov     [rsp+40h+dwFlagsAndAttributes], eax
0x1800752f3  lea     rax, aPhysicaldrive; "\\\\.\\PhysicalDrive"
0x1800752fa  lea     r9, aStringcchprint; "StringCchPrintf"
0x180075301  jmp     loc_1800755C7
0x180075306  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x18007530f  mov     [rsp+40h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180075317  mov     [rsp+40h+dwCreationDisposition], 3; unsigned int
0x18007531f  xor     r9d, r9d; lpSecurityAttributes
0x180075322  mov     edx, 80000000h; dwDesiredAccess
0x180075327  lea     r8d, [r9+7]; dwShareMode
0x18007532b  mov     rcx, [rsi+48h]; lpFileName
0x18007532f  call    cs:__imp_CreateFileW
0x180075335  mov     rdx, rax
0x180075338  lea     rcx, [rbp+hDevice]
0x18007533c  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x180075341  mov     rbx, [rbp+hDevice]
0x180075345  lea     rax, [rbx-1]
0x180075349  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007534d  ja      loc_18007559A
0x180075353  lea     rdx, [rbp+arg_0]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x180075357  mov     rcx, rbx; hDevice
0x18007535a  call    ?GetDiskLayoutInternal@@YAJQEAXPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAK@Z; GetDiskLayoutInternal(void * const,_DRIVE_LAYOUT_INFORMATION_EX * *,ulong *)
0x18007535f  mov     edi, eax
0x180075361  test    eax, eax
0x180075363  js      loc_1800755D8
0x180075369  lea     rdx, [rsi+70h]; unsigned int *
0x18007536d  mov     rcx, rbx; void *
0x180075370  call    ?GetDiskNumber@@YAJQEAXPEAK@Z; GetDiskNumber(void * const,ulong *)
0x180075375  mov     edi, eax
0x180075377  test    eax, eax
0x180075379  js      loc_1800755D8
0x18007537f  mov     r14, [rbp+arg_0]
0x180075383  mov     eax, [r14]
0x180075386  mov     [rsi+18h], eax
0x180075389  xor     ecx, ecx
0x18007538b  cmp     ecx, [r14+4]
0x18007538f  jnb     loc_180075576
0x180075395  lea     r15, [rcx+rcx*8]
0x180075399  shl     r15, 4
0x18007539d  mov     rax, [rsi+78h]
0x1800753a1  cmp     [r15+r14+38h], rax
0x1800753a6  jz      short loc_1800753AC
0x1800753a8  inc     ecx
0x1800753aa  jmp     short loc_18007538B
0x1800753ac  cmp     dword ptr [r14], 2
0x1800753b0  jb      short loc_1800753DC
0x1800753b2  mov     edi, 80070032h
0x1800753b7  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x1800753be  jz      loc_1800755D8
0x1800753c4  lea     r8, aVolumetrackerv_1; "VolumeTrackerVolume::GetPartitionInform"...
0x1800753cb  lea     rdx, InvalidPartitionStyle
0x1800753d2  call    McTemplateU0z_EventWriteTransfer
0x1800753d7  jmp     loc_1800755D8
0x1800753dc  mov     eax, [r15+r14+48h]
0x1800753e1  mov     [rsi+74h], eax
0x1800753e4  lea     rcx, [rsi+2Ch]
0x1800753e8  test    rcx, rcx
0x1800753eb  jz      short loc_18007540E
0x1800753ed  mov     eax, [r15+r14+30h]
0x1800753f2  test    eax, eax
0x1800753f4  jnz     short loc_1800753FF
0x1800753f6  mov     al, [r15+r14+50h]
0x1800753fb  mov     [rcx], al
0x1800753fd  jmp     short loc_18007540E
0x1800753ff  cmp     eax, 1
0x180075402  jnz     short loc_18007540E
0x180075404  movups  xmm0, xmmword ptr [r15+r14+50h]
0x18007540a  movdqu  xmmword ptr [rcx], xmm0
0x18007540e  lea     rdx, [rsi+40h]; struct std::nothrow_t *
0x180075412  test    rdx, rdx
0x180075415  jz      short loc_18007543D
0x180075417  mov     eax, [r15+r14+30h]
0x18007541c  test    eax, eax
0x18007541e  jnz     short loc_180075430
0x180075420  mov     al, [r15+r14+51h]
0x180075425  neg     al
0x180075427  sbb     cl, cl
0x180075429  and     cl, 80h
0x18007542c  mov     [rdx], cl
0x18007542e  jmp     short loc_18007543D
0x180075430  cmp     eax, 1
0x180075433  jnz     short loc_18007543D
0x180075435  mov     rax, [r15+r14+70h]
0x18007543a  mov     [rdx], rax
0x18007543d  mov     eax, [r14]
0x180075440  mov     [rsi+18h], eax
0x180075443  test    eax, eax
0x180075445  jz      short loc_180075475
0x180075447  cmp     eax, 1
0x18007544a  jz      short loc_180075469
0x18007544c  mov     rcx, [rbp+28h]; this
0x180075450  mov     r9d, 571h; char *
0x180075456  lea     r8, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\storage\\storagehel"...
0x18007545d  mov     edx, 7Ah ; 'z'; void *
0x180075462  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180075467  jmp     short loc_18007547C
0x180075469  movups  xmm0, xmmword ptr [r14+8]
0x18007546e  movdqu  xmmword ptr [rsi+1Ch], xmm0
0x180075473  jmp     short loc_18007547C
0x180075475  mov     eax, [r14+8]
0x180075479  mov     [rsi+1Ch], eax
0x18007547c  mov     ecx, [rsi+18h]
0x18007547f  test    ecx, ecx
0x180075481  jz      loc_18007550A
0x180075487  cmp     ecx, 1
0x18007548a  jnz     loc_1800753B2
0x180075490  movups  xmm0, xmmword ptr [r15+r14+60h]
0x180075496  movdqu  xmmword ptr [rsi+60h], xmm0
0x18007549b  mov     rcx, [rsi+58h]; void *
0x18007549f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800754a4  mov     qword ptr [rsi+58h], 0
0x1800754ac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800754b3  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800754b8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800754bd  mov     [rsi+58h], rax
0x1800754c1  test    rax, rax
0x1800754c4  jz      short loc_180075537
0x1800754c6  lea     r8, [r14+78h]
0x1800754ca  add     r8, r15; wchar_t *
0x1800754cd  mov     edx, 24h ; '$'; unsigned __int64
0x1800754d2  mov     rcx, rax; wchar_t *
0x1800754d5  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800754da  mov     edi, eax
0x1800754dc  test    eax, eax
0x1800754de  jns     loc_180075576
0x1800754e4  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x1800754eb  jz      loc_180075576
0x1800754f1  mov     [rsp+40h+dwCreationDisposition], eax
0x1800754f5  lea     r9, aStringcchcopy; "StringCchCopy"
0x1800754fc  lea     r8, aVolumetrackerv_1; "VolumeTrackerVolume::GetPartitionInform"...
0x180075503  call    McTemplateU0zzq_EventWriteTransfer
0x180075508  jmp     short loc_180075576
0x18007550a  cmp     qword ptr [rsi+58h], 0
0x18007550f  jnz     short loc_180075576
0x180075511  mov     rcx, rbx; hDevice
0x180075514  call    ?ValidMbrMetadataPartitionExists@@YA_NQEAX@Z; ValidMbrMetadataPartitionExists(void * const)
0x180075519  test    al, al
0x18007551b  jz      short loc_180075576
0x18007551d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180075524  mov     ecx, 48h ; 'H'; unsigned __int64
0x180075529  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007552e  mov     [rsi+58h], rax
0x180075532  test    rax, rax
0x180075535  jnz     short loc_180075561
0x180075537  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 1
0x18007553e  jz      short loc_18007555A
0x180075540  lea     r9, aStrpartitionna_0; "_strPartitionName"
0x180075547  lea     r8, aVolumetrackerv_1; "VolumeTrackerVolume::GetPartitionInform"...
0x18007554e  lea     rdx, AllocationFailure
0x180075555  call    McTemplateU0zz_EventWriteTransfer
0x18007555a  mov     edi, 8007000Eh
0x18007555f  jmp     short loc_1800755D8
0x180075561  mov     r8, rax; wchar_t *
0x180075564  mov     rdx, [rsi+78h]; unsigned __int64
0x180075568  mov     rcx, rbx; void *
0x18007556b  call    ?MbrMetaGetPartitionName@@YAJQEAX_KPEA_WK@Z; MbrMetaGetPartitionName(void * const,unsigned __int64,wchar_t *,ulong)
0x180075570  mov     edi, eax
0x180075572  test    eax, eax
0x180075574  js      short loc_1800755D8
0x180075576  cmp     dword ptr [rsi+50h], 0
0x18007557a  jnz     short loc_1800755D8
0x18007557c  lea     rdx, [rbp+arg_8]; struct _DISK_GEOMETRY_EX **
0x180075580  mov     rcx, rbx; hDevice
0x180075583  call    ?GetDiskGeometry@@YAJQEAXPEAPEAU_DISK_GEOMETRY_EX@@PEAK@Z; GetDiskGeometry(void * const,_DISK_GEOMETRY_EX * *,ulong *)
0x180075588  mov     edi, eax
0x18007558a  test    eax, eax
0x18007558c  js      short loc_1800755D8
0x18007558e  mov     rax, [rbp+arg_8]
0x180075592  mov     ecx, [rax+14h]
0x180075595  mov     [rsi+50h], ecx
0x180075598  jmp     short loc_1800755D8
0x18007559a  call    cs:__imp_GetLastError
0x1800755a0  mov     edi, eax
0x1800755a2  test    eax, eax
0x1800755a4  jle     short loc_1800755AF
0x1800755a6  movzx   edi, ax
0x1800755a9  or      edi, 80070000h
0x1800755af  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x1800755b6  jz      short loc_1800755D8
0x1800755b8  mov     [rsp+40h+dwFlagsAndAttributes], edi
0x1800755bc  mov     rax, [rsi+48h]
0x1800755c0  lea     r9, aCreatefile; "CreateFile"
0x1800755c7  mov     qword ptr [rsp+40h+dwCreationDisposition], rax
0x1800755cc  lea     r8, aVolumetrackerv_1; "VolumeTrackerVolume::GetPartitionInform"...
0x1800755d3  call    McTemplateU0zzzq_EventWriteTransfer
0x1800755d8  lea     rcx, [rbp+arg_0]; struct _DISK_GEOMETRY_EX **
0x1800755dc  call    ?SafeFreeDiskGeometry@@YAXPEAPEAU_DISK_GEOMETRY_EX@@@Z; SafeFreeDiskGeometry(_DISK_GEOMETRY_EX * *)
0x1800755e1  lea     rcx, [rbp+arg_8]; struct _DISK_GEOMETRY_EX **
0x1800755e5  call    ?SafeFreeDiskGeometry@@YAXPEAPEAU_DISK_GEOMETRY_EX@@@Z; SafeFreeDiskGeometry(_DISK_GEOMETRY_EX * *)
0x1800755ea  nop
0x1800755eb  lea     rcx, [rbp+hDevice]
0x1800755ef  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800755f4  mov     eax, edi
0x1800755f6  mov     rbx, [rsp+40h+arg_18]
0x1800755fe  add     rsp, 40h
0x180075602  pop     r15
0x180075604  pop     r14
0x180075606  pop     rdi
0x180075607  pop     rsi
0x180075608  pop     rbp
0x180075609  retn
```
