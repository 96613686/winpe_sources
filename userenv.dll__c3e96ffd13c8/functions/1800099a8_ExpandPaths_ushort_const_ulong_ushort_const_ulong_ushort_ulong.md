# ExpandPaths(ushort const *,ulong,ushort const *,ulong,ushort *,ulong &)

- ea: `0x1800099a8`
- end: `0x180009bb2`
- name: `?ExpandPaths@@YAJPEBGK0KPEAGAEAK@Z`
- size: `522`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800098c4`

## callees

- `0x1800099a8`
- `0x1800197fc`
- `0x18001992c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b8f`

## string_xrefs

- `0x180009b78`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall ExpandPaths(
        const unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int *a6)
{
  unsigned int v7; // r10d
  const unsigned __int16 *v8; // r11
  __int64 v9; // rdi
  const unsigned __int16 *v10; // rax
  __int64 v11; // r14
  unsigned int v12; // ebx
  __int64 v13; // r14
  unsigned __int16 v14; // ax
  char v15; // r15
  unsigned int v16; // r9d
  unsigned int i; // esi
  const unsigned __int16 *v18; // r8
  __int64 v19; // rbp
  int v21; // [rsp+20h] [rbp-78h]
  unsigned int v22; // [rsp+30h] [rbp-68h]
  const unsigned __int16 *v23; // [rsp+48h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  unsigned __int16 v25; // [rsp+A0h] [rbp+8h]

  v7 = a4;
  v8 = a3;
  v9 = 0;
  if ( !a1 || (unsigned int)a2 > 0x7FFFFFFF )
  {
    v12 = -2147024809;
LABEL_30:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA8B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)v12,
      v21);
    SetLastError((unsigned __int16)v12);
    goto LABEL_31;
  }
  a2 = (unsigned int)a2;
  v10 = a1;
  v11 = (unsigned int)a2;
  if ( (_DWORD)a2 )
  {
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --a2;
    }
    while ( a2 );
  }
  v12 = a2 == 0 ? 0x80070057 : 0;
  if ( a2 )
    v13 = v11 - a2;
  else
    v13 = 0;
  if ( !a2 )
    goto LABEL_30;
  v25 = a1[v13 - 1];
  v14 = v25;
  v15 = 1;
  v16 = 0;
  for ( i = 0; i < v7; ++i )
  {
    v18 = &v8[i];
    v23 = v18;
    if ( *v18 )
    {
      if ( *v18 != 32 )
      {
        if ( *v18 == 59 )
          goto LABEL_14;
LABEL_26:
        v15 = 0;
        ++v16;
        continue;
      }
      if ( !v15 )
        goto LABEL_26;
    }
    else
    {
      if ( !v15 )
      {
LABEL_14:
        v15 = 1;
        if ( v16 )
        {
          v19 = v13 + v16 + (v14 != 92) + 1LL;
          if ( a5 && v9 + v19 + 1 <= (unsigned __int64)*a6 )
          {
            _GenerateFullyQualifiedPath(a1, v13, &v8[i - (unsigned __int64)v16], v16, v25 == 92, &a5[v9], v22);
            v7 = a4;
            v8 = a3;
          }
          v9 += v19;
          v16 = 0;
          v14 = v25;
          if ( !*v23 )
            i = v7;
        }
        continue;
      }
      i = v7;
    }
  }
  if ( a5 && *a6 >= (unsigned __int64)(v9 + 1) )
    a5[v9] = 0;
  LODWORD(v9) = v9 + 1;
LABEL_31:
  *a6 = v9;
  return v12;
}

```

## disassembly

