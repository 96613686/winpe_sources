# Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::StartActivity(void)

- ea: `0x180046e48`
- end: `0x180046fb1`
- name: `?StartActivity@TokenBrokerHandler_GetTokenAsync@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ`
- size: `361`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043000`

## callees

- `0x1800019cc`
- `0x180002810`
- `0x180009610`
- `0x18004460c`
- `0x180046e48`
- `0x180048950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046ec1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046f7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046ec1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046f7a`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::StartActivity(
        Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync *this)
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
      tlgWriteTransfer_EventWriteTransfer(v5, &unk_18008D840, v6 + 8);
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
0x180046e48  mov     [rsp+arg_8], rbx
0x180046e4d  mov     [rsp+arg_10], rbp
0x180046e52  push    rdi
0x180046e53  sub     rsp, 90h
0x180046e5a  mov     rax, cs:__security_cookie
0x180046e61  xor     rax, rsp
0x180046e64  mov     [rsp+98h+var_18], rax
0x180046e6c  mov     rbx, rcx
0x180046e6f  call    ?zInternalStart@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180046e74  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x180046e79  lea     rdx, [rax+10h]
0x180046e7d  mov     ebp, 8
0x180046e82  test    rax, rax
0x180046e85  cmovz   rdx, rbp
0x180046e89  mov     rdi, [rdx]
0x180046e8c  mov     eax, [rdi]
0x180046e8e  cmp     eax, 5
0x180046e91  jbe     loc_180046F47
0x180046e97  mov     rcx, [rdi+18h]
0x180046e9b  mov     rax, [rdi+10h]
0x180046e9f  mov     rdx, 200000000000h
0x180046ea9  test    rdx, rax
0x180046eac  jz      loc_180046F47
0x180046eb2  mov     rax, rcx
0x180046eb5  and     rax, rdx
0x180046eb8  cmp     rax, rcx
0x180046ebb  jnz     loc_180046F47
0x180046ec1  call    cs:__imp_GetCurrentThreadId
0x180046ec7  mov     [rsp+98h+var_68], eax
0x180046ecb  mov     [rsp+98h+var_60], 1000000h
0x180046ed4  mov     r8, [rbx+110h]
0x180046edb  cmp     byte ptr [r8+4], 0
0x180046ee0  jz      short loc_180046F01
0x180046ee2  lea     r9, [r8+18h]
0x180046ee6  cmp     dword ptr [r9], 0
0x180046eea  jnz     short loc_180046F04
0x180046eec  cmp     dword ptr [r9+4], 0
0x180046ef1  jnz     short loc_180046F04
0x180046ef3  cmp     dword ptr [r9+8], 0
0x180046ef8  jnz     short loc_180046F04
0x180046efa  cmp     dword ptr [r9+0Ch], 0
0x180046eff  jnz     short loc_180046F04
0x180046f01  xor     r9d, r9d
0x180046f04  lea     rax, [rsp+98h+var_68]
0x180046f09  mov     [rsp+98h+var_28], rax
0x180046f0e  mov     ecx, 4
0x180046f13  mov     [rsp+98h+var_20], rcx
0x180046f18  lea     rax, [rsp+98h+var_60]
0x180046f1d  mov     [rsp+98h+var_38], rax
0x180046f22  mov     [rsp+98h+var_30], rbp
0x180046f27  add     r8, rbp
0x180046f2a  lea     rax, [rsp+98h+var_58]
0x180046f2f  mov     [rsp+98h+var_70], rax
0x180046f34  mov     [rsp+98h+var_78], ecx
0x180046f38  lea     rdx, unk_18008D840
0x180046f3f  mov     rcx, rdi
0x180046f42  call    _tlgWriteTransfer_EventWriteTransfer
0x180046f47  cmp     dword ptr [rbx+138h], 0
0x180046f4e  jnz     short loc_180046F8C
0x180046f50  add     rbx, 120h
0x180046f57  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180046f5f  jz      short loc_180046F85
0x180046f61  mov     dl, 1
0x180046f63  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180046f68  mov     [rbx], rax
0x180046f6b  test    rax, rax
0x180046f6e  jz      short loc_180046F8C
0x180046f70  mov     rcx, [rax]
0x180046f73  mov     [rbx+10h], rcx
0x180046f77  mov     [rax], rbx
0x180046f7a  call    cs:__imp_GetCurrentThreadId
0x180046f80  mov     [rbx+18h], eax
0x180046f83  jmp     short loc_180046F8C
0x180046f85  mov     qword ptr [rbx], 0
0x180046f8c  mov     rcx, [rsp+98h+var_18]
0x180046f94  xor     rcx, rsp; StackCookie
0x180046f97  call    __security_check_cookie
0x180046f9c  lea     r11, [rsp+98h+var_8]
0x180046fa4  mov     rbx, [r11+18h]
0x180046fa8  mov     rbp, [r11+20h]
0x180046fac  mov     rsp, r11
0x180046faf  pop     rdi
0x180046fb0  retn
```
