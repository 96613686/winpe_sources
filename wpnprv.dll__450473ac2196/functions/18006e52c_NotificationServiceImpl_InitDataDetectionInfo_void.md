# NotificationServiceImpl::InitDataDetectionInfo(void)

- ea: `0x18006e52c`
- end: `0x18006e71b`
- name: `?InitDataDetectionInfo@NotificationServiceImpl@@AEAAJXZ`
- size: `495`
- prototype: `__int64 __fastcall(NotificationServiceImpl *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006c720`
- `0x1800709d0`
- `0x180071770`

## callees

- `0x18000fe2c`
- `0x18000fe54`
- `0x18006e52c`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e5e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e65a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e6cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e5e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e65a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e6cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e5af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e622`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e695`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e5af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e622`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e695`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall NotificationServiceImpl::InitDataDetectionInfo(NotificationServiceImpl *this)
{
  unsigned int v3; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  hKey = 0;
  v3 = 0;
  *((_DWORD *)this + 47) = 60;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
          0,
          0x20019u,
          &hKey)
    && (int)WpnRegLoadDWord(hKey, L"SignalStrengthChangePeriod", &v3) >= 0
    && v3 )
  {
    *((_DWORD *)this + 47) = v3;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v3 = 0;
  *((_DWORD *)this + 48) = 25;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
          0,
          0x20019u,
          &hKey)
    && (int)WpnRegLoadDWord(hKey, L"MinimumWifiSignalStrength", &v3) >= 0
    && v3 )
  {
    *((_DWORD *)this + 48) = v3;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v3 = 0;
  *((_DWORD *)this + 49) = 35;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
          0,
          0x20019u,
          &hKey)
    && (int)WpnRegLoadDWord(hKey, L"MinimumWifiSignalStrengthDelta", &v3) >= 0
    && v3 )
  {
    *((_DWORD *)this + 49) = v3;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 255, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18006e52c  mov     [rsp-18h+arg_10], rbx
0x18006e531  push    rbp
0x18006e532  push    rsi
0x18006e533  push    r12
0x18006e535  mov     rbp, rsp
0x18006e538  sub     rsp, 30h
0x18006e53c  mov     rbx, rcx
0x18006e53f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e546  lea     rsi, WPP_GLOBAL_Control
0x18006e54d  cmp     rcx, rsi
0x18006e550  jz      short loc_18006E573
0x18006e552  test    byte ptr [rcx+1Ch], 2
0x18006e556  jz      short loc_18006E573
0x18006e558  cmp     byte ptr [rcx+19h], 6
0x18006e55c  jb      short loc_18006E573
0x18006e55e  mov     rcx, [rcx+10h]
0x18006e562  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006e569  mov     edx, 0FEh
0x18006e56e  call    WPP_SF_
0x18006e573  lea     rax, [rbp+hKey]
0x18006e577  mov     [rbp+hKey], 0
0x18006e57f  mov     r12, 0FFFFFFFF80000002h
0x18006e586  mov     [rbp+arg_0], 0
0x18006e58d  mov     rcx, r12; hKey
0x18006e590  mov     dword ptr [rbx+0BCh], 3Ch ; '<'
0x18006e59a  mov     r9d, 20019h; samDesired
0x18006e5a0  mov     [rsp+30h+phkResult], rax; phkResult
0x18006e5a5  xor     r8d, r8d; ulOptions
0x18006e5a8  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006e5af  call    cs:__imp_RegOpenKeyExW
0x18006e5b5  test    eax, eax
0x18006e5b7  jnz     short loc_18006E5DE
0x18006e5b9  mov     rcx, [rbp+hKey]; hKey
0x18006e5bd  lea     r8, [rbp+arg_0]; unsigned int *
0x18006e5c1  lea     rdx, aSignalstrength; "SignalStrengthChangePeriod"
0x18006e5c8  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18006e5cd  test    eax, eax
0x18006e5cf  js      short loc_18006E5DE
0x18006e5d1  mov     eax, [rbp+arg_0]
0x18006e5d4  test    eax, eax
0x18006e5d6  jz      short loc_18006E5DE
0x18006e5d8  mov     [rbx+0BCh], eax
0x18006e5de  mov     rcx, [rbp+hKey]; hKey
0x18006e5e2  test    rcx, rcx
0x18006e5e5  jz      short loc_18006E5F5
0x18006e5e7  call    cs:__imp_RegCloseKey
0x18006e5ed  mov     [rbp+hKey], 0
0x18006e5f5  lea     rax, [rbp+hKey]
0x18006e5f9  mov     [rbp+arg_0], 0
0x18006e600  mov     r9d, 20019h; samDesired
0x18006e606  mov     [rsp+30h+phkResult], rax; phkResult
0x18006e60b  xor     r8d, r8d; ulOptions
0x18006e60e  mov     dword ptr [rbx+0C0h], 19h
0x18006e618  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006e61f  mov     rcx, r12; hKey
0x18006e622  call    cs:__imp_RegOpenKeyExW
0x18006e628  test    eax, eax
0x18006e62a  jnz     short loc_18006E651
0x18006e62c  mov     rcx, [rbp+hKey]; hKey
0x18006e630  lea     r8, [rbp+arg_0]; unsigned int *
0x18006e634  lea     rdx, aMinimumwifisig_0; "MinimumWifiSignalStrength"
0x18006e63b  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18006e640  test    eax, eax
0x18006e642  js      short loc_18006E651
0x18006e644  mov     eax, [rbp+arg_0]
0x18006e647  test    eax, eax
0x18006e649  jz      short loc_18006E651
0x18006e64b  mov     [rbx+0C0h], eax
0x18006e651  mov     rcx, [rbp+hKey]; hKey
0x18006e655  test    rcx, rcx
0x18006e658  jz      short loc_18006E668
0x18006e65a  call    cs:__imp_RegCloseKey
0x18006e660  mov     [rbp+hKey], 0
0x18006e668  lea     rax, [rbp+hKey]
0x18006e66c  mov     [rbp+arg_0], 0
0x18006e673  mov     r9d, 20019h; samDesired
0x18006e679  mov     [rsp+30h+phkResult], rax; phkResult
0x18006e67e  xor     r8d, r8d; ulOptions
0x18006e681  mov     dword ptr [rbx+0C4h], 23h ; '#'
0x18006e68b  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006e692  mov     rcx, r12; hKey
0x18006e695  call    cs:__imp_RegOpenKeyExW
0x18006e69b  test    eax, eax
0x18006e69d  jnz     short loc_18006E6C4
0x18006e69f  mov     rcx, [rbp+hKey]; hKey
0x18006e6a3  lea     r8, [rbp+arg_0]; unsigned int *
0x18006e6a7  lea     rdx, aMinimumwifisig; "MinimumWifiSignalStrengthDelta"
0x18006e6ae  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18006e6b3  test    eax, eax
0x18006e6b5  js      short loc_18006E6C4
0x18006e6b7  mov     eax, [rbp+arg_0]
0x18006e6ba  test    eax, eax
0x18006e6bc  jz      short loc_18006E6C4
0x18006e6be  mov     [rbx+0C4h], eax
0x18006e6c4  mov     rcx, [rbp+hKey]; hKey
0x18006e6c8  test    rcx, rcx
0x18006e6cb  jz      short loc_18006E6DB
0x18006e6cd  call    cs:__imp_RegCloseKey
0x18006e6d3  mov     [rbp+hKey], 0
0x18006e6db  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e6e2  cmp     rcx, rsi
0x18006e6e5  jz      short loc_18006E70B
0x18006e6e7  test    byte ptr [rcx+1Ch], 2
0x18006e6eb  jz      short loc_18006E70B
0x18006e6ed  cmp     byte ptr [rcx+19h], 6
0x18006e6f1  jb      short loc_18006E70B
0x18006e6f3  mov     rcx, [rcx+10h]
0x18006e6f7  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006e6fe  mov     edx, 0FFh
0x18006e703  xor     r9d, r9d
0x18006e706  call    WPP_SF_d
0x18006e70b  mov     rbx, [rsp+30h+arg_10]
0x18006e710  xor     eax, eax
0x18006e712  add     rsp, 30h
0x18006e716  pop     r12
0x18006e718  pop     rsi
0x18006e719  pop     rbp
0x18006e71a  retn
```
