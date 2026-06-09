# wpc::UI::Logging::MonitorUILogger::ClearAppTimeLimitToast::StopActivity(void)

- ea: `0x14004adb0`
- end: `0x14004b03e`
- name: `?StopActivity@ClearAppTimeLimitToast@MonitorUILogger@Logging@UI@wpc@@MEAAXXZ`
- size: `654`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::ClearAppTimeLimitToast *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x1400015d0`
- `0x140012bd4`
- `0x140018560`
- `0x14002af88`
- `0x14004adb0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004ae0a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004af9a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004ae0a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004af9a`
- `KERNEL32!GetCurrentThreadId` at `0x14004afd1`
- `KERNEL32!GetCurrentThreadId` at `0x14004afd1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wpc::UI::Logging::MonitorUILogger::ClearAppTimeLimitToast::StopActivity(
        wpc::UI::Logging::MonitorUILogger::ClearAppTimeLimitToast *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v15; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v16; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v17; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v18; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v19; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v20; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v21; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

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
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0 && (v7 & 0x200000000000LL) == v7 )
      {
        v15 = (const WCHAR *)*((_QWORD *)v4 + 15);
        v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v17 = (const WCHAR *)*((_QWORD *)v4 + 12);
        v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v26 = v4[20];
        v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        LODWORD(v27) = v4[8];
        v20 = (const WCHAR *)*((_QWORD *)v4 + 3);
        v28 = *v4;
        v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v13 = v4[16];
        v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        v14 = v4[2];
        v23 = 0x1000000;
        v24[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)byte_1400D6295,
          *((_QWORD *)this + 34) + 8LL,
          v6,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v14,
          &v22,
          (__int64)&v13,
          &v21,
          (__int64)&v28,
          &v20,
          (__int64)&v27,
          &v19,
          (__int64)&v26,
          &v18,
          &v17,
          (__int64)&SRWLock,
          &v16,
          &v15);
      }
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
    v8 = wpc::UI::Logging::MonitorUILogger::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0 && (v10 & 0x200000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v26 = *(_DWORD *)(v11 + 72);
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (__int64)&word_1400D623E,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wpc::UI::Logging::MonitorUILogger::ClearAppTimeLimitToast *)((char *)this + 288));
}

