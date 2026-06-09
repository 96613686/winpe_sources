# DiskMountOperation::RunTaskInternal(void)

- ea: `0x14014ac10`
- end: `0x14014b1a5`
- name: `?RunTaskInternal@DiskMountOperation@@UEAAJXZ`
- size: `1429`
- prototype: `__int64 __fastcall(DiskMountOperation *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x14001a000`
- `0x14001ded4`
- `0x140034404`
- `0x14005c630`
- `0x140071534`
- `0x140149058`
- `0x14014ac10`
- `0x14014b1ac`
- `0x140159cac`
- `0x14017a4fc`
- `0x1401be65c`
- `0x1401befac`
- `0x1404828e0`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14014afb7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14014afb7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14014ae32`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14014ae32`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x14014ae77`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x14014ae77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14014ad83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14014ad83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14014afcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14014afe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14014afcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14014afe1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14014aeb0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14014aeb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14014af9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14014af9e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14014ad73`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14014ad73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14014af02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14014af02`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14014af4c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14014af4c`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x14014ae5d`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x14014ae98`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x14014ae5d`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x14014ae98`
- `VirtDisk!AttachVirtualDisk` at `0x14014adfa`
- `VirtDisk!AttachVirtualDisk` at `0x14014adfa`
- `VirtDisk!OpenVirtualDisk` at `0x14014ad15`
- `VirtDisk!OpenVirtualDisk` at `0x14014ad15`

## string_xrefs

