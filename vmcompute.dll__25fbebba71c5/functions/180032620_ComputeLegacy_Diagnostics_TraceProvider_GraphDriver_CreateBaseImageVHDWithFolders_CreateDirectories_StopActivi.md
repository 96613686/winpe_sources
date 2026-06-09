# ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories::StopActivity(void)

- ea: `0x180032620`
- end: `0x180032906`
- name: `?StopActivity@GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories@TraceProvider@Diagnostics@ComputeLegacy@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18000a41c`
- `0x18001c384`
- `0x180021d1c`
- `0x180032620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032687`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032853`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032687`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032853`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032886`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032886`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories::StopActivity(
        ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories *this)
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
        (int)&dword_18009DE84,
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
        (unsigned int)word_18009E89A,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLegacy::Diagnostics::TraceProvider::GraphDriver_CreateBaseImageVHDWithFolders_CreateDirectories *)((char *)this + 288));
}

```

## disassembly

```asm
0x180032620  mov     [rsp-8+arg_8], rbx
0x180032625  mov     [rsp-8+arg_10], rdi
0x18003262a  push    rbp
0x18003262b  mov     rbp, rsp
0x18003262e  sub     rsp, 140h
0x180032635  mov     rbx, rcx
0x180032638  mov     rdi, [rcx+110h]
0x18003263f  mov     eax, [rdi+48h]
0x180032642  test    eax, eax
0x180032644  jns     loc_18003282C
0x18003264a  add     rdi, 50h ; 'P'
0x18003264e  cmp     eax, [rdi+8]
0x180032651  jnz     loc_18003282C
0x180032657  test    rdi, rdi
0x18003265a  jz      loc_18003282C
0x180032660  mov     [rbp+SRWLock], 0
0x180032668  lea     rdx, [rbp+SRWLock]
0x18003266c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180032671  mov     rax, [rbx+110h]
0x180032678  mov     dword ptr [rax], 2
0x18003267e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180032682  test    rcx, rcx
0x180032685  jz      short loc_180032693
0x180032687  call    cs:__imp_ReleaseSRWLockExclusive
0x18003268e  nop     dword ptr [rax+rax+00h]
0x180032693  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180032698  mov     rcx, [rax+8]; int
0x18003269c  mov     eax, [rcx]
0x18003269e  cmp     eax, 4
0x1800326a1  jbe     loc_1800328DD
0x1800326a7  mov     rdx, [rcx+18h]
0x1800326ab  mov     rax, [rcx+10h]
0x1800326af  test    al, 40h
0x1800326b1  jz      loc_1800328DD
0x1800326b7  mov     rax, rdx
0x1800326ba  and     eax, 40h
0x1800326bd  cmp     rax, rdx
0x1800326c0  jnz     loc_1800328DD
0x1800326c6  mov     rax, [rdi+30h]
0x1800326ca  mov     [rbp+var_50], rax
0x1800326ce  mov     eax, [rdi+44h]
0x1800326d1  mov     dword ptr [rbp+var_78+4], eax
0x1800326d4  mov     eax, [rdi+10h]
0x1800326d7  mov     dword ptr [rbp+var_70], eax
0x1800326da  mov     rax, [rdi+78h]
0x1800326de  mov     [rbp+var_48], rax
0x1800326e2  mov     rax, [rdi+70h]
0x1800326e6  mov     [rbp+var_40], rax
0x1800326ea  mov     eax, [rdi+68h]
0x1800326ed  mov     dword ptr [rbp+var_70+4], eax
0x1800326f0  mov     rax, [rdi+60h]
0x1800326f4  mov     [rbp+var_38], rax
0x1800326f8  mov     rax, [rdi+58h]
0x1800326fc  mov     [rbp+var_30], rax
0x180032700  mov     eax, [rdi+50h]
0x180032703  mov     dword ptr [rbp+var_68], eax
0x180032706  mov     rax, [rdi+48h]
0x18003270a  mov     [rbp+var_28], rax
0x18003270e  mov     eax, [rdi+20h]
0x180032711  mov     dword ptr [rbp+var_68+4], eax
0x180032714  mov     rax, [rdi+18h]
0x180032718  mov     [rbp+var_20], rax
0x18003271c  mov     eax, [rdi]
0x18003271e  mov     [rbp+var_60], eax
0x180032721  mov     rax, [rdi+80h]
0x180032728  mov     [rbp+var_18], rax
0x18003272c  mov     eax, [rdi+40h]
0x18003272f  mov     dword ptr [rbp+var_78], eax
0x180032732  mov     rax, [rdi+38h]
0x180032736  mov     [rbp+var_10], rax
0x18003273a  mov     eax, [rdi+8]
0x18003273d  mov     dword ptr [rbp+SRWLock], eax
0x180032740  mov     [rbp+var_8], 1000000h
0x180032748  mov     [rbp+var_58], 0
0x180032750  mov     r8, [rbx+110h]
0x180032757  add     r8, 8; int
0x18003275b  lea     rax, [rbp+var_50]
0x18003275f  mov     [rsp+140h+var_90], rax; __int64
0x180032767  lea     rax, [rbp+var_78+4]
0x18003276b  mov     [rsp+140h+var_98], rax; __int64
0x180032773  lea     rax, [rbp+var_70]
0x180032777  mov     [rsp+140h+var_A0], rax; __int64
0x18003277f  lea     rax, [rbp+var_48]
0x180032783  mov     [rsp+140h+var_A8], rax; __int64
0x18003278b  lea     rax, [rbp+var_40]
0x18003278f  mov     [rsp+140h+var_B0], rax; __int64
0x180032797  lea     rax, [rbp+var_70+4]
0x18003279b  mov     [rsp+140h+var_B8], rax; __int64
0x1800327a3  lea     rax, [rbp+var_38]
0x1800327a7  mov     [rsp+140h+var_C0], rax; __int64
0x1800327af  lea     rax, [rbp+var_30]
0x1800327b3  mov     [rsp+140h+var_C8], rax; __int64
0x1800327b8  lea     rax, [rbp+var_68]
0x1800327bc  mov     [rsp+140h+var_D0], rax; __int64
0x1800327c1  lea     rax, [rbp+var_28]
0x1800327c5  mov     [rsp+140h+var_D8], rax; __int64
0x1800327ca  lea     rax, [rbp+var_68+4]
0x1800327ce  mov     [rsp+140h+var_E0], rax; __int64
0x1800327d3  lea     rax, [rbp+var_20]
0x1800327d7  mov     [rsp+140h+var_E8], rax; __int64
0x1800327dc  lea     rax, [rbp+var_60]
0x1800327e0  mov     [rsp+140h+var_F0], rax; __int64
0x1800327e5  lea     rax, [rbp+var_18]
0x1800327e9  mov     [rsp+140h+var_F8], rax; __int64
0x1800327ee  lea     rax, [rbp+var_78]
0x1800327f2  mov     [rsp+140h+var_100], rax; __int64
0x1800327f7  lea     rax, [rbp+var_10]
0x1800327fb  mov     [rsp+140h+var_108], rax; __int64
0x180032800  lea     rax, [rbp+SRWLock]
0x180032804  mov     [rsp+140h+var_110], rax; __int64
0x180032809  lea     rax, [rbp+var_8]
0x18003280d  mov     [rsp+140h+var_118], rax; __int64
0x180032812  lea     rax, [rbp+var_58]
0x180032816  mov     [rsp+140h+var_120], rax; __int64
0x18003281b  lea     rdx, dword_18009DE84; int
0x180032822  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180032827  jmp     loc_1800328DD
0x18003282c  mov     [rbp+SRWLock], 0
0x180032834  lea     rdx, [rbp+SRWLock]
0x180032838  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003283d  mov     rax, [rbx+110h]
0x180032844  mov     dword ptr [rax], 2
0x18003284a  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003284e  test    rcx, rcx
0x180032851  jz      short loc_18003285F
0x180032853  call    cs:__imp_ReleaseSRWLockExclusive
0x18003285a  nop     dword ptr [rax+rax+00h]
0x18003285f  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180032864  mov     rdi, [rax+8]
0x180032868  mov     eax, [rdi]
0x18003286a  cmp     eax, 4
0x18003286d  jbe     short loc_1800328DD
0x18003286f  mov     rcx, [rdi+18h]
0x180032873  mov     rax, [rdi+10h]
0x180032877  test    al, 40h
0x180032879  jz      short loc_1800328DD
0x18003287b  mov     rax, rcx
0x18003287e  and     eax, 40h
0x180032881  cmp     rax, rcx
0x180032884  jnz     short loc_1800328DD
0x180032886  call    cs:__imp_GetCurrentThreadId
0x18003288d  nop     dword ptr [rax+rax+00h]
0x180032892  mov     dword ptr [rbp+SRWLock], eax
0x180032895  mov     r8, [rbx+110h]
0x18003289c  mov     eax, [r8+48h]
0x1800328a0  mov     dword ptr [rbp+var_78], eax
0x1800328a3  mov     [rbp+var_58], 0
0x1800328ab  add     r8, 8
0x1800328af  lea     rax, [rbp+SRWLock]
0x1800328b3  mov     [rsp+140h+var_110], rax
0x1800328b8  lea     rax, [rbp+var_78]
0x1800328bc  mov     [rsp+140h+var_118], rax
0x1800328c1  lea     rax, [rbp+var_58]
0x1800328c5  mov     [rsp+140h+var_120], rax
0x1800328ca  xor     r9d, r9d
0x1800328cd  lea     rdx, word_18009E89A
0x1800328d4  mov     rcx, rdi
0x1800328d7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800328dc  nop
0x1800328dd  lea     rcx, [rbx+120h]; this
0x1800328e4  cmp     dword ptr [rcx+18h], 0
0x1800328e8  jz      short loc_1800328F0
0x1800328ea  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800328ef  nop
0x1800328f0  lea     r11, [rsp+140h+var_s0]
0x1800328f8  mov     rbx, [r11+18h]
0x1800328fc  mov     rdi, [r11+20h]
0x180032900  mov     rsp, r11
0x180032903  pop     rbp
0x180032904  retn
```
