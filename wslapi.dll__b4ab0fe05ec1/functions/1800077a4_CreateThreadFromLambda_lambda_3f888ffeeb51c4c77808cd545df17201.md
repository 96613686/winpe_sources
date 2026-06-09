# CreateThreadFromLambda__lambda_3f888ffeeb51c4c77808cd545df17201_

- ea: `0x1800077a4`
- end: `0x180007847`
- name: `CreateThreadFromLambda__lambda_3f888ffeeb51c4c77808cd545df17201___`
- size: `163`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007e60`

## callees

- `0x180002460`
- `0x1800059bc`
- `0x180006b80`
- `0x1800077a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180007816`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180007816`

## pseudocode

```c
_QWORD *__fastcall CreateThreadFromLambda__lambda_3f888ffeeb51c4c77808cd545df17201_(_QWORD *a1, __int64 a2)
{
  _OWORD *v4; // rax
  const char *v5; // r9
  HANDLE Thread; // rax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x19,
      (__int64)"onecore\\vm\\wsl\\lxss\\wslapi\\WslSession.hpp",
      v5);
  *v4 = *(_OWORD *)a2;
  v4[1] = *(_OWORD *)(a2 + 16);
  *((_QWORD *)v4 + 4) = *(_QWORD *)(a2 + 32);
  *a1 = 0;
  Thread = CreateThread(0, 0, LambdaWrapper__lambda_3f888ffeeb51c4c77808cd545df17201_, v4, 0, 0);
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
0x1800077a4  mov     [rsp+arg_8], rbx
0x1800077a9  push    rdi
0x1800077aa  sub     rsp, 30h
0x1800077ae  mov     rdi, rdx
0x1800077b1  mov     rbx, rcx
0x1800077b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800077bb  mov     ecx, 28h ; '('; unsigned __int64
0x1800077c0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800077c5  test    rax, rax
0x1800077c8  jz      short loc_1800077E2
0x1800077ca  movups  xmm0, xmmword ptr [rdi]
0x1800077cd  movups  xmmword ptr [rax], xmm0
0x1800077d0  movups  xmm1, xmmword ptr [rdi+10h]
0x1800077d4  movups  xmmword ptr [rax+10h], xmm1
0x1800077d8  movsd   xmm0, qword ptr [rdi+20h]
0x1800077dd  movsd   qword ptr [rax+20h], xmm0
0x1800077e2  mov     rcx, [rsp+38h]; this
0x1800077e7  test    rax, rax
0x1800077ea  jnz     short loc_1800077FC
0x1800077ec  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x1800077f3  lea     edx, [rax+19h]; void *
0x1800077f6  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x1800077fc  xor     ecx, ecx; lpThreadAttributes
0x1800077fe  lea     r8, LambdaWrapper__lambda_3f888ffeeb51c4c77808cd545df17201___; lpStartAddress
0x180007805  mov     [rsp+38h+lpThreadId], rcx; lpThreadId
0x18000780a  mov     r9, rax; lpParameter
0x18000780d  xor     edx, edx; dwStackSize
0x18000780f  mov     [rsp+38h+dwCreationFlags], ecx; dwCreationFlags
0x180007813  mov     [rbx], rcx
0x180007816  call    cs:__imp_CreateThread
0x18000781c  mov     [rbx], rax
0x18000781f  test    rax, rax
0x180007822  jnz     short loc_180007839
0x180007824  mov     rcx, [rsp+38h]; this
0x180007829  lea     r8, aOnecoreVmWslLx_1; "onecore\\vm\\wsl\\lxss\\wslapi\\WslSess"...
0x180007830  lea     edx, [rax+22h]; void *
0x180007833  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007839  mov     rax, rbx
0x18000783c  mov     rbx, [rsp+38h+arg_8]
0x180007841  add     rsp, 30h
0x180007845  pop     rdi
0x180007846  retn
```
