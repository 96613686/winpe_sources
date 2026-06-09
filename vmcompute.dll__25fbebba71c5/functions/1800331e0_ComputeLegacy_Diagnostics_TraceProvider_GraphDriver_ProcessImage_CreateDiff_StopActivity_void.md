# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateDiff::StopActivity(void)

- ea: `0x1800331e0`
- end: `0x1800334c6`
- name: `?StopActivity@GraphDriver_ProcessImage_CreateDiff@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateDiff *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x1800331e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033247`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033413`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033247`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033446`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateDiff::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateDiff *this)
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
        (int)&word_18009E916,
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
        (unsigned int)byte_18009F92B,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_CreateDiff *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800331e0  mov     [rsp-8+arg_8], rbx
0x1800331e5  mov     [rsp-8+arg_10], rdi
0x1800331ea  push    rbp
0x1800331eb  mov     rbp, rsp
0x1800331ee  sub     rsp, 140h
0x1800331f5  mov     rbx, rcx
0x1800331f8  mov     rdi, [rcx+110h]
0x1800331ff  mov     eax, [rdi+48h]
0x180033202  test    eax, eax
0x180033204  jns     loc_1800333EC
0x18003320a  add     rdi, 50h ; 'P'
0x18003320e  cmp     eax, [rdi+8]
0x180033211  jnz     loc_1800333EC
0x180033217  test    rdi, rdi
0x18003321a  jz      loc_1800333EC
0x180033220  mov     [rbp+SRWLock], 0
0x180033228  lea     rdx, [rbp+SRWLock]
0x18003322c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180033231  mov     rax, [rbx+110h]
0x180033238  mov     dword ptr [rax], 2
0x18003323e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180033242  test    rcx, rcx
0x180033245  jz      short loc_180033253
0x180033247  call    cs:__imp_ReleaseSRWLockExclusive
0x18003324e  nop     dword ptr [rax+rax+00h]
0x180033253  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033258  mov     rcx, [rax+8]; int
0x18003325c  mov     eax, [rcx]
0x18003325e  cmp     eax, 4
0x180033261  jbe     loc_18003349D
0x180033267  mov     rdx, [rcx+18h]
0x18003326b  mov     rax, [rcx+10h]
0x18003326f  test    al, 40h
0x180033271  jz      loc_18003349D
0x180033277  mov     rax, rdx
0x18003327a  and     eax, 40h
0x18003327d  cmp     rax, rdx
0x180033280  jnz     loc_18003349D
0x180033286  mov     rax, [rdi+30h]
0x18003328a  mov     [rbp+var_50], rax
0x18003328e  mov     eax, [rdi+44h]
0x180033291  mov     dword ptr [rbp+var_78+4], eax
0x180033294  mov     eax, [rdi+10h]
0x180033297  mov     dword ptr [rbp+var_70], eax
0x18003329a  mov     rax, [rdi+78h]
0x18003329e  mov     [rbp+var_48], rax
0x1800332a2  mov     rax, [rdi+70h]
0x1800332a6  mov     [rbp+var_40], rax
0x1800332aa  mov     eax, [rdi+68h]
0x1800332ad  mov     dword ptr [rbp+var_70+4], eax
0x1800332b0  mov     rax, [rdi+60h]
0x1800332b4  mov     [rbp+var_38], rax
0x1800332b8  mov     rax, [rdi+58h]
0x1800332bc  mov     [rbp+var_30], rax
0x1800332c0  mov     eax, [rdi+50h]
0x1800332c3  mov     dword ptr [rbp+var_68], eax
0x1800332c6  mov     rax, [rdi+48h]
0x1800332ca  mov     [rbp+var_28], rax
0x1800332ce  mov     eax, [rdi+20h]
0x1800332d1  mov     dword ptr [rbp+var_68+4], eax
0x1800332d4  mov     rax, [rdi+18h]
0x1800332d8  mov     [rbp+var_20], rax
0x1800332dc  mov     eax, [rdi]
0x1800332de  mov     [rbp+var_60], eax
0x1800332e1  mov     rax, [rdi+80h]
0x1800332e8  mov     [rbp+var_18], rax
0x1800332ec  mov     eax, [rdi+40h]
0x1800332ef  mov     dword ptr [rbp+var_78], eax
0x1800332f2  mov     rax, [rdi+38h]
0x1800332f6  mov     [rbp+var_10], rax
0x1800332fa  mov     eax, [rdi+8]
0x1800332fd  mov     dword ptr [rbp+SRWLock], eax
0x180033300  mov     [rbp+var_8], 1000000h
0x180033308  mov     [rbp+var_58], 0
0x180033310  mov     r8, [rbx+110h]
0x180033317  add     r8, 8; int
0x18003331b  lea     rax, [rbp+var_50]
0x18003331f  mov     [rsp+140h+var_90], rax; __int64
0x180033327  lea     rax, [rbp+var_78+4]
0x18003332b  mov     [rsp+140h+var_98], rax; __int64
0x180033333  lea     rax, [rbp+var_70]
0x180033337  mov     [rsp+140h+var_A0], rax; __int64
0x18003333f  lea     rax, [rbp+var_48]
0x180033343  mov     [rsp+140h+var_A8], rax; __int64
0x18003334b  lea     rax, [rbp+var_40]
0x18003334f  mov     [rsp+140h+var_B0], rax; __int64
0x180033357  lea     rax, [rbp+var_70+4]
0x18003335b  mov     [rsp+140h+var_B8], rax; __int64
0x180033363  lea     rax, [rbp+var_38]
0x180033367  mov     [rsp+140h+var_C0], rax; __int64
0x18003336f  lea     rax, [rbp+var_30]
0x180033373  mov     [rsp+140h+var_C8], rax; __int64
0x180033378  lea     rax, [rbp+var_68]
0x18003337c  mov     [rsp+140h+var_D0], rax; __int64
0x180033381  lea     rax, [rbp+var_28]
0x180033385  mov     [rsp+140h+var_D8], rax; __int64
0x18003338a  lea     rax, [rbp+var_68+4]
0x18003338e  mov     [rsp+140h+var_E0], rax; __int64
0x180033393  lea     rax, [rbp+var_20]
0x180033397  mov     [rsp+140h+var_E8], rax; __int64
0x18003339c  lea     rax, [rbp+var_60]
0x1800333a0  mov     [rsp+140h+var_F0], rax; __int64
0x1800333a5  lea     rax, [rbp+var_18]
0x1800333a9  mov     [rsp+140h+var_F8], rax; __int64
0x1800333ae  lea     rax, [rbp+var_78]
0x1800333b2  mov     [rsp+140h+var_100], rax; __int64
0x1800333b7  lea     rax, [rbp+var_10]
0x1800333bb  mov     [rsp+140h+var_108], rax; __int64
0x1800333c0  lea     rax, [rbp+SRWLock]
0x1800333c4  mov     [rsp+140h+var_110], rax; __int64
0x1800333c9  lea     rax, [rbp+var_8]
0x1800333cd  mov     [rsp+140h+var_118], rax; __int64
0x1800333d2  lea     rax, [rbp+var_58]
0x1800333d6  mov     [rsp+140h+var_120], rax; __int64
0x1800333db  lea     rdx, word_18009E916; int
0x1800333e2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800333e7  jmp     loc_18003349D
0x1800333ec  mov     [rbp+SRWLock], 0
0x1800333f4  lea     rdx, [rbp+SRWLock]
0x1800333f8  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800333fd  mov     rax, [rbx+110h]
0x180033404  mov     dword ptr [rax], 2
0x18003340a  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003340e  test    rcx, rcx
0x180033411  jz      short loc_18003341F
0x180033413  call    cs:__imp_ReleaseSRWLockExclusive
0x18003341a  nop     dword ptr [rax+rax+00h]
0x18003341f  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033424  mov     rdi, [rax+8]
0x180033428  mov     eax, [rdi]
0x18003342a  cmp     eax, 4
0x18003342d  jbe     short loc_18003349D
0x18003342f  mov     rcx, [rdi+18h]
0x180033433  mov     rax, [rdi+10h]
0x180033437  test    al, 40h
0x180033439  jz      short loc_18003349D
0x18003343b  mov     rax, rcx
0x18003343e  and     eax, 40h
0x180033441  cmp     rax, rcx
0x180033444  jnz     short loc_18003349D
0x180033446  call    cs:__imp_GetCurrentThreadId
0x18003344d  nop     dword ptr [rax+rax+00h]
0x180033452  mov     dword ptr [rbp+SRWLock], eax
0x180033455  mov     r8, [rbx+110h]
0x18003345c  mov     eax, [r8+48h]
0x180033460  mov     dword ptr [rbp+var_78], eax
0x180033463  mov     [rbp+var_58], 0
0x18003346b  add     r8, 8
0x18003346f  lea     rax, [rbp+SRWLock]
0x180033473  mov     [rsp+140h+var_110], rax
0x180033478  lea     rax, [rbp+var_78]
0x18003347c  mov     [rsp+140h+var_118], rax
0x180033481  lea     rax, [rbp+var_58]
0x180033485  mov     [rsp+140h+var_120], rax
0x18003348a  xor     r9d, r9d
0x18003348d  lea     rdx, byte_18009F92B
0x180033494  mov     rcx, rdi
0x180033497  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003349c  nop
0x18003349d  lea     rcx, [rbx+120h]; this
0x1800334a4  cmp     dword ptr [rcx+18h], 0
0x1800334a8  jz      short loc_1800334B0
0x1800334aa  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800334af  nop
0x1800334b0  lea     r11, [rsp+140h+var_s0]
0x1800334b8  mov     rbx, [r11+18h]
0x1800334bc  mov     rdi, [r11+20h]
0x1800334c0  mov     rsp, r11
0x1800334c3  pop     rbp
0x1800334c4  retn
```
