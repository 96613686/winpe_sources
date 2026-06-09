# ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Terminate::StopActivity(void)

- ea: `0x14007c750`
- end: `0x14007ca23`
- name: `?StopActivity@ComputeSystemManager_Terminate@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Terminate *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x14007c750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c7b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c97d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c7b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007c97d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007c9aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007c9aa`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Terminate::StopActivity(
        ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Terminate *this)
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
        (int)&byte_140136A77,
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
        (unsigned int)&unk_140136A18,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::ComputeSystemManager_Terminate *)((char *)this + 288));
}

```

## disassembly

```asm
0x14007c750  mov     [rsp-8+arg_8], rbx
0x14007c755  mov     [rsp-8+arg_10], rdi
0x14007c75a  push    rbp
0x14007c75b  mov     rbp, rsp
0x14007c75e  sub     rsp, 140h
0x14007c765  mov     rbx, rcx
0x14007c768  mov     rdi, [rcx+110h]
0x14007c76f  mov     eax, [rdi+48h]
0x14007c772  test    eax, eax
0x14007c774  jns     loc_14007C956
0x14007c77a  add     rdi, 50h ; 'P'
0x14007c77e  cmp     eax, [rdi+8]
0x14007c781  jnz     loc_14007C956
0x14007c787  test    rdi, rdi
0x14007c78a  jz      loc_14007C956
0x14007c790  mov     [rbp+SRWLock], 0
0x14007c798  lea     rdx, [rbp+SRWLock]
0x14007c79c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14007c7a1  mov     rax, [rbx+110h]
0x14007c7a8  mov     dword ptr [rax], 2
0x14007c7ae  mov     rcx, [rbp+SRWLock]; SRWLock
0x14007c7b2  test    rcx, rcx
0x14007c7b5  jz      short loc_14007C7BD
0x14007c7b7  call    cs:__imp_ReleaseSRWLockExclusive
0x14007c7bd  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14007c7c2  mov     rcx, [rax+8]; int
0x14007c7c6  mov     eax, [rcx]
0x14007c7c8  cmp     eax, 4
0x14007c7cb  jbe     loc_14007C9FB
0x14007c7d1  mov     rdx, [rcx+18h]
0x14007c7d5  mov     rax, [rcx+10h]
0x14007c7d9  test    al, 1
0x14007c7db  jz      loc_14007C9FB
0x14007c7e1  mov     rax, rdx
0x14007c7e4  and     eax, 1
0x14007c7e7  cmp     rax, rdx
0x14007c7ea  jnz     loc_14007C9FB
0x14007c7f0  mov     rax, [rdi+30h]
0x14007c7f4  mov     [rbp+var_50], rax
0x14007c7f8  mov     eax, [rdi+44h]
0x14007c7fb  mov     dword ptr [rbp+var_78+4], eax
0x14007c7fe  mov     eax, [rdi+10h]
0x14007c801  mov     dword ptr [rbp+var_70], eax
0x14007c804  mov     rax, [rdi+78h]
0x14007c808  mov     [rbp+var_48], rax
0x14007c80c  mov     rax, [rdi+70h]
0x14007c810  mov     [rbp+var_40], rax
0x14007c814  mov     eax, [rdi+68h]
0x14007c817  mov     dword ptr [rbp+var_70+4], eax
0x14007c81a  mov     rax, [rdi+60h]
0x14007c81e  mov     [rbp+var_38], rax
0x14007c822  mov     rax, [rdi+58h]
0x14007c826  mov     [rbp+var_30], rax
0x14007c82a  mov     eax, [rdi+50h]
0x14007c82d  mov     dword ptr [rbp+var_68], eax
0x14007c830  mov     rax, [rdi+48h]
0x14007c834  mov     [rbp+var_28], rax
0x14007c838  mov     eax, [rdi+20h]
0x14007c83b  mov     dword ptr [rbp+var_68+4], eax
0x14007c83e  mov     rax, [rdi+18h]
0x14007c842  mov     [rbp+var_20], rax
0x14007c846  mov     eax, [rdi]
0x14007c848  mov     [rbp+var_60], eax
0x14007c84b  mov     rax, [rdi+80h]
0x14007c852  mov     [rbp+var_18], rax
0x14007c856  mov     eax, [rdi+40h]
0x14007c859  mov     dword ptr [rbp+var_78], eax
0x14007c85c  mov     rax, [rdi+38h]
0x14007c860  mov     [rbp+var_10], rax
0x14007c864  mov     eax, [rdi+8]
0x14007c867  mov     dword ptr [rbp+SRWLock], eax
0x14007c86a  mov     [rbp+var_8], 1000000h
0x14007c872  mov     [rbp+var_58], 0
0x14007c87a  mov     r8, [rbx+110h]
0x14007c881  add     r8, 8; int
0x14007c885  lea     rax, [rbp+var_50]
0x14007c889  mov     [rsp+140h+var_90], rax; __int64
0x14007c891  lea     rax, [rbp+var_78+4]
0x14007c895  mov     [rsp+140h+var_98], rax; __int64
0x14007c89d  lea     rax, [rbp+var_70]
0x14007c8a1  mov     [rsp+140h+var_A0], rax; __int64
0x14007c8a9  lea     rax, [rbp+var_48]
0x14007c8ad  mov     [rsp+140h+var_A8], rax; __int64
0x14007c8b5  lea     rax, [rbp+var_40]
0x14007c8b9  mov     [rsp+140h+var_B0], rax; __int64
0x14007c8c1  lea     rax, [rbp+var_70+4]
0x14007c8c5  mov     [rsp+140h+var_B8], rax; __int64
0x14007c8cd  lea     rax, [rbp+var_38]
0x14007c8d1  mov     [rsp+140h+var_C0], rax; __int64
0x14007c8d9  lea     rax, [rbp+var_30]
0x14007c8dd  mov     [rsp+140h+var_C8], rax; __int64
0x14007c8e2  lea     rax, [rbp+var_68]
0x14007c8e6  mov     [rsp+140h+var_D0], rax; __int64
0x14007c8eb  lea     rax, [rbp+var_28]
0x14007c8ef  mov     [rsp+140h+var_D8], rax; __int64
0x14007c8f4  lea     rax, [rbp+var_68+4]
0x14007c8f8  mov     [rsp+140h+var_E0], rax; __int64
0x14007c8fd  lea     rax, [rbp+var_20]
0x14007c901  mov     [rsp+140h+var_E8], rax; __int64
0x14007c906  lea     rax, [rbp+var_60]
0x14007c90a  mov     [rsp+140h+var_F0], rax; __int64
0x14007c90f  lea     rax, [rbp+var_18]
0x14007c913  mov     [rsp+140h+var_F8], rax; __int64
0x14007c918  lea     rax, [rbp+var_78]
0x14007c91c  mov     [rsp+140h+var_100], rax; __int64
0x14007c921  lea     rax, [rbp+var_10]
0x14007c925  mov     [rsp+140h+var_108], rax; __int64
0x14007c92a  lea     rax, [rbp+SRWLock]
0x14007c92e  mov     [rsp+140h+var_110], rax; __int64
0x14007c933  lea     rax, [rbp+var_8]
0x14007c937  mov     [rsp+140h+var_118], rax; __int64
0x14007c93c  lea     rax, [rbp+var_58]
0x14007c940  mov     [rsp+140h+var_120], rax; __int64
0x14007c945  lea     rdx, byte_140136A77; int
0x14007c94c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14007c951  jmp     loc_14007C9FB
0x14007c956  mov     [rbp+SRWLock], 0
0x14007c95e  lea     rdx, [rbp+SRWLock]
0x14007c962  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14007c967  mov     rax, [rbx+110h]
0x14007c96e  mov     dword ptr [rax], 2
0x14007c974  mov     rcx, [rbp+SRWLock]; SRWLock
0x14007c978  test    rcx, rcx
0x14007c97b  jz      short loc_14007C983
0x14007c97d  call    cs:__imp_ReleaseSRWLockExclusive
0x14007c983  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x14007c988  mov     rdi, [rax+8]
0x14007c98c  mov     eax, [rdi]
0x14007c98e  cmp     eax, 4
0x14007c991  jbe     short loc_14007C9FB
0x14007c993  mov     rcx, [rdi+18h]
0x14007c997  mov     rax, [rdi+10h]
0x14007c99b  test    al, 1
0x14007c99d  jz      short loc_14007C9FB
0x14007c99f  mov     rax, rcx
0x14007c9a2  and     eax, 1
0x14007c9a5  cmp     rax, rcx
0x14007c9a8  jnz     short loc_14007C9FB
0x14007c9aa  call    cs:__imp_GetCurrentThreadId
0x14007c9b0  mov     dword ptr [rbp+SRWLock], eax
0x14007c9b3  mov     r8, [rbx+110h]
0x14007c9ba  mov     eax, [r8+48h]
0x14007c9be  mov     dword ptr [rbp+var_78], eax
0x14007c9c1  mov     [rbp+var_58], 0
0x14007c9c9  add     r8, 8
0x14007c9cd  lea     rax, [rbp+SRWLock]
0x14007c9d1  mov     [rsp+140h+var_110], rax
0x14007c9d6  lea     rax, [rbp+var_78]
0x14007c9da  mov     [rsp+140h+var_118], rax
0x14007c9df  lea     rax, [rbp+var_58]
0x14007c9e3  mov     [rsp+140h+var_120], rax
0x14007c9e8  xor     r9d, r9d
0x14007c9eb  lea     rdx, unk_140136A18
0x14007c9f2  mov     rcx, rdi
0x14007c9f5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14007c9fa  nop
0x14007c9fb  lea     rcx, [rbx+120h]; this
0x14007ca02  cmp     dword ptr [rcx+18h], 0
0x14007ca06  jz      short loc_14007CA0E
0x14007ca08  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14007ca0d  nop
0x14007ca0e  lea     r11, [rsp+140h+var_s0]
0x14007ca16  mov     rbx, [r11+18h]
0x14007ca1a  mov     rdi, [r11+20h]
0x14007ca1e  mov     rsp, r11
0x14007ca21  pop     rbp
0x14007ca22  retn
```
