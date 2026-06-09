# Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::ProcessEnd(void)

- ea: `0x180069b90`
- end: `0x18006a6d2`
- name: `?ProcessEnd@?$Connector_UpdateEventPattern@UUpdateEventPatternOther@Diagnostics@@@Diagnostics@@UEAAXXZ`
- size: `2882`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180015c50`
- `0x180018eec`
- `0x180018f80`
- `0x18001c92c`
- `0x18002a018`
- `0x18002a204`
- `0x18002d4ac`
- `0x18002da90`
- `0x180041624`
- `0x180056dc4`
- `0x18005c5d8`
- `0x1800691dc`
- `0x180069224`
- `0x180069b90`
- `0x18006b8d0`
- `0x18006b950`
- `0x18006bb54`
- `0x18006bbe4`
- `0x18006c740`
- `0x18006cb48`
- `0x18006cea4`
- `0x18006d9fc`
- `0x18006e014`
- `0x18006e12c`
- `0x18008fc58`
- `0x18008fe00`
- `0x18008ffd4`
- `0x180095af0`
- `0x1800961f0`
- `0x1800965b0`

## string_xrefs

- `0x18006a189`: `UPDATEID`
- `0x18006a312`: `COMPLETION`
- `0x18006a0f6`: `UpdateEventPattern`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_UNKNOWN **__fastcall Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::ProcessEnd(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _UNKNOWN **result; // rax
  __int64 ***v6; // rdi
  __int64 **i; // rbx
  unsigned __int64 v8; // rdi
  _QWORD *v9; // rbx
  _QWORD **v10; // rax
  _QWORD *v11; // rbx
  __int64 *v12; // rdi
  __int64 *v13; // rbx
  __int64 *v14; // r14
  _QWORD *v15; // rax
  float v16; // xmm0_4
  unsigned __int64 v17; // rax
  void *v18; // rbx
  float v19; // xmm0_4
  float v20; // xmm0_4
  unsigned __int64 v21; // rax
  void *v22; // rdx
  unsigned __int64 j; // rbx
  _QWORD *v24; // rdx
  _QWORD *v25; // r9
  __int64 v26; // rcx
  unsigned __int64 v27; // r8
  unsigned __int64 v28; // r10
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rax
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx
  __int64 v39; // rcx
  _QWORD *v40; // rdi
  _QWORD *k; // rbx
  __int64 v42; // rcx
  _QWORD *v43; // rax
  _QWORD *v44; // rax
  __int64 v45; // r8
  const wchar_t **v46; // r15
  const wchar_t *v47; // rcx
  const wchar_t *v48; // rax
  __int64 v49; // r8
  const wchar_t **v50; // r15
  const wchar_t *v51; // rcx
  const wchar_t *v52; // rax
  _QWORD *v53; // rax
  _QWORD *v54; // rax
  const wchar_t *v55; // rcx
  __int64 v56; // rax
  const wchar_t *v57; // rcx
  __int64 v58; // rax
  const wchar_t *v59; // rcx
  __int64 v60; // rax
  _QWORD *v61; // rax
  __int64 v62; // rax
  void **v63; // rax
  __int64 v64; // rcx
  _QWORD *v65; // rax
  _WORD *v66; // rdx
  void **v67; // rax
  __int64 v68; // [rsp+28h] [rbp-E0h]
  unsigned __int64 v69; // [rsp+30h] [rbp-D8h] BYREF
  __int64 *v70; // [rsp+38h] [rbp-D0h]
  _QWORD v71[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v72[2]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v73[2]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v74[2]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v75[2]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v76[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v77[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v78[2]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v79[2]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v80[2]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v81[2]; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v82[2]; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v83[2]; // [rsp+108h] [rbp+0h] BYREF
  _QWORD v84[2]; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v85[2]; // [rsp+128h] [rbp+20h] BYREF
  _QWORD v86[2]; // [rsp+138h] [rbp+30h] BYREF
  _QWORD v87[2]; // [rsp+148h] [rbp+40h] BYREF
  _QWORD v88[2]; // [rsp+158h] [rbp+50h] BYREF
  _QWORD v89[2]; // [rsp+168h] [rbp+60h] BYREF
  _QWORD v90[2]; // [rsp+178h] [rbp+70h] BYREF
  _QWORD v91[2]; // [rsp+188h] [rbp+80h] BYREF
  _QWORD v92[2]; // [rsp+198h] [rbp+90h] BYREF
  _QWORD v93[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  _QWORD v94[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  _QWORD v95[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  _QWORD v96[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  _QWORD v97[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  void *v98; // [rsp+1F8h] [rbp+F0h] BYREF
  void *Src[2]; // [rsp+208h] [rbp+100h] BYREF
  __int64 *v100; // [rsp+218h] [rbp+110h]
  unsigned __int64 v101; // [rsp+220h] [rbp+118h]
  void *v102[8]; // [rsp+228h] [rbp+120h] BYREF
  _QWORD v103[4]; // [rsp+268h] [rbp+160h] BYREF
  _QWORD v104[4]; // [rsp+288h] [rbp+180h] BYREF
  char v105; // [rsp+2A8h] [rbp+1A0h]
  char v106; // [rsp+2A9h] [rbp+1A1h]
  char v107; // [rsp+2AAh] [rbp+1A2h]
  _QWORD v108[5]; // [rsp+2B0h] [rbp+1A8h] BYREF
  _BYTE v109[378]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _BYTE v110[6]; // [rsp+452h] [rbp+34Ah] BYREF
  _UNKNOWN *retaddr; // [rsp+4A0h] [rbp+398h] BYREF

  result = &retaddr;
  if ( *(_QWORD *)(a1 + 72) && *(_QWORD *)(a1 + 24) )
  {
    v6 = *(__int64 ****)(a1 + 16);
    for ( i = *v6; i != (__int64 **)v6; i = (__int64 **)*i )
      ____Sort_unchecked_PEAUEventEntry___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__V_lambda_1___8__ProcessEnd_23_UEAAXXZ__std__YAXPEAUEventEntry___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__0_JV_lambda_1___8__ProcessEnd_23_UEAAXXZ__Z(
        i[22],
        i[23],
        0x4EC4EC4EC4EC4EC5LL * (i[23] - i[22]),
        v68);
    v8 = *(_QWORD *)(a1 + 24);
    if ( v8 > 0xA )
    {
      *(_OWORD *)Src = 0;
      v100 = 0;
      if ( v8 > 0x1FFFFFFFFFFFFFFFLL )
        std::vector<Diagnostics::SourceHandler_Tsv<Diagnostics::TsvTraitsReportingEvents>::ColumnSpec,std::allocator<Diagnostics::SourceHandler_Tsv<Diagnostics::TsvTraitsReportingEvents>::ColumnSpec>>::_Xlength(
          a1,
          a2,
          a3,
          a4,
          v68);
      v9 = std::_Allocate<16,std::_Default_allocate_traits>(8 * v8);
      memmove(v9, Src[0], (char *)Src[1] - (char *)Src[0]);
      std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>>>>::_Change_array(
        Src,
        v9,
        0,
        v8);
      v10 = *(_QWORD ***)(a1 + 16);
      v11 = *v10;
      v69 = (unsigned __int64)v11;
      v12 = (__int64 *)Src[1];
      if ( v11 != v10 )
      {
        do
        {
          if ( v12 == v100 )
          {
            std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::UpdateGroup>>>>>::_Emplace_reallocate<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::UpdateGroup>>>> const &>(
              (const void **)Src,
              v12,
              &v69);
            v12 = (__int64 *)Src[1];
          }
          else
          {
            *v12 = (__int64)v11;
            v12 = (__int64 *)((char *)Src[1] + 8);
            Src[1] = (char *)Src[1] + 8;
          }
          v11 = (_QWORD *)*v11;
          v69 = (unsigned __int64)v11;
        }
        while ( v11 != *(_QWORD **)(a1 + 16) );
      }
      v13 = (__int64 *)Src[0];
      v14 = (__int64 *)((char *)Src[0] + 80);
      if ( (char *)Src[0] + 80 != (char *)v12 )
      {
        while ( (__int64)(((char *)v12 - (char *)v13) & 0xFFFFFFFFFFFFFFF8uLL) > 256 )
        {
          ____Partition_by_median_guess_unchecked_PEAV___List_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics___std___std___std___std__V_lambda_2___M___ProcessEnd___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__UEAAXXZ__std__YA_AU__pair_PEAV___List_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics___std___std___std___std__PEAV12__0_PEAV___List_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics___std___std___std___0_0V_lambda_2___M___ProcessEnd___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__UEAAXXZ__Z(
            (__int64 **)&v69,
            v13,
            v12);
          if ( v70 > v14 )
          {
            v12 = (__int64 *)v69;
            if ( v69 <= (unsigned __int64)v14 )
              goto LABEL_19;
          }
          else
          {
            v13 = v70;
          }
        }
        ____Insertion_sort_unchecked_PEAV___List_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics___std___std___std___std__V_lambda_2___M___ProcessEnd___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__UEAAXXZ__std__YAPEAV___List_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics___std___std___std___0_QEAV10_0V_lambda_2___M___ProcessEnd___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__UEAAXXZ__Z(
          (char *)v13,
          (char *)v12);
      }
LABEL_19:
      memset(v102, 0, sizeof(v102));
      v102[2] = 0;
      v15 = operator new(0xC8u);
      *v15 = v15;
      v15[1] = v15;
      v102[1] = v15;
      memset(&v102[3], 0, 24);
      v102[6] = (void *)7;
      v102[7] = (void *)8;
      LODWORD(v102[0]) = 1065353216;
      __Assign_grow____Hash_vec_V__allocator_V___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std___std___std___std___std___std__QEAAX_KV___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std___std___std___2__Z(
        &v102[3],
        16,
        v15);
      v16 = o_ceilf_0(10.0 / *(float *)v102);
      v17 = 0;
      if ( v16 >= 9.223372e18 )
      {
        v16 = v16 - 9.223372e18;
        if ( v16 < 9.223372e18 )
          v17 = 0x8000000000000000uLL;
      }
      v18 = (void *)(v17 + (unsigned int)(int)v16);
      if ( (__int64)v102[2] < 0 )
        v19 = (float)(int)((__int64)v102[2] & 1 | ((unsigned __int64)v102[2] >> 1))
            + (float)(int)((__int64)v102[2] & 1 | ((unsigned __int64)v102[2] >> 1));
      else
        v19 = (float)SLODWORD(v102[2]);
      v20 = o_ceilf_0(v19 / *(float *)v102);
      v21 = 0;
      if ( v20 >= 9.223372e18 )
      {
        v20 = v20 - 9.223372e18;
        if ( v20 < 9.223372e18 )
          v21 = 0x8000000000000000uLL;
      }
      v22 = (void *)(v21 + (unsigned int)(int)v20);
      if ( v22 < v18 )
        v22 = v18;
      if ( v22 > v102[7] )
        std::_Hash<std::_Umap_traits<std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,0>>::_Forced_rehash(
          v102,
          v22);
      for ( j = 0; j < 0x50; j += 8LL )
      {
        v24 = *(_QWORD **)((char *)Src[0] + j);
        v25 = v24 + 2;
        if ( v24[5] > 7u )
          v25 = (_QWORD *)*v25;
        v26 = 0xCBF29CE484222325uLL;
        v27 = 0;
        v28 = 2LL * v24[4];
        if ( v28 )
        {
          do
            v26 = 0x100000001B3LL * (*((unsigned __int8 *)v25 + v27++) ^ (unsigned __int64)v26);
          while ( v27 < v28 );
        }
        v29 = 2 * (*(_QWORD *)(a1 + 56) & v26);
        v30 = *(_QWORD *)(a1 + 32);
        if ( *(_QWORD **)(v30 + 8 * v29 + 8) == v24 )
        {
          if ( *(_QWORD **)(v30 + 8 * v29) == v24 )
          {
            v31 = *(_QWORD *)(a1 + 16);
            *(_QWORD *)(v30 + 8 * v29) = v31;
          }
          else
          {
            v31 = v24[1];
          }
          *(_QWORD *)(v30 + 8 * v29 + 8) = v31;
        }
        else if ( *(_QWORD **)(v30 + 8 * v29) == v24 )
        {
          *(_QWORD *)(v30 + 8 * v29) = *v24;
        }
        *(_QWORD *)v24[1] = *v24;
        *(_QWORD *)(*v24 + 8LL) = v24[1];
        --*(_QWORD *)(a1 + 24);
        v69 = (unsigned __int64)v24;
        std::_Hash<std::_Umap_traits<std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,0>>::insert(
          v102,
          v97,
          &v69,
          v25);
        std::_Node_handle<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,std::_Node_handle_map_base,std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>::~_Node_handle<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,std::_Node_handle_map_base,std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>(&v98);
        std::_Node_handle<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,std::_Node_handle_map_base,std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>::~_Node_handle<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,std::_Node_handle_map_base,std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>((void **)&v69);
      }
      if ( (void **)(a1 + 8) != v102 )
      {
        std::_Hash<std::_Umap_traits<std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,0>>::clear(a1 + 8);
        *(_DWORD *)(a1 + 8) = v102[0];
        v32 = *(void **)(a1 + 16);
        *(void **)(a1 + 16) = v102[1];
        v102[1] = v32;
        v33 = *(void **)(a1 + 24);
        *(void **)(a1 + 24) = v102[2];
        v102[2] = v33;
        v34 = *(void **)(a1 + 32);
        *(void **)(a1 + 32) = v102[3];
        v102[3] = v34;
        v35 = *(void **)(a1 + 40);
        *(void **)(a1 + 40) = v102[4];
        v102[4] = v35;
        v36 = *(void **)(a1 + 48);
        *(void **)(a1 + 48) = v102[5];
        v102[5] = v36;
        v37 = *(void **)(a1 + 56);
        *(void **)(a1 + 56) = v102[6];
        v102[6] = v37;
        v38 = *(void **)(a1 + 64);
        *(void **)(a1 + 64) = v102[7];
        v102[7] = v38;
      }
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>((__int64)&v102[3]);
      std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>>>(
        v39,
        (_QWORD **)v102[1]);
      operator delete(v102[1], 0xC8u);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>((__int64)Src);
    }
    v40 = *(_QWORD **)(a1 + 16);
    for ( k = (_QWORD *)*v40; k != v40; k = (_QWORD *)*k )
    {
      Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(
        (char *)v103,
        (__int64)(k + 6));
      if ( k[22] == k[23] )
        v42 = 0;
      else
        v42 = *(_QWORD *)(k[23] - 104LL);
      v69 = v42 / 100;
      memset(v109, 0, 0x150u);
      *(_OWORD *)Src = *(_OWORD *)&Diagnostics::OTelLogRecord::DefaultVersion;
      v71[0] = L"UpdateEventPattern";
      v71[1] = 18;
      Diagnostics::OTelLogRecord::OTelLogRecord(v109, &v69, v71, Src);
      v43 = k + 6;
      if ( k[9] > 7u )
        v43 = (_QWORD *)k[6];
      v72[0] = v43;
      v72[1] = k[8];
      v73[0] = L"PROVIDERID";
      v73[1] = 10;
      Diagnostics::OTelLogRecord::AddAttribute(v109, v73, v72);
      v44 = k + 10;
      if ( k[13] > 7u )
        v44 = (_QWORD *)*v44;
      v74[0] = v44;
      v74[1] = k[12];
      v75[0] = L"UPDATEID";
      v75[1] = 8;
      Diagnostics::OTelLogRecord::AddAttribute(v109, v75, v74);
      v45 = k[16];
      if ( v45 )
      {
        v46 = (const wchar_t **)(k + 14);
        v47 = (const wchar_t *)(k + 14);
        if ( k[17] > 7u )
          v47 = *v46;
        if ( v45 != 4 || wmemcmp(v47, L"NULL", 4u) )
        {
          v48 = (const wchar_t *)(k + 14);
          if ( k[17] > 7u )
            v48 = *v46;
          v76[0] = v48;
          v76[1] = k[16];
          v77[0] = L"TITLE";
          v77[1] = 5;
          Diagnostics::OTelLogRecord::AddAttribute(v109, v77, v76);
        }
      }
      v49 = k[20];
      if ( v49 )
      {
        v50 = (const wchar_t **)(k + 18);
        v51 = (const wchar_t *)(k + 18);
        if ( k[21] > 7u )
          v51 = *v50;
        if ( v49 != 4 || wmemcmp(v51, L"NULL", 4u) )
        {
          v52 = (const wchar_t *)(k + 18);
          if ( k[21] > 7u )
            v52 = *v50;
          v78[0] = v52;
          v78[1] = k[20];
          v79[0] = L"CATEGORY";
          v79[1] = 8;
          Diagnostics::OTelLogRecord::AddAttribute(v109, v79, v78);
        }
      }
      v53 = v103;
      if ( v103[3] > 7u )
        v53 = (_QWORD *)v103[0];
      v80[0] = v53;
      v80[1] = v103[2];
      v81[0] = L"STATE";
      v81[1] = 5;
      Diagnostics::OTelLogRecord::AddAttribute(v109, v81, v80);
      v54 = v104;
      if ( v104[3] > 7u )
        v54 = (_QWORD *)v104[0];
      v82[0] = v54;
      v82[1] = v104[2];
      v83[0] = L"COMPLETION";
      v83[1] = 10;
      Diagnostics::OTelLogRecord::AddAttribute(v109, v83, v82);
      v55 = L"false";
      if ( v105 )
        v55 = L"true";
      v56 = -1;
      do
        ++v56;
      while ( v55[v56] );
      v84[0] = v55;
      v84[1] = v56;
      v85[0] = L"ISONESHOT";
      v85[1] = 9;
      Diagnostics::OTelLogRecord::AddAttribute(v109, v85, v84);
      v57 = L"false";
      if ( v106 )
        v57 = L"true";
      v58 = -1;
      do
        ++v58;
      while ( v57[v58] );
      v86[0] = v57;
      v86[1] = v58;
      v87[0] = L"HASLOOPING";
      v87[1] = 10;
      Diagnostics::OTelLogRecord::AddAttribute(v109, v87, v86);
      v59 = L"false";
      if ( v107 )
        v59 = L"true";
      v60 = -1;
      do
        ++v60;
      while ( v59[v60] );
      v88[0] = v59;
      v88[1] = v60;
      v89[0] = L"HASERROR";
      v89[1] = 8;
      Diagnostics::OTelLogRecord::AddAttribute(v109, v89, v88);
      v61 = v108;
      if ( v108[3] > 7u )
        v61 = (_QWORD *)v108[0];
      v90[0] = v61;
      v90[1] = v108[2];
      v91[0] = L"DETAILS";
      v91[1] = 7;
      Diagnostics::OTelLogRecord::AddAttribute(v109, v91, v90);
      v62 = std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v110);
      std::wstring::wstring(Src, v62, v110);
      v63 = Src;
      if ( v101 > 7 )
        v63 = (void **)Src[0];
      v92[0] = v63;
      v92[1] = v100;
      v93[0] = L"EVENTCOUNT";
      v93[1] = 10;
      Diagnostics::OTelLogRecord::AddAttribute(v109, v93, v92);
      std::wstring::~wstring((__int64)Src);
      v64 = k[23];
      if ( k[22] != v64 )
      {
        v65 = (_QWORD *)(v64 - 96);
        if ( *(_QWORD *)(v64 - 72) > 7u )
          v65 = (_QWORD *)*v65;
        v94[0] = v65;
        v94[1] = *(_QWORD *)(v64 - 80);
        v95[0] = L"LASTEVENT";
        v95[1] = 9;
        Diagnostics::OTelLogRecord::AddAttribute(v109, v95, v94);
        if ( *(__int64 *)(k[23] - 104LL) >= 0 )
        {
          v66 = (_WORD *)std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v110);
        }
        else
        {
          v66 = (_WORD *)(std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v110) - 2);
          *v66 = 45;
        }
        std::wstring::wstring(Src, v66, v110);
        v67 = Src;
        if ( v101 > 7 )
          v67 = (void **)Src[0];
        v96[0] = v67;
        v96[1] = v100;
        v97[0] = L"LASTEVENTTIMESTAMP";
        v97[1] = 18;
        Diagnostics::OTelLogRecord::AddAttribute(v109, v97, v96);
        std::wstring::~wstring((__int64)Src);
      }
      Diagnostics::OTelFile::AppendLogRecord(
        *(Diagnostics::OTelFile **)(a1 + 72),
        (const struct Diagnostics::OTelLogRecord *)v109);
      Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v109);
      std::wstring::~wstring((__int64)v108);
      std::wstring::~wstring((__int64)v104);
      std::wstring::~wstring((__int64)v103);
    }
    result = (_UNKNOWN **)std::_Hash<std::_Umap_traits<std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,0>>::clear(a1 + 8);
    *(_QWORD *)(a1 + 72) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180069b90  mov     rax, rsp
0x180069b93  mov     [rax+10h], rbx
0x180069b97  mov     [rax+18h], rsi
0x180069b9b  mov     [rax+20h], rdi
0x180069b9f  push    rbp
0x180069ba0  push    r12
0x180069ba2  push    r13
0x180069ba4  push    r14
0x180069ba6  push    r15
0x180069ba8  lea     rbp, [rax-398h]
0x180069baf  sub     rsp, 470h
0x180069bb6  movaps  xmmword ptr [rax-38h], xmm6
0x180069bba  mov     rax, cs:__security_cookie
0x180069bc1  xor     rax, rsp
0x180069bc4  mov     [rbp+390h+var_40], rax
0x180069bcb  mov     rsi, rcx
0x180069bce  xor     r12d, r12d
0x180069bd1  cmp     [rcx+48h], r12
0x180069bd5  jz      loc_18006A697
0x180069bdb  cmp     [rcx+18h], r12
0x180069bdf  jz      loc_18006A697
0x180069be5  mov     rdi, [rcx+10h]
0x180069be9  mov     rbx, [rdi]
0x180069bec  cmp     rbx, rdi
0x180069bef  jz      short loc_180069C2C
0x180069bf1  mov     r12, 4EC4EC4EC4EC4EC5h
0x180069bfb  mov     rdx, [rbx+0B8h]
0x180069c02  mov     rcx, [rbx+0B0h]
0x180069c09  mov     r8, rdx
0x180069c0c  sub     r8, rcx
0x180069c0f  sar     r8, 3
0x180069c13  imul    r8, r12
0x180069c17  mov     r9b, byte ptr [rsp+490h+var_470]
0x180069c1c  call    ??$_Sort_unchecked@PEAUEventEntry@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@V_lambda_1_@?8??ProcessEnd@23@UEAAXXZ@@std@@YAXPEAUEventEntry@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@0_JV_lambda_1_@?8??ProcessEnd@23@UEAAXXZ@@Z; std::_Sort_unchecked<Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::EventEntry *,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ProcessEnd(void)'::`9'::_lambda_1_>(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::EventEntry *,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::EventEntry *,__int64,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ProcessEnd(void)'::`9'::_lambda_1_)
0x180069c21  mov     rbx, [rbx]
0x180069c24  cmp     rbx, rdi
0x180069c27  jnz     short loc_180069BFB
0x180069c29  xor     r12d, r12d
0x180069c2c  mov     rdi, [rsi+18h]
0x180069c30  mov     r13d, 7
0x180069c36  cmp     rdi, 0Ah
0x180069c3a  jbe     loc_18006A065
0x180069c40  xorps   xmm1, xmm1
0x180069c43  movdqu  xmmword ptr [rbp+390h+Src], xmm1
0x180069c4b  mov     [rbp+390h+var_280], r12
0x180069c52  mov     rax, 1FFFFFFFFFFFFFFFh
0x180069c5c  cmp     rdi, rax
0x180069c5f  ja      loc_18006A6CC
0x180069c65  lea     rcx, ds:0[rdi*8]
0x180069c6d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180069c72  mov     rbx, rax
0x180069c75  mov     r8, [rbp+390h+Src+8]
0x180069c7c  mov     rdx, [rbp+390h+Src]; Src
0x180069c83  sub     r8, rdx; Size
0x180069c86  mov     rcx, rax; void *
0x180069c89  call    memmove
0x180069c8e  mov     r9, rdi
0x180069c91  xor     r8d, r8d
0x180069c94  mov     rdx, rbx
0x180069c97  lea     rcx, [rbp+390h+Src]
0x180069c9e  call    ?_Change_array@?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@std@@@2@@std@@AEAAXQEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@2@_K1@Z; std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>>>>::_Change_array(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>>> * const,unsigned __int64,unsigned __int64)
0x180069ca3  mov     rax, [rsi+10h]
0x180069ca7  mov     rbx, [rax]
0x180069caa  mov     [rsp+490h+var_468], rbx
0x180069caf  mov     rdi, [rbp+390h+Src+8]
0x180069cb6  cmp     rbx, rax
0x180069cb9  jz      short loc_180069D07
0x180069cbb  cmp     rdi, [rbp+390h+var_280]
0x180069cc2  jz      short loc_180069CDB
0x180069cc4  mov     [rdi], rbx
0x180069cc7  mov     rdi, [rbp+390h+Src+8]
0x180069cce  add     rdi, 8
0x180069cd2  mov     [rbp+390h+Src+8], rdi
0x180069cd9  jmp     short loc_180069CF6
0x180069cdb  lea     r8, [rsp+490h+var_468]
0x180069ce0  mov     rdx, rdi
0x180069ce3  lea     rcx, [rbp+390h+Src]
0x180069cea  call    ??$_Emplace_reallocate@AEBV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternOther@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@std@@@?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternOther@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternOther@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@std@@@2@@std@@AEAAPEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternOther@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@1@QEAV21@AEBV21@@Z; std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::UpdateGroup>>>>>::_Emplace_reallocate<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::UpdateGroup>>>> const &>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::UpdateGroup>>>> * const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternOther>::UpdateGroup>>>> const &)
0x180069cef  mov     rdi, [rbp+390h+Src+8]
0x180069cf6  mov     rax, [rbx]
0x180069cf9  mov     rbx, rax
0x180069cfc  mov     [rsp+490h+var_468], rax
0x180069d01  cmp     rax, [rsi+10h]
0x180069d05  jnz     short loc_180069CBB
0x180069d07  mov     rbx, [rbp+390h+Src]
0x180069d0e  lea     r14, [rbx+50h]
0x180069d12  cmp     r14, rdi
0x180069d15  jz      short loc_180069D66
0x180069d17  mov     r15d, 100h
0x180069d1d  jmp     short loc_180069D4C
0x180069d1f  mov     r9b, byte ptr [rsp+490h+var_470]
0x180069d24  mov     r8, rdi
0x180069d27  mov     rdx, rbx
0x180069d2a  lea     rcx, [rsp+490h+var_468]
0x180069d2f  call    ??$_Partition_by_median_guess_unchecked@PEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@std@@V_lambda_2_@?M@??ProcessEnd@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@UEAAXXZ@@std@@YA?AU?$pair@PEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@std@@PEAV12@@0@PEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@0@0V_lambda_2_@?M@??ProcessEnd@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@UEAAXXZ@@Z; std::_Partition_by_median_guess_unchecked<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>>> *,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ProcessEnd(void)'::`12'::_lambda_2_>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>>> *,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>>> *,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ProcessEnd(void)'::`12'::_lambda_2_)
0x180069d34  cmp     [rsp+490h+var_460], r14
0x180069d39  ja      short loc_180069D42
0x180069d3b  mov     rbx, [rsp+490h+var_460]
0x180069d40  jmp     short loc_180069D4C
0x180069d42  mov     rdi, [rsp+490h+var_468]
0x180069d47  cmp     rdi, r14
0x180069d4a  jbe     short loc_180069D66
0x180069d4c  mov     rax, rdi
0x180069d4f  sub     rax, rbx
0x180069d52  and     rax, 0FFFFFFFFFFFFFFF8h
0x180069d56  cmp     rax, r15
0x180069d59  jg      short loc_180069D1F
0x180069d5b  mov     rdx, rdi
0x180069d5e  mov     rcx, rbx; Src
0x180069d61  call    ??$_Insertion_sort_unchecked@PEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@std@@V_lambda_2_@?M@??ProcessEnd@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@UEAAXXZ@@std@@YAPEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@0@QEAV10@0V_lambda_2_@?M@??ProcessEnd@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@UEAAXXZ@@Z; std::_Insertion_sort_unchecked<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>>> *,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ProcessEnd(void)'::`12'::_lambda_2_>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>>> * const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>>> * const,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ProcessEnd(void)'::`12'::_lambda_2_)
0x180069d66  xor     edx, edx; Val
0x180069d68  lea     r8d, [rdx+40h]; Size
0x180069d6c  lea     rcx, [rbp+390h+var_270]; void *
0x180069d73  call    memset
0x180069d78  mov     [rbp+390h+var_260], r12
0x180069d7f  mov     r14d, 0C8h
0x180069d85  mov     ecx, r14d; Size
0x180069d88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069d8d  mov     [rax], rax
0x180069d90  mov     [rax+8], rax
0x180069d94  mov     [rbp+390h+var_268], rax
0x180069d9b  mov     [rbp+390h+var_258], r12
0x180069da2  xorps   xmm0, xmm0
0x180069da5  movdqa  [rbp+390h+var_250], xmm0
0x180069dad  mov     [rbp+390h+var_240], r13
0x180069db4  mov     [rbp+390h+var_238], 8
0x180069dbf  mov     [rbp+390h+var_270], 3F800000h
0x180069dc9  mov     r8, rax
0x180069dcc  mov     edx, 10h
0x180069dd1  lea     rcx, [rbp+390h+var_258]
0x180069dd8  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)'::`2'::EventStats>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)'::`2'::EventStats>>>>)
0x180069ddd  nop
0x180069dde  movss   xmm0, cs:__real@41200000
0x180069de6  divss   xmm0, [rbp+390h+var_270]; X
0x180069dee  call    _o_ceilf_0
0x180069df3  xor     eax, eax
0x180069df5  mov     rdi, 8000000000000000h
0x180069dff  movss   xmm6, cs:__real@5f000000
0x180069e07  comiss  xmm0, xmm6
0x180069e0a  jb      short loc_180069E18
0x180069e0c  subss   xmm0, xmm6
0x180069e10  comiss  xmm0, xmm6
0x180069e13  jnb     short loc_180069E18
0x180069e15  mov     rax, rdi
0x180069e18  cvttss2si rbx, xmm0
0x180069e1d  add     rbx, rax
0x180069e20  mov     rcx, [rbp+390h+var_260]
0x180069e27  xorps   xmm0, xmm0
0x180069e2a  test    rcx, rcx
0x180069e2d  js      short loc_180069E36
0x180069e2f  cvtsi2ss xmm0, rcx
0x180069e34  jmp     short loc_180069E4B
0x180069e36  mov     rax, rcx
0x180069e39  shr     rax, 1
0x180069e3c  and     ecx, 1
0x180069e3f  or      rax, rcx
0x180069e42  cvtsi2ss xmm0, rax
0x180069e47  addss   xmm0, xmm0
0x180069e4b  divss   xmm0, [rbp+390h+var_270]; X
0x180069e53  call    _o_ceilf_0
0x180069e58  xor     eax, eax
0x180069e5a  comiss  xmm0, xmm6
0x180069e5d  jb      short loc_180069E6B
0x180069e5f  subss   xmm0, xmm6
0x180069e63  comiss  xmm0, xmm6
0x180069e66  jnb     short loc_180069E6B
0x180069e68  mov     rax, rdi
0x180069e6b  cvttss2si rdx, xmm0
0x180069e70  add     rdx, rax
0x180069e73  cmp     rdx, rbx
0x180069e76  cmovb   rdx, rbx
0x180069e7a  cmp     rdx, [rbp+390h+var_238]
0x180069e81  jbe     short loc_180069E8F
0x180069e83  lea     rcx, [rbp+390h+var_270]
0x180069e8a  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,0>>::_Forced_rehash(unsigned __int64)
0x180069e8f  mov     rbx, r12
0x180069e92  mov     rax, [rbp+390h+Src]
0x180069e99  mov     rdx, [rbx+rax]
0x180069e9d  mov     r10, [rdx+20h]
0x180069ea1  lea     r9, [rdx+10h]
0x180069ea5  cmp     [rdx+28h], r13
0x180069ea9  jbe     short loc_180069EAE
0x180069eab  mov     r9, [r9]
0x180069eae  mov     rcx, 0CBF29CE484222325h
0x180069eb8  mov     r8, r12
0x180069ebb  add     r10, r10
0x180069ebe  jz      short loc_180069EDE
0x180069ec0  movzx   eax, byte ptr [r8+r9]
0x180069ec5  xor     rcx, rax
0x180069ec8  mov     r11, 100000001B3h
0x180069ed2  imul    rcx, r11
0x180069ed6  inc     r8
0x180069ed9  cmp     r8, r10
0x180069edc  jb      short loc_180069EC0
0x180069ede  and     rcx, [rsi+38h]
0x180069ee2  add     rcx, rcx
0x180069ee5  mov     r8, [rsi+20h]
0x180069ee9  cmp     [r8+rcx*8+8], rdx
0x180069eee  jnz     short loc_180069F0B
0x180069ef0  cmp     [r8+rcx*8], rdx
0x180069ef4  jnz     short loc_180069F00
0x180069ef6  mov     rax, [rsi+10h]
0x180069efa  mov     [r8+rcx*8], rax
0x180069efe  jmp     short loc_180069F04
0x180069f00  mov     rax, [rdx+8]
0x180069f04  mov     [r8+rcx*8+8], rax
0x180069f09  jmp     short loc_180069F18
0x180069f0b  cmp     [r8+rcx*8], rdx
0x180069f0f  jnz     short loc_180069F18
0x180069f11  mov     rax, [rdx]
0x180069f14  mov     [r8+rcx*8], rax
0x180069f18  mov     rcx, [rdx+8]
0x180069f1c  mov     rax, [rdx]
0x180069f1f  mov     [rcx], rax
0x180069f22  mov     rcx, [rdx]
0x180069f25  mov     rax, [rdx+8]
0x180069f29  mov     [rcx+8], rax
0x180069f2d  dec     qword ptr [rsi+18h]
0x180069f31  mov     [rsp+490h+var_468], rdx
0x180069f36  lea     r8, [rsp+490h+var_468]
0x180069f3b  lea     rdx, [rbp+390h+var_2B0]
0x180069f42  lea     rcx, [rbp+390h+var_270]
0x180069f49  call    ?insert@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$_Insert_return_type@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@std@@@std@@@std@@V?$_Node_handle@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@PEAX@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@2@U_Node_handle_map_base@2@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@2@@2@$$QEAV?$_Node_handle@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@PEAX@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@2@U_Node_handle_map_base@2@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@2@@Z
0x180069f4e  lea     rcx, [rbp+390h+var_2A0]
0x180069f55  call    ??1?$_Node_handle@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@PEAX@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@2@U_Node_handle_map_base@2@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@QEAA@XZ; std::_Node_handle<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,std::_Node_handle_map_base,std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>::~_Node_handle<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,std::_Node_handle_map_base,std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>(void)
0x180069f5a  nop
0x180069f5b  lea     rcx, [rsp+490h+var_468]
0x180069f60  call    ??1?$_Node_handle@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@PEAX@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@2@U_Node_handle_map_base@2@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@QEAA@XZ; std::_Node_handle<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,std::_Node_handle_map_base,std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>::~_Node_handle<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,std::_Node_handle_map_base,std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>(void)
0x180069f65  add     rbx, 8
0x180069f69  cmp     rbx, 50h ; 'P'
0x180069f6d  jb      loc_180069E92
0x180069f73  lea     rbx, [rsi+8]
0x180069f77  lea     rax, [rbp+390h+var_270]
0x180069f7e  cmp     rbx, rax
0x180069f81  jz      loc_18006A031
0x180069f87  mov     rcx, rbx
0x180069f8a  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>>,0>>::clear(void)
0x180069f8f  mov     eax, [rbp+390h+var_270]
0x180069f95  mov     [rbx], eax
0x180069f97  mov     rcx, [rbx+8]
0x180069f9b  mov     rax, [rbp+390h+var_268]
0x180069fa2  mov     [rbx+8], rax
0x180069fa6  mov     [rbp+390h+var_268], rcx
0x180069fad  mov     rcx, [rbx+10h]
0x180069fb1  mov     rax, [rbp+390h+var_260]
0x180069fb8  mov     [rbx+10h], rax
0x180069fbc  mov     [rbp+390h+var_260], rcx
0x180069fc3  mov     rcx, [rbx+18h]
0x180069fc7  mov     rax, [rbp+390h+var_258]
0x180069fce  mov     [rbx+18h], rax
0x180069fd2  mov     [rbp+390h+var_258], rcx
0x180069fd9  mov     rcx, [rbx+20h]
0x180069fdd  mov     rax, qword ptr [rbp+390h+var_250]
0x180069fe4  mov     [rbx+20h], rax
0x180069fe8  mov     qword ptr [rbp+390h+var_250], rcx
0x180069fef  mov     rcx, [rbx+28h]
0x180069ff3  mov     rax, qword ptr [rbp+390h+var_250+8]
0x180069ffa  mov     [rbx+28h], rax
0x180069ffe  mov     qword ptr [rbp+390h+var_250+8], rcx
0x18006a005  mov     rcx, [rbx+30h]
0x18006a009  mov     rax, [rbp+390h+var_240]
0x18006a010  mov     [rbx+30h], rax
0x18006a014  mov     [rbp+390h+var_240], rcx
0x18006a01b  mov     rcx, [rbx+38h]
0x18006a01f  mov     rax, [rbp+390h+var_238]
0x18006a026  mov     [rbx+38h], rax
0x18006a02a  mov     [rbp+390h+var_238], rcx
0x18006a031  lea     rcx, [rbp+390h+var_258]
0x18006a038  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@USpanStartData@EtwFileProcessor@Diagnostics@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>(void)
0x18006a03d  mov     rdx, [rbp+390h+var_268]
0x18006a044  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *>> &,std::_List_node<std::pair<std::wstring const,Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup>,void *> *)
0x18006a049  mov     rdx, r14; unsigned __int64
0x18006a04c  mov     rcx, [rbp+390h+var_268]; void *
0x18006a053  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006a058  nop
0x18006a059  lea     rcx, [rbp+390h+Src]
0x18006a060  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@USpanStartData@EtwFileProcessor@Diagnostics@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>(void)
0x18006a065  mov     rdi, [rsi+10h]
0x18006a069  mov     rbx, [rdi]
0x18006a06c  cmp     rbx, rdi
0x18006a06f  jz      loc_18006A68A
0x18006a075  lea     r15, aTrue; "true"
0x18006a07c  lea     r14, [rbx+30h]
0x18006a080  mov     rdx, r14
0x18006a083  lea     rcx, [rbp+390h+var_230]; void *
0x18006a08a  call    ?ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@12@AEBUUpdateGroup@12@@Z; Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)
0x18006a08f  nop
0x18006a090  mov     rax, [rbx+0B8h]
0x18006a097  cmp     [rbx+0B0h], rax
0x18006a09e  jnz     short loc_18006A0A5
0x18006a0a0  mov     rcx, r12
0x18006a0a3  jmp     short loc_18006A0B0
0x18006a0a5  mov     rax, [r14+88h]
0x18006a0ac  mov     rcx, [rax-68h]
0x18006a0b0  mov     rax, 0A3D70A3D70A3D70Bh
0x18006a0ba  imul    rcx
0x18006a0bd  add     rdx, rcx
0x18006a0c0  sar     rdx, 6
0x18006a0c4  mov     rax, rdx
0x18006a0c7  shr     rax, 3Fh
  ... truncated ...
```
