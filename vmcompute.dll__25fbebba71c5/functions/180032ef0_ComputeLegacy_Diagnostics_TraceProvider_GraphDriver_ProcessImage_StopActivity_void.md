# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage::StopActivity(void)

- ea: `0x180032ef0`
- end: `0x1800331d6`
- name: `?StopActivity@GraphDriver_ProcessImage@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x180032ef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032f57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033123`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032f57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033123`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033156`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033156`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *this)
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
        (int)&byte_18009F04B,
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
        (unsigned int)&dword_18009F47C,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage *)((char *)this + 288));
}

```

## disassembly

```asm
0x180032ef0  mov     [rsp-8+arg_8], rbx
0x180032ef5  mov     [rsp-8+arg_10], rdi
0x180032efa  push    rbp
0x180032efb  mov     rbp, rsp
0x180032efe  sub     rsp, 140h
0x180032f05  mov     rbx, rcx
0x180032f08  mov     rdi, [rcx+110h]
0x180032f0f  mov     eax, [rdi+48h]
0x180032f12  test    eax, eax
0x180032f14  jns     loc_1800330FC
0x180032f1a  add     rdi, 50h ; 'P'
0x180032f1e  cmp     eax, [rdi+8]
0x180032f21  jnz     loc_1800330FC
0x180032f27  test    rdi, rdi
0x180032f2a  jz      loc_1800330FC
0x180032f30  mov     [rbp+SRWLock], 0
0x180032f38  lea     rdx, [rbp+SRWLock]
0x180032f3c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180032f41  mov     rax, [rbx+110h]
0x180032f48  mov     dword ptr [rax], 2
0x180032f4e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180032f52  test    rcx, rcx
0x180032f55  jz      short loc_180032F63
0x180032f57  call    cs:__imp_ReleaseSRWLockExclusive
0x180032f5e  nop     dword ptr [rax+rax+00h]
0x180032f63  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180032f68  mov     rcx, [rax+8]; int
0x180032f6c  mov     eax, [rcx]
0x180032f6e  cmp     eax, 4
0x180032f71  jbe     loc_1800331AD
0x180032f77  mov     rdx, [rcx+18h]
0x180032f7b  mov     rax, [rcx+10h]
0x180032f7f  test    al, 40h
0x180032f81  jz      loc_1800331AD
0x180032f87  mov     rax, rdx
0x180032f8a  and     eax, 40h
0x180032f8d  cmp     rax, rdx
0x180032f90  jnz     loc_1800331AD
0x180032f96  mov     rax, [rdi+30h]
0x180032f9a  mov     [rbp+var_50], rax
0x180032f9e  mov     eax, [rdi+44h]
0x180032fa1  mov     dword ptr [rbp+var_78+4], eax
0x180032fa4  mov     eax, [rdi+10h]
0x180032fa7  mov     dword ptr [rbp+var_70], eax
0x180032faa  mov     rax, [rdi+78h]
0x180032fae  mov     [rbp+var_48], rax
0x180032fb2  mov     rax, [rdi+70h]
0x180032fb6  mov     [rbp+var_40], rax
0x180032fba  mov     eax, [rdi+68h]
0x180032fbd  mov     dword ptr [rbp+var_70+4], eax
0x180032fc0  mov     rax, [rdi+60h]
0x180032fc4  mov     [rbp+var_38], rax
0x180032fc8  mov     rax, [rdi+58h]
0x180032fcc  mov     [rbp+var_30], rax
0x180032fd0  mov     eax, [rdi+50h]
0x180032fd3  mov     dword ptr [rbp+var_68], eax
0x180032fd6  mov     rax, [rdi+48h]
0x180032fda  mov     [rbp+var_28], rax
0x180032fde  mov     eax, [rdi+20h]
0x180032fe1  mov     dword ptr [rbp+var_68+4], eax
0x180032fe4  mov     rax, [rdi+18h]
0x180032fe8  mov     [rbp+var_20], rax
0x180032fec  mov     eax, [rdi]
0x180032fee  mov     [rbp+var_60], eax
0x180032ff1  mov     rax, [rdi+80h]
0x180032ff8  mov     [rbp+var_18], rax
0x180032ffc  mov     eax, [rdi+40h]
0x180032fff  mov     dword ptr [rbp+var_78], eax
0x180033002  mov     rax, [rdi+38h]
0x180033006  mov     [rbp+var_10], rax
0x18003300a  mov     eax, [rdi+8]
0x18003300d  mov     dword ptr [rbp+SRWLock], eax
0x180033010  mov     [rbp+var_8], 1000000h
0x180033018  mov     [rbp+var_58], 0
0x180033020  mov     r8, [rbx+110h]
0x180033027  add     r8, 8; int
0x18003302b  lea     rax, [rbp+var_50]
0x18003302f  mov     [rsp+140h+var_90], rax; __int64
0x180033037  lea     rax, [rbp+var_78+4]
0x18003303b  mov     [rsp+140h+var_98], rax; __int64
0x180033043  lea     rax, [rbp+var_70]
0x180033047  mov     [rsp+140h+var_A0], rax; __int64
0x18003304f  lea     rax, [rbp+var_48]
0x180033053  mov     [rsp+140h+var_A8], rax; __int64
0x18003305b  lea     rax, [rbp+var_40]
0x18003305f  mov     [rsp+140h+var_B0], rax; __int64
0x180033067  lea     rax, [rbp+var_70+4]
0x18003306b  mov     [rsp+140h+var_B8], rax; __int64
0x180033073  lea     rax, [rbp+var_38]
0x180033077  mov     [rsp+140h+var_C0], rax; __int64
0x18003307f  lea     rax, [rbp+var_30]
0x180033083  mov     [rsp+140h+var_C8], rax; __int64
0x180033088  lea     rax, [rbp+var_68]
0x18003308c  mov     [rsp+140h+var_D0], rax; __int64
0x180033091  lea     rax, [rbp+var_28]
0x180033095  mov     [rsp+140h+var_D8], rax; __int64
0x18003309a  lea     rax, [rbp+var_68+4]
0x18003309e  mov     [rsp+140h+var_E0], rax; __int64
0x1800330a3  lea     rax, [rbp+var_20]
0x1800330a7  mov     [rsp+140h+var_E8], rax; __int64
0x1800330ac  lea     rax, [rbp+var_60]
0x1800330b0  mov     [rsp+140h+var_F0], rax; __int64
0x1800330b5  lea     rax, [rbp+var_18]
0x1800330b9  mov     [rsp+140h+var_F8], rax; __int64
0x1800330be  lea     rax, [rbp+var_78]
0x1800330c2  mov     [rsp+140h+var_100], rax; __int64
0x1800330c7  lea     rax, [rbp+var_10]
0x1800330cb  mov     [rsp+140h+var_108], rax; __int64
0x1800330d0  lea     rax, [rbp+SRWLock]
0x1800330d4  mov     [rsp+140h+var_110], rax; __int64
0x1800330d9  lea     rax, [rbp+var_8]
0x1800330dd  mov     [rsp+140h+var_118], rax; __int64
0x1800330e2  lea     rax, [rbp+var_58]
0x1800330e6  mov     [rsp+140h+var_120], rax; __int64
0x1800330eb  lea     rdx, byte_18009F04B; int
0x1800330f2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800330f7  jmp     loc_1800331AD
0x1800330fc  mov     [rbp+SRWLock], 0
0x180033104  lea     rdx, [rbp+SRWLock]
0x180033108  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003310d  mov     rax, [rbx+110h]
0x180033114  mov     dword ptr [rax], 2
0x18003311a  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003311e  test    rcx, rcx
0x180033121  jz      short loc_18003312F
0x180033123  call    cs:__imp_ReleaseSRWLockExclusive
0x18003312a  nop     dword ptr [rax+rax+00h]
0x18003312f  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033134  mov     rdi, [rax+8]
0x180033138  mov     eax, [rdi]
0x18003313a  cmp     eax, 4
0x18003313d  jbe     short loc_1800331AD
0x18003313f  mov     rcx, [rdi+18h]
0x180033143  mov     rax, [rdi+10h]
0x180033147  test    al, 40h
0x180033149  jz      short loc_1800331AD
0x18003314b  mov     rax, rcx
0x18003314e  and     eax, 40h
0x180033151  cmp     rax, rcx
0x180033154  jnz     short loc_1800331AD
0x180033156  call    cs:__imp_GetCurrentThreadId
0x18003315d  nop     dword ptr [rax+rax+00h]
0x180033162  mov     dword ptr [rbp+SRWLock], eax
0x180033165  mov     r8, [rbx+110h]
0x18003316c  mov     eax, [r8+48h]
0x180033170  mov     dword ptr [rbp+var_78], eax
0x180033173  mov     [rbp+var_58], 0
0x18003317b  add     r8, 8
0x18003317f  lea     rax, [rbp+SRWLock]
0x180033183  mov     [rsp+140h+var_110], rax
0x180033188  lea     rax, [rbp+var_78]
0x18003318c  mov     [rsp+140h+var_118], rax
0x180033191  lea     rax, [rbp+var_58]
0x180033195  mov     [rsp+140h+var_120], rax
0x18003319a  xor     r9d, r9d
0x18003319d  lea     rdx, dword_18009F47C
0x1800331a4  mov     rcx, rdi
0x1800331a7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800331ac  nop
0x1800331ad  lea     rcx, [rbx+120h]; this
0x1800331b4  cmp     dword ptr [rcx+18h], 0
0x1800331b8  jz      short loc_1800331C0
0x1800331ba  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800331bf  nop
0x1800331c0  lea     r11, [rsp+140h+var_s0]
0x1800331c8  mov     rbx, [r11+18h]
0x1800331cc  mov     rdi, [r11+20h]
0x1800331d0  mov     rsp, r11
0x1800331d3  pop     rbp
0x1800331d4  retn
```
