# SIO_RAID5::OnOperationCompletionReconstruct(SC_PACKET *,uchar)

- ea: `0x14004fef4`
- end: `0x1400500a9`
- name: `?OnOperationCompletionReconstruct@SIO_RAID5@@QEAAJPEAVSC_PACKET@@E@Z`
- size: `437`
- prototype: `__int64 __fastcall(SIO_RAID5 *__hidden this, struct SC_PACKET *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001cae0`

## callees

- `0x140016160`
- `0x14001b090`
- `0x14004fef4`
- `0x140068300`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140050089`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050089`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004ff93`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004fff1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004ff93`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004fff1`

## pseudocode

```c
__int64 __fastcall SIO_RAID5::OnOperationCompletionReconstruct(SIO_RAID5 *this, struct SC_PACKET *a2, char a3)
{
  int v3; // ebp
  __int64 v5; // rsi
  _QWORD *v7; // rdi
  _QWORD *v8; // r14
  unsigned __int64 v9; // r12
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r15
  PVOID v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdi
  PVOID v17; // rdx
  __int64 *i; // rdi
  void *v19; // rcx
  const void *v20; // r14
  __int64 v22; // [rsp+88h] [rbp+10h]

  v3 = *((_DWORD *)a2 + 45);
  v5 = *((_QWORD *)a2 + 24);
  if ( v3 >= 0 )
  {
    if ( !a3 )
    {
      v7 = (_QWORD *)((char *)a2 + 96);
      v8 = (_QWORD *)*((_QWORD *)a2 + 12);
      v9 = *((_QWORD *)a2 + 17) >> *((_BYTE *)this + 42);
      while ( v8 != v7 )
      {
        v10 = SIO_RAID5::UnRotate(this, v9, *((_DWORD *)v8 - 13));
        v11 = *(v8 - 10);
        v12 = v10;
        if ( (*(_BYTE *)(v11 + 10) & 5) != 0 )
          v13 = *(PVOID *)(v11 + 24);
        else
          v13 = MmMapLockedPagesSpecifyCache((PMDL)v11, 0, MmCached, 0, 0, 0x40000020u);
        *(_QWORD *)(v5 + 8 * v12 + 16) = v13;
        v8 = (_QWORD *)*v8;
      }
      if ( (_QWORD *)*v7 == v7 )
      {
        v14 = SIO_RAID5::UnRotate(this, v9, *((_DWORD *)a2 + 37));
        v15 = *((_QWORD *)a2 + 15);
        v16 = v14;
        if ( (*(_BYTE *)(v15 + 10) & 5) != 0 )
          v17 = *(PVOID *)(v15 + 24);
        else
          v17 = MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000020u);
        *(_QWORD *)(v5 + 8 * v16 + 16) = v17;
      }
      for ( i = (__int64 *)*((_QWORD *)a2 + 5); i != (__int64 *)((char *)a2 + 40); i = (__int64 *)*i )
      {
        v22 = SIO_RAID5::UnRotate(this, v9, *((_DWORD *)i + 23));
        v19 = *(void **)(v5 + 8 * v22 + 16);
        v20 = (const void *)(*(_QWORD *)(i[8] + 32) + *(unsigned int *)(i[8] + 44));
        if ( v19 )
          memmove(v19, v20, *((unsigned int *)i + 22));
        *(_QWORD *)(v5 + 8 * v22 + 16) = v20;
      }
      if ( *(_DWORD *)(v5 + 8) )
        SC_PARITY::Execute(
          *(SC_PARITY **)(*((_QWORD *)this + 1) + 384LL),
          (struct SC_PARITY_CONTEXT *)v5,
          *((_DWORD *)a2 + 36),
          0);
      goto LABEL_25;
    }
  }
  else
  {
    if ( *((_DWORD *)a2 + 40) )
      v3 = -1073741267;
    if ( !a3 )
LABEL_25:
      ExFreePoolWithTag((PVOID)v5, 0);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14004fef4  push    rbx
0x14004fef6  push    rbp
0x14004fef7  push    rsi
0x14004fef8  push    rdi
0x14004fef9  push    r12
0x14004fefb  push    r13
0x14004fefd  push    r14
0x14004feff  push    r15
0x14004ff01  sub     rsp, 38h
0x14004ff05  mov     ebp, [rdx+0B4h]
0x14004ff0b  mov     rbx, rdx
0x14004ff0e  mov     rsi, [rdx+0C0h]
0x14004ff15  mov     r13, rcx
0x14004ff18  test    ebp, ebp
0x14004ff1a  jns     short loc_14004FF39
0x14004ff1c  cmp     dword ptr [rdx+0A0h], 0
0x14004ff23  mov     eax, 0C000022Dh
0x14004ff28  cmovnz  ebp, eax
0x14004ff2b  test    r8b, r8b
0x14004ff2e  jnz     loc_140050095
0x14004ff34  jmp     loc_140050084
0x14004ff39  test    r8b, r8b
0x14004ff3c  jnz     loc_140050095
0x14004ff42  mov     cl, [rcx+2Ah]
0x14004ff45  lea     rdi, [rdx+60h]
0x14004ff49  mov     r12, [rdx+88h]
0x14004ff50  mov     r14, [rdi]
0x14004ff53  shr     r12, cl
0x14004ff56  jmp     short loc_14004FFAA
0x14004ff58  mov     r8d, [r14-34h]; unsigned int
0x14004ff5c  mov     rdx, r12; unsigned __int64
0x14004ff5f  mov     rcx, r13; this
0x14004ff62  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004ff67  mov     rcx, [r14-50h]; MemoryDescriptorList
0x14004ff6b  mov     r15d, eax
0x14004ff6e  test    byte ptr [rcx+0Ah], 5
0x14004ff72  jz      short loc_14004FF7A
0x14004ff74  mov     rdx, [rcx+18h]
0x14004ff78  jmp     short loc_14004FFA2
0x14004ff7a  xor     r9d, r9d; RequestedAddress
0x14004ff7d  mov     [rsp+78h+Priority], 40000020h; Priority
0x14004ff85  xor     edx, edx; AccessMode
0x14004ff87  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004ff8f  lea     r8d, [r9+1]; CacheType
0x14004ff93  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004ff9a  nop     dword ptr [rax+rax+00h]
0x14004ff9f  mov     rdx, rax
0x14004ffa2  mov     [rsi+r15*8+10h], rdx
0x14004ffa7  mov     r14, [r14]
0x14004ffaa  cmp     r14, rdi
0x14004ffad  jnz     short loc_14004FF58
0x14004ffaf  cmp     [rdi], rdi
0x14004ffb2  jnz     short loc_140050005
0x14004ffb4  mov     r8d, [rbx+94h]; unsigned int
0x14004ffbb  mov     rdx, r12; unsigned __int64
0x14004ffbe  mov     rcx, r13; this
0x14004ffc1  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004ffc6  mov     rcx, [rbx+78h]; MemoryDescriptorList
0x14004ffca  mov     edi, eax
0x14004ffcc  test    byte ptr [rcx+0Ah], 5
0x14004ffd0  jz      short loc_14004FFD8
0x14004ffd2  mov     rdx, [rcx+18h]
0x14004ffd6  jmp     short loc_140050000
0x14004ffd8  xor     r9d, r9d; RequestedAddress
0x14004ffdb  mov     [rsp+78h+Priority], 40000020h; Priority
0x14004ffe3  xor     edx, edx; AccessMode
0x14004ffe5  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004ffed  lea     r8d, [r9+1]; CacheType
0x14004fff1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004fff8  nop     dword ptr [rax+rax+00h]
0x14004fffd  mov     rdx, rax
0x140050000  mov     [rsi+rdi*8+10h], rdx
0x140050005  lea     r15, [rbx+28h]
0x140050009  mov     rdi, [r15]
0x14005000c  jmp     short loc_14005005C
0x14005000e  mov     r8d, [rdi+5Ch]; unsigned int
0x140050012  mov     rdx, r12; unsigned __int64
0x140050015  mov     rcx, r13; this
0x140050018  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14005001d  mov     eax, eax
0x14005001f  mov     [rsp+78h+arg_8], rax
0x140050027  mov     rcx, [rsi+rax*8+10h]; void *
0x14005002c  mov     rax, [rdi+40h]
0x140050030  mov     edx, [rax+2Ch]
0x140050033  mov     r8, [rax+20h]
0x140050037  lea     r14, [r8+rdx]
0x14005003b  test    rcx, rcx
0x14005003e  jz      short loc_14005004C
0x140050040  mov     r8d, [rdi+58h]; Size
0x140050044  mov     rdx, r14; Src
0x140050047  call    memmove
0x14005004c  mov     rax, [rsp+78h+arg_8]
0x140050054  mov     [rsi+rax*8+10h], r14
0x140050059  mov     rdi, [rdi]
0x14005005c  cmp     rdi, r15
0x14005005f  jnz     short loc_14005000E
0x140050061  cmp     dword ptr [rsi+8], 0
0x140050065  jz      short loc_140050084
0x140050067  mov     rcx, [r13+8]
0x14005006b  xor     r9d, r9d; unsigned __int8
0x14005006e  mov     r8d, [rbx+90h]; unsigned int
0x140050075  mov     rdx, rsi; struct SC_PARITY_CONTEXT *
0x140050078  mov     rcx, [rcx+180h]; this
0x14005007f  call    ?Execute@SC_PARITY@@QEAAXPEAVSC_PARITY_CONTEXT@@KE@Z; SC_PARITY::Execute(SC_PARITY_CONTEXT *,ulong,uchar)
0x140050084  xor     edx, edx; Tag
0x140050086  mov     rcx, rsi; P
0x140050089  call    cs:__imp_ExFreePoolWithTag
0x140050090  nop     dword ptr [rax+rax+00h]
0x140050095  mov     eax, ebp
0x140050097  add     rsp, 38h
0x14005009b  pop     r15
0x14005009d  pop     r14
0x14005009f  pop     r13
0x1400500a1  pop     r12
0x1400500a3  pop     rdi
0x1400500a4  pop     rsi
0x1400500a5  pop     rbp
0x1400500a6  pop     rbx
0x1400500a7  retn
```
