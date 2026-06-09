# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders::StopActivity(void)

- ea: `0x180032330`
- end: `0x180032616`
- name: `?StopActivity@GraphDriver_CreateBaseImageVHDWithFolders@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x180032330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032397`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032563`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032397`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032563`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032596`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032596`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders *this)
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
    wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 4u
      && (*(_QWORD *)(v5 + 16) & 0x40) != 0
      && (*(_QWORD *)(v5 + 24) & 0x40LL) == *(_QWORD *)(v5 + 24) )
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
        (int)&word_18009F19E,
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
      && (*(_QWORD *)(v6 + 16) & 0x40) != 0
      && (*(_QWORD *)(v6 + 24) & 0x40LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&dword_18009E2F4,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders *)((char *)this + 288));
}

```

## disassembly

```asm
0x180032330  mov     [rsp-8+arg_8], rbx
0x180032335  mov     [rsp-8+arg_10], rdi
0x18003233a  push    rbp
0x18003233b  mov     rbp, rsp
0x18003233e  sub     rsp, 140h
0x180032345  mov     rbx, rcx
0x180032348  mov     rdi, [rcx+110h]
0x18003234f  mov     eax, [rdi+48h]
0x180032352  test    eax, eax
0x180032354  jns     loc_18003253C
0x18003235a  add     rdi, 50h ; 'P'
0x18003235e  cmp     eax, [rdi+8]
0x180032361  jnz     loc_18003253C
0x180032367  test    rdi, rdi
0x18003236a  jz      loc_18003253C
0x180032370  mov     [rbp+SRWLock], 0
0x180032378  lea     rdx, [rbp+SRWLock]
0x18003237c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180032381  mov     rax, [rbx+110h]
0x180032388  mov     dword ptr [rax], 2
0x18003238e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180032392  test    rcx, rcx
0x180032395  jz      short loc_1800323A3
0x180032397  call    cs:__imp_ReleaseSRWLockExclusive
0x18003239e  nop     dword ptr [rax+rax+00h]
0x1800323a3  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x1800323a8  mov     rcx, [rax+8]; int
0x1800323ac  mov     eax, [rcx]
0x1800323ae  cmp     eax, 4
0x1800323b1  jbe     loc_1800325ED
0x1800323b7  mov     rdx, [rcx+18h]
0x1800323bb  mov     rax, [rcx+10h]
0x1800323bf  test    al, 40h
0x1800323c1  jz      loc_1800325ED
0x1800323c7  mov     rax, rdx
0x1800323ca  and     eax, 40h
0x1800323cd  cmp     rax, rdx
0x1800323d0  jnz     loc_1800325ED
0x1800323d6  mov     rax, [rdi+30h]
0x1800323da  mov     [rbp+var_50], rax
0x1800323de  mov     eax, [rdi+44h]
0x1800323e1  mov     dword ptr [rbp+var_78+4], eax
0x1800323e4  mov     eax, [rdi+10h]
0x1800323e7  mov     dword ptr [rbp+var_70], eax
0x1800323ea  mov     rax, [rdi+78h]
0x1800323ee  mov     [rbp+var_48], rax
0x1800323f2  mov     rax, [rdi+70h]
0x1800323f6  mov     [rbp+var_40], rax
0x1800323fa  mov     eax, [rdi+68h]
0x1800323fd  mov     dword ptr [rbp+var_70+4], eax
0x180032400  mov     rax, [rdi+60h]
0x180032404  mov     [rbp+var_38], rax
0x180032408  mov     rax, [rdi+58h]
0x18003240c  mov     [rbp+var_30], rax
0x180032410  mov     eax, [rdi+50h]
0x180032413  mov     dword ptr [rbp+var_68], eax
0x180032416  mov     rax, [rdi+48h]
0x18003241a  mov     [rbp+var_28], rax
0x18003241e  mov     eax, [rdi+20h]
0x180032421  mov     dword ptr [rbp+var_68+4], eax
0x180032424  mov     rax, [rdi+18h]
0x180032428  mov     [rbp+var_20], rax
0x18003242c  mov     eax, [rdi]
0x18003242e  mov     [rbp+var_60], eax
0x180032431  mov     rax, [rdi+80h]
0x180032438  mov     [rbp+var_18], rax
0x18003243c  mov     eax, [rdi+40h]
0x18003243f  mov     dword ptr [rbp+var_78], eax
0x180032442  mov     rax, [rdi+38h]
0x180032446  mov     [rbp+var_10], rax
0x18003244a  mov     eax, [rdi+8]
0x18003244d  mov     dword ptr [rbp+SRWLock], eax
0x180032450  mov     [rbp+var_8], 1000000h
0x180032458  mov     [rbp+var_58], 0
0x180032460  mov     r8, [rbx+110h]
0x180032467  add     r8, 8; int
0x18003246b  lea     rax, [rbp+var_50]
0x18003246f  mov     [rsp+140h+var_90], rax; __int64
0x180032477  lea     rax, [rbp+var_78+4]
0x18003247b  mov     [rsp+140h+var_98], rax; __int64
0x180032483  lea     rax, [rbp+var_70]
0x180032487  mov     [rsp+140h+var_A0], rax; __int64
0x18003248f  lea     rax, [rbp+var_48]
0x180032493  mov     [rsp+140h+var_A8], rax; __int64
0x18003249b  lea     rax, [rbp+var_40]
0x18003249f  mov     [rsp+140h+var_B0], rax; __int64
0x1800324a7  lea     rax, [rbp+var_70+4]
0x1800324ab  mov     [rsp+140h+var_B8], rax; __int64
0x1800324b3  lea     rax, [rbp+var_38]
0x1800324b7  mov     [rsp+140h+var_C0], rax; __int64
0x1800324bf  lea     rax, [rbp+var_30]
0x1800324c3  mov     [rsp+140h+var_C8], rax; __int64
0x1800324c8  lea     rax, [rbp+var_68]
0x1800324cc  mov     [rsp+140h+var_D0], rax; __int64
0x1800324d1  lea     rax, [rbp+var_28]
0x1800324d5  mov     [rsp+140h+var_D8], rax; __int64
0x1800324da  lea     rax, [rbp+var_68+4]
0x1800324de  mov     [rsp+140h+var_E0], rax; __int64
0x1800324e3  lea     rax, [rbp+var_20]
0x1800324e7  mov     [rsp+140h+var_E8], rax; __int64
0x1800324ec  lea     rax, [rbp+var_60]
0x1800324f0  mov     [rsp+140h+var_F0], rax; __int64
0x1800324f5  lea     rax, [rbp+var_18]
0x1800324f9  mov     [rsp+140h+var_F8], rax; __int64
0x1800324fe  lea     rax, [rbp+var_78]
0x180032502  mov     [rsp+140h+var_100], rax; __int64
0x180032507  lea     rax, [rbp+var_10]
0x18003250b  mov     [rsp+140h+var_108], rax; __int64
0x180032510  lea     rax, [rbp+SRWLock]
0x180032514  mov     [rsp+140h+var_110], rax; __int64
0x180032519  lea     rax, [rbp+var_8]
0x18003251d  mov     [rsp+140h+var_118], rax; __int64
0x180032522  lea     rax, [rbp+var_58]
0x180032526  mov     [rsp+140h+var_120], rax; __int64
0x18003252b  lea     rdx, word_18009F19E; int
0x180032532  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180032537  jmp     loc_1800325ED
0x18003253c  mov     [rbp+SRWLock], 0
0x180032544  lea     rdx, [rbp+SRWLock]
0x180032548  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003254d  mov     rax, [rbx+110h]
0x180032554  mov     dword ptr [rax], 2
0x18003255a  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003255e  test    rcx, rcx
0x180032561  jz      short loc_18003256F
0x180032563  call    cs:__imp_ReleaseSRWLockExclusive
0x18003256a  nop     dword ptr [rax+rax+00h]
0x18003256f  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180032574  mov     rdi, [rax+8]
0x180032578  mov     eax, [rdi]
0x18003257a  cmp     eax, 4
0x18003257d  jbe     short loc_1800325ED
0x18003257f  mov     rcx, [rdi+18h]
0x180032583  mov     rax, [rdi+10h]
0x180032587  test    al, 40h
0x180032589  jz      short loc_1800325ED
0x18003258b  mov     rax, rcx
0x18003258e  and     eax, 40h
0x180032591  cmp     rax, rcx
0x180032594  jnz     short loc_1800325ED
0x180032596  call    cs:__imp_GetCurrentThreadId
0x18003259d  nop     dword ptr [rax+rax+00h]
0x1800325a2  mov     dword ptr [rbp+SRWLock], eax
0x1800325a5  mov     r8, [rbx+110h]
0x1800325ac  mov     eax, [r8+48h]
0x1800325b0  mov     dword ptr [rbp+var_78], eax
0x1800325b3  mov     [rbp+var_58], 0
0x1800325bb  add     r8, 8
0x1800325bf  lea     rax, [rbp+SRWLock]
0x1800325c3  mov     [rsp+140h+var_110], rax
0x1800325c8  lea     rax, [rbp+var_78]
0x1800325cc  mov     [rsp+140h+var_118], rax
0x1800325d1  lea     rax, [rbp+var_58]
0x1800325d5  mov     [rsp+140h+var_120], rax
0x1800325da  xor     r9d, r9d
0x1800325dd  lea     rdx, dword_18009E2F4
0x1800325e4  mov     rcx, rdi
0x1800325e7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800325ec  nop
0x1800325ed  lea     rcx, [rbx+120h]; this
0x1800325f4  cmp     dword ptr [rcx+18h], 0
0x1800325f8  jz      short loc_180032600
0x1800325fa  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800325ff  nop
0x180032600  lea     r11, [rsp+140h+var_s0]
0x180032608  mov     rbx, [r11+18h]
0x18003260c  mov     rdi, [r11+20h]
0x180032610  mov     rsp, r11
0x180032613  pop     rbp
0x180032614  retn
```
