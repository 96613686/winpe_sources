# __memset_spec_ermsb_repmovsb

- ea: `0x1400067c0`
- end: `0x1400067f3`
- name: `__memset_spec_ermsb_repmovsb`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140006680`

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
0x1400067c0  push    rdi
0x1400067c1  mov     rdi, rcx
0x1400067c4  add     r8, rcx
0x1400067c7  movups  xmmword ptr [rcx], xmm0
0x1400067ca  add     rdi, 40h ; '@'
0x1400067ce  movups  xmmword ptr [rcx+10h], xmm0
0x1400067d2  and     rdi, 0FFFFFFFFFFFFFFC0h
0x1400067d6  movups  xmmword ptr [rcx+20h], xmm0
0x1400067da  sub     r8, rdi
0x1400067dd  movups  xmmword ptr [rcx+30h], xmm0
0x1400067e1  mov     rcx, r8
0x1400067e4  mov     r9, rax
0x1400067e7  movq    rax, xmm0
0x1400067ec  rep stosb
0x1400067ee  mov     rax, r9
0x1400067f1  pop     rdi
0x1400067f2  retn
```
