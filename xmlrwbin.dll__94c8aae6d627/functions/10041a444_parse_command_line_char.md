# parse_command_line_char_

- ea: `0x10041a444`
- end: `0x10041a609`
- name: `parse_command_line_char_`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10041a674`

## callees

- `0x10041a444`
- `0x10041dbcc`

## pseudocode

```c
char __fastcall parse_command_line_char_(char *a1, char **a2, char *a3, _QWORD *a4, _QWORD *a5)
{
  char *v6; // rbx
  char **v7; // r14
  bool v9; // bp
  char *v10; // r15
  unsigned int v11; // esi
  bool v12; // si
  char result; // al
  int v14; // edx
  unsigned int v15; // eax
  char v16; // al

  v6 = a3;
  v7 = a2;
  *a5 = 0;
  *a4 = 1;
  if ( a2 )
  {
    *a2 = a3;
    v7 = a2 + 1;
  }
  v9 = 0;
  do
  {
    v10 = a1;
    if ( *a1 == 34 )
    {
      LOBYTE(v11) = 34;
      v9 = !v9;
      ++a1;
    }
    else
    {
      ++*a5;
      if ( v6 )
        *v6++ = *a1;
      v11 = *a1++;
      if ( ismbblead(v11) )
      {
        ++*a5;
        if ( v6 )
          *v6++ = *a1;
        a1 = v10 + 2;
      }
      if ( !(_BYTE)v11 )
      {
        --a1;
        goto LABEL_19;
      }
    }
  }
  while ( v9 || (_BYTE)v11 != 32 && (_BYTE)v11 != 9 );
  if ( v6 )
    *(v6 - 1) = 0;
LABEL_19:
  v12 = 0;
  while ( 1 )
  {
    result = *a1;
    if ( !*a1 )
      break;
    while ( result == 32 || result == 9 )
      result = *++a1;
    if ( !result )
      break;
    if ( v7 )
      *v7++ = v6;
    ++*a4;
    while ( 1 )
    {
      v14 = 1;
      v15 = 0;
      while ( *a1 == 92 )
      {
        ++a1;
        ++v15;
      }
      if ( *a1 == 34 )
      {
        if ( (v15 & 1) == 0 )
        {
          if ( v12 && a1[1] == 34 )
          {
            ++a1;
          }
          else
          {
            v14 = 0;
            v12 = !v12;
          }
        }
        v15 >>= 1;
      }
      while ( v15 )
      {
        --v15;
        if ( v6 )
          *v6++ = 92;
        ++*a5;
      }
      v16 = *a1;
      if ( !*a1 || !v12 && (v16 == 32 || v16 == 9) )
        break;
      if ( v14 )
      {
        if ( v6 )
          *v6++ = v16;
        if ( ismbblead(*a1) )
        {
          ++*a5;
          ++a1;
          if ( v6 )
            *v6++ = *a1;
        }
        ++*a5;
      }
      ++a1;
    }
    if ( v6 )
      *v6++ = 0;
    ++*a5;
  }
  if ( v7 )
    *v7 = 0;
  ++*a4;
  return result;
}

