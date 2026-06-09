# parse_command_line_char_

- ea: `0x10042a3d4`
- end: `0x10042a599`
- name: `parse_command_line_char_`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10042a604`

## callees

- `0x10042a3d4`
- `0x10043015c`

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
0x10042a3d4  mov     [rsp+arg_0], rbx
0x10042a3d9  mov     [rsp+arg_8], rbp
0x10042a3de  mov     [rsp+arg_10], rsi
0x10042a3e3  push    rdi
0x10042a3e4  push    r12
0x10042a3e6  push    r13
0x10042a3e8  push    r14
0x10042a3ea  push    r15
0x10042a3ec  sub     rsp, 20h
0x10042a3f0  mov     r12, [rsp+48h+arg_20]
0x10042a3f5  mov     r13, r9
0x10042a3f8  mov     rbx, r8
0x10042a3fb  mov     r14, rdx
0x10042a3fe  mov     rdi, rcx
0x10042a401  and     qword ptr [r12], 0
0x10042a406  mov     qword ptr [r9], 1
0x10042a40d  test    rdx, rdx
0x10042a410  jz      short loc_10042A419
0x10042a412  mov     [rdx], rbx
0x10042a415  add     r14, 8
0x10042a419  xor     bpl, bpl
0x10042a41c  cmp     byte ptr [rdi], 22h ; '"'
0x10042a41f  mov     r15, rdi
0x10042a422  jnz     short loc_10042A433
0x10042a424  test    bpl, bpl
0x10042a427  mov     sil, 22h ; '"'
0x10042a42a  setz    bpl
0x10042a42e  inc     rdi
0x10042a431  jmp     short loc_10042A46D
0x10042a433  inc     qword ptr [r12]
0x10042a437  test    rbx, rbx
0x10042a43a  jz      short loc_10042A443
0x10042a43c  mov     al, [rdi]
0x10042a43e  mov     [rbx], al
0x10042a440  inc     rbx
0x10042a443  movsx   esi, byte ptr [rdi]
0x10042a446  inc     rdi
0x10042a449  mov     ecx, esi; Ch
0x10042a44b  call    _ismbblead
0x10042a450  test    eax, eax
0x10042a452  jz      short loc_10042A468
0x10042a454  inc     qword ptr [r12]
0x10042a458  test    rbx, rbx
0x10042a45b  jz      short loc_10042A464
0x10042a45d  mov     al, [rdi]
0x10042a45f  mov     [rbx], al
0x10042a461  inc     rbx
0x10042a464  lea     rdi, [r15+2]
0x10042a468  test    sil, sil
0x10042a46b  jz      short loc_10042A489
0x10042a46d  test    bpl, bpl
0x10042a470  jnz     short loc_10042A41C
0x10042a472  cmp     sil, 20h ; ' '
0x10042a476  jz      short loc_10042A47E
0x10042a478  cmp     sil, 9
0x10042a47c  jnz     short loc_10042A41C
0x10042a47e  test    rbx, rbx
0x10042a481  jz      short loc_10042A48C
0x10042a483  mov     byte ptr [rbx-1], 0
0x10042a487  jmp     short loc_10042A48C
0x10042a489  dec     rdi
0x10042a48c  xor     sil, sil
0x10042a48f  mov     al, [rdi]
0x10042a491  test    al, al
0x10042a493  jz      loc_10042A56F
0x10042a499  cmp     al, 20h ; ' '
0x10042a49b  jz      short loc_10042A4A1
0x10042a49d  cmp     al, 9
0x10042a49f  jnz     short loc_10042A4A8
0x10042a4a1  inc     rdi
0x10042a4a4  mov     al, [rdi]
0x10042a4a6  jmp     short loc_10042A499
0x10042a4a8  test    al, al
0x10042a4aa  jz      loc_10042A56F
0x10042a4b0  test    r14, r14
0x10042a4b3  jz      short loc_10042A4BC
0x10042a4b5  mov     [r14], rbx
0x10042a4b8  add     r14, 8
0x10042a4bc  inc     qword ptr [r13+0]
0x10042a4c0  mov     edx, 1
0x10042a4c5  xor     eax, eax
0x10042a4c7  jmp     short loc_10042A4CE
0x10042a4c9  inc     rdi
0x10042a4cc  inc     eax
0x10042a4ce  mov     cl, [rdi]
0x10042a4d0  cmp     cl, 5Ch ; '\'
0x10042a4d3  jz      short loc_10042A4C9
0x10042a4d5  cmp     cl, 22h ; '"'
0x10042a4d8  jnz     short loc_10042A50B
0x10042a4da  test    dl, al
0x10042a4dc  jnz     short loc_10042A4F6
0x10042a4de  test    sil, sil
0x10042a4e1  jz      short loc_10042A4ED
0x10042a4e3  cmp     [rdi+1], cl
0x10042a4e6  jnz     short loc_10042A4ED
0x10042a4e8  inc     rdi
0x10042a4eb  jmp     short loc_10042A4F6
0x10042a4ed  xor     edx, edx
0x10042a4ef  test    sil, sil
0x10042a4f2  setz    sil
0x10042a4f6  shr     eax, 1
0x10042a4f8  jmp     short loc_10042A50B
0x10042a4fa  dec     eax
0x10042a4fc  test    rbx, rbx
0x10042a4ff  jz      short loc_10042A507
0x10042a501  mov     byte ptr [rbx], 5Ch ; '\'
0x10042a504  inc     rbx
0x10042a507  inc     qword ptr [r12]
0x10042a50b  test    eax, eax
0x10042a50d  jnz     short loc_10042A4FA
0x10042a50f  mov     al, [rdi]
0x10042a511  test    al, al
0x10042a513  jz      short loc_10042A55B
0x10042a515  test    sil, sil
0x10042a518  jnz     short loc_10042A522
0x10042a51a  cmp     al, 20h ; ' '
0x10042a51c  jz      short loc_10042A55B
0x10042a51e  cmp     al, 9
0x10042a520  jz      short loc_10042A55B
0x10042a522  test    edx, edx
0x10042a524  jz      short loc_10042A553
0x10042a526  test    rbx, rbx
0x10042a529  jz      short loc_10042A530
0x10042a52b  mov     [rbx], al
0x10042a52d  inc     rbx
0x10042a530  movsx   ecx, byte ptr [rdi]; Ch
0x10042a533  call    _ismbblead
0x10042a538  test    eax, eax
0x10042a53a  jz      short loc_10042A54F
0x10042a53c  inc     qword ptr [r12]
0x10042a540  inc     rdi
0x10042a543  test    rbx, rbx
0x10042a546  jz      short loc_10042A54F
0x10042a548  mov     al, [rdi]
0x10042a54a  mov     [rbx], al
0x10042a54c  inc     rbx
0x10042a54f  inc     qword ptr [r12]
0x10042a553  inc     rdi
0x10042a556  jmp     loc_10042A4C0
0x10042a55b  test    rbx, rbx
0x10042a55e  jz      short loc_10042A566
0x10042a560  mov     byte ptr [rbx], 0
0x10042a563  inc     rbx
0x10042a566  inc     qword ptr [r12]
0x10042a56a  jmp     loc_10042A48F
0x10042a56f  test    r14, r14
0x10042a572  jz      short loc_10042A578
0x10042a574  and     qword ptr [r14], 0
0x10042a578  inc     qword ptr [r13+0]
0x10042a57c  mov     rbx, [rsp+48h+arg_0]
0x10042a581  mov     rbp, [rsp+48h+arg_8]
0x10042a586  mov     rsi, [rsp+48h+arg_10]
0x10042a58b  add     rsp, 20h
0x10042a58f  pop     r15
0x10042a591  pop     r14
0x10042a593  pop     r13
0x10042a595  pop     r12
0x10042a597  pop     rdi
0x10042a598  retn
```
