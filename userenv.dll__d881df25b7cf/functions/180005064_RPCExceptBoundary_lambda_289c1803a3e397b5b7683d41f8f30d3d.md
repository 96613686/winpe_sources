# RPCExceptBoundary__lambda_289c1803a3e397b5b7683d41f8f30d3d_

- ea: `0x180005064`
- end: `0x1800050f0`
- name: `_RPCExceptBoundary__lambda_289c1803a3e397b5b7683d41f8f30d3d___`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004f48`

## callees

- `0x180005064`
- `0x18000db08`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000509a`
- `RPCRT4!NdrClientCall3` at `0x18000509a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001c8f4`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001c8f4`

## string_xrefs

- `0x1800050be`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

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
0x180005064  push    rbx
0x180005066  sub     rsp, 40h
0x18000506a  mov     r8, [rcx+10h]
0x18000506e  mov     rax, [rcx+8]
0x180005072  mov     rdx, [rax]
0x180005075  mov     rax, [rcx]
0x180005078  mov     [rsp+48h+arg_8], 0
0x180005081  mov     [rsp+48h+var_20], r8
0x180005086  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18000508b  mov     r9, [rax]
0x18000508e  xor     r8d, r8d; pReturnValue
0x180005091  xor     edx, edx; nProcNum
0x180005093  lea     rcx, pProxyInfo; pProxyInfo
0x18000509a  call    cs:__imp_NdrClientCall3
0x1800050a1  nop     dword ptr [rax+rax+00h]
0x1800050a6  mov     rbx, rax
0x1800050a9  mov     [rsp+48h+arg_8], rax
0x1800050ae  test    eax, eax
0x1800050b0  js      short loc_1800050B6
0x1800050b2  xor     ebx, ebx
0x1800050b4  jmp     short loc_1800050CF
0x1800050b6  mov     rcx, [rsp+48h]; this
0x1800050bb  mov     r9d, eax; char *
0x1800050be  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800050c5  mov     edx, 0DCh; void *
0x1800050ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050cf  mov     [rsp+48h+var_18], ebx
0x1800050d3  jmp     short loc_1800050E7
0x1800050d5  test    eax, eax
0x1800050d7  jle     short loc_1800050E1
0x1800050d9  movzx   eax, ax
0x1800050dc  or      eax, 80070000h
0x1800050e1  mov     ebx, eax
0x1800050e3  mov     [rsp+48h+var_18], eax
0x1800050e7  mov     eax, ebx
0x1800050e9  add     rsp, 40h
0x1800050ed  pop     rbx
0x1800050ee  retn
0x18001c8e6  push    rbp
0x18001c8e8  sub     rsp, 30h
0x18001c8ec  mov     rbp, rdx
0x18001c8ef  mov     rcx, [rcx]
0x18001c8f2  mov     ecx, [rcx]; ExceptionCode
0x18001c8f4  call    cs:__imp_I_RpcExceptionFilter
0x18001c8fb  nop     dword ptr [rax+rax+00h]
0x18001c900  nop
0x18001c901  add     rsp, 30h
0x18001c905  pop     rbp
0x18001c906  retn
```
