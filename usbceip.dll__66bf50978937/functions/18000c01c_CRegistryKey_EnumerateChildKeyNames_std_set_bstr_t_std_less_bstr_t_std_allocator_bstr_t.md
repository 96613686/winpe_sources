# CRegistryKey::EnumerateChildKeyNames(std::set<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>> &)

- ea: `0x18000c01c`
- end: `0x18000c081`
- name: `?EnumerateChildKeyNames@CRegistryKey@@QEAAXAEAV?$set@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@@std@@@Z`
- size: `101`
- prototype: `void __fastcall(CRegistryKey *this, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005e94`
- `0x180007754`

## callees

- `0x180003fec`
- `0x18000bc24`
- `0x18000be14`
- `0x18000c01c`

## pseudocode

```c
void __fastcall CRegistryKey::EnumerateChildKeyNames(CRegistryKey *this, __int64 a2)
{
  CRegistryKey *v3; // rdi
  int v4; // ebx
  unsigned int v5; // edx
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  v3 = this;
  v7 = 0;
  v4 = 0;
  v5 = 0;
  while ( CRegistryKey::EnumKeyName(this, v5, (struct _bstr_t *)&v7) )
  {
    std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::insert<0,0>(a2, v6, &v7);
    v5 = ++v4;
    this = v3;
  }
  _bstr_t::_Free((_bstr_t *)&v7);
}

```

## disassembly

```asm
0x18000c01c  mov     [rsp+arg_0], rbx
0x18000c021  mov     [rsp+arg_8], rsi
0x18000c026  push    rdi
0x18000c027  sub     rsp, 30h
0x18000c02b  mov     rsi, rdx
0x18000c02e  mov     rdi, rcx
0x18000c031  mov     [rsp+38h+arg_10], 0
0x18000c03a  xor     ebx, ebx
0x18000c03c  xor     edx, edx
0x18000c03e  jmp     short loc_18000C059
0x18000c040  lea     r8, [rsp+38h+arg_10]
0x18000c045  lea     rdx, [rsp+38h+var_18]
0x18000c04a  mov     rcx, rsi
0x18000c04d  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V_bstr_t@@@std@@@std@@@std@@_N@1@AEBV_bstr_t@@@Z; std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::insert<0,0>(_bstr_t const &)
0x18000c052  inc     ebx
0x18000c054  mov     edx, ebx; unsigned int
0x18000c056  mov     rcx, rdi; this
0x18000c059  lea     r8, [rsp+38h+arg_10]; struct _bstr_t *
0x18000c05e  call    ?EnumKeyName@CRegistryKey@@AEAAEKAEAV_bstr_t@@@Z; CRegistryKey::EnumKeyName(ulong,_bstr_t &)
0x18000c063  test    al, al
0x18000c065  jnz     short loc_18000C040
0x18000c067  lea     rcx, [rsp+38h+arg_10]; this
0x18000c06c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c071  mov     rbx, [rsp+38h+arg_0]
0x18000c076  mov     rsi, [rsp+38h+arg_8]
0x18000c07b  add     rsp, 30h
0x18000c07f  pop     rdi
0x18000c080  retn
```
