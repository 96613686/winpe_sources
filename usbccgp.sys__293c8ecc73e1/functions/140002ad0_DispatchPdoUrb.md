# DispatchPdoUrb

- ea: `0x140002ad0`
- end: `0x140003382`
- name: `DispatchPdoUrb`
- size: `2226`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140002630`

## callees

- `0x1400019d8`
- `0x140001bc8`
- `0x140002ad0`
- `0x140003388`
- `0x140003470`
- `0x140003b3c`
- `0x1400083c8`
- `0x1400088b4`
- `0x140008eac`
- `0x14000b4bc`
- `0x14000ba3c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002cb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ec9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000312d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002cb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002ec9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000312d`
- `ntoskrnl!IofCompleteRequest` at `0x140002e5a`
- `ntoskrnl!IofCompleteRequest` at `0x1400030be`
- `ntoskrnl!IofCompleteRequest` at `0x140002e5a`
- `ntoskrnl!IofCompleteRequest` at `0x1400030be`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002cdd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002ef5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003159`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002cdd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002ef5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003159`
- `ntoskrnl!KeSetEvent` at `0x140002d93`
- `ntoskrnl!KeSetEvent` at `0x140002d93`
- `ntoskrnl!IofCallDriver` at `0x140002c3c`
- `ntoskrnl!IofCallDriver` at `0x140002c3c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002bd5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002cc1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002d76`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002ed9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000313d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400031f0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000328e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000331f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002bd5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002cc1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002d76`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002ed9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000313d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400031f0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000328e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000331f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002b2f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002c62`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002d01`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002e7e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400030e2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002b2f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002c62`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002d01`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002e7e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400030e2`
- `ntoskrnl!KeResetEvent` at `0x140002bc5`
- `ntoskrnl!KeResetEvent` at `0x140002bc5`
- `ntoskrnl!ExAllocatePool2` at `0x140002b5a`
- `ntoskrnl!ExAllocatePool2` at `0x140002b5a`

## pseudocode

```c
__int64 __fastcall DispatchPdoUrb(__int64 a1, IRP *a2)
{
  IRP *v2; // rdi
  __int64 v3; // rbx
  _IO_SECURITY_CONTEXT *SecurityContext; // r14
  int v6; // r13d
  __int64 Pool2; // rax
  int v8; // edx
  _QWORD *v9; // rdx
  _QWORD *v10; // rax
  signed __int32 v11; // r15d
  int v12; // edx
  struct _DEVICE_OBJECT *v13; // rcx
  unsigned int v14; // esi
  _QWORD *i; // rax
  _QWORD *v16; // rcx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *j; // rax
  signed __int32 v20; // r15d
  _QWORD *v21; // r8
  _QWORD *v22; // rdx
  _QWORD *n; // rax
  _QWORD *v25; // rcx
  _QWORD *v26; // rdx
  _ACCESS_STATE **p_AccessState; // r15
  _BYTE *v29; // r14
  __int64 k; // rcx
  __int64 *v31; // r12
  __int64 v32; // rax
  __int64 v33; // r14
  __int64 v34; // rdx
  _QWORD *m; // rax
  _QWORD *v36; // rcx
  _QWORD *v37; // rdx
  int v38; // edx
  unsigned int v39; // r14d
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-28h] BYREF
  int v41; // [rsp+B0h] [rbp+48h] BYREF

  v2 = a2;
  v3 = *(_QWORD *)(a1 + 232);
  SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( SecurityContext )
  {
    v6 = WORD1(SecurityContext->SecurityQos);
    if ( *(_BYTE *)(a1 + 404) == 1 && *(_BYTE *)(a1 + 405) == 1 && (unsigned __int16)(v6 - 53) > 1u )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 3;
        WPP_RECORDER_SF_q(
          *(_QWORD *)(a1 + 392),
          (_DWORD)a2,
          8,
          33,
          (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
          *(_QWORD *)(a1 + 224));
      }
      HIDWORD(SecurityContext->SecurityQos) = -1073741807;
      UsbcCompleteIrp(v3, 3221225473LL, v2);
      return 3221225473LL;
    }
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 256), &LockHandle);
    if ( (unsigned int)(*(_DWORD *)(v3 + 12) - 5) <= 1 )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v39 = -1073741436;
    }
    else
    {
      Pool2 = ExAllocatePool2(64, 40, 1130525525);
      if ( Pool2 )
      {
        *(_DWORD *)Pool2 = 1801678668;
        *(_DWORD *)(Pool2 + 24) = 1347768898;
        *(_QWORD *)(Pool2 + 32) = v2;
        v9 = *(_QWORD **)(v3 + 272);
        if ( *v9 != v3 + 264 )
          goto LABEL_95;
        v10 = (_QWORD *)(Pool2 + 8);
        *v10 = v3 + 264;
        v10[1] = v9;
        *v9 = v10;
        *(_QWORD *)(v3 + 272) = v10;
LABEL_7:
        v11 = 1;
        if ( _InterlockedIncrement((volatile signed __int32 *)(v3 + 280)) == 1 )
          KeResetEvent((PRKEVENT)(v3 + 288));
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( v6 )
        {
          if ( v6 == 1 )
            goto LABEL_53;
          if ( v6 != 11 )
          {
            if ( v6 != 59 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                && LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                LOBYTE(v12) = 5;
                WPP_RECORDER_SF_D(
                  *(_QWORD *)(a1 + 392),
                  v12,
                  4,
                  38,
                  (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
                  v6);
              }
              v13 = *(struct _DEVICE_OBJECT **)(v3 + 40);
              ++v2->CurrentLocation;
              ++v2->Tail.Overlay.CurrentStackLocation;
              v14 = IofCallDriver(v13, v2);
              memset(&LockHandle, 0, sizeof(LockHandle));
              KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 248), &LockHandle);
              for ( i = *(_QWORD **)(v3 + 232); i != (_QWORD *)(v3 + 232); i = (_QWORD *)*i )
              {
                v16 = (_QWORD *)*i;
                if ( (IRP *)i[3] == v2 )
                {
                  if ( (_QWORD *)v16[1] != i )
                    goto LABEL_95;
                  v17 = (_QWORD *)i[1];
                  if ( (_QWORD *)*v17 != i )
                    goto LABEL_95;
                  *v17 = v16;
                  v16[1] = v17;
                  ExFreePoolWithTag(i - 1, 0x43627355u);
                  break;
                }
              }
              KeReleaseInStackQueuedSpinLock(&LockHandle);
              IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 200), v2, 0x20u);
              memset(&LockHandle, 0, sizeof(LockHandle));
              KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 256), &LockHandle);
              v18 = (_QWORD *)(v3 + 264);
              for ( j = *(_QWORD **)(v3 + 264); j != v18; j = (_QWORD *)*j )
              {
                if ( (IRP *)j[3] == v2 )
                {
                  v20 = _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF);
                  v21 = (_QWORD *)*j;
                  v11 = v20 - 1;
                  if ( *(_QWORD **)(*j + 8LL) == j )
                  {
                    v22 = (_QWORD *)j[1];
                    if ( (_QWORD *)*v22 == j )
                    {
                      *v22 = v21;
                      v21[1] = v22;
                      ExFreePoolWithTag(j - 1, 0x43627355u);
LABEL_28:
                      KeReleaseInStackQueuedSpinLock(&LockHandle);
                      if ( !v11 )
                        KeSetEvent((PRKEVENT)(v3 + 288), 0, 0);
                      return v14;
                    }
                  }
LABEL_95:
                  __fastfail(3u);
                }
              }
              if ( *(_BYTE *)(v3 + 1376) == 1 )
              {
                v11 = _InterlockedDecrement((volatile signed __int32 *)(v3 + 280));
                goto LABEL_28;
              }
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_28;
              LOBYTE(v18) = 3;
              WPP_RECORDER_SF_(
                g_RecorderLog,
                (_DWORD)v18,
                8,
                59,
                (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
              KeReleaseInStackQueuedSpinLock(&LockHandle);
              return v14;
            }
LABEL_53:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v12) = 4;
              WPP_RECORDER_SF_qq(
                *(_QWORD *)(a1 + 392),
                v12,
                1,
                37,
                (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
                *(_QWORD *)(a1 + 224),
                (char)SecurityContext);
            }
            if ( v6 == 1 )
            {
              p_AccessState = &SecurityContext[1].AccessState;
              v29 = (char *)&SecurityContext[1].AccessState + 2;
            }
            else
            {
              p_AccessState = (_ACCESS_STATE **)&SecurityContext[2];
              v29 = (char *)&SecurityContext[2].SecurityQos + 2;
            }
            for ( k = 0; ; k = (unsigned int)(k + 1) )
            {
              if ( (unsigned int)k >= *(_DWORD *)(a1 + 12) )
                return (unsigned int)UsbcForwardIrpWithCompletion(
                                       v3,
                                       *(_QWORD *)(v3 + 40),
                                       v2,
                                       &CompletionPdoSelectInterface,
                                       *(_QWORD *)(a1 + 224),
                                       a1);
              v31 = *(__int64 **)(*(_QWORD *)(*(_QWORD *)(a1 + 240) + 8LL) + 8 * k);
              v32 = v31[1];
              if ( *(_BYTE *)(v32 + 2) == *v29 )
                break;
            }
            v33 = 0;
            if ( *(_DWORD *)(v32 + 16) )
            {
              do
              {
                v34 = *v31;
                v41 = 0;
                if ( (int)GetEndpointPriority(a1, v34, (unsigned int)v33, &v41) >= 0 )
                {
                  switch ( v41 )
                  {
                    case 1:
                      HIDWORD(p_AccessState[3 * v33 + 5]) |= 0x10u;
                      break;
                    case 2:
                      HIDWORD(p_AccessState[3 * v33 + 5]) |= 0x20u;
                      break;
                    case 3:
                      HIDWORD(p_AccessState[3 * v33 + 5]) |= 0x30u;
                      break;
                  }
                }
                v33 = (unsigned int)(v33 + 1);
              }
              while ( (unsigned int)v33 < *(_DWORD *)(v31[1] + 16) );
            }
            return (unsigned int)UsbcForwardIrpWithCompletion(
                                   v3,
                                   *(_QWORD *)(v3 + 40),
                                   v2,
                                   &CompletionPdoSelectInterface,
                                   *(_QWORD *)(a1 + 224),
                                   a1);
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v12) = 5;
            WPP_RECORDER_SF_qq(
              *(_QWORD *)(a1 + 392),
              v12,
              1,
              36,
              (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
              *(_QWORD *)(a1 + 224),
              (char)SecurityContext);
          }
          return (unsigned int)DispatchPdoUrbGetDescriptorFromDevice(a1, v2);
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = 4;
            WPP_RECORDER_SF_qq(
              *(_QWORD *)(a1 + 392),
              v12,
              1,
              35,
              (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
              *(_QWORD *)(a1 + 224),
              (char)SecurityContext);
          }
          return (unsigned int)DispatchPdoUrbSelectConfiguration(a1, v2);
        }
      }
      if ( *(_BYTE *)(v3 + 1376) )
        goto LABEL_7;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_(g_RecorderLog, v8, 8, 58, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v39 = -1073741670;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v38) = 2;
      WPP_RECORDER_SF_qD(
        *(_QWORD *)(a1 + 392),
        v38,
        8,
        34,
        (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
        *(_QWORD *)(a1 + 224),
        *(_DWORD *)(v3 + 12));
    }
    v2->IoStatus.Status = v39;
    IofCompleteRequest(v2, 0);
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 248), &LockHandle);
    for ( m = *(_QWORD **)(v3 + 232); m != (_QWORD *)(v3 + 232); m = (_QWORD *)*m )
    {
      v36 = (_QWORD *)*m;
      if ( (IRP *)m[3] == v2 )
      {
        if ( (_QWORD *)v36[1] != m )
          goto LABEL_95;
        v37 = (_QWORD *)m[1];
        if ( (_QWORD *)*v37 != m )
          goto LABEL_95;
        *v37 = v36;
        v36[1] = v37;
        ExFreePoolWithTag(m - 1, 0x43627355u);
        break;
      }
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 200), v2, 0x20u);
    return v39;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_q(
        *(_QWORD *)(a1 + 392),
        (_DWORD)a2,
        8,
        32,
        (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
        *(_QWORD *)(a1 + 224));
    }
    v2->IoStatus.Status = -1073741811;
    IofCompleteRequest(v2, 0);
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 248), &LockHandle);
    for ( n = *(_QWORD **)(v3 + 232); n != (_QWORD *)(v3 + 232); n = (_QWORD *)*n )
    {
      v25 = (_QWORD *)*n;
      if ( (IRP *)n[3] == v2 )
      {
        if ( (_QWORD *)v25[1] != n )
          goto LABEL_95;
        v26 = (_QWORD *)n[1];
        if ( (_QWORD *)*v26 != n )
          goto LABEL_95;
        *v26 = v25;
        v25[1] = v26;
        ExFreePoolWithTag(n - 1, 0x43627355u);
        break;
      }
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 200), v2, 0x20u);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140002ad0  push    rbp
0x140002ad2  push    rbx
0x140002ad3  push    rsi
0x140002ad4  push    rdi
0x140002ad5  push    r12
0x140002ad7  push    r13
0x140002ad9  push    r14
0x140002adb  push    r15
0x140002add  mov     rbp, rsp
0x140002ae0  sub     rsp, 68h
0x140002ae4  mov     rax, [rdx+0B8h]
0x140002aeb  mov     rdi, rdx
0x140002aee  mov     rbx, [rcx+0E8h]
0x140002af5  mov     rsi, rcx
0x140002af8  mov     r14, [rax+8]
0x140002afc  test    r14, r14
0x140002aff  jz      loc_140002E3A
0x140002b05  cmp     byte ptr [rcx+194h], 1
0x140002b0c  movzx   r13d, word ptr [r14+2]
0x140002b11  jz      loc_140002DB3
0x140002b17  xorps   xmm0, xmm0
0x140002b1a  lea     rdx, [rbp+LockHandle]; LockHandle
0x140002b1e  xor     eax, eax
0x140002b20  lea     rcx, [rbx+100h]; SpinLock
0x140002b27  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140002b2b  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140002b2f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002b36  nop     dword ptr [rax+rax+00h]
0x140002b3b  mov     eax, [rbx+0Ch]
0x140002b3e  sub     eax, 5
0x140002b41  cmp     eax, 1
0x140002b44  jbe     loc_14000331B
0x140002b4a  mov     edx, 28h ; '('
0x140002b4f  mov     ecx, 40h ; '@'
0x140002b54  mov     r8d, 43627355h
0x140002b5a  call    cs:__imp_ExAllocatePool2
0x140002b61  nop     dword ptr [rax+rax+00h]
0x140002b66  test    rax, rax
0x140002b69  jz      loc_1400031A9
0x140002b6f  lea     rcx, [rbx+108h]
0x140002b76  mov     dword ptr [rax], 6B636F4Ch
0x140002b7c  mov     dword ptr [rax+18h], 50555242h
0x140002b83  mov     [rax+20h], rdi
0x140002b87  mov     rdx, [rcx+8]
0x140002b8b  cmp     [rdx], rcx
0x140002b8e  jnz     loc_14000337B
0x140002b94  add     rax, 8
0x140002b98  mov     [rax], rcx
0x140002b9b  mov     [rax+8], rdx
0x140002b9f  mov     [rdx], rax
0x140002ba2  mov     [rcx+8], rax
0x140002ba6  mov     r15d, 1
0x140002bac  mov     eax, r15d
0x140002baf  lock xadd [rbx+118h], eax
0x140002bb7  inc     eax
0x140002bb9  cmp     eax, r15d
0x140002bbc  jnz     short loc_140002BD1
0x140002bbe  lea     rcx, [rbx+120h]; Event
0x140002bc5  call    cs:__imp_KeResetEvent
0x140002bcc  nop     dword ptr [rax+rax+00h]
0x140002bd1  lea     rcx, [rbp+LockHandle]; LockHandle
0x140002bd5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002bdc  nop     dword ptr [rax+rax+00h]
0x140002be1  mov     ecx, r13d
0x140002be4  test    r13d, r13d
0x140002be7  jz      loc_140002FD9
0x140002bed  sub     ecx, r15d
0x140002bf0  jz      loc_140002F4C
0x140002bf6  sub     ecx, 0Ah
0x140002bf9  jz      loc_140002F18
0x140002bff  cmp     ecx, 30h ; '0'
0x140002c02  jz      loc_140002F4C
0x140002c08  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002c0f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140002c16  jz      short loc_140002C2A
0x140002c18  mov     rax, cs:WPP_GLOBAL_Control
0x140002c1f  cmp     word ptr [rax+48h], 0
0x140002c24  jnz     loc_140003207
0x140002c2a  mov     rcx, [rbx+28h]; DeviceObject
0x140002c2e  mov     rdx, rdi; Irp
0x140002c31  inc     byte ptr [rdi+43h]
0x140002c34  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140002c3c  call    cs:__imp_IofCallDriver
0x140002c43  nop     dword ptr [rax+rax+00h]
0x140002c48  xorps   xmm0, xmm0
0x140002c4b  lea     rcx, [rbx+0F8h]; SpinLock
0x140002c52  mov     esi, eax
0x140002c54  lea     rdx, [rbp+LockHandle]; LockHandle
0x140002c58  xor     eax, eax
0x140002c5a  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140002c5e  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140002c62  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002c69  nop     dword ptr [rax+rax+00h]
0x140002c6e  lea     rdx, [rbx+0E8h]
0x140002c75  mov     rax, [rdx]
0x140002c78  cmp     rax, rdx
0x140002c7b  jz      short loc_140002CBD
0x140002c7d  mov     rcx, [rax]
0x140002c80  cmp     [rax+18h], rdi
0x140002c84  jnz     loc_140002E32
0x140002c8a  cmp     [rcx+8], rax
0x140002c8e  jnz     loc_14000337B
0x140002c94  mov     rdx, [rax+8]
0x140002c98  cmp     [rdx], rax
0x140002c9b  jnz     loc_14000337B
0x140002ca1  mov     [rdx], rcx
0x140002ca4  mov     [rcx+8], rdx
0x140002ca8  mov     edx, 43627355h; Tag
0x140002cad  lea     rcx, [rax-8]; P
0x140002cb1  call    cs:__imp_ExFreePoolWithTag
0x140002cb8  nop     dword ptr [rax+rax+00h]
0x140002cbd  lea     rcx, [rbp+LockHandle]; LockHandle
0x140002cc1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002cc8  nop     dword ptr [rax+rax+00h]
0x140002ccd  lea     rcx, [rbx+0C8h]; RemoveLock
0x140002cd4  mov     r8d, 20h ; ' '; RemlockSize
0x140002cda  mov     rdx, rdi; Tag
0x140002cdd  call    cs:__imp_IoReleaseRemoveLockEx
0x140002ce4  nop     dword ptr [rax+rax+00h]
0x140002ce9  xorps   xmm0, xmm0
0x140002cec  lea     rdx, [rbp+LockHandle]; LockHandle
0x140002cf0  xor     eax, eax
0x140002cf2  lea     rcx, [rbx+100h]; SpinLock
0x140002cf9  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140002cfd  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140002d01  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002d08  nop     dword ptr [rax+rax+00h]
0x140002d0d  lea     rdx, [rbx+108h]
0x140002d14  mov     rax, [rdx]
0x140002d17  cmp     rax, rdx
0x140002d1a  jz      loc_140003237
0x140002d20  cmp     [rax+18h], rdi
0x140002d24  lea     rcx, [rax-8]; P
0x140002d28  jnz     loc_140002F10
0x140002d2e  mov     r15d, 0FFFFFFFFh
0x140002d34  lock xadd [rbx+118h], r15d
0x140002d3d  mov     r8, [rax]
0x140002d40  dec     r15d
0x140002d43  cmp     [r8+8], rax
0x140002d47  jnz     loc_14000337B
0x140002d4d  mov     rdx, [rax+8]
0x140002d51  cmp     [rdx], rax
0x140002d54  jnz     loc_14000337B
0x140002d5a  mov     [rdx], r8
0x140002d5d  mov     [r8+8], rdx
0x140002d61  mov     edx, 43627355h; Tag
0x140002d66  call    cs:__imp_ExFreePoolWithTag
0x140002d6d  nop     dword ptr [rax+rax+00h]
0x140002d72  lea     rcx, [rbp+LockHandle]; LockHandle
0x140002d76  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002d7d  nop     dword ptr [rax+rax+00h]
0x140002d82  test    r15d, r15d
0x140002d85  jnz     short loc_140002D9F
0x140002d87  lea     rcx, [rbx+120h]; Event
0x140002d8e  xor     r8d, r8d; Wait
0x140002d91  xor     edx, edx; Increment
0x140002d93  call    cs:__imp_KeSetEvent
0x140002d9a  nop     dword ptr [rax+rax+00h]
0x140002d9f  mov     eax, esi
0x140002da1  add     rsp, 68h
0x140002da5  pop     r15
0x140002da7  pop     r14
0x140002da9  pop     r13
0x140002dab  pop     r12
0x140002dad  pop     rdi
0x140002dae  pop     rsi
0x140002daf  pop     rbx
0x140002db0  pop     rbp
0x140002db1  retn
0x140002db3  cmp     byte ptr [rcx+195h], 1
0x140002dba  jnz     loc_140002B17
0x140002dc0  lea     eax, [r13-35h]
0x140002dc4  cmp     ax, 1
0x140002dc8  jbe     loc_140002B17
0x140002dce  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002dd5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002ddc  jz      short loc_140002E10
0x140002dde  mov     rax, [rcx+0E0h]
0x140002de5  mov     r9d, 21h ; '!'
0x140002deb  mov     rcx, [rcx+188h]
0x140002df2  mov     r8d, 8
0x140002df8  mov     [rsp+68h+var_40], rax
0x140002dfd  mov     dl, 3
0x140002dff  lea     rax, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x140002e06  mov     [rsp+68h+var_48], rax
0x140002e0b  call    WPP_RECORDER_SF_q
0x140002e10  mov     r8, rdi
0x140002e13  mov     dword ptr [r14+4], 0C0000011h
0x140002e1b  mov     edx, 0C0000001h
0x140002e20  mov     rcx, rbx
0x140002e23  call    UsbcCompleteIrp
0x140002e28  mov     eax, 0C0000001h
0x140002e2d  jmp     loc_140002DA1
0x140002e32  mov     rax, rcx
0x140002e35  jmp     loc_140002C78
0x140002e3a  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002e41  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002e48  jnz     loc_140003172
0x140002e4e  xor     edx, edx; PriorityBoost
0x140002e50  mov     dword ptr [rdi+30h], 0C000000Dh
0x140002e57  mov     rcx, rdi; Irp
0x140002e5a  call    cs:__imp_IofCompleteRequest
0x140002e61  nop     dword ptr [rax+rax+00h]
0x140002e66  xorps   xmm0, xmm0
0x140002e69  lea     rcx, [rbx+0F8h]; SpinLock
0x140002e70  xor     eax, eax
0x140002e72  lea     rdx, [rbp+LockHandle]; LockHandle
0x140002e76  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140002e7a  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140002e7e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002e85  nop     dword ptr [rax+rax+00h]
0x140002e8a  lea     rdx, [rbx+0E8h]
0x140002e91  mov     rax, [rdx]
0x140002e94  cmp     rax, rdx
0x140002e97  jz      short loc_140002ED5
0x140002e99  mov     rcx, [rax]
0x140002e9c  cmp     [rax+18h], rdi
0x140002ea0  jnz     short loc_140002F0B
0x140002ea2  cmp     [rcx+8], rax
0x140002ea6  jnz     loc_14000337B
0x140002eac  mov     rdx, [rax+8]
0x140002eb0  cmp     [rdx], rax
0x140002eb3  jnz     loc_14000337B
0x140002eb9  mov     [rdx], rcx
0x140002ebc  mov     [rcx+8], rdx
0x140002ec0  mov     edx, 43627355h; Tag
0x140002ec5  lea     rcx, [rax-8]; P
0x140002ec9  call    cs:__imp_ExFreePoolWithTag
0x140002ed0  nop     dword ptr [rax+rax+00h]
0x140002ed5  lea     rcx, [rbp+LockHandle]; LockHandle
0x140002ed9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002ee0  nop     dword ptr [rax+rax+00h]
0x140002ee5  lea     rcx, [rbx+0C8h]; RemoveLock
0x140002eec  mov     r8d, 20h ; ' '; RemlockSize
0x140002ef2  mov     rdx, rdi; Tag
0x140002ef5  call    cs:__imp_IoReleaseRemoveLockEx
0x140002efc  nop     dword ptr [rax+rax+00h]
0x140002f01  mov     eax, 0C000000Dh
0x140002f06  jmp     loc_140002DA1
0x140002f0b  mov     rax, rcx
0x140002f0e  jmp     short loc_140002E94
0x140002f10  mov     rax, [rax]
0x140002f13  jmp     loc_140002D17
0x140002f18  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002f1f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002f26  jz      short loc_140002F3A
0x140002f28  mov     rax, cs:WPP_GLOBAL_Control
0x140002f2f  cmp     word ptr [rax+48h], 0
0x140002f34  jnz     loc_14000329F
0x140002f3a  mov     rdx, rdi
0x140002f3d  mov     rcx, rsi
0x140002f40  call    DispatchPdoUrbGetDescriptorFromDevice
0x140002f45  mov     esi, eax
0x140002f47  jmp     loc_140002D9F
0x140002f4c  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002f53  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002f5a  jnz     loc_140003036
0x140002f60  cmp     r13d, r15d
0x140002f63  jnz     short loc_140002FCF
0x140002f65  lea     r15, [r14+20h]
0x140002f69  add     r14, 22h ; '"'
0x140002f6d  mov     rax, [rsi+0F0h]
0x140002f74  xor     ecx, ecx
0x140002f76  movzx   r8d, byte ptr [r14]
0x140002f7a  mov     edx, [rsi+0Ch]
0x140002f7d  mov     r9, [rax+8]
0x140002f81  cmp     ecx, edx
0x140002f83  jnb     short loc_140002FA1
0x140002f85  mov     r12, [r9+rcx*8]
0x140002f89  mov     rax, [r12+8]
0x140002f8e  cmp     [rax+2], r8b
0x140002f92  jz      short loc_140002F98
0x140002f94  inc     ecx
0x140002f96  jmp     short loc_140002F81
0x140002f98  xor     r14d, r14d
0x140002f9b  cmp     [rax+10h], r14d
0x140002f9f  ja      short loc_140003000
0x140002fa1  mov     rax, [rsi+0E0h]
0x140002fa8  lea     r9, CompletionPdoSelectInterface
0x140002faf  mov     rdx, [rbx+28h]
0x140002fb3  mov     r8, rdi
0x140002fb6  mov     [rsp+68h+var_40], rsi
0x140002fbb  mov     rcx, rbx
0x140002fbe  mov     [rsp+68h+var_48], rax
0x140002fc3  call    UsbcForwardIrpWithCompletion
0x140002fc8  mov     esi, eax
0x140002fca  jmp     loc_140002D9F
0x140002fcf  lea     r15, [r14+30h]
0x140002fd3  add     r14, 32h ; '2'
0x140002fd7  jmp     short loc_140002F6D
0x140002fd9  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002fe0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002fe7  jnz     loc_14000306F
0x140002fed  mov     rdx, rdi
0x140002ff0  mov     rcx, rsi
0x140002ff3  call    DispatchPdoUrbSelectConfiguration
0x140002ff8  jmp     loc_140002F45
0x140003000  mov     rdx, [r12]
0x140003004  lea     r9, [rbp+arg_0]
0x140003008  mov     r8d, r14d
  ... truncated ...
```
