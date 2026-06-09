# inverted::CInvertedIndex::EndDocument(void *,long,std::function<void (void)> const &)

- ea: `0x1800b9a30`
- end: `0x1800ba8a4`
- name: `?EndDocument@CInvertedIndex@inverted@@UEAAXPEAXJAEBV?$function@$$A6AXXZ@std@@@Z`
- size: `3700`
- prototype: `__int64 __fastcall(inverted::CInvertedIndex *this, inverted::SIndexingDocument *)`
- caller_count: `0`
- callee_count: `50`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18002a3e0`
- `0x18002be24`
- `0x18002f284`
- `0x18002f6e0`
- `0x180030230`
- `0x1800302f4`
- `0x180030a84`
- `0x1800324c8`
- `0x180036d60`
- `0x180047e78`
- `0x18004d9d8`
- `0x180050858`
- `0x180050c58`
- `0x18005166c`
- `0x1800516b8`
- `0x180076e30`
- `0x1800791ac`
- `0x1800791d8`
- `0x180087674`
- `0x180088214`
- `0x180088bc8`
- `0x18008904c`
- `0x180089458`
- `0x1800ae484`
- `0x1800b8c2c`
- `0x1800b9034`
- `0x1800b9064`
- `0x1800b9a30`
- `0x1800ba918`
- `0x1800ba944`
- `0x1800ba9a0`
- `0x1800baac4`
- `0x1800babc8`
- `0x1800bac7c`
- `0x1800bacbc`
- `0x1800bad24`
- `0x1800bad80`
- `0x1800e40a4`
- `0x1800e9920`
- `0x1801183f0`
- `0x18013d1e4`
- `0x18013e868`
- `0x1801470d4`
- `0x180147190`
- `0x18015708c`
- `0x180170000`
- `0x180188dc0`
- `0x180189cce`
- `0x180217258`
- `0x1802c0010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b9c5b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b9f7a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800ba403`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b9c5b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800b9f7a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800ba403`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9bbe`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9eda`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800ba36b`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9bbe`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800b9eda`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800ba36b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ba87e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ba87e`
- `cryptdll!MD5Final` at `0x1800ba196`
- `cryptdll!MD5Final` at `0x1800ba196`

## string_xrefs

