# CEnum::Open(void *)

- ea: `0x180008494`
- end: `0x180008501`
- name: `?Open@CEnum@@QEAAJPEAX@Z`
- size: `109`
- prototype: `__int64 __fastcall(CEnum *__hidden this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006ed0`
- `0x180012b40`
- `0x180013fcc`
- `0x180021af0`

## callees

- `0x180005b40`
- `0x180008494`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18003314e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003314e`
- `RPCRT4!NdrClientCall3` at `0x1800084b7`
- `RPCRT4!NdrClientCall3` at `0x1800084b7`

## string_xrefs

- `0x1800084e6`: `RpcOpenEnum threw an exception: 0x%x`

## pseudocode

```c
__int64 __fastcall CEnum::Open(CEnum *this, void *a2)
{
  return (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035048, 0, 0, a2, this).Pointer;
}

```

## disassembly

```asm
0x180008494  push    rbx
0x180008496  sub     rsp, 40h
0x18000849a  mov     [rsp+48h+arg_10], 0
0x1800084a3  mov     [rsp+48h+var_28], rcx
0x1800084a8  mov     r9, rdx
0x1800084ab  xor     r8d, r8d; pReturnValue
0x1800084ae  xor     edx, edx; nProcNum
0x1800084b0  lea     rcx, stru_180035048; pProxyInfo
0x1800084b7  call    cs:__imp_NdrClientCall3
0x1800084be  nop     dword ptr [rax+rax+00h]
0x1800084c3  mov     rbx, rax
0x1800084c6  mov     [rsp+48h+arg_10], rax
0x1800084cb  mov     [rsp+48h+var_18], eax
0x1800084cf  jmp     short loc_1800084F8
0x1800084d1  test    eax, eax
0x1800084d3  jle     short loc_1800084DD
0x1800084d5  movzx   eax, ax
0x1800084d8  or      eax, 80070000h
0x1800084dd  mov     ebx, eax
0x1800084df  mov     [rsp+48h+var_18], eax
0x1800084e3  mov     r8d, eax
0x1800084e6  lea     rdx, aRpcopenenumThr; "RpcOpenEnum threw an exception: 0x%x"
0x1800084ed  mov     ecx, 8; int
0x1800084f2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800084f7  nop
0x1800084f8  mov     eax, ebx
0x1800084fa  add     rsp, 40h
0x1800084fe  pop     rbx
0x1800084ff  retn
0x180033140  push    rbp
0x180033142  sub     rsp, 30h
0x180033146  mov     rbp, rdx
0x180033149  mov     rcx, [rcx]
0x18003314c  mov     ecx, [rcx]; ExceptionCode
0x18003314e  call    cs:__imp_I_RpcExceptionFilter
0x180033155  nop     dword ptr [rax+rax+00h]
0x18003315a  nop
0x18003315b  add     rsp, 30h
0x18003315f  pop     rbp
0x180033160  retn
```
