# ParsePath(ushort const *,ushort * *,ushort * *)

- ea: `0x180007870`
- end: `0x180007a3a`
- name: `?ParsePath@@YAKPEBGPEAPEAG1@Z`
- size: `458`
- prototype: `unsigned int __fastcall(const unsigned __int16 *Src, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001b610`

## callees

- `0x18000214c`
- `0x180007870`
- `0x1800172b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800079c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800079d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800079c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800079d4`

## pseudocode

```c
__int64 __fastcall ParsePath(const unsigned __int16 *Src, unsigned __int16 **a2, unsigned __int16 **a3)
{
  unsigned int v6; // ebx
  const unsigned __int16 *i; // rsi
  _WORD *v8; // rdi
  unsigned __int16 *v9; // rbp
  __int64 v10; // rax
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // rax
  _WORD *v13; // rcx
  char *v14; // r14
  __int16 v15; // ax
  _WORD *v16; // rax
  unsigned int v17; // ecx
  const unsigned __int16 *v18; // rcx
  unsigned __int64 v20; // [rsp+50h] [rbp+8h]

  v6 = 0;
  i = Src;
  v8 = 0;
  v9 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( *Src )
  {
    v10 = -1;
    do
      ++v10;
    while ( Src[v10] );
    for ( i = &Src[v10 - 1]; Src < i && *i != 92; --i )
      ;
  }
  if ( !a2 )
    goto LABEL_25;
  v20 = i - Src;
  v11 = v20 + 1;
  v12 = 2 * (v20 + 1);
  if ( !is_mul_ok(v20 + 1, 2u) )
    v12 = -1;
  v8 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v8 )
    return 8;
  if ( v20 > 0x7FFFFFFE )
  {
    v17 = -2147024809;
    if ( v20 != -1 )
      *v8 = 0;
LABEL_34:
    v6 = (unsigned __int16)v17;
    if ( (v17 & 0x1FFF0000) != 0x70000 )
      v6 = v17;
    if ( v6 )
      goto LABEL_30;
    return v6;
  }
  v13 = v8;
  v14 = (char *)((char *)Src - (char *)v8);
  while ( v11 != 1 )
  {
    v15 = *(_WORD *)((char *)v13 + (_QWORD)v14);
    if ( !v15 )
      break;
    *v13 = v15;
    --v11;
    ++v13;
  }
  v16 = v13 - 1;
  if ( v11 )
    v16 = v13;
  v17 = v11 == 0 ? 0x8007007A : 0;
  *v16 = 0;
  if ( !v11 )
    goto LABEL_34;
LABEL_25:
  if ( a3 )
  {
    v18 = i + 1;
    if ( *i != 92 )
      v18 = i;
    v9 = WcsDup(v18);
    if ( !v9 )
    {
      v6 = 8;
LABEL_30:
      if ( v8 )
        operator delete(v8);
      return v6;
    }
  }
  if ( a2 )
    *a2 = v8;
  if ( a3 )
    *a3 = v9;
  return v6;
}

```

## disassembly

