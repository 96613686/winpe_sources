# SstpSvcSetConfig

- ea: `0x180014840`
- end: `0x180014ab9`
- name: `SstpSvcSetConfig`
- size: `633`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800068e0`
- `0x180007c34`
- `0x18000827c`
- `0x180008360`
- `0x180008434`
- `0x18000b2e0`
- `0x18000c8d0`
- `0x180010b84`
- `0x180013464`
- `0x180014840`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014995`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014995`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800149a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800149a6`
- `RPCRT4!RpcRevertToSelf` at `0x180014a2c`
- `RPCRT4!RpcRevertToSelf` at `0x180014a2c`
- `RPCRT4!RpcImpersonateClient` at `0x180014897`
- `RPCRT4!RpcImpersonateClient` at `0x180014897`
- `sstpcfg!SetSstpProxyConfig` at `0x1800149b0`
- `sstpcfg!SetSstpProxyConfig` at `0x1800149b0`
- `sstpcfg!SetSstpConfiguration` at `0x1800148f3`
- `sstpcfg!SetSstpConfiguration` at `0x1800148f3`
- `sstpcfg!SetupSstpServerConfig` at `0x180014923`
- `sstpcfg!SetupSstpServerConfig` at `0x180014923`

## string_xrefs

- `0x1800148b5`: `SstpSvcSetConfig: RpcImpersonateClient failed with error %d`
- `0x18001490c`: `SstpSvcSetConfig: SetSstpConfiguration failed with error %d`
- `0x18001493c`: `SstpSvcSetConfig: SetupSstpServerConfig failed with error %d`
- `0x180014967`: `SstpSvcSetConfig: InitializeSstpServer failed with error %d`
- `0x1800149c5`: `SstpSvcSetConfig: SetSstpProxyConfig failed with error %d`
- `0x1800149f0`: `SstpSvcSetConfig: LoadSstpProxyConfigFromXmlFile failed with error %d`
- `0x180014a42`: `SstpSvcGetConfig: FATAL ERROR. RpcRevertToSelf failed with error %d`

## pseudocode

```c
__int64 __fastcall SstpSvcSetConfig(__int64 a1, unsigned int *a2)
{
  bool v3; // r15
  unsigned int v4; // eax
  unsigned int SstpProxyConfigFromXmlFile; // ebx
  int SstpConfigFlag; // r14d
  const wchar_t *v7; // rdx
  RTL_SRWLOCK *Instance; // rbx
  unsigned int v9; // eax
  int v11; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v12[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v3 = 0;
  TenantGatewayMap::GetInstance();
  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  v4 = RpcImpersonateClient(0);
  SstpProxyConfigFromXmlFile = v4;
  if ( v4 )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_29;
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"SstpSvcSetConfig: RpcImpersonateClient failed with error %d", v4);
    goto LABEL_27;
  }
  if ( !*a2 )
  {
    ShutdownSstpServer(0);
    Instance = (RTL_SRWLOCK *)TenantGatewayMap::GetInstance();
    if ( (unsigned int)GetSstpConfigFlag(1) )
    {
      AcquireSRWLockExclusive(Instance);
      TenantGatewayMap::DeleteSstpProxyRules((TenantGatewayMap *)Instance);
      ReleaseSRWLockExclusive(Instance);
    }
    goto LABEL_19;
  }
  SstpConfigFlag = GetSstpConfigFlag(1);
  if ( a2[6] )
  {
    SstpProxyConfigFromXmlFile = SetSstpConfiguration(0, 0, a2[1], *((_QWORD *)a2 + 4), v11);
    if ( SstpProxyConfigFromXmlFile )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_29;
      v7 = L"SstpSvcSetConfig: SetSstpConfiguration failed with error %d";
      goto LABEL_26;
    }
    v3 = SstpConfigFlag == 1;
  }
  SstpProxyConfigFromXmlFile = SetupSstpServerConfig();
  if ( SstpProxyConfigFromXmlFile )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_29;
    v7 = L"SstpSvcSetConfig: SetupSstpServerConfig failed with error %d";
    goto LABEL_26;
  }
  if ( *a2 == SstpConfigFlag || (SstpProxyConfigFromXmlFile = InitializeSstpServer(0)) == 0 )
  {
LABEL_19:
    SstpProxyConfigFromXmlFile = SetSstpProxyConfig(0, *a2);
    if ( SstpProxyConfigFromXmlFile )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_29;
      v7 = L"SstpSvcSetConfig: SetSstpProxyConfig failed with error %d";
    }
    else
    {
      SetSstpConfigFlag(1, *a2);
      if ( !*a2 )
        goto LABEL_29;
      SstpProxyConfigFromXmlFile = LoadSstpProxyConfigFromXmlFile();
      if ( !SstpProxyConfigFromXmlFile || (byte_18002D803 & 8) == 0 )
        goto LABEL_29;
      v7 = L"SstpSvcSetConfig: LoadSstpProxyConfigFromXmlFile failed with error %d";
    }
    goto LABEL_26;
  }
  if ( (byte_18002D803 & 8) == 0 )
    goto LABEL_29;
  v7 = L"SstpSvcSetConfig: InitializeSstpServer failed with error %d";
LABEL_26:
  LOWORD(v11) = 0;
  FormatRRASErrorString(&v11, v7, SstpProxyConfigFromXmlFile);
LABEL_27:
  if ( (byte_18002D803 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v11);
LABEL_29:
  v9 = RpcRevertToSelf();
  if ( v9 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"SstpSvcGetConfig: FATAL ERROR. RpcRevertToSelf failed with error %d", v9);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v11);
    }
  }
  if ( v3 && !SstpProxyConfigFromXmlFile )
    return 3011;
  return SstpProxyConfigFromXmlFile;
}

```

