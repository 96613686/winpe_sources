# inverted::CCombinedRankCursor::NextWid(ushort,uint,bool)

- ea: `0x1800808c0`
- end: `0x18008123a`
- name: `?NextWid@CCombinedRankCursor@inverted@@UEAAXGI_N@Z`
- size: `2426`
- prototype: `void(inverted::CCombinedRankCursor *__hidden this, unsigned __int16, unsigned int, bool)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180047e78`
- `0x18004d9d8`
- `0x180050858`
- `0x18007f39c`
- `0x1800808c0`
- `0x180081240`
- `0x18008190c`
- `0x1801183f0`
- `0x1801470d4`
- `0x180147190`
- `0x180189cce`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180081045`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180081045`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180080bd8`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180080c1e`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180080c64`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180080df0`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180080ee1`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180080bd8`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180080c1e`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180080c64`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180080df0`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180080ee1`

## string_xrefs

- `0x180080bf2`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180080c38`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180080c7e`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180080e0a`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180080efb`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`

## pseudocode

```c
void __fastcall inverted::CCombinedRankCursor::NextWid(
        inverted::CCombinedRankCursor *this,
        unsigned __int16 a2,
        unsigned int a3,
        char a4)
{
  inverted::CCombinedRankCursor *v4; // rdi
  unsigned __int64 v5; // r14
  char v6; // bl
  __int64 v7; // rax
  __int64 v8; // r15
  unsigned int **v9; // rsi
  unsigned int v10; // edx
  __int64 *v11; // r12
  unsigned int *v12; // r15
  signed __int64 v13; // rax
  signed __int64 v14; // rbx
  __int64 v15; // rcx
  void *v16; // rdi
  __int64 v17; // r8
  unsigned __int64 v18; // rdx
  __int64 v19; // r13
  __int64 v20; // rax
  unsigned __int16 v21; // r10
  __int64 v22; // rdx
  int v23; // r9d
  unsigned int v24; // eax
  unsigned int v25; // ecx
  __int64 v26; // r8
  __int64 v27; // rax
  unsigned int **v28; // rbx
  unsigned int v29; // edx
  _QWORD *v30; // r12
  unsigned int *v31; // r15
  signed __int64 v32; // rax
  signed __int64 v33; // rdi
  __int64 v34; // rcx
  void *v35; // rsi
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rdi
  __int64 v39; // rax
  unsigned int **v40; // rsi
  unsigned int v41; // r14d
  unsigned int *v42; // r12
  unsigned int *v43; // r14
  signed __int64 v44; // rax
  signed __int64 v45; // rdi
  _QWORD *v46; // r13
  void **v47; // rax
  void *v48; // rbx
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // r8
  void *v52; // rax
  const char *v53; // r9
  __int64 v54; // r8
  inverted::CCombinedRankCursor *v55; // rax
  const char *v56; // r9
  __int64 v57; // r8
  void *v58; // rax
  const char *v59; // r9
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  unsigned int **v66; // rdi
  unsigned int v67; // edx
  _QWORD *v68; // r15
  unsigned int *v69; // r12
  signed __int64 v70; // rax
  signed __int64 v71; // rbx
  __int64 v72; // rcx
  void *v73; // rsi
  __int64 v74; // r8
  void *v75; // rax
  const char *v76; // r9
  unsigned int v77; // ecx
  __int64 v78; // rcx
  __int64 v79; // r8
  struct inverted::CCombinedRankCursor::CThreadData *v80; // rdi
  unsigned int **v81; // rbx
  unsigned int v82; // edx
  _QWORD *v83; // r12
  unsigned int *v84; // r15
  signed __int64 v85; // rax
  signed __int64 v86; // rdi
  __int64 v87; // rcx
  __int64 v88; // r8
  void *v89; // rax
  const char *v90; // r9
  void *v91; // rsi
  unsigned int v92; // ecx
  inverted::CCombinedRankCursor *v93; // rcx
  __int64 v94; // r8
  __int64 v95; // rax
  __int64 v96; // rax
  _QWORD *v97; // rdx
  unsigned __int64 v98; // rdx
  unsigned __int64 v99; // rax
  inverted::CCombinedRankCursor **v100; // rdx
  unsigned __int64 v101; // rcx
  unsigned __int64 v102; // rax
  _QWORD *v103; // rdx
  unsigned __int64 v104; // rdx
  unsigned __int64 v105; // rax
  _QWORD *v106; // rdx
  unsigned __int64 v107; // rdx
  unsigned __int64 v108; // rax
  _QWORD *v109; // rdx
  unsigned __int64 v110; // rdx
  unsigned __int64 v111; // rax
  struct inverted::CCombinedRankCursor::CThreadData *v112; // [rsp+20h] [rbp-38h]
  unsigned __int64 v113; // [rsp+28h] [rbp-30h]
  __int64 v114; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v115[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  inverted::CCombinedRankCursor *v117; // [rsp+A0h] [rbp+48h] BYREF
  unsigned __int16 v118; // [rsp+A8h] [rbp+50h]
  int v119; // [rsp+B0h] [rbp+58h]
  char v120; // [rsp+B8h] [rbp+60h]

  v120 = a4;
  v118 = a2;
  v117 = this;
  v4 = this;
  v5 = a3;
  v6 = a4;
  v7 = TPUtils::combinable<inverted::CCombinedRankCursor::CThreadData>::local(*((_QWORD *)this + 99));
  v112 = (struct inverted::CCombinedRankCursor::CThreadData *)v7;
  v8 = v7;
  v9 = (unsigned int **)(v7 + 128);
  v10 = (unsigned int)v5 >> *(_DWORD *)(*(_QWORD *)(v7 + 128) + 20LL);
  if ( v10 < *(_DWORD *)(v7 + 136) )
  {
    v63 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v7 + 128);
  }
  else
  {
    if ( v10 < *(_DWORD *)(v7 + 140) )
    {
      v11 = (__int64 *)(*(_QWORD *)(v7 + 144) + 8LL * (v10 - *(_DWORD *)(v7 + 136)));
      goto LABEL_4;
    }
    v63 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v7 + 128);
  }
  v11 = (__int64 *)v63;
