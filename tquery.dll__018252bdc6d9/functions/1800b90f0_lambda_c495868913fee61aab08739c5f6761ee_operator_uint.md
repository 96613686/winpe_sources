# _lambda_c495868913fee61aab08739c5f6761ee_::operator()(uint)

- ea: `0x1800b90f0`
- end: `0x1800b9978`
- name: `??R_lambda_c495868913fee61aab08739c5f6761ee_@@QEBA_NI@Z`
- size: `2184`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800b90e0`

## callees

- `0x180047e78`
- `0x18004d9d8`
- `0x180050858`
- `0x18008190c`
- `0x1800b90f0`
- `0x1800b9980`
- `0x1800bad24`
- `0x1800dea58`
- `0x1801183f0`
- `0x1801470d4`
- `0x180147190`
- `0x180189cce`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b9300`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b9300`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1800b9115`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x1800b9115`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9235`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b95d1`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b96e3`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9851`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9235`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b95d1`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b96e3`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9851`

## string_xrefs

- `0x1800b924b`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800b95e7`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800b96f9`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800b9867`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`

## pseudocode

```c
char __fastcall _lambda_c495868913fee61aab08739c5f6761ee_::operator()(__int64 a1, unsigned int a2)
{
  _QWORD *v3; // rbx
  unsigned int CurrentThreadId; // ecx
  unsigned __int64 v5; // rdx
  __int64 i; // rax
  __int64 v7; // rbx
  unsigned int v8; // r15d
  unsigned int *v9; // rcx
  unsigned int v10; // edx
  _QWORD *v11; // r13
  unsigned int *v12; // r14
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rcx
  void *v16; // rsi
  unsigned __int64 v17; // r8
  char v18; // r15
  unsigned __int64 v19; // r8
  __int64 v20; // rax
  __int64 v22; // r8
  _QWORD *v23; // rax
  const char *v24; // r9
  __int64 v25; // rax
  _QWORD *v26; // rdx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rax
  _QWORD *v29; // r13
  unsigned int v30; // r15d
  unsigned __int64 v31; // rdx
  __int64 v32; // rdi
  __int64 v33; // rax
  unsigned int *v34; // r11
  unsigned int *v35; // r14
  unsigned int v36; // r15d
  unsigned int v37; // r9d
  unsigned int v38; // ecx
  __int64 v39; // r10
  __int64 v40; // rdi
  __int64 v41; // rax
  __int64 v42; // rax
  _QWORD *v43; // r13
  unsigned int *v44; // r14
  __int64 v45; // rax
  __int64 v46; // rdi
  __int64 v47; // rcx
  __int64 v48; // r8
  void *v49; // rsi
  unsigned __int64 v50; // r8
  char v51; // r15
  unsigned __int64 v52; // r8
  __int64 v53; // rax
  inverted::CPidWids *v54; // rsi
  __int64 v55; // rax
  unsigned __int64 v56; // rbx
  __int64 v57; // rax
  _DWORD *v58; // r14
  unsigned int v59; // edx
  __int64 v60; // rax
  bool v61; // zf
  unsigned int *v62; // r15
  __int64 v63; // rax
  __int64 v64; // rbx
  __int64 v65; // rcx
  __int64 v66; // r8
  void *v67; // rsi
  _QWORD *v68; // rax
  const char *v69; // r9
  _QWORD *v70; // rax
  _WORD *v71; // rcx
  _QWORD *v72; // rdx
  unsigned __int64 v73; // rdx
  unsigned __int64 v74; // rax
  void *v75; // rax
  const char *v76; // r9
  _QWORD *v77; // rdx
  unsigned __int64 v78; // rdx
  unsigned __int64 v79; // rax
  inverted::CPidWids *v80; // rsi
  __int64 v81; // rax
  unsigned __int64 v82; // rbx
  __int64 v83; // rax
  unsigned int v84; // edx
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rbx
  __int64 v88; // rcx
  __int64 v89; // r8
  void *v90; // rax
  const char *v91; // r9
  _QWORD *v92; // rdx
  unsigned __int64 v93; // rcx
  unsigned __int64 v94; // rax
  char v95[16]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  _QWORD *v97; // [rsp+70h] [rbp+40h] BYREF
  unsigned int v98; // [rsp+78h] [rbp+48h]
  void *v99; // [rsp+80h] [rbp+50h] BYREF

  v98 = a2;
  v3 = *(_QWORD **)(*(_QWORD *)a1 + 48LL);
  CurrentThreadId = Concurrency::details::platform::GetCurrentThreadId((Concurrency::details::platform *)a1);
  v5 = (unsigned __int64)CurrentThreadId % v3[1];
  for ( i = *(_QWORD *)(*v3 + 8 * v5); i; i = *(_QWORD *)(i + 80) )
  {
    if ( *(_DWORD *)i == CurrentThreadId )
      goto LABEL_4;
  }
  i = TPUtils::combinable<inverted::CPhraseCursor::SPerThreadData>::_AddLocalItem(v3, CurrentThreadId, v5);
LABEL_4:
  v7 = i + 8;
  if ( !*(_BYTE *)(*(_QWORD *)a1 + 104LL) )
  {
    v9 = *(unsigned int **)v7;
    v98 = *(_DWORD *)(a1 + 20);
    v8 = v98;
    v10 = v98 >> v9[5];
    if ( v10 < *(_DWORD *)(i + 16) )
    {
      v25 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v7);
    }
    else
    {
      if ( v10 < *(_DWORD *)(i + 20) )
      {
        v11 = (_QWORD *)(*(_QWORD *)(i + 24) + 8LL * (v10 - *(_DWORD *)(i + 16)));
        goto LABEL_8;
      }
      v25 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v7);
    }
    v11 = (_QWORD *)v25;
