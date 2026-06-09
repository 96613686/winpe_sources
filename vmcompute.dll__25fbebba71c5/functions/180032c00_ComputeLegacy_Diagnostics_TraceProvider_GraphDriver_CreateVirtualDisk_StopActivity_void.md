# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::StopActivity(void)

- ea: `0x180032c00`
- end: `0x180032ee6`
- name: `?StopActivity@GraphDriver_CreateVirtualDisk@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x180032c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032c67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032e33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032c67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032e33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032e66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032e66`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk *this)
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
        (int)&byte_18009EDEB,
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
        (unsigned int)&word_18009DE26,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateVirtualDisk *)((char *)this + 288));
}

```

## disassembly

```asm
0x180032c00  mov     [rsp-8+arg_8], rbx
0x180032c05  mov     [rsp-8+arg_10], rdi
0x180032c0a  push    rbp
0x180032c0b  mov     rbp, rsp
0x180032c0e  sub     rsp, 140h
0x180032c15  mov     rbx, rcx
0x180032c18  mov     rdi, [rcx+110h]
0x180032c1f  mov     eax, [rdi+48h]
0x180032c22  test    eax, eax
0x180032c24  jns     loc_180032E0C
0x180032c2a  add     rdi, 50h ; 'P'
0x180032c2e  cmp     eax, [rdi+8]
0x180032c31  jnz     loc_180032E0C
0x180032c37  test    rdi, rdi
0x180032c3a  jz      loc_180032E0C
0x180032c40  mov     [rbp+SRWLock], 0
0x180032c48  lea     rdx, [rbp+SRWLock]
0x180032c4c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180032c51  mov     rax, [rbx+110h]
0x180032c58  mov     dword ptr [rax], 2
0x180032c5e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180032c62  test    rcx, rcx
0x180032c65  jz      short loc_180032C73
0x180032c67  call    cs:__imp_ReleaseSRWLockExclusive
0x180032c6e  nop     dword ptr [rax+rax+00h]
0x180032c73  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180032c78  mov     rcx, [rax+8]; int
0x180032c7c  mov     eax, [rcx]
0x180032c7e  cmp     eax, 4
0x180032c81  jbe     loc_180032EBD
0x180032c87  mov     rdx, [rcx+18h]
0x180032c8b  mov     rax, [rcx+10h]
0x180032c8f  test    al, 40h
0x180032c91  jz      loc_180032EBD
0x180032c97  mov     rax, rdx
0x180032c9a  and     eax, 40h
0x180032c9d  cmp     rax, rdx
0x180032ca0  jnz     loc_180032EBD
0x180032ca6  mov     rax, [rdi+30h]
0x180032caa  mov     [rbp+var_50], rax
0x180032cae  mov     eax, [rdi+44h]
0x180032cb1  mov     dword ptr [rbp+var_78+4], eax
0x180032cb4  mov     eax, [rdi+10h]
0x180032cb7  mov     dword ptr [rbp+var_70], eax
0x180032cba  mov     rax, [rdi+78h]
0x180032cbe  mov     [rbp+var_48], rax
0x180032cc2  mov     rax, [rdi+70h]
0x180032cc6  mov     [rbp+var_40], rax
0x180032cca  mov     eax, [rdi+68h]
0x180032ccd  mov     dword ptr [rbp+var_70+4], eax
0x180032cd0  mov     rax, [rdi+60h]
0x180032cd4  mov     [rbp+var_38], rax
0x180032cd8  mov     rax, [rdi+58h]
0x180032cdc  mov     [rbp+var_30], rax
0x180032ce0  mov     eax, [rdi+50h]
0x180032ce3  mov     dword ptr [rbp+var_68], eax
0x180032ce6  mov     rax, [rdi+48h]
0x180032cea  mov     [rbp+var_28], rax
0x180032cee  mov     eax, [rdi+20h]
0x180032cf1  mov     dword ptr [rbp+var_68+4], eax
0x180032cf4  mov     rax, [rdi+18h]
0x180032cf8  mov     [rbp+var_20], rax
0x180032cfc  mov     eax, [rdi]
0x180032cfe  mov     [rbp+var_60], eax
0x180032d01  mov     rax, [rdi+80h]
0x180032d08  mov     [rbp+var_18], rax
0x180032d0c  mov     eax, [rdi+40h]
0x180032d0f  mov     dword ptr [rbp+var_78], eax
0x180032d12  mov     rax, [rdi+38h]
0x180032d16  mov     [rbp+var_10], rax
0x180032d1a  mov     eax, [rdi+8]
0x180032d1d  mov     dword ptr [rbp+SRWLock], eax
0x180032d20  mov     [rbp+var_8], 1000000h
0x180032d28  mov     [rbp+var_58], 0
0x180032d30  mov     r8, [rbx+110h]
0x180032d37  add     r8, 8; int
0x180032d3b  lea     rax, [rbp+var_50]
0x180032d3f  mov     [rsp+140h+var_90], rax; __int64
0x180032d47  lea     rax, [rbp+var_78+4]
0x180032d4b  mov     [rsp+140h+var_98], rax; __int64
0x180032d53  lea     rax, [rbp+var_70]
0x180032d57  mov     [rsp+140h+var_A0], rax; __int64
0x180032d5f  lea     rax, [rbp+var_48]
0x180032d63  mov     [rsp+140h+var_A8], rax; __int64
0x180032d6b  lea     rax, [rbp+var_40]
0x180032d6f  mov     [rsp+140h+var_B0], rax; __int64
0x180032d77  lea     rax, [rbp+var_70+4]
0x180032d7b  mov     [rsp+140h+var_B8], rax; __int64
0x180032d83  lea     rax, [rbp+var_38]
0x180032d87  mov     [rsp+140h+var_C0], rax; __int64
0x180032d8f  lea     rax, [rbp+var_30]
0x180032d93  mov     [rsp+140h+var_C8], rax; __int64
0x180032d98  lea     rax, [rbp+var_68]
0x180032d9c  mov     [rsp+140h+var_D0], rax; __int64
0x180032da1  lea     rax, [rbp+var_28]
0x180032da5  mov     [rsp+140h+var_D8], rax; __int64
0x180032daa  lea     rax, [rbp+var_68+4]
0x180032dae  mov     [rsp+140h+var_E0], rax; __int64
0x180032db3  lea     rax, [rbp+var_20]
0x180032db7  mov     [rsp+140h+var_E8], rax; __int64
0x180032dbc  lea     rax, [rbp+var_60]
0x180032dc0  mov     [rsp+140h+var_F0], rax; __int64
0x180032dc5  lea     rax, [rbp+var_18]
0x180032dc9  mov     [rsp+140h+var_F8], rax; __int64
0x180032dce  lea     rax, [rbp+var_78]
0x180032dd2  mov     [rsp+140h+var_100], rax; __int64
0x180032dd7  lea     rax, [rbp+var_10]
0x180032ddb  mov     [rsp+140h+var_108], rax; __int64
0x180032de0  lea     rax, [rbp+SRWLock]
0x180032de4  mov     [rsp+140h+var_110], rax; __int64
0x180032de9  lea     rax, [rbp+var_8]
0x180032ded  mov     [rsp+140h+var_118], rax; __int64
0x180032df2  lea     rax, [rbp+var_58]
0x180032df6  mov     [rsp+140h+var_120], rax; __int64
0x180032dfb  lea     rdx, byte_18009EDEB; int
0x180032e02  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180032e07  jmp     loc_180032EBD
0x180032e0c  mov     [rbp+SRWLock], 0
0x180032e14  lea     rdx, [rbp+SRWLock]
0x180032e18  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180032e1d  mov     rax, [rbx+110h]
0x180032e24  mov     dword ptr [rax], 2
0x180032e2a  mov     rcx, [rbp+SRWLock]; SRWLock
0x180032e2e  test    rcx, rcx
0x180032e31  jz      short loc_180032E3F
0x180032e33  call    cs:__imp_ReleaseSRWLockExclusive
0x180032e3a  nop     dword ptr [rax+rax+00h]
0x180032e3f  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180032e44  mov     rdi, [rax+8]
0x180032e48  mov     eax, [rdi]
0x180032e4a  cmp     eax, 4
0x180032e4d  jbe     short loc_180032EBD
0x180032e4f  mov     rcx, [rdi+18h]
0x180032e53  mov     rax, [rdi+10h]
0x180032e57  test    al, 40h
0x180032e59  jz      short loc_180032EBD
0x180032e5b  mov     rax, rcx
0x180032e5e  and     eax, 40h
0x180032e61  cmp     rax, rcx
0x180032e64  jnz     short loc_180032EBD
0x180032e66  call    cs:__imp_GetCurrentThreadId
0x180032e6d  nop     dword ptr [rax+rax+00h]
0x180032e72  mov     dword ptr [rbp+SRWLock], eax
0x180032e75  mov     r8, [rbx+110h]
0x180032e7c  mov     eax, [r8+48h]
0x180032e80  mov     dword ptr [rbp+var_78], eax
0x180032e83  mov     [rbp+var_58], 0
0x180032e8b  add     r8, 8
0x180032e8f  lea     rax, [rbp+SRWLock]
0x180032e93  mov     [rsp+140h+var_110], rax
0x180032e98  lea     rax, [rbp+var_78]
0x180032e9c  mov     [rsp+140h+var_118], rax
0x180032ea1  lea     rax, [rbp+var_58]
0x180032ea5  mov     [rsp+140h+var_120], rax
0x180032eaa  xor     r9d, r9d
0x180032ead  lea     rdx, word_18009DE26
0x180032eb4  mov     rcx, rdi
0x180032eb7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180032ebc  nop
0x180032ebd  lea     rcx, [rbx+120h]; this
0x180032ec4  cmp     dword ptr [rcx+18h], 0
0x180032ec8  jz      short loc_180032ED0
0x180032eca  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180032ecf  nop
0x180032ed0  lea     r11, [rsp+140h+var_s0]
0x180032ed8  mov     rbx, [r11+18h]
0x180032edc  mov     rdi, [r11+20h]
0x180032ee0  mov     rsp, r11
0x180032ee3  pop     rbp
0x180032ee4  retn
```
