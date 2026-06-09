# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Try_emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x180025dcc`
- end: `0x180026013`
- name: `??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `583`
- prototype: `__int64 __fastcall(float *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800227bc`

## callees

- `0x180003be4`
- `0x180003d44`
- `0x180018114`
- `0x180025dcc`
- `0x18002615c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180025e64`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180025e64`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Try_emplace<std::wstring,>(
        float *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // r8
  _QWORD *v7; // rdx
  __int64 v8; // rbp
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  _OWORD *v11; // rdi
  __int64 v12; // rcx
  float v13; // xmm0_4
  unsigned __int64 v14; // rbx
  float v15; // xmm2_4
  __int64 v16; // rcx
  float v17; // xmm0_4
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r9
  _OWORD v27[4]; // [rsp+20h] [rbp-48h] BYREF

  v6 = a3[2];
  if ( a3[3] <= 7u )
    v7 = a3;
  else
    v7 = (_QWORD *)*a3;
  v8 = 0xCBF29CE484222325uLL;
  v9 = 0;
  v10 = 2 * v6;
  if ( v10 )
  {
    do
      v8 = 0x100000001B3LL * (*((unsigned __int8 *)v7 + v9++) ^ (unsigned __int64)v8);
    while ( v9 < v10 );
  }
  std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(
    a1,
    v27,
    (__int64)a3,
    v8);
  if ( !*((_QWORD *)&v27[0] + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0x38E38E38E38E38ELL )
      std::_Xlength_error("unordered_map/set too long");
    v11 = operator new(0x48u);
    v11[1] = 0;
    *((_QWORD *)v11 + 4) = 0;
    *((_QWORD *)v11 + 5) = 0;
    v11[1] = *(_OWORD *)a3;
    v11[2] = *((_OWORD *)a3 + 1);
    a3[2] = 0;
    a3[3] = 7;
    *(_WORD *)a3 = 0;
    v11[3] = 0;
    *((_QWORD *)v11 + 8) = 0;
    v12 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v12 < 0 )
      v13 = (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1))
          + (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1));
    else
      v13 = (float)(int)v12;
    v14 = *((_QWORD *)a1 + 7);
    if ( (v14 & 0x8000000000000000uLL) != 0LL )
    {
      v16 = *((_QWORD *)a1 + 7) & 1LL | (v14 >> 1);
      v15 = (float)(int)v16 + (float)(int)v16;
    }
    else
    {
      v15 = (float)(int)v14;
    }
    if ( (float)(v13 / v15) > *a1 )
    {
      v17 = o_ceilf_0(v13 / *a1);
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
      if ( v14 < v20 )
      {
        if ( v14 >= 0x200 || (v14 *= 8LL, v14 < v20) )
          v14 = v20;
      }
      std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Forced_rehash(
        a1,
        v14);
      v27[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(
                            a1,
                            v27,
                            (__int64)(v11 + 1),
                            v8);
    }
    v21 = *(_QWORD *)&v27[0];
    v22 = *(_QWORD **)(*(_QWORD *)&v27[0] + 8LL);
    ++*((_QWORD *)a1 + 2);
    *(_QWORD *)v11 = v21;
    *((_QWORD *)v11 + 1) = v22;
    *v22 = v11;
    *(_QWORD *)(v21 + 8) = v11;
    v23 = *((_QWORD *)a1 + 3);
    v24 = 2 * (v8 & *((_QWORD *)a1 + 6));
    v25 = *(_QWORD *)(v23 + 16 * (v8 & *((_QWORD *)a1 + 6)));
    if ( v25 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v23 + 16 * (v8 & *((_QWORD *)a1 + 6))) = v11;
LABEL_32:
      *(_QWORD *)(v23 + 8 * v24 + 8) = v11;
      goto LABEL_33;
    }
    if ( v25 == v21 )
    {
      *(_QWORD *)(v23 + 16 * (v8 & *((_QWORD *)a1 + 6))) = v11;
    }
    else if ( *(_QWORD **)(v23 + 16 * (v8 & *((_QWORD *)a1 + 6)) + 8) == v22 )
    {
      goto LABEL_32;
    }
