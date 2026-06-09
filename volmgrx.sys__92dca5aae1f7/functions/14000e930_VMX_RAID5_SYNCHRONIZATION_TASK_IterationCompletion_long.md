# VMX_RAID5_SYNCHRONIZATION_TASK::IterationCompletion(long)

- ea: `0x14000e930`
- end: `0x14000ea30`
- name: `?IterationCompletion@VMX_RAID5_SYNCHRONIZATION_TASK@@QEAAXJ@Z`
- size: `256`
- prototype: `void __fastcall(VMX_RAID5_SYNCHRONIZATION_TASK *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140011c20`
- `0x140017ad0`

## callees

- `0x140003bd8`
- `0x14000d0dc`
- `0x14000e930`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e94e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e94e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e9c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e9c1`

## pseudocode

```c
void __fastcall VMX_RAID5_SYNCHRONIZATION_TASK::IterationCompletion(VMX_RAID5_SYNCHRONIZATION_TASK *this, int a2)
{
  __int64 v2; // rdi
  KIRQL v5; // al
  unsigned __int64 v6; // r9
  int v7; // ecx
  KIRQL v8; // r11
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  struct VMX_LOG_TRANSFER_PACKET *v11; // rdx

  v2 = *((_QWORD *)this + 4);
  if ( a2 < 0 )
  {
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 24));
    v6 = *(unsigned int *)(v2 + 56);
    v7 = *(_DWORD *)(v2 + 124);
    v8 = v5;
    *(_BYTE *)(v2 + 261) = 0;
    v9 = (*((_QWORD *)this + 7) >> v7) / (unsigned __int64)(unsigned int)(v6 - 1) % v6;
    if ( !*(_BYTE *)(v2 + 260) )
      LODWORD(v9) = v6 - v9 - 1;
    if ( !*(_DWORD *)(*(_QWORD *)(v2 + 112) + 24LL * (unsigned int)v9 + 16)
      && VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)v2, v9, 1) )
    {
      ++*(_DWORD *)(*((_QWORD *)this + 13) + 168LL);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), v8);
  }
  *(_DWORD *)(*((_QWORD *)this + 13) + 96LL) = a2;
  *(_QWORD *)(*((_QWORD *)this + 13) + 40LL) = VmxpRaid5SynchronizationCompletionRoutine;
  v10 = *((_QWORD *)this + 13);
  if ( *(_DWORD *)(v10 + 168) )
  {
    v11 = (struct VMX_LOG_TRANSFER_PACKET *)*((_QWORD *)this + 13);
    *(_QWORD *)(v10 + 152) = VmxpRaid5LogDetachOperation;
    *(_QWORD *)(v10 + 160) = VmxpRaid5LogDetachCompletion;
    VMX_LOG::QueueLogPacket(*(VMX_LOG **)(v2 + 232), v11);
  }
  else
  {
    (*(void (**)(void))(v10 + 40))();
  }
}

```

## disassembly

```asm
0x14000e930  push    rbx
0x14000e932  push    rbp
0x14000e933  push    rsi
0x14000e934  push    rdi
0x14000e935  sub     rsp, 28h
0x14000e939  mov     rdi, [rcx+20h]
0x14000e93d  mov     esi, edx
0x14000e93f  mov     rbx, rcx
0x14000e942  test    edx, edx
0x14000e944  jns     loc_14000E9CD
0x14000e94a  lea     rcx, [rdi+18h]; SpinLock
0x14000e94e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e955  nop     dword ptr [rax+rax+00h]
0x14000e95a  mov     r9d, [rdi+38h]
0x14000e95e  xor     edx, edx
0x14000e960  mov     ecx, [rdi+7Ch]
0x14000e963  mov     r11b, al
0x14000e966  mov     byte ptr [rdi+105h], 0
0x14000e96d  mov     rax, [rbx+38h]
0x14000e971  shr     rax, cl
0x14000e974  lea     r8d, [r9-1]
0x14000e978  div     r8
0x14000e97b  xor     edx, edx
0x14000e97d  div     r9
0x14000e980  cmp     byte ptr [rdi+104h], 0
0x14000e987  jnz     short loc_14000E990
0x14000e989  sub     r9d, edx
0x14000e98c  lea     edx, [r9-1]; unsigned int
0x14000e990  mov     eax, edx
0x14000e992  lea     rcx, [rax+rax*2]
0x14000e996  mov     rax, [rdi+70h]
0x14000e99a  cmp     dword ptr [rax+rcx*8+10h], 0
0x14000e99f  jnz     short loc_14000E9BA
0x14000e9a1  mov     r8b, 1; unsigned __int8
0x14000e9a4  mov     rcx, rdi; this
0x14000e9a7  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x14000e9ac  test    al, al
0x14000e9ae  jz      short loc_14000E9BA
0x14000e9b0  mov     rax, [rbx+68h]
0x14000e9b4  inc     dword ptr [rax+0A8h]
0x14000e9ba  mov     dl, r11b; NewIrql
0x14000e9bd  lea     rcx, [rdi+18h]; SpinLock
0x14000e9c1  call    cs:__imp_KeReleaseSpinLock
0x14000e9c8  nop     dword ptr [rax+rax+00h]
0x14000e9cd  mov     rax, [rbx+68h]
0x14000e9d1  lea     rcx, ?VmxpRaid5SynchronizationCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5SynchronizationCompletionRoutine(VMX_TRANSFER_PACKET *)
0x14000e9d8  mov     [rax+60h], esi
0x14000e9db  mov     rax, [rbx+68h]
0x14000e9df  mov     [rax+28h], rcx
0x14000e9e3  mov     rcx, [rbx+68h]
0x14000e9e7  cmp     dword ptr [rcx+0A8h], 0
0x14000e9ee  jbe     short loc_14000EA1D
0x14000e9f0  lea     rax, ?VmxpRaid5LogDetachOperation@@YAJPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VmxpRaid5LogDetachOperation(VMX_LOG_TRANSFER_PACKET *)
0x14000e9f7  mov     rdx, rcx; struct VMX_LOG_TRANSFER_PACKET *
0x14000e9fa  mov     [rcx+98h], rax
0x14000ea01  lea     rax, ?VmxpRaid5LogDetachCompletion@@YAXPEAVVMX_LOG_TRANSFER_PACKET@@J@Z; VmxpRaid5LogDetachCompletion(VMX_LOG_TRANSFER_PACKET *,long)
0x14000ea08  mov     [rcx+0A0h], rax
0x14000ea0f  mov     rcx, [rdi+0E8h]; this
0x14000ea16  call    ?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)
0x14000ea1b  jmp     short loc_14000EA26
0x14000ea1d  mov     rax, [rcx+28h]
0x14000ea21  call    _guard_dispatch_icall
0x14000ea26  add     rsp, 28h
0x14000ea2a  pop     rdi
0x14000ea2b  pop     rsi
0x14000ea2c  pop     rbp
0x14000ea2d  pop     rbx
0x14000ea2e  retn
```
