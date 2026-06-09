# mciEatToken

- ea: `0x180014ca8`
- end: `0x180014dfd`
- name: `mciEatToken`
- size: `341`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800100b0`
- `0x180010de8`
- `0x18001213c`
- `0x180015480`

## callees

- `0x180014ca8`
- `0x18001a408`

## pseudocode

```c
__int64 __fastcall mciEatToken(__int16 **a1, __int16 a2, __int64 *a3, int a4)
{
  __int16 *v4; // rbx
  int v7; // eax
  int v8; // r10d
  int v9; // ebp
  unsigned __int64 v11; // rdi
  __int64 v12; // rax
  _WORD *v13; // rcx
  __int16 *v14; // rax
  int v15; // r8d
  _WORD *v16; // r9
  __int16 v17; // dx

  v4 = *a1;
  *a3 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 1;
  while ( 1 )
  {
    if ( *v4 == a2 && !v7 )
      goto LABEL_22;
    if ( !*v4 )
      break;
    if ( *v4 == 34 && v9 )
    {
      if ( v7 )
      {
        if ( v4[1] == 34 )
          ++v4;
        else
          v7 = 0;
      }
      else
      {
        v7 = 1;
        v8 = 1;
      }
    }
    else if ( !v7 )
    {
      if ( v8 )
        return 305;
      v9 = 0;
    }
    ++v4;
  }
  if ( v7 )
    return 294;
  if ( *v4 != a2 && a4 )
    return 0;
LABEL_22:
  v11 = 2LL * ((unsigned int)(v4 - *a1) + 1);
  if ( v11 <= 0xFFFFFFFF )
  {
    v12 = winmmAlloc((unsigned int)v11);
    *a3 = v12;
    v13 = (_WORD *)v12;
    if ( v12 )
    {
      v14 = *a1;
      v15 = 0;
      if ( *a1 != v4 )
      {
        v16 = &v13[v11 / 2];
        do
        {
          if ( v13 < v16 )
          {
            v17 = *v14;
            if ( *v14 == 34 && v9 )
            {
              if ( v15 )
              {
                if ( v14[1] == 34 )
                {
                  ++v14;
                  *v13++ = 34;
                }
                else
                {
                  v15 = 0;
                }
              }
              else
              {
                v15 = 1;
              }
              ++v14;
            }
            else
            {
              ++v14;
              *v13++ = v17;
            }
          }
        }
        while ( v14 != v4 );
      }
      *v13 = 0;
      if ( *v4 )
        ++v4;
      *a1 = v4;
      return 0;
    }
  }
  return 264;
}

