# TLoad64BitDllsMgr::StopLdrRPCServer(void)

- ea: `0x1400083f4`
- end: `0x140008523`
- name: `?StopLdrRPCServer@TLoad64BitDllsMgr@@QEAAKXZ`
- size: `303`
- prototype: `unsigned int __fastcall(TLoad64BitDllsMgr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007dac`

## callees

- `0x1400083f4`
- `0x1400085d8`
- `0x1400086e0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400084bd`
- `KERNEL32!FreeLibrary` at `0x1400084bd`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x140008437`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x140008437`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x1400084d1`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x1400084d1`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140008485`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140008485`

## string_xrefs

- `0x140008403`: `TLoad64BitDllsMgr::StopLdrRPCServer`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::StopLdrRPCServer(TLoad64BitDllsMgr *this)
{
  void *v1; // rdi
  unsigned int v2; // ebx
  unsigned int v3; // eax
  __int64 *v4; // rdx
  HRESULT v5; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // rbx
  DWORD v7; // ecx

  SplWow64Telemetry::WriteDbgTraceInfo("TLoad64BitDllsMgr::StopLdrRPCServer", L"Entered..");
  v1 = TLoad64BitDllsMgr::m_interfaceGroup;
  v2 = 0;
  if ( TLoad64BitDllsMgr::m_interfaceGroup )
  {
    TLoad64BitDllsMgr::m_interfaceGroup = 0;
    v3 = RpcServerInterfaceGroupDeactivate(v1, 0);
    v2 = v3;
    if ( v3 )
    {
      if ( v3 == 1723 )
        SplWow64Telemetry::WriteDbgTraceError(
          "TLoad64BitDllsMgr::StopLdrRPCServer",
          L"RPC interface has outstanding client activity. Don't shutdown");
      else
        SplWow64Telemetry::WriteDbgTraceError(
          "TLoad64BitDllsMgr::StopLdrRPCServer",
          L"Failed to deactivate RPC interface group: %d",
          v3);
    }
    else
    {
      if ( sandbox::g_pfnDllCanUnloadNow )
      {
        SplWow64Telemetry::WriteDbgTraceInfo("TLoad64BitDllsMgr::StopLdrRPCServer", L"Unloading isolation host");
        v4 = off_140021278;
        v5 = 0;
        for ( i = off_140021270; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 && !v5; ++i )
        {
          if ( *i )
          {
            v7 = *((_DWORD *)*i + 10);
            if ( v7 )
            {
              v5 = CoRevokeClassObject(v7);
              v4 = off_140021278;
            }
          }
        }
        if ( sandbox::g_hInprocSandbox )
        {
          sandbox::g_pfnCreate = 0;
          sandbox::g_pfnDllCanUnloadNow = 0;
          FreeLibrary(sandbox::g_hInprocSandbox);
          sandbox::g_hInprocSandbox = 0;
        }
      }
      v2 = RpcServerInterfaceGroupClose(v1);
      SplWow64Telemetry::WriteDbgTraceInfo("TLoad64BitDllsMgr::StopLdrRPCServer", L"Unregistered RPC interface group");
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400083f4  mov     [rsp+arg_0], rbx
0x1400083f9  mov     [rsp+arg_8], rbp
0x1400083fe  push    rdi
0x1400083ff  sub     rsp, 20h
0x140008403  lea     rbp, aTload64bitdlls_3; "TLoad64BitDllsMgr::StopLdrRPCServer"
0x14000840a  mov     rcx, rbp; char *
0x14000840d  lea     rdx, aEntered; "Entered.."
0x140008414  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140008419  mov     rdi, cs:?m_interfaceGroup@TLoad64BitDllsMgr@@0PEAXEA; void * TLoad64BitDllsMgr::m_interfaceGroup
0x140008420  xor     ebx, ebx
0x140008422  test    rdi, rdi
0x140008425  jz      loc_140008511
0x14000842b  xor     edx, edx
0x14000842d  mov     cs:?m_interfaceGroup@TLoad64BitDllsMgr@@0PEAXEA, rbx; void * TLoad64BitDllsMgr::m_interfaceGroup
0x140008434  mov     rcx, rdi
0x140008437  call    cs:__imp_RpcServerInterfaceGroupDeactivate
0x14000843d  mov     ebx, eax
0x14000843f  test    eax, eax
0x140008441  jnz     loc_1400084EA
0x140008447  cmp     cs:?g_pfnDllCanUnloadNow@sandbox@@3P6AJXZEA, 0; long (*sandbox::g_pfnDllCanUnloadNow)(void)
0x14000844f  jz      short loc_1400084CE
0x140008451  lea     rdx, aUnloadingIsola; "Unloading isolation host"
0x140008458  mov     rcx, rbp; char *
0x14000845b  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140008460  mov     rdx, cs:off_140021278
0x140008467  xor     eax, eax
0x140008469  mov     rbx, cs:off_140021270
0x140008470  jmp     short loc_140008496
0x140008472  test    eax, eax
0x140008474  jnz     short loc_14000849B
0x140008476  mov     rcx, [rbx]
0x140008479  test    rcx, rcx
0x14000847c  jz      short loc_140008492
0x14000847e  mov     ecx, [rcx+28h]; dwRegister
0x140008481  test    ecx, ecx
0x140008483  jz      short loc_140008492
0x140008485  call    cs:__imp_CoRevokeClassObject
0x14000848b  mov     rdx, cs:off_140021278
0x140008492  add     rbx, 8
0x140008496  cmp     rbx, rdx
0x140008499  jb      short loc_140008472
0x14000849b  mov     rcx, cs:?g_hInprocSandbox@sandbox@@3PEAXEA; hLibModule
0x1400084a2  test    rcx, rcx
0x1400084a5  jz      short loc_1400084CE
0x1400084a7  mov     cs:?g_pfnCreate@sandbox@@3P6AKHPEAPEAUIPrintSandbox@@@ZEA, 0; ulong (*sandbox::g_pfnCreate)(int,IPrintSandbox * *)
0x1400084b2  mov     cs:?g_pfnDllCanUnloadNow@sandbox@@3P6AJXZEA, 0; long (*sandbox::g_pfnDllCanUnloadNow)(void)
0x1400084bd  call    cs:__imp_FreeLibrary
0x1400084c3  mov     cs:?g_hInprocSandbox@sandbox@@3PEAXEA, 0; void * sandbox::g_hInprocSandbox
0x1400084ce  mov     rcx, rdi
0x1400084d1  call    cs:__imp_RpcServerInterfaceGroupClose
0x1400084d7  lea     rdx, aUnregisteredRp; "Unregistered RPC interface group"
0x1400084de  mov     rcx, rbp; char *
0x1400084e1  mov     ebx, eax
0x1400084e3  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400084e8  jmp     short loc_140008511
0x1400084ea  mov     rcx, rbp; char *
0x1400084ed  cmp     eax, 6BBh
0x1400084f2  jnz     short loc_140008502
0x1400084f4  lea     rdx, aRpcInterfaceHa; "RPC interface has outstanding client ac"...
0x1400084fb  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140008500  jmp     short loc_140008511
0x140008502  mov     r8d, eax
0x140008505  lea     rdx, aFailedToDeacti; "Failed to deactivate RPC interface grou"...
0x14000850c  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140008511  mov     rbp, [rsp+28h+arg_8]
0x140008516  mov     eax, ebx
0x140008518  mov     rbx, [rsp+28h+arg_0]
0x14000851d  add     rsp, 20h
0x140008521  pop     rdi
0x140008522  retn
```
