# YReader::ParseDeclElementCp(DeclElement *)

- ea: `0x1004062a0`
- end: `0x10040649a`
- name: `?ParseDeclElementCp@YReader@@AEAAXPEAVDeclElement@@@Z`
- size: `506`
- prototype: `void __fastcall(YReader *__hidden this, struct DeclElement *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x100405fc0`
- `0x1004062a0`

## callees

- `0x100401780`
- `0x1004062a0`
- `0x10040a020`

## pseudocode

```c
void __fastcall YReader::ParseDeclElementCp(YReader *this, struct DeclElement *a2)
{
  int TokenDeclInner; // eax
  int v5; // eax
  int v6; // eax
  bool v7; // zf
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax

  TokenDeclInner = YReader::GetTokenDeclInner(this);
  if ( TokenDeclInner == 12 )
  {
    *((_DWORD *)a2 + 8) = 4;
    v10 = YReader::GetTokenDeclInner(this) - 52;
    if ( !v10 || (v11 = v10 - 1) == 0 || v11 == 5 )
      YReader::GetTokenDeclInner(this);
LABEL_26:
    switch ( *((_DWORD *)this + 28) )
    {
      case '/':
        do
        {
          v15 = YReader::GetTokenDeclInner(this);
          if ( v15 == 12 )
          {
            v16 = YReader::GetTokenDeclInner(this) - 52;
            if ( !v16 || (v17 = v16 - 1) == 0 || v17 == 5 )
              YReader::GetTokenDeclInner(this);
          }
          else
          {
            if ( v15 != 50 )
              goto LABEL_48;
            YReader::ParseDeclElementCp(this, a2);
          }
          v18 = *((_DWORD *)this + 28);
        }
        while ( v18 == 47 );
        if ( v18 == 56 )
        {
LABEL_5:
          v5 = YReader::GetTokenDeclInner(this) - 52;
          if ( v5 )
          {
            v6 = v5 - 1;
            if ( v6 )
            {
              v7 = v6 == 5;
              goto LABEL_8;
            }
          }
          goto LABEL_9;
        }
        break;
      case '8':
        goto LABEL_5;
      case '9':
        while ( 1 )
        {
          v12 = YReader::GetTokenDeclInner(this);
          if ( v12 == 12 )
          {
            v13 = YReader::GetTokenDeclInner(this) - 52;
            if ( !v13 || (v14 = v13 - 1) == 0 || v14 == 5 )
              YReader::GetTokenDeclInner(this);
          }
          else
          {
            if ( v12 != 50 )
              goto LABEL_48;
            YReader::ParseDeclElementCp(this, a2);
          }
          if ( *((_DWORD *)this + 28) == 56 )
            goto LABEL_5;
          if ( *((_DWORD *)this + 28) != 57 )
            goto LABEL_48;
        }
    }
LABEL_48:
    MXRRaiseException(-1072894419);
    JUMPOUT(0x100406499LL);
  }
  if ( TokenDeclInner != 43 )
  {
    if ( TokenDeclInner != 50 )
      goto LABEL_48;
    *((_DWORD *)a2 + 8) = 4;
    YReader::ParseDeclElementCp(this, a2);
    if ( *((_DWORD *)this + 28) == 56 )
      goto LABEL_5;
    goto LABEL_26;
  }
  if ( *((_DWORD *)a2 + 8) == 4 )
    goto LABEL_48;
  v8 = YReader::GetTokenDeclInner(this) - 56;
  if ( !v8 )
  {
    *((_DWORD *)a2 + 8) = 3;
    v7 = (unsigned int)YReader::GetTokenDeclInner(this) == 58;
LABEL_8:
    if ( !v7 )
      return;
    goto LABEL_9;
  }
  if ( v8 != 1 )
    goto LABEL_48;
  *((_DWORD *)a2 + 8) = 2;
  if ( (unsigned int)YReader::GetTokenDeclInner(this) != 12 )
    goto LABEL_48;
  while ( 1 )
  {
    v9 = YReader::GetTokenDeclInner(this) - 56;
    if ( !v9 )
      break;
    if ( v9 != 1 || (unsigned int)YReader::GetTokenDeclInner(this) != 12 )
      goto LABEL_48;
  }
  if ( (unsigned int)YReader::GetTokenDeclInner(this) != 58 )
    goto LABEL_48;
LABEL_9:
  YReader::GetTokenDeclInner(this);
}

```

## disassembly

