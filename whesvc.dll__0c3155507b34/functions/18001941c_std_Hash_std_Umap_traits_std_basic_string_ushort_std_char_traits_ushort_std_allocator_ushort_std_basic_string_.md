# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> * const)

- ea: `0x18001941c`
- end: `0x18001963c`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `544`
- prototype: `char *__fastcall(_QWORD *, char *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018b40`

## callees

- `0x180003304`
- `0x1800115e0`
- `0x18001941c`

## pseudocode

```c
char *__fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        char *a2,
        char *a3)
{
  char **v6; // rax
  char *v7; // r14
  __int64 v8; // r12
  _QWORD *v9; // rcx
  char **v10; // r15
  __int64 v11; // r10
  unsigned __int64 v12; // r8
  __int64 v13; // rdx
  unsigned __int64 v14; // r10
  __int64 v15; // rax
  char **v16; // rdi
  _QWORD *v17; // r9
  char **v18; // rcx
  __int64 v19; // r13
  _QWORD *v20; // rcx
  unsigned __int64 v21; // r8
  __int64 v22; // rdx
  unsigned __int64 v23; // r10
  __int64 v24; // rax
  __int64 v25; // r12
  char **v26; // rdi
  char **v28; // [rsp+20h] [rbp-58h]
  __int64 v30; // [rsp+88h] [rbp+10h]
  char **v31; // [rsp+88h] [rbp+10h]
  char *v32; // [rsp+90h] [rbp+18h]
  char **v33; // [rsp+98h] [rbp+20h]

  if ( a2 != a3 )
  {
    v6 = (char **)a1[1];
    v7 = a2;
    v8 = a1[3];
    v9 = a2 + 16;
    v10 = (char **)*((_QWORD *)a2 + 1);
    v11 = *((_QWORD *)a2 + 4);
    v33 = v6;
    if ( *((_QWORD *)a2 + 5) > 7u )
      v9 = (_QWORD *)*v9;
    v12 = 0;
    v13 = 0xCBF29CE484222325uLL;
    v14 = 2 * v11;
    if ( v14 )
    {
      do
      {
        v15 = *((unsigned __int8 *)v9 + v12++);
        v13 = 0x100000001B3LL * (v15 ^ v13);
      }
      while ( v12 < v14 );
    }
    v30 = 16 * (v13 & a1[6]);
    v28 = *(char ***)(v30 + v8 + 8);
    v32 = *(char **)(v30 + v8);
    while ( 1 )
    {
      v16 = (char **)v7;
      v7 = *(char **)v7;
      std::wstring::~wstring(v16 + 6);
      std::wstring::~wstring(v16 + 2);
      operator delete(v16);
      v17 = a1;
      --a1[2];
      if ( v16 == v28 )
        break;
      if ( v7 == a3 )
      {
        if ( v32 == a2 )
          *(_QWORD *)(v30 + v8) = v7;
        goto LABEL_25;
      }
    }
    if ( v32 == a2 )
    {
      *(_QWORD *)(v30 + v8) = v33;
      v18 = v33;
    }
    else
    {
      v18 = v10;
    }
    *(_QWORD *)(v30 + v8 + 8) = v18;
    if ( v7 != a3 )
    {
      v19 = v8;
      do
      {
        v20 = v7 + 16;
        if ( *((_QWORD *)v7 + 5) > 7u )
          v20 = (_QWORD *)*v20;
        v21 = 0;
        v22 = 0xCBF29CE484222325uLL;
        v23 = 2LL * *((_QWORD *)v7 + 4);
        if ( v23 )
        {
          do
          {
            v24 = *((unsigned __int8 *)v20 + v21++);
            v22 = 0x100000001B3LL * (v24 ^ v22);
          }
          while ( v21 < v23 );
          v17 = a1;
        }
        v25 = 2 * (v22 & v17[6]);
        v31 = *(char ***)(v19 + 16 * (v22 & v17[6]) + 8);
        while ( 1 )
        {
          v26 = (char **)v7;
          v7 = *(char **)v7;
          std::wstring::~wstring(v26 + 6);
          std::wstring::~wstring(v26 + 2);
          operator delete(v26);
          v17 = a1;
          --a1[2];
          if ( v26 == v31 )
            break;
          if ( v7 == a3 )
          {
            *(_QWORD *)(v19 + 8 * v25) = v7;
            goto LABEL_25;
          }
        }
        *(_QWORD *)(v19 + 8 * v25) = v33;
        *(_QWORD *)(v19 + 8 * v25 + 8) = v33;
      }
      while ( v7 != a3 );
    }
LABEL_25:
    *v10 = v7;
    *((_QWORD *)v7 + 1) = v10;
  }
  return a3;
}

```

## disassembly

