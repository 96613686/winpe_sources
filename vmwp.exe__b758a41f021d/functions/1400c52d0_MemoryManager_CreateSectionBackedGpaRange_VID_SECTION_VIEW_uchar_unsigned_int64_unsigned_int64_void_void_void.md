# MemoryManager::CreateSectionBackedGpaRange(_VID_SECTION_VIEW *,uchar,unsigned __int64,unsigned __int64,void * *,void * *,void * *)

- ea: `0x1400c52d0`
- end: `0x1400c572f`
- name: `?CreateSectionBackedGpaRange@MemoryManager@@UEAAJPEAU_VID_SECTION_VIEW@@E_K1PEAPEAX22@Z`
- size: `1119`
- prototype: `__int64 __fastcall(MemoryManager *__hidden this, struct _VID_SECTION_VIEW *, unsigned __int8, unsigned __int64, unsigned __int64, void **, void **, void **)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140022888`
- `0x140033514`
- `0x140033d44`
- `0x140035238`
- `0x140035c9c`
- `0x1400364a0`
- `0x140039e50`
- `0x14003d338`
- `0x14003d3a4`
- `0x14003d828`
- `0x140045004`
- `0x14004a6bc`
- `0x14004aaa4`
- `0x14004ce28`
- `0x14004e724`
- `0x1400526c0`
- `0x1400545bc`
- `0x14005551c`
- `0x140083990`
- `0x1400ba144`
- `0x1400c52d0`
- `0x1400c5738`
- `0x14011ea40`
- `0x14011f6fc`
- `0x140204ef0`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400c5696`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400c5696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400c534e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400c534e`
- `vid!VidCreateVaGpaRange` at `0x1400c5550`
- `vid!VidCreateVaGpaRange` at `0x1400c5550`

## string_xrefs

