# CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::StopActivity(void)

- ea: `0x1400e3280`
- end: `0x1400e3556`
- name: `?StopActivity@CreateProcessAsUserW@TraceProvider@Diagnostics@CExec@@MEAAXXZ`
- size: `726`
- prototype: `void __fastcall(CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400017a8`
- `0x140001abc`
- `0x140031be8`
- `0x14003407c`
- `0x1400e2850`
- `0x1400e3280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e32e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e34b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e32e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e34b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400e34dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400e34dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::StopActivity(
        CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *this)
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
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = CExec::Diagnostics::TraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 2) != 0 && (v7 & 2) == v7 )
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
          (int)&byte_14013B237,
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
    wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = CExec::Diagnostics::TraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 2) != 0 && (v10 & 2) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&word_14013B386,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400e3280  mov     [rsp-8+arg_8], rbx
0x1400e3285  mov     [rsp-8+arg_10], rdi
0x1400e328a  push    rbp
0x1400e328b  mov     rbp, rsp
0x1400e328e  sub     rsp, 140h
0x1400e3295  mov     rbx, rcx
0x1400e3298  mov     rdi, [rcx+110h]
0x1400e329f  mov     eax, [rdi+48h]
0x1400e32a2  test    eax, eax
0x1400e32a4  jns     loc_1400E3489
0x1400e32aa  add     rdi, 50h ; 'P'
0x1400e32ae  cmp     eax, [rdi+8]
0x1400e32b1  jnz     loc_1400E3489
0x1400e32b7  test    rdi, rdi
0x1400e32ba  jz      loc_1400E3489
0x1400e32c0  mov     [rbp+SRWLock], 0
0x1400e32c8  lea     rdx, [rbp+SRWLock]
0x1400e32cc  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400e32d1  mov     rax, [rbx+110h]
0x1400e32d8  mov     dword ptr [rax], 2
0x1400e32de  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400e32e2  test    rcx, rcx
0x1400e32e5  jz      short loc_1400E32ED
0x1400e32e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400e32ed  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x1400e32f2  mov     r9, rax
0x1400e32f5  mov     ecx, [rax]
0x1400e32f7  cmp     ecx, 4
0x1400e32fa  jbe     loc_1400E352E
0x1400e3300  mov     rax, [rax+18h]
0x1400e3304  mov     rcx, [r9+10h]
0x1400e3308  test    cl, 2
0x1400e330b  jz      loc_1400E352E
0x1400e3311  mov     rcx, rax
0x1400e3314  and     ecx, 2
0x1400e3317  cmp     rcx, rax
0x1400e331a  jnz     loc_1400E352E
0x1400e3320  mov     rax, [rdi+30h]
0x1400e3324  mov     [rbp+var_50], rax
0x1400e3328  mov     eax, [rdi+44h]
0x1400e332b  mov     dword ptr [rbp+var_78+4], eax
0x1400e332e  mov     eax, [rdi+10h]
0x1400e3331  mov     dword ptr [rbp+var_70], eax
0x1400e3334  mov     rax, [rdi+78h]
0x1400e3338  mov     [rbp+var_48], rax
0x1400e333c  mov     rax, [rdi+70h]
0x1400e3340  mov     [rbp+var_40], rax
0x1400e3344  mov     eax, [rdi+68h]
0x1400e3347  mov     dword ptr [rbp+var_70+4], eax
0x1400e334a  mov     rax, [rdi+60h]
0x1400e334e  mov     [rbp+var_38], rax
0x1400e3352  mov     rax, [rdi+58h]
0x1400e3356  mov     [rbp+var_30], rax
0x1400e335a  mov     eax, [rdi+50h]
0x1400e335d  mov     dword ptr [rbp+var_68], eax
0x1400e3360  mov     rax, [rdi+48h]
0x1400e3364  mov     [rbp+var_28], rax
0x1400e3368  mov     eax, [rdi+20h]
0x1400e336b  mov     dword ptr [rbp+var_68+4], eax
0x1400e336e  mov     rax, [rdi+18h]
0x1400e3372  mov     [rbp+var_20], rax
0x1400e3376  mov     eax, [rdi]
0x1400e3378  mov     [rbp+var_60], eax
0x1400e337b  mov     rax, [rdi+80h]
0x1400e3382  mov     [rbp+var_18], rax
0x1400e3386  mov     eax, [rdi+40h]
0x1400e3389  mov     dword ptr [rbp+var_78], eax
0x1400e338c  mov     rax, [rdi+38h]
0x1400e3390  mov     [rbp+var_10], rax
0x1400e3394  mov     eax, [rdi+8]
0x1400e3397  mov     dword ptr [rbp+SRWLock], eax
0x1400e339a  mov     [rbp+var_8], 1000000h
0x1400e33a2  mov     [rbp+var_58], 0
0x1400e33aa  mov     r8, [rbx+110h]
0x1400e33b1  add     r8, 8; int
0x1400e33b5  lea     rax, [rbp+var_50]
0x1400e33b9  mov     [rsp+140h+var_90], rax; __int64
0x1400e33c1  lea     rax, [rbp+var_78+4]
0x1400e33c5  mov     [rsp+140h+var_98], rax; __int64
0x1400e33cd  lea     rax, [rbp+var_70]
0x1400e33d1  mov     [rsp+140h+var_A0], rax; __int64
0x1400e33d9  lea     rax, [rbp+var_48]
0x1400e33dd  mov     [rsp+140h+var_A8], rax; __int64
0x1400e33e5  lea     rax, [rbp+var_40]
0x1400e33e9  mov     [rsp+140h+var_B0], rax; __int64
0x1400e33f1  lea     rax, [rbp+var_70+4]
0x1400e33f5  mov     [rsp+140h+var_B8], rax; __int64
0x1400e33fd  lea     rax, [rbp+var_38]
0x1400e3401  mov     [rsp+140h+var_C0], rax; __int64
0x1400e3409  lea     rax, [rbp+var_30]
0x1400e340d  mov     [rsp+140h+var_C8], rax; __int64
0x1400e3412  lea     rax, [rbp+var_68]
0x1400e3416  mov     [rsp+140h+var_D0], rax; __int64
0x1400e341b  lea     rax, [rbp+var_28]
0x1400e341f  mov     [rsp+140h+var_D8], rax; __int64
0x1400e3424  lea     rax, [rbp+var_68+4]
0x1400e3428  mov     [rsp+140h+var_E0], rax; __int64
0x1400e342d  lea     rax, [rbp+var_20]
0x1400e3431  mov     [rsp+140h+var_E8], rax; __int64
0x1400e3436  lea     rax, [rbp+var_60]
0x1400e343a  mov     [rsp+140h+var_F0], rax; __int64
0x1400e343f  lea     rax, [rbp+var_18]
0x1400e3443  mov     [rsp+140h+var_F8], rax; __int64
0x1400e3448  lea     rax, [rbp+var_78]
0x1400e344c  mov     [rsp+140h+var_100], rax; __int64
0x1400e3451  lea     rax, [rbp+var_10]
0x1400e3455  mov     [rsp+140h+var_108], rax; __int64
0x1400e345a  lea     rax, [rbp+SRWLock]
0x1400e345e  mov     [rsp+140h+var_110], rax; __int64
0x1400e3463  lea     rax, [rbp+var_8]
0x1400e3467  mov     [rsp+140h+var_118], rax; __int64
0x1400e346c  lea     rax, [rbp+var_58]
0x1400e3470  mov     [rsp+140h+var_120], rax; __int64
0x1400e3475  lea     rdx, byte_14013B237; int
0x1400e347c  mov     rcx, r9; int
0x1400e347f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400e3484  jmp     loc_1400E352E
0x1400e3489  mov     [rbp+SRWLock], 0
0x1400e3491  lea     rdx, [rbp+SRWLock]
0x1400e3495  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0EAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,16384,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400e349a  mov     rax, [rbx+110h]
0x1400e34a1  mov     dword ptr [rax], 2
0x1400e34a7  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400e34ab  test    rcx, rcx
0x1400e34ae  jz      short loc_1400E34B6
0x1400e34b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400e34b6  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x1400e34bb  mov     rdi, rax
0x1400e34be  mov     ecx, [rax]
0x1400e34c0  cmp     ecx, 4
0x1400e34c3  jbe     short loc_1400E352E
0x1400e34c5  mov     rax, [rax+18h]
0x1400e34c9  mov     rcx, [rdi+10h]
0x1400e34cd  test    cl, 2
0x1400e34d0  jz      short loc_1400E352E
0x1400e34d2  mov     rcx, rax
0x1400e34d5  and     ecx, 2
0x1400e34d8  cmp     rcx, rax
0x1400e34db  jnz     short loc_1400E352E
0x1400e34dd  call    cs:__imp_GetCurrentThreadId
0x1400e34e3  mov     dword ptr [rbp+SRWLock], eax
0x1400e34e6  mov     r8, [rbx+110h]
0x1400e34ed  mov     eax, [r8+48h]
0x1400e34f1  mov     dword ptr [rbp+var_78], eax
0x1400e34f4  mov     [rbp+var_58], 0
0x1400e34fc  add     r8, 8
0x1400e3500  lea     rax, [rbp+SRWLock]
0x1400e3504  mov     [rsp+140h+var_110], rax
0x1400e3509  lea     rax, [rbp+var_78]
0x1400e350d  mov     [rsp+140h+var_118], rax
0x1400e3512  lea     rax, [rbp+var_58]
0x1400e3516  mov     [rsp+140h+var_120], rax
0x1400e351b  xor     r9d, r9d
0x1400e351e  lea     rdx, word_14013B386
0x1400e3525  mov     rcx, rdi
0x1400e3528  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400e352d  nop
0x1400e352e  lea     rcx, [rbx+120h]; this
0x1400e3535  cmp     dword ptr [rcx+18h], 0
0x1400e3539  jz      short loc_1400E3541
0x1400e353b  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400e3540  nop
0x1400e3541  lea     r11, [rsp+140h+var_s0]
0x1400e3549  mov     rbx, [r11+18h]
0x1400e354d  mov     rdi, [r11+20h]
0x1400e3551  mov     rsp, r11
0x1400e3554  pop     rbp
0x1400e3555  retn
```
