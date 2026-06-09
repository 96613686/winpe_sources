# GetBindingHandleForLocalService

- ea: `0x14001989c`
- end: `0x140019a62`
- name: `GetBindingHandleForLocalService`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001ae18`

## callees

- `0x14001989c`
- `0x14001c340`
- `0x14001c38c`
- `0x140021b00`
- `0x140022cec`
- `0x14002b9fc`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x14001994b`
- `RPCRT4!RpcBindingFree` at `0x14001994b`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400198f3`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400198f3`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140019977`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140019977`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140019a10`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140019a10`
- `RPCRT4!RpcStringFreeW` at `0x140019983`
- `RPCRT4!RpcStringFreeW` at `0x140019983`
- `RPCRT4!RpcBindingSetOption` at `0x140019a27`
- `RPCRT4!RpcBindingSetOption` at `0x140019a27`

## pseudocode

```c
__int64 __fastcall GetBindingHandleForLocalService(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  RPC_BINDING_HANDLE hBinding; // [rsp+40h] [rbp-30h] BYREF
  RPC_WSTR StringBinding; // [rsp+48h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-20h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+58h] [rbp-18h] BYREF

  StringBinding = 0;
  hBinding = 0;
  v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"eventlog", 0, &StringBinding);
  v4 = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, v2);
    }
  }
  else
  {
    Binding = hBinding;
    hBinding = 0;
    tlx::handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0_::operator()(v3, &Binding);
    v4 = RpcBindingFromStringBindingW(StringBinding, &hBinding);
    RpcStringFreeW(&StringBinding);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, v4);
      }
    }
    else
    {
      *(_QWORD *)&SecurityQOS.Version = 1;
      SecurityQOS.IdentityTracking = 1;
      SecurityQOS.ImpersonationType = 3;
      v4 = RpcBindingSetAuthInfoExW(hBinding, 0, 6u, 0xAu, 0, 0xFFFFFFFF, &SecurityQOS);
      if ( !v4 )
      {
        RpcBindingSetOption(hBinding, 9u, 1u);
        tlx::unique_any_tlx::handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0___::swap(a1, &hBinding);
      }
    }
    tlx::unique_any_tlx::handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0___::_unique_any_tlx::handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0___(&hBinding);
  }
  return v4;
}

```

## disassembly

