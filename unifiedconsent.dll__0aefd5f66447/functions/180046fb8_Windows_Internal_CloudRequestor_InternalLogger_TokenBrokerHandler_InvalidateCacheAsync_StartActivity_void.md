# Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::StartActivity(void)

- ea: `0x180046fb8`
- end: `0x180047121`
- name: `?StartActivity@TokenBrokerHandler_InvalidateCacheAsync@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ`
- size: `361`
- prototype: `void __fastcall(Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800446f0`

## callees

- `0x1800019cc`
- `0x180002810`
- `0x180009610`
- `0x18004460c`
- `0x180046fb8`
- `0x180048950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047031`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800470ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047031`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800470ea`

## pseudocode

```c
void __fastcall Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::StartActivity(
        Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync *this)
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
      tlgWriteTransfer_EventWriteTransfer(v5, word_18008D4BA, v6 + 8);
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
0x180046fb8  mov     [rsp+arg_8], rbx
0x180046fbd  mov     [rsp+arg_10], rbp
0x180046fc2  push    rdi
0x180046fc3  sub     rsp, 90h
0x180046fca  mov     rax, cs:__security_cookie
0x180046fd1  xor     rax, rsp
0x180046fd4  mov     [rsp+98h+var_18], rax
0x180046fdc  mov     rbx, rcx
0x180046fdf  call    ?zInternalStart@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180046fe4  call    ?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ; Windows::Internal::CloudRequestor::InternalLogger::Instance(void)
0x180046fe9  lea     rdx, [rax+10h]
0x180046fed  mov     ebp, 8
0x180046ff2  test    rax, rax
0x180046ff5  cmovz   rdx, rbp
0x180046ff9  mov     rdi, [rdx]
0x180046ffc  mov     eax, [rdi]
0x180046ffe  cmp     eax, 5
0x180047001  jbe     loc_1800470B7
0x180047007  mov     rcx, [rdi+18h]
0x18004700b  mov     rax, [rdi+10h]
0x18004700f  mov     rdx, 200000000000h
0x180047019  test    rdx, rax
0x18004701c  jz      loc_1800470B7
0x180047022  mov     rax, rcx
0x180047025  and     rax, rdx
0x180047028  cmp     rax, rcx
0x18004702b  jnz     loc_1800470B7
0x180047031  call    cs:__imp_GetCurrentThreadId
0x180047037  mov     [rsp+98h+var_68], eax
0x18004703b  mov     [rsp+98h+var_60], 1000000h
0x180047044  mov     r8, [rbx+110h]
0x18004704b  cmp     byte ptr [r8+4], 0
0x180047050  jz      short loc_180047071
0x180047052  lea     r9, [r8+18h]
0x180047056  cmp     dword ptr [r9], 0
0x18004705a  jnz     short loc_180047074
0x18004705c  cmp     dword ptr [r9+4], 0
0x180047061  jnz     short loc_180047074
0x180047063  cmp     dword ptr [r9+8], 0
0x180047068  jnz     short loc_180047074
0x18004706a  cmp     dword ptr [r9+0Ch], 0
0x18004706f  jnz     short loc_180047074
0x180047071  xor     r9d, r9d
0x180047074  lea     rax, [rsp+98h+var_68]
0x180047079  mov     [rsp+98h+var_28], rax
0x18004707e  mov     ecx, 4
0x180047083  mov     [rsp+98h+var_20], rcx
0x180047088  lea     rax, [rsp+98h+var_60]
0x18004708d  mov     [rsp+98h+var_38], rax
0x180047092  mov     [rsp+98h+var_30], rbp
0x180047097  add     r8, rbp
0x18004709a  lea     rax, [rsp+98h+var_58]
0x18004709f  mov     [rsp+98h+var_70], rax
0x1800470a4  mov     [rsp+98h+var_78], ecx
0x1800470a8  lea     rdx, word_18008D4BA
0x1800470af  mov     rcx, rdi
0x1800470b2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800470b7  cmp     dword ptr [rbx+138h], 0
0x1800470be  jnz     short loc_1800470FC
0x1800470c0  add     rbx, 120h
0x1800470c7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800470cf  jz      short loc_1800470F5
0x1800470d1  mov     dl, 1
0x1800470d3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800470d8  mov     [rbx], rax
0x1800470db  test    rax, rax
0x1800470de  jz      short loc_1800470FC
0x1800470e0  mov     rcx, [rax]
0x1800470e3  mov     [rbx+10h], rcx
0x1800470e7  mov     [rax], rbx
0x1800470ea  call    cs:__imp_GetCurrentThreadId
0x1800470f0  mov     [rbx+18h], eax
0x1800470f3  jmp     short loc_1800470FC
0x1800470f5  mov     qword ptr [rbx], 0
0x1800470fc  mov     rcx, [rsp+98h+var_18]
0x180047104  xor     rcx, rsp; StackCookie
0x180047107  call    __security_check_cookie
0x18004710c  lea     r11, [rsp+98h+var_8]
0x180047114  mov     rbx, [r11+18h]
0x180047118  mov     rbp, [r11+20h]
0x18004711c  mov     rsp, r11
0x18004711f  pop     rdi
0x180047120  retn
```