- `0x14014b14b`: `%hs unable to add the affected Msvm_MountedStorageImage to the mount task. HRESULT = 0x%081X\n`
- `0x14014b144`: `DiskMountOperation::RunTaskInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DiskMountOperation::RunTaskInternal(DiskMountOperation *this)
{
  __int64 FileW; // r14
  WCHAR *v3; // rsi
  const unsigned __int16 *v4; // rdi
  const unsigned __int16 *v5; // rcx
  const WCHAR *v6; // rdx
  signed int LastError; // eax
  signed int VirtualDiskPhysicalPath; // ebx
  bool v9; // cc
  int v10; // r8d
  WCHAR *v11; // rax
  __int64 v12; // rax
  int v13; // edi
  const struct Vml::ExceptionTraceParameters *v14; // r8
  signed int v16; // [rsp+40h] [rbp-118h]
  __int64 v17; // [rsp+48h] [rbp-110h] BYREF
  __int64 *p_OutBuffer; // [rsp+50h] [rbp-108h] BYREF
  __int64 v19; // [rsp+58h] [rbp-100h] BYREF
  size_t Size; // [rsp+60h] [rbp-F8h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+68h] [rbp-F0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-E8h] BYREF
  DWORD BytesReturned; // [rsp+78h] [rbp-E0h] BYREF
  __int64 OutBuffer; // [rsp+80h] [rbp-D8h] BYREF
  _ATTACH_VIRTUAL_DISK_PARAMETERS v25[2]; // [rsp+88h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+98h] [rbp-C0h]
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+A0h] [rbp-B8h] BYREF
  struct _OPEN_VIRTUAL_DISK_PARAMETERS Parameters; // [rsp+B8h] [rbp-A0h] BYREF
  __int64 v29[4]; // [rsp+E8h] [rbp-70h] BYREF
  __int64 v30[4]; // [rsp+108h] [rbp-50h] BYREF

  *(_OWORD *)&v25[0].Version = 0;
  v26 = 0;
  SecurityDescriptor = 0;
  VirtualStorageType.DeviceId = 0;
  VirtualDiskHandle = (HANDLE)-1LL;
  FileW = -1;
  v3 = 0;
  LODWORD(Size) = 50;
  BytesReturned = 0;
  v19 = 0;
  memset(&Parameters, 0, sizeof(Parameters));
  OutBuffer = 0;
  VirtualStorageType.VendorId = VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT;
  v4 = (const unsigned __int16 *)((char *)this + 168);
  if ( *((_QWORD *)this + 24) <= 7u )
    v5 = (const unsigned __int16 *)((char *)this + 168);
  else
    v5 = *(const unsigned __int16 **)v4;
  VirtualStorageType.DeviceId = GetVhdDeviceIDFromExtension(v5);
  *(_QWORD *)&Parameters.Version = 2;
  if ( *((_QWORD *)v4 + 3) <= 7u )
    v6 = v4;
  else
    v6 = *(const WCHAR **)v4;
  LastError = OpenVirtualDisk(
                &VirtualStorageType,
                v6,
                VIRTUAL_DISK_ACCESS_NONE,
                OPEN_VIRTUAL_DISK_FLAG_NONE,
                &Parameters,
                &VirtualDiskHandle);
  VirtualDiskPhysicalPath = LastError;
  v9 = LastError <= 0;
  if ( LastError )
  {
    VirtualDiskHandle = (HANDLE)-1LL;
    goto LABEL_9;
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 80LL))(*((_QWORD *)this + 18), 30) < 0 )
  {
LABEL_12:
    VirtualDiskPhysicalPath = -2147213311;
    goto LABEL_35;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;GA;;;WD)(A;;GA;;;AC)",
          1u,
          &SecurityDescriptor,
          0) )
    goto LABEL_14;
  *(_OWORD *)&v25[0].Version = 0;
  v26 = 0;
  v25[0].Version = ATTACH_VIRTUAL_DISK_VERSION_1;
  v10 = (*((_DWORD *)this + 50) == 0 ? 2 : 0) | 1;
  if ( !*((_DWORD *)this + 51) )
    v10 = *((_DWORD *)this + 50) == 0 ? 2 : 0;
  LastError = AttachVirtualDisk(VirtualDiskHandle, SecurityDescriptor, (ATTACH_VIRTUAL_DISK_FLAG)(v10 | 4), 0, v25, 0);
  VirtualDiskPhysicalPath = LastError;
  v9 = LastError <= 0;
  if ( LastError )
  {
LABEL_9:
    if ( !v9 )
    {
      VirtualDiskPhysicalPath = (unsigned __int16)LastError;
LABEL_34:
      VirtualDiskPhysicalPath |= 0x80070000;
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 80LL))(*((_QWORD *)this + 18), 50) < 0 )
    goto LABEL_12;
  v3 = (WCHAR *)malloc((unsigned int)Size);
  if ( !v3 )
  {
LABEL_20:
    VirtualDiskPhysicalPath = -2147024882;
    goto LABEL_35;
  }
  while ( 1 )
  {
    VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, (PULONG)&Size, v3);
    if ( VirtualDiskPhysicalPath == 122 )
    {
      v11 = (WCHAR *)_o_realloc(v3, (unsigned int)Size);
      if ( !v11 )
        goto LABEL_20;
      v3 = v11;
      VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, (PULONG)&Size, v11);
    }
    if ( VirtualDiskPhysicalPath != 55 )
      break;
    Sleep(0x3E8u);
  }
  if ( !VirtualDiskPhysicalPath )
  {
    if ( (*(int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 80LL))(*((_QWORD *)this + 18), 80) < 0 )
      goto LABEL_12;
    FileW = (__int64)CreateFileW(v3, 0, 3u, 0, 3u, 0x100080u, 0);
    if ( FileW != -1 && DeviceIoControl((HANDLE)FileW, 0x41018u, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
    {
      VirtualDiskPhysicalPath = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 80LL))(
                                  *((_QWORD *)this + 18),
                                  100);
      v16 = VirtualDiskPhysicalPath;
      if ( VirtualDiskPhysicalPath >= 0 )
        goto LABEL_36;
      goto LABEL_12;
    }
LABEL_14:
    LastError = GetLastError();
    VirtualDiskPhysicalPath = LastError;
    v9 = LastError <= 0;
    goto LABEL_9;
  }
  if ( VirtualDiskPhysicalPath > 0 )
  {
    VirtualDiskPhysicalPath = (unsigned __int16)VirtualDiskPhysicalPath;
    goto LABEL_34;
  }
LABEL_35:
  v16 = VirtualDiskPhysicalPath;
LABEL_36:
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( v3 )
    free(v3);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( VirtualDiskHandle != (HANDLE)-1LL )
  {
    CloseHandle(VirtualDiskHandle);
    VirtualDiskHandle = (HANDLE)-1LL;
  }
  if ( VirtualDiskPhysicalPath >= 0 )
  {
    VmEventWrite<unsigned short const *>(&MSVHDSVC_MOUNT_COMPLETED, 1u);
    v17 = 0;
    try
    {
      p_OutBuffer = &OutBuffer;
      v12 = Vml::VmComMultiInstanceObject<WmiMsvmMountedStorageImage>::CreateInstance<_SCSI_ADDRESS *,std::wstring &,unsigned short const (&)[1]>(
              &p_OutBuffer,
              v4);
      Vml::VmComPtr<IVmWmiObject>::Attach<WmiMsvmVirtualSystemReferencePointService>(&v17, v12);
      v13 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 320LL))(*((_QWORD *)this + 18), v17);
      if ( v13 < 0 && (unsigned int)VmlIsDebugTraceEnabled(32865) )
        VmlDebugTrace(
          32865,
          L"%hs unable to add the affected Msvm_MountedStorageImage to the mount task. HRESULT = 0x%081X\n",
          "DiskMountOperation::RunTaskInternal",
          (unsigned int)v13);
    }
    catch ( ... )
    {
      Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x8061, (unsigned __int16)&off_140922008, v14);
      VirtualDiskPhysicalPath = v16;
    }
    Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v17);
  }
  else
  {
    _snwprintf_s<16>(v30, 16, L"%%%%%u", VirtualDiskPhysicalPath & 0xEFFFFFFF);
    _snwprintf_s<16>(v29, 16, L"0x%08X", VirtualDiskPhysicalPath & 0xEFFFFFFF);
    if ( VirtualDiskPhysicalPath == -2147213311 )
    {
      if ( *((_QWORD *)v4 + 3) > 7u )
        v4 = *(const unsigned __int16 **)v4;
      v17 = (__int64)v4;
      VmEventWriteAndReport<unsigned short const * &>(
        (struct _EVENT_DESCRIPTOR *)&MSVHDSVC_MOUNT_CANCELED,
        5u,
        (__int64)&v17);
    }
    else
    {
      if ( *((_QWORD *)v4 + 3) > 7u )
        v4 = *(const unsigned __int16 **)v4;
      v17 = (__int64)v4;
      VmEventWriteAndReport<unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
        (struct _EVENT_DESCRIPTOR *)&MSVHDSVC_MOUNT_FAILURE,
        5u,
        (__int64)&v17,
        (__int64)v30,
        (__int64)v29);
    }
  }
  Vml::VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>::~VmReferencePtr<Vml::VmMethodDelegate<VmmsRealizedVirtualMachine,void,IVmTask *,_REFERENCE_POINT_CREATE_PARAMS const &>,Vml::VmUserReferenceTraits>(&v19);
  return (unsigned int)VirtualDiskPhysicalPath;
}

```

