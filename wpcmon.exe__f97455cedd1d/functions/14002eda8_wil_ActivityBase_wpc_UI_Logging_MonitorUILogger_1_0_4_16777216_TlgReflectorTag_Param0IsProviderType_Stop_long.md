# wil::ActivityBase<wpc::UI::Logging::MonitorUILogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x14002eda8`
- end: `0x14002eec8`
- name: `?Stop@?$ActivityBase@VMonitorUILogger@Logging@UI@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `288`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: ``

## callers

- `0x14002c480`
- `0x14002eed0`
- `0x1400463ec`
- `0x14004c4d0`
- `0x140092dc0`
- `0x140095770`

## callees

- `0x1400015d0`
- `0x140006314`
- `0x140012bd4`
- `0x140018560`
- `0x140019420`
- `0x14002af88`
- `0x14002e9a8`
- `0x14002eda8`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14002edfe`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14002edfe`
- `KERNEL32!GetCurrentThreadId` at `0x14002ee23`
- `KERNEL32!GetCurrentThreadId` at `0x14002ee23`

## pseudocode

```c
void __fastcall wil::ActivityBase<wpc::UI::Logging::MonitorUILogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // esi
  int v6; // edi
  int v7; // esi
  const struct _tlgProvider_t *v8; // rdi
  __int64 v9; // r9
  const struct wil::FailureInfo *v10; // rdx
  _BYTE v11[184]; // [rsp+40h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+100h] [rbp+8h] BYREF
  int v13; // [rsp+110h] [rbp+18h] BYREF
  __int64 v14; // [rsp+118h] [rbp+20h] BYREF

  wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v11, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v11, v10);
  }
  v6 = *(_DWORD *)(v4 + 72);
  if ( v6 >= 0 )
  {
    *(_DWORD *)(v4 + 72) = a2;
    v6 = a2;
  }
  v7 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v7;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v7 )
  {
    v8 = wpc::UI::Logging::MonitorUILogger::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v13 = a2;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (__int64)&word_1400D53DE,
        *(_QWORD *)(a1 + 272) + 8LL,
        v9,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&SRWLock);
    }
  }
  else
  {
    wil::ActivityBase<wpc::UI::Logging::MonitorUILogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      (unsigned int)v6);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x14002eda8  mov     rax, rsp
0x14002edab  mov     [rax+10h], rbx
0x14002edaf  push    rbp
0x14002edb0  push    rsi
0x14002edb1  push    rdi
0x14002edb2  sub     rsp, 0E0h
0x14002edb9  mov     ebp, edx
0x14002edbb  mov     rbx, rcx
0x14002edbe  lea     rdx, [rax+8]
0x14002edc2  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002edc7  mov     rax, [rbx+110h]
0x14002edce  mov     esi, [rax+0F8h]
0x14002edd4  cmp     esi, 1
0x14002edd7  jl      loc_14002EEAB
0x14002eddd  mov     edi, [rax+48h]
0x14002ede0  test    edi, edi
0x14002ede2  js      short loc_14002EDE9
0x14002ede4  mov     [rax+48h], ebp
0x14002ede7  mov     edi, ebp
0x14002ede9  dec     esi
0x14002edeb  mov     [rax+0F8h], esi
0x14002edf1  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x14002edf9  test    rcx, rcx
0x14002edfc  jz      short loc_14002EE04
0x14002edfe  call    cs:__imp_ReleaseSRWLockExclusive
0x14002ee04  test    esi, esi
0x14002ee06  jnz     short loc_14002EE14
0x14002ee08  mov     edx, edi
0x14002ee0a  mov     rcx, rbx
0x14002ee0d  call    ?ReportStopActivity@?$ActivityBase@VMonitorUILogger@Logging@UI@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<wpc::UI::Logging::MonitorUILogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x14002ee12  jmp     short loc_14002EE85
0x14002ee14  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14002ee19  mov     rdi, rax
0x14002ee1c  mov     ecx, [rax]
0x14002ee1e  cmp     ecx, 5
0x14002ee21  jbe     short loc_14002EE85
0x14002ee23  call    cs:__imp_GetCurrentThreadId
0x14002ee29  mov     dword ptr [rsp+0F8h+SRWLock], eax
0x14002ee30  mov     [rsp+0F8h+arg_10], ebp
0x14002ee37  mov     [rsp+0F8h+arg_18], 1000000h
0x14002ee43  mov     r8, [rbx+110h]
0x14002ee4a  add     r8, 8
0x14002ee4e  lea     rax, [rsp+0F8h+SRWLock]
0x14002ee56  mov     [rsp+0F8h+var_C8], rax
0x14002ee5b  lea     rax, [rsp+0F8h+arg_10]
0x14002ee63  mov     [rsp+0F8h+var_D0], rax
0x14002ee68  lea     rax, [rsp+0F8h+arg_18]
0x14002ee70  mov     [rsp+0F8h+var_D8], rax
0x14002ee75  lea     rdx, word_1400D53DE
0x14002ee7c  mov     rcx, rdi
0x14002ee7f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002ee84  nop
0x14002ee85  lea     rcx, [rbx+120h]; this
0x14002ee8c  cmp     dword ptr [rcx+18h], 0
0x14002ee90  jz      short loc_14002EE98
0x14002ee92  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14002ee97  nop
0x14002ee98  mov     rbx, [rsp+0F8h+arg_8]
0x14002eea0  add     rsp, 0E0h
0x14002eea7  pop     rdi
0x14002eea8  pop     rsi
0x14002eea9  pop     rbp
0x14002eeaa  retn
0x14002eeab  xor     edx, edx; Val
0x14002eead  mov     r8d, 98h; Size
0x14002eeb3  lea     rcx, [rsp+0F8h+var_B8]; void *
0x14002eeb8  call    memset_0
0x14002eebd  lea     rcx, [rsp+0F8h+var_B8]; this
0x14002eec2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
