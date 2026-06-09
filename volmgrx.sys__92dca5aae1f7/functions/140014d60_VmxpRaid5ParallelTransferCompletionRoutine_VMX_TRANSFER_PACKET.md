# VmxpRaid5ParallelTransferCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x140014d60`
- end: `0x140014fb4`
- name: `?VmxpRaid5ParallelTransferCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `596`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140003bd8`
- `0x140007828`
- `0x14000d0dc`
- `0x140010ac4`
- `0x140010c00`
- `0x140014d60`
- `0x140018fcc`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014d8c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014e3f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014f08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014d8c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014e3f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014f08`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014e8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014f42`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014e8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014f42`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140014df0`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140014df0`

## pseudocode

```c
void __fastcall VmxpRaid5ParallelTransferCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  NTSTATUS v1; // ebx
  __int64 v3; // rbp
  __int64 v4; // rdi
  KSPIN_LOCK *v5; // r14
  KIRQL v6; // al
  NTSTATUS v7; // edx
  KIRQL v8; // r15
  __int64 v9; // r8
  KIRQL v10; // al
  __int64 v11; // r9
  KIRQL v12; // r11
  int v13; // ebx

  v1 = *((_DWORD *)a1 + 24);
  v3 = *((_QWORD *)a1 + 29);
  v4 = *((_QWORD *)a1 + 28);
  if ( v1 >= 0 )
  {
    v5 = (KSPIN_LOCK *)(v4 + 88);
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 88));
    v7 = *(_DWORD *)(v4 + 96);
    v8 = v6;
    if ( v7 >= 0 )
      *(_QWORD *)(v4 + 104) += *((_QWORD *)a1 + 13);
    if ( !*((_BYTE *)a1 + 264) || !VmxpIsWorseStatus(v1, v7) )
      goto LABEL_28;
    goto LABEL_27;
  }
  if ( !*((_BYTE *)a1 + 82) || *((_BYTE *)a1 + 264) || v1 == -2147483626 )
  {
LABEL_25:
    v5 = (KSPIN_LOCK *)(v4 + 88);
    v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 88));
    if ( !VmxpIsWorseStatus(v1, *(_DWORD *)(v4 + 96)) )
      goto LABEL_28;
    *(_QWORD *)(v4 + 104) = 0;
LABEL_27:
    *(_DWORD *)(v4 + 96) = v1;
LABEL_28:
    v13 = --*(_DWORD *)(v4 + 128);
    KeReleaseSpinLock(v5, v8);
    (**(void (__fastcall ***)(struct VMX_TRANSFER_PACKET *, __int64))a1)(a1, 1);
    if ( !v13 )
    {
      if ( *(_DWORD *)(v4 + 168) )
      {
        *(_QWORD *)(v4 + 152) = VmxpRaid5LogDetachOperation;
        *(_QWORD *)(v4 + 160) = VmxpRaid5LogDetachCompletion;
        VMX_LOG::QueueLogPacket(*(VMX_LOG **)(v3 + 232), (struct VMX_LOG_TRANSFER_PACKET *)v4);
      }
      else
      {
        (*(void (__fastcall **)(__int64))(v4 + 40))(v4);
      }
    }
    return;
  }
  if ( !FsRtlIsTotalDeviceFailure(v1) )
  {
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
    {
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 23, v9, v3, v1);
    }
    if ( *((_QWORD *)a1 + 3) )
    {
      *((_BYTE *)a1 + 264) = 1;
      VMX_IO_RAID5::RecoverReadStripe((VMX_IO_RAID5 *)v3, a1, 1u);
      return;
    }
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 22, v9, v3, v1);
  }
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 24));
  v11 = *((unsigned int *)a1 + 60);
  v12 = v10;
  if ( *(_DWORD *)(*(_QWORD *)(v3 + 112) + 24 * v11 + 16) != 4
    && VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)v3, v11, 1u) )
  {
    ++*(_DWORD *)(*((_QWORD *)a1 + 32) + 168LL);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 24), v12);
  VMX_IO_RAID5::ReconstructStripe((VMX_IO_RAID5 *)v3, a1, 1u);
}

