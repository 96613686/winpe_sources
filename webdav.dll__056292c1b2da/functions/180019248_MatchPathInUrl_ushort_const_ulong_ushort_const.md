# MatchPathInUrl(ushort const *,ulong,ushort const *)

- ea: `0x180019248`
- end: `0x180019491`
- name: `?MatchPathInUrl@@YAPEBGPEBGK0@Z`
- size: `585`
- prototype: `const unsigned __int16 *__fastcall(wchar_t *String1, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016538`

## callees

- `0x180019248`
- `0x1800224f2`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800192ab`
- `msvcrt!wcsrchr` at `0x1800192bf`
- `msvcrt!wcsrchr` at `0x1800192ab`
- `msvcrt!wcsrchr` at `0x1800192bf`

## pseudocode

```c
wchar_t *__fastcall MatchPathInUrl(wchar_t *String1, unsigned int a2, const unsigned __int16 *a3)
{
  unsigned __int16 v3; // r12
  const unsigned __int16 *v4; // rax
  const unsigned __int16 *v5; // r15
  __int64 v6; // r13
  __int64 v8; // rax
  wchar_t *v10; // rax
  wchar_t *v11; // rax
  __int64 v12; // rax
  wchar_t *v13; // rbx
  const unsigned __int16 *v14; // rdi
  wchar_t *v15; // r14
  wchar_t v16; // ax
  unsigned __int16 v17; // cx
  const wchar_t *v18; // rbp
  wchar_t v19; // cx
  wchar_t *v20; // rdx
  __int64 v21; // rsi

  v3 = *a3;
  v4 = a3 + 1;
  v5 = a3;
  v6 = a2;
  if ( *a3 != 42 )
  {
    if ( v3 == 47 )
      v5 = a3 + 1;
LABEL_17:
    v13 = String1 + 1;
    v14 = v5;
    if ( *String1 != 47 )
      v13 = String1;
    v15 = v13;
    while ( 1 )
    {
      v16 = *v14;
      if ( *v14 == 63 )
      {
        if ( !*v13 )
          return 0;
        if ( *v13 == 47 )
          goto LABEL_59;
        ++v14;
        ++v13;
      }
      else
      {
        if ( v16 == 42 )
          v17 = v14[1];
        else
          v17 = *v14;
        v18 = v14 + 1;
        if ( v16 != 42 )
          v18 = v14;
        if ( v17 )
        {
          v19 = *v18;
          v14 = v18;
          while ( v19 != 42 && v19 != 63 && v19 )
            v19 = *++v14;
          if ( v16 == 42 )
          {
            if ( !*v14 )
            {
              v20 = &v13[v14 - v18];
              if ( v20 > &v15[v6] )
                return 0;
              while ( *v20 != 47 && *v20 && *v13 != 47 && *v13 )
              {
                ++v13;
                ++v20;
              }
            }
            v21 = v14 - v18;
            while ( wcsncmp_0(v13, v18, (unsigned int)v21) )
            {
              if ( !*v13 )
                return 0;
              if ( *v13 == 47 )
                goto LABEL_59;
              ++v13;
            }
          }
          else
          {
            v21 = v14 - v18;
            if ( wcsncmp_0(v13, v18, (unsigned int)v21) )
              goto LABEL_59;
          }
          v13 += v21;
        }
        else
        {
          if ( v16 == 42 )
          {
            while ( *v13 != 47 && *v13 )
              ++v13;
          }
          if ( *v13 == 47 || !*v13 )
            return v13;
LABEL_59:
          if ( v3 == 47 )
            return 0;
          while ( *v15 != 47 && *v15 )
            ++v15;
          if ( !*v15 )
            return 0;
          ++v15;
          v14 = v5;
          v13 = v15;
        }
      }
    }
  }
  if ( !*v4 )
  {
    v8 = -1;
    do
      ++v8;
    while ( String1[v8] );
    return &String1[v8];
  }
  if ( *v4 != 46 || a3[2] )
    goto LABEL_17;
  v10 = wcsrchr(String1, 0x2Fu);
  if ( !v10 )
    v10 = String1;
  v11 = wcsrchr(v10, 0x2Eu);
  if ( v11 && v11[1] )
    return 0;
  v12 = -1;
  do
    ++v12;
  while ( String1[v12] );
  return &String1[v12];
}

