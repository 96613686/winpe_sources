# CHidDeviceSqm::IsParentVisited(std::unique_ptr<CDevNode,std::default_delete<CDevNode>> &)

- ea: `0x180006c28`
- end: `0x180006d24`
- name: `?IsParentVisited@CHidDeviceSqm@@AEAA_NAEAV?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@@Z`
- size: `252`
- prototype: `char __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180006d2c`

## callees

- `0x180002410`
- `0x180003fec`
- `0x180004344`
- `0x180005d58`
- `0x180006808`
- `0x1800068f0`
- `0x180006980`
- `0x180006a20`
- `0x180006a88`
- `0x180006c28`

## pseudocode

```c
char __fastcall CHidDeviceSqm::IsParentVisited(__int64 a1, _QWORD *a2)
{
  char *String; // rax
  __int64 v4; // r8
  __int64 v5; // rdi
  __int64 v6; // rcx
  char v7; // bl
  _bstr_t::Data_t *v9; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v10[16]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v11; // [rsp+38h] [rbp-38h]
  _OWORD v12[2]; // [rsp+40h] [rbp-30h] BYREF

  v9 = 0;
  _bstr_t::operator=((_bstr_t *)&v9, *a2 + 96LL);
  if ( v9 )
    String = _bstr_t::Data_t::GetString(v9);
  else
    String = 0;
  memset(v12, 0, sizeof(v12));
  v4 = -1;
  do
    ++v4;
  while ( String[v4] );
  std::string::_Construct<1,char const *>(v12, String);
  std::_Tree<std::_Tmap_traits<std::string,unsigned long,CHidDeviceSqm::StrLess,std::allocator<std::pair<std::string const,unsigned long>>,0>>::_Find_lower_bound<std::string>(
    a1 + 16,
    v10,
    v12);
  v5 = v11;
  if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::string,unsigned long,CHidDeviceSqm::StrLess,std::allocator<std::pair<std::string const,unsigned long>>,0>>::_Lower_bound_duplicate<std::string>(
                           v6,
                           v11,
                           v12)
    || v5 == *(_QWORD *)(a1 + 16) )
  {
    *(_DWORD *)(*(_QWORD *)std::map<std::string,unsigned long,CHidDeviceSqm::StrLess,std::allocator<std::pair<std::string const,unsigned long>>>::_Try_emplace<std::string const &,>(
                             a1 + 16,
                             v10,
                             v12)
              + 64LL) = 0;
    v7 = 0;
  }
  else
  {
    v7 = 1;
    ++*(_DWORD *)(v5 + 64);
  }
  std::string::_Tidy_deallocate(v12);
  _bstr_t::_Free((_bstr_t *)&v9);
  return v7;
}

```

## disassembly

```asm
0x180006c28  mov     [rsp-8+arg_10], rbx
0x180006c2d  mov     [rsp-8+arg_18], rdi
0x180006c32  push    rbp
0x180006c33  mov     rbp, rsp
0x180006c36  sub     rsp, 70h
0x180006c3a  mov     rax, cs:__security_cookie
0x180006c41  xor     rax, rsp
0x180006c44  mov     [rbp+var_10], rax
0x180006c48  mov     rbx, rcx
0x180006c4b  mov     [rbp+var_50], 0
0x180006c53  mov     rdx, [rdx]
0x180006c56  add     rdx, 60h ; '`'
0x180006c5a  lea     rcx, [rbp+var_50]
0x180006c5e  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180006c63  mov     rcx, [rbp+var_50]; this
0x180006c67  test    rcx, rcx
0x180006c6a  jz      short loc_180006C73
0x180006c6c  call    ?GetString@Data_t@_bstr_t@@QEBAPEBDXZ; _bstr_t::Data_t::GetString(void)
0x180006c71  jmp     short loc_180006C75
0x180006c73  xor     eax, eax
0x180006c75  xorps   xmm0, xmm0
0x180006c78  movups  [rbp+var_30], xmm0
0x180006c7c  xorps   xmm1, xmm1
0x180006c7f  movdqu  [rbp+var_20], xmm1
0x180006c84  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006c88  inc     r8
0x180006c8b  cmp     byte ptr [rax+r8], 0
0x180006c90  jnz     short loc_180006C88
0x180006c92  mov     rdx, rax
0x180006c95  lea     rcx, [rbp+var_30]
0x180006c99  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180006c9e  nop
0x180006c9f  lea     r8, [rbp+var_30]
0x180006ca3  lea     rdx, [rbp+var_48]
0x180006ca7  lea     rcx, [rbx+10h]
0x180006cab  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@KUStrLess@CHidDeviceSqm@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,ulong,CHidDeviceSqm::StrLess,std::allocator<std::pair<std::string const,ulong>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x180006cb0  lea     r8, [rbp+var_30]
0x180006cb4  mov     rdi, [rbp+var_38]
0x180006cb8  mov     rdx, rdi
0x180006cbb  call    ??$_Lower_bound_duplicate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@KUStrLess@CHidDeviceSqm@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,ulong,CHidDeviceSqm::StrLess,std::allocator<std::pair<std::string const,ulong>>,0>>::_Lower_bound_duplicate<std::string>(std::_Tree_node<std::pair<std::string const,ulong>,void *> * const,std::string const &)
0x180006cc0  test    al, al
0x180006cc2  jz      short loc_180006CD4
0x180006cc4  cmp     rdi, [rbx+10h]
0x180006cc8  jz      short loc_180006CD4
0x180006cca  mov     ebx, 1
0x180006ccf  add     [rdi+40h], ebx
0x180006cd2  jmp     short loc_180006CF1
0x180006cd4  lea     r8, [rbp+var_30]
0x180006cd8  lea     rdx, [rbp+var_48]
0x180006cdc  lea     rcx, [rbx+10h]
0x180006ce0  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@KUStrLess@CHidDeviceSqm@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,ulong,CHidDeviceSqm::StrLess,std::allocator<std::pair<std::string const,ulong>>>::_Try_emplace<std::string const &,>(std::string const &)
0x180006ce5  mov     rcx, [rax]
0x180006ce8  mov     dword ptr [rcx+40h], 0
0x180006cef  xor     bl, bl
0x180006cf1  lea     rcx, [rbp+var_30]
0x180006cf5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180006cfa  nop
0x180006cfb  lea     rcx, [rbp+var_50]; this
0x180006cff  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180006d04  mov     al, bl
0x180006d06  mov     rcx, [rbp+var_10]
0x180006d0a  xor     rcx, rsp; StackCookie
0x180006d0d  call    __security_check_cookie
0x180006d12  lea     r11, [rsp+70h+var_s0]
0x180006d17  mov     rbx, [r11+20h]
0x180006d1b  mov     rdi, [r11+28h]
0x180006d1f  mov     rsp, r11
0x180006d22  pop     rbp
0x180006d23  retn
```
