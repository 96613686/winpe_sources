# SpControlDeviceControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400b5950`
- end: `0x1400b5c95`
- name: `?SpControlDeviceControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `837`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `64`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x14002d738`
- `0x14002d9a0`
- `0x14002de54`
- `0x14002e30c`
- `0x140068110`
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

- `ntoskrnl!IoGetActivityIdIrp` at `0x1400b598b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400b598b`
- `ntoskrnl!IofCompleteRequest` at `0x1400b5a24`
- `ntoskrnl!IofCompleteRequest` at `0x1400b5a24`

## pseudocode

```c
__int64 __fastcall SpControlDeviceControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v4; // rcx
  unsigned int LowPart; // eax
  unsigned int Pools; // eax
  unsigned int v7; // ebx
  unsigned int v9; // eax
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
  struct _IO_STACK_LOCATION *v25; // rax
  struct _IO_STACK_LOCATION *v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int128 v29; // [rsp+20h] [rbp-28h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  a2->IoStatus.Information = 0;
  v29 = 0;
  if ( (int)IoGetActivityIdIrp(a2, &v29) >= 0 )
  {
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
      McTemplateK0q_EtwWriteTransfer(
        v4,
        AdapterRequestStart,
        &v29,
        CurrentStackLocation->Parameters.Read.ByteOffset.LowPart);
    v25 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v25[-1].MajorFunction = *(_OWORD *)&v25->MajorFunction;
    *(_OWORD *)&v25[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v25->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v25[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v25->Parameters.SetQuota + 6);
    v25[-1].FileObject = v25->FileObject;
    v25[-1].Control = 0;
    v26 = a2->Tail.Overlay.CurrentStackLocation;
    v26[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SpControlCompletionRoutine;
    v26[-1].Context = 0;
    v26[-1].Control = -32;
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
        v21 = LowPart - 15189040;
        if ( v21 )
        {
          if ( v21 != 4 )
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
        v22 = LowPart - 15192076;
        if ( v22 )
        {
          v23 = v22 - 1024;
          if ( v23 )
          {
            v24 = v23 - 4;
            if ( v24 )
            {
              if ( v24 != 4 )
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
      v9 = LowPart - 15194128;
      if ( v9 )
      {
        v10 = v9 - 4;
        if ( v10 )
        {
          if ( v10 != 4 )
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
          Pools = SpIoctlSetMetadataDrives(a2);
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
      v19 = LowPart - 15187988;
      if ( v19 )
      {
        v20 = v19 - 4;
        if ( v20 )
        {
          if ( v20 != 4 )
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
      v13 = LowPart - 15144964;
      if ( v13 )
      {
        v18 = v13 - 8;
        if ( v18 )
        {
          if ( v18 != 43008 )
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
      v27 = LowPart - 15142920;
      if ( v27 )
      {
        v28 = v27 - 8;
        if ( v28 )
        {
          if ( v28 != 1012 )
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
      v16 = LowPart - 15140872;
      if ( v16 )
      {
        v17 = v16 - 1020;
        if ( v17 )
        {
          if ( v17 != 4 )
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
    v14 = LowPart - 15139848;
    if ( v14 )
    {
      v15 = v14 - 20;
      if ( v15 )
      {
        if ( v15 != 4 )
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
    v11 = LowPart - 15138824;
    if ( v11 )
    {
      v12 = v11 - 28;
      if ( v12 )
      {
        if ( v12 == 4 )
        {
          Pools = SpIoctlGetBootVersion(a2);
          goto LABEL_4;
        }
LABEL_12:
        v7 = -1073741808;
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
  v7 = Pools;
  if ( Pools != 259 )
  {
LABEL_13:
    a2->IoStatus.Status = v7;
    IofCompleteRequest(a2, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x1400b5950  mov     [rsp+arg_0], rbx
0x1400b5955  push    rdi
0x1400b5956  sub     rsp, 40h
0x1400b595a  mov     rax, cs:__security_cookie
0x1400b5961  xor     rax, rsp
0x1400b5964  mov     [rsp+48h+var_18], rax
0x1400b5969  mov     rbx, [rdx+0B8h]
0x1400b5970  mov     rdi, rdx
0x1400b5973  xorps   xmm0, xmm0
0x1400b5976  mov     qword ptr [rdx+38h], 0
0x1400b597e  mov     rcx, rdi
0x1400b5981  lea     rdx, [rsp+48h+var_28]
0x1400b5986  movups  [rsp+48h+var_28], xmm0
0x1400b598b  call    cs:__imp_IoGetActivityIdIrp
0x1400b5992  nop     dword ptr [rax+rax+00h]
0x1400b5997  test    eax, eax
0x1400b5999  jns     loc_1400B5ACA
0x1400b599f  mov     eax, [rbx+18h]
0x1400b59a2  cmp     eax, 0E70004h
0x1400b59a7  jnz     loc_1400B5A32
0x1400b59ad  mov     rcx, rdi; struct _IRP *
0x1400b59b0  call    ?SpIoctlGetPools@@YAJPEAU_IRP@@@Z; SpIoctlGetPools(_IRP *)
0x1400b59b5  mov     ebx, eax
0x1400b59b7  cmp     eax, 103h
0x1400b59bc  jnz     short loc_1400B5A1C
0x1400b59be  mov     eax, ebx
0x1400b59c0  mov     rcx, [rsp+48h+var_18]
0x1400b59c5  xor     rcx, rsp; StackCookie
0x1400b59c8  call    __security_check_cookie
0x1400b59cd  mov     rbx, [rsp+48h+arg_0]
0x1400b59d2  add     rsp, 40h
0x1400b59d6  pop     rdi
0x1400b59d7  retn
0x1400b59d9  cmp     eax, 0E7C80Ch
0x1400b59de  jbe     loc_1400B5C0C
0x1400b59e4  cmp     eax, 0E7CC0Ch
0x1400b59e9  jbe     loc_1400BB06A
0x1400b59ef  cmp     eax, 0E7D808h
0x1400b59f4  jbe     loc_1400B5C33
0x1400b59fa  sub     eax, 0E7D810h
0x1400b59ff  jz      loc_1400B5C88
0x1400b5a05  sub     eax, 4
0x1400b5a08  jz      loc_1400B5C7B
0x1400b5a0e  cmp     eax, 4
0x1400b5a11  jz      loc_1400B5C6E
0x1400b5a17  mov     ebx, 0C0000010h; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5a1c  xor     edx, edx; PriorityBoost
0x1400b5a1e  mov     [rdi+30h], ebx
0x1400b5a21  mov     rcx, rdi; Irp
0x1400b5a24  call    cs:__imp_IofCompleteRequest
0x1400b5a2b  nop     dword ptr [rax+rax+00h]
0x1400b5a30  jmp     short loc_1400B59BE
0x1400b5a32  cmp     eax, 0E7C42Ch
0x1400b5a37  ja      short loc_1400B59D9
0x1400b5a39  jz      loc_1400B5BFF
0x1400b5a3f  cmp     eax, 0E71408h
0x1400b5a44  ja      short loc_1400B5A90
0x1400b5a46  jz      loc_1400B5B8D
0x1400b5a4c  cmp     eax, 0E70804h
0x1400b5a51  ja      loc_1400B5B50
0x1400b5a57  jz      loc_1400B5B43
0x1400b5a5d  cmp     eax, 0E70404h
0x1400b5a62  ja      loc_1400B5B19
0x1400b5a68  jz      loc_1400B5B0C
0x1400b5a6e  sub     eax, 0E70008h
0x1400b5a73  jz      loc_1400B5AFF
0x1400b5a79  sub     eax, 1Ch
0x1400b5a7c  jz      short loc_1400B5AF2
0x1400b5a7e  cmp     eax, 4
0x1400b5a81  jnz     short def_1400BAFF4; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5a83  mov     rcx, rdi; struct _IRP *
0x1400b5a86  call    ?SpIoctlGetBootVersion@@YAJPEAU_IRP@@@Z; SpIoctlGetBootVersion(_IRP *)
0x1400b5a8b  jmp     loc_1400B59B5
0x1400b5a90  cmp     eax, 0E7C020h
0x1400b5a95  ja      loc_1400BAFCD
0x1400b5a9b  jz      loc_1400B5BF2
0x1400b5aa1  cmp     eax, 0E7C010h
0x1400b5aa6  ja      loc_1400B5BC8
0x1400b5aac  jz      loc_1400B5BBB
0x1400b5ab2  sub     eax, 0E71804h
0x1400b5ab7  jnz     loc_1400B5B9A
0x1400b5abd  mov     rcx, rdi; struct _IRP *
0x1400b5ac0  call    ?SpIoctlGetControlInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetControlInfo(_IRP *)
0x1400b5ac5  jmp     loc_1400B59B5
0x1400b5aca  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x1400b5ad1  jz      loc_1400BAEC2
0x1400b5ad7  mov     r9d, [rbx+18h]
0x1400b5adb  lea     r8, [rsp+48h+var_28]
0x1400b5ae0  lea     rdx, AdapterRequestStart
0x1400b5ae7  call    McTemplateK0q_EtwWriteTransfer
0x1400b5aec  nop
0x1400b5aed  jmp     loc_1400BAEC2
0x1400b5af2  mov     rcx, rdi; struct _IRP *
0x1400b5af5  call    ?SpIoctlRefreshPool@@YAJPEAU_IRP@@@Z; SpIoctlRefreshPool(_IRP *)
0x1400b5afa  jmp     loc_1400B59B5
0x1400b5aff  mov     rcx, rdi; struct _IRP *
0x1400b5b02  call    ?SpIoctlGetPoolInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetPoolInfo(_IRP *)
0x1400b5b07  jmp     loc_1400B59B5
0x1400b5b0c  mov     rcx, rdi; struct _IRP *
0x1400b5b0f  call    ?SpIoctlGetDrives@@YAJPEAU_IRP@@@Z; SpIoctlGetDrives(_IRP *)
0x1400b5b14  jmp     loc_1400B59B5
0x1400b5b19  sub     eax, 0E70408h
0x1400b5b1e  jz      loc_1400BAF2A
0x1400b5b24  sub     eax, 14h
0x1400b5b27  jz      loc_1400BAF1C
0x1400b5b2d  cmp     eax, 4
0x1400b5b30  jnz     def_1400BAFF4; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5b36  mov     rcx, rdi; struct _IRP *
0x1400b5b39  call    ?SpIoctlRemoveDrivesEstimate@@YAJPEAU_IRP@@@Z; SpIoctlRemoveDrivesEstimate(_IRP *)
0x1400b5b3e  jmp     loc_1400B59B5
0x1400b5b43  mov     rcx, rdi; struct _IRP *
0x1400b5b46  call    ?SpIoctlGetSpaces@@YAJPEAU_IRP@@@Z; SpIoctlGetSpaces(_IRP *)
0x1400b5b4b  jmp     loc_1400B59B5
0x1400b5b50  cmp     eax, 0E71004h
0x1400b5b55  ja      loc_1400BAF62
0x1400b5b5b  jz      loc_1400BAF54
0x1400b5b61  sub     eax, 0E70808h
0x1400b5b66  jz      loc_1400BAF46
0x1400b5b6c  sub     eax, 3FCh
0x1400b5b71  jz      loc_1400BAF38
0x1400b5b77  cmp     eax, 4
0x1400b5b7a  jnz     def_1400BAFF4; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5b80  mov     rcx, rdi; struct _IRP *
0x1400b5b83  call    ?SpIoctlGetTaskInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetTaskInfo(_IRP *)
0x1400b5b88  jmp     loc_1400B59B5
0x1400b5b8d  mov     rcx, rdi; struct _IRP *
0x1400b5b90  call    ?SpIoctlGetTierInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetTierInfo(_IRP *)
0x1400b5b95  jmp     loc_1400B59B5
0x1400b5b9a  sub     eax, 8
0x1400b5b9d  jz      loc_1400BAFA3
0x1400b5ba3  cmp     eax, 0A800h
0x1400b5ba8  jnz     def_1400BAFF4; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5bae  mov     rcx, rdi; struct _IRP *
0x1400b5bb1  call    ?SpIoctlSetPoolInfo@@YAJPEAU_IRP@@@Z; SpIoctlSetPoolInfo(_IRP *)
0x1400b5bb6  jmp     loc_1400B59B5
0x1400b5bbb  mov     rcx, rdi; struct _IRP *
0x1400b5bbe  call    ?SpIoctlCreatePool@@YAJPEAU_IRP@@@Z; SpIoctlCreatePool(_IRP *)
0x1400b5bc3  jmp     loc_1400B59B5
0x1400b5bc8  sub     eax, 0E7C014h
0x1400b5bcd  jz      loc_1400BAFBF
0x1400b5bd3  sub     eax, 4
0x1400b5bd6  jz      loc_1400BAFB1
0x1400b5bdc  cmp     eax, 4
0x1400b5bdf  jnz     def_1400BAFF4; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5be5  mov     rcx, rdi; struct _IRP *
0x1400b5be8  call    ?SpIoctlUpgradePool@@YAJPEAU_IRP@@@Z; SpIoctlUpgradePool(_IRP *)
0x1400b5bed  jmp     loc_1400B59B5
0x1400b5bf2  mov     rcx, rdi; struct _IRP *
0x1400b5bf5  call    ?SpIoctlRebalancePool@@YAJPEAU_IRP@@@Z; SpIoctlRebalancePool(_IRP *)
0x1400b5bfa  jmp     loc_1400B59B5
0x1400b5bff  mov     rcx, rdi; struct _IRP *
0x1400b5c02  call    ?SpIoctlReallocateDrives@@YAJPEAU_IRP@@@Z; SpIoctlReallocateDrives(_IRP *)
0x1400b5c07  jmp     loc_1400B59B5
0x1400b5c0c  jz      loc_1400BB05C
0x1400b5c12  sub     eax, 0E7C430h
0x1400b5c17  jz      loc_1400BB04E
0x1400b5c1d  cmp     eax, 4
0x1400b5c20  jnz     def_1400BAFF4; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5c26  mov     rcx, rdi; struct _IRP *
0x1400b5c29  call    ?SpIoctlUpdateDrives@@YAJPEAU_IRP@@@Z; SpIoctlUpdateDrives(_IRP *)
0x1400b5c2e  jmp     loc_1400B59B5
0x1400b5c33  jz      loc_1400BB1C3
0x1400b5c39  sub     eax, 0E7D00Ch
0x1400b5c3e  jz      loc_1400BB1B5
0x1400b5c44  sub     eax, 400h
0x1400b5c49  jz      loc_1400BB1A7
0x1400b5c4f  sub     eax, 4
0x1400b5c52  jz      loc_1400BB199
0x1400b5c58  cmp     eax, 4
0x1400b5c5b  jnz     def_1400BAFF4; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400b5c61  mov     rcx, rdi; struct _IRP *
0x1400b5c64  call    ?SpIoctlDeleteTier@@YAJPEAU_IRP@@@Z; SpIoctlDeleteTier(_IRP *)
0x1400b5c69  jmp     loc_1400B59B5
0x1400b5c6e  mov     rcx, rdi; struct _IRP *
0x1400b5c71  call    ?SpIoctlSetControlAttributes@@YAJPEAU_IRP@@@Z; SpIoctlSetControlAttributes(_IRP *)
0x1400b5c76  jmp     loc_1400B59B5
0x1400b5c7b  mov     rcx, rdi; struct _IRP *
0x1400b5c7e  call    ?SpIoctlExecuteControlWork@@YAJPEAU_IRP@@@Z; SpIoctlExecuteControlWork(_IRP *)
0x1400b5c83  jmp     loc_1400B59B5
0x1400b5c88  mov     rcx, rdi; struct _IRP *
0x1400b5c8b  call    ?SpIoctlSetControlWork@@YAJPEAU_IRP@@@Z; SpIoctlSetControlWork(_IRP *)
0x1400b5c90  jmp     loc_1400B59B5
0x1400baec2  mov     rax, [rdi+0B8h]
0x1400baec9  lea     rcx, ?SpControlCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; SpControlCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x1400baed0  movups  xmm0, xmmword ptr [rax]
0x1400baed3  movups  xmmword ptr [rax-48h], xmm0
0x1400baed7  movups  xmm1, xmmword ptr [rax+10h]
0x1400baedb  movups  xmmword ptr [rax-38h], xmm1
0x1400baedf  movups  xmm0, xmmword ptr [rax+20h]
0x1400baee3  movups  xmmword ptr [rax-28h], xmm0
0x1400baee7  movsd   xmm1, qword ptr [rax+30h]
0x1400baeec  movsd   qword ptr [rax-18h], xmm1
0x1400baef1  mov     byte ptr [rax-45h], 0
0x1400baef5  mov     rax, [rdi+0B8h]
0x1400baefc  mov     [rax-10h], rcx
0x1400baf00  mov     qword ptr [rax-8], 0
0x1400baf08  mov     byte ptr [rax-45h], 0E0h
0x1400baf0c  dec     byte ptr [rdi+43h]
0x1400baf0f  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400baf17  jmp     loc_1400B599F
0x1400baf1c  mov     rcx, rdi; struct _IRP *
0x1400baf1f  call    ?SpIoctlRefreshDrive@@YAJPEAU_IRP@@@Z; SpIoctlRefreshDrive(_IRP *)
0x1400baf24  nop
0x1400baf25  jmp     loc_1400B59B5
0x1400baf2a  mov     rcx, rdi; struct _IRP *
0x1400baf2d  call    ?SpIoctlGetDriveInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetDriveInfo(_IRP *)
0x1400baf32  nop
0x1400baf33  jmp     loc_1400B59B5
0x1400baf38  mov     rcx, rdi; struct _IRP *
0x1400baf3b  call    ?SpIoctlGetTasks@@YAJPEAU_IRP@@@Z; SpIoctlGetTasks(_IRP *)
0x1400baf40  nop
0x1400baf41  jmp     loc_1400B59B5
0x1400baf46  mov     rcx, rdi; struct _IRP *
0x1400baf49  call    ?SpIoctlGetSpaceInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetSpaceInfo(_IRP *)
0x1400baf4e  nop
0x1400baf4f  jmp     loc_1400B59B5
0x1400baf54  mov     rcx, rdi; struct _IRP *
0x1400baf57  call    ?SpIoctlGetEnclosures@@YAJPEAU_IRP@@@Z; SpIoctlGetEnclosures(_IRP *)
0x1400baf5c  nop
0x1400baf5d  jmp     loc_1400B59B5
0x1400baf62  sub     eax, 0E71008h
0x1400baf67  jz      short loc_1400BAF95
0x1400baf69  sub     eax, 8
0x1400baf6c  jz      short loc_1400BAF87
0x1400baf6e  cmp     eax, 3F4h
0x1400baf73  jnz     def_1400BAFF4; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400baf79  mov     rcx, rdi; struct _IRP *
0x1400baf7c  call    ?SpIoctlGetTiers@@YAJPEAU_IRP@@@Z; SpIoctlGetTiers(_IRP *)
0x1400baf81  nop
0x1400baf82  jmp     loc_1400B59B5
0x1400baf87  mov     rcx, rdi; struct _IRP *
0x1400baf8a  call    ?SpIoctlRefreshEnclosure@@YAJPEAU_IRP@@@Z; SpIoctlRefreshEnclosure(_IRP *)
0x1400baf8f  nop
0x1400baf90  jmp     loc_1400B59B5
0x1400baf95  mov     rcx, rdi; struct _IRP *
0x1400baf98  call    ?SpIoctlGetEnclosureInfo@@YAJPEAU_IRP@@@Z; SpIoctlGetEnclosureInfo(_IRP *)
0x1400baf9d  nop
0x1400baf9e  jmp     loc_1400B59B5
0x1400bafa3  mov     rcx, rdi; struct _IRP *
0x1400bafa6  call    ?SpIoctlGetControlWork@@YAJPEAU_IRP@@@Z; SpIoctlGetControlWork(_IRP *)
0x1400bafab  nop
0x1400bafac  jmp     loc_1400B59B5
0x1400bafb1  mov     rcx, rdi; struct _IRP *
0x1400bafb4  call    ?SpIoctlSetPoolAttributes@@YAJPEAU_IRP@@@Z; SpIoctlSetPoolAttributes(_IRP *)
0x1400bafb9  nop
0x1400bafba  jmp     loc_1400B59B5
0x1400bafbf  mov     rcx, rdi; struct _IRP *
0x1400bafc2  call    ?SpIoctlDeletePool@@YAJPEAU_IRP@@@Z; SpIoctlDeletePool(_IRP *)
0x1400bafc7  nop
0x1400bafc8  jmp     loc_1400B59B5
0x1400bafcd  add     eax, 0FF183BF4h; switch 29 cases
0x1400bafd2  cmp     eax, 1Ch
0x1400bafd5  ja      def_1400BAFF4; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400bafdb  lea     rdx, cs:140000000h
0x1400bafe2  movzx   eax, ds:(byte_140073F4C - 140000000h)[rdx+rax]
0x1400bafea  mov     ecx, ds:(jpt_1400BAFF4 - 140000000h)[rdx+rax*4]
0x1400baff1  add     rcx, rdx
0x1400baff4  jmp     rcx; switch jump
0x1400baffa  mov     rcx, rdi; jumptable 00000001400BAFF4 case 15189004
0x1400baffd  call    ?SpIoctlSetDriveInfo@@YAJPEAU_IRP@@@Z; SpIoctlSetDriveInfo(_IRP *)
0x1400bb002  nop
0x1400bb003  jmp     loc_1400B59B5
0x1400bb008  mov     rcx, rdi; jumptable 00000001400BAFF4 case 15189008
0x1400bb00b  call    ?SpIoctlAddDrives@@YAJPEAU_IRP@@@Z; SpIoctlAddDrives(_IRP *)
0x1400bb010  nop
0x1400bb011  jmp     loc_1400B59B5
0x1400bb016  mov     rcx, rdi; jumptable 00000001400BAFF4 case 15189012
0x1400bb019  call    ?SpIoctlRemoveDrives@@YAJPEAU_IRP@@@Z; SpIoctlRemoveDrives(_IRP *)
0x1400bb01e  nop
0x1400bb01f  jmp     loc_1400B59B5
0x1400bb024  mov     rcx, rdi; jumptable 00000001400BAFF4 case 15189016
0x1400bb027  call    ?SpIoctlResetDrive@@YAJPEAU_IRP@@@Z; SpIoctlResetDrive(_IRP *)
0x1400bb02c  nop
0x1400bb02d  jmp     loc_1400B59B5
0x1400bb032  mov     rcx, rdi; jumptable 00000001400BAFF4 case 15189028
0x1400bb035  call    ?SpIoctlSetMetadataDrives@@YAJPEAU_IRP@@@Z; SpIoctlSetMetadataDrives(_IRP *)
0x1400bb03a  nop
0x1400bb03b  jmp     loc_1400B59B5
0x1400bb040  mov     rcx, rdi; jumptable 00000001400BAFF4 case 15189032
0x1400bb043  call    ?SpIoctlRetireDrives@@YAJPEAU_IRP@@@Z; SpIoctlRetireDrives(_IRP *)
0x1400bb048  nop
0x1400bb049  jmp     loc_1400B59B5
0x1400bb04e  mov     rcx, rdi; struct _IRP *
0x1400bb051  call    ?SpIoctlSetMaintenanceMode@@YAJPEAU_IRP@@@Z; SpIoctlSetMaintenanceMode(_IRP *)
0x1400bb056  nop
0x1400bb057  jmp     loc_1400B59B5
0x1400bb05c  mov     rcx, rdi; struct _IRP *
0x1400bb05f  call    ?SpIoctlSetSpaceInfo@@YAJPEAU_IRP@@@Z; SpIoctlSetSpaceInfo(_IRP *)
0x1400bb064  nop
0x1400bb065  jmp     loc_1400B59B5
0x1400bb06a  jz      loc_1400BB18B
0x1400bb070  add     eax, 0FF1837F0h; switch 69 cases
0x1400bb075  cmp     eax, 44h
0x1400bb078  ja      def_1400BAFF4; jumptable 00000001400BAFF4 default case, cases 15189005-15189007,15189009-15189011,15189013-15189015,15189017-15189027,15189029-15189031
0x1400bb07e  lea     rdx, cs:140000000h
0x1400bb085  movzx   eax, ds:(byte_140073FB1 - 140000000h)[rdx+rax]
0x1400bb08d  mov     ecx, ds:(jpt_1400BB097 - 140000000h)[rdx+rax*4]
0x1400bb094  add     rcx, rdx
0x1400bb097  jmp     rcx; switch jump
0x1400bb09d  mov     rcx, rdi; jumptable 00000001400BB097 case 15190032
  ... truncated ...
```
