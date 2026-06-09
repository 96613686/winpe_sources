# inverted::CAndCursor::GetRank(std::vector<std::shared_ptr<inverted::IDecoder>,std::allocator<std::shared_ptr<inverted::IDecoder>>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *)

- ea: `0x180144580`
- end: `0x1801449e0`
- name: `?GetRank@CAndCursor@inverted@@UEAAXAEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@std@@PEAUIInvertedQuery@2@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAG@Z`
- size: `1120`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800d5e3c`
- `0x1800d7330`
- `0x180139dbc`
- `0x18013cd74`
- `0x180144580`
- `0x1801449e8`
- `0x180144e5c`
- `0x180145908`
- `0x180188d90`
- `0x18022891c`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144671`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144703`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144757`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801447dd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144671`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144703`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144757`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801447dd`

## string_xrefs

- `0x18014474b`: `CONVEXCOMBINATION`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall inverted::CAndCursor::GetRank(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v11; // rsi
  __int64 v12; // r14
  inverted::CRankCoercion *v13; // r8
  __int64 result; // rax
  int v15; // edx
  const WCHAR *v16; // rdi
  int v17; // edx
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  int v20; // edx
  int v21; // edx
  __int64 v22; // rax
  int v23; // edx
  char v25[8]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v26[7]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v27; // [rsp+98h] [rbp-68h]
  _QWORD v28[7]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v29; // [rsp+D8h] [rbp-28h]
  _QWORD v30[7]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v31; // [rsp+118h] [rbp+18h]
  _QWORD v32[7]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v33; // [rsp+158h] [rbp+58h]
  _QWORD v34[7]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD *v35; // [rsp+198h] [rbp+98h]
  _BYTE v36[56]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD *v37; // [rsp+1D8h] [rbp+D8h]

  v11 = a6;
  v12 = a7;
  v13 = (inverted::CRankCoercion *)(a1 + 32);
  if ( *(_BYTE *)(a1 + 132) )
    return inverted::FillRankConstant(a5, a6, a7, 1001, 0, (inverted::CRankCoercion *)(a1 + 32));
  if ( *(_WORD *)v13 != 0xFFFF )
    return inverted::FillRankConstant(a5, a6, a7, 1000, (a1 + 136) & -(__int64)((*(_DWORD *)(a1 + 128) & 8) != 0), v13);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
  {
    v16 = (const WCHAR *)(a1 + 48);
    if ( *(_QWORD *)(a1 + 72) > 7u )
      v16 = *(const WCHAR **)v16;
    if ( CompareStringOrdinal(v16, -1, L"ADD", -1, 1) == 2 )
    {
      v26[0] = off_1802C6170;
      v26[1] = a1;
      v27 = v26;
      LOBYTE(v17) = 1;
      result = inverted::GetData(0, v17, (int)a1 + 8, a2, a3, a4, a5, v11, v12, (__int64)v26);
      v18 = v27;
      if ( !v27 )
        return result;
      v19 = v26;
    }
    else
    {
      if ( CompareStringOrdinal(v16, -1, L"FILESEARCH1", -1, 1) == 2 )
        return inverted::RRFRankMerge((int)a1 + 8, a2, a3, a4, (__int64)&a5, v11, v12);
      if ( CompareStringOrdinal(v16, -1, L"CONVEXCOMBINATION", -1, 1) == 2 )
      {
        v28[0] = off_1802C6230;
        v28[1] = a1;
        v29 = v28;
        result = inverted::ConvexCombinationRankMerge((int)a1 + 8, a2, a3, a4, (__int64)&a5, v11, v12, (__int64)v28);
        v18 = v29;
        if ( !v29 )
          return result;
        v19 = v28;
      }
      else if ( CompareStringOrdinal(v16, -1, L"MAX", -1, 1) == 2 )
      {
        v30[0] = off_1802C6200;
        v30[1] = a1;
        v31 = v30;
        LOBYTE(v20) = 1;
        result = inverted::GetData(0, v20, (int)a1 + 8, a2, a3, a4, a5, v11, v12, (__int64)v30);
        v18 = v31;
        if ( !v31 )
          return result;
        v19 = v30;
      }
      else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55652650>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55652650>::GetImpl'::`2'::impl) )
      {
        v22 = XPtr<CPropertyList>::XPtr<CPropertyList>(v25, a1);
        std::function_unsigned_short___cdecl_unsigned_short_unsigned_short__::function_unsigned_short___cdecl_unsigned_short_unsigned_short____lambda_e76007ac2459e7d7b4ef5ea1e52b2b62__0_(
          v36,
          v22);
        LOBYTE(v23) = 1;
        result = inverted::GetData(1000, v23, (int)a1 + 8, a2, a3, a4, a5, v11, v12, (__int64)v36);
        v18 = v37;
        if ( !v37 )
          return result;
        v19 = v36;
      }
      else
      {
        v32[0] = off_1802C61D0;
        v32[1] = a1;
        v33 = v32;
        LOBYTE(v21) = 1;
        result = inverted::GetData(1000, v21, (int)a1 + 8, a2, a3, a4, a5, v11, v12, (__int64)v32);
        v18 = v33;
        if ( !v33 )
          return result;
        v19 = v32;
      }
    }
  }
  else
  {
    v34[0] = off_1802C61A0;
    v34[1] = a1;
    v35 = v34;
    LOBYTE(v15) = 1;
    result = inverted::GetData(1000, v15, (int)a1 + 8, a2, a3, a4, a5, v11, v12, (__int64)v34);
    v18 = v35;
    if ( !v35 )
      return result;
    v19 = v34;
  }
  LOBYTE(v19) = v18 != v19;
  return (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(*v18 + 32LL))(v18, v19);
}

