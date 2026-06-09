# MANPARSE_INFO::FillEventMapInformation(MAPLIST_ENTRY *,std::unique_ptr<_EVENT_MAP_INFO,HeapFreeDelete> &,ulong &)

- ea: `0x180036320`
- end: `0x180036682`
- name: `?FillEventMapInformation@MANPARSE_INFO@@AEAAXPEAVMAPLIST_ENTRY@@AEAV?$unique_ptr@U_EVENT_MAP_INFO@@UHeapFreeDelete@@@std@@AEAK@Z`
- size: `866`
- prototype: `unsigned __int64 __fastcall(__int64, __int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180037dec`

## callees

- `0x180001084`
- `0x18001e09c`
- `0x18001e284`
- `0x18002149c`
- `0x180023b05`
- `0x180024a60`
- `0x18002cbb4`
- `0x18002fc8c`
- `0x180036320`
- `0x180037138`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036493`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036493`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036482`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036482`

## pseudocode

```c
unsigned __int64 __fastcall MANPARSE_INFO::FillEventMapInformation(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int *a4)
{
  __int64 v6; // rsi
  __int64 v7; // rcx
  unsigned __int64 v8; // rbx
  __int64 v9; // r14
  __int64 v10; // rdx
  STRING_ENTRY *v11; // rcx
  const wchar_t *TranslationValue; // rax
  __int64 v13; // r8
  __int64 v14; // r15
  __int64 v15; // rax
  __int64 v16; // rsi
  unsigned __int64 v17; // r13
  SIZE_T v18; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v20; // rax
  _DWORD *v21; // rdx
  _DWORD *v22; // rbx
  __int64 v23; // r14
  _QWORD *v24; // rdx
  size_t v25; // r8
  size_t v26; // rsi
  unsigned int *v27; // rcx
  unsigned __int64 result; // rax
  __int64 v29; // r8
  _QWORD *v30; // rdx
  size_t v31; // r8
  size_t v32; // rdi
  unsigned int v33; // r12d
  __int64 v34; // rsi
  char *v35; // rax
  char *v36; // rdx
  size_t v37; // r8
  size_t v38; // r14
  __int64 v39; // r8
  _QWORD *v40; // rdx
  size_t v41; // r8
  STRING_TRANSLATION *v42[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v43; // [rsp+30h] [rbp-28h]
  _QWORD pExceptionObject[4]; // [rsp+38h] [rbp-20h] BYREF

  v6 = 0;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  if ( (__int64)(*(_QWORD *)(a2 + 112) - *(_QWORD *)(a2 + 104)) >> 3 )
    std::vector<MAP_INFO>::_Resize_reallocate<std::_Value_init_tag>(v42);
  v7 = *(_QWORD *)(a2 + 104);
  if ( (*(_QWORD *)(a2 + 112) - v7) >> 3 )
  {
    v8 = 0;
    v9 = 0;
    do
    {
      v10 = *(_QWORD *)(v7 + 8 * v8);
      v11 = *(STRING_ENTRY **)(v10 + 144);
      if ( v11 )
      {
        TranslationValue = STRING_ENTRY::FirstTranslationValue(v11);
        v13 = -1;
        do
          ++v13;
        while ( TranslationValue[v13] );
        std::wstring::_Assign<wchar_t>((char *)v42[0] + v9, TranslationValue, v13);
      }
      else
      {
        std::wstring::operator=((char *)v42[0] + v9, v10 + 104);
      }
      v14 = *((_QWORD *)v42[0] + 9 * v8 + 2);
      v15 = *(_QWORD *)(*(_QWORD *)(a2 + 104) + 8 * v8);
      if ( *(_QWORD *)(v15 + 88) )
      {
        std::wstring::operator=((char *)v42[0] + 72 * v8 + 32, v15 + 72);
        v16 = v6 + 2 * (v14 + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 104) + 8 * v8) + 88LL)) + 2;
      }
      else
      {
        *(_DWORD *)((char *)v42[0] + v9 + 64) = *(_DWORD *)(v15 + 64);
        v16 = v6 + 2 * v14;
      }
      v6 = v16 + 2;
      ++v8;
      v7 = *(_QWORD *)(a2 + 104);
      v9 += 72;
    }
    while ( v8 < (*(_QWORD *)(a2 + 112) - v7) >> 3 );
  }
  v17 = 0x8E38E38E38E38E39uLL * ((v42[1] - v42[0]) >> 3);
  v18 = v6 + 2 * (*(_QWORD *)(a2 + 48) + *(_QWORD *)(a2 + 80) + 14LL + 4LL * (unsigned int)(v17 - 1));
  *a4 = v18;
  ProcessHeap = GetProcessHeap();
  v20 = HeapAlloc(ProcessHeap, 8u, v18);
  v21 = (_DWORD *)*a3;
  *a3 = v20;
  if ( v21 )
    HeapFreeDelete::operator()<_EVENT_MAP_INFO>();
  v22 = (_DWORD *)*a3;
  if ( !*a3 )
  {
    pExceptionObject[2] = 0;
    pExceptionObject[1] = "bad allocation";
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  v23 = 8LL * (unsigned int)(v17 - 1) + 24;
  if ( !(_DWORD)v17 )
    v23 = 24;
  v22[1] = *(_DWORD *)(a2 + 96);
  v22[2] = v17;
  v24 = (_QWORD *)(a2 + 32);
  if ( *(_QWORD *)(a2 + 56) > 7u )
    v24 = (_QWORD *)*v24;
  v25 = 2LL * *(_QWORD *)(a2 + 48) + 2;
  v26 = v25 + v23;
  v27 = a4;
  result = *a4;
  if ( v25 + v23 <= result )
  {
    result = (unsigned __int64)memcpy_0((char *)v22 + v23, v24, v25);
    v27 = a4;
  }
  *v22 = v23;
  v29 = *(_QWORD *)(a2 + 80);
  if ( v29 )
  {
    v30 = (_QWORD *)(a2 + 64);
    if ( *(_QWORD *)(a2 + 88) > 7u )
      v30 = (_QWORD *)*v30;
    v31 = 2 * v29 + 2;
    v32 = v31 + v26;
    result = *v27;
    if ( v31 + v26 <= result )
    {
      result = (unsigned __int64)memcpy_0((char *)v22 + v26, v30, v31);
      v27 = a4;
    }
    v22[3] = v26;
  }
  else
  {
    v32 = v26;
    v22[3] = 0;
  }
  v33 = 0;
  if ( (_DWORD)v17 )
  {
    v34 = 0;
    do
    {
      v35 = (char *)v42[0] + 72 * v34;
      if ( *((_QWORD *)v35 + 3) <= 7u )
        v36 = (char *)v42[0] + 72 * v34;
      else
        v36 = *(char **)v35;
      v37 = 2LL * *((_QWORD *)v35 + 2) + 2;
      v38 = v37 + v32;
      if ( v37 + v32 <= *v27 )
      {
        memcpy_0((char *)v22 + v32, v36, v37);
        v27 = a4;
      }
      v22[2 * v34 + 4] = v32;
      result = (unsigned __int64)v42[0];
      if ( v22[1] == 4 && (v39 = *((_QWORD *)v42[0] + 9 * v34 + 6)) != 0 )
      {
        v40 = (_QWORD *)((char *)v42[0] + 72 * v34 + 32);
        if ( v40[3] > 7u )
          v40 = (_QWORD *)*v40;
        v41 = 2 * v39 + 2;
        v32 = v41 + v38;
        result = *v27;
        if ( v41 + v38 <= result )
        {
          result = (unsigned __int64)memcpy_0((char *)v22 + v38, v40, v41);
          v27 = a4;
        }
      }
      else
      {
        v32 = v38;
        LODWORD(v38) = *((_DWORD *)v42[0] + 18 * v34 + 16);
      }
      v22[2 * v34 + 5] = v38;
      ++v33;
      ++v34;
    }
    while ( v33 < (unsigned int)v17 );
  }
  if ( v42[0] )
  {
    std::_Destroy_range<std::allocator<MAP_INFO>>(v42[0]);
    return std::_Deallocate<16>(v42[0], 8 * ((signed __int64)(v43 - (unsigned __int64)v42[0]) >> 3));
  }
  return result;
}

```

