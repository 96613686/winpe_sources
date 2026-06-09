# VMX_RAID5_SYNCHRONIZATION_TASK::Resume(void)

- ea: `0x140011c20`
- end: `0x140011e3f`
- name: `?Resume@VMX_RAID5_SYNCHRONIZATION_TASK@@UEAAXXZ`
- size: `543`
- prototype: `void __fastcall(VMX_RAID5_SYNCHRONIZATION_TASK *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000d0dc`
- `0x14000e930`
- `0x140010ac4`
- `0x140011c20`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011c47`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011cdb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011c47`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011cdb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c88`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011d57`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011d82`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c88`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011d57`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011d82`

## pseudocode

```c
void __fastcall VMX_RAID5_SYNCHRONIZATION_TASK::Resume(VMX_RAID5_SYNCHRONIZATION_TASK *this)
{
  __int64 v1; // rdi
  KSPIN_LOCK *v3; // rbp
  KIRQL v4; // di
  VMX_RAID5_SYNCHRONIZATION_TASK **v5; // r8
  VMX_RAID5_SYNCHRONIZATION_TASK **v6; // rdx
  unsigned int *v7; // rsi
  KIRQL v8; // r12
  __int64 v9; // r11
  unsigned int v10; // r14d
  char v11; // r15
  int v12; // ecx
  unsigned __int64 v13; // rdx
  unsigned int v14; // r10d

  v1 = *((_QWORD *)this + 4);
  v3 = (KSPIN_LOCK *)(v1 + 24);
  if ( *((_QWORD *)this + 7) < *((_QWORD *)this + 6) )
  {
    *(_QWORD *)(*((_QWORD *)this + 13) + 48LL) = v1;
    *(_DWORD *)(*((_QWORD *)this + 13) + 168LL) = 0;
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
              ++*(_DWORD *)(*((_QWORD *)this + 13) + 168LL);
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
          VMX_RAID5_SYNCHRONIZATION_TASK::IterationCompletion(this, -1073741823);
          return;
        }
      }
      *(_BYTE *)(v1 + 264) = 0;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 24), v8);
    v12 = *(_DWORD *)(v1 + 124);
    v13 = (*((_QWORD *)this + 7) >> v12) / (unsigned __int64)(*v7 - 1) % *v7;
    v14 = v13;
    if ( !*(_BYTE *)(v1 + 260) )
      v14 = *v7 - v13 - 1;
    *(_QWORD *)(*((_QWORD *)this + 12) + 16LL) = ((*((_QWORD *)this + 7) >> v12) / (unsigned __int64)(*v7 - 1)) << v12;
    *(_DWORD *)(*((_QWORD *)this + 12) + 8LL) = *(_DWORD *)(v1 + 120);
    *(_QWORD *)(*((_QWORD *)this + 12) + 48LL) = *(_QWORD *)(*(_QWORD *)(v1 + 48) + 8LL * v14);
    *(_QWORD *)(*((_QWORD *)this + 12) + 56LL) = 0;
    *(_BYTE *)(*((_QWORD *)this + 12) + 82LL) = 1;
    *(_QWORD *)(*((_QWORD *)this + 12) + 232LL) = v1;
    *(_DWORD *)(*((_QWORD *)this + 12) + 240LL) = v14;
    *(_BYTE *)(*((_QWORD *)this + 12) + 264LL) = 0;
    VMX_IO_RAID5::ReconstructStripe((KSPIN_LOCK *)v1, *((struct VMX_RAID5_TRANSFER_PACKET **)this + 12), 1);
  }
  else
  {
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 24));
    (*(void (__fastcall **)(VMX_RAID5_SYNCHRONIZATION_TASK *))(*(_QWORD *)this + 16LL))(this);
    v5 = (VMX_RAID5_SYNCHRONIZATION_TASK **)*((_QWORD *)this + 1);
    if ( v5[1] != (VMX_RAID5_SYNCHRONIZATION_TASK *)((char *)this + 8)
      || (v6 = (VMX_RAID5_SYNCHRONIZATION_TASK **)*((_QWORD *)this + 2),
          *v6 != (VMX_RAID5_SYNCHRONIZATION_TASK *)((char *)this + 8)) )
    {
      __fastfail(3u);
    }
    *v6 = (VMX_RAID5_SYNCHRONIZATION_TASK *)v5;
    v5[1] = (VMX_RAID5_SYNCHRONIZATION_TASK *)v6;
    KeReleaseSpinLock(v3, v4);
    (*(void (__fastcall **)(VMX_RAID5_SYNCHRONIZATION_TASK *))(*(_QWORD *)this + 24LL))(this);
    (**(void (__fastcall ***)(VMX_RAID5_SYNCHRONIZATION_TASK *, __int64))this)(this, 1);
  }
}

```

