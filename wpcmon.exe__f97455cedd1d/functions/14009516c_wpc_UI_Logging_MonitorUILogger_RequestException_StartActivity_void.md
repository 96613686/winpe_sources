# wpc::UI::Logging::MonitorUILogger::RequestException::StartActivity(void)

- ea: `0x14009516c`
- end: `0x1400952ab`
- name: `?StartActivity@RequestException@MonitorUILogger@Logging@UI@wpc@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::RequestException *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140092dc0`

## callees

- `0x140001e2c`
- `0x140005530`
- `0x140012bd4`
- `0x140018138`
- `0x14002af88`
- `0x14009516c`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x1400951bb`
- `ADVAPI32!EventActivityIdControl` at `0x1400951bb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400951d9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400951d9`
- `KERNEL32!GetCurrentThreadId` at `0x1400951f2`
- `KERNEL32!GetCurrentThreadId` at `0x1400951f2`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::RequestException::StartActivity(
        wpc::UI::Logging::MonitorUILogger::RequestException *this)
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
      (unsigned __int8 *)byte_1400D7863,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wpc::UI::Logging::MonitorUILogger::RequestException *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x14009516c  mov     [rsp-8+arg_8], rbx
0x140095171  mov     [rsp-8+arg_10], rdi
0x140095176  push    rbp
0x140095177  lea     rbp, [rsp-57h]
0x14009517c  sub     rsp, 90h
0x140095183  mov     rax, cs:__security_cookie
0x14009518a  xor     rax, rsp
0x14009518d  mov     [rbp+57h+var_10], rax
0x140095191  mov     rbx, rcx
0x140095194  lea     rdx, [rbp+57h+SRWLock]
0x140095198  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14009519d  mov     rdi, [rbx+110h]
0x1400951a4  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x1400951a9  mov     r8d, [rax]
0x1400951ac  cmp     r8d, 4
0x1400951b0  jbe     short loc_1400951C3
0x1400951b2  lea     rdx, [rdi+8]; ActivityId
0x1400951b6  mov     ecx, 3; ControlCode
0x1400951bb  call    cs:__imp_EventActivityIdControl
0x1400951c1  jmp     short loc_1400951CA
0x1400951c3  xorps   xmm0, xmm0
0x1400951c6  movups  xmmword ptr [rdi+8], xmm0
0x1400951ca  mov     dword ptr [rdi], 1
0x1400951d0  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400951d4  test    rcx, rcx
0x1400951d7  jz      short loc_1400951DF
0x1400951d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400951df  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x1400951e4  mov     rdi, rax
0x1400951e7  mov     ecx, [rax]
0x1400951e9  cmp     ecx, 4
0x1400951ec  jbe     loc_140095277
0x1400951f2  call    cs:__imp_GetCurrentThreadId
0x1400951f8  mov     dword ptr [rbp+57h+SRWLock], eax
0x1400951fb  mov     [rbp+57h+var_58], 1000000h
0x140095203  mov     r8, [rbx+110h]
0x14009520a  cmp     byte ptr [r8+4], 0
0x14009520f  jz      short loc_140095230
0x140095211  lea     r9, [r8+18h]
0x140095215  cmp     dword ptr [r9], 0
0x140095219  jnz     short loc_140095233
0x14009521b  cmp     dword ptr [r9+4], 0
0x140095220  jnz     short loc_140095233
0x140095222  cmp     dword ptr [r9+8], 0
0x140095227  jnz     short loc_140095233
0x140095229  cmp     dword ptr [r9+0Ch], 0
0x14009522e  jnz     short loc_140095233
0x140095230  xor     r9d, r9d
0x140095233  lea     rax, [rbp+57h+SRWLock]
0x140095237  mov     [rbp+57h+var_20], rax
0x14009523b  mov     [rbp+57h+var_18], 4
0x140095243  lea     rax, [rbp+57h+var_58]
0x140095247  mov     [rbp+57h+var_30], rax
0x14009524b  mov     [rbp+57h+var_28], 8
0x140095253  add     r8, 8
0x140095257  lea     rax, [rbp+57h+var_50]
0x14009525b  mov     [rsp+90h+var_68], rax
0x140095260  mov     [rsp+90h+var_70], 4
0x140095268  lea     rdx, byte_1400D7863
0x14009526f  mov     rcx, rdi
0x140095272  call    _tlgWriteTransfer_EventWriteTransfer
0x140095277  lea     rcx, [rbx+120h]; this
0x14009527e  cmp     dword ptr [rcx+18h], 0
0x140095282  jnz     short loc_14009528A
0x140095284  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140095289  nop
0x14009528a  mov     rcx, [rbp+57h+var_10]
0x14009528e  xor     rcx, rsp; StackCookie
0x140095291  call    __security_check_cookie
0x140095296  lea     r11, [rsp+90h+var_s0]
0x14009529e  mov     rbx, [r11+18h]
0x1400952a2  mov     rdi, [r11+20h]
0x1400952a6  mov     rsp, r11
0x1400952a9  pop     rbp
0x1400952aa  retn
```
