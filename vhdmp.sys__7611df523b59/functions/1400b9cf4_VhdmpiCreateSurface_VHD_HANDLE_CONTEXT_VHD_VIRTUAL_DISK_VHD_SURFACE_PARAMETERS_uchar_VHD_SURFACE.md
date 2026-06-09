# VhdmpiCreateSurface(_VHD_HANDLE_CONTEXT *,_VHD_VIRTUAL_DISK *,VHD_SURFACE_PARAMETERS *,uchar *,_VHD_SURFACE * *)

- ea: `0x1400b9cf4`
- end: `0x1400ba8f2`
- name: `?VhdmpiCreateSurface@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_VIRTUAL_DISK@@PEAUVHD_SURFACE_PARAMETERS@@PEAEPEAPEAU_VHD_SURFACE@@@Z`
- size: `3070`
- prototype: `__int64 __fastcall(struct _VHD_HANDLE_CONTEXT *, struct _VHD_VIRTUAL_DISK *, struct VHD_SURFACE_PARAMETERS *, unsigned __int8 *, struct _VHD_SURFACE **)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400bc264`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x14001e94c`
- `0x1400201d0`
- `0x140021094`
- `0x140022234`
- `0x140023560`
- `0x140023be4`
- `0x140026510`
- `0x1400272b4`
- `0x14002e55c`
- `0x140035aa4`
- `0x140035c2c`
- `0x140035e94`
- `0x14004ded8`
- `0x14005d7c0`
- `0x14005d840`
- `0x14005da00`
- `0x1400adf48`
- `0x1400b9b34`
- `0x1400b9cf4`
- `0x1400bab54`
- `0x1400bac50`
- `0x1400bba54`
- `0x1400bbaf4`
- `0x1400bc108`
- `0x1400bcf38`
- `0x1400cff00`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x1400ba6a4`
- `ntoskrnl!ZwFsControlFile` at `0x1400ba6a4`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ba6c2`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400ba6c2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b9ecc`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b9ecc`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b9f01`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b9f01`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400ba261`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400ba261`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba292`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba292`
- `FSDEPENDS!DependentFSCheckStoragePrivilege` at `0x1400b9eef`
- `FSDEPENDS!DependentFSCheckStoragePrivilege` at `0x1400b9eef`
- `FSDEPENDS!DependentFSCheckFileHandle` at `0x1400ba06a`
- `FSDEPENDS!DependentFSCheckFileHandle` at `0x1400ba06a`

## string_xrefs

- `0x1400ba2c7`: `VhdmpiSurfaceVirtualDisk: could not allocate nonpaged buffer for ACL.`
- `0x1400ba4bb`: `VhdmpiSurfaceVirtualDisk: VhdmpiGetFileACL returned 0x%08x.`
- `0x1400ba6f9`: `FSCTL_SET_BOOTLOADER_ACCESSED failed: 0x%08x`
- `0x1400ba7ad`: `ExpandOnMount failed: 0x%08x`
- `0x1400b9dd0`: `VhdmpiCreateSurface`
- `0x1400b9e35`: `VhdmpiCreateSurface`
- `0x1400b9f54`: `VhdmpiCreateSurface`
- `0x1400ba0d0`: `VhdmpiCreateSurface`
- `0x1400ba229`: `VhdmpiCreateSurface`
- `0x1400ba2de`: `VhdmpiCreateSurface`
- `0x1400ba4cf`: `VhdmpiCreateSurface`
- `0x1400ba577`: `VhdmpiCreateSurface`
- `0x1400ba70d`: `VhdmpiCreateSurface`
- `0x1400ba7b8`: `VhdmpiCreateSurface`
- `0x1400b9e23`: `Cannot loopback mount empty ISO backing store.`
- `0x1400b9e96`: `Attempting to mount a PMEM-compatible virtual disk as a VM SCSI device.`
- `0x1400b9f48`: `VhdmpiSurfaceVirtualDisk : CheckStoragePrivilege failed for disk %p, returned status 0x%x`

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
  int v11; // edx
  char *v12; // rax
  unsigned __int8 (__fastcall *v13)(__int64, _QWORD); // rax
  char v14; // r14
  struct _VHD_VIRTUAL_DISK *v15; // r14
  char v16; // al
  __int64 v17; // rdx
  __int64 v18; // r8
  HANDLE v19; // rax
  char v20; // r13
  char v21; // di
  int Surface; // eax
  struct VHD_SURFACE_PARAMETERS *v23; // rbx
  unsigned int v24; // eax
  void *Pool2; // rax
  struct _VHD_VIRTUAL_DISK *v26; // rdx
  char v27; // cl
  char IsRemoteSmbFile; // al
  struct VHD_SURFACE_PARAMETERS *v29; // r13
  _OWORD *v30; // r12
  char v31; // r8
  __int64 *v32; // rcx
  int v33; // r8d
  NTSTATUS Status; // r8d
  char v35; // r8
  int v36; // eax
  __int64 i; // rbx
  int v38; // edx
  char *v39; // rax
  char FsControlCode; // [rsp+28h] [rbp-D8h]
  char v42; // [rsp+50h] [rbp-B0h]
  char v43; // [rsp+53h] [rbp-ADh]
  char v45; // [rsp+60h] [rbp-A0h]
  HANDLE FileHandle; // [rsp+68h] [rbp-98h]
  int v48; // [rsp+78h] [rbp-88h] BYREF
  void *v49; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+88h] [rbp-78h] BYREF
  PVOID DeferredContext; // [rsp+90h] [rbp-70h] BYREF
  struct VHD_SURFACE_PARAMETERS *v52; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v53; // [rsp+A0h] [rbp-60h]
  struct _VHD_SURFACE **v54; // [rsp+A8h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v57; // [rsp+E0h] [rbp-20h] BYREF
  int v58; // [rsp+F0h] [rbp-10h]

  v5 = *((_QWORD *)a2 + 18);
  v6 = *(_DWORD *)a3;
  v7 = 0;
  v54 = a5;
  v58 = 0;
  FileHandle = 0;
  v49 = 0;
  v8 = a2;
  v50 = 0;
  IoStatusBlock = 0;
  v48 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v53 = a4;
  v52 = a3;
  v57 = 0;
  v9 = *(_QWORD *)v5;
  DeferredContext = 0;
  v43 = v6 & 1;
  if ( (char **)v9 == &IsoParser && (v6 & 1) == 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents(
        (int)"VhdmpiCreateSurface",
        2753,
        2,
        16,
        "VhdmpiSurfaceVirtualDisk: invalid flags for ISO",
        FsControlCode);
    return (unsigned int)-1073741811;
  }
  if ( (__int64 *)v5 == &VhdmpiEmptyISOBackingStore && (v6 & 8) == 0 )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      return (unsigned int)-1073741637;
    v11 = 2770;
    v12 = "Cannot loopback mount empty ISO backing store.";
LABEL_12:
    TraceEvents((int)"VhdmpiCreateSurface", v11, 2, 16, v12, FsControlCode);
    return (unsigned int)-1073741637;
  }
  if ( *((_BYTE *)a2 + 92) )
  {
    v13 = *(unsigned __int8 (__fastcall **)(__int64, _QWORD))(v9 + 560);
    if ( v13 )
    {
      if ( v13(v5, 0) )
      {
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
          return (unsigned int)-1073741637;
        v11 = 2787;
        v12 = "Attempting to mount a PMEM-compatible virtual disk as a VM SCSI device.";
        goto LABEL_12;
      }
    }
  }
  v14 = 0;
  v42 = 0;
  if ( !*((_BYTE *)v8 + 80) && (v6 & 8) == 0 )
  {
    VhdmpiGetVirtualStorageType(v8, &v57);
    SeCaptureSubjectContext(&SubjectContext);
    Guid = DependentFSCheckStoragePrivilege(&SubjectContext, &v57, ((unsigned int)!(v6 & 1) + 1) << 16);
    SeReleaseSubjectContext(&SubjectContext);
    if ( Guid < 0 )
    {
      if ( (unsigned int)dword_140087708 <= 2 )
      {
        v15 = v8;
      }
      else
      {
        v15 = a2;
        if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 64) )
          TraceEvents(
            (int)"VhdmpiCreateSurface",
            2817,
            2,
            64,
            "VhdmpiSurfaceVirtualDisk : CheckStoragePrivilege failed for disk %p, returned status 0x%x",
            (char)a2);
      }
LABEL_170:
      if ( v7 )
        VhdmpiFreeVirtualDiskSurface((char)v7);
      goto LABEL_173;
    }
  }
  v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 112LL))(v5);
  v18 = 0;
  if ( v16 && (*((_DWORD *)a1 + 1) & 2) != 0 && !*((_BYTE *)v8 + 87) )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      return (unsigned int)-1073741637;
    v11 = 2838;
    v12 = "VhdmpiSurfaceVirtualDisk: cannot surface 'No Parents' diff disk";
    goto LABEL_12;
  }
  v45 = 0;
  if ( (__int64 *)v5 == &VhdmpiEmptyISOBackingStore )
    goto LABEL_59;
  LOBYTE(v17) = 1;
  Guid = VhdmpiPinFile(v5, v17, &v49, &v50);
  if ( Guid < 0 )
  {
    v19 = v49;
    goto LABEL_43;
  }
  VhdmpiGetVirtualStorageType(v8, &v57);
  FileHandle = v49;
  Guid = DependentFSCheckFileHandle(v49, v50, *(_DWORD *)(v5 + 220) | ((v6 & 8) != 0 ? 0x200 : 0), &v57, 0, 0, &v48);
  if ( Guid < 0 )
    goto LABEL_41;
  if ( (v6 & 8) != 0 || (Guid = VhdmpiVerifyBackingStorePresence(v8), Guid >= 0) )
  {
LABEL_59:
    VhdmpiAcquirePassiveLock((char *)v8 + 184, v17, v18);
    v14 = 1;
    v42 = 1;
    Guid = VhdmpiValidateProposedOperationUnderLock(a1, v8, 0x4EFu, ((unsigned __int8)!(v6 & 1) << 9) + 256);
    if ( Guid < 0 )
    {
      if ( (unsigned int)dword_140087708 > 2 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
          TraceEvents(
            (int)"VhdmpiCreateSurface",
            2959,
            2,
            16,
            "VhdmpiSurfaceVirtualDisk: conflicts with existing meta-operation",
            FsControlCode);
        v14 = 1;
      }
      goto LABEL_42;
    }
    Surface = VhdmpiAllocateSurface((struct _EX_RUNDOWN_REF **)&DeferredContext);
    v7 = (char *)DeferredContext;
    Guid = Surface;
    if ( Surface < 0 )
      goto LABEL_74;
    if ( v43 )
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)DeferredContext + 10);
    v23 = v52;
    v24 = *((_DWORD *)v52 + 4);
    if ( v24 )
    {
      Pool2 = (void *)ExAllocatePool2(64, v24, 2017740886);
      *((_QWORD *)v7 + 61) = Pool2;
      if ( !Pool2 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
          TraceEvents(
            (int)"VhdmpiCreateSurface",
            2991,
            2,
            16,
            "VhdmpiSurfaceVirtualDisk: could not allocate nonpaged buffer for ACL.",
            FsControlCode);
        Guid = -1073741670;
        goto LABEL_73;
      }
      memmove(Pool2, *((const void **)v23 + 1), *((unsigned int *)v23 + 4));
      *((_DWORD *)v7 + 124) = *((_DWORD *)v23 + 4);
    }
    else
    {
      v26 = a2;
      if ( *((_BYTE *)a2 + 80) || (__int64 *)v5 == &VhdmpiEmptyISOBackingStore || (v6 & 0x18) != 0 )
      {
        *((_QWORD *)v7 + 61) = 0;
        *((_DWORD *)v7 + 124) = 0;
        goto LABEL_78;
      }
      if ( (int)VhdmpiGetFileSecurityDescriptor(v50, v7 + 488, v7 + 496) < 0 )
      {
        if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
          TraceEvents(
            (int)"VhdmpiCreateSurface",
            3023,
            2,
            16,
            "VhdmpiSurfaceVirtualDisk: VhdmpiGetFileACL returned 0x%08x.",
            v31);
        *((_DWORD *)v7 + 124) = 0;
      }
    }
    v26 = a2;
LABEL_78:
    v27 = v6 & 1;
    if ( v43 )
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
      IsRemoteSmbFile = VhdmpiIsRemoteSmbFile(v5 + 72);
      v27 = v6 & 1;
      if ( !IsRemoteSmbFile )
        *((_DWORD *)v7 + 14) |= 0x200000u;
    }
    v29 = v52;
    if ( (*((_DWORD *)v52 + 1) & 1) != 0 )
      *((_DWORD *)v7 + 14) |= 0x4000u;
    if ( (*((_DWORD *)v29 + 1) & 4) != 0 )
      *((_DWORD *)v7 + 14) |= 0x8000u;
    if ( (*((_DWORD *)v29 + 1) & 0x20) != 0 )
      *((_DWORD *)v7 + 14) |= 0x20000u;
    if ( (*((_DWORD *)v29 + 1) & 0x40) != 0 )
      *((_DWORD *)v7 + 14) |= 0x40000u;
    if ( (*((_DWORD *)v29 + 1) & 0x80u) != 0 )
      *((_DWORD *)v7 + 14) |= 0x80000u;
    if ( (*((_DWORD *)v29 + 1) & 0x100) != 0 )
      *((_DWORD *)v7 + 14) |= 0x100000u;
    if ( !v27 && (unsigned __int8)VhdmpiIsRctEnabled(v5) )
      v7[64] = 1;
    *((_DWORD *)v7 + 15) = *((_DWORD *)v29 + 5);
    if ( (*((_DWORD *)v29 + 1) & 0x10) == 0 )
      goto LABEL_128;
    v30 = (_OWORD *)((char *)v26 + 2504);
    *(_OWORD *)((char *)v26 + 2504) = 0;
    if ( *(_OWORD *)((char *)v29 + 24) == *(_OWORD *)&VhdmpZeroGuid )
    {
      Guid = DvGenerateGuid((PUCHAR)v26 + 2504);
      if ( Guid < 0 )
        goto LABEL_73;
      v26 = a2;
    }
    else
    {
      *v30 = *(_OWORD *)((char *)v29 + 24);
    }
    v32 = (__int64 *)*((_QWORD *)v26 + 18);
    if ( v32 == &VhdmpiEmptyISOBackingStore )
    {
LABEL_128:
      v8 = a2;
    }
    else
    {
      Guid = VhdmpiInitializeQoSPolicyForBackingStoreChain(v32, 0, v30);
      if ( Guid < 0 )
      {
        if ( (unsigned int)dword_140087708 > 3 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4) )
          TraceEvents(
            (int)"VhdmpiCreateSurface",
            3149,
            v33,
            v33 + 1,
            "VhdmpiSurfaceVirtualDisk: Failed to initialize QoS policy: 0x%08x",
            Guid);
        goto LABEL_73;
      }
      v8 = a2;
      *((_BYTE *)a2 + 91) = 1;
    }
    *((_QWORD *)v7 + 190) = 0;
    *((_QWORD *)v7 + 189) = VhdmpiIsoAsyncNotify;
    *((_QWORD *)v7 + 188) = v8;
    if ( (*((_DWORD *)v29 + 1) & 2) != 0 )
    {
      *((_QWORD *)a1 + 36) = *((_QWORD *)v29 + 8);
      *((_QWORD *)v7 + 189) = *((_QWORD *)v29 + 6);
      *((_QWORD *)v7 + 190) = *((_QWORD *)v29 + 7);
      *((_QWORD *)v7 + 188) = *((_QWORD *)v29 + 5);
      *((_DWORD *)v7 + 14) |= 0x10000u;
    }
    if ( (*((_DWORD *)v7 + 14) & 0x1000) == 0 )
    {
      v20 = 0;
      goto LABEL_136;
    }
    Guid = VhdmpiCopySecurityContext((PSECURITY_SUBJECT_CONTEXT)(v7 + 1464));
    if ( Guid >= 0 )
    {
      v20 = 1;
      v8 = a2;
      Guid = VhdmpiAcquireSurfaceBackingStoreChainAccess(
               (struct VHD_SECURITY_CONTEXT *)(v7 + 1464),
               (struct _VHD_BACKING_STORE_HEADER *)v5);
      if ( Guid < 0 )
      {
        v21 = 0;
        v14 = 1;
        goto LABEL_75;
      }
LABEL_136:
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
          if ( Status < 0 && (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
            TraceEvents((int)"VhdmpiCreateSurface", 3242, 2, 16, "FSCTL_SET_BOOTLOADER_ACCESSED failed: 0x%08x", v35);
        }
        VhdmpiFileWrapperUnpinFile(v5 + 72, 1);
        v36 = *((_DWORD *)v7 + 14);
        FileHandle = 0;
        if ( (v36 & 0x200) == 0 )
        {
          if ( (v36 & 0x100) == 0 )
            VhdmpiFileWrapperNotifyCSVFSLoopbackMount(v5 + 72);
          for ( i = v5; i; i = *(_QWORD *)(i + 1144) )
            VhdmpiFileWrapperNotifyCSVFSLoopbackMount(i + 72);
          v45 = 1;
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
              *v53 = 0;
            }
            v21 = 0;
            v20 = 0;
            Guid = 0;
            *v54 = (struct _VHD_SURFACE *)v7;
            goto LABEL_156;
          }
          if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
          {
LABEL_155:
            v21 = v20;
LABEL_156:
            v14 = 1;
            goto LABEL_75;
          }
          v38 = 3329;
          v39 = "RegisterDiskAddress failed: 0x%08x";
        }
        else
        {
          if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
            goto LABEL_155;
          v38 = 3308;
          v39 = "VhdmpiInitializeScsiStateForSurface failed: 0x%08x";
        }
      }
      else
      {
        if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
          goto LABEL_155;
        v38 = 3296;
        v39 = "ExpandOnMount failed: 0x%08x";
      }
      TraceEvents((int)"VhdmpiCreateSurface", v38, 2, 16, v39, Guid);
      goto LABEL_155;
    }
LABEL_73:
    v8 = a2;
    v14 = 1;
LABEL_74:
    v21 = 0;
    v20 = 0;
LABEL_75:
    v19 = FileHandle;
    goto LABEL_44;
  }
  if ( (unsigned int)dword_140087708 > 2 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 64) )
      TraceEvents(
        (int)"VhdmpiCreateSurface",
        2926,
        2,
        64,
        "VhdmpiSurfaceVirtualDisk: backing store presence could not be verified (0x%08x)",
        Guid);
    v8 = a2;
  }
LABEL_41:
  v14 = 0;
LABEL_42:
  v19 = FileHandle;
LABEL_43:
  v20 = 0;
  v21 = 0;
LABEL_44:
  if ( v19 && (__int64 *)v5 != &VhdmpiEmptyISOBackingStore )
    VhdmpiFileWrapperUnpinFile(v5 + 72, 1);
  if ( v21 )
    VhdmpiReleaseSurfaceBackingStoreChainAccess(
      (struct VHD_SECURITY_CONTEXT *)(v7 + 1464),
      *((struct _VHD_BACKING_STORE_HEADER **)v8 + 18));
  if ( v20 )
    VhdmpiCleanupSecurityContext(v7 + 1464);
  if ( Guid < 0 )
  {
    v42 = v14;
    if ( !v45 )
      goto LABEL_168;
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
LABEL_168:
      v42 = v14;
    }
    v15 = a2;
    goto LABEL_170;
  }
  v15 = a2;
LABEL_173:
  if ( v42 )
    VhdmpiReleasePassiveLock((char *)v15 + 184);
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x1400b9cf4  push    rbp
0x1400b9cf6  push    rbx
0x1400b9cf7  push    rsi
0x1400b9cf8  push    rdi
0x1400b9cf9  push    r12
0x1400b9cfb  push    r13
0x1400b9cfd  push    r14
0x1400b9cff  push    r15
0x1400b9d01  lea     rbp, [rsp-8]
0x1400b9d06  sub     rsp, 108h
0x1400b9d0d  mov     rax, cs:__security_cookie
0x1400b9d14  xor     rax, rsp
0x1400b9d17  mov     [rbp+40h+var_48], rax
0x1400b9d1b  mov     rax, [rbp+40h+arg_20]
0x1400b9d1f  xorps   xmm0, xmm0
0x1400b9d22  mov     r15, [rdx+90h]
0x1400b9d29  xorps   xmm1, xmm1
0x1400b9d2c  mov     r13d, [r8]
0x1400b9d2f  xor     esi, esi
0x1400b9d31  mov     [rbp+40h+var_98], rax
0x1400b9d35  mov     bl, r13b
0x1400b9d38  xor     eax, eax
0x1400b9d3a  mov     [rsp+140h+var_D0], rcx
0x1400b9d3f  and     bl, 1
0x1400b9d42  mov     [rbp+40h+var_50], eax
0x1400b9d45  mov     [rsp+140h+FileHandle], rax
0x1400b9d4a  lea     rcx, IsoParser
0x1400b9d51  mov     [rbp+40h+var_C0], rax
0x1400b9d55  mov     r12, rdx
0x1400b9d58  mov     [rbp+40h+var_B8], rax
0x1400b9d5c  movups  xmmword ptr [rbp+40h+var_90], xmm0
0x1400b9d60  mov     [rsp+140h+var_C8], 0
0x1400b9d68  movups  xmmword ptr [rbp+40h+SubjectContext.ClientToken], xmm1
0x1400b9d6c  mov     [rbp+40h+var_A0], r9
0x1400b9d70  movups  xmmword ptr [rbp+40h+SubjectContext.PrimaryToken], xmm1
0x1400b9d74  mov     [rbp+40h+var_A8], r8
0x1400b9d78  movups  [rbp+40h+var_60], xmm0
0x1400b9d7c  mov     rax, [r15]
0x1400b9d7f  mov     [rsp+140h+var_E8], rdx
0x1400b9d84  mov     [rbp+40h+DeferredContext], rsi
0x1400b9d88  mov     [rsp+140h+var_ED], bl
0x1400b9d8c  cmp     rax, rcx
0x1400b9d8f  jnz     short loc_1400B9DE6
0x1400b9d91  test    bl, bl
0x1400b9d93  jnz     short loc_1400B9DE6
0x1400b9d95  mov     eax, cs:dword_140087708
0x1400b9d9b  lea     edi, [rsi+2]
0x1400b9d9e  cmp     eax, edi
0x1400b9da0  jbe     short loc_1400B9DDC
0x1400b9da2  lea     r14d, [rsi+10h]
0x1400b9da6  mov     edx, r14d
0x1400b9da9  lea     rcx, dword_140087708
0x1400b9db0  call    _tlgKeywordOn
0x1400b9db5  test    al, al
0x1400b9db7  jz      short loc_1400B9DDC
0x1400b9db9  lea     rax, aVhdmpisurfacev_15; "VhdmpiSurfaceVirtualDisk: invalid flags"...
0x1400b9dc0  mov     edx, 0AC1h; int
0x1400b9dc5  mov     r9d, r14d; int
0x1400b9dc8  mov     [rsp+140h+IoStatusBlock], rax; char *
0x1400b9dcd  mov     r8d, edi; int
0x1400b9dd0  lea     rcx, aVhdmpicreatesu; "VhdmpiCreateSurface"
0x1400b9dd7  call    TraceEvents
0x1400b9ddc  mov     ebx, 0C000000Dh
0x1400b9de1  jmp     loc_1400BA8CF
0x1400b9de6  lea     rcx, VhdmpiEmptyISOBackingStore
0x1400b9ded  cmp     r15, rcx
0x1400b9df0  jnz     short loc_1400B9E4B
0x1400b9df2  test    r13b, 8
0x1400b9df6  jnz     short loc_1400B9E4B
0x1400b9df8  mov     eax, cs:dword_140087708
0x1400b9dfe  mov     edi, 2
0x1400b9e03  cmp     eax, edi
0x1400b9e05  jbe     short loc_1400B9E41
0x1400b9e07  lea     r14d, [rdi+0Eh]
0x1400b9e0b  mov     edx, r14d
0x1400b9e0e  lea     rcx, dword_140087708
0x1400b9e15  call    _tlgKeywordOn
0x1400b9e1a  test    al, al
0x1400b9e1c  jz      short loc_1400B9E41
0x1400b9e1e  mov     edx, 0AD2h; int
0x1400b9e23  lea     rax, aCannotLoopback; "Cannot loopback mount empty ISO backing"...
0x1400b9e2a  mov     r9d, r14d; int
0x1400b9e2d  mov     [rsp+140h+IoStatusBlock], rax; char *
0x1400b9e32  mov     r8d, edi; int
0x1400b9e35  lea     rcx, aVhdmpicreatesu; "VhdmpiCreateSurface"
0x1400b9e3c  call    TraceEvents
0x1400b9e41  mov     ebx, 0C00000BBh
0x1400b9e46  jmp     loc_1400BA8CF
0x1400b9e4b  cmp     [rdx+5Ch], sil
0x1400b9e4f  jz      short loc_1400B9E9F
0x1400b9e51  mov     rax, [rax+230h]
0x1400b9e58  test    rax, rax
0x1400b9e5b  jz      short loc_1400B9E9F
0x1400b9e5d  xor     edx, edx
0x1400b9e5f  mov     rcx, r15
0x1400b9e62  call    _guard_dispatch_icall
0x1400b9e67  test    al, al
0x1400b9e69  jz      short loc_1400B9E9F
0x1400b9e6b  mov     eax, cs:dword_140087708
0x1400b9e71  mov     edi, 2
0x1400b9e76  cmp     eax, edi
0x1400b9e78  jbe     short loc_1400B9E41
0x1400b9e7a  lea     r14d, [rdi+0Eh]
0x1400b9e7e  mov     edx, r14d
0x1400b9e81  lea     rcx, dword_140087708
0x1400b9e88  call    _tlgKeywordOn
0x1400b9e8d  test    al, al
0x1400b9e8f  jz      short loc_1400B9E41
0x1400b9e91  mov     edx, 0AE3h
0x1400b9e96  lea     rax, aAttemptingToMo; "Attempting to mount a PMEM-compatible v"...
0x1400b9e9d  jmp     short loc_1400B9E2A
0x1400b9e9f  xor     r14b, r14b
0x1400b9ea2  mov     [rsp+140h+var_F0], r14b
0x1400b9ea7  cmp     [r12+50h], sil
0x1400b9eac  jnz     loc_1400B9F75
0x1400b9eb2  test    r13b, 8
0x1400b9eb6  jnz     loc_1400B9F75
0x1400b9ebc  lea     rdx, [rbp+40h+var_60]
0x1400b9ec0  mov     rcx, r12
0x1400b9ec3  call    VhdmpiGetVirtualStorageType
0x1400b9ec8  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x1400b9ecc  call    cs:__imp_SeCaptureSubjectContext
0x1400b9ed3  nop     dword ptr [rax+rax+00h]
0x1400b9ed8  movzx   r8d, bl
0x1400b9edc  lea     rdx, [rbp+40h+var_60]
0x1400b9ee0  xor     r8d, 1
0x1400b9ee4  lea     rcx, [rbp+40h+SubjectContext]
0x1400b9ee8  inc     r8d
0x1400b9eeb  shl     r8d, 10h
0x1400b9eef  call    cs:__imp_DependentFSCheckStoragePrivilege
0x1400b9ef6  nop     dword ptr [rax+rax+00h]
0x1400b9efb  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x1400b9eff  mov     ebx, eax
0x1400b9f01  call    cs:__imp_SeReleaseSubjectContext
0x1400b9f08  nop     dword ptr [rax+rax+00h]
0x1400b9f0d  test    ebx, ebx
0x1400b9f0f  jns     short loc_1400B9F75
0x1400b9f11  mov     ecx, cs:dword_140087708
0x1400b9f17  mov     edi, 2
0x1400b9f1c  cmp     ecx, edi
0x1400b9f1e  jbe     loc_1400BA8A5
0x1400b9f24  lea     r12d, [rdi+3Eh]
0x1400b9f28  mov     edx, r12d
0x1400b9f2b  lea     rcx, dword_140087708
0x1400b9f32  call    _tlgKeywordOn
0x1400b9f37  mov     r14, [rsp+140h+var_E8]
0x1400b9f3c  test    al, al
0x1400b9f3e  jz      loc_1400BA8A8
0x1400b9f44  mov     dword ptr [rsp+140h+InputBuffer], ebx
0x1400b9f48  lea     rax, aVhdmpisurfacev_1; "VhdmpiSurfaceVirtualDisk : CheckStorage"...
0x1400b9f4f  mov     qword ptr [rsp+140h+FsControlCode], r14; char
0x1400b9f54  lea     rcx, aVhdmpicreatesu; "VhdmpiCreateSurface"
0x1400b9f5b  mov     edx, 0B01h; int
0x1400b9f60  mov     [rsp+140h+IoStatusBlock], rax; char *
0x1400b9f65  mov     r9d, r12d; int
0x1400b9f68  mov     r8d, edi; int
0x1400b9f6b  call    TraceEvents
0x1400b9f70  jmp     loc_1400BA8A8
0x1400b9f75  mov     rax, [r15]
0x1400b9f78  mov     rcx, r15
0x1400b9f7b  mov     rax, [rax+70h]
0x1400b9f7f  call    _guard_dispatch_icall
0x1400b9f84  xor     r8d, r8d
0x1400b9f87  mov     edi, 2
0x1400b9f8c  test    al, al
0x1400b9f8e  jz      short loc_1400B9FDE
0x1400b9f90  mov     rax, [rsp+140h+var_D0]
0x1400b9f95  mov     eax, [rax+4]
0x1400b9f98  test    dil, al
0x1400b9f9b  jz      short loc_1400B9FDE
0x1400b9f9d  cmp     [r12+57h], r8b
0x1400b9fa2  jnz     short loc_1400B9FDE
0x1400b9fa4  mov     eax, cs:dword_140087708
0x1400b9faa  cmp     eax, edi
0x1400b9fac  jbe     loc_1400B9E41
0x1400b9fb2  lea     r14d, [rdi+0Eh]
0x1400b9fb6  mov     edx, r14d
0x1400b9fb9  lea     rcx, dword_140087708
0x1400b9fc0  call    _tlgKeywordOn
0x1400b9fc5  test    al, al
0x1400b9fc7  jz      loc_1400B9E41
0x1400b9fcd  mov     edx, 0B16h
0x1400b9fd2  lea     rax, aVhdmpisurfacev_14; "VhdmpiSurfaceVirtualDisk: cannot surfac"...
0x1400b9fd9  jmp     loc_1400B9E2A
0x1400b9fde  lea     rax, VhdmpiEmptyISOBackingStore
0x1400b9fe5  mov     [rsp+140h+var_E0], r8b
0x1400b9fea  mov     [rsp+140h+var_EE], r8b
0x1400b9fef  mov     [rsp+140h+var_EF], r8b
0x1400b9ff4  cmp     r15, rax
0x1400b9ff7  jz      loc_1400BA1A8
0x1400b9ffd  lea     r9, [rbp+40h+var_B8]
0x1400ba001  mov     dl, 1
0x1400ba003  lea     r8, [rbp+40h+var_C0]
0x1400ba007  mov     rcx, r15
0x1400ba00a  call    VhdmpiPinFile
0x1400ba00f  mov     ebx, eax
0x1400ba011  test    eax, eax
0x1400ba013  js      loc_1400BA19F
0x1400ba019  mov     r14d, r13d
0x1400ba01c  lea     rdx, [rbp+40h+var_60]
0x1400ba020  mov     rcx, r12
0x1400ba023  and     r14d, 8
0x1400ba027  call    VhdmpiGetVirtualStorageType
0x1400ba02c  mov     edx, r14d
0x1400ba02f  lea     rax, [rsp+140h+var_C8]
0x1400ba034  mov     [rsp+140h+InputBuffer], rax
0x1400ba039  lea     r9, [rbp+40h+var_60]
0x1400ba03d  mov     rax, [rbp+40h+var_C0]
0x1400ba041  neg     edx
0x1400ba043  mov     rdx, [rbp+40h+var_B8]
0x1400ba047  mov     rcx, rax
0x1400ba04a  sbb     r8d, r8d
0x1400ba04d  mov     qword ptr [rsp+140h+FsControlCode], rsi
0x1400ba052  and     r8d, 200h
0x1400ba059  mov     [rsp+140h+IoStatusBlock], rsi
0x1400ba05e  or      r8d, [r15+0DCh]
0x1400ba065  mov     [rsp+140h+FileHandle], rax
0x1400ba06a  call    cs:__imp_DependentFSCheckFileHandle
0x1400ba071  nop     dword ptr [rax+rax+00h]
0x1400ba076  mov     ebx, eax
0x1400ba078  test    eax, eax
0x1400ba07a  js      short loc_1400BA0E4
0x1400ba07c  test    r14d, r14d
0x1400ba07f  jnz     loc_1400BA1A8
0x1400ba085  mov     rcx, r12
0x1400ba088  call    VhdmpiVerifyBackingStorePresence
0x1400ba08d  mov     ebx, eax
0x1400ba08f  test    eax, eax
0x1400ba091  jns     loc_1400BA1A8
0x1400ba097  mov     eax, cs:dword_140087708
0x1400ba09d  cmp     eax, edi
0x1400ba09f  jbe     short loc_1400BA0E4
0x1400ba0a1  lea     r12d, [r14+40h]
0x1400ba0a5  mov     edx, r12d
0x1400ba0a8  lea     rcx, dword_140087708
0x1400ba0af  call    _tlgKeywordOn
0x1400ba0b4  test    al, al
0x1400ba0b6  jz      short loc_1400BA0DF
0x1400ba0b8  lea     rax, aVhdmpisurfacev; "VhdmpiSurfaceVirtualDisk: backing store"...
0x1400ba0bf  mov     [rsp+140h+FsControlCode], ebx; char
0x1400ba0c3  mov     edx, 0B6Eh; int
0x1400ba0c8  mov     [rsp+140h+IoStatusBlock], rax; char *
0x1400ba0cd  mov     r9d, r12d; int
0x1400ba0d0  lea     rcx, aVhdmpicreatesu; "VhdmpiCreateSurface"
0x1400ba0d7  mov     r8d, edi; int
0x1400ba0da  call    TraceEvents
0x1400ba0df  mov     r12, [rsp+140h+var_E8]
0x1400ba0e4  mov     r14b, sil
0x1400ba0e7  mov     rax, [rsp+140h+FileHandle]
0x1400ba0ec  mov     r13b, sil
0x1400ba0ef  mov     dil, sil
0x1400ba0f2  test    rax, rax
0x1400ba0f5  jz      short loc_1400BA111
0x1400ba0f7  lea     rax, VhdmpiEmptyISOBackingStore
0x1400ba0fe  cmp     r15, rax
0x1400ba101  jz      short loc_1400BA111
0x1400ba103  lea     rcx, [r15+48h]
0x1400ba107  mov     edx, 1
0x1400ba10c  call    VhdmpiFileWrapperUnpinFile
0x1400ba111  test    dil, dil
0x1400ba114  jz      short loc_1400BA130
0x1400ba116  movzx   r8d, [rsp+140h+var_ED]
0x1400ba11c  lea     rcx, [rsi+5B8h]; struct VHD_SECURITY_CONTEXT *
0x1400ba123  mov     rdx, [r12+90h]; struct _VHD_BACKING_STORE_HEADER *
0x1400ba12b  call    VhdmpiReleaseSurfaceBackingStoreChainAccess
0x1400ba130  test    r13b, r13b
0x1400ba133  jz      short loc_1400BA141
0x1400ba135  lea     rcx, [rsi+5B8h]
0x1400ba13c  call    VhdmpiCleanupSecurityContext
0x1400ba141  test    ebx, ebx
0x1400ba143  jns     loc_1400BA8B7
0x1400ba149  cmp     [rsp+140h+var_E0], 0
0x1400ba14e  mov     [rsp+140h+var_F0], r14b
0x1400ba153  jz      loc_1400BA89B
0x1400ba159  test    dword ptr [rsi+38h], 100h
0x1400ba160  jnz     short loc_1400BA172
0x1400ba162  xor     r8d, r8d
0x1400ba165  lea     rcx, [r15+48h]; char
0x1400ba169  lea     edx, [r8+1]
0x1400ba16d  call    VhdmpiFileWrapperNotifyCSVFSLoopbackMount
0x1400ba172  test    r15, r15
0x1400ba175  jz      loc_1400BA89B
0x1400ba17b  lea     rcx, [r15+48h]; char
0x1400ba17f  xor     r8d, r8d
0x1400ba182  xor     edx, edx
0x1400ba184  call    VhdmpiFileWrapperNotifyCSVFSLoopbackMount
0x1400ba189  mov     r15, [r15+478h]
0x1400ba190  test    r15, r15
0x1400ba193  jnz     short loc_1400BA17B
0x1400ba195  mov     r14, [rsp+140h+var_E8]
0x1400ba19a  jmp     loc_1400BA8A8
0x1400ba19f  mov     rax, [rbp+40h+var_C0]
0x1400ba1a3  jmp     loc_1400BA0EC
0x1400ba1a8  lea     rcx, [r12+0B8h]
0x1400ba1b0  call    VhdmpiAcquirePassiveLock
0x1400ba1b5  movzx   r9d, [rsp+140h+var_ED]
0x1400ba1bb  mov     r14b, 1
0x1400ba1be  mov     rcx, [rsp+140h+var_D0]; struct _VHD_HANDLE_CONTEXT *
0x1400ba1c3  xor     r9d, 1
0x1400ba1c7  shl     r9d, 9
  ... truncated ...
```
