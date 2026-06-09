# Windows::Telemetry::Art::RebootDowntimeEvaluationActivity::StopActivity(void)

- ea: `0x1800c18b0`
- end: `0x1800c1b43`
- name: `?StopActivity@RebootDowntimeEvaluationActivity@Art@Telemetry@Windows@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(Windows::Telemetry::Art::RebootDowntimeEvaluationActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000109c`
- `0x180001f10`
- `0x180085644`
- `0x18008c454`
- `0x1800b781c`
- `0x1800c18b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c191e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1aaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c191e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1aaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c1ada`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c1ada`

## pseudocode

```c
void __fastcall Windows::Telemetry::Art::RebootDowntimeEvaluationActivity::StopActivity(
        Windows::Telemetry::Art::RebootDowntimeEvaluationActivity *this)
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
          (int)&byte_180132A23,
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
      (unsigned int)word_1801329C2,
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
0x1800c18b0  mov     [rsp-8+arg_8], rbx
0x1800c18b5  mov     [rsp-8+arg_10], rsi
0x1800c18ba  push    rbp
0x1800c18bb  push    rdi
0x1800c18bc  push    r14
0x1800c18be  lea     rbp, [rsp+10h]
0x1800c18c3  sub     rsp, 110h
0x1800c18ca  lea     rdi, [rcx+110h]
0x1800c18d1  mov     rsi, rcx
0x1800c18d4  mov     rbx, [rdi]
0x1800c18d7  mov     eax, [rbx+48h]
0x1800c18da  test    eax, eax
0x1800c18dc  jns     loc_1800C1A84
0x1800c18e2  add     rbx, 50h ; 'P'
0x1800c18e6  cmp     eax, [rbx+8]
0x1800c18e9  jnz     loc_1800C1A84
0x1800c18ef  mov     r14, rdi
0x1800c18f2  test    rbx, rbx
0x1800c18f5  jz      loc_1800C1A87
0x1800c18fb  lea     rdx, [rbp+SRWLock]
0x1800c18ff  mov     [rbp+SRWLock], 0
0x1800c1907  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800c190c  mov     rax, [rdi]
0x1800c190f  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800c1913  mov     dword ptr [rax], 2
0x1800c1919  test    rcx, rcx
0x1800c191c  jz      short loc_1800C1924
0x1800c191e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c1924  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800c1929  mov     r9, rax
0x1800c192c  cmp     dword ptr [rax], 5
0x1800c192f  jbe     loc_1800C1B24
0x1800c1935  mov     rdx, 400000000000h
0x1800c193f  test    [rax+10h], rdx
0x1800c1943  jz      loc_1800C1B24
0x1800c1949  mov     rcx, [rax+18h]
0x1800c194d  and     rcx, rdx
0x1800c1950  cmp     rcx, [rax+18h]
0x1800c1954  jnz     loc_1800C1B24
0x1800c195a  mov     rax, [rbx+78h]
0x1800c195e  lea     rdx, byte_180132A23; int
0x1800c1965  mov     r8, [rdi]
0x1800c1968  mov     rcx, r9; int
0x1800c196b  mov     [rbp+var_58], rax
0x1800c196f  add     r8, 8; int
0x1800c1973  mov     rax, [rbx+70h]
0x1800c1977  mov     [rbp+var_50], rax
0x1800c197b  mov     eax, [rbx+68h]
0x1800c197e  mov     dword ptr [rbp+var_78+4], eax
0x1800c1981  mov     rax, [rbx+60h]
0x1800c1985  mov     [rbp+var_48], rax
0x1800c1989  mov     rax, [rbx+58h]
0x1800c198d  mov     [rbp+var_40], rax
0x1800c1991  mov     eax, [rbx+50h]
0x1800c1994  mov     dword ptr [rbp+var_70], eax
0x1800c1997  mov     rax, [rbx+48h]
0x1800c199b  mov     [rbp+var_38], rax
0x1800c199f  mov     eax, [rbx+20h]
0x1800c19a2  mov     dword ptr [rbp+var_70+4], eax
0x1800c19a5  mov     rax, [rbx+18h]
0x1800c19a9  mov     [rbp+var_30], rax
0x1800c19ad  mov     eax, [rbx]
0x1800c19af  mov     dword ptr [rbp+var_68], eax
0x1800c19b2  mov     rax, [rbx+80h]
0x1800c19b9  mov     [rbp+var_28], rax
0x1800c19bd  mov     eax, [rbx+40h]
0x1800c19c0  mov     dword ptr [rbp+var_78], eax
0x1800c19c3  mov     rax, [rbx+38h]
0x1800c19c7  mov     [rbp+var_20], rax
0x1800c19cb  mov     eax, [rbx+8]
0x1800c19ce  mov     dword ptr [rbp+SRWLock], eax
0x1800c19d1  mov     eax, 1000000h
0x1800c19d6  mov     [rbp+var_18], rax
0x1800c19da  mov     [rbp+var_60], rax
0x1800c19de  lea     rax, [rbp+var_58]
0x1800c19e2  mov     [rsp+120h+var_88], rax; __int64
0x1800c19ea  lea     rax, [rbp+var_50]
0x1800c19ee  mov     [rsp+120h+var_90], rax; __int64
0x1800c19f6  lea     rax, [rbp+var_78+4]
0x1800c19fa  mov     [rsp+120h+var_98], rax; __int64
0x1800c1a02  lea     rax, [rbp+var_48]
0x1800c1a06  mov     [rsp+120h+var_A0], rax; __int64
0x1800c1a0e  lea     rax, [rbp+var_40]
0x1800c1a12  mov     [rsp+120h+var_A8], rax; __int64
0x1800c1a17  lea     rax, [rbp+var_70]
0x1800c1a1b  mov     [rsp+120h+var_B0], rax; __int64
0x1800c1a20  lea     rax, [rbp+var_38]
0x1800c1a24  mov     [rsp+120h+var_B8], rax; __int64
0x1800c1a29  lea     rax, [rbp+var_70+4]
0x1800c1a2d  mov     [rsp+120h+var_C0], rax; __int64
0x1800c1a32  lea     rax, [rbp+var_30]
0x1800c1a36  mov     [rsp+120h+var_C8], rax; __int64
0x1800c1a3b  lea     rax, [rbp+var_68]
0x1800c1a3f  mov     [rsp+120h+var_D0], rax; __int64
0x1800c1a44  lea     rax, [rbp+var_28]
0x1800c1a48  mov     [rsp+120h+var_D8], rax; __int64
0x1800c1a4d  lea     rax, [rbp+var_78]
0x1800c1a51  mov     [rsp+120h+var_E0], rax; __int64
0x1800c1a56  lea     rax, [rbp+var_20]
0x1800c1a5a  mov     [rsp+120h+var_E8], rax; __int64
0x1800c1a5f  lea     rax, [rbp+SRWLock]
0x1800c1a63  mov     [rsp+120h+var_F0], rax; __int64
0x1800c1a68  lea     rax, [rbp+var_18]
0x1800c1a6c  mov     [rsp+120h+var_F8], rax; __int64
0x1800c1a71  lea     rax, [rbp+var_60]
0x1800c1a75  mov     [rsp+120h+var_100], rax; __int64
0x1800c1a7a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x1800c1a7f  jmp     loc_1800C1B24
0x1800c1a84  mov     r14, rdi
0x1800c1a87  lea     rdx, [rbp+SRWLock]
0x1800c1a8b  mov     [rbp+SRWLock], 0
0x1800c1a93  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800c1a98  mov     rax, [r14]
0x1800c1a9b  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800c1a9f  mov     dword ptr [rax], 2
0x1800c1aa5  test    rcx, rcx
0x1800c1aa8  jz      short loc_1800C1AB0
0x1800c1aaa  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c1ab0  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800c1ab5  mov     rbx, rax
0x1800c1ab8  cmp     dword ptr [rax], 5
0x1800c1abb  jbe     short loc_1800C1B24
0x1800c1abd  mov     rdx, 400000000000h
0x1800c1ac7  test    [rax+10h], rdx
0x1800c1acb  jz      short loc_1800C1B24
0x1800c1acd  mov     rcx, [rax+18h]
0x1800c1ad1  and     rcx, rdx
0x1800c1ad4  cmp     rcx, [rax+18h]
0x1800c1ad8  jnz     short loc_1800C1B24
0x1800c1ada  call    cs:__imp_GetCurrentThreadId
0x1800c1ae0  mov     r8, [rdi]
0x1800c1ae3  lea     rdx, word_1801329C2
0x1800c1aea  mov     dword ptr [rbp+SRWLock], eax
0x1800c1aed  mov     rcx, rbx
0x1800c1af0  mov     eax, [r8+48h]
0x1800c1af4  add     r8, 8
0x1800c1af8  mov     dword ptr [rbp+var_78], eax
0x1800c1afb  mov     eax, 1000000h
0x1800c1b00  mov     [rbp+var_60], rax
0x1800c1b04  lea     rax, [rbp+SRWLock]
0x1800c1b08  mov     [rsp+120h+var_F0], rax
0x1800c1b0d  lea     rax, [rbp+var_78]
0x1800c1b11  mov     [rsp+120h+var_F8], rax
0x1800c1b16  lea     rax, [rbp+var_60]
0x1800c1b1a  mov     [rsp+120h+var_100], rax
0x1800c1b1f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c1b24  mov     rcx, rsi
0x1800c1b27  lea     r11, [rsp+120h+var_10]
0x1800c1b2f  mov     rbx, [r11+28h]
0x1800c1b33  mov     rsi, [r11+30h]
0x1800c1b37  mov     rsp, r11
0x1800c1b3a  pop     r14
0x1800c1b3c  pop     rdi
0x1800c1b3d  pop     rbp
0x1800c1b3e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
