# CEnum::Open(void *)

- ea: `0x180009ba4`
- end: `0x180009c0a`
- name: `?Open@CEnum@@QEAAJPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CEnum *__hidden this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008740`
- `0x180011cb0`
- `0x180013088`
- `0x180020380`

## callees

- `0x180007890`
- `0x180009ba4`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x1800303d0`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800303d0`
- `RPCRT4!NdrClientCall3` at `0x180009bc7`
- `RPCRT4!NdrClientCall3` at `0x180009bc7`

## string_xrefs

- `0x180009bf0`: `RpcOpenEnum threw an exception: 0x%x`

## pseudocode

```c
__int64 __fastcall CEnum::Open(CEnum *this, void *a2)
{
  return (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800320B0, 0, 0, a2, this).Pointer;
}

```

## disassembly

```asm
0x180009ba4  push    rbx
0x180009ba6  sub     rsp, 40h
0x180009baa  mov     [rsp+48h+arg_10], 0
0x180009bb3  mov     [rsp+48h+var_28], rcx
0x180009bb8  mov     r9, rdx
0x180009bbb  xor     r8d, r8d; pReturnValue
0x180009bbe  xor     edx, edx; nProcNum
0x180009bc0  lea     rcx, stru_1800320B0; pProxyInfo
0x180009bc7  call    cs:__imp_NdrClientCall3
0x180009bcd  mov     rbx, rax
0x180009bd0  mov     [rsp+48h+arg_10], rax
0x180009bd5  mov     [rsp+48h+var_18], eax
0x180009bd9  jmp     short loc_180009C02
0x180009bdb  test    eax, eax
0x180009bdd  jle     short loc_180009BE7
0x180009bdf  movzx   eax, ax
0x180009be2  or      eax, 80070000h
0x180009be7  mov     ebx, eax
0x180009be9  mov     [rsp+48h+var_18], eax
0x180009bed  mov     r8d, eax
0x180009bf0  lea     rdx, aRpcopenenumThr; "RpcOpenEnum threw an exception: 0x%x"
0x180009bf7  mov     ecx, 8; int
0x180009bfc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009c01  nop
0x180009c02  mov     eax, ebx
0x180009c04  add     rsp, 40h
0x180009c08  pop     rbx
0x180009c09  retn
0x1800303c2  push    rbp
0x1800303c4  sub     rsp, 30h
0x1800303c8  mov     rbp, rdx
0x1800303cb  mov     rcx, [rcx]
0x1800303ce  mov     ecx, [rcx]; ExceptionCode
0x1800303d0  call    cs:__imp_I_RpcExceptionFilter
0x1800303d6  nop
0x1800303d7  add     rsp, 30h
0x1800303db  pop     rbp
0x1800303dc  retn
```
