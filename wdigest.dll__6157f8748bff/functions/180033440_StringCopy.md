# StringCopy

- ea: `0x180033440`
- end: `0x1800334f8`
- name: `StringCopy`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002ba20`

## callees

- `0x180011fec`
- `0x180033440`
- `0x1800377bc`

## pseudocode

```c
__int64 __fastcall StringCopy(__int64 a1, const void **a2)
{
  unsigned int v3; // ebx
  size_t v4; // rdx
  void *v5; // rsi

  v3 = 0;
  if ( a2 && a2[1] && (v4 = *(unsigned __int16 *)a2, (_WORD)v4) )
  {
    if ( (_WORD)v4 == 0xFFFF )
    {
      return (unsigned int)-1073741811;
    }
    else
    {
      v5 = *(void **)(a1 + 8);
      if ( v5 && *(unsigned __int16 *)(a1 + 2) >= v4 + 1 )
      {
        *(_WORD *)a1 = v4;
        memcpy_0(v5, a2[1], v4);
        *((_BYTE *)v5 + *(unsigned __int16 *)a2) = 0;
      }
      else
      {
        v3 = -1073741789;
        *(_WORD *)a1 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
      }
    }
  }
  else
  {
    *(_WORD *)a1 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180033440  push    rbx
0x180033442  push    rbp
0x180033443  push    rsi
0x180033444  push    rdi
0x180033445  sub     rsp, 28h
0x180033449  xor     ebp, ebp
0x18003344b  mov     rdi, rdx
0x18003344e  mov     r8, rcx
0x180033451  mov     ebx, ebp
0x180033453  test    rdx, rdx
0x180033456  jz      loc_1800334EA
0x18003345c  cmp     [rdx+8], rbp
0x180033460  jz      loc_1800334EA
0x180033466  movzx   edx, word ptr [rdx]
0x180033469  test    dx, dx
0x18003346c  jz      short loc_1800334EA
0x18003346e  mov     eax, 0FFFEh
0x180033473  cmp     dx, ax
0x180033476  jbe     short loc_18003347F
0x180033478  mov     ebx, 0C000000Dh
0x18003347d  jmp     short loc_1800334ED
0x18003347f  mov     rsi, [rcx+8]
0x180033483  test    rsi, rsi
0x180033486  jz      short loc_1800334B1
0x180033488  movzx   ecx, word ptr [rcx+2]
0x18003348c  lea     rax, [rdx+1]
0x180033490  cmp     rcx, rax
0x180033493  jb      short loc_1800334B1
0x180033495  mov     [r8], dx
0x180033499  mov     rcx, rsi; void *
0x18003349c  mov     r8, rdx; Size
0x18003349f  mov     rdx, [rdi+8]; Src
0x1800334a3  call    memcpy_0
0x1800334a8  movzx   eax, word ptr [rdi]
0x1800334ab  mov     [rax+rsi], bpl
0x1800334af  jmp     short loc_1800334ED
0x1800334b1  mov     ebx, 0C0000023h
0x1800334b6  mov     [r8], bp
0x1800334ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334c1  lea     rax, WPP_GLOBAL_Control
0x1800334c8  cmp     rcx, rax
0x1800334cb  jz      short loc_1800334ED
0x1800334cd  test    byte ptr [rcx+1Ch], 1
0x1800334d1  jz      short loc_1800334ED
0x1800334d3  mov     rcx, [rcx+10h]
0x1800334d7  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x1800334de  mov     edx, 0Fh
0x1800334e3  call    WPP_SF_
0x1800334e8  jmp     short loc_1800334ED
0x1800334ea  mov     [rcx], bp
0x1800334ed  mov     eax, ebx
0x1800334ef  add     rsp, 28h
0x1800334f3  pop     rdi
0x1800334f4  pop     rsi
0x1800334f5  pop     rbp
0x1800334f6  pop     rbx
0x1800334f7  retn
```
