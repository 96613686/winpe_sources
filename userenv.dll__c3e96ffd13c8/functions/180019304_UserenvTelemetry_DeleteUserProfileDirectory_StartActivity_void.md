# UserenvTelemetry::DeleteUserProfileDirectory::StartActivity(void)

- ea: `0x180019304`
- end: `0x18001940d`
- name: `?StartActivity@DeleteUserProfileDirectory@UserenvTelemetry@@QEAAXXZ`
- size: `265`
- prototype: `void __fastcall(UserenvTelemetry::DeleteUserProfileDirectory *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180018ff4`

## callees

- `0x180001d58`
- `0x180002184`
- `0x18000cba4`
- `0x18000cc14`
- `0x18000d9b0`
- `0x180012b98`
- `0x180019304`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019358`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019358`

## pseudocode

```c
void __fastcall UserenvTelemetry::DeleteUserProfileDirectory::StartActivity(
        UserenvTelemetry::DeleteUserProfileDirectory *this)
{
  __int64 v2; // rcx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  const struct _tlgProvider_t *v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v9; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v10[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v3 = ProfileAPILogging::Provider(v2);
  v5 = v3;
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0x1000000;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v14 = 4;
    v11 = &v9;
    v12 = 8;
    tlgWriteTransfer_EventWriteTransfer(v5, &unk_180021418, v6 + 8, v7, 4, v10);
  }
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180019304  mov     [rsp+arg_8], rbx
0x180019309  push    rdi
0x18001930a  sub     rsp, 90h
0x180019311  mov     rax, cs:__security_cookie
0x180019318  xor     rax, rsp
0x18001931b  mov     [rsp+98h+var_18], rax
0x180019323  mov     rbx, rcx
0x180019326  call    ?zInternalStart@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001932b  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x180019330  mov     rdi, rax
0x180019333  mov     ecx, [rax]
0x180019335  cmp     ecx, 5
0x180019338  jbe     loc_1800193E3
0x18001933e  mov     rdx, 400000000000h
0x180019348  mov     rcx, rax
0x18001934b  call    _tlgKeywordOn
0x180019350  test    al, al
0x180019352  jz      loc_1800193E3
0x180019358  call    cs:__imp_GetCurrentThreadId
0x18001935e  mov     [rsp+98h+var_68], eax
0x180019362  mov     [rsp+98h+var_60], 1000000h
0x18001936b  mov     r8, [rbx+110h]
0x180019372  cmp     byte ptr [r8+4], 0
0x180019377  jz      short loc_180019398
0x180019379  lea     r9, [r8+18h]
0x18001937d  cmp     dword ptr [r9], 0
0x180019381  jnz     short loc_18001939B
0x180019383  cmp     dword ptr [r9+4], 0
0x180019388  jnz     short loc_18001939B
0x18001938a  cmp     dword ptr [r9+8], 0
0x18001938f  jnz     short loc_18001939B
0x180019391  cmp     dword ptr [r9+0Ch], 0
0x180019396  jnz     short loc_18001939B
0x180019398  xor     r9d, r9d
0x18001939b  lea     rax, [rsp+98h+var_68]
0x1800193a0  mov     [rsp+98h+var_28], rax
0x1800193a5  mov     ecx, 4
0x1800193aa  mov     [rsp+98h+var_20], rcx
0x1800193af  lea     rax, [rsp+98h+var_60]
0x1800193b4  mov     [rsp+98h+var_38], rax
0x1800193b9  mov     [rsp+98h+var_30], 8
0x1800193c2  add     r8, 8
0x1800193c6  lea     rax, [rsp+98h+var_58]
0x1800193cb  mov     [rsp+98h+var_70], rax
0x1800193d0  mov     [rsp+98h+var_78], ecx
0x1800193d4  lea     rdx, unk_180021418
0x1800193db  mov     rcx, rdi
0x1800193de  call    _tlgWriteTransfer_EventWriteTransfer
0x1800193e3  mov     rcx, rbx
0x1800193e6  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800193eb  nop
0x1800193ec  mov     rcx, [rsp+98h+var_18]
0x1800193f4  xor     rcx, rsp; StackCookie
0x1800193f7  call    __security_check_cookie
0x1800193fc  mov     rbx, [rsp+98h+arg_8]
0x180019404  add     rsp, 90h
0x18001940b  pop     rdi
0x18001940c  retn
```
