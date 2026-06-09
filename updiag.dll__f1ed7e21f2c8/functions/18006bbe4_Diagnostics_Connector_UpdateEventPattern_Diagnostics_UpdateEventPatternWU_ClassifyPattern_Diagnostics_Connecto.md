# Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)

- ea: `0x18006bbe4`
- end: `0x18006c6a4`
- name: `?ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@12@AEBUUpdateGroup@12@@Z`
- size: `2752`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180069b90`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x180018f68`
- `0x180018f80`
- `0x18001abd4`
- `0x18001adcc`
- `0x18001c92c`
- `0x180020dc8`
- `0x18003b934`
- `0x180041624`
- `0x180056dc4`
- `0x1800691dc`
- `0x180069224`
- `0x18006bbe4`
- `0x18006d23c`
- `0x18006d53c`
- `0x18006d5c0`
- `0x18006dda8`
- `0x18008fc1c`
- `0x18008fe00`
- `0x1800961f0`

## string_xrefs

- `0x18006bca8`: `Incomplete`
- `0x18006bd73`: `Incomplete`
- `0x18006bd5c`: `Complete`
- `0x18006bd6a`: `Completed`
- `0x18006bce0`: `UpdateRemoved`
- `0x18006bd3f`: `UpdateRemoved`
- `0x18006bcf9`: `UpdateRemovedUnexpectedly`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
char *__fastcall Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(
        char *a1,
        __int64 a2)
{
  __int64 v4; // r12
  char *v5; // rbx
  char *v6; // rdi
  int v7; // esi
  __int64 v8; // r15
  const wchar_t *v9; // rbx
  const wchar_t *v10; // rcx
  int v11; // eax
  char v12; // bl
  wchar_t *v13; // rdx
  const wchar_t *v14; // rcx
  const wchar_t *v15; // rcx
  int v16; // eax
  wchar_t *v17; // rdx
  _QWORD *v18; // rax
  unsigned __int64 v19; // r15
  unsigned __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r13
  __int64 v23; // rbx
  __int64 v24; // rsi
  __int64 v25; // rax
  __int64 v26; // r8
  const wchar_t *v27; // rcx
  __int64 updated; // rax
  __int64 v29; // rdi
  bool v30; // al
  __int64 *v31; // rdi
  __int64 *v32; // rbx
  __m128i si128; // xmm8
  const wchar_t *v34; // rdx
  unsigned __int64 v35; // r12
  const wchar_t *v36; // rcx
  size_t v37; // r8
  int v38; // eax
  unsigned __int64 v39; // rdi
  __int64 v40; // rax
  void *v41; // rax
  __int64 v42; // rax
  __int128 v43; // xmm7
  __int128 v44; // xmm6
  void **Src; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  _QWORD *v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int128 v52; // xmm7
  __int128 v53; // xmm6
  __int64 v55; // [rsp+50h] [rbp-B8h]
  unsigned __int64 v56; // [rsp+58h] [rbp-B0h]
  __int64 v57; // [rsp+68h] [rbp-A0h]
  __int64 v58[2]; // [rsp+70h] [rbp-98h] BYREF
  __m128i v59; // [rsp+80h] [rbp-88h]
  __int64 v60; // [rsp+90h] [rbp-78h]
  __int64 v61; // [rsp+98h] [rbp-70h]
  __int128 v62; // [rsp+A0h] [rbp-68h] BYREF
  __m128i v63; // [rsp+B0h] [rbp-58h]
  __int64 v64; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-38h]
  __int64 v66; // [rsp+D8h] [rbp-30h]
  __int64 v67; // [rsp+E0h] [rbp-28h]
  char *v68; // [rsp+E8h] [rbp-20h]
  _BYTE v69[32]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v70[32]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v71[32]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v72[32]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v73[32]; // [rsp+178h] [rbp+70h] BYREF
  __int128 v74; // [rsp+198h] [rbp+90h] BYREF
  __int128 v75; // [rsp+1A8h] [rbp+A0h]
  wchar_t *S2[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  unsigned __int64 v77; // [rsp+1C8h] [rbp+C0h]
  unsigned __int64 v78; // [rsp+1D0h] [rbp+C8h]
  void *v79[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v80; // [rsp+1E8h] [rbp+E0h]
  __int64 v81; // [rsp+1F0h] [rbp+E8h]
  __int128 v82; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v83; // [rsp+208h] [rbp+100h]
  __int64 v84; // [rsp+210h] [rbp+108h]
  __int128 v85; // [rsp+218h] [rbp+110h] BYREF
  __int64 v86; // [rsp+228h] [rbp+120h]
  __int64 v87; // [rsp+230h] [rbp+128h]
  _OWORD v88[4]; // [rsp+238h] [rbp+130h] BYREF
  _BYTE v89[42]; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v90[6]; // [rsp+2A2h] [rbp+19Ah] BYREF

  v68 = a1;
  *(_OWORD *)a1 = 0;
  v4 = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 7;
  *(_WORD *)a1 = 0;
  v5 = a1 + 32;
  *((_OWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 6) = 0;
  *((_QWORD *)a1 + 7) = 7;
  *((_WORD *)a1 + 16) = 0;
  *((_WORD *)a1 + 32) = 0;
  a1[66] = 0;
  v6 = a1 + 72;
  *(_OWORD *)(a1 + 72) = 0;
  *((_QWORD *)a1 + 11) = 0;
  *((_QWORD *)a1 + 12) = 7;
  *((_WORD *)a1 + 36) = 0;
  v7 = 1;
  v8 = *(_QWORD *)(a2 + 136);
  v67 = v8;
  if ( *(_QWORD *)(a2 + 128) == v8 )
  {
    std::wstring::operator=(a1, L"InProgress");
    std::wstring::operator=(v5, L"Incomplete");
    std::wstring::operator=(v6, L"No events found");
    return a1;
  }
  v9 = (const wchar_t *)(v8 - 96);
  v10 = (const wchar_t *)(v8 - 96);
  if ( *(_QWORD *)(v8 - 96 + 24) > 7u )
    v10 = *(const wchar_t **)v9;
  if ( !wcsicmp(v10, L"UpdateRemoved") )
    goto LABEL_9;
  if ( *((_QWORD *)v9 + 3) > 7u )
    v9 = *(const wchar_t **)v9;
  v11 = wcsicmp(v9, L"UpdateRemovedUnexpectedly");
  v12 = 0;
  if ( !v11 )
LABEL_9:
    v12 = 1;
  v13 = L"InProgress";
  if ( v12 )
    v13 = L"Done";
  std::wstring::operator=(a1, v13);
  if ( !v12 )
    goto LABEL_19;
  v14 = (const wchar_t *)(v8 - 96);
  if ( *(_QWORD *)(v8 - 96 + 24) > 7u )
    v14 = *(const wchar_t **)v14;
  if ( wcsicmp(v14, L"UpdateRemoved") )
    goto LABEL_19;
  v15 = (const wchar_t *)(v8 - 32);
  if ( *(_QWORD *)(v8 - 32 + 24) > 7u )
    v15 = *(const wchar_t **)v15;
  v16 = wcsicmp(v15, L"Complete");
  v17 = L"Completed";
  if ( v16 )
LABEL_19:
    v17 = L"Incomplete";
  std::wstring::operator=(a1 + 32, v17);
  memset(v88, 0, sizeof(v88));
  LODWORD(v88[0]) = 0;
  *((_QWORD *)&v88[0] + 1) = 0;
  *(_QWORD *)&v88[1] = 0;
  v18 = std::_Allocate<16,std::_Default_allocate_traits>(0x60u);
  *v18 = v18;
  v18[1] = v18;
  *((_QWORD *)&v88[0] + 1) = v18;
  *((_QWORD *)&v88[1] + 1) = 0;
  v88[2] = 0;
  *(_QWORD *)&v88[3] = 7;
  *((_QWORD *)&v88[3] + 1) = 8;
  LODWORD(v88[0]) = 1065353216;
  __Assign_grow____Hash_vec_V__allocator_V___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std___std___std___std___std___std__QEAAX_KV___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std___std___std___2__Z(
    (char *)&v88[1] + 8,
    16,
    v18);
  v85 = 0;
  v57 = 0;
  v86 = 0;
  v60 = 7;
  v87 = 7;
  LOWORD(v85) = 0;
  v82 = 0;
  v64 = 0;
  v83 = 0;
  v61 = 7;
  v84 = 7;
  LOWORD(v82) = 0;
  *(_OWORD *)S2 = 0;
  v19 = 0;
  v77 = 0;
  v78 = 7;
  LOWORD(S2[0]) = 0;
  v20 = 0;
  v56 = 0;
  *(_OWORD *)v79 = 0;
  v65 = 0;
  v80 = 0;
  v66 = 7;
  v81 = 7;
  LOWORD(v79[0]) = 0;
  v21 = *(_QWORD *)(a2 + 136);
  v55 = v21;
  v22 = *(_QWORD *)(a2 + 128);
  if ( v22 != v21 )
  {
    v23 = v22 + 8;
    v24 = 0;
    v25 = v21;
    do
    {
      v26 = *(_QWORD *)(v23 + 16);
      if ( v26 )
      {
        v27 = (const wchar_t *)v23;
        if ( *(_QWORD *)(v23 + 24) > 7u )
          v27 = *(const wchar_t **)v23;
        if ( v26 != 4 || wmemcmp(v27, L"NULL", 4u) )
        {
          updated = ____Try_emplace_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std____V____Hash_V___Umap_traits_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z_V___Uhash_compare_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std___2__0A__std___std__IEAA_AU__pair_PEAU___List_node_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std__PEAX_std___N_1_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__1__Z(
                      (float *)v88,
                      (__int64)&v64,
                      (_QWORD *)v23);
          v29 = *(_QWORD *)updated;
          ++*(_QWORD *)(*(_QWORD *)updated + 48LL);
          if ( (unsigned __int8)Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::IsFailureResult((wchar_t *)(v23 + 32)) )
          {
            if ( !*(_BYTE *)(v29 + 56) )
            {
              *(_BYTE *)(v29 + 56) = 1;
              std::wstring::operator=((void *)(v29 + 64));
            }
            if ( !v24 )
            {
              std::wstring::operator=(&v85);
              std::wstring::operator=(&v82);
              v24 = v86;
            }
          }
        }
        v25 = v55;
      }
      v22 += 104;
      v23 += 104;
    }
    while ( v22 != v25 );
    v57 = v24;
    v60 = v87;
    v61 = v84;
    v64 = v83;
    v7 = 1;
    v4 = v65;
    v20 = 0;
  }
  v30 = *(_QWORD *)&v88[1] != 0;
  v31 = (__int64 *)*((_QWORD *)&v88[0] + 1);
  v32 = (__int64 *)**((_QWORD **)&v88[0] + 1);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( **((_QWORD **)&v88[0] + 1) != *((_QWORD *)&v88[0] + 1) )
  {
    while ( (unsigned __int64)v32[6] < 2 )
    {
LABEL_59:
      if ( *((_BYTE *)v32 + 56) )
        a1[66] = 1;
      v32 = (__int64 *)*v32;
      if ( v32 == v31 )
      {
        v39 = v81;
        v4 = v80;
        goto LABEL_64;
      }
    }
    a1[65] = 1;
    if ( v32[6] <= v20 )
    {
      if ( v32[6] != v20 )
      {
LABEL_58:
        v30 = 0;
        goto LABEL_59;
      }
      if ( v19 )
      {
        v34 = (const wchar_t *)S2;
        if ( v78 > 7 )
          v34 = S2[0];
        v35 = v32[4];
        v36 = (const wchar_t *)(v32 + 2);
        if ( (unsigned __int64)v32[5] > 7 )
          v36 = (const wchar_t *)v32[2];
        v37 = v32[4];
        if ( v19 < v35 )
          v37 = v19;
        v38 = wmemcmp(v36, v34, v37);
        if ( v38 )
        {
          if ( v38 >= 0 )
            goto LABEL_57;
        }
        else if ( v35 >= v19 )
        {
LABEL_57:
          v19 = v77;
          v20 = v56;
          goto LABEL_58;
        }
      }
    }
    std::wstring::operator=(S2);
    v56 = v32[6];
    if ( *((_BYTE *)v32 + 56) )
    {
      std::wstring::wstring((__int64)v89, (__int64)(v32 + 8));
      v7 |= 2u;
    }
    else
    {
      v62 = 0;
      v63 = si128;
      LOWORD(v62) = 0;
      v7 |= 4u;
    }
    std::wstring::operator=(v79);
    if ( (v7 & 4) != 0 )
    {
      v7 &= ~4u;
      std::wstring::~wstring((__int64)&v62);
    }
    if ( (v7 & 2) != 0 )
    {
      v7 &= ~2u;
      std::wstring::~wstring((__int64)v89);
    }
    goto LABEL_57;
  }
  v39 = v66;
LABEL_64:
  a1[64] = v30;
  v74 = 0;
  *(_QWORD *)&v75 = 0;
  *((_QWORD *)&v75 + 1) = 7;
  LOWORD(v74) = 0;
  if ( a1[65] )
  {
    v40 = std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v90);
    std::wstring::wstring(v70, v40, v90);
    if ( 0x7FFFFFFFFFFFFFFELL - v19 < 0xA )
      std::_Xlen_string();
    std::wstring::wstring(v69, v19, L" repeated ", 10);
    v41 = (void *)std::operator+<wchar_t>(v73, v69, v70);
    v42 = std::wstring::append(v41);
    *(_OWORD *)v58 = *(_OWORD *)v42;
    v43 = *(_OWORD *)v58;
    v44 = *(_OWORD *)(v42 + 16);
    *(_WORD *)v42 = 0;
    *(_QWORD *)(v42 + 16) = 0;
    *(_QWORD *)(v42 + 24) = 7;
    std::wstring::~wstring((__int64)&v74);
    v74 = v43;
    v75 = v44;
    v59 = si128;
    LOWORD(v58[0]) = 0;
    std::wstring::~wstring((__int64)v58);
    std::wstring::~wstring((__int64)v73);
    std::wstring::~wstring((__int64)v69);
    std::wstring::~wstring((__int64)v70);
    if ( v4 )
    {
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v4) < 0x11 )
        std::_Xlen_string();
      Src = v79;
      if ( v39 > 7 )
        Src = (void **)v79[0];
      std::wstring::wstring(v71, 17, Src, v4);
      v46 = std::wstring::append(v71);
      *(_OWORD *)v58 = *(_OWORD *)v46;
      v59 = *(__m128i *)(v46 + 16);
      *(_WORD *)v46 = 0;
      *(_QWORD *)(v46 + 16) = 0;
      *(_QWORD *)(v46 + 24) = 7;
      std::wstring::append(&v74);
      std::wstring::~wstring((__int64)v58);
      std::wstring::~wstring((__int64)v71);
    }
  }
  if ( a1[66] && v57 )
  {
    if ( (_QWORD)v75 )
      std::wstring::append(&v74);
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v57) < 0x15 )
      std::_Xlen_string();
    std::wstring::wstring(v72, v57, L" failed with result: ", 21);
    v47 = std::wstring::append(v72);
    *(_OWORD *)v58 = *(_OWORD *)v47;
    v59 = *(__m128i *)(v47 + 16);
    *(_WORD *)v47 = 0;
    *(_QWORD *)(v47 + 16) = 0;
    *(_QWORD *)(v47 + 24) = 7;
    std::wstring::append(&v74);
    std::wstring::~wstring((__int64)v58);
    std::wstring::~wstring((__int64)v72);
  }
  if ( !a1[64] )
    goto LABEL_80;
  if ( !(_QWORD)v75 )
  {
    std::wstring::operator=(&v74, L"Each event occurred once");
LABEL_80:
    if ( !(_QWORD)v75 )
    {
      v48 = (_QWORD *)(v67 - 96);
      v49 = *(_QWORD *)(v67 - 96 + 16);
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v49) < 0xC )
        std::_Xlen_string();
      if ( v48[3] > 7u )
        v48 = (_QWORD *)*v48;
      std::wstring::wstring(v89, 12, v48, v49);
      v50 = std::wstring::append(v89);
      v62 = 0;
      v63 = 0;
      v62 = *(_OWORD *)v50;
      v63 = *(__m128i *)(v50 + 16);
      *(_WORD *)v50 = 0;
      *(_QWORD *)(v50 + 16) = 0;
      *(_QWORD *)(v50 + 24) = 7;
      v51 = std::wstring::append(&v62);
      *(_OWORD *)v58 = *(_OWORD *)v51;
      v52 = *(_OWORD *)v58;
      v53 = *(_OWORD *)(v51 + 16);
      *(_WORD *)v51 = 0;
      *(_QWORD *)(v51 + 16) = 0;
      *(_QWORD *)(v51 + 24) = 7;
      std::wstring::~wstring((__int64)&v74);
      v74 = v52;
      v75 = v53;
      v59 = si128;
      LOWORD(v58[0]) = 0;
      std::wstring::~wstring((__int64)v58);
      std::wstring::~wstring((__int64)&v62);
      std::wstring::~wstring((__int64)v89);
    }
  }
  if ( a1 + 72 != (char *)&v74 )
  {
    std::wstring::~wstring((__int64)(a1 + 72));
    *(_OWORD *)(a1 + 72) = v74;
    *(_OWORD *)(a1 + 88) = v75;
    *(_QWORD *)&v75 = 0;
    *((_QWORD *)&v75 + 1) = 7;
    LOWORD(v74) = 0;
  }
  std::wstring::~wstring((__int64)&v74);
  std::wstring::~wstring((__int64)v79);
  std::wstring::~wstring((__int64)S2);
  std::wstring::~wstring((__int64)&v82);
  std::wstring::~wstring((__int64)&v85);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>((__int64)&v88[1] + 8);
  __1__list_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std__V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std___2__std__QEAA_XZ((void **)v88 + 1);
  return a1;
}

