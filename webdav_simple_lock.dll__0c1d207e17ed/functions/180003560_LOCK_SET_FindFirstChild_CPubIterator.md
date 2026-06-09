# LOCK_SET::FindFirstChild(CPubIterator *)

- ea: `0x180003560`
- end: `0x18000359d`
- name: `?FindFirstChild@LOCK_SET@@UEAAPEAVIPubUriLockList@@PEAVCPubIterator@@@Z`
- size: `61`
- prototype: `struct IPubUriLockList *__fastcall(LOCK_SET *__hidden this, struct CPubIterator *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003560`

## pseudocode

```c
struct IPubUriLockList *__fastcall LOCK_SET::FindFirstChild(LOCK_SET *this, struct CPubIterator *a2)
{
  unsigned int i; // r8d
  __int64 v3; // rax

  *((_QWORD *)a2 + 1) = 0;
  for ( i = 0; i < 0x83; ++i )
  {
    v3 = *((_QWORD *)this + i + 229);
    if ( v3 )
      break;
  }
  *((_DWORD *)a2 + 2) = i;
  *(_QWORD *)a2 = v3;
  return (struct IPubUriLockList *)((v3 - 32) & -(__int64)(v3 != 0));
}

```

## disassembly

```asm
0x180003560  mov     r9, rcx
0x180003563  xor     ecx, ecx
0x180003565  mov     [rdx+8], rcx
0x180003569  mov     r8d, ecx
0x18000356c  mov     eax, r8d
0x18000356f  mov     rax, [r9+rax*8+728h]
0x180003577  test    rax, rax
0x18000357a  jnz     short loc_180003588
0x18000357c  inc     r8d
0x18000357f  cmp     r8d, 83h
0x180003586  jb      short loc_18000356C
0x180003588  lea     rcx, [rax-20h]
0x18000358c  mov     [rdx+8], r8d
0x180003590  mov     [rdx], rax
0x180003593  neg     rax
0x180003596  sbb     rax, rax
0x180003599  and     rax, rcx
0x18000359c  retn
```
