# GetRemovedProducts(int,ulong *,__MIDL_SecurityCenter_0001 * *)

- ea: `0x180028e9c`
- end: `0x18002914f`
- name: `?GetRemovedProducts@@YAJHPEAKPEAPEAU__MIDL_SecurityCenter_0001@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(int, unsigned int *, struct __MIDL_SecurityCenter_0001 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180033540`
- `0x180033550`

## callees

- `0x180002db0`
- `0x180022130`
- `0x180027e00`
- `0x180028e9c`
- `0x180029158`
- `0x180030e24`
- `0x180032508`
- `0x18003734c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028f11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028fbe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028feb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028f11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028fbe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028feb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800290b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800290d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800290f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800290b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800290d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800290f9`

## pseudocode

```c
__int64 __fastcall GetRemovedProducts(int a1, unsigned int *a2, struct __MIDL_SecurityCenter_0001 **a3)
{
  __int64 *v4; // rdx
  __int64 v6; // rax
  unsigned int v7; // edi
  CThirdPartyManager *v8; // rcx
  _QWORD *v9; // rbp
  __int64 v10; // r12
  _QWORD *v11; // rbx
  bool v12; // cf
  const unsigned __int16 *v13; // rsi
  const unsigned __int16 *v14; // rdx
  LPVOID v15; // rax
  LPVOID v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // r8
  _QWORD *i; // rax
  unsigned int v20; // r15d
  __int64 v21; // r14
  void *v22; // r8
  void *v23; // r8
  _QWORD *v25; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v26; // [rsp+28h] [rbp-40h]
  int v28; // [rsp+78h] [rbp+10h] BYREF

  v4 = &g_UpgradableProducts;
  if ( !a1 )
    v4 = &g_RemovedButNotUpgradableProducts;
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(
    &v25,
    v4);
  if ( a2 && a3 )
  {
    v6 = v26;
    v7 = 0;
    *a2 = 0;
    *a3 = 0;
    if ( (_DWORD)v6 )
    {
      v9 = HeapAlloc(g_hHeap, 8u, 80 * v6);
      if ( v9 )
      {
        v10 = 0;
        v11 = (_QWORD *)*v25;
        while ( v11 != v25 )
        {
          v12 = v11[7] < 8u;
          v13 = (const unsigned __int16 *)(v11 + 4);
          v28 = 0;
          if ( v12 )
            v14 = (const unsigned __int16 *)(v11 + 4);
          else
            v14 = *(const unsigned __int16 **)v13;
          CThirdPartyManager::IsRegisteredProduct(v8, v14, &v28);
          if ( v28 )
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              if ( v11[7] >= 8u )
                v13 = *(const unsigned __int16 **)v13;
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v13);
            }
          }
          else
          {
            v15 = HeapAlloc(g_hHeap, 8u, 0x208u);
            v9[10 * v10 + 2] = v15;
            if ( !v15 || (v16 = HeapAlloc(g_hHeap, 8u, 0x208u), (v9[10 * v10 + 1] = v16) == 0) )
            {
              v7 = 14;
              goto LABEL_38;
            }
            if ( v11[7] >= 8u )
              v13 = *(const unsigned __int16 **)v13;
            v17 = StringCchCopyW((unsigned __int16 *)v9[10 * v10 + 2], 0x104u, v13);
            if ( v17 < 0 )
              goto LABEL_36;
            v18 = (const unsigned __int16 *)(v11 + 8);
            if ( v11[11] >= 8u )
              v18 = *(const unsigned __int16 **)v18;
            v17 = StringCchCopyW((unsigned __int16 *)v9[10 * v10 + 1], 0x104u, v18);
            if ( v17 < 0 )
            {
LABEL_36:
              v7 = (unsigned __int16)v17;
LABEL_38:
              v20 = 0;
              if ( (_DWORD)v10 )
              {
                v21 = 0;
                do
                {
                  v22 = (void *)v9[10 * v21 + 1];
                  if ( v22 )
                  {
                    HeapFree(g_hHeap, 0, v22);
                    v9[10 * v21 + 1] = 0;
                  }
                  v23 = (void *)v9[10 * v21 + 2];
                  if ( v23 )
                  {
                    HeapFree(g_hHeap, 0, v23);
                    v9[10 * v21 + 2] = 0;
                  }
                  ++v20;
                  ++v21;
                }
                while ( v20 < (unsigned int)v10 );
              }
              HeapFree(g_hHeap, 0, v9);
              goto LABEL_48;
            }
            v10 = (unsigned int)(v10 + 1);
          }
          if ( !*((_BYTE *)v11 + 25) )
          {
            v8 = (CThirdPartyManager *)v11[2];
            if ( *((_BYTE *)v8 + 25) )
            {
              for ( i = (_QWORD *)v11[1]; !*((_BYTE *)i + 25) && v11 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
                v11 = i;
            }
            else
            {
              i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min(v8);
            }
            v11 = i;
          }
        }
        *a3 = (struct __MIDL_SecurityCenter_0001 *)v9;
        *a2 = v10;
        if ( !a1 )
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(&g_RemovedButNotUpgradableProducts);
      }
      else
      {
        v7 = 14;
      }
    }
LABEL_48:
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v25);
    return v7;
  }
  else
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v25);
    return 87;
  }
}

```

