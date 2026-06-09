# GlobalDataInitialize(void)

- ea: `0x180013778`
- end: `0x180013d67`
- name: `?GlobalDataInitialize@@YAKXZ`
- size: `1519`
- prototype: `unsigned int(void)`
- caller_count: `9`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a6a0`
- `0x180011970`
- `0x180012f10`
- `0x18001e610`
- `0x1800295a0`
- `0x18004c6d0`
- `0x1800604c0`
- `0x180062570`
- `0x1800a49f0`

## callees

- `0x180013778`
- `0x18001dae0`
- `0x180033af4`
- `0x18004e050`
- `0x180070cfc`
- `0x180070dbc`
- `0x180070f1c`
- `0x180071498`
- `0x180073fc4`
- `0x1800768fc`
- `0x18007d258`
- `0x18007de68`
- `0x1800865b4`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013806`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013806`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013d1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013d1d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001387b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001387b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013c1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013c93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013c1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013c93`

## string_xrefs

- `0x180013949`: `DefaultSecureProtocols`
- `0x180013b83`: `DefaultHttp2StreamReceiveWindowUpdateDelta`
- `0x180013ab4`: `DefaultDisableSecureProtocolFallback`
- `0x1800139a9`: `DisableBranchCache`
- `0x180013924`: `ForceDefaultSecureProtocols`
- `0x180013c6a`: `DisableProxyLinkLocalNameResolution`

## pseudocode

