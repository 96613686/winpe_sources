# Windows::Internal::CloudRequestor::InternalLogger::HomeCloudHandler_GetHomeCloudAsync::StartActivity(void)

- ea: `0x180066f14`
- end: `0x18006707d`
- name: `?StartActivity@HomeCloudHandler_GetHomeCloudAsync@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ`
- size: `361`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::HomeCloudHandler_GetHomeCloudAsync *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180061d10`

## callees

- `0x1800019cc`
- `0x180002810`
- `0x180009610`
- `0x18004460c`
- `0x180048950`
- `0x180066f14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066f8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067046`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066f8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067046`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::HomeCloudHandler_GetHomeCloudAsync::StartActivity(
        Windows::Internal::CloudRequestor::InternalLogger::HomeCloudHandler_GetHomeCloudAsync *this)
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
      tlgWriteTransfer_EventWriteTransfer(v5, &byte_18008E4F7, v6 + 8);
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
0x180066f14  mov     [rsp+arg_8], rbx
0x180066f19  mov     [rsp+arg_10], rbp
0x180066f1e  push    rdi
0x180066f1f  sub     rsp, 90h
0x180066f26  mov     rax, cs:__security_cookie
0x180066f2d  xor     rax, rsp
0x180066f30  mov     [rsp+98h+var_18], rax
0x180066f38  mov     rbx, rcx
0x180066f3b  call    ?zInternalStart@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180066f40  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x180066f45  lea     rdx, [rax+10h]
0x180066f49  mov     ebp, 8
0x180066f4e  test    rax, rax
0x180066f51  cmovz   rdx, rbp
0x180066f55  mov     rdi, [rdx]
0x180066f58  mov     eax, [rdi]
0x180066f5a  cmp     eax, 5
0x180066f5d  jbe     loc_180067013
0x180066f63  mov     rcx, [rdi+18h]
0x180066f67  mov     rax, [rdi+10h]
0x180066f6b  mov     rdx, 200000000000h
0x180066f75  test    rdx, rax
0x180066f78  jz      loc_180067013
0x180066f7e  mov     rax, rcx
0x180066f81  and     rax, rdx
0x180066f84  cmp     rax, rcx
0x180066f87  jnz     loc_180067013
0x180066f8d  call    cs:__imp_GetCurrentThreadId
0x180066f93  mov     [rsp+98h+var_68], eax
0x180066f97  mov     [rsp+98h+var_60], 1000000h
0x180066fa0  mov     r8, [rbx+110h]
0x180066fa7  cmp     byte ptr [r8+4], 0
0x180066fac  jz      short loc_180066FCD
0x180066fae  lea     r9, [r8+18h]
0x180066fb2  cmp     dword ptr [r9], 0
0x180066fb6  jnz     short loc_180066FD0
0x180066fb8  cmp     dword ptr [r9+4], 0
0x180066fbd  jnz     short loc_180066FD0
0x180066fbf  cmp     dword ptr [r9+8], 0
0x180066fc4  jnz     short loc_180066FD0
0x180066fc6  cmp     dword ptr [r9+0Ch], 0
0x180066fcb  jnz     short loc_180066FD0
0x180066fcd  xor     r9d, r9d
0x180066fd0  lea     rax, [rsp+98h+var_68]
0x180066fd5  mov     [rsp+98h+var_28], rax
0x180066fda  mov     ecx, 4
0x180066fdf  mov     [rsp+98h+var_20], rcx
0x180066fe4  lea     rax, [rsp+98h+var_60]
0x180066fe9  mov     [rsp+98h+var_38], rax
0x180066fee  mov     [rsp+98h+var_30], rbp
0x180066ff3  add     r8, rbp
0x180066ff6  lea     rax, [rsp+98h+var_58]
0x180066ffb  mov     [rsp+98h+var_70], rax
0x180067000  mov     [rsp+98h+var_78], ecx
0x180067004  lea     rdx, byte_18008E4F7
0x18006700b  mov     rcx, rdi
0x18006700e  call    _tlgWriteTransfer_EventWriteTransfer
0x180067013  cmp     dword ptr [rbx+138h], 0
0x18006701a  jnz     short loc_180067058
0x18006701c  add     rbx, 120h
0x180067023  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18006702b  jz      short loc_180067051
0x18006702d  mov     dl, 1
0x18006702f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180067034  mov     [rbx], rax
0x180067037  test    rax, rax
0x18006703a  jz      short loc_180067058
0x18006703c  mov     rcx, [rax]
0x18006703f  mov     [rbx+10h], rcx
0x180067043  mov     [rax], rbx
0x180067046  call    cs:__imp_GetCurrentThreadId
0x18006704c  mov     [rbx+18h], eax
0x18006704f  jmp     short loc_180067058
0x180067051  mov     qword ptr [rbx], 0
0x180067058  mov     rcx, [rsp+98h+var_18]
0x180067060  xor     rcx, rsp; StackCookie
0x180067063  call    __security_check_cookie
0x180067068  lea     r11, [rsp+98h+var_8]
0x180067070  mov     rbx, [r11+18h]
0x180067074  mov     rbp, [r11+20h]
0x180067078  mov     rsp, r11
0x18006707b  pop     rdi
0x18006707c  retn
```