```

## disassembly

```asm
0x140014d60  push    rbx
0x140014d62  push    rbp
0x140014d63  push    rsi
0x140014d64  push    rdi
0x140014d65  push    r14
0x140014d67  push    r15
0x140014d69  sub     rsp, 38h
0x140014d6d  mov     ebx, [rcx+60h]
0x140014d70  mov     rsi, rcx
0x140014d73  mov     rbp, [rcx+0E8h]
0x140014d7a  mov     rdi, [rcx+0E0h]
0x140014d81  test    ebx, ebx
0x140014d83  js      short loc_140014DCB
0x140014d85  lea     r14, [rdi+58h]
0x140014d89  mov     rcx, r14; SpinLock
0x140014d8c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014d93  nop     dword ptr [rax+rax+00h]
0x140014d98  mov     edx, [rdi+60h]; NTSTATUS
0x140014d9b  mov     r15b, al
0x140014d9e  test    edx, edx
0x140014da0  js      short loc_140014DAA
0x140014da2  mov     rcx, [rsi+68h]
0x140014da6  add     [rdi+68h], rcx
0x140014daa  cmp     byte ptr [rsi+108h], 0
0x140014db1  jz      loc_140014F30
0x140014db7  mov     ecx, ebx; Status
0x140014db9  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x140014dbe  test    al, al
0x140014dc0  jz      loc_140014F30
0x140014dc6  jmp     loc_140014F2D
0x140014dcb  cmp     byte ptr [rcx+52h], 0
0x140014dcf  jz      loc_140014F01
0x140014dd5  cmp     byte ptr [rcx+108h], 0
0x140014ddc  jnz     loc_140014F01
0x140014de2  cmp     ebx, 80000016h
0x140014de8  jz      loc_140014F01
0x140014dee  mov     ecx, ebx; Status
0x140014df0  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140014df7  nop     dword ptr [rax+rax+00h]
0x140014dfc  test    al, al
0x140014dfe  jz      loc_140014EA9
0x140014e04  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e0b  lea     rax, WPP_GLOBAL_Control
0x140014e12  cmp     rcx, rax
0x140014e15  jz      short loc_140014E3B
0x140014e17  test    dword ptr [rcx+2Ch], 1000h
0x140014e1e  jz      short loc_140014E3B
0x140014e20  cmp     byte ptr [rcx+29h], 3
0x140014e24  jb      short loc_140014E3B
0x140014e26  mov     rcx, [rcx+18h]
0x140014e2a  mov     edx, 16h
0x140014e2f  mov     r9, rbp
0x140014e32  mov     [rsp+68h+var_48], ebx
0x140014e36  call    WPP_SF_qd
0x140014e3b  lea     rcx, [rbp+18h]; SpinLock
0x140014e3f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014e46  nop     dword ptr [rax+rax+00h]
0x140014e4b  mov     r9d, [rsi+0F0h]
0x140014e52  mov     r11b, al
0x140014e55  mov     rcx, [rbp+70h]
0x140014e59  lea     rdx, [r9+r9*2]
0x140014e5d  cmp     dword ptr [rcx+rdx*8+10h], 4
0x140014e62  jz      short loc_140014E83
0x140014e64  mov     r8b, 1; unsigned __int8
0x140014e67  mov     edx, r9d; unsigned int
0x140014e6a  mov     rcx, rbp; this
0x140014e6d  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x140014e72  test    al, al
0x140014e74  jz      short loc_140014E83
0x140014e76  mov     rax, [rsi+100h]
0x140014e7d  inc     dword ptr [rax+0A8h]
0x140014e83  mov     dl, r11b; NewIrql
0x140014e86  lea     rcx, [rbp+18h]; SpinLock
0x140014e8a  call    cs:__imp_KeReleaseSpinLock
0x140014e91  nop     dword ptr [rax+rax+00h]
0x140014e96  mov     r8b, 1; unsigned __int8
0x140014e99  mov     rdx, rsi; struct VMX_RAID5_TRANSFER_PACKET *
0x140014e9c  mov     rcx, rbp; this
0x140014e9f  call    ?ReconstructStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@E@Z; VMX_IO_RAID5::ReconstructStripe(VMX_RAID5_TRANSFER_PACKET *,uchar)
0x140014ea4  jmp     loc_140014FA6
0x140014ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x140014eb0  lea     rax, WPP_GLOBAL_Control
0x140014eb7  cmp     rcx, rax
0x140014eba  jz      short loc_140014EE0
0x140014ebc  test    dword ptr [rcx+2Ch], 1000h
0x140014ec3  jz      short loc_140014EE0
0x140014ec5  cmp     byte ptr [rcx+29h], 3
0x140014ec9  jb      short loc_140014EE0
0x140014ecb  mov     rcx, [rcx+18h]
0x140014ecf  mov     edx, 17h
0x140014ed4  mov     r9, rbp
0x140014ed7  mov     [rsp+68h+var_48], ebx
0x140014edb  call    WPP_SF_qd
0x140014ee0  cmp     qword ptr [rsi+18h], 0
0x140014ee5  jz      short loc_140014F01
0x140014ee7  mov     r8b, 1; unsigned __int8
0x140014eea  mov     byte ptr [rsi+108h], 1
0x140014ef1  mov     rdx, rsi; struct VMX_RAID5_TRANSFER_PACKET *
0x140014ef4  mov     rcx, rbp; this
0x140014ef7  call    ?RecoverReadStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@E@Z; VMX_IO_RAID5::RecoverReadStripe(VMX_RAID5_TRANSFER_PACKET *,uchar)
0x140014efc  jmp     loc_140014FA6
0x140014f01  lea     r14, [rdi+58h]
0x140014f05  mov     rcx, r14; SpinLock
0x140014f08  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014f0f  nop     dword ptr [rax+rax+00h]
0x140014f14  mov     edx, [rdi+60h]; NTSTATUS
0x140014f17  mov     ecx, ebx; Status
0x140014f19  mov     r15b, al
0x140014f1c  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x140014f21  test    al, al
0x140014f23  jz      short loc_140014F30
0x140014f25  mov     qword ptr [rdi+68h], 0
0x140014f2d  mov     [rdi+60h], ebx
0x140014f30  dec     dword ptr [rdi+80h]
0x140014f36  mov     dl, r15b; NewIrql
0x140014f39  mov     ebx, [rdi+80h]
0x140014f3f  mov     rcx, r14; SpinLock
0x140014f42  call    cs:__imp_KeReleaseSpinLock
0x140014f49  nop     dword ptr [rax+rax+00h]
0x140014f4e  mov     rax, [rsi]
0x140014f51  mov     edx, 1
0x140014f56  mov     rcx, rsi
0x140014f59  mov     rax, [rax]
0x140014f5c  call    _guard_dispatch_icall
0x140014f61  test    ebx, ebx
0x140014f63  jnz     short loc_140014FA6
0x140014f65  cmp     [rdi+0A8h], ebx
0x140014f6b  jbe     short loc_140014F9A
0x140014f6d  lea     rax, ?VmxpRaid5LogDetachOperation@@YAJPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VmxpRaid5LogDetachOperation(VMX_LOG_TRANSFER_PACKET *)
0x140014f74  mov     rdx, rdi; struct VMX_LOG_TRANSFER_PACKET *
0x140014f77  mov     [rdi+98h], rax
0x140014f7e  lea     rax, ?VmxpRaid5LogDetachCompletion@@YAXPEAVVMX_LOG_TRANSFER_PACKET@@J@Z; VmxpRaid5LogDetachCompletion(VMX_LOG_TRANSFER_PACKET *,long)
0x140014f85  mov     [rdi+0A0h], rax
0x140014f8c  mov     rcx, [rbp+0E8h]; this
0x140014f93  call    ?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)
0x140014f98  jmp     short loc_140014FA6
0x140014f9a  mov     rax, [rdi+28h]
0x140014f9e  mov     rcx, rdi
0x140014fa1  call    _guard_dispatch_icall
0x140014fa6  add     rsp, 38h
0x140014faa  pop     r15
0x140014fac  pop     r14
0x140014fae  pop     rdi
0x140014faf  pop     rsi
0x140014fb0  pop     rbp
0x140014fb1  pop     rbx
0x140014fb2  retn
```
