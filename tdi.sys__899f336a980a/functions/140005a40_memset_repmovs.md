# __memset_repmovs

- ea: `0x140005a40`
- end: `0x140005a83`
- name: `__memset_repmovs`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005900`

## callees

- `0x140005a40`
- `0x140005ac0`

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
0x140005a40  push    rdi
0x140005a41  test    cs:__isa_info, 1
0x140005a48  jz      short loc_140005A7C
0x140005a4a  mov     rdi, rcx
0x140005a4d  add     r8, rcx
0x140005a50  movups  xmmword ptr [rcx], xmm0
0x140005a53  add     rdi, 40h ; '@'
0x140005a57  movups  xmmword ptr [rcx+10h], xmm0
0x140005a5b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140005a5f  movups  xmmword ptr [rcx+20h], xmm0
0x140005a63  sub     r8, rdi
0x140005a66  movups  xmmword ptr [rcx+30h], xmm0
0x140005a6a  mov     rcx, r8
0x140005a6d  mov     r9, rax
0x140005a70  movq    rax, xmm0
0x140005a75  rep stosb
0x140005a77  mov     rax, r9
0x140005a7a  pop     rdi
0x140005a7b  retn
0x140005a7c  call    __memset_query
0x140005a81  jmp     short loc_140005A4A
```
