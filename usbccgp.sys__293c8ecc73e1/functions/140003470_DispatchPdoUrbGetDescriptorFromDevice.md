# DispatchPdoUrbGetDescriptorFromDevice

- ea: `0x140003470`
- end: `0x140003875`
- name: `DispatchPdoUrbGetDescriptorFromDevice`
- size: `1029`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140002ad0`

## callees

- `0x140003388`
- `0x140003470`
- `0x14000387c`
- `0x1400083c8`
- `0x1400088b4`
- `0x14000b4bc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000356c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003622`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000356c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003622`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003599`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003599`
- `ntoskrnl!KeSetEvent` at `0x14000364f`
- `ntoskrnl!KeSetEvent` at `0x14000364f`
- `ntoskrnl!IofCallDriver` at `0x1400034f3`
- `ntoskrnl!IofCallDriver` at `0x1400034f3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000357d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003633`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003864`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000357d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003633`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003864`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000351d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400035c0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000351d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400035c0`

## pseudocode

```c
__int64 __fastcall DispatchPdoUrbGetDescriptorFromDevice(__int64 a1, IRP *a2)
{
  __int64 v3; // rdi
  _IO_SECURITY_CONTEXT *SecurityContext; // rbp
  int v6; // edx
  signed __int32 v7; // ebx
  __int64 v8; // rbp
  struct _DEVICE_OBJECT *v9; // rcx
  unsigned int v10; // r14d
  _QWORD *i; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx
  _QWORD *j; // rax
  signed __int32 v16; // ebx
  _QWORD *v17; // r9
  _QWORD *v18; // r8
  __int64 v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-58h] BYREF

  v3 = *(_QWORD *)(a1 + 232);
  SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  v6 = BYTE3(SecurityContext[5].AccessState);
  if ( v6 == 1 )
  {
    v7 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_q(
        *(_QWORD *)(v3 + 1368),
        v6,
        1,
        27,
        (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids,
        *(_QWORD *)(a1 + 224));
    }
    if ( HIDWORD(SecurityContext[1].AccessState) < 0x12 )
    {
      v21 = 0x80000000;
      v10 = -1073741306;
    }
    else
    {
      v20 = *(_QWORD *)&SecurityContext[1].DesiredAccess;
      *(_OWORD *)v20 = *(_OWORD *)(a1 + 256);
      *(_WORD *)(v20 + 16) = *(_WORD *)(a1 + 272);
      v21 = 0;
      v10 = 0;
    }
    HIDWORD(SecurityContext[1].AccessState) = 18;
    HIDWORD(SecurityContext->SecurityQos) = v21;
LABEL_25:
    UsbcCompleteIrp(v3, v10, a2);
    goto LABEL_13;
  }
  if ( BYTE3(SecurityContext[5].AccessState) == 2 )
  {
    v7 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_q(
        *(_QWORD *)(v3 + 1368),
        v6,
        1,
        28,
        (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids,
        *(_QWORD *)(a1 + 224));
    }
    v10 = BuildFunctionConfigurationDescriptor(
            a1,
            *(_QWORD *)&SecurityContext[1].DesiredAccess,
            HIDWORD(SecurityContext[1].AccessState),
            (char *)&SecurityContext[1].AccessState + 4);
    if ( v10 != 0x80000000 )
    {
      if ( v10 == -1073741811 )
      {
        HIDWORD(SecurityContext->SecurityQos) = -2147482880;
        UsbcCompleteIrp(v3, -1073741811, a2);
        goto LABEL_13;
      }
      if ( v10 )
      {
        v22 = 0x40000000;
        if ( v10 != 259 )
          v22 = 0x80000000;
        HIDWORD(SecurityContext->SecurityQos) = v22;
      }
      else
      {
        HIDWORD(SecurityContext->SecurityQos) = 0;
      }
    }
    goto LABEL_25;
  }
  v7 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_qD(
      *(_QWORD *)(v3 + 1368),
      v6,
      1,
      29,
      (__int64)WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids,
      *(_QWORD *)(a1 + 224),
      BYTE3(SecurityContext[5].AccessState));
  }
  v8 = *(_QWORD *)(a1 + 232);
  v9 = *(struct _DEVICE_OBJECT **)(v8 + 40);
  ++a2->CurrentLocation;
  ++a2->Tail.Overlay.CurrentStackLocation;
  v10 = IofCallDriver(v9, a2);
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v8 + 248), &LockHandle);
  for ( i = *(_QWORD **)(v8 + 232); i != (_QWORD *)(v8 + 232); i = (_QWORD *)*i )
  {
    v12 = (_QWORD *)*i;
    if ( (IRP *)i[3] == a2 )
    {
      if ( (_QWORD *)v12[1] != i )
        goto LABEL_41;
      v13 = (_QWORD *)i[1];
      if ( (_QWORD *)*v13 != i )
        goto LABEL_41;
      *v13 = v12;
      v12[1] = v13;
      ExFreePoolWithTag(i - 1, 0x43627355u);
      break;
    }
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v8 + 200), a2, 0x20u);
LABEL_13:
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 256), &LockHandle);
  v14 = (_QWORD *)(v3 + 264);
  for ( j = *(_QWORD **)(v3 + 264); j != v14; j = (_QWORD *)*j )
  {
    if ( (IRP *)j[3] == a2 )
    {
      v16 = _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF);
      v17 = (_QWORD *)*j;
      v7 = v16 - 1;
      if ( *(_QWORD **)(*j + 8LL) == j )
      {
        v18 = (_QWORD *)j[1];
        if ( (_QWORD *)*v18 == j )
        {
          *v18 = v17;
          v17[1] = v18;
          ExFreePoolWithTag(j - 1, 0x43627355u);
LABEL_19:
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( !v7 )
            KeSetEvent((PRKEVENT)(v3 + 288), 0, 0);
          return v10;
        }
      }
LABEL_41:
      __fastfail(3u);
    }
  }
  if ( *(_BYTE *)(v3 + 1376) == 1 )
  {
    v7 = _InterlockedDecrement((volatile signed __int32 *)(v3 + 280));
    goto LABEL_19;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_19;
  LOBYTE(v14) = 3;
  WPP_RECORDER_SF_(g_RecorderLog, (_DWORD)v14, 8, 59, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return v10;
}

```

