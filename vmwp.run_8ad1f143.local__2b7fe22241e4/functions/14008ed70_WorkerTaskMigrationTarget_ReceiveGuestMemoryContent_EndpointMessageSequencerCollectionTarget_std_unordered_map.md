# WorkerTaskMigrationTarget::ReceiveGuestMemoryContent(EndpointMessageSequencerCollectionTarget *,std::unordered_map<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>,std::allocator<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>,std::allocator<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>>>,Vml::VmComPtr<IMigrationTransferDependencyGroup>)

- ea: `0x14008ed70`
- end: `0x14008f2a2`
- name: `?ReceiveGuestMemoryContent@WorkerTaskMigrationTarget@@AEAAJPEAVEndpointMessageSequencerCollectionTarget@@V?$unordered_map@W4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@U?$hash@W4ReplyType@MuxMigrationReply@@@4@U?$equal_to@W4ReplyType@MuxMigrationReply@@@4@V?$allocator@U?$pair@$$CBW4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@@std@@@4@@std@@V?$VmComPtr@UIMigrationTransferDependencyGroup@@@Vml@@@Z`
- size: `1330`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400793b0`
- `0x14008f4f0`

## callees

- `0x14002dd88`
- `0x140032f60`
- `0x14006af58`
- `0x140088c2c`
- `0x1400898a4`
- `0x14008eb9c`
- `0x14008ed70`
- `0x14008f2a8`
- `0x14008f42c`
- `0x14009b170`
- `0x1400a30c8`
- `0x1400a3e48`
- `0x1400a7110`
- `0x1400e2cc4`
- `0x140108fbc`
- `0x140132960`
- `0x140222aa8`
- `0x140222b00`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008edf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008f1e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008edf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14008f1e6`

## string_xrefs

