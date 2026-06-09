# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x1800068cc`
- end: `0x180006b5c`
- name: `?replace@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_K0PEBG0@Z`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180004d28`

## callees

- `0x180001680`
- `0x180006604`
- `0x1800066a8`
- `0x1800068cc`
- `0x180012172`
- `0x18001217e`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::replace(
        char **a1,
        __int64 a2,
        unsigned __int64 a3,
        __int16 *a4,
        unsigned __int64 a5)
{
  char *v5; // r13
  unsigned __int64 v8; // r8
  unsigned __int64 v10; // r12
  char v11; // r15
  char *v13; // r10
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  char *v16; // r11
  _WORD *v17; // rdi
  unsigned __int64 v18; // rdx
  _WORD *v19; // rcx
  char v20; // al
  __int16 v21; // ax
  __int64 v22; // r12
  char *v23; // rdi
  void *v24; // r14
  void *v25[2]; // [rsp+20h] [rbp-30h] BYREF
  _WORD *v26; // [rsp+30h] [rbp-20h] BYREF
  _WORD *v27; // [rsp+38h] [rbp-18h]
  _WORD Block[8]; // [rsp+40h] [rbp-10h] BYREF
  char *v29; // [rsp+90h] [rbp+40h]
  char *Src; // [rsp+98h] [rbp+48h]

  v5 = *a1;
  v8 = (unsigned __int64)a1[1];
  if ( (__int64)(v8 - (_QWORD)*a1) >> 1 < a3 )
    a3 = (a1[1] - *a1) >> 1;
  v10 = v8 + 2 * (a5 - a3);
  if ( v10 < (unsigned __int64)v5 )
    return 0;
  v11 = 1;
  v13 = &v5[2 * a3];
  Src = v13;
  if ( v5 == (char *)(a1 + 2) )
    v14 = (unsigned __int64)a1 + 30;
  else
    v14 = (unsigned __int64)a1[2];
  if ( v10 <= v14 )
  {
    v15 = 2 * a5;
    v16 = (char *)&a4[a5];
    v29 = v16;
    if ( v16 <= v5 || v8 < (unsigned __int64)a4 )
    {
      memmove_0(&v5[2 * a5], &v5[2 * a3], 2 * ((__int64)(v8 - (_QWORD)v13) >> 1) + 2);
      memcpy_0(v5, a4, 2 * a5);
      goto LABEL_29;
    }
    if ( a5 <= a3 )
    {
      memmove_0(v5, a4, 2 * a5);
      memmove_0(&v5[2 * a5], Src, 2 * ((a1[1] - Src) >> 1) + 2);
LABEL_29:
      a1[1] = (char *)v10;
      return v11;
    }
    v17 = Block;
    v26 = Block;
    v18 = v15 >> 1;
    v19 = Block;
    v27 = Block;
    Block[0] = 0;
    if ( (unsigned __int64)(v15 >> 1) >= 8 )
    {
      if ( v18 <= 0xF )
      {
        v18 = 15;
      }
      else if ( v18 > 0x3FFFFFFFFFFFFFF7LL )
      {
LABEL_20:
        v11 = 0;
LABEL_26:
        if ( v17 != Block )
          operator delete(v17);
        return v11;
      }
      v20 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowTo(
              &v26,
              v18);
      v17 = v26;
      if ( !v20 )
        goto LABEL_20;
      v19 = v27;
      v13 = Src;
      v16 = v29;
    }
    if ( a4 != (__int16 *)v16 )
    {
      do
      {
        v21 = *a4++;
        *v19 = v21;
        v19 = ++v27;
      }
      while ( a4 != (__int16 *)v16 );
      v17 = v26;
    }
    memmove_0(&v5[2 * a5], v13, 2 * ((a1[1] - v13) >> 1) + 2);
    memcpy_0(v5, v17, 2 * a5);
    a1[1] = (char *)v10;
    goto LABEL_26;
  }
  v22 = (__int64)(v10 - (_QWORD)v5) >> 1;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowAlloc(
    a1,
    v25,
    v22);
  v23 = (char *)v25[0];
  if ( !v25[0] )
    return 0;
  memcpy_0(v25[0], a4, 2 * a5);
  memcpy_0(&v23[2 * a5], Src, 2 * ((a1[1] - Src) >> 1) + 2);
  v24 = v25[1];
  if ( *a1 != (char *)(a1 + 2) )
    operator delete(*a1);
  *a1 = v23;
  a1[1] = &v23[2 * v22];
  a1[2] = &v23[2 * ((__int64)v24 - 1)];
  return v11;
}

```

