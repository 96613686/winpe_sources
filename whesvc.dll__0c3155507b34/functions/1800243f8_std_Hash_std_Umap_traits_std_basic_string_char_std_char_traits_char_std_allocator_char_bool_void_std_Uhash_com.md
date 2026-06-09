# std::_Hash<std::_Umap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool (*)(void),std::_Uhash_compare<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::hash<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::equal_to<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bool (*)(void)>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bool (*)(void)>,void *> *,std::_List_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bool (*)(void)>,void *> * const)

- ea: `0x1800243f8`
- end: `0x1800245c4`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `460`
- prototype: `char *__fastcall(_QWORD *, char *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ba78`

## callees

- `0x180003304`
- `0x180011578`
- `0x1800243f8`

## pseudocode

```c
char *__fastcall std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        char *a2,
        char *a3)
{
  char **v6; // rax
  char *v7; // rsi
  __int64 v8; // r12
  _QWORD *v9; // rcx
  char **v10; // r15
  unsigned __int64 v11; // r10
  unsigned __int64 v12; // rdx
  __int64 i; // r8
  __int64 v14; // rax
  __int64 v15; // r13
  char **v16; // rbx
  _QWORD *v17; // r8
  char **v18; // rax
  _QWORD *v19; // rcx
  unsigned __int64 v20; // r9
  unsigned __int64 v21; // rdx
  __int64 v22; // r14
  __int64 v23; // rax
  __int64 v24; // r14
  char **v25; // r13
  char **v26; // rbx
  char *v29; // [rsp+78h] [rbp+10h]
  char **v30; // [rsp+80h] [rbp+18h]
  char **v31; // [rsp+88h] [rbp+20h]

  if ( a2 != a3 )
  {
    v6 = (char **)a1[1];
    v7 = a2;
    v8 = a1[3];
    v9 = a2 + 16;
    v10 = (char **)*((_QWORD *)a2 + 1);
    v11 = *((_QWORD *)a2 + 4);
    v30 = v6;
    if ( *((_QWORD *)a2 + 5) > 0xFu )
      v9 = (_QWORD *)*v9;
    v12 = 0;
    for ( i = 0xCBF29CE484222325uLL; v12 < v11; i = 0x100000001B3LL * (v14 ^ i) )
      v14 = *((unsigned __int8 *)v9 + v12++);
    v15 = 2 * (i & a1[6]);
    v29 = *(char **)(v8 + 16 * (i & a1[6]));
    v31 = *(char ***)(v8 + 16 * (i & a1[6]) + 8);
    while ( 1 )
    {
      v16 = (char **)v7;
      v7 = *(char **)v7;
      std::string::~string(v16 + 2);
      operator delete(v16);
      v17 = a1;
      --a1[2];
      if ( v16 == v31 )
        break;
      if ( v7 == a3 )
      {
        if ( v29 == a2 )
          *(_QWORD *)(v8 + 8 * v15) = v7;
        goto LABEL_24;
      }
    }
    if ( v29 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v15) = v30;
      v18 = v30;
    }
    else
    {
      v18 = v10;
    }
    *(_QWORD *)(v8 + 8 * v15 + 8) = v18;
    while ( v7 != a3 )
    {
      v19 = v7 + 16;
      v20 = *((_QWORD *)v7 + 4);
      if ( *((_QWORD *)v7 + 5) > 0xFu )
        v19 = (_QWORD *)*v19;
      v21 = 0;
      v22 = 0xCBF29CE484222325uLL;
      if ( v20 )
      {
        do
        {
          v23 = *((unsigned __int8 *)v19 + v21++);
          v22 = 0x100000001B3LL * (v23 ^ v22);
        }
        while ( v21 < v20 );
        v17 = a1;
      }
      v24 = 2 * (v17[6] & v22);
      v25 = *(char ***)(v8 + 8 * v24 + 8);
      while ( 1 )
      {
        v26 = (char **)v7;
        v7 = *(char **)v7;
        std::string::~string(v26 + 2);
        operator delete(v26);
        v17 = a1;
        --a1[2];
        if ( v26 == v25 )
          break;
        if ( v7 == a3 )
        {
          *(_QWORD *)(v8 + 8 * v24) = v7;
          goto LABEL_24;
        }
      }
      *(_QWORD *)(v8 + 8 * v24) = v30;
      *(_QWORD *)(v8 + 8 * v24 + 8) = v30;
    }
LABEL_24:
    *v10 = v7;
    *((_QWORD *)v7 + 1) = v10;
  }
  return a3;
}

```

## disassembly

