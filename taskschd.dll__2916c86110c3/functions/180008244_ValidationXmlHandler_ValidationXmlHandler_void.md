# ValidationXmlHandler::~ValidationXmlHandler(void)

- ea: `0x180008244`
- end: `0x180008671`
- name: `??1ValidationXmlHandler@@QEAA@XZ`
- size: `1069`
- prototype: `void __fastcall(ValidationXmlHandler *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180007100`
- `0x18000a250`
- `0x180048ad4`
- `0x18004f3d0`
- `0x1800530c9`

## callees

- `0x180008244`
- `0x180008d30`
- `0x180009a30`
- `0x180009a78`
- `0x18000a30c`
- `0x18000b370`
- `0x18002b46c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180008446`
- `OLEAUT32!__imp_SysFreeString` at `0x18000846e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008499`
- `OLEAUT32!__imp_SysFreeString` at `0x1800084c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800084ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18000851a`
- `OLEAUT32!__imp_SysFreeString` at `0x180008545`
- `OLEAUT32!__imp_SysFreeString` at `0x180008570`
- `OLEAUT32!__imp_SysFreeString` at `0x18000859b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800085c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180008446`
- `OLEAUT32!__imp_SysFreeString` at `0x18000846e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008499`
- `OLEAUT32!__imp_SysFreeString` at `0x1800084c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800084ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18000851a`
- `OLEAUT32!__imp_SysFreeString` at `0x180008545`
- `OLEAUT32!__imp_SysFreeString` at `0x180008570`
- `OLEAUT32!__imp_SysFreeString` at `0x18000859b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800085c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ValidationXmlHandler::~ValidationXmlHandler(ValidationXmlHandler *this)
{
  void **v2; // rbx
  __int64 v3; // rbx
  __int64 v4; // rbx
  __int64 v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rbx
  void *v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // rbx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx

  v2 = (void **)((char *)this + 496);
  std::_Tree<std::_Tmap_traits<_bstr_t,void *,ValidationXmlHandler::stringless,std::allocator<std::pair<_bstr_t const,void *>>,0>>::_Erase(
    (char *)this + 496,
    *(_QWORD *)(*((_QWORD *)this + 62) + 8LL));
  *((_QWORD *)*v2 + 1) = *v2;
  *(_QWORD *)*v2 = *v2;
  *((_QWORD *)*v2 + 2) = *v2;
  v2[1] = 0;
  operator delete(*v2);
  v3 = *((_QWORD *)this + 60);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v3 )
      {
        SysFreeString(*(BSTR *)v3);
        *(_QWORD *)v3 = 0;
      }
      v15 = *(void **)(v3 + 8);
      if ( v15 )
      {
        operator delete(v15);
        *(_QWORD *)(v3 + 8) = 0;
      }
      operator delete((void *)v3);
    }
    *((_QWORD *)this + 60) = 0;
  }
  v4 = *((_QWORD *)this + 59);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v4 )
      {
        SysFreeString(*(BSTR *)v4);
        *(_QWORD *)v4 = 0;
      }
      v16 = *(void **)(v4 + 8);
      if ( v16 )
      {
        operator delete(v16);
        *(_QWORD *)(v4 + 8) = 0;
      }
      operator delete((void *)v4);
    }
    *((_QWORD *)this + 59) = 0;
  }
  v5 = *((_QWORD *)this + 58);
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v5 )
      {
        SysFreeString(*(BSTR *)v5);
        *(_QWORD *)v5 = 0;
      }
      v17 = *(void **)(v5 + 8);
      if ( v17 )
      {
        operator delete(v17);
        *(_QWORD *)(v5 + 8) = 0;
      }
      operator delete((void *)v5);
    }
    *((_QWORD *)this + 58) = 0;
  }
  v6 = *((_QWORD *)this + 57);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v6 )
      {
        SysFreeString(*(BSTR *)v6);
        *(_QWORD *)v6 = 0;
      }
      v18 = *(void **)(v6 + 8);
      if ( v18 )
      {
        operator delete(v18);
        *(_QWORD *)(v6 + 8) = 0;
      }
      operator delete((void *)v6);
    }
    *((_QWORD *)this + 57) = 0;
  }
  v7 = *((_QWORD *)this + 56);
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v7 )
      {
        SysFreeString(*(BSTR *)v7);
        *(_QWORD *)v7 = 0;
      }
      v19 = *(void **)(v7 + 8);
      if ( v19 )
      {
        operator delete(v19);
        *(_QWORD *)(v7 + 8) = 0;
      }
      operator delete((void *)v7);
    }
    *((_QWORD *)this + 56) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 44);
  if ( v8 )
    operator delete(v8);
  ValidationXmlHandler::CurrentTrigger::_unnamed_type_strings_::~_unnamed_type_strings_((ValidationXmlHandler *)((char *)this + 360));
  _bstr_t::_Free((ValidationXmlHandler *)((char *)this + 200));
  _bstr_t::_Free((ValidationXmlHandler *)((char *)this + 192));
  _bstr_t::_Free((ValidationXmlHandler *)((char *)this + 184));
  std::_Tree<std::_Tmap_traits<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>,0>>::~_Tree<std::_Tmap_traits<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>,0>>((char *)this + 168);
  _bstr_t::_Free((ValidationXmlHandler *)((char *)this + 160));
  _bstr_t::_Free((ValidationXmlHandler *)((char *)this + 144));
  _bstr_t::_Free((ValidationXmlHandler *)((char *)this + 120));
  v9 = *((_QWORD *)this + 12);
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v9 )
      {
        SysFreeString(*(BSTR *)v9);
        *(_QWORD *)v9 = 0;
      }
      v20 = *(void **)(v9 + 8);
      if ( v20 )
      {
        operator delete(v20);
        *(_QWORD *)(v9 + 8) = 0;
      }
      operator delete((void *)v9);
    }
    *((_QWORD *)this + 12) = 0;
  }
  v10 = *((_QWORD *)this + 11);
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v10 )
      {
        SysFreeString(*(BSTR *)v10);
        *(_QWORD *)v10 = 0;
      }
      v21 = *(void **)(v10 + 8);
      if ( v21 )
      {
        operator delete(v21);
        *(_QWORD *)(v10 + 8) = 0;
      }
      operator delete((void *)v10);
    }
    *((_QWORD *)this + 11) = 0;
  }
  v11 = *((_QWORD *)this + 10);
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v11 )
      {
        SysFreeString(*(BSTR *)v11);
        *(_QWORD *)v11 = 0;
      }
      v22 = *(void **)(v11 + 8);
      if ( v22 )
      {
        operator delete(v22);
        *(_QWORD *)(v11 + 8) = 0;
      }
      operator delete((void *)v11);
    }
    *((_QWORD *)this + 10) = 0;
  }
  v12 = *((_QWORD *)this + 9);
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v12 )
      {
        SysFreeString(*(BSTR *)v12);
        *(_QWORD *)v12 = 0;
      }
      v23 = *(void **)(v12 + 8);
      if ( v23 )
      {
        operator delete(v23);
        *(_QWORD *)(v12 + 8) = 0;
      }
      operator delete((void *)v12);
    }
    *((_QWORD *)this + 9) = 0;
  }
  wmi::AutoRef<RpcFolderSnapshot>::Release((char *)this + 40);
  v13 = *((_QWORD *)this + 3);
  if ( v13 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v13 + 16)) )
    {
      if ( *(_QWORD *)v13 )
      {
        SysFreeString(*(BSTR *)v13);
        *(_QWORD *)v13 = 0;
      }
      v14 = *(void **)(v13 + 8);
      if ( v14 )
      {
        operator delete(v14);
        *(_QWORD *)(v13 + 8) = 0;
      }
      operator delete((void *)v13);
    }
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180008244  push    rbx
0x180008246  push    rbp
0x180008247  push    rsi
0x180008248  push    rdi
0x180008249  sub     rsp, 28h
0x18000824d  mov     rdi, rcx
0x180008250  lea     rbx, [rcx+1F0h]
0x180008257  mov     rdx, [rbx]
0x18000825a  mov     rdx, [rdx+8]
0x18000825e  mov     rcx, rbx
0x180008261  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V_bstr_t@@PEAXUstringless@ValidationXmlHandler@@V?$allocator@U?$pair@$$CBV_bstr_t@@PEAX@std@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAX@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<_bstr_t,void *,ValidationXmlHandler::stringless,std::allocator<std::pair<_bstr_t const,void *>>,0>>::_Erase(std::_Tree_node<std::pair<_bstr_t const,void *>,void *> *)
0x180008266  mov     rax, [rbx]
0x180008269  mov     [rax+8], rax
0x18000826d  mov     rax, [rbx]
0x180008270  mov     [rax], rax
0x180008273  mov     rax, [rbx]
0x180008276  mov     [rax+10h], rax
0x18000827a  xor     esi, esi
0x18000827c  mov     [rbx+8], rsi
0x180008280  mov     rcx, [rbx]; void *
0x180008283  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008288  nop
0x180008289  mov     rbx, [rdi+1E0h]
0x180008290  or      ebp, 0FFFFFFFFh
0x180008293  test    rbx, rbx
0x180008296  jz      short loc_1800082AE
0x180008298  mov     eax, ebp
0x18000829a  lock xadd [rbx+10h], eax
0x18000829f  add     eax, ebp
0x1800082a1  jz      loc_180008466
0x1800082a7  mov     [rdi+1E0h], rsi
0x1800082ae  mov     rbx, [rdi+1D8h]
0x1800082b5  test    rbx, rbx
0x1800082b8  jz      short loc_1800082D0
0x1800082ba  mov     eax, ebp
0x1800082bc  lock xadd [rbx+10h], eax
0x1800082c1  add     eax, ebp
0x1800082c3  jz      loc_180008491
0x1800082c9  mov     [rdi+1D8h], rsi
0x1800082d0  mov     rbx, [rdi+1D0h]
0x1800082d7  test    rbx, rbx
0x1800082da  jz      short loc_1800082F2
0x1800082dc  mov     eax, ebp
0x1800082de  lock xadd [rbx+10h], eax
0x1800082e3  add     eax, ebp
0x1800082e5  jz      loc_1800084BC
0x1800082eb  mov     [rdi+1D0h], rsi
0x1800082f2  mov     rbx, [rdi+1C8h]
0x1800082f9  test    rbx, rbx
0x1800082fc  jz      short loc_180008314
0x1800082fe  mov     eax, ebp
0x180008300  lock xadd [rbx+10h], eax
0x180008305  add     eax, ebp
0x180008307  jz      loc_1800084E7
0x18000830d  mov     [rdi+1C8h], rsi
0x180008314  mov     rbx, [rdi+1C0h]
0x18000831b  test    rbx, rbx
0x18000831e  jz      short loc_180008336
0x180008320  mov     eax, ebp
0x180008322  lock xadd [rbx+10h], eax
0x180008327  add     eax, ebp
0x180008329  jz      loc_180008512
0x18000832f  mov     [rdi+1C0h], rsi
0x180008336  mov     rcx, [rdi+160h]; void *
0x18000833d  test    rcx, rcx
0x180008340  jz      short loc_180008347
0x180008342  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008347  lea     rcx, [rdi+168h]; this
0x18000834e  call    ??1_unnamed_type_strings_@CurrentTrigger@ValidationXmlHandler@@QEAA@XZ; ValidationXmlHandler::CurrentTrigger::_unnamed_type_strings_::~_unnamed_type_strings_(void)
0x180008353  lea     rcx, [rdi+0C8h]; this
0x18000835a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000835f  lea     rcx, [rdi+0C0h]; this
0x180008366  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000836b  lea     rcx, [rdi+0B8h]; this
0x180008372  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008377  lea     rcx, [rdi+0A8h]
0x18000837e  call    ??1?$_Tree@V?$_Tmap_traits@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>,0>>::~_Tree<std::_Tmap_traits<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>,0>>(void)
0x180008383  lea     rcx, [rdi+0A0h]; this
0x18000838a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000838f  lea     rcx, [rdi+90h]; this
0x180008396  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000839b  lea     rcx, [rdi+78h]; this
0x18000839f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800083a4  mov     rbx, [rdi+60h]
0x1800083a8  test    rbx, rbx
0x1800083ab  jz      short loc_1800083C0
0x1800083ad  mov     eax, ebp
0x1800083af  lock xadd [rbx+10h], eax
0x1800083b4  add     eax, ebp
0x1800083b6  jz      loc_18000853D
0x1800083bc  mov     [rdi+60h], rsi
0x1800083c0  mov     rbx, [rdi+58h]
0x1800083c4  test    rbx, rbx
0x1800083c7  jz      short loc_1800083DC
0x1800083c9  mov     eax, ebp
0x1800083cb  lock xadd [rbx+10h], eax
0x1800083d0  add     eax, ebp
0x1800083d2  jz      loc_180008568
0x1800083d8  mov     [rdi+58h], rsi
0x1800083dc  mov     rbx, [rdi+50h]
0x1800083e0  test    rbx, rbx
0x1800083e3  jz      short loc_1800083F8
0x1800083e5  mov     eax, ebp
0x1800083e7  lock xadd [rbx+10h], eax
0x1800083ec  add     eax, ebp
0x1800083ee  jz      loc_180008593
0x1800083f4  mov     [rdi+50h], rsi
0x1800083f8  mov     rbx, [rdi+48h]
0x1800083fc  test    rbx, rbx
0x1800083ff  jz      short loc_180008414
0x180008401  mov     eax, ebp
0x180008403  lock xadd [rbx+10h], eax
0x180008408  add     eax, ebp
0x18000840a  jz      loc_1800085BE
0x180008410  mov     [rdi+48h], rsi
0x180008414  lea     rcx, [rdi+28h]
0x180008418  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x18000841d  mov     rbx, [rdi+18h]
0x180008421  test    rbx, rbx
0x180008424  jz      short loc_180008435
0x180008426  mov     eax, ebp
0x180008428  lock xadd [rbx+10h], eax
0x18000842d  add     eax, ebp
0x18000842f  jz      short loc_18000843E
0x180008431  mov     [rdi+18h], rsi
0x180008435  add     rsp, 28h
0x180008439  pop     rdi
0x18000843a  pop     rsi
0x18000843b  pop     rbp
0x18000843c  pop     rbx
0x18000843d  retn
0x18000843e  mov     rcx, [rbx]; bstrString
0x180008441  test    rcx, rcx
0x180008444  jz      short loc_18000844F
0x180008446  call    cs:__imp_SysFreeString
0x18000844c  mov     [rbx], rsi
0x18000844f  mov     rcx, [rbx+8]; void *
0x180008453  test    rcx, rcx
0x180008456  jnz     loc_180008663
0x18000845c  mov     rcx, rbx; void *
0x18000845f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008464  jmp     short loc_180008431
0x180008466  mov     rcx, [rbx]; bstrString
0x180008469  test    rcx, rcx
0x18000846c  jz      short loc_180008477
0x18000846e  call    cs:__imp_SysFreeString
0x180008474  mov     [rbx], rsi
0x180008477  mov     rcx, [rbx+8]; void *
0x18000847b  test    rcx, rcx
0x18000847e  jnz     loc_1800085E5
0x180008484  mov     rcx, rbx; void *
0x180008487  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000848c  jmp     loc_1800082A7
0x180008491  mov     rcx, [rbx]; bstrString
0x180008494  test    rcx, rcx
0x180008497  jz      short loc_1800084A2
0x180008499  call    cs:__imp_SysFreeString
0x18000849f  mov     [rbx], rsi
0x1800084a2  mov     rcx, [rbx+8]; void *
0x1800084a6  test    rcx, rcx
0x1800084a9  jnz     loc_1800085F3
0x1800084af  mov     rcx, rbx; void *
0x1800084b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800084b7  jmp     loc_1800082C9
0x1800084bc  mov     rcx, [rbx]; bstrString
0x1800084bf  test    rcx, rcx
0x1800084c2  jz      short loc_1800084CD
0x1800084c4  call    cs:__imp_SysFreeString
0x1800084ca  mov     [rbx], rsi
0x1800084cd  mov     rcx, [rbx+8]; void *
0x1800084d1  test    rcx, rcx
0x1800084d4  jnz     loc_180008601
0x1800084da  mov     rcx, rbx; void *
0x1800084dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800084e2  jmp     loc_1800082EB
0x1800084e7  mov     rcx, [rbx]; bstrString
0x1800084ea  test    rcx, rcx
0x1800084ed  jz      short loc_1800084F8
0x1800084ef  call    cs:__imp_SysFreeString
0x1800084f5  mov     [rbx], rsi
0x1800084f8  mov     rcx, [rbx+8]; void *
0x1800084fc  test    rcx, rcx
0x1800084ff  jnz     loc_18000860F
0x180008505  mov     rcx, rbx; void *
0x180008508  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000850d  jmp     loc_18000830D
0x180008512  mov     rcx, [rbx]; bstrString
0x180008515  test    rcx, rcx
0x180008518  jz      short loc_180008523
0x18000851a  call    cs:__imp_SysFreeString
0x180008520  mov     [rbx], rsi
0x180008523  mov     rcx, [rbx+8]; void *
0x180008527  test    rcx, rcx
0x18000852a  jnz     loc_18000861D
0x180008530  mov     rcx, rbx; void *
0x180008533  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008538  jmp     loc_18000832F
0x18000853d  mov     rcx, [rbx]; bstrString
0x180008540  test    rcx, rcx
0x180008543  jz      short loc_18000854E
0x180008545  call    cs:__imp_SysFreeString
0x18000854b  mov     [rbx], rsi
0x18000854e  mov     rcx, [rbx+8]; void *
0x180008552  test    rcx, rcx
0x180008555  jnz     loc_18000862B
0x18000855b  mov     rcx, rbx; void *
0x18000855e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008563  jmp     loc_1800083BC
0x180008568  mov     rcx, [rbx]; bstrString
0x18000856b  test    rcx, rcx
0x18000856e  jz      short loc_180008579
0x180008570  call    cs:__imp_SysFreeString
0x180008576  mov     [rbx], rsi
0x180008579  mov     rcx, [rbx+8]; void *
0x18000857d  test    rcx, rcx
0x180008580  jnz     loc_180008639
0x180008586  mov     rcx, rbx; void *
0x180008589  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000858e  jmp     loc_1800083D8
0x180008593  mov     rcx, [rbx]; bstrString
0x180008596  test    rcx, rcx
0x180008599  jz      short loc_1800085A4
0x18000859b  call    cs:__imp_SysFreeString
0x1800085a1  mov     [rbx], rsi
0x1800085a4  mov     rcx, [rbx+8]; void *
0x1800085a8  test    rcx, rcx
0x1800085ab  jnz     loc_180008647
0x1800085b1  mov     rcx, rbx; void *
0x1800085b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800085b9  jmp     loc_1800083F4
0x1800085be  mov     rcx, [rbx]; bstrString
0x1800085c1  test    rcx, rcx
0x1800085c4  jz      short loc_1800085CF
0x1800085c6  call    cs:__imp_SysFreeString
0x1800085cc  mov     [rbx], rsi
0x1800085cf  mov     rcx, [rbx+8]; void *
0x1800085d3  test    rcx, rcx
0x1800085d6  jnz     short loc_180008655
0x1800085d8  mov     rcx, rbx; void *
0x1800085db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800085e0  jmp     loc_180008410
0x1800085e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800085ea  mov     [rbx+8], rsi
0x1800085ee  jmp     loc_180008484
0x1800085f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800085f8  mov     [rbx+8], rsi
0x1800085fc  jmp     loc_1800084AF
0x180008601  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008606  mov     [rbx+8], rsi
0x18000860a  jmp     loc_1800084DA
0x18000860f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008614  mov     [rbx+8], rsi
0x180008618  jmp     loc_180008505
0x18000861d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008622  mov     [rbx+8], rsi
0x180008626  jmp     loc_180008530
0x18000862b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008630  mov     [rbx+8], rsi
0x180008634  jmp     loc_18000855B
0x180008639  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000863e  mov     [rbx+8], rsi
0x180008642  jmp     loc_180008586
0x180008647  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000864c  mov     [rbx+8], rsi
0x180008650  jmp     loc_1800085B1
0x180008655  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000865a  mov     [rbx+8], rsi
0x18000865e  jmp     loc_1800085D8
0x180008663  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008668  mov     [rbx+8], rsi
0x18000866c  jmp     loc_18000845C
```
