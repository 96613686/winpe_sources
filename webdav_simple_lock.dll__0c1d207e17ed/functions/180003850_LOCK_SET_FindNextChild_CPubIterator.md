# LOCK_SET::FindNextChild(CPubIterator *)

- ea: `0x180003850`
- end: `0x1800038db`
- name: `?FindNextChild@LOCK_SET@@UEAAPEAVIPubUriLockList@@PEAVCPubIterator@@@Z`
- size: `139`
- prototype: `struct IPubUriLockList *__fastcall(LOCK_SET *__hidden this, struct CPubIterator *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003850`

## pseudocode

```c
struct IPubUriLockList *__fastcall LOCK_SET::FindNextChild(LOCK_SET *this, struct CPubIterator *a2)
{
  __int64 v2; // rax
  unsigned int *v3; // r8
  unsigned int i; // ecx

  v2 = *(_QWORD *)a2;
  v3 = (unsigned int *)((char *)a2 + 8);
  if ( *(_QWORD *)a2 )
  {
    v2 = *((_DWORD *)a2 + 3) ? *((_QWORD *)this + *v3 + 229) : *(_QWORD *)(v2 + 8);
    *(_QWORD *)a2 = v2;
    if ( !v2 )
    {
      for ( i = ++*v3; i < 0x83; ++i )
      {
        v2 = *((_QWORD *)this + i + 229);
        if ( v2 )
          break;
      }
      *v3 = i;
      *(_QWORD *)a2 = v2;
    }
  }
  if ( *((_DWORD *)a2 + 3) && v2 )
    *((_QWORD *)this + *v3 + 229) = *(_QWORD *)(v2 + 8);
  return (struct IPubUriLockList *)((*(_QWORD *)a2 - 32LL) & -(__int64)(*(_QWORD *)a2 != 0));
}

```

## disassembly

```asm
0x180003850  mov     rax, [rdx]
0x180003853  lea     r8, [rdx+8]
0x180003857  mov     r10, rcx
0x18000385a  test    rax, rax
0x18000385d  jz      short loc_1800038A8
0x18000385f  cmp     dword ptr [rdx+0Ch], 0
0x180003863  jz      short loc_180003872
0x180003865  mov     eax, [r8]
0x180003868  mov     rax, [rcx+rax*8+728h]
0x180003870  jmp     short loc_180003876
0x180003872  mov     rax, [rax+8]
0x180003876  mov     [rdx], rax
0x180003879  test    rax, rax
0x18000387c  jnz     short loc_1800038A8
0x18000387e  inc     dword ptr [r8]
0x180003881  mov     r9d, 83h
0x180003887  mov     ecx, [r8]
0x18000388a  jmp     short loc_18000389D
0x18000388c  mov     eax, ecx
0x18000388e  mov     rax, [r10+rax*8+728h]
0x180003896  test    rax, rax
0x180003899  jnz     short loc_1800038A2
0x18000389b  inc     ecx
0x18000389d  cmp     ecx, r9d
0x1800038a0  jb      short loc_18000388C
0x1800038a2  mov     [r8], ecx
0x1800038a5  mov     [rdx], rax
0x1800038a8  mov     ecx, 0Ch
0x1800038ad  mov     r9, rdx
0x1800038b0  cmp     dword ptr [rdx+rcx], 0
0x1800038b4  jz      short loc_1800038CA
0x1800038b6  test    rax, rax
0x1800038b9  jz      short loc_1800038CA
0x1800038bb  mov     ecx, [r8]
0x1800038be  mov     rax, [rax+8]
0x1800038c2  mov     [r10+rcx*8+728h], rax
0x1800038ca  mov     rax, [rdx]
0x1800038cd  lea     rcx, [rax-20h]
0x1800038d1  neg     rax
0x1800038d4  sbb     rax, rax
0x1800038d7  and     rax, rcx
0x1800038da  retn
```
