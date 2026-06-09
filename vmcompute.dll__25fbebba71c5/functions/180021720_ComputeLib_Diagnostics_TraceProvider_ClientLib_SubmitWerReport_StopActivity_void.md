# ComputeLib::Diagnostics::TraceProvider::ClientLib_SubmitWerReport::StopActivity(void)

- ea: `0x180021720`
- end: `0x180021a13`
- name: `?StopActivity@ClientLib_SubmitWerReport@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_SubmitWerReport *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001ad4`
- `0x18001c384`
- `0x18001ed48`
- `0x180021720`
- `0x180021d1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021787`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002195b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021787`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002195b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021993`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021993`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_SubmitWerReport::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_SubmitWerReport *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  int v15; // [rsp+D0h] [rbp-70h] BYREF
  int v16; // [rsp+D4h] [rbp-6Ch] BYREF
  int v17; // [rsp+D8h] [rbp-68h] BYREF
  int v18; // [rsp+DCh] [rbp-64h] BYREF
  int v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27; // [rsp+120h] [rbp-20h] BYREF
  __int64 v28; // [rsp+128h] [rbp-18h] BYREF
  __int64 v29; // [rsp+130h] [rbp-10h] BYREF
  __int64 v30; // [rsp+138h] [rbp-8h] BYREF

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
    v5 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x10000LL) != 0 && (v7 & 0x10000) == v7 )
      {
        v21 = *((_QWORD *)v4 + 6);
        v14 = v4[17];
        v15 = v4[4];
        v22 = *((_QWORD *)v4 + 15);
        v23 = *((_QWORD *)v4 + 14);
        v16 = v4[26];
        v24 = *((_QWORD *)v4 + 12);
        v25 = *((_QWORD *)v4 + 11);
        v17 = v4[20];
        v26 = *((_QWORD *)v4 + 9);
        v18 = v4[8];
        v27 = *((_QWORD *)v4 + 3);
        v19 = *v4;
        v28 = *((_QWORD *)v4 + 16);
        v13 = v4[16];
        v29 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (int)v6,
          (int)&dword_18009D26C,
          *((_QWORD *)this + 34) + 8,
          (__int64)&v20,
          (__int64)&v30,
          (__int64)&SRWLock,
          (__int64)&v29,
          (__int64)&v13,
          (__int64)&v28,
          (__int64)&v19,
          (__int64)&v27,
          (__int64)&v18,
          (__int64)&v26,
          (__int64)&v17,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v16,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v21);
      }
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
    v8 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x10000LL) != 0 && (v10 & 0x10000) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)word_18009CE22,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_SubmitWerReport *)((char *)this + 288));
}

```

## disassembly

