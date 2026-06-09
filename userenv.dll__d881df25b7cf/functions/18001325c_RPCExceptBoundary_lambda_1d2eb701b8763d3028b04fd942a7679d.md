# RPCExceptBoundary__lambda_1d2eb701b8763d3028b04fd942a7679d_

- ea: `0x18001325c`
- end: `0x1800132ed`
- name: `_RPCExceptBoundary__lambda_1d2eb701b8763d3028b04fd942a7679d___`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013984`

## callees

- `0x18000db08`
- `0x18001325c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180013297`
- `RPCRT4!NdrClientCall3` at `0x180013297`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001ca5e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001ca5e`

## string_xrefs

- `0x1800132b7`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall RPCExceptBoundary__lambda_1d2eb701b8763d3028b04fd942a7679d_(_QWORD **a1)
{
  int Pointer; // eax
  unsigned int v2; // ebx
  int v4[2]; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)v4 = *a1[1];
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 4u, 0, **a1).Pointer;
  v2 = Pointer;
  if ( Pointer >= 0 )
    return 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)Pointer,
      v4[0]);
  return v2;
}

```

## disassembly

```asm
0x18001325c  push    rbx
0x18001325e  sub     rsp, 40h
0x180013262  mov     rax, [rcx+10h]
0x180013266  mov     r8, [rax]
0x180013269  mov     rax, [rcx+8]
0x18001326d  mov     rdx, [rax]
0x180013270  mov     rax, [rcx]
0x180013273  mov     [rsp+48h+arg_8], 0
0x18001327c  mov     [rsp+48h+var_20], r8
0x180013281  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180013286  mov     r9, [rax]
0x180013289  xor     r8d, r8d; pReturnValue
0x18001328c  lea     edx, [r8+4]; nProcNum
0x180013290  lea     rcx, pProxyInfo; pProxyInfo
0x180013297  call    cs:__imp_NdrClientCall3
0x18001329e  nop     dword ptr [rax+rax+00h]
0x1800132a3  mov     rbx, rax
0x1800132a6  mov     [rsp+48h+arg_8], rax
0x1800132ab  test    eax, eax
0x1800132ad  jns     short loc_1800132CA
0x1800132af  mov     rcx, [rsp+48h]; this
0x1800132b4  mov     r9d, eax; char *
0x1800132b7  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800132be  mov     edx, 18Eh; void *
0x1800132c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800132c8  jmp     short loc_1800132CC
0x1800132ca  xor     ebx, ebx
0x1800132cc  mov     [rsp+48h+var_18], ebx
0x1800132d0  jmp     short loc_1800132E4
0x1800132d2  test    eax, eax
0x1800132d4  jle     short loc_1800132DE
0x1800132d6  movzx   eax, ax
0x1800132d9  or      eax, 80070000h
0x1800132de  mov     ebx, eax
0x1800132e0  mov     [rsp+48h+var_18], eax
0x1800132e4  mov     eax, ebx
0x1800132e6  add     rsp, 40h
0x1800132ea  pop     rbx
0x1800132eb  retn
0x18001ca50  push    rbp
0x18001ca52  sub     rsp, 30h
0x18001ca56  mov     rbp, rdx
0x18001ca59  mov     rcx, [rcx]
0x18001ca5c  mov     ecx, [rcx]; ExceptionCode
0x18001ca5e  call    cs:__imp_I_RpcExceptionFilter
0x18001ca65  nop     dword ptr [rax+rax+00h]
0x18001ca6a  nop
0x18001ca6b  add     rsp, 30h
0x18001ca6f  pop     rbp
0x18001ca70  retn
```