```asm
0x14001989c  mov     r11, rsp
0x14001989f  mov     [r11+10h], rbx
0x1400198a3  mov     [r11+18h], rdi
0x1400198a7  push    rbp
0x1400198a8  mov     rbp, rsp
0x1400198ab  sub     rsp, 70h
0x1400198af  mov     rax, cs:__security_cookie
0x1400198b6  xor     rax, rsp
0x1400198b9  mov     [rbp+var_8], rax
0x1400198bd  lea     rax, [rbp+StringBinding]
0x1400198c1  mov     [rbp+StringBinding], 0
0x1400198c9  mov     rdi, rcx
0x1400198cc  mov     [r11-50h], rax
0x1400198d0  lea     r9, Endpoint; "eventlog"
0x1400198d7  mov     qword ptr [r11-58h], 0
0x1400198df  xor     r8d, r8d; NetworkAddr
0x1400198e2  mov     [rbp+hBinding], 0
0x1400198ea  lea     rdx, ProtSeq; "ncalrpc"
0x1400198f1  xor     ecx, ecx; ObjUuid
0x1400198f3  call    cs:__imp_RpcStringBindingComposeW
0x1400198f9  mov     ebx, eax
0x1400198fb  test    eax, eax
0x1400198fd  jz      short loc_140019956
0x1400198ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140019906  lea     rdx, WPP_GLOBAL_Control
0x14001990d  cmp     rcx, rdx
0x140019910  jz      short loc_140019936
0x140019912  test    byte ptr [rcx+1Ch], 4
0x140019916  jz      short loc_140019936
0x140019918  cmp     byte ptr [rcx+19h], 2
0x14001991c  jb      short loc_140019936
0x14001991e  mov     rcx, [rcx+10h]
0x140019922  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140019929  mov     edx, 12h
0x14001992e  mov     r9d, eax
0x140019931  call    WPP_SF_d
0x140019936  mov     rax, [rbp+hBinding]
0x14001993a  test    rax, rax
0x14001993d  jz      loc_140019A42
0x140019943  lea     rcx, [rbp+Binding]; Binding
0x140019947  mov     [rbp+Binding], rax
0x14001994b  call    cs:__imp_RpcBindingFree
0x140019951  jmp     loc_140019A42
0x140019956  mov     rax, [rbp+hBinding]
0x14001995a  lea     rdx, [rbp+Binding]
0x14001995e  mov     [rbp+Binding], rax
0x140019962  mov     [rbp+hBinding], 0
0x14001996a  call    tlx__handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0___operator__
0x14001996f  mov     rcx, [rbp+StringBinding]; StringBinding
0x140019973  lea     rdx, [rbp+hBinding]; Binding
0x140019977  call    cs:__imp_RpcBindingFromStringBindingW
0x14001997d  lea     rcx, [rbp+StringBinding]; String
0x140019981  mov     ebx, eax
0x140019983  call    cs:__imp_RpcStringFreeW
0x140019989  test    ebx, ebx
0x14001998b  jz      short loc_1400199D2
0x14001998d  mov     rcx, cs:WPP_GLOBAL_Control
0x140019994  lea     rdx, WPP_GLOBAL_Control
0x14001999b  cmp     rcx, rdx
0x14001999e  jz      loc_140019A39
0x1400199a4  test    byte ptr [rcx+1Ch], 4
0x1400199a8  jz      loc_140019A39
0x1400199ae  cmp     byte ptr [rcx+19h], 2
0x1400199b2  jb      loc_140019A39
0x1400199b8  mov     rcx, [rcx+10h]
0x1400199bc  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x1400199c3  mov     edx, 13h
0x1400199c8  mov     r9d, ebx
0x1400199cb  call    WPP_SF_d
0x1400199d0  jmp     short loc_140019A39
0x1400199d2  mov     rcx, [rbp+hBinding]; Binding
0x1400199d6  lea     rax, [rbp+var_18]
0x1400199da  xor     edx, edx; ServerPrincName
0x1400199dc  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x1400199e1  mov     [rsp+70h+AuthzSvc], 0FFFFFFFFh; AuthzSvc
0x1400199e9  mov     qword ptr [rbp+var_18.Version], 1
0x1400199f1  mov     [rbp+var_18.IdentityTracking], 1
0x1400199f8  lea     r9d, [rdx+0Ah]; AuthnSvc
0x1400199fc  mov     [rbp+var_18.ImpersonationType], 3
0x140019a03  lea     r8d, [rdx+6]; AuthnLevel
0x140019a07  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x140019a10  call    cs:__imp_RpcBindingSetAuthInfoExW
0x140019a16  mov     ebx, eax
0x140019a18  test    eax, eax
0x140019a1a  jnz     short loc_140019A39
0x140019a1c  mov     rcx, [rbp+hBinding]; hBinding
0x140019a20  lea     edx, [rax+9]; option
0x140019a23  lea     r8d, [rax+1]; optionValue
0x140019a27  call    cs:__imp_RpcBindingSetOption
0x140019a2d  lea     rdx, [rbp+hBinding]
0x140019a31  mov     rcx, rdi
0x140019a34  call    tlx__unique_any_tlx__handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0_____swap
0x140019a39  lea     rcx, [rbp+hBinding]
0x140019a3d  call    tlx__unique_any_tlx__handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0______unique_any_tlx__handle_traits_void___void____cdecl___void_____MyRpcBindingFree_0___
0x140019a42  mov     eax, ebx
0x140019a44  mov     rcx, [rbp+var_8]
0x140019a48  xor     rcx, rsp; StackCookie
0x140019a4b  call    __security_check_cookie
0x140019a50  lea     r11, [rsp+70h+var_s0]
0x140019a55  mov     rbx, [r11+18h]
0x140019a59  mov     rdi, [r11+20h]
0x140019a5d  mov     rsp, r11
0x140019a60  pop     rbp
0x140019a61  retn
```
