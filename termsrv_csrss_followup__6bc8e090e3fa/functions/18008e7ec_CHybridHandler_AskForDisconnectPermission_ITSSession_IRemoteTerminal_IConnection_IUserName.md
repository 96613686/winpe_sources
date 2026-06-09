# CHybridHandler::AskForDisconnectPermission(ITSSession *,IRemoteTerminal *,IConnection *,IUserName *)

- ea: `0x18008e7ec`
- end: `0x18008eb7a`
- name: `?AskForDisconnectPermission@CHybridHandler@@AEAAJPEAUITSSession@@PEAVIRemoteTerminal@@PEAVIConnection@@PEAUIUserName@@@Z`
- size: `910`
- prototype: `__int64 __fastcall(CHybridHandler *__hidden this, struct ITSSession *, struct IRemoteTerminal *, struct IConnection *, struct IUserName *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008fd70`

## callees

- `0x180009940`
- `0x1800139c0`
- `0x180016558`
- `0x180018e2c`
- `0x180033f60`
- `0x18008e7ec`
- `0x18008f7d0`
- `0x180090340`
- `0x1800ce010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008e9ef`
- `OLEAUT32!__imp_SysAllocString` at `0x18008e9ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18008eb3a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008eb3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008eb10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008eb26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008eb10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008eb26`

## string_xrefs

