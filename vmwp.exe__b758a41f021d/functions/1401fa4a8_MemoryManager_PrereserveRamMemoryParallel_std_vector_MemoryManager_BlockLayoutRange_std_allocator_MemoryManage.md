# MemoryManager::PrereserveRamMemoryParallel(std::vector<MemoryManager::BlockLayoutRange,std::allocator<MemoryManager::BlockLayoutRange>> &,MemoryManager::ReserveMemoryPassQosFlags const *,int)

- ea: `0x1401fa4a8`
- end: `0x1401fab87`
- name: `?PrereserveRamMemoryParallel@MemoryManager@@AEAAXAEAV?$vector@VBlockLayoutRange@MemoryManager@@V?$allocator@VBlockLayoutRange@MemoryManager@@@std@@@std@@PEBUReserveMemoryPassQosFlags@1@H@Z`
- size: `1759`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: ``

## callers

- `0x140119164`

## callees

- `0x140024504`
- `0x14004f4d0`
- `0x1400690dc`
- `0x140073f70`
- `0x140082354`
- `0x1400823ec`
- `0x1400da040`
- `0x14011ea40`
- `0x1401281c8`
- `0x14012c0c0`
- `0x140161ed4`
- `0x1401877f4`
- `0x1401eed3c`
- `0x1401eee68`
- `0x1401f134c`
- `0x1401f19e4`
- `0x1401f23cc`
- `0x1401f81f8`
- `0x1401f8490`
- `0x1401fa4a8`
- `0x1401fe644`
- `0x140200214`
- `0x1402002d8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1401fa94f`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1401fa9d7`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1401fa94f`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1401fa9d7`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1401fa7e5`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1401fa976`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1401fa7e5`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1401fa976`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1401fa7f9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1401fa9f3`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1401fa7f9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1401fa9f3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1401fa7cd`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1401fa909`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1401fa7cd`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1401fa909`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MemoryManager::PrereserveRamMemoryParallel(
        MemoryManager *a1,
        __int64 *a2,
        __int64 a3,
        unsigned int a4)
{
  MemoryManager *v5; // r15
  char *v6; // r12
  char *v7; // r13
  unsigned __int8 VirtualNumaNodeCount; // al
  unsigned __int64 v9; // rbx
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  MemoryManager::ReserveRamMemoryContext *v12; // rbx
  __int64 v13; // r14
  __int64 v14; // rbx
  _QWORD *v15; // rsi
  int i; // r14d
  __int64 v17; // rdx
  char *v18; // r12
  unsigned __int8 j; // si
  __int64 v20; // r8
  char *v21; // rbx
  std::thread *v22; // rbx
  std::thread *v23; // rsi
  unsigned __int8 v24; // cl
  __int64 v25; // rbx
  MemoryManager::ReserveRamMemoryContext *v26; // rdx
  unsigned __int8 v27; // r14
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v30; // r9
  __int64 k; // r8
  __int64 v33; // rcx
  unsigned int v34; // eax
  const void *v35; // rax
  unsigned __int8 v36; // bl
  int v37; // r8d
  int v38; // r9d
  unsigned __int8 v39; // [rsp+40h] [rbp-128h] BYREF
  unsigned __int8 v40; // [rsp+41h] [rbp-127h]
  __int64 v41; // [rsp+48h] [rbp-120h] BYREF
  __int64 v42; // [rsp+50h] [rbp-118h] BYREF
  char *v43; // [rsp+58h] [rbp-110h]
  char *v44; // [rsp+60h] [rbp-108h]
  __int64 *v45; // [rsp+68h] [rbp-100h]
  __int64 *v46; // [rsp+70h] [rbp-F8h]
  _BYTE v47[12]; // [rsp+78h] [rbp-F0h] BYREF
  int v48; // [rsp+84h] [rbp-E4h]
  char *v49; // [rsp+88h] [rbp-E0h]
  MemoryManager *v50; // [rsp+90h] [rbp-D8h]
  __int64 *v51; // [rsp+98h] [rbp-D0h]
  void (__fastcall *v52)(MemoryManager *__hidden, void *); // [rsp+A0h] [rbp-C8h] BYREF
  int v53; // [rsp+A8h] [rbp-C0h]
  int v54; // [rsp+ACh] [rbp-BCh]
  _BYTE v55[16]; // [rsp+B0h] [rbp-B8h] BYREF
  MemoryManager::ReserveRamMemoryContext *v56[2]; // [rsp+C0h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-98h]
  void *v58[2]; // [rsp+D8h] [rbp-90h] BYREF
  __int64 v59; // [rsp+E8h] [rbp-80h]
  std::thread *v60[2]; // [rsp+F0h] [rbp-78h] BYREF
  __int64 v61; // [rsp+100h] [rbp-68h]
  __int128 v62; // [rsp+108h] [rbp-60h] BYREF
  __int128 v63; // [rsp+118h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v45 = a2;
  v5 = a1;
  v50 = a1;
  v51 = a2;
  *(_OWORD *)v58 = 0;
  v59 = 0;
  v6 = 0;
  v44 = 0;
  v7 = 0;
  v43 = 0;
  *(_OWORD *)v56 = 0;
  v57 = 0;
  VirtualNumaNodeCount = MemoryManager::GetVirtualNumaNodeCount(a1);
  v40 = VirtualNumaNodeCount;
  v41 = 0;
  v9 = VirtualNumaNodeCount;
  if ( VirtualNumaNodeCount )
  {
    if ( VirtualNumaNodeCount <= (unsigned __int64)((signed __int64)(v59 - (unsigned __int64)v58[0]) >> 3) )
      v58[1] = (void *)std::_Uninitialized_fill_n<std::allocator<unsigned __int64>>(v58[1]);
    else
      std::vector<unsigned char const *>::_Resize_reallocate<unsigned char const *>(v58, VirtualNumaNodeCount, &v41);
  }
  v10 = 0x2E8BA2E8BA2E8BA3LL;
  v11 = 0x2E8BA2E8BA2E8BA3LL * ((v56[1] - v56[0]) >> 3);
  if ( v9 >= v11 )
  {
    if ( v9 > v11 )
    {
      if ( v9 <= 0x2E8BA2E8BA2E8BA3LL * ((signed __int64)(v57 - (unsigned __int64)v56[0]) >> 3) )
        v56[1] = (MemoryManager::ReserveRamMemoryContext *)std::_Uninitialized_value_construct_n<std::allocator<MemoryManager::ReserveRamMemoryContext>>(v56[1]);
      else
        std::vector<MemoryManager::ReserveRamMemoryContext>::_Resize_reallocate<std::_Value_init_tag>(v56, v9);
    }
  }
  else
  {
    v12 = (MemoryManager::ReserveRamMemoryContext *)((char *)v56[0] + 88 * v9);
    std::_Destroy_range<std::allocator<MemoryManager::ReserveRamMemoryContext>>(v12);
    v56[1] = v12;
  }
  v46 = a2 + 1;
  v13 = a2[1];
  v14 = *a2;
  if ( *a2 != v13 )
  {
    do
    {
      if ( (*(_BYTE *)(v14 + 4) & 2) == 0 )
      {
        LOBYTE(v10) = *(_BYTE *)(v14 + 32);
        v15 = (_QWORD *)(v14 + 56);
        if ( (unsigned int)MemoryManager::GetPrimaryRamBackingType(v5, v10) )
        {
          *((_QWORD *)v5 + 23) -= *v15;
        }
        else
        {
          std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64>(
            (char *)v56[0] + 88 * *(unsigned __int8 *)(v14 + 32) + 32,
            v14 + 64);
          std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64>(
            (char *)v56[0] + 88 * *(unsigned __int8 *)(v14 + 32) + 8,
            v14 + 56);
          v10 = *(unsigned __int8 *)(v14 + 32);
          *((_QWORD *)v58[0] + v10) += *v15;
          v6 += *v15;
        }
      }
      v14 += 112;
    }
    while ( v14 != v13 );
    v44 = v6;
  }
  for ( i = 0; ; ++i )
  {
    LODWORD(v41) = i;
    v17 = a4;
    if ( i >= (int)a4 )
      break;
    v18 = (char *)v5 + 184;
    if ( !*((_QWORD *)v5 + 23) )
      break;
    v49 = (char *)v5 + 184;
    *(_OWORD *)v60 = 0;
    v61 = 0;
    for ( j = 0; ; ++j )
    {
      v39 = j;
      if ( j >= v40 )
        break;
      if ( *((_QWORD *)v58[0] + j) )
      {
        v20 = 88LL * j;
        v42 = v20;
        *((_BYTE *)v56[0] + v20) = i == (_DWORD)v17 - 1;
        *((_BYTE *)v56[0] + v20 + 1) = j;
        *(_QWORD *)((char *)v56[0] + v20 + 56) = 0;
        *(_DWORD *)((char *)v56[0] + v20 + 64) = *(_DWORD *)(a3 + 8LL * i);
        *(_DWORD *)((char *)v56[0] + v20 + 68) = *(_DWORD *)(a3 + 8LL * i + 4);
        v21 = (char *)v56[0] + v20;
        v63 = 0;
        __ExceptionPtrCreate(&v63);
        __ExceptionPtrAssign(v21 + 72, &v63);
        __ExceptionPtrDestroy(&v63);
        try
        {
          v42 += (__int64)v56[0];
          *(_QWORD *)&v63 = v5;
          v52 = MemoryManager::ReserveRamMemoryThreadRoutine;
          v53 = 0;
          v54 = v48;
          std::thread::_Start<void (MemoryManager::*)(void *),MemoryManager *,MemoryManager::ReserveRamMemoryContext *>(
            v55,
            &v52,
            &v63,
            &v42);
          std::vector<std::thread>::push_back(v60, v55);
          std::thread::~thread((std::thread *)v55);
          LODWORD(v17) = a4;
        }
        catch ( ... )
        {
          v35 = (const void *)std::current_exception(v47);
          v36 = v39;
          __ExceptionPtrAssign((char *)v56[0] + 88 * v39 + 72, v35);
          __ExceptionPtrDestroy(v47);
          if ( (unsigned int)dword_1403B5980 > 5 )
          {
            v39 = v36;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(
              (unsigned int)&dword_1403B5980,
              (unsigned int)&word_140359A8E,
              v37,
              v38,
              (__int64)&v39);
          }
          v7 = v43;
          i = v41;
          v18 = v49;
          v5 = v50;
          v45 = v51;
          break;
        }
      }
    }
    v22 = v60[0];
    v23 = v60[1];
    while ( v22 != v23 )
    {
      std::thread::join(v22);
      v22 = (std::thread *)((char *)v22 + 16);
    }
    std::vector<std::thread>::clear(v60);
    v62 = 0;
    __ExceptionPtrCreate(&v62);
    v24 = 0;
    v39 = 0;
    if ( v40 )
    {
      v25 = 0;
      v26 = v56[0];
      v27 = v40;
      do
      {
        if ( *((_QWORD *)v58[0] + v25) )
        {
          v28 = 88 * v25;
          if ( __ExceptionPtrToBool((char *)v26 + 88 * v25 + 72) )
            __ExceptionPtrAssign(&v62, (char *)v56[0] + v28 + 72);
          *((_QWORD *)v58[0] + v25) -= *(_QWORD *)((char *)v56[0] + v28 + 56);
          v26 = v56[0];
          v29 = *(_QWORD *)((char *)v56[0] + v28 + 56);
          v7 += v29;
          *(_QWORD *)v18 -= v29;
          v24 = v39;
        }
        v39 = ++v24;
        ++v25;
      }
      while ( v24 < v27 );
      v43 = v7;
      i = v41;
    }
    if ( __ExceptionPtrToBool(&v62) )
    {
      v33 = std::exception_ptr::exception_ptr((std::exception_ptr *)v47, (const struct std::exception_ptr *)&v62);
      std::rethrow_exception(v33);
LABEL_52:
      MemoryManager::TraceLoggingReserveMemoryFailure(v5, 2, v18, v7, -2147023446);
      v34 = wil::verify_hresult<long>(2147943850LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x1059,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)v34,
        (int)"PageCountToReserve = %I64u, PageCountReserved = %I64u",
        v18,
        v7);
    }
    __ExceptionPtrDestroy(&v62);
    if ( v60[0] )
    {
      std::_Destroy_range<std::allocator<std::thread>>(v60[0]);
      std::_Deallocate<16>(v60[0], (v61 - (unsigned __int64)v60[0]) & 0xFFFFFFFFFFFFFFF0uLL);
    }
  }
  v18 = v44;
  if ( v44 != v7 )
    goto LABEL_52;
  v30 = *v46;
  for ( k = *v45; k != v30; k += 112 )
  {
    if ( (*(_BYTE *)(k + 4) & 2) == 0 )
    {
      LOBYTE(v17) = *(_BYTE *)(k + 32);
      if ( !(unsigned int)MemoryManager::GetPrimaryRamBackingType(v5, v17) )
        *(_QWORD *)(k + 72) = *(_QWORD *)(k + 56);
    }
  }
  if ( v56[0] )
  {
    std::_Destroy_range<std::allocator<MemoryManager::ReserveRamMemoryContext>>(v56[0]);
    std::_Deallocate<16>(v56[0], 8 * ((signed __int64)(v57 - (unsigned __int64)v56[0]) >> 3));
    *(_OWORD *)v56 = 0;
    v57 = 0;
  }
  return std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>(v58);
}

