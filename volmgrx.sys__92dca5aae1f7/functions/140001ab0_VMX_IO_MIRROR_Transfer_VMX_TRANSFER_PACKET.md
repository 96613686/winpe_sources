# VMX_IO_MIRROR::Transfer(VMX_TRANSFER_PACKET *)

- ea: `0x140001ab0`
- end: `0x140001e8d`
- name: `?Transfer@VMX_IO_MIRROR@@UEAAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `989`
- prototype: `void __fastcall(KSPIN_LOCK *this, struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x140001ab0`
- `0x140001ea0`
- `0x140002470`
- `0x140002650`
- `0x140002b70`
- `0x140003774`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d6a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001e4a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d6a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001e4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001d8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001dcd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e72`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001d8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001dcd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e72`
- `ntoskrnl!ExAllocatePool2` at `0x140001b82`
- `ntoskrnl!ExAllocatePool2` at `0x140001d47`
- `ntoskrnl!ExAllocatePool2` at `0x140001b82`
- `ntoskrnl!ExAllocatePool2` at `0x140001d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001c9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001d26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001c9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001d26`
- `ntoskrnl!IoAllocateMdl` at `0x140001c3b`
- `ntoskrnl!IoAllocateMdl` at `0x140001c3b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140001e1b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140001e1b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001af3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001af3`

## pseudocode

```c
void __fastcall VMX_IO_MIRROR::Transfer(KSPIN_LOCK *this, struct VMX_TRANSFER_PACKET *a2)
{
  unsigned int v2; // esi
  struct _LIST_ENTRY *Flink; // rcx
  struct VMX_MIRROR_TRANSFER_PACKET *v6; // rax
  struct VMX_MIRROR_TRANSFER_PACKET *v7; // rdi
  _QWORD *v8; // rdi
  unsigned int v9; // r12d
  VMX_TRANSFER_PACKET *v10; // rax
  VMX_TRANSFER_PACKET *v11; // r15
  __int64 v12; // rax
  __int64 v13; // rax
  void *v14; // rdi
  ULONG v15; // esi
  PMDL Mdl; // rax
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  void (__fastcall *v18)(struct VMX_TRANSFER_PACKET *); // rax
  _QWORD *v19; // rsi
  struct VMX_MIRROR_TRANSFER_PACKET *v20; // rdx
  __int64 i; // rbx
  void (__fastcall ***v22)(_QWORD, __int64); // rcx
  struct _LIST_ENTRY *Pool2; // rax
  KSPIN_LOCK *v24; // rdi
  KIRQL v25; // al
  char *v26; // r14
  char **v27; // rcx
  char *v28; // rbx
  _QWORD *P; // [rsp+98h] [rbp+10h]

  v2 = 0;
  *((_DWORD *)a2 + 42) = 0;
  if ( *((_BYTE *)a2 + 82) && *((_QWORD *)a2 + 3) )
  {
    Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
    if ( !WPP_MAIN_CB.Queue.ListEntry.Flink )
    {
      Pool2 = (struct _LIST_ENTRY *)ExAllocatePool2(66, 128, 538996054);
      WPP_MAIN_CB.Queue.ListEntry.Flink = Pool2;
      if ( !Pool2 )
        goto LABEL_32;
      ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Pool2, 0, 0, 0x200u, 0x128u, 0x32506D56u, 0x20u);
      Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
    }
    v6 = (struct VMX_MIRROR_TRANSFER_PACKET *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)Flink);
    v7 = v6;
    if ( v6 )
    {
      *((_BYTE *)v6 + 80) = 2;
      *(_QWORD *)v6 = &VMX_RAID5_TRANSFER_PACKET::`vftable';
      *((_QWORD *)v6 + 4) = 0;
      *((_QWORD *)v6 + 3) = 0;
      *((_BYTE *)v6 + 83) = 0;
      *((_WORD *)v6 + 66) = 0;
      *((_QWORD *)v6 + 27) = 0;
      *((_BYTE *)v6 + 177) = 0;
      *((_WORD *)v6 + 136) = 0;
      *((_BYTE *)v6 + 274) = 0;
LABEL_6:
      if ( VMX_IO_MIRROR::LaunchRead((VMX_IO_MIRROR *)this, a2, v7) )
        return;
      v20 = v7;
LABEL_40:
      VMX_IO_MIRROR::RecyclePacket((VMX_IO_MIRROR *)this, v20);
      return;
    }
LABEL_32:
    v24 = this + 3;
    v25 = KeAcquireSpinLockRaiseToDpc(this + 3);
    if ( !*((_BYTE *)this + 160) )
    {
      *((_BYTE *)this + 160) = 1;
      KeReleaseSpinLock(this + 3, v25);
      v7 = (struct VMX_MIRROR_TRANSFER_PACKET *)this[21];
      goto LABEL_6;
    }
    v26 = (char *)(this + 22);
    v27 = (char **)*((_QWORD *)v26 + 1);
    if ( *v27 != v26 )
LABEL_37:
      __fastfail(3u);
LABEL_35:
    v28 = (char *)a2 + 112;
    *(_QWORD *)v28 = v26;
    *((_QWORD *)v28 + 1) = v27;
    *v27 = v28;
    *((_QWORD *)v26 + 1) = v28;
    KeReleaseSpinLock(v24, v25);
    return;
  }
  P = (_QWORD *)ExAllocatePool2(66, 8LL * *((unsigned int *)this + 14), 1934650710);
  v8 = P;
  if ( !P )
    goto LABEL_21;
  v9 = 0;
  while ( 1 )
  {
    if ( v9 >= *((_DWORD *)this + 14) )
    {
      v19 = this + 21;
      goto LABEL_24;
    }
    v10 = (VMX_TRANSFER_PACKET *)VMX_TRANSFER_PACKET::operator new(0x128u);
    v11 = v10;
    if ( !v10 )
      break;
    *((_QWORD *)v10 + 4) = 0;
    *((_QWORD *)v10 + 3) = 0;
    *((_BYTE *)v10 + 83) = 0;
    *((_WORD *)v10 + 66) = 0;
    *((_QWORD *)v10 + 27) = 0;
    *((_BYTE *)v10 + 177) = 0;
    *(_QWORD *)v10 = &VMX_RAID5_TRANSFER_PACKET::`vftable';
    *((_WORD *)v10 + 136) = 0;
    *((_BYTE *)v10 + 274) = 0;
    v12 = v9++;
    v8[v12] = v11;
    v13 = *((_QWORD *)a2 + 3);
    if ( v13 )
    {
      v14 = (void *)(*(_QWORD *)(v13 + 32) + *(unsigned int *)(v13 + 44));
      v15 = *(_DWORD *)(v13 + 40);
      VMX_TRANSFER_PACKET::FreeMdl(v11);
      Mdl = IoAllocateMdl(v14, v15, 0, 0, 0);
      v8 = P;
      v2 = 0;
      *((_QWORD *)v11 + 3) = Mdl;
      if ( !Mdl )
        goto LABEL_16;
      *((_BYTE *)v11 + 132) = 1;
    }
  }
  v8[v9] = 0;
LABEL_16:
  if ( v9 )
  {
    do
    {
      v17 = (void (__fastcall ***)(_QWORD, __int64))v8[v2];
      if ( v17 )
        (**v17)(v17, 1);
      ++v2;
    }
    while ( v2 < v9 );
  }
  ExFreePoolWithTag(v8, 0);
LABEL_21:
  if ( !*((_QWORD *)a2 + 3) )
  {
    v18 = (void (__fastcall *)(struct VMX_TRANSFER_PACKET *))*((_QWORD *)a2 + 5);
    *((_DWORD *)a2 + 24) = -1073741670;
    *((_QWORD *)a2 + 13) = 0;
    v18(a2);
    return;
  }
  v24 = this + 3;
  v25 = KeAcquireSpinLockRaiseToDpc(this + 3);
  if ( *((_BYTE *)this + 160) )
  {
    v26 = (char *)(this + 22);
    v27 = (char **)*((_QWORD *)v26 + 1);
    if ( *v27 != v26 )
      goto LABEL_37;
    goto LABEL_35;
  }
  *((_BYTE *)this + 160) = 1;
  KeReleaseSpinLock(this + 3, v25);
  v8 = this + 21;
  v19 = this + 21;
LABEL_24:
  if ( !VMX_IO_MIRROR::LaunchWrite((VMX_IO_MIRROR *)this, a2, (struct VMX_MIRROR_TRANSFER_PACKET **)v8) )
  {
    v20 = (struct VMX_MIRROR_TRANSFER_PACKET *)*v8;
    if ( *v8 == *v19 )
      goto LABEL_40;
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 14); i = (unsigned int)(i + 1) )
    {
      v22 = (void (__fastcall ***)(_QWORD, __int64))v8[i];
      if ( v22 )
        (**v22)(v22, 1);
    }
    ExFreePoolWithTag(v8, 0);
  }
}

