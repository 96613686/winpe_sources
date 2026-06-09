# RunDLL_ParseCommand(ushort *,SWITCH_FLAGS *,ushort * *,ushort * *,ushort * *)

- ea: `0x140007da8`
- end: `0x140007fd1`
- name: `?RunDLL_ParseCommand@@YAHPEAGPEAW4SWITCH_FLAGS@@PEAPEAG22@Z`
- size: `553`
- prototype: `__int64 __fastcall(unsigned __int16 *, enum SWITCH_FLAGS *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007798`

## callees

- `0x140007da8`
- `0x1400081cc`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007f94`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007f94`

## pseudocode

```c
__int64 __fastcall RunDLL_ParseCommand(
        unsigned __int16 *a1,
        enum SWITCH_FLAGS *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  unsigned __int16 **v5; // rbp
  unsigned __int16 v7; // ax
  unsigned __int16 *v10; // rdi
  unsigned __int16 *v11; // rbx
  unsigned __int16 **v12; // rdi
  unsigned __int16 v13; // ax
  __int64 result; // rax
  unsigned __int16 v15; // ax
  unsigned __int16 i; // ax
  unsigned __int16 *v17; // rsi
  unsigned __int16 v18; // ax
  LPWSTR v19; // rcx
  unsigned __int16 v20; // ax
  WCHAR j; // ax
  bool v22; // zf

  v5 = a5;
  *(_DWORD *)a2 = 0;
  v7 = *a1;
  *a3 = 0;
  *a4 = 0;
  v10 = a1;
  *v5 = 0;
  if ( !v7 )
    return 0;
  v11 = a1;
  while ( v7 == 32 )
  {
LABEL_3:
    v10 = v11 + 1;
    v7 = v11[1];
    ++v11;
  }
  switch ( v7 )
  {
    case 0x2Fu:
    case 0x2Du:
      v12 = (unsigned __int16 **)(v11 + 1);
      v13 = v11[1];
      a5 = (unsigned __int16 **)(v11 + 1);
      if ( v13 )
      {
        ++v11;
        while ( 1 )
        {
          if ( v13 == 32 )
            goto LABEL_3;
          if ( v13 == 76 )
            break;
          if ( v13 == 83 )
            goto LABEL_14;
          if ( v13 == 108 )
            break;
          if ( v13 == 115 )
          {
LABEL_14:
            if ( (unsigned int)_GetSwitch(L"sta", (const WCHAR **)&a5) )
              *(_DWORD *)a2 |= 1u;
LABEL_18:
            v12 = a5;
          }
          v12 = (unsigned __int16 **)((char *)v12 + 2);
          a5 = v12;
          v11 = (unsigned __int16 *)v12;
          v13 = *(_WORD *)v12;
          if ( !*(_WORD *)v12 )
            return 0;
        }
        if ( (unsigned int)_GetSwitch(L"localserver", (const WCHAR **)&a5) )
          *(_DWORD *)a2 |= 2u;
        goto LABEL_18;
      }
      return 0;
    case 0u:
      return 0;
    case 0x22u:
      v10 = v11 + 1;
      v15 = v11[1];
      ++v11;
      if ( !v15 )
        return 0;
      do
      {
        if ( v15 == 34 )
          break;
        v15 = *++v11;
      }
      while ( *v11 );
      if ( !*v11 )
        return 0;
      goto LABEL_27;
  }
  while ( 1 )
  {
    v20 = *v11;
    if ( !*v11 || v20 == 32 || v20 == 44 )
      break;
    ++v11;
  }
  if ( *v11 )
  {
LABEL_27:
    *v11++ = 0;
    for ( i = *v11; *v11; i = *v11 )
    {
      if ( i != 32 && i != 44 )
        break;
      ++v11;
    }
    goto LABEL_31;
  }
  if ( (*(_BYTE *)a2 & 3) == 0 )
    return 0;
LABEL_31:
  v17 = v11;
  if ( (*(_BYTE *)a2 & 3) == 0 )
  {
    v18 = *v11;
    if ( *v11 )
    {
      v19 = v11;
      do
      {
        if ( v18 == 32 )
          break;
        v18 = *++v11;
      }
      while ( *v11 );
      if ( *v11 )
      {
        *v11 = 0;
        do
          ++v11;
        while ( *v11 && *v11 <= 0x20u );
      }
      for ( j = *v19; j; j = *v19 )
      {
        if ( j == 92 || j == 47 )
        {
          if ( v19 )
            return 0;
          goto LABEL_54;
        }
        v19 = CharNextW(v19);
      }
      goto LABEL_54;
    }
    return 0;
  }
LABEL_54:
  v22 = (*(_BYTE *)a2 & 3) == 0;
  *a3 = v10;
  if ( !v22 )
  {
    v11 = v17;
    v17 = 0;
  }
  *a4 = v17;
  result = 1;
  *v5 = v11;
  return result;
}

```

