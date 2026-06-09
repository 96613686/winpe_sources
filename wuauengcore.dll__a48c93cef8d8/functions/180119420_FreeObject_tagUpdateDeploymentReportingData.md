# FreeObject(tagUpdateDeploymentReportingData *)

- ea: `0x180119420`
- end: `0x1801196ec`
- name: `?FreeObject@@YAXPEAUtagUpdateDeploymentReportingData@@@Z`
- size: `716`
- prototype: `void __fastcall(struct tagUpdateDeploymentReportingData *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1801196f4`

## callees

- `0x180113ae8`
- `0x180113ca0`
- `0x180119420`
- `0x18011a84c`
- `0x180238984`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011964f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119672`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011964f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119672`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119697`
- `OLEAUT32!__imp_SysFreeString` at `0x180119445`
- `OLEAUT32!__imp_SysFreeString` at `0x18011945e`
- `OLEAUT32!__imp_SysFreeString` at `0x18011946c`
- `OLEAUT32!__imp_SysFreeString` at `0x18011947a`
- `OLEAUT32!__imp_SysFreeString` at `0x18011948b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801194c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18011950e`
- `OLEAUT32!__imp_SysFreeString` at `0x180119522`
- `OLEAUT32!__imp_SysFreeString` at `0x180119536`
- `OLEAUT32!__imp_SysFreeString` at `0x18011955d`
- `OLEAUT32!__imp_SysFreeString` at `0x180119571`
- `OLEAUT32!__imp_SysFreeString` at `0x180119585`
- `OLEAUT32!__imp_SysFreeString` at `0x180119445`
- `OLEAUT32!__imp_SysFreeString` at `0x18011945e`
- `OLEAUT32!__imp_SysFreeString` at `0x18011946c`
- `OLEAUT32!__imp_SysFreeString` at `0x18011947a`
- `OLEAUT32!__imp_SysFreeString` at `0x18011948b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801194c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18011950e`
- `OLEAUT32!__imp_SysFreeString` at `0x180119522`
- `OLEAUT32!__imp_SysFreeString` at `0x180119536`
- `OLEAUT32!__imp_SysFreeString` at `0x18011955d`
- `OLEAUT32!__imp_SysFreeString` at `0x180119571`
- `OLEAUT32!__imp_SysFreeString` at `0x180119585`

## pseudocode

```c
void __fastcall FreeObject(struct tagUpdateDeploymentReportingData *a1)
{
  void *v2; // rcx
  unsigned __int64 v3; // rcx
  wchar_t **v4; // rdx
  unsigned int v5; // esi
  void *v6; // rcx
  unsigned int v7; // esi
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx

  if ( a1 )
  {
    SysFreeString(*(BSTR *)a1);
    *(_QWORD *)a1 = 0;
    SafeBstrArrayFree(*((unsigned int *)a1 + 6), *((wchar_t ***)a1 + 4));
    SysFreeString(*((BSTR *)a1 + 9));
    *((_QWORD *)a1 + 9) = 0;
    SysFreeString(*((BSTR *)a1 + 10));
    *((_QWORD *)a1 + 10) = 0;
    SysFreeString(*((BSTR *)a1 + 13));
    *((_QWORD *)a1 + 13) = 0;
    SysFreeString(*((BSTR *)a1 + 18));
    *((_QWORD *)a1 + 18) = 0;
    SafeBstrArrayFree(*((unsigned int *)a1 + 40), *((wchar_t ***)a1 + 21));
    SafeBstrArrayFree(*((unsigned int *)a1 + 44), *((wchar_t ***)a1 + 23));
    SysFreeString(*((BSTR *)a1 + 24));
    *((_QWORD *)a1 + 24) = 0;
    SafeBstrArrayFree(*((unsigned int *)a1 + 51), *((wchar_t ***)a1 + 26));
    SafeBstrArrayFree(*((unsigned int *)a1 + 54), *((wchar_t ***)a1 + 28));
    SusFree(*((void **)a1 + 36));
    *((_QWORD *)a1 + 36) = 0;
    SysFreeString(*((BSTR *)a1 + 40));
    *((_QWORD *)a1 + 40) = 0;
    SysFreeString(*((BSTR *)a1 + 41));
    *((_QWORD *)a1 + 41) = 0;
    SysFreeString(*((BSTR *)a1 + 42));
    *((_QWORD *)a1 + 42) = 0;
    SusFree(*((void **)a1 + 43));
    *((_QWORD *)a1 + 43) = 0;
    SysFreeString(*((BSTR *)a1 + 44));
    *((_QWORD *)a1 + 44) = 0;
    SysFreeString(*((BSTR *)a1 + 51));
    *((_QWORD *)a1 + 51) = 0;
    SysFreeString(*((BSTR *)a1 + 52));
    *((_QWORD *)a1 + 52) = 0;
    operator delete(*((void **)a1 + 54), (const struct std::nothrow_t *)1);
    v2 = (void *)*((_QWORD *)a1 + 55);
    *((_QWORD *)a1 + 54) = 0;
    operator delete(v2, (const struct std::nothrow_t *)1);
    v3 = *((unsigned int *)a1 + 113);
    v4 = (wchar_t **)*((_QWORD *)a1 + 57);
    *((_QWORD *)a1 + 55) = 0;
    SafeBstrArrayFree(v3, v4);
    SafeBstrArrayFree(*((unsigned int *)a1 + 113), *((wchar_t ***)a1 + 58));
    SafeBstrArrayFree(*((unsigned int *)a1 + 120), *((wchar_t ***)a1 + 61));
    SusFree(*((void **)a1 + 62));
    *((_QWORD *)a1 + 62) = 0;
    SusFree(*((void **)a1 + 63));
    *((_QWORD *)a1 + 63) = 0;
    SusFree(*((void **)a1 + 66));
    *((_QWORD *)a1 + 66) = 0;
    if ( a1 != (struct tagUpdateDeploymentReportingData *)-544LL )
    {
      if ( *((_DWORD *)a1 + 141) )
      {
        v5 = 0;
        do
        {
          v6 = *(void **)(*((_QWORD *)a1 + 71) + 8LL * v5);
          if ( v6 )
            CoTaskMemFree(v6);
          ++v5;
        }
        while ( v5 < *((_DWORD *)a1 + 141) );
      }
      if ( *((_DWORD *)a1 + 144) )
      {
        v7 = 0;
        do
        {
          v8 = *(void **)(*((_QWORD *)a1 + 73) + 8LL * v7);
          if ( v8 )
            CoTaskMemFree(v8);
          ++v7;
        }
        while ( v7 < *((_DWORD *)a1 + 144) );
      }
      v9 = (void *)*((_QWORD *)a1 + 71);
      if ( v9 )
        CoTaskMemFree(v9);
      v10 = (void *)*((_QWORD *)a1 + 73);
      if ( v10 )
        CoTaskMemFree(v10);
      *((_OWORD *)a1 + 34) = 0;
      *((_OWORD *)a1 + 35) = 0;
      *((_OWORD *)a1 + 36) = 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl'::`2'::impl) )
      SusFree(*((void **)a1 + 76));
    memset(a1, 0, 0x288u);
  }
}

