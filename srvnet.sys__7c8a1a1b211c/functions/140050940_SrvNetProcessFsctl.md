# SrvNetProcessFsctl

- ea: `0x140050940`
- end: `0x140051112`
- name: `SrvNetProcessFsctl`
- size: `2002`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140042370`
- `0x1400507c0`

## callees

- `0x14000d2a0`
- `0x14000da70`
- `0x140011cb8`
- `0x140014808`
- `0x140016384`
- `0x14002a410`
- `0x140050940`
- `0x140055bb0`
- `0x140056534`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140050f58`
- `ntoskrnl!MmUnlockPages` at `0x140050fe1`
- `ntoskrnl!MmUnlockPages` at `0x140050f58`
- `ntoskrnl!MmUnlockPages` at `0x140050fe1`
- `ntoskrnl!MmProbeAndLockPages` at `0x140050ece`
- `ntoskrnl!MmProbeAndLockPages` at `0x140050ece`
- `ntoskrnl!IoAllocateMdl` at `0x140050e8c`
- `ntoskrnl!IoAllocateMdl` at `0x140050e8c`
- `ntoskrnl!IoFreeMdl` at `0x140050eeb`
- `ntoskrnl!IoFreeMdl` at `0x140050f68`
- `ntoskrnl!IoFreeMdl` at `0x140050ff1`
- `ntoskrnl!IoFreeMdl` at `0x140050eeb`
- `ntoskrnl!IoFreeMdl` at `0x140050f68`
- `ntoskrnl!IoFreeMdl` at `0x140050ff1`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140050b65`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140050b65`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140050bf6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140050bf6`
- `ntoskrnl!ExAllocatePool2` at `0x140050f3a`
- `ntoskrnl!ExAllocatePool2` at `0x140050f3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050be5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050be5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140050b94`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140050b94`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140050b7b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140050b7b`
- `ntoskrnl!IoAllocateWorkItem` at `0x140050e44`
- `ntoskrnl!IoAllocateWorkItem` at `0x140050e44`
- `ntoskrnl!IofCompleteRequest` at `0x1400510b4`
- `ntoskrnl!IofCompleteRequest` at `0x1400510b4`
- `ntoskrnl!IoQueueWorkItem` at `0x140051050`
- `ntoskrnl!IoQueueWorkItem` at `0x140051050`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050fc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050fc2`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140050d41`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140050d41`
- `ntoskrnl!IoFreeWorkItem` at `0x140050ea0`
- `ntoskrnl!IoFreeWorkItem` at `0x140050f07`
- `ntoskrnl!IoFreeWorkItem` at `0x140050f7b`
- `ntoskrnl!IoFreeWorkItem` at `0x14005100d`
- `ntoskrnl!IoFreeWorkItem` at `0x140050ea0`
- `ntoskrnl!IoFreeWorkItem` at `0x140050f07`
- `ntoskrnl!IoFreeWorkItem` at `0x140050f7b`
- `ntoskrnl!IoFreeWorkItem` at `0x14005100d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050bd9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050bd9`

## pseudocode

