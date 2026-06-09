# InitOnce::ExecuteOnce__lambda_9fd9c68d428bdefa2bad9293eff33a9d___

- ea: `0x180043b24`
- end: `0x180043bd5`
- name: `InitOnce::ExecuteOnce__lambda_9fd9c68d428bdefa2bad9293eff33a9d___`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180043b00`

## callees

- `0x180043b24`
- `0x180080fb0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180043bab`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180043bab`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180043b7f`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180043b7f`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180043b57`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180043b57`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180043b99`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180043b99`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180043bb6`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180043bb6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180043b73`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180043b73`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 InitOnce::ExecuteOnce__lambda_9fd9c68d428bdefa2bad9293eff33a9d___()
{
  unsigned int inited; // ebx
  __int128 v2; // [rsp+20h] [rbp-40h] BYREF
  __int128 *v3; // [rsp+30h] [rbp-30h]
  char Parameter; // [rsp+38h] [rbp-28h] BYREF
  int v5; // [rsp+39h] [rbp-27h]
  __int16 v6; // [rsp+3Dh] [rbp-23h]
  char v7; // [rsp+3Fh] [rbp-21h]
  __int128 v8; // [rsp+40h] [rbp-20h] BYREF

  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  __ExceptionPtrCreate(&v8);
  inited = InitOnceExecuteOnce(
             &InitOnce,
             lambda_0f9d8247afcc32b896a3295bde432310_::_lambda_invoker_cdecl_,
             &Parameter,
             0);
  if ( __ExceptionPtrToBool(&v8) )
  {
    v2 = 0;
    __ExceptionPtrCopy(&v2, &v8);
    v3 = &v2;
    __ExceptionPtrRethrow(&v2);
  }
  __ExceptionPtrDestroy(&v8);
  return inited;
}

```

## disassembly

```asm
0x180043b24  mov     [rsp-8+arg_0], rbx
0x180043b29  push    rbp
0x180043b2a  mov     rbp, rsp
0x180043b2d  sub     rsp, 60h
0x180043b31  mov     rax, cs:__security_cookie
0x180043b38  xor     rax, rsp
0x180043b3b  mov     [rbp+var_10], rax
0x180043b3f  xor     eax, eax
0x180043b41  mov     [rbp+var_27], eax
0x180043b44  mov     [rbp+var_23], ax
0x180043b48  mov     [rbp+var_21], al
0x180043b4b  xorps   xmm0, xmm0
0x180043b4e  movdqu  [rbp+var_20], xmm0
0x180043b53  lea     rcx, [rbp+var_20]
0x180043b57  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180043b5d  nop
0x180043b5e  xor     r9d, r9d; Context
0x180043b61  lea     r8, [rbp+Parameter]; Parameter
0x180043b65  lea     rdx, _lambda_0f9d8247afcc32b896a3295bde432310____lambda_invoker_cdecl_; InitFn
0x180043b6c  lea     rcx, InitOnce; InitOnce
0x180043b73  call    cs:__imp_InitOnceExecuteOnce
0x180043b79  mov     ebx, eax
0x180043b7b  lea     rcx, [rbp+var_20]
0x180043b7f  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180043b85  test    al, al
0x180043b87  jz      short loc_180043BB2
0x180043b89  xorps   xmm0, xmm0
0x180043b8c  movdqu  [rbp+var_40], xmm0
0x180043b91  lea     rdx, [rbp+var_20]
0x180043b95  lea     rcx, [rbp+var_40]
0x180043b99  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180043b9f  lea     rax, [rbp+var_40]
0x180043ba3  mov     [rbp+var_30], rax
0x180043ba7  lea     rcx, [rbp+var_40]
0x180043bab  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180043bb1  nop
0x180043bb2  lea     rcx, [rbp+var_20]
0x180043bb6  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180043bbc  mov     eax, ebx
0x180043bbe  mov     rcx, [rbp+var_10]
0x180043bc2  xor     rcx, rsp; StackCookie
0x180043bc5  call    __security_check_cookie
0x180043bca  mov     rbx, [rsp+60h+arg_0]
0x180043bcf  add     rsp, 60h
0x180043bd3  pop     rbp
0x180043bd4  retn
```
