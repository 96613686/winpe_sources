# IdSegStartSrv

- ea: `0x180013d18`
- end: `0x180013f74`
- name: `IdSegStartSrv`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015500`

## callees

- `0x180013d18`
- `0x180020dc0`
- `0x180020de8`

## import_xrefs

- `RPCRT4!RpcServerRegisterIfEx` at `0x180013d7b`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180013d7b`
- `RPCRT4!RpcEpRegisterW` at `0x180013df0`
- `RPCRT4!RpcEpRegisterW` at `0x180013df0`
- `RPCRT4!RpcServerUnregisterIf` at `0x180013f2a`
- `RPCRT4!RpcServerUnregisterIf` at `0x180013f2a`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180013d3d`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180013d3d`
- `RPCRT4!RpcBindingVectorFree` at `0x180013e75`
- `RPCRT4!RpcBindingVectorFree` at `0x180013f09`
- `RPCRT4!RpcBindingVectorFree` at `0x180013e75`
- `RPCRT4!RpcBindingVectorFree` at `0x180013f09`
- `RPCRT4!RpcServerInqBindings` at `0x180013d93`
- `RPCRT4!RpcServerInqBindings` at `0x180013d93`

## string_xrefs

- `0x180013ddf`: `IdSegSrv service`

## pseudocode

```c
__int64 IdSegStartSrv()
{
  RPC_STATUS v0; // eax
  unsigned int v1; // ebx
  char v2; // r14
  unsigned int v3; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  unsigned int v8; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+60h] [rbp+8h] BYREF

  BindingVector = 0;
  v0 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, 0, 0);
  v1 = 0;
  if ( v0 != 1740 )
    v1 = v0;
  if ( v1
    || (v1 = RpcServerRegisterIfEx(
               qword_180045000,
               0,
               0,
               0xA1u,
               0x4D2u,
               (RPC_IF_CALLBACK_FN *)IdSegSrvRpcSecurityCallback)) != 0 )
  {
    v2 = 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v5 = 16;
        v6 = v1;
        goto LABEL_27;
      }
      goto LABEL_28;
    }
    goto LABEL_32;
  }
  v2 = 1;
  v3 = RpcServerInqBindings(&BindingVector);
  v1 = v3;
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v5 = 17;
LABEL_10:
        v6 = v3;
LABEL_27:
        WPP_SF_d(v4[2], v5, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids, v6);
        v4 = WPP_GLOBAL_Control;
        goto LABEL_28;
      }
      goto LABEL_28;
    }
    goto LABEL_32;
  }
  v3 = RpcEpRegisterW(qword_180045000, BindingVector, 0, (RPC_WSTR)L"IdSegSrv service");
  v1 = v3;
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v5 = 18;
        goto LABEL_10;
      }
LABEL_28:
      if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x400) != 0 && *((_BYTE *)v4 + 25) )
        WPP_SF_d(v4[2], 20, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids, v1);
    }
LABEL_32:
    if ( BindingVector )
    {
      RpcBindingVectorFree(&BindingVector);
      BindingVector = 0;
    }
    if ( v2 )
    {
      v8 = RpcServerUnregisterIf(qword_180045000, 0, 1u);
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids, v8);
        }
      }
    }
    return v1;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids);
  }
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  dword_18005E440 = 1;
  return 0;
}

```

## disassembly

