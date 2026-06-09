# ServerBFEHandler::CleanupIPsecPolicy(void)

- ea: `0x18003b62c`
- end: `0x18003ba01`
- name: `?CleanupIPsecPolicy@ServerBFEHandler@@SAKXZ`
- size: `981`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006e90`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18002d070`
- `0x18002e6f4`
- `0x18003b62c`
- `0x18003ba08`
- `0x1800400a8`
- `0x180074cc8`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x180077546`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x18003b741`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x18003b7b1`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x18003b821`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x18003b891`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x18003b741`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x18003b7b1`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x18003b821`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x18003b891`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b93d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b93d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b92f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b92f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b98a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b98a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b910`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b910`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b956`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b956`

## string_xrefs

- `0x18003b75f`: `FwpmIPsecTunnelDeleteByKey V4 failed: %u`
- `0x18003b8af`: `FwpmIPsecTunnelDeleteByKey V4 failed: %u`
- `0x18003b7cf`: `FwpmIPsecTunnelDeleteByKey V6 failed: %u`
- `0x18003b83f`: `FwpmIPsecTunnelDeleteByKey V6 failed: %u`

## pseudocode

```c
__int64 ServerBFEHandler::CleanupIPsecPolicy(void)
{
  HANDLE v0; // rbx
  DWORD v1; // eax
  DWORD v2; // eax
  DWORD v3; // eax
  DWORD v4; // eax
  HANDLE ProcessHeap; // rax
  struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *v6; // rbx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  unsigned int v10; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD Buf2[2]; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE engineHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+48h] [rbp-B8h]
  __int128 v15; // [rsp+58h] [rbp-A8h]
  __int64 v16; // [rsp+68h] [rbp-98h]
  int v17; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+74h] [rbp-8Ch]
  int v19; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v20[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
  }
  v10 = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v13,
      L"ServerBFEHandler::CleanupIPsecPolicy",
      &v10,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  engineHandle = 0;
  Buf2[0] = 0;
  Buf2[1] = 0;
  BFEHandler::GetBfeHandle(&engineHandle);
  v0 = engineHandle;
  if ( engineHandle )
  {
    if ( memcmp_0(&ServerBFEHandler::serverV4TunnelCtxt, Buf2, 0x10u) )
    {
      v1 = FwpmIPsecTunnelDeleteByKey0(v0, &ServerBFEHandler::serverV4TunnelCtxt);
      v10 = v1;
      if ( v1 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v19) = 0;
          FormatRRASErrorString(&v19, L"FwpmIPsecTunnelDeleteByKey V4 failed: %u", v1);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v19);
        }
      }
    }
    if ( memcmp_0(&ServerBFEHandler::serverV6TunnelCtxt, Buf2, 0x10u) )
    {
      v2 = FwpmIPsecTunnelDeleteByKey0(v0, &ServerBFEHandler::serverV6TunnelCtxt);
      v10 = v2;
      if ( v2 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v19) = 0;
          FormatRRASErrorString(&v19, L"FwpmIPsecTunnelDeleteByKey V6 failed: %u", v2);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v19);
        }
      }
    }
    if ( memcmp_0(&ServerBFEHandler::serverMMv6TunnelCtxt, Buf2, 0x10u) )
    {
      v3 = FwpmIPsecTunnelDeleteByKey0(v0, &ServerBFEHandler::serverMMv6TunnelCtxt);
      v10 = v3;
      if ( v3 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v19) = 0;
          FormatRRASErrorString(&v19, L"FwpmIPsecTunnelDeleteByKey V6 failed: %u", v3);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v19);
        }
      }
    }
    if ( memcmp_0(&ServerBFEHandler::serverMMv4TunnelCtxt, Buf2, 0x10u) )
    {
      v4 = FwpmIPsecTunnelDeleteByKey0(v0, &ServerBFEHandler::serverMMv4TunnelCtxt);
      v10 = v4;
      if ( v4 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v19) = 0;
          FormatRRASErrorString(&v19, L"FwpmIPsecTunnelDeleteByKey V4 failed: %u", v4);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v19);
        }
      }
    }
    ServerBFEHandler::serverV4TunnelCtxt = 0;
    ServerBFEHandler::serverV6TunnelCtxt = 0;
    ServerBFEHandler::serverMMv4TunnelCtxt = 0;
    ServerBFEHandler::serverMMv6TunnelCtxt = 0;
    if ( ServerBFEHandler::csInitialized )
    {
      EnterCriticalSection(&ServerBFEHandler::csInterfacePolicyMapping);
      while ( 1 )
      {
        v6 = ServerBFEHandler::interfacePolicyMapping;
        if ( !ServerBFEHandler::interfacePolicyMapping )
          break;
        ServerBFEHandler::interfacePolicyMapping = *(struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP **)ServerBFEHandler::interfacePolicyMapping;
        ServerBFEHandler::RemovePolicyForMap(v6);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v6);
      }
      LeaveCriticalSection(&ServerBFEHandler::csInterfacePolicyMapping);
    }
  }
  BFEHandler::CloseBfeHandle();
  if ( ServerBFEHandler::globalPolicyObjectCreated )
  {
    ServerBFEHandler::globalPolicyObjectCreated = 0;
    ServerBFEHandler::FreeGlobalPolicyObjects();
  }
  if ( ServerBFEHandler::csInitialized )
  {
    DeleteCriticalSection(&ServerBFEHandler::csInterfacePolicyMapping);
    ServerBFEHandler::csInitialized = 0;
  }
  FreeIkev2ConfigParams(v7, &ServerBFEHandler::serverConfigParams);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v10);
  }
  v8 = v10;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v8;
}

