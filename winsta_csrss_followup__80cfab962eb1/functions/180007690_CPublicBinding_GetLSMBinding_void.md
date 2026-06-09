# CPublicBinding::GetLSMBinding(void)

- ea: `0x180007690`
- end: `0x180007afb`
- name: `?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ`
- size: `1131`
- prototype: `void *__fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800032b4`
- `0x1800049a0`
- `0x180006740`
- `0x1800075a0`

## callees

- `0x180004558`
- `0x180005b40`
- `0x180007690`
- `0x18000df38`
- `0x18000e2c0`
- `0x18000eb30`
- `0x180032c20`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007755`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007755`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007770`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007770`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007737`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007737`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007a85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007a85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800079c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800079c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007aea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007aea`
- `RPCRT4!RpcBindingFree` at `0x1800078a8`
- `RPCRT4!RpcBindingFree` at `0x180007a63`
- `RPCRT4!RpcBindingFree` at `0x1800078a8`
- `RPCRT4!RpcBindingFree` at `0x180007a63`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800077cc`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000792d`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800077cc`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000792d`
- `RPCRT4!RpcStringFreeW` at `0x18000781f`
- `RPCRT4!RpcStringFreeW` at `0x18000797f`
- `RPCRT4!RpcStringFreeW` at `0x18000781f`
- `RPCRT4!RpcStringFreeW` at `0x18000797f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800077ef`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000794f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800077ef`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000794f`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180007878`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180007a35`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180007ad9`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180007878`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180007a35`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180007ad9`

## string_xrefs

- `0x180007728`: `ntdll.dll`
- `0x1800077b4`: `Security=Impersonation Dynamic False`
- `0x1800078f4`: `Security=Impersonation Dynamic False`
- `0x1800077de`: `Error %d in RpcStringBindingCompose`
- `0x18000793f`: `Error %d in RpcStringBindingCompose`
- `0x18000788d`: `OpenLocalLSM: RpcBindingSetAuthInfoExW failed %d`
- `0x1800078e4`: `\pipe\LSM_API_service`

## pseudocode

```c
void *__fastcall CPublicBinding::GetLSMBinding(RPC_BINDING_HANDLE *Binding)
{
  PSID v2; // r14
  int LocalSids; // eax
  DWORD v4; // eax
  int v6; // ebx
  HMODULE Library; // rax
  HMODULE v8; // r15
  __int64 (*ProcAddress)(void); // rax
  DWORD v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  RPC_STATUS v13; // eax
  unsigned __int16 *v14; // r14
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned __int64 v20; // rbx
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // r15
  RPC_WSTR String; // [rsp+40h] [rbp-29h] BYREF
  RPC_SECURITY_QOS SecurityQOS[2]; // [rsp+48h] [rbp-21h] BYREF
  PSID v25; // [rsp+68h] [rbp-1h]
  RPC_SECURITY_QOS Bindinga; // [rsp+70h] [rbp+7h] BYREF

  if ( *Binding )
    return *Binding;
  if ( *((_DWORD *)Binding + 12) != 1 )
  {
    v14 = (unsigned __int16 *)Binding[5];
    Bindinga.Capabilities = 1;
    *Binding = 0;
    Bindinga.IdentityTracking = 1;
    Bindinga.ImpersonationType = 3;
    Bindinga.Version = 1;
    String = 0;
    v15 = RpcStringBindingComposeW(
            (RPC_WSTR)L"484809d6-4239-471b-b5bc-61df8c23ac48",
            (RPC_WSTR)L"ncacn_np",
            v14,
            (RPC_WSTR)L"\\pipe\\LSM_API_service",
            (RPC_WSTR)L"Security=Impersonation Dynamic False",
            &String);
    v16 = v15;
    if ( v15 )
    {
      _DbgPrintMessage(8, "Error %d in RpcStringBindingCompose", v15);
    }
    else
    {
      v17 = RpcBindingFromStringBindingW(String, Binding);
      v16 = v17;
      if ( v17 )
        _DbgPrintMessage(8, "Error %d in RpcBindingFromStringBinding", v17);
    }
    if ( String )
      RpcStringFreeW(&String);
    if ( v16 )
    {
      _DbgPrintMessage(8, "Error %d in TermSrvBind", v16);
      goto LABEL_46;
    }
    if ( v14 )
    {
      v18 = -1;
      while ( v14[++v18] != 0 )
        ;
      v20 = v18 + 8;
      v21 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v18 + 8));
      v22 = v21;
      if ( !v21 || StringCchPrintfW(v21, v20, L"host/%s", v14) >= 0 )
      {
        v16 = RpcBindingSetAuthInfoExW(*Binding, v22, 6u, 9u, 0, 1u, &Bindinga);
        LocalFree(v22);
        goto LABEL_44;
      }
      LocalFree(v22);
    }
    v16 = RpcBindingSetAuthInfoExW(*Binding, v14, 6u, 9u, 0, 1u, &Bindinga);
