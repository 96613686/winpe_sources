# Diagnostics::Telemetry4Diag::RunAnalyzer::StopActivity(void)

- ea: `0x180035e30`
- end: `0x1800360c6`
- name: `?StopActivity@RunAnalyzer@Telemetry4Diag@Diagnostics@@MEAAXXZ`
- size: `662`
- prototype: `void __fastcall(Diagnostics::Telemetry4Diag::RunAnalyzer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000109c`
- `0x1800017ec`
- `0x1800080f8`
- `0x180017ad8`
- `0x180017e80`
- `0x180035e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035e9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003602c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035e9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003602c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003605d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003605d`

## pseudocode

```c
void __fastcall Diagnostics::Telemetry4Diag::RunAnalyzer::StopActivity(Diagnostics::Telemetry4Diag::RunAnalyzer *this)
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
          (int)&unk_180172B10,
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
      (int)&dword_180172AC4,
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
0x180035e30  mov     [rsp-8+arg_8], rbx
0x180035e35  mov     [rsp-8+arg_10], rsi
0x180035e3a  push    rbp
0x180035e3b  push    rdi
0x180035e3c  push    r14
0x180035e3e  lea     rbp, [rsp+10h]
0x180035e43  sub     rsp, 110h
0x180035e4a  lea     rdi, [rcx+110h]
0x180035e51  mov     rsi, rcx
0x180035e54  mov     rbx, [rdi]
0x180035e57  mov     eax, [rbx+48h]
0x180035e5a  test    eax, eax
0x180035e5c  jns     loc_180036006
0x180035e62  add     rbx, 50h ; 'P'
0x180035e66  cmp     eax, [rbx+8]
0x180035e69  jnz     loc_180036006
0x180035e6f  mov     r14, rdi
0x180035e72  test    rbx, rbx
0x180035e75  jz      loc_180036009
0x180035e7b  lea     rdx, [rbp+SRWLock]
0x180035e7f  mov     [rbp+SRWLock], 0
0x180035e87  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180035e8c  mov     rax, [rdi]
0x180035e8f  mov     rcx, [rbp+SRWLock]; SRWLock
0x180035e93  mov     dword ptr [rax], 2
0x180035e99  test    rcx, rcx
0x180035e9c  jz      short loc_180035EA4
0x180035e9e  call    cs:__imp_ReleaseSRWLockExclusive
0x180035ea4  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180035ea9  mov     r9, [rax+8]
0x180035ead  cmp     dword ptr [r9], 5
0x180035eb1  jbe     loc_1800360A7
0x180035eb7  mov     rcx, 400000000000h
0x180035ec1  test    [r9+10h], rcx
0x180035ec5  jz      loc_1800360A7
0x180035ecb  mov     rax, [r9+18h]
0x180035ecf  and     rax, rcx
0x180035ed2  cmp     rax, [r9+18h]
0x180035ed6  jnz     loc_1800360A7
0x180035edc  mov     rax, [rbx+78h]
0x180035ee0  lea     rdx, unk_180172B10; int
0x180035ee7  mov     r8, [rdi]
0x180035eea  mov     rcx, r9; int
0x180035eed  mov     [rbp+var_58], rax
0x180035ef1  add     r8, 8; int
0x180035ef5  mov     rax, [rbx+70h]
0x180035ef9  mov     [rbp+var_50], rax
0x180035efd  mov     eax, [rbx+68h]
0x180035f00  mov     dword ptr [rbp+var_78+4], eax
0x180035f03  mov     rax, [rbx+60h]
0x180035f07  mov     [rbp+var_48], rax
0x180035f0b  mov     rax, [rbx+58h]
0x180035f0f  mov     [rbp+var_40], rax
0x180035f13  mov     eax, [rbx+50h]
0x180035f16  mov     dword ptr [rbp+var_70], eax
0x180035f19  mov     rax, [rbx+48h]
0x180035f1d  mov     [rbp+var_38], rax
0x180035f21  mov     eax, [rbx+20h]
0x180035f24  mov     dword ptr [rbp+var_70+4], eax
0x180035f27  mov     rax, [rbx+18h]
0x180035f2b  mov     [rbp+var_30], rax
0x180035f2f  mov     eax, [rbx]
0x180035f31  mov     dword ptr [rbp+var_68], eax
0x180035f34  mov     rax, [rbx+80h]
0x180035f3b  mov     [rbp+var_28], rax
0x180035f3f  mov     eax, [rbx+40h]
0x180035f42  mov     dword ptr [rbp+var_78], eax
0x180035f45  mov     rax, [rbx+38h]
0x180035f49  mov     [rbp+var_20], rax
0x180035f4d  mov     eax, [rbx+8]
0x180035f50  mov     dword ptr [rbp+SRWLock], eax
0x180035f53  mov     eax, 1000000h
0x180035f58  mov     [rbp+var_18], rax
0x180035f5c  mov     [rbp+var_60], rax
0x180035f60  lea     rax, [rbp+var_58]
0x180035f64  mov     [rsp+120h+var_88], rax; __int64
0x180035f6c  lea     rax, [rbp+var_50]
0x180035f70  mov     [rsp+120h+var_90], rax; __int64
0x180035f78  lea     rax, [rbp+var_78+4]
0x180035f7c  mov     [rsp+120h+var_98], rax; __int64
0x180035f84  lea     rax, [rbp+var_48]
0x180035f88  mov     [rsp+120h+var_A0], rax; __int64
0x180035f90  lea     rax, [rbp+var_40]
0x180035f94  mov     [rsp+120h+var_A8], rax; __int64
0x180035f99  lea     rax, [rbp+var_70]
0x180035f9d  mov     [rsp+120h+var_B0], rax; __int64
0x180035fa2  lea     rax, [rbp+var_38]
0x180035fa6  mov     [rsp+120h+var_B8], rax; __int64
0x180035fab  lea     rax, [rbp+var_70+4]
0x180035faf  mov     [rsp+120h+var_C0], rax; __int64
0x180035fb4  lea     rax, [rbp+var_30]
0x180035fb8  mov     [rsp+120h+var_C8], rax; __int64
0x180035fbd  lea     rax, [rbp+var_68]
0x180035fc1  mov     [rsp+120h+var_D0], rax; __int64
0x180035fc6  lea     rax, [rbp+var_28]
0x180035fca  mov     [rsp+120h+var_D8], rax; __int64
0x180035fcf  lea     rax, [rbp+var_78]
0x180035fd3  mov     [rsp+120h+var_E0], rax; __int64
0x180035fd8  lea     rax, [rbp+var_20]
0x180035fdc  mov     [rsp+120h+var_E8], rax; __int64
0x180035fe1  lea     rax, [rbp+SRWLock]
0x180035fe5  mov     [rsp+120h+var_F0], rax; __int64
0x180035fea  lea     rax, [rbp+var_18]
0x180035fee  mov     [rsp+120h+var_F8], rax; __int64
0x180035ff3  lea     rax, [rbp+var_60]
0x180035ff7  mov     [rsp+120h+var_100], rax; __int64
0x180035ffc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180036001  jmp     loc_1800360A7
0x180036006  mov     r14, rdi
0x180036009  lea     rdx, [rbp+SRWLock]
0x18003600d  mov     [rbp+SRWLock], 0
0x180036015  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003601a  mov     rax, [r14]
0x18003601d  mov     rcx, [rbp+SRWLock]; SRWLock
0x180036021  mov     dword ptr [rax], 2
0x180036027  test    rcx, rcx
0x18003602a  jz      short loc_180036032
0x18003602c  call    cs:__imp_ReleaseSRWLockExclusive
0x180036032  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180036037  mov     rbx, [rax+8]
0x18003603b  cmp     dword ptr [rbx], 5
0x18003603e  jbe     short loc_1800360A7
0x180036040  mov     rcx, 400000000000h
0x18003604a  test    [rbx+10h], rcx
0x18003604e  jz      short loc_1800360A7
0x180036050  mov     rax, [rbx+18h]
0x180036054  and     rax, rcx
0x180036057  cmp     rax, [rbx+18h]
0x18003605b  jnz     short loc_1800360A7
0x18003605d  call    cs:__imp_GetCurrentThreadId
0x180036063  mov     r8, [rdi]
0x180036066  lea     rdx, dword_180172AC4
0x18003606d  mov     dword ptr [rbp+SRWLock], eax
0x180036070  mov     rcx, rbx
0x180036073  mov     eax, [r8+48h]
0x180036077  add     r8, 8
0x18003607b  mov     dword ptr [rbp+var_78], eax
0x18003607e  mov     eax, 1000000h
0x180036083  mov     [rbp+var_60], rax
0x180036087  lea     rax, [rbp+SRWLock]
0x18003608b  mov     [rsp+120h+var_F0], rax
0x180036090  lea     rax, [rbp+var_78]
0x180036094  mov     [rsp+120h+var_F8], rax
0x180036099  lea     rax, [rbp+var_60]
0x18003609d  mov     [rsp+120h+var_100], rax
0x1800360a2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800360a7  mov     rcx, rsi
0x1800360aa  lea     r11, [rsp+120h+var_10]
0x1800360b2  mov     rbx, [r11+28h]
0x1800360b6  mov     rsi, [r11+30h]
0x1800360ba  mov     rsp, r11
0x1800360bd  pop     r14
0x1800360bf  pop     rdi
0x1800360c0  pop     rbp
0x1800360c1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
