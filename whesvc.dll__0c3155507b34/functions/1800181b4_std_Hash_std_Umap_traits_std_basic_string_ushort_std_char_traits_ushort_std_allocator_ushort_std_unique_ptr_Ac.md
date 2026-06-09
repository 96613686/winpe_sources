# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>>,0>>::_Try_emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800181b4`
- end: `0x1800183f1`
- name: `??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `573`
- prototype: `__int64 __fastcall(float *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018c10`

## callees

- `0x180003be4`
- `0x180003d44`
- `0x180018114`
- `0x1800181b4`
- `0x180018664`
- `0x180018970`
- `0x1800191fc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018251`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018251`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Try_emplace<std::wstring const &,>(
        float *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // r8
  _QWORD *v7; // rdx
  unsigned __int64 v8; // rcx
  __int64 v9; // r14
  unsigned __int64 v10; // r8
  _QWORD *v11; // rbx
  unsigned __int64 v12; // rdi
  __int64 v13; // rcx
  float v14; // xmm0_4
  float v15; // xmm2_4
  __int64 v16; // rcx
  float v17; // xmm0_4
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // r8
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r9
  _QWORD *v27; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v28; // [rsp+28h] [rbp-50h]
  _OWORD v29[4]; // [rsp+30h] [rbp-48h] BYREF

  v6 = a3[2];
  if ( a3[3] <= 7u )
    v7 = a3;
  else
    v7 = (_QWORD *)*a3;
  v8 = 0;
  v9 = 0xCBF29CE484222325uLL;
  v10 = 2 * v6;
  if ( v10 )
  {
    do
      v9 = 0x100000001B3LL * (*((unsigned __int8 *)v7 + v8++) ^ (unsigned __int64)v9);
    while ( v8 < v10 );
  }
  std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(
    a1,
    v29,
    (__int64)a3,
    v9);
  if ( !*((_QWORD *)&v29[0] + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0x492492492492492LL )
      std::_Xlength_error("unordered_map/set too long");
    v27 = a1 + 2;
    v11 = operator new(0x38u);
    v28 = v11;
    std::wstring::wstring(v11 + 2, a3);
    v11[6] = 0;
    v12 = *((_QWORD *)a1 + 7);
    v13 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v13 < 0 )
      v14 = (float)(v13 & 1 | (unsigned int)((unsigned __int64)v13 >> 1))
          + (float)(v13 & 1 | (unsigned int)((unsigned __int64)v13 >> 1));
    else
      v14 = (float)(int)v13;
    if ( (v12 & 0x8000000000000000uLL) != 0LL )
    {
      v16 = *((_QWORD *)a1 + 7) & 1LL | (v12 >> 1);
      v15 = (float)(int)v16 + (float)(int)v16;
    }
    else
    {
      v15 = (float)(int)v12;
    }
    if ( (float)(v14 / v15) > *a1 )
    {
      v17 = o_ceilf_0(v14 / *a1);
      v18 = 0;
      if ( v17 >= 9.223372e18 )
      {
        v17 = v17 - 9.223372e18;
        if ( v17 < 9.223372e18 )
          v18 = 0x8000000000000000uLL;
      }
      v19 = v18 + (unsigned int)(int)v17;
      v20 = 8;
      if ( v19 > 8 )
        v20 = v19;
      if ( v12 < v20 )
      {
        if ( v12 >= 0x200 || (v12 *= 8LL, v12 < v20) )
          v12 = v20;
      }
      std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Forced_rehash(
        a1,
        v12);
      v29[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(
                            a1,
                            v29,
                            (__int64)(v11 + 2),
                            v9);
    }
    v28 = 0;
    v21 = *(_QWORD *)&v29[0];
    v22 = *(_QWORD **)(*(_QWORD *)&v29[0] + 8LL);
    ++*((_QWORD *)a1 + 2);
    *v11 = v21;
    v11[1] = v22;
    *v22 = v11;
    *(_QWORD *)(v21 + 8) = v11;
    v23 = 2 * (v9 & *((_QWORD *)a1 + 6));
    v24 = *((_QWORD *)a1 + 3);
    v25 = *(_QWORD *)(v24 + 16 * (v9 & *((_QWORD *)a1 + 6)));
    if ( v25 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v24 + 16 * (v9 & *((_QWORD *)a1 + 6))) = v11;
LABEL_32:
      *(_QWORD *)(v24 + 8 * v23 + 8) = v11;
      goto LABEL_33;
    }
    if ( v25 == v21 )
    {
      *(_QWORD *)(v24 + 16 * (v9 & *((_QWORD *)a1 + 6))) = v11;
    }
    else if ( *(_QWORD **)(v24 + 16 * (v9 & *((_QWORD *)a1 + 6)) + 8) == v22 )
    {
      goto LABEL_32;
    }
LABEL_33:
    *(_QWORD *)a2 = v11;
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>,void *>>>(&v27);
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v29[0] + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x1800181b4  push    rbx
0x1800181b6  push    rbp
0x1800181b7  push    rsi
0x1800181b8  push    rdi
0x1800181b9  push    r13
0x1800181bb  push    r14
0x1800181bd  push    r15
0x1800181bf  sub     rsp, 40h
0x1800181c3  mov     rdi, r8
0x1800181c6  mov     rsi, rdx
0x1800181c9  mov     rbp, rcx
0x1800181cc  mov     r8, [r8+10h]
0x1800181d0  cmp     qword ptr [rdi+18h], 7
0x1800181d5  jbe     short loc_1800181DC
0x1800181d7  mov     rdx, [rdi]
0x1800181da  jmp     short loc_1800181DF
0x1800181dc  mov     rdx, rdi
0x1800181df  xor     ecx, ecx
0x1800181e1  mov     r14, 0CBF29CE484222325h
0x1800181eb  add     r8, r8
0x1800181ee  jz      short loc_18001820D
0x1800181f0  movzx   eax, byte ptr [rdx+rcx]
0x1800181f4  xor     r14, rax
0x1800181f7  mov     r9, 100000001B3h
0x180018201  imul    r14, r9
0x180018205  inc     rcx
0x180018208  cmp     rcx, r8
0x18001820b  jb      short loc_1800181F0
0x18001820d  mov     r9, r14
0x180018210  mov     r8, rdi
0x180018213  lea     rdx, [rsp+78h+var_48]
0x180018218  mov     rcx, rbp
0x18001821b  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180018220  mov     rax, qword ptr [rsp+78h+var_48+8]
0x180018225  test    rax, rax
0x180018228  jz      short loc_180018236
0x18001822a  mov     [rsi], rax
0x18001822d  mov     byte ptr [rsi+8], 0
0x180018231  jmp     loc_1800183DF
0x180018236  lea     r15, [rbp+8]
0x18001823a  mov     rax, 492492492492492h
0x180018244  cmp     [r15+8], rax
0x180018248  jnz     short loc_180018258
0x18001824a  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180018251  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180018258  mov     [rsp+78h+var_58], r15
0x18001825d  mov     [rsp+78h+var_50], 0
0x180018266  mov     ecx, 38h ; '8'; Size
0x18001826b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018270  mov     rbx, rax
0x180018273  mov     [rsp+78h+var_50], rax
0x180018278  mov     rdx, rdi
0x18001827b  lea     rcx, [rax+10h]
0x18001827f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180018284  mov     qword ptr [rbx+30h], 0
0x18001828c  mov     rdi, [rbp+38h]
0x180018290  mov     rcx, [rbp+10h]
0x180018294  add     rcx, 1
0x180018298  xorps   xmm0, xmm0
0x18001829b  js      short loc_1800182A4
0x18001829d  cvtsi2ss xmm0, rcx
0x1800182a2  jmp     short loc_1800182B9
0x1800182a4  mov     rax, rcx
0x1800182a7  shr     rax, 1
0x1800182aa  and     ecx, 1
0x1800182ad  or      rax, rcx
0x1800182b0  cvtsi2ss xmm0, rax
0x1800182b5  addss   xmm0, xmm0
0x1800182b9  xorps   xmm2, xmm2
0x1800182bc  test    rdi, rdi
0x1800182bf  js      short loc_1800182C8
0x1800182c1  cvtsi2ss xmm2, rdi
0x1800182c6  jmp     short loc_1800182E0
0x1800182c8  mov     rcx, rdi
0x1800182cb  shr     rcx, 1
0x1800182ce  mov     rax, rdi
0x1800182d1  and     eax, 1
0x1800182d4  or      rcx, rax
0x1800182d7  cvtsi2ss xmm2, rcx
0x1800182dc  addss   xmm2, xmm2
0x1800182e0  movaps  xmm1, xmm0
0x1800182e3  divss   xmm1, xmm2
0x1800182e7  comiss  xmm1, dword ptr [rbp+0]
0x1800182eb  jbe     loc_180018376
0x1800182f1  divss   xmm0, dword ptr [rbp+0]; X
0x1800182f6  call    _o_ceilf_0
0x1800182fb  xor     ecx, ecx
0x1800182fd  movss   xmm1, cs:__real@5f000000
0x180018305  comiss  xmm0, xmm1
0x180018308  jb      short loc_180018320
0x18001830a  subss   xmm0, xmm1
0x18001830e  comiss  xmm0, xmm1
0x180018311  jnb     short loc_180018320
0x180018313  mov     rax, 8000000000000000h
0x18001831d  mov     rcx, rax
0x180018320  cvttss2si rax, xmm0
0x180018325  add     rax, rcx
0x180018328  mov     ecx, 8
0x18001832d  cmp     rax, rcx
0x180018330  cmova   rcx, rax
0x180018334  cmp     rdi, rcx
0x180018337  jnb     short loc_18001834E
0x180018339  cmp     rdi, 200h
0x180018340  jnb     short loc_18001834B
0x180018342  shl     rdi, 3
0x180018346  cmp     rdi, rcx
0x180018349  jnb     short loc_18001834E
0x18001834b  mov     rdi, rcx
0x18001834e  mov     rdx, rdi
0x180018351  mov     rcx, rbp
0x180018354  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Forced_rehash(unsigned __int64)
0x180018359  mov     r9, r14
0x18001835c  lea     r8, [rbx+10h]
0x180018360  lea     rdx, [rsp+78h+var_48]
0x180018365  mov     rcx, rbp
0x180018368  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18001836d  movups  xmm0, xmmword ptr [rax]
0x180018370  movdqu  [rsp+78h+var_48], xmm0
0x180018376  mov     [rsp+78h+var_50], 0
0x18001837f  mov     rdx, qword ptr [rsp+78h+var_48]
0x180018384  mov     r8, [rdx+8]
0x180018388  inc     qword ptr [rbp+10h]
0x18001838c  mov     [rbx], rdx
0x18001838f  mov     [rbx+8], r8
0x180018393  mov     [r8], rbx
0x180018396  mov     [rdx+8], rbx
0x18001839a  mov     rax, [rbp+30h]
0x18001839e  and     rax, r14
0x1800183a1  add     rax, rax
0x1800183a4  mov     rcx, [rbp+18h]
0x1800183a8  mov     r9, [rcx+rax*8]
0x1800183ac  cmp     r9, [r15]
0x1800183af  jnz     short loc_1800183B7
0x1800183b1  mov     [rcx+rax*8], rbx
0x1800183b5  jmp     short loc_1800183C9
0x1800183b7  cmp     r9, rdx
0x1800183ba  jnz     short loc_1800183C2
0x1800183bc  mov     [rcx+rax*8], rbx
0x1800183c0  jmp     short loc_1800183CE
0x1800183c2  cmp     [rcx+rax*8+8], r8
0x1800183c7  jnz     short loc_1800183CE
0x1800183c9  mov     [rcx+rax*8+8], rbx
0x1800183ce  mov     [rsi], rbx
0x1800183d1  mov     byte ptr [rsi+8], 1
0x1800183d5  lea     rcx, [rsp+78h+var_58]
0x1800183da  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>,void *>>>(void)
0x1800183df  mov     rax, rsi
0x1800183e2  add     rsp, 40h
0x1800183e6  pop     r15
0x1800183e8  pop     r14
0x1800183ea  pop     r13
0x1800183ec  pop     rdi
0x1800183ed  pop     rsi
0x1800183ee  pop     rbp
0x1800183ef  pop     rbx
0x1800183f0  retn
```