## disassembly

```asm
0x140007da8  push    rbx
0x140007daa  push    rbp
0x140007dab  push    rsi
0x140007dac  push    rdi
0x140007dad  push    r12
0x140007daf  push    r13
0x140007db1  push    r14
0x140007db3  push    r15
0x140007db5  sub     rsp, 28h
0x140007db9  mov     rbp, [rsp+68h+arg_20]
0x140007dc1  xor     r13d, r13d
0x140007dc4  mov     [rdx], r13d
0x140007dc7  mov     r15, r9
0x140007dca  movzx   eax, word ptr [rcx]
0x140007dcd  mov     r12, r8
0x140007dd0  mov     [r8], r13
0x140007dd3  mov     r14, rdx
0x140007dd6  mov     [r9], r13
0x140007dd9  mov     rdi, rcx
0x140007ddc  mov     [rbp+0], r13
0x140007de0  test    ax, ax
0x140007de3  jz      loc_140007E9C
0x140007de9  mov     rbx, rcx
0x140007dec  jmp     short loc_140007DF8
0x140007dee  lea     rdi, [rbx+2]
0x140007df2  movzx   eax, word ptr [rdi]
0x140007df5  mov     rbx, rdi
0x140007df8  cmp     ax, 20h ; ' '
0x140007dfc  jz      short loc_140007DEE
0x140007dfe  cmp     ax, 2Fh ; '/'
0x140007e02  jz      short loc_140007E0E
0x140007e04  cmp     ax, 2Dh ; '-'
0x140007e08  jnz     loc_140007EAF
0x140007e0e  lea     rdi, [rbx+2]
0x140007e12  movzx   eax, word ptr [rdi]
0x140007e15  mov     [rsp+68h+arg_20], rdi
0x140007e1d  test    ax, ax
0x140007e20  jz      short loc_140007E9C
0x140007e22  mov     rbx, rdi
0x140007e25  cmp     ax, 20h ; ' '
0x140007e29  jz      short loc_140007DEE
0x140007e2b  cmp     ax, 4Ch ; 'L'
0x140007e2f  jz      short loc_140007E61
0x140007e31  cmp     ax, 53h ; 'S'
0x140007e35  jz      short loc_140007E43
0x140007e37  cmp     ax, 6Ch ; 'l'
0x140007e3b  jz      short loc_140007E61
0x140007e3d  cmp     ax, 73h ; 's'
0x140007e41  jnz     short loc_140007E85
0x140007e43  lea     rdx, [rsp+68h+arg_20]; unsigned __int16 **
0x140007e4b  lea     rcx, String1; "sta"
0x140007e52  call    ?_GetSwitch@@YAHPEBGPEAPEAG@Z; _GetSwitch(ushort const *,ushort * *)
0x140007e57  test    eax, eax
0x140007e59  jz      short loc_140007E7D
0x140007e5b  or      dword ptr [r14], 1
0x140007e5f  jmp     short loc_140007E7D
0x140007e61  lea     rdx, [rsp+68h+arg_20]; unsigned __int16 **
0x140007e69  lea     rcx, aLocalserver; "localserver"
0x140007e70  call    ?_GetSwitch@@YAHPEBGPEAPEAG@Z; _GetSwitch(ushort const *,ushort * *)
0x140007e75  test    eax, eax
0x140007e77  jz      short loc_140007E7D
0x140007e79  or      dword ptr [r14], 2
0x140007e7d  mov     rdi, [rsp+68h+arg_20]
0x140007e85  add     rdi, 2
0x140007e89  mov     [rsp+68h+arg_20], rdi
0x140007e91  mov     rbx, rdi
0x140007e94  movzx   eax, word ptr [rdi]
0x140007e97  test    ax, ax
0x140007e9a  jnz     short loc_140007E25
0x140007e9c  xor     eax, eax
0x140007e9e  add     rsp, 28h
0x140007ea2  pop     r15
0x140007ea4  pop     r14
0x140007ea6  pop     r13
0x140007ea8  pop     r12
0x140007eaa  pop     rdi
0x140007eab  pop     rsi
0x140007eac  pop     rbp
0x140007ead  pop     rbx
0x140007eae  retn
0x140007eaf  test    ax, ax
0x140007eb2  jz      short loc_140007E9C
0x140007eb4  cmp     ax, 22h ; '"'
0x140007eb8  jnz     loc_140007F57
0x140007ebe  lea     rdi, [rbx+2]
0x140007ec2  movzx   eax, word ptr [rdi]
0x140007ec5  mov     rbx, rdi
0x140007ec8  test    ax, ax
0x140007ecb  jz      short loc_140007E9C
0x140007ecd  cmp     ax, 22h ; '"'
0x140007ed1  jz      short loc_140007EDF
0x140007ed3  add     rbx, 2
0x140007ed7  movzx   eax, word ptr [rbx]
0x140007eda  test    ax, ax
0x140007edd  jnz     short loc_140007ECD
0x140007edf  cmp     [rbx], r13w
0x140007ee3  jz      short loc_140007E9C
0x140007ee5  mov     [rbx], r13w
0x140007ee9  add     rbx, 2
0x140007eed  movzx   eax, word ptr [rbx]
0x140007ef0  test    ax, ax
0x140007ef3  jz      short loc_140007F0D
0x140007ef5  cmp     ax, 20h ; ' '
0x140007ef9  jz      short loc_140007F01
0x140007efb  cmp     ax, 2Ch ; ','
0x140007eff  jnz     short loc_140007F0D
0x140007f01  add     rbx, 2
0x140007f05  movzx   eax, word ptr [rbx]
0x140007f08  test    ax, ax
0x140007f0b  jnz     short loc_140007EF5
0x140007f0d  test    byte ptr [r14], 3
0x140007f11  mov     rsi, rbx
0x140007f14  jnz     loc_140007FB0
0x140007f1a  movzx   eax, word ptr [rbx]
0x140007f1d  test    ax, ax
0x140007f20  jz      loc_140007E9C
0x140007f26  mov     rcx, rbx
0x140007f29  cmp     ax, 20h ; ' '
0x140007f2d  jz      short loc_140007F3B
0x140007f2f  add     rbx, 2
0x140007f33  movzx   eax, word ptr [rbx]
0x140007f36  test    ax, ax
0x140007f39  jnz     short loc_140007F29
0x140007f3b  cmp     [rbx], r13w
0x140007f3f  jz      short loc_140007F83
0x140007f41  mov     [rbx], r13w
0x140007f45  jmp     short loc_140007F77
0x140007f47  cmp     ax, 20h ; ' '
0x140007f4b  jz      short loc_140007F5F
0x140007f4d  cmp     ax, 2Ch ; ','
0x140007f51  jz      short loc_140007F5F
0x140007f53  add     rbx, 2
0x140007f57  movzx   eax, word ptr [rbx]
0x140007f5a  test    ax, ax
0x140007f5d  jnz     short loc_140007F47
0x140007f5f  cmp     [rbx], r13w
0x140007f63  jnz     short loc_140007EE5
0x140007f65  test    byte ptr [r14], 3
0x140007f69  jz      loc_140007E9C
0x140007f6f  jmp     short loc_140007F0D
0x140007f71  cmp     ax, 20h ; ' '
0x140007f75  ja      short loc_140007F83
0x140007f77  add     rbx, 2
0x140007f7b  movzx   eax, word ptr [rbx]
0x140007f7e  test    ax, ax
0x140007f81  jnz     short loc_140007F71
0x140007f83  movzx   eax, word ptr [rcx]
0x140007f86  jmp     short loc_140007FA0
0x140007f88  cmp     ax, 5Ch ; '\'
0x140007f8c  jz      short loc_140007FA7
0x140007f8e  cmp     ax, 2Fh ; '/'
0x140007f92  jz      short loc_140007FA7
0x140007f94  call    cs:__imp_CharNextW
0x140007f9a  mov     rcx, rax; lpsz
0x140007f9d  movzx   eax, word ptr [rax]
0x140007fa0  test    ax, ax
0x140007fa3  jnz     short loc_140007F88
0x140007fa5  jmp     short loc_140007FB0
0x140007fa7  test    rcx, rcx
0x140007faa  jnz     loc_140007E9C
0x140007fb0  test    byte ptr [r14], 3
0x140007fb4  mov     [r12], rdi
0x140007fb8  jz      short loc_140007FC0
0x140007fba  mov     rbx, rsi
0x140007fbd  mov     rsi, r13
0x140007fc0  mov     [r15], rsi
0x140007fc3  mov     eax, 1
0x140007fc8  mov     [rbp+0], rbx
0x140007fcc  jmp     loc_140007E9E
```
