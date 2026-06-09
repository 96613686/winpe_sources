# SIO_RAID::OnPacketCompletionReadUnit(SC_PACKET *)

- ea: `0x1400129d0`
- end: `0x140012b12`
- name: `?OnPacketCompletionReadUnit@SIO_RAID@@AEAAJPEAVSC_PACKET@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(SIO_RAID *__hidden this, struct SC_PACKET *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140011e70`
- `0x140012280`

## callees

- `0x14000b290`
- `0x140012600`
- `0x1400129d0`
- `0x140012d50`
- `0x140015da0`
- `0x140026f40`
- `0x1400540bc`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012a83`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140069b42`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012a83`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140069b42`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012a59`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140069b10`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012a59`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140069b10`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012adb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012adb`

## pseudocode

```c
__int64 __fastcall SIO_RAID::OnPacketCompletionReadUnit(volatile LONG *this, struct SC_PACKET *a2)
{
  int v2; // ebx
  unsigned int v4; // esi
  int v7; // ecx
  KIRQL v8; // r14
  __int64 v9; // r10
  PVOID v10; // rbp
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  volatile LONG *v16; // r15
  struct SIO_COLUMN *v17; // rax
  KIRQL v18; // r9
  int v19; // eax
  size_t BugCheckOnFailure; // [rsp+20h] [rbp-48h]

  v2 = *((_DWORD *)a2 + 45);
  v4 = *((_DWORD *)a2 + 38);
  if ( v2 == -2147483626 )
    goto LABEL_2;
  v7 = *((unsigned __int8 *)a2 + 170);
  if ( v7 == 1 )
  {
    if ( v2 >= 0 )
      goto LABEL_2;
    *((_BYTE *)a2 + 170) = 3;
  }
  else
  {
    v13 = v7 - 3;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( !v14 )
      {
        *((_BYTE *)a2 + 170) = 5;
        return (unsigned int)-1073741267;
      }
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( v15 == 1 )
        {
          if ( v2 < 0 )
            v2 = 1073741834;
          if ( (*((_DWORD *)a2 + 19) & 0x40000000) == 0 )
          {
LABEL_3:
            if ( (unsigned __int8)(*((_BYTE *)a2 + 170) - 5) <= 1u )
              SIO_RAID::ReleaseRegion((SIO_RAID *)this, a2);
            if ( v2 >= 0 && (*((_DWORD *)a2 + 19) & 2) != 0 )
              *(_QWORD *)(*((_QWORD *)a2 + 2) + 192LL) += *((unsigned int *)a2 + 36);
            return (unsigned int)v2;
          }
          LODWORD(BugCheckOnFailure) = *((_DWORD *)a2 + 36);
          SC_BUFFER::Copy(
            (SC_BUFFER *)(*((_QWORD *)a2 + 2) + 112LL),
            (struct SC_PACKET *)((char *)a2 + 112),
            0,
            *((_DWORD *)a2 + 34) - *(_DWORD *)(*((_QWORD *)a2 + 2) + 136LL),
            BugCheckOnFailure);
LABEL_2:
          if ( v2 == -1073741267 )
            return (unsigned int)v2;
          goto LABEL_3;
        }
      }
      else if ( v2 >= 0 )
      {
        v2 = -1073741267;
        *((_DWORD *)a2 + 39) = *((_DWORD *)a2 + 44);
        *((_DWORD *)a2 + 38) = -1;
        *((_BYTE *)a2 + 168) = 4;
        *((_BYTE *)a2 + 170) = 6;
        return (unsigned int)v2;
      }
    }
    else if ( v2 >= 0 )
    {
      goto LABEL_2;
    }
  }
  v16 = this + 6;
  if ( !ScIsMediaError(*((_DWORD *)a2 + 45)) )
  {
    ExAcquireSpinLockExclusive(this + 6);
    v17 = SIO_RAID::Get((SIO_RAID *)this, *((_DWORD *)a2 + 37), v4);
    *(_WORD *)v17 |= 1u;
    ExReleaseSpinLockExclusive(this + 6, v18);
  }
  _bittestandreset((signed __int32 *)a2 + 39, v4);
  v19 = (*(__int64 (__fastcall **)(volatile LONG *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 144LL))(
          this,
          *((unsigned int *)a2 + 37),
          *((unsigned int *)a2 + 39),
          *((_QWORD *)a2 + 17));
  *((_DWORD *)a2 + 38) = v19;
  if ( v19 == -1 )
    goto LABEL_2;
  v2 = -1073741267;
  if ( !ScIsMediaError(*((_DWORD *)a2 + 45)) || (*((_DWORD *)a2 + 19) & 2) != 0 )
    return (unsigned int)v2;
  if ( !SC_BUFFER::IsStable((struct SC_PACKET *)((char *)a2 + 112)) )
  {
    v8 = ExAcquireSpinLockExclusive(this + 6);
    v9 = *(_QWORD *)(*((_QWORD *)a2 + 2) + 120LL);
    if ( (*(_BYTE *)(v9 + 10) & 5) != 0 )
      v10 = *(PVOID *)(v9 + 24);
    else
      v10 = MmMapLockedPagesSpecifyCache((PMDL)v9, 0, MmCached, 0, 0, 0x40000020u);
    ExReleaseSpinLockExclusive(v16, v8);
    if ( !v10 || (int)SC_BUFFER::Reinitialize((char *)a2 + 112, v11, v12, *((unsigned int *)a2 + 36)) < 0 )
      return (unsigned int)v2;
    *((_DWORD *)a2 + 19) |= 0x40000000u;
  }
  _bittestandset((signed __int32 *)a2 + 44, v4);
  if ( *((_BYTE *)a2 + 170) == 3 )
    *((_BYTE *)a2 + 170) = 4;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400129d0  push    rbx
0x1400129d2  push    rsi
0x1400129d3  push    rdi
0x1400129d4  push    r12
0x1400129d6  push    r14
0x1400129d8  push    r15
0x1400129da  sub     rsp, 38h
0x1400129de  mov     ebx, [rdx+0B4h]
0x1400129e4  mov     rdi, rdx
0x1400129e7  mov     esi, [rdx+98h]
0x1400129ed  mov     r14, rcx
0x1400129f0  cmp     ebx, 80000016h
0x1400129f6  jnz     short loc_140012A31
0x1400129f8  cmp     ebx, 0C000022Dh
0x1400129fe  jz      short loc_140012A20
0x140012a00  movzx   eax, byte ptr [rdi+0AAh]
0x140012a07  sub     al, 5
0x140012a09  cmp     al, 1
0x140012a0b  jbe     loc_140012AEC
0x140012a11  test    ebx, ebx
0x140012a13  js      short loc_140012A20
0x140012a15  mov     eax, [rdi+4Ch]
0x140012a18  test    al, 2
0x140012a1a  jnz     loc_140012AFC
0x140012a20  mov     eax, ebx
0x140012a22  add     rsp, 38h
0x140012a26  pop     r15
0x140012a28  pop     r14
0x140012a2a  pop     r12
0x140012a2c  pop     rdi
0x140012a2d  pop     rsi
0x140012a2e  pop     rbx
0x140012a2f  retn
0x140012a31  movzx   ecx, byte ptr [rdx+0AAh]
0x140012a38  cmp     ecx, 1
0x140012a3b  jnz     loc_140069A46
0x140012a41  test    ebx, ebx
0x140012a43  jns     short loc_1400129F8
0x140012a45  mov     byte ptr [rdx+0AAh], 3
0x140012a4c  jmp     loc_140069AFA
0x140012a51  mov     rcx, r15; SpinLock
0x140012a54  mov     [rsp+68h+arg_0], rbp
0x140012a59  call    cs:__imp_ExAcquireSpinLockExclusive
0x140012a60  nop     dword ptr [rax+rax+00h]
0x140012a65  mov     rcx, [rdi+10h]
0x140012a69  movzx   r14d, al
0x140012a6d  mov     r10, [rcx+78h]
0x140012a71  test    byte ptr [r10+0Ah], 5
0x140012a76  jz      short loc_140012ABD
0x140012a78  mov     rbp, [r10+18h]
0x140012a7c  movzx   edx, r14b; OldIrql
0x140012a80  mov     rcx, r15; SpinLock
0x140012a83  call    cs:__imp_ExReleaseSpinLockExclusive
0x140012a8a  nop     dword ptr [rax+rax+00h]
0x140012a8f  test    rbp, rbp
0x140012a92  mov     rbp, [rsp+68h+arg_0]
0x140012a97  jz      short loc_140012A20
0x140012a99  mov     r9d, [rdi+90h]
0x140012aa0  lea     rcx, [rdi+70h]
0x140012aa4  call    ?Reinitialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Reinitialize(_SC_BUFFER_TYPE,void *,ulong)
0x140012aa9  test    eax, eax
0x140012aab  js      loc_140012A20
0x140012ab1  or      dword ptr [rdi+4Ch], 40000000h
0x140012ab8  jmp     loc_140069BC3
0x140012abd  mov     [rsp+68h+Priority], 40000020h; Priority
0x140012ac5  xor     r9d, r9d; RequestedAddress
0x140012ac8  xor     edx, edx; AccessMode
0x140012aca  mov     dword ptr [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140012ad2  mov     r8d, 1; CacheType
0x140012ad8  mov     rcx, r10; MemoryDescriptorList
0x140012adb  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140012ae2  nop     dword ptr [rax+rax+00h]
0x140012ae7  mov     rbp, rax
0x140012aea  jmp     short loc_140012A7C
0x140012aec  mov     rdx, rdi; struct SC_PACKET *
0x140012aef  mov     rcx, r14; this
0x140012af2  call    ?ReleaseRegion@SIO_RAID@@QEAAXPEAVSC_PACKET@@@Z; SIO_RAID::ReleaseRegion(SC_PACKET *)
0x140012af7  jmp     loc_140012A11
0x140012afc  mov     rcx, [rdi+10h]
0x140012b00  mov     eax, [rdi+90h]
0x140012b06  add     [rcx+0C0h], rax
0x140012b0d  jmp     loc_140012A20
0x140069a46  sub     ecx, 3
0x140069a49  jz      loc_140069AF2
0x140069a4f  sub     ecx, 1
0x140069a52  jz      loc_140069AE1
0x140069a58  sub     ecx, 1
0x140069a5b  jz      short loc_140069AAF
0x140069a5d  cmp     ecx, 1
0x140069a60  jnz     loc_140069AFA
0x140069a66  test    ebx, ebx
0x140069a68  mov     eax, 4000000Ah
0x140069a6d  cmovs   ebx, eax
0x140069a70  test    dword ptr [rdx+4Ch], 40000000h
0x140069a77  jz      loc_140012A00
0x140069a7d  mov     rcx, [rdx+10h]
0x140069a81  xor     r8d, r8d; unsigned int
0x140069a84  mov     r9d, [rdx+88h]
0x140069a8b  add     rdx, 70h ; 'p'; struct SC_BUFFER *
0x140069a8f  mov     eax, [rdi+90h]
0x140069a95  mov     dword ptr [rsp+68h+BugCheckOnFailure], eax; Size
0x140069a99  sub     r9d, [rcx+88h]; unsigned int
0x140069aa0  add     rcx, 70h ; 'p'; this
0x140069aa4  call    ?Copy@SC_BUFFER@@QEAAJPEAV1@KKK@Z; SC_BUFFER::Copy(SC_BUFFER *,ulong,ulong,ulong)
0x140069aa9  nop
0x140069aaa  jmp     loc_1400129F8
0x140069aaf  test    ebx, ebx
0x140069ab1  js      short loc_140069AFA
0x140069ab3  mov     eax, [rdx+0B0h]
0x140069ab9  mov     ebx, 0C000022Dh
0x140069abe  mov     [rdx+9Ch], eax
0x140069ac4  mov     dword ptr [rdx+98h], 0FFFFFFFFh
0x140069ace  mov     byte ptr [rdx+0A8h], 4
0x140069ad5  mov     byte ptr [rdx+0AAh], 6
0x140069adc  jmp     loc_140012A20
0x140069ae1  mov     byte ptr [rdx+0AAh], 5
0x140069ae8  mov     ebx, 0C000022Dh
0x140069aed  jmp     loc_140012A20
0x140069af2  test    ebx, ebx
0x140069af4  jns     loc_1400129F8
0x140069afa  mov     ecx, [rdx+0B4h]; int
0x140069b00  call    ?ScIsMediaError@@YAEJ@Z; ScIsMediaError(long)
0x140069b05  lea     r15, [r14+18h]
0x140069b09  test    al, al
0x140069b0b  jnz     short loc_140069B4E
0x140069b0d  mov     rcx, r15; SpinLock
0x140069b10  call    cs:__imp_ExAcquireSpinLockExclusive
0x140069b17  nop     dword ptr [rax+rax+00h]
0x140069b1c  mov     edx, [rdi+94h]; unsigned int
0x140069b22  mov     r8d, esi; unsigned int
0x140069b25  mov     rcx, r14; this
0x140069b28  movzx   r9d, al
0x140069b2c  call    ?Get@SIO_RAID@@QEAAPEAVSIO_COLUMN@@KK@Z; SIO_RAID::Get(ulong,ulong)
0x140069b31  movzx   edx, r9b; OldIrql
0x140069b35  movzx   ecx, word ptr [rax]
0x140069b38  or      cx, 1
0x140069b3c  mov     [rax], cx
0x140069b3f  mov     rcx, r15; SpinLock
0x140069b42  call    cs:__imp_ExReleaseSpinLockExclusive
0x140069b49  nop     dword ptr [rax+rax+00h]
0x140069b4e  btr     [rdi+9Ch], esi
0x140069b55  mov     rax, [r14]
0x140069b58  mov     edx, 94h
0x140069b5d  mov     r9, [rdi+88h]
0x140069b64  mov     rcx, rdi
0x140069b67  mov     r8d, [rdi+9Ch]
0x140069b6e  mov     rax, [rax+90h]
0x140069b75  mov     edx, [rdx+rcx]
0x140069b78  mov     rcx, r14
0x140069b7b  call    _guard_dispatch_icall
0x140069b80  mov     [rdi+98h], eax
0x140069b86  cmp     eax, 0FFFFFFFFh
0x140069b89  jz      loc_1400129F8
0x140069b8f  mov     ecx, [rdi+0B4h]; int
0x140069b95  mov     ebx, 0C000022Dh
0x140069b9a  call    ?ScIsMediaError@@YAEJ@Z; ScIsMediaError(long)
0x140069b9f  test    al, al
0x140069ba1  jz      loc_140012A20
0x140069ba7  mov     eax, [rdi+4Ch]
0x140069baa  test    al, 2
0x140069bac  jnz     loc_140012A20
0x140069bb2  lea     rcx, [rdi+70h]; this
0x140069bb6  call    ?IsStable@SC_BUFFER@@QEAAEXZ; SC_BUFFER::IsStable(void)
0x140069bbb  test    al, al
0x140069bbd  jz      loc_140012A51
0x140069bc3  bts     [rdi+0B0h], esi
0x140069bca  cmp     byte ptr [rdi+0AAh], 3
0x140069bd1  jnz     loc_140012A20
0x140069bd7  mov     byte ptr [rdi+0AAh], 4
0x140069bde  jmp     loc_140012A20
```