## disassembly

```asm
0x180036320  mov     [rsp-40h+arg_18], r9
0x180036325  push    rbp
0x180036326  push    rbx
0x180036327  push    rsi
0x180036328  push    rdi
0x180036329  push    r12
0x18003632b  push    r13
0x18003632d  push    r14
0x18003632f  push    r15
0x180036331  mov     rbp, rsp
0x180036334  sub     rsp, 58h
0x180036338  mov     r12, r8
0x18003633b  mov     rdi, rdx
0x18003633e  xor     r15d, r15d
0x180036341  mov     esi, r15d
0x180036344  xorps   xmm0, xmm0
0x180036347  movdqu  xmmword ptr [rbp+var_38], xmm0
0x18003634c  mov     [rbp+var_28], r15
0x180036350  mov     rdx, [rdx+70h]
0x180036354  sub     rdx, [rdi+68h]
0x180036358  sar     rdx, 3
0x18003635c  test    rdx, rdx
0x18003635f  jz      short loc_18003636A
0x180036361  lea     rcx, [rbp+var_38]
0x180036365  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UMAP_INFO@@V?$allocator@UMAP_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<MAP_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003636a  mov     rcx, [rdi+68h]
0x18003636e  mov     rax, [rdi+70h]
0x180036372  sub     rax, rcx
0x180036375  sar     rax, 3
0x180036379  test    rax, rax
0x18003637c  jz      loc_180036447
0x180036382  mov     rbx, r15
0x180036385  mov     r14, r15
0x180036388  mov     rdx, [rcx+rbx*8]
0x18003638c  mov     rcx, [rdx+90h]; this
0x180036393  test    rcx, rcx
0x180036396  jz      short loc_1800363BC
0x180036398  call    ?FirstTranslationValue@STRING_ENTRY@@QEBAPEB_WXZ; STRING_ENTRY::FirstTranslationValue(void)
0x18003639d  mov     rcx, [rbp+var_38]
0x1800363a1  add     rcx, r14
0x1800363a4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800363a8  inc     r8
0x1800363ab  cmp     [rax+r8*2], r15w
0x1800363b0  jnz     short loc_1800363A8
0x1800363b2  mov     rdx, rax
0x1800363b5  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800363ba  jmp     short loc_1800363CC
0x1800363bc  add     rdx, 68h ; 'h'
0x1800363c0  mov     rcx, [rbp+var_38]
0x1800363c4  add     rcx, r14
0x1800363c7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800363cc  lea     r8, [rbx+rbx*8]
0x1800363d0  mov     rcx, [rbp+var_38]
0x1800363d4  mov     r15, [rcx+r8*8+10h]
0x1800363d9  mov     rax, [rdi+68h]
0x1800363dd  mov     rax, [rax+rbx*8]
0x1800363e1  lea     rdx, [rax+48h]
0x1800363e5  cmp     qword ptr [rdx+10h], 0
0x1800363ea  jz      short loc_180036412
0x1800363ec  lea     rcx, [rcx+r8*8]
0x1800363f0  add     rcx, 20h ; ' '
0x1800363f4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800363f9  mov     rax, [rdi+68h]
0x1800363fd  mov     rcx, [rax+rbx*8]
0x180036401  mov     rax, [rcx+58h]
0x180036405  add     rax, r15
0x180036408  lea     rsi, [rsi+rax*2]
0x18003640c  add     rsi, 2
0x180036410  jmp     short loc_18003641E
0x180036412  mov     eax, [rax+40h]
0x180036415  mov     [r14+rcx+40h], eax
0x18003641a  lea     rsi, [rsi+r15*2]
0x18003641e  add     rsi, 2
0x180036422  inc     rbx
0x180036425  mov     rcx, [rdi+68h]
0x180036429  add     r14, 48h ; 'H'
0x18003642d  mov     rax, [rdi+70h]
0x180036431  sub     rax, rcx
0x180036434  sar     rax, 3
0x180036438  cmp     rbx, rax
0x18003643b  mov     r15d, 0
0x180036441  jb      loc_180036388
0x180036447  mov     r13, [rbp+var_38+8]
0x18003644b  sub     r13, [rbp+var_38]
0x18003644f  sar     r13, 3
0x180036453  mov     rax, 8E38E38E38E38E39h
0x18003645d  imul    r13, rax
0x180036461  lea     eax, [r13-1]
0x180036465  mov     r14d, eax
0x180036468  mov     rcx, [rdi+50h]
0x18003646c  add     rcx, 0Eh
0x180036470  lea     rcx, [rcx+rax*4]
0x180036474  add     rcx, [rdi+30h]
0x180036478  lea     rbx, [rsi+rcx*2]
0x18003647c  mov     rax, [rbp+arg_18]
0x180036480  mov     [rax], ebx
0x180036482  call    cs:__imp_GetProcessHeap
0x180036488  mov     rcx, rax; hHeap
0x18003648b  mov     r8, rbx; dwBytes
0x18003648e  mov     edx, 8; dwFlags
0x180036493  call    cs:__imp_HeapAlloc
0x180036499  mov     rdx, [r12]
0x18003649d  mov     [r12], rax
0x1800364a1  test    rdx, rdx
0x1800364a4  jz      short loc_1800364AB
0x1800364a6  call    ??$?RU_EVENT_MAP_INFO@@@HeapFreeDelete@@QEBAXPEAU_EVENT_MAP_INFO@@@Z; HeapFreeDelete::operator()<_EVENT_MAP_INFO>(_EVENT_MAP_INFO *)
0x1800364ab  mov     rbx, [r12]
0x1800364af  test    rbx, rbx
0x1800364b2  jz      loc_180036654
0x1800364b8  test    r13d, r13d
0x1800364bb  lea     r14, ds:18h[r14*8]
0x1800364c3  jnz     short loc_1800364CB
0x1800364c5  mov     r14d, 18h
0x1800364cb  mov     eax, [rdi+60h]
0x1800364ce  mov     [rbx+4], eax
0x1800364d1  mov     [rbx+8], r13d
0x1800364d5  lea     rdx, [rdi+20h]
0x1800364d9  cmp     qword ptr [rdx+18h], 7
0x1800364de  jbe     short loc_1800364E3
0x1800364e0  mov     rdx, [rdx]; Src
0x1800364e3  mov     rax, [rdi+30h]
0x1800364e7  lea     r8, ds:2[rax*2]; Size
0x1800364ef  lea     rsi, [r8+r14]
0x1800364f3  mov     rcx, [rbp+arg_18]
0x1800364f7  mov     eax, [rcx]
0x1800364f9  cmp     rsi, rax
0x1800364fc  ja      short loc_18003650B
0x1800364fe  lea     rcx, [r14+rbx]; void *
0x180036502  call    memcpy_0
0x180036507  mov     rcx, [rbp+arg_18]
0x18003650b  mov     [rbx], r14d
0x18003650e  mov     r8, [rdi+50h]
0x180036512  test    r8, r8
0x180036515  jz      short loc_18003654A
0x180036517  lea     rdx, [rdi+40h]
0x18003651b  cmp     qword ptr [rdx+18h], 7
0x180036520  jbe     short loc_180036525
0x180036522  mov     rdx, [rdx]; Src
0x180036525  lea     r8, ds:2[r8*2]; Size
0x18003652d  lea     rdi, [r8+rsi]
0x180036531  mov     eax, [rcx]
0x180036533  cmp     rdi, rax
0x180036536  ja      short loc_180036545
0x180036538  lea     rcx, [rsi+rbx]; void *
0x18003653c  call    memcpy_0
0x180036541  mov     rcx, [rbp+arg_18]
0x180036545  mov     [rbx+0Ch], esi
0x180036548  jmp     short loc_180036551
0x18003654a  mov     rdi, rsi
0x18003654d  mov     [rbx+0Ch], r15d
0x180036551  mov     r12d, r15d
0x180036554  test    r13d, r13d
0x180036557  jz      loc_180036607
0x18003655d  mov     rsi, r15
0x180036560  lea     r15, [rsi+rsi*8]
0x180036564  mov     rax, [rbp+var_38]
0x180036568  lea     rax, [rax+r15*8]
0x18003656c  cmp     qword ptr [rax+18h], 7
0x180036571  jbe     short loc_180036578
0x180036573  mov     rdx, [rax]
0x180036576  jmp     short loc_18003657B
0x180036578  mov     rdx, rax; Src
0x18003657b  mov     rax, [rax+10h]
0x18003657f  lea     r8, ds:2[rax*2]; Size
0x180036587  lea     r14, [r8+rdi]
0x18003658b  mov     eax, [rcx]
0x18003658d  cmp     r14, rax
0x180036590  ja      short loc_18003659F
0x180036592  lea     rcx, [rdi+rbx]; void *
0x180036596  call    memcpy_0
0x18003659b  mov     rcx, [rbp+arg_18]
0x18003659f  mov     [rbx+rsi*8+10h], edi
0x1800365a3  mov     rax, [rbp+var_38]
0x1800365a7  cmp     dword ptr [rbx+4], 4
0x1800365ab  jnz     short loc_1800365EB
0x1800365ad  mov     r8, [rax+r15*8+30h]
0x1800365b2  test    r8, r8
0x1800365b5  jz      short loc_1800365EB
0x1800365b7  lea     rdx, [rax+20h]
0x1800365bb  lea     rdx, [rdx+r15*8]
0x1800365bf  cmp     qword ptr [rdx+18h], 7
0x1800365c4  jbe     short loc_1800365C9
0x1800365c6  mov     rdx, [rdx]; Src
0x1800365c9  lea     r8, ds:2[r8*2]; Size
0x1800365d1  lea     rdi, [r8+r14]
0x1800365d5  mov     eax, [rcx]
0x1800365d7  cmp     rdi, rax
0x1800365da  ja      short loc_1800365F3
0x1800365dc  lea     rcx, [r14+rbx]; void *
0x1800365e0  call    memcpy_0
0x1800365e5  mov     rcx, [rbp+arg_18]
0x1800365e9  jmp     short loc_1800365F3
0x1800365eb  mov     rdi, r14
0x1800365ee  mov     r14d, [rax+r15*8+40h]
0x1800365f3  mov     [rbx+rsi*8+14h], r14d
0x1800365f8  inc     r12d
0x1800365fb  inc     rsi
0x1800365fe  cmp     r12d, r13d
0x180036601  jb      loc_180036560
0x180036607  mov     rcx, [rbp+var_38]; this
0x18003660b  test    rcx, rcx
0x18003660e  jz      short loc_180036643
0x180036610  mov     rdx, [rbp+var_38+8]
0x180036614  call    ??$_Destroy_range@V?$allocator@UMAP_INFO@@@std@@@std@@YAXPEAUMAP_INFO@@QEAU1@AEAV?$allocator@UMAP_INFO@@@0@@Z; std::_Destroy_range<std::allocator<MAP_INFO>>(MAP_INFO *,MAP_INFO * const,std::allocator<MAP_INFO> &)
0x180036619  mov     rcx, [rbp+var_38]
0x18003661d  mov     rax, [rbp+var_28]
0x180036621  sub     rax, rcx
0x180036624  sar     rax, 3
0x180036628  mov     rdx, 8E38E38E38E38E39h
0x180036632  imul    rax, rdx
0x180036636  lea     rdx, [rax+rax*8]
0x18003663a  shl     rdx, 3
0x18003663e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180036643  add     rsp, 58h
0x180036647  pop     r15
0x180036649  pop     r14
0x18003664b  pop     r13
0x18003664d  pop     r12
0x18003664f  pop     rdi
0x180036650  pop     rsi
0x180036651  pop     rbx
0x180036652  pop     rbp
0x180036653  retn
0x180036654  xorps   xmm0, xmm0
0x180036657  movups  [rbp+var_18], xmm0
0x18003665b  lea     rax, aBadAllocation; "bad allocation"
0x180036662  mov     qword ptr [rbp+var_18], rax
0x180036666  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18003666d  mov     [rbp+pExceptionObject], rax
0x180036671  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180036678  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003667c  call    _CxxThrowException_0
```
