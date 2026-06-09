# QuerySessionIsolationConfigId(ulong)

- ea: `0x180026d68`
- end: `0x180026e17`
- name: `?QuerySessionIsolationConfigId@@YA?AW4_ISOLATION_CONFIG_ID@@K@Z`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180026e20`
- `0x180028120`

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180026d68`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180026dc8`
- `RPCRT4!NdrClientCall3` at `0x180026dc8`

## string_xrefs

- `0x180026df0`: `RpcGetIsolationConfigId failed: 0x%x`

## pseudocode

```c
__int64 __fastcall QuerySessionIsolationConfigId(int a1)
{
  void *v2; // rax
  CLIENT_CALL_RETURN v3; // rax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-38h]
  unsigned __int16 v7[16]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v8; // [rsp+68h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v9; // [rsp+70h] [rbp+18h]

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v7, 0, 0);
  v8 = 0;
  if ( CSmartPublicBinding::operator void *(v7) )
  {
    v2 = CSmartPublicBinding::operator void *(v7);
    v9.Simple = 0;
    v6 = a1;
    v3.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032290, 4u, 0, v2, v6, &v8).Pointer;
    v9.Pointer = v3.Pointer;
    if ( SLODWORD(v3.Simple) < 0 )
      _DbgPrintMessage(8, "RpcGetIsolationConfigId failed: 0x%x", LODWORD(v3.Pointer));
  }
  v4 = v8;
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v7);
  return v4;
}

```

## disassembly

```asm
0x180026d68  push    rbx
0x180026d6a  sub     rsp, 50h
0x180026d6e  mov     ebx, ecx
0x180026d70  xor     r8d, r8d; int
0x180026d73  xor     edx, edx; void *
0x180026d75  lea     rcx, [rsp+58h+var_20]; this
0x180026d7a  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180026d7f  mov     [rsp+58h+arg_8], 0
0x180026d87  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180026d8c  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180026d91  test    rax, rax
0x180026d94  jz      short loc_180026E01
0x180026d96  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180026d9b  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180026da0  mov     [rsp+58h+arg_10], 0
0x180026da9  lea     rcx, [rsp+58h+arg_8]
0x180026dae  mov     [rsp+58h+var_30], rcx
0x180026db3  mov     [rsp+58h+var_38], ebx
0x180026db7  mov     r9, rax
0x180026dba  xor     r8d, r8d; pReturnValue
0x180026dbd  lea     edx, [r8+4]; nProcNum
0x180026dc1  lea     rcx, stru_180032290; pProxyInfo
0x180026dc8  call    cs:__imp_NdrClientCall3
0x180026dce  mov     [rsp+58h+arg_10], rax
0x180026dd3  mov     [rsp+58h+var_28], eax
0x180026dd7  jmp     short loc_180026DE9
0x180026dd9  test    eax, eax
0x180026ddb  jle     short loc_180026DE5
0x180026ddd  movzx   eax, ax
0x180026de0  or      eax, 80070000h
0x180026de5  mov     [rsp+58h+var_28], eax
0x180026de9  test    eax, eax
0x180026deb  jns     short loc_180026E01
0x180026ded  mov     r8d, eax
0x180026df0  lea     rdx, aRpcgetisolatio; "RpcGetIsolationConfigId failed: 0x%x"
0x180026df7  mov     ecx, 8; int
0x180026dfc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180026e01  mov     ebx, [rsp+58h+arg_8]
0x180026e05  lea     rcx, [rsp+58h+var_20]; this
0x180026e0a  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180026e0f  mov     eax, ebx
0x180026e11  add     rsp, 50h
0x180026e15  pop     rbx
0x180026e16  retn
0x180030851  push    rbp
0x180030853  sub     rsp, 30h
0x180030857  mov     rbp, rdx
0x18003085a  mov     rcx, [rcx]
0x18003085d  mov     ecx, [rcx]; ExceptionCode
0x18003085f  call    cs:__imp_I_RpcExceptionFilter
0x180030865  nop
0x180030866  add     rsp, 30h
0x18003086a  pop     rbp
0x18003086b  retn
```
