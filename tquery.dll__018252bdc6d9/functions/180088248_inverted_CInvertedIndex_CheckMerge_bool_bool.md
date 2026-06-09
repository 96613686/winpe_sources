# inverted::CInvertedIndex::_CheckMerge(bool,bool)

- ea: `0x180088248`
- end: `0x180088b2b`
- name: `?_CheckMerge@CInvertedIndex@inverted@@AEAAX_N0@Z`
- size: `2275`
- prototype: `void __fastcall(inverted::CInvertedIndex *__hidden this, bool, bool)`
- caller_count: `3`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x1800785dc`
- `0x180087940`
- `0x18021a9d0`

## callees

- `0x18002a3e0`
- `0x18002a3f8`
- `0x18002ca28`
- `0x18002d30c`
- `0x1800324c8`
- `0x180036d60`
- `0x180047e78`
- `0x180048890`
- `0x180048b10`
- `0x18004d9d8`
- `0x180050858`
- `0x18005b8c8`
- `0x18007aca0`
- `0x180088248`
- `0x180088bc8`
- `0x180088c84`
- `0x180088d18`
- `0x180088d80`
- `0x180089084`
- `0x1800de9a4`
- `0x1800eaa2c`
- `0x1800ef1a0`
- `0x1801183f0`
- `0x1801470d4`
- `0x180147190`
- `0x18015708c`
- `0x18016d8d4`
- `0x18016f9fc`
- `0x18017787c`
- `0x180178344`
- `0x180188d90`
- `0x180188dc0`
- `0x180189cce`
- `0x1802173a4`
- `0x1802185dc`
- `0x18021d780`
- `0x180294310`
- `0x1802c0010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800888cd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800888cd`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800885ef`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180088638`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800885ef`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180088638`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008884c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008884c`

## string_xrefs