LABEL_4:
  if ( !*v11 )
  {
    v12 = *v9;
    v13 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local((Concurrency::details::platform *)(*v9 + 12));
    v14 = v13;
    v15 = *(_QWORD *)(v13 + 24);
    if ( *(_QWORD *)(v13 + 16) == v15 )
    {
      v51 = *(unsigned int *)(v13 + 8);
      if ( (unsigned int)v51 < v12[7] )
      {
        v16 = (void *)(*(_QWORD *)v13 + 8 * v51);
        v60 = v51 + v12[2];
      }
      else
      {
        v52 = _aligned_malloc(8LL * v12[7], v12[8]);
        v114 = (__int64)v52;
        v16 = v52;
        if ( !v52 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x430,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
            v53);
        v97 = *(_QWORD **)(v14 + 48);
        if ( v97 == *(_QWORD **)(v14 + 56) )
        {
          std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
            v14 + 40,
            v97,
            &v114);
          v16 = (void *)v114;
        }
        else
        {
          *v97 = v52;
          *(_QWORD *)(v14 + 48) += 8LL;
        }
        v98 = v12[6] * ((__int64)(*(_QWORD *)(v14 + 48) - *(_QWORD *)(v14 + 40)) >> 3);
        v99 = (__int64)(*(_QWORD *)(v14 + 32) - *(_QWORD *)(v14 + 16)) >> 3;
        v115[0] = v98;
        if ( v98 > v99 )
        {
          if ( v98 > 0x1FFFFFFFFFFFFFFFLL )
            goto LABEL_108;
          std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v14 + 16, v115);
        }
        *(_QWORD *)v14 = v16;
        v60 = v12[2];
      }
      *(_DWORD *)(v14 + 8) = v60;
    }
    else
    {
      v16 = *(void **)(v15 - 8);
      *(_QWORD *)(v13 + 24) = v15 - 8;
    }
    *v11 = (__int64)v16;
    memset_0(v16, 0, v12[1]);
    v6 = v120;
    v4 = v117;
    v8 = (__int64)v112;
  }
  v17 = *v11;
  v113 = v5 >> 6;
  v18 = (v5 >> 6) & (*v9)[4];
  v19 = 1LL << v5;
  v114 = 1LL << v5;
  v20 = *(_QWORD *)(v17 + 8 * v18);
  if ( (v20 & (1LL << v5)) == 0 )
    *(_QWORD *)(v17 + 8 * v18) = v19 | v20;
  v21 = v118;
  v22 = *((_QWORD *)v4 + 20);
  v23 = v118;
  v119 = v118;
  v24 = v118 >> *(_DWORD *)(v22 + 20);
  v25 = *((_DWORD *)v4 + 42);
  if ( v24 >= v25 && v24 < *((_DWORD *)v4 + 43) )
  {
    v26 = *(_QWORD *)(*((_QWORD *)v4 + 22) + 8LL * (v24 - v25));
    if ( v26 )
    {
      v27 = *(_QWORD *)(v26 + 8 * (((unsigned __int64)v118 >> 6) & *(unsigned int *)(v22 + 16)));
      if ( _bittest64(&v27, v118 & 0x3F) )
      {
        v66 = (unsigned int **)(v8 + 176);
        v67 = (unsigned int)v5 >> *(_DWORD *)(*(_QWORD *)(v8 + 176) + 20LL);
        if ( v67 < *(_DWORD *)(v8 + 184) )
        {
          v95 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v8 + 176);
        }
        else
        {
          if ( v67 < *(_DWORD *)(v8 + 188) )
          {
            v68 = (_QWORD *)(*(_QWORD *)(v8 + 192) + 8LL * (v67 - *(_DWORD *)(v8 + 184)));
            goto LABEL_65;
          }
          v95 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v8 + 176);
        }
        v68 = (_QWORD *)v95;
LABEL_65:
        if ( !*v68 )
        {
          v69 = *v66;
          v70 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local((Concurrency::details::platform *)(*v66 + 12));
          v71 = v70;
          v72 = *(_QWORD *)(v70 + 24);
          if ( *(_QWORD *)(v70 + 16) == v72 )
          {
            v74 = *(unsigned int *)(v70 + 8);
            if ( (unsigned int)v74 < v69[7] )
            {
              v73 = (void *)(*(_QWORD *)v70 + 8 * v74);
              v77 = v74 + v69[2];
            }
            else
            {
              v75 = _aligned_malloc(8LL * v69[7], v69[8]);
              v115[0] = v75;
              v73 = v75;
              if ( !v75 )
                wil::details::in1diag3::_Throw_NullAlloc(
                  retaddr,
                  (void *)0x430,
                  (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                  v76);
              v106 = *(_QWORD **)(v71 + 48);
              if ( v106 == *(_QWORD **)(v71 + 56) )
              {
                std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                  v71 + 40,
                  v106,
                  v115);
                v73 = (void *)v115[0];
              }
              else
              {
                *v106 = v75;
                *(_QWORD *)(v71 + 48) += 8LL;
              }
              v107 = v69[6] * ((__int64)(*(_QWORD *)(v71 + 48) - *(_QWORD *)(v71 + 40)) >> 3);
              v108 = (__int64)(*(_QWORD *)(v71 + 32) - *(_QWORD *)(v71 + 16)) >> 3;
              v115[0] = v107;
              if ( v107 > v108 )
              {
                if ( v107 > 0x1FFFFFFFFFFFFFFFLL )
                  goto LABEL_108;
                std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v71 + 16, v115);
              }
              *(_QWORD *)v71 = v73;
              v77 = v69[2];
            }
            *(_DWORD *)(v71 + 8) = v77;
          }
          else
          {
            v73 = *(void **)(v72 - 8);
            *(_QWORD *)(v70 + 24) = v72 - 8;
          }
          *v68 = v73;
          memset_0(v73, 0, v69[1]);
        }
        v78 = (unsigned int)v113 & (*v66)[4];
        v79 = *(_QWORD *)(*v68 + 8 * v78);
        if ( (v19 & v79) == 0 )
          *(_QWORD *)(*v68 + 8 * v78) = v79 | v19;
        if ( !v120 )
        {
          v4 = v117;
          v23 = v119;
          v21 = v118;
          goto LABEL_24;
        }
        v80 = v112;
        v81 = (unsigned int **)((char *)v112 + 200);
        v82 = (unsigned int)v5 >> *(_DWORD *)(*((_QWORD *)v112 + 25) + 20LL);
        if ( v82 < *((_DWORD *)v112 + 52) )
        {
          v96 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)v112 + 200);
        }
        else
        {
          if ( v82 < *((_DWORD *)v112 + 53) )
          {
            v83 = (_QWORD *)(*((_QWORD *)v112 + 27) + 8LL * (v82 - *((_DWORD *)v112 + 52)));
LABEL_83:
            if ( !*v83 )
            {
              v84 = *v81;
              v85 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local((Concurrency::details::platform *)(*v81 + 12));
              v86 = v85;
              v87 = *(_QWORD *)(v85 + 24);
              if ( *(_QWORD *)(v85 + 16) == v87 )
              {
                v88 = *(unsigned int *)(v85 + 8);
                if ( (unsigned int)v88 < v84[7] )
                {
                  v91 = (void *)(*(_QWORD *)v85 + 8 * v88);
                  v92 = v88 + v84[2];
                }
                else
                {
                  v89 = _aligned_malloc(8LL * v84[7], v84[8]);
                  v115[0] = v89;
                  v91 = v89;
                  if ( !v89 )
                    wil::details::in1diag3::_Throw_NullAlloc(
                      retaddr,
                      (void *)0x430,
                      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                      v90);
                  v109 = *(_QWORD **)(v86 + 48);
                  if ( v109 == *(_QWORD **)(v86 + 56) )
                  {
                    std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                      v86 + 40,
                      v109,
                      v115);
                    v91 = (void *)v115[0];
                  }
                  else
                  {
                    *v109 = v89;
                    *(_QWORD *)(v86 + 48) += 8LL;
                  }
                  v110 = v84[6] * ((__int64)(*(_QWORD *)(v86 + 48) - *(_QWORD *)(v86 + 40)) >> 3);
                  v111 = (__int64)(*(_QWORD *)(v86 + 32) - *(_QWORD *)(v86 + 16)) >> 3;
                  v115[0] = v110;
                  if ( v110 > v111 )
                  {
                    if ( v110 > 0x1FFFFFFFFFFFFFFFLL )
                      goto LABEL_108;
                    std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v86 + 16, v115);
                  }
                  *(_QWORD *)v86 = v91;
                  v92 = v84[2];
                }
                *(_DWORD *)(v86 + 8) = v92;
              }
              else
              {
                v91 = *(void **)(v87 - 8);
                *(_QWORD *)(v85 + 24) = v87 - 8;
              }
              *v83 = v91;
              memset_0(v91, 0, v84[1]);
              v80 = v112;
            }
            v93 = (inverted::CCombinedRankCursor *)((unsigned int)v113 & (*v81)[4]);
            v94 = *(_QWORD *)(*v83 + 8LL * (_QWORD)v93);
            if ( (v19 & v94) == 0 )
              *(_QWORD *)(*v83 + 8LL * (_QWORD)v93) = v94 | v19;
            if ( *((_BYTE *)v117 + 825) )
              inverted::CCombinedRankCursor::_SetExact(v93, v5, v118, v80);
            goto LABEL_15;
          }
          v96 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)v112 + 200);
        }
        v83 = (_QWORD *)v96;
        goto LABEL_83;
      }
    }
  }
  if ( !v6 )
    goto LABEL_24;