```

## disassembly

```asm
0x140001ab0  push    rbx
0x140001ab2  push    rbp
0x140001ab3  push    rsi
0x140001ab4  push    rdi
0x140001ab5  push    r12
0x140001ab7  push    r13
0x140001ab9  push    r14
0x140001abb  push    r15
0x140001abd  sub     rsp, 48h
0x140001ac1  xor     esi, esi
0x140001ac3  mov     rbx, rdx
0x140001ac6  mov     r14, rcx
0x140001ac9  mov     [rdx+0A8h], esi
0x140001acf  cmp     [rdx+52h], sil
0x140001ad3  jz      loc_140001B70
0x140001ad9  cmp     [rdx+18h], rsi
0x140001add  jz      loc_140001B70
0x140001ae3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; Lookaside
0x140001aea  test    rcx, rcx
0x140001aed  jz      loc_140001D37
0x140001af3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140001afa  nop     dword ptr [rax+rax+00h]
0x140001aff  mov     rdi, rax
0x140001b02  test    rax, rax
0x140001b05  jz      loc_140001D63
0x140001b0b  mov     byte ptr [rax+50h], 2
0x140001b0f  lea     r13, ??_7VMX_RAID5_TRANSFER_PACKET@@6B@; const VMX_RAID5_TRANSFER_PACKET::`vftable'
0x140001b16  mov     [rax], r13
0x140001b19  mov     [rax+20h], rsi
0x140001b1d  mov     [rax+18h], rsi
0x140001b21  mov     [rax+53h], sil
0x140001b25  mov     [rax+84h], si
0x140001b2c  mov     [rax+0D8h], rsi
0x140001b33  mov     [rax+0B1h], sil
0x140001b3a  mov     [rax+110h], si
0x140001b41  mov     [rax+112h], sil
0x140001b48  mov     r8, rdi; struct VMX_MIRROR_TRANSFER_PACKET *
0x140001b4b  mov     rdx, rbx; struct VMX_TRANSFER_PACKET *
0x140001b4e  mov     rcx, r14; this
0x140001b51  call    ?LaunchRead@VMX_IO_MIRROR@@QEAAEPEAVVMX_TRANSFER_PACKET@@PEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::LaunchRead(VMX_TRANSFER_PACKET *,VMX_MIRROR_TRANSFER_PACKET *)
0x140001b56  test    al, al
0x140001b58  jz      loc_140001E33
0x140001b5e  add     rsp, 48h
0x140001b62  pop     r15
0x140001b64  pop     r14
0x140001b66  pop     r13
0x140001b68  pop     r12
0x140001b6a  pop     rdi
0x140001b6b  pop     rsi
0x140001b6c  pop     rbp
0x140001b6d  pop     rbx
0x140001b6e  retn
0x140001b70  mov     edx, [rcx+38h]
0x140001b73  mov     r8d, 73506D56h
0x140001b79  shl     rdx, 3
0x140001b7d  mov     ecx, 42h ; 'B'
0x140001b82  call    cs:__imp_ExAllocatePool2
0x140001b89  nop     dword ptr [rax+rax+00h]
0x140001b8e  mov     [rsp+88h+P], rax
0x140001b96  mov     rdi, rax
0x140001b99  test    rax, rax
0x140001b9c  jz      loc_140001CA8
0x140001ba2  mov     r12d, esi
0x140001ba5  lea     r13, ??_7VMX_RAID5_TRANSFER_PACKET@@6B@; const VMX_RAID5_TRANSFER_PACKET::`vftable'
0x140001bac  cmp     r12d, [r14+38h]
0x140001bb0  jnb     loc_140001CCF
0x140001bb6  mov     ecx, 128h; unsigned __int64
0x140001bbb  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x140001bc0  mov     r15, rax
0x140001bc3  test    rax, rax
0x140001bc6  jz      loc_140001C67
0x140001bcc  mov     [rax+20h], rsi
0x140001bd0  mov     [rax+18h], rsi
0x140001bd4  mov     byte ptr [rax+53h], 0
0x140001bd8  mov     word ptr [rax+84h], 0
0x140001be1  mov     [rax+0D8h], rsi
0x140001be8  mov     byte ptr [rax+0B1h], 0
0x140001bef  mov     [rax], r13
0x140001bf2  mov     word ptr [rax+110h], 0
0x140001bfb  mov     byte ptr [rax+112h], 0
0x140001c02  mov     eax, r12d
0x140001c05  inc     r12d
0x140001c08  mov     [rdi+rax*8], r15
0x140001c0c  mov     rax, [rbx+18h]
0x140001c10  test    rax, rax
0x140001c13  jz      short loc_140001BAC
0x140001c15  mov     edi, [rax+2Ch]
0x140001c18  mov     rcx, r15; this
0x140001c1b  add     rdi, [rax+20h]
0x140001c1f  mov     esi, [rax+28h]
0x140001c22  call    ?FreeMdl@VMX_TRANSFER_PACKET@@AEAAXXZ; VMX_TRANSFER_PACKET::FreeMdl(void)
0x140001c27  xor     r9d, r9d; ChargeQuota
0x140001c2a  mov     [rsp+88h+Irp], 0; Irp
0x140001c33  xor     r8d, r8d; SecondaryBuffer
0x140001c36  mov     edx, esi; Length
0x140001c38  mov     rcx, rdi; VirtualAddress
0x140001c3b  call    cs:__imp_IoAllocateMdl
0x140001c42  nop     dword ptr [rax+rax+00h]
0x140001c47  mov     rdi, [rsp+88h+P]
0x140001c4f  xor     esi, esi
0x140001c51  mov     [r15+18h], rax
0x140001c55  test    rax, rax
0x140001c58  jz      short loc_140001C6E
0x140001c5a  mov     byte ptr [r15+84h], 1
0x140001c62  jmp     loc_140001BAC
0x140001c67  mov     eax, r12d
0x140001c6a  mov     [rdi+rax*8], rsi
0x140001c6e  test    r12d, r12d
0x140001c71  jz      short loc_140001C95
0x140001c73  mov     eax, esi
0x140001c75  mov     rcx, [rdi+rax*8]
0x140001c79  test    rcx, rcx
0x140001c7c  jz      short loc_140001C8E
0x140001c7e  mov     rax, [rcx]
0x140001c81  mov     edx, 1
0x140001c86  mov     rax, [rax]
0x140001c89  call    _guard_dispatch_icall
0x140001c8e  inc     esi
0x140001c90  cmp     esi, r12d
0x140001c93  jb      short loc_140001C73
0x140001c95  xor     edx, edx; Tag
0x140001c97  mov     rcx, rdi; P
0x140001c9a  call    cs:__imp_ExFreePoolWithTag
0x140001ca1  nop     dword ptr [rax+rax+00h]
0x140001ca6  xor     esi, esi
0x140001ca8  cmp     qword ptr [rbx+18h], 0
0x140001cad  jnz     loc_140001E43
0x140001cb3  mov     rax, [rbx+28h]
0x140001cb7  mov     rcx, rbx
0x140001cba  mov     dword ptr [rbx+60h], 0C000009Ah
0x140001cc1  mov     [rbx+68h], rsi
0x140001cc5  call    _guard_dispatch_icall
0x140001cca  jmp     loc_140001B5E
0x140001ccf  lea     rsi, [r14+0A8h]
0x140001cd6  mov     r8, rdi; struct VMX_MIRROR_TRANSFER_PACKET **
0x140001cd9  mov     rdx, rbx; struct VMX_TRANSFER_PACKET *
0x140001cdc  mov     rcx, r14; this
0x140001cdf  call    ?LaunchWrite@VMX_IO_MIRROR@@QEAAEPEAVVMX_TRANSFER_PACKET@@PEAPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::LaunchWrite(VMX_TRANSFER_PACKET *,VMX_MIRROR_TRANSFER_PACKET * *)
0x140001ce4  test    al, al
0x140001ce6  jnz     loc_140001B5E
0x140001cec  mov     rdx, [rdi]
0x140001cef  cmp     rdx, [rsi]
0x140001cf2  jz      loc_140001E36
0x140001cf8  xor     ebx, ebx
0x140001cfa  cmp     [r14+38h], ebx
0x140001cfe  jbe     short loc_140001D21
0x140001d00  mov     rcx, [rdi+rbx*8]
0x140001d04  test    rcx, rcx
0x140001d07  jz      short loc_140001D19
0x140001d09  mov     rax, [rcx]
0x140001d0c  mov     edx, 1
0x140001d11  mov     rax, [rax]
0x140001d14  call    _guard_dispatch_icall
0x140001d19  inc     ebx
0x140001d1b  cmp     ebx, [r14+38h]
0x140001d1f  jb      short loc_140001D00
0x140001d21  xor     edx, edx; Tag
0x140001d23  mov     rcx, rdi; P
0x140001d26  call    cs:__imp_ExFreePoolWithTag
0x140001d2d  nop     dword ptr [rax+rax+00h]
0x140001d32  jmp     loc_140001B5E
0x140001d37  mov     edx, 80h
0x140001d3c  mov     ecx, 42h ; 'B'
0x140001d41  mov     r8d, 20206D56h
0x140001d47  call    cs:__imp_ExAllocatePool2
0x140001d4e  nop     dword ptr [rax+rax+00h]
0x140001d53  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x140001d5a  test    rax, rax
0x140001d5d  jnz     loc_140001DF5
0x140001d63  lea     rdi, [r14+18h]
0x140001d67  mov     rcx, rdi; SpinLock
0x140001d6a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001d71  nop     dword ptr [rax+rax+00h]
0x140001d76  cmp     [r14+0A0h], sil
0x140001d7d  jnz     short loc_140001DDE
0x140001d7f  movzx   edx, al; NewIrql
0x140001d82  mov     byte ptr [r14+0A0h], 1
0x140001d8a  mov     rcx, rdi; SpinLock
0x140001d8d  call    cs:__imp_KeReleaseSpinLock
0x140001d94  nop     dword ptr [rax+rax+00h]
0x140001d99  mov     rdi, [r14+0A8h]
0x140001da0  jmp     loc_140001B48
0x140001da5  add     r14, 0B0h
0x140001dac  mov     rcx, [r14+8]
0x140001db0  cmp     [rcx], r14
0x140001db3  jnz     short loc_140001DEE
0x140001db5  add     rbx, 70h ; 'p'
0x140001db9  movzx   edx, al; NewIrql
0x140001dbc  mov     [rbx], r14
0x140001dbf  mov     [rbx+8], rcx
0x140001dc3  mov     [rcx], rbx
0x140001dc6  mov     rcx, rdi; SpinLock
0x140001dc9  mov     [r14+8], rbx
0x140001dcd  call    cs:__imp_KeReleaseSpinLock
0x140001dd4  nop     dword ptr [rax+rax+00h]
0x140001dd9  jmp     loc_140001B5E
0x140001dde  add     r14, 0B0h
0x140001de5  mov     rcx, [r14+8]
0x140001de9  cmp     [rcx], r14
0x140001dec  jz      short loc_140001DB5
0x140001dee  mov     ecx, 3
0x140001df3  int     29h; Win8: RtlFailFast(ecx)
0x140001df5  mov     [rsp+88h+Depth], 20h ; ' '; Depth
0x140001dfc  mov     r9d, 200h; Flags
0x140001e02  mov     [rsp+88h+Tag], 32506D56h; Tag
0x140001e0a  xor     r8d, r8d; Free
0x140001e0d  xor     edx, edx; Allocate
0x140001e0f  mov     [rsp+88h+Irp], 128h; Size
0x140001e18  mov     rcx, rax; Lookaside
0x140001e1b  call    cs:__imp_ExInitializeNPagedLookasideList
0x140001e22  nop     dword ptr [rax+rax+00h]
0x140001e27  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140001e2e  jmp     loc_140001AF3
0x140001e33  mov     rdx, rdi; struct VMX_MIRROR_TRANSFER_PACKET *
0x140001e36  mov     rcx, r14; this
0x140001e39  call    ?RecyclePacket@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::RecyclePacket(VMX_MIRROR_TRANSFER_PACKET *)
0x140001e3e  jmp     loc_140001B5E
0x140001e43  lea     rdi, [r14+18h]
0x140001e47  mov     rcx, rdi; SpinLock
0x140001e4a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001e51  nop     dword ptr [rax+rax+00h]
0x140001e56  cmp     byte ptr [r14+0A0h], 0
0x140001e5e  jnz     loc_140001DA5
0x140001e64  movzx   edx, al; NewIrql
0x140001e67  mov     byte ptr [r14+0A0h], 1
0x140001e6f  mov     rcx, rdi; SpinLock
0x140001e72  call    cs:__imp_KeReleaseSpinLock
0x140001e79  nop     dword ptr [rax+rax+00h]
0x140001e7e  lea     rdi, [r14+0A8h]
0x140001e85  mov     rsi, rdi
0x140001e88  jmp     loc_140001CD6
```
