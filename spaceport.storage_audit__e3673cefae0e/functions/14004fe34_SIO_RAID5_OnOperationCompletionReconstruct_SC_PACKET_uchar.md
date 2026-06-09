# SIO_RAID5::OnOperationCompletionReconstruct(SC_PACKET *,uchar)

- ea: `0x14004fe34`
- end: `0x14004ffe9`
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
- `0x14004fe34`
- `0x1400681c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004ffc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ffc9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004fed3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004ff31`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004fed3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004ff31`

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
0x14004fe34  push    rbx
0x14004fe36  push    rbp
0x14004fe37  push    rsi
0x14004fe38  push    rdi
0x14004fe39  push    r12
0x14004fe3b  push    r13
0x14004fe3d  push    r14
0x14004fe3f  push    r15
0x14004fe41  sub     rsp, 38h
0x14004fe45  mov     ebp, [rdx+0B4h]
0x14004fe4b  mov     rbx, rdx
0x14004fe4e  mov     rsi, [rdx+0C0h]
0x14004fe55  mov     r13, rcx
0x14004fe58  test    ebp, ebp
0x14004fe5a  jns     short loc_14004FE79
0x14004fe5c  cmp     dword ptr [rdx+0A0h], 0
0x14004fe63  mov     eax, 0C000022Dh
0x14004fe68  cmovnz  ebp, eax
0x14004fe6b  test    r8b, r8b
0x14004fe6e  jnz     loc_14004FFD5
0x14004fe74  jmp     loc_14004FFC4
0x14004fe79  test    r8b, r8b
0x14004fe7c  jnz     loc_14004FFD5
0x14004fe82  mov     cl, [rcx+2Ah]
0x14004fe85  lea     rdi, [rdx+60h]
0x14004fe89  mov     r12, [rdx+88h]
0x14004fe90  mov     r14, [rdi]
0x14004fe93  shr     r12, cl
0x14004fe96  jmp     short loc_14004FEEA
0x14004fe98  mov     r8d, [r14-34h]; unsigned int
0x14004fe9c  mov     rdx, r12; unsigned __int64
0x14004fe9f  mov     rcx, r13; this
0x14004fea2  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004fea7  mov     rcx, [r14-50h]; MemoryDescriptorList
0x14004feab  mov     r15d, eax
0x14004feae  test    byte ptr [rcx+0Ah], 5
0x14004feb2  jz      short loc_14004FEBA
0x14004feb4  mov     rdx, [rcx+18h]
0x14004feb8  jmp     short loc_14004FEE2
0x14004feba  xor     r9d, r9d; RequestedAddress
0x14004febd  mov     [rsp+78h+Priority], 40000020h; Priority
0x14004fec5  xor     edx, edx; AccessMode
0x14004fec7  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004fecf  lea     r8d, [r9+1]; CacheType
0x14004fed3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004feda  nop     dword ptr [rax+rax+00h]
0x14004fedf  mov     rdx, rax
0x14004fee2  mov     [rsi+r15*8+10h], rdx
0x14004fee7  mov     r14, [r14]
0x14004feea  cmp     r14, rdi
0x14004feed  jnz     short loc_14004FE98
0x14004feef  cmp     [rdi], rdi
0x14004fef2  jnz     short loc_14004FF45
0x14004fef4  mov     r8d, [rbx+94h]; unsigned int
0x14004fefb  mov     rdx, r12; unsigned __int64
0x14004fefe  mov     rcx, r13; this
0x14004ff01  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004ff06  mov     rcx, [rbx+78h]; MemoryDescriptorList
0x14004ff0a  mov     edi, eax
0x14004ff0c  test    byte ptr [rcx+0Ah], 5
0x14004ff10  jz      short loc_14004FF18
0x14004ff12  mov     rdx, [rcx+18h]
0x14004ff16  jmp     short loc_14004FF40
0x14004ff18  xor     r9d, r9d; RequestedAddress
0x14004ff1b  mov     [rsp+78h+Priority], 40000020h; Priority
0x14004ff23  xor     edx, edx; AccessMode
0x14004ff25  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004ff2d  lea     r8d, [r9+1]; CacheType
0x14004ff31  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004ff38  nop     dword ptr [rax+rax+00h]
0x14004ff3d  mov     rdx, rax
0x14004ff40  mov     [rsi+rdi*8+10h], rdx
0x14004ff45  lea     r15, [rbx+28h]
0x14004ff49  mov     rdi, [r15]
0x14004ff4c  jmp     short loc_14004FF9C
0x14004ff4e  mov     r8d, [rdi+5Ch]; unsigned int
0x14004ff52  mov     rdx, r12; unsigned __int64
0x14004ff55  mov     rcx, r13; this
0x14004ff58  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14004ff5d  mov     eax, eax
0x14004ff5f  mov     [rsp+78h+arg_8], rax
0x14004ff67  mov     rcx, [rsi+rax*8+10h]; void *
0x14004ff6c  mov     rax, [rdi+40h]
0x14004ff70  mov     edx, [rax+2Ch]
0x14004ff73  mov     r8, [rax+20h]
0x14004ff77  lea     r14, [r8+rdx]
0x14004ff7b  test    rcx, rcx
0x14004ff7e  jz      short loc_14004FF8C
0x14004ff80  mov     r8d, [rdi+58h]; Size
0x14004ff84  mov     rdx, r14; Src
0x14004ff87  call    memmove
0x14004ff8c  mov     rax, [rsp+78h+arg_8]
0x14004ff94  mov     [rsi+rax*8+10h], r14
0x14004ff99  mov     rdi, [rdi]
0x14004ff9c  cmp     rdi, r15
0x14004ff9f  jnz     short loc_14004FF4E
0x14004ffa1  cmp     dword ptr [rsi+8], 0
0x14004ffa5  jz      short loc_14004FFC4
0x14004ffa7  mov     rcx, [r13+8]
0x14004ffab  xor     r9d, r9d; unsigned __int8
0x14004ffae  mov     r8d, [rbx+90h]; unsigned int
0x14004ffb5  mov     rdx, rsi; struct SC_PARITY_CONTEXT *
0x14004ffb8  mov     rcx, [rcx+180h]; this
0x14004ffbf  call    ?Execute@SC_PARITY@@QEAAXPEAVSC_PARITY_CONTEXT@@KE@Z; SC_PARITY::Execute(SC_PARITY_CONTEXT *,ulong,uchar)
0x14004ffc4  xor     edx, edx; Tag
0x14004ffc6  mov     rcx, rsi; P
0x14004ffc9  call    cs:__imp_ExFreePoolWithTag
0x14004ffd0  nop     dword ptr [rax+rax+00h]
0x14004ffd5  mov     eax, ebp
0x14004ffd7  add     rsp, 38h
0x14004ffdb  pop     r15
0x14004ffdd  pop     r14
0x14004ffdf  pop     r13
0x14004ffe1  pop     r12
0x14004ffe3  pop     rdi
0x14004ffe4  pop     rsi
0x14004ffe5  pop     rbp
0x14004ffe6  pop     rbx
0x14004ffe7  retn
```
