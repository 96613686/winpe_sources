# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer::StopActivity(void)

- ea: `0x180033da0`
- end: `0x180034086`
- name: `?StopActivity@GraphDriver_ProcessImage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x180033da0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033e07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033fd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033e07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033fd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034006`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer *this)
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
        (int)&word_18009F76A,
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
        (unsigned int)byte_18009DC2D,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_ProcessOsLayer *)((char *)this + 288));
}

```

## disassembly

```asm
0x180033da0  mov     [rsp-8+arg_8], rbx
0x180033da5  mov     [rsp-8+arg_10], rdi
0x180033daa  push    rbp
0x180033dab  mov     rbp, rsp
0x180033dae  sub     rsp, 140h
0x180033db5  mov     rbx, rcx
0x180033db8  mov     rdi, [rcx+110h]
0x180033dbf  mov     eax, [rdi+48h]
0x180033dc2  test    eax, eax
0x180033dc4  jns     loc_180033FAC
0x180033dca  add     rdi, 50h ; 'P'
0x180033dce  cmp     eax, [rdi+8]
0x180033dd1  jnz     loc_180033FAC
0x180033dd7  test    rdi, rdi
0x180033dda  jz      loc_180033FAC
0x180033de0  mov     [rbp+SRWLock], 0
0x180033de8  lea     rdx, [rbp+SRWLock]
0x180033dec  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180033df1  mov     rax, [rbx+110h]
0x180033df8  mov     dword ptr [rax], 2
0x180033dfe  mov     rcx, [rbp+SRWLock]; SRWLock
0x180033e02  test    rcx, rcx
0x180033e05  jz      short loc_180033E13
0x180033e07  call    cs:__imp_ReleaseSRWLockExclusive
0x180033e0e  nop     dword ptr [rax+rax+00h]
0x180033e13  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033e18  mov     rcx, [rax+8]; int
0x180033e1c  mov     eax, [rcx]
0x180033e1e  cmp     eax, 4
0x180033e21  jbe     loc_18003405D
0x180033e27  mov     rdx, [rcx+18h]
0x180033e2b  mov     rax, [rcx+10h]
0x180033e2f  test    al, 40h
0x180033e31  jz      loc_18003405D
0x180033e37  mov     rax, rdx
0x180033e3a  and     eax, 40h
0x180033e3d  cmp     rax, rdx
0x180033e40  jnz     loc_18003405D
0x180033e46  mov     rax, [rdi+30h]
0x180033e4a  mov     [rbp+var_50], rax
0x180033e4e  mov     eax, [rdi+44h]
0x180033e51  mov     dword ptr [rbp+var_78+4], eax
0x180033e54  mov     eax, [rdi+10h]
0x180033e57  mov     dword ptr [rbp+var_70], eax
0x180033e5a  mov     rax, [rdi+78h]
0x180033e5e  mov     [rbp+var_48], rax
0x180033e62  mov     rax, [rdi+70h]
0x180033e66  mov     [rbp+var_40], rax
0x180033e6a  mov     eax, [rdi+68h]
0x180033e6d  mov     dword ptr [rbp+var_70+4], eax
0x180033e70  mov     rax, [rdi+60h]
0x180033e74  mov     [rbp+var_38], rax
0x180033e78  mov     rax, [rdi+58h]
0x180033e7c  mov     [rbp+var_30], rax
0x180033e80  mov     eax, [rdi+50h]
0x180033e83  mov     dword ptr [rbp+var_68], eax
0x180033e86  mov     rax, [rdi+48h]
0x180033e8a  mov     [rbp+var_28], rax
0x180033e8e  mov     eax, [rdi+20h]
0x180033e91  mov     dword ptr [rbp+var_68+4], eax
0x180033e94  mov     rax, [rdi+18h]
0x180033e98  mov     [rbp+var_20], rax
0x180033e9c  mov     eax, [rdi]
0x180033e9e  mov     [rbp+var_60], eax
0x180033ea1  mov     rax, [rdi+80h]
0x180033ea8  mov     [rbp+var_18], rax
0x180033eac  mov     eax, [rdi+40h]
0x180033eaf  mov     dword ptr [rbp+var_78], eax
0x180033eb2  mov     rax, [rdi+38h]
0x180033eb6  mov     [rbp+var_10], rax
0x180033eba  mov     eax, [rdi+8]
0x180033ebd  mov     dword ptr [rbp+SRWLock], eax
0x180033ec0  mov     [rbp+var_8], 1000000h
0x180033ec8  mov     [rbp+var_58], 0
0x180033ed0  mov     r8, [rbx+110h]
0x180033ed7  add     r8, 8; int
0x180033edb  lea     rax, [rbp+var_50]
0x180033edf  mov     [rsp+140h+var_90], rax; __int64
0x180033ee7  lea     rax, [rbp+var_78+4]
0x180033eeb  mov     [rsp+140h+var_98], rax; __int64
0x180033ef3  lea     rax, [rbp+var_70]
0x180033ef7  mov     [rsp+140h+var_A0], rax; __int64
0x180033eff  lea     rax, [rbp+var_48]
0x180033f03  mov     [rsp+140h+var_A8], rax; __int64
0x180033f0b  lea     rax, [rbp+var_40]
0x180033f0f  mov     [rsp+140h+var_B0], rax; __int64
0x180033f17  lea     rax, [rbp+var_70+4]
0x180033f1b  mov     [rsp+140h+var_B8], rax; __int64
0x180033f23  lea     rax, [rbp+var_38]
0x180033f27  mov     [rsp+140h+var_C0], rax; __int64
0x180033f2f  lea     rax, [rbp+var_30]
0x180033f33  mov     [rsp+140h+var_C8], rax; __int64
0x180033f38  lea     rax, [rbp+var_68]
0x180033f3c  mov     [rsp+140h+var_D0], rax; __int64
0x180033f41  lea     rax, [rbp+var_28]
0x180033f45  mov     [rsp+140h+var_D8], rax; __int64
0x180033f4a  lea     rax, [rbp+var_68+4]
0x180033f4e  mov     [rsp+140h+var_E0], rax; __int64
0x180033f53  lea     rax, [rbp+var_20]
0x180033f57  mov     [rsp+140h+var_E8], rax; __int64
0x180033f5c  lea     rax, [rbp+var_60]
0x180033f60  mov     [rsp+140h+var_F0], rax; __int64
0x180033f65  lea     rax, [rbp+var_18]
0x180033f69  mov     [rsp+140h+var_F8], rax; __int64
0x180033f6e  lea     rax, [rbp+var_78]
0x180033f72  mov     [rsp+140h+var_100], rax; __int64
0x180033f77  lea     rax, [rbp+var_10]
0x180033f7b  mov     [rsp+140h+var_108], rax; __int64
0x180033f80  lea     rax, [rbp+SRWLock]
0x180033f84  mov     [rsp+140h+var_110], rax; __int64
0x180033f89  lea     rax, [rbp+var_8]
0x180033f8d  mov     [rsp+140h+var_118], rax; __int64
0x180033f92  lea     rax, [rbp+var_58]
0x180033f96  mov     [rsp+140h+var_120], rax; __int64
0x180033f9b  lea     rdx, word_18009F76A; int
0x180033fa2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180033fa7  jmp     loc_18003405D
0x180033fac  mov     [rbp+SRWLock], 0
0x180033fb4  lea     rdx, [rbp+SRWLock]
0x180033fb8  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180033fbd  mov     rax, [rbx+110h]
0x180033fc4  mov     dword ptr [rax], 2
0x180033fca  mov     rcx, [rbp+SRWLock]; SRWLock
0x180033fce  test    rcx, rcx
0x180033fd1  jz      short loc_180033FDF
0x180033fd3  call    cs:__imp_ReleaseSRWLockExclusive
0x180033fda  nop     dword ptr [rax+rax+00h]
0x180033fdf  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033fe4  mov     rdi, [rax+8]
0x180033fe8  mov     eax, [rdi]
0x180033fea  cmp     eax, 4
0x180033fed  jbe     short loc_18003405D
0x180033fef  mov     rcx, [rdi+18h]
0x180033ff3  mov     rax, [rdi+10h]
0x180033ff7  test    al, 40h
0x180033ff9  jz      short loc_18003405D
0x180033ffb  mov     rax, rcx
0x180033ffe  and     eax, 40h
0x180034001  cmp     rax, rcx
0x180034004  jnz     short loc_18003405D
0x180034006  call    cs:__imp_GetCurrentThreadId
0x18003400d  nop     dword ptr [rax+rax+00h]
0x180034012  mov     dword ptr [rbp+SRWLock], eax
0x180034015  mov     r8, [rbx+110h]
0x18003401c  mov     eax, [r8+48h]
0x180034020  mov     dword ptr [rbp+var_78], eax
0x180034023  mov     [rbp+var_58], 0
0x18003402b  add     r8, 8
0x18003402f  lea     rax, [rbp+SRWLock]
0x180034033  mov     [rsp+140h+var_110], rax
0x180034038  lea     rax, [rbp+var_78]
0x18003403c  mov     [rsp+140h+var_118], rax
0x180034041  lea     rax, [rbp+var_58]
0x180034045  mov     [rsp+140h+var_120], rax
0x18003404a  xor     r9d, r9d
0x18003404d  lea     rdx, byte_18009DC2D
0x180034054  mov     rcx, rdi
0x180034057  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003405c  nop
0x18003405d  lea     rcx, [rbx+120h]; this
0x180034064  cmp     dword ptr [rcx+18h], 0
0x180034068  jz      short loc_180034070
0x18003406a  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003406f  nop
0x180034070  lea     r11, [rsp+140h+var_s0]
0x180034078  mov     rbx, [r11+18h]
0x18003407c  mov     rdi, [r11+20h]
0x180034080  mov     rsp, r11
0x180034083  pop     rbp
0x180034084  retn
```
