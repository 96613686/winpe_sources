# ClusApi::DiskPartition::GetMountPoints(std::set<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *)

- ea: `0x18004b290`
- end: `0x18004b4b6`
- name: `?GetMountPoints@DiskPartition@ClusApi@@UEAAJPEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `550`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path`

## callees

- `0x1800035b4`
- `0x18000bc64`
- `0x180013864`
- `0x18002176c`
- `0x1800219a0`
- `0x18002274c`
- `0x18004527c`
- `0x1800484f8`
- `0x180048e98`
- `0x180049618`
- `0x18004b290`
- `0x1800511f8`
- `0x18008e010`

## string_xrefs

- `0x18004b2f8`: `cluswmiext!ClusApi::DiskPartition::GetMountPoints`
- `0x18004b3d6`: `cluswmiext!ClusApi::DiskPartition::GetMountPoints`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ClusApi::DiskPartition::GetMountPoints(ClusApi::DiskPartition *a1, __int64 a2)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // esi
  unsigned __int64 v7; // rbx
  char *v8; // rdi
  unsigned __int64 v9; // rcx
  char *v10; // rax
  size_t v11; // rbx
  __int64 *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rbx
  char v17[8]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v18; // [rsp+58h] [rbp-11h]
  std::_Ref_count_base *v19[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v20; // [rsp+70h] [rbp+7h] BYREF
  void *v21; // [rsp+78h] [rbp+Fh]
  __int64 v22; // [rsp+80h] [rbp+17h]
  unsigned int v23; // [rsp+E0h] [rbp+77h] BYREF

  if ( !ClusApi::DiskPartition::CanRetrieveMountPoints(a1) )
    return 0;
  v23 = 0;
  std::vector<wchar_t>::vector<wchar_t>(&v20, 125);
  v4 = (__int64 *)*((_QWORD *)a1 + 6);
  v5 = *v4;
  *(_OWORD *)v19 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int64, unsigned int, unsigned int *, std::_Ref_count_base **, const wchar_t *))(v5 + 40))(
         v4,
         16777745,
         *((_QWORD *)a1 + 5) + 1140LL,
         4,
         v20,
         2 * (unsigned int)((v22 - v20) >> 1),
         &v23,
         v19,
         L"cluswmiext!ClusApi::DiskPartition::GetMountPoints");
  if ( v19[1] )
    std::_Ref_count_base::_Decref(v19[1]);
  if ( v6 == -2147024662 )
  {
    v7 = (unsigned __int64)v23 >> 1;
    v8 = (char *)v21;
    v9 = ((__int64)v21 - v20) >> 1;
    if ( v7 >= v9 )
    {
      if ( v7 <= v9 )
        goto LABEL_12;
      if ( v7 > (v22 - v20) >> 1 )
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&v20, (unsigned __int64)v23 >> 1);
        goto LABEL_12;
      }
      v11 = 2 * (v7 - v9);
      memset_0(v21, 0, v11);
      v10 = &v8[v11];
    }
    else
    {
      v10 = (char *)(v20 + 2 * v7);
    }
    v21 = v10;
