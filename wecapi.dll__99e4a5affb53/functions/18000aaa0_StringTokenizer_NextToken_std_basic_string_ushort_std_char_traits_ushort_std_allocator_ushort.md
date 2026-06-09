# StringTokenizer::NextToken(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000aaa0`
- end: `0x18000ace4`
- name: `?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000aea4`

## callees

- `0x1800026c0`
- `0x180009ba0`
- `0x180009ff0`
- `0x18000a44c`
- `0x18000aaa0`
- `0x18000b480`
- `0x18000ba60`

## import_xrefs

- `msvcrt!iswspace` at `0x18000ab21`
- `msvcrt!iswspace` at `0x18000ab48`
- `msvcrt!iswspace` at `0x18000ab21`
- `msvcrt!iswspace` at `0x18000ab48`

## pseudocode

```c
__int64 __fastcall StringTokenizer::NextToken(__int64 *a1, __int64 a2)
{
  _QWORD *v4; // r12
  _QWORD *v5; // rdi
  __int64 v6; // r14
  __int64 first_of; // rax
  __int64 v8; // rcx
  _QWORD *v9; // r13
  char v10; // r15
  __int64 *v11; // rcx
  __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  _WORD *v14; // r10
  __int64 *v15; // rax
  __int16 v16; // di
  _WORD *v17; // rax
  _WORD *v18; // rcx
  __int64 result; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // rax
  unsigned __int64 v22; // r9
  __int64 v23; // rax
  _WORD *v24; // rdi
  __int64 v25; // rcx
  _WORD *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rdi
  void *Src[3]; // [rsp+28h] [rbp-28h] BYREF
  unsigned __int64 v30; // [rsp+40h] [rbp-10h]

  if ( a1[8] == -1 )
    return 2;
  v4 = a1 + 4;
  v5 = a1 + 3;
  do
  {
    v6 = a1[8];
    first_of = std::wstring::find_first_of(a1, v4, v6);
    v8 = first_of;
    if ( first_of == v6 && first_of != -1 )
    {
      if ( *v5 < 8u )
        v15 = a1;
      else
        v15 = (__int64 *)*a1;
      v16 = *((_WORD *)v15 + v8);
      if ( !*(_QWORD *)(a2 + 24) )
        std::wstring::_Copy((const void **)a2, 1u, *(_QWORD *)(a2 + 16));
      if ( *(_QWORD *)(a2 + 24) < 8u )
        v17 = (_WORD *)a2;
      else
        v17 = *(_WORD **)a2;
      *v17 = v16;
      if ( *(_QWORD *)(a2 + 24) < 8u )
        v18 = (_WORD *)a2;
      else
        v18 = *(_WORD **)a2;
      result = 0;
      *(_QWORD *)(a2 + 16) = 1;
      v18[1] = 0;
      ++a1[8];
      return result;
    }
    v9 = v5;
    if ( !*((_BYTE *)a1 + 72) )
      break;
    v10 = 0;
    v5 = a1 + 3;
    if ( (unsigned __int64)a1[3] < 8 )
      v11 = a1;
    else
      v11 = (__int64 *)*a1;
    if ( iswspace(*((_WORD *)v11 + v6)) )
    {
      v10 = 1;
      goto LABEL_11;
    }
    while ( 1 )
    {
      v12 = *v5 < 8u ? (__int64)a1 : *a1;
      if ( !iswspace(*(_WORD *)(v12 + 2 * a1[8])) )
        break;
LABEL_11:
      ++a1[8];
    }
  }
  while ( v10 );
  v13 = a1[8];
  if ( v4[3] < 8u )
    v14 = v4;
  else
    v14 = (_WORD *)*v4;
  v20 = a1[2];
  if ( v13 >= v20 )
    goto LABEL_48;
  v21 = *v9 < 8u ? (__int64)a1 : *a1;
  v22 = v21 + 2 * v20;
  v23 = *v9 < 8u ? (__int64)a1 : *a1;
  v24 = (_WORD *)(v23 + 2 * v13);
  if ( (unsigned __int64)v24 >= v22 )
    goto LABEL_48;
  if ( v4[2] )
  {
    while ( 1 )
    {
      v25 = v4[2];
      v26 = v14;
      while ( *v26 != *v24 )
      {
        ++v26;
        if ( !--v25 )
          goto LABEL_44;
      }
      if ( !v26 )
        break;
      if ( (unsigned __int64)++v24 >= v22 )
        goto LABEL_48;
    }
  }
LABEL_44:
  v27 = *v9 < 8u ? (__int64)a1 : *a1;
  v28 = ((__int64)v24 - v27) >> 1;
  if ( v28 == -1 )
  {
LABEL_48:
    a1[8] = -1;
    return 2;
  }
  a1[8] = std::wstring::find_first_of(a1, v4, v28);
  v30 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  std::wstring::assign(Src);
  std::wstring::operator=((void *)a2, Src);
  if ( v30 >= 8 )
    operator delete(Src[0]);
  return 1;
}

```

