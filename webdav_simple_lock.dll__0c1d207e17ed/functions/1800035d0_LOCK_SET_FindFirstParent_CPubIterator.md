# LOCK_SET::FindFirstParent(CPubIterator *)

- ea: `0x1800035d0`
- end: `0x18000360d`
- name: `?FindFirstParent@LOCK_SET@@UEAAPEAVIPubUriLockList@@PEAVCPubIterator@@@Z`
- size: `61`
- prototype: `struct IPubUriLockList *__fastcall(LOCK_SET *__hidden this, struct CPubIterator *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800035d0`

## pseudocode

```c
struct IPubUriLockList *__fastcall LOCK_SET::FindFirstParent(LOCK_SET *this, struct CPubIterator *a2)
{
  unsigned int i; // r8d
  __int64 v3; // rax

  *((_QWORD *)a2 + 1) = 0;
  for ( i = 0; i < 0x83; ++i )
  {
    v3 = *((_QWORD *)this + i + 97);
    if ( v3 )
      break;
  }
  *((_DWORD *)a2 + 2) = i;
  *(_QWORD *)a2 = v3;
  return (struct IPubUriLockList *)((v3 - 8) & -(__int64)(v3 != 0));
}

```

## disassembly

```asm
0x1800035d0  mov     r9, rcx
0x1800035d3  xor     ecx, ecx
0x1800035d5  mov     [rdx+8], rcx
0x1800035d9  mov     r8d, ecx
0x1800035dc  mov     eax, r8d
0x1800035df  mov     rax, [r9+rax*8+308h]
0x1800035e7  test    rax, rax
0x1800035ea  jnz     short loc_1800035F8
0x1800035ec  inc     r8d
0x1800035ef  cmp     r8d, 83h
0x1800035f6  jb      short loc_1800035DC
0x1800035f8  lea     rcx, [rax-8]
0x1800035fc  mov     [rdx+8], r8d
0x180003600  mov     [rdx], rax
0x180003603  neg     rax
0x180003606  sbb     rax, rax
0x180003609  and     rax, rcx
0x18000360c  retn
```
