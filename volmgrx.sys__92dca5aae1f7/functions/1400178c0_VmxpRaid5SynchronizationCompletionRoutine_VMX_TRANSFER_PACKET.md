# VmxpRaid5SynchronizationCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x1400178c0`
- end: `0x140017ac0`
- name: `?VmxpRaid5SynchronizationCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `512`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140003cf0`
- `0x14000fa68`
- `0x140010ac4`
- `0x1400178c0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017928`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017928`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001796a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400179c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017a21`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017a4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001796a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400179c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017a21`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017a4b`
- `ntoskrnl!KeSetEvent` at `0x14001797f`
- `ntoskrnl!KeSetEvent` at `0x14001797f`

## pseudocode

```c
void __fastcall VmxpRaid5SynchronizationCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  int v3; // r14d
  __int64 v4; // rsi
  unsigned __int64 v5; // rbp
  KIRQL v6; // al
  KIRQL v7; // r12
  __int64 v8; // rcx
  _QWORD *v9; // rdx
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  unsigned __int64 v12; // rdx

  v1 = *((_QWORD *)a1 + 28);
  v2 = *((_QWORD *)a1 + 6);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *(_QWORD *)(v1 + 96);
  *((_DWORD *)a1 + 42) = 0;
  VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(
    (VMX_OVERLAPPED_IO_MANAGER *)(v2 + 136),
    (struct VMX_OVERLAP_TRANSFER_PACKET *)v4);
  if ( v3 < 0 )
    VMX_IO_RAID5::PropagateFaultTolerantChanges((VMX_IO_RAID5 *)v2);
  v5 = (*(_QWORD *)(v1 + 56) >> *(_DWORD *)(v2 + 124)) / (unsigned __int64)(unsigned int)(*(_DWORD *)(v2 + 56) - 1);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 24));
  v7 = v6;
  if ( v3 < 0 )
    *(_BYTE *)(v1 + 66) = 1;
  else
    *(_QWORD *)(v1 + 56) = (++v5 * (unsigned int)(*(_DWORD *)(v2 + 56) - 1)) << *(_DWORD *)(v2 + 124);
  if ( *(_BYTE *)(v1 + 65) )
  {
    *(_WORD *)(v1 + 64) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), v6);
    KeSetEvent((PRKEVENT)(v1 + 72), 0, 0);
    return;
  }
  if ( *(_BYTE *)(v1 + 66) )
  {
    v8 = *(_QWORD *)(v1 + 8);
    if ( *(_QWORD *)(v8 + 8) == v1 + 8 )
    {
      v9 = *(_QWORD **)(v1 + 16);
      if ( *v9 == v1 + 8 )
      {
        *v9 = v8;
        *(_QWORD *)(v8 + 8) = v9;
        KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), v6);
LABEL_12:
        (**(void (__fastcall ***)(__int64, __int64))v1)(v1, 1);
        return;
      }
    }
    goto LABEL_17;
  }
  if ( *(_QWORD *)(v1 + 56) >= *(_QWORD *)(v1 + 48) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
    v10 = *(_QWORD *)(v1 + 8);
    if ( *(_QWORD *)(v10 + 8) == v1 + 8 )
    {
      v11 = *(_QWORD **)(v1 + 16);
      if ( *v11 == v1 + 8 )
      {
        *v11 = v10;
        *(_QWORD *)(v10 + 8) = v11;
        KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), v7);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 24LL))(v1);
        goto LABEL_12;
      }
    }
LABEL_17:
    __fastfail(3u);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), v6);
  v12 = v5 % *(unsigned int *)(v2 + 56);
  if ( !*(_BYTE *)(v2 + 260) )
    LODWORD(v12) = *(_DWORD *)(v2 + 56) - v12 - 1;
  *(_QWORD *)(v4 + 16) = v5 << *(_DWORD *)(v2 + 124);
  *(_QWORD *)(v4 + 48) = *(_QWORD *)(*(_QWORD *)(v2 + 48) + 8LL * (unsigned int)v12);
  *(_DWORD *)(v4 + 240) = v12;
  *(_BYTE *)(v4 + 82) = 1;
  *(_QWORD *)(v4 + 56) = 0;
  *(_BYTE *)(v4 + 264) = 0;
  VMX_IO_RAID5::ReconstructStripe((KSPIN_LOCK *)v2, (struct VMX_RAID5_TRANSFER_PACKET *)v4, 1);
}

```