LABEL_44:
    if ( !v16 )
      return *Binding;
    _DbgPrintMessage(8, "Error %d in RpcBindingSetAuthInfoEx", v16);
LABEL_46:
    if ( *Binding )
      RpcBindingFree(Binding);
    _DbgPrintMessage(8, "CRpcUtils::BindSecure failed: %d", v16);
    SetLastError(v16);
    return *Binding;
  }
  v2 = CPublicBinding::pSystemSid;
  if ( !CPublicBinding::pSystemSid )
  {
    LocalSids = CPublicBinding::CreateLocalSids();
    if ( LocalSids < 0 )
    {
      v4 = ConvertHRESULT2WIN32(LocalSids);
      SetLastError(v4);
      return 0;
    }
    v2 = CPublicBinding::pSystemSid;
  }
  *(_QWORD *)&Bindinga.Version = 0;
  memset(SecurityQOS, 0, sizeof(SecurityQOS));
  v25 = 0;
  if ( byte_18005A9B0 )
  {
    LOBYTE(v6) = dword_18005A5B8;
  }
  else
  {
    v6 = MEMORY[0x7FFE02D0];
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v8 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetSuiteMask");
      if ( ProcAddress )
        v6 = ProcAddress();
      FreeLibrary(v8);
    }
    dword_18005A5B8 = v6;
    byte_18005A9B0 = 1;
  }
  if ( (v6 & 0x10) == 0 )
  {
    v10 = 1058;
LABEL_25:
    if ( *(_QWORD *)&Bindinga.Version )
    {
      RpcBindingFree((RPC_BINDING_HANDLE *)&Bindinga);
      *(_QWORD *)&Bindinga.Version = 0;
    }
    SetLastError(v10);
    goto LABEL_28;
  }
  String = 0;
  v11 = RpcStringBindingComposeW(
          0,
          (RPC_WSTR)L"ncalrpc",
          0,
          (RPC_WSTR)L"LSMApi",
          (RPC_WSTR)L"Security=Impersonation Dynamic False",
          &String);
  v10 = v11;
  if ( v11 )
  {
    _DbgPrintMessage(8, "Error %d in RpcStringBindingCompose", v11);
  }
  else
  {
    v12 = RpcBindingFromStringBindingW(String, (RPC_BINDING_HANDLE *)&Bindinga);
    v10 = v12;
    if ( v12 )
      _DbgPrintMessage(8, "Error %d in RpcBindingFromStringBinding", v12);
  }
  if ( String )
    RpcStringFreeW(&String);
  if ( v10 )
    goto LABEL_25;
  SecurityQOS[0].IdentityTracking = 1;
  *(_QWORD *)&SecurityQOS[0].ImpersonationType = 3;
  *(_QWORD *)&SecurityQOS[1].IdentityTracking = 0;
  v25 = v2;
  *(_QWORD *)&SecurityQOS[0].Version = 0x100000003LL;
  v13 = RpcBindingSetAuthInfoExW(*(RPC_BINDING_HANDLE *)&Bindinga.Version, 0, 6u, 0xAu, 0, 0, SecurityQOS);
  v10 = v13;
  if ( v13 )
  {
    _DbgPrintMessage(8, "OpenLocalLSM: RpcBindingSetAuthInfoExW failed %d", v13);
    goto LABEL_25;
  }
