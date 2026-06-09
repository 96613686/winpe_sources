# StartupRpc(void)

- ea: `0x180022678`
- end: `0x1800228cb`
- name: `?StartupRpc@@YAJXZ`
- size: `595`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d9e0`

## callees

- `0x180008e48`
- `0x180022678`

## import_xrefs

- `RPCRT4!RpcServerUseProtseqW` at `0x180022695`
- `RPCRT4!RpcServerUseProtseqW` at `0x180022695`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800226ff`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800226ff`
- `RPCRT4!RpcEpRegisterW` at `0x1800227fc`
- `RPCRT4!RpcEpRegisterW` at `0x1800227fc`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180022739`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180022739`
- `RPCRT4!RpcBindingVectorFree` at `0x180022809`
- `RPCRT4!RpcBindingVectorFree` at `0x180022809`
- `RPCRT4!RpcServerListen` at `0x18002283c`
- `RPCRT4!RpcServerListen` at `0x18002283c`
- `RPCRT4!RpcServerInqBindings` at `0x1800227b6`
- `RPCRT4!RpcServerInqBindings` at `0x1800227b6`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180022778`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180022778`
- `RPCRT4!RpcStringFreeW` at `0x18002288d`
- `RPCRT4!RpcStringFreeW` at `0x18002288d`

## string_xrefs

- `0x1800227eb`: `Security Center`

## pseudocode

```c
__int64 StartupRpc(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  CThirdPartyManager *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r9
  RPC_WSTR PrincName; // [rsp+40h] [rbp+8h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+48h] [rbp+10h] BYREF

  v0 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0);
  PrincName = 0;
  v1 = v0;
  if ( !v0 )
  {
    v0 = RpcServerRegisterIfEx(qword_180043120, 0, 0, 0x20u, 0x4D2u, 0);
    v1 = v0;
    if ( v0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v3 = 115;
        goto LABEL_31;
      }
    }
    else
    {
      v0 = RpcServerInqDefaultPrincNameW(9u, &PrincName);
      v1 = v0;
      if ( v0 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v3 = 116;
          goto LABEL_31;
        }
      }
      else
      {
        v0 = RpcServerRegisterAuthInfoW(PrincName, 9u, 0, 0);
        v1 = v0;
        if ( v0 )
        {
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v3 = 117;
            goto LABEL_31;
          }
        }
        else
        {
          BindingVector = 0;
          v0 = RpcServerInqBindings(&BindingVector);
          v1 = v0;
          if ( v0 )
          {
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v3 = 118;
              goto LABEL_31;
            }
          }
          else
          {
            v1 = RpcEpRegisterW(qword_180043120, BindingVector, 0, (RPC_WSTR)L"Security Center");
            RpcBindingVectorFree(&BindingVector);
            if ( v1 )
            {
              v2 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v3 = 119;
                v4 = v1;
LABEL_32:
                WPP_SF_d(*((_QWORD *)v2 + 2), v3, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v4);
                goto LABEL_33;
              }
            }
            else
            {
              v0 = RpcServerListen(1u, 0x4D2u, 1u);
              v1 = v0;
              if ( !v0 )
              {
LABEL_33:
                v2 = WPP_GLOBAL_Control;
                goto LABEL_34;
              }
              v2 = WPP_GLOBAL_Control;
              if ( v0 == 1713 )
              {
                v1 = 0;
                goto LABEL_34;
              }
              if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v3 = 120;
                goto LABEL_31;
              }
            }
          }
        }
      }
    }
LABEL_34:
    if ( PrincName )
    {
      RpcStringFreeW(&PrincName);
      v2 = WPP_GLOBAL_Control;
    }
    goto LABEL_36;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v3 = 113;
LABEL_31:
    v4 = v0;
    goto LABEL_32;
  }
LABEL_36:
  if ( v2 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v2 + 2), 121, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180022678  mov     [rsp+arg_10], rbx