```asm
0x18001941c  mov     [rsp+arg_0], rcx
0x180019421  push    rbx
0x180019422  push    rbp
0x180019423  push    rsi
0x180019424  push    rdi
0x180019425  push    r12
0x180019427  push    r13
0x180019429  push    r14
0x18001942b  push    r15
0x18001942d  sub     rsp, 38h
0x180019431  mov     rbp, r8
0x180019434  mov     r13, rdx
0x180019437  mov     r9, rcx
0x18001943a  cmp     rdx, r8
0x18001943d  jz      loc_18001960B
0x180019443  mov     rax, [rcx+8]
0x180019447  mov     r14, rdx
0x18001944a  mov     r12, [rcx+18h]
0x18001944e  lea     rcx, [rdx+10h]
0x180019452  cmp     qword ptr [rcx+18h], 7
0x180019457  mov     r15, [rdx+8]
0x18001945b  mov     r10, [rcx+10h]
0x18001945f  mov     [rsp+78h+arg_18], rax
0x180019467  jbe     short loc_18001946C
0x180019469  mov     rcx, [rcx]
0x18001946c  xor     r8d, r8d
0x18001946f  mov     rdx, 0CBF29CE484222325h
0x180019479  mov     r11, 100000001B3h
0x180019483  add     r10, r10
0x180019486  jz      short loc_18001949C
0x180019488  movzx   eax, byte ptr [rcx+r8]
0x18001948d  inc     r8
0x180019490  xor     rdx, rax
0x180019493  imul    rdx, r11
0x180019497  cmp     r8, r10
0x18001949a  jb      short loc_180019488
0x18001949c  mov     rax, [r9+30h]
0x1800194a0  and     rax, rdx
0x1800194a3  shl     rax, 4
0x1800194a7  mov     [rsp+78h+arg_8], rax
0x1800194af  mov     rcx, [rax+r12]
0x1800194b3  mov     rax, [rax+r12+8]
0x1800194b8  mov     [rsp+78h+var_58], rax
0x1800194bd  mov     [rsp+78h+arg_10], rcx
0x1800194c5  mov     rdi, r14
0x1800194c8  mov     rsi, r14
0x1800194cb  mov     r14, [r14]
0x1800194ce  lea     rcx, [rdi+30h]
0x1800194d2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800194d7  lea     rcx, [rdi+10h]
0x1800194db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800194e0  mov     edx, 50h ; 'P'; unsigned __int64
0x1800194e5  mov     rcx, rdi; void *
0x1800194e8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800194ed  mov     r9, [rsp+78h+arg_0]
0x1800194f5  dec     qword ptr [r9+10h]
0x1800194f9  cmp     rdi, [rsp+78h+var_58]
0x1800194fe  jz      short loc_180019524
0x180019500  cmp     r14, rbp
0x180019503  jnz     short loc_1800194C5
0x180019505  cmp     [rsp+78h+arg_10], r13
0x18001950d  jnz     loc_180019604
0x180019513  mov     rax, [rsp+78h+arg_8]
0x18001951b  mov     [rax+r12], r14
0x18001951f  jmp     loc_180019604
0x180019524  mov     rax, [rsp+78h+arg_8]
0x18001952c  cmp     [rsp+78h+arg_10], r13
0x180019534  jnz     short loc_180019547
0x180019536  mov     rdx, [rsp+78h+arg_18]
0x18001953e  mov     [rax+r12], rdx
0x180019542  mov     rcx, rdx
0x180019545  jmp     short loc_18001954A
0x180019547  mov     rcx, r15
0x18001954a  mov     [rax+r12+8], rcx
0x18001954f  cmp     r14, rbp
0x180019552  jz      loc_180019604
0x180019558  mov     r13, r12
0x18001955b  lea     rcx, [r14+10h]
0x18001955f  cmp     qword ptr [rcx+18h], 7
0x180019564  mov     r10, [rcx+10h]
0x180019568  jbe     short loc_18001956D
0x18001956a  mov     rcx, [rcx]
0x18001956d  xor     r8d, r8d
0x180019570  mov     rdx, 0CBF29CE484222325h
0x18001957a  add     r10, r10
0x18001957d  jz      short loc_1800195A5
0x18001957f  mov     r9, 100000001B3h
0x180019589  movzx   eax, byte ptr [rcx+r8]
0x18001958e  inc     r8
0x180019591  xor     rdx, rax
0x180019594  imul    rdx, r9
0x180019598  cmp     r8, r10
0x18001959b  jb      short loc_180019589
0x18001959d  mov     r9, [rsp+78h+arg_0]
0x1800195a5  mov     r12, [r9+30h]
0x1800195a9  and     r12, rdx
0x1800195ac  add     r12, r12
0x1800195af  mov     rax, [r13+r12*8+8]
0x1800195b4  mov     [rsp+78h+arg_8], rax
0x1800195bc  mov     rdi, r14
0x1800195bf  mov     rsi, r14
0x1800195c2  mov     r14, [r14]
0x1800195c5  lea     rcx, [rdi+30h]
0x1800195c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800195ce  lea     rcx, [rdi+10h]
0x1800195d2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800195d7  mov     edx, 50h ; 'P'; unsigned __int64
0x1800195dc  mov     rcx, rdi; void *
0x1800195df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800195e4  mov     r9, [rsp+78h+arg_0]
0x1800195ec  dec     qword ptr [r9+10h]
0x1800195f0  cmp     rdi, [rsp+78h+arg_8]
0x1800195f8  jz      short loc_18001961F
0x1800195fa  cmp     r14, rbp
0x1800195fd  jnz     short loc_1800195BC
0x1800195ff  mov     [r13+r12*8+0], r14
0x180019604  mov     [r15], r14
0x180019607  mov     [r14+8], r15
0x18001960b  mov     rax, rbp
0x18001960e  add     rsp, 38h
0x180019612  pop     r15
0x180019614  pop     r14
0x180019616  pop     r13
0x180019618  pop     r12
0x18001961a  pop     rdi
0x18001961b  pop     rsi
0x18001961c  pop     rbp
0x18001961d  pop     rbx
0x18001961e  retn
0x18001961f  mov     rax, [rsp+78h+arg_18]
0x180019627  mov     [r13+r12*8+0], rax
0x18001962c  mov     [r13+r12*8+8], rax
0x180019631  cmp     r14, rbp
0x180019634  jnz     loc_18001955B
0x18001963a  jmp     short loc_180019604
```