LABEL_15:
  v28 = (unsigned int **)((char *)v112 + 152);
  v29 = (unsigned int)v5 >> *(_DWORD *)(*((_QWORD *)v112 + 19) + 20LL);
  if ( v29 < *((_DWORD *)v112 + 40) )
  {
    v65 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)v112 + 152);
LABEL_61:
    v30 = (_QWORD *)v65;
    goto LABEL_18;
  }
  if ( v29 >= *((_DWORD *)v112 + 41) )
  {
    v65 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)v112 + 152);
    goto LABEL_61;
  }
  v30 = (_QWORD *)(*((_QWORD *)v112 + 21) + 8LL * (v29 - *((_DWORD *)v112 + 40)));
LABEL_18:
  if ( !*v30 )
  {
    v31 = *v28;
    v32 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local((Concurrency::details::platform *)(*v28 + 12));
    v33 = v32;
    v34 = *(_QWORD *)(v32 + 24);
    if ( *(_QWORD *)(v32 + 16) == v34 )
    {
      v57 = *(unsigned int *)(v32 + 8);
      if ( (unsigned int)v57 < v31[7] )
      {
        v35 = (void *)(*(_QWORD *)v32 + 8 * v57);
        v62 = v57 + v31[2];
      }
      else
      {
        v58 = _aligned_malloc(8LL * v31[7], v31[8]);
        v115[0] = v58;
        v35 = v58;
        if ( !v58 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x430,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
            v59);
        v103 = *(_QWORD **)(v33 + 48);
        if ( v103 == *(_QWORD **)(v33 + 56) )
        {
          std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
            v33 + 40,
            v103,
            v115);
          v35 = (void *)v115[0];
        }
        else
        {
          *v103 = v58;
          *(_QWORD *)(v33 + 48) += 8LL;
        }
        v104 = v31[6] * ((__int64)(*(_QWORD *)(v33 + 48) - *(_QWORD *)(v33 + 40)) >> 3);
        v105 = (__int64)(*(_QWORD *)(v33 + 32) - *(_QWORD *)(v33 + 16)) >> 3;
        v115[0] = v104;
        if ( v104 > v105 )
        {
          if ( v104 > 0x1FFFFFFFFFFFFFFFLL )
            goto LABEL_108;
          std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v33 + 16, v115);
        }
        v19 = v114;
        *(_QWORD *)v33 = v35;
        v62 = v31[2];
      }
      *(_DWORD *)(v33 + 8) = v62;
    }
    else
    {
      v35 = *(void **)(v34 - 8);
      *(_QWORD *)(v32 + 24) = v34 - 8;
    }
    *v30 = v35;
    memset_0(v35, 0, v31[1]);
  }
  v4 = v117;
  v23 = v119;
  v36 = (unsigned int)v113 & (*v28)[4];
  v21 = v118;
  v37 = *(_QWORD *)(*v30 + 8 * v36);
  if ( (v19 & v37) == 0 )
    *(_QWORD *)(*v30 + 8 * v36) = v37 | v19;
