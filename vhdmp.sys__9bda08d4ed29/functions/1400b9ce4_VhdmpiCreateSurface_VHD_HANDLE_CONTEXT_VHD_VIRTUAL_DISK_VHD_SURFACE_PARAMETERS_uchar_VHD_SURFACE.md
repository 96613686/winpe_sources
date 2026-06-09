# VhdmpiCreateSurface(_VHD_HANDLE_CONTEXT *,_VHD_VIRTUAL_DISK *,VHD_SURFACE_PARAMETERS *,uchar *,_VHD_SURFACE * *)

- ea: `0x1400b9ce4`
- end: `0x1400ba8e2`
- name: `?VhdmpiCreateSurface@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_VIRTUAL_DISK@@PEAUVHD_SURFACE_PARAMETERS@@PEAEPEAPEAU_VHD_SURFACE@@@Z`
- size: `3070`
- prototype: `int(struct _VHD_HANDLE_CONTEXT *, struct _VHD_VIRTUAL_DISK *, struct VHD_SURFACE_PARAMETERS *, unsigned __int8 *, struct _VHD_SURFACE **)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400bc254`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x14001ed6c`
- `0x1400205f0`
- `0x1400214b4`
- `0x140022654`
- `0x140023980`
- `0x140024004`
- `0x140026930`
- `0x1400277d4`
- `0x14002ea1c`
- `0x140035e94`
- `0x14003601c`
- `0x140036284`
- `0x14004e2c8`
- `0x14005dbb0`
- `0x14005dc30`
- `0x14005de00`
- `0x1400adf48`
- `0x1400b9b24`
- `0x1400b9ce4`
- `0x1400bab44`
- `0x1400bac40`
- `0x1400bba44`
- `0x1400bbae4`
- `0x1400bc0f8`
- `0x1400bcf28`
- `0x1400cfe90`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x1400ba694`
- `ntoskrnl!ZwFsControlFile` at `0x1400ba694`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ba6b2`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ba6b2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b9ebc`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b9ebc`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b9ef1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b9ef1`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400ba251`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400ba251`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba282`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba282`
- `FSDEPENDS!DependentFSCheckStoragePrivilege` at `0x1400b9edf`
- `FSDEPENDS!DependentFSCheckStoragePrivilege` at `0x1400b9edf`
- `FSDEPENDS!DependentFSCheckFileHandle` at `0x1400ba05a`
- `FSDEPENDS!DependentFSCheckFileHandle` at `0x1400ba05a`

## string_xrefs

