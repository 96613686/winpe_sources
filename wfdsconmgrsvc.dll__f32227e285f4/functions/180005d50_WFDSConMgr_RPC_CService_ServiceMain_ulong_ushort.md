# WFDSConMgr::RPC::CService::ServiceMain(ulong,ushort * *)

- ea: `0x180005d50`
- end: `0x180006089`
- name: `?ServiceMain@CService@RPC@WFDSConMgr@@QEAAXKPEAPEAG@Z`
- size: `825`
- prototype: `void __fastcall(WFDSConMgr::RPC::CService *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800047e0`

## callees

- `0x180005224`
- `0x1800056dc`
- `0x180005cb4`
- `0x180005d50`
- `0x1800061a0`
- `0x180006348`
- `0x1800063a8`
- `0x180006514`
- `0x18000665c`
- `0x1800066ac`
- `0x180006740`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000600e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000600e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005e3a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006004`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005e3a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006004`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005ddb`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005ddb`

## string_xrefs

- `0x180005e0c`: `RegisterServiceCtrlHandlerExW failed`
- `0x180005e1e`: `onecoreuap\net\wlan\wfdsconmgr\server\src\service.cpp`
- `0x180005e6d`: `onecoreuap\net\wlan\wfdsconmgr\server\src\service.cpp`
- `0x180005f23`: `onecoreuap\net\wlan\wfdsconmgr\server\src\service.cpp`
- `0x180006037`: `onecoreuap\net\wlan\wfdsconmgr\server\src\service.cpp`
- `0x180005e25`: `WFDSConMgr::RPC::CService::ServiceMain`
- `0x180005e74`: `WFDSConMgr::RPC::CService::ServiceMain`
- `0x180005f2a`: `WFDSConMgr::RPC::CService::ServiceMain`
- `0x18000603e`: `WFDSConMgr::RPC::CService::ServiceMain`
- `0x180005e5b`: `SetServiceStatus failed`
- `0x180006025`: `SetServiceStatus failed`

## pseudocode

