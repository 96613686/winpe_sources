# SrvAdminProcessFsctl

- ea: `0x140011cb8`
- end: `0x14001298f`
- name: `SrvAdminProcessFsctl`
- size: `3287`
- prototype: ``
- caller_count: `1`
- callee_count: `54`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140050940`

## callees

- `0x140004d30`
- `0x140007360`
- `0x140007700`
- `0x140007c60`
- `0x14000a1f0`
- `0x14000c550`
- `0x14000ed94`
- `0x140011cb8`
- `0x14001389c`
- `0x1400138e0`
- `0x1400139bc`
- `0x140014808`
- `0x140015790`
- `0x140016384`
- `0x14001f0b4`
- `0x14001f244`
- `0x14001f640`
- `0x1400220a8`
- `0x140023ae0`
- `0x140023be0`
- `0x140023c20`
- `0x140023f90`
- `0x1400254a0`
- `0x1400254d0`
- `0x140025510`
- `0x1400256e0`
- `0x140025730`
- `0x140025740`
- `0x140026730`
- `0x1400269f0`
- `0x140026a60`
- `0x140026e00`
- `0x140026e90`
- `0x140027040`
- `0x140027150`
- `0x140027220`
- `0x140027390`
- `0x140027450`
- `0x140027470`
- `0x1400276e0`
- `0x140027750`
- `0x1400277b0`
- `0x140027b80`
- `0x140027bf0`
- `0x140027c50`
- `0x140027ce0`
- `0x14002a3e0`
- `0x14002a410`
- `0x14002a4c0`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!IoQueueWorkItemEx` at `0x140012096`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140012096`
- `ntoskrnl!MmUnlockPages` at `0x14001289c`
- `ntoskrnl!MmUnlockPages` at `0x14001289c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140012031`
- `ntoskrnl!MmProbeAndLockPages` at `0x140012655`
- `ntoskrnl!MmProbeAndLockPages` at `0x140012031`
- `ntoskrnl!MmProbeAndLockPages` at `0x140012655`
- `ntoskrnl!IoAllocateMdl` at `0x140011fef`
- `ntoskrnl!IoAllocateMdl` at `0x14001231e`
- `ntoskrnl!IoAllocateMdl` at `0x140011fef`
- `ntoskrnl!IoAllocateMdl` at `0x14001231e`
- `ntoskrnl!IoFreeMdl` at `0x1400128b0`
- `ntoskrnl!IoFreeMdl` at `0x1400128b0`
- `ntoskrnl!IoClearActivityIdThread` at `0x14001292f`
- `ntoskrnl!IoClearActivityIdThread` at `0x14001292f`
- `ntoskrnl!ExAllocatePool2` at `0x140011f08`
- `ntoskrnl!ExAllocatePool2` at `0x140011f74`
- `ntoskrnl!ExAllocatePool2` at `0x140011f08`
- `ntoskrnl!ExAllocatePool2` at `0x140011f74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001293b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001293b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011d37`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011d37`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011ed7`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011ed7`
- `ntoskrnl!ProbeForRead` at `0x140011f45`
- `ntoskrnl!ProbeForRead` at `0x1400126ae`
- `ntoskrnl!ProbeForRead` at `0x140011f45`
- `ntoskrnl!ProbeForRead` at `0x1400126ae`
- `ntoskrnl!IofCompleteRequest` at `0x14001295d`
- `ntoskrnl!IofCompleteRequest` at `0x14001295d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012062`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012062`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140011fae`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140011fae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012009`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400120b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400120d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001210d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012128`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001215d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400128d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400128fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011f8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012009`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400120b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400120d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001210d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012128`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001215d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400128d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400128fc`
- `ntoskrnl!IoFreeWorkItem` at `0x140011f24`
- `ntoskrnl!IoFreeWorkItem` at `0x1400120ed`
- `ntoskrnl!IoFreeWorkItem` at `0x140012141`
- `ntoskrnl!IoFreeWorkItem` at `0x14001217b`
- `ntoskrnl!IoFreeWorkItem` at `0x140011f24`
- `ntoskrnl!IoFreeWorkItem` at `0x1400120ed`
- `ntoskrnl!IoFreeWorkItem` at `0x140012141`
- `ntoskrnl!IoFreeWorkItem` at `0x14001217b`

## pseudocode

```c
__int64 __fastcall SrvAdminProcessFsctl(
        size_t a1,
        __int64 a2,
        unsigned __int64 a3,
        int a4,
        unsigned int *Address,
        ULONG Length,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        KPROCESSOR_MODE AccessMode,
        PIRP a11)
{
  int v12; // r9d
  bool v13; // zf
  unsigned int v14; // eax
  int NameList; // eax
  int updated; // edi
  unsigned int v17; // eax
  struct _IO_WORKITEM *WorkItem; // rdi
  void *Pool2; // r15
  struct _IRP *v20; // rax
  struct _MDL *v21; // rax
  struct _MDL *v22; // rbx
  __int64 v24; // rdx
  unsigned __int64 v25; // r8
  unsigned int v26; // eax
  struct _MDL *v27; // r15
  _QWORD *PoolWithTag; // rax
  _QWORD *v29; // rbx
  struct _MDL *Mdl; // rax
  int v31; // r8d
  __int64 v32; // rdx
  int v33; // eax
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rax
  char v37; // dl
  struct _IO_WORKITEM *v38; // rax
  __int64 v39; // rax
  unsigned __int64 v40; // rcx
  size_t v41; // r8
  __int64 v42; // rax
  char *v43; // rcx
  __int64 v44; // rax
  char *v45; // rcx
  PIO_WORKITEM v46; // r8
  _QWORD *v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  PIRP Irp; // [rsp+20h] [rbp-D8h]
  char v54; // [rsp+40h] [rbp-B8h]
  char v55; // [rsp+41h] [rbp-B7h]
  _DWORD Size[3]; // [rsp+44h] [rbp-B4h] BYREF
  PIO_WORKITEM IoWorkItem; // [rsp+50h] [rbp-A8h]
  PVOID P; // [rsp+58h] [rbp-A0h]
  __int64 v59; // [rsp+60h] [rbp-98h]
  size_t v60[2]; // [rsp+68h] [rbp-90h] BYREF
  struct _MDL *v61; // [rsp+78h] [rbp-80h]
  PVOID VirtualAddress[2]; // [rsp+80h] [rbp-78h] BYREF
  int v63; // [rsp+94h] [rbp-64h]
  __int64 v64; // [rsp+98h] [rbp-60h] BYREF
  __int128 v65; // [rsp+A0h] [rbp-58h] BYREF

  Size[0] = a4;
  v60[0] = a1;
  VirtualAddress[0] = Address;
  *(_QWORD *)&Size[1] = a11;
  v59 = *(_QWORD *)(a1 + 24);
  v65 = 0;
  v64 = 0;
  KeEnterCriticalRegion();
  v63 = SvcSetActivityIdForCurrentThread(a11, &v65, &v64);
  if ( a7 > 0x146067 )
  {
    if ( a7 <= 0x146093 )
    {
      if ( a7 == 1335443 )
      {
        SrvAdminMarkHandleAsClusSvc(v60[0]);
        updated = 0;
        goto LABEL_191;
      }
      if ( a7 > 0x14607F )
      {
        v13 = a7 == 1335427;
        v14 = a7 - 1335427;
      }
      else
      {
        if ( a7 == 1335423 || a7 == 1335403 )
          goto LABEL_80;
        v14 = a7 - 1335407;
        v13 = a7 == 1335407;
      }
      goto LABEL_76;
    }
    switch ( a7 )
    {
      case 0x146097u:
        NameList = SvcNodeResetInfo(v59, 0, 0, 0);
        goto LABEL_190;
      case 0x14609Fu:
      case 0x1460A3u:
        goto LABEL_80;
      case 0x1460A4u:
        Size[1] = 0;
        if ( Size[0] < 0xCu )
        {
          updated = -1073741811;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              12,
              WPP_b5f9d596a2403a8baa719df916c96a72_Traceguids,
              3221225485LL);
          }
          goto LABEL_191;
        }
        if ( Length - 1 > 6 )
        {
          LODWORD(Irp) = Length;
          updated = SrvNetListenerRuleEntryUpdate(
                      *(unsigned __int16 *)a3,
                      *(unsigned __int8 *)(a3 + 2),
                      *(_DWORD *)(a3 + 4),
                      *(_DWORD *)(a3 + 8),
                      (size_t)Irp,
                      Address,
                      (__int64)&Size[1]);
          if ( (int)(updated + 0x80000000) >= 0 && updated != -2147483643 )
            goto LABEL_191;
          v36 = Size[1];
LABEL_137:
          *(_QWORD *)(a8 + 8) = v36;
          goto LABEL_191;
        }
        updated = -1073741789;
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_191;
        }
        v35 = 13;
        break;
      case 0x1460A8u:
        if ( Length >= 8 && Address )
        {
          v33 = SrvNetListenerRuleEnumAllEntries(Address, Length);
LABEL_116:
          updated = v33;
          if ( (int)(v33 + 0x80000000) >= 0 && v33 != -2147483643 )
            goto LABEL_191;
          v36 = *Address;
          goto LABEL_137;
        }
        updated = -1073741789;
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_191;
        }
        v35 = 14;
        break;
      case 0x1460ACu:
        if ( Length >= 8 && Address )
        {
          v33 = SrvNetListenerEnumEndpoints(Address, Length);
          goto LABEL_116;
        }
        updated = -1073741789;
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_191;
        }
        v35 = 15;
        break;
      default:
        switch ( a7 )
        {
          case 0x148088u:
            *(_OWORD *)v60 = 0;
            *(_OWORD *)VirtualAddress = 0;
            if ( Size[0] < 8u )
              goto LABEL_33;
            v31 = *(unsigned __int16 *)(a3 + 2);
            v32 = *(unsigned __int16 *)(a3 + 4);
            if ( Size[0] < (unsigned int)(v32 + v31 + 6) )
              goto LABEL_33;
            LOWORD(VirtualAddress[0]) = *(_WORD *)(a3 + 4);
            WORD1(VirtualAddress[0]) = v32;
            VirtualAddress[1] = (PVOID)(a3 + 6);
            LOWORD(v60[0]) = v31;
            WORD1(v60[0]) = v31;
            v60[1] = a3 + 6 + v32;
            LOBYTE(v12) = *(_BYTE *)a3;
            NameList = SrvAdminModifyShareDfsBits(
                         v59,
                         (unsigned int)VirtualAddress,
                         (unsigned int)v60,
                         v12,
                         *(_BYTE *)a3);
            break;
          case 0x14808Cu:
            NameList = SrvAdminModifyShareDfsBits(v59, 0, 0, 0, 0);
            break;
          case 0x148090u:
            if ( !a11 || a11->RequestorMode )
            {
              updated = -1073741808;
              goto LABEL_191;
            }
            NameList = SrvAdminDfsServerFilterAttach(1343632);
            break;
          default:
            goto LABEL_33;
        }
        goto LABEL_190;
    }
    WPP_SF_Dd(v34->AttachedDevice, v35, WPP_b5f9d596a2403a8baa719df916c96a72_Traceguids, Length, -1073741789);
    goto LABEL_191;
  }
  if ( a7 == 1335399 )
    goto LABEL_80;
  if ( a7 > 0x146033 )
  {
    if ( a7 > 0x146053 )
    {
      if ( a7 != 1335380 )
      {
        if ( a7 == 1335387 )
          goto LABEL_80;
        v17 = a7 - 1335391;
        if ( a7 == 1335391 )
          goto LABEL_30;
        goto LABEL_79;
      }
      v60[0] = 1179666;
      v60[1] = (size_t)L"LocalHost";
      *(_QWORD *)(a8 + 8) = 0;
      if ( Size[0] < 0x60u )
        goto LABEL_33;
      v24 = *(unsigned __int16 *)a3;
      if ( !(_WORD)v24 )
        goto LABEL_33;
      *(_QWORD *)(a3 + 8) += a3;
      v25 = *(_QWORD *)(a3 + 8);
      if ( v25 < a3 || (unsigned int)v24 > Size[0] || v25 > a3 + Size[0] - v24 || (v25 & 1) != 0 )
      {
        updated = -1073741819;
        goto LABEL_191;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b5f9d596a2403a8baa719df916c96a72_Traceguids);
      }
      NameList = SrvLibAllocateNameList(a3, v60, &SrvAdminNameLock, &SrvAdminServerNameList);
    }
    else
    {
      if ( a7 == 1335379 )
      {
        updated = SvcUpdateNetname(v59, 0, 0, 0);
        if ( !updated
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            (unsigned int)(updated + 11),
            WPP_b5f9d596a2403a8baa719df916c96a72_Traceguids);
        }
        goto LABEL_191;
      }
      if ( a7 == 1335351 || a7 == 1335359 || a7 == 1335363 || a7 == 1335367 )
        goto LABEL_80;
      if ( a7 != 1335371 )
        goto LABEL_33;
      NameList = SvcShareCleanup(v59, 0, 0, 0);
    }
