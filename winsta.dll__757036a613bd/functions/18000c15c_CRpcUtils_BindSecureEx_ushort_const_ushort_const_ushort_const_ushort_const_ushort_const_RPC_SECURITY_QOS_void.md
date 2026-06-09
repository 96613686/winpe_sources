# CRpcUtils::BindSecureEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_RPC_SECURITY_QOS *,void * *)

- ea: `0x18000c15c`
- end: `0x18000c244`
- name: `?BindSecureEx@CRpcUtils@@SAJPEBG0000PEAU_RPC_SECURITY_QOS@@PEAPEAX@Z`
- size: `232`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _RPC_SECURITY_QOS *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c0e8`
- `0x18001fad0`

## callees

- `0x180007890`
- `0x18000c15c`
- `0x18000c250`
- `0x18000c2d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c1f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c1f8`
- `RPCRT4!RpcBindingFree` at `0x18000c22c`
- `RPCRT4!RpcBindingFree` at `0x18000c22c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000c1eb`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000c203`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000c1eb`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000c203`

## pseudocode

```c
__int64 __fastcall CRpcUtils::BindSecureEx(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct _RPC_SECURITY_QOS *SecurityQOS,
        void **Binding)
{
  unsigned int v8; // ebx
  int v9; // eax
  RPC_BINDING_HANDLE v10; // rcx
  RPC_WSTR ServerPrincName; // [rsp+40h] [rbp-18h] BYREF

  ServerPrincName = 0;
  *Binding = 0;
  v8 = CRpcUtils::Bind(a1, a2, a3, a4, a5, Binding);
  if ( v8 )
  {
    _DbgPrintMessage(8, "Error %d in TermSrvBind", v8);
    goto LABEL_8;
  }
  v9 = CRpcUtils::PrepareServerSPN(a3, &ServerPrincName);
  v10 = *Binding;
  if ( v9 )
  {
    v8 = RpcBindingSetAuthInfoExW(v10, ServerPrincName, 6u, 9u, 0, 1u, SecurityQOS);
    LocalFree(ServerPrincName);
  }
  else
  {
    v8 = RpcBindingSetAuthInfoExW(v10, a3, 6u, 9u, 0, 1u, SecurityQOS);
  }
  if ( v8 )
  {
    _DbgPrintMessage(8, "Error %d in RpcBindingSetAuthInfoEx", v8);
LABEL_8:
    if ( *Binding )
      RpcBindingFree(Binding);
  }
  return v8;
}

```

## disassembly

```asm
0x18000c15c  mov     r11, rsp
0x18000c15f  mov     [r11+8], rbx
0x18000c163  mov     [r11+10h], rsi
0x18000c167  push    rdi
0x18000c168  sub     rsp, 50h
0x18000c16c  mov     rdi, [rsp+58h+Binding]
0x18000c174  mov     rsi, r8
0x18000c177  mov     rax, [rsp+58h+arg_20]
0x18000c17f  mov     [r11-30h], rdi
0x18000c183  mov     qword ptr [r11-18h], 0
0x18000c18b  mov     qword ptr [rdi], 0
0x18000c192  mov     [r11-38h], rax
0x18000c196  call    ?Bind@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::Bind(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x18000c19b  mov     ebx, eax
0x18000c19d  test    eax, eax
0x18000c19f  jz      short loc_18000C1AA
0x18000c1a1  lea     rdx, aErrorDInTermsr; "Error %d in TermSrvBind"
0x18000c1a8  jmp     short loc_18000C216
0x18000c1aa  lea     rdx, [rsp+58h+ServerPrincName]; unsigned __int16 **
0x18000c1af  mov     rcx, rsi; unsigned __int16 *
0x18000c1b2  call    ?PrepareServerSPN@CRpcUtils@@SAHPEBGPEAPEAG@Z; CRpcUtils::PrepareServerSPN(ushort const *,ushort * *)
0x18000c1b7  mov     rcx, [rdi]; Binding
0x18000c1ba  mov     r9d, 9; AuthnSvc
0x18000c1c0  test    eax, eax
0x18000c1c2  mov     rax, [rsp+58h+arg_28]
0x18000c1ca  mov     [rsp+58h+SecurityQOS], rax; SecurityQOS
0x18000c1cf  mov     [rsp+58h+AuthzSvc], 1; AuthzSvc
0x18000c1d7  lea     r8d, [r9-3]; AuthnLevel
0x18000c1db  mov     [rsp+58h+AuthIdentity], 0; AuthIdentity
0x18000c1e4  jz      short loc_18000C200
0x18000c1e6  mov     rdx, [rsp+58h+ServerPrincName]; ServerPrincName
0x18000c1eb  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000c1f1  mov     rcx, [rsp+58h+ServerPrincName]; hMem
0x18000c1f6  mov     ebx, eax
0x18000c1f8  call    cs:__imp_LocalFree
0x18000c1fe  jmp     short loc_18000C20B
0x18000c200  mov     rdx, rsi; ServerPrincName
0x18000c203  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000c209  mov     ebx, eax
0x18000c20b  test    ebx, ebx
0x18000c20d  jz      short loc_18000C232
0x18000c20f  lea     rdx, aErrorDInRpcbin; "Error %d in RpcBindingSetAuthInfoEx"
0x18000c216  mov     r8d, ebx
0x18000c219  mov     ecx, 8; int
0x18000c21e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000c223  cmp     qword ptr [rdi], 0
0x18000c227  jz      short loc_18000C232
0x18000c229  mov     rcx, rdi; Binding
0x18000c22c  call    cs:__imp_RpcBindingFree
0x18000c232  mov     rsi, [rsp+58h+arg_8]
0x18000c237  mov     eax, ebx
0x18000c239  mov     rbx, [rsp+58h+arg_0]
0x18000c23e  add     rsp, 50h
0x18000c242  pop     rdi
0x18000c243  retn
```
