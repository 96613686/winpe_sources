# CListener::Open(void *,ushort *)

- ea: `0x180003ad4`
- end: `0x180003b3f`
- name: `?Open@CListener@@QEAAJPEAXPEAG@Z`
- size: `107`
- prototype: `__int64 __fastcall(CListener *__hidden this, void *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ba8`
- `0x1800207f4`

## callees

- `0x180003ad4`
- `0x180007890`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180030088`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030088`
- `RPCRT4!NdrClientCall3` at `0x180003afc`
- `RPCRT4!NdrClientCall3` at `0x180003afc`

## string_xrefs

- `0x180003b25`: `RpcOpenListener threw an exception: 0x%x`

## pseudocode

```c
__int64 __fastcall CListener::Open(CListener *this, void *a2, unsigned __int16 *a3)
{
  return (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032110, 0, 0, a2, a3, this).Pointer;
}

```

## disassembly

```asm
0x180003ad4  push    rbx
0x180003ad6  sub     rsp, 40h
0x180003ada  mov     [rsp+48h+arg_18], 0
0x180003ae3  mov     [rsp+48h+var_20], rcx
0x180003ae8  mov     [rsp+48h+var_28], r8
0x180003aed  mov     r9, rdx
0x180003af0  xor     r8d, r8d; pReturnValue
0x180003af3  xor     edx, edx; nProcNum
0x180003af5  lea     rcx, stru_180032110; pProxyInfo
0x180003afc  call    cs:__imp_NdrClientCall3
0x180003b02  mov     rbx, rax
0x180003b05  mov     [rsp+48h+arg_18], rax
0x180003b0a  mov     [rsp+48h+var_18], eax
0x180003b0e  jmp     short loc_180003B37
0x180003b10  test    eax, eax
0x180003b12  jle     short loc_180003B1C
0x180003b14  movzx   eax, ax
0x180003b17  or      eax, 80070000h
0x180003b1c  mov     ebx, eax
0x180003b1e  mov     [rsp+48h+var_18], eax
0x180003b22  mov     r8d, eax
0x180003b25  lea     rdx, aRpcopenlistene; "RpcOpenListener threw an exception: 0x%"...
0x180003b2c  mov     ecx, 8; int
0x180003b31  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003b36  nop
0x180003b37  mov     eax, ebx
0x180003b39  add     rsp, 40h
0x180003b3d  pop     rbx
0x180003b3e  retn
0x18003007a  push    rbp
0x18003007c  sub     rsp, 30h
0x180030080  mov     rbp, rdx
0x180030083  mov     rcx, [rcx]
0x180030086  mov     ecx, [rcx]; ExceptionCode
0x180030088  call    cs:__imp_I_RpcExceptionFilter
0x18003008e  nop
0x18003008f  add     rsp, 30h
0x180030093  pop     rbp
0x180030094  retn
```
