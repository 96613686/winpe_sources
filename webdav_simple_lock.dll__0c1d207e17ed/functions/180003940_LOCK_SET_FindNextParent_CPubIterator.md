# LOCK_SET::FindNextParent(CPubIterator *)

- ea: `0x180003940`
- end: `0x1800039cb`
- name: `?FindNextParent@LOCK_SET@@UEAAPEAVIPubUriLockList@@PEAVCPubIterator@@@Z`
- size: `139`
- prototype: `struct IPubUriLockList *__fastcall(LOCK_SET *__hidden this, struct CPubIterator *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003940`

## pseudocode

```c
struct IPubUriLockList *__fastcall LOCK_SET::FindNextParent(LOCK_SET *this, struct CPubIterator *a2)
{
  __int64 v2; // rax
  unsigned int *v3; // r8
  unsigned int i; // ecx

  v2 = *(_QWORD *)a2;
  v3 = (unsigned int *)((char *)a2 + 8);
  if ( *(_QWORD *)a2 )
  {
    v2 = *((_DWORD *)a2 + 3) ? *((_QWORD *)this + *v3 + 97) : *(_QWORD *)(v2 + 8);
    *(_QWORD *)a2 = v2;
    if ( !v2 )
    {
      for ( i = ++*v3; i < 0x83; ++i )
      {
        v2 = *((_QWORD *)this + i + 97);
        if ( v2 )
          break;
      }
      *v3 = i;
      *(_QWORD *)a2 = v2;
    }
  }
  if ( *((_DWORD *)a2 + 3) && v2 )
    *((_QWORD *)this + *v3 + 97) = *(_QWORD *)(v2 + 8);
  return (struct IPubUriLockList *)((*(_QWORD *)a2 - 8LL) & -(__int64)(*(_QWORD *)a2 != 0));
}

```

## disassembly

```asm
0x180003940  mov     rax, [rdx]
0x180003943  lea     r8, [rdx+8]
0x180003947  mov     r10, rcx
0x18000394a  test    rax, rax
0x18000394d  jz      short loc_180003998
0x18000394f  cmp     dword ptr [rdx+0Ch], 0
0x180003953  jz      short loc_180003962
0x180003955  mov     eax, [r8]
0x180003958  mov     rax, [rcx+rax*8+308h]
0x180003960  jmp     short loc_180003966
0x180003962  mov     rax, [rax+8]
0x180003966  mov     [rdx], rax
0x180003969  test    rax, rax
0x18000396c  jnz     short loc_180003998
0x18000396e  inc     dword ptr [r8]
0x180003971  mov     r9d, 83h
0x180003977  mov     ecx, [r8]
0x18000397a  jmp     short loc_18000398D
0x18000397c  mov     eax, ecx
0x18000397e  mov     rax, [r10+rax*8+308h]
0x180003986  test    rax, rax
0x180003989  jnz     short loc_180003992
0x18000398b  inc     ecx
0x18000398d  cmp     ecx, r9d
0x180003990  jb      short loc_18000397C
0x180003992  mov     [r8], ecx
0x180003995  mov     [rdx], rax
0x180003998  mov     ecx, 0Ch
0x18000399d  mov     r9, rdx
0x1800039a0  cmp     dword ptr [rdx+rcx], 0
0x1800039a4  jz      short loc_1800039BA
0x1800039a6  test    rax, rax
0x1800039a9  jz      short loc_1800039BA
0x1800039ab  mov     ecx, [r8]
0x1800039ae  mov     rax, [rax+8]
0x1800039b2  mov     [r10+rcx*8+308h], rax
0x1800039ba  mov     rax, [rdx]
0x1800039bd  lea     rcx, [rax-8]
0x1800039c1  neg     rax
0x1800039c4  sbb     rax, rax
0x1800039c7  and     rax, rcx
0x1800039ca  retn
```
