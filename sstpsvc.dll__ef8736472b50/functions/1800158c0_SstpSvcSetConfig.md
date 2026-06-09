# SstpSvcSetConfig

- ea: `0x1800158c0`
- end: `0x180015b64`
- name: `SstpSvcSetConfig`
- size: `676`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180006f00`
- `0x180008404`
- `0x1800089dc`
- `0x180008b90`
- `0x180008c70`
- `0x18000bd24`
- `0x18000d444`
- `0x180011a14`
- `0x180014484`
- `0x1800158c0`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015a27`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015a27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015a3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015a3e`
- `RPCRT4!RpcRevertToSelf` at `0x180015ad0`
- `RPCRT4!RpcRevertToSelf` at `0x180015ad0`
- `RPCRT4!RpcImpersonateClient` at `0x180015917`
- `RPCRT4!RpcImpersonateClient` at `0x180015917`
- `sstpcfg!SetSstpProxyConfig` at `0x180015a4e`
- `sstpcfg!SetSstpProxyConfig` at `0x180015a4e`
- `sstpcfg!SetSstpConfiguration` at `0x180015979`
- `sstpcfg!SetSstpConfiguration` at `0x180015979`
- `sstpcfg!SetupSstpServerConfig` at `0x1800159af`
- `sstpcfg!SetupSstpServerConfig` at `0x1800159af`

## string_xrefs

- `0x18001593b`: `SstpSvcSetConfig: RpcImpersonateClient failed with error %d`
- `0x180015998`: `SstpSvcSetConfig: SetSstpConfiguration failed with error %d`
- `0x1800159ce`: `SstpSvcSetConfig: SetupSstpServerConfig failed with error %d`
- `0x1800159f9`: `SstpSvcSetConfig: InitializeSstpServer failed with error %d`
- `0x180015a69`: `SstpSvcSetConfig: SetSstpProxyConfig failed with error %d`
- `0x180015a94`: `SstpSvcSetConfig: LoadSstpProxyConfigFromXmlFile failed with error %d`
- `0x180015aec`: `SstpSvcGetConfig: FATAL ERROR. RpcRevertToSelf failed with error %d`

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
    if ( (byte_18002E903 & 8) == 0 )
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
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_29;
      v7 = L"SstpSvcSetConfig: SetSstpConfiguration failed with error %d";
      goto LABEL_26;
    }
    v3 = SstpConfigFlag == 1;
  }
  SstpProxyConfigFromXmlFile = SetupSstpServerConfig();
  if ( SstpProxyConfigFromXmlFile )
  {
    if ( (byte_18002E903 & 8) == 0 )
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
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_29;
      v7 = L"SstpSvcSetConfig: SetSstpProxyConfig failed with error %d";
    }
    else
    {
      SetSstpConfigFlag(1, *a2);
      if ( !*a2 )
        goto LABEL_29;
      SstpProxyConfigFromXmlFile = LoadSstpProxyConfigFromXmlFile();
      if ( !SstpProxyConfigFromXmlFile || (byte_18002E903 & 8) == 0 )
        goto LABEL_29;
      v7 = L"SstpSvcSetConfig: LoadSstpProxyConfigFromXmlFile failed with error %d";
    }
    goto LABEL_26;
  }
  if ( (byte_18002E903 & 8) == 0 )
    goto LABEL_29;
  v7 = L"SstpSvcSetConfig: InitializeSstpServer failed with error %d";
LABEL_26:
  LOWORD(v11) = 0;
  FormatRRASErrorString(&v11, v7, SstpProxyConfigFromXmlFile);
LABEL_27:
  if ( (byte_18002E903 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v11);
LABEL_29:
  v9 = RpcRevertToSelf();
  if ( v9 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"SstpSvcGetConfig: FATAL ERROR. RpcRevertToSelf failed with error %d", v9);
      if ( (byte_18002E903 & 8) != 0 )
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
0x1800158c0  mov     [rsp-8+arg_0], rbx
0x1800158c5  mov     [rsp-8+arg_10], rsi
0x1800158ca  push    rbp
0x1800158cb  push    rdi
0x1800158cc  push    r13
0x1800158ce  push    r14
0x1800158d0  push    r15
0x1800158d2  lea     rbp, [rsp-730h]
0x1800158da  sub     rsp, 830h
0x1800158e1  mov     rax, cs:__security_cookie
0x1800158e8  xor     rax, rsp
0x1800158eb  mov     [rbp+750h+var_30], rax
0x1800158f2  mov     rdi, rdx
0x1800158f5  xor     r15b, r15b
0x1800158f8  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x1800158fd  xor     eax, eax
0x1800158ff  lea     rcx, [rsp+850h+var_82C]; void *
0x180015904  xor     edx, edx; Val
0x180015906  mov     [rsp+850h+var_830], eax
0x18001590a  mov     r8d, 7FCh; Size
0x180015910  call    memset_0
0x180015915  xor     ecx, ecx; BindingHandle
0x180015917  call    cs:__imp_RpcImpersonateClient
0x18001591e  nop     dword ptr [rax+rax+00h]
0x180015923  mov     ebx, eax
0x180015925  mov     r13b, 8
0x180015928  test    eax, eax
0x18001592a  jz      short loc_18001594F
0x18001592c  test    cs:byte_18002E903, r13b
0x180015933  jz      loc_180015AD0
0x180015939  xor     ecx, ecx
0x18001593b  lea     rdx, aSstpsvcsetconf_2; "SstpSvcSetConfig: RpcImpersonateClient "...
0x180015942  mov     word ptr [rsp+850h+var_830], cx
0x180015947  mov     r8d, eax
0x18001594a  jmp     loc_180015AA5
0x18001594f  cmp     dword ptr [rdi], 0
0x180015952  jz      loc_180015A05
0x180015958  mov     esi, 1
0x18001595d  mov     ecx, esi
0x18001595f  call    GetSstpConfigFlag
0x180015964  cmp     dword ptr [rdi+18h], 0
0x180015968  mov     r14d, eax
0x18001596b  jz      short loc_1800159AF
0x18001596d  mov     r9, [rdi+20h]
0x180015971  xor     edx, edx
0x180015973  mov     r8d, [rdi+4]
0x180015977  xor     ecx, ecx
0x180015979  call    cs:__imp_SetSstpConfiguration
0x180015980  nop     dword ptr [rax+rax+00h]
0x180015985  mov     ebx, eax
0x180015987  test    eax, eax
0x180015989  jz      short loc_1800159A4
0x18001598b  test    cs:byte_18002E903, r13b
0x180015992  jz      loc_180015AD0
0x180015998  lea     rdx, aSstpsvcsetconf_4; "SstpSvcSetConfig: SetSstpConfiguration "...
0x18001599f  jmp     loc_180015A9B
0x1800159a4  cmp     r14d, esi
0x1800159a7  movzx   r15d, r15b
0x1800159ab  cmovz   r15d, esi
0x1800159af  call    cs:__imp_SetupSstpServerConfig
0x1800159b6  nop     dword ptr [rax+rax+00h]
0x1800159bb  mov     ebx, eax
0x1800159bd  test    eax, eax
0x1800159bf  jz      short loc_1800159DA
0x1800159c1  test    cs:byte_18002E903, r13b
0x1800159c8  jz      loc_180015AD0
0x1800159ce  lea     rdx, aSstpsvcsetconf; "SstpSvcSetConfig: SetupSstpServerConfig"...
0x1800159d5  jmp     loc_180015A9B
0x1800159da  cmp     [rdi], r14d
0x1800159dd  jz      short loc_180015A4A
0x1800159df  xor     ecx, ecx
0x1800159e1  call    InitializeSstpServer
0x1800159e6  mov     ebx, eax
0x1800159e8  test    eax, eax
0x1800159ea  jz      short loc_180015A4A
0x1800159ec  test    cs:byte_18002E903, r13b
0x1800159f3  jz      loc_180015AD0
0x1800159f9  lea     rdx, aSstpsvcsetconf_0; "SstpSvcSetConfig: InitializeSstpServer "...
0x180015a00  jmp     loc_180015A9B
0x180015a05  xor     ecx, ecx
0x180015a07  call    ShutdownSstpServer
0x180015a0c  call    ?GetInstance@TenantGatewayMap@@SAPEAV1@XZ; TenantGatewayMap::GetInstance(void)
0x180015a11  mov     esi, 1
0x180015a16  mov     rbx, rax
0x180015a19  mov     ecx, esi
0x180015a1b  call    GetSstpConfigFlag
0x180015a20  test    eax, eax
0x180015a22  jz      short loc_180015A4A
0x180015a24  mov     rcx, rbx; SRWLock
0x180015a27  call    cs:__imp_AcquireSRWLockExclusive
0x180015a2e  nop     dword ptr [rax+rax+00h]
0x180015a33  mov     rcx, rbx; this
0x180015a36  call    ?DeleteSstpProxyRules@TenantGatewayMap@@QEAAKXZ; TenantGatewayMap::DeleteSstpProxyRules(void)
0x180015a3b  mov     rcx, rbx; SRWLock
0x180015a3e  call    cs:__imp_ReleaseSRWLockExclusive
0x180015a45  nop     dword ptr [rax+rax+00h]
0x180015a4a  mov     edx, [rdi]
0x180015a4c  xor     ecx, ecx
0x180015a4e  call    cs:__imp_SetSstpProxyConfig
0x180015a55  nop     dword ptr [rax+rax+00h]
0x180015a5a  mov     ebx, eax
0x180015a5c  test    eax, eax
0x180015a5e  jz      short loc_180015A72
0x180015a60  test    cs:byte_18002E903, r13b
0x180015a67  jz      short loc_180015AD0
0x180015a69  lea     rdx, aSstpsvcsetconf_3; "SstpSvcSetConfig: SetSstpProxyConfig fa"...
0x180015a70  jmp     short loc_180015A9B
0x180015a72  mov     edx, [rdi]
0x180015a74  mov     ecx, esi
0x180015a76  call    SetSstpConfigFlag
0x180015a7b  cmp     dword ptr [rdi], 0
0x180015a7e  jz      short loc_180015AD0
0x180015a80  call    LoadSstpProxyConfigFromXmlFile
0x180015a85  mov     ebx, eax
0x180015a87  test    eax, eax
0x180015a89  jz      short loc_180015AD0
0x180015a8b  test    cs:byte_18002E903, r13b
0x180015a92  jz      short loc_180015AD0
0x180015a94  lea     rdx, aSstpsvcsetconf_1; "SstpSvcSetConfig: LoadSstpProxyConfigFr"...
0x180015a9b  xor     eax, eax
0x180015a9d  mov     r8d, ebx
0x180015aa0  mov     word ptr [rsp+850h+var_830], ax
0x180015aa5  lea     rcx, [rsp+850h+var_830]
0x180015aaa  call    FormatRRASErrorString
0x180015aaf  test    cs:byte_18002E903, r13b
0x180015ab6  jz      short loc_180015AD0
0x180015ab8  lea     r8, [rsp+850h+var_830]
0x180015abd  lea     rdx, RasSSTPSvcTraceError
0x180015ac4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015acb  call    McTemplateU0z_EventWriteTransfer
0x180015ad0  call    cs:__imp_RpcRevertToSelf
0x180015ad7  nop     dword ptr [rax+rax+00h]
0x180015adc  test    eax, eax
0x180015ade  jz      short loc_180015B27
0x180015ae0  test    cs:byte_18002E903, r13b
0x180015ae7  jz      short loc_180015B27
0x180015ae9  xor     r8d, r8d
0x180015aec  lea     rdx, aSstpsvcgetconf_0; "SstpSvcGetConfig: FATAL ERROR. RpcRever"...
0x180015af3  mov     word ptr [rsp+850h+var_830], r8w
0x180015af9  lea     rcx, [rsp+850h+var_830]
0x180015afe  mov     r8d, eax
0x180015b01  call    FormatRRASErrorString
0x180015b06  test    cs:byte_18002E903, r13b
0x180015b0d  jz      short loc_180015B27
0x180015b0f  lea     r8, [rsp+850h+var_830]
0x180015b14  lea     rdx, RasSSTPSvcTraceError
0x180015b1b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015b22  call    McTemplateU0z_EventWriteTransfer
0x180015b27  test    r15b, r15b
0x180015b2a  jz      short loc_180015B36
0x180015b2c  test    ebx, ebx
0x180015b2e  mov     eax, 0BC3h
0x180015b33  cmovz   ebx, eax
0x180015b36  mov     eax, ebx
0x180015b38  mov     rcx, [rbp+750h+var_30]
0x180015b3f  xor     rcx, rsp; StackCookie
0x180015b42  call    __security_check_cookie
0x180015b47  lea     r11, [rsp+850h+var_20]
0x180015b4f  mov     rbx, [r11+30h]
0x180015b53  mov     rsi, [r11+40h]
0x180015b57  mov     rsp, r11
0x180015b5a  pop     r15
0x180015b5c  pop     r14
0x180015b5e  pop     r13
0x180015b60  pop     rdi
0x180015b61  pop     rbp
0x180015b62  retn
```
