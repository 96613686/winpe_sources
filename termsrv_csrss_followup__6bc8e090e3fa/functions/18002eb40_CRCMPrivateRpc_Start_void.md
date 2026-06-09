# CRCMPrivateRpc::Start(void)

- ea: `0x18002eb40`
- end: `0x18002edd6`
- name: `?Start@CRCMPrivateRpc@@UEAAJXZ`
- size: `662`
- prototype: `__int64 __fastcall(CRCMPrivateRpc *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009940`
- `0x18002eb40`
- `0x180033f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec66`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002ec9f`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002ec9f`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002ecff`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002ed40`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002ecff`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002ed40`
- `RPCRT4!RpcServerListen` at `0x18002ed6b`
- `RPCRT4!RpcServerListen` at `0x18002ed6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eda6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eda6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ec36`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ec36`

## string_xrefs

- `0x18002ec52`: `Error %d ConvertStringSecurityDescriptorToSecurityDescriptor`
- `0x18002ec0f`: `RCMPrivateRpc already started`

## pseudocode

```c
__int64 __fastcall CRCMPrivateRpc::Start(CRCMPrivateRpc *this)
{
  __int64 v2; // rcx
  WCHAR *v3; // rax
  const wchar_t *v4; // rdx
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  DWORD LastError; // eax
  signed int v20; // eax
  unsigned int v21; // ebx
  unsigned int v22; // eax
  unsigned int v23; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-1A8h] BYREF
  WCHAR StringSecurityDescriptor[192]; // [rsp+40h] [rbp-198h] BYREF

  SecurityDescriptor = 0;
  v2 = 2;
  v3 = StringSecurityDescriptor;
  v4 = L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GRGWGX;;;AC)(A;;GRGWGX;;;S-1-15-3-1024-1864111754-7"
        "76273317-3666925027-2523908081-3792458206-3582472437-4114419977-1582884857)";
  do
  {
    v5 = *((_OWORD *)v4 + 1);
    *(_OWORD *)v3 = *(_OWORD *)v4;
    v6 = *((_OWORD *)v4 + 2);
    *((_OWORD *)v3 + 1) = v5;
    v7 = *((_OWORD *)v4 + 3);
    *((_OWORD *)v3 + 2) = v6;
    v8 = *((_OWORD *)v4 + 4);
    *((_OWORD *)v3 + 3) = v7;
    v9 = *((_OWORD *)v4 + 5);
    *((_OWORD *)v3 + 4) = v8;
    v10 = *((_OWORD *)v4 + 6);
    *((_OWORD *)v3 + 5) = v9;
    v11 = *((_OWORD *)v4 + 7);
    v4 += 64;
    *((_OWORD *)v3 + 6) = v10;
    *((_OWORD *)v3 + 7) = v11;
    v3 += 64;
    --v2;
  }
  while ( v2 );
  v12 = *((_OWORD *)v4 + 1);
  *(_OWORD *)v3 = *(_OWORD *)v4;
  v13 = *((_OWORD *)v4 + 2);
  *((_OWORD *)v3 + 1) = v12;
  v14 = *((_OWORD *)v4 + 3);
  *((_OWORD *)v3 + 2) = v13;
  v15 = *((_OWORD *)v4 + 4);
  *((_OWORD *)v3 + 3) = v14;
  v16 = *((_OWORD *)v4 + 5);
  *((_OWORD *)v3 + 4) = v15;
  v17 = *((_OWORD *)v4 + 6);
  *((_OWORD *)v3 + 5) = v16;
  v18 = *(_OWORD *)(v4 + 53);
  *((_OWORD *)v3 + 6) = v17;
  *(_OWORD *)(v3 + 53) = v18;
  if ( !*((_DWORD *)this + 398) )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      v22 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x80u, (RPC_WSTR)L"TermSrvApi", SecurityDescriptor);
      v21 = v22;
      if ( !v22 || v22 == 1740 )
      {
        v21 = RpcServerRegisterIfEx(
                qword_1800D59C0,
                0,
                0,
                9u,
                0x4D2u,
                CRCMPrivateRpc::staticRCMPrivateRpcSecurityCallback);
        if ( v21 )
        {
          _DbgPrintMessage(8, "Error %d RpcServerRegisterIf", v21);
        }
        else
        {
          v21 = RpcServerRegisterIfEx(
                  qword_1800D5710,
                  0,
                  0,
                  9u,
                  0x4D2u,
                  CRCMPrivateRpc::staticRCMAdminRpcSecurityCallback);
          if ( v21 )
          {
            _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( admin )", v21);
          }
          else
          {
            v23 = RpcServerListen(1u, 0x4D2u, 1u);
            v21 = v23;
            if ( !v23 || v23 == 1713 )
            {
              *((_DWORD *)this + 398) = 1;
              goto LABEL_22;
            }
            _DbgPrintMessage(8, "Error %d RpcServerListen", v23);
          }
        }
      }
      else
      {
        _DbgPrintMessage(8, "Error %d RpcUseProtseqEp on ncalrpc", v22);
      }
      if ( (int)v21 <= 0 )
        goto LABEL_23;
      v21 = (unsigned __int16)v21;
    }
    else
    {
      LastError = GetLastError();
      _DbgPrintMessage(8, "Error %d ConvertStringSecurityDescriptorToSecurityDescriptor", LastError);
      v20 = GetLastError();
      v21 = v20;
      if ( v20 <= 0 )
        goto LABEL_23;
      v21 = (unsigned __int16)v20;
    }
    v21 |= 0x80070000;
    goto LABEL_23;
  }
  _DbgPrintMessage(1, "RCMPrivateRpc already started");
