# FindGroupEntry

- ea: `0x18001dc28`
- end: `0x18001dcb3`
- name: `FindGroupEntry`
- size: `139`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180017f48`
- `0x180018070`
- `0x18001a360`
- `0x18001c1a8`
- `0x18001ca9c`
- `0x18001d378`
- `0x18001de20`
- `0x18001e8d4`
- `0x18001ed64`

## callees

- `0x18001dc28`

## pseudocode

```c
__int64 __fastcall FindGroupEntry(_QWORD **a1, unsigned int a2, __int64 a3, _QWORD *a4, int a5)
{
  _QWORD *v5; // r8
  unsigned int v6; // r10d
  _QWORD *v9; // rbx
  unsigned int v10; // r9d
  int v11; // ecx

  v5 = *a1;
  v6 = 0;
  *a4 = 0;
  if ( v5 != a1 )
  {
    while ( 1 )
    {
      v9 = v5 - 2;
      if ( !a5 )
        v9 = v5;
      v10 = *((_DWORD *)v9 + 8);
      v11 = (unsigned __int8)v10 - (unsigned __int8)a2;
      if ( (unsigned __int8)v10 == (unsigned __int8)a2 )
      {
        v11 = (v9[4] & 0xFF00) - (a2 & 0xFF00);
        if ( !v11 )
        {
          v11 = (v10 & 0xFF0000) - (a2 & 0xFF0000);
          if ( (v10 & 0xFF0000) == (a2 & 0xFF0000) )
            v11 = ((v10 >> 8) & 0xFF0000) - ((a2 >> 8) & 0xFF0000);
        }
      }
      if ( v11 >= 0 )
        break;
      v5 = (_QWORD *)*v5;
      if ( v5 == a1 )
        return v6;
    }
    *a4 = v9;
    LOBYTE(v6) = v11 <= 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18001dc28  push    rbx
0x18001dc2a  push    rbp
0x18001dc2b  push    rsi
0x18001dc2c  push    rdi
0x18001dc2d  mov     r8, [rcx]
0x18001dc30  xor     r10d, r10d
0x18001dc33  mov     [r9], r10
0x18001dc36  mov     rdi, r9
0x18001dc39  mov     r11, rcx
0x18001dc3c  cmp     r8, rcx
0x18001dc3f  jz      short loc_18001DCAB
0x18001dc41  movzx   esi, dl
0x18001dc44  mov     ebp, 0FF0000h
0x18001dc49  cmp     [rsp+20h+arg_20], r10d
0x18001dc4e  lea     rbx, [r8-10h]
0x18001dc52  cmovz   rbx, r8
0x18001dc56  mov     r9d, [rbx+20h]
0x18001dc5a  movzx   ecx, r9b
0x18001dc5e  sub     ecx, esi
0x18001dc60  jnz     short loc_18001DC94
0x18001dc62  mov     eax, edx
0x18001dc64  mov     ecx, r9d
0x18001dc67  and     eax, 0FF00h
0x18001dc6c  and     ecx, 0FF00h
0x18001dc72  sub     ecx, eax
0x18001dc74  jnz     short loc_18001DC94
0x18001dc76  mov     ecx, r9d
0x18001dc79  mov     eax, edx
0x18001dc7b  and     ecx, ebp
0x18001dc7d  and     eax, ebp
0x18001dc7f  sub     ecx, eax
0x18001dc81  jnz     short loc_18001DC94
0x18001dc83  mov     ecx, r9d
0x18001dc86  mov     eax, edx
0x18001dc88  shr     ecx, 8
0x18001dc8b  shr     eax, 8
0x18001dc8e  and     ecx, ebp
0x18001dc90  and     eax, ebp
0x18001dc92  sub     ecx, eax
0x18001dc94  test    ecx, ecx
0x18001dc96  jns     short loc_18001DCA2
0x18001dc98  mov     r8, [r8]
0x18001dc9b  cmp     r8, r11
0x18001dc9e  jnz     short loc_18001DC49
0x18001dca0  jmp     short loc_18001DCAB
0x18001dca2  test    ecx, ecx
0x18001dca4  mov     [rdi], rbx
0x18001dca7  setle   r10b
0x18001dcab  mov     eax, r10d
0x18001dcae  pop     rdi
0x18001dcaf  pop     rsi
0x18001dcb0  pop     rbp
0x18001dcb1  pop     rbx
0x18001dcb2  retn
```
