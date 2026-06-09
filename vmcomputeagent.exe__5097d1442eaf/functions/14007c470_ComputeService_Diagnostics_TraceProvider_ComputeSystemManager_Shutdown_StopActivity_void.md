# ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Shutdown::StopActivity(void)

- ea: `0x14007c470`
- end: `0x14007c743`
- name: `?StopActivity@ComputeSystemManager_Shutdown@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Shutdown *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x14007c470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c4d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c69d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c4d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c69d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007c6ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007c6ca`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Shutdown::StopActivity(
        ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Shutdown *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v9; // [rsp+C8h] [rbp-78h] BYREF
  int v10; // [rsp+CCh] [rbp-74h] BYREF
  int v11; // [rsp+D0h] [rbp-70h] BYREF
  int v12; // [rsp+D4h] [rbp-6Ch] BYREF
  int v13; // [rsp+D8h] [rbp-68h] BYREF
  int v14; // [rsp+DCh] [rbp-64h] BYREF
  int v15; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v17; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v18; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v19; // [rsp+100h] [rbp-40h] BYREF
  __int64 v20; // [rsp+108h] [rbp-38h] BYREF
  __int64 v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23; // [rsp+120h] [rbp-20h] BYREF
  __int64 v24; // [rsp+128h] [rbp-18h] BYREF
  __int64 v25; // [rsp+130h] [rbp-10h] BYREF
  __int64 v26; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 4u && (*(_QWORD *)(v5 + 16) & 1) != 0 && (*(_QWORD *)(v5 + 24) & 1LL) == *(_QWORD *)(v5 + 24) )
    {
      v17 = *((_QWORD *)v4 + 6);
      v10 = v4[17];
      v11 = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v19 = *((_QWORD *)v4 + 14);
      v12 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v13 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v9 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v26 = 0x1000000;
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (int)&word_140136C2E,
        *((_QWORD *)this + 34) + 8,
        (__int64)&v16,
        (__int64)&v26,
        (__int64)&SRWLock,
        (__int64)&v25,
        (__int64)&v9,
        (__int64)&v24,
        (__int64)&v15,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v12,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v17);
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 4u && (*(_QWORD *)(v6 + 16) & 1) != 0 && (*(_QWORD *)(v6 + 24) & 1LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&unk_140136BD0,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Shutdown *)((char *)this + 288));
}