```

## disassembly

```asm
0x180119420  test    rcx, rcx
0x180119423  jz      locret_1801196EB
0x180119429  mov     [rsp+arg_0], rbx
0x18011942e  mov     [rsp+arg_8], rbp
0x180119433  mov     [rsp+arg_10], rsi
0x180119438  push    rdi
0x180119439  sub     rsp, 20h
0x18011943d  mov     rdi, rcx
0x180119440  xor     ebp, ebp
0x180119442  mov     rcx, [rcx]; bstrString
0x180119445  call    cs:__imp_SysFreeString
0x18011944b  mov     [rdi], rbp
0x18011944e  mov     ecx, [rdi+18h]; unsigned __int64
0x180119451  mov     rdx, [rdi+20h]; wchar_t **
0x180119455  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x18011945a  mov     rcx, [rdi+48h]; bstrString
0x18011945e  call    cs:__imp_SysFreeString
0x180119464  mov     [rdi+48h], rbp
0x180119468  mov     rcx, [rdi+50h]; bstrString
0x18011946c  call    cs:__imp_SysFreeString
0x180119472  mov     [rdi+50h], rbp
0x180119476  mov     rcx, [rdi+68h]; bstrString
0x18011947a  call    cs:__imp_SysFreeString
0x180119480  mov     [rdi+68h], rbp
0x180119484  mov     rcx, [rdi+90h]; bstrString
0x18011948b  call    cs:__imp_SysFreeString
0x180119491  mov     [rdi+90h], rbp
0x180119498  mov     ecx, [rdi+0A0h]; unsigned __int64
0x18011949e  mov     rdx, [rdi+0A8h]; wchar_t **
0x1801194a5  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x1801194aa  mov     ecx, [rdi+0B0h]; unsigned __int64
0x1801194b0  mov     rdx, [rdi+0B8h]; wchar_t **
0x1801194b7  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x1801194bc  mov     rcx, [rdi+0C0h]; bstrString
0x1801194c3  call    cs:__imp_SysFreeString
0x1801194c9  mov     [rdi+0C0h], rbp
0x1801194d0  mov     ecx, [rdi+0CCh]; unsigned __int64
0x1801194d6  mov     rdx, [rdi+0D0h]; wchar_t **
0x1801194dd  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x1801194e2  mov     ecx, [rdi+0D8h]; unsigned __int64
0x1801194e8  mov     rdx, [rdi+0E0h]; wchar_t **
0x1801194ef  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x1801194f4  mov     rcx, [rdi+120h]; lpMem
0x1801194fb  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180119500  mov     [rdi+120h], rbp
0x180119507  mov     rcx, [rdi+140h]; bstrString
0x18011950e  call    cs:__imp_SysFreeString
0x180119514  mov     [rdi+140h], rbp
0x18011951b  mov     rcx, [rdi+148h]; bstrString
0x180119522  call    cs:__imp_SysFreeString
0x180119528  mov     [rdi+148h], rbp
0x18011952f  mov     rcx, [rdi+150h]; bstrString
0x180119536  call    cs:__imp_SysFreeString
0x18011953c  mov     [rdi+150h], rbp
0x180119543  mov     rcx, [rdi+158h]; lpMem
0x18011954a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18011954f  mov     [rdi+158h], rbp
0x180119556  mov     rcx, [rdi+160h]; bstrString
0x18011955d  call    cs:__imp_SysFreeString
0x180119563  mov     [rdi+160h], rbp
0x18011956a  mov     rcx, [rdi+198h]; bstrString
0x180119571  call    cs:__imp_SysFreeString
0x180119577  mov     [rdi+198h], rbp
0x18011957e  mov     rcx, [rdi+1A0h]; bstrString
0x180119585  call    cs:__imp_SysFreeString
0x18011958b  mov     [rdi+1A0h], rbp
0x180119592  lea     edx, [rbp+1]; struct std::nothrow_t *
0x180119595  mov     rcx, [rdi+1B0h]; void *
0x18011959c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801195a1  mov     rcx, [rdi+1B8h]; void *
0x1801195a8  lea     edx, [rbp+1]; struct std::nothrow_t *
0x1801195ab  mov     [rdi+1B0h], rbp
0x1801195b2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801195b7  mov     ecx, [rdi+1C4h]; unsigned __int64
0x1801195bd  mov     rdx, [rdi+1C8h]; wchar_t **
0x1801195c4  mov     [rdi+1B8h], rbp
0x1801195cb  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x1801195d0  mov     ecx, [rdi+1C4h]; unsigned __int64
0x1801195d6  mov     rdx, [rdi+1D0h]; wchar_t **
0x1801195dd  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x1801195e2  mov     ecx, [rdi+1E0h]; unsigned __int64
0x1801195e8  mov     rdx, [rdi+1E8h]; wchar_t **
0x1801195ef  call    ?SafeBstrArrayFree@@YAX_KPEAPEA_W@Z; SafeBstrArrayFree(unsigned __int64,wchar_t * *)
0x1801195f4  mov     rcx, [rdi+1F0h]; lpMem
0x1801195fb  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180119600  mov     [rdi+1F0h], rbp
0x180119607  mov     rcx, [rdi+1F8h]; lpMem
0x18011960e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180119613  mov     [rdi+1F8h], rbp
0x18011961a  mov     rcx, [rdi+210h]; lpMem
0x180119621  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180119626  lea     rbx, [rdi+220h]
0x18011962d  mov     [rdi+210h], rbp
0x180119634  test    rbx, rbx
0x180119637  jz      short loc_1801196AB
0x180119639  cmp     [rbx+14h], ebp
0x18011963c  jbe     short loc_18011965C
0x18011963e  mov     esi, ebp
0x180119640  mov     rax, [rbx+18h]
0x180119644  mov     ecx, esi
0x180119646  mov     rcx, [rax+rcx*8]; pv
0x18011964a  test    rcx, rcx
0x18011964d  jz      short loc_180119655
0x18011964f  call    cs:__imp_CoTaskMemFree
0x180119655  inc     esi
0x180119657  cmp     esi, [rbx+14h]
0x18011965a  jb      short loc_180119640
0x18011965c  cmp     [rbx+20h], ebp
0x18011965f  jbe     short loc_18011967F
0x180119661  mov     esi, ebp
0x180119663  mov     rax, [rbx+28h]
0x180119667  mov     ecx, esi
0x180119669  mov     rcx, [rax+rcx*8]; pv
0x18011966d  test    rcx, rcx
0x180119670  jz      short loc_180119678
0x180119672  call    cs:__imp_CoTaskMemFree
0x180119678  inc     esi
0x18011967a  cmp     esi, [rbx+20h]
0x18011967d  jb      short loc_180119663
0x18011967f  mov     rcx, [rbx+18h]; pv
0x180119683  test    rcx, rcx
0x180119686  jz      short loc_18011968E
0x180119688  call    cs:__imp_CoTaskMemFree
0x18011968e  mov     rcx, [rbx+28h]; pv
0x180119692  test    rcx, rcx
0x180119695  jz      short loc_18011969D
0x180119697  call    cs:__imp_CoTaskMemFree
0x18011969d  xorps   xmm0, xmm0
0x1801196a0  movups  xmmword ptr [rbx], xmm0
0x1801196a3  movups  xmmword ptr [rbx+10h], xmm0
0x1801196a7  movups  xmmword ptr [rbx+20h], xmm0
0x1801196ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration> `wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl(void)'::`2'::impl
0x1801196b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(void)
0x1801196b7  test    al, al
0x1801196b9  jz      short loc_1801196C7
0x1801196bb  mov     rcx, [rdi+260h]; lpMem
0x1801196c2  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1801196c7  xor     edx, edx; Val
0x1801196c9  mov     r8d, 288h; Size
0x1801196cf  mov     rcx, rdi; void *
0x1801196d2  call    memset
0x1801196d7  mov     rbx, [rsp+28h+arg_0]
0x1801196dc  mov     rbp, [rsp+28h+arg_8]
0x1801196e1  mov     rsi, [rsp+28h+arg_10]
0x1801196e6  add     rsp, 20h
0x1801196ea  pop     rdi
0x1801196eb  retn
```
