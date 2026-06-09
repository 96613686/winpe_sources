# CEnfRpcHelper::IsCallerAdminOrSystem(int)

- ea: `0x18009d5a0`
- end: `0x18009d69f`
- name: `?IsCallerAdminOrSystem@CEnfRpcHelper@@UEAAJH@Z`
- size: `255`
- prototype: `__int64 __fastcall(CEnfRpcHelper *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009940`
- `0x18009d5a0`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18009d66c`
- `RPCRT4!RpcRevertToSelf` at `0x18009d66c`
- `RPCRT4!RpcImpersonateClient` at `0x18009d5c3`
- `RPCRT4!RpcImpersonateClient` at `0x18009d5c3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009d5ff`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009d645`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009d5ff`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18009d645`

## string_xrefs

- `0x18009d5d6`: `CEnfRpcHelper::IsCallerAdminOrSystem FAILED - Can not impersonate client: 0x%x`
- `0x18009d60f`: `CEnfRpcHelper::IsCallerAdminOrSystem FAILED - Error in CheckTokenMembership`
- `0x18009d655`: `CEnfRpcHelper::IsCallerAdminOrSystem FAILED - Error in CheckTokenMembership`

## pseudocode

```c
__int64 __fastcall CEnfRpcHelper::IsCallerAdminOrSystem(CEnfRpcHelper *this, int a2)
{
  unsigned int v4; // ebx
  RPC_STATUS v5; // eax
  void *v6; // rdx
  WINBOOL v7; // eax
  void *v8; // rdx
  WINBOOL IsMember; // [rsp+40h] [rbp+18h] BYREF

  IsMember = 0;
  v4 = -1073741555;
  v5 = RpcImpersonateClient(0);
  if ( v5 )
  {
    _DbgPrintMessage(8, "CEnfRpcHelper::IsCallerAdminOrSystem FAILED - Can not impersonate client: 0x%x", v5);
  }
  else
  {
    v6 = (void *)*((_QWORD *)this + 200);
    if ( !v6 || CheckTokenMembership(0, v6, &IsMember) )
    {
      v7 = IsMember;
    }
    else
    {
      _DbgPrintMessage(8, "CEnfRpcHelper::IsCallerAdminOrSystem FAILED - Error in CheckTokenMembership");
      v7 = 0;
      IsMember = 0;
    }
    if ( !v7 )
    {
      if ( a2 )
      {
        v8 = (void *)*((_QWORD *)this + 201);
        if ( v8 )
        {
          if ( !CheckTokenMembership(0, v8, &IsMember) )
          {
            _DbgPrintMessage(8, "CEnfRpcHelper::IsCallerAdminOrSystem FAILED - Error in CheckTokenMembership");
            IsMember = 0;
          }
        }
      }
    }
    if ( !RpcRevertToSelf() )
      return IsMember == 0 ? 0xC0000022 : 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18009d5a0  mov     [rsp+arg_0], rbx
0x18009d5a5  mov     [rsp+arg_8], rsi
0x18009d5aa  push    rdi
0x18009d5ab  sub     rsp, 20h
0x18009d5af  mov     rdi, rcx
0x18009d5b2  mov     [rsp+28h+IsMember], 0
0x18009d5ba  xor     ecx, ecx; BindingHandle
0x18009d5bc  mov     esi, edx
0x18009d5be  mov     ebx, 0C000010Dh
0x18009d5c3  call    cs:__imp_RpcImpersonateClient
0x18009d5ca  nop     dword ptr [rax+rax+00h]
0x18009d5cf  test    eax, eax
0x18009d5d1  jz      short loc_18009D5EC
0x18009d5d3  mov     r8d, eax
0x18009d5d6  lea     rdx, aCenfrpchelperI; "CEnfRpcHelper::IsCallerAdminOrSystem FA"...
0x18009d5dd  mov     ecx, 8; int
0x18009d5e2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009d5e7  jmp     loc_18009D68C
0x18009d5ec  mov     rdx, [rdi+640h]; SidToCheck
0x18009d5f3  test    rdx, rdx
0x18009d5f6  jz      short loc_18009D626
0x18009d5f8  lea     r8, [rsp+28h+IsMember]; IsMember
0x18009d5fd  xor     ecx, ecx; TokenHandle
0x18009d5ff  call    cs:__imp_CheckTokenMembership
0x18009d606  nop     dword ptr [rax+rax+00h]
0x18009d60b  test    eax, eax
0x18009d60d  jnz     short loc_18009D626
0x18009d60f  lea     rdx, aCenfrpchelperI_0; "CEnfRpcHelper::IsCallerAdminOrSystem FA"...
0x18009d616  lea     ecx, [rax+8]; int
0x18009d619  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009d61e  xor     eax, eax
0x18009d620  mov     [rsp+28h+IsMember], eax
0x18009d624  jmp     short loc_18009D62A
0x18009d626  mov     eax, [rsp+28h+IsMember]
0x18009d62a  test    eax, eax
0x18009d62c  jnz     short loc_18009D66C
0x18009d62e  test    esi, esi
0x18009d630  jz      short loc_18009D66C
0x18009d632  mov     rdx, [rdi+648h]; SidToCheck
0x18009d639  test    rdx, rdx
0x18009d63c  jz      short loc_18009D66C
0x18009d63e  lea     r8, [rsp+28h+IsMember]; IsMember
0x18009d643  xor     ecx, ecx; TokenHandle
0x18009d645  call    cs:__imp_CheckTokenMembership
0x18009d64c  nop     dword ptr [rax+rax+00h]
0x18009d651  test    eax, eax
0x18009d653  jnz     short loc_18009D66C
0x18009d655  lea     rdx, aCenfrpchelperI_0; "CEnfRpcHelper::IsCallerAdminOrSystem FA"...
0x18009d65c  lea     ecx, [rax+8]; int
0x18009d65f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009d664  mov     [rsp+28h+IsMember], 0
0x18009d66c  call    cs:__imp_RpcRevertToSelf
0x18009d673  nop     dword ptr [rax+rax+00h]
0x18009d678  test    eax, eax
0x18009d67a  jnz     short loc_18009D68C
0x18009d67c  mov     eax, [rsp+28h+IsMember]
0x18009d680  neg     eax
0x18009d682  sbb     ebx, ebx
0x18009d684  not     ebx
0x18009d686  and     ebx, 0C0000022h
0x18009d68c  mov     rsi, [rsp+28h+arg_8]
0x18009d691  mov     eax, ebx
0x18009d693  mov     rbx, [rsp+28h+arg_0]
0x18009d698  add     rsp, 20h
0x18009d69c  pop     rdi
0x18009d69d  retn
```