```

## disassembly

```asm
0x14007c470  mov     [rsp-8+arg_8], rbx
0x14007c475  mov     [rsp-8+arg_10], rdi
0x14007c47a  push    rbp
0x14007c47b  mov     rbp, rsp
0x14007c47e  sub     rsp, 140h
0x14007c485  mov     rbx, rcx
0x14007c488  mov     rdi, [rcx+110h]
0x14007c48f  mov     eax, [rdi+48h]
0x14007c492  test    eax, eax
0x14007c494  jns     loc_14007C676
0x14007c49a  add     rdi, 50h ; 'P'
0x14007c49e  cmp     eax, [rdi+8]
0x14007c4a1  jnz     loc_14007C676
0x14007c4a7  test    rdi, rdi
0x14007c4aa  jz      loc_14007C676
0x14007c4b0  mov     [rbp+SRWLock], 0
0x14007c4b8  lea     rdx, [rbp+SRWLock]
0x14007c4bc  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14007c4c1  mov     rax, [rbx+110h]
0x14007c4c8  mov     dword ptr [rax], 2
0x14007c4ce  mov     rcx, [rbp+SRWLock]; SRWLock
0x14007c4d2  test    rcx, rcx
0x14007c4d5  jz      short loc_14007C4DD
0x14007c4d7  call    cs:__imp_ReleaseSRWLockExclusive
0x14007c4dd  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14007c4e2  mov     rcx, [rax+8]; int
0x14007c4e6  mov     eax, [rcx]
0x14007c4e8  cmp     eax, 4
0x14007c4eb  jbe     loc_14007C71B
0x14007c4f1  mov     rdx, [rcx+18h]
0x14007c4f5  mov     rax, [rcx+10h]
0x14007c4f9  test    al, 1
0x14007c4fb  jz      loc_14007C71B
0x14007c501  mov     rax, rdx
0x14007c504  and     eax, 1
0x14007c507  cmp     rax, rdx
0x14007c50a  jnz     loc_14007C71B
0x14007c510  mov     rax, [rdi+30h]
0x14007c514  mov     [rbp+var_50], rax
0x14007c518  mov     eax, [rdi+44h]
0x14007c51b  mov     dword ptr [rbp+var_78+4], eax
0x14007c51e  mov     eax, [rdi+10h]
0x14007c521  mov     dword ptr [rbp+var_70], eax
0x14007c524  mov     rax, [rdi+78h]
0x14007c528  mov     [rbp+var_48], rax
0x14007c52c  mov     rax, [rdi+70h]
0x14007c530  mov     [rbp+var_40], rax
0x14007c534  mov     eax, [rdi+68h]
0x14007c537  mov     dword ptr [rbp+var_70+4], eax
0x14007c53a  mov     rax, [rdi+60h]
0x14007c53e  mov     [rbp+var_38], rax
0x14007c542  mov     rax, [rdi+58h]
0x14007c546  mov     [rbp+var_30], rax
0x14007c54a  mov     eax, [rdi+50h]
0x14007c54d  mov     dword ptr [rbp+var_68], eax
0x14007c550  mov     rax, [rdi+48h]
0x14007c554  mov     [rbp+var_28], rax
0x14007c558  mov     eax, [rdi+20h]
0x14007c55b  mov     dword ptr [rbp+var_68+4], eax
0x14007c55e  mov     rax, [rdi+18h]
0x14007c562  mov     [rbp+var_20], rax
0x14007c566  mov     eax, [rdi]
0x14007c568  mov     [rbp+var_60], eax
0x14007c56b  mov     rax, [rdi+80h]
0x14007c572  mov     [rbp+var_18], rax
0x14007c576  mov     eax, [rdi+40h]
0x14007c579  mov     dword ptr [rbp+var_78], eax
0x14007c57c  mov     rax, [rdi+38h]
0x14007c580  mov     [rbp+var_10], rax
0x14007c584  mov     eax, [rdi+8]
0x14007c587  mov     dword ptr [rbp+SRWLock], eax
0x14007c58a  mov     [rbp+var_8], 1000000h
0x14007c592  mov     [rbp+var_58], 0
0x14007c59a  mov     r8, [rbx+110h]
0x14007c5a1  add     r8, 8; int
0x14007c5a5  lea     rax, [rbp+var_50]
0x14007c5a9  mov     [rsp+140h+var_90], rax; __int64
0x14007c5b1  lea     rax, [rbp+var_78+4]
0x14007c5b5  mov     [rsp+140h+var_98], rax; __int64
0x14007c5bd  lea     rax, [rbp+var_70]
0x14007c5c1  mov     [rsp+140h+var_A0], rax; __int64
0x14007c5c9  lea     rax, [rbp+var_48]
0x14007c5cd  mov     [rsp+140h+var_A8], rax; __int64
0x14007c5d5  lea     rax, [rbp+var_40]
0x14007c5d9  mov     [rsp+140h+var_B0], rax; __int64
0x14007c5e1  lea     rax, [rbp+var_70+4]
0x14007c5e5  mov     [rsp+140h+var_B8], rax; __int64
0x14007c5ed  lea     rax, [rbp+var_38]
0x14007c5f1  mov     [rsp+140h+var_C0], rax; __int64
0x14007c5f9  lea     rax, [rbp+var_30]
0x14007c5fd  mov     [rsp+140h+var_C8], rax; __int64
0x14007c602  lea     rax, [rbp+var_68]
0x14007c606  mov     [rsp+140h+var_D0], rax; __int64
0x14007c60b  lea     rax, [rbp+var_28]
0x14007c60f  mov     [rsp+140h+var_D8], rax; __int64
0x14007c614  lea     rax, [rbp+var_68+4]
0x14007c618  mov     [rsp+140h+var_E0], rax; __int64
0x14007c61d  lea     rax, [rbp+var_20]
0x14007c621  mov     [rsp+140h+var_E8], rax; __int64
0x14007c626  lea     rax, [rbp+var_60]
0x14007c62a  mov     [rsp+140h+var_F0], rax; __int64
0x14007c62f  lea     rax, [rbp+var_18]
0x14007c633  mov     [rsp+140h+var_F8], rax; __int64
0x14007c638  lea     rax, [rbp+var_78]
0x14007c63c  mov     [rsp+140h+var_100], rax; __int64
0x14007c641  lea     rax, [rbp+var_10]
0x14007c645  mov     [rsp+140h+var_108], rax; __int64
0x14007c64a  lea     rax, [rbp+SRWLock]
0x14007c64e  mov     [rsp+140h+var_110], rax; __int64
0x14007c653  lea     rax, [rbp+var_8]
0x14007c657  mov     [rsp+140h+var_118], rax; __int64
0x14007c65c  lea     rax, [rbp+var_58]
0x14007c660  mov     [rsp+140h+var_120], rax; __int64
0x14007c665  lea     rdx, word_140136C2E; int
0x14007c66c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14007c671  jmp     loc_14007C71B
0x14007c676  mov     [rbp+SRWLock], 0
0x14007c67e  lea     rdx, [rbp+SRWLock]
0x14007c682  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14007c687  mov     rax, [rbx+110h]
0x14007c68e  mov     dword ptr [rax], 2
0x14007c694  mov     rcx, [rbp+SRWLock]; SRWLock
0x14007c698  test    rcx, rcx
0x14007c69b  jz      short loc_14007C6A3
0x14007c69d  call    cs:__imp_ReleaseSRWLockExclusive
0x14007c6a3  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14007c6a8  mov     rdi, [rax+8]
0x14007c6ac  mov     eax, [rdi]
0x14007c6ae  cmp     eax, 4
0x14007c6b1  jbe     short loc_14007C71B
0x14007c6b3  mov     rcx, [rdi+18h]
0x14007c6b7  mov     rax, [rdi+10h]
0x14007c6bb  test    al, 1
0x14007c6bd  jz      short loc_14007C71B
0x14007c6bf  mov     rax, rcx
0x14007c6c2  and     eax, 1
0x14007c6c5  cmp     rax, rcx
0x14007c6c8  jnz     short loc_14007C71B
0x14007c6ca  call    cs:__imp_GetCurrentThreadId
0x14007c6d0  mov     dword ptr [rbp+SRWLock], eax
0x14007c6d3  mov     r8, [rbx+110h]
0x14007c6da  mov     eax, [r8+48h]
0x14007c6de  mov     dword ptr [rbp+var_78], eax
0x14007c6e1  mov     [rbp+var_58], 0
0x14007c6e9  add     r8, 8
0x14007c6ed  lea     rax, [rbp+SRWLock]
0x14007c6f1  mov     [rsp+140h+var_110], rax
0x14007c6f6  lea     rax, [rbp+var_78]
0x14007c6fa  mov     [rsp+140h+var_118], rax
0x14007c6ff  lea     rax, [rbp+var_58]
0x14007c703  mov     [rsp+140h+var_120], rax
0x14007c708  xor     r9d, r9d
0x14007c70b  lea     rdx, unk_140136BD0
0x14007c712  mov     rcx, rdi
0x14007c715  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14007c71a  nop
0x14007c71b  lea     rcx, [rbx+120h]; this
0x14007c722  cmp     dword ptr [rcx+18h], 0
0x14007c726  jz      short loc_14007C72E
0x14007c728  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14007c72d  nop
0x14007c72e  lea     r11, [rsp+140h+var_s0]
0x14007c736  mov     rbx, [r11+18h]
0x14007c73a  mov     rdi, [r11+20h]
0x14007c73e  mov     rsp, r11
0x14007c741  pop     rbp
0x14007c742  retn
```
