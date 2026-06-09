# Windows::UI::Composition::EffectInstance::CalcInversedWorldInputBoundsFromVisibleWorldOutputBounds(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const *,uint,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> *,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> *)

- ea: `0x18000efc0`
- end: `0x18000fb83`
- name: `?CalcInversedWorldInputBoundsFromVisibleWorldOutputBounds@EffectInstance@Composition@UI@Windows@@UEBAJAEBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@0PEBV5@IPEAV5@2@Z`
- size: `3011`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64, unsigned __int64, unsigned int, _OWORD *, _OWORD *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009ee8`
- `0x18000e690`
- `0x18000efc0`
- `0x18000fb90`
- `0x18000fba4`
- `0x18000fdf0`
- `0x18000fe20`
- `0x18000fe60`
- `0x18001f204`
- `0x180021060`
- `0x180021084`
- `0x1800257b8`
- `0x18002b8b0`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000f2be`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000f464`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000f491`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000f2be`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000f464`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000f491`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f058`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f0e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f175`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f201`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f058`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f0e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f175`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f201`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f04a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f0d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f167`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f1f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f539`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f54e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f563`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f579`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f04a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f0d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f167`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f1f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f539`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f54e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f563`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f579`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f55c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f572`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f589`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f55c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f572`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f589`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::EffectInstance::CalcInversedWorldInputBoundsFromVisibleWorldOutputBounds(
        __int64 a1,
        _OWORD *a2,
        __int64 a3,
        unsigned __int64 a4,
        unsigned int a5,
        _OWORD *a6,
        _OWORD *a7)
{
  __int64 v7; // r13
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rdi
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  char *v12; // rax
  void *v13; // r15
  unsigned __int64 v14; // rbx
  char *i; // rsi
  __int64 v16; // rsi
  SIZE_T v17; // rbx
  HANDLE v18; // rax
  char *v19; // rax
  void *v20; // r15
  char *v21; // rbx
  SIZE_T v22; // rbx
  HANDLE v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // r15
  unsigned __int64 v26; // rbx
  _QWORD *j; // rsi
  SIZE_T v28; // rbx
  HANDLE v29; // rax
  __m128 *v30; // rax
  __m128 *v31; // r12
  __m128 *v32; // rbx
  unsigned int k; // ecx
  __int64 v34; // rax
  unsigned int v35; // r9d
  unsigned int v36; // edi
  __int64 v37; // rcx
  unsigned __int64 v38; // rsi
  int v39; // ebx
  void **v40; // rcx
  unsigned __int64 v41; // rdx
  unsigned int v42; // ecx
  __int64 v43; // rax
  __int64 v44; // r10
  int v45; // eax
  __int64 v46; // rdi
  __int64 v47; // rcx
  char *v48; // rdx
  __int64 v49; // r8
  int v50; // r9d
  char *v51; // r8
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  _OWORD *v57; // rax
  void **v58; // rcx
  unsigned __int64 v59; // rdx
  HANDLE v60; // rax
  HANDLE v61; // rax
  HANDLE v62; // rax
  HANDLE v63; // rax
  int v65; // r9d
  __int64 v66; // rax
  __int64 v67; // r9
  unsigned __int64 v68; // r10
  __int64 *v69; // r13
  unsigned int v70; // r15d
  unsigned int m; // ebx
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // r8
  _OWORD *v77; // rax
  __int64 v78; // r8
  int v79; // ecx
  _OWORD *v80; // r8
  int v81; // ecx
  unsigned __int64 v82; // r9
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // rdi
  unsigned int v86; // ebx
  __m128 v87; // xmm3
  unsigned int v88; // r11d
  float v89; // xmm4_4
  unsigned __int32 v90; // xmm6_4
  unsigned __int32 v91; // xmm5_4
  __m128 v92; // xmm7
  __int64 v93; // r8
  int v94; // ecx
  __int64 v95; // rax
  int v96; // r8d
  float v97; // xmm1_4
  float v98; // xmm2_4
  float *v99; // rdx
  BOOL v100; // ecx
  int v101; // ecx
  unsigned __int64 v102; // r9
  __int64 v103; // rcx
  _QWORD *v104; // rcx
  __m128 *v105; // rcx
  int v106; // r11d
  __m128 v107; // xmm3
  __m128 v108; // xmm3
  float v109; // xmm0_4
  __m128 v110; // xmm3
  __m128 v111; // xmm3
  __m128 v112; // xmm3
  __int64 v113; // rcx
  float v114; // xmm0_4
  __m128 v115; // xmm3
  float v116; // xmm0_4
  __m128 v117; // xmm3
  void **pExceptionObject; // [rsp+48h] [rbp-C0h] BYREF
  __int128 pExceptionObject_8; // [rsp+50h] [rbp-B8h]
  unsigned __int64 v120; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v121; // [rsp+68h] [rbp-A0h]
  LPVOID v122; // [rsp+70h] [rbp-98h]
  _QWORD *v123; // [rsp+78h] [rbp-90h]
  unsigned __int64 v124; // [rsp+80h] [rbp-88h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-80h]
  _OWORD *v126; // [rsp+90h] [rbp-78h]
  _OWORD *v127; // [rsp+98h] [rbp-70h]
  __int128 v128; // [rsp+A0h] [rbp-68h] BYREF
  void *v129; // [rsp+B0h] [rbp-58h]
  void *v130; // [rsp+B8h] [rbp-50h]
  _QWORD *v131; // [rsp+C0h] [rbp-48h]
  __m128 *v132; // [rsp+C8h] [rbp-40h]
  void *v133[2]; // [rsp+D0h] [rbp-38h] BYREF
  _OWORD *v134; // [rsp+E0h] [rbp-28h] BYREF

  v124 = a4;
  v134 = a2;
  v7 = a1;
  v121 = a1;
  v126 = a6;
  v127 = a7;
  v8 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 80LL))(*(_QWORD *)(a1 + 16) + 16LL);
  v9 = v8;
  v133[0] = (void *)v8;
  v10 = 16 * v8;
  if ( !is_mul_ok(v8, 0x10u) )
    v10 = -1;
  ProcessHeap = GetProcessHeap();
  v12 = (char *)HeapAlloc(ProcessHeap, 0, v10);
  v13 = v12;
  v122 = v12;
  if ( !v12 )
  {
    *((_QWORD *)&pExceptionObject_8 + 1) = 0;
    *(_QWORD *)&pExceptionObject_8 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  lpMem = v12;
  v14 = v8;
  for ( i = v12; v14; --v14 )
  {
    TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(i);
    i += 16;
  }
  v129 = v13;
  v16 = a5;
  v133[0] = (void *)a5;
  v17 = 16LL * a5;
  if ( !is_mul_ok(a5, 0x10u) )
    v17 = -1;
  v18 = GetProcessHeap();
  v19 = (char *)HeapAlloc(v18, 0, v17);
  v20 = v19;
  lpMem = v19;
  if ( !v19 )
  {
    *((_QWORD *)&pExceptionObject_8 + 1) = 0;
    *(_QWORD *)&pExceptionObject_8 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v123 = v19;
  v21 = v19;
  if ( a5 )
  {
    do
    {
      TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(v21);
      v21 += 16;
      --v16;
    }
    while ( v16 );
  }
  v130 = v20;
  v128 = 0;
  v133[0] = (void *)v8;
  v22 = 16 * v8;
  if ( !is_mul_ok(v8, 0x10u) )
    v22 = -1;
  v23 = GetProcessHeap();
  v24 = HeapAlloc(v23, 0, v22);
  v25 = v24;
  v123 = v24;
  if ( !v24 )
  {
    *((_QWORD *)&pExceptionObject_8 + 1) = 0;
    *(_QWORD *)&pExceptionObject_8 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v120 = (unsigned __int64)v24;
  v26 = v8;
  for ( j = v24; v26; --v26 )
  {
    TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(j);
    j += 2;
  }
  v131 = v25;
  v133[0] = (void *)v8;
  v28 = 16 * v8;
  if ( !is_mul_ok(v8, 0x10u) )
    v28 = -1;
  v29 = GetProcessHeap();
  v30 = (__m128 *)HeapAlloc(v29, 0, v28);
  v31 = v30;
  if ( !v30 )
  {
    *((_QWORD *)&pExceptionObject_8 + 1) = 0;
    *(_QWORD *)&pExceptionObject_8 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v120 = (unsigned __int64)v30;
  v32 = v30;
  if ( (_DWORD)v8 )
  {
    do
    {
      TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(v32++);
      --v9;
    }
    while ( v9 );
  }
  v132 = v31;
  for ( k = 0; k < (unsigned int)v8; ++k )
  {
    v34 = 2LL * k;
    v25[v34] = 0;
    v25[v34 + 1] = 0;
  }
  LODWORD(v120) = 0;
  std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(&pExceptionObject);
  v36 = v35;
LABEL_28:
  if ( v36 >= (unsigned int)v8 )
  {
    LODWORD(v38) = -2147024809;
    v39 = v120;
    goto LABEL_32;
  }
  v37 = *(_QWORD *)(v7 + 16);
  if ( (__int64)(*(_QWORD *)(v37 + 56) - *(_QWORD *)(v37 + 48)) >> 3 <= (unsigned __int64)v36 )
  {
LABEL_30:
    std::_Xout_of_range("invalid vector subscript");
    __debugbreak();
  }
  _mm_lfence();
  v69 = *(__int64 **)(*(_QWORD *)(v37 + 48) + 8LL * v36);
  v70 = *((_DWORD *)v69 + 5);
  if ( pExceptionObject != (void **)pExceptionObject_8 )
    *(_QWORD *)&pExceptionObject_8 = pExceptionObject;
  for ( m = v35; ; ++m )
  {
    if ( m >= v70 )
    {
      v72 = *(_QWORD *)(v121 + 16);
      v73 = *(_QWORD *)(v72 + 48);
      if ( (*(_QWORD *)(v72 + 56) - v73) >> 3 <= (unsigned __int64)v36 )
        goto LABEL_30;
      v74 = *v69;
      v7 = v121;
      v75 = *(_QWORD *)(v121 + 32);
      if ( !v75 || (v76 = *(_QWORD *)(v75 + 8LL * v36)) == 0 )
        v76 = *(_QWORD *)(*(_QWORD *)(v73 + 8LL * v36) + 24LL);
      v77 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, void **, __int64, void ***))(*(_QWORD *)v74 + 120LL))(
                        v74,
                        v133,
                        v76,
                        &pExceptionObject);
      v25 = v123;
      *(_OWORD *)&v123[2 * v36++] = *v77;
      v35 = 0;
      goto LABEL_28;
    }
    v78 = v69[1];
    v79 = *(_DWORD *)(v78 + 8LL * m);
    if ( v79 == 2 )
    {
      v80 = (_OWORD *)(v124 + 16LL * *(unsigned int *)(v78 + 8LL * m + 4));
      goto LABEL_83;
    }
    v81 = v79 - 1;
    if ( !v81 )
    {
      v80 = &v123[2 * *(unsigned int *)(v78 + 8LL * m + 4)];
      goto LABEL_83;
    }
    if ( v81 != 2 )
      break;
    v82 = *(unsigned int *)(v78 + 8LL * m + 4);
    v83 = *(_QWORD *)(v121 + 16);
    if ( (__int64)(*(_QWORD *)(v83 + 32) - *(_QWORD *)(v83 + 24)) >> 3 <= v82 )
      goto LABEL_30;
    _mm_lfence();
    v80 = &v123[2 * *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v83 + 24) + 8 * v82) + 8LL) - 4LL)];
LABEL_83:
    if ( (_QWORD)pExceptionObject_8 == *((_QWORD *)&pExceptionObject_8 + 1) )
    {
      std::vector<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>>::_Emplace_reallocate<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &>(
        &pExceptionObject,
        pExceptionObject_8,
        v80);
    }
    else
    {
      *(_OWORD *)pExceptionObject_8 = *v80;
      *(_QWORD *)&pExceptionObject_8 = pExceptionObject_8 + 16;
    }
  }
  LODWORD(v38) = -2147024809;
  v39 = -2147024809;
  DoStackCaptureDirect(-2147024809, 0x24Fu);
  v25 = v123;
  v7 = v121;
  v35 = 0;
LABEL_32:
  v40 = pExceptionObject;
  if ( pExceptionObject )
  {
    v41 = (*((_QWORD *)&pExceptionObject_8 + 1) - (_QWORD)pExceptionObject) & 0xFFFFFFFFFFFFFFF0uLL;
    v120 = v41;
    v133[0] = pExceptionObject;
    if ( v41 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v133, &v120);
      v41 = v120;
      v40 = (void **)v133[0];
    }
    operator delete(v40, v41);
    v35 = 0;
    pExceptionObject = 0;
    pExceptionObject_8 = 0;
  }
  if ( v39 < 0 )
  {
    LODWORD(v38) = v39;
    DoStackCaptureDirect(v39, 0x1AEu);
  }
  else
  {
    v42 = v35;
    if ( (_DWORD)v8 )
    {
      do
      {
        v43 = v42;
        v31[v43].m128_u64[0] = 0;
        v31[v43].m128_u64[1] = 0;
        ++v42;
      }
      while ( v42 < (unsigned int)v8 );
    }
    v44 = (unsigned int)(v8 - 1);
LABEL_40:
    if ( (int)v44 >= 0 )
    {
LABEL_55:
      v54 = *(_QWORD *)(v7 + 16);
      v55 = *(_QWORD *)(v54 + 48);
      if ( (*(_QWORD *)(v54 + 56) - v55) >> 3 <= (unsigned __int64)(unsigned int)v44 )
      {
LABEL_56:
        std::_Xout_of_range("invalid vector subscript");
        __debugbreak();
      }
      v85 = *(_QWORD *)(v55 + 8 * v44);
      v86 = *(_DWORD *)(v85 + 20);
      v87 = 0;
      *(_OWORD *)v133 = 0;
      v88 = v35;
      LODWORD(v89) = _mm_shuffle_ps((__m128)0LL, (__m128)0LL, 255).m128_u32[0];
      v90 = _mm_shuffle_ps((__m128)0LL, (__m128)0LL, 170).m128_u32[0];
      v91 = _mm_shuffle_ps((__m128)0LL, (__m128)0LL, 85).m128_u32[0];
      v92.m128_i32[0] = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v88 >= v86 )
          {
            v31[(int)v44] = v87;
            v44 = (unsigned int)(v44 - 1);
            goto LABEL_40;
          }
          v93 = *(_QWORD *)(v85 + 8);
          v94 = *(_DWORD *)(v93 + 8LL * v88);
          if ( v94 == 2 )
            break;
          v101 = v94 - 1;
          if ( v101 )
          {
            if ( v101 != 2 )
            {
              DoStackCaptureDirect(v38, 0x29Du);
              DoStackCaptureDirect(v38, 0x1B2u);
              goto LABEL_66;
            }
            v102 = *(unsigned int *)(v93 + 8LL * v88 + 4);
            v103 = *(_QWORD *)(v7 + 16);
            if ( (__int64)(*(_QWORD *)(v103 + 32) - *(_QWORD *)(v103 + 24)) >> 3 <= v102 )
              goto LABEL_56;
            _mm_lfence();
            v104 = &v25[2 * *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v103 + 24) + 8 * v102) + 8LL) - 4LL)];
            if ( *(float *)&v90 <= v92.m128_f32[0] || v89 <= *(float *)&v91 )
            {
              if ( (unsigned __int8)TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::IsEmpty(v104)
                || !(unsigned __int8)TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::HasValidValues() )
              {
                goto LABEL_133;
              }
              v87 = *v105;
              LODWORD(v89) = _mm_shuffle_ps(v87, v87, 255).m128_u32[0];
              v90 = _mm_shuffle_ps(*v105, *v105, 170).m128_u32[0];
              v91 = _mm_shuffle_ps(*v105, *v105, 85).m128_u32[0];
              v92 = *v105;
              *(__m128 *)v133 = *v105;
              ++v88;
              v35 = 0;
            }
            else
            {
              if ( (unsigned __int8)TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::IsEmpty(v104) )
                goto LABEL_109;
              if ( v92.m128_f32[0] > *(float *)v113 )
              {
                v92.m128_i32[0] = *(_DWORD *)v113;
                v87 = *(__m128 *)v133;
                v87.m128_f32[0] = *(float *)v113;
                *(__m128 *)v133 = v87;
              }
              v114 = *(float *)(v113 + 4);
              if ( *(float *)&v91 > v114 )
              {
                v91 = *(unsigned __int32 *)(v113 + 4);
                v115 = _mm_shuffle_ps(*(__m128 *)v133, *(__m128 *)v133, 225);
                v115.m128_f32[0] = v114;
                v87 = _mm_shuffle_ps(v115, v115, 225);
                *(__m128 *)v133 = v87;
              }
              v116 = *(float *)(v113 + 8);
              if ( v116 > *(float *)&v90 )
              {
                v90 = *(unsigned __int32 *)(v113 + 8);
                v117 = _mm_shuffle_ps(*(__m128 *)v133, *(__m128 *)v133, 210);
                v117.m128_f32[0] = v116;
                v87 = _mm_shuffle_ps(v117, v117, 201);
                *(__m128 *)v133 = v87;
              }
              v109 = *(float *)(v113 + 12);
LABEL_131:
              if ( v109 > v89 )
              {
                v110 = _mm_shuffle_ps(*(__m128 *)v133, *(__m128 *)v133, 147);
                v110.m128_f32[0] = v109;
                v87 = _mm_shuffle_ps(v110, v110, 57);
                v89 = v109;
                goto LABEL_108;
              }
LABEL_109:
              ++v88;
              v35 = 0;
            }
          }
          else
          {
            TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::UnionUnsafe(
              v133,
              &v25[2 * *(unsigned int *)(v93 + 8LL * v88 + 4)]);
            v89 = *((float *)&v133[1] + 1);
            v90 = (unsigned __int32)v133[1];
            v91 = HIDWORD(v133[0]);
            v92.m128_i32[0] = (__int32)v133[0];
            v87 = *(__m128 *)v133;
            v88 = v106 + 1;
            v35 = 0;
          }
        }
        v95 = 16LL * *(unsigned int *)(v93 + 8LL * v88 + 4);
        if ( *(float *)&v90 <= v92.m128_f32[0] || v89 <= *(float *)&v91 )
          v96 = 1;
        else
          v96 = v35;
        v97 = *(float *)(v95 + v124);
        v98 = *(float *)(v95 + v124 + 8);
        v99 = (float *)(v95 + v124 + 4);
        v100 = v98 <= v97 || *(float *)(v95 + v124 + 12) <= *v99;
        if ( !v96 )
        {
          if ( v100 )
            goto LABEL_109;
          if ( v92.m128_f32[0] > v97 )
          {
            v92.m128_i32[0] = *(_DWORD *)(v95 + v124);
            v87 = *(__m128 *)v133;
            v87.m128_f32[0] = v97;
            *(__m128 *)v133 = v87;
          }
          if ( *(float *)&v91 > *v99 )
          {
            v91 = *(unsigned __int32 *)v99;
            v107 = _mm_shuffle_ps(*(__m128 *)v133, *(__m128 *)v133, 225);
            v107.m128_f32[0] = *v99;
            v87 = _mm_shuffle_ps(v107, v107, 225);
            *(__m128 *)v133 = v87;
          }
          if ( v98 > *(float *)&v90 )
          {
            *(float *)&v90 = v98;
            v108 = _mm_shuffle_ps(*(__m128 *)v133, *(__m128 *)v133, 210);
            v108.m128_f32[0] = v98;
            v87 = _mm_shuffle_ps(v108, v108, 201);
            *(__m128 *)v133 = v87;
          }
          v109 = *(float *)(v95 + v124 + 12);
          goto LABEL_131;
        }
        if ( !v100 )
        {
          v87 = *(__m128 *)(v95 + v124);
          LODWORD(v89) = _mm_shuffle_ps(v87, v87, 255).m128_u32[0];
          v90 = _mm_shuffle_ps(v87, v87, 170).m128_u32[0];
          v91 = _mm_shuffle_ps(v87, v87, 85).m128_u32[0];
          v92.m128_i32[0] = v87.m128_i32[0];
LABEL_108:
          *(__m128 *)v133 = v87;
          goto LABEL_109;
        }
LABEL_133:
        v89 = 0.0;
        *(float *)&v90 = 0.0;
        *(float *)&v91 = 0.0;
        v92.m128_i32[0] = 0;
        v111 = _mm_shuffle_ps((__m128)0LL, (__m128)0LL, 210);
        v111.m128_f32[0] = 0.0;
        v112 = _mm_shuffle_ps(v111, v111, 198);
        v112.m128_f32[0] = 0.0;
        v87 = _mm_shuffle_ps(v112, v112, 225);
        v87.m128_f32[0] = 0.0;
        *(__m128 *)v133 = v87;
        ++v88;
        v35 = 0;
      }
    }
    v38 = (unsigned __int64)v122;
    v45 = Windows::UI::Composition::EffectInstance::CalcInversedInputBounds(
            v7,
            v134,
            v8,
            a5,
            (__int64)v31,
            (__int64)v122,
            (__int64)lpMem,
            (__int64)&v128);
    LODWORD(v120) = v45;
    if ( v45 < 0 )
    {
      DoStackCaptureDirect(v45, 0x1BCu);
      LODWORD(v38) = v120;
      goto LABEL_66;
    }
    std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(&pExceptionObject);
    v46 = 0;
    if ( (_DWORD)v8 )
    {
      while ( 1 )
      {
        v47 = *(_QWORD *)(v7 + 16);
        if ( (__int64)(*(_QWORD *)(v47 + 56) - *(_QWORD *)(v47 + 48)) >> 3 <= (unsigned __int64)(unsigned int)v46 )
          break;
        _mm_lfence();
        v25 = *(_QWORD **)(*(_QWORD *)(v47 + 48) + 8 * v46);
        v7 = *((unsigned int *)v25 + 5);
        v48 = (char *)pExceptionObject_8;
        if ( pExceptionObject != (void **)pExceptionObject_8 )
        {
          v48 = (char *)pExceptionObject;
          *(_QWORD *)&pExceptionObject_8 = pExceptionObject;
        }
        v38 = 0;
        if ( (_DWORD)v7 )
        {
          while ( 1 )
          {
            v49 = v25[1];
            v50 = *(_DWORD *)(v49 + 8 * v38);
            if ( v50 == 2 )
              break;
            v65 = v50 - 1;
            if ( !v65 )
            {
              v51 = (char *)v122 + 16 * *(unsigned int *)(v49 + 8 * v38 + 4);
LABEL_49:
              if ( v48 == *((char **)&pExceptionObject_8 + 1) )
              {
                std::vector<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>>::_Emplace_reallocate<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &>(
                  &pExceptionObject,
                  v48,
                  v51);
                v48 = (char *)pExceptionObject_8;
              }
              else
              {
                *(_OWORD *)v48 = *(_OWORD *)v51;
                v48 = (char *)(pExceptionObject_8 + 16);
                *(_QWORD *)&pExceptionObject_8 = pExceptionObject_8 + 16;
              }
              goto LABEL_51;
            }
            if ( v65 == 2 )
            {
              v66 = *(_QWORD *)(v121 + 16);
              v67 = *(_QWORD *)(v66 + 24);
              v68 = *(unsigned int *)(v49 + 8 * v38 + 4);
              if ( (*(_QWORD *)(v66 + 32) - v67) >> 3 <= v68 )
                goto LABEL_54;
              v51 = (char *)v122 + 16 * *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v67 + 8 * v68) + 8LL) - 4LL);
              goto LABEL_49;
            }
LABEL_51:
            v38 = (unsigned int)(v38 + 1);
            if ( (unsigned int)v38 >= (unsigned int)v7 )
              goto LABEL_52;
          }
          v51 = (char *)lpMem + 16 * *(unsigned int *)(v49 + 8 * v38 + 4);
          goto LABEL_49;
        }
LABEL_52:
        v7 = v121;
        if ( (v48 - (char *)pExceptionObject) >> 4 )
        {
          v52 = *(_QWORD *)(v121 + 16);
          v53 = *(_QWORD *)(v52 + 48);
          if ( (*(_QWORD *)(v52 + 56) - v53) >> 3 <= (unsigned __int64)(unsigned int)v46 )
            break;
          v84 = *(_QWORD *)(v121 + 32);
          if ( !v84 || (v56 = *(_QWORD *)(v84 + 8 * v46)) == 0 )
            v56 = *(_QWORD *)(*(_QWORD *)(v53 + 8 * v46) + 24LL);
          v57 = (_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _OWORD **, __int64, void ***))(*(_QWORD *)*v25 + 120LL))(
                            *v25,
                            &v134,
                            v56,
                            &pExceptionObject);
          v38 = (unsigned __int64)v122;
          *((_OWORD *)v122 + (unsigned int)v46) = *v57;
        }
        else
        {
          v38 = (unsigned __int64)v122;
        }
        v46 = (unsigned int)(v46 + 1);
        if ( (unsigned int)v46 >= (unsigned int)v8 )
          goto LABEL_61;
      }
LABEL_54:
      std::_Xout_of_range("invalid vector subscript");
      goto LABEL_55;
    }
LABEL_61:
    v58 = pExceptionObject;
    if ( pExceptionObject )
    {
      v59 = (*((_QWORD *)&pExceptionObject_8 + 1) - (_QWORD)pExceptionObject) & 0xFFFFFFFFFFFFFFF0uLL;
      v124 = v59;
      v133[0] = pExceptionObject;
      if ( v59 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(v133, &v124);
        v59 = v124;
        v58 = (void **)v133[0];
      }
      operator delete(v58, v59);
    }
    *v126 = v128;
    *v127 = *(_OWORD *)(v38 + 16LL * (unsigned int)(v8 - 1));
    v25 = v123;
    LODWORD(v38) = v120;
  }
LABEL_66:
  v60 = GetProcessHeap();
  HeapFree(v60, 0, v31);
  v61 = GetProcessHeap();
  HeapFree(v61, 0, v25);
  v62 = GetProcessHeap();
  HeapFree(v62, 0, lpMem);
  v63 = GetProcessHeap();
  HeapFree(v63, 0, v122);
  return (unsigned int)v38;
}

```

