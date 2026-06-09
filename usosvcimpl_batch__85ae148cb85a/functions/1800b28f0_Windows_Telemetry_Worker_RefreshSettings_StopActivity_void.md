# Windows::Telemetry::Worker::RefreshSettings::StopActivity(void)

- ea: `0x1800b28f0`
- end: `0x1800b2b83`
- name: `?StopActivity@RefreshSettings@Worker@Telemetry@Windows@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(Windows::Telemetry::Worker::RefreshSettings *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x18000109c`
- `0x180001f10`
- `0x180085644`
- `0x18008c454`
- `0x1800b28f0`
- `0x1800b781c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b295e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b2aea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b295e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b2aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2b1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2b1a`

## pseudocode

```c
void __fastcall Windows::Telemetry::Worker::RefreshSettings::StopActivity(
        Windows::Telemetry::Worker::RefreshSettings *this)
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
  int v15; // r9d
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
          (int)&qword_1801319A8,
          (_DWORD)v9 + 8,
          (__int64)&v22,
          (__int64)&v31,
          (__int64)&SRWLock,
          (__int64)&v30,
          (__int64)&v17,
          (__int64)&v29,
          (__int64)&v21,
          (__int64)&v28,
          (__int64)&v20,
          (__int64)&v27,
          (__int64)&v19,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v18,
          (__int64)&v24,
          (__int64)&v23);
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
      (unsigned int)qword_180131958,
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
0x1800b28f0  mov     [rsp-8+arg_8], rbx
0x1800b28f5  mov     [rsp-8+arg_10], rsi
0x1800b28fa  push    rbp
0x1800b28fb  push    rdi
0x1800b28fc  push    r14
0x1800b28fe  lea     rbp, [rsp+10h]
0x1800b2903  sub     rsp, 110h
0x1800b290a  lea     rdi, [rcx+110h]
0x1800b2911  mov     rsi, rcx
0x1800b2914  mov     rbx, [rdi]
0x1800b2917  mov     eax, [rbx+48h]
0x1800b291a  test    eax, eax
0x1800b291c  jns     loc_1800B2AC4
0x1800b2922  add     rbx, 50h ; 'P'
0x1800b2926  cmp     eax, [rbx+8]
0x1800b2929  jnz     loc_1800B2AC4
0x1800b292f  mov     r14, rdi
0x1800b2932  test    rbx, rbx
0x1800b2935  jz      loc_1800B2AC7
0x1800b293b  lea     rdx, [rbp+SRWLock]
0x1800b293f  mov     [rbp+SRWLock], 0
0x1800b2947  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800b294c  mov     rax, [rdi]
0x1800b294f  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800b2953  mov     dword ptr [rax], 2
0x1800b2959  test    rcx, rcx
0x1800b295c  jz      short loc_1800B2964
0x1800b295e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b2964  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800b2969  mov     r9, rax
0x1800b296c  cmp     dword ptr [rax], 5
0x1800b296f  jbe     loc_1800B2B64
0x1800b2975  mov     rdx, 400000000000h
0x1800b297f  test    [rax+10h], rdx
0x1800b2983  jz      loc_1800B2B64
0x1800b2989  mov     rcx, [rax+18h]
0x1800b298d  and     rcx, rdx
0x1800b2990  cmp     rcx, [rax+18h]
0x1800b2994  jnz     loc_1800B2B64
0x1800b299a  mov     rax, [rbx+78h]
0x1800b299e  lea     rdx, qword_1801319A8; int
0x1800b29a5  mov     r8, [rdi]
0x1800b29a8  mov     rcx, r9; int
0x1800b29ab  mov     [rbp+var_58], rax
0x1800b29af  add     r8, 8; int
0x1800b29b3  mov     rax, [rbx+70h]
0x1800b29b7  mov     [rbp+var_50], rax
0x1800b29bb  mov     eax, [rbx+68h]
0x1800b29be  mov     dword ptr [rbp+var_78+4], eax
0x1800b29c1  mov     rax, [rbx+60h]
0x1800b29c5  mov     [rbp+var_48], rax
0x1800b29c9  mov     rax, [rbx+58h]
0x1800b29cd  mov     [rbp+var_40], rax
0x1800b29d1  mov     eax, [rbx+50h]
0x1800b29d4  mov     dword ptr [rbp+var_70], eax
0x1800b29d7  mov     rax, [rbx+48h]
0x1800b29db  mov     [rbp+var_38], rax
0x1800b29df  mov     eax, [rbx+20h]
0x1800b29e2  mov     dword ptr [rbp+var_70+4], eax
0x1800b29e5  mov     rax, [rbx+18h]
0x1800b29e9  mov     [rbp+var_30], rax
0x1800b29ed  mov     eax, [rbx]
0x1800b29ef  mov     dword ptr [rbp+var_68], eax
0x1800b29f2  mov     rax, [rbx+80h]
0x1800b29f9  mov     [rbp+var_28], rax
0x1800b29fd  mov     eax, [rbx+40h]
0x1800b2a00  mov     dword ptr [rbp+var_78], eax
0x1800b2a03  mov     rax, [rbx+38h]
0x1800b2a07  mov     [rbp+var_20], rax
0x1800b2a0b  mov     eax, [rbx+8]
0x1800b2a0e  mov     dword ptr [rbp+SRWLock], eax
0x1800b2a11  mov     eax, 1000000h
0x1800b2a16  mov     [rbp+var_18], rax
0x1800b2a1a  mov     [rbp+var_60], rax
0x1800b2a1e  lea     rax, [rbp+var_58]
0x1800b2a22  mov     [rsp+120h+var_88], rax; __int64
0x1800b2a2a  lea     rax, [rbp+var_50]
0x1800b2a2e  mov     [rsp+120h+var_90], rax; __int64
0x1800b2a36  lea     rax, [rbp+var_78+4]
0x1800b2a3a  mov     [rsp+120h+var_98], rax; __int64
0x1800b2a42  lea     rax, [rbp+var_48]
0x1800b2a46  mov     [rsp+120h+var_A0], rax; __int64
0x1800b2a4e  lea     rax, [rbp+var_40]
0x1800b2a52  mov     [rsp+120h+var_A8], rax; __int64
0x1800b2a57  lea     rax, [rbp+var_70]
0x1800b2a5b  mov     [rsp+120h+var_B0], rax; __int64
0x1800b2a60  lea     rax, [rbp+var_38]
0x1800b2a64  mov     [rsp+120h+var_B8], rax; __int64
0x1800b2a69  lea     rax, [rbp+var_70+4]
0x1800b2a6d  mov     [rsp+120h+var_C0], rax; __int64
0x1800b2a72  lea     rax, [rbp+var_30]
0x1800b2a76  mov     [rsp+120h+var_C8], rax; __int64
0x1800b2a7b  lea     rax, [rbp+var_68]
0x1800b2a7f  mov     [rsp+120h+var_D0], rax; __int64
0x1800b2a84  lea     rax, [rbp+var_28]
0x1800b2a88  mov     [rsp+120h+var_D8], rax; __int64
0x1800b2a8d  lea     rax, [rbp+var_78]
0x1800b2a91  mov     [rsp+120h+var_E0], rax; __int64
0x1800b2a96  lea     rax, [rbp+var_20]
0x1800b2a9a  mov     [rsp+120h+var_E8], rax; __int64
0x1800b2a9f  lea     rax, [rbp+SRWLock]
0x1800b2aa3  mov     [rsp+120h+var_F0], rax; __int64
0x1800b2aa8  lea     rax, [rbp+var_18]
0x1800b2aac  mov     [rsp+120h+var_F8], rax; __int64
0x1800b2ab1  lea     rax, [rbp+var_60]
0x1800b2ab5  mov     [rsp+120h+var_100], rax; __int64
0x1800b2aba  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x1800b2abf  jmp     loc_1800B2B64
0x1800b2ac4  mov     r14, rdi
0x1800b2ac7  lea     rdx, [rbp+SRWLock]
0x1800b2acb  mov     [rbp+SRWLock], 0
0x1800b2ad3  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800b2ad8  mov     rax, [r14]
0x1800b2adb  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800b2adf  mov     dword ptr [rax], 2
0x1800b2ae5  test    rcx, rcx
0x1800b2ae8  jz      short loc_1800B2AF0
0x1800b2aea  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b2af0  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800b2af5  mov     rbx, rax
0x1800b2af8  cmp     dword ptr [rax], 5
0x1800b2afb  jbe     short loc_1800B2B64
0x1800b2afd  mov     rdx, 400000000000h
0x1800b2b07  test    [rax+10h], rdx
0x1800b2b0b  jz      short loc_1800B2B64
0x1800b2b0d  mov     rcx, [rax+18h]
0x1800b2b11  and     rcx, rdx
0x1800b2b14  cmp     rcx, [rax+18h]
0x1800b2b18  jnz     short loc_1800B2B64
0x1800b2b1a  call    cs:__imp_GetCurrentThreadId
0x1800b2b20  mov     r8, [rdi]
0x1800b2b23  lea     rdx, qword_180131958
0x1800b2b2a  mov     dword ptr [rbp+SRWLock], eax
0x1800b2b2d  mov     rcx, rbx
0x1800b2b30  mov     eax, [r8+48h]
0x1800b2b34  add     r8, 8
0x1800b2b38  mov     dword ptr [rbp+var_78], eax
0x1800b2b3b  mov     eax, 1000000h
0x1800b2b40  mov     [rbp+var_60], rax
0x1800b2b44  lea     rax, [rbp+SRWLock]
0x1800b2b48  mov     [rsp+120h+var_F0], rax
0x1800b2b4d  lea     rax, [rbp+var_78]
0x1800b2b51  mov     [rsp+120h+var_F8], rax
0x1800b2b56  lea     rax, [rbp+var_60]
0x1800b2b5a  mov     [rsp+120h+var_100], rax
0x1800b2b5f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b2b64  mov     rcx, rsi
0x1800b2b67  lea     r11, [rsp+120h+var_10]
0x1800b2b6f  mov     rbx, [r11+28h]
0x1800b2b73  mov     rsi, [r11+30h]
0x1800b2b77  mov     rsp, r11
0x1800b2b7a  pop     r14
0x1800b2b7c  pop     rdi
0x1800b2b7d  pop     rbp
0x1800b2b7e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
