# LockSyncSendSetFeatureControlRequestForFunctionSuspend

- ea: `0x140014060`
- end: `0x1400142ab`
- name: `LockSyncSendSetFeatureControlRequestForFunctionSuspend`
- size: `587`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140007170`
- `0x140010650`
- `0x14002ced0`

## callees

- `0x1400054a0`
- `0x140008eac`
- `0x140014060`
- `0x1400142fc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001423f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001423f`
- `ntoskrnl!IofCompleteRequest` at `0x1400141fc`
- `ntoskrnl!IofCompleteRequest` at `0x1400141fc`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400141e1`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400141e1`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001422b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001422b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400140d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001424e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400140d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001424e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014127`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014284`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014127`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014284`
- `ntoskrnl!KeSetEvent` at `0x140014273`
- `ntoskrnl!KeSetEvent` at `0x140014273`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400140a5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400140a5`
- `ntoskrnl!IoCancelIrp` at `0x1400141c7`
- `ntoskrnl!IoCancelIrp` at `0x1400141c7`

## pseudocode

```c
__int64 __fastcall LockSyncSendSetFeatureControlRequestForFunctionSuspend(__int64 a1, _QWORD *a2, unsigned int a3)
{
  NTSTATUS v6; // ebp
  KIRQL v7; // al
  _QWORD **v8; // rsi
  BOOL v9; // r15d
  KIRQL v10; // bl
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  PIRP *v13; // r14
  unsigned int *v14; // rbx
  int v15; // edx
  struct _KEVENT *Event; // [rsp+88h] [rbp+10h]

  Event = (struct _KEVENT *)(a2 + 54);
  v6 = KeWaitForSingleObject(a2 + 54, Executive, 0, 0, 0);
  if ( !v6 )
  {
    v6 = SyncSendSetFeatureControlRequestForFunctionSuspend(a1, a2, a3);
    v7 = KeAcquireSpinLockRaiseToDpc(a2 + 57);
    v8 = (_QWORD **)(a2 + 58);
    v9 = v6 >= 0;
    while ( 1 )
    {
      v10 = v7;
      v11 = *v8;
      if ( *v8 == v8 )
        break;
      if ( (_QWORD **)v11[1] != v8 || (v12 = (_QWORD *)*v11, *(_QWORD **)(*v11 + 8LL) != v11) )
        __fastfail(3u);
      *v8 = v12;
      v13 = (PIRP *)(v11 - 2);
      v12[1] = v8;
      KeReleaseSpinLock(a2 + 57, v10);
      v14 = (unsigned int *)(v13 + 1);
      if ( !v9 || *v14 != a3 )
      {
        if ( (int)SyncSendSetFeatureControlRequestForFunctionSuspend(a1, a2, *v14) >= 0 )
        {
          a3 = *v14;
          v9 = 1;
        }
        else if ( (*v13)->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v15) = 2;
            WPP_RECORDER_SF_qq(
              a2[49],
              v15,
              3,
              85,
              (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
              a2[28],
              *(_QWORD *)(a2[48] + 40LL));
          }
          IoCancelIrp(*(PIRP *)(a2[48] + 40LL));
        }
      }
      PoStartNextPowerIrp(*v13);
      (*v13)->IoStatus.Status = 0;
      IofCompleteRequest(*v13, 0);
      UsbcReleaseRemoveLock(a1, *v13);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), *v13, 0x20u);
      ExFreePoolWithTag(v13, 0x43627355u);
      v7 = KeAcquireSpinLockRaiseToDpc(a2 + 57);
    }
    KeSetEvent(Event, 0, 0);
    KeReleaseSpinLock(a2 + 57, v10);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140014060  mov     [rsp+arg_10], rbx
0x140014065  mov     [rsp+arg_0], rcx
0x14001406a  push    rbp
0x14001406b  push    rsi
0x14001406c  push    rdi
0x14001406d  push    r12
0x14001406f  push    r13
0x140014071  push    r14
0x140014073  push    r15
0x140014075  sub     rsp, 40h
0x140014079  lea     r14, [rdx+1B0h]
0x140014080  mov     [rsp+78h+Timeout], 0; Timeout
0x140014089  mov     r12d, r8d
0x14001408c  mov     [rsp+78h+Event], r14
0x140014094  mov     rdi, rdx
0x140014097  mov     rbx, rcx
0x14001409a  mov     rcx, r14; Object
0x14001409d  xor     r9d, r9d; Alertable
0x1400140a0  xor     r8d, r8d; WaitMode
0x1400140a3  xor     edx, edx; WaitReason
0x1400140a5  call    cs:__imp_KeWaitForSingleObject
0x1400140ac  nop     dword ptr [rax+rax+00h]
0x1400140b1  mov     ebp, eax
0x1400140b3  test    eax, eax
0x1400140b5  jnz     loc_140014290
0x1400140bb  mov     r8d, r12d
0x1400140be  mov     rdx, rdi
0x1400140c1  mov     rcx, rbx
0x1400140c4  call    SyncSendSetFeatureControlRequestForFunctionSuspend
0x1400140c9  lea     r13, [rdi+1C8h]
0x1400140d0  mov     ebp, eax
0x1400140d2  mov     rcx, r13; SpinLock
0x1400140d5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400140dc  nop     dword ptr [rax+rax+00h]
0x1400140e1  mov     r15d, ebp
0x1400140e4  lea     rsi, [rdi+1D0h]
0x1400140eb  not     r15d
0x1400140ee  shr     r15d, 1Fh
0x1400140f2  mov     bl, al
0x1400140f4  mov     rax, [rsi]
0x1400140f7  cmp     rax, rsi
0x1400140fa  jz      loc_140014266
0x140014100  cmp     [rax+8], rsi
0x140014104  jnz     loc_14001425F
0x14001410a  mov     rcx, [rax]
0x14001410d  cmp     [rcx+8], rax
0x140014111  jnz     loc_14001425F
0x140014117  mov     [rsi], rcx
0x14001411a  lea     r14, [rax-10h]
0x14001411e  mov     [rcx+8], rsi
0x140014122  mov     dl, bl; NewIrql
0x140014124  mov     rcx, r13; SpinLock
0x140014127  call    cs:__imp_KeReleaseSpinLock
0x14001412e  nop     dword ptr [rax+rax+00h]
0x140014133  lea     rbx, [r14+8]
0x140014137  test    r15d, r15d
0x14001413a  jz      short loc_140014145
0x14001413c  cmp     [rbx], r12d
0x14001413f  jz      loc_1400141DE
0x140014145  mov     r8d, [rbx]
0x140014148  mov     rdx, rdi
0x14001414b  mov     rcx, [rsp+78h+arg_0]
0x140014153  call    SyncSendSetFeatureControlRequestForFunctionSuspend
0x140014158  test    eax, eax
0x14001415a  jns     short loc_1400141D5
0x14001415c  mov     rax, [r14]
0x14001415f  mov     rcx, [rax+0B8h]
0x140014166  cmp     dword ptr [rcx+18h], 1
0x14001416a  jz      short loc_1400141DE
0x14001416c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140014173  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001417a  jz      short loc_1400141BC
0x14001417c  mov     rax, [rdi+180h]
0x140014183  mov     r9d, 55h ; 'U'
0x140014189  mov     rcx, [rdi+188h]
0x140014190  mov     dl, 2
0x140014192  mov     rax, [rax+28h]
0x140014196  lea     r8d, [r9-52h]
0x14001419a  mov     [rsp+78h+var_48], rax
0x14001419f  mov     rax, [rdi+0E0h]
0x1400141a6  mov     [rsp+78h+var_50], rax
0x1400141ab  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x1400141b2  mov     [rsp+78h+Timeout], rax
0x1400141b7  call    WPP_RECORDER_SF_qq
0x1400141bc  mov     rcx, [rdi+180h]
0x1400141c3  mov     rcx, [rcx+28h]; Irp
0x1400141c7  call    cs:__imp_IoCancelIrp
0x1400141ce  nop     dword ptr [rax+rax+00h]
0x1400141d3  jmp     short loc_1400141DE
0x1400141d5  mov     r12d, [rbx]
0x1400141d8  mov     r15d, 1
0x1400141de  mov     rcx, [r14]; Irp
0x1400141e1  call    cs:__imp_PoStartNextPowerIrp
0x1400141e8  nop     dword ptr [rax+rax+00h]
0x1400141ed  mov     rax, [r14]
0x1400141f0  xor     edx, edx; PriorityBoost
0x1400141f2  mov     dword ptr [rax+30h], 0
0x1400141f9  mov     rcx, [r14]; Irp
0x1400141fc  call    cs:__imp_IofCompleteRequest
0x140014203  nop     dword ptr [rax+rax+00h]
0x140014208  mov     rbx, [rsp+78h+arg_0]
0x140014210  mov     rdx, [r14]
0x140014213  mov     rcx, rbx
0x140014216  call    UsbcReleaseRemoveLock
0x14001421b  mov     rdx, [r14]; Tag
0x14001421e  lea     rcx, [rbx+0C8h]; RemoveLock
0x140014225  mov     r8d, 20h ; ' '; RemlockSize
0x14001422b  call    cs:__imp_IoReleaseRemoveLockEx
0x140014232  nop     dword ptr [rax+rax+00h]
0x140014237  mov     edx, 43627355h; Tag
0x14001423c  mov     rcx, r14; P
0x14001423f  call    cs:__imp_ExFreePoolWithTag
0x140014246  nop     dword ptr [rax+rax+00h]
0x14001424b  mov     rcx, r13; SpinLock
0x14001424e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014255  nop     dword ptr [rax+rax+00h]
0x14001425a  jmp     loc_1400140F2
0x14001425f  mov     ecx, 3
0x140014264  int     29h; Win8: RtlFailFast(ecx)
0x140014266  mov     rcx, [rsp+78h+Event]; Event
0x14001426e  xor     r8d, r8d; Wait
0x140014271  xor     edx, edx; Increment
0x140014273  call    cs:__imp_KeSetEvent
0x14001427a  nop     dword ptr [rax+rax+00h]
0x14001427f  mov     dl, bl; NewIrql
0x140014281  mov     rcx, r13; SpinLock
0x140014284  call    cs:__imp_KeReleaseSpinLock
0x14001428b  nop     dword ptr [rax+rax+00h]
0x140014290  mov     rbx, [rsp+78h+arg_10]
0x140014298  mov     eax, ebp
0x14001429a  add     rsp, 40h
0x14001429e  pop     r15
0x1400142a0  pop     r14
0x1400142a2  pop     r13
0x1400142a4  pop     r12
0x1400142a6  pop     rdi
0x1400142a7  pop     rsi
0x1400142a8  pop     rbp
0x1400142a9  retn
```
