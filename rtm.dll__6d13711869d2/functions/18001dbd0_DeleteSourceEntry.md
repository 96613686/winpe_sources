# DeleteSourceEntry

- ea: `0x18001dbd0`
- end: `0x18001dc20`
- name: `DeleteSourceEntry`
- size: `80`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c1a8`
- `0x18001d378`
- `0x18001decc`

## callees

- `0x18001dbd0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001dc12`

## pseudocode

```c
BOOL __fastcall DeleteSourceEntry(_QWORD *a1)
{
  __int64 v1; // r8
  _QWORD *v2; // rdx
  __int64 v3; // rdx
  _QWORD *v4; // rax

  v1 = a1[2];
  if ( *(_QWORD **)(v1 + 8) != a1 + 2
    || (v2 = (_QWORD *)a1[3], (_QWORD *)*v2 != a1 + 2)
    || (*v2 = v1, *(_QWORD *)(v1 + 8) = v2, v3 = *a1, *(_QWORD **)(*a1 + 8LL) != a1)
    || (v4 = (_QWORD *)a1[1], (_QWORD *)*v4 != a1) )
  {
    __fastfail(3u);
  }
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  return HeapFree(hHeap, 0, a1);
}

```

## disassembly

```asm
0x18001dbd0  lea     rax, [rcx+10h]
0x18001dbd4  mov     r8, [rax]
0x18001dbd7  cmp     [r8+8], rax
0x18001dbdb  jnz     short loc_18001DC19
0x18001dbdd  mov     rdx, [rax+8]
0x18001dbe1  cmp     [rdx], rax
0x18001dbe4  jnz     short loc_18001DC19
0x18001dbe6  mov     [rdx], r8
0x18001dbe9  mov     [r8+8], rdx
0x18001dbed  mov     rdx, [rcx]
0x18001dbf0  cmp     [rdx+8], rcx
0x18001dbf4  jnz     short loc_18001DC19
0x18001dbf6  mov     rax, [rcx+8]
0x18001dbfa  cmp     [rax], rcx
0x18001dbfd  jnz     short loc_18001DC19
0x18001dbff  mov     [rax], rdx
0x18001dc02  mov     r8, rcx
0x18001dc05  mov     [rdx+8], rax
0x18001dc09  xor     edx, edx
0x18001dc0b  mov     rcx, cs:hHeap
0x18001dc12  jmp     cs:__imp_HeapFree
0x18001dc19  mov     ecx, 3
0x18001dc1e  int     29h; Win8: RtlFailFast(ecx)
```
