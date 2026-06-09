# InitOnce::ExecuteOnce__lambda_c4d4aa6a7bfb6a9f4e7bc7f240c0537d___

- ea: `0x180051814`
- end: `0x1800518bd`
- name: `InitOnce::ExecuteOnce__lambda_c4d4aa6a7bfb6a9f4e7bc7f240c0537d___`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800517bc`

## callees

- `0x180051814`
- `0x180080fb0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800518b6`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800518b6`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180051867`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180051867`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005183f`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005183f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800518a4`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800518a4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180051875`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180051875`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005185b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005185b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitOnce::ExecuteOnce__lambda_c4d4aa6a7bfb6a9f4e7bc7f240c0537d___(__int64 a1, __int64 a2)
{
  unsigned int inited; // ebx
  __int128 v4; // [rsp+20h] [rbp-40h] BYREF
  __int128 *v5; // [rsp+30h] [rbp-30h]
  __int64 Parameter; // [rsp+38h] [rbp-28h] BYREF
  __int128 v7; // [rsp+40h] [rbp-20h] BYREF

  Parameter = a2;
  v7 = 0;
  __ExceptionPtrCreate(&v7);
  inited = InitOnceExecuteOnce(
             &stru_1801136D0,
             lambda_7734959fa65c8759edab909eb1bb74e3_::_lambda_invoker_cdecl_,
             &Parameter,
             0);
  if ( __ExceptionPtrToBool(&v7) )
  {
    v4 = 0;
    __ExceptionPtrCopy(&v4, &v7);
    v5 = &v4;
    __ExceptionPtrRethrow(&v4);
    JUMPOUT(0x1800518BCLL);
  }
  __ExceptionPtrDestroy(&v7);
  return inited;
}

```

## disassembly

```asm
0x180051814  mov     [rsp-8+arg_0], rbx
0x180051819  push    rbp
0x18005181a  mov     rbp, rsp
0x18005181d  sub     rsp, 60h
0x180051821  mov     rax, cs:__security_cookie
0x180051828  xor     rax, rsp
0x18005182b  mov     [rbp+var_10], rax
0x18005182f  mov     [rbp+Parameter], rdx
0x180051833  xorps   xmm0, xmm0
0x180051836  movdqu  [rbp+var_20], xmm0
0x18005183b  lea     rcx, [rbp+var_20]
0x18005183f  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180051845  nop
0x180051846  xor     r9d, r9d; Context
0x180051849  lea     r8, [rbp+Parameter]; Parameter
0x18005184d  lea     rdx, _lambda_7734959fa65c8759edab909eb1bb74e3____lambda_invoker_cdecl_; InitFn
0x180051854  lea     rcx, stru_1801136D0; InitOnce
0x18005185b  call    cs:__imp_InitOnceExecuteOnce
0x180051861  mov     ebx, eax
0x180051863  lea     rcx, [rbp+var_20]
0x180051867  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18005186d  test    al, al
0x18005186f  jnz     short loc_180051894
0x180051871  lea     rcx, [rbp+var_20]
0x180051875  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18005187b  mov     eax, ebx
0x18005187d  mov     rcx, [rbp+var_10]
0x180051881  xor     rcx, rsp; StackCookie
0x180051884  call    __security_check_cookie
0x180051889  mov     rbx, [rsp+60h+arg_0]
0x18005188e  add     rsp, 60h
0x180051892  pop     rbp
0x180051893  retn
0x180051894  xorps   xmm0, xmm0
0x180051897  movdqu  [rbp+var_40], xmm0
0x18005189c  lea     rdx, [rbp+var_20]
0x1800518a0  lea     rcx, [rbp+var_40]
0x1800518a4  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800518aa  lea     rax, [rbp+var_40]
0x1800518ae  mov     [rbp+var_30], rax
0x1800518b2  lea     rcx, [rbp+var_40]
0x1800518b6  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
