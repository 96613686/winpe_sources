# __memset_repmovs

- ea: `0x140003640`
- end: `0x140003683`
- name: `__memset_repmovs`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003500`

## callees

- `0x140003640`
- `0x1400036c0`

## pseudocode

```c
__int64 __fastcall _memset_repmovs(_OWORD *a1, __int64 a2, __int64 a3)
{
  __int128 v3; // xmm0
  __int64 result; // rax

  if ( (_isa_info & 1) == 0 )
    result = _memset_query();
  *a1 = v3;
  a1[1] = v3;
  a1[2] = v3;
  a1[3] = v3;
  memset(
    (void *)((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL),
    v3,
    (unsigned __int64)a1 + a3 - ((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL));
  return result;
}

```

## disassembly

```asm
0x140003640  push    rdi
0x140003641  test    cs:__isa_info, 1
0x140003648  jz      short loc_14000367C
0x14000364a  mov     rdi, rcx
0x14000364d  add     r8, rcx
0x140003650  movups  xmmword ptr [rcx], xmm0
0x140003653  add     rdi, 40h ; '@'
0x140003657  movups  xmmword ptr [rcx+10h], xmm0
0x14000365b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x14000365f  movups  xmmword ptr [rcx+20h], xmm0
0x140003663  sub     r8, rdi
0x140003666  movups  xmmword ptr [rcx+30h], xmm0
0x14000366a  mov     rcx, r8
0x14000366d  mov     r9, rax
0x140003670  movq    rax, xmm0
0x140003675  rep stosb
0x140003677  mov     rax, r9
0x14000367a  pop     rdi
0x14000367b  retn
0x14000367c  call    __memset_query
0x140003681  jmp     short loc_14000364A
```