## disassembly

```asm
0x1800068cc  mov     [rsp-38h+arg_18], rbx
0x1800068d1  mov     [rsp-38h+Src], rdx
0x1800068d6  push    rbp
0x1800068d7  push    rsi
0x1800068d8  push    rdi
0x1800068d9  push    r12
0x1800068db  push    r13
0x1800068dd  push    r14
0x1800068df  push    r15
0x1800068e1  mov     rbp, rsp
0x1800068e4  sub     rsp, 50h
0x1800068e8  mov     r13, [rcx]
0x1800068eb  mov     r14, r9
0x1800068ee  mov     rbx, [rbp+arg_20]
0x1800068f2  mov     r9, r8
0x1800068f5  mov     r8, [rcx+8]
0x1800068f9  mov     rsi, rcx
0x1800068fc  mov     rax, r8
0x1800068ff  sub     rax, r13
0x180006902  sar     rax, 1
0x180006905  cmp     rax, r9
0x180006908  cmovb   r9, rax
0x18000690c  mov     rax, rbx
0x18000690f  sub     rax, r9
0x180006912  lea     r12, [r8+rax*2]
0x180006916  cmp     r12, r13
0x180006919  jnb     short loc_18000693B
0x18000691b  xor     ebx, ebx
0x18000691d  mov     r15b, bl
0x180006920  mov     rbx, [rsp+50h+arg_18]
0x180006928  mov     al, r15b
0x18000692b  add     rsp, 50h
0x18000692f  pop     r15
0x180006931  pop     r14
0x180006933  pop     r13
0x180006935  pop     r12
0x180006937  pop     rdi
0x180006938  pop     rsi
0x180006939  pop     rbp
0x18000693a  retn
0x18000693b  lea     r10, ds:0[r9*2]
0x180006943  mov     r15b, 1
0x180006946  add     r10, r13
0x180006949  lea     rax, [rcx+10h]
0x18000694d  mov     [rbp+Src], r10
0x180006951  cmp     r13, rax
0x180006954  jnz     short loc_18000695C
0x180006956  lea     rax, [rcx+1Eh]
0x18000695a  jmp     short loc_18000695F
0x18000695c  mov     rax, [rax]
0x18000695f  cmp     r12, rax
0x180006962  ja      loc_180006AD0
0x180006968  lea     rax, [rbx+rbx]
0x18000696c  lea     r11, [rax+r14]
0x180006970  mov     [rbp+arg_0], r11
0x180006974  lea     rdi, [rax+r13]
0x180006978  mov     [rbp+arg_10], rdi
0x18000697c  cmp     r11, r13
0x18000697f  jbe     loc_180006A9F
0x180006985  cmp     r8, r14
0x180006988  jb      loc_180006A9F
0x18000698e  cmp     rbx, r9
0x180006991  ja      short loc_1800069C4
0x180006993  mov     r8, rax; Size
0x180006996  mov     rdx, r14; Src
0x180006999  mov     rcx, r13; void *
0x18000699c  call    memmove_0
0x1800069a1  mov     r8, [rsi+8]
0x1800069a5  mov     rcx, rdi; void *
0x1800069a8  mov     rdx, [rbp+Src]; Src
0x1800069ac  sub     r8, rdx
0x1800069af  sar     r8, 1
0x1800069b2  lea     r8, ds:2[r8*2]; Size
0x1800069ba  call    memmove_0
0x1800069bf  jmp     loc_180006AC7
0x1800069c4  xor     ebx, ebx
0x1800069c6  lea     rdi, [rbp+Block]
0x1800069ca  mov     rdx, rax
0x1800069cd  mov     [rbp+var_20], rdi
0x1800069d1  sar     rdx, 1
0x1800069d4  lea     rcx, [rbp+Block]
0x1800069d8  mov     [rbp+var_18], rcx
0x1800069dc  mov     [rbp+Block], bx
0x1800069e0  cmp     rdx, 8
0x1800069e4  jb      short loc_180006A24
0x1800069e6  cmp     rdx, 0Fh
0x1800069ea  jbe     short loc_1800069FD
0x1800069ec  mov     rax, 3FFFFFFFFFFFFFF7h
0x1800069f6  cmp     rdx, rax
0x1800069f9  ja      short loc_180006A13
0x1800069fb  jmp     short loc_180006A02
0x1800069fd  mov     edx, 0Fh
0x180006a02  lea     rcx, [rbp+var_20]
0x180006a06  call    ?_GrowTo@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowTo(unsigned __int64)
0x180006a0b  mov     rdi, [rbp+var_20]
0x180006a0f  test    al, al
0x180006a11  jnz     short loc_180006A18
0x180006a13  mov     r15b, bl
0x180006a16  jmp     short loc_180006A7E
0x180006a18  mov     rcx, [rbp+var_18]
0x180006a1c  mov     r10, [rbp+Src]
0x180006a20  mov     r11, [rbp+arg_0]
0x180006a24  cmp     r14, r11
0x180006a27  jz      short loc_180006A49
0x180006a29  movzx   eax, word ptr [r14]
0x180006a2d  add     r14, 2
0x180006a31  mov     [rcx], ax
0x180006a34  mov     rcx, [rbp+var_18]
0x180006a38  add     rcx, 2
0x180006a3c  mov     [rbp+var_18], rcx
0x180006a40  cmp     r14, r11
0x180006a43  jnz     short loc_180006A29
0x180006a45  mov     rdi, [rbp+var_20]
0x180006a49  mov     r8, [rsi+8]
0x180006a4d  mov     rdx, r10; Src
0x180006a50  mov     rcx, [rbp+arg_10]; void *
0x180006a54  sub     r8, r10
0x180006a57  sar     r8, 1
0x180006a5a  lea     r8, ds:2[r8*2]; Size
0x180006a62  call    memmove_0
0x180006a67  mov     rbx, [rbp+arg_20]
0x180006a6b  mov     rdx, rdi; Src
0x180006a6e  mov     rcx, r13; void *
0x180006a71  lea     r8, [rbx+rbx]; Size
0x180006a75  call    memcpy_0
0x180006a7a  mov     [rsi+8], r12
0x180006a7e  lea     rax, [rbp+Block]
0x180006a82  cmp     rdi, rax
0x180006a85  jz      loc_180006920
0x180006a8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180006a92  mov     rcx, rdi; Block
0x180006a95  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006a9a  jmp     loc_180006920
0x180006a9f  sub     r8, r10
0x180006aa2  mov     rdx, r10; Src
0x180006aa5  sar     r8, 1
0x180006aa8  mov     rcx, rdi; void *
0x180006aab  lea     r8, ds:2[r8*2]; Size
0x180006ab3  call    memmove_0
0x180006ab8  lea     r8, [rbx+rbx]; Size
0x180006abc  mov     rdx, r14; Src
0x180006abf  mov     rcx, r13; void *
0x180006ac2  call    memcpy_0
0x180006ac7  mov     [rsi+8], r12
0x180006acb  jmp     loc_180006920
0x180006ad0  sub     r12, r13
0x180006ad3  lea     rdx, [rbp+var_30]
0x180006ad7  sar     r12, 1
0x180006ada  mov     r8, r12
0x180006add  call    ?_GrowAlloc@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA?AU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowAlloc(unsigned __int64)
0x180006ae2  mov     rdi, [rbp+var_30]
0x180006ae6  xor     ebx, ebx
0x180006ae8  test    rdi, rdi
0x180006aeb  jz      loc_18000691D
0x180006af1  mov     rbx, [rbp+arg_20]
0x180006af5  mov     rdx, r14; Src
0x180006af8  add     rbx, rbx
0x180006afb  mov     rcx, rdi; void *
0x180006afe  mov     r8, rbx; Size
0x180006b01  call    memcpy_0
0x180006b06  mov     r8, [rsi+8]
0x180006b0a  lea     rcx, [rbx+rdi]; void *
0x180006b0e  mov     rdx, [rbp+Src]; Src
0x180006b12  sub     r8, rdx
0x180006b15  sar     r8, 1
0x180006b18  lea     r8, ds:2[r8*2]; Size
0x180006b20  call    memcpy_0
0x180006b25  mov     r14, [rbp+var_28]
0x180006b29  lea     rbx, [rsi+10h]
0x180006b2d  cmp     [rsi], rbx
0x180006b30  jz      short loc_180006B41
0x180006b32  mov     rcx, [rsi]; Block
0x180006b35  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180006b3c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006b41  lea     rax, [rdi+r12*2]
0x180006b45  mov     [rsi], rdi
0x180006b48  mov     [rsi+8], rax
0x180006b4c  lea     rax, [r14-1]
0x180006b50  lea     rax, [rdi+rax*2]
0x180006b54  mov     [rbx], rax
0x180006b57  jmp     loc_180006920
```
