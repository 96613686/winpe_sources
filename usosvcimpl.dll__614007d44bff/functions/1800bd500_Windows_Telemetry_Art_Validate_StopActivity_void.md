# Windows::Telemetry::Art::Validate::StopActivity(void)

- ea: `0x1800bd500`
- end: `0x1800bd793`
- name: `?StopActivity@Validate@Art@Telemetry@Windows@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(Windows::Telemetry::Art::Validate *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000109c`
- `0x180001f10`
- `0x180085644`
- `0x18008c454`
- `0x1800b781c`
- `0x1800bd500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bd56e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bd6fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bd56e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bd6fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bd72a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bd72a`

## pseudocode

```c
void __fastcall Windows::Telemetry::Art::Validate::StopActivity(Windows::Telemetry::Art::Validate *this)
{
  _DWORD **v1; // rdi
  __int64 v3; // rbx
  int v4; // eax
  __int64 v5; // rbx
  _DWORD **v6; // r14
  RTL_SRWLOCK *v7; // rcx
  const struct _tlgProvider_t *v8; // rax
  _DWORD *v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  int v12; // ebx
  DWORD CurrentThreadId; // eax
  _DWORD *v14; // r8
  __int64 v15; // r9
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-80h] BYREF
  int v17; // [rsp+A8h] [rbp-78h] BYREF
  int v18; // [rsp+ACh] [rbp-74h] BYREF
  int v19; // [rsp+B0h] [rbp-70h] BYREF
  int v20; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v21; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v29; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v30; // [rsp+100h] [rbp-20h] BYREF
  __int64 v31; // [rsp+108h] [rbp-18h] BYREF

  v1 = (_DWORD **)((char *)this + 272);
  v3 = *((_QWORD *)this + 34);
  v4 = *(_DWORD *)(v3 + 72);
  if ( v4 < 0 && (v5 = v3 + 80, v4 == *(_DWORD *)(v5 + 8)) )
  {
    v6 = (_DWORD **)((char *)this + 272);
    if ( v5 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        this,
        &SRWLock);
      v7 = SRWLock;
      **v1 = 2;
      if ( v7 )
        ReleaseSRWLockExclusive(v7);
      v8 = Windows::Telemetry::Base::Provider();
      if ( *(_DWORD *)v8 > 5u
        && (*((_QWORD *)v8 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v8 + 3) & 0x400000000000LL) == *((_QWORD *)v8 + 3) )
      {
        v9 = *v1;
        v23 = *(_QWORD *)(v5 + 120);
        v24 = *(_QWORD *)(v5 + 112);
        v18 = *(_DWORD *)(v5 + 104);
        v25 = *(_QWORD *)(v5 + 96);
        v26 = *(_QWORD *)(v5 + 88);
        v19 = *(_DWORD *)(v5 + 80);
        v27 = *(_QWORD *)(v5 + 72);
        v20 = *(_DWORD *)(v5 + 32);
        v28 = *(_QWORD *)(v5 + 24);
        LODWORD(v21) = *(_DWORD *)v5;
        v29 = *(_QWORD *)(v5 + 128);
        v17 = *(_DWORD *)(v5 + 64);
        v30 = *(_QWORD *)(v5 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v5 + 8);
        v31 = 0x1000000;
        v22 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
          (int)v8,
          (int)&byte_180131E93,
          (_DWORD)v9 + 8,
          (__int64)v8,
          (__int64)&v22,
          (__int64)&v31,
          (__int64)&SRWLock,
          (const wchar_t **)&v30,
          (__int64)&v17,
          (const wchar_t **)&v29,
          (__int64)&v21,
          (const OLECHAR **)&v28,
          (__int64)&v20,
          (const wchar_t **)&v27,
          (__int64)&v19,
          (const wchar_t **)&v26,
          (const OLECHAR **)&v25,
          (__int64)&v18,
          (const wchar_t **)&v24,
          (const OLECHAR **)&v23);
      }
      goto LABEL_17;
    }
  }
  else
  {
    v6 = (_DWORD **)((char *)this + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v10 = SRWLock;
  **v6 = 2;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v11 = Windows::Telemetry::Base::Provider();
  v12 = (int)v11;
  if ( *(_DWORD *)v11 > 5u
    && (*((_QWORD *)v11 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v11 + 3) & 0x400000000000LL) == *((_QWORD *)v11 + 3) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v14 = *v1;
    LODWORD(SRWLock) = CurrentThreadId;
    v17 = v14[18];
    v22 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (int)word_180131E4A,
      (_DWORD)v14 + 8,
      v15,
      (__int64)&v22,
      (__int64)&v17,
      (__int64)&SRWLock);
  }
LABEL_17:
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800bd500  mov     [rsp-8+arg_8], rbx
0x1800bd505  mov     [rsp-8+arg_10], rsi
0x1800bd50a  push    rbp
0x1800bd50b  push    rdi
0x1800bd50c  push    r14
0x1800bd50e  lea     rbp, [rsp+10h]
0x1800bd513  sub     rsp, 110h
0x1800bd51a  lea     rdi, [rcx+110h]
0x1800bd521  mov     rsi, rcx
0x1800bd524  mov     rbx, [rdi]
0x1800bd527  mov     eax, [rbx+48h]
0x1800bd52a  test    eax, eax
0x1800bd52c  jns     loc_1800BD6D4
0x1800bd532  add     rbx, 50h ; 'P'
0x1800bd536  cmp     eax, [rbx+8]
0x1800bd539  jnz     loc_1800BD6D4
0x1800bd53f  mov     r14, rdi
0x1800bd542  test    rbx, rbx
0x1800bd545  jz      loc_1800BD6D7
0x1800bd54b  lea     rdx, [rbp+SRWLock]
0x1800bd54f  mov     [rbp+SRWLock], 0
0x1800bd557  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800bd55c  mov     rax, [rdi]
0x1800bd55f  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800bd563  mov     dword ptr [rax], 2
0x1800bd569  test    rcx, rcx
0x1800bd56c  jz      short loc_1800BD574
0x1800bd56e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bd574  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800bd579  mov     r9, rax
0x1800bd57c  cmp     dword ptr [rax], 5
0x1800bd57f  jbe     loc_1800BD774
0x1800bd585  mov     rdx, 400000000000h
0x1800bd58f  test    [rax+10h], rdx
0x1800bd593  jz      loc_1800BD774
0x1800bd599  mov     rcx, [rax+18h]
0x1800bd59d  and     rcx, rdx
0x1800bd5a0  cmp     rcx, [rax+18h]
0x1800bd5a4  jnz     loc_1800BD774
0x1800bd5aa  mov     rax, [rbx+78h]
0x1800bd5ae  lea     rdx, byte_180131E93; int
0x1800bd5b5  mov     r8, [rdi]
0x1800bd5b8  mov     rcx, r9; int
0x1800bd5bb  mov     [rbp+var_58], rax
0x1800bd5bf  add     r8, 8; int
0x1800bd5c3  mov     rax, [rbx+70h]
0x1800bd5c7  mov     [rbp+var_50], rax
0x1800bd5cb  mov     eax, [rbx+68h]
0x1800bd5ce  mov     dword ptr [rbp+var_78+4], eax
0x1800bd5d1  mov     rax, [rbx+60h]
0x1800bd5d5  mov     [rbp+var_48], rax
0x1800bd5d9  mov     rax, [rbx+58h]
0x1800bd5dd  mov     [rbp+var_40], rax
0x1800bd5e1  mov     eax, [rbx+50h]
0x1800bd5e4  mov     dword ptr [rbp+var_70], eax
0x1800bd5e7  mov     rax, [rbx+48h]
0x1800bd5eb  mov     [rbp+var_38], rax
0x1800bd5ef  mov     eax, [rbx+20h]
0x1800bd5f2  mov     dword ptr [rbp+var_70+4], eax
0x1800bd5f5  mov     rax, [rbx+18h]
0x1800bd5f9  mov     [rbp+var_30], rax
0x1800bd5fd  mov     eax, [rbx]
0x1800bd5ff  mov     dword ptr [rbp+var_68], eax
0x1800bd602  mov     rax, [rbx+80h]
0x1800bd609  mov     [rbp+var_28], rax
0x1800bd60d  mov     eax, [rbx+40h]
0x1800bd610  mov     dword ptr [rbp+var_78], eax
0x1800bd613  mov     rax, [rbx+38h]
0x1800bd617  mov     [rbp+var_20], rax
0x1800bd61b  mov     eax, [rbx+8]
0x1800bd61e  mov     dword ptr [rbp+SRWLock], eax
0x1800bd621  mov     eax, 1000000h
0x1800bd626  mov     [rbp+var_18], rax
0x1800bd62a  mov     [rbp+var_60], rax
0x1800bd62e  lea     rax, [rbp+var_58]
0x1800bd632  mov     [rsp+120h+var_88], rax; __int64
0x1800bd63a  lea     rax, [rbp+var_50]
0x1800bd63e  mov     [rsp+120h+var_90], rax; __int64
0x1800bd646  lea     rax, [rbp+var_78+4]
0x1800bd64a  mov     [rsp+120h+var_98], rax; __int64
0x1800bd652  lea     rax, [rbp+var_48]
0x1800bd656  mov     [rsp+120h+var_A0], rax; __int64
0x1800bd65e  lea     rax, [rbp+var_40]
0x1800bd662  mov     [rsp+120h+var_A8], rax; __int64
0x1800bd667  lea     rax, [rbp+var_70]
0x1800bd66b  mov     [rsp+120h+var_B0], rax; __int64
0x1800bd670  lea     rax, [rbp+var_38]
0x1800bd674  mov     [rsp+120h+var_B8], rax; __int64
0x1800bd679  lea     rax, [rbp+var_70+4]
0x1800bd67d  mov     [rsp+120h+var_C0], rax; __int64
0x1800bd682  lea     rax, [rbp+var_30]
0x1800bd686  mov     [rsp+120h+var_C8], rax; __int64
0x1800bd68b  lea     rax, [rbp+var_68]
0x1800bd68f  mov     [rsp+120h+var_D0], rax; __int64
0x1800bd694  lea     rax, [rbp+var_28]
0x1800bd698  mov     [rsp+120h+var_D8], rax; __int64
0x1800bd69d  lea     rax, [rbp+var_78]
0x1800bd6a1  mov     [rsp+120h+var_E0], rax; __int64
0x1800bd6a6  lea     rax, [rbp+var_20]
0x1800bd6aa  mov     [rsp+120h+var_E8], rax; __int64
0x1800bd6af  lea     rax, [rbp+SRWLock]
0x1800bd6b3  mov     [rsp+120h+var_F0], rax; __int64
0x1800bd6b8  lea     rax, [rbp+var_18]
0x1800bd6bc  mov     [rsp+120h+var_F8], rax; __int64
0x1800bd6c1  lea     rax, [rbp+var_60]
0x1800bd6c5  mov     [rsp+120h+var_100], rax; __int64
0x1800bd6ca  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x1800bd6cf  jmp     loc_1800BD774
0x1800bd6d4  mov     r14, rdi
0x1800bd6d7  lea     rdx, [rbp+SRWLock]
0x1800bd6db  mov     [rbp+SRWLock], 0
0x1800bd6e3  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800bd6e8  mov     rax, [r14]
0x1800bd6eb  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800bd6ef  mov     dword ptr [rax], 2
0x1800bd6f5  test    rcx, rcx
0x1800bd6f8  jz      short loc_1800BD700
0x1800bd6fa  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bd700  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800bd705  mov     rbx, rax
0x1800bd708  cmp     dword ptr [rax], 5
0x1800bd70b  jbe     short loc_1800BD774
0x1800bd70d  mov     rdx, 400000000000h
0x1800bd717  test    [rax+10h], rdx
0x1800bd71b  jz      short loc_1800BD774
0x1800bd71d  mov     rcx, [rax+18h]
0x1800bd721  and     rcx, rdx
0x1800bd724  cmp     rcx, [rax+18h]
0x1800bd728  jnz     short loc_1800BD774
0x1800bd72a  call    cs:__imp_GetCurrentThreadId
0x1800bd730  mov     r8, [rdi]
0x1800bd733  lea     rdx, word_180131E4A
0x1800bd73a  mov     dword ptr [rbp+SRWLock], eax
0x1800bd73d  mov     rcx, rbx
0x1800bd740  mov     eax, [r8+48h]
0x1800bd744  add     r8, 8
0x1800bd748  mov     dword ptr [rbp+var_78], eax
0x1800bd74b  mov     eax, 1000000h
0x1800bd750  mov     [rbp+var_60], rax
0x1800bd754  lea     rax, [rbp+SRWLock]
0x1800bd758  mov     [rsp+120h+var_F0], rax
0x1800bd75d  lea     rax, [rbp+var_78]
0x1800bd761  mov     [rsp+120h+var_F8], rax
0x1800bd766  lea     rax, [rbp+var_60]
0x1800bd76a  mov     [rsp+120h+var_100], rax
0x1800bd76f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bd774  mov     rcx, rsi
0x1800bd777  lea     r11, [rsp+120h+var_10]
0x1800bd77f  mov     rbx, [r11+28h]
0x1800bd783  mov     rsi, [r11+30h]
0x1800bd787  mov     rsp, r11
0x1800bd78a  pop     r14
0x1800bd78c  pop     rdi
0x1800bd78d  pop     rbp
0x1800bd78e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
