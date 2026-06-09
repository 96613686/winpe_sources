# wpc::UI::Logging::MonitorUILogger::GetAppDisplayName::StartActivity(void)

- ea: `0x14004a9ec`
- end: `0x14004ab2b`
- name: `?StartActivity@GetAppDisplayName@MonitorUILogger@Logging@UI@wpc@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::GetAppDisplayName *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400463ec`

## callees

- `0x140001e2c`
- `0x140005530`
- `0x140012bd4`
- `0x140018138`
- `0x14002af88`
- `0x14004a9ec`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x14004aa3b`
- `ADVAPI32!EventActivityIdControl` at `0x14004aa3b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004aa59`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14004aa59`
- `KERNEL32!GetCurrentThreadId` at `0x14004aa72`
- `KERNEL32!GetCurrentThreadId` at `0x14004aa72`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::GetAppDisplayName::StartActivity(
        wpc::UI::Logging::MonitorUILogger::GetAppDisplayName *this)
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
      (unsigned __int8 *)byte_1400D6009,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wpc::UI::Logging::MonitorUILogger::GetAppDisplayName *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x14004a9ec  mov     [rsp-8+arg_8], rbx
0x14004a9f1  mov     [rsp-8+arg_10], rdi
0x14004a9f6  push    rbp
0x14004a9f7  lea     rbp, [rsp-57h]
0x14004a9fc  sub     rsp, 90h
0x14004aa03  mov     rax, cs:__security_cookie
0x14004aa0a  xor     rax, rsp
0x14004aa0d  mov     [rbp+57h+var_10], rax
0x14004aa11  mov     rbx, rcx
0x14004aa14  lea     rdx, [rbp+57h+SRWLock]
0x14004aa18  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14004aa1d  mov     rdi, [rbx+110h]
0x14004aa24  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14004aa29  mov     r8d, [rax]
0x14004aa2c  cmp     r8d, 4
0x14004aa30  jbe     short loc_14004AA43
0x14004aa32  lea     rdx, [rdi+8]; ActivityId
0x14004aa36  mov     ecx, 3; ControlCode
0x14004aa3b  call    cs:__imp_EventActivityIdControl
0x14004aa41  jmp     short loc_14004AA4A
0x14004aa43  xorps   xmm0, xmm0
0x14004aa46  movups  xmmword ptr [rdi+8], xmm0
0x14004aa4a  mov     dword ptr [rdi], 1
0x14004aa50  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14004aa54  test    rcx, rcx
0x14004aa57  jz      short loc_14004AA5F
0x14004aa59  call    cs:__imp_ReleaseSRWLockExclusive
0x14004aa5f  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x14004aa64  mov     rdi, rax
0x14004aa67  mov     ecx, [rax]
0x14004aa69  cmp     ecx, 4
0x14004aa6c  jbe     loc_14004AAF7
0x14004aa72  call    cs:__imp_GetCurrentThreadId
0x14004aa78  mov     dword ptr [rbp+57h+SRWLock], eax
0x14004aa7b  mov     [rbp+57h+var_58], 1000000h
0x14004aa83  mov     r8, [rbx+110h]
0x14004aa8a  cmp     byte ptr [r8+4], 0
0x14004aa8f  jz      short loc_14004AAB0
0x14004aa91  lea     r9, [r8+18h]
0x14004aa95  cmp     dword ptr [r9], 0
0x14004aa99  jnz     short loc_14004AAB3
0x14004aa9b  cmp     dword ptr [r9+4], 0
0x14004aaa0  jnz     short loc_14004AAB3
0x14004aaa2  cmp     dword ptr [r9+8], 0
0x14004aaa7  jnz     short loc_14004AAB3
0x14004aaa9  cmp     dword ptr [r9+0Ch], 0
0x14004aaae  jnz     short loc_14004AAB3
0x14004aab0  xor     r9d, r9d
0x14004aab3  lea     rax, [rbp+57h+SRWLock]
0x14004aab7  mov     [rbp+57h+var_20], rax
0x14004aabb  mov     [rbp+57h+var_18], 4
0x14004aac3  lea     rax, [rbp+57h+var_58]
0x14004aac7  mov     [rbp+57h+var_30], rax
0x14004aacb  mov     [rbp+57h+var_28], 8
0x14004aad3  add     r8, 8
0x14004aad7  lea     rax, [rbp+57h+var_50]
0x14004aadb  mov     [rsp+90h+var_68], rax
0x14004aae0  mov     [rsp+90h+var_70], 4
0x14004aae8  lea     rdx, byte_1400D6009
0x14004aaef  mov     rcx, rdi
0x14004aaf2  call    _tlgWriteTransfer_EventWriteTransfer
0x14004aaf7  lea     rcx, [rbx+120h]; this
0x14004aafe  cmp     dword ptr [rcx+18h], 0
0x14004ab02  jnz     short loc_14004AB0A
0x14004ab04  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14004ab09  nop
0x14004ab0a  mov     rcx, [rbp+57h+var_10]
0x14004ab0e  xor     rcx, rsp; StackCookie
0x14004ab11  call    __security_check_cookie
0x14004ab16  lea     r11, [rsp+90h+var_s0]
0x14004ab1e  mov     rbx, [r11+18h]
0x14004ab22  mov     rdi, [r11+20h]
0x14004ab26  mov     rsp, r11
0x14004ab29  pop     rbp
0x14004ab2a  retn
```
