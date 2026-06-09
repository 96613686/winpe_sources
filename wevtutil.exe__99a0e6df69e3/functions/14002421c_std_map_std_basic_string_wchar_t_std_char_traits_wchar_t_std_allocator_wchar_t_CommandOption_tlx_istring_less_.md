# std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,CommandOption>>>::_Try_emplace<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&)

- ea: `0x14002421c`
- end: `0x140024352`
- name: `??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_NV12@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEA_N$$QEAV31@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140024504`

## callees

- `0x140023f1c`
- `0x140023ffc`
- `0x14002421c`
- `0x1400243e4`
- `0x140024910`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400242ca`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400242ca`

## pseudocode

```c
__int64 __fastcall std::map<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>>::_Try_emplace<std::wstring const &,bool &,std::wstring>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int64 v5; // rdi
  __int64 *v9; // r14
  unsigned __int64 v10; // rbx
  unsigned __int64 *v11; // rax
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rbx
  __int128 v16; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v17[16]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v18; // [rsp+50h] [rbp-20h]
  __int64 v19; // [rsp+A0h] [rbp+30h] BYREF

  v5 = *(_QWORD *)a1;
  v9 = (__int64 *)a1;
  v10 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
  v18 = v10;
  while ( !*(_BYTE *)(v10 + 25) )
  {
    *(_QWORD *)&v18 = v10;
    LOBYTE(a1) = tlx::istring_less_ordinal::operator()<std::wstring,std::wstring,wchar_t,wchar_t,0>(a1, v10 + 32);
    if ( (_BYTE)a1 )
    {
      DWORD2(v18) = 0;
    }
    else
    {
      DWORD2(v18) = 1;
      v5 = v10;
    }
    v11 = (unsigned __int64 *)(v10 + 16);
    if ( !(_BYTE)a1 )
      v11 = (unsigned __int64 *)v10;
    v10 = *v11;
  }
  if ( *(_BYTE *)(v5 + 25) || tlx::istring_less_ordinal::operator()<std::wstring,std::wstring,wchar_t,wchar_t,0>(a1, a3) )
  {
    if ( v9[1] == 0x276276276276276LL )
      std::_Xlength_error("map/set too long");
    v12 = *v9;
    *(_QWORD *)&v16 = a5;
    *((_QWORD *)&v16 + 1) = a4;
    v19 = a3;
    v13 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *>>>(
            (unsigned int)v17,
            (_DWORD)v9,
            v12,
            a4,
            (__int64)&v19,
            (__int64)&v16);
    v14 = *(_QWORD *)(v13 + 8);
    *(_QWORD *)(v13 + 8) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *>>>(v17);
    v16 = v18;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CommandOption>>>::_Insert_node(
                      v9,
                      &v16,
                      v14);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v5;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x14002421c  mov     [rsp-28h+arg_8], rbx
0x140024221  mov     [rsp-28h+arg_10], rsi
0x140024226  push    rbp
0x140024227  push    rdi
0x140024228  push    r12
0x14002422a  push    r14
0x14002422c  push    r15
0x14002422e  mov     rbp, rsp
0x140024231  sub     rsp, 70h
0x140024235  mov     rdi, [rcx]
0x140024238  mov     r12, r9
0x14002423b  mov     r15, r8
0x14002423e  mov     qword ptr [rbp+var_20+8], 0
0x140024246  mov     rsi, rdx
0x140024249  mov     r14, rcx
0x14002424c  mov     rbx, [rdi+8]
0x140024250  mov     qword ptr [rbp+var_20], rbx
0x140024254  jmp     short loc_14002428C
0x140024256  lea     rdx, [rbx+20h]
0x14002425a  mov     qword ptr [rbp+var_20], rbx
0x14002425e  mov     r8, r15
0x140024261  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V01@_W_W$0A@@istring_less_ordinal@tlx@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; tlx::istring_less_ordinal::operator()<std::wstring,std::wstring,wchar_t,wchar_t,0>(std::wstring const &,std::wstring const &)
0x140024266  mov     cl, al
0x140024268  test    al, al
0x14002426a  jz      short loc_140024275
0x14002426c  mov     dword ptr [rbp+var_20+8], 0
0x140024273  jmp     short loc_14002427F
0x140024275  mov     dword ptr [rbp+var_20+8], 1
0x14002427c  mov     rdi, rbx
0x14002427f  lea     rax, [rbx+10h]
0x140024283  test    cl, cl
0x140024285  cmovz   rax, rbx
0x140024289  mov     rbx, [rax]
0x14002428c  cmp     byte ptr [rbx+19h], 0
0x140024290  jz      short loc_140024256
0x140024292  cmp     byte ptr [rdi+19h], 0
0x140024296  jnz     short loc_1400242B3
0x140024298  lea     r8, [rdi+20h]
0x14002429c  mov     rdx, r15
0x14002429f  call    ??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V01@_W_W$0A@@istring_less_ordinal@tlx@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; tlx::istring_less_ordinal::operator()<std::wstring,std::wstring,wchar_t,wchar_t,0>(std::wstring const &,std::wstring const &)
0x1400242a4  test    al, al
0x1400242a6  jnz     short loc_1400242B3
0x1400242a8  mov     [rsi], rdi
0x1400242ab  mov     [rsi+8], al
0x1400242ae  jmp     loc_140024336
0x1400242b3  mov     rax, 276276276276276h
0x1400242bd  cmp     [r14+8], rax
0x1400242c1  jnz     short loc_1400242D1
0x1400242c3  lea     rcx, aMapSetTooLong; "map/set too long"
0x1400242ca  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1400242d1  mov     rax, [rbp+arg_20]
0x1400242d5  lea     rcx, [rbp+var_30]
0x1400242d9  mov     r8, [r14]
0x1400242dc  mov     rdx, r14
0x1400242df  mov     qword ptr [rbp+var_40], rax
0x1400242e3  lea     rax, [rbp+var_40]
0x1400242e7  mov     [rsp+70h+var_48], rax
0x1400242ec  lea     rax, [rbp+arg_0]
0x1400242f0  mov     [rsp+70h+var_50], rax
0x1400242f5  mov     qword ptr [rbp+var_40+8], r12
0x1400242f9  mov     [rbp+arg_0], r15
0x1400242fd  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@V?$tuple@AEA_N$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@$$QEAV?$tuple@AEA_N$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *>> &,std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *> *,std::piecewise_construct_t const &,std::tuple<std::wstring const &> &&,std::tuple<bool &,std::wstring &&> &&)
0x140024302  lea     rcx, [rbp+var_30]
0x140024306  mov     rbx, [rax+8]
0x14002430a  mov     qword ptr [rax+8], 0
0x140024312  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *>>>(void)
0x140024317  movups  xmm0, [rbp+var_20]
0x14002431b  mov     r8, rbx
0x14002431e  lea     rdx, [rbp+var_40]
0x140024322  mov     rcx, r14
0x140024325  movdqu  [rbp+var_40], xmm0
0x14002432a  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CommandOption>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *> *>,std::_Tree_node<std::pair<std::wstring const,CommandOption>,void *> * const)
0x14002432f  mov     [rsi], rax
0x140024332  mov     byte ptr [rsi+8], 1
0x140024336  lea     r11, [rsp+70h+var_s0]
0x14002433b  mov     rax, rsi
0x14002433e  mov     rbx, [r11+38h]
0x140024342  mov     rsi, [r11+40h]
0x140024346  mov     rsp, r11
0x140024349  pop     r15
0x14002434b  pop     r14
0x14002434d  pop     r12
0x14002434f  pop     rdi
0x140024350  pop     rbp
0x140024351  retn
```
