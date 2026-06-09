# SpControlDeviceControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400b57b0`
- end: `0x1400b5af5`
- name: `?SpControlDeviceControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `837`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `64`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x14002d738`
- `0x14002d9a0`
- `0x14002de54`
- `0x14002e30c`
- `0x140067fc0`
- `0x14008d55c`
- `0x14008d854`
- `0x1400927e0`
- `0x140092d74`
- `0x140092fbc`
- `0x14009365c`
- `0x140093b94`
- `0x140093f68`
- `0x140094274`
- `0x1400944b8`
- `0x140094680`
- `0x140094848`
- `0x14009494c`
- `0x1400949b8`
- `0x140094bd0`
- `0x140094cb8`
- `0x140094e14`
- `0x1400951a0`
- `0x140095338`
- `0x140095a54`
- `0x140095d18`
- `0x1400963a4`
- `0x14009665c`
- `0x1400967bc`
- `0x14009697c`
- `0x140096b90`
- `0x140096e90`
- `0x14009702c`
- `0x140097280`
- `0x140097518`
- `0x140097bdc`
- `0x140097d58`
- `0x1400985a0`
- `0x140098760`
- `0x14009882c`
- `0x140098b78`
- `0x140098cd8`
- `0x14009905c`
- `0x1400991dc`
- `0x140099414`
- `0x1400997a8`
- `0x140099dc8`
- `0x14009a4d4`
- `0x14009aa74`
- `0x14009b068`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1400b57eb`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400b57eb`
- `ntoskrnl!IofCompleteRequest` at `0x1400b5884`
- `ntoskrnl!IofCompleteRequest` at `0x1400b5884`

## pseudocode

