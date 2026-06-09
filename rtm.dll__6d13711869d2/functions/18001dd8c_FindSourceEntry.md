# FindSourceEntry

- ea: `0x18001dd8c`
- end: `0x18001de17`
- name: `FindSourceEntry`
- size: `139`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180017f48`
- `0x180018070`
- `0x18001a360`
- `0x18001af20`
- `0x18001c1a8`
- `0x18001cf18`
- `0x18001d378`
- `0x18001de98`
- `0x18001eba0`
- `0x18001ed64`

## callees

- `0x18001dd8c`

## pseudocode

```c
__int64 __fastcall FindSourceEntry(_QWORD **a1, unsigned int a2, __int64 a3, _QWORD *a4, int a5)
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
      v10 = *((_DWORD *)v9 + 26);
      v11 = (unsigned __int8)v10 - (unsigned __int8)a2;
      if ( (unsigned __int8)v10 == (unsigned __int8)a2 )
      {
        v11 = (v9[13] & 0xFF00) - (a2 & 0xFF00);
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
0x18001dd8c  push    rbx
0x18001dd8e  push    rbp
0x18001dd8f  push    rsi
0x18001dd90  push    rdi
0x18001dd91  mov     r8, [rcx]
0x18001dd94  xor     r10d, r10d
0x18001dd97  mov     [r9], r10
0x18001dd9a  mov     rdi, r9
0x18001dd9d  mov     r11, rcx
0x18001dda0  cmp     r8, rcx
0x18001dda3  jz      short loc_18001DE0F
0x18001dda5  movzx   esi, dl
0x18001dda8  mov     ebp, 0FF0000h
0x18001ddad  cmp     [rsp+20h+arg_20], r10d
0x18001ddb2  lea     rbx, [r8-10h]
0x18001ddb6  cmovz   rbx, r8
0x18001ddba  mov     r9d, [rbx+68h]
0x18001ddbe  movzx   ecx, r9b
0x18001ddc2  sub     ecx, esi
0x18001ddc4  jnz     short loc_18001DDF8
0x18001ddc6  mov     eax, edx
0x18001ddc8  mov     ecx, r9d
0x18001ddcb  and     eax, 0FF00h
0x18001ddd0  and     ecx, 0FF00h
0x18001ddd6  sub     ecx, eax
0x18001ddd8  jnz     short loc_18001DDF8
0x18001ddda  mov     ecx, r9d
0x18001dddd  mov     eax, edx
0x18001dddf  and     ecx, ebp
0x18001dde1  and     eax, ebp
0x18001dde3  sub     ecx, eax
0x18001dde5  jnz     short loc_18001DDF8
0x18001dde7  mov     ecx, r9d
0x18001ddea  mov     eax, edx
0x18001ddec  shr     ecx, 8
0x18001ddef  shr     eax, 8
0x18001ddf2  and     ecx, ebp
0x18001ddf4  and     eax, ebp
0x18001ddf6  sub     ecx, eax
0x18001ddf8  test    ecx, ecx
0x18001ddfa  jns     short loc_18001DE06
0x18001ddfc  mov     r8, [r8]
0x18001ddff  cmp     r8, r11
0x18001de02  jnz     short loc_18001DDAD
0x18001de04  jmp     short loc_18001DE0F
0x18001de06  test    ecx, ecx
0x18001de08  mov     [rdi], rbx
0x18001de0b  setle   r10b
0x18001de0f  mov     eax, r10d
0x18001de12  pop     rdi
0x18001de13  pop     rsi
0x18001de14  pop     rbp
0x18001de15  pop     rbx
0x18001de16  retn
```
