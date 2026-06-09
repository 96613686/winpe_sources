# TASK_LIST::TASK_ENTRY_MAP::Add(TASK_ENTRY &)

- ea: `0x18001a15c`
- end: `0x18001a2c1`
- name: `?Add@TASK_ENTRY_MAP@TASK_LIST@@QEAAXAEAVTASK_ENTRY@@@Z`
- size: `357`
- prototype: `void __fastcall(TASK_LIST::TASK_ENTRY_MAP *__hidden this, struct TASK_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180018eb8`

## callees

- `0x18001a15c`
- `0x18001b340`
- `0x18001c02c`
- `0x1800207c0`
- `0x18002d1ac`
- `0x180030fe4`
- `0x180031018`
- `0x18003104c`
- `0x180033df0`

## pseudocode

```c
void __fastcall TASK_LIST::TASK_ENTRY_MAP::Add(TASK_LIST::TASK_ENTRY_MAP *this, struct TASK_ENTRY *a2)
{
  struct TASK_ENTRY *v2; // rbx
  unsigned __int16 *v4; // rdi
  _QWORD *v5; // rdi
  __int64 v6; // rax
  unsigned __int64 v7; // rcx
  __int64 v8; // r8
  _BYTE v9[8]; // [rsp+20h] [rbp-39h] BYREF
  char v10; // [rsp+28h] [rbp-31h]
  _QWORD v11[2]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v12[80]; // [rsp+40h] [rbp-19h] BYREF

  v2 = a2;
  v11[0] = a2;
  std::_Tree<std::_Tmap_traits<std::wstring_view,TASK_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TASK_ENTRY *>>,0>>::_Emplace<std::wstring &,TASK_ENTRY *>(
    this,
    v9,
    a2,
    v11);
  if ( !v10 )
  {
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(struct TASK_ENTRY **)v2;
    ThrowWithFormatMessage(-1073221873, v2);
  }
  v4 = (unsigned __int16 *)((char *)v2 + 32);
  LODWORD(v11[0]) = *((unsigned __int16 *)v2 + 16);
  std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
    (char *)this + 16,
    v9,
    v11);
  if ( !v10 )
  {
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(struct TASK_ENTRY **)v2;
    ThrowWithFormatMessage(-1073221872, *v4, v2);
  }
  v5 = (_QWORD *)((char *)v2 + 40);
  if ( *((_QWORD *)v2 + 7) )
  {
    v6 = std::wstring::operator std::wstring_view((char *)v2 + 40, v11);
    std::_Tree<std::_Tset_traits<std::wstring_view,std::less<std::wstring_view>,std::allocator<std::wstring_view>,0>>::insert<0,0>(
      (char *)this + 32,
      v9,
      v6);
    if ( !v10 )
    {
      if ( *((_QWORD *)v2 + 8) > 7u )
        v5 = (_QWORD *)*v5;
      ThrowWithFormatMessage(-1073221871, v5);
    }
  }
  v7 = *((_QWORD *)v2 + 13);
  if ( !v7 )
    v7 = *((_QWORD *)v2 + 14) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v7 )
  {
    std::_Tree<std::_Tset_traits<_GUID,ManparseGuidLess,std::allocator<_GUID>,0>>::insert<0,0>(
      (char *)this + 48,
      v9,
      (char *)v2 + 104);
    if ( !v10 )
    {
      LOBYTE(v8) = 1;
      tlx::guid_to_string_lower<wchar_t>(v12, (char *)v2 + 104, v8);
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(struct TASK_ENTRY **)v2;
      ThrowWithFormatMessage(-1073221870, v12, v2);
    }
  }
}

```

## disassembly

