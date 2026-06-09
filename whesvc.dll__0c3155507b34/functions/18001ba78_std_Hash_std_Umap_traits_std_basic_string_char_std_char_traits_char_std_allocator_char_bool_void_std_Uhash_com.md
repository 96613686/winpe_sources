# std::_Hash<std::_Umap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool (*)(void),std::_Uhash_compare<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::hash<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::equal_to<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bool (*)(void)>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x18001ba78`
- end: `0x18001bb44`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `204`
- prototype: `void __fastcall(unsigned __int64 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023f78`

## callees

- `0x180003304`
- `0x180011578`
- `0x18001ba78`
- `0x1800243f8`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  unsigned __int64 v2; // rcx
  char **v3; // rsi
  char *v4; // rdi
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
          std::string::~string(v3 + 2);
          operator delete(v3, 0x38u);
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
      std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Unchecked_erase(
        v1,
        *(_QWORD *)v2,
        v1[1]);
    }
  }
}

```

## disassembly

```asm
0x18001ba78  mov     [rsp+arg_0], rbx
0x18001ba7d  mov     [rsp+arg_8], rsi
0x18001ba82  push    rdi
0x18001ba83  sub     rsp, 20h
0x18001ba87  mov     rbx, [rcx]
0x18001ba8a  test    rbx, rbx
0x18001ba8d  jz      loc_18001BB34
0x18001ba93  cmp     qword ptr [rbx+10h], 0
0x18001ba98  jz      loc_18001BB34
0x18001ba9e  mov     rax, [rbx+38h]
0x18001baa2  mov     rcx, [rbx+8]
0x18001baa6  shr     rax, 3
0x18001baaa  cmp     rax, [rbx+10h]
0x18001baae  jbe     short loc_18001BAC0
0x18001bab0  mov     rdx, [rcx]
0x18001bab3  mov     r8, rcx
0x18001bab6  mov     rcx, rbx
0x18001bab9  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::string const,bool (*)(void)>,void *> *,std::_List_node<std::pair<std::string const,bool (*)(void)>,void *> * const)
0x18001babe  jmp     short loc_18001BB34
0x18001bac0  mov     rax, [rcx+8]
0x18001bac4  mov     qword ptr [rax], 0
0x18001bacb  mov     rsi, [rcx]
0x18001bace  test    rsi, rsi
0x18001bad1  jz      short loc_18001BAF4
0x18001bad3  mov     rdi, [rsi]
0x18001bad6  lea     rcx, [rsi+10h]
0x18001bada  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001badf  mov     edx, 38h ; '8'; unsigned __int64
0x18001bae4  mov     rcx, rsi; void *
0x18001bae7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001baec  mov     rsi, rdi
0x18001baef  test    rdi, rdi
0x18001baf2  jnz     short loc_18001BAD3
0x18001baf4  mov     rax, [rbx+8]
0x18001baf8  xor     edx, edx
0x18001bafa  mov     [rax], rax
0x18001bafd  mov     rax, [rbx+8]
0x18001bb01  mov     [rax+8], rax
0x18001bb05  mov     qword ptr [rbx+10h], 0
0x18001bb0d  mov     rdi, [rbx+18h]
0x18001bb11  mov     rcx, [rbx+20h]
0x18001bb15  sub     rcx, rdi
0x18001bb18  add     rcx, 7
0x18001bb1c  shr     rcx, 3
0x18001bb20  cmp     rdi, [rbx+20h]
0x18001bb24  cmova   rcx, rdx
0x18001bb28  test    rcx, rcx
0x18001bb2b  jz      short loc_18001BB34
0x18001bb2d  mov     rax, [rbx+8]
0x18001bb31  rep stosq
0x18001bb34  mov     rbx, [rsp+28h+arg_0]
0x18001bb39  mov     rsi, [rsp+28h+arg_8]
0x18001bb3e  add     rsp, 20h
0x18001bb42  pop     rdi
0x18001bb43  retn
```
