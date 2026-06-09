# LOCK_SET::FindNextAllUri(URI_LOCK_LIST_ITER *)

- ea: `0x1800037b4`
- end: `0x18000383f`
- name: `?FindNextAllUri@LOCK_SET@@QEAAPEAVURI_LOCK_LIST@@PEAUURI_LOCK_LIST_ITER@@@Z`
- size: `139`
- prototype: `struct URI_LOCK_LIST *__fastcall(LOCK_SET *__hidden this, struct URI_LOCK_LIST_ITER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002b2c`

## callees

- `0x1800037b4`

## pseudocode

```c
struct URI_LOCK_LIST *__fastcall LOCK_SET::FindNextAllUri(LOCK_SET *this, struct URI_LOCK_LIST_ITER *a2)
{
  __int64 v2; // rax
  unsigned int *v3; // r8
  unsigned int i; // ecx

  v2 = *(_QWORD *)a2;
  v3 = (unsigned int *)((char *)a2 + 8);
  if ( *(_QWORD *)a2 )
  {
    v2 = *((_DWORD *)a2 + 3) ? *((_QWORD *)this + *v3 + 361) : *(_QWORD *)(v2 + 8);
    *(_QWORD *)a2 = v2;
    if ( !v2 )
    {
      for ( i = ++*v3; i < 0x83; ++i )
      {
        v2 = *((_QWORD *)this + i + 361);
        if ( v2 )
          break;
      }
      *v3 = i;
      *(_QWORD *)a2 = v2;
    }
  }
  if ( *((_DWORD *)a2 + 3) && v2 )
    *((_QWORD *)this + *v3 + 361) = *(_QWORD *)(v2 + 8);
  return (struct URI_LOCK_LIST *)((*(_QWORD *)a2 - 56LL) & -(__int64)(*(_QWORD *)a2 != 0));
}

```

## disassembly

```asm
0x1800037b4  mov     rax, [rdx]
0x1800037b7  lea     r8, [rdx+8]
0x1800037bb  mov     r10, rcx
0x1800037be  test    rax, rax
0x1800037c1  jz      short loc_18000380C
0x1800037c3  cmp     dword ptr [rdx+0Ch], 0
0x1800037c7  jz      short loc_1800037D6
0x1800037c9  mov     eax, [r8]
0x1800037cc  mov     rax, [rcx+rax*8+0B48h]
0x1800037d4  jmp     short loc_1800037DA
0x1800037d6  mov     rax, [rax+8]
0x1800037da  mov     [rdx], rax
0x1800037dd  test    rax, rax
0x1800037e0  jnz     short loc_18000380C
0x1800037e2  inc     dword ptr [r8]
0x1800037e5  mov     r9d, 83h
0x1800037eb  mov     ecx, [r8]
0x1800037ee  jmp     short loc_180003801
0x1800037f0  mov     eax, ecx
0x1800037f2  mov     rax, [r10+rax*8+0B48h]
0x1800037fa  test    rax, rax
0x1800037fd  jnz     short loc_180003806
0x1800037ff  inc     ecx
0x180003801  cmp     ecx, r9d
0x180003804  jb      short loc_1800037F0
0x180003806  mov     [r8], ecx
0x180003809  mov     [rdx], rax
0x18000380c  mov     ecx, 0Ch
0x180003811  mov     r9, rdx
0x180003814  cmp     dword ptr [rdx+rcx], 0
0x180003818  jz      short loc_18000382E
0x18000381a  test    rax, rax
0x18000381d  jz      short loc_18000382E
0x18000381f  mov     ecx, [r8]
0x180003822  mov     rax, [rax+8]
0x180003826  mov     [r10+rcx*8+0B48h], rax
0x18000382e  mov     rax, [rdx]
0x180003831  lea     rcx, [rax-38h]
0x180003835  neg     rax
0x180003838  sbb     rax, rax
0x18000383b  and     rax, rcx
0x18000383e  retn
```
