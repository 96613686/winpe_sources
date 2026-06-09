# Smb2CreateFile

- ea: `0x14007a89c`
- end: `0x14007c2a4`
- name: `Smb2CreateFile`
- size: `6664`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, int, __int64, __int64, ULONG, __int64, __int64, char, __int64, int, int, int, __int64, __int64, int, __int64, __int64, char, char)`
- caller_count: `2`
- callee_count: `44`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14006fc74`
- `0x140079c80`

## callees

- `0x140005070`
- `0x14000c4bc`
- `0x140012790`
- `0x140012ca0`
- `0x140013810`
- `0x1400139d0`
- `0x140013bc0`
- `0x140014df0`
- `0x140015000`
- `0x1400152a0`
- `0x140015830`
- `0x140017240`
- `0x140018020`
- `0x14001f838`
- `0x1400222ec`
- `0x140022690`
- `0x140022958`
- `0x1400229ac`
- `0x14002402c`
- `0x140024f9c`
- `0x140028dbc`
- `0x140028e58`
- `0x14002a25c`
- `0x14002a478`
- `0x14002a5d4`
- `0x14002a9d8`
- `0x14002abb0`
- `0x14002adf4`
- `0x14002af00`
- `0x14002b3c8`
- `0x140038490`
- `0x140038680`
- `0x140038980`
- `0x1400593dc`
- `0x140066300`
- `0x140067bd4`
- `0x14006f438`
- `0x140077650`
- `0x14007a89c`
- `0x14007c2b0`
- `0x14007cc40`
- `0x140080a10`
- `0x140081de0`
- `0x140084e90`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14007aedf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007aedf`
- `ntoskrnl!ExAllocatePool2` at `0x14007adfe`
- `ntoskrnl!ExAllocatePool2` at `0x14007b418`
- `ntoskrnl!ExAllocatePool2` at `0x14007adfe`
- `ntoskrnl!ExAllocatePool2` at `0x14007b418`
- `ntoskrnl!ExInitializeResourceLite` at `0x14007b4aa`
- `ntoskrnl!ExInitializeResourceLite` at `0x14007b4aa`
- `ntoskrnl!ZwClose` at `0x14007b435`
- `ntoskrnl!ZwClose` at `0x14007b512`
- `ntoskrnl!ZwClose` at `0x14007b435`
- `ntoskrnl!ZwClose` at `0x14007b512`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14007b5aa`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14007b5aa`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007b712`
- `ntoskrnl!KeInitializeSpinLock` at `0x14007b712`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c1e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c1e8`
- `ntoskrnl!EtwActivityIdControl` at `0x14007b7d7`
- `ntoskrnl!EtwActivityIdControl` at `0x14007b7d7`
- `ntoskrnl!KeInitializeEvent` at `0x14007b488`
- `ntoskrnl!KeInitializeEvent` at `0x14007b488`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14007af72`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14007af72`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14007afbb`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14007c22a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14007afbb`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14007c22a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14007bc2b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14007bc2b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007bc4e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007bca7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007bd02`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007bdf0`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007c017`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007bc4e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007bca7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007bd02`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007bdf0`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007c017`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14007c03c`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14007c06d`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14007c0a9`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14007c03c`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14007c06d`
- `ntoskrnl!IoCheckFunctionAccess` at `0x14007c0a9`
- `ntoskrnl!IoCreateFileEx` at `0x14007b16c`
- `ntoskrnl!IoCreateFileEx` at `0x14007b354`
- `ntoskrnl!IoCreateFileEx` at `0x14007b16c`
- `ntoskrnl!IoCreateFileEx` at `0x14007b354`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007b2a9`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007b575`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007b5f7`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007b964`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007b2a9`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007b575`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007b5f7`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007b964`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x14007b60b`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x14007ba91`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x14007b60b`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x14007ba91`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x14007bb38`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x14007bb38`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007bb4c`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007bb4c`
- `srvnet!SrvLibGetBaseFileName` at `0x14007a980`
- `srvnet!SrvLibGetBaseFileName` at `0x14007a980`
- `srvnet!SrvLibIsDosDeviceName` at `0x14007a990`
- `srvnet!SrvLibIsDosDeviceName` at `0x14007a990`
- `srvnet!SrvNetCheckIfPipeAccessAllowed` at `0x14007aa1e`
- `srvnet!SrvNetCheckIfPipeAccessAllowed` at `0x14007aa1e`
- `srvnet!SrvAdminAllowClusterPipeAccess` at `0x14007ad44`
- `srvnet!SrvAdminAllowClusterPipeAccess` at `0x14007ad44`
- `srvnet!SrvAdminRemapPipeName` at `0x14007adbe`
- `srvnet!SrvAdminRemapPipeName` at `0x14007adbe`
- `srvnet!SrvAdminNodeGetNextId` at `0x14007bc87`
- `srvnet!SrvAdminNodeGetNextId` at `0x14007bc87`
- `srvnet!SrvAdminNodeGetSignature` at `0x14007bcb5`
- `srvnet!SrvAdminNodeGetSignature` at `0x14007bcb5`
- `srvnet!SrvNetFreePool` at `0x14007c202`
- `srvnet!SrvNetFreePool` at `0x14007c202`

## string_xrefs

- `0x14007b0f6`: `Smb2CreateFile`
- `0x14007b178`: `Smb2CreateFile`
- `0x14007b2cf`: `Smb2CreateFile`
- `0x14007b360`: `Smb2CreateFile`

## pseudocode