- `0x18008e8a1`: `0 == SessId failed: 0x%x in %s`
- `0x18008e8c4`: `ptrIncomingTerminal->GetProtocolName failed: 0x%x in %s`
- `0x18008eaf5`: `The incoming connection is from VMBus or HvSocket listener, auto-approving the disconnect.`
- `0x18008e916`: `pIncomingUser->IsConnectedUser failed: 0x%x in %s`
- `0x18008e942`: `pIncomingUser->GetInternetPrincipalStr failed: 0x%x in %s`
- `0x18008e968`: `pIncomingUser->GetInternetProviderStr failed: 0x%x in %s`
- `0x18008e983`: `pIncomingUser->GetUserStr failed: 0x%x in %s`
- `0x18008e9a9`: `pIncomingUser->GetDomainStr failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHybridHandler::AskForDisconnectPermission(
        CHybridHandler *this,
        struct ITSSession *a2,
        struct IRemoteTerminal *a3,
        struct IConnection *a4,
        struct IUserName *a5)
{
  OLECHAR *v7; // rsi
  int RequestDialogObject; // eax
  unsigned int v9; // ebx
  const char *v10; // rdx
  __int64 v11; // rax
  OLECHAR *v12; // rcx
  CHybridHandler *v13; // rcx
  int v14; // eax
  struct ITSSession *v15; // rdx
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // r9
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  int v21; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-B8h] BYREF
  void *v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[80]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[128]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR psz[1024]; // [rsp+130h] [rbp+30h] BYREF

  v19 = 0;
  pv = 0;
  v23 = 0;
  v21 = 0;
  v24[0] = 0;
  v7 = 0;
  v20 = 0;
  RequestDialogObject = (*(__int64 (__fastcall **)(struct ITSSession *, int *))(*(_QWORD *)a2 + 80LL))(a2, &v19);
  v9 = RequestDialogObject;
  if ( RequestDialogObject < 0 )
  {
    v10 = "ptrSession->getId failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v10, (unsigned int)RequestDialogObject, "CHybridHandler::AskForDisconnectPermission");
    goto LABEL_44;
  }
  if ( !v19 )
  {
    v9 = -2147418113;
    _DbgPrintMessage(8, "0 == SessId failed: 0x%x in %s", 2147549183LL, "CHybridHandler::AskForDisconnectPermission");
    goto LABEL_44;
  }
  RequestDialogObject = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, _BYTE *))(*(_QWORD *)a3 + 96LL))(a3, v25);
  v9 = RequestDialogObject;
  if ( RequestDialogObject < 0 )
  {
    v10 = "ptrIncomingTerminal->GetProtocolName failed: 0x%x in %s";
    goto LABEL_3;
  }
  if ( (unsigned int)CHardcodedListenerConfig::ListenerTypeFromProtoName(v25) == 2
    || (unsigned int)CHardcodedListenerConfig::ListenerTypeFromProtoName(v25) == 3 )
  {
    _DbgPrintMessage(4, "The incoming connection is from VMBus or HvSocket listener, auto-approving the disconnect.");
    goto LABEL_44;
  }
  if ( a5 )
  {
    RequestDialogObject = (*(__int64 (__fastcall **)(struct IUserName *, int *))(*(_QWORD *)a5 + 104LL))(a5, &v21);
    v9 = RequestDialogObject;
    if ( RequestDialogObject < 0 )
    {
      v10 = "pIncomingUser->IsConnectedUser failed: 0x%x in %s";
      goto LABEL_3;
    }
    v11 = *(_QWORD *)a5;
    if ( v21 )
    {
      RequestDialogObject = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(v11 + 56))(a5, &pv);
      v9 = RequestDialogObject;
      if ( RequestDialogObject < 0 )
      {
        v10 = "pIncomingUser->GetInternetPrincipalStr failed: 0x%x in %s";
        goto LABEL_3;
      }
      RequestDialogObject = (*(__int64 (__fastcall **)(struct IUserName *, unsigned __int16 **))(*(_QWORD *)a5 + 64LL))(
                              a5,
                              &v23);
      v9 = RequestDialogObject;
      if ( RequestDialogObject < 0 )
      {
        v10 = "pIncomingUser->GetInternetProviderStr failed: 0x%x in %s";
        goto LABEL_3;
      }
    }
    else
    {
      RequestDialogObject = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(v11 + 40))(a5, &pv);
      v9 = RequestDialogObject;
      if ( RequestDialogObject < 0 )
      {
        v10 = "pIncomingUser->GetUserStr failed: 0x%x in %s";
        goto LABEL_3;
      }
      RequestDialogObject = (*(__int64 (__fastcall **)(struct IUserName *, unsigned __int16 **))(*(_QWORD *)a5 + 48LL))(
                              a5,
                              &v23);
      v9 = RequestDialogObject;
      if ( RequestDialogObject < 0 )
      {
        v10 = "pIncomingUser->GetDomainStr failed: 0x%x in %s";
        goto LABEL_3;
      }
    }
    RequestDialogObject = StringCchPrintfW(psz, 0x400u, L"%s\\%s", v23, pv);
    v9 = RequestDialogObject;
    if ( RequestDialogObject < 0 )
    {
      v10 = "StringCchPrintf failed: 0x%x in %s";
      goto LABEL_3;
    }
    v12 = psz;
  }
  else
  {
    v12 = (OLECHAR *)((char *)this + 1704);
  }
  v7 = SysAllocString(v12);
  if ( !v7 )
  {
    v9 = -2147024882;
    goto LABEL_44;
  }
  RequestDialogObject = CHybridHandler::GetRequestDialogObject(v13, v19, v24);
  v9 = RequestDialogObject;
  if ( RequestDialogObject < 0 )
  {
    v10 = "GetRequestDialogObject failed: 0x%x in %s";
    goto LABEL_3;
  }
  RequestDialogObject = (*(__int64 (__fastcall **)(void *, OLECHAR *, int *))(*(_QWORD *)v24[0] + 24LL))(
                          v24[0],
                          v7,
                          &v20);
  v9 = RequestDialogObject;
  if ( RequestDialogObject < 0 )
  {
    v10 = "ptrRequestDialog->ShowBumpDialog failed: 0x%x in %s";
    goto LABEL_3;
  }
  if ( v20 != 1 && v20 != 32000 )
  {
    v14 = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, _BYTE *))(*(_QWORD *)a3 + 152LL))(a3, v26);
    if ( a5 )
    {
      v15 = (struct ITSSession *)pv;
      v16 = v23;
    }
    else
    {
      v16 = (unsigned __int16 *)((char *)this + 1832);
      v15 = (CHybridHandler *)((char *)this + 1832);
    }
    v17 = (unsigned __int16 *)v26;
    if ( v14 < 0 )
      v17 = (unsigned __int16 *)((char *)this + 1832);
    CHybridHandler::LogDeniedEvent(
      (CHybridHandler *)((char *)this + 1832),
      v15,
      (struct IConnection *)v16,
      v17,
      v16,
      (unsigned __int16 *)v15);
    v9 = -2147024891;
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "Target User reject disconnect request");
    _DbgPrintMessage(
      8,
      "IDOK != ulResponse && IDTIMEOUT != ulResponse failed: 0x%x in %s",
      2147942405LL,
      "CHybridHandler::AskForDisconnectPermission");
  }
LABEL_44:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v23 )
    CoTaskMemFree(v23);
  if ( v7 )
    SysFreeString(v7);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(v24);
  return v9;
}

```

