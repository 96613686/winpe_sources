# ClusterAlgorithm(std::vector<NtpTimeSample,std::allocator<NtpTimeSample>> *)

- ea: `0x180027ec4`
- end: `0x180028448`
- name: `?ClusterAlgorithm@@YAHPEAV?$vector@UNtpTimeSample@@V?$allocator@UNtpTimeSample@@@std@@@std@@@Z`
- size: `1412`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180027e80`

## callees

- `0x180016454`
- `0x180018138`
- `0x180018dfc`
- `0x18001d9a0`
- `0x180027ec4`
- `0x180028fa4`
- `0x180034214`
- `0x180034aa0`
- `0x18003d2d8`
- `0x18003dd20`
- `0x18003f49d`
- `0x1800411d4`
- `0x180048848`
- `0x180048b0c`
- `0x18004efac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180028272`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800282e5`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002830f`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002835f`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180028272`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800282e5`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002830f`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002835f`

## string_xrefs

- `0x180028036`: `Only considering the best %d clocks for clustering algorithm.\n`

## pseudocode

```c
__int64 __fastcall ClusterAlgorithm(unsigned __int64 a1)
{
  _QWORD *v1; // r12
  void *v2; // rcx
  _QWORD *v4; // r10
  _QWORD *v5; // rsi
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rdi
  _QWORD *i; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // r9
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned __int64 v13; // r8
  double v14; // xmm0_8
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // r13
  char v17; // cl
  _QWORD *v18; // rax
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  _QWORD *j; // rbx
  void *v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int128 v26; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-D8h]
  _QWORD *v28; // [rsp+48h] [rbp-D0h] BYREF
  __int128 v29; // [rsp+50h] [rbp-C8h]
  _QWORD *v30; // [rsp+60h] [rbp-B8h]
  __int64 v31; // [rsp+68h] [rbp-B0h]
  _BYTE v32[24]; // [rsp+70h] [rbp-A8h] BYREF
  int v33; // [rsp+88h] [rbp-90h]
  _BYTE v34[24]; // [rsp+90h] [rbp-88h] BYREF
  int v35; // [rsp+A8h] [rbp-70h]
  _BYTE v36[24]; // [rsp+B0h] [rbp-68h] BYREF
  _BYTE v37[80]; // [rsp+C8h] [rbp-50h] BYREF
  unsigned __int64 v38; // [rsp+120h] [rbp+8h] BYREF
  void *v39; // [rsp+128h] [rbp+10h] BYREF
  unsigned int v40; // [rsp+130h] [rbp+18h]
  _QWORD *v41; // [rsp+138h] [rbp+20h] BYREF

  v38 = a1;
  v1 = (_QWORD *)a1;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v26);
  v30 = v1 + 1;
  if ( v1[1] == *v1 )
  {
    v2 = (void *)v26;
    if ( (_QWORD)v26 )
    {
      v38 = 8 * ((v27 - (__int64)v26) >> 3);
      v39 = (void *)v26;
      if ( v38 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v39, &v38);
        v2 = v39;
      }
      operator delete(v2);
      goto LABEL_9;
    }
    return 0;
  }
  v40 = CreateAndSortCandidateList(v1, &v26);
  if ( !v40 )
  {
    if ( (_QWORD)v26 )
    {
      std::_Deallocate<16>((void *)v26, 8 * ((v27 - (__int64)v26) >> 3));
LABEL_9:
      v27 = 0;
      v26 = 0;
    }
    return 0;
  }
  v4 = (_QWORD *)v26;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v26 + 1) - v26) >> 3) <= 0xA )
    goto LABEL_15;
  std::vector<CandidateEntry>::erase(&v26, &v39, v26 + 240);
  if ( (unsigned __int8)FileLogAllowEntry(133) )
    FileLogAdd(L"Only considering the best %d clocks for clustering algorithm.\n", 10);
  while ( 1 )
  {
    v4 = (_QWORD *)v26;
LABEL_15:
    v5 = 0;
    LOBYTE(v39) = 0;
    v6 = -1;
    v7 = 0;
    for ( i = v4; ; i += 3 )
    {
      v9 = (_QWORD *)*((_QWORD *)&v26 + 1);
      if ( i == *((_QWORD **)&v26 + 1) )
        break;
      v10 = (_QWORD *)i[2];
      v41 = v10;
      v11 = 0;
      while ( v9 != v4 )
      {
        v12 = v10[74] - *(_QWORD *)(*(v9 - 1) + 592LL);
        if ( v12 < 0 )
          v12 = *(_QWORD *)(*(v9 - 1) + 592LL) - v10[74];
        v11 += v12 * v12;
        v9 -= 3;
      }
      v13 = 1;
      if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v26 + 1) - (_QWORD)v4) >> 3) - 1 > 1 )
        v13 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v26 + 1) - (_QWORD)v4) >> 3) - 1;
      v14 = sqrt((double)(int)(v11 / v13));
      v15 = 0;
      if ( v14 >= 9.223372036854776e18 )
      {
        v14 = v14 - 9.223372036854776e18;
        if ( v14 < 9.223372036854776e18 )
          v15 = 0x8000000000000000uLL;
      }
      v16 = v15 + (unsigned int)(int)v14;
      if ( v7 > v16 )
      {
        v17 = 0;
      }
      else
      {
        v17 = 1;
        LOBYTE(v39) = 1;
      }
      v18 = i;
      if ( !v17 )
        v18 = v5;
      v5 = v18;
      v19 = v16;
      if ( !v17 )
        v19 = v7;
      v7 = v19;
      v20 = v41[73];
      if ( v6 <= v20 )
        v20 = v6;
      v6 = v20;
      if ( (unsigned __int8)FileLogAllowEntry(133) )
        FileLogAdd(
          L"  SyncDist:%I64u SelectJitter:%I64u PeerJitter:%I64u CorrectedOffset:%I64d\n",
          i[1],
          v16,
          v41[73],
          v41[74]);
      v4 = (_QWORD *)v26;
    }
    if ( (unsigned __int8)FileLogAllowEntry(133) )
      FileLogAdd(L" MaxSelectJitter: %u MinPeerJitter: %u\n", v7, v6);
    if ( v7 <= v6 || 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v26 + 1) - v26) >> 3) <= 1 )
      break;
    if ( (unsigned __int8)FileLogAllowEntry(133) )
    {
      FileLogAdd(L"Discarding Sample with offset: ");
      FileLogNtTimeOffsetEx(v21, *(_QWORD *)(v5[2] + 592LL));
      FileLogAppend(L"\n");
    }
    if ( !(_BYTE)v39 )
      goto LABEL_58;
    memmove_0(v5, v5 + 3, *((_QWORD *)&v26 + 1) - (_QWORD)(v5 + 3));
    *((_QWORD *)&v26 + 1) -= 24LL;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v28);
  for ( j = (_QWORD *)v26; ; j += 3 )
  {
    v41 = j;
    if ( j == *((_QWORD **)&v26 + 1) )
      break;
    v31 = _set_se_translator(SeTransFunc);
    LODWORD(v39) = 0;
    try
    {
      std::vector<NtpTimeSample>::_Emplace_one_at_back<NtpTimeSample const &>(&v28, j[2]);
    }
    catch ( SeException v34 )
    {
      v25 = v35;
      if ( v35 > 0 )
        v25 = (unsigned __int16)v35 | 0x80070000;
      LODWORD(v39) = v25;
      SeException::~SeException((SeException *)v34);
      v1 = (_QWORD *)v38;
      j = v41;
    }
    catch ( std::bad_alloc v37 )
    {
      LODWORD(v39) = -2147024882;
      SeException::~SeException((SeException *)v37);
      v1 = (_QWORD *)v38;
      j = v41;
    }
    catch ( ... )
    {
      LODWORD(v39) = -2147418113;
      v1 = (_QWORD *)v38;
      j = v41;
    }
    _set_se_translator(v31);
    if ( (int)v39 < 0 )
      goto LABEL_56;
  }
  if ( *v1 != *v30 )
    *v30 = *v1;
  v38 = _set_se_translator(SeTransFunc);
  LODWORD(v39) = 0;
  try
  {
    v41 = v28;
    v41 = (_QWORD *)*v1;
    std::vector<NtpTimeSample>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<NtpTimeSample>>>,0>(
      (_DWORD)v1,
      (unsigned int)&v41,
      (_DWORD)v41,
      (_DWORD)v28,
      v29);
  }
  catch ( SeException v32 )
  {
    v24 = v33;
    if ( v33 > 0 )
      v24 = (unsigned __int16)v33 | 0x80070000;
    LODWORD(v39) = v24;
    SeException::~SeException((SeException *)v32);
  }
  catch ( std::bad_alloc v36 )
  {
    LODWORD(v39) = -2147024882;
    SeException::~SeException((SeException *)v36);
  }
  catch ( ... )
  {
    LODWORD(v39) = -2147418113;
  }
  _set_se_translator(v38);
  if ( (int)v39 >= 0 )
    v40 = 1;
LABEL_56:
  if ( v28 )
  {
    std::_Deallocate<16>(v28, 32 * ((__int64)(*((_QWORD *)&v29 + 1) - (_QWORD)v28) >> 5));
    v28 = 0;
    v29 = 0;
  }
LABEL_58:
  v23 = (void *)v26;
  if ( (_QWORD)v26 )
  {
    v38 = 8 * ((v27 - (__int64)v26) >> 3);
    v39 = (void *)v26;
    if ( v38 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v39, &v38);
      v23 = v39;
    }
    operator delete(v23);
    v26 = 0;
    v27 = 0;
  }
  return v40;
}

```