```c
__int64 __fastcall Smb2CreateFile(
        struct _UNICODE_STRING *a1,
        ACCESS_MASK a2,
        ULONG a3,
        ULONG a4,
        ULONG Disposition,
        unsigned int a6,
        union _LARGE_INTEGER *a7,
        void *a8,
        ULONG EaLength,
        __int64 a10,
        void *a11,
        char a12,
        __int64 a13,
        int a14,
        int a15,
        int a16,
        _QWORD *a17,
        struct _IO_STATUS_BLOCK *a18,
        int a19,
        struct _ECP_LIST *a20,
        __int64 a21,
        unsigned __int8 a22,
        unsigned __int8 a23)
{
  _QWORD *v23; // rsi
  __int64 v25; // r15
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rax
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  __int64 result; // rax
  int v32; // edi
  ULONG CreateOptions; // ebx
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rdx
  int v36; // edi
  __int64 v37; // rcx
  unsigned __int64 v38; // rdx
  WCHAR *v39; // rcx
  const WCHAR *v40; // rcx
  int v41; // edx
  int v42; // r8d
  _QWORD *v43; // rcx
  bool v44; // cf
  __int64 v45; // rax
  _QWORD *BypassCSVHandle; // rax
  void *v47; // rax
  __int64 v48; // r9
  __int64 Pool2; // r14
  int v50; // eax
  int v51; // r8d
  __int64 v52; // rdx
  NTSTATUS v53; // eax
  NTSTATUS inserted; // ebx
  int v55; // r8d
  PVOID v56; // rcx
  HANDLE *ShareHandle; // rax
  __int64 v58; // rdx
  NTSTATUS v59; // eax
  PDEVICE_OBJECT v60; // rcx
  struct _UNICODE_STRING *v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  USHORT SectorSize; // cx
  BOOLEAN IsEcpAcknowledged; // al
  __int64 v67; // rdx
  int v68; // eax
  const void **v69; // rdx
  __int16 v70; // ax
  _QWORD *v71; // rbx
  __int64 v72; // rax
  __int64 *v73; // r8
  NTSTATUS Parameter; // eax
  __int64 v75; // r8
  __int64 v76; // rcx
  int v77; // r8d
  __int64 v78; // rcx
  PVOID v79; // rcx
  char v80; // al
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // r8
  unsigned __int64 v84; // rcx
  unsigned __int64 v85; // rax
  unsigned __int64 v86; // rdx
  __int64 v87; // r9
  ACCESS_MASK v88; // ecx
  int v89; // ecx
  __int64 v90; // rax
  struct _UNICODE_STRING *v91; // rdi
  int AllocationSize; // [rsp+20h] [rbp-F0h]
  int AllocationSizeb; // [rsp+20h] [rbp-F0h]
  int AllocationSizea; // [rsp+20h] [rbp-F0h]
  int AllocationSizec; // [rsp+20h] [rbp-F0h]
  int FileAttributes; // [rsp+28h] [rbp-E8h]
  char v97; // [rsp+90h] [rbp-80h]
  char v98; // [rsp+91h] [rbp-7Fh] BYREF
  char v99; // [rsp+92h] [rbp-7Eh]
  ULONG EcpContextSize[2]; // [rsp+98h] [rbp-78h] BYREF
  ULONG ShareAccess; // [rsp+A0h] [rbp-70h] BYREF
  ULONG v102[2]; // [rsp+A8h] [rbp-68h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+B0h] [rbp-60h]
  ULONG v104; // [rsp+B4h] [rbp-5Ch]
  struct _UNICODE_STRING *v105; // [rsp+B8h] [rbp-58h]
  PLARGE_INTEGER v106; // [rsp+C0h] [rbp-50h] BYREF
  int v107; // [rsp+C8h] [rbp-48h] BYREF
  ULONG v108; // [rsp+CCh] [rbp-44h]
  int v109; // [rsp+D0h] [rbp-40h]
  PVOID P; // [rsp+D8h] [rbp-38h]
  void *v111; // [rsp+E0h] [rbp-30h]
  void *FileHandle; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v113; // [rsp+F0h] [rbp-20h]
  PVOID EaBuffer; // [rsp+F8h] [rbp-18h] BYREF
  PCWSTR SourceString; // [rsp+100h] [rbp-10h]
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp-8h]
  PVOID v117; // [rsp+110h] [rbp+0h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+118h] [rbp+8h] BYREF
  __int64 v119; // [rsp+138h] [rbp+28h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+140h] [rbp+30h] BYREF
  _QWORD v121[2]; // [rsp+170h] [rbp+60h] BYREF
  _QWORD *v122; // [rsp+180h] [rbp+70h]
  _QWORD *v123; // [rsp+188h] [rbp+78h]
  struct _UNICODE_STRING DestinationString; // [rsp+190h] [rbp+80h] BYREF
  __int128 v125; // [rsp+1A0h] [rbp+90h] BYREF
  _BYTE v126[512]; // [rsp+1B0h] [rbp+A0h] BYREF

  v23 = a17;
  v106 = a7;
  v25 = a17[70];
  EaBuffer = a8;
  *(_QWORD *)EcpContextSize = a10;
  v111 = a11;
  v113 = a13;
  IoStatusBlock = a18;
  LOWORD(v119) = 0;
  v26 = a17[12];
  DesiredAccess = a2;
  memset(&ObjectAttributes, 0, 44);
  FileHandle = 0;
  v121[0] = 0;
  DestinationString = 0;
  v121[1] = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  v98 = 0;
  v27 = *(_QWORD *)(v26 + 496);
  v108 = a3;
  v105 = a1;
  ShareAccess = a4;
  v122 = a17;
  v107 = 0;
  SrvLibGetBaseFileName(a1, v121);
  if ( (unsigned __int8)SrvLibIsDosDeviceName(v121) && !Smb2AllowOpeningDosNames )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u) )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          (unsigned int)WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
          (_DWORD)a17,
          (__int64)v121);
    }
    return 3221225506LL;
  }
  v28 = *(_QWORD *)(v25 + 56);
  if ( v28
    && *(_DWORD *)(v28 + 76) == 1
    && !(unsigned __int8)SrvNetCheckIfPipeAccessAllowed(*(_QWORD *)(*(_QWORD *)(v27 + 56) + 480LL)) )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225506LL;
    }
    v30 = 11;
LABEL_28:
    WPP_SF_q(v29->AttachedDevice, v30, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, a17);
    return 3221225506LL;
  }
  *(_DWORD *)(&DriverContext.Size + 1) = 0;
  *(&DriverContext.Size + 3) = 0;
  DriverContext.Size = 40;
  v119 = 1;
  DriverContext.ExtraCreateParameter = a20;
  *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
  if ( (a6 & 0x102080) != 0 )
    return 3221225659LL;
  v32 = Smb2CheckShareAccess((_DWORD)a17, (_DWORD)a1, DesiredAccess, (unsigned int)&ShareAccess, (__int64)&v107);
  if ( v32 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, a17, v32);
    }
    return (unsigned int)v32;
  }
  CreateOptions = a6 & (~(unsigned __int8)(a6 >> 1) & 4 | 0xFFFEFFCB);
  v104 = CreateOptions;
  if ( (CreateOptions & 0x1000) != 0 && (v107 & 0x10000) == 0 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225506LL;
    }
    v30 = 13;
    goto LABEL_28;
  }
  v99 = 0;
  if ( Disposition != 1 )
  {
    if ( (CreateOptions & 1) != 0 )
    {
      if ( (CreateOptions & 0x40) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
            a17,
            CreateOptions);
        }
        return 3221225485LL;
      }
      if ( Disposition != 2 && Disposition != 3 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          return 3221225485LL;
        }
        v35 = 15;
LABEL_52:
        WPP_SF_qD(v34->AttachedDevice, v35, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, a17, Disposition);
        return 3221225485LL;
      }
      v36 = 4;
    }
    else if ( Disposition )
    {
      if ( Disposition != 2 && Disposition != 3 && Disposition - 4 >= 2 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          return 3221225485LL;
        }
        v35 = 16;
        goto LABEL_52;
      }
      v36 = 2;
    }
    else
    {
      v36 = 65538;
    }
    v102[0] = Smb2CheckShareAccess((_DWORD)a17, (_DWORD)a1, v36, (unsigned int)&ShareAccess, 0);
    if ( (v102[0] & 0x80000000) != 0 )
    {
      if ( Disposition != 3 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
            a17,
            Disposition,
            v36);
        }
        return v102[0];
      }
      v99 = 1;
      Disposition = 1;
    }
  }
  P = 0;
  v117 = 0;
  SourceString = 0;
  v109 = 0;
  v97 = 0;
  if ( (a12 & 1) != 0 )
  {
    ObjectAttributes.ObjectName = a1;
LABEL_83:
    ObjectAttributes.SecurityDescriptor = *(PVOID *)EcpContextSize;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Length = 48;
    goto LABEL_104;
  }
  v37 = *(_QWORD *)(v25 + 56);
  *(_QWORD *)v102 = v37;
  if ( *(_DWORD *)(v37 + 76) == 1 )
  {
    v125 = 0;
    if ( (*(_DWORD *)(v37 + 84) & 0x4000000) != 0 )
    {
      if ( !(unsigned __int8)SrvAdminAllowClusterPipeAccess(a1) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qZ(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            (unsigned int)WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
            (_DWORD)a17,
            (__int64)a1);
        }
        return 3221225524LL;
      }
      v37 = *(_QWORD *)v102;
    }
    if ( *(_BYTE *)(*(_QWORD *)(v25 + 56) + 152LL) )
    {
      result = SrvAdminRemapPipeName(&v125, v37 + 40, a1, &v98);
      if ( (int)result < 0 )
        return result;
    }
    v38 = a1->Length + 38LL + *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL) + 120LL);
    if ( v38 <= 0x200 )
    {
      v109 = 0;
      SourceString = (PCWSTR)v126;
      memset(v126, 0, sizeof(v126));
      v39 = (WCHAR *)v126;
    }
    else
    {
      SourceString = (PCWSTR)ExAllocatePool2(64, v38, 1647465292);
      v39 = (WCHAR *)SourceString;
      if ( !SourceString )
        return 3221225989LL;
      v109 = 2;
    }
    *(_OWORD *)v39 = *(_OWORD *)L"\\Device\\NamedPipe\\";
    *((_OWORD *)v39 + 1) = *(_OWORD *)L"NamedPipe\\";
    *((_DWORD *)v39 + 8) = *(_DWORD *)L"e\\";
    memmove(
      v39 + 18,
      *(const void **)(*(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL) + 128LL),
      *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL) + 120LL));
    memmove(
      (void *)&SourceString[((unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL) + 120LL) >> 1)
                          + 18],
      a1->Buffer,
      a1->Length);
    v40 = SourceString;
    *(PCWSTR)((char *)SourceString
            + ((a1->Length + (unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL) + 120LL))
             & 0xFFFFFFFFFFFFFFFEuLL)
            + 36) = 0;
    RtlInitUnicodeString(&DestinationString, v40);
    ObjectAttributes.ObjectName = &DestinationString;
    goto LABEL_83;
  }
  P = (PVOID)Smb2GetShareHandleEx(*(_QWORD *)(v37 + 96), v113, 0, 0);
  v43 = P;
  if ( !P )
  {
    v44 = v113 != 0;
    v113 = -v113;
    return v44 ? -1073741772 : -1073741202;
  }
  v45 = *(_QWORD *)(v25 + 56);
  if ( !*(_BYTE *)(v45 + 153) || v113 )
  {
    BypassCSVHandle = 0;
LABEL_97:
    ObjectAttributes.Length = 48;
    if ( v97 )
      v47 = (void *)BypassCSVHandle[11];
    else
      v47 = (void *)v43[11];
    ObjectAttributes.RootDirectory = v47;
    ObjectAttributes.SecurityDescriptor = *(PVOID *)EcpContextSize;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = a1;
    ObjectAttributes.SecurityQualityOfService = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v48 = *(_QWORD *)(v25 + 56);
      LOBYTE(v42) = v97 != 0 ? 89 : 78;
      LOBYTE(v41) = *(_BYTE *)(v48 + 153) != 0 ? 89 : 78;
      WPP_SF_qZqqcc(
        WPP_GLOBAL_Control->AttachedDevice,
        v41,
        v42,
        (_DWORD)a17,
        (__int64)a1,
        v48,
        *(_QWORD *)(*(_QWORD *)(v48 + 96) + 328LL),
        v41,
        v42);
    }
LABEL_104:
    ObjectAttributes.SecurityQualityOfService = v111;
    LOBYTE(Pool2) = 0;
    v50 = Smb2ImpersonateWorkItem(v25);
    v52 = 0;
    v102[0] = v50;
    if ( v50 < 0 )
    {
      LODWORD(v111) = 0;
      inserted = v50;
      goto LABEL_274;
    }
    LOBYTE(AllocationSize) = 1;
    v123 = a17 + 73;
    LOBYTE(v52) = 3;
    SRV2_PERF_ENTER_EX(a17 + 73, v52, 808, "Smb2CreateFile", AllocationSize);
    v53 = IoCreateFileEx(
            &FileHandle,
            DesiredAccess,
            &ObjectAttributes,
            IoStatusBlock,
            v106,
            v108,
            ShareAccess,
            Disposition,
            CreateOptions,
            EaBuffer,
            EaLength,
            CreateFileTypeNone,
            0,
            0x209u,
            &DriverContext);
    LOBYTE(AllocationSizeb) = 1;
    inserted = v53;
    SRV2_PERF_ENTER_EX(a17 + 73, 0, 825, "Smb2CreateFile", AllocationSizeb);
    LODWORD(v111) = inserted;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_dqqZddddqidd(
        WPP_GLOBAL_Control->AttachedDevice,
        a22,
        v55,
        inserted,
        (char)a17,
        (char)ObjectAttributes.RootDirectory,
        (__int64)ObjectAttributes.ObjectName,
        DesiredAccess,
        ShareAccess,
        Disposition,
        v104,
        (char)DriverContext.ExtraCreateParameter,
        a21,
        a22,
        a23);
    }
    if ( inserted == -1073741202 || inserted == -1073741810 || inserted == -1073741806 )
    {
      if ( P )
      {
        v56 = P;
        *((_BYTE *)P + 104) = 1;
        Smb2DereferenceHandle(v56);
        ShareHandle = (HANDLE *)Smb2GetShareHandleEx(*(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL), v113, 0, 0);
        P = ShareHandle;
        if ( ShareHandle )
        {
          ObjectAttributes.RootDirectory = ShareHandle[11];
          if ( !DriverContext.ExtraCreateParameter
            || !*(_BYTE *)(v25 + 306)
            || !*(_QWORD *)(v25 + 104)
            || FsRtlFindExtraCreateParameter(DriverContext.ExtraCreateParameter, &GUID_ECP_DUAL_OPLOCK_KEY, 0, 0) >= 0
            || (inserted = Smb2AllocateAndInsertLeasingEcp(a17, DriverContext.ExtraCreateParameter), inserted >= 0) )
          {
            LOBYTE(AllocationSizea) = 1;
            LOBYTE(v58) = 3;
            SRV2_PERF_ENTER_EX(a17 + 73, v58, 875, "Smb2CreateFile", AllocationSizea);
            v59 = IoCreateFileEx(
                    &FileHandle,
                    DesiredAccess,
                    &ObjectAttributes,
                    IoStatusBlock,
                    v106,
                    v108,
                    ShareAccess,
                    Disposition,
                    v104,
                    EaBuffer,
                    EaLength,
                    CreateFileTypeNone,
                    0,
                    0x209u,
                    &DriverContext);
            LOBYTE(AllocationSizec) = 1;
            LODWORD(v111) = v59;
            inserted = v59;
            SRV2_PERF_ENTER_EX(a17 + 73, 0, 893, "Smb2CreateFile", AllocationSizec);
          }
        }
      }
    }
    if ( inserted == -2147483603 && !IoStatusBlock->Information )
    {
      v60 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, a17);
      }
      if ( (byte_14004C33B & 1) != 0 )
        McTemplateK0_EtwWriteTransfer(v60, SRV2_EVENT_RECEIVED_NULL_REPARSE_BUFFER);
      inserted = -1073741192;
      Smb2Revert();
      goto LABEL_274;
    }
    Smb2Revert();
    LODWORD(v52) = 0;
    if ( inserted < 0 )
    {
      if ( inserted == -1073741810 )
      {
        v90 = *(_QWORD *)(v25 + 56);
        if ( !v90 )
          goto LABEL_274;
        if ( (*(_DWORD *)(v90 + 84) & 0x4000000) != 0 )
          goto LABEL_269;
      }
      if ( inserted == -1069547514 && DriverContext.ExtraCreateParameter && (a22 || a23) )
      {
LABEL_269:
        LODWORD(v52) = -1073740697;
        LODWORD(v111) = -1073740697;
        inserted = -1073740697;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_279;
        if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u) && BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_qZ(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            (unsigned int)WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
            (_DWORD)a17,
            (__int64)v105);
      }
      goto LABEL_274;
    }
    v61 = v105;
    EaBuffer = 0;
    Pool2 = ExAllocatePool2(64, v105->Length + 928LL, 1714574156);
    if ( !Pool2 )
    {
      inserted = -1073741670;
LABEL_132:
      ZwClose(FileHandle);
LABEL_279:
      Smb2Revert();
      goto LABEL_280;
    }
    v62 = a17[8];
    *(_WORD *)(Pool2 + 16) = v61->Length + 928;
    *(_QWORD *)Pool2 = 1;
    *(_DWORD *)(Pool2 + 8) = 2;
    *(_DWORD *)(Pool2 + 12) = 219;
    *(_QWORD *)(Pool2 + 48) = 0;
    *(_QWORD *)(Pool2 + 56) = Pool2;
    *(_QWORD *)(Pool2 + 64) = v62;
    *(_DWORD *)(Pool2 + 72) = 0;
    KeInitializeEvent((PRKEVENT)(Pool2 + 880), NotificationEvent, 0);
    if ( v97 )
    {
      *(_BYTE *)(Pool2 + 245) = 1;
      v97 = 0;
    }
    inserted = ExInitializeResourceLite((PERESOURCE)(Pool2 + 688));
    if ( inserted < 0 )
    {
      *(_DWORD *)(Pool2 + 12) = 221;
      Smb2FreeFile((PVOID)Pool2);
      goto LABEL_132;
    }
    *(_BYTE *)(Pool2 + 792) = 1;
    _InterlockedAdd((volatile signed __int32 *)(Srv2Statistics + 72), 1u);
    v63 = Smb2AllocateReferencedHandle(a17[8], FileHandle, &EaBuffer);
    *(_QWORD *)(Pool2 + 120) = v63;
    if ( !v63 )
    {
      *(_DWORD *)(Pool2 + 12) = 221;
      Smb2FreeFile((PVOID)Pool2);
      ZwClose(FileHandle);
      inserted = -1073741670;
      goto LABEL_279;
    }
    v64 = *(_QWORD *)(v63 + 96);
    LOBYTE(inserted) = 0;
    v102[0] = inserted;
    *(_DWORD *)(Pool2 + 224) = *(_DWORD *)(Pool2 + 224) & 0xFFFFFDFF
                             | (*(_DWORD *)(*(_QWORD *)(v64 + 8) + 52LL) >> 7) & 0x200;
    if ( DriverContext.ExtraCreateParameter )
    {
      v106 = 0;
      EcpContextSize[0] = 0;
      if ( FsRtlFindExtraCreateParameter(
             DriverContext.ExtraCreateParameter,
             &ECP_TYPE_IO_STOP_ON_SYMLINK_FILTER_GUID,
             (PVOID *)&v106,
             EcpContextSize) >= 0
        && EcpContextSize[0] >= 8
        && v106->LowPart )
      {
        v102[0] = v106->HighPart == 0;
      }
    }
    SectorSize = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(*(_QWORD *)(Pool2 + 120) + 96LL))->SectorSize;
    *(_WORD *)(Pool2 + 196) = SectorSize;
    if ( SectorSize != 512 )
    {
      if ( DriverContext.ExtraCreateParameter )
      {
        v106 = 0;
        EcpContextSize[0] = 0;
        if ( FsRtlFindExtraCreateParameter(
               DriverContext.ExtraCreateParameter,
               &GUID_ECP_OPEN_AS_BLOCK_DEVICE,
               (PVOID *)&v106,
               EcpContextSize) >= 0 )
        {
          IsEcpAcknowledged = FsRtlIsEcpAcknowledged(v106);
          if ( IsEcpAcknowledged )
            *(_WORD *)(Pool2 + 196) = 512;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            LOBYTE(v67) = IsEcpAcknowledged != 0 ? 89 : 78;
            LOBYTE(FileAttributes) = v67;
            WPP_SF_qdc(
              WPP_GLOBAL_Control->AttachedDevice,
              v67,
              WPP_GLOBAL_Control,
              a17,
              *(unsigned __int16 *)(Pool2 + 196),
              FileAttributes);
          }
        }
      }
    }
    ++*(_DWORD *)(Srv2Statistics + 68);
    *(_QWORD *)(*(_QWORD *)(Pool2 + 120) + 80LL) = *(_QWORD *)(v25 + 48);
    if ( ((_InterlockedExchangeAdd64(*(volatile signed __int64 **)(*(_QWORD *)(Pool2 + 120) + 80LL), 1u) + 2)
        & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      __int2c();
    Smb2Revert();
    v68 = HIDWORD(EaBuffer);
    if ( *(_DWORD *)(*(_QWORD *)(v25 + 56) + 84LL) != 0x1000000 )
      v68 = v107 & HIDWORD(EaBuffer);
    v69 = (const void **)v105;
    *(_DWORD *)(Pool2 + 184) = v68;
    *(_DWORD *)(Pool2 + 188) = ShareAccess;
    *(_DWORD *)(Pool2 + 192) = v104;
    v70 = *(_WORD *)v69;
    *(_WORD *)(Pool2 + 210) = *(_WORD *)v69;
    *(_WORD *)(Pool2 + 208) = v70;
    *(_QWORD *)(Pool2 + 216) = Pool2 + 928;
    memmove((void *)(Pool2 + 928), v69[1], *(unsigned __int16 *)v69);
    *(_DWORD *)(Pool2 + 456) = IoStatusBlock->Information;
    KeInitializeSpinLock((PKSPIN_LOCK)(Pool2 + 112));
    v71 = (_QWORD *)(Pool2 + 80);
    *(_QWORD *)(Pool2 + 80) = a21;
    *(_DWORD *)(Pool2 + 88) = -1;
    *(_DWORD *)(Pool2 + 92) = -1;
    *(_QWORD *)(Pool2 + 320) = -1;
    *(_WORD *)(Pool2 + 864) = *(_WORD *)(v25 + 12);
    *(_QWORD *)(Pool2 + 144) = *(_QWORD *)(v25 + 32);
    *(_QWORD *)(Pool2 + 152) = *(_QWORD *)(*(_QWORD *)(v25 + 32) + 24LL);
    Smb2ReferenceSession(*(_QWORD *)(v25 + 32));
    *(_QWORD *)(Pool2 + 128) = *(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL);
    *(_QWORD *)(Pool2 + 136) = *(_QWORD *)(*(_QWORD *)(v25 + 56) + 104LL);
    Smb2ReferenceShare();
    *(_QWORD *)(Pool2 + 64) = a17[8];
    *(_QWORD *)(Pool2 + 160) = *(_QWORD *)(v25 + 56);
    Srv2ReferenceConnection(*(_QWORD *)(v25 + 56));
    _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v25 + 56) + 148LL), 1u);
    *(_QWORD *)(Pool2 + 312) = MEMORY[0xFFFFF78000000014];
    EtwActivityIdControl(3u, (LPGUID)(Pool2 + 96));
    if ( (byte_14004C339 & 8) != 0 )
    {
      v72 = *(_QWORD *)(v25 + 104);
      v73 = (__int64 *)(v72 + 80);
      if ( !v72 )
        v73 = &Srv2ZeroGuid;
      McTemplateK0jjjjjhzr5jqqqqtt_EtwWriteTransfer(
        *(_QWORD *)(v25 + 56) + 24,
        a23,
        (_DWORD)v123,
        Pool2 + 96,
        *(_QWORD *)(v25 + 56) + 24LL,
        *(_QWORD *)(v25 + 32) + 72LL,
        *(_QWORD *)(v122[12] + 496LL) + 72LL,
        *(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL) + 8LL,
        *(_WORD *)(Pool2 + 208) >> 1,
        *(_QWORD *)(Pool2 + 216),
        (__int64)v73,
        DesiredAccess,
        ShareAccess,
        v104,
        v108,
        a22,
        a23);
      v23 = v122;
      v71 = (_QWORD *)(Pool2 + 80);
    }
    if ( *(_BYTE *)(v25 + 377) || *(_BYTE *)(v25 + 378) )
      *(_OWORD *)(Pool2 + 672) = *(_OWORD *)(v25 + 336);
    *(_QWORD *)(Pool2 + 664) = Pool2 + 656;
    *(_QWORD *)(Pool2 + 656) = Pool2 + 656;
    *(_QWORD *)(Pool2 + 400) = Pool2 + 392;
    *(_QWORD *)(Pool2 + 392) = Pool2 + 392;
    *(_QWORD *)(Pool2 + 440) = Pool2 + 432;
    *(_QWORD *)(Pool2 + 432) = Pool2 + 432;
    memset((void *)(Pool2 + 592), 255, 0x40u);
    *(_BYTE *)(v25 + 308) = v102[0];
    if ( DriverContext.ExtraCreateParameter && (*(_BYTE *)(v25 + 379) || *(_BYTE *)(v25 + 382) || *(_BYTE *)(v25 + 328)) )
    {
      *(_QWORD *)EcpContextSize = 0;
      v102[0] = 0;
      Parameter = FsRtlFindExtraCreateParameter(
                    DriverContext.ExtraCreateParameter,
                    &Smb2RkfGuidEcpIn,
                    (PVOID *)EcpContextSize,
                    v102);
      if ( Parameter == -1073741275 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqZ(
            WPP_GLOBAL_Control->AttachedDevice,
            24,
            (unsigned int)WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
            (_DWORD)v23,
            (char)DriverContext.ExtraCreateParameter,
            v25 + 192);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqZD(
            WPP_GLOBAL_Control->AttachedDevice,
            25,
            (unsigned int)WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
            (_DWORD)v23,
            (char)DriverContext.ExtraCreateParameter,
            v25 + 192,
            Parameter);
        }
        if ( FsRtlIsEcpAcknowledged(*(PVOID *)EcpContextSize) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              26,
              WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
              *(_QWORD *)EcpContextSize);
          }
          if ( *(_BYTE *)(v25 + 379) )
            *(_BYTE *)(v25 + 380) = 1;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              27,
              WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
              *(_QWORD *)EcpContextSize);
          }
          *(_BYTE *)(v25 + 380) = 0;
          if ( FsRtlRemoveExtraCreateParameter(
                 DriverContext.ExtraCreateParameter,
                 &Smb2RkfGuidEcpIn,
                 (PVOID *)EcpContextSize,
                 v102) < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                28,
                WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
                *(_QWORD *)EcpContextSize,
                DriverContext.ExtraCreateParameter);
            }
          }
          else
          {
            FsRtlFreeExtraCreateParameter(*(PVOID *)EcpContextSize);
          }
          if ( a23 )
          {
            if ( byte_14004C339 < 0 )
            {
              v75 = *(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL);
              McTemplateK0hzr0hzr2hzr4_EtwWriteTransfer(
                *(_WORD *)(Pool2 + 208) >> 1,
                *(_WORD *)(v75 + 72) >> 1,
                v75,
                *(_WORD *)(v75 + 88) >> 1,
                *(_QWORD *)(v75 + 96),
                *(_WORD *)(v75 + 72) >> 1,
                *(_QWORD *)(v75 + 80),
                *(_WORD *)(Pool2 + 208) >> 1,
                *(_QWORD *)(Pool2 + 216));
            }
            *v71 = -1;
            Smb2CreateAbortAndCloseFile((PVOID)Pool2);
            inserted = -1073741772;
            goto LABEL_280;
          }
        }
      }
    }
    if ( (a22 || a23) && *(_BYTE *)(v25 + 380) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, v23);
      }
      inserted = Smb2RkfReadStateAndResume(v23, Pool2);
      if ( inserted < 0 )
      {
        *(_QWORD *)(Pool2 + 80) = -1;
        Smb2CreateAbortAndCloseFile((PVOID)Pool2);
LABEL_280:
        if ( P )
          Smb2DereferenceHandle(P);
        if ( v117 )
          Smb2DereferenceHandle(v117);
        if ( SourceString && v109 == 2 )
          ExFreePoolWithTag((PVOID)SourceString, 0);
        v91 = v105;
        if ( v98 == 1 )
        {
          SrvNetFreePool(v105->Buffer);
          *(_DWORD *)&v91->Length = 0;
        }
        if ( v97 )
          ExReleaseRundownProtection((PEX_RUNDOWN_REF)(**(_QWORD **)(*(_QWORD *)(v25 + 56) + 96LL) + 304LL));
        if ( inserted >= 0 )
          return (unsigned int)v111;
        if ( (*(_DWORD *)(*(_QWORD *)(v25 + 56) + 80LL) & 0x800) != 0 )
          inserted = Smb2CheckAbeError(v23, v91, v113, (unsigned int)inserted, Disposition);
        if ( v99 && inserted == -1073741772 )
          return (unsigned int)-1073741790;
        return (unsigned int)inserted;
      }
    }
    Smb2ReferenceFile(Pool2);
    ExAcquirePushLockSharedEx(*(_QWORD *)(*(_QWORD *)(v25 + 32) + 24LL) + 80LL, 0);
    v76 = *(_QWORD *)(*(_QWORD *)(v25 + 32) + 24LL);
    if ( *(_DWORD *)(v76 + 12) == 221 )
    {
      ExReleasePushLockSharedEx(v76 + 80, 0);
      inserted = -1073740964;
LABEL_209:
      *(_QWORD *)(Pool2 + 80) = -1;
LABEL_210:
      Smb2CreateAbortAndCloseFile((PVOID)Pool2);
      Smb2DereferenceFile((PVOID)Pool2);
      goto LABEL_280;
    }
    if ( *(_QWORD *)(Pool2 + 80) == -1 )
    {
      inserted = SrvAdminNodeGetNextId(Pool2 + 80);
      if ( inserted < 0 )
      {
LABEL_213:
        ExReleasePushLockSharedEx(*(_QWORD *)(*(_QWORD *)(v25 + 32) + 24LL) + 80LL, 0);
        goto LABEL_210;
      }
    }
    *(_DWORD *)(Pool2 + 92) = (unsigned __int16)SrvAdminNodeGetSignature();
    inserted = RfsHashTableInsertEx(*(_QWORD *)(*(_QWORD *)(v23[8] + 160LL) + 8LL), Pool2, (int)Pool2 + 80, 8, 0);
    if ( inserted < 0 )
    {
      ExReleasePushLockSharedEx(*(_QWORD *)(*(_QWORD *)(v25 + 32) + 24LL) + 80LL, 0);
      goto LABEL_209;
    }
    if ( *(_BYTE *)(v25 + 400) )
    {
      v77 = Pool2 + 796;
      v78 = *(_QWORD *)(v23[12] + 496LL);
      *(_OWORD *)(Pool2 + 796) = *(_OWORD *)(v25 + 384);
      *(_OWORD *)(Pool2 + 832) = *(_OWORD *)(v78 + 88);
      *(_QWORD *)(Pool2 + 816) = *(_QWORD *)(v25 + 408);
      *(_QWORD *)(Pool2 + 824) = *(_QWORD *)(v25 + 416);
      if ( (*(_DWORD *)(*(_QWORD *)(v25 + 56) + 80LL) & 0x4000) == 0 )
      {
        v79 = Smb2AppInstanceFileTableForNonCA;
        *(_BYTE *)(Pool2 + 794) = 1;
        goto LABEL_222;
      }
      if ( *(_BYTE *)(v25 + 377) || *(_BYTE *)(v25 + 378) )
      {
        v79 = Smb2AppInstanceFileTableForCA;
        v77 = Pool2 + 672;
        *(_BYTE *)(Pool2 + 793) = 1;
LABEL_222:
        if ( v79 )
        {
          inserted = RfsHashTableInsertEx((_DWORD)v79, Pool2, v77, 16, 0);
          if ( inserted < 0 )
            goto LABEL_213;
        }
      }
    }
    v80 = RfsTableInsert(*(PEX_SPIN_LOCK *)(*(_QWORD *)(v25 + 32) + 104LL));
    v81 = *(_QWORD *)(v25 + 32);
    if ( !v80 )
    {
      ExReleasePushLockSharedEx(*(_QWORD *)(v81 + 24) + 80LL, 0);
      inserted = -1073741670;
      goto LABEL_210;
    }
    _InterlockedAdd((volatile signed __int32 *)(v81 + 112), 1u);
    inserted = Smb2AdmRegisterFile(Pool2, v105, v25);
    if ( inserted < 0 )
      goto LABEL_213;
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(Pool2 + 136) + 440LL), 1u);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(Pool2 + 136) + 448LL), 1u);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v25 + 40) + 272LL), 1u);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v25 + 40) + 280LL), 1u);
    if ( *(_BYTE *)(Pool2 + 245) && *(_QWORD *)(*(_QWORD *)(Pool2 + 128) + 328LL) )
      _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(Pool2 + 136) + 528LL), 1u);
    if ( *(_BYTE *)(v25 + 377) )
    {
      if ( !*(_DWORD *)(*(_QWORD *)(v25 + 56) + 76LL) )
      {
        inserted = Smb2InsertFileIntoCachingTable(*(_QWORD *)(*(_QWORD *)(v25 + 152) + 144LL), Pool2, v25 + 336);
        if ( inserted < 0 )
          goto LABEL_213;
      }
    }
    *(_QWORD *)(Pool2 + 176) = *(_QWORD *)(v25 + 152);
    v82 = *(_QWORD *)(v25 + 152);
    v102[0] = -1073741823;
    Srv2ReferenceConnection(v82);
    if ( !*(_QWORD *)(v25 + 72) )
    {
      *(_QWORD *)(v25 + 72) = Pool2;
      Smb2ReferenceFile(Pool2);
    }
    inserted = Smb2SetStorQoSPolicy(Pool2, *(_QWORD *)(Pool2 + 128), *(_QWORD *)(v25 + 32));
    if ( inserted >= 0 )
    {
      *(_BYTE *)(Pool2 + 246) = 1;
    }
    else
    {
      v83 = *(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL);
      v84 = MEMORY[0xFFFFF78000000320];
      v85 = _InterlockedCompareExchange64((volatile signed __int64 *)(v83 + 424), 0, 0);
      while ( !v85 || v85 < v84 && v84 - v85 >= *(_QWORD *)(v83 + 432) )
      {
        v86 = v85;
        v85 = _InterlockedCompareExchange64((volatile signed __int64 *)(v83 + 424), v84, v85);
        if ( v85 == v86 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qZd(
              WPP_GLOBAL_Control->AttachedDevice,
              30,
              (unsigned int)WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
              Pool2,
              (__int64)v105,
              inserted);
          }
          if ( (byte_14004C33B & 2) != 0 )
          {
            v87 = *(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL);
            McTemplateK0qhzr1hzr3hzr5_EtwWriteTransfer(
              v105->Length >> 1,
              *(_WORD *)(v87 + 72) >> 1,
              *(_WORD *)(v87 + 88) >> 1,
              inserted,
              *(_WORD *)(v87 + 88) >> 1,
              *(_QWORD *)(v87 + 96),
              *(_WORD *)(v87 + 72) >> 1,
              *(_QWORD *)(v87 + 80),
              v105->Length >> 1,
              (__int64)v105->Buffer);
          }
          break;
        }
      }
      inserted = 0;
    }
    ExReleasePushLockSharedEx(*(_QWORD *)(*(_QWORD *)(v25 + 32) + 24LL) + 80LL, 0);
    if ( IoCheckFunctionAccess(*(_DWORD *)(Pool2 + 184), 0x11u, 1u, 0, 0, 0) >= 0 )
      *(_DWORD *)(Pool2 + 224) |= 0x2Cu;
    if ( IoCheckFunctionAccess(*(_DWORD *)(Pool2 + 184), 3u, 0, 0, 0, 0) >= 0 )
      *(_DWORD *)(Pool2 + 224) |= 1u;
    v88 = *(_DWORD *)(Pool2 + 184);
    if ( (v88 & 0x20) != 0 )
      *(_DWORD *)(Pool2 + 224) |= 1u;
    if ( IoCheckFunctionAccess(v88, 4u, 0, 0, 0, 0) < 0 )
    {
      *(_DWORD *)(Pool2 + 224) &= ~0x20u;
    }
    else
    {
      v89 = *(_DWORD *)(Pool2 + 184);
      if ( (v89 & 2) != 0 )
        *(_DWORD *)(Pool2 + 224) |= 2u;
      if ( (v89 & 4) != 0 )
        *(_DWORD *)(Pool2 + 224) |= 0x12u;
    }
    Smb2TransitionFileToActive((PVOID)Pool2);
    Smb2DereferenceFile((PVOID)Pool2);
LABEL_274:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Zq(WPP_GLOBAL_Control->AttachedDevice, v52, v51, (_DWORD)v105, Pool2);
    }
    if ( (v102[0] & 0x80000000) != 0 )
      goto LABEL_280;
    goto LABEL_279;
  }
  if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)(**(_QWORD **)(v45 + 96) + 304LL)) )
  {
    v97 = 1;
    BypassCSVHandle = (_QWORD *)Smb2ShareGetBypassCSVHandle(*(_QWORD *)(*(_QWORD *)(v25 + 56) + 96LL));
    v43 = P;
    v117 = BypassCSVHandle;
    if ( !BypassCSVHandle )
    {
      Smb2DereferenceHandle(P);
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)(**(_QWORD **)(*(_QWORD *)(v25 + 56) + 96LL) + 304LL));
      return 3221226094LL;
    }
    goto LABEL_97;
  }
  Smb2DereferenceHandle(P);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x14u)
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      (unsigned int)WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
      (_DWORD)a17,
      (__int64)a1);
  }
  return 3221226598LL;
}

```