## disassembly

```asm
0x180014840  mov     [rsp-8+arg_0], rbx
0x180014845  mov     [rsp-8+arg_10], rsi
0x18001484a  push    rbp
0x18001484b  push    rdi
0x18001484c  push    r13
0x18001484e  push    r14
0x180014850  push    r15
0x180014852  lea     rbp, [rsp-730h]
0x18001485a  sub     rsp, 830h
0x180014861  mov     rax, cs:__security_cookie
0x180014868  xor     rax, rsp
0x18001486b  mov     [rbp+750h+var_30], rax
0x180014872  mov     rdi, rdx
0x180014875  xor     r15b, r15b
0x180014878  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x18001487d  xor     eax, eax
0x18001487f  lea     rcx, [rsp+850h+var_82C]; void *
0x180014884  xor     edx, edx; Val
0x180014886  mov     [rsp+850h+var_830], eax
0x18001488a  mov     r8d, 7FCh; Size
0x180014890  call    memset_0
0x180014895  xor     ecx, ecx; BindingHandle
0x180014897  call    cs:__imp_RpcImpersonateClient
0x18001489d  mov     ebx, eax
0x18001489f  mov     r13b, 8
0x1800148a2  test    eax, eax
0x1800148a4  jz      short loc_1800148C9
0x1800148a6  test    cs:byte_18002D803, r13b
0x1800148ad  jz      loc_180014A2C
0x1800148b3  xor     ecx, ecx
0x1800148b5  lea     rdx, aSstpsvcsetconf_2; "SstpSvcSetConfig: RpcImpersonateClient "...
0x1800148bc  mov     word ptr [rsp+850h+var_830], cx
0x1800148c1  mov     r8d, eax
0x1800148c4  jmp     loc_180014A01
0x1800148c9  cmp     dword ptr [rdi], 0
0x1800148cc  jz      loc_180014973
0x1800148d2  mov     esi, 1
0x1800148d7  mov     ecx, esi
0x1800148d9  call    GetSstpConfigFlag
0x1800148de  cmp     dword ptr [rdi+18h], 0
0x1800148e2  mov     r14d, eax
0x1800148e5  jz      short loc_180014923
0x1800148e7  mov     r9, [rdi+20h]
0x1800148eb  xor     edx, edx
0x1800148ed  mov     r8d, [rdi+4]
0x1800148f1  xor     ecx, ecx
0x1800148f3  call    cs:__imp_SetSstpConfiguration
0x1800148f9  mov     ebx, eax
0x1800148fb  test    eax, eax
0x1800148fd  jz      short loc_180014918
0x1800148ff  test    cs:byte_18002D803, r13b
0x180014906  jz      loc_180014A2C
0x18001490c  lea     rdx, aSstpsvcsetconf_4; "SstpSvcSetConfig: SetSstpConfiguration "...
0x180014913  jmp     loc_1800149F7
0x180014918  cmp     r14d, esi
0x18001491b  movzx   r15d, r15b
0x18001491f  cmovz   r15d, esi
0x180014923  call    cs:__imp_SetupSstpServerConfig
0x180014929  mov     ebx, eax
0x18001492b  test    eax, eax
0x18001492d  jz      short loc_180014948
0x18001492f  test    cs:byte_18002D803, r13b
0x180014936  jz      loc_180014A2C
0x18001493c  lea     rdx, aSstpsvcsetconf; "SstpSvcSetConfig: SetupSstpServerConfig"...
0x180014943  jmp     loc_1800149F7
0x180014948  cmp     [rdi], r14d
0x18001494b  jz      short loc_1800149AC
0x18001494d  xor     ecx, ecx
0x18001494f  call    InitializeSstpServer
0x180014954  mov     ebx, eax
0x180014956  test    eax, eax
0x180014958  jz      short loc_1800149AC
0x18001495a  test    cs:byte_18002D803, r13b
0x180014961  jz      loc_180014A2C
0x180014967  lea     rdx, aSstpsvcsetconf_0; "SstpSvcSetConfig: InitializeSstpServer "...
0x18001496e  jmp     loc_1800149F7
0x180014973  xor     ecx, ecx
0x180014975  call    ShutdownSstpServer
0x18001497a  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x18001497f  mov     esi, 1
0x180014984  mov     rbx, rax
0x180014987  mov     ecx, esi
0x180014989  call    GetSstpConfigFlag
0x18001498e  test    eax, eax
0x180014990  jz      short loc_1800149AC
0x180014992  mov     rcx, rbx; SRWLock
0x180014995  call    cs:__imp_AcquireSRWLockExclusive
0x18001499b  mov     rcx, rbx; this
0x18001499e  call    ?DeleteSstpProxyRules@TenantGatewayMap@@QEAAKXZ; TenantGatewayMap::DeleteSstpProxyRules(void)
0x1800149a3  mov     rcx, rbx; SRWLock
0x1800149a6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800149ac  mov     edx, [rdi]
0x1800149ae  xor     ecx, ecx
0x1800149b0  call    cs:__imp_SetSstpProxyConfig
0x1800149b6  mov     ebx, eax
0x1800149b8  test    eax, eax
0x1800149ba  jz      short loc_1800149CE
0x1800149bc  test    cs:byte_18002D803, r13b
0x1800149c3  jz      short loc_180014A2C
0x1800149c5  lea     rdx, aSstpsvcsetconf_3; "SstpSvcSetConfig: SetSstpProxyConfig fa"...
0x1800149cc  jmp     short loc_1800149F7
0x1800149ce  mov     edx, [rdi]
0x1800149d0  mov     ecx, esi
0x1800149d2  call    SetSstpConfigFlag
0x1800149d7  cmp     dword ptr [rdi], 0
0x1800149da  jz      short loc_180014A2C
0x1800149dc  call    LoadSstpProxyConfigFromXmlFile
0x1800149e1  mov     ebx, eax
0x1800149e3  test    eax, eax
0x1800149e5  jz      short loc_180014A2C
0x1800149e7  test    cs:byte_18002D803, r13b
0x1800149ee  jz      short loc_180014A2C
0x1800149f0  lea     rdx, aSstpsvcsetconf_1; "SstpSvcSetConfig: LoadSstpProxyConfigFr"...
0x1800149f7  xor     eax, eax
0x1800149f9  mov     r8d, ebx
0x1800149fc  mov     word ptr [rsp+850h+var_830], ax
0x180014a01  lea     rcx, [rsp+850h+var_830]
0x180014a06  call    FormatRRASErrorString
0x180014a0b  test    cs:byte_18002D803, r13b
0x180014a12  jz      short loc_180014A2C
0x180014a14  lea     r8, [rsp+850h+var_830]
0x180014a19  lea     rdx, RasSSTPSvcTraceError
0x180014a20  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014a27  call    McTemplateU0z_EventWriteTransfer
0x180014a2c  call    cs:__imp_RpcRevertToSelf
0x180014a32  test    eax, eax
0x180014a34  jz      short loc_180014A7D
0x180014a36  test    cs:byte_18002D803, r13b
0x180014a3d  jz      short loc_180014A7D
0x180014a3f  xor     r8d, r8d
0x180014a42  lea     rdx, aSstpsvcgetconf_0; "SstpSvcGetConfig: FATAL ERROR. RpcRever"...
0x180014a49  mov     word ptr [rsp+850h+var_830], r8w
0x180014a4f  lea     rcx, [rsp+850h+var_830]
0x180014a54  mov     r8d, eax
0x180014a57  call    FormatRRASErrorString
0x180014a5c  test    cs:byte_18002D803, r13b
0x180014a63  jz      short loc_180014A7D
0x180014a65  lea     r8, [rsp+850h+var_830]
0x180014a6a  lea     rdx, RasSSTPSvcTraceError
0x180014a71  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014a78  call    McTemplateU0z_EventWriteTransfer
0x180014a7d  test    r15b, r15b
0x180014a80  jz      short loc_180014A8C
0x180014a82  test    ebx, ebx
0x180014a84  mov     eax, 0BC3h
0x180014a89  cmovz   ebx, eax
0x180014a8c  mov     eax, ebx
0x180014a8e  mov     rcx, [rbp+750h+var_30]
0x180014a95  xor     rcx, rsp; StackCookie
0x180014a98  call    __security_check_cookie
0x180014a9d  lea     r11, [rsp+850h+var_20]
0x180014aa5  mov     rbx, [r11+30h]
0x180014aa9  mov     rsi, [r11+40h]
0x180014aad  mov     rsp, r11
0x180014ab0  pop     r15
0x180014ab2  pop     r14
0x180014ab4  pop     r13
0x180014ab6  pop     rdi
0x180014ab7  pop     rbp
0x180014ab8  retn
```
