# __memset_spec_ermsb_repmovsb

- ea: `0x140001ec0`
- end: `0x140001ef3`
- name: `__memset_spec_ermsb_repmovsb`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001d80`

## pseudocode

```c
void __fastcall _memset_spec_ermsb_repmovsb(_OWORD *a1, __int64 a2, __int64 a3)
{
  __int128 v3; // xmm0

  *a1 = v3;
  a1[1] = v3;
  a1[2] = v3;
  a1[3] = v3;
  memset(
    (void *)((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL),
    v3,
    (unsigned __int64)a1 + a3 - ((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL));
}

```

## disassembly

```asm
0x140001ec0  push    rdi
0x140001ec1  mov     rdi, rcx
0x140001ec4  add     r8, rcx
0x140001ec7  movups  xmmword ptr [rcx], xmm0
0x140001eca  add     rdi, 40h ; '@'
0x140001ece  movups  xmmword ptr [rcx+10h], xmm0
0x140001ed2  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140001ed6  movups  xmmword ptr [rcx+20h], xmm0
0x140001eda  sub     r8, rdi
0x140001edd  movups  xmmword ptr [rcx+30h], xmm0
0x140001ee1  mov     rcx, r8
0x140001ee4  mov     r9, rax
0x140001ee7  movq    rax, xmm0
0x140001eec  rep stosb
0x140001eee  mov     rax, r9
0x140001ef1  pop     rdi
0x140001ef2  retn
```