```asm
0x18001a15c  mov     [rsp-8+arg_10], rbx
0x18001a161  push    rbp
0x18001a162  push    rsi
0x18001a163  push    rdi
0x18001a164  lea     rbp, [rsp-47h]
0x18001a169  sub     rsp, 0A0h
0x18001a170  mov     rax, cs:__security_cookie
0x18001a177  xor     rax, rsp
0x18001a17a  mov     [rbp+57h+var_20], rax
0x18001a17e  mov     rbx, rdx
0x18001a181  mov     [rbp+57h+var_80], rdx
0x18001a185  mov     r8, rdx
0x18001a188  lea     r9, [rbp+57h+var_80]
0x18001a18c  lea     rdx, [rbp+57h+var_90]
0x18001a190  mov     rsi, rcx
0x18001a193  call    ??$_Emplace@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVTASK_ENTRY@@@?$_Tree@V?$_Tmap_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@PEAX@std@@_N@1@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAPEAVTASK_ENTRY@@@Z; std::_Tree<std::_Tmap_traits<std::wstring_view,TASK_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TASK_ENTRY *>>,0>>::_Emplace<std::wstring &,TASK_ENTRY *>(std::wstring &,TASK_ENTRY * &&)
0x18001a198  cmp     [rbp+57h+var_88], 0
0x18001a19c  jnz     short loc_18001A1B6
0x18001a19e  cmp     qword ptr [rbx+18h], 7
0x18001a1a3  jbe     short loc_18001A1A8
0x18001a1a5  mov     rbx, [rbx]
0x18001a1a8  mov     rdx, rbx
0x18001a1ab  mov     ecx, 0C007EF0Fh; int
0x18001a1b0  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001a1b6  lea     rdi, [rbx+20h]
0x18001a1ba  movzx   eax, word ptr [rdi]
0x18001a1bd  lea     rcx, [rsi+10h]
0x18001a1c1  lea     r8, [rbp+57h+var_80]
0x18001a1c5  mov     dword ptr [rbp+57h+var_80], eax
0x18001a1c8  lea     rdx, [rbp+57h+var_90]
0x18001a1cc  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@$$QEAK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<0,0>(ulong &&)
0x18001a1d1  cmp     [rbp+57h+var_88], 0
0x18001a1d5  jnz     short loc_18001A1F2
0x18001a1d7  cmp     qword ptr [rbx+18h], 7
0x18001a1dc  jbe     short loc_18001A1E1
0x18001a1de  mov     rbx, [rbx]
0x18001a1e1  movzx   edx, word ptr [rdi]
0x18001a1e4  mov     r8, rbx
0x18001a1e7  mov     ecx, 0C007EF10h; int
0x18001a1ec  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001a1f2  lea     rdi, [rbx+28h]
0x18001a1f6  cmp     qword ptr [rdi+10h], 0
0x18001a1fb  jz      short loc_18001A237
0x18001a1fd  lea     rdx, [rbp+57h+var_80]
0x18001a201  mov     rcx, rdi
0x18001a204  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18001a209  mov     r8, rax
0x18001a20c  lea     rcx, [rsi+20h]
0x18001a210  lea     rdx, [rbp+57h+var_90]
0x18001a214  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring_view,std::less<std::wstring_view>,std::allocator<std::wstring_view>,0>>::insert<0,0>(std::wstring_view &&)
0x18001a219  cmp     [rbp+57h+var_88], 0
0x18001a21d  jnz     short loc_18001A237
0x18001a21f  cmp     qword ptr [rdi+18h], 7
0x18001a224  jbe     short loc_18001A229
0x18001a226  mov     rdi, [rdi]
0x18001a229  mov     rdx, rdi
0x18001a22c  mov     ecx, 0C007EF11h; int
0x18001a231  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001a237  xorps   xmm0, xmm0
0x18001a23a  lea     rdi, [rbx+68h]
0x18001a23e  mov     rcx, [rdi]
0x18001a241  movq    rax, xmm0
0x18001a246  sub     rcx, rax
0x18001a249  jnz     short loc_18001A25C
0x18001a24b  mov     rcx, [rdi+8]
0x18001a24f  psrldq  xmm0, 8
0x18001a254  movq    rax, xmm0
0x18001a259  sub     rcx, rax
0x18001a25c  test    rcx, rcx
0x18001a25f  jz      short loc_18001A2A2
0x18001a261  lea     rcx, [rsi+30h]
0x18001a265  mov     r8, rdi
0x18001a268  lea     rdx, [rbp+57h+var_90]
0x18001a26c  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_GUID@@UManparseGuidLess@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@@std@@_N@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<_GUID,ManparseGuidLess,std::allocator<_GUID>,0>>::insert<0,0>(_GUID const &)
0x18001a271  cmp     [rbp+57h+var_88], 0
0x18001a275  jnz     short loc_18001A2A2
0x18001a277  mov     r8b, 1
0x18001a27a  lea     rcx, [rbp+57h+var_70]
0x18001a27e  mov     rdx, rdi
0x18001a281  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x18001a286  cmp     qword ptr [rbx+18h], 7
0x18001a28b  jbe     short loc_18001A290
0x18001a28d  mov     rbx, [rbx]
0x18001a290  mov     r8, rbx
0x18001a293  lea     rdx, [rbp+57h+var_70]
0x18001a297  mov     ecx, 0C007EF12h; int
0x18001a29c  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001a2a2  mov     rcx, [rbp+57h+var_20]
0x18001a2a6  xor     rcx, rsp; StackCookie
0x18001a2a9  call    __security_check_cookie
0x18001a2ae  mov     rbx, [rsp+0B0h+arg_10]
0x18001a2b6  add     rsp, 0A0h
0x18001a2bd  pop     rdi
0x18001a2be  pop     rsi
0x18001a2bf  pop     rbp
0x18001a2c0  retn
```
