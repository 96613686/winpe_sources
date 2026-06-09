# CSearchQueryBuilder::AppendCondition(TLMString<1024,1024,1048576> *,ICondition *)

- ea: `0x1800f5e24`
- end: `0x1800f61a3`
- name: `?AppendCondition@CSearchQueryBuilder@@AEAAXPEAV?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@PEAUICondition@@@Z`
- size: `895`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f5c90`
- `0x1802112a4`

## callees

- `0x18002a3e0`
- `0x18002c7f4`
- `0x180038f08`
- `0x18008f3f0`
- `0x18008f4a4`
- `0x1800f5e24`
- `0x1801309cc`
- `0x18015e264`
- `0x18017756c`
- `0x18019c834`
- `0x180210878`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f60e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f612c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f60e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f612c`
- `PROPSYS!PSGetPropertySystem` at `0x1800f5e58`
- `PROPSYS!PSGetPropertySystem` at `0x1800f5e58`

## string_xrefs

- `0x1800f5e69`: `onecoreuap\base\appmodel\search\tquery\icommand\searchquery.cpp`
- `0x1800f5ea9`: `onecoreuap\base\appmodel\search\tquery\icommand\searchquery.cpp`
- `0x1800f5eea`: `onecoreuap\base\appmodel\search\tquery\icommand\searchquery.cpp`
- `0x1800f5f4d`: `onecoreuap\base\appmodel\search\tquery\icommand\searchquery.cpp`
- `0x1800f601d`: `onecoreuap\base\appmodel\search\tquery\icommand\searchquery.cpp`
- `0x1800f6083`: `onecoreuap\base\appmodel\search\tquery\icommand\searchquery.cpp`
- `0x1800f60f8`: `onecoreuap\base\appmodel\search\tquery\icommand\searchquery.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CSearchQueryBuilder::AppendCondition(__int64 a1, CLMString *a2, __int64 a3)
{
  HRESULT v6; // eax
  int v7; // eax
  const struct _GUID *v8; // r8
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  unsigned int i; // edi
  _QWORD *v15; // rdx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, bool); // rbx
  int v19; // eax
  int v20; // eax
  __int64 *v21; // rcx
  __int64 v22; // rax
  int v23; // ebx
  void *v24; // rcx
  void *v25; // rcx
  int v26; // [rsp+20h] [rbp-60h]
  int v27; // [rsp+20h] [rbp-60h]
  void *v28; // [rsp+48h] [rbp-38h] BYREF
  __int64 v29; // [rsp+50h] [rbp-30h] BYREF
  void *ppv; // [rsp+58h] [rbp-28h] BYREF
  _QWORD *v31; // [rsp+60h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+68h] [rbp-18h] BYREF
  _QWORD *v33; // [rsp+70h] [rbp-10h] BYREF
  _QWORD *v34; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  LPVOID pv; // [rsp+B8h] [rbp+38h] BYREF

  ppv = 0;
  v6 = PSGetPropertySystem(&GUID_9e1c40f8_a6da_4fae_a275_c7df51ccbe01, &ppv);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x285,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\searchquery.cpp",
      (const char *)(unsigned int)v6,
      v26);
  v29 = 0;
  v7 = (*(__int64 (__fastcall **)(void *, GUID *, __int64 *))(*(_QWORD *)ppv + 48LL))(
         ppv,
         &GUID_a8765599_6915_4a84_ab8c_3bf8927b06c6,
         &v29);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\searchquery.cpp",
      (const char *)(unsigned int)v7,
      v26);
  v9 = 0;
  v28 = 0;
  v10 = *(_DWORD *)(a1 + 14816);
  if ( v10 < 1792 )
  {
    v11 = CPropertySubstitution::CreateInstance(v10, *(_DWORD *)(a1 + 14820), v8, &v28);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x290,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\searchquery.cpp",
        (const char *)(unsigned int)v11,
        v26);
    v9 = (int)v28;
  }
  v27 = v9;
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 24) + 40LL))(
          *(_QWORD *)(a1 + 24),
          a3,
          v29,
          1);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x297,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\searchquery.cpp",
      (const char *)(unsigned int)v12,
      v27);
  if ( *(int *)(a1 + 14816) < 1792 )
  {
    *(_DWORD *)(a1 + 8) |= 0x40u;
    if ( *(int *)(a1 + 14820) < 6 )
      *(_DWORD *)(a1 + 8) |= 0x80u;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
  {
    v13 = (__int64)(*(_QWORD *)(a1 + 14840) - *(_QWORD *)(a1 + 14832)) >> 5;
    std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&p_pv);
    for ( i = 0; i < (unsigned int)v13; ++i )
    {
      v15 = (_QWORD *)(*(_QWORD *)(a1 + 14832) + 32LL * i);
      if ( v15[3] > 7u )
        v15 = (_QWORD *)*v15;
      v31 = v15;
      if ( v33 == v34 )
        std::vector<inverted::CDocOccReference>::_Emplace_reallocate<inverted::CDocOccReference>(&p_pv, v33, &v31);
      else
        *v33++ = v15;
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(**(_QWORD **)(a1 + 32) + 120LL))(
            *(_QWORD *)(a1 + 32),
            (unsigned __int64)p_pv & -(__int64)((_DWORD)v13 != 0),
            (unsigned int)v13);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2AE,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\searchquery.cpp",
        (const char *)(unsigned int)v16,
        v27);
    std::vector<std::pair<long,unsigned long>>::~vector<std::pair<long,unsigned long>>(&p_pv);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl) )
  {
    v17 = *(_QWORD *)(a1 + 32);
    v18 = *(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)v17 + 128LL);
    v19 = stringCmpI(*(PCNZWCH *)(a1 + 56), L".");
    v20 = v18(v17, v19 != 0);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2B2,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\searchquery.cpp",
        (const char *)(unsigned int)v20,
        v27);
  }
  pv = 0;
  v21 = *(__int64 **)(a1 + 32);
  v22 = *v21;
  p_pv = &pv;
  v33 = 0;
  LOBYTE(v34) = 1;
  v23 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD **))(v22 + 104))(
          v21,
          0,
          *(unsigned int *)(a1 + 8),
          &v33);
  if ( (_BYTE)v34 )
  {
    v24 = *p_pv;
    *p_pv = v33;
    if ( v24 )
      CoTaskMemFree(v24);
  }
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B6,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\icommand\\searchquery.cpp",
      (const char *)(unsigned int)v23,
      v27);
  CLMString::Append(a2, (const wchar_t *)pv, 0xFFFFFFFF);
  v25 = pv;
  pv = 0;
  if ( v25 )
    CoTaskMemFree(v25);
  if ( v28 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x1800f5e24  mov     [rsp-18h+arg_0], rbx
0x1800f5e29  mov     [rsp-18h+arg_8], rsi
0x1800f5e2e  push    rbp
0x1800f5e2f  push    rdi
0x1800f5e30  push    r14
0x1800f5e32  mov     rbp, rsp
0x1800f5e35  sub     rsp, 80h
0x1800f5e3c  mov     rbx, r8
0x1800f5e3f  mov     r14, rdx
0x1800f5e42  mov     rsi, rcx
0x1800f5e45  mov     [rbp+ppv], 0
0x1800f5e4d  lea     rdx, [rbp+ppv]; ppv
0x1800f5e51  lea     rcx, _GUID_9e1c40f8_a6da_4fae_a275_c7df51ccbe01; riid
0x1800f5e58  call    cs:__imp_PSGetPropertySystem
0x1800f5e5e  mov     rcx, [rbp+18h]; this
0x1800f5e62  test    eax, eax
0x1800f5e64  jns     short loc_1800F5E7B
0x1800f5e66  mov     r9d, eax; char *
0x1800f5e69  lea     r8, aOnecoreuapBase_292; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f5e70  mov     edx, 285h; void *
0x1800f5e75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f5e7b  mov     [rbp+var_30], 0
0x1800f5e83  mov     rcx, [rbp+ppv]
0x1800f5e87  mov     rax, [rcx]
0x1800f5e8a  lea     r8, [rbp+var_30]
0x1800f5e8e  lea     rdx, _GUID_a8765599_6915_4a84_ab8c_3bf8927b06c6
0x1800f5e95  mov     rax, [rax+30h]
0x1800f5e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5e9e  mov     rcx, [rbp+18h]; this
0x1800f5ea2  test    eax, eax
0x1800f5ea4  jns     short loc_1800F5EBB
0x1800f5ea6  mov     r9d, eax; char *
0x1800f5ea9  lea     r8, aOnecoreuapBase_292; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f5eb0  mov     edx, 289h; void *
0x1800f5eb5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f5ebb  xor     eax, eax
0x1800f5ebd  mov     [rbp+var_38], rax
0x1800f5ec1  mov     ecx, [rsi+39E0h]; int
0x1800f5ec7  mov     edi, 700h
0x1800f5ecc  cmp     ecx, edi
0x1800f5ece  jge     short loc_1800F5F00
0x1800f5ed0  lea     r9, [rbp+var_38]; void **
0x1800f5ed4  mov     edx, [rsi+39E4h]; int
0x1800f5eda  call    ?CreateInstance@CPropertySubstitution@@SAJHHAEBU_GUID@@PEAPEAX@Z; CPropertySubstitution::CreateInstance(int,int,_GUID const &,void * *)
0x1800f5edf  mov     rcx, [rbp+18h]; this
0x1800f5ee3  test    eax, eax
0x1800f5ee5  jns     short loc_1800F5EFC
0x1800f5ee7  mov     r9d, eax; char *
0x1800f5eea  lea     r8, aOnecoreuapBase_292; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f5ef1  mov     edx, 290h; void *
0x1800f5ef6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f5efc  mov     rax, [rbp+var_38]
0x1800f5f00  mov     [rbp+var_40], 0
0x1800f5f08  mov     rcx, [rsi+18h]
0x1800f5f0c  mov     rdx, [rcx]
0x1800f5f0f  mov     r10, [rdx+28h]
0x1800f5f13  lea     rdx, [rbp+var_40]
0x1800f5f17  mov     [rsp+80h+var_50], rdx
0x1800f5f1c  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x1800f5f23  mov     [rsp+80h+var_58], rdx
0x1800f5f28  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800f5f2d  mov     r9d, 1
0x1800f5f33  mov     r8, [rbp+var_30]
0x1800f5f37  mov     rdx, rbx
0x1800f5f3a  mov     rax, r10
0x1800f5f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5f42  mov     rcx, [rbp+18h]; this
0x1800f5f46  test    eax, eax
0x1800f5f48  jns     short loc_1800F5F5F
0x1800f5f4a  mov     r9d, eax; char *
0x1800f5f4d  lea     r8, aOnecoreuapBase_292; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f5f54  mov     edx, 297h; void *
0x1800f5f59  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f5f5f  cmp     [rsi+39E0h], edi
0x1800f5f65  jge     short loc_1800F5F79
0x1800f5f67  or      dword ptr [rsi+8], 40h
0x1800f5f6b  cmp     dword ptr [rsi+39E4h], 6
0x1800f5f72  jge     short loc_1800F5F79
0x1800f5f74  bts     dword ptr [rsi+8], 7
0x1800f5f79  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x1800f5f80  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x1800f5f85  test    al, al
0x1800f5f87  jz      loc_1800F6038
0x1800f5f8d  mov     rbx, [rsi+39F8h]
0x1800f5f94  sub     rbx, [rsi+39F0h]
0x1800f5f9b  sar     rbx, 5
0x1800f5f9f  lea     rcx, [rbp+var_18]; void *
0x1800f5fa3  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x1800f5fa8  nop
0x1800f5fa9  xor     edi, edi
0x1800f5fab  test    ebx, ebx
0x1800f5fad  jz      short loc_1800F5FF4
0x1800f5faf  mov     edx, edi
0x1800f5fb1  shl     rdx, 5
0x1800f5fb5  add     rdx, [rsi+39F0h]
0x1800f5fbc  cmp     qword ptr [rdx+18h], 7
0x1800f5fc1  jbe     short loc_1800F5FC6
0x1800f5fc3  mov     rdx, [rdx]
0x1800f5fc6  mov     [rbp+var_20], rdx
0x1800f5fca  mov     rax, [rbp+var_10]
0x1800f5fce  cmp     rax, [rbp+var_8]
0x1800f5fd2  jz      short loc_1800F5FDE
0x1800f5fd4  mov     [rax], rdx
0x1800f5fd7  add     [rbp+var_10], 8
0x1800f5fdc  jmp     short loc_1800F5FEE
0x1800f5fde  lea     r8, [rbp+var_20]
0x1800f5fe2  mov     rdx, rax
0x1800f5fe5  lea     rcx, [rbp+var_18]
0x1800f5fe9  call    ??$_Emplace_reallocate@VCDocOccReference@inverted@@@?$vector@VCDocOccReference@inverted@@V?$allocator@VCDocOccReference@inverted@@@std@@@std@@AEAAPEAVCDocOccReference@inverted@@QEAV23@$$QEAV23@@Z; std::vector<inverted::CDocOccReference>::_Emplace_reallocate<inverted::CDocOccReference>(inverted::CDocOccReference * const,inverted::CDocOccReference &&)
0x1800f5fee  inc     edi
0x1800f5ff0  cmp     edi, ebx
0x1800f5ff2  jb      short loc_1800F5FAF
0x1800f5ff4  mov     rcx, [rsi+20h]
0x1800f5ff8  mov     rax, [rcx]
0x1800f5ffb  mov     edx, ebx
0x1800f5ffd  neg     edx
0x1800f5fff  sbb     rdx, rdx
0x1800f6002  and     rdx, [rbp+var_18]
0x1800f6006  mov     r8d, ebx
0x1800f6009  mov     rax, [rax+78h]
0x1800f600d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6012  mov     rcx, [rbp+18h]; this
0x1800f6016  test    eax, eax
0x1800f6018  jns     short loc_1800F602F
0x1800f601a  mov     r9d, eax; char *
0x1800f601d  lea     r8, aOnecoreuapBase_292; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f6024  mov     edx, 2AEh; void *
0x1800f6029  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f602e  nop
0x1800f602f  lea     rcx, [rbp+var_18]
0x1800f6033  call    ??1?$vector@U?$pair@JK@std@@V?$allocator@U?$pair@JK@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<long,ulong>>::~vector<std::pair<long,ulong>>(void)
0x1800f6038  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45262758@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758> `wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl(void)'::`2'::impl
0x1800f603f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled(void)
0x1800f6044  test    al, al
0x1800f6046  jz      short loc_1800F6094
0x1800f6048  mov     rdi, [rsi+20h]
0x1800f604c  mov     rax, [rdi]
0x1800f604f  mov     rbx, [rax+80h]
0x1800f6056  lea     rdx, asc_1802EC9B0; "."
0x1800f605d  mov     rcx, [rsi+38h]; lpString1
0x1800f6061  call    ?stringCmpI@@YAHPEB_W0@Z; stringCmpI(wchar_t const *,wchar_t const *)
0x1800f6066  xor     edx, edx
0x1800f6068  test    eax, eax
0x1800f606a  setnz   dl
0x1800f606d  mov     rcx, rdi
0x1800f6070  mov     rax, rbx
0x1800f6073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6078  mov     rcx, [rbp+18h]; this
0x1800f607c  test    eax, eax
0x1800f607e  jns     short loc_1800F6094
0x1800f6080  mov     r9d, eax; char *
0x1800f6083  lea     r8, aOnecoreuapBase_292; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f608a  mov     edx, 2B2h; void *
0x1800f608f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f6094  mov     [rbp+pv], 0
0x1800f609c  mov     rcx, [rsi+20h]
0x1800f60a0  mov     rax, [rcx]
0x1800f60a3  lea     rdx, [rbp+pv]
0x1800f60a7  mov     [rbp+var_18], rdx
0x1800f60ab  mov     [rbp+var_10], 0
0x1800f60b3  mov     byte ptr [rbp+var_8], 1
0x1800f60b7  lea     r9, [rbp+var_10]
0x1800f60bb  mov     r8d, [rsi+8]
0x1800f60bf  mov     rdx, [rbp+var_40]
0x1800f60c3  mov     rax, [rax+68h]
0x1800f60c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f60cc  mov     ebx, eax
0x1800f60ce  cmp     byte ptr [rbp+var_8], 0
0x1800f60d2  jz      short loc_1800F60ED
0x1800f60d4  mov     r8, [rbp+var_18]
0x1800f60d8  mov     rcx, [r8]; pv
0x1800f60db  mov     rdx, [rbp+var_10]
0x1800f60df  mov     [r8], rdx
0x1800f60e2  test    rcx, rcx
0x1800f60e5  jz      short loc_1800F60ED
0x1800f60e7  call    cs:__imp_CoTaskMemFree
0x1800f60ed  mov     rcx, [rbp+18h]; this
0x1800f60f1  test    ebx, ebx
0x1800f60f3  jns     short loc_1800F610A
0x1800f60f5  mov     r9d, ebx; char *
0x1800f60f8  lea     r8, aOnecoreuapBase_292; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f60ff  mov     edx, 2B6h; void *
0x1800f6104  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f610a  or      r8d, 0FFFFFFFFh; unsigned int
0x1800f610e  mov     rdx, [rbp+pv]; wchar_t *
0x1800f6112  mov     rcx, r14; this
0x1800f6115  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1800f611a  nop
0x1800f611b  mov     rcx, [rbp+pv]; pv
0x1800f611f  mov     [rbp+pv], 0
0x1800f6127  test    rcx, rcx
0x1800f612a  jz      short loc_1800F6133
0x1800f612c  call    cs:__imp_CoTaskMemFree
0x1800f6132  nop
0x1800f6133  mov     rcx, [rbp+var_40]
0x1800f6137  test    rcx, rcx
0x1800f613a  jz      short loc_1800F6149
0x1800f613c  mov     rax, [rcx]
0x1800f613f  mov     rax, [rax+10h]
0x1800f6143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6148  nop
0x1800f6149  mov     rcx, [rbp+var_38]
0x1800f614d  test    rcx, rcx
0x1800f6150  jz      short loc_1800F615F
0x1800f6152  mov     rax, [rcx]
0x1800f6155  mov     rax, [rax+10h]
0x1800f6159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f615e  nop
0x1800f615f  mov     rcx, [rbp+var_30]
0x1800f6163  test    rcx, rcx
0x1800f6166  jz      short loc_1800F6175
0x1800f6168  mov     rax, [rcx]
0x1800f616b  mov     rax, [rax+10h]
0x1800f616f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6174  nop
0x1800f6175  mov     rcx, [rbp+ppv]
0x1800f6179  test    rcx, rcx
0x1800f617c  jz      short loc_1800F618B
0x1800f617e  mov     rax, [rcx]
0x1800f6181  mov     rax, [rax+10h]
0x1800f6185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f618a  nop
0x1800f618b  lea     r11, [rsp+80h+var_s0]
0x1800f6193  mov     rbx, [r11+20h]
0x1800f6197  mov     rsi, [r11+28h]
0x1800f619b  mov     rsp, r11
0x1800f619e  pop     r14
0x1800f61a0  pop     rdi
0x1800f61a1  pop     rbp
0x1800f61a2  retn
```