```c
__int64 __fastcall SpControlDeviceControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int LowPart; // eax
  unsigned int Pools; // eax
  unsigned int v8; // ebx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  struct _IO_STACK_LOCATION *v26; // rax
  struct _IO_STACK_LOCATION *v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int128 v30; // [rsp+20h] [rbp-28h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  a2->IoStatus.Information = 0;
  v30 = 0;
  if ( (int)IoGetActivityIdIrp(a2, &v30) >= 0 )
  {
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
      McTemplateK0q_EtwWriteTransfer(
        v4,
        AdapterRequestStart,
        &v30,
        CurrentStackLocation->Parameters.Read.ByteOffset.LowPart);
    v26 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v26[-1].MajorFunction = *(_OWORD *)&v26->MajorFunction;
    *(_OWORD *)&v26[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v26->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v26[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v26->Parameters.SetQuota + 6);
    v26[-1].FileObject = v26->FileObject;
    v26[-1].Control = 0;
    v27 = a2->Tail.Overlay.CurrentStackLocation;
    v27[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpControlCompletionRoutine;
    v27[-1].Context = 0;
    v27[-1].Control = -32;
    --a2->CurrentLocation;
    --a2->Tail.Overlay.CurrentStackLocation;
  }
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 15138820 )
  {
    Pools = SpIoctlGetPools(a2);
    goto LABEL_4;
  }
  if ( LowPart > 0xE7C42C )
  {
    if ( LowPart <= 0xE7C80C )
    {
      if ( LowPart == 15190028 )
      {
        Pools = SpIoctlSetSpaceInfo(a2);
      }
      else
      {
        v22 = LowPart - 15189040;
        if ( v22 )
        {
          if ( v22 != 4 )
            goto LABEL_12;
          Pools = SpIoctlUpdateDrives(a2);
        }
        else
        {
          Pools = SpIoctlSetMaintenanceMode(a2);
        }
      }
    }
    else if ( LowPart <= 0xE7CC0C )
    {
      if ( LowPart != 15191052 )
      {
        switch ( LowPart )
        {
          case 0xE7C810u:
            Pools = SpIoctlCreateSpace(a2);
            goto LABEL_4;
          case 0xE7C814u:
            Pools = SpIoctlDeleteSpace(a2);
            goto LABEL_4;
          case 0xE7C818u:
            Pools = SpIoctlRepairSpace(a2);
            goto LABEL_4;
          case 0xE7C81Cu:
            Pools = SpIoctlSetSpaceAttributes(a2);
            goto LABEL_4;
          case 0xE7C820u:
            Pools = SpIoctlAttachSpace(a2);
            goto LABEL_4;
          case 0xE7C824u:
            Pools = SpIoctlDetachSpace(a2);
            goto LABEL_4;
          case 0xE7C828u:
            Pools = SpIoctlSetSpacePriority(a2);
            goto LABEL_4;
          case 0xE7C82Cu:
            Pools = SpIoctlGrowSpace(a2);
            goto LABEL_4;
          case 0xE7C830u:
            Pools = SpIoctlFinalizeSpace(a2);
            goto LABEL_4;
          case 0xE7C834u:
            Pools = SpIoctlUpdateSpaces(a2);
            goto LABEL_4;
          case 0xE7C838u:
            Pools = SpIoctlSetActiveSpaces(a2);
            goto LABEL_4;
          case 0xE7C840u:
            Pools = SpIoctlSnapshotSpace(a2);
            goto LABEL_4;
          case 0xE7C844u:
            Pools = SpIoctlUnlinkSpace(a2);
            goto LABEL_4;
          case 0xE7C848u:
            Pools = SpIoctlAttachSpaceRemote(a2);
            goto LABEL_4;
          case 0xE7C84Cu:
            Pools = SpIoctlSetSpaceQos(a2);
            goto LABEL_4;
          case 0xE7C850u:
            Pools = SpIoctlSetSpacesFlags(a2);
            goto LABEL_4;
          case 0xE7C854u:
            Pools = SpIoctlDetachSpaceRemote(a2);
            goto LABEL_4;
          default:
            goto LABEL_12;
        }
      }
      Pools = SpIoctlStopTask(a2);
    }
    else if ( LowPart <= 0xE7D808 )
    {
      if ( LowPart == 15194120 )
      {
        Pools = SpIoctlSetControlInfo(a2);
      }
      else
      {
        v23 = LowPart - 15192076;
        if ( v23 )
        {
          v24 = v23 - 1024;
          if ( v24 )
          {
            v25 = v24 - 4;
            if ( v25 )
            {
              if ( v25 != 4 )
                goto LABEL_12;
              Pools = SpIoctlDeleteTier(a2);
            }
            else
            {
              Pools = SpIoctlCreateTier(a2);
            }
          }
          else
          {
            Pools = SpIoctlSetTierInfo(a2);
          }
        }
        else
        {
          Pools = SpIoctlSetEnclosureInfo(a2);
        }
      }
    }
    else
    {
      v10 = LowPart - 15194128;
      if ( v10 )
      {
        v11 = v10 - 4;
        if ( v11 )
        {
          if ( v11 != 4 )
            goto LABEL_12;
          Pools = SpIoctlSetControlAttributes(a2);
        }
        else
        {
          Pools = SpIoctlExecuteControlWork(a2);
        }
      }
      else
      {
        Pools = SpIoctlSetControlWork(a2);
      }
    }
  }
  else if ( LowPart == 15189036 )
  {
    Pools = SpIoctlReallocateDrives(a2);
  }
  else if ( LowPart > 0xE71408 )
  {
    if ( LowPart > 0xE7C020 )
    {
      switch ( LowPart )
      {
        case 0xE7C40Cu:
          Pools = SpIoctlSetDriveInfo(a2);
          goto LABEL_4;
        case 0xE7C410u:
          Pools = SpIoctlAddDrives(a2);
          goto LABEL_4;
        case 0xE7C414u:
          Pools = SpIoctlRemoveDrives(a2);
          goto LABEL_4;
        case 0xE7C418u:
          Pools = SpIoctlResetDrive(a2);
          goto LABEL_4;
        case 0xE7C424u:
          Pools = SpIoctlSetMetadataDrives(a2, 0x140000000LL, v5);
          goto LABEL_4;
        case 0xE7C428u:
          Pools = SpIoctlRetireDrives(a2);
          goto LABEL_4;
        default:
          goto LABEL_12;
      }
    }
    if ( LowPart == 15188000 )
    {
      Pools = SpIoctlRebalancePool(a2);
    }
    else if ( LowPart > 0xE7C010 )
    {
      v20 = LowPart - 15187988;
      if ( v20 )
      {
        v21 = v20 - 4;
        if ( v21 )
        {
          if ( v21 != 4 )
            goto LABEL_12;
          Pools = SpIoctlUpgradePool(a2);
        }
        else
        {
          Pools = SpIoctlSetPoolAttributes(a2);
        }
      }
      else
      {
        Pools = SpIoctlDeletePool(a2);
      }
    }
    else if ( LowPart == 15187984 )
    {
      Pools = SpIoctlCreatePool(a2);
    }
    else
    {
      v14 = LowPart - 15144964;
      if ( v14 )
      {
        v19 = v14 - 8;
        if ( v19 )
        {
          if ( v19 != 43008 )
            goto LABEL_12;
          Pools = SpIoctlSetPoolInfo(a2);
        }
        else
        {
          Pools = SpIoctlGetControlWork(a2);
        }
      }
      else
      {
        Pools = SpIoctlGetControlInfo(a2);
      }
    }
  }
  else if ( LowPart == 15143944 )
  {
    Pools = SpIoctlGetTierInfo(a2);
  }
  else if ( LowPart > 0xE70804 )
  {
    if ( LowPart > 0xE71004 )
    {
      v28 = LowPart - 15142920;
      if ( v28 )
      {
        v29 = v28 - 8;
        if ( v29 )
        {
          if ( v29 != 1012 )
            goto LABEL_12;
          Pools = SpIoctlGetTiers(a2);
        }
        else
        {
          Pools = SpIoctlRefreshEnclosure(a2);
        }
      }
      else
      {
        Pools = SpIoctlGetEnclosureInfo(a2);
      }
    }
    else if ( LowPart == 15142916 )
    {
      Pools = SpIoctlGetEnclosures(a2);
    }
    else
    {
      v17 = LowPart - 15140872;
      if ( v17 )
      {
        v18 = v17 - 1020;
        if ( v18 )
        {
          if ( v18 != 4 )
            goto LABEL_12;
          Pools = SpIoctlGetTaskInfo(a2);
        }
        else
        {
          Pools = SpIoctlGetTasks(a2);
        }
      }
      else
      {
        Pools = SpIoctlGetSpaceInfo(a2);
      }
    }
  }
  else if ( LowPart == 15140868 )
  {
    Pools = SpIoctlGetSpaces(a2);
  }
  else if ( LowPart > 0xE70404 )
  {
    v15 = LowPart - 15139848;
    if ( v15 )
    {
      v16 = v15 - 20;
      if ( v16 )
      {
        if ( v16 != 4 )
          goto LABEL_12;
        Pools = SpIoctlRemoveDrivesEstimate(a2);
      }
      else
      {
        Pools = SpIoctlRefreshDrive(a2);
      }
    }
    else
    {
      Pools = SpIoctlGetDriveInfo(a2);
    }
  }
  else if ( LowPart == 15139844 )
  {
    Pools = SpIoctlGetDrives(a2);
  }
  else
  {
    v12 = LowPart - 15138824;
    if ( v12 )
    {
      v13 = v12 - 28;
      if ( v13 )
      {
        if ( v13 == 4 )
        {
          Pools = SpIoctlGetBootVersion(a2);
          goto LABEL_4;
        }
LABEL_12:
        v8 = -1073741808;
        goto LABEL_13;
      }
      Pools = SpIoctlRefreshPool(a2);
    }
    else
    {
      Pools = SpIoctlGetPoolInfo(a2);
    }
  }
LABEL_4:
  v8 = Pools;
  if ( Pools != 259 )
  {
LABEL_13:
    a2->IoStatus.Status = v8;
    IofCompleteRequest(a2, 0);
  }
  return v8;
}

```

