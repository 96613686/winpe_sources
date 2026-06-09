# inverted::CProximityCallback::NextWid(ushort,uint,unsigned __int64,inverted::COccSet *,inverted::COccSet *)

- ea: `0x1802377f0`
- end: `0x180238095`
- name: `?NextWid@CProximityCallback@inverted@@UEAAXGI_KPEAVCOccSet@2@1@Z`
- size: `2213`
- prototype: `void __fastcall(inverted::CProximityCallback *__hidden this, unsigned __int16, unsigned int, unsigned __int64, struct inverted::COccSet *, struct inverted::COccSet *)`
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x18002a3e0`
- `0x18002c970`
- `0x180047e78`
- `0x18004d9d8`
- `0x180050858`
- `0x18008190c`
- `0x1800e8ea0`
- `0x1801183f0`
- `0x18013e868`
- `0x1801470d4`
- `0x180147190`
- `0x180188d90`
- `0x180189cce`
- `0x1801cff14`
- `0x180236250`
- `0x180236774`
- `0x180236888`
- `0x180236ba8`
- `0x180236c60`
- `0x180236cb8`
- `0x180237478`
- `0x1802377f0`
- `0x18023809c`
- `0x1802c0010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1802378ca`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180237e55`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1802378ca`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180237e55`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18023783c`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18023783c`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180237be0`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180237dc2`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180237be0`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180237dc2`

## string_xrefs

