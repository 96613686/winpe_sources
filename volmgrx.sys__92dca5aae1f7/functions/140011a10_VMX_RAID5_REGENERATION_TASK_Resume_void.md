# VMX_RAID5_REGENERATION_TASK::Resume(void)

- ea: `0x140011a10`
- end: `0x140011c11`
- name: `?Resume@VMX_RAID5_REGENERATION_TASK@@UEAAXXZ`
- size: `513`
- prototype: `void __fastcall(VMX_RAID5_REGENERATION_TASK *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000d0dc`
- `0x14000e85c`
- `0x140010ac4`
- `0x140011a10`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011a37`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011acb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011a37`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011acb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011a78`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011b47`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011b72`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011a78`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011b47`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011b72`

## pseudocode

```c
void __fastcall VMX_RAID5_REGENERATION_TASK::Resume(VMX_RAID5_REGENERATION_TASK *this)
{
  __int64 v1; // rdi
  KSPIN_LOCK *v3; // rbp
  KIRQL v4; // di
  VMX_RAID5_REGENERATION_TASK **v5; // r8
  VMX_RAID5_REGENERATION_TASK **v6; // rdx
  unsigned int *v7; // rsi
  KIRQL v8; // r12
  __int64 v9; // r11
  unsigned int v10; // r14d
  char v11; // r15

  v1 = *((_QWORD *)this + 4);
  v3 = (KSPIN_LOCK *)(v1 + 24);
  if ( *((_QWORD *)this + 7) < *((_QWORD *)this + 6) )
  {
    *(_QWORD *)(*((_QWORD *)this + 14) + 48LL) = v1;
    *(_DWORD *)(*((_QWORD *)this + 14) + 168LL) = 0;
    v7 = (unsigned int *)(v1 + 56);
    v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 24));
    if ( *(_BYTE *)(v1 + 264) )
    {
      v9 = *(_QWORD *)(v1 + 112);
      v10 = 0;
      v11 = 1;
      if ( *v7 )
      {
        do
        {
          if ( *(_BYTE *)(v9 + 20) && *(_DWORD *)(v9 + 16) != 4 )
          {
            if ( VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)v1, v10, 1) )
              ++*(_DWORD *)(*((_QWORD *)this + 14) + 168LL);
            else
              v11 = 0;
          }
          ++v10;
          v9 += 24;
        }
        while ( v10 < *v7 );
        if ( !v11 )
        {
          *(_BYTE *)(v1 + 263) = 1;
          KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 24), v8);
          VMX_RAID5_REGENERATION_TASK::IterationCompletion(this, -1073741823);
          return;
        }
      }
      *(_BYTE *)(v1 + 264) = 0;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 24), v8);
    *(_QWORD *)(*((_QWORD *)this + 13) + 16LL) = ((*((_QWORD *)this + 7) >> *(_DWORD *)(v1 + 124))
                                                / (unsigned __int64)(*v7 - 1)) << *(_DWORD *)(v1 + 124);
    *(_DWORD *)(*((_QWORD *)this + 13) + 8LL) = *(_DWORD *)(v1 + 120);
    *(_QWORD *)(*((_QWORD *)this + 13) + 48LL) = *(_QWORD *)(*(_QWORD *)(v1 + 48) + 8LL * *((unsigned int *)this + 24));
    *(_QWORD *)(*((_QWORD *)this + 13) + 56LL) = 0;
    *(_BYTE *)(*((_QWORD *)this + 13) + 82LL) = 1;
    *(_QWORD *)(*((_QWORD *)this + 13) + 232LL) = v1;
    *(_DWORD *)(*((_QWORD *)this + 13) + 240LL) = *((_DWORD *)this + 24);
    *(_BYTE *)(*((_QWORD *)this + 13) + 264LL) = 0;
    VMX_IO_RAID5::ReconstructStripe((KSPIN_LOCK *)v1, *((struct VMX_RAID5_TRANSFER_PACKET **)this + 13), 1);
  }
  else
  {
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 24));
    (*(void (__fastcall **)(VMX_RAID5_REGENERATION_TASK *))(*(_QWORD *)this + 16LL))(this);
    v5 = (VMX_RAID5_REGENERATION_TASK **)*((_QWORD *)this + 1);
    if ( v5[1] != (VMX_RAID5_REGENERATION_TASK *)((char *)this + 8)
      || (v6 = (VMX_RAID5_REGENERATION_TASK **)*((_QWORD *)this + 2),
          *v6 != (VMX_RAID5_REGENERATION_TASK *)((char *)this + 8)) )
    {
      __fastfail(3u);
    }
    *v6 = (VMX_RAID5_REGENERATION_TASK *)v5;
    v5[1] = (VMX_RAID5_REGENERATION_TASK *)v6;
    KeReleaseSpinLock(v3, v4);
    (*(void (__fastcall **)(VMX_RAID5_REGENERATION_TASK *))(*(_QWORD *)this + 24LL))(this);
    (**(void (__fastcall ***)(VMX_RAID5_REGENERATION_TASK *, __int64))this)(this, 1);
  }
}

```

