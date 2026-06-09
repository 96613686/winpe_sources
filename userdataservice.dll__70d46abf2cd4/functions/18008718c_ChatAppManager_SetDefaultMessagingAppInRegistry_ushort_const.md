# ChatAppManager::_SetDefaultMessagingAppInRegistry(ushort const *)

- ea: `0x18008718c`
- end: `0x180087354`
- name: `?_SetDefaultMessagingAppInRegistry@ChatAppManager@@CAJPEBG@Z`
- size: `456`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e68f0`
- `0x1800e6e5c`

## callees

- `0x180005bac`
- `0x180008f0c`
- `0x180042360`
- `0x180068404`
- `0x18007be90`
- `0x18008718c`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180087259`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180087259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008732b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008732b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180087300`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180087300`

## string_xrefs

- `0x1800871f3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`
- `0x180087278`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatappmanager.cpp`

## pseudocode

```c
__int64 __fastcall ChatAppManager::_SetDefaultMessagingAppInRegistry(const unsigned __int16 *a1)
{
  int PackageInstallTime; // eax
  unsigned int v3; // ebx
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+50h] [rbp-59h] BYREF
  __int64 v11; // [rsp+58h] [rbp-51h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 v13[68]; // [rsp+68h] [rbp-41h] BYREF

  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      ChatAppManager_SetDefaultMessagingAppInRegistry,
      a1);
  v11 = 0;
  PackageInstallTime = GetPackageInstallTime(a1, &v11);
  v3 = PackageInstallTime;
  if ( PackageInstallTime < 0 )
  {
    Log_HREvent(
      (unsigned int)PackageInstallTime,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
      215);
    return v3;
  }
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\UserData\\ChatRT", 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  v3 = Key;
  if ( Key )
  {
    if ( Key > 0 )
      v3 = (unsigned __int16)Key | 0x80070000;
    v7 = 220;
LABEL_10:
    v8 = 0;
    goto LABEL_11;
  }
  memset_0(&Data[4], 0, 0x88u);
  *(_QWORD *)Data = v11;
  v3 = StringCchCopyW(v13, 0x41u, a1);
  if ( (v3 & 0x80000000) != 0 )
  {
    v7 = 226;
    v8 = 1;
LABEL_11:
    Log_HREvent(
      v3,
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatappmanager.cpp",
      v7);
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  v9 = RegSetValueExW(hKey, L"defaultMessagingAppInstanceId", 0, 3u, Data, 0x8Cu);
  v3 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
    v7 = 230;
    goto LABEL_10;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18008718c  mov     [rsp-8+arg_8], rbx
0x180087191  mov     [rsp-8+arg_10], rdi
0x180087196  push    rbp
0x180087197  lea     rbp, [rsp-57h]
0x18008719c  sub     rsp, 100h
0x1800871a3  mov     rax, cs:__security_cookie
0x1800871aa  xor     rax, rsp
0x1800871ad  mov     [rbp+57h+var_10], rax
0x1800871b1  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 10h
0x1800871b8  mov     rdi, rcx
0x1800871bb  jz      short loc_1800871D3
0x1800871bd  mov     r8, rcx
0x1800871c0  lea     rdx, ChatAppManager_SetDefaultMessagingAppInRegistry
0x1800871c7  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x1800871ce  call    McTemplateU0z_EventWriteTransfer
0x1800871d3  lea     rdx, [rbp+57h+var_A8]
0x1800871d7  mov     [rbp+57h+var_A8], 0
0x1800871df  mov     rcx, rdi
0x1800871e2  call    GetPackageInstallTime
0x1800871e7  mov     ebx, eax
0x1800871e9  test    eax, eax
0x1800871eb  jns     short loc_18008720D
0x1800871ed  mov     r9d, 0D7h
0x1800871f3  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800871fa  mov     edx, 1
0x1800871ff  mov     ecx, eax
0x180087201  call    Log_HREvent
0x180087206  mov     eax, ebx
0x180087208  jmp     loc_180087333
0x18008720d  lea     rcx, [rbp+57h+hKey]
0x180087211  mov     [rbp+57h+hKey], 0
0x180087219  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18008721e  mov     [rsp+100h+lpdwDisposition], 0; lpdwDisposition
0x180087227  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\UserData\\ChatRT"
0x18008722e  mov     [rsp+100h+phkResult], rax; phkResult
0x180087233  xor     r9d, r9d; lpClass
0x180087236  mov     [rsp+100h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008723f  xor     r8d, r8d; Reserved
0x180087242  mov     [rsp+100h+samDesired], 0F003Fh; samDesired
0x18008724a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180087251  mov     [rsp+100h+dwOptions], 0; dwOptions
0x180087259  call    cs:__imp_RegCreateKeyExW
0x18008725f  mov     ebx, eax
0x180087261  test    eax, eax
0x180087263  jz      short loc_18008729E
0x180087265  jle     short loc_180087270
0x180087267  movzx   ebx, ax
0x18008726a  or      ebx, 80070000h
0x180087270  mov     r9d, 0DCh
0x180087276  xor     edx, edx
0x180087278  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18008727f  mov     ecx, ebx
0x180087281  call    Log_HREvent
0x180087286  mov     rcx, [rbp+57h+hKey]; hKey
0x18008728a  test    rcx, rcx
0x18008728d  jz      loc_180087206
0x180087293  call    cs:__imp_RegCloseKey
0x180087299  jmp     loc_180087206
0x18008729e  xor     edx, edx; Val
0x1800872a0  lea     rcx, [rbp+57h+Data+4]; void *
0x1800872a4  mov     r8d, 88h; Size
0x1800872aa  call    memset_0
0x1800872af  mov     rax, [rbp+57h+var_A8]
0x1800872b3  lea     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x1800872b7  mov     r8, rdi; unsigned __int16 *
0x1800872ba  mov     qword ptr [rbp+57h+Data], rax
0x1800872be  mov     edx, 41h ; 'A'; unsigned __int64
0x1800872c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800872c8  mov     ebx, eax
0x1800872ca  test    eax, eax
0x1800872cc  jns     short loc_1800872DB
0x1800872ce  mov     r9d, 0E2h
0x1800872d4  mov     edx, 1
0x1800872d9  jmp     short loc_180087278
0x1800872db  mov     rcx, [rbp+57h+hKey]; hKey
0x1800872df  lea     rax, [rbp+57h+Data]
0x1800872e3  mov     [rsp+100h+samDesired], 8Ch; cbData
0x1800872eb  lea     rdx, aDefaultmessagi; "defaultMessagingAppInstanceId"
0x1800872f2  mov     r9d, 3; dwType
0x1800872f8  mov     qword ptr [rsp+100h+dwOptions], rax; lpData
0x1800872fd  xor     r8d, r8d; Reserved
0x180087300  call    cs:__imp_RegSetValueExW
0x180087306  mov     ebx, eax
0x180087308  test    eax, eax
0x18008730a  jz      short loc_180087322
0x18008730c  jle     short loc_180087317
0x18008730e  movzx   ebx, ax
0x180087311  or      ebx, 80070000h
0x180087317  mov     r9d, 0E6h
0x18008731d  jmp     loc_180087276
0x180087322  mov     rcx, [rbp+57h+hKey]; hKey
0x180087326  test    rcx, rcx
0x180087329  jz      short loc_180087331
0x18008732b  call    cs:__imp_RegCloseKey
0x180087331  xor     eax, eax
0x180087333  mov     rcx, [rbp+57h+var_10]
0x180087337  xor     rcx, rsp; StackCookie
0x18008733a  call    __security_check_cookie
0x18008733f  lea     r11, [rsp+100h+var_s0]
0x180087347  mov     rbx, [r11+18h]
0x18008734b  mov     rdi, [r11+20h]
0x18008734f  mov     rsp, r11
0x180087352  pop     rbp
0x180087353  retn
```