- `0x180237bf7`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180237dd9`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall inverted::CProximityCallback::NextWid(
        inverted::CProximityCallback *this,
        unsigned __int16 a2,
        unsigned int a3,
        __int64 a4,
        struct inverted::COccSet *a5)
{
  unsigned int v5; // r13d
  __int64 v7; // r14
  _QWORD *v8; // rbx
  unsigned __int64 CurrentThreadId; // r9
  unsigned __int64 v10; // rdx
  __int64 i; // r12
  unsigned __int64 v12; // rcx
  bool v13; // r8
  unsigned __int64 v14; // rsi
  __int64 v15; // rdx
  unsigned __int64 v16; // r15
  char *v17; // rax
  __int64 v18; // rbx
  char v19; // r13
  unsigned int v20; // ebx
  unsigned int *v21; // rax
  unsigned int *v22; // rcx
  unsigned int v23; // r9d
  __int64 v24; // rcx
  unsigned int *v25; // rax
  unsigned __int64 v26; // r8
  _QWORD *v27; // rdx
  char *v28; // rdx
  __int64 v29; // rcx
  unsigned int v30; // edx
  __int64 *v31; // r15
  __int64 v32; // rax
  unsigned int *v33; // rsi
  __int64 v34; // rdi
  __int64 v35; // rax
  __int64 v36; // r8
  void *v37; // rbx
  void *v38; // rax
  const char *v39; // r9
  _QWORD *v40; // rdx
  unsigned __int64 v41; // rcx
  void **v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r15
  __int64 v46; // rax
  __int64 v47; // rdi
  __int64 v48; // rdi
  unsigned int v49; // edx
  _QWORD *v50; // r13
  __int64 v51; // rax
  unsigned int *v52; // r14
  __int64 v53; // rsi
  __int64 v54; // rax
  __int64 v55; // r8
  void *v56; // rbx
  void *v57; // rax
  const char *v58; // r9
  _QWORD *v59; // rdx
  unsigned __int64 v60; // rdx
  void **v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rdx
  char *v65; // r14
  signed __int64 v66; // rdi
  __int64 v67; // rsi
  __int64 v68; // rsi
  unsigned int v69; // ebx
  double v70; // xmm6_8
  __int16 v71; // di
  char NextMinSequence; // al
  __int64 v73; // rcx
  unsigned __int64 v74; // r8
  int v75; // [rsp+28h] [rbp-E0h]
  __int64 v76; // [rsp+38h] [rbp-D0h] BYREF
  void *v77; // [rsp+40h] [rbp-C8h] BYREF
  char *v78; // [rsp+48h] [rbp-C0h] BYREF
  char *v79; // [rsp+50h] [rbp-B8h]
  char *v80; // [rsp+58h] [rbp-B0h]
  unsigned __int16 v81; // [rsp+60h] [rbp-A8h]
  __int128 v82; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v83; // [rsp+78h] [rbp-90h]
  _QWORD *v84; // [rsp+80h] [rbp-88h] BYREF
  __int64 v85; // [rsp+88h] [rbp-80h]
  unsigned __int64 v86; // [rsp+90h] [rbp-78h] BYREF
  __int128 v87; // [rsp+98h] [rbp-70h] BYREF
  __int64 v88; // [rsp+A8h] [rbp-60h]
  _QWORD v89[7]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD *v90; // [rsp+F0h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  v5 = a3;
  LODWORD(v76) = a3;
  v81 = a2;
  v7 = *((_QWORD *)this + 1);
  v85 = v7;
  v8 = *(_QWORD **)(v7 + 8);
  CurrentThreadId = (unsigned int)Concurrency::details::platform::GetCurrentThreadId(this);
  v10 = CurrentThreadId % v8[1];
  for ( i = *(_QWORD *)(*v8 + 8 * v10); i; i = *(_QWORD *)(i + 88) )
  {
    if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      goto LABEL_6;
  }
  i = TPUtils::combinable<inverted::CProximityCursor::SPerThreadData>::_AddLocalItem(
        v8,
        (unsigned int)CurrentThreadId,
        v10);
LABEL_6:
  std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v78);
  v12 = (__int64)(*(_QWORD *)(v7 + 48) - *(_QWORD *)(v7 + 40)) >> 2;
  v77 = (void *)v12;
  if ( v12 > 0xAAAAAAAAAAAAAAABuLL * ((v80 - v78) >> 3) )
  {
    if ( v12 > 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("vector too long");
    std::vector<inverted::CPhraseOccSet>::_Reallocate<0>(&v78, &v77);
  }
  v87 = 0;
  v88 = 0;
  std::vector<std::vector<unsigned int>>::_Construct_n<>(
    &v87,
    (__int64)(*(_QWORD *)(v7 + 48) - *(_QWORD *)(v7 + 40)) >> 2);
  v13 = 1;
  v14 = 0;
  v15 = *(_QWORD *)(v7 + 40);
  if ( !((*(_QWORD *)(v7 + 48) - v15) >> 2) )
  {
LABEL_47:
    v30 = v5 >> *(_DWORD *)(*(_QWORD *)(i + 8) + 20LL);
    if ( v30 < *(_DWORD *)(i + 16) )
    {
      v32 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(i + 8);
    }
    else
    {
      if ( v30 < *(_DWORD *)(i + 20) )
      {
        v31 = (__int64 *)(*(_QWORD *)(i + 24) + 8LL * (v30 - *(_DWORD *)(i + 16)));
        goto LABEL_53;
      }
      v32 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(i + 8);
    }
    v31 = (__int64 *)v32;
LABEL_53:
    if ( !*v31 )
    {
      v33 = *(unsigned int **)(i + 8);
      v34 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(v33 + 12);
      v35 = *(_QWORD *)(v34 + 24);
      if ( *(_QWORD *)(v34 + 16) == v35 )
      {
        v36 = *(unsigned int *)(v34 + 8);
        if ( (unsigned int)v36 >= v33[7] )
        {
          v38 = _aligned_malloc(8LL * v33[7], v33[8]);
          v37 = v38;
          v84 = v38;
          if ( !v38 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x430,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
              v39);
          v40 = *(_QWORD **)(v34 + 48);
          if ( v40 == *(_QWORD **)(v34 + 56) )
          {
            std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
              v34 + 40,
              v40,
              &v84);
            v37 = v84;
          }
          else
          {
            *v40 = v38;
            *(_QWORD *)(v34 + 48) += 8LL;
          }
          v41 = v33[6] * ((__int64)(*(_QWORD *)(v34 + 48) - *(_QWORD *)(v34 + 40)) >> 3);
          v77 = (void *)v41;
          if ( v41 > (__int64)(*(_QWORD *)(v34 + 32) - *(_QWORD *)(v34 + 16)) >> 3 )
          {
            if ( v41 > 0x1FFFFFFFFFFFFFFFLL )
              goto LABEL_90;
            std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v34 + 16, &v77);
          }
          *(_QWORD *)v34 = v37;
          *(_DWORD *)(v34 + 8) = v33[2];
          v7 = v85;
        }
        else
        {
          v37 = (void *)(*(_QWORD *)v34 + 8 * v36);
          *(_DWORD *)(v34 + 8) = v36 + v33[2];
        }
      }
      else
      {
        v42 = (void **)(v35 - 8);
        v37 = *v42;
        *(_QWORD *)(v34 + 24) = v42;
      }
      *v31 = (__int64)v37;
      memset_0(v37, 0, v33[1]);
      v5 = v76;
    }
    v86 = (unsigned __int64)v5 >> 6;
    v43 = (unsigned int)v86 & *(_DWORD *)(*(_QWORD *)(i + 8) + 16LL);
    v44 = *v31;
    v45 = 1LL << v5;
    v46 = *(_QWORD *)(v44 + 8 * v43);
    if ( (v46 & (1LL << v5)) == 0 )
      *(_QWORD *)(v44 + 8 * v43) = v45 | v46;
    if ( (*(_BYTE *)(v7 + 320) & 4) == 0 )
      goto LABEL_97;
    v47 = v81;
    if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(i + 72) - *(_QWORD *)(i + 64)) >> 3) <= v81 )
      inverted::CPidWids::Reserve((inverted::CPidWids *)(i + 56), (unsigned int)v81 + 1);
    v48 = *(_QWORD *)(i + 64) + 24 * v47;
    v49 = v5 >> *(_DWORD *)(*(_QWORD *)v48 + 20LL);
    if ( v49 < *(_DWORD *)(v48 + 8) )
    {
      v51 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(v48);
    }
    else
    {
      if ( v49 < *(_DWORD *)(v48 + 12) )
      {
        v50 = (_QWORD *)(*(_QWORD *)(v48 + 16) + 8LL * (v49 - *(_DWORD *)(v48 + 8)));
        goto LABEL_79;
      }
      v51 = _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(v48);
    }
    v50 = (_QWORD *)v51;
LABEL_79:
    v84 = v50;
    if ( *v50 )
      goto LABEL_95;
    v52 = *(unsigned int **)v48;
    v53 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(*(_QWORD *)v48 + 48LL);
    v54 = *(_QWORD *)(v53 + 24);
    if ( *(_QWORD *)(v53 + 16) != v54 )
    {
      v61 = (void **)(v54 - 8);
      v56 = *v61;
      *(_QWORD *)(v53 + 24) = v61;
      goto LABEL_94;
    }
    v55 = *(unsigned int *)(v53 + 8);
    if ( (unsigned int)v55 < v52[7] )
    {
      v56 = (void *)(*(_QWORD *)v53 + 8 * v55);
      *(_DWORD *)(v53 + 8) = v55 + v52[2];
LABEL_94:
      *v50 = v56;
      memset_0(v56, 0, v52[1]);
      v7 = v85;
LABEL_95:
      v62 = (unsigned int)v86 & *(_DWORD *)(*(_QWORD *)v48 + 16LL);
      v63 = *v50;
      v64 = *(_QWORD *)(*v50 + 8 * v62);
      v5 = v76;
      if ( (v45 & v64) == 0 )
        *(_QWORD *)(v63 + 8 * v62) = v64 | v45;
LABEL_97:
      if ( (*(_BYTE *)(v7 + 320) & 3) != 0 )
      {
        v65 = v78;
        v66 = 0xAAAAAAAAAAAAAAABuLL * ((v79 - v78) >> 3);
        v67 = v66 >> 1;
        if ( v66 >> 1 > 0 )
        {
          do
          {
            --v67;
            v82 = *(_OWORD *)&v65[24 * v67];
            v83 = *(_QWORD *)&v65[24 * v67 + 16];
            LOBYTE(v75) = 0;
            std::_Pop_heap_hole_by_index<inverted::CPhraseOccSet *,inverted::CPhraseOccSet,std::less<void>>(
              v65,
              v67,
              v66,
              &v82,
              v75);
          }
          while ( v67 > 0 );
          v5 = v76;
        }
        std::pop_heap<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<inverted::CPhraseOccSet>>>>(v78, v79);
        v82 = *(_OWORD *)(v79 - 24);
        v83 = *((_QWORD *)v79 - 1);
        v79 -= 24;
        v68 = v85;
        v69 = *(_DWORD *)(v85 + 216);
        v70 = 0.0;
        v71 = 0;
        do
        {
          LODWORD(v76) = 0;
          NextMinSequence = inverted::CProximityCursor::GetNextMinSequence(v68, &v78, &v82, &v76);
          v73 = (unsigned int)v76;
          if ( v69 >= (unsigned int)v76 )
            v69 = v76;
          if ( (unsigned int)v76 >= 0x31 )
            v73 = 49;
          v70 = v70 + *(double *)&qword_1803184B0[v73];
          ++v71;
        }
        while ( NextMinSequence );
        LODWORD(v82) = v5;
        WORD2(v82) = v71;
        *((double *)&v82 + 1) = v70;
        LODWORD(v83) = v69;
        std::lower_bound<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<inverted::CProximityCursor::SPerWidData>>>,inverted::CProximityCursor::SPerWidData>(
          &v86,
          *(_QWORD *)(i + 32),
          *(_QWORD *)(i + 40),
          &v82);
        v74 = v86;
        if ( v86 == *(_QWORD *)(i + 40) || *(_DWORD *)v86 != v5 )
        {
          std::vector<inverted::CProximityCursor::SPerWidData>::emplace<inverted::CProximityCursor::SPerWidData const &>(
            i + 32,
            &v86,
            v86,
            &v82);
        }
        else
        {
          *(_WORD *)(v86 + 4) += v71;
          *(double *)(v74 + 8) = v70 + *(double *)(v74 + 8);
          if ( *(_DWORD *)(v74 + 16) < v69 )
            v69 = *(_DWORD *)(v74 + 16);
          *(_DWORD *)(v74 + 16) = v69;
        }
      }
      goto LABEL_113;
    }
    v57 = _aligned_malloc(8LL * v52[7], v52[8]);
    v56 = v57;
    v77 = v57;
    if ( !v57 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x430,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
        v58);
    v59 = *(_QWORD **)(v53 + 48);
    if ( v59 == *(_QWORD **)(v53 + 56) )
    {
      std::vector<std::pair<unsigned long,unsigned long>>::_Emplace_reallocate<std::pair<unsigned long,unsigned long>>(
        v53 + 40,
        v59,
        &v77);
      v56 = v77;
    }
    else
    {
      *v59 = v57;
      *(_QWORD *)(v53 + 48) += 8LL;
    }
    v60 = v52[6] * ((__int64)(*(_QWORD *)(v53 + 48) - *(_QWORD *)(v53 + 40)) >> 3);
    v77 = (void *)v60;
    if ( v60 > (__int64)(*(_QWORD *)(v53 + 32) - *(_QWORD *)(v53 + 16)) >> 3 )
    {
      if ( v60 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_90:
        std::_Xlength_error("vector too long");
      std::vector<std::pair<unsigned long,unsigned long>>::_Reallocate<0>(v53 + 16, &v77);
    }
    *(_QWORD *)v53 = v56;
    *(_DWORD *)(v53 + 8) = v52[2];
    v50 = v84;
    goto LABEL_94;
  }
  do
  {
    if ( !v13 )
      goto LABEL_113;
    v16 = *(int *)(v15 + 4 * v14);
    if ( (unsigned int)v16 >= 2 )
    {
      v89[0] = &std::_Func_impl_no_alloc<_lambda_09a9708a9991144632614db2e6876d3c_,bool,unsigned int>::`vftable';
      v89[1] = &v87;
      v89[2] = v14;
      v90 = v89;
      v19 = 1;
      v20 = 0;
      do
      {
        v21 = *(unsigned int **)a5;
        if ( *(_QWORD *)a5 >= *((_QWORD *)a5 + 1) )
        {
          v22 = *(unsigned int **)a5;
        }
        else
        {
          do
          {
            v22 = v21;
            if ( *v21 >= v20 )
              break;
            *(_QWORD *)a5 = ++v21;
            v22 = v21;
          }
          while ( (unsigned __int64)v21 < *((_QWORD *)a5 + 1) );
        }
        if ( (unsigned __int64)v22 >= *((_QWORD *)a5 + 1) )
          break;
        v23 = *v22;
        v24 = 1;
        while ( 1 )
        {
          ++v23;
          v25 = (unsigned int *)*((_QWORD *)a5 + 2 * v24);
          v26 = *((_QWORD *)a5 + 2 * v24 + 1);
          while ( (unsigned __int64)v25 < v26 && *v25 < v23 )
            *((_QWORD *)a5 + 2 * v24) = ++v25;
          if ( (unsigned __int64)v25 >= v26 )
            break;
          if ( *v25 != v23 )
          {
            v20 = *v25 - v24;
            goto LABEL_35;
          }
          if ( ++v24 >= v16 )
            goto LABEL_35;
        }
        v19 = 0;
LABEL_35:
        if ( v24 == v16 )
        {
          v20 = v23 + 1;
          if ( !(unsigned __int8)std::_Func_class<bool,unsigned int>::operator()(v89, v23 + 1 - (unsigned int)v16) )
            break;
        }
      }
      while ( v19 );
      if ( v90 )
      {
        v27 = v89;
        LOBYTE(v27) = v90 != v89;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v90 + 32LL))(v90, v27);
      }
      v18 = 24 * v14;
      *(_QWORD *)&v82 = *(_QWORD *)(24 * v14 + v87);
      *((_QWORD *)&v82 + 1) = v82 + 4 * ((__int64)(*(_QWORD *)(24 * v14 + v87 + 8) - v82) >> 2);
      LODWORD(v83) = v16;
      v28 = v79;
      if ( v79 == v80 )
      {
        std::vector<inverted::CPhraseOccSet>::_Emplace_reallocate<inverted::CPhraseOccSet const &>(&v78, v79, &v82);
      }
      else
      {
        *(_OWORD *)v79 = v82;
        *((_QWORD *)v28 + 2) = v83;
        v79 += 24;
      }
      a5 = (struct inverted::COccSet *)((char *)a5 + 16 * v16);
      v7 = v85;
    }
    else
    {
      v82 = *(_OWORD *)a5;
      LODWORD(v83) = 1;
      v17 = v79;
      if ( v79 == v80 )
      {
        std::vector<inverted::CPhraseOccSet>::_Emplace_reallocate<inverted::CPhraseOccSet const &>(&v78, v79, &v82);
      }
      else
      {
        *(_OWORD *)v79 = v82;
        *((_QWORD *)v17 + 2) = v83;
        v79 += 24;
      }
      a5 = (struct inverted::COccSet *)((char *)a5 + 16);
      v18 = 24 * v14;
    }
    v29 = (__int64)(*(_QWORD *)&v78[v18 + 8] - *(_QWORD *)&v78[v18]) >> 2;
    ++v14;
    v15 = *(_QWORD *)(v7 + 40);
    v13 = v29 > 0;
  }
  while ( v14 < (*(_QWORD *)(v7 + 48) - v15) >> 2 );
  if ( v29 > 0 )
  {
    v5 = v76;
    goto LABEL_47;
  }
