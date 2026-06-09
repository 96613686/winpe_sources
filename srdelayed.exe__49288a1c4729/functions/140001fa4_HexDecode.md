# HexDecode

- ea: `0x140001fa4`
- end: `0x14000205e`
- name: `HexDecode`
- size: `186`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400028a4`

## callees

- `0x1400012f0`
- `0x140001ab4`
- `0x140001fa4`

## pseudocode

```c
__int64 __fastcall HexDecode(unsigned __int16 *a1, __int64 a2)
{
  __int64 v2; // r8
  unsigned __int16 *v3; // rbx
  unsigned __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  unsigned __int16 v9; // r9
  __int64 v10; // rsi
  int v11; // eax
  unsigned __int16 v13; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 v14; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v3 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
  v5 = (unsigned __int64)&v3[(unsigned __int64)*a1 >> 1];
  while ( (unsigned __int64)v3 < v5 )
  {
    v6 = *v3;
    if ( (_WORD)v6 == 37 && (unsigned __int64)(v3 + 1) < v5 && (unsigned __int64)(v3 + 2) < v5 )
    {
      v7 = v3[1];
      v14 = v3[2];
      v13 = v7;
      v8 = FromHex(v7, &v13, v2);
      LODWORD(v2) = v8;
      if ( v8 < 0 )
        return (unsigned int)v2;
      LODWORD(v2) = FromHex(v9, &v14, (unsigned int)v8);
      if ( (int)v2 < 0 )
        return (unsigned int)v2;
      v6 = v13;
      v10 = 6;
      LOWORD(v6) = v14 | (16 * v13);
    }
    else
    {
      v10 = 2;
    }
    v11 = AddToUnicodeString(a2, v6);
    v2 = (unsigned int)v11;
    if ( v11 < 0 )
      return (unsigned int)v2;
    v3 = (unsigned __int16 *)((char *)v3 + v10);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140001fa4  mov     [rsp+arg_8], rbx
0x140001fa9  push    rbp
0x140001faa  push    rsi
0x140001fab  push    rdi
0x140001fac  sub     rsp, 20h
0x140001fb0  movzx   eax, word ptr [rcx]
0x140001fb3  xor     r8d, r8d
0x140001fb6  mov     rbx, [rcx+8]
0x140001fba  mov     rbp, rdx
0x140001fbd  shr     rax, 1
0x140001fc0  lea     rdi, [rbx+rax*2]
0x140001fc4  jmp     short loc_140002045
0x140001fc6  movzx   edx, word ptr [rbx]
0x140001fc9  cmp     dx, 25h ; '%'
0x140001fcd  jnz     short loc_14000202E
0x140001fcf  lea     rcx, [rbx+2]
0x140001fd3  cmp     rcx, rdi
0x140001fd6  jnb     short loc_14000202E
0x140001fd8  lea     rax, [rbx+4]
0x140001fdc  cmp     rax, rdi
0x140001fdf  jnb     short loc_14000202E
0x140001fe1  movzx   r9d, word ptr [rax]
0x140001fe5  lea     rdx, [rsp+38h+arg_0]
0x140001fea  movzx   ecx, word ptr [rcx]
0x140001fed  mov     [rsp+38h+arg_10], r9w
0x140001ff3  mov     [rsp+38h+arg_0], cx
0x140001ff8  call    FromHex
0x140001ffd  mov     r8d, eax
0x140002000  test    eax, eax
0x140002002  js      short loc_14000204E
0x140002004  lea     rdx, [rsp+38h+arg_10]
0x140002009  movzx   ecx, r9w
0x14000200d  call    FromHex
0x140002012  mov     r8d, eax
0x140002015  test    eax, eax
0x140002017  js      short loc_14000204E
0x140002019  movzx   edx, [rsp+38h+arg_0]
0x14000201e  mov     esi, 6
0x140002023  shl     dx, 4
0x140002027  or      dx, [rsp+38h+arg_10]
0x14000202c  jmp     short loc_140002033
0x14000202e  mov     esi, 2
0x140002033  mov     rcx, rbp
0x140002036  call    AddToUnicodeString
0x14000203b  mov     r8d, eax
0x14000203e  test    eax, eax
0x140002040  js      short loc_14000204E
0x140002042  add     rbx, rsi
0x140002045  cmp     rbx, rdi
0x140002048  jb      loc_140001FC6
0x14000204e  mov     rbx, [rsp+38h+arg_8]
0x140002053  mov     eax, r8d
0x140002056  add     rsp, 20h
0x14000205a  pop     rdi
0x14000205b  pop     rsi
0x14000205c  pop     rbp
0x14000205d  retn
```