- `0x18008860d`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180088656`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall inverted::CInvertedIndex::_CheckMerge(inverted::CInvertedIndex *this, char a2, char a3)
{
  char *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int *v9; // r13
  unsigned __int64 v10; // rax
  unsigned int **v11; // rbx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  __int64 *v14; // r8
  __int64 *v15; // rcx
  __int64 *v16; // rdx
  unsigned int v17; // ebx
  unsigned int **v18; // r14
  unsigned int v19; // edx
  unsigned int *v20; // rax
  unsigned int *v21; // r12
  __int64 v22; // r15
  __int64 v23; // rax
  void **v24; // rax
  void *v25; // rbx
  unsigned int *v26; // r15
  unsigned __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rax
  unsigned int v30; // r15d
  unsigned int v31; // edx
  _QWORD *v32; // r12
  __int64 v33; // r14
  __int64 v34; // rax
  void **v35; // rax
  void *v36; // rbx
  unsigned __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // r8
  void *v41; // rax
  const char *v42; // r9
  __int64 v43; // r8
  void *v44; // rax
  const char *v45; // r9
  unsigned int v46; // r14d
  unsigned int **v47; // r12
  char IndicesToMerge; // r15
  unsigned int v49; // eax
  char *v50; // rcx
  __int64 v51; // rax
  __int64 *v52; // r10
  __int64 v53; // rbx
  char *v54; // rax
  unsigned int v55; // edx
  int v56; // ecx
  __int64 v57; // rbx
  _QWORD *v58; // rdx
  unsigned __int64 v59; // rdx
  _QWORD *v60; // rdx
  unsigned __int64 v61; // rdx
  __int64 v62; // rbx
  __int64 v63; // r13
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // r9
  char v68[8]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int *v69; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v70; // [rsp+30h] [rbp-D0h]
  void *v71; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v72; // [rsp+40h] [rbp-C0h]
  unsigned int *v73; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v74; // [rsp+50h] [rbp-B0h]
  unsigned int v75; // [rsp+54h] [rbp-ACh]
  __int64 v76; // [rsp+58h] [rbp-A8h]
  unsigned int **v77; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v78; // [rsp+68h] [rbp-98h]
  __int64 v79; // [rsp+70h] [rbp-90h]
  char *v80; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v81; // [rsp+80h] [rbp-80h]
  unsigned __int64 v82; // [rsp+88h] [rbp-78h] BYREF
  __int64 v83; // [rsp+90h] [rbp-70h] BYREF
  __int64 v84; // [rsp+98h] [rbp-68h]
  __int64 v85; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v86; // [rsp+B0h] [rbp-50h]
  _DWORD v87[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v88; // [rsp+D0h] [rbp-30h]
  unsigned int v89; // [rsp+D4h] [rbp-2Ch]
  int v90; // [rsp+D8h] [rbp-28h]
  int v91; // [rsp+E8h] [rbp-18h]
  int v92; // [rsp+ECh] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+1508h] [rbp+1408h]

  (*(void (__fastcall **)(_QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30), &v85, 0);
  v6 = (char *)(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v85 + 8LL))(v85);
  inverted::CInvertedIndex::_RestartPausedMerges(this);
  if ( a2 )
  {
    LOBYTE(v7) = a3;
    if ( (unsigned __int8)inverted::CInvertedIndex::_CheckMasterMerge(this, v7, &v85) )
    {
      *((_BYTE *)this + 624) = 0;
      if ( *((_QWORD *)this + 77) <= 1u )
        MicrosoftTelemetryAssertTriggeredNoArgs(v8);
      v69 = (unsigned int *)*((_QWORD *)this + 76);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned int>>,std::_Iterator_base0>::operator--(&v69);
      v53 = *v52;
      v54 = (char *)operator new(0x20u);
      v80 = v54;
      *(_OWORD *)v54 = 0;
      *((_DWORD *)v54 + 2) = 1;
      *((_DWORD *)v54 + 3) = 1;
      *(_QWORD *)v54 = &std::_Ref_count_obj2<inverted::SMergeData>::`vftable';
      v55 = v69[7];
      v56 = *(_DWORD *)(v53 + 28);
      *((_WORD *)v54 + 8) = 1;
      *((_DWORD *)v54 + 5) = v56;
      *((_DWORD *)v54 + 6) = v55;
      *((_DWORD *)v54 + 7) = -1;
      v80 = v54 + 16;
      v81 = (std::_Ref_count_base *)v54;
      std::shared_ptr<inverted::CQueryOperator>::operator=<inverted::CNoneOperator,0>((char *)this + 520, &v80);
      if ( v81 )
        std::_Ref_count_base::_Decref(v81);
      std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::clear((char *)this + 608);
      *((_BYTE *)this + 481) = 1;
      SubmitThreadpoolWork(*((PTP_WORK *)this + 59));
      goto LABEL_58;
    }
  }
  if ( *((_BYTE *)this + 624) )
    goto LABEL_58;
  v80 = v6;
  v73 = 0;
  v74 = -1;
  v75 = -1;
  v76 = 0;
  dynamic_sparse_bit<unsigned __int64>::Empty(&v73);
  v9 = (unsigned int *)((char *)this + 904);
  v73 = (unsigned int *)((char *)this + 904);
  std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v77);
  v10 = (unsigned int)(*((_DWORD *)this + 93) - 1);
  v11 = v77;
  v12 = 0xAAAAAAAAAAAAAAABuLL * ((v78 - (__int64)v77) >> 3);
  if ( v10 < v12 )
  {
    v57 = (__int64)&v77[3 * v10];
    std::_Destroy_range<std::allocator<dynamic_sparse_bit<unsigned __int64>>>(v57, v78);
    v78 = v57;
LABEL_8:
    v11 = v77;
    goto LABEL_9;
  }
  if ( v10 > v12 )
  {
    if ( v10 <= 0xAAAAAAAAAAAAAAABuLL * ((v79 - (__int64)v77) >> 3) )
      v78 = std::_Uninitialized_value_construct_n<std::allocator<dynamic_sparse_bit<unsigned __int64>>>(v78, v10 - v12);
    else
      std::vector<dynamic_sparse_bit<unsigned __int64>>::_Resize_reallocate<std::_Value_init_tag>(&v77);
    goto LABEL_8;
  }