```c
__int64 __fastcall SrvNetProcessFsctl(
        size_t a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        unsigned int *VirtualAddress,
        ULONG Length,
        unsigned int a7,
        __int64 a8,
        PIO_WORKITEM IoWorkItem,
        KPROCESSOR_MODE a10,
        PIRP a11)
{
  size_t v11; // r14
  int v13; // r9d
  unsigned __int64 v14; // rax
  __int64 v15; // r9
  int v16; // eax
  int QueueStatistics; // ebx
  PIRP Irp; // rdi
  __int128 v19; // xmm12
  __int128 v20; // xmm13
  __int128 v21; // xmm14
  __int128 v22; // xmm15
  __int64 v23; // xmm6_8
  __int128 v24; // xmm7
  __int128 v25; // xmm8
  __int128 v26; // xmm9
  __int128 v27; // xmm10
  __int128 v28; // xmm11
  __int64 v29; // rbx
  struct _IRP *MasterIrp; // rax
  struct _IO_WORKITEM *WorkItem; // rbx
  struct _IRP *Pool2; // rax
  struct _MDL *MdlAddress; // rcx
  struct _STRING SourceString; // [rsp+68h] [rbp-1F0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-1E0h] BYREF
  __int128 v37; // [rsp+88h] [rbp-1D0h]
  __int128 v38; // [rsp+110h] [rbp-148h]

  v11 = a4;
  if ( IoWorkItem == (PIO_WORKITEM)SrvNetAdminDeviceObject )
  {
    if ( a7 - 1336327 > 0xC || (v13 = 4369, !_bittest(&v13, a7 - 1336327)) )
    {
      v14 = a7 - 1327124;
      if ( (unsigned int)v14 > 0x33 || (v15 = 0x8100000000081LL, !_bittest64(&v15, v14)) )
      {
        if ( a7 != 1310732 && a7 != 1310792 && a7 != 1335451 )
        {
          v16 = SrvAdminProcessFsctl(
                  a1,
                  a2,
                  (unsigned __int64)a3,
                  v11,
                  VirtualAddress,
                  Length,
                  a7,
                  a8,
                  (__int64)IoWorkItem,
                  a10,
                  a11);
          QueueStatistics = v16;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_6a4d2c8a1a8134e9dfbfd0e9f83a7911_Traceguids, a7, v16);
          }
          return (unsigned int)QueueStatistics;
        }
      }
    }
  }
  *(_QWORD *)(a8 + 8) = 0;
  if ( a7 > 0x144047 )
  {
    if ( a7 != 1335451 && a7 != 1336327 && a7 != 1336331 && a7 != 1336335 && a7 != 1336339 )
    {
LABEL_46:
      QueueStatistics = -1073741822;
      Irp = a11;
      goto LABEL_66;
    }
  }
  else
  {
    switch ( a7 )
    {
      case 0x144047u:
        SrvNetRefreshLanmanServerParameters();
        QueueStatistics = 0;
        Irp = a11;
        goto LABEL_66;
      case 0x14000Cu:
        Irp = a11;
        if ( a11 )
        {
          if ( LOBYTE(SrvNetDeviceExtension[8].SystemResourcesList.Flink) )
          {
            if ( a11->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length >= 0xD8 )
            {
              SrvNetUpdateStatisticsFromQueues();
              v19 = SrvNetStatistics;
              v20 = xmmword_1400365A0;
              v21 = xmmword_1400365B0;
              v22 = xmmword_1400365C0;
              DestinationString = (struct _UNICODE_STRING)xmmword_1400365D0;
              SourceString = *(struct _STRING *)byte_1400365E0;
              v37 = xmmword_1400365F0;
              *((_QWORD *)&v38 + 1) = *((_QWORD *)&xmmword_140036600 + 1);
              v23 = xmmword_140036600;
              v24 = xmmword_140036610;
              v25 = xmmword_140036620;
              v26 = xmmword_140036630;
              v27 = xmmword_140036640;
              v28 = xmmword_140036650;
              v29 = qword_140036660;
              *(_QWORD *)&v38 = (int)KeQueryTimeIncrement() * v23;
              MasterIrp = Irp->AssociatedIrp.MasterIrp;
              *(_OWORD *)&MasterIrp->Type = v19;
              *(_OWORD *)&MasterIrp->Flags = v20;
              MasterIrp->ThreadListEntry = (LIST_ENTRY)v21;
              *(_OWORD *)&MasterIrp->IoStatus.Status = v22;
              *(struct _UNICODE_STRING *)&MasterIrp->RequestorMode = DestinationString;
              *(struct _STRING *)&MasterIrp->UserEvent = SourceString;
              *(union _IRP::$6B96A96ED958C92F2CB4B83EAB343043 *)((char *)&MasterIrp->Overlay + 8) = (union _IRP::$6B96A96ED958C92F2CB4B83EAB343043)v37;
              *(_OWORD *)&MasterIrp->UserBuffer = v38;
              *(_OWORD *)(&MasterIrp->Tail.CompletionKey + 1) = v24;
              *(_OWORD *)(&MasterIrp->Tail.CompletionKey + 3) = v25;
              *(_OWORD *)(&MasterIrp->Tail.CompletionKey + 5) = v26;
              *(_OWORD *)(&MasterIrp->Tail.CompletionKey + 7) = v27;
              *(_OWORD *)(&MasterIrp->Tail.CompletionKey + 9) = v28;
              *(_QWORD *)&MasterIrp[1].Type = v29;
              Irp->IoStatus.Information = 216;
              QueueStatistics = 0;
            }
            else
            {
              QueueStatistics = -1073741789;
            }
          }
          else
          {
            QueueStatistics = -1073740698;
          }
        }
        else
        {
          QueueStatistics = -1073741637;
        }
        goto LABEL_66;
      case 0x140048u:
        LODWORD(IoWorkItem) = 0;
        Irp = a11;
        if ( a11 )
        {
          if ( LOBYTE(SrvNetDeviceExtension[8].SystemResourcesList.Flink) )
          {
            QueueStatistics = SrvNetGetQueueStatistics(
                                &a11->AssociatedIrp.MasterIrp->Type,
                                a11->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length,
                                (int *)&IoWorkItem);
            Irp->IoStatus.Information = (unsigned int)IoWorkItem;
          }
          else
          {
            QueueStatistics = -1073740698;
          }
        }
        else
        {
          QueueStatistics = -1073741637;
        }
        goto LABEL_66;
      case 0x144014u:
        *(_QWORD *)&SourceString.Length = 0;
        DestinationString = 0;
        Irp = a11;
        if ( a11 )
        {
          SourceString.Buffer = (PCHAR)a11->AssociatedIrp.MasterIrp;
          SourceString.Length = a11->Tail.Overlay.CurrentStackLocation->Parameters.QueryInterface.Size;
          QueueStatistics = RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 1u);
          if ( QueueStatistics >= 0 )
          {
            KeEnterCriticalRegion();
            ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 120), 1u);
            if ( !LOBYTE(SrvNetDeviceExtension[8].SystemResourcesList.Flink) )
            {
              QueueStatistics = SrvXsConnect(&DestinationString);
              if ( QueueStatistics >= 0 )
                LOBYTE(SrvNetDeviceExtension[8].SystemResourcesList.Flink) = 1;
            }
            ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 120));
            KeLeaveCriticalRegion();
            RtlFreeUnicodeString(&DestinationString);
          }
        }
        else
        {
          QueueStatistics = -1073741637;
        }
        goto LABEL_66;
    }
    if ( a7 != 1327131 )
    {
      if ( a7 == 1327168 )
      {
        QueueStatistics = 0;
        Irp = a11;
        goto LABEL_66;
      }
      goto LABEL_46;
    }
  }
  Irp = a11;
  if ( !a11 )
  {
    QueueStatistics = -1073741637;
    goto LABEL_66;
  }
  WorkItem = IoAllocateWorkItem((PDEVICE_OBJECT)SrvNetDeviceObject);
  IoWorkItem = WorkItem;
  if ( !WorkItem )
  {
    QueueStatistics = -1073741670;
    goto LABEL_66;
  }
  if ( Length )
  {
    if ( !IoAllocateMdl(VirtualAddress, Length, 0, 1u, Irp) )
    {
LABEL_53:
      IoFreeWorkItem(WorkItem);
      QueueStatistics = -1073741670;
      goto LABEL_66;
    }
    Irp->MdlAddress->MdlFlags |= 0x2000u;
    MmProbeAndLockPages(Irp->MdlAddress, Irp->RequestorMode, IoReadAccess);
  }
  else
  {
    Irp->MdlAddress = 0;
  }
  if ( (_DWORD)v11 )
  {
    Pool2 = (struct _IRP *)ExAllocatePool2(258, v11, 1717719884);
    Irp->AssociatedIrp.MasterIrp = Pool2;
    if ( !Pool2 )
    {
      MdlAddress = Irp->MdlAddress;
      if ( MdlAddress )
      {
        MmUnlockPages(MdlAddress);
        IoFreeMdl(Irp->MdlAddress);
        Irp->MdlAddress = 0;
      }
      goto LABEL_53;
    }
    if ( a10 )
      RtlCopyFromUser(Pool2, a3, v11);
    else
      RtlCopyVolatileMemory(Pool2, a3, v11);
  }
  else
  {
    Irp->AssociatedIrp.MasterIrp = 0;
  }
  Irp->Tail.Overlay.AuxiliaryBuffer = (PCHAR)WorkItem;
  *(_DWORD *)a8 = 259;
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  IoQueueWorkItem(WorkItem, (PIO_WORKITEM_ROUTINE)SrvNetProcessFsctlFsp, CriticalWorkQueue, Irp);
  QueueStatistics = 259;
LABEL_66:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      WPP_6a4d2c8a1a8134e9dfbfd0e9f83a7911_Traceguids,
      a7,
      QueueStatistics);
  }
  if ( Irp && QueueStatistics != 259 )
  {
    Irp->IoStatus.Status = QueueStatistics;
    IofCompleteRequest(Irp, 2);
  }
  return (unsigned int)QueueStatistics;
}

```

