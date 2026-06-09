# CRegistryKey::EnumValueNames(std::set<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>> &)

- ea: `0x18000bfa0`
- end: `0x18000c013`
- name: `?EnumValueNames@CRegistryKey@@QEAAXAEAV?$set@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@@std@@@Z`
- size: `115`
- prototype: `void __fastcall(CRegistryKey *this, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180005e94`

## callees

- `0x180003fec`
- `0x180007294`
- `0x18000bc24`
- `0x18000bebc`
- `0x18000bfa0`

## pseudocode

```c
void __fastcall CRegistryKey::EnumValueNames(CRegistryKey *this, __int64 a2)
{
  CRegistryKey *v3; // rdi
  int v4; // ebx
  DWORD v5; // edx
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  v3 = this;
  v7 = 0;
  v4 = 0;
  v5 = 0;
  while ( CRegistryKey::EnumValueName(this, v5, (struct _bstr_t *)&v7) )
  {
    if ( _bstr_t::length((_bstr_t *)&v7) )
      std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::insert<0,0>(a2, v6, &v7);
    v5 = ++v4;
    this = v3;
  }
  _bstr_t::_Free((_bstr_t *)&v7);
}

```

## disassembly

```asm
0x18000bfa0  mov     [rsp+arg_0], rbx
0x18000bfa5  mov     [rsp+arg_8], rsi
0x18000bfaa  push    rdi
0x18000bfab  sub     rsp, 30h
0x18000bfaf  mov     rsi, rdx
0x18000bfb2  mov     rdi, rcx
0x18000bfb5  mov     [rsp+38h+arg_10], 0
0x18000bfbe  xor     ebx, ebx
0x18000bfc0  xor     edx, edx
0x18000bfc2  jmp     short loc_18000BFEB
0x18000bfc4  lea     rcx, [rsp+38h+arg_10]; this
0x18000bfc9  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18000bfce  test    eax, eax
0x18000bfd0  jz      short loc_18000BFE4
0x18000bfd2  lea     r8, [rsp+38h+arg_10]
0x18000bfd7  lea     rdx, [rsp+38h+var_18]
0x18000bfdc  mov     rcx, rsi
0x18000bfdf  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V_bstr_t@@@std@@@std@@@std@@_N@1@AEBV_bstr_t@@@Z; std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::insert<0,0>(_bstr_t const &)
0x18000bfe4  inc     ebx
0x18000bfe6  mov     edx, ebx; unsigned int
0x18000bfe8  mov     rcx, rdi; this
0x18000bfeb  lea     r8, [rsp+38h+arg_10]; struct _bstr_t *
0x18000bff0  call    ?EnumValueName@CRegistryKey@@AEAAEKAEAV_bstr_t@@@Z; CRegistryKey::EnumValueName(ulong,_bstr_t &)
0x18000bff5  test    al, al
0x18000bff7  jnz     short loc_18000BFC4
0x18000bff9  lea     rcx, [rsp+38h+arg_10]; this
0x18000bffe  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c003  mov     rbx, [rsp+38h+arg_0]
0x18000c008  mov     rsi, [rsp+38h+arg_8]
0x18000c00d  add     rsp, 30h
0x18000c011  pop     rdi
0x18000c012  retn
```
