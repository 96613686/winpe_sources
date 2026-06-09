# strip_absolute_path

- ea: `0x1400054bc`
- end: `0x140005614`
- name: `strip_absolute_path`
- size: `344`
- prototype: `char *__fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004bd4`

## callees

- `0x1400054bc`
- `0x140007298`

## pseudocode

```c
char *__fastcall strip_absolute_path(__int64 a1, char *a2)
{
  char v2; // al
  char *v3; // rbx
  char v5; // al
  __int64 v6; // rax
  char *v7; // rdi
  char *v8; // rdi
  char *v9; // rcx
  char *v10; // rdx
  char v11; // al

  v2 = *a2;
  v3 = a2;
  if ( (*a2 == 47 || v2 == 92)
    && (a2[1] == 47 || a2[1] == 92)
    && (a2[2] == 46 || a2[2] == 63)
    && (a2[3] == 47 || a2[3] == 92) )
  {
    if ( a2[2] != 63
      || ((a2[4] - 85) & 0xDF) != 0
      || ((a2[5] - 78) & 0xDF) != 0
      || ((a2[6] - 67) & 0xDF) != 0
      || (v5 = a2[7], v5 != 47) && v5 != 92 )
    {
      v6 = 4;
    }
    else
    {
      v6 = 8;
    }
    v7 = &a2[v6];
    if ( !*(_BYTE *)(a1 + 192) )
    {
      lafe_warnc(0, "Removing leading drive letter from member names");
      *(_BYTE *)(a1 + 192) = 1;
    }
    v2 = *v7;
    v3 = v7;
  }
  do
  {
    v8 = v3;
    if ( (v2 >= 97 && *v3 <= 122 || (unsigned __int8)(*v3 - 65) <= 0x19u) && v3[1] == 58 )
    {
      v3 += 2;
      if ( !*(_BYTE *)(a1 + 192) )
      {
        lafe_warnc(0, "Removing leading drive letter from member names");
LABEL_26:
        *(_BYTE *)(a1 + 192) = 1;
      }
    }
    while ( 1 )
    {
      v2 = *v3;
      if ( *v3 != 47 && v2 != 92 )
        break;
      v9 = v3 + 1;
      if ( v3[1] != 46 )
        goto LABEL_36;
      v10 = v3 + 2;
      v11 = v3[2];
      if ( v11 == 46 )
      {
        v3 += 3;
        if ( *v3 == 47 || *v3 == 92 )
          goto LABEL_37;
      }
      if ( v11 == 47 || v11 == 92 )
        v3 = v10;
      else
LABEL_36:
        v3 = v9;
LABEL_37:
      if ( !*(_BYTE *)(a1 + 192) )
      {
        lafe_warnc(0, "Removing leading '%c' from member names", (unsigned int)*v8);
        goto LABEL_26;
      }
    }
  }
  while ( v8 != v3 );
  return v3;
}

```

## disassembly

