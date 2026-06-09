# CreateThreadFromLambda__lambda_4e29967ac626feff930376ab7442d83b_

- ea: `0x180006d64`
- end: `0x180006dff`
- name: `CreateThreadFromLambda__lambda_4e29967ac626feff930376ab7442d83b___`
- size: `155`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007680`

## callees

- `0x180002460`
- `0x1800059bc`
- `0x180006b80`
- `0x180006d64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006dce`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006dce`

## pseudocode

```c
_QWORD *__fastcall CreateThreadFromLambda__lambda_4e29967ac626feff930376ab7442d83b_(_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // rax
  const char *v5; // r9
  HANDLE Thread; // rax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x19,
      (__int64)"onecore\\vm\\wsl\\lxss\\wslapi\\WslSession.hpp",
      v5);
  *(_OWORD *)v4 = *(_OWORD *)a2;
  v4[2] = *(_QWORD *)(a2 + 16);
  *a1 = 0;
  Thread = CreateThread(0, 0, LambdaWrapper__lambda_4e29967ac626feff930376ab7442d83b_, v4, 0, 0);
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
0x180006d64  mov     [rsp+arg_8], rbx
0x180006d69  push    rdi
0x180006d6a  sub     rsp, 30h
0x180006d6e  mov     rdi, rdx
0x180006d71  mov     rbx, rcx
0x180006d74  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006d7b  mov     ecx, 18h; unsigned __int64
0x180006d80  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006d85  test    rax, rax
0x180006d88  jz      short loc_180006D9A
0x180006d8a  movups  xmm0, xmmword ptr [rdi]
0x180006d8d  movups  xmmword ptr [rax], xmm0
0x180006d90  movsd   xmm1, qword ptr [rdi+10h]
0x180006d95  movsd   qword ptr [rax+10h], xmm1
0x180006d9a  mov     rcx, [rsp+38h]; this
0x180006d9f  test    rax, rax
0x180006da2  jnz     short loc_180006DB4
0x180006da4  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x180006dab  lea     edx, [rax+19h]; void *
0x180006dae  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180006db4  xor     ecx, ecx; lpThreadAttributes
0x180006db6  lea     r8, LambdaWrapper__lambda_4e29967ac626feff930376ab7442d83b___; lpStartAddress
0x180006dbd  mov     [rsp+38h+lpThreadId], rcx; lpThreadId
0x180006dc2  mov     r9, rax; lpParameter
0x180006dc5  xor     edx, edx; dwStackSize
0x180006dc7  mov     [rsp+38h+dwCreationFlags], ecx; dwCreationFlags
0x180006dcb  mov     [rbx], rcx
0x180006dce  call    cs:__imp_CreateThread
0x180006dd4  mov     [rbx], rax
0x180006dd7  test    rax, rax
0x180006dda  jnz     short loc_180006DF1
0x180006ddc  mov     rcx, [rsp+38h]; this
0x180006de1  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x180006de8  lea     edx, [rax+22h]; void *
0x180006deb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006df1  mov     rax, rbx
0x180006df4  mov     rbx, [rsp+38h+arg_8]
0x180006df9  add     rsp, 30h
0x180006dfd  pop     rdi
0x180006dfe  retn
```
