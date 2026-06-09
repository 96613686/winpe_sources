# USBC_Dispatch

- ea: `0x140002200`
- end: `0x140002629`
- name: `USBC_Dispatch`
- size: `1065`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400018b0`
- `0x140002200`
- `0x140002630`
- `0x1400029d0`
- `0x140003388`
- `0x140003c28`
- `0x1400083c8`
- `0x140009450`
- `0x14000ba3c`
- `0x140028630`
- `0x14002c08c`
- `0x14002c8a0`
- `0x14002d418`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400022dd`
- `ntoskrnl!IofCompleteRequest` at `0x140002504`
- `ntoskrnl!IofCompleteRequest` at `0x1400022dd`
- `ntoskrnl!IofCompleteRequest` at `0x140002504`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000251c`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140002618`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000251c`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140002618`
- `ntoskrnl!KeSetEvent` at `0x14000248f`
- `ntoskrnl!KeSetEvent` at `0x14000248f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000238b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000238b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000234a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000234a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000229a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000229a`
- `ntoskrnl!ExAllocatePool2` at `0x140002313`
- `ntoskrnl!ExAllocatePool2` at `0x140002313`

## pseudocode

```c
__int64 __fastcall USBC_Dispatch(__int64 a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  char v3; // r13
  __int64 v4; // rsi
  int MinorFunction; // ecx
  int MajorFunction; // r15d
  __int64 v8; // r12
  __int64 v9; // rdi
  char v10; // r14
  int v11; // edx
  unsigned int v12; // ebx
  __int64 Pool2; // rax
  int v14; // edx
  __int64 v15; // r12
  _QWORD *v16; // rcx
  __int64 v17; // r13
  void *v18; // rcx
  char v20; // [rsp+28h] [rbp-80h]
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-68h] BYREF
  char v22; // [rsp+B0h] [rbp+8h]
  int v23; // [rsp+B8h] [rbp+10h]
  __int64 v24; // [rsp+C0h] [rbp+18h]
  __int64 v25; // [rsp+C8h] [rbp+20h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = a1;
  v4 = *(_QWORD *)(a1 + 64);
  MinorFunction = CurrentStackLocation->MinorFunction;
  MajorFunction = CurrentStackLocation->MajorFunction;
  v23 = MinorFunction;
  v22 = *(_BYTE *)(v4 + 4);
  if ( v22 )
  {
    v10 = 0;
    v24 = v4 + 8;
    v9 = 0;
    v8 = v4 + 8;
    goto LABEL_4;
  }
  v8 = *(_QWORD *)(v4 + 240);
  v24 = v8;
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 316));
  if ( *(_DWORD *)(v4 + 28) != 10 )
  {
    v9 = v4 + 8;
    v10 = 1;
LABEL_4:
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v8 + 200), a2, File, 1u, 0x20u) >= 0 )
    {
      Pool2 = ExAllocatePool2(64, 40, 1130525525);
      v25 = Pool2;
      if ( Pool2 )
      {
        *(_DWORD *)Pool2 = 1801678668;
        *(_DWORD *)(Pool2 + 24) = 1148219977;
        *(_QWORD *)(Pool2 + 32) = a2;
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v8 + 248), &LockHandle);
        v15 = v8 + 232;
        v16 = *(_QWORD **)(v15 + 8);
        if ( *v16 != v15 )
          __fastfail(3u);
        *(_QWORD *)(v25 + 16) = v16;
        *(_QWORD *)(v25 + 8) = v15;
        *v16 = v25 + 8;
        *(_QWORD *)(v15 + 8) = v25 + 8;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v14) = 5;
        v20 = v3;
        v17 = v24;
        WPP_RECORDER_SF_qDD(
          *(_QWORD *)(v24 + 1368),
          v14,
          9,
          11,
          (__int64)WPP_b8ba6c0bda43381ffdf12cf14fa10529_Traceguids,
          v20,
          MajorFunction,
          v23);
      }
      else
      {
        v17 = v24;
      }
      if ( MajorFunction )
      {
        switch ( MajorFunction )
        {
          case 15:
            v18 = (void *)(v4 + 8);
            if ( *(_BYTE *)(v4 + 4) )
              v12 = DispatchFdoInternalDeviceControl(v18, a2);
            else
              v12 = DispatchPdoInternalDeviceControl(v18, a2);
            break;
          case 2:
            if ( *(_BYTE *)(v4 + 4) )
            {
              v12 = UsbcForwardIrp(v4 + 8, *(_QWORD *)(v4 + 48), a2);
            }
            else
            {
              v12 = -1073741637;
              UsbcCompleteIrp(*(_QWORD *)(v4 + 240), 3221225659LL, a2);
            }
            break;
          case 14:
            v12 = USBC_DeviceControl(v4, a2);
            break;
          case 22:
            v12 = USBC_Power(v4, a2);
            break;
          case 23:
            v12 = USBC_SystemControl(v4, a2);
            break;
          case 27:
            v12 = USBC_PnP(v4, a2);
            break;
          default:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v14) = 2;
              WPP_RECORDER_SF_D(
                *(_QWORD *)(v17 + 1368),
                v14,
                9,
                12,
                (__int64)WPP_b8ba6c0bda43381ffdf12cf14fa10529_Traceguids,
                MajorFunction);
            }
            if ( v22 )
            {
              v12 = UsbcForwardIrp(v17, *(_QWORD *)(v17 + 40), a2);
            }
            else
            {
              v12 = -1073741637;
              UsbcCompleteIrp(v17, 3221225659LL, a2);
            }
            break;
        }
      }
      else
      {
        v12 = USBC_Create(v4, a2);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 4;
        WPP_RECORDER_SF_q(g_RecorderLog, v11, 1, 10, (__int64)WPP_b8ba6c0bda43381ffdf12cf14fa10529_Traceguids, (char)a2);
      }
      if ( MajorFunction == 22 && v23 )
        PoStartNextPowerIrp(a2);
      v12 = -1073741738;
      a2->IoStatus.Information = 0;
      a2->IoStatus.Status = -1073741738;
      IofCompleteRequest(a2, 0);
    }
    if ( v10 && _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 308), 0xFFFFFFFF) == 1 )
      KeSetEvent((PRKEVENT)(v9 + 312), 0, 0);
    return v12;
  }
  _InterlockedDecrement((volatile signed __int32 *)(v4 + 316));
  if ( MajorFunction == 22 && MinorFunction )
    PoStartNextPowerIrp(a2);
  v12 = -1073741738;
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741738;
  IofCompleteRequest(a2, 0);
  return v12;
}

```