LABEL_33:
    *(_QWORD *)a2 = v11;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v27[0] + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x180025dcc  push    rbx
0x180025dce  push    rbp
0x180025dcf  push    rsi
0x180025dd0  push    rdi
0x180025dd1  push    r14
0x180025dd3  push    r15
0x180025dd5  sub     rsp, 38h
0x180025dd9  mov     rbx, r8
0x180025ddc  mov     r14, rdx
0x180025ddf  mov     rsi, rcx
0x180025de2  mov     r8, [r8+10h]
0x180025de6  cmp     qword ptr [rbx+18h], 7
0x180025deb  jbe     short loc_180025DF2
0x180025ded  mov     rdx, [rbx]
0x180025df0  jmp     short loc_180025DF5
0x180025df2  mov     rdx, rbx
0x180025df5  mov     rbp, 0CBF29CE484222325h
0x180025dff  xor     ecx, ecx
0x180025e01  add     r8, r8
0x180025e04  jz      short loc_180025E23
0x180025e06  movzx   eax, byte ptr [rdx+rcx]
0x180025e0a  xor     rbp, rax
0x180025e0d  mov     r9, 100000001B3h
0x180025e17  imul    rbp, r9
0x180025e1b  inc     rcx
0x180025e1e  cmp     rcx, r8
0x180025e21  jb      short loc_180025E06
0x180025e23  mov     r9, rbp
0x180025e26  mov     r8, rbx
0x180025e29  lea     rdx, [rsp+68h+var_48]
0x180025e2e  mov     rcx, rsi
0x180025e31  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180025e36  mov     rax, qword ptr [rsp+68h+var_48+8]
0x180025e3b  test    rax, rax
0x180025e3e  jz      short loc_180025E4D
0x180025e40  mov     [r14], rax
0x180025e43  mov     byte ptr [r14+8], 0
0x180025e48  jmp     loc_180026003
0x180025e4d  mov     rax, 38E38E38E38E38Eh
0x180025e57  cmp     [rsi+10h], rax
0x180025e5b  jnz     short loc_180025E6B
0x180025e5d  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180025e64  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180025e6b  mov     ecx, 48h ; 'H'; Size
0x180025e70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025e75  mov     rdi, rax
0x180025e78  lea     r15, [rax+10h]
0x180025e7c  xorps   xmm0, xmm0
0x180025e7f  movups  xmmword ptr [r15], xmm0
0x180025e83  mov     qword ptr [r15+10h], 0
0x180025e8b  mov     qword ptr [r15+18h], 0
0x180025e93  movups  xmm0, xmmword ptr [rbx]
0x180025e96  movups  xmmword ptr [r15], xmm0
0x180025e9a  movups  xmm1, xmmword ptr [rbx+10h]
0x180025e9e  movups  xmmword ptr [r15+10h], xmm1
0x180025ea3  mov     qword ptr [rbx+10h], 0
0x180025eab  mov     qword ptr [rbx+18h], 7
0x180025eb3  xor     eax, eax
0x180025eb5  mov     [rbx], ax
0x180025eb8  xorps   xmm0, xmm0
0x180025ebb  movups  xmmword ptr [r15+20h], xmm0
0x180025ec0  mov     [r15+30h], rax
0x180025ec4  mov     rcx, [rsi+10h]
0x180025ec8  add     rcx, 1
0x180025ecc  xorps   xmm0, xmm0
0x180025ecf  js      short loc_180025ED8
0x180025ed1  cvtsi2ss xmm0, rcx
0x180025ed6  jmp     short loc_180025EED
0x180025ed8  mov     rax, rcx
0x180025edb  shr     rax, 1
0x180025ede  and     ecx, 1
0x180025ee1  or      rax, rcx
0x180025ee4  cvtsi2ss xmm0, rax
0x180025ee9  addss   xmm0, xmm0
0x180025eed  mov     rbx, [rsi+38h]
0x180025ef1  xorps   xmm2, xmm2
0x180025ef4  test    rbx, rbx
0x180025ef7  js      short loc_180025F00
0x180025ef9  cvtsi2ss xmm2, rbx
0x180025efe  jmp     short loc_180025F18
0x180025f00  mov     rcx, rbx
0x180025f03  shr     rcx, 1
0x180025f06  mov     rax, rbx
0x180025f09  and     eax, 1
0x180025f0c  or      rcx, rax
0x180025f0f  cvtsi2ss xmm2, rcx
0x180025f14  addss   xmm2, xmm2
0x180025f18  movaps  xmm1, xmm0
0x180025f1b  divss   xmm1, xmm2
0x180025f1f  comiss  xmm1, dword ptr [rsi]
0x180025f22  jbe     loc_180025FAB
0x180025f28  divss   xmm0, dword ptr [rsi]; X
0x180025f2c  call    _o_ceilf_0
0x180025f31  xor     ecx, ecx
0x180025f33  movss   xmm1, cs:__real@5f000000
0x180025f3b  comiss  xmm0, xmm1
0x180025f3e  jb      short loc_180025F56
0x180025f40  subss   xmm0, xmm1
0x180025f44  comiss  xmm0, xmm1
0x180025f47  jnb     short loc_180025F56
0x180025f49  mov     rax, 8000000000000000h
0x180025f53  mov     rcx, rax
0x180025f56  cvttss2si rax, xmm0
0x180025f5b  add     rax, rcx
0x180025f5e  mov     ecx, 8
0x180025f63  cmp     rax, rcx
0x180025f66  cmova   rcx, rax
0x180025f6a  cmp     rbx, rcx
0x180025f6d  jnb     short loc_180025F84
0x180025f6f  cmp     rbx, 200h
0x180025f76  jnb     short loc_180025F81
0x180025f78  shl     rbx, 3
0x180025f7c  cmp     rbx, rcx
0x180025f7f  jnb     short loc_180025F84
0x180025f81  mov     rbx, rcx
0x180025f84  mov     rdx, rbx
0x180025f87  mov     rcx, rsi
0x180025f8a  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Forced_rehash(unsigned __int64)
0x180025f8f  mov     r9, rbp
0x180025f92  mov     r8, r15
0x180025f95  lea     rdx, [rsp+68h+var_48]
0x180025f9a  mov     rcx, rsi
0x180025f9d  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180025fa2  movups  xmm0, xmmword ptr [rax]
0x180025fa5  movdqu  [rsp+68h+var_48], xmm0
0x180025fab  mov     rdx, qword ptr [rsp+68h+var_48]
0x180025fb0  mov     r8, [rdx+8]
0x180025fb4  inc     qword ptr [rsi+10h]
0x180025fb8  mov     [rdi], rdx
0x180025fbb  mov     [rdi+8], r8
0x180025fbf  mov     [r8], rdi
0x180025fc2  mov     [rdx+8], rdi
0x180025fc6  mov     rcx, [rsi+18h]
0x180025fca  mov     rax, [rsi+30h]
0x180025fce  and     rax, rbp
0x180025fd1  add     rax, rax
0x180025fd4  mov     r9, [rcx+rax*8]
0x180025fd8  cmp     r9, [rsi+8]
0x180025fdc  jnz     short loc_180025FE4
0x180025fde  mov     [rcx+rax*8], rdi
0x180025fe2  jmp     short loc_180025FF6
0x180025fe4  cmp     r9, rdx
0x180025fe7  jnz     short loc_180025FEF
0x180025fe9  mov     [rcx+rax*8], rdi
0x180025fed  jmp     short loc_180025FFB
0x180025fef  cmp     [rcx+rax*8+8], r8
0x180025ff4  jnz     short loc_180025FFB
0x180025ff6  mov     [rcx+rax*8+8], rdi
0x180025ffb  mov     [r14], rdi
0x180025ffe  mov     byte ptr [r14+8], 1
0x180026003  mov     rax, r14
0x180026006  add     rsp, 38h
0x18002600a  pop     r15
0x18002600c  pop     r14
0x18002600e  pop     rdi
0x18002600f  pop     rsi
0x180026010  pop     rbp
0x180026011  pop     rbx
0x180026012  retn
```