0x18002267d  mov     [rsp+arg_18], rbp
0x180022682  push    rsi
0x180022683  sub     rsp, 30h
0x180022687  xor     r8d, r8d; SecurityDescriptor
0x18002268a  lea     rcx, Protseq; "ncalrpc"
0x180022691  lea     edx, [r8+0Ah]; MaxCalls
0x180022695  call    cs:__imp_RpcServerUseProtseqW
0x18002269b  mov     [rsp+38h+PrincName], 0
0x1800226a4  lea     rbp, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800226ab  lea     rsi, WPP_GLOBAL_Control
0x1800226b2  mov     ebx, eax
0x1800226b4  test    eax, eax
0x1800226b6  jz      short loc_1800226DC
0x1800226b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226bf  cmp     rcx, rsi
0x1800226c2  jz      loc_1800228B9
0x1800226c8  test    byte ptr [rcx+1Ch], 1
0x1800226cc  jz      loc_18002289A
0x1800226d2  mov     edx, 71h ; 'q'
0x1800226d7  jmp     loc_18002286A
0x1800226dc  mov     [rsp+38h+IfCallback], 0; IfCallback
0x1800226e5  lea     rcx, qword_180043120; IfSpec
0x1800226ec  mov     r9d, 20h ; ' '; Flags
0x1800226f2  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x1800226fa  xor     r8d, r8d; MgrEpv
0x1800226fd  xor     edx, edx; MgrTypeUuid
0x1800226ff  call    cs:__imp_RpcServerRegisterIfEx
0x180022705  mov     ebx, eax
0x180022707  test    eax, eax
0x180022709  jz      short loc_18002272F
0x18002270b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022712  cmp     rcx, rsi
0x180022715  jz      loc_180022880
0x18002271b  test    byte ptr [rcx+1Ch], 1
0x18002271f  jz      loc_180022880
0x180022725  mov     edx, 73h ; 's'
0x18002272a  jmp     loc_18002286A
0x18002272f  lea     rdx, [rsp+38h+PrincName]; PrincName
0x180022734  mov     ecx, 9; AuthnSvc
0x180022739  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x18002273f  mov     ebx, eax
0x180022741  test    eax, eax
0x180022743  jz      short loc_180022769
0x180022745  mov     rcx, cs:WPP_GLOBAL_Control
0x18002274c  cmp     rcx, rsi
0x18002274f  jz      loc_180022880
0x180022755  test    byte ptr [rcx+1Ch], 1
0x180022759  jz      loc_180022880
0x18002275f  mov     edx, 74h ; 't'
0x180022764  jmp     loc_18002286A
0x180022769  mov     rcx, [rsp+38h+PrincName]; ServerPrincName
0x18002276e  xor     r9d, r9d; Arg
0x180022771  xor     r8d, r8d; GetKeyFn
0x180022774  lea     edx, [r9+9]; AuthnSvc
0x180022778  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18002277e  mov     ebx, eax
0x180022780  test    eax, eax
0x180022782  jz      short loc_1800227A8
0x180022784  mov     rcx, cs:WPP_GLOBAL_Control
0x18002278b  cmp     rcx, rsi
0x18002278e  jz      loc_180022880
0x180022794  test    byte ptr [rcx+1Ch], 1
0x180022798  jz      loc_180022880
0x18002279e  mov     edx, 75h ; 'u'
0x1800227a3  jmp     loc_18002286A
0x1800227a8  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x1800227ad  mov     [rsp+38h+BindingVector], 0
0x1800227b6  call    cs:__imp_RpcServerInqBindings
0x1800227bc  mov     ebx, eax
0x1800227be  test    eax, eax
0x1800227c0  jz      short loc_1800227E6
0x1800227c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227c9  cmp     rcx, rsi
0x1800227cc  jz      loc_180022880
0x1800227d2  test    byte ptr [rcx+1Ch], 1
0x1800227d6  jz      loc_180022880
0x1800227dc  mov     edx, 76h ; 'v'
0x1800227e1  jmp     loc_18002286A
0x1800227e6  mov     rdx, [rsp+38h+BindingVector]; BindingVector
0x1800227eb  lea     r9, Annotation; "Security Center"
0x1800227f2  xor     r8d, r8d; UuidVector
0x1800227f5  lea     rcx, qword_180043120; IfSpec
0x1800227fc  call    cs:__imp_RpcEpRegisterW
0x180022802  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x180022807  mov     ebx, eax
0x180022809  call    cs:__imp_RpcBindingVectorFree
0x18002280f  test    ebx, ebx
0x180022811  jz      short loc_18002282F
0x180022813  mov     rcx, cs:WPP_GLOBAL_Control
0x18002281a  cmp     rcx, rsi
0x18002281d  jz      short loc_180022880
0x18002281f  test    byte ptr [rcx+1Ch], 1
0x180022823  jz      short loc_180022880
0x180022825  mov     edx, 77h ; 'w'
0x18002282a  mov     r9d, ebx
0x18002282d  jmp     short loc_18002286D
0x18002282f  mov     ecx, 1; MinimumCallThreads
0x180022834  mov     edx, 4D2h; MaxCalls
0x180022839  mov     r8d, ecx; DontWait
0x18002283c  call    cs:__imp_RpcServerListen
0x180022842  mov     ebx, eax
0x180022844  test    eax, eax
0x180022846  jz      short loc_180022879
0x180022848  mov     rcx, cs:WPP_GLOBAL_Control
0x18002284f  cmp     eax, 6B1h
0x180022854  jnz     short loc_18002285A
0x180022856  xor     ebx, ebx
0x180022858  jmp     short loc_180022880
0x18002285a  cmp     rcx, rsi
0x18002285d  jz      short loc_180022880
0x18002285f  test    byte ptr [rcx+1Ch], 1
0x180022863  jz      short loc_180022880
0x180022865  mov     edx, 78h ; 'x'
0x18002286a  mov     r9d, eax
0x18002286d  mov     rcx, [rcx+10h]
0x180022871  mov     r8, rbp
0x180022874  call    WPP_SF_d
0x180022879  mov     rcx, cs:WPP_GLOBAL_Control
0x180022880  cmp     [rsp+38h+PrincName], 0
0x180022886  jz      short loc_18002289A
0x180022888  lea     rcx, [rsp+38h+PrincName]; String
0x18002288d  call    cs:__imp_RpcStringFreeW
0x180022893  mov     rcx, cs:WPP_GLOBAL_Control
0x18002289a  cmp     rcx, rsi
0x18002289d  jz      short loc_1800228B9
0x18002289f  test    byte ptr [rcx+1Ch], 8
0x1800228a3  jz      short loc_1800228B9
0x1800228a5  mov     rcx, [rcx+10h]
0x1800228a9  mov     edx, 79h ; 'y'
0x1800228ae  mov     r9d, ebx
0x1800228b1  mov     r8, rbp
0x1800228b4  call    WPP_SF_d
0x1800228b9  mov     rbp, [rsp+38h+arg_18]
0x1800228be  mov     eax, ebx
0x1800228c0  mov     rbx, [rsp+38h+arg_10]
0x1800228c5  add     rsp, 30h
0x1800228c9  pop     rsi
0x1800228ca  retn
```