LABEL_8:
    if ( !*v11 )
    {
      v12 = *(unsigned int **)v7;
      v13 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v7 + 48LL);
      v14 = v13;
      v15 = *(_QWORD *)(v13 + 24);
      if ( *(_QWORD *)(v13 + 16) == v15 )
      {
        v22 = *(unsigned int *)(v13 + 8);
        if ( (unsigned int)v22 < v12[7] )
        {
          v16 = (void *)(*(_QWORD *)v13 + 8 * v22);
          *(_DWORD *)(v13 + 8) = v22 + v12[2];
        }
        else
        {
          v23 = _aligned_malloc(8LL * v12[7], v12[8]);
          v97 = v23;
          v16 = v23;
          if ( !v23 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x430,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
              v24);
          v26 = *(_QWORD **)(v14 + 48);
          if ( v26 == *(_QWORD **)(v14 + 56) )
          {
            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
              v14 + 40,
              v26,
              &v97);
            v16 = v97;
          }
          else
          {
            *v26 = v23;
            *(_QWORD *)(v14 + 48) += 8LL;
          }
          v27 = v12[6] * ((__int64)(*(_QWORD *)(v14 + 48) - *(_QWORD *)(v14 + 40)) >> 3);
          v28 = (__int64)(*(_QWORD *)(v14 + 32) - *(_QWORD *)(v14 + 16)) >> 3;
          v97 = (_QWORD *)v27;
          if ( v27 > v28 )
          {
            if ( v27 > 0x1FFFFFFFFFFFFFFFLL )
              goto LABEL_29;
            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v14 + 16, &v97);
          }
          v8 = v98;
          *(_QWORD *)v14 = v16;
          *(_DWORD *)(v14 + 8) = v12[2];
        }
      }
      else
      {
        v16 = *(void **)(v15 - 8);
        *(_QWORD *)(v13 + 24) = v15 - 8;
      }
      *v11 = v16;
      memset_0(v16, 0, v12[1]);
    }
    v17 = v8;
    v18 = v8 & 0x3F;
    v19 = *(unsigned int *)(*(_QWORD *)v7 + 16LL) & (v17 >> 6);
    v20 = *(_QWORD *)(*v11 + 8 * v19);
    if ( (v20 & (1LL << v18)) == 0 )
      *(_QWORD *)(*v11 + 8 * v19) = (1LL << v18) | v20;
    if ( !*(_BYTE *)(*(_QWORD *)a1 + 105LL) )
      return *(_BYTE *)(*(_QWORD *)a1 + 104LL);
    v30 = *(_DWORD *)(a1 + 20);
    v80 = (inverted::CPidWids *)(v7 + 40);
    v81 = *(_QWORD *)(v7 + 56) - *(_QWORD *)(v7 + 48);
    v82 = *(unsigned __int16 *)(a1 + 16);
    v98 = v30;
    if ( 0xAAAAAAAAAAAAAAABuLL * (v81 >> 3) <= v82 )
      inverted::CPidWids::Reserve(v80, v82 + 1);
    v83 = *((_QWORD *)v80 + 1);
    v58 = (_DWORD *)(v83 + 24 * v82);
    v84 = v30 >> *(_DWORD *)(*(_QWORD *)v58 + 20LL);
    if ( v84 < v58[2] )
    {
      v85 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v83 + 24 * v82);
    }
    else
    {
      if ( v84 < v58[3] )
      {
        v29 = (_QWORD *)(*((_QWORD *)v58 + 2) + 8LL * (v84 - v58[2]));
LABEL_96:
        v61 = *v29 == 0;
        v97 = v29;
        if ( v61 )
        {
          v62 = *(unsigned int **)v58;
          v86 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v58 + 48LL);
          v87 = v86;
          v88 = *(_QWORD *)(v86 + 24);
          if ( *(_QWORD *)(v86 + 16) != v88 )
          {
            v67 = *(void **)(v88 - 8);
            *(_QWORD *)(v86 + 24) = v88 - 8;
            goto LABEL_33;
          }
          v89 = *(unsigned int *)(v86 + 8);
          if ( (unsigned int)v89 < v62[7] )
          {
            v67 = (void *)(*(_QWORD *)v86 + 8 * v89);
            *(_DWORD *)(v86 + 8) = v89 + v62[2];
            goto LABEL_33;
          }
          v90 = _aligned_malloc(8LL * v62[7], v62[8]);
          v99 = v90;
          v67 = v90;
          if ( !v90 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x430,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
              v91);
          v92 = *(_QWORD **)(v87 + 48);
          if ( v92 == *(_QWORD **)(v87 + 56) )
          {
            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
              v87 + 40,
              v92,
              &v99);
            v67 = v99;
          }
          else
          {
            *v92 = v90;
            *(_QWORD *)(v87 + 48) += 8LL;
          }
          v93 = v62[6] * ((__int64)(*(_QWORD *)(v87 + 48) - *(_QWORD *)(v87 + 40)) >> 3);
          v94 = (__int64)(*(_QWORD *)(v87 + 32) - *(_QWORD *)(v87 + 16)) >> 3;
          v99 = (void *)v93;
          if ( v93 > v94 )
          {
            if ( v93 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_29:
              std::_Xlength_error("vector too long");
            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v87 + 16, &v99);
          }
          v29 = v97;
          *(_QWORD *)v87 = v67;
          *(_DWORD *)(v87 + 8) = v62[2];
          goto LABEL_33;
        }
        goto LABEL_34;
      }
      v85 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v83 + 24 * v82);
    }
    v29 = (_QWORD *)v85;
    goto LABEL_96;
  }
  v71 = **(_WORD ***)(a1 + 32);
  if ( v71 )
  {
LABEL_73:
    ++*v71;
    return *(_BYTE *)(*(_QWORD *)a1 + 104LL);
  }
  v34 = *(unsigned int **)v7;
  v35 = (unsigned int *)(a1 + 20);
  v98 = *(_DWORD *)(a1 + 20);
  v36 = v98;
  v37 = v98 >> v34[5];
  v38 = *(_DWORD *)(i + 16);
  if ( v37 < v38 )
    goto LABEL_66;
  if ( v37 >= *(_DWORD *)(i + 20) )
  {
    if ( v37 >= v38 )
    {
      v39 = v37 - v38;
      goto LABEL_42;
    }
LABEL_66:
    v42 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v7);
    goto LABEL_44;
  }
  v39 = v37 - v38;
  v40 = *(_QWORD *)(*(_QWORD *)(i + 24) + 8 * v39);
  if ( v40 )
  {
    v41 = *(_QWORD *)(v40 + 8 * (v34[4] & ((unsigned __int64)v98 >> 6)));
    if ( _bittest64(&v41, v98 & 0x3F) )
    {
      std::_Tree<std::_Tmap_traits<unsigned int,unsigned short,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,unsigned short>>,0>>::find(
        v7 + 24,
        &v97,
        a1 + 20);
      v70 = v97;
      if ( v97 == *(_QWORD **)(v7 + 24) )
      {
        LODWORD(v97) = v36;
        WORD2(v97) = 1;
        v70 = *(_QWORD **)std::map<unsigned int,unsigned short>::insert<std::pair<unsigned int,unsigned short>,0>(
                            v7 + 24,
                            v95,
                            &v97);
      }
      **(_QWORD **)(a1 + 32) = v70 + 4;
      v71 = **(_WORD ***)(a1 + 32);
      goto LABEL_73;
    }
  }
