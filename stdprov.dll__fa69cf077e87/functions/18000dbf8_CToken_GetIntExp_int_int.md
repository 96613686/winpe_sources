# CToken::GetIntExp(int,int)

- ea: `0x18000dbf8`
- end: `0x18000dd83`
- name: `?GetIntExp@CToken@@QEAAJHH@Z`
- size: `395`
- prototype: `__int64 __fastcall(CToken *this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000deb4`

## callees

- `0x1800087f0`
- `0x18000b458`
- `0x18000cad4`
- `0x18000dbf8`
- `0x18000ddbc`
- `0x18000ddf4`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000dc48`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000dc48`

## pseudocode

```c
__int64 __fastcall CToken::GetIntExp(CToken *this, int a2)
{
  CFlexArray *v3; // rdi
  TString *v4; // rax
  int v5; // r8d
  TString *v6; // rbx
  unsigned int v7; // edi
  __int16 v8; // r9
  unsigned __int16 v9; // r15
  unsigned __int16 v10; // r12
  int v11; // r14d
  int v12; // esi
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int16 v15; // ax
  __int64 v16; // rax
  unsigned __int16 *i; // rbx
  int v18; // eax
  int v19; // eax
  unsigned __int16 *v21; // [rsp+20h] [rbp-18h] BYREF
  __int16 v22; // [rsp+28h] [rbp-10h] BYREF
  int v23; // [rsp+2Ch] [rbp-Ch]
  int v24; // [rsp+90h] [rbp+58h] BYREF

  v22 = 0;
  v21 = (unsigned __int16 *)&v22;
  v23 = 0;
  v24 = 0;
  v3 = (CToken *)((char *)this + 48);
  if ( *((_DWORD *)this + 12) <= a2
    || (unsigned int)CToken::IsExpString(this, a2)
    || (v4 = (TString *)CFlexArray::GetAt(v3, a2), (v6 = v4) == 0) )
  {
LABEL_30:
    TString::Empty((TString *)&v21);
    return 0xFFFFFFFFLL;
  }
  else
  {
    v7 = 0;
    v8 = 32;
    v9 = 32;
    v10 = 43;
    v11 = 0;
    v12 = 0;
    v13 = *(_QWORD *)v4;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v13 + 2 * v14) );
    if ( (int)v14 > 0 )
    {
      do
      {
        v15 = TString::GetAt(v6, v12);
        if ( v15 != v8 )
        {
          TString::GetAt(v6, v12);
          TString::operator+=((TString *)&v21);
          v8 = 32;
        }
        ++v12;
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(*(_QWORD *)v6 + 2 * v16) );
      }
      while ( v12 < (int)v16 );
    }
    for ( i = v21; *i; ++i )
    {
      if ( ((*i - 43) & 0xFFFD) != 0 )
      {
        if ( v11 )
          goto LABEL_30;
        v18 = CToken::iConvOprand((CToken *)0xFFFD, i, v5, &v24);
        if ( v18 > 1 )
          i += v18 - 1;
        v19 = v24;
        if ( v9 == 45 )
        {
          v19 = -v24;
          v24 = -v24;
        }
        if ( v10 == 43 )
          v7 += v19;
        else
          v7 -= v19;
        v11 = 1;
        v8 = 32;
        v9 = 32;
      }
      else if ( v11 )
      {
        v10 = *i;
        v11 = 0;
      }
      else
      {
        if ( v9 != v8 )
          goto LABEL_30;
        v9 = *i;
      }
    }
    TString::Empty((TString *)&v21);
    return v7;
  }
}

```

## disassembly