```

## disassembly

```asm
0x1401fa4a8  mov     r11, rsp
0x1401fa4ab  mov     [r11+20h], r9d
0x1401fa4af  mov     [r11+18h], r8
0x1401fa4b3  push    rbx
0x1401fa4b4  push    rsi
0x1401fa4b5  push    r12
0x1401fa4b7  push    r13
0x1401fa4b9  push    r14
0x1401fa4bb  push    r15
0x1401fa4bd  sub     rsp, 138h
0x1401fa4c4  mov     rax, cs:__security_cookie
0x1401fa4cb  xor     rax, rsp
0x1401fa4ce  mov     [rsp+168h+var_40], rax
0x1401fa4d6  mov     rsi, rdx
0x1401fa4d9  mov     [rsp+168h+var_100], rdx
0x1401fa4de  mov     r15, rcx
0x1401fa4e1  mov     [rsp+168h+var_D8], rcx
0x1401fa4e9  mov     [rsp+168h+var_D0], rdx
0x1401fa4f1  xor     eax, eax
0x1401fa4f3  xorps   xmm1, xmm1
0x1401fa4f6  movdqu  xmmword ptr [rsp+168h+var_90], xmm1
0x1401fa4ff  mov     [r11-80h], rax
0x1401fa503  xor     r12d, r12d
0x1401fa506  mov     [rsp+168h+var_108], r12
0x1401fa50b  xor     r13d, r13d
0x1401fa50e  mov     [rsp+168h+var_110], r13
0x1401fa513  movdqu  xmmword ptr [rsp+168h+var_A8], xmm1
0x1401fa51c  mov     [r11-98h], rax
0x1401fa523  call    ?GetVirtualNumaNodeCount@MemoryManager@@AEBAEXZ; MemoryManager::GetVirtualNumaNodeCount(void)
0x1401fa528  mov     [rsp+168h+var_127], al
0x1401fa52c  mov     [rsp+168h+var_120], r13
0x1401fa531  movzx   ebx, al
0x1401fa534  mov     rdx, [rsp+168h+var_90]
0x1401fa53c  mov     rcx, [rsp+168h+var_90+8]
0x1401fa544  sub     rcx, rdx
0x1401fa547  sar     rcx, 3
0x1401fa54b  cmp     rbx, rcx
0x1401fa54e  jnb     short loc_1401FA55E
0x1401fa550  lea     rcx, [rdx+rbx*8]
0x1401fa554  mov     [rsp+168h+var_90+8], rcx
0x1401fa55c  jmp     short loc_1401FA5A3
0x1401fa55e  jbe     short loc_1401FA5A3
0x1401fa560  mov     rax, [rsp+168h+var_80]
0x1401fa568  sub     rax, rdx
0x1401fa56b  sar     rax, 3
0x1401fa56f  lea     r8, [rsp+168h+var_120]
0x1401fa574  mov     rdx, rbx
0x1401fa577  cmp     rbx, rax
0x1401fa57a  jbe     short loc_1401FA58B
0x1401fa57c  lea     rcx, [rsp+168h+var_90]
0x1401fa584  call    ??$_Resize_reallocate@PEBE@?$vector@PEBEV?$allocator@PEBE@std@@@std@@AEAAX_KAEBQEBE@Z; std::vector<uchar const *>::_Resize_reallocate<uchar const *>(unsigned __int64,uchar const * const &)
0x1401fa589  jmp     short loc_1401FA5A3
0x1401fa58b  sub     rdx, rcx
0x1401fa58e  mov     rcx, [rsp+168h+var_90+8]; void *
0x1401fa596  call    ??$_Uninitialized_fill_n@V?$allocator@_K@std@@@std@@YAPEA_KPEA_K_KAEB_KAEAV?$allocator@_K@0@@Z; std::_Uninitialized_fill_n<std::allocator<unsigned __int64>>(unsigned __int64 *,unsigned __int64,unsigned __int64 const &,std::allocator<unsigned __int64> &)
0x1401fa59b  mov     [rsp+168h+var_90+8], rax
0x1401fa5a3  mov     r8, [rsp+168h+var_A8]
0x1401fa5ab  mov     r9, [rsp+168h+var_A8+8]
0x1401fa5b3  mov     rcx, r9
0x1401fa5b6  sub     rcx, r8
0x1401fa5b9  sar     rcx, 3
0x1401fa5bd  mov     rdx, 2E8BA2E8BA2E8BA3h
0x1401fa5c7  imul    rcx, rdx
0x1401fa5cb  cmp     rbx, rcx
0x1401fa5ce  jnb     short loc_1401FA5EC
0x1401fa5d0  imul    rbx, 58h ; 'X'
0x1401fa5d4  add     rbx, r8
0x1401fa5d7  mov     rdx, r9
0x1401fa5da  mov     rcx, rbx; this
0x1401fa5dd  call    ??$_Destroy_range@V?$allocator@UReserveRamMemoryContext@MemoryManager@@@std@@@std@@YAXPEAUReserveRamMemoryContext@MemoryManager@@QEAU12@AEAV?$allocator@UReserveRamMemoryContext@MemoryManager@@@0@@Z; std::_Destroy_range<std::allocator<MemoryManager::ReserveRamMemoryContext>>(MemoryManager::ReserveRamMemoryContext *,MemoryManager::ReserveRamMemoryContext * const,std::allocator<MemoryManager::ReserveRamMemoryContext> &)
0x1401fa5e2  mov     [rsp+168h+var_A8+8], rbx
0x1401fa5ea  jmp     short loc_1401FA62E
0x1401fa5ec  jbe     short loc_1401FA62E
0x1401fa5ee  mov     rax, [rsp+168h+var_98]
0x1401fa5f6  sub     rax, r8
0x1401fa5f9  sar     rax, 3
0x1401fa5fd  imul    rax, rdx
0x1401fa601  cmp     rbx, rax
0x1401fa604  jbe     short loc_1401FA618
0x1401fa606  mov     rdx, rbx
0x1401fa609  lea     rcx, [rsp+168h+var_A8]
0x1401fa611  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UReserveRamMemoryContext@MemoryManager@@V?$allocator@UReserveRamMemoryContext@MemoryManager@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<MemoryManager::ReserveRamMemoryContext>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1401fa616  jmp     short loc_1401FA62E
0x1401fa618  sub     rbx, rcx
0x1401fa61b  mov     rdx, rbx
0x1401fa61e  mov     rcx, r9; this
0x1401fa621  call    ??$_Uninitialized_value_construct_n@V?$allocator@UReserveRamMemoryContext@MemoryManager@@@std@@@std@@YAPEAUReserveRamMemoryContext@MemoryManager@@PEAU12@_KAEAV?$allocator@UReserveRamMemoryContext@MemoryManager@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<MemoryManager::ReserveRamMemoryContext>>(MemoryManager::ReserveRamMemoryContext *,unsigned __int64,std::allocator<MemoryManager::ReserveRamMemoryContext> &)
0x1401fa626  mov     [rsp+168h+var_A8+8], rax
0x1401fa62e  lea     rax, [rsi+8]
0x1401fa632  mov     [rsp+168h+var_F8], rax
0x1401fa637  mov     r14, [rax]
0x1401fa63a  mov     rbx, [rsi]
0x1401fa63d  cmp     rbx, r14
0x1401fa640  jz      loc_1401FA6D2
0x1401fa646  test    byte ptr [rbx+4], 2
0x1401fa64a  jnz     short loc_1401FA6C0
0x1401fa64c  mov     dl, [rbx+20h]
0x1401fa64f  mov     rcx, r15
0x1401fa652  call    ?GetPrimaryRamBackingType@MemoryManager@@AEBA?AW4MemoryBackingType@Compute@Resources@VirtualMachines@Schema@@E@Z; MemoryManager::GetPrimaryRamBackingType(uchar)
0x1401fa657  lea     rsi, [rbx+38h]
0x1401fa65b  test    eax, eax
0x1401fa65d  jz      short loc_1401FA66B
0x1401fa65f  mov     rax, [rsi]
0x1401fa662  sub     [r15+0B8h], rax
0x1401fa669  jmp     short loc_1401FA6C0
0x1401fa66b  lea     rdx, [rbx+40h]
0x1401fa66f  movzx   eax, byte ptr [rbx+20h]
0x1401fa673  imul    rcx, rax, 58h ; 'X'
0x1401fa677  mov     rax, [rsp+168h+var_A8]
0x1401fa67f  add     rax, 20h ; ' '
0x1401fa683  add     rcx, rax
0x1401fa686  call    ??$_Emplace_one_at_back@_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAAEA_K$$QEA_K@Z; std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64>(unsigned __int64 &&)
0x1401fa68b  movzx   eax, byte ptr [rbx+20h]
0x1401fa68f  imul    rcx, rax, 58h ; 'X'
0x1401fa693  mov     rax, [rsp+168h+var_A8]
0x1401fa69b  add     rax, 8
0x1401fa69f  add     rcx, rax
0x1401fa6a2  mov     rdx, rsi
0x1401fa6a5  call    ??$_Emplace_one_at_back@_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAAEA_K$$QEA_K@Z; std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64>(unsigned __int64 &&)
0x1401fa6aa  movzx   edx, byte ptr [rbx+20h]
0x1401fa6ae  mov     rcx, [rsp+168h+var_90]
0x1401fa6b6  mov     rax, [rsi]
0x1401fa6b9  add     [rcx+rdx*8], rax
0x1401fa6bd  add     r12, [rsi]
0x1401fa6c0  add     rbx, 70h ; 'p'
0x1401fa6c4  cmp     rbx, r14
0x1401fa6c7  jnz     loc_1401FA646
0x1401fa6cd  mov     [rsp+168h+var_108], r12
0x1401fa6d2  xor     r14d, r14d
0x1401fa6d5  mov     dword ptr [rsp+168h+var_120], r14d
0x1401fa6da  mov     edx, [rsp+168h+arg_18]
0x1401fa6e1  cmp     r14d, edx
0x1401fa6e4  jge     loc_1401FAA3E
0x1401fa6ea  lea     r12, [r15+0B8h]
0x1401fa6f1  cmp     qword ptr [r12], 0
0x1401fa6f6  jz      loc_1401FAA3E
0x1401fa6fc  mov     [rsp+168h+var_E0], r12
0x1401fa704  xor     eax, eax
0x1401fa706  xorps   xmm1, xmm1
0x1401fa709  movdqu  xmmword ptr [rsp+168h+var_78], xmm1
0x1401fa712  mov     [rsp+168h+var_68], rax
0x1401fa71a  xor     sil, sil
0x1401fa71d  mov     [rsp+168h+var_128], sil
0x1401fa722  cmp     sil, [rsp+168h+var_127]
0x1401fa727  jnb     loc_1401FA8C5
0x1401fa72d  movzx   ecx, sil
0x1401fa731  mov     rax, [rsp+168h+var_90]
0x1401fa739  cmp     qword ptr [rax+rcx*8], 0
0x1401fa73e  jz      loc_1401FA896
0x1401fa744  imul    r8, rcx, 58h ; 'X'
0x1401fa748  mov     [rsp+168h+var_118], r8
0x1401fa74d  lea     eax, [rdx-1]
0x1401fa750  cmp     r14d, eax
0x1401fa753  setz    cl
0x1401fa756  mov     rax, [rsp+168h+var_A8]
0x1401fa75e  mov     [rax+r8], cl
0x1401fa762  mov     rax, [rsp+168h+var_A8]
0x1401fa76a  mov     [rax+r8+1], sil
0x1401fa76f  mov     rax, [rsp+168h+var_A8]
0x1401fa777  mov     qword ptr [rax+r8+38h], 0
0x1401fa780  movsxd  rdx, r14d
0x1401fa783  mov     r9, [rsp+168h+arg_10]
0x1401fa78b  mov     ecx, [r9+rdx*8]
0x1401fa78f  mov     rax, [rsp+168h+var_A8]
0x1401fa797  mov     [rax+r8+40h], ecx
0x1401fa79c  mov     ecx, [r9+rdx*8+4]
0x1401fa7a1  mov     rax, [rsp+168h+var_A8]
0x1401fa7a9  mov     [rax+r8+44h], ecx
0x1401fa7ae  mov     rbx, [rsp+168h+var_A8]
0x1401fa7b6  add     rbx, r8
0x1401fa7b9  xorps   xmm0, xmm0
0x1401fa7bc  movdqu  [rsp+168h+var_50], xmm0
0x1401fa7c5  lea     rcx, [rsp+168h+var_50]
0x1401fa7cd  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1401fa7d4  nop     dword ptr [rax+rax+00h]
0x1401fa7d9  lea     rdx, [rsp+168h+var_50]
0x1401fa7e1  lea     rcx, [rbx+48h]
0x1401fa7e5  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1401fa7ec  nop     dword ptr [rax+rax+00h]
0x1401fa7f1  lea     rcx, [rsp+168h+var_50]
0x1401fa7f9  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1401fa800  nop     dword ptr [rax+rax+00h]
0x1401fa805  nop
0x1401fa806  mov     rcx, [rsp+168h+var_118]
0x1401fa80b  add     rcx, [rsp+168h+var_A8]
0x1401fa813  mov     [rsp+168h+var_118], rcx
0x1401fa818  mov     qword ptr [rsp+168h+var_50], r15
0x1401fa820  lea     rax, ?ReserveRamMemoryThreadRoutine@MemoryManager@@AEAAXPEAX@Z; MemoryManager::ReserveRamMemoryThreadRoutine(void *)
0x1401fa827  mov     [rsp+168h+var_C8], rax
0x1401fa82f  mov     [rsp+168h+var_C0], 0
0x1401fa83a  mov     eax, [rsp+168h+var_E4]
0x1401fa841  mov     [rsp+168h+var_BC], eax
0x1401fa848  lea     r9, [rsp+168h+var_118]
0x1401fa84d  lea     r8, [rsp+168h+var_50]
0x1401fa855  lea     rdx, [rsp+168h+var_C8]
0x1401fa85d  lea     rcx, [rsp+168h+var_B8]
0x1401fa865  call    ??$_Start@P8MemoryManager@@EAAXPEAX@ZPEAV1@PEAUReserveRamMemoryContext@1@@thread@std@@AEAAX$$QEAP8MemoryManager@@EAAXPEAX@Z$$QEAPEAV2@$$QEAPEAUReserveRamMemoryContext@2@@Z; std::thread::_Start<void (MemoryManager::*)(void *),MemoryManager *,MemoryManager::ReserveRamMemoryContext *>(void (MemoryManager::*&&)(void *),MemoryManager * &&,MemoryManager::ReserveRamMemoryContext * &&)
0x1401fa86a  nop
0x1401fa86b  lea     rdx, [rsp+168h+var_B8]
0x1401fa873  lea     rcx, [rsp+168h+var_78]
0x1401fa87b  call    ?push_back@?$vector@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@QEAAX$$QEAVthread@2@@Z; std::vector<std::thread>::push_back(std::thread &&)
0x1401fa880  nop
0x1401fa881  lea     rcx, [rsp+168h+var_B8]; this
0x1401fa889  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x1401fa88e  nop
0x1401fa88f  mov     edx, [rsp+168h+arg_18]
0x1401fa896  inc     sil
0x1401fa899  jmp     loc_1401FA71D
0x1401fa89e  mov     r13, [rsp+168h+var_110]
0x1401fa8a3  mov     r14d, dword ptr [rsp+168h+var_120]
0x1401fa8a8  mov     r12, [rsp+168h+var_E0]
0x1401fa8b0  mov     r15, [rsp+168h+var_D8]
0x1401fa8b8  mov     rax, [rsp+168h+var_D0]
0x1401fa8c0  mov     [rsp+168h+var_100], rax
0x1401fa8c5  mov     rbx, [rsp+168h+var_78]
0x1401fa8cd  mov     rsi, [rsp+168h+var_78+8]
0x1401fa8d5  jmp     short loc_1401FA8E3
0x1401fa8d7  mov     rcx, rbx; this
0x1401fa8da  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x1401fa8df  add     rbx, 10h
0x1401fa8e3  cmp     rbx, rsi
0x1401fa8e6  jnz     short loc_1401FA8D7
0x1401fa8e8  lea     rcx, [rsp+168h+var_78]
0x1401fa8f0  call    ?clear@?$vector@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@QEAAXXZ; std::vector<std::thread>::clear(void)
0x1401fa8f5  xorps   xmm1, xmm1
0x1401fa8f8  movdqu  [rsp+168h+var_60], xmm1
0x1401fa901  lea     rcx, [rsp+168h+var_60]
0x1401fa909  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1401fa910  nop     dword ptr [rax+rax+00h]
0x1401fa915  nop
0x1401fa916  xor     cl, cl
0x1401fa918  mov     [rsp+168h+var_128], cl
0x1401fa91c  cmp     [rsp+168h+var_127], cl
0x1401fa920  jbe     loc_1401FA9CF
0x1401fa926  xor     ebx, ebx
0x1401fa928  mov     rdx, [rsp+168h+var_A8]
0x1401fa930  mov     r14b, [rsp+168h+var_127]
0x1401fa935  mov     rax, [rsp+168h+var_90]
0x1401fa93d  cmp     qword ptr [rax+rbx*8], 0
0x1401fa942  jz      short loc_1401FA9B3
0x1401fa944  imul    rsi, rbx, 58h ; 'X'
0x1401fa948  lea     rcx, [rdx+48h]
0x1401fa94c  add     rcx, rsi
0x1401fa94f  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1401fa956  nop     dword ptr [rax+rax+00h]
0x1401fa95b  test    al, al
0x1401fa95d  jz      short loc_1401FA982
0x1401fa95f  mov     rdx, [rsp+168h+var_A8]
0x1401fa967  add     rdx, 48h ; 'H'
0x1401fa96b  add     rdx, rsi
0x1401fa96e  lea     rcx, [rsp+168h+var_60]
0x1401fa976  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1401fa97d  nop     dword ptr [rax+rax+00h]
0x1401fa982  mov     rdx, [rsp+168h+var_90]
0x1401fa98a  mov     rax, [rsp+168h+var_A8]
0x1401fa992  mov     rcx, [rsi+rax+38h]
0x1401fa997  sub     [rdx+rbx*8], rcx
0x1401fa99b  mov     rdx, [rsp+168h+var_A8]
0x1401fa9a3  mov     rax, [rsi+rdx+38h]
0x1401fa9a8  add     r13, rax
0x1401fa9ab  sub     [r12], rax
0x1401fa9af  mov     cl, [rsp+168h+var_128]
0x1401fa9b3  inc     cl
0x1401fa9b5  mov     [rsp+168h+var_128], cl
0x1401fa9b9  inc     rbx
0x1401fa9bc  cmp     cl, r14b
0x1401fa9bf  jb      loc_1401FA935
0x1401fa9c5  mov     [rsp+168h+var_110], r13
0x1401fa9ca  mov     r14d, dword ptr [rsp+168h+var_120]
0x1401fa9cf  lea     rcx, [rsp+168h+var_60]
0x1401fa9d7  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1401fa9de  nop     dword ptr [rax+rax+00h]
0x1401fa9e3  test    al, al
0x1401fa9e5  jnz     loc_1401FAB16
0x1401fa9eb  lea     rcx, [rsp+168h+var_60]
0x1401fa9f3  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1401fa9fa  nop     dword ptr [rax+rax+00h]
0x1401fa9ff  nop
0x1401faa00  mov     rcx, [rsp+168h+var_78]; this
0x1401faa08  test    rcx, rcx
0x1401faa0b  jz      short loc_1401FAA36
0x1401faa0d  mov     rdx, [rsp+168h+var_78+8]
0x1401faa15  call    ??$_Destroy_range@V?$allocator@Vthread@std@@@std@@@std@@YAXPEAVthread@0@QEAV10@AEAV?$allocator@Vthread@std@@@0@@Z; std::_Destroy_range<std::allocator<std::thread>>(std::thread *,std::thread * const,std::allocator<std::thread> &)
0x1401faa1a  mov     rcx, [rsp+168h+var_78]
0x1401faa22  mov     rdx, [rsp+168h+var_68]
0x1401faa2a  sub     rdx, rcx
0x1401faa2d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1401faa31  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1401faa36  inc     r14d
0x1401faa39  jmp     loc_1401FA6D5
0x1401faa3e  mov     r12, [rsp+168h+var_108]
0x1401faa43  cmp     r12, r13
0x1401faa46  jnz     loc_1401FAB31
0x1401faa4c  mov     r9, [rsp+168h+var_F8]
0x1401faa51  mov     r9, [r9]
0x1401faa54  mov     r8, [rsp+168h+var_100]
0x1401faa59  mov     r8, [r8]
0x1401faa5c  jmp     short loc_1401FAA81
0x1401faa5e  test    byte ptr [r8+4], 2
0x1401faa63  jnz     short loc_1401FAA7D
  ... truncated ...
```
