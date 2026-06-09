# wil::init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___

- ea: `0x180054368`
- end: `0x18005440a`
- name: `wil::init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___`
- size: `162`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e2bc`
- `0x18000eadc`
- `0x180019cec`

## callees

- `0x18005362c`
- `0x180053bd8`
- `0x180054368`
- `0x180054410`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800543e6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800543fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800543e6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800543fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18005438b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18005438b`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const char *v3; // r9
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL fPending; // [rsp+40h] [rbp+18h] BYREF
  int v10; // [rsp+44h] [rbp+1Ch]

  v10 = HIDWORD(a3);
  fPending = 0;
  if ( !InitOnceBeginInitialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = lambda_4d618c0176c5f0f37bb52e96518a1ec6_::operator()();
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v5, v7);
      InitOnceComplete(&InitOnce, 4u, 0);
      return v6;
    }
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180054368  mov     qword ptr [rsp+fPending], r8
0x18005436d  push    rbx; int
0x18005436e  sub     rsp, 20h
0x180054372  xor     r9d, r9d; lpContext
0x180054375  mov     [rsp+28h+fPending], 0
0x18005437d  lea     r8, [rsp+28h+fPending]; fPending
0x180054382  xor     edx, edx; dwFlags
0x180054384  lea     rcx, InitOnce; lpInitOnce
0x18005438b  call    cs:__imp_InitOnceBeginInitialize
0x180054391  test    eax, eax
0x180054393  jnz     short loc_1800543AD
0x180054395  mov     rcx, [rsp+28h]; this
0x18005439a  lea     r8, aWil; "wil"
0x1800543a1  mov     edx, 37Ah; void *
0x1800543a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800543ab  jmp     short loc_180054404
0x1800543ad  cmp     [rsp+28h+fPending], 0
0x1800543b2  jz      short loc_180054402
0x1800543b4  call    _lambda_4d618c0176c5f0f37bb52e96518a1ec6___operator__
0x1800543b9  mov     ebx, eax
0x1800543bb  test    eax, eax
0x1800543bd  jns     short loc_1800543F0
0x1800543bf  mov     rcx, [rsp+28h]; this
0x1800543c4  lea     r8, aWil; "wil"
0x1800543cb  mov     r9d, eax; char *
0x1800543ce  mov     edx, 37Fh; void *
0x1800543d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800543d8  xor     r8d, r8d; lpContext
0x1800543db  lea     rcx, InitOnce; lpInitOnce
0x1800543e2  lea     edx, [r8+4]; dwFlags
0x1800543e6  call    cs:__imp_InitOnceComplete
0x1800543ec  mov     eax, ebx
0x1800543ee  jmp     short loc_180054404
0x1800543f0  xor     r8d, r8d; lpContext
0x1800543f3  lea     rcx, InitOnce; lpInitOnce
0x1800543fa  xor     edx, edx; dwFlags
0x1800543fc  call    cs:__imp_InitOnceComplete
0x180054402  xor     eax, eax
0x180054404  add     rsp, 20h
0x180054408  pop     rbx
0x180054409  retn
```
