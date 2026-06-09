# inverted::COrCursor::GetRank(std::vector<std::shared_ptr<inverted::IDecoder>,std::allocator<std::shared_ptr<inverted::IDecoder>>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *)

- ea: `0x180144a10`
- end: `0x180144e56`
- name: `?GetRank@COrCursor@inverted@@UEAAXAEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@std@@PEAUIInvertedQuery@2@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAG@Z`
- size: `1094`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800d5e3c`
- `0x1800d7330`
- `0x180139dbc`
- `0x18013cd74`
- `0x180144a10`
- `0x180144e5c`
- `0x180188d90`
- `0x18022891c`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144adf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144b71`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144bc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144c4b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144adf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144b71`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144bc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180144c4b`

## string_xrefs

- `0x180144bb9`: `CONVEXCOMBINATION`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall inverted::COrCursor::GetRank(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v11; // r14
  __int64 v12; // r15
  __int64 result; // rax
  int v14; // edx
  const WCHAR *v15; // rdi
  int v16; // edx
  _QWORD *v17; // rcx
  _QWORD *v18; // rdx
  int v19; // edx
  int v20; // edx
  _QWORD v22[7]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v23; // [rsp+98h] [rbp-68h]
  _QWORD v24[7]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v25; // [rsp+D8h] [rbp-28h]
  _QWORD v26[7]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v27; // [rsp+118h] [rbp+18h]
  _QWORD v28[7]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v29; // [rsp+158h] [rbp+58h]
  _QWORD v30[7]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD *v31; // [rsp+198h] [rbp+98h]
  _QWORD v32[7]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD *v33; // [rsp+1D8h] [rbp+D8h]

  v11 = a6;
  v12 = a7;
  if ( *(_WORD *)(a1 + 32) != 0xFFFF )
    return inverted::FillRankConstant(
             a5,
             a6,
             a7,
             1000,
             (a1 + 128) & -(__int64)((*(_DWORD *)(a1 + 152) & 8) != 0),
             (inverted::CRankCoercion *)(a1 + 32));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
  {
    v15 = (const WCHAR *)(a1 + 48);
    if ( *(_QWORD *)(a1 + 72) > 7u )
      v15 = *(const WCHAR **)v15;
    if ( CompareStringOrdinal(v15, -1, L"ADD", -1, 1) == 2 )
    {
      v22[0] = off_1802C6320;
      v22[1] = a1;
      v23 = v22;
      LOBYTE(v16) = 1;
      result = inverted::GetData(0, v16, (int)a1 + 8, a2, a3, a4, a5, v11, v12, (__int64)v22);
      v17 = v23;
      if ( !v23 )
        return result;
      v18 = v22;
    }
    else
    {
      if ( CompareStringOrdinal(v15, -1, L"FILESEARCH1", -1, 1) == 2 )
        return inverted::RRFRankMerge((int)a1 + 8, a2, a3, a4, (__int64)&a5, v11, v12);
      if ( CompareStringOrdinal(v15, -1, L"CONVEXCOMBINATION", -1, 1) == 2 )
      {
        v24[0] = off_1802C62F0;
        v24[1] = a1;
        v25 = v24;
        result = inverted::ConvexCombinationRankMerge((int)a1 + 8, a2, a3, a4, (__int64)&a5, v11, v12, (__int64)v24);
        v17 = v25;
        if ( !v25 )
          return result;
        v18 = v24;
      }
      else if ( CompareStringOrdinal(v15, -1, L"MIN", -1, 1) == 2 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55652650>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55652650>::GetImpl'::`2'::impl) )
        {
          v28[0] = off_1802C6290;
          v28[1] = a1;
          v29 = v28;
          LOBYTE(v20) = 1;
          result = inverted::GetData(1001, v20, (int)a1 + 8, a2, a3, a4, a5, v11, v12, (__int64)v28);
          v17 = v29;
          if ( !v29 )
            return result;
          v18 = v28;
        }
        else
        {
          v26[0] = off_1802C6350;
          v26[1] = a1;
          v27 = v26;
          LOBYTE(v20) = 1;
          result = inverted::GetData(1000, v20, (int)a1 + 8, a2, a3, a4, a5, v11, v12, (__int64)v26);
          v17 = v27;
          if ( !v27 )
            return result;
          v18 = v26;
        }
      }
      else
      {
        v30[0] = off_1802C6260;
        v30[1] = a1;
        v31 = v30;
        LOBYTE(v19) = 1;
        result = inverted::GetData(0, v19, (int)a1 + 8, a2, a3, a4, a5, v11, v12, (__int64)v30);
        v17 = v31;
        if ( !v31 )
          return result;
        v18 = v30;
      }
    }
  }
  else
  {
    v32[0] = off_1802C62C0;
    v32[1] = a1;
    v33 = v32;
    LOBYTE(v14) = 1;
    result = inverted::GetData(0, v14, (int)a1 + 8, a2, a3, a4, a5, v11, v12, (__int64)v32);
    v17 = v33;
    if ( !v33 )
      return result;
    v18 = v32;
  }
  LOBYTE(v18) = v17 != v18;
  return (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(*v17 + 32LL))(v17, v18);
}