LABEL_9:
  while ( v11 != (unsigned int **)v78 )
  {
    dynamic_sparse_bit<unsigned __int64>::Empty(v11);
    *v11 = v9;
    v11 += 3;
  }
  LODWORD(v13) = 0;
  v82 = 0;
  if ( v6 )
  {
    while ( 1 )
    {
      memset_0(v87, 0, 0x13F0u);
      v87[0] = -1;
      v87[3] = 1;
      v88 = -1;
      v89 = -1;
      v90 = 0;
      v91 = -1;
      v92 = 0;
      (*(void (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v85 + 16LL))(v85, (unsigned int)v13, v87);
      if ( v89 != 17 && v89 < *((_DWORD *)this + 93) - 1 && v88 == -1 )
      {
        v14 = (__int64 *)*((_QWORD *)this + 76);
        v15 = (__int64 *)v14[1];
        HIDWORD(v84) = 0;
        v16 = v14;
        while ( !*((_BYTE *)v15 + 25) )
        {
          if ( *((_DWORD *)v15 + 7) < v87[0] )
          {
            v15 = (__int64 *)v15[2];
          }
          else
          {
            v16 = v15;
            v15 = (__int64 *)*v15;
          }
        }
        if ( !*((_BYTE *)v16 + 25) )
        {
          v17 = v87[0];
          v70 = v87[0];
          if ( v16 != v14 && v87[0] >= *((_DWORD *)v16 + 7) )
          {
            v18 = &v77[3 * v89];
            v19 = v87[0] >> (*v18)[5];
            if ( v19 < *((_DWORD *)v18 + 2) )
            {
              v20 = (unsigned int *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(&v77[3 * v89]);
            }
            else if ( v19 >= *((_DWORD *)v18 + 3) )
            {
              v20 = (unsigned int *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(&v77[3 * v89]);
            }
            else
            {
              v20 = &v18[2][2 * (v19 - *((_DWORD *)v18 + 2))];
            }
            v69 = v20;
            if ( *(_QWORD *)v20 )
            {
              v26 = v69;
            }
            else
            {
              v21 = *v18;
              v22 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*v18 + 12);
              v23 = *(_QWORD *)(v22 + 24);
              if ( *(_QWORD *)(v22 + 16) == v23 )
              {
                v43 = *(unsigned int *)(v22 + 8);
                if ( (unsigned int)v43 < v21[7] )
                {
                  v25 = (void *)(*(_QWORD *)v22 + 8 * v43);
                  *(_DWORD *)(v22 + 8) = v43 + v21[2];
                }
                else
                {
                  v44 = _aligned_malloc(8LL * v21[7], v21[8]);
                  v25 = v44;
                  v71 = v44;
                  if ( !v44 )
                    wil::details::in1diag3::_Throw_NullAlloc(
                      retaddr,
                      (void *)0x430,
                      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                      v45);
                  v60 = *(_QWORD **)(v22 + 48);
                  if ( v60 == *(_QWORD **)(v22 + 56) )
                  {
                    std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                      v22 + 40,
                      v60,
                      &v71);
                    v25 = v71;
                  }
                  else
                  {
                    *v60 = v44;
                    *(_QWORD *)(v22 + 48) += 8LL;
                  }
                  v61 = v21[6] * ((__int64)(*(_QWORD *)(v22 + 48) - *(_QWORD *)(v22 + 40)) >> 3);
                  v71 = (void *)v61;
                  if ( v61 > (__int64)(*(_QWORD *)(v22 + 32) - *(_QWORD *)(v22 + 16)) >> 3 )
                  {
                    if ( v61 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_77:
                      std::_Xlength_error("vector too long");
                    std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v22 + 16, &v71);
                  }
                  *(_QWORD *)v22 = v25;
                  *(_DWORD *)(v22 + 8) = v21[2];
                  v9 = v73;
                }
              }
              else
              {
                v24 = (void **)(v23 - 8);
                v25 = *v24;
                *(_QWORD *)(v22 + 24) = v24;
              }
              v26 = v69;
              *(_QWORD *)v69 = v25;
              memset_0(v25, 0, v21[1]);
              v17 = v70;
            }
            v27 = ((unsigned __int64)v17 >> 6) & (*v18)[4];
            v28 = 1LL << (v17 & 0x3F);
            v29 = *(_QWORD *)(*(_QWORD *)v26 + 8 * v27);
            if ( (v29 & v28) == 0 )
              *(_QWORD *)(*(_QWORD *)v26 + 8 * v27) = v28 | v29;
          }
        }
      }
      v30 = v87[0];
      v70 = v87[0];
      v31 = v87[0] >> v9[5];
      if ( v31 < v74 )
        break;
      if ( v31 >= v75 )
      {
        v51 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(&v73);
        goto LABEL_62;
      }
      v32 = (_QWORD *)(v76 + 8LL * (v31 - v74));
LABEL_34:
      if ( !*v32 )
      {
        v33 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(v9 + 12);
        v34 = *(_QWORD *)(v33 + 24);
        if ( *(_QWORD *)(v33 + 16) == v34 )
        {
          v40 = *(unsigned int *)(v33 + 8);
          if ( (unsigned int)v40 < v9[7] )
          {
            v36 = (void *)(*(_QWORD *)v33 + 8 * v40);
            *(_DWORD *)(v33 + 8) = v40 + v9[2];
          }
          else
          {
            v41 = _aligned_malloc(8LL * v9[7], v9[8]);
            v36 = v41;
            v71 = v41;
            if ( !v41 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0x430,
                (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                v42);
            v58 = *(_QWORD **)(v33 + 48);
            if ( v58 == *(_QWORD **)(v33 + 56) )
            {
              std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                v33 + 40,
                v58,
                &v71);
              v36 = v71;
            }
            else
            {
              *v58 = v41;
              *(_QWORD *)(v33 + 48) += 8LL;
            }
            v59 = v9[6] * ((__int64)(*(_QWORD *)(v33 + 48) - *(_QWORD *)(v33 + 40)) >> 3);
            v71 = (void *)v59;
            if ( v59 > (__int64)(*(_QWORD *)(v33 + 32) - *(_QWORD *)(v33 + 16)) >> 3 )
            {
              if ( v59 > 0x1FFFFFFFFFFFFFFFLL )
                goto LABEL_77;
              std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v33 + 16, &v71);
            }
            *(_QWORD *)v33 = v36;
            *(_DWORD *)(v33 + 8) = v9[2];
            v30 = v70;
          }
        }
        else
        {
          v35 = (void **)(v34 - 8);
          v36 = *v35;
          *(_QWORD *)(v33 + 24) = v35;
        }
        *v32 = v36;
        memset_0(v36, 0, v9[1]);
      }
      v37 = ((unsigned __int64)v30 >> 6) & v9[4];
      v38 = 1LL << (v30 & 0x3F);
      v39 = *(_QWORD *)(*v32 + 8 * v37);
      if ( (v39 & v38) == 0 )
        *(_QWORD *)(*v32 + 8 * v37) = v38 | v39;
      v13 = v82 + 1;
      v82 = v13;
      if ( v13 >= (unsigned __int64)v80 )
        goto LABEL_51;
    }
    v51 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(&v73);
LABEL_62:
    v9 = v73;
    v32 = (_QWORD *)v51;
    goto LABEL_34;
  }
