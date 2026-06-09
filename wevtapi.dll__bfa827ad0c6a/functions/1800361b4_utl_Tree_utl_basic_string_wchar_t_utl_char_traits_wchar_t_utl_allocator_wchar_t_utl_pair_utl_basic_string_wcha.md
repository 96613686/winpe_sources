# utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_NewNodeConstruct<utl::_PairMapTag,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,SectionCache::SectionHeader>(utl::_PairMapTag &&,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,SectionCache::SectionHeader &&)

- ea: `0x1800361b4`
- end: `0x180036239`
- name: `??$_NewNodeConstruct@U_PairMapTag@utl@@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@2@USectionHeader@SectionCache@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@AEAAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@1@$$QEAU_PairMapTag@1@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@$$QEAUSectionHeader@SectionCache@@@Z`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800362c8`

## callees

- `0x18000a0dc`
- `0x180023bb0`
- `0x18002786c`
- `0x180036158`
- `0x180036184`
- `0x1800361b4`
- `0x180036a48`

## pseudocode

```c
__int64 __fastcall utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_NewNodeConstruct<utl::_PairMapTag,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,SectionCache::SectionHeader>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF
  __int64 v12; // [rsp+38h] [rbp+10h] BYREF

  v12 = a2;
  v11 = a1;
  utl::_ContainerBase<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>>::_NewNode<utl::_TreeNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>>(
    a1,
    &v12);
  if ( v12 )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      v12 + 24,
      a3);
    SectionCache::SectionHeader::SectionHeader(v8 + 32, a4);
    v11 = 0;
    utl::_DestroyOnExit<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~_DestroyOnExit<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(&v11);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  v9 = utl::_ContainerBase<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>>::_NewNodeCommit<utl::_TreeNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>>(
         v6,
         &v12,
         v7);
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v12);
  return v9;
}

```

## disassembly

```asm
0x1800361b4  mov     rax, rsp
0x1800361b7  mov     [rax+18h], rbx
0x1800361bb  mov     [rax+10h], rdx
0x1800361bf  mov     [rax+8], rcx
0x1800361c3  push    rdi
0x1800361c4  sub     rsp, 20h
0x1800361c8  lea     rdx, [rax+10h]
0x1800361cc  mov     rbx, r9
0x1800361cf  mov     rdi, r8
0x1800361d2  call    ??$_NewNode@U?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@@utl@@IEAA?AU?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@utl@@@utl@@@1@XZ; utl::_ContainerBase<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>>::_NewNode<utl::_TreeNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>>(void)
0x1800361d7  mov     rax, [rsp+28h+arg_8]
0x1800361dc  test    rax, rax
0x1800361df  jz      short loc_180036211
0x1800361e1  lea     rcx, [rax+18h]
0x1800361e5  mov     rdx, rdi
0x1800361e8  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1800361ed  add     rcx, 20h ; ' '
0x1800361f1  mov     rdx, rbx
0x1800361f4  call    ??0SectionHeader@SectionCache@@QEAA@$$QEAU01@@Z; SectionCache::SectionHeader::SectionHeader(SectionCache::SectionHeader &&)
0x1800361f9  lea     rcx, [rsp+28h+arg_0]
0x1800361fe  mov     [rsp+28h+arg_0], 0
0x180036207  call    ??1?$_DestroyOnExit@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@QEAA@XZ; utl::_DestroyOnExit<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~_DestroyOnExit<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(void)
0x18003620c  mov     r8b, 1
0x18003620f  jmp     short loc_180036214
0x180036211  xor     r8b, r8b
0x180036214  lea     rdx, [rsp+28h+arg_8]
0x180036219  call    ??$_NewNodeCommit@U?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@@utl@@IEAAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@1@AEAU?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@utl@@@utl@@@1@_N@Z; utl::_ContainerBase<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>>::_NewNodeCommit<utl::_TreeNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>>(utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>>> &,bool)
0x18003621e  lea     rcx, [rsp+28h+arg_8]
0x180036223  mov     rbx, rax
0x180036226  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x18003622b  mov     rax, rbx
0x18003622e  mov     rbx, [rsp+28h+arg_10]
0x180036233  add     rsp, 20h
0x180036237  pop     rdi
0x180036238  retn
```