LABEL_190:
    updated = NameList;
    goto LABEL_191;
  }
  if ( a7 == 1335347 )
    goto LABEL_80;
  if ( a7 > 0x14601F )
  {
    v13 = a7 == 1335331;
    v14 = a7 - 1335331;
LABEL_76:
    if ( !v13 )
    {
      v26 = v14 - 4;
      if ( v26 )
      {
        v17 = v26 - 4;
        if ( v17 )
        {
LABEL_79:
          if ( v17 == 4 )
            goto LABEL_80;
LABEL_33:
          updated = -1073741811;
          goto LABEL_191;
        }
      }
    }
LABEL_80:
    if ( a7 == 1335339 || (v54 = 0, a7 == 1335351) )
      v54 = 1;
    if ( Size[0] < 0x60u )
      goto LABEL_33;
    IoWorkItem = 0;
    v27 = 0;
    v61 = 0;
    v55 = 0;
    v60[0] = Size[0];
    PoolWithTag = (_QWORD *)SrvNetAllocatePoolWithTag(258, Size[0], 1684095315);
    v29 = PoolWithTag;
    P = PoolWithTag;
    if ( !PoolWithTag )
      goto LABEL_36;
    memmove(PoolWithTag, (const void *)a3, v60[0]);
    if ( Length )
    {
      Mdl = IoAllocateMdl(VirtualAddress[0], Length, 0, 1u, 0);
      v27 = Mdl;
      v61 = Mdl;
      if ( !Mdl )
      {
LABEL_87:
        updated = -1073741670;
LABEL_183:
        if ( v55 )
          MmUnlockPages(v27);
        if ( v27 )
          IoFreeMdl(v27);
        SrvNetUpdateMemStatistics(*((unsigned int *)v29 - 3), *((unsigned int *)v29 - 4), 0);
        ExFreePoolWithTag(v29 - 2, 0);
        if ( IoWorkItem )
        {
          SrvNetUpdateMemStatistics(*((unsigned int *)IoWorkItem - 3), *((unsigned int *)IoWorkItem - 4), 0);
          ExFreePoolWithTag((char *)IoWorkItem - 16, 0);
        }
        goto LABEL_191;
      }
      MmProbeAndLockPages(Mdl, AccessMode, IoWriteAccess);
      v55 = 1;
      v37 = v54;
      if ( v54 )
      {
        v38 = (struct _IO_WORKITEM *)SrvNetAllocatePoolWithTag(258, Length, 1684095315);
        IoWorkItem = v38;
        if ( !v38 )
          goto LABEL_87;
        if ( AccessMode == 1 )
        {
          ProbeForRead(VirtualAddress[0], Length, 1u);
          v38 = IoWorkItem;
        }
        memmove(v38, VirtualAddress[0], Length);
        v37 = v54;
      }
    }
    else
    {
      v37 = v54;
    }
    v39 = v29[1];
    if ( v39 )
    {
      v40 = (unsigned __int64)v29 + v39;
      v29[1] = (char *)v29 + v39;
    }
    else
    {
      v40 = 0;
    }
    if ( v40 )
    {
      if ( v40 <= (unsigned __int64)v29 || (v41 = v60[0], v40 >= (unsigned __int64)v29 + v60[0]) )
      {
LABEL_150:
        updated = -1073741819;
        goto LABEL_183;
      }
    }
    else
    {
      v41 = v60[0];
    }
    v42 = v29[3];
    if ( v42 )
    {
      v43 = (char *)v29 + v42;
      v29[3] = (char *)v29 + v42;
    }
    else
    {
      v43 = 0;
    }
    if ( !v43 || v43 > (char *)v29 && v43 < (char *)v29 + v41 )
    {
      v44 = v29[5];
      if ( v44 )
      {
        v45 = (char *)v29 + v44;
        v29[5] = (char *)v29 + v44;
      }
      else
      {
        v45 = 0;
      }
      if ( !v45 || v45 > (char *)v29 && v45 < (char *)v29 + Size[0] )
      {
        if ( v37 )
        {
          v46 = IoWorkItem;
        }
        else if ( v27 )
        {
          v46 = (PIO_WORKITEM)((char *)v27->StartVa + v27->ByteOffset);
        }
        else
        {
          v46 = 0;
        }
        updated = ((__int64 (__fastcall *)(__int64, _QWORD *, PIO_WORKITEM, _QWORD))SvcApiDispatch[(a7 >> 2) & 0x7FF])(
                    v59,
                    v29,
                    v46,
                    Length);
        memmove((void *)a3, v29, Size[0]);
        if ( updated >= 0 && v54 && IoWorkItem && Length >= 0x50 )
        {
          v47 = (char *)v27->StartVa + v27->ByteOffset;
          if ( *v47 )
            *v47 += v47;
          v48 = v47[7];
          if ( v48 )
            v47[7] = (char *)v47 + v48;
          v49 = v47[2];
          if ( v49 )
            v47[2] = (char *)v47 + v49;
          v50 = v47[5];
          if ( v50 )
            v47[5] = (char *)v47 + v50;
          v51 = v47[9];
          if ( v51 )
            v47[9] = (char *)v47 + v51;
        }
        goto LABEL_183;
      }
    }
    goto LABEL_150;
  }
  if ( a7 == 1335327 || a7 == 1335299 || a7 == 1335303 || a7 == 1335307 )
    goto LABEL_80;
  if ( a7 != 1335319 && a7 != 1335323 )
    goto LABEL_33;
