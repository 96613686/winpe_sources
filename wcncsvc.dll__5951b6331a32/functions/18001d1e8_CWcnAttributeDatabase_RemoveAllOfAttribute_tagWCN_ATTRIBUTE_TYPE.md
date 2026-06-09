# CWcnAttributeDatabase::RemoveAllOfAttribute(tagWCN_ATTRIBUTE_TYPE)

- ea: `0x18001d1e8`
- end: `0x18001d27f`
- name: `?RemoveAllOfAttribute@CWcnAttributeDatabase@@QEAAXW4tagWCN_ATTRIBUTE_TYPE@@@Z`
- size: `151`
- prototype: `void __fastcall(CWcnAttributeDatabase *__hidden this, enum tagWCN_ATTRIBUTE_TYPE)`
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000c6e8`
- `0x18000c864`
- `0x18000ccc8`
- `0x180017604`
- `0x180017a70`
- `0x180017ff4`
- `0x18002a3a8`
- `0x180048c94`
- `0x1800496c0`
- `0x18004d374`

## callees

- `0x18000a5ac`
- `0x18001d1e8`
- `0x18001d474`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001d24d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d24d`

## pseudocode

```c
void __fastcall CWcnAttributeDatabase::RemoveAllOfAttribute(CWcnAttributeDatabase *this, enum tagWCN_ATTRIBUTE_TYPE a2)
{
  char *v2; // r14
  __int64 *v3; // rcx
  __int64 *v4; // rbx
  __int64 *v5; // rax
  __int64 *v6; // rbp
  __int64 *i; // rdi
  __int64 v8; // rsi
  char v9; // [rsp+40h] [rbp+8h] BYREF

  v2 = (char *)this + 16;
  v3 = (__int64 *)*((_QWORD *)this + 2);
  v4 = v3;
  v5 = (__int64 *)v3[1];
  if ( !*((_BYTE *)v5 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v5 + 8) >= a2 )
      {
        v4 = v5;
        v5 = (__int64 *)*v5;
      }
      else
      {
        v5 = (__int64 *)v5[2];
      }
    }
    while ( !*((_BYTE *)v5 + 25) );
    if ( v4 != v3 && a2 >= *((_DWORD *)v4 + 8) )
    {
      v6 = (__int64 *)v4[6];
      for ( i = (__int64 *)v4[5]; i != v6; ++i )
      {
        v8 = *i;
        if ( *i )
        {
          CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)(v8 + 24));
          operator delete((void *)v8);
        }
      }
      std::_Tree<std::_Tmap_traits<enum tagWCN_ATTRIBUTE_TYPE,std::vector<CWcnAttribute *>,std::less<enum tagWCN_ATTRIBUTE_TYPE>,std::allocator<std::pair<enum tagWCN_ATTRIBUTE_TYPE const,std::vector<CWcnAttribute *>>>,0>>::erase(
        v2,
        &v9,
        v4);
    }
  }
}

```

## disassembly

```asm
0x18001d1e8  mov     [rsp+arg_8], rbx
0x18001d1ed  mov     [rsp+arg_10], rbp
0x18001d1f2  push    rsi
0x18001d1f3  push    rdi
0x18001d1f4  push    r14
0x18001d1f6  sub     rsp, 20h
0x18001d1fa  lea     r14, [rcx+10h]
0x18001d1fe  mov     rcx, [r14]
0x18001d201  mov     rbx, rcx
0x18001d204  mov     rax, [rcx+8]
0x18001d208  cmp     byte ptr [rax+19h], 0
0x18001d20c  jnz     short loc_18001D26C
0x18001d20e  cmp     [rax+20h], edx
0x18001d211  jge     short loc_18001D219
0x18001d213  mov     rax, [rax+10h]
0x18001d217  jmp     short loc_18001D21F
0x18001d219  mov     rbx, rax
0x18001d21c  mov     rax, [rax]
0x18001d21f  cmp     byte ptr [rax+19h], 0
0x18001d223  jz      short loc_18001D20E
0x18001d225  cmp     rbx, rcx
0x18001d228  jz      short loc_18001D26C
0x18001d22a  cmp     edx, [rbx+20h]
0x18001d22d  jl      short loc_18001D26C
0x18001d22f  mov     rbp, [rbx+30h]
0x18001d233  mov     rdi, [rbx+28h]
0x18001d237  jmp     short loc_18001D257
0x18001d239  mov     rsi, [rdi]
0x18001d23c  test    rsi, rsi
0x18001d23f  jz      short loc_18001D253
0x18001d241  lea     rcx, [rsi+18h]; this
0x18001d245  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x18001d24a  mov     rcx, rsi
0x18001d24d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d253  add     rdi, 8
0x18001d257  cmp     rdi, rbp
0x18001d25a  jnz     short loc_18001D239
0x18001d25c  mov     r8, rbx
0x18001d25f  lea     rdx, [rsp+38h+arg_0]
0x18001d264  mov     rcx, r14
0x18001d267  call    ?erase@?$_Tree@V?$_Tmap_traits@W4tagWCN_ATTRIBUTE_TYPE@@V?$vector@PEAVCWcnAttribute@@V?$allocator@PEAVCWcnAttribute@@@std@@@std@@U?$less@W4tagWCN_ATTRIBUTE_TYPE@@@3@V?$allocator@U?$pair@$$CBW4tagWCN_ATTRIBUTE_TYPE@@V?$vector@PEAVCWcnAttribute@@V?$allocator@PEAVCWcnAttribute@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagWCN_ATTRIBUTE_TYPE@@V?$vector@PEAVCWcnAttribute@@V?$allocator@PEAVCWcnAttribute@@@std@@@std@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4tagWCN_ATTRIBUTE_TYPE@@V?$vector@PEAVCWcnAttribute@@V?$allocator@PEAVCWcnAttribute@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<tagWCN_ATTRIBUTE_TYPE,std::vector<CWcnAttribute *>,std::less<tagWCN_ATTRIBUTE_TYPE>,std::allocator<std::pair<tagWCN_ATTRIBUTE_TYPE const,std::vector<CWcnAttribute *>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<tagWCN_ATTRIBUTE_TYPE const,std::vector<CWcnAttribute *>>>>>)
0x18001d26c  mov     rbx, [rsp+38h+arg_8]
0x18001d271  mov     rbp, [rsp+38h+arg_10]
0x18001d276  add     rsp, 20h
0x18001d27a  pop     r14
0x18001d27c  pop     rdi
0x18001d27d  pop     rsi
0x18001d27e  retn
```
