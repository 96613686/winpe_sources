# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>>,0>>::clear(void)

- ea: `0x180019890`
- end: `0x180019974`
- name: `?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ`
- size: `228`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000ba38`

## callees

- `0x180003304`
- `0x1800115e0`
- `0x180019644`
- `0x180019890`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800198f5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800198f5`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::clear(
        _QWORD *a1)
{
  char ***v2; // rcx
  char **v3; // rbx
  HMODULE *v4; // rsi
  char *v5; // r14
  void *v6; // r8
  unsigned __int64 v7; // rcx

  if ( a1[2] )
  {
    v2 = (char ***)a1[1];
    if ( a1[7] >> 3 <= a1[2] )
    {
      *v2[1] = 0;
      v3 = *v2;
      if ( *v2 )
      {
        do
        {
          v4 = (HMODULE *)v3[6];
          v5 = *v3;
          if ( v4 )
          {
            if ( *v4 )
              FreeLibrary(*v4);
            operator delete(v4);
          }
          std::wstring::~wstring(v3 + 2);
          operator delete(v3);
          v3 = (char **)v5;
        }
        while ( v5 );
      }
      *(_QWORD *)a1[1] = a1[1];
      *(_QWORD *)(a1[1] + 8LL) = a1[1];
      a1[2] = 0;
      v6 = (void *)a1[3];
      v7 = (unsigned __int64)(a1[4] - (_QWORD)v6 + 7LL) >> 3;
      if ( (unsigned __int64)v6 > a1[4] )
        v7 = 0;
      if ( v7 )
        memset64(v6, a1[1], v7);
    }
    else
    {
      std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Unchecked_erase(
        a1,
        *v2,
        v2);
    }
  }
}

```

## disassembly

```asm
0x180019890  push    rbx
0x180019892  push    rbp
0x180019893  push    rsi
0x180019894  push    rdi
0x180019895  push    r14
0x180019897  sub     rsp, 20h
0x18001989b  cmp     qword ptr [rcx+10h], 0
0x1800198a0  mov     rdi, rcx
0x1800198a3  jz      loc_180019969
0x1800198a9  mov     rax, [rdi+38h]
0x1800198ad  mov     rcx, [rcx+8]
0x1800198b1  shr     rax, 3
0x1800198b5  cmp     rax, [rdi+10h]
0x1800198b9  jbe     short loc_1800198CE
0x1800198bb  mov     rdx, [rcx]
0x1800198be  mov     r8, rcx
0x1800198c1  mov     rcx, rdi
0x1800198c4  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>,void *> *,std::_List_node<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>,void *> * const)
0x1800198c9  jmp     loc_180019969
0x1800198ce  mov     rax, [rcx+8]
0x1800198d2  mov     qword ptr [rax], 0
0x1800198d9  mov     rbx, [rcx]
0x1800198dc  test    rbx, rbx
0x1800198df  jz      short loc_180019926
0x1800198e1  mov     rsi, [rbx+30h]
0x1800198e5  mov     r14, [rbx]
0x1800198e8  test    rsi, rsi
0x1800198eb  jz      short loc_180019908
0x1800198ed  mov     rcx, [rsi]; hLibModule
0x1800198f0  test    rcx, rcx
0x1800198f3  jz      short loc_1800198FB
0x1800198f5  call    cs:__imp_FreeLibrary
0x1800198fb  mov     edx, 10h; unsigned __int64
0x180019900  mov     rcx, rsi; void *
0x180019903  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019908  lea     rcx, [rbx+10h]
0x18001990c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019911  mov     edx, 38h ; '8'; unsigned __int64
0x180019916  mov     rcx, rbx; void *
0x180019919  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001991e  mov     rbx, r14
0x180019921  test    r14, r14
0x180019924  jnz     short loc_1800198E1
0x180019926  mov     rax, [rdi+8]
0x18001992a  xor     edx, edx
0x18001992c  mov     [rax], rax
0x18001992f  mov     rax, [rdi+8]
0x180019933  mov     [rax+8], rax
0x180019937  mov     qword ptr [rdi+10h], 0
0x18001993f  mov     r8, [rdi+18h]
0x180019943  mov     rcx, [rdi+20h]
0x180019947  mov     rax, [rdi+8]
0x18001994b  sub     rcx, r8
0x18001994e  add     rcx, 7
0x180019952  shr     rcx, 3
0x180019956  cmp     r8, [rdi+20h]
0x18001995a  cmova   rcx, rdx
0x18001995e  test    rcx, rcx
0x180019961  jz      short loc_180019969
0x180019963  mov     rdi, r8
0x180019966  rep stosq
0x180019969  add     rsp, 20h
0x18001996d  pop     r14
0x18001996f  pop     rdi
0x180019970  pop     rsi
0x180019971  pop     rbp
0x180019972  pop     rbx
0x180019973  retn
```