## disassembly

```asm
0x18000aaa0  mov     [rsp-38h+arg_10], rbx
0x18000aaa5  push    rbp
0x18000aaa6  push    rsi
0x18000aaa7  push    rdi
0x18000aaa8  push    r12
0x18000aaaa  push    r13
0x18000aaac  push    r14
0x18000aaae  push    r15
0x18000aab0  mov     rbp, rsp
0x18000aab3  sub     rsp, 50h
0x18000aab7  mov     rax, cs:__security_cookie
0x18000aabe  xor     rax, rsp
0x18000aac1  mov     [rbp+var_8], rax
0x18000aac5  cmp     qword ptr [rcx+40h], 0FFFFFFFFFFFFFFFFh
0x18000aaca  mov     rsi, rdx
0x18000aacd  mov     rbx, rcx
0x18000aad0  jz      loc_18000AC3E
0x18000aad6  lea     r12, [rcx+20h]
0x18000aada  lea     rdi, [rcx+18h]
0x18000aade  mov     r14, [rbx+40h]
0x18000aae2  mov     rdx, r12
0x18000aae5  mov     r8, r14
0x18000aae8  mov     rcx, rbx
0x18000aaeb  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find_first_of(std::wstring const &,unsigned __int64)
0x18000aaf0  mov     rcx, rax
0x18000aaf3  cmp     rax, r14
0x18000aaf6  jnz     short loc_18000AAFE
0x18000aaf8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000aafc  jnz     short loc_18000AB69
0x18000aafe  cmp     byte ptr [rbx+48h], 0
0x18000ab02  mov     r13, rdi
0x18000ab05  jz      short loc_18000AB57
0x18000ab07  xor     r15b, r15b
0x18000ab0a  lea     rdi, [rbx+18h]
0x18000ab0e  cmp     qword ptr [rdi], 8
0x18000ab12  jb      short loc_18000AB19
0x18000ab14  mov     rcx, [rbx]
0x18000ab17  jmp     short loc_18000AB1C
0x18000ab19  mov     rcx, rbx
0x18000ab1c  movzx   ecx, word ptr [rcx+r14*2]; C
0x18000ab21  call    cs:__imp_iswspace
0x18000ab27  test    eax, eax
0x18000ab29  jz      short loc_18000AB32
0x18000ab2b  mov     r15b, 1
0x18000ab2e  inc     qword ptr [rbx+40h]
0x18000ab32  cmp     qword ptr [rdi], 8
0x18000ab36  mov     rax, [rbx+40h]
0x18000ab3a  jb      short loc_18000AB41
0x18000ab3c  mov     rcx, [rbx]
0x18000ab3f  jmp     short loc_18000AB44
0x18000ab41  mov     rcx, rbx
0x18000ab44  movzx   ecx, word ptr [rcx+rax*2]; C
0x18000ab48  call    cs:__imp_iswspace
0x18000ab4e  test    eax, eax
0x18000ab50  jnz     short loc_18000AB2E
0x18000ab52  test    r15b, r15b
0x18000ab55  jnz     short loc_18000AADE
0x18000ab57  cmp     qword ptr [r12+18h], 8
0x18000ab5d  mov     rdx, [rbx+40h]
0x18000ab61  jb      short loc_18000ABC8
0x18000ab63  mov     r10, [r12]
0x18000ab67  jmp     short loc_18000ABCB
0x18000ab69  cmp     qword ptr [rdi], 8
0x18000ab6d  jb      short loc_18000AB74
0x18000ab6f  mov     rax, [rbx]
0x18000ab72  jmp     short loc_18000AB77
0x18000ab74  mov     rax, rbx
0x18000ab77  cmp     qword ptr [rsi+18h], 1
0x18000ab7c  movzx   edi, word ptr [rax+rcx*2]
0x18000ab80  jnb     short loc_18000AB93
0x18000ab82  mov     r8, [rsi+10h]
0x18000ab86  mov     edx, 1
0x18000ab8b  mov     rcx, rsi; Src
0x18000ab8e  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000ab93  cmp     qword ptr [rsi+18h], 8
0x18000ab98  jb      short loc_18000AB9F
0x18000ab9a  mov     rax, [rsi]
0x18000ab9d  jmp     short loc_18000ABA2
0x18000ab9f  mov     rax, rsi
0x18000aba2  mov     [rax], di
0x18000aba5  cmp     qword ptr [rsi+18h], 8
0x18000abaa  jb      short loc_18000ABB1
0x18000abac  mov     rcx, [rsi]
0x18000abaf  jmp     short loc_18000ABB4
0x18000abb1  mov     rcx, rsi
0x18000abb4  xor     eax, eax
0x18000abb6  mov     qword ptr [rsi+10h], 1
0x18000abbe  mov     [rcx+2], ax
0x18000abc2  inc     qword ptr [rbx+40h]
0x18000abc6  jmp     short loc_18000AC43
0x18000abc8  mov     r10, r12
0x18000abcb  mov     rcx, [rbx+10h]
0x18000abcf  cmp     rdx, rcx
0x18000abd2  jnb     short loc_18000AC36
0x18000abd4  cmp     qword ptr [r13+0], 8
0x18000abd9  mov     r8, [r12+10h]
0x18000abde  jb      short loc_18000ABE5
0x18000abe0  mov     rax, [rbx]
0x18000abe3  jmp     short loc_18000ABE8
0x18000abe5  mov     rax, rbx
0x18000abe8  lea     r9, [rax+rcx*2]
0x18000abec  jb      short loc_18000ABF3
0x18000abee  mov     rax, [rbx]
0x18000abf1  jmp     short loc_18000ABF6
0x18000abf3  mov     rax, rbx
0x18000abf6  lea     rdi, [rax+rdx*2]
0x18000abfa  cmp     rdi, r9
0x18000abfd  jnb     short loc_18000AC36
0x18000abff  test    r8, r8
0x18000ac02  jz      short loc_18000AC1C
0x18000ac04  movzx   edx, word ptr [rdi]
0x18000ac07  mov     rcx, r8
0x18000ac0a  mov     rax, r10
0x18000ac0d  cmp     [rax], dx
0x18000ac10  jz      short loc_18000AC28
0x18000ac12  add     rax, 2
0x18000ac16  sub     rcx, 1
0x18000ac1a  jnz     short loc_18000AC0D
0x18000ac1c  cmp     qword ptr [r13+0], 8
0x18000ac21  jb      short loc_18000AC67
0x18000ac23  mov     rax, [rbx]
0x18000ac26  jmp     short loc_18000AC6A
0x18000ac28  test    rax, rax
0x18000ac2b  jz      short loc_18000AC1C
0x18000ac2d  add     rdi, 2
0x18000ac31  cmp     rdi, r9
0x18000ac34  jb      short loc_18000AC04
0x18000ac36  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x18000ac3e  mov     eax, 2
0x18000ac43  mov     rcx, [rbp+var_8]
0x18000ac47  xor     rcx, rsp; StackCookie
0x18000ac4a  call    __security_check_cookie
0x18000ac4f  mov     rbx, [rsp+50h+arg_10]
0x18000ac57  add     rsp, 50h
0x18000ac5b  pop     r15
0x18000ac5d  pop     r14
0x18000ac5f  pop     r13
0x18000ac61  pop     r12
0x18000ac63  pop     rdi
0x18000ac64  pop     rsi
0x18000ac65  pop     rbp
0x18000ac66  retn
0x18000ac67  mov     rax, rbx
0x18000ac6a  sub     rdi, rax
0x18000ac6d  sar     rdi, 1
0x18000ac70  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000ac74  jz      short loc_18000AC36
0x18000ac76  mov     r8, rdi
0x18000ac79  mov     rdx, r12
0x18000ac7c  mov     rcx, rbx
0x18000ac7f  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find_first_of(std::wstring const &,unsigned __int64)
0x18000ac84  mov     [rbx+40h], rax
0x18000ac88  mov     r9, rax
0x18000ac8b  mov     [rbp+var_10], 7
0x18000ac93  mov     r8, rdi
0x18000ac96  mov     [rbp+var_18], 0
0x18000ac9e  mov     rdx, rbx
0x18000aca1  lea     rcx, [rbp+Src]; void *
0x18000aca5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000aca9  jnz     short loc_18000ACB0
0x18000acab  or      r9, rax
0x18000acae  jmp     short loc_18000ACB3
0x18000acb0  sub     r9, rdi
0x18000acb3  xor     eax, eax
0x18000acb5  mov     word ptr [rbp+Src], ax
0x18000acb9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000acbe  lea     rdx, [rbp+Src]; Src
0x18000acc2  mov     rcx, rsi; void *
0x18000acc5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000acca  cmp     [rbp+var_10], 8
0x18000accf  jb      short loc_18000ACDA
0x18000acd1  mov     rcx, [rbp+Src]; void *
0x18000acd5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000acda  mov     eax, 1
0x18000acdf  jmp     loc_18000AC43
```
