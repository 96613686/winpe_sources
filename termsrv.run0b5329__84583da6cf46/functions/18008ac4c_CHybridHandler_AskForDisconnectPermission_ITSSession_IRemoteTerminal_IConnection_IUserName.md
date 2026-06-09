# CHybridHandler::AskForDisconnectPermission(ITSSession *,IRemoteTerminal *,IConnection *,IUserName *)

- ea: `0x18008ac4c`
- end: `0x18008afc1`
- name: `?AskForDisconnectPermission@CHybridHandler@@AEAAJPEAUITSSession@@PEAVIRemoteTerminal@@PEAVIConnection@@PEAUIUserName@@@Z`
- size: `885`
- prototype: `__int64 __fastcall(CHybridHandler *__hidden this, struct ITSSession *, struct IRemoteTerminal *, struct IConnection *, struct IUserName *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008c160`

## callees

- `0x18000a210`
- `0x180013150`
- `0x180015ab0`
- `0x1800181e0`
- `0x1800321f0`
- `0x18008ac4c`
- `0x18008bbd0`
- `0x18008c730`
- `0x1800c8010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008ae4f`
- `OLEAUT32!__imp_SysAllocString` at `0x18008ae4f`
- `OLEAUT32!__imp_SysFreeString` at `0x18008af88`
- `OLEAUT32!__imp_SysFreeString` at `0x18008af88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008af6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008af7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008af6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008af7a`

## string_xrefs

