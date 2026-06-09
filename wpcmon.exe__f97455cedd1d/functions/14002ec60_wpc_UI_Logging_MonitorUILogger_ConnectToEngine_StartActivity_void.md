# wpc::UI::Logging::MonitorUILogger::ConnectToEngine::StartActivity(void)

- ea: `0x14002ec60`
- end: `0x14002ed9f`
- name: `?StartActivity@ConnectToEngine@MonitorUILogger@Logging@UI@wpc@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::ConnectToEngine *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002bf5c`

## callees

- `0x140001e2c`
- `0x140005530`
- `0x140012bd4`
- `0x140018138`
- `0x14002af88`
- `0x14002ec60`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x14002ecaf`
- `ADVAPI32!EventActivityIdControl` at `0x14002ecaf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14002eccd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14002eccd`
- `KERNEL32!GetCurrentThreadId` at `0x14002ece6`
- `KERNEL32!GetCurrentThreadId` at `0x14002ece6`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::ConnectToEngine::StartActivity(
        wpc::UI::Logging::MonitorUILogger::ConnectToEngine *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  const struct _tlgProvider_t *v4; // rdi
  __int64 v5; // r8
  const GUID *v6; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  __int64 v8; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v10; // [rsp+60h] [rbp+27h]
  __int64 v11; // [rsp+68h] [rbp+2Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+37h]
  __int64 v13; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)wpc::UI::Logging::MonitorUILogger::Provider() <= 4u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = wpc::UI::Logging::MonitorUILogger::Provider();
  if ( *(_DWORD *)v4 > 4u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v8 = 0x1000000;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = (const GUID *)(v5 + 24), !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    p_SRWLock = &SRWLock;
    v13 = 4;
    v10 = &v8;
    v11 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v4,
      (unsigned __int8 *)&dword_1400D5684,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wpc::UI::Logging::MonitorUILogger::ConnectToEngine *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x14002ec60  mov     [rsp-8+arg_8], rbx
0x14002ec65  mov     [rsp-8+arg_10], rdi
0x14002ec6a  push    rbp
0x14002ec6b  lea     rbp, [rsp-57h]
0x14002ec70  sub     rsp, 90h
0x14002ec77  mov     rax, cs:__security_cookie
0x14002ec7e  xor     rax, rsp
0x14002ec81  mov     [rbp+57h+var_10], rax
0x14002ec85  mov     rbx, rcx
0x14002ec88  lea     rdx, [rbp+57h+SRWLock]
0x14002ec8c  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14002ec91  mov     rdi, [rbx+110h]
0x14002ec98  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14002ec9d  mov     r8d, [rax]
0x14002eca0  cmp     r8d, 4
0x14002eca4  jbe     short loc_14002ECB7
0x14002eca6  lea     rdx, [rdi+8]; ActivityId
0x14002ecaa  mov     ecx, 3; ControlCode
0x14002ecaf  call    cs:__imp_EventActivityIdControl
0x14002ecb5  jmp     short loc_14002ECBE
0x14002ecb7  xorps   xmm0, xmm0
0x14002ecba  movups  xmmword ptr [rdi+8], xmm0
0x14002ecbe  mov     dword ptr [rdi], 1
0x14002ecc4  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14002ecc8  test    rcx, rcx
0x14002eccb  jz      short loc_14002ECD3
0x14002eccd  call    cs:__imp_ReleaseSRWLockExclusive
0x14002ecd3  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14002ecd8  mov     rdi, rax
0x14002ecdb  mov     ecx, [rax]
0x14002ecdd  cmp     ecx, 4
0x14002ece0  jbe     loc_14002ED6B
0x14002ece6  call    cs:__imp_GetCurrentThreadId
0x14002ecec  mov     dword ptr [rbp+57h+SRWLock], eax
0x14002ecef  mov     [rbp+57h+var_58], 1000000h
0x14002ecf7  mov     r8, [rbx+110h]
0x14002ecfe  cmp     byte ptr [r8+4], 0
0x14002ed03  jz      short loc_14002ED24
0x14002ed05  lea     r9, [r8+18h]
0x14002ed09  cmp     dword ptr [r9], 0
0x14002ed0d  jnz     short loc_14002ED27
0x14002ed0f  cmp     dword ptr [r9+4], 0
0x14002ed14  jnz     short loc_14002ED27
0x14002ed16  cmp     dword ptr [r9+8], 0
0x14002ed1b  jnz     short loc_14002ED27
0x14002ed1d  cmp     dword ptr [r9+0Ch], 0
0x14002ed22  jnz     short loc_14002ED27
0x14002ed24  xor     r9d, r9d
0x14002ed27  lea     rax, [rbp+57h+SRWLock]
0x14002ed2b  mov     [rbp+57h+var_20], rax
0x14002ed2f  mov     [rbp+57h+var_18], 4
0x14002ed37  lea     rax, [rbp+57h+var_58]
0x14002ed3b  mov     [rbp+57h+var_30], rax
0x14002ed3f  mov     [rbp+57h+var_28], 8
0x14002ed47  add     r8, 8
0x14002ed4b  lea     rax, [rbp+57h+var_50]
0x14002ed4f  mov     [rsp+90h+var_68], rax
0x14002ed54  mov     [rsp+90h+var_70], 4
0x14002ed5c  lea     rdx, dword_1400D5684
0x14002ed63  mov     rcx, rdi
0x14002ed66  call    _tlgWriteTransfer_EventWriteTransfer
0x14002ed6b  lea     rcx, [rbx+120h]; this
0x14002ed72  cmp     dword ptr [rcx+18h], 0
0x14002ed76  jnz     short loc_14002ED7E
0x14002ed78  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14002ed7d  nop
0x14002ed7e  mov     rcx, [rbp+57h+var_10]
0x14002ed82  xor     rcx, rsp; StackCookie
0x14002ed85  call    __security_check_cookie
0x14002ed8a  lea     r11, [rsp+90h+var_s0]
0x14002ed92  mov     rbx, [r11+18h]
0x14002ed96  mov     rdi, [r11+20h]
0x14002ed9a  mov     rsp, r11
0x14002ed9d  pop     rbp
0x14002ed9e  retn
```
