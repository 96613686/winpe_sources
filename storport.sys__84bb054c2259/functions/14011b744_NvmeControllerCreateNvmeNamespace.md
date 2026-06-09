# NvmeControllerCreateNvmeNamespace

- ea: `0x14011b744`
- end: `0x14011bd28`
- name: `NvmeControllerCreateNvmeNamespace`
- size: `1508`
- prototype: ``
- caller_count: `4`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400e8074`
- `0x1400e8c50`
- `0x140105da4`
- `0x14010a0dc`

## callees

- `0x1400290b0`
- `0x140066cc0`
- `0x140066d94`
- `0x14007d330`
- `0x1401073d0`
- `0x14011acc0`
- `0x14011b744`
- `0x14011d430`
- `0x14011d6dc`
- `0x14011d77c`
- `0x14011dbe0`
- `0x14011dc48`
- `0x1401224dc`
- `0x14012a524`
- `0x14012b204`
- `0x14012b2e8`
- `0x14013ce34`
- `0x14013d568`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14011b86c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14011bb91`
- `ntoskrnl!KeInitializeSpinLock` at `0x14011b86c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14011bb91`
- `ntoskrnl!IoDeleteDevice` at `0x14011bcfd`
- `ntoskrnl!IoDeleteDevice` at `0x14011bcfd`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14011b7dc`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14011b7dc`
- `ntoskrnl!IoFreeWorkItem` at `0x14011bc31`
- `ntoskrnl!IoFreeWorkItem` at `0x14011bc31`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011bc93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011bcb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011bc93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011bcb4`
- `ntoskrnl!KeInitializeEvent` at `0x14011b8d6`
- `ntoskrnl!KeInitializeEvent` at `0x14011b8d6`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14011bce0`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14011bce0`
- `ntoskrnl!IoCreateDevice` at `0x14011b7a3`
- `ntoskrnl!IoCreateDevice` at `0x14011b7a3`
- `ntoskrnl!IoAllocateWorkItem` at `0x14011bbf7`
- `ntoskrnl!IoAllocateWorkItem` at `0x14011bbf7`

## string_xrefs

- `0x14011ba2f`: `Identify namespace descriptor failed`

## pseudocode

```c
__int64 __fastcall NvmeControllerCreateNvmeNamespace(__int64 a1, int a2, __int64 a3, _QWORD *a4)
{
  __int64 v4; // rax
  NTSTATUS FabricControllerIdentifyData; // edi
  _DWORD *DeviceExtension; // rbx
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  PDEVICE_OBJECT v11; // rax
  __int64 IoQueue; // rax
  __int64 v13; // rax
  char v14; // al
  int v15; // edx
  int v16; // r8d
  __int64 v17; // rdx
  unsigned __int16 v18; // ax
  __int64 Pool; // rax
  __int64 ExtendedCommand; // rax
  __int64 v21; // rdx
  __int16 v22; // ax
  PIO_WORKITEM WorkItem; // rax
  struct _IO_WORKITEM *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v27; // rcx
  PDEVICE_OBJECT DeviceObject; // [rsp+D0h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 128);
  DeviceObject = 0;
  FabricControllerIdentifyData = IoCreateDevice(
                                   *(PDRIVER_OBJECT *)(*(_QWORD *)(v4 + 8) + 8LL),
                                   0x2C0u,
                                   0,
                                   0x2Du,
                                   0x180u,
                                   0,
                                   &DeviceObject);
  if ( FabricControllerIdentifyData >= 0 )
  {
    DeviceExtension = DeviceObject->DeviceExtension;
    memset_0(DeviceExtension, 0, 0x2C0u);
    CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection(NonPagedPoolNx, 0x6D526152u);
    *((_QWORD *)DeviceExtension + 15) = CacheAwareRundownProtection;
    if ( !CacheAwareRundownProtection )
    {
      FabricControllerIdentifyData = -1073741801;
      goto LABEL_30;
    }
    DeviceObject->Flags |= 0x10u;
    *((_QWORD *)DeviceExtension + 4) = DeviceExtension + 6;
    *((_QWORD *)DeviceExtension + 3) = DeviceExtension + 6;
    *DeviceExtension = 1314278989;
    v11 = DeviceObject;
    *((_QWORD *)DeviceExtension + 14) |= 2uLL;
    *((_QWORD *)DeviceExtension + 1) = v11;
    *((_QWORD *)DeviceExtension + 2) = a1;
    DeviceExtension[14] = a2;
    *((_BYTE *)DeviceExtension + 60) = 0;
    DeviceExtension[24] = 2;
    *((_BYTE *)DeviceExtension + 100) = *(_BYTE *)(a1 + 616);
    *((_BYTE *)DeviceExtension + 101) = *(_BYTE *)(a1 + 617);
    *((_BYTE *)DeviceExtension + 102) = a2;
    *((_WORD *)DeviceExtension + 212) = *(_WORD *)(*(_QWORD *)(a1 + 128) + 1108LL);
    KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 13);
    IoQueue = NvmeNamespaceCreateIoQueue(DeviceExtension);
    *((_QWORD *)DeviceExtension + 32) = IoQueue;
    if ( IoQueue )
    {
      v13 = NvmeNamespaceCreateIoQueue(DeviceExtension);
      *((_QWORD *)DeviceExtension + 33) = v13;
      if ( v13 )
      {
        _interlockedbittestandset(*((volatile signed __int32 **)DeviceExtension + 32), 2u);
        _interlockedbittestandset(*((volatile signed __int32 **)DeviceExtension + 33), 2u);
        KeInitializeEvent((PRKEVENT)DeviceExtension + 20, SynchronizationEvent, 0);
        if ( (*(_BYTE *)(*((_QWORD *)DeviceExtension + 2) + 136LL) & 2) != 0 )
        {
          v14 = *((_BYTE *)DeviceExtension + 60);
          v15 = DeviceExtension[14];
          *((_QWORD *)DeviceExtension + 14) |= 4uLL;
          FabricControllerIdentifyData = NvmeAdapterGetFabricControllerIdentifyData(
                                           a1,
                                           v15,
                                           0,
                                           0,
                                           v14,
                                           (__int64)(DeviceExtension + 44));
          if ( FabricControllerIdentifyData < 0 )
          {
            StorEtwNvmeNamespaceEvent(
              (_DWORD)DeviceExtension,
              1,
              2,
              (unsigned int)L"Identify namespace failed",
              (__int64)L"NtStatus",
              FabricControllerIdentifyData,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0);
            goto LABEL_30;
          }
          LOBYTE(v16) = 3;
          FabricControllerIdentifyData = NvmeAdapterGetFabricControllerIdentifyData(
                                           a1,
                                           DeviceExtension[14],
                                           v16,
                                           0,
                                           0,
                                           (__int64)(DeviceExtension + 46));
          if ( FabricControllerIdentifyData < 0 )
          {
            StorEtwNvmeNamespaceEvent(
              (_DWORD)DeviceExtension,
              1,
              2,
              (unsigned int)L"Identify namespace descriptor failed",
              (__int64)L"NtStatus",
              FabricControllerIdentifyData,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0);
            goto LABEL_30;
          }
          if ( (unsigned __int8)NvmeNamespaceIsInactive(*((_QWORD *)DeviceExtension + 22)) )
          {
            StorEtwNvmeNamespaceEvent(
              (_DWORD)DeviceExtension,
              1,
              3,
              (unsigned int)L"Inactive namespace",
              (__int64)L"NSZE",
              *(_QWORD *)v17,
              (__int64)L"LBADS",
              *(_BYTE *)(v17 + 4LL * (*(_BYTE *)(v17 + 26) & 0xF) + 130),
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0,
              (__int64)&word_140155F3C,
              0);
            FabricControllerIdentifyData = -1073741637;
            goto LABEL_30;
          }
          if ( *(_QWORD *)(a1 + 624) )
          {
            v18 = *(_WORD *)(v17 + 100);
            if ( v18 <= *(_WORD *)(a1 + 618) )
              *((_WORD *)DeviceExtension + 31) = v18;
          }
          if ( !*((_BYTE *)DeviceExtension + 60) )
            NvmeNamespaceComputeBlockInfo(DeviceExtension);
        }
        FabricControllerIdentifyData = NvmeNamespaceInitializeIoTracking(DeviceExtension);
        if ( FabricControllerIdentifyData < 0 )
          goto LABEL_30;
        Pool = RaidAllocatePool(72, 2328, 1700028754, *((_QWORD *)DeviceExtension + 1));
        *((_QWORD *)DeviceExtension + 78) = Pool;
        if ( Pool )
        {
          FabricControllerIdentifyData = NvmeNamespacePowerInitialize(DeviceExtension);
          if ( FabricControllerIdentifyData < 0
            || (FabricControllerIdentifyData = NvmeNamespaceCreateErrorRecoveryContext(DeviceExtension),
                FabricControllerIdentifyData < 0) )
          {
LABEL_30:
            if ( DeviceExtension )
            {
              v24 = (struct _IO_WORKITEM *)*((_QWORD *)DeviceExtension + 69);
              if ( v24 )
              {
                IoFreeWorkItem(v24);
                *((_QWORD *)DeviceExtension + 69) = 0;
              }
              if ( *((_QWORD *)DeviceExtension + 68) )
              {
                NvmeControllerFreeExtendedCommand(*((_QWORD *)DeviceExtension + 2));
                *((_QWORD *)DeviceExtension + 68) = 0;
              }
              NvmeNamespaceDeleteErrorRecoveryContext(DeviceExtension);
              NvmeNamespaceUninitializeIoTracking(DeviceExtension);
              NvmeNamespacePowerUninitialize(DeviceExtension);
              NvmeNamespaceTelemetryDelete(DeviceExtension);
              v25 = (void *)*((_QWORD *)DeviceExtension + 23);
              if ( v25 )
              {
                ExFreePoolWithTag(v25, 0x52436152u);
                *((_QWORD *)DeviceExtension + 23) = 0;
              }
              v26 = (void *)*((_QWORD *)DeviceExtension + 22);
              if ( v26 )
              {
                ExFreePoolWithTag(v26, 0x52436152u);
                *((_QWORD *)DeviceExtension + 22) = 0;
              }
              NvmeNamespaceTerminateSystemThread(DeviceExtension);
              NvmeNamespaceDeleteIoQueue(DeviceExtension);
              v27 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)DeviceExtension + 15);
              if ( v27 )
              {
                ExFreeCacheAwareRundownProtection(v27);
                *((_QWORD *)DeviceExtension + 15) = 0;
              }
            }
            goto LABEL_41;
          }
          if ( (*(_BYTE *)(*((_QWORD *)DeviceExtension + 2) + 136LL) & 2) != 0 )
            goto LABEL_28;
          KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 70);
          *((_QWORD *)DeviceExtension + 73) = DeviceExtension + 144;
          *((_QWORD *)DeviceExtension + 72) = DeviceExtension + 144;
          *((_QWORD *)DeviceExtension + 76) = DeviceExtension + 150;
          *((_QWORD *)DeviceExtension + 75) = DeviceExtension + 150;
          ExtendedCommand = NvmeControllerAllocateExtendedCommand(*((_QWORD *)DeviceExtension + 2));
          *((_QWORD *)DeviceExtension + 68) = ExtendedCommand;
          v21 = ExtendedCommand;
          if ( ExtendedCommand )
          {
            v22 = 10;
            if ( (unsigned int)(3 * *(_DWORD *)(*(_QWORD *)(*((_QWORD *)DeviceExtension + 2) + 128LL) + 1108LL)) > 0xA )
              v22 = 3 * *(_WORD *)(*(_QWORD *)(*((_QWORD *)DeviceExtension + 2) + 128LL) + 1108LL);
            *(_WORD *)(v21 + 68) = v22;
            WorkItem = IoAllocateWorkItem(*((PDEVICE_OBJECT *)DeviceExtension + 1));
            *((_QWORD *)DeviceExtension + 69) = WorkItem;
            if ( WorkItem )
            {
LABEL_28:
              *a4 = DeviceExtension;
              return (unsigned int)FabricControllerIdentifyData;
            }
          }
        }
      }
    }
    FabricControllerIdentifyData = -1073741670;
    goto LABEL_30;
  }
