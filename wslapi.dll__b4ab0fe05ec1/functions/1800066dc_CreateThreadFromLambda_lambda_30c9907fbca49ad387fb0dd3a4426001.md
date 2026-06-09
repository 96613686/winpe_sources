# CreateThreadFromLambda__lambda_30c9907fbca49ad387fb0dd3a4426001_

- ea: `0x1800066dc`
- end: `0x180006775`
- name: `CreateThreadFromLambda__lambda_30c9907fbca49ad387fb0dd3a4426001___`
- size: `153`
- prototype: `_QWORD *__fastcall(_QWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006c10`

## callees

- `0x180002460`
- `0x1800059bc`
- `0x1800066dc`
- `0x180006b80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006744`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006744`

## pseudocode

```c
_QWORD *__fastcall CreateThreadFromLambda__lambda_30c9907fbca49ad387fb0dd3a4426001_(_QWORD *a1, _OWORD *a2)
{
  _OWORD *v4; // rax
  const char *v5; // r9
  HANDLE Thread; // rax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x19,
      (__int64)"onecore\\vm\\wsl\\lxss\\wslapi\\WslSession.hpp",
      v5);
  *v4 = *a2;
  v4[1] = a2[1];
  *a1 = 0;
  Thread = CreateThread(0, 0, LambdaWrapper__lambda_30c9907fbca49ad387fb0dd3a4426001_, v4, 0, 0);
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
0x1800066dc  mov     [rsp+arg_8], rbx
0x1800066e1  push    rdi
0x1800066e2  sub     rsp, 30h
0x1800066e6  mov     rdi, rdx
0x1800066e9  mov     rbx, rcx
0x1800066ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800066f3  mov     ecx, 20h ; ' '; unsigned __int64
0x1800066f8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800066fd  test    rax, rax
0x180006700  jz      short loc_180006710
0x180006702  movups  xmm0, xmmword ptr [rdi]
0x180006705  movups  xmmword ptr [rax], xmm0
0x180006708  movups  xmm1, xmmword ptr [rdi+10h]
0x18000670c  movups  xmmword ptr [rax+10h], xmm1
0x180006710  mov     rcx, [rsp+38h]; this
0x180006715  test    rax, rax
0x180006718  jnz     short loc_18000672A
0x18000671a  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x180006721  lea     edx, [rax+19h]; void *
0x180006724  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18000672a  xor     ecx, ecx; lpThreadAttributes
0x18000672c  lea     r8, LambdaWrapper__lambda_30c9907fbca49ad387fb0dd3a4426001___; lpStartAddress
0x180006733  mov     [rsp+38h+lpThreadId], rcx; lpThreadId
0x180006738  mov     r9, rax; lpParameter
0x18000673b  xor     edx, edx; dwStackSize
0x18000673d  mov     [rsp+38h+dwCreationFlags], ecx; dwCreationFlags
0x180006741  mov     [rbx], rcx
0x180006744  call    cs:__imp_CreateThread
0x18000674a  mov     [rbx], rax
0x18000674d  test    rax, rax
0x180006750  jnz     short loc_180006767
0x180006752  mov     rcx, [rsp+38h]; this
0x180006757  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x18000675e  lea     edx, [rax+22h]; void *
0x180006761  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006767  mov     rax, rbx
0x18000676a  mov     rbx, [rsp+38h+arg_8]
0x18000676f  add     rsp, 30h
0x180006773  pop     rdi
0x180006774  retn
```
