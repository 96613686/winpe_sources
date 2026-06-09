# CreateThreadFromLambda__lambda_9e18749395fb31002599b6510f759e9a_

- ea: `0x180006ea0`
- end: `0x180006f32`
- name: `CreateThreadFromLambda__lambda_9e18749395fb31002599b6510f759e9a___`
- size: `146`
- prototype: `_QWORD *__fastcall(_QWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007720`

## callees

- `0x180002460`
- `0x1800059bc`
- `0x180006b80`
- `0x180006ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006f01`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006f01`

## pseudocode

```c
_QWORD *__fastcall CreateThreadFromLambda__lambda_9e18749395fb31002599b6510f759e9a_(_QWORD *a1, _OWORD *a2)
{
  _OWORD *v4; // rax
  const char *v5; // r9
  HANDLE Thread; // rax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x19,
      (__int64)"onecore\\vm\\wsl\\lxss\\wslapi\\WslSession.hpp",
      v5);
  *v4 = *a2;
  *a1 = 0;
  Thread = CreateThread(0, 0, LambdaWrapper__lambda_9e18749395fb31002599b6510f759e9a_, v4, 0, 0);
  *a1 = Thread;
  if ( !Thread )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x22,
      (int)"onecore\\vm\\wsl\\lxss\\wslapi\\WslSession.hpp",
      v7);
  return a1;
}

```

## disassembly

```asm
0x180006ea0  mov     [rsp+arg_8], rbx
0x180006ea5  push    rdi
0x180006ea6  sub     rsp, 30h
0x180006eaa  mov     rdi, rdx
0x180006ead  mov     rbx, rcx
0x180006eb0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006eb7  mov     ecx, 10h; unsigned __int64
0x180006ebc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006ec1  test    rax, rax
0x180006ec4  jz      short loc_180006ECD
0x180006ec6  movups  xmm0, xmmword ptr [rdi]
0x180006ec9  movdqu  xmmword ptr [rax], xmm0
0x180006ecd  mov     rcx, [rsp+38h]; this
0x180006ed2  test    rax, rax
0x180006ed5  jnz     short loc_180006EE7
0x180006ed7  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x180006ede  lea     edx, [rax+19h]; void *
0x180006ee1  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180006ee7  xor     ecx, ecx; lpThreadAttributes
0x180006ee9  lea     r8, LambdaWrapper__lambda_9e18749395fb31002599b6510f759e9a___; lpStartAddress
0x180006ef0  mov     [rsp+38h+lpThreadId], rcx; lpThreadId
0x180006ef5  mov     r9, rax; lpParameter
0x180006ef8  xor     edx, edx; dwStackSize
0x180006efa  mov     [rsp+38h+dwCreationFlags], ecx; dwCreationFlags
0x180006efe  mov     [rbx], rcx
0x180006f01  call    cs:__imp_CreateThread
0x180006f07  mov     [rbx], rax
0x180006f0a  test    rax, rax
0x180006f0d  jnz     short loc_180006F24
0x180006f0f  mov     rcx, [rsp+38h]; this
0x180006f14  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x180006f1b  lea     edx, [rax+22h]; void *
0x180006f1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f24  mov     rax, rbx
0x180006f27  mov     rbx, [rsp+38h+arg_8]
0x180006f2c  add     rsp, 30h
0x180006f30  pop     rdi
0x180006f31  retn
```
