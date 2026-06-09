# wpc::UI::Logging::MonitorUILogger::ObserverConnection::StartActivity(void)

- ea: `0x14003218c`
- end: `0x1400322cb`
- name: `?StartActivity@ObserverConnection@MonitorUILogger@Logging@UI@wpc@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::ObserverConnection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002f42c`

## callees

- `0x140001e2c`
- `0x140005530`
- `0x140012bd4`
- `0x140018138`
- `0x14002af88`
- `0x14003218c`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x1400321db`
- `ADVAPI32!EventActivityIdControl` at `0x1400321db`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400321f9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400321f9`
- `KERNEL32!GetCurrentThreadId` at `0x140032212`
- `KERNEL32!GetCurrentThreadId` at `0x140032212`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::ObserverConnection::StartActivity(
        wpc::UI::Logging::MonitorUILogger::ObserverConnection *this)
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
      (unsigned __int8 *)&word_1400D5A76,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wpc::UI::Logging::MonitorUILogger::ObserverConnection *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x14003218c  mov     [rsp-8+arg_8], rbx
0x140032191  mov     [rsp-8+arg_10], rdi
0x140032196  push    rbp
0x140032197  lea     rbp, [rsp-57h]
0x14003219c  sub     rsp, 90h
0x1400321a3  mov     rax, cs:__security_cookie
0x1400321aa  xor     rax, rsp
0x1400321ad  mov     [rbp+57h+var_10], rax
0x1400321b1  mov     rbx, rcx
0x1400321b4  lea     rdx, [rbp+57h+SRWLock]
0x1400321b8  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400321bd  mov     rdi, [rbx+110h]
0x1400321c4  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x1400321c9  mov     r8d, [rax]
0x1400321cc  cmp     r8d, 4
0x1400321d0  jbe     short loc_1400321E3
0x1400321d2  lea     rdx, [rdi+8]; ActivityId
0x1400321d6  mov     ecx, 3; ControlCode
0x1400321db  call    cs:__imp_EventActivityIdControl
0x1400321e1  jmp     short loc_1400321EA
0x1400321e3  xorps   xmm0, xmm0
0x1400321e6  movups  xmmword ptr [rdi+8], xmm0
0x1400321ea  mov     dword ptr [rdi], 1
0x1400321f0  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400321f4  test    rcx, rcx
0x1400321f7  jz      short loc_1400321FF
0x1400321f9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400321ff  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x140032204  mov     rdi, rax
0x140032207  mov     ecx, [rax]
0x140032209  cmp     ecx, 4
0x14003220c  jbe     loc_140032297
0x140032212  call    cs:__imp_GetCurrentThreadId
0x140032218  mov     dword ptr [rbp+57h+SRWLock], eax
0x14003221b  mov     [rbp+57h+var_58], 1000000h
0x140032223  mov     r8, [rbx+110h]
0x14003222a  cmp     byte ptr [r8+4], 0
0x14003222f  jz      short loc_140032250
0x140032231  lea     r9, [r8+18h]
0x140032235  cmp     dword ptr [r9], 0
0x140032239  jnz     short loc_140032253
0x14003223b  cmp     dword ptr [r9+4], 0
0x140032240  jnz     short loc_140032253
0x140032242  cmp     dword ptr [r9+8], 0
0x140032247  jnz     short loc_140032253
0x140032249  cmp     dword ptr [r9+0Ch], 0
0x14003224e  jnz     short loc_140032253
0x140032250  xor     r9d, r9d
0x140032253  lea     rax, [rbp+57h+SRWLock]
0x140032257  mov     [rbp+57h+var_20], rax
0x14003225b  mov     [rbp+57h+var_18], 4
0x140032263  lea     rax, [rbp+57h+var_58]
0x140032267  mov     [rbp+57h+var_30], rax
0x14003226b  mov     [rbp+57h+var_28], 8
0x140032273  add     r8, 8
0x140032277  lea     rax, [rbp+57h+var_50]
0x14003227b  mov     [rsp+90h+var_68], rax
0x140032280  mov     [rsp+90h+var_70], 4
0x140032288  lea     rdx, word_1400D5A76
0x14003228f  mov     rcx, rdi
0x140032292  call    _tlgWriteTransfer_EventWriteTransfer
0x140032297  lea     rcx, [rbx+120h]; this
0x14003229e  cmp     dword ptr [rcx+18h], 0
0x1400322a2  jnz     short loc_1400322AA
0x1400322a4  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1400322a9  nop
0x1400322aa  mov     rcx, [rbp+57h+var_10]
0x1400322ae  xor     rcx, rsp; StackCookie
0x1400322b1  call    __security_check_cookie
0x1400322b6  lea     r11, [rsp+90h+var_s0]
0x1400322be  mov     rbx, [r11+18h]
0x1400322c2  mov     rdi, [r11+20h]
0x1400322c6  mov     rsp, r11
0x1400322c9  pop     rbp
0x1400322ca  retn
```