```c
__int64 GlobalDataInitialize(void)
{
  HKEY v0; // rcx
  int v1; // eax
  bool v2; // sf
  HKEY v3; // rcx
  HKEY v4; // rcx
  unsigned int v5; // edx
  const unsigned __int16 *v6; // rcx
  unsigned int v7; // eax
  HKEY v8; // rcx
  HKEY v9; // rcx
  HKEY v10; // rcx
  HKEY v11; // rcx
  HKEY v12; // rcx
  HKEY v13; // rcx
  HKEY v14; // rcx
  HKEY v15; // rcx
  HKEY v16; // rcx
  HKEY v17; // rcx
  HKEY v18; // rcx
  HKEY v19; // rcx
  HKEY v20; // rcx
  HKEY v21; // rcx
  LPDWORD pdwType; // [rsp+20h] [rbp-59h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-59h]
  int v25; // [rsp+40h] [rbp-39h] BYREF
  int v26; // [rsp+44h] [rbp-35h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-31h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v29; // [rsp+54h] [rbp-25h] BYREF
  HKEY v30; // [rsp+58h] [rbp-21h] BYREF
  unsigned int pvData; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v32; // [rsp+64h] [rbp-15h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-11h] BYREF
  int v34; // [rsp+6Ch] [rbp-Dh]
  unsigned int v35; // [rsp+70h] [rbp-9h] BYREF
  unsigned int v36; // [rsp+74h] [rbp-5h] BYREF
  unsigned int v37; // [rsp+78h] [rbp-1h] BYREF
  unsigned int v38; // [rsp+7Ch] [rbp+3h] BYREF
  unsigned int v39; // [rsp+80h] [rbp+7h] BYREF
  unsigned int v40; // [rsp+84h] [rbp+Bh] BYREF
  unsigned int v41; // [rsp+88h] [rbp+Fh] BYREF
  unsigned int v42; // [rsp+8Ch] [rbp+13h] BYREF
  unsigned int v43; // [rsp+90h] [rbp+17h] BYREF
  unsigned int v44; // [rsp+94h] [rbp+1Bh] BYREF
  unsigned int v45; // [rsp+98h] [rbp+1Fh] BYREF
  unsigned int v46; // [rsp+9Ch] [rbp+23h] BYREF
  unsigned int v47; // [rsp+A0h] [rbp+27h] BYREF

  if ( (BYTE2(xmmword_180107A60) & 4) != 0 )
    WPP_SF_(1042, 16, WPP_3940219b5a96348d12e2c9b8a820269d_Traceguids);
  v29 = 10240;
  pcbData = 0;
  v35 = 0;
  v30 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  pvData = 0;
  v32 = 0;
  v47 = 0;
  v25 = 0;
  v26 = 4;
  EnterCriticalSection(&GlobalDataInitCritSec);
  if ( dword_18010833C )
  {
    dword_180108338 = 12172;
  }
  else if ( GlobalDataInitialized )
  {
    dword_180108338 = 0;
  }
  else if ( dword_180108334 )
  {
    dword_180108338 = 12004;
  }
  else
  {
    dword_18010833C = 1;
    WinHttpInitializeEtw();
    if ( !*(_BYTE *)(qword_1801089D0 + 72) && !WinHttpTraceLoggingInitialized )
    {
      TlgRegisterAggregateProviderEx();
      QueryPerformanceFrequency(&g_liResolverFrequency);
      WinHttpTraceLoggingInitialized = 1;
    }
    v33 = 0;
    if ( !InternetReadRegistryDwordKey(
            v0,
            L"ShareCredsWithWinHttp",
            &v33,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings") )
      GLOBAL_CRED_LIST::sm_fEnabled = v33 != 0;
    v34 = 0;
    hObject = (HANDLE)-1LL;
    v1 = Unimpersonate(&hObject);
    v2 = v1 < 0;
    if ( v1 > 0 )
      v2 = 1;
    if ( v2 )
    {
      v34 = 436;
    }
    else if ( (int)WxIsSystemService(&GlobalIsProcessNtService) < 0 )
    {
      v34 = 442;
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      RevertToken(hObject);
    g_TokenBindingEnabled = IsTokenBindingEnabled();
    if ( !InternetReadRegistryDwordKey(
            v3,
            L"ForceDefaultSecureProtocols",
            &v35,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalForceDefaultSecureProtocols = v35 != 0;
    if ( InternetReadRegistryDwordKey(
           v4,
           L"DefaultSecureProtocols",
           &v29,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp")
      || (v7 = v29, (v29 & 0xFFFFD557) != 0)
      || !v29 )
    {
      v7 = 10240;
      v29 = 10240;
    }
    GlobalDefaultSecureProtocols = v7;
    if ( WxGetRegistryDwordWithPolicies(v6, v5, (enum WX_REG_SETTINGS_TYPE *)&v26) )
    {
      GlobalEnableTlsAlgorithmMismatchAcEvent = 1;
      if ( GlobalEnableTlsProtocolsAppCompat )
        GlobalDefaultSecureProtocols |= 0x280u;
    }
    else
    {
      GlobalEnableTlsAlgorithmMismatchAcEvent = 0;
    }
    if ( InternetReadRegistryDwordKey(
           v8,
           L"DisableBranchCache",
           (unsigned int *)&v30,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
    {
      v9 = 0;
      LODWORD(v30) = 0;
    }
    else
    {
      v9 = (HKEY)(unsigned int)v30;
    }
    GlobalEnableBranchCache = (_DWORD)v9 == 0;
    if ( InternetReadRegistryDwordKey(
           v9,
           L"DisableAutoProxyAuth",
           (unsigned int *)&v30 + 1,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
    {
      v10 = 0;
      HIDWORD(v30) = 0;
    }
    else
    {
      v10 = (HKEY)HIDWORD(v30);
    }
    GlobalEnableAutomaticProxyAuth = (_DWORD)v10 == 0;
    if ( !InternetReadRegistryDwordKey(
            v10,
            L"AutoProxyQueryWithFullUrl",
            &v36,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalAutoProxyQueryWithFullUrl = v36 != 0;
    if ( GlobalIsProcessNtService || (int)WxIsProcessAppContainer(&v25) >= 0 && v25 )
      GlobalEnableDefaultHttp2 = 1;
    if ( !InternetReadRegistryDwordKey(
            v11,
            L"EnableDefaultHttp2",
            &v37,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalEnableDefaultHttp2 = v37 != 0;
    if ( GlobalIsProcessNtService || (int)WxIsProcessAppContainer(&v25) >= 0 && v25 )
      GlobalDefaultIpv6FastFallback = 1;
    if ( !InternetReadRegistryDwordKey(
            v12,
            L"DefaultIpv6FastFallback",
            &v38,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalDefaultIpv6FastFallback = v38 != 0;
    if ( !InternetReadRegistryDwordKey(
            v13,
            L"DefaultDisableSecureProtocolFallback",
            &v39,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalDefaultDisableSecureProtocolFallback = v39 != 0;
    if ( !InternetReadRegistryDwordKey(
            v14,
            L"EnableInsecureTlsFallback",
            &v40,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalDefaultEnableInsecureTlsFallback = v40 != 0;
    if ( !InternetReadRegistryDwordKey(
            v15,
            L"EnableHttp2ClientCerts",
            &v41,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalDefaultEnableHttp2ClientCerts = v41 != 0;
    g_GlobalIsHvsiContainer = WxIsHvsiContainer();
    g_GlobalIsHvsiContainerOverride = WxIsHvsiContainerOverride();
    WxIsEdpEnabled();
    if ( !InternetReadRegistryDwordKey(
            v16,
            L"AllowHttp2TransferEncoding",
            &v42,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      g_AllowHttp2TransferEncoding = v42 != 0;
    if ( !InternetReadRegistryDwordKey(
            v17,
            L"DefaultHttp2StreamReceiveWindow",
            &v43,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalDefaultHttp2StreamReceiveWindow = v43;
    if ( !InternetReadRegistryDwordKey(
            v18,
            L"DefaultHttp2StreamReceiveWindowUpdateDelta",
            &v44,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalDefaultHttp2StreamReceiveWindowUpdateDelta = v44;
    if ( !InternetReadRegistryDwordKey(
            v19,
            L"DefaultUseSessionSchCred",
            &v45,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalDefaultUseSessionSchCred = v45 != 0;
    if ( !InternetReadRegistryDwordKey(
            v20,
            L"UseSystemCodepageForRedirects",
            &v46,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp") )
      GlobalUseSystemCodepageForRedirects = v46 != 0;
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
            L"DisableProxyAuthenticationSchemes",
            0x10u,
            0,
            &pvData,
            &pcbData) )
    {
      if ( (BYTE2(xmmword_180107A60) & 4) != 0 )
        WPP_SF_d(1042, 17, WPP_3940219b5a96348d12e2c9b8a820269d_Traceguids, pvData, pdwTypea);
      if ( (pvData & 0xFFFFFEE0) == 0 )
        GlobalDisabledProxyAuthenticationSchemes = pvData;
    }
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
            L"DisableProxyLinkLocalNameResolution",
            0x10u,
            0,
            &v32,
            &pcbData) )
    {
      if ( (BYTE2(xmmword_180107A60) & 4) != 0 )
        WPP_SF_d(1042, 18, WPP_3940219b5a96348d12e2c9b8a820269d_Traceguids, v32, pdwType);
      GlobalDisableProxyLinkLocalNameResolution = v32 != 0;
    }
    if ( !g_fKirAddDisableAiaFlag
      || !InternetReadRegistryDwordKey(
            v21,
            L"DefaultDisableAia",
            &v47,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\WinHttp")
      && (GlobalDefaultDisableAia = 1, !v47) )
    {
      GlobalDefaultDisableAia = 0;
    }
    if ( !dword_180108338 )
      GlobalDataInitialized = 1;
    dword_180108334 = 1;
    dword_18010833C = 0;
  }
  LeaveCriticalSection(&GlobalDataInitCritSec);
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_d(1032, 19, WPP_3940219b5a96348d12e2c9b8a820269d_Traceguids, (unsigned int)dword_180108338, pdwType);
  return (unsigned int)dword_180108338;
}

```

