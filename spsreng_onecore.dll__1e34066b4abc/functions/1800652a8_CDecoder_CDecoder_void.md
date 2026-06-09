# CDecoder::~CDecoder(void)

- ea: `0x1800652a8`
- end: `0x18006562f`
- name: `??1CDecoder@@QEAA@XZ`
- size: `903`
- prototype: `void __fastcall(CDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1800afd80`

## callees

- `0x180002aac`
- `0x1800034e0`
- `0x180006abc`
- `0x18005ae60`
- `0x1800652a8`
- `0x180065678`
- `0x180065774`
- `0x1800657f4`
- `0x18006581c`
- `0x180065884`
- `0x1800658ac`
- `0x180067518`
- `0x18006c0b0`
- `0x18006c184`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800654c7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800654c7`

## pseudocode

```c
void __fastcall CDecoder::~CDecoder(CDecoder *this)
{
  RCDFanoutCache *v2; // r14
  __int64 i; // rdi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  unsigned int v6; // edx
  CStreamPair *v7; // rcx
  CLatticeWrapper *v8; // rcx
  __int64 j; // rdi
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  unsigned int v12; // edx
  CPhraseStatContainer *v13; // rcx
  CUgtFilter *v14; // rcx
  CWFSTDecoder *v15; // rcx

  v2 = (CDecoder *)((char *)this + 6432);
  RCDFanoutCache::Reset((CDecoder *)((char *)this + 6432));
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 826));
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 828));
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 900));
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 431));
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 430));
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 357));
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 358));
  for ( i = 0; i != 16; ++i )
  {
    CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + i + 862));
    CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + i + 878));
    CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + i + 830));
    CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + i + 341));
    CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + i + 325));
  }
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 437));
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 438));
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 859));
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 320));
  CVirtualArrayVoid<0>::ReleaseVoid((char *)this + 8);
  *((_DWORD *)this + 10) = 0;
  CVirtualArrayVoid<0>::ReleaseVoid((char *)this + 7280);
  *((_DWORD *)this + 1828) = 0;
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 442);
  if ( v4 )
    (**v4)(v4, 1);
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 443);
  if ( v5 )
    (**v5)(v5, 1);
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 440));
  CDecoder::DiscardLattice(this);
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 61));
  v7 = (CStreamPair *)*((_QWORD *)this + 63);
  if ( v7 )
    CStreamPair::`scalar deleting destructor'(v7, v6);
  v8 = (CLatticeWrapper *)*((_QWORD *)this + 65);
  if ( v8 )
    CLatticeWrapper::`scalar deleting destructor'(v8, v6);
  for ( j = 0; j != 16; ++j )
  {
    v10 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + j + 29);
    if ( v10 )
      (**v10)(v10, 1);
    v11 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + j + 45);
    if ( v11 )
      (**v11)(v11, 1);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 15);
  v13 = (CPhraseStatContainer *)*((_QWORD *)this + 959);
  if ( v13 )
  {
    CPhraseStatContainer::`scalar deleting destructor'(v13, v12);
    *((_QWORD *)this + 959) = 0;
  }
  v14 = (CUgtFilter *)*((_QWORD *)this + 407);
  if ( v14 )
    CUgtFilter::`scalar deleting destructor'(v14, v12);
  v15 = (CWFSTDecoder *)*((_QWORD *)this + 857);
  if ( v15 )
    CWFSTDecoder::`scalar deleting destructor'(v15, v12);
  CWinHeap::Free(*((CWinHeap **)this + 9), *((void **)this + 855));
  `eh vector destructor iterator'(
    (char *)this + 7376,
    0x108u,
    1u,
    (void (*)(void *))CChannelPartition::~CChannelPartition);
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 7344));
  *((_DWORD *)this + 1828) = 0;
  CVirtualArrayVoid<0>::ReleaseVoid((char *)this + 7280);
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 7256));
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 7232));
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 6568));
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 6536));
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 6504));
  RCDFanoutCache::~RCDFanoutCache(v2);
  `eh vector destructor iterator'((char *)this + 3568, 0xB0u, 0x10u, (void (*)(void *))cfData::~cfData);
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 2520));
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 2488));
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 2464));
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 2432));
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 2392));
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 2360));
  CGrowableArrayVoid::~CGrowableArrayVoid((CDecoder *)((char *)this + 2336));
  NGTreeProbCacheSize<64>::Release((CDecoder *)((char *)this + 680));
  *((_DWORD *)this + 10) = 0;
  CVirtualArrayVoid<0>::ReleaseVoid((char *)this + 8);
}

```

## disassembly

