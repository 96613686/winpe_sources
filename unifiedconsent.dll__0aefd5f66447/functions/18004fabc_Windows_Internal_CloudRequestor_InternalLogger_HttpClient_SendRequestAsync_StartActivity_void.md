# Windows::Internal::CloudRequestor::InternalLogger::HttpClient_SendRequestAsync::StartActivity(void)

- ea: `0x18004fabc`
- end: `0x18004fc25`
- name: `?StartActivity@HttpClient_SendRequestAsync@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ`
- size: `361`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::HttpClient_SendRequestAsync *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004f160`

## callees

- `0x1800019cc`
- `0x180002810`
- `0x180009610`
- `0x18004460c`
- `0x180048950`
- `0x18004fabc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fb35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fbee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fb35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004fbee`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::HttpClient_SendRequestAsync::StartActivity(
        Windows::Internal::CloudRequestor::InternalLogger::HttpClient_SendRequestAsync *this)
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
      tlgWriteTransfer_EventWriteTransfer(v5, &byte_18008DE67, v6 + 8);
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
0x18004fabc  mov     [rsp+arg_8], rbx
0x18004fac1  mov     [rsp+arg_10], rbp
0x18004fac6  push    rdi
0x18004fac7  sub     rsp, 90h
0x18004face  mov     rax, cs:__security_cookie
0x18004fad5  xor     rax, rsp
0x18004fad8  mov     [rsp+98h+var_18], rax
0x18004fae0  mov     rbx, rcx
0x18004fae3  call    ?zInternalStart@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18004fae8  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x18004faed  lea     rdx, [rax+10h]
0x18004faf1  mov     ebp, 8
0x18004faf6  test    rax, rax
0x18004faf9  cmovz   rdx, rbp
0x18004fafd  mov     rdi, [rdx]
0x18004fb00  mov     eax, [rdi]
0x18004fb02  cmp     eax, 5
0x18004fb05  jbe     loc_18004FBBB
0x18004fb0b  mov     rcx, [rdi+18h]
0x18004fb0f  mov     rax, [rdi+10h]
0x18004fb13  mov     rdx, 200000000000h
0x18004fb1d  test    rdx, rax
0x18004fb20  jz      loc_18004FBBB
0x18004fb26  mov     rax, rcx
0x18004fb29  and     rax, rdx
0x18004fb2c  cmp     rax, rcx
0x18004fb2f  jnz     loc_18004FBBB
0x18004fb35  call    cs:__imp_GetCurrentThreadId
0x18004fb3b  mov     [rsp+98h+var_68], eax
0x18004fb3f  mov     [rsp+98h+var_60], 1000000h
0x18004fb48  mov     r8, [rbx+110h]
0x18004fb4f  cmp     byte ptr [r8+4], 0
0x18004fb54  jz      short loc_18004FB75
0x18004fb56  lea     r9, [r8+18h]
0x18004fb5a  cmp     dword ptr [r9], 0
0x18004fb5e  jnz     short loc_18004FB78
0x18004fb60  cmp     dword ptr [r9+4], 0
0x18004fb65  jnz     short loc_18004FB78
0x18004fb67  cmp     dword ptr [r9+8], 0
0x18004fb6c  jnz     short loc_18004FB78
0x18004fb6e  cmp     dword ptr [r9+0Ch], 0
0x18004fb73  jnz     short loc_18004FB78
0x18004fb75  xor     r9d, r9d
0x18004fb78  lea     rax, [rsp+98h+var_68]
0x18004fb7d  mov     [rsp+98h+var_28], rax
0x18004fb82  mov     ecx, 4
0x18004fb87  mov     [rsp+98h+var_20], rcx
0x18004fb8c  lea     rax, [rsp+98h+var_60]
0x18004fb91  mov     [rsp+98h+var_38], rax
0x18004fb96  mov     [rsp+98h+var_30], rbp
0x18004fb9b  add     r8, rbp
0x18004fb9e  lea     rax, [rsp+98h+var_58]
0x18004fba3  mov     [rsp+98h+var_70], rax
0x18004fba8  mov     [rsp+98h+var_78], ecx
0x18004fbac  lea     rdx, byte_18008DE67
0x18004fbb3  mov     rcx, rdi
0x18004fbb6  call    _tlgWriteTransfer_EventWriteTransfer
0x18004fbbb  cmp     dword ptr [rbx+138h], 0
0x18004fbc2  jnz     short loc_18004FC00
0x18004fbc4  add     rbx, 120h
0x18004fbcb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004fbd3  jz      short loc_18004FBF9
0x18004fbd5  mov     dl, 1
0x18004fbd7  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18004fbdc  mov     [rbx], rax
0x18004fbdf  test    rax, rax
0x18004fbe2  jz      short loc_18004FC00
0x18004fbe4  mov     rcx, [rax]
0x18004fbe7  mov     [rbx+10h], rcx
0x18004fbeb  mov     [rax], rbx
0x18004fbee  call    cs:__imp_GetCurrentThreadId
0x18004fbf4  mov     [rbx+18h], eax
0x18004fbf7  jmp     short loc_18004FC00
0x18004fbf9  mov     qword ptr [rbx], 0
0x18004fc00  mov     rcx, [rsp+98h+var_18]
0x18004fc08  xor     rcx, rsp; StackCookie
0x18004fc0b  call    __security_check_cookie
0x18004fc10  lea     r11, [rsp+98h+var_8]
0x18004fc18  mov     rbx, [r11+18h]
0x18004fc1c  mov     rbp, [r11+20h]
0x18004fc20  mov     rsp, r11
0x18004fc23  pop     rdi
0x18004fc24  retn
```