## disassembly

```asm
0x180027ec4  mov     [rsp+arg_0], rcx
0x180027ec9  push    rbx
0x180027eca  push    rsi
0x180027ecb  push    rdi
0x180027ecc  push    r12
0x180027ece  push    r13
0x180027ed0  push    r14
0x180027ed2  push    r15
0x180027ed4  sub     rsp, 0E0h
0x180027edb  mov     r12, rcx
0x180027ede  lea     rcx, [rsp+118h+var_E8]
0x180027ee3  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180027ee8  nop
0x180027ee9  lea     rax, [r12+8]
0x180027eee  mov     [rsp+118h+var_B8], rax
0x180027ef3  mov     rax, [rax]
0x180027ef6  cmp     rax, [r12]
0x180027efa  jnz     short loc_180027F71
0x180027efc  mov     rcx, qword ptr [rsp+118h+var_E8]
0x180027f01  test    rcx, rcx
0x180027f04  jz      loc_180027FCC
0x180027f0a  mov     rax, [rsp+118h+var_D8]
0x180027f0f  sub     rax, rcx
0x180027f12  sar     rax, 3
0x180027f16  mov     r15, 0AAAAAAAAAAAAAAABh
0x180027f20  imul    rax, r15
0x180027f24  lea     rdx, [rax+rax*2]
0x180027f28  shl     rdx, 3
0x180027f2c  mov     [rsp+118h+arg_0], rdx
0x180027f34  mov     [rsp+118h+arg_8], rcx
0x180027f3c  cmp     rdx, 1000h
0x180027f43  jb      short loc_180027F6A
0x180027f45  lea     rdx, [rsp+118h+arg_0]; unsigned __int64 *
0x180027f4d  lea     rcx, [rsp+118h+arg_8]; void **
0x180027f55  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180027f5a  mov     rdx, [rsp+118h+arg_0]; unsigned __int64
0x180027f62  mov     rcx, [rsp+118h+arg_8]; void *
0x180027f6a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027f6f  jmp     short loc_180027FBA
0x180027f71  lea     rdx, [rsp+118h+var_E8]
0x180027f76  mov     rcx, r12
0x180027f79  call    ?CreateAndSortCandidateList@@YAHPEAV?$vector@UNtpTimeSample@@V?$allocator@UNtpTimeSample@@@std@@@std@@PEAV?$vector@UCandidateEntry@@V?$allocator@UCandidateEntry@@@std@@@2@@Z; CreateAndSortCandidateList(std::vector<NtpTimeSample> *,std::vector<CandidateEntry> *)
0x180027f7e  mov     [rsp+118h+arg_10], eax
0x180027f85  test    eax, eax
0x180027f87  jnz     short loc_180027FE2
0x180027f89  mov     rcx, qword ptr [rsp+118h+var_E8]
0x180027f8e  test    rcx, rcx
0x180027f91  jz      short loc_180027FCC
0x180027f93  mov     rax, [rsp+118h+var_D8]
0x180027f98  sub     rax, rcx
0x180027f9b  sar     rax, 3
0x180027f9f  mov     r15, 0AAAAAAAAAAAAAAABh
0x180027fa9  imul    rax, r15
0x180027fad  lea     rdx, [rax+rax*2]
0x180027fb1  shl     rdx, 3
0x180027fb5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180027fba  xorps   xmm0, xmm0
0x180027fbd  mov     [rsp+118h+var_D8], 0
0x180027fc6  movdqu  [rsp+118h+var_E8], xmm0
0x180027fcc  xor     eax, eax
0x180027fce  add     rsp, 0E0h
0x180027fd5  pop     r15
0x180027fd7  pop     r14
0x180027fd9  pop     r13
0x180027fdb  pop     r12
0x180027fdd  pop     rdi
0x180027fde  pop     rsi
0x180027fdf  pop     rbx
0x180027fe0  retn
0x180027fe2  mov     r9, qword ptr [rsp+118h+var_E8+8]
0x180027fe7  mov     rax, r9
0x180027fea  mov     r10, qword ptr [rsp+118h+var_E8]
0x180027fef  sub     rax, r10
0x180027ff2  sar     rax, 3
0x180027ff6  mov     r15, 0AAAAAAAAAAAAAAABh
0x180028000  imul    rax, r15
0x180028004  cmp     rax, 0Ah
0x180028008  jbe     short loc_180028047
0x18002800a  lea     r8, [r10+0F0h]
0x180028011  lea     rdx, [rsp+118h+arg_8]
0x180028019  lea     rcx, [rsp+118h+var_E8]
0x18002801e  call    ?erase@?$vector@UCandidateEntry@@V?$allocator@UCandidateEntry@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCandidateEntry@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UCandidateEntry@@@std@@@std@@@2@0@Z; std::vector<CandidateEntry>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CandidateEntry>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CandidateEntry>>>)
0x180028023  mov     ecx, 85h
0x180028028  call    FileLogAllowEntry
0x18002802d  test    al, al
0x18002802f  jz      short loc_180028042
0x180028031  mov     edx, 0Ah
0x180028036  lea     rcx, aOnlyConsiderin; "Only considering the best %d clocks for"...
0x18002803d  call    FileLogAdd
0x180028042  mov     r10, qword ptr [rsp+118h+var_E8]
0x180028047  xor     esi, esi
0x180028049  mov     byte ptr [rsp+118h+arg_8], sil
0x180028051  or      r14, 0FFFFFFFFFFFFFFFFh
0x180028055  xor     edi, edi
0x180028057  mov     rbx, r10
0x18002805a  mov     rax, qword ptr [rsp+118h+var_E8+8]
0x18002805f  cmp     rbx, rax
0x180028062  jz      loc_180028197
0x180028068  mov     r9, [rbx+10h]
0x18002806c  mov     [rsp+118h+arg_18], r9
0x180028074  xor     ecx, ecx
0x180028076  cmp     rax, r10
0x180028079  jz      short loc_1800280A4
0x18002807b  mov     rdx, [rax-8]
0x18002807f  mov     r8, [rdx+250h]
0x180028086  sub     r8, [r9+250h]
0x18002808d  mov     rdx, r8
0x180028090  neg     rdx
0x180028093  cmovs   rdx, r8
0x180028097  imul    rdx, rdx
0x18002809b  add     rcx, rdx
0x18002809e  sub     rax, 18h
0x1800280a2  jmp     short loc_180028076
0x1800280a4  mov     rax, qword ptr [rsp+118h+var_E8+8]
0x1800280a9  sub     rax, r10
0x1800280ac  sar     rax, 3
0x1800280b0  imul    rax, r15
0x1800280b4  dec     rax
0x1800280b7  mov     r8d, 1
0x1800280bd  cmp     rax, r8
0x1800280c0  cmova   r8, rax
0x1800280c4  xor     edx, edx
0x1800280c6  mov     rax, rcx
0x1800280c9  div     r8
0x1800280cc  xorps   xmm0, xmm0
0x1800280cf  cvtsi2sd xmm0, rax; X
0x1800280d4  call    sqrt
0x1800280d9  xor     eax, eax
0x1800280db  comisd  xmm0, cs:__real@43e0000000000000
0x1800280e3  jb      short loc_180028104
0x1800280e5  subsd   xmm0, cs:__real@43e0000000000000
0x1800280ed  comisd  xmm0, cs:__real@43e0000000000000
0x1800280f5  jnb     short loc_180028104
0x1800280f7  mov     rcx, 8000000000000000h
0x180028101  mov     rax, rcx
0x180028104  cvttsd2si r13, xmm0
0x180028109  add     r13, rax
0x18002810c  cmp     rdi, r13
0x18002810f  ja      short loc_18002811C
0x180028111  mov     cl, 1
0x180028113  mov     byte ptr [rsp+118h+arg_8], cl
0x18002811a  jmp     short loc_18002811E
0x18002811c  xor     cl, cl
0x18002811e  mov     rax, rbx
0x180028121  test    cl, cl
0x180028123  cmovz   rax, rsi
0x180028127  mov     rsi, rax
0x18002812a  mov     rax, r13
0x18002812d  cmovz   rax, rdi
0x180028131  mov     rdi, rax
0x180028134  mov     rax, [rsp+118h+arg_18]
0x18002813c  mov     rax, [rax+248h]
0x180028143  cmp     r14, rax
0x180028146  cmovbe  rax, r14
0x18002814a  mov     r14, rax
0x18002814d  mov     ecx, 85h
0x180028152  call    FileLogAllowEntry
0x180028157  test    al, al
0x180028159  jz      short loc_180028189
0x18002815b  mov     rcx, [rsp+118h+arg_18]
0x180028163  mov     rax, [rcx+250h]
0x18002816a  mov     [rsp+118h+var_F8], rax
0x18002816f  mov     r9, [rcx+248h]
0x180028176  mov     r8, r13
0x180028179  mov     rdx, [rbx+8]
0x18002817d  lea     rcx, aSyncdistI64uSe; "  SyncDist:%I64u SelectJitter:%I64u Pee"...
0x180028184  call    FileLogAdd
0x180028189  add     rbx, 18h
0x18002818d  mov     r10, qword ptr [rsp+118h+var_E8]
0x180028192  jmp     loc_18002805A
0x180028197  mov     ecx, 85h
0x18002819c  call    FileLogAllowEntry
0x1800281a1  test    al, al
0x1800281a3  jz      short loc_1800281B7
0x1800281a5  mov     r8, r14
0x1800281a8  mov     rdx, rdi
0x1800281ab  lea     rcx, aMaxselectjitte; " MaxSelectJitter: %u MinPeerJitter: %u"...
0x1800281b2  call    FileLogAdd
0x1800281b7  cmp     rdi, r14
0x1800281ba  jbe     short loc_180028237
0x1800281bc  mov     rax, qword ptr [rsp+118h+var_E8+8]
0x1800281c1  sub     rax, qword ptr [rsp+118h+var_E8]
0x1800281c6  sar     rax, 3
0x1800281ca  imul    rax, r15
0x1800281ce  cmp     rax, 1
0x1800281d2  jbe     short loc_180028237
0x1800281d4  mov     ecx, 85h
0x1800281d9  call    FileLogAllowEntry
0x1800281de  test    al, al
0x1800281e0  jz      short loc_18002820A
0x1800281e2  lea     rcx, aDiscardingSamp; "Discarding Sample with offset: "
0x1800281e9  call    FileLogAdd
0x1800281ee  mov     rdx, [rsi+10h]
0x1800281f2  mov     rdx, [rdx+250h]
0x1800281f9  call    FileLogNtTimeOffsetEx
0x1800281fe  lea     rcx, asc_18007145C; "\n"
0x180028205  call    FileLogAppend
0x18002820a  cmp     byte ptr [rsp+118h+arg_8], 0
0x180028212  jz      loc_1800283BB
0x180028218  lea     rdx, [rsi+18h]; Src
0x18002821c  mov     r8, qword ptr [rsp+118h+var_E8+8]
0x180028221  sub     r8, rdx; Size
0x180028224  mov     rcx, rsi; void *
0x180028227  call    memmove_0
0x18002822c  sub     qword ptr [rsp+118h+var_E8+8], 18h
0x180028232  jmp     loc_180028042
0x180028237  lea     rcx, [rsp+118h+var_D0]
0x18002823c  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180028241  nop
0x180028242  mov     rbx, qword ptr [rsp+118h+var_E8]
0x180028247  mov     [rsp+118h+arg_18], rbx
0x18002824f  cmp     rbx, qword ptr [rsp+118h+var_E8+8]
0x180028254  jnz     loc_180028308
0x18002825a  mov     rax, [rsp+118h+var_B8]
0x18002825f  mov     rcx, [r12]
0x180028263  cmp     rcx, [rax]
0x180028266  jz      short loc_18002826B
0x180028268  mov     [rax], rcx
0x18002826b  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180028272  call    cs:__imp__set_se_translator
0x180028279  nop     dword ptr [rax+rax+00h]
0x18002827e  mov     [rsp+118h+arg_0], rax
0x180028286  mov     dword ptr [rsp+118h+arg_8], 0
0x180028291  mov     rax, qword ptr [rsp+118h+var_C8]
0x180028296  mov     [rsp+118h+arg_18], rax
0x18002829e  mov     r9, [rsp+118h+var_D0]
0x1800282a3  mov     [rsp+118h+arg_18], r9
0x1800282ab  mov     r8, [r12]
0x1800282af  mov     [rsp+118h+arg_18], r8
0x1800282b7  mov     [rsp+118h+var_F8], rax
0x1800282bc  lea     rdx, [rsp+118h+arg_18]
0x1800282c4  mov     rcx, r12
0x1800282c7  call    ??$insert@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UNtpTimeSample@@@std@@@std@@@std@@$0A@@?$vector@UNtpTimeSample@@V?$allocator@UNtpTimeSample@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UNtpTimeSample@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UNtpTimeSample@@@std@@@std@@@1@V21@1@Z; std::vector<NtpTimeSample>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<NtpTimeSample>>>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<NtpTimeSample>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<NtpTimeSample>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<NtpTimeSample>>>)
0x1800282cc  nop
0x1800282cd  jmp     short loc_1800282DD
0x1800282cf  jmp     short loc_1800282D3
0x1800282d1  jmp     short $+2
0x1800282d3  mov     r15, 0AAAAAAAAAAAAAAABh
0x1800282dd  mov     rcx, [rsp+118h+arg_0]
0x1800282e5  call    cs:__imp__set_se_translator
0x1800282ec  nop     dword ptr [rax+rax+00h]
0x1800282f1  cmp     dword ptr [rsp+118h+arg_8], 0
0x1800282f9  jl      short loc_180028379
0x1800282fb  mov     [rsp+118h+arg_10], 1
0x180028306  jmp     short loc_180028379
0x180028308  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18002830f  call    cs:__imp__set_se_translator
0x180028316  nop     dword ptr [rax+rax+00h]
0x18002831b  mov     [rsp+118h+var_B0], rax
0x180028320  mov     dword ptr [rsp+118h+arg_8], 0
0x18002832b  mov     rdx, [rbx+10h]
0x18002832f  lea     rcx, [rsp+118h+var_D0]
0x180028334  call    ??$_Emplace_one_at_back@AEBUNtpTimeSample@@@?$vector@UNtpTimeSample@@V?$allocator@UNtpTimeSample@@@std@@@std@@AEAAAEAUNtpTimeSample@@AEBU2@@Z; std::vector<NtpTimeSample>::_Emplace_one_at_back<NtpTimeSample const &>(NtpTimeSample const &)
0x180028339  nop
0x18002833a  jmp     short loc_18002835A
0x18002833c  jmp     short loc_180028340
0x18002833e  jmp     short $+2
0x180028340  mov     r15, 0AAAAAAAAAAAAAAABh
0x18002834a  mov     r12, [rsp+118h+arg_0]
0x180028352  mov     rbx, [rsp+118h+arg_18]
0x18002835a  mov     rcx, [rsp+118h+var_B0]
0x18002835f  call    cs:__imp__set_se_translator
0x180028366  nop     dword ptr [rax+rax+00h]
0x18002836b  cmp     dword ptr [rsp+118h+arg_8], 0
0x180028373  jge     loc_18002843E
0x180028379  mov     rcx, [rsp+118h+var_D0]
0x18002837e  test    rcx, rcx
0x180028381  jz      short loc_1800283BB
0x180028383  mov     rax, qword ptr [rsp+118h+var_C8+8]
0x180028388  sub     rax, rcx
0x18002838b  mov     rdx, 86BCA1AF286BCA1Bh
0x180028395  sar     rax, 5
0x180028399  imul    rax, rdx
0x18002839d  imul    rdx, rax, 260h
0x1800283a4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800283a9  xorps   xmm0, xmm0
0x1800283ac  mov     [rsp+118h+var_D0], 0
0x1800283b5  movdqu  [rsp+118h+var_C8], xmm0
0x1800283bb  mov     rcx, qword ptr [rsp+118h+var_E8]
0x1800283c0  test    rcx, rcx
0x1800283c3  jz      short loc_180028432
0x1800283c5  mov     rax, [rsp+118h+var_D8]
0x1800283ca  sub     rax, rcx
0x1800283cd  sar     rax, 3
0x1800283d1  imul    rax, r15
0x1800283d5  lea     rdx, [rax+rax*2]
0x1800283d9  shl     rdx, 3
0x1800283dd  mov     [rsp+118h+arg_0], rdx
0x1800283e5  mov     [rsp+118h+arg_8], rcx
0x1800283ed  cmp     rdx, 1000h
0x1800283f4  jb      short loc_18002841B
0x1800283f6  lea     rdx, [rsp+118h+arg_0]; unsigned __int64 *
0x1800283fe  lea     rcx, [rsp+118h+arg_8]; void **
0x180028406  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18002840b  mov     rdx, [rsp+118h+arg_0]; unsigned __int64
0x180028413  mov     rcx, [rsp+118h+arg_8]; void *
0x18002841b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028420  xorps   xmm0, xmm0
0x180028423  movdqu  [rsp+118h+var_E8], xmm0
0x180028429  mov     [rsp+118h+var_D8], 0
  ... truncated ...
```
