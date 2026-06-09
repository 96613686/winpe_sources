# Diagnostics::Telemetry4Diag::RunAnalyzerGroup::StopActivity(void)

- ea: `0x180036740`
- end: `0x1800369d6`
- name: `?StopActivity@RunAnalyzerGroup@Telemetry4Diag@Diagnostics@@MEAAXXZ`
- size: `662`
- prototype: `void __fastcall(Diagnostics::Telemetry4Diag::RunAnalyzerGroup *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000109c`
- `0x1800017ec`
- `0x1800080f8`
- `0x180017ad8`
- `0x180017e80`
- `0x180036740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800367ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003693c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800367ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003693c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003696d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003696d`

## pseudocode

```c
void __fastcall Diagnostics::Telemetry4Diag::RunAnalyzerGroup::StopActivity(
        Diagnostics::Telemetry4Diag::RunAnalyzerGroup *this)
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
          (int)&byte_18017274D,
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
      (int)&dword_1801726FC,
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
0x180036740  mov     [rsp-8+arg_8], rbx
0x180036745  mov     [rsp-8+arg_10], rsi
0x18003674a  push    rbp
0x18003674b  push    rdi
0x18003674c  push    r14
0x18003674e  lea     rbp, [rsp+10h]
0x180036753  sub     rsp, 110h
0x18003675a  lea     rdi, [rcx+110h]
0x180036761  mov     rsi, rcx
0x180036764  mov     rbx, [rdi]
0x180036767  mov     eax, [rbx+48h]
0x18003676a  test    eax, eax
0x18003676c  jns     loc_180036916
0x180036772  add     rbx, 50h ; 'P'
0x180036776  cmp     eax, [rbx+8]
0x180036779  jnz     loc_180036916
0x18003677f  mov     r14, rdi
0x180036782  test    rbx, rbx
0x180036785  jz      loc_180036919
0x18003678b  lea     rdx, [rbp+SRWLock]
0x18003678f  mov     [rbp+SRWLock], 0
0x180036797  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003679c  mov     rax, [rdi]
0x18003679f  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800367a3  mov     dword ptr [rax], 2
0x1800367a9  test    rcx, rcx
0x1800367ac  jz      short loc_1800367B4
0x1800367ae  call    cs:__imp_ReleaseSRWLockExclusive
0x1800367b4  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x1800367b9  mov     r9, [rax+8]
0x1800367bd  cmp     dword ptr [r9], 5
0x1800367c1  jbe     loc_1800369B7
0x1800367c7  mov     rcx, 400000000000h
0x1800367d1  test    [r9+10h], rcx
0x1800367d5  jz      loc_1800369B7
0x1800367db  mov     rax, [r9+18h]
0x1800367df  and     rax, rcx
0x1800367e2  cmp     rax, [r9+18h]
0x1800367e6  jnz     loc_1800369B7
0x1800367ec  mov     rax, [rbx+78h]
0x1800367f0  lea     rdx, byte_18017274D; int
0x1800367f7  mov     r8, [rdi]
0x1800367fa  mov     rcx, r9; int
0x1800367fd  mov     [rbp+var_58], rax
0x180036801  add     r8, 8; int
0x180036805  mov     rax, [rbx+70h]
0x180036809  mov     [rbp+var_50], rax
0x18003680d  mov     eax, [rbx+68h]
0x180036810  mov     dword ptr [rbp+var_78+4], eax
0x180036813  mov     rax, [rbx+60h]
0x180036817  mov     [rbp+var_48], rax
0x18003681b  mov     rax, [rbx+58h]
0x18003681f  mov     [rbp+var_40], rax
0x180036823  mov     eax, [rbx+50h]
0x180036826  mov     dword ptr [rbp+var_70], eax
0x180036829  mov     rax, [rbx+48h]
0x18003682d  mov     [rbp+var_38], rax
0x180036831  mov     eax, [rbx+20h]
0x180036834  mov     dword ptr [rbp+var_70+4], eax
0x180036837  mov     rax, [rbx+18h]
0x18003683b  mov     [rbp+var_30], rax
0x18003683f  mov     eax, [rbx]
0x180036841  mov     dword ptr [rbp+var_68], eax
0x180036844  mov     rax, [rbx+80h]
0x18003684b  mov     [rbp+var_28], rax
0x18003684f  mov     eax, [rbx+40h]
0x180036852  mov     dword ptr [rbp+var_78], eax
0x180036855  mov     rax, [rbx+38h]
0x180036859  mov     [rbp+var_20], rax
0x18003685d  mov     eax, [rbx+8]
0x180036860  mov     dword ptr [rbp+SRWLock], eax
0x180036863  mov     eax, 1000000h
0x180036868  mov     [rbp+var_18], rax
0x18003686c  mov     [rbp+var_60], rax
0x180036870  lea     rax, [rbp+var_58]
0x180036874  mov     [rsp+120h+var_88], rax; __int64
0x18003687c  lea     rax, [rbp+var_50]
0x180036880  mov     [rsp+120h+var_90], rax; __int64
0x180036888  lea     rax, [rbp+var_78+4]
0x18003688c  mov     [rsp+120h+var_98], rax; __int64
0x180036894  lea     rax, [rbp+var_48]
0x180036898  mov     [rsp+120h+var_A0], rax; __int64
0x1800368a0  lea     rax, [rbp+var_40]
0x1800368a4  mov     [rsp+120h+var_A8], rax; __int64
0x1800368a9  lea     rax, [rbp+var_70]
0x1800368ad  mov     [rsp+120h+var_B0], rax; __int64
0x1800368b2  lea     rax, [rbp+var_38]
0x1800368b6  mov     [rsp+120h+var_B8], rax; __int64
0x1800368bb  lea     rax, [rbp+var_70+4]
0x1800368bf  mov     [rsp+120h+var_C0], rax; __int64
0x1800368c4  lea     rax, [rbp+var_30]
0x1800368c8  mov     [rsp+120h+var_C8], rax; __int64
0x1800368cd  lea     rax, [rbp+var_68]
0x1800368d1  mov     [rsp+120h+var_D0], rax; __int64
0x1800368d6  lea     rax, [rbp+var_28]
0x1800368da  mov     [rsp+120h+var_D8], rax; __int64
0x1800368df  lea     rax, [rbp+var_78]
0x1800368e3  mov     [rsp+120h+var_E0], rax; __int64
0x1800368e8  lea     rax, [rbp+var_20]
0x1800368ec  mov     [rsp+120h+var_E8], rax; __int64
0x1800368f1  lea     rax, [rbp+SRWLock]
0x1800368f5  mov     [rsp+120h+var_F0], rax; __int64
0x1800368fa  lea     rax, [rbp+var_18]
0x1800368fe  mov     [rsp+120h+var_F8], rax; __int64
0x180036903  lea     rax, [rbp+var_60]
0x180036907  mov     [rsp+120h+var_100], rax; __int64
0x18003690c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180036911  jmp     loc_1800369B7
0x180036916  mov     r14, rdi
0x180036919  lea     rdx, [rbp+SRWLock]
0x18003691d  mov     [rbp+SRWLock], 0
0x180036925  call    ?LockExclusive@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003692a  mov     rax, [r14]
0x18003692d  mov     rcx, [rbp+SRWLock]; SRWLock
0x180036931  mov     dword ptr [rax], 2
0x180036937  test    rcx, rcx
0x18003693a  jz      short loc_180036942
0x18003693c  call    cs:__imp_ReleaseSRWLockExclusive
0x180036942  call    ?Instance@Telemetry4Diag@Diagnostics@@KAPEAV12@XZ; Diagnostics::Telemetry4Diag::Instance(void)
0x180036947  mov     rbx, [rax+8]
0x18003694b  cmp     dword ptr [rbx], 5
0x18003694e  jbe     short loc_1800369B7
0x180036950  mov     rcx, 400000000000h
0x18003695a  test    [rbx+10h], rcx
0x18003695e  jz      short loc_1800369B7
0x180036960  mov     rax, [rbx+18h]
0x180036964  and     rax, rcx
0x180036967  cmp     rax, [rbx+18h]
0x18003696b  jnz     short loc_1800369B7
0x18003696d  call    cs:__imp_GetCurrentThreadId
0x180036973  mov     r8, [rdi]
0x180036976  lea     rdx, dword_1801726FC
0x18003697d  mov     dword ptr [rbp+SRWLock], eax
0x180036980  mov     rcx, rbx
0x180036983  mov     eax, [r8+48h]
0x180036987  add     r8, 8
0x18003698b  mov     dword ptr [rbp+var_78], eax
0x18003698e  mov     eax, 1000000h
0x180036993  mov     [rbp+var_60], rax
0x180036997  lea     rax, [rbp+SRWLock]
0x18003699b  mov     [rsp+120h+var_F0], rax
0x1800369a0  lea     rax, [rbp+var_78]
0x1800369a4  mov     [rsp+120h+var_F8], rax
0x1800369a9  lea     rax, [rbp+var_60]
0x1800369ad  mov     [rsp+120h+var_100], rax
0x1800369b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800369b7  mov     rcx, rsi
0x1800369ba  lea     r11, [rsp+120h+var_10]
0x1800369c2  mov     rbx, [r11+28h]
0x1800369c6  mov     rsi, [r11+30h]
0x1800369ca  mov     rsp, r11
0x1800369cd  pop     r14
0x1800369cf  pop     rdi
0x1800369d0  pop     rbp
0x1800369d1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetry4Diag@Diagnostics@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
