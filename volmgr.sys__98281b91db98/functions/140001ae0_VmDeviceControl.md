# VmDeviceControl

- ea: `0x140001ae0`
- end: `0x140002905`
- name: `VmDeviceControl`
- size: `3621`
- prototype: `NTSTATUS __fastcall(__int64, struct _IRP *)`
- caller_count: `0`
- callee_count: `43`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400014d0`
- `0x140001ae0`
- `0x140002910`
- `0x1400029e0`
- `0x140002a30`
- `0x140003e70`
- `0x140003ef0`
- `0x140005090`
- `0x14000e010`
- `0x14000e270`
- `0x14000e300`
- `0x14000e400`
- `0x14000f3b0`
- `0x14000fbf8`
- `0x140010814`
- `0x1400109d4`
- `0x140012128`
- `0x14001218c`
- `0x140012524`
- `0x14001256c`
- `0x140012710`
- `0x140012d60`
- `0x140012db4`
- `0x140012f18`
- `0x140013138`
- `0x1400131bc`
- `0x1400134c8`
- `0x140013674`
- `0x140013e00`
- `0x1400156d0`
- `0x140015800`
- `0x140015ae0`
- `0x140015bb0`
- `0x140015d10`
- `0x140015d30`
- `0x140015d70`
- `0x140016130`
- `0x140016320`
- `0x140016540`
- `0x140016680`
- `0x140016760`
- `0x140016a60`
- `0x140016ff0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140001c63`
- `ntoskrnl!KeReleaseMutex` at `0x140001c75`
- `ntoskrnl!KeReleaseMutex` at `0x140001c63`
- `ntoskrnl!KeReleaseMutex` at `0x140001c75`
- `ntoskrnl!IofCallDriver` at `0x14000251f`
- `ntoskrnl!IofCallDriver` at `0x14000251f`
- `ntoskrnl!IofCompleteRequest` at `0x140001b66`
- `ntoskrnl!IofCompleteRequest` at `0x140001be0`
- `ntoskrnl!IofCompleteRequest` at `0x140001c89`
- `ntoskrnl!IofCompleteRequest` at `0x140001db3`
- `ntoskrnl!IofCompleteRequest` at `0x140001f43`
- `ntoskrnl!IofCompleteRequest` at `0x140001b66`
- `ntoskrnl!IofCompleteRequest` at `0x140001be0`
- `ntoskrnl!IofCompleteRequest` at `0x140001c89`
- `ntoskrnl!IofCompleteRequest` at `0x140001db3`
- `ntoskrnl!IofCompleteRequest` at `0x140001f43`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001c06`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001c23`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001c06`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001c23`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001b52`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001d50`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001e42`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140002402`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400028b6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001b52`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001d50`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140001e42`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140002402`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400028b6`

## pseudocode

