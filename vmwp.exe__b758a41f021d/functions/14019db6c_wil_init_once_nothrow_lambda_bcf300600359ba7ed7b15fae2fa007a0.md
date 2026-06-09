# wil::init_once_nothrow__lambda_bcf300600359ba7ed7b15fae2fa007a0___

- ea: `0x14019db6c`
- end: `0x14019dc39`
- name: `wil::init_once_nothrow__lambda_bcf300600359ba7ed7b15fae2fa007a0___`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400950d8`

## callees

- `0x14006d540`
- `0x1400c5bf4`
- `0x14011ea40`
- `0x14019db6c`
- `0x14019e398`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14019db9a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14019db9a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14019dbfb`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14019dc17`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14019dbfb`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14019dc17`

## pseudocode

```c
__int64 wil::init_once_nothrow__lambda_bcf300600359ba7ed7b15fae2fa007a0___()
{
  const char *v0; // r9
  int v2; // eax
  unsigned int v3; // ebx
  WINBOOL fPending; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  fPending = 0;
  if ( !InitOnceBeginInitialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v0);
  if ( fPending )
  {
    v2 = lambda_bcf300600359ba7ed7b15fae2fa007a0_::operator()();
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37F,
        (unsigned int)"wil",
        (const char *)(unsigned int)v2,
        fPending);
      InitOnceComplete(&InitOnce, 4u, 0);
      return v3;
    }
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14019db6c  push    rbx
0x14019db6e  sub     rsp, 30h
0x14019db72  mov     rax, cs:__security_cookie
0x14019db79  xor     rax, rsp
0x14019db7c  mov     [rsp+38h+var_10], rax
0x14019db81  mov     [rsp+38h+fPending], 0; int
0x14019db89  xor     r9d, r9d; lpContext
0x14019db8c  lea     r8, [rsp+38h+fPending]; fPending
0x14019db91  xor     edx, edx; dwFlags
0x14019db93  lea     rcx, InitOnce; lpInitOnce
0x14019db9a  call    cs:__imp_InitOnceBeginInitialize
0x14019dba1  nop     dword ptr [rax+rax+00h]
0x14019dba6  test    eax, eax
0x14019dba8  jnz     short loc_14019DBC2
0x14019dbaa  mov     rcx, [rsp+38h]; this
0x14019dbaf  lea     r8, aWil; "wil"
0x14019dbb6  mov     edx, 37Ah; void *
0x14019dbbb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14019dbc0  jmp     short loc_14019DC25
0x14019dbc2  cmp     [rsp+38h+fPending], 0
0x14019dbc7  jz      short loc_14019DC23
0x14019dbc9  call    _lambda_bcf300600359ba7ed7b15fae2fa007a0___operator__
0x14019dbce  mov     ebx, eax
0x14019dbd0  test    eax, eax
0x14019dbd2  jns     short loc_14019DC0B
0x14019dbd4  mov     rcx, [rsp+38h]; this
0x14019dbd9  mov     r9d, eax; char *
0x14019dbdc  lea     r8, aWil; "wil"
0x14019dbe3  mov     edx, 37Fh; void *
0x14019dbe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14019dbed  xor     r8d, r8d; lpContext
0x14019dbf0  lea     edx, [r8+4]; dwFlags
0x14019dbf4  lea     rcx, InitOnce; lpInitOnce
0x14019dbfb  call    cs:__imp_InitOnceComplete
0x14019dc02  nop     dword ptr [rax+rax+00h]
0x14019dc07  mov     eax, ebx
0x14019dc09  jmp     short loc_14019DC25
0x14019dc0b  xor     r8d, r8d; lpContext
0x14019dc0e  xor     edx, edx; dwFlags
0x14019dc10  lea     rcx, InitOnce; lpInitOnce
0x14019dc17  call    cs:__imp_InitOnceComplete
0x14019dc1e  nop     dword ptr [rax+rax+00h]
0x14019dc23  xor     eax, eax
0x14019dc25  mov     rcx, [rsp+38h+var_10]
0x14019dc2a  xor     rcx, rsp; StackCookie
0x14019dc2d  call    __security_check_cookie
0x14019dc32  add     rsp, 30h
0x14019dc36  pop     rbx
0x14019dc37  retn
```