LABEL_113:
  std::vector<std::vector<unsigned int>>::_Tidy(&v87);
  if ( v78 )
    std::_Deallocate<16>(v78, 8 * ((v80 - v78) >> 3));
}

```

## disassembly

```asm
0x1802377f0  mov     rax, rsp
0x1802377f3  mov     [rax+20h], rbx
0x1802377f7  push    rbp
0x1802377f8  push    rsi
0x1802377f9  push    rdi
0x1802377fa  push    r12
0x1802377fc  push    r13
0x1802377fe  push    r14
0x180237800  push    r15
0x180237802  lea     rbp, [rax-48h]
0x180237806  sub     rsp, 110h
0x18023780d  movaps  xmmword ptr [rax-48h], xmm6
0x180237811  mov     rax, cs:__security_cookie
0x180237818  xor     rax, rsp
0x18023781b  mov     [rbp+40h+var_50], rax
0x18023781f  mov     r13d, r8d
0x180237822  mov     dword ptr [rsp+140h+var_110], r8d
0x180237827  mov     word ptr [rsp+140h+var_E8], dx
0x18023782c  mov     rdi, [rbp+40h+arg_20]
0x180237830  mov     r14, [rcx+8]
0x180237834  mov     [rbp+40h+var_C0], r14
0x180237838  mov     rbx, [r14+8]
0x18023783c  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180237842  mov     r9d, eax
0x180237845  mov     eax, eax
0x180237847  xor     edx, edx
0x180237849  div     qword ptr [rbx+8]
0x18023784d  mov     rcx, [rbx]
0x180237850  mov     r12, [rcx+rdx*8]
0x180237854  test    r12, r12
0x180237857  jz      short loc_180237866
0x180237859  cmp     [r12], r9d
0x18023785d  jz      short loc_180237877
0x18023785f  mov     r12, [r12+58h]
0x180237864  jmp     short loc_180237854
0x180237866  mov     r8, rdx
0x180237869  mov     edx, r9d
0x18023786c  mov     rcx, rbx
0x18023786f  call    ?_AddLocalItem@?$combinable@USPerThreadData@CProximityCursor@inverted@@@TPUtils@@AEAAPEAU_Node@12@K_K@Z; TPUtils::combinable<inverted::CProximityCursor::SPerThreadData>::_AddLocalItem(ulong,unsigned __int64)
0x180237874  mov     r12, rax
0x180237877  lea     rcx, [rsp+140h+var_100]; void *
0x18023787c  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x180237881  nop
0x180237882  mov     rcx, [r14+30h]
0x180237886  sub     rcx, [r14+28h]
0x18023788a  sar     rcx, 2
0x18023788e  mov     [rsp+140h+var_108], rcx
0x180237893  mov     rax, [rsp+140h+var_F0]
0x180237898  sub     rax, [rsp+140h+var_100]
0x18023789d  sar     rax, 3
0x1802378a1  mov     rbx, 0AAAAAAAAAAAAAAABh
0x1802378ab  imul    rax, rbx
0x1802378af  cmp     rcx, rax
0x1802378b2  jbe     short loc_1802378E0
0x1802378b4  mov     rax, 0AAAAAAAAAAAAAAAh
0x1802378be  cmp     rcx, rax
0x1802378c1  jbe     short loc_1802378D1
0x1802378c3  lea     rcx, aVectorTooLong; "vector too long"
0x1802378ca  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1802378d1  lea     rdx, [rsp+140h+var_108]
0x1802378d6  lea     rcx, [rsp+140h+var_100]
0x1802378db  call    ??$_Reallocate@$0A@@?$vector@VCPhraseOccSet@inverted@@V?$allocator@VCPhraseOccSet@inverted@@@std@@@std@@AEAAXAEA_K@Z; std::vector<inverted::CPhraseOccSet>::_Reallocate<0>(unsigned __int64 &)
0x1802378e0  xorps   xmm0, xmm0
0x1802378e3  movdqu  [rbp+40h+var_B0], xmm0
0x1802378e8  mov     [rbp+40h+var_A0], 0
0x1802378f0  mov     rdx, [r14+30h]
0x1802378f4  sub     rdx, [r14+28h]
0x1802378f8  sar     rdx, 2
0x1802378fc  lea     rcx, [rbp+40h+var_B0]
0x180237900  call    ??$_Construct_n@$$V@?$vector@V?$vector@IV?$allocator@I@std@@@std@@V?$allocator@V?$vector@IV?$allocator@I@std@@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::vector<uint>>::_Construct_n<>(unsigned __int64)
0x180237905  nop
0x180237906  mov     r10d, 1
0x18023790c  mov     r8b, r10b
0x18023790f  xor     esi, esi
0x180237911  mov     rdx, [r14+28h]
0x180237915  mov     rax, [r14+30h]
0x180237919  sub     rax, rdx
0x18023791c  sar     rax, 2
0x180237920  test    rax, rax
0x180237923  jz      loc_180237B46
0x180237929  test    r8b, r8b
0x18023792c  jz      loc_18023802E
0x180237932  movsxd  r15, dword ptr [rdx+rsi*4]
0x180237936  cmp     r15d, 2
0x18023793a  jnb     short loc_1802379A4
0x18023793c  mov     rax, [rdi]
0x18023793f  mov     qword ptr [rsp+140h+var_E8+8], rax
0x180237944  mov     rax, [rdi+8]
0x180237948  mov     [rsp+140h+var_D8], rax
0x18023794d  mov     dword ptr [rsp+140h+var_D0], r10d
0x180237952  mov     rax, [rsp+140h+var_F8]
0x180237957  cmp     rax, [rsp+140h+var_F0]
0x18023795c  jz      short loc_180237979
0x18023795e  movups  xmm0, [rsp+140h+var_E8+8]
0x180237963  movups  xmmword ptr [rax], xmm0
0x180237966  movsd   xmm1, [rsp+140h+var_D0]
0x18023796c  movsd   qword ptr [rax+10h], xmm1
0x180237971  add     [rsp+140h+var_F8], 18h
0x180237977  jmp     short loc_180237993
0x180237979  lea     r8, [rsp+140h+var_E8+8]
0x18023797e  mov     rdx, [rsp+140h+var_F8]
0x180237983  lea     rcx, [rsp+140h+var_100]
0x180237988  call    ??$_Emplace_reallocate@AEBVCPhraseOccSet@inverted@@@?$vector@VCPhraseOccSet@inverted@@V?$allocator@VCPhraseOccSet@inverted@@@std@@@std@@AEAAPEAVCPhraseOccSet@inverted@@QEAV23@AEBV23@@Z; std::vector<inverted::CPhraseOccSet>::_Emplace_reallocate<inverted::CPhraseOccSet const &>(inverted::CPhraseOccSet * const,inverted::CPhraseOccSet const &)
0x18023798d  mov     r10d, 1
0x180237993  add     rdi, 10h
0x180237997  lea     rbx, [rsi+rsi*2]
0x18023799b  shl     rbx, 3
0x18023799f  jmp     loc_180237B04
0x1802379a4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_09a9708a9991144632614db2e6876d3c_@@_NI@std@@6B@; const std::_Func_impl_no_alloc<_lambda_09a9708a9991144632614db2e6876d3c_,bool,uint>::`vftable'
0x1802379ab  mov     [rbp+40h+var_90], rax
0x1802379af  lea     rax, [rbp+40h+var_B0]
0x1802379b3  mov     [rbp+40h+var_88], rax
0x1802379b7  mov     [rbp+40h+var_80], rsi
0x1802379bb  lea     rax, [rbp+40h+var_90]
0x1802379bf  mov     [rbp+40h+var_58], rax
0x1802379c3  mov     r14, r15
0x1802379c6  mov     r13b, r10b
0x1802379c9  xor     ebx, ebx
0x1802379cb  mov     rax, [rdi]
0x1802379ce  cmp     rax, [rdi+8]
0x1802379d2  jnb     short loc_1802379ED
0x1802379d4  mov     rcx, rax
0x1802379d7  cmp     [rax], ebx
0x1802379d9  jnb     short loc_1802379F0
0x1802379db  add     rax, 4
0x1802379df  mov     [rdi], rax
0x1802379e2  mov     rcx, rax
0x1802379e5  cmp     rax, [rdi+8]
0x1802379e9  jb      short loc_1802379D4
0x1802379eb  jmp     short loc_1802379F0
0x1802379ed  mov     rcx, rax
0x1802379f0  cmp     rcx, [rdi+8]
0x1802379f4  jnb     short loc_180237A6B
0x1802379f6  mov     r9d, [rcx]
0x1802379f9  mov     rcx, r10
0x1802379fc  mov     rdx, rcx
0x1802379ff  add     rdx, rdx
0x180237a02  add     r9d, r10d
0x180237a05  mov     rax, [rdi+rdx*8]
0x180237a09  mov     r8, [rdi+rdx*8+8]
0x180237a0e  jmp     short loc_180237A1D
0x180237a10  cmp     [rax], r9d
0x180237a13  jnb     short loc_180237A22
0x180237a15  add     rax, 4
0x180237a19  mov     [rdi+rdx*8], rax
0x180237a1d  cmp     rax, r8
0x180237a20  jb      short loc_180237A10
0x180237a22  cmp     rax, r8
0x180237a25  jnb     short loc_180237A3E
0x180237a27  mov     edx, [rax]
0x180237a29  cmp     edx, r9d
0x180237a2c  jnz     short loc_180237A38
0x180237a2e  add     rcx, r10
0x180237a31  cmp     rcx, r14
0x180237a34  jb      short loc_1802379FC
0x180237a36  jmp     short loc_180237A41
0x180237a38  mov     ebx, edx
0x180237a3a  sub     ebx, ecx
0x180237a3c  jmp     short loc_180237A41
0x180237a3e  xor     r13b, r13b
0x180237a41  cmp     rcx, r14
0x180237a44  jnz     short loc_180237A62
0x180237a46  lea     ebx, [r9+1]
0x180237a4a  mov     edx, ebx
0x180237a4c  sub     edx, r15d
0x180237a4f  lea     rcx, [rbp+40h+var_90]
0x180237a53  call    ??R?$_Func_class@_NI@std@@QEBA_NI@Z; std::_Func_class<bool,uint>::operator()(uint)
0x180237a58  test    al, al
0x180237a5a  jz      short loc_180237A6B
0x180237a5c  mov     r10d, 1
0x180237a62  test    r13b, r13b
0x180237a65  jnz     loc_1802379CB
0x180237a6b  mov     rcx, [rbp+40h+var_58]
0x180237a6f  test    rcx, rcx
0x180237a72  jz      short loc_180237A8A
0x180237a74  mov     rax, [rcx]
0x180237a77  lea     rdx, [rbp+40h+var_90]
0x180237a7b  cmp     rcx, rdx
0x180237a7e  setnz   dl
0x180237a81  mov     rax, [rax+20h]
0x180237a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180237a8a  lea     rax, [rsi+rsi*2]
0x180237a8e  lea     rbx, ds:0[rax*8]
0x180237a96  mov     rax, qword ptr [rbp+40h+var_B0]
0x180237a9a  mov     rdx, [rbx+rax]
0x180237a9e  mov     qword ptr [rsp+140h+var_E8+8], rdx
0x180237aa3  mov     rcx, [rbx+rax+8]
0x180237aa8  sub     rcx, rdx
0x180237aab  sar     rcx, 2
0x180237aaf  lea     rax, [rdx+rcx*4]
0x180237ab3  mov     [rsp+140h+var_D8], rax
0x180237ab8  mov     dword ptr [rsp+140h+var_D0], r15d
0x180237abd  mov     rdx, [rsp+140h+var_F8]
0x180237ac2  cmp     rdx, [rsp+140h+var_F0]
0x180237ac7  jz      short loc_180237AE4
0x180237ac9  movups  xmm0, [rsp+140h+var_E8+8]
0x180237ace  movups  xmmword ptr [rdx], xmm0
0x180237ad1  movsd   xmm1, [rsp+140h+var_D0]
0x180237ad7  movsd   qword ptr [rdx+10h], xmm1
0x180237adc  add     [rsp+140h+var_F8], 18h
0x180237ae2  jmp     short loc_180237AF3
0x180237ae4  lea     r8, [rsp+140h+var_E8+8]
0x180237ae9  lea     rcx, [rsp+140h+var_100]
0x180237aee  call    ??$_Emplace_reallocate@AEBVCPhraseOccSet@inverted@@@?$vector@VCPhraseOccSet@inverted@@V?$allocator@VCPhraseOccSet@inverted@@@std@@@std@@AEAAPEAVCPhraseOccSet@inverted@@QEAV23@AEBV23@@Z; std::vector<inverted::CPhraseOccSet>::_Emplace_reallocate<inverted::CPhraseOccSet const &>(inverted::CPhraseOccSet * const,inverted::CPhraseOccSet const &)
0x180237af3  shl     r14, 4
0x180237af7  add     rdi, r14
0x180237afa  mov     r14, [rbp+40h+var_C0]
0x180237afe  mov     r10d, 1
0x180237b04  mov     rax, [rsp+140h+var_100]
0x180237b09  mov     rcx, [rbx+rax+8]
0x180237b0e  sub     rcx, [rbx+rax]
0x180237b12  sar     rcx, 2
0x180237b16  add     rsi, r10
0x180237b19  mov     rdx, [r14+28h]
0x180237b1d  test    rcx, rcx
0x180237b20  setnle  r8b
0x180237b24  mov     rax, [r14+30h]
0x180237b28  sub     rax, rdx
0x180237b2b  sar     rax, 2
0x180237b2f  cmp     rsi, rax
0x180237b32  jb      loc_180237929
0x180237b38  test    rcx, rcx
0x180237b3b  jle     loc_18023802E
0x180237b41  mov     r13d, dword ptr [rsp+140h+var_110]
0x180237b46  mov     rcx, [r12+8]
0x180237b4b  mov     ecx, [rcx+14h]
0x180237b4e  mov     edx, r13d
0x180237b51  shr     edx, cl
0x180237b53  cmp     edx, [r12+10h]
0x180237b58  jb      short loc_180237B7D
0x180237b5a  cmp     edx, [r12+14h]
0x180237b5f  jnb     short loc_180237B71
0x180237b61  sub     edx, [r12+10h]
0x180237b66  mov     rax, [r12+18h]
0x180237b6b  lea     r15, [rax+rdx*8]
0x180237b6f  jmp     short loc_180237B8A
0x180237b71  lea     rcx, [r12+8]
0x180237b76  call    ?_AddPagesToEnd@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x180237b7b  jmp     short loc_180237B87
0x180237b7d  lea     rcx, [r12+8]
0x180237b82  call    ?_AddPagesToStart@?$_sparse_bit@U?$dynamic_sparse_bit@_K@@@@SAPEAPEA_KAEAU?$dynamic_sparse_bit@_K@@K@Z; _sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart(dynamic_sparse_bit<unsigned __int64> &,ulong)
0x180237b87  mov     r15, rax
0x180237b8a  cmp     qword ptr [r15], 0
0x180237b8e  jnz     loc_180237CA9
0x180237b94  mov     rsi, [r12+8]
0x180237b99  lea     rcx, [rsi+30h]
0x180237b9d  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x180237ba2  mov     rdi, rax
0x180237ba5  lea     r13, [rax+10h]
0x180237ba9  mov     rax, [r13+8]
0x180237bad  cmp     [r13+0], rax
0x180237bb1  jnz     loc_180237C88
0x180237bb7  mov     r8d, [rdi+8]
0x180237bbb  cmp     r8d, [rsi+1Ch]
0x180237bbf  jnb     short loc_180237BD6
0x180237bc1  mov     rcx, [rdi]
0x180237bc4  lea     rbx, [rcx+r8*8]
0x180237bc8  mov     ecx, [rsi+8]
0x180237bcb  add     ecx, r8d
0x180237bce  mov     [rdi+8], ecx
0x180237bd1  jmp     loc_180237C93
0x180237bd6  mov     edx, [rsi+20h]; Alignment
0x180237bd9  mov     ecx, [rsi+1Ch]
0x180237bdc  shl     rcx, 3; Size
0x180237be0  call    cs:__imp__aligned_malloc
0x180237be6  mov     rbx, rax
0x180237be9  mov     [rsp+140h+var_C8], rax
0x180237bee  mov     rcx, [rbp+48h]; this
0x180237bf2  test    rax, rax
0x180237bf5  jnz     short loc_180237C09
0x180237bf7  lea     r8, aOnecoreuapBase_203; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180237bfe  mov     edx, 430h; void *
0x180237c03  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180237c09  mov     rdx, [rdi+30h]
0x180237c0d  cmp     rdx, [rdi+38h]
0x180237c11  jz      short loc_180237C1D
0x180237c13  mov     [rdx], rax
0x180237c16  add     qword ptr [rdi+30h], 8
0x180237c1b  jmp     short loc_180237C30
0x180237c1d  lea     r8, [rsp+140h+var_C8]
0x180237c22  lea     rcx, [rdi+28h]
0x180237c26  call    ??$_Emplace_reallocate@U?$pair@KK@std@@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAPEAU?$pair@KK@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<ulong,ulong>>::_Emplace_reallocate<std::pair<ulong,ulong>>(std::pair<ulong,ulong> * const,std::pair<ulong,ulong> &&)
0x180237c2b  mov     rbx, [rsp+140h+var_C8]
0x180237c30  mov     rcx, [rdi+30h]
0x180237c34  sub     rcx, [rdi+28h]
0x180237c38  sar     rcx, 3
0x180237c3c  mov     eax, [rsi+18h]
0x180237c3f  imul    rcx, rax
0x180237c43  mov     [rsp+140h+var_108], rcx
0x180237c48  mov     rax, [r13+10h]
0x180237c4c  sub     rax, [r13+0]
0x180237c50  sar     rax, 3
0x180237c54  cmp     rcx, rax
0x180237c57  jbe     short loc_180237C79
0x180237c59  mov     rax, 1FFFFFFFFFFFFFFFh
0x180237c63  cmp     rcx, rax
0x180237c66  ja      loc_180237E4E
0x180237c6c  lea     rdx, [rsp+140h+var_108]
0x180237c71  mov     rcx, r13
0x180237c74  call    ??$_Reallocate@$0A@@?$vector@U?$pair@KK@std@@V?$allocator@U?$pair@KK@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<ulong,ulong>>::_Reallocate<0>(unsigned __int64 &)
  ... truncated ...
```