LABEL_22:
  v21 = 0;
LABEL_23:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v21;
}

```

## disassembly

```asm
0x18002eb40  mov     [rsp+arg_8], rbx
0x18002eb45  push    rsi
0x18002eb46  sub     rsp, 1D0h
0x18002eb4d  mov     rax, cs:__security_cookie
0x18002eb54  xor     rax, rsp
0x18002eb57  mov     [rsp+1D8h+var_18], rax
0x18002eb5f  mov     rsi, rcx
0x18002eb62  mov     [rsp+1D8h+SecurityDescriptor], 0
0x18002eb6b  mov     ecx, 2
0x18002eb70  lea     rax, [rsp+1D8h+StringSecurityDescriptor]
0x18002eb75  lea     rdx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18002eb7c  lea     ebx, [rcx+7Eh]
0x18002eb7f  movups  xmm0, xmmword ptr [rdx]
0x18002eb82  movups  xmm1, xmmword ptr [rdx+10h]
0x18002eb86  movups  xmmword ptr [rax], xmm0
0x18002eb89  movups  xmm0, xmmword ptr [rdx+20h]
0x18002eb8d  movups  xmmword ptr [rax+10h], xmm1
0x18002eb91  movups  xmm1, xmmword ptr [rdx+30h]
0x18002eb95  movups  xmmword ptr [rax+20h], xmm0
0x18002eb99  movups  xmm0, xmmword ptr [rdx+40h]
0x18002eb9d  movups  xmmword ptr [rax+30h], xmm1
0x18002eba1  movups  xmm1, xmmword ptr [rdx+50h]
0x18002eba5  movups  xmmword ptr [rax+40h], xmm0
0x18002eba9  movups  xmm0, xmmword ptr [rdx+60h]
0x18002ebad  movups  xmmword ptr [rax+50h], xmm1
0x18002ebb1  movups  xmm1, xmmword ptr [rdx+70h]
0x18002ebb5  add     rdx, rbx
0x18002ebb8  movups  xmmword ptr [rax+60h], xmm0
0x18002ebbc  movups  xmmword ptr [rax+70h], xmm1
0x18002ebc0  add     rax, rbx
0x18002ebc3  sub     rcx, 1
0x18002ebc7  jnz     short loc_18002EB7F
0x18002ebc9  movups  xmm0, xmmword ptr [rdx]
0x18002ebcc  movups  xmm1, xmmword ptr [rdx+10h]
0x18002ebd0  movups  xmmword ptr [rax], xmm0
0x18002ebd3  movups  xmm0, xmmword ptr [rdx+20h]
0x18002ebd7  movups  xmmword ptr [rax+10h], xmm1
0x18002ebdb  movups  xmm1, xmmword ptr [rdx+30h]
0x18002ebdf  movups  xmmword ptr [rax+20h], xmm0
0x18002ebe3  movups  xmm0, xmmword ptr [rdx+40h]
0x18002ebe7  movups  xmmword ptr [rax+30h], xmm1
0x18002ebeb  movups  xmm1, xmmword ptr [rdx+50h]
0x18002ebef  movups  xmmword ptr [rax+40h], xmm0
0x18002ebf3  movups  xmm0, xmmword ptr [rdx+60h]
0x18002ebf7  movups  xmmword ptr [rax+50h], xmm1
0x18002ebfb  movups  xmm1, xmmword ptr [rdx+6Ah]
0x18002ebff  movups  xmmword ptr [rax+60h], xmm0
0x18002ec03  movups  xmmword ptr [rax+6Ah], xmm1
0x18002ec07  cmp     [rsi+638h], ecx
0x18002ec0d  jz      short loc_18002EC25
0x18002ec0f  lea     rdx, aRcmprivaterpcA; "RCMPrivateRpc already started"
0x18002ec16  mov     ecx, 1; int
0x18002ec1b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ec20  jmp     loc_18002ED9A
0x18002ec25  xor     r9d, r9d; SecurityDescriptorSize
0x18002ec28  lea     r8, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x18002ec2d  lea     rcx, [rsp+1D8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002ec32  lea     edx, [r9+1]; StringSDRevision
0x18002ec36  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002ec3d  nop     dword ptr [rax+rax+00h]
0x18002ec42  test    eax, eax
0x18002ec44  jnz     short loc_18002EC8A
0x18002ec46  call    cs:__imp_GetLastError
0x18002ec4d  nop     dword ptr [rax+rax+00h]
0x18002ec52  lea     rdx, aErrorDConverts_2; "Error %d ConvertStringSecurityDescripto"...
0x18002ec59  mov     ecx, 8; int
0x18002ec5e  mov     r8d, eax
0x18002ec61  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ec66  call    cs:__imp_GetLastError
0x18002ec6d  nop     dword ptr [rax+rax+00h]
0x18002ec72  mov     ebx, eax
0x18002ec74  test    eax, eax
0x18002ec76  jle     loc_18002ED9C
0x18002ec7c  movzx   ebx, ax
0x18002ec7f  or      ebx, 80070000h
0x18002ec85  jmp     loc_18002ED9C
0x18002ec8a  mov     r9, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x18002ec8f  lea     r8, aTermsrvapi; "TermSrvApi"
0x18002ec96  mov     edx, ebx; MaxCalls
0x18002ec98  lea     rcx, aNcalrpc; "ncalrpc"
0x18002ec9f  call    cs:__imp_RpcServerUseProtseqEpW
0x18002eca6  nop     dword ptr [rax+rax+00h]
0x18002ecab  mov     ebx, eax
0x18002ecad  test    eax, eax
0x18002ecaf  jz      short loc_18002ECD9
0x18002ecb1  cmp     eax, 6CCh
0x18002ecb6  jz      short loc_18002ECD9
0x18002ecb8  lea     rdx, aErrorDRpcusepr; "Error %d RpcUseProtseqEp on ncalrpc"
0x18002ecbf  mov     r8d, ebx
0x18002ecc2  mov     ecx, 8; int
0x18002ecc7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002eccc  test    ebx, ebx
0x18002ecce  jle     loc_18002ED9C
0x18002ecd4  movzx   ebx, bx
0x18002ecd7  jmp     short loc_18002EC7F
0x18002ecd9  lea     rax, ?staticRCMPrivateRpcSecurityCallback@CRCMPrivateRpc@@CAJPEAX0@Z; CRCMPrivateRpc::staticRCMPrivateRpcSecurityCallback(void *,void *)
0x18002ece0  mov     r9d, 9; Flags
0x18002ece6  mov     [rsp+1D8h+IfCallback], rax; IfCallback
0x18002eceb  lea     rcx, qword_1800D59C0; IfSpec
0x18002ecf2  xor     r8d, r8d; MgrEpv
0x18002ecf5  mov     [rsp+1D8h+MaxCalls], 4D2h; MaxCalls
0x18002ecfd  xor     edx, edx; MgrTypeUuid
0x18002ecff  call    cs:__imp_RpcServerRegisterIfEx
0x18002ed06  nop     dword ptr [rax+rax+00h]
0x18002ed0b  mov     ebx, eax
0x18002ed0d  test    eax, eax
0x18002ed0f  jz      short loc_18002ED1A
0x18002ed11  lea     rdx, aErrorDRpcserve_2; "Error %d RpcServerRegisterIf"
0x18002ed18  jmp     short loc_18002ECBF
0x18002ed1a  lea     rax, ?staticRCMAdminRpcSecurityCallback@CRCMPrivateRpc@@CAJPEAX0@Z; CRCMPrivateRpc::staticRCMAdminRpcSecurityCallback(void *,void *)
0x18002ed21  mov     r9d, 9; Flags
0x18002ed27  mov     [rsp+1D8h+IfCallback], rax; IfCallback
0x18002ed2c  lea     rcx, qword_1800D5710; IfSpec
0x18002ed33  xor     r8d, r8d; MgrEpv
0x18002ed36  mov     [rsp+1D8h+MaxCalls], 4D2h; MaxCalls
0x18002ed3e  xor     edx, edx; MgrTypeUuid
0x18002ed40  call    cs:__imp_RpcServerRegisterIfEx
0x18002ed47  nop     dword ptr [rax+rax+00h]
0x18002ed4c  mov     ebx, eax
0x18002ed4e  test    eax, eax
0x18002ed50  jz      short loc_18002ED5E
0x18002ed52  lea     rdx, aErrorDRpcserve_4; "Error %d RpcServerRegisterIf( admin )"
0x18002ed59  jmp     loc_18002ECBF
0x18002ed5e  mov     ecx, 1; MinimumCallThreads
0x18002ed63  mov     edx, 4D2h; MaxCalls
0x18002ed68  mov     r8d, ecx; DontWait
0x18002ed6b  call    cs:__imp_RpcServerListen
0x18002ed72  nop     dword ptr [rax+rax+00h]
0x18002ed77  mov     ebx, eax
0x18002ed79  test    eax, eax
0x18002ed7b  jz      short loc_18002ED90
0x18002ed7d  cmp     eax, 6B1h
0x18002ed82  jz      short loc_18002ED90
0x18002ed84  lea     rdx, aErrorDRpcserve; "Error %d RpcServerListen"
0x18002ed8b  jmp     loc_18002ECBF
0x18002ed90  mov     dword ptr [rsi+638h], 1
0x18002ed9a  xor     ebx, ebx
0x18002ed9c  mov     rcx, [rsp+1D8h+SecurityDescriptor]; hMem
0x18002eda1  test    rcx, rcx
0x18002eda4  jz      short loc_18002EDB2
0x18002eda6  call    cs:__imp_LocalFree
0x18002edad  nop     dword ptr [rax+rax+00h]
0x18002edb2  mov     eax, ebx
0x18002edb4  mov     rcx, [rsp+1D8h+var_18]
0x18002edbc  xor     rcx, rsp; StackCookie
0x18002edbf  call    __security_check_cookie
0x18002edc4  mov     rbx, [rsp+1D8h+arg_8]
0x18002edcc  add     rsp, 1D0h
0x18002edd3  pop     rsi
0x18002edd4  retn
```
