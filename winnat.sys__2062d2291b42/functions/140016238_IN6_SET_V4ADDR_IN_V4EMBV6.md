# IN6_SET_V4ADDR_IN_V4EMBV6

- ea: `0x140016238`
- end: `0x1400162ae`
- name: `IN6_SET_V4ADDR_IN_V4EMBV6`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140003830`
- `0x140016760`
- `0x140016af0`
- `0x140016ea4`
- `0x14001b150`
- `0x14001e58c`

## callees

- `0x140016238`

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
0x140016238  push    rbx
0x14001623a  push    rsi
0x14001623b  push    rdi
0x14001623c  lea     eax, [rdx-20h]
0x14001623f  mov     rbx, r8
0x140016242  mov     rdi, rcx
0x140016245  cmp     al, 20h ; ' '
0x140016247  ja      short loc_140016259
0x140016249  mov     rcx, 101010101h
0x140016253  bt      rcx, rax
0x140016257  jb      short loc_140016262
0x140016259  cmp     dl, 60h ; '`'
0x14001625c  jz      short loc_140016262
0x14001625e  xor     al, al
0x140016260  jmp     short loc_1400162A9
0x140016262  xor     r11b, r11b
0x140016265  movzx   r9d, dl
0x140016269  xor     r10b, r10b
0x14001626c  mov     esi, 1
0x140016271  shr     r9d, 3
0x140016275  movzx   ecx, r10b
0x140016279  movzx   r8d, r10b
0x14001627d  movzx   r11d, r11b
0x140016281  lea     edx, [rcx+r9]
0x140016285  lea     eax, [rcx+r9]
0x140016289  cmp     eax, 8
0x14001628c  cmovz   r11d, esi
0x140016290  add     r10b, sil
0x140016293  movzx   ecx, r11b
0x140016297  add     edx, ecx
0x140016299  mov     cl, [r8+rbx]
0x14001629d  mov     [rdx+rdi], cl
0x1400162a0  cmp     r10b, 4
0x1400162a4  jb      short loc_140016275
0x1400162a6  mov     al, sil
0x1400162a9  pop     rdi
0x1400162aa  pop     rsi
0x1400162ab  pop     rbx
0x1400162ac  retn
```