```

## disassembly

```asm
0x18006bbe4  mov     rax, rsp
0x18006bbe7  mov     [rax+18h], rbx
0x18006bbeb  push    rbp
0x18006bbec  push    rsi
0x18006bbed  push    rdi
0x18006bbee  push    r12
0x18006bbf0  push    r13
0x18006bbf2  push    r14
0x18006bbf4  push    r15
0x18006bbf6  lea     rbp, [rax-218h]
0x18006bbfd  sub     rsp, 2E0h
0x18006bc04  movaps  xmmword ptr [rax-48h], xmm6
0x18006bc08  movaps  xmmword ptr [rax-58h], xmm7
0x18006bc0c  movaps  xmmword ptr [rax-68h], xmm8
0x18006bc11  mov     rax, cs:__security_cookie
0x18006bc18  xor     rax, rsp
0x18006bc1b  mov     [rbp+210h+var_70], rax
0x18006bc22  mov     r13, rdx
0x18006bc25  mov     r14, rcx
0x18006bc28  mov     [rbp+210h+var_230], rcx
0x18006bc2c  mov     dword ptr [rsp+310h+var_2D0], 1
0x18006bc34  xorps   xmm0, xmm0
0x18006bc37  movups  xmmword ptr [rcx], xmm0
0x18006bc3a  xor     r12d, r12d
0x18006bc3d  mov     [rcx+10h], r12
0x18006bc41  lea     eax, [r12+7]
0x18006bc46  mov     [rcx+18h], rax
0x18006bc4a  mov     [rcx], r12w
0x18006bc4e  lea     rbx, [rcx+20h]
0x18006bc52  movups  xmmword ptr [rbx], xmm0
0x18006bc55  mov     [rbx+10h], r12
0x18006bc59  mov     [rbx+18h], rax
0x18006bc5d  mov     [rbx], r12w
0x18006bc61  mov     [rcx+40h], r12w
0x18006bc66  mov     [rcx+42h], r12b
0x18006bc6a  lea     rdi, [rcx+48h]
0x18006bc6e  movups  xmmword ptr [rdi], xmm0
0x18006bc71  mov     [rdi+10h], r12
0x18006bc75  mov     [rdi+18h], rax
0x18006bc79  mov     [rdi], r12w
0x18006bc7d  lea     esi, [rax-6]
0x18006bc80  mov     dword ptr [rsp+310h+var_2B8], esi
0x18006bc84  mov     dword ptr [rsp+310h+var_2D0], esi
0x18006bc88  mov     r15, [rdx+88h]
0x18006bc8f  mov     [rbp+210h+var_238], r15
0x18006bc93  cmp     [rdx+80h], r15
0x18006bc9a  jnz     short loc_18006BCCB
0x18006bc9c  lea     rdx, aInprogress; "InProgress"
0x18006bca3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x18006bca8  lea     rdx, aIncomplete; "Incomplete"
0x18006bcaf  mov     rcx, rbx; void *
0x18006bcb2  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x18006bcb7  lea     rdx, aNoEventsFound; "No events found"
0x18006bcbe  mov     rcx, rdi; void *
0x18006bcc1  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x18006bcc6  jmp     loc_18006C650
0x18006bccb  lea     rbx, [r15-60h]
0x18006bccf  mov     rcx, rbx
0x18006bcd2  mov     edi, 7
0x18006bcd7  cmp     [rbx+18h], rdi
0x18006bcdb  jbe     short loc_18006BCE0
0x18006bcdd  mov     rcx, [rbx]; String1
0x18006bce0  lea     rdx, aUpdateremoved; "UpdateRemoved"
0x18006bce7  call    _wcsicmp
0x18006bcec  test    eax, eax
0x18006bcee  jz      short loc_18006BD0F
0x18006bcf0  cmp     [rbx+18h], rdi
0x18006bcf4  jbe     short loc_18006BCF9
0x18006bcf6  mov     rbx, [rbx]
0x18006bcf9  lea     rdx, aUpdateremovedu; "UpdateRemovedUnexpectedly"
0x18006bd00  mov     rcx, rbx; String1
0x18006bd03  call    _wcsicmp
0x18006bd08  test    eax, eax
0x18006bd0a  mov     bl, r12b
0x18006bd0d  jnz     short loc_18006BD12
0x18006bd0f  mov     bl, sil
0x18006bd12  lea     rax, aDone; "Done"
0x18006bd19  lea     rdx, aInprogress; "InProgress"
0x18006bd20  test    bl, bl
0x18006bd22  cmovnz  rdx, rax; Src
0x18006bd26  mov     rcx, r14; void *
0x18006bd29  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x18006bd2e  test    bl, bl
0x18006bd30  jz      short loc_18006BD73
0x18006bd32  lea     rcx, [r15-60h]
0x18006bd36  cmp     [rcx+18h], rdi
0x18006bd3a  jbe     short loc_18006BD3F
0x18006bd3c  mov     rcx, [rcx]; String1
0x18006bd3f  lea     rdx, aUpdateremoved; "UpdateRemoved"
0x18006bd46  call    _wcsicmp
0x18006bd4b  test    eax, eax
0x18006bd4d  jnz     short loc_18006BD73
0x18006bd4f  lea     rcx, [r15-20h]
0x18006bd53  cmp     [rcx+18h], rdi
0x18006bd57  jbe     short loc_18006BD5C
0x18006bd59  mov     rcx, [rcx]; String1
0x18006bd5c  lea     rdx, aComplete; "Complete"
0x18006bd63  call    _wcsicmp
0x18006bd68  test    eax, eax
0x18006bd6a  lea     rdx, aCompleted; "Completed"
0x18006bd71  jz      short loc_18006BD7A
0x18006bd73  lea     rdx, aIncomplete; "Incomplete"
0x18006bd7a  lea     rcx, [r14+20h]; void *
0x18006bd7e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x18006bd83  xor     edx, edx; Val
0x18006bd85  lea     r8d, [rdx+40h]; Size
0x18006bd89  lea     rcx, [rbp+210h+var_E0]; void *
0x18006bd90  call    memset
0x18006bd95  mov     [rbp+210h+var_E0], 0
0x18006bd9f  mov     [rbp+210h+var_D8], r12
0x18006bda6  mov     [rbp+210h+var_D0], r12
0x18006bdad  mov     ecx, 60h ; '`'
0x18006bdb2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18006bdb7  mov     [rax], rax
0x18006bdba  mov     [rax+8], rax
0x18006bdbe  mov     [rbp+210h+var_D8], rax
0x18006bdc5  mov     [rbp+210h+var_C8], r12
0x18006bdcc  xorps   xmm0, xmm0
0x18006bdcf  movdqa  [rbp+210h+var_C0], xmm0
0x18006bdd7  mov     [rbp+210h+var_B0], rdi
0x18006bdde  mov     [rbp+210h+var_A8], 8
0x18006bde9  mov     [rbp+210h+var_E0], 3F800000h
0x18006bdf3  mov     r8, rax
0x18006bdf6  mov     edx, 10h
0x18006bdfb  lea     rcx, [rbp+210h+var_C8]
0x18006be02  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)'::`2'::EventStats>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)'::`2'::EventStats>>>>)
0x18006be07  nop
0x18006be08  xorps   xmm0, xmm0
0x18006be0b  movups  [rbp+210h+var_100], xmm0
0x18006be12  mov     rax, r12
0x18006be15  mov     [rsp+310h+var_2B0], rax
0x18006be1a  mov     [rbp+210h+var_F0], rax
0x18006be21  mov     [rbp+210h+var_288], rdi
0x18006be25  mov     [rbp+210h+var_E8], rdi
0x18006be2c  mov     word ptr [rbp+210h+var_100], r12w
0x18006be34  movups  [rbp+210h+var_120], xmm0
0x18006be3b  mov     [rbp+210h+var_258], r12
0x18006be3f  mov     [rbp+210h+var_110], r12
0x18006be46  mov     [rbp+210h+var_280], rdi
0x18006be4a  mov     [rbp+210h+var_108], rdi
0x18006be51  mov     word ptr [rbp+210h+var_120], r12w
0x18006be59  movups  xmmword ptr [rbp+210h+S2], xmm0
0x18006be60  mov     r15, r12
0x18006be63  mov     [rbp+210h+var_150], r12
0x18006be6a  mov     [rbp+210h+var_148], rdi
0x18006be71  mov     word ptr [rbp+210h+S2], r12w
0x18006be79  mov     rcx, r12
0x18006be7c  mov     [rsp+310h+var_2C0], rcx
0x18006be81  movups  xmmword ptr [rbp+210h+var_140], xmm0
0x18006be88  mov     [rbp+210h+var_248], r12
0x18006be8c  mov     [rbp+210h+var_130], r12
0x18006be93  mov     rdx, rdi
0x18006be96  mov     [rbp+210h+var_240], rdx
0x18006be9a  mov     [rbp+210h+var_128], rdx
0x18006bea1  xor     edx, edx
0x18006bea3  mov     word ptr [rbp+210h+var_140], dx
0x18006beaa  mov     r8, [r13+88h]
0x18006beb1  mov     [rsp+310h+var_2C8], r8
0x18006beb6  mov     r13, [r13+80h]
0x18006bebd  cmp     r13, r8
0x18006bec0  jz      loc_18006BFBE
0x18006bec6  lea     rbx, [r13+8]
0x18006beca  mov     rsi, r12
0x18006becd  mov     rax, r8
0x18006bed0  mov     r8, [rbx+10h]; N
0x18006bed4  test    r8, r8
0x18006bed7  jz      loc_18006BF7A
0x18006bedd  mov     rcx, rbx
0x18006bee0  cmp     [rbx+18h], rdi
0x18006bee4  jbe     short loc_18006BEE9
0x18006bee6  mov     rcx, [rbx]; S1
0x18006bee9  cmp     r8, 4
0x18006beed  jnz     short loc_18006BF01
0x18006beef  lea     rdx, aNull_1; "NULL"
0x18006bef6  call    wmemcmp
0x18006befb  xor     edx, edx
0x18006befd  test    eax, eax
0x18006beff  jz      short loc_18006BF75
0x18006bf01  mov     r8, rbx
0x18006bf04  lea     rdx, [rbp+210h+var_258]
0x18006bf08  lea     rcx, [rbp+210h+var_E0]
0x18006bf0f  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)'::`2'::EventStats,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)'::`2'::EventStats>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18006bf14  mov     rdi, [rax]
0x18006bf17  inc     qword ptr [rdi+30h]
0x18006bf1b  lea     r12, [rbx+20h]
0x18006bf1f  mov     rcx, r12; String
0x18006bf22  call    ?IsFailureResult@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::IsFailureResult(std::wstring const &)
0x18006bf27  xor     edx, edx
0x18006bf29  test    al, al
0x18006bf2b  jz      short loc_18006BF70
0x18006bf2d  cmp     [rdi+38h], dl
0x18006bf30  jnz     short loc_18006BF44
0x18006bf32  mov     byte ptr [rdi+38h], 1
0x18006bf36  lea     rcx, [rdi+40h]; void *
0x18006bf3a  mov     rdx, r12
0x18006bf3d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006bf42  xor     edx, edx
0x18006bf44  test    rsi, rsi
0x18006bf47  jnz     short loc_18006BF70
0x18006bf49  mov     rdx, rbx
0x18006bf4c  lea     rcx, [rbp+210h+var_100]; void *
0x18006bf53  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006bf58  mov     rdx, r12
0x18006bf5b  lea     rcx, [rbp+210h+var_120]; void *
0x18006bf62  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006bf67  mov     rsi, [rbp+210h+var_F0]
0x18006bf6e  xor     edx, edx
0x18006bf70  mov     edi, 7
0x18006bf75  mov     rax, [rsp+310h+var_2C8]
0x18006bf7a  add     r13, 68h ; 'h'
0x18006bf7e  add     rbx, 68h ; 'h'
0x18006bf82  cmp     r13, rax
0x18006bf85  jnz     loc_18006BED0
0x18006bf8b  mov     [rsp+310h+var_2B0], rsi
0x18006bf90  mov     rax, [rbp+210h+var_E8]
0x18006bf97  mov     [rbp+210h+var_288], rax
0x18006bf9b  mov     rax, [rbp+210h+var_108]
0x18006bfa2  mov     [rbp+210h+var_280], rax
0x18006bfa6  mov     rax, [rbp+210h+var_110]
0x18006bfad  mov     [rbp+210h+var_258], rax
0x18006bfb1  mov     esi, dword ptr [rsp+310h+var_2B8]
0x18006bfb5  mov     r12, [rbp+210h+var_248]
0x18006bfb9  mov     rcx, [rsp+310h+var_2C0]
0x18006bfbe  xor     r13d, r13d
0x18006bfc1  cmp     [rbp+210h+var_D0], r13
0x18006bfc8  setnz   al
0x18006bfcb  mov     rdi, [rbp+210h+var_D8]
0x18006bfd2  mov     rbx, [rdi]
0x18006bfd5  movdqa  xmm8, cs:__xmm@00000000000000070000000000000000
0x18006bfde  cmp     rbx, rdi
0x18006bfe1  jz      loc_18006C125
0x18006bfe7  cmp     qword ptr [rbx+30h], 2
0x18006bfec  jb      loc_18006C0FB
0x18006bff2  mov     byte ptr [r14+41h], 1
0x18006bff7  cmp     [rbx+30h], rcx
0x18006bffb  ja      short loc_18006C055
0x18006bffd  jnz     loc_18006C0F3
0x18006c003  test    r15, r15
0x18006c006  jz      short loc_18006C055
0x18006c008  lea     rdx, [rbp+210h+S2]
0x18006c00f  cmp     [rbp+210h+var_148], 7
0x18006c017  cmova   rdx, [rbp+210h+S2]; S2
0x18006c01f  mov     r12, [rbx+20h]
0x18006c023  lea     rcx, [rbx+10h]
0x18006c027  cmp     qword ptr [rbx+28h], 7
0x18006c02c  jbe     short loc_18006C032
0x18006c02e  mov     rcx, [rbx+10h]; S1
0x18006c032  mov     r8, r12
0x18006c035  cmp     r15, r12
0x18006c038  cmovb   r8, r15; N
0x18006c03c  call    wmemcmp
0x18006c041  test    eax, eax
0x18006c043  jz      short loc_18006C04C
0x18006c045  js      short loc_18006C055
0x18006c047  jmp     loc_18006C0E7
0x18006c04c  cmp     r12, r15
0x18006c04f  jnb     loc_18006C0E7
0x18006c055  lea     rdx, [rbx+10h]
0x18006c059  lea     rcx, [rbp+210h+S2]; void *
0x18006c060  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006c065  mov     rax, [rbx+30h]
0x18006c069  mov     [rsp+310h+var_2C0], rax
0x18006c06e  xor     eax, eax
0x18006c070  cmp     [rbx+38h], al
0x18006c073  jz      short loc_18006C08B
0x18006c075  lea     rdx, [rbx+40h]
0x18006c079  lea     rcx, [rbp+210h+var_A0]
0x18006c080  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006c085  nop
0x18006c086  or      esi, 2
0x18006c089  jmp     short loc_18006C0A3
0x18006c08b  xorps   xmm0, xmm0
0x18006c08e  movups  [rbp+210h+var_278], xmm0
0x18006c092  movdqu  [rbp+210h+var_268], xmm8
0x18006c098  mov     word ptr [rbp+210h+var_278], ax
0x18006c09c  lea     rax, [rbp+210h+var_278]
0x18006c0a0  or      esi, 4
0x18006c0a3  mov     dword ptr [rsp+310h+var_2D0], esi
0x18006c0a7  mov     rdx, rax
0x18006c0aa  lea     rcx, [rbp+210h+var_140]; void *
0x18006c0b1  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006c0b6  nop
0x18006c0b7  test    sil, 4
0x18006c0bb  jz      short loc_18006C0CE
0x18006c0bd  and     esi, 0FFFFFFFBh
0x18006c0c0  mov     dword ptr [rsp+310h+var_2D0], esi
0x18006c0c4  lea     rcx, [rbp+210h+var_278]
0x18006c0c8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006c0cd  nop
0x18006c0ce  test    sil, 2
0x18006c0d2  jz      short loc_18006C0E7
0x18006c0d4  and     esi, 0FFFFFFFDh
0x18006c0d7  mov     dword ptr [rsp+310h+var_2D0], esi
0x18006c0db  lea     rcx, [rbp+210h+var_A0]
0x18006c0e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006c0e7  mov     r15, [rbp+210h+var_150]
0x18006c0ee  mov     rcx, [rsp+310h+var_2C0]
0x18006c0f3  xor     r13d, r13d
0x18006c0f6  mov     al, r13b
0x18006c0f9  jmp     short loc_18006C0FE
  ... truncated ...
```