```c
void __fastcall WFDSConMgr::RPC::CService::ServiceMain(
        WFDSConMgr::RPC::CService *this,
        __int64 a2,
        unsigned __int16 **a3)
{
  WFDSConMgr::RPC::CService *v3; // rbx
  LPSERVICE_STATUS v4; // rdi
  int *v5; // r14
  const WCHAR *v6; // rax
  SERVICE_STATUS_HANDLE v7; // rax
  SERVICE_STATUS_HANDLE *v8; // r15
  char LastError; // al
  char v10; // al
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  int v16; // ecx
  char v17; // al
  __int64 v18; // rax
  const WFDSConMgr::CException *v19; // rbx
  int v20; // ecx
  int *v21; // [rsp+40h] [rbp-58h]
  SERVICE_STATUS_HANDLE *v22; // [rsp+48h] [rbp-50h]
  const WFDSConMgr::CException *v23; // [rsp+50h] [rbp-48h] BYREF
  const std::exception *v24; // [rsp+58h] [rbp-40h] BYREF
  char v25[56]; // [rsp+60h] [rbp-38h] BYREF
  int v27; // [rsp+A8h] [rbp+10h]
  unsigned __int16 **v28; // [rsp+B0h] [rbp+18h] BYREF
  LPSERVICE_STATUS lpServiceStatus; // [rsp+B8h] [rbp+20h]

  v28 = a3;
  v3 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, this);
  }
  v4 = (LPSERVICE_STATUS)((char *)v3 + 184);
  lpServiceStatus = (LPSERVICE_STATUS)((char *)v3 + 184);
  v5 = (int *)((char *)v3 + 188);
  v21 = (int *)((char *)v3 + 188);
  *((_DWORD *)v3 + 47) = 2;
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(WFDSConMgr::Common::c_WFDSConMgrServiceName);
  v7 = RegisterServiceCtrlHandlerExW(v6, WFDSConMgr::RPC::CService::ServiceHandlerCallback, v3);
  v8 = (SERVICE_STATUS_HANDLE *)((char *)v3 + 216);
  v22 = (SERVICE_STATUS_HANDLE *)((char *)v3 + 216);
  *((_QWORD *)v3 + 27) = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    WFDSConMgr::CException::Throw(
      LastError,
      "WFDSConMgr::RPC::CService::ServiceMain",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\service.cpp",
      93,
      L"RegisterServiceCtrlHandlerExW failed",
      v3);
  }
  if ( !SetServiceStatus(v7, (LPSERVICE_STATUS)((char *)v3 + 184)) )
  {
    v10 = GetLastError();
    WFDSConMgr::CException::Throw(
      v10,
      "WFDSConMgr::RPC::CService::ServiceMain",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\service.cpp",
      100,
      L"SetServiceStatus failed",
      v3);
  }
  try
  {
    v11 = std::enable_shared_from_this<WFDSConMgr::RPC::CServiceLifetimeRefCount>::shared_from_this((char *)v3 + 8, v25);
    WFDSConMgr::RPC::CService::StoreInstance(v11);
    WFDSConMgr::RPC::CService::CIdleTimer::Start((WFDSConMgr::RPC::CService *)((char *)v3 + 264));
    WFDSConMgr::RPC::CService::ServiceInit(v3);
    v28 = 0;
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(WFDSConMgr::Common::c_WFDSConMgrServiceName);
    v13 = (*((__int64 (__fastcall **)(unsigned __int16 ***, __int64, _QWORD, void (__fastcall *)(WFDSConMgr::RPC::CService *, unsigned __int8), WFDSConMgr::RPC::CService *, int))s_pSvcsGlobalData
           + 24))(
            &v28,
            v12,
            *((_QWORD *)v3 + 30),
            WFDSConMgr::RPC::CService::ShutdownCallback,
            v3,
            8);
    if ( v13 )
      WFDSConMgr::CException::Throw(
        v13,
        "WFDSConMgr::RPC::CService::ServiceMain",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\service.cpp",
        126,
        L"RegisterStopCallback failed",
        v3);
    v14 = *((_QWORD *)v3 + 29);
    *((_QWORD *)v3 + 29) = v28;
    if ( v14 )
      WFDSConMgr::RPC::UnregisterWaitDeleter::operator()();
  }
  catch ( std::bad_alloc )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, this);
    }
    v27 = 14;
    goto LABEL_14;
  }
  catch ( const std::exception *v24 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v24 + 8LL))(v24);
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_75b4082a698737eb13803f331f4b6971_Traceguids,
        (_DWORD)this,
        v18);
    }
    v27 = 774;
    goto LABEL_14;
  }
  catch ( const WFDSConMgr::CException *v23 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v19 = v23;
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_75b4082a698737eb13803f331f4b6971_Traceguids,
        this,
        *(_DWORD *)v23);
    }
    else
    {
      v19 = v23;
    }
    v20 = *(_DWORD *)v19;
    if ( (*(_DWORD *)v19 & 0x1FFF0000) == 0x70000 )
      v20 = (unsigned __int16)v20;
    LODWORD(v28) = v20;
    v27 = v20;
    if ( !(_DWORD)v28 )
    {
      v3 = this;
      v4 = lpServiceStatus;
      v5 = v21;
      v8 = v22;
      goto LABEL_18;
    }
LABEL_14:
    WFDSConMgr::RPC::CService::CleanupInstance();
    v3 = this;
    WFDSConMgr::RPC::CService::CIdleTimer::Stop((WFDSConMgr::RPC::CService *)((char *)this + 264));
    if ( *((_BYTE *)this + 224) )
      WFDSConMgr::RPC::CService::ShutdownService(this);
    *((_DWORD *)this + 50) = v27;
    v15 = 1066;
    v16 = 1;
    v4 = lpServiceStatus;
    v5 = v21;
    v8 = v22;
LABEL_19:
    *v5 = v16;
    v4->dwWin32ExitCode = v15;
    if ( !SetServiceStatus(*v8, v4) )
    {
      v17 = GetLastError();
      WFDSConMgr::CException::Throw(
        v17,
        "WFDSConMgr::RPC::CService::ServiceMain",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\service.cpp",
        185,
        L"SetServiceStatus failed",
        v3);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, v3);
    }
  }
LABEL_18:
  *((_DWORD *)v3 + 48) = 5;
  v15 = 0;
  v16 = 4;
  goto LABEL_19;
}

```

