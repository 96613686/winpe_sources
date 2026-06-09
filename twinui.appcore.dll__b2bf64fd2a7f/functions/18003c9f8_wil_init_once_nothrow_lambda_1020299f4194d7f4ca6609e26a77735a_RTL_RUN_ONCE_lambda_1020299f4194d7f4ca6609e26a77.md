# wil::init_once_nothrow<_lambda_1020299f4194d7f4ca6609e26a77735a_>(_RTL_RUN_ONCE &,_lambda_1020299f4194d7f4ca6609e26a77735a_,bool *)

- ea: `0x18003c9f8`
- end: `0x18003cab9`
- name: `??$init_once_nothrow@V_lambda_1020299f4194d7f4ca6609e26a77735a_@@@wil@@YAJAEAT_RTL_RUN_ONCE@@V_lambda_1020299f4194d7f4ca6609e26a77735a_@@PEA_N@Z`
- size: `193`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180040450`

## callees

- `0x18001cc38`
- `0x18001e340`
- `0x18002b1b0`
- `0x18003c9f8`
- `0x18003f1cc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003ca87`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003ca99`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003ca87`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003ca99`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003ca2b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003ca2b`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow<_lambda_1020299f4194d7f4ca6609e26a77735a_>(
        LPINIT_ONCE lpInitOnce,
        __int64 a2)
{
  const char *v3; // r9
  int v5; // eax
  unsigned int v6; // ebx
  WINBOOL fPending; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = a2;
  fPending = 0;
  if ( !InitOnceBeginInitialize(lpInitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = _lambda_1020299f4194d7f4ca6609e26a77735a_::operator()(&v9);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37F,
        (unsigned int)"wil",
        (const char *)(unsigned int)v5,
        fPending);
      InitOnceComplete(lpInitOnce, 4u, 0);
      return v6;
    }
    InitOnceComplete(lpInitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18003c9f8  mov     [rsp+arg_10], rbx
0x18003c9fd  mov     [rsp+arg_8], rdx
0x18003ca02  push    rdi
0x18003ca03  sub     rsp, 30h
0x18003ca07  mov     rax, cs:__security_cookie
0x18003ca0e  xor     rax, rsp
0x18003ca11  mov     [rsp+38h+var_10], rax
0x18003ca16  mov     rdi, rcx
0x18003ca19  mov     [rsp+38h+fPending], 0; int
0x18003ca21  xor     r9d, r9d; lpContext
0x18003ca24  lea     r8, [rsp+38h+fPending]; fPending
0x18003ca29  xor     edx, edx; dwFlags
0x18003ca2b  call    cs:__imp_InitOnceBeginInitialize
0x18003ca31  test    eax, eax
0x18003ca33  jnz     short loc_18003CA4D
0x18003ca35  mov     rcx, [rsp+38h]; this
0x18003ca3a  lea     r8, aWil; "wil"
0x18003ca41  mov     edx, 37Ah; void *
0x18003ca46  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ca4b  jmp     short loc_18003CAA1
0x18003ca4d  cmp     [rsp+38h+fPending], 0
0x18003ca52  jz      short loc_18003CA9F
0x18003ca54  lea     rcx, [rsp+38h+arg_8]
0x18003ca59  call    ??R_lambda_1020299f4194d7f4ca6609e26a77735a_@@QEBA@XZ; _lambda_1020299f4194d7f4ca6609e26a77735a_::operator()(void)
0x18003ca5e  mov     ebx, eax
0x18003ca60  test    eax, eax
0x18003ca62  jns     short loc_18003CA91
0x18003ca64  mov     rcx, [rsp+38h]; this
0x18003ca69  mov     r9d, eax; char *
0x18003ca6c  lea     r8, aWil; "wil"
0x18003ca73  mov     edx, 37Fh; void *
0x18003ca78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ca7d  xor     r8d, r8d; lpContext
0x18003ca80  lea     edx, [r8+4]; dwFlags
0x18003ca84  mov     rcx, rdi; lpInitOnce
0x18003ca87  call    cs:__imp_InitOnceComplete
0x18003ca8d  mov     eax, ebx
0x18003ca8f  jmp     short loc_18003CAA1
0x18003ca91  xor     r8d, r8d; lpContext
0x18003ca94  xor     edx, edx; dwFlags
0x18003ca96  mov     rcx, rdi; lpInitOnce
0x18003ca99  call    cs:__imp_InitOnceComplete
0x18003ca9f  xor     eax, eax
0x18003caa1  mov     rcx, [rsp+38h+var_10]
0x18003caa6  xor     rcx, rsp; StackCookie
0x18003caa9  call    __security_check_cookie
0x18003caae  mov     rbx, [rsp+38h+arg_10]
0x18003cab3  add     rsp, 30h
0x18003cab7  pop     rdi
0x18003cab8  retn
```
