# StringVerifier::TryDecodeExtension(void)

- ea: `0x18000b620`
- end: `0x18000b774`
- name: `?TryDecodeExtension@StringVerifier@@AEAAHXZ`
- size: `340`
- prototype: `__int64 __fastcall(char **this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000b620`
- `0x18000b77c`
- `0x18000b7f0`

## pseudocode

```c
__int64 __fastcall StringVerifier::TryDecodeExtension(char **this)
{
  __int64 result; // rax
  char *v3; // rdi
  char *v4; // rax
  char *v5; // rax
  char *v6; // rax
  char *v7; // rax

  result = StringVerifier::TryDecodeToken((StringVerifier *)this);
  if ( (_DWORD)result )
  {
    while ( (unsigned int)StringVerifier::TryDecodeLWS((StringVerifier *)this) )
      ;
    while ( 1 )
    {
      do
      {
        v3 = this[1];
        if ( v3 >= this[2] || *v3 != 59 )
          return 1;
        this[1] = v3 + 1;
        if ( v3 + 1 < this[2] )
        {
          while ( (unsigned int)StringVerifier::TryDecodeLWS((StringVerifier *)this) )
            ;
          if ( (unsigned int)StringVerifier::TryDecodeToken((StringVerifier *)this) )
            continue;
        }
        goto LABEL_27;
      }
      while ( this[1] >= this[2] );
      while ( (unsigned int)StringVerifier::TryDecodeLWS((StringVerifier *)this) )
        ;
      v3 = this[1];
      if ( v3 >= this[2] )
        goto LABEL_27;
      if ( *v3 == 61 )
      {
        this[1] = v3 + 1;
        if ( v3 + 1 >= this[2] )
          goto LABEL_27;
      }
      while ( (unsigned int)StringVerifier::TryDecodeLWS((StringVerifier *)this) )
        ;
      if ( !(unsigned int)StringVerifier::TryDecodeToken((StringVerifier *)this) )
        break;
LABEL_36:
      while ( (unsigned int)StringVerifier::TryDecodeLWS((StringVerifier *)this) )
        ;
    }
    v4 = this[1];
    if ( v4 < this[2] && *v4 == 34 )
    {
      v5 = v4 + 1;
      for ( this[1] = v5; ; v5 = this[1] )
      {
        if ( v5 >= this[2] )
          goto LABEL_27;
        if ( *v5 > 31 )
          break;
        if ( *v5 == 34 )
          goto LABEL_35;
        if ( *v5 != 13 )
        {
          if ( *v5 != 92 )
            goto LABEL_27;
          goto LABEL_31;
        }
        if ( !(unsigned int)StringVerifier::TryDecodeLWS((StringVerifier *)this) )
          goto LABEL_27;
LABEL_34:
        ;
      }
      switch ( *v5 )
      {
        case '\x7F':
          goto LABEL_27;
        case '"':
LABEL_35:
          this[1] = v5 + 1;
          goto LABEL_36;
        case '\\':
LABEL_31:
          v7 = v5 + 1;
          this[1] = v7;
          if ( v7 >= this[2] )
            goto LABEL_27;
          v6 = v7 + 1;
          break;
        default:
          v6 = v5 + 1;
          break;
      }
      this[1] = v6;
      goto LABEL_34;
    }
LABEL_27:
    this[1] = v3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000b620  mov     [rsp+arg_0], rbx
0x18000b625  push    rdi
0x18000b626  sub     rsp, 20h
0x18000b62a  mov     rbx, rcx
0x18000b62d  call    ?TryDecodeToken@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeToken(void)
0x18000b632  test    eax, eax
0x18000b634  jz      loc_18000B732
0x18000b63a  mov     rcx, rbx; this
0x18000b63d  call    ?TryDecodeLWS@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeLWS(void)
0x18000b642  test    eax, eax
0x18000b644  jnz     short loc_18000B63A
0x18000b646  mov     rdi, [rbx+8]
0x18000b64a  cmp     rdi, [rbx+10h]
0x18000b64e  jnb     loc_18000B72D
0x18000b654  cmp     byte ptr [rdi], 3Bh ; ';'
0x18000b657  jnz     loc_18000B72D
0x18000b65d  lea     rax, [rdi+1]
0x18000b661  mov     [rbx+8], rax
0x18000b665  cmp     rax, [rbx+10h]
0x18000b669  jnb     loc_18000B729
0x18000b66f  mov     rcx, rbx; this
0x18000b672  call    ?TryDecodeLWS@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeLWS(void)
0x18000b677  test    eax, eax
0x18000b679  jnz     short loc_18000B66F
0x18000b67b  mov     rcx, rbx; this
0x18000b67e  call    ?TryDecodeToken@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeToken(void)
0x18000b683  test    eax, eax
0x18000b685  jz      loc_18000B729
0x18000b68b  mov     rax, [rbx+10h]
0x18000b68f  cmp     [rbx+8], rax
0x18000b693  jnb     short loc_18000B646
0x18000b695  mov     rcx, rbx; this
0x18000b698  call    ?TryDecodeLWS@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeLWS(void)
0x18000b69d  test    eax, eax
0x18000b69f  jnz     short loc_18000B695
0x18000b6a1  mov     rdi, [rbx+8]
0x18000b6a5  cmp     rdi, [rbx+10h]
0x18000b6a9  jnb     short loc_18000B729
0x18000b6ab  cmp     byte ptr [rdi], 3Dh ; '='
0x18000b6ae  jnz     short loc_18000B6BE
0x18000b6b0  lea     rax, [rdi+1]
0x18000b6b4  mov     [rbx+8], rax
0x18000b6b8  cmp     rax, [rbx+10h]
0x18000b6bc  jnb     short loc_18000B729
0x18000b6be  mov     rcx, rbx; this
0x18000b6c1  call    ?TryDecodeLWS@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeLWS(void)
0x18000b6c6  test    eax, eax
0x18000b6c8  jnz     short loc_18000B6BE
0x18000b6ca  mov     rcx, rbx; this
0x18000b6cd  call    ?TryDecodeToken@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeToken(void)
0x18000b6d2  test    eax, eax
0x18000b6d4  jnz     loc_18000B763
0x18000b6da  mov     rax, [rbx+8]
0x18000b6de  cmp     rax, [rbx+10h]
0x18000b6e2  jnb     short loc_18000B729
0x18000b6e4  cmp     byte ptr [rax], 22h ; '"'
0x18000b6e7  jnz     short loc_18000B729
0x18000b6e9  inc     rax
0x18000b6ec  mov     [rbx+8], rax
0x18000b6f0  cmp     rax, [rbx+10h]
0x18000b6f4  jnb     short loc_18000B729
0x18000b6f6  cmp     byte ptr [rax], 1Fh
0x18000b6f9  mov     rcx, rax
0x18000b6fc  jle     short loc_18000B713
0x18000b6fe  cmp     byte ptr [rax], 7Fh
0x18000b701  jz      short loc_18000B729
0x18000b703  cmp     byte ptr [rax], 22h ; '"'
0x18000b706  jz      short loc_18000B75C
0x18000b708  cmp     byte ptr [rax], 5Ch ; '\'
0x18000b70b  jz      short loc_18000B742
0x18000b70d  lea     rax, [rax+1]
0x18000b711  jmp     short loc_18000B752
0x18000b713  cmp     byte ptr [rax], 22h ; '"'
0x18000b716  jz      short loc_18000B75C
0x18000b718  cmp     byte ptr [rax], 0Dh
0x18000b71b  jnz     short loc_18000B73D
0x18000b71d  mov     rcx, rbx; this
0x18000b720  call    ?TryDecodeLWS@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeLWS(void)
0x18000b725  test    eax, eax
0x18000b727  jnz     short loc_18000B756
0x18000b729  mov     [rbx+8], rdi
0x18000b72d  mov     eax, 1
0x18000b732  mov     rbx, [rsp+28h+arg_0]
0x18000b737  add     rsp, 20h
0x18000b73b  pop     rdi
0x18000b73c  retn
0x18000b73d  cmp     byte ptr [rax], 5Ch ; '\'
0x18000b740  jnz     short loc_18000B729
0x18000b742  inc     rax
0x18000b745  mov     [rbx+8], rax
0x18000b749  cmp     rax, [rbx+10h]
0x18000b74d  jnb     short loc_18000B729
0x18000b74f  inc     rax
0x18000b752  mov     [rbx+8], rax
0x18000b756  mov     rax, [rbx+8]
0x18000b75a  jmp     short loc_18000B6F0
0x18000b75c  inc     rax
0x18000b75f  mov     [rbx+8], rax
0x18000b763  mov     rcx, rbx; this
0x18000b766  call    ?TryDecodeLWS@StringVerifier@@AEAAHXZ; StringVerifier::TryDecodeLWS(void)
0x18000b76b  test    eax, eax
0x18000b76d  jnz     short loc_18000B763
0x18000b76f  jmp     loc_18000B646
```
