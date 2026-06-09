# __memset_spec_ermsb_repmovsb

- ea: `0x140003380`
- end: `0x1400033b3`
- name: `__memset_spec_ermsb_repmovsb`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140003240`

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
0x140003380  push    rdi
0x140003381  mov     rdi, rcx
0x140003384  add     r8, rcx
0x140003387  movups  xmmword ptr [rcx], xmm0
0x14000338a  add     rdi, 40h ; '@'
0x14000338e  movups  xmmword ptr [rcx+10h], xmm0
0x140003392  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140003396  movups  xmmword ptr [rcx+20h], xmm0
0x14000339a  sub     r8, rdi
0x14000339d  movups  xmmword ptr [rcx+30h], xmm0
0x1400033a1  mov     rcx, r8
0x1400033a4  mov     r9, rax
0x1400033a7  movq    rax, xmm0
0x1400033ac  rep stosb
0x1400033ae  mov     rax, r9
0x1400033b1  pop     rdi
0x1400033b2  retn
```
