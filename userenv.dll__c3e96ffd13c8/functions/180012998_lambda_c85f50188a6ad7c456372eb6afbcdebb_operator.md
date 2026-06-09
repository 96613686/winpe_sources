# _lambda_c85f50188a6ad7c456372eb6afbcdebb_::operator()

- ea: `0x180012998`
- end: `0x180012a73`
- name: `_lambda_c85f50188a6ad7c456372eb6afbcdebb_::operator()`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012064`

## callees

- `0x18000542c`
- `0x180005de0`
- `0x18000cea0`
- `0x18001231c`
- `0x180012998`

## string_xrefs

- `0x180012a3e`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_c85f50188a6ad7c456372eb6afbcdebb_::operator()(_QWORD *a1, __int64 a2)
{
  int v3; // ebx
  int v4; // eax
  unsigned int v6[4]; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v7[4]; // [rsp+30h] [rbp-50h] BYREF
  int v8; // [rsp+50h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-28h]
  __int64 v10; // [rsp+60h] [rbp-20h]
  int v11; // [rsp+68h] [rbp-18h]
  __int128 v12; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  __int64 v14; // [rsp+98h] [rbp+18h] BYREF

  v14 = a2;
  v6[0] = 9;
  v6[1] = 17;
  v6[2] = 18;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v3 = CThreadContext::EnablePrivileges((CThreadContext *)&v8, v6, 3u);
  if ( v3 >= 0 )
  {
    v7[0] = &v14;
    v7[1] = *a1;
    v7[2] = a1[1];
    v7[3] = a1[2];
    v4 = RPCExceptBoundary__lambda_22175907ae03129252517f142cadb095_(v7);
    v3 = v4;
    if ( v4 >= 0 )
      v3 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EC,
        (int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
        (const char *)(unsigned int)v4);
  }
  CThreadContext::~CThreadContext((CThreadContext *)&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180012998  mov     [rsp-8+arg_0], rbx
0x18001299d  mov     [rsp-8+arg_10], rdi
0x1800129a2  mov     [rsp-8+arg_8], rdx
0x1800129a7  push    rbp
0x1800129a8  mov     rbp, rsp
0x1800129ab  sub     rsp, 80h
0x1800129b2  mov     rdi, rcx
0x1800129b5  mov     [rbp+var_60], 9
0x1800129bc  mov     [rbp+var_5C], 11h
0x1800129c3  mov     [rbp+var_58], 12h
0x1800129ca  mov     [rbp+var_30], 0
0x1800129d1  mov     [rbp+var_28], 0
0x1800129d9  mov     [rbp+var_20], 0
0x1800129e1  mov     [rbp+var_18], 0
0x1800129e8  xorps   xmm0, xmm0
0x1800129eb  movdqu  [rbp+var_10], xmm0
0x1800129f0  mov     r8d, 3; unsigned int
0x1800129f6  lea     rdx, [rbp+var_60]; unsigned int *
0x1800129fa  lea     rcx, [rbp+var_30]; this
0x1800129fe  call    ?EnablePrivileges@CThreadContext@@QEAAJPEAKK@Z; CThreadContext::EnablePrivileges(ulong *,ulong)
0x180012a03  mov     ebx, eax
0x180012a05  test    eax, eax
0x180012a07  js      short loc_180012A53
0x180012a09  lea     rax, [rbp+arg_8]
0x180012a0d  mov     [rbp+var_50], rax
0x180012a11  mov     rax, [rdi]
0x180012a14  mov     [rbp+var_48], rax
0x180012a18  mov     rax, [rdi+8]
0x180012a1c  mov     [rbp+var_40], rax
0x180012a20  mov     rax, [rdi+10h]
0x180012a24  mov     [rbp+var_38], rax
0x180012a28  lea     rcx, [rbp+var_50]
0x180012a2c  call    _RPCExceptBoundary__lambda_22175907ae03129252517f142cadb095___; RPCExceptBoundary__lambda_22175907ae03129252517f142cadb095_
0x180012a31  mov     ebx, eax
0x180012a33  test    eax, eax
0x180012a35  jns     short loc_180012A51
0x180012a37  mov     rcx, [rbp+8]; this
0x180012a3b  mov     r9d, eax; char *
0x180012a3e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180012a45  mov     edx, 1ECh; void *
0x180012a4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a4f  jmp     short loc_180012A53
0x180012a51  xor     ebx, ebx
0x180012a53  lea     rcx, [rbp+var_30]; this
0x180012a57  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180012a5c  mov     eax, ebx
0x180012a5e  lea     r11, [rsp+80h+var_s0]
0x180012a66  mov     rbx, [r11+10h]
0x180012a6a  mov     rdi, [r11+20h]
0x180012a6e  mov     rsp, r11
0x180012a71  pop     rbp
0x180012a72  retn
```