## disassembly

```asm
0x140011a10  push    rbx
0x140011a12  push    rbp
0x140011a13  push    rsi
0x140011a14  push    rdi
0x140011a15  push    r12
0x140011a17  push    r14
0x140011a19  push    r15
0x140011a1b  sub     rsp, 20h
0x140011a1f  mov     rdi, [rcx+20h]
0x140011a23  mov     rbx, rcx
0x140011a26  mov     rax, [rcx+30h]
0x140011a2a  lea     rbp, [rdi+18h]
0x140011a2e  cmp     [rcx+38h], rax
0x140011a32  jb      short loc_140011AB2
0x140011a34  mov     rcx, rbp; SpinLock
0x140011a37  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011a3e  nop     dword ptr [rax+rax+00h]
0x140011a43  mov     rdx, [rbx]
0x140011a46  mov     rcx, rbx
0x140011a49  mov     dil, al
0x140011a4c  mov     rax, [rdx+10h]
0x140011a50  call    _guard_dispatch_icall
0x140011a55  lea     rcx, [rbx+8]
0x140011a59  mov     r8, [rcx]
0x140011a5c  cmp     [r8+8], rcx
0x140011a60  jnz     short loc_140011AAB
0x140011a62  mov     rdx, [rcx+8]
0x140011a66  cmp     [rdx], rcx
0x140011a69  jnz     short loc_140011AAB
0x140011a6b  mov     [rdx], r8
0x140011a6e  mov     rcx, rbp; SpinLock
0x140011a71  mov     [r8+8], rdx
0x140011a75  mov     dl, dil; NewIrql
0x140011a78  call    cs:__imp_KeReleaseSpinLock
0x140011a7f  nop     dword ptr [rax+rax+00h]
0x140011a84  mov     rax, [rbx]
0x140011a87  mov     rcx, rbx
0x140011a8a  mov     rax, [rax+18h]
0x140011a8e  call    _guard_dispatch_icall
0x140011a93  mov     rax, [rbx]
0x140011a96  mov     edx, 1
0x140011a9b  mov     rcx, rbx
0x140011a9e  mov     rax, [rax]
0x140011aa1  call    _guard_dispatch_icall
0x140011aa6  jmp     loc_140011C01
0x140011aab  mov     ecx, 3
0x140011ab0  int     29h; Win8: RtlFailFast(ecx)
0x140011ab2  mov     rax, [rcx+70h]
0x140011ab6  mov     [rax+30h], rdi
0x140011aba  mov     rax, [rcx+70h]
0x140011abe  mov     rcx, rbp; SpinLock
0x140011ac1  mov     dword ptr [rax+0A8h], 0
0x140011acb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011ad2  nop     dword ptr [rax+rax+00h]
0x140011ad7  cmp     byte ptr [rdi+108h], 0
0x140011ade  lea     rsi, [rdi+38h]
0x140011ae2  mov     r12b, al
0x140011ae5  jz      loc_140011B6C
0x140011aeb  mov     r11, [rdi+70h]
0x140011aef  xor     r14d, r14d
0x140011af2  mov     r15b, 1
0x140011af5  cmp     [rsi], r14d
0x140011af8  jbe     short loc_140011B65
0x140011afa  cmp     byte ptr [r11+14h], 0
0x140011aff  jz      short loc_140011B29
0x140011b01  cmp     dword ptr [r11+10h], 4
0x140011b06  jz      short loc_140011B29
0x140011b08  mov     r8b, 1; unsigned __int8
0x140011b0b  mov     edx, r14d; unsigned int
0x140011b0e  mov     rcx, rdi; this
0x140011b11  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x140011b16  test    al, al
0x140011b18  jz      short loc_140011B26
0x140011b1a  mov     rax, [rbx+70h]
0x140011b1e  inc     dword ptr [rax+0A8h]
0x140011b24  jmp     short loc_140011B29
0x140011b26  xor     r15b, r15b
0x140011b29  inc     r14d
0x140011b2c  add     r11, 18h
0x140011b30  cmp     r14d, [rsi]
0x140011b33  jb      short loc_140011AFA
0x140011b35  test    r15b, r15b
0x140011b38  jnz     short loc_140011B65
0x140011b3a  mov     dl, r12b; NewIrql
0x140011b3d  mov     byte ptr [rdi+107h], 1
0x140011b44  mov     rcx, rbp; SpinLock
0x140011b47  call    cs:__imp_KeReleaseSpinLock
0x140011b4e  nop     dword ptr [rax+rax+00h]
0x140011b53  mov     edx, 0C0000001h; int
0x140011b58  mov     rcx, rbx; this
0x140011b5b  call    ?IterationCompletion@VMX_RAID5_REGENERATION_TASK@@QEAAXJ@Z; VMX_RAID5_REGENERATION_TASK::IterationCompletion(long)
0x140011b60  jmp     loc_140011C01
0x140011b65  mov     byte ptr [rdi+108h], 0
0x140011b6c  mov     dl, r12b; NewIrql
0x140011b6f  mov     rcx, rbp; SpinLock
0x140011b72  call    cs:__imp_KeReleaseSpinLock
0x140011b79  nop     dword ptr [rax+rax+00h]
0x140011b7e  mov     ecx, [rdi+7Ch]
0x140011b81  xor     edx, edx
0x140011b83  mov     r8d, [rsi]
0x140011b86  mov     rax, [rbx+38h]
0x140011b8a  dec     r8d
0x140011b8d  shr     rax, cl
0x140011b90  div     r8
0x140011b93  mov     r8b, 1; unsigned __int8
0x140011b96  shl     rax, cl
0x140011b99  mov     rcx, [rbx+68h]
0x140011b9d  mov     [rcx+10h], rax
0x140011ba1  mov     rcx, [rbx+68h]
0x140011ba5  mov     eax, [rdi+78h]
0x140011ba8  mov     [rcx+8], eax
0x140011bab  mov     ecx, [rbx+60h]
0x140011bae  mov     rax, [rdi+30h]
0x140011bb2  mov     rdx, [rbx+68h]
0x140011bb6  mov     rax, [rax+rcx*8]
0x140011bba  mov     rcx, rdi; this
0x140011bbd  mov     [rdx+30h], rax
0x140011bc1  mov     rax, [rbx+68h]
0x140011bc5  mov     qword ptr [rax+38h], 0
0x140011bcd  mov     rax, [rbx+68h]
0x140011bd1  mov     byte ptr [rax+52h], 1
0x140011bd5  mov     rax, [rbx+68h]
0x140011bd9  mov     [rax+0E8h], rdi
0x140011be0  mov     rdx, [rbx+68h]
0x140011be4  mov     eax, [rbx+60h]
0x140011be7  mov     [rdx+0F0h], eax
0x140011bed  mov     rax, [rbx+68h]
0x140011bf1  mov     byte ptr [rax+108h], 0
0x140011bf8  mov     rdx, [rbx+68h]; struct VMX_RAID5_TRANSFER_PACKET *
0x140011bfc  call    ?ReconstructStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@E@Z; VMX_IO_RAID5::ReconstructStripe(VMX_RAID5_TRANSFER_PACKET *,uchar)
0x140011c01  add     rsp, 20h
0x140011c05  pop     r15
0x140011c07  pop     r14
0x140011c09  pop     r12
0x140011c0b  pop     rdi
0x140011c0c  pop     rsi
0x140011c0d  pop     rbp
0x140011c0e  pop     rbx
0x140011c0f  retn
```