## disassembly

```asm
0x14007a89c  push    rbp
0x14007a89e  push    rbx
0x14007a89f  push    rsi
0x14007a8a0  push    rdi
0x14007a8a1  push    r12
0x14007a8a3  push    r13
0x14007a8a5  push    r14
0x14007a8a7  push    r15
0x14007a8a9  lea     rbp, [rsp-2B8h]
0x14007a8b1  sub     rsp, 3C8h
0x14007a8b8  mov     rax, cs:__security_cookie
0x14007a8bf  xor     rax, rsp
0x14007a8c2  mov     [rbp+2F0h+var_50], rax
0x14007a8c9  mov     rsi, [rbp+2F0h+arg_80]
0x14007a8d0  xorps   xmm0, xmm0
0x14007a8d3  mov     rax, [rbp+2F0h+arg_30]
0x14007a8da  xor     r13d, r13d
0x14007a8dd  mov     rdi, [rbp+2F0h+arg_98]
0x14007a8e4  mov     r14, rcx
0x14007a8e7  mov     [rbp+2F0h+var_340], rax
0x14007a8eb  mov     rax, [rbp+2F0h+arg_38]
0x14007a8f2  mov     r15, [rsi+230h]
0x14007a8f9  mov     [rbp+2F0h+var_308], rax
0x14007a8fd  mov     rax, [rbp+2F0h+arg_48]
0x14007a904  mov     qword ptr [rbp+2F0h+EcpContextSize], rax
0x14007a908  mov     rax, [rbp+2F0h+arg_50]
0x14007a90f  mov     [rbp+2F0h+var_320], rax
0x14007a913  mov     rax, [rbp+2F0h+arg_60]
0x14007a91a  mov     [rbp+2F0h+var_310], rax
0x14007a91e  mov     rax, [rbp+2F0h+arg_88]
0x14007a925  mov     [rbp+2F0h+IoStatusBlock], rax
0x14007a929  xor     eax, eax
0x14007a92b  mov     word ptr [rbp+2F0h+var_2C8], ax
0x14007a92f  mov     rax, [rsi+60h]
0x14007a933  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.ObjectName], xmm0
0x14007a937  mov     [rbp+2F0h+DesiredAccess], edx
0x14007a93a  lea     rdx, [rbp+2F0h+var_290]
0x14007a93e  movups  xmmword ptr [rbp+2F0h+ObjectAttributes.Length], xmm0
0x14007a942  mov     [rbp+2F0h+FileHandle], r13
0x14007a946  movups  xmmword ptr [rbp+2F0h+ObjectAttributes+1Ch], xmm0
0x14007a94a  mov     [rbp+2F0h+var_290], r13
0x14007a94e  movups  xmmword ptr [rbp+2F0h+DestinationString.Length], xmm0
0x14007a955  mov     [rbp+2F0h+var_288], r13
0x14007a959  movups  xmmword ptr [rbp+2F0h+var_2E8.Size], xmm0
0x14007a95d  mov     [rbp+2F0h+var_36F], r13b
0x14007a961  movups  xmmword ptr [rbp+2F0h+var_2E8.DeviceObjectHint], xmm0
0x14007a965  mov     rbx, [rax+1F0h]
0x14007a96c  mov     [rbp+2F0h+var_334], r8d
0x14007a970  mov     [rbp+2F0h+var_348], rcx
0x14007a974  mov     [rbp+2F0h+var_360], r9d
0x14007a978  mov     [rbp+2F0h+var_280], rsi
0x14007a97c  mov     [rbp+2F0h+var_338], r13d
0x14007a980  call    cs:__imp_SrvLibGetBaseFileName
0x14007a987  nop     dword ptr [rax+rax+00h]
0x14007a98c  lea     rcx, [rbp+2F0h+var_290]
0x14007a990  call    cs:__imp_SrvLibIsDosDeviceName
0x14007a997  nop     dword ptr [rax+rax+00h]
0x14007a99c  test    al, al
0x14007a99e  jz      short loc_14007A9FE
0x14007a9a0  cmp     cs:Smb2AllowOpeningDosNames, r13b
0x14007a9a7  jnz     short loc_14007A9FE
0x14007a9a9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007a9b0  lea     rax, WPP_GLOBAL_Control
0x14007a9b7  cmp     rcx, rax
0x14007a9ba  jz      loc_14007AB62
0x14007a9c0  bt      dword ptr [rcx+2Ch], 14h
0x14007a9c5  jnb     loc_14007AB62
0x14007a9cb  lea     r12d, [r13+1]
0x14007a9cf  cmp     [rcx+29h], r12b
0x14007a9d3  jb      loc_14007AB62
0x14007a9d9  mov     rcx, [rcx+18h]
0x14007a9dd  lea     rax, [rbp+2F0h+var_290]
0x14007a9e1  lea     edx, [r13+0Ah]
0x14007a9e5  mov     [rsp+400h+AllocationSize], rax
0x14007a9ea  mov     r9, rsi
0x14007a9ed  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007a9f4  call    WPP_SF_qZ
0x14007a9f9  jmp     loc_14007AB62
0x14007a9fe  mov     rax, [r15+38h]
0x14007aa02  mov     r12d, 1
0x14007aa08  test    rax, rax
0x14007aa0b  jz      short loc_14007AA64
0x14007aa0d  cmp     [rax+4Ch], r12d
0x14007aa11  jnz     short loc_14007AA64
0x14007aa13  mov     rcx, [rbx+38h]
0x14007aa17  mov     rcx, [rcx+1E0h]
0x14007aa1e  call    cs:__imp_SrvNetCheckIfPipeAccessAllowed
0x14007aa25  nop     dword ptr [rax+rax+00h]
0x14007aa2a  test    al, al
0x14007aa2c  jnz     short loc_14007AA64
0x14007aa2e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007aa35  lea     rax, WPP_GLOBAL_Control
0x14007aa3c  cmp     rcx, rax
0x14007aa3f  jz      loc_14007AB62
0x14007aa45  bt      dword ptr [rcx+2Ch], 14h
0x14007aa4a  jnb     loc_14007AB62
0x14007aa50  cmp     [rcx+29h], r12b
0x14007aa54  jb      loc_14007AB62
0x14007aa5a  lea     edx, [r12+0Ah]
0x14007aa5f  jmp     loc_14007AB4F
0x14007aa64  mov     dword ptr [rbp+2F0h+var_2E8+2], r13d
0x14007aa68  xorps   xmm0, xmm0
0x14007aa6b  mov     word ptr [rbp+2F0h+var_2E8+6], r13w
0x14007aa70  mov     eax, 28h ; '('
0x14007aa75  mov     r13d, [rbp+2F0h+arg_28]
0x14007aa7c  mov     [rbp+2F0h+var_2E8.Size], ax
0x14007aa80  mov     [rbp+2F0h+var_2C8], r12
0x14007aa84  mov     [rbp+2F0h+var_2E8.ExtraCreateParameter], rdi
0x14007aa88  movdqu  xmmword ptr [rbp+2F0h+var_2E8.DeviceObjectHint], xmm0
0x14007aa8d  test    r13d, 102080h
0x14007aa94  jz      short loc_14007AAA0
0x14007aa96  mov     eax, 0C00000BBh
0x14007aa9b  jmp     loc_14007C280
0x14007aaa0  mov     r8d, [rbp+2F0h+DesiredAccess]
0x14007aaa4  lea     rax, [rbp+2F0h+var_338]
0x14007aaa8  mov     ebx, r13d
0x14007aaab  mov     [rsp+400h+AllocationSize], rax
0x14007aab0  shr     ebx, 1
0x14007aab2  lea     r9, [rbp+2F0h+var_360]
0x14007aab6  not     ebx
0x14007aab8  mov     rdx, r14
0x14007aabb  and     ebx, 4
0x14007aabe  mov     rcx, rsi
0x14007aac1  or      ebx, 0FFFEFFCBh
0x14007aac7  call    Smb2CheckShareAccess
0x14007aacc  mov     edi, eax
0x14007aace  test    eax, eax
0x14007aad0  jns     short loc_14007AB15
0x14007aad2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007aad9  lea     rax, WPP_GLOBAL_Control
0x14007aae0  cmp     rcx, rax
0x14007aae3  jz      short loc_14007AB0E
0x14007aae5  bt      dword ptr [rcx+2Ch], 14h
0x14007aaea  jnb     short loc_14007AB0E
0x14007aaec  cmp     [rcx+29h], r12b
0x14007aaf0  jb      short loc_14007AB0E
0x14007aaf2  mov     rcx, [rcx+18h]
0x14007aaf6  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007aafd  mov     edx, 0Ch
0x14007ab02  mov     dword ptr [rsp+400h+AllocationSize], edi
0x14007ab06  mov     r9, rsi
0x14007ab09  call    WPP_SF_qD
0x14007ab0e  mov     eax, edi
0x14007ab10  jmp     loc_14007C280
0x14007ab15  and     ebx, r13d
0x14007ab18  mov     [rbp+2F0h+var_34C], ebx
0x14007ab1b  bt      ebx, 0Ch
0x14007ab1f  jnb     short loc_14007AB6C
0x14007ab21  test    [rbp+2F0h+var_338], 10000h
0x14007ab28  jnz     short loc_14007AB6C
0x14007ab2a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ab31  lea     rax, WPP_GLOBAL_Control
0x14007ab38  cmp     rcx, rax
0x14007ab3b  jz      short loc_14007AB62
0x14007ab3d  bt      dword ptr [rcx+2Ch], 14h
0x14007ab42  jnb     short loc_14007AB62
0x14007ab44  cmp     [rcx+29h], r12b
0x14007ab48  jb      short loc_14007AB62
0x14007ab4a  mov     edx, 0Dh
0x14007ab4f  mov     rcx, [rcx+18h]
0x14007ab53  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007ab5a  mov     r9, rsi
0x14007ab5d  call    WPP_SF_q
0x14007ab62  mov     eax, 0C0000022h
0x14007ab67  jmp     loc_14007C280
0x14007ab6c  mov     r8d, [rbp+2F0h+arg_20]
0x14007ab73  xor     r13d, r13d
0x14007ab76  mov     [rbp+2F0h+var_36E], r13b
0x14007ab7a  cmp     r8d, r12d
0x14007ab7d  jz      loc_14007ACA6
0x14007ab83  test    r12b, bl
0x14007ab86  jz      short loc_14007AC01
0x14007ab88  test    bl, 40h
0x14007ab8b  jz      short loc_14007ABC6
0x14007ab8d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ab94  lea     rax, WPP_GLOBAL_Control
0x14007ab9b  cmp     rcx, rax
0x14007ab9e  jz      loc_14007AC5A
0x14007aba4  bt      dword ptr [rcx+2Ch], 14h
0x14007aba9  jnb     loc_14007AC5A
0x14007abaf  cmp     [rcx+29h], r12b
0x14007abb3  jb      loc_14007AC5A
0x14007abb9  lea     edx, [r13+0Eh]
0x14007abbd  mov     dword ptr [rsp+400h+AllocationSize], ebx
0x14007abc1  jmp     loc_14007AC47
0x14007abc6  mov     eax, r8d
0x14007abc9  sub     eax, 2
0x14007abcc  jz      short loc_14007ABFA
0x14007abce  cmp     eax, r12d
0x14007abd1  jz      short loc_14007ABFA
0x14007abd3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007abda  lea     rax, WPP_GLOBAL_Control
0x14007abe1  cmp     rcx, rax
0x14007abe4  jz      short loc_14007AC5A
0x14007abe6  bt      dword ptr [rcx+2Ch], 14h
0x14007abeb  jnb     short loc_14007AC5A
0x14007abed  cmp     [rcx+29h], r12b
0x14007abf1  jb      short loc_14007AC5A
0x14007abf3  mov     edx, 0Fh
0x14007abf8  jmp     short loc_14007AC42
0x14007abfa  mov     edi, 4
0x14007abff  jmp     short loc_14007AC70
0x14007ac01  mov     eax, r8d
0x14007ac04  test    r8d, r8d
0x14007ac07  jz      short loc_14007AC6B
0x14007ac09  sub     eax, 2
0x14007ac0c  jz      short loc_14007AC64
0x14007ac0e  sub     eax, r12d
0x14007ac11  jz      short loc_14007AC64
0x14007ac13  sub     eax, r12d
0x14007ac16  jz      short loc_14007AC64
0x14007ac18  cmp     eax, r12d
0x14007ac1b  jz      short loc_14007AC64
0x14007ac1d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ac24  lea     rax, WPP_GLOBAL_Control
0x14007ac2b  cmp     rcx, rax
0x14007ac2e  jz      short loc_14007AC5A
0x14007ac30  bt      dword ptr [rcx+2Ch], 14h
0x14007ac35  jnb     short loc_14007AC5A
0x14007ac37  cmp     [rcx+29h], r12b
0x14007ac3b  jb      short loc_14007AC5A
0x14007ac3d  mov     edx, 10h
0x14007ac42  mov     dword ptr [rsp+400h+AllocationSize], r8d
0x14007ac47  mov     rcx, [rcx+18h]
0x14007ac4b  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007ac52  mov     r9, rsi
0x14007ac55  call    WPP_SF_qD
0x14007ac5a  mov     eax, 0C000000Dh
0x14007ac5f  jmp     loc_14007C280
0x14007ac64  mov     edi, 2
0x14007ac69  jmp     short loc_14007AC70
0x14007ac6b  mov     edi, 10002h
0x14007ac70  lea     r9, [rbp+2F0h+var_360]
0x14007ac74  mov     [rsp+400h+AllocationSize], r13
0x14007ac79  mov     r8d, edi
0x14007ac7c  mov     rdx, r14
0x14007ac7f  mov     rcx, rsi
0x14007ac82  call    Smb2CheckShareAccess
0x14007ac87  mov     [rbp+2F0h+var_358], eax
0x14007ac8a  test    eax, eax
0x14007ac8c  jns     short loc_14007ACA6
0x14007ac8e  mov     r8d, [rbp+2F0h+arg_20]
0x14007ac95  cmp     r8d, 3
0x14007ac99  jnz     short loc_14007ACD3
0x14007ac9b  mov     [rbp+2F0h+var_36E], r12b
0x14007ac9f  mov     [rbp+2F0h+arg_20], r12d
0x14007aca6  lea     rdi, WPP_GLOBAL_Control
0x14007acad  mov     [rbp+2F0h+P], r13
0x14007acb1  mov     [rbp+2F0h+var_2F0], r13
0x14007acb5  mov     [rbp+2F0h+SourceString], r13
0x14007acb9  mov     [rbp+2F0h+var_330], r13d
0x14007acbd  mov     [rbp+2F0h+var_370], r13b
0x14007acc1  test    [rbp+2F0h+arg_58], r12b
0x14007acc8  jz      short loc_14007AD1C
0x14007acca  mov     [rbp+2F0h+ObjectAttributes.ObjectName], r14
0x14007acce  jmp     loc_14007AEF6
0x14007acd3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007acda  lea     rax, WPP_GLOBAL_Control
0x14007ace1  cmp     rcx, rax
0x14007ace4  jz      short loc_14007AD14
0x14007ace6  bt      dword ptr [rcx+2Ch], 14h
0x14007aceb  jnb     short loc_14007AD14
0x14007aced  cmp     [rcx+29h], r12b
0x14007acf1  jb      short loc_14007AD14
0x14007acf3  mov     rcx, [rcx+18h]
0x14007acf7  mov     edx, 11h
0x14007acfc  mov     [rsp+400h+FileAttributes], edi
0x14007ad00  mov     r9, rsi
0x14007ad03  mov     dword ptr [rsp+400h+AllocationSize], r8d
0x14007ad08  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007ad0f  call    WPP_SF_qDD
0x14007ad14  mov     eax, [rbp+2F0h+var_358]
0x14007ad17  jmp     loc_14007C280
0x14007ad1c  mov     rcx, [r15+38h]
0x14007ad20  mov     qword ptr [rbp+2F0h+var_358], rcx
0x14007ad24  cmp     [rcx+4Ch], r12d
0x14007ad28  jnz     loc_14007AF15
0x14007ad2e  xorps   xmm0, xmm0
0x14007ad31  movups  [rbp+2F0h+var_260], xmm0
0x14007ad38  test    dword ptr [rcx+54h], 4000000h
0x14007ad3f  jz      short loc_14007AD9F
0x14007ad41  mov     rcx, r14
0x14007ad44  call    cs:__imp_SrvAdminAllowClusterPipeAccess
0x14007ad4b  nop     dword ptr [rax+rax+00h]
0x14007ad50  test    al, al
0x14007ad52  jnz     short loc_14007AD9B
0x14007ad54  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007ad5b  lea     rax, WPP_GLOBAL_Control
0x14007ad62  cmp     rcx, rax
0x14007ad65  jz      short loc_14007AD91
0x14007ad67  bt      dword ptr [rcx+2Ch], 14h
0x14007ad6c  jnb     short loc_14007AD91
0x14007ad6e  cmp     [rcx+29h], r12b
0x14007ad72  jb      short loc_14007AD91
0x14007ad74  mov     rcx, [rcx+18h]
0x14007ad78  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007ad7f  mov     edx, 12h
0x14007ad84  mov     [rsp+400h+AllocationSize], r14
0x14007ad89  mov     r9, rsi
0x14007ad8c  call    WPP_SF_qZ
  ... truncated ...
```
