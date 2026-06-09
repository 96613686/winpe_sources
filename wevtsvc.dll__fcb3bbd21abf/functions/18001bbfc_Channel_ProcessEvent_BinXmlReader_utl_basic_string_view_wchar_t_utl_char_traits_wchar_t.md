# Channel::ProcessEvent(BinXmlReader &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x18001bbfc`
- end: `0x18001c09f`
- name: `?ProcessEvent@Channel@@QEAAKAEAVBinXmlReader@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z`
- size: `1187`
- prototype: `__int64 __fastcall(Channel *this, BinXmlReader *, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001bbcc`

## callees

- `0x18000bf10`
- `0x180012018`
- `0x1800121f8`
- `0x18001bbc0`
- `0x18001bbfc`
- `0x18001c320`
- `0x18001c39c`
- `0x180024918`
- `0x180028314`
- `0x1800471c0`
- `0x180056714`
- `0x180063510`
- `0x180065a78`
- `0x1800660ac`
- `0x1800660cc`
- `0x18006d84c`
- `0x18006f820`
- `0x180090c60`
- `0x180091e34`
- `0x180092008`
- `0x1800a7d70`
- `0x1800aa1b4`
- `0x1800c5c1c`
- `0x1800c644c`
- `0x1800c662c`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001be1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001be1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001be0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001c030`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001be0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001c030`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bc2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bc2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bd88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001beb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bd88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001beb6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!PulseEvent` at `0x18001bda3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!PulseEvent` at `0x18001bda3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001bd61`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001bd61`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001bfd8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001bfd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Channel::ProcessEvent(Channel *this, BinXmlReader *a2, __int64 a3)
{
  __int64 v3; // rdi
  bool v6; // r8
  unsigned int v7; // esi
  void (__fastcall ***v8)(_QWORD, BinXmlReader *, void **); // rbx
  __int64 (__fastcall ***v9)(_QWORD, BinXmlReader *, void **); // rcx
  HANDLE *i; // rbx
  __int64 *v11; // rbx
  __int64 v13; // rbx
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rsi
  RTL_SRWLOCK *v16; // rdi
  WINBOOL v17; // esi
  void ***v18; // rdi
  unsigned int Size; // esi
  WINBOOL *v20; // rax
  __int64 v21; // rdx
  unsigned int v22; // ebx
  __int64 v23; // rcx
  const struct _EVENTLOGRECORD *v24; // rbx
  int v25; // eax
  __int64 v26; // rcx
  PSRWLOCK SRWLock; // [rsp+20h] [rbp-50h] BYREF
  char v28; // [rsp+28h] [rbp-48h]
  void *p_SRWLock; // [rsp+30h] [rbp-40h] BYREF
  void *v30; // [rsp+38h] [rbp-38h]
  unsigned int v31; // [rsp+40h] [rbp-30h]
  unsigned int v32; // [rsp+44h] [rbp-2Ch]
  void **v33; // [rsp+48h] [rbp-28h] BYREF
  void *v34; // [rsp+50h] [rbp-20h]
  __int64 v35; // [rsp+58h] [rbp-18h]
  char v36; // [rsp+60h] [rbp-10h]
  WINBOOL fPending; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID Context; // [rsp+B8h] [rbp+48h] BYREF
  union _RTL_RUN_ONCE *v39; // [rsp+C0h] [rbp+50h] BYREF

  v3 = *(_QWORD *)(a3 + 8);
  SRWLock = (PSRWLOCK)((char *)this + 472);
  AcquireSRWLockExclusive((PSRWLOCK)this + 59);
  v28 = 1;
  *((_QWORD *)a2 + 9) = *((_QWORD *)a2 + 8);
  *((_QWORD *)a2 + 6) = *((_QWORD *)a2 + 5);
  *((_DWORD *)a2 + 9) = -1;
  *((_QWORD *)a2 + 2) = 0;
  *((_BYTE *)a2 + 188) = 0;
  *((_DWORD *)a2 + 42) = 0;
  BinXmlReader::NextReaderData(a2);
  if ( v3 )
  {
    v8 = (void (__fastcall ***)(_QWORD, BinXmlReader *, void **))*((_QWORD *)this + 58);
    if ( v8 )
    {
      utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(&p_SRWLock);
      (**v8)(v8, a2, &p_SRWLock);
      BinXmlReader::Reset(a2);
      utl::vector<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::allocator<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>>::_Uninit(&p_SRWLock);
    }
    v6 = 1;
    goto LABEL_5;
  }
  if ( !*((_BYTE *)this + 878) || *((Channel **)this + 102) != (Channel *)((char *)this + 800) )
  {
    v6 = 0;
LABEL_5:
    v7 = ChannelFilter::Indicate((Channel *)((char *)this + 480), a2, v6);
    if ( !v3 )
      Channel::NotifyLegacySubscribers(this);
    goto LABEL_16;
  }
  v7 = 0;
  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(&p_SRWLock);
  v9 = (__int64 (__fastcall ***)(_QWORD, BinXmlReader *, void **))*((_QWORD *)this + 95);
  if ( v9 )
    v7 = (**v9)(v9, a2, &p_SRWLock);
  for ( i = (HANDLE *)*((_QWORD *)this + 97); i != (HANDLE *)((char *)this + 776); i = (HANDLE *)*i )
    PulseEvent(i[3]);
  if ( p_SRWLock != (void *)-1LL )
  {
    v30 = p_SRWLock;
    operator delete(p_SRWLock);
  }
LABEL_16:
  if ( v7 != 1502 || (v22 = Channel::ProcessLogFull(this)) == 0 )
  {
    if ( *((_BYTE *)this + 84) )
    {
      v13 = *((_QWORD *)this + 95);
      if ( *(_BYTE *)(v13 + 80) == 1 && EvtxFileEventSink::OpenOrCreateFile(*((EvtxFileEventSink **)this + 95)) )
      {
        v14 = 0;
        Context = 0;
        v15 = 0;
      }
      else
      {
        if ( *(_BYTE *)(v13 + 80) )
          __int2c();
        v14 = *(volatile signed __int32 **)(v13 + 8);
        Context = (LPVOID)v14;
        v15 = v14;
        if ( v14 )
          _InterlockedIncrement(v14 + 202);
      }
      if ( v15 )
      {
        v16 = (RTL_SRWLOCK *)(v15 + 166);
        AcquireSRWLockShared((PSRWLOCK)v15 + 83);
        v17 = *((_DWORD *)v15 + 204);
        ReleaseSRWLockShared(v16);
        fPending = v17;
        if ( v17 )
        {
          v33 = &Buffer::`vftable';
          v34 = 0;
          v35 = 0;
          v36 = 1;
          v18 = &v33;
          p_SRWLock = &v33;
          v31 = 0;
          Size = Buffer::GetSize((Buffer *)&v33);
          v20 = (WINBOOL *)((__int64 (__fastcall *)(void ***))v33[6])(&v33);
          v30 = v20;
          v32 = Size;
          if ( v20 && Size >= 4 )
          {
            *v20 = fPending;
            v21 = 4;
          }
          else
          {
            WriteBuffer::SlowWrite((WriteBuffer *)&p_SRWLock, &fPending, 4u);
            v21 = v31;
            v18 = (void ***)p_SRWLock;
          }
          ((void (__fastcall *)(void ***, __int64))(*v18)[4])(v18, v21);
          if ( !v28 )
            __int2c();
          ReleaseSRWLockExclusive(SRWLock);
          v28 = 0;
          p_SRWLock = &SRWLock;
          LOBYTE(v30) = 1;
          Channel::FireEventIntoLog(this, (struct Buffer *)&v33, &EVENT_AUDIT_LOG_EXCEEDS_WARNING_LEVEL, 0);
          utl::unique_lock<utl::mutex>::lock(&SRWLock);
          v33 = &Buffer::`vftable';
          if ( v36 )
            operator delete(v34);
        }
      }
      if ( v14 )
        File::Release((File *)v14);
    }
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&stru_180111620, 0, &fPending, &Context);
    v11 = (__int64 *)Context;
    if ( !Context )
    {
      v39 = &stru_180111620;
      v11 = qword_180111628;
      ContainerCommon::LazyMachineId::LazyMachineId((ContainerCommon::LazyMachineId *)qword_180111628);
      v39 = 0;
      InitOnceComplete(&stru_180111620, 0, qword_180111628);
      tlx::_LazyImpl<LazyFeatureRestrictions,tlx::lazy_construct<LazyFeatureRestrictions>,tlx::static_lazy<LazyFeatureRestrictions,1,tlx::lazy_construct<LazyFeatureRestrictions>>>::_Initializer::~_Initializer(&v39);
    }
    if ( *((_DWORD *)v11 + 8) != 2 )
      goto LABEL_21;
    if ( !*((_QWORD *)this + 9) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v23 = *((_QWORD *)a2 + 22);
    fPending = 0;
    v24 = (const struct _EVENTLOGRECORD *)(*(__int64 (__fastcall **)(__int64, WINBOOL *))(*(_QWORD *)v23 + 32LL))(
                                            v23,
                                            &fPending);
    if ( !v24 )
      goto LABEL_21;
    utl::unique_lock<utl::mutex>::unlock(&SRWLock);
    p_SRWLock = (char *)this + 56;
    AcquireSRWLockShared((PSRWLOCK)this + 7);
    LOBYTE(v30) = 1;
    if ( fPending )
    {
      if ( fPending == 1 )
      {
        v25 = ContainerForwarder::ForwardEventToHost(
                *((ContainerForwarder **)this + 9),
                v24,
                *((const wchar_t **)this + 17));
        if ( v25 >= 0 )
          goto LABEL_61;
LABEL_60:
        MicrosoftTelemetryAssertTriggeredArgs(v26, (unsigned int)v25, 0);
        goto LABEL_61;
      }
      if ( fPending != 5 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_61:
        utl::shared_lock<utl::shared_mutex>::~shared_lock<utl::shared_mutex>(&p_SRWLock);
LABEL_21:
        if ( v28 )
          ReleaseSRWLockExclusive(SRWLock);
        return 0;
      }
    }
    v25 = ContainerForwarder::ForwardEventToHost(*((ContainerForwarder **)this + 9), (const struct _EVENT_RECORD *)v24);
    if ( v25 >= 0 )
      goto LABEL_61;
    goto LABEL_60;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c5cf29227a703fd4aa73a50734329760_Traceguids, v22);
  }
  utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&SRWLock);
  return v22;
}

