# MinAsn1ExtractContent

- ea: `0x18004dd2c`
- end: `0x18004ddf3`
- name: `MinAsn1ExtractContent`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180014ec4`
- `0x1800152bc`
- `0x180015624`
- `0x18002151c`
- `0x180045408`
- `0x1800457dc`
- `0x18004c6f4`
- `0x18004c91c`
- `0x18004ca40`
- `0x18004cc70`
- `0x18004ce44`
- `0x18004d040`
- `0x18004d198`
- `0x18004db40`
- `0x18004de78`
- `0x18004e328`

## callees

- `0x18004dd2c`

## pseudocode

```c
__int64 __fastcall MinAsn1ExtractContent(_BYTE *a1, int a2, unsigned int *a3, _QWORD *a4)
{
  unsigned __int8 *v6; // r10
  char v7; // al
  unsigned int v8; // edx
  unsigned int v9; // ecx
  int v10; // r11d
  char v11; // al
  char v12; // al
  unsigned __int8 v14; // al
  int v15; // r9d
  unsigned int v16; // r8d
  unsigned __int8 *v17; // rdi
  int v18; // ebx
  int v19; // eax

  if ( a2 )
  {
    v6 = a1 + 1;
    v7 = *a1 & 0x1F;
    v8 = a2 - 1;
    v9 = 1;
    if ( v7 == 31 )
    {
      v10 = 2;
      while ( v8 )
      {
        v11 = *v6;
        --v8;
        ++v6;
        if ( v11 >= 0 )
          goto LABEL_8;
        ++v10;
      }
    }
    else
    {
      v10 = 1;
LABEL_8:
      if ( v8 )
      {
        v12 = *v6;
        if ( *v6 == 0x80 )
          return 4294967293LL;
        if ( v12 >= 0 )
        {
          v16 = *v6;
        }
        else
        {
          v14 = v12 & 0x7F;
          if ( v14 > 4u )
            return 0xFFFFFFFFLL;
          v15 = v14;
          if ( v14 >= v8 )
            return 4294967294LL;
          v16 = 0;
          v17 = v6 + 1;
          v18 = v14;
          if ( v14 )
          {
            do
            {
              v19 = *v17;
              --v18;
              ++v17;
              v16 = v19 + (v16 << 8);
            }
            while ( v18 > 0 );
          }
          v9 = v15 + 1;
        }
        if ( v16 <= v8 - v9 )
        {
          *a3 = v16;
          *a4 = &v6[v9];
          return v9 + v10;
        }
      }
    }
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x18004dd2c  push    rbx
0x18004dd2e  push    rsi
0x18004dd2f  push    rdi
0x18004dd30  push    r14
0x18004dd32  mov     rsi, r9
0x18004dd35  mov     r14, r8
0x18004dd38  test    edx, edx
0x18004dd3a  jz      loc_18004DDE7
0x18004dd40  mov     al, [rcx]
0x18004dd42  lea     r10, [rcx+1]
0x18004dd46  or      r8d, 0FFFFFFFFh
0x18004dd4a  and     al, 1Fh
0x18004dd4c  add     edx, r8d
0x18004dd4f  mov     ecx, 1
0x18004dd54  cmp     al, 1Fh
0x18004dd56  jnz     short loc_18004DD77
0x18004dd58  lea     r11d, [rcx+1]
0x18004dd5c  test    edx, edx
0x18004dd5e  jz      loc_18004DDE7
0x18004dd64  movzx   eax, byte ptr [r10]
0x18004dd68  add     edx, r8d
0x18004dd6b  add     r10, rcx
0x18004dd6e  test    al, 80h
0x18004dd70  jz      short loc_18004DD7A
0x18004dd72  add     r11d, ecx
0x18004dd75  jmp     short loc_18004DD5C
0x18004dd77  mov     r11d, ecx
0x18004dd7a  cmp     edx, ecx
0x18004dd7c  jb      short loc_18004DDE7
0x18004dd7e  movzx   eax, byte ptr [r10]
0x18004dd82  cmp     al, 80h
0x18004dd84  jnz     short loc_18004DD8D
0x18004dd86  mov     eax, 0FFFFFFFDh
0x18004dd8b  jmp     short loc_18004DDEC
0x18004dd8d  test    al, al
0x18004dd8f  jns     short loc_18004DDCC
0x18004dd91  and     al, 7Fh
0x18004dd93  cmp     al, 4
0x18004dd95  jbe     short loc_18004DD9C
0x18004dd97  or      eax, 0FFFFFFFFh
0x18004dd9a  jmp     short loc_18004DDEC
0x18004dd9c  movzx   r9d, al
0x18004dda0  cmp     r9d, edx
0x18004dda3  jnb     short loc_18004DDE7
0x18004dda5  xor     r8d, r8d
0x18004dda8  lea     rdi, [r10+1]
0x18004ddac  mov     ebx, r9d
0x18004ddaf  test    al, al
0x18004ddb1  jz      short loc_18004DDC6
0x18004ddb3  movzx   eax, byte ptr [rdi]
0x18004ddb6  sub     ebx, ecx
0x18004ddb8  shl     r8d, 8
0x18004ddbc  add     rdi, rcx
0x18004ddbf  add     r8d, eax
0x18004ddc2  test    ebx, ebx
0x18004ddc4  jg      short loc_18004DDB3
0x18004ddc6  lea     ecx, [r9+1]
0x18004ddca  jmp     short loc_18004DDCF
0x18004ddcc  mov     r8d, eax
0x18004ddcf  sub     edx, ecx
0x18004ddd1  cmp     r8d, edx
0x18004ddd4  ja      short loc_18004DDE7
0x18004ddd6  mov     eax, ecx
0x18004ddd8  add     rax, r10
0x18004dddb  mov     [r14], r8d
0x18004ddde  mov     [rsi], rax
0x18004dde1  lea     eax, [rcx+r11]
0x18004dde5  jmp     short loc_18004DDEC
0x18004dde7  mov     eax, 0FFFFFFFEh
0x18004ddec  pop     r14
0x18004ddee  pop     rdi
0x18004ddef  pop     rsi
0x18004ddf0  pop     rbx
0x18004ddf1  retn
```
