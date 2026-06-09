# MemoryBlock::CreateMemoryBlock(void *,_VID_MEMORY_BLOCK_CONFIG *,MemoryBlock::_ADDITIONAL_MB_ATTRIBUTES,unsigned __int64,PoisonedPageContainer *,_VID_FILE_MAPPING *,MemoryTraceTracker &)

- ea: `0x1402133e8`
- end: `0x1402138d3`
- name: `?CreateMemoryBlock@MemoryBlock@@KAPEAV1@PEAXPEAU_VID_MEMORY_BLOCK_CONFIG@@T_ADDITIONAL_MB_ATTRIBUTES@1@_KPEAVPoisonedPageContainer@@PEAU_VID_FILE_MAPPING@@AEAUMemoryTraceTracker@@@Z`
- size: `1259`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1400bfa50`
- `0x1400d6170`
- `0x140205828`

## callees

- `0x14001f394`
- `0x1400205cc`
- `0x14002c750`
- `0x140033970`
- `0x14004d6c0`
- `0x140051a78`
- `0x14005b648`
- `0x1400db688`
- `0x140132960`
- `0x140132d0c`
- `0x14013361c`
- `0x1401fe9a0`
- `0x140212004`
- `0x140212fd8`
- `0x1402133e8`

## import_xrefs

- `vid!VidQueryMemoryBlockInformation` at `0x14021372b`
- `vid!VidQueryMemoryBlockInformation` at `0x14021372b`
- `vid!VidCreateMemoryBlock` at `0x140213689`
- `vid!VidCreateMemoryBlock` at `0x140213689`
- `vid!VidCreateDaxFileMemoryBlock` at `0x140213618`
- `vid!VidCreateDaxFileMemoryBlock` at `0x140213618`

## string_xrefs

- `0x14021363f`: `PageCountTotal = %I64x, MbCreateFlags = %I64x, VirtualNode = %u, PersistId = %I64u`
- `0x1402136bf`: `PageCountTotal = %I64x, PageCountValid = %I64x, MbCreateFlags = %I64x, BackingBitmapBufferSizeInBytes = %I64u, VirtualNode = %u, PersistId = %I64u`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
MemoryBlock *MemoryBlock::CreateMemoryBlock(__int64 a1, _QWORD *a2, char a3, ...)
{
  PoisonedPageContainer *v6; // r13
  __int64 v7; // rsi
  __int64 v8; // r14
  __int64 v9; // rax
  __int64 *v10; // rdi
  __int64 v11; // rax
  _BYTE *v12; // rsi
  _BYTE *v13; // r14
  __int64 v14; // r9
  __int64 v15; // r15
  __int64 v16; // rdi
  int v17; // ebx
  const char *v18; // rsi
  unsigned int DaxFileMemoryBlock; // eax
  __int64 v20; // rbx
  int v21; // edi
  __int64 v22; // rsi
  __int64 v23; // r14
  const char *v24; // r15
  unsigned int MemoryBlock; // eax
  const char *v26; // r9
  wil *v27; // rcx
  char *v28; // rbx
  MemoryBlock *v29; // rbx
  double v30; // xmm0_8
  double v31; // xmm0_8
  unsigned __int64 v32; // rax
  unsigned int v34; // ebx
  __int64 v35; // r9
  __int64 v36; // r9
  __int64 v37; // r9
  __int64 v38; // [rsp+38h] [rbp-2C0h]
  __int64 v39; // [rsp+48h] [rbp-2B0h]
  __int64 v40; // [rsp+60h] [rbp-298h] BYREF
  __int64 v41; // [rsp+68h] [rbp-290h] BYREF
  __int64 v42; // [rsp+70h] [rbp-288h] BYREF
  __int64 v43; // [rsp+78h] [rbp-280h]
  __int64 v44; // [rsp+80h] [rbp-278h]
  _QWORD *v45; // [rsp+90h] [rbp-268h]
  MemoryBlock **v46; // [rsp+A0h] [rbp-258h]
  char v47; // [rsp+A8h] [rbp-250h]
  MemoryBlock *v48; // [rsp+B0h] [rbp-248h] BYREF
  struct _GUID v49; // [rsp+C0h] [rbp-238h] BYREF
  char v50; // [rsp+102h] [rbp-1F6h]
  double v51; // [rsp+118h] [rbp-1E0h]
  __int64 v52; // [rsp+270h] [rbp-88h] BYREF
  __int64 v53; // [rsp+290h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]
  __int64 v55; // [rsp+318h] [rbp+20h] BYREF
  va_list va; // [rsp+318h] [rbp+20h]
  PoisonedPageContainer *v57; // [rsp+320h] [rbp+28h]
  __int64 v58; // [rsp+328h] [rbp+30h]
  __int64 v59; // [rsp+330h] [rbp+38h]
  va_list va1; // [rsp+338h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v55 = va_arg(va1, _QWORD);
  v57 = va_arg(va1, PoisonedPageContainer *);
  v58 = va_arg(va1, _QWORD);
  v59 = va_arg(va1, _QWORD);
  v45 = a2;
  v6 = v57;
  v7 = v58;
  v43 = v58;
  v8 = v59;
  v44 = v59;
  v40 = (__int64)operator new(0xF8u);
  memset_0((void *)v40, 0, 0xF8u);
  v48 = MemoryBlock::MemoryBlock((MemoryBlock *)v40);
  v46 = &v48;
  v47 = 1;
  memset_0(&v49, 0, 0x1B0u);
  MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>(&v49, v8);
  if ( v7 )
    v9 = *(_QWORD *)(v7 + 8);
  else
    v9 = 0;
  v42 = v9;
  v10 = a2 + 9;
  if ( v6 )
    v11 = *((_QWORD *)v6 + 1);
  else
    v11 = 0;
  v40 = v11;
  v12 = (char *)a2 + 65;
  LODWORD(v41) = a3 & 1;
  v13 = a2 + 2;
  MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::Start<unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,int,unsigned __int64 &,unsigned __int64 &,unsigned char &,unsigned __int64,unsigned __int64 &,unsigned __int64>(
    &v49,
    (__int64)(a2 + 3),
    (__int64)&v41,
    (__int64)(a2 + 5),
    (__int64)va,
    (__int64)a2 + 65,
    (__int64)&v40,
    (__int64)(a2 + 9),
    (__int64)&v42);
  try
  {
    *((_QWORD *)v48 + 20) = a1;
    *(_BYTE *)v48 = *v13 & 1;
    *((_BYTE *)v48 + 1) = a3 & 1;
    *((_BYTE *)v48 + 2) = (a3 & 2) != 0;
    *((_BYTE *)v48 + 3) = (a3 & 4) != 0;
    *((_QWORD *)v48 + 21) = *(_QWORD *)v13;
    *((_BYTE *)v48 + 184) = *v12;
    v15 = *(_QWORD *)v13;
    v40 = v15;
    if ( (v15 & 0x40) != 0 )
    {
      v16 = *v10;
      v17 = (unsigned __int8)*v12;
      v18 = (const char *)*a2;
      LOBYTE(v14) = v17;
      DaxFileMemoryBlock = VidCreateDaxFileMemoryBlock(
                             *((_QWORD *)v48 + 20),
                             *a2,
                             v15,
                             v14,
                             v16,
                             v43,
                             (char *)v48 + 152);
      LODWORD(v38) = v17;
      wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecore\\vm\\worker\\memory\\memoryblock.cpp",
        (const char *)DaxFileMemoryBlock,
        (int)"PageCountTotal = %I64x, MbCreateFlags = %I64x, VirtualNode = %u, PersistId = %I64u",
        v18,
        v15,
        v38,
        v16);
    }
    else
    {
      v20 = *v10;
      v21 = (unsigned __int8)*v12;
      v22 = a2[5];
      v23 = a2[1];
      v24 = (const char *)*a2;
      MemoryBlock = VidCreateMemoryBlock(*((_QWORD *)v48 + 20), a2, (char *)v48 + 152);
      LODWORD(v39) = v21;
      wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
        retaddr,
        (void *)0xE1,
        (unsigned int)"onecore\\vm\\worker\\memory\\memoryblock.cpp",
        (const char *)MemoryBlock,
        (int)"PageCountTotal = %I64x, PageCountValid = %I64x, MbCreateFlags = %I64x, BackingBitmapBufferSizeInBytes = %I6"
             "4u, VirtualNode = %u, PersistId = %I64u",
        v24,
        v23,
        v40,
        v22,
        v39,
        v20);
      v13 = a2 + 2;
    }
    if ( (*v13 & 8) != 0
      && !(unsigned int)VidQueryMemoryBlockInformation(
                          *((_QWORD *)v48 + 20),
                          *((_QWORD *)v48 + 19),
                          0,
                          0,
                          0,
                          (char *)v48 + 240,
                          8,
                          0) )
    {
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xF2,
        (unsigned int)"onecore\\vm\\worker\\memory\\memoryblock.cpp",
        v26);
    }
    *((_QWORD *)v48 + 14) = *a2;
    v27 = (wil *)a2[1];
    *((_QWORD *)v48 + 15) = v27;
  }
  catch ( ... )
  {
    v34 = wil::ResultFromCaughtException(v27);
    v35 = v34;
    LODWORD(v35) = v34 & 0xEFFFFFFF;
    _snwprintf_s<16>(&v52, 16, L"%%%%%u", v35);
    v36 = v34;
    LODWORD(v36) = v34 & 0xEFFFFFFF;
    _snwprintf_s<16>(&v53, 16, L"0x%08X", v36);
    if ( v34 == -2147023446 || v34 + 1070137301 <= 1 )
    {
      if ( v34 == -1070137301 )
      {
        v37 = 2;
      }
      else
      {
        v37 = 1;
        if ( v34 == -1070137300 )
          v37 = 3;
      }
      MemoryManager::VmStartOutOfMemoryErrorPopulateCache(
        &MemoryManager::m_Instance,
        0,
        2,
        v37,
        *((_BYTE *)v45 + 65),
        v45[1],
        v45[2]);
      SetLastError(0x5AAu);
    }
    throw;
  }
  *((_QWORD *)v48 + 16) = v55;
  if ( v6 )
  {
    if ( (*v13 & 0x44) == 0 )
      PoisonedPageContainer::Mark(v6, *((void **)v48 + 20), *((void **)v48 + 19));
    v28 = (char *)v48 + 192;
    if ( (MemoryBlock *)((char *)v48 + 192) != v6 )
    {
      std::_Tree<std::_Tset_traits<HyperVStorageObjectTable *,std::less<HyperVStorageObjectTable *>,std::allocator<HyperVStorageObjectTable *>,0>>::clear((char *)v48 + 192);
      std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::_Copy<0>(
        v28,
        v6);
    }
  }
  if ( (*v13 & 4) != 0 )
    *((_QWORD *)v48 + 26) = a2[9];
  MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::Stop(&v49);
  MemoryTraceTracker::IncreaseTimeSpentInOperation(v44, &off_1402DACF8);
  v29 = v48;
  if ( *(_BYTE *)v48 )
  {
    v30 = v50 ? v51 : 0.0;
    if ( *(_QWORD *)MemoryManagerStats::gm_SingletonInstance )
    {
      v31 = v30 * 1000000.0;
      v32 = 0;
      if ( v31 >= 9.223372036854776e18 )
      {
        v31 = v31 - 9.223372036854776e18;
        if ( v31 < 9.223372036854776e18 )
          v32 = 0x8000000000000000uLL;
      }
      _InterlockedAdd64(
        (volatile signed __int64 *)(**(_QWORD **)MemoryManagerStats::gm_SingletonInstance
                                  + *(unsigned int *)(*((_QWORD *)MemoryManagerStats::gm_SingletonInstance + 1) + 220LL)),
        v32 + (unsigned int)(int)v31);
      v29 = v48;
    }
  }
  MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::~MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>(&v49);
  return v29;
}

```

