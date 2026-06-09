# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd::StopActivity(void)

- ea: `0x180033ab0`
- end: `0x180033d96`
- name: `?StopActivity@GraphDriver_ProcessImage_MountVhd@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x180033ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033b17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033ce3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033b17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033ce3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033d16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033d16`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd *this)
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
        (int)&unk_18009E418,
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
        (unsigned int)&byte_18009E107,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_ProcessImage_MountVhd *)((char *)this + 288));
}

```

## disassembly

```asm
0x180033ab0  mov     [rsp-8+arg_8], rbx
0x180033ab5  mov     [rsp-8+arg_10], rdi
0x180033aba  push    rbp
0x180033abb  mov     rbp, rsp
0x180033abe  sub     rsp, 140h
0x180033ac5  mov     rbx, rcx
0x180033ac8  mov     rdi, [rcx+110h]
0x180033acf  mov     eax, [rdi+48h]
0x180033ad2  test    eax, eax
0x180033ad4  jns     loc_180033CBC
0x180033ada  add     rdi, 50h ; 'P'
0x180033ade  cmp     eax, [rdi+8]
0x180033ae1  jnz     loc_180033CBC
0x180033ae7  test    rdi, rdi
0x180033aea  jz      loc_180033CBC
0x180033af0  mov     [rbp+SRWLock], 0
0x180033af8  lea     rdx, [rbp+SRWLock]
0x180033afc  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180033b01  mov     rax, [rbx+110h]
0x180033b08  mov     dword ptr [rax], 2
0x180033b0e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180033b12  test    rcx, rcx
0x180033b15  jz      short loc_180033B23
0x180033b17  call    cs:__imp_ReleaseSRWLockExclusive
0x180033b1e  nop     dword ptr [rax+rax+00h]
0x180033b23  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033b28  mov     rcx, [rax+8]; int
0x180033b2c  mov     eax, [rcx]
0x180033b2e  cmp     eax, 4
0x180033b31  jbe     loc_180033D6D
0x180033b37  mov     rdx, [rcx+18h]
0x180033b3b  mov     rax, [rcx+10h]
0x180033b3f  test    al, 40h
0x180033b41  jz      loc_180033D6D
0x180033b47  mov     rax, rdx
0x180033b4a  and     eax, 40h
0x180033b4d  cmp     rax, rdx
0x180033b50  jnz     loc_180033D6D
0x180033b56  mov     rax, [rdi+30h]
0x180033b5a  mov     [rbp+var_50], rax
0x180033b5e  mov     eax, [rdi+44h]
0x180033b61  mov     dword ptr [rbp+var_78+4], eax
0x180033b64  mov     eax, [rdi+10h]
0x180033b67  mov     dword ptr [rbp+var_70], eax
0x180033b6a  mov     rax, [rdi+78h]
0x180033b6e  mov     [rbp+var_48], rax
0x180033b72  mov     rax, [rdi+70h]
0x180033b76  mov     [rbp+var_40], rax
0x180033b7a  mov     eax, [rdi+68h]
0x180033b7d  mov     dword ptr [rbp+var_70+4], eax
0x180033b80  mov     rax, [rdi+60h]
0x180033b84  mov     [rbp+var_38], rax
0x180033b88  mov     rax, [rdi+58h]
0x180033b8c  mov     [rbp+var_30], rax
0x180033b90  mov     eax, [rdi+50h]
0x180033b93  mov     dword ptr [rbp+var_68], eax
0x180033b96  mov     rax, [rdi+48h]
0x180033b9a  mov     [rbp+var_28], rax
0x180033b9e  mov     eax, [rdi+20h]
0x180033ba1  mov     dword ptr [rbp+var_68+4], eax
0x180033ba4  mov     rax, [rdi+18h]
0x180033ba8  mov     [rbp+var_20], rax
0x180033bac  mov     eax, [rdi]
0x180033bae  mov     [rbp+var_60], eax
0x180033bb1  mov     rax, [rdi+80h]
0x180033bb8  mov     [rbp+var_18], rax
0x180033bbc  mov     eax, [rdi+40h]
0x180033bbf  mov     dword ptr [rbp+var_78], eax
0x180033bc2  mov     rax, [rdi+38h]
0x180033bc6  mov     [rbp+var_10], rax
0x180033bca  mov     eax, [rdi+8]
0x180033bcd  mov     dword ptr [rbp+SRWLock], eax
0x180033bd0  mov     [rbp+var_8], 1000000h
0x180033bd8  mov     [rbp+var_58], 0
0x180033be0  mov     r8, [rbx+110h]
0x180033be7  add     r8, 8; int
0x180033beb  lea     rax, [rbp+var_50]
0x180033bef  mov     [rsp+140h+var_90], rax; __int64
0x180033bf7  lea     rax, [rbp+var_78+4]
0x180033bfb  mov     [rsp+140h+var_98], rax; __int64
0x180033c03  lea     rax, [rbp+var_70]
0x180033c07  mov     [rsp+140h+var_A0], rax; __int64
0x180033c0f  lea     rax, [rbp+var_48]
0x180033c13  mov     [rsp+140h+var_A8], rax; __int64
0x180033c1b  lea     rax, [rbp+var_40]
0x180033c1f  mov     [rsp+140h+var_B0], rax; __int64
0x180033c27  lea     rax, [rbp+var_70+4]
0x180033c2b  mov     [rsp+140h+var_B8], rax; __int64
0x180033c33  lea     rax, [rbp+var_38]
0x180033c37  mov     [rsp+140h+var_C0], rax; __int64
0x180033c3f  lea     rax, [rbp+var_30]
0x180033c43  mov     [rsp+140h+var_C8], rax; __int64
0x180033c48  lea     rax, [rbp+var_68]
0x180033c4c  mov     [rsp+140h+var_D0], rax; __int64
0x180033c51  lea     rax, [rbp+var_28]
0x180033c55  mov     [rsp+140h+var_D8], rax; __int64
0x180033c5a  lea     rax, [rbp+var_68+4]
0x180033c5e  mov     [rsp+140h+var_E0], rax; __int64
0x180033c63  lea     rax, [rbp+var_20]
0x180033c67  mov     [rsp+140h+var_E8], rax; __int64
0x180033c6c  lea     rax, [rbp+var_60]
0x180033c70  mov     [rsp+140h+var_F0], rax; __int64
0x180033c75  lea     rax, [rbp+var_18]
0x180033c79  mov     [rsp+140h+var_F8], rax; __int64
0x180033c7e  lea     rax, [rbp+var_78]
0x180033c82  mov     [rsp+140h+var_100], rax; __int64
0x180033c87  lea     rax, [rbp+var_10]
0x180033c8b  mov     [rsp+140h+var_108], rax; __int64
0x180033c90  lea     rax, [rbp+SRWLock]
0x180033c94  mov     [rsp+140h+var_110], rax; __int64
0x180033c99  lea     rax, [rbp+var_8]
0x180033c9d  mov     [rsp+140h+var_118], rax; __int64
0x180033ca2  lea     rax, [rbp+var_58]
0x180033ca6  mov     [rsp+140h+var_120], rax; __int64
0x180033cab  lea     rdx, unk_18009E418; int
0x180033cb2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180033cb7  jmp     loc_180033D6D
0x180033cbc  mov     [rbp+SRWLock], 0
0x180033cc4  lea     rdx, [rbp+SRWLock]
0x180033cc8  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180033ccd  mov     rax, [rbx+110h]
0x180033cd4  mov     dword ptr [rax], 2
0x180033cda  mov     rcx, [rbp+SRWLock]; SRWLock
0x180033cde  test    rcx, rcx
0x180033ce1  jz      short loc_180033CEF
0x180033ce3  call    cs:__imp_ReleaseSRWLockExclusive
0x180033cea  nop     dword ptr [rax+rax+00h]
0x180033cef  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180033cf4  mov     rdi, [rax+8]
0x180033cf8  mov     eax, [rdi]
0x180033cfa  cmp     eax, 4
0x180033cfd  jbe     short loc_180033D6D
0x180033cff  mov     rcx, [rdi+18h]
0x180033d03  mov     rax, [rdi+10h]
0x180033d07  test    al, 40h
0x180033d09  jz      short loc_180033D6D
0x180033d0b  mov     rax, rcx
0x180033d0e  and     eax, 40h
0x180033d11  cmp     rax, rcx
0x180033d14  jnz     short loc_180033D6D
0x180033d16  call    cs:__imp_GetCurrentThreadId
0x180033d1d  nop     dword ptr [rax+rax+00h]
0x180033d22  mov     dword ptr [rbp+SRWLock], eax
0x180033d25  mov     r8, [rbx+110h]
0x180033d2c  mov     eax, [r8+48h]
0x180033d30  mov     dword ptr [rbp+var_78], eax
0x180033d33  mov     [rbp+var_58], 0
0x180033d3b  add     r8, 8
0x180033d3f  lea     rax, [rbp+SRWLock]
0x180033d43  mov     [rsp+140h+var_110], rax
0x180033d48  lea     rax, [rbp+var_78]
0x180033d4c  mov     [rsp+140h+var_118], rax
0x180033d51  lea     rax, [rbp+var_58]
0x180033d55  mov     [rsp+140h+var_120], rax
0x180033d5a  xor     r9d, r9d
0x180033d5d  lea     rdx, byte_18009E107
0x180033d64  mov     rcx, rdi
0x180033d67  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180033d6c  nop
0x180033d6d  lea     rcx, [rbx+120h]; this
0x180033d74  cmp     dword ptr [rcx+18h], 0
0x180033d78  jz      short loc_180033D80
0x180033d7a  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180033d7f  nop
0x180033d80  lea     r11, [rsp+140h+var_s0]
0x180033d88  mov     rbx, [r11+18h]
0x180033d8c  mov     rdi, [r11+20h]
0x180033d90  mov     rsp, r11
0x180033d93  pop     rbp
0x180033d94  retn
```
