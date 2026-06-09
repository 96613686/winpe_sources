# __memset_spec_ermsb_repmovsb

- ea: `0x140003880`
- end: `0x1400038b3`
- name: `__memset_spec_ermsb_repmovsb`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140003740`

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
0x140003880  push    rdi
0x140003881  mov     rdi, rcx
0x140003884  add     r8, rcx
0x140003887  movups  xmmword ptr [rcx], xmm0
0x14000388a  add     rdi, 40h ; '@'
0x14000388e  movups  xmmword ptr [rcx+10h], xmm0
0x140003892  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140003896  movups  xmmword ptr [rcx+20h], xmm0
0x14000389a  sub     r8, rdi
0x14000389d  movups  xmmword ptr [rcx+30h], xmm0
0x1400038a1  mov     rcx, r8
0x1400038a4  mov     r9, rax
0x1400038a7  movq    rax, xmm0
0x1400038ac  rep stosb
0x1400038ae  mov     rax, r9
0x1400038b1  pop     rdi
0x1400038b2  retn
```
