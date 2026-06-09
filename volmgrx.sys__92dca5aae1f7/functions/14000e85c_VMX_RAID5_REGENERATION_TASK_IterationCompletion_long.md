# VMX_RAID5_REGENERATION_TASK::IterationCompletion(long)

- ea: `0x14000e85c`
- end: `0x14000e927`
- name: `?IterationCompletion@VMX_RAID5_REGENERATION_TASK@@QEAAXJ@Z`
- size: `203`
- prototype: `void __fastcall(VMX_RAID5_REGENERATION_TASK *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140011a10`
- `0x140016f10`

## callees

- `0x140003bd8`
- `0x14000d0dc`
- `0x14000e85c`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e876`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e876`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e8b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e8b8`

## pseudocode

```c
void __fastcall VMX_RAID5_REGENERATION_TASK::IterationCompletion(VMX_RAID5_REGENERATION_TASK *this, int a2)
{
  __int64 v2; // rdi
  KIRQL v5; // al
  __int64 v6; // rdx
  KIRQL v7; // r11
  __int64 v8; // rcx
  struct VMX_LOG_TRANSFER_PACKET *v9; // rdx

  v2 = *((_QWORD *)this + 4);
  if ( a2 < 0 )
  {
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 24));
    v6 = *((unsigned int *)this + 24);
    v7 = v5;
    if ( *(_DWORD *)(*(_QWORD *)(v2 + 112) + 24 * v6 + 16) == 2
      && VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)v2, v6, 1) )
    {
      ++*(_DWORD *)(*((_QWORD *)this + 14) + 168LL);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), v7);
  }
  *(_DWORD *)(*((_QWORD *)this + 14) + 96LL) = a2;
  *(_QWORD *)(*((_QWORD *)this + 14) + 40LL) = VmxpRaid5RegenerationCompletionRoutine;
  v8 = *((_QWORD *)this + 14);
  if ( *(_DWORD *)(v8 + 168) )
  {
    v9 = (struct VMX_LOG_TRANSFER_PACKET *)*((_QWORD *)this + 14);
    *(_QWORD *)(v8 + 152) = VmxpRaid5LogDetachOperation;
    *(_QWORD *)(v8 + 160) = VmxpRaid5LogDetachCompletion;
    VMX_LOG::QueueLogPacket(*(VMX_LOG **)(v2 + 232), v9);
  }
  else
  {
    (*(void (**)(void))(v8 + 40))();
  }
}

```

## disassembly

```asm
0x14000e85c  push    rbx
0x14000e85e  push    rbp
0x14000e85f  push    rsi
0x14000e860  push    rdi
0x14000e861  sub     rsp, 28h
0x14000e865  mov     rdi, [rcx+20h]
0x14000e869  mov     esi, edx
0x14000e86b  mov     rbx, rcx
0x14000e86e  test    edx, edx
0x14000e870  jns     short loc_14000E8C4
0x14000e872  lea     rcx, [rdi+18h]; SpinLock
0x14000e876  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e87d  nop     dword ptr [rax+rax+00h]
0x14000e882  mov     edx, [rbx+60h]; unsigned int
0x14000e885  mov     r11b, al
0x14000e888  mov     r8, [rdi+70h]
0x14000e88c  lea     r9, [rdx+rdx*2]
0x14000e890  cmp     dword ptr [r8+r9*8+10h], 2
0x14000e896  jnz     short loc_14000E8B1
0x14000e898  mov     r8b, 1; unsigned __int8
0x14000e89b  mov     rcx, rdi; this
0x14000e89e  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x14000e8a3  test    al, al
0x14000e8a5  jz      short loc_14000E8B1
0x14000e8a7  mov     rax, [rbx+70h]
0x14000e8ab  inc     dword ptr [rax+0A8h]
0x14000e8b1  mov     dl, r11b; NewIrql
0x14000e8b4  lea     rcx, [rdi+18h]; SpinLock
0x14000e8b8  call    cs:__imp_KeReleaseSpinLock
0x14000e8bf  nop     dword ptr [rax+rax+00h]
0x14000e8c4  mov     rax, [rbx+70h]
0x14000e8c8  lea     rcx, ?VmxpRaid5RegenerationCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RegenerationCompletionRoutine(VMX_TRANSFER_PACKET *)
0x14000e8cf  mov     [rax+60h], esi
0x14000e8d2  mov     rax, [rbx+70h]
0x14000e8d6  mov     [rax+28h], rcx
0x14000e8da  mov     rcx, [rbx+70h]
0x14000e8de  cmp     dword ptr [rcx+0A8h], 0
0x14000e8e5  jbe     short loc_14000E914
0x14000e8e7  lea     rax, ?VmxpRaid5LogDetachOperation@@YAJPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VmxpRaid5LogDetachOperation(VMX_LOG_TRANSFER_PACKET *)
0x14000e8ee  mov     rdx, rcx; struct VMX_LOG_TRANSFER_PACKET *
0x14000e8f1  mov     [rcx+98h], rax
0x14000e8f8  lea     rax, ?VmxpRaid5LogDetachCompletion@@YAXPEAVVMX_LOG_TRANSFER_PACKET@@J@Z; VmxpRaid5LogDetachCompletion(VMX_LOG_TRANSFER_PACKET *,long)
0x14000e8ff  mov     [rcx+0A0h], rax
0x14000e906  mov     rcx, [rdi+0E8h]; this
0x14000e90d  call    ?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)
0x14000e912  jmp     short loc_14000E91D
0x14000e914  mov     rax, [rcx+28h]
0x14000e918  call    _guard_dispatch_icall
0x14000e91d  add     rsp, 28h
0x14000e921  pop     rdi
0x14000e922  pop     rsi
0x14000e923  pop     rbp
0x14000e924  pop     rbx
0x14000e925  retn
```