- `0x18008ad01`: `0 == SessId failed: 0x%x in %s`
- `0x18008ad24`: `ptrIncomingTerminal->GetProtocolName failed: 0x%x in %s`
- `0x18008af4f`: `The incoming connection is from VMBus or HvSocket listener, auto-approving the disconnect.`
- `0x18008ad76`: `pIncomingUser->IsConnectedUser failed: 0x%x in %s`
- `0x18008ada2`: `pIncomingUser->GetInternetPrincipalStr failed: 0x%x in %s`
- `0x18008adc8`: `pIncomingUser->GetInternetProviderStr failed: 0x%x in %s`
- `0x18008ade3`: `pIncomingUser->GetUserStr failed: 0x%x in %s`
- `0x18008ae09`: `pIncomingUser->GetDomainStr failed: 0x%x in %s`

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
0x18008ac4c  mov     [rsp-8+arg_18], rbx
0x18008ac51  push    rbp
0x18008ac52  push    rsi
0x18008ac53  push    rdi
0x18008ac54  push    r14
0x18008ac56  push    r15
0x18008ac58  lea     rbp, [rsp-840h]
0x18008ac60  sub     rsp, 940h
0x18008ac67  mov     rax, cs:__security_cookie
0x18008ac6e  xor     rax, rsp
0x18008ac71  mov     [rbp+860h+var_30], rax
0x18008ac78  mov     r14, r8
0x18008ac7b  mov     r8, rdx
0x18008ac7e  mov     r15, rcx
0x18008ac81  mov     rdi, [rbp+860h+arg_20]
0x18008ac88  mov     [rsp+960h+var_930], 0
0x18008ac90  mov     [rsp+960h+pv], 0
0x18008ac99  mov     [rsp+960h+var_918], 0
0x18008aca2  mov     [rsp+960h+var_928], 0
0x18008acaa  mov     [rsp+960h+var_910], 0
0x18008acb3  xor     esi, esi
0x18008acb5  mov     [rsp+960h+var_92C], esi
0x18008acb9  mov     rax, [rdx]
0x18008acbc  lea     rdx, [rsp+960h+var_930]
0x18008acc1  mov     rcx, r8
0x18008acc4  mov     rax, [rax+50h]
0x18008acc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008accd  mov     ebx, eax
0x18008accf  test    eax, eax
0x18008acd1  jns     short loc_18008ACF3
0x18008acd3  lea     rdx, aPtrsessionGeti_0; "ptrSession->getId failed: 0x%x in %s"
0x18008acda  mov     r8d, eax
0x18008acdd  lea     r9, aChybridhandler_5; "CHybridHandler::AskForDisconnectPermiss"...
0x18008ace4  mov     ecx, 8; int
0x18008ace9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008acee  jmp     loc_18008AF60
0x18008acf3  cmp     [rsp+960h+var_930], esi
0x18008acf7  jnz     short loc_18008AD0A
0x18008acf9  mov     ebx, 8000FFFFh
0x18008acfe  mov     r8d, ebx
0x18008ad01  lea     rdx, a0SessidFailed0; "0 == SessId failed: 0x%x in %s"
0x18008ad08  jmp     short loc_18008ACDD
0x18008ad0a  mov     rax, [r14]
0x18008ad0d  lea     rdx, [rsp+960h+var_900]
0x18008ad12  mov     rcx, r14
0x18008ad15  mov     rax, [rax+60h]
0x18008ad19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ad1e  mov     ebx, eax
0x18008ad20  test    eax, eax
0x18008ad22  jns     short loc_18008AD2D
0x18008ad24  lea     rdx, aPtrincomingter; "ptrIncomingTerminal->GetProtocolName fa"...
0x18008ad2b  jmp     short loc_18008ACDA
0x18008ad2d  lea     rcx, [rsp+960h+var_900]
0x18008ad32  call    ?ListenerTypeFromProtoName@CHardcodedListenerConfig@@SA?AW4RdpListenerTypeEnum@@PEBG@Z; CHardcodedListenerConfig::ListenerTypeFromProtoName(ushort const *)
0x18008ad37  cmp     eax, 2
0x18008ad3a  jz      loc_18008AF4F
0x18008ad40  lea     rcx, [rsp+960h+var_900]
0x18008ad45  call    ?ListenerTypeFromProtoName@CHardcodedListenerConfig@@SA?AW4RdpListenerTypeEnum@@PEBG@Z; CHardcodedListenerConfig::ListenerTypeFromProtoName(ushort const *)
0x18008ad4a  cmp     eax, 3
0x18008ad4d  jz      loc_18008AF4F
0x18008ad53  test    rdi, rdi
0x18008ad56  jz      loc_18008AE67
0x18008ad5c  mov     rax, [rdi]
0x18008ad5f  lea     rdx, [rsp+960h+var_928]
0x18008ad64  mov     rcx, rdi
0x18008ad67  mov     rax, [rax+68h]
0x18008ad6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ad70  mov     ebx, eax
0x18008ad72  test    eax, eax
0x18008ad74  jns     short loc_18008AD82
0x18008ad76  lea     rdx, aPincominguserI; "pIncomingUser->IsConnectedUser failed: "...
0x18008ad7d  jmp     loc_18008ACDA
0x18008ad82  mov     rax, [rdi]
0x18008ad85  lea     rdx, [rsp+960h+pv]
0x18008ad8a  mov     rcx, rdi
0x18008ad8d  cmp     [rsp+960h+var_928], esi
0x18008ad91  jz      short loc_18008ADD4
0x18008ad93  mov     rax, [rax+38h]
0x18008ad97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ad9c  mov     ebx, eax
0x18008ad9e  test    eax, eax
0x18008ada0  jns     short loc_18008ADAE
0x18008ada2  lea     rdx, aPincominguserG_0; "pIncomingUser->GetInternetPrincipalStr "...
0x18008ada9  jmp     loc_18008ACDA
0x18008adae  mov     rax, [rdi]
0x18008adb1  lea     rdx, [rsp+960h+var_918]
0x18008adb6  mov     rcx, rdi
0x18008adb9  mov     rax, [rax+40h]
0x18008adbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008adc2  mov     ebx, eax
0x18008adc4  test    eax, eax
0x18008adc6  jns     short loc_18008AE15
0x18008adc8  lea     rdx, aPincominguserG_1; "pIncomingUser->GetInternetProviderStr f"...
0x18008adcf  jmp     loc_18008ACDA
0x18008add4  mov     rax, [rax+28h]
0x18008add8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008addd  mov     ebx, eax
0x18008addf  test    eax, eax
0x18008ade1  jns     short loc_18008ADEF
0x18008ade3  lea     rdx, aPincominguserG_2; "pIncomingUser->GetUserStr failed: 0x%x "...
0x18008adea  jmp     loc_18008ACDA
0x18008adef  mov     rax, [rdi]
0x18008adf2  lea     rdx, [rsp+960h+var_918]
0x18008adf7  mov     rcx, rdi
0x18008adfa  mov     rax, [rax+30h]
0x18008adfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ae03  mov     ebx, eax
0x18008ae05  test    eax, eax
0x18008ae07  jns     short loc_18008AE15
0x18008ae09  lea     rdx, aPincominguserG; "pIncomingUser->GetDomainStr failed: 0x%"...
0x18008ae10  jmp     loc_18008ACDA
0x18008ae15  mov     rax, [rsp+960h+pv]
0x18008ae1a  mov     [rsp+960h+var_940], rax
0x18008ae1f  mov     r9, [rsp+960h+var_918]
0x18008ae24  lea     r8, aSS_0; "%s\\%s"
0x18008ae2b  mov     edx, 400h; unsigned __int64
0x18008ae30  lea     rcx, [rbp+860h+psz]; unsigned __int16 *
0x18008ae34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008ae39  mov     ebx, eax
0x18008ae3b  test    eax, eax
0x18008ae3d  jns     short loc_18008AE4B
0x18008ae3f  lea     rdx, aStringcchprint_0; "StringCchPrintf failed: 0x%x in %s"
0x18008ae46  jmp     loc_18008ACDA
0x18008ae4b  lea     rcx, [rbp+860h+psz]; psz
0x18008ae4f  call    cs:__imp_SysAllocString
0x18008ae55  mov     rsi, rax
0x18008ae58  test    rax, rax
0x18008ae5b  jnz     short loc_18008AE70
0x18008ae5d  mov     ebx, 8007000Eh
0x18008ae62  jmp     loc_18008AF60
0x18008ae67  lea     rcx, [r15+6A8h]
0x18008ae6e  jmp     short loc_18008AE4F
0x18008ae70  lea     r8, [rsp+960h+var_910]; void **
0x18008ae75  mov     edx, [rsp+960h+var_930]; int
0x18008ae79  call    ?GetRequestDialogObject@CHybridHandler@@AEAAJJPEAPEAX@Z; CHybridHandler::GetRequestDialogObject(long,void * *)
0x18008ae7e  mov     ebx, eax
0x18008ae80  test    eax, eax
0x18008ae82  jns     short loc_18008AE90
0x18008ae84  lea     rdx, aGetrequestdial; "GetRequestDialogObject failed: 0x%x in "...
0x18008ae8b  jmp     loc_18008ACDA
0x18008ae90  mov     rcx, [rsp+960h+var_910]
0x18008ae95  mov     rax, [rcx]
0x18008ae98  lea     r8, [rsp+960h+var_92C]
0x18008ae9d  mov     rdx, rsi
0x18008aea0  mov     rax, [rax+18h]
0x18008aea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aea9  mov     ebx, eax
0x18008aeab  test    eax, eax
0x18008aead  jns     short loc_18008AEBB
0x18008aeaf  lea     rdx, aPtrrequestdial; "ptrRequestDialog->ShowBumpDialog failed"...
0x18008aeb6  jmp     loc_18008ACDA
0x18008aebb  cmp     [rsp+960h+var_92C], 1
0x18008aec0  jz      loc_18008AF60
0x18008aec6  cmp     [rsp+960h+var_92C], 7D00h
0x18008aece  jz      loc_18008AF60
0x18008aed4  mov     rax, [r14]
0x18008aed7  lea     rdx, [rbp+860h+var_8B0]
0x18008aedb  mov     rcx, r14
0x18008aede  mov     rax, [rax+98h]
0x18008aee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aeea  lea     rcx, [r15+728h]; this
0x18008aef1  test    rdi, rdi
0x18008aef4  jz      short loc_18008AF02
0x18008aef6  mov     rdx, [rsp+960h+pv]
0x18008aefb  mov     r8, [rsp+960h+var_918]
0x18008af00  jmp     short loc_18008AF08
0x18008af02  mov     r8, rcx; struct IConnection *
0x18008af05  mov     rdx, rcx; struct ITSSession *
0x18008af08  lea     r9, [rbp+860h+var_8B0]
0x18008af0c  test    eax, eax
0x18008af0e  cmovs   r9, rcx; unsigned __int16 *
0x18008af12  mov     [rsp+960h+var_938], rdx; unsigned __int16 *
0x18008af17  mov     [rsp+960h+var_940], r8; unsigned __int16 *
0x18008af1c  call    ?LogDeniedEvent@CHybridHandler@@AEAAJPEAUITSSession@@PEAVIConnection@@PEAG22@Z; CHybridHandler::LogDeniedEvent(ITSSession *,IConnection *,ushort *,ushort *,ushort *)
0x18008af21  mov     ebx, 80070005h
0x18008af26  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18008af2d  jz      short loc_18008AF40
0x18008af2f  lea     rdx, aTargetUserReje; "Target User reject disconnect request"
0x18008af36  mov     ecx, 2; int
0x18008af3b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008af40  mov     r8d, ebx
0x18008af43  lea     rdx, aIdokUlresponse; "IDOK != ulResponse && IDTIMEOUT != ulRe"...
0x18008af4a  jmp     loc_18008ACDD
0x18008af4f  lea     rdx, aTheIncomingCon; "The incoming connection is from VMBus o"...
0x18008af56  mov     ecx, 4; int
0x18008af5b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008af60  mov     rcx, [rsp+960h+pv]; pv
0x18008af65  test    rcx, rcx
0x18008af68  jz      short loc_18008AF70
0x18008af6a  call    cs:__imp_CoTaskMemFree
0x18008af70  mov     rcx, [rsp+960h+var_918]; pv
0x18008af75  test    rcx, rcx
0x18008af78  jz      short loc_18008AF80
0x18008af7a  call    cs:__imp_CoTaskMemFree
0x18008af80  test    rsi, rsi
0x18008af83  jz      short loc_18008AF8F
0x18008af85  mov     rcx, rsi; bstrString
0x18008af88  call    cs:__imp_SysFreeString
0x18008af8e  nop
0x18008af8f  lea     rcx, [rsp+960h+var_910]; void *
0x18008af94  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18008af99  mov     eax, ebx
0x18008af9b  mov     rcx, [rbp+860h+var_30]
0x18008afa2  xor     rcx, rsp; StackCookie
0x18008afa5  call    __security_check_cookie
0x18008afaa  mov     rbx, [rsp+960h+arg_18]
0x18008afb2  add     rsp, 940h
0x18008afb9  pop     r15
0x18008afbb  pop     r14
0x18008afbd  pop     rdi
0x18008afbe  pop     rsi
0x18008afbf  pop     rbp
0x18008afc0  retn
```