```asm
0x180013d18  push    rbx
0x180013d1a  push    rbp
0x180013d1b  push    r14
0x180013d1d  push    r15
0x180013d1f  sub     rsp, 38h
0x180013d23  xor     r9d, r9d; SecurityDescriptor
0x180013d26  mov     [rsp+58h+BindingVector], 0
0x180013d2f  xor     r8d, r8d; Endpoint
0x180013d32  lea     rcx, String2; "ncalrpc"
0x180013d39  lea     edx, [r9+0Ah]; MaxCalls
0x180013d3d  call    cs:__imp_RpcServerUseProtseqEpW
0x180013d43  xor     ebx, ebx
0x180013d45  cmp     eax, 6CCh
0x180013d4a  cmovnz  ebx, eax
0x180013d4d  test    ebx, ebx
0x180013d4f  jnz     loc_180013E8C
0x180013d55  lea     rax, IdSegSrvRpcSecurityCallback
0x180013d5c  mov     r9d, 0A1h; Flags
0x180013d62  mov     [rsp+58h+IfCallback], rax; IfCallback
0x180013d67  lea     rcx, qword_180045000; IfSpec
0x180013d6e  xor     r8d, r8d; MgrEpv
0x180013d71  mov     [rsp+58h+MaxCalls], 4D2h; MaxCalls
0x180013d79  xor     edx, edx; MgrTypeUuid
0x180013d7b  call    cs:__imp_RpcServerRegisterIfEx
0x180013d81  mov     ebx, eax
0x180013d83  test    eax, eax
0x180013d85  jnz     loc_180013E8C
0x180013d8b  lea     rcx, [rsp+58h+BindingVector]; BindingVector
0x180013d90  mov     r14b, 1
0x180013d93  call    cs:__imp_RpcServerInqBindings
0x180013d99  mov     ebx, eax
0x180013d9b  test    eax, eax
0x180013d9d  jz      short loc_180013DDA
0x180013d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013da6  lea     rbp, WPP_GLOBAL_Control
0x180013dad  cmp     rcx, rbp
0x180013db0  jz      loc_180013EFC
0x180013db6  test    dword ptr [rcx+1Ch], 400h
0x180013dbd  jz      loc_180013ED0
0x180013dc3  cmp     [rcx+19h], r14b
0x180013dc7  jb      loc_180013ED0
0x180013dcd  mov     edx, 11h
0x180013dd2  mov     r9d, eax
0x180013dd5  jmp     loc_180013EB9
0x180013dda  mov     rdx, [rsp+58h+BindingVector]; BindingVector
0x180013ddf  lea     r9, aIdsegsrvServic; "IdSegSrv service"
0x180013de6  xor     r8d, r8d; UuidVector
0x180013de9  lea     rcx, qword_180045000; IfSpec
0x180013df0  call    cs:__imp_RpcEpRegisterW
0x180013df6  mov     ebx, eax
0x180013df8  test    eax, eax
0x180013dfa  jz      short loc_180013E31
0x180013dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e03  lea     rbp, WPP_GLOBAL_Control
0x180013e0a  cmp     rcx, rbp
0x180013e0d  jz      loc_180013EFC
0x180013e13  test    dword ptr [rcx+1Ch], 400h
0x180013e1a  jz      loc_180013ED0
0x180013e20  cmp     [rcx+19h], r14b
0x180013e24  jb      loc_180013ED0
0x180013e2a  mov     edx, 12h
0x180013e2f  jmp     short loc_180013DD2
0x180013e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e38  lea     rbp, WPP_GLOBAL_Control
0x180013e3f  cmp     rcx, rbp
0x180013e42  jz      short loc_180013E68
0x180013e44  test    dword ptr [rcx+1Ch], 400h
0x180013e4b  jz      short loc_180013E68
0x180013e4d  cmp     byte ptr [rcx+19h], 2
0x180013e51  jb      short loc_180013E68
0x180013e53  mov     rcx, [rcx+10h]
0x180013e57  lea     r8, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids
0x180013e5e  mov     edx, 13h
0x180013e63  call    WPP_SF_
0x180013e68  cmp     [rsp+58h+BindingVector], 0
0x180013e6e  jz      short loc_180013E7B
0x180013e70  lea     rcx, [rsp+58h+BindingVector]; BindingVector
0x180013e75  call    cs:__imp_RpcBindingVectorFree
0x180013e7b  mov     cs:dword_18005E440, 1
0x180013e85  xor     eax, eax
0x180013e87  jmp     loc_180013F69
0x180013e8c  xor     r14b, r14b
0x180013e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e96  lea     rbp, WPP_GLOBAL_Control
0x180013e9d  cmp     rcx, rbp
0x180013ea0  jz      short loc_180013EFC
0x180013ea2  test    dword ptr [rcx+1Ch], 400h
0x180013ea9  jz      short loc_180013ED0
0x180013eab  cmp     byte ptr [rcx+19h], 1
0x180013eaf  jb      short loc_180013ED0
0x180013eb1  mov     edx, 10h
0x180013eb6  mov     r9d, ebx
0x180013eb9  mov     rcx, [rcx+10h]
0x180013ebd  lea     r8, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids
0x180013ec4  call    WPP_SF_d
0x180013ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ed0  cmp     rcx, rbp
0x180013ed3  jz      short loc_180013EFC
0x180013ed5  test    dword ptr [rcx+1Ch], 400h
0x180013edc  jz      short loc_180013EFC
0x180013ede  cmp     byte ptr [rcx+19h], 1
0x180013ee2  jb      short loc_180013EFC
0x180013ee4  mov     rcx, [rcx+10h]
0x180013ee8  lea     r8, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids
0x180013eef  mov     edx, 14h
0x180013ef4  mov     r9d, ebx
0x180013ef7  call    WPP_SF_d
0x180013efc  cmp     [rsp+58h+BindingVector], 0
0x180013f02  jz      short loc_180013F18
0x180013f04  lea     rcx, [rsp+58h+BindingVector]; BindingVector
0x180013f09  call    cs:__imp_RpcBindingVectorFree
0x180013f0f  mov     [rsp+58h+BindingVector], 0
0x180013f18  test    r14b, r14b
0x180013f1b  jz      short loc_180013F67
0x180013f1d  xor     edx, edx; MgrTypeUuid
0x180013f1f  lea     rcx, qword_180045000; IfSpec
0x180013f26  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x180013f2a  call    cs:__imp_RpcServerUnregisterIf
0x180013f30  test    eax, eax
0x180013f32  jz      short loc_180013F67
0x180013f34  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f3b  cmp     rcx, rbp
0x180013f3e  jz      short loc_180013F67
0x180013f40  test    dword ptr [rcx+1Ch], 400h
0x180013f47  jz      short loc_180013F67
0x180013f49  cmp     byte ptr [rcx+19h], 1
0x180013f4d  jb      short loc_180013F67
0x180013f4f  mov     rcx, [rcx+10h]
0x180013f53  lea     r8, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids
0x180013f5a  mov     edx, 15h
0x180013f5f  mov     r9d, eax
0x180013f62  call    WPP_SF_d
0x180013f67  mov     eax, ebx
0x180013f69  add     rsp, 38h
0x180013f6d  pop     r15
0x180013f6f  pop     r14
0x180013f71  pop     rbp
0x180013f72  pop     rbx
0x180013f73  retn
```