LABEL_41:
  if ( DeviceObject )
    IoDeleteDevice(DeviceObject);
  return (unsigned int)FabricControllerIdentifyData;
}

```

## disassembly

```asm
0x14011b744  mov     r11, rsp
0x14011b747  mov     [r11+10h], rbx
0x14011b74b  mov     [r11+18h], rbp
0x14011b74f  push    rsi
0x14011b750  push    rdi
0x14011b751  push    r12
0x14011b753  push    r14
0x14011b755  push    r15
0x14011b757  sub     rsp, 0A0h
0x14011b75e  mov     rax, [rcx+80h]
0x14011b765  xor     r12d, r12d
0x14011b768  mov     rsi, rcx
0x14011b76b  mov     [r11+8], r12
0x14011b76f  mov     r15, r9
0x14011b772  mov     ebp, edx
0x14011b774  mov     r14d, 2C0h
0x14011b77a  xor     r8d, r8d; DeviceName
0x14011b77d  mov     rcx, [rax+8]
0x14011b781  lea     r9d, [r12+2Dh]; DeviceType
0x14011b786  lea     rax, [r11+8]
0x14011b78a  mov     edx, r14d; DeviceExtensionSize
0x14011b78d  mov     [rsp+0C8h+DeviceObject], rax; DeviceObject
0x14011b792  mov     [rsp+0C8h+Exclusive], r12b; Exclusive
0x14011b797  mov     rcx, [rcx+8]; DriverObject
0x14011b79b  mov     [rsp+0C8h+DeviceCharacteristics], 180h; DeviceCharacteristics
0x14011b7a3  call    cs:__imp_IoCreateDevice
0x14011b7aa  nop     dword ptr [rax+rax+00h]
0x14011b7af  mov     edi, eax
0x14011b7b1  test    eax, eax
0x14011b7b3  js      loc_14011BCF0
0x14011b7b9  mov     rax, [rsp+0C8h+arg_0]
0x14011b7c1  mov     r8d, r14d; Size
0x14011b7c4  xor     edx, edx; Val
0x14011b7c6  mov     rbx, [rax+40h]
0x14011b7ca  mov     rcx, rbx; void *
0x14011b7cd  call    memset_0
0x14011b7d2  mov     edx, 6D526152h; PoolTag
0x14011b7d7  mov     ecx, 200h; PoolType
0x14011b7dc  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14011b7e3  nop     dword ptr [rax+rax+00h]
0x14011b7e8  mov     [rbx+78h], rax
0x14011b7ec  test    rax, rax
0x14011b7ef  jnz     short loc_14011B7FB
0x14011b7f1  mov     edi, 0C0000017h
0x14011b7f6  jmp     loc_14011BC1C
0x14011b7fb  mov     rax, [rsp+0C8h+arg_0]
0x14011b803  or      dword ptr [rax+30h], 10h
0x14011b807  lea     rax, [rbx+18h]
0x14011b80b  mov     [rax+8], rax
0x14011b80f  mov     [rax], rax
0x14011b812  mov     dword ptr [rbx], 4E564E4Dh
0x14011b818  mov     rax, [rsp+0C8h+arg_0]
0x14011b820  or      qword ptr [rbx+70h], 2
0x14011b825  mov     [rbx+8], rax
0x14011b829  mov     [rbx+10h], rsi
0x14011b82d  mov     [rbx+38h], ebp
0x14011b830  mov     [rbx+3Ch], r12b
0x14011b834  mov     dword ptr [rbx+60h], 2
0x14011b83b  mov     al, [rsi+268h]
0x14011b841  mov     [rbx+64h], al
0x14011b844  mov     al, [rsi+269h]
0x14011b84a  mov     [rbx+65h], al
0x14011b84d  mov     al, bpl
0x14011b850  mov     [rbx+66h], al
0x14011b853  mov     rax, [rsi+80h]
0x14011b85a  movzx   ecx, word ptr [rax+454h]
0x14011b861  mov     [rbx+1A8h], cx
0x14011b868  lea     rcx, [rbx+68h]; SpinLock
0x14011b86c  call    cs:__imp_KeInitializeSpinLock
0x14011b873  nop     dword ptr [rax+rax+00h]
0x14011b878  xor     edx, edx
0x14011b87a  mov     rcx, rbx; DeferredContext
0x14011b87d  call    NvmeNamespaceCreateIoQueue
0x14011b882  mov     [rbx+100h], rax
0x14011b889  test    rax, rax
0x14011b88c  jz      loc_14011BC17
0x14011b892  mov     ebp, 1
0x14011b897  mov     rcx, rbx; DeferredContext
0x14011b89a  mov     dl, bpl
0x14011b89d  call    NvmeNamespaceCreateIoQueue
0x14011b8a2  mov     [rbx+108h], rax
0x14011b8a9  test    rax, rax
0x14011b8ac  jz      loc_14011BC17
0x14011b8b2  mov     rax, [rbx+100h]
0x14011b8b9  lea     rcx, [rbx+1E0h]; Event
0x14011b8c0  xor     r8d, r8d; State
0x14011b8c3  mov     edx, ebp; Type
0x14011b8c5  lock bts dword ptr [rax], 2
0x14011b8ca  mov     rax, [rbx+108h]
0x14011b8d1  lock bts dword ptr [rax], 2
0x14011b8d6  call    cs:__imp_KeInitializeEvent
0x14011b8dd  nop     dword ptr [rax+rax+00h]
0x14011b8e2  mov     rax, [rbx+10h]
0x14011b8e6  test    byte ptr [rax+88h], 2
0x14011b8ed  jz      loc_14011BB1A
0x14011b8f3  mov     al, [rbx+3Ch]
0x14011b8f6  lea     r14, [rbx+0B0h]
0x14011b8fd  mov     edx, [rbx+38h]
0x14011b900  xor     r9d, r9d
0x14011b903  or      qword ptr [rbx+70h], 4
0x14011b908  xor     r8d, r8d
0x14011b90b  mov     qword ptr [rsp+0C8h+Exclusive], r14
0x14011b910  mov     rcx, rsi
0x14011b913  mov     byte ptr [rsp+0C8h+DeviceCharacteristics], al
0x14011b917  call    NvmeAdapterGetFabricControllerIdentifyData
0x14011b91c  movsxd  rdi, eax
0x14011b91f  test    eax, eax
0x14011b921  jns     loc_14011B9AD
0x14011b927  mov     [rsp+0C8h+var_30], r12
0x14011b92f  lea     r9, word_140155F3C
0x14011b936  mov     [rsp+0C8h+var_38], r9
0x14011b93e  mov     [rsp+0C8h+var_40], r12
0x14011b946  mov     [rsp+0C8h+var_48], r9
0x14011b94e  mov     [rsp+0C8h+var_50], r12
0x14011b953  mov     [rsp+0C8h+var_58], r9
0x14011b958  mov     [rsp+0C8h+var_60], r12
0x14011b95d  mov     [rsp+0C8h+var_68], r9
0x14011b962  mov     [rsp+0C8h+var_70], r12
0x14011b967  mov     [rsp+0C8h+var_78], r9
0x14011b96c  mov     [rsp+0C8h+var_80], r12
0x14011b971  mov     [rsp+0C8h+var_88], r9
0x14011b976  mov     [rsp+0C8h+var_90], r12
0x14011b97b  mov     [rsp+0C8h+DeviceObject], r9
0x14011b980  lea     r9, aIdentifyNamesp; "Identify namespace failed"
0x14011b987  lea     rax, aNtstatus; "NtStatus"
0x14011b98e  mov     qword ptr [rsp+0C8h+Exclusive], rdi
0x14011b993  mov     r8d, 2
0x14011b999  mov     qword ptr [rsp+0C8h+DeviceCharacteristics], rax
0x14011b99e  mov     edx, ebp
0x14011b9a0  mov     rcx, rbx
0x14011b9a3  call    StorEtwNvmeNamespaceEvent
0x14011b9a8  jmp     loc_14011BC1C
0x14011b9ad  mov     edx, [rbx+38h]
0x14011b9b0  lea     rax, [rbx+0B8h]
0x14011b9b7  mov     qword ptr [rsp+0C8h+Exclusive], rax
0x14011b9bc  xor     r9d, r9d
0x14011b9bf  mov     r8b, 3
0x14011b9c2  mov     byte ptr [rsp+0C8h+DeviceCharacteristics], r12b
0x14011b9c7  mov     rcx, rsi
0x14011b9ca  call    NvmeAdapterGetFabricControllerIdentifyData
0x14011b9cf  movsxd  rdi, eax
0x14011b9d2  test    eax, eax
0x14011b9d4  jns     short loc_14011BA3B
0x14011b9d6  mov     [rsp+0C8h+var_30], r12
0x14011b9de  lea     r9, word_140155F3C
0x14011b9e5  mov     [rsp+0C8h+var_38], r9
0x14011b9ed  mov     [rsp+0C8h+var_40], r12
0x14011b9f5  mov     [rsp+0C8h+var_48], r9
0x14011b9fd  mov     [rsp+0C8h+var_50], r12
0x14011ba02  mov     [rsp+0C8h+var_58], r9
0x14011ba07  mov     [rsp+0C8h+var_60], r12
0x14011ba0c  mov     [rsp+0C8h+var_68], r9
0x14011ba11  mov     [rsp+0C8h+var_70], r12
0x14011ba16  mov     [rsp+0C8h+var_78], r9
0x14011ba1b  mov     [rsp+0C8h+var_80], r12
0x14011ba20  mov     [rsp+0C8h+var_88], r9
0x14011ba25  mov     [rsp+0C8h+var_90], r12
0x14011ba2a  mov     [rsp+0C8h+DeviceObject], r9
0x14011ba2f  lea     r9, aIdentifyNamesp_0; "Identify namespace descriptor failed"
0x14011ba36  jmp     loc_14011B987
0x14011ba3b  mov     rdx, [r14]
0x14011ba3e  mov     rcx, rdx
0x14011ba41  call    NvmeNamespaceIsInactive
0x14011ba46  test    al, al
0x14011ba48  jz      loc_14011BAF2
0x14011ba4e  movzx   eax, byte ptr [rdx+1Ah]
0x14011ba52  lea     r9, word_140155F3C
0x14011ba59  mov     [rsp+0C8h+var_30], r12
0x14011ba61  and     eax, 0Fh
0x14011ba64  mov     [rsp+0C8h+var_38], r9
0x14011ba6c  mov     r8d, 3
0x14011ba72  mov     [rsp+0C8h+var_40], r12
0x14011ba7a  mov     [rsp+0C8h+var_48], r9
0x14011ba82  movzx   ecx, byte ptr [rdx+rax*4+82h]
0x14011ba8a  lea     rax, aLbads; "LBADS"
0x14011ba91  mov     [rsp+0C8h+var_50], r12
0x14011ba96  mov     [rsp+0C8h+var_58], r9
0x14011ba9b  mov     [rsp+0C8h+var_60], r12
0x14011baa0  mov     [rsp+0C8h+var_68], r9
0x14011baa5  mov     [rsp+0C8h+var_70], r12
0x14011baaa  mov     [rsp+0C8h+var_78], r9
0x14011baaf  mov     [rsp+0C8h+var_80], r12
0x14011bab4  mov     [rsp+0C8h+var_88], r9
0x14011bab9  lea     r9, aInactiveNamesp; "Inactive namespace"
0x14011bac0  mov     [rsp+0C8h+var_90], rcx
0x14011bac5  mov     rcx, rbx
0x14011bac8  mov     [rsp+0C8h+DeviceObject], rax
0x14011bacd  mov     rax, [rdx]
0x14011bad0  mov     edx, ebp
0x14011bad2  mov     qword ptr [rsp+0C8h+Exclusive], rax
0x14011bad7  lea     rax, aNsze; "NSZE"
0x14011bade  mov     qword ptr [rsp+0C8h+DeviceCharacteristics], rax
0x14011bae3  call    StorEtwNvmeNamespaceEvent
0x14011bae8  mov     edi, 0C00000BBh
0x14011baed  jmp     loc_14011BC1C
0x14011baf2  cmp     [rsi+270h], r12
0x14011baf9  jz      short loc_14011BB0C
0x14011bafb  movzx   eax, word ptr [rdx+64h]
0x14011baff  cmp     ax, [rsi+26Ah]
0x14011bb06  ja      short loc_14011BB0C
0x14011bb08  mov     [rbx+3Eh], ax
0x14011bb0c  cmp     [rbx+3Ch], r12b
0x14011bb10  jnz     short loc_14011BB1A
0x14011bb12  mov     rcx, rbx
0x14011bb15  call    NvmeNamespaceComputeBlockInfo
0x14011bb1a  mov     rcx, rbx
0x14011bb1d  call    NvmeNamespaceInitializeIoTracking
0x14011bb22  mov     edi, eax
0x14011bb24  test    eax, eax
0x14011bb26  js      loc_14011BC1C
0x14011bb2c  mov     r9, [rbx+8]
0x14011bb30  mov     edx, 918h
0x14011bb35  mov     ecx, 48h ; 'H'
0x14011bb3a  mov     r8d, 65546152h
0x14011bb40  call    RaidAllocatePool
0x14011bb45  mov     [rbx+270h], rax
0x14011bb4c  test    rax, rax
0x14011bb4f  jz      loc_14011BC17
0x14011bb55  mov     rcx, rbx
0x14011bb58  call    NvmeNamespacePowerInitialize
0x14011bb5d  mov     edi, eax
0x14011bb5f  test    eax, eax
0x14011bb61  js      loc_14011BC1C
0x14011bb67  mov     rcx, rbx
0x14011bb6a  call    NvmeNamespaceCreateErrorRecoveryContext
0x14011bb6f  mov     edi, eax
0x14011bb71  test    eax, eax
0x14011bb73  js      loc_14011BC1C
0x14011bb79  mov     rax, [rbx+10h]
0x14011bb7d  test    byte ptr [rax+88h], 2
0x14011bb84  jnz     loc_14011BC0F
0x14011bb8a  lea     rcx, [rbx+230h]; SpinLock
0x14011bb91  call    cs:__imp_KeInitializeSpinLock
0x14011bb98  nop     dword ptr [rax+rax+00h]
0x14011bb9d  lea     rax, [rbx+240h]
0x14011bba4  mov     [rax+8], rax
0x14011bba8  mov     [rax], rax
0x14011bbab  lea     rax, [rbx+258h]
0x14011bbb2  mov     [rax+8], rax
0x14011bbb6  mov     [rax], rax
0x14011bbb9  mov     rcx, [rbx+10h]
0x14011bbbd  call    NvmeControllerAllocateExtendedCommand
0x14011bbc2  mov     [rbx+220h], rax
0x14011bbc9  mov     rdx, rax
0x14011bbcc  test    rax, rax
0x14011bbcf  jz      short loc_14011BC17
0x14011bbd1  mov     rax, [rbx+10h]
0x14011bbd5  mov     rcx, [rax+80h]
0x14011bbdc  mov     eax, [rcx+454h]
0x14011bbe2  lea     ecx, [rax+rax*2]
0x14011bbe5  mov     eax, 0Ah
0x14011bbea  cmp     ecx, eax
0x14011bbec  cmova   eax, ecx
0x14011bbef  mov     [rdx+44h], ax
0x14011bbf3  mov     rcx, [rbx+8]; DeviceObject
0x14011bbf7  call    cs:__imp_IoAllocateWorkItem
0x14011bbfe  nop     dword ptr [rax+rax+00h]
0x14011bc03  mov     [rbx+228h], rax
0x14011bc0a  test    rax, rax
0x14011bc0d  jz      short loc_14011BC17
0x14011bc0f  mov     [r15], rbx
0x14011bc12  jmp     loc_14011BD09
0x14011bc17  mov     edi, 0C000009Ah
0x14011bc1c  test    rbx, rbx
0x14011bc1f  jz      loc_14011BCF0
0x14011bc25  mov     rcx, [rbx+228h]; IoWorkItem
0x14011bc2c  test    rcx, rcx
0x14011bc2f  jz      short loc_14011BC44
0x14011bc31  call    cs:__imp_IoFreeWorkItem
0x14011bc38  nop     dword ptr [rax+rax+00h]
0x14011bc3d  mov     [rbx+228h], r12
0x14011bc44  mov     rdx, [rbx+220h]
0x14011bc4b  test    rdx, rdx
0x14011bc4e  jz      short loc_14011BC60
0x14011bc50  mov     rcx, [rbx+10h]
0x14011bc54  call    NvmeControllerFreeExtendedCommand
0x14011bc59  mov     [rbx+220h], r12
0x14011bc60  mov     rcx, rbx
0x14011bc63  call    NvmeNamespaceDeleteErrorRecoveryContext
0x14011bc68  mov     rcx, rbx
0x14011bc6b  call    NvmeNamespaceUninitializeIoTracking
0x14011bc70  mov     rcx, rbx
0x14011bc73  call    NvmeNamespacePowerUninitialize
0x14011bc78  mov     rcx, rbx
0x14011bc7b  call    NvmeNamespaceTelemetryDelete
0x14011bc80  mov     rcx, [rbx+0B8h]; P
0x14011bc87  mov     esi, 52436152h
0x14011bc8c  test    rcx, rcx
0x14011bc8f  jz      short loc_14011BCA6
0x14011bc91  mov     edx, esi; Tag
0x14011bc93  call    cs:__imp_ExFreePoolWithTag
0x14011bc9a  nop     dword ptr [rax+rax+00h]
0x14011bc9f  mov     [rbx+0B8h], r12
0x14011bca6  mov     rcx, [rbx+0B0h]; P
0x14011bcad  test    rcx, rcx
0x14011bcb0  jz      short loc_14011BCC7
0x14011bcb2  mov     edx, esi; Tag
0x14011bcb4  call    cs:__imp_ExFreePoolWithTag
0x14011bcbb  nop     dword ptr [rax+rax+00h]
0x14011bcc0  mov     [rbx+0B0h], r12
  ... truncated ...
```
