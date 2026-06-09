# Pca::MergeSdb::PreviousMergeDbInfo::Compare(Pca::MergeSdb::PreviousMergeDbInfo const &)

- ea: `0x1400225d8`
- end: `0x140022695`
- name: `?Compare@PreviousMergeDbInfo@MergeSdb@Pca@@QEBA_NAEBV123@@Z`
- size: `189`
- prototype: `char __fastcall(Pca::MergeSdb::PreviousMergeDbInfo *this, const struct Pca::MergeSdb::PreviousMergeDbInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140021078`

## callees

- `0x1400225d8`
- `0x14002e3d6`

## pseudocode

```c
char __fastcall Pca::MergeSdb::PreviousMergeDbInfo::Compare(
        Pca::MergeSdb::PreviousMergeDbInfo *this,
        const struct Pca::MergeSdb::PreviousMergeDbInfo *a2)
{
  _QWORD *v2; // r10
  __int64 v3; // r8
  _QWORD *v4; // r9
  __int64 v6; // rax
  bool v7; // sf
  bool v8; // of
  unsigned int v9; // eax
  __int64 v10; // rax

  v2 = (_QWORD *)((char *)this + 24);
  v3 = *((_QWORD *)this + 3) - *((_QWORD *)this + 5);
  if ( !v3 )
    v3 = *((_QWORD *)this + 4) - *((_QWORD *)this + 6);
  v4 = (_QWORD *)((char *)a2 + 24);
  if ( !v3 && (*v4 != *((_QWORD *)a2 + 5) || *((_QWORD *)a2 + 4) != *((_QWORD *)a2 + 6)) )
    return 1;
  if ( (*v2 != *((_QWORD *)this + 5) || *((_QWORD *)this + 4) != *((_QWORD *)this + 6))
    && *v4 == *((_QWORD *)a2 + 5)
    && *((_QWORD *)a2 + 4) == *((_QWORD *)a2 + 6) )
  {
    return 0;
  }
  v6 = *((_QWORD *)a2 + 2);
  v8 = __OFSUB__(*((_QWORD *)this + 2), v6);
  v7 = *((_QWORD *)this + 2) - v6 < 0;
  if ( *((_QWORD *)this + 2) != v6 )
    return v7 ^ v8;
  if ( *v2 != *v4 || *((_QWORD *)this + 4) != *((_QWORD *)a2 + 4) )
    return memcmp_0((char *)this + 24, (char *)a2 + 24, 0x10u) < 0;
  v9 = *((_DWORD *)a2 + 14);
  if ( *((_DWORD *)this + 14) == v9 )
  {
    v10 = *((_QWORD *)a2 + 1);
    v8 = __OFSUB__(*((_QWORD *)this + 1), v10);
    v7 = *((_QWORD *)this + 1) - v10 < 0;
    return v7 ^ v8;
  }
  return *((_DWORD *)this + 14) < v9;
}

```

## disassembly

```asm
0x1400225d8  sub     rsp, 28h
0x1400225dc  lea     r10, [rcx+18h]
0x1400225e0  mov     r8, [r10]
0x1400225e3  sub     r8, [rcx+28h]
0x1400225e7  jnz     short loc_1400225F1
0x1400225e9  mov     r8, [r10+8]
0x1400225ed  sub     r8, [rcx+30h]
0x1400225f1  xor     eax, eax
0x1400225f3  lea     r9, [rdx+18h]
0x1400225f7  test    r8, r8
0x1400225fa  setz    al
0x1400225fd  test    eax, eax
0x1400225ff  jz      short loc_140022618
0x140022601  mov     rax, [r9]
0x140022604  cmp     rax, [rdx+28h]
0x140022608  jnz     short loc_140022614
0x14002260a  mov     rax, [r9+8]
0x14002260e  cmp     rax, [rdx+30h]
0x140022612  jz      short loc_140022618
0x140022614  mov     al, 1
0x140022616  jmp     short loc_140022690
0x140022618  mov     rax, [r10]
0x14002261b  cmp     rax, [rcx+28h]
0x14002261f  jnz     short loc_14002262B
0x140022621  mov     rax, [r10+8]
0x140022625  cmp     rax, [rcx+30h]
0x140022629  jz      short loc_140022642
0x14002262b  mov     rax, [r9]
0x14002262e  cmp     rax, [rdx+28h]
0x140022632  jnz     short loc_140022642
0x140022634  mov     rax, [r9+8]
0x140022638  cmp     rax, [rdx+30h]
0x14002263c  jnz     short loc_140022642
0x14002263e  xor     al, al
0x140022640  jmp     short loc_140022690
0x140022642  mov     rax, [rdx+10h]
0x140022646  cmp     [rcx+10h], rax
0x14002264a  jz      short loc_140022651
0x14002264c  setl    al
0x14002264f  jmp     short loc_140022690
0x140022651  mov     rax, [r10]
0x140022654  cmp     rax, [r9]
0x140022657  jnz     short loc_14002267A
0x140022659  mov     rax, [r10+8]
0x14002265d  cmp     rax, [r9+8]
0x140022661  jnz     short loc_14002267A
0x140022663  mov     eax, [rdx+38h]
0x140022666  cmp     [rcx+38h], eax
0x140022669  jz      short loc_140022670
0x14002266b  setb    al
0x14002266e  jmp     short loc_140022690
0x140022670  mov     rax, [rdx+8]
0x140022674  cmp     [rcx+8], rax
0x140022678  jmp     short loc_14002264C
0x14002267a  mov     r8d, 10h; Size
0x140022680  mov     rdx, r9; Buf2
0x140022683  mov     rcx, r10; Buf1
0x140022686  call    memcmp_0
0x14002268b  test    eax, eax
0x14002268d  sets    al
0x140022690  add     rsp, 28h
0x140022694  retn
```
