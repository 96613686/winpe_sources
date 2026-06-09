# CRCMPrivateRpc::Start(void)

- ea: `0x18002d180`
- end: `0x18002d3e5`
- name: `?Start@CRCMPrivateRpc@@UEAAJXZ`
- size: `613`
- prototype: `__int64 __fastcall(CRCMPrivateRpc *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a210`
- `0x18002d180`
- `0x1800321f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d29a`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002d2cd`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002d2cd`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002d327`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002d362`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002d327`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18002d362`
- `RPCRT4!RpcServerListen` at `0x18002d387`
- `RPCRT4!RpcServerListen` at `0x18002d387`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d3bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d3bc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002d276`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002d276`

## string_xrefs

- `0x18002d286`: `Error %d ConvertStringSecurityDescriptorToSecurityDescriptor`
- `0x18002d24f`: `RCMPrivateRpc already started`

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
                qword_1800CF970,
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
                  qword_1800CF5B0,
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
0x18002d180  mov     [rsp+arg_8], rbx
0x18002d185  push    rsi
0x18002d186  sub     rsp, 1D0h
0x18002d18d  mov     rax, cs:__security_cookie
0x18002d194  xor     rax, rsp
0x18002d197  mov     [rsp+1D8h+var_18], rax
0x18002d19f  mov     rsi, rcx
0x18002d1a2  mov     [rsp+1D8h+SecurityDescriptor], 0
0x18002d1ab  mov     ecx, 2
0x18002d1b0  lea     rax, [rsp+1D8h+StringSecurityDescriptor]
0x18002d1b5  lea     rdx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18002d1bc  lea     ebx, [rcx+7Eh]
0x18002d1bf  movups  xmm0, xmmword ptr [rdx]
0x18002d1c2  movups  xmm1, xmmword ptr [rdx+10h]
0x18002d1c6  movups  xmmword ptr [rax], xmm0
0x18002d1c9  movups  xmm0, xmmword ptr [rdx+20h]
0x18002d1cd  movups  xmmword ptr [rax+10h], xmm1
0x18002d1d1  movups  xmm1, xmmword ptr [rdx+30h]
0x18002d1d5  movups  xmmword ptr [rax+20h], xmm0
0x18002d1d9  movups  xmm0, xmmword ptr [rdx+40h]
0x18002d1dd  movups  xmmword ptr [rax+30h], xmm1
0x18002d1e1  movups  xmm1, xmmword ptr [rdx+50h]
0x18002d1e5  movups  xmmword ptr [rax+40h], xmm0
0x18002d1e9  movups  xmm0, xmmword ptr [rdx+60h]
0x18002d1ed  movups  xmmword ptr [rax+50h], xmm1
0x18002d1f1  movups  xmm1, xmmword ptr [rdx+70h]
0x18002d1f5  add     rdx, rbx
0x18002d1f8  movups  xmmword ptr [rax+60h], xmm0
0x18002d1fc  movups  xmmword ptr [rax+70h], xmm1
0x18002d200  add     rax, rbx
0x18002d203  sub     rcx, 1
0x18002d207  jnz     short loc_18002D1BF
0x18002d209  movups  xmm0, xmmword ptr [rdx]
0x18002d20c  movups  xmm1, xmmword ptr [rdx+10h]
0x18002d210  movups  xmmword ptr [rax], xmm0
0x18002d213  movups  xmm0, xmmword ptr [rdx+20h]
0x18002d217  movups  xmmword ptr [rax+10h], xmm1
0x18002d21b  movups  xmm1, xmmword ptr [rdx+30h]
0x18002d21f  movups  xmmword ptr [rax+20h], xmm0
0x18002d223  movups  xmm0, xmmword ptr [rdx+40h]
0x18002d227  movups  xmmword ptr [rax+30h], xmm1
0x18002d22b  movups  xmm1, xmmword ptr [rdx+50h]
0x18002d22f  movups  xmmword ptr [rax+40h], xmm0
0x18002d233  movups  xmm0, xmmword ptr [rdx+60h]
0x18002d237  movups  xmmword ptr [rax+50h], xmm1
0x18002d23b  movups  xmm1, xmmword ptr [rdx+6Ah]
0x18002d23f  movups  xmmword ptr [rax+60h], xmm0
0x18002d243  movups  xmmword ptr [rax+6Ah], xmm1
0x18002d247  cmp     [rsi+638h], ecx
0x18002d24d  jz      short loc_18002D265
0x18002d24f  lea     rdx, aRcmprivaterpcA; "RCMPrivateRpc already started"
0x18002d256  mov     ecx, 1; int
0x18002d25b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d260  jmp     loc_18002D3B0
0x18002d265  xor     r9d, r9d; SecurityDescriptorSize
0x18002d268  lea     r8, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x18002d26d  lea     rcx, [rsp+1D8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002d272  lea     edx, [r9+1]; StringSDRevision
0x18002d276  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002d27c  test    eax, eax
0x18002d27e  jnz     short loc_18002D2B8
0x18002d280  call    cs:__imp_GetLastError
0x18002d286  lea     rdx, aErrorDConverts_2; "Error %d ConvertStringSecurityDescripto"...
0x18002d28d  mov     ecx, 8; int
0x18002d292  mov     r8d, eax
0x18002d295  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d29a  call    cs:__imp_GetLastError
0x18002d2a0  mov     ebx, eax
0x18002d2a2  test    eax, eax
0x18002d2a4  jle     loc_18002D3B2
0x18002d2aa  movzx   ebx, ax
0x18002d2ad  or      ebx, 80070000h
0x18002d2b3  jmp     loc_18002D3B2
0x18002d2b8  mov     r9, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x18002d2bd  lea     r8, aTermsrvapi; "TermSrvApi"
0x18002d2c4  mov     edx, ebx; MaxCalls
0x18002d2c6  lea     rcx, aNcalrpc; "ncalrpc"
0x18002d2cd  call    cs:__imp_RpcServerUseProtseqEpW
0x18002d2d3  mov     ebx, eax
0x18002d2d5  test    eax, eax
0x18002d2d7  jz      short loc_18002D301
0x18002d2d9  cmp     eax, 6CCh
0x18002d2de  jz      short loc_18002D301
0x18002d2e0  lea     rdx, aErrorDRpcusepr; "Error %d RpcUseProtseqEp on ncalrpc"
0x18002d2e7  mov     r8d, ebx
0x18002d2ea  mov     ecx, 8; int
0x18002d2ef  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d2f4  test    ebx, ebx
0x18002d2f6  jle     loc_18002D3B2
0x18002d2fc  movzx   ebx, bx
0x18002d2ff  jmp     short loc_18002D2AD
0x18002d301  lea     rax, ?staticRCMPrivateRpcSecurityCallback@CRCMPrivateRpc@@CAJPEAX0@Z; CRCMPrivateRpc::staticRCMPrivateRpcSecurityCallback(void *,void *)
0x18002d308  mov     r9d, 9; Flags
0x18002d30e  mov     [rsp+1D8h+IfCallback], rax; IfCallback
0x18002d313  lea     rcx, qword_1800CF970; IfSpec
0x18002d31a  xor     r8d, r8d; MgrEpv
0x18002d31d  mov     [rsp+1D8h+MaxCalls], 4D2h; MaxCalls
0x18002d325  xor     edx, edx; MgrTypeUuid
0x18002d327  call    cs:__imp_RpcServerRegisterIfEx
0x18002d32d  mov     ebx, eax
0x18002d32f  test    eax, eax
0x18002d331  jz      short loc_18002D33C
0x18002d333  lea     rdx, aErrorDRpcserve_2; "Error %d RpcServerRegisterIf"
0x18002d33a  jmp     short loc_18002D2E7
0x18002d33c  lea     rax, ?staticRCMAdminRpcSecurityCallback@CRCMPrivateRpc@@CAJPEAX0@Z; CRCMPrivateRpc::staticRCMAdminRpcSecurityCallback(void *,void *)
0x18002d343  mov     r9d, 9; Flags
0x18002d349  mov     [rsp+1D8h+IfCallback], rax; IfCallback
0x18002d34e  lea     rcx, qword_1800CF5B0; IfSpec
0x18002d355  xor     r8d, r8d; MgrEpv
0x18002d358  mov     [rsp+1D8h+MaxCalls], 4D2h; MaxCalls
0x18002d360  xor     edx, edx; MgrTypeUuid
0x18002d362  call    cs:__imp_RpcServerRegisterIfEx
0x18002d368  mov     ebx, eax
0x18002d36a  test    eax, eax
0x18002d36c  jz      short loc_18002D37A
0x18002d36e  lea     rdx, aErrorDRpcserve_4; "Error %d RpcServerRegisterIf( admin )"
0x18002d375  jmp     loc_18002D2E7
0x18002d37a  mov     ecx, 1; MinimumCallThreads
0x18002d37f  mov     edx, 4D2h; MaxCalls
0x18002d384  mov     r8d, ecx; DontWait
0x18002d387  call    cs:__imp_RpcServerListen
0x18002d38d  mov     ebx, eax
0x18002d38f  test    eax, eax
0x18002d391  jz      short loc_18002D3A6
0x18002d393  cmp     eax, 6B1h
0x18002d398  jz      short loc_18002D3A6
0x18002d39a  lea     rdx, aErrorDRpcserve; "Error %d RpcServerListen"
0x18002d3a1  jmp     loc_18002D2E7
0x18002d3a6  mov     dword ptr [rsi+638h], 1
0x18002d3b0  xor     ebx, ebx
0x18002d3b2  mov     rcx, [rsp+1D8h+SecurityDescriptor]; hMem
0x18002d3b7  test    rcx, rcx
0x18002d3ba  jz      short loc_18002D3C2
0x18002d3bc  call    cs:__imp_LocalFree
0x18002d3c2  mov     eax, ebx
0x18002d3c4  mov     rcx, [rsp+1D8h+var_18]
0x18002d3cc  xor     rcx, rsp; StackCookie
0x18002d3cf  call    __security_check_cookie
0x18002d3d4  mov     rbx, [rsp+1D8h+arg_8]
0x18002d3dc  add     rsp, 1D0h
0x18002d3e3  pop     rsi
0x18002d3e4  retn
```
