# CRpcUtils::BindSecureEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_RPC_SECURITY_QOS *,void * *)

- ea: `0x18000dcec`
- end: `0x18000dded`
- name: `?BindSecureEx@CRpcUtils@@SAJPEBG0000PEAU_RPC_SECURITY_QOS@@PEAPEAX@Z`
- size: `257`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _RPC_SECURITY_QOS *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000dc78`
- `0x1800211d0`

## callees

- `0x180005b40`
- `0x18000dcec`
- `0x18000de00`
- `0x18000de98`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd8e`
- `RPCRT4!RpcBindingFree` at `0x18000ddce`
- `RPCRT4!RpcBindingFree` at `0x18000ddce`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000dd7b`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000dd9f`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000dd7b`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000dd9f`

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
0x18000dcec  mov     r11, rsp
0x18000dcef  mov     [r11+8], rbx
0x18000dcf3  mov     [r11+10h], rsi
0x18000dcf7  push    rdi
0x18000dcf8  sub     rsp, 50h
0x18000dcfc  mov     rdi, [rsp+58h+Binding]
0x18000dd04  mov     rsi, r8
0x18000dd07  mov     rax, [rsp+58h+arg_20]
0x18000dd0f  mov     [r11-30h], rdi
0x18000dd13  mov     qword ptr [r11-18h], 0
0x18000dd1b  mov     qword ptr [rdi], 0
0x18000dd22  mov     [r11-38h], rax
0x18000dd26  call    ?Bind@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::Bind(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x18000dd2b  mov     ebx, eax
0x18000dd2d  test    eax, eax
0x18000dd2f  jz      short loc_18000DD3A
0x18000dd31  lea     rdx, aErrorDInTermsr; "Error %d in TermSrvBind"
0x18000dd38  jmp     short loc_18000DDB8
0x18000dd3a  lea     rdx, [rsp+58h+ServerPrincName]; unsigned __int16 **
0x18000dd3f  mov     rcx, rsi; unsigned __int16 *
0x18000dd42  call    ?PrepareServerSPN@CRpcUtils@@SAHPEBGPEAPEAG@Z; CRpcUtils::PrepareServerSPN(ushort const *,ushort * *)
0x18000dd47  mov     rcx, [rdi]; Binding
0x18000dd4a  mov     r9d, 9; AuthnSvc
0x18000dd50  test    eax, eax
0x18000dd52  mov     rax, [rsp+58h+arg_28]
0x18000dd5a  mov     [rsp+58h+SecurityQOS], rax; SecurityQOS
0x18000dd5f  mov     [rsp+58h+AuthzSvc], 1; AuthzSvc
0x18000dd67  lea     r8d, [r9-3]; AuthnLevel
0x18000dd6b  mov     [rsp+58h+AuthIdentity], 0; AuthIdentity
0x18000dd74  jz      short loc_18000DD9C
0x18000dd76  mov     rdx, [rsp+58h+ServerPrincName]; ServerPrincName
0x18000dd7b  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000dd82  nop     dword ptr [rax+rax+00h]
0x18000dd87  mov     rcx, [rsp+58h+ServerPrincName]; hMem
0x18000dd8c  mov     ebx, eax
0x18000dd8e  call    cs:__imp_LocalFree
0x18000dd95  nop     dword ptr [rax+rax+00h]
0x18000dd9a  jmp     short loc_18000DDAD
0x18000dd9c  mov     rdx, rsi; ServerPrincName
0x18000dd9f  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000dda6  nop     dword ptr [rax+rax+00h]
0x18000ddab  mov     ebx, eax
0x18000ddad  test    ebx, ebx
0x18000ddaf  jz      short loc_18000DDDA
0x18000ddb1  lea     rdx, aErrorDInRpcbin; "Error %d in RpcBindingSetAuthInfoEx"
0x18000ddb8  mov     r8d, ebx
0x18000ddbb  mov     ecx, 8; int
0x18000ddc0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ddc5  cmp     qword ptr [rdi], 0
0x18000ddc9  jz      short loc_18000DDDA
0x18000ddcb  mov     rcx, rdi; Binding
0x18000ddce  call    cs:__imp_RpcBindingFree
0x18000ddd5  nop     dword ptr [rax+rax+00h]
0x18000ddda  mov     rsi, [rsp+58h+arg_8]
0x18000dddf  mov     eax, ebx
0x18000dde1  mov     rbx, [rsp+58h+arg_0]
0x18000dde6  add     rsp, 50h
0x18000ddea  pop     rdi
0x18000ddeb  retn
```