```

## disassembly

```asm
0x180014ca8  push    rbx
0x180014caa  push    rbp
0x180014cab  push    rsi
0x180014cac  push    rdi
0x180014cad  push    r12
0x180014caf  push    r14
0x180014cb1  push    r15
0x180014cb3  sub     rsp, 20h
0x180014cb7  mov     rbx, [rcx]
0x180014cba  xor     r15d, r15d
0x180014cbd  mov     rsi, r8
0x180014cc0  mov     [r8], r15
0x180014cc3  mov     r14, rcx
0x180014cc6  mov     eax, r15d
0x180014cc9  mov     r10d, r15d
0x180014ccc  lea     ebp, [r15+1]
0x180014cd0  lea     r12d, [r15+22h]
0x180014cd4  cmp     [rbx], dx
0x180014cd7  jnz     short loc_180014CDD
0x180014cd9  test    eax, eax
0x180014cdb  jz      short loc_180014D48
0x180014cdd  cmp     [rbx], r15w
0x180014ce1  jz      short loc_180014D29
0x180014ce3  cmp     [rbx], r12w
0x180014ce7  jnz     short loc_180014D0D
0x180014ce9  test    ebp, ebp
0x180014ceb  jz      short loc_180014D0D
0x180014ced  test    eax, eax
0x180014cef  jz      short loc_180014D03
0x180014cf1  cmp     [rbx+2], r12w
0x180014cf6  jnz     short loc_180014CFE
0x180014cf8  add     rbx, 2
0x180014cfc  jmp     short loc_180014D19
0x180014cfe  mov     eax, r15d
0x180014d01  jmp     short loc_180014D19
0x180014d03  mov     eax, 1
0x180014d08  mov     r10d, eax
0x180014d0b  jmp     short loc_180014D19
0x180014d0d  test    eax, eax
0x180014d0f  jnz     short loc_180014D19
0x180014d11  test    r10d, r10d
0x180014d14  jnz     short loc_180014D1F
0x180014d16  mov     ebp, r15d
0x180014d19  add     rbx, 2
0x180014d1d  jmp     short loc_180014CD4
0x180014d1f  mov     eax, 131h
0x180014d24  jmp     loc_180014DEE
0x180014d29  test    eax, eax
0x180014d2b  jz      short loc_180014D37
0x180014d2d  mov     eax, 126h
0x180014d32  jmp     loc_180014DEE
0x180014d37  cmp     [rbx], dx
0x180014d3a  jz      short loc_180014D48
0x180014d3c  test    r9d, r9d
0x180014d3f  jz      short loc_180014D48
0x180014d41  xor     eax, eax
0x180014d43  jmp     loc_180014DEE
0x180014d48  mov     rax, rbx
0x180014d4b  sub     rax, [rcx]
0x180014d4e  sar     rax, 1
0x180014d51  inc     eax
0x180014d53  lea     rdi, [rax+rax]
0x180014d57  mov     eax, 0FFFFFFFFh
0x180014d5c  cmp     rdi, rax
0x180014d5f  ja      loc_180014DE9
0x180014d65  mov     ecx, edi; Size
0x180014d67  call    winmmAlloc
0x180014d6c  mov     [rsi], rax
0x180014d6f  mov     rcx, rax
0x180014d72  test    rax, rax
0x180014d75  jz      short loc_180014DE9
0x180014d77  mov     rax, [r14]
0x180014d7a  mov     r8d, r15d
0x180014d7d  cmp     rax, rbx
0x180014d80  jz      short loc_180014DD3
0x180014d82  lea     r9, [rdi+rcx]
0x180014d86  cmp     rcx, r9
0x180014d89  jnb     short loc_180014DCE
0x180014d8b  movzx   edx, word ptr [rax]
0x180014d8e  cmp     dx, r12w
0x180014d92  jnz     short loc_180014DC3
0x180014d94  test    ebp, ebp
0x180014d96  jz      short loc_180014DC3
0x180014d98  test    r8d, r8d
0x180014d9b  jz      short loc_180014DB7
0x180014d9d  cmp     [rax+2], r12w
0x180014da2  jnz     short loc_180014DB2
0x180014da4  add     rax, 2
0x180014da8  mov     [rcx], r12w
0x180014dac  add     rcx, 2
0x180014db0  jmp     short loc_180014DBD
0x180014db2  mov     r8d, r15d
0x180014db5  jmp     short loc_180014DBD
0x180014db7  mov     r8d, 1
0x180014dbd  add     rax, 2
0x180014dc1  jmp     short loc_180014DCE
0x180014dc3  add     rax, 2
0x180014dc7  mov     [rcx], dx
0x180014dca  add     rcx, 2
0x180014dce  cmp     rax, rbx
0x180014dd1  jnz     short loc_180014D86
0x180014dd3  mov     [rcx], r15w
0x180014dd7  cmp     [rbx], r15w
0x180014ddb  jz      short loc_180014DE1
0x180014ddd  add     rbx, 2
0x180014de1  mov     [r14], rbx
0x180014de4  jmp     loc_180014D41
0x180014de9  mov     eax, 108h
0x180014dee  add     rsp, 20h
0x180014df2  pop     r15
0x180014df4  pop     r14
0x180014df6  pop     r12
0x180014df8  pop     rdi
0x180014df9  pop     rsi
0x180014dfa  pop     rbp
0x180014dfb  pop     rbx
0x180014dfc  retn
```
