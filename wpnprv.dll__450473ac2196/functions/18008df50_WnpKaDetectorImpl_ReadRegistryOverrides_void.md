# WnpKaDetectorImpl::ReadRegistryOverrides(void)

- ea: `0x18008df50`
- end: `0x18008e12e`
- name: `?ReadRegistryOverrides@WnpKaDetectorImpl@@AEAAXXZ`
- size: `478`
- prototype: `void __fastcall(WnpKaDetectorImpl *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008a7fc`
- `0x18008af84`

## callees

- `0x18000fe2c`
- `0x1800852d4`
- `0x18008df50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e0eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e0eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18008dfc8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18008dfc8`

## pseudocode

```c
void __fastcall WnpKaDetectorImpl::ReadRegistryOverrides(WnpKaDetectorImpl *this)
{
  unsigned int v2; // ecx
  unsigned int v3; // eax
  unsigned int v4; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
  }
  hKey = 0;
  v4 = 0;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
          0,
          1u,
          &hKey) )
  {
    if ( (int)WpnRegLoadDWord(hKey, L"KaTimeDivisor", &v4) >= 0 )
    {
      v2 = v4;
      if ( v4 )
      {
        v3 = *((_DWORD *)this + 60) / v4;
        *((_DWORD *)this + 59) = v4;
        *((_DWORD *)this + 60) = v3;
        *((_DWORD *)this + 61) /= v2;
        *((_DWORD *)this + 62) /= v2;
      }
    }
    if ( (int)WpnRegLoadDWord(hKey, L"IdleSucceededCountThresholdForSteadyState", &v4) >= 0 && v4 )
      *((_DWORD *)this + 63) = v4;
    if ( (int)WpnRegLoadDWord(hKey, L"NetworkLossEventTolerance", &v4) >= 0 && v4 )
      *((_DWORD *)this + 64) = v4;
    if ( (int)WpnRegLoadDWord(hKey, L"BypassNCBRegistration", &v4) >= 0 && v4 )
      *((_DWORD *)this + 65) = 1;
    if ( (int)WpnRegLoadDWord(hKey, L"KaMaxTime", &v4) >= 0 && v4 )
      *((_DWORD *)this + 49) = v4;
    if ( (int)WpnRegLoadDWord(hKey, L"KaMinNonworkingTime", &v4) >= 0 && v4 )
      *((_DWORD *)this + 50) = v4;
    RegCloseKey(hKey);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
  }
}

```

## disassembly