LABEL_42:
  if ( v37 >= *(_DWORD *)(v7 + 12) )
  {
    v42 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v7);
LABEL_44:
    v43 = (_QWORD *)v42;
    goto LABEL_45;
  }
  v43 = (_QWORD *)(*(_QWORD *)(v7 + 16) + 8 * v39);
LABEL_45:
  if ( !*v43 )
  {
    v44 = *(unsigned int **)v7;
    v45 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v7 + 48LL);
    v46 = v45;
    v47 = *(_QWORD *)(v45 + 24);
    if ( *(_QWORD *)(v45 + 16) == v47 )
    {
      v48 = *(unsigned int *)(v45 + 8);
      if ( (unsigned int)v48 >= v44[7] )
      {
        v68 = _aligned_malloc(8LL * v44[7], v44[8]);
        v97 = v68;
        v49 = v68;
        if ( !v68 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x430,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
            v69);
        v72 = *(_QWORD **)(v46 + 48);
        if ( v72 == *(_QWORD **)(v46 + 56) )
        {
          std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
            v46 + 40,
            v72,
            &v97);
          v49 = v97;
        }
        else
        {
          *v72 = v68;
          *(_QWORD *)(v46 + 48) += 8LL;
        }
        v73 = v44[6] * ((__int64)(*(_QWORD *)(v46 + 48) - *(_QWORD *)(v46 + 40)) >> 3);
        v74 = (__int64)(*(_QWORD *)(v46 + 32) - *(_QWORD *)(v46 + 16)) >> 3;
        v97 = (_QWORD *)v73;
        if ( v73 > v74 )
        {
          if ( v73 > 0x1FFFFFFFFFFFFFFFLL )
            goto LABEL_29;
          std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v46 + 16, &v97);
        }
        v36 = v98;
        *(_QWORD *)v46 = v49;
        *(_DWORD *)(v46 + 8) = v44[2];
      }
      else
      {
        v49 = (void *)(*(_QWORD *)v45 + 8 * v48);
        *(_DWORD *)(v45 + 8) = v48 + v44[2];
      }
    }
    else
    {
      v49 = *(void **)(v47 - 8);
      *(_QWORD *)(v45 + 24) = v47 - 8;
    }
    *v43 = v49;
    memset_0(v49, 0, v44[1]);
    v35 = (unsigned int *)(a1 + 20);
  }
  v50 = v36;
  v51 = v36 & 0x3F;
  v52 = *(unsigned int *)(*(_QWORD *)v7 + 16LL) & (v50 >> 6);
  v53 = *(_QWORD *)(*v43 + 8 * v52);
  if ( (v53 & (1LL << v51)) == 0 )
    *(_QWORD *)(*v43 + 8 * v52) = (1LL << v51) | v53;
  if ( *(_BYTE *)(*(_QWORD *)a1 + 105LL) )
  {
    v30 = *v35;
    v54 = (inverted::CPidWids *)(v7 + 40);
    v55 = *(_QWORD *)(v7 + 56) - *(_QWORD *)(v7 + 48);
    v56 = *(unsigned __int16 *)(a1 + 16);
    v98 = *v35;
    if ( 0xAAAAAAAAAAAAAAABuLL * (v55 >> 3) <= v56 )
      inverted::CPidWids::Reserve(v54, v56 + 1);
    v57 = *((_QWORD *)v54 + 1);
    v58 = (_DWORD *)(v57 + 24 * v56);
    v59 = v30 >> *(_DWORD *)(*(_QWORD *)v58 + 20LL);
    if ( v59 < v58[2] )
    {
      v60 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v57 + 24 * v56);
    }
    else
    {
      if ( v59 < v58[3] )
      {
        v29 = (_QWORD *)(*((_QWORD *)v58 + 2) + 8LL * (v59 - v58[2]));
LABEL_59:
        v61 = *v29 == 0;
        v97 = v29;
        if ( v61 )
        {
          v62 = *(unsigned int **)v58;
          v63 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v58 + 48LL);
          v64 = v63;
          v65 = *(_QWORD *)(v63 + 24);
          if ( *(_QWORD *)(v63 + 16) == v65 )
          {
            v66 = *(unsigned int *)(v63 + 8);
            if ( (unsigned int)v66 >= v62[7] )
            {
              v75 = _aligned_malloc(8LL * v62[7], v62[8]);
              v99 = v75;
              v67 = v75;
              if ( !v75 )
                wil::details::in1diag3::_Throw_NullAlloc(
                  retaddr,
                  (void *)0x430,
                  (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                  v76);
              v77 = *(_QWORD **)(v64 + 48);
              if ( v77 == *(_QWORD **)(v64 + 56) )
              {
                std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                  v64 + 40,
                  v77,
                  &v99);
                v67 = v99;
              }
              else
              {
                *v77 = v75;
                *(_QWORD *)(v64 + 48) += 8LL;
              }
              v78 = v62[6] * ((__int64)(*(_QWORD *)(v64 + 48) - *(_QWORD *)(v64 + 40)) >> 3);
              v79 = (__int64)(*(_QWORD *)(v64 + 32) - *(_QWORD *)(v64 + 16)) >> 3;
              v99 = (void *)v78;
              if ( v78 > v79 )
              {
                if ( v78 > 0x1FFFFFFFFFFFFFFFLL )
                  goto LABEL_29;
                std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v64 + 16, &v99);
              }
              v29 = v97;
              *(_QWORD *)v64 = v67;
              *(_DWORD *)(v64 + 8) = v62[2];
            }
            else
            {
              v67 = (void *)(*(_QWORD *)v63 + 8 * v66);
              *(_DWORD *)(v63 + 8) = v66 + v62[2];
            }
          }
          else
          {
            v67 = *(void **)(v65 - 8);
            *(_QWORD *)(v63 + 24) = v65 - 8;
          }
LABEL_33:
          *v29 = v67;
          memset_0(v67, 0, v62[1]);
          v30 = v98;
        }