## disassembly

```asm
0x180005d50  mov     [rsp+arg_10], r8
0x180005d55  mov     [rsp+arg_8], edx
0x180005d59  mov     [rsp+arg_0], rcx
0x180005d5e  push    rbx
0x180005d5f  push    rsi
0x180005d60  push    rdi
0x180005d61  push    r14
0x180005d63  push    r15
0x180005d65  sub     rsp, 70h
0x180005d69  mov     rbx, rcx
0x180005d6c  lea     rsi, WPP_GLOBAL_Control
0x180005d73  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d7a  cmp     rcx, rsi
0x180005d7d  jz      short loc_180005DA3
0x180005d7f  cmp     byte ptr [rcx+19h], 3
0x180005d83  jb      short loc_180005DA3
0x180005d85  test    byte ptr [rcx+1Ch], 1
0x180005d89  jz      short loc_180005DA3
0x180005d8b  mov     edx, 0Ch
0x180005d90  mov     r9, rbx
0x180005d93  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x180005d9a  mov     rcx, [rcx+10h]
0x180005d9e  call    WPP_SF_q
0x180005da3  lea     rdi, [rbx+0B8h]
0x180005daa  mov     [rsp+98h+lpServiceStatus], rdi
0x180005db2  lea     r14, [rdi+4]
0x180005db6  mov     [rsp+98h+var_58], r14
0x180005dbb  mov     dword ptr [r14], 2
0x180005dc2  lea     rcx, ?c_WFDSConMgrServiceName@Common@WFDSConMgr@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const WFDSConMgr::Common::c_WFDSConMgrServiceName
0x180005dc9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180005dce  mov     rcx, rax; lpServiceName
0x180005dd1  mov     r8, rbx; lpContext
0x180005dd4  lea     rdx, ?ServiceHandlerCallback@CService@RPC@WFDSConMgr@@CAKKKPEAX0@Z; lpHandlerProc
0x180005ddb  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180005de1  lea     r15, [rbx+0D8h]
0x180005de8  mov     [rsp+98h+var_50], r15
0x180005ded  mov     [r15], rax
0x180005df0  test    rax, rax
0x180005df3  jnz     short loc_180005E34
0x180005df5  call    cs:__imp_GetLastError
0x180005dfb  test    eax, eax
0x180005dfd  jle     short loc_180005E07
0x180005dff  movzx   eax, ax
0x180005e02  or      eax, 80070000h
0x180005e07  mov     [rsp+98h+var_70], rbx; void *
0x180005e0c  lea     rcx, aRegisterservic; "RegisterServiceCtrlHandlerExW failed"
0x180005e13  mov     [rsp+98h+var_78], rcx; unsigned __int16 *
0x180005e18  mov     r9d, 5Dh ; ']'; char
0x180005e1e  lea     r8, aOnecoreuapNetW_28; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x180005e25  lea     rdx, aWfdsconmgrRpcC; "WFDSConMgr::RPC::CService::ServiceMain"
0x180005e2c  mov     ecx, eax; char
0x180005e2e  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180005e34  mov     rdx, rdi; lpServiceStatus
0x180005e37  mov     rcx, rax; hServiceStatus
0x180005e3a  call    cs:__imp_SetServiceStatus
0x180005e40  test    eax, eax
0x180005e42  jnz     short loc_180005E83
0x180005e44  call    cs:__imp_GetLastError
0x180005e4a  test    eax, eax
0x180005e4c  jle     short loc_180005E56
0x180005e4e  movzx   eax, ax
0x180005e51  or      eax, 80070000h
0x180005e56  mov     [rsp+98h+var_70], rbx; void *
0x180005e5b  lea     rcx, aSetservicestat; "SetServiceStatus failed"
0x180005e62  mov     [rsp+98h+var_78], rcx; unsigned __int16 *
0x180005e67  mov     r9d, 64h ; 'd'; char
0x180005e6d  lea     r8, aOnecoreuapNetW_28; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x180005e74  lea     rdx, aWfdsconmgrRpcC; "WFDSConMgr::RPC::CService::ServiceMain"
0x180005e7b  mov     ecx, eax; char
0x180005e7d  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180005e83  lea     rcx, [rbx+8]
0x180005e87  lea     rdx, [rsp+98h+var_38]
0x180005e8c  call    ?shared_from_this@?$enable_shared_from_this@VCServiceLifetimeRefCount@RPC@WFDSConMgr@@@std@@QEAA?AV?$shared_ptr@VCServiceLifetimeRefCount@RPC@WFDSConMgr@@@2@XZ; std::enable_shared_from_this<WFDSConMgr::RPC::CServiceLifetimeRefCount>::shared_from_this(void)
0x180005e91  mov     rcx, rax
0x180005e94  call    ?StoreInstance@CService@RPC@WFDSConMgr@@CAXV?$shared_ptr@VCService@RPC@WFDSConMgr@@@std@@@Z; WFDSConMgr::RPC::CService::StoreInstance(std::shared_ptr<WFDSConMgr::RPC::CService>)
0x180005e99  lea     rcx, [rbx+108h]; this
0x180005ea0  call    ?Start@CIdleTimer@CService@RPC@WFDSConMgr@@QEAAXXZ; WFDSConMgr::RPC::CService::CIdleTimer::Start(void)
0x180005ea5  mov     rcx, rbx; this
0x180005ea8  call    ?ServiceInit@CService@RPC@WFDSConMgr@@AEAAXXZ; WFDSConMgr::RPC::CService::ServiceInit(void)
0x180005ead  mov     [rsp+98h+arg_10], 0
0x180005eb9  lea     rcx, ?c_WFDSConMgrServiceName@Common@WFDSConMgr@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const WFDSConMgr::Common::c_WFDSConMgrServiceName
0x180005ec0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180005ec5  mov     rdx, rax
0x180005ec8  mov     rax, cs:?s_pSvcsGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * s_pSvcsGlobalData
0x180005ecf  mov     dword ptr [rsp+98h+var_70], 8
0x180005ed7  mov     [rsp+98h+var_78], rbx
0x180005edc  lea     r9, ?ShutdownCallback@CService@RPC@WFDSConMgr@@CAXPEAXE@Z; WFDSConMgr::RPC::CService::ShutdownCallback(void *,uchar)
0x180005ee3  mov     r8, [rbx+0F0h]
0x180005eea  lea     rcx, [rsp+98h+arg_10]
0x180005ef2  mov     rax, [rax+0C0h]
0x180005ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005efe  test    eax, eax
0x180005f00  jz      short loc_180005F38
0x180005f02  jle     short loc_180005F0C
0x180005f04  movzx   eax, ax
0x180005f07  or      eax, 80070000h
0x180005f0c  mov     [rsp+98h+var_70], rbx; void *
0x180005f11  lea     rcx, aRegisterstopca; "RegisterStopCallback failed"
0x180005f18  mov     [rsp+98h+var_78], rcx; unsigned __int16 *
0x180005f1d  mov     r9d, 7Eh ; '~'; char
0x180005f23  lea     r8, aOnecoreuapNetW_28; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x180005f2a  lea     rdx, aWfdsconmgrRpcC; "WFDSConMgr::RPC::CService::ServiceMain"
0x180005f31  mov     ecx, eax; char
0x180005f33  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180005f38  mov     rdx, [rbx+0E8h]
0x180005f3f  mov     rax, [rsp+98h+arg_10]
0x180005f47  mov     [rbx+0E8h], rax
0x180005f4e  test    rdx, rdx
0x180005f51  jz      short loc_180005F59
0x180005f53  call    ??RUnregisterWaitDeleter@RPC@WFDSConMgr@@QEAAXPEAX@Z; WFDSConMgr::RPC::UnregisterWaitDeleter::operator()(void *)
0x180005f58  nop
0x180005f59  jmp     loc_180005FE9
0x180005f5e  jmp     short loc_180005F6C
0x180005f60  jmp     short loc_180005F6C
0x180005f62  cmp     dword ptr [rsp+98h+arg_10], 0
0x180005f6a  jz      short loc_180005FC8
0x180005f6c  call    ?CleanupInstance@CService@RPC@WFDSConMgr@@CAXXZ; WFDSConMgr::RPC::CService::CleanupInstance(void)
0x180005f71  mov     rbx, [rsp+98h+arg_0]
0x180005f79  lea     rcx, [rbx+108h]; this
0x180005f80  call    ?Stop@CIdleTimer@CService@RPC@WFDSConMgr@@QEAAXXZ; WFDSConMgr::RPC::CService::CIdleTimer::Stop(void)
0x180005f85  cmp     byte ptr [rbx+0E0h], 0
0x180005f8c  jz      short loc_180005F96
0x180005f8e  mov     rcx, rbx; this
0x180005f91  call    ?ShutdownService@CService@RPC@WFDSConMgr@@QEAAXXZ; WFDSConMgr::RPC::CService::ShutdownService(void)
0x180005f96  mov     eax, [rsp+98h+arg_8]
0x180005f9d  mov     [rbx+0C8h], eax
0x180005fa3  mov     eax, 42Ah
0x180005fa8  mov     ecx, 1
0x180005fad  lea     rsi, WPP_GLOBAL_Control
0x180005fb4  mov     rdi, [rsp+98h+lpServiceStatus]
0x180005fbc  mov     r14, [rsp+98h+var_58]
0x180005fc1  mov     r15, [rsp+98h+var_50]
0x180005fc6  jmp     short loc_180005FF8
0x180005fc8  lea     rsi, WPP_GLOBAL_Control
0x180005fcf  mov     rbx, [rsp+98h+arg_0]
0x180005fd7  mov     rdi, [rsp+98h+lpServiceStatus]
0x180005fdf  mov     r14, [rsp+98h+var_58]
0x180005fe4  mov     r15, [rsp+98h+var_50]
0x180005fe9  mov     dword ptr [rbx+0C0h], 5
0x180005ff3  xor     eax, eax
0x180005ff5  lea     ecx, [rax+4]
0x180005ff8  mov     [r14], ecx
0x180005ffb  mov     [rdi+0Ch], eax
0x180005ffe  mov     rdx, rdi; lpServiceStatus
0x180006001  mov     rcx, [r15]; hServiceStatus
0x180006004  call    cs:__imp_SetServiceStatus
0x18000600a  test    eax, eax
0x18000600c  jnz     short loc_18000604D
0x18000600e  call    cs:__imp_GetLastError
0x180006014  test    eax, eax
0x180006016  jle     short loc_180006020
0x180006018  movzx   eax, ax
0x18000601b  or      eax, 80070000h
0x180006020  mov     [rsp+98h+var_70], rbx; void *
0x180006025  lea     rcx, aSetservicestat; "SetServiceStatus failed"
0x18000602c  mov     [rsp+98h+var_78], rcx; unsigned __int16 *
0x180006031  mov     r9d, 0B9h; char
0x180006037  lea     r8, aOnecoreuapNetW_28; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x18000603e  lea     rdx, aWfdsconmgrRpcC; "WFDSConMgr::RPC::CService::ServiceMain"
0x180006045  mov     ecx, eax; char
0x180006047  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18000604d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006054  cmp     rcx, rsi
0x180006057  jz      short loc_18000607D
0x180006059  cmp     byte ptr [rcx+19h], 3
0x18000605d  jb      short loc_18000607D
0x18000605f  test    byte ptr [rcx+1Ch], 1
0x180006063  jz      short loc_18000607D
0x180006065  mov     edx, 10h
0x18000606a  mov     r9, rbx
0x18000606d  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x180006074  mov     rcx, [rcx+10h]
0x180006078  call    WPP_SF_q
0x18000607d  add     rsp, 70h
0x180006081  pop     r15
0x180006083  pop     r14
0x180006085  pop     rdi
0x180006086  pop     rsi
0x180006087  pop     rbx
0x180006088  retn
```
