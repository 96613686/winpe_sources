# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x180018b40`
- end: `0x180018c0a`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `202`
- prototype: `void __fastcall(unsigned __int64 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018fb4`

## callees

- `0x180003304`
- `0x1800115e0`
- `0x180018b40`
- `0x18001941c`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rsi
  unsigned __int64 v2; // rcx
  char **v3; // r14
  char *v4; // rbx
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = v1[1];
    if ( v1[7] >> 3 <= v1[2] )
    {
      **(_QWORD **)(v2 + 8) = 0;
      v3 = *(char ***)v2;
      if ( *(_QWORD *)v2 )
      {
        do
        {
          v4 = *v3;
          std::wstring::~wstring(v3 + 6);
          std::wstring::~wstring(v3 + 2);
          operator delete(v3, 0x50u);
          v3 = (char **)v4;
        }
        while ( v4 );
      }
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8) = v1[1];
      v1[2] = 0;
      v5 = (void *)v1[3];
      v6 = (v1[4] - (unsigned __int64)v5 + 7) >> 3;
      if ( (unsigned __int64)v5 > v1[4] )
        v6 = 0;
      if ( v6 )
        memset64(v5, v1[1], v6);
    }
    else
    {
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Unchecked_erase(
        v1,
        *(_QWORD *)v2,
        v1[1]);
    }
  }
}

```

## disassembly

```asm
0x180018b40  push    rbx
0x180018b42  push    rsi
0x180018b43  push    rdi
0x180018b44  push    r14
0x180018b46  sub     rsp, 28h
0x180018b4a  mov     rsi, [rcx]
0x180018b4d  test    rsi, rsi
0x180018b50  jz      loc_180018C00
0x180018b56  cmp     qword ptr [rsi+10h], 0
0x180018b5b  jz      loc_180018C00
0x180018b61  mov     rax, [rsi+38h]
0x180018b65  mov     rcx, [rsi+8]
0x180018b69  shr     rax, 3
0x180018b6d  cmp     rax, [rsi+10h]
0x180018b71  jbe     short loc_180018B83
0x180018b73  mov     rdx, [rcx]
0x180018b76  mov     r8, rcx
0x180018b79  mov     rcx, rsi
0x180018b7c  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x180018b81  jmp     short loc_180018C00
0x180018b83  mov     rax, [rcx+8]
0x180018b87  mov     qword ptr [rax], 0
0x180018b8e  mov     r14, [rcx]
0x180018b91  test    r14, r14
0x180018b94  jz      short loc_180018BC0
0x180018b96  mov     rbx, [r14]
0x180018b99  lea     rcx, [r14+30h]
0x180018b9d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018ba2  lea     rcx, [r14+10h]
0x180018ba6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018bab  mov     edx, 50h ; 'P'; unsigned __int64
0x180018bb0  mov     rcx, r14; void *
0x180018bb3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018bb8  mov     r14, rbx
0x180018bbb  test    rbx, rbx
0x180018bbe  jnz     short loc_180018B96
0x180018bc0  mov     rax, [rsi+8]
0x180018bc4  xor     edx, edx
0x180018bc6  mov     [rax], rax
0x180018bc9  mov     rax, [rsi+8]
0x180018bcd  mov     [rax+8], rax
0x180018bd1  mov     qword ptr [rsi+10h], 0
0x180018bd9  mov     rdi, [rsi+18h]
0x180018bdd  mov     rcx, [rsi+20h]
0x180018be1  sub     rcx, rdi
0x180018be4  add     rcx, 7
0x180018be8  shr     rcx, 3
0x180018bec  cmp     rdi, [rsi+20h]
0x180018bf0  cmova   rcx, rdx
0x180018bf4  test    rcx, rcx
0x180018bf7  jz      short loc_180018C00
0x180018bf9  mov     rax, [rsi+8]
0x180018bfd  rep stosq
0x180018c00  add     rsp, 28h
0x180018c04  pop     r14
0x180018c06  pop     rdi
0x180018c07  pop     rsi
0x180018c08  pop     rbx
0x180018c09  retn
```