```

## disassembly

```asm
0x10041a444  mov     [rsp+arg_0], rbx
0x10041a449  mov     [rsp+arg_8], rbp
0x10041a44e  mov     [rsp+arg_10], rsi
0x10041a453  push    rdi
0x10041a454  push    r12
0x10041a456  push    r13
0x10041a458  push    r14
0x10041a45a  push    r15
0x10041a45c  sub     rsp, 20h
0x10041a460  mov     r12, [rsp+48h+arg_20]
0x10041a465  mov     r13, r9
0x10041a468  mov     rbx, r8
0x10041a46b  mov     r14, rdx
0x10041a46e  mov     rdi, rcx
0x10041a471  and     qword ptr [r12], 0
0x10041a476  mov     qword ptr [r9], 1
0x10041a47d  test    rdx, rdx
0x10041a480  jz      short loc_10041A489
0x10041a482  mov     [rdx], rbx
0x10041a485  add     r14, 8
0x10041a489  xor     bpl, bpl
0x10041a48c  cmp     byte ptr [rdi], 22h ; '"'
0x10041a48f  mov     r15, rdi
0x10041a492  jnz     short loc_10041A4A3
0x10041a494  test    bpl, bpl
0x10041a497  mov     sil, 22h ; '"'
0x10041a49a  setz    bpl
0x10041a49e  inc     rdi
0x10041a4a1  jmp     short loc_10041A4DD
0x10041a4a3  inc     qword ptr [r12]
0x10041a4a7  test    rbx, rbx
0x10041a4aa  jz      short loc_10041A4B3
0x10041a4ac  mov     al, [rdi]
0x10041a4ae  mov     [rbx], al
0x10041a4b0  inc     rbx
0x10041a4b3  movsx   esi, byte ptr [rdi]
0x10041a4b6  inc     rdi
0x10041a4b9  mov     ecx, esi; Ch
0x10041a4bb  call    _ismbblead
0x10041a4c0  test    eax, eax
0x10041a4c2  jz      short loc_10041A4D8
0x10041a4c4  inc     qword ptr [r12]
0x10041a4c8  test    rbx, rbx
0x10041a4cb  jz      short loc_10041A4D4
0x10041a4cd  mov     al, [rdi]
0x10041a4cf  mov     [rbx], al
0x10041a4d1  inc     rbx
0x10041a4d4  lea     rdi, [r15+2]
0x10041a4d8  test    sil, sil
0x10041a4db  jz      short loc_10041A4F9
0x10041a4dd  test    bpl, bpl
0x10041a4e0  jnz     short loc_10041A48C
0x10041a4e2  cmp     sil, 20h ; ' '
0x10041a4e6  jz      short loc_10041A4EE
0x10041a4e8  cmp     sil, 9
0x10041a4ec  jnz     short loc_10041A48C
0x10041a4ee  test    rbx, rbx
0x10041a4f1  jz      short loc_10041A4FC
0x10041a4f3  mov     byte ptr [rbx-1], 0
0x10041a4f7  jmp     short loc_10041A4FC
0x10041a4f9  dec     rdi
0x10041a4fc  xor     sil, sil
0x10041a4ff  mov     al, [rdi]
0x10041a501  test    al, al
0x10041a503  jz      loc_10041A5DF
0x10041a509  cmp     al, 20h ; ' '
0x10041a50b  jz      short loc_10041A511
0x10041a50d  cmp     al, 9
0x10041a50f  jnz     short loc_10041A518
0x10041a511  inc     rdi
0x10041a514  mov     al, [rdi]
0x10041a516  jmp     short loc_10041A509
0x10041a518  test    al, al
0x10041a51a  jz      loc_10041A5DF
0x10041a520  test    r14, r14
0x10041a523  jz      short loc_10041A52C
0x10041a525  mov     [r14], rbx
0x10041a528  add     r14, 8
0x10041a52c  inc     qword ptr [r13+0]
0x10041a530  mov     edx, 1
0x10041a535  xor     eax, eax
0x10041a537  jmp     short loc_10041A53E
0x10041a539  inc     rdi
0x10041a53c  inc     eax
0x10041a53e  mov     cl, [rdi]
0x10041a540  cmp     cl, 5Ch ; '\'
0x10041a543  jz      short loc_10041A539
0x10041a545  cmp     cl, 22h ; '"'
0x10041a548  jnz     short loc_10041A57B
0x10041a54a  test    dl, al
0x10041a54c  jnz     short loc_10041A566
0x10041a54e  test    sil, sil
0x10041a551  jz      short loc_10041A55D
0x10041a553  cmp     [rdi+1], cl
0x10041a556  jnz     short loc_10041A55D
0x10041a558  inc     rdi
0x10041a55b  jmp     short loc_10041A566
0x10041a55d  xor     edx, edx
0x10041a55f  test    sil, sil
0x10041a562  setz    sil
0x10041a566  shr     eax, 1
0x10041a568  jmp     short loc_10041A57B
0x10041a56a  dec     eax
0x10041a56c  test    rbx, rbx
0x10041a56f  jz      short loc_10041A577
0x10041a571  mov     byte ptr [rbx], 5Ch ; '\'
0x10041a574  inc     rbx
0x10041a577  inc     qword ptr [r12]
0x10041a57b  test    eax, eax
0x10041a57d  jnz     short loc_10041A56A
0x10041a57f  mov     al, [rdi]
0x10041a581  test    al, al
0x10041a583  jz      short loc_10041A5CB
0x10041a585  test    sil, sil
0x10041a588  jnz     short loc_10041A592
0x10041a58a  cmp     al, 20h ; ' '
0x10041a58c  jz      short loc_10041A5CB
0x10041a58e  cmp     al, 9
0x10041a590  jz      short loc_10041A5CB
0x10041a592  test    edx, edx
0x10041a594  jz      short loc_10041A5C3
0x10041a596  test    rbx, rbx
0x10041a599  jz      short loc_10041A5A0
0x10041a59b  mov     [rbx], al
0x10041a59d  inc     rbx
0x10041a5a0  movsx   ecx, byte ptr [rdi]; Ch
0x10041a5a3  call    _ismbblead
0x10041a5a8  test    eax, eax
0x10041a5aa  jz      short loc_10041A5BF
0x10041a5ac  inc     qword ptr [r12]
0x10041a5b0  inc     rdi
0x10041a5b3  test    rbx, rbx
0x10041a5b6  jz      short loc_10041A5BF
0x10041a5b8  mov     al, [rdi]
0x10041a5ba  mov     [rbx], al
0x10041a5bc  inc     rbx
0x10041a5bf  inc     qword ptr [r12]
0x10041a5c3  inc     rdi
0x10041a5c6  jmp     loc_10041A530
0x10041a5cb  test    rbx, rbx
0x10041a5ce  jz      short loc_10041A5D6
0x10041a5d0  mov     byte ptr [rbx], 0
0x10041a5d3  inc     rbx
0x10041a5d6  inc     qword ptr [r12]
0x10041a5da  jmp     loc_10041A4FF
0x10041a5df  test    r14, r14
0x10041a5e2  jz      short loc_10041A5E8
0x10041a5e4  and     qword ptr [r14], 0
0x10041a5e8  inc     qword ptr [r13+0]
0x10041a5ec  mov     rbx, [rsp+48h+arg_0]
0x10041a5f1  mov     rbp, [rsp+48h+arg_8]
0x10041a5f6  mov     rsi, [rsp+48h+arg_10]
0x10041a5fb  add     rsp, 20h
0x10041a5ff  pop     r15
0x10041a601  pop     r14
0x10041a603  pop     r13
0x10041a605  pop     r12
0x10041a607  pop     rdi
0x10041a608  retn
```