## disassembly

```asm
0x140011c20  push    rbx
0x140011c22  push    rbp
0x140011c23  push    rsi
0x140011c24  push    rdi
0x140011c25  push    r12
0x140011c27  push    r14
0x140011c29  push    r15
0x140011c2b  sub     rsp, 20h
0x140011c2f  mov     rdi, [rcx+20h]
0x140011c33  mov     rbx, rcx
0x140011c36  mov     rax, [rcx+30h]
0x140011c3a  lea     rbp, [rdi+18h]
0x140011c3e  cmp     [rcx+38h], rax
0x140011c42  jb      short loc_140011CC2
0x140011c44  mov     rcx, rbp; SpinLock
0x140011c47  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011c4e  nop     dword ptr [rax+rax+00h]
0x140011c53  mov     rdx, [rbx]
0x140011c56  mov     rcx, rbx
0x140011c59  mov     dil, al
0x140011c5c  mov     rax, [rdx+10h]
0x140011c60  call    _guard_dispatch_icall
0x140011c65  lea     rcx, [rbx+8]
0x140011c69  mov     r8, [rcx]
0x140011c6c  cmp     [r8+8], rcx
0x140011c70  jnz     short loc_140011CBB
0x140011c72  mov     rdx, [rcx+8]
0x140011c76  cmp     [rdx], rcx
0x140011c79  jnz     short loc_140011CBB
0x140011c7b  mov     [rdx], r8
0x140011c7e  mov     rcx, rbp; SpinLock
0x140011c81  mov     [r8+8], rdx
0x140011c85  mov     dl, dil; NewIrql
0x140011c88  call    cs:__imp_KeReleaseSpinLock
0x140011c8f  nop     dword ptr [rax+rax+00h]
0x140011c94  mov     rax, [rbx]
0x140011c97  mov     rcx, rbx
0x140011c9a  mov     rax, [rax+18h]
0x140011c9e  call    _guard_dispatch_icall
0x140011ca3  mov     rax, [rbx]
0x140011ca6  mov     edx, 1
0x140011cab  mov     rcx, rbx
0x140011cae  mov     rax, [rax]
0x140011cb1  call    _guard_dispatch_icall
0x140011cb6  jmp     loc_140011E2F
0x140011cbb  mov     ecx, 3
0x140011cc0  int     29h; Win8: RtlFailFast(ecx)
0x140011cc2  mov     rax, [rcx+68h]
0x140011cc6  mov     [rax+30h], rdi
0x140011cca  mov     rax, [rcx+68h]
0x140011cce  mov     rcx, rbp; SpinLock
0x140011cd1  mov     dword ptr [rax+0A8h], 0
0x140011cdb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011ce2  nop     dword ptr [rax+rax+00h]
0x140011ce7  cmp     byte ptr [rdi+108h], 0
0x140011cee  lea     rsi, [rdi+38h]
0x140011cf2  mov     r12b, al
0x140011cf5  jz      loc_140011D7C
0x140011cfb  mov     r11, [rdi+70h]
0x140011cff  xor     r14d, r14d
0x140011d02  mov     r15b, 1
0x140011d05  cmp     [rsi], r14d
0x140011d08  jbe     short loc_140011D75
0x140011d0a  cmp     byte ptr [r11+14h], 0
0x140011d0f  jz      short loc_140011D39
0x140011d11  cmp     dword ptr [r11+10h], 4
0x140011d16  jz      short loc_140011D39
0x140011d18  mov     r8b, 1; unsigned __int8
0x140011d1b  mov     edx, r14d; unsigned int
0x140011d1e  mov     rcx, rdi; this
0x140011d21  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x140011d26  test    al, al
0x140011d28  jz      short loc_140011D36
0x140011d2a  mov     rax, [rbx+68h]
0x140011d2e  inc     dword ptr [rax+0A8h]
0x140011d34  jmp     short loc_140011D39
0x140011d36  xor     r15b, r15b
0x140011d39  inc     r14d
0x140011d3c  add     r11, 18h
0x140011d40  cmp     r14d, [rsi]
0x140011d43  jb      short loc_140011D0A
0x140011d45  test    r15b, r15b
0x140011d48  jnz     short loc_140011D75
0x140011d4a  mov     dl, r12b; NewIrql
0x140011d4d  mov     byte ptr [rdi+107h], 1
0x140011d54  mov     rcx, rbp; SpinLock
0x140011d57  call    cs:__imp_KeReleaseSpinLock
0x140011d5e  nop     dword ptr [rax+rax+00h]
0x140011d63  mov     edx, 0C0000001h; int
0x140011d68  mov     rcx, rbx; this
0x140011d6b  call    ?IterationCompletion@VMX_RAID5_SYNCHRONIZATION_TASK@@QEAAXJ@Z; VMX_RAID5_SYNCHRONIZATION_TASK::IterationCompletion(long)
0x140011d70  jmp     loc_140011E2F
0x140011d75  mov     byte ptr [rdi+108h], 0
0x140011d7c  mov     dl, r12b; NewIrql
0x140011d7f  mov     rcx, rbp; SpinLock
0x140011d82  call    cs:__imp_KeReleaseSpinLock
0x140011d89  nop     dword ptr [rax+rax+00h]
0x140011d8e  mov     r9d, [rsi]
0x140011d91  xor     edx, edx
0x140011d93  mov     r11d, [rdi+7Ch]
0x140011d97  mov     ecx, r11d
0x140011d9a  mov     rax, [rbx+38h]
0x140011d9e  shr     rax, cl
0x140011da1  lea     r8d, [r9-1]
0x140011da5  div     r8
0x140011da8  xor     edx, edx
0x140011daa  mov     r8, rax
0x140011dad  div     r9
0x140011db0  cmp     byte ptr [rdi+104h], 0
0x140011db7  mov     r10, rdx
0x140011dba  jnz     short loc_140011DC3
0x140011dbc  sub     r9d, edx
0x140011dbf  lea     r10d, [r9-1]
0x140011dc3  mov     rax, [rbx+60h]
0x140011dc7  shl     r8, cl
0x140011dca  mov     [rax+10h], r8
0x140011dce  mov     rcx, [rbx+60h]
0x140011dd2  mov     eax, [rdi+78h]
0x140011dd5  mov     r8d, r10d
0x140011dd8  mov     [rcx+8], eax
0x140011ddb  mov     rcx, rdi; this
0x140011dde  mov     rax, [rdi+30h]
0x140011de2  mov     rdx, [rbx+60h]
0x140011de6  mov     rax, [rax+r8*8]
0x140011dea  mov     r8b, 1; unsigned __int8
0x140011ded  mov     [rdx+30h], rax
0x140011df1  mov     rax, [rbx+60h]
0x140011df5  mov     qword ptr [rax+38h], 0
0x140011dfd  mov     rax, [rbx+60h]
0x140011e01  mov     byte ptr [rax+52h], 1
0x140011e05  mov     rax, [rbx+60h]
0x140011e09  mov     [rax+0E8h], rdi
0x140011e10  mov     rax, [rbx+60h]
0x140011e14  mov     [rax+0F0h], r10d
0x140011e1b  mov     rax, [rbx+60h]
0x140011e1f  mov     byte ptr [rax+108h], 0
0x140011e26  mov     rdx, [rbx+60h]; struct VMX_RAID5_TRANSFER_PACKET *
0x140011e2a  call    ?ReconstructStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@E@Z; VMX_IO_RAID5::ReconstructStripe(VMX_RAID5_TRANSFER_PACKET *,uchar)
0x140011e2f  add     rsp, 20h
0x140011e33  pop     r15
0x140011e35  pop     r14
0x140011e37  pop     r12
0x140011e39  pop     rdi
0x140011e3a  pop     rsi
0x140011e3b  pop     rbp
0x140011e3c  pop     rbx
0x140011e3d  retn
```