## disassembly

```asm
0x18008e7ec  mov     [rsp-8+arg_18], rbx
0x18008e7f1  push    rbp
0x18008e7f2  push    rsi
0x18008e7f3  push    rdi
0x18008e7f4  push    r14
0x18008e7f6  push    r15
0x18008e7f8  lea     rbp, [rsp-840h]
0x18008e800  sub     rsp, 940h
0x18008e807  mov     rax, cs:__security_cookie
0x18008e80e  xor     rax, rsp
0x18008e811  mov     [rbp+860h+var_30], rax
0x18008e818  mov     r14, r8
0x18008e81b  mov     r8, rdx
0x18008e81e  mov     r15, rcx
0x18008e821  mov     rdi, [rbp+860h+arg_20]
0x18008e828  mov     [rsp+960h+var_930], 0
0x18008e830  mov     [rsp+960h+pv], 0
0x18008e839  mov     [rsp+960h+var_918], 0
0x18008e842  mov     [rsp+960h+var_928], 0
0x18008e84a  mov     [rsp+960h+var_910], 0
0x18008e853  xor     esi, esi
0x18008e855  mov     [rsp+960h+var_92C], esi
0x18008e859  mov     rax, [rdx]
0x18008e85c  lea     rdx, [rsp+960h+var_930]
0x18008e861  mov     rcx, r8
0x18008e864  mov     rax, [rax+50h]
0x18008e868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e86d  mov     ebx, eax
0x18008e86f  test    eax, eax
0x18008e871  jns     short loc_18008E893
0x18008e873  lea     rdx, aPtrsessionGeti_0; "ptrSession->getId failed: 0x%x in %s"
0x18008e87a  mov     r8d, eax
0x18008e87d  lea     r9, aChybridhandler_5; "CHybridHandler::AskForDisconnectPermiss"...
0x18008e884  mov     ecx, 8; int
0x18008e889  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008e88e  jmp     loc_18008EB06
0x18008e893  cmp     [rsp+960h+var_930], esi
0x18008e897  jnz     short loc_18008E8AA
0x18008e899  mov     ebx, 8000FFFFh
0x18008e89e  mov     r8d, ebx
0x18008e8a1  lea     rdx, a0SessidFailed0; "0 == SessId failed: 0x%x in %s"
0x18008e8a8  jmp     short loc_18008E87D
0x18008e8aa  mov     rax, [r14]
0x18008e8ad  lea     rdx, [rsp+960h+var_900]
0x18008e8b2  mov     rcx, r14
0x18008e8b5  mov     rax, [rax+60h]
0x18008e8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e8be  mov     ebx, eax
0x18008e8c0  test    eax, eax
0x18008e8c2  jns     short loc_18008E8CD
0x18008e8c4  lea     rdx, aPtrincomingter; "ptrIncomingTerminal->GetProtocolName fa"...
0x18008e8cb  jmp     short loc_18008E87A
0x18008e8cd  lea     rcx, [rsp+960h+var_900]
0x18008e8d2  call    ?ListenerTypeFromProtoName@CHardcodedListenerConfig@@SA?AW4RdpListenerTypeEnum@@PEBG@Z; CHardcodedListenerConfig::ListenerTypeFromProtoName(ushort const *)
0x18008e8d7  cmp     eax, 2
0x18008e8da  jz      loc_18008EAF5
0x18008e8e0  lea     rcx, [rsp+960h+var_900]
0x18008e8e5  call    ?ListenerTypeFromProtoName@CHardcodedListenerConfig@@SA?AW4RdpListenerTypeEnum@@PEBG@Z; CHardcodedListenerConfig::ListenerTypeFromProtoName(ushort const *)
0x18008e8ea  cmp     eax, 3
0x18008e8ed  jz      loc_18008EAF5
0x18008e8f3  test    rdi, rdi
0x18008e8f6  jz      loc_18008EA0D
0x18008e8fc  mov     rax, [rdi]
0x18008e8ff  lea     rdx, [rsp+960h+var_928]
0x18008e904  mov     rcx, rdi
0x18008e907  mov     rax, [rax+68h]
0x18008e90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e910  mov     ebx, eax
0x18008e912  test    eax, eax
0x18008e914  jns     short loc_18008E922
0x18008e916  lea     rdx, aPincominguserI; "pIncomingUser->IsConnectedUser failed: "...
0x18008e91d  jmp     loc_18008E87A
0x18008e922  mov     rax, [rdi]
0x18008e925  lea     rdx, [rsp+960h+pv]
0x18008e92a  mov     rcx, rdi
0x18008e92d  cmp     [rsp+960h+var_928], esi
0x18008e931  jz      short loc_18008E974
0x18008e933  mov     rax, [rax+38h]
0x18008e937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e93c  mov     ebx, eax
0x18008e93e  test    eax, eax
0x18008e940  jns     short loc_18008E94E
0x18008e942  lea     rdx, aPincominguserG_0; "pIncomingUser->GetInternetPrincipalStr "...
0x18008e949  jmp     loc_18008E87A
0x18008e94e  mov     rax, [rdi]
0x18008e951  lea     rdx, [rsp+960h+var_918]
0x18008e956  mov     rcx, rdi
0x18008e959  mov     rax, [rax+40h]
0x18008e95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e962  mov     ebx, eax
0x18008e964  test    eax, eax
0x18008e966  jns     short loc_18008E9B5
0x18008e968  lea     rdx, aPincominguserG_1; "pIncomingUser->GetInternetProviderStr f"...
0x18008e96f  jmp     loc_18008E87A
0x18008e974  mov     rax, [rax+28h]
0x18008e978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e97d  mov     ebx, eax
0x18008e97f  test    eax, eax
0x18008e981  jns     short loc_18008E98F
0x18008e983  lea     rdx, aPincominguserG_2; "pIncomingUser->GetUserStr failed: 0x%x "...
0x18008e98a  jmp     loc_18008E87A
0x18008e98f  mov     rax, [rdi]
0x18008e992  lea     rdx, [rsp+960h+var_918]
0x18008e997  mov     rcx, rdi
0x18008e99a  mov     rax, [rax+30h]
0x18008e99e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e9a3  mov     ebx, eax
0x18008e9a5  test    eax, eax
0x18008e9a7  jns     short loc_18008E9B5
0x18008e9a9  lea     rdx, aPincominguserG; "pIncomingUser->GetDomainStr failed: 0x%"...
0x18008e9b0  jmp     loc_18008E87A
0x18008e9b5  mov     rax, [rsp+960h+pv]
0x18008e9ba  mov     [rsp+960h+var_940], rax
0x18008e9bf  mov     r9, [rsp+960h+var_918]
0x18008e9c4  lea     r8, aSS_0; "%s\\%s"
0x18008e9cb  mov     edx, 400h; unsigned __int64
0x18008e9d0  lea     rcx, [rbp+860h+psz]; unsigned __int16 *
0x18008e9d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008e9d9  mov     ebx, eax
0x18008e9db  test    eax, eax
0x18008e9dd  jns     short loc_18008E9EB
0x18008e9df  lea     rdx, aStringcchprint_0; "StringCchPrintf failed: 0x%x in %s"
0x18008e9e6  jmp     loc_18008E87A
0x18008e9eb  lea     rcx, [rbp+860h+psz]; psz
0x18008e9ef  call    cs:__imp_SysAllocString
0x18008e9f6  nop     dword ptr [rax+rax+00h]
0x18008e9fb  mov     rsi, rax
0x18008e9fe  test    rax, rax
0x18008ea01  jnz     short loc_18008EA16
0x18008ea03  mov     ebx, 8007000Eh
0x18008ea08  jmp     loc_18008EB06
0x18008ea0d  lea     rcx, [r15+6A8h]
0x18008ea14  jmp     short loc_18008E9EF
0x18008ea16  lea     r8, [rsp+960h+var_910]; void **
0x18008ea1b  mov     edx, [rsp+960h+var_930]; int
0x18008ea1f  call    ?GetRequestDialogObject@CHybridHandler@@AEAAJJPEAPEAX@Z; CHybridHandler::GetRequestDialogObject(long,void * *)
0x18008ea24  mov     ebx, eax
0x18008ea26  test    eax, eax
0x18008ea28  jns     short loc_18008EA36
0x18008ea2a  lea     rdx, aGetrequestdial; "GetRequestDialogObject failed: 0x%x in "...
0x18008ea31  jmp     loc_18008E87A
0x18008ea36  mov     rcx, [rsp+960h+var_910]
0x18008ea3b  mov     rax, [rcx]
0x18008ea3e  lea     r8, [rsp+960h+var_92C]
0x18008ea43  mov     rdx, rsi
0x18008ea46  mov     rax, [rax+18h]
0x18008ea4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea4f  mov     ebx, eax
0x18008ea51  test    eax, eax
0x18008ea53  jns     short loc_18008EA61
0x18008ea55  lea     rdx, aPtrrequestdial; "ptrRequestDialog->ShowBumpDialog failed"...
0x18008ea5c  jmp     loc_18008E87A
0x18008ea61  cmp     [rsp+960h+var_92C], 1
0x18008ea66  jz      loc_18008EB06
0x18008ea6c  cmp     [rsp+960h+var_92C], 7D00h
0x18008ea74  jz      loc_18008EB06
0x18008ea7a  mov     rax, [r14]
0x18008ea7d  lea     rdx, [rbp+860h+var_8B0]
0x18008ea81  mov     rcx, r14
0x18008ea84  mov     rax, [rax+98h]
0x18008ea8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea90  lea     rcx, [r15+728h]; this
0x18008ea97  test    rdi, rdi
0x18008ea9a  jz      short loc_18008EAA8
0x18008ea9c  mov     rdx, [rsp+960h+pv]
0x18008eaa1  mov     r8, [rsp+960h+var_918]
0x18008eaa6  jmp     short loc_18008EAAE
0x18008eaa8  mov     r8, rcx; struct IConnection *
0x18008eaab  mov     rdx, rcx; struct ITSSession *
0x18008eaae  lea     r9, [rbp+860h+var_8B0]
0x18008eab2  test    eax, eax
0x18008eab4  cmovs   r9, rcx; unsigned __int16 *
0x18008eab8  mov     [rsp+960h+var_938], rdx; unsigned __int16 *
0x18008eabd  mov     [rsp+960h+var_940], r8; unsigned __int16 *
0x18008eac2  call    ?LogDeniedEvent@CHybridHandler@@AEAAJPEAUITSSession@@PEAVIConnection@@PEAG22@Z; CHybridHandler::LogDeniedEvent(ITSSession *,IConnection *,ushort *,ushort *,ushort *)
0x18008eac7  mov     ebx, 80070005h
0x18008eacc  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18008ead3  jz      short loc_18008EAE6
0x18008ead5  lea     rdx, aTargetUserReje; "Target User reject disconnect request"
0x18008eadc  mov     ecx, 2; int
0x18008eae1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008eae6  mov     r8d, ebx
0x18008eae9  lea     rdx, aIdokUlresponse; "IDOK != ulResponse && IDTIMEOUT != ulRe"...
0x18008eaf0  jmp     loc_18008E87D
0x18008eaf5  lea     rdx, aTheIncomingCon; "The incoming connection is from VMBus o"...
0x18008eafc  mov     ecx, 4; int
0x18008eb01  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008eb06  mov     rcx, [rsp+960h+pv]; pv
0x18008eb0b  test    rcx, rcx
0x18008eb0e  jz      short loc_18008EB1C
0x18008eb10  call    cs:__imp_CoTaskMemFree
0x18008eb17  nop     dword ptr [rax+rax+00h]
0x18008eb1c  mov     rcx, [rsp+960h+var_918]; pv
0x18008eb21  test    rcx, rcx
0x18008eb24  jz      short loc_18008EB32
0x18008eb26  call    cs:__imp_CoTaskMemFree
0x18008eb2d  nop     dword ptr [rax+rax+00h]
0x18008eb32  test    rsi, rsi
0x18008eb35  jz      short loc_18008EB47
0x18008eb37  mov     rcx, rsi; bstrString
0x18008eb3a  call    cs:__imp_SysFreeString
0x18008eb41  nop     dword ptr [rax+rax+00h]
0x18008eb46  nop
0x18008eb47  lea     rcx, [rsp+960h+var_910]; void *
0x18008eb4c  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18008eb51  mov     eax, ebx
0x18008eb53  mov     rcx, [rbp+860h+var_30]
0x18008eb5a  xor     rcx, rsp; StackCookie
0x18008eb5d  call    __security_check_cookie
0x18008eb62  mov     rbx, [rsp+960h+arg_18]
0x18008eb6a  add     rsp, 940h
0x18008eb71  pop     r15
0x18008eb73  pop     r14
0x18008eb75  pop     rdi
0x18008eb76  pop     rsi
0x18008eb77  pop     rbp
0x18008eb78  retn
```
