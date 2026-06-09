# IN6_SET_V4ADDR_IN_V4EMBV6

- ea: `0x1400158b8`
- end: `0x14001592e`
- name: `IN6_SET_V4ADDR_IN_V4EMBV6`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003830`
- `0x140015b28`
- `0x140015eb8`
- `0x14001ac70`
- `0x14001e08c`

## callees

- `0x1400158b8`

## pseudocode

```c
char __fastcall IN6_SET_V4ADDR_IN_V4EMBV6(__int64 a1, int a2, __int64 a3)
{
  __int64 v5; // rcx
  unsigned __int8 v7; // r11
  unsigned __int8 v8; // r10
  int v9; // r9d
  __int64 v10; // r8
  int v11; // edx

  if ( (unsigned __int8)(a2 - 32) > 0x20u || (v5 = 0x101010101LL, !_bittest64(&v5, (unsigned int)(a2 - 32))) )
  {
    if ( (_BYTE)a2 != 96 )
      return 0;
  }
  v7 = 0;
  v8 = 0;
  v9 = (unsigned __int8)a2 >> 3;
  do
  {
    v10 = v8;
    v11 = v8 + v9;
    if ( v11 == 8 )
      v7 = 1;
    ++v8;
    *(_BYTE *)((unsigned int)v7 + v11 + a1) = *(_BYTE *)(v10 + a3);
  }
  while ( v8 < 4u );
  return 1;
}

```

## disassembly

```asm
0x1400158b8  push    rbx
0x1400158ba  push    rsi
0x1400158bb  push    rdi
0x1400158bc  lea     eax, [rdx-20h]
0x1400158bf  mov     rbx, r8
0x1400158c2  mov     rdi, rcx
0x1400158c5  cmp     al, 20h ; ' '
0x1400158c7  ja      short loc_1400158D9
0x1400158c9  mov     rcx, 101010101h
0x1400158d3  bt      rcx, rax
0x1400158d7  jb      short loc_1400158E2
0x1400158d9  cmp     dl, 60h ; '`'
0x1400158dc  jz      short loc_1400158E2
0x1400158de  xor     al, al
0x1400158e0  jmp     short loc_140015929
0x1400158e2  xor     r11b, r11b
0x1400158e5  movzx   r9d, dl
0x1400158e9  xor     r10b, r10b
0x1400158ec  mov     esi, 1
0x1400158f1  shr     r9d, 3
0x1400158f5  movzx   ecx, r10b
0x1400158f9  movzx   r8d, r10b
0x1400158fd  movzx   r11d, r11b
0x140015901  lea     edx, [rcx+r9]
0x140015905  lea     eax, [rcx+r9]
0x140015909  cmp     eax, 8
0x14001590c  cmovz   r11d, esi
0x140015910  add     r10b, sil
0x140015913  movzx   ecx, r11b
0x140015917  add     edx, ecx
0x140015919  mov     cl, [r8+rbx]
0x14001591d  mov     [rdx+rdi], cl
0x140015920  cmp     r10b, 4
0x140015924  jb      short loc_1400158F5
0x140015926  mov     al, sil
0x140015929  pop     rdi
0x14001592a  pop     rsi
0x14001592b  pop     rbx
0x14001592c  retn
```
