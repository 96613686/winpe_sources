# Diagnostics::Telemetry4Diag::RunCliAnalyze::StopActivity(void)

- ea: `0x180017b50`
- end: `0x180017de6`
- name: `?StopActivity@RunCliAnalyze@Telemetry4Diag@Diagnostics@@MEAAXXZ`
- size: `662`
- prototype: `void __fastcall(Diagnostics::Telemetry4Diag::RunCliAnalyze *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000109c`
- `0x1800017ec`
- `0x1800080f8`
- `0x180017ad8`
- `0x180017b50`
- `0x180017e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017bbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017d4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017bbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017d4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017d7d`

## pseudocode

```c
void __fastcall Diagnostics::Telemetry4Diag::RunCliAnalyze::StopActivity(
        Diagnostics::Telemetry4Diag::RunCliAnalyze *this)
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
          (int)&word_180171F46,
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
      (int)byte_18017206B,
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
0x180017b50  mov     [rsp-8+arg_8], rbx
0x180017b55  mov     [rsp-8+arg_10], rsi
0x180017b5a  push    rbp
0x180017b5b  push    rdi
0x180017b5c  push    r14
0x180017b5e  lea     rbp, [rsp+10h]
0x180017b63  sub     rsp, 110h
0x180017b6a  lea     rdi, [rcx+110h]
0x180017b71  mov     rsi, rcx
0x180017b74  mov     rbx, [rdi]
0x180017b77  mov     eax, [rbx+48h]
0x180017b7a  test    eax, eax
0x180017b7c  jns     loc_180017D26
0x180017b82  add     rbx, 50h ; 'P'
0x180017b86  cmp     eax, [rbx+8]
0x180017b89  jnz     loc_180017D26
0x180017b8f  mov     r14, rdi
0x180017b92  test    rbx, rbx
0x180017b95  jz      loc_180017D29
0x180017b9b  lea     rdx, [rbp+SRWLock]
0x180017b9f  mov     [rbp+SRWLock], 0
0x180017ba7  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017bac  mov     rax, [rdi]
0x180017baf  mov     rcx, [rbp+SRWLock]; SRWLock
0x180017bb3  mov     dword ptr [rax], 2
0x180017bb9  test    rcx, rcx
0x180017bbc  jz      short loc_180017BC4
0x180017bbe  call    cs:__imp_ReleaseSRWLockExclusive
0x180017bc4  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180017bc9  mov     r9, [rax+8]
0x180017bcd  cmp     dword ptr [r9], 5
0x180017bd1  jbe     loc_180017DC7
0x180017bd7  mov     rcx, 400000000000h
0x180017be1  test    [r9+10h], rcx
0x180017be5  jz      loc_180017DC7
0x180017beb  mov     rax, [r9+18h]
0x180017bef  and     rax, rcx
0x180017bf2  cmp     rax, [r9+18h]
0x180017bf6  jnz     loc_180017DC7
0x180017bfc  mov     rax, [rbx+78h]
0x180017c00  lea     rdx, word_180171F46; int
0x180017c07  mov     r8, [rdi]
0x180017c0a  mov     rcx, r9; int
0x180017c0d  mov     [rbp+var_58], rax
0x180017c11  add     r8, 8; int
0x180017c15  mov     rax, [rbx+70h]
0x180017c19  mov     [rbp+var_50], rax
0x180017c1d  mov     eax, [rbx+68h]
0x180017c20  mov     dword ptr [rbp+var_78+4], eax
0x180017c23  mov     rax, [rbx+60h]
0x180017c27  mov     [rbp+var_48], rax
0x180017c2b  mov     rax, [rbx+58h]
0x180017c2f  mov     [rbp+var_40], rax
0x180017c33  mov     eax, [rbx+50h]
0x180017c36  mov     dword ptr [rbp+var_70], eax
0x180017c39  mov     rax, [rbx+48h]
0x180017c3d  mov     [rbp+var_38], rax
0x180017c41  mov     eax, [rbx+20h]
0x180017c44  mov     dword ptr [rbp+var_70+4], eax
0x180017c47  mov     rax, [rbx+18h]
0x180017c4b  mov     [rbp+var_30], rax
0x180017c4f  mov     eax, [rbx]
0x180017c51  mov     dword ptr [rbp+var_68], eax
0x180017c54  mov     rax, [rbx+80h]
0x180017c5b  mov     [rbp+var_28], rax
0x180017c5f  mov     eax, [rbx+40h]
0x180017c62  mov     dword ptr [rbp+var_78], eax
0x180017c65  mov     rax, [rbx+38h]
0x180017c69  mov     [rbp+var_20], rax
0x180017c6d  mov     eax, [rbx+8]
0x180017c70  mov     dword ptr [rbp+SRWLock], eax
0x180017c73  mov     eax, 1000000h
0x180017c78  mov     [rbp+var_18], rax
0x180017c7c  mov     [rbp+var_60], rax
0x180017c80  lea     rax, [rbp+var_58]
0x180017c84  mov     [rsp+120h+var_88], rax; __int64
0x180017c8c  lea     rax, [rbp+var_50]
0x180017c90  mov     [rsp+120h+var_90], rax; __int64
0x180017c98  lea     rax, [rbp+var_78+4]
0x180017c9c  mov     [rsp+120h+var_98], rax; __int64
0x180017ca4  lea     rax, [rbp+var_48]
0x180017ca8  mov     [rsp+120h+var_A0], rax; __int64
0x180017cb0  lea     rax, [rbp+var_40]
0x180017cb4  mov     [rsp+120h+var_A8], rax; __int64
0x180017cb9  lea     rax, [rbp+var_70]
0x180017cbd  mov     [rsp+120h+var_B0], rax; __int64
0x180017cc2  lea     rax, [rbp+var_38]
0x180017cc6  mov     [rsp+120h+var_B8], rax; __int64
0x180017ccb  lea     rax, [rbp+var_70+4]
0x180017ccf  mov     [rsp+120h+var_C0], rax; __int64
0x180017cd4  lea     rax, [rbp+var_30]
0x180017cd8  mov     [rsp+120h+var_C8], rax; __int64
0x180017cdd  lea     rax, [rbp+var_68]
0x180017ce1  mov     [rsp+120h+var_D0], rax; __int64
0x180017ce6  lea     rax, [rbp+var_28]
0x180017cea  mov     [rsp+120h+var_D8], rax; __int64
0x180017cef  lea     rax, [rbp+var_78]
0x180017cf3  mov     [rsp+120h+var_E0], rax; __int64
0x180017cf8  lea     rax, [rbp+var_20]
0x180017cfc  mov     [rsp+120h+var_E8], rax; __int64
0x180017d01  lea     rax, [rbp+SRWLock]
0x180017d05  mov     [rsp+120h+var_F0], rax; __int64
0x180017d0a  lea     rax, [rbp+var_18]
0x180017d0e  mov     [rsp+120h+var_F8], rax; __int64
0x180017d13  lea     rax, [rbp+var_60]
0x180017d17  mov     [rsp+120h+var_100], rax; __int64
0x180017d1c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180017d21  jmp     loc_180017DC7
0x180017d26  mov     r14, rdi
0x180017d29  lea     rdx, [rbp+SRWLock]
0x180017d2d  mov     [rbp+SRWLock], 0
0x180017d35  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017d3a  mov     rax, [r14]
0x180017d3d  mov     rcx, [rbp+SRWLock]; SRWLock
0x180017d41  mov     dword ptr [rax], 2
0x180017d47  test    rcx, rcx
0x180017d4a  jz      short loc_180017D52
0x180017d4c  call    cs:__imp_ReleaseSRWLockExclusive
0x180017d52  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180017d57  mov     rbx, [rax+8]
0x180017d5b  cmp     dword ptr [rbx], 5
0x180017d5e  jbe     short loc_180017DC7
0x180017d60  mov     rcx, 400000000000h
0x180017d6a  test    [rbx+10h], rcx
0x180017d6e  jz      short loc_180017DC7
0x180017d70  mov     rax, [rbx+18h]
0x180017d74  and     rax, rcx
0x180017d77  cmp     rax, [rbx+18h]
0x180017d7b  jnz     short loc_180017DC7
0x180017d7d  call    cs:__imp_GetCurrentThreadId
0x180017d83  mov     r8, [rdi]
0x180017d86  lea     rdx, byte_18017206B
0x180017d8d  mov     dword ptr [rbp+SRWLock], eax
0x180017d90  mov     rcx, rbx
0x180017d93  mov     eax, [r8+48h]
0x180017d97  add     r8, 8
0x180017d9b  mov     dword ptr [rbp+var_78], eax
0x180017d9e  mov     eax, 1000000h
0x180017da3  mov     [rbp+var_60], rax
0x180017da7  lea     rax, [rbp+SRWLock]
0x180017dab  mov     [rsp+120h+var_F0], rax
0x180017db0  lea     rax, [rbp+var_78]
0x180017db4  mov     [rsp+120h+var_F8], rax
0x180017db9  lea     rax, [rbp+var_60]
0x180017dbd  mov     [rsp+120h+var_100], rax
0x180017dc2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017dc7  mov     rcx, rsi
0x180017dca  lea     r11, [rsp+120h+var_10]
0x180017dd2  mov     rbx, [r11+28h]
0x180017dd6  mov     rsi, [r11+30h]
0x180017dda  mov     rsp, r11
0x180017ddd  pop     r14
0x180017ddf  pop     rdi
0x180017de0  pop     rbp
0x180017de1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
