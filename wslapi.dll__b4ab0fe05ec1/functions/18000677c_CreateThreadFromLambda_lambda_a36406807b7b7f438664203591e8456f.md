# CreateThreadFromLambda__lambda_a36406807b7b7f438664203591e8456f_

- ea: `0x18000677c`
- end: `0x180006827`
- name: `CreateThreadFromLambda__lambda_a36406807b7b7f438664203591e8456f___`
- size: `171`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006cb0`

## callees

- `0x180002460`
- `0x1800059bc`
- `0x18000677c`
- `0x180006b80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800067f6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800067f6`

## pseudocode

```c
_QWORD *__fastcall CreateThreadFromLambda__lambda_a36406807b7b7f438664203591e8456f_(_QWORD *a1, __int64 a2)
{
  _OWORD *v4; // rax
  const char *v5; // r9
  HANDLE Thread; // rax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x19,
      (__int64)"onecore\\vm\\wsl\\lxss\\wslapi\\WslSession.hpp",
      v5);
  *v4 = *(_OWORD *)a2;
  v4[1] = *(_OWORD *)(a2 + 16);
  v4[2] = *(_OWORD *)(a2 + 32);
  *((_QWORD *)v4 + 6) = *(_QWORD *)(a2 + 48);
  *a1 = 0;
  Thread = CreateThread(0, 0, LambdaWrapper__lambda_a36406807b7b7f438664203591e8456f_, v4, 0, 0);
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
0x18000677c  mov     [rsp+arg_8], rbx
0x180006781  push    rdi
0x180006782  sub     rsp, 30h
0x180006786  mov     rdi, rdx
0x180006789  mov     rbx, rcx
0x18000678c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006793  mov     ecx, 38h ; '8'; unsigned __int64
0x180006798  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000679d  test    rax, rax
0x1800067a0  jz      short loc_1800067C2
0x1800067a2  movups  xmm0, xmmword ptr [rdi]
0x1800067a5  movups  xmmword ptr [rax], xmm0
0x1800067a8  movups  xmm1, xmmword ptr [rdi+10h]
0x1800067ac  movups  xmmword ptr [rax+10h], xmm1
0x1800067b0  movups  xmm0, xmmword ptr [rdi+20h]
0x1800067b4  movups  xmmword ptr [rax+20h], xmm0
0x1800067b8  movsd   xmm1, qword ptr [rdi+30h]
0x1800067bd  movsd   qword ptr [rax+30h], xmm1
0x1800067c2  mov     rcx, [rsp+38h]; this
0x1800067c7  test    rax, rax
0x1800067ca  jnz     short loc_1800067DC
0x1800067cc  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x1800067d3  lea     edx, [rax+19h]; void *
0x1800067d6  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x1800067dc  xor     ecx, ecx; lpThreadAttributes
0x1800067de  lea     r8, LambdaWrapper__lambda_a36406807b7b7f438664203591e8456f___; lpStartAddress
0x1800067e5  mov     [rsp+38h+lpThreadId], rcx; lpThreadId
0x1800067ea  mov     r9, rax; lpParameter
0x1800067ed  xor     edx, edx; dwStackSize
0x1800067ef  mov     [rsp+38h+dwCreationFlags], ecx; dwCreationFlags
0x1800067f3  mov     [rbx], rcx
0x1800067f6  call    cs:__imp_CreateThread
0x1800067fc  mov     [rbx], rax
0x1800067ff  test    rax, rax
0x180006802  jnz     short loc_180006819
0x180006804  mov     rcx, [rsp+38h]; this
0x180006809  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x180006810  lea     edx, [rax+22h]; void *
0x180006813  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006819  mov     rax, rbx
0x18000681c  mov     rbx, [rsp+38h+arg_8]
0x180006821  add     rsp, 30h
0x180006825  pop     rdi
0x180006826  retn
```