## disassembly

```asm
0x1400b57b0  mov     [rsp+arg_0], rbx
0x1400b57b5  push    rdi
0x1400b57b6  sub     rsp, 40h
0x1400b57ba  mov     rax, cs:__security_cookie
0x1400b57c1  xor     rax, rsp
0x1400b57c4  mov     [rsp+48h+var_18], rax
0x1400b57c9  mov     rbx, [rdx+0B8h]
0x1400b57d0  mov     rdi, rdx
0x1400b57d3  xorps   xmm0, xmm0
0x1400b57d6  mov     qword ptr [rdx+38h], 0
0x1400b57de  mov     rcx, rdi
0x1400b57e1  lea     rdx, [rsp+48h+var_28]
0x1400b57e6  movups  [rsp+48h+var_28], xmm0
0x1400b57eb  call    cs:__imp_IoGetActivityIdIrp
0x1400b57f2  nop     dword ptr [rax+rax+00h]
0x1400b57f7  test    eax, eax
0x1400b57f9  jns     loc_1400B592A
0x1400b57ff  mov     eax, [rbx+18h]
0x1400b5802  cmp     eax, 0E70004h
0x1400b5807  jnz     loc_1400B5892
0x1400b580d  mov     rcx, rdi; struct _IRP *
0x1400b5810  call    ?SpIoctlGetPools@@YAJPEAU_IRP@@@Z; SpIoctlGetPools(_IRP *)
0x1400b5815  mov     ebx, eax
0x1400b5817  cmp     eax, 103h
0x1400b581c  jnz     short loc_1400B587C
0x1400b581e  mov     eax, ebx
0x1400b5820  mov     rcx, [rsp+48h+var_18]
0x1400b5825  xor     rcx, rsp; StackCookie
0x1400b5828  call    __security_check_cookie
0x1400b582d  mov     rbx, [rsp+48h+arg_0]
0x1400b5832  add     rsp, 40h
0x1400b5836  pop     rdi
0x1400b5837  retn
0x1400b5839  cmp     eax, 0E7C80Ch
0x1400b583e  jbe     loc_1400B5A6C
0x1400b5844  cmp     eax, 0E7CC0Ch
0x1400b5849  jbe     loc_1400BAECA
0x1400b584f  cmp     eax, 0E7D808h
0x1400b5854  jbe     loc_1400B5A93
0x1400b585a  sub     eax, 0E7D810h
0x1400b585f  jz      loc_1400B5AE8
0x1400b5865  sub     eax, 4
0x1400b5868  jz      loc_1400B5ADB
0x1400b586e  cmp     eax, 4
0x1400b5871  jz      loc_1400B5ACE
0x1400b5877  mov     ebx, 0C0000010h; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b587c  xor     edx, edx; PriorityBoost
0x1400b587e  mov     [rdi+30h], ebx
0x1400b5881  mov     rcx, rdi; Irp
0x1400b5884  call    cs:__imp_IofCompleteRequest
0x1400b588b  nop     dword ptr [rax+rax+00h]
0x1400b5890  jmp     short loc_1400B581E
0x1400b5892  cmp     eax, 0E7C42Ch
0x1400b5897  ja      short loc_1400B5839
0x1400b5899  jz      loc_1400B5A5F
0x1400b589f  cmp     eax, 0E71408h
0x1400b58a4  ja      short loc_1400B58F0
0x1400b58a6  jz      loc_1400B59ED
0x1400b58ac  cmp     eax, 0E70804h
0x1400b58b1  ja      loc_1400B59B0
0x1400b58b7  jz      loc_1400B59A3
0x1400b58bd  cmp     eax, 0E70404h
0x1400b58c2  ja      loc_1400B5979
0x1400b58c8  jz      loc_1400B596C
0x1400b58ce  sub     eax, 0E70008h
0x1400b58d3  jz      loc_1400B595F
0x1400b58d9  sub     eax, 1Ch
0x1400b58dc  jz      short loc_1400B5952
0x1400b58de  cmp     eax, 4
0x1400b58e1  jnz     short def_1400BAE54; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b58e3  mov     rcx, rdi; struct _IRP *
0x1400b58e6  call    ?SpIoctlGetBootVersion@@YAJPEAU_IRP@@@Z; SpIoctlGetBootVersion(_IRP *)
0x1400b58eb  jmp     loc_1400B5815
0x1400b58f0  cmp     eax, 0E7C020h
0x1400b58f5  ja      loc_1400BAE2D
0x1400b58fb  jz      loc_1400B5A52
0x1400b5901  cmp     eax, 0E7C010h
0x1400b5906  ja      loc_1400B5A28
0x1400b590c  jz      loc_1400B5A1B
0x1400b5912  sub     eax, 0E71804h
0x1400b5917  jnz     loc_1400B59FA
0x1400b591d  mov     rcx, rdi; struct _IRP *
0x1400b5920  call    ?SpIoctlGetControlInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetControlInfo(_IRP *)
0x1400b5925  jmp     loc_1400B5815
0x1400b592a  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x1400b5931  jz      loc_1400BAD22
0x1400b5937  mov     r9d, [rbx+18h]
0x1400b593b  lea     r8, [rsp+48h+var_28]
0x1400b5940  lea     rdx, AdapterRequestStart
0x1400b5947  call    McTemplateK0q_EtwWriteTransfer
0x1400b594c  nop
0x1400b594d  jmp     loc_1400BAD22
0x1400b5952  mov     rcx, rdi; struct _IRP *
0x1400b5955  call    ?SpIoctlRefreshPool@@YAJPEAU_IRP@@@Z; SpIoctlRefreshPool(_IRP *)
0x1400b595a  jmp     loc_1400B5815
0x1400b595f  mov     rcx, rdi; struct _IRP *
0x1400b5962  call    ?SpIoctlGetPoolInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetPoolInfo(_IRP *)
0x1400b5967  jmp     loc_1400B5815
0x1400b596c  mov     rcx, rdi; struct _IRP *
0x1400b596f  call    ?SpIoctlGetDrives@@YAJPEAU_IRP@@@Z; SpIoctlGetDrives(_IRP *)
0x1400b5974  jmp     loc_1400B5815
0x1400b5979  sub     eax, 0E70408h
0x1400b597e  jz      loc_1400BAD8A
0x1400b5984  sub     eax, 14h
0x1400b5987  jz      loc_1400BAD7C
0x1400b598d  cmp     eax, 4
0x1400b5990  jnz     def_1400BAE54; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5996  mov     rcx, rdi; struct _IRP *
0x1400b5999  call    ?SpIoctlRemoveDrivesEstimate@@YAJPEAU_IRP@@@Z; SpIoctlRemoveDrivesEstimate(_IRP *)
0x1400b599e  jmp     loc_1400B5815
0x1400b59a3  mov     rcx, rdi; struct _IRP *
0x1400b59a6  call    ?SpIoctlGetSpaces@@YAJPEAU_IRP@@@Z; SpIoctlGetSpaces(_IRP *)
0x1400b59ab  jmp     loc_1400B5815
0x1400b59b0  cmp     eax, 0E71004h
0x1400b59b5  ja      loc_1400BADC2
0x1400b59bb  jz      loc_1400BADB4
0x1400b59c1  sub     eax, 0E70808h
0x1400b59c6  jz      loc_1400BADA6
0x1400b59cc  sub     eax, 3FCh
0x1400b59d1  jz      loc_1400BAD98
0x1400b59d7  cmp     eax, 4
0x1400b59da  jnz     def_1400BAE54; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b59e0  mov     rcx, rdi; struct _IRP *
0x1400b59e3  call    ?SpIoctlGetTaskInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetTaskInfo(_IRP *)
0x1400b59e8  jmp     loc_1400B5815
0x1400b59ed  mov     rcx, rdi; struct _IRP *
0x1400b59f0  call    ?SpIoctlGetTierInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetTierInfo(_IRP *)
0x1400b59f5  jmp     loc_1400B5815
0x1400b59fa  sub     eax, 8
0x1400b59fd  jz      loc_1400BAE03
0x1400b5a03  cmp     eax, 0A800h
0x1400b5a08  jnz     def_1400BAE54; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5a0e  mov     rcx, rdi; struct _IRP *
0x1400b5a11  call    ?SpIoctlSetPoolInfo@@YAJPEAU_IRP@@@Z; SpIoctlSetPoolInfo(_IRP *)
0x1400b5a16  jmp     loc_1400B5815
0x1400b5a1b  mov     rcx, rdi; struct _IRP *
0x1400b5a1e  call    ?SpIoctlCreatePool@@YAJPEAU_IRP@@@Z; SpIoctlCreatePool(_IRP *)
0x1400b5a23  jmp     loc_1400B5815
0x1400b5a28  sub     eax, 0E7C014h
0x1400b5a2d  jz      loc_1400BAE1F
0x1400b5a33  sub     eax, 4
0x1400b5a36  jz      loc_1400BAE11
0x1400b5a3c  cmp     eax, 4
0x1400b5a3f  jnz     def_1400BAE54; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5a45  mov     rcx, rdi; struct _IRP *
0x1400b5a48  call    ?SpIoctlUpgradePool@@YAJPEAU_IRP@@@Z; SpIoctlUpgradePool(_IRP *)
0x1400b5a4d  jmp     loc_1400B5815
0x1400b5a52  mov     rcx, rdi; struct _IRP *
0x1400b5a55  call    ?SpIoctlRebalancePool@@YAJPEAU_IRP@@@Z; SpIoctlRebalancePool(_IRP *)
0x1400b5a5a  jmp     loc_1400B5815
0x1400b5a5f  mov     rcx, rdi; struct _IRP *
0x1400b5a62  call    ?SpIoctlReallocateDrives@@YAJPEAU_IRP@@@Z; SpIoctlReallocateDrives(_IRP *)
0x1400b5a67  jmp     loc_1400B5815
0x1400b5a6c  jz      loc_1400BAEBC
0x1400b5a72  sub     eax, 0E7C430h
0x1400b5a77  jz      loc_1400BAEAE
0x1400b5a7d  cmp     eax, 4
0x1400b5a80  jnz     def_1400BAE54; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5a86  mov     rcx, rdi; struct _IRP *
0x1400b5a89  call    ?SpIoctlUpdateDrives@@YAJPEAU_IRP@@@Z; SpIoctlUpdateDrives(_IRP *)
0x1400b5a8e  jmp     loc_1400B5815
0x1400b5a93  jz      loc_1400BB023
0x1400b5a99  sub     eax, 0E7D00Ch
0x1400b5a9e  jz      loc_1400BB015
0x1400b5aa4  sub     eax, 400h
0x1400b5aa9  jz      loc_1400BB007
0x1400b5aaf  sub     eax, 4
0x1400b5ab2  jz      loc_1400BAFF9
0x1400b5ab8  cmp     eax, 4
0x1400b5abb  jnz     def_1400BAE54; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5ac1  mov     rcx, rdi; struct _IRP *
0x1400b5ac4  call    ?SpIoctlDeleteTier@@YAJPEAU_IRP@@@Z; SpIoctlDeleteTier(_IRP *)
0x1400b5ac9  jmp     loc_1400B5815
0x1400b5ace  mov     rcx, rdi; struct _IRP *
0x1400b5ad1  call    ?SpIoctlSetControlAttributes@@YAJPEAU_IRP@@@Z; SpIoctlSetControlAttributes(_IRP *)
0x1400b5ad6  jmp     loc_1400B5815
0x1400b5adb  mov     rcx, rdi; struct _IRP *
0x1400b5ade  call    ?SpIoctlExecuteControlWork@@YAJPEAU_IRP@@@Z; SpIoctlExecuteControlWork(_IRP *)
0x1400b5ae3  jmp     loc_1400B5815
0x1400b5ae8  mov     rcx, rdi; struct _IRP *
0x1400b5aeb  call    ?SpIoctlSetControlWork@@YAJPEAU_IRP@@@Z; SpIoctlSetControlWork(_IRP *)
0x1400b5af0  jmp     loc_1400B5815
0x1400bad22  mov     rax, [rdi+0B8h]
0x1400bad29  lea     rcx, ?SpControlCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpControlCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1400bad30  movups  xmm0, xmmword ptr [rax]
0x1400bad33  movups  xmmword ptr [rax-48h], xmm0
0x1400bad37  movups  xmm1, xmmword ptr [rax+10h]
0x1400bad3b  movups  xmmword ptr [rax-38h], xmm1
0x1400bad3f  movups  xmm0, xmmword ptr [rax+20h]
0x1400bad43  movups  xmmword ptr [rax-28h], xmm0
0x1400bad47  movsd   xmm1, qword ptr [rax+30h]
0x1400bad4c  movsd   qword ptr [rax-18h], xmm1
0x1400bad51  mov     byte ptr [rax-45h], 0
0x1400bad55  mov     rax, [rdi+0B8h]
0x1400bad5c  mov     [rax-10h], rcx
0x1400bad60  mov     qword ptr [rax-8], 0
0x1400bad68  mov     byte ptr [rax-45h], 0E0h
0x1400bad6c  dec     byte ptr [rdi+43h]
0x1400bad6f  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400bad77  jmp     loc_1400B57FF
0x1400bad7c  mov     rcx, rdi; struct _IRP *
0x1400bad7f  call    ?SpIoctlRefreshDrive@@YAJPEAU_IRP@@@Z; SpIoctlRefreshDrive(_IRP *)
0x1400bad84  nop
0x1400bad85  jmp     loc_1400B5815
0x1400bad8a  mov     rcx, rdi; struct _IRP *
0x1400bad8d  call    ?SpIoctlGetDriveInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetDriveInfo(_IRP *)
0x1400bad92  nop
0x1400bad93  jmp     loc_1400B5815
0x1400bad98  mov     rcx, rdi; struct _IRP *
0x1400bad9b  call    ?SpIoctlGetTasks@@YAJPEAU_IRP@@@Z; SpIoctlGetTasks(_IRP *)
0x1400bada0  nop
0x1400bada1  jmp     loc_1400B5815
0x1400bada6  mov     rcx, rdi; struct _IRP *
0x1400bada9  call    ?SpIoctlGetSpaceInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetSpaceInfo(_IRP *)
0x1400badae  nop
0x1400badaf  jmp     loc_1400B5815
0x1400badb4  mov     rcx, rdi; struct _IRP *
0x1400badb7  call    ?SpIoctlGetEnclosures@@YAJPEAU_IRP@@@Z; SpIoctlGetEnclosures(_IRP *)
0x1400badbc  nop
0x1400badbd  jmp     loc_1400B5815
0x1400badc2  sub     eax, 0E71008h
0x1400badc7  jz      short loc_1400BADF5
0x1400badc9  sub     eax, 8
0x1400badcc  jz      short loc_1400BADE7
0x1400badce  cmp     eax, 3F4h
0x1400badd3  jnz     def_1400BAE54; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400badd9  mov     rcx, rdi; struct _IRP *
0x1400baddc  call    ?SpIoctlGetTiers@@YAJPEAU_IRP@@@Z; SpIoctlGetTiers(_IRP *)
0x1400bade1  nop
0x1400bade2  jmp     loc_1400B5815
0x1400bade7  mov     rcx, rdi; struct _IRP *
0x1400badea  call    ?SpIoctlRefreshEnclosure@@YAJPEAU_IRP@@@Z; SpIoctlRefreshEnclosure(_IRP *)
0x1400badef  nop
0x1400badf0  jmp     loc_1400B5815
0x1400badf5  mov     rcx, rdi; struct _IRP *
0x1400badf8  call    ?SpIoctlGetEnclosureInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetEnclosureInfo(_IRP *)
0x1400badfd  nop
0x1400badfe  jmp     loc_1400B5815
0x1400bae03  mov     rcx, rdi; struct _IRP *
0x1400bae06  call    ?SpIoctlGetControlWork@@YAJPEAU_IRP@@@Z; SpIoctlGetControlWork(_IRP *)
0x1400bae0b  nop
0x1400bae0c  jmp     loc_1400B5815
0x1400bae11  mov     rcx, rdi; struct _IRP *
0x1400bae14  call    ?SpIoctlSetPoolAttributes@@YAJPEAU_IRP@@@Z; SpIoctlSetPoolAttributes(_IRP *)
0x1400bae19  nop
0x1400bae1a  jmp     loc_1400B5815
0x1400bae1f  mov     rcx, rdi; struct _IRP *
0x1400bae22  call    ?SpIoctlDeletePool@@YAJPEAU_IRP@@@Z; SpIoctlDeletePool(_IRP *)
0x1400bae27  nop
0x1400bae28  jmp     loc_1400B5815
0x1400bae2d  add     eax, 0FF183BF4h; switch 29 cases
0x1400bae32  cmp     eax, 1Ch
0x1400bae35  ja      def_1400BAE54; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400bae3b  lea     rdx, cs:140000000h
0x1400bae42  movzx   eax, ds:(byte_140073F4C - 140000000h)[rdx+rax]
0x1400bae4a  mov     ecx, ds:(jpt_1400BAE54 - 140000000h)[rdx+rax*4]
0x1400bae51  add     rcx, rdx
0x1400bae54  jmp     rcx; switch jump
0x1400bae5a  mov     rcx, rdi; jumptable 00000001400BAE54 case 15189004
0x1400bae5d  call    ?SpIoctlSetDriveInfo@@YAJPEAU_IRP@@@Z; SpIoctlSetDriveInfo(_IRP *)
0x1400bae62  nop
0x1400bae63  jmp     loc_1400B5815
0x1400bae68  mov     rcx, rdi; jumptable 00000001400BAE54 case 15189008
0x1400bae6b  call    ?SpIoctlAddDrives@@YAJPEAU_IRP@@@Z; SpIoctlAddDrives(_IRP *)
0x1400bae70  nop
0x1400bae71  jmp     loc_1400B5815
0x1400bae76  mov     rcx, rdi; jumptable 00000001400BAE54 case 15189012
0x1400bae79  call    ?SpIoctlRemoveDrives@@YAJPEAU_IRP@@@Z; SpIoctlRemoveDrives(_IRP *)
0x1400bae7e  nop
0x1400bae7f  jmp     loc_1400B5815
0x1400bae84  mov     rcx, rdi; jumptable 00000001400BAE54 case 15189016
0x1400bae87  call    ?SpIoctlResetDrive@@YAJPEAU_IRP@@@Z; SpIoctlResetDrive(_IRP *)
0x1400bae8c  nop
0x1400bae8d  jmp     loc_1400B5815
0x1400bae92  mov     rcx, rdi; jumptable 00000001400BAE54 case 15189028
0x1400bae95  call    ?SpIoctlSetMetadataDrives@@YAJPEAU_IRP@@@Z; SpIoctlSetMetadataDrives(_IRP *)
0x1400bae9a  nop
0x1400bae9b  jmp     loc_1400B5815
0x1400baea0  mov     rcx, rdi; jumptable 00000001400BAE54 case 15189032
0x1400baea3  call    ?SpIoctlRetireDrives@@YAJPEAU_IRP@@@Z; SpIoctlRetireDrives(_IRP *)
0x1400baea8  nop
0x1400baea9  jmp     loc_1400B5815
0x1400baeae  mov     rcx, rdi; struct _IRP *
0x1400baeb1  call    ?SpIoctlSetMaintenanceMode@@YAJPEAU_IRP@@@Z; SpIoctlSetMaintenanceMode(_IRP *)
0x1400baeb6  nop
0x1400baeb7  jmp     loc_1400B5815
0x1400baebc  mov     rcx, rdi; struct _IRP *
0x1400baebf  call    ?SpIoctlSetSpaceInfo@@YAJPEAU_IRP@@@Z; SpIoctlSetSpaceInfo(_IRP *)
0x1400baec4  nop
0x1400baec5  jmp     loc_1400B5815
0x1400baeca  jz      loc_1400BAFEB
0x1400baed0  add     eax, 0FF1837F0h; switch 69 cases
0x1400baed5  cmp     eax, 44h
0x1400baed8  ja      def_1400BAE54; jumptable 00000001400BAE54 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400baede  lea     rdx, cs:140000000h
0x1400baee5  movzx   eax, ds:(byte_140073FB1 - 140000000h)[rdx+rax]
0x1400baeed  mov     ecx, ds:(jpt_1400BAEF7 - 140000000h)[rdx+rax*4]
0x1400baef4  add     rcx, rdx
0x1400baef7  jmp     rcx; switch jump
0x1400baefd  mov     rcx, rdi; jumptable 00000001400BAEF7 case 15190032
  ... truncated ...
```
