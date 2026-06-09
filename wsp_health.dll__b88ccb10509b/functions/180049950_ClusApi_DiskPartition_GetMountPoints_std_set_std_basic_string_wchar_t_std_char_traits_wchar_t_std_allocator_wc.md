# ClusApi::DiskPartition::GetMountPoints(std::set<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *)

- ea: `0x180049950`
- end: `0x180049b75`
- name: `?GetMountPoints@DiskPartition@ClusApi@@UEAAJPEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `549`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path`

## callees

- `0x180003514`
- `0x18000b8e4`
- `0x1800131a0`
- `0x180020b80`
- `0x180020db0`
- `0x180021b50`
- `0x180043a5c`
- `0x180046c68`
- `0x1800475e4`
- `0x180047d04`
- `0x180049950`
- `0x18004f7c4`
- `0x18008c010`

## string_xrefs

- `0x1800499b8`: `cluswmiext!ClusApi::DiskPartition::GetMountPoints`
- `0x180049a96`: `cluswmiext!ClusApi::DiskPartition::GetMountPoints`

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
0x180049950  push    rbp
0x180049952  push    rbx
0x180049953  push    rsi
0x180049954  push    rdi
0x180049955  push    r14
0x180049957  push    r15
0x180049959  lea     rbp, [rsp-2Fh]
0x18004995e  sub     rsp, 98h
0x180049965  mov     r15, rdx
0x180049968  mov     r14, rcx
0x18004996b  call    ?CanRetrieveMountPoints@DiskPartition@ClusApi@@AEBA_NXZ; ClusApi::DiskPartition::CanRetrieveMountPoints(void)
0x180049970  test    al, al
0x180049972  jz      loc_180049B63
0x180049978  mov     [rbp+57h+arg_10], 0
0x18004997f  mov     edx, 7Dh ; '}'
0x180049984  lea     rcx, [rbp+57h+var_50]
0x180049988  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18004998d  nop
0x18004998e  mov     rcx, [r14+30h]
0x180049992  mov     rax, [rcx]
0x180049995  xorps   xmm0, xmm0
0x180049998  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004999d  mov     r9, [rbp+57h+var_50]
0x1800499a1  mov     rdx, [rbp+57h+var_40]
0x1800499a5  sub     rdx, r9
0x1800499a8  sar     rdx, 1
0x1800499ab  add     edx, edx
0x1800499ad  mov     r8, [r14+28h]
0x1800499b1  add     r8, 474h
0x1800499b8  lea     r10, aCluswmiextClus_45; "cluswmiext!ClusApi::DiskPartition::GetM"...
0x1800499bf  mov     [rsp+0C0h+var_80], r10
0x1800499c4  lea     r10, [rbp+57h+var_60]
0x1800499c8  mov     [rsp+0C0h+var_88], r10
0x1800499cd  lea     r10, [rbp+57h+arg_10]
0x1800499d1  mov     [rsp+0C0h+var_90], r10
0x1800499d6  mov     [rsp+0C0h+var_98], edx
0x1800499da  mov     [rsp+0C0h+var_A0], r9
0x1800499df  mov     edx, 1000211h
0x1800499e4  mov     r9d, 4
0x1800499ea  mov     rax, [rax+28h]
0x1800499ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499f3  mov     esi, eax
0x1800499f5  mov     rcx, [rbp+57h+var_60+8]; this
0x1800499f9  test    rcx, rcx
0x1800499fc  jz      short loc_180049A03
0x1800499fe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049a03  cmp     esi, 800700EAh
0x180049a09  jnz     loc_180049AE2
0x180049a0f  mov     ebx, [rbp+57h+arg_10]
0x180049a12  shr     rbx, 1
0x180049a15  mov     rdx, [rbp+57h+var_50]
0x180049a19  mov     rdi, [rbp+57h+var_48]
0x180049a1d  mov     rcx, rdi
0x180049a20  sub     rcx, rdx
0x180049a23  sar     rcx, 1
0x180049a26  cmp     rbx, rcx
0x180049a29  jnb     short loc_180049A31
0x180049a2b  lea     rax, [rdx+rbx*2]
0x180049a2f  jmp     short loc_180049A67
0x180049a31  jbe     short loc_180049A6B
0x180049a33  mov     rax, [rbp+57h+var_40]
0x180049a37  sub     rax, rdx
0x180049a3a  sar     rax, 1
0x180049a3d  cmp     rbx, rax
0x180049a40  jbe     short loc_180049A50
0x180049a42  mov     rdx, rbx
0x180049a45  lea     rcx, [rbp+57h+var_50]
0x180049a49  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180049a4e  jmp     short loc_180049A6B
0x180049a50  sub     rbx, rcx
0x180049a53  add     rbx, rbx
0x180049a56  mov     r8, rbx; Size
0x180049a59  xor     edx, edx; Val
0x180049a5b  mov     rcx, rdi; void *
0x180049a5e  call    memset_0
0x180049a63  lea     rax, [rbx+rdi]
0x180049a67  mov     [rbp+57h+var_48], rax
0x180049a6b  mov     rcx, [r14+30h]
0x180049a6f  mov     rax, [rcx]
0x180049a72  xorps   xmm0, xmm0
0x180049a75  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180049a7a  mov     r11, [rbp+57h+var_50]
0x180049a7e  mov     r10, [rbp+57h+var_40]
0x180049a82  sub     r10, r11
0x180049a85  sar     r10, 1
0x180049a88  add     r10d, r10d
0x180049a8b  mov     r8, [r14+28h]
0x180049a8f  add     r8, 474h
0x180049a96  lea     rdx, aCluswmiextClus_45; "cluswmiext!ClusApi::DiskPartition::GetM"...
0x180049a9d  mov     [rsp+0C0h+var_80], rdx
0x180049aa2  lea     rbx, [rbp+57h+var_60]
0x180049aa6  mov     [rsp+0C0h+var_88], rbx
0x180049aab  mov     [rsp+0C0h+var_90], 0
0x180049ab4  mov     [rsp+0C0h+var_98], r10d
0x180049ab9  mov     [rsp+0C0h+var_A0], r11
0x180049abe  mov     edx, 1000211h
0x180049ac3  mov     r9d, 4
0x180049ac9  mov     rax, [rax+28h]
0x180049acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ad2  mov     esi, eax
0x180049ad4  mov     rcx, [rbp+57h+var_60+8]; this
0x180049ad8  test    rcx, rcx
0x180049adb  jz      short loc_180049AE2
0x180049add  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049ae2  test    esi, esi
0x180049ae4  js      short loc_180049B4B
0x180049ae6  mov     rdi, [rbp+57h+var_50]
0x180049aea  mov     rbx, [rbp+57h+var_48]
0x180049aee  sub     rbx, rdi
0x180049af1  sar     rbx, 1
0x180049af4  lea     rcx, [rbp+57h+var_60]
0x180049af8  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180049afd  nop
0x180049afe  mov     r8, rbx
0x180049b01  mov     rdx, rdi
0x180049b04  lea     rcx, [rbp+57h+var_60]
0x180049b08  call    ?construct@?$MultiSz@V?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@cxl@@AEAAXPEB_W_K@Z; cxl::MultiSz<std::set<std::wstring>>::construct(wchar_t const *,unsigned __int64)
0x180049b0d  nop
0x180049b0e  lea     rdx, [rbp+57h+var_60]
0x180049b12  lea     rcx, [rbp+57h+var_70]
0x180049b16  call    ??$?0V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitive_LessThan@cxl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,cxl::CaseInsensitive_LessThan,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,cxl::CaseInsensitive_LessThan,std::allocator<std::wstring>,0>>(std::_Tree<std::_Tset_traits<std::wstring,cxl::CaseInsensitive_LessThan,std::allocator<std::wstring>,0>> const &,std::allocator<std::_Tree_node<std::wstring,void *>> &&)
0x180049b1b  cmp     [rbp+57h+var_68], 0
0x180049b20  jbe     short loc_180049B2E
0x180049b22  lea     rdx, [rbp+57h+var_70]
0x180049b26  mov     rcx, r15
0x180049b29  call    ??4?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::set<std::wstring>::operator=(std::set<std::wstring> &&)
0x180049b2e  lea     rdx, [rbp+57h+var_70]
0x180049b32  lea     rcx, [rbp+57h+var_70]
0x180049b36  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x180049b3b  nop
0x180049b3c  lea     rdx, [rbp+57h+var_60]
0x180049b40  lea     rcx, [rbp+57h+var_60]
0x180049b44  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x180049b49  jmp     short loc_180049B56
0x180049b4b  xor     eax, eax
0x180049b4d  cmp     esi, 80070001h
0x180049b53  cmovz   esi, eax
0x180049b56  lea     rcx, [rbp+57h+var_50]
0x180049b5a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180049b5f  mov     eax, esi
0x180049b61  jmp     short loc_180049B65
0x180049b63  xor     eax, eax
0x180049b65  add     rsp, 98h
0x180049b6c  pop     r15
0x180049b6e  pop     r14
0x180049b70  pop     rdi
0x180049b71  pop     rsi
0x180049b72  pop     rbx
0x180049b73  pop     rbp
0x180049b74  retn
```
