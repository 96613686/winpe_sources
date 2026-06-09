# VmxpMirrorSynchronizationCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x140005870`
- end: `0x140005a94`
- name: `?VmxpMirrorSynchronizationCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `548`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140005870`
- `0x14000f9f8`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400058aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005a74`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400058aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005a74`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400058d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000595b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400059a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005a0b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400058d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000595b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400059a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005a0b`
- `ntoskrnl!KeSetEvent` at `0x1400058e8`
- `ntoskrnl!KeSetEvent` at `0x1400058e8`

## pseudocode

```c
void __fastcall VmxpMirrorSynchronizationCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rsi
  __int64 v3; // rbp
  KSPIN_LOCK *v4; // r15
  KIRQL v5; // al
  KIRQL v6; // r14
  unsigned int v7; // ecx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // rcx

  v1 = *((_QWORD *)a1 + 28);
  v2 = *((_QWORD *)a1 + 6);
  v3 = *(_QWORD *)(v1 + 96);
  *((_DWORD *)a1 + 42) = 0;
  if ( *((int *)a1 + 24) < 0 )
  {
    VMX_IO_MIRROR::PropagateFaultTolerantChanges((VMX_IO_MIRROR *)v2);
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 24));
    *(_BYTE *)(v1 + 66) = 1;
    v4 = (KSPIN_LOCK *)(v2 + 24);
  }
  else
  {
    v4 = (KSPIN_LOCK *)(v2 + 24);
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 24));
    *(_QWORD *)(v1 + 56) += *(unsigned int *)(v3 + 8);
  }
  v6 = v5;
  if ( *(_BYTE *)(v1 + 65) )
  {
    *(_WORD *)(v1 + 64) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), v5);
    KeSetEvent((PRKEVENT)(v1 + 72), 0, 0);
    return;
  }
  if ( *(_BYTE *)(v1 + 66) )
  {
    v13 = *(_QWORD *)(v1 + 8);
    if ( *(_QWORD *)(v13 + 8) == v1 + 8 )
    {
      v14 = *(_QWORD **)(v1 + 16);
      if ( *v14 == v1 + 8 )
      {
        *v14 = v13;
        *(_QWORD *)(v13 + 8) = v14;
        KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), v5);
        goto LABEL_13;
      }
    }
LABEL_23:
    __fastfail(3u);
  }
  v7 = *(_DWORD *)(v2 + 56);
  v8 = 0;
  v9 = *(_QWORD *)(v2 + 96);
  v10 = 0;
  if ( !v7 )
    goto LABEL_7;
  do
  {
    if ( (*(_DWORD *)(v9 + 16) & 0xFFFFFFFD) == 0 )
      v8 = (unsigned int)(v8 + 1);
    v10 = (unsigned int)(v10 + 1);
    v9 += 40;
  }
  while ( (unsigned int)v10 < v7 );
  if ( (unsigned int)v8 < 2 || *(_QWORD *)(v1 + 56) >= *(_QWORD *)(v1 + 48) )
  {
LABEL_7:
    (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v1 + 16LL))(v1, v8, v9, v10);
    v11 = *(_QWORD *)(v1 + 8);
    if ( *(_QWORD *)(v11 + 8) == v1 + 8 )
    {
      v12 = *(_QWORD **)(v1 + 16);
      if ( *v12 == v1 + 8 )
      {
        *v12 = v11;
        *(_QWORD *)(v11 + 8) = v12;
        KeReleaseSpinLock(v4, v6);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 24LL))(v1);
LABEL_13:
        (**(void (__fastcall ***)(__int64, __int64))v1)(v1, 1);
        return;
      }
    }
    goto LABEL_23;
  }
  KeReleaseSpinLock(v4, v5);
  *(_QWORD *)(v3 + 16) = *(_QWORD *)(v1 + 56);
  v15 = *(_QWORD *)(v1 + 56);
  v16 = *(_QWORD *)(v1 + 48) - v15;
  if ( (unsigned __int64)(v15 + 0x10000) <= *(_QWORD *)(v1 + 48) )
    v16 = 0x10000;
  *(_DWORD *)(v3 + 8) = v16;
  v17 = *(_QWORD *)(v3 + 48);
  *(_QWORD *)(v3 + 56) = 0;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 8LL))(v17, v3);
}