- `0x1400c5666`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x1400c53a1`: `CreateSectionBackedGpaRange`
- `0x1400c56b5`: `Failed to create section. HR=%d.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MemoryManager::CreateSectionBackedGpaRange(
        struct IVidPartitionManager **this,
        struct _VID_SECTION_VIEW *a2,
        char a3,
        __int64 a4,
        unsigned __int64 a5,
        void **a6,
        void **a7,
        void **a8)
{
  volatile signed __int32 *v11; // rbx
  DWORD CurrentThreadId; // esi
  __int64 v13; // r8
  unsigned __int32 v14; // eax
  unsigned __int32 v15; // edx
  struct MemoryBlock *MemoryBlock; // rsi
  void *v17; // r14
  const char *v18; // r9
  void *v19; // rcx
  unsigned int v21; // [rsp+20h] [rbp-368h]
  __int64 v23; // [rsp+44h] [rbp-344h] BYREF
  struct MemoryBlock *v24; // [rsp+50h] [rbp-338h]
  MemoryManager *v25; // [rsp+58h] [rbp-330h]
  _QWORD v26[2]; // [rsp+60h] [rbp-328h] BYREF
  void **v27; // [rsp+70h] [rbp-318h]
  __int128 v28; // [rsp+80h] [rbp-308h] BYREF
  volatile signed __int32 *v29; // [rsp+90h] [rbp-2F8h]
  _BYTE v30[32]; // [rsp+98h] [rbp-2F0h] BYREF
  void *v31; // [rsp+B8h] [rbp-2D0h] BYREF
  _QWORD v32[8]; // [rsp+C0h] [rbp-2C8h] BYREF
  char v33; // [rsp+101h] [rbp-287h]
  __int64 v34; // [rsp+110h] [rbp-278h]
  __int128 v35; // [rsp+118h] [rbp-270h]
  __int64 v36; // [rsp+128h] [rbp-260h]
  __int64 v37; // [rsp+130h] [rbp-258h]
  _BYTE v38[80]; // [rsp+140h] [rbp-248h] BYREF
  struct _GUID v39; // [rsp+190h] [rbp-1F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v25 = (MemoryManager *)this;
  v37 = a4;
  v27 = a7;
  v26[0] = a8;
  v24 = 0;
  v31 = (void *)-1LL;
  v11 = (volatile signed __int32 *)(this + 88);
  CurrentThreadId = GetCurrentThreadId();
  v14 = _InterlockedCompareExchange(v11, 1, 0);
  if ( v14 )
  {
    if ( *((_DWORD *)v11 + 1) == CurrentThreadId )
    {
      _InterlockedAdd(v11 + 2, 1u);
      goto LABEL_8;
    }
    do
    {
      while ( (v14 & 1) != 0 || v14 >= 4 )
      {
        LOBYTE(v13) = 1;
        if ( !(unsigned int)RrwpLockWait(v11, 0xFFFFFFFFLL, v13) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x2FE,
            (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
            (const char *)0x102,
            v21);
        _m_prefetchw((const void *)v11);
        v14 = *v11;
      }
      v15 = v14;
      v14 = _InterlockedCompareExchange(v11, v14 + 1, v14);
    }
    while ( v14 != v15 );
  }
  _InterlockedExchange(v11 + 1, CurrentThreadId);
LABEL_8:
  v29 = v11;
  std::wstring::wstring(v30, L"CreateSectionBackedGpaRange");
  v28 = *(_OWORD *)(*(__int64 (__fastcall **)(__int64))(*((_QWORD *)this[4] + 2) + 16LL))((__int64)this[4] + 16);
  MemoryTraceTracker::MemoryTraceTracker(v38, &v28, v30, 0);
  std::wstring::_Tidy_deallocate(v30);
  memset_0(v32, 0, 0x70u);
  v32[0] = a5;
  v32[1] = a5;
  v32[2] = 8;
  v33 = a3;
  v35 = *(_OWORD *)a2;
  v36 = *((_QWORD *)a2 + 2);
  if ( a6 )
    v34 = (__int64)*a6;
  MemoryBlock = (struct MemoryBlock *)MemoryBlock::CreateMemoryBlock(this[2], v32, 0, 0, 0, 0, v38);
  v24 = MemoryBlock;
  v17 = (void *)*((_QWORD *)MemoryBlock + 19);
  MemoryBlock::NotificationHandlerRegister(MemoryBlock, this[3], (struct MemoryNotificationsCallback *)(this + 9));
  memset_0(&v39, 0, 0x1B0u);
  MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>(&v39, v38);
  v23 = 0;
  MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Start<int,unsigned __int64 &,unsigned __int64 &,int>(
    &v39,
    (__int64)&v23);
  if ( !(unsigned int)VidCreateVaGpaRange(this[2], a4, a5, v17, 0, &v31) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1F45,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      v18);
  MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Stop(&v39);
  MemoryTraceTracker::IncreaseTimeSpentInOperation(v38, &off_1402CE750);
  MemoryTraceTracker::Complete((MemoryTraceTracker *)v38);
  MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::~MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>(&v39);
  MemoryTraceTracker::~MemoryTraceTracker((MemoryTraceTracker *)v38);
  (*(void (__fastcall **)(struct IVidPartitionManager *))(*(_QWORD *)this[3] + 216LL))(this[3]);
  MemoryBlockContainer::Insert(this[20], MemoryBlock);
  *v27 = v17;
  v19 = v31;
  *(_QWORD *)v26[0] = v31;
  if ( a6 )
    *a6 = (void *)*((_QWORD *)MemoryBlock + 30);
  v26[0] = a4;
  v26[1] = v19;
  std::_Tree<std::_Tmap_traits<unsigned __int64,void *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,void *>>,0>>::_Emplace<std::pair<unsigned __int64,void *>>(
    this + 94,
    &v28,
    v26);
  RrwLockRelease(v11);
  return 0;
}

```

## disassembly

```asm
0x1400c52d0  push    rbx
0x1400c52d2  push    rsi
0x1400c52d3  push    rdi
0x1400c52d4  push    r12
0x1400c52d6  push    r13
0x1400c52d8  push    r14
0x1400c52da  push    r15
0x1400c52dc  sub     rsp, 350h
0x1400c52e3  mov     rax, cs:__security_cookie
0x1400c52ea  xor     rax, rsp
0x1400c52ed  mov     [rsp+388h+var_48], rax
0x1400c52f5  mov     r13, r9
0x1400c52f8  mov     [rsp+388h+var_348], r8b
0x1400c52fd  mov     r14, rdx
0x1400c5300  mov     rdi, rcx
0x1400c5303  mov     [rsp+388h+var_330], rcx
0x1400c5308  mov     [rsp+388h+var_258], r9
0x1400c5310  mov     r15, [rsp+388h+arg_28]
0x1400c5318  mov     rax, [rsp+388h+arg_30]
0x1400c5320  mov     [rsp+388h+var_318], rax
0x1400c5325  mov     rax, [rsp+388h+arg_38]
0x1400c532d  mov     [rsp+388h+var_328], rax
0x1400c5332  mov     [rsp+388h+var_338], 0
0x1400c533b  mov     [rsp+388h+var_2D0], 0FFFFFFFFFFFFFFFFh
0x1400c5347  lea     rbx, [rcx+2C0h]
0x1400c534e  call    cs:__imp_GetCurrentThreadId
0x1400c5355  nop     dword ptr [rax+rax+00h]
0x1400c535a  mov     esi, eax
0x1400c535c  xor     eax, eax
0x1400c535e  lea     r12d, [rax+1]
0x1400c5362  lock cmpxchg [rbx], r12d
0x1400c5367  jz      short loc_1400C5396
0x1400c5369  mov     ecx, [rbx+4]
0x1400c536c  cmp     ecx, esi
0x1400c536e  jnz     short loc_1400C5377
0x1400c5370  lock add [rbx+8], r12d
0x1400c5375  jmp     short loc_1400C5399
0x1400c5377  test    r12b, al
0x1400c537a  jnz     loc_1400C5642
0x1400c5380  cmp     eax, 4
0x1400c5383  jnb     loc_1400C5642
0x1400c5389  mov     edx, eax
0x1400c538b  lea     ecx, [rax+1]
0x1400c538e  lock cmpxchg [rbx], ecx
0x1400c5392  cmp     eax, edx
0x1400c5394  jnz     short loc_1400C5377
0x1400c5396  xchg    esi, [rbx+4]
0x1400c5399  mov     [rsp+388h+var_2F8], rbx
0x1400c53a1  lea     rdx, aCreatesectionb; "CreateSectionBackedGpaRange"
0x1400c53a8  lea     rcx, [rsp+388h+var_2F0]
0x1400c53b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400c53b5  nop
0x1400c53b6  mov     rcx, [rdi+20h]
0x1400c53ba  add     rcx, 10h
0x1400c53be  mov     rax, [rcx]
0x1400c53c1  mov     rax, [rax+10h]
0x1400c53c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c53ca  movups  xmm0, xmmword ptr [rax]
0x1400c53cd  movdqu  [rsp+388h+var_308], xmm0
0x1400c53d6  xor     r9d, r9d
0x1400c53d9  lea     r8, [rsp+388h+var_2F0]
0x1400c53e1  lea     rdx, [rsp+388h+var_308]
0x1400c53e9  lea     rcx, [rsp+388h+var_248]
0x1400c53f1  call    ??0MemoryTraceTracker@@QEAA@U_GUID@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU1@@Z; MemoryTraceTracker::MemoryTraceTracker(_GUID,std::wstring &&,_GUID const *)
0x1400c53f6  nop
0x1400c53f7  lea     rcx, [rsp+388h+var_2F0]
0x1400c53ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400c5404  xor     edx, edx; Val
0x1400c5406  lea     r8d, [rdx+70h]; Size
0x1400c540a  lea     rcx, [rsp+388h+var_2C8]; void *
0x1400c5412  call    memset_0
0x1400c5417  mov     r12, [rsp+388h+arg_20]
0x1400c541f  mov     [rsp+388h+var_2C8], r12
0x1400c5427  mov     [rsp+388h+var_2C0], r12
0x1400c542f  mov     [rsp+388h+var_2B8], 8
0x1400c543b  mov     al, [rsp+388h+var_348]
0x1400c543f  mov     [rsp+388h+var_287], al
0x1400c5446  movups  xmm0, xmmword ptr [r14]
0x1400c544a  movups  [rsp+388h+var_270], xmm0
0x1400c5452  movsd   xmm1, qword ptr [r14+10h]
0x1400c5458  movsd   [rsp+388h+var_260], xmm1
0x1400c5461  test    r15, r15
0x1400c5464  jz      short loc_1400C5471
0x1400c5466  mov     rax, [r15]
0x1400c5469  mov     [rsp+388h+var_278], rax
0x1400c5471  lea     rax, [rsp+388h+var_248]
0x1400c5479  mov     [rsp+388h+var_358], rax
0x1400c547e  mov     [rsp+388h+var_360], 0
0x1400c5487  mov     [rsp+388h+var_368], 0
0x1400c5490  xor     r9d, r9d
0x1400c5493  xor     r8d, r8d
0x1400c5496  lea     rdx, [rsp+388h+var_2C8]
0x1400c549e  mov     rcx, [rdi+10h]
0x1400c54a2  call    ?CreateMemoryBlock@MemoryBlock@@KAPEAV1@PEAXPEAU_VID_MEMORY_BLOCK_CONFIG@@T_ADDITIONAL_MB_ATTRIBUTES@1@_KPEAVPoisonedPageContainer@@PEAU_VID_FILE_MAPPING@@AEAUMemoryTraceTracker@@@Z; MemoryBlock::CreateMemoryBlock(void *,_VID_MEMORY_BLOCK_CONFIG *,MemoryBlock::_ADDITIONAL_MB_ATTRIBUTES,unsigned __int64,PoisonedPageContainer *,_VID_FILE_MAPPING *,MemoryTraceTracker &)
0x1400c54a7  mov     rsi, rax
0x1400c54aa  mov     [rsp+388h+var_338], rax
0x1400c54af  mov     r14, [rax+98h]
0x1400c54b6  lea     r8, [rdi+48h]; struct MemoryNotificationsCallback *
0x1400c54ba  mov     rdx, [rdi+18h]; struct IVidPartitionManager *
0x1400c54be  mov     rcx, rax; this
0x1400c54c1  call    ?NotificationHandlerRegister@MemoryBlock@@IEAAXPEAUIVidPartitionManager@@AEAVMemoryNotificationsCallback@@@Z; MemoryBlock::NotificationHandlerRegister(IVidPartitionManager *,MemoryNotificationsCallback &)
0x1400c54c6  xor     edx, edx; Val
0x1400c54c8  mov     r8d, 1B0h; Size
0x1400c54ce  lea     rcx, [rsp+388h+var_1F8]; void *
0x1400c54d6  call    memset_0
0x1400c54db  lea     rdx, [rsp+388h+var_248]
0x1400c54e3  lea     rcx, [rsp+388h+var_1F8]
0x1400c54eb  call    ??0?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAA@AEBUMemoryTraceTracker@@@Z; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>(MemoryTraceTracker const &)
0x1400c54f0  nop
0x1400c54f1  mov     dword ptr [rsp+388h+var_344], 0
0x1400c54f9  mov     dword ptr [rsp+388h+var_344+4], 0
0x1400c5501  lea     rax, [rsp+388h+var_344]
0x1400c5506  mov     [rsp+388h+var_368], rax; __int64
0x1400c550b  lea     r9, [rsp+388h+arg_20]
0x1400c5513  lea     r8, [rsp+388h+var_258]
0x1400c551b  lea     rdx, [rsp+388h+var_344+4]
0x1400c5520  lea     rcx, [rsp+388h+var_1F8]; struct _GUID *
0x1400c5528  call    ??$Start@HAEA_KAEA_KH@?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAAX$$QEAHAEA_K10@Z; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Start<int,unsigned __int64 &,unsigned __int64 &,int>(int &&,unsigned __int64 &,unsigned __int64 &,int &&)
0x1400c552d  lea     rax, [rsp+388h+var_2D0]
0x1400c5535  mov     [rsp+388h+var_360], rax
0x1400c553a  mov     [rsp+388h+var_368], 0
0x1400c5543  mov     r9, r14
0x1400c5546  mov     r8, r12
0x1400c5549  mov     rdx, r13
0x1400c554c  mov     rcx, [rdi+10h]
0x1400c5550  call    cs:__imp_VidCreateVaGpaRange
0x1400c5557  nop     dword ptr [rax+rax+00h]
0x1400c555c  mov     rcx, [rsp+388h]; this
0x1400c5564  test    eax, eax
0x1400c5566  jnz     short loc_1400C5579
0x1400c5568  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400c556f  mov     edx, 1F45h; void *
0x1400c5574  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c5579  lea     rcx, [rsp+388h+var_1F8]
0x1400c5581  call    ?Stop@?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAANXZ; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Stop(void)
0x1400c5586  movaps  xmm2, xmm0
0x1400c5589  lea     rdx, off_1402CE750; "GpaMappingRamMemoryBlocks"
0x1400c5590  lea     rcx, [rsp+388h+var_248]
0x1400c5598  call    ?IncreaseTimeSpentInOperation@MemoryTraceTracker@@QEAAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@N@Z; MemoryTraceTracker::IncreaseTimeSpentInOperation(std::basic_string_view<ushort> const &,double)
0x1400c559d  lea     rcx, [rsp+388h+var_248]; this
0x1400c55a5  call    ?Complete@MemoryTraceTracker@@QEAA_KXZ; MemoryTraceTracker::Complete(void)
0x1400c55aa  nop
0x1400c55ab  lea     rcx, [rsp+388h+var_1F8]
0x1400c55b3  call    ??1?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAA@XZ; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::~MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>(void)
0x1400c55b8  nop
0x1400c55b9  lea     rcx, [rsp+388h+var_248]; this
0x1400c55c1  call    ??1MemoryTraceTracker@@QEAA@XZ; MemoryTraceTracker::~MemoryTraceTracker(void)
0x1400c55c6  mov     rcx, [rdi+18h]
0x1400c55ca  mov     rax, [rcx]
0x1400c55cd  mov     rax, [rax+0D8h]
0x1400c55d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c55d9  mov     rdx, rsi; struct MemoryBlock *
0x1400c55dc  mov     rcx, [rdi+0A0h]; this
0x1400c55e3  call    ?Insert@MemoryBlockContainer@@QEAAXPEAVMemoryBlock@@@Z; MemoryBlockContainer::Insert(MemoryBlock *)
0x1400c55e8  mov     rax, [rsp+388h+var_318]
0x1400c55ed  mov     [rax], r14
0x1400c55f0  mov     rcx, [rsp+388h+var_2D0]
0x1400c55f8  mov     rax, [rsp+388h+var_328]
0x1400c55fd  mov     [rax], rcx
0x1400c5600  test    r15, r15
0x1400c5603  jz      short loc_1400C560F
0x1400c5605  mov     rax, [rsi+0F0h]
0x1400c560c  mov     [r15], rax
0x1400c560f  mov     [rsp+388h+var_328], r13
0x1400c5614  mov     [rsp+388h+var_320], rcx
0x1400c5619  lea     rcx, [rdi+2F0h]
0x1400c5620  lea     r8, [rsp+388h+var_328]
0x1400c5625  lea     rdx, [rsp+388h+var_308]
0x1400c562d  call    ??$_Emplace@U?$pair@_KPEAX@std@@@?$_Tree@V?$_Tmap_traits@_KPEAXU?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAX@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KPEAX@std@@PEAX@std@@_N@1@$$QEAU?$pair@_KPEAX@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,void *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,void *>>,0>>::_Emplace<std::pair<unsigned __int64,void *>>(std::pair<unsigned __int64,void *> &&)
0x1400c5632  nop
0x1400c5633  mov     rcx, rbx
0x1400c5636  call    RrwLockRelease
0x1400c563b  xor     eax, eax
0x1400c563d  jmp     loc_1400C56FF
0x1400c5642  mov     r8b, r12b
0x1400c5645  or      edx, 0FFFFFFFFh
0x1400c5648  mov     rcx, rbx
0x1400c564b  call    RrwpLockWait
0x1400c5650  test    eax, eax
0x1400c5652  jnz     loc_1400C5723
0x1400c5658  mov     rcx, [rsp+388h]; this
0x1400c5660  mov     r9d, 102h; char *
0x1400c5666  lea     r8, aOnecoreVmCommo_23; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x1400c566d  mov     edx, 2FEh; void *
0x1400c5672  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c5678  mov     ebx, dword ptr [rsp+388h+var_344]
0x1400c567c  test    ebx, ebx
0x1400c567e  jns     short loc_1400C56FD
0x1400c5680  lea     eax, [rbx+3FC8FFD5h]
0x1400c5686  cmp     eax, 2
0x1400c5689  ja      short loc_1400C56A2
0x1400c568b  mov     ebx, 5AAh
0x1400c5690  mov     dword ptr [rsp+388h+var_344], ebx
0x1400c5694  mov     ecx, ebx; dwErrCode
0x1400c5696  call    cs:__imp_SetLastError
0x1400c569d  nop     dword ptr [rax+rax+00h]
0x1400c56a2  mov     edi, 4020h
0x1400c56a7  mov     ecx, edi
0x1400c56a9  call    VmlIsDebugTraceEnabled
0x1400c56ae  test    eax, eax
0x1400c56b0  jz      short loc_1400C56C3
0x1400c56b2  mov     r8d, ebx
0x1400c56b5  lea     rdx, aFailedToCreate_10; "Failed to create section. HR=%d.\n"
0x1400c56bc  mov     ecx, edi
0x1400c56be  call    VmlDebugTrace
0x1400c56c3  mov     rdx, [rsp+388h+var_2D0]; void *
0x1400c56cb  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400c56cf  jz      short loc_1400C56E2
0x1400c56d1  mov     rcx, [rsp+388h+var_330]; this
0x1400c56d6  call    ?DestroyGpaRange@MemoryManager@@AEAAXPEAX@Z; MemoryManager::DestroyGpaRange(void *)
0x1400c56db  nop
0x1400c56dc  jmp     short loc_1400C56E2
0x1400c56de  mov     ebx, dword ptr [rsp+388h+var_344]
0x1400c56e2  mov     rdx, [rsp+388h+var_338]; struct MemoryBlock *
0x1400c56e7  test    rdx, rdx
0x1400c56ea  jz      short loc_1400C56FD
0x1400c56ec  mov     rcx, [rsp+388h+var_330]; this
0x1400c56f1  call    ?DestroyMemoryBlockInternal@MemoryManager@@AEAAXPEAVMemoryBlock@@@Z; MemoryManager::DestroyMemoryBlockInternal(MemoryBlock *)
0x1400c56f6  nop
0x1400c56f7  jmp     short loc_1400C56FD
0x1400c56f9  mov     ebx, dword ptr [rsp+388h+var_344]
0x1400c56fd  mov     eax, ebx
0x1400c56ff  mov     rcx, [rsp+388h+var_48]
0x1400c5707  xor     rcx, rsp; StackCookie
0x1400c570a  call    __security_check_cookie
0x1400c570f  add     rsp, 350h
0x1400c5716  pop     r15
0x1400c5718  pop     r14
0x1400c571a  pop     r13
0x1400c571c  pop     r12
0x1400c571e  pop     rdi
0x1400c571f  pop     rsi
0x1400c5720  pop     rbx
0x1400c5721  retn
0x1400c5723  prefetchw byte ptr [rbx]
0x1400c5726  mov     eax, [rbx]
0x1400c5728  jmp     loc_1400C5377
```
