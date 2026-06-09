# RPCExceptBoundary__lambda_1d2eb701b8763d3028b04fd942a7679d_

- ea: `0x18001228c`
- end: `0x180012316`
- name: `_RPCExceptBoundary__lambda_1d2eb701b8763d3028b04fd942a7679d___`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800128cc`

## callees

- `0x18000cea0`
- `0x18001228c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800122c7`
- `RPCRT4!NdrClientCall3` at `0x1800122c7`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001aefc`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001aefc`

## string_xrefs

- `0x1800122e1`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
__int64 __fastcall RPCExceptBoundary__lambda_1d2eb701b8763d3028b04fd942a7679d_(_QWORD **a1)
{
  int Pointer; // eax
  unsigned int v2; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 4u, 0, **a1, *a1[1], *a1[2]).Pointer;
  v2 = Pointer;
  if ( Pointer >= 0 )
    return 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
      (const char *)(unsigned int)Pointer);
  return v2;
}

```

## disassembly

```asm
0x18001228c  push    rbx
0x18001228e  sub     rsp, 40h
0x180012292  mov     rax, [rcx+10h]
0x180012296  mov     r8, [rax]
0x180012299  mov     rax, [rcx+8]
0x18001229d  mov     rdx, [rax]
0x1800122a0  mov     rax, [rcx]
0x1800122a3  mov     [rsp+48h+arg_8], 0
0x1800122ac  mov     [rsp+48h+var_20], r8
0x1800122b1  mov     qword ptr [rsp+48h+var_28], rdx; int
0x1800122b6  mov     r9, [rax]
0x1800122b9  xor     r8d, r8d; pReturnValue
0x1800122bc  lea     edx, [r8+4]; nProcNum
0x1800122c0  lea     rcx, pProxyInfo; pProxyInfo
0x1800122c7  call    cs:__imp_NdrClientCall3
0x1800122cd  mov     rbx, rax
0x1800122d0  mov     [rsp+48h+arg_8], rax
0x1800122d5  test    eax, eax
0x1800122d7  jns     short loc_1800122F4
0x1800122d9  mov     rcx, [rsp+48h]; this
0x1800122de  mov     r9d, eax; char *
0x1800122e1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800122e8  mov     edx, 18Eh; void *
0x1800122ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800122f2  jmp     short loc_1800122F6
0x1800122f4  xor     ebx, ebx
0x1800122f6  mov     [rsp+48h+var_18], ebx
0x1800122fa  jmp     short loc_18001230E
0x1800122fc  test    eax, eax
0x1800122fe  jle     short loc_180012308
0x180012300  movzx   eax, ax
0x180012303  or      eax, 80070000h
0x180012308  mov     ebx, eax
0x18001230a  mov     [rsp+48h+var_18], eax
0x18001230e  mov     eax, ebx
0x180012310  add     rsp, 40h
0x180012314  pop     rbx
0x180012315  retn
0x18001aeee  push    rbp
0x18001aef0  sub     rsp, 30h
0x18001aef4  mov     rbp, rdx
0x18001aef7  mov     rcx, [rcx]
0x18001aefa  mov     ecx, [rcx]; ExceptionCode
0x18001aefc  call    cs:__imp_I_RpcExceptionFilter
0x18001af02  nop
0x18001af03  add     rsp, 30h
0x18001af07  pop     rbp
0x18001af08  retn
```