LABEL_28:
  WaitForLsmStart();
  *Binding = *(RPC_BINDING_HANDLE *)&Bindinga.Version;
  return *Binding;
}

```

## disassembly

```asm
0x180007690  push    rbp
0x180007692  push    rbx
0x180007693  push    rsi
0x180007694  push    rdi
0x180007695  push    r14
0x180007697  push    r15
0x180007699  lea     rbp, [rsp-2Fh]
0x18000769e  sub     rsp, 98h
0x1800076a5  mov     rax, cs:__security_cookie
0x1800076ac  xor     rax, rsp
0x1800076af  mov     [rbp+57h+var_40], rax
0x1800076b3  cmp     qword ptr [rcx], 0
0x1800076b7  mov     rdi, rcx
0x1800076ba  jnz     loc_180007A91
0x1800076c0  cmp     dword ptr [rcx+30h], 1
0x1800076c4  jnz     loc_1800078D7
0x1800076ca  mov     r14, cs:?pSystemSid@CPublicBinding@@1PEAXEA; void * CPublicBinding::pSystemSid
0x1800076d1  test    r14, r14
0x1800076d4  jnz     short loc_180007702
0x1800076d6  call    ?CreateLocalSids@CPublicBinding@@SAJXZ; CPublicBinding::CreateLocalSids(void)
0x1800076db  test    eax, eax
0x1800076dd  jns     short loc_1800076FB
0x1800076df  mov     ecx, eax; int
0x1800076e1  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800076e6  mov     ecx, eax; dwErrCode
0x1800076e8  call    cs:__imp_SetLastError
0x1800076ef  nop     dword ptr [rax+rax+00h]
0x1800076f4  xor     eax, eax
0x1800076f6  jmp     loc_180007A94
0x1800076fb  mov     r14, cs:?pSystemSid@CPublicBinding@@1PEAXEA; void * CPublicBinding::pSystemSid
0x180007702  xor     esi, esi
0x180007704  xor     eax, eax
0x180007706  cmp     cs:byte_18005A9B0, al
0x18000770c  xorps   xmm0, xmm0
0x18000770f  mov     [rbp+57h+Binding], rsi
0x180007713  movups  xmmword ptr [rbp+57h+var_78.Version], xmm0
0x180007717  mov     [rbp+57h+var_58], rax
0x18000771b  movups  [rbp+57h+var_68], xmm0
0x18000771f  jnz     short loc_18000778B
0x180007721  mov     ebx, ds:7FFE02D0h
0x180007728  lea     rcx, ModuleName; "ntdll.dll"
0x18000772f  xor     edx, edx; hFile
0x180007731  mov     r8d, 800h; dwFlags
0x180007737  call    cs:__imp_LoadLibraryExW
0x18000773e  nop     dword ptr [rax+rax+00h]
0x180007743  mov     r15, rax
0x180007746  test    rax, rax
0x180007749  jz      short loc_18000777C
0x18000774b  lea     rdx, ProcName; "RtlGetSuiteMask"
0x180007752  mov     rcx, rax; hModule
0x180007755  call    cs:__imp_GetProcAddress
0x18000775c  nop     dword ptr [rax+rax+00h]
0x180007761  test    rax, rax
0x180007764  jz      short loc_18000776D
0x180007766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000776b  mov     ebx, eax
0x18000776d  mov     rcx, r15; hLibModule
0x180007770  call    cs:__imp_FreeLibrary
0x180007777  nop     dword ptr [rax+rax+00h]
0x18000777c  mov     cs:dword_18005A5B8, ebx
0x180007782  mov     cs:byte_18005A9B0, 1
0x180007789  jmp     short loc_180007791
0x18000778b  mov     ebx, cs:dword_18005A5B8
0x180007791  test    bl, 10h
0x180007794  jnz     short loc_1800077A0
0x180007796  mov     ebx, 422h
0x18000779b  jmp     loc_18000789E
0x1800077a0  lea     rax, [rbp+57h+String]
0x1800077a4  mov     [rbp+57h+String], rsi
0x1800077a8  mov     [rsp+0C0h+StringBinding], rax; StringBinding
0x1800077ad  lea     r9, Endpoint; "LSMApi"
0x1800077b4  lea     rax, Options; "Security=Impersonation Dynamic False"
0x1800077bb  xor     r8d, r8d; NetworkAddr
0x1800077be  lea     rdx, ProtSeq; "ncalrpc"
0x1800077c5  mov     [rsp+0C0h+Options], rax; Options
0x1800077ca  xor     ecx, ecx; ObjUuid
0x1800077cc  call    cs:__imp_RpcStringBindingComposeW
0x1800077d3  nop     dword ptr [rax+rax+00h]
0x1800077d8  mov     ebx, eax
0x1800077da  test    eax, eax
0x1800077dc  jz      short loc_1800077E7
0x1800077de  lea     rdx, aErrorDInRpcstr; "Error %d in RpcStringBindingCompose"
0x1800077e5  jmp     short loc_180007808
0x1800077e7  mov     rcx, [rbp+57h+String]; StringBinding
0x1800077eb  lea     rdx, [rbp+57h+Binding]; Binding
0x1800077ef  call    cs:__imp_RpcBindingFromStringBindingW
0x1800077f6  nop     dword ptr [rax+rax+00h]
0x1800077fb  mov     ebx, eax
0x1800077fd  test    eax, eax
0x1800077ff  jz      short loc_180007815
0x180007801  lea     rdx, aErrorDInRpcbin_0; "Error %d in RpcBindingFromStringBinding"
0x180007808  mov     r8d, eax
0x18000780b  mov     ecx, 8; int
0x180007810  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007815  cmp     [rbp+57h+String], rsi
0x180007819  jz      short loc_18000782B
0x18000781b  lea     rcx, [rbp+57h+String]; String
0x18000781f  call    cs:__imp_RpcStringFreeW
0x180007826  nop     dword ptr [rax+rax+00h]
0x18000782b  test    ebx, ebx
0x18000782d  jnz     short loc_18000789E
0x18000782f  mov     rcx, [rbp+57h+Binding]; Binding
0x180007833  lea     rax, [rbp+57h+var_78]
0x180007837  mov     [rsp+0C0h+SecurityQOS], rax; SecurityQOS
0x18000783c  xor     edx, edx; ServerPrincName
0x18000783e  mov     dword ptr [rsp+0C0h+StringBinding], esi; AuthzSvc
0x180007842  mov     r9d, 0Ah; AuthnSvc
0x180007848  mov     r8d, 6; AuthnLevel
0x18000784e  mov     [rsp+0C0h+Options], rsi; AuthIdentity
0x180007853  mov     [rbp+57h+var_78.Capabilities], 1
0x18000785a  mov     [rbp+57h+var_78.IdentityTracking], 1
0x180007861  mov     qword ptr [rbp+57h+var_78.ImpersonationType], 3
0x180007869  mov     qword ptr [rbp+57h+var_68+8], rsi
0x18000786d  mov     [rbp+57h+var_58], r14
0x180007871  mov     [rbp+57h+var_78.Version], 3
0x180007878  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000787f  nop     dword ptr [rax+rax+00h]
0x180007884  mov     ebx, eax
0x180007886  test    eax, eax
0x180007888  jz      short loc_1800078C6
0x18000788a  mov     r8d, eax
0x18000788d  lea     rdx, aOpenlocallsmRp; "OpenLocalLSM: RpcBindingSetAuthInfoExW "...
0x180007894  mov     ecx, 8; int
0x180007899  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000789e  cmp     [rbp+57h+Binding], rsi
0x1800078a2  jz      short loc_1800078B8
0x1800078a4  lea     rcx, [rbp+57h+Binding]; Binding
0x1800078a8  call    cs:__imp_RpcBindingFree
0x1800078af  nop     dword ptr [rax+rax+00h]
0x1800078b4  mov     [rbp+57h+Binding], rsi
0x1800078b8  mov     ecx, ebx; dwErrCode
0x1800078ba  call    cs:__imp_SetLastError
0x1800078c1  nop     dword ptr [rax+rax+00h]
0x1800078c6  call    ?WaitForLsmStart@@YAHXZ; WaitForLsmStart(void)
0x1800078cb  mov     rax, [rbp+57h+Binding]
0x1800078cf  mov     [rdi], rax
0x1800078d2  jmp     loc_180007A91
0x1800078d7  mov     r14, [rcx+28h]
0x1800078db  lea     rax, [rbp+57h+String]
0x1800078df  mov     [rsp+0C0h+StringBinding], rax; StringBinding
0x1800078e4  lea     r9, aPipeLsmApiServ; "\\pipe\\LSM_API_service"
0x1800078eb  xor     esi, esi
0x1800078ed  mov     dword ptr [rbp+57h+Binding+4], 1
0x1800078f4  lea     rax, Options; "Security=Impersonation Dynamic False"
0x1800078fb  mov     [rcx], rsi
0x1800078fe  mov     r8, r14; NetworkAddr
0x180007901  mov     [rsp+0C0h+Options], rax; Options
0x180007906  lea     rdx, aNcacnNp; "ncacn_np"
0x18000790d  mov     [rbp+57h+var_48], 1
0x180007914  lea     rcx, ObjUuid; "484809d6-4239-471b-b5bc-61df8c23ac48"
0x18000791b  mov     [rbp+57h+var_44], 3
0x180007922  mov     dword ptr [rbp+57h+Binding], 1
0x180007929  mov     [rbp+57h+String], rsi
0x18000792d  call    cs:__imp_RpcStringBindingComposeW
0x180007934  nop     dword ptr [rax+rax+00h]
0x180007939  mov     ebx, eax
0x18000793b  test    eax, eax
0x18000793d  jz      short loc_180007948
0x18000793f  lea     rdx, aErrorDInRpcstr; "Error %d in RpcStringBindingCompose"
0x180007946  jmp     short loc_180007968
0x180007948  mov     rcx, [rbp+57h+String]; StringBinding
0x18000794c  mov     rdx, rdi; Binding
0x18000794f  call    cs:__imp_RpcBindingFromStringBindingW
0x180007956  nop     dword ptr [rax+rax+00h]
0x18000795b  mov     ebx, eax
0x18000795d  test    eax, eax
0x18000795f  jz      short loc_180007975
0x180007961  lea     rdx, aErrorDInRpcbin_0; "Error %d in RpcBindingFromStringBinding"
0x180007968  mov     r8d, eax
0x18000796b  mov     ecx, 8; int
0x180007970  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007975  cmp     [rbp+57h+String], rsi
0x180007979  jz      short loc_18000798B
0x18000797b  lea     rcx, [rbp+57h+String]; String
0x18000797f  call    cs:__imp_RpcStringFreeW
0x180007986  nop     dword ptr [rax+rax+00h]
0x18000798b  test    ebx, ebx
0x18000798d  jz      short loc_18000799B
0x18000798f  lea     rdx, aErrorDInTermsr; "Error %d in TermSrvBind"
0x180007996  jmp     loc_180007A4E
0x18000799b  test    r14, r14
0x18000799e  jz      short loc_180007A0D
0x1800079a0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800079a7  nop     word ptr [rax+rax+00000000h]
0x1800079b0  cmp     [r14+rax*2+2], si
0x1800079b6  lea     rax, [rax+1]
0x1800079ba  jnz     short loc_1800079B0
0x1800079bc  lea     rbx, [rax+8]
0x1800079c0  mov     ecx, 40h ; '@'; uFlags
0x1800079c5  lea     rdx, [rbx+rbx]; uBytes
0x1800079c9  call    cs:__imp_LocalAlloc
0x1800079d0  nop     dword ptr [rax+rax+00h]
0x1800079d5  mov     r15, rax
0x1800079d8  test    rax, rax
0x1800079db  jz      loc_180007AB1
0x1800079e1  mov     r9, r14
0x1800079e4  lea     r8, aHostS; "host/%s"
0x1800079eb  mov     rdx, rbx; unsigned __int64
0x1800079ee  mov     rcx, rax; unsigned __int16 *
0x1800079f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800079f6  test    eax, eax
0x1800079f8  jns     loc_180007AB1
0x1800079fe  mov     rcx, r15; hMem
0x180007a01  call    cs:__imp_LocalFree
0x180007a08  nop     dword ptr [rax+rax+00h]
0x180007a0d  mov     rcx, [rdi]; Binding
0x180007a10  lea     rax, [rbp+57h+Binding]
0x180007a14  mov     [rsp+0C0h+SecurityQOS], rax; SecurityQOS
0x180007a19  mov     r9d, 9; AuthnSvc
0x180007a1f  mov     dword ptr [rsp+0C0h+StringBinding], 1; AuthzSvc
0x180007a27  mov     r8d, 6; AuthnLevel
0x180007a2d  mov     rdx, r14; ServerPrincName
0x180007a30  mov     [rsp+0C0h+Options], rsi; AuthIdentity
0x180007a35  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180007a3c  nop     dword ptr [rax+rax+00h]
0x180007a41  mov     ebx, eax
0x180007a43  test    ebx, ebx
0x180007a45  jz      short loc_180007A91
0x180007a47  lea     rdx, aErrorDInRpcbin; "Error %d in RpcBindingSetAuthInfoEx"
0x180007a4e  mov     r8d, ebx
0x180007a51  mov     ecx, 8; int
0x180007a56  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007a5b  cmp     [rdi], rsi
0x180007a5e  jz      short loc_180007A6F
0x180007a60  mov     rcx, rdi; Binding
0x180007a63  call    cs:__imp_RpcBindingFree
0x180007a6a  nop     dword ptr [rax+rax+00h]
0x180007a6f  mov     r8d, ebx
0x180007a72  lea     rdx, aCrpcutilsBinds; "CRpcUtils::BindSecure failed: %d"
0x180007a79  mov     ecx, 8; int
0x180007a7e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007a83  mov     ecx, ebx; dwErrCode
0x180007a85  call    cs:__imp_SetLastError
0x180007a8c  nop     dword ptr [rax+rax+00h]
0x180007a91  mov     rax, [rdi]
0x180007a94  mov     rcx, [rbp+57h+var_40]
0x180007a98  xor     rcx, rsp; StackCookie
0x180007a9b  call    __security_check_cookie
0x180007aa0  add     rsp, 98h
0x180007aa7  pop     r15
0x180007aa9  pop     r14
0x180007aab  pop     rdi
0x180007aac  pop     rsi
0x180007aad  pop     rbx
0x180007aae  pop     rbp
0x180007aaf  retn
0x180007ab1  mov     rcx, [rdi]; Binding
0x180007ab4  lea     rax, [rbp+57h+Binding]
0x180007ab8  mov     [rsp+0C0h+SecurityQOS], rax; SecurityQOS
0x180007abd  mov     r9d, 9; AuthnSvc
0x180007ac3  mov     dword ptr [rsp+0C0h+StringBinding], 1; AuthzSvc
0x180007acb  mov     r8d, 6; AuthnLevel
0x180007ad1  mov     rdx, r15; ServerPrincName
0x180007ad4  mov     [rsp+0C0h+Options], rsi; AuthIdentity
0x180007ad9  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180007ae0  nop     dword ptr [rax+rax+00h]
0x180007ae5  mov     rcx, r15; hMem
0x180007ae8  mov     ebx, eax
0x180007aea  call    cs:__imp_LocalFree
0x180007af1  nop     dword ptr [rax+rax+00h]
0x180007af6  jmp     loc_180007A43
```
