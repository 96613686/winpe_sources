# UserenvTelemetry::DeleteUserProfileDirectory::StartActivity(void)

- ea: `0x18001adcc`
- end: `0x18001aedc`
- name: `?StartActivity@DeleteUserProfileDirectory@UserenvTelemetry@@QEAAXXZ`
- size: `272`
- prototype: `void __fastcall(UserenvTelemetry::DeleteUserProfileDirectory *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001aa00`

## callees

- `0x180001d68`
- `0x18000219c`
- `0x18000d718`
- `0x18000d8ec`
- `0x18000e640`
- `0x180013c58`
- `0x18001adcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ae20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ae20`

## pseudocode

```c
void __fastcall UserenvTelemetry::DeleteUserProfileDirectory::StartActivity(
        UserenvTelemetry::DeleteUserProfileDirectory *this)
{
  const struct _tlgProvider_t *v2; // rax
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v7; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v8[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v9; // [rsp+60h] [rbp-38h]
  __int64 v10; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v12; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = ProfileAPILogging::Provider();
  v3 = v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = 0x1000000;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = v4 + 24, !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v12 = 4;
    v9 = &v7;
    v10 = 8;
    tlgWriteTransfer_EventWriteTransfer(v3, &unk_180022458, v4 + 8, v5, 4, v8);
  }
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18001adcc  mov     [rsp+arg_8], rbx
0x18001add1  push    rdi
0x18001add2  sub     rsp, 90h
0x18001add9  mov     rax, cs:__security_cookie
0x18001ade0  xor     rax, rsp
0x18001ade3  mov     [rsp+98h+var_18], rax
0x18001adeb  mov     rbx, rcx
0x18001adee  call    ?zInternalStart@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001adf3  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x18001adf8  mov     rdi, rax
0x18001adfb  mov     ecx, [rax]
0x18001adfd  cmp     ecx, 5
0x18001ae00  jbe     loc_18001AEB1
0x18001ae06  mov     rdx, 400000000000h
0x18001ae10  mov     rcx, rax
0x18001ae13  call    _tlgKeywordOn
0x18001ae18  test    al, al
0x18001ae1a  jz      loc_18001AEB1
0x18001ae20  call    cs:__imp_GetCurrentThreadId
0x18001ae27  nop     dword ptr [rax+rax+00h]
0x18001ae2c  mov     [rsp+98h+var_68], eax
0x18001ae30  mov     [rsp+98h+var_60], 1000000h
0x18001ae39  mov     r8, [rbx+110h]
0x18001ae40  cmp     byte ptr [r8+4], 0
0x18001ae45  jz      short loc_18001AE66
0x18001ae47  lea     r9, [r8+18h]
0x18001ae4b  cmp     dword ptr [r9], 0
0x18001ae4f  jnz     short loc_18001AE69
0x18001ae51  cmp     dword ptr [r9+4], 0
0x18001ae56  jnz     short loc_18001AE69
0x18001ae58  cmp     dword ptr [r9+8], 0
0x18001ae5d  jnz     short loc_18001AE69
0x18001ae5f  cmp     dword ptr [r9+0Ch], 0
0x18001ae64  jnz     short loc_18001AE69
0x18001ae66  xor     r9d, r9d
0x18001ae69  lea     rax, [rsp+98h+var_68]
0x18001ae6e  mov     [rsp+98h+var_28], rax
0x18001ae73  mov     ecx, 4
0x18001ae78  mov     [rsp+98h+var_20], rcx
0x18001ae7d  lea     rax, [rsp+98h+var_60]
0x18001ae82  mov     [rsp+98h+var_38], rax
0x18001ae87  mov     [rsp+98h+var_30], 8
0x18001ae90  add     r8, 8
0x18001ae94  lea     rax, [rsp+98h+var_58]
0x18001ae99  mov     [rsp+98h+var_70], rax
0x18001ae9e  mov     [rsp+98h+var_78], ecx
0x18001aea2  lea     rdx, unk_180022458
0x18001aea9  mov     rcx, rdi
0x18001aeac  call    _tlgWriteTransfer_EventWriteTransfer
0x18001aeb1  mov     rcx, rbx
0x18001aeb4  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001aeb9  nop
0x18001aeba  mov     rcx, [rsp+98h+var_18]
0x18001aec2  xor     rcx, rsp; StackCookie
0x18001aec5  call    __security_check_cookie
0x18001aeca  mov     rbx, [rsp+98h+arg_8]
0x18001aed2  add     rsp, 90h
0x18001aed9  pop     rdi
0x18001aeda  retn
```
