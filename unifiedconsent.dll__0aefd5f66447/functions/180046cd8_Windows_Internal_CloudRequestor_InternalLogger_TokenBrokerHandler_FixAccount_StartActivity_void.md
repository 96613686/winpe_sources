# Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_FixAccount::StartActivity(void)

- ea: `0x180046cd8`
- end: `0x180046e41`
- name: `?StartActivity@TokenBrokerHandler_FixAccount@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ`
- size: `361`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_FixAccount *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041410`

## callees

- `0x1800019cc`
- `0x180002810`
- `0x180009610`
- `0x18004460c`
- `0x180046cd8`
- `0x180048950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046d51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046e0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046d51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046e0a`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_FixAccount::StartActivity(
        Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_FixAccount *this)
{
  struct Windows::Internal::CloudRequestor::InternalLogger *v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rdx
  _DWORD *v5; // rdi
  __int64 v6; // r8
  char *v7; // rbx
  _QWORD *Local; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v10[9]; // [rsp+38h] [rbp-60h] BYREF

  wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = Windows::Internal::CloudRequestor::InternalLogger::Instance();
  v4 = (__int64)v2 + 16;
  if ( !v2 )
    v4 = 8;
  v5 = *(_DWORD **)v4;
  if ( **(_DWORD **)v4 > 5u )
  {
    v3 = *((_QWORD *)v5 + 3);
    v4 = 0x200000000000LL;
    if ( (*((_QWORD *)v5 + 2) & 0x200000000000LL) != 0 && (v3 & 0x200000000000LL) == v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10[0] = 0x1000000;
      v6 = *((_QWORD *)this + 34);
      v10[7] = &CurrentThreadId;
      v10[8] = 4;
      v10[5] = v10;
      v10[6] = 8;
      tlgWriteTransfer_EventWriteTransfer(v5, &unk_18008D658, v6 + 8);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v7 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v4) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          v4);
      *(_QWORD *)v7 = Local;
      if ( Local )
      {
        *((_QWORD *)v7 + 2) = *Local;
        *Local = v7;
        *((_DWORD *)v7 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v7 = 0;
    }
  }
}

```

## disassembly

```asm
0x180046cd8  mov     [rsp+arg_8], rbx
0x180046cdd  mov     [rsp+arg_10], rbp
0x180046ce2  push    rdi
0x180046ce3  sub     rsp, 90h
0x180046cea  mov     rax, cs:__security_cookie
0x180046cf1  xor     rax, rsp
0x180046cf4  mov     [rsp+98h+var_18], rax
0x180046cfc  mov     rbx, rcx
0x180046cff  call    ?zInternalStart@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180046d04  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x180046d09  lea     rdx, [rax+10h]
0x180046d0d  mov     ebp, 8
0x180046d12  test    rax, rax
0x180046d15  cmovz   rdx, rbp
0x180046d19  mov     rdi, [rdx]
0x180046d1c  mov     eax, [rdi]
0x180046d1e  cmp     eax, 5
0x180046d21  jbe     loc_180046DD7
0x180046d27  mov     rcx, [rdi+18h]
0x180046d2b  mov     rax, [rdi+10h]
0x180046d2f  mov     rdx, 200000000000h
0x180046d39  test    rdx, rax
0x180046d3c  jz      loc_180046DD7
0x180046d42  mov     rax, rcx
0x180046d45  and     rax, rdx
0x180046d48  cmp     rax, rcx
0x180046d4b  jnz     loc_180046DD7
0x180046d51  call    cs:__imp_GetCurrentThreadId
0x180046d57  mov     [rsp+98h+var_68], eax
0x180046d5b  mov     [rsp+98h+var_60], 1000000h
0x180046d64  mov     r8, [rbx+110h]
0x180046d6b  cmp     byte ptr [r8+4], 0
0x180046d70  jz      short loc_180046D91
0x180046d72  lea     r9, [r8+18h]
0x180046d76  cmp     dword ptr [r9], 0
0x180046d7a  jnz     short loc_180046D94
0x180046d7c  cmp     dword ptr [r9+4], 0
0x180046d81  jnz     short loc_180046D94
0x180046d83  cmp     dword ptr [r9+8], 0
0x180046d88  jnz     short loc_180046D94
0x180046d8a  cmp     dword ptr [r9+0Ch], 0
0x180046d8f  jnz     short loc_180046D94
0x180046d91  xor     r9d, r9d
0x180046d94  lea     rax, [rsp+98h+var_68]
0x180046d99  mov     [rsp+98h+var_28], rax
0x180046d9e  mov     ecx, 4
0x180046da3  mov     [rsp+98h+var_20], rcx
0x180046da8  lea     rax, [rsp+98h+var_60]
0x180046dad  mov     [rsp+98h+var_38], rax
0x180046db2  mov     [rsp+98h+var_30], rbp
0x180046db7  add     r8, rbp
0x180046dba  lea     rax, [rsp+98h+var_58]
0x180046dbf  mov     [rsp+98h+var_70], rax
0x180046dc4  mov     [rsp+98h+var_78], ecx
0x180046dc8  lea     rdx, unk_18008D658
0x180046dcf  mov     rcx, rdi
0x180046dd2  call    _tlgWriteTransfer_EventWriteTransfer
0x180046dd7  cmp     dword ptr [rbx+138h], 0
0x180046dde  jnz     short loc_180046E1C
0x180046de0  add     rbx, 120h
0x180046de7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180046def  jz      short loc_180046E15
0x180046df1  mov     dl, 1
0x180046df3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180046df8  mov     [rbx], rax
0x180046dfb  test    rax, rax
0x180046dfe  jz      short loc_180046E1C
0x180046e00  mov     rcx, [rax]
0x180046e03  mov     [rbx+10h], rcx
0x180046e07  mov     [rax], rbx
0x180046e0a  call    cs:__imp_GetCurrentThreadId
0x180046e10  mov     [rbx+18h], eax
0x180046e13  jmp     short loc_180046E1C
0x180046e15  mov     qword ptr [rbx], 0
0x180046e1c  mov     rcx, [rsp+98h+var_18]
0x180046e24  xor     rcx, rsp; StackCookie
0x180046e27  call    __security_check_cookie
0x180046e2c  lea     r11, [rsp+98h+var_8]
0x180046e34  mov     rbx, [r11+18h]
0x180046e38  mov     rbp, [r11+20h]
0x180046e3c  mov     rsp, r11
0x180046e3f  pop     rdi
0x180046e40  retn
```
