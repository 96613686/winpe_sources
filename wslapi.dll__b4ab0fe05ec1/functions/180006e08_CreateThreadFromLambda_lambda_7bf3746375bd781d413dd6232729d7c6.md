# CreateThreadFromLambda__lambda_7bf3746375bd781d413dd6232729d7c6_

- ea: `0x180006e08`
- end: `0x180006e9a`
- name: `CreateThreadFromLambda__lambda_7bf3746375bd781d413dd6232729d7c6___`
- size: `146`
- prototype: `_QWORD *__fastcall(_QWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800075f0`

## callees

- `0x180002460`
- `0x1800059bc`
- `0x180006b80`
- `0x180006e08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006e69`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006e69`

## pseudocode

```c
_QWORD *__fastcall CreateThreadFromLambda__lambda_7bf3746375bd781d413dd6232729d7c6_(_QWORD *a1, _OWORD *a2)
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
  Thread = CreateThread(0, 0, LambdaWrapper__lambda_7bf3746375bd781d413dd6232729d7c6_, v4, 0, 0);
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
0x180006e08  mov     [rsp+arg_8], rbx
0x180006e0d  push    rdi
0x180006e0e  sub     rsp, 30h
0x180006e12  mov     rdi, rdx
0x180006e15  mov     rbx, rcx
0x180006e18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006e1f  mov     ecx, 10h; unsigned __int64
0x180006e24  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006e29  test    rax, rax
0x180006e2c  jz      short loc_180006E35
0x180006e2e  movups  xmm0, xmmword ptr [rdi]
0x180006e31  movdqu  xmmword ptr [rax], xmm0
0x180006e35  mov     rcx, [rsp+38h]; this
0x180006e3a  test    rax, rax
0x180006e3d  jnz     short loc_180006E4F
0x180006e3f  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x180006e46  lea     edx, [rax+19h]; void *
0x180006e49  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180006e4f  xor     ecx, ecx; lpThreadAttributes
0x180006e51  lea     r8, LambdaWrapper__lambda_7bf3746375bd781d413dd6232729d7c6___; lpStartAddress
0x180006e58  mov     [rsp+38h+lpThreadId], rcx; lpThreadId
0x180006e5d  mov     r9, rax; lpParameter
0x180006e60  xor     edx, edx; dwStackSize
0x180006e62  mov     [rsp+38h+dwCreationFlags], ecx; dwCreationFlags
0x180006e66  mov     [rbx], rcx
0x180006e69  call    cs:__imp_CreateThread
0x180006e6f  mov     [rbx], rax
0x180006e72  test    rax, rax
0x180006e75  jnz     short loc_180006E8C
0x180006e77  mov     rcx, [rsp+38h]; this
0x180006e7c  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x180006e83  lea     edx, [rax+22h]; void *
0x180006e86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e8c  mov     rax, rbx
0x180006e8f  mov     rbx, [rsp+38h+arg_8]
0x180006e94  add     rsp, 30h
0x180006e98  pop     rdi
0x180006e99  retn
```
