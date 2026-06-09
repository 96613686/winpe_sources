# FindRefEntry

- ea: `0x1800157ec`
- end: `0x1800158c3`
- name: `FindRefEntry`
- size: `215`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180011850`
- `0x1800151ec`
- `0x1800155fc`
- `0x180016d00`
- `0x18001b668`
- `0x18001bb28`
- `0x18001decc`

## callees

- `0x1800157ec`

## pseudocode

```c
__int64 __fastcall FindRefEntry(__int64 **a1, unsigned int a2, __int64 a3, unsigned int a4, __int64 a5, _QWORD *a6)
{
  unsigned int v6; // r11d
  __int64 *v7; // r8
  unsigned int v10; // edx
  int v11; // ecx
  unsigned int v12; // edx
  int v13; // ecx

  v6 = 0;
  v7 = *a1;
  *a6 = 0;
  if ( v7 != (__int64 *)a1 )
  {
    while ( 1 )
    {
      v10 = *((_DWORD *)v7 + 4);
      v11 = (unsigned __int8)v10 - (unsigned __int8)a4;
      if ( (unsigned __int8)v10 == (unsigned __int8)a4 )
      {
        v11 = (v7[2] & 0xFF00) - (a4 & 0xFF00);
        if ( (v7[2] & 0xFF00) == (a4 & 0xFF00) )
        {
          v11 = (v10 & 0xFF0000) - (a4 & 0xFF0000);
          if ( (v10 & 0xFF0000) == (a4 & 0xFF0000) )
            v11 = ((v10 >> 8) & 0xFF0000) - ((a4 >> 8) & 0xFF0000);
        }
      }
      if ( v11 >= 0 )
      {
        if ( v11 > 0 )
        {
          *a6 = v7;
          return v6;
        }
        v12 = *((_DWORD *)v7 + 6);
        v13 = (unsigned __int8)v12 - (unsigned __int8)a2;
        if ( (unsigned __int8)v12 == (unsigned __int8)a2 )
        {
          v13 = (v7[3] & 0xFF00) - (a2 & 0xFF00);
          if ( (v7[3] & 0xFF00) == (a2 & 0xFF00) )
          {
            v13 = (v12 & 0xFF0000) - (a2 & 0xFF0000);
            if ( (v12 & 0xFF0000) == (a2 & 0xFF0000) )
              v13 = ((v12 >> 8) & 0xFF0000) - ((a2 >> 8) & 0xFF0000);
          }
        }
        if ( v13 >= 0 )
          break;
      }
      v7 = (__int64 *)*v7;
      if ( v7 == (__int64 *)a1 )
        return v6;
    }
    *a6 = v7;
    if ( v13 <= 0 )
      return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x1800157ec  push    rbx
0x1800157ee  push    rbp
0x1800157ef  push    rsi
0x1800157f0  push    rdi
0x1800157f1  push    r14
0x1800157f3  mov     r10, [rsp+28h+arg_28]
0x1800157f8  xor     r11d, r11d
0x1800157fb  mov     r8, [rcx]
0x1800157fe  mov     edi, edx
0x180015800  mov     rbx, rcx
0x180015803  mov     [r10], r11
0x180015806  cmp     r8, rcx
0x180015809  jz      loc_1800158B9
0x18001580f  movzx   esi, r9b
0x180015813  mov     ebp, 0FF0000h
0x180015818  mov     r14d, 0FF00h
0x18001581e  mov     edx, [r8+10h]
0x180015822  movzx   ecx, dl
0x180015825  sub     ecx, esi
0x180015827  jnz     short loc_180015856
0x180015829  mov     eax, r9d
0x18001582c  mov     ecx, edx
0x18001582e  and     eax, r14d
0x180015831  and     ecx, r14d
0x180015834  sub     ecx, eax
0x180015836  jnz     short loc_180015856
0x180015838  mov     ecx, edx
0x18001583a  mov     eax, r9d
0x18001583d  and     ecx, ebp
0x18001583f  and     eax, ebp
0x180015841  sub     ecx, eax
0x180015843  jnz     short loc_180015856
0x180015845  mov     ecx, edx
0x180015847  mov     eax, r9d
0x18001584a  shr     ecx, 8
0x18001584d  shr     eax, 8
0x180015850  and     ecx, ebp
0x180015852  and     eax, ebp
0x180015854  sub     ecx, eax
0x180015856  test    ecx, ecx
0x180015858  js      short loc_180015899
0x18001585a  jg      short loc_1800158B6
0x18001585c  mov     edx, [r8+18h]
0x180015860  movzx   ecx, dl
0x180015863  movzx   eax, dil
0x180015867  sub     ecx, eax
0x180015869  jnz     short loc_180015895
0x18001586b  mov     eax, edi
0x18001586d  mov     ecx, edx
0x18001586f  and     eax, r14d
0x180015872  and     ecx, r14d
0x180015875  sub     ecx, eax
0x180015877  jnz     short loc_180015895
0x180015879  mov     ecx, edx
0x18001587b  mov     eax, edi
0x18001587d  and     ecx, ebp
0x18001587f  and     eax, ebp
0x180015881  sub     ecx, eax
0x180015883  jnz     short loc_180015895
0x180015885  mov     ecx, edx
0x180015887  mov     eax, edi
0x180015889  shr     ecx, 8
0x18001588c  shr     eax, 8
0x18001588f  and     ecx, ebp
0x180015891  and     eax, ebp
0x180015893  sub     ecx, eax
0x180015895  test    ecx, ecx
0x180015897  jns     short loc_1800158A7
0x180015899  mov     r8, [r8]
0x18001589c  cmp     r8, rbx
0x18001589f  jnz     loc_18001581E
0x1800158a5  jmp     short loc_1800158B9
0x1800158a7  mov     [r10], r8
0x1800158aa  test    ecx, ecx
0x1800158ac  jg      short loc_1800158B9
0x1800158ae  mov     r11d, 1
0x1800158b4  jmp     short loc_1800158B9
0x1800158b6  mov     [r10], r8
0x1800158b9  mov     eax, r11d
0x1800158bc  pop     r14
0x1800158be  pop     rdi
0x1800158bf  pop     rsi
0x1800158c0  pop     rbp
0x1800158c1  pop     rbx
0x1800158c2  retn
```
