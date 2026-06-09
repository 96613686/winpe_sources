# std::map<_GUID,ulong,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,ulong>>>::_Try_emplace<_GUID const &,>(_GUID const &)

- ea: `0x180004f98`
- end: `0x1800050a1`
- name: `??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@KUGUIDComparer@CUsbHubSqm@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180005258`

## callees

- `0x180004e18`
- `0x180004e78`
- `0x180004ee4`
- `0x180004f68`
- `0x180004f98`
- `0x1800050a8`
- `0x180005170`
- `0x18000580c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180004ff5`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180004ff5`

## pseudocode

```c
__int64 __fastcall std::map<_GUID,unsigned long,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned long>>>::_Try_emplace<_GUID const &,>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v12; // [rsp+30h] [rbp-40h] BYREF
  __int128 v13; // [rsp+40h] [rbp-30h] BYREF
  __int128 v14; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]
  __int64 v16; // [rsp+A8h] [rbp+38h] BYREF

  std::_Tree<std::_Tmap_traits<_GUID,unsigned long,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::_Find_lower_bound<_GUID>(
    (__int64)a1,
    &v14,
    a3);
  v6 = v15;
  if ( std::_Tree<std::_Tmap_traits<_GUID,unsigned long,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::_Lower_bound_duplicate<_GUID>(
         v7,
         v15,
         a3) )
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v12 = a3;
    v16 = *a1;
    v13 = (unsigned __int64)a1;
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<_GUID const,unsigned long>,void *>>>::construct<std::pair<_GUID const,unsigned long>,std::piecewise_construct_t const &,std::tuple<_GUID const &>,std::tuple<>>(
      v9,
      (char *)v8 + 28,
      v10,
      &v12);
    std::_Construct_in_place<std::_Tree_node<_bstr_t,void *> *,std::_Tree_node<_bstr_t,void *> * &>(v8, &v16);
    std::_Construct_in_place<std::_Tree_node<_bstr_t,void *> *,std::_Tree_node<_bstr_t,void *> * &>(v8 + 1, &v16);
    std::_Construct_in_place<std::_Tree_node<_bstr_t,void *> *,std::_Tree_node<_bstr_t,void *> * &>(v8 + 2, &v16);
    *((_WORD *)v8 + 12) = 0;
    *((_QWORD *)&v13 + 1) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,unsigned long>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,unsigned long>,void *>>>(&v13);
    v13 = v14;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<_bstr_t>>::_Insert_node(a1, &v13, v8);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x180004f98  mov     [rsp-18h+arg_0], rbx
0x180004f9d  mov     [rsp-18h+arg_8], rsi
0x180004fa2  push    rbp
0x180004fa3  push    rdi
0x180004fa4  push    r14
0x180004fa6  mov     rbp, rsp
0x180004fa9  sub     rsp, 70h
0x180004fad  mov     r14, r8
0x180004fb0  mov     rdi, rdx
0x180004fb3  mov     rsi, rcx
0x180004fb6  lea     rdx, [rbp+var_20]
0x180004fba  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@KUGUIDComparer@CUsbHubSqm@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ulong,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x180004fbf  mov     r8, r14
0x180004fc2  mov     rbx, [rbp+var_10]
0x180004fc6  mov     rdx, rbx
0x180004fc9  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@KUGUIDComparer@CUsbHubSqm@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ulong,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,ulong>,void *> * const,_GUID const &)
0x180004fce  test    al, al
0x180004fd0  jz      short loc_180004FDE
0x180004fd2  mov     [rdi], rbx
0x180004fd5  mov     byte ptr [rdi+8], 0
0x180004fd9  jmp     loc_180005089
0x180004fde  mov     rax, 555555555555555h
0x180004fe8  cmp     [rsi+8], rax
0x180004fec  jnz     short loc_180004FFC
0x180004fee  lea     rcx, aMapSetTooLong; "map/set too long"
0x180004ff5  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180004ffc  mov     [rbp+var_40], r14
0x180005000  mov     rax, [rsi]
0x180005003  mov     [rbp+arg_18], rax
0x180005007  mov     qword ptr [rbp+var_30], rsi
0x18000500b  mov     qword ptr [rbp+var_30+8], 0
0x180005013  mov     ecx, 30h ; '0'
0x180005018  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000501d  mov     rbx, rax
0x180005020  lea     rdx, [rax+1Ch]
0x180005024  lea     r9, [rbp+var_40]
0x180005028  call    ??$construct@U?$pair@$$CBU_GUID@@K@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBU_GUID@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@1@QEAU?$pair@$$CBU_GUID@@K@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBU_GUID@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>>>::construct<std::pair<_GUID const,ulong>,std::piecewise_construct_t const &,std::tuple<_GUID const &>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>> &,std::pair<_GUID const,ulong> * const,std::piecewise_construct_t const &,std::tuple<_GUID const &> &&,std::tuple<> &&)
0x18000502d  lea     rdx, [rbp+arg_18]
0x180005031  mov     rcx, rbx
0x180005034  call    ??$_Construct_in_place@PEAU?$_Tree_node@V_bstr_t@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V_bstr_t@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<_bstr_t,void *> *,std::_Tree_node<_bstr_t,void *> * &>(std::_Tree_node<_bstr_t,void *> * &,std::_Tree_node<_bstr_t,void *> * &)
0x180005039  lea     rcx, [rbx+8]
0x18000503d  lea     rdx, [rbp+arg_18]
0x180005041  call    ??$_Construct_in_place@PEAU?$_Tree_node@V_bstr_t@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V_bstr_t@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<_bstr_t,void *> *,std::_Tree_node<_bstr_t,void *> * &>(std::_Tree_node<_bstr_t,void *> * &,std::_Tree_node<_bstr_t,void *> * &)
0x180005046  lea     rcx, [rbx+10h]
0x18000504a  lea     rdx, [rbp+arg_18]
0x18000504e  call    ??$_Construct_in_place@PEAU?$_Tree_node@V_bstr_t@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V_bstr_t@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<_bstr_t,void *> *,std::_Tree_node<_bstr_t,void *> * &>(std::_Tree_node<_bstr_t,void *> * &,std::_Tree_node<_bstr_t,void *> * &)
0x180005053  mov     word ptr [rbx+18h], 0
0x180005059  mov     qword ptr [rbp+var_30+8], 0
0x180005061  lea     rcx, [rbp+var_30]
0x180005065  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>>>(void)
0x18000506a  movups  xmm0, [rbp+var_20]
0x18000506e  movdqu  [rbp+var_30], xmm0
0x180005073  mov     r8, rbx
0x180005076  lea     rdx, [rbp+var_30]
0x18000507a  mov     rcx, rsi
0x18000507d  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V_bstr_t@@@std@@@std@@QEAAPEAU?$_Tree_node@V_bstr_t@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V_bstr_t@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<_bstr_t>>::_Insert_node(std::_Tree_id<std::_Tree_node<_bstr_t,void *> *>,std::_Tree_node<_bstr_t,void *> * const)
0x180005082  mov     [rdi], rax
0x180005085  mov     byte ptr [rdi+8], 1
0x180005089  mov     rax, rdi
0x18000508c  lea     r11, [rsp+70h+var_s0]
0x180005091  mov     rbx, [r11+20h]
0x180005095  mov     rsi, [r11+28h]
0x180005099  mov     rsp, r11
0x18000509c  pop     r14
0x18000509e  pop     rdi
0x18000509f  pop     rbp
0x1800050a0  retn
```
