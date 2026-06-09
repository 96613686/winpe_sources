# Windows::Internal::CloudRequestor::InternalLogger::CommonHttpInterface_ProcessRequestAsync::StartActivity(void)

- ea: `0x180054d44`
- end: `0x180054ead`
- name: `?StartActivity@CommonHttpInterface_ProcessRequestAsync@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ`
- size: `361`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::CommonHttpInterface_ProcessRequestAsync *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180052980`

## callees

- `0x1800019cc`
- `0x180002810`
- `0x180009610`
- `0x18004460c`
- `0x180048950`
- `0x180054d44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054dbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054e76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054dbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054e76`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::CommonHttpInterface_ProcessRequestAsync::StartActivity(
        Windows::Internal::CloudRequestor::InternalLogger::CommonHttpInterface_ProcessRequestAsync *this)
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
      tlgWriteTransfer_EventWriteTransfer(v5, byte_18008E0B1, v6 + 8);
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
0x180054d44  mov     [rsp+arg_8], rbx
0x180054d49  mov     [rsp+arg_10], rbp
0x180054d4e  push    rdi
0x180054d4f  sub     rsp, 90h
0x180054d56  mov     rax, cs:__security_cookie
0x180054d5d  xor     rax, rsp
0x180054d60  mov     [rsp+98h+var_18], rax
0x180054d68  mov     rbx, rcx
0x180054d6b  call    ?zInternalStart@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180054d70  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x180054d75  lea     rdx, [rax+10h]
0x180054d79  mov     ebp, 8
0x180054d7e  test    rax, rax
0x180054d81  cmovz   rdx, rbp
0x180054d85  mov     rdi, [rdx]
0x180054d88  mov     eax, [rdi]
0x180054d8a  cmp     eax, 5
0x180054d8d  jbe     loc_180054E43
0x180054d93  mov     rcx, [rdi+18h]
0x180054d97  mov     rax, [rdi+10h]
0x180054d9b  mov     rdx, 200000000000h
0x180054da5  test    rdx, rax
0x180054da8  jz      loc_180054E43
0x180054dae  mov     rax, rcx
0x180054db1  and     rax, rdx
0x180054db4  cmp     rax, rcx
0x180054db7  jnz     loc_180054E43
0x180054dbd  call    cs:__imp_GetCurrentThreadId
0x180054dc3  mov     [rsp+98h+var_68], eax
0x180054dc7  mov     [rsp+98h+var_60], 1000000h
0x180054dd0  mov     r8, [rbx+110h]
0x180054dd7  cmp     byte ptr [r8+4], 0
0x180054ddc  jz      short loc_180054DFD
0x180054dde  lea     r9, [r8+18h]
0x180054de2  cmp     dword ptr [r9], 0
0x180054de6  jnz     short loc_180054E00
0x180054de8  cmp     dword ptr [r9+4], 0
0x180054ded  jnz     short loc_180054E00
0x180054def  cmp     dword ptr [r9+8], 0
0x180054df4  jnz     short loc_180054E00
0x180054df6  cmp     dword ptr [r9+0Ch], 0
0x180054dfb  jnz     short loc_180054E00
0x180054dfd  xor     r9d, r9d
0x180054e00  lea     rax, [rsp+98h+var_68]
0x180054e05  mov     [rsp+98h+var_28], rax
0x180054e0a  mov     ecx, 4
0x180054e0f  mov     [rsp+98h+var_20], rcx
0x180054e14  lea     rax, [rsp+98h+var_60]
0x180054e19  mov     [rsp+98h+var_38], rax
0x180054e1e  mov     [rsp+98h+var_30], rbp
0x180054e23  add     r8, rbp
0x180054e26  lea     rax, [rsp+98h+var_58]
0x180054e2b  mov     [rsp+98h+var_70], rax
0x180054e30  mov     [rsp+98h+var_78], ecx
0x180054e34  lea     rdx, byte_18008E0B1
0x180054e3b  mov     rcx, rdi
0x180054e3e  call    _tlgWriteTransfer_EventWriteTransfer
0x180054e43  cmp     dword ptr [rbx+138h], 0
0x180054e4a  jnz     short loc_180054E88
0x180054e4c  add     rbx, 120h
0x180054e53  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180054e5b  jz      short loc_180054E81
0x180054e5d  mov     dl, 1
0x180054e5f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180054e64  mov     [rbx], rax
0x180054e67  test    rax, rax
0x180054e6a  jz      short loc_180054E88
0x180054e6c  mov     rcx, [rax]
0x180054e6f  mov     [rbx+10h], rcx
0x180054e73  mov     [rax], rbx
0x180054e76  call    cs:__imp_GetCurrentThreadId
0x180054e7c  mov     [rbx+18h], eax
0x180054e7f  jmp     short loc_180054E88
0x180054e81  mov     qword ptr [rbx], 0
0x180054e88  mov     rcx, [rsp+98h+var_18]
0x180054e90  xor     rcx, rsp; StackCookie
0x180054e93  call    __security_check_cookie
0x180054e98  lea     r11, [rsp+98h+var_8]
0x180054ea0  mov     rbx, [r11+18h]
0x180054ea4  mov     rbp, [r11+20h]
0x180054ea8  mov     rsp, r11
0x180054eab  pop     rdi
0x180054eac  retn
```
