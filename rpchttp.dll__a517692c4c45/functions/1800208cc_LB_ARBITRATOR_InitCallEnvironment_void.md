# LB_ARBITRATOR::InitCallEnvironment(void)

- ea: `0x1800208cc`
- end: `0x180020a95`
- name: `?InitCallEnvironment@LB_ARBITRATOR@@AEAAJXZ`
- size: `457`
- prototype: `__int64 __fastcall(LB_ARBITRATOR *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020c3c`

## callees

- `0x18001fbdc`
- `0x1800208cc`
- `0x180024640`

## import_xrefs

- `ntdll!_itow_s` at `0x1800209a1`
- `ntdll!_itow_s` at `0x1800209a1`
- `KERNEL32!CreateEventW` at `0x18002095c`
- `KERNEL32!CreateEventW` at `0x18002095c`
- `RPCRT4!I_RpcFree` at `0x180020a59`
- `RPCRT4!I_RpcFree` at `0x180020a59`
- `RPCRT4!RpcStringFreeW` at `0x1800209f7`
- `RPCRT4!RpcStringFreeW` at `0x1800209f7`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180020a4e`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180020a4e`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800209d0`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800209d0`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800209ea`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800209ea`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18002093d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18002093d`

## pseudocode

```c
__int64 __fastcall LB_ARBITRATOR::InitCallEnvironment(LB_ARBITRATOR *this)
{
  unsigned int v1; // esi
  __int64 v3; // r14
  __int64 v4; // rcx
  unsigned __int16 *v5; // r9
  RPC_STATUS v6; // ebx
  unsigned __int16 *SPN; // rbp
  RPC_STATUS v8; // ebx
  RPC_WSTR String; // [rsp+40h] [rbp-68h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+48h] [rbp-60h] BYREF
  wchar_t Buffer[8]; // [rsp+58h] [rbp-50h] BYREF

  SecurityQOS.Version = 1;
  String = 0;
  v1 = 0;
  *(_QWORD *)&SecurityQOS.Capabilities = 1;
  SecurityQOS.ImpersonationType = 2;
  while ( v1 < *((_DWORD *)this + 12) )
  {
    v3 = 184LL * v1;
    *(_QWORD *)(*((_QWORD *)this + 3) + v3 + 168) = this;
    RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(v3 + *((_QWORD *)this + 3) + 8LL), 0x70u);
    *(_DWORD *)(*((_QWORD *)this + 3) + v3 + 52) = 1;
    *(_QWORD *)(*((_QWORD *)this + 3) + v3 + 56) = CreateEventW(0, 1, 0, 0);
    if ( !*(_QWORD *)(*((_QWORD *)this + 3) + v3 + 56) )
      return 14;
    v4 = *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * v1);
    if ( *(_WORD *)(v4 + 34) )
    {
      _itow_s(*(unsigned __int16 *)(v4 + 34), Buffer, 6u, 10);
      v5 = Buffer;
    }
    else
    {
      v5 = 0;
    }
    if ( RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncacn_ip_tcp",
           *(RPC_WSTR *)(*(_QWORD *)(*((_QWORD *)this + 7) + 8LL * v1) + 24LL),
           v5,
           0,
           &String) )
    {
      return 14;
    }
    v6 = RpcBindingFromStringBindingW(String, (RPC_BINDING_HANDLE *)(v3 + *((_QWORD *)this + 3)));
    RpcStringFreeW(&String);
    if ( v6 )
    {
      *(_QWORD *)(v3 + *((_QWORD *)this + 3)) = 0;
      return 14;
    }
    if ( !LODWORD(g_pConfigurationManager[1].LockSemaphore) )
    {
      SPN = CreateSPN(*(unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 7) + 8LL * v1) + 24LL));
      if ( !SPN )
        return 14;
      v8 = RpcBindingSetAuthInfoExW(
             *(RPC_BINDING_HANDLE *)(*((_QWORD *)this + 3) + 184LL * v1),
             SPN,
             6u,
             9u,
             0,
             0,
             &SecurityQOS);
      I_RpcFree(SPN);
      if ( v8 )
        return 14;
    }
    ++v1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800208cc  push    rbx