- `0x1800b9bd9`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800b9ef5`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800ba386`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x1800ba699`: `Partial Item Update Commited - Updated PIDs:`
- `0x1800b9db5`: `PID deleted by omission: %d`
- `0x1800ba1e2`: `MD5 Unchanged - Not commiting the following properties:`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall inverted::CInvertedIndex::EndDocument(
        inverted::CInvertedIndex *this,
        inverted::SIndexingDocument *a2,
        int a3,
        __int64 a4)
{
  int v4; // r15d
  bool v7; // di
  RTL_SRWLOCK *v8; // rsi
  __int64 v9; // rcx
  struct inverted::PROPERTYVALUE *OldProp; // rax
  _WORD *v11; // rbx
  _WORD *v12; // rax
  char *v13; // r15
  unsigned int v14; // edi
  unsigned int v15; // edx
  _QWORD *v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rdx
  void *v22; // rdi
  const char *v23; // r9
  _QWORD *v24; // rax
  _QWORD *v25; // rdx
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rax
  int *j; // rdi
  _DWORD *v31; // rbx
  __int64 v32; // rdx
  unsigned int v33; // eax
  unsigned int v34; // ecx
  __int64 v35; // r9
  __int64 v36; // rax
  inverted::PROPERTYVALUE *v37; // rcx
  unsigned int **v38; // r8
  unsigned int v39; // ebx
  unsigned int v40; // edx
  _QWORD *v41; // rax
  unsigned int *v42; // rbx
  __int64 v43; // r15
  __int64 v44; // rax
  __int64 v45; // rdx
  _WORD *v46; // rbx
  const char *v47; // r9
  _QWORD *v48; // rax
  _QWORD *v49; // rdx
  unsigned __int64 v50; // rdx
  void **v51; // rax
  _QWORD *v52; // r15
  unsigned __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // rax
  _DWORD *v56; // rbx
  __int64 v57; // rdx
  char *v58; // rax
  inverted::PROPERTYVALUE *v59; // rcx
  unsigned int BitGE; // ebx
  __int64 v61; // rdx
  char *v62; // r15
  unsigned int v63; // edx
  _QWORD *v64; // rax
  __int64 v65; // rdi
  __int64 v66; // rax
  __int64 v67; // rbx
  __int64 v68; // rcx
  __int64 v69; // r8
  void *v70; // rdi
  __int64 v71; // rdx
  void *v72; // rax
  const char *v73; // r9
  _QWORD *v74; // rdx
  unsigned __int64 v75; // rcx
  unsigned __int64 v76; // rdx
  __int64 v77; // rax
  unsigned __int64 v78; // r8
  __int64 v79; // r9
  unsigned __int64 v80; // rcx
  __int64 v81; // r8
  __int64 v82; // r9
  unsigned int k; // ebx
  __int64 v84; // rcx
  int v85; // eax
  int *v86; // rbx
  char *v87; // rdx
  int v88; // ecx
  __int64 v89; // rbx
  __int64 v90; // rax
  unsigned int v91; // [rsp+30h] [rbp-E8h]
  unsigned int v92; // [rsp+30h] [rbp-E8h]
  unsigned int v93; // [rsp+30h] [rbp-E8h]
  unsigned int *v94; // [rsp+38h] [rbp-E0h]
  _QWORD *v95; // [rsp+38h] [rbp-E0h]
  unsigned int v96; // [rsp+38h] [rbp-E0h]
  _QWORD *v97; // [rsp+38h] [rbp-E0h]
  _QWORD *v98; // [rsp+40h] [rbp-D8h]
  unsigned int *v99; // [rsp+40h] [rbp-D8h]
  __int64 v100; // [rsp+40h] [rbp-D8h]
  _WORD *v101; // [rsp+48h] [rbp-D0h] BYREF
  char *v102; // [rsp+50h] [rbp-C8h]
  char *v103; // [rsp+58h] [rbp-C0h]
  _DWORD *i; // [rsp+60h] [rbp-B8h] BYREF
  std::_Ref_count_base *v105; // [rsp+68h] [rbp-B0h]
  void *v106; // [rsp+70h] [rbp-A8h] BYREF
  unsigned int v107; // [rsp+78h] [rbp-A0h]
  int v108; // [rsp+80h] [rbp-98h] BYREF
  __int64 v109; // [rsp+88h] [rbp-90h]
  __int64 v110; // [rsp+90h] [rbp-88h]
  std::_Ref_count_base *v111[2]; // [rsp+98h] [rbp-80h] BYREF
  __int64 v112; // [rsp+A8h] [rbp-70h] BYREF
  int v113; // [rsp+B0h] [rbp-68h] BYREF
  char *v114; // [rsp+B8h] [rbp-60h]
  __int64 v115; // [rsp+C0h] [rbp-58h]
  std::_Ref_count_base *v116[2]; // [rsp+C8h] [rbp-50h]
  char *v117; // [rsp+D8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  __int64 v120; // [rsp+128h] [rbp+10h] BYREF
  int v121; // [rsp+130h] [rbp+18h]
  __int64 v122; // [rsp+138h] [rbp+20h]

  v122 = a4;
  v121 = a3;
  v4 = a3;
  v7 = 0;
  LOBYTE(v120) = 0;
  v8 = (RTL_SRWLOCK *)((char *)this + 680);
  v117 = (char *)this + 680;
  CSRWLock::AcquireExclusive((inverted::CInvertedIndex *)((char *)this + 680));
  inverted::CInvertedIndex::_ThrowIfShutdown(this);
  std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<inverted::SIndexingDocument>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<inverted::SIndexingDocument>>>,0>>::find(
    (char *)this + 824,
    &v112,
    a2);
  if ( v112 == *((_QWORD *)this + 103) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
  try
  {
    if ( v4 < 0 )
      goto LABEL_175;
    if ( *((_DWORD *)a2 + 2) == 2 )
    {
      OldProp = inverted::SIndexingDocument::FindOldProp(a2, *((_DWORD *)this + 83));
      if ( OldProp )
      {
        v11 = (_WORD *)*((_QWORD *)OldProp + 1);
        v12 = &v11[*((_QWORD *)OldProp + 2) >> 1];
        for ( i = v12; ; v12 = i )
        {
          v101 = v11;
          if ( v11 >= v12 )
            break;
          if ( (*((_BYTE *)a2 + 12) & 1) == 0 )
            inverted::SIndexingDocument::SetPropSeen(a2, *v11, 1);
          v13 = (char *)a2 + 312;
          v14 = (unsigned __int16)*v11;
          v91 = v14;
          v15 = v14 >> *(_DWORD *)(*((_QWORD *)a2 + 39) + 20LL);
          if ( v15 < *((_DWORD *)a2 + 80) )
          {
            v16 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)a2 + 312);
            v98 = v16;
          }
          else
          {
            if ( v15 >= *((_DWORD *)a2 + 81) )
              v16 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)a2 + 312);
            else
              v16 = (_QWORD *)(*((_QWORD *)a2 + 41) + 8LL * (v15 - *((_DWORD *)a2 + 80)));
            v98 = v16;
          }
          if ( !*v16 )
          {
            v17 = *(_QWORD *)v13;
            v94 = *(unsigned int **)v13;
            v18 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v13 + 48LL);
            v19 = v18;
            v20 = *(_QWORD *)(v18 + 24);
            if ( *(_QWORD *)(v18 + 16) == v20 )
            {
              v21 = *(unsigned int *)(v18 + 8);
              if ( (unsigned int)v21 >= *(_DWORD *)(v17 + 28) )
              {
                v22 = _aligned_malloc(8LL * *(unsigned int *)(v17 + 28), *(unsigned int *)(v17 + 32));
                v106 = v22;
                if ( !v22 )
                  wil::details::in1diag3::_Throw_NullAlloc(
                    retaddr,
                    (void *)0x430,
                    (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                    v23);
                v24 = (_QWORD *)(v19 + 40);
                v25 = *(_QWORD **)(v19 + 48);
                if ( v25 == *(_QWORD **)(v19 + 56) )
                {
                  std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                    v24,
                    v25,
                    &v106);
                  v22 = v106;
                  v24 = (_QWORD *)(v19 + 40);
                }
                else
                {
                  *v25 = v22;
                  *(_QWORD *)(v19 + 48) += 8LL;
                }
                v26 = v94[6] * ((__int64)(v24[1] - *v24) >> 3);
                v106 = (void *)v26;
                if ( v26 > (__int64)(*(_QWORD *)(v19 + 32) - *(_QWORD *)(v19 + 16)) >> 3 )
                {
                  if ( v26 > 0x1FFFFFFFFFFFFFFFLL )
                    std::_Xlength_error("vector too long");
                  std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v19 + 16, &v106);
                }
                *(_QWORD *)v19 = v22;
                *(_DWORD *)(v19 + 8) = v94[2];
              }
              else
              {
                v22 = (void *)(*(_QWORD *)v18 + 8 * v21);
                *(_DWORD *)(v18 + 8) = v21 + v94[2];
              }
            }
            else
            {
              v22 = *(void **)(v20 - 8);
              *(_QWORD *)(v18 + 24) = v20 - 8;
            }
            *v98 = v22;
            memset_0(v22, 0, v94[1]);
            v11 = v101;
            v14 = v91;
          }
          v27 = *(unsigned int *)(*(_QWORD *)v13 + 16LL) & ((unsigned __int64)v14 >> 6);
          v28 = 1LL << (v14 & 0x3F);
          v29 = *(_QWORD *)(*v98 + 8 * v27);
          if ( (v29 & v28) == 0 )
            *(_QWORD *)(*v98 + 8 * v27) = v28 | v29;
          ++v11;
        }
      }
      for ( j = (int *)*((_QWORD *)a2 + 2); ; j += 10 )
      {
        if ( j == *((int **)a2 + 3) )
          goto LABEL_75;
        if ( *j != (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 80LL))(*((_QWORD *)this + 30)) )
        {
          std::_Tree<std::_Tmap_traits<unsigned int,unsigned short,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,unsigned short>>,0>>::find(
            (char *)this + 760,
            &i,
            j);
          v31 = i;
          if ( i != *((_DWORD **)this + 95) )
          {
            v32 = *((_QWORD *)a2 + 36);
            v33 = *((unsigned __int16 *)i + 16) >> *(_DWORD *)(v32 + 20);
            v34 = *((_DWORD *)a2 + 74);
            if ( v33 < v34
              || v33 >= *((_DWORD *)a2 + 75)
              || (v35 = *(_QWORD *)(*((_QWORD *)a2 + 38) + 8LL * (v33 - v34))) == 0
              || (v36 = *(_QWORD *)(v35
                                  + 8
                                  * (((unsigned __int64)*((unsigned __int16 *)i + 16) >> 6) & *(unsigned int *)(v32 + 16))),
                  !_bittest64(&v36, i[8] & 0x3F)) )
            {
              if ( (*((_BYTE *)a2 + 12) & 1) == 0 )
                break;
            }
          }
        }
LABEL_74:
        ;
      }
      ETWLog::Log(L"PID deleted by omission: %d", *((unsigned __int16 *)i + 16));
      v109 = 0;
      v110 = 0;
      *(_OWORD *)v111 = 0;
      v108 = *j;
      v37 = (inverted::PROPERTYVALUE *)*((_QWORD *)a2 + 6);
      if ( v37 == *((inverted::PROPERTYVALUE **)a2 + 7) )
      {
        std::vector<inverted::PROPERTYVALUE>::_Emplace_reallocate<inverted::PROPERTYVALUE const &>(
          (char *)a2 + 40,
          *((_QWORD *)a2 + 6),
          &v108);
      }
      else
      {
        inverted::PROPERTYVALUE::PROPERTYVALUE(v37, (const struct inverted::PROPERTYVALUE *)&v108);
        *((_QWORD *)a2 + 6) += 40LL;
      }
      v38 = (unsigned int **)((char *)a2 + 264);
      v39 = *((unsigned __int16 *)v31 + 16);
      v92 = v39;
      v40 = v39 >> *(_DWORD *)(*((_QWORD *)a2 + 33) + 20LL);
      if ( v40 < *((_DWORD *)a2 + 68) )
      {
        v41 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)a2 + 264);
        v95 = v41;
      }
      else
      {
        if ( v40 < *((_DWORD *)a2 + 69) )
        {
          v41 = (_QWORD *)(*((_QWORD *)a2 + 35) + 8LL * (v40 - *((_DWORD *)a2 + 68)));
          v95 = v41;
LABEL_53:
          if ( *v41 )
          {
            v52 = v95;
          }
          else
          {
            v42 = *v38;
            v99 = *v38;
            v43 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*v38 + 12);
            v44 = *(_QWORD *)(v43 + 24);
            if ( *(_QWORD *)(v43 + 16) == v44 )
            {
              v45 = *(unsigned int *)(v43 + 8);
              if ( (unsigned int)v45 >= v42[7] )
              {
                v46 = _aligned_malloc(8LL * v42[7], v42[8]);
                v101 = v46;
                if ( !v46 )
                  wil::details::in1diag3::_Throw_NullAlloc(
                    retaddr,
                    (void *)0x430,
                    (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
                    v47);
                v48 = (_QWORD *)(v43 + 40);
                v49 = *(_QWORD **)(v43 + 48);
                if ( v49 == *(_QWORD **)(v43 + 56) )
                {
                  std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
                    v48,
                    v49,
                    &v101);
                  v46 = v101;
                  v48 = (_QWORD *)(v43 + 40);
                }
                else
                {
                  *v49 = v46;
                  *(_QWORD *)(v43 + 48) += 8LL;
                }
                v50 = v99[6] * ((__int64)(v48[1] - *v48) >> 3);
                v101 = (_WORD *)v50;
                if ( v50 > (__int64)(*(_QWORD *)(v43 + 32) - *(_QWORD *)(v43 + 16)) >> 3 )
                {
                  if ( v50 > 0x1FFFFFFFFFFFFFFFLL )
                    std::_Xlength_error("vector too long");
                  std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v43 + 16, &v101);
                }
                *(_QWORD *)v43 = v46;
                *(_DWORD *)(v43 + 8) = v99[2];
              }
              else
              {
                v46 = (_WORD *)(*(_QWORD *)v43 + 8 * v45);
                *(_DWORD *)(v43 + 8) = v45 + v99[2];
              }
            }
            else
            {
              v51 = (void **)(v44 - 8);
              v46 = *v51;
              *(_QWORD *)(v43 + 24) = v51;
            }
            v52 = v95;
            *v95 = v46;
            memset_0(v46, 0, v99[1]);
            v39 = v92;
          }
          v53 = *(unsigned int *)(*((_QWORD *)a2 + 33) + 16LL) & ((unsigned __int64)v39 >> 6);
          v54 = 1LL << (v39 & 0x3F);
          v55 = *(_QWORD *)(*v52 + 8 * v53);
          if ( (v55 & v54) == 0 )
            *(_QWORD *)(*v52 + 8 * v53) = v54 | v55;
          if ( v111[1] )
            std::_Ref_count_base::_Decref(v111[1]);
          goto LABEL_74;
        }
        v41 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)a2 + 264);
        v95 = v41;
      }
      v38 = (unsigned int **)((char *)a2 + 264);
      goto LABEL_53;
    }
LABEL_75:
    v109 = 0;
    v110 = 0;
    *(_OWORD *)v111 = 0;
    v96 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::size((char *)a2 + 312);
    v108 = *((_DWORD *)this + 83);
    v56 = operator new(0x20u);
    i = v56;
    v56[2] = 1;
    v56[3] = 1;
    *(_QWORD *)v56 = &std::_Ref_count_obj2<inverted::CBuffer>::`vftable';
    inverted::CBuffer::CBuffer((inverted::CBuffer *)(v56 + 4), 2 * v96);
    i = v56 + 4;
    v105 = (std::_Ref_count_base *)v56;
    std::shared_ptr<inverted::ICatalogStorage>::operator=(v111, &i);
    if ( v105 )
      std::_Ref_count_base::_Decref(v105);
    v109 = *(_QWORD *)v111[0];
    v110 = 2LL * v96;
    dynamic_sparse_bit<unsigned __int64>::CopyTo<unsigned short *>((char *)a2 + 312, v57, v109, v110 + v109);
    if ( *((_DWORD *)a2 + 2) != 2
      || !inverted::SIndexingDocument::IdenticalOldPropExists(a2, (const struct inverted::PROPERTYVALUE *)&v108) )
    {
      std::vector<inverted::PROPERTYVALUE>::push_back((char *)a2 + 40, &v108);
    }
    v113 = -1;
    v114 = 0;
    v115 = 0;
    *(_OWORD *)v116 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdateCryptoAPIs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UpdateCryptoAPIs>::GetImpl'::`2'::impl) )
    {
      CngRsa32Compat_MD5Final((char *)a2 + 440);
      v113 = *((_DWORD *)this + 84);
      v58 = (char *)a2 + 448;
    }
    else
    {
      MD5Final((char *)a2 + 336);
      v113 = *((_DWORD *)this + 84);
      v58 = (char *)a2 + 424;
    }
    v115 = 16;
    v114 = v58;
    if ( *((_DWORD *)a2 + 2) == 2
      && inverted::SIndexingDocument::IdenticalOldPropExists(a2, (const struct inverted::PROPERTYVALUE *)&v113) )
    {
      ETWLog::Log(L"MD5 Unchanged - Not commiting the following properties:");
      inverted::LogBitVector(L"pids", (char *)a2 + 312);
      dynamic_sparse_bit<unsigned __int64>::Difference((char *)a2 + 264, (char *)a2 + 312);
    }
    else
    {
      v59 = (inverted::PROPERTYVALUE *)*((_QWORD *)a2 + 6);
      if ( v59 == *((inverted::PROPERTYVALUE **)a2 + 7) )
      {
        std::vector<inverted::PROPERTYVALUE>::_Emplace_reallocate<inverted::PROPERTYVALUE const &>(
          (char *)a2 + 40,
          *((_QWORD *)a2 + 6),
          &v113);
      }
      else
      {
        inverted::PROPERTYVALUE::PROPERTYVALUE(v59, (const struct inverted::PROPERTYVALUE *)&v113);
        *((_QWORD *)a2 + 6) += 40LL;
      }
    }
    if ( *((_DWORD *)a2 + 2) != 2 )
      goto LABEL_129;
    dynamic_sparse_bit<unsigned __int64>::begin((char *)a2 + 264, &v106);
    BitGE = v107;
    v93 = v107;
    while ( BitGE != -1 )
    {
      v61 = *((_QWORD *)this + 89);
      if ( BitGE >= 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 90) - v61) >> 2)
        || (*(_BYTE *)(v61 + 12LL * BitGE + 2) & 1) != 0
        || inverted::CInvertedIndex::_HasValueIndexForProperty(this, BitGE) )
      {
        goto LABEL_120;
      }
      v62 = (char *)a2 + 264;
      v63 = BitGE >> *(_DWORD *)(*((_QWORD *)a2 + 33) + 20LL);
      if ( v63 < *((_DWORD *)a2 + 68) )
      {
        v64 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)a2 + 264);
        v97 = v64;
      }
      else
      {
        if ( v63 >= *((_DWORD *)a2 + 69) )
          v64 = (_QWORD *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)a2 + 264);
        else
          v64 = (_QWORD *)(*((_QWORD *)a2 + 35) + 8LL * (v63 - *((_DWORD *)a2 + 68)));
        v97 = v64;
      }
      if ( !*v64 )
      {
        v65 = *(_QWORD *)v62;
        v100 = *(_QWORD *)v62;
        v66 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v62 + 48LL);
        v67 = v66;
        v68 = *(_QWORD *)(v66 + 24);
        if ( *(_QWORD *)(v66 + 16) == v68 )
        {
          v69 = *(unsigned int *)(v66 + 8);
          if ( (unsigned int)v69 < *(_DWORD *)(v65 + 28) )
          {
            v70 = (void *)(*(_QWORD *)v66 + 8 * v69);
            v71 = v100;
            *(_DWORD *)(v66 + 8) = v69 + *(_DWORD *)(v100 + 8);
LABEL_117:
            *v97 = v70;
            memset_0(v70, 0, *(unsigned int *)(v71 + 4));
            BitGE = v93;
            goto LABEL_118;
          }
          v72 = _aligned_malloc(8LL * *(unsigned int *)(v65 + 28), *(unsigned int *)(v65 + 32));
          v70 = v72;
          v101 = v72;
          if ( !v72 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x430,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
              v73);
          v74 = *(_QWORD **)(v67 + 48);
          if ( v74 == *(_QWORD **)(v67 + 56) )
          {
            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
              v67 + 40,
              v74,
              &v101);
            v70 = v101;
          }
          else
          {
            *v74 = v72;
            *(_QWORD *)(v67 + 48) += 8LL;
          }
          v75 = *(unsigned int *)(v100 + 24) * ((__int64)(*(_QWORD *)(v67 + 48) - *(_QWORD *)(v67 + 40)) >> 3);
          i = (_DWORD *)v75;
          if ( v75 > (__int64)(*(_QWORD *)(v67 + 32) - *(_QWORD *)(v67 + 16)) >> 3 )
          {
            if ( v75 > 0x1FFFFFFFFFFFFFFFLL )
              std::_Xlength_error("vector too long");
            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v67 + 16, &i);
          }
          *(_QWORD *)v67 = v70;
          *(_DWORD *)(v67 + 8) = *(_DWORD *)(v100 + 8);
          v62 = (char *)a2 + 264;
        }
        else
        {
          v70 = *(void **)(v68 - 8);
          *(_QWORD *)(v66 + 24) = v68 - 8;
        }
        v71 = v100;
        goto LABEL_117;
      }
