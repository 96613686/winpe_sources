# UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(ushort const *)

- ea: `0x18000b61c`
- end: `0x18000b819`
- name: `?StartActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEBG@Z`
- size: `509`
- prototype: `int __fastcall(__int64, int *)`
- caller_count: `10`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180008ee0`
- `0x1800091c0`
- `0x18000d2d0`
- `0x18000dcb0`
- `0x18000e300`
- `0x18000e610`
- `0x18000e9f0`
- `0x18000ed30`
- `0x18000f340`
- `0x18000f8a0`

## callees

- `0x180001ecc`
- `0x180005b0c`
- `0x180009644`
- `0x180009f60`
- `0x18000b61c`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b6f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b6f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b7e3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b695`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b695`

## pseudocode

```c
int __fastcall UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(__int64 a1, int *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rax
  RTL_SRWLOCK *v6; // rcx
  _QWORD *Local; // rax
  _QWORD *v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // rbx
  int v18; // [rsp+30h] [rbp-59h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-51h] BYREF
  __int64 v20; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v22; // [rsp+70h] [rbp-19h]
  __int64 v23; // [rsp+78h] [rbp-11h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-9h]
  __int64 v25; // [rsp+88h] [rbp-1h]
  int *v26; // [rsp+90h] [rbp+7h]
  __int64 v27; // [rsp+98h] [rbp+Fh]
  int *v28; // [rsp+A0h] [rbp+17h]
  int v29; // [rsp+A8h] [rbp+1Fh]
  int v30; // [rsp+ACh] [rbp+23h]

  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = UwfTraceLoggingProvider<2>::Provider();
  if ( *(_DWORD *)v5 > 5u
    && (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v5 + 24) & 0x400000000000LL) == *(_QWORD *)(v5 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  }
  else
  {
    *(_OWORD *)(v4 + 8) = 0;
  }
  v6 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  Local = (_QWORD *)UwfTraceLoggingProvider<2>::Provider();
  v8 = Local;
  v9 = *(unsigned int *)Local;
  if ( (unsigned int)v9 > 5 )
  {
    v10 = Local[3];
    v9 = Local[2];
    if ( (v9 & 0x400000000000LL) != 0 )
    {
      v9 = v10 & 0x400000000000LL;
      if ( (v10 & 0x400000000000LL) == v10 )
      {
        v11 = 2;
        v18 = 2;
        CurrentThreadId = GetCurrentThreadId();
        v13 = *(_QWORD *)(a1 + 272);
        LODWORD(SRWLock) = CurrentThreadId;
        v20 = 0;
        if ( !*(_BYTE *)(v13 + 4)
          || (v14 = v13 + 24, !*(_DWORD *)(v13 + 24))
          && !*(_DWORD *)(v13 + 28)
          && !*(_DWORD *)(v13 + 32)
          && !*(_DWORD *)(v13 + 36) )
        {
          v14 = 0;
        }
        if ( a2 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *((_WORD *)a2 + v15) );
          v11 = 2 * v15 + 2;
        }
        else
        {
          a2 = &dword_18001F7A4;
        }
        v28 = a2;
        v26 = &v18;
        v29 = v11;
        p_SRWLock = &SRWLock;
        v30 = 0;
        v22 = &v20;
        v27 = 4;
        v25 = 4;
        v23 = 8;
        LODWORD(Local) = tlgWriteTransfer_EventWriteTransfer(v8, word_180022B42, v13 + 8, v14, 6, v21);
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v16 = a1 + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v9,
                          1);
      *(_QWORD *)v16 = Local;
      if ( Local )
      {
        *(_QWORD *)(v16 + 16) = *Local;
        *Local = v16;
        LODWORD(Local) = GetCurrentThreadId();
        *(_DWORD *)(v16 + 24) = (_DWORD)Local;
      }
    }
    else
    {
      *(_QWORD *)v16 = 0;
    }
  }
  return (int)Local;
}