## disassembly

```asm
0x18000efc0  mov     rax, rsp
0x18000efc3  mov     [rax+18h], rbx
0x18000efc7  push    rbp
0x18000efc8  push    rsi
0x18000efc9  push    rdi
0x18000efca  push    r12
0x18000efcc  push    r13
0x18000efce  push    r14
0x18000efd0  push    r15
0x18000efd2  lea     rbp, [rax-48h]
0x18000efd6  sub     rsp, 110h
0x18000efdd  movaps  xmmword ptr [rax-48h], xmm6
0x18000efe1  movaps  xmmword ptr [rax-58h], xmm7
0x18000efe5  mov     rax, cs:__security_cookie
0x18000efec  xor     rax, rsp
0x18000efef  mov     [rbp+40h+var_58], rax
0x18000eff3  mov     [rsp+140h+var_C8], r9
0x18000eff8  mov     [rbp+40h+var_68], rdx
0x18000effc  mov     r13, rcx
0x18000efff  mov     [rsp+140h+var_E0], rcx
0x18000f004  mov     rax, [rbp+40h+arg_28]
0x18000f008  mov     [rbp+40h+var_B8], rax
0x18000f00c  mov     rax, [rbp+40h+arg_30]
0x18000f013  mov     [rbp+40h+var_B0], rax
0x18000f017  mov     rcx, [rcx+10h]
0x18000f01b  add     rcx, 10h
0x18000f01f  mov     rax, [rcx]
0x18000f022  mov     rax, [rax+50h]
0x18000f026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f02b  mov     r14d, eax
0x18000f02e  mov     edi, eax
0x18000f030  mov     [rbp+40h+var_78], rdi
0x18000f034  mov     eax, 10h
0x18000f039  mul     r14
0x18000f03c  mov     rbx, rax
0x18000f03f  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000f046  cmovb   rbx, r12
0x18000f04a  call    cs:__imp_GetProcessHeap
0x18000f050  mov     rcx, rax; hHeap
0x18000f053  mov     r8, rbx; dwBytes
0x18000f056  xor     edx, edx; dwFlags
0x18000f058  call    cs:__imp_HeapAlloc
0x18000f05e  mov     r15, rax
0x18000f061  mov     [rsp+140h+var_D8], rax
0x18000f066  test    rax, rax
0x18000f069  jnz     short loc_18000F09D
0x18000f06b  xorps   xmm0, xmm0
0x18000f06e  movups  [rsp+140h+pExceptionObject+8], xmm0
0x18000f073  lea     rax, aBadAllocation; "bad allocation"
0x18000f07a  mov     qword ptr [rsp+140h+pExceptionObject+8], rax
0x18000f07f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000f086  mov     qword ptr [rsp+140h+pExceptionObject], rax
0x18000f08b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000f092  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18000f097  call    _CxxThrowException_0
0x18000f09d  mov     [rbp+40h+lpMem], r15
0x18000f0a1  mov     rbx, rdi
0x18000f0a4  mov     rsi, r15
0x18000f0a7  test    rdi, rdi
0x18000f0aa  jz      short loc_18000F0BE
0x18000f0ac  mov     rcx, rsi
0x18000f0af  call    ??0?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@QEAA@XZ; TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(void)
0x18000f0b4  add     rsi, 10h
0x18000f0b8  sub     rbx, 1
0x18000f0bc  jnz     short loc_18000F0AC
0x18000f0be  mov     [rbp+40h+var_98], r15
0x18000f0c2  mov     esi, [rbp+40h+arg_20]
0x18000f0c5  mov     [rbp+40h+var_78], rsi
0x18000f0c9  mov     eax, 10h
0x18000f0ce  mul     rsi
0x18000f0d1  mov     rbx, rax
0x18000f0d4  cmovb   rbx, r12
0x18000f0d8  call    cs:__imp_GetProcessHeap
0x18000f0de  mov     rcx, rax; hHeap
0x18000f0e1  mov     r8, rbx; dwBytes
0x18000f0e4  xor     edx, edx; dwFlags
0x18000f0e6  call    cs:__imp_HeapAlloc
0x18000f0ec  mov     r15, rax
0x18000f0ef  mov     [rbp+40h+lpMem], rax
0x18000f0f3  test    rax, rax
0x18000f0f6  jnz     short loc_18000F12A
0x18000f0f8  xorps   xmm0, xmm0
0x18000f0fb  movups  [rsp+140h+pExceptionObject+8], xmm0
0x18000f100  lea     rax, aBadAllocation; "bad allocation"
0x18000f107  mov     qword ptr [rsp+140h+pExceptionObject+8], rax
0x18000f10c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000f113  mov     qword ptr [rsp+140h+pExceptionObject], rax
0x18000f118  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000f11f  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18000f124  call    _CxxThrowException_0
0x18000f12a  mov     [rsp+140h+var_D0], r15
0x18000f12f  mov     rbx, r15
0x18000f132  test    rsi, rsi
0x18000f135  jz      short loc_18000F149
0x18000f137  mov     rcx, rbx
0x18000f13a  call    ??0?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@QEAA@XZ; TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(void)
0x18000f13f  add     rbx, 10h
0x18000f143  sub     rsi, 1
0x18000f147  jnz     short loc_18000F137
0x18000f149  mov     [rbp+40h+var_90], r15
0x18000f14d  xorps   xmm0, xmm0
0x18000f150  movups  [rbp+40h+var_A8], xmm0
0x18000f154  mov     [rbp+40h+var_78], rdi
0x18000f158  mov     eax, 10h
0x18000f15d  mul     rdi
0x18000f160  mov     rbx, rax
0x18000f163  cmovb   rbx, r12
0x18000f167  call    cs:__imp_GetProcessHeap
0x18000f16d  mov     rcx, rax; hHeap
0x18000f170  mov     r8, rbx; dwBytes
0x18000f173  xor     edx, edx; dwFlags
0x18000f175  call    cs:__imp_HeapAlloc
0x18000f17b  mov     r15, rax
0x18000f17e  mov     [rsp+140h+var_D0], rax
0x18000f183  test    rax, rax
0x18000f186  jnz     short loc_18000F1BA
0x18000f188  xorps   xmm0, xmm0
0x18000f18b  movups  [rsp+140h+pExceptionObject+8], xmm0
0x18000f190  lea     rax, aBadAllocation; "bad allocation"
0x18000f197  mov     qword ptr [rsp+140h+pExceptionObject+8], rax
0x18000f19c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000f1a3  mov     qword ptr [rsp+140h+pExceptionObject], rax
0x18000f1a8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000f1af  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18000f1b4  call    _CxxThrowException_0
0x18000f1ba  mov     [rsp+140h+var_E8], r15
0x18000f1bf  mov     rbx, rdi
0x18000f1c2  mov     rsi, r15
0x18000f1c5  test    rdi, rdi
0x18000f1c8  jz      short loc_18000F1DC
0x18000f1ca  mov     rcx, rsi
0x18000f1cd  call    ??0?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@QEAA@XZ; TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(void)
0x18000f1d2  add     rsi, 10h
0x18000f1d6  sub     rbx, 1
0x18000f1da  jnz     short loc_18000F1CA
0x18000f1dc  mov     [rbp+40h+var_88], r15
0x18000f1e0  mov     [rbp+40h+var_78], rdi
0x18000f1e4  mov     eax, 10h
0x18000f1e9  mul     rdi
0x18000f1ec  mov     rbx, rax
0x18000f1ef  cmovb   rbx, r12
0x18000f1f3  call    cs:__imp_GetProcessHeap
0x18000f1f9  mov     rcx, rax; hHeap
0x18000f1fc  mov     r8, rbx; dwBytes
0x18000f1ff  xor     edx, edx; dwFlags
0x18000f201  call    cs:__imp_HeapAlloc
0x18000f207  mov     r12, rax
0x18000f20a  test    rax, rax
0x18000f20d  jnz     short loc_18000F241
0x18000f20f  xorps   xmm0, xmm0
0x18000f212  movups  [rsp+140h+pExceptionObject+8], xmm0
0x18000f217  lea     rax, aBadAllocation; "bad allocation"
0x18000f21e  mov     qword ptr [rsp+140h+pExceptionObject+8], rax
0x18000f223  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000f22a  mov     qword ptr [rsp+140h+pExceptionObject], rax
0x18000f22f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000f236  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18000f23b  call    _CxxThrowException_0
0x18000f241  mov     [rsp+140h+var_E8], r12
0x18000f246  mov     rbx, r12
0x18000f249  test    r14d, r14d
0x18000f24c  jz      short loc_18000F260
0x18000f24e  mov     rcx, rbx
0x18000f251  call    ??0?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@QEAA@XZ; TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>::TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>(void)
0x18000f256  add     rbx, 10h
0x18000f25a  sub     rdi, 1
0x18000f25e  jnz     short loc_18000F24E
0x18000f260  mov     [rbp+40h+var_80], r12
0x18000f264  xor     r9d, r9d
0x18000f267  mov     ecx, r9d
0x18000f26a  test    r14d, r14d
0x18000f26d  jz      short loc_18000F284
0x18000f26f  mov     eax, ecx
0x18000f271  add     rax, rax
0x18000f274  mov     [r15+rax*8], r9
0x18000f278  mov     [r15+rax*8+8], r9
0x18000f27d  inc     ecx
0x18000f27f  cmp     ecx, r14d
0x18000f282  jb      short loc_18000F26F
0x18000f284  mov     dword ptr [rsp+140h+var_E8], r9d
0x18000f289  lea     rcx, [rsp+140h+pExceptionObject]
0x18000f28e  call    ??0?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(void)
0x18000f293  nop
0x18000f294  mov     edi, r9d
0x18000f297  cmp     edi, r14d
0x18000f29a  jnb     short loc_18000F2C5
0x18000f29c  mov     rcx, [r13+10h]
0x18000f2a0  mov     esi, edi
0x18000f2a2  mov     rax, [rcx+38h]
0x18000f2a6  sub     rax, [rcx+30h]
0x18000f2aa  sar     rax, 3
0x18000f2ae  cmp     rax, rsi
0x18000f2b1  ja      loc_18000F62A
0x18000f2b7  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x18000f2be  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000f2c4  int     3; Trap to Debugger
0x18000f2c5  mov     esi, 80070057h
0x18000f2ca  mov     ebx, dword ptr [rsp+140h+var_E8]
0x18000f2ce  mov     rcx, qword ptr [rsp+140h+pExceptionObject]; void *
0x18000f2d3  test    rcx, rcx
0x18000f2d6  jz      short loc_18000F310
0x18000f2d8  mov     rdx, [rsp+140h+var_F0]
0x18000f2dd  sub     rdx, rcx
0x18000f2e0  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x18000f2e4  mov     [rsp+140h+var_E8], rdx
0x18000f2e9  mov     [rbp+40h+var_78], rcx
0x18000f2ed  cmp     rdx, 1000h
0x18000f2f4  jnb     loc_18000FB2B
0x18000f2fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f2ff  xor     r9d, r9d
0x18000f302  mov     qword ptr [rsp+140h+pExceptionObject], r9
0x18000f307  xorps   xmm0, xmm0
0x18000f30a  movdqu  [rsp+140h+pExceptionObject+8], xmm0
0x18000f310  test    ebx, ebx
0x18000f312  js      loc_18000F498
0x18000f318  mov     ecx, r9d
0x18000f31b  test    r14d, r14d
0x18000f31e  jz      short loc_18000F33D
0x18000f320  mov     eax, ecx
0x18000f322  add     rax, rax
0x18000f325  mov     qword ptr [r12+rax*8], 0
0x18000f32d  mov     qword ptr [r12+rax*8+8], 0
0x18000f336  inc     ecx
0x18000f338  cmp     ecx, r14d
0x18000f33b  jb      short loc_18000F320
0x18000f33d  lea     r10d, [r14-1]
0x18000f341  test    r10d, r10d
0x18000f344  jns     loc_18000F46B
0x18000f34a  lea     rax, [rbp+40h+var_A8]
0x18000f34e  mov     [rsp+140h+var_108], rax
0x18000f353  mov     rax, [rbp+40h+lpMem]
0x18000f357  mov     [rsp+140h+var_110], rax
0x18000f35c  mov     rsi, [rsp+140h+var_D8]
0x18000f361  mov     [rsp+140h+var_118], rsi
0x18000f366  mov     [rsp+140h+var_120], r12
0x18000f36b  mov     r9d, [rbp+40h+arg_20]
0x18000f36f  mov     r8d, r14d
0x18000f372  mov     rdx, [rbp+40h+var_68]
0x18000f376  mov     rcx, r13
0x18000f379  call    ?CalcInversedInputBounds@EffectInstance@Composition@UI@Windows@@AEBAJAEBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@IIPEBV5@PEAV5@22@Z; Windows::UI::Composition::EffectInstance::CalcInversedInputBounds(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &,uint,uint,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const *,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> *,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> *,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> *)
0x18000f37e  mov     dword ptr [rsp+140h+var_E8], eax
0x18000f382  test    eax, eax
0x18000f384  js      loc_18000FB6D
0x18000f38a  lea     rcx, [rsp+140h+pExceptionObject]
0x18000f38f  call    ??0?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(void)
0x18000f394  nop
0x18000f395  xor     edi, edi
0x18000f397  test    r14d, r14d
0x18000f39a  jz      loc_18000F4E2
0x18000f3a0  mov     rcx, [r13+10h]
0x18000f3a4  mov     ebx, edi
0x18000f3a6  mov     rax, [rcx+38h]
0x18000f3aa  sub     rax, [rcx+30h]
0x18000f3ae  sar     rax, 3
0x18000f3b2  cmp     rax, rbx
0x18000f3b5  jbe     loc_18000F45D
0x18000f3bb  lfence
0x18000f3be  mov     rax, [rcx+30h]
0x18000f3c2  mov     r15, [rax+rdi*8]
0x18000f3c6  mov     r13d, [r15+14h]
0x18000f3ca  mov     rax, qword ptr [rsp+140h+pExceptionObject]
0x18000f3cf  mov     rdx, qword ptr [rsp+140h+pExceptionObject+8]
0x18000f3d4  cmp     rax, rdx
0x18000f3d7  jnz     loc_18000F7CF
0x18000f3dd  xor     esi, esi
0x18000f3df  test    r13d, r13d
0x18000f3e2  jz      short loc_18000F42A
0x18000f3e4  mov     r8, [r15+8]
0x18000f3e8  mov     r9d, [r8+rsi*8]
0x18000f3ec  cmp     r9d, 2
0x18000f3f0  jnz     loc_18000F5D6
0x18000f3f6  mov     r8d, [r8+rsi*8+4]
0x18000f3fb  shl     r8, 4
0x18000f3ff  add     r8, [rbp+40h+lpMem]
0x18000f403  cmp     rdx, [rsp+140h+var_F0]
0x18000f408  jz      loc_18000F5C2
0x18000f40e  movups  xmm0, xmmword ptr [r8]
0x18000f412  movups  xmmword ptr [rdx], xmm0
0x18000f415  mov     rdx, qword ptr [rsp+140h+pExceptionObject+8]
0x18000f41a  add     rdx, 10h
0x18000f41e  mov     qword ptr [rsp+140h+pExceptionObject+8], rdx
0x18000f423  inc     esi
0x18000f425  cmp     esi, r13d
0x18000f428  jb      short loc_18000F3E4
0x18000f42a  sub     rdx, qword ptr [rsp+140h+pExceptionObject]
0x18000f42f  sar     rdx, 4
0x18000f433  mov     r13, [rsp+140h+var_E0]
0x18000f438  test    rdx, rdx
0x18000f43b  jz      loc_18000FB47
0x18000f441  mov     rax, [r13+10h]
0x18000f445  mov     rdx, [rax+30h]
0x18000f449  mov     rcx, [rax+38h]
0x18000f44d  sub     rcx, rdx
0x18000f450  sar     rcx, 3
0x18000f454  cmp     rcx, rbx
0x18000f457  ja      loc_18000F7AD
0x18000f45d  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x18000f464  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000f46a  nop
0x18000f46b  mov     rax, [r13+10h]
  ... truncated ...
```