```asm
0x18008df50  mov     [rsp-8+arg_0], rbx
0x18008df55  mov     [rsp-8+arg_18], rsi
0x18008df5a  push    rbp
0x18008df5b  mov     rbp, rsp
0x18008df5e  sub     rsp, 30h
0x18008df62  mov     rbx, rcx
0x18008df65  mov     rcx, cs:WPP_GLOBAL_Control
0x18008df6c  lea     rsi, WPP_GLOBAL_Control
0x18008df73  cmp     rcx, rsi
0x18008df76  jz      short loc_18008DF99
0x18008df78  test    byte ptr [rcx+1Ch], 8
0x18008df7c  jz      short loc_18008DF99
0x18008df7e  cmp     byte ptr [rcx+19h], 6
0x18008df82  jb      short loc_18008DF99
0x18008df84  mov     rcx, [rcx+10h]
0x18008df88  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008df8f  mov     edx, 0F7h
0x18008df94  call    WPP_SF_
0x18008df99  lea     rax, [rbp+hKey]
0x18008df9d  mov     [rbp+hKey], 0
0x18008dfa5  mov     r9d, 1; samDesired
0x18008dfab  mov     [rsp+30h+phkResult], rax; phkResult
0x18008dfb0  xor     r8d, r8d; ulOptions
0x18008dfb3  mov     [rbp+arg_8], 0
0x18008dfba  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18008dfc1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008dfc8  call    cs:__imp_RegOpenKeyExA
0x18008dfce  test    eax, eax
0x18008dfd0  jnz     loc_18008E0F1
0x18008dfd6  mov     rcx, [rbp+hKey]; hKey
0x18008dfda  lea     r8, [rbp+arg_8]; unsigned int *
0x18008dfde  lea     rdx, ?g_KaTimeScaleFactor@@3QBGB; "KaTimeDivisor"
0x18008dfe5  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18008dfea  test    eax, eax
0x18008dfec  js      short loc_18008E02B
0x18008dfee  mov     ecx, [rbp+arg_8]
0x18008dff1  test    ecx, ecx
0x18008dff3  jz      short loc_18008E02B
0x18008dff5  mov     eax, [rbx+0F0h]
0x18008dffb  xor     edx, edx
0x18008dffd  div     ecx
0x18008dfff  xor     edx, edx
0x18008e001  mov     [rbx+0ECh], ecx
0x18008e007  mov     [rbx+0F0h], eax
0x18008e00d  mov     eax, [rbx+0F4h]
0x18008e013  div     ecx
0x18008e015  xor     edx, edx
0x18008e017  mov     [rbx+0F4h], eax
0x18008e01d  mov     eax, [rbx+0F8h]
0x18008e023  div     ecx
0x18008e025  mov     [rbx+0F8h], eax
0x18008e02b  mov     rcx, [rbp+hKey]; hKey
0x18008e02f  lea     r8, [rbp+arg_8]; unsigned int *
0x18008e033  lea     rdx, ?g_IdleSucceededCountThresholdForSteadyState@@3QBGB; "IdleSucceededCountThresholdForSteadySta"...
0x18008e03a  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18008e03f  test    eax, eax
0x18008e041  js      short loc_18008E050
0x18008e043  mov     eax, [rbp+arg_8]
0x18008e046  test    eax, eax
0x18008e048  jz      short loc_18008E050
0x18008e04a  mov     [rbx+0FCh], eax
0x18008e050  mov     rcx, [rbp+hKey]; hKey
0x18008e054  lea     r8, [rbp+arg_8]; unsigned int *
0x18008e058  lea     rdx, ?g_NetworkLossEventTolerance@@3QBGB; "NetworkLossEventTolerance"
0x18008e05f  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18008e064  test    eax, eax
0x18008e066  js      short loc_18008E075
0x18008e068  mov     eax, [rbp+arg_8]
0x18008e06b  test    eax, eax
0x18008e06d  jz      short loc_18008E075
0x18008e06f  mov     [rbx+100h], eax
0x18008e075  mov     rcx, [rbp+hKey]; hKey
0x18008e079  lea     r8, [rbp+arg_8]; unsigned int *
0x18008e07d  lea     rdx, ?g_BypassNCBRegistration@@3QBGB; "BypassNCBRegistration"
0x18008e084  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18008e089  test    eax, eax
0x18008e08b  js      short loc_18008E09D
0x18008e08d  cmp     [rbp+arg_8], 0
0x18008e091  jz      short loc_18008E09D
0x18008e093  mov     dword ptr [rbx+104h], 1
0x18008e09d  mov     rcx, [rbp+hKey]; hKey
0x18008e0a1  lea     r8, [rbp+arg_8]; unsigned int *
0x18008e0a5  lea     rdx, ?g_KaMaxTime@@3QBGB; "KaMaxTime"
0x18008e0ac  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18008e0b1  test    eax, eax
0x18008e0b3  js      short loc_18008E0C2
0x18008e0b5  mov     eax, [rbp+arg_8]
0x18008e0b8  test    eax, eax
0x18008e0ba  jz      short loc_18008E0C2
0x18008e0bc  mov     [rbx+0C4h], eax
0x18008e0c2  mov     rcx, [rbp+hKey]; hKey
0x18008e0c6  lea     r8, [rbp+arg_8]; unsigned int *
0x18008e0ca  lea     rdx, ?g_KaMinNonworkingTime@@3QBGB; "KaMinNonworkingTime"
0x18008e0d1  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18008e0d6  test    eax, eax
0x18008e0d8  js      short loc_18008E0E7
0x18008e0da  mov     eax, [rbp+arg_8]
0x18008e0dd  test    eax, eax
0x18008e0df  jz      short loc_18008E0E7
0x18008e0e1  mov     [rbx+0C8h], eax
0x18008e0e7  mov     rcx, [rbp+hKey]; hKey
0x18008e0eb  call    cs:__imp_RegCloseKey
0x18008e0f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e0f8  cmp     rcx, rsi
0x18008e0fb  jz      short loc_18008E11E
0x18008e0fd  test    byte ptr [rcx+1Ch], 8
0x18008e101  jz      short loc_18008E11E
0x18008e103  cmp     byte ptr [rcx+19h], 6
0x18008e107  jb      short loc_18008E11E
0x18008e109  mov     rcx, [rcx+10h]
0x18008e10d  lea     r8, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008e114  mov     edx, 0F8h
0x18008e119  call    WPP_SF_
0x18008e11e  mov     rbx, [rsp+30h+arg_0]
0x18008e123  mov     rsi, [rsp+30h+arg_18]
0x18008e128  add     rsp, 30h
0x18008e12c  pop     rbp
0x18008e12d  retn
```