## disassembly

```asm
0x180013778  push    rbp
0x18001377a  push    rbx
0x18001377b  push    rsi
0x18001377c  push    rdi
0x18001377d  lea     rbp, [rsp-3Fh]
0x180013782  sub     rsp, 0B8h
0x180013789  mov     rax, cs:__security_cookie
0x180013790  xor     rax, rsp
0x180013793  mov     [rbp+57h+var_28], rax
0x180013797  test    byte ptr cs:xmmword_180107A60+2, 4
0x18001379e  jz      short loc_1800137B6
0x1800137a0  mov     edx, 10h
0x1800137a5  lea     r8, WPP_3940219b5a96348d12e2c9b8a820269d_Traceguids
0x1800137ac  mov     ecx, 412h
0x1800137b1  call    WPP_SF_
0x1800137b6  xor     ebx, ebx
0x1800137b8  mov     [rbp+57h+var_7C], 2800h
0x1800137bf  lea     rcx, ?GlobalDataInitCritSec@@3UCCritSec@@A; lpCriticalSection
0x1800137c6  mov     [rbp+57h+var_80], ebx
0x1800137c9  mov     [rbp+57h+var_60], ebx
0x1800137cc  mov     dword ptr [rbp+57h+var_78], ebx
0x1800137cf  mov     dword ptr [rbp+57h+var_78+4], ebx
0x1800137d2  mov     [rbp+57h+var_5C], ebx
0x1800137d5  mov     [rbp+57h+var_58], ebx
0x1800137d8  mov     [rbp+57h+var_54], ebx
0x1800137db  mov     [rbp+57h+var_50], ebx
0x1800137de  mov     [rbp+57h+var_4C], ebx
0x1800137e1  mov     [rbp+57h+var_48], ebx
0x1800137e4  mov     [rbp+57h+var_44], ebx
0x1800137e7  mov     [rbp+57h+var_40], ebx
0x1800137ea  mov     [rbp+57h+var_3C], ebx
0x1800137ed  mov     [rbp+57h+var_38], ebx
0x1800137f0  mov     [rbp+57h+var_34], ebx
0x1800137f3  mov     [rbp+57h+var_70], ebx
0x1800137f6  mov     [rbp+57h+var_6C], ebx
0x1800137f9  mov     [rbp+57h+var_30], ebx
0x1800137fc  mov     [rbp+57h+var_90], ebx
0x1800137ff  mov     [rbp+57h+var_8C], 4
0x180013806  call    cs:__imp_EnterCriticalSection
0x18001380c  cmp     cs:dword_18010833C, ebx
0x180013812  lea     esi, [rbx+1]
0x180013815  jz      short loc_180013826
0x180013817  mov     cs:dword_180108338, 2F8Ch
0x180013821  jmp     loc_180013D16
0x180013826  cmp     cs:?GlobalDataInitialized@@3HA, ebx; int GlobalDataInitialized
0x18001382c  jz      short loc_180013839
0x18001382e  mov     cs:dword_180108338, ebx
0x180013834  jmp     loc_180013D16
0x180013839  cmp     cs:dword_180108334, ebx
0x18001383f  jz      short loc_180013850
0x180013841  mov     cs:dword_180108338, 2EE4h
0x18001384b  jmp     loc_180013D16
0x180013850  mov     cs:dword_18010833C, esi
0x180013856  call    ?WinHttpInitializeEtw@@YAXXZ; WinHttpInitializeEtw(void)
0x18001385b  mov     rax, cs:qword_1801089D0
0x180013862  cmp     [rax+48h], bl
0x180013865  jnz     short loc_180013888
0x180013867  cmp     cs:?WinHttpTraceLoggingInitialized@@3EA, bl; uchar WinHttpTraceLoggingInitialized
0x18001386d  jnz     short loc_180013888
0x18001386f  call    TlgRegisterAggregateProviderEx
0x180013874  lea     rcx, ?g_liResolverFrequency@@3T_LARGE_INTEGER@@A; lpFrequency
0x18001387b  call    cs:__imp_QueryPerformanceFrequency
0x180013881  mov     cs:?WinHttpTraceLoggingInitialized@@3EA, sil; uchar WinHttpTraceLoggingInitialized
0x180013888  lea     r9, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001388f  mov     [rbp+57h+var_68], ebx
0x180013892  lea     r8, [rbp+57h+var_68]; unsigned int *
0x180013896  lea     rdx, aSharecredswith; "ShareCredsWithWinHttp"
0x18001389d  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x1800138a2  test    eax, eax
0x1800138a4  jnz     short loc_1800138B4
0x1800138a6  cmp     [rbp+57h+var_68], ebx
0x1800138a9  mov     eax, ebx
0x1800138ab  setnz   al
0x1800138ae  mov     cs:?sm_fEnabled@GLOBAL_CRED_LIST@@0HA, eax; int GLOBAL_CRED_LIST::sm_fEnabled
0x1800138b4  lea     rcx, [rbp+57h+hObject]; void **
0x1800138b8  mov     [rbp+57h+var_64], ebx
0x1800138bb  mov     [rbp+57h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800138c3  call    ?Unimpersonate@@YAKPEAPEAX@Z; Unimpersonate(void * *)
0x1800138c8  test    eax, eax
0x1800138ca  jle     short loc_1800138D6
0x1800138cc  movzx   eax, ax
0x1800138cf  or      eax, 80070000h
0x1800138d4  test    eax, eax
0x1800138d6  jns     short loc_1800138E1
0x1800138d8  mov     [rbp+57h+var_64], 1B4h
0x1800138df  jmp     short loc_1800138F8
0x1800138e1  lea     rcx, ?GlobalIsProcessNtService@@3HA; AccessStatus
0x1800138e8  call    WxIsSystemService
0x1800138ed  test    eax, eax
0x1800138ef  jns     short loc_1800138F8
0x1800138f1  mov     [rbp+57h+var_64], 1BAh
0x1800138f8  mov     rcx, [rbp+57h+hObject]; hObject
0x1800138fc  lea     rax, [rcx-1]
0x180013900  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013904  ja      short loc_18001390B
0x180013906  call    ?RevertToken@@YAXPEAX@Z; RevertToken(void *)
0x18001390b  call    ?IsTokenBindingEnabled@@YAHXZ; IsTokenBindingEnabled(void)
0x180013910  lea     rdi, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180013917  mov     cs:?g_TokenBindingEnabled@@3HA, eax; int g_TokenBindingEnabled
0x18001391d  mov     r9, rdi; unsigned __int16 *
0x180013920  lea     r8, [rbp+57h+var_60]; unsigned int *
0x180013924  lea     rdx, aForcedefaultse; "ForceDefaultSecureProtocols"
0x18001392b  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013930  test    eax, eax
0x180013932  jnz     short loc_180013942
0x180013934  cmp     [rbp+57h+var_60], ebx
0x180013937  mov     eax, ebx
0x180013939  setnz   al
0x18001393c  mov     cs:?GlobalForceDefaultSecureProtocols@@3HA, eax; int GlobalForceDefaultSecureProtocols
0x180013942  mov     r9, rdi; unsigned __int16 *
0x180013945  lea     r8, [rbp+57h+var_7C]; unsigned int *
0x180013949  lea     rdx, aDefaultsecurep; "DefaultSecureProtocols"
0x180013950  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013955  test    eax, eax
0x180013957  jnz     short loc_180013967
0x180013959  mov     eax, [rbp+57h+var_7C]
0x18001395c  test    eax, 0FFFFD557h
0x180013961  jnz     short loc_180013967
0x180013963  test    eax, eax
0x180013965  jnz     short loc_18001396F
0x180013967  mov     eax, 2800h
0x18001396c  mov     [rbp+57h+var_7C], eax
0x18001396f  lea     r8, [rbp+57h+var_8C]; enum WX_REG_SETTINGS_TYPE *
0x180013973  mov     cs:?GlobalDefaultSecureProtocols@@3KA, eax; ulong GlobalDefaultSecureProtocols
0x180013979  call    ?WxGetRegistryDwordWithPolicies@@YAKPEBGKPEAW4WX_REG_SETTINGS_TYPE@@@Z; WxGetRegistryDwordWithPolicies(ushort const *,ulong,WX_REG_SETTINGS_TYPE *)
0x18001397e  test    eax, eax
0x180013980  jz      short loc_18001399C
0x180013982  cmp     cs:?GlobalEnableTlsProtocolsAppCompat@@3HA, ebx; int GlobalEnableTlsProtocolsAppCompat
0x180013988  mov     cs:?GlobalEnableTlsAlgorithmMismatchAcEvent@@3HA, esi; int GlobalEnableTlsAlgorithmMismatchAcEvent
0x18001398e  jz      short loc_1800139A2
0x180013990  or      cs:?GlobalDefaultSecureProtocols@@3KA, 280h; ulong GlobalDefaultSecureProtocols
0x18001399a  jmp     short loc_1800139A2
0x18001399c  mov     cs:?GlobalEnableTlsAlgorithmMismatchAcEvent@@3HA, ebx; int GlobalEnableTlsAlgorithmMismatchAcEvent
0x1800139a2  mov     r9, rdi; unsigned __int16 *
0x1800139a5  lea     r8, [rbp+57h+var_78]; unsigned int *
0x1800139a9  lea     rdx, aDisablebranchc; "DisableBranchCache"
0x1800139b0  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x1800139b5  test    eax, eax
0x1800139b7  jz      short loc_1800139C0
0x1800139b9  mov     ecx, ebx
0x1800139bb  mov     dword ptr [rbp+57h+var_78], ebx
0x1800139be  jmp     short loc_1800139C3
0x1800139c0  mov     ecx, dword ptr [rbp+57h+var_78]; HKEY
0x1800139c3  mov     eax, ebx
0x1800139c5  lea     r8, [rbp+57h+var_78+4]; unsigned int *
0x1800139c9  test    ecx, ecx
0x1800139cb  lea     rdx, aDisableautopro; "DisableAutoProxyAuth"
0x1800139d2  mov     r9, rdi; unsigned __int16 *
0x1800139d5  setz    al
0x1800139d8  mov     cs:?GlobalEnableBranchCache@@3KA, eax; ulong GlobalEnableBranchCache
0x1800139de  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x1800139e3  test    eax, eax
0x1800139e5  jz      short loc_1800139EE
0x1800139e7  mov     ecx, ebx
0x1800139e9  mov     dword ptr [rbp+57h+var_78+4], ebx
0x1800139ec  jmp     short loc_1800139F1
0x1800139ee  mov     ecx, dword ptr [rbp+57h+var_78+4]; HKEY
0x1800139f1  mov     eax, ebx
0x1800139f3  lea     r8, [rbp+57h+var_5C]; unsigned int *
0x1800139f7  test    ecx, ecx
0x1800139f9  lea     rdx, aAutoproxyquery; "AutoProxyQueryWithFullUrl"
0x180013a00  mov     r9, rdi; unsigned __int16 *
0x180013a03  setz    al
0x180013a06  mov     cs:?GlobalEnableAutomaticProxyAuth@@3KA, eax; ulong GlobalEnableAutomaticProxyAuth
0x180013a0c  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013a11  test    eax, eax
0x180013a13  jnz     short loc_180013A23
0x180013a15  cmp     [rbp+57h+var_5C], ebx
0x180013a18  mov     eax, ebx
0x180013a1a  setnz   al
0x180013a1d  mov     cs:?GlobalAutoProxyQueryWithFullUrl@@3KA, eax; ulong GlobalAutoProxyQueryWithFullUrl
0x180013a23  cmp     cs:?GlobalIsProcessNtService@@3HA, ebx; int GlobalIsProcessNtService
0x180013a29  jnz     short loc_180013A3D
0x180013a2b  lea     rcx, [rbp+57h+var_90]; int *
0x180013a2f  call    ?WxIsProcessAppContainer@@YAJPEAH@Z; WxIsProcessAppContainer(int *)
0x180013a34  test    eax, eax
0x180013a36  js      short loc_180013A43
0x180013a38  cmp     [rbp+57h+var_90], ebx
0x180013a3b  jz      short loc_180013A43
0x180013a3d  mov     cs:?GlobalEnableDefaultHttp2@@3HA, esi; int GlobalEnableDefaultHttp2
0x180013a43  mov     r9, rdi; unsigned __int16 *
0x180013a46  lea     r8, [rbp+57h+var_58]; unsigned int *
0x180013a4a  lea     rdx, aEnabledefaulth; "EnableDefaultHttp2"
0x180013a51  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013a56  test    eax, eax
0x180013a58  jnz     short loc_180013A68
0x180013a5a  cmp     [rbp+57h+var_58], ebx
0x180013a5d  mov     eax, ebx
0x180013a5f  setnz   al
0x180013a62  mov     cs:?GlobalEnableDefaultHttp2@@3HA, eax; int GlobalEnableDefaultHttp2
0x180013a68  cmp     cs:?GlobalIsProcessNtService@@3HA, ebx; int GlobalIsProcessNtService
0x180013a6e  jnz     short loc_180013A82
0x180013a70  lea     rcx, [rbp+57h+var_90]; int *
0x180013a74  call    ?WxIsProcessAppContainer@@YAJPEAH@Z; WxIsProcessAppContainer(int *)
0x180013a79  test    eax, eax
0x180013a7b  js      short loc_180013A88
0x180013a7d  cmp     [rbp+57h+var_90], ebx
0x180013a80  jz      short loc_180013A88
0x180013a82  mov     cs:?GlobalDefaultIpv6FastFallback@@3HA, esi; int GlobalDefaultIpv6FastFallback
0x180013a88  mov     r9, rdi; unsigned __int16 *
0x180013a8b  lea     r8, [rbp+57h+var_54]; unsigned int *
0x180013a8f  lea     rdx, aDefaultipv6fas; "DefaultIpv6FastFallback"
0x180013a96  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013a9b  test    eax, eax
0x180013a9d  jnz     short loc_180013AAD
0x180013a9f  cmp     [rbp+57h+var_54], ebx
0x180013aa2  mov     eax, ebx
0x180013aa4  setnz   al
0x180013aa7  mov     cs:?GlobalDefaultIpv6FastFallback@@3HA, eax; int GlobalDefaultIpv6FastFallback
0x180013aad  mov     r9, rdi; unsigned __int16 *
0x180013ab0  lea     r8, [rbp+57h+var_50]; unsigned int *
0x180013ab4  lea     rdx, aDefaultdisable_0; "DefaultDisableSecureProtocolFallback"
0x180013abb  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013ac0  test    eax, eax
0x180013ac2  jnz     short loc_180013AD2
0x180013ac4  cmp     [rbp+57h+var_50], ebx
0x180013ac7  mov     eax, ebx
0x180013ac9  setnz   al
0x180013acc  mov     cs:?GlobalDefaultDisableSecureProtocolFallback@@3HA, eax; int GlobalDefaultDisableSecureProtocolFallback
0x180013ad2  mov     r9, rdi; unsigned __int16 *
0x180013ad5  lea     r8, [rbp+57h+var_4C]; unsigned int *
0x180013ad9  lea     rdx, aEnableinsecure; "EnableInsecureTlsFallback"
0x180013ae0  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013ae5  test    eax, eax
0x180013ae7  jnz     short loc_180013AF7
0x180013ae9  cmp     [rbp+57h+var_4C], ebx
0x180013aec  mov     eax, ebx
0x180013aee  setnz   al
0x180013af1  mov     cs:?GlobalDefaultEnableInsecureTlsFallback@@3HA, eax; int GlobalDefaultEnableInsecureTlsFallback
0x180013af7  mov     r9, rdi; unsigned __int16 *
0x180013afa  lea     r8, [rbp+57h+var_48]; unsigned int *
0x180013afe  lea     rdx, aEnablehttp2cli; "EnableHttp2ClientCerts"
0x180013b05  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013b0a  test    eax, eax
0x180013b0c  jnz     short loc_180013B1C
0x180013b0e  cmp     [rbp+57h+var_48], ebx
0x180013b11  mov     eax, ebx
0x180013b13  setnz   al
0x180013b16  mov     cs:?GlobalDefaultEnableHttp2ClientCerts@@3HA, eax; int GlobalDefaultEnableHttp2ClientCerts
0x180013b1c  call    WxIsHvsiContainer
0x180013b21  mov     cs:?g_GlobalIsHvsiContainer@@3HA, eax; int g_GlobalIsHvsiContainer
0x180013b27  call    WxIsHvsiContainerOverride
0x180013b2c  mov     cs:?g_GlobalIsHvsiContainerOverride@@3HA, eax; int g_GlobalIsHvsiContainerOverride
0x180013b32  call    WxIsEdpEnabled
0x180013b37  mov     r9, rdi; unsigned __int16 *
0x180013b3a  lea     r8, [rbp+57h+var_44]; unsigned int *
0x180013b3e  lea     rdx, aAllowhttp2tran; "AllowHttp2TransferEncoding"
0x180013b45  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013b4a  test    eax, eax
0x180013b4c  jnz     short loc_180013B5C
0x180013b4e  cmp     [rbp+57h+var_44], ebx
0x180013b51  mov     eax, ebx
0x180013b53  setnz   al
0x180013b56  mov     cs:?g_AllowHttp2TransferEncoding@@3HA, eax; int g_AllowHttp2TransferEncoding
0x180013b5c  mov     r9, rdi; unsigned __int16 *
0x180013b5f  lea     r8, [rbp+57h+var_40]; unsigned int *
0x180013b63  lea     rdx, aDefaulthttp2st; "DefaultHttp2StreamReceiveWindow"
0x180013b6a  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013b6f  test    eax, eax
0x180013b71  jnz     short loc_180013B7C
0x180013b73  mov     eax, [rbp+57h+var_40]
0x180013b76  mov     cs:?GlobalDefaultHttp2StreamReceiveWindow@@3KA, eax; ulong GlobalDefaultHttp2StreamReceiveWindow
0x180013b7c  mov     r9, rdi; unsigned __int16 *
0x180013b7f  lea     r8, [rbp+57h+var_3C]; unsigned int *
0x180013b83  lea     rdx, aDefaulthttp2st_0; "DefaultHttp2StreamReceiveWindowUpdateDe"...
0x180013b8a  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013b8f  test    eax, eax
0x180013b91  jnz     short loc_180013B9C
0x180013b93  mov     eax, [rbp+57h+var_3C]
0x180013b96  mov     cs:?GlobalDefaultHttp2StreamReceiveWindowUpdateDelta@@3KA, eax; ulong GlobalDefaultHttp2StreamReceiveWindowUpdateDelta
0x180013b9c  mov     r9, rdi; unsigned __int16 *
0x180013b9f  lea     r8, [rbp+57h+var_38]; unsigned int *
0x180013ba3  lea     rdx, aDefaultusesess; "DefaultUseSessionSchCred"
0x180013baa  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013baf  test    eax, eax
0x180013bb1  jnz     short loc_180013BC1
0x180013bb3  cmp     [rbp+57h+var_38], ebx
0x180013bb6  mov     eax, ebx
0x180013bb8  setnz   al
0x180013bbb  mov     cs:?GlobalDefaultUseSessionSchCred@@3HA, eax; int GlobalDefaultUseSessionSchCred
0x180013bc1  mov     r9, rdi; unsigned __int16 *
0x180013bc4  lea     r8, [rbp+57h+var_34]; unsigned int *
0x180013bc8  lea     rdx, aUsesystemcodep; "UseSystemCodepageForRedirects"
0x180013bcf  call    ?InternetReadRegistryDwordKey@@YAKPEAUHKEY__@@PEBGPEAK1@Z; InternetReadRegistryDwordKey(HKEY__ *,ushort const *,ulong *,ushort const *)
0x180013bd4  test    eax, eax
0x180013bd6  jnz     short loc_180013BE6
0x180013bd8  cmp     [rbp+57h+var_34], ebx
0x180013bdb  mov     eax, ebx
0x180013bdd  setnz   al
0x180013be0  mov     cs:?GlobalUseSystemCodepageForRedirects@@3HA, eax; int GlobalUseSystemCodepageForRedirects
0x180013be6  lea     rax, [rbp+57h+var_80]
0x180013bea  mov     [rbp+57h+var_80], 4
0x180013bf1  mov     [rsp+0D0h+pcbData], rax; pcbData
0x180013bf6  lea     r8, Value; "DisableProxyAuthenticationSchemes"
0x180013bfd  lea     rax, [rbp+57h+var_70]
0x180013c01  mov     r9d, 10h; dwFlags
0x180013c07  mov     [rsp+0D0h+pvData], rax; pvData
0x180013c0c  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180013c13  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180013c1a  mov     [rsp+0D0h+pdwType], rbx; pdwType
  ... truncated ...
```