```c
NTSTATUS __fastcall VmDeviceControl(__int64 a1, struct _IRP *a2)
{
  __int64 v2; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  __int64 v5; // r14
  unsigned int LowPart; // eax
  NTSTATUS result; // eax
  int Capabilities; // esi
  int DeviceName; // eax
  _QWORD *v10; // rsi
  NTSTATUS GptAttributes; // edi
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  char v16; // cl
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  char v21; // cl
  struct VM_VOLUME_EXTENSION *v22; // rcx
  char v23; // cl
  NTSTATUS v24; // edi
  struct VM_VOLUME_EXTENSION *v25; // rcx
  char v26; // cl
  char v27; // cl
  char v28; // cl
  char v29; // cl
  unsigned int v30; // eax
  char v31; // cl
  unsigned int v32; // eax
  char v33; // cl
  unsigned int v34; // eax
  char v35; // cl
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  struct _IO_STACK_LOCATION *v39; // rax
  bool v40; // zf
  struct _IO_STACK_LOCATION *v41; // rcx
  void *v42; // rax
  NTSTATUS SuggestedLinkName; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  struct VM_VOLUME_EXTENSION *v50; // rcx
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax

  v2 = *(_QWORD *)(a1 + 64);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = *(_QWORD *)(v2 + 8);
  a2->IoStatus.Information = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( !*(_DWORD *)(v2 + 16) )
  {
    if ( LowPart != 7783344 )
    {
      if ( LowPart > 0x76C340 )
      {
        switch ( LowPart )
        {
          case 0x76C344u:
          case 0x76C348u:
          case 0x76C34Cu:
          case 0x76C350u:
          case 0x76C354u:
          case 0x76C358u:
          case 0x76C35Cu:
          case 0x76C360u:
          case 0x76C364u:
          case 0x76C368u:
          case 0x76C36Cu:
          case 0x76C370u:
          case 0x76C374u:
          case 0x76C378u:
          case 0x76C37Cu:
          case 0x76C380u:
          case 0x76C384u:
          case 0x76C388u:
          case 0x76C38Cu:
          case 0x76C390u:
          case 0x76C3A4u:
          case 0x76C3A8u:
            goto LABEL_171;
          default:
            goto LABEL_29;
        }
      }
      if ( LowPart == 7783232 )
      {
        Capabilities = VmpCheckDynamicDiskConversion((struct VM_ROOT_EXTENSION *)v5, a2);
        if ( Capabilities < 0 )
          goto LABEL_9;
      }
      else
      {
        if ( LowPart > 0x764324 )
        {
          switch ( LowPart )
          {
            case 0x764328u:
            case 0x76432Cu:
            case 0x764330u:
            case 0x764334u:
            case 0x764338u:
            case 0x76433Cu:
            case 0x764394u:
            case 0x764398u:
            case 0x76439Cu:
            case 0x7643A0u:
            case 0x7643ACu:
              goto LABEL_171;
            default:
              goto LABEL_29;
          }
        }
        if ( LowPart != 7750436 )
        {
          if ( LowPart != 7734048 )
            goto LABEL_29;
          VmpAcquireAll((struct VM_ROOT_EXTENSION *)v5);
          Capabilities = VmpQueryCapabilities((struct VM_ROOT_EXTENSION *)v5, a2);
          goto LABEL_173;
        }
      }
    }
LABEL_171:
    if ( !*(_QWORD *)(v5 + 392) )
      goto LABEL_29;
    VmpAcquireAll((struct VM_ROOT_EXTENSION *)v5);
    VmpRestoreExtensionDriver(v5);
    Capabilities = (*(__int64 (__fastcall **)(struct _IRP *))(*(_QWORD *)(v5 + 392) + 96LL))(a2);
    VmpPageExtensionDriver(v5);
LABEL_173:
    VmpReleaseAll((struct VM_ROOT_EXTENSION *)v5);
    if ( Capabilities != 259 )
      goto LABEL_9;
    return 259;
  }
  if ( LowPart == 5046280 )
  {
    result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
    Capabilities = result;
    if ( result == 259 )
      return result;
    if ( *(_BYTE *)(v2 + 156) )
    {
      if ( result >= 0 )
      {
        DeviceName = VmpQueryDeviceName((struct VM_VOLUME_EXTENSION *)v2, a2);
LABEL_7:
        Capabilities = DeviceName;
LABEL_8:
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 112));
      }
LABEL_9:
      a2->IoStatus.Status = Capabilities;
      IofCompleteRequest(a2, 0);
      return Capabilities;
    }
LABEL_176:
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 112));
    Capabilities = -1073741810;
    goto LABEL_9;
  }
  if ( LowPart == 5636152 )
  {
    KeWaitForSingleObject((PVOID)(v5 + 56), Executive, 0, 0, 0);
    KeWaitForSingleObject((PVOID)(v5 + 112), Executive, 0, 0, 0);
    v10 = (_QWORD *)(v5 + 184);
    if ( (_QWORD *)*v10 != v10 )
      VmpProcessDiskNotifications((struct VM_ROOT_EXTENSION *)v5);
    GptAttributes = VmpGetGptAttributes((struct VM_VOLUME_EXTENSION *)v2, a2);
    if ( (_QWORD *)*v10 != v10 )
      VmpProcessDiskNotifications((struct VM_ROOT_EXTENSION *)v5);
    KeReleaseMutex((PRKMUTEX)(v5 + 112), 0);
    KeReleaseMutex((PRKMUTEX)(v5 + 56), 0);
    a2->IoStatus.Status = GptAttributes;
    IofCompleteRequest(a2, 0);
    return GptAttributes;
  }
  if ( LowPart <= 0x560000 )
  {
    if ( LowPart == 5636096 )
      goto LABEL_70;
    if ( LowPart <= 0x2D08C0 )
    {
      if ( LowPart == 2951360 )
        return VmpManageBypassIo((struct VM_VOLUME_EXTENSION *)v2, a2);
      if ( LowPart > 0x70224 )
      {
        v12 = LowPart - 475140;
        if ( !v12 )
          return VmpGetPartitionInfo((struct VM_VOLUME_EXTENSION *)v2, a2);
        v13 = v12 - 88;
        if ( !v13 )
          return VmpGetLengthInfo((struct VM_VOLUME_EXTENSION *)v2, a2);
        if ( v13 != 32776 )
          goto LABEL_34;
LABEL_29:
        Capabilities = -1073741808;
        goto LABEL_9;
      }
      if ( LowPart == 459300 )
        goto LABEL_29;
      v17 = LowPart - 458784;
      if ( !v17 )
      {
        v24 = VmpPerformance((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_80;
      }
      v18 = v17 - 4;
      if ( v18 )
      {
        v19 = v18 - 36;
        if ( !v19 )
          return VmpGetPartitionInfoEx((struct VM_VOLUME_EXTENSION *)v2, a2);
        if ( v19 == 24 )
        {
          VmpPerformanceOff((struct VM_VOLUME_EXTENSION *)v2, a2);
          a2->IoStatus.Status = 0;
          IofCompleteRequest(a2, 0);
          return 0;
        }
        goto LABEL_34;
      }
      if ( _bittest64((const signed __int64 *)(v2 + 312), 0x3Cu) )
      {
        Capabilities = -1073741662;
        goto LABEL_9;
      }
      Capabilities = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
      if ( Capabilities == 259 )
        goto LABEL_40;
      if ( *(_BYTE *)(v2 + 426) )
      {
        if ( *(_QWORD *)(v2 + 432) )
          goto LABEL_90;
      }
      else if ( *(_QWORD *)(v2 + 344) )
      {
LABEL_90:
        v26 = 1;
LABEL_91:
        if ( *(_BYTE *)(v2 + 156) && v26 )
        {
          if ( !*(_BYTE *)(v2 + 160) )
          {
            if ( Capabilities >= 0 )
              return VmpDiskIsWritable((struct VM_VOLUME_EXTENSION *)v2, a2);
            goto LABEL_40;
          }
          goto LABEL_60;
        }
        goto LABEL_39;
      }
      v26 = 0;
      goto LABEL_91;
    }
    if ( LowPart != 5046296 )
    {
      if ( LowPart <= 0x4D0018 )
      {
        v20 = LowPart - 2987012;
        if ( v20 )
        {
          v30 = v20 - 2059260;
          if ( !v30 )
          {
            result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
            Capabilities = result;
            if ( result != 259 )
            {
              if ( *(_BYTE *)(v2 + 426) )
              {
                if ( !*(_QWORD *)(v2 + 432) )
                  goto LABEL_176;
              }
              else if ( !*(_QWORD *)(v2 + 344) )
              {
                goto LABEL_176;
              }
              if ( result < 0 )
                goto LABEL_9;
              DeviceName = VmpQueryUniqueId((struct VM_VOLUME_EXTENSION *)v2, a2);
              goto LABEL_7;
            }
            return result;
          }
          if ( v30 == 12 )
          {
            VmpAcquireAll((struct VM_ROOT_EXTENSION *)v5);
            SuggestedLinkName = VmpQuerySuggestedLinkName((struct VM_VOLUME_EXTENSION *)v2, a2);
LABEL_211:
            v24 = SuggestedLinkName;
            VmpReleaseAll((struct VM_ROOT_EXTENSION *)v5);
            goto LABEL_80;
          }
          goto LABEL_34;
        }
        Capabilities = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
        if ( Capabilities == 259 )
          goto LABEL_40;
        if ( *(_BYTE *)(v2 + 426) )
        {
          if ( *(_QWORD *)(v2 + 432) )
            goto LABEL_56;
        }
        else if ( *(_QWORD *)(v2 + 344) )
        {
LABEL_56:
          v21 = 1;
LABEL_57:
          if ( *(_BYTE *)(v2 + 156) && v21 )
          {
            if ( !*(_BYTE *)(v2 + 160) )
              goto LABEL_40;
LABEL_60:
            ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 112));
            Capabilities = -2147483632;
            goto LABEL_40;
          }
LABEL_39:
          ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 112));
          Capabilities = -1073741810;
          goto LABEL_40;
        }
        v21 = 0;
        goto LABEL_57;
      }
      v32 = LowPart - 5046300;
      if ( !v32 )
      {
        result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
        Capabilities = result;
        if ( result == 259 )
          return result;
        if ( *(_BYTE *)(v2 + 426) )
        {
          if ( *(_QWORD *)(v2 + 432) )
            goto LABEL_143;
        }
        else if ( *(_QWORD *)(v2 + 344) )
        {
LABEL_143:
          v33 = 1;
LABEL_144:
          if ( *(_BYTE *)(v2 + 156) && v33 )
          {
            if ( result < 0 )
              goto LABEL_9;
            DeviceName = VmpQueryInterfaceName((struct VM_VOLUME_EXTENSION *)v2, a2);
            goto LABEL_7;
          }
          goto LABEL_176;
        }
        v33 = 0;
        goto LABEL_144;
      }
      v34 = v32 - 49140;
      if ( v34 )
      {
        if ( v34 != 4 )
          goto LABEL_34;
        v44 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 0);
        Capabilities = v44;
        if ( v44 == 259 )
          return 259;
        if ( v44 < 0 )
          goto LABEL_9;
LABEL_160:
        DeviceName = VmpLinkCreated((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_7;
      }
      result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
      Capabilities = result;
      if ( result == 259 )
        return result;
      if ( *(_BYTE *)(v2 + 426) )
      {
        if ( *(_QWORD *)(v2 + 432) )
          goto LABEL_156;
      }
      else if ( *(_QWORD *)(v2 + 344) )
      {
LABEL_156:
        v35 = 1;
        goto LABEL_157;
      }
      v35 = 0;
LABEL_157:
      if ( !*(_BYTE *)(v2 + 156) || !v35 )
        goto LABEL_176;
      if ( result < 0 )
        goto LABEL_9;
      goto LABEL_160;
    }
    result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
    Capabilities = result;
    if ( result == 259 )
      return result;
    if ( *(_BYTE *)(v2 + 426) )
    {
      if ( *(_QWORD *)(v2 + 432) )
        goto LABEL_117;
    }
    else if ( *(_QWORD *)(v2 + 344) )
    {
LABEL_117:
      v29 = 1;
LABEL_118:
      if ( *(_BYTE *)(v2 + 156) && v29 )
      {
        if ( result < 0 )
          goto LABEL_9;
        DeviceName = VmpQueryStableGuid((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_7;
      }
      goto LABEL_176;
    }
    v29 = 0;
    goto LABEL_118;
  }
  if ( LowPart > 0x564000 )
  {
    if ( LowPart > 0x56C040 )
    {
      v14 = LowPart - 5685316;
      if ( v14 )
      {
        v15 = v14 - 8;
        if ( v15 )
        {
          if ( v15 != 16 )
            goto LABEL_34;
          v53 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 0);
          Capabilities = v53;
          if ( v53 == 259 )
            return 259;
          if ( v53 < 0 )
            goto LABEL_9;
LABEL_69:
          DeviceName = VmpPrepareForCriticalIo(v22, a2);
          goto LABEL_7;
        }
        result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
        Capabilities = result;
        if ( result == 259 )
          return result;
        if ( *(_BYTE *)(v2 + 426) )
        {
          if ( *(_QWORD *)(v2 + 432) )
            goto LABEL_64;
        }
        else if ( *(_QWORD *)(v2 + 344) )
        {
LABEL_64:
          LOBYTE(v22) = 1;
          goto LABEL_65;
        }
        LOBYTE(v22) = 0;
LABEL_65:
        if ( !*(_BYTE *)(v2 + 156) || !(_BYTE)v22 )
          goto LABEL_176;
        if ( *(_BYTE *)(v2 + 160) )
        {
          ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 112));
          Capabilities = -2147483632;
          goto LABEL_9;
        }
        if ( result < 0 )
          goto LABEL_9;
        goto LABEL_69;
      }
      v54 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 1);
      Capabilities = v54;
      if ( v54 != 259 )
      {
        if ( v54 < 0 )
          goto LABEL_9;
        DeviceName = VmpFreeBCStream((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_7;
      }
      return 259;
    }
    if ( LowPart == 5685312 )
    {
      v52 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 1);
      Capabilities = v52;
      if ( v52 != 259 )
      {
        if ( v52 < 0 )
          goto LABEL_9;
        DeviceName = VmpAllocateBCStream((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_7;
      }
      return 259;
    }
    v36 = LowPart - 5652540;
    if ( !v36 )
    {
      v51 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 0);
      Capabilities = v51;
      if ( v51 != 259 )
      {
        if ( v51 < 0 )
          goto LABEL_9;
        DeviceName = VmpGetBCProperties((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_7;
      }
      return 259;
    }
    v37 = v36 - 28;
    if ( !v37 )
    {
      v49 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 0);
      Capabilities = v49;
      if ( v49 != 259 )
      {
        if ( v49 < 0 )
          goto LABEL_9;
        DeviceName = VmpQueryMinimumShrinkSize(v50, a2);
        goto LABEL_7;
      }
      return 259;
    }
    v38 = v37 - 32688;
    if ( !v38 )
      return VmpOnline((struct VM_VOLUME_EXTENSION *)v2, a2);
    if ( v38 == 4 )
      return VmpOffline((struct VM_VOLUME_EXTENSION *)v2, a2);
LABEL_34:
    Capabilities = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
    if ( Capabilities == 259 )
    {
LABEL_40:
      if ( Capabilities == 259 )
        return 259;
      if ( Capabilities < 0 )
        goto LABEL_9;
      v39 = a2->Tail.Overlay.CurrentStackLocation;
      v40 = *(_BYTE *)(v2 + 426) == 0;
      *(_OWORD *)&v39[-1].MajorFunction = *(_OWORD *)&v39->MajorFunction;
      *(_OWORD *)&v39[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v39->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v39[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v39->Parameters.SetQuota + 6);
      v39[-1].FileObject = v39->FileObject;
      v39[-1].Control = 0;
      v41 = a2->Tail.Overlay.CurrentStackLocation;
      v42 = (void *)CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      v41[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)VmpRefCountCompletionRoutine;
      v41[-1].Context = v42;
      v41[-1].Control = -32;
      if ( v40 )
        return IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 344), a2);
      --a2->CurrentLocation;
      --a2->Tail.Overlay.CurrentStackLocation;
      result = (*(__int64 (__fastcall **)(_QWORD, struct _IRP *))(*(_QWORD *)(v5 + 392) + 104LL))(
                 *(_QWORD *)(v2 + 432),
                 a2);
      v24 = result;
      if ( result == 259 )
        return result;
LABEL_80:
      a2->IoStatus.Status = v24;
      IofCompleteRequest(a2, 0);
      return v24;
    }
    if ( *(_BYTE *)(v2 + 426) )
    {
      if ( *(_QWORD *)(v2 + 432) )
        goto LABEL_37;
    }
    else if ( *(_QWORD *)(v2 + 344) )
    {
LABEL_37:
      v16 = 1;
LABEL_38:
      if ( *(_BYTE *)(v2 + 156) && v16 )
        goto LABEL_40;
      goto LABEL_39;
    }
    v16 = 0;
    goto LABEL_38;
  }
  if ( LowPart != 5652480 )
  {
    switch ( LowPart )
    {
      case 0x560004u:
        a2->IoStatus.Status = 0;
        IofCompleteRequest(a2, 0);
        return 0;
      case 0x560010u:
        result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
        Capabilities = result;
        if ( result == 259 )
          return result;
        if ( *(_BYTE *)(v2 + 426) )
        {
          if ( *(_QWORD *)(v2 + 432) )
            goto LABEL_100;
        }
        else if ( *(_QWORD *)(v2 + 344) )
        {
LABEL_100:
          v27 = 1;
          goto LABEL_101;
        }
        v27 = 0;
LABEL_101:
        if ( *(_BYTE *)(v2 + 156) && v27 )
        {
          if ( result < 0 )
            goto LABEL_9;
          if ( !*(_BYTE *)(v2 + 160) )
            Capabilities = -1073741823;
          goto LABEL_8;
        }
        goto LABEL_176;
      case 0x560014u:
        v45 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 0);
        Capabilities = v45;
        if ( v45 == 259 )
          return 259;
        if ( v45 >= 0 )
          goto LABEL_8;
        goto LABEL_9;
      case 0x560018u:
        VmpAcquireAll((struct VM_ROOT_EXTENSION *)v5);
        SuggestedLinkName = VmpQueryFailoverSet((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_211;
      case 0x56001Cu:
        v46 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 0);
        Capabilities = v46;
        if ( v46 == 259 )
          return 259;
        if ( v46 < 0 )
          goto LABEL_9;
        DeviceName = VmpQueryVolumeNumber((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_7;
      case 0x560020u:
        v47 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 0);
        Capabilities = v47;
        if ( v47 == 259 )
          return 259;
        if ( v47 < 0 )
          goto LABEL_9;
        DeviceName = VmpLogicalToPhysical((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_7;
      case 0x560024u:
        v48 = VmpAllSystemsGo((struct VM_VOLUME_EXTENSION *)v2, a2, 1u, 1u, 0);
        Capabilities = v48;
        if ( v48 == 259 )
          return 259;
        if ( v48 < 0 )
          goto LABEL_9;
        DeviceName = VmpPhysicalToLogical((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_7;
      case 0x560028u:
        result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
        Capabilities = result;
        if ( result == 259 )
          return result;
        if ( *(_BYTE *)(v2 + 426) )
        {
          if ( *(_QWORD *)(v2 + 432) )
            goto LABEL_134;
        }
        else if ( *(_QWORD *)(v2 + 344) )
        {
LABEL_134:
          v31 = 1;
          goto LABEL_135;
        }
        v31 = 0;
LABEL_135:
        if ( *(_BYTE *)(v2 + 156) && v31 )
        {
          if ( result < 0 )
            goto LABEL_9;
          DeviceName = VmpIsPartition((struct VM_VOLUME_EXTENSION *)v2, a2);
          goto LABEL_7;
        }
        goto LABEL_176;
      case 0x560034u:
        Capabilities = VmpCheckSecurity((struct VM_VOLUME_EXTENSION *)v2, a2);
        if ( Capabilities < 0 )
          goto LABEL_40;
        VmpAcquireAll((struct VM_ROOT_EXTENSION *)v5);
        SuggestedLinkName = VmpSetGptAttributes((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_211;
      case 0x560048u:
        result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
        Capabilities = result;
        if ( result == 259 )
          return result;
        if ( *(_BYTE *)(v2 + 426) )
        {
          if ( *(_QWORD *)(v2 + 432) )
            goto LABEL_109;
        }
        else if ( *(_QWORD *)(v2 + 344) )
        {
LABEL_109:
          v28 = 1;
          goto LABEL_110;
        }
        v28 = 0;
LABEL_110:
        if ( *(_BYTE *)(v2 + 156) && v28 )
        {
          if ( result < 0 )
            goto LABEL_9;
          DeviceName = VmpIsDynamic((struct VM_VOLUME_EXTENSION *)v2, a2);
          goto LABEL_7;
        }
        goto LABEL_176;
      case 0x560054u:
        VmpAcquireAll((struct VM_ROOT_EXTENSION *)v5);
        SuggestedLinkName = VmpUpdateProperties((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_211;
      case 0x560060u:
        result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
        Capabilities = result;
        if ( result == 259 )
          return result;
        if ( *(_BYTE *)(v2 + 426) )
        {
          if ( !*(_QWORD *)(v2 + 432) )
            goto LABEL_176;
        }
        else if ( !*(_QWORD *)(v2 + 344) )
        {
          goto LABEL_176;
        }
        if ( result < 0 )
          goto LABEL_9;
        DeviceName = VmpIsCsv(v25, a2);
        goto LABEL_7;
      default:
        goto LABEL_34;
    }
  }
LABEL_70:
  result = VmpAcquireRundownShared((struct VM_VOLUME_EXTENSION *)v2, a2);
  Capabilities = result;
  if ( result != 259 )
  {
    if ( *(_BYTE *)(v2 + 426) )
    {
      if ( *(_QWORD *)(v2 + 432) )
        goto LABEL_73;
    }
    else if ( *(_QWORD *)(v2 + 344) )
    {
LABEL_73:
      v23 = 1;
LABEL_74:
      if ( *(_BYTE *)(v2 + 156) && v23 )
      {
        if ( result < 0 )
          goto LABEL_9;
        DeviceName = VmpGetVolumeDiskExtents((struct VM_VOLUME_EXTENSION *)v2, a2);
        goto LABEL_7;
      }
      goto LABEL_176;
    }
    v23 = 0;
    goto LABEL_74;
  }
  return result;
}

```