```asm
0x1004062a0  mov     [rsp+arg_0], rbx
0x1004062a5  push    rdi
0x1004062a6  sub     rsp, 20h
0x1004062aa  mov     rdi, rdx
0x1004062ad  mov     rbx, rcx
0x1004062b0  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004062b5  cmp     eax, 0Ch
0x1004062b8  jz      loc_1004063A5
0x1004062be  cmp     eax, 2Bh ; '+'
0x1004062c1  jz      short loc_100406312
0x1004062c3  cmp     eax, 32h ; '2'
0x1004062c6  jnz     loc_10040648F
0x1004062cc  mov     rdx, rdi; struct DeclElement *
0x1004062cf  mov     dword ptr [rdi+20h], 4
0x1004062d6  mov     rcx, rbx; this
0x1004062d9  call    ?ParseDeclElementCp@YReader@@AEAAXPEAVDeclElement@@@Z; YReader::ParseDeclElementCp(DeclElement *)
0x1004062de  cmp     dword ptr [rbx+70h], 38h ; '8'
0x1004062e2  jnz     loc_1004063CB
0x1004062e8  mov     rcx, rbx; this
0x1004062eb  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004062f0  sub     eax, 34h ; '4'
0x1004062f3  jz      short loc_1004062FF
0x1004062f5  sub     eax, 1
0x1004062f8  jz      short loc_1004062FF
0x1004062fa  cmp     eax, 5
0x1004062fd  jnz     short loc_100406307
0x1004062ff  mov     rcx, rbx; this
0x100406302  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406307  mov     rbx, [rsp+28h+arg_0]
0x10040630c  add     rsp, 20h
0x100406310  pop     rdi
0x100406311  retn
0x100406312  cmp     dword ptr [rdi+20h], 4
0x100406316  jz      loc_10040648F
0x10040631c  mov     rcx, rbx; this
0x10040631f  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406324  sub     eax, 38h ; '8'
0x100406327  jz      short loc_10040638E
0x100406329  cmp     eax, 1
0x10040632c  jnz     loc_10040648F
0x100406332  mov     rcx, rbx; this
0x100406335  mov     dword ptr [rdi+20h], 2
0x10040633c  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406341  cmp     eax, 0Ch
0x100406344  jnz     loc_10040648F
0x10040634a  nop     word ptr [rax+rax+00h]
0x100406350  mov     rcx, rbx; this
0x100406353  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406358  sub     eax, 38h ; '8'
0x10040635b  jz      short loc_100406378
0x10040635d  cmp     eax, 1
0x100406360  jnz     loc_10040648F
0x100406366  mov     rcx, rbx; this
0x100406369  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x10040636e  cmp     eax, 0Ch
0x100406371  jz      short loc_100406350
0x100406373  jmp     loc_10040648F
0x100406378  mov     rcx, rbx; this
0x10040637b  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406380  cmp     eax, 3Ah ; ':'
0x100406383  jz      loc_1004062FF
0x100406389  jmp     loc_10040648F
0x10040638e  mov     rcx, rbx; this
0x100406391  mov     dword ptr [rdi+20h], 3
0x100406398  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x10040639d  cmp     eax, 3Ah ; ':'
0x1004063a0  jmp     loc_1004062FD
0x1004063a5  mov     rcx, rbx; this
0x1004063a8  mov     dword ptr [rdi+20h], 4
0x1004063af  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004063b4  sub     eax, 34h ; '4'
0x1004063b7  jz      short loc_1004063C3
0x1004063b9  sub     eax, 1
0x1004063bc  jz      short loc_1004063C3
0x1004063be  cmp     eax, 5
0x1004063c1  jnz     short loc_1004063CB
0x1004063c3  mov     rcx, rbx; this
0x1004063c6  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004063cb  mov     ecx, [rbx+70h]
0x1004063ce  sub     ecx, 2Fh ; '/'
0x1004063d1  jz      short loc_100406440
0x1004063d3  sub     ecx, 9
0x1004063d6  jz      loc_1004062E8
0x1004063dc  cmp     ecx, 1
0x1004063df  jnz     loc_10040648F
0x1004063e5  mov     rcx, rbx; this
0x1004063e8  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004063ed  cmp     eax, 0Ch
0x1004063f0  jz      short loc_100406408
0x1004063f2  cmp     eax, 32h ; '2'
0x1004063f5  jnz     loc_10040648F
0x1004063fb  mov     rdx, rdi; struct DeclElement *
0x1004063fe  mov     rcx, rbx; this
0x100406401  call    ?ParseDeclElementCp@YReader@@AEAAXPEAVDeclElement@@@Z; YReader::ParseDeclElementCp(DeclElement *)
0x100406406  jmp     short loc_100406427
0x100406408  mov     rcx, rbx; this
0x10040640b  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406410  sub     eax, 34h ; '4'
0x100406413  jz      short loc_10040641F
0x100406415  sub     eax, 1
0x100406418  jz      short loc_10040641F
0x10040641a  cmp     eax, 5
0x10040641d  jnz     short loc_100406427
0x10040641f  mov     rcx, rbx; this
0x100406422  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406427  mov     ecx, [rbx+70h]
0x10040642a  sub     ecx, 38h ; '8'
0x10040642d  jz      loc_1004062E8
0x100406433  cmp     ecx, 1
0x100406436  jz      short loc_1004063E5
0x100406438  jmp     short loc_10040648F
0x100406440  mov     rcx, rbx; this
0x100406443  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406448  cmp     eax, 0Ch
0x10040644b  jz      short loc_10040645F
0x10040644d  cmp     eax, 32h ; '2'
0x100406450  jnz     short loc_10040648F
0x100406452  mov     rdx, rdi; struct DeclElement *
0x100406455  mov     rcx, rbx; this
0x100406458  call    ?ParseDeclElementCp@YReader@@AEAAXPEAVDeclElement@@@Z; YReader::ParseDeclElementCp(DeclElement *)
0x10040645d  jmp     short loc_10040647E
0x10040645f  mov     rcx, rbx; this
0x100406462  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406467  sub     eax, 34h ; '4'
0x10040646a  jz      short loc_100406476
0x10040646c  sub     eax, 1
0x10040646f  jz      short loc_100406476
0x100406471  cmp     eax, 5
0x100406474  jnz     short loc_10040647E
0x100406476  mov     rcx, rbx; this
0x100406479  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x10040647e  mov     eax, [rbx+70h]
0x100406481  cmp     eax, 2Fh ; '/'
0x100406484  jz      short loc_100406440
0x100406486  cmp     eax, 38h ; '8'
0x100406489  jz      loc_1004062E8
0x10040648f  mov     ecx, 0C00CEE2Dh; int
0x100406494  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
