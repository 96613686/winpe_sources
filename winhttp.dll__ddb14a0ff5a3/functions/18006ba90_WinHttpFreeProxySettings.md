# WinHttpFreeProxySettings

- ea: `0x18006ba90`
- end: `0x18006bc48`
- name: `WinHttpFreeProxySettings`
- size: `440`
- prototype: `void __stdcall(WINHTTP_PROXY_SETTINGS *pWinHttpProxySettings)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18006ba90`
- `0x1800c82d0`
- `0x1800c830c`
- `0x1800cf008`
- `0x1800db704`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bbb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bbc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bbd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bbeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bbfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bc0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bc21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bbb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bbc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bbd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bbeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bbfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bc0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bc21`

## pseudocode

```c
void __stdcall WinHttpFreeProxySettings(WINHTTP_PROXY_SETTINGS *pWinHttpProxySettings)
{
  PWSTR *p_pwszConnectionName; // rax
  PWSTR v3; // rcx
  PWSTR *p_pwszProxy; // rax
  PWSTR v5; // rcx
  PWSTR *p_pwszProxyBypass; // rax
  PWSTR v7; // rcx
  PWSTR *p_pwszLastKnownGoodAutoConfigUrl; // rax
  PWSTR v9; // rcx
  PWSTR *p_pwszAutoconfigUrl; // rax
  PWSTR v11; // rcx
  PWSTR *p_pwszAutoconfigSecondaryUrl; // rax
  PWSTR v13; // rcx
  PDWORD *p_pdwDetectedInterfaceIp; // rax
  PDWORD v15; // rcx
  PWINHTTP_PROXY_NETWORKING_KEY *p_pNetworkKeys; // rdi
  PWINHTTP_PROXY_NETWORKING_KEY v17; // rcx

  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 52, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids);
  if ( pWinHttpProxySettings )
  {
    p_pwszConnectionName = &pWinHttpProxySettings->pwszConnectionName;
    if ( pWinHttpProxySettings != (WINHTTP_PROXY_SETTINGS *)-16LL )
    {
      v3 = *p_pwszConnectionName;
      if ( *p_pwszConnectionName )
      {
        *p_pwszConnectionName = 0;
        CoTaskMemFree(v3);
      }
    }
    p_pwszProxy = &pWinHttpProxySettings->pwszProxy;
    if ( pWinHttpProxySettings != (WINHTTP_PROXY_SETTINGS *)-24LL )
    {
      v5 = *p_pwszProxy;
      if ( *p_pwszProxy )
      {
        *p_pwszProxy = 0;
        CoTaskMemFree(v5);
      }
    }
    p_pwszProxyBypass = &pWinHttpProxySettings->pwszProxyBypass;
    if ( pWinHttpProxySettings != (WINHTTP_PROXY_SETTINGS *)-32LL )
    {
      v7 = *p_pwszProxyBypass;
      if ( *p_pwszProxyBypass )
      {
        *p_pwszProxyBypass = 0;
        CoTaskMemFree(v7);
      }
    }
    p_pwszLastKnownGoodAutoConfigUrl = &pWinHttpProxySettings->pwszLastKnownGoodAutoConfigUrl;
    if ( pWinHttpProxySettings != (WINHTTP_PROXY_SETTINGS *)-64LL )
    {
      v9 = *p_pwszLastKnownGoodAutoConfigUrl;
      if ( *p_pwszLastKnownGoodAutoConfigUrl )
      {
        *p_pwszLastKnownGoodAutoConfigUrl = 0;
        CoTaskMemFree(v9);
      }
    }
    p_pwszAutoconfigUrl = &pWinHttpProxySettings->pwszAutoconfigUrl;
    if ( pWinHttpProxySettings != (WINHTTP_PROXY_SETTINGS *)-40LL )
    {
      v11 = *p_pwszAutoconfigUrl;
      if ( *p_pwszAutoconfigUrl )
      {
        *p_pwszAutoconfigUrl = 0;
        CoTaskMemFree(v11);
      }
    }
    p_pwszAutoconfigSecondaryUrl = &pWinHttpProxySettings->pwszAutoconfigSecondaryUrl;
    if ( pWinHttpProxySettings != (WINHTTP_PROXY_SETTINGS *)-48LL )
    {
      v13 = *p_pwszAutoconfigSecondaryUrl;
      if ( *p_pwszAutoconfigSecondaryUrl )
      {
        *p_pwszAutoconfigSecondaryUrl = 0;
        CoTaskMemFree(v13);
      }
    }
    p_pdwDetectedInterfaceIp = &pWinHttpProxySettings->pdwDetectedInterfaceIp;
    if ( pWinHttpProxySettings != (WINHTTP_PROXY_SETTINGS *)-88LL )
    {
      v15 = *p_pdwDetectedInterfaceIp;
      if ( *p_pdwDetectedInterfaceIp )
      {
        *p_pdwDetectedInterfaceIp = 0;
        CoTaskMemFree(v15);
      }
    }
    p_pNetworkKeys = &pWinHttpProxySettings->pNetworkKeys;
    if ( p_pNetworkKeys )
    {
      v17 = *p_pNetworkKeys;
      if ( *p_pNetworkKeys )
      {
        *p_pNetworkKeys = 0;
        CoTaskMemFree(v17);
      }
    }
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 53, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids);
}

