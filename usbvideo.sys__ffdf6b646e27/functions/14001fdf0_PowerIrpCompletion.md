# PowerIrpCompletion

- ea: `0x14001fdf0`
- end: `0x1400202ae`
- name: `PowerIrpCompletion`
- size: `1214`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140005308`
- `0x1400054c0`
- `0x1400199e8`
- `0x14001ab4c`
- `0x14001b15c`
- `0x14001d20c`
- `0x14001fdf0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140020001`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400200c8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002019f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140020001`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400200c8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002019f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001feaa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001feaa`
- `ntoskrnl!IoQueueWorkItem` at `0x14001ffc8`
- `ntoskrnl!IoQueueWorkItem` at `0x140020178`
- `ntoskrnl!IoQueueWorkItem` at `0x14001ffc8`
- `ntoskrnl!IoQueueWorkItem` at `0x140020178`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001ff93`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400201c2`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001ff93`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400201c2`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001ff46`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001ff46`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ffe1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ffe1`
- `ntoskrnl!IoInitializeWorkItem` at `0x140020158`
- `ntoskrnl!IoInitializeWorkItem` at `0x140020158`

## pseudocode

```c
void __fastcall PowerIrpCompletion(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        char *Context,
        PIO_STATUS_BLOCK IoStatus)
{
  _DWORD *v5; // rsi
  KIRQL v8; // r12
  __int64 v9; // rcx
  __int64 v10; // r8
  PIO_WORKITEM WorkItem; // rax
  __int64 v12; // r8
  IO_WORKITEM_ROUTINE *v13; // rdx
  struct _IO_WORKITEM *v14; // rcx
  __int64 v15; // r8
  PDEVICE_OBJECT v16; // rcx
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rcx
  struct _IO_WORKITEM *v22; // rdx
  __int64 v23; // rcx
  PIO_WORKITEM v24; // rbx

  v5 = Context + 224;
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
    ((void (__fastcall *)(_DWORD, _BYTE, _DWORD, _DWORD, char, char, char, char))McTemplateK0pqqqq_EtwWriteTransfer)(
      (_DWORD)DeviceObject,
      MinorFunction,
      (POWER_STATE)PowerState.SystemState,
      (_DWORD)Context,
      PowerState.SystemState,
      PowerState.SystemState,
      *v5,
      IoStatus->Status);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 146, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, Context);
      v5 = Context + 224;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        147,
        WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
        Context,
        IoStatus->Status);
  }
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 27);
  if ( PowerState.SystemState != PowerSystemWorking )
  {
    if ( *((_DWORD *)Context + 56) == 2 )
    {
      *((_DWORD *)Context + 56) = 3;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 148, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, Context);
    }
    goto LABEL_24;
  }
  if ( IoStatus->Status >= 0 )
  {
    if ( IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)Context + 24, IdleDetectWorkItem, File, 1u, 0x20u) < 0 )
      goto LABEL_24;
    if ( *v5 == 3 )
    {
      if ( !Context[2] && !Context[1] )
      {
        if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 4) != 0 )
          McTemplateK0p_EtwWriteTransfer(v9, USBVideo_PowerIrp_PowerUpWithNoOp, v10, 0);
        WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(*((_QWORD *)Context + 3) + 24LL));
        if ( WorkItem )
        {
          *((_QWORD *)Context + 30) = WorkItem;
          v13 = IdleDetectWorkItem;
          *((_DWORD *)Context + 56) = 1;
          v14 = WorkItem;
LABEL_23:
          IoQueueWorkItem(v14, v13, DelayedWorkQueue, Context);
          goto LABEL_24;
        }
        *((_DWORD *)Context + 56) = 0;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          goto LABEL_34;
        v18 = 149;
        goto LABEL_33;
      }
      *v5 = 0;
      if ( !(unsigned int)Feature_Servicing_UvcPerfIrpCache__private_IsEnabledNoReportingNoInline() )
      {
        if ( *((_QWORD *)Context + 31) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 152, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, Context);
          goto LABEL_36;
        }
        v24 = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(*((_QWORD *)Context + 3) + 24LL));
        if ( v24 )
        {
          if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
            McTemplateK0p_EtwWriteTransfer(v23, USBVideo_PowerIrp_CheckingPLFRegistry, v12, 0);
          *((_QWORD *)Context + 31) = v24;
          v13 = PassiveWakeup;
          v14 = v24;
          goto LABEL_23;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        {
LABEL_34:
          if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 4) != 0 )
            McTemplateK0p_EtwWriteTransfer(v17, USBVideo_PowerIrp_AllocationFailure, v12, 0);
LABEL_36:
          FilterCreateQueue_CompleteQueue(Context, 0);
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)Context + 24, IdleDetectWorkItem, 0x20u);
          goto LABEL_24;
        }
        v18 = 151;
LABEL_33:
        WPP_SF_q(v17->AttachedDevice, v18, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, Context);
        goto LABEL_34;
      }
      if ( !Context[353] )
      {
        if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
          McTemplateK0p_EtwWriteTransfer(v19, USBVideo_PowerIrp_CheckingPLFRegistry, v20, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 150, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, Context);
        v21 = *((_QWORD *)Context + 3);
        v22 = (struct _IO_WORKITEM *)*((_QWORD *)Context + 31);
        Context[353] = 1;
        IoInitializeWorkItem(*(PVOID *)(v21 + 24), v22);
        IoQueueWorkItem(*((PIO_WORKITEM *)Context + 31), PassiveWakeup, CriticalWorkQueue, Context);
        goto LABEL_24;
      }
      FilterCreateQueue_CompleteQueue(Context, 0);
    }
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)Context + 24, IdleDetectWorkItem, 0x20u);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 153, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, Context);
  FilterCreateQueue_CompleteQueue(Context, (unsigned int)IoStatus->Status);
LABEL_24:
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 27, v8);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)Context + 24, PowerIrpCompletion, 0x20u);
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 154, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, Context);
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(v16, USBVideo_PowerIrpCompletion_Stop, v15, 0);
}

```