LABEL_34:
        v31 = ((unsigned __int64)v30 >> 6) & *(unsigned int *)(*(_QWORD *)v58 + 16LL);
        v32 = 1LL << (v30 & 0x3F);
        v33 = *(_QWORD *)(*v29 + 8 * v31);
        if ( (v33 & v32) == 0 )
          *(_QWORD *)(*v29 + 8 * v31) = v32 | v33;
        return *(_BYTE *)(*(_QWORD *)a1 + 104LL);
      }
      v60 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v57 + 24 * v56);
    }
    v29 = (_QWORD *)v60;
    goto LABEL_59;
  }
  return *(_BYTE *)(*(_QWORD *)a1 + 104LL);
}

```

## disassembly

```asm
0x1800b90f0  mov     [rsp-38h+arg_18], rbx
0x1800b90f5  mov     [rsp-38h+arg_8], edx
0x1800b90f9  push    rbp
0x1800b90fa  push    rsi
0x1800b90fb  push    rdi
0x1800b90fc  push    r12
0x1800b90fe  push    r13
0x1800b9100  push    r14
0x1800b9102  push    r15
0x1800b9104  mov     rbp, rsp
0x1800b9107  sub     rsp, 30h
0x1800b910b  mov     rax, [rcx]
0x1800b910e  mov     r12, rcx
0x1800b9111  mov     rbx, [rax+30h]
0x1800b9115  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x1800b911b  mov     r8, [rbx]
0x1800b911e  xor     edx, edx
0x1800b9120  mov     ecx, eax
0x1800b9122  mov     eax, eax
0x1800b9124  div     qword ptr [rbx+8]
0x1800b9128  mov     rax, [r8+rdx*8]
0x1800b912c  test    rax, rax
0x1800b912f  jz      loc_1800B927C
0x1800b9135  cmp     [rax], ecx
0x1800b9137  jnz     loc_1800B925D
0x1800b913d  lea     rbx, [rax+8]
0x1800b9141  mov     rax, [r12]
0x1800b9145  cmp     byte ptr [rax+68h], 0
0x1800b9149  jnz     loc_1800B98E4
0x1800b914f  mov     r15d, [r12+14h]
0x1800b9154  mov     edx, r15d
0x1800b9157  mov     rcx, [rbx]
0x1800b915a  mov     [rbp+arg_8], r15d
0x1800b915e  mov     ecx, [rcx+14h]
0x1800b9161  shr     edx, cl
0x1800b9163  cmp     edx, [rbx+8]
0x1800b9166  jb      loc_1800B928E
0x1800b916c  cmp     edx, [rbx+0Ch]
0x1800b916f  jnb     loc_1800B929E
0x1800b9175  sub     edx, [rbx+8]
0x1800b9178  mov     rax, [rbx+10h]
0x1800b917c  lea     r13, [rax+rdx*8]
0x1800b9180  cmp     qword ptr [r13+0], 0
0x1800b9185  jnz     short loc_1800B91BD
0x1800b9187  mov     r14, [rbx]
0x1800b918a  lea     rcx, [r14+30h]
0x1800b918e  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800b9193  mov     rdi, rax
0x1800b9196  mov     rcx, [rax+18h]
0x1800b919a  cmp     [rax+10h], rcx
0x1800b919e  jz      short loc_1800B921F
0x1800b91a0  lea     rax, [rcx-8]
0x1800b91a4  mov     rsi, [rax]
0x1800b91a7  mov     [rdi+18h], rax
0x1800b91ab  mov     [r13+0], rsi
0x1800b91af  xor     edx, edx; Val
0x1800b91b1  mov     r8d, [r14+4]; Size
0x1800b91b5  mov     rcx, rsi; void *
0x1800b91b8  call    memset_0
0x1800b91bd  mov     rax, [rbx]
0x1800b91c0  mov     edi, 1
0x1800b91c5  mov     r9, [r13+0]
0x1800b91c9  mov     r8d, r15d
0x1800b91cc  and     r15d, 3Fh
0x1800b91d0  shr     r8, 6
0x1800b91d4  mov     cl, r15b
0x1800b91d7  mov     edx, [rax+10h]
0x1800b91da  and     r8, rdx
0x1800b91dd  mov     edx, edi
0x1800b91df  shl     rdx, cl
0x1800b91e2  mov     rax, [r9+r8*8]
0x1800b91e6  test    rdx, rax
0x1800b91e9  jnz     short loc_1800B91F2
0x1800b91eb  or      rax, rdx
0x1800b91ee  mov     [r9+r8*8], rax
0x1800b91f2  mov     rax, [r12]
0x1800b91f6  cmp     byte ptr [rax+69h], 0
0x1800b91fa  jnz     loc_1800B9779
0x1800b9200  mov     rax, [r12]
0x1800b9204  mov     rbx, [rsp+30h+arg_18]
0x1800b920c  mov     al, [rax+68h]
0x1800b920f  add     rsp, 30h
0x1800b9213  pop     r15
0x1800b9215  pop     r14
0x1800b9217  pop     r13
0x1800b9219  pop     r12
0x1800b921b  pop     rdi
0x1800b921c  pop     rsi
0x1800b921d  pop     rbp
0x1800b921e  retn
0x1800b921f  mov     r8d, [rax+8]
0x1800b9223  cmp     r8d, [r14+1Ch]
0x1800b9227  jb      short loc_1800B9266
0x1800b9229  mov     ecx, [r14+1Ch]
0x1800b922d  mov     edx, [r14+20h]; Alignment
0x1800b9231  shl     rcx, 3; Size
0x1800b9235  call    cs:__imp__aligned_malloc
0x1800b923b  mov     [rbp+arg_0], rax
0x1800b923f  mov     rsi, rax
0x1800b9242  test    rax, rax
0x1800b9245  jnz     short loc_1800B92A8
0x1800b9247  mov     rcx, [rbp+38h]; this
0x1800b924b  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800b9252  mov     edx, 430h; void *
0x1800b9257  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800b925d  mov     rax, [rax+50h]
0x1800b9261  jmp     loc_1800B912C
0x1800b9266  mov     rcx, [rax]
0x1800b9269  lea     rsi, [rcx+r8*8]
0x1800b926d  mov     ecx, [r14+8]
0x1800b9271  add     ecx, r8d
0x1800b9274  mov     [rax+8], ecx
0x1800b9277  jmp     loc_1800B91AB
0x1800b927c  mov     r8, rdx
0x1800b927f  mov     edx, ecx
0x1800b9281  mov     rcx, rbx
0x1800b9284  call    ?_AddLocalItem@?$combinable@USPerThreadData@CPhraseCursor@inverted@@@TPUtils@@AEAAPEAU_Node@12@K_K@Z; TPUtils::combinable<inverted::CPhraseCursor::SPerThreadData>::_AddLocalItem(ulong,unsigned __int64)
0x1800b9289  jmp     loc_1800B913D
0x1800b928e  mov     rcx, rbx
0x1800b9291  call    ?_AddPagesToStart@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9296  mov     r13, rax
0x1800b9299  jmp     loc_1800B9180
0x1800b929e  mov     rcx, rbx
0x1800b92a1  call    ?_AddPagesToEnd@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b92a6  jmp     short loc_1800B9296
0x1800b92a8  mov     rdx, [rdi+30h]
0x1800b92ac  cmp     rdx, [rdi+38h]
0x1800b92b0  jz      loc_1800B994C
0x1800b92b6  mov     [rdx], rax
0x1800b92b9  add     qword ptr [rdi+30h], 8
0x1800b92be  mov     eax, [r14+18h]
0x1800b92c2  lea     rcx, [rdi+10h]
0x1800b92c6  mov     rdx, [rdi+30h]
0x1800b92ca  sub     rdx, [rdi+28h]
0x1800b92ce  sar     rdx, 3
0x1800b92d2  imul    rdx, rax
0x1800b92d6  mov     rax, [rcx+10h]
0x1800b92da  sub     rax, [rcx]
0x1800b92dd  sar     rax, 3
0x1800b92e1  mov     [rbp+arg_0], rdx
0x1800b92e5  cmp     rdx, rax
0x1800b92e8  jbe     short loc_1800B9310
0x1800b92ea  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800b92f4  cmp     rdx, rax
0x1800b92f7  jbe     short loc_1800B9307
0x1800b92f9  lea     rcx, aVectorTooLong; "vector too long"
0x1800b9300  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b9307  lea     rdx, [rbp+arg_0]
0x1800b930b  call    ??$_Reallocate@$0A@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<ulong,ulong>>::_Reallocate<0>(unsigned __int64 &)
0x1800b9310  mov     r15d, [rbp+arg_8]
0x1800b9314  mov     [rdi], rsi
0x1800b9317  mov     eax, [r14+8]
0x1800b931b  mov     [rdi+8], eax
0x1800b931e  jmp     loc_1800B91AB
0x1800b9323  lea     rdx, [rbp+arg_10]
0x1800b9327  call    ??$_Reallocate@$0A@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<ulong,ulong>>::_Reallocate<0>(unsigned __int64 &)
0x1800b932c  mov     r13, [rbp+arg_0]
0x1800b9330  mov     [rbx], rsi
0x1800b9333  mov     eax, [r15+8]
0x1800b9337  mov     [rbx+8], eax
0x1800b933a  mov     [r13+0], rsi
0x1800b933e  xor     edx, edx; Val
0x1800b9340  mov     r8d, [r15+4]; Size
0x1800b9344  mov     rcx, rsi; void *
0x1800b9347  call    memset_0
0x1800b934c  mov     r15d, [rbp+arg_8]
0x1800b9350  mov     rax, [r14]
0x1800b9353  mov     r8, [r13+0]
0x1800b9357  mov     edx, [rax+10h]
0x1800b935a  mov     eax, r15d
0x1800b935d  and     r15d, 3Fh
0x1800b9361  shr     rax, 6
0x1800b9365  mov     cl, r15b
0x1800b9368  and     rdx, rax
0x1800b936b  shl     rdi, cl
0x1800b936e  mov     rax, [r8+rdx*8]
0x1800b9372  test    rdi, rax
0x1800b9375  jnz     loc_1800B9200
0x1800b937b  or      rax, rdi
0x1800b937e  mov     [r8+rdx*8], rax
0x1800b9382  jmp     loc_1800B9200
0x1800b9387  lea     rdx, [rbp+arg_10]
0x1800b938b  lea     rcx, [rbx+10h]
0x1800b938f  call    ??$_Reallocate@$0A@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<ulong,ulong>>::_Reallocate<0>(unsigned __int64 &)
0x1800b9394  mov     r13, [rbp+arg_0]
0x1800b9398  mov     [rbx], rsi
0x1800b939b  mov     eax, [r15+8]
0x1800b939f  mov     [rbx+8], eax
0x1800b93a2  mov     [r13+0], rsi
0x1800b93a6  xor     edx, edx; Val
0x1800b93a8  mov     r8d, [r15+4]; Size
0x1800b93ac  mov     rcx, rsi; void *
0x1800b93af  call    memset_0
0x1800b93b4  mov     r15d, [rbp+arg_8]
0x1800b93b8  jmp     short loc_1800B9350
0x1800b93ba  mov     r11, [rbx]
0x1800b93bd  lea     r14, [r12+14h]
0x1800b93c2  mov     r15d, [r14]
0x1800b93c5  mov     r9d, r15d
0x1800b93c8  mov     [rbp+arg_8], r15d
0x1800b93cc  mov     ecx, [r11+14h]
0x1800b93d0  shr     r9d, cl
0x1800b93d3  mov     ecx, [rbx+8]
0x1800b93d6  cmp     r9d, ecx
0x1800b93d9  jb      loc_1800B95B5
0x1800b93df  cmp     r9d, [rbx+0Ch]
0x1800b93e3  jnb     loc_1800B9598
0x1800b93e9  mov     rax, [rbx+10h]
0x1800b93ed  mov     r10d, r9d
0x1800b93f0  sub     r10d, ecx
0x1800b93f3  mov     rdi, [rax+r10*8]
0x1800b93f7  test    rdi, rdi
0x1800b93fa  jz      short loc_1800B9421
0x1800b93fc  mov     eax, [r11+10h]
0x1800b9400  mov     edx, r15d
0x1800b9403  shr     rdx, 6
0x1800b9407  and     rdx, rax
0x1800b940a  mov     eax, r15d
0x1800b940d  and     eax, 3Fh
0x1800b9410  movzx   ecx, al
0x1800b9413  mov     rax, [rdi+rdx*8]
0x1800b9417  bt      rax, rcx
0x1800b941b  jb      loc_1800B9609
0x1800b9421  cmp     r9d, [rbx+0Ch]
0x1800b9425  jb      loc_1800B95A8
0x1800b942b  mov     edx, r9d
0x1800b942e  mov     rcx, rbx
0x1800b9431  call    ?_AddPagesToEnd@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9436  mov     r13, rax
0x1800b9439  cmp     qword ptr [r13+0], 0
0x1800b943e  jnz     short loc_1800B9493
0x1800b9440  mov     r14, [rbx]
0x1800b9443  lea     rcx, [r14+30h]
0x1800b9447  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800b944c  mov     rdi, rax
0x1800b944f  mov     rcx, [rax+18h]
0x1800b9453  cmp     [rax+10h], rcx
0x1800b9457  jnz     loc_1800B95F9
0x1800b945d  mov     r8d, [rax+8]
0x1800b9461  cmp     r8d, [r14+1Ch]
0x1800b9465  jnb     loc_1800B95C5
0x1800b946b  mov     rcx, [rax]
0x1800b946e  lea     rsi, [rcx+r8*8]
0x1800b9472  mov     ecx, [r14+8]
0x1800b9476  add     ecx, r8d
0x1800b9479  mov     [rax+8], ecx
0x1800b947c  mov     [r13+0], rsi
0x1800b9480  xor     edx, edx; Val
0x1800b9482  mov     r8d, [r14+4]; Size
0x1800b9486  mov     rcx, rsi; void *
0x1800b9489  call    memset_0
0x1800b948e  lea     r14, [r12+14h]
0x1800b9493  mov     rax, [rbx]
0x1800b9496  mov     edi, 1
0x1800b949b  mov     r9, [r13+0]
0x1800b949f  mov     r8d, r15d
0x1800b94a2  and     r15d, 3Fh
0x1800b94a6  shr     r8, 6
0x1800b94aa  mov     cl, r15b
0x1800b94ad  mov     edx, [rax+10h]
0x1800b94b0  and     r8, rdx
0x1800b94b3  mov     edx, edi
0x1800b94b5  shl     rdx, cl
0x1800b94b8  mov     rax, [r9+r8*8]
0x1800b94bc  test    rdx, rax
0x1800b94bf  jnz     short loc_1800B94C8
0x1800b94c1  or      rax, rdx
0x1800b94c4  mov     [r9+r8*8], rax
0x1800b94c8  mov     rax, [r12]
0x1800b94cc  cmp     byte ptr [rax+69h], 0
0x1800b94d0  jz      loc_1800B9200
0x1800b94d6  mov     r15d, [r14]
0x1800b94d9  lea     rsi, [rbx+28h]
0x1800b94dd  mov     rax, [rsi+10h]
0x1800b94e1  mov     rcx, 0AAAAAAAAAAAAAAABh
0x1800b94eb  sub     rax, [rsi+8]
0x1800b94ef  movzx   ebx, word ptr [r12+10h]
0x1800b94f5  sar     rax, 3
0x1800b94f9  imul    rax, rcx
0x1800b94fd  mov     [rbp+arg_8], r15d
0x1800b9501  cmp     rax, rbx
0x1800b9504  ja      short loc_1800B9512
0x1800b9506  lea     rdx, [rdi+rbx]; unsigned __int64
0x1800b950a  mov     rcx, rsi; this
0x1800b950d  call    ?Reserve@CPidWids@inverted@@AEAAX_K@Z; inverted::CPidWids::Reserve(unsigned __int64)
0x1800b9512  mov     rax, [rsi+8]
0x1800b9516  lea     rcx, [rbx+rbx*2]
0x1800b951a  mov     edx, r15d
0x1800b951d  lea     r14, [rax+rcx*8]
0x1800b9521  mov     rcx, [r14]
0x1800b9524  mov     ecx, [rcx+14h]
0x1800b9527  shr     edx, cl
0x1800b9529  cmp     edx, [r14+8]
0x1800b952d  jb      loc_1800B96CA
0x1800b9533  cmp     edx, [r14+0Ch]
0x1800b9537  jb      loc_1800B96B9
0x1800b953d  mov     rcx, r14
0x1800b9540  call    ?_AddPagesToEnd@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9545  mov     r13, rax
0x1800b9548  cmp     qword ptr [r13+0], 0
  ... truncated ...
```