- `0x14008efc8`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008eff9`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f036`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f0b2`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f0e7`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f156`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f187`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`
- `0x14008f243`: `onecore\vm\worker\migration\workertaskmigrationtarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WorkerTaskMigrationTarget::ReceiveGuestMemoryContent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 v8; // rcx
  unsigned int *v9; // r12
  __int64 v10; // rax
  int v11; // r9d
  __int64 v12; // rdi
  int v13; // eax
  int v14; // eax
  EndpointMessageSequencerTarget **v15; // rdi
  EndpointMessageSequencerTarget **v16; // rsi
  __int64 v17; // rdi
  int v18; // eax
  char i; // al
  __int64 v20; // r8
  int v21; // edi
  int v22; // eax
  int v23; // eax
  __int64 result; // rax
  int v25; // eax
  const char *v26; // [rsp+20h] [rbp-198h]
  int v27; // [rsp+20h] [rbp-198h]
  int v28[2]; // [rsp+80h] [rbp-138h] BYREF
  __int64 v29; // [rsp+88h] [rbp-130h] BYREF
  void *v30; // [rsp+90h] [rbp-128h]
  __int64 v31; // [rsp+98h] [rbp-120h]
  __int64 v32; // [rsp+A0h] [rbp-118h]
  _BYTE v33[32]; // [rsp+A8h] [rbp-110h] BYREF
  __int64 v34[8]; // [rsp+C8h] [rbp-F0h] BYREF
  __int64 v35; // [rsp+108h] [rbp-B0h]
  int v36[2]; // [rsp+110h] [rbp-A8h] BYREF
  __int64 v37[4]; // [rsp+118h] [rbp-A0h] BYREF
  __int128 v38; // [rsp+138h] [rbp-80h]
  __int128 v39; // [rsp+148h] [rbp-70h]
  __int128 v40; // [rsp+158h] [rbp-60h]
  __int64 v41; // [rsp+168h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v35 = a3;
  v30 = a4;
  v8 = *(_QWORD *)(a1 + 464);
  try
  {
    *(_QWORD *)(a1 + 472) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 496LL))(v8);
    if ( *(_DWORD *)(a1 + 492) )
    {
      Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(a1 + 592));
      *(_BYTE *)(a1 + 608) = 1;
      *(_DWORD *)(a1 + 600) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 592));
    }
    v32 = 1;
    v31 = a1;
    v37[0] = (__int64)&MigrationTargetMemoryStatistics::`vftable';
    v37[1] = *(_QWORD *)(a1 + 440);
    v37[2] = *(_QWORD *)(a1 + 432);
    v9 = (unsigned int *)(a1 + 612);
    v37[3] = a1 + 612;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    *(_QWORD *)v36 = 0;
    *(_QWORD *)v28 = &v29;
    v10 = *a4;
    *a4 = 0;
    v29 = v10;
    std::_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>>>,0>>::_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>>>,0>>(
      v34,
      a3);
    LOBYTE(v11) = *(_DWORD *)(a1 + 488) != 0;
    CreateVmMigrationMessageHandler(
      (int)v36,
      a1 + 640,
      *(_QWORD *)(a1 + 464),
      v11,
      *(_DWORD *)(a1 + 484) != 0,
      *(_BYTE *)(a1 + 408),
      *(_DWORD *)(a1 + 492) != 0,
      *(_QWORD *)(a1 + 584),
      a1 + 496,
      (__int64)v37,
      *(_QWORD *)(a1 + 440),
      *(_QWORD *)(a1 + 720),
      a2,
      (__int64)v34,
      &v29);
    if ( !(***(unsigned __int8 (__fastcall ****)(_QWORD))(a1 + 720))(*(_QWORD *)(a1 + 720)) )
    {
      for ( i = 1; ; i = 0 )
      {
        *(_QWORD *)v28 = 0;
        v20 = i != 0 ? 900000 : 30000;
        v21 = *(_DWORD *)(a1 + 480) & 8;
        if ( v21 )
          v20 = 3600000;
        v22 = VmMigrationConnection::WaitForRequest(*(_QWORD *)(a1 + 440), 27, v20);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x83B,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)(unsigned int)v22,
            (int)v28);
        v23 = VmMigrationConnection::AcknowledgeMessageSequence(*(VmMigrationConnection **)(a1 + 440), 0, 0);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x83C,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
            (const char *)(unsigned int)v23,
            (int)v28);
        if ( !v21 )
        {
          MigrationTargetMemoryStatistics::OnNewMemoryTransferPassStartedAtTarget((MigrationTargetMemoryStatistics *)v37);
          v25 = VmMigrationConnection::ReceiveAsynchronousMessageSequence(
                  *(_QWORD *)(a1 + 440),
                  6u,
                  *(__int64 *)v36,
                  *v9);
          if ( v25 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x854,
              (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
              (const char *)(unsigned int)v25,
              (int)v28);
        }
      }
    }
    v12 = *(_QWORD *)(VmMigrationConnection::WaitForRequest(*(_QWORD *)(a1 + 440), v33, 48, 900000) + 16);
    std::unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>::~unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>(v33);
    if ( (unsigned __int8)MuxMigrationHeader::TransferRequestHeaderData::Parse(v12) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x80B,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8007000DLL,
        v27);
    v13 = VmMigrationConnection::AcknowledgeMessageSequence(*(VmMigrationConnection **)(a1 + 440), 0, 0);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x80D,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v13,
        v27);
    v14 = VmMigrationConnection::ReceiveAsynchronousMessageSequence(*(_QWORD *)(a1 + 440), 0x31u, *(__int64 *)v36, *v9);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x812,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v14,
        v27);
    if ( a2 )
    {
      v15 = *(EndpointMessageSequencerTarget ***)(a2 + 24);
      v16 = *(EndpointMessageSequencerTarget ***)(a2 + 32);
      while ( v15 != v16 )
      {
        EndpointMessageSequencerTarget::EnsureTransferCompleted(*v15);
        v15 += 2;
      }
    }
    v17 = *(_QWORD *)(VmMigrationConnection::WaitForRequest(*(_QWORD *)(a1 + 440), v33, 48, 30000) + 16);
    std::unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>::~unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>(v33);
    if ( (unsigned __int8)MuxMigrationHeader::TransferRequestHeaderData::Parse(v17) != 1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x81E,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)0x8007000DLL,
        v27);
    v18 = VmMigrationConnection::AcknowledgeMessageSequence(*(VmMigrationConnection **)(a1 + 440), 0, 0);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x820,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
        (const char *)(unsigned int)v18,
        v27);
    std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(v36);
    if ( *(_DWORD *)(a1 + 492) )
    {
      Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(a1 + 592));
      *(_BYTE *)(a1 + 608) = 0;
      *(_DWORD *)(a1 + 600) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 592));
    }
    std::_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>::~_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>(a3);
    Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(a4);
    result = 0;
  }
  catch ( ... )
  {
    v36[0] = wil::details::in1diag3::Return_CaughtExceptionMsg(
               retaddr,
               (void *)0x85D,
               (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationtarget.cpp",
               "Failed to receive guest memory content",
               v26);
    std::_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>::~_Hash<std::_Umap_traits<enum MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<enum MuxMigrationReply::ReplyType,std::hash<enum MuxMigrationReply::ReplyType>,std::equal_to<enum MuxMigrationReply::ReplyType>>,std::allocator<std::pair<enum MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>(v35);
    Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(v30);
    return (unsigned int)v36[0];
  }
  return result;
}

```