LABEL_51:
  v46 = 0;
  if ( *((_DWORD *)this + 93) != 1 )
  {
    do
    {
      v47 = &v77[3 * v46];
      IndicesToMerge = 1;
      while ( 1 )
      {
        v49 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::size(v47);
        v50 = (char *)this + 368;
        if ( !*((_BYTE *)this + 340) )
          v50 = (char *)this + 364;
        if ( v49 < *(_DWORD *)v50 || !IndicesToMerge )
          break;
        std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v83);
        IndicesToMerge = inverted::CInvertedIndex::_GetIndicesToMerge(v66, v47, &v73, &v83);
        if ( (unsigned __int64)((v84 - v83) >> 2) > 1 )
        {
          LOBYTE(v67) = 0;
          std::_Sort_unchecked<unsigned int *,std::less<void>>(v83, v84, (v84 - v83) >> 2, v67);
          v62 = v83;
          std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::find(
            (char *)this + 608,
            &v80,
            v83);
          v63 = v84;
          std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::find(
            (char *)this + 608,
            &v69,
            v84 - 4);
          if ( v69 == *((unsigned int **)this + 76) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v64);
            v63 = v84;
            v62 = v83;
          }
          v68[0] = 0;
          ((void (__fastcall *)(void **, __int64, __int64, char *))std::make_shared<inverted::SMergeData,unsigned int &,unsigned int &,bool>)(
            &v71,
            v62,
            v63 - 4,
            v68);
          if ( (unsigned __int8)inverted::MergeAllowed(v71, (char *)this + 536)
            && (unsigned __int8)inverted::MergeAllowed(v71, (char *)this + 560) )
          {
            v65 = *((_QWORD *)this + 71);
            if ( v65 == *((_QWORD *)this + 72) )
            {
              std::vector<std::shared_ptr<inverted::SMergeData>>::_Emplace_reallocate<std::shared_ptr<inverted::SMergeData> const &>(
                (char *)this + 560,
                *((_QWORD *)this + 71),
                &v71);
            }
            else
            {
              std::shared_ptr<inverted::IInvertedQueryProps>::shared_ptr<inverted::IInvertedQueryProps>(v65, &v71);
              *((_QWORD *)this + 71) += 16LL;
            }
            std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<long const,unsigned long>>>,std::_Iterator_base0>::operator++(&v69);
            std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::erase(
              (char *)this + 608,
              &v82,
              v80,
              v69);
            CThreadPoolWork::SubmitThreadpoolWork((inverted::CInvertedIndex *)((char *)this + 472), 1u);
          }
          if ( v72 )
            std::_Ref_count_base::_Decref(v72);
        }
        else
        {
          IndicesToMerge = 0;
        }
        std::vector<enum inverted::DateField>::~vector<enum inverted::DateField>(&v83);
      }
      ++v46;
    }
    while ( v46 < *((_DWORD *)this + 93) - 1 );
  }
  std::vector<dynamic_sparse_bit<unsigned __int64>>::_Tidy(&v77);
  _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::clear(&v73);