0x1800208ce  push    rbp
0x1800208cf  push    rsi
0x1800208d0  push    rdi
0x1800208d1  push    r14
0x1800208d3  push    r15
0x1800208d5  sub     rsp, 78h
0x1800208d9  mov     rax, cs:__security_cookie
0x1800208e0  xor     rax, rsp
0x1800208e3  mov     [rsp+0A8h+var_40], rax
0x1800208e8  xor     r15d, r15d
0x1800208eb  mov     [rsp+0A8h+var_60.Version], 1
0x1800208f3  mov     [rsp+0A8h+String], r15
0x1800208f8  mov     esi, r15d
0x1800208fb  mov     rdi, rcx
0x1800208fe  mov     qword ptr [rsp+0A8h+var_60.Capabilities], 1
0x180020907  mov     [rsp+0A8h+var_60.ImpersonationType], 2
0x18002090f  cmp     esi, [rdi+30h]
0x180020912  jnb     loc_180020A79
0x180020918  mov     rax, [rdi+18h]
0x18002091c  mov     edx, 70h ; 'p'; Size
0x180020921  mov     ebp, esi
0x180020923  imul    r14, rbp, 0B8h
0x18002092a  mov     [rax+r14+0A8h], rdi
0x180020932  mov     rcx, [rdi+18h]
0x180020936  add     rcx, 8
0x18002093a  add     rcx, r14; pAsync
0x18002093d  call    cs:__imp_RpcAsyncInitializeHandle
0x180020943  mov     rax, [rdi+18h]
0x180020947  xor     r9d, r9d; lpName
0x18002094a  xor     r8d, r8d; bInitialState
0x18002094d  xor     ecx, ecx; lpEventAttributes
0x18002094f  lea     edx, [r9+1]; bManualReset
0x180020953  mov     dword ptr [rax+r14+34h], 1
0x18002095c  call    cs:__imp_CreateEventW
0x180020962  mov     rcx, [rdi+18h]
0x180020966  mov     [rcx+r14+38h], rax
0x18002096b  mov     rax, [rdi+18h]
0x18002096f  cmp     [rax+r14+38h], r15
0x180020974  jz      loc_180020A72
0x18002097a  mov     rax, [rdi+38h]
0x18002097e  mov     rcx, [rax+rbp*8]
0x180020982  cmp     [rcx+22h], r15w
0x180020987  jnz     short loc_18002098E
0x180020989  mov     r9, r15
0x18002098c  jmp     short loc_1800209AC
0x18002098e  movzx   ecx, word ptr [rcx+22h]; Value
0x180020992  lea     rdx, [rsp+0A8h+Buffer]; Buffer
0x180020997  mov     r9d, 0Ah; Radix
0x18002099d  lea     r8d, [r9-4]; BufferCount
0x1800209a1  call    cs:__imp__itow_s
0x1800209a7  lea     r9, [rsp+0A8h+Buffer]; Endpoint
0x1800209ac  mov     rax, [rdi+38h]
0x1800209b0  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x1800209b7  xor     ecx, ecx; ObjUuid
0x1800209b9  mov     r8, [rax+rbp*8]
0x1800209bd  lea     rax, [rsp+0A8h+String]
0x1800209c2  mov     [rsp+0A8h+StringBinding], rax; StringBinding
0x1800209c7  mov     [rsp+0A8h+Options], r15; Options
0x1800209cc  mov     r8, [r8+18h]; NetworkAddr
0x1800209d0  call    cs:__imp_RpcStringBindingComposeW
0x1800209d6  test    eax, eax
0x1800209d8  jnz     loc_180020A72
0x1800209de  mov     rdx, [rdi+18h]
0x1800209e2  mov     rcx, [rsp+0A8h+String]; StringBinding
0x1800209e7  add     rdx, r14; Binding
0x1800209ea  call    cs:__imp_RpcBindingFromStringBindingW
0x1800209f0  lea     rcx, [rsp+0A8h+String]; String
0x1800209f5  mov     ebx, eax
0x1800209f7  call    cs:__imp_RpcStringFreeW
0x1800209fd  test    ebx, ebx
0x1800209ff  jnz     short loc_180020A6A
0x180020a01  mov     rax, cs:?g_pConfigurationManager@@3PEAVLB_CONFIGURATION_MANAGER@@EA; LB_CONFIGURATION_MANAGER * g_pConfigurationManager
0x180020a08  cmp     [rax+40h], r15d
0x180020a0c  jnz     short loc_180020A63
0x180020a0e  mov     rax, [rdi+38h]
0x180020a12  mov     rcx, [rax+rbp*8]
0x180020a16  mov     rcx, [rcx+18h]; Src
0x180020a1a  call    ?CreateSPN@@YAPEAGPEAG@Z; CreateSPN(ushort *)
0x180020a1f  mov     rbp, rax
0x180020a22  test    rax, rax
0x180020a25  jz      short loc_180020A72
0x180020a27  mov     rcx, [rdi+18h]
0x180020a2b  lea     rax, [rsp+0A8h+var_60]
0x180020a30  mov     [rsp+0A8h+SecurityQOS], rax; SecurityQOS
0x180020a35  lea     r9d, [rbx+9]; AuthnSvc
0x180020a39  mov     dword ptr [rsp+0A8h+StringBinding], r15d; AuthzSvc
0x180020a3e  lea     r8d, [rbx+6]; AuthnLevel
0x180020a42  mov     rdx, rbp; ServerPrincName
0x180020a45  mov     [rsp+0A8h+Options], r15; AuthIdentity
0x180020a4a  mov     rcx, [rcx+r14]; Binding
0x180020a4e  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180020a54  mov     rcx, rbp; Object
0x180020a57  mov     ebx, eax
0x180020a59  call    cs:__imp_I_RpcFree
0x180020a5f  test    ebx, ebx
0x180020a61  jnz     short loc_180020A72
0x180020a63  inc     esi
0x180020a65  jmp     loc_18002090F
0x180020a6a  mov     rax, [rdi+18h]
0x180020a6e  mov     [r14+rax], r15
0x180020a72  mov     eax, 0Eh
0x180020a77  jmp     short loc_180020A7B
0x180020a79  xor     eax, eax
0x180020a7b  mov     rcx, [rsp+0A8h+var_40]
0x180020a80  xor     rcx, rsp; StackCookie
0x180020a83  call    __security_check_cookie
0x180020a88  add     rsp, 78h
0x180020a8c  pop     r15
0x180020a8e  pop     r14
0x180020a90  pop     rdi
0x180020a91  pop     rsi
0x180020a92  pop     rbp
0x180020a93  pop     rbx
0x180020a94  retn
```
