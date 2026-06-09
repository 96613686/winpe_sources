# std::vector<Windows::UI::Composition::EffectInstance::SubgraphData,std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x1800092e0`
- end: `0x180009489`
- name: `??$_Resize@U_Value_init_tag@std@@@?$vector@USubgraphData@EffectInstance@Composition@UI@Windows@@V?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `425`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800160c4`

## callees

- `0x1800092e0`
- `0x180009490`
- `0x18000a88c`
- `0x18000ad40`
- `0x18000adc0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009440`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009440`

## pseudocode

```c
char *__fastcall std::vector<Windows::UI::Composition::EffectInstance::SubgraphData>::_Resize<std::_Value_init_tag>(
        char **a1,
        unsigned __int64 a2)
{
  char *v2; // rsi
  char *result; // rax
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // rcx
  __int64 v8; // rsi
  unsigned __int64 v9; // rdx
  SIZE_T size_of; // rax
  __int64 v11; // rax
  _QWORD *v12; // rcx
  _DWORD *v13; // r15
  unsigned __int64 v14; // rdx
  char *v15; // r8
  _DWORD *v16; // rcx
  char *i; // rdx
  char *v18; // rbx
  unsigned __int64 v19; // rdi
  __int64 v20; // rax

  v2 = a1[1];
  result = *a1;
  v6 = (v2 - *a1) >> 4;
  if ( a2 < v6 )
  {
    v18 = &result[16 * a2];
    result = (char *)std::_Destroy_range<std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>(v18);
    a1[1] = v18;
  }
  else if ( a2 > v6 )
  {
    v7 = (a1[2] - result) >> 4;
    if ( a2 <= v7 )
    {
      v19 = a2 - v6;
      if ( a2 != v6 )
      {
        do
        {
          *((_QWORD *)v2 + 1) = 0;
          *(_QWORD *)v2 = 0;
          v2 += 16;
          --v19;
        }
        while ( v19 );
      }
      result = (char *)std::_Destroy_range<std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>(v2);
      a1[1] = v2;
    }
    else
    {
      v8 = 0xFFFFFFFFFFFFFFFLL;
      if ( a2 > 0xFFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      v9 = v7 >> 1;
      if ( v7 <= 0xFFFFFFFFFFFFFFFLL - (v7 >> 1) )
      {
        v8 = v9 + v7;
        if ( v9 + v7 < a2 )
          v8 = a2;
      }
      size_of = std::_Get_size_of_n<16>(v8);
      v11 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
      v12 = (_QWORD *)(v11 + 16 * v6);
      v13 = (_DWORD *)v11;
      v14 = a2 - v6;
      if ( a2 != v6 )
      {
        do
        {
          v12[1] = 0;
          *v12 = 0;
          v12 += 2;
          --v14;
        }
        while ( v14 );
      }
      std::_Destroy_range<std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>(v12);
      v15 = a1[1];
      v16 = v13;
      for ( i = *a1; i != v15; v16 += 4 )
      {
        v20 = *(_QWORD *)i;
        *(_QWORD *)i = 0;
        *(_QWORD *)v16 = v20;
        LODWORD(v20) = *((_DWORD *)i + 2);
        i += 16;
        v16[2] = v20;
      }
      result = (char *)std::_Destroy_range<std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>(v16);
      if ( *a1 )
      {
        std::_Destroy_range<std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>(*a1);
        result = (char *)std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL);
      }
      *a1 = (char *)v13;
      a1[1] = (char *)&v13[4 * a2];
      a1[2] = (char *)&v13[4 * v8];
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800092e0  mov     [rsp+arg_8], rbx
0x1800092e5  mov     [rsp+arg_10], rbp
0x1800092ea  push    rsi
0x1800092eb  push    rdi
0x1800092ec  push    r14
0x1800092ee  sub     rsp, 20h
0x1800092f2  mov     rsi, [rcx+8]
0x1800092f6  mov     rdi, rdx
0x1800092f9  mov     rax, [rcx]
0x1800092fc  mov     rbp, rsi
0x1800092ff  sub     rbp, rax
0x180009302  mov     r14, rcx
0x180009305  sar     rbp, 4
0x180009309  cmp     rdx, rbp
0x18000930c  jb      loc_1800093F8
0x180009312  jbe     loc_1800093E5
0x180009318  mov     rcx, [rcx+10h]
0x18000931c  sub     rcx, rax
0x18000931f  sar     rcx, 4
0x180009323  cmp     rdx, rcx
0x180009326  jbe     loc_180009410
0x18000932c  mov     rsi, 0FFFFFFFFFFFFFFFh
0x180009336  cmp     rdx, rsi
0x180009339  ja      loc_180009439
0x18000933f  mov     rdx, rcx
0x180009342  mov     [rsp+38h+arg_0], r15
0x180009347  shr     rdx, 1
0x18000934a  mov     rax, rsi
0x18000934d  sub     rax, rdx
0x180009350  cmp     rcx, rax
0x180009353  ja      short loc_180009360
0x180009355  lea     rsi, [rdx+rcx]
0x180009359  cmp     rsi, rdi
0x18000935c  cmovb   rsi, rdi
0x180009360  mov     rcx, rsi
0x180009363  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x180009368  mov     rcx, rax; dwBytes
0x18000936b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009370  mov     rcx, rbp
0x180009373  mov     rdx, rdi
0x180009376  shl     rcx, 4
0x18000937a  xor     ebx, ebx
0x18000937c  add     rcx, rax
0x18000937f  mov     r15, rax
0x180009382  sub     rdx, rbp
0x180009385  jz      short loc_180009398
0x180009387  mov     [rcx+8], rbx
0x18000938b  mov     [rcx], rbx
0x18000938e  add     rcx, 10h
0x180009392  sub     rdx, 1
0x180009396  jnz     short loc_180009387
0x180009398  mov     rdx, rcx
0x18000939b  call    ??$_Destroy_range@V?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@std@@@std@@YAXPEAUSubgraphData@EffectInstance@Composition@UI@Windows@@QEAU12345@AEAV?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>(Windows::UI::Composition::EffectInstance::SubgraphData *,Windows::UI::Composition::EffectInstance::SubgraphData * const,std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData> &)
0x1800093a0  mov     r8, [r14+8]
0x1800093a4  mov     rcx, r15
0x1800093a7  mov     rdx, [r14]
0x1800093aa  cmp     rdx, r8
0x1800093ad  jnz     loc_180009447
0x1800093b3  mov     rdx, rcx
0x1800093b6  call    ??$_Destroy_range@V?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@std@@@std@@YAXPEAUSubgraphData@EffectInstance@Composition@UI@Windows@@QEAU12345@AEAV?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>(Windows::UI::Composition::EffectInstance::SubgraphData *,Windows::UI::Composition::EffectInstance::SubgraphData * const,std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData> &)
0x1800093bb  mov     rcx, [r14]
0x1800093be  test    rcx, rcx
0x1800093c1  jnz     loc_180009468
0x1800093c7  mov     [r14], r15
0x1800093ca  shl     rdi, 4
0x1800093ce  add     rdi, r15
0x1800093d1  shl     rsi, 4
0x1800093d5  add     rsi, r15
0x1800093d8  mov     [r14+8], rdi
0x1800093dc  mov     r15, [rsp+38h+arg_0]
0x1800093e1  mov     [r14+10h], rsi
0x1800093e5  mov     rbx, [rsp+38h+arg_8]
0x1800093ea  mov     rbp, [rsp+38h+arg_10]
0x1800093ef  add     rsp, 20h
0x1800093f3  pop     r14
0x1800093f5  pop     rdi
0x1800093f6  pop     rsi
0x1800093f7  retn
0x1800093f8  add     rdi, rdi
0x1800093fb  mov     rdx, rsi
0x1800093fe  lea     rbx, [rax+rdi*8]
0x180009402  mov     rcx, rbx
0x180009405  call    ??$_Destroy_range@V?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@std@@@std@@YAXPEAUSubgraphData@EffectInstance@Composition@UI@Windows@@QEAU12345@AEAV?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>(Windows::UI::Composition::EffectInstance::SubgraphData *,Windows::UI::Composition::EffectInstance::SubgraphData * const,std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData> &)
0x18000940a  mov     [r14+8], rbx
0x18000940e  jmp     short loc_1800093E5
0x180009410  sub     rdi, rbp
0x180009413  jz      short loc_180009428
0x180009415  xor     ebx, ebx
0x180009417  mov     [rsi+8], rbx
0x18000941b  mov     [rsi], rbx
0x18000941e  add     rsi, 10h
0x180009422  sub     rdi, 1
0x180009426  jnz     short loc_180009417
0x180009428  mov     rdx, rsi
0x18000942b  mov     rcx, rsi
0x18000942e  call    ??$_Destroy_range@V?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@std@@@std@@YAXPEAUSubgraphData@EffectInstance@Composition@UI@Windows@@QEAU12345@AEAV?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>(Windows::UI::Composition::EffectInstance::SubgraphData *,Windows::UI::Composition::EffectInstance::SubgraphData * const,std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData> &)
0x180009433  mov     [r14+8], rsi
0x180009437  jmp     short loc_1800093E5
0x180009439  lea     rcx, aVectorTooLong; "vector too long"
0x180009440  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180009447  mov     rax, [rdx]
0x18000944a  mov     [rdx], rbx
0x18000944d  mov     [rcx], rax
0x180009450  mov     eax, [rdx+8]
0x180009453  add     rdx, 10h
0x180009457  mov     [rcx+8], eax
0x18000945a  add     rcx, 10h
0x18000945e  cmp     rdx, r8
0x180009461  jnz     short loc_180009447
0x180009463  jmp     loc_1800093B3
0x180009468  mov     rdx, [r14+8]
0x18000946c  call    ??$_Destroy_range@V?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@std@@@std@@YAXPEAUSubgraphData@EffectInstance@Composition@UI@Windows@@QEAU12345@AEAV?$allocator@USubgraphData@EffectInstance@Composition@UI@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData>>(Windows::UI::Composition::EffectInstance::SubgraphData *,Windows::UI::Composition::EffectInstance::SubgraphData * const,std::allocator<Windows::UI::Composition::EffectInstance::SubgraphData> &)
0x180009471  mov     rcx, [r14]
0x180009474  mov     rdx, [r14+10h]
0x180009478  sub     rdx, rcx
0x18000947b  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18000947f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009484  jmp     loc_1800093C7
```