LABEL_24:
  if ( !*((_BYTE *)v4 + 824) )
    return;
  v38 = v21;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)v112 + 51) - *((_QWORD *)v112 + 50)) >> 3) <= v21 )
    inverted::CPidWids::Reserve(
      (struct inverted::CCombinedRankCursor::CThreadData *)((char *)v112 + 392),
      (unsigned int)(v23 + 1));
  v39 = *((_QWORD *)v112 + 50);
  v40 = (unsigned int **)(v39 + 24 * v38);
  v41 = (unsigned int)v5 >> (*v40)[5];
  if ( v41 < *((_DWORD *)v40 + 2) )
  {
    v64 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v39 + 24 * v38);
  }
  else
  {
    if ( v41 < *((_DWORD *)v40 + 3) )
    {
      v42 = &v40[2][2 * (v41 - *((_DWORD *)v40 + 2))];
      goto LABEL_30;
    }
    v64 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v39 + 24 * v38);
  }
  v42 = (unsigned int *)v64;
LABEL_30:
  if ( *(_QWORD *)v42 )
    goto LABEL_34;
  v43 = *v40;
  v44 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local((Concurrency::details::platform *)(*v40 + 12));
  v45 = v44;
  v46 = (_QWORD *)(v44 + 16);
  if ( *(_QWORD *)(v44 + 16) == *(_QWORD *)(v44 + 24) )
  {
    v54 = *(unsigned int *)(v44 + 8);
    if ( (unsigned int)v54 < v43[7] )
    {
      v48 = (void *)(*(_QWORD *)v44 + 8 * v54);
      v61 = v54 + v43[2];
LABEL_52:
      *(_DWORD *)(v45 + 8) = v61;
      goto LABEL_33;
    }
    v55 = (inverted::CCombinedRankCursor *)_aligned_malloc(8LL * v43[7], v43[8]);
    v117 = v55;
    v48 = v55;
    if ( !v55 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x430,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
        v56);
    v100 = *(inverted::CCombinedRankCursor ***)(v45 + 48);
    if ( v100 == *(inverted::CCombinedRankCursor ***)(v45 + 56) )
    {
      std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
        v45 + 40,
        v100,
        &v117);
      v48 = v117;
    }
    else
    {
      *v100 = v55;
      *(_QWORD *)(v45 + 48) += 8LL;
    }
    v101 = v43[6] * ((__int64)(*(_QWORD *)(v45 + 48) - *(_QWORD *)(v45 + 40)) >> 3);
    v102 = (__int64)(v46[2] - *v46) >> 3;
    v117 = (inverted::CCombinedRankCursor *)v101;
    if ( v101 <= v102 )
    {
LABEL_51:
      *(_QWORD *)v45 = v48;
      v61 = v43[2];
      goto LABEL_52;
    }
    if ( v101 <= 0x1FFFFFFFFFFFFFFFLL )
    {
      std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v46, &v117);
      goto LABEL_51;
    }