```

## disassembly

```asm
0x180019248  push    rbx
0x18001924a  push    rbp
0x18001924b  push    rsi
0x18001924c  push    rdi
0x18001924d  push    r12
0x18001924f  push    r13
0x180019251  push    r14
0x180019253  push    r15
0x180019255  sub     rsp, 28h
0x180019259  movzx   r12d, word ptr [r8]
0x18001925d  lea     rax, [r8+2]
0x180019261  mov     r15, r8
0x180019264  mov     r13d, edx
0x180019267  xor     r8d, r8d
0x18001926a  mov     rsi, rcx
0x18001926d  mov     r9d, 2Fh ; '/'
0x180019273  cmp     r12w, 2Ah ; '*'
0x180019278  jnz     short loc_1800192EA
0x18001927a  cmp     [rax], r8w
0x18001927e  jnz     short loc_180019297
0x180019280  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019284  inc     rax
0x180019287  cmp     [rcx+rax*2], r8w
0x18001928c  jnz     short loc_180019284
0x18001928e  lea     rax, [rcx+rax*2]
0x180019292  jmp     loc_1800193BF
0x180019297  mov     edi, 2Eh ; '.'
0x18001929c  cmp     [rax], di
0x18001929f  jnz     short loc_1800192F2
0x1800192a1  cmp     [r15+4], r8w
0x1800192a6  jnz     short loc_1800192F2
0x1800192a8  mov     edx, r9d; Ch
0x1800192ab  call    cs:__imp_wcsrchr
0x1800192b1  xor     ebx, ebx
0x1800192b3  mov     edx, edi; Ch
0x1800192b5  test    rax, rax
0x1800192b8  cmovz   rax, rsi
0x1800192bc  mov     rcx, rax; Str
0x1800192bf  call    cs:__imp_wcsrchr
0x1800192c5  test    rax, rax
0x1800192c8  jz      short loc_1800192D4
0x1800192ca  cmp     [rax+2], bx
0x1800192ce  jnz     loc_1800193BD
0x1800192d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800192d8  inc     rax
0x1800192db  cmp     [rsi+rax*2], bx
0x1800192df  jnz     short loc_1800192D8
0x1800192e1  lea     rax, [rsi+rax*2]
0x1800192e5  jmp     loc_1800193BF
0x1800192ea  cmp     r12w, r9w
0x1800192ee  cmovz   r15, rax
0x1800192f2  cmp     [rcx], r9w
0x1800192f6  lea     rbx, [rcx+2]
0x1800192fa  mov     rdi, r15
0x1800192fd  cmovnz  rbx, rsi
0x180019301  mov     r14, rbx
0x180019304  jmp     short loc_180019322
0x180019306  cmp     [rbx], r8w
0x18001930a  jz      loc_1800193BD
0x180019310  cmp     [rbx], r9w
0x180019314  jz      loc_180019459
0x18001931a  add     rdi, 2
0x18001931e  add     rbx, 2
0x180019322  movzx   eax, word ptr [rdi]
0x180019325  cmp     ax, 3Fh ; '?'
0x180019329  jz      short loc_180019306
0x18001932b  cmp     ax, 2Ah ; '*'
0x18001932f  jnz     short loc_180019337
0x180019331  movzx   ecx, word ptr [rdi+2]
0x180019335  jmp     short loc_18001933A
0x180019337  movzx   ecx, ax
0x18001933a  lea     rbp, [rdi+2]
0x18001933e  cmovnz  rbp, rdi
0x180019342  test    cx, cx
0x180019345  jnz     short loc_180019376
0x180019347  cmp     ax, 2Ah ; '*'
0x18001934b  jnz     short loc_180019361
0x18001934d  jmp     short loc_180019358
0x18001934f  test    ax, ax
0x180019352  jz      short loc_180019361
0x180019354  add     rbx, 2
0x180019358  movzx   eax, word ptr [rbx]
0x18001935b  cmp     ax, r9w
0x18001935f  jnz     short loc_18001934F
0x180019361  cmp     [rbx], r9w
0x180019365  jz      short loc_180019371
0x180019367  cmp     [rbx], r8w
0x18001936b  jnz     loc_180019459
0x180019371  mov     rax, rbx
0x180019374  jmp     short loc_1800193BF
0x180019376  movzx   ecx, word ptr [rbp+0]
0x18001937a  mov     rdi, rbp
0x18001937d  jmp     short loc_180019391
0x18001937f  cmp     cx, 3Fh ; '?'
0x180019383  jz      short loc_180019397
0x180019385  test    cx, cx
0x180019388  jz      short loc_180019397
0x18001938a  add     rdi, 2
0x18001938e  movzx   ecx, word ptr [rdi]
0x180019391  cmp     cx, 2Ah ; '*'
0x180019395  jnz     short loc_18001937F
0x180019397  cmp     ax, 2Ah ; '*'
0x18001939b  jnz     loc_180019437
0x1800193a1  cmp     [rdi], r8w
0x1800193a5  jnz     short loc_1800193F2
0x1800193a7  mov     rax, rdi
0x1800193aa  lea     rcx, [r14+r13*2]
0x1800193ae  sub     rax, rbp
0x1800193b1  sar     rax, 1
0x1800193b4  lea     rdx, [rbx+rax*2]
0x1800193b8  cmp     rdx, rcx
0x1800193bb  jbe     short loc_1800193E9
0x1800193bd  xor     eax, eax
0x1800193bf  add     rsp, 28h
0x1800193c3  pop     r15
0x1800193c5  pop     r14
0x1800193c7  pop     r13
0x1800193c9  pop     r12
0x1800193cb  pop     rdi
0x1800193cc  pop     rsi
0x1800193cd  pop     rbp
0x1800193ce  pop     rbx
0x1800193cf  retn
0x1800193d0  test    ax, ax
0x1800193d3  jz      short loc_1800193F2
0x1800193d5  cmp     [rbx], r9w
0x1800193d9  jz      short loc_1800193F2
0x1800193db  cmp     [rbx], r8w
0x1800193df  jz      short loc_1800193F2
0x1800193e1  add     rbx, 2
0x1800193e5  add     rdx, 2
0x1800193e9  movzx   eax, word ptr [rdx]
0x1800193ec  cmp     ax, r9w
0x1800193f0  jnz     short loc_1800193D0
0x1800193f2  mov     rsi, rdi
0x1800193f5  sub     rsi, rbp
0x1800193f8  sar     rsi, 1
0x1800193fb  jmp     short loc_180019413
0x1800193fd  cmp     [rbx], r8w
0x180019401  jz      short loc_1800193BD
0x180019403  mov     r9d, 2Fh ; '/'
0x180019409  cmp     [rbx], r9w
0x18001940d  jz      short loc_180019459
0x18001940f  add     rbx, 2
0x180019413  mov     r8d, esi; MaxCount
0x180019416  mov     rdx, rbp; String2
0x180019419  mov     rcx, rbx; String1
0x18001941c  call    wcsncmp_0
0x180019421  xor     r8d, r8d
0x180019424  test    eax, eax
0x180019426  jnz     short loc_1800193FD
0x180019428  lea     rbx, [rbx+rsi*2]
0x18001942c  mov     r9d, 2Fh ; '/'
0x180019432  jmp     loc_180019322
0x180019437  mov     rsi, rdi
0x18001943a  mov     rdx, rbp; String2
0x18001943d  sub     rsi, rbp
0x180019440  mov     rcx, rbx; String1
0x180019443  sar     rsi, 1
0x180019446  mov     r8d, esi; MaxCount
0x180019449  call    wcsncmp_0
0x18001944e  xor     r8d, r8d
0x180019451  test    eax, eax
0x180019453  jz      short loc_180019428
0x180019455  lea     r9d, [r8+2Fh]
0x180019459  cmp     r12w, r9w
0x18001945d  jz      loc_1800193BD
0x180019463  jmp     short loc_18001946E
0x180019465  test    ax, ax
0x180019468  jz      short loc_180019478
0x18001946a  add     r14, 2
0x18001946e  movzx   eax, word ptr [r14]
0x180019472  cmp     ax, r9w
0x180019476  jnz     short loc_180019465
0x180019478  cmp     [r14], r8w
0x18001947c  jz      loc_1800193BD
0x180019482  add     r14, 2
0x180019486  mov     rdi, r15
0x180019489  mov     rbx, r14
0x18001948c  jmp     loc_180019322
```
