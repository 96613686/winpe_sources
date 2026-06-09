# CreateThreadFromLambda__lambda_d4251f4926f6295bfcc87f753188dddd_

- ea: `0x180007850`
- end: `0x1800078f9`
- name: `CreateThreadFromLambda__lambda_d4251f4926f6295bfcc87f753188dddd___`
- size: `169`
- prototype: `_QWORD *__fastcall(_QWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007d90`

## callees

- `0x180002460`
- `0x1800059bc`
- `0x180006b80`
- `0x180007850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800078c8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800078c8`

## pseudocode

```c
_QWORD *__fastcall CreateThreadFromLambda__lambda_d4251f4926f6295bfcc87f753188dddd_(_QWORD *a1, _OWORD *a2)
{
  _OWORD *v4; // rax
  const char *v5; // r9
  HANDLE Thread; // rax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x19,
      (__int64)"onecore\\vm\\wsl\\lxss\\wslapi\\WslSession.hpp",
      v5);
  *v4 = *a2;
  v4[1] = a2[1];
  v4[2] = a2[2];
  v4[3] = a2[3];
  *a1 = 0;
  Thread = CreateThread(0, 0, LambdaWrapper__lambda_d4251f4926f6295bfcc87f753188dddd_, v4, 0, 0);
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
0x180007850  mov     [rsp+arg_8], rbx
0x180007855  push    rdi
0x180007856  sub     rsp, 30h
0x18000785a  mov     rdi, rdx
0x18000785d  mov     rbx, rcx
0x180007860  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007867  mov     ecx, 40h ; '@'; unsigned __int64
0x18000786c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007871  test    rax, rax
0x180007874  jz      short loc_180007894
0x180007876  movups  xmm0, xmmword ptr [rdi]
0x180007879  movups  xmmword ptr [rax], xmm0
0x18000787c  movups  xmm1, xmmword ptr [rdi+10h]
0x180007880  movups  xmmword ptr [rax+10h], xmm1
0x180007884  movups  xmm0, xmmword ptr [rdi+20h]
0x180007888  movups  xmmword ptr [rax+20h], xmm0
0x18000788c  movups  xmm1, xmmword ptr [rdi+30h]
0x180007890  movups  xmmword ptr [rax+30h], xmm1
0x180007894  mov     rcx, [rsp+38h]; this
0x180007899  test    rax, rax
0x18000789c  jnz     short loc_1800078AE
0x18000789e  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x1800078a5  lea     edx, [rax+19h]; void *
0x1800078a8  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x1800078ae  xor     ecx, ecx; lpThreadAttributes
0x1800078b0  lea     r8, LambdaWrapper__lambda_d4251f4926f6295bfcc87f753188dddd___; lpStartAddress
0x1800078b7  mov     [rsp+38h+lpThreadId], rcx; lpThreadId
0x1800078bc  mov     r9, rax; lpParameter
0x1800078bf  xor     edx, edx; dwStackSize
0x1800078c1  mov     [rsp+38h+dwCreationFlags], ecx; dwCreationFlags
0x1800078c5  mov     [rbx], rcx
0x1800078c8  call    cs:__imp_CreateThread
0x1800078ce  mov     [rbx], rax
0x1800078d1  test    rax, rax
0x1800078d4  jnz     short loc_1800078EB
0x1800078d6  mov     rcx, [rsp+38h]; this
0x1800078db  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x1800078e2  lea     edx, [rax+22h]; void *
0x1800078e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800078eb  mov     rax, rbx
0x1800078ee  mov     rbx, [rsp+38h+arg_8]
0x1800078f3  add     rsp, 30h
0x1800078f7  pop     rdi
0x1800078f8  retn
```
