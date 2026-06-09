# std::map<ShaderLinkingArgument,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::less<ShaderLinkingArgument>,std::allocator<std::pair<ShaderLinkingArgument const,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>>::_Try_emplace<ShaderLinkingArgument const &,>(ShaderLinkingArgument const &)

- ea: `0x18000268c`
- end: `0x1800027b6`
- name: `??$_Try_emplace@AEBW4ShaderLinkingArgument@@$$V@?$map@W4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4ShaderLinkingArgument@@@3@V?$allocator@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@_N@1@AEBW4ShaderLinkingArgument@@@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000241c`
- `0x1800024f0`

## callees

- `0x180001660`
- `0x180001788`
- `0x18000268c`
- `0x1800090a0`
- `0x18000a88c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000278a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000278a`

## pseudocode

```c
__int64 __fastcall std::map<enum ShaderLinkingArgument,std::string>::_Try_emplace<enum ShaderLinkingArgument const &,>(
        _QWORD *a1,
        __int64 a2,
        unsigned __int16 *a3)
{
  __int64 *v3; // r9
  __int64 *v6; // rdx
  __int64 *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rsi
  unsigned __int16 v11; // cx
  char v12; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+38h] [rbp-30h]
  __int128 v14; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 *v15; // [rsp+90h] [rbp+28h] BYREF

  v3 = (__int64 *)*a1;
  v6 = (__int64 *)*a1;
  v7 = *(__int64 **)(*a1 + 8LL);
  v14 = (unsigned __int64)v7;
  if ( !*((_BYTE *)v7 + 25) )
  {
    v11 = *a3;
    do
    {
      *(_QWORD *)&v14 = v7;
      if ( *((_WORD *)v7 + 16) >= v11 )
      {
        DWORD2(v14) = 1;
        v6 = v7;
      }
      else
      {
        DWORD2(v14) = 0;
        v7 += 2;
      }
      v7 = (__int64 *)*v7;
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  if ( *((_BYTE *)v6 + 25) || *a3 < *((_WORD *)v6 + 16) )
  {
    if ( a1[1] == 0x38E38E38E38E38ELL )
      std::_Xlength_error("map/set too long");
    v15 = a3;
    v8 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum ShaderLinkingArgument const,std::string>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum ShaderLinkingArgument const,std::string>,void *>>>(
           (unsigned int)&v12,
           (_DWORD)a1,
           (_DWORD)v3,
           (_DWORD)v3,
           (__int64)&v15);
    v9 = *(_QWORD *)(v8 + 8);
    *(_QWORD *)(v8 + 8) = 0;
    if ( v13 )
    {
      std::string::~string((void *)(v13 + 40));
      if ( v13 )
        std::_Deallocate<16>(v13, 72);
    }
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum ShaderLinkingArgument const,std::string>>>::_Insert_node(
                      a1,
                      &v14,
                      v9);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000268c  push    rbp
0x18000268e  push    rbx
0x18000268f  push    rsi
0x180002690  push    rdi
0x180002691  mov     rbp, rsp
0x180002694  sub     rsp, 68h
0x180002698  mov     r9, [rcx]
0x18000269b  mov     rbx, rdx
0x18000269e  mov     rdi, rcx
0x1800026a1  mov     qword ptr [rbp+var_28+8], 0
0x1800026a9  mov     rdx, r9
0x1800026ac  mov     rax, [r9+8]
0x1800026b0  mov     qword ptr [rbp+var_28], rax
0x1800026b4  cmp     byte ptr [rax+19h], 0
0x1800026b8  jz      short loc_180002738
0x1800026ba  cmp     byte ptr [rdx+19h], 0
0x1800026be  jz      loc_18000276C
0x1800026c4  mov     rax, 38E38E38E38E38Eh
0x1800026ce  cmp     [rdi+8], rax
0x1800026d2  jz      loc_180002783
0x1800026d8  mov     [rbp+arg_0], r8
0x1800026dc  lea     rax, [rbp+arg_0]
0x1800026e0  mov     r8, r9
0x1800026e3  mov     [rsp+68h+var_48], rax
0x1800026e8  mov     rdx, rdi
0x1800026eb  lea     rcx, [rbp+var_38]
0x1800026ef  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBW4ShaderLinkingArgument@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBW4ShaderLinkingArgument@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ShaderLinkingArgument const,std::string>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ShaderLinkingArgument const,std::string>,void *>>>(std::allocator<std::_Tree_node<std::pair<ShaderLinkingArgument const,std::string>,void *>> &,std::_Tree_node<std::pair<ShaderLinkingArgument const,std::string>,void *> *,std::piecewise_construct_t const &,std::tuple<ShaderLinkingArgument const &> &&,std::tuple<> &&)
0x1800026f4  mov     rsi, [rax+8]
0x1800026f8  mov     qword ptr [rax+8], 0
0x180002700  mov     rcx, [rbp+var_30]
0x180002704  test    rcx, rcx
0x180002707  jnz     loc_180002791
0x18000270d  movups  xmm0, [rbp+var_28]
0x180002711  mov     r8, rsi
0x180002714  lea     rdx, [rbp+var_28]
0x180002718  mov     rcx, rdi
0x18000271b  movdqu  [rbp+var_28], xmm0
0x180002720  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ShaderLinkingArgument const,std::string>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ShaderLinkingArgument const,std::string>,void *> *>,std::_Tree_node<std::pair<ShaderLinkingArgument const,std::string>,void *> * const)
0x180002725  mov     [rbx], rax
0x180002728  mov     byte ptr [rbx+8], 1
0x18000272c  mov     rax, rbx
0x18000272f  add     rsp, 68h
0x180002733  pop     rdi
0x180002734  pop     rsi
0x180002735  pop     rbx
0x180002736  pop     rbp
0x180002737  retn
0x180002738  movzx   ecx, word ptr [r8]
0x18000273c  mov     qword ptr [rbp+var_28], rax
0x180002740  cmp     [rax+20h], cx
0x180002744  jnb     short loc_180002760
0x180002746  mov     dword ptr [rbp+var_28+8], 0
0x18000274d  add     rax, 10h
0x180002751  mov     rax, [rax]
0x180002754  cmp     byte ptr [rax+19h], 0
0x180002758  jnz     loc_1800026BA
0x18000275e  jmp     short loc_18000273C
0x180002760  mov     dword ptr [rbp+var_28+8], 1
0x180002767  mov     rdx, rax
0x18000276a  jmp     short loc_180002751
0x18000276c  movzx   eax, word ptr [rdx+20h]
0x180002770  cmp     [r8], ax
0x180002774  jb      loc_1800026C4
0x18000277a  mov     [rbx], rdx
0x18000277d  mov     byte ptr [rbx+8], 0
0x180002781  jmp     short loc_18000272C
0x180002783  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000278a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180002791  add     rcx, 28h ; '('; void *
0x180002795  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000279a  mov     rcx, [rbp+var_30]
0x18000279e  test    rcx, rcx
0x1800027a1  jz      loc_18000270D
0x1800027a7  mov     edx, 48h ; 'H'
0x1800027ac  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800027b1  jmp     loc_18000270D
```