## disassembly

```asm
0x140050940  mov     rax, rsp
0x140050943  push    rbx
0x140050944  push    rsi
0x140050945  push    rdi
0x140050946  push    r12
0x140050948  push    r13
0x14005094a  push    r14
0x14005094c  push    r15
0x14005094e  sub     rsp, 220h
0x140050955  movaps  xmmword ptr [rax-48h], xmm6
0x140050959  movaps  xmmword ptr [rax-58h], xmm7
0x14005095d  movaps  xmmword ptr [rax-68h], xmm8
0x140050962  movaps  xmmword ptr [rax-78h], xmm9
0x140050967  movaps  xmmword ptr [rax-88h], xmm10
0x14005096f  movaps  xmmword ptr [rax-98h], xmm11
0x140050977  movaps  xmmword ptr [rax-0A8h], xmm12
0x14005097f  movaps  xmmword ptr [rax-0B8h], xmm13
0x140050987  movaps  xmmword ptr [rax-0C8h], xmm14
0x14005098f  movaps  xmmword ptr [rax-0D8h], xmm15
0x140050997  mov     r14d, r9d
0x14005099a  mov     r15, r8
0x14005099d  mov     r8, [rsp+258h+IoWorkItem]
0x1400509a5  mov     esi, [rsp+258h+arg_30]
0x1400509ac  cmp     r8, cs:SrvNetAdminDeviceObject
0x1400509b3  jnz     loc_140050ABA
0x1400509b9  lea     eax, [rsi-146407h]
0x1400509bf  cmp     eax, 0Ch
0x1400509c2  ja      short loc_1400509D4
0x1400509c4  mov     r9d, 1111h
0x1400509ca  bt      r9d, eax
0x1400509ce  jb      loc_140050ABA
0x1400509d4  lea     eax, [rsi-144014h]
0x1400509da  cmp     eax, 33h ; '3'
0x1400509dd  ja      short loc_1400509F3
0x1400509df  mov     r9, 8100000000081h
0x1400509e9  bt      r9, rax
0x1400509ed  jb      loc_140050ABA
0x1400509f3  cmp     esi, 14000Ch
0x1400509f9  jz      loc_140050ABA
0x1400509ff  cmp     esi, 140048h
0x140050a05  jz      loc_140050ABA
0x140050a0b  cmp     esi, 14609Bh
0x140050a11  jz      loc_140050ABA
0x140050a17  mov     rax, [rsp+258h+arg_50]
0x140050a1f  mov     [rsp+258h+var_208], rax
0x140050a24  movzx   eax, [rsp+258h+arg_48]
0x140050a2c  mov     [rsp+258h+var_210], al
0x140050a30  mov     [rsp+258h+var_218], r8
0x140050a35  mov     rax, [rsp+258h+arg_38]
0x140050a3d  mov     [rsp+258h+var_220], rax
0x140050a42  mov     [rsp+258h+var_228], esi
0x140050a46  mov     eax, [rsp+258h+Length]
0x140050a4d  mov     [rsp+258h+var_230], eax
0x140050a51  mov     rax, [rsp+258h+VirtualAddress]
0x140050a59  mov     [rsp+258h+Irp], rax
0x140050a5e  mov     r9d, r14d
0x140050a61  mov     r8, r15
0x140050a64  call    SrvAdminProcessFsctl
0x140050a69  mov     ebx, eax
0x140050a6b  lea     rdx, WPP_GLOBAL_Control; __annotation("TMF:",
0x140050a72  mov     rcx, cs:WPP_GLOBAL_Control
0x140050a79  cmp     rcx, rdx
0x140050a7c  jz      loc_1400510C0
0x140050a82  test    dword ptr [rcx+2Ch], 4000h
0x140050a89  jz      loc_1400510C0
0x140050a8f  cmp     byte ptr [rcx+29h], 2
0x140050a93  jb      loc_1400510C0
0x140050a99  mov     edx, 0Eh
0x140050a9e  mov     dword ptr [rsp+258h+Irp], eax
0x140050aa2  mov     r9d, esi
0x140050aa5  lea     r8, WPP_6a4d2c8a1a8134e9dfbfd0e9f83a7911_Traceguids
0x140050aac  mov     rcx, [rcx+18h]
0x140050ab0  call    WPP_SF_Dd
0x140050ab5  jmp     loc_1400510C0
0x140050aba  xor     r13d, r13d
0x140050abd  mov     r12, [rsp+258h+arg_38]
0x140050ac5  mov     [r12+8], r13
0x140050aca  cmp     esi, 144047h
0x140050ad0  ja      loc_140050DF5
0x140050ad6  jz      loc_140050DE0
0x140050adc  mov     eax, esi
0x140050ade  sub     eax, 14000Ch
0x140050ae3  jz      loc_140050C6D
0x140050ae9  sub     eax, 3Ch ; '<'
0x140050aec  jz      loc_140050C07
0x140050af2  sub     eax, 3FCCh
0x140050af7  jz      short loc_140050B1B
0x140050af9  sub     eax, 7
0x140050afc  jz      loc_140050E26
0x140050b02  cmp     eax, 25h ; '%'
0x140050b05  jnz     loc_140050E14
0x140050b0b  mov     ebx, r13d
0x140050b0e  mov     rdi, [rsp+258h+arg_50]
0x140050b16  jmp     loc_140051061
0x140050b1b  mov     qword ptr [rsp+258h+SourceString.Length], r13
0x140050b20  xorps   xmm0, xmm0
0x140050b23  movups  xmmword ptr [rsp+258h+DestinationString.Length], xmm0
0x140050b28  mov     rdi, [rsp+258h+arg_50]
0x140050b30  test    rdi, rdi
0x140050b33  jnz     short loc_140050B3F
0x140050b35  mov     ebx, 0C00000BBh
0x140050b3a  jmp     loc_140051061
0x140050b3f  mov     rax, [rdi+18h]
0x140050b43  mov     [rsp+258h+SourceString.Buffer], rax
0x140050b48  mov     rax, [rdi+0B8h]
0x140050b4f  movzx   ecx, word ptr [rax+10h]
0x140050b53  mov     [rsp+258h+SourceString.Length], cx
0x140050b58  mov     r8b, 1; AllocateDestinationString
0x140050b5b  lea     rdx, [rsp+258h+SourceString]; SourceString
0x140050b60  lea     rcx, [rsp+258h+DestinationString]; DestinationString
0x140050b65  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140050b6c  nop     dword ptr [rax+rax+00h]
0x140050b71  mov     ebx, eax
0x140050b73  test    eax, eax
0x140050b75  js      loc_140051061
0x140050b7b  call    cs:__imp_KeEnterCriticalRegion
0x140050b82  nop     dword ptr [rax+rax+00h]
0x140050b87  mov     rcx, cs:SrvNetDeviceExtension
0x140050b8e  add     rcx, 78h ; 'x'; Resource
0x140050b92  mov     dl, 1; Wait
0x140050b94  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140050b9b  nop     dword ptr [rax+rax+00h]
0x140050ba0  mov     rcx, cs:SrvNetDeviceExtension
0x140050ba7  cmp     [rcx+340h], r13b
0x140050bae  jnz     short loc_140050BCE
0x140050bb0  lea     rcx, [rsp+258h+DestinationString]; String1
0x140050bb5  call    SrvXsConnect
0x140050bba  mov     ebx, eax
0x140050bbc  test    eax, eax
0x140050bbe  js      short loc_140050BCE
0x140050bc0  mov     rax, cs:SrvNetDeviceExtension
0x140050bc7  mov     byte ptr [rax+340h], 1
0x140050bce  mov     rcx, cs:SrvNetDeviceExtension
0x140050bd5  add     rcx, 78h ; 'x'; Resource
0x140050bd9  call    cs:__imp_ExReleaseResourceLite
0x140050be0  nop     dword ptr [rax+rax+00h]
0x140050be5  call    cs:__imp_KeLeaveCriticalRegion
0x140050bec  nop     dword ptr [rax+rax+00h]
0x140050bf1  lea     rcx, [rsp+258h+DestinationString]; UnicodeString
0x140050bf6  call    cs:__imp_RtlFreeUnicodeString
0x140050bfd  nop     dword ptr [rax+rax+00h]
0x140050c02  jmp     loc_140051061
0x140050c07  mov     dword ptr [rsp+258h+IoWorkItem], r13d
0x140050c0f  mov     rdi, [rsp+258h+arg_50]
0x140050c17  test    rdi, rdi
0x140050c1a  jnz     short loc_140050C26
0x140050c1c  mov     ebx, 0C00000BBh
0x140050c21  jmp     loc_140051061
0x140050c26  mov     rax, cs:SrvNetDeviceExtension
0x140050c2d  cmp     [rax+340h], r13b
0x140050c34  jnz     short loc_140050C40
0x140050c36  mov     ebx, 0C0000466h
0x140050c3b  jmp     loc_140051061
0x140050c40  mov     rdx, [rdi+0B8h]
0x140050c47  lea     r8, [rsp+258h+IoWorkItem]
0x140050c4f  mov     edx, [rdx+8]
0x140050c52  mov     rcx, [rdi+18h]
0x140050c56  call    SrvNetGetQueueStatistics
0x140050c5b  mov     ebx, eax
0x140050c5d  mov     eax, dword ptr [rsp+258h+IoWorkItem]
0x140050c64  mov     [rdi+38h], rax
0x140050c68  jmp     loc_140051061
0x140050c6d  mov     rdi, [rsp+258h+arg_50]
0x140050c75  test    rdi, rdi
0x140050c78  jnz     short loc_140050C84
0x140050c7a  mov     ebx, 0C00000BBh
0x140050c7f  jmp     loc_140051061
0x140050c84  mov     rax, cs:SrvNetDeviceExtension
0x140050c8b  cmp     [rax+340h], r13b
0x140050c92  jnz     short loc_140050C9E
0x140050c94  mov     ebx, 0C0000466h
0x140050c99  jmp     loc_140051061
0x140050c9e  mov     rax, [rdi+0B8h]
0x140050ca5  cmp     dword ptr [rax+8], 0D8h
0x140050cac  jnb     short loc_140050CB8
0x140050cae  mov     ebx, 0C0000023h
0x140050cb3  jmp     loc_140051061
0x140050cb8  call    SrvNetUpdateStatisticsFromQueues
0x140050cbd  movups  xmm12, cs:SrvNetStatistics
0x140050cc5  movups  xmm13, cs:xmmword_1400365A0
0x140050ccd  movups  xmm14, cs:xmmword_1400365B0
0x140050cd5  movups  xmm15, cs:xmmword_1400365C0
0x140050cdd  movups  xmm0, cs:xmmword_1400365D0
0x140050ce4  movups  xmmword ptr [rsp+258h+DestinationString.Length], xmm0
0x140050ce9  movups  xmm0, xmmword ptr cs:byte_1400365E0
0x140050cf0  movups  xmmword ptr [rsp+258h+SourceString.Length], xmm0
0x140050cf5  movups  xmm0, cs:xmmword_1400365F0
0x140050cfc  movups  [rsp+258h+var_1D0], xmm0
0x140050d04  movups  xmm6, cs:xmmword_140036600
0x140050d0b  movaps  [rsp+258h+var_148], xmm6
0x140050d13  movups  xmm7, cs:xmmword_140036610
0x140050d1a  movups  xmm8, cs:xmmword_140036620
0x140050d22  movups  xmm9, cs:xmmword_140036630
0x140050d2a  movups  xmm10, cs:xmmword_140036640
0x140050d32  movups  xmm11, cs:xmmword_140036650
0x140050d3a  mov     rbx, cs:qword_140036660
0x140050d41  call    cs:__imp_KeQueryTimeIncrement
0x140050d48  nop     dword ptr [rax+rax+00h]
0x140050d4d  movsxd  rcx, eax
0x140050d50  movq    rax, xmm6
0x140050d55  imul    rax, rcx
0x140050d59  mov     qword ptr [rsp+258h+var_148], rax
0x140050d61  mov     rax, [rdi+18h]
0x140050d65  movups  xmmword ptr [rax], xmm12
0x140050d69  movups  xmmword ptr [rax+10h], xmm13
0x140050d6e  movups  xmmword ptr [rax+20h], xmm14
0x140050d73  movups  xmmword ptr [rax+30h], xmm15
0x140050d78  movups  xmm0, xmmword ptr [rsp+258h+DestinationString.Length]
0x140050d7d  movups  xmmword ptr [rax+40h], xmm0
0x140050d81  movups  xmm1, xmmword ptr [rsp+258h+SourceString.Length]
0x140050d86  movups  xmmword ptr [rax+50h], xmm1
0x140050d8a  movups  xmm0, [rsp+258h+var_1D0]
0x140050d92  movups  xmmword ptr [rax+60h], xmm0
0x140050d96  movaps  xmm0, [rsp+258h+var_148]
0x140050d9e  movups  xmmword ptr [rax+70h], xmm0
0x140050da2  movups  xmmword ptr [rax+80h], xmm7
0x140050da9  movups  xmmword ptr [rax+90h], xmm8
0x140050db1  movups  xmmword ptr [rax+0A0h], xmm9
0x140050db9  movups  xmmword ptr [rax+0B0h], xmm10
0x140050dc1  movups  xmmword ptr [rax+0C0h], xmm11
0x140050dc9  mov     [rax+0D0h], rbx
0x140050dd0  mov     qword ptr [rdi+38h], 0D8h
0x140050dd8  mov     ebx, r13d
0x140050ddb  jmp     loc_140051061
0x140050de0  call    SrvNetRefreshLanmanServerParameters
0x140050de5  mov     ebx, r13d
0x140050de8  mov     rdi, [rsp+258h+arg_50]
0x140050df0  jmp     loc_140051061
0x140050df5  mov     eax, esi
0x140050df7  sub     eax, 14609Bh
0x140050dfc  jz      short loc_140050E26
0x140050dfe  sub     eax, 36Ch
0x140050e03  jz      short loc_140050E26
0x140050e05  sub     eax, 4
0x140050e08  jz      short loc_140050E26
0x140050e0a  sub     eax, 4
0x140050e0d  jz      short loc_140050E26
0x140050e0f  cmp     eax, 4
0x140050e12  jz      short loc_140050E26
0x140050e14  mov     ebx, 0C0000002h
0x140050e19  mov     rdi, [rsp+258h+arg_50]
0x140050e21  jmp     loc_140051061
0x140050e26  mov     rdi, [rsp+258h+arg_50]
0x140050e2e  test    rdi, rdi
0x140050e31  jnz     short loc_140050E3D
0x140050e33  mov     ebx, 0C00000BBh
0x140050e38  jmp     loc_140051061
0x140050e3d  mov     rcx, cs:SrvNetDeviceObject; DeviceObject
0x140050e44  call    cs:__imp_IoAllocateWorkItem
0x140050e4b  nop     dword ptr [rax+rax+00h]
0x140050e50  mov     rbx, rax
0x140050e53  mov     [rsp+258h+IoWorkItem], rax
0x140050e5b  test    rax, rax
0x140050e5e  jnz     short loc_140050E6A
0x140050e60  mov     ebx, 0C000009Ah
0x140050e65  jmp     loc_140051061
0x140050e6a  mov     edx, [rsp+258h+Length]; Length
0x140050e71  test    edx, edx
0x140050e73  jz      loc_140050F1F
0x140050e79  mov     [rsp+258h+Irp], rdi; Irp
0x140050e7e  mov     r9b, 1; ChargeQuota
0x140050e81  xor     r8d, r8d; SecondaryBuffer
0x140050e84  mov     rcx, [rsp+258h+VirtualAddress]; VirtualAddress
0x140050e8c  call    cs:__imp_IoAllocateMdl
0x140050e93  nop     dword ptr [rax+rax+00h]
0x140050e98  test    rax, rax
0x140050e9b  jnz     short loc_140050EB6
0x140050e9d  mov     rcx, rbx; IoWorkItem
0x140050ea0  call    cs:__imp_IoFreeWorkItem
0x140050ea7  nop     dword ptr [rax+rax+00h]
0x140050eac  mov     ebx, 0C000009Ah
0x140050eb1  jmp     loc_140051061
0x140050eb6  mov     rax, [rdi+8]
0x140050eba  mov     ecx, 2000h
0x140050ebf  or      [rax+0Ah], cx
0x140050ec3  xor     r8d, r8d; Operation
0x140050ec6  movzx   edx, byte ptr [rdi+40h]; AccessMode
0x140050eca  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140050ece  call    cs:__imp_MmProbeAndLockPages
0x140050ed5  nop     dword ptr [rax+rax+00h]
0x140050eda  nop
0x140050edb  jmp     short loc_140050F23
0x140050edd  mov     ebx, eax
0x140050edf  mov     rdi, [rsp+258h+arg_50]
0x140050ee7  mov     rcx, [rdi+8]; Mdl
0x140050eeb  call    cs:__imp_IoFreeMdl
0x140050ef2  nop     dword ptr [rax+rax+00h]
0x140050ef7  mov     qword ptr [rdi+8], 0
0x140050eff  mov     rcx, [rsp+258h+IoWorkItem]; IoWorkItem
0x140050f07  call    cs:__imp_IoFreeWorkItem
0x140050f0e  nop     dword ptr [rax+rax+00h]
0x140050f13  mov     esi, [rsp+258h+arg_30]
0x140050f1a  jmp     loc_140051061
0x140050f1f  mov     [rdi+8], r13
0x140050f23  test    r14d, r14d
0x140050f26  jz      loc_140051022
0x140050f2c  mov     r8d, 6662534Ch
0x140050f32  mov     rdx, r14
0x140050f35  mov     ecx, 102h
0x140050f3a  call    cs:__imp_ExAllocatePool2
  ... truncated ...
```