```

## disassembly

```asm
0x14004adb0  push    rbp
0x14004adb2  push    rbx
0x14004adb3  push    rdi
0x14004adb4  lea     rbp, [rsp-47h]
0x14004adb9  sub     rsp, 100h
0x14004adc0  mov     rbx, rcx
0x14004adc3  mov     rdi, [rcx+110h]
0x14004adca  mov     eax, [rdi+48h]
0x14004adcd  test    eax, eax
0x14004adcf  jns     loc_14004AF7B
0x14004add5  add     rdi, 50h ; 'P'
0x14004add9  cmp     eax, [rdi+8]
0x14004addc  jnz     loc_14004AF7B
0x14004ade2  test    rdi, rdi
0x14004ade5  jz      loc_14004AF7B
0x14004adeb  lea     rdx, [rbp+57h+SRWLock]
0x14004adef  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004adf4  mov     rax, [rbx+110h]
0x14004adfb  mov     dword ptr [rax], 2
0x14004ae01  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14004ae05  test    rcx, rcx
0x14004ae08  jz      short loc_14004AE10
0x14004ae0a  call    cs:__imp_ReleaseSRWLockExclusive
0x14004ae10  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14004ae15  mov     r9, rax
0x14004ae18  mov     ecx, [rax]
0x14004ae1a  cmp     ecx, 4
0x14004ae1d  jbe     loc_14004B020
0x14004ae23  mov     rax, [rax+18h]
0x14004ae27  mov     rcx, [r9+10h]
0x14004ae2b  mov     rdx, 200000000000h
0x14004ae35  test    rdx, rcx
0x14004ae38  jz      loc_14004B020
0x14004ae3e  mov     rcx, rax
0x14004ae41  and     rcx, rdx
0x14004ae44  cmp     rcx, rax
0x14004ae47  jnz     loc_14004B020
0x14004ae4d  mov     rax, [rdi+78h]
0x14004ae51  mov     [rbp+57h+var_68], rax
0x14004ae55  mov     rax, [rdi+70h]
0x14004ae59  mov     [rbp+57h+var_60], rax
0x14004ae5d  mov     eax, [rdi+68h]
0x14004ae60  mov     dword ptr [rbp+57h+SRWLock], eax
0x14004ae63  mov     rax, [rdi+60h]
0x14004ae67  mov     [rbp+57h+var_58], rax
0x14004ae6b  mov     rax, [rdi+58h]
0x14004ae6f  mov     [rbp+57h+var_50], rax
0x14004ae73  mov     eax, [rdi+50h]
0x14004ae76  mov     [rbp+57h+arg_8], eax
0x14004ae79  mov     rax, [rdi+48h]
0x14004ae7d  mov     [rbp+57h+var_48], rax
0x14004ae81  mov     eax, [rdi+20h]
0x14004ae84  mov     dword ptr [rbp+57h+arg_10], eax
0x14004ae87  mov     rax, [rdi+18h]
0x14004ae8b  mov     [rbp+57h+var_40], rax
0x14004ae8f  mov     eax, [rdi]
0x14004ae91  mov     [rbp+57h+arg_18], eax
0x14004ae94  mov     rax, [rdi+80h]
0x14004ae9b  mov     [rbp+57h+var_38], rax
0x14004ae9f  mov     eax, [rdi+40h]
0x14004aea2  mov     [rbp+57h+var_70], eax
0x14004aea5  mov     rax, [rdi+38h]
0x14004aea9  mov     [rbp+57h+var_30], rax
0x14004aead  mov     eax, [rdi+8]
0x14004aeb0  mov     [rbp+57h+var_6C], eax
0x14004aeb3  mov     eax, 1000000h
0x14004aeb8  mov     [rbp+57h+var_28], rax
0x14004aebc  mov     [rbp+57h+var_20], rax
0x14004aec0  mov     r8, [rbx+110h]
0x14004aec7  add     r8, 8
0x14004aecb  lea     rax, [rbp+57h+var_68]
0x14004aecf  mov     [rsp+110h+var_78], rax
0x14004aed7  lea     rax, [rbp+57h+var_60]
0x14004aedb  mov     [rsp+110h+var_80], rax
0x14004aee3  lea     rax, [rbp+57h+SRWLock]
0x14004aee7  mov     [rsp+110h+var_88], rax
0x14004aeef  lea     rax, [rbp+57h+var_58]
0x14004aef3  mov     [rsp+110h+var_90], rax
0x14004aefb  lea     rax, [rbp+57h+var_50]
0x14004aeff  mov     [rsp+110h+var_98], rax
0x14004af04  lea     rax, [rbp+57h+arg_8]
0x14004af08  mov     [rsp+110h+var_A0], rax
0x14004af0d  lea     rax, [rbp+57h+var_48]
0x14004af11  mov     [rsp+110h+var_A8], rax
0x14004af16  lea     rax, [rbp+57h+arg_10]
0x14004af1a  mov     [rsp+110h+var_B0], rax
0x14004af1f  lea     rax, [rbp+57h+var_40]
0x14004af23  mov     [rsp+110h+var_B8], rax
0x14004af28  lea     rax, [rbp+57h+arg_18]
0x14004af2c  mov     [rsp+110h+var_C0], rax
0x14004af31  lea     rax, [rbp+57h+var_38]
0x14004af35  mov     [rsp+110h+var_C8], rax
0x14004af3a  lea     rax, [rbp+57h+var_70]
0x14004af3e  mov     [rsp+110h+var_D0], rax
0x14004af43  lea     rax, [rbp+57h+var_30]
0x14004af47  mov     [rsp+110h+var_D8], rax
0x14004af4c  lea     rax, [rbp+57h+var_6C]
0x14004af50  mov     [rsp+110h+var_E0], rax
0x14004af55  lea     rax, [rbp+57h+var_28]
0x14004af59  mov     [rsp+110h+var_E8], rax
0x14004af5e  lea     rax, [rbp+57h+var_20]
0x14004af62  mov     [rsp+110h+var_F0], rax
0x14004af67  lea     rdx, byte_1400D6295
0x14004af6e  mov     rcx, r9
0x14004af71  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14004af76  jmp     loc_14004B020
0x14004af7b  lea     rdx, [rbp+57h+SRWLock]
0x14004af7f  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004af84  mov     rax, [rbx+110h]
0x14004af8b  mov     dword ptr [rax], 2
0x14004af91  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14004af95  test    rcx, rcx
0x14004af98  jz      short loc_14004AFA0
0x14004af9a  call    cs:__imp_ReleaseSRWLockExclusive
0x14004afa0  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14004afa5  mov     rdi, rax
0x14004afa8  mov     ecx, [rax]
0x14004afaa  cmp     ecx, 4
0x14004afad  jbe     short loc_14004B020
0x14004afaf  mov     rax, [rax+18h]
0x14004afb3  mov     rcx, [rdi+10h]
0x14004afb7  mov     rdx, 200000000000h
0x14004afc1  test    rdx, rcx
0x14004afc4  jz      short loc_14004B020
0x14004afc6  mov     rcx, rax
0x14004afc9  and     rcx, rdx
0x14004afcc  cmp     rcx, rax
0x14004afcf  jnz     short loc_14004B020
0x14004afd1  call    cs:__imp_GetCurrentThreadId
0x14004afd7  mov     dword ptr [rbp+57h+SRWLock], eax
0x14004afda  mov     r8, [rbx+110h]
0x14004afe1  mov     eax, [r8+48h]
0x14004afe5  mov     [rbp+57h+arg_8], eax
0x14004afe8  mov     eax, 1000000h
0x14004afed  mov     [rbp+57h+arg_10], rax
0x14004aff1  add     r8, 8
0x14004aff5  lea     rax, [rbp+57h+SRWLock]
0x14004aff9  mov     [rsp+110h+var_E0], rax
0x14004affe  lea     rax, [rbp+57h+arg_8]
0x14004b002  mov     [rsp+110h+var_E8], rax
0x14004b007  lea     rax, [rbp+57h+arg_10]
0x14004b00b  mov     [rsp+110h+var_F0], rax
0x14004b010  lea     rdx, word_1400D623E
0x14004b017  mov     rcx, rdi
0x14004b01a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14004b01f  nop
0x14004b020  lea     rcx, [rbx+120h]; this
0x14004b027  cmp     dword ptr [rcx+18h], 0
0x14004b02b  jz      short loc_14004B033
0x14004b02d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14004b032  nop
0x14004b033  add     rsp, 100h
0x14004b03a  pop     rdi
0x14004b03b  pop     rbx
0x14004b03c  pop     rbp
0x14004b03d  retn
```