LABEL_108:
    std::_Xlength_error("vector too long");
  }
  v47 = (void **)(*(_QWORD *)(v44 + 24) - 8LL);
  v48 = *v47;
  *(_QWORD *)(v45 + 24) = v47;
LABEL_33:
  *(_QWORD *)v42 = v48;
  memset_0(v48, 0, v43[1]);
  v19 = v114;
LABEL_34:
  v49 = (unsigned int)v113 & (*v40)[4];
  v50 = *(_QWORD *)(*(_QWORD *)v42 + 8 * v49);
  if ( (v19 & v50) == 0 )
    *(_QWORD *)(*(_QWORD *)v42 + 8 * v49) = v50 | v19;
}

```

## disassembly

```asm
0x1800808c0  mov     [rsp-40h+arg_18], r9b
0x1800808c5  mov     [rsp-40h+arg_8], dx
0x1800808ca  mov     [rsp-40h+arg_0], rcx
0x1800808cf  push    rbp
0x1800808d0  push    rbx
0x1800808d1  push    rsi
0x1800808d2  push    rdi
0x1800808d3  push    r12
0x1800808d5  push    r13
0x1800808d7  push    r14
0x1800808d9  push    r15
0x1800808db  mov     rbp, rsp
0x1800808de  sub     rsp, 58h
0x1800808e2  mov     rdi, rcx
0x1800808e5  mov     r14d, r8d
0x1800808e8  mov     rcx, [rcx+318h]
0x1800808ef  mov     bl, r9b
0x1800808f2  call    ?local@?$combinable@VCThreadData@CCombinedRankCursor@inverted@@@TPUtils@@QEAAAEAVCThreadData@CCombinedRankCursor@inverted@@XZ; TPUtils::combinable<inverted::CCombinedRankCursor::CThreadData>::local(void)
0x1800808f7  mov     edx, r14d
0x1800808fa  mov     [rbp+var_38], rax
0x1800808fe  mov     r15, rax
0x180080901  lea     rsi, [rax+80h]
0x180080908  mov     rcx, [rsi]
0x18008090b  mov     ecx, [rcx+14h]
0x18008090e  shr     edx, cl
0x180080910  cmp     edx, [rsi+8]
0x180080913  jb      loc_180080D0F
0x180080919  cmp     edx, [rsi+0Ch]
0x18008091c  jnb     loc_180080DA9
0x180080922  sub     edx, [rsi+8]
0x180080925  mov     rax, [rsi+10h]
0x180080929  lea     r12, [rax+rdx*8]
0x18008092d  cmp     qword ptr [r12], 0
0x180080932  jnz     short loc_180080979
0x180080934  mov     r15, [rsi]
0x180080937  lea     rcx, [r15+30h]
0x18008093b  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x180080940  mov     rbx, rax
0x180080943  mov     rcx, [rax+18h]
0x180080947  cmp     [rax+10h], rcx
0x18008094b  jz      loc_180080BBE
0x180080951  lea     rax, [rcx-8]
0x180080955  mov     rdi, [rax]
0x180080958  mov     [rbx+18h], rax
0x18008095c  mov     [r12], rdi
0x180080960  xor     edx, edx; Val
0x180080962  mov     r8d, [r15+4]; Size
0x180080966  mov     rcx, rdi; void *
0x180080969  call    memset_0
0x18008096e  mov     bl, [rbp+arg_18]
0x180080971  mov     rdi, [rbp+arg_0]
0x180080975  mov     r15, [rbp+var_38]
0x180080979  mov     rax, [rsi]
0x18008097c  mov     rcx, r14
0x18008097f  mov     r8, [r12]
0x180080983  mov     r13d, 1
0x180080989  shr     rcx, 6
0x18008098d  mov     [rbp+var_30], rcx
0x180080991  mov     edx, [rax+10h]
0x180080994  and     rdx, rcx
0x180080997  mov     ecx, r14d
0x18008099a  shl     r13, cl
0x18008099d  mov     [rbp+var_20], r13
0x1800809a1  mov     rax, [r8+rdx*8]
0x1800809a5  test    r13, rax
0x1800809a8  jnz     short loc_1800809B1
0x1800809aa  or      rax, r13
0x1800809ad  mov     [r8+rdx*8], rax
0x1800809b1  movzx   r10d, [rbp+arg_8]
0x1800809b6  mov     rdx, [rdi+0A0h]
0x1800809bd  mov     eax, r10d
0x1800809c0  mov     r9d, r10d
0x1800809c3  mov     [rbp+arg_10], r10d
0x1800809c7  mov     ecx, [rdx+14h]
0x1800809ca  shr     eax, cl
0x1800809cc  mov     ecx, [rdi+0A8h]
0x1800809d2  cmp     eax, ecx
0x1800809d4  jb      short loc_180080A16
0x1800809d6  cmp     eax, [rdi+0ACh]
0x1800809dc  jnb     short loc_180080A16
0x1800809de  sub     eax, ecx
0x1800809e0  mov     ecx, eax
0x1800809e2  mov     rax, [rdi+0B0h]
0x1800809e9  mov     r8, [rax+rcx*8]
0x1800809ed  test    r8, r8
0x1800809f0  jz      short loc_180080A16
0x1800809f2  mov     edx, [rdx+10h]
0x1800809f5  mov     eax, r10d
0x1800809f8  shr     rax, 6
0x1800809fc  and     rdx, rax
0x1800809ff  mov     eax, r10d
0x180080a02  and     eax, 3Fh
0x180080a05  movzx   ecx, al
0x180080a08  mov     rax, [r8+rdx*8]
0x180080a0c  bt      rax, rcx
0x180080a10  jb      loc_180080D42
0x180080a16  test    bl, bl
0x180080a18  jz      loc_180080AC0
0x180080a1e  mov     rbx, [rbp+var_38]
0x180080a22  mov     edx, r14d
0x180080a25  add     rbx, 98h
0x180080a2c  mov     rcx, [rbx]
0x180080a2f  mov     ecx, [rcx+14h]
0x180080a32  shr     edx, cl
0x180080a34  cmp     edx, [rbx+8]
0x180080a37  jb      loc_180080D32
0x180080a3d  cmp     edx, [rbx+0Ch]
0x180080a40  jnb     loc_180080DC6
0x180080a46  sub     edx, [rbx+8]
0x180080a49  mov     rax, [rbx+10h]
0x180080a4d  lea     r12, [rax+rdx*8]
0x180080a51  cmp     qword ptr [r12], 0
0x180080a56  jnz     short loc_180080A92
0x180080a58  mov     r15, [rbx]
0x180080a5b  lea     rcx, [r15+30h]
0x180080a5f  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x180080a64  mov     rdi, rax
0x180080a67  mov     rcx, [rax+18h]
0x180080a6b  cmp     [rax+10h], rcx
0x180080a6f  jz      loc_180080C4A
0x180080a75  lea     rax, [rcx-8]
0x180080a79  mov     rsi, [rax]
0x180080a7c  mov     [rdi+18h], rax
0x180080a80  mov     [r12], rsi
0x180080a84  xor     edx, edx; Val
0x180080a86  mov     r8d, [r15+4]; Size
0x180080a8a  mov     rcx, rsi; void *
0x180080a8d  call    memset_0
0x180080a92  mov     rax, [rbx]
0x180080a95  mov     rdx, [r12]
0x180080a99  mov     rdi, [rbp+arg_0]
0x180080a9d  mov     r9d, [rbp+arg_10]
0x180080aa1  mov     ecx, [rax+10h]
0x180080aa4  and     rcx, [rbp+var_30]
0x180080aa8  movzx   r10d, [rbp+arg_8]
0x180080aad  mov     r8, [rdx+rcx*8]
0x180080ab1  test    r8, r13
0x180080ab4  jnz     short loc_180080AC0
0x180080ab6  mov     rax, r13
0x180080ab9  or      rax, r8
0x180080abc  mov     [rdx+rcx*8], rax
0x180080ac0  cmp     byte ptr [rdi+338h], 0
0x180080ac7  jz      loc_180080BAD
0x180080acd  mov     rbx, [rbp+var_38]
0x180080ad1  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180080adb  movzx   edi, r10w
0x180080adf  mov     rax, [rbx+198h]
0x180080ae6  sub     rax, [rbx+190h]
0x180080aed  sar     rax, 3
0x180080af1  imul    rax, rcx
0x180080af5  cmp     rax, rdi
0x180080af8  ja      short loc_180080B0A
0x180080afa  lea     edx, [r9+1]; unsigned __int64
0x180080afe  lea     rcx, [rbx+188h]; this
0x180080b05  call    ?Reserve@CPidWids@inverted@@AEAAX_K@Z; inverted::CPidWids::Reserve(unsigned __int64)
0x180080b0a  mov     rax, [rbx+190h]
0x180080b11  lea     rcx, [rdi+rdi*2]
0x180080b15  lea     rsi, [rax+rcx*8]
0x180080b19  mov     rcx, [rsi]
0x180080b1c  mov     ecx, [rcx+14h]
0x180080b1f  shr     r14d, cl
0x180080b22  cmp     r14d, [rsi+8]
0x180080b26  jb      loc_180080D1F
0x180080b2c  cmp     r14d, [rsi+0Ch]
0x180080b30  jnb     loc_180080DB6
0x180080b36  sub     r14d, [rsi+8]
0x180080b3a  mov     rax, [rsi+10h]
0x180080b3e  lea     r12, [rax+r14*8]
0x180080b42  cmp     qword ptr [r12], 0
0x180080b47  jnz     short loc_180080B8F
0x180080b49  mov     r14, [rsi]
0x180080b4c  lea     rcx, [r14+30h]
0x180080b50  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x180080b55  mov     rdi, rax
0x180080b58  lea     r13, [rax+10h]
0x180080b5c  mov     rcx, [r13+8]
0x180080b60  cmp     [r13+0], rcx
0x180080b64  jz      loc_180080C04
0x180080b6a  mov     rax, [rax+18h]
0x180080b6e  add     rax, 0FFFFFFFFFFFFFFF8h
0x180080b72  mov     rbx, [rax]
0x180080b75  mov     [rdi+18h], rax
0x180080b79  mov     [r12], rbx
0x180080b7d  xor     edx, edx; Val
0x180080b7f  mov     r8d, [r14+4]; Size
0x180080b83  mov     rcx, rbx; void *
0x180080b86  call    memset_0
0x180080b8b  mov     r13, [rbp+var_20]
0x180080b8f  mov     rax, [rsi]
0x180080b92  mov     ecx, [rax+10h]
0x180080b95  and     rcx, [rbp+var_30]
0x180080b99  mov     rax, [r12]
0x180080b9d  mov     rdx, [rax+rcx*8]
0x180080ba1  test    rdx, r13
0x180080ba4  jnz     short loc_180080BAD
0x180080ba6  or      r13, rdx
0x180080ba9  mov     [rax+rcx*8], r13
0x180080bad  add     rsp, 58h
0x180080bb1  pop     r15
0x180080bb3  pop     r14
0x180080bb5  pop     r13
0x180080bb7  pop     r12
0x180080bb9  pop     rdi
0x180080bba  pop     rsi
0x180080bbb  pop     rbx
0x180080bbc  pop     rbp
0x180080bbd  retn
0x180080bbe  mov     r8d, [rax+8]
0x180080bc2  cmp     r8d, [r15+1Ch]
0x180080bc6  jb      loc_180080C90
0x180080bcc  mov     ecx, [r15+1Ch]
0x180080bd0  mov     edx, [r15+20h]; Alignment
0x180080bd4  shl     rcx, 3; Size
0x180080bd8  call    cs:__imp__aligned_malloc
0x180080bde  mov     [rbp+var_20], rax
0x180080be2  mov     rdi, rax
0x180080be5  test    rax, rax
0x180080be8  jnz     loc_180080FE5
0x180080bee  mov     rcx, [rbp+40h]; this
0x180080bf2  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180080bf9  mov     edx, 430h; void *
0x180080bfe  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180080c04  mov     r8d, [rax+8]
0x180080c08  cmp     r8d, [r14+1Ch]
0x180080c0c  jb      loc_180080CB8
0x180080c12  mov     ecx, [r14+1Ch]
0x180080c16  mov     edx, [r14+20h]; Alignment
0x180080c1a  shl     rcx, 3; Size
0x180080c1e  call    cs:__imp__aligned_malloc
0x180080c24  mov     [rbp+arg_0], rax
0x180080c28  mov     rbx, rax
0x180080c2b  test    rax, rax
0x180080c2e  jnz     loc_18008104C
0x180080c34  mov     rcx, [rbp+40h]; this
0x180080c38  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180080c3f  mov     edx, 430h; void *
0x180080c44  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180080c4a  mov     r8d, [rax+8]
0x180080c4e  cmp     r8d, [r15+1Ch]
0x180080c52  jb      loc_180080CE3
0x180080c58  mov     ecx, [r15+1Ch]
0x180080c5c  mov     edx, [r15+20h]; Alignment
0x180080c60  shl     rcx, 3; Size
0x180080c64  call    cs:__imp__aligned_malloc
0x180080c6a  mov     [rbp+var_18], rax
0x180080c6e  mov     rsi, rax
0x180080c71  test    rax, rax
0x180080c74  jnz     loc_1800810A3
0x180080c7a  mov     rcx, [rbp+40h]; this
0x180080c7e  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180080c85  mov     edx, 430h; void *
0x180080c8a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180080c90  mov     rcx, [rax]
0x180080c93  lea     rdi, [rcx+r8*8]
0x180080c97  mov     ecx, [r15+8]
0x180080c9b  add     ecx, r8d
0x180080c9e  jmp     short loc_180080CB0
0x180080ca0  lea     rdx, [rbp+var_18]
0x180080ca4  call    ??$_Reallocate@$0A@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<ulong,ulong>>::_Reallocate<0>(unsigned __int64 &)
0x180080ca9  mov     [rbx], rdi
0x180080cac  mov     ecx, [r15+8]
0x180080cb0  mov     [rbx+8], ecx
0x180080cb3  jmp     loc_18008095C
0x180080cb8  mov     rcx, [rax]
0x180080cbb  lea     rbx, [rcx+r8*8]
0x180080cbf  mov     ecx, [r14+8]
0x180080cc3  add     ecx, r8d
0x180080cc6  jmp     short loc_180080CDB
0x180080cc8  lea     rdx, [rbp+arg_0]
0x180080ccc  mov     rcx, r13
0x180080ccf  call    ??$_Reallocate@$0A@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<ulong,ulong>>::_Reallocate<0>(unsigned __int64 &)
0x180080cd4  mov     [rdi], rbx
0x180080cd7  mov     ecx, [r14+8]
0x180080cdb  mov     [rdi+8], ecx
0x180080cde  jmp     loc_180080B79
0x180080ce3  mov     rcx, [rax]
0x180080ce6  lea     rsi, [rcx+r8*8]
0x180080cea  mov     ecx, [r15+8]
0x180080cee  add     ecx, r8d
0x180080cf1  jmp     short loc_180080D07
0x180080cf3  lea     rdx, [rbp+var_18]
0x180080cf7  call    ??$_Reallocate@$0A@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<ulong,ulong>>::_Reallocate<0>(unsigned __int64 &)
0x180080cfc  mov     r13, [rbp+var_20]
0x180080d00  mov     [rdi], rsi
0x180080d03  mov     ecx, [r15+8]
0x180080d07  mov     [rdi+8], ecx
0x180080d0a  jmp     loc_180080A80
0x180080d0f  mov     rcx, rsi
0x180080d12  call    ?_AddPagesToStart@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x180080d17  mov     r12, rax
0x180080d1a  jmp     loc_18008092D
0x180080d1f  mov     edx, r14d
0x180080d22  mov     rcx, rsi
0x180080d25  call    ?_AddPagesToStart@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x180080d2a  mov     r12, rax
0x180080d2d  jmp     loc_180080B42
0x180080d32  mov     rcx, rbx
0x180080d35  call    ?_AddPagesToStart@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x180080d3a  mov     r12, rax
0x180080d3d  jmp     loc_180080A51
  ... truncated ...
```
