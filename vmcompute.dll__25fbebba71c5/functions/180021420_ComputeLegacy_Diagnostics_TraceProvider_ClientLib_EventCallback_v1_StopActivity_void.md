# ComputeLegacy::Diagnostics::TraceProvider::ClientLib_EventCallback_v1::StopActivity(void)

- ea: `0x180021420`
- end: `0x180021716`
- name: `?StopActivity@ClientLib_EventCallback_v1@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `758`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::ClientLib_EventCallback_v1 *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021420`
- `0x180021d1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021487`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002165d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021487`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002165d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021696`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::ClientLib_EventCallback_v1::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::ClientLib_EventCallback_v1 *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
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
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 4u
      && (*(_QWORD *)(v5 + 16) & 0x10000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x10000LL) == *(_QWORD *)(v5 + 24) )
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
        (int)&byte_18009D47F,
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
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 4u
      && (*(_QWORD *)(v6 + 16) & 0x10000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x10000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&dword_18009D774,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::ClientLib_EventCallback_v1 *)((char *)this + 288));
}

```

## disassembly

```asm
0x180021420  mov     [rsp-8+arg_8], rbx
0x180021425  mov     [rsp-8+arg_10], rdi
0x18002142a  push    rbp
0x18002142b  mov     rbp, rsp
0x18002142e  sub     rsp, 140h
0x180021435  mov     rbx, rcx
0x180021438  mov     rdi, [rcx+110h]
0x18002143f  mov     eax, [rdi+48h]
0x180021442  test    eax, eax
0x180021444  jns     loc_180021636
0x18002144a  add     rdi, 50h ; 'P'
0x18002144e  cmp     eax, [rdi+8]
0x180021451  jnz     loc_180021636
0x180021457  test    rdi, rdi
0x18002145a  jz      loc_180021636
0x180021460  mov     [rbp+SRWLock], 0
0x180021468  lea     rdx, [rbp+SRWLock]
0x18002146c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180021471  mov     rax, [rbx+110h]
0x180021478  mov     dword ptr [rax], 2
0x18002147e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180021482  test    rcx, rcx
0x180021485  jz      short loc_180021493
0x180021487  call    cs:__imp_ReleaseSRWLockExclusive
0x18002148e  nop     dword ptr [rax+rax+00h]
0x180021493  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180021498  mov     r9, [rax+8]
0x18002149c  mov     eax, [r9]
0x18002149f  cmp     eax, 4
0x1800214a2  jbe     loc_1800216ED
0x1800214a8  mov     rdx, [r9+18h]
0x1800214ac  mov     rax, [r9+10h]
0x1800214b0  mov     ecx, 10000h
0x1800214b5  test    rcx, rax
0x1800214b8  jz      loc_1800216ED
0x1800214be  mov     rax, rdx
0x1800214c1  and     rax, rcx
0x1800214c4  cmp     rax, rdx
0x1800214c7  jnz     loc_1800216ED
0x1800214cd  mov     rax, [rdi+30h]
0x1800214d1  mov     [rbp+var_50], rax
0x1800214d5  mov     eax, [rdi+44h]
0x1800214d8  mov     dword ptr [rbp+var_78+4], eax
0x1800214db  mov     eax, [rdi+10h]
0x1800214de  mov     dword ptr [rbp+var_70], eax
0x1800214e1  mov     rax, [rdi+78h]
0x1800214e5  mov     [rbp+var_48], rax
0x1800214e9  mov     rax, [rdi+70h]
0x1800214ed  mov     [rbp+var_40], rax
0x1800214f1  mov     eax, [rdi+68h]
0x1800214f4  mov     dword ptr [rbp+var_70+4], eax
0x1800214f7  mov     rax, [rdi+60h]
0x1800214fb  mov     [rbp+var_38], rax
0x1800214ff  mov     rax, [rdi+58h]
0x180021503  mov     [rbp+var_30], rax
0x180021507  mov     eax, [rdi+50h]
0x18002150a  mov     dword ptr [rbp+var_68], eax
0x18002150d  mov     rax, [rdi+48h]
0x180021511  mov     [rbp+var_28], rax
0x180021515  mov     eax, [rdi+20h]
0x180021518  mov     dword ptr [rbp+var_68+4], eax
0x18002151b  mov     rax, [rdi+18h]
0x18002151f  mov     [rbp+var_20], rax
0x180021523  mov     eax, [rdi]
0x180021525  mov     [rbp+var_60], eax
0x180021528  mov     rax, [rdi+80h]
0x18002152f  mov     [rbp+var_18], rax
0x180021533  mov     eax, [rdi+40h]
0x180021536  mov     dword ptr [rbp+var_78], eax
0x180021539  mov     rax, [rdi+38h]
0x18002153d  mov     [rbp+var_10], rax
0x180021541  mov     eax, [rdi+8]
0x180021544  mov     dword ptr [rbp+SRWLock], eax
0x180021547  mov     [rbp+var_8], 1000000h
0x18002154f  mov     [rbp+var_58], 0
0x180021557  mov     r8, [rbx+110h]
0x18002155e  add     r8, 8; int
0x180021562  lea     rax, [rbp+var_50]
0x180021566  mov     [rsp+140h+var_90], rax; __int64
0x18002156e  lea     rax, [rbp+var_78+4]
0x180021572  mov     [rsp+140h+var_98], rax; __int64
0x18002157a  lea     rax, [rbp+var_70]
0x18002157e  mov     [rsp+140h+var_A0], rax; __int64
0x180021586  lea     rax, [rbp+var_48]
0x18002158a  mov     [rsp+140h+var_A8], rax; __int64
0x180021592  lea     rax, [rbp+var_40]
0x180021596  mov     [rsp+140h+var_B0], rax; __int64
0x18002159e  lea     rax, [rbp+var_70+4]
0x1800215a2  mov     [rsp+140h+var_B8], rax; __int64
0x1800215aa  lea     rax, [rbp+var_38]
0x1800215ae  mov     [rsp+140h+var_C0], rax; __int64
0x1800215b6  lea     rax, [rbp+var_30]
0x1800215ba  mov     [rsp+140h+var_C8], rax; __int64
0x1800215bf  lea     rax, [rbp+var_68]
0x1800215c3  mov     [rsp+140h+var_D0], rax; __int64
0x1800215c8  lea     rax, [rbp+var_28]
0x1800215cc  mov     [rsp+140h+var_D8], rax; __int64
0x1800215d1  lea     rax, [rbp+var_68+4]
0x1800215d5  mov     [rsp+140h+var_E0], rax; __int64
0x1800215da  lea     rax, [rbp+var_20]
0x1800215de  mov     [rsp+140h+var_E8], rax; __int64
0x1800215e3  lea     rax, [rbp+var_60]
0x1800215e7  mov     [rsp+140h+var_F0], rax; __int64
0x1800215ec  lea     rax, [rbp+var_18]
0x1800215f0  mov     [rsp+140h+var_F8], rax; __int64
0x1800215f5  lea     rax, [rbp+var_78]
0x1800215f9  mov     [rsp+140h+var_100], rax; __int64
0x1800215fe  lea     rax, [rbp+var_10]
0x180021602  mov     [rsp+140h+var_108], rax; __int64
0x180021607  lea     rax, [rbp+SRWLock]
0x18002160b  mov     [rsp+140h+var_110], rax; __int64
0x180021610  lea     rax, [rbp+var_8]
0x180021614  mov     [rsp+140h+var_118], rax; __int64
0x180021619  lea     rax, [rbp+var_58]
0x18002161d  mov     [rsp+140h+var_120], rax; __int64
0x180021622  lea     rdx, byte_18009D47F; int
0x180021629  mov     rcx, r9; int
0x18002162c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180021631  jmp     loc_1800216ED
0x180021636  mov     [rbp+SRWLock], 0
0x18002163e  lea     rdx, [rbp+SRWLock]
0x180021642  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180021647  mov     rax, [rbx+110h]
0x18002164e  mov     dword ptr [rax], 2
0x180021654  mov     rcx, [rbp+SRWLock]; SRWLock
0x180021658  test    rcx, rcx
0x18002165b  jz      short loc_180021669
0x18002165d  call    cs:__imp_ReleaseSRWLockExclusive
0x180021664  nop     dword ptr [rax+rax+00h]
0x180021669  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x18002166e  mov     rdi, [rax+8]
0x180021672  mov     eax, [rdi]
0x180021674  cmp     eax, 4
0x180021677  jbe     short loc_1800216ED
0x180021679  mov     rdx, [rdi+18h]
0x18002167d  mov     rax, [rdi+10h]
0x180021681  mov     ecx, 10000h
0x180021686  test    rcx, rax
0x180021689  jz      short loc_1800216ED
0x18002168b  mov     rax, rdx
0x18002168e  and     rax, rcx
0x180021691  cmp     rax, rdx
0x180021694  jnz     short loc_1800216ED
0x180021696  call    cs:__imp_GetCurrentThreadId
0x18002169d  nop     dword ptr [rax+rax+00h]
0x1800216a2  mov     dword ptr [rbp+SRWLock], eax
0x1800216a5  mov     r8, [rbx+110h]
0x1800216ac  mov     eax, [r8+48h]
0x1800216b0  mov     dword ptr [rbp+var_78], eax
0x1800216b3  mov     [rbp+var_58], 0
0x1800216bb  add     r8, 8
0x1800216bf  lea     rax, [rbp+SRWLock]
0x1800216c3  mov     [rsp+140h+var_110], rax
0x1800216c8  lea     rax, [rbp+var_78]
0x1800216cc  mov     [rsp+140h+var_118], rax
0x1800216d1  lea     rax, [rbp+var_58]
0x1800216d5  mov     [rsp+140h+var_120], rax
0x1800216da  xor     r9d, r9d
0x1800216dd  lea     rdx, dword_18009D774
0x1800216e4  mov     rcx, rdi
0x1800216e7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800216ec  nop
0x1800216ed  lea     rcx, [rbx+120h]; this
0x1800216f4  cmp     dword ptr [rcx+18h], 0
0x1800216f8  jz      short loc_180021700
0x1800216fa  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800216ff  nop
0x180021700  lea     r11, [rsp+140h+var_s0]
0x180021708  mov     rbx, [r11+18h]
0x18002170c  mov     rdi, [r11+20h]
0x180021710  mov     rsp, r11
0x180021713  pop     rbp
0x180021714  retn
```