```asm
0x1800243f8  mov     [rsp+arg_0], rcx
0x1800243fd  push    rbx
0x1800243fe  push    rbp
0x1800243ff  push    rsi
0x180024400  push    rdi
0x180024401  push    r12
0x180024403  push    r13
0x180024405  push    r14
0x180024407  push    r15
0x180024409  sub     rsp, 28h
0x18002440d  mov     rbp, r8
0x180024410  mov     r14, rdx
0x180024413  mov     r9, rcx
0x180024416  cmp     rdx, r8
0x180024419  jz      loc_180024594
0x18002441f  mov     rax, [rcx+8]
0x180024423  mov     rsi, rdx
0x180024426  mov     r12, [rcx+18h]
0x18002442a  lea     rcx, [rdx+10h]
0x18002442e  cmp     qword ptr [rcx+18h], 0Fh
0x180024433  mov     r15, [rdx+8]
0x180024437  mov     r10, [rcx+10h]
0x18002443b  mov     [rsp+68h+arg_10], rax
0x180024443  jbe     short loc_180024448
0x180024445  mov     rcx, [rcx]
0x180024448  xor     edx, edx
0x18002444a  mov     r8, 0CBF29CE484222325h
0x180024454  mov     r11, 100000001B3h
0x18002445e  test    r10, r10
0x180024461  jz      short loc_180024476
0x180024463  movzx   eax, byte ptr [rcx+rdx]
0x180024467  inc     rdx
0x18002446a  xor     r8, rax
0x18002446d  imul    r8, r11
0x180024471  cmp     rdx, r10
0x180024474  jb      short loc_180024463
0x180024476  mov     r13, [r9+30h]
0x18002447a  and     r13, r8
0x18002447d  add     r13, r13
0x180024480  mov     rax, [r12+r13*8]
0x180024484  mov     [rsp+68h+arg_8], rax
0x180024489  mov     rax, [r12+r13*8+8]
0x18002448e  mov     [rsp+68h+arg_18], rax
0x180024496  mov     rbx, rsi
0x180024499  mov     rdi, rsi
0x18002449c  mov     rsi, [rsi]
0x18002449f  lea     rcx, [rbx+10h]
0x1800244a3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800244a8  mov     edx, 38h ; '8'; unsigned __int64
0x1800244ad  mov     rcx, rbx; void *
0x1800244b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800244b5  mov     r8, [rsp+68h+arg_0]
0x1800244ba  dec     qword ptr [r8+10h]
0x1800244be  cmp     rbx, [rsp+68h+arg_18]
0x1800244c6  jz      short loc_1800244E1
0x1800244c8  cmp     rsi, rbp
0x1800244cb  jnz     short loc_180024496
0x1800244cd  cmp     [rsp+68h+arg_8], r14
0x1800244d2  jnz     loc_18002458D
0x1800244d8  mov     [r12+r13*8], rsi
0x1800244dc  jmp     loc_18002458D
0x1800244e1  cmp     [rsp+68h+arg_8], r14
0x1800244e6  jnz     short loc_1800244F9
0x1800244e8  mov     rdx, [rsp+68h+arg_10]
0x1800244f0  mov     [r12+r13*8], rdx
0x1800244f4  mov     rax, rdx
0x1800244f7  jmp     short loc_1800244FC
0x1800244f9  mov     rax, r15
0x1800244fc  mov     [r12+r13*8+8], rax
0x180024501  jmp     loc_1800245B9
0x180024506  lea     rcx, [rsi+10h]
0x18002450a  cmp     qword ptr [rcx+18h], 0Fh
0x18002450f  mov     r9, [rcx+10h]
0x180024513  jbe     short loc_180024518
0x180024515  mov     rcx, [rcx]
0x180024518  xor     edx, edx
0x18002451a  mov     r14, 0CBF29CE484222325h
0x180024524  test    r9, r9
0x180024527  jz      short loc_18002454B
0x180024529  mov     r8, 100000001B3h
0x180024533  movzx   eax, byte ptr [rcx+rdx]
0x180024537  inc     rdx
0x18002453a  xor     r14, rax
0x18002453d  imul    r14, r8
0x180024541  cmp     rdx, r9
0x180024544  jb      short loc_180024533
0x180024546  mov     r8, [rsp+68h+arg_0]
0x18002454b  and     r14, [r8+30h]
0x18002454f  add     r14, r14
0x180024552  mov     r13, [r12+r14*8+8]
0x180024557  mov     rbx, rsi
0x18002455a  mov     rdi, rsi
0x18002455d  mov     rsi, [rsi]
0x180024560  lea     rcx, [rbx+10h]
0x180024564  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180024569  mov     edx, 38h ; '8'; unsigned __int64
0x18002456e  mov     rcx, rbx; void *
0x180024571  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024576  mov     r8, [rsp+68h+arg_0]
0x18002457b  dec     qword ptr [r8+10h]
0x18002457f  cmp     rbx, r13
0x180024582  jz      short loc_1800245A8
0x180024584  cmp     rsi, rbp
0x180024587  jnz     short loc_180024557
0x180024589  mov     [r12+r14*8], rsi
0x18002458d  mov     [r15], rsi
0x180024590  mov     [rsi+8], r15
0x180024594  mov     rax, rbp
0x180024597  add     rsp, 28h
0x18002459b  pop     r15
0x18002459d  pop     r14
0x18002459f  pop     r13
0x1800245a1  pop     r12
0x1800245a3  pop     rdi
0x1800245a4  pop     rsi
0x1800245a5  pop     rbp
0x1800245a6  pop     rbx
0x1800245a7  retn
0x1800245a8  mov     rax, [rsp+68h+arg_10]
0x1800245b0  mov     [r12+r14*8], rax
0x1800245b4  mov     [r12+r14*8+8], rax
0x1800245b9  cmp     rsi, rbp
0x1800245bc  jnz     loc_180024506
0x1800245c2  jmp     short loc_18002458D
```