## disassembly

```asm
0x140001ae0  mov     [rsp+arg_8], rbx
0x140001ae5  mov     [rsp+arg_10], rbp
0x140001aea  push    rsi
0x140001aeb  push    rdi
0x140001aec  push    r14
0x140001aee  sub     rsp, 30h
0x140001af2  mov     rdi, [rcx+40h]
0x140001af6  xor     esi, esi
0x140001af8  mov     rbp, [rdx+0B8h]
0x140001aff  mov     rbx, rdx
0x140001b02  mov     r14, [rdi+8]
0x140001b06  mov     [rdx+38h], rsi
0x140001b0a  mov     eax, [rbp+18h]
0x140001b0d  cmp     [rdi+10h], esi
0x140001b10  jz      loc_140002391
0x140001b16  cmp     eax, 4D0008h
0x140001b1b  jnz     short loc_140001B88
0x140001b1d  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001b20  call    ?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)
0x140001b25  mov     esi, eax
0x140001b27  cmp     eax, 103h
0x140001b2c  jz      short loc_140001B74
0x140001b2e  movzx   eax, byte ptr [rdi+9Ch]
0x140001b35  test    al, al
0x140001b37  jz      loc_1400023FE
0x140001b3d  test    esi, esi
0x140001b3f  js      short loc_140001B5E
0x140001b41  mov     rdx, rbx; struct _IRP *
0x140001b44  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001b47  call    ?VmpQueryDeviceName@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpQueryDeviceName(VM_VOLUME_EXTENSION *,_IRP *)
0x140001b4c  mov     esi, eax
0x140001b4e  mov     rcx, [rdi+70h]; RunRefCacheAware
0x140001b52  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140001b59  nop     dword ptr [rax+rax+00h]
0x140001b5e  xor     edx, edx; PriorityBoost
0x140001b60  mov     [rbx+30h], esi
0x140001b63  mov     rcx, rbx; Irp
0x140001b66  call    cs:__imp_IofCompleteRequest
0x140001b6d  nop     dword ptr [rax+rax+00h]
0x140001b72  mov     eax, esi
0x140001b74  mov     rbx, [rsp+48h+arg_8]
0x140001b79  mov     rbp, [rsp+48h+arg_10]
0x140001b7e  add     rsp, 30h
0x140001b82  pop     r14
0x140001b84  pop     rdi
0x140001b85  pop     rsi
0x140001b86  retn
0x140001b88  cmp     eax, 560038h
0x140001b8d  jz      short loc_140001BF0
0x140001b8f  cmp     eax, 560000h
0x140001b94  jbe     loc_140001CA1
0x140001b9a  cmp     eax, 564000h
0x140001b9f  ja      loc_140001CE8
0x140001ba5  jz      loc_140001EC3
0x140001bab  add     eax, 0FFA9FFFCh; switch 93 cases
0x140001bb0  cmp     eax, 5Ch
0x140001bb3  ja      def_140001BD2; jumptable 0000000140001BD2 default case, cases 5636101-5636111,5636113-5636115,5636117-5636119,5636121-5636123,5636125-5636127,5636129-5636131,5636133-5636135,5636137-5636147,5636149-5636167,5636169-5636179,5636181-5636191
0x140001bb9  lea     rdx, cs:140000000h
0x140001bc0  movzx   eax, ds:(byte_140007CD5 - 140000000h)[rdx+rax]
0x140001bc8  mov     ecx, ds:(jpt_140001BD2 - 140000000h)[rdx+rax*4]
0x140001bcf  add     rcx, rdx
0x140001bd2  jmp     rcx; switch jump
0x140001bd8  xor     edx, edx; jumptable 0000000140001BD2 case 5636100
0x140001bda  mov     [rbx+30h], esi
0x140001bdd  mov     rcx, rbx; Irp
0x140001be0  call    cs:__imp_IofCompleteRequest
0x140001be7  nop     dword ptr [rax+rax+00h]
0x140001bec  xor     eax, eax
0x140001bee  jmp     short loc_140001B74
0x140001bf0  xor     r9d, r9d; Alertable
0x140001bf3  mov     [rsp+48h+arg_0], r15
0x140001bf8  xor     r8d, r8d; WaitMode
0x140001bfb  mov     [rsp+48h+Timeout], rsi; Timeout
0x140001c00  xor     edx, edx; WaitReason
0x140001c02  lea     rcx, [r14+38h]; Object
0x140001c06  call    cs:__imp_KeWaitForSingleObject
0x140001c0d  nop     dword ptr [rax+rax+00h]
0x140001c12  xor     r9d, r9d; Alertable
0x140001c15  mov     [rsp+48h+Timeout], rsi; Timeout
0x140001c1a  xor     r8d, r8d; WaitMode
0x140001c1d  lea     rcx, [r14+70h]; Object
0x140001c21  xor     edx, edx; WaitReason
0x140001c23  call    cs:__imp_KeWaitForSingleObject
0x140001c2a  nop     dword ptr [rax+rax+00h]
0x140001c2f  lea     rsi, [r14+0B8h]
0x140001c36  cmp     [rsi], rsi
0x140001c39  jz      short loc_140001C43
0x140001c3b  mov     rcx, r14; struct VM_ROOT_EXTENSION *
0x140001c3e  call    ?VmpProcessDiskNotifications@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpProcessDiskNotifications(VM_ROOT_EXTENSION *)
0x140001c43  mov     rdx, rbx; struct _IRP *
0x140001c46  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001c49  call    ?VmpGetGptAttributes@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpGetGptAttributes(VM_VOLUME_EXTENSION *,_IRP *)
0x140001c4e  mov     edi, eax
0x140001c50  cmp     [rsi], rsi
0x140001c53  jz      short loc_140001C5D
0x140001c55  mov     rcx, r14; struct VM_ROOT_EXTENSION *
0x140001c58  call    ?VmpProcessDiskNotifications@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpProcessDiskNotifications(VM_ROOT_EXTENSION *)
0x140001c5d  xor     edx, edx; Wait
0x140001c5f  lea     rcx, [r14+70h]; Mutex
0x140001c63  call    cs:__imp_KeReleaseMutex
0x140001c6a  nop     dword ptr [rax+rax+00h]
0x140001c6f  xor     edx, edx; Wait
0x140001c71  lea     rcx, [r14+38h]; Mutex
0x140001c75  call    cs:__imp_KeReleaseMutex
0x140001c7c  nop     dword ptr [rax+rax+00h]
0x140001c81  xor     edx, edx; PriorityBoost
0x140001c83  mov     [rbx+30h], edi
0x140001c86  mov     rcx, rbx; Irp
0x140001c89  call    cs:__imp_IofCompleteRequest
0x140001c90  nop     dword ptr [rax+rax+00h]
0x140001c95  mov     r15, [rsp+48h+arg_0]
0x140001c9a  mov     eax, edi
0x140001c9c  jmp     loc_140001B74
0x140001ca1  jz      loc_140001EC3
0x140001ca7  cmp     eax, 2D08C0h
0x140001cac  ja      loc_140001DCC
0x140001cb2  jz      loc_14000233D
0x140001cb8  cmp     eax, 70224h
0x140001cbd  jbe     loc_140001D77
0x140001cc3  sub     eax, 74004h
0x140001cc8  jz      loc_140002330
0x140001cce  sub     eax, 58h ; 'X'
0x140001cd1  jz      loc_14000201B
0x140001cd7  cmp     eax, 8008h
0x140001cdc  jnz     short def_140001BD2; jumptable 0000000140001BD2 default case, cases 5636101-5636111,5636113-5636115,5636117-5636119,5636121-5636123,5636125-5636127,5636129-5636131,5636133-5636135,5636137-5636147,5636149-5636167,5636169-5636179,5636181-5636191
0x140001cde  mov     esi, 0C0000010h; jumptable 00000001400025C8 default case, cases 7750441-7750443,7750445-7750447,7750449-7750451,7750453-7750455,7750457-7750459,7750461-7750547,7750549-7750551,7750553-7750555,7750557-7750559,7750561-7750571
0x140001ce3  jmp     loc_140001B5E
0x140001ce8  cmp     eax, 56C040h
0x140001ced  jbe     loc_14000235F
0x140001cf3  sub     eax, 56C044h
0x140001cf8  jz      loc_1400028CC
0x140001cfe  sub     eax, 8
0x140001d01  jz      loc_140001E58
0x140001d07  cmp     eax, 10h
0x140001d0a  jz      loc_14000287C
0x140001d10  mov     rdx, rbx; jumptable 0000000140001BD2 default case, cases 5636101-5636111,5636113-5636115,5636117-5636119,5636121-5636123,5636125-5636127,5636129-5636131,5636133-5636135,5636137-5636147,5636149-5636167,5636169-5636179,5636181-5636191
0x140001d13  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001d16  call    ?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)
0x140001d1b  mov     esi, eax
0x140001d1d  cmp     eax, 103h
0x140001d22  jz      short loc_140001D61
0x140001d24  cmp     byte ptr [rdi+1AAh], 0
0x140001d2b  jnz     loc_1400021AB
0x140001d31  cmp     qword ptr [rdi+158h], 0
0x140001d39  jz      loc_1400021B9
0x140001d3f  mov     cl, 1
0x140001d41  movzx   eax, byte ptr [rdi+9Ch]
0x140001d48  test    al, al
0x140001d4a  jnz     short loc_140001DC6
0x140001d4c  mov     rcx, [rdi+70h]; RunRefCacheAware
0x140001d50  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140001d57  nop     dword ptr [rax+rax+00h]
0x140001d5c  mov     esi, 0C000000Eh
0x140001d61  cmp     esi, 103h
0x140001d67  jnz     loc_1400024BB
0x140001d6d  mov     eax, 103h
0x140001d72  jmp     loc_140001B74
0x140001d77  jz      def_1400025C8; jumptable 00000001400025C8 default case, cases 7750441-7750443,7750445-7750447,7750449-7750451,7750453-7750455,7750457-7750459,7750461-7750547,7750549-7750551,7750553-7750555,7750557-7750559,7750561-7750571
0x140001d7d  sub     eax, 70020h
0x140001d82  jz      loc_140001F31
0x140001d88  sub     eax, 4
0x140001d8b  jz      loc_140001F9E
0x140001d91  sub     eax, 24h ; '$'
0x140001d94  jz      loc_140001F24
0x140001d9a  cmp     eax, 18h
0x140001d9d  jnz     def_140001BD2; jumptable 0000000140001BD2 default case, cases 5636101-5636111,5636113-5636115,5636117-5636119,5636121-5636123,5636125-5636127,5636129-5636131,5636133-5636135,5636137-5636147,5636149-5636167,5636169-5636179,5636181-5636191
0x140001da3  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001da6  call    ?VmpPerformanceOff@@YAXPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpPerformanceOff(VM_VOLUME_EXTENSION *,_IRP *)
0x140001dab  xor     edx, edx; PriorityBoost
0x140001dad  mov     [rbx+30h], esi
0x140001db0  mov     rcx, rbx; Irp
0x140001db3  call    cs:__imp_IofCompleteRequest
0x140001dba  nop     dword ptr [rax+rax+00h]
0x140001dbf  xor     eax, eax
0x140001dc1  jmp     loc_140001B74
0x140001dc6  test    cl, cl
0x140001dc8  jnz     short loc_140001D61
0x140001dca  jmp     short loc_140001D4C
0x140001dcc  cmp     eax, 4D0018h
0x140001dd1  jz      loc_1400020F7
0x140001dd7  ja      loc_14000222E
0x140001ddd  sub     eax, 2D9404h
0x140001de2  jnz     loc_140002158
0x140001de8  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001deb  call    ?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)
0x140001df0  mov     esi, eax
0x140001df2  cmp     eax, 103h
0x140001df7  jz      loc_140001D61
0x140001dfd  cmp     byte ptr [rdi+1AAh], 0
0x140001e04  jnz     loc_14000229A
0x140001e0a  cmp     qword ptr [rdi+158h], 0
0x140001e12  jz      loc_1400022A8
0x140001e18  mov     cl, 1
0x140001e1a  movzx   eax, byte ptr [rdi+9Ch]
0x140001e21  test    al, al
0x140001e23  jz      loc_140001D4C
0x140001e29  test    cl, cl
0x140001e2b  jz      loc_140001D4C
0x140001e31  cmp     byte ptr [rdi+0A0h], 0
0x140001e38  jz      loc_140001D61
0x140001e3e  mov     rcx, [rdi+70h]; RunRefCacheAware
0x140001e42  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140001e49  nop     dword ptr [rax+rax+00h]
0x140001e4e  mov     esi, 80000010h
0x140001e53  jmp     loc_140001D61
0x140001e58  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001e5b  call    ?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)
0x140001e60  mov     esi, eax
0x140001e62  cmp     eax, 103h
0x140001e67  jz      loc_140001B74
0x140001e6d  cmp     byte ptr [rdi+1AAh], 0
0x140001e74  jnz     loc_1400022AF
0x140001e7a  cmp     qword ptr [rdi+158h], 0
0x140001e82  jz      loc_1400022BD
0x140001e88  mov     cl, 1; struct VM_VOLUME_EXTENSION *
0x140001e8a  movzx   eax, byte ptr [rdi+9Ch]
0x140001e91  test    al, al
0x140001e93  jz      loc_1400023FE
0x140001e99  test    cl, cl
0x140001e9b  jz      loc_1400023FE
0x140001ea1  cmp     byte ptr [rdi+0A0h], 0
0x140001ea8  jnz     loc_1400028B2
0x140001eae  test    esi, esi
0x140001eb0  js      loc_140001B5E
0x140001eb6  mov     rdx, rbx; struct _IRP *
0x140001eb9  call    ?VmpPrepareForCriticalIo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpPrepareForCriticalIo(VM_VOLUME_EXTENSION *,_IRP *)
0x140001ebe  jmp     loc_140001B4C
0x140001ec3  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001ec6  call    ?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)
0x140001ecb  mov     esi, eax
0x140001ecd  cmp     eax, 103h
0x140001ed2  jz      loc_140001B74
0x140001ed8  cmp     byte ptr [rdi+1AAh], 0
0x140001edf  jnz     loc_14000234A
0x140001ee5  cmp     qword ptr [rdi+158h], 0
0x140001eed  jz      loc_140002358
0x140001ef3  mov     cl, 1
0x140001ef5  movzx   eax, byte ptr [rdi+9Ch]
0x140001efc  test    al, al
0x140001efe  jz      loc_1400023FE
0x140001f04  test    cl, cl
0x140001f06  jz      loc_1400023FE
0x140001f0c  test    esi, esi
0x140001f0e  js      loc_140001B5E
0x140001f14  mov     rdx, rbx; struct _IRP *
0x140001f17  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001f1a  call    ?VmpGetVolumeDiskExtents@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpGetVolumeDiskExtents(VM_VOLUME_EXTENSION *,_IRP *)
0x140001f1f  jmp     loc_140001B4C
0x140001f24  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001f27  call    ?VmpGetPartitionInfoEx@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpGetPartitionInfoEx(VM_VOLUME_EXTENSION *,_IRP *)
0x140001f2c  jmp     loc_140001B74
0x140001f31  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001f34  call    ?VmpPerformance@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpPerformance(VM_VOLUME_EXTENSION *,_IRP *)
0x140001f39  mov     edi, eax
0x140001f3b  xor     edx, edx; PriorityBoost
0x140001f3d  mov     [rbx+30h], edi
0x140001f40  mov     rcx, rbx; Irp
0x140001f43  call    cs:__imp_IofCompleteRequest
0x140001f4a  nop     dword ptr [rax+rax+00h]
0x140001f4f  mov     eax, edi
0x140001f51  jmp     loc_140001B74
0x140001f56  mov     rdx, rbx; jumptable 0000000140001BD2 case 5636192
0x140001f59  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001f5c  call    ?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)
0x140001f61  mov     esi, eax
0x140001f63  cmp     eax, 103h
0x140001f68  jz      loc_140001B74
0x140001f6e  cmp     byte ptr [rdi+1AAh], 0
0x140001f75  jnz     loc_1400023F0
0x140001f7b  cmp     qword ptr [rdi+158h], 0
0x140001f83  jz      loc_1400023FE
0x140001f89  test    eax, eax
0x140001f8b  js      loc_140001B5E
0x140001f91  mov     rdx, rbx; struct _IRP *
0x140001f94  call    ?VmpIsCsv@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpIsCsv(VM_VOLUME_EXTENSION *,_IRP *)
0x140001f99  jmp     loc_140001B4C
0x140001f9e  bt      qword ptr [rdi+138h], 3Ch ; '<'
0x140001fa7  jb      loc_1400021C0
0x140001fad  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140001fb0  call    ?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)
0x140001fb5  mov     esi, eax
0x140001fb7  cmp     eax, 103h
0x140001fbc  jz      loc_140001D61
0x140001fc2  cmp     byte ptr [rdi+1AAh], 0
0x140001fc9  jnz     loc_140002418
0x140001fcf  cmp     qword ptr [rdi+158h], 0
0x140001fd7  jz      loc_140002426
0x140001fdd  mov     cl, 1
0x140001fdf  movzx   eax, byte ptr [rdi+9Ch]
0x140001fe6  test    al, al
0x140001fe8  jz      loc_140001D4C
0x140001fee  test    cl, cl
0x140001ff0  jz      loc_140001D4C
0x140001ff6  cmp     byte ptr [rdi+0A0h], 0
0x140001ffd  jnz     loc_140001E3E
0x140002003  test    esi, esi
0x140002005  js      loc_140001D61
0x14000200b  mov     rdx, rbx; struct _IRP *
0x14000200e  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140002011  call    ?VmpDiskIsWritable@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z; VmpDiskIsWritable(VM_VOLUME_EXTENSION *,_IRP *)
  ... truncated ...
```
