# wpc::UI::Logging::MonitorUILogger::RequestException::StopActivity(void)

- ea: `0x1400952c0`
- end: `0x14009553a`
- name: `?StopActivity@RequestException@MonitorUILogger@Logging@UI@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::RequestException *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400012bc`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x14002af88`
- `0x1400952c0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14009531a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400954b8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14009531a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400954b8`
- `KERNEL32!GetCurrentThreadId` at `0x1400954cd`
- `KERNEL32!GetCurrentThreadId` at `0x1400954cd`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::RequestException::StopActivity(
        wpc::UI::Logging::MonitorUILogger::RequestException *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+C0h] [rbp-80h] BYREF
  int v10; // [rsp+C4h] [rbp-7Ch] BYREF
  int v11; // [rsp+C8h] [rbp-78h] BYREF
  int v12; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v13; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v14; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v15; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v16; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v17; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v18; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v19; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v20; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v25; // [rsp+158h] [rbp+18h] BYREF
  __int64 v26; // [rsp+160h] [rbp+20h] BYREF
  int v27; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = wpc::UI::Logging::MonitorUILogger::Provider();
    if ( *(_DWORD *)v5 > 4u )
    {
      v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v25 = v4[4];
      v14 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v26) = v4[26];
      v16 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v9 = v4[8];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v10 = *v4;
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v12 = v4[2];
      v22 = 0x1000000;
      v23[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)&unk_1400D7718,
        *((_QWORD *)this + 34) + 8LL,
        (__int64)v5,
        (__int64)v23,
        (__int64)&v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v10,
        &v19,
        (__int64)&v9,
        &v18,
        (__int64)&v27,
        &v17,
        &v16,
        (__int64)&v26,
        &v15,
        &v14,
        (__int64)&v25,
        (__int64)&SRWLock,
        &v13);
    }
  }
  else
  {
    wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = wpc::UI::Logging::MonitorUILogger::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v25 = *(_DWORD *)(v7 + 72);
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (__int64)&byte_1400D76C7,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::UI::Logging::MonitorUILogger::RequestException *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400952c0  push    rbp
0x1400952c2  push    rbx
0x1400952c3  push    rdi
0x1400952c4  lea     rbp, [rsp+10h]
0x1400952c9  sub     rsp, 130h
0x1400952d0  mov     rbx, rcx
0x1400952d3  mov     rdi, [rcx+110h]
0x1400952da  mov     eax, [rdi+48h]
0x1400952dd  test    eax, eax
0x1400952df  jns     loc_140095499
0x1400952e5  add     rdi, 50h ; 'P'
0x1400952e9  cmp     eax, [rdi+8]
0x1400952ec  jnz     loc_140095499
0x1400952f2  test    rdi, rdi
0x1400952f5  jz      loc_140095499
0x1400952fb  lea     rdx, [rbp+SRWLock]
0x1400952ff  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140095304  mov     rax, [rbx+110h]
0x14009530b  mov     dword ptr [rax], 2
0x140095311  mov     rcx, [rbp+SRWLock]; SRWLock
0x140095315  test    rcx, rcx
0x140095318  jz      short loc_140095320
0x14009531a  call    cs:__imp_ReleaseSRWLockExclusive
0x140095320  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x140095325  mov     r9, rax
0x140095328  mov     ecx, [rax]
0x14009532a  cmp     ecx, 4
0x14009532d  jbe     loc_14009551C
0x140095333  mov     rcx, [rdi+30h]
0x140095337  mov     [rbp+var_70], rcx
0x14009533b  mov     ecx, [rdi+44h]
0x14009533e  mov     dword ptr [rbp+SRWLock], ecx
0x140095341  mov     ecx, [rdi+10h]
0x140095344  mov     [rbp+arg_8], ecx
0x140095347  mov     rcx, [rdi+78h]
0x14009534b  mov     [rbp+var_68], rcx
0x14009534f  mov     rax, [rdi+70h]
0x140095353  mov     [rbp+var_60], rax
0x140095357  mov     eax, [rdi+68h]
0x14009535a  mov     dword ptr [rbp+arg_10], eax
0x14009535d  mov     rax, [rdi+60h]
0x140095361  mov     [rbp+var_58], rax
0x140095365  mov     rax, [rdi+58h]
0x140095369  mov     [rbp+var_50], rax
0x14009536d  mov     eax, [rdi+50h]
0x140095370  mov     [rbp+arg_18], eax
0x140095373  mov     rax, [rdi+48h]
0x140095377  mov     [rbp+var_48], rax
0x14009537b  mov     eax, [rdi+20h]
0x14009537e  mov     [rbp+var_80], eax
0x140095381  mov     rax, [rdi+18h]
0x140095385  mov     [rbp+var_40], rax
0x140095389  mov     eax, [rdi]
0x14009538b  mov     [rbp+var_7C], eax
0x14009538e  mov     rax, [rdi+80h]
0x140095395  mov     [rbp+var_38], rax
0x140095399  mov     eax, [rdi+40h]
0x14009539c  mov     [rbp+var_78], eax
0x14009539f  mov     rax, [rdi+38h]
0x1400953a3  mov     [rbp+var_30], rax
0x1400953a7  mov     eax, [rdi+8]
0x1400953aa  mov     [rbp+var_74], eax
0x1400953ad  mov     eax, 1000000h
0x1400953b2  mov     [rbp+var_28], rax
0x1400953b6  mov     [rbp+var_20], rax
0x1400953ba  mov     r8, [rbx+110h]
0x1400953c1  add     r8, 8
0x1400953c5  lea     rax, [rbp+var_70]
0x1400953c9  mov     [rsp+140h+var_90], rax
0x1400953d1  lea     rax, [rbp+SRWLock]
0x1400953d5  mov     [rsp+140h+var_98], rax
0x1400953dd  lea     rax, [rbp+arg_8]
0x1400953e1  mov     [rsp+140h+var_A0], rax
0x1400953e9  lea     rax, [rbp+var_68]
0x1400953ed  mov     [rsp+140h+var_A8], rax
0x1400953f5  lea     rax, [rbp+var_60]
0x1400953f9  mov     [rsp+140h+var_B0], rax
0x140095401  lea     rax, [rbp+arg_10]
0x140095405  mov     [rsp+140h+var_B8], rax
0x14009540d  lea     rax, [rbp+var_58]
0x140095411  mov     [rsp+140h+var_C0], rax
0x140095419  lea     rax, [rbp+var_50]
0x14009541d  mov     [rsp+140h+var_C8], rax
0x140095422  lea     rax, [rbp+arg_18]
0x140095426  mov     [rsp+140h+var_D0], rax
0x14009542b  lea     rax, [rbp+var_48]
0x14009542f  mov     [rsp+140h+var_D8], rax
0x140095434  lea     rax, [rbp+var_80]
0x140095438  mov     [rsp+140h+var_E0], rax
0x14009543d  lea     rax, [rbp+var_40]
0x140095441  mov     [rsp+140h+var_E8], rax
0x140095446  lea     rax, [rbp+var_7C]
0x14009544a  mov     [rsp+140h+var_F0], rax
0x14009544f  lea     rax, [rbp+var_38]
0x140095453  mov     [rsp+140h+var_F8], rax
0x140095458  lea     rax, [rbp+var_78]
0x14009545c  mov     [rsp+140h+var_100], rax
0x140095461  lea     rax, [rbp+var_30]
0x140095465  mov     [rsp+140h+var_108], rax
0x14009546a  lea     rax, [rbp+var_74]
0x14009546e  mov     [rsp+140h+var_110], rax
0x140095473  lea     rax, [rbp+var_28]
0x140095477  mov     [rsp+140h+var_118], rax
0x14009547c  lea     rax, [rbp+var_20]
0x140095480  mov     [rsp+140h+var_120], rax
0x140095485  lea     rdx, unk_1400D7718
0x14009548c  mov     rcx, r9
0x14009548f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140095494  jmp     loc_14009551C
0x140095499  lea     rdx, [rbp+SRWLock]
0x14009549d  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400954a2  mov     rax, [rbx+110h]
0x1400954a9  mov     dword ptr [rax], 2
0x1400954af  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400954b3  test    rcx, rcx
0x1400954b6  jz      short loc_1400954BE
0x1400954b8  call    cs:__imp_ReleaseSRWLockExclusive
0x1400954be  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x1400954c3  mov     rdi, rax
0x1400954c6  mov     ecx, [rax]
0x1400954c8  cmp     ecx, 4
0x1400954cb  jbe     short loc_14009551C
0x1400954cd  call    cs:__imp_GetCurrentThreadId
0x1400954d3  mov     dword ptr [rbp+SRWLock], eax
0x1400954d6  mov     r8, [rbx+110h]
0x1400954dd  mov     ecx, [r8+48h]
0x1400954e1  mov     [rbp+arg_8], ecx
0x1400954e4  mov     eax, 1000000h
0x1400954e9  mov     [rbp+arg_10], rax
0x1400954ed  add     r8, 8
0x1400954f1  lea     rax, [rbp+SRWLock]
0x1400954f5  mov     [rsp+140h+var_110], rax
0x1400954fa  lea     rax, [rbp+arg_8]
0x1400954fe  mov     [rsp+140h+var_118], rax
0x140095503  lea     rax, [rbp+arg_10]
0x140095507  mov     [rsp+140h+var_120], rax
0x14009550c  lea     rdx, byte_1400D76C7
0x140095513  mov     rcx, rdi
0x140095516  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14009551b  nop
0x14009551c  lea     rcx, [rbx+120h]; this
0x140095523  cmp     dword ptr [rcx+18h], 0
0x140095527  jz      short loc_14009552F
0x140095529  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14009552e  nop
0x14009552f  add     rsp, 130h
0x140095536  pop     rdi
0x140095537  pop     rbx
0x140095538  pop     rbp
0x140095539  retn
```