```asm
0x1800099a8  mov     [rsp+arg_18], r9d
0x1800099ad  mov     [rsp+arg_10], r8
0x1800099b2  push    rbx
0x1800099b3  push    rbp
0x1800099b4  push    rsi
0x1800099b5  push    rdi
0x1800099b6  push    r12
0x1800099b8  push    r13
0x1800099ba  push    r14
0x1800099bc  push    r15
0x1800099be  sub     rsp, 58h
0x1800099c2  mov     r13, rcx
0x1800099c5  mov     r10d, r9d
0x1800099c8  xor     ecx, ecx
0x1800099ca  mov     r11, r8
0x1800099cd  mov     edi, ecx
0x1800099cf  test    r13, r13
0x1800099d2  jz      loc_180009B6B
0x1800099d8  cmp     edx, 7FFFFFFFh
0x1800099de  ja      loc_180009B6B
0x1800099e4  mov     edx, edx
0x1800099e6  mov     rax, r13
0x1800099e9  mov     r14d, edx
0x1800099ec  test    rdx, rdx
0x1800099ef  jz      short loc_180009A00
0x1800099f1  cmp     [rax], cx
0x1800099f4  jz      short loc_180009A00
0x1800099f6  add     rax, 2
0x1800099fa  sub     rdx, 1
0x1800099fe  jnz     short loc_1800099F1
0x180009a00  mov     rax, rdx
0x180009a03  neg     rax
0x180009a06  sbb     ebx, ebx
0x180009a08  not     ebx
0x180009a0a  and     ebx, 80070057h
0x180009a10  test    rdx, rdx
0x180009a13  jz      short loc_180009A1A
0x180009a15  sub     r14, rdx
0x180009a18  jmp     short loc_180009A1D
0x180009a1a  mov     r14, rcx
0x180009a1d  test    rdx, rdx
0x180009a20  jz      loc_180009B70
0x180009a26  movzx   eax, word ptr [r13+r14*2-2]
0x180009a2c  mov     edx, 5Ch ; '\'
0x180009a31  mov     r12, [rsp+98h+arg_20]
0x180009a39  cmp     dx, ax
0x180009a3c  mov     [rsp+98h+arg_0], ax
0x180009a44  mov     r15b, 1
0x180009a47  setz    [rsp+98h+arg_8]
0x180009a4f  mov     [rsp+98h+var_58], edx
0x180009a53  mov     r9d, ecx; unsigned int
0x180009a56  mov     esi, ecx
0x180009a58  test    r10d, r10d
0x180009a5b  jz      loc_180009B2C
0x180009a61  mov     [rsp+98h+var_54], ebx
0x180009a65  mov     rbx, [rsp+98h+arg_28]
0x180009a6d  mov     edx, esi
0x180009a6f  lea     r8, [r11+rdx*2]
0x180009a73  mov     [rsp+98h+var_50], r8
0x180009a78  cmp     [r8], cx
0x180009a7c  jz      loc_180009B5D
0x180009a82  cmp     word ptr [r8], 20h ; ' '
0x180009a87  jz      loc_180009B50
0x180009a8d  cmp     word ptr [r8], 3Bh ; ';'
0x180009a92  jnz     loc_180009B55
0x180009a98  mov     r15b, 1
0x180009a9b  test    r9d, r9d
0x180009a9e  jz      short loc_180009B1D
0x180009aa0  cmp     word ptr [rsp+98h+var_58], ax
0x180009aa5  mov     rbp, rcx
0x180009aa8  mov     r8d, r9d
0x180009aab  setnz   bpl
0x180009aaf  inc     rbp
0x180009ab2  add     rbp, r8
0x180009ab5  add     rbp, r14
0x180009ab8  test    r12, r12
0x180009abb  jz      short loc_180009B01
0x180009abd  mov     eax, [rbx]
0x180009abf  lea     rcx, [rbp+1]
0x180009ac3  add     rcx, rdi
0x180009ac6  cmp     rcx, rax
0x180009ac9  ja      short loc_180009B01
0x180009acb  sub     rdx, r8
0x180009ace  lea     rax, [r12+rdi*2]
0x180009ad2  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x180009ad7  mov     rcx, r13; unsigned __int16 *
0x180009ada  mov     al, [rsp+98h+arg_8]
0x180009ae1  mov     [rsp+98h+var_78], al; bool
0x180009ae5  lea     r8, [r11+rdx*2]; unsigned __int16 *
0x180009ae9  mov     edx, r14d; unsigned int
0x180009aec  call    ?_GenerateFullyQualifiedPath@@YAXPEBGK0K_NPEAGK@Z; _GenerateFullyQualifiedPath(ushort const *,ulong,ushort const *,ulong,bool,ushort *,ulong)
0x180009af1  mov     r10d, [rsp+98h+arg_18]
0x180009af9  mov     r11, [rsp+98h+arg_10]
0x180009b01  mov     rax, [rsp+98h+var_50]
0x180009b06  xor     ecx, ecx
0x180009b08  add     rdi, rbp
0x180009b0b  mov     r9d, ecx
0x180009b0e  cmp     cx, [rax]
0x180009b11  movzx   eax, [rsp+98h+arg_0]
0x180009b19  cmovz   esi, r10d
0x180009b1d  inc     esi
0x180009b1f  cmp     esi, r10d
0x180009b22  jb      loc_180009A6D
0x180009b28  mov     ebx, [rsp+98h+var_54]
0x180009b2c  test    r12, r12
0x180009b2f  jz      short loc_180009B4B
0x180009b31  mov     rax, [rsp+98h+arg_28]
0x180009b39  lea     rcx, [rdi+1]
0x180009b3d  mov     eax, [rax]
0x180009b3f  cmp     rax, rcx
0x180009b42  jb      short loc_180009B4B
0x180009b44  xor     eax, eax
0x180009b46  mov     [r12+rdi*2], ax
0x180009b4b  inc     rdi
0x180009b4e  jmp     short loc_180009B95
0x180009b50  test    r15b, r15b
0x180009b53  jnz     short loc_180009B1D
0x180009b55  mov     r15b, cl
0x180009b58  inc     r9d
0x180009b5b  jmp     short loc_180009B1D
0x180009b5d  test    r15b, r15b
0x180009b60  jz      loc_180009A98
0x180009b66  mov     esi, r10d
0x180009b69  jmp     short loc_180009B1D
0x180009b6b  mov     ebx, 80070057h
0x180009b70  mov     rcx, [rsp+98h]; this
0x180009b78  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180009b7f  mov     r9d, ebx; char *
0x180009b82  mov     edx, 0A8Bh; void *
0x180009b87  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009b8c  movzx   ecx, bx; dwErrCode
0x180009b8f  call    cs:__imp_SetLastError
0x180009b95  mov     rax, [rsp+98h+arg_28]
0x180009b9d  mov     [rax], edi
0x180009b9f  mov     eax, ebx
0x180009ba1  add     rsp, 58h
0x180009ba5  pop     r15
0x180009ba7  pop     r14
0x180009ba9  pop     r13
0x180009bab  pop     r12
0x180009bad  pop     rdi
0x180009bae  pop     rsi
0x180009baf  pop     rbp
0x180009bb0  pop     rbx
0x180009bb1  retn
```
