# std::map<uchar,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>,std::less<uchar>,std::allocator<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>>>::_Try_emplace<uchar const &,>(uchar const &)

- ea: `0x18000d1b4`
- end: `0x18000d2a4`
- name: `??$_Try_emplace@AEBE$$V@?$map@EV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBE@Z`
- size: `240`
- prototype: `__int64 __fastcall(__int64 *, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000f6a0`

## callees

- `0x1800060b8`
- `0x18000cc90`
- `0x18000ccf8`
- `0x18000d1b4`
- `0x18000d2ac`
- `0x18000db58`
- `0x1800151a0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d204`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000d204`

## pseudocode

```c
__int64 __fastcall std::map<unsigned char,std::unique_ptr<KEY_MAP_RECORD_CACHE>>::_Try_emplace<unsigned char const &,>(
        __int64 *a1,
        __int64 a2,
        _BYTE *a3)
{
  _BYTE *v5; // r8
  _QWORD *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r8
  _BYTE *v10; // [rsp+30h] [rbp-48h] BYREF
  __int128 v11; // [rsp+40h] [rbp-38h] BYREF
  __int128 v12; // [rsp+50h] [rbp-28h] BYREF
  __int64 v13; // [rsp+60h] [rbp-18h]
  __int64 v14; // [rsp+B8h] [rbp+40h] BYREF

  std::_Tree<std::_Tmap_traits<unsigned char,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::_Find_lower_bound<unsigned char>(
    a1,
    &v12,
    a3);
  if ( *(_BYTE *)(v13 + 25) || *v5 < *(_BYTE *)(v13 + 32) )
  {
    if ( a1[1] == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v10 = v5;
    v14 = *a1;
    v11 = (unsigned __int64)a1;
    v6 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>::construct<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,std::piecewise_construct_t const &,std::tuple<unsigned char const &>,std::tuple<>>(
      v7,
      v6 + 4,
      v8,
      &v10);
    std::_Construct_in_place<unsigned short *,unsigned short * const &>(v6, &v14);
    std::_Construct_in_place<unsigned short *,unsigned short * const &>(v6 + 1, &v14);
    std::_Construct_in_place<unsigned short *,unsigned short * const &>(v6 + 2, &v14);
    *((_WORD *)v6 + 12) = 0;
    *((_QWORD *)&v11 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(&v11);
    v11 = v12;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Insert_node(
                      a1,
                      &v11,
                      v6);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v13;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000d1b4  push    rbp
0x18000d1b6  push    rbx
0x18000d1b7  push    rsi
0x18000d1b8  push    rdi
0x18000d1b9  mov     rbp, rsp
0x18000d1bc  sub     rsp, 78h
0x18000d1c0  mov     rdi, rdx
0x18000d1c3  mov     rsi, rcx
0x18000d1c6  lea     rdx, [rbp+var_28]
0x18000d1ca  call    ??$_Find_lower_bound@E@?$_Tree@V?$_Tmap_traits@EV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@1@AEBE@Z; std::_Tree<std::_Tmap_traits<uchar,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<uchar>,std::allocator<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::_Find_lower_bound<uchar>(uchar const &)
0x18000d1cf  mov     rdx, [rbp+var_18]
0x18000d1d3  cmp     byte ptr [rdx+19h], 0
0x18000d1d7  jnz     short loc_18000D1ED
0x18000d1d9  mov     al, [rdx+20h]
0x18000d1dc  cmp     [r8], al
0x18000d1df  jb      short loc_18000D1ED
0x18000d1e1  mov     [rdi], rdx
0x18000d1e4  mov     byte ptr [rdi+8], 0
0x18000d1e8  jmp     loc_18000D298
0x18000d1ed  mov     rax, 555555555555555h
0x18000d1f7  cmp     [rsi+8], rax
0x18000d1fb  jnz     short loc_18000D20B
0x18000d1fd  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000d204  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000d20b  mov     [rbp+var_48], r8
0x18000d20f  mov     rax, [rsi]
0x18000d212  mov     [rbp+arg_18], rax
0x18000d216  mov     qword ptr [rbp+var_38], rsi
0x18000d21a  mov     qword ptr [rbp+var_38+8], 0
0x18000d222  mov     ecx, 30h ; '0'
0x18000d227  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000d22c  mov     rbx, rax
0x18000d22f  lea     rdx, [rax+20h]
0x18000d233  lea     r9, [rbp+var_48]
0x18000d237  call    ??$construct@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBE@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBE@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>::construct<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,std::piecewise_construct_t const &,std::tuple<uchar const &>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>> &,std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>> * const,std::piecewise_construct_t const &,std::tuple<uchar const &> &&,std::tuple<> &&)
0x18000d23c  lea     rdx, [rbp+arg_18]
0x18000d240  mov     rcx, rbx
0x18000d243  call    ??$_Construct_in_place@PEAGAEBQEAG@std@@YAXAEAPEAGAEBQEAG@Z; std::_Construct_in_place<ushort *,ushort * const &>(ushort * &,ushort * const &)
0x18000d248  lea     rcx, [rbx+8]
0x18000d24c  lea     rdx, [rbp+arg_18]
0x18000d250  call    ??$_Construct_in_place@PEAGAEBQEAG@std@@YAXAEAPEAGAEBQEAG@Z; std::_Construct_in_place<ushort *,ushort * const &>(ushort * &,ushort * const &)
0x18000d255  lea     rcx, [rbx+10h]
0x18000d259  lea     rdx, [rbp+arg_18]
0x18000d25d  call    ??$_Construct_in_place@PEAGAEBQEAG@std@@YAXAEAPEAGAEBQEAG@Z; std::_Construct_in_place<ushort *,ushort * const &>(ushort * &,ushort * const &)
0x18000d262  mov     word ptr [rbx+18h], 0
0x18000d268  mov     qword ptr [rbp+var_38+8], 0
0x18000d270  lea     rcx, [rbp+var_38]
0x18000d274  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(void)
0x18000d279  movups  xmm0, [rbp+var_28]
0x18000d27d  movdqu  [rbp+var_38], xmm0
0x18000d282  mov     r8, rbx
0x18000d285  lea     rdx, [rbp+var_38]
0x18000d289  mov     rcx, rsi
0x18000d28c  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> *>,std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *> * const)
0x18000d291  mov     [rdi], rax
0x18000d294  mov     byte ptr [rdi+8], 1
0x18000d298  mov     rax, rdi
0x18000d29b  add     rsp, 78h
0x18000d29f  pop     rdi
0x18000d2a0  pop     rsi
0x18000d2a1  pop     rbx
0x18000d2a2  pop     rbp
0x18000d2a3  retn
```
