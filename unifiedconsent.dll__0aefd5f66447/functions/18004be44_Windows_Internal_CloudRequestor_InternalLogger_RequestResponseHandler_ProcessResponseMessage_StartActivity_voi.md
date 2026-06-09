# Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_ProcessResponseMessage::StartActivity(void)

- ea: `0x18004be44`
- end: `0x18004bfad`
- name: `?StartActivity@RequestResponseHandler_ProcessResponseMessage@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ`
- size: `361`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_ProcessResponseMessage *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004b950`

## callees

- `0x1800019cc`
- `0x180002810`
- `0x180009610`
- `0x18004460c`
- `0x180048950`
- `0x18004be44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bebd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bf76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bebd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bf76`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_ProcessResponseMessage::StartActivity(
        Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_ProcessResponseMessage *this)
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
      tlgWriteTransfer_EventWriteTransfer(v5, byte_18008DA31, v6 + 8);
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
0x18004be44  mov     [rsp+arg_8], rbx
0x18004be49  mov     [rsp+arg_10], rbp
0x18004be4e  push    rdi
0x18004be4f  sub     rsp, 90h
0x18004be56  mov     rax, cs:__security_cookie
0x18004be5d  xor     rax, rsp
0x18004be60  mov     [rsp+98h+var_18], rax
0x18004be68  mov     rbx, rcx
0x18004be6b  call    ?zInternalStart@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18004be70  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x18004be75  lea     rdx, [rax+10h]
0x18004be79  mov     ebp, 8
0x18004be7e  test    rax, rax
0x18004be81  cmovz   rdx, rbp
0x18004be85  mov     rdi, [rdx]
0x18004be88  mov     eax, [rdi]
0x18004be8a  cmp     eax, 5
0x18004be8d  jbe     loc_18004BF43
0x18004be93  mov     rcx, [rdi+18h]
0x18004be97  mov     rax, [rdi+10h]
0x18004be9b  mov     rdx, 200000000000h
0x18004bea5  test    rdx, rax
0x18004bea8  jz      loc_18004BF43
0x18004beae  mov     rax, rcx
0x18004beb1  and     rax, rdx
0x18004beb4  cmp     rax, rcx
0x18004beb7  jnz     loc_18004BF43
0x18004bebd  call    cs:__imp_GetCurrentThreadId
0x18004bec3  mov     [rsp+98h+var_68], eax
0x18004bec7  mov     [rsp+98h+var_60], 1000000h
0x18004bed0  mov     r8, [rbx+110h]
0x18004bed7  cmp     byte ptr [r8+4], 0
0x18004bedc  jz      short loc_18004BEFD
0x18004bede  lea     r9, [r8+18h]
0x18004bee2  cmp     dword ptr [r9], 0
0x18004bee6  jnz     short loc_18004BF00
0x18004bee8  cmp     dword ptr [r9+4], 0
0x18004beed  jnz     short loc_18004BF00
0x18004beef  cmp     dword ptr [r9+8], 0
0x18004bef4  jnz     short loc_18004BF00
0x18004bef6  cmp     dword ptr [r9+0Ch], 0
0x18004befb  jnz     short loc_18004BF00
0x18004befd  xor     r9d, r9d
0x18004bf00  lea     rax, [rsp+98h+var_68]
0x18004bf05  mov     [rsp+98h+var_28], rax
0x18004bf0a  mov     ecx, 4
0x18004bf0f  mov     [rsp+98h+var_20], rcx
0x18004bf14  lea     rax, [rsp+98h+var_60]
0x18004bf19  mov     [rsp+98h+var_38], rax
0x18004bf1e  mov     [rsp+98h+var_30], rbp
0x18004bf23  add     r8, rbp
0x18004bf26  lea     rax, [rsp+98h+var_58]
0x18004bf2b  mov     [rsp+98h+var_70], rax
0x18004bf30  mov     [rsp+98h+var_78], ecx
0x18004bf34  lea     rdx, byte_18008DA31
0x18004bf3b  mov     rcx, rdi
0x18004bf3e  call    _tlgWriteTransfer_EventWriteTransfer
0x18004bf43  cmp     dword ptr [rbx+138h], 0
0x18004bf4a  jnz     short loc_18004BF88
0x18004bf4c  add     rbx, 120h
0x18004bf53  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004bf5b  jz      short loc_18004BF81
0x18004bf5d  mov     dl, 1
0x18004bf5f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18004bf64  mov     [rbx], rax
0x18004bf67  test    rax, rax
0x18004bf6a  jz      short loc_18004BF88
0x18004bf6c  mov     rcx, [rax]
0x18004bf6f  mov     [rbx+10h], rcx
0x18004bf73  mov     [rax], rbx
0x18004bf76  call    cs:__imp_GetCurrentThreadId
0x18004bf7c  mov     [rbx+18h], eax
0x18004bf7f  jmp     short loc_18004BF88
0x18004bf81  mov     qword ptr [rbx], 0
0x18004bf88  mov     rcx, [rsp+98h+var_18]
0x18004bf90  xor     rcx, rsp; StackCookie
0x18004bf93  call    __security_check_cookie
0x18004bf98  lea     r11, [rsp+98h+var_8]
0x18004bfa0  mov     rbx, [r11+18h]
0x18004bfa4  mov     rbp, [r11+20h]
0x18004bfa8  mov     rsp, r11
0x18004bfab  pop     rdi
0x18004bfac  retn
```
