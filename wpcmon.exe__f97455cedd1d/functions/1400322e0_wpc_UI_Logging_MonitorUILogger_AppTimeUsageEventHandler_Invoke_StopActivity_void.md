# wpc::UI::Logging::MonitorUILogger::AppTimeUsageEventHandler_Invoke::StopActivity(void)

- ea: `0x1400322e0`
- end: `0x14003255a`
- name: `?StopActivity@AppTimeUsageEventHandler_Invoke@MonitorUILogger@Logging@UI@wpc@@MEAAXXZ`
- size: `634`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::AppTimeUsageEventHandler_Invoke *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1400012bc`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x14002af88`
- `0x1400322e0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14003233a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400324d8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14003233a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400324d8`
- `KERNEL32!GetCurrentThreadId` at `0x1400324ed`
- `KERNEL32!GetCurrentThreadId` at `0x1400324ed`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::AppTimeUsageEventHandler_Invoke::StopActivity(
        wpc::UI::Logging::MonitorUILogger::AppTimeUsageEventHandler_Invoke *this)
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
        (__int64)&dword_1400D591C,
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
        (__int64)&dword_1400D58BC,
        v7 + 8,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::UI::Logging::MonitorUILogger::AppTimeUsageEventHandler_Invoke *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400322e0  push    rbp