LABEL_30:
  if ( !a11 )
  {
    updated = -1073741637;
    goto LABEL_191;
  }
  if ( Size[0] < 0x60u || !Length )
    goto LABEL_33;
  WorkItem = IoAllocateWorkItem(SrvAdminDeviceObject);
  IoWorkItem = WorkItem;
  if ( !WorkItem )
  {
LABEL_36:
    updated = -1073741670;
    goto LABEL_191;
  }
  Pool2 = (void *)ExAllocatePool2(258, Length, 1684095315);
  P = Pool2;
  if ( !Pool2 )
  {
LABEL_38:
    IoFreeWorkItem(WorkItem);
    goto LABEL_36;
  }
  if ( a11->RequestorMode == 1 )
    ProbeForRead(Address, Length, 1u);
  memmove(Pool2, Address, Length);
  a11->UserBuffer = Pool2;
  v20 = (struct _IRP *)ExAllocatePool2(258, Size[0], 1684095315);
  a11->AssociatedIrp.MasterIrp = v20;
  if ( !v20 )
  {
LABEL_42:
    ExFreePoolWithTag(Pool2, 0);
    a11->UserBuffer = 0;
    goto LABEL_38;
  }
  if ( a11->RequestorMode )
  {
    if ( (a3 & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(v20, (void *)a3, Size[0]);
  }
  else
  {
    RtlCopyVolatileMemory(v20, (const void *)a3, Size[0]);
  }
  v21 = IoAllocateMdl((PVOID)a3, 0x60u, 0, 0, a11);
  v22 = v21;
  if ( !v21 )
    goto LABEL_49;
  if ( a11->RequestorMode == 1 )
    MmProbeAndLockPages(v21, 1, IoWriteAccess);
  if ( !((v22->MdlFlags & 5) != 0
       ? v22->MappedSystemVa
       : MmMapLockedPagesSpecifyCache(v22, 0, MmCached, 0, 0, 0x40000010u)) )
  {
LABEL_49:
    ExFreePoolWithTag(a11->AssociatedIrp.MasterIrp, 0);
    a11->AssociatedIrp.MasterIrp = 0;
    goto LABEL_42;
  }
  a11->IoStatus.Status = 259;
  a11->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  IoQueueWorkItemEx(WorkItem, SrvAdminProcessFsctlFsp, CriticalWorkQueue, a11);
  updated = 259;
LABEL_191:
  if ( v63 >= 0 )
    IoClearActivityIdThread(v64);
  KeLeaveCriticalRegion();
  if ( updated != 259 && a11 )
  {
    a11->IoStatus.Status = updated;
    IofCompleteRequest(a11, 2);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140011cb8  mov     r11, rsp
0x140011cbb  push    rbx
0x140011cbc  push    rsi
0x140011cbd  push    rdi
0x140011cbe  push    r12
0x140011cc0  push    r13
0x140011cc2  push    r14
0x140011cc4  push    r15
0x140011cc6  sub     rsp, 0C0h
0x140011ccd  mov     rax, cs:__security_cookie
0x140011cd4  xor     rax, rsp
0x140011cd7  mov     [rsp+0F8h+var_48], rax
0x140011cdf  mov     dword ptr [rsp+0F8h+Size], r9d
0x140011ce4  mov     r12, r8
0x140011ce7  mov     [rsp+0F8h+var_90], rcx
0x140011cec  mov     rbx, [rsp+0F8h+Address]
0x140011cf4  mov     [rsp+0F8h+VirtualAddress], rbx
0x140011cfc  mov     r13d, dword ptr [rsp+0F8h+Length]
0x140011d04  mov     edi, [rsp+0F8h+arg_30]
0x140011d0b  mov     r15, [rsp+0F8h+arg_38]
0x140011d13  mov     r14, [rsp+0F8h+arg_50]
0x140011d1b  mov     qword ptr [rsp+0F8h+Size+4], r14
0x140011d20  mov     rax, [rcx+18h]
0x140011d24  mov     [rsp+0F8h+var_98], rax
0x140011d29  xorps   xmm0, xmm0
0x140011d2c  movups  xmmword ptr [r11-58h], xmm0
0x140011d31  xor     esi, esi
0x140011d33  mov     [r11-60h], rsi
0x140011d37  call    cs:__imp_KeEnterCriticalRegion
0x140011d3e  nop     dword ptr [rax+rax+00h]
0x140011d43  lea     r8, [rsp+0F8h+var_60]
0x140011d4b  lea     rdx, [rsp+0F8h+var_58]
0x140011d53  mov     rcx, r14
0x140011d56  call    SvcSetActivityIdForCurrentThread
0x140011d5b  mov     [rsp+0F8h+var_64], eax
0x140011d62  mov     eax, 146067h
0x140011d67  cmp     edi, eax
0x140011d69  ja      loc_140012245
0x140011d6f  jz      loc_14001228D
0x140011d75  mov     eax, 146033h
0x140011d7a  cmp     edi, eax
0x140011d7c  ja      short loc_140011DD5
0x140011d7e  jz      loc_14001228D
0x140011d84  mov     eax, 14601Fh
0x140011d89  cmp     edi, eax
0x140011d8b  ja      short loc_140011DC9
0x140011d8d  jz      loc_14001228D
0x140011d93  mov     eax, edi
0x140011d95  sub     eax, 146003h
0x140011d9a  jz      loc_14001228D
0x140011da0  sub     eax, 4
0x140011da3  jz      loc_14001228D
0x140011da9  sub     eax, 4
0x140011dac  jz      loc_14001228D
0x140011db2  sub     eax, 0Ch
0x140011db5  jz      loc_140011EAB
0x140011dbb  cmp     eax, 4
0x140011dbe  jnz     loc_140011EC1
0x140011dc4  jmp     loc_140011EAB
0x140011dc9  mov     eax, edi
0x140011dcb  sub     eax, 146023h
0x140011dd0  jmp     loc_140012278
0x140011dd5  mov     eax, 146053h
0x140011dda  cmp     edi, eax
0x140011ddc  ja      loc_140011E8C
0x140011de2  jz      short loc_140011E2C
0x140011de4  mov     eax, edi
0x140011de6  sub     eax, 146037h
0x140011deb  jz      loc_14001228D
0x140011df1  sub     eax, 8
0x140011df4  jz      loc_14001228D
0x140011dfa  sub     eax, 4
0x140011dfd  jz      loc_14001228D
0x140011e03  sub     eax, 4
0x140011e06  jz      loc_14001228D
0x140011e0c  cmp     eax, 4
0x140011e0f  jnz     loc_140011EC1
0x140011e15  xor     r9d, r9d
0x140011e18  xor     r8d, r8d
0x140011e1b  xor     edx, edx
0x140011e1d  mov     rcx, [rsp+0F8h+var_98]
0x140011e22  call    SvcShareCleanup
0x140011e27  jmp     loc_14001291C
0x140011e2c  xor     r9d, r9d
0x140011e2f  xor     r8d, r8d
0x140011e32  xor     edx, edx
0x140011e34  mov     rcx, [rsp+0F8h+var_98]
0x140011e39  call    SvcUpdateNetname
0x140011e3e  mov     edi, eax
0x140011e40  test    eax, eax
0x140011e42  jnz     loc_14001291E
0x140011e48  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140011e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e56  cmp     rcx, rax
0x140011e59  jz      loc_14001291E
0x140011e5f  mov     eax, [rcx+2Ch]
0x140011e62  test    al, 20h
0x140011e64  jz      loc_14001291E
0x140011e6a  cmp     byte ptr [rcx+29h], 2
0x140011e6e  jb      loc_14001291E
0x140011e74  lea     edx, [rdi+0Bh]
0x140011e77  lea     r8, WPP_b5f9d596a2403a8baa719df916c96a72_Traceguids
0x140011e7e  mov     rcx, [rcx+18h]
0x140011e82  call    WPP_SF_
0x140011e87  jmp     loc_14001291E
0x140011e8c  mov     eax, edi
0x140011e8e  sub     eax, 146054h
0x140011e93  jz      loc_14001218E
0x140011e99  sub     eax, 7
0x140011e9c  jz      loc_14001228D
0x140011ea2  sub     eax, 4
0x140011ea5  jnz     loc_140012284
0x140011eab  test    r14, r14
0x140011eae  jnz     short loc_140011EBA
0x140011eb0  mov     edi, 0C00000BBh
0x140011eb5  jmp     loc_14001291E
0x140011eba  cmp     dword ptr [rsp+0F8h+Size], 60h ; '`'
0x140011ebf  jnb     short loc_140011ECB
0x140011ec1  mov     edi, 0C000000Dh
0x140011ec6  jmp     loc_14001291E
0x140011ecb  test    r13d, r13d
0x140011ece  jz      short loc_140011EC1
0x140011ed0  mov     rcx, cs:SrvAdminDeviceObject; DeviceObject
0x140011ed7  call    cs:__imp_IoAllocateWorkItem
0x140011ede  nop     dword ptr [rax+rax+00h]
0x140011ee3  mov     rdi, rax
0x140011ee6  mov     [rsp+0F8h+IoWorkItem], rax
0x140011eeb  test    rax, rax
0x140011eee  jnz     short loc_140011EFA
0x140011ef0  mov     edi, 0C000009Ah
0x140011ef5  jmp     loc_14001291E
0x140011efa  mov     r8d, 64614153h
0x140011f00  mov     rdx, r13
0x140011f03  mov     ecx, 102h
0x140011f08  call    cs:__imp_ExAllocatePool2
0x140011f0f  nop     dword ptr [rax+rax+00h]
0x140011f14  mov     r15, rax
0x140011f17  mov     [rsp+0F8h+P], rax
0x140011f1c  test    rax, rax
0x140011f1f  jnz     short loc_140011F32
0x140011f21  mov     rcx, rdi; IoWorkItem
0x140011f24  call    cs:__imp_IoFreeWorkItem
0x140011f2b  nop     dword ptr [rax+rax+00h]
0x140011f30  jmp     short loc_140011EF0
0x140011f32  cmp     byte ptr [r14+40h], 1
0x140011f37  jnz     short loc_140011F51
0x140011f39  mov     r8d, 1; Alignment
0x140011f3f  mov     rdx, r13; Length
0x140011f42  mov     rcx, rbx; Address
0x140011f45  call    cs:__imp_ProbeForRead
0x140011f4c  nop     dword ptr [rax+rax+00h]
0x140011f51  mov     r8, r13; Size
0x140011f54  mov     rdx, rbx; Src
0x140011f57  mov     rcx, r15; void *
0x140011f5a  call    memmove
0x140011f5f  mov     [r14+70h], r15
0x140011f63  mov     ebx, dword ptr [rsp+0F8h+Size]
0x140011f67  mov     r8d, 64614153h
0x140011f6d  mov     edx, ebx
0x140011f6f  mov     ecx, 102h
0x140011f74  call    cs:__imp_ExAllocatePool2
0x140011f7b  nop     dword ptr [rax+rax+00h]
0x140011f80  mov     [r14+18h], rax
0x140011f84  test    rax, rax
0x140011f87  jnz     short loc_140011FA0
0x140011f89  xor     edx, edx; Tag
0x140011f8b  mov     rcx, r15; P
0x140011f8e  call    cs:__imp_ExFreePoolWithTag
0x140011f95  nop     dword ptr [rax+rax+00h]
0x140011f9a  mov     [r14+70h], rsi
0x140011f9e  jmp     short loc_140011F21
0x140011fa0  mov     cl, [r14+40h]
0x140011fa4  test    cl, cl
0x140011fa6  jz      short loc_140011FCE
0x140011fa8  test    r12b, 7
0x140011fac  jz      short loc_140011FBA
0x140011fae  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140011fb5  nop     dword ptr [rax+rax+00h]
0x140011fba  test    cl, cl
0x140011fbc  jz      short loc_140011FCE
0x140011fbe  mov     r8, rbx; Size
0x140011fc1  mov     rdx, r12; Src
0x140011fc4  mov     rcx, rax; void *
0x140011fc7  call    RtlCopyFromUser
0x140011fcc  jmp     short loc_140011FDD
0x140011fce  mov     r8, rbx; Size
0x140011fd1  mov     rdx, r12; Src
0x140011fd4  mov     rcx, rax; void *
0x140011fd7  call    RtlCopyVolatileMemory
0x140011fdc  nop
0x140011fdd  mov     [rsp+0F8h+Irp], r14; Irp
0x140011fe2  xor     r9d, r9d; ChargeQuota
0x140011fe5  xor     r8d, r8d; SecondaryBuffer
0x140011fe8  lea     edx, [r9+60h]; Length
0x140011fec  mov     rcx, r12; VirtualAddress
0x140011fef  call    cs:__imp_IoAllocateMdl
0x140011ff6  nop     dword ptr [rax+rax+00h]
0x140011ffb  mov     rbx, rax
0x140011ffe  test    rax, rax
0x140012001  jnz     short loc_14001201E
0x140012003  xor     edx, edx; Tag
0x140012005  mov     rcx, [r14+18h]; P
0x140012009  call    cs:__imp_ExFreePoolWithTag
0x140012010  nop     dword ptr [rax+rax+00h]
0x140012015  mov     [r14+18h], rsi
0x140012019  jmp     loc_140011F89
0x14001201e  cmp     byte ptr [r14+40h], 1
0x140012023  jnz     short loc_14001203E
0x140012025  mov     r8d, 1; Operation
0x14001202b  mov     dl, r8b; AccessMode
0x14001202e  mov     rcx, rbx; MemoryDescriptorList
0x140012031  call    cs:__imp_MmProbeAndLockPages
0x140012038  nop     dword ptr [rax+rax+00h]
0x14001203d  nop
0x14001203e  test    byte ptr [rbx+0Ah], 5
0x140012042  jz      short loc_14001204A
0x140012044  mov     rax, [rbx+18h]
0x140012048  jmp     short loc_14001206E
0x14001204a  mov     [rsp+0F8h+Priority], 40000010h; Priority
0x140012052  mov     dword ptr [rsp+0F8h+Irp], esi; BugCheckOnFailure
0x140012056  xor     r9d, r9d; RequestedAddress
0x140012059  xor     edx, edx; AccessMode
0x14001205b  lea     r8d, [r9+1]; CacheType
0x14001205f  mov     rcx, rbx; MemoryDescriptorList
0x140012062  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140012069  nop     dword ptr [rax+rax+00h]
0x14001206e  test    rax, rax
0x140012071  jz      short loc_140012003
0x140012073  mov     dword ptr [r14+30h], 103h
0x14001207b  mov     rax, [r14+0B8h]
0x140012082  or      byte ptr [rax+3], 1
0x140012086  mov     r9, r14; Context
0x140012089  xor     r8d, r8d; QueueType
0x14001208c  lea     rdx, SrvAdminProcessFsctlFsp; WorkerRoutine
0x140012093  mov     rcx, rdi; IoWorkItem
0x140012096  call    cs:__imp_IoQueueWorkItemEx
0x14001209d  nop     dword ptr [rax+rax+00h]
0x1400120a2  mov     edi, 103h
0x1400120a7  jmp     loc_14001291E
0x1400120ac  mov     edi, eax
0x1400120ae  xor     edx, edx; Tag
0x1400120b0  mov     r14, qword ptr [rsp+0F8h+Size+4]
0x1400120b5  mov     rcx, [r14+18h]; P
0x1400120b9  call    cs:__imp_ExFreePoolWithTag
0x1400120c0  nop     dword ptr [rax+rax+00h]
0x1400120c5  mov     qword ptr [r14+18h], 0
0x1400120cd  xor     edx, edx; Tag
0x1400120cf  mov     rcx, [rsp+0F8h+P]; P
0x1400120d4  call    cs:__imp_ExFreePoolWithTag
0x1400120db  nop     dword ptr [rax+rax+00h]
0x1400120e0  mov     qword ptr [r14+70h], 0
0x1400120e8  mov     rcx, [rsp+0F8h+IoWorkItem]; IoWorkItem
0x1400120ed  call    cs:__imp_IoFreeWorkItem
0x1400120f4  nop     dword ptr [rax+rax+00h]
0x1400120f9  xor     esi, esi
0x1400120fb  jmp     loc_14001291E
0x140012100  mov     edi, eax
0x140012102  xor     edx, edx; Tag
0x140012104  mov     r14, qword ptr [rsp+0F8h+Size+4]
0x140012109  mov     rcx, [r14+18h]; P
0x14001210d  call    cs:__imp_ExFreePoolWithTag
0x140012114  nop     dword ptr [rax+rax+00h]
0x140012119  mov     qword ptr [r14+18h], 0
0x140012121  xor     edx, edx; Tag
0x140012123  mov     rcx, [rsp+0F8h+P]; P
0x140012128  call    cs:__imp_ExFreePoolWithTag
0x14001212f  nop     dword ptr [rax+rax+00h]
0x140012134  mov     qword ptr [r14+70h], 0
0x14001213c  mov     rcx, [rsp+0F8h+IoWorkItem]; IoWorkItem
0x140012141  call    cs:__imp_IoFreeWorkItem
0x140012148  nop     dword ptr [rax+rax+00h]
0x14001214d  xor     esi, esi
0x14001214f  jmp     loc_14001291E
0x140012154  mov     edi, eax
0x140012156  xor     edx, edx; Tag
0x140012158  mov     rcx, [rsp+0F8h+P]; P
0x14001215d  call    cs:__imp_ExFreePoolWithTag
0x140012164  nop     dword ptr [rax+rax+00h]
0x140012169  mov     r14, qword ptr [rsp+0F8h+Size+4]
0x14001216e  mov     qword ptr [r14+70h], 0
0x140012176  mov     rcx, [rsp+0F8h+IoWorkItem]; IoWorkItem
0x14001217b  call    cs:__imp_IoFreeWorkItem
0x140012182  nop     dword ptr [rax+rax+00h]
0x140012187  xor     esi, esi
0x140012189  jmp     loc_14001291E
0x14001218e  mov     [rsp+0F8h+var_90], 120012h
0x140012197  lea     rax, aLocalhost; "LocalHost"
0x14001219e  mov     [rsp+0F8h+var_90+8], rax
0x1400121a3  mov     [r15+8], rsi
0x1400121a7  mov     ecx, dword ptr [rsp+0F8h+Size]
0x1400121ab  cmp     ecx, 60h ; '`'
0x1400121ae  jb      loc_140011EC1
0x1400121b4  movzx   edx, word ptr [r12]
0x1400121b9  test    dx, dx
0x1400121bc  jz      loc_140011EC1
0x1400121c2  add     [r12+8], r12
0x1400121c7  mov     r8, [r12+8]
0x1400121cc  cmp     r8, r12
0x1400121cf  jb      short loc_14001223B
0x1400121d1  cmp     edx, ecx
  ... truncated ...
```