## disassembly

```asm
0x14008ed70  push    rbx
0x14008ed72  push    rsi
0x14008ed73  push    rdi
0x14008ed74  push    r12
0x14008ed76  push    r13
0x14008ed78  push    r14
0x14008ed7a  push    r15
0x14008ed7c  sub     rsp, 180h
0x14008ed83  mov     rax, cs:__security_cookie
0x14008ed8a  xor     rax, rsp
0x14008ed8d  mov     [rsp+1B8h+var_48], rax
0x14008ed95  mov     r14, r9
0x14008ed98  mov     r15, r8
0x14008ed9b  mov     rsi, rdx
0x14008ed9e  mov     rbx, rcx
0x14008eda1  mov     [rsp+1B8h+var_B0], r8
0x14008eda9  mov     [rsp+1B8h+var_128], r9
0x14008edb1  mov     rcx, [rcx+1D0h]
0x14008edb8  mov     rax, [rcx]
0x14008edbb  mov     rax, [rax+1F0h]
0x14008edc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008edc7  mov     [rbx+1D8h], rax
0x14008edce  xor     r13d, r13d
0x14008edd1  cmp     [rbx+1ECh], r13d
0x14008edd8  jz      short loc_14008EE03
0x14008edda  lea     rdi, [rbx+250h]
0x14008ede1  mov     rcx, rdi; this
0x14008ede4  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x14008ede9  mov     byte ptr [rbx+260h], 1
0x14008edf0  mov     [rdi+8], r13d
0x14008edf4  mov     rcx, rdi; SRWLock
0x14008edf7  call    cs:__imp_ReleaseSRWLockExclusive
0x14008edfe  nop     dword ptr [rax+rax+00h]
0x14008ee03  xorps   xmm0, xmm0
0x14008ee06  movups  [rsp+1B8h+var_120], xmm0
0x14008ee0e  mov     qword ptr [rsp+1B8h+var_120], rbx
0x14008ee16  mov     byte ptr [rsp+1B8h+var_120+8], 1
0x14008ee1e  lea     rax, ??_7MigrationTargetMemoryStatistics@@6B@; const MigrationTargetMemoryStatistics::`vftable'
0x14008ee25  mov     [rsp+1B8h+var_A0], rax
0x14008ee2d  mov     rax, [rbx+1B8h]
0x14008ee34  mov     [rsp+1B8h+var_98], rax
0x14008ee3c  mov     rax, [rbx+1B0h]
0x14008ee43  mov     [rsp+1B8h+var_90], rax
0x14008ee4b  lea     r12, [rbx+264h]
0x14008ee52  mov     [rsp+1B8h+var_88], r12
0x14008ee5a  movdqu  [rsp+1B8h+var_80], xmm0
0x14008ee63  xorps   xmm1, xmm1
0x14008ee66  movdqu  [rsp+1B8h+var_70], xmm1
0x14008ee6f  movdqu  [rsp+1B8h+var_60], xmm0
0x14008ee78  mov     [rsp+1B8h+var_50], r13
0x14008ee80  mov     qword ptr [rsp+1B8h+var_A8], r13
0x14008ee88  lea     rax, [rsp+1B8h+var_130]
0x14008ee90  mov     qword ptr [rsp+1B8h+var_138], rax
0x14008ee98  mov     rax, [r14]
0x14008ee9b  mov     [r14], r13
0x14008ee9e  mov     [rsp+1B8h+var_130], rax
0x14008eea6  mov     rdx, r15
0x14008eea9  lea     rcx, [rsp+1B8h+var_F0]
0x14008eeb1  call    ??0?$_Hash@V?$_Umap_traits@W4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@@2@@std@@V?$_Uhash_compare@W4ReplyType@MuxMigrationReply@@U?$hash@W4ReplyType@MuxMigrationReply@@@std@@U?$equal_to@W4ReplyType@MuxMigrationReply@@@4@@4@V?$allocator@U?$pair@$$CBW4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@@2@@std@@@std@@@4@$0A@@std@@@std@@IEAA@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>>>,0>>::_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>>>,0>>(std::_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::IReplyProcessor>>>>,0>> &&)
0x14008eeb6  lea     rcx, [rbx+1F0h]
0x14008eebd  cmp     [rbx+1ECh], r13d
0x14008eec4  setnz   r8b
0x14008eec8  cmp     [rbx+1E4h], r13d
0x14008eecf  setnz   r10b
0x14008eed3  cmp     [rbx+1E8h], r13d
0x14008eeda  setnz   r9b; int
0x14008eede  lea     rdx, [rbx+280h]; int
0x14008eee5  lea     rax, [rsp+1B8h+var_130]
0x14008eeed  mov     [rsp+1B8h+var_148], rax; void *
0x14008eef2  lea     rax, [rsp+1B8h+var_F0]
0x14008eefa  mov     [rsp+1B8h+var_150], rax; __int64
0x14008eeff  mov     [rsp+1B8h+var_158], rsi; __int64
0x14008ef04  mov     rax, [rbx+2D0h]
0x14008ef0b  mov     [rsp+1B8h+var_160], rax; __int64
0x14008ef10  mov     rax, [rbx+1B8h]
0x14008ef17  mov     [rsp+1B8h+var_168], rax; __int64
0x14008ef1c  lea     rax, [rsp+1B8h+var_A0]
0x14008ef24  mov     [rsp+1B8h+var_170], rax; __int64
0x14008ef29  mov     [rsp+1B8h+var_178], rcx; __int64
0x14008ef2e  mov     rax, [rbx+248h]
0x14008ef35  mov     [rsp+1B8h+var_180], rax; __int64
0x14008ef3a  mov     [rsp+1B8h+var_188], r8b; char
0x14008ef3f  mov     al, [rbx+198h]
0x14008ef45  mov     [rsp+1B8h+var_190], al; char
0x14008ef49  mov     [rsp+1B8h+var_198], r10b; int
0x14008ef4e  mov     r8, [rbx+1D0h]; int
0x14008ef55  lea     rcx, [rsp+1B8h+var_A8]; int
0x14008ef5d  call    ?CreateVmMigrationMessageHandler@@YA?AV?$unique_ptr@VIVmMigrationMessageHandler@@U?$default_delete@VIVmMigrationMessageHandler@@@std@@@std@@PEBVWorkerTaskMigrationTargetSettings@@PEAUIMemoryManager@@_N222_KPEAV?$GmoMigrationQueue@UDECOMPRESSOR_INFO@WorkerTaskMigrationTarget@@@@PEAVMigrationTargetMemoryStatistics@@PEAVVmMigrationConnection@@PEAVIMigrationTransferOrchestratorTarget@@PEAVEndpointMessageSequencerCollectionTarget@@V?$unordered_map@W4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@U?$hash@W4ReplyType@MuxMigrationReply@@@4@U?$equal_to@W4ReplyType@MuxMigrationReply@@@4@V?$allocator@U?$pair@$$CBW4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@@std@@@4@@2@V?$VmComPtr@UIMigrationTransferDependencyGroup@@@Vml@@@Z; CreateVmMigrationMessageHandler(WorkerTaskMigrationTargetSettings const *,IMemoryManager *,bool,bool,bool,bool,unsigned __int64,GmoMigrationQueue<WorkerTaskMigrationTarget::DECOMPRESSOR_INFO> *,MigrationTargetMemoryStatistics *,VmMigrationConnection *,IMigrationTransferOrchestratorTarget *,EndpointMessageSequencerCollectionTarget *,std::unordered_map<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>,Vml::VmComPtr<IMigrationTransferDependencyGroup>)
0x14008ef62  nop
0x14008ef63  mov     rcx, [rbx+2D0h]
0x14008ef6a  mov     rax, [rcx]
0x14008ef6d  mov     rax, [rax]
0x14008ef70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ef75  test    al, al
0x14008ef77  jz      loc_14008F0F8
0x14008ef7d  mov     r9d, 0DBBA0h
0x14008ef83  mov     r8d, 30h ; '0'
0x14008ef89  lea     rdx, [rsp+1B8h+var_110]
0x14008ef91  mov     rcx, [rbx+1B8h]
0x14008ef98  call    ?WaitForRequest@VmMigrationConnection@@QEAA?AU?$pair@V?$unique_ptr@VVmMigrationNetworkBuffer@@VVmMigrationNetworkBufferDeleter@@@std@@_K@std@@W4MESSAGE_SEQUENCE_TYPE@1@K@Z; VmMigrationConnection::WaitForRequest(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,ulong)
0x14008ef9d  mov     rdi, [rax+10h]
0x14008efa1  lea     rcx, [rsp+1B8h+var_110]
0x14008efa9  call    ??1?$unique_ptr@VVmMigrationNetworkBuffer@@VVmMigrationNetworkBufferDeleter@@@std@@QEAA@XZ; std::unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>::~unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>(void)
0x14008efae  mov     rcx, rdi
0x14008efb1  call    ?Parse@TransferRequestHeaderData@MuxMigrationHeader@@SA?AW4TransferRequestFlags@2@_K@Z; MuxMigrationHeader::TransferRequestHeaderData::Parse(unsigned __int64)
0x14008efb6  mov     rcx, [rsp+1B8h]; this
0x14008efbe  test    al, al
0x14008efc0  jz      short loc_14008EFD9
0x14008efc2  mov     r9d, 8007000Dh; char *
0x14008efc8  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008efcf  mov     edx, 80Bh; void *
0x14008efd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008efd9  xor     r8d, r8d; unsigned __int64
0x14008efdc  xor     edx, edx; struct VmMigrationNetworkBuffer *
0x14008efde  mov     rcx, [rbx+1B8h]; this
0x14008efe5  call    ?AcknowledgeMessageSequence@VmMigrationConnection@@QEAAJPEBVVmMigrationNetworkBuffer@@_K@Z; VmMigrationConnection::AcknowledgeMessageSequence(VmMigrationNetworkBuffer const *,unsigned __int64)
0x14008efea  mov     rcx, [rsp+1B8h]; this
0x14008eff2  test    eax, eax
0x14008eff4  jns     short loc_14008F00A
0x14008eff6  mov     r9d, eax; char *
0x14008eff9  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f000  mov     edx, 80Dh; void *
0x14008f005  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f00a  mov     r9d, [r12]
0x14008f00e  mov     r8, qword ptr [rsp+1B8h+var_A8]
0x14008f016  mov     edx, 31h ; '1'
0x14008f01b  mov     rcx, [rbx+1B8h]
0x14008f022  call    ?ReceiveAsynchronousMessageSequence@VmMigrationConnection@@QEAAJW4MESSAGE_SEQUENCE_TYPE@1@PEAVIVmMigrationMessageHandler@@I@Z; VmMigrationConnection::ReceiveAsynchronousMessageSequence(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,IVmMigrationMessageHandler *,uint)
0x14008f027  mov     rcx, [rsp+1B8h]; this
0x14008f02f  test    eax, eax
0x14008f031  jns     short loc_14008F047
0x14008f033  mov     r9d, eax; char *
0x14008f036  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f03d  mov     edx, 812h; void *
0x14008f042  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f047  test    rsi, rsi
0x14008f04a  jz      short loc_14008F067
0x14008f04c  mov     rdi, [rsi+18h]
0x14008f050  mov     rsi, [rsi+20h]
0x14008f054  cmp     rdi, rsi
0x14008f057  jz      short loc_14008F067
0x14008f059  mov     rcx, [rdi]; this
0x14008f05c  call    ?EnsureTransferCompleted@EndpointMessageSequencerTarget@@QEAAXXZ; EndpointMessageSequencerTarget::EnsureTransferCompleted(void)
0x14008f061  add     rdi, 10h
0x14008f065  jmp     short loc_14008F054
0x14008f067  mov     r9d, 7530h
0x14008f06d  mov     r8d, 30h ; '0'
0x14008f073  lea     rdx, [rsp+1B8h+var_110]
0x14008f07b  mov     rcx, [rbx+1B8h]
0x14008f082  call    ?WaitForRequest@VmMigrationConnection@@QEAA?AU?$pair@V?$unique_ptr@VVmMigrationNetworkBuffer@@VVmMigrationNetworkBufferDeleter@@@std@@_K@std@@W4MESSAGE_SEQUENCE_TYPE@1@K@Z; VmMigrationConnection::WaitForRequest(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,ulong)
0x14008f087  mov     rdi, [rax+10h]
0x14008f08b  lea     rcx, [rsp+1B8h+var_110]
0x14008f093  call    ??1?$unique_ptr@VVmMigrationNetworkBuffer@@VVmMigrationNetworkBufferDeleter@@@std@@QEAA@XZ; std::unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>::~unique_ptr<VmMigrationNetworkBuffer,VmMigrationNetworkBufferDeleter>(void)
0x14008f098  mov     rcx, rdi
0x14008f09b  call    ?Parse@TransferRequestHeaderData@MuxMigrationHeader@@SA?AW4TransferRequestFlags@2@_K@Z; MuxMigrationHeader::TransferRequestHeaderData::Parse(unsigned __int64)
0x14008f0a0  mov     rcx, [rsp+1B8h]; this
0x14008f0a8  cmp     al, 1
0x14008f0aa  jz      short loc_14008F0C3
0x14008f0ac  mov     r9d, 8007000Dh; char *
0x14008f0b2  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f0b9  mov     edx, 81Eh; void *
0x14008f0be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f0c3  xor     r8d, r8d; unsigned __int64
0x14008f0c6  xor     edx, edx; struct VmMigrationNetworkBuffer *
0x14008f0c8  mov     rcx, [rbx+1B8h]; this
0x14008f0cf  call    ?AcknowledgeMessageSequence@VmMigrationConnection@@QEAAJPEBVVmMigrationNetworkBuffer@@_K@Z; VmMigrationConnection::AcknowledgeMessageSequence(VmMigrationNetworkBuffer const *,unsigned __int64)
0x14008f0d4  mov     rcx, [rsp+1B8h]; this
0x14008f0dc  test    eax, eax
0x14008f0de  jns     loc_14008F1B2
0x14008f0e4  mov     r9d, eax; char *
0x14008f0e7  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f0ee  mov     edx, 820h; void *
0x14008f0f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f0f8  mov     al, 1
0x14008f0fa  mov     qword ptr [rsp+1B8h+var_138], r13
0x14008f102  mov     edi, [rbx+1E0h]
0x14008f108  neg     al
0x14008f10a  sbb     r8d, r8d
0x14008f10d  and     r8d, 0D4670h
0x14008f114  add     r8d, 7530h
0x14008f11b  mov     eax, 36EE80h
0x14008f120  and     edi, 8
0x14008f123  cmovnz  r8d, eax
0x14008f127  lea     rax, [rsp+1B8h+var_138]
0x14008f12f  mov     qword ptr [rsp+1B8h+var_198], rax; int
0x14008f134  xor     r9d, r9d
0x14008f137  lea     edx, [r9+1Bh]
0x14008f13b  mov     rcx, [rbx+1B8h]
0x14008f142  call    ?WaitForRequest@VmMigrationConnection@@QEAAJW4MESSAGE_SEQUENCE_TYPE@1@KPEAPEAVVmMigrationNetworkBuffer@@AEA_K@Z; VmMigrationConnection::WaitForRequest(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,ulong,VmMigrationNetworkBuffer * *,unsigned __int64 &)
0x14008f147  mov     rcx, [rsp+1B8h]; this
0x14008f14f  test    eax, eax
0x14008f151  jns     short loc_14008F167
0x14008f153  mov     r9d, eax; char *
0x14008f156  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f15d  mov     edx, 83Bh; void *
0x14008f162  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f167  xor     r8d, r8d; unsigned __int64
0x14008f16a  xor     edx, edx; struct VmMigrationNetworkBuffer *
0x14008f16c  mov     rcx, [rbx+1B8h]; this
0x14008f173  call    ?AcknowledgeMessageSequence@VmMigrationConnection@@QEAAJPEBVVmMigrationNetworkBuffer@@_K@Z; VmMigrationConnection::AcknowledgeMessageSequence(VmMigrationNetworkBuffer const *,unsigned __int64)
0x14008f178  mov     rcx, [rsp+1B8h]; this
0x14008f180  test    eax, eax
0x14008f182  jns     short loc_14008F198
0x14008f184  mov     r9d, eax; char *
0x14008f187  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f18e  mov     edx, 83Ch; void *
0x14008f193  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f198  test    byte ptr [rsp+1B8h+var_138], 1
0x14008f1a0  jz      short loc_14008F208
0x14008f1a2  mov     dl, 1; bool
0x14008f1a4  lea     rcx, [rsp+1B8h+var_A0]; this
0x14008f1ac  call    ?UpdatePerfCounters@MigrationTargetMemoryStatistics@@QEAAX_N@Z; MigrationTargetMemoryStatistics::UpdatePerfCounters(bool)
0x14008f1b1  nop
0x14008f1b2  lea     rcx, [rsp+1B8h+var_A8]
0x14008f1ba  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14008f1bf  nop
0x14008f1c0  cmp     [rbx+1ECh], r13d
0x14008f1c7  jz      short loc_14008F1F3
0x14008f1c9  lea     rdi, [rbx+250h]
0x14008f1d0  mov     rcx, rdi; this
0x14008f1d3  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x14008f1d8  mov     [rbx+260h], r13b
0x14008f1df  mov     [rdi+8], r13d
0x14008f1e3  mov     rcx, rdi; SRWLock
0x14008f1e6  call    cs:__imp_ReleaseSRWLockExclusive
0x14008f1ed  nop     dword ptr [rax+rax+00h]
0x14008f1f2  nop
0x14008f1f3  mov     rcx, r15
0x14008f1f6  call    ??1?$_Hash@V?$_Umap_traits@W4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@V?$_Uhash_compare@W4ReplyType@MuxMigrationReply@@U?$hash@W4ReplyType@MuxMigrationReply@@@std@@U?$equal_to@W4ReplyType@MuxMigrationReply@@@4@@4@V?$allocator@U?$pair@$$CBW4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>::~_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>(void)
0x14008f1fb  nop
0x14008f1fc  mov     rcx, r14; void *
0x14008f1ff  call    ??1?$VmComPtr@UIVmMetricValueSink@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(void)
0x14008f204  xor     eax, eax
0x14008f206  jmp     short loc_14008F27E
0x14008f208  test    edi, edi
0x14008f20a  jnz     short loc_14008F254
0x14008f20c  lea     rcx, [rsp+1B8h+var_A0]; this
0x14008f214  call    ?OnNewMemoryTransferPassStartedAtTarget@MigrationTargetMemoryStatistics@@QEAAXXZ; MigrationTargetMemoryStatistics::OnNewMemoryTransferPassStartedAtTarget(void)
0x14008f219  mov     r9d, [r12]
0x14008f21d  mov     r8, qword ptr [rsp+1B8h+var_A8]
0x14008f225  lea     edx, [rdi+6]
0x14008f228  mov     rcx, [rbx+1B8h]
0x14008f22f  call    ?ReceiveAsynchronousMessageSequence@VmMigrationConnection@@QEAAJW4MESSAGE_SEQUENCE_TYPE@1@PEAVIVmMigrationMessageHandler@@I@Z; VmMigrationConnection::ReceiveAsynchronousMessageSequence(VmMigrationConnection::MESSAGE_SEQUENCE_TYPE,IVmMigrationMessageHandler *,uint)
0x14008f234  mov     rcx, [rsp+1B8h]; this
0x14008f23c  test    eax, eax
0x14008f23e  jns     short loc_14008F254
0x14008f240  mov     r9d, eax; char *
0x14008f243  lea     r8, aOnecoreVmWorke_89; "onecore\\vm\\worker\\migration\\workert"...
0x14008f24a  mov     edx, 854h; void *
0x14008f24f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008f254  mov     al, r13b
0x14008f257  jmp     loc_14008F0FA
0x14008f25c  mov     rcx, [rsp+1B8h+var_B0]
0x14008f264  call    ??1?$_Hash@V?$_Umap_traits@W4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@V?$_Uhash_compare@W4ReplyType@MuxMigrationReply@@U?$hash@W4ReplyType@MuxMigrationReply@@@std@@U?$equal_to@W4ReplyType@MuxMigrationReply@@@4@@4@V?$allocator@U?$pair@$$CBW4ReplyType@MuxMigrationReply@@V?$vector@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@V?$allocator@V?$shared_ptr@VReplyBuilder@MuxMigrationReply@@@std@@@2@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>::~_Hash<std::_Umap_traits<MuxMigrationReply::ReplyType,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>,std::_Uhash_compare<MuxMigrationReply::ReplyType,std::hash<MuxMigrationReply::ReplyType>,std::equal_to<MuxMigrationReply::ReplyType>>,std::allocator<std::pair<MuxMigrationReply::ReplyType const,std::vector<std::shared_ptr<MuxMigrationReply::ReplyBuilder>>>>,0>>(void)
0x14008f269  nop
0x14008f26a  mov     rcx, [rsp+1B8h+var_128]; void *
0x14008f272  call    ??1?$VmComPtr@UIVmMetricValueSink@@@Vml@@QEAA@XZ; Vml::VmComPtr<IVmMetricValueSink>::~VmComPtr<IVmMetricValueSink>(void)
0x14008f277  mov     eax, [rsp+1B8h+var_A8]
0x14008f27e  mov     rcx, [rsp+1B8h+var_48]
0x14008f286  xor     rcx, rsp; StackCookie
0x14008f289  call    __security_check_cookie
0x14008f28e  add     rsp, 180h
0x14008f295  pop     r15
0x14008f297  pop     r14
0x14008f299  pop     r13
0x14008f29b  pop     r12
0x14008f29d  pop     rdi
0x14008f29e  pop     rsi
0x14008f29f  pop     rbx
0x14008f2a0  retn
```