```

## disassembly

```asm
0x18006ba90  mov     [rsp+arg_0], rsi
0x18006ba95  push    rdi
0x18006ba96  sub     rsp, 30h
0x18006ba9a  mov     rdi, rcx
0x18006ba9d  mov     esi, 1
0x18006baa2  mov     [rsp+38h+var_14], esi
0x18006baa6  test    byte ptr cs:xmmword_180107A60, 20h
0x18006baad  jz      short loc_18006BAC6
0x18006baaf  lea     edx, [rsi+33h]
0x18006bab2  mov     ecx, 405h
0x18006bab7  mov     r9, rdi
0x18006baba  lea     r8, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids
0x18006bac1  call    WPP_SF_q
0x18006bac6  test    rdi, rdi
0x18006bac9  jz      loc_18006BB74
0x18006bacf  lea     rax, [rdi+10h]
0x18006bad3  test    rax, rax
0x18006bad6  jz      short loc_18006BAE4
0x18006bad8  mov     rcx, [rax]; pv
0x18006badb  test    rcx, rcx
0x18006bade  jnz     loc_18006BB9C
0x18006bae4  lea     rax, [rdi+18h]
0x18006bae8  test    rax, rax
0x18006baeb  jz      short loc_18006BAF9
0x18006baed  mov     rcx, [rax]; pv
0x18006baf0  test    rcx, rcx
0x18006baf3  jnz     loc_18006BBAE
0x18006baf9  lea     rax, [rdi+20h]
0x18006bafd  test    rax, rax
0x18006bb00  jz      short loc_18006BB0E
0x18006bb02  mov     rcx, [rax]; pv
0x18006bb05  test    rcx, rcx
0x18006bb08  jnz     loc_18006BBC0
0x18006bb0e  lea     rax, [rdi+40h]
0x18006bb12  test    rax, rax
0x18006bb15  jz      short loc_18006BB23
0x18006bb17  mov     rcx, [rax]; pv
0x18006bb1a  test    rcx, rcx
0x18006bb1d  jnz     loc_18006BBD2
0x18006bb23  lea     rax, [rdi+28h]
0x18006bb27  test    rax, rax
0x18006bb2a  jz      short loc_18006BB38
0x18006bb2c  mov     rcx, [rax]; pv
0x18006bb2f  test    rcx, rcx
0x18006bb32  jnz     loc_18006BBE4
0x18006bb38  lea     rax, [rdi+30h]
0x18006bb3c  test    rax, rax
0x18006bb3f  jz      short loc_18006BB4D
0x18006bb41  mov     rcx, [rax]; pv
0x18006bb44  test    rcx, rcx
0x18006bb47  jnz     loc_18006BBF6
0x18006bb4d  lea     rax, [rdi+58h]
0x18006bb51  test    rax, rax
0x18006bb54  jz      short loc_18006BB62
0x18006bb56  mov     rcx, [rax]; pv
0x18006bb59  test    rcx, rcx
0x18006bb5c  jnz     loc_18006BC08
0x18006bb62  add     rdi, 68h ; 'h'
0x18006bb66  jz      short loc_18006BB74
0x18006bb68  mov     rcx, [rdi]; pv
0x18006bb6b  test    rcx, rcx
0x18006bb6e  jnz     loc_18006BC1A
0x18006bb74  test    byte ptr cs:xmmword_180107A60, 20h
0x18006bb7b  jz      loc_18006BC2C
0x18006bb81  mov     edx, 35h ; '5'
0x18006bb86  mov     ecx, 405h
0x18006bb8b  lea     r8, WPP_2da281ed2f793cb45e1fc5c7f2805ac1_Traceguids
0x18006bb92  call    WPP_SF_
0x18006bb97  jmp     loc_18006BC2C
0x18006bb9c  mov     qword ptr [rax], 0
0x18006bba3  call    cs:__imp_CoTaskMemFree
0x18006bba9  jmp     loc_18006BAE4
0x18006bbae  mov     qword ptr [rax], 0
0x18006bbb5  call    cs:__imp_CoTaskMemFree
0x18006bbbb  jmp     loc_18006BAF9
0x18006bbc0  mov     qword ptr [rax], 0
0x18006bbc7  call    cs:__imp_CoTaskMemFree
0x18006bbcd  jmp     loc_18006BB0E
0x18006bbd2  mov     qword ptr [rax], 0
0x18006bbd9  call    cs:__imp_CoTaskMemFree
0x18006bbdf  jmp     loc_18006BB23
0x18006bbe4  mov     qword ptr [rax], 0
0x18006bbeb  call    cs:__imp_CoTaskMemFree
0x18006bbf1  jmp     loc_18006BB38
0x18006bbf6  mov     qword ptr [rax], 0
0x18006bbfd  call    cs:__imp_CoTaskMemFree
0x18006bc03  jmp     loc_18006BB4D
0x18006bc08  mov     qword ptr [rax], 0
0x18006bc0f  call    cs:__imp_CoTaskMemFree
0x18006bc15  jmp     loc_18006BB62
0x18006bc1a  mov     qword ptr [rdi], 0
0x18006bc21  call    cs:__imp_CoTaskMemFree
0x18006bc27  jmp     loc_18006BB74
0x18006bc2c  jmp     short loc_18006BC32
0x18006bc2e  mov     esi, [rsp+38h+var_14]
0x18006bc32  test    esi, esi
0x18006bc34  jz      short loc_18006BC41
0x18006bc36  mov     rsi, [rsp+38h+arg_0]
0x18006bc3b  add     rsp, 30h
0x18006bc3f  pop     rdi
0x18006bc40  retn
0x18006bc41  call    WxReportSwallowedFatalException
0x18006bc46  jmp     short loc_18006BC36
0x1800ce43b  push    rbp
0x1800ce43d  sub     rsp, 20h
0x1800ce441  mov     rbp, rdx
0x1800ce444  call    WxSaveExceptionFilter
0x1800ce449  mov     [rbp+24h], eax
0x1800ce44c  mov     eax, [rbp+24h]
0x1800ce44f  add     rsp, 20h
0x1800ce453  pop     rbp
0x1800ce454  retn
0x1800ce456  push    rbp
0x1800ce458  sub     rsp, 20h
0x1800ce45c  mov     rbp, rdx
0x1800ce45f  cmp     dword ptr [rbp+24h], 0
0x1800ce463  jnz     short loc_1800CE46B
0x1800ce465  call    WxReportSwallowedFatalException
0x1800ce46b  add     rsp, 20h
0x1800ce46f  pop     rbp
0x1800ce470  retn
```
