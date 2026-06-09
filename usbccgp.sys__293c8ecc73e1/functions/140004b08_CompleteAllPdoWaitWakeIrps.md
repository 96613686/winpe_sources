# CompleteAllPdoWaitWakeIrps

- ea: `0x140004b08`
- end: `0x140004e27`
- name: `CompleteAllPdoWaitWakeIrps`
- size: `799`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140005bb0`
- `0x140008980`
- `0x140008d58`
- `0x140014560`

## callees

- `0x140004b08`
- `0x1400054a0`
- `0x1400059e4`
- `0x140005eb0`
- `0x1400083c8`
- `0x140008d58`
- `0x140009f10`
- `0x140010b00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140004d5c`
- `ntoskrnl!IofCompleteRequest` at `0x140004d5c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004cb6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004d83`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004cb6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004d83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004bb0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004c38`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004bb0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004c38`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004c0a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004c79`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004c0a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004c79`
- `ntoskrnl!KeSetEvent` at `0x140004c53`
- `ntoskrnl!KeSetEvent` at `0x140004c53`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140004b58`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140004b58`

## pseudocode

```c
void __fastcall CompleteAllPdoWaitWakeIrps(char *Context, int a2)
{
  _DWORD *v3; // rcx
  char v5; // r12
  __int64 v6; // rdi
  _LIST_ENTRY *v7; // rsi
  PIRP v8; // rax
  _LIST_ENTRY *v9; // rcx
  _LIST_ENTRY *p_ListEntry; // rax
  void *v11; // rsi
  int v12; // edx
  KIRQL v13; // r14
  void *v14; // rax
  int v15; // r8d
  __int64 *v16; // rax
  KIRQL v17; // r15
  int v18; // ecx
  __int64 v19; // rdi
  __int64 *v20; // rcx
  IRP *v21; // rdi
  __int64 v22; // rax
  int v23; // [rsp+20h] [rbp-40h]
  __int64 *v24; // [rsp+50h] [rbp-10h] BYREF
  _LIST_ENTRY *v25; // [rsp+58h] [rbp-8h]

  v3 = (_DWORD *)*((_QWORD *)Context + 16);
  v25 = (_LIST_ENTRY *)&v24;
  v5 = 1;
  v24 = (__int64 *)&v24;
  if ( *v3 )
  {
    v6 = 0;
    do
    {
      v7 = (_LIST_ENTRY *)(*(_QWORD *)(*(_QWORD *)&v3[2 * v6 + 2] + 64LL) + 8LL);
      v8 = IoCsqRemoveNextIrp((PIO_CSQ)(*(_QWORD *)(*(_QWORD *)&v3[2 * v6 + 2] + 64LL) + 40LL), v7);
      if ( v8 )
      {
        v8->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = v7;
        v9 = v25;
        if ( (__int64 **)v25->Flink != &v24 )
LABEL_28:
          __fastfail(3u);
        p_ListEntry = &v8->Tail.Overlay.ListEntry;
        p_ListEntry->Flink = (_LIST_ENTRY *)&v24;
        p_ListEntry->Blink = v9;
        v9->Flink = p_ListEntry;
        v25 = p_ListEntry;
      }
      v3 = (_DWORD *)*((_QWORD *)Context + 16);
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < *v3 );
  }
  v11 = 0;
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 50);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)Context + 171),
      v12,
      3,
      22,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *((_QWORD *)Context + 4));
  }
  v14 = (void *)*((_QWORD *)Context + 48);
  Context[440] = 0;
  if ( v14 )
  {
    v11 = v14;
    *((_QWORD *)Context + 48) = 0;
  }
  _InterlockedExchange((volatile __int32 *)Context + 98, 0);
  _InterlockedExchange((volatile __int32 *)Context + 99, 0);
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 50, v13);
  while ( 1 )
  {
    v16 = v24;
    if ( v24 == (__int64 *)&v24 )
      break;
    if ( (__int64 **)v24[1] != &v24 )
      goto LABEL_28;
    v20 = (__int64 *)*v24;
    if ( *(__int64 **)(*v24 + 8) != v24 )
      goto LABEL_28;
    v24 = (__int64 *)*v24;
    v21 = (IRP *)(v16 - 21);
    v20[1] = (__int64)&v24;
    v21->IoStatus.Status = a2;
    v22 = *(v16 - 6);
    v21->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
    if ( Context[1362] )
    {
      CancelRemoteWakeNotificationIrp(v22, v21);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qqqd(
          *((_QWORD *)Context + 171),
          (unsigned int)&v24,
          v15,
          23,
          v23,
          *((_QWORD *)Context + 4),
          (char)v21,
          *(_QWORD *)(v22 + 224),
          a2);
      IofCompleteRequest(v21, 0);
      UsbcReleaseRemoveLock(Context, v21);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 200), v21, 0x20u);
    }
  }
  v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 43);
  KeSetEvent((PRKEVENT)(Context + 416), 0, 0);
  v18 = *((_DWORD *)Context + 307);
  if ( (v18 & 0x20) != 0 )
  {
    v19 = *((_QWORD *)Context + 154);
    *((_DWORD *)Context + 307) = v18 & 0xFFFFFFDF;
    *((_QWORD *)Context + 154) = 0;
  }
  else
  {
    v5 = 0;
    v19 = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 43, v17);
  if ( v5 && (int)AllocateWorker(Context, IdleFinishCompletionWorker, v19) < 0 )
    IdleFinishCompletionWorker(Context, v19);
  CheckParentWaitWake(Context);
  if ( v11 )
  {
    UsbcReleaseRemoveLock(Context, v11);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 200), v11, 0x20u);
  }
}

