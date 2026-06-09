# VMX_IO_MIRROR::PropagateIncompleteRegenerationDetaches(void)

- ea: `0x14000fad8`
- end: `0x14000fc91`
- name: `?PropagateIncompleteRegenerationDetaches@VMX_IO_MIRROR@@QEAAXXZ`
- size: `441`
- prototype: `void __fastcall(KSPIN_LOCK *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140039d00`

## callees

- `0x140002470`
- `0x140003f04`
- `0x14000d078`
- `0x14000fad8`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fafe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fafe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fbf6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fc77`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fbf6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fc77`
- `ntoskrnl!KeInitializeEvent` at `0x14000fc0c`
- `ntoskrnl!KeInitializeEvent` at `0x14000fc0c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fc50`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fc50`

## pseudocode

```c
void __fastcall VMX_IO_MIRROR::PropagateIncompleteRegenerationDetaches(KSPIN_LOCK *this)
{
  KSPIN_LOCK *v1; // rbp
  KIRQL v3; // r14
  char v4; // r8
  unsigned int v5; // ecx
  KSPIN_LOCK v6; // rax
  _BYTE *v7; // rax
  _BYTE *v8; // rbx
  unsigned int v9; // esi
  KSPIN_LOCK v10; // rax
  struct _KEVENT Event; // [rsp+30h] [rbp-58h] BYREF

  v1 = this + 3;
  memset(&Event, 0, sizeof(Event));
  v3 = KeAcquireSpinLockRaiseToDpc(this + 3);
  v4 = 0;
  v5 = 0;
  if ( !*((_DWORD *)this + 14) )
    goto LABEL_17;
  do
  {
    v6 = this[12];
    if ( *(_BYTE *)(v6 + 40LL * v5 + 26) )
    {
      if ( *(_DWORD *)(v6 + 40LL * v5 + 16) )
        *(_BYTE *)(v6 + 40LL * v5 + 26) = 0;
      else
        v4 = 1;
    }
    ++v5;
  }
  while ( v5 < *((_DWORD *)this + 14) );
  if ( v4 && (v7 = VMX_TRANSFER_PACKET::operator new(0x128u), (v8 = v7) != 0) )
  {
    *((_QWORD *)v7 + 4) = 0;
    v9 = 0;
    *((_QWORD *)v7 + 3) = 0;
    v7[83] = 0;
    *((_WORD *)v7 + 66) = 0;
    *((_QWORD *)v7 + 27) = 0;
    v7[177] = 0;
    *(_QWORD *)v7 = &VMX_RAID5_TRANSFER_PACKET::`vftable';
    *((_WORD *)v7 + 136) = 0;
    v7[274] = 0;
    for ( *((_DWORD *)v7 + 42) = 0; v9 < *((_DWORD *)this + 14); ++v9 )
    {
      v10 = this[12];
      if ( *(_BYTE *)(v10 + 40LL * v9 + 26) )
      {
        *(_BYTE *)(v10 + 40LL * v9 + 26) = 0;
      }
      else if ( !*(_DWORD *)(v10 + 40LL * v9 + 16) )
      {
        if ( VMX_IO_MIRROR::DetachFaultTolerantMember((VMX_IO_MIRROR *)this, v9, 1) )
          ++*((_DWORD *)v8 + 42);
      }
    }
    KeReleaseSpinLock(v1, v3);
    KeInitializeEvent(&Event, NotificationEvent, 0);
    *((_QWORD *)v8 + 6) = this;
    *((_QWORD *)v8 + 28) = &Event;
    *((_QWORD *)v8 + 5) = VmxpPropagateIncompleteRegenerationDetachesCompletionRoutine;
    VMX_IO_MIRROR::QueueLogPacketDetach((VMX_IO_MIRROR *)this, (struct VMX_LOG_TRANSFER_PACKET *)v8);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    (**(void (__fastcall ***)(_BYTE *, __int64))v8)(v8, 1);
  }
  else
  {
LABEL_17:
    KeReleaseSpinLock(v1, v3);
  }
}

```

## disassembly

```asm
0x14000fad8  push    rbx
0x14000fada  push    rbp
0x14000fadb  push    rsi
0x14000fadc  push    rdi
0x14000fadd  push    r14
0x14000fadf  push    r15
0x14000fae1  sub     rsp, 58h
0x14000fae5  lea     rbp, [rcx+18h]
0x14000fae9  mov     rdi, rcx
0x14000faec  xorps   xmm0, xmm0
0x14000faef  xor     eax, eax
0x14000faf1  mov     rcx, rbp; SpinLock
0x14000faf4  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000faf9  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14000fafe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fb05  nop     dword ptr [rax+rax+00h]
0x14000fb0a  xor     r15d, r15d
0x14000fb0d  mov     r14b, al
0x14000fb10  mov     r8b, r15b
0x14000fb13  mov     ecx, r15d
0x14000fb16  cmp     [rdi+38h], r15d
0x14000fb1a  jbe     loc_14000FC71
0x14000fb20  mov     eax, ecx
0x14000fb22  lea     rdx, [rax+rax*4]
0x14000fb26  mov     rax, [rdi+60h]
0x14000fb2a  cmp     [rax+rdx*8+1Ah], r15b
0x14000fb2f  jz      short loc_14000FB42
0x14000fb31  cmp     [rax+rdx*8+10h], r15d
0x14000fb36  jz      short loc_14000FB3F
0x14000fb38  mov     [rax+rdx*8+1Ah], r15b
0x14000fb3d  jmp     short loc_14000FB42
0x14000fb3f  mov     r8b, 1
0x14000fb42  inc     ecx
0x14000fb44  cmp     ecx, [rdi+38h]
0x14000fb47  jb      short loc_14000FB20
0x14000fb49  test    r8b, r8b
0x14000fb4c  jz      loc_14000FC71
0x14000fb52  mov     ecx, 128h; unsigned __int64
0x14000fb57  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x14000fb5c  mov     rbx, rax
0x14000fb5f  test    rax, rax
0x14000fb62  jz      loc_14000FC71
0x14000fb68  mov     [rax+20h], r15
0x14000fb6c  mov     esi, r15d
0x14000fb6f  mov     [rax+18h], r15
0x14000fb73  mov     [rax+53h], r15b
0x14000fb77  mov     [rax+84h], r15w
0x14000fb7f  mov     [rax+0D8h], r15
0x14000fb86  mov     [rax+0B1h], r15b
0x14000fb8d  lea     rax, ??_7VMX_RAID5_TRANSFER_PACKET@@6B@; const VMX_RAID5_TRANSFER_PACKET::`vftable'
0x14000fb94  mov     [rbx], rax
0x14000fb97  mov     [rbx+110h], r15w
0x14000fb9f  mov     [rbx+112h], r15b
0x14000fba6  mov     [rbx+0A8h], r15d
0x14000fbad  cmp     [rdi+38h], r15d
0x14000fbb1  jbe     short loc_14000FBF0
0x14000fbb3  mov     eax, esi
0x14000fbb5  lea     rcx, [rax+rax*4]
0x14000fbb9  mov     rax, [rdi+60h]
0x14000fbbd  cmp     [rax+rcx*8+1Ah], r15b
0x14000fbc2  jz      short loc_14000FBCB
0x14000fbc4  mov     [rax+rcx*8+1Ah], r15b
0x14000fbc9  jmp     short loc_14000FBE9
0x14000fbcb  cmp     [rax+rcx*8+10h], r15d
0x14000fbd0  jnz     short loc_14000FBE9
0x14000fbd2  mov     r8b, 1; unsigned __int8
0x14000fbd5  mov     edx, esi; unsigned int
0x14000fbd7  mov     rcx, rdi; this
0x14000fbda  call    ?DetachFaultTolerantMember@VMX_IO_MIRROR@@QEAAEKE@Z; VMX_IO_MIRROR::DetachFaultTolerantMember(ulong,uchar)
0x14000fbdf  test    al, al
0x14000fbe1  jz      short loc_14000FBE9
0x14000fbe3  inc     dword ptr [rbx+0A8h]
0x14000fbe9  inc     esi
0x14000fbeb  cmp     esi, [rdi+38h]
0x14000fbee  jb      short loc_14000FBB3
0x14000fbf0  mov     dl, r14b; NewIrql
0x14000fbf3  mov     rcx, rbp; SpinLock
0x14000fbf6  call    cs:__imp_KeReleaseSpinLock
0x14000fbfd  nop     dword ptr [rax+rax+00h]
0x14000fc02  xor     r8d, r8d; State
0x14000fc05  lea     rcx, [rsp+88h+Event]; Event
0x14000fc0a  xor     edx, edx; Type
0x14000fc0c  call    cs:__imp_KeInitializeEvent
0x14000fc13  nop     dword ptr [rax+rax+00h]
0x14000fc18  lea     rax, [rsp+88h+Event]
0x14000fc1d  mov     [rbx+30h], rdi
0x14000fc21  mov     [rbx+0E0h], rax
0x14000fc28  mov     rdx, rbx; struct VMX_LOG_TRANSFER_PACKET *
0x14000fc2b  lea     rax, ?VmxpPropagateIncompleteRegenerationDetachesCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpPropagateIncompleteRegenerationDetachesCompletionRoutine(VMX_TRANSFER_PACKET *)
0x14000fc32  mov     rcx, rdi; this
0x14000fc35  mov     [rbx+28h], rax
0x14000fc39  call    ?QueueLogPacketDetach@VMX_IO_MIRROR@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::QueueLogPacketDetach(VMX_LOG_TRANSFER_PACKET *)
0x14000fc3e  xor     r9d, r9d; Alertable
0x14000fc41  mov     [rsp+88h+Timeout], r15; Timeout
0x14000fc46  xor     r8d, r8d; WaitMode
0x14000fc49  lea     rcx, [rsp+88h+Event]; Object
0x14000fc4e  xor     edx, edx; WaitReason
0x14000fc50  call    cs:__imp_KeWaitForSingleObject
0x14000fc57  nop     dword ptr [rax+rax+00h]
0x14000fc5c  mov     rax, [rbx]
0x14000fc5f  mov     edx, 1
0x14000fc64  mov     rcx, rbx
0x14000fc67  mov     rax, [rax]
0x14000fc6a  call    _guard_dispatch_icall
0x14000fc6f  jmp     short loc_14000FC83
0x14000fc71  mov     dl, r14b; NewIrql
0x14000fc74  mov     rcx, rbp; SpinLock
0x14000fc77  call    cs:__imp_KeReleaseSpinLock
0x14000fc7e  nop     dword ptr [rax+rax+00h]
0x14000fc83  add     rsp, 58h
0x14000fc87  pop     r15
0x14000fc89  pop     r14
0x14000fc8b  pop     rdi
0x14000fc8c  pop     rsi
0x14000fc8d  pop     rbp
0x14000fc8e  pop     rbx
0x14000fc8f  retn
```