## disassembly

```asm
0x1402133e8  mov     [rsp+arg_18], r9
0x1402133ed  push    rbx
0x1402133ee  push    rsi
0x1402133ef  push    rdi
0x1402133f0  push    r12
0x1402133f2  push    r13
0x1402133f4  push    r14
0x1402133f6  push    r15
0x1402133f8  sub     rsp, 2C0h
0x1402133ff  mov     rax, cs:__security_cookie
0x140213406  xor     rax, rsp
0x140213409  mov     [rsp+2F8h+var_48], rax
0x140213411  mov     ebx, r8d
0x140213414  mov     r12, rdx
0x140213417  mov     r15, rcx
0x14021341a  mov     [rsp+2F8h+var_268], rdx
0x140213422  mov     r13, [rsp+2F8h+arg_20]
0x14021342a  mov     rsi, [rsp+2F8h+arg_28]
0x140213432  mov     [rsp+2F8h+var_280], rsi
0x140213437  mov     r14, [rsp+2F8h+arg_30]
0x14021343f  mov     [rsp+2F8h+var_278], r14
0x140213447  mov     ecx, 0F8h; Size
0x14021344c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140213451  mov     rdi, rax
0x140213454  mov     [rsp+2F8h+var_298], rax
0x140213459  xor     edx, edx; Val
0x14021345b  mov     r8d, 0F8h; Size
0x140213461  mov     rcx, rax; void *
0x140213464  call    memset_0
0x140213469  mov     rcx, rdi; this
0x14021346c  call    ??0MemoryBlock@@AEAA@XZ; MemoryBlock::MemoryBlock(void)
0x140213471  nop
0x140213472  mov     [rsp+2F8h+var_248], rax
0x14021347a  lea     rax, [rsp+2F8h+var_248]
0x140213482  mov     [rsp+2F8h+var_258], rax
0x14021348a  mov     [rsp+2F8h+var_250], 1
0x140213492  xor     edx, edx; Val
0x140213494  mov     r8d, 1B0h; Size
0x14021349a  lea     rcx, [rsp+2F8h+var_238]; void *
0x1402134a2  call    memset_0
0x1402134a7  mov     rdx, r14
0x1402134aa  lea     rcx, [rsp+2F8h+var_238]
0x1402134b2  call    ??0?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAA@AEBUMemoryTraceTracker@@@Z; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>(MemoryTraceTracker const &)
0x1402134b7  nop
0x1402134b8  test    rsi, rsi
0x1402134bb  jz      short loc_1402134C3
0x1402134bd  mov     rax, [rsi+8]
0x1402134c1  jmp     short loc_1402134C5
0x1402134c3  xor     eax, eax
0x1402134c5  mov     [rsp+2F8h+var_288], rax
0x1402134ca  lea     rdi, [r12+48h]
0x1402134cf  test    r13, r13
0x1402134d2  jz      short loc_1402134DA
0x1402134d4  mov     rax, [r13+8]
0x1402134d8  jmp     short loc_1402134DC
0x1402134da  xor     eax, eax
0x1402134dc  mov     [rsp+2F8h+var_298], rax
0x1402134e1  lea     rsi, [r12+41h]
0x1402134e6  lea     rdx, [r12+28h]
0x1402134eb  mov     eax, ebx
0x1402134ed  and     eax, 1
0x1402134f0  mov     dword ptr [rsp+2F8h+var_290], eax
0x1402134f4  lea     r14, [r12+10h]
0x1402134f9  lea     rax, [r12+18h]
0x1402134fe  lea     r8, [rsp+2F8h+var_288]
0x140213503  mov     [rsp+2F8h+var_2A0], r8; __int64
0x140213508  mov     [rsp+2F8h+var_2A8], rdi; __int64
0x14021350d  lea     r8, [rsp+2F8h+var_298]
0x140213512  mov     [rsp+2F8h+var_2B0], r8; __int64
0x140213517  mov     [rsp+2F8h+var_2B8], rsi; __int64
0x14021351c  lea     r8, [rsp+2F8h+arg_18]
0x140213524  mov     [rsp+2F8h+var_2C0], r8; __int64
0x140213529  mov     [rsp+2F8h+var_2C8], rdx; __int64
0x14021352e  lea     rdx, [rsp+2F8h+var_290]
0x140213533  mov     [rsp+2F8h+var_2D0], rdx; __int64
0x140213538  mov     [rsp+2F8h+var_2D8], rax; __int64
0x14021353d  mov     r9, r14
0x140213540  lea     r8, [r12+8]
0x140213545  mov     rdx, r12
0x140213548  lea     rcx, [rsp+2F8h+var_238]; struct _GUID *
0x140213550  call    ??$Start@AEA_KAEA_KAEA_KAEA_KHAEA_KAEA_KAEAE_KAEA_K_K@?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAAXAEA_K000$$QEAH00AEAE$$QEA_K03@Z; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::Start<unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,int,unsigned __int64 &,unsigned __int64 &,uchar &,unsigned __int64,unsigned __int64 &,unsigned __int64>(unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,int &&,unsigned __int64 &,unsigned __int64 &,uchar &,unsigned __int64 &&,unsigned __int64 &,unsigned __int64 &&)
0x140213555  mov     rax, [rsp+2F8h+var_248]
0x14021355d  mov     [rax+0A0h], r15
0x140213564  mov     cl, [r14]
0x140213567  and     cl, 1
0x14021356a  mov     rax, [rsp+2F8h+var_248]
0x140213572  mov     [rax], cl
0x140213574  mov     cl, bl
0x140213576  and     cl, 1
0x140213579  mov     rax, [rsp+2F8h+var_248]
0x140213581  mov     [rax+1], cl
0x140213584  mov     ecx, ebx
0x140213586  shr     ecx, 1
0x140213588  and     cl, 1
0x14021358b  mov     rax, [rsp+2F8h+var_248]
0x140213593  mov     [rax+2], cl
0x140213596  shr     ebx, 2
0x140213599  and     bl, 1
0x14021359c  mov     rax, [rsp+2F8h+var_248]
0x1402135a4  mov     [rax+3], bl
0x1402135a7  mov     rcx, [r14]
0x1402135aa  mov     rax, [rsp+2F8h+var_248]
0x1402135b2  mov     [rax+0A8h], rcx
0x1402135b9  mov     cl, [rsi]
0x1402135bb  mov     rax, [rsp+2F8h+var_248]
0x1402135c3  mov     [rax+0B8h], cl
0x1402135c9  mov     r15, [r14]
0x1402135cc  mov     [rsp+2F8h+var_298], r15
0x1402135d1  mov     rcx, [rsp+2F8h+var_248]
0x1402135d9  test    r15b, 40h
0x1402135dd  jz      loc_140213664
0x1402135e3  mov     rdi, [rdi]
0x1402135e6  movzx   ebx, byte ptr [rsi]
0x1402135e9  mov     rsi, [r12]
0x1402135ed  lea     rax, [rcx+98h]
0x1402135f4  mov     [rsp+2F8h+var_2C8], rax
0x1402135f9  mov     rax, [rsp+2F8h+var_280]
0x1402135fe  mov     [rsp+2F8h+var_2D0], rax
0x140213603  mov     [rsp+2F8h+var_2D8], rdi
0x140213608  mov     r9b, bl
0x14021360b  mov     r8, r15
0x14021360e  mov     rdx, rsi
0x140213611  mov     rcx, [rcx+0A0h]
0x140213618  call    cs:__imp_VidCreateDaxFileMemoryBlock
0x14021361f  nop     dword ptr [rax+rax+00h]
0x140213624  mov     rcx, [rsp+2F8h]; this
0x14021362c  mov     [rsp+2F8h+var_2B8], rdi
0x140213631  mov     dword ptr [rsp+2F8h+var_2C0], ebx
0x140213635  mov     [rsp+2F8h+var_2C8], r15
0x14021363a  mov     [rsp+2F8h+var_2D0], rsi; char *
0x14021363f  lea     rdx, aPagecounttotal_1; "PageCountTotal = %I64x, MbCreateFlags ="...
0x140213646  mov     [rsp+2F8h+var_2D8], rdx; int
0x14021364b  mov     r9d, eax; char *
0x14021364e  lea     r8, aOnecoreVmWorke_68; "onecore\\vm\\worker\\memory\\memorybloc"...
0x140213655  mov     edx, 0D0h; void *
0x14021365a  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x14021365f  jmp     loc_1402136E4
0x140213664  mov     rbx, [rdi]
0x140213667  movzx   edi, byte ptr [rsi]
0x14021366a  mov     rsi, [r12+28h]
0x14021366f  mov     r14, [r12+8]
0x140213674  mov     r15, [r12]
0x140213678  lea     r8, [rcx+98h]
0x14021367f  mov     rdx, r12
0x140213682  mov     rcx, [rcx+0A0h]
0x140213689  call    cs:__imp_VidCreateMemoryBlock
0x140213690  nop     dword ptr [rax+rax+00h]
0x140213695  mov     rcx, [rsp+2F8h]; this
0x14021369d  mov     [rsp+2F8h+var_2A8], rbx
0x1402136a2  mov     dword ptr [rsp+2F8h+var_2B0], edi
0x1402136a6  mov     [rsp+2F8h+var_2B8], rsi
0x1402136ab  mov     rdx, [rsp+2F8h+var_298]
0x1402136b0  mov     [rsp+2F8h+var_2C0], rdx
0x1402136b5  mov     [rsp+2F8h+var_2C8], r14
0x1402136ba  mov     [rsp+2F8h+var_2D0], r15; char *
0x1402136bf  lea     rdx, aPagecounttotal; "PageCountTotal = %I64x, PageCountValid "...
0x1402136c6  mov     [rsp+2F8h+var_2D8], rdx; int
0x1402136cb  mov     r9d, eax; char *
0x1402136ce  lea     r8, aOnecoreVmWorke_68; "onecore\\vm\\worker\\memory\\memorybloc"...
0x1402136d5  mov     edx, 0E1h; void *
0x1402136da  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1402136df  lea     r14, [r12+10h]
0x1402136e4  test    byte ptr [r14], 8
0x1402136e8  jz      short loc_140213754
0x1402136ea  mov     rcx, [rsp+2F8h+var_248]
0x1402136f2  lea     rax, [rcx+0F0h]
0x1402136f9  mov     [rsp+2F8h+var_2C0], 0
0x140213702  mov     dword ptr [rsp+2F8h+var_2C8], 8
0x14021370a  mov     [rsp+2F8h+var_2D0], rax
0x14021370f  mov     dword ptr [rsp+2F8h+var_2D8], 0
0x140213717  xor     r9d, r9d
0x14021371a  xor     r8d, r8d
0x14021371d  mov     rdx, [rcx+98h]
0x140213724  mov     rcx, [rcx+0A0h]
0x14021372b  call    cs:__imp_VidQueryMemoryBlockInformation
0x140213732  nop     dword ptr [rax+rax+00h]
0x140213737  mov     rcx, [rsp+2F8h]; this
0x14021373f  test    eax, eax
0x140213741  jnz     short loc_140213754
0x140213743  lea     r8, aOnecoreVmWorke_68; "onecore\\vm\\worker\\memory\\memorybloc"...
0x14021374a  mov     edx, 0F2h; void *
0x14021374f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140213754  mov     rcx, [r12]
0x140213758  mov     rax, [rsp+2F8h+var_248]
0x140213760  mov     [rax+70h], rcx
0x140213764  mov     rcx, [r12+8]
0x140213769  mov     rax, [rsp+2F8h+var_248]
0x140213771  mov     [rax+78h], rcx
0x140213775  mov     rax, [rsp+2F8h+var_248]
0x14021377d  mov     rcx, [rsp+2F8h+arg_18]
0x140213785  mov     [rax+80h], rcx
0x14021378c  test    r13, r13
0x14021378f  jz      short loc_1402137DC
0x140213791  test    byte ptr [r14], 44h
0x140213795  jnz     short loc_1402137B5
0x140213797  mov     rdx, [rsp+2F8h+var_248]
0x14021379f  mov     r8, [rdx+98h]; void *
0x1402137a6  mov     rdx, [rdx+0A0h]; void *
0x1402137ad  mov     rcx, r13; this
0x1402137b0  call    ?Mark@PoisonedPageContainer@@QEAAXPEAX0@Z; PoisonedPageContainer::Mark(void *,void *)
0x1402137b5  mov     rbx, [rsp+2F8h+var_248]
0x1402137bd  add     rbx, 0C0h
0x1402137c4  cmp     rbx, r13
0x1402137c7  jz      short loc_1402137DC
0x1402137c9  mov     rcx, rbx
0x1402137cc  call    ?clear@?$_Tree@V?$_Tset_traits@PEAVHyperVStorageObjectTable@@U?$less@PEAVHyperVStorageObjectTable@@@std@@V?$allocator@PEAVHyperVStorageObjectTable@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<HyperVStorageObjectTable *,std::less<HyperVStorageObjectTable *>,std::allocator<HyperVStorageObjectTable *>,0>>::clear(void)
0x1402137d1  mov     rdx, r13
0x1402137d4  mov     rcx, rbx
0x1402137d7  call    ??$_Copy@$0A@@?$_Tree@V?$_Tset_traits@_KU?$less@_K@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::_Copy<0>(std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>> const &)
0x1402137dc  test    byte ptr [r14], 4
0x1402137e0  jz      short loc_1402137F6
0x1402137e2  mov     rdx, [r12+48h]
0x1402137e7  mov     rax, [rsp+2F8h+var_248]
0x1402137ef  mov     [rax+0D0h], rdx
0x1402137f6  lea     rcx, [rsp+2F8h+var_238]
0x1402137fe  call    ?Stop@?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAANXZ; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::Stop(void)
0x140213803  movaps  xmm2, xmm0
0x140213806  lea     rdx, off_1402DACF8; "CreatingRamMemoryBlocks"
0x14021380d  mov     rcx, [rsp+2F8h+var_278]
0x140213815  call    ?IncreaseTimeSpentInOperation@MemoryTraceTracker@@QEAAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@N@Z; MemoryTraceTracker::IncreaseTimeSpentInOperation(std::basic_string_view<ushort> const &,double)
0x14021381a  mov     rbx, [rsp+2F8h+var_248]
0x140213822  cmp     byte ptr [rbx], 0
0x140213825  jz      short loc_14021389E
0x140213827  mov     rcx, cs:?gm_SingletonInstance@MemoryManagerStats@@0PEAV1@EA; MemoryManagerStats * MemoryManagerStats::gm_SingletonInstance
0x14021382e  cmp     [rsp+2F8h+var_1F6], 0
0x140213836  jz      short loc_140213843
0x140213838  movsd   xmm0, [rsp+2F8h+var_1E0]
0x140213841  jmp     short loc_140213846
0x140213843  xorps   xmm0, xmm0
0x140213846  mov     r8, [rcx]
0x140213849  test    r8, r8
0x14021384c  jz      short loc_14021389E
0x14021384e  mulsd   xmm0, cs:__real@412e848000000000
0x140213856  xor     eax, eax
0x140213858  movsd   xmm1, cs:__real@43e0000000000000
0x140213860  comisd  xmm0, xmm1
0x140213864  jb      short loc_14021387D
0x140213866  subsd   xmm0, xmm1
0x14021386a  comisd  xmm0, xmm1
0x14021386e  jnb     short loc_14021387D
0x140213870  mov     rdx, 8000000000000000h
0x14021387a  mov     rax, rdx
0x14021387d  cvttsd2si rdx, xmm0
0x140213882  add     rdx, rax
0x140213885  mov     rax, [rcx+8]
0x140213889  mov     ecx, [rax+0DCh]
0x14021388f  add     rcx, [r8]
0x140213892  lock add [rcx], rdx
0x140213896  mov     rbx, [rsp+2F8h+var_248]
0x14021389e  lea     rcx, [rsp+2F8h+var_238]
0x1402138a6  call    ??1?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAA@XZ; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::~MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>(void)
0x1402138ab  nop
0x1402138ac  mov     rax, rbx
0x1402138af  mov     rcx, [rsp+2F8h+var_48]
0x1402138b7  xor     rcx, rsp; StackCookie
0x1402138ba  call    __security_check_cookie
0x1402138bf  add     rsp, 2C0h
0x1402138c6  pop     r15
0x1402138c8  pop     r14
0x1402138ca  pop     r13
0x1402138cc  pop     r12
0x1402138ce  pop     rdi
0x1402138cf  pop     rsi
0x1402138d0  pop     rbx
0x1402138d1  retn
```
