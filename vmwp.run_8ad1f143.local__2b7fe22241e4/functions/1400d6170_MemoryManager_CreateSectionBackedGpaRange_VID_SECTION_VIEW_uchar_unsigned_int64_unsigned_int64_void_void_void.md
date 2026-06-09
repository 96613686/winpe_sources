# MemoryManager::CreateSectionBackedGpaRange(_VID_SECTION_VIEW *,uchar,unsigned __int64,unsigned __int64,void * *,void * *,void * *)

- ea: `0x1400d6170`
- end: `0x1400d65cf`
- name: `?CreateSectionBackedGpaRange@MemoryManager@@UEAAJPEAU_VID_SECTION_VIEW@@E_K1PEAPEAX22@Z`
- size: `1119`
- prototype: `__int64 __fastcall(MemoryManager *__hidden this, struct _VID_SECTION_VIEW *, unsigned __int8, unsigned __int64, unsigned __int64, void **, void **, void **)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140022318`
- `0x14002c750`
- `0x1400317bc`
- `0x140031828`
- `0x140031ca8`
- `0x140033a24`
- `0x14003f2d4`
- `0x14003fb04`
- `0x140040ff8`
- `0x140041a5c`
- `0x140042260`
- `0x14004badc`
- `0x14004bec4`
- `0x14004dee8`
- `0x1400504a4`
- `0x140052d50`
- `0x140054a90`
- `0x14005584c`
- `0x14005b648`
- `0x14009d7cc`
- `0x1400d6170`
- `0x1400d65d8`
- `0x140132960`
- `0x14013361c`
- `0x1402133e8`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d6536`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d6536`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400d61ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400d61ee`
- `vid!VidCreateVaGpaRange` at `0x1400d63f0`
- `vid!VidCreateVaGpaRange` at `0x1400d63f0`

## string_xrefs

- `0x1400d6506`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x1400d6241`: `CreateSectionBackedGpaRange`
- `0x1400d6555`: `Failed to create section. HR=%d.\n`

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
      (void *)0x1F58,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      v18);
  MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Stop(&v39);
  MemoryTraceTracker::IncreaseTimeSpentInOperation(v38, &off_1402C5B20);
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
0x1400d6170  push    rbx
0x1400d6172  push    rsi
0x1400d6173  push    rdi
0x1400d6174  push    r12
0x1400d6176  push    r13
0x1400d6178  push    r14
0x1400d617a  push    r15
0x1400d617c  sub     rsp, 350h
0x1400d6183  mov     rax, cs:__security_cookie
0x1400d618a  xor     rax, rsp
0x1400d618d  mov     [rsp+388h+var_48], rax
0x1400d6195  mov     r13, r9
0x1400d6198  mov     [rsp+388h+var_348], r8b
0x1400d619d  mov     r14, rdx
0x1400d61a0  mov     rdi, rcx
0x1400d61a3  mov     [rsp+388h+var_330], rcx
0x1400d61a8  mov     [rsp+388h+var_258], r9
0x1400d61b0  mov     r15, [rsp+388h+arg_28]
0x1400d61b8  mov     rax, [rsp+388h+arg_30]
0x1400d61c0  mov     [rsp+388h+var_318], rax
0x1400d61c5  mov     rax, [rsp+388h+arg_38]
0x1400d61cd  mov     [rsp+388h+var_328], rax
0x1400d61d2  mov     [rsp+388h+var_338], 0
0x1400d61db  mov     [rsp+388h+var_2D0], 0FFFFFFFFFFFFFFFFh
0x1400d61e7  lea     rbx, [rcx+2C0h]
0x1400d61ee  call    cs:__imp_GetCurrentThreadId
0x1400d61f5  nop     dword ptr [rax+rax+00h]
0x1400d61fa  mov     esi, eax
0x1400d61fc  xor     eax, eax
0x1400d61fe  lea     r12d, [rax+1]
0x1400d6202  lock cmpxchg [rbx], r12d
0x1400d6207  jz      short loc_1400D6236
0x1400d6209  mov     ecx, [rbx+4]
0x1400d620c  cmp     ecx, esi
0x1400d620e  jnz     short loc_1400D6217
0x1400d6210  lock add [rbx+8], r12d
0x1400d6215  jmp     short loc_1400D6239
0x1400d6217  test    r12b, al
0x1400d621a  jnz     loc_1400D64E2
0x1400d6220  cmp     eax, 4
0x1400d6223  jnb     loc_1400D64E2
0x1400d6229  mov     edx, eax
0x1400d622b  lea     ecx, [rax+1]
0x1400d622e  lock cmpxchg [rbx], ecx
0x1400d6232  cmp     eax, edx
0x1400d6234  jnz     short loc_1400D6217
0x1400d6236  xchg    esi, [rbx+4]
0x1400d6239  mov     [rsp+388h+var_2F8], rbx
0x1400d6241  lea     rdx, aCreatesectionb; "CreateSectionBackedGpaRange"
0x1400d6248  lea     rcx, [rsp+388h+var_2F0]
0x1400d6250  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400d6255  nop
0x1400d6256  mov     rcx, [rdi+20h]
0x1400d625a  add     rcx, 10h
0x1400d625e  mov     rax, [rcx]
0x1400d6261  mov     rax, [rax+10h]
0x1400d6265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400d626a  movups  xmm0, xmmword ptr [rax]
0x1400d626d  movdqu  [rsp+388h+var_308], xmm0
0x1400d6276  xor     r9d, r9d
0x1400d6279  lea     r8, [rsp+388h+var_2F0]
0x1400d6281  lea     rdx, [rsp+388h+var_308]
0x1400d6289  lea     rcx, [rsp+388h+var_248]
0x1400d6291  call    ??0MemoryTraceTracker@@QEAA@U_GUID@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU1@@Z; MemoryTraceTracker::MemoryTraceTracker(_GUID,std::wstring &&,_GUID const *)
0x1400d6296  nop
0x1400d6297  lea     rcx, [rsp+388h+var_2F0]
0x1400d629f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400d62a4  xor     edx, edx; Val
0x1400d62a6  lea     r8d, [rdx+70h]; Size
0x1400d62aa  lea     rcx, [rsp+388h+var_2C8]; void *
0x1400d62b2  call    memset_0
0x1400d62b7  mov     r12, [rsp+388h+arg_20]
0x1400d62bf  mov     [rsp+388h+var_2C8], r12
0x1400d62c7  mov     [rsp+388h+var_2C0], r12
0x1400d62cf  mov     [rsp+388h+var_2B8], 8
0x1400d62db  mov     al, [rsp+388h+var_348]
0x1400d62df  mov     [rsp+388h+var_287], al
0x1400d62e6  movups  xmm0, xmmword ptr [r14]
0x1400d62ea  movups  [rsp+388h+var_270], xmm0
0x1400d62f2  movsd   xmm1, qword ptr [r14+10h]
0x1400d62f8  movsd   [rsp+388h+var_260], xmm1
0x1400d6301  test    r15, r15
0x1400d6304  jz      short loc_1400D6311
0x1400d6306  mov     rax, [r15]
0x1400d6309  mov     [rsp+388h+var_278], rax
0x1400d6311  lea     rax, [rsp+388h+var_248]
0x1400d6319  mov     [rsp+388h+var_358], rax
0x1400d631e  mov     [rsp+388h+var_360], 0
0x1400d6327  mov     [rsp+388h+var_368], 0
0x1400d6330  xor     r9d, r9d
0x1400d6333  xor     r8d, r8d
0x1400d6336  lea     rdx, [rsp+388h+var_2C8]
0x1400d633e  mov     rcx, [rdi+10h]
0x1400d6342  call    ?CreateMemoryBlock@MemoryBlock@@KAPEAV1@PEAXPEAU_VID_MEMORY_BLOCK_CONFIG@@T_ADDITIONAL_MB_ATTRIBUTES@1@_KPEAVPoisonedPageContainer@@PEAU_VID_FILE_MAPPING@@AEAUMemoryTraceTracker@@@Z; MemoryBlock::CreateMemoryBlock(void *,_VID_MEMORY_BLOCK_CONFIG *,MemoryBlock::_ADDITIONAL_MB_ATTRIBUTES,unsigned __int64,PoisonedPageContainer *,_VID_FILE_MAPPING *,MemoryTraceTracker &)
0x1400d6347  mov     rsi, rax
0x1400d634a  mov     [rsp+388h+var_338], rax
0x1400d634f  mov     r14, [rax+98h]
0x1400d6356  lea     r8, [rdi+48h]; struct MemoryNotificationsCallback *
0x1400d635a  mov     rdx, [rdi+18h]; struct IVidPartitionManager *
0x1400d635e  mov     rcx, rax; this
0x1400d6361  call    ?NotificationHandlerRegister@MemoryBlock@@IEAAXPEAUIVidPartitionManager@@AEAVMemoryNotificationsCallback@@@Z; MemoryBlock::NotificationHandlerRegister(IVidPartitionManager *,MemoryNotificationsCallback &)
0x1400d6366  xor     edx, edx; Val
0x1400d6368  mov     r8d, 1B0h; Size
0x1400d636e  lea     rcx, [rsp+388h+var_1F8]; void *
0x1400d6376  call    memset_0
0x1400d637b  lea     rdx, [rsp+388h+var_248]
0x1400d6383  lea     rcx, [rsp+388h+var_1F8]
0x1400d638b  call    ??0?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAA@AEBUMemoryTraceTracker@@@Z; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>(MemoryTraceTracker const &)
0x1400d6390  nop
0x1400d6391  mov     dword ptr [rsp+388h+var_344], 0
0x1400d6399  mov     dword ptr [rsp+388h+var_344+4], 0
0x1400d63a1  lea     rax, [rsp+388h+var_344]
0x1400d63a6  mov     [rsp+388h+var_368], rax; __int64
0x1400d63ab  lea     r9, [rsp+388h+arg_20]
0x1400d63b3  lea     r8, [rsp+388h+var_258]
0x1400d63bb  lea     rdx, [rsp+388h+var_344+4]
0x1400d63c0  lea     rcx, [rsp+388h+var_1F8]; struct _GUID *
0x1400d63c8  call    ??$Start@HAEA_KAEA_KH@?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAAX$$QEAHAEA_K10@Z; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Start<int,unsigned __int64 &,unsigned __int64 &,int>(int &&,unsigned __int64 &,unsigned __int64 &,int &&)
0x1400d63cd  lea     rax, [rsp+388h+var_2D0]
0x1400d63d5  mov     [rsp+388h+var_360], rax
0x1400d63da  mov     [rsp+388h+var_368], 0
0x1400d63e3  mov     r9, r14
0x1400d63e6  mov     r8, r12
0x1400d63e9  mov     rdx, r13
0x1400d63ec  mov     rcx, [rdi+10h]
0x1400d63f0  call    cs:__imp_VidCreateVaGpaRange
0x1400d63f7  nop     dword ptr [rax+rax+00h]
0x1400d63fc  mov     rcx, [rsp+388h]; this
0x1400d6404  test    eax, eax
0x1400d6406  jnz     short loc_1400D6419
0x1400d6408  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400d640f  mov     edx, 1F58h; void *
0x1400d6414  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400d6419  lea     rcx, [rsp+388h+var_1F8]
0x1400d6421  call    ?Stop@?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAANXZ; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::Stop(void)
0x1400d6426  movaps  xmm2, xmm0
0x1400d6429  lea     rdx, off_1402C5B20; "GpaMappingRamMemoryBlocks"
0x1400d6430  lea     rcx, [rsp+388h+var_248]
0x1400d6438  call    ?IncreaseTimeSpentInOperation@MemoryTraceTracker@@QEAAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@N@Z; MemoryTraceTracker::IncreaseTimeSpentInOperation(std::basic_string_view<ushort> const &,double)
0x1400d643d  lea     rcx, [rsp+388h+var_248]; this
0x1400d6445  call    ?Complete@MemoryTraceTracker@@QEAA_KXZ; MemoryTraceTracker::Complete(void)
0x1400d644a  nop
0x1400d644b  lea     rcx, [rsp+388h+var_1F8]
0x1400d6453  call    ??1?$MemoryTrace@VGpaMapRamMemoryBlock@VmWorkerTrace@@@@QEAA@XZ; MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>::~MemoryTrace<VmWorkerTrace::GpaMapRamMemoryBlock>(void)
0x1400d6458  nop
0x1400d6459  lea     rcx, [rsp+388h+var_248]; this
0x1400d6461  call    ??1MemoryTraceTracker@@QEAA@XZ; MemoryTraceTracker::~MemoryTraceTracker(void)
0x1400d6466  mov     rcx, [rdi+18h]
0x1400d646a  mov     rax, [rcx]
0x1400d646d  mov     rax, [rax+0D8h]
0x1400d6474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400d6479  mov     rdx, rsi; struct MemoryBlock *
0x1400d647c  mov     rcx, [rdi+0A0h]; this
0x1400d6483  call    ?Insert@MemoryBlockContainer@@QEAAXPEAVMemoryBlock@@@Z; MemoryBlockContainer::Insert(MemoryBlock *)
0x1400d6488  mov     rax, [rsp+388h+var_318]
0x1400d648d  mov     [rax], r14
0x1400d6490  mov     rcx, [rsp+388h+var_2D0]
0x1400d6498  mov     rax, [rsp+388h+var_328]
0x1400d649d  mov     [rax], rcx
0x1400d64a0  test    r15, r15
0x1400d64a3  jz      short loc_1400D64AF
0x1400d64a5  mov     rax, [rsi+0F0h]
0x1400d64ac  mov     [r15], rax
0x1400d64af  mov     [rsp+388h+var_328], r13
0x1400d64b4  mov     [rsp+388h+var_320], rcx
0x1400d64b9  lea     rcx, [rdi+2F0h]
0x1400d64c0  lea     r8, [rsp+388h+var_328]
0x1400d64c5  lea     rdx, [rsp+388h+var_308]
0x1400d64cd  call    ??$_Emplace@U?$pair@_KPEAX@std@@@?$_Tree@V?$_Tmap_traits@_KPEAXU?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAX@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KPEAX@std@@PEAX@std@@_N@1@$$QEAU?$pair@_KPEAX@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,void *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,void *>>,0>>::_Emplace<std::pair<unsigned __int64,void *>>(std::pair<unsigned __int64,void *> &&)
0x1400d64d2  nop
0x1400d64d3  mov     rcx, rbx
0x1400d64d6  call    RrwLockRelease
0x1400d64db  xor     eax, eax
0x1400d64dd  jmp     loc_1400D659F
0x1400d64e2  mov     r8b, r12b
0x1400d64e5  or      edx, 0FFFFFFFFh
0x1400d64e8  mov     rcx, rbx
0x1400d64eb  call    RrwpLockWait
0x1400d64f0  test    eax, eax
0x1400d64f2  jnz     loc_1400D65C3
0x1400d64f8  mov     rcx, [rsp+388h]; this
0x1400d6500  mov     r9d, 102h; char *
0x1400d6506  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x1400d650d  mov     edx, 2FEh; void *
0x1400d6512  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400d6518  mov     ebx, dword ptr [rsp+388h+var_344]
0x1400d651c  test    ebx, ebx
0x1400d651e  jns     short loc_1400D659D
0x1400d6520  lea     eax, [rbx+3FC8FFD5h]
0x1400d6526  cmp     eax, 2
0x1400d6529  ja      short loc_1400D6542
0x1400d652b  mov     ebx, 5AAh
0x1400d6530  mov     dword ptr [rsp+388h+var_344], ebx
0x1400d6534  mov     ecx, ebx; dwErrCode
0x1400d6536  call    cs:__imp_SetLastError
0x1400d653d  nop     dword ptr [rax+rax+00h]
0x1400d6542  mov     edi, 4020h
0x1400d6547  mov     ecx, edi
0x1400d6549  call    VmlIsDebugTraceEnabled
0x1400d654e  test    eax, eax
0x1400d6550  jz      short loc_1400D6563
0x1400d6552  mov     r8d, ebx
0x1400d6555  lea     rdx, aFailedToCreate_10; "Failed to create section. HR=%d.\n"
0x1400d655c  mov     ecx, edi
0x1400d655e  call    VmlDebugTrace
0x1400d6563  mov     rdx, [rsp+388h+var_2D0]; void *
0x1400d656b  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400d656f  jz      short loc_1400D6582
0x1400d6571  mov     rcx, [rsp+388h+var_330]; this
0x1400d6576  call    ?DestroyGpaRange@MemoryManager@@AEAAXPEAX@Z; MemoryManager::DestroyGpaRange(void *)
0x1400d657b  nop
0x1400d657c  jmp     short loc_1400D6582
0x1400d657e  mov     ebx, dword ptr [rsp+388h+var_344]
0x1400d6582  mov     rdx, [rsp+388h+var_338]; struct MemoryBlock *
0x1400d6587  test    rdx, rdx
0x1400d658a  jz      short loc_1400D659D
0x1400d658c  mov     rcx, [rsp+388h+var_330]; this
0x1400d6591  call    ?DestroyMemoryBlockInternal@MemoryManager@@AEAAXPEAVMemoryBlock@@@Z; MemoryManager::DestroyMemoryBlockInternal(MemoryBlock *)
0x1400d6596  nop
0x1400d6597  jmp     short loc_1400D659D
0x1400d6599  mov     ebx, dword ptr [rsp+388h+var_344]
0x1400d659d  mov     eax, ebx
0x1400d659f  mov     rcx, [rsp+388h+var_48]
0x1400d65a7  xor     rcx, rsp; StackCookie
0x1400d65aa  call    __security_check_cookie
0x1400d65af  add     rsp, 350h
0x1400d65b6  pop     r15
0x1400d65b8  pop     r14
0x1400d65ba  pop     r13
0x1400d65bc  pop     r12
0x1400d65be  pop     rdi
0x1400d65bf  pop     rsi
0x1400d65c0  pop     rbx
0x1400d65c1  retn
0x1400d65c3  prefetchw byte ptr [rbx]
0x1400d65c6  mov     eax, [rbx]
0x1400d65c8  jmp     loc_1400D6217
```
