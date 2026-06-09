# ComputeLegacy::Diagnostics::TraceProvider::ClientLib_EventCallback_v1::StartActivity<HCS_EVENT * &,uint>(HCS_EVENT * &,uint &&)

- ea: `0x180013690`
- end: `0x18001385f`
- name: `??$StartActivity@AEAPEAUHCS_EVENT@@I@ClientLib_EventCallback_v1@TraceProvider@Diagnostics@ComputeLegacy@@QEAAXAEAPEAUHCS_EVENT@@$$QEAI@Z`
- size: `463`
- prototype: `void __fastcall(__int64, __int64 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a4b0`

## callees

- `0x180001700`
- `0x180002f50`
- `0x18000a41c`
- `0x180013690`
- `0x18001c384`
- `0x180020fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013736`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013782`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013782`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013712`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013712`

## pseudocode

```c
void __fastcall ComputeLegacy::Diagnostics::TraceProvider::ClientLib_EventCallback_v1::StartActivity<HCS_EVENT * &,unsigned int>(
        __int64 a1,
        __int64 *a2,
        int *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-59h] BYREF
  int v14; // [rsp+38h] [rbp-51h] BYREF
  __int64 v15; // [rsp+40h] [rbp-49h] BYREF
  __int64 v16; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v18; // [rsp+70h] [rbp-19h]
  __int64 v19; // [rsp+78h] [rbp-11h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-9h]
  __int64 v21; // [rsp+88h] [rbp-1h]
  __int64 *v22; // [rsp+90h] [rbp+7h]
  __int64 v23; // [rsp+98h] [rbp+Fh]
  int *v24; // [rsp+A0h] [rbp+17h]
  __int64 v25; // [rsp+A8h] [rbp+1Fh]

  SRWLock = 0;
  wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v6 = *(_QWORD *)(a1 + 272);
  v7 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v7 > 4u
    && (*(_QWORD *)(v7 + 16) & 0x10000LL) != 0
    && (*(_QWORD *)(v7 + 24) & 0x10000LL) == *(_QWORD *)(v7 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  }
  else
  {
    *(_OWORD *)(v6 + 8) = 0;
  }
  v8 = SRWLock;
  *(_DWORD *)v6 = 1;
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  v9 = *((_QWORD *)ComputeLegacy::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v9 > 4u
    && (*(_QWORD *)(v9 + 16) & 0x10000LL) != 0
    && (*(_QWORD *)(v9 + 24) & 0x10000LL) == *(_QWORD *)(v9 + 24) )
  {
    v14 = *a3;
    v15 = *a2;
    CurrentThreadId = GetCurrentThreadId();
    v11 = *(_QWORD *)(a1 + 272);
    LODWORD(SRWLock) = CurrentThreadId;
    v16 = 0;
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    v25 = 4;
    v24 = &v14;
    v23 = 8;
    v22 = &v15;
    v21 = 4;
    p_SRWLock = &SRWLock;
    v19 = 8;
    v18 = &v16;
    tlgWriteTransfer_EventWriteTransfer(v9, (int)&dword_18009CE7C, v11 + 8, v12, 6u, &v17);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x180013690  mov     [rsp-8+arg_8], rbx
0x180013695  mov     [rsp-8+arg_10], rsi
0x18001369a  push    rbp
0x18001369b  push    rdi
0x18001369c  push    r12
0x18001369e  push    r14
0x1800136a0  push    r15
0x1800136a2  lea     rbp, [rsp-37h]
0x1800136a7  sub     rsp, 0C0h
0x1800136ae  mov     rax, cs:__security_cookie
0x1800136b5  xor     rax, rsp
0x1800136b8  mov     [rbp+57h+var_30], rax
0x1800136bc  mov     r14, rdx
0x1800136bf  xor     r15d, r15d
0x1800136c2  lea     rdx, [rbp+57h+SRWLock]
0x1800136c6  mov     [rbp+57h+SRWLock], r15
0x1800136ca  mov     rsi, r8
0x1800136cd  mov     rdi, rcx
0x1800136d0  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLegacy@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeLegacy::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800136d5  mov     rbx, [rdi+110h]
0x1800136dc  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x1800136e1  mov     r12d, 10000h
0x1800136e7  mov     rdx, [rax+8]
0x1800136eb  mov     eax, [rdx]
0x1800136ed  cmp     eax, 4
0x1800136f0  jbe     short loc_180013720
0x1800136f2  mov     rcx, [rdx+18h]
0x1800136f6  mov     rax, [rdx+10h]
0x1800136fa  test    r12, rax
0x1800136fd  jz      short loc_180013720
0x1800136ff  mov     rax, rcx
0x180013702  and     rax, r12
0x180013705  cmp     rax, rcx
0x180013708  jnz     short loc_180013720
0x18001370a  lea     rdx, [rbx+8]; ActivityId
0x18001370e  lea     ecx, [r15+3]; ControlCode
0x180013712  call    cs:__imp_EventActivityIdControl
0x180013719  nop     dword ptr [rax+rax+00h]
0x18001371e  jmp     short loc_180013727
0x180013720  xorps   xmm0, xmm0
0x180013723  movups  xmmword ptr [rbx+8], xmm0
0x180013727  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001372b  mov     dword ptr [rbx], 1
0x180013731  test    rcx, rcx
0x180013734  jz      short loc_180013742
0x180013736  call    cs:__imp_ReleaseSRWLockExclusive
0x18001373d  nop     dword ptr [rax+rax+00h]
0x180013742  call    ?Instance@TraceProvider@Diagnostics@ComputeLegacy@@KAPEAV123@XZ; ComputeLegacy::Diagnostics::TraceProvider::Instance(void)
0x180013747  mov     rbx, [rax+8]
0x18001374b  mov     eax, [rbx]
0x18001374d  cmp     eax, 4
0x180013750  jbe     loc_180013824
0x180013756  mov     rcx, [rbx+18h]
0x18001375a  mov     rax, [rbx+10h]
0x18001375e  test    r12, rax
0x180013761  jz      loc_180013824
0x180013767  mov     rax, rcx
0x18001376a  and     rax, r12
0x18001376d  cmp     rax, rcx
0x180013770  jnz     loc_180013824
0x180013776  mov     eax, [rsi]
0x180013778  mov     [rbp+57h+var_A8], eax
0x18001377b  mov     rax, [r14]
0x18001377e  mov     [rbp+57h+var_A0], rax
0x180013782  call    cs:__imp_GetCurrentThreadId
0x180013789  nop     dword ptr [rax+rax+00h]
0x18001378e  mov     r8, [rdi+110h]
0x180013795  mov     dword ptr [rbp+57h+SRWLock], eax
0x180013798  mov     [rbp+57h+var_98], r15
0x18001379c  cmp     [r8+4], r15b
0x1800137a0  jz      short loc_1800137BD
0x1800137a2  lea     r9, [r8+18h]
0x1800137a6  cmp     [r9], r15d
0x1800137a9  jnz     short loc_1800137C0
0x1800137ab  cmp     [r9+4], r15d
0x1800137af  jnz     short loc_1800137C0
0x1800137b1  cmp     [r9+8], r15d
0x1800137b5  jnz     short loc_1800137C0
0x1800137b7  cmp     [r9+0Ch], r15d
0x1800137bb  jnz     short loc_1800137C0
0x1800137bd  mov     r9, r15; int
0x1800137c0  lea     rax, [rbp+57h+var_A8]
0x1800137c4  mov     [rbp+57h+var_38], 4
0x1800137cc  mov     [rbp+57h+var_40], rax
0x1800137d0  lea     rdx, dword_18009CE7C; int
0x1800137d7  lea     rax, [rbp+57h+var_A0]
0x1800137db  mov     [rbp+57h+var_48], 8
0x1800137e3  mov     [rbp+57h+var_50], rax
0x1800137e7  add     r8, 8; int
0x1800137eb  lea     rax, [rbp+57h+SRWLock]
0x1800137ef  mov     [rbp+57h+var_58], 4
0x1800137f7  mov     [rbp+57h+var_60], rax
0x1800137fb  mov     rcx, rbx; int
0x1800137fe  lea     rax, [rbp+57h+var_98]
0x180013802  mov     [rbp+57h+var_68], 8
0x18001380a  mov     [rbp+57h+var_70], rax
0x18001380e  lea     rax, [rbp+57h+var_90]
0x180013812  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x180013817  mov     [rsp+0E0h+var_C0], 6; ULONG
0x18001381f  call    _tlgWriteTransfer_EventWriteTransfer
0x180013824  lea     rcx, [rdi+120h]; this
0x18001382b  cmp     [rcx+18h], r15d
0x18001382f  jnz     short loc_180013836
0x180013831  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180013836  mov     rcx, [rbp+57h+var_30]
0x18001383a  xor     rcx, rsp; StackCookie
0x18001383d  call    __security_check_cookie
0x180013842  lea     r11, [rsp+0E0h+var_20]
0x18001384a  mov     rbx, [r11+38h]
0x18001384e  mov     rsi, [r11+40h]
0x180013852  mov     rsp, r11
0x180013855  pop     r15
0x180013857  pop     r14
0x180013859  pop     r12
0x18001385b  pop     rdi
0x18001385c  pop     rbp
0x18001385d  retn
```