```

## disassembly

```asm
0x140004b08  push    rbp
0x140004b0a  push    rbx
0x140004b0b  push    rsi
0x140004b0c  push    rdi
0x140004b0d  push    r12
0x140004b0f  push    r14
0x140004b11  push    r15
0x140004b13  mov     rbp, rsp
0x140004b16  sub     rsp, 60h
0x140004b1a  lea     rax, [rbp+var_10]
0x140004b1e  mov     rbx, rcx
0x140004b21  mov     rcx, [rcx+80h]
0x140004b28  mov     r15d, edx
0x140004b2b  mov     [rbp+var_8], rax
0x140004b2f  mov     r12d, 1
0x140004b35  lea     rax, [rbp+var_10]
0x140004b39  mov     [rbp+var_10], rax
0x140004b3d  cmp     dword ptr [rcx], 0
0x140004b40  jbe     short loc_140004BA4
0x140004b42  xor     edi, edi
0x140004b44  mov     rcx, [rcx+rdi*8+8]
0x140004b49  mov     rsi, [rcx+40h]
0x140004b4d  add     rsi, 8
0x140004b51  mov     rdx, rsi; PeekContext
0x140004b54  lea     rcx, [rsi+20h]; Csq
0x140004b58  call    cs:__imp_IoCsqRemoveNextIrp
0x140004b5f  nop     dword ptr [rax+rax+00h]
0x140004b64  test    rax, rax
0x140004b67  jz      short loc_140004B96
0x140004b69  mov     [rax+78h], rsi
0x140004b6d  lea     rdx, [rbp+var_10]
0x140004b71  mov     rcx, [rbp+var_8]
0x140004b75  cmp     [rcx], rdx
0x140004b78  jnz     loc_140004E00
0x140004b7e  add     rax, 0A8h
0x140004b84  lea     rdx, [rbp+var_10]
0x140004b88  mov     [rax], rdx
0x140004b8b  mov     [rax+8], rcx
0x140004b8f  mov     [rcx], rax
0x140004b92  mov     [rbp+var_8], rax
0x140004b96  mov     rcx, [rbx+80h]
0x140004b9d  add     edi, r12d
0x140004ba0  cmp     edi, [rcx]
0x140004ba2  jb      short loc_140004B44
0x140004ba4  lea     rdi, [rbx+190h]
0x140004bab  xor     esi, esi
0x140004bad  mov     rcx, rdi; SpinLock
0x140004bb0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004bb7  nop     dword ptr [rax+rax+00h]
0x140004bbc  mov     r14b, al
0x140004bbf  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004bc6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004bcd  jnz     loc_140004D94
0x140004bd3  mov     rax, [rbx+180h]
0x140004bda  mov     [rbx+1B8h], sil
0x140004be1  test    rax, rax
0x140004be4  jz      short loc_140004BF4
0x140004be6  mov     rsi, rax
0x140004be9  mov     qword ptr [rbx+180h], 0
0x140004bf4  xor     eax, eax
0x140004bf6  mov     dl, r14b; NewIrql
0x140004bf9  xchg    eax, [rbx+188h]
0x140004bff  xor     eax, eax
0x140004c01  mov     rcx, rdi; SpinLock
0x140004c04  xchg    eax, [rbx+18Ch]
0x140004c0a  call    cs:__imp_KeReleaseSpinLock
0x140004c11  nop     dword ptr [rax+rax+00h]
0x140004c16  lea     r14, WPP_RECORDER_INITIALIZED
0x140004c1d  mov     rax, [rbp+var_10]
0x140004c21  lea     rcx, [rbp+var_10]
0x140004c25  cmp     rax, rcx
0x140004c28  jnz     loc_140004CD2
0x140004c2e  lea     r14, [rbx+158h]
0x140004c35  mov     rcx, r14; SpinLock
0x140004c38  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004c3f  nop     dword ptr [rax+rax+00h]
0x140004c44  lea     rcx, [rbx+1A0h]; Event
0x140004c4b  xor     r8d, r8d; Wait
0x140004c4e  xor     edx, edx; Increment
0x140004c50  mov     r15b, al
0x140004c53  call    cs:__imp_KeSetEvent
0x140004c5a  nop     dword ptr [rax+rax+00h]
0x140004c5f  mov     ecx, [rbx+4CCh]
0x140004c65  test    cl, 20h
0x140004c68  jnz     loc_140004E07
0x140004c6e  xor     r12b, r12b
0x140004c71  xor     edi, edi
0x140004c73  mov     dl, r15b; NewIrql
0x140004c76  mov     rcx, r14; SpinLock
0x140004c79  call    cs:__imp_KeReleaseSpinLock
0x140004c80  nop     dword ptr [rax+rax+00h]
0x140004c85  test    r12b, r12b
0x140004c88  jnz     loc_140004DC6
0x140004c8e  mov     rcx, rbx; Context
0x140004c91  call    CheckParentWaitWake
0x140004c96  test    rsi, rsi
0x140004c99  jz      short loc_140004CC2
0x140004c9b  mov     rdx, rsi
0x140004c9e  mov     rcx, rbx
0x140004ca1  call    UsbcReleaseRemoveLock
0x140004ca6  lea     rcx, [rbx+0C8h]; RemoveLock
0x140004cad  mov     r8d, 20h ; ' '; RemlockSize
0x140004cb3  mov     rdx, rsi; Tag
0x140004cb6  call    cs:__imp_IoReleaseRemoveLockEx
0x140004cbd  nop     dword ptr [rax+rax+00h]
0x140004cc2  add     rsp, 60h
0x140004cc6  pop     r15
0x140004cc8  pop     r14
0x140004cca  pop     r12
0x140004ccc  pop     rdi
0x140004ccd  pop     rsi
0x140004cce  pop     rbx
0x140004ccf  pop     rbp
0x140004cd0  retn
0x140004cd2  lea     rcx, [rbp+var_10]
0x140004cd6  cmp     [rax+8], rcx
0x140004cda  jnz     loc_140004E00
0x140004ce0  mov     rcx, [rax]
0x140004ce3  cmp     [rcx+8], rax
0x140004ce7  jnz     loc_140004E00
0x140004ced  mov     [rbp+var_10], rcx
0x140004cf1  lea     rdi, [rax-0A8h]
0x140004cf8  lea     rdx, [rbp+var_10]
0x140004cfc  mov     [rcx+8], rdx
0x140004d00  mov     [rdi+30h], r15d
0x140004d04  mov     rax, [rdi+78h]
0x140004d08  mov     qword ptr [rdi+78h], 0
0x140004d10  cmp     byte ptr [rbx+552h], 0
0x140004d17  jnz     loc_140004DF0
0x140004d1d  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140004d24  jz      short loc_140004D57
0x140004d26  mov     rax, [rax+0E0h]
0x140004d2d  mov     r9d, 17h
0x140004d33  mov     rcx, [rbx+558h]
0x140004d3a  mov     [rsp+60h+var_20], r15d
0x140004d3f  mov     [rsp+60h+var_28], rax
0x140004d44  mov     rax, [rbx+20h]
0x140004d48  mov     [rsp+60h+var_30], rdi
0x140004d4d  mov     [rsp+60h+var_38], rax
0x140004d52  call    WPP_RECORDER_SF_qqqd
0x140004d57  xor     edx, edx; PriorityBoost
0x140004d59  mov     rcx, rdi; Irp
0x140004d5c  call    cs:__imp_IofCompleteRequest
0x140004d63  nop     dword ptr [rax+rax+00h]
0x140004d68  mov     rdx, rdi
0x140004d6b  mov     rcx, rbx
0x140004d6e  call    UsbcReleaseRemoveLock
0x140004d73  lea     rcx, [rbx+0C8h]; RemoveLock
0x140004d7a  mov     r8d, 20h ; ' '; RemlockSize
0x140004d80  mov     rdx, rdi; Tag
0x140004d83  call    cs:__imp_IoReleaseRemoveLockEx
0x140004d8a  nop     dword ptr [rax+rax+00h]
0x140004d8f  jmp     loc_140004C1D
0x140004d94  mov     rcx, [rbx+20h]
0x140004d98  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140004d9f  mov     [rsp+60h+var_38], rcx
0x140004da4  mov     r9d, 16h
0x140004daa  mov     rcx, [rbx+558h]
0x140004db1  mov     dl, 4
0x140004db3  mov     [rsp+60h+var_40], rax
0x140004db8  lea     r8d, [r9-13h]
0x140004dbc  call    WPP_RECORDER_SF_q
0x140004dc1  jmp     loc_140004BD3
0x140004dc6  mov     r8, rdi
0x140004dc9  lea     rdx, IdleFinishCompletionWorker
0x140004dd0  mov     rcx, rbx
0x140004dd3  call    AllocateWorker
0x140004dd8  test    eax, eax
0x140004dda  jns     loc_140004C8E
0x140004de0  mov     rdx, rdi
0x140004de3  mov     rcx, rbx
0x140004de6  call    IdleFinishCompletionWorker
0x140004deb  jmp     loc_140004C8E
0x140004df0  mov     rdx, rdi
0x140004df3  mov     rcx, rax
0x140004df6  call    CancelRemoteWakeNotificationIrp
0x140004dfb  jmp     loc_140004C1D
0x140004e00  mov     ecx, 3
0x140004e05  int     29h; Win8: RtlFailFast(ecx)
0x140004e07  mov     rdi, [rbx+4D0h]
0x140004e0e  and     ecx, 0FFFFFFDFh
0x140004e11  mov     [rbx+4CCh], ecx
0x140004e17  mov     qword ptr [rbx+4D0h], 0
0x140004e22  jmp     loc_140004C73
```
