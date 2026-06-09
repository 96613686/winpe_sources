# QuerySessionIsolationConfigId(ulong)

- ea: `0x1800287d8`
- end: `0x18002888e`
- name: `?QuerySessionIsolationConfigId@@YA?AW4_ISOLATION_CONFIG_ID@@K@Z`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800288a0`
- `0x180029c60`

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x1800287d8`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180028838`
- `RPCRT4!NdrClientCall3` at `0x180028838`

## string_xrefs

- `0x180028866`: `RpcGetIsolationConfigId failed: 0x%x`

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
    v3.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035290, 4u, 0, v2, v6, &v8).Pointer;
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
0x1800287d8  push    rbx
0x1800287da  sub     rsp, 50h
0x1800287de  mov     ebx, ecx
0x1800287e0  xor     r8d, r8d; int
0x1800287e3  xor     edx, edx; void *
0x1800287e5  lea     rcx, [rsp+58h+var_20]; this
0x1800287ea  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800287ef  mov     [rsp+58h+arg_8], 0
0x1800287f7  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x1800287fc  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180028801  test    rax, rax
0x180028804  jz      short loc_180028877
0x180028806  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002880b  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180028810  mov     [rsp+58h+arg_10], 0
0x180028819  lea     rcx, [rsp+58h+arg_8]
0x18002881e  mov     [rsp+58h+var_30], rcx
0x180028823  mov     [rsp+58h+var_38], ebx
0x180028827  mov     r9, rax
0x18002882a  xor     r8d, r8d; pReturnValue
0x18002882d  lea     edx, [r8+4]; nProcNum
0x180028831  lea     rcx, stru_180035290; pProxyInfo
0x180028838  call    cs:__imp_NdrClientCall3
0x18002883f  nop     dword ptr [rax+rax+00h]
0x180028844  mov     [rsp+58h+arg_10], rax
0x180028849  mov     [rsp+58h+var_28], eax
0x18002884d  jmp     short loc_18002885F
0x18002884f  test    eax, eax
0x180028851  jle     short loc_18002885B
0x180028853  movzx   eax, ax
0x180028856  or      eax, 80070000h
0x18002885b  mov     [rsp+58h+var_28], eax
0x18002885f  test    eax, eax
0x180028861  jns     short loc_180028877
0x180028863  mov     r8d, eax
0x180028866  lea     rdx, aRpcgetisolatio; "RpcGetIsolationConfigId failed: 0x%x"
0x18002886d  mov     ecx, 8; int
0x180028872  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028877  mov     ebx, [rsp+58h+arg_8]
0x18002887b  lea     rcx, [rsp+58h+var_20]; this
0x180028880  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180028885  mov     eax, ebx
0x180028887  add     rsp, 50h
0x18002888b  pop     rbx
0x18002888c  retn
0x180033757  push    rbp
0x180033759  sub     rsp, 30h
0x18003375d  mov     rbp, rdx
0x180033760  mov     rcx, [rcx]
0x180033763  mov     ecx, [rcx]; ExceptionCode
0x180033765  call    cs:__imp_I_RpcExceptionFilter
0x18003376c  nop     dword ptr [rax+rax+00h]
0x180033771  nop
0x180033772  add     rsp, 30h
0x180033776  pop     rbp
0x180033777  retn
```
