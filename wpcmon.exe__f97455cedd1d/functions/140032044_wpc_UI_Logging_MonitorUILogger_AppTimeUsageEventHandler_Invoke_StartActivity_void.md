# wpc::UI::Logging::MonitorUILogger::AppTimeUsageEventHandler_Invoke::StartActivity(void)

- ea: `0x140032044`
- end: `0x140032183`
- name: `?StartActivity@AppTimeUsageEventHandler_Invoke@MonitorUILogger@Logging@UI@wpc@@QEAAXXZ`
- size: `319`
- prototype: `void __fastcall(wpc::UI::Logging::MonitorUILogger::AppTimeUsageEventHandler_Invoke *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140031750`

## callees

- `0x140001e2c`
- `0x140005530`
- `0x140012bd4`
- `0x140018138`
- `0x14002af88`
- `0x140032044`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140032093`
- `ADVAPI32!EventActivityIdControl` at `0x140032093`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400320b1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400320b1`
- `KERNEL32!GetCurrentThreadId` at `0x1400320ca`
- `KERNEL32!GetCurrentThreadId` at `0x1400320ca`

## pseudocode

```c
void __fastcall wpc::UI::Logging::MonitorUILogger::AppTimeUsageEventHandler_Invoke::StartActivity(
        wpc::UI::Logging::MonitorUILogger::AppTimeUsageEventHandler_Invoke *this)
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
      (unsigned __int8 *)byte_1400D5865,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wpc::UI::Logging::MonitorUILogger::AppTimeUsageEventHandler_Invoke *)((char *)this + 288),
      v3);
}

```

## disassembly

```asm
0x140032044  mov     [rsp-8+arg_8], rbx
0x140032049  mov     [rsp-8+arg_10], rdi
0x14003204e  push    rbp
0x14003204f  lea     rbp, [rsp-57h]
0x140032054  sub     rsp, 90h
0x14003205b  mov     rax, cs:__security_cookie
0x140032062  xor     rax, rsp
0x140032065  mov     [rbp+57h+var_10], rax
0x140032069  mov     rbx, rcx
0x14003206c  lea     rdx, [rbp+57h+SRWLock]
0x140032070  call    ?LockExclusive@?$ActivityBase@VScreenTime@Providers@TraceLog@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TraceLog::Providers::ScreenTime,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140032075  mov     rdi, [rbx+110h]
0x14003207c  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x140032081  mov     r8d, [rax]
0x140032084  cmp     r8d, 4
0x140032088  jbe     short loc_14003209B
0x14003208a  lea     rdx, [rdi+8]; ActivityId
0x14003208e  mov     ecx, 3; ControlCode
0x140032093  call    cs:__imp_EventActivityIdControl
0x140032099  jmp     short loc_1400320A2
0x14003209b  xorps   xmm0, xmm0
0x14003209e  movups  xmmword ptr [rdi+8], xmm0
0x1400320a2  mov     dword ptr [rdi], 1
0x1400320a8  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400320ac  test    rcx, rcx
0x1400320af  jz      short loc_1400320B7
0x1400320b1  call    cs:__imp_ReleaseSRWLockExclusive
0x1400320b7  call    ?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::UI::Logging::MonitorUILogger::Provider(void)
0x1400320bc  mov     rdi, rax
0x1400320bf  mov     ecx, [rax]
0x1400320c1  cmp     ecx, 4
0x1400320c4  jbe     loc_14003214F
0x1400320ca  call    cs:__imp_GetCurrentThreadId
0x1400320d0  mov     dword ptr [rbp+57h+SRWLock], eax
0x1400320d3  mov     [rbp+57h+var_58], 1000000h
0x1400320db  mov     r8, [rbx+110h]
0x1400320e2  cmp     byte ptr [r8+4], 0
0x1400320e7  jz      short loc_140032108
0x1400320e9  lea     r9, [r8+18h]
0x1400320ed  cmp     dword ptr [r9], 0
0x1400320f1  jnz     short loc_14003210B
0x1400320f3  cmp     dword ptr [r9+4], 0
0x1400320f8  jnz     short loc_14003210B
0x1400320fa  cmp     dword ptr [r9+8], 0
0x1400320ff  jnz     short loc_14003210B
0x140032101  cmp     dword ptr [r9+0Ch], 0
0x140032106  jnz     short loc_14003210B
0x140032108  xor     r9d, r9d
0x14003210b  lea     rax, [rbp+57h+SRWLock]
0x14003210f  mov     [rbp+57h+var_20], rax
0x140032113  mov     [rbp+57h+var_18], 4
0x14003211b  lea     rax, [rbp+57h+var_58]
0x14003211f  mov     [rbp+57h+var_30], rax
0x140032123  mov     [rbp+57h+var_28], 8
0x14003212b  add     r8, 8
0x14003212f  lea     rax, [rbp+57h+var_50]
0x140032133  mov     [rsp+90h+var_68], rax
0x140032138  mov     [rsp+90h+var_70], 4
0x140032140  lea     rdx, byte_1400D5865
0x140032147  mov     rcx, rdi
0x14003214a  call    _tlgWriteTransfer_EventWriteTransfer
0x14003214f  lea     rcx, [rbx+120h]; this
0x140032156  cmp     dword ptr [rcx+18h], 0
0x14003215a  jnz     short loc_140032162
0x14003215c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140032161  nop
0x140032162  mov     rcx, [rbp+57h+var_10]
0x140032166  xor     rcx, rsp; StackCookie
0x140032169  call    __security_check_cookie
0x14003216e  lea     r11, [rsp+90h+var_s0]
0x140032176  mov     rbx, [r11+18h]
0x14003217a  mov     rdi, [r11+20h]
0x14003217e  mov     rsp, r11
0x140032181  pop     rbp
0x140032182  retn
```
