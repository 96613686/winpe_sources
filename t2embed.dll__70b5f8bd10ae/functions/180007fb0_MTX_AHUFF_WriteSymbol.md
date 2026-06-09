# MTX_AHUFF_WriteSymbol

- ea: `0x180007fb0`
- end: `0x180008229`
- name: `MTX_AHUFF_WriteSymbol`
- size: `633`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006c10`
- `0x180006d30`

## callees

- `0x180007fb0`
- `0x180009770`
- `0x18000ddd4`
- `0x18001c9ec`
- `0x18002a590`

## import_xrefs

- `msvcrt!longjmp` at `0x180008152`
- `msvcrt!longjmp` at `0x1800081da`
- `msvcrt!longjmp` at `0x180008152`
- `msvcrt!longjmp` at `0x1800081da`

## pseudocode

```c
int __fastcall MTX_AHUFF_WriteSymbol(__int64 *a1, __int16 a2)
{
  __int64 v3; // r14
  int v4; // edi
  __int64 v5; // rbx
  __int64 v6; // rbp
  unsigned __int16 v7; // si
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // ecx
  int v11; // edx
  __int64 i; // r14
  __int16 v13; // di
  __int64 v14; // rax
  int v15; // ebx
  bool v16; // zf
  __int64 v17; // rbp
  __int64 v18; // rcx
  int result; // eax
  __int16 v20; // bp
  __int64 v21; // r8
  _BYTE v22[56]; // [rsp+20h] [rbp-68h]

  v3 = *a1;
  v4 = 0;
  v5 = a1[4];
  v6 = *(__int16 *)(a1[1] + 2LL * a2);
  if ( *(_WORD *)(*a1 + 12 * v6 + 6) != a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v7 = v6;
  do
  {
    v8 = v4;
    v9 = *(__int16 *)(v3 + 12LL * (__int16)v6);
    v16 = *(_WORD *)(v3 + 12 * v9 + 4) == (unsigned __int16)v6;
    LOWORD(v6) = *(_WORD *)(v3 + 12LL * (__int16)v6);
    ++v4;
    v22[v8] = v16;
  }
  while ( (_DWORD)v9 != 1 );
  if ( v4 >= 50 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  do
  {
    v10 = *(_DWORD *)(v5 + 8);
    if ( v10 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_21:
      if ( *(int *)(v5 + 12) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      longjmp((_JBTYPE *)(*(_QWORD *)(v5 + 40) + 48LL), 3321);
    }
    v11 = *(_DWORD *)(v5 + 12);
    if ( v11 < 0 )
      goto LABEL_21;
    *(_WORD *)(v5 + 26) *= 2;
    if ( v22[--v4] )
      *(_WORD *)(v5 + 26) |= 1u;
    if ( ++*(_WORD *)(v5 + 24) == 8 )
    {
      if ( v10 >= (unsigned int)v11 )
      {
        v21 = ((unsigned int)v11 >> 1) + v10;
        if ( (unsigned int)v21 < v10 )
          goto LABEL_32;
        if ( (unsigned int)v21 > 0x7FFFFFFF )
        {
          *(_DWORD *)(v5 + 12) = -1;
LABEL_32:
          longjmp((_JBTYPE *)(*(_QWORD *)(v5 + 40) + 48LL), 3321);
        }
        *(_DWORD *)(v5 + 12) = v21;
        *(_QWORD *)v5 = MTX_mem_realloc(*(_QWORD *)(v5 + 40), *(_QWORD *)v5, v21);
      }
      *(_BYTE *)((int)(*(_DWORD *)(v5 + 8))++ + *(_QWORD *)v5) = *(_BYTE *)(v5 + 26);
      ++*(_DWORD *)(v5 + 28);
      *(_WORD *)(v5 + 24) = 0;
    }
  }
  while ( v4 );
  for ( i = *a1; v7 != 1; *(_DWORD *)(i + 4 * v18 + 8) = v15 + 1 )
  {
    v13 = v7 - 1;
    v14 = (__int16)(v7 - 1);
    v15 = *(_DWORD *)(i + 12LL * (__int16)v7 + 8);
    v16 = *(_DWORD *)(i + 12 * v14 + 8) == v15;
    v17 = i + 12 * v14;
    if ( *(_DWORD *)(v17 + 8) < v15 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v16 = *(_DWORD *)(v17 + 8) == v15;
    }
    if ( v16 )
    {
      do
        v20 = v13--;
      while ( *(_DWORD *)(i + 12LL * v13 + 8) == v15 );
      if ( v20 < 1 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      else if ( v20 > 1 )
      {
        SwapNodes(a1, v7, (unsigned __int16)v20);
        v7 = v20;
      }
    }
    v18 = 3LL * (__int16)v7;
    v7 = *(_WORD *)(i + 12LL * (__int16)v7);
  }
  ++*(_DWORD *)(i + 12LL * v7 + 8);
  result = *(_DWORD *)(i + 12LL * *(__int16 *)(i + 12LL * v7 + 2) + 8)
         + *(_DWORD *)(i + 12LL * *(__int16 *)(i + 12LL * v7 + 4) + 8);
  if ( *(_DWORD *)(i + 12LL * v7 + 8) != result )
    return MicrosoftTelemetryAssertTriggeredNoArgs();
  return result;
}

```

## disassembly

```asm
0x180007fb0  mov     [rsp+arg_10], rbx
0x180007fb5  push    rbp
0x180007fb6  push    rsi
0x180007fb7  push    rdi
0x180007fb8  push    r14
0x180007fba  push    r15
0x180007fbc  sub     rsp, 60h
0x180007fc0  mov     rax, cs:__security_cookie
0x180007fc7  xor     rax, rsp
0x180007fca  mov     [rsp+88h+var_30], rax
0x180007fcf  mov     rax, [rcx+8]
0x180007fd3  mov     r15, rcx
0x180007fd6  mov     r14, [rcx]
0x180007fd9  xor     edi, edi
0x180007fdb  mov     rbx, [rcx+20h]
0x180007fdf  movsx   r8, dx
0x180007fe3  movsx   rbp, word ptr [rax+r8*2]
0x180007fe8  lea     rcx, ds:0[rbp*2]
0x180007ff0  add     rcx, rbp
0x180007ff3  cmp     [r14+rcx*4+6], dx
0x180007ff9  jnz     loc_1800081F3
0x180007fff  movzx   esi, bp
0x180008002  movsx   rax, bp
0x180008006  lea     rcx, [rax+rax*2]
0x18000800a  movsxd  rax, edi
0x18000800d  movsx   rdx, word ptr [r14+rcx*4]
0x180008012  lea     rcx, [rdx+rdx*2]
0x180008016  cmp     [r14+rcx*4+4], bp
0x18000801c  movzx   ebp, dx
0x18000801f  setz    cl
0x180008022  inc     edi
0x180008024  mov     [rsp+rax+88h+var_68], cl
0x180008028  cmp     edx, 1
0x18000802b  jnz     short loc_180008002
0x18000802d  cmp     edi, 32h ; '2'
0x180008030  jge     loc_1800081FD
0x180008036  nop     word ptr [rax+rax+00000000h]
0x180008040  mov     ecx, [rbx+8]
0x180008043  test    ecx, ecx
0x180008045  js      loc_180008135
0x18000804b  mov     edx, [rbx+0Ch]
0x18000804e  test    edx, edx
0x180008050  js      loc_18000813A
0x180008056  shl     word ptr [rbx+1Ah], 1
0x18000805a  dec     edi
0x18000805c  movsxd  rax, edi
0x18000805f  cmp     [rsp+rax+88h+var_68], 0
0x180008064  jz      short loc_18000806B
0x180008066  or      word ptr [rbx+1Ah], 1
0x18000806b  inc     word ptr [rbx+18h]
0x18000806f  cmp     word ptr [rbx+18h], 8
0x180008074  jz      loc_180008159
0x18000807a  test    edi, edi
0x18000807c  jnz     short loc_180008040
0x18000807e  mov     r14, [r15]
0x180008081  cmp     si, 1
0x180008085  jz      short loc_1800080DC
0x180008087  nop     word ptr [rax+rax+00000000h]
0x180008090  movsx   rax, si
0x180008094  lea     edi, [rsi-1]
0x180008097  lea     rcx, [rax+rax*2]
0x18000809b  movsx   rax, di
0x18000809f  mov     ebx, [r14+rcx*4+8]
0x1800080a4  lea     rcx, [rax+rax*2]
0x1800080a8  cmp     [r14+rcx*4+8], ebx
0x1800080ad  lea     rbp, [r14+rcx*4]
0x1800080b1  jge     short loc_1800080BB
0x1800080b3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800080b8  cmp     [rbp+8], ebx
0x1800080bb  jz      loc_180008180
0x1800080c1  movsx   rax, si
0x1800080c5  lea     rcx, [rax+rax*2]
0x1800080c9  movzx   esi, word ptr [r14+rcx*4]
0x1800080ce  lea     eax, [rbx+1]
0x1800080d1  mov     [r14+rcx*4+8], eax
0x1800080d6  cmp     si, 1
0x1800080da  jnz     short loc_180008090
0x1800080dc  movzx   eax, si
0x1800080df  lea     rcx, [rax+rax*2]
0x1800080e3  inc     dword ptr [r14+rcx*4+8]
0x1800080e8  movsx   rax, word ptr [r14+rcx*4+4]
0x1800080ee  mov     r8d, [r14+rcx*4+8]
0x1800080f3  lea     rdx, [rax+rax*2]
0x1800080f7  movsx   rax, word ptr [r14+rcx*4+2]
0x1800080fd  lea     rcx, [rax+rax*2]
0x180008101  mov     eax, [r14+rdx*4+8]
0x180008106  add     eax, [r14+rcx*4+8]
0x18000810b  cmp     r8d, eax
0x18000810e  jnz     loc_18000821F
0x180008114  mov     rcx, [rsp+88h+var_30]
0x180008119  xor     rcx, rsp; StackCookie
0x18000811c  call    __security_check_cookie
0x180008121  mov     rbx, [rsp+88h+arg_10]
0x180008129  add     rsp, 60h
0x18000812d  pop     r15
0x18000812f  pop     r14
0x180008131  pop     rdi
0x180008132  pop     rsi
0x180008133  pop     rbp
0x180008134  retn
0x180008135  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000813a  cmp     dword ptr [rbx+0Ch], 0
0x18000813e  jge     short loc_180008145
0x180008140  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008145  mov     rcx, [rbx+28h]
0x180008149  mov     edx, 0CF9h; Value
0x18000814e  add     rcx, 30h ; '0'; Buf
0x180008152  call    cs:__imp_longjmp
0x180008159  cmp     ecx, edx
0x18000815b  jnb     short loc_1800081C2
0x18000815d  movsxd  rdx, dword ptr [rbx+8]
0x180008161  movzx   eax, byte ptr [rbx+1Ah]
0x180008165  mov     rcx, [rbx]
0x180008168  mov     [rdx+rcx], al
0x18000816b  xor     eax, eax
0x18000816d  inc     dword ptr [rbx+8]
0x180008170  inc     dword ptr [rbx+1Ch]
0x180008173  mov     [rbx+18h], ax
0x180008177  jmp     loc_18000807A
0x180008180  movzx   ebp, di
0x180008183  dec     di
0x180008186  movsx   rax, di
0x18000818a  lea     rcx, [rax+rax*2]
0x18000818e  cmp     [r14+rcx*4+8], ebx
0x180008193  jz      short loc_180008180
0x180008195  cmp     bp, 1
0x180008199  jl      short loc_1800081B8
0x18000819b  jle     loc_1800080C1
0x1800081a1  movzx   r8d, bp
0x1800081a5  movzx   edx, si
0x1800081a8  mov     rcx, r15
0x1800081ab  call    SwapNodes
0x1800081b0  movzx   esi, bp
0x1800081b3  jmp     loc_1800080C1
0x1800081b8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800081bd  jmp     loc_1800080C1
0x1800081c2  shr     edx, 1
0x1800081c4  lea     r8d, [rdx+rcx]
0x1800081c8  cmp     r8d, ecx
0x1800081cb  jnb     short loc_1800081E1
0x1800081cd  mov     rcx, [rbx+28h]
0x1800081d1  mov     edx, 0CF9h; Value
0x1800081d6  add     rcx, 30h ; '0'; Buf
0x1800081da  call    cs:__imp_longjmp
0x1800081e1  cmp     r8d, 7FFFFFFFh
0x1800081e8  jbe     short loc_180008207
0x1800081ea  mov     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x1800081f1  jmp     short loc_1800081CD
0x1800081f3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800081f8  jmp     loc_180007FFF
0x1800081fd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008202  jmp     loc_180008040
0x180008207  mov     [rbx+0Ch], r8d
0x18000820b  mov     rdx, [rbx]
0x18000820e  mov     rcx, [rbx+28h]
0x180008212  call    MTX_mem_realloc
0x180008217  mov     [rbx], rax
0x18000821a  jmp     loc_18000815D
0x18000821f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008224  jmp     loc_180008114
```