## disassembly

```asm
0x180028e9c  mov     [rsp+arg_10], rbx
0x180028ea1  mov     [rsp+arg_0], ecx
0x180028ea5  push    rbp
0x180028ea6  push    rsi
0x180028ea7  push    rdi
0x180028ea8  push    r12
0x180028eaa  push    r13
0x180028eac  push    r14
0x180028eae  push    r15
0x180028eb0  sub     rsp, 30h
0x180028eb4  mov     r13, rdx
0x180028eb7  lea     r14, ?g_RemovedButNotUpgradableProducts@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> g_RemovedButNotUpgradableProducts
0x180028ebe  test    ecx, ecx
0x180028ec0  lea     rdx, ?g_UpgradableProducts@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> g_UpgradableProducts
0x180028ec7  lea     rcx, [rsp+68h+var_48]
0x180028ecc  mov     r15, r8
0x180028ecf  cmovz   rdx, r14
0x180028ed3  call    ??0?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>> const &,std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x180028ed8  test    r13, r13
0x180028edb  jz      loc_180029128
0x180028ee1  test    r15, r15
0x180028ee4  jz      loc_180029128
0x180028eea  mov     eax, [rsp+68h+var_40]
0x180028eee  xor     edi, edi
0x180028ef0  mov     [r13+0], edi
0x180028ef4  mov     [r15], rdi
0x180028ef7  test    eax, eax
0x180028ef9  jz      loc_18002911A
0x180028eff  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x180028f06  lea     r8, [rax+rax*4]
0x180028f0a  shl     r8, 4; dwBytes
0x180028f0e  lea     edx, [rdi+8]; dwFlags
0x180028f11  call    cs:__imp_HeapAlloc
0x180028f17  mov     rbp, rax
0x180028f1a  test    rax, rax
0x180028f1d  jnz     short loc_180028F27
0x180028f1f  lea     edi, [rax+0Eh]
0x180028f22  jmp     loc_18002911A
0x180028f27  mov     rbx, [rsp+68h+var_48]
0x180028f2c  xor     r12d, r12d
0x180028f2f  mov     rbx, [rbx]
0x180028f32  cmp     rbx, [rsp+68h+var_48]
0x180028f37  jz      loc_180029101
0x180028f3d  cmp     qword ptr [rbx+38h], 8
0x180028f42  lea     rsi, [rbx+20h]
0x180028f46  mov     [rsp+68h+arg_8], edi
0x180028f4a  jb      short loc_180028F51
0x180028f4c  mov     rdx, [rsi]
0x180028f4f  jmp     short loc_180028F54
0x180028f51  mov     rdx, rsi; unsigned __int16 *
0x180028f54  lea     r8, [rsp+68h+arg_8]; int *
0x180028f59  call    ?IsRegisteredProduct@CThirdPartyManager@@QEAAJPEBGAEAH@Z; CThirdPartyManager::IsRegisteredProduct(ushort const *,int &)
0x180028f5e  cmp     [rsp+68h+arg_8], edi
0x180028f62  jz      short loc_180028FAC
0x180028f64  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f6b  lea     rax, WPP_GLOBAL_Control
0x180028f72  cmp     rcx, rax
0x180028f75  jz      loc_180029043
0x180028f7b  test    byte ptr [rcx+1Ch], 4
0x180028f7f  jz      loc_180029043
0x180028f85  cmp     qword ptr [rbx+38h], 8
0x180028f8a  jb      short loc_180028F8F
0x180028f8c  mov     rsi, [rsi]
0x180028f8f  mov     rcx, [rcx+10h]
0x180028f93  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180028f9a  mov     edx, 9Bh
0x180028f9f  mov     r9, rsi
0x180028fa2  call    WPP_SF_S
0x180028fa7  jmp     loc_180029043
0x180028fac  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x180028fb3  mov     edx, 8; dwFlags
0x180028fb8  mov     r8d, 208h; dwBytes
0x180028fbe  call    cs:__imp_HeapAlloc
0x180028fc4  lea     r14, [r12+r12*4]
0x180028fc8  add     r14, r14
0x180028fcb  mov     [rbp+r14*8+10h], rax
0x180028fd0  test    rax, rax
0x180028fd3  jz      loc_180029084
0x180028fd9  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x180028fe0  mov     edx, 8; dwFlags
0x180028fe5  mov     r8d, 208h; dwBytes
0x180028feb  call    cs:__imp_HeapAlloc
0x180028ff1  mov     [rbp+r14*8+8], rax
0x180028ff6  test    rax, rax
0x180028ff9  jz      loc_180029084
0x180028fff  cmp     qword ptr [rbx+38h], 8
0x180029004  jb      short loc_180029009
0x180029006  mov     rsi, [rsi]
0x180029009  mov     rcx, [rbp+r14*8+10h]; unsigned __int16 *
0x18002900e  mov     r8, rsi; unsigned __int16 *
0x180029011  mov     edx, 104h; unsigned __int64
0x180029016  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002901b  test    eax, eax
0x18002901d  js      short loc_18002907F
0x18002901f  cmp     qword ptr [rbx+58h], 8
0x180029024  lea     r8, [rbx+40h]
0x180029028  jb      short loc_18002902D
0x18002902a  mov     r8, [r8]; unsigned __int16 *
0x18002902d  mov     rcx, [rbp+r14*8+8]; unsigned __int16 *
0x180029032  mov     edx, 104h; unsigned __int64
0x180029037  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002903c  test    eax, eax
0x18002903e  js      short loc_18002907F
0x180029040  inc     r12d
0x180029043  cmp     [rbx+19h], dil
0x180029047  jnz     loc_180028F32
0x18002904d  mov     rcx, [rbx+10h]
0x180029051  cmp     [rcx+19h], dil
0x180029055  jnz     short loc_18002905E
0x180029057  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Min(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x18002905c  jmp     short loc_180029077
0x18002905e  mov     rax, [rbx+8]
0x180029062  jmp     short loc_180029071
0x180029064  cmp     rbx, [rax+10h]
0x180029068  jnz     short loc_180029077
0x18002906a  mov     rbx, rax
0x18002906d  mov     rax, [rax+8]
0x180029071  cmp     [rax+19h], dil
0x180029075  jz      short loc_180029064
0x180029077  mov     rbx, rax
0x18002907a  jmp     loc_180028F32
0x18002907f  movzx   edi, ax
0x180029082  jmp     short loc_180029089
0x180029084  mov     edi, 0Eh
0x180029089  xor     r15d, r15d
0x18002908c  mov     rbx, rbp
0x18002908f  test    r12d, r12d
0x180029092  jz      short loc_1800290ED
0x180029094  xor     r14d, r14d
0x180029097  lea     rsi, [r14+r14*4]
0x18002909b  add     rsi, rsi
0x18002909e  mov     r8, [rbx+rsi*8+8]; lpMem
0x1800290a3  test    r8, r8
0x1800290a6  jz      short loc_1800290C0
0x1800290a8  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1800290af  xor     edx, edx; dwFlags
0x1800290b1  call    cs:__imp_HeapFree
0x1800290b7  mov     qword ptr [rbx+rsi*8+8], 0
0x1800290c0  mov     r8, [rbx+rsi*8+10h]; lpMem
0x1800290c5  test    r8, r8
0x1800290c8  jz      short loc_1800290E2
0x1800290ca  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1800290d1  xor     edx, edx; dwFlags
0x1800290d3  call    cs:__imp_HeapFree
0x1800290d9  mov     qword ptr [rbx+rsi*8+10h], 0
0x1800290e2  inc     r15d
0x1800290e5  inc     r14
0x1800290e8  cmp     r15d, r12d
0x1800290eb  jb      short loc_180029097
0x1800290ed  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1800290f4  mov     r8, rbp; lpMem
0x1800290f7  xor     edx, edx; dwFlags
0x1800290f9  call    cs:__imp_HeapFree
0x1800290ff  jmp     short loc_18002911A
0x180029101  mov     [r15], rbp
0x180029104  mov     [r13+0], r12d
0x180029108  cmp     [rsp+68h+arg_0], edi
0x18002910c  jnz     short loc_18002911A
0x18002910e  lea     rcx, ?g_RemovedButNotUpgradableProducts@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@A; std::map<std::wstring,std::wstring> g_RemovedButNotUpgradableProducts
0x180029115  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(void)
0x18002911a  lea     rcx, [rsp+68h+var_48]
0x18002911f  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180029124  mov     eax, edi
0x180029126  jmp     short loc_180029137
0x180029128  lea     rcx, [rsp+68h+var_48]
0x18002912d  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180029132  mov     eax, 57h ; 'W'
0x180029137  mov     rbx, [rsp+68h+arg_10]
0x18002913f  add     rsp, 30h
0x180029143  pop     r15
0x180029145  pop     r14
0x180029147  pop     r13
0x180029149  pop     r12
0x18002914b  pop     rdi
0x18002914c  pop     rsi
0x18002914d  pop     rbp
0x18002914e  retn
```
