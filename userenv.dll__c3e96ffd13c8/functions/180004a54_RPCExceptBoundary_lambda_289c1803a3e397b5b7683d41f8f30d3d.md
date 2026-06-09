# RPCExceptBoundary__lambda_289c1803a3e397b5b7683d41f8f30d3d_

- ea: `0x180004a54`
- end: `0x180004ad9`
- name: `_RPCExceptBoundary__lambda_289c1803a3e397b5b7683d41f8f30d3d___`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004938`

## callees

- `0x180004a54`
- `0x18000cea0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180004a8a`
- `RPCRT4!NdrClientCall3` at `0x180004a8a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001ada4`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001ada4`

## string_xrefs

- `0x180004aa8`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall RPCExceptBoundary__lambda_289c1803a3e397b5b7683d41f8f30d3d_(_QWORD **a1)
{
  int Pointer; // eax
  unsigned int v2; // ebx
  int v4[2]; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)v4 = *a1[1];
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, **a1).Pointer;
  v2 = Pointer;
  if ( Pointer < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)Pointer,
      v4[0]);
  else
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180004a54  push    rbx
0x180004a56  sub     rsp, 40h
0x180004a5a  mov     r8, [rcx+10h]
0x180004a5e  mov     rax, [rcx+8]
0x180004a62  mov     rdx, [rax]
0x180004a65  mov     rax, [rcx]
0x180004a68  mov     [rsp+48h+arg_8], 0
0x180004a71  mov     [rsp+48h+var_20], r8
0x180004a76  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180004a7b  mov     r9, [rax]
0x180004a7e  xor     r8d, r8d; pReturnValue
0x180004a81  xor     edx, edx; nProcNum
0x180004a83  lea     rcx, pProxyInfo; pProxyInfo
0x180004a8a  call    cs:__imp_NdrClientCall3
0x180004a90  mov     rbx, rax
0x180004a93  mov     [rsp+48h+arg_8], rax
0x180004a98  test    eax, eax
0x180004a9a  js      short loc_180004AA0
0x180004a9c  xor     ebx, ebx
0x180004a9e  jmp     short loc_180004AB9
0x180004aa0  mov     rcx, [rsp+48h]; this
0x180004aa5  mov     r9d, eax; char *
0x180004aa8  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180004aaf  mov     edx, 0DCh; void *
0x180004ab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ab9  mov     [rsp+48h+var_18], ebx
0x180004abd  jmp     short loc_180004AD1
0x180004abf  test    eax, eax
0x180004ac1  jle     short loc_180004ACB
0x180004ac3  movzx   eax, ax
0x180004ac6  or      eax, 80070000h
0x180004acb  mov     ebx, eax
0x180004acd  mov     [rsp+48h+var_18], eax
0x180004ad1  mov     eax, ebx
0x180004ad3  add     rsp, 40h
0x180004ad7  pop     rbx
0x180004ad8  retn
0x18001ad96  push    rbp
0x18001ad98  sub     rsp, 30h
0x18001ad9c  mov     rbp, rdx
0x18001ad9f  mov     rcx, [rcx]
0x18001ada2  mov     ecx, [rcx]; ExceptionCode
0x18001ada4  call    cs:__imp_I_RpcExceptionFilter
0x18001adaa  nop
0x18001adab  add     rsp, 30h
0x18001adaf  pop     rbp
0x18001adb0  retn
```