```

## disassembly

```asm
0x180144a10  push    rbp
0x180144a12  push    rbx
0x180144a13  push    rdi
0x180144a14  push    r12
0x180144a16  push    r13
0x180144a18  push    r14
0x180144a1a  push    r15
0x180144a1c  lea     rbp, [rsp-0F0h]
0x180144a24  sub     rsp, 1F0h
0x180144a2b  mov     rax, cs:__security_cookie
0x180144a32  xor     rax, rsp
0x180144a35  mov     [rbp+120h+var_40], rax
0x180144a3c  mov     rdi, r9
0x180144a3f  mov     [rsp+220h+var_1D0], r9
0x180144a44  mov     r13, r8
0x180144a47  mov     r12, rdx
0x180144a4a  mov     rbx, rcx
0x180144a4d  mov     r14, [rbp+120h+arg_28]
0x180144a54  mov     r15, [rbp+120h+arg_30]
0x180144a5b  lea     rdx, [rcx+20h]
0x180144a5f  mov     eax, 0FFFFh
0x180144a64  cmp     [rdx], ax
0x180144a67  jz      short loc_180144AA3
0x180144a69  mov     eax, [rcx+98h]
0x180144a6f  and     al, 8
0x180144a71  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180144a75  neg     al
0x180144a77  sbb     r8, r8
0x180144a7a  and     r8, rcx
0x180144a7d  mov     r9d, 3E8h; int
0x180144a83  mov     [rsp+220h+var_1F8], rdx; inverted::CRankCoercion *
0x180144a88  mov     qword ptr [rsp+220h+bIgnoreCase], r8; __int64
0x180144a8d  mov     r8, r15; int
0x180144a90  mov     rdx, r14; int
0x180144a93  mov     ecx, [rbp+120h+arg_20]; int
0x180144a99  call    ?FillRankConstant@inverted@@YAXIPEBIPEAGGPEAU?$dynamic_sparse_bit@_K@@AEAVCRankCoercion@1@@Z; inverted::FillRankConstant(uint,uint const *,ushort *,ushort,dynamic_sparse_bit<unsigned __int64> *,inverted::CRankCoercion &)
0x180144a9e  jmp     loc_180144E34
0x180144aa3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x180144aaa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x180144aaf  test    al, al
0x180144ab1  jz      loc_180144DB1
0x180144ab7  lea     rdi, [rbx+30h]
0x180144abb  cmp     qword ptr [rdi+18h], 7
0x180144ac0  jbe     short loc_180144AC5
0x180144ac2  mov     rdi, [rdi]
0x180144ac5  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x180144acd  or      eax, 0FFFFFFFFh
0x180144ad0  mov     r9d, eax; cchCount2
0x180144ad3  lea     r8, aAdd_2; "ADD"
0x180144ada  mov     edx, eax; cchCount1
0x180144adc  mov     rcx, rdi; lpString1
0x180144adf  call    cs:__imp_CompareStringOrdinal
0x180144ae5  cmp     eax, 2
0x180144ae8  jnz     short loc_180144B59
0x180144aea  lea     rax, off_1802C6320
0x180144af1  mov     [rsp+220h+var_1C0], rax
0x180144af6  mov     [rsp+220h+var_1B8], rbx
0x180144afb  lea     rax, [rsp+220h+var_1C0]
0x180144b00  mov     [rbp+120h+var_188], rax
0x180144b04  lea     r8, [rbx+8]
0x180144b08  xor     ecx, ecx
0x180144b0a  lea     rax, [rsp+220h+var_1C0]
0x180144b0f  mov     [rsp+220h+var_1D8], rax
0x180144b14  mov     [rsp+220h+var_1E0], r15
0x180144b19  mov     [rsp+220h+var_1E8], r14
0x180144b1e  mov     eax, [rbp+120h+arg_20]
0x180144b24  mov     dword ptr [rsp+220h+var_1F0], eax
0x180144b28  mov     rax, [rsp+220h+var_1D0]
0x180144b2d  mov     [rsp+220h+var_1F8], rax
0x180144b32  mov     qword ptr [rsp+220h+bIgnoreCase], r13
0x180144b37  mov     r9, r12
0x180144b3a  mov     dl, 1
0x180144b3c  call    ?GetData@inverted@@YAXG_NAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAGAEBV?$function@$$A6AGGG@Z@3@@Z; inverted::GetData(ushort,bool,std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *,std::function<ushort (ushort,ushort)> const &)
0x180144b41  nop
0x180144b42  mov     rcx, [rbp+120h+var_188]
0x180144b46  test    rcx, rcx
0x180144b49  jz      loc_180144E34
0x180144b4f  lea     rdx, [rsp+220h+var_1C0]
0x180144b54  jmp     loc_180144E22
0x180144b59  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x180144b61  or      edx, 0FFFFFFFFh; cchCount1
0x180144b64  mov     r9d, edx; cchCount2
0x180144b67  lea     r8, aFilesearch1; "FILESEARCH1"
0x180144b6e  mov     rcx, rdi; lpString1
0x180144b71  call    cs:__imp_CompareStringOrdinal
0x180144b77  cmp     eax, 2
0x180144b7a  jnz     short loc_180144BAB
0x180144b7c  lea     rcx, [rbx+8]
0x180144b80  mov     [rsp+220h+var_1F0], r15
0x180144b85  mov     [rsp+220h+var_1F8], r14
0x180144b8a  lea     rax, [rbp+120h+arg_20]
0x180144b91  mov     qword ptr [rsp+220h+bIgnoreCase], rax
0x180144b96  mov     r9, [rsp+220h+var_1D0]
0x180144b9b  mov     r8, r13
0x180144b9e  mov     rdx, r12
0x180144ba1  call    ?RRFRankMerge@inverted@@YAXAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@AEAIPEBIPEAG@Z; inverted::RRFRankMerge(std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint &,uint const *,ushort *)
0x180144ba6  jmp     loc_180144E34
0x180144bab  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x180144bb3  or      eax, 0FFFFFFFFh
0x180144bb6  mov     r9d, eax; cchCount2
0x180144bb9  lea     r8, aConvexcombinat; "CONVEXCOMBINATION"
0x180144bc0  mov     edx, eax; cchCount1
0x180144bc2  mov     rcx, rdi; lpString1
0x180144bc5  call    cs:__imp_CompareStringOrdinal
0x180144bcb  cmp     eax, 2
0x180144bce  jnz     short loc_180144C31
0x180144bd0  lea     rax, off_1802C62F0
0x180144bd7  mov     [rbp+120h+var_180], rax
0x180144bdb  mov     [rbp+120h+var_178], rbx
0x180144bdf  lea     rax, [rbp+120h+var_180]
0x180144be3  mov     [rbp+120h+var_148], rax
0x180144be7  lea     rcx, [rbx+8]
0x180144beb  lea     rax, [rbp+120h+var_180]
0x180144bef  mov     [rsp+220h+var_1E8], rax
0x180144bf4  mov     [rsp+220h+var_1F0], r15
0x180144bf9  mov     [rsp+220h+var_1F8], r14
0x180144bfe  lea     rax, [rbp+120h+arg_20]
0x180144c05  mov     qword ptr [rsp+220h+bIgnoreCase], rax
0x180144c0a  mov     r9, [rsp+220h+var_1D0]
0x180144c0f  mov     r8, r13
0x180144c12  mov     rdx, r12
0x180144c15  call    ?ConvexCombinationRankMerge@inverted@@YAXAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@AEAIPEBIPEAGAEBV?$function@$$A6AGG@Z@3@@Z; inverted::ConvexCombinationRankMerge(std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint &,uint const *,ushort *,std::function<ushort (ushort)> const &)
0x180144c1a  nop
0x180144c1b  mov     rcx, [rbp+120h+var_148]
0x180144c1f  test    rcx, rcx
0x180144c22  jz      loc_180144E34
0x180144c28  lea     rdx, [rbp+120h+var_180]
0x180144c2c  jmp     loc_180144E22
0x180144c31  mov     [rsp+220h+bIgnoreCase], 1; bIgnoreCase
0x180144c39  or      eax, 0FFFFFFFFh
0x180144c3c  mov     r9d, eax; cchCount2
0x180144c3f  lea     r8, aMin_3; "MIN"
0x180144c46  mov     edx, eax; cchCount1
0x180144c48  mov     rcx, rdi; lpString1
0x180144c4b  call    cs:__imp_CompareStringOrdinal
0x180144c51  cmp     eax, 2
0x180144c54  jnz     loc_180144D44
0x180144c5a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55652650@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55652650@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55652650> `wil::Feature<__WilFeatureTraits_Feature_55652650>::GetImpl(void)'::`2'::impl
0x180144c61  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55652650@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55652650>::__private_IsEnabled(void)
0x180144c66  test    al, al
0x180144c68  jnz     short loc_180144CD7
0x180144c6a  lea     rax, off_1802C6350
0x180144c71  mov     [rbp+120h+var_140], rax
0x180144c75  mov     [rbp+120h+var_138], rbx
0x180144c79  lea     rax, [rbp+120h+var_140]
0x180144c7d  mov     [rbp+120h+var_108], rax
0x180144c81  lea     r8, [rbx+8]
0x180144c85  mov     ecx, 3E8h
0x180144c8a  lea     rax, [rbp+120h+var_140]
0x180144c8e  mov     [rsp+220h+var_1D8], rax
0x180144c93  mov     [rsp+220h+var_1E0], r15
0x180144c98  mov     [rsp+220h+var_1E8], r14
0x180144c9d  mov     eax, [rbp+120h+arg_20]
0x180144ca3  mov     dword ptr [rsp+220h+var_1F0], eax
0x180144ca7  mov     rax, [rsp+220h+var_1D0]
0x180144cac  mov     [rsp+220h+var_1F8], rax
0x180144cb1  mov     qword ptr [rsp+220h+bIgnoreCase], r13
0x180144cb6  mov     r9, r12
0x180144cb9  mov     dl, 1
0x180144cbb  call    ?GetData@inverted@@YAXG_NAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAGAEBV?$function@$$A6AGGG@Z@3@@Z; inverted::GetData(ushort,bool,std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *,std::function<ushort (ushort,ushort)> const &)
0x180144cc0  nop
0x180144cc1  mov     rcx, [rbp+120h+var_108]
0x180144cc5  test    rcx, rcx
0x180144cc8  jz      loc_180144E34
0x180144cce  lea     rdx, [rbp+120h+var_140]
0x180144cd2  jmp     loc_180144E22
0x180144cd7  lea     rax, off_1802C6290
0x180144cde  mov     [rbp+120h+var_100], rax
0x180144ce2  mov     [rbp+120h+var_F8], rbx
0x180144ce6  lea     rax, [rbp+120h+var_100]
0x180144cea  mov     [rbp+120h+var_C8], rax
0x180144cee  lea     r8, [rbx+8]
0x180144cf2  mov     ecx, 3E9h
0x180144cf7  lea     rax, [rbp+120h+var_100]
0x180144cfb  mov     [rsp+220h+var_1D8], rax
0x180144d00  mov     [rsp+220h+var_1E0], r15
0x180144d05  mov     [rsp+220h+var_1E8], r14
0x180144d0a  mov     eax, [rbp+120h+arg_20]
0x180144d10  mov     dword ptr [rsp+220h+var_1F0], eax
0x180144d14  mov     rax, [rsp+220h+var_1D0]
0x180144d19  mov     [rsp+220h+var_1F8], rax
0x180144d1e  mov     qword ptr [rsp+220h+bIgnoreCase], r13
0x180144d23  mov     r9, r12
0x180144d26  mov     dl, 1
0x180144d28  call    ?GetData@inverted@@YAXG_NAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAGAEBV?$function@$$A6AGGG@Z@3@@Z; inverted::GetData(ushort,bool,std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *,std::function<ushort (ushort,ushort)> const &)
0x180144d2d  nop
0x180144d2e  mov     rcx, [rbp+120h+var_C8]
0x180144d32  test    rcx, rcx
0x180144d35  jz      loc_180144E34
0x180144d3b  lea     rdx, [rbp+120h+var_100]
0x180144d3f  jmp     loc_180144E22
0x180144d44  lea     rax, off_1802C6260
0x180144d4b  mov     [rbp+120h+var_C0], rax
0x180144d4f  mov     [rbp+120h+var_B8], rbx
0x180144d53  lea     rax, [rbp+120h+var_C0]
0x180144d57  mov     [rbp+120h+var_88], rax
0x180144d5e  lea     r8, [rbx+8]
0x180144d62  xor     ecx, ecx
0x180144d64  lea     rax, [rbp+120h+var_C0]
0x180144d68  mov     [rsp+220h+var_1D8], rax
0x180144d6d  mov     [rsp+220h+var_1E0], r15
0x180144d72  mov     [rsp+220h+var_1E8], r14
0x180144d77  mov     eax, [rbp+120h+arg_20]
0x180144d7d  mov     dword ptr [rsp+220h+var_1F0], eax
0x180144d81  mov     rax, [rsp+220h+var_1D0]
0x180144d86  mov     [rsp+220h+var_1F8], rax
0x180144d8b  mov     qword ptr [rsp+220h+bIgnoreCase], r13
0x180144d90  mov     r9, r12
0x180144d93  mov     dl, 1
0x180144d95  call    ?GetData@inverted@@YAXG_NAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAGAEBV?$function@$$A6AGGG@Z@3@@Z; inverted::GetData(ushort,bool,std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *,std::function<ushort (ushort,ushort)> const &)
0x180144d9a  nop
0x180144d9b  mov     rcx, [rbp+120h+var_88]
0x180144da2  test    rcx, rcx
0x180144da5  jz      loc_180144E34
0x180144dab  lea     rdx, [rbp+120h+var_C0]
0x180144daf  jmp     short loc_180144E22
0x180144db1  lea     rax, off_1802C62C0
0x180144db8  mov     [rbp+120h+var_80], rax
0x180144dbf  mov     [rbp+120h+var_78], rbx
0x180144dc6  lea     rax, [rbp+120h+var_80]
0x180144dcd  mov     [rbp+120h+var_48], rax
0x180144dd4  lea     r8, [rbx+8]
0x180144dd8  xor     ecx, ecx
0x180144dda  lea     rax, [rbp+120h+var_80]
0x180144de1  mov     [rsp+220h+var_1D8], rax
0x180144de6  mov     [rsp+220h+var_1E0], r15
0x180144deb  mov     [rsp+220h+var_1E8], r14
0x180144df0  mov     eax, [rbp+120h+arg_20]
0x180144df6  mov     dword ptr [rsp+220h+var_1F0], eax
0x180144dfa  mov     [rsp+220h+var_1F8], rdi
0x180144dff  mov     qword ptr [rsp+220h+bIgnoreCase], r13
0x180144e04  mov     r9, r12
0x180144e07  mov     dl, 1
0x180144e09  call    ?GetData@inverted@@YAXG_NAEBV?$vector@V?$shared_ptr@UICursor@inverted@@@std@@V?$allocator@V?$shared_ptr@UICursor@inverted@@@std@@@2@@std@@AEBV?$vector@V?$shared_ptr@UIDecoder@inverted@@@std@@V?$allocator@V?$shared_ptr@UIDecoder@inverted@@@std@@@2@@3@PEAUIInvertedQuery@1@AEBU?$dynamic_sparse_bit@_K@@IPEBIPEAGAEBV?$function@$$A6AGGG@Z@3@@Z; inverted::GetData(ushort,bool,std::vector<std::shared_ptr<inverted::ICursor>> const &,std::vector<std::shared_ptr<inverted::IDecoder>> const &,inverted::IInvertedQuery *,dynamic_sparse_bit<unsigned __int64> const &,uint,uint const *,ushort *,std::function<ushort (ushort,ushort)> const &)
0x180144e0e  nop
0x180144e0f  mov     rcx, [rbp+120h+var_48]
0x180144e16  test    rcx, rcx
0x180144e19  jz      short loc_180144E34
0x180144e1b  lea     rdx, [rbp+120h+var_80]
0x180144e22  cmp     rcx, rdx
0x180144e25  mov     rax, [rcx]
0x180144e28  setnz   dl
0x180144e2b  mov     rax, [rax+20h]
0x180144e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144e34  mov     rcx, [rbp+120h+var_40]
0x180144e3b  xor     rcx, rsp; StackCookie
0x180144e3e  call    __security_check_cookie
0x180144e43  add     rsp, 1F0h
0x180144e4a  pop     r15
0x180144e4c  pop     r14
0x180144e4e  pop     r13
0x180144e50  pop     r12
0x180144e52  pop     rdi
0x180144e53  pop     rbx
0x180144e54  pop     rbp
0x180144e55  retn
```
