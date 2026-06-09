# MatchPathInUrl(ushort const *,ulong,ushort const *)

- ea: `0x18000632c`
- end: `0x180006575`
- name: `?MatchPathInUrl@@YAPEBGPEBGK0@Z`
- size: `585`
- prototype: `const unsigned __int16 *__fastcall(wchar_t *String1, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000657c`

## callees

- `0x18000632c`
- `0x1800067de`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000638f`
- `msvcrt!wcsrchr` at `0x1800063a3`
- `msvcrt!wcsrchr` at `0x18000638f`
- `msvcrt!wcsrchr` at `0x1800063a3`

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
0x18000632c  push    rbx
0x18000632e  push    rbp
0x18000632f  push    rsi
0x180006330  push    rdi
0x180006331  push    r12
0x180006333  push    r13
0x180006335  push    r14
0x180006337  push    r15
0x180006339  sub     rsp, 28h
0x18000633d  movzx   r12d, word ptr [r8]
0x180006341  lea     rax, [r8+2]
0x180006345  mov     r15, r8
0x180006348  mov     r13d, edx
0x18000634b  xor     r8d, r8d
0x18000634e  mov     rsi, rcx
0x180006351  mov     r9d, 2Fh ; '/'
0x180006357  cmp     r12w, 2Ah ; '*'
0x18000635c  jnz     short loc_1800063CE
0x18000635e  cmp     [rax], r8w
0x180006362  jnz     short loc_18000637B
0x180006364  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006368  inc     rax
0x18000636b  cmp     [rcx+rax*2], r8w
0x180006370  jnz     short loc_180006368
0x180006372  lea     rax, [rcx+rax*2]
0x180006376  jmp     loc_1800064A3
0x18000637b  mov     edi, 2Eh ; '.'
0x180006380  cmp     [rax], di
0x180006383  jnz     short loc_1800063D6
0x180006385  cmp     [r15+4], r8w
0x18000638a  jnz     short loc_1800063D6
0x18000638c  mov     edx, r9d; Ch
0x18000638f  call    cs:__imp_wcsrchr
0x180006395  xor     ebx, ebx
0x180006397  mov     edx, edi; Ch
0x180006399  test    rax, rax
0x18000639c  cmovz   rax, rsi
0x1800063a0  mov     rcx, rax; Str
0x1800063a3  call    cs:__imp_wcsrchr
0x1800063a9  test    rax, rax
0x1800063ac  jz      short loc_1800063B8
0x1800063ae  cmp     [rax+2], bx
0x1800063b2  jnz     loc_1800064A1
0x1800063b8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800063bc  inc     rax
0x1800063bf  cmp     [rsi+rax*2], bx
0x1800063c3  jnz     short loc_1800063BC
0x1800063c5  lea     rax, [rsi+rax*2]
0x1800063c9  jmp     loc_1800064A3
0x1800063ce  cmp     r12w, r9w
0x1800063d2  cmovz   r15, rax
0x1800063d6  cmp     [rcx], r9w
0x1800063da  lea     rbx, [rcx+2]
0x1800063de  mov     rdi, r15
0x1800063e1  cmovnz  rbx, rsi
0x1800063e5  mov     r14, rbx
0x1800063e8  jmp     short loc_180006406
0x1800063ea  cmp     [rbx], r8w
0x1800063ee  jz      loc_1800064A1
0x1800063f4  cmp     [rbx], r9w
0x1800063f8  jz      loc_18000653D
0x1800063fe  add     rdi, 2
0x180006402  add     rbx, 2
0x180006406  movzx   eax, word ptr [rdi]
0x180006409  cmp     ax, 3Fh ; '?'
0x18000640d  jz      short loc_1800063EA
0x18000640f  cmp     ax, 2Ah ; '*'
0x180006413  jnz     short loc_18000641B
0x180006415  movzx   ecx, word ptr [rdi+2]
0x180006419  jmp     short loc_18000641E
0x18000641b  movzx   ecx, ax
0x18000641e  lea     rbp, [rdi+2]
0x180006422  cmovnz  rbp, rdi
0x180006426  test    cx, cx
0x180006429  jnz     short loc_18000645A
0x18000642b  cmp     ax, 2Ah ; '*'
0x18000642f  jnz     short loc_180006445
0x180006431  jmp     short loc_18000643C
0x180006433  test    ax, ax
0x180006436  jz      short loc_180006445
0x180006438  add     rbx, 2
0x18000643c  movzx   eax, word ptr [rbx]
0x18000643f  cmp     ax, r9w
0x180006443  jnz     short loc_180006433
0x180006445  cmp     [rbx], r9w
0x180006449  jz      short loc_180006455
0x18000644b  cmp     [rbx], r8w
0x18000644f  jnz     loc_18000653D
0x180006455  mov     rax, rbx
0x180006458  jmp     short loc_1800064A3
0x18000645a  movzx   ecx, word ptr [rbp+0]
0x18000645e  mov     rdi, rbp
0x180006461  jmp     short loc_180006475
0x180006463  cmp     cx, 3Fh ; '?'
0x180006467  jz      short loc_18000647B
0x180006469  test    cx, cx
0x18000646c  jz      short loc_18000647B
0x18000646e  add     rdi, 2
0x180006472  movzx   ecx, word ptr [rdi]
0x180006475  cmp     cx, 2Ah ; '*'
0x180006479  jnz     short loc_180006463
0x18000647b  cmp     ax, 2Ah ; '*'
0x18000647f  jnz     loc_18000651B
0x180006485  cmp     [rdi], r8w
0x180006489  jnz     short loc_1800064D6
0x18000648b  mov     rax, rdi
0x18000648e  lea     rcx, [r14+r13*2]
0x180006492  sub     rax, rbp
0x180006495  sar     rax, 1
0x180006498  lea     rdx, [rbx+rax*2]
0x18000649c  cmp     rdx, rcx
0x18000649f  jbe     short loc_1800064CD
0x1800064a1  xor     eax, eax
0x1800064a3  add     rsp, 28h
0x1800064a7  pop     r15
0x1800064a9  pop     r14
0x1800064ab  pop     r13
0x1800064ad  pop     r12
0x1800064af  pop     rdi
0x1800064b0  pop     rsi
0x1800064b1  pop     rbp
0x1800064b2  pop     rbx
0x1800064b3  retn
0x1800064b4  test    ax, ax
0x1800064b7  jz      short loc_1800064D6
0x1800064b9  cmp     [rbx], r9w
0x1800064bd  jz      short loc_1800064D6
0x1800064bf  cmp     [rbx], r8w
0x1800064c3  jz      short loc_1800064D6
0x1800064c5  add     rbx, 2
0x1800064c9  add     rdx, 2
0x1800064cd  movzx   eax, word ptr [rdx]
0x1800064d0  cmp     ax, r9w
0x1800064d4  jnz     short loc_1800064B4
0x1800064d6  mov     rsi, rdi
0x1800064d9  sub     rsi, rbp
0x1800064dc  sar     rsi, 1
0x1800064df  jmp     short loc_1800064F7
0x1800064e1  cmp     [rbx], r8w
0x1800064e5  jz      short loc_1800064A1
0x1800064e7  mov     r9d, 2Fh ; '/'
0x1800064ed  cmp     [rbx], r9w
0x1800064f1  jz      short loc_18000653D
0x1800064f3  add     rbx, 2
0x1800064f7  mov     r8d, esi; MaxCount
0x1800064fa  mov     rdx, rbp; String2
0x1800064fd  mov     rcx, rbx; String1
0x180006500  call    wcsncmp_0
0x180006505  xor     r8d, r8d
0x180006508  test    eax, eax
0x18000650a  jnz     short loc_1800064E1
0x18000650c  lea     rbx, [rbx+rsi*2]
0x180006510  mov     r9d, 2Fh ; '/'
0x180006516  jmp     loc_180006406
0x18000651b  mov     rsi, rdi
0x18000651e  mov     rdx, rbp; String2
0x180006521  sub     rsi, rbp
0x180006524  mov     rcx, rbx; String1
0x180006527  sar     rsi, 1
0x18000652a  mov     r8d, esi; MaxCount
0x18000652d  call    wcsncmp_0
0x180006532  xor     r8d, r8d
0x180006535  test    eax, eax
0x180006537  jz      short loc_18000650C
0x180006539  lea     r9d, [r8+2Fh]
0x18000653d  cmp     r12w, r9w
0x180006541  jz      loc_1800064A1
0x180006547  jmp     short loc_180006552
0x180006549  test    ax, ax
0x18000654c  jz      short loc_18000655C
0x18000654e  add     r14, 2
0x180006552  movzx   eax, word ptr [r14]
0x180006556  cmp     ax, r9w
0x18000655a  jnz     short loc_180006549
0x18000655c  cmp     [r14], r8w
0x180006560  jz      loc_1800064A1
0x180006566  add     r14, 2
0x18000656a  mov     rdi, r15
0x18000656d  mov     rbx, r14
0x180006570  jmp     loc_180006406
```