LABEL_118:
      v76 = *(unsigned int *)(*(_QWORD *)v62 + 16LL) & ((unsigned __int64)BitGE >> 6);
      v77 = *(_QWORD *)(*v97 + 8 * v76);
      if ( (v77 & (1LL << BitGE)) != 0 )
        *(_QWORD *)(*v97 + 8 * v76) = (1LL << BitGE) ^ v77;
LABEL_120:
      BitGE = dynamic_sparse_bit<unsigned __int64>::NextBitGE(v106, BitGE + 1);
      v93 = BitGE;
    }
    dynamic_sparse_bit<unsigned __int64>::begin((char *)a2 + 264, &i);
    while ( 1 )
    {
      if ( (_DWORD)v105 == -1 )
      {
        dynamic_sparse_bit<unsigned __int64>::Empty((char *)a2 + 264);
        std::vector<inverted::PROPERTYVALUE>::clear((char *)a2 + 40);
        goto LABEL_129;
      }
      v78 = inverted::CInvertedIndex::_PidIndexToProperty(this, (unsigned __int16)v105);
      v79 = *((_QWORD *)this + 89);
      v80 = 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 90) - v79) >> 2);
      if ( v78 >= v80 )
        break;
      v80 = 256;
      if ( (*(_WORD *)(v79 + 12 * v78 + 2) & 0x100) == 0 )
        break;
      _sparse_bit_iterator<dynamic_sparse_bit<unsigned __int64>>::operator++(&i, &v101);
    }
    if ( (unsigned __int16)v78 >= 0x4000u )
      MicrosoftTelemetryAssertTriggeredNoArgs(v80);