## disassembly

```asm
0x14014ac10  mov     r11, rsp
0x14014ac13  mov     [r11+10h], rbx
0x14014ac17  mov     [r11+18h], rsi
0x14014ac1b  push    rdi
0x14014ac1c  push    r12
0x14014ac1e  push    r13
0x14014ac20  push    r14
0x14014ac22  push    r15
0x14014ac24  sub     rsp, 130h
0x14014ac2b  mov     rax, cs:__security_cookie
0x14014ac32  xor     rax, rsp
0x14014ac35  mov     [rsp+158h+var_30], rax
0x14014ac3d  mov     r15, rcx
0x14014ac40  xorps   xmm0, xmm0
0x14014ac43  xor     eax, eax
0x14014ac45  movups  xmmword ptr [rsp+158h+var_D0.Version], xmm0
0x14014ac4d  mov     [r11-0C0h], rax
0x14014ac54  xor     r12d, r12d
0x14014ac57  mov     [rsp+158h+SecurityDescriptor], r12
0x14014ac5c  mov     [r11-0B8h], r12d
0x14014ac63  or      r13, 0FFFFFFFFFFFFFFFFh
0x14014ac67  mov     [rsp+158h+VirtualDiskHandle], r13
0x14014ac6c  mov     r14, r13
0x14014ac6f  mov     esi, r12d
0x14014ac72  mov     dword ptr [rsp+158h+Size], 32h ; '2'
0x14014ac7a  mov     [rsp+158h+BytesReturned], r12d
0x14014ac7f  mov     [rsp+158h+var_100], r12
0x14014ac84  movups  xmmword ptr [rsp+158h+var_A0.Version], xmm0
0x14014ac8c  movups  xmmword ptr [rsp+158h+var_A0.4+0Ch], xmm0
0x14014ac94  movups  xmmword ptr [rsp+158h+var_A0.4+18h], xmm0
0x14014ac9c  mov     [r11-0D8h], r12
0x14014aca3  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x14014acaa  movdqu  xmmword ptr [rsp+158h+VirtualStorageType.VendorId.Data1], xmm0
0x14014acb3  lea     rdi, [rcx+0A8h]
0x14014acba  cmp     qword ptr [rdi+18h], 7
0x14014acbf  jbe     short loc_14014ACC6
0x14014acc1  mov     rcx, [rdi]
0x14014acc4  jmp     short loc_14014ACC9
0x14014acc6  mov     rcx, rdi; unsigned __int16 *
0x14014acc9  call    ?GetVhdDeviceIDFromExtension@@YAKPEBG@Z; GetVhdDeviceIDFromExtension(ushort const *)
0x14014acce  mov     [rsp+158h+VirtualStorageType.DeviceId], eax
0x14014acd5  mov     qword ptr [rsp+158h+var_A0.Version], 2
0x14014ace1  cmp     qword ptr [rdi+18h], 7
0x14014ace6  jbe     short loc_14014ACED
0x14014ace8  mov     rdx, [rdi]
0x14014aceb  jmp     short loc_14014ACF0
0x14014aced  mov     rdx, rdi; Path
0x14014acf0  lea     rax, [rsp+158h+VirtualDiskHandle]
0x14014acf5  mov     [rsp+158h+Handle], rax; Handle
0x14014acfa  lea     rax, [rsp+158h+var_A0]
0x14014ad02  mov     [rsp+158h+Parameters], rax; Parameters
0x14014ad07  xor     r9d, r9d; Flags
0x14014ad0a  xor     r8d, r8d; VirtualDiskAccessMask
0x14014ad0d  lea     rcx, [rsp+158h+VirtualStorageType]; VirtualStorageType
0x14014ad15  call    cs:__imp_OpenVirtualDisk
0x14014ad1c  nop     dword ptr [rax+rax+00h]
0x14014ad21  mov     ebx, eax
0x14014ad23  test    eax, eax
0x14014ad25  jz      short loc_14014AD3A
0x14014ad27  mov     [rsp+158h+VirtualDiskHandle], r13
0x14014ad2c  jle     loc_14014AF90
0x14014ad32  movzx   ebx, ax
0x14014ad35  jmp     loc_14014AF8A
0x14014ad3a  mov     rcx, [r15+90h]
0x14014ad41  mov     rax, [rcx]
0x14014ad44  mov     edx, 1Eh
0x14014ad49  mov     rax, [rax+50h]
0x14014ad4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14014ad52  test    eax, eax
0x14014ad54  jns     short loc_14014AD60
0x14014ad56  mov     ebx, 80042001h
0x14014ad5b  jmp     loc_14014AF90
0x14014ad60  xor     r9d, r9d; SecurityDescriptorSize
0x14014ad63  lea     r8, [rsp+158h+SecurityDescriptor]; SecurityDescriptor
0x14014ad68  lea     edx, [r9+1]; StringSDRevision
0x14014ad6c  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;GA;;;WD)(A;;GA;;;AC)"
0x14014ad73  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14014ad7a  nop     dword ptr [rax+rax+00h]
0x14014ad7f  test    eax, eax
0x14014ad81  jnz     short loc_14014AD95
0x14014ad83  call    cs:__imp_GetLastError
0x14014ad8a  nop     dword ptr [rax+rax+00h]
0x14014ad8f  mov     ebx, eax
0x14014ad91  test    eax, eax
0x14014ad93  jmp     short loc_14014AD2C
0x14014ad95  xorps   xmm0, xmm0
0x14014ad98  xor     eax, eax
0x14014ad9a  movups  xmmword ptr [rsp+158h+var_D0.Version], xmm0
0x14014ada2  mov     [rsp+158h+var_C0], rax
0x14014adaa  mov     [rsp+158h+var_D0.Version], 1
0x14014adb5  mov     eax, [r15+0C8h]
0x14014adbc  neg     eax
0x14014adbe  sbb     ecx, ecx
0x14014adc0  not     ecx
0x14014adc2  and     ecx, 2
0x14014adc5  mov     r8d, ecx
0x14014adc8  or      r8d, 1
0x14014adcc  cmp     [r15+0CCh], r12d
0x14014add3  cmovz   r8d, ecx
0x14014add7  or      r8d, 4; Flags
0x14014addb  mov     [rsp+158h+Handle], r12; Overlapped
0x14014ade0  lea     rax, [rsp+158h+var_D0]
0x14014ade8  mov     [rsp+158h+Parameters], rax; Parameters
0x14014aded  xor     r9d, r9d; ProviderSpecificFlags
0x14014adf0  mov     rdx, [rsp+158h+SecurityDescriptor]; SecurityDescriptor
0x14014adf5  mov     rcx, [rsp+158h+VirtualDiskHandle]; VirtualDiskHandle
0x14014adfa  call    cs:__imp_AttachVirtualDisk
0x14014ae01  nop     dword ptr [rax+rax+00h]
0x14014ae06  mov     ebx, eax
0x14014ae08  test    eax, eax
0x14014ae0a  jnz     loc_14014AD2C
0x14014ae10  mov     rcx, [r15+90h]
0x14014ae17  mov     rax, [rcx]
0x14014ae1a  lea     edx, [rbx+32h]
0x14014ae1d  mov     rax, [rax+50h]
0x14014ae21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14014ae26  test    eax, eax
0x14014ae28  js      loc_14014AD56
0x14014ae2e  mov     ecx, dword ptr [rsp+158h+Size]; Size
0x14014ae32  call    cs:__imp_malloc
0x14014ae39  nop     dword ptr [rax+rax+00h]
0x14014ae3e  mov     rsi, rax
0x14014ae41  test    rax, rax
0x14014ae44  jnz     short loc_14014AE50
0x14014ae46  mov     ebx, 8007000Eh
0x14014ae4b  jmp     loc_14014AF90
0x14014ae50  mov     r8, rsi; DiskPath
0x14014ae53  lea     rdx, [rsp+158h+Size]; DiskPathSizeInBytes
0x14014ae58  mov     rcx, [rsp+158h+VirtualDiskHandle]; VirtualDiskHandle
0x14014ae5d  call    cs:__imp_GetVirtualDiskPhysicalPath
0x14014ae64  nop     dword ptr [rax+rax+00h]
0x14014ae69  mov     ebx, eax
0x14014ae6b  cmp     eax, 7Ah ; 'z'
0x14014ae6e  jnz     short loc_14014AEA6
0x14014ae70  mov     edx, dword ptr [rsp+158h+Size]
0x14014ae74  mov     rcx, rsi
0x14014ae77  call    cs:__imp__o_realloc
0x14014ae7e  nop     dword ptr [rax+rax+00h]
0x14014ae83  test    rax, rax
0x14014ae86  jz      short loc_14014AE46
0x14014ae88  mov     rsi, rax
0x14014ae8b  mov     r8, rax; DiskPath
0x14014ae8e  lea     rdx, [rsp+158h+Size]; DiskPathSizeInBytes
0x14014ae93  mov     rcx, [rsp+158h+VirtualDiskHandle]; VirtualDiskHandle
0x14014ae98  call    cs:__imp_GetVirtualDiskPhysicalPath
0x14014ae9f  nop     dword ptr [rax+rax+00h]
0x14014aea4  mov     ebx, eax
0x14014aea6  cmp     ebx, 37h ; '7'
0x14014aea9  jnz     short loc_14014AEBE
0x14014aeab  mov     ecx, 3E8h; dwMilliseconds
0x14014aeb0  call    cs:__imp_Sleep
0x14014aeb7  nop     dword ptr [rax+rax+00h]
0x14014aebc  jmp     short loc_14014AE50
0x14014aebe  test    ebx, ebx
0x14014aec0  jnz     loc_14014AF85
0x14014aec6  mov     rcx, [r15+90h]
0x14014aecd  mov     rax, [rcx]
0x14014aed0  lea     edx, [rbx+50h]
0x14014aed3  mov     rax, [rax+50h]
0x14014aed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14014aedc  test    eax, eax
0x14014aede  js      loc_14014AD56
0x14014aee4  mov     [rsp+158h+hTemplateFile], r12; hTemplateFile
0x14014aee9  mov     dword ptr [rsp+158h+Handle], 100080h; dwFlagsAndAttributes
0x14014aef1  lea     r8d, [rbx+3]; dwShareMode
0x14014aef5  mov     dword ptr [rsp+158h+Parameters], r8d; dwCreationDisposition
0x14014aefa  xor     r9d, r9d; lpSecurityAttributes
0x14014aefd  xor     edx, edx; dwDesiredAccess
0x14014aeff  mov     rcx, rsi; lpFileName
0x14014af02  call    cs:__imp_CreateFileW
0x14014af09  nop     dword ptr [rax+rax+00h]
0x14014af0e  mov     r14, rax
0x14014af11  cmp     rax, r13
0x14014af14  jz      loc_14014AD83
0x14014af1a  mov     [rsp+158h+lpOverlapped], r12; lpOverlapped
0x14014af1f  lea     rax, [rsp+158h+BytesReturned]
0x14014af24  mov     [rsp+158h+hTemplateFile], rax; lpBytesReturned
0x14014af29  mov     dword ptr [rsp+158h+Handle], 8; nOutBufferSize
0x14014af31  lea     rax, [rsp+158h+OutBuffer]
0x14014af39  mov     [rsp+158h+Parameters], rax; lpOutBuffer
0x14014af3e  xor     r9d, r9d; nInBufferSize
0x14014af41  xor     r8d, r8d; lpInBuffer
0x14014af44  mov     edx, 41018h; dwIoControlCode
0x14014af49  mov     rcx, r14; hDevice
0x14014af4c  call    cs:__imp_DeviceIoControl
0x14014af53  nop     dword ptr [rax+rax+00h]
0x14014af58  test    eax, eax
0x14014af5a  jz      loc_14014AD83
0x14014af60  mov     rcx, [r15+90h]
0x14014af67  mov     rax, [rcx]
0x14014af6a  lea     edx, [rbx+64h]
0x14014af6d  mov     rax, [rax+50h]
0x14014af71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14014af76  mov     ebx, eax
0x14014af78  mov     [rsp+158h+var_118], eax
0x14014af7c  test    eax, eax
0x14014af7e  jns     short loc_14014AF94
0x14014af80  jmp     loc_14014AD56
0x14014af85  jle     short loc_14014AF90
0x14014af87  movzx   ebx, bx
0x14014af8a  or      ebx, 80070000h
0x14014af90  mov     [rsp+158h+var_118], ebx
0x14014af94  mov     rcx, [rsp+158h+SecurityDescriptor]; hMem
0x14014af99  test    rcx, rcx
0x14014af9c  jz      short loc_14014AFAF
0x14014af9e  call    cs:__imp_LocalFree
0x14014afa5  nop     dword ptr [rax+rax+00h]
0x14014afaa  mov     [rsp+158h+SecurityDescriptor], r12
0x14014afaf  test    rsi, rsi
0x14014afb2  jz      short loc_14014AFC3
0x14014afb4  mov     rcx, rsi; Block
0x14014afb7  call    cs:__imp_free
0x14014afbe  nop     dword ptr [rax+rax+00h]
0x14014afc3  cmp     r14, r13
0x14014afc6  jz      short loc_14014AFD7
0x14014afc8  mov     rcx, r14; hObject
0x14014afcb  call    cs:__imp_CloseHandle
0x14014afd2  nop     dword ptr [rax+rax+00h]
0x14014afd7  mov     rcx, [rsp+158h+VirtualDiskHandle]; hObject
0x14014afdc  cmp     rcx, r13
0x14014afdf  jz      short loc_14014AFF2
0x14014afe1  call    cs:__imp_CloseHandle
0x14014afe8  nop     dword ptr [rax+rax+00h]
0x14014afed  mov     [rsp+158h+VirtualDiskHandle], r13
0x14014aff2  test    ebx, ebx
0x14014aff4  jns     loc_14014B0BA
0x14014affa  mov     esi, ebx
0x14014affc  btr     esi, 1Ch
0x14014b000  mov     r9d, esi
0x14014b003  lea     r8, aU_1; "%%%%%u"
0x14014b00a  mov     r14d, 10h
0x14014b010  lea     rcx, [rsp+158h+var_50]
0x14014b018  mov     edx, r14d
0x14014b01b  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14014b020  mov     r9d, esi
0x14014b023  lea     r8, a0x08x; "0x%08X"
0x14014b02a  mov     edx, r14d
0x14014b02d  lea     rcx, [rsp+158h+var_70]
0x14014b035  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x14014b03a  cmp     ebx, 80042001h
0x14014b040  jz      short loc_14014B08B
0x14014b042  cmp     qword ptr [rdi+18h], 7
0x14014b047  jbe     short loc_14014B04C
0x14014b049  mov     rdi, [rdi]
0x14014b04c  mov     [rsp+158h+var_110], rdi
0x14014b051  lea     rax, [rsp+158h+var_70]
0x14014b059  mov     [rsp+158h+hTemplateFile], rax; __int64
0x14014b05e  lea     rax, [rsp+158h+var_50]
0x14014b066  mov     [rsp+158h+Handle], rax; __int64
0x14014b06b  lea     rax, [rsp+158h+var_110]
0x14014b070  mov     [rsp+158h+Parameters], rax; __int64
0x14014b075  mov     edx, 5; unsigned int
0x14014b07a  lea     rcx, MSVHDSVC_MOUNT_FAILURE; struct _EVENT_DESCRIPTOR *
0x14014b081  call    ??$VmEventWriteAndReport@PEBGAEAY0BA@GAEAY0BA@G@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBGAEAY0BA@G4@Z; VmEventWriteAndReport<ushort const *,ushort (&)[16],ushort (&)[16]>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort (&)[16],ushort (&)[16])
0x14014b086  jmp     loc_14014B16B
0x14014b08b  cmp     qword ptr [rdi+18h], 7
0x14014b090  jbe     short loc_14014B095
0x14014b092  mov     rdi, [rdi]
0x14014b095  mov     [rsp+158h+var_110], rdi
0x14014b09a  lea     rax, [rsp+158h+var_110]
0x14014b09f  mov     [rsp+158h+Parameters], rax; __int64
0x14014b0a4  mov     edx, 5; unsigned int
0x14014b0a9  lea     rcx, MSVHDSVC_MOUNT_CANCELED; struct _EVENT_DESCRIPTOR *
0x14014b0b0  call    ??$VmEventWriteAndReport@AEAPEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBGAEAPEBG@Z; VmEventWriteAndReport<ushort const * &>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &)
0x14014b0b5  jmp     loc_14014B16B
0x14014b0ba  cmp     qword ptr [rdi+18h], 7
0x14014b0bf  jbe     short loc_14014B0C6
0x14014b0c1  mov     rax, [rdi]
0x14014b0c4  jmp     short loc_14014B0C9
0x14014b0c6  mov     rax, rdi
0x14014b0c9  mov     [rsp+158h+var_110], rax
0x14014b0ce  lea     r9, [rsp+158h+var_110]
0x14014b0d3  mov     edx, 1; unsigned int
0x14014b0d8  lea     rcx, MSVHDSVC_MOUNT_COMPLETED; EventDescriptor
0x14014b0df  call    ??$VmEventWrite@PEBG@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@$$QEAPEBG@Z; VmEventWrite<ushort const *>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const * &&)
0x14014b0e4  mov     [rsp+158h+var_110], r12
0x14014b0e9  lea     rax, [rsp+158h+OutBuffer]
0x14014b0f1  mov     [rsp+158h+var_108], rax
0x14014b0f6  mov     rdx, rdi
0x14014b0f9  lea     rcx, [rsp+158h+var_108]
0x14014b0fe  call    ??$CreateInstance@PEAU_SCSI_ADDRESS@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY00$$CBG@?$VmComMultiInstanceObject@VWmiMsvmMountedStorageImage@@@Vml@@SAPEAVWmiMsvmMountedStorageImage@@$$QEAPEAU_SCSI_ADDRESS@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY00$$CBG@Z; Vml::VmComMultiInstanceObject<WmiMsvmMountedStorageImage>::CreateInstance<_SCSI_ADDRESS *,std::wstring &,ushort const (&)[1]>(_SCSI_ADDRESS * &&,std::wstring &,ushort const (&)[1])
0x14014b103  mov     rdx, rax
0x14014b106  lea     rcx, [rsp+158h+var_110]
0x14014b10b  call    ??$Attach@VWmiMsvmVirtualSystemReferencePointService@@@?$VmComPtr@UIVmWmiObject@@@Vml@@QEAAXPEAVWmiMsvmVirtualSystemReferencePointService@@@Z; Vml::VmComPtr<IVmWmiObject>::Attach<WmiMsvmVirtualSystemReferencePointService>(WmiMsvmVirtualSystemReferencePointService *)
0x14014b110  mov     rcx, [r15+90h]
0x14014b117  mov     rax, [rcx]
0x14014b11a  mov     rdx, [rsp+158h+var_110]
0x14014b11f  mov     rax, [rax+140h]
0x14014b126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14014b12b  mov     edi, eax
0x14014b12d  test    eax, eax
0x14014b12f  jns     short loc_14014B15A
0x14014b131  mov     esi, 8061h
0x14014b136  mov     ecx, esi
0x14014b138  call    VmlIsDebugTraceEnabled
0x14014b13d  test    eax, eax
0x14014b13f  jz      short loc_14014B15A
0x14014b141  mov     r9d, edi
0x14014b144  lea     r8, aDiskmountopera; "DiskMountOperation::RunTaskInternal"
0x14014b14b  lea     rdx, aHsUnableToAddT; "%hs unable to add the affected Msvm_Mou"...
  ... truncated ...
```
