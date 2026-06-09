# std::_Hash<std::_Umap_traits<uint,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>>,0>>::emplace<uint const &,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>>>(uint const &,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>> &&)

- ea: `0x1800101f4`
- end: `0x1800103ef`
- name: `??$emplace@AEBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@?$_Hash@V?$_Umap_traits@IV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@AEBI$$QEAV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@1@@Z`
- size: `507`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016208`

## callees

- `0x180003be4`
- `0x1800101f4`
- `0x18001147c`
- `0x180016f40`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010291`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010291`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned int,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>,0>>::emplace<unsigned int const &,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        __int64 *a4)
{
  __int64 v8; // rbp
  unsigned __int64 i; // rcx
  __int64 v10; // rdx
  __int64 *v11; // rax
  __int64 **v12; // r12
  __int64 *v13; // rsi
  _DWORD *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  float v17; // xmm0_4
  __int64 v18; // rcx
  float v19; // xmm1_4
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rax
  _QWORD *v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 *v26; // r8
  __int64 v28; // [rsp+20h] [rbp-58h] BYREF
  _DWORD *v29; // [rsp+28h] [rbp-50h]

  v8 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v8 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + i) ^ (unsigned __int64)v8);
  v10 = *(_QWORD *)(a1 + 24);
  v11 = *(__int64 **)(v10 + 16 * (v8 & *(_QWORD *)(a1 + 48)) + 8);
  v12 = (__int64 **)(a1 + 8);
  v13 = *(__int64 **)(a1 + 8);
  if ( v11 == v13 )
  {
LABEL_8:
    if ( *(_QWORD *)(a1 + 16) == 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("unordered_map/set too long");
    v28 = a1 + 8;
    v14 = operator new(0x20u);
    v29 = v14;
    v14[4] = *a3;
    v15 = *a4;
    *a4 = 0;
    *((_QWORD *)v14 + 3) = v15;
    v16 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v16 < 0 )
      v17 = (float)(v16 & 1 | (unsigned int)((unsigned __int64)v16 >> 1))
          + (float)(v16 & 1 | (unsigned int)((unsigned __int64)v16 >> 1));
    else
      v17 = (float)(int)v16;
    v18 = *(_QWORD *)(a1 + 56);
    if ( v18 < 0 )
    {
      v20 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v18 >> 1);
      v19 = (float)(int)v20 + (float)(int)v20;
    }
    else
    {
      v19 = (float)(int)v18;
    }
    if ( (float)(v17 / v19) > *(float *)a1 )
    {
      std::_Hash<std::_Umap_traits<enum _WHESVC_SCENARIOS,_WNF_STATE_NAME,std::_Uhash_compare<enum _WHESVC_SCENARIOS,std::hash<enum _WHESVC_SCENARIOS>,std::equal_to<enum _WHESVC_SCENARIOS>>,std::allocator<std::pair<enum _WHESVC_SCENARIOS const,_WNF_STATE_NAME>>,0>>::_Rehash_for_1(a1);
      v21 = *(_QWORD *)(a1 + 24);
      v22 = *(__int64 **)(v21 + 16 * (v8 & *(_QWORD *)(a1 + 48)) + 8);
      v13 = *v12;
      if ( v22 != *v12 )
      {
        while ( v14[4] != *((_DWORD *)v22 + 4) )
        {
          if ( v22 == *(__int64 **)(v21 + 16 * (v8 & *(_QWORD *)(a1 + 48))) )
          {
            v13 = v22;
            goto LABEL_23;
          }
          v22 = (__int64 *)v22[1];
        }
        v13 = (__int64 *)*v22;
      }
    }
LABEL_23:
    v29 = 0;
    v23 = (_QWORD *)v13[1];
    ++*(_QWORD *)(a1 + 16);
    *(_QWORD *)v14 = v13;
    *((_QWORD *)v14 + 1) = v23;
    *v23 = v14;
    v13[1] = (__int64)v14;
    v24 = 2 * (v8 & *(_QWORD *)(a1 + 48));
    v25 = *(_QWORD *)(a1 + 24);
    v26 = *(__int64 **)(v25 + 16 * (v8 & *(_QWORD *)(a1 + 48)));
    if ( v26 == *v12 )
    {
      *(_QWORD *)(v25 + 16 * (v8 & *(_QWORD *)(a1 + 48))) = v14;
LABEL_28:
      *(_QWORD *)(v25 + 8 * v24 + 8) = v14;
      goto LABEL_29;
    }
    if ( v26 == v13 )
    {
      *(_QWORD *)(v25 + 16 * (v8 & *(_QWORD *)(a1 + 48))) = v14;
    }
    else if ( *(_QWORD **)(v25 + 16 * (v8 & *(_QWORD *)(a1 + 48)) + 8) == v23 )
    {
      goto LABEL_28;
    }
LABEL_29:
    *(_QWORD *)a2 = v14;
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>,void *>>>(&v28);
    return a2;
  }
  while ( *a3 != *((_DWORD *)v11 + 4) )
  {
    if ( v11 == *(__int64 **)(v10 + 16 * (v8 & *(_QWORD *)(a1 + 48))) )
    {
      v13 = v11;
      goto LABEL_8;
    }
    v11 = (__int64 *)v11[1];
  }
  *(_QWORD *)a2 = v11;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x1800101f4  push    rbx
0x1800101f6  push    rbp
0x1800101f7  push    rsi
0x1800101f8  push    rdi
0x1800101f9  push    r12
0x1800101fb  push    r13
0x1800101fd  push    r14
0x1800101ff  push    r15
0x180010201  sub     rsp, 38h
0x180010205  mov     r13, r9
0x180010208  mov     r15, r8
0x18001020b  mov     r14, rdx
0x18001020e  mov     rdi, rcx
0x180010211  mov     rbp, 0CBF29CE484222325h
0x18001021b  xor     ecx, ecx
0x18001021d  movzx   eax, byte ptr [r8+rcx]
0x180010222  xor     rbp, rax
0x180010225  mov     rdx, 100000001B3h
0x18001022f  imul    rbp, rdx
0x180010233  inc     rcx
0x180010236  cmp     rcx, 4
0x18001023a  jb      short loc_18001021D
0x18001023c  mov     rcx, [rdi+30h]
0x180010240  and     rcx, rbp
0x180010243  add     rcx, rcx
0x180010246  mov     rdx, [rdi+18h]
0x18001024a  mov     rax, [rdx+rcx*8+8]
0x18001024f  lea     r12, [rdi+8]
0x180010253  mov     rsi, [r12]
0x180010257  cmp     rax, rsi
0x18001025a  jz      short loc_18001027A
0x18001025c  mov     r8, [rdx+rcx*8]
0x180010260  mov     ecx, [r15]
0x180010263  cmp     ecx, [rax+10h]
0x180010266  jz      loc_1800103D3
0x18001026c  cmp     rax, r8
0x18001026f  jz      short loc_180010277
0x180010271  mov     rax, [rax+8]
0x180010275  jmp     short loc_180010263
0x180010277  mov     rsi, rax
0x18001027a  mov     rax, 7FFFFFFFFFFFFFFh
0x180010284  cmp     [rdi+10h], rax
0x180010288  jnz     short loc_180010298
0x18001028a  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180010291  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180010298  mov     [rsp+78h+var_58], r12
0x18001029d  mov     [rsp+78h+var_50], 0
0x1800102a6  mov     ecx, 20h ; ' '; Size
0x1800102ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800102b0  mov     rbx, rax
0x1800102b3  mov     [rsp+78h+var_50], rax
0x1800102b8  mov     ecx, [r15]
0x1800102bb  mov     [rax+10h], ecx
0x1800102be  mov     rcx, [r13+0]
0x1800102c2  mov     qword ptr [r13+0], 0
0x1800102ca  mov     [rax+18h], rcx
0x1800102ce  mov     rcx, [rdi+10h]
0x1800102d2  add     rcx, 1
0x1800102d6  xorps   xmm0, xmm0
0x1800102d9  js      short loc_1800102E2
0x1800102db  cvtsi2ss xmm0, rcx
0x1800102e0  jmp     short loc_1800102F7
0x1800102e2  mov     rax, rcx
0x1800102e5  shr     rax, 1
0x1800102e8  and     ecx, 1
0x1800102eb  or      rax, rcx
0x1800102ee  cvtsi2ss xmm0, rax
0x1800102f3  addss   xmm0, xmm0
0x1800102f7  mov     rcx, [rdi+38h]
0x1800102fb  xorps   xmm1, xmm1
0x1800102fe  test    rcx, rcx
0x180010301  js      short loc_18001030A
0x180010303  cvtsi2ss xmm1, rcx
0x180010308  jmp     short loc_18001031F
0x18001030a  mov     rax, rcx
0x18001030d  shr     rax, 1
0x180010310  and     ecx, 1
0x180010313  or      rax, rcx
0x180010316  cvtsi2ss xmm1, rax
0x18001031b  addss   xmm1, xmm1
0x18001031f  divss   xmm0, xmm1
0x180010323  comiss  xmm0, dword ptr [rdi]
0x180010326  jbe     short loc_18001036B
0x180010328  mov     rcx, rdi
0x18001032b  call    ?_Rehash_for_1@?$_Hash@V?$_Umap_traits@W4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@V?$_Uhash_compare@W4_WHESVC_SCENARIOS@@U?$hash@W4_WHESVC_SCENARIOS@@@std@@U?$equal_to@W4_WHESVC_SCENARIOS@@@3@@std@@V?$allocator@U?$pair@$$CBW4_WHESVC_SCENARIOS@@U_WNF_STATE_NAME@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Umap_traits<_WHESVC_SCENARIOS,_WNF_STATE_NAME,std::_Uhash_compare<_WHESVC_SCENARIOS,std::hash<_WHESVC_SCENARIOS>,std::equal_to<_WHESVC_SCENARIOS>>,std::allocator<std::pair<_WHESVC_SCENARIOS const,_WNF_STATE_NAME>>,0>>::_Rehash_for_1(void)
0x180010330  mov     rcx, [rdi+30h]
0x180010334  and     rcx, rbp
0x180010337  add     rcx, rcx
0x18001033a  mov     rdx, [rdi+18h]
0x18001033e  mov     rax, [rdx+rcx*8+8]
0x180010343  mov     rsi, [r12]
0x180010347  cmp     rax, rsi
0x18001034a  jz      short loc_18001036B
0x18001034c  mov     r8, [rdx+rcx*8]
0x180010350  mov     ecx, [rbx+10h]
0x180010353  cmp     ecx, [rax+10h]
0x180010356  jz      short loc_180010368
0x180010358  cmp     rax, r8
0x18001035b  jz      short loc_180010363
0x18001035d  mov     rax, [rax+8]
0x180010361  jmp     short loc_180010353
0x180010363  mov     rsi, rax
0x180010366  jmp     short loc_18001036B
0x180010368  mov     rsi, [rax]
0x18001036b  mov     [rsp+78h+var_50], 0
0x180010374  mov     rdx, [rsi+8]
0x180010378  inc     qword ptr [rdi+10h]
0x18001037c  mov     [rbx], rsi
0x18001037f  mov     [rbx+8], rdx
0x180010383  mov     [rdx], rbx
0x180010386  mov     [rsi+8], rbx
0x18001038a  mov     rax, [rdi+30h]
0x18001038e  and     rax, rbp
0x180010391  add     rax, rax
0x180010394  mov     rcx, [rdi+18h]
0x180010398  mov     r8, [rcx+rax*8]
0x18001039c  cmp     r8, [r12]
0x1800103a0  jnz     short loc_1800103A8
0x1800103a2  mov     [rcx+rax*8], rbx
0x1800103a6  jmp     short loc_1800103BA
0x1800103a8  cmp     r8, rsi
0x1800103ab  jnz     short loc_1800103B3
0x1800103ad  mov     [rcx+rax*8], rbx
0x1800103b1  jmp     short loc_1800103BF
0x1800103b3  cmp     [rcx+rax*8+8], rdx
0x1800103b8  jnz     short loc_1800103BF
0x1800103ba  mov     [rcx+rax*8+8], rbx
0x1800103bf  mov     [r14], rbx
0x1800103c2  mov     byte ptr [r14+8], 1
0x1800103c7  lea     rcx, [rsp+78h+var_58]
0x1800103cc  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>,void *>>>(void)
0x1800103d1  jmp     short loc_1800103DB
0x1800103d3  mov     [r14], rax
0x1800103d6  mov     byte ptr [r14+8], 0
0x1800103db  mov     rax, r14
0x1800103de  add     rsp, 38h
0x1800103e2  pop     r15
0x1800103e4  pop     r14
0x1800103e6  pop     r13
0x1800103e8  pop     r12
0x1800103ea  pop     rdi
0x1800103eb  pop     rsi
0x1800103ec  pop     rbp
0x1800103ed  pop     rbx
0x1800103ee  retn
```