LABEL_129:
    v81 = *((_QWORD *)a2 + 5);
    v82 = *((_QWORD *)a2 + 6);
    if ( v81 != v82 )
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int64))(**((_QWORD **)this + 30) + 88LL))(
        *((_QWORD *)this + 30),
        *(unsigned int *)a2,
        v81,
        0xCCCCCCCCCCCCCCCDuLL * ((v82 - v81) >> 3));
    if ( *((_DWORD *)a2 + 2) != 2
      || (unsigned __int8)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::HasAtLeast((char *)a2 + 264, 1) )
    {
      std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v101);
      if ( *((_DWORD *)a2 + 2) == 2 )
      {
        dynamic_sparse_bit<unsigned __int64>::begin((char *)a2 + 264, &i);
        for ( k = (unsigned int)v105; k != -1; k = dynamic_sparse_bit<unsigned __int64>::NextBitGE(i, k + 1) )
        {
          v84 = *((_QWORD *)a2 + 58);
          if ( k < (unsigned __int64)((*((_QWORD *)a2 + 59) - v84) >> 2) )
          {
            v85 = *(_DWORD *)(v84 + 4LL * k);
            if ( v85 )
            {
              LOWORD(v120) = k;
              HIDWORD(v120) = v85;
              if ( v102 == v103 )
              {
                std::vector<std::pair<unsigned int,unsigned int>>::_Emplace_reallocate<std::pair<unsigned int,unsigned int>>(
                  &v101,
                  v102,
                  &v120);
              }
              else
              {
                *(_QWORD *)v102 = v120;
                v102 += 8;
              }
            }
          }
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, char *, signed __int64, _WORD *))(***((_QWORD ***)this + 99) + 64LL))(
          **((_QWORD **)this + 99),
          *((unsigned int *)a2 + 1),
          (char *)a2 + 264,
          (v102 - (char *)v101) >> 3,
          v101);
        ++*((_DWORD *)this + 104);
        ETWLog::Log(L"Partial Item Update Commited - Updated PIDs:");
        inverted::LogBitVector(L"pids", (char *)a2 + 312);
      }
      else
      {
        v86 = (int *)*((_QWORD *)a2 + 58);
        v87 = v102;
        while ( v86 != *((int **)a2 + 59) )
        {
          v88 = *v86;
          if ( *v86 )
          {
            LOWORD(v120) = (__int64)(unsigned int)((_DWORD)v86 - *((_DWORD *)a2 + 116)) >> 2;
            HIDWORD(v120) = v88;
            if ( v87 == v103 )
            {
              std::vector<std::pair<unsigned int,unsigned int>>::_Emplace_reallocate<std::pair<unsigned int,unsigned int>>(
                &v101,
                v87,
                &v120);
              v87 = v102;
            }
            else
            {
              *(_QWORD *)v87 = v120;
              v87 = v102 + 8;
              v102 += 8;
            }
          }
          ++v86;
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, signed __int64))(***((_QWORD ***)this + 99) + 72LL))(
          **((_QWORD **)this + 99),
          *((unsigned int *)a2 + 1),
          (v87 - (char *)v101) >> 3);
        ++*((_DWORD *)this + 106);
      }
      v89 = *((_QWORD *)this + 99);
      if ( *(_QWORD *)(v89 + 24) == *(_QWORD *)(v89 + 32) )
      {
        std::vector<std::function<void (void)>>::_Emplace_reallocate<std::function<void (void)> const &>(
          v89 + 16,
          *(_QWORD *)(v89 + 24),
          v122);
      }
      else
      {
        std::function<void (void)>::function<void (void)>(*(_QWORD *)(v89 + 24), v122);
        *(_QWORD *)(v89 + 24) += 64LL;
      }
      std::shared_ptr<inverted::IInvertedIndex>::reset((char *)this + 888);
      v7 = *(_QWORD *)(*((_QWORD *)this + 99) + 24LL) - *(_QWORD *)(*((_QWORD *)this + 99) + 16LL) == 64;
      if ( v101 )
        std::_Deallocate<16>(v101, (v103 - (char *)v101) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    else
    {
      ++*((_DWORD *)this + 105);
      std::_Func_class<void,>::operator()(v122);
      v7 = v120;
    }
    if ( v116[1] )
      std::_Ref_count_base::_Decref(v116[1]);
    if ( v111[1] )
      std::_Ref_count_base::_Decref(v111[1]);
    v4 = v121;
  }
  catch ( ... )
  {
    inverted::CInvertedIndex::_EndDocument(this, v112);
    throw;
  }