```

## disassembly

```asm
0x140005870  push    rbx
0x140005872  push    rbp
0x140005873  push    rsi
0x140005874  push    rdi
0x140005875  push    r12
0x140005877  push    r14
0x140005879  push    r15
0x14000587b  sub     rsp, 20h
0x14000587f  mov     rbx, [rcx+0E0h]
0x140005886  xor     r12d, r12d
0x140005889  mov     rsi, [rcx+30h]
0x14000588d  mov     rbp, [rbx+60h]
0x140005891  mov     [rcx+0A8h], r12d
0x140005898  cmp     [rcx+60h], r12d
0x14000589c  jl      loc_140005A68
0x1400058a2  lea     rcx, [rsi+18h]; SpinLock
0x1400058a6  lea     r15, [rsi+18h]
0x1400058aa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400058b1  nop     dword ptr [rax+rax+00h]
0x1400058b6  mov     edx, [rbp+8]
0x1400058b9  add     [rbx+38h], rdx
0x1400058bd  movzx   r14d, al
0x1400058c1  cmp     [rbx+41h], r12b
0x1400058c5  jz      short loc_140005904
0x1400058c7  movzx   edx, al; NewIrql
0x1400058ca  mov     [rbx+40h], r12w
0x1400058cf  lea     rcx, [rsi+18h]; SpinLock
0x1400058d3  call    cs:__imp_KeReleaseSpinLock
0x1400058da  nop     dword ptr [rax+rax+00h]
0x1400058df  lea     rcx, [rbx+48h]; Event
0x1400058e3  xor     r8d, r8d; Wait
0x1400058e6  xor     edx, edx; Increment
0x1400058e8  call    cs:__imp_KeSetEvent
0x1400058ef  nop     dword ptr [rax+rax+00h]
0x1400058f4  add     rsp, 20h
0x1400058f8  pop     r15
0x1400058fa  pop     r14
0x1400058fc  pop     r12
0x1400058fe  pop     rdi
0x1400058ff  pop     rsi
0x140005900  pop     rbp
0x140005901  pop     rbx
0x140005902  retn
0x140005904  cmp     [rbx+42h], r12b
0x140005908  jnz     short loc_140005978
0x14000590a  mov     ecx, [rsi+38h]
0x14000590d  mov     edx, r12d
0x140005910  mov     r8, [rsi+60h]
0x140005914  mov     r9d, r12d
0x140005917  test    ecx, ecx
0x140005919  jnz     loc_1400059D5
0x14000591f  mov     rax, [rbx]
0x140005922  mov     rcx, rbx
0x140005925  mov     rax, [rax+10h]
0x140005929  call    _guard_dispatch_icall
0x14000592e  mov     rdx, [rbx+8]
0x140005932  lea     rax, [rbx+8]
0x140005936  cmp     [rdx+8], rax
0x14000593a  jnz     loc_140005A8D
0x140005940  mov     rcx, [rax+8]
0x140005944  cmp     [rcx], rax
0x140005947  jnz     loc_140005A8D
0x14000594d  mov     [rcx], rdx
0x140005950  mov     [rdx+8], rcx
0x140005954  movzx   edx, r14b; NewIrql
0x140005958  mov     rcx, r15; SpinLock
0x14000595b  call    cs:__imp_KeReleaseSpinLock
0x140005962  nop     dword ptr [rax+rax+00h]
0x140005967  mov     rax, [rbx]
0x14000596a  mov     rcx, rbx
0x14000596d  mov     rax, [rax+18h]
0x140005971  call    _guard_dispatch_icall
0x140005976  jmp     short loc_1400059B2
0x140005978  mov     rcx, [rbx+8]
0x14000597c  lea     rax, [rbx+8]
0x140005980  cmp     [rcx+8], rax
0x140005984  jnz     loc_140005A8D
0x14000598a  mov     rdx, [rax+8]
0x14000598e  cmp     [rdx], rax
0x140005991  jnz     loc_140005A8D
0x140005997  mov     [rdx], rcx
0x14000599a  mov     [rcx+8], rdx
0x14000599e  movzx   edx, r14b; NewIrql
0x1400059a2  lea     rcx, [rsi+18h]; SpinLock
0x1400059a6  call    cs:__imp_KeReleaseSpinLock
0x1400059ad  nop     dword ptr [rax+rax+00h]
0x1400059b2  mov     rax, [rbx]
0x1400059b5  mov     edx, 1
0x1400059ba  mov     rcx, rbx
0x1400059bd  mov     rax, [rax]
0x1400059c0  call    _guard_dispatch_icall
0x1400059c5  add     rsp, 20h
0x1400059c9  pop     r15
0x1400059cb  pop     r14
0x1400059cd  pop     r12
0x1400059cf  pop     rdi
0x1400059d0  pop     rsi
0x1400059d1  pop     rbp
0x1400059d2  pop     rbx
0x1400059d3  retn
0x1400059d5  test    dword ptr [r8+10h], 0FFFFFFFDh
0x1400059dd  jnz     short loc_1400059E1
0x1400059df  inc     edx
0x1400059e1  inc     r9d
0x1400059e4  add     r8, 28h ; '('
0x1400059e8  cmp     r9d, ecx
0x1400059eb  jb      short loc_1400059D5
0x1400059ed  cmp     edx, 2
0x1400059f0  jb      loc_14000591F
0x1400059f6  mov     rax, [rbx+30h]
0x1400059fa  cmp     [rbx+38h], rax
0x1400059fe  jnb     loc_14000591F
0x140005a04  movzx   edx, r14b; NewIrql
0x140005a08  mov     rcx, r15; SpinLock
0x140005a0b  call    cs:__imp_KeReleaseSpinLock
0x140005a12  nop     dword ptr [rax+rax+00h]
0x140005a17  mov     rax, [rbx+38h]
0x140005a1b  mov     edx, 10000h
0x140005a20  mov     [rbp+10h], rax
0x140005a24  mov     rax, [rbx+38h]
0x140005a28  mov     r9, [rbx+30h]
0x140005a2c  mov     ecx, r9d
0x140005a2f  sub     ecx, eax
0x140005a31  lea     r8, [rax+10000h]
0x140005a38  cmp     r8, r9
0x140005a3b  cmovbe  ecx, edx
0x140005a3e  mov     rdx, rbp
0x140005a41  mov     [rbp+8], ecx
0x140005a44  mov     rcx, [rbp+30h]
0x140005a48  mov     [rbp+38h], r12
0x140005a4c  mov     rax, [rcx]
0x140005a4f  mov     rax, [rax+8]
0x140005a53  call    _guard_dispatch_icall
0x140005a58  add     rsp, 20h
0x140005a5c  pop     r15
0x140005a5e  pop     r14
0x140005a60  pop     r12
0x140005a62  pop     rdi
0x140005a63  pop     rsi
0x140005a64  pop     rbp
0x140005a65  pop     rbx
0x140005a66  retn
0x140005a68  mov     rcx, rsi; this
0x140005a6b  call    ?PropagateFaultTolerantChanges@VMX_IO_MIRROR@@QEAAXXZ; VMX_IO_MIRROR::PropagateFaultTolerantChanges(void)
0x140005a70  lea     rcx, [rsi+18h]; SpinLock
0x140005a74  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005a7b  nop     dword ptr [rax+rax+00h]
0x140005a80  mov     byte ptr [rbx+42h], 1
0x140005a84  lea     r15, [rsi+18h]
0x140005a88  jmp     loc_1400058BD
0x140005a8d  mov     ecx, 3
0x140005a92  int     29h; Win8: RtlFailFast(ecx)
```
