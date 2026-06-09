# MemoryBlock::CreateMemoryBlock(void *,_VID_MEMORY_BLOCK_CONFIG *,MemoryBlock::_ADDITIONAL_MB_ATTRIBUTES,unsigned __int64,PoisonedPageContainer *,_VID_FILE_MAPPING *,MemoryTraceTracker &)

- ea: `0x140204ef0`
- end: `0x1402053db`
- name: `?CreateMemoryBlock@MemoryBlock@@KAPEAV1@PEAXPEAU_VID_MEMORY_BLOCK_CONFIG@@T_ADDITIONAL_MB_ATTRIBUTES@1@_KPEAVPoisonedPageContainer@@PEAU_VID_FILE_MAPPING@@AEAUMemoryTraceTracker@@@Z`
- size: `1259`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1400b06d0`
- `0x1400c52d0`
- `0x1401f5848`

## callees

- `0x14001f8dc`
- `0x140020b1c`
- `0x140039e50`
- `0x140044f50`
- `0x14004c600`
- `0x14004fcf8`
- `0x140083990`
- `0x1400cbae8`
- `0x14011ea40`
- `0x14011edec`
- `0x14011f6fc`
- `0x1401eec44`
- `0x140203b34`
- `0x140204b08`
- `0x140204ef0`

## import_xrefs

- `vid!VidQueryMemoryBlockInformation` at `0x140205233`
- `vid!VidQueryMemoryBlockInformation` at `0x140205233`
- `vid!VidCreateMemoryBlock` at `0x140205191`
- `vid!VidCreateMemoryBlock` at `0x140205191`
- `vid!VidCreateDaxFileMemoryBlock` at `0x140205120`
- `vid!VidCreateDaxFileMemoryBlock` at `0x140205120`

## string_xrefs

- `0x140205147`: `PageCountTotal = %I64x, MbCreateFlags = %I64x, VirtualNode = %u, PersistId = %I64u`
- `0x1402051c7`: `PageCountTotal = %I64x, PageCountValid = %I64x, MbCreateFlags = %I64x, BackingBitmapBufferSizeInBytes = %I64u, VirtualNode = %u, PersistId = %I64u`

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
  MemoryTraceTracker::IncreaseTimeSpentInOperation(v44, &off_1402E4108);
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
0x140204ef0  mov     [rsp+arg_18], r9
0x140204ef5  push    rbx
0x140204ef6  push    rsi
0x140204ef7  push    rdi
0x140204ef8  push    r12
0x140204efa  push    r13
0x140204efc  push    r14
0x140204efe  push    r15
0x140204f00  sub     rsp, 2C0h
0x140204f07  mov     rax, cs:__security_cookie
0x140204f0e  xor     rax, rsp
0x140204f11  mov     [rsp+2F8h+var_48], rax
0x140204f19  mov     ebx, r8d
0x140204f1c  mov     r12, rdx
0x140204f1f  mov     r15, rcx
0x140204f22  mov     [rsp+2F8h+var_268], rdx
0x140204f2a  mov     r13, [rsp+2F8h+arg_20]
0x140204f32  mov     rsi, [rsp+2F8h+arg_28]
0x140204f3a  mov     [rsp+2F8h+var_280], rsi
0x140204f3f  mov     r14, [rsp+2F8h+arg_30]
0x140204f47  mov     [rsp+2F8h+var_278], r14
0x140204f4f  mov     ecx, 0F8h; Size
0x140204f54  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140204f59  mov     rdi, rax
0x140204f5c  mov     [rsp+2F8h+var_298], rax
0x140204f61  xor     edx, edx; Val
0x140204f63  mov     r8d, 0F8h; Size
0x140204f69  mov     rcx, rax; void *
0x140204f6c  call    memset_0
0x140204f71  mov     rcx, rdi; this
0x140204f74  call    ??0MemoryBlock@@AEAA@XZ; MemoryBlock::MemoryBlock(void)
0x140204f79  nop
0x140204f7a  mov     [rsp+2F8h+var_248], rax
0x140204f82  lea     rax, [rsp+2F8h+var_248]
0x140204f8a  mov     [rsp+2F8h+var_258], rax
0x140204f92  mov     [rsp+2F8h+var_250], 1
0x140204f9a  xor     edx, edx; Val
0x140204f9c  mov     r8d, 1B0h; Size
0x140204fa2  lea     rcx, [rsp+2F8h+var_238]; void *
0x140204faa  call    memset_0
0x140204faf  mov     rdx, r14
0x140204fb2  lea     rcx, [rsp+2F8h+var_238]
0x140204fba  call    ??0?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAA@AEBUMemoryTraceTracker@@@Z; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>(MemoryTraceTracker const &)
0x140204fbf  nop
0x140204fc0  test    rsi, rsi
0x140204fc3  jz      short loc_140204FCB
0x140204fc5  mov     rax, [rsi+8]
0x140204fc9  jmp     short loc_140204FCD
0x140204fcb  xor     eax, eax
0x140204fcd  mov     [rsp+2F8h+var_288], rax
0x140204fd2  lea     rdi, [r12+48h]
0x140204fd7  test    r13, r13
0x140204fda  jz      short loc_140204FE2
0x140204fdc  mov     rax, [r13+8]
0x140204fe0  jmp     short loc_140204FE4
0x140204fe2  xor     eax, eax
0x140204fe4  mov     [rsp+2F8h+var_298], rax
0x140204fe9  lea     rsi, [r12+41h]
0x140204fee  lea     rdx, [r12+28h]
0x140204ff3  mov     eax, ebx
0x140204ff5  and     eax, 1
0x140204ff8  mov     dword ptr [rsp+2F8h+var_290], eax
0x140204ffc  lea     r14, [r12+10h]
0x140205001  lea     rax, [r12+18h]
0x140205006  lea     r8, [rsp+2F8h+var_288]
0x14020500b  mov     [rsp+2F8h+var_2A0], r8; __int64
0x140205010  mov     [rsp+2F8h+var_2A8], rdi; __int64
0x140205015  lea     r8, [rsp+2F8h+var_298]
0x14020501a  mov     [rsp+2F8h+var_2B0], r8; __int64
0x14020501f  mov     [rsp+2F8h+var_2B8], rsi; __int64
0x140205024  lea     r8, [rsp+2F8h+arg_18]
0x14020502c  mov     [rsp+2F8h+var_2C0], r8; __int64
0x140205031  mov     [rsp+2F8h+var_2C8], rdx; __int64
0x140205036  lea     rdx, [rsp+2F8h+var_290]
0x14020503b  mov     [rsp+2F8h+var_2D0], rdx; __int64
0x140205040  mov     [rsp+2F8h+var_2D8], rax; __int64
0x140205045  mov     r9, r14
0x140205048  lea     r8, [r12+8]
0x14020504d  mov     rdx, r12
0x140205050  lea     rcx, [rsp+2F8h+var_238]; struct _GUID *
0x140205058  call    ??$Start@AEA_KAEA_KAEA_KAEA_KHAEA_KAEA_KAEAE_KAEA_K_K@?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAAXAEA_K000$$QEAH00AEAE$$QEA_K03@Z; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::Start<unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,int,unsigned __int64 &,unsigned __int64 &,uchar &,unsigned __int64,unsigned __int64 &,unsigned __int64>(unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,int &&,unsigned __int64 &,unsigned __int64 &,uchar &,unsigned __int64 &&,unsigned __int64 &,unsigned __int64 &&)
0x14020505d  mov     rax, [rsp+2F8h+var_248]
0x140205065  mov     [rax+0A0h], r15
0x14020506c  mov     cl, [r14]
0x14020506f  and     cl, 1
0x140205072  mov     rax, [rsp+2F8h+var_248]
0x14020507a  mov     [rax], cl
0x14020507c  mov     cl, bl
0x14020507e  and     cl, 1
0x140205081  mov     rax, [rsp+2F8h+var_248]
0x140205089  mov     [rax+1], cl
0x14020508c  mov     ecx, ebx
0x14020508e  shr     ecx, 1
0x140205090  and     cl, 1
0x140205093  mov     rax, [rsp+2F8h+var_248]
0x14020509b  mov     [rax+2], cl
0x14020509e  shr     ebx, 2
0x1402050a1  and     bl, 1
0x1402050a4  mov     rax, [rsp+2F8h+var_248]
0x1402050ac  mov     [rax+3], bl
0x1402050af  mov     rcx, [r14]
0x1402050b2  mov     rax, [rsp+2F8h+var_248]
0x1402050ba  mov     [rax+0A8h], rcx
0x1402050c1  mov     cl, [rsi]
0x1402050c3  mov     rax, [rsp+2F8h+var_248]
0x1402050cb  mov     [rax+0B8h], cl
0x1402050d1  mov     r15, [r14]
0x1402050d4  mov     [rsp+2F8h+var_298], r15
0x1402050d9  mov     rcx, [rsp+2F8h+var_248]
0x1402050e1  test    r15b, 40h
0x1402050e5  jz      loc_14020516C
0x1402050eb  mov     rdi, [rdi]
0x1402050ee  movzx   ebx, byte ptr [rsi]
0x1402050f1  mov     rsi, [r12]
0x1402050f5  lea     rax, [rcx+98h]
0x1402050fc  mov     [rsp+2F8h+var_2C8], rax
0x140205101  mov     rax, [rsp+2F8h+var_280]
0x140205106  mov     [rsp+2F8h+var_2D0], rax
0x14020510b  mov     [rsp+2F8h+var_2D8], rdi
0x140205110  mov     r9b, bl
0x140205113  mov     r8, r15
0x140205116  mov     rdx, rsi
0x140205119  mov     rcx, [rcx+0A0h]
0x140205120  call    cs:__imp_VidCreateDaxFileMemoryBlock
0x140205127  nop     dword ptr [rax+rax+00h]
0x14020512c  mov     rcx, [rsp+2F8h]; this
0x140205134  mov     [rsp+2F8h+var_2B8], rdi
0x140205139  mov     dword ptr [rsp+2F8h+var_2C0], ebx
0x14020513d  mov     [rsp+2F8h+var_2C8], r15
0x140205142  mov     [rsp+2F8h+var_2D0], rsi; char *
0x140205147  lea     rdx, aPagecounttotal_1; "PageCountTotal = %I64x, MbCreateFlags ="...
0x14020514e  mov     [rsp+2F8h+var_2D8], rdx; int
0x140205153  mov     r9d, eax; char *
0x140205156  lea     r8, aOnecoreVmWorke_68; "onecore\\vm\\worker\\memory\\memorybloc"...
0x14020515d  mov     edx, 0D0h; void *
0x140205162  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x140205167  jmp     loc_1402051EC
0x14020516c  mov     rbx, [rdi]
0x14020516f  movzx   edi, byte ptr [rsi]
0x140205172  mov     rsi, [r12+28h]
0x140205177  mov     r14, [r12+8]
0x14020517c  mov     r15, [r12]
0x140205180  lea     r8, [rcx+98h]
0x140205187  mov     rdx, r12
0x14020518a  mov     rcx, [rcx+0A0h]
0x140205191  call    cs:__imp_VidCreateMemoryBlock
0x140205198  nop     dword ptr [rax+rax+00h]
0x14020519d  mov     rcx, [rsp+2F8h]; this
0x1402051a5  mov     [rsp+2F8h+var_2A8], rbx
0x1402051aa  mov     dword ptr [rsp+2F8h+var_2B0], edi
0x1402051ae  mov     [rsp+2F8h+var_2B8], rsi
0x1402051b3  mov     rdx, [rsp+2F8h+var_298]
0x1402051b8  mov     [rsp+2F8h+var_2C0], rdx
0x1402051bd  mov     [rsp+2F8h+var_2C8], r14
0x1402051c2  mov     [rsp+2F8h+var_2D0], r15; char *
0x1402051c7  lea     rdx, aPagecounttotal; "PageCountTotal = %I64x, PageCountValid "...
0x1402051ce  mov     [rsp+2F8h+var_2D8], rdx; int
0x1402051d3  mov     r9d, eax; char *
0x1402051d6  lea     r8, aOnecoreVmWorke_68; "onecore\\vm\\worker\\memory\\memorybloc"...
0x1402051dd  mov     edx, 0E1h; void *
0x1402051e2  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1402051e7  lea     r14, [r12+10h]
0x1402051ec  test    byte ptr [r14], 8
0x1402051f0  jz      short loc_14020525C
0x1402051f2  mov     rcx, [rsp+2F8h+var_248]
0x1402051fa  lea     rax, [rcx+0F0h]
0x140205201  mov     [rsp+2F8h+var_2C0], 0
0x14020520a  mov     dword ptr [rsp+2F8h+var_2C8], 8
0x140205212  mov     [rsp+2F8h+var_2D0], rax
0x140205217  mov     dword ptr [rsp+2F8h+var_2D8], 0
0x14020521f  xor     r9d, r9d
0x140205222  xor     r8d, r8d
0x140205225  mov     rdx, [rcx+98h]
0x14020522c  mov     rcx, [rcx+0A0h]
0x140205233  call    cs:__imp_VidQueryMemoryBlockInformation
0x14020523a  nop     dword ptr [rax+rax+00h]
0x14020523f  mov     rcx, [rsp+2F8h]; this
0x140205247  test    eax, eax
0x140205249  jnz     short loc_14020525C
0x14020524b  lea     r8, aOnecoreVmWorke_68; "onecore\\vm\\worker\\memory\\memorybloc"...
0x140205252  mov     edx, 0F2h; void *
0x140205257  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14020525c  mov     rcx, [r12]
0x140205260  mov     rax, [rsp+2F8h+var_248]
0x140205268  mov     [rax+70h], rcx
0x14020526c  mov     rcx, [r12+8]
0x140205271  mov     rax, [rsp+2F8h+var_248]
0x140205279  mov     [rax+78h], rcx
0x14020527d  mov     rax, [rsp+2F8h+var_248]
0x140205285  mov     rcx, [rsp+2F8h+arg_18]
0x14020528d  mov     [rax+80h], rcx
0x140205294  test    r13, r13
0x140205297  jz      short loc_1402052E4
0x140205299  test    byte ptr [r14], 44h
0x14020529d  jnz     short loc_1402052BD
0x14020529f  mov     rdx, [rsp+2F8h+var_248]
0x1402052a7  mov     r8, [rdx+98h]; void *
0x1402052ae  mov     rdx, [rdx+0A0h]; void *
0x1402052b5  mov     rcx, r13; this
0x1402052b8  call    ?Mark@PoisonedPageContainer@@QEAAXPEAX0@Z; PoisonedPageContainer::Mark(void *,void *)
0x1402052bd  mov     rbx, [rsp+2F8h+var_248]
0x1402052c5  add     rbx, 0C0h
0x1402052cc  cmp     rbx, r13
0x1402052cf  jz      short loc_1402052E4
0x1402052d1  mov     rcx, rbx
0x1402052d4  call    ?clear@?$_Tree@V?$_Tset_traits@PEAVHyperVStorageObjectTable@@U?$less@PEAVHyperVStorageObjectTable@@@std@@V?$allocator@PEAVHyperVStorageObjectTable@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<HyperVStorageObjectTable *,std::less<HyperVStorageObjectTable *>,std::allocator<HyperVStorageObjectTable *>,0>>::clear(void)
0x1402052d9  mov     rdx, r13
0x1402052dc  mov     rcx, rbx
0x1402052df  call    ??$_Copy@$0A@@?$_Tree@V?$_Tset_traits@_KU?$less@_K@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::_Copy<0>(std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>> const &)
0x1402052e4  test    byte ptr [r14], 4
0x1402052e8  jz      short loc_1402052FE
0x1402052ea  mov     rdx, [r12+48h]
0x1402052ef  mov     rax, [rsp+2F8h+var_248]
0x1402052f7  mov     [rax+0D0h], rdx
0x1402052fe  lea     rcx, [rsp+2F8h+var_238]
0x140205306  call    ?Stop@?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAANXZ; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::Stop(void)
0x14020530b  movaps  xmm2, xmm0
0x14020530e  lea     rdx, off_1402E4108; "CreatingRamMemoryBlocks"
0x140205315  mov     rcx, [rsp+2F8h+var_278]
0x14020531d  call    ?IncreaseTimeSpentInOperation@MemoryTraceTracker@@QEAAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@N@Z; MemoryTraceTracker::IncreaseTimeSpentInOperation(std::basic_string_view<ushort> const &,double)
0x140205322  mov     rbx, [rsp+2F8h+var_248]
0x14020532a  cmp     byte ptr [rbx], 0
0x14020532d  jz      short loc_1402053A6
0x14020532f  mov     rcx, cs:?gm_SingletonInstance@MemoryManagerStats@@0PEAV1@EA; MemoryManagerStats * MemoryManagerStats::gm_SingletonInstance
0x140205336  cmp     [rsp+2F8h+var_1F6], 0
0x14020533e  jz      short loc_14020534B
0x140205340  movsd   xmm0, [rsp+2F8h+var_1E0]
0x140205349  jmp     short loc_14020534E
0x14020534b  xorps   xmm0, xmm0
0x14020534e  mov     r8, [rcx]
0x140205351  test    r8, r8
0x140205354  jz      short loc_1402053A6
0x140205356  mulsd   xmm0, cs:__real@412e848000000000
0x14020535e  xor     eax, eax
0x140205360  movsd   xmm1, cs:__real@43e0000000000000
0x140205368  comisd  xmm0, xmm1
0x14020536c  jb      short loc_140205385
0x14020536e  subsd   xmm0, xmm1
0x140205372  comisd  xmm0, xmm1
0x140205376  jnb     short loc_140205385
0x140205378  mov     rdx, 8000000000000000h
0x140205382  mov     rax, rdx
0x140205385  cvttsd2si rdx, xmm0
0x14020538a  add     rdx, rax
0x14020538d  mov     rax, [rcx+8]
0x140205391  mov     ecx, [rax+0DCh]
0x140205397  add     rcx, [r8]
0x14020539a  lock add [rcx], rdx
0x14020539e  mov     rbx, [rsp+2F8h+var_248]
0x1402053a6  lea     rcx, [rsp+2F8h+var_238]
0x1402053ae  call    ??1?$MemoryTrace@VCreateRamMemoryBlock@VmWorkerTrace@@@@QEAA@XZ; MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>::~MemoryTrace<VmWorkerTrace::CreateRamMemoryBlock>(void)
0x1402053b3  nop
0x1402053b4  mov     rax, rbx
0x1402053b7  mov     rcx, [rsp+2F8h+var_48]
0x1402053bf  xor     rcx, rsp; StackCookie
0x1402053c2  call    __security_check_cookie
0x1402053c7  add     rsp, 2C0h
0x1402053ce  pop     r15
0x1402053d0  pop     r14
0x1402053d2  pop     r13
0x1402053d4  pop     r12
0x1402053d6  pop     rdi
0x1402053d7  pop     rsi
0x1402053d8  pop     rbx
0x1402053d9  retn
```