- `0x1400b9dc0`: `VhdmpiCreateSurface`
- `0x1400b9e25`: `VhdmpiCreateSurface`
- `0x1400b9f44`: `VhdmpiCreateSurface`
- `0x1400ba0c0`: `VhdmpiCreateSurface`
- `0x1400ba219`: `VhdmpiCreateSurface`
- `0x1400ba2ce`: `VhdmpiCreateSurface`
- `0x1400ba4bf`: `VhdmpiCreateSurface`
- `0x1400ba567`: `VhdmpiCreateSurface`
- `0x1400ba6fd`: `VhdmpiCreateSurface`
- `0x1400ba7a8`: `VhdmpiCreateSurface`
- `0x1400b9e13`: `Cannot loopback mount empty ISO backing store.`
- `0x1400b9e86`: `Attempting to mount a PMEM-compatible virtual disk as a VM SCSI device.`
- `0x1400b9f38`: `VhdmpiSurfaceVirtualDisk : CheckStoragePrivilege failed for disk %p, returned status 0x%x`
- `0x1400ba2b7`: `VhdmpiSurfaceVirtualDisk: could not allocate nonpaged buffer for ACL.`
- `0x1400ba4ab`: `VhdmpiSurfaceVirtualDisk: VhdmpiGetFileACL returned 0x%08x.`
- `0x1400ba6e9`: `FSCTL_SET_BOOTLOADER_ACCESSED failed: 0x%08x`
- `0x1400ba79d`: `ExpandOnMount failed: 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiCreateSurface(
        struct _VHD_HANDLE_CONTEXT *a1,
        struct _VHD_VIRTUAL_DISK *a2,
        struct VHD_SURFACE_PARAMETERS *a3,
        unsigned __int8 *a4,
        struct _VHD_SURFACE **a5)
{
  __int64 v5; // r15
  int v6; // r13d
  char *v7; // rsi
  struct _VHD_VIRTUAL_DISK *v8; // r12
  __int64 v9; // rax
  int Guid; // ebx
  unsigned __int8 (__fastcall *v11)(__int64, _QWORD); // rax
  char v12; // r14
  struct _VHD_VIRTUAL_DISK *v13; // r14
  __int64 v14; // rdx
  HANDLE v15; // rax
  char v16; // r13
  char v17; // di
  int Surface; // eax
  struct VHD_SURFACE_PARAMETERS *v19; // rbx
  unsigned int v20; // eax
  void *Pool2; // rax
  struct _VHD_VIRTUAL_DISK *v22; // rdx
  char v23; // cl
  char IsRemoteSmbFile; // al
  struct VHD_SURFACE_PARAMETERS *v25; // r13
  _OWORD *v26; // r12
  int v27; // r8d
  __int64 *v28; // rcx
  int v29; // r8d
  NTSTATUS Status; // r8d
  int v31; // r8d
  int v32; // eax
  __int64 i; // rbx
  unsigned __int16 v34; // dx
  char *v35; // rax
  ULONG FsControlCode[2]; // [rsp+28h] [rbp-D8h]
  char v38; // [rsp+50h] [rbp-B0h]
  char v39; // [rsp+53h] [rbp-ADh]
  char v41; // [rsp+60h] [rbp-A0h]
  HANDLE FileHandle; // [rsp+68h] [rbp-98h]
  int v44; // [rsp+78h] [rbp-88h] BYREF
  void *v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h]
  PVOID DeferredContext; // [rsp+90h] [rbp-70h] BYREF
  struct VHD_SURFACE_PARAMETERS *v48; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v49; // [rsp+A0h] [rbp-60h]
  struct _VHD_SURFACE **v50; // [rsp+A8h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v53; // [rsp+E0h] [rbp-20h] BYREF
  int v54; // [rsp+F0h] [rbp-10h]

  v5 = *((_QWORD *)a2 + 18);
  v6 = *(_DWORD *)a3;
  v7 = 0;
  v50 = a5;
  v54 = 0;
  FileHandle = 0;
  v45 = 0;
  v8 = a2;
  v46 = 0;
  IoStatusBlock = 0;
  v44 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v49 = a4;
  v48 = a3;
  v53 = 0;
  v9 = *(_QWORD *)v5;
  DeferredContext = 0;
  v39 = v6 & 1;
  if ( (char **)v9 == &IsoParser && (v6 & 1) == 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents("VhdmpiCreateSurface", 0xAC1u, 2u, 0x10u, "VhdmpiSurfaceVirtualDisk: invalid flags for ISO");
    return (unsigned int)-1073741811;
  }
  if ( (__int64 *)v5 == &VhdmpiEmptyISOBackingStore && (v6 & 8) == 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents("VhdmpiCreateSurface", 0xAD2u, 2u, 0x10u, "Cannot loopback mount empty ISO backing store.");
    return (unsigned int)-1073741637;
  }
  if ( *((_BYTE *)a2 + 92) )
  {
    v11 = *(unsigned __int8 (__fastcall **)(__int64, _QWORD))(v9 + 560);
    if ( v11 )
    {
      if ( v11(v5, 0) )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
          TraceEvents(
            "VhdmpiCreateSurface",
            0xAE3u,
            2u,
            0x10u,
            "Attempting to mount a PMEM-compatible virtual disk as a VM SCSI device.");
        return (unsigned int)-1073741637;
      }
    }
  }
  v12 = 0;
  v38 = 0;
  if ( !*((_BYTE *)v8 + 80) && (v6 & 8) == 0 )
  {
    VhdmpiGetVirtualStorageType(v8, &v53);
    SeCaptureSubjectContext(&SubjectContext);
    Guid = DependentFSCheckStoragePrivilege(&SubjectContext, &v53, ((unsigned int)!(v6 & 1) + 1) << 16);
    SeReleaseSubjectContext(&SubjectContext);
    if ( Guid < 0 )
    {
      if ( (unsigned int)dword_1400876D0 <= 2 )
      {
        v13 = v8;
      }
      else
      {
        v13 = a2;
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 64) )
          TraceEvents(
            "VhdmpiCreateSurface",
            0xB01u,
            2u,
            0x40u,
            "VhdmpiSurfaceVirtualDisk : CheckStoragePrivilege failed for disk %p, returned status 0x%x",
            a2,
            Guid);
      }
LABEL_169:
      if ( v7 )
        VhdmpiFreeVirtualDiskSurface((char)v7);
      goto LABEL_172;
    }
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v5 + 112LL))(v5)
    && (*((_DWORD *)a1 + 1) & 2) != 0
    && !*((_BYTE *)v8 + 87) )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents(
        "VhdmpiCreateSurface",
        0xB16u,
        2u,
        0x10u,
        "VhdmpiSurfaceVirtualDisk: cannot surface 'No Parents' diff disk");
    return (unsigned int)-1073741637;
  }
  v41 = 0;
  if ( (__int64 *)v5 == &VhdmpiEmptyISOBackingStore )
    goto LABEL_58;
  LOBYTE(v14) = 1;
  Guid = VhdmpiPinFile(v5, v14, &v45);
  if ( Guid < 0 )
  {
    v15 = v45;
    goto LABEL_42;
  }
  VhdmpiGetVirtualStorageType(v8, &v53);
  FileHandle = v45;
  Guid = DependentFSCheckFileHandle(v45, v46, *(_DWORD *)(v5 + 220) | ((v6 & 8) != 0 ? 0x200 : 0), &v53, 0, 0, &v44);
  if ( Guid < 0 )
    goto LABEL_40;
  if ( (v6 & 8) != 0 || (Guid = VhdmpiVerifyBackingStorePresence(v8), Guid >= 0) )
  {
LABEL_58:
    VhdmpiAcquirePassiveLock((char *)v8 + 184);
    v12 = 1;
    v38 = 1;
    Guid = VhdmpiValidateProposedOperationUnderLock(a1, v8, 0x4EFu, ((unsigned __int8)!(v6 & 1) << 9) + 256);
    if ( Guid < 0 )
    {
      if ( (unsigned int)dword_1400876D0 > 2 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
          TraceEvents(
            "VhdmpiCreateSurface",
            0xB8Fu,
            2u,
            0x10u,
            "VhdmpiSurfaceVirtualDisk: conflicts with existing meta-operation");
        v12 = 1;
      }
      goto LABEL_41;
    }
    Surface = VhdmpiAllocateSurface((struct _VHD_SURFACE **)&DeferredContext);
    v7 = (char *)DeferredContext;
    Guid = Surface;
    if ( Surface < 0 )
      goto LABEL_73;
    if ( v39 )
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)DeferredContext + 10);
    v19 = v48;
    v20 = *((_DWORD *)v48 + 4);
    if ( v20 )
    {
      Pool2 = (void *)ExAllocatePool2(64, v20, 2017740886);
      *((_QWORD *)v7 + 61) = Pool2;
      if ( !Pool2 )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
          TraceEvents(
            "VhdmpiCreateSurface",
            0xBAFu,
            2u,
            0x10u,
            "VhdmpiSurfaceVirtualDisk: could not allocate nonpaged buffer for ACL.");
        Guid = -1073741670;
        goto LABEL_72;
      }
      memmove(Pool2, *((const void **)v19 + 1), *((unsigned int *)v19 + 4));
      *((_DWORD *)v7 + 124) = *((_DWORD *)v19 + 4);
    }
    else
    {
      v22 = a2;
      if ( *((_BYTE *)a2 + 80) || (__int64 *)v5 == &VhdmpiEmptyISOBackingStore || (v6 & 0x18) != 0 )
      {
        *((_QWORD *)v7 + 61) = 0;
        *((_DWORD *)v7 + 124) = 0;
        goto LABEL_77;
      }
      if ( (int)VhdmpiGetFileSecurityDescriptor(v46, v7 + 488, v7 + 496) < 0 )
      {
        if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
          TraceEvents(
            "VhdmpiCreateSurface",
            0xBCFu,
            2u,
            0x10u,
            "VhdmpiSurfaceVirtualDisk: VhdmpiGetFileACL returned 0x%08x.",
            v27);
        *((_DWORD *)v7 + 124) = 0;
      }
    }
    v22 = a2;
LABEL_77:
    v23 = v6 & 1;
    if ( v39 )
      *((_DWORD *)v7 + 14) |= 0x100u;
    if ( (v6 & 8) != 0 )
      *((_DWORD *)v7 + 14) |= 0x200u;
    if ( (v6 & 2) != 0 )
      *((_DWORD *)v7 + 14) |= 0x800u;
    if ( (v6 & 4) != 0 )
      *((_DWORD *)v7 + 14) |= 0x1000u;
    if ( (v6 & 0x400) != 0 )
      *((_DWORD *)v7 + 14) |= 0x2000u;
    if ( (v6 & 0x40) != 0 )
      *((_DWORD *)v7 + 14) |= 0x400u;
    if ( (v6 & 0x20) != 0 )
    {
      IsRemoteSmbFile = VhdmpiIsRemoteSmbFile(v5 + 72, v22);
      v23 = v6 & 1;
      if ( !IsRemoteSmbFile )
        *((_DWORD *)v7 + 14) |= 0x200000u;
    }
    v25 = v48;
    if ( (*((_DWORD *)v48 + 1) & 1) != 0 )
      *((_DWORD *)v7 + 14) |= 0x4000u;
    if ( (*((_DWORD *)v25 + 1) & 4) != 0 )
      *((_DWORD *)v7 + 14) |= 0x8000u;
    if ( (*((_DWORD *)v25 + 1) & 0x20) != 0 )
      *((_DWORD *)v7 + 14) |= 0x20000u;
    if ( (*((_DWORD *)v25 + 1) & 0x40) != 0 )
      *((_DWORD *)v7 + 14) |= 0x40000u;
    if ( (*((_DWORD *)v25 + 1) & 0x80u) != 0 )
      *((_DWORD *)v7 + 14) |= 0x80000u;
    if ( (*((_DWORD *)v25 + 1) & 0x100) != 0 )
      *((_DWORD *)v7 + 14) |= 0x100000u;
    if ( !v23 && (unsigned __int8)VhdmpiIsRctEnabled(v5, v22) )
      v7[64] = 1;
    *((_DWORD *)v7 + 15) = *((_DWORD *)v25 + 5);
    if ( (*((_DWORD *)v25 + 1) & 0x10) == 0 )
      goto LABEL_127;
    v26 = (_OWORD *)((char *)v22 + 2504);
    *(_OWORD *)((char *)v22 + 2504) = 0;
    if ( *(_OWORD *)((char *)v25 + 24) == *(_OWORD *)&VhdmpZeroGuid )
    {
      Guid = DvGenerateGuid((PUCHAR)v22 + 2504);
      if ( Guid < 0 )
        goto LABEL_72;
      v22 = a2;
    }
    else
    {
      *v26 = *(_OWORD *)((char *)v25 + 24);
    }
    v28 = (__int64 *)*((_QWORD *)v22 + 18);
    if ( v28 == &VhdmpiEmptyISOBackingStore )
    {
LABEL_127:
      v8 = a2;
    }
    else
    {
      Guid = VhdmpiInitializeQoSPolicyForBackingStoreChain(v28, 0, v26);
      if ( Guid < 0 )
      {
        if ( (unsigned int)dword_1400876D0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4) )
          TraceEvents(
            "VhdmpiCreateSurface",
            0xC4Du,
            v29,
            v29 + 1,
            "VhdmpiSurfaceVirtualDisk: Failed to initialize QoS policy: 0x%08x",
            Guid);
        goto LABEL_72;
      }
      v8 = a2;
      *((_BYTE *)a2 + 91) = 1;
    }
    *((_QWORD *)v7 + 190) = 0;
    *((_QWORD *)v7 + 189) = VhdmpiIsoAsyncNotify;
    *((_QWORD *)v7 + 188) = v8;
    if ( (*((_DWORD *)v25 + 1) & 2) != 0 )
    {
      *((_QWORD *)a1 + 36) = *((_QWORD *)v25 + 8);
      *((_QWORD *)v7 + 189) = *((_QWORD *)v25 + 6);
      *((_QWORD *)v7 + 190) = *((_QWORD *)v25 + 7);
      *((_QWORD *)v7 + 188) = *((_QWORD *)v25 + 5);
      *((_DWORD *)v7 + 14) |= 0x10000u;
    }
    if ( (*((_DWORD *)v7 + 14) & 0x1000) == 0 )
    {
      v16 = 0;
      goto LABEL_135;
    }
    Guid = VhdmpiCopySecurityContext((PSECURITY_SUBJECT_CONTEXT)(v7 + 1464), (__int64)a1 + 16);
    if ( Guid >= 0 )
    {
      v16 = 1;
      v8 = a2;
      Guid = VhdmpiAcquireSurfaceBackingStoreChainAccess(
               (struct VHD_SECURITY_CONTEXT *)(v7 + 1464),
               (struct _VHD_BACKING_STORE_HEADER *)v5);
      if ( Guid < 0 )
      {
        v17 = 0;
        v12 = 1;
        goto LABEL_74;
      }
LABEL_135:
      if ( (__int64 *)v5 != &VhdmpiEmptyISOBackingStore )
      {
        if ( *((_BYTE *)v8 + 80) )
        {
          Status = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x9004Fu, 0, 0, 0, 0);
          if ( Status == 259 )
          {
            ZwWaitForSingleObject(FileHandle, 0, 0);
            Status = IoStatusBlock.Status;
          }
          if ( Status < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
            TraceEvents("VhdmpiCreateSurface", 0xCAAu, 2u, 0x10u, "FSCTL_SET_BOOTLOADER_ACCESSED failed: 0x%08x", v31);
        }
        VhdmpiFileWrapperUnpinFile(v5 + 72, 1);
        v32 = *((_DWORD *)v7 + 14);
        FileHandle = 0;
        if ( (v32 & 0x200) == 0 )
        {
          if ( (v32 & 0x100) == 0 )
            VhdmpiFileWrapperNotifyCSVFSLoopbackMount(v5 + 72);
          for ( i = v5; i; i = *(_QWORD *)(i + 1144) )
            VhdmpiFileWrapperNotifyCSVFSLoopbackMount(i + 72);
          v41 = 1;
        }
      }
      Guid = VhdmpiExpandOnMount(v8, (struct _VHD_SURFACE *)v7);
      if ( Guid >= 0 )
      {
        Guid = VhdmpiInitializeScsiStateForSurface(v7, v8);
        if ( Guid >= 0 )
        {
          Guid = VhdmpiRegisterDiskAddress(v7, a1);
          if ( Guid >= 0 )
          {
            ++*((_DWORD *)v8 + 38);
            if ( (*((_DWORD *)v7 + 14) & 0x1000) != 0 )
            {
              VhdmpiReleaseSurfaceBackingStoreChainAccess(
                (struct _VHD_HANDLE_CONTEXT *)((char *)a1 + 16),
                (struct _VHD_BACKING_STORE_HEADER *)v5);
              *v49 = 0;
            }
            v17 = 0;
            v16 = 0;
            Guid = 0;
            *v50 = (struct _VHD_SURFACE *)v7;
            goto LABEL_155;
          }
          if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
          {
LABEL_154:
            v17 = v16;
LABEL_155:
            v12 = 1;
            goto LABEL_74;
          }
          v34 = 3329;
          v35 = "RegisterDiskAddress failed: 0x%08x";
        }
        else
        {
          if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
            goto LABEL_154;
          v34 = 3308;
          v35 = "VhdmpiInitializeScsiStateForSurface failed: 0x%08x";
        }
      }
      else
      {
        if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
          goto LABEL_154;
        v34 = 3296;
        v35 = "ExpandOnMount failed: 0x%08x";
      }
      FsControlCode[0] = Guid;
      TraceEvents("VhdmpiCreateSurface", v34, 2u, 0x10u, v35, *(_QWORD *)FsControlCode);
      goto LABEL_154;
    }
LABEL_72:
    v8 = a2;
    v12 = 1;
LABEL_73:
    v17 = 0;
    v16 = 0;
LABEL_74:
    v15 = FileHandle;
    goto LABEL_43;
  }
  if ( (unsigned int)dword_1400876D0 > 2 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 64) )
      TraceEvents(
        "VhdmpiCreateSurface",
        0xB6Eu,
        2u,
        0x40u,
        "VhdmpiSurfaceVirtualDisk: backing store presence could not be verified (0x%08x)",
        Guid);
    v8 = a2;
  }
LABEL_40:
  v12 = 0;
LABEL_41:
  v15 = FileHandle;
LABEL_42:
  v16 = 0;
  v17 = 0;
LABEL_43:
  if ( v15 && (__int64 *)v5 != &VhdmpiEmptyISOBackingStore )
    VhdmpiFileWrapperUnpinFile(v5 + 72, 1);
  if ( v17 )
    VhdmpiReleaseSurfaceBackingStoreChainAccess(
      (struct VHD_SECURITY_CONTEXT *)(v7 + 1464),
      *((struct _VHD_BACKING_STORE_HEADER **)v8 + 18));
  if ( v16 )
    VhdmpiCleanupSecurityContext(v7 + 1464);
  if ( Guid < 0 )
  {
    v38 = v12;
    if ( !v41 )
      goto LABEL_167;
    if ( (*((_DWORD *)v7 + 14) & 0x100) == 0 )
      VhdmpiFileWrapperNotifyCSVFSLoopbackMount(v5 + 72);
    if ( v5 )
    {
      do
      {
        VhdmpiFileWrapperNotifyCSVFSLoopbackMount(v5 + 72);
        v5 = *(_QWORD *)(v5 + 1144);
      }
      while ( v5 );
    }
    else
    {
LABEL_167:
      v38 = v12;
    }
    v13 = a2;
    goto LABEL_169;
  }
  v13 = a2;
LABEL_172:
  if ( v38 )
    VhdmpiReleasePassiveLock((char *)v13 + 184);
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x1400b9ce4  push    rbp
0x1400b9ce6  push    rbx
0x1400b9ce7  push    rsi
0x1400b9ce8  push    rdi
0x1400b9ce9  push    r12
0x1400b9ceb  push    r13
0x1400b9ced  push    r14
0x1400b9cef  push    r15
0x1400b9cf1  lea     rbp, [rsp-8]
0x1400b9cf6  sub     rsp, 108h
0x1400b9cfd  mov     rax, cs:__security_cookie
0x1400b9d04  xor     rax, rsp
0x1400b9d07  mov     [rbp+40h+var_48], rax
0x1400b9d0b  mov     rax, [rbp+40h+arg_20]
0x1400b9d0f  xorps   xmm0, xmm0
0x1400b9d12  mov     r15, [rdx+90h]
0x1400b9d19  xorps   xmm1, xmm1
0x1400b9d1c  mov     r13d, [r8]
0x1400b9d1f  xor     esi, esi
0x1400b9d21  mov     [rbp+40h+var_98], rax
0x1400b9d25  mov     bl, r13b
0x1400b9d28  xor     eax, eax
0x1400b9d2a  mov     [rsp+140h+var_D0], rcx
0x1400b9d2f  and     bl, 1
0x1400b9d32  mov     [rbp+40h+var_50], eax
0x1400b9d35  mov     [rsp+140h+FileHandle], rax
0x1400b9d3a  lea     rcx, IsoParser
0x1400b9d41  mov     [rbp+40h+var_C0], rax
0x1400b9d45  mov     r12, rdx
0x1400b9d48  mov     [rbp+40h+var_B8], rax
0x1400b9d4c  movups  xmmword ptr [rbp+40h+var_90], xmm0
0x1400b9d50  mov     [rsp+140h+var_C8], 0
0x1400b9d58  movups  xmmword ptr [rbp+40h+SubjectContext.ClientToken], xmm1
0x1400b9d5c  mov     [rbp+40h+var_A0], r9
0x1400b9d60  movups  xmmword ptr [rbp+40h+SubjectContext.PrimaryToken], xmm1
0x1400b9d64  mov     [rbp+40h+var_A8], r8
0x1400b9d68  movups  [rbp+40h+var_60], xmm0
0x1400b9d6c  mov     rax, [r15]
0x1400b9d6f  mov     [rsp+140h+var_E8], rdx
0x1400b9d74  mov     [rbp+40h+DeferredContext], rsi
0x1400b9d78  mov     [rsp+140h+var_ED], bl
0x1400b9d7c  cmp     rax, rcx
0x1400b9d7f  jnz     short loc_1400B9DD6
0x1400b9d81  test    bl, bl
0x1400b9d83  jnz     short loc_1400B9DD6
0x1400b9d85  mov     eax, cs:dword_1400876D0
0x1400b9d8b  lea     edi, [rsi+2]
0x1400b9d8e  cmp     eax, edi
0x1400b9d90  jbe     short loc_1400B9DCC
0x1400b9d92  lea     r14d, [rsi+10h]
0x1400b9d96  mov     edx, r14d
0x1400b9d99  lea     rcx, dword_1400876D0
0x1400b9da0  call    _tlgKeywordOn
0x1400b9da5  test    al, al
0x1400b9da7  jz      short loc_1400B9DCC
0x1400b9da9  lea     rax, aVhdmpisurfacev_15; "VhdmpiSurfaceVirtualDisk: invalid flags"...
0x1400b9db0  mov     edx, 0AC1h; int
0x1400b9db5  mov     r9d, r14d; int
0x1400b9db8  mov     [rsp+140h+IoStatusBlock], rax; char *
0x1400b9dbd  mov     r8d, edi; int
0x1400b9dc0  lea     rcx, aVhdmpicreatesu; "VhdmpiCreateSurface"
0x1400b9dc7  call    TraceEvents
0x1400b9dcc  mov     ebx, 0C000000Dh
0x1400b9dd1  jmp     loc_1400BA8BF
0x1400b9dd6  lea     rcx, VhdmpiEmptyISOBackingStore
0x1400b9ddd  cmp     r15, rcx
0x1400b9de0  jnz     short loc_1400B9E3B
0x1400b9de2  test    r13b, 8
0x1400b9de6  jnz     short loc_1400B9E3B
0x1400b9de8  mov     eax, cs:dword_1400876D0
0x1400b9dee  mov     edi, 2
0x1400b9df3  cmp     eax, edi
0x1400b9df5  jbe     short loc_1400B9E31
0x1400b9df7  lea     r14d, [rdi+0Eh]
0x1400b9dfb  mov     edx, r14d
0x1400b9dfe  lea     rcx, dword_1400876D0
0x1400b9e05  call    _tlgKeywordOn
0x1400b9e0a  test    al, al
0x1400b9e0c  jz      short loc_1400B9E31
0x1400b9e0e  mov     edx, 0AD2h; int
0x1400b9e13  lea     rax, aCannotLoopback; "Cannot loopback mount empty ISO backing"...
0x1400b9e1a  mov     r9d, r14d; int
0x1400b9e1d  mov     [rsp+140h+IoStatusBlock], rax; char *
0x1400b9e22  mov     r8d, edi; int
0x1400b9e25  lea     rcx, aVhdmpicreatesu; "VhdmpiCreateSurface"
0x1400b9e2c  call    TraceEvents
0x1400b9e31  mov     ebx, 0C00000BBh
0x1400b9e36  jmp     loc_1400BA8BF
0x1400b9e3b  cmp     [rdx+5Ch], sil
0x1400b9e3f  jz      short loc_1400B9E8F
0x1400b9e41  mov     rax, [rax+230h]
0x1400b9e48  test    rax, rax
0x1400b9e4b  jz      short loc_1400B9E8F
0x1400b9e4d  xor     edx, edx
0x1400b9e4f  mov     rcx, r15
0x1400b9e52  call    _guard_dispatch_icall
0x1400b9e57  test    al, al
0x1400b9e59  jz      short loc_1400B9E8F
0x1400b9e5b  mov     eax, cs:dword_1400876D0
0x1400b9e61  mov     edi, 2
0x1400b9e66  cmp     eax, edi
0x1400b9e68  jbe     short loc_1400B9E31
0x1400b9e6a  lea     r14d, [rdi+0Eh]
0x1400b9e6e  mov     edx, r14d
0x1400b9e71  lea     rcx, dword_1400876D0
0x1400b9e78  call    _tlgKeywordOn
0x1400b9e7d  test    al, al
0x1400b9e7f  jz      short loc_1400B9E31
0x1400b9e81  mov     edx, 0AE3h
0x1400b9e86  lea     rax, aAttemptingToMo; "Attempting to mount a PMEM-compatible v"...
0x1400b9e8d  jmp     short loc_1400B9E1A
0x1400b9e8f  xor     r14b, r14b
0x1400b9e92  mov     [rsp+140h+var_F0], r14b
0x1400b9e97  cmp     [r12+50h], sil
0x1400b9e9c  jnz     loc_1400B9F65
0x1400b9ea2  test    r13b, 8
0x1400b9ea6  jnz     loc_1400B9F65
0x1400b9eac  lea     rdx, [rbp+40h+var_60]
0x1400b9eb0  mov     rcx, r12
0x1400b9eb3  call    VhdmpiGetVirtualStorageType
0x1400b9eb8  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x1400b9ebc  call    cs:__imp_SeCaptureSubjectContext
0x1400b9ec3  nop     dword ptr [rax+rax+00h]
0x1400b9ec8  movzx   r8d, bl
0x1400b9ecc  lea     rdx, [rbp+40h+var_60]
0x1400b9ed0  xor     r8d, 1
0x1400b9ed4  lea     rcx, [rbp+40h+SubjectContext]
0x1400b9ed8  inc     r8d
0x1400b9edb  shl     r8d, 10h
0x1400b9edf  call    cs:__imp_DependentFSCheckStoragePrivilege
0x1400b9ee6  nop     dword ptr [rax+rax+00h]
0x1400b9eeb  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x1400b9eef  mov     ebx, eax
0x1400b9ef1  call    cs:__imp_SeReleaseSubjectContext
0x1400b9ef8  nop     dword ptr [rax+rax+00h]
0x1400b9efd  test    ebx, ebx
0x1400b9eff  jns     short loc_1400B9F65
0x1400b9f01  mov     ecx, cs:dword_1400876D0
0x1400b9f07  mov     edi, 2
0x1400b9f0c  cmp     ecx, edi
0x1400b9f0e  jbe     loc_1400BA895
0x1400b9f14  lea     r12d, [rdi+3Eh]
0x1400b9f18  mov     edx, r12d
0x1400b9f1b  lea     rcx, dword_1400876D0
0x1400b9f22  call    _tlgKeywordOn
0x1400b9f27  mov     r14, [rsp+140h+var_E8]
0x1400b9f2c  test    al, al
0x1400b9f2e  jz      loc_1400BA898
0x1400b9f34  mov     dword ptr [rsp+140h+InputBuffer], ebx
0x1400b9f38  lea     rax, aVhdmpisurfacev_1; "VhdmpiSurfaceVirtualDisk : CheckStorage"...
0x1400b9f3f  mov     qword ptr [rsp+140h+FsControlCode], r14; char
0x1400b9f44  lea     rcx, aVhdmpicreatesu; "VhdmpiCreateSurface"
0x1400b9f4b  mov     edx, 0B01h; int
0x1400b9f50  mov     [rsp+140h+IoStatusBlock], rax; char *
0x1400b9f55  mov     r9d, r12d; int
0x1400b9f58  mov     r8d, edi; int
0x1400b9f5b  call    TraceEvents
0x1400b9f60  jmp     loc_1400BA898
0x1400b9f65  mov     rax, [r15]
0x1400b9f68  mov     rcx, r15
0x1400b9f6b  mov     rax, [rax+70h]
0x1400b9f6f  call    _guard_dispatch_icall
0x1400b9f74  xor     r8d, r8d
0x1400b9f77  mov     edi, 2
0x1400b9f7c  test    al, al
0x1400b9f7e  jz      short loc_1400B9FCE
0x1400b9f80  mov     rax, [rsp+140h+var_D0]
0x1400b9f85  mov     eax, [rax+4]
0x1400b9f88  test    dil, al
0x1400b9f8b  jz      short loc_1400B9FCE
0x1400b9f8d  cmp     [r12+57h], r8b
0x1400b9f92  jnz     short loc_1400B9FCE
0x1400b9f94  mov     eax, cs:dword_1400876D0
0x1400b9f9a  cmp     eax, edi
0x1400b9f9c  jbe     loc_1400B9E31
0x1400b9fa2  lea     r14d, [rdi+0Eh]
0x1400b9fa6  mov     edx, r14d
0x1400b9fa9  lea     rcx, dword_1400876D0
0x1400b9fb0  call    _tlgKeywordOn
0x1400b9fb5  test    al, al
0x1400b9fb7  jz      loc_1400B9E31
0x1400b9fbd  mov     edx, 0B16h
0x1400b9fc2  lea     rax, aVhdmpisurfacev_14; "VhdmpiSurfaceVirtualDisk: cannot surfac"...
0x1400b9fc9  jmp     loc_1400B9E1A
0x1400b9fce  lea     rax, VhdmpiEmptyISOBackingStore
0x1400b9fd5  mov     [rsp+140h+var_E0], r8b
0x1400b9fda  mov     [rsp+140h+var_EE], r8b
0x1400b9fdf  mov     [rsp+140h+var_EF], r8b
0x1400b9fe4  cmp     r15, rax
0x1400b9fe7  jz      loc_1400BA198
0x1400b9fed  lea     r9, [rbp+40h+var_B8]
0x1400b9ff1  mov     dl, 1
0x1400b9ff3  lea     r8, [rbp+40h+var_C0]
0x1400b9ff7  mov     rcx, r15
0x1400b9ffa  call    VhdmpiPinFile
0x1400b9fff  mov     ebx, eax
0x1400ba001  test    eax, eax
0x1400ba003  js      loc_1400BA18F
0x1400ba009  mov     r14d, r13d
0x1400ba00c  lea     rdx, [rbp+40h+var_60]
0x1400ba010  mov     rcx, r12
0x1400ba013  and     r14d, 8
0x1400ba017  call    VhdmpiGetVirtualStorageType
0x1400ba01c  mov     edx, r14d
0x1400ba01f  lea     rax, [rsp+140h+var_C8]
0x1400ba024  mov     [rsp+140h+InputBuffer], rax
0x1400ba029  lea     r9, [rbp+40h+var_60]
0x1400ba02d  mov     rax, [rbp+40h+var_C0]
0x1400ba031  neg     edx
0x1400ba033  mov     rdx, [rbp+40h+var_B8]
0x1400ba037  mov     rcx, rax
0x1400ba03a  sbb     r8d, r8d
0x1400ba03d  mov     qword ptr [rsp+140h+FsControlCode], rsi
0x1400ba042  and     r8d, 200h
0x1400ba049  mov     [rsp+140h+IoStatusBlock], rsi
0x1400ba04e  or      r8d, [r15+0DCh]
0x1400ba055  mov     [rsp+140h+FileHandle], rax
0x1400ba05a  call    cs:__imp_DependentFSCheckFileHandle
0x1400ba061  nop     dword ptr [rax+rax+00h]
0x1400ba066  mov     ebx, eax
0x1400ba068  test    eax, eax
0x1400ba06a  js      short loc_1400BA0D4
0x1400ba06c  test    r14d, r14d
0x1400ba06f  jnz     loc_1400BA198
0x1400ba075  mov     rcx, r12
0x1400ba078  call    VhdmpiVerifyBackingStorePresence
0x1400ba07d  mov     ebx, eax
0x1400ba07f  test    eax, eax
0x1400ba081  jns     loc_1400BA198
0x1400ba087  mov     eax, cs:dword_1400876D0
0x1400ba08d  cmp     eax, edi
0x1400ba08f  jbe     short loc_1400BA0D4
0x1400ba091  lea     r12d, [r14+40h]
0x1400ba095  mov     edx, r12d
0x1400ba098  lea     rcx, dword_1400876D0
0x1400ba09f  call    _tlgKeywordOn
0x1400ba0a4  test    al, al
0x1400ba0a6  jz      short loc_1400BA0CF
0x1400ba0a8  lea     rax, aVhdmpisurfacev; "VhdmpiSurfaceVirtualDisk: backing store"...
0x1400ba0af  mov     [rsp+140h+FsControlCode], ebx; char
0x1400ba0b3  mov     edx, 0B6Eh; int
0x1400ba0b8  mov     [rsp+140h+IoStatusBlock], rax; char *
0x1400ba0bd  mov     r9d, r12d; int
0x1400ba0c0  lea     rcx, aVhdmpicreatesu; "VhdmpiCreateSurface"
0x1400ba0c7  mov     r8d, edi; int
0x1400ba0ca  call    TraceEvents
0x1400ba0cf  mov     r12, [rsp+140h+var_E8]
0x1400ba0d4  mov     r14b, sil
0x1400ba0d7  mov     rax, [rsp+140h+FileHandle]
0x1400ba0dc  mov     r13b, sil
0x1400ba0df  mov     dil, sil
0x1400ba0e2  test    rax, rax
0x1400ba0e5  jz      short loc_1400BA101
0x1400ba0e7  lea     rax, VhdmpiEmptyISOBackingStore
0x1400ba0ee  cmp     r15, rax
0x1400ba0f1  jz      short loc_1400BA101
0x1400ba0f3  lea     rcx, [r15+48h]
0x1400ba0f7  mov     edx, 1
0x1400ba0fc  call    VhdmpiFileWrapperUnpinFile
0x1400ba101  test    dil, dil
0x1400ba104  jz      short loc_1400BA120
0x1400ba106  movzx   r8d, [rsp+140h+var_ED]
0x1400ba10c  lea     rcx, [rsi+5B8h]; struct VHD_SECURITY_CONTEXT *
0x1400ba113  mov     rdx, [r12+90h]; struct _VHD_BACKING_STORE_HEADER *
0x1400ba11b  call    VhdmpiReleaseSurfaceBackingStoreChainAccess
0x1400ba120  test    r13b, r13b
0x1400ba123  jz      short loc_1400BA131
0x1400ba125  lea     rcx, [rsi+5B8h]
0x1400ba12c  call    VhdmpiCleanupSecurityContext
0x1400ba131  test    ebx, ebx
0x1400ba133  jns     loc_1400BA8A7
0x1400ba139  cmp     [rsp+140h+var_E0], 0
0x1400ba13e  mov     [rsp+140h+var_F0], r14b
0x1400ba143  jz      loc_1400BA88B
0x1400ba149  test    dword ptr [rsi+38h], 100h
0x1400ba150  jnz     short loc_1400BA162
0x1400ba152  xor     r8d, r8d
0x1400ba155  lea     rcx, [r15+48h]; char
0x1400ba159  lea     edx, [r8+1]
0x1400ba15d  call    VhdmpiFileWrapperNotifyCSVFSLoopbackMount
0x1400ba162  test    r15, r15
0x1400ba165  jz      loc_1400BA88B
0x1400ba16b  lea     rcx, [r15+48h]; char
0x1400ba16f  xor     r8d, r8d
0x1400ba172  xor     edx, edx
0x1400ba174  call    VhdmpiFileWrapperNotifyCSVFSLoopbackMount
0x1400ba179  mov     r15, [r15+478h]
0x1400ba180  test    r15, r15
0x1400ba183  jnz     short loc_1400BA16B
0x1400ba185  mov     r14, [rsp+140h+var_E8]
0x1400ba18a  jmp     loc_1400BA898
0x1400ba18f  mov     rax, [rbp+40h+var_C0]
0x1400ba193  jmp     loc_1400BA0DC
0x1400ba198  lea     rcx, [r12+0B8h]
0x1400ba1a0  call    VhdmpiAcquirePassiveLock
0x1400ba1a5  movzx   r9d, [rsp+140h+var_ED]
0x1400ba1ab  mov     r14b, 1
0x1400ba1ae  mov     rcx, [rsp+140h+var_D0]; struct _VHD_HANDLE_CONTEXT *
0x1400ba1b3  xor     r9d, 1
0x1400ba1b7  shl     r9d, 9
  ... truncated ...
```
