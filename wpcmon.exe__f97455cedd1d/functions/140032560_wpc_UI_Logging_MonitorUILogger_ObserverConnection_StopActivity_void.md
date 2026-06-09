# wpc::UI::Logging::MonitorUILogger::ObserverConnection::StopActivity(void)

- ea: `0x140032560`
- end: `0x1400327da`
- name: `?StopActivity@ObserverConnection@MonitorUILogger@Logging@UI@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::ObserverConnection *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400012bc`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x14002af88`
- `0x140032560`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400325ba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140032758`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400325ba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140032758`
- `KERNEL32!GetCurrentThreadId` at `0x14003276d`
- `KERNEL32!GetCurrentThreadId` at `0x14003276d`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::ObserverConnection::StopActivity(
        wpc::UI::Logging::MonitorUILogger::ObserverConnection *this)
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
        (__int64)byte_1400D5B13,
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
        (__int64)&unk_1400D5AC0,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::UI::Logging::MonitorUILogger::ObserverConnection *)((char *)this + 288));
}

```

## disassembly

```asm
0x140032560  push    rbp
0x140032562  push    rbx
0x140032563  push    rdi
0x140032564  lea     rbp, [rsp+10h]
0x140032569  sub     rsp, 130h
0x140032570  mov     rbx, rcx
0x140032573  mov     rdi, [rcx+110h]
0x14003257a  mov     eax, [rdi+48h]
0x14003257d  test    eax, eax
0x14003257f  jns     loc_140032739
0x140032585  add     rdi, 50h ; 'P'
0x140032589  cmp     eax, [rdi+8]
0x14003258c  jnz     loc_140032739
0x140032592  test    rdi, rdi
0x140032595  jz      loc_140032739
0x14003259b  lea     rdx, [rbp+SRWLock]
0x14003259f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400325a4  mov     rax, [rbx+110h]
0x1400325ab  mov     dword ptr [rax], 2
0x1400325b1  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400325b5  test    rcx, rcx
0x1400325b8  jz      short loc_1400325C0
0x1400325ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1400325c0  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x1400325c5  mov     r9, rax
0x1400325c8  mov     ecx, [rax]
0x1400325ca  cmp     ecx, 4
0x1400325cd  jbe     loc_1400327BC
0x1400325d3  mov     rcx, [rdi+30h]
0x1400325d7  mov     [rbp+var_70], rcx
0x1400325db  mov     ecx, [rdi+44h]
0x1400325de  mov     dword ptr [rbp+SRWLock], ecx
0x1400325e1  mov     ecx, [rdi+10h]
0x1400325e4  mov     [rbp+arg_8], ecx
0x1400325e7  mov     rcx, [rdi+78h]
0x1400325eb  mov     [rbp+var_68], rcx
0x1400325ef  mov     rax, [rdi+70h]
0x1400325f3  mov     [rbp+var_60], rax
0x1400325f7  mov     eax, [rdi+68h]
0x1400325fa  mov     dword ptr [rbp+arg_10], eax
0x1400325fd  mov     rax, [rdi+60h]
0x140032601  mov     [rbp+var_58], rax
0x140032605  mov     rax, [rdi+58h]
0x140032609  mov     [rbp+var_50], rax
0x14003260d  mov     eax, [rdi+50h]
0x140032610  mov     [rbp+arg_18], eax
0x140032613  mov     rax, [rdi+48h]
0x140032617  mov     [rbp+var_48], rax
0x14003261b  mov     eax, [rdi+20h]
0x14003261e  mov     [rbp+var_80], eax
0x140032621  mov     rax, [rdi+18h]
0x140032625  mov     [rbp+var_40], rax
0x140032629  mov     eax, [rdi]
0x14003262b  mov     [rbp+var_7C], eax
0x14003262e  mov     rax, [rdi+80h]
0x140032635  mov     [rbp+var_38], rax
0x140032639  mov     eax, [rdi+40h]
0x14003263c  mov     [rbp+var_78], eax
0x14003263f  mov     rax, [rdi+38h]
0x140032643  mov     [rbp+var_30], rax
0x140032647  mov     eax, [rdi+8]
0x14003264a  mov     [rbp+var_74], eax
0x14003264d  mov     eax, 1000000h
0x140032652  mov     [rbp+var_28], rax
0x140032656  mov     [rbp+var_20], rax
0x14003265a  mov     r8, [rbx+110h]
0x140032661  add     r8, 8
0x140032665  lea     rax, [rbp+var_70]
0x140032669  mov     [rsp+140h+var_90], rax
0x140032671  lea     rax, [rbp+SRWLock]
0x140032675  mov     [rsp+140h+var_98], rax
0x14003267d  lea     rax, [rbp+arg_8]
0x140032681  mov     [rsp+140h+var_A0], rax
0x140032689  lea     rax, [rbp+var_68]
0x14003268d  mov     [rsp+140h+var_A8], rax
0x140032695  lea     rax, [rbp+var_60]
0x140032699  mov     [rsp+140h+var_B0], rax
0x1400326a1  lea     rax, [rbp+arg_10]
0x1400326a5  mov     [rsp+140h+var_B8], rax
0x1400326ad  lea     rax, [rbp+var_58]
0x1400326b1  mov     [rsp+140h+var_C0], rax
0x1400326b9  lea     rax, [rbp+var_50]
0x1400326bd  mov     [rsp+140h+var_C8], rax
0x1400326c2  lea     rax, [rbp+arg_18]
0x1400326c6  mov     [rsp+140h+var_D0], rax
0x1400326cb  lea     rax, [rbp+var_48]
0x1400326cf  mov     [rsp+140h+var_D8], rax
0x1400326d4  lea     rax, [rbp+var_80]
0x1400326d8  mov     [rsp+140h+var_E0], rax
0x1400326dd  lea     rax, [rbp+var_40]
0x1400326e1  mov     [rsp+140h+var_E8], rax
0x1400326e6  lea     rax, [rbp+var_7C]
0x1400326ea  mov     [rsp+140h+var_F0], rax
0x1400326ef  lea     rax, [rbp+var_38]
0x1400326f3  mov     [rsp+140h+var_F8], rax
0x1400326f8  lea     rax, [rbp+var_78]
0x1400326fc  mov     [rsp+140h+var_100], rax
0x140032701  lea     rax, [rbp+var_30]
0x140032705  mov     [rsp+140h+var_108], rax
0x14003270a  lea     rax, [rbp+var_74]
0x14003270e  mov     [rsp+140h+var_110], rax
0x140032713  lea     rax, [rbp+var_28]
0x140032717  mov     [rsp+140h+var_118], rax
0x14003271c  lea     rax, [rbp+var_20]
0x140032720  mov     [rsp+140h+var_120], rax
0x140032725  lea     rdx, byte_1400D5B13
0x14003272c  mov     rcx, r9
0x14003272f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140032734  jmp     loc_1400327BC
0x140032739  lea     rdx, [rbp+SRWLock]
0x14003273d  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140032742  mov     rax, [rbx+110h]
0x140032749  mov     dword ptr [rax], 2
0x14003274f  mov     rcx, [rbp+SRWLock]; SRWLock
0x140032753  test    rcx, rcx
0x140032756  jz      short loc_14003275E
0x140032758  call    cs:__imp_ReleaseSRWLockExclusive
0x14003275e  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x140032763  mov     rdi, rax
0x140032766  mov     ecx, [rax]
0x140032768  cmp     ecx, 4
0x14003276b  jbe     short loc_1400327BC
0x14003276d  call    cs:__imp_GetCurrentThreadId
0x140032773  mov     dword ptr [rbp+SRWLock], eax
0x140032776  mov     r8, [rbx+110h]
0x14003277d  mov     ecx, [r8+48h]
0x140032781  mov     [rbp+arg_8], ecx
0x140032784  mov     eax, 1000000h
0x140032789  mov     [rbp+arg_10], rax
0x14003278d  add     r8, 8
0x140032791  lea     rax, [rbp+SRWLock]
0x140032795  mov     [rsp+140h+var_110], rax
0x14003279a  lea     rax, [rbp+arg_8]
0x14003279e  mov     [rsp+140h+var_118], rax
0x1400327a3  lea     rax, [rbp+arg_10]
0x1400327a7  mov     [rsp+140h+var_120], rax
0x1400327ac  lea     rdx, unk_1400D5AC0
0x1400327b3  mov     rcx, rdi
0x1400327b6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400327bb  nop
0x1400327bc  lea     rcx, [rbx+120h]; this
0x1400327c3  cmp     dword ptr [rcx+18h], 0
0x1400327c7  jz      short loc_1400327CF
0x1400327c9  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1400327ce  nop
0x1400327cf  add     rsp, 130h
0x1400327d6  pop     rdi
0x1400327d7  pop     rbx
0x1400327d8  pop     rbp
0x1400327d9  retn
```
