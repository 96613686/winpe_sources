# WhesvcTelemetryProvider::WhesvcStartActivity::StartActivity(void)

- ea: `0x18000b1d8`
- end: `0x18000b379`
- name: `?StartActivity@WhesvcStartActivity@WhesvcTelemetryProvider@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(WhesvcTelemetryProvider::WhesvcStartActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b380`

## callees

- `0x1800018dc`
- `0x1800032e0`
- `0x1800084d0`
- `0x18000a9ac`
- `0x18000ae4c`
- `0x18000b1d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b34e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b34e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b260`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b260`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b242`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b242`

## pseudocode

```c
void __fastcall WhesvcTelemetryProvider::WhesvcStartActivity::StartActivity(
        WhesvcTelemetryProvider::WhesvcStartActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v14[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v15; // [rsp+60h] [rbp+7h]
  __int64 v16; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v18; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = WhesvcTelemetryProvider::Provider();
  if ( *(_DWORD *)v3 > 5u
    && (*((_QWORD *)v3 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v3 + 3) & 0x200000000000LL) == *((_QWORD *)v3 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v4 = WhesvcTelemetryProvider::Provider();
  v5 = v4;
  v6 = *(unsigned int *)v4;
  if ( (unsigned int)v6 > 5 )
  {
    v7 = *((_QWORD *)v4 + 3);
    v6 = *((_QWORD *)v5 + 2);
    if ( (v6 & 0x200000000000LL) != 0 )
    {
      v6 = v7 & 0x200000000000LL;
      if ( (v7 & 0x200000000000LL) == v7 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v13 = 0;
        v8 = *((_QWORD *)this + 34);
        if ( !*(_BYTE *)(v8 + 4)
          || (v9 = v8 + 24, !*(_DWORD *)(v8 + 24))
          && !*(_DWORD *)(v8 + 28)
          && !*(_DWORD *)(v8 + 32)
          && !*(_DWORD *)(v8 + 36) )
        {
          v9 = 0;
        }
        p_SRWLock = &SRWLock;
        v18 = 4;
        v15 = &v13;
        v16 = 8;
        tlgWriteTransfer_EventWriteTransfer(v5, byte_18002D1A1, v8 + 8, v9, 4, v14);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v10 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v6,
                          1);
      *(_QWORD *)v10 = Local;
      if ( Local )
      {
        *((_QWORD *)v10 + 2) = *Local;
        *Local = v10;
        *((_DWORD *)v10 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v10 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000b1d8  push    rbp
0x18000b1da  push    rbx
0x18000b1db  push    rdi
0x18000b1dc  push    r14
0x18000b1de  lea     rbp, [rsp-3Fh]
0x18000b1e3  sub     rsp, 98h
0x18000b1ea  mov     rax, cs:__security_cookie
0x18000b1f1  xor     rax, rsp
0x18000b1f4  mov     [rbp+57h+var_30], rax
0x18000b1f8  mov     rbx, rcx
0x18000b1fb  lea     rdx, [rbp+57h+SRWLock]
0x18000b1ff  call    ?LockExclusive@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b204  mov     rdi, [rbx+110h]
0x18000b20b  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x18000b210  mov     edx, [rax]
0x18000b212  mov     r14, 200000000000h
0x18000b21c  cmp     edx, 5
0x18000b21f  jbe     short loc_18000B24A
0x18000b221  mov     rcx, [rax+18h]
0x18000b225  mov     rax, [rax+10h]
0x18000b229  test    r14, rax
0x18000b22c  jz      short loc_18000B24A
0x18000b22e  mov     rax, rcx
0x18000b231  and     rax, r14
0x18000b234  cmp     rax, rcx
0x18000b237  jnz     short loc_18000B24A
0x18000b239  lea     rdx, [rdi+8]; ActivityId
0x18000b23d  mov     ecx, 3; ControlCode
0x18000b242  call    cs:__imp_EventActivityIdControl
0x18000b248  jmp     short loc_18000B251
0x18000b24a  xorps   xmm0, xmm0
0x18000b24d  movups  xmmword ptr [rdi+8], xmm0
0x18000b251  mov     dword ptr [rdi], 1
0x18000b257  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000b25b  test    rcx, rcx
0x18000b25e  jz      short loc_18000B266
0x18000b260  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b266  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x18000b26b  mov     rdi, rax
0x18000b26e  mov     ecx, [rax]
0x18000b270  cmp     ecx, 5
0x18000b273  jbe     loc_18000B31B
0x18000b279  mov     rax, [rax+18h]
0x18000b27d  mov     rcx, [rdi+10h]
0x18000b281  test    r14, rcx
0x18000b284  jz      loc_18000B31B
0x18000b28a  mov     rcx, rax
0x18000b28d  and     rcx, r14
0x18000b290  cmp     rcx, rax
0x18000b293  jnz     loc_18000B31B
0x18000b299  call    cs:__imp_GetCurrentThreadId
0x18000b29f  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000b2a2  mov     [rbp+57h+var_78], 0
0x18000b2aa  mov     r8, [rbx+110h]
0x18000b2b1  cmp     byte ptr [r8+4], 0
0x18000b2b6  jz      short loc_18000B2D7
0x18000b2b8  lea     r9, [r8+18h]
0x18000b2bc  cmp     dword ptr [r9], 0
0x18000b2c0  jnz     short loc_18000B2DA
0x18000b2c2  cmp     dword ptr [r9+4], 0
0x18000b2c7  jnz     short loc_18000B2DA
0x18000b2c9  cmp     dword ptr [r9+8], 0
0x18000b2ce  jnz     short loc_18000B2DA
0x18000b2d0  cmp     dword ptr [r9+0Ch], 0
0x18000b2d5  jnz     short loc_18000B2DA
0x18000b2d7  xor     r9d, r9d
0x18000b2da  lea     rax, [rbp+57h+SRWLock]
0x18000b2de  mov     [rbp+57h+var_40], rax
0x18000b2e2  mov     ecx, 4
0x18000b2e7  mov     [rbp+57h+var_38], rcx
0x18000b2eb  lea     rax, [rbp+57h+var_78]
0x18000b2ef  mov     [rbp+57h+var_50], rax
0x18000b2f3  mov     [rbp+57h+var_48], 8
0x18000b2fb  add     r8, 8
0x18000b2ff  lea     rax, [rbp+57h+var_70]
0x18000b303  mov     [rsp+0B0h+var_88], rax
0x18000b308  mov     [rsp+0B0h+var_90], ecx
0x18000b30c  lea     rdx, byte_18002D1A1
0x18000b313  mov     rcx, rdi
0x18000b316  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b31b  cmp     dword ptr [rbx+138h], 0
0x18000b322  jnz     short loc_18000B360
0x18000b324  add     rbx, 120h
0x18000b32b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b333  jz      short loc_18000B359
0x18000b335  mov     dl, 1
0x18000b337  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000b33c  mov     [rbx], rax
0x18000b33f  test    rax, rax
0x18000b342  jz      short loc_18000B360
0x18000b344  mov     rcx, [rax]
0x18000b347  mov     [rbx+10h], rcx
0x18000b34b  mov     [rax], rbx
0x18000b34e  call    cs:__imp_GetCurrentThreadId
0x18000b354  mov     [rbx+18h], eax
0x18000b357  jmp     short loc_18000B360
0x18000b359  mov     qword ptr [rbx], 0
0x18000b360  mov     rcx, [rbp+57h+var_30]
0x18000b364  xor     rcx, rsp; StackCookie
0x18000b367  call    __security_check_cookie
0x18000b36c  add     rsp, 98h
0x18000b373  pop     r14
0x18000b375  pop     rdi
0x18000b376  pop     rbx
0x18000b377  pop     rbp
0x18000b378  retn
```