```

## disassembly

```asm
0x18001bbfc  push    rbp
0x18001bbfe  push    rbx
0x18001bbff  push    rsi
0x18001bc00  push    rdi
0x18001bc01  push    r12
0x18001bc03  push    r14
0x18001bc05  push    r15
0x18001bc07  mov     rbp, rsp
0x18001bc0a  sub     rsp, 70h
0x18001bc0e  mov     rdi, [r8+8]
0x18001bc12  mov     r15, rdx
0x18001bc15  mov     r14, rcx
0x18001bc18  add     rcx, 1D8h; SRWLock
0x18001bc1f  mov     [rbp+SRWLock], rcx
0x18001bc23  xor     r12d, r12d
0x18001bc26  mov     [rbp+var_48], r12b
0x18001bc2a  call    cs:__imp_AcquireSRWLockExclusive
0x18001bc30  mov     [rbp+var_48], 1
0x18001bc34  mov     rax, [r15+40h]
0x18001bc38  mov     [r15+48h], rax
0x18001bc3c  mov     rax, [r15+28h]
0x18001bc40  mov     [r15+30h], rax
0x18001bc44  mov     dword ptr [r15+24h], 0FFFFFFFFh
0x18001bc4c  mov     [r15+10h], r12
0x18001bc50  mov     [r15+0BCh], r12b
0x18001bc57  mov     [r15+0A8h], r12d
0x18001bc5e  mov     rcx, r15; this
0x18001bc61  call    ?NextReaderData@BinXmlReader@@AEAAXXZ; BinXmlReader::NextReaderData(void)
0x18001bc66  test    rdi, rdi
0x18001bc69  jnz     short loc_18001BCAB
0x18001bc6b  cmp     [r14+36Eh], r12b
0x18001bc72  jz      short loc_18001BC81
0x18001bc74  lea     rax, [r14+320h]
0x18001bc7b  cmp     [rax+10h], rax
0x18001bc7f  jz      short loc_18001BCED
0x18001bc81  mov     r8b, r12b; bool
0x18001bc84  lea     rcx, [r14+1E0h]; this
0x18001bc8b  mov     rdx, r15; struct BinXmlReader *
0x18001bc8e  call    ?Indicate@ChannelFilter@@QEAAKAEAVBinXmlReader@@_N@Z; ChannelFilter::Indicate(BinXmlReader &,bool)
0x18001bc93  mov     esi, eax
0x18001bc95  test    rdi, rdi
0x18001bc98  jnz     loc_18001BD2F
0x18001bc9e  mov     rcx, r14; this
0x18001bca1  call    ?NotifyLegacySubscribers@Channel@@AEAAXXZ; Channel::NotifyLegacySubscribers(void)
0x18001bca6  jmp     loc_18001BD2F
0x18001bcab  mov     rbx, [r14+1D0h]
0x18001bcb2  test    rbx, rbx
0x18001bcb5  jz      short loc_18001BCE8
0x18001bcb7  lea     rcx, [rbp+var_40]; void *
0x18001bcbb  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x18001bcc0  nop
0x18001bcc1  mov     rax, [rbx]
0x18001bcc4  lea     r8, [rbp+var_40]
0x18001bcc8  mov     rdx, r15
0x18001bccb  mov     rcx, rbx
0x18001bcce  mov     rax, [rax]
0x18001bcd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcd6  mov     rcx, r15; this
0x18001bcd9  call    ?Reset@BinXmlReader@@QEAAXXZ; BinXmlReader::Reset(void)
0x18001bcde  nop
0x18001bcdf  lea     rcx, [rbp+var_40]
0x18001bce3  call    ?_Uninit@?$vector@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::allocator<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>>::_Uninit(void)
0x18001bce8  mov     r8b, 1
0x18001bceb  jmp     short loc_18001BC84
0x18001bced  mov     esi, r12d
0x18001bcf0  lea     rcx, [rbp+var_40]; void *
0x18001bcf4  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x18001bcf9  mov     rcx, [r14+2F8h]
0x18001bd00  test    rcx, rcx
0x18001bd03  jnz     loc_18001BDB1
0x18001bd09  lea     rdi, [r14+308h]
0x18001bd10  mov     rbx, [rdi]
0x18001bd13  cmp     rbx, rdi
0x18001bd16  jnz     loc_18001BD9F
0x18001bd1c  mov     rcx, [rbp+var_40]; void *
0x18001bd20  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001bd24  jz      short loc_18001BD2F
0x18001bd26  mov     [rbp+var_38], rcx
0x18001bd2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bd2f  cmp     esi, 5DEh
0x18001bd35  jz      loc_18001BF36
0x18001bd3b  cmp     [r14+54h], r12b
0x18001bd3f  jnz     loc_18001BDCA
0x18001bd45  mov     [rbp+fPending], r12d
0x18001bd49  mov     [rbp+Context], r12
0x18001bd4d  lea     r9, [rbp+Context]; lpContext
0x18001bd51  lea     r8, [rbp+fPending]; fPending
0x18001bd55  xor     edx, edx; dwFlags
0x18001bd57  lea     rdi, stru_180111620
0x18001bd5e  mov     rcx, rdi; lpInitOnce
0x18001bd61  call    cs:__imp_InitOnceBeginInitialize
0x18001bd67  mov     rbx, [rbp+Context]
0x18001bd6b  test    rbx, rbx
0x18001bd6e  jz      loc_18001BFB9
0x18001bd74  cmp     dword ptr [rbx+20h], 2
0x18001bd78  jz      loc_18001BFED
0x18001bd7e  cmp     [rbp+var_48], r12b
0x18001bd82  jz      short loc_18001BD8E
0x18001bd84  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001bd88  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bd8e  xor     eax, eax
0x18001bd90  add     rsp, 70h
0x18001bd94  pop     r15
0x18001bd96  pop     r14
0x18001bd98  pop     r12
0x18001bd9a  pop     rdi
0x18001bd9b  pop     rsi
0x18001bd9c  pop     rbx
0x18001bd9d  pop     rbp
0x18001bd9e  retn
0x18001bd9f  mov     rcx, [rbx+18h]; hEvent
0x18001bda3  call    cs:__imp_PulseEvent
0x18001bda9  mov     rbx, [rbx]
0x18001bdac  jmp     loc_18001BD13
0x18001bdb1  mov     rax, [rcx]
0x18001bdb4  lea     r8, [rbp+var_40]
0x18001bdb8  mov     rdx, r15
0x18001bdbb  mov     rax, [rax]
0x18001bdbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdc3  mov     esi, eax
0x18001bdc5  jmp     loc_18001BD09
0x18001bdca  mov     rbx, [r14+2F8h]
0x18001bdd1  cmp     byte ptr [rbx+50h], 1
0x18001bdd5  jz      loc_18001BF9A
0x18001bddb  cmp     [rbx+50h], r12b
0x18001bddf  jnz     loc_18001BF2F
0x18001bde5  mov     rbx, [rbx+8]
0x18001bde9  mov     [rbp+Context], rbx
0x18001bded  mov     rsi, rbx
0x18001bdf0  test    rbx, rbx
0x18001bdf3  jz      short loc_18001BDFC
0x18001bdf5  lock inc dword ptr [rbx+328h]
0x18001bdfc  test    rsi, rsi
0x18001bdff  jz      short loc_18001BE27
0x18001be01  lea     rdi, [rsi+298h]
0x18001be08  mov     rcx, rdi; SRWLock
0x18001be0b  call    cs:__imp_AcquireSRWLockShared
0x18001be11  mov     esi, [rsi+330h]
0x18001be17  mov     rcx, rdi; SRWLock
0x18001be1a  call    cs:__imp_ReleaseSRWLockShared
0x18001be20  mov     [rbp+fPending], esi
0x18001be23  test    esi, esi
0x18001be25  jnz     short loc_18001BE3D
0x18001be27  test    rbx, rbx
0x18001be2a  jz      loc_18001BD45
0x18001be30  mov     rcx, rbx; this
0x18001be33  call    ?Release@File@@QEAAKXZ; File::Release(void)
0x18001be38  jmp     loc_18001BD45
0x18001be3d  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x18001be44  mov     [rbp+var_28], rax
0x18001be48  mov     [rbp+var_20], r12
0x18001be4c  mov     [rbp+var_18], r12
0x18001be50  mov     [rbp+var_10], 1
0x18001be54  lea     rdi, [rbp+var_28]
0x18001be58  mov     [rbp+var_40], rdi
0x18001be5c  mov     [rbp+var_30], r12d
0x18001be60  lea     rcx, [rbp+var_28]; this
0x18001be64  call    ?GetSize@Buffer@@UEBAKXZ; Buffer::GetSize(void)
0x18001be69  mov     esi, eax
0x18001be6b  mov     rcx, [rbp+var_28]
0x18001be6f  mov     rax, [rcx+30h]
0x18001be73  lea     rcx, [rbp+var_28]
0x18001be77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be7c  mov     [rbp+var_38], rax
0x18001be80  mov     [rbp+var_2C], esi
0x18001be83  test    rax, rax
0x18001be86  jz      loc_18001BF10
0x18001be8c  cmp     esi, 4
0x18001be8f  jb      short loc_18001BF10
0x18001be91  mov     ecx, [rbp+fPending]
0x18001be94  mov     [rax], ecx
0x18001be96  mov     edx, 4
0x18001be9b  mov     rax, [rdi]
0x18001be9e  mov     rcx, rdi
0x18001bea1  mov     rax, [rax+20h]
0x18001bea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001beaa  cmp     [rbp+var_48], r12b
0x18001beae  jnz     short loc_18001BEB2
0x18001beb0  int     2Ch; Windows NT - assertion failure
0x18001beb2  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001beb6  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bebc  mov     [rbp+var_48], r12b
0x18001bec0  lea     rax, [rbp+SRWLock]
0x18001bec4  mov     [rbp+var_40], rax
0x18001bec8  mov     byte ptr [rbp+var_38], 1
0x18001becc  xor     r9d, r9d; void *
0x18001becf  lea     r8, EVENT_AUDIT_LOG_EXCEEDS_WARNING_LEVEL; struct _EVENT_DESCRIPTOR *
0x18001bed6  lea     rdx, [rbp+var_28]; struct Buffer *
0x18001beda  mov     rcx, r14; this
0x18001bedd  call    ?FireEventIntoLog@Channel@@AEAAXAEAVBuffer@@AEBU_EVENT_DESCRIPTOR@@PEAX@Z; Channel::FireEventIntoLog(Buffer &,_EVENT_DESCRIPTOR const &,void *)
0x18001bee2  nop
0x18001bee3  lea     rcx, [rbp+SRWLock]
0x18001bee7  call    ?lock@?$unique_lock@Vmutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::mutex>::lock(void)
0x18001beec  nop
0x18001beed  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x18001bef4  mov     [rbp+var_28], rax
0x18001bef8  cmp     [rbp+var_10], r12b
0x18001befc  jz      loc_18001BE27
0x18001bf02  mov     rcx, [rbp+var_20]; void *
0x18001bf06  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bf0b  jmp     loc_18001BE27
0x18001bf10  mov     r8d, 4; unsigned int
0x18001bf16  lea     rdx, [rbp+fPending]; void *
0x18001bf1a  lea     rcx, [rbp+var_40]; this
0x18001bf1e  call    ?SlowWrite@WriteBuffer@@AEAAXQEBXK@Z; WriteBuffer::SlowWrite(void const * const,ulong)
0x18001bf23  mov     edx, [rbp+var_30]
0x18001bf26  mov     rdi, [rbp+var_40]
0x18001bf2a  jmp     loc_18001BE9B
0x18001bf2f  int     2Ch; Windows NT - assertion failure
0x18001bf31  jmp     loc_18001BDE5
0x18001bf36  lea     r8, [rbp+SRWLock]
0x18001bf3a  mov     rdx, r15
0x18001bf3d  mov     rcx, r14; this
0x18001bf40  call    ?ProcessLogFull@Channel@@AEAAKAEAVBinXmlReader@@AEAV?$unique_lock@Vmutex@utl@@@utl@@@Z; Channel::ProcessLogFull(BinXmlReader &,utl::unique_lock<utl::mutex> &)
0x18001bf45  mov     ebx, eax
0x18001bf47  test    eax, eax
0x18001bf49  jz      loc_18001BD3B
0x18001bf4f  lea     rax, WPP_GLOBAL_Control
0x18001bf56  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf5d  cmp     rcx, rax
0x18001bf60  jz      short loc_18001BF8A
0x18001bf62  test    dword ptr [rcx+1Ch], 800h
0x18001bf69  jz      short loc_18001BF8A
0x18001bf6b  cmp     byte ptr [rcx+19h], 2
0x18001bf6f  jb      short loc_18001BF8A
0x18001bf71  mov     edx, 0Ah
0x18001bf76  mov     r9d, ebx
0x18001bf79  lea     r8, WPP_c5cf29227a703fd4aa73a50734329760_Traceguids
0x18001bf80  mov     rcx, [rcx+10h]
0x18001bf84  call    WPP_SF_d
0x18001bf89  nop
0x18001bf8a  lea     rcx, [rbp+SRWLock]
0x18001bf8e  call    ??1?$unique_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(void)
0x18001bf93  mov     eax, ebx
0x18001bf95  jmp     loc_18001BD90
0x18001bf9a  mov     rcx, rbx; this
0x18001bf9d  call    ?OpenOrCreateFile@EvtxFileEventSink@@AEAAKXZ; EvtxFileEventSink::OpenOrCreateFile(void)
0x18001bfa2  test    eax, eax
0x18001bfa4  jz      loc_18001BDDB
0x18001bfaa  mov     rbx, r12
0x18001bfad  mov     [rbp+Context], rbx
0x18001bfb1  mov     rsi, r12
0x18001bfb4  jmp     loc_18001BDFC
0x18001bfb9  mov     [rbp+arg_10], rdi
0x18001bfbd  lea     rbx, qword_180111628
0x18001bfc4  mov     rcx, rbx; this
0x18001bfc7  call    ??0LazyMachineId@ContainerCommon@@QEAA@XZ; ContainerCommon::LazyMachineId::LazyMachineId(void)
0x18001bfcc  mov     [rbp+arg_10], r12
0x18001bfd0  mov     r8, rbx; lpContext
0x18001bfd3  xor     edx, edx; dwFlags
0x18001bfd5  mov     rcx, rdi; lpInitOnce
0x18001bfd8  call    cs:__imp_InitOnceComplete
0x18001bfde  nop
0x18001bfdf  lea     rcx, [rbp+arg_10]
0x18001bfe3  call    ??1_Initializer@?$_LazyImpl@VLazyFeatureRestrictions@@V?$lazy_construct@VLazyFeatureRestrictions@@@tlx@@V?$static_lazy@VLazyFeatureRestrictions@@$00V?$lazy_construct@VLazyFeatureRestrictions@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<LazyFeatureRestrictions,tlx::lazy_construct<LazyFeatureRestrictions>,tlx::static_lazy<LazyFeatureRestrictions,1,tlx::lazy_construct<LazyFeatureRestrictions>>>::_Initializer::~_Initializer(void)
0x18001bfe8  jmp     loc_18001BD74
0x18001bfed  cmp     [r14+48h], r12
0x18001bff1  jnz     short loc_18001BFF8
0x18001bff3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001bff8  mov     rcx, [r15+0B0h]
0x18001bfff  mov     [rbp+fPending], r12d
0x18001c003  mov     rax, [rcx]
0x18001c006  lea     rdx, [rbp+fPending]
0x18001c00a  mov     rax, [rax+20h]
0x18001c00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c013  mov     rbx, rax
0x18001c016  test    rax, rax
0x18001c019  jz      loc_18001BD7E
0x18001c01f  lea     rcx, [rbp+SRWLock]
0x18001c023  call    ?unlock@?$unique_lock@Vmutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::mutex>::unlock(void)
0x18001c028  lea     rcx, [r14+38h]; SRWLock
0x18001c02c  mov     [rbp+var_40], rcx
0x18001c030  call    cs:__imp_AcquireSRWLockShared
0x18001c036  mov     byte ptr [rbp+var_38], 1
0x18001c03a  mov     edx, [rbp+fPending]
0x18001c03d  test    edx, edx
0x18001c03f  jz      short loc_18001C075
0x18001c041  sub     edx, 1
0x18001c044  jz      short loc_18001C052
0x18001c046  cmp     edx, 4
0x18001c049  jz      short loc_18001C075
0x18001c04b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c050  jmp     short loc_18001C090
0x18001c052  mov     r8, [r14+88h]; wchar_t *
0x18001c059  mov     rdx, rbx; struct _EVENTLOGRECORD *
0x18001c05c  mov     rcx, [r14+48h]; this
0x18001c060  call    ?ForwardEventToHost@ContainerForwarder@@QEAAJPEBU_EVENTLOGRECORD@@PEB_W@Z; ContainerForwarder::ForwardEventToHost(_EVENTLOGRECORD const *,wchar_t const *)
0x18001c065  test    eax, eax
0x18001c067  jns     short loc_18001C090
0x18001c069  xor     r8d, r8d
0x18001c06c  mov     edx, eax
0x18001c06e  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001c073  jmp     short loc_18001C090
0x18001c075  mov     rdx, rbx; struct _EVENT_RECORD *
0x18001c078  mov     rcx, [r14+48h]; this
0x18001c07c  call    ?ForwardEventToHost@ContainerForwarder@@QEAAJPEBU_EVENT_RECORD@@@Z; ContainerForwarder::ForwardEventToHost(_EVENT_RECORD const *)
0x18001c081  test    eax, eax
0x18001c083  jns     short loc_18001C090
0x18001c085  xor     r8d, r8d
0x18001c088  mov     edx, eax
  ... truncated ...
```