```asm
0x180021720  mov     [rsp-8+arg_8], rbx
0x180021725  mov     [rsp-8+arg_10], rdi
0x18002172a  push    rbp
0x18002172b  mov     rbp, rsp
0x18002172e  sub     rsp, 140h
0x180021735  mov     rbx, rcx
0x180021738  mov     rdi, [rcx+110h]
0x18002173f  mov     eax, [rdi+48h]
0x180021742  test    eax, eax
0x180021744  jns     loc_180021934
0x18002174a  add     rdi, 50h ; 'P'
0x18002174e  cmp     eax, [rdi+8]
0x180021751  jnz     loc_180021934
0x180021757  test    rdi, rdi
0x18002175a  jz      loc_180021934
0x180021760  mov     [rbp+SRWLock], 0
0x180021768  lea     rdx, [rbp+SRWLock]
0x18002176c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180021771  mov     rax, [rbx+110h]
0x180021778  mov     dword ptr [rax], 2
0x18002177e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180021782  test    rcx, rcx
0x180021785  jz      short loc_180021793
0x180021787  call    cs:__imp_ReleaseSRWLockExclusive
0x18002178e  nop     dword ptr [rax+rax+00h]
0x180021793  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x180021798  mov     r9, rax
0x18002179b  mov     ecx, [rax]
0x18002179d  cmp     ecx, 4
0x1800217a0  jbe     loc_1800219EA
0x1800217a6  mov     rax, [rax+18h]
0x1800217aa  mov     rcx, [r9+10h]
0x1800217ae  mov     edx, 10000h
0x1800217b3  test    rdx, rcx
0x1800217b6  jz      loc_1800219EA
0x1800217bc  mov     rcx, rax
0x1800217bf  and     rcx, rdx
0x1800217c2  cmp     rcx, rax
0x1800217c5  jnz     loc_1800219EA
0x1800217cb  mov     rax, [rdi+30h]
0x1800217cf  mov     [rbp+var_50], rax
0x1800217d3  mov     eax, [rdi+44h]
0x1800217d6  mov     dword ptr [rbp+var_78+4], eax
0x1800217d9  mov     eax, [rdi+10h]
0x1800217dc  mov     dword ptr [rbp+var_70], eax
0x1800217df  mov     rax, [rdi+78h]
0x1800217e3  mov     [rbp+var_48], rax
0x1800217e7  mov     rax, [rdi+70h]
0x1800217eb  mov     [rbp+var_40], rax
0x1800217ef  mov     eax, [rdi+68h]
0x1800217f2  mov     dword ptr [rbp+var_70+4], eax
0x1800217f5  mov     rax, [rdi+60h]
0x1800217f9  mov     [rbp+var_38], rax
0x1800217fd  mov     rax, [rdi+58h]
0x180021801  mov     [rbp+var_30], rax
0x180021805  mov     eax, [rdi+50h]
0x180021808  mov     dword ptr [rbp+var_68], eax
0x18002180b  mov     rax, [rdi+48h]
0x18002180f  mov     [rbp+var_28], rax
0x180021813  mov     eax, [rdi+20h]
0x180021816  mov     dword ptr [rbp+var_68+4], eax
0x180021819  mov     rax, [rdi+18h]
0x18002181d  mov     [rbp+var_20], rax
0x180021821  mov     eax, [rdi]
0x180021823  mov     [rbp+var_60], eax
0x180021826  mov     rax, [rdi+80h]
0x18002182d  mov     [rbp+var_18], rax
0x180021831  mov     eax, [rdi+40h]
0x180021834  mov     dword ptr [rbp+var_78], eax
0x180021837  mov     rax, [rdi+38h]
0x18002183b  mov     [rbp+var_10], rax
0x18002183f  mov     eax, [rdi+8]
0x180021842  mov     dword ptr [rbp+SRWLock], eax
0x180021845  mov     [rbp+var_8], 1000000h
0x18002184d  mov     [rbp+var_58], 0
0x180021855  mov     r8, [rbx+110h]
0x18002185c  add     r8, 8; int
0x180021860  lea     rax, [rbp+var_50]
0x180021864  mov     [rsp+140h+var_90], rax; __int64
0x18002186c  lea     rax, [rbp+var_78+4]
0x180021870  mov     [rsp+140h+var_98], rax; __int64
0x180021878  lea     rax, [rbp+var_70]
0x18002187c  mov     [rsp+140h+var_A0], rax; __int64
0x180021884  lea     rax, [rbp+var_48]
0x180021888  mov     [rsp+140h+var_A8], rax; __int64
0x180021890  lea     rax, [rbp+var_40]
0x180021894  mov     [rsp+140h+var_B0], rax; __int64
0x18002189c  lea     rax, [rbp+var_70+4]
0x1800218a0  mov     [rsp+140h+var_B8], rax; __int64
0x1800218a8  lea     rax, [rbp+var_38]
0x1800218ac  mov     [rsp+140h+var_C0], rax; __int64
0x1800218b4  lea     rax, [rbp+var_30]
0x1800218b8  mov     [rsp+140h+var_C8], rax; __int64
0x1800218bd  lea     rax, [rbp+var_68]
0x1800218c1  mov     [rsp+140h+var_D0], rax; __int64
0x1800218c6  lea     rax, [rbp+var_28]
0x1800218ca  mov     [rsp+140h+var_D8], rax; __int64
0x1800218cf  lea     rax, [rbp+var_68+4]
0x1800218d3  mov     [rsp+140h+var_E0], rax; __int64
0x1800218d8  lea     rax, [rbp+var_20]
0x1800218dc  mov     [rsp+140h+var_E8], rax; __int64
0x1800218e1  lea     rax, [rbp+var_60]
0x1800218e5  mov     [rsp+140h+var_F0], rax; __int64
0x1800218ea  lea     rax, [rbp+var_18]
0x1800218ee  mov     [rsp+140h+var_F8], rax; __int64
0x1800218f3  lea     rax, [rbp+var_78]
0x1800218f7  mov     [rsp+140h+var_100], rax; __int64
0x1800218fc  lea     rax, [rbp+var_10]
0x180021900  mov     [rsp+140h+var_108], rax; __int64
0x180021905  lea     rax, [rbp+SRWLock]
0x180021909  mov     [rsp+140h+var_110], rax; __int64
0x18002190e  lea     rax, [rbp+var_8]
0x180021912  mov     [rsp+140h+var_118], rax; __int64
0x180021917  lea     rax, [rbp+var_58]
0x18002191b  mov     [rsp+140h+var_120], rax; __int64
0x180021920  lea     rdx, dword_18009D26C; int
0x180021927  mov     rcx, r9; int
0x18002192a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002192f  jmp     loc_1800219EA
0x180021934  mov     [rbp+SRWLock], 0
0x18002193c  lea     rdx, [rbp+SRWLock]
0x180021940  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180021945  mov     rax, [rbx+110h]
0x18002194c  mov     dword ptr [rax], 2
0x180021952  mov     rcx, [rbp+SRWLock]; SRWLock
0x180021956  test    rcx, rcx
0x180021959  jz      short loc_180021967
0x18002195b  call    cs:__imp_ReleaseSRWLockExclusive
0x180021962  nop     dword ptr [rax+rax+00h]
0x180021967  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18002196c  mov     rdi, rax
0x18002196f  mov     ecx, [rax]
0x180021971  cmp     ecx, 4
0x180021974  jbe     short loc_1800219EA
0x180021976  mov     rax, [rax+18h]
0x18002197a  mov     rcx, [rdi+10h]
0x18002197e  mov     edx, 10000h
0x180021983  test    rdx, rcx
0x180021986  jz      short loc_1800219EA
0x180021988  mov     rcx, rax
0x18002198b  and     rcx, rdx
0x18002198e  cmp     rcx, rax
0x180021991  jnz     short loc_1800219EA
0x180021993  call    cs:__imp_GetCurrentThreadId
0x18002199a  nop     dword ptr [rax+rax+00h]
0x18002199f  mov     dword ptr [rbp+SRWLock], eax
0x1800219a2  mov     r8, [rbx+110h]
0x1800219a9  mov     eax, [r8+48h]
0x1800219ad  mov     dword ptr [rbp+var_78], eax
0x1800219b0  mov     [rbp+var_58], 0
0x1800219b8  add     r8, 8
0x1800219bc  lea     rax, [rbp+SRWLock]
0x1800219c0  mov     [rsp+140h+var_110], rax
0x1800219c5  lea     rax, [rbp+var_78]
0x1800219c9  mov     [rsp+140h+var_118], rax
0x1800219ce  lea     rax, [rbp+var_58]
0x1800219d2  mov     [rsp+140h+var_120], rax
0x1800219d7  xor     r9d, r9d
0x1800219da  lea     rdx, word_18009CE22
0x1800219e1  mov     rcx, rdi
0x1800219e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800219e9  nop
0x1800219ea  lea     rcx, [rbx+120h]; this
0x1800219f1  cmp     dword ptr [rcx+18h], 0
0x1800219f5  jz      short loc_1800219FD
0x1800219f7  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800219fc  nop
0x1800219fd  lea     r11, [rsp+140h+var_s0]
0x180021a05  mov     rbx, [r11+18h]
0x180021a09  mov     rdi, [r11+20h]
0x180021a0d  mov     rsp, r11
0x180021a10  pop     rbp
0x180021a11  retn
```
