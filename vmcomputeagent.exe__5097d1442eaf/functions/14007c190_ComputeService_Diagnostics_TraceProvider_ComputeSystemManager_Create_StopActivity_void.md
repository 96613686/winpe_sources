# ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create::StopActivity(void)

- ea: `0x14007c190`
- end: `0x14007c463`
- name: `?StopActivity@ComputeSystemManager_Create@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x14007c190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c1f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c3bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c1f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c3bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007c3ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007c3ea`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create::StopActivity(
        ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create *this)
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
        (int)&byte_140136E57,
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
        (unsigned int)&word_140136D86,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Create *)((char *)this + 288));
}

```

## disassembly

```asm
0x14007c190  mov     [rsp-8+arg_8], rbx
0x14007c195  mov     [rsp-8+arg_10], rdi
0x14007c19a  push    rbp
0x14007c19b  mov     rbp, rsp
0x14007c19e  sub     rsp, 140h
0x14007c1a5  mov     rbx, rcx
0x14007c1a8  mov     rdi, [rcx+110h]
0x14007c1af  mov     eax, [rdi+48h]
0x14007c1b2  test    eax, eax
0x14007c1b4  jns     loc_14007C396
0x14007c1ba  add     rdi, 50h ; 'P'
0x14007c1be  cmp     eax, [rdi+8]
0x14007c1c1  jnz     loc_14007C396
0x14007c1c7  test    rdi, rdi
0x14007c1ca  jz      loc_14007C396
0x14007c1d0  mov     [rbp+SRWLock], 0
0x14007c1d8  lea     rdx, [rbp+SRWLock]
0x14007c1dc  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14007c1e1  mov     rax, [rbx+110h]
0x14007c1e8  mov     dword ptr [rax], 2
0x14007c1ee  mov     rcx, [rbp+SRWLock]; SRWLock
0x14007c1f2  test    rcx, rcx
0x14007c1f5  jz      short loc_14007C1FD
0x14007c1f7  call    cs:__imp_ReleaseSRWLockExclusive
0x14007c1fd  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14007c202  mov     rcx, [rax+8]; int
0x14007c206  mov     eax, [rcx]
0x14007c208  cmp     eax, 4
0x14007c20b  jbe     loc_14007C43B
0x14007c211  mov     rdx, [rcx+18h]
0x14007c215  mov     rax, [rcx+10h]
0x14007c219  test    al, 1
0x14007c21b  jz      loc_14007C43B
0x14007c221  mov     rax, rdx
0x14007c224  and     eax, 1
0x14007c227  cmp     rax, rdx
0x14007c22a  jnz     loc_14007C43B
0x14007c230  mov     rax, [rdi+30h]
0x14007c234  mov     [rbp+var_50], rax
0x14007c238  mov     eax, [rdi+44h]
0x14007c23b  mov     dword ptr [rbp+var_78+4], eax
0x14007c23e  mov     eax, [rdi+10h]
0x14007c241  mov     dword ptr [rbp+var_70], eax
0x14007c244  mov     rax, [rdi+78h]
0x14007c248  mov     [rbp+var_48], rax
0x14007c24c  mov     rax, [rdi+70h]
0x14007c250  mov     [rbp+var_40], rax
0x14007c254  mov     eax, [rdi+68h]
0x14007c257  mov     dword ptr [rbp+var_70+4], eax
0x14007c25a  mov     rax, [rdi+60h]
0x14007c25e  mov     [rbp+var_38], rax
0x14007c262  mov     rax, [rdi+58h]
0x14007c266  mov     [rbp+var_30], rax
0x14007c26a  mov     eax, [rdi+50h]
0x14007c26d  mov     dword ptr [rbp+var_68], eax
0x14007c270  mov     rax, [rdi+48h]
0x14007c274  mov     [rbp+var_28], rax
0x14007c278  mov     eax, [rdi+20h]
0x14007c27b  mov     dword ptr [rbp+var_68+4], eax
0x14007c27e  mov     rax, [rdi+18h]
0x14007c282  mov     [rbp+var_20], rax
0x14007c286  mov     eax, [rdi]
0x14007c288  mov     [rbp+var_60], eax
0x14007c28b  mov     rax, [rdi+80h]
0x14007c292  mov     [rbp+var_18], rax
0x14007c296  mov     eax, [rdi+40h]
0x14007c299  mov     dword ptr [rbp+var_78], eax
0x14007c29c  mov     rax, [rdi+38h]
0x14007c2a0  mov     [rbp+var_10], rax
0x14007c2a4  mov     eax, [rdi+8]
0x14007c2a7  mov     dword ptr [rbp+SRWLock], eax
0x14007c2aa  mov     [rbp+var_8], 1000000h
0x14007c2b2  mov     [rbp+var_58], 0
0x14007c2ba  mov     r8, [rbx+110h]
0x14007c2c1  add     r8, 8; int
0x14007c2c5  lea     rax, [rbp+var_50]
0x14007c2c9  mov     [rsp+140h+var_90], rax; __int64
0x14007c2d1  lea     rax, [rbp+var_78+4]
0x14007c2d5  mov     [rsp+140h+var_98], rax; __int64
0x14007c2dd  lea     rax, [rbp+var_70]
0x14007c2e1  mov     [rsp+140h+var_A0], rax; __int64
0x14007c2e9  lea     rax, [rbp+var_48]
0x14007c2ed  mov     [rsp+140h+var_A8], rax; __int64
0x14007c2f5  lea     rax, [rbp+var_40]
0x14007c2f9  mov     [rsp+140h+var_B0], rax; __int64
0x14007c301  lea     rax, [rbp+var_70+4]
0x14007c305  mov     [rsp+140h+var_B8], rax; __int64
0x14007c30d  lea     rax, [rbp+var_38]
0x14007c311  mov     [rsp+140h+var_C0], rax; __int64
0x14007c319  lea     rax, [rbp+var_30]
0x14007c31d  mov     [rsp+140h+var_C8], rax; __int64
0x14007c322  lea     rax, [rbp+var_68]
0x14007c326  mov     [rsp+140h+var_D0], rax; __int64
0x14007c32b  lea     rax, [rbp+var_28]
0x14007c32f  mov     [rsp+140h+var_D8], rax; __int64
0x14007c334  lea     rax, [rbp+var_68+4]
0x14007c338  mov     [rsp+140h+var_E0], rax; __int64
0x14007c33d  lea     rax, [rbp+var_20]
0x14007c341  mov     [rsp+140h+var_E8], rax; __int64
0x14007c346  lea     rax, [rbp+var_60]
0x14007c34a  mov     [rsp+140h+var_F0], rax; __int64
0x14007c34f  lea     rax, [rbp+var_18]
0x14007c353  mov     [rsp+140h+var_F8], rax; __int64
0x14007c358  lea     rax, [rbp+var_78]
0x14007c35c  mov     [rsp+140h+var_100], rax; __int64
0x14007c361  lea     rax, [rbp+var_10]
0x14007c365  mov     [rsp+140h+var_108], rax; __int64
0x14007c36a  lea     rax, [rbp+SRWLock]
0x14007c36e  mov     [rsp+140h+var_110], rax; __int64
0x14007c373  lea     rax, [rbp+var_8]
0x14007c377  mov     [rsp+140h+var_118], rax; __int64
0x14007c37c  lea     rax, [rbp+var_58]
0x14007c380  mov     [rsp+140h+var_120], rax; __int64
0x14007c385  lea     rdx, byte_140136E57; int
0x14007c38c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14007c391  jmp     loc_14007C43B
0x14007c396  mov     [rbp+SRWLock], 0
0x14007c39e  lea     rdx, [rbp+SRWLock]
0x14007c3a2  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14007c3a7  mov     rax, [rbx+110h]
0x14007c3ae  mov     dword ptr [rax], 2
0x14007c3b4  mov     rcx, [rbp+SRWLock]; SRWLock
0x14007c3b8  test    rcx, rcx
0x14007c3bb  jz      short loc_14007C3C3
0x14007c3bd  call    cs:__imp_ReleaseSRWLockExclusive
0x14007c3c3  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14007c3c8  mov     rdi, [rax+8]
0x14007c3cc  mov     eax, [rdi]
0x14007c3ce  cmp     eax, 4
0x14007c3d1  jbe     short loc_14007C43B
0x14007c3d3  mov     rcx, [rdi+18h]
0x14007c3d7  mov     rax, [rdi+10h]
0x14007c3db  test    al, 1
0x14007c3dd  jz      short loc_14007C43B
0x14007c3df  mov     rax, rcx
0x14007c3e2  and     eax, 1
0x14007c3e5  cmp     rax, rcx
0x14007c3e8  jnz     short loc_14007C43B
0x14007c3ea  call    cs:__imp_GetCurrentThreadId
0x14007c3f0  mov     dword ptr [rbp+SRWLock], eax
0x14007c3f3  mov     r8, [rbx+110h]
0x14007c3fa  mov     eax, [r8+48h]
0x14007c3fe  mov     dword ptr [rbp+var_78], eax
0x14007c401  mov     [rbp+var_58], 0
0x14007c409  add     r8, 8
0x14007c40d  lea     rax, [rbp+SRWLock]
0x14007c411  mov     [rsp+140h+var_110], rax
0x14007c416  lea     rax, [rbp+var_78]
0x14007c41a  mov     [rsp+140h+var_118], rax
0x14007c41f  lea     rax, [rbp+var_58]
0x14007c423  mov     [rsp+140h+var_120], rax
0x14007c428  xor     r9d, r9d
0x14007c42b  lea     rdx, word_140136D86
0x14007c432  mov     rcx, rdi
0x14007c435  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14007c43a  nop
0x14007c43b  lea     rcx, [rbx+120h]; this
0x14007c442  cmp     dword ptr [rcx+18h], 0
0x14007c446  jz      short loc_14007C44E
0x14007c448  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14007c44d  nop
0x14007c44e  lea     r11, [rsp+140h+var_s0]
0x14007c456  mov     rbx, [r11+18h]
0x14007c45a  mov     rdi, [r11+20h]
0x14007c45e  mov     rsp, r11
0x14007c461  pop     rbp
0x14007c462  retn
```