LABEL_175:
  ((void (*)(void))inverted::CInvertedIndex::_EndDocument)();
  if ( v4 < 0
    && !*((_QWORD *)this + 104)
    && !(*(unsigned int (__fastcall **)(_QWORD))(***((_QWORD ***)this + 99) + 16LL))(**((_QWORD **)this + 99)) )
  {
    v90 = std::make_shared<inverted::SWordListData,>(&i);
    std::shared_ptr<inverted::ICatalogStorage>::operator=((char *)this + 792, v90);
    if ( v105 )
      std::_Ref_count_base::_Decref(v105);
  }
  inverted::CInvertedIndex::_CheckWordList(this, 0);
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  if ( v7 )
    inverted::CInvertedIndex::_SendStatsChangeNoLock(this);
}

```

## disassembly

```asm
0x1800b9a30  mov     rax, rsp
0x1800b9a33  mov     [rax+20h], r9
0x1800b9a37  mov     [rax+18h], r8d
0x1800b9a3b  mov     [rax+8], rcx
0x1800b9a3f  push    rbx
0x1800b9a40  push    rsi
0x1800b9a41  push    rdi
0x1800b9a42  push    r12
0x1800b9a44  push    r13
0x1800b9a46  push    r14
0x1800b9a48  push    r15
0x1800b9a4a  sub     rsp, 0E0h
0x1800b9a51  mov     r15d, r8d
0x1800b9a54  mov     r12, rdx
0x1800b9a57  mov     r13, rcx
0x1800b9a5a  xor     dil, dil
0x1800b9a5d  mov     byte ptr [rsp+118h+arg_8], dil
0x1800b9a65  lea     rsi, [rcx+2A8h]
0x1800b9a6c  mov     [rax-40h], rsi
0x1800b9a70  mov     rcx, rsi; this
0x1800b9a73  call    ?AcquireExclusive@CSRWLock@@QEAAXXZ; CSRWLock::AcquireExclusive(void)
0x1800b9a78  nop
0x1800b9a79  mov     rcx, r13; this
0x1800b9a7c  call    ?_ThrowIfShutdown@CInvertedIndex@inverted@@AEAAXXZ; inverted::CInvertedIndex::_ThrowIfShutdown(void)
0x1800b9a81  lea     rbx, [r13+338h]
0x1800b9a88  mov     r8, r12
0x1800b9a8b  lea     rdx, [rsp+118h+var_70]
0x1800b9a93  mov     rcx, rbx
0x1800b9a96  call    ?find@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@USIndexingDocument@inverted@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@USIndexingDocument@inverted@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@USIndexingDocument@inverted@@@std@@@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<inverted::SIndexingDocument>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<inverted::SIndexingDocument>>>,0>>::find(uint const &)
0x1800b9a9b  mov     r14, [rsp+118h+var_70]
0x1800b9aa3  cmp     r14, [rbx]
0x1800b9aa6  jnz     short loc_1800B9AAE
0x1800b9aa8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b9aad  nop
0x1800b9aae  test    r15d, r15d
0x1800b9ab1  js      loc_1800BA810
0x1800b9ab7  cmp     dword ptr [r12+8], 2
0x1800b9abd  jnz     loc_1800BA01C
0x1800b9ac3  mov     edx, [r13+14Ch]; unsigned int
0x1800b9aca  mov     rcx, r12; this
0x1800b9acd  call    ?FindOldProp@SIndexingDocument@inverted@@QEAAPEAUPROPERTYVALUE@2@I@Z; inverted::SIndexingDocument::FindOldProp(uint)
0x1800b9ad2  test    rax, rax
0x1800b9ad5  jz      loc_1800B9CF2
0x1800b9adb  mov     rbx, [rax+8]
0x1800b9adf  mov     rax, [rax+10h]
0x1800b9ae3  shr     rax, 1
0x1800b9ae6  lea     rax, [rbx+rax*2]
0x1800b9aea  mov     [rsp+118h+var_B8], rax
0x1800b9aef  mov     [rsp+118h+var_D0], rbx
0x1800b9af4  cmp     rbx, rax
0x1800b9af7  jnb     loc_1800B9CF2
0x1800b9afd  test    byte ptr [r12+0Ch], 1
0x1800b9b03  jnz     short loc_1800B9B13
0x1800b9b05  mov     r8b, 1; bool
0x1800b9b08  movzx   edx, word ptr [rbx]; unsigned __int16
0x1800b9b0b  mov     rcx, r12; this
0x1800b9b0e  call    ?SetPropSeen@SIndexingDocument@inverted@@QEAAXG_N@Z; inverted::SIndexingDocument::SetPropSeen(ushort,bool)
0x1800b9b13  lea     r15, [r12+138h]
0x1800b9b1b  movzx   edi, word ptr [rbx]
0x1800b9b1e  mov     [rsp+118h+var_E8], edi
0x1800b9b22  mov     rcx, [r15]
0x1800b9b25  mov     ecx, [rcx+14h]
0x1800b9b28  mov     edx, edi
0x1800b9b2a  shr     edx, cl
0x1800b9b2c  cmp     edx, [r15+8]
0x1800b9b30  jb      short loc_1800B9B5A
0x1800b9b32  cmp     edx, [r15+0Ch]
0x1800b9b36  jnb     short loc_1800B9B4B
0x1800b9b38  sub     edx, [r15+8]
0x1800b9b3c  mov     rax, [r15+10h]
0x1800b9b40  lea     rax, [rax+rdx*8]
0x1800b9b44  mov     [rsp+118h+var_D8], rax
0x1800b9b49  jmp     short loc_1800B9B67
0x1800b9b4b  mov     rcx, r15
0x1800b9b4e  call    ?_AddPagesToEnd@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9b53  mov     [rsp+118h+var_D8], rax
0x1800b9b58  jmp     short loc_1800B9B67
0x1800b9b5a  mov     rcx, r15
0x1800b9b5d  call    ?_AddPagesToStart@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9b62  mov     [rsp+118h+var_D8], rax
0x1800b9b67  cmp     qword ptr [rax], 0
0x1800b9b6b  jnz     loc_1800B9CAE
0x1800b9b71  mov     rdi, [r15]
0x1800b9b74  mov     [rsp+118h+var_E0], rdi
0x1800b9b79  lea     rcx, [rdi+30h]
0x1800b9b7d  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800b9b82  mov     rbx, rax
0x1800b9b85  mov     rcx, [rax+18h]
0x1800b9b89  cmp     [rax+10h], rcx
0x1800b9b8d  jnz     loc_1800B9C7F
0x1800b9b93  mov     edx, [rax+8]
0x1800b9b96  cmp     edx, [rdi+1Ch]
0x1800b9b99  jnb     short loc_1800B9BB4
0x1800b9b9b  mov     rax, [rax]
0x1800b9b9e  lea     rdi, [rax+rdx*8]
0x1800b9ba2  mov     rax, [rsp+118h+var_E0]
0x1800b9ba7  mov     ecx, [rax+8]
0x1800b9baa  add     ecx, edx
0x1800b9bac  mov     [rbx+8], ecx
0x1800b9baf  jmp     loc_1800B9C8A
0x1800b9bb4  mov     edx, [rdi+20h]; Alignment
0x1800b9bb7  mov     ecx, [rdi+1Ch]
0x1800b9bba  shl     rcx, 3; Size
0x1800b9bbe  call    cs:__imp__aligned_malloc
0x1800b9bc4  mov     rdi, rax
0x1800b9bc7  mov     [rsp+118h+var_A8], rax
0x1800b9bcc  mov     rcx, [rsp+118h]; this
0x1800b9bd4  test    rax, rax
0x1800b9bd7  jnz     short loc_1800B9BEA
0x1800b9bd9  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800b9be0  mov     edx, 430h; void *
0x1800b9be5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800b9bea  lea     rax, [rbx+28h]
0x1800b9bee  mov     rdx, [rax+8]
0x1800b9bf2  cmp     rdx, [rax+10h]
0x1800b9bf6  jz      short loc_1800B9C02
0x1800b9bf8  mov     [rdx], rdi
0x1800b9bfb  add     qword ptr [rax+8], 8
0x1800b9c00  jmp     short loc_1800B9C18
0x1800b9c02  lea     r8, [rsp+118h+var_A8]
0x1800b9c07  mov     rcx, rax
0x1800b9c0a  call    ??$_Emplace_reallocate@U?$pair@KK@std@@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAPEAU?$pair@KK@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<ulong,ulong>>::_Emplace_reallocate<std::pair<ulong,ulong>>(std::pair<ulong,ulong> * const,std::pair<ulong,ulong> &&)
0x1800b9c0f  mov     rdi, [rsp+118h+var_A8]
0x1800b9c14  lea     rax, [rbx+28h]
0x1800b9c18  mov     rcx, [rax+8]
0x1800b9c1c  sub     rcx, [rax]
0x1800b9c1f  sar     rcx, 3
0x1800b9c23  mov     rax, [rsp+118h+var_E0]
0x1800b9c28  mov     eax, [rax+18h]
0x1800b9c2b  imul    rcx, rax
0x1800b9c2f  mov     [rsp+118h+var_A8], rcx
0x1800b9c34  mov     rax, [rbx+20h]
0x1800b9c38  sub     rax, [rbx+10h]
0x1800b9c3c  sar     rax, 3
0x1800b9c40  cmp     rcx, rax
0x1800b9c43  jbe     short loc_1800B9C6F
0x1800b9c45  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800b9c4f  cmp     rcx, rax
0x1800b9c52  jbe     short loc_1800B9C61
0x1800b9c54  lea     rcx, aVectorTooLong; "vector too long"
0x1800b9c5b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800b9c61  lea     rdx, [rsp+118h+var_A8]
0x1800b9c66  lea     rcx, [rbx+10h]
0x1800b9c6a  call    ??$_Reallocate@$0A@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<ulong,ulong>>::_Reallocate<0>(unsigned __int64 &)
0x1800b9c6f  mov     [rbx], rdi
0x1800b9c72  mov     rax, [rsp+118h+var_E0]
0x1800b9c77  mov     eax, [rax+8]
0x1800b9c7a  mov     [rbx+8], eax
0x1800b9c7d  jmp     short loc_1800B9C8A
0x1800b9c7f  lea     rax, [rcx-8]
0x1800b9c83  mov     rdi, [rax]
0x1800b9c86  mov     [rbx+18h], rax
0x1800b9c8a  mov     rax, [rsp+118h+var_D8]
0x1800b9c8f  mov     [rax], rdi
0x1800b9c92  mov     rax, [rsp+118h+var_E0]
0x1800b9c97  mov     r8d, [rax+4]; Size
0x1800b9c9b  xor     edx, edx; Val
0x1800b9c9d  mov     rcx, rdi; void *
0x1800b9ca0  call    memset_0
0x1800b9ca5  mov     rbx, [rsp+118h+var_D0]
0x1800b9caa  mov     edi, [rsp+118h+var_E8]
0x1800b9cae  mov     r8d, edi
0x1800b9cb1  shr     r8, 6
0x1800b9cb5  mov     rax, [r15]
0x1800b9cb8  mov     edx, [rax+10h]
0x1800b9cbb  and     r8, rdx
0x1800b9cbe  mov     rax, [rsp+118h+var_D8]
0x1800b9cc3  mov     r9, [rax]
0x1800b9cc6  and     edi, 3Fh
0x1800b9cc9  mov     edx, 1
0x1800b9cce  mov     cl, dil
0x1800b9cd1  shl     rdx, cl
0x1800b9cd4  mov     rax, [r9+r8*8]
0x1800b9cd8  test    rdx, rax
0x1800b9cdb  jnz     short loc_1800B9CE4
0x1800b9cdd  or      rax, rdx
0x1800b9ce0  mov     [r9+r8*8], rax
0x1800b9ce4  add     rbx, 2
0x1800b9ce8  mov     rax, [rsp+118h+var_B8]
0x1800b9ced  jmp     loc_1800B9AEF
0x1800b9cf2  mov     rdi, [r12+10h]
0x1800b9cf7  cmp     rdi, [r12+18h]
0x1800b9cfc  jz      loc_1800BA01C
0x1800b9d02  mov     rcx, [r13+0F0h]
0x1800b9d09  mov     rax, [rcx]
0x1800b9d0c  mov     rax, [rax+50h]
0x1800b9d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9d15  cmp     [rdi], eax
0x1800b9d17  jz      loc_1800BA013
0x1800b9d1d  lea     r15, [r13+2F8h]
0x1800b9d24  mov     r8, rdi
0x1800b9d27  lea     rdx, [rsp+118h+var_B8]
0x1800b9d2c  mov     rcx, r15
0x1800b9d2f  call    ?find@?$_Tree@V?$_Tmap_traits@IGU?$less@I@std@@V?$allocator@U?$pair@$$CBIG@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIG@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,ushort,std::less<uint>,std::allocator<std::pair<uint const,ushort>>,0>>::find(uint const &)
0x1800b9d34  mov     rbx, [rsp+118h+var_B8]
0x1800b9d39  cmp     rbx, [r15]
0x1800b9d3c  jz      loc_1800BA013
0x1800b9d42  movzx   r8d, word ptr [rbx+20h]
0x1800b9d47  mov     rdx, [r12+120h]
0x1800b9d4f  mov     ecx, [rdx+14h]
0x1800b9d52  mov     eax, r8d
0x1800b9d55  shr     eax, cl
0x1800b9d57  mov     ecx, [r12+128h]
0x1800b9d5f  cmp     eax, ecx
0x1800b9d61  jb      short loc_1800B9DA6
0x1800b9d63  cmp     eax, [r12+12Ch]
0x1800b9d6b  jnb     short loc_1800B9DA6
0x1800b9d6d  sub     eax, ecx
0x1800b9d6f  mov     ecx, eax
0x1800b9d71  mov     rax, [r12+130h]
0x1800b9d79  mov     r9, [rax+rcx*8]
0x1800b9d7d  test    r9, r9
0x1800b9d80  jz      short loc_1800B9DA6
0x1800b9d82  mov     edx, [rdx+10h]
0x1800b9d85  mov     eax, r8d
0x1800b9d88  shr     rax, 6
0x1800b9d8c  and     rdx, rax
0x1800b9d8f  mov     eax, r8d
0x1800b9d92  and     eax, 3Fh
0x1800b9d95  movzx   ecx, al
0x1800b9d98  mov     rax, [r9+rdx*8]
0x1800b9d9c  bt      rax, rcx
0x1800b9da0  jb      loc_1800BA013
0x1800b9da6  test    byte ptr [r12+0Ch], 1
0x1800b9dac  jnz     loc_1800BA013
0x1800b9db2  mov     edx, r8d
0x1800b9db5  lea     rcx, aPidDeletedByOm; "PID deleted by omission: %d"
0x1800b9dbc  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800b9dc1  mov     [rsp+118h+var_90], 0
0x1800b9dcd  mov     [rsp+118h+var_88], 0
0x1800b9dd9  xorps   xmm0, xmm0
0x1800b9ddc  movdqu  xmmword ptr [rsp+118h+var_80], xmm0
0x1800b9de5  mov     eax, [rdi]
0x1800b9de7  mov     [rsp+118h+var_98], eax
0x1800b9dee  mov     rcx, [r12+30h]; this
0x1800b9df3  cmp     rcx, [r12+38h]
0x1800b9df8  jz      short loc_1800B9E0F
0x1800b9dfa  lea     rdx, [rsp+118h+var_98]; struct inverted::PROPERTYVALUE *
0x1800b9e02  call    ??0PROPERTYVALUE@inverted@@QEAA@AEBU01@@Z; inverted::PROPERTYVALUE::PROPERTYVALUE(inverted::PROPERTYVALUE const &)
0x1800b9e07  add     qword ptr [r12+30h], 28h ; '('
0x1800b9e0d  jmp     short loc_1800B9E24
0x1800b9e0f  lea     r8, [rsp+118h+var_98]
0x1800b9e17  mov     rdx, rcx
0x1800b9e1a  lea     rcx, [r12+28h]
0x1800b9e1f  call    ??$_Emplace_reallocate@AEBUPROPERTYVALUE@inverted@@@?$vector@UPROPERTYVALUE@inverted@@V?$allocator@UPROPERTYVALUE@inverted@@@std@@@std@@AEAAPEAUPROPERTYVALUE@inverted@@QEAU23@AEBU23@@Z; std::vector<inverted::PROPERTYVALUE>::_Emplace_reallocate<inverted::PROPERTYVALUE const &>(inverted::PROPERTYVALUE * const,inverted::PROPERTYVALUE const &)
0x1800b9e24  lea     r8, [r12+108h]
0x1800b9e2c  movzx   ebx, word ptr [rbx+20h]
0x1800b9e30  mov     [rsp+118h+var_E8], ebx
0x1800b9e34  mov     rcx, [r8]
0x1800b9e37  mov     ecx, [rcx+14h]
0x1800b9e3a  mov     edx, ebx
0x1800b9e3c  shr     edx, cl
0x1800b9e3e  cmp     edx, [r8+8]
0x1800b9e42  jb      short loc_1800B9E6C
0x1800b9e44  cmp     edx, [r8+0Ch]
0x1800b9e48  jnb     short loc_1800B9E5D
0x1800b9e4a  sub     edx, [r8+8]
0x1800b9e4e  mov     rax, [r8+10h]
0x1800b9e52  lea     rax, [rax+rdx*8]
0x1800b9e56  mov     [rsp+118h+var_E0], rax
0x1800b9e5b  jmp     short loc_1800B9E81
0x1800b9e5d  mov     rcx, r8
0x1800b9e60  call    ?_AddPagesToEnd@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9e65  mov     [rsp+118h+var_E0], rax
0x1800b9e6a  jmp     short loc_1800B9E79
0x1800b9e6c  mov     rcx, r8
0x1800b9e6f  call    ?_AddPagesToStart@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x1800b9e74  mov     [rsp+118h+var_E0], rax
0x1800b9e79  lea     r8, [r12+108h]
0x1800b9e81  cmp     qword ptr [rax], 0
0x1800b9e85  jnz     loc_1800B9FC7
0x1800b9e8b  mov     rbx, [r8]
0x1800b9e8e  mov     [rsp+118h+var_D8], rbx
0x1800b9e93  lea     rcx, [rbx+30h]
0x1800b9e97  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x1800b9e9c  mov     r15, rax
0x1800b9e9f  mov     rax, [rax+18h]
0x1800b9ea3  cmp     [r15+10h], rax
0x1800b9ea7  jnz     loc_1800B9F9B
0x1800b9ead  mov     edx, [r15+8]
0x1800b9eb1  cmp     edx, [rbx+1Ch]
0x1800b9eb4  jnb     short loc_1800B9ED0
0x1800b9eb6  mov     rax, [r15]
0x1800b9eb9  lea     rbx, [rax+rdx*8]
0x1800b9ebd  mov     rax, [rsp+118h+var_D8]
0x1800b9ec2  mov     ecx, [rax+8]
0x1800b9ec5  add     ecx, edx
0x1800b9ec7  mov     [r15+8], ecx
0x1800b9ecb  jmp     loc_1800B9FA6
0x1800b9ed0  mov     edx, [rbx+20h]; Alignment
0x1800b9ed3  mov     ecx, [rbx+1Ch]
0x1800b9ed6  shl     rcx, 3; Size
0x1800b9eda  call    cs:__imp__aligned_malloc
0x1800b9ee0  mov     rbx, rax
0x1800b9ee3  mov     [rsp+118h+var_D0], rax
0x1800b9ee8  mov     rcx, [rsp+118h]; this
0x1800b9ef0  test    rax, rax
0x1800b9ef3  jnz     short loc_1800B9F06
0x1800b9ef5  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800b9efc  mov     edx, 430h; void *
  ... truncated ...
```