## disassembly

```asm
0x140002200  push    rbx
0x140002202  push    rbp
0x140002203  push    rsi
0x140002204  push    rdi
0x140002205  push    r12
0x140002207  push    r13
0x140002209  push    r14
0x14000220b  push    r15
0x14000220d  sub     rsp, 68h
0x140002211  mov     rax, [rdx+0B8h]
0x140002218  mov     r13, rcx
0x14000221b  mov     rsi, [rcx+40h]
0x14000221f  mov     rbp, rdx
0x140002222  movzx   ecx, byte ptr [rax+1]
0x140002226  movzx   r15d, byte ptr [rax]
0x14000222a  lea     rbx, [rsi+8]
0x14000222e  movzx   eax, byte ptr [rsi+4]
0x140002232  mov     [rsp+0A8h+arg_8], ecx
0x140002239  mov     [rsp+0A8h+arg_0], al
0x140002240  test    al, al
0x140002242  jnz     loc_1400022EE
0x140002248  mov     r12, [rbx+0E8h]
0x14000224f  mov     [rsp+0A8h+arg_10], r12
0x140002257  lock inc dword ptr [rbx+134h]
0x14000225e  cmp     dword ptr [rbx+14h], 0Ah
0x140002262  jz      loc_1400024E2
0x140002268  mov     rdi, rbx
0x14000226b  mov     r14b, 1
0x14000226e  xorps   xmm0, xmm0
0x140002271  mov     [rsp+0A8h+RemlockSize], 20h ; ' '; RemlockSize
0x140002279  xor     eax, eax
0x14000227b  lea     rcx, [r12+0C8h]; RemoveLock
0x140002283  mov     r9d, 1; Line
0x140002289  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14000228e  lea     r8, File; File
0x140002295  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14000229a  call    cs:__imp_IoAcquireRemoveLockEx
0x1400022a1  nop     dword ptr [rax+rax+00h]
0x1400022a6  test    eax, eax
0x1400022a8  jns     short loc_140002303
0x1400022aa  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400022b1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400022b8  jnz     loc_1400025D7
0x1400022be  cmp     r15d, 16h
0x1400022c2  jz      loc_140002607
0x1400022c8  mov     ebx, 0C0000056h
0x1400022cd  mov     qword ptr [rbp+38h], 0
0x1400022d5  xor     edx, edx; PriorityBoost
0x1400022d7  mov     [rbp+30h], ebx
0x1400022da  mov     rcx, rbp; Irp
0x1400022dd  call    cs:__imp_IofCompleteRequest
0x1400022e4  nop     dword ptr [rax+rax+00h]
0x1400022e9  jmp     loc_1400023F9
0x1400022ee  xor     r14b, r14b
0x1400022f1  mov     [rsp+0A8h+arg_10], rbx
0x1400022f9  xor     edi, edi
0x1400022fb  mov     r12, rbx
0x1400022fe  jmp     loc_14000226E
0x140002303  mov     edx, 28h ; '('
0x140002308  mov     ecx, 40h ; '@'
0x14000230d  mov     r8d, 43627355h
0x140002313  call    cs:__imp_ExAllocatePool2
0x14000231a  nop     dword ptr [rax+rax+00h]
0x14000231f  mov     [rsp+0A8h+arg_18], rax
0x140002327  test    rax, rax
0x14000232a  jz      short loc_140002397
0x14000232c  lea     rcx, [r12+0F8h]; SpinLock
0x140002334  mov     dword ptr [rax], 6B636F4Ch
0x14000233a  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14000233f  mov     dword ptr [rax+18h], 44707249h
0x140002346  mov     [rax+20h], rbp
0x14000234a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002351  nop     dword ptr [rax+rax+00h]
0x140002356  add     r12, 0E8h
0x14000235d  mov     rcx, [r12+8]
0x140002362  cmp     [rcx], r12
0x140002365  jnz     loc_14000252A
0x14000236b  mov     rax, [rsp+0A8h+arg_18]
0x140002373  add     rax, 8
0x140002377  mov     [rax+8], rcx
0x14000237b  mov     [rax], r12
0x14000237e  mov     [rcx], rax
0x140002381  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140002386  mov     [r12+8], rax
0x14000238b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002392  nop     dword ptr [rax+rax+00h]
0x140002397  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000239e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400023a5  lea     rcx, WPP_b8ba6c0bda43381ffdf12cf14fa10529_Traceguids
0x1400023ac  jz      short loc_1400023C0
0x1400023ae  mov     rax, cs:WPP_GLOBAL_Control
0x1400023b5  cmp     word ptr [rax+48h], 0
0x1400023ba  jnz     loc_140002531
0x1400023c0  mov     r13, [rsp+0A8h+arg_10]
0x1400023c8  test    r15d, r15d
0x1400023cb  jz      short loc_1400023EC
0x1400023cd  cmp     r15d, 0Fh
0x1400023d1  jnz     short loc_140002424
0x1400023d3  cmp     byte ptr [rsi+4], 0
0x1400023d7  mov     rdx, rbp; Irp
0x1400023da  mov     rcx, rbx; PeekContext
0x1400023dd  jnz     loc_1400024D6
0x1400023e3  call    DispatchPdoInternalDeviceControl
0x1400023e8  mov     ebx, eax
0x1400023ea  jmp     short loc_1400023F9
0x1400023ec  mov     rdx, rbp
0x1400023ef  mov     rcx, rsi
0x1400023f2  call    USBC_Create
0x1400023f7  mov     ebx, eax
0x1400023f9  test    r14b, r14b
0x1400023fc  jz      short loc_140002410
0x1400023fe  mov     eax, 0FFFFFFFFh
0x140002403  lock xadd [rdi+134h], eax
0x14000240b  cmp     eax, 1
0x14000240e  jz      short loc_140002483
0x140002410  mov     eax, ebx
0x140002412  add     rsp, 68h
0x140002416  pop     r15
0x140002418  pop     r14
0x14000241a  pop     r13
0x14000241c  pop     r12
0x14000241e  pop     rdi
0x14000241f  pop     rsi
0x140002420  pop     rbp
0x140002421  pop     rbx
0x140002422  retn
0x140002424  mov     eax, r15d
0x140002427  sub     eax, 2
0x14000242a  jnz     short loc_140002459
0x14000242c  mov     r8, rbp
0x14000242f  cmp     [rsi+4], al
0x140002432  jz      short loc_140002444
0x140002434  mov     rdx, [rbx+28h]
0x140002438  mov     rcx, rbx
0x14000243b  call    UsbcForwardIrp
0x140002440  mov     ebx, eax
0x140002442  jmp     short loc_1400023F9
0x140002444  mov     rcx, [rsi+0F0h]
0x14000244b  mov     ebx, 0C00000BBh
0x140002450  mov     edx, ebx
0x140002452  call    UsbcCompleteIrp
0x140002457  jmp     short loc_1400023F9
0x140002459  sub     eax, 0Ch
0x14000245c  jz      short loc_1400024B2
0x14000245e  sub     eax, 8
0x140002461  jz      short loc_1400024A0
0x140002463  sub     eax, 1
0x140002466  jz      short loc_1400024C4
0x140002468  cmp     eax, 4
0x14000246b  jnz     loc_140002579
0x140002471  mov     rdx, rbp
0x140002474  mov     rcx, rsi
0x140002477  call    USBC_PnP
0x14000247c  mov     ebx, eax
0x14000247e  jmp     loc_1400023F9
0x140002483  lea     rcx, [rdi+138h]; Event
0x14000248a  xor     r8d, r8d; Wait
0x14000248d  xor     edx, edx; Increment
0x14000248f  call    cs:__imp_KeSetEvent
0x140002496  nop     dword ptr [rax+rax+00h]
0x14000249b  jmp     loc_140002410
0x1400024a0  mov     rdx, rbp
0x1400024a3  mov     rcx, rsi
0x1400024a6  call    USBC_Power
0x1400024ab  mov     ebx, eax
0x1400024ad  jmp     loc_1400023F9
0x1400024b2  mov     rdx, rbp
0x1400024b5  mov     rcx, rsi
0x1400024b8  call    USBC_DeviceControl
0x1400024bd  mov     ebx, eax
0x1400024bf  jmp     loc_1400023F9
0x1400024c4  mov     rdx, rbp
0x1400024c7  mov     rcx, rsi
0x1400024ca  call    USBC_SystemControl
0x1400024cf  mov     ebx, eax
0x1400024d1  jmp     loc_1400023F9
0x1400024d6  call    DispatchFdoInternalDeviceControl
0x1400024db  mov     ebx, eax
0x1400024dd  jmp     loc_1400023F9
0x1400024e2  lock dec dword ptr [rbx+134h]
0x1400024e9  cmp     r15d, 16h
0x1400024ed  jz      short loc_140002515
0x1400024ef  mov     ebx, 0C0000056h
0x1400024f4  mov     qword ptr [rbp+38h], 0
0x1400024fc  xor     edx, edx; PriorityBoost
0x1400024fe  mov     [rbp+30h], ebx
0x140002501  mov     rcx, rbp; Irp
0x140002504  call    cs:__imp_IofCompleteRequest
0x14000250b  nop     dword ptr [rax+rax+00h]
0x140002510  jmp     loc_140002410
0x140002515  test    ecx, ecx
0x140002517  jz      short loc_1400024EF
0x140002519  mov     rcx, rbp; Irp
0x14000251c  call    cs:__imp_PoStartNextPowerIrp
0x140002523  nop     dword ptr [rax+rax+00h]
0x140002528  jmp     short loc_1400024EF
0x14000252a  mov     ecx, 3
0x14000252f  int     29h; Win8: RtlFailFast(ecx)
0x140002531  mov     eax, [rsp+0A8h+arg_8]
0x140002538  mov     r9d, 0Bh
0x14000253e  mov     [rsp+0A8h+var_70], eax
0x140002542  mov     r8d, 9
0x140002548  mov     [rsp+0A8h+var_78], r15d
0x14000254d  mov     dl, 5
0x14000254f  mov     [rsp+0A8h+var_80], r13
0x140002554  mov     r13, [rsp+0A8h+arg_10]
0x14000255c  mov     qword ptr [rsp+0A8h+RemlockSize], rcx
0x140002561  mov     rcx, [r13+558h]
0x140002568  call    WPP_RECORDER_SF_qDD
0x14000256d  lea     rcx, WPP_b8ba6c0bda43381ffdf12cf14fa10529_Traceguids
0x140002574  jmp     loc_1400023C8
0x140002579  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140002580  jz      short loc_1400025A6
0x140002582  mov     dword ptr [rsp+0A8h+var_80], r15d
0x140002587  mov     r9d, 0Ch
0x14000258d  mov     qword ptr [rsp+0A8h+RemlockSize], rcx
0x140002592  mov     r8d, 9
0x140002598  mov     rcx, [r13+558h]
0x14000259f  mov     dl, 2
0x1400025a1  call    WPP_RECORDER_SF_D
0x1400025a6  cmp     [rsp+0A8h+arg_0], 0
0x1400025ae  mov     r8, rbp
0x1400025b1  mov     rcx, r13
0x1400025b4  jz      short loc_1400025C6
0x1400025b6  mov     rdx, [r13+28h]
0x1400025ba  call    UsbcForwardIrp
0x1400025bf  mov     ebx, eax
0x1400025c1  jmp     loc_1400023F9
0x1400025c6  mov     ebx, 0C00000BBh
0x1400025cb  mov     edx, ebx
0x1400025cd  call    UsbcCompleteIrp
0x1400025d2  jmp     loc_1400023F9
0x1400025d7  mov     rcx, cs:g_RecorderLog
0x1400025de  lea     rax, WPP_b8ba6c0bda43381ffdf12cf14fa10529_Traceguids
0x1400025e5  mov     r9d, 0Ah
0x1400025eb  mov     [rsp+0A8h+var_80], rbp
0x1400025f0  mov     r8d, 1
0x1400025f6  mov     qword ptr [rsp+0A8h+RemlockSize], rax
0x1400025fb  mov     dl, 4
0x1400025fd  call    WPP_RECORDER_SF_q
0x140002602  jmp     loc_1400022BE
0x140002607  cmp     [rsp+0A8h+arg_8], 0
0x14000260f  jz      loc_1400022C8
0x140002615  mov     rcx, rbp; Irp
0x140002618  call    cs:__imp_PoStartNextPowerIrp
0x14000261f  nop     dword ptr [rax+rax+00h]
0x140002624  jmp     loc_1400022C8
```
