# CEnfRpcHelper::IsCallerAdminOrSystem(int)

- ea: `0x180099430`
- end: `0x180099516`
- name: `?IsCallerAdminOrSystem@CEnfRpcHelper@@UEAAJH@Z`
- size: `230`
- prototype: `__int64 __fastcall(CEnfRpcHelper *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a210`
- `0x180099430`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800994ea`
- `RPCRT4!RpcRevertToSelf` at `0x1800994ea`
- `RPCRT4!RpcImpersonateClient` at `0x180099453`
- `RPCRT4!RpcImpersonateClient` at `0x180099453`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180099489`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800994c9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180099489`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800994c9`

## string_xrefs

- `0x180099493`: `CEnfRpcHelper::IsCallerAdminOrSystem FAILED - Error in CheckTokenMembership`
- `0x1800994d3`: `CEnfRpcHelper::IsCallerAdminOrSystem FAILED - Error in CheckTokenMembership`
- `0x180099460`: `CEnfRpcHelper::IsCallerAdminOrSystem FAILED - Can not impersonate client: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180099430  mov     [rsp+arg_0], rbx
0x180099435  mov     [rsp+arg_8], rsi
0x18009943a  push    rdi
0x18009943b  sub     rsp, 20h
0x18009943f  mov     rdi, rcx
0x180099442  mov     [rsp+28h+IsMember], 0
0x18009944a  xor     ecx, ecx; BindingHandle
0x18009944c  mov     esi, edx
0x18009944e  mov     ebx, 0C000010Dh
0x180099453  call    cs:__imp_RpcImpersonateClient
0x180099459  test    eax, eax
0x18009945b  jz      short loc_180099476
0x18009945d  mov     r8d, eax
0x180099460  lea     rdx, aCenfrpchelperI; "CEnfRpcHelper::IsCallerAdminOrSystem FA"...
0x180099467  mov     ecx, 8; int
0x18009946c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180099471  jmp     loc_180099504
0x180099476  mov     rdx, [rdi+640h]; SidToCheck
0x18009947d  test    rdx, rdx
0x180099480  jz      short loc_1800994AA
0x180099482  lea     r8, [rsp+28h+IsMember]; IsMember
0x180099487  xor     ecx, ecx; TokenHandle
0x180099489  call    cs:__imp_CheckTokenMembership
0x18009948f  test    eax, eax
0x180099491  jnz     short loc_1800994AA
0x180099493  lea     rdx, aCenfrpchelperI_0; "CEnfRpcHelper::IsCallerAdminOrSystem FA"...
0x18009949a  lea     ecx, [rax+8]; int
0x18009949d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800994a2  xor     eax, eax
0x1800994a4  mov     [rsp+28h+IsMember], eax
0x1800994a8  jmp     short loc_1800994AE
0x1800994aa  mov     eax, [rsp+28h+IsMember]
0x1800994ae  test    eax, eax
0x1800994b0  jnz     short loc_1800994EA
0x1800994b2  test    esi, esi
0x1800994b4  jz      short loc_1800994EA
0x1800994b6  mov     rdx, [rdi+648h]; SidToCheck
0x1800994bd  test    rdx, rdx
0x1800994c0  jz      short loc_1800994EA
0x1800994c2  lea     r8, [rsp+28h+IsMember]; IsMember
0x1800994c7  xor     ecx, ecx; TokenHandle
0x1800994c9  call    cs:__imp_CheckTokenMembership
0x1800994cf  test    eax, eax
0x1800994d1  jnz     short loc_1800994EA
0x1800994d3  lea     rdx, aCenfrpchelperI_0; "CEnfRpcHelper::IsCallerAdminOrSystem FA"...
0x1800994da  lea     ecx, [rax+8]; int
0x1800994dd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800994e2  mov     [rsp+28h+IsMember], 0
0x1800994ea  call    cs:__imp_RpcRevertToSelf
0x1800994f0  test    eax, eax
0x1800994f2  jnz     short loc_180099504
0x1800994f4  mov     eax, [rsp+28h+IsMember]
0x1800994f8  neg     eax
0x1800994fa  sbb     ebx, ebx
0x1800994fc  not     ebx
0x1800994fe  and     ebx, 0C0000022h
0x180099504  mov     rsi, [rsp+28h+arg_8]
0x180099509  mov     eax, ebx
0x18009950b  mov     rbx, [rsp+28h+arg_0]
0x180099510  add     rsp, 20h
0x180099514  pop     rdi
0x180099515  retn
```
