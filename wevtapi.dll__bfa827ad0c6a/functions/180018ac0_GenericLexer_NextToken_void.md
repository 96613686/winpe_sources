# GenericLexer::NextToken(void)

- ea: `0x180018ac0`
- end: `0x180018d62`
- name: `?NextToken@GenericLexer@@QEAA?AW4XmlTokenType@@XZ`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018468`

## callees

- `0x180018ac0`
- `0x180021ea0`
- `0x180021f40`

## pseudocode

```c
__int64 __fastcall GenericLexer::NextToken(__int64 *a1)
{
  __int64 v1; // r15
  int v2; // r14d
  __int64 *v3; // r11
  char v4; // di
  __int64 v5; // r9
  int v6; // r10d
  __int64 v7; // r8
  __int64 v8; // rsi
  __int64 v9; // rbx
  char v10; // bp
  unsigned __int16 v11; // ax
  char started; // al
  __int64 result; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx

  v1 = *a1;
  v2 = 0;
  *((_DWORD *)a1 + 9) = 0;
  v3 = a1;
  *((_DWORD *)a1 + 8) = -1;
  v4 = 1;
  v5 = 0x100002600LL;
  v6 = 1038847;
  v7 = 0x43FFFFFF03FFBLL;
  do
  {
    while ( 1 )
    {
      v8 = *((int *)v3 + 6);
      v9 = 8 * v8;
      v10 = *(_BYTE *)(8 * v8 + v1 + 7);
      if ( v4 )
      {
        v14 = *((unsigned int *)v3 + 7);
        if ( v14 == v3[2] )
          v2 = 0;
        else
          v2 = *(unsigned __int16 *)(v3[1] + 2 * v14);
        *((_DWORD *)v3 + 7) = v14 + 1;
      }
      v11 = *(_WORD *)(v1 + v9 + 2);
      v4 = 0;
      if ( v11 != 0xFFFE )
        break;
      if ( *(_WORD *)(v1 + 8 * v8) == 0xFFFF )
        goto LABEL_7;
      started = (_WORD)v2 == *(_WORD *)(v1 + 8 * v8);
LABEL_6:
      if ( started )
        goto LABEL_7;
LABEL_24:
      *((_DWORD *)v3 + 6) = v8 + 1;
    }
    if ( *(_WORD *)(v1 + 8 * v8) == 0xFFFD )
    {
      if ( (_BYTE)v11 == 1 )
      {
        if ( (unsigned __int16)v2 < 0x80u )
        {
          if ( (unsigned __int16)(v2 - 97) > 0x19u
            && ((unsigned __int16)(v2 - 45) > 0x32u || !_bittest64(&v7, (unsigned __int16)(v2 - 45))) )
          {
            goto LABEL_29;
          }
LABEL_31:
          started = 1;
          goto LABEL_6;
        }
        started = IsNameCharSlow((unsigned __int16)v2, 65533, 0x43FFFFFF03FFBLL, 0x100002600LL);
      }
      else
      {
        if ( !(_BYTE)v11 )
        {
          if ( (unsigned __int16)v2 <= 0x13u && _bittest(&v6, (unsigned __int16)v2) )
            goto LABEL_29;
          if ( (unsigned __int16)v2 >= 0xFFFEu )
          {
            started = 0;
            goto LABEL_6;
          }
          goto LABEL_31;
        }
        if ( (unsigned __int8)v11 != 2 )
        {
          if ( (unsigned __int8)v11 != 3 )
          {
            started = 0;
            goto LABEL_6;
          }
          if ( (unsigned __int16)v2 > 0x20u || !_bittest64(&v5, (unsigned __int16)v2) )
          {
LABEL_29:
            started = 0;
            goto LABEL_6;
          }
          goto LABEL_31;
        }
        if ( (unsigned __int16)v2 < 0x80u )
        {
          if ( (unsigned __int16)(v2 - 65) > 0x39u
            || (v15 = 0x3FFFFFF43FFFFFFLL, !_bittest64(&v15, (unsigned int)(v2 - 65))) )
          {
            if ( (_WORD)v2 != 58 )
            {
              started = 0;
              goto LABEL_6;
            }
          }
          goto LABEL_31;
        }
        started = IsNameStartCharSlow((unsigned __int16)v2, 65533, 0x43FFFFFF03FFBLL, 0x100002600LL);
      }
      v6 = 1038847;
      v5 = 0x100002600LL;
      v7 = 0x43FFFFFF03FFBLL;
      goto LABEL_6;
    }
    if ( (unsigned __int16)v2 < *(_WORD *)(v1 + 8 * v8) || (unsigned __int16)v2 > v11 )
      goto LABEL_24;
LABEL_7:
    if ( (v10 & 1) != 0 )
    {
      if ( *((_DWORD *)v3 + 8) == -1 )
        *((_DWORD *)v3 + 8) = *((_DWORD *)v3 + 7) - 1;
      ++*((_DWORD *)v3 + 9);
    }
    else if ( (v10 & 2) == 0 )
    {
      if ( (v10 & 4) == 0 )
        goto LABEL_12;
      *((_DWORD *)v3 + 7) -= *(unsigned __int8 *)(v1 + v9 + 6);
    }
    v4 = 1;
LABEL_12:
    *((_DWORD *)v3 + 6) = *(unsigned __int8 *)(v1 + v9 + 4);
    result = *(unsigned __int8 *)(v1 + v9 + 5);
  }
  while ( !(_BYTE)result && (v10 & 0x20) == 0 );
  return result;
}