LABEL_12:
    v12 = (__int64 *)*((_QWORD *)a1 + 6);
    v13 = *v12;
    *(_OWORD *)v19 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int64, unsigned int, _QWORD, std::_Ref_count_base **, const wchar_t *))(v13 + 40))(
           v12,
           16777745,
           *((_QWORD *)a1 + 5) + 1140LL,
           4,
           v20,
           2 * (unsigned int)((v22 - v20) >> 1),
           0,
           v19,
           L"cluswmiext!ClusApi::DiskPartition::GetMountPoints");
    if ( v19[1] )
      std::_Ref_count_base::_Decref(v19[1]);
  }
  if ( v6 < 0 )
  {
    if ( v6 == -2147024895 )
      v6 = 0;
  }
  else
  {
    v14 = v20;
    v15 = ((__int64)v21 - v20) >> 1;
    std::set<std::wstring>::set<std::wstring>(v19);
    cxl::MultiSz<std::set<std::wstring>>::construct(v19, v14, v15);
    std::_Tree<std::_Tset_traits<std::wstring,cxl::CaseInsensitive_LessThan,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,cxl::CaseInsensitive_LessThan,std::allocator<std::wstring>,0>>(
      v17,
      v19);
    if ( v18 )
      std::set<std::wstring>::operator=(a2, v17);
    std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
      v17,
      v17);
    std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
      v19,
      v19);
  }
  std::vector<unsigned short>::_Tidy(&v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004b290  push    rbp
0x18004b292  push    rbx
0x18004b293  push    rsi
0x18004b294  push    rdi
0x18004b295  push    r14
0x18004b297  push    r15
0x18004b299  lea     rbp, [rsp-2Fh]
0x18004b29e  sub     rsp, 98h
0x18004b2a5  mov     r15, rdx
0x18004b2a8  mov     r14, rcx
0x18004b2ab  call    ?CanRetrieveMountPoints@DiskPartition@ClusApi@@AEBA_NXZ; ClusApi::DiskPartition::CanRetrieveMountPoints(void)
0x18004b2b0  test    al, al
0x18004b2b2  jz      loc_18004B4A3
0x18004b2b8  mov     [rbp+57h+arg_10], 0
0x18004b2bf  mov     edx, 7Dh ; '}'
0x18004b2c4  lea     rcx, [rbp+57h+var_50]
0x18004b2c8  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18004b2cd  nop
0x18004b2ce  mov     rcx, [r14+30h]
0x18004b2d2  mov     rax, [rcx]
0x18004b2d5  xorps   xmm0, xmm0
0x18004b2d8  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004b2dd  mov     r9, [rbp+57h+var_50]
0x18004b2e1  mov     rdx, [rbp+57h+var_40]
0x18004b2e5  sub     rdx, r9
0x18004b2e8  sar     rdx, 1
0x18004b2eb  add     edx, edx
0x18004b2ed  mov     r8, [r14+28h]
0x18004b2f1  add     r8, 474h
0x18004b2f8  lea     r10, aCluswmiextClus_45; "cluswmiext!ClusApi::DiskPartition::GetM"...
0x18004b2ff  mov     [rsp+0C0h+var_80], r10
0x18004b304  lea     r10, [rbp+57h+var_60]
0x18004b308  mov     [rsp+0C0h+var_88], r10
0x18004b30d  lea     r10, [rbp+57h+arg_10]
0x18004b311  mov     [rsp+0C0h+var_90], r10
0x18004b316  mov     [rsp+0C0h+var_98], edx
0x18004b31a  mov     [rsp+0C0h+var_A0], r9
0x18004b31f  mov     edx, 1000211h
0x18004b324  mov     r9d, 4
0x18004b32a  mov     rax, [rax+28h]
0x18004b32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b333  mov     esi, eax
0x18004b335  mov     rcx, [rbp+57h+var_60+8]; this
0x18004b339  test    rcx, rcx
0x18004b33c  jz      short loc_18004B343
0x18004b33e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b343  cmp     esi, 800700EAh
0x18004b349  jnz     loc_18004B422
0x18004b34f  mov     ebx, [rbp+57h+arg_10]
0x18004b352  shr     rbx, 1
0x18004b355  mov     rdx, [rbp+57h+var_50]
0x18004b359  mov     rdi, [rbp+57h+var_48]
0x18004b35d  mov     rcx, rdi
0x18004b360  sub     rcx, rdx
0x18004b363  sar     rcx, 1
0x18004b366  cmp     rbx, rcx
0x18004b369  jnb     short loc_18004B371
0x18004b36b  lea     rax, [rdx+rbx*2]
0x18004b36f  jmp     short loc_18004B3A7
0x18004b371  jbe     short loc_18004B3AB
0x18004b373  mov     rax, [rbp+57h+var_40]
0x18004b377  sub     rax, rdx
0x18004b37a  sar     rax, 1
0x18004b37d  cmp     rbx, rax
0x18004b380  jbe     short loc_18004B390
0x18004b382  mov     rdx, rbx
0x18004b385  lea     rcx, [rbp+57h+var_50]
0x18004b389  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18004b38e  jmp     short loc_18004B3AB
0x18004b390  sub     rbx, rcx
0x18004b393  add     rbx, rbx
0x18004b396  mov     r8, rbx; Size
0x18004b399  xor     edx, edx; Val
0x18004b39b  mov     rcx, rdi; void *
0x18004b39e  call    memset_0
0x18004b3a3  lea     rax, [rbx+rdi]
0x18004b3a7  mov     [rbp+57h+var_48], rax
0x18004b3ab  mov     rcx, [r14+30h]
0x18004b3af  mov     rax, [rcx]
0x18004b3b2  xorps   xmm0, xmm0
0x18004b3b5  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004b3ba  mov     r11, [rbp+57h+var_50]
0x18004b3be  mov     r10, [rbp+57h+var_40]
0x18004b3c2  sub     r10, r11
0x18004b3c5  sar     r10, 1
0x18004b3c8  add     r10d, r10d
0x18004b3cb  mov     r8, [r14+28h]
0x18004b3cf  add     r8, 474h
0x18004b3d6  lea     rdx, aCluswmiextClus_45; "cluswmiext!ClusApi::DiskPartition::GetM"...
0x18004b3dd  mov     [rsp+0C0h+var_80], rdx
0x18004b3e2  lea     rbx, [rbp+57h+var_60]
0x18004b3e6  mov     [rsp+0C0h+var_88], rbx
0x18004b3eb  mov     [rsp+0C0h+var_90], 0
0x18004b3f4  mov     [rsp+0C0h+var_98], r10d
0x18004b3f9  mov     [rsp+0C0h+var_A0], r11
0x18004b3fe  mov     edx, 1000211h
0x18004b403  mov     r9d, 4
0x18004b409  mov     rax, [rax+28h]
0x18004b40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b412  mov     esi, eax
0x18004b414  mov     rcx, [rbp+57h+var_60+8]; this
0x18004b418  test    rcx, rcx
0x18004b41b  jz      short loc_18004B422
0x18004b41d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004b422  test    esi, esi
0x18004b424  js      short loc_18004B48B
0x18004b426  mov     rdi, [rbp+57h+var_50]
0x18004b42a  mov     rbx, [rbp+57h+var_48]
0x18004b42e  sub     rbx, rdi
0x18004b431  sar     rbx, 1
0x18004b434  lea     rcx, [rbp+57h+var_60]
0x18004b438  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18004b43d  nop
0x18004b43e  mov     r8, rbx
0x18004b441  mov     rdx, rdi
0x18004b444  lea     rcx, [rbp+57h+var_60]
0x18004b448  call    ?construct@?$MultiSz@V?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@cxl@@AEAAXPEB_W_K@Z; cxl::MultiSz<std::set<std::wstring>>::construct(wchar_t const *,unsigned __int64)
0x18004b44d  nop
0x18004b44e  lea     rdx, [rbp+57h+var_60]
0x18004b452  lea     rcx, [rbp+57h+var_70]
0x18004b456  call    ??$?0V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitive_LessThan@cxl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,cxl::CaseInsensitive_LessThan,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,cxl::CaseInsensitive_LessThan,std::allocator<std::wstring>,0>>(std::_Tree<std::_Tset_traits<std::wstring,cxl::CaseInsensitive_LessThan,std::allocator<std::wstring>,0>> const &,std::allocator<std::_Tree_node<std::wstring,void *>> &&)
0x18004b45b  cmp     [rbp+57h+var_68], 0
0x18004b460  jbe     short loc_18004B46E
0x18004b462  lea     rdx, [rbp+57h+var_70]
0x18004b466  mov     rcx, r15
0x18004b469  call    ??4?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::set<std::wstring>::operator=(std::set<std::wstring> &&)
0x18004b46e  lea     rdx, [rbp+57h+var_70]
0x18004b472  lea     rcx, [rbp+57h+var_70]
0x18004b476  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x18004b47b  nop
0x18004b47c  lea     rdx, [rbp+57h+var_60]
0x18004b480  lea     rcx, [rbp+57h+var_60]
0x18004b484  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x18004b489  jmp     short loc_18004B496
0x18004b48b  xor     eax, eax
0x18004b48d  cmp     esi, 80070001h
0x18004b493  cmovz   esi, eax
0x18004b496  lea     rcx, [rbp+57h+var_50]
0x18004b49a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004b49f  mov     eax, esi
0x18004b4a1  jmp     short loc_18004B4A5
0x18004b4a3  xor     eax, eax
0x18004b4a5  add     rsp, 98h
0x18004b4ac  pop     r15
0x18004b4ae  pop     r14
0x18004b4b0  pop     rdi
0x18004b4b1  pop     rsi
0x18004b4b2  pop     rbx
0x18004b4b3  pop     rbp
0x18004b4b4  retn
```