0x1400322e2  push    rbx
0x1400322e3  push    rdi
0x1400322e4  lea     rbp, [rsp+10h]
0x1400322e9  sub     rsp, 130h
0x1400322f0  mov     rbx, rcx
0x1400322f3  mov     rdi, [rcx+110h]
0x1400322fa  mov     eax, [rdi+48h]
0x1400322fd  test    eax, eax
0x1400322ff  jns     loc_1400324B9
0x140032305  add     rdi, 50h ; 'P'
0x140032309  cmp     eax, [rdi+8]
0x14003230c  jnz     loc_1400324B9
0x140032312  test    rdi, rdi
0x140032315  jz      loc_1400324B9
0x14003231b  lea     rdx, [rbp+SRWLock]
0x14003231f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140032324  mov     rax, [rbx+110h]
0x14003232b  mov     dword ptr [rax], 2
0x140032331  mov     rcx, [rbp+SRWLock]; SRWLock
0x140032335  test    rcx, rcx
0x140032338  jz      short loc_140032340
0x14003233a  call    cs:__imp_ReleaseSRWLockExclusive
0x140032340  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x140032345  mov     r9, rax
0x140032348  mov     ecx, [rax]
0x14003234a  cmp     ecx, 4
0x14003234d  jbe     loc_14003253C
0x140032353  mov     rcx, [rdi+30h]
0x140032357  mov     [rbp+var_70], rcx
0x14003235b  mov     ecx, [rdi+44h]
0x14003235e  mov     dword ptr [rbp+SRWLock], ecx
0x140032361  mov     ecx, [rdi+10h]
0x140032364  mov     [rbp+arg_8], ecx
0x140032367  mov     rcx, [rdi+78h]
0x14003236b  mov     [rbp+var_68], rcx
0x14003236f  mov     rax, [rdi+70h]
0x140032373  mov     [rbp+var_60], rax
0x140032377  mov     eax, [rdi+68h]
0x14003237a  mov     dword ptr [rbp+arg_10], eax
0x14003237d  mov     rax, [rdi+60h]
0x140032381  mov     [rbp+var_58], rax
0x140032385  mov     rax, [rdi+58h]
0x140032389  mov     [rbp+var_50], rax
0x14003238d  mov     eax, [rdi+50h]
0x140032390  mov     [rbp+arg_18], eax
0x140032393  mov     rax, [rdi+48h]
0x140032397  mov     [rbp+var_48], rax
0x14003239b  mov     eax, [rdi+20h]
0x14003239e  mov     [rbp+var_80], eax
0x1400323a1  mov     rax, [rdi+18h]
0x1400323a5  mov     [rbp+var_40], rax
0x1400323a9  mov     eax, [rdi]
0x1400323ab  mov     [rbp+var_7C], eax
0x1400323ae  mov     rax, [rdi+80h]
0x1400323b5  mov     [rbp+var_38], rax
0x1400323b9  mov     eax, [rdi+40h]
0x1400323bc  mov     [rbp+var_78], eax
0x1400323bf  mov     rax, [rdi+38h]
0x1400323c3  mov     [rbp+var_30], rax
0x1400323c7  mov     eax, [rdi+8]
0x1400323ca  mov     [rbp+var_74], eax
0x1400323cd  mov     eax, 1000000h
0x1400323d2  mov     [rbp+var_28], rax
0x1400323d6  mov     [rbp+var_20], rax
0x1400323da  mov     r8, [rbx+110h]
0x1400323e1  add     r8, 8
0x1400323e5  lea     rax, [rbp+var_70]
0x1400323e9  mov     [rsp+140h+var_90], rax
0x1400323f1  lea     rax, [rbp+SRWLock]
0x1400323f5  mov     [rsp+140h+var_98], rax
0x1400323fd  lea     rax, [rbp+arg_8]
0x140032401  mov     [rsp+140h+var_A0], rax
0x140032409  lea     rax, [rbp+var_68]
0x14003240d  mov     [rsp+140h+var_A8], rax
0x140032415  lea     rax, [rbp+var_60]
0x140032419  mov     [rsp+140h+var_B0], rax
0x140032421  lea     rax, [rbp+arg_10]
0x140032425  mov     [rsp+140h+var_B8], rax
0x14003242d  lea     rax, [rbp+var_58]
0x140032431  mov     [rsp+140h+var_C0], rax
0x140032439  lea     rax, [rbp+var_50]
0x14003243d  mov     [rsp+140h+var_C8], rax
0x140032442  lea     rax, [rbp+arg_18]
0x140032446  mov     [rsp+140h+var_D0], rax
0x14003244b  lea     rax, [rbp+var_48]
0x14003244f  mov     [rsp+140h+var_D8], rax
0x140032454  lea     rax, [rbp+var_80]
0x140032458  mov     [rsp+140h+var_E0], rax
0x14003245d  lea     rax, [rbp+var_40]
0x140032461  mov     [rsp+140h+var_E8], rax
0x140032466  lea     rax, [rbp+var_7C]
0x14003246a  mov     [rsp+140h+var_F0], rax
0x14003246f  lea     rax, [rbp+var_38]
0x140032473  mov     [rsp+140h+var_F8], rax
0x140032478  lea     rax, [rbp+var_78]
0x14003247c  mov     [rsp+140h+var_100], rax
0x140032481  lea     rax, [rbp+var_30]
0x140032485  mov     [rsp+140h+var_108], rax
0x14003248a  lea     rax, [rbp+var_74]
0x14003248e  mov     [rsp+140h+var_110], rax
0x140032493  lea     rax, [rbp+var_28]
0x140032497  mov     [rsp+140h+var_118], rax
0x14003249c  lea     rax, [rbp+var_20]
0x1400324a0  mov     [rsp+140h+var_120], rax
0x1400324a5  lea     rdx, dword_1400D591C
0x1400324ac  mov     rcx, r9
0x1400324af  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400324b4  jmp     loc_14003253C
0x1400324b9  lea     rdx, [rbp+SRWLock]
0x1400324bd  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400324c2  mov     rax, [rbx+110h]
0x1400324c9  mov     dword ptr [rax], 2
0x1400324cf  mov     rcx, [rbp+SRWLock]; SRWLock
0x1400324d3  test    rcx, rcx
0x1400324d6  jz      short loc_1400324DE
0x1400324d8  call    cs:__imp_ReleaseSRWLockExclusive
0x1400324de  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x1400324e3  mov     rdi, rax
0x1400324e6  mov     ecx, [rax]
0x1400324e8  cmp     ecx, 4
0x1400324eb  jbe     short loc_14003253C
0x1400324ed  call    cs:__imp_GetCurrentThreadId
0x1400324f3  mov     dword ptr [rbp+SRWLock], eax
0x1400324f6  mov     r8, [rbx+110h]
0x1400324fd  mov     ecx, [r8+48h]
0x140032501  mov     [rbp+arg_8], ecx
0x140032504  mov     eax, 1000000h
0x140032509  mov     [rbp+arg_10], rax
0x14003250d  add     r8, 8
0x140032511  lea     rax, [rbp+SRWLock]
0x140032515  mov     [rsp+140h+var_110], rax
0x14003251a  lea     rax, [rbp+arg_8]
0x14003251e  mov     [rsp+140h+var_118], rax
0x140032523  lea     rax, [rbp+arg_10]
0x140032527  mov     [rsp+140h+var_120], rax
0x14003252c  lea     rdx, dword_1400D58BC
0x140032533  mov     rcx, rdi
0x140032536  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14003253b  nop
0x14003253c  lea     rcx, [rbx+120h]; this
0x140032543  cmp     dword ptr [rcx+18h], 0
0x140032547  jz      short loc_14003254F
0x140032549  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14003254e  nop
0x14003254f  add     rsp, 130h
0x140032556  pop     rdi
0x140032557  pop     rbx
0x140032558  pop     rbp
0x140032559  retn
```