```

## disassembly

```asm
0x180018ac0  push    rbx
0x180018ac2  push    rbp
0x180018ac3  push    rsi
0x180018ac4  push    rdi
0x180018ac5  push    r12
0x180018ac7  push    r13
0x180018ac9  push    r14
0x180018acb  push    r15
0x180018acd  sub     rsp, 28h
0x180018ad1  mov     r15, [rcx]
0x180018ad4  xor     r14d, r14d
0x180018ad7  mov     [rcx+24h], r14d
0x180018adb  mov     r11, rcx
0x180018ade  mov     dword ptr [rcx+20h], 0FFFFFFFFh
0x180018ae5  mov     dil, 1
0x180018ae8  mov     ecx, 0FFFFh
0x180018aed  mov     edx, 0FFFDh
0x180018af2  mov     r12d, 0FFFEh
0x180018af8  mov     r9, 100002600h
0x180018b02  mov     r13d, 80h
0x180018b08  mov     r10d, 0FD9FFh
0x180018b0e  mov     r8, 43FFFFFF03FFBh
0x180018b18  nop     dword ptr [rax+rax+00000000h]
0x180018b20  movsxd  rsi, dword ptr [r11+18h]
0x180018b24  lea     rbx, ds:0[rsi*8]
0x180018b2c  movzx   ebp, byte ptr [rbx+r15+7]
0x180018b32  test    dil, dil
0x180018b35  jnz     short loc_180018BA8
0x180018b37  movzx   eax, word ptr [r15+rbx+2]
0x180018b3d  xor     dil, dil
0x180018b40  cmp     ax, r12w
0x180018b44  jnz     loc_180018BD0
0x180018b4a  cmp     [r15+rbx], cx
0x180018b4f  jz      short loc_180018B61
0x180018b51  cmp     r14w, [r15+rbx]
0x180018b56  setz    al
0x180018b59  test    al, al
0x180018b5b  jz      loc_180018C08
0x180018b61  test    bpl, 1
0x180018b65  jz      loc_180018C68
0x180018b6b  cmp     dword ptr [r11+20h], 0FFFFFFFFh
0x180018b70  jz      loc_180018C14
0x180018b76  inc     dword ptr [r11+24h]
0x180018b7a  mov     dil, 1
0x180018b7d  movzx   eax, byte ptr [r15+rbx+4]
0x180018b83  mov     [r11+18h], eax
0x180018b87  movzx   eax, byte ptr [r15+rbx+5]
0x180018b8d  test    al, al
0x180018b8f  jnz     short loc_180018B97
0x180018b91  test    bpl, 20h
0x180018b95  jz      short loc_180018B20
0x180018b97  add     rsp, 28h
0x180018b9b  pop     r15
0x180018b9d  pop     r14
0x180018b9f  pop     r13
0x180018ba1  pop     r12
0x180018ba3  pop     rdi
0x180018ba4  pop     rsi
0x180018ba5  pop     rbp
0x180018ba6  pop     rbx
0x180018ba7  retn
0x180018ba8  mov     ecx, [r11+1Ch]
0x180018bac  cmp     rcx, [r11+10h]
0x180018bb0  jz      loc_180018CFE
0x180018bb6  mov     rax, [r11+8]
0x180018bba  movzx   r14d, word ptr [rax+rcx*2]
0x180018bbf  lea     eax, [rcx+1]
0x180018bc2  mov     [r11+1Ch], eax
0x180018bc6  mov     ecx, 0FFFFh
0x180018bcb  jmp     loc_180018B37
0x180018bd0  cmp     [r15+rbx], dx
0x180018bd5  jnz     loc_180018D48
0x180018bdb  cmp     al, 1
0x180018bdd  jz      short loc_180018C23
0x180018bdf  movzx   ecx, al
0x180018be2  test    al, al
0x180018be4  jz      loc_180018C8B
0x180018bea  sub     ecx, 2
0x180018bed  jz      loc_180018CC8
0x180018bf3  cmp     ecx, 1
0x180018bf6  jz      loc_180018D15
0x180018bfc  xor     al, al
0x180018bfe  mov     ecx, 0FFFFh
0x180018c03  jmp     loc_180018B59
0x180018c08  lea     eax, [rsi+1]
0x180018c0b  mov     [r11+18h], eax
0x180018c0f  jmp     loc_180018B20
0x180018c14  mov     eax, [r11+1Ch]
0x180018c18  dec     eax
0x180018c1a  mov     [r11+20h], eax
0x180018c1e  jmp     loc_180018B76
0x180018c23  cmp     r14w, r13w
0x180018c27  jnb     short loc_180018C9E
0x180018c29  lea     eax, [r14-61h]
0x180018c2d  cmp     ax, 19h
0x180018c31  jbe     short loc_180018C5C
0x180018c33  lea     eax, [r14-2Dh]
0x180018c37  cmp     ax, 32h ; '2'
0x180018c3b  ja      short loc_180018C46
0x180018c3d  movzx   eax, ax
0x180018c40  bt      r8, rax
0x180018c44  jb      short loc_180018C5C
0x180018c46  xor     al, al
0x180018c48  mov     ecx, 0FFFFh
0x180018c4d  jmp     loc_180018B59
0x180018c52  cmp     r14w, r12w
0x180018c56  jnb     loc_180018D41
0x180018c5c  mov     al, 1
0x180018c5e  mov     ecx, 0FFFFh
0x180018c63  jmp     loc_180018B59
0x180018c68  test    bpl, 2
0x180018c6c  jnz     loc_180018B7A
0x180018c72  test    bpl, 4
0x180018c76  jz      loc_180018B7D
0x180018c7c  movzx   eax, byte ptr [r15+rbx+6]
0x180018c82  sub     [r11+1Ch], eax
0x180018c86  jmp     loc_180018B7A
0x180018c8b  cmp     r14w, 13h
0x180018c90  ja      short loc_180018C52
0x180018c92  movzx   eax, r14w
0x180018c96  bt      r10d, eax
0x180018c9a  jnb     short loc_180018C52
0x180018c9c  jmp     short loc_180018C46
0x180018c9e  movzx   ecx, r14w
0x180018ca2  call    IsNameCharSlow
0x180018ca7  mov     r10d, 0FD9FFh
0x180018cad  mov     r9, 100002600h
0x180018cb7  mov     r8, 43FFFFFF03FFBh
0x180018cc1  mov     edx, 0FFFDh
0x180018cc6  jmp     short loc_180018C5E
0x180018cc8  cmp     r14w, r13w
0x180018ccc  jnb     short loc_180018D33
0x180018cce  lea     eax, [r14-41h]
0x180018cd2  cmp     ax, 39h ; '9'
0x180018cd6  ja      short loc_180018CEC
0x180018cd8  mov     rcx, 3FFFFFF43FFFFFFh
0x180018ce2  bt      rcx, rax
0x180018ce6  jb      loc_180018C5C
0x180018cec  cmp     r14w, 3Ah ; ':'
0x180018cf1  jz      loc_180018C5C
0x180018cf7  xor     al, al
0x180018cf9  jmp     loc_180018C5E
0x180018cfe  xor     eax, eax
0x180018d00  movzx   r14d, ax
0x180018d04  lea     eax, [rcx+1]
0x180018d07  mov     [r11+1Ch], eax
0x180018d0b  mov     ecx, 0FFFFh
0x180018d10  jmp     loc_180018B37
0x180018d15  cmp     r14w, 20h ; ' '
0x180018d1a  ja      loc_180018C46
0x180018d20  movzx   eax, r14w
0x180018d24  bt      r9, rax
0x180018d28  jb      loc_180018C5C
0x180018d2e  jmp     loc_180018C46
0x180018d33  movzx   ecx, r14w
0x180018d37  call    IsNameStartCharSlow
0x180018d3c  jmp     loc_180018CA7
0x180018d41  xor     al, al
0x180018d43  jmp     loc_180018C5E
0x180018d48  cmp     r14w, [r15+rbx]
0x180018d4d  jb      loc_180018C08
0x180018d53  cmp     r14w, ax
0x180018d57  ja      loc_180018C08
0x180018d5d  jmp     loc_180018B61
```