LABEL_58:
  if ( v86 )
    std::_Ref_count_base::_Decref(v86);
}

```

## disassembly

```asm
0x180088248  push    rbp
0x18008824a  push    rbx
0x18008824b  push    rsi
0x18008824c  push    rdi
0x18008824d  push    r12
0x18008824f  push    r13
0x180088251  push    r14
0x180088253  push    r15
0x180088255  lea     rbp, [rsp-13C8h]
0x18008825d  mov     eax, 14C8h
0x180088262  call    _alloca_probe
0x180088267  sub     rsp, rax
0x18008826a  mov     rax, cs:__security_cookie
0x180088271  xor     rax, rsp
0x180088274  mov     [rbp+1400h+var_50], rax
0x18008827b  mov     sil, r8b
0x18008827e  mov     bl, dl
0x180088280  mov     rdi, rcx
0x180088283  xor     r12d, r12d
0x180088286  mov     rcx, [rcx+0F0h]
0x18008828d  mov     rax, [rcx]
0x180088290  xor     r8d, r8d
0x180088293  lea     rdx, [rbp+1400h+var_1458]
0x180088297  mov     rax, [rax+30h]
0x18008829b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800882a0  nop
0x1800882a1  mov     rcx, [rbp+1400h+var_1458]
0x1800882a5  mov     rax, [rcx]
0x1800882a8  mov     rax, [rax+8]
0x1800882ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800882b1  mov     r14d, eax
0x1800882b4  mov     rcx, rdi; this
0x1800882b7  call    ?_RestartPausedMerges@CInvertedIndex@inverted@@AEAAXXZ; inverted::CInvertedIndex::_RestartPausedMerges(void)
0x1800882bc  test    bl, bl
0x1800882be  jz      short loc_1800882D7
0x1800882c0  lea     r8, [rbp+1400h+var_1458]
0x1800882c4  mov     dl, sil
0x1800882c7  mov     rcx, rdi
0x1800882ca  call    ?_CheckMasterMerge@CInvertedIndex@inverted@@AEAA_N_NAEAV?$shared_ptr@UIIndexStorageSnapshot@inverted@@@std@@@Z; inverted::CInvertedIndex::_CheckMasterMerge(bool,std::shared_ptr<inverted::IIndexStorageSnapshot> &)
0x1800882cf  test    al, al
0x1800882d1  jnz     loc_180088791
0x1800882d7  cmp     [rdi+270h], r12b
0x1800882de  jnz     loc_180088719
0x1800882e4  mov     r15, r14
0x1800882e7  mov     [rsp+1500h+var_1488], r14
0x1800882ec  mov     [rsp+1500h+var_14B8], r12
0x1800882f1  or      r14d, 0FFFFFFFFh
0x1800882f5  mov     [rsp+1500h+var_14B0], r14d
0x1800882fa  mov     [rsp+1500h+var_14AC], r14d
0x1800882ff  mov     [rsp+1500h+var_14A8], r12
0x180088304  lea     rcx, [rsp+1500h+var_14B8]
0x180088309  call    ?Empty@?$dynamic_sparse_bit@_K@@QEAAXXZ; dynamic_sparse_bit<unsigned __int64>::Empty(void)
0x18008830e  lea     r13, [rdi+388h]
0x180088315  mov     [rsp+1500h+var_14B8], r13
0x18008831a  lea     rcx, [rsp+1500h+var_14A0]; void *
0x18008831f  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x180088324  nop
0x180088325  mov     eax, [rdi+174h]
0x18008832b  mov     esi, 1
0x180088330  sub     eax, esi
0x180088332  mov     edx, eax
0x180088334  mov     r8, [rsp+1500h+var_1498]
0x180088339  mov     rcx, r8
0x18008833c  mov     rbx, [rsp+1500h+var_14A0]
0x180088341  sub     rcx, rbx
0x180088344  sar     rcx, 3
0x180088348  mov     r9, 0AAAAAAAAAAAAAAABh
0x180088352  imul    rcx, r9
0x180088356  cmp     rdx, rcx
0x180088359  jb      loc_180088857
0x18008835f  jbe     short loc_180088389
0x180088361  mov     rax, [rsp+1500h+var_1490]
0x180088366  sub     rax, rbx
0x180088369  sar     rax, 3
0x18008836d  imul    rax, r9
0x180088371  cmp     rdx, rax
0x180088374  jbe     loc_180088A86
0x18008837a  lea     rcx, [rsp+1500h+var_14A0]
0x18008837f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U?$dynamic_sparse_bit@_K@@V?$allocator@U?$dynamic_sparse_bit@_K@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<dynamic_sparse_bit<unsigned __int64>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180088384  mov     rbx, [rsp+1500h+var_14A0]
0x180088389  cmp     rbx, [rsp+1500h+var_1498]
0x18008838e  jnz     loc_180088697
0x180088394  mov     rbx, r12
0x180088397  mov     [rbp+1400h+var_1478], rbx
0x18008839b  test    r15, r15
0x18008839e  jz      loc_1800886AE
0x1800883a4  xor     edx, edx; Val
0x1800883a6  mov     r8d, 13F0h; Size
0x1800883ac  lea     rcx, [rbp+1400h+var_1440]; void *
0x1800883b0  call    memset_0
0x1800883b5  mov     [rbp+1400h+var_1440], r14d
0x1800883b9  mov     [rbp+1400h+var_1434], esi
0x1800883bc  mov     [rbp+1400h+var_1430], r14d
0x1800883c0  mov     [rbp+1400h+var_142C], r14d
0x1800883c4  mov     [rbp+1400h+var_1428], r12d
0x1800883c8  mov     [rbp+1400h+var_1418], r14d
0x1800883cc  mov     [rbp+1400h+var_1414], r12d
0x1800883d0  mov     rcx, [rbp+1400h+var_1458]
0x1800883d4  mov     rax, [rcx]
0x1800883d7  mov     edx, ebx
0x1800883d9  lea     r8, [rbp+1400h+var_1440]
0x1800883dd  mov     rax, [rax+10h]
0x1800883e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800883e6  mov     r9d, [rbp+1400h+var_142C]
0x1800883ea  cmp     r9d, 11h
0x1800883ee  jz      loc_180088517
0x1800883f4  mov     eax, [rdi+174h]
0x1800883fa  sub     eax, esi
0x1800883fc  cmp     r9d, eax
0x1800883ff  jnb     loc_180088517
0x180088405  cmp     [rbp+1400h+var_1430], r14d
0x180088409  jnz     loc_180088517
0x18008840f  mov     r8, [rdi+260h]
0x180088416  mov     rcx, [r8+8]
0x18008841a  xor     eax, eax
0x18008841c  mov     [rbp+1400h+var_1464], eax
0x18008841f  mov     rdx, r8
0x180088422  jmp     short loc_180088428
0x180088424  mov     rcx, [rcx+10h]
0x180088428  cmp     [rcx+19h], r12b
0x18008842c  jnz     short loc_18008843E
0x18008842e  mov     eax, [rbp+1400h+var_1440]
0x180088431  cmp     [rcx+1Ch], eax
0x180088434  jb      short loc_180088424
0x180088436  mov     rdx, rcx
0x180088439  mov     rcx, [rcx]
0x18008843c  jmp     short loc_180088428
0x18008843e  cmp     [rdx+19h], r12b
0x180088442  jnz     loc_180088517
0x180088448  mov     ebx, [rbp+1400h+var_1440]
0x18008844b  mov     [rsp+1500h+var_14D0], ebx
0x18008844f  cmp     rdx, r8
0x180088452  jz      loc_180088517
0x180088458  cmp     ebx, [rdx+1Ch]
0x18008845b  jb      loc_180088517
0x180088461  lea     rcx, [r9+r9*2]
0x180088465  mov     rax, [rsp+1500h+var_14A0]
0x18008846a  lea     r14, [rax+rcx*8]
0x18008846e  mov     rcx, [r14]
0x180088471  mov     ecx, [rcx+14h]
0x180088474  mov     edx, ebx
0x180088476  shr     edx, cl
0x180088478  cmp     edx, [r14+8]
0x18008847c  jb      loc_180088761
0x180088482  cmp     edx, [r14+0Ch]
0x180088486  jnb     loc_18008877A
0x18008848c  sub     edx, [r14+8]
0x180088490  mov     rax, [r14+10h]
0x180088494  lea     rax, [rax+rdx*8]
0x180088498  mov     [rsp+1500h+var_14D8], rax
0x18008849d  cmp     [rax], r12
0x1800884a0  jnz     loc_180088787
0x1800884a6  mov     r12, [r14]
0x1800884a9  lea     rcx, [r12+30h]
0x1800884ae  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800884b3  mov     r15, rax
0x1800884b6  mov     rax, [rax+18h]
0x1800884ba  cmp     [r15+10h], rax
0x1800884be  jz      loc_18008861F
0x1800884c4  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800884c8  mov     rbx, [rax]
0x1800884cb  mov     [r15+18h], rax
0x1800884cf  mov     r15, [rsp+1500h+var_14D8]
0x1800884d4  mov     [r15], rbx
0x1800884d7  mov     r8d, [r12+4]; Size
0x1800884dc  xor     edx, edx; Val
0x1800884de  mov     rcx, rbx; void *
0x1800884e1  call    memset_0
0x1800884e6  mov     ebx, [rsp+1500h+var_14D0]
0x1800884ea  mov     rax, [r14]
0x1800884ed  mov     edx, [rax+10h]
0x1800884f0  mov     eax, ebx
0x1800884f2  shr     rax, 6
0x1800884f6  and     rdx, rax
0x1800884f9  mov     r9, [r15]
0x1800884fc  and     ebx, 3Fh
0x1800884ff  mov     r8, rsi
0x180088502  mov     cl, bl
0x180088504  shl     r8, cl
0x180088507  mov     rax, [r9+rdx*8]
0x18008850b  test    r8, rax
0x18008850e  jnz     short loc_180088517
0x180088510  or      rax, r8
0x180088513  mov     [r9+rdx*8], rax
0x180088517  mov     r15d, [rbp+1400h+var_1440]
0x18008851b  mov     [rsp+1500h+var_14D0], r15d
0x180088520  mov     ecx, [r13+14h]
0x180088524  mov     edx, r15d
0x180088527  shr     edx, cl
0x180088529  cmp     edx, [rsp+1500h+var_14B0]
0x18008852d  jb      loc_18008874A
0x180088533  cmp     edx, [rsp+1500h+var_14AC]
0x180088537  jnb     loc_18008876E
0x18008853d  sub     edx, [rsp+1500h+var_14B0]
0x180088541  mov     rax, [rsp+1500h+var_14A8]
0x180088546  lea     r12, [rax+rdx*8]
0x18008854a  cmp     qword ptr [r12], 0
0x18008854f  jnz     short loc_180088584
0x180088551  lea     rcx, [r13+30h]
0x180088555  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x18008855a  mov     r14, rax
0x18008855d  mov     rax, [rax+18h]
0x180088561  cmp     [r14+10h], rax
0x180088565  jz      short loc_1800885D5
0x180088567  add     rax, 0FFFFFFFFFFFFFFF8h
0x18008856b  mov     rbx, [rax]
0x18008856e  mov     [r14+18h], rax
0x180088572  mov     [r12], rbx
0x180088576  mov     r8d, [r13+4]; Size
0x18008857a  xor     edx, edx; Val
0x18008857c  mov     rcx, rbx; void *
0x18008857f  call    memset_0
0x180088584  mov     edx, [r13+10h]
0x180088588  mov     eax, r15d
0x18008858b  shr     rax, 6
0x18008858f  and     rdx, rax
0x180088592  mov     r9, [r12]
0x180088596  and     r15d, 3Fh
0x18008859a  mov     r8, rsi
0x18008859d  mov     cl, r15b
0x1800885a0  shl     r8, cl
0x1800885a3  mov     rax, [r9+rdx*8]
0x1800885a7  test    r8, rax
0x1800885aa  jnz     short loc_1800885B3
0x1800885ac  or      rax, r8
0x1800885af  mov     [r9+rdx*8], rax
0x1800885b3  mov     rbx, [rbp+1400h+var_1478]
0x1800885b7  add     rbx, rsi
0x1800885ba  mov     [rbp+1400h+var_1478], rbx
0x1800885be  cmp     rbx, [rsp+1500h+var_1488]
0x1800885c3  jnb     loc_1800886AB
0x1800885c9  or      r14d, 0FFFFFFFFh
0x1800885cd  xor     r12d, r12d
0x1800885d0  jmp     loc_1800883A4
0x1800885d5  mov     r8d, [r14+8]
0x1800885d9  cmp     r8d, [r13+1Ch]
0x1800885dd  jb      loc_180088668
0x1800885e3  mov     edx, [r13+20h]; Alignment
0x1800885e7  mov     ecx, [r13+1Ch]
0x1800885eb  shl     rcx, 3; Size
0x1800885ef  call    cs:__imp__aligned_malloc
0x1800885f5  mov     rbx, rax
0x1800885f8  mov     [rsp+1500h+var_14C8], rax
0x1800885fd  mov     rcx, [rbp+1408h]; this
0x180088604  test    rax, rax
0x180088607  jnz     loc_180088874
0x18008860d  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180088614  mov     edx, 430h; void *
0x180088619  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18008861f  mov     r8d, [r15+8]
0x180088623  cmp     r8d, [r12+1Ch]
0x180088628  jb      short loc_18008867F
0x18008862a  mov     edx, [r12+20h]; Alignment
0x18008862f  mov     ecx, [r12+1Ch]
0x180088634  shl     rcx, 3; Size
0x180088638  call    cs:__imp__aligned_malloc
0x18008863e  mov     rbx, rax
0x180088641  mov     [rsp+1500h+var_14C8], rax
0x180088646  mov     rcx, [rbp+1408h]; this
0x18008864d  test    rax, rax
0x180088650  jnz     loc_1800888F3
0x180088656  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18008865d  mov     edx, 430h; void *
0x180088662  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180088668  mov     rcx, [r14]
0x18008866b  lea     rbx, [rcx+r8*8]
0x18008866f  mov     ecx, [r13+8]
0x180088673  add     ecx, r8d
0x180088676  mov     [r14+8], ecx
0x18008867a  jmp     loc_180088572
0x18008867f  mov     rcx, [r15]
0x180088682  lea     rbx, [rcx+r8*8]
0x180088686  mov     ecx, [r12+8]
0x18008868b  add     ecx, r8d
0x18008868e  mov     [r15+8], ecx
0x180088692  jmp     loc_1800884CF
0x180088697  mov     rcx, rbx
0x18008869a  call    ?Empty@?$dynamic_sparse_bit@_K@@QEAAXXZ; dynamic_sparse_bit<unsigned __int64>::Empty(void)
0x18008869f  mov     [rbx], r13
0x1800886a2  add     rbx, 18h
0x1800886a6  jmp     loc_180088389
0x1800886ab  xor     r12d, r12d
0x1800886ae  mov     r14d, r12d
0x1800886b1  cmp     [rdi+174h], esi
0x1800886b7  jz      short loc_180088703
0x1800886b9  mov     eax, r14d
0x1800886bc  lea     rcx, [rax+rax*2]
0x1800886c0  mov     rax, [rsp+1500h+var_14A0]
0x1800886c5  lea     r12, [rax+rcx*8]
0x1800886c9  mov     r15b, sil
0x1800886cc  mov     rcx, r12
0x1800886cf  call    ?size@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAKAEBU?$dynamic_sparse_bit@_K@@@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::size(dynamic_sparse_bit<unsigned __int64> const &)
0x1800886d4  cmp     byte ptr [rdi+154h], 0
0x1800886db  lea     rcx, [rdi+170h]
0x1800886e2  jnz     short loc_1800886EB
0x1800886e4  lea     rcx, [rdi+16Ch]
0x1800886eb  cmp     eax, [rcx]
0x1800886ed  jnb     loc_180088ACB
0x1800886f3  add     r14d, esi
0x1800886f6  mov     eax, [rdi+174h]
  ... truncated ...
```