## disassembly

```asm
0x14001fdf0  push    rbx
0x14001fdf2  push    rbp
0x14001fdf3  push    rsi
0x14001fdf4  push    rdi
0x14001fdf5  push    r12
0x14001fdf7  push    r14
0x14001fdf9  push    r15
0x14001fdfb  sub     rsp, 40h
0x14001fdff  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x14001fe06  lea     rsi, [r9+0E0h]
0x14001fe0d  mov     r14, [rsp+78h+IoStatus]
0x14001fe15  mov     rdi, r9
0x14001fe18  mov     ebx, r8d
0x14001fe1b  jz      short loc_14001FE37
0x14001fe1d  mov     eax, [r14]
0x14001fe20  mov     [rsp+78h+var_40], eax
0x14001fe24  mov     eax, [rsi]
0x14001fe26  mov     [rsp+78h+var_48], eax
0x14001fe2a  mov     [rsp+78h+var_50], ebx
0x14001fe2e  mov     [rsp+78h+RemlockSize], ebx
0x14001fe32  call    McTemplateK0pqqqq_EtwWriteTransfer
0x14001fe37  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fe3e  lea     r15, WPP_GLOBAL_Control
0x14001fe45  cmp     rcx, r15
0x14001fe48  jz      short loc_14001FEA0
0x14001fe4a  cmp     byte ptr [rcx+29h], 5
0x14001fe4e  jb      short loc_14001FE6F
0x14001fe50  mov     rcx, [rcx+18h]
0x14001fe54  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14001fe5b  mov     edx, 92h
0x14001fe60  mov     r9, rdi
0x14001fe63  call    WPP_SF_q
0x14001fe68  lea     rsi, [rdi+0E0h]
0x14001fe6f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fe76  cmp     rcx, r15
0x14001fe79  jz      short loc_14001FEA0
0x14001fe7b  cmp     byte ptr [rcx+29h], 4
0x14001fe7f  jb      short loc_14001FEA0
0x14001fe81  mov     eax, [r14]
0x14001fe84  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14001fe8b  mov     rcx, [rcx+18h]
0x14001fe8f  mov     edx, 93h
0x14001fe94  mov     r9, rdi
0x14001fe97  mov     [rsp+78h+RemlockSize], eax
0x14001fe9b  call    WPP_SF_qD
0x14001fea0  lea     r15, [rdi+0D8h]
0x14001fea7  mov     rcx, r15; SpinLock
0x14001feaa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001feb1  nop     dword ptr [rax+rax+00h]
0x14001feb6  mov     r12b, al
0x14001feb9  cmp     ebx, 1
0x14001febc  jz      short loc_14001FF13
0x14001febe  cmp     dword ptr [rdi+0E0h], 2
0x14001fec5  jnz     loc_14001FFD4
0x14001fecb  mov     dword ptr [rdi+0E0h], 3
0x14001fed5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fedc  lea     rbx, WPP_GLOBAL_Control
0x14001fee3  cmp     rcx, rbx
0x14001fee6  jz      loc_14001FFDB
0x14001feec  cmp     byte ptr [rcx+29h], 4
0x14001fef0  jb      loc_14001FFDB
0x14001fef6  mov     rcx, [rcx+18h]
0x14001fefa  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14001ff01  mov     edx, 94h
0x14001ff06  mov     r9, rdi
0x14001ff09  call    WPP_SF_q
0x14001ff0e  jmp     loc_14001FFDB
0x14001ff13  cmp     dword ptr [r14], 0
0x14001ff17  jl      loc_14002026D
0x14001ff1d  lea     rbp, [rdi+300h]
0x14001ff24  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x14001ff2c  lea     r14, IdleDetectWorkItem
0x14001ff33  mov     rcx, rbp; RemoveLock
0x14001ff36  mov     rdx, r14; Tag
0x14001ff39  lea     r8, File; File
0x14001ff40  mov     r9d, 1; Line
0x14001ff46  call    cs:__imp_IoAcquireRemoveLockEx
0x14001ff4d  nop     dword ptr [rax+rax+00h]
0x14001ff52  test    eax, eax
0x14001ff54  js      short loc_14001FFD4
0x14001ff56  cmp     dword ptr [rsi], 3
0x14001ff59  jnz     loc_140020193
0x14001ff5f  cmp     byte ptr [rdi+2], 0
0x14001ff63  jnz     loc_1400200D9
0x14001ff69  cmp     byte ptr [rdi+1], 0
0x14001ff6d  jnz     loc_1400200D9
0x14001ff73  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 4
0x14001ff7a  jz      short loc_14001FF8B
0x14001ff7c  xor     r9d, r9d
0x14001ff7f  lea     rdx, USBVideo_PowerIrp_PowerUpWithNoOp
0x14001ff86  call    McTemplateK0p_EtwWriteTransfer
0x14001ff8b  mov     rcx, [rdi+18h]
0x14001ff8f  mov     rcx, [rcx+18h]; DeviceObject
0x14001ff93  call    cs:__imp_IoAllocateWorkItem
0x14001ff9a  nop     dword ptr [rax+rax+00h]
0x14001ff9f  test    rax, rax
0x14001ffa2  jz      loc_14002005F
0x14001ffa8  mov     [rdi+0F0h], rax
0x14001ffaf  mov     rdx, r14; WorkerRoutine
0x14001ffb2  mov     dword ptr [rdi+0E0h], 1
0x14001ffbc  mov     rcx, rax; IoWorkItem
0x14001ffbf  mov     r8d, 1; QueueType
0x14001ffc5  mov     r9, rdi; Context
0x14001ffc8  call    cs:__imp_IoQueueWorkItem
0x14001ffcf  nop     dword ptr [rax+rax+00h]
0x14001ffd4  lea     rbx, WPP_GLOBAL_Control
0x14001ffdb  mov     dl, r12b; NewIrql
0x14001ffde  mov     rcx, r15; SpinLock
0x14001ffe1  call    cs:__imp_KeReleaseSpinLock
0x14001ffe8  nop     dword ptr [rax+rax+00h]
0x14001ffed  lea     rcx, [rdi+300h]; RemoveLock
0x14001fff4  mov     r8d, 20h ; ' '; RemlockSize
0x14001fffa  lea     rdx, PowerIrpCompletion; Tag
0x140020001  call    cs:__imp_IoReleaseRemoveLockEx
0x140020008  nop     dword ptr [rax+rax+00h]
0x14002000d  mov     rcx, cs:WPP_GLOBAL_Control
0x140020014  cmp     rcx, rbx
0x140020017  jz      short loc_140020037
0x140020019  cmp     byte ptr [rcx+29h], 5
0x14002001d  jb      short loc_140020037
0x14002001f  mov     rcx, [rcx+18h]
0x140020023  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14002002a  mov     edx, 9Ah
0x14002002f  mov     r9, rdi
0x140020032  call    WPP_SF_q
0x140020037  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x14002003e  jz      short loc_14002004F
0x140020040  xor     r9d, r9d
0x140020043  lea     rdx, USBVideo_PowerIrpCompletion_Stop
0x14002004a  call    McTemplateK0p_EtwWriteTransfer
0x14002004f  add     rsp, 40h
0x140020053  pop     r15
0x140020055  pop     r14
0x140020057  pop     r12
0x140020059  pop     rdi
0x14002005a  pop     rsi
0x14002005b  pop     rbp
0x14002005c  pop     rbx
0x14002005d  retn
0x14002005f  mov     dword ptr [rdi+0E0h], 0
0x140020069  mov     rcx, cs:WPP_GLOBAL_Control
0x140020070  lea     rbx, WPP_GLOBAL_Control
0x140020077  cmp     rcx, rbx
0x14002007a  jz      short loc_14002009A
0x14002007c  cmp     byte ptr [rcx+29h], 3
0x140020080  jb      short loc_14002009A
0x140020082  mov     edx, 95h
0x140020087  mov     rcx, [rcx+18h]
0x14002008b  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020092  mov     r9, rdi
0x140020095  call    WPP_SF_q
0x14002009a  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 4
0x1400200a1  jz      short loc_1400200B2
0x1400200a3  xor     r9d, r9d
0x1400200a6  lea     rdx, USBVideo_PowerIrp_AllocationFailure
0x1400200ad  call    McTemplateK0p_EtwWriteTransfer
0x1400200b2  xor     edx, edx
0x1400200b4  mov     rcx, rdi
0x1400200b7  call    FilterCreateQueue_CompleteQueue
0x1400200bc  mov     r8d, 20h ; ' '; RemlockSize
0x1400200c2  mov     rdx, r14; Tag
0x1400200c5  mov     rcx, rbp; RemoveLock
0x1400200c8  call    cs:__imp_IoReleaseRemoveLockEx
0x1400200cf  nop     dword ptr [rax+rax+00h]
0x1400200d4  jmp     loc_14001FFDB
0x1400200d9  mov     dword ptr [rsi], 0
0x1400200df  call    Feature_Servicing_UvcPerfIrpCache__private_IsEnabledNoReportingNoInline
0x1400200e4  test    eax, eax
0x1400200e6  jz      loc_1400201B0
0x1400200ec  cmp     byte ptr [rdi+161h], 0
0x1400200f3  jnz     loc_140020189
0x1400200f9  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x140020100  jz      short loc_140020111
0x140020102  xor     r9d, r9d
0x140020105  lea     rdx, USBVideo_PowerIrp_CheckingPLFRegistry
0x14002010c  call    McTemplateK0p_EtwWriteTransfer
0x140020111  mov     rcx, cs:WPP_GLOBAL_Control
0x140020118  lea     rbx, WPP_GLOBAL_Control
0x14002011f  cmp     rcx, rbx
0x140020122  jz      short loc_140020142
0x140020124  cmp     byte ptr [rcx+29h], 4
0x140020128  jb      short loc_140020142
0x14002012a  mov     rcx, [rcx+18h]
0x14002012e  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020135  mov     edx, 96h
0x14002013a  mov     r9, rdi
0x14002013d  call    WPP_SF_q
0x140020142  mov     rcx, [rdi+18h]
0x140020146  mov     rdx, [rdi+0F8h]; IoWorkItem
0x14002014d  mov     byte ptr [rdi+161h], 1
0x140020154  mov     rcx, [rcx+18h]; IoObject
0x140020158  call    cs:__imp_IoInitializeWorkItem
0x14002015f  nop     dword ptr [rax+rax+00h]
0x140020164  mov     rcx, [rdi+0F8h]; IoWorkItem
0x14002016b  lea     rdx, PassiveWakeup; WorkerRoutine
0x140020172  mov     r9, rdi; Context
0x140020175  xor     r8d, r8d; QueueType
0x140020178  call    cs:__imp_IoQueueWorkItem
0x14002017f  nop     dword ptr [rax+rax+00h]
0x140020184  jmp     loc_14001FFDB
0x140020189  xor     edx, edx
0x14002018b  mov     rcx, rdi
0x14002018e  call    FilterCreateQueue_CompleteQueue
0x140020193  mov     r8d, 20h ; ' '; RemlockSize
0x140020199  mov     rdx, r14; Tag
0x14002019c  mov     rcx, rbp; RemoveLock
0x14002019f  call    cs:__imp_IoReleaseRemoveLockEx
0x1400201a6  nop     dword ptr [rax+rax+00h]
0x1400201ab  jmp     loc_14001FFD4
0x1400201b0  cmp     qword ptr [rdi+0F8h], 0
0x1400201b8  jnz     short loc_14002022F
0x1400201ba  mov     rcx, [rdi+18h]
0x1400201be  mov     rcx, [rcx+18h]; DeviceObject
0x1400201c2  call    cs:__imp_IoAllocateWorkItem
0x1400201c9  nop     dword ptr [rax+rax+00h]
0x1400201ce  mov     rbx, rax
0x1400201d1  test    rax, rax
0x1400201d4  jz      short loc_140020204
0x1400201d6  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x1400201dd  jz      short loc_1400201EE
0x1400201df  xor     r9d, r9d
0x1400201e2  lea     rdx, USBVideo_PowerIrp_CheckingPLFRegistry
0x1400201e9  call    McTemplateK0p_EtwWriteTransfer
0x1400201ee  mov     [rdi+0F8h], rbx
0x1400201f5  lea     rdx, PassiveWakeup
0x1400201fc  mov     rcx, rbx
0x1400201ff  jmp     loc_14001FFBF
0x140020204  mov     rcx, cs:WPP_GLOBAL_Control
0x14002020b  lea     rbx, WPP_GLOBAL_Control
0x140020212  cmp     rcx, rbx
0x140020215  jz      loc_14002009A
0x14002021b  cmp     byte ptr [rcx+29h], 3
0x14002021f  jb      loc_14002009A
0x140020225  mov     edx, 97h
0x14002022a  jmp     loc_140020087
0x14002022f  mov     rcx, cs:WPP_GLOBAL_Control
0x140020236  lea     rbx, WPP_GLOBAL_Control
0x14002023d  cmp     rcx, rbx
0x140020240  jz      loc_1400200B2
0x140020246  cmp     byte ptr [rcx+29h], 4
0x14002024a  jb      loc_1400200B2
0x140020250  mov     rcx, [rcx+18h]
0x140020254  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14002025b  mov     edx, 98h
0x140020260  mov     r9, rdi
0x140020263  call    WPP_SF_q
0x140020268  jmp     loc_1400200B2
0x14002026d  mov     rcx, cs:WPP_GLOBAL_Control
0x140020274  lea     rbx, WPP_GLOBAL_Control
0x14002027b  cmp     rcx, rbx
0x14002027e  jz      short loc_14002029E
0x140020280  cmp     byte ptr [rcx+29h], 3
0x140020284  jb      short loc_14002029E
0x140020286  mov     rcx, [rcx+18h]
0x14002028a  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020291  mov     edx, 99h
0x140020296  mov     r9, rdi
0x140020299  call    WPP_SF_q
0x14002029e  mov     edx, [r14]
0x1400202a1  mov     rcx, rdi
0x1400202a4  call    FilterCreateQueue_CompleteQueue
0x1400202a9  jmp     loc_14001FFDB
```