## disassembly

```asm
0x140003470  push    rbx
0x140003472  push    rbp
0x140003473  push    rsi
0x140003474  push    rdi
0x140003475  push    r14
0x140003477  push    r15
0x140003479  sub     rsp, 68h
0x14000347d  mov     rax, [rdx+0B8h]
0x140003484  mov     rsi, rdx
0x140003487  mov     rdi, [rcx+0E8h]
0x14000348e  mov     r14, rcx
0x140003491  mov     rbp, [rax+8]
0x140003495  movzx   edx, byte ptr [rbp+83h]
0x14000349c  mov     r8d, edx
0x14000349f  sub     r8d, 1
0x1400034a3  jz      loc_1400036CD
0x1400034a9  cmp     r8d, 1
0x1400034ad  jz      loc_14000366C
0x1400034b3  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400034ba  mov     ebx, 1
0x1400034bf  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400034c6  jz      short loc_1400034DA
0x1400034c8  mov     rax, cs:WPP_GLOBAL_Control
0x1400034cf  cmp     word ptr [rax+48h], 0
0x1400034d4  jnz     loc_1400037B9
0x1400034da  mov     rbp, [r14+0E8h]
0x1400034e1  mov     rdx, rsi; Irp
0x1400034e4  mov     rcx, [rbp+28h]; DeviceObject
0x1400034e8  inc     byte ptr [rsi+43h]
0x1400034eb  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x1400034f3  call    cs:__imp_IofCallDriver
0x1400034fa  nop     dword ptr [rax+rax+00h]
0x1400034ff  xorps   xmm0, xmm0
0x140003502  lea     rcx, [rbp+0F8h]; SpinLock
0x140003509  mov     r14d, eax
0x14000350c  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x140003511  xor     eax, eax
0x140003513  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x140003518  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x14000351d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003524  nop     dword ptr [rax+rax+00h]
0x140003529  lea     rdx, [rbp+0E8h]
0x140003530  mov     rax, [rdx]
0x140003533  cmp     rax, rdx
0x140003536  jz      short loc_140003578
0x140003538  mov     rcx, [rax]
0x14000353b  cmp     [rax+18h], rsi
0x14000353f  jnz     loc_1400036BD
0x140003545  cmp     [rcx+8], rax
0x140003549  jnz     loc_140003808
0x14000354f  mov     rdx, [rax+8]
0x140003553  cmp     [rdx], rax
0x140003556  jnz     loc_140003808
0x14000355c  mov     [rdx], rcx
0x14000355f  mov     [rcx+8], rdx
0x140003563  mov     edx, 43627355h; Tag
0x140003568  lea     rcx, [rax-8]; P
0x14000356c  call    cs:__imp_ExFreePoolWithTag
0x140003573  nop     dword ptr [rax+rax+00h]
0x140003578  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x14000357d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003584  nop     dword ptr [rax+rax+00h]
0x140003589  lea     rcx, [rbp+0C8h]; RemoveLock
0x140003590  mov     r8d, 20h ; ' '; RemlockSize
0x140003596  mov     rdx, rsi; Tag
0x140003599  call    cs:__imp_IoReleaseRemoveLockEx
0x1400035a0  nop     dword ptr [rax+rax+00h]
0x1400035a5  xorps   xmm0, xmm0
0x1400035a8  lea     rcx, [rdi+100h]; SpinLock
0x1400035af  xor     eax, eax
0x1400035b1  lea     rdx, [rsp+98h+LockHandle]; LockHandle
0x1400035b6  movups  xmmword ptr [rsp+98h+LockHandle.LockQueue.Next], xmm0
0x1400035bb  mov     qword ptr [rsp+98h+LockHandle.OldIrql], rax
0x1400035c0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400035c7  nop     dword ptr [rax+rax+00h]
0x1400035cc  lea     rdx, [rdi+108h]
0x1400035d3  mov     rax, [rdx]
0x1400035d6  cmp     rax, rdx
0x1400035d9  jz      loc_14000380F
0x1400035df  cmp     [rax+18h], rsi
0x1400035e3  lea     rcx, [rax-8]; P
0x1400035e7  jnz     loc_1400036C5
0x1400035ed  mov     ebx, 0FFFFFFFFh
0x1400035f2  lock xadd [rdi+118h], ebx
0x1400035fa  mov     r9, [rax]
0x1400035fd  dec     ebx
0x1400035ff  cmp     [r9+8], rax
0x140003603  jnz     loc_140003808
0x140003609  mov     r8, [rax+8]
0x14000360d  cmp     [r8], rax
0x140003610  jnz     loc_140003808
0x140003616  mov     [r8], r9
0x140003619  mov     edx, 43627355h; Tag
0x14000361e  mov     [r9+8], r8
0x140003622  call    cs:__imp_ExFreePoolWithTag
0x140003629  nop     dword ptr [rax+rax+00h]
0x14000362e  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140003633  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000363a  nop     dword ptr [rax+rax+00h]
0x14000363f  test    ebx, ebx
0x140003641  jnz     short loc_14000365B
0x140003643  lea     rcx, [rdi+120h]; Event
0x14000364a  xor     r8d, r8d; Wait
0x14000364d  xor     edx, edx; Increment
0x14000364f  call    cs:__imp_KeSetEvent
0x140003656  nop     dword ptr [rax+rax+00h]
0x14000365b  mov     eax, r14d
0x14000365e  add     rsp, 68h
0x140003662  pop     r15
0x140003664  pop     r14
0x140003666  pop     rdi
0x140003667  pop     rsi
0x140003668  pop     rbp
0x140003669  pop     rbx
0x14000366a  retn
0x14000366c  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140003673  mov     ebx, 1
0x140003678  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000367f  jnz     loc_140003776
0x140003685  mov     r8d, [rbp+24h]
0x140003689  lea     r9, [rbp+24h]
0x14000368d  mov     rdx, [rbp+28h]
0x140003691  mov     rcx, r14
0x140003694  call    BuildFunctionConfigurationDescriptor
0x140003699  mov     r14d, eax
0x14000369c  mov     eax, 80000000h
0x1400036a1  cmp     r14d, eax
0x1400036a4  jnz     loc_140003746
0x1400036aa  mov     r8, rsi
0x1400036ad  mov     edx, r14d
0x1400036b0  mov     rcx, rdi
0x1400036b3  call    UsbcCompleteIrp
0x1400036b8  jmp     loc_1400035A5
0x1400036bd  mov     rax, rcx
0x1400036c0  jmp     loc_140003533
0x1400036c5  mov     rax, [rax]
0x1400036c8  jmp     loc_1400035D6
0x1400036cd  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400036d4  mov     ebx, 1
0x1400036d9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400036e0  jz      short loc_140003711
0x1400036e2  mov     rax, [rcx+0E0h]
0x1400036e9  mov     r9d, 1Bh
0x1400036ef  mov     rcx, [rdi+558h]
0x1400036f6  mov     r8d, ebx
0x1400036f9  mov     [rsp+98h+var_70], rax
0x1400036fe  mov     dl, 4
0x140003700  lea     rax, WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids
0x140003707  mov     [rsp+98h+var_78], rax
0x14000370c  call    WPP_RECORDER_SF_q
0x140003711  cmp     dword ptr [rbp+24h], 12h
0x140003715  jb      short loc_140003769
0x140003717  movups  xmm0, xmmword ptr [r14+100h]
0x14000371f  mov     rcx, [rbp+28h]
0x140003723  movups  xmmword ptr [rcx], xmm0
0x140003726  movzx   eax, word ptr [r14+110h]
0x14000372e  mov     [rcx+10h], ax
0x140003732  xor     eax, eax
0x140003734  mov     r14d, eax
0x140003737  mov     dword ptr [rbp+24h], 12h
0x14000373e  mov     [rbp+4], eax
0x140003741  jmp     loc_1400036AA
0x140003746  cmp     r14d, 0C000000Dh
0x14000374d  jnz     short loc_1400037AA
0x14000374f  mov     r8, rsi
0x140003752  mov     dword ptr [rbp+4], 80000300h
0x140003759  mov     edx, r14d
0x14000375c  mov     rcx, rdi
0x14000375f  call    UsbcCompleteIrp
0x140003764  jmp     loc_1400035A5
0x140003769  mov     eax, 80000000h
0x14000376e  mov     r14d, 0C0000206h
0x140003774  jmp     short loc_140003737
0x140003776  mov     rax, [rcx+0E0h]
0x14000377d  mov     r9d, 1Ch
0x140003783  mov     rcx, [rdi+558h]
0x14000378a  mov     r8d, ebx
0x14000378d  mov     [rsp+98h+var_70], rax
0x140003792  mov     dl, 4
0x140003794  lea     rax, WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids
0x14000379b  mov     [rsp+98h+var_78], rax
0x1400037a0  call    WPP_RECORDER_SF_q
0x1400037a5  jmp     loc_140003685
0x1400037aa  test    r14d, r14d
0x1400037ad  jnz     short loc_1400037F1
0x1400037af  xor     eax, eax
0x1400037b1  mov     [rbp+4], eax
0x1400037b4  jmp     loc_1400036AA
0x1400037b9  mov     rax, [rcx+0E0h]
0x1400037c0  mov     r9d, 1Dh
0x1400037c6  mov     rcx, [rdi+558h]
0x1400037cd  mov     r8d, ebx
0x1400037d0  mov     [rsp+98h+var_68], edx
0x1400037d4  mov     dl, 5
0x1400037d6  mov     [rsp+98h+var_70], rax
0x1400037db  lea     rax, WPP_fc1b814fd1aa3eaffd95e56bc3961d1e_Traceguids
0x1400037e2  mov     [rsp+98h+var_78], rax
0x1400037e7  call    WPP_RECORDER_SF_qD
0x1400037ec  jmp     loc_1400034DA
0x1400037f1  cmp     r14d, 103h
0x1400037f8  mov     ecx, 40000000h
0x1400037fd  cmovnz  ecx, eax
0x140003800  mov     [rbp+4], ecx
0x140003803  jmp     loc_1400036AA
0x140003808  mov     ecx, 3
0x14000380d  int     29h; Win8: RtlFailFast(ecx)
0x14000380f  cmp     byte ptr [rdi+560h], 1
0x140003816  jnz     short loc_14000382C
0x140003818  mov     ebx, 0FFFFFFFFh
0x14000381d  lock xadd [rdi+118h], ebx
0x140003825  dec     ebx
0x140003827  jmp     loc_14000362E
0x14000382c  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140003833  jz      loc_14000362E
0x140003839  mov     rcx, cs:g_RecorderLog
0x140003840  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140003847  mov     r9d, 3Bh ; ';'
0x14000384d  mov     [rsp+98h+var_78], rax
0x140003852  mov     r8d, 8
0x140003858  mov     dl, 3
0x14000385a  call    WPP_RECORDER_SF_
0x14000385f  lea     rcx, [rsp+98h+LockHandle]; LockHandle
0x140003864  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000386b  nop     dword ptr [rax+rax+00h]
0x140003870  jmp     loc_14000365B
```