```asm
0x180007870  mov     [rsp+arg_8], rbx
0x180007875  mov     [rsp+arg_10], rbp
0x18000787a  mov     [rsp+arg_18], rsi
0x18000787f  push    rdi
0x180007880  push    r12
0x180007882  push    r13
0x180007884  push    r14
0x180007886  push    r15
0x180007888  sub     rsp, 20h
0x18000788c  mov     r12, r8
0x18000788f  mov     r13, rdx
0x180007892  xor     r8d, r8d
0x180007895  mov     r14, rcx
0x180007898  mov     ebx, r8d
0x18000789b  mov     rsi, rcx
0x18000789e  mov     edi, r8d
0x1800078a1  mov     ebp, r8d
0x1800078a4  test    rdx, rdx
0x1800078a7  jz      short loc_1800078AC
0x1800078a9  mov     [rdx], r8
0x1800078ac  test    r12, r12
0x1800078af  jz      short loc_1800078B5
0x1800078b1  mov     [r12], r8
0x1800078b5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800078b9  cmp     [r14], r8w
0x1800078bd  jz      short loc_1800078E5
0x1800078bf  mov     rax, rcx
0x1800078c2  inc     rax
0x1800078c5  cmp     [r14+rax*2], r8w
0x1800078ca  jnz     short loc_1800078C2
0x1800078cc  lea     rsi, [r14-2]
0x1800078d0  lea     rsi, [rsi+rax*2]
0x1800078d4  jmp     short loc_1800078E0
0x1800078d6  cmp     word ptr [rsi], 5Ch ; '\'
0x1800078da  jz      short loc_1800078E5
0x1800078dc  sub     rsi, 2
0x1800078e0  cmp     r14, rsi
0x1800078e3  jb      short loc_1800078D6
0x1800078e5  test    r13, r13
0x1800078e8  jz      loc_180007997
0x1800078ee  mov     rax, rsi
0x1800078f1  sub     rax, r14
0x1800078f4  sar     rax, 1
0x1800078f7  mov     [rsp+48h+arg_0], rax
0x1800078fc  lea     r15, [rax+1]
0x180007900  mov     eax, 2
0x180007905  mul     r15
0x180007908  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000790f  cmovo   rax, rcx
0x180007913  mov     rcx, rax; unsigned __int64
0x180007916  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000791b  xor     r8d, r8d
0x18000791e  mov     rdi, rax
0x180007921  test    rax, rax
0x180007924  jnz     short loc_18000792E
0x180007926  lea     ebx, [rax+8]
0x180007929  jmp     loc_180007A1A
0x18000792e  lea     rax, [r15-1]
0x180007932  mov     ecx, 7FFFFFFEh
0x180007937  cmp     rax, rcx
0x18000793a  ja      loc_1800079E2
0x180007940  cmp     [rsp+48h+arg_0], rcx
0x180007945  jbe     short loc_180007952
0x180007947  mov     ecx, 80070057h
0x18000794c  mov     [rdi], r8w
0x180007950  jmp     short loc_180007993
0x180007952  mov     rcx, rdi
0x180007955  sub     r14, rdi
0x180007958  lea     rdx, [r15-1]
0x18000795c  test    rdx, rdx
0x18000795f  jz      short loc_180007977
0x180007961  movzx   eax, word ptr [r14+rcx]
0x180007966  test    ax, ax
0x180007969  jz      short loc_180007977
0x18000796b  mov     [rcx], ax
0x18000796e  mov     r15, rdx
0x180007971  add     rcx, 2
0x180007975  jmp     short loc_180007958
0x180007977  lea     rax, [rcx-2]
0x18000797b  test    r15, r15
0x18000797e  cmovnz  rax, rcx
0x180007982  neg     r15
0x180007985  sbb     ecx, ecx
0x180007987  not     ecx
0x180007989  and     ecx, 8007007Ah
0x18000798f  mov     [rax], r8w
0x180007993  test    ecx, ecx
0x180007995  js      short loc_1800079F0
0x180007997  test    r12, r12
0x18000799a  jz      short loc_180007A08
0x18000799c  cmp     word ptr [rsi], 5Ch ; '\'
0x1800079a0  lea     rcx, [rsi+2]
0x1800079a4  cmovnz  rcx, rsi; Src
0x1800079a8  call    ?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x1800079ad  mov     rbp, rax
0x1800079b0  test    rax, rax
0x1800079b3  jnz     short loc_180007A08
0x1800079b5  lea     ebx, [rax+8]
0x1800079b8  test    rdi, rdi
0x1800079bb  jz      short loc_180007A1A
0x1800079bd  mov     rcx, rdi
0x1800079c0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800079c7  nop     dword ptr [rax+rax+00h]
0x1800079cc  test    rbp, rbp
0x1800079cf  jz      short loc_180007A1A
0x1800079d1  mov     rcx, rbp
0x1800079d4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800079db  nop     dword ptr [rax+rax+00h]
0x1800079e0  jmp     short loc_180007A1A
0x1800079e2  mov     ecx, 80070057h
0x1800079e7  test    r15, r15
0x1800079ea  jz      short loc_1800079F0
0x1800079ec  mov     [rdi], r8w
0x1800079f0  mov     eax, ecx
0x1800079f2  movzx   ebx, cx
0x1800079f5  and     eax, 1FFF0000h
0x1800079fa  cmp     eax, 70000h
0x1800079ff  cmovnz  ebx, ecx
0x180007a02  test    ebx, ebx
0x180007a04  jz      short loc_180007A1A
0x180007a06  jmp     short loc_1800079B8
0x180007a08  test    r13, r13
0x180007a0b  jz      short loc_180007A11
0x180007a0d  mov     [r13+0], rdi
0x180007a11  test    r12, r12
0x180007a14  jz      short loc_180007A1A
0x180007a16  mov     [r12], rbp
0x180007a1a  mov     rbp, [rsp+48h+arg_10]
0x180007a1f  mov     eax, ebx
0x180007a21  mov     rbx, [rsp+48h+arg_8]
0x180007a26  mov     rsi, [rsp+48h+arg_18]
0x180007a2b  add     rsp, 20h
0x180007a2f  pop     r15
0x180007a31  pop     r14
0x180007a33  pop     r13
0x180007a35  pop     r12
0x180007a37  pop     rdi
0x180007a38  retn
```
