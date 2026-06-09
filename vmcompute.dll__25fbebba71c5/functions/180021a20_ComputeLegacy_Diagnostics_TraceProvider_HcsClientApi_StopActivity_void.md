# ComputeLegacy::Diagnostics::TraceProvider::HcsClientApi::StopActivity(void)

- ea: `0x180021a20`
- end: `0x180021d16`
- name: `?StopActivity@HcsClientApi@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `758`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::HcsClientApi *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021a20`
- `0x180021d1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021a87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021c5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021a87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021c5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021c96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021c96`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::HcsClientApi::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::HcsClientApi *this)
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
      && (*(_QWORD *)(v5 + 16) & 0x20000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x20000LL) == *(_QWORD *)(v5 + 24) )
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
        (int)&byte_18009D125,
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
      && (*(_QWORD *)(v6 + 16) & 0x20000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x20000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)byte_18009D7FB,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::HcsClientApi *)((char *)this + 288));
}

```

## disassembly

```asm
0x180021a20  mov     [rsp-8+arg_8], rbx
0x180021a25  mov     [rsp-8+arg_10], rdi
0x180021a2a  push    rbp
0x180021a2b  mov     rbp, rsp
0x180021a2e  sub     rsp, 140h
0x180021a35  mov     rbx, rcx
0x180021a38  mov     rdi, [rcx+110h]
0x180021a3f  mov     eax, [rdi+48h]
0x180021a42  test    eax, eax
0x180021a44  jns     loc_180021C36
0x180021a4a  add     rdi, 50h ; 'P'
0x180021a4e  cmp     eax, [rdi+8]
0x180021a51  jnz     loc_180021C36
0x180021a57  test    rdi, rdi
0x180021a5a  jz      loc_180021C36
0x180021a60  mov     [rbp+SRWLock], 0
0x180021a68  lea     rdx, [rbp+SRWLock]
0x180021a6c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180021a71  mov     rax, [rbx+110h]
0x180021a78  mov     dword ptr [rax], 2
0x180021a7e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180021a82  test    rcx, rcx
0x180021a85  jz      short loc_180021A93
0x180021a87  call    cs:__imp_ReleaseSRWLockExclusive
0x180021a8e  nop     dword ptr [rax+rax+00h]
0x180021a93  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180021a98  mov     r9, [rax+8]
0x180021a9c  mov     eax, [r9]
0x180021a9f  cmp     eax, 4
0x180021aa2  jbe     loc_180021CED
0x180021aa8  mov     rdx, [r9+18h]
0x180021aac  mov     rax, [r9+10h]
0x180021ab0  mov     ecx, 20000h
0x180021ab5  test    rcx, rax
0x180021ab8  jz      loc_180021CED
0x180021abe  mov     rax, rdx
0x180021ac1  and     rax, rcx
0x180021ac4  cmp     rax, rdx
0x180021ac7  jnz     loc_180021CED
0x180021acd  mov     rax, [rdi+30h]
0x180021ad1  mov     [rbp+var_50], rax
0x180021ad5  mov     eax, [rdi+44h]
0x180021ad8  mov     dword ptr [rbp+var_78+4], eax
0x180021adb  mov     eax, [rdi+10h]
0x180021ade  mov     dword ptr [rbp+var_70], eax
0x180021ae1  mov     rax, [rdi+78h]
0x180021ae5  mov     [rbp+var_48], rax
0x180021ae9  mov     rax, [rdi+70h]
0x180021aed  mov     [rbp+var_40], rax
0x180021af1  mov     eax, [rdi+68h]
0x180021af4  mov     dword ptr [rbp+var_70+4], eax
0x180021af7  mov     rax, [rdi+60h]
0x180021afb  mov     [rbp+var_38], rax
0x180021aff  mov     rax, [rdi+58h]
0x180021b03  mov     [rbp+var_30], rax
0x180021b07  mov     eax, [rdi+50h]
0x180021b0a  mov     dword ptr [rbp+var_68], eax
0x180021b0d  mov     rax, [rdi+48h]
0x180021b11  mov     [rbp+var_28], rax
0x180021b15  mov     eax, [rdi+20h]
0x180021b18  mov     dword ptr [rbp+var_68+4], eax
0x180021b1b  mov     rax, [rdi+18h]
0x180021b1f  mov     [rbp+var_20], rax
0x180021b23  mov     eax, [rdi]
0x180021b25  mov     [rbp+var_60], eax
0x180021b28  mov     rax, [rdi+80h]
0x180021b2f  mov     [rbp+var_18], rax
0x180021b33  mov     eax, [rdi+40h]
0x180021b36  mov     dword ptr [rbp+var_78], eax
0x180021b39  mov     rax, [rdi+38h]
0x180021b3d  mov     [rbp+var_10], rax
0x180021b41  mov     eax, [rdi+8]
0x180021b44  mov     dword ptr [rbp+SRWLock], eax
0x180021b47  mov     [rbp+var_8], 1000000h
0x180021b4f  mov     [rbp+var_58], 0
0x180021b57  mov     r8, [rbx+110h]
0x180021b5e  add     r8, 8; int
0x180021b62  lea     rax, [rbp+var_50]
0x180021b66  mov     [rsp+140h+var_90], rax; __int64
0x180021b6e  lea     rax, [rbp+var_78+4]
0x180021b72  mov     [rsp+140h+var_98], rax; __int64
0x180021b7a  lea     rax, [rbp+var_70]
0x180021b7e  mov     [rsp+140h+var_A0], rax; __int64
0x180021b86  lea     rax, [rbp+var_48]
0x180021b8a  mov     [rsp+140h+var_A8], rax; __int64
0x180021b92  lea     rax, [rbp+var_40]
0x180021b96  mov     [rsp+140h+var_B0], rax; __int64
0x180021b9e  lea     rax, [rbp+var_70+4]
0x180021ba2  mov     [rsp+140h+var_B8], rax; __int64
0x180021baa  lea     rax, [rbp+var_38]
0x180021bae  mov     [rsp+140h+var_C0], rax; __int64
0x180021bb6  lea     rax, [rbp+var_30]
0x180021bba  mov     [rsp+140h+var_C8], rax; __int64
0x180021bbf  lea     rax, [rbp+var_68]
0x180021bc3  mov     [rsp+140h+var_D0], rax; __int64
0x180021bc8  lea     rax, [rbp+var_28]
0x180021bcc  mov     [rsp+140h+var_D8], rax; __int64
0x180021bd1  lea     rax, [rbp+var_68+4]
0x180021bd5  mov     [rsp+140h+var_E0], rax; __int64
0x180021bda  lea     rax, [rbp+var_20]
0x180021bde  mov     [rsp+140h+var_E8], rax; __int64
0x180021be3  lea     rax, [rbp+var_60]
0x180021be7  mov     [rsp+140h+var_F0], rax; __int64
0x180021bec  lea     rax, [rbp+var_18]
0x180021bf0  mov     [rsp+140h+var_F8], rax; __int64
0x180021bf5  lea     rax, [rbp+var_78]
0x180021bf9  mov     [rsp+140h+var_100], rax; __int64
0x180021bfe  lea     rax, [rbp+var_10]
0x180021c02  mov     [rsp+140h+var_108], rax; __int64
0x180021c07  lea     rax, [rbp+SRWLock]
0x180021c0b  mov     [rsp+140h+var_110], rax; __int64
0x180021c10  lea     rax, [rbp+var_8]
0x180021c14  mov     [rsp+140h+var_118], rax; __int64
0x180021c19  lea     rax, [rbp+var_58]
0x180021c1d  mov     [rsp+140h+var_120], rax; __int64
0x180021c22  lea     rdx, byte_18009D125; int
0x180021c29  mov     rcx, r9; int
0x180021c2c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180021c31  jmp     loc_180021CED
0x180021c36  mov     [rbp+SRWLock], 0
0x180021c3e  lea     rdx, [rbp+SRWLock]
0x180021c42  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180021c47  mov     rax, [rbx+110h]
0x180021c4e  mov     dword ptr [rax], 2
0x180021c54  mov     rcx, [rbp+SRWLock]; SRWLock
0x180021c58  test    rcx, rcx
0x180021c5b  jz      short loc_180021C69
0x180021c5d  call    cs:__imp_ReleaseSRWLockExclusive
0x180021c64  nop     dword ptr [rax+rax+00h]
0x180021c69  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180021c6e  mov     rdi, [rax+8]
0x180021c72  mov     eax, [rdi]
0x180021c74  cmp     eax, 4
0x180021c77  jbe     short loc_180021CED
0x180021c79  mov     rdx, [rdi+18h]
0x180021c7d  mov     rax, [rdi+10h]
0x180021c81  mov     ecx, 20000h
0x180021c86  test    rcx, rax
0x180021c89  jz      short loc_180021CED
0x180021c8b  mov     rax, rdx
0x180021c8e  and     rax, rcx
0x180021c91  cmp     rax, rdx
0x180021c94  jnz     short loc_180021CED
0x180021c96  call    cs:__imp_GetCurrentThreadId
0x180021c9d  nop     dword ptr [rax+rax+00h]
0x180021ca2  mov     dword ptr [rbp+SRWLock], eax
0x180021ca5  mov     r8, [rbx+110h]
0x180021cac  mov     eax, [r8+48h]
0x180021cb0  mov     dword ptr [rbp+var_78], eax
0x180021cb3  mov     [rbp+var_58], 0
0x180021cbb  add     r8, 8
0x180021cbf  lea     rax, [rbp+SRWLock]
0x180021cc3  mov     [rsp+140h+var_110], rax
0x180021cc8  lea     rax, [rbp+var_78]
0x180021ccc  mov     [rsp+140h+var_118], rax
0x180021cd1  lea     rax, [rbp+var_58]
0x180021cd5  mov     [rsp+140h+var_120], rax
0x180021cda  xor     r9d, r9d
0x180021cdd  lea     rdx, byte_18009D7FB
0x180021ce4  mov     rcx, rdi
0x180021ce7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180021cec  nop
0x180021ced  lea     rcx, [rbx+120h]; this
0x180021cf4  cmp     dword ptr [rcx+18h], 0
0x180021cf8  jz      short loc_180021D00
0x180021cfa  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180021cff  nop
0x180021d00  lea     r11, [rsp+140h+var_s0]
0x180021d08  mov     rbx, [r11+18h]
0x180021d0c  mov     rdi, [r11+20h]
0x180021d10  mov     rsp, r11
0x180021d13  pop     rbp
0x180021d14  retn
```
