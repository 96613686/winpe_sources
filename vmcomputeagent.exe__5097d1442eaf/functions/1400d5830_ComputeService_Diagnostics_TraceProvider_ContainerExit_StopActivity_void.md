# ComputeService::Diagnostics::TraceProvider::ContainerExit::StopActivity(void)

- ea: `0x1400d5830`
- end: `0x1400d5b03`
- name: `?StopActivity@ContainerExit@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::ContainerExit *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x1400d5830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400d5897`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400d5a5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400d5897`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400d5a5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400d5a8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400d5a8a`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::ContainerExit::StopActivity(
        ComputeService::Diagnostics::TraceProvider::ContainerExit *this)
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
    if ( *(_DWORD *)v5 > 4u && (*(_QWORD *)(v5 + 16) & 8) != 0 && (*(_QWORD *)(v5 + 24) & 8LL) == *(_QWORD *)(v5 + 24) )
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
        (int)&byte_14013AC2B,
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
    if ( *(_DWORD *)v6 > 4u && (*(_QWORD *)(v6 + 16) & 8) != 0 && (*(_QWORD *)(v6 + 24) & 8LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)byte_14013AB7B,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::ContainerExit *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400d5830  mov     [rsp-8+arg_8], rbx
0x1400d5835  mov     [rsp-8+arg_10], rdi
0x1400d583a  push    rbp
0x1400d583b  mov     rbp, rsp
0x1400d583e  sub     rsp, 140h
0x1400d5845  mov     rbx, rcx
0x1400d5848  mov     rdi, [rcx+110h]
0x1400d584f  mov     eax, [rdi+48h]
0x1400d5852  test    eax, eax
0x1400d5854  jns     loc_1400D5A36
0x1400d585a  add     rdi, 50h ; 'P'
0x1400d585e  cmp     eax, [rdi+8]
0x1400d5861  jnz     loc_1400D5A36
0x1400d5867  test    rdi, rdi
0x1400d586a  jz      loc_1400D5A36
0x1400d5870  mov     [rbp+SRWLock], 0
0x1400d5878  lea     rdx, [rbp+SRWLock]
0x1400d587c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400d5881  mov     rax, [rbx+110h]
0x1400d5888  mov     dword ptr [rax], 2
0x1400d588e  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400d5892  test    rcx, rcx
0x1400d5895  jz      short loc_1400D589D
0x1400d5897  call    cs:__imp_ReleaseSRWLockExclusive
0x1400d589d  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400d58a2  mov     rcx, [rax+8]; int
0x1400d58a6  mov     eax, [rcx]
0x1400d58a8  cmp     eax, 4
0x1400d58ab  jbe     loc_1400D5ADB
0x1400d58b1  mov     rdx, [rcx+18h]
0x1400d58b5  mov     rax, [rcx+10h]
0x1400d58b9  test    al, 8
0x1400d58bb  jz      loc_1400D5ADB
0x1400d58c1  mov     rax, rdx
0x1400d58c4  and     eax, 8
0x1400d58c7  cmp     rax, rdx
0x1400d58ca  jnz     loc_1400D5ADB
0x1400d58d0  mov     rax, [rdi+30h]
0x1400d58d4  mov     [rbp+var_50], rax
0x1400d58d8  mov     eax, [rdi+44h]
0x1400d58db  mov     dword ptr [rbp+var_78+4], eax
0x1400d58de  mov     eax, [rdi+10h]
0x1400d58e1  mov     dword ptr [rbp+var_70], eax
0x1400d58e4  mov     rax, [rdi+78h]
0x1400d58e8  mov     [rbp+var_48], rax
0x1400d58ec  mov     rax, [rdi+70h]
0x1400d58f0  mov     [rbp+var_40], rax
0x1400d58f4  mov     eax, [rdi+68h]
0x1400d58f7  mov     dword ptr [rbp+var_70+4], eax
0x1400d58fa  mov     rax, [rdi+60h]
0x1400d58fe  mov     [rbp+var_38], rax
0x1400d5902  mov     rax, [rdi+58h]
0x1400d5906  mov     [rbp+var_30], rax
0x1400d590a  mov     eax, [rdi+50h]
0x1400d590d  mov     dword ptr [rbp+var_68], eax
0x1400d5910  mov     rax, [rdi+48h]
0x1400d5914  mov     [rbp+var_28], rax
0x1400d5918  mov     eax, [rdi+20h]
0x1400d591b  mov     dword ptr [rbp+var_68+4], eax
0x1400d591e  mov     rax, [rdi+18h]
0x1400d5922  mov     [rbp+var_20], rax
0x1400d5926  mov     eax, [rdi]
0x1400d5928  mov     [rbp+var_60], eax
0x1400d592b  mov     rax, [rdi+80h]
0x1400d5932  mov     [rbp+var_18], rax
0x1400d5936  mov     eax, [rdi+40h]
0x1400d5939  mov     dword ptr [rbp+var_78], eax
0x1400d593c  mov     rax, [rdi+38h]
0x1400d5940  mov     [rbp+var_10], rax
0x1400d5944  mov     eax, [rdi+8]
0x1400d5947  mov     dword ptr [rbp+SRWLock], eax
0x1400d594a  mov     [rbp+var_8], 1000000h
0x1400d5952  mov     [rbp+var_58], 0
0x1400d595a  mov     r8, [rbx+110h]
0x1400d5961  add     r8, 8; int
0x1400d5965  lea     rax, [rbp+var_50]
0x1400d5969  mov     [rsp+140h+var_90], rax; __int64
0x1400d5971  lea     rax, [rbp+var_78+4]
0x1400d5975  mov     [rsp+140h+var_98], rax; __int64
0x1400d597d  lea     rax, [rbp+var_70]
0x1400d5981  mov     [rsp+140h+var_A0], rax; __int64
0x1400d5989  lea     rax, [rbp+var_48]
0x1400d598d  mov     [rsp+140h+var_A8], rax; __int64
0x1400d5995  lea     rax, [rbp+var_40]
0x1400d5999  mov     [rsp+140h+var_B0], rax; __int64
0x1400d59a1  lea     rax, [rbp+var_70+4]
0x1400d59a5  mov     [rsp+140h+var_B8], rax; __int64
0x1400d59ad  lea     rax, [rbp+var_38]
0x1400d59b1  mov     [rsp+140h+var_C0], rax; __int64
0x1400d59b9  lea     rax, [rbp+var_30]
0x1400d59bd  mov     [rsp+140h+var_C8], rax; __int64
0x1400d59c2  lea     rax, [rbp+var_68]
0x1400d59c6  mov     [rsp+140h+var_D0], rax; __int64
0x1400d59cb  lea     rax, [rbp+var_28]
0x1400d59cf  mov     [rsp+140h+var_D8], rax; __int64
0x1400d59d4  lea     rax, [rbp+var_68+4]
0x1400d59d8  mov     [rsp+140h+var_E0], rax; __int64
0x1400d59dd  lea     rax, [rbp+var_20]
0x1400d59e1  mov     [rsp+140h+var_E8], rax; __int64
0x1400d59e6  lea     rax, [rbp+var_60]
0x1400d59ea  mov     [rsp+140h+var_F0], rax; __int64
0x1400d59ef  lea     rax, [rbp+var_18]
0x1400d59f3  mov     [rsp+140h+var_F8], rax; __int64
0x1400d59f8  lea     rax, [rbp+var_78]
0x1400d59fc  mov     [rsp+140h+var_100], rax; __int64
0x1400d5a01  lea     rax, [rbp+var_10]
0x1400d5a05  mov     [rsp+140h+var_108], rax; __int64
0x1400d5a0a  lea     rax, [rbp+SRWLock]
0x1400d5a0e  mov     [rsp+140h+var_110], rax; __int64
0x1400d5a13  lea     rax, [rbp+var_8]
0x1400d5a17  mov     [rsp+140h+var_118], rax; __int64
0x1400d5a1c  lea     rax, [rbp+var_58]
0x1400d5a20  mov     [rsp+140h+var_120], rax; __int64
0x1400d5a25  lea     rdx, byte_14013AC2B; int
0x1400d5a2c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400d5a31  jmp     loc_1400D5ADB
0x1400d5a36  mov     [rbp+SRWLock], 0
0x1400d5a3e  lea     rdx, [rbp+SRWLock]
0x1400d5a42  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400d5a47  mov     rax, [rbx+110h]
0x1400d5a4e  mov     dword ptr [rax], 2
0x1400d5a54  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400d5a58  test    rcx, rcx
0x1400d5a5b  jz      short loc_1400D5A63
0x1400d5a5d  call    cs:__imp_ReleaseSRWLockExclusive
0x1400d5a63  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400d5a68  mov     rdi, [rax+8]
0x1400d5a6c  mov     eax, [rdi]
0x1400d5a6e  cmp     eax, 4
0x1400d5a71  jbe     short loc_1400D5ADB
0x1400d5a73  mov     rcx, [rdi+18h]
0x1400d5a77  mov     rax, [rdi+10h]
0x1400d5a7b  test    al, 8
0x1400d5a7d  jz      short loc_1400D5ADB
0x1400d5a7f  mov     rax, rcx
0x1400d5a82  and     eax, 8
0x1400d5a85  cmp     rax, rcx
0x1400d5a88  jnz     short loc_1400D5ADB
0x1400d5a8a  call    cs:__imp_GetCurrentThreadId
0x1400d5a90  mov     dword ptr [rbp+SRWLock], eax
0x1400d5a93  mov     r8, [rbx+110h]
0x1400d5a9a  mov     eax, [r8+48h]
0x1400d5a9e  mov     dword ptr [rbp+var_78], eax
0x1400d5aa1  mov     [rbp+var_58], 0
0x1400d5aa9  add     r8, 8
0x1400d5aad  lea     rax, [rbp+SRWLock]
0x1400d5ab1  mov     [rsp+140h+var_110], rax
0x1400d5ab6  lea     rax, [rbp+var_78]
0x1400d5aba  mov     [rsp+140h+var_118], rax
0x1400d5abf  lea     rax, [rbp+var_58]
0x1400d5ac3  mov     [rsp+140h+var_120], rax
0x1400d5ac8  xor     r9d, r9d
0x1400d5acb  lea     rdx, byte_14013AB7B
0x1400d5ad2  mov     rcx, rdi
0x1400d5ad5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400d5ada  nop
0x1400d5adb  lea     rcx, [rbx+120h]; this
0x1400d5ae2  cmp     dword ptr [rcx+18h], 0
0x1400d5ae6  jz      short loc_1400D5AEE
0x1400d5ae8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400d5aed  nop
0x1400d5aee  lea     r11, [rsp+140h+var_s0]
0x1400d5af6  mov     rbx, [r11+18h]
0x1400d5afa  mov     rdi, [r11+20h]
0x1400d5afe  mov     rsp, r11
0x1400d5b01  pop     rbp
0x1400d5b02  retn
```
