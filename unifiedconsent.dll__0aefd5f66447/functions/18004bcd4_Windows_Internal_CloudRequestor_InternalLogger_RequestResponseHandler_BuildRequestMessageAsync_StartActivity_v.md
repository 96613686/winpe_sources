# Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync::StartActivity(void)

- ea: `0x18004bcd4`
- end: `0x18004be3d`
- name: `?StartActivity@RequestResponseHandler_BuildRequestMessageAsync@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ`
- size: `361`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180049ec0`

## callees

- `0x1800019cc`
- `0x180002810`
- `0x180009610`
- `0x18004460c`
- `0x180048950`
- `0x18004bcd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bd4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004be06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bd4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004be06`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync::StartActivity(
        Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync *this)
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
      tlgWriteTransfer_EventWriteTransfer(v5, byte_18008DC49, v6 + 8);
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
0x18004bcd4  mov     [rsp+arg_8], rbx
0x18004bcd9  mov     [rsp+arg_10], rbp
0x18004bcde  push    rdi
0x18004bcdf  sub     rsp, 90h
0x18004bce6  mov     rax, cs:__security_cookie
0x18004bced  xor     rax, rsp
0x18004bcf0  mov     [rsp+98h+var_18], rax
0x18004bcf8  mov     rbx, rcx
0x18004bcfb  call    ?zInternalStart@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18004bd00  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x18004bd05  lea     rdx, [rax+10h]
0x18004bd09  mov     ebp, 8
0x18004bd0e  test    rax, rax
0x18004bd11  cmovz   rdx, rbp
0x18004bd15  mov     rdi, [rdx]
0x18004bd18  mov     eax, [rdi]
0x18004bd1a  cmp     eax, 5
0x18004bd1d  jbe     loc_18004BDD3
0x18004bd23  mov     rcx, [rdi+18h]
0x18004bd27  mov     rax, [rdi+10h]
0x18004bd2b  mov     rdx, 200000000000h
0x18004bd35  test    rdx, rax
0x18004bd38  jz      loc_18004BDD3
0x18004bd3e  mov     rax, rcx
0x18004bd41  and     rax, rdx
0x18004bd44  cmp     rax, rcx
0x18004bd47  jnz     loc_18004BDD3
0x18004bd4d  call    cs:__imp_GetCurrentThreadId
0x18004bd53  mov     [rsp+98h+var_68], eax
0x18004bd57  mov     [rsp+98h+var_60], 1000000h
0x18004bd60  mov     r8, [rbx+110h]
0x18004bd67  cmp     byte ptr [r8+4], 0
0x18004bd6c  jz      short loc_18004BD8D
0x18004bd6e  lea     r9, [r8+18h]
0x18004bd72  cmp     dword ptr [r9], 0
0x18004bd76  jnz     short loc_18004BD90
0x18004bd78  cmp     dword ptr [r9+4], 0
0x18004bd7d  jnz     short loc_18004BD90
0x18004bd7f  cmp     dword ptr [r9+8], 0
0x18004bd84  jnz     short loc_18004BD90
0x18004bd86  cmp     dword ptr [r9+0Ch], 0
0x18004bd8b  jnz     short loc_18004BD90
0x18004bd8d  xor     r9d, r9d
0x18004bd90  lea     rax, [rsp+98h+var_68]
0x18004bd95  mov     [rsp+98h+var_28], rax
0x18004bd9a  mov     ecx, 4
0x18004bd9f  mov     [rsp+98h+var_20], rcx
0x18004bda4  lea     rax, [rsp+98h+var_60]
0x18004bda9  mov     [rsp+98h+var_38], rax
0x18004bdae  mov     [rsp+98h+var_30], rbp
0x18004bdb3  add     r8, rbp
0x18004bdb6  lea     rax, [rsp+98h+var_58]
0x18004bdbb  mov     [rsp+98h+var_70], rax
0x18004bdc0  mov     [rsp+98h+var_78], ecx
0x18004bdc4  lea     rdx, byte_18008DC49
0x18004bdcb  mov     rcx, rdi
0x18004bdce  call    _tlgWriteTransfer_EventWriteTransfer
0x18004bdd3  cmp     dword ptr [rbx+138h], 0
0x18004bdda  jnz     short loc_18004BE18
0x18004bddc  add     rbx, 120h
0x18004bde3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004bdeb  jz      short loc_18004BE11
0x18004bded  mov     dl, 1
0x18004bdef  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18004bdf4  mov     [rbx], rax
0x18004bdf7  test    rax, rax
0x18004bdfa  jz      short loc_18004BE18
0x18004bdfc  mov     rcx, [rax]
0x18004bdff  mov     [rbx+10h], rcx
0x18004be03  mov     [rax], rbx
0x18004be06  call    cs:__imp_GetCurrentThreadId
0x18004be0c  mov     [rbx+18h], eax
0x18004be0f  jmp     short loc_18004BE18
0x18004be11  mov     qword ptr [rbx], 0
0x18004be18  mov     rcx, [rsp+98h+var_18]
0x18004be20  xor     rcx, rsp; StackCookie
0x18004be23  call    __security_check_cookie
0x18004be28  lea     r11, [rsp+98h+var_8]
0x18004be30  mov     rbx, [r11+18h]
0x18004be34  mov     rbp, [r11+20h]
0x18004be38  mov     rsp, r11
0x18004be3b  pop     rdi
0x18004be3c  retn
```
