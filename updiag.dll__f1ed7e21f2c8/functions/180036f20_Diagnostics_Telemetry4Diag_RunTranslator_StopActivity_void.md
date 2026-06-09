# Diagnostics::Telemetry4Diag::RunTranslator::StopActivity(void)

- ea: `0x180036f20`
- end: `0x1800371b6`
- name: `?StopActivity@RunTranslator@Telemetry4Diag@Diagnostics@@MEAAXXZ`
- size: `662`
- prototype: `void __fastcall(Diagnostics::Telemetry4Diag::RunTranslator *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000109c`
- `0x1800017ec`
- `0x1800080f8`
- `0x180017ad8`
- `0x180017e80`
- `0x180036f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036f8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003711c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036f8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003711c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003714d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003714d`

## pseudocode

```c
void __fastcall Diagnostics::Telemetry4Diag::RunTranslator::StopActivity(
        Diagnostics::Telemetry4Diag::RunTranslator *this)
{
  _DWORD **v1; // rdi
  __int64 v3; // rbx
  int v4; // eax
  __int64 v5; // rbx
  _DWORD **v6; // r14
  RTL_SRWLOCK *v7; // rcx
  __int64 v8; // r9
  _DWORD *v9; // r8
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rbx
  DWORD CurrentThreadId; // eax
  _DWORD *v13; // r8
  __int64 v14; // r9
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-80h] BYREF
  int v16; // [rsp+A8h] [rbp-78h] BYREF
  int v17; // [rsp+ACh] [rbp-74h] BYREF
  int v18; // [rsp+B0h] [rbp-70h] BYREF
  int v19; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v20; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v29; // [rsp+100h] [rbp-20h] BYREF
  __int64 v30; // [rsp+108h] [rbp-18h] BYREF

  v1 = (_DWORD **)((char *)this + 272);
  v3 = *((_QWORD *)this + 34);
  v4 = *(_DWORD *)(v3 + 72);
  if ( v4 < 0 && (v5 = v3 + 80, v4 == *(_DWORD *)(v5 + 8)) )
  {
    v6 = (_DWORD **)((char *)this + 272);
    if ( v5 )
    {
      SRWLock = 0;
      wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        this,
        &SRWLock);
      v7 = SRWLock;
      **v1 = 2;
      if ( v7 )
        ReleaseSRWLockExclusive(v7);
      v8 = *((_QWORD *)Diagnostics::Telemetry4Diag::Instance() + 1);
      if ( *(_DWORD *)v8 > 5u
        && (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v8 + 24) & 0x400000000000LL) == *(_QWORD *)(v8 + 24) )
      {
        v9 = *v1;
        v22 = *(_QWORD *)(v5 + 120);
        v23 = *(_QWORD *)(v5 + 112);
        v17 = *(_DWORD *)(v5 + 104);
        v24 = *(_QWORD *)(v5 + 96);
        v25 = *(_QWORD *)(v5 + 88);
        v18 = *(_DWORD *)(v5 + 80);
        v26 = *(_QWORD *)(v5 + 72);
        v19 = *(_DWORD *)(v5 + 32);
        v27 = *(_QWORD *)(v5 + 24);
        LODWORD(v20) = *(_DWORD *)v5;
        v28 = *(_QWORD *)(v5 + 128);
        v16 = *(_DWORD *)(v5 + 64);
        v29 = *(_QWORD *)(v5 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v5 + 8);
        v30 = 0x1000000;
        v21 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
          v8,
          (int)&byte_18017239B,
          (_DWORD)v9 + 8,
          v8,
          (__int64)&v21,
          (__int64)&v30,
          (__int64)&SRWLock,
          (const wchar_t **)&v29,
          (__int64)&v16,
          (const wchar_t **)&v28,
          (__int64)&v20,
          (const wchar_t **)&v27,
          (__int64)&v19,
          (const wchar_t **)&v26,
          (__int64)&v18,
          (const wchar_t **)&v25,
          (const wchar_t **)&v24,
          (__int64)&v17,
          (const wchar_t **)&v23,
          (const wchar_t **)&v22);
      }
      goto LABEL_17;
    }
  }
  else
  {
    v6 = (_DWORD **)((char *)this + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v10 = SRWLock;
  **v6 = 2;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v11 = *((_QWORD *)Diagnostics::Telemetry4Diag::Instance() + 1);
  if ( *(_DWORD *)v11 > 5u
    && (*(_QWORD *)(v11 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v11 + 24) & 0x400000000000LL) == *(_QWORD *)(v11 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v13 = *v1;
    LODWORD(SRWLock) = CurrentThreadId;
    v16 = v13[18];
    v21 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (int)byte_18017234D,
      (_DWORD)v13 + 8,
      v14,
      (__int64)&v21,
      (__int64)&v16,
      (__int64)&SRWLock);
  }
LABEL_17:
  wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180036f20  mov     [rsp-8+arg_8], rbx
0x180036f25  mov     [rsp-8+arg_10], rsi
0x180036f2a  push    rbp
0x180036f2b  push    rdi
0x180036f2c  push    r14
0x180036f2e  lea     rbp, [rsp+10h]
0x180036f33  sub     rsp, 110h
0x180036f3a  lea     rdi, [rcx+110h]
0x180036f41  mov     rsi, rcx
0x180036f44  mov     rbx, [rdi]
0x180036f47  mov     eax, [rbx+48h]
0x180036f4a  test    eax, eax
0x180036f4c  jns     loc_1800370F6
0x180036f52  add     rbx, 50h ; 'P'
0x180036f56  cmp     eax, [rbx+8]
0x180036f59  jnz     loc_1800370F6
0x180036f5f  mov     r14, rdi
0x180036f62  test    rbx, rbx
0x180036f65  jz      loc_1800370F9
0x180036f6b  lea     rdx, [rbp+SRWLock]
0x180036f6f  mov     [rbp+SRWLock], 0
0x180036f77  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180036f7c  mov     rax, [rdi]
0x180036f7f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180036f83  mov     dword ptr [rax], 2
0x180036f89  test    rcx, rcx
0x180036f8c  jz      short loc_180036F94
0x180036f8e  call    cs:__imp_ReleaseSRWLockExclusive
0x180036f94  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180036f99  mov     r9, [rax+8]
0x180036f9d  cmp     dword ptr [r9], 5
0x180036fa1  jbe     loc_180037197
0x180036fa7  mov     rcx, 400000000000h
0x180036fb1  test    [r9+10h], rcx
0x180036fb5  jz      loc_180037197
0x180036fbb  mov     rax, [r9+18h]
0x180036fbf  and     rax, rcx
0x180036fc2  cmp     rax, [r9+18h]
0x180036fc6  jnz     loc_180037197
0x180036fcc  mov     rax, [rbx+78h]
0x180036fd0  lea     rdx, byte_18017239B; int
0x180036fd7  mov     r8, [rdi]
0x180036fda  mov     rcx, r9; int
0x180036fdd  mov     [rbp+var_58], rax
0x180036fe1  add     r8, 8; int
0x180036fe5  mov     rax, [rbx+70h]
0x180036fe9  mov     [rbp+var_50], rax
0x180036fed  mov     eax, [rbx+68h]
0x180036ff0  mov     dword ptr [rbp+var_78+4], eax
0x180036ff3  mov     rax, [rbx+60h]
0x180036ff7  mov     [rbp+var_48], rax
0x180036ffb  mov     rax, [rbx+58h]
0x180036fff  mov     [rbp+var_40], rax
0x180037003  mov     eax, [rbx+50h]
0x180037006  mov     dword ptr [rbp+var_70], eax
0x180037009  mov     rax, [rbx+48h]
0x18003700d  mov     [rbp+var_38], rax
0x180037011  mov     eax, [rbx+20h]
0x180037014  mov     dword ptr [rbp+var_70+4], eax
0x180037017  mov     rax, [rbx+18h]
0x18003701b  mov     [rbp+var_30], rax
0x18003701f  mov     eax, [rbx]
0x180037021  mov     dword ptr [rbp+var_68], eax
0x180037024  mov     rax, [rbx+80h]
0x18003702b  mov     [rbp+var_28], rax
0x18003702f  mov     eax, [rbx+40h]
0x180037032  mov     dword ptr [rbp+var_78], eax
0x180037035  mov     rax, [rbx+38h]
0x180037039  mov     [rbp+var_20], rax
0x18003703d  mov     eax, [rbx+8]
0x180037040  mov     dword ptr [rbp+SRWLock], eax
0x180037043  mov     eax, 1000000h
0x180037048  mov     [rbp+var_18], rax
0x18003704c  mov     [rbp+var_60], rax
0x180037050  lea     rax, [rbp+var_58]
0x180037054  mov     [rsp+120h+var_88], rax; __int64
0x18003705c  lea     rax, [rbp+var_50]
0x180037060  mov     [rsp+120h+var_90], rax; __int64
0x180037068  lea     rax, [rbp+var_78+4]
0x18003706c  mov     [rsp+120h+var_98], rax; __int64
0x180037074  lea     rax, [rbp+var_48]
0x180037078  mov     [rsp+120h+var_A0], rax; __int64
0x180037080  lea     rax, [rbp+var_40]
0x180037084  mov     [rsp+120h+var_A8], rax; __int64
0x180037089  lea     rax, [rbp+var_70]
0x18003708d  mov     [rsp+120h+var_B0], rax; __int64
0x180037092  lea     rax, [rbp+var_38]
0x180037096  mov     [rsp+120h+var_B8], rax; __int64
0x18003709b  lea     rax, [rbp+var_70+4]
0x18003709f  mov     [rsp+120h+var_C0], rax; __int64
0x1800370a4  lea     rax, [rbp+var_30]
0x1800370a8  mov     [rsp+120h+var_C8], rax; __int64
0x1800370ad  lea     rax, [rbp+var_68]
0x1800370b1  mov     [rsp+120h+var_D0], rax; __int64
0x1800370b6  lea     rax, [rbp+var_28]
0x1800370ba  mov     [rsp+120h+var_D8], rax; __int64
0x1800370bf  lea     rax, [rbp+var_78]
0x1800370c3  mov     [rsp+120h+var_E0], rax; __int64
0x1800370c8  lea     rax, [rbp+var_20]
0x1800370cc  mov     [rsp+120h+var_E8], rax; __int64
0x1800370d1  lea     rax, [rbp+SRWLock]
0x1800370d5  mov     [rsp+120h+var_F0], rax; __int64
0x1800370da  lea     rax, [rbp+var_18]
0x1800370de  mov     [rsp+120h+var_F8], rax; __int64
0x1800370e3  lea     rax, [rbp+var_60]
0x1800370e7  mov     [rsp+120h+var_100], rax; __int64
0x1800370ec  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x1800370f1  jmp     loc_180037197
0x1800370f6  mov     r14, rdi
0x1800370f9  lea     rdx, [rbp+SRWLock]
0x1800370fd  mov     [rbp+SRWLock], 0
0x180037105  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003710a  mov     rax, [r14]
0x18003710d  mov     rcx, [rbp+SRWLock]; SRWLock
0x180037111  mov     dword ptr [rax], 2
0x180037117  test    rcx, rcx
0x18003711a  jz      short loc_180037122
0x18003711c  call    cs:__imp_ReleaseSRWLockExclusive
0x180037122  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180037127  mov     rbx, [rax+8]
0x18003712b  cmp     dword ptr [rbx], 5
0x18003712e  jbe     short loc_180037197
0x180037130  mov     rcx, 400000000000h
0x18003713a  test    [rbx+10h], rcx
0x18003713e  jz      short loc_180037197
0x180037140  mov     rax, [rbx+18h]
0x180037144  and     rax, rcx
0x180037147  cmp     rax, [rbx+18h]
0x18003714b  jnz     short loc_180037197
0x18003714d  call    cs:__imp_GetCurrentThreadId
0x180037153  mov     r8, [rdi]
0x180037156  lea     rdx, byte_18017234D
0x18003715d  mov     dword ptr [rbp+SRWLock], eax
0x180037160  mov     rcx, rbx
0x180037163  mov     eax, [r8+48h]
0x180037167  add     r8, 8
0x18003716b  mov     dword ptr [rbp+var_78], eax
0x18003716e  mov     eax, 1000000h
0x180037173  mov     [rbp+var_60], rax
0x180037177  lea     rax, [rbp+SRWLock]
0x18003717b  mov     [rsp+120h+var_F0], rax
0x180037180  lea     rax, [rbp+var_78]
0x180037184  mov     [rsp+120h+var_F8], rax
0x180037189  lea     rax, [rbp+var_60]
0x18003718d  mov     [rsp+120h+var_100], rax
0x180037192  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180037197  mov     rcx, rsi
0x18003719a  lea     r11, [rsp+120h+var_10]
0x1800371a2  mov     rbx, [r11+28h]
0x1800371a6  mov     rsi, [r11+30h]
0x1800371aa  mov     rsp, r11
0x1800371ad  pop     r14
0x1800371af  pop     rdi
0x1800371b0  pop     rbp
0x1800371b1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
