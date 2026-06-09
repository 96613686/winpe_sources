# VmxpMirrorConsolidationCompletionRoutine(void *,long)

- ea: `0x140007930`
- end: `0x140007a75`
- name: `?VmxpMirrorConsolidationCompletionRoutine@@YAXPEAXJ@Z`
- size: `325`
- prototype: `void(void *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140003f04`
- `0x140007828`
- `0x140007930`
- `0x14000d078`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007955`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007955`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007a03`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007a03`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000798c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000798c`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14000796f`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14000796f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400079cd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400079cd`

## pseudocode

```c
void __fastcall VmxpMirrorConsolidationCompletionRoutine(_QWORD *a1, NTSTATUS a2)
{
  __int64 v2; // rdi
  KSPIN_LOCK *v5; // rbp
  __int64 v6; // rdx
  KSPIN_LOCK v7; // r12
  __int64 v8; // rbx
  int v9; // ebx
  int v10; // ebx
  KIRQL NewIrql; // [rsp+78h] [rbp+10h]

  v2 = a1[28];
  v5 = *(KSPIN_LOCK **)(v2 + 48);
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 88));
  if ( a2 < 0 )
  {
    if ( !FsRtlIsTotalDeviceFailure(a2) || !*(_BYTE *)(v2 + 192) )
      goto LABEL_16;
    KeAcquireSpinLockAtDpcLevel(v5 + 3);
    v6 = *((unsigned int *)a1 + 60);
    v7 = v5[12];
    v8 = 5 * v6;
    if ( *(_DWORD *)(v7 + 40 * v6 + 16) != 4 && VMX_IO_MIRROR::DetachFaultTolerantMember((VMX_IO_MIRROR *)v5, v6, 1) )
      ++*(_DWORD *)(v2 + 168);
    v9 = *(_DWORD *)(v7 + 8 * v8 + 16);
    KeReleaseSpinLockFromDpcLevel(v5 + 3);
    if ( v9 != 4 )
    {
LABEL_16:
      if ( VmxpIsWorseStatus(a2, *(_DWORD *)(v2 + 96)) )
        *(_DWORD *)(v2 + 96) = a2;
    }
  }
  v10 = --*(_DWORD *)(v2 + 128);
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 88), NewIrql);
  (*(void (__fastcall **)(_QWORD *, __int64))*a1)(a1, 1);
  if ( !v10 )
  {
    if ( *(_DWORD *)(v2 + 168) )
    {
      VMX_IO_MIRROR::QueueLogPacketDetach((VMX_IO_MIRROR *)v5, (struct VMX_LOG_TRANSFER_PACKET *)v2);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(v2 + 176))(*(_QWORD *)(v2 + 184), *(unsigned int *)(v2 + 96));
      (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 1);
    }
  }
}

```

## disassembly

```asm
0x140007930  push    rbx
0x140007932  push    rbp
0x140007933  push    rsi
0x140007934  push    rdi
0x140007935  push    r12
0x140007937  push    r13
0x140007939  push    r14
0x14000793b  push    r15
0x14000793d  sub     rsp, 28h
0x140007941  mov     rdi, [rcx+0E0h]
0x140007948  mov     r14, rcx
0x14000794b  mov     esi, edx
0x14000794d  mov     rbp, [rdi+30h]
0x140007951  lea     rcx, [rdi+58h]; SpinLock
0x140007955  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000795c  nop     dword ptr [rax+rax+00h]
0x140007961  mov     [rsp+68h+NewIrql], al
0x140007965  test    esi, esi
0x140007967  jns     loc_1400079EF
0x14000796d  mov     ecx, esi; Status
0x14000796f  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140007976  nop     dword ptr [rax+rax+00h]
0x14000797b  test    al, al
0x14000797d  jz      short loc_1400079DE
0x14000797f  cmp     byte ptr [rdi+0C0h], 0
0x140007986  jz      short loc_1400079DE
0x140007988  lea     rcx, [rbp+18h]; SpinLock
0x14000798c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140007993  nop     dword ptr [rax+rax+00h]
0x140007998  mov     edx, [r14+0F0h]; unsigned int
0x14000799f  mov     r12, [rbp+60h]
0x1400079a3  lea     rbx, [rdx+rdx*4]
0x1400079a7  cmp     dword ptr [r12+rbx*8+10h], 4
0x1400079ad  jz      short loc_1400079C4
0x1400079af  mov     r8b, 1; unsigned __int8
0x1400079b2  mov     rcx, rbp; this
0x1400079b5  call    ?DetachFaultTolerantMember@VMX_IO_MIRROR@@QEAAEKE@Z; VMX_IO_MIRROR::DetachFaultTolerantMember(ulong,uchar)
0x1400079ba  test    al, al
0x1400079bc  jz      short loc_1400079C4
0x1400079be  inc     dword ptr [rdi+0A8h]
0x1400079c4  mov     ebx, [r12+rbx*8+10h]
0x1400079c9  lea     rcx, [rbp+18h]; SpinLock
0x1400079cd  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400079d4  nop     dword ptr [rax+rax+00h]
0x1400079d9  cmp     ebx, 4
0x1400079dc  jz      short loc_1400079EF
0x1400079de  mov     edx, [rdi+60h]; NTSTATUS
0x1400079e1  mov     ecx, esi; Status
0x1400079e3  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x1400079e8  test    al, al
0x1400079ea  jz      short loc_1400079EF
0x1400079ec  mov     [rdi+60h], esi
0x1400079ef  dec     dword ptr [rdi+80h]
0x1400079f5  lea     rcx, [rdi+58h]; SpinLock
0x1400079f9  mov     dl, [rsp+68h+NewIrql]; NewIrql
0x1400079fd  mov     ebx, [rdi+80h]
0x140007a03  call    cs:__imp_KeReleaseSpinLock
0x140007a0a  nop     dword ptr [rax+rax+00h]
0x140007a0f  mov     rax, [r14]
0x140007a12  mov     esi, 1
0x140007a17  mov     edx, esi
0x140007a19  mov     rcx, r14
0x140007a1c  mov     rax, [rax]
0x140007a1f  call    _guard_dispatch_icall
0x140007a24  test    ebx, ebx
0x140007a26  jnz     short loc_140007A63
0x140007a28  cmp     [rdi+0A8h], ebx
0x140007a2e  jbe     short loc_140007A3D
0x140007a30  mov     rdx, rdi; struct VMX_LOG_TRANSFER_PACKET *
0x140007a33  mov     rcx, rbp; this
0x140007a36  call    ?QueueLogPacketDetach@VMX_IO_MIRROR@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::QueueLogPacketDetach(VMX_LOG_TRANSFER_PACKET *)
0x140007a3b  jmp     short loc_140007A63
0x140007a3d  mov     rax, [rdi+0B0h]
0x140007a44  mov     edx, [rdi+60h]
0x140007a47  mov     rcx, [rdi+0B8h]
0x140007a4e  call    _guard_dispatch_icall
0x140007a53  mov     rax, [rdi]
0x140007a56  mov     edx, esi
0x140007a58  mov     rcx, rdi
0x140007a5b  mov     rax, [rax]
0x140007a5e  call    _guard_dispatch_icall
0x140007a63  add     rsp, 28h
0x140007a67  pop     r15
0x140007a69  pop     r14
0x140007a6b  pop     r13
0x140007a6d  pop     r12
0x140007a6f  pop     rdi
0x140007a70  pop     rsi
0x140007a71  pop     rbp
0x140007a72  pop     rbx
0x140007a73  retn
```
