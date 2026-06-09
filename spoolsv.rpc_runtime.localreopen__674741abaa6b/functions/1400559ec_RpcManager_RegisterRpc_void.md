# RpcManager::RegisterRpc(void)

- ea: `0x1400559ec`
- end: `0x140055c62`
- name: `?RegisterRpc@RpcManager@@SAJXZ`
- size: `630`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140054600`

## callees

- `0x14000bca0`
- `0x14001748c`
- `0x14002d0a0`
- `0x14002dd20`
- `0x140031720`
- `0x1400559ec`
- `0x14005e1dc`
- `0x14005e2dc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140055c02`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140055c02`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x140055bce`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x140055bce`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x140055b75`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x140055b75`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140055aed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140055aed`

## string_xrefs

- `0x140055c2d`: `Failed to create RPC interface group: 0x%x`

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
    v20[0] = qword_1400D1480;
    v19 = *(_OWORD *)byte_1400D1470;
  }
  if ( v0 )
  {
    if ( (RpcProtocolsEnabled & 2) != 0 )
    {
      v5 = 5 * v4;
      v4 = (unsigned int)(v4 + 1);
      v6 = *(_OWORD *)&off_1400D1498;
      *(__int128 *)((char *)&v18 + 8 * v5) = *(_OWORD *)&qword_1400D1488;
      v7 = qword_1400D14A8;
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
      v9 = xmmword_1400D14C0;
      LODWORD(v4) = v4 + 1;
      *(__int128 *)((char *)&v18 + 8 * v8) = *(_OWORD *)byte_1400D14B0;
      v10 = qword_1400D14D0;
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
0x1400559ec  push    rbp
0x1400559ee  push    rbx
0x1400559ef  push    rsi
0x1400559f0  push    rdi
0x1400559f1  push    r14
0x1400559f3  push    r15
0x1400559f5  lea     rbp, [rsp-2Fh]
0x1400559fa  sub     rsp, 0E8h
0x140055a01  mov     rax, cs:__security_cookie
0x140055a08  xor     rax, rsp
0x140055a0b  mov     [rbp+57h+var_40], rax
0x140055a0f  cmp     cs:?gNamedPipeState@@3UNamedPipeState@@A, 2; NamedPipeState gNamedPipeState
0x140055a16  setnz   sil
0x140055a1a  movzx   eax, sil
0x140055a1e  lea     r15d, ds:5[rax*2]
0x140055a26  call    ?GetRpcOverTcpPortString@@YAPEAGXZ; GetRpcOverTcpPortString(void)
0x140055a2b  xor     edx, edx; Val
0x140055a2d  lea     rcx, [rbp+57h+var_C0]; void *
0x140055a31  mov     r14, rax
0x140055a34  lea     r8d, [rdx+78h]; Size
0x140055a38  call    memset_0
0x140055a3d  call    ?GetRpcProtocolsEnabled@@YAKXZ; GetRpcProtocolsEnabled(void)
0x140055a42  mov     ebx, eax
0x140055a44  mov     edi, eax
0x140055a46  and     ebx, 1
0x140055a49  jz      short loc_140055A6E
0x140055a4b  movaps  xmm0, xmmword ptr cs:?m_rpcEndpoint@RpcManager@@0PAURPC_ENDPOINT_TEMPLATEW@@A; RPC_ENDPOINT_TEMPLATEW near * RpcManager::m_rpcEndpoint
0x140055a52  movaps  xmm1, xmmword ptr cs:byte_1400D1470
0x140055a59  movaps  [rbp+57h+var_C0], xmm0
0x140055a5d  movsd   xmm0, cs:qword_1400D1480
0x140055a65  movsd   [rbp+57h+var_A0], xmm0
0x140055a6a  movaps  [rbp+57h+var_B0], xmm1
0x140055a6e  test    sil, sil
0x140055a71  jz      loc_140055B39
0x140055a77  test    dil, 2
0x140055a7b  jz      short loc_140055AA9
0x140055a7d  movups  xmm0, xmmword ptr cs:qword_1400D1488
0x140055a84  lea     rcx, [rbx+rbx*4]
0x140055a88  inc     ebx
0x140055a8a  movups  xmm1, xmmword ptr cs:off_1400D1498; "\\pipe\\spoolss"
0x140055a91  movups  [rbp+rcx*8+57h+var_C0], xmm0
0x140055a96  movsd   xmm0, cs:qword_1400D14A8
0x140055a9e  movups  [rbp+rcx*8+57h+var_B0], xmm1
0x140055aa3  movsd   [rbp+rcx*8+57h+var_A0], xmm0
0x140055aa9  lea     rax, [rbp+57h+var_CC]
0x140055aad  mov     [rbp+57h+var_D0], 0
0x140055ab4  mov     [rsp+110h+pcbData], rax; pcbData
0x140055ab9  lea     r8, aDisablerpctcp; "DisableRpcTcp"
0x140055ac0  lea     rax, [rbp+57h+var_D0]
0x140055ac4  mov     [rbp+57h+var_CC], 4
0x140055acb  mov     [rsp+110h+pvData], rax; pvData
0x140055ad0  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x140055ad7  mov     r9d, 18h; dwFlags
0x140055add  mov     [rsp+110h+pdwType], 0; pdwType
0x140055ae6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140055aed  call    cs:__imp_RegGetValueW
0x140055af4  nop     dword ptr [rax+rax+00h]
0x140055af9  test    eax, eax
0x140055afb  jnz     short loc_140055B02
0x140055afd  cmp     [rbp+57h+var_D0], eax
0x140055b00  jnz     short loc_140055B39
0x140055b02  test    dil, 4
0x140055b06  jz      short loc_140055B39
0x140055b08  movaps  xmm0, xmmword ptr cs:byte_1400D14B0
0x140055b0f  lea     rcx, [rbx+rbx*4]
0x140055b13  movaps  xmm1, cs:xmmword_1400D14C0
0x140055b1a  inc     ebx
0x140055b1c  movups  [rbp+rcx*8+57h+var_C0], xmm0
0x140055b21  movsd   xmm0, cs:qword_1400D14D0
0x140055b29  movups  [rbp+rcx*8+57h+var_B0], xmm1
0x140055b2e  movsd   [rbp+rcx*8+57h+var_A0], xmm0
0x140055b34  mov     qword ptr [rbp+rcx*8+57h+var_B0], r14
0x140055b39  lea     rax, ?m_interfaceGroup@RpcManager@@0PEAXEA; void * RpcManager::m_interfaceGroup
0x140055b40  mov     r9d, ebx
0x140055b43  mov     [rsp+110h+var_D8], rax
0x140055b48  lea     r8, [rbp+57h+var_C0]
0x140055b4c  lea     rax, ?IdleCallback@DemandStart@@SAXPEAX0K@Z; DemandStart::IdleCallback(void *,void *,ulong)
0x140055b53  mov     [rsp+110h+pcbData], 0
0x140055b5c  mov     [rsp+110h+pvData], rax
0x140055b61  lea     rcx, ?m_rpcInterface@RpcManager@@0PAURPC_INTERFACE_TEMPLATEW@@A; RPC_INTERFACE_TEMPLATEW near * RpcManager::m_rpcInterface
0x140055b68  mov     eax, cs:?m_timeout@RpcManager@@0KA; ulong RpcManager::m_timeout
0x140055b6e  mov     edx, r15d
0x140055b71  mov     dword ptr [rsp+110h+pdwType], eax
0x140055b75  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x140055b7c  nop     dword ptr [rax+rax+00h]
0x140055b81  mov     ebx, eax
0x140055b83  mov     r15d, 80070000h
0x140055b89  test    eax, eax
0x140055b8b  jle     short loc_140055B93
0x140055b8d  movzx   ebx, ax
0x140055b90  or      ebx, r15d
0x140055b93  mov     rcx, r14
0x140055b96  call    DllFreeSplStr
0x140055b9b  test    ebx, ebx
0x140055b9d  js      loc_140055C2D
0x140055ba3  mov     r8, cs:?m_interfaceGroup@RpcManager@@0PEAXEA; void * RpcManager::m_interfaceGroup
0x140055baa  lea     rdi, aRpcmanagerRegi; "RpcManager::RegisterRpc"
0x140055bb1  mov     rcx, rdi; char *
0x140055bb4  lea     rdx, aRegisteredRpcI; "Registered RPC interface group 0x%p"
0x140055bbb  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140055bc0  xor     esi, esi
0x140055bc2  cmp     esi, 5
0x140055bc5  jge     short loc_140055C43
0x140055bc7  mov     rcx, cs:?m_interfaceGroup@RpcManager@@0PEAXEA; void * RpcManager::m_interfaceGroup
0x140055bce  call    cs:__imp_RpcServerInterfaceGroupActivate
0x140055bd5  nop     dword ptr [rax+rax+00h]
0x140055bda  mov     ebx, eax
0x140055bdc  test    eax, eax
0x140055bde  jle     short loc_140055BE6
0x140055be0  movzx   ebx, ax
0x140055be3  or      ebx, r15d
0x140055be6  mov     rcx, rdi; char *
0x140055be9  cmp     ebx, 800706CCh
0x140055bef  jnz     short loc_140055C12
0x140055bf1  lea     rdx, aWaitingForPrev_0; "Waiting for previous spoooler endpoints"...
0x140055bf8  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140055bfd  mov     ecx, 0BB8h; dwMilliseconds
0x140055c02  call    cs:__imp_Sleep
0x140055c09  nop     dword ptr [rax+rax+00h]
0x140055c0e  inc     esi
0x140055c10  jmp     short loc_140055BC2
0x140055c12  test    ebx, ebx
0x140055c14  jns     short loc_140055C1F
0x140055c16  lea     rdx, aFailedToActiva; "Failed to activate RPC interface group:"...
0x140055c1d  jmp     short loc_140055C3B
0x140055c1f  lea     rdx, aActivatedRpcIn; "Activated RPC interface group"
0x140055c26  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140055c2b  jmp     short loc_140055C43
0x140055c2d  lea     rdx, aFailedToCreate_1; "Failed to create RPC interface group: 0"...
0x140055c34  lea     rcx, aRpcmanagerRegi; "RpcManager::RegisterRpc"
0x140055c3b  mov     r8d, ebx
0x140055c3e  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140055c43  mov     eax, ebx
0x140055c45  mov     rcx, [rbp+57h+var_40]
0x140055c49  xor     rcx, rsp; StackCookie
0x140055c4c  call    __security_check_cookie
0x140055c51  add     rsp, 0E8h
0x140055c58  pop     r15
0x140055c5a  pop     r14
0x140055c5c  pop     rdi
0x140055c5d  pop     rsi
0x140055c5e  pop     rbx
0x140055c5f  pop     rbp
0x140055c60  retn
```
