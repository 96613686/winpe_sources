# SIO_RAID5::OnPacketCompletionReconstruct(SC_PACKET *)

- ea: `0x14005037c`
- end: `0x140050538`
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
- `0x14005037c`
- `0x1400681c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140050432`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140050499`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140050432`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140050499`

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
0x14005037c  push    rbx
0x14005037e  push    rbp
0x14005037f  push    rsi
0x140050380  push    rdi
0x140050381  push    r12
0x140050383  push    r13
0x140050385  push    r14
0x140050387  push    r15
0x140050389  sub     rsp, 38h
0x14005038d  mov     r13d, [rdx+0B4h]
0x140050394  mov     r14, rcx
0x140050397  mov     rbx, [rdx+10h]
0x14005039b  mov     rdi, rdx
0x14005039e  mov     cl, [rcx+2Ah]
0x1400503a1  mov     rsi, [rbx+88h]
0x1400503a8  shr     rsi, cl
0x1400503ab  test    r13d, r13d
0x1400503ae  jns     short loc_1400503CF
0x1400503b0  mov     r8d, [rdx+94h]; unsigned int
0x1400503b7  mov     rcx, r14; this
0x1400503ba  mov     rdx, rsi; unsigned __int64
0x1400503bd  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x1400503c2  lock bts [rbx+0A0h], eax
0x1400503ca  jmp     loc_140050523
0x1400503cf  mov     eax, [rdx+4Ch]
0x1400503d2  test    al, 2
0x1400503d4  jz      loc_140050523
0x1400503da  mov     dl, 16h
0x1400503dc  mov     rcx, r14
0x1400503df  call    ?GetSequential@SIO_RAID5@@UEAAPEAVSC_SEQUENTIAL@@W4_SC_OPERATION@@@Z; SIO_RAID5::GetSequential(_SC_OPERATION)
0x1400503e4  lea     r15, [rbx+60h]
0x1400503e8  mov     r12, [r15]
0x1400503eb  mov     rbp, [rax+20h]
0x1400503ef  jmp     short loc_140050451
0x1400503f1  mov     r8d, [r12-34h]; unsigned int
0x1400503f6  mov     rdx, rsi; unsigned __int64
0x1400503f9  mov     rcx, r14; this
0x1400503fc  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x140050401  mov     rcx, [r12-50h]; MemoryDescriptorList
0x140050406  mov     [rsp+78h+arg_0], eax
0x14005040d  test    byte ptr [rcx+0Ah], 5
0x140050411  jz      short loc_140050419
0x140050413  mov     rdx, [rcx+18h]
0x140050417  jmp     short loc_140050441
0x140050419  xor     r9d, r9d; RequestedAddress
0x14005041c  mov     [rsp+78h+Priority], 40000020h; Priority
0x140050424  xor     edx, edx; AccessMode
0x140050426  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14005042e  lea     r8d, [r9+1]; CacheType
0x140050432  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140050439  nop     dword ptr [rax+rax+00h]
0x14005043e  mov     rdx, rax
0x140050441  mov     eax, [rsp+78h+arg_0]
0x140050448  mov     [rbp+rax*8+10h], rdx
0x14005044d  mov     r12, [r12]
0x140050451  cmp     r12, r15
0x140050454  jnz     short loc_1400503F1
0x140050456  cmp     [r15], r15
0x140050459  jnz     short loc_1400504AD
0x14005045b  mov     r8d, [rbx+94h]; unsigned int
0x140050462  mov     rdx, rsi; unsigned __int64
0x140050465  mov     rcx, r14; this
0x140050468  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x14005046d  mov     rcx, [rbx+78h]; MemoryDescriptorList
0x140050471  mov     r15d, eax
0x140050474  test    byte ptr [rcx+0Ah], 5
0x140050478  jz      short loc_140050480
0x14005047a  mov     rdx, [rcx+18h]
0x14005047e  jmp     short loc_1400504A8
0x140050480  xor     r9d, r9d; RequestedAddress
0x140050483  mov     [rsp+78h+Priority], 40000020h; Priority
0x14005048b  xor     edx, edx; AccessMode
0x14005048d  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140050495  lea     r8d, [r9+1]; CacheType
0x140050499  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400504a0  nop     dword ptr [rax+rax+00h]
0x1400504a5  mov     rdx, rax
0x1400504a8  mov     [rbp+r15*8+10h], rdx
0x1400504ad  mov     r8d, [rdi+94h]; unsigned int
0x1400504b4  mov     rdx, rsi; unsigned __int64
0x1400504b7  mov     rcx, r14; this
0x1400504ba  call    ?UnRotate@SIO_RAID5@@QEAAK_KK@Z; SIO_RAID5::UnRotate(unsigned __int64,ulong)
0x1400504bf  mov     r8, [rdi+78h]
0x1400504c3  mov     r15d, eax
0x1400504c6  mov     esi, [r8+2Ch]
0x1400504ca  add     rsi, [r8+20h]
0x1400504ce  mov     rcx, [rbp+r15*8+10h]; void *
0x1400504d3  test    rcx, rcx
0x1400504d6  jz      short loc_1400504E7
0x1400504d8  mov     r8d, [rdi+90h]; Size
0x1400504df  mov     rdx, rsi; Src
0x1400504e2  call    memmove
0x1400504e7  mov     [rbp+r15*8+10h], rsi
0x1400504ec  bt      [rbp+8], r15d
0x1400504f1  jnb     short loc_140050523
0x1400504f3  mov     rcx, [r14+8]
0x1400504f7  mov     rdx, rbp; struct SC_PARITY_CONTEXT *
0x1400504fa  mov     r9b, [rbx+0C0h]; unsigned __int8
0x140050501  mov     r8d, [rbx+90h]; unsigned int
0x140050508  mov     rcx, [rcx+180h]; this
0x14005050f  call    ?Execute@SC_PARITY@@QEAAXPEAVSC_PARITY_CONTEXT@@KE@Z; SC_PARITY::Execute(SC_PARITY_CONTEXT *,ulong,uchar)
0x140050514  mov     ecx, [rdi+94h]
0x14005051a  inc     ecx
0x14005051c  mov     [rbx+0C0h], rcx
0x140050523  mov     eax, r13d
0x140050526  add     rsp, 38h
0x14005052a  pop     r15
0x14005052c  pop     r14
0x14005052e  pop     r13
0x140050530  pop     r12
0x140050532  pop     rdi
0x140050533  pop     rsi
0x140050534  pop     rbp
0x140050535  pop     rbx
0x140050536  retn
```
