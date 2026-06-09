# VMX_MIRROR_REGENERATION_TASK::IterationCompletion(long)

- ea: `0x14000e784`
- end: `0x14000e854`
- name: `?IterationCompletion@VMX_MIRROR_REGENERATION_TASK@@QEAAXJ@Z`
- size: `208`
- prototype: `void __fastcall(VMX_MIRROR_REGENERATION_TASK *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400116d0`
- `0x140013e50`
- `0x1400141d0`

## callees

- `0x140003f04`
- `0x14000d078`
- `0x14000e784`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e7a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e7a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e7f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e7f8`

## pseudocode

```c
void __fastcall VMX_MIRROR_REGENERATION_TASK::IterationCompletion(VMX_MIRROR_REGENERATION_TASK *this, int a2)
{
  KSPIN_LOCK *v2; // rdi
  __int64 v5; // rsi
  KIRQL i; // r15
  __int64 v7; // rdx
  __int64 v8; // rcx

  v2 = (KSPIN_LOCK *)*((_QWORD *)this + 4);
  if ( a2 < 0 )
  {
    v5 = 0;
    for ( i = KeAcquireSpinLockRaiseToDpc(v2 + 3); (unsigned int)v5 < *((_DWORD *)this + 24); v5 = (unsigned int)(v5 + 1) )
    {
      v7 = *(unsigned int *)(*((_QWORD *)this + 13) + 4 * v5);
      if ( *(_DWORD *)(v2[12] + 40 * v7 + 16) == 2
        && VMX_IO_MIRROR::DetachFaultTolerantMember((VMX_IO_MIRROR *)v2, v7, 1) )
      {
        ++*(_DWORD *)(*((_QWORD *)this + 16) + 168LL);
      }
    }
    KeReleaseSpinLock(v2 + 3, i);
  }
  *(_DWORD *)(*((_QWORD *)this + 16) + 96LL) = a2;
  *(_QWORD *)(*((_QWORD *)this + 16) + 40LL) = VmxpMirrorRegenerationCompletionRoutine;
  v8 = *((_QWORD *)this + 16);
  if ( *(_DWORD *)(v8 + 168) )
    VMX_IO_MIRROR::QueueLogPacketDetach((VMX_IO_MIRROR *)v2, *((struct VMX_LOG_TRANSFER_PACKET **)this + 16));
  else
    (*(void (**)(void))(v8 + 40))();
}

```

## disassembly

```asm
0x14000e784  push    rbx
0x14000e786  push    rbp
0x14000e787  push    rsi
0x14000e788  push    rdi
0x14000e789  push    r14
0x14000e78b  push    r15
0x14000e78d  sub     rsp, 28h
0x14000e791  mov     rdi, [rcx+20h]
0x14000e795  mov     ebp, edx
0x14000e797  mov     rbx, rcx
0x14000e79a  test    edx, edx
0x14000e79c  jns     short loc_14000E804
0x14000e79e  lea     rcx, [rdi+18h]; SpinLock
0x14000e7a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e7a9  nop     dword ptr [rax+rax+00h]
0x14000e7ae  xor     esi, esi
0x14000e7b0  mov     r15b, al
0x14000e7b3  cmp     [rbx+60h], esi
0x14000e7b6  jbe     short loc_14000E7F1
0x14000e7b8  mov     rax, [rbx+68h]
0x14000e7bc  mov     edx, [rax+rsi*4]; unsigned int
0x14000e7bf  mov     rax, [rdi+60h]
0x14000e7c3  lea     rcx, [rdx+rdx*4]
0x14000e7c7  cmp     dword ptr [rax+rcx*8+10h], 2
0x14000e7cc  jnz     short loc_14000E7EA
0x14000e7ce  mov     r8b, 1; unsigned __int8
0x14000e7d1  mov     rcx, rdi; this
0x14000e7d4  call    ?DetachFaultTolerantMember@VMX_IO_MIRROR@@QEAAEKE@Z; VMX_IO_MIRROR::DetachFaultTolerantMember(ulong,uchar)
0x14000e7d9  test    al, al
0x14000e7db  jz      short loc_14000E7EA
0x14000e7dd  mov     rax, [rbx+80h]
0x14000e7e4  inc     dword ptr [rax+0A8h]
0x14000e7ea  inc     esi
0x14000e7ec  cmp     esi, [rbx+60h]
0x14000e7ef  jb      short loc_14000E7B8
0x14000e7f1  mov     dl, r15b; NewIrql
0x14000e7f4  lea     rcx, [rdi+18h]; SpinLock
0x14000e7f8  call    cs:__imp_KeReleaseSpinLock
0x14000e7ff  nop     dword ptr [rax+rax+00h]
0x14000e804  mov     rax, [rbx+80h]
0x14000e80b  lea     rcx, ?VmxpMirrorRegenerationCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRegenerationCompletionRoutine(VMX_TRANSFER_PACKET *)
0x14000e812  mov     [rax+60h], ebp
0x14000e815  mov     rax, [rbx+80h]
0x14000e81c  mov     [rax+28h], rcx
0x14000e820  mov     rcx, [rbx+80h]
0x14000e827  cmp     dword ptr [rcx+0A8h], 0
0x14000e82e  jbe     short loc_14000E83D
0x14000e830  mov     rdx, rcx; struct VMX_LOG_TRANSFER_PACKET *
0x14000e833  mov     rcx, rdi; this
0x14000e836  call    ?QueueLogPacketDetach@VMX_IO_MIRROR@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::QueueLogPacketDetach(VMX_LOG_TRANSFER_PACKET *)
0x14000e83b  jmp     short loc_14000E846
0x14000e83d  mov     rax, [rcx+28h]
0x14000e841  call    _guard_dispatch_icall
0x14000e846  add     rsp, 28h
0x14000e84a  pop     r15
0x14000e84c  pop     r14
0x14000e84e  pop     rdi
0x14000e84f  pop     rsi
0x14000e850  pop     rbp
0x14000e851  pop     rbx
0x14000e852  retn
```
