# InitOnce::ExecuteOnce__lambda_ed8a419c9d1189281073be2368c19977___

- ea: `0x180073d00`
- end: `0x180073d94`
- name: `InitOnce::ExecuteOnce__lambda_ed8a419c9d1189281073be2368c19977___`
- size: `148`
- prototype: ``
- caller_count: `52`
- callee_count: `1`
- tags: ``

## callers

- `0x18005b3f0`
- `0x18005ba80`
- `0x18005bb10`
- `0x18005ccf0`
- `0x180072880`
- `0x180072920`
- `0x1800729a0`
- `0x180072a00`
- `0x180072a70`
- `0x180072b00`
- `0x180072bb0`
- `0x180072c10`
- `0x180072c90`
- `0x180072d50`
- `0x180072dc0`
- `0x180072e20`
- `0x180072e70`
- `0x180072eb0`
- `0x180072f50`
- `0x180072fd0`
- `0x180073020`
- `0x180073080`
- `0x1800730e0`
- `0x180073150`
- `0x1800731a0`
- `0x180073200`
- `0x180073260`
- `0x1800732c0`
- `0x180073330`
- `0x180073370`
- `0x1800733d0`
- `0x180073480`
- `0x180073500`
- `0x180073570`
- `0x1800735d0`
- `0x180073620`
- `0x180073670`
- `0x1800736c0`
- `0x180073730`
- `0x180073770`
- `0x1800737b0`
- `0x1800737f0`
- `0x180073880`
- `0x1800738e0`
- `0x180073970`
- `0x1800739f0`
- `0x180073a70`
- `0x180073af0`
- `0x180073b40`
- `0x180073bc0`

## callees

- `0x180073d00`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180073d76`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180073d76`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180073d4a`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180073d4a`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180073d22`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180073d22`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180073d64`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180073d64`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180073d81`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180073d81`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180073d3e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180073d3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitOnce::ExecuteOnce__lambda_ed8a419c9d1189281073be2368c19977___(__int64 a1, __int64 a2)
{
  unsigned int inited; // ebx
  __int128 v4; // [rsp+20h] [rbp-30h] BYREF
  __int64 Parameter; // [rsp+30h] [rbp-20h] BYREF
  __int128 v6; // [rsp+38h] [rbp-18h] BYREF

  Parameter = a2;
  v6 = 0;
  __ExceptionPtrCreate(&v6);
  inited = InitOnceExecuteOnce(
             &stru_180113A40,
             lambda_61abcf6ac849066730e761e8ef020134_::_lambda_invoker_cdecl_,
             &Parameter,
             0);
  if ( __ExceptionPtrToBool(&v6) )
  {
    v4 = 0;
    __ExceptionPtrCopy(&v4, &v6);
    __ExceptionPtrRethrow(&v4);
  }
  __ExceptionPtrDestroy(&v6);
  return inited;
}

```

## disassembly

```asm
0x180073d00  mov     [rsp-8+arg_8], rbx
0x180073d05  mov     [rsp-8+arg_0], rcx
0x180073d0a  push    rbp
0x180073d0b  mov     rbp, rsp
0x180073d0e  sub     rsp, 50h
0x180073d12  mov     [rbp+Parameter], rdx
0x180073d16  xorps   xmm0, xmm0
0x180073d19  movdqu  [rbp+var_18], xmm0
0x180073d1e  lea     rcx, [rbp+var_18]
0x180073d22  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180073d28  nop
0x180073d29  xor     r9d, r9d; Context
0x180073d2c  lea     r8, [rbp+Parameter]; Parameter
0x180073d30  lea     rdx, _lambda_61abcf6ac849066730e761e8ef020134____lambda_invoker_cdecl_; InitFn
0x180073d37  lea     rcx, stru_180113A40; InitOnce
0x180073d3e  call    cs:__imp_InitOnceExecuteOnce
0x180073d44  mov     ebx, eax
0x180073d46  lea     rcx, [rbp+var_18]
0x180073d4a  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180073d50  test    al, al
0x180073d52  jz      short loc_180073D7D
0x180073d54  xorps   xmm0, xmm0
0x180073d57  movdqu  [rbp+var_30], xmm0
0x180073d5c  lea     rdx, [rbp+var_18]
0x180073d60  lea     rcx, [rbp+var_30]
0x180073d64  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180073d6a  lea     rax, [rbp+var_30]
0x180073d6e  mov     [rbp+arg_0], rax
0x180073d72  lea     rcx, [rbp+var_30]
0x180073d76  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180073d7c  nop
0x180073d7d  lea     rcx, [rbp+var_18]
0x180073d81  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180073d87  mov     eax, ebx
0x180073d89  mov     rbx, [rsp+50h+arg_8]
0x180073d8e  add     rsp, 50h
0x180073d92  pop     rbp
0x180073d93  retn
```
