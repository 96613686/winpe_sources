# TsgQecSecurityCallback(void * *,void *)

- ea: `0x1800040f0`
- end: `0x18000419c`
- name: `?TsgQecSecurityCallback@@YAJPEAPEAXPEAX@Z`
- size: `172`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002e64`
- `0x1800040f0`
- `0x180005518`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180004185`
- `RPCRT4!RpcRevertToSelf` at `0x180004185`
- `RPCRT4!RpcImpersonateClient` at `0x1800040fb`
- `RPCRT4!RpcImpersonateClient` at `0x1800040fb`

## string_xrefs

- `0x180004128`: `RpcImpersonateClient`
- `0x180004170`: `CheckForLeastRequiredSecurity`

## pseudocode

```c
__int64 __fastcall TsgQecSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  RPC_STATUS v3; // eax
  int v4; // r8d
  unsigned int v5; // eax
  int v6; // r8d
  unsigned int v7; // ebx

  v3 = RpcImpersonateClient(0);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v4, (unsigned int)L"RpcImpersonateClient", v3);
    }
    return 5;
  }
  v5 = CheckForLeastRequiredSecurity(Context);
  v7 = v5;
  if ( v5
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v6, (unsigned int)L"CheckForLeastRequiredSecurity", v5);
  }
  RpcRevertToSelf();
  if ( v7 )
    return 5;
  return v7;
}

```

## disassembly

```asm
0x1800040f0  push    rbx
0x1800040f2  sub     rsp, 30h
0x1800040f6  xor     ecx, ecx; BindingHandle
0x1800040f8  mov     rbx, rdx
0x1800040fb  call    cs:__imp_RpcImpersonateClient
0x180004101  test    eax, eax
0x180004103  jz      short loc_18000413F
0x180004105  mov     rcx, cs:WPP_GLOBAL_Control
0x18000410c  lea     rdx, WPP_GLOBAL_Control
0x180004113  cmp     rcx, rdx
0x180004116  jz      short loc_18000418F
0x180004118  test    byte ptr [rcx+1Ch], 8
0x18000411c  jz      short loc_18000418F
0x18000411e  cmp     byte ptr [rcx+19h], 2
0x180004122  jb      short loc_18000418F
0x180004124  mov     rcx, [rcx+10h]
0x180004128  lea     r9, aRpcimpersonate; "RpcImpersonateClient"
0x18000412f  mov     edx, 35h ; '5'
0x180004134  mov     [rsp+38h+var_18], eax
0x180004138  call    WPP_SF_SD
0x18000413d  jmp     short loc_18000418F
0x18000413f  mov     rcx, rbx; ClientBinding
0x180004142  call    ?CheckForLeastRequiredSecurity@@YAJPEAX@Z; CheckForLeastRequiredSecurity(void *)
0x180004147  mov     ebx, eax
0x180004149  test    eax, eax
0x18000414b  jz      short loc_180004185
0x18000414d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004154  lea     rdx, WPP_GLOBAL_Control
0x18000415b  cmp     rcx, rdx
0x18000415e  jz      short loc_180004185
0x180004160  test    byte ptr [rcx+1Ch], 8
0x180004164  jz      short loc_180004185
0x180004166  cmp     byte ptr [rcx+19h], 2
0x18000416a  jb      short loc_180004185
0x18000416c  mov     rcx, [rcx+10h]
0x180004170  lea     r9, aCheckforleastr; "CheckForLeastRequiredSecurity"
0x180004177  mov     edx, 36h ; '6'
0x18000417c  mov     [rsp+38h+var_18], eax
0x180004180  call    WPP_SF_SD
0x180004185  call    cs:__imp_RpcRevertToSelf
0x18000418b  test    ebx, ebx
0x18000418d  jz      short loc_180004194
0x18000418f  mov     ebx, 5
0x180004194  mov     eax, ebx
0x180004196  add     rsp, 30h
0x18000419a  pop     rbx
0x18000419b  retn
```
