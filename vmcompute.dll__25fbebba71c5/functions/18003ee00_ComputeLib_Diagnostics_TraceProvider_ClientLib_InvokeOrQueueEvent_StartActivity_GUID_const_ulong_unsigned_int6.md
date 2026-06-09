# ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent::StartActivity(_GUID const &,ulong,unsigned __int64)

- ea: `0x18003ee00`
- end: `0x18003f002`
- name: `?StartActivity@ClientLib_InvokeOrQueueEvent@TraceProvider@Diagnostics@ComputeLib@@QEAAXAEBU_GUID@@K_K@Z`
- size: `514`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *__hidden this, const struct _GUID *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003dea0`

## callees

- `0x180001700`
- `0x180002f50`
- `0x18001c384`
- `0x18001ed48`
- `0x180020fa4`
- `0x18003ee00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ee64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003eede`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ee64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003eede`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ef25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ef25`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003eeba`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003eeba`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent::StartActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *this,
        const struct _GUID *a2,
        int a3,
        __int64 a4)
{
  __int64 v8; // rax
  __int128 v9; // xmm0
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rbx
  const struct _tlgProvider_t *v12; // rax
  RTL_SRWLOCK *v13; // rcx
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rax
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  const GUID *v20; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-59h] BYREF
  int v22; // [rsp+38h] [rbp-51h] BYREF
  __int64 v23; // [rsp+40h] [rbp-49h] BYREF
  __int64 v24; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v26; // [rsp+70h] [rbp-19h]
  __int64 v27; // [rsp+78h] [rbp-11h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-9h]
  __int64 v29; // [rsp+88h] [rbp-1h]
  int *v30; // [rsp+90h] [rbp+7h]
  __int64 v31; // [rsp+98h] [rbp+Fh]
  __int64 *v32; // [rsp+A0h] [rbp+17h]
  __int64 v33; // [rsp+A8h] [rbp+1Fh]

  SRWLock = 0;
  wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v8 = *((_QWORD *)this + 34);
  v9 = (__int128)*a2;
  v10 = SRWLock;
  *(_BYTE *)(v8 + 4) = 1;
  *(_OWORD *)(v8 + 24) = v9;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  SRWLock = 0;
  wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v11 = *((_QWORD *)this + 34);
  v12 = ComputeLib::Diagnostics::TraceProvider::Provider();
  if ( *(_DWORD *)v12 > 5u
    && (*((_QWORD *)v12 + 2) & 0x10000LL) != 0
    && (*((_QWORD *)v12 + 3) & 0x10000LL) == *((_QWORD *)v12 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v11 + 8));
  }
  else
  {
    *(_OWORD *)(v11 + 8) = 0;
  }
  v13 = SRWLock;
  *(_DWORD *)v11 = 1;
  if ( v13 )
    ReleaseSRWLockExclusive(v13);
  v14 = ComputeLib::Diagnostics::TraceProvider::Provider();
  v16 = (__int64)v14;
  if ( *(_DWORD *)v14 > 5u )
  {
    v17 = *((_QWORD *)v14 + 3);
    if ( (*(_QWORD *)(v16 + 16) & 0x10000LL) != 0 && (v17 & 0x10000) == v17 )
    {
      v23 = a4;
      v22 = a3;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v24 = 0;
      if ( !*(_BYTE *)(v19 + 4)
        || (v20 = (const GUID *)(v19 + 24), !*(_DWORD *)(v19 + 24))
        && !*(_DWORD *)(v19 + 28)
        && !*(_DWORD *)(v19 + 32)
        && !*(_DWORD *)(v19 + 36) )
      {
        v20 = 0;
      }
      v33 = 8;
      v32 = &v23;
      v31 = 4;
      v30 = &v22;
      v29 = 4;
      p_SRWLock = &SRWLock;
      v27 = 8;
      v26 = &v24;
      tlgWriteTransfer_EventWriteTransfer(
        v16,
        (unsigned __int8 *)&byte_1800A0B6F,
        (const GUID *)(v19 + 8),
        v20,
        6u,
        &v25);
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (ComputeLib::Diagnostics::TraceProvider::ClientLib_InvokeOrQueueEvent *)((char *)this + 288),
      v15);
}

```

## disassembly