## disassembly

```asm
0x1400178c0  push    rbx
0x1400178c2  push    rbp
0x1400178c3  push    rsi
0x1400178c4  push    rdi
0x1400178c5  push    r12
0x1400178c7  push    r14
0x1400178c9  push    r15
0x1400178cb  sub     rsp, 20h
0x1400178cf  mov     rbx, [rcx+0E0h]
0x1400178d6  mov     rdi, [rcx+30h]
0x1400178da  mov     r14d, [rcx+60h]
0x1400178de  mov     rsi, [rbx+60h]
0x1400178e2  mov     dword ptr [rcx+0A8h], 0
0x1400178ec  mov     rdx, rsi; struct VMX_OVERLAP_TRANSFER_PACKET *
0x1400178ef  lea     rcx, [rdi+88h]; this
0x1400178f6  call    ?ReleaseIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@@Z; VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(VMX_OVERLAP_TRANSFER_PACKET *)
0x1400178fb  test    r14d, r14d
0x1400178fe  jns     short loc_140017908
0x140017900  mov     rcx, rdi; this
0x140017903  call    ?PropagateFaultTolerantChanges@VMX_IO_RAID5@@QEAAXXZ; VMX_IO_RAID5::PropagateFaultTolerantChanges(void)
0x140017908  mov     r8d, [rdi+38h]
0x14001790c  lea     r15, [rdi+18h]
0x140017910  mov     ecx, [rdi+7Ch]
0x140017913  dec     r8d
0x140017916  mov     rax, [rbx+38h]
0x14001791a  xor     edx, edx
0x14001791c  shr     rax, cl
0x14001791f  mov     rcx, r15; SpinLock
0x140017922  div     r8
0x140017925  mov     rbp, rax
0x140017928  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001792f  nop     dword ptr [rax+rax+00h]
0x140017934  mov     r12b, al
0x140017937  test    r14d, r14d
0x14001793a  js      short loc_140017954
0x14001793c  mov     edx, [rdi+38h]
0x14001793f  inc     rbp
0x140017942  mov     ecx, [rdi+7Ch]
0x140017945  dec     edx
0x140017947  imul    rdx, rbp
0x14001794b  shl     rdx, cl
0x14001794e  mov     [rbx+38h], rdx
0x140017952  jmp     short loc_140017958
0x140017954  mov     byte ptr [rbx+42h], 1
0x140017958  cmp     byte ptr [rbx+41h], 0
0x14001795c  jz      short loc_140017990
0x14001795e  mov     dl, r12b; NewIrql
0x140017961  mov     word ptr [rbx+40h], 0
0x140017967  mov     rcx, r15; SpinLock
0x14001796a  call    cs:__imp_KeReleaseSpinLock
0x140017971  nop     dword ptr [rax+rax+00h]
0x140017976  lea     rcx, [rbx+48h]; Event
0x14001797a  xor     r8d, r8d; Wait
0x14001797d  xor     edx, edx; Increment
0x14001797f  call    cs:__imp_KeSetEvent
0x140017986  nop     dword ptr [rax+rax+00h]
0x14001798b  jmp     loc_140017AB0
0x140017990  cmp     byte ptr [rbx+42h], 0
0x140017994  jz      short loc_1400179E5
0x140017996  lea     rax, [rbx+8]
0x14001799a  mov     rcx, [rax]
0x14001799d  cmp     [rcx+8], rax
0x1400179a1  jnz     loc_140017A3E
0x1400179a7  mov     rdx, [rax+8]
0x1400179ab  cmp     [rdx], rax
0x1400179ae  jnz     loc_140017A3E
0x1400179b4  mov     [rdx], rcx
0x1400179b7  mov     [rcx+8], rdx
0x1400179bb  mov     dl, r12b; NewIrql
0x1400179be  mov     rcx, r15; SpinLock
0x1400179c1  call    cs:__imp_KeReleaseSpinLock
0x1400179c8  nop     dword ptr [rax+rax+00h]
0x1400179cd  mov     rax, [rbx]
0x1400179d0  mov     edx, 1
0x1400179d5  mov     rcx, rbx
0x1400179d8  mov     rax, [rax]
0x1400179db  call    _guard_dispatch_icall
0x1400179e0  jmp     loc_140017AB0
0x1400179e5  mov     rax, [rbx+30h]
0x1400179e9  cmp     [rbx+38h], rax
0x1400179ed  jb      short loc_140017A45
0x1400179ef  mov     rax, [rbx]
0x1400179f2  mov     rcx, rbx
0x1400179f5  mov     rax, [rax+10h]
0x1400179f9  call    _guard_dispatch_icall
0x1400179fe  lea     rax, [rbx+8]
0x140017a02  mov     rdx, [rax]
0x140017a05  cmp     [rdx+8], rax
0x140017a09  jnz     short loc_140017A3E
0x140017a0b  mov     rcx, [rax+8]
0x140017a0f  cmp     [rcx], rax
0x140017a12  jnz     short loc_140017A3E
0x140017a14  mov     [rcx], rdx
0x140017a17  mov     [rdx+8], rcx
0x140017a1b  mov     dl, r12b; NewIrql
0x140017a1e  mov     rcx, r15; SpinLock
0x140017a21  call    cs:__imp_KeReleaseSpinLock
0x140017a28  nop     dword ptr [rax+rax+00h]
0x140017a2d  mov     rax, [rbx]
0x140017a30  mov     rcx, rbx
0x140017a33  mov     rax, [rax+18h]
0x140017a37  call    _guard_dispatch_icall
0x140017a3c  jmp     short loc_1400179CD
0x140017a3e  mov     ecx, 3
0x140017a43  int     29h; Win8: RtlFailFast(ecx)
0x140017a45  mov     dl, r12b; NewIrql
0x140017a48  mov     rcx, r15; SpinLock
0x140017a4b  call    cs:__imp_KeReleaseSpinLock
0x140017a52  nop     dword ptr [rax+rax+00h]
0x140017a57  mov     ecx, [rdi+38h]
0x140017a5a  xor     edx, edx
0x140017a5c  mov     rax, rbp
0x140017a5f  div     rcx
0x140017a62  cmp     byte ptr [rdi+104h], 0
0x140017a69  jnz     short loc_140017A70
0x140017a6b  sub     ecx, edx
0x140017a6d  lea     edx, [rcx-1]
0x140017a70  mov     ecx, [rdi+7Ch]
0x140017a73  shl     rbp, cl
0x140017a76  mov     rcx, rdi; this
0x140017a79  mov     [rsi+10h], rbp
0x140017a7d  mov     rax, [rdi+30h]
0x140017a81  mov     r8d, edx
0x140017a84  mov     r8, [rax+r8*8]
0x140017a88  mov     [rsi+30h], r8
0x140017a8c  mov     r8b, 1; unsigned __int8
0x140017a8f  mov     [rsi+0F0h], edx
0x140017a95  mov     rdx, rsi; struct VMX_RAID5_TRANSFER_PACKET *
0x140017a98  mov     byte ptr [rsi+52h], 1
0x140017a9c  mov     qword ptr [rsi+38h], 0
0x140017aa4  mov     byte ptr [rsi+108h], 0
0x140017aab  call    ?ReconstructStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@E@Z; VMX_IO_RAID5::ReconstructStripe(VMX_RAID5_TRANSFER_PACKET *,uchar)
0x140017ab0  add     rsp, 20h
0x140017ab4  pop     r15
0x140017ab6  pop     r14
0x140017ab8  pop     r12
0x140017aba  pop     rdi
0x140017abb  pop     rsi
0x140017abc  pop     rbp
0x140017abd  pop     rbx
0x140017abe  retn
```
