# SIO_RAID5::OnPacketCompletionReconstruct(SC_PACKET *)

- ea: `0x14005043c`
- end: `0x1400505f8`
- name: `?OnPacketCompletionReconstruct@SIO_RAID5@@QEAAJPEAVSC_PACKET@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(SIO_RAID5 *__hidden this, struct SC_PACKET *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140011dc0`

## callees

- `0x140016160`
- `0x1400191f0`
- `0x14001b090`
- `0x14005043c`
- `0x140068300`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400504f2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140050559`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400504f2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140050559`

## pseudocode

```c
__int64 __fastcall SIO_RAID5::OnPacketCompletionReconstruct(SIO_RAID5 *this, struct SC_PACKET *a2)
{
  int v2; // r13d
  __int64 v4; // rbx
  struct SC_PACKET *v5; // rdi
  unsigned __int64 v6; // rsi
  __int64 Sequential; // rax
  _QWORD *v8; // r15
  _QWORD *v9; // r12
  __int64 v10; // rbp
  unsigned int v11; // eax
  __int64 v12; // rcx
  PVOID v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r15
  PVOID v17; // rdx
  __int64 v18; // r15
  const void *v19; // rsi
  void *v20; // rcx
  unsigned int v22; // [rsp+80h] [rbp+8h]

  v2 = *((_DWORD *)a2 + 45);
  v4 = *((_QWORD *)a2 + 2);
  v5 = a2;
  v6 = *(_QWORD *)(v4 + 136) >> *((_BYTE *)this + 42);
  if ( v2 >= 0 )
  {
    if ( (*((_DWORD *)a2 + 19) & 2) != 0 )
    {
      LOBYTE(a2) = 22;
      Sequential = SIO_RAID5::GetSequential(this, a2);
      v8 = (_QWORD *)(v4 + 96);
      v9 = *(_QWORD **)(v4 + 96);
      v10 = *(_QWORD *)(Sequential + 32);
      while ( v9 != v8 )
      {
        v11 = SIO_RAID5::UnRotate(this, v6, *((_DWORD *)v9 - 13));
        v12 = *(v9 - 10);
        v22 = v11;
        if ( (*(_BYTE *)(v12 + 10) & 5) != 0 )
          v13 = *(PVOID *)(v12 + 24);
        else
          v13 = MmMapLockedPagesSpecifyCache((PMDL)v12, 0, MmCached, 0, 0, 0x40000020u);
        *(_QWORD *)(v10 + 8LL * v22 + 16) = v13;
        v9 = (_QWORD *)*v9;
      }
      if ( (_QWORD *)*v8 == v8 )
      {
        v14 = SIO_RAID5::UnRotate(this, v6, *(_DWORD *)(v4 + 148));
        v15 = *(_QWORD *)(v4 + 120);
        v16 = v14;
        if ( (*(_BYTE *)(v15 + 10) & 5) != 0 )
          v17 = *(PVOID *)(v15 + 24);
        else
          v17 = MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000020u);
        *(_QWORD *)(v10 + 8 * v16 + 16) = v17;
      }
      v18 = SIO_RAID5::UnRotate(this, v6, *((_DWORD *)v5 + 37));
      v19 = (const void *)(*(_QWORD *)(*((_QWORD *)v5 + 15) + 32LL) + *(unsigned int *)(*((_QWORD *)v5 + 15) + 44LL));
      v20 = *(void **)(v10 + 8 * v18 + 16);
      if ( v20 )
        memmove(v20, v19, *((unsigned int *)v5 + 36));
      *(_QWORD *)(v10 + 8 * v18 + 16) = v19;
      if ( _bittest((const signed __int32 *)(v10 + 8), v18) )
      {
        SC_PARITY::Execute(
          *(SC_PARITY **)(*((_QWORD *)this + 1) + 384LL),
          (struct SC_PARITY_CONTEXT *)v10,
          *(_DWORD *)(v4 + 144),
          *(_BYTE *)(v4 + 192));
        *(_QWORD *)(v4 + 192) = (unsigned int)(*((_DWORD *)v5 + 37) + 1);
      }
    }
  }
  else
  {
    _interlockedbittestandset(
      (volatile signed __int32 *)(v4 + 160),
      SIO_RAID5::UnRotate(this, v6, *((_DWORD *)a2 + 37)));
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14005043c  push    rbx
0x14005043e  push    rbp
0x14005043f  push    rsi
0x140050440  push    rdi
0x140050441  push    r12
0x140050443  push    r13
0x140050445  push    r14
0x140050447  push    r15
0x140050449  sub     rsp, 38h
0x14005044d  mov     r13d, [rdx+0B4h]
0x140050454  mov     r14, rcx
0x140050457  mov     rbx, [rdx+10h]
0x14005045b  mov     rdi, rdx
0x14005045e  mov     cl, [rcx+2Ah]
0x140050461  mov     rsi, [rbx+88h]
0x140050468  shr     rsi, cl
0x14005046b  test    r13d, r13d
0x14005046e  jns     short loc_14005048F
0x140050470  mov     r8d, [rdx+94h]; unsigned int
0x140050477  mov     rcx, r14; this
0x14005047a  mov     rdx, rsi; unsigned __int64
0x14005047d  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x140050482  lock bts [rbx+0A0h], eax
0x14005048a  jmp     loc_1400505E3
0x14005048f  mov     eax, [rdx+4Ch]
0x140050492  test    al, 2
0x140050494  jz      loc_1400505E3
0x14005049a  mov     dl, 16h
0x14005049c  mov     rcx, r14
0x14005049f  call    ?GetSequential@SIO_RAID5@@UEAAPEAVSC_SEQUENTIAL@@W4_SC_OPERATION@@@Z; SIO_RAID5::GetSequential(_SC_OPERATION)
0x1400504a4  lea     r15, [rbx+60h]
0x1400504a8  mov     r12, [r15]
0x1400504ab  mov     rbp, [rax+20h]
0x1400504af  jmp     short loc_140050511
0x1400504b1  mov     r8d, [r12-34h]; unsigned int
0x1400504b6  mov     rdx, rsi; unsigned __int64
0x1400504b9  mov     rcx, r14; this
0x1400504bc  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x1400504c1  mov     rcx, [r12-50h]; MemoryDescriptorList
0x1400504c6  mov     [rsp+78h+arg_0], eax
0x1400504cd  test    byte ptr [rcx+0Ah], 5
0x1400504d1  jz      short loc_1400504D9
0x1400504d3  mov     rdx, [rcx+18h]
0x1400504d7  jmp     short loc_140050501
0x1400504d9  xor     r9d, r9d; RequestedAddress
0x1400504dc  mov     [rsp+78h+Priority], 40000020h; Priority
0x1400504e4  xor     edx, edx; AccessMode
0x1400504e6  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400504ee  lea     r8d, [r9+1]; CacheType
0x1400504f2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400504f9  nop     dword ptr [rax+rax+00h]
0x1400504fe  mov     rdx, rax
0x140050501  mov     eax, [rsp+78h+arg_0]
0x140050508  mov     [rbp+rax*8+10h], rdx
0x14005050d  mov     r12, [r12]
0x140050511  cmp     r12, r15
0x140050514  jnz     short loc_1400504B1
0x140050516  cmp     [r15], r15
0x140050519  jnz     short loc_14005056D
0x14005051b  mov     r8d, [rbx+94h]; unsigned int
0x140050522  mov     rdx, rsi; unsigned __int64
0x140050525  mov     rcx, r14; this
0x140050528  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14005052d  mov     rcx, [rbx+78h]; MemoryDescriptorList
0x140050531  mov     r15d, eax
0x140050534  test    byte ptr [rcx+0Ah], 5
0x140050538  jz      short loc_140050540
0x14005053a  mov     rdx, [rcx+18h]
0x14005053e  jmp     short loc_140050568
0x140050540  xor     r9d, r9d; RequestedAddress
0x140050543  mov     [rsp+78h+Priority], 40000020h; Priority
0x14005054b  xor     edx, edx; AccessMode
0x14005054d  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140050555  lea     r8d, [r9+1]; CacheType
0x140050559  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140050560  nop     dword ptr [rax+rax+00h]
0x140050565  mov     rdx, rax
0x140050568  mov     [rbp+r15*8+10h], rdx
0x14005056d  mov     r8d, [rdi+94h]; unsigned int
0x140050574  mov     rdx, rsi; unsigned __int64
0x140050577  mov     rcx, r14; this
0x14005057a  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14005057f  mov     r8, [rdi+78h]
0x140050583  mov     r15d, eax
0x140050586  mov     esi, [r8+2Ch]
0x14005058a  add     rsi, [r8+20h]
0x14005058e  mov     rcx, [rbp+r15*8+10h]; void *
0x140050593  test    rcx, rcx
0x140050596  jz      short loc_1400505A7
0x140050598  mov     r8d, [rdi+90h]; Size
0x14005059f  mov     rdx, rsi; Src
0x1400505a2  call    memmove
0x1400505a7  mov     [rbp+r15*8+10h], rsi
0x1400505ac  bt      [rbp+8], r15d
0x1400505b1  jnb     short loc_1400505E3
0x1400505b3  mov     rcx, [r14+8]
0x1400505b7  mov     rdx, rbp; struct SC_PARITY_CONTEXT *
0x1400505ba  mov     r9b, [rbx+0C0h]; unsigned __int8
0x1400505c1  mov     r8d, [rbx+90h]; unsigned int
0x1400505c8  mov     rcx, [rcx+180h]; this
0x1400505cf  call    ?Execute@SC_PARITY@@QEAAXPEAVSC_PARITY_CONTEXT@@KE@Z; SC_PARITY::Execute(SC_PARITY_CONTEXT *,ulong,uchar)
0x1400505d4  mov     ecx, [rdi+94h]
0x1400505da  inc     ecx
0x1400505dc  mov     [rbx+0C0h], rcx
0x1400505e3  mov     eax, r13d
0x1400505e6  add     rsp, 38h
0x1400505ea  pop     r15
0x1400505ec  pop     r14
0x1400505ee  pop     r13
0x1400505f0  pop     r12
0x1400505f2  pop     rdi
0x1400505f3  pop     rsi
0x1400505f4  pop     rbp
0x1400505f5  pop     rbx
0x1400505f6  retn
```