```

## disassembly

```asm
0x18003b62c  push    rbp
0x18003b62e  push    rbx
0x18003b62f  push    rsi
0x18003b630  push    rdi
0x18003b631  push    r13
0x18003b633  lea     rbp, [rsp-790h]
0x18003b63b  sub     rsp, 890h
0x18003b642  mov     rax, cs:__security_cookie
0x18003b649  xor     rax, rsp
0x18003b64c  mov     [rbp+7B0h+var_30], rax
0x18003b653  lea     rsi, WPP_GLOBAL_Control
0x18003b65a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b661  cmp     rcx, rsi
0x18003b664  jz      short loc_18003B687
0x18003b666  test    byte ptr [rcx+1Ch], 1
0x18003b66a  jz      short loc_18003B687
0x18003b66c  cmp     byte ptr [rcx+19h], 6
0x18003b670  jb      short loc_18003B687
0x18003b672  mov     edx, 2Dh ; '-'
0x18003b677  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003b67e  mov     rcx, [rcx+10h]
0x18003b682  call    WPP_SF_
0x18003b687  xor     edi, edi
0x18003b689  mov     [rsp+8B0h+var_890], edi
0x18003b68d  mov     [rbp+7B0h+var_830], edi
0x18003b690  xor     edx, edx; Val
0x18003b692  mov     r8d, 7FCh; Size
0x18003b698  lea     rcx, [rbp+7B0h+var_82C]; void *
0x18003b69c  call    memset_0
0x18003b6a1  xorps   xmm0, xmm0
0x18003b6a4  movdqu  [rsp+8B0h+var_868], xmm0
0x18003b6aa  mov     [rsp+8B0h+var_870], rdi
0x18003b6af  xorps   xmm1, xmm1
0x18003b6b2  movdqu  [rsp+8B0h+var_858], xmm1
0x18003b6b8  mov     [rsp+8B0h+var_848], rdi
0x18003b6bd  mov     [rsp+8B0h+var_840], 0FFFFFFFFh
0x18003b6c5  mov     [rsp+8B0h+var_83C], edi
0x18003b6c9  test    cs:byte_1800AA941, 8
0x18003b6d0  jz      short loc_18003B6EF
0x18003b6d2  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18003b6d9  lea     r8, [rsp+8B0h+var_890]; unsigned int *
0x18003b6de  lea     rdx, aServerbfehandl_11; "ServerBFEHandler::CleanupIPsecPolicy"
0x18003b6e5  lea     rcx, [rsp+8B0h+var_870]; this
0x18003b6ea  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003b6ef  mov     [rsp+8B0h+engineHandle], rdi
0x18003b6f4  mov     [rsp+8B0h+Buf2], rdi
0x18003b6f9  mov     [rsp+8B0h+var_880], rdi
0x18003b6fe  lea     rcx, [rsp+8B0h+engineHandle]; void **
0x18003b703  call    ?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z; BFEHandler::GetBfeHandle(void * *)
0x18003b708  mov     rbx, [rsp+8B0h+engineHandle]
0x18003b70d  test    rbx, rbx
0x18003b710  jz      loc_18003B963
0x18003b716  mov     r13d, 10h
0x18003b71c  mov     r8d, r13d; Size
0x18003b71f  lea     rdx, [rsp+8B0h+Buf2]; Buf2
0x18003b724  lea     rcx, ?serverV4TunnelCtxt@ServerBFEHandler@@2U_GUID@@A; Buf1
0x18003b72b  call    memcmp_0
0x18003b730  mov     sil, 4
0x18003b733  test    eax, eax
0x18003b735  jz      short loc_18003B78F
0x18003b737  lea     rdx, ?serverV4TunnelCtxt@ServerBFEHandler@@2U_GUID@@A; key
0x18003b73e  mov     rcx, rbx; engineHandle
0x18003b741  call    cs:__imp_FwpmIPsecTunnelDeleteByKey0
0x18003b747  mov     r8d, eax
0x18003b74a  mov     [rsp+8B0h+var_890], eax
0x18003b74e  test    eax, eax
0x18003b750  jz      short loc_18003B78F
0x18003b752  test    cs:byte_1800AA941, sil
0x18003b759  jz      short loc_18003B78F
0x18003b75b  mov     word ptr [rbp+7B0h+var_830], di
0x18003b75f  lea     rdx, aFwpmipsectunne_1; "FwpmIPsecTunnelDeleteByKey V4 failed: %"...
0x18003b766  lea     rcx, [rbp+7B0h+var_830]
0x18003b76a  call    FormatRRASErrorString
0x18003b76f  test    cs:byte_1800AA941, sil
0x18003b776  jz      short loc_18003B78F
0x18003b778  lea     r8, [rbp+7B0h+var_830]
0x18003b77c  lea     rdx, RasVpnIkeTraceError
0x18003b783  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003b78a  call    McTemplateU0z_EventWriteTransfer
0x18003b78f  mov     r8, r13; Size
0x18003b792  lea     rdx, [rsp+8B0h+Buf2]; Buf2
0x18003b797  lea     rcx, ?serverV6TunnelCtxt@ServerBFEHandler@@2U_GUID@@A; Buf1
0x18003b79e  call    memcmp_0
0x18003b7a3  test    eax, eax
0x18003b7a5  jz      short loc_18003B7FF
0x18003b7a7  lea     rdx, ?serverV6TunnelCtxt@ServerBFEHandler@@2U_GUID@@A; key
0x18003b7ae  mov     rcx, rbx; engineHandle
0x18003b7b1  call    cs:__imp_FwpmIPsecTunnelDeleteByKey0
0x18003b7b7  mov     r8d, eax
0x18003b7ba  mov     [rsp+8B0h+var_890], eax
0x18003b7be  test    eax, eax
0x18003b7c0  jz      short loc_18003B7FF
0x18003b7c2  test    cs:byte_1800AA941, sil
0x18003b7c9  jz      short loc_18003B7FF
0x18003b7cb  mov     word ptr [rbp+7B0h+var_830], di
0x18003b7cf  lea     rdx, aFwpmipsectunne_4; "FwpmIPsecTunnelDeleteByKey V6 failed: %"...
0x18003b7d6  lea     rcx, [rbp+7B0h+var_830]
0x18003b7da  call    FormatRRASErrorString
0x18003b7df  test    cs:byte_1800AA941, sil
0x18003b7e6  jz      short loc_18003B7FF
0x18003b7e8  lea     r8, [rbp+7B0h+var_830]
0x18003b7ec  lea     rdx, RasVpnIkeTraceError
0x18003b7f3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003b7fa  call    McTemplateU0z_EventWriteTransfer
0x18003b7ff  mov     r8, r13; Size
0x18003b802  lea     rdx, [rsp+8B0h+Buf2]; Buf2
0x18003b807  lea     rcx, ?serverMMv6TunnelCtxt@ServerBFEHandler@@2U_GUID@@A; Buf1
0x18003b80e  call    memcmp_0
0x18003b813  test    eax, eax
0x18003b815  jz      short loc_18003B86F
0x18003b817  lea     rdx, ?serverMMv6TunnelCtxt@ServerBFEHandler@@2U_GUID@@A; key
0x18003b81e  mov     rcx, rbx; engineHandle
0x18003b821  call    cs:__imp_FwpmIPsecTunnelDeleteByKey0
0x18003b827  mov     r8d, eax
0x18003b82a  mov     [rsp+8B0h+var_890], eax
0x18003b82e  test    eax, eax
0x18003b830  jz      short loc_18003B86F
0x18003b832  test    cs:byte_1800AA941, sil
0x18003b839  jz      short loc_18003B86F
0x18003b83b  mov     word ptr [rbp+7B0h+var_830], di
0x18003b83f  lea     rdx, aFwpmipsectunne_4; "FwpmIPsecTunnelDeleteByKey V6 failed: %"...
0x18003b846  lea     rcx, [rbp+7B0h+var_830]
0x18003b84a  call    FormatRRASErrorString
0x18003b84f  test    cs:byte_1800AA941, sil
0x18003b856  jz      short loc_18003B86F
0x18003b858  lea     r8, [rbp+7B0h+var_830]
0x18003b85c  lea     rdx, RasVpnIkeTraceError
0x18003b863  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003b86a  call    McTemplateU0z_EventWriteTransfer
0x18003b86f  mov     r8, r13; Size
0x18003b872  lea     rdx, [rsp+8B0h+Buf2]; Buf2
0x18003b877  lea     rcx, ?serverMMv4TunnelCtxt@ServerBFEHandler@@2U_GUID@@A; Buf1
0x18003b87e  call    memcmp_0
0x18003b883  test    eax, eax
0x18003b885  jz      short loc_18003B8DF
0x18003b887  lea     rdx, ?serverMMv4TunnelCtxt@ServerBFEHandler@@2U_GUID@@A; key
0x18003b88e  mov     rcx, rbx; engineHandle
0x18003b891  call    cs:__imp_FwpmIPsecTunnelDeleteByKey0
0x18003b897  mov     r8d, eax
0x18003b89a  mov     [rsp+8B0h+var_890], eax
0x18003b89e  test    eax, eax
0x18003b8a0  jz      short loc_18003B8DF
0x18003b8a2  test    cs:byte_1800AA941, sil
0x18003b8a9  jz      short loc_18003B8DF
0x18003b8ab  mov     word ptr [rbp+7B0h+var_830], di
0x18003b8af  lea     rdx, aFwpmipsectunne_1; "FwpmIPsecTunnelDeleteByKey V4 failed: %"...
0x18003b8b6  lea     rcx, [rbp+7B0h+var_830]
0x18003b8ba  call    FormatRRASErrorString
0x18003b8bf  test    cs:byte_1800AA941, sil
0x18003b8c6  jz      short loc_18003B8DF
0x18003b8c8  lea     r8, [rbp+7B0h+var_830]
0x18003b8cc  lea     rdx, RasVpnIkeTraceError
0x18003b8d3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003b8da  call    McTemplateU0z_EventWriteTransfer
0x18003b8df  xorps   xmm0, xmm0
0x18003b8e2  movups  xmmword ptr cs:?serverV4TunnelCtxt@ServerBFEHandler@@2U_GUID@@A.Data1, xmm0; _GUID ServerBFEHandler::serverV4TunnelCtxt ...
0x18003b8e9  xorps   xmm1, xmm1
0x18003b8ec  movups  xmmword ptr cs:?serverV6TunnelCtxt@ServerBFEHandler@@2U_GUID@@A.Data1, xmm1; _GUID ServerBFEHandler::serverV6TunnelCtxt ...
0x18003b8f3  movups  xmmword ptr cs:?serverMMv4TunnelCtxt@ServerBFEHandler@@2U_GUID@@A.Data1, xmm0; _GUID ServerBFEHandler::serverMMv4TunnelCtxt ...
0x18003b8fa  movups  xmmword ptr cs:?serverMMv6TunnelCtxt@ServerBFEHandler@@2U_GUID@@A.Data1, xmm1; _GUID ServerBFEHandler::serverMMv6TunnelCtxt ...
0x18003b901  cmp     cs:?csInitialized@ServerBFEHandler@@1HA, edi; int ServerBFEHandler::csInitialized
0x18003b907  jz      short loc_18003B95C
0x18003b909  lea     rcx, ?csInterfacePolicyMapping@ServerBFEHandler@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003b910  call    cs:__imp_EnterCriticalSection
0x18003b916  jmp     short loc_18003B943
0x18003b918  mov     rax, [rbx]
0x18003b91b  mov     cs:?interfacePolicyMapping@ServerBFEHandler@@1PEAU_VPNIKE_INTERFACE_POLICY_MAP@1@EA, rax; ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP * ServerBFEHandler::interfacePolicyMapping
0x18003b922  mov     rcx, rbx; struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *
0x18003b925  call    ?RemovePolicyForMap@ServerBFEHandler@@KAKPEAU_VPNIKE_INTERFACE_POLICY_MAP@1@@Z; ServerBFEHandler::RemovePolicyForMap(ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *)
0x18003b92a  test    rbx, rbx
0x18003b92d  jz      short loc_18003B943
0x18003b92f  call    cs:__imp_GetProcessHeap
0x18003b935  mov     rcx, rax; hHeap
0x18003b938  mov     r8, rbx; lpMem
0x18003b93b  xor     edx, edx; dwFlags
0x18003b93d  call    cs:__imp_HeapFree
0x18003b943  mov     rbx, cs:?interfacePolicyMapping@ServerBFEHandler@@1PEAU_VPNIKE_INTERFACE_POLICY_MAP@1@EA; ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP * ServerBFEHandler::interfacePolicyMapping
0x18003b94a  test    rbx, rbx
0x18003b94d  jnz     short loc_18003B918
0x18003b94f  lea     rcx, ?csInterfacePolicyMapping@ServerBFEHandler@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003b956  call    cs:__imp_LeaveCriticalSection
0x18003b95c  lea     rsi, WPP_GLOBAL_Control
0x18003b963  call    ?CloseBfeHandle@BFEHandler@@SAKXZ; BFEHandler::CloseBfeHandle(void)
0x18003b968  cmp     cs:?globalPolicyObjectCreated@ServerBFEHandler@@1HA, edi; int ServerBFEHandler::globalPolicyObjectCreated
0x18003b96e  jz      short loc_18003B97B
0x18003b970  mov     cs:?globalPolicyObjectCreated@ServerBFEHandler@@1HA, edi; int ServerBFEHandler::globalPolicyObjectCreated
0x18003b976  call    ?FreeGlobalPolicyObjects@ServerBFEHandler@@KAXXZ; ServerBFEHandler::FreeGlobalPolicyObjects(void)
0x18003b97b  cmp     cs:?csInitialized@ServerBFEHandler@@1HA, edi; int ServerBFEHandler::csInitialized
0x18003b981  jz      short loc_18003B996
0x18003b983  lea     rcx, ?csInterfacePolicyMapping@ServerBFEHandler@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003b98a  call    cs:__imp_DeleteCriticalSection
0x18003b990  mov     cs:?csInitialized@ServerBFEHandler@@1HA, edi; int ServerBFEHandler::csInitialized
0x18003b996  lea     rdx, ?serverConfigParams@ServerBFEHandler@@1U_IKEV2_TUNNEL_CONFIG_PARAMS_4@@A; _IKEV2_TUNNEL_CONFIG_PARAMS_4 ServerBFEHandler::serverConfigParams
0x18003b99d  call    FreeIkev2ConfigParams
0x18003b9a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b9a9  cmp     rcx, rsi
0x18003b9ac  jz      short loc_18003B9D4
0x18003b9ae  test    byte ptr [rcx+1Ch], 1
0x18003b9b2  jz      short loc_18003B9D4
0x18003b9b4  cmp     byte ptr [rcx+19h], 6
0x18003b9b8  jb      short loc_18003B9D4
0x18003b9ba  mov     edx, 2Eh ; '.'
0x18003b9bf  mov     r9d, [rsp+8B0h+var_890]
0x18003b9c4  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003b9cb  mov     rcx, [rcx+10h]
0x18003b9cf  call    WPP_SF_d
0x18003b9d4  mov     ebx, [rsp+8B0h+var_890]
0x18003b9d8  lea     rcx, [rsp+8B0h+var_870]; this
0x18003b9dd  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003b9e2  mov     eax, ebx
0x18003b9e4  mov     rcx, [rbp+7B0h+var_30]
0x18003b9eb  xor     rcx, rsp; StackCookie
0x18003b9ee  call    __security_check_cookie
0x18003b9f3  add     rsp, 890h
0x18003b9fa  pop     r13
0x18003b9fc  pop     rdi
0x18003b9fd  pop     rsi
0x18003b9fe  pop     rbx
0x18003b9ff  pop     rbp
0x18003ba00  retn
```
