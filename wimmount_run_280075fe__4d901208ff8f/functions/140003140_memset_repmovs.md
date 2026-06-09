# __memset_repmovs

- ea: `0x140003140`
- end: `0x140003183`
- name: `__memset_repmovs`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003000`

## callees

- `0x140003140`
- `0x1400031c0`

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
0x140003140  push    rdi
0x140003141  test    cs:__isa_info, 1
0x140003148  jz      short loc_14000317C
0x14000314a  mov     rdi, rcx
0x14000314d  add     r8, rcx
0x140003150  movups  xmmword ptr [rcx], xmm0
0x140003153  add     rdi, 40h ; '@'
0x140003157  movups  xmmword ptr [rcx+10h], xmm0
0x14000315b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x14000315f  movups  xmmword ptr [rcx+20h], xmm0
0x140003163  sub     r8, rdi
0x140003166  movups  xmmword ptr [rcx+30h], xmm0
0x14000316a  mov     rcx, r8
0x14000316d  mov     r9, rax
0x140003170  movq    rax, xmm0
0x140003175  rep stosb
0x140003177  mov     rax, r9
0x14000317a  pop     rdi
0x14000317b  retn
0x14000317c  call    __memset_query
0x140003181  jmp     short loc_14000314A
```
