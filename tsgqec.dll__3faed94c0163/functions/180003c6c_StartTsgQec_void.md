# StartTsgQec(void)

- ea: `0x180003c6c`
- end: `0x180003ef1`
- name: `?StartTsgQec@@YAKXZ`
- size: `645`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004970`

## callees

- `0x180003a04`
- `0x180003c6c`
- `0x180003ef8`
- `0x180005518`

## import_xrefs

- `RPCRT4!RpcServerRegisterIfEx` at `0x180003cf0`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180003cf0`
- `RPCRT4!RpcServerUseProtseqW` at `0x180003c86`
- `RPCRT4!RpcServerUseProtseqW` at `0x180003c86`
- `RPCRT4!RpcServerListen` at `0x180003e82`
- `RPCRT4!RpcServerListen` at `0x180003e82`
- `RPCRT4!RpcEpRegisterW` at `0x180003dec`
- `RPCRT4!RpcEpRegisterW` at `0x180003dec`
- `RPCRT4!RpcServerInqBindings` at `0x180003d8e`
- `RPCRT4!RpcServerInqBindings` at `0x180003d8e`

## string_xrefs

- `0x180003e6c`: `RegisterAuthServices`

## pseudocode

```c
__int64 StartTsgQec(void)
{
  RPC_STATUS v0; // eax
  int v1; // r8d
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  int v4; // edx
  const wchar_t *v5; // r9
  RPC_STATUS v6; // eax
  int v7; // r8d
  _QWORD *v8; // rcx
  int v9; // edx
  const wchar_t *v10; // r9
  RPC_STATUS v11; // eax
  int v12; // r8d

  v0 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 5u, 0);
  v2 = v0;
  if ( v0 != 1740 && v0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_17;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_13;
    v4 = 48;
    v5 = L"RpcServerUseProtseqEpEx for qec";
    goto LABEL_12;
  }
  v0 = RpcServerRegisterIfEx(qword_18000DE40, 0, 0, 0x29u, 5u, (RPC_IF_CALLBACK_FN *)TsgQecSecurityCallback);
  v2 = v0;
  if ( !v0 )
  {
    v6 = RpcServerInqBindings(&g_pQECBindingVector);
    v2 = v6;
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      v9 = 41;
      v10 = L"RpcServerInqBindings";
    }
    else
    {
      v6 = RpcEpRegisterW(qword_18000DE40, g_pQECBindingVector, 0, (RPC_WSTR)L"Terminal Server QEC");
      v2 = v6;
      if ( v6 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_18;
        }
        v9 = 42;
        v10 = L"RpcEpRegister";
      }
      else
      {
        v6 = RegisterAuthServices();
        v2 = v6;
        if ( !v6 )
        {
          v11 = RpcServerListen(1u, 5u, 1u);
          v2 = v11;
          if ( !v11 )
            return 0;
          if ( v11 != 1713 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, v12, (unsigned int)L"RpcServerListen", v11);
            }
            goto LABEL_19;
          }
          goto LABEL_18;
        }
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_18;
        }
        v9 = 43;
        v10 = L"RegisterAuthServices";
      }
    }
    WPP_SF_SD(v8[2], v9, v7, (_DWORD)v10, v6);
    goto LABEL_18;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_13:
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 && *((_BYTE *)v3 + 25) >= 2u )
        WPP_SF_SD(v3[2], 40, v1, (unsigned int)L"RegisterQecInterfaces", v2);
      goto LABEL_17;
    }
    v4 = 49;
    v5 = L"RpcServerRegisterIfEx for qec";
LABEL_12:
    WPP_SF_SD(v3[2], v4, v1, (_DWORD)v5, v0);
    v3 = WPP_GLOBAL_Control;
    goto LABEL_13;
  }
LABEL_17:
  if ( !v2 )
    return 0;
LABEL_18:
  if ( v2 == 1713 )
    return 0;
LABEL_19:
  StopTsgQec();
  return v2;
}

```

## disassembly