```asm
0x1800652a8  push    rbx
0x1800652aa  push    rbp
0x1800652ab  push    rsi
0x1800652ac  push    rdi
0x1800652ad  push    r12
0x1800652af  push    r14
0x1800652b1  sub     rsp, 28h
0x1800652b5  mov     rbx, rcx
0x1800652b8  lea     r14, [rcx+1920h]
0x1800652bf  mov     rcx, r14; this
0x1800652c2  call    ?Reset@RCDFanoutCache@@QEAAXXZ; RCDFanoutCache::Reset(void)
0x1800652c7  mov     rdx, [rbx+19D0h]; void *
0x1800652ce  mov     rcx, [rbx+48h]; this
0x1800652d2  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800652d7  mov     rdx, [rbx+19E0h]; void *
0x1800652de  mov     rcx, [rbx+48h]; this
0x1800652e2  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800652e7  mov     rdx, [rbx+1C20h]; void *
0x1800652ee  mov     rcx, [rbx+48h]; this
0x1800652f2  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800652f7  mov     rdx, [rbx+0D78h]; void *
0x1800652fe  mov     rcx, [rbx+48h]; this
0x180065302  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180065307  mov     rdx, [rbx+0D70h]; void *
0x18006530e  mov     rcx, [rbx+48h]; this
0x180065312  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180065317  mov     rdx, [rbx+0B28h]; void *
0x18006531e  mov     rcx, [rbx+48h]; this
0x180065322  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180065327  mov     rdx, [rbx+0B30h]; void *
0x18006532e  mov     rcx, [rbx+48h]; this
0x180065332  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180065337  xor     edi, edi
0x180065339  lea     r12d, [rdi+1]
0x18006533d  mov     rdx, [rbx+rdi*8+1AF0h]; void *
0x180065345  mov     rcx, [rbx+48h]; this
0x180065349  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18006534e  mov     rdx, [rbx+rdi*8+1B70h]; void *
0x180065356  mov     rcx, [rbx+48h]; this
0x18006535a  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18006535f  mov     rdx, [rbx+rdi*8+19F0h]; void *
0x180065367  mov     rcx, [rbx+48h]; this
0x18006536b  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180065370  mov     rdx, [rbx+rdi*8+0AA8h]; void *
0x180065378  mov     rcx, [rbx+48h]; this
0x18006537c  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180065381  mov     rdx, [rbx+rdi*8+0A28h]; void *
0x180065389  mov     rcx, [rbx+48h]; this
0x18006538d  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180065392  add     rdi, r12
0x180065395  cmp     rdi, 10h
0x180065399  jnz     short loc_18006533D
0x18006539b  mov     rdx, [rbx+0DA8h]; void *
0x1800653a2  mov     rcx, [rbx+48h]; this
0x1800653a6  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800653ab  mov     rdx, [rbx+0DB0h]; void *
0x1800653b2  mov     rcx, [rbx+48h]; this
0x1800653b6  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800653bb  mov     rdx, [rbx+1AD8h]; void *
0x1800653c2  mov     rcx, [rbx+48h]; this
0x1800653c6  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800653cb  mov     rdx, [rbx+0A00h]; void *
0x1800653d2  mov     rcx, [rbx+48h]; this
0x1800653d6  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800653db  lea     rcx, [rbx+8]
0x1800653df  call    ?ReleaseVoid@?$CVirtualArrayVoid@$0A@@@IEAAXXZ; CVirtualArrayVoid<0>::ReleaseVoid(void)
0x1800653e4  mov     dword ptr [rbx+28h], 0
0x1800653eb  lea     rbp, [rbx+1C70h]
0x1800653f2  mov     rcx, rbp
0x1800653f5  call    ?ReleaseVoid@?$CVirtualArrayVoid@$0A@@@IEAAXXZ; CVirtualArrayVoid<0>::ReleaseVoid(void)
0x1800653fa  mov     dword ptr [rbp+20h], 0
0x180065401  mov     rcx, [rbx+0DD0h]
0x180065408  test    rcx, rcx
0x18006540b  jz      short loc_18006541B
0x18006540d  mov     rax, [rcx]
0x180065410  mov     edx, r12d
0x180065413  mov     rax, [rax]
0x180065416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006541b  mov     rcx, [rbx+0DD8h]
0x180065422  test    rcx, rcx
0x180065425  jz      short loc_180065435
0x180065427  mov     rax, [rcx]
0x18006542a  mov     edx, r12d
0x18006542d  mov     rax, [rax]
0x180065430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065435  mov     rdx, [rbx+0DC0h]; void *
0x18006543c  mov     rcx, [rbx+48h]; this
0x180065440  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180065445  mov     rcx, rbx; this
0x180065448  call    ?DiscardLattice@CDecoder@@QEAAXXZ; CDecoder::DiscardLattice(void)
0x18006544d  mov     rdx, [rbx+1E8h]; void *
0x180065454  mov     rcx, [rbx+48h]; this
0x180065458  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18006545d  mov     rcx, [rbx+1F8h]; this
0x180065464  test    rcx, rcx
0x180065467  jz      short loc_18006546E
0x180065469  call    ??_GCStreamPair@@QEAAPEAXI@Z; CStreamPair::`scalar deleting destructor'(uint)
0x18006546e  mov     rcx, [rbx+208h]; this
0x180065475  test    rcx, rcx
0x180065478  jz      short loc_18006547F
0x18006547a  call    ??_GCLatticeWrapper@@AEAAPEAXI@Z; CLatticeWrapper::`scalar deleting destructor'(uint)
0x18006547f  xor     edi, edi
0x180065481  mov     rcx, [rbx+rdi*8+0E8h]
0x180065489  test    rcx, rcx
0x18006548c  jz      short loc_18006549C
0x18006548e  mov     rax, [rcx]
0x180065491  mov     edx, r12d
0x180065494  mov     rax, [rax]
0x180065497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006549c  mov     rcx, [rbx+rdi*8+168h]
0x1800654a4  test    rcx, rcx
0x1800654a7  jz      short loc_1800654B7
0x1800654a9  mov     rax, [rcx]
0x1800654ac  mov     edx, r12d
0x1800654af  mov     rax, [rax]
0x1800654b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654b7  add     rdi, r12
0x1800654ba  cmp     rdi, 10h
0x1800654be  jnz     short loc_180065481
0x1800654c0  lea     rcx, [rbx+258h]; lpCriticalSection
0x1800654c7  call    cs:__imp_DeleteCriticalSection
0x1800654cd  mov     rcx, [rbx+1DF8h]; this
0x1800654d4  test    rcx, rcx
0x1800654d7  jz      short loc_1800654E9
0x1800654d9  call    ??_GCPhraseStatContainer@@QEAAPEAXI@Z; CPhraseStatContainer::`scalar deleting destructor'(uint)
0x1800654de  mov     qword ptr [rbx+1DF8h], 0
0x1800654e9  mov     rcx, [rbx+0CB8h]; this
0x1800654f0  test    rcx, rcx
0x1800654f3  jz      short loc_1800654FA
0x1800654f5  call    ??_GCUgtFilter@@QEAAPEAXI@Z; CUgtFilter::`scalar deleting destructor'(uint)
0x1800654fa  mov     rcx, [rbx+1AC8h]; this
0x180065501  test    rcx, rcx
0x180065504  jz      short loc_18006550B
0x180065506  call    ??_GCWFSTDecoder@@QEAAPEAXI@Z; CWFSTDecoder::`scalar deleting destructor'(uint)
0x18006550b  mov     rdx, [rbx+1AB8h]; void *
0x180065512  mov     rcx, [rbx+48h]; this
0x180065516  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18006551b  lea     rcx, [rbx+1CD0h]; void *
0x180065522  lea     r9, ??1CChannelPartition@@QEAA@XZ; void (*)(void *)
0x180065529  mov     r8, r12; unsigned __int64
0x18006552c  mov     edx, 108h; unsigned __int64
0x180065531  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180065536  lea     rcx, [rbx+1CB0h]; this
0x18006553d  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x180065542  mov     dword ptr [rbp+20h], 0
0x180065549  mov     rcx, rbp
0x18006554c  call    ?ReleaseVoid@?$CVirtualArrayVoid@$0A@@@IEAAXXZ; CVirtualArrayVoid<0>::ReleaseVoid(void)
0x180065551  lea     rcx, [rbx+1C58h]; this
0x180065558  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18006555d  lea     rcx, [rbx+1C40h]; this
0x180065564  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x180065569  lea     rcx, [rbx+19A8h]; this
0x180065570  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x180065575  lea     rcx, [rbx+1988h]; this
0x18006557c  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x180065581  lea     rcx, [rbx+1968h]; this
0x180065588  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18006558d  mov     rcx, r14; this
0x180065590  call    ??1RCDFanoutCache@@QEAA@XZ; RCDFanoutCache::~RCDFanoutCache(void)
0x180065595  lea     rcx, [rbx+0DF0h]; void *
0x18006559c  lea     r9, ??1cfData@@QEAA@XZ; void (*)(void *)
0x1800655a3  mov     edx, 0B0h; unsigned __int64
0x1800655a8  mov     r8d, 10h; unsigned __int64
0x1800655ae  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800655b3  lea     rcx, [rbx+9D8h]; this
0x1800655ba  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x1800655bf  lea     rcx, [rbx+9B8h]; this
0x1800655c6  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x1800655cb  lea     rcx, [rbx+9A0h]; this
0x1800655d2  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x1800655d7  lea     rcx, [rbx+980h]; this
0x1800655de  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x1800655e3  lea     rcx, [rbx+958h]; this
0x1800655ea  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x1800655ef  lea     rcx, [rbx+938h]; this
0x1800655f6  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x1800655fb  lea     rcx, [rbx+920h]; this
0x180065602  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x180065607  lea     rcx, [rbx+2A8h]; this
0x18006560e  call    ?Release@?$NGTreeProbCacheSize@$0EA@@@IEAAXXZ; NGTreeProbCacheSize<64>::Release(void)
0x180065613  mov     dword ptr [rbx+28h], 0
0x18006561a  lea     rcx, [rbx+8]
0x18006561e  add     rsp, 28h
0x180065622  pop     r14
0x180065624  pop     r12
0x180065626  pop     rdi
0x180065627  pop     rsi
0x180065628  pop     rbp
0x180065629  pop     rbx
0x18006562a  jmp     ?ReleaseVoid@?$CVirtualArrayVoid@$0A@@@IEAAXXZ; CVirtualArrayVoid<0>::ReleaseVoid(void)
```
