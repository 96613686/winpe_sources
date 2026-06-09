# ComputeService::Diagnostics::TraceProvider::Bridge_Receive::StopActivity(void)

- ea: `0x1400573d0`
- end: `0x1400576a3`
- name: `?StopActivity@Bridge_Receive@TraceProvider@Diagnostics@ComputeService@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(ComputeService::Diagnostics::TraceProvider::Bridge_Receive *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x14000aeec`
- `0x140031be8`
- `0x14003407c`
- `0x1400573d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140057437`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400575fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140057437`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400575fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005762a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005762a`

## pseudocode

```c
void __fastcall ComputeService::Diagnostics::TraceProvider::Bridge_Receive::StopActivity(
        ComputeService::Diagnostics::TraceProvider::Bridge_Receive *this)
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
    if ( *(_DWORD *)v5 > 5u && (*(_QWORD *)(v5 + 16) & 2) != 0 && (*(_QWORD *)(v5 + 24) & 2LL) == *(_QWORD *)(v5 + 24) )
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
        (int)&byte_140134A71,
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
    if ( *(_DWORD *)v6 > 5u && (*(_QWORD *)(v6 + 16) & 2) != 0 && (*(_QWORD *)(v6 + 24) & 2LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)word_140134A22,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeService::Diagnostics::TraceProvider::Bridge_Receive *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400573d0  mov     [rsp-8+arg_8], rbx
0x1400573d5  mov     [rsp-8+arg_10], rdi
0x1400573da  push    rbp
0x1400573db  mov     rbp, rsp
0x1400573de  sub     rsp, 140h
0x1400573e5  mov     rbx, rcx
0x1400573e8  mov     rdi, [rcx+110h]
0x1400573ef  mov     eax, [rdi+48h]
0x1400573f2  test    eax, eax
0x1400573f4  jns     loc_1400575D6
0x1400573fa  add     rdi, 50h ; 'P'
0x1400573fe  cmp     eax, [rdi+8]
0x140057401  jnz     loc_1400575D6
0x140057407  test    rdi, rdi
0x14005740a  jz      loc_1400575D6
0x140057410  mov     [rbp+SRWLock], 0
0x140057418  lea     rdx, [rbp+SRWLock]
0x14005741c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140057421  mov     rax, [rbx+110h]
0x140057428  mov     dword ptr [rax], 2
0x14005742e  mov     rcx, [rbp+SRWLock]; SRWLock
0x140057432  test    rcx, rcx
0x140057435  jz      short loc_14005743D
0x140057437  call    cs:__imp_ReleaseSRWLockExclusive
0x14005743d  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140057442  mov     rcx, [rax+8]; int
0x140057446  mov     eax, [rcx]
0x140057448  cmp     eax, 5
0x14005744b  jbe     loc_14005767B
0x140057451  mov     rdx, [rcx+18h]
0x140057455  mov     rax, [rcx+10h]
0x140057459  test    al, 2
0x14005745b  jz      loc_14005767B
0x140057461  mov     rax, rdx
0x140057464  and     eax, 2
0x140057467  cmp     rax, rdx
0x14005746a  jnz     loc_14005767B
0x140057470  mov     rax, [rdi+30h]
0x140057474  mov     [rbp+var_50], rax
0x140057478  mov     eax, [rdi+44h]
0x14005747b  mov     dword ptr [rbp+var_78+4], eax
0x14005747e  mov     eax, [rdi+10h]
0x140057481  mov     dword ptr [rbp+var_70], eax
0x140057484  mov     rax, [rdi+78h]
0x140057488  mov     [rbp+var_48], rax
0x14005748c  mov     rax, [rdi+70h]
0x140057490  mov     [rbp+var_40], rax
0x140057494  mov     eax, [rdi+68h]
0x140057497  mov     dword ptr [rbp+var_70+4], eax
0x14005749a  mov     rax, [rdi+60h]
0x14005749e  mov     [rbp+var_38], rax
0x1400574a2  mov     rax, [rdi+58h]
0x1400574a6  mov     [rbp+var_30], rax
0x1400574aa  mov     eax, [rdi+50h]
0x1400574ad  mov     dword ptr [rbp+var_68], eax
0x1400574b0  mov     rax, [rdi+48h]
0x1400574b4  mov     [rbp+var_28], rax
0x1400574b8  mov     eax, [rdi+20h]
0x1400574bb  mov     dword ptr [rbp+var_68+4], eax
0x1400574be  mov     rax, [rdi+18h]
0x1400574c2  mov     [rbp+var_20], rax
0x1400574c6  mov     eax, [rdi]
0x1400574c8  mov     [rbp+var_60], eax
0x1400574cb  mov     rax, [rdi+80h]
0x1400574d2  mov     [rbp+var_18], rax
0x1400574d6  mov     eax, [rdi+40h]
0x1400574d9  mov     dword ptr [rbp+var_78], eax
0x1400574dc  mov     rax, [rdi+38h]
0x1400574e0  mov     [rbp+var_10], rax
0x1400574e4  mov     eax, [rdi+8]
0x1400574e7  mov     dword ptr [rbp+SRWLock], eax
0x1400574ea  mov     [rbp+var_8], 1000000h
0x1400574f2  mov     [rbp+var_58], 0
0x1400574fa  mov     r8, [rbx+110h]
0x140057501  add     r8, 8; int
0x140057505  lea     rax, [rbp+var_50]
0x140057509  mov     [rsp+140h+var_90], rax; __int64
0x140057511  lea     rax, [rbp+var_78+4]
0x140057515  mov     [rsp+140h+var_98], rax; __int64
0x14005751d  lea     rax, [rbp+var_70]
0x140057521  mov     [rsp+140h+var_A0], rax; __int64
0x140057529  lea     rax, [rbp+var_48]
0x14005752d  mov     [rsp+140h+var_A8], rax; __int64
0x140057535  lea     rax, [rbp+var_40]
0x140057539  mov     [rsp+140h+var_B0], rax; __int64
0x140057541  lea     rax, [rbp+var_70+4]
0x140057545  mov     [rsp+140h+var_B8], rax; __int64
0x14005754d  lea     rax, [rbp+var_38]
0x140057551  mov     [rsp+140h+var_C0], rax; __int64
0x140057559  lea     rax, [rbp+var_30]
0x14005755d  mov     [rsp+140h+var_C8], rax; __int64
0x140057562  lea     rax, [rbp+var_68]
0x140057566  mov     [rsp+140h+var_D0], rax; __int64
0x14005756b  lea     rax, [rbp+var_28]
0x14005756f  mov     [rsp+140h+var_D8], rax; __int64
0x140057574  lea     rax, [rbp+var_68+4]
0x140057578  mov     [rsp+140h+var_E0], rax; __int64
0x14005757d  lea     rax, [rbp+var_20]
0x140057581  mov     [rsp+140h+var_E8], rax; __int64
0x140057586  lea     rax, [rbp+var_60]
0x14005758a  mov     [rsp+140h+var_F0], rax; __int64
0x14005758f  lea     rax, [rbp+var_18]
0x140057593  mov     [rsp+140h+var_F8], rax; __int64
0x140057598  lea     rax, [rbp+var_78]
0x14005759c  mov     [rsp+140h+var_100], rax; __int64
0x1400575a1  lea     rax, [rbp+var_10]
0x1400575a5  mov     [rsp+140h+var_108], rax; __int64
0x1400575aa  lea     rax, [rbp+SRWLock]
0x1400575ae  mov     [rsp+140h+var_110], rax; __int64
0x1400575b3  lea     rax, [rbp+var_8]
0x1400575b7  mov     [rsp+140h+var_118], rax; __int64
0x1400575bc  lea     rax, [rbp+var_58]
0x1400575c0  mov     [rsp+140h+var_120], rax; __int64
0x1400575c5  lea     rdx, byte_140134A71; int
0x1400575cc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400575d1  jmp     loc_14005767B
0x1400575d6  mov     [rbp+SRWLock], 0
0x1400575de  lea     rdx, [rbp+SRWLock]
0x1400575e2  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400575e7  mov     rax, [rbx+110h]
0x1400575ee  mov     dword ptr [rax], 2
0x1400575f4  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400575f8  test    rcx, rcx
0x1400575fb  jz      short loc_140057603
0x1400575fd  call    cs:__imp_ReleaseSRWLockExclusive
0x140057603  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x140057608  mov     rdi, [rax+8]
0x14005760c  mov     eax, [rdi]
0x14005760e  cmp     eax, 5
0x140057611  jbe     short loc_14005767B
0x140057613  mov     rcx, [rdi+18h]
0x140057617  mov     rax, [rdi+10h]
0x14005761b  test    al, 2
0x14005761d  jz      short loc_14005767B
0x14005761f  mov     rax, rcx
0x140057622  and     eax, 2
0x140057625  cmp     rax, rcx
0x140057628  jnz     short loc_14005767B
0x14005762a  call    cs:__imp_GetCurrentThreadId
0x140057630  mov     dword ptr [rbp+SRWLock], eax
0x140057633  mov     r8, [rbx+110h]
0x14005763a  mov     eax, [r8+48h]
0x14005763e  mov     dword ptr [rbp+var_78], eax
0x140057641  mov     [rbp+var_58], 0
0x140057649  add     r8, 8
0x14005764d  lea     rax, [rbp+SRWLock]
0x140057651  mov     [rsp+140h+var_110], rax
0x140057656  lea     rax, [rbp+var_78]
0x14005765a  mov     [rsp+140h+var_118], rax
0x14005765f  lea     rax, [rbp+var_58]
0x140057663  mov     [rsp+140h+var_120], rax
0x140057668  xor     r9d, r9d
0x14005766b  lea     rdx, word_140134A22
0x140057672  mov     rcx, rdi
0x140057675  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005767a  nop
0x14005767b  lea     rcx, [rbx+120h]; this
0x140057682  cmp     dword ptr [rcx+18h], 0
0x140057686  jz      short loc_14005768E
0x140057688  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14005768d  nop
0x14005768e  lea     r11, [rsp+140h+var_s0]
0x140057696  mov     rbx, [r11+18h]
0x14005769a  mov     rdi, [r11+20h]
0x14005769e  mov     rsp, r11
0x1400576a1  pop     rbp
0x1400576a2  retn
```