```asm
0x1400054bc  mov     [rsp+arg_0], rbx
0x1400054c1  mov     [rsp+arg_8], rsi
0x1400054c6  push    rdi
0x1400054c7  sub     rsp, 20h
0x1400054cb  mov     al, [rdx]
0x1400054cd  mov     rbx, rdx
0x1400054d0  mov     rsi, rcx
0x1400054d3  cmp     al, 2Fh ; '/'
0x1400054d5  jz      short loc_1400054DF
0x1400054d7  cmp     al, 5Ch ; '\'
0x1400054d9  jnz     loc_140005564
0x1400054df  cmp     byte ptr [rdx+1], 2Fh ; '/'
0x1400054e3  jz      short loc_1400054EB
0x1400054e5  cmp     byte ptr [rdx+1], 5Ch ; '\'
0x1400054e9  jnz     short loc_140005564
0x1400054eb  cmp     byte ptr [rdx+2], 2Eh ; '.'
0x1400054ef  jz      short loc_1400054F7
0x1400054f1  cmp     byte ptr [rdx+2], 3Fh ; '?'
0x1400054f5  jnz     short loc_140005564
0x1400054f7  cmp     byte ptr [rdx+3], 2Fh ; '/'
0x1400054fb  jz      short loc_140005503
0x1400054fd  cmp     byte ptr [rdx+3], 5Ch ; '\'
0x140005501  jnz     short loc_140005564
0x140005503  cmp     byte ptr [rdx+2], 3Fh ; '?'
0x140005507  jnz     short loc_140005538
0x140005509  mov     al, [rdx+4]
0x14000550c  mov     cl, 0DFh
0x14000550e  sub     al, 55h ; 'U'
0x140005510  test    cl, al
0x140005512  jnz     short loc_140005538
0x140005514  mov     al, [rdx+5]
0x140005517  sub     al, 4Eh ; 'N'
0x140005519  test    cl, al
0x14000551b  jnz     short loc_140005538
0x14000551d  mov     al, [rdx+6]
0x140005520  sub     al, 43h ; 'C'
0x140005522  test    cl, al
0x140005524  jnz     short loc_140005538
0x140005526  mov     al, [rdx+7]
0x140005529  cmp     al, 2Fh ; '/'
0x14000552b  jz      short loc_140005531
0x14000552d  cmp     al, 5Ch ; '\'
0x14000552f  jnz     short loc_140005538
0x140005531  mov     eax, 8
0x140005536  jmp     short loc_14000553D
0x140005538  mov     eax, 4
0x14000553d  cmp     byte ptr [rsi+0C0h], 0
0x140005544  lea     rdi, [rax+rdx]
0x140005548  jnz     short loc_14000555F
0x14000554a  lea     rdx, aRemovingLeadin_0; "Removing leading drive letter from memb"...
0x140005551  xor     ecx, ecx
0x140005553  call    lafe_warnc
0x140005558  mov     byte ptr [rsi+0C0h], 1
0x14000555f  mov     al, [rdi]
0x140005561  mov     rbx, rdi
0x140005564  mov     rdi, rbx
0x140005567  cmp     al, 61h ; 'a'
0x140005569  jl      short loc_140005570
0x14000556b  cmp     byte ptr [rbx], 7Ah ; 'z'
0x14000556e  jle     short loc_140005578
0x140005570  mov     al, [rbx]
0x140005572  sub     al, 41h ; 'A'
0x140005574  cmp     al, 19h
0x140005576  ja      short loc_1400055A0
0x140005578  cmp     byte ptr [rbx+1], 3Ah ; ':'
0x14000557c  jnz     short loc_1400055A0
0x14000557e  add     rbx, 2
0x140005582  cmp     byte ptr [rsi+0C0h], 0
0x140005589  jnz     short loc_1400055A0
0x14000558b  lea     rdx, aRemovingLeadin_0; "Removing leading drive letter from memb"...
0x140005592  xor     ecx, ecx
0x140005594  call    lafe_warnc
0x140005599  mov     byte ptr [rsi+0C0h], 1
0x1400055a0  mov     al, [rbx]
0x1400055a2  cmp     al, 2Fh ; '/'
0x1400055a4  jz      short loc_1400055AA
0x1400055a6  cmp     al, 5Ch ; '\'
0x1400055a8  jnz     short loc_1400055F8
0x1400055aa  lea     rcx, [rbx+1]
0x1400055ae  cmp     byte ptr [rcx], 2Eh ; '.'
0x1400055b1  jnz     short loc_1400055D8
0x1400055b3  lea     rdx, [rbx+2]
0x1400055b7  mov     al, [rdx]
0x1400055b9  cmp     al, 2Eh ; '.'
0x1400055bb  jnz     short loc_1400055CB
0x1400055bd  add     rbx, 3
0x1400055c1  cmp     byte ptr [rbx], 2Fh ; '/'
0x1400055c4  jz      short loc_1400055DB
0x1400055c6  cmp     byte ptr [rbx], 5Ch ; '\'
0x1400055c9  jz      short loc_1400055DB
0x1400055cb  cmp     al, 2Fh ; '/'
0x1400055cd  jz      short loc_1400055D3
0x1400055cf  cmp     al, 5Ch ; '\'
0x1400055d1  jnz     short loc_1400055D8
0x1400055d3  mov     rbx, rdx
0x1400055d6  jmp     short loc_1400055DB
0x1400055d8  mov     rbx, rcx
0x1400055db  cmp     byte ptr [rsi+0C0h], 0
0x1400055e2  jnz     short loc_1400055A0
0x1400055e4  movsx   r8d, byte ptr [rdi]
0x1400055e8  lea     rdx, aRemovingLeadin; "Removing leading '%c' from member names"
0x1400055ef  xor     ecx, ecx
0x1400055f1  call    lafe_warnc
0x1400055f6  jmp     short loc_140005599
0x1400055f8  cmp     rdi, rbx
0x1400055fb  jnz     loc_140005564
0x140005601  mov     rsi, [rsp+28h+arg_8]
0x140005606  mov     rax, rbx
0x140005609  mov     rbx, [rsp+28h+arg_0]
0x14000560e  add     rsp, 20h
0x140005612  pop     rdi
0x140005613  retn
```