```asm
0x180003c6c  mov     [rsp+arg_0], rbx
0x180003c71  push    rdi
0x180003c72  sub     rsp, 30h
0x180003c76  xor     r8d, r8d; SecurityDescriptor
0x180003c79  lea     rcx, aNcalrpc; "ncalrpc"
0x180003c80  lea     edi, [r8+5]
0x180003c84  mov     edx, edi; MaxCalls
0x180003c86  call    cs:__imp_RpcServerUseProtseqW
0x180003c8c  mov     ebx, eax
0x180003c8e  cmp     eax, 6CCh
0x180003c93  jz      short loc_180003CCE
0x180003c95  test    eax, eax
0x180003c97  jz      short loc_180003CCE
0x180003c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ca0  lea     rdi, WPP_GLOBAL_Control
0x180003ca7  cmp     rcx, rdi
0x180003caa  jz      loc_180003D69
0x180003cb0  test    byte ptr [rcx+1Ch], 8
0x180003cb4  jz      loc_180003D3F
0x180003cba  cmp     byte ptr [rcx+19h], 2
0x180003cbe  jb      short loc_180003D3F
0x180003cc0  mov     edx, 30h ; '0'
0x180003cc5  lea     r9, aRpcserverusepr; "RpcServerUseProtseqEpEx for qec"
0x180003ccc  jmp     short loc_180003D2B
0x180003cce  lea     rax, ?TsgQecSecurityCallback@@YAJPEAPEAXPEAX@Z; TsgQecSecurityCallback(void * *,void *)
0x180003cd5  mov     r9d, 29h ; ')'; Flags
0x180003cdb  mov     [rsp+38h+IfCallback], rax; IfCallback
0x180003ce0  lea     rcx, qword_18000DE40; IfSpec
0x180003ce7  xor     r8d, r8d; MgrEpv
0x180003cea  mov     [rsp+38h+MaxCalls], edi; MaxCalls
0x180003cee  xor     edx, edx; MgrTypeUuid
0x180003cf0  call    cs:__imp_RpcServerRegisterIfEx
0x180003cf6  mov     ebx, eax
0x180003cf8  test    eax, eax
0x180003cfa  jz      loc_180003D87
0x180003d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d07  lea     rdi, WPP_GLOBAL_Control
0x180003d0e  cmp     rcx, rdi
0x180003d11  jz      short loc_180003D69
0x180003d13  test    byte ptr [rcx+1Ch], 8
0x180003d17  jz      short loc_180003D3F
0x180003d19  cmp     byte ptr [rcx+19h], 2
0x180003d1d  jb      short loc_180003D3F
0x180003d1f  mov     edx, 31h ; '1'
0x180003d24  lea     r9, aRpcserverregis_0; "RpcServerRegisterIfEx for qec"
0x180003d2b  mov     rcx, [rcx+10h]
0x180003d2f  mov     [rsp+38h+MaxCalls], eax
0x180003d33  call    WPP_SF_SD
0x180003d38  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d3f  cmp     rcx, rdi
0x180003d42  jz      short loc_180003D69
0x180003d44  test    byte ptr [rcx+1Ch], 8
0x180003d48  jz      short loc_180003D69
0x180003d4a  cmp     byte ptr [rcx+19h], 2
0x180003d4e  jb      short loc_180003D69
0x180003d50  mov     rcx, [rcx+10h]
0x180003d54  lea     r9, aRegisterqecint; "RegisterQecInterfaces"
0x180003d5b  mov     edx, 28h ; '('
0x180003d60  mov     [rsp+38h+MaxCalls], ebx
0x180003d64  call    WPP_SF_SD
0x180003d69  test    ebx, ebx
0x180003d6b  jz      loc_180003EE2
0x180003d71  cmp     ebx, 6B1h
0x180003d77  jz      loc_180003EE2
0x180003d7d  call    ?StopTsgQec@@YAKXZ; StopTsgQec(void)
0x180003d82  jmp     loc_180003EE4
0x180003d87  lea     rcx, ?g_pQECBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; BindingVector
0x180003d8e  call    cs:__imp_RpcServerInqBindings
0x180003d94  mov     ebx, eax
0x180003d96  test    eax, eax
0x180003d98  jz      short loc_180003DD4
0x180003d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003da1  lea     rdi, WPP_GLOBAL_Control
0x180003da8  cmp     rcx, rdi
0x180003dab  jz      short loc_180003D71
0x180003dad  test    byte ptr [rcx+1Ch], 8
0x180003db1  jz      short loc_180003D71
0x180003db3  cmp     byte ptr [rcx+19h], 2
0x180003db7  jb      short loc_180003D71
0x180003db9  mov     edx, 29h ; ')'
0x180003dbe  lea     r9, aRpcserverinqbi; "RpcServerInqBindings"
0x180003dc5  mov     rcx, [rcx+10h]
0x180003dc9  mov     [rsp+38h+MaxCalls], eax
0x180003dcd  call    WPP_SF_SD
0x180003dd2  jmp     short loc_180003D71
0x180003dd4  mov     rdx, cs:?g_pQECBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; BindingVector
0x180003ddb  lea     r9, Annotation; "Terminal Server QEC"
0x180003de2  xor     r8d, r8d; UuidVector
0x180003de5  lea     rcx, qword_18000DE40; IfSpec
0x180003dec  call    cs:__imp_RpcEpRegisterW
0x180003df2  mov     ebx, eax
0x180003df4  test    eax, eax
0x180003df6  jz      short loc_180003E31
0x180003df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dff  lea     rdi, WPP_GLOBAL_Control
0x180003e06  cmp     rcx, rdi
0x180003e09  jz      loc_180003D71
0x180003e0f  test    byte ptr [rcx+1Ch], 8
0x180003e13  jz      loc_180003D71
0x180003e19  cmp     byte ptr [rcx+19h], 2
0x180003e1d  jb      loc_180003D71
0x180003e23  mov     edx, 2Ah ; '*'
0x180003e28  lea     r9, aRpcepregister; "RpcEpRegister"
0x180003e2f  jmp     short loc_180003DC5
0x180003e31  call    ?RegisterAuthServices@@YAKXZ; RegisterAuthServices(void)
0x180003e36  mov     ebx, eax
0x180003e38  test    eax, eax
0x180003e3a  jz      short loc_180003E78
0x180003e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e43  lea     rdi, WPP_GLOBAL_Control
0x180003e4a  cmp     rcx, rdi
0x180003e4d  jz      loc_180003D71
0x180003e53  test    byte ptr [rcx+1Ch], 8
0x180003e57  jz      loc_180003D71
0x180003e5d  cmp     byte ptr [rcx+19h], 2
0x180003e61  jb      loc_180003D71
0x180003e67  mov     edx, 2Bh ; '+'
0x180003e6c  lea     r9, aRegisterauthse; "RegisterAuthServices"
0x180003e73  jmp     loc_180003DC5
0x180003e78  mov     ecx, 1; MinimumCallThreads
0x180003e7d  mov     edx, edi; MaxCalls
0x180003e7f  mov     r8d, ecx; DontWait
0x180003e82  call    cs:__imp_RpcServerListen
0x180003e88  mov     ebx, eax
0x180003e8a  test    eax, eax
0x180003e8c  jz      short loc_180003EE2
0x180003e8e  cmp     eax, 6B1h
0x180003e93  jz      loc_180003D71
0x180003e99  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ea0  lea     rdi, WPP_GLOBAL_Control
0x180003ea7  cmp     rcx, rdi
0x180003eaa  jz      loc_180003D7D
0x180003eb0  test    byte ptr [rcx+1Ch], 8
0x180003eb4  jz      loc_180003D7D
0x180003eba  cmp     byte ptr [rcx+19h], 2
0x180003ebe  jb      loc_180003D7D
0x180003ec4  mov     rcx, [rcx+10h]
0x180003ec8  lea     r9, aRpcserverliste; "RpcServerListen"
0x180003ecf  mov     edx, 2Ch ; ','
0x180003ed4  mov     [rsp+38h+MaxCalls], eax
0x180003ed8  call    WPP_SF_SD
0x180003edd  jmp     loc_180003D7D
0x180003ee2  xor     ebx, ebx
0x180003ee4  mov     eax, ebx
0x180003ee6  mov     rbx, [rsp+38h+arg_0]
0x180003eeb  add     rsp, 30h
0x180003eef  pop     rdi
0x180003ef0  retn
```