```

## disassembly

```asm
0x180144580  push    rbp
0x180144582  push    rbx
0x180144583  push    rsi
0x180144584  push    rdi
0x180144585  push    r12
0x180144587  push    r13
0x180144589  push    r14
0x18014458b  lea     rbp, [rsp-0F0h]
0x180144593  sub     rsp, 1F0h
0x18014459a  mov     rax, cs:__security_cookie
0x1801445a1  xor     rax, rsp
0x1801445a4  mov     [rbp+120h+var_40], rax
0x1801445ab  mov     rdi, r9
0x1801445ae  mov     [rsp+220h+var_1D0], r9
0x1801445b3  mov     r13, r8
0x1801445b6  mov     r12, rdx
0x1801445b9  mov     rbx, rcx
0x1801445bc  mov     rsi, [rbp+120h+arg_28]
0x1801445c3  mov     r14, [rbp+120h+arg_30]
0x1801445ca  lea     r8, [rcx+20h]
0x1801445ce  cmp     byte ptr [rcx+84h], 0
0x1801445d5  jz      short loc_1801445ED
0x1801445d7  mov     r9d, 3E9h
0x1801445dd  mov     [rsp+220h+var_1F8], r8
0x1801445e2  mov     qword ptr [rsp+220h+bIgnoreCase], 0
0x1801445eb  jmp     short loc_18014461F
0x1801445ed  mov     eax, 0FFFFh
0x1801445f2  cmp     [r8], ax
0x1801445f6  jz      short loc_180144635
0x1801445f8  mov     eax, [rcx+80h]
0x1801445fe  and     al, 8
0x180144600  add     rcx, 88h
0x180144607  neg     al
0x180144609  sbb     rdx, rdx
0x18014460c  and     rdx, rcx
0x18014460f  mov     r9d, 3E8h; int
0x180144615  mov     [rsp+220h+var_1F8], r8; inverted::CRankCoercion *
0x18014461a  mov     qword ptr [rsp+220h+bIgnoreCase], rdx; __int64
0x18014461f  mov     r8, r14; int
0x180144622  mov     rdx, rsi; int
0x180144625  mov     ecx, [rbp+120h+arg_20]; int
0x18014462b  call    ?FillRankConstant@inverted@@YAXIPEBIPEAGGPEAU?$dynamic_sparse_bit@_K@@AEAVCRankCoercion@1@@Z; inverted::FillRankConstant(uint,uint const *,ushort *,ushort,dynamic_sparse_bit<unsigned __int64> *,inverted::CRankCoercion &)
0x180144630  jmp     loc_1801449BF
0x180144635  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x18014463c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x180144641  test    al, al
0x180144643  jz      loc_180144948
0x180144649  lea     rdi, [rbx+30h]
0x18014464d  cmp     qword ptr [rdi+18h], 7
0x180144652  jbe     short loc_180144657
0x180144654  mov     rdi, [rdi]
0x180144657  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x18014465f  or      eax, 0FFFFFFFFh
0x180144662  mov     r9d, eax; cchCount2
0x180144665  lea     r8, aAdd_2; "ADD"
0x18014466c  mov     edx, eax; cchCount1
0x18014466e  mov     rcx, rdi; lpString1
0x180144671  call    cs:__imp_CompareStringOrdinal
0x180144677  cmp     eax, 2
0x18014467a  jnz     short loc_1801446EB
0x18014467c  lea     rax, off_1802C6170
0x180144683  mov     [rsp+220h+var_1C0], rax
0x180144688  mov     [rsp+220h+var_1B8], rbx
0x18014468d  lea     rax, [rsp+220h+var_1C0]
0x180144692  mov     [rbp+120h+var_188], rax
0x180144696  lea     r8, [rbx+8]
0x18014469a  xor     ecx, ecx
0x18014469c  lea     rax, [rsp+220h+var_1C0]
0x1801446a1  mov     [rsp+220h+var_1D8], rax
0x1801446a6  mov     [rsp+220h+var_1E0], r14
0x1801446ab  mov     [rsp+220h+var_1E8], rsi
0x1801446b0  mov     eax, [rbp+120h+arg_20]
0x1801446b6  mov     dword ptr [rsp+220h+var_1F0], eax
0x1801446ba  mov     rax, [rsp+220h+var_1D0]
0x1801446bf  mov     [rsp+220h+var_1F8], rax
0x1801446c4  mov     qword ptr [rsp+220h+bIgnoreCase], r13
0x1801446c9  mov     r9, r12
0x1801446cc  mov     dl, 1
0x1801446ce  call    ?GetData@inverted@@YAXG_NAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAGAEBV?$function@$$A6AGGG@Z@3@@Z; inverted::GetData(ushort,bool,std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *,std::function<ushort (ushort,ushort)> const &)
0x1801446d3  nop
0x1801446d4  mov     rcx, [rbp+120h+var_188]
0x1801446d8  test    rcx, rcx
0x1801446db  jz      loc_1801449BF
0x1801446e1  lea     rdx, [rsp+220h+var_1C0]
0x1801446e6  jmp     loc_1801449AD
0x1801446eb  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x1801446f3  or      edx, 0FFFFFFFFh; cchCount1
0x1801446f6  mov     r9d, edx; cchCount2
0x1801446f9  lea     r8, aFilesearch1; "FILESEARCH1"
0x180144700  mov     rcx, rdi; lpString1
0x180144703  call    cs:__imp_CompareStringOrdinal
0x180144709  cmp     eax, 2
0x18014470c  jnz     short loc_18014473D
0x18014470e  lea     rcx, [rbx+8]
0x180144712  mov     [rsp+220h+var_1F0], r14
0x180144717  mov     [rsp+220h+var_1F8], rsi
0x18014471c  lea     rax, [rbp+120h+arg_20]
0x180144723  mov     qword ptr [rsp+220h+bIgnoreCase], rax
0x180144728  mov     r9, [rsp+220h+var_1D0]
0x18014472d  mov     r8, r13
0x180144730  mov     rdx, r12
0x180144733  call    ?RRFRankMerge@inverted@@YAXAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@AEAIPEBIPEAG@Z; inverted::RRFRankMerge(std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint &,uint const *,ushort *)
0x180144738  jmp     loc_1801449BF
0x18014473d  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x180144745  or      eax, 0FFFFFFFFh
0x180144748  mov     r9d, eax; cchCount2
0x18014474b  lea     r8, aConvexcombinat; "CONVEXCOMBINATION"
0x180144752  mov     edx, eax; cchCount1
0x180144754  mov     rcx, rdi; lpString1
0x180144757  call    cs:__imp_CompareStringOrdinal
0x18014475d  cmp     eax, 2
0x180144760  jnz     short loc_1801447C3
0x180144762  lea     rax, off_1802C6230
0x180144769  mov     [rbp+120h+var_180], rax
0x18014476d  mov     [rbp+120h+var_178], rbx
0x180144771  lea     rax, [rbp+120h+var_180]
0x180144775  mov     [rbp+120h+var_148], rax
0x180144779  lea     rcx, [rbx+8]
0x18014477d  lea     rax, [rbp+120h+var_180]
0x180144781  mov     [rsp+220h+var_1E8], rax
0x180144786  mov     [rsp+220h+var_1F0], r14
0x18014478b  mov     [rsp+220h+var_1F8], rsi
0x180144790  lea     rax, [rbp+120h+arg_20]
0x180144797  mov     qword ptr [rsp+220h+bIgnoreCase], rax
0x18014479c  mov     r9, [rsp+220h+var_1D0]
0x1801447a1  mov     r8, r13
0x1801447a4  mov     rdx, r12
0x1801447a7  call    ?ConvexCombinationRankMerge@inverted@@YAXAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@AEAIPEBIPEAGAEBV?$function@$$A6AGG@Z@3@@Z; inverted::ConvexCombinationRankMerge(std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint &,uint const *,ushort *,std::function<ushort (ushort)> const &)
0x1801447ac  nop
0x1801447ad  mov     rcx, [rbp+120h+var_148]
0x1801447b1  test    rcx, rcx
0x1801447b4  jz      loc_1801449BF
0x1801447ba  lea     rdx, [rbp+120h+var_180]
0x1801447be  jmp     loc_1801449AD
0x1801447c3  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x1801447cb  or      eax, 0FFFFFFFFh
0x1801447ce  mov     r9d, eax; cchCount2
0x1801447d1  lea     r8, aMax_1; "MAX"
0x1801447d8  mov     edx, eax; cchCount1
0x1801447da  mov     rcx, rdi; lpString1
0x1801447dd  call    cs:__imp_CompareStringOrdinal
0x1801447e3  cmp     eax, 2
0x1801447e6  jnz     short loc_180144852
0x1801447e8  lea     rax, off_1802C6200
0x1801447ef  mov     [rbp+120h+var_140], rax
0x1801447f3  mov     [rbp+120h+var_138], rbx
0x1801447f7  lea     rax, [rbp+120h+var_140]
0x1801447fb  mov     [rbp+120h+var_108], rax
0x1801447ff  lea     r8, [rbx+8]
0x180144803  xor     ecx, ecx
0x180144805  lea     rax, [rbp+120h+var_140]
0x180144809  mov     [rsp+220h+var_1D8], rax
0x18014480e  mov     [rsp+220h+var_1E0], r14
0x180144813  mov     [rsp+220h+var_1E8], rsi
0x180144818  mov     eax, [rbp+120h+arg_20]
0x18014481e  mov     dword ptr [rsp+220h+var_1F0], eax
0x180144822  mov     rax, [rsp+220h+var_1D0]
0x180144827  mov     [rsp+220h+var_1F8], rax
0x18014482c  mov     qword ptr [rsp+220h+bIgnoreCase], r13
0x180144831  mov     r9, r12
0x180144834  mov     dl, 1
0x180144836  call    ?GetData@inverted@@YAXG_NAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAGAEBV?$function@$$A6AGGG@Z@3@@Z; inverted::GetData(ushort,bool,std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *,std::function<ushort (ushort,ushort)> const &)
0x18014483b  nop
0x18014483c  mov     rcx, [rbp+120h+var_108]
0x180144840  test    rcx, rcx
0x180144843  jz      loc_1801449BF
0x180144849  lea     rdx, [rbp+120h+var_140]
0x18014484d  jmp     loc_1801449AD
0x180144852  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55652650@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55652650@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55652650> `wil::Feature<__WilFeatureTraits_Feature_55652650>::GetImpl(void)'::`2'::impl
0x180144859  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55652650@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55652650>::__private_IsEnabled(void)
0x18014485e  test    al, al
0x180144860  jnz     short loc_1801448CF
0x180144862  lea     rax, off_1802C61D0
0x180144869  mov     [rbp+120h+var_100], rax
0x18014486d  mov     [rbp+120h+var_F8], rbx
0x180144871  lea     rax, [rbp+120h+var_100]
0x180144875  mov     [rbp+120h+var_C8], rax
0x180144879  lea     r8, [rbx+8]
0x18014487d  mov     ecx, 3E8h
0x180144882  lea     rax, [rbp+120h+var_100]
0x180144886  mov     [rsp+220h+var_1D8], rax
0x18014488b  mov     [rsp+220h+var_1E0], r14
0x180144890  mov     [rsp+220h+var_1E8], rsi
0x180144895  mov     eax, [rbp+120h+arg_20]
0x18014489b  mov     dword ptr [rsp+220h+var_1F0], eax
0x18014489f  mov     rax, [rsp+220h+var_1D0]
0x1801448a4  mov     [rsp+220h+var_1F8], rax
0x1801448a9  mov     qword ptr [rsp+220h+bIgnoreCase], r13
0x1801448ae  mov     r9, r12
0x1801448b1  mov     dl, 1
0x1801448b3  call    ?GetData@inverted@@YAXG_NAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAGAEBV?$function@$$A6AGGG@Z@3@@Z; inverted::GetData(ushort,bool,std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *,std::function<ushort (ushort,ushort)> const &)
0x1801448b8  nop
0x1801448b9  mov     rcx, [rbp+120h+var_C8]
0x1801448bd  test    rcx, rcx
0x1801448c0  jz      loc_1801449BF
0x1801448c6  lea     rdx, [rbp+120h+var_100]
0x1801448ca  jmp     loc_1801449AD
0x1801448cf  mov     rdx, rbx
0x1801448d2  lea     rcx, [rsp+220h+var_1C8]
0x1801448d7  call    ??0?$XPtr@VCPropertyList@@@@QEAA@PEAVCPropertyList@@@Z; XPtr<CPropertyList>::XPtr<CPropertyList>(CPropertyList *)
0x1801448dc  mov     rdx, rax
0x1801448df  lea     rcx, [rbp+120h+var_80]
0x1801448e6  call    std__function_unsigned_short___cdecl_unsigned_short_unsigned_short____function_unsigned_short___cdecl_unsigned_short_unsigned_short____lambda_e76007ac2459e7d7b4ef5ea1e52b2b62__0_
0x1801448eb  nop
0x1801448ec  lea     r8, [rbx+8]
0x1801448f0  mov     ecx, 3E8h
0x1801448f5  lea     rax, [rbp+120h+var_80]
0x1801448fc  mov     [rsp+220h+var_1D8], rax
0x180144901  mov     [rsp+220h+var_1E0], r14
0x180144906  mov     [rsp+220h+var_1E8], rsi
0x18014490b  mov     eax, [rbp+120h+arg_20]
0x180144911  mov     dword ptr [rsp+220h+var_1F0], eax
0x180144915  mov     rax, [rsp+220h+var_1D0]
0x18014491a  mov     [rsp+220h+var_1F8], rax
0x18014491f  mov     qword ptr [rsp+220h+bIgnoreCase], r13
0x180144924  mov     r9, r12
0x180144927  mov     dl, 1
0x180144929  call    ?GetData@inverted@@YAXG_NAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAGAEBV?$function@$$A6AGGG@Z@3@@Z; inverted::GetData(ushort,bool,std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *,std::function<ushort (ushort,ushort)> const &)
0x18014492e  nop
0x18014492f  mov     rcx, [rbp+120h+var_48]
0x180144936  test    rcx, rcx
0x180144939  jz      loc_1801449BF
0x18014493f  lea     rdx, [rbp+120h+var_80]
0x180144946  jmp     short loc_1801449AD
0x180144948  lea     rax, off_1802C61A0
0x18014494f  mov     [rbp+120h+var_C0], rax
0x180144953  mov     [rbp+120h+var_B8], rbx
0x180144957  lea     rax, [rbp+120h+var_C0]
0x18014495b  mov     [rbp+120h+var_88], rax
0x180144962  lea     r8, [rbx+8]
0x180144966  mov     ecx, 3E8h
0x18014496b  lea     rax, [rbp+120h+var_C0]
0x18014496f  mov     [rsp+220h+var_1D8], rax
0x180144974  mov     [rsp+220h+var_1E0], r14
0x180144979  mov     [rsp+220h+var_1E8], rsi
0x18014497e  mov     eax, [rbp+120h+arg_20]
0x180144984  mov     dword ptr [rsp+220h+var_1F0], eax
0x180144988  mov     [rsp+220h+var_1F8], rdi
0x18014498d  mov     qword ptr [rsp+220h+bIgnoreCase], r13
0x180144992  mov     r9, r12
0x180144995  mov     dl, 1
0x180144997  call    ?GetData@inverted@@YAXG_NAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAGAEBV?$function@$$A6AGGG@Z@3@@Z; inverted::GetData(ushort,bool,std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *,std::function<ushort (ushort,ushort)> const &)
0x18014499c  nop
0x18014499d  mov     rcx, [rbp+120h+var_88]
0x1801449a4  test    rcx, rcx
0x1801449a7  jz      short loc_1801449BF
0x1801449a9  lea     rdx, [rbp+120h+var_C0]
0x1801449ad  cmp     rcx, rdx
0x1801449b0  mov     rax, [rcx]
0x1801449b3  setnz   dl
0x1801449b6  mov     rax, [rax+20h]
0x1801449ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801449bf  mov     rcx, [rbp+120h+var_40]
0x1801449c6  xor     rcx, rsp; StackCookie
0x1801449c9  call    __security_check_cookie
0x1801449ce  add     rsp, 1F0h
0x1801449d5  pop     r14
0x1801449d7  pop     r13
0x1801449d9  pop     r12
0x1801449db  pop     rdi
0x1801449dc  pop     rsi
0x1801449dd  pop     rbx
0x1801449de  pop     rbp
0x1801449df  retn
```
