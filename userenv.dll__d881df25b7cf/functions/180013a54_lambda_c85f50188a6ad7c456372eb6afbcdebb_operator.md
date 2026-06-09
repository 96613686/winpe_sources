# _lambda_c85f50188a6ad7c456372eb6afbcdebb_::operator()

- ea: `0x180013a54`
- end: `0x180013b30`
- name: `_lambda_c85f50188a6ad7c456372eb6afbcdebb_::operator()`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013030`

## callees

- `0x180005b78`
- `0x1800065d8`
- `0x18000db08`
- `0x1800132f4`
- `0x180013a54`

## string_xrefs

- `0x180013afa`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

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
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
        (const char *)(unsigned int)v4,
        v6[0]);
  }
  CThreadContext::~CThreadContext((CThreadContext *)&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013a54  mov     [rsp-8+arg_0], rbx
0x180013a59  mov     [rsp-8+arg_10], rdi
0x180013a5e  mov     [rsp-8+arg_8], rdx
0x180013a63  push    rbp
0x180013a64  mov     rbp, rsp
0x180013a67  sub     rsp, 80h
0x180013a6e  mov     rdi, rcx
0x180013a71  mov     [rbp+var_60], 9
0x180013a78  mov     [rbp+var_5C], 11h
0x180013a7f  mov     [rbp+var_58], 12h
0x180013a86  mov     [rbp+var_30], 0
0x180013a8d  mov     [rbp+var_28], 0
0x180013a95  mov     [rbp+var_20], 0
0x180013a9d  mov     [rbp+var_18], 0
0x180013aa4  xorps   xmm0, xmm0
0x180013aa7  movdqu  [rbp+var_10], xmm0
0x180013aac  mov     r8d, 3; unsigned int
0x180013ab2  lea     rdx, [rbp+var_60]; unsigned int *
0x180013ab6  lea     rcx, [rbp+var_30]; this
0x180013aba  call    ?EnablePrivileges@CThreadContext@@QEAAJPEAKK@Z; CThreadContext::EnablePrivileges(ulong *,ulong)
0x180013abf  mov     ebx, eax
0x180013ac1  test    eax, eax
0x180013ac3  js      short loc_180013B0F
0x180013ac5  lea     rax, [rbp+arg_8]
0x180013ac9  mov     [rbp+var_50], rax
0x180013acd  mov     rax, [rdi]
0x180013ad0  mov     [rbp+var_48], rax
0x180013ad4  mov     rax, [rdi+8]
0x180013ad8  mov     [rbp+var_40], rax
0x180013adc  mov     rax, [rdi+10h]
0x180013ae0  mov     [rbp+var_38], rax
0x180013ae4  lea     rcx, [rbp+var_50]
0x180013ae8  call    _RPCExceptBoundary__lambda_22175907ae03129252517f142cadb095___; RPCExceptBoundary__lambda_22175907ae03129252517f142cadb095_
0x180013aed  mov     ebx, eax
0x180013aef  test    eax, eax
0x180013af1  jns     short loc_180013B0D
0x180013af3  mov     rcx, [rbp+8]; this
0x180013af7  mov     r9d, eax; char *
0x180013afa  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180013b01  mov     edx, 1ECh; void *
0x180013b06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b0b  jmp     short loc_180013B0F
0x180013b0d  xor     ebx, ebx
0x180013b0f  lea     rcx, [rbp+var_30]; this
0x180013b13  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180013b18  mov     eax, ebx
0x180013b1a  lea     r11, [rsp+80h+var_s0]
0x180013b22  mov     rbx, [r11+10h]
0x180013b26  mov     rdi, [r11+20h]
0x180013b2a  mov     rsp, r11
0x180013b2d  pop     rbp
0x180013b2e  retn
```
