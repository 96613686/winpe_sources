# CListener::Open(void *,ushort *)

- ea: `0x18000adc4`
- end: `0x18000ae36`
- name: `?Open@CListener@@QEAAJPEAXPEAG@Z`
- size: `114`
- prototype: `__int64 __fastcall(CListener *__hidden this, void *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aac4`
- `0x180021fa4`

## callees

- `0x180005b40`
- `0x18000adc4`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x1800332d0`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800332d0`
- `RPCRT4!NdrClientCall3` at `0x18000adec`
- `RPCRT4!NdrClientCall3` at `0x18000adec`

## string_xrefs

- `0x18000ae1b`: `RpcOpenListener threw an exception: 0x%x`

## pseudocode

```c
__int64 __fastcall CListener::Open(CListener *this, void *a2, unsigned __int16 *a3)
{
  return (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800350A8, 0, 0, a2, a3, this).Pointer;
}

```

## disassembly

```asm
0x18000adc4  push    rbx
0x18000adc6  sub     rsp, 40h
0x18000adca  mov     [rsp+48h+arg_18], 0
0x18000add3  mov     [rsp+48h+var_20], rcx
0x18000add8  mov     [rsp+48h+var_28], r8
0x18000addd  mov     r9, rdx
0x18000ade0  xor     r8d, r8d; pReturnValue
0x18000ade3  xor     edx, edx; nProcNum
0x18000ade5  lea     rcx, stru_1800350A8; pProxyInfo
0x18000adec  call    cs:__imp_NdrClientCall3
0x18000adf3  nop     dword ptr [rax+rax+00h]
0x18000adf8  mov     rbx, rax
0x18000adfb  mov     [rsp+48h+arg_18], rax
0x18000ae00  mov     [rsp+48h+var_18], eax
0x18000ae04  jmp     short loc_18000AE2D
0x18000ae06  test    eax, eax
0x18000ae08  jle     short loc_18000AE12
0x18000ae0a  movzx   eax, ax
0x18000ae0d  or      eax, 80070000h
0x18000ae12  mov     ebx, eax
0x18000ae14  mov     [rsp+48h+var_18], eax
0x18000ae18  mov     r8d, eax
0x18000ae1b  lea     rdx, aRpcopenlistene; "RpcOpenListener threw an exception: 0x%"...
0x18000ae22  mov     ecx, 8; int
0x18000ae27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ae2c  nop
0x18000ae2d  mov     eax, ebx
0x18000ae2f  add     rsp, 40h
0x18000ae33  pop     rbx
0x18000ae34  retn
0x1800332c2  push    rbp
0x1800332c4  sub     rsp, 30h
0x1800332c8  mov     rbp, rdx
0x1800332cb  mov     rcx, [rcx]
0x1800332ce  mov     ecx, [rcx]; ExceptionCode
0x1800332d0  call    cs:__imp_I_RpcExceptionFilter
0x1800332d7  nop     dword ptr [rax+rax+00h]
0x1800332dc  nop
0x1800332dd  add     rsp, 30h
0x1800332e1  pop     rbp
0x1800332e2  retn
```
