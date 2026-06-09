# RpcManager::RegisterRpc(void)

- ea: `0x140050bfc`
- end: `0x140050e55`
- name: `?RegisterRpc@RpcManager@@SAJXZ`
- size: `601`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14004f988`

## callees

- `0x14000ad50`
- `0x1400160a0`
- `0x14002abc0`
- `0x14002b810`
- `0x14002f030`
- `0x140050bfc`
- `0x140058a9c`
- `0x140058b94`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140050dfc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140050dfc`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x140050dce`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x140050dce`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x140050d7f`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x140050d7f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140050cfd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140050cfd`

## string_xrefs

- `0x140050e21`: `Failed to create RPC interface group: 0x%x`

## pseudocode

```c
__int64 RpcManager::RegisterRpc(void)
{
  bool v0; // si
  unsigned int v1; // r15d
  unsigned __int16 *RpcOverTcpPortString; // r14
  char RpcProtocolsEnabled; // di
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int128 v6; // xmm1
  __int64 v7; // xmm0_8
  __int64 v8; // rcx
  __int128 v9; // xmm1
  __int64 v10; // xmm0_8
  int v11; // eax
  unsigned int v12; // ebx
  int i; // esi
  int v14; // eax
  int pvData; // [rsp+40h] [rbp-79h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-75h] BYREF
  __int128 v18; // [rsp+50h] [rbp-69h] BYREF
  __int128 v19; // [rsp+60h] [rbp-59h]
  _QWORD v20[12]; // [rsp+70h] [rbp-49h]

  v0 = gNamedPipeState != 2;
  v1 = 2 * (gNamedPipeState != 2) + 5;
  RpcOverTcpPortString = GetRpcOverTcpPortString();
  memset_0(&v18, 0, 0x78u);
  RpcProtocolsEnabled = GetRpcProtocolsEnabled();
  v4 = RpcProtocolsEnabled & 1;
  if ( (RpcProtocolsEnabled & 1) != 0 )
  {
    v18 = *(_OWORD *)&RpcManager::m_rpcEndpoint;
    v20[0] = qword_1400CA480;
    v19 = *(_OWORD *)byte_1400CA470;
  }
  if ( v0 )
  {
    if ( (RpcProtocolsEnabled & 2) != 0 )
    {
      v5 = 5 * v4;
      v4 = (unsigned int)(v4 + 1);
      v6 = *(_OWORD *)&off_1400CA498;
      *(__int128 *)((char *)&v18 + 8 * v5) = *(_OWORD *)&qword_1400CA488;
      v7 = qword_1400CA4A8;
      *(_OWORD *)&v20[v5 - 2] = v6;
      v20[v5] = v7;
    }
    pvData = 0;
    pcbData[0] = 4;
    if ( (RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\Print",
            L"DisableRpcTcp",
            0x18u,
            0,
            &pvData,
            pcbData)
       || !pvData)
      && (RpcProtocolsEnabled & 4) != 0 )
    {
      v8 = 5 * v4;
      v9 = xmmword_1400CA4C0;
      LODWORD(v4) = v4 + 1;
      *(__int128 *)((char *)&v18 + 8 * v8) = *(_OWORD *)byte_1400CA4B0;
      v10 = qword_1400CA4D0;
      *(_OWORD *)&v20[v8 - 2] = v9;
      v20[v8] = v10;
      v20[v8 - 2] = RpcOverTcpPortString;
    }
  }
  v11 = RpcServerInterfaceGroupCreateW(
          &RpcManager::m_rpcInterface,
          v1,
          &v18,
          (unsigned int)v4,
          RpcManager::m_timeout,
          DemandStart::IdleCallback,
          0,
          &RpcManager::m_interfaceGroup);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  DllFreeSplStr(RpcOverTcpPortString);
  if ( (v12 & 0x80000000) != 0 )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "RpcManager::RegisterRpc",
      L"Failed to create RPC interface group: 0x%x",
      v12);
  }
  else
  {
    SpoolerServiceTelemetry::WriteDbgTraceInfo(
      "RpcManager::RegisterRpc",
      L"Registered RPC interface group 0x%p",
      RpcManager::m_interfaceGroup);
    for ( i = 0; i < 5; ++i )
    {
      v14 = RpcServerInterfaceGroupActivate(RpcManager::m_interfaceGroup);
      v12 = v14;
      if ( v14 > 0 )
        v12 = (unsigned __int16)v14 | 0x80070000;
      if ( v12 != -2147023156 )
      {
        if ( (v12 & 0x80000000) == 0 )
          SpoolerServiceTelemetry::WriteDbgTraceInfo("RpcManager::RegisterRpc", L"Activated RPC interface group");
        else
          SpoolerServiceTelemetry::WriteDbgTraceError(
            "RpcManager::RegisterRpc",
            L"Failed to activate RPC interface group: 0x%x",
            v12);
        return v12;
      }
      SpoolerServiceTelemetry::WriteDbgTraceInfo(
        "RpcManager::RegisterRpc",
        L"Waiting for previous spoooler endpoints to clean up");
      Sleep(0xBB8u);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140050bfc  push    rbp
0x140050bfe  push    rbx
0x140050bff  push    rsi
0x140050c00  push    rdi
0x140050c01  push    r14
0x140050c03  push    r15
0x140050c05  lea     rbp, [rsp-2Fh]
0x140050c0a  sub     rsp, 0E8h
0x140050c11  mov     rax, cs:__security_cookie
0x140050c18  xor     rax, rsp
0x140050c1b  mov     [rbp+57h+var_40], rax
0x140050c1f  cmp     cs:?gNamedPipeState@@3UNamedPipeState@@A, 2; NamedPipeState gNamedPipeState
0x140050c26  setnz   sil
0x140050c2a  movzx   eax, sil
0x140050c2e  lea     r15d, ds:5[rax*2]
0x140050c36  call    ?GetRpcOverTcpPortString@@YAPEAGXZ; GetRpcOverTcpPortString(void)
0x140050c3b  xor     edx, edx; Val
0x140050c3d  lea     rcx, [rbp+57h+var_C0]; void *
0x140050c41  mov     r14, rax
0x140050c44  lea     r8d, [rdx+78h]; Size
0x140050c48  call    memset_0
0x140050c4d  call    ?GetRpcProtocolsEnabled@@YAKXZ; GetRpcProtocolsEnabled(void)
0x140050c52  mov     ebx, eax
0x140050c54  mov     edi, eax
0x140050c56  and     ebx, 1
0x140050c59  jz      short loc_140050C7E
0x140050c5b  movaps  xmm0, xmmword ptr cs:?m_rpcEndpoint@RpcManager@@0PAURPC_ENDPOINT_TEMPLATEW@@A; RPC_ENDPOINT_TEMPLATEW near * RpcManager::m_rpcEndpoint
0x140050c62  movaps  xmm1, xmmword ptr cs:byte_1400CA470
0x140050c69  movaps  [rbp+57h+var_C0], xmm0
0x140050c6d  movsd   xmm0, cs:qword_1400CA480
0x140050c75  movsd   [rbp+57h+var_A0], xmm0
0x140050c7a  movaps  [rbp+57h+var_B0], xmm1
0x140050c7e  test    sil, sil
0x140050c81  jz      loc_140050D43
0x140050c87  test    dil, 2
0x140050c8b  jz      short loc_140050CB9
0x140050c8d  movups  xmm0, xmmword ptr cs:qword_1400CA488
0x140050c94  lea     rcx, [rbx+rbx*4]
0x140050c98  inc     ebx
0x140050c9a  movups  xmm1, xmmword ptr cs:off_1400CA498; "\\pipe\\spoolss"
0x140050ca1  movups  [rbp+rcx*8+57h+var_C0], xmm0
0x140050ca6  movsd   xmm0, cs:qword_1400CA4A8
0x140050cae  movups  [rbp+rcx*8+57h+var_B0], xmm1
0x140050cb3  movsd   [rbp+rcx*8+57h+var_A0], xmm0
0x140050cb9  lea     rax, [rbp+57h+var_CC]
0x140050cbd  mov     [rbp+57h+var_D0], 0
0x140050cc4  mov     [rsp+110h+pcbData], rax; pcbData
0x140050cc9  lea     r8, aDisablerpctcp; "DisableRpcTcp"
0x140050cd0  lea     rax, [rbp+57h+var_D0]
0x140050cd4  mov     [rbp+57h+var_CC], 4
0x140050cdb  mov     [rsp+110h+pvData], rax; pvData
0x140050ce0  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x140050ce7  mov     r9d, 18h; dwFlags
0x140050ced  mov     [rsp+110h+pdwType], 0; pdwType
0x140050cf6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140050cfd  call    cs:__imp_RegGetValueW
0x140050d03  test    eax, eax
0x140050d05  jnz     short loc_140050D0C
0x140050d07  cmp     [rbp+57h+var_D0], eax
0x140050d0a  jnz     short loc_140050D43
0x140050d0c  test    dil, 4
0x140050d10  jz      short loc_140050D43
0x140050d12  movaps  xmm0, xmmword ptr cs:byte_1400CA4B0
0x140050d19  lea     rcx, [rbx+rbx*4]
0x140050d1d  movaps  xmm1, cs:xmmword_1400CA4C0
0x140050d24  inc     ebx
0x140050d26  movups  [rbp+rcx*8+57h+var_C0], xmm0
0x140050d2b  movsd   xmm0, cs:qword_1400CA4D0
0x140050d33  movups  [rbp+rcx*8+57h+var_B0], xmm1
0x140050d38  movsd   [rbp+rcx*8+57h+var_A0], xmm0
0x140050d3e  mov     qword ptr [rbp+rcx*8+57h+var_B0], r14
0x140050d43  lea     rax, ?m_interfaceGroup@RpcManager@@0PEAXEA; void * RpcManager::m_interfaceGroup
0x140050d4a  mov     r9d, ebx
0x140050d4d  mov     [rsp+110h+var_D8], rax
0x140050d52  lea     r8, [rbp+57h+var_C0]
0x140050d56  lea     rax, ?IdleCallback@DemandStart@@SAXPEAX0K@Z; DemandStart::IdleCallback(void *,void *,ulong)
0x140050d5d  mov     [rsp+110h+pcbData], 0
0x140050d66  mov     [rsp+110h+pvData], rax
0x140050d6b  lea     rcx, ?m_rpcInterface@RpcManager@@0PAURPC_INTERFACE_TEMPLATEW@@A; RPC_INTERFACE_TEMPLATEW near * RpcManager::m_rpcInterface
0x140050d72  mov     eax, cs:?m_timeout@RpcManager@@0KA; ulong RpcManager::m_timeout
0x140050d78  mov     edx, r15d
0x140050d7b  mov     dword ptr [rsp+110h+pdwType], eax
0x140050d7f  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x140050d85  mov     ebx, eax
0x140050d87  mov     r15d, 80070000h
0x140050d8d  test    eax, eax
0x140050d8f  jle     short loc_140050D97
0x140050d91  movzx   ebx, ax
0x140050d94  or      ebx, r15d
0x140050d97  mov     rcx, r14
0x140050d9a  call    DllFreeSplStr
0x140050d9f  test    ebx, ebx
0x140050da1  js      short loc_140050E21
0x140050da3  mov     r8, cs:?m_interfaceGroup@RpcManager@@0PEAXEA; void * RpcManager::m_interfaceGroup
0x140050daa  lea     rdi, aRpcmanagerRegi; "RpcManager::RegisterRpc"
0x140050db1  mov     rcx, rdi; char *
0x140050db4  lea     rdx, aRegisteredRpcI; "Registered RPC interface group 0x%p"
0x140050dbb  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140050dc0  xor     esi, esi
0x140050dc2  cmp     esi, 5
0x140050dc5  jge     short loc_140050E37
0x140050dc7  mov     rcx, cs:?m_interfaceGroup@RpcManager@@0PEAXEA; void * RpcManager::m_interfaceGroup
0x140050dce  call    cs:__imp_RpcServerInterfaceGroupActivate
0x140050dd4  mov     ebx, eax
0x140050dd6  test    eax, eax
0x140050dd8  jle     short loc_140050DE0
0x140050dda  movzx   ebx, ax
0x140050ddd  or      ebx, r15d
0x140050de0  mov     rcx, rdi; char *
0x140050de3  cmp     ebx, 800706CCh
0x140050de9  jnz     short loc_140050E06
0x140050deb  lea     rdx, aWaitingForPrev_0; "Waiting for previous spoooler endpoints"...
0x140050df2  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140050df7  mov     ecx, 0BB8h; dwMilliseconds
0x140050dfc  call    cs:__imp_Sleep
0x140050e02  inc     esi
0x140050e04  jmp     short loc_140050DC2
0x140050e06  test    ebx, ebx
0x140050e08  jns     short loc_140050E13
0x140050e0a  lea     rdx, aFailedToActiva; "Failed to activate RPC interface group:"...
0x140050e11  jmp     short loc_140050E2F
0x140050e13  lea     rdx, aActivatedRpcIn; "Activated RPC interface group"
0x140050e1a  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140050e1f  jmp     short loc_140050E37
0x140050e21  lea     rdx, aFailedToCreate_1; "Failed to create RPC interface group: 0"...
0x140050e28  lea     rcx, aRpcmanagerRegi; "RpcManager::RegisterRpc"
0x140050e2f  mov     r8d, ebx
0x140050e32  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140050e37  mov     eax, ebx
0x140050e39  mov     rcx, [rbp+57h+var_40]
0x140050e3d  xor     rcx, rsp; StackCookie
0x140050e40  call    __security_check_cookie
0x140050e45  add     rsp, 0E8h
0x140050e4c  pop     r15
0x140050e4e  pop     r14
0x140050e50  pop     rdi
0x140050e51  pop     rsi
0x140050e52  pop     rbx
0x140050e53  pop     rbp
0x140050e54  retn
```
