# InitOnce::ExecuteOnce__lambda_132599c54087ef279e3c133a08d6e11e___

- ea: `0x180071bbc`
- end: `0x180071c57`
- name: `InitOnce::ExecuteOnce__lambda_132599c54087ef279e3c133a08d6e11e___`
- size: `155`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005bbb8`

## callees

- `0x180071bbc`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180071c39`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180071c39`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180071c0d`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180071c0d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180071be9`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180071be9`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180071c27`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180071c27`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180071c44`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180071c44`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180071c01`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180071c01`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitOnce::ExecuteOnce__lambda_132599c54087ef279e3c133a08d6e11e___(PINIT_ONCE InitOnce, __int128 *a2)
{
  unsigned int inited; // ebx
  __int128 v5; // [rsp+20h] [rbp-40h] BYREF
  __int128 Parameter; // [rsp+30h] [rbp-30h] BYREF
  __int64 v7; // [rsp+40h] [rbp-20h]
  __int128 v8; // [rsp+48h] [rbp-18h] BYREF

  Parameter = *a2;
  v7 = *((_QWORD *)a2 + 2);
  v8 = 0;
  __ExceptionPtrCreate(&v8);
  inited = InitOnceExecuteOnce(
             InitOnce,
             lambda_d84d4c29c9c4db7c6cc456dbe7a4d93e_::_lambda_invoker_cdecl_,
             &Parameter,
             0);
  if ( __ExceptionPtrToBool(&v8) )
  {
    v5 = 0;
    __ExceptionPtrCopy(&v5, &v8);
    __ExceptionPtrRethrow(&v5);
  }
  __ExceptionPtrDestroy(&v8);
  return inited;
}

```

## disassembly

```asm
0x180071bbc  mov     [rsp-8+arg_8], rbx
0x180071bc1  push    rbp
0x180071bc2  mov     rbp, rsp
0x180071bc5  sub     rsp, 60h
0x180071bc9  mov     rbx, rcx
0x180071bcc  movaps  xmm0, xmmword ptr [rdx]
0x180071bcf  movups  [rbp+Parameter], xmm0
0x180071bd3  movsd   xmm1, qword ptr [rdx+10h]
0x180071bd8  movsd   [rbp+var_20], xmm1
0x180071bdd  xorps   xmm0, xmm0
0x180071be0  movdqu  [rbp+var_18], xmm0
0x180071be5  lea     rcx, [rbp+var_18]
0x180071be9  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180071bef  nop
0x180071bf0  xor     r9d, r9d; Context
0x180071bf3  lea     r8, [rbp+Parameter]; Parameter
0x180071bf7  lea     rdx, _lambda_d84d4c29c9c4db7c6cc456dbe7a4d93e____lambda_invoker_cdecl_; InitFn
0x180071bfe  mov     rcx, rbx; InitOnce
0x180071c01  call    cs:__imp_InitOnceExecuteOnce
0x180071c07  mov     ebx, eax
0x180071c09  lea     rcx, [rbp+var_18]
0x180071c0d  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180071c13  test    al, al
0x180071c15  jz      short loc_180071C40
0x180071c17  xorps   xmm0, xmm0
0x180071c1a  movdqu  [rbp+var_40], xmm0
0x180071c1f  lea     rdx, [rbp+var_18]
0x180071c23  lea     rcx, [rbp+var_40]
0x180071c27  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180071c2d  lea     rax, [rbp+var_40]
0x180071c31  mov     [rbp+arg_0], rax
0x180071c35  lea     rcx, [rbp+var_40]
0x180071c39  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180071c3f  nop
0x180071c40  lea     rcx, [rbp+var_18]
0x180071c44  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180071c4a  mov     eax, ebx
0x180071c4c  mov     rbx, [rsp+60h+arg_8]
0x180071c51  add     rsp, 60h
0x180071c55  pop     rbp
0x180071c56  retn
```