```asm
0x18003ee00  mov     [rsp-8+arg_8], rbx
0x18003ee05  mov     [rsp-8+arg_10], rsi
0x18003ee0a  push    rbp
0x18003ee0b  push    rdi
0x18003ee0c  push    r12
0x18003ee0e  push    r14
0x18003ee10  push    r15
0x18003ee12  lea     rbp, [rsp-37h]
0x18003ee17  sub     rsp, 0C0h
0x18003ee1e  mov     rax, cs:__security_cookie
0x18003ee25  xor     rax, rsp
0x18003ee28  mov     [rbp+57h+var_30], rax
0x18003ee2c  mov     rbx, rdx
0x18003ee2f  xor     r15d, r15d
0x18003ee32  lea     rdx, [rbp+57h+SRWLock]
0x18003ee36  mov     [rbp+57h+SRWLock], r15
0x18003ee3a  mov     rsi, r9
0x18003ee3d  mov     r14d, r8d
0x18003ee40  mov     rdi, rcx
0x18003ee43  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003ee48  mov     rax, [rdi+110h]
0x18003ee4f  movups  xmm0, xmmword ptr [rbx]
0x18003ee52  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003ee56  mov     byte ptr [rax+4], 1
0x18003ee5a  movdqu  xmmword ptr [rax+18h], xmm0
0x18003ee5f  test    rcx, rcx
0x18003ee62  jz      short loc_18003EE70
0x18003ee64  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ee6b  nop     dword ptr [rax+rax+00h]
0x18003ee70  lea     rdx, [rbp+57h+SRWLock]
0x18003ee74  mov     [rbp+57h+SRWLock], r15
0x18003ee78  mov     rcx, rdi
0x18003ee7b  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003ee80  mov     rbx, [rdi+110h]
0x18003ee87  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003ee8c  mov     r12d, 10000h
0x18003ee92  mov     ecx, [rax]
0x18003ee94  cmp     ecx, 5
0x18003ee97  jbe     short loc_18003EEC8
0x18003ee99  mov     rcx, [rax+18h]
0x18003ee9d  mov     rax, [rax+10h]
0x18003eea1  test    r12, rax
0x18003eea4  jz      short loc_18003EEC8
0x18003eea6  mov     rax, rcx
0x18003eea9  and     rax, r12
0x18003eeac  cmp     rax, rcx
0x18003eeaf  jnz     short loc_18003EEC8
0x18003eeb1  lea     rdx, [rbx+8]; ActivityId
0x18003eeb5  mov     ecx, 3; ControlCode
0x18003eeba  call    cs:__imp_EventActivityIdControl
0x18003eec1  nop     dword ptr [rax+rax+00h]
0x18003eec6  jmp     short loc_18003EECF
0x18003eec8  xorps   xmm0, xmm0
0x18003eecb  movups  xmmword ptr [rbx+8], xmm0
0x18003eecf  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003eed3  mov     dword ptr [rbx], 1
0x18003eed9  test    rcx, rcx
0x18003eedc  jz      short loc_18003EEEA
0x18003eede  call    cs:__imp_ReleaseSRWLockExclusive
0x18003eee5  nop     dword ptr [rax+rax+00h]
0x18003eeea  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003eeef  mov     rbx, rax
0x18003eef2  mov     ecx, [rax]
0x18003eef4  cmp     ecx, 5
0x18003eef7  jbe     loc_18003EFC7
0x18003eefd  mov     rax, [rax+18h]
0x18003ef01  mov     rcx, [rbx+10h]
0x18003ef05  test    r12, rcx
0x18003ef08  jz      loc_18003EFC7
0x18003ef0e  mov     rcx, rax
0x18003ef11  and     rcx, r12
0x18003ef14  cmp     rcx, rax
0x18003ef17  jnz     loc_18003EFC7
0x18003ef1d  mov     [rbp+57h+var_A0], rsi
0x18003ef21  mov     [rbp+57h+var_A8], r14d
0x18003ef25  call    cs:__imp_GetCurrentThreadId
0x18003ef2c  nop     dword ptr [rax+rax+00h]
0x18003ef31  mov     r8, [rdi+110h]
0x18003ef38  mov     dword ptr [rbp+57h+SRWLock], eax
0x18003ef3b  mov     [rbp+57h+var_98], r15
0x18003ef3f  cmp     [r8+4], r15b
0x18003ef43  jz      short loc_18003EF60
0x18003ef45  lea     r9, [r8+18h]
0x18003ef49  cmp     [r9], r15d
0x18003ef4c  jnz     short loc_18003EF63
0x18003ef4e  cmp     [r9+4], r15d
0x18003ef52  jnz     short loc_18003EF63
0x18003ef54  cmp     [r9+8], r15d
0x18003ef58  jnz     short loc_18003EF63
0x18003ef5a  cmp     [r9+0Ch], r15d
0x18003ef5e  jnz     short loc_18003EF63
0x18003ef60  mov     r9, r15; int
0x18003ef63  lea     rax, [rbp+57h+var_A0]
0x18003ef67  mov     [rbp+57h+var_38], 8
0x18003ef6f  mov     [rbp+57h+var_40], rax
0x18003ef73  lea     rdx, byte_1800A0B6F; int
0x18003ef7a  lea     rax, [rbp+57h+var_A8]
0x18003ef7e  mov     [rbp+57h+var_48], 4
0x18003ef86  mov     [rbp+57h+var_50], rax
0x18003ef8a  add     r8, 8; int
0x18003ef8e  lea     rax, [rbp+57h+SRWLock]
0x18003ef92  mov     [rbp+57h+var_58], 4
0x18003ef9a  mov     [rbp+57h+var_60], rax
0x18003ef9e  mov     rcx, rbx; int
0x18003efa1  lea     rax, [rbp+57h+var_98]
0x18003efa5  mov     [rbp+57h+var_68], 8
0x18003efad  mov     [rbp+57h+var_70], rax
0x18003efb1  lea     rax, [rbp+57h+var_90]
0x18003efb5  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x18003efba  mov     [rsp+0E0h+var_C0], 6; ULONG
0x18003efc2  call    _tlgWriteTransfer_EventWriteTransfer
0x18003efc7  lea     rcx, [rdi+120h]; this
0x18003efce  cmp     [rcx+18h], r15d
0x18003efd2  jnz     short loc_18003EFD9
0x18003efd4  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18003efd9  mov     rcx, [rbp+57h+var_30]
0x18003efdd  xor     rcx, rsp; StackCookie
0x18003efe0  call    __security_check_cookie
0x18003efe5  lea     r11, [rsp+0E0h+var_20]
0x18003efed  mov     rbx, [r11+38h]
0x18003eff1  mov     rsi, [r11+40h]
0x18003eff5  mov     rsp, r11
0x18003eff8  pop     r15
0x18003effa  pop     r14
0x18003effc  pop     r12
0x18003effe  pop     rdi
0x18003efff  pop     rbp
0x18003f000  retn
```