```

## disassembly

```asm
0x18000b61c  mov     [rsp-8+arg_8], rbx
0x18000b621  mov     [rsp-8+arg_10], rsi
0x18000b626  push    rbp
0x18000b627  push    rdi
0x18000b628  push    r12
0x18000b62a  push    r14
0x18000b62c  push    r15
0x18000b62e  lea     rbp, [rsp-37h]
0x18000b633  sub     rsp, 0C0h
0x18000b63a  mov     rax, cs:__security_cookie
0x18000b641  xor     rax, rsp
0x18000b644  mov     [rbp+57h+var_30], rax
0x18000b648  mov     r14, rdx
0x18000b64b  mov     rbx, rcx
0x18000b64e  lea     rdx, [rbp+57h+SRWLock]
0x18000b652  call    ?LockExclusive@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b657  mov     rdi, [rbx+110h]
0x18000b65e  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000b663  mov     r12, 400000000000h
0x18000b66d  mov     edx, [rax]
0x18000b66f  cmp     edx, 5
0x18000b672  jbe     short loc_18000B69D
0x18000b674  mov     rcx, [rax+18h]
0x18000b678  mov     rax, [rax+10h]
0x18000b67c  test    r12, rax
0x18000b67f  jz      short loc_18000B69D
0x18000b681  mov     rax, rcx
0x18000b684  and     rax, r12
0x18000b687  cmp     rax, rcx
0x18000b68a  jnz     short loc_18000B69D
0x18000b68c  lea     rdx, [rdi+8]; ActivityId
0x18000b690  mov     ecx, 3; ControlCode
0x18000b695  call    cs:__imp_EventActivityIdControl
0x18000b69b  jmp     short loc_18000B6A4
0x18000b69d  xorps   xmm0, xmm0
0x18000b6a0  movups  xmmword ptr [rdi+8], xmm0
0x18000b6a4  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000b6a8  xor     r15d, r15d
0x18000b6ab  mov     dword ptr [rdi], 1
0x18000b6b1  test    rcx, rcx
0x18000b6b4  jz      short loc_18000B6BC
0x18000b6b6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b6bc  call    ?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ; UwfTraceLoggingProvider<2>::Provider(void)
0x18000b6c1  mov     rsi, rax
0x18000b6c4  mov     ecx, [rax]
0x18000b6c6  cmp     ecx, 5
0x18000b6c9  jbe     loc_18000B7B1
0x18000b6cf  mov     rdx, [rax+18h]
0x18000b6d3  mov     rcx, [rax+10h]
0x18000b6d7  test    r12, rcx
0x18000b6da  jz      loc_18000B7B1
0x18000b6e0  mov     rcx, rdx
0x18000b6e3  and     rcx, r12
0x18000b6e6  cmp     rcx, rdx
0x18000b6e9  jnz     loc_18000B7B1
0x18000b6ef  mov     edi, 2
0x18000b6f4  mov     [rbp+57h+var_B0], edi
0x18000b6f7  call    cs:__imp_GetCurrentThreadId
0x18000b6fd  mov     r8, [rbx+110h]
0x18000b704  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000b707  mov     [rbp+57h+var_A0], r15
0x18000b70b  cmp     [r8+4], r15b
0x18000b70f  jz      short loc_18000B72C
0x18000b711  lea     r9, [r8+18h]
0x18000b715  cmp     [r9], r15d
0x18000b718  jnz     short loc_18000B72F
0x18000b71a  cmp     [r9+4], r15d
0x18000b71e  jnz     short loc_18000B72F
0x18000b720  cmp     [r9+8], r15d
0x18000b724  jnz     short loc_18000B72F
0x18000b726  cmp     [r9+0Ch], r15d
0x18000b72a  jnz     short loc_18000B72F
0x18000b72c  mov     r9, r15
0x18000b72f  test    r14, r14
0x18000b732  jz      short loc_18000B74B
0x18000b734  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b738  inc     rax
0x18000b73b  cmp     [r14+rax*2], r15w
0x18000b740  jnz     short loc_18000B738
0x18000b742  lea     edi, ds:2[rax*2]
0x18000b749  jmp     short loc_18000B752
0x18000b74b  lea     r14, dword_18001F7A4
0x18000b752  lea     rax, [rbp+57h+var_B0]
0x18000b756  mov     [rbp+57h+var_40], r14
0x18000b75a  mov     [rbp+57h+var_50], rax
0x18000b75e  lea     rdx, word_180022B42
0x18000b765  lea     rax, [rbp+57h+SRWLock]
0x18000b769  mov     [rbp+57h+var_38], edi
0x18000b76c  mov     [rbp+57h+var_60], rax
0x18000b770  add     r8, 8
0x18000b774  lea     rax, [rbp+57h+var_A0]
0x18000b778  mov     [rbp+57h+var_34], r15d
0x18000b77c  mov     [rbp+57h+var_70], rax
0x18000b780  mov     rcx, rsi
0x18000b783  lea     rax, [rbp+57h+var_90]
0x18000b787  mov     [rbp+57h+var_48], 4
0x18000b78f  mov     [rsp+0E0h+var_B8], rax
0x18000b794  mov     [rsp+0E0h+var_C0], 6
0x18000b79c  mov     [rbp+57h+var_58], 4
0x18000b7a4  mov     [rbp+57h+var_68], 8
0x18000b7ac  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b7b1  cmp     [rbx+138h], r15d
0x18000b7b8  jnz     short loc_18000B7F1
0x18000b7ba  add     rbx, 120h
0x18000b7c1  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r15; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b7c8  jz      short loc_18000B7EE
0x18000b7ca  mov     dl, 1
0x18000b7cc  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000b7d1  mov     [rbx], rax
0x18000b7d4  test    rax, rax
0x18000b7d7  jz      short loc_18000B7F1
0x18000b7d9  mov     rcx, [rax]
0x18000b7dc  mov     [rbx+10h], rcx
0x18000b7e0  mov     [rax], rbx
0x18000b7e3  call    cs:__imp_GetCurrentThreadId
0x18000b7e9  mov     [rbx+18h], eax
0x18000b7ec  jmp     short loc_18000B7F1
0x18000b7ee  mov     [rbx], r15
0x18000b7f1  mov     rcx, [rbp+57h+var_30]
0x18000b7f5  xor     rcx, rsp; StackCookie
0x18000b7f8  call    __security_check_cookie
0x18000b7fd  lea     r11, [rsp+0E0h+var_20]
0x18000b805  mov     rbx, [r11+38h]
0x18000b809  mov     rsi, [r11+40h]
0x18000b80d  mov     rsp, r11
0x18000b810  pop     r15
0x18000b812  pop     r14
0x18000b814  pop     r12
0x18000b816  pop     rdi
0x18000b817  pop     rbp
0x18000b818  retn
```