```asm
0x18000dbf8  mov     [rsp-40h+arg_10], r8d
0x18000dbfd  push    rbp
0x18000dbfe  push    rbx
0x18000dbff  push    rsi
0x18000dc00  push    rdi
0x18000dc01  push    r12
0x18000dc03  push    r13
0x18000dc05  push    r14
0x18000dc07  push    r15
0x18000dc09  mov     rbp, rsp
0x18000dc0c  sub     rsp, 38h
0x18000dc10  mov     ebx, edx
0x18000dc12  xor     r13d, r13d
0x18000dc15  mov     [rbp+var_10], r13w
0x18000dc1a  lea     rax, [rbp+var_10]
0x18000dc1e  mov     [rbp+var_18], rax
0x18000dc22  mov     [rbp+var_C], r13d
0x18000dc26  mov     [rbp+arg_10], r13d
0x18000dc2a  lea     rdi, [rcx+30h]
0x18000dc2e  cmp     [rdi], edx
0x18000dc30  jle     loc_18000DD66
0x18000dc36  call    ?IsExpString@CToken@@QEAAHH@Z; CToken::IsExpString(int)
0x18000dc3b  test    eax, eax
0x18000dc3d  jnz     loc_18000DD66
0x18000dc43  mov     edx, ebx
0x18000dc45  mov     rcx, rdi
0x18000dc48  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000dc4e  mov     rbx, rax
0x18000dc51  test    rax, rax
0x18000dc54  jz      loc_18000DD66
0x18000dc5a  mov     edi, r13d
0x18000dc5d  lea     r9d, [r13+20h]
0x18000dc61  movzx   r15d, r9w
0x18000dc65  lea     edx, [r13+2Bh]
0x18000dc69  movzx   r12d, dx
0x18000dc6d  mov     r14d, r13d
0x18000dc70  mov     esi, r13d
0x18000dc73  mov     rcx, [rax]
0x18000dc76  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dc7a  inc     rax
0x18000dc7d  cmp     [rcx+rax*2], r13w
0x18000dc82  jnz     short loc_18000DC7A
0x18000dc84  test    eax, eax
0x18000dc86  jle     short loc_18000DCD0
0x18000dc88  mov     edx, esi; int
0x18000dc8a  mov     rcx, rbx; this
0x18000dc8d  call    ?GetAt@TString@@QEAAGH@Z; TString::GetAt(int)
0x18000dc92  cmp     ax, r9w
0x18000dc96  jz      short loc_18000DCB4
0x18000dc98  mov     edx, esi; int
0x18000dc9a  mov     rcx, rbx; this
0x18000dc9d  call    ?GetAt@TString@@QEAAGH@Z; TString::GetAt(int)
0x18000dca2  movzx   edx, ax
0x18000dca5  lea     rcx, [rbp+var_18]; this
0x18000dca9  call    ??YTString@@QEAAAEAV0@G@Z; TString::operator+=(ushort)
0x18000dcae  mov     r9d, 20h ; ' '
0x18000dcb4  inc     esi
0x18000dcb6  mov     rcx, [rbx]
0x18000dcb9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dcbd  inc     rax
0x18000dcc0  cmp     [rcx+rax*2], r13w
0x18000dcc5  jnz     short loc_18000DCBD
0x18000dcc7  cmp     esi, eax
0x18000dcc9  jl      short loc_18000DC88
0x18000dccb  mov     edx, 2Bh ; '+'
0x18000dcd0  mov     rbx, [rbp+var_18]
0x18000dcd4  cmp     [rbx], r13w
0x18000dcd8  jz      short loc_18000DD59
0x18000dcda  movzx   eax, word ptr [rbx]
0x18000dcdd  sub     ax, dx
0x18000dce0  mov     ecx, 0FFFDh; this
0x18000dce5  test    cx, ax
0x18000dce8  jz      short loc_18000DD38
0x18000dcea  test    r14d, r14d
0x18000dced  jnz     short loc_18000DD66
0x18000dcef  lea     r9, [rbp+arg_10]; int *
0x18000dcf3  mov     rdx, rbx; unsigned __int16 *
0x18000dcf6  call    ?iConvOprand@CToken@@QEAAJPEBGHAEAJ@Z; CToken::iConvOprand(ushort const *,int,long &)
0x18000dcfb  cmp     eax, 1
0x18000dcfe  jle     short loc_18000DD09
0x18000dd00  dec     eax
0x18000dd02  movsxd  rcx, eax
0x18000dd05  lea     rbx, [rbx+rcx*2]
0x18000dd09  mov     eax, [rbp+arg_10]
0x18000dd0c  cmp     r15w, 2Dh ; '-'
0x18000dd11  jnz     short loc_18000DD18
0x18000dd13  neg     eax
0x18000dd15  mov     [rbp+arg_10], eax
0x18000dd18  mov     edx, 2Bh ; '+'
0x18000dd1d  cmp     r12w, dx
0x18000dd21  jnz     short loc_18000DD27
0x18000dd23  add     edi, eax
0x18000dd25  jmp     short loc_18000DD29
0x18000dd27  sub     edi, eax
0x18000dd29  mov     r14d, 1
0x18000dd2f  lea     r9d, [r14+1Fh]
0x18000dd33  mov     r15d, r9d
0x18000dd36  jmp     short loc_18000DD50
0x18000dd38  test    r14d, r14d
0x18000dd3b  jz      short loc_18000DD46
0x18000dd3d  movzx   r12d, word ptr [rbx]
0x18000dd41  mov     r14d, r13d
0x18000dd44  jmp     short loc_18000DD50
0x18000dd46  cmp     r15w, r9w
0x18000dd4a  jnz     short loc_18000DD66
0x18000dd4c  movzx   r15d, word ptr [rbx]
0x18000dd50  add     rbx, 2
0x18000dd54  jmp     loc_18000DCD4
0x18000dd59  lea     rcx, [rbp+var_18]; this
0x18000dd5d  call    ?Empty@TString@@QEAAXXZ; TString::Empty(void)
0x18000dd62  mov     eax, edi
0x18000dd64  jmp     short loc_18000DD72
0x18000dd66  lea     rcx, [rbp+var_18]; this
0x18000dd6a  call    ?Empty@TString@@QEAAXXZ; TString::Empty(void)
0x18000dd6f  or      eax, 0FFFFFFFFh
0x18000dd72  add     rsp, 38h
0x18000dd76  pop     r15
0x18000dd78  pop     r14
0x18000dd7a  pop     r13
0x18000dd7c  pop     r12
0x18000dd7e  pop     rdi
0x18000dd7f  pop     rsi
0x18000dd80  pop     rbx
0x18000dd81  pop     rbp
0x18000dd82  retn
```
