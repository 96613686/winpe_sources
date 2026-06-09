# WPDLibEnumerateCustomKeys

- ea: `0x180004f10`
- end: `0x180005416`
- name: `WPDLibEnumerateCustomKeys`
- size: `1286`
- prototype: `char *__fastcall(int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180004f10`
- `0x180005420`
- `0x180007f68`
- `0x1800097d0`
- `0x1800127ec`
- `0x180012ef8`
- `0x1800137a0`
- `0x1800138c4`
- `0x180014334`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000509c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000509c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005359`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005364`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005359`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005364`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000525e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800052ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000525e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800052ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800052a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800052a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000518f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000518f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800051d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053ff`
- `KERNEL32!RegOpenCurrentUser` at `0x180005147`
- `KERNEL32!RegOpenCurrentUser` at `0x180005147`
- `KERNEL32!RegEnumValueW` at `0x180005325`
- `KERNEL32!RegEnumValueW` at `0x180005325`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005091`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005091`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005057`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005057`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005083`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800051bb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005083`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800051bb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800053f0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800053f0`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x180004fbc`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x180004fbc`
- `WTSAPI32!WTSQueryUserToken` at `0x180005045`
- `WTSAPI32!WTSQueryUserToken` at `0x180005045`
- `WTSAPI32!WTSFreeMemory` at `0x1800050c9`
- `WTSAPI32!WTSFreeMemory` at `0x1800050c9`

## string_xrefs

- `0x180005228`: `Deny_Read`
- `0x180005219`: `Deny_Write`

## pseudocode

```c
char *__fastcall WPDLibEnumerateCustomKeys(int a1)
{
  PSECURITY_DESCRIPTOR v2; // rsi
  char *v3; // rbx
  char *n; // rdi
  DWORD v6; // edi
  WTS_CONNECTSTATE_CLASS State; // edx
  __int64 v8; // r14
  _QWORD *v9; // rsi
  void *v10; // r15
  char *m; // rax
  char *k; // r14
  unsigned int v13; // ecx
  unsigned int i; // r15d
  const WCHAR *v15; // rbx
  int v16; // r14d
  DWORD j; // ebx
  struct _ACL *v18; // rcx
  PSECURITY_DESCRIPTOR v19; // rcx
  DWORD pCount[2]; // [rsp+48h] [rbp-C0h] BYREF
  char *v21; // [rsp+50h] [rbp-B8h] BYREF
  DWORD cchValueName[2]; // [rsp+58h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+60h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-A0h] BYREF
  HKEY v25; // [rsp+70h] [rbp-98h] BYREF
  void *phToken; // [rsp+78h] [rbp-90h] BYREF
  DWORD cbData; // [rsp+80h] [rbp-88h] BYREF
  DWORD Type; // [rsp+84h] [rbp-84h] BYREF
  HKEY v29; // [rsp+88h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-78h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+98h] [rbp-70h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-68h] BYREF
  WCHAR ValueName[64]; // [rsp+B8h] [rbp-50h] BYREF

  v25 = 0;
  ppSessionInfo = 0;
  phToken = 0;
  pCount[1] = 0;
  v2 = 0;
  pSecurityDescriptor = 0;
  hKey = 0;
  phkResult = 0;
  cchValueName[0] = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\RemovableStorageDevices\\Custom",
         0,
         0x20019u,
         &hKey) )
  {
    v3 = 0;
  }
  else
  {
    v21 = 0;
    for ( i = 0; i < 4; ++i )
    {
      if ( i )
      {
        if ( i == 1 )
        {
          v15 = L"Deny_Read";
          v16 = 4;
        }
        else if ( i == 2 )
        {
          v15 = L"Deny_Write";
          v16 = 2;
        }
        else
        {
          v15 = L"Deny_Execute";
          v16 = 1;
        }
      }
      else
      {
        v15 = L"Deny_All";
        v16 = 7;
      }
      if ( !RegOpenKeyExW(hKey, v15, 0, 0x20019u, &phkResult) )
      {
        pCount[0] = 0;
        Type = 4;
        cbData = 4;
        if ( RegQueryValueExW(phkResult, v15, 0, &Type, (LPBYTE)pCount, &cbData) )
        {
          pCount[0] = 0;
        }
        else if ( pCount[0] == 1 )
        {
          v29 = 0;
          v32 = 0;
          if ( !RegOpenKeyExW(phkResult, L"List", 0, 0x20019u, &v29) )
          {
            for ( j = 0; ; ++j )
            {
              cchValueName[0] = 64;
              if ( RegEnumValueW(v29, j, ValueName, cchValueName, 0, 0, 0, 0)
                || !(unsigned int)WPDLibConvertStringGUIDToGUID(ValueName, &v32) )
              {
                break;
              }
              UpdateAccessMaskForGUID(&v21, &v32, v16);
            }
            RegCloseKey(v29);
          }
        }
        RegCloseKey(phkResult);
      }
    }
    RegCloseKey(hKey);
    v3 = v21;
    for ( k = v21; k; k = *(char **)k )
    {
      v13 = *((_DWORD *)k + 11);
      v21 = 0;
      if ( !(unsigned int)BuildMachinePolicyACL(v13, (HLOCAL *)&v21) )
        *((_QWORD *)k + 1) = v21;
    }
  }
  if ( a1 != 1 && WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount[1]) )
  {
    v6 = 0;
    if ( pCount[1] )
    {
      do
      {
        State = ppSessionInfo[v6].State;
        if ( State == WTSDisconnected || (unsigned int)State <= WTSConnected )
        {
          v8 = 0;
          if ( WTSQueryUserToken(ppSessionInfo[v6].SessionId, &phToken) )
          {
            v9 = 0;
            if ( ImpersonateLoggedOnUser(phToken) )
            {
              v10 = phToken;
              pCount[0] = 0;
              if ( !GetTokenInformation(phToken, TokenUser, 0, 0, pCount) && GetLastError() == 122 )
              {
                v9 = LocalAlloc(0x40u, pCount[0]);
                if ( v9 )
                {
                  if ( GetTokenInformation(v10, TokenUser, v9, pCount[0], pCount) )
                  {
                    if ( !RegOpenCurrentUser(0x20019u, &v25) )
                    {
                      v8 = EnumerateCustomDeviceGUIDs(v25);
                      RegCloseKey(v25);
                      v25 = 0;
                    }
                  }
                  else
                  {
                    GetLastError();
                    LocalFree(v9);
                    v9 = 0;
                  }
                }
              }
              RevertToSelf();
            }
            CloseHandle(phToken);
            if ( v8 )
            {
              v21 = (char *)WPDLibRemoveDuplicateEntries(v3, v8);
              if ( v21 )
                MergeUserLists(&pSecurityDescriptor, &v21, *v9);
            }
            if ( v9 )
              LocalFree(v9);
          }
        }
        ++v6;
      }
      while ( v6 < pCount[1] );
      v2 = pSecurityDescriptor;
    }
    WTSFreeMemory(ppSessionInfo);
    if ( v2 )
    {
      for ( m = v3; m; m = *(char **)m )
      {
        if ( !*(_QWORD *)m )
        {
          *(_QWORD *)m = v2;
          break;
        }
      }
    }
  }
  for ( n = v3; n; n = *(char **)n )
  {
    v18 = (struct _ACL *)*((_QWORD *)n + 1);
    pSecurityDescriptor = 0;
    if ( (unsigned int)GetSecurityDescriptorForACL(v18, 0, &pSecurityDescriptor) )
    {
      LocalFree(*((HLOCAL *)n + 1));
      *((_QWORD *)n + 1) = 0;
    }
    else
    {
      v19 = pSecurityDescriptor;
      *((_QWORD *)n + 2) = pSecurityDescriptor;
      *((_DWORD *)n + 6) = GetSecurityDescriptorLength(v19);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180004f10  mov     r11, rsp
0x180004f13  mov     [r11+20h], rbx
0x180004f17  push    rbp
0x180004f18  push    rdi
0x180004f19  push    r12
0x180004f1b  lea     rbp, [r11-58h]
0x180004f1f  sub     rsp, 140h
0x180004f26  mov     rax, cs:__security_cookie
0x180004f2d  xor     rax, rsp
0x180004f30  mov     [rbp+50h+var_20], rax
0x180004f34  xor     r12d, r12d
0x180004f37  mov     [r11+8], rsi
0x180004f3b  mov     edi, ecx
0x180004f3d  mov     [r11+10h], r14
0x180004f41  lea     rax, [rbp+50h+hKey]
0x180004f45  mov     [r11+18h], r15
0x180004f49  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004f50  mov     [rsp+150h+var_E8], r12
0x180004f55  mov     r9d, 20019h; samDesired
0x180004f5b  mov     [rbp+50h+ppSessionInfo], r12
0x180004f5f  xor     r8d, r8d; ulOptions
0x180004f62  mov     [rsp+150h+phToken], r12
0x180004f67  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180004f6e  mov     [rsp+150h+pCount+4], r12d
0x180004f73  mov     esi, r12d
0x180004f76  mov     [rsp+150h+pSecurityDescriptor], r12
0x180004f7b  mov     [rbp+50h+hKey], r12
0x180004f7f  mov     [rsp+150h+var_F0], r12
0x180004f84  mov     [rsp+150h+cchValueName], r12d
0x180004f89  mov     [rsp+150h+phkResult], rax; phkResult
0x180004f8e  call    cs:__imp_RegOpenKeyExW
0x180004f94  test    eax, eax
0x180004f96  jz      loc_1800051E0
0x180004f9c  mov     ebx, r12d
0x180004f9f  cmp     edi, 1
0x180004fa2  jz      short loc_180004FC6
0x180004fa4  lea     rax, [rsp+150h+pCount+4]
0x180004fa9  xor     edx, edx; Reserved
0x180004fab  lea     r9, [rbp+50h+ppSessionInfo]; ppSessionInfo
0x180004faf  mov     [rsp+150h+phkResult], rax; pCount
0x180004fb4  xor     ecx, ecx; hServer
0x180004fb6  mov     r8d, 1; Version
0x180004fbc  call    cs:__imp_WTSEnumerateSessionsW
0x180004fc2  test    eax, eax
0x180004fc4  jnz     short loc_18000500D
0x180004fc6  mov     r15, [rsp+150h+arg_10]
0x180004fce  mov     rdi, rbx
0x180004fd1  mov     r14, [rsp+150h+arg_8]
0x180004fd9  mov     rsi, [rsp+150h+arg_0]
0x180004fe1  test    rbx, rbx
0x180004fe4  jnz     loc_1800053CE
0x180004fea  mov     rax, rbx
0x180004fed  mov     rcx, [rbp+50h+var_20]
0x180004ff1  xor     rcx, rsp; StackCookie
0x180004ff4  call    __security_check_cookie
0x180004ff9  mov     rbx, [rsp+150h+arg_18]
0x180005001  add     rsp, 140h
0x180005008  pop     r12
0x18000500a  pop     rdi
0x18000500b  pop     rbp
0x18000500c  retn
0x18000500d  mov     edi, r12d
0x180005010  cmp     [rsp+150h+pCount+4], esi
0x180005014  jbe     loc_1800050C5
0x18000501a  nop     word ptr [rax+rax+00h]
0x180005020  mov     eax, edi
0x180005022  lea     rcx, [rax+rax*2]
0x180005026  mov     rax, [rbp+50h+ppSessionInfo]
0x18000502a  mov     edx, [rax+rcx*8+10h]
0x18000502e  lea     rcx, [rax+rcx*8]
0x180005032  cmp     edx, 4
0x180005035  jnz     loc_180005372
0x18000503b  mov     ecx, [rcx]; SessionId
0x18000503d  lea     rdx, [rsp+150h+phToken]; phToken
0x180005042  mov     r14, r12
0x180005045  call    cs:__imp_WTSQueryUserToken
0x18000504b  test    eax, eax
0x18000504d  jz      short loc_1800050B4
0x18000504f  mov     rcx, [rsp+150h+phToken]; hToken
0x180005054  mov     rsi, r12
0x180005057  call    cs:__imp_ImpersonateLoggedOnUser
0x18000505d  test    eax, eax
0x18000505f  jz      short loc_180005097
0x180005061  mov     r15, [rsp+150h+phToken]
0x180005066  lea     rax, [rsp+150h+pCount]
0x18000506b  mov     rcx, r15; TokenHandle
0x18000506e  mov     [rsp+150h+pCount], r12d
0x180005073  xor     r9d, r9d; TokenInformationLength
0x180005076  mov     [rsp+150h+phkResult], rax; ReturnLength
0x18000507b  xor     r8d, r8d; TokenInformation
0x18000507e  mov     edx, 1; TokenInformationClass
0x180005083  call    cs:__imp_GetTokenInformation
0x180005089  test    eax, eax
0x18000508b  jz      loc_180005177
0x180005091  call    cs:__imp_RevertToSelf
0x180005097  mov     rcx, [rsp+150h+phToken]; hObject
0x18000509c  call    cs:__imp_CloseHandle
0x1800050a2  test    r14, r14
0x1800050a5  jnz     loc_180005388
0x1800050ab  test    rsi, rsi
0x1800050ae  jnz     loc_1800053B8
0x1800050b4  inc     edi
0x1800050b6  cmp     edi, [rsp+150h+pCount+4]
0x1800050ba  jb      loc_180005020
0x1800050c0  mov     rsi, [rsp+150h+pSecurityDescriptor]
0x1800050c5  mov     rcx, [rbp+50h+ppSessionInfo]; pMemory
0x1800050c9  call    cs:__imp_WTSFreeMemory
0x1800050cf  test    rsi, rsi
0x1800050d2  jz      loc_180004FC6
0x1800050d8  mov     rax, rbx
0x1800050db  test    rax, rax
0x1800050de  jz      loc_180004FC6
0x1800050e4  mov     rcx, [rax]
0x1800050e7  test    rcx, rcx
0x1800050ea  jz      loc_1800053C6
0x1800050f0  mov     rax, rcx
0x1800050f3  jmp     short loc_1800050DB
0x1800050f5  mov     rcx, [rbp+50h+hKey]; hKey
0x1800050f9  call    cs:__imp_RegCloseKey
0x1800050ff  mov     rbx, [rsp+150h+var_108]
0x180005104  mov     r14, rbx
0x180005107  test    rbx, rbx
0x18000510a  jz      loc_180004F9F
0x180005110  mov     ecx, [r14+2Ch]
0x180005114  lea     rdx, [rsp+150h+var_108]
0x180005119  mov     [rsp+150h+var_108], r12
0x18000511e  call    BuildMachinePolicyACL
0x180005123  test    eax, eax
0x180005125  jnz     short loc_180005130
0x180005127  mov     rax, [rsp+150h+var_108]
0x18000512c  mov     [r14+8], rax
0x180005130  mov     r14, [r14]
0x180005133  test    r14, r14
0x180005136  jnz     short loc_180005110
0x180005138  jmp     loc_180004F9F
0x18000513d  lea     rdx, [rsp+150h+var_E8]; phkResult
0x180005142  mov     ecx, 20019h; samDesired
0x180005147  call    cs:__imp_RegOpenCurrentUser
0x18000514d  test    eax, eax
0x18000514f  jnz     loc_180005091
0x180005155  mov     rcx, [rsp+150h+var_E8]
0x18000515a  call    EnumerateCustomDeviceGUIDs
0x18000515f  mov     rcx, [rsp+150h+var_E8]; hKey
0x180005164  mov     r14, rax
0x180005167  call    cs:__imp_RegCloseKey
0x18000516d  mov     [rsp+150h+var_E8], r12
0x180005172  jmp     loc_180005091
0x180005177  call    cs:__imp_GetLastError
0x18000517d  cmp     eax, 7Ah ; 'z'
0x180005180  jnz     loc_180005091
0x180005186  mov     edx, [rsp+150h+pCount]; uBytes
0x18000518a  mov     ecx, 40h ; '@'; uFlags
0x18000518f  call    cs:__imp_LocalAlloc
0x180005195  mov     rsi, rax
0x180005198  test    rax, rax
0x18000519b  jz      loc_180005091
0x1800051a1  mov     r9d, [rsp+150h+pCount]; TokenInformationLength
0x1800051a6  lea     rax, [rsp+150h+pCount]
0x1800051ab  mov     r8, rsi; TokenInformation
0x1800051ae  mov     [rsp+150h+phkResult], rax; ReturnLength
0x1800051b3  mov     edx, 1; TokenInformationClass
0x1800051b8  mov     rcx, r15; TokenHandle
0x1800051bb  call    cs:__imp_GetTokenInformation
0x1800051c1  test    eax, eax
0x1800051c3  jnz     loc_18000513D
0x1800051c9  call    cs:__imp_GetLastError
0x1800051cf  mov     rcx, rsi; hMem
0x1800051d2  call    cs:__imp_LocalFree
0x1800051d8  mov     rsi, r12
0x1800051db  jmp     loc_180005091
0x1800051e0  mov     [rsp+150h+var_108], r12
0x1800051e5  mov     r15d, r12d
0x1800051e8  cmp     r15d, 4
0x1800051ec  jnb     loc_1800050F5
0x1800051f2  mov     eax, r15d
0x1800051f5  test    r15d, r15d
0x1800051f8  jz      short loc_180005237
0x1800051fa  sub     eax, 1
0x1800051fd  jz      short loc_180005228
0x1800051ff  sub     eax, 1
0x180005202  jz      short loc_180005219
0x180005204  cmp     eax, 1
0x180005207  jnz     loc_1800050F5
0x18000520d  lea     rbx, aDenyExecute; "Deny_Execute"
0x180005214  mov     r14d, eax
0x180005217  jmp     short loc_180005244
0x180005219  lea     rbx, aDenyWrite; "Deny_Write"
0x180005220  mov     r14d, 2
0x180005226  jmp     short loc_180005244
0x180005228  lea     rbx, aDenyRead; "Deny_Read"
0x18000522f  mov     r14d, 4
0x180005235  jmp     short loc_180005244
0x180005237  lea     rbx, aDenyAll; "Deny_All"
0x18000523e  mov     r14d, 7
0x180005244  mov     rcx, [rbp+50h+hKey]; hKey
0x180005248  lea     rax, [rsp+150h+var_F0]
0x18000524d  mov     r9d, 20019h; samDesired
0x180005253  mov     [rsp+150h+phkResult], rax; phkResult
0x180005258  xor     r8d, r8d; ulOptions
0x18000525b  mov     rdx, rbx; lpSubKey
0x18000525e  call    cs:__imp_RegOpenKeyExW
0x180005264  test    eax, eax
0x180005266  jnz     loc_18000536A
0x18000526c  mov     rcx, [rsp+150h+var_F0]; hKey
0x180005271  lea     rax, [rsp+150h+cbData]
0x180005276  mov     [rsp+150h+lpcbData], rax; lpcbData
0x18000527b  lea     r9, [rsp+150h+Type]; lpType
0x180005280  lea     rax, [rsp+150h+pCount]
0x180005285  mov     [rsp+150h+pCount], r12d
0x18000528a  xor     r8d, r8d; lpReserved
0x18000528d  mov     [rsp+150h+phkResult], rax; lpData
0x180005292  mov     rdx, rbx; lpValueName
0x180005295  mov     [rsp+150h+Type], 4
0x18000529d  mov     [rsp+150h+cbData], 4
0x1800052a5  call    cs:__imp_RegQueryValueExW
0x1800052ab  test    eax, eax
0x1800052ad  jz      short loc_1800052B9
0x1800052af  mov     [rsp+150h+pCount], r12d
0x1800052b4  jmp     loc_18000535F
0x1800052b9  cmp     [rsp+150h+pCount], 1
0x1800052be  jnz     loc_18000535F
0x1800052c4  mov     rcx, [rsp+150h+var_F0]; hKey
0x1800052c9  lea     rax, [rbp+50h+var_D0]
0x1800052cd  xorps   xmm0, xmm0
0x1800052d0  mov     [rsp+150h+phkResult], rax; phkResult
0x1800052d5  mov     r9d, 20019h; samDesired
0x1800052db  mov     [rbp+50h+var_D0], r12
0x1800052df  xor     r8d, r8d; ulOptions
0x1800052e2  lea     rdx, aList; "List"
0x1800052e9  movups  [rbp+50h+var_B8], xmm0
0x1800052ed  call    cs:__imp_RegOpenKeyExW
0x1800052f3  test    eax, eax
0x1800052f5  jnz     short loc_18000535F
0x1800052f7  mov     ebx, r12d
0x1800052fa  mov     rcx, [rbp+50h+var_D0]; hKey
0x1800052fe  lea     r9, [rsp+150h+cchValueName]; lpcchValueName
0x180005303  mov     [rsp+150h+var_118], r12; lpcbData
0x180005308  lea     r8, [rbp+50h+ValueName]; lpValueName
0x18000530c  mov     [rsp+150h+lpData], r12; lpData
0x180005311  mov     edx, ebx; dwIndex
0x180005313  mov     [rsp+150h+lpcbData], r12; lpType
0x180005318  mov     [rsp+150h+phkResult], r12; lpReserved
0x18000531d  mov     [rsp+150h+cchValueName], 40h ; '@'
0x180005325  call    cs:__imp_RegEnumValueW
0x18000532b  test    eax, eax
0x18000532d  jnz     short loc_180005355
0x18000532f  lea     rdx, [rbp+50h+var_B8]
0x180005333  lea     rcx, [rbp+50h+ValueName]
0x180005337  call    WPDLibConvertStringGUIDToGUID
0x18000533c  test    eax, eax
0x18000533e  jz      short loc_180005355
0x180005340  mov     r8d, r14d
0x180005343  lea     rdx, [rbp+50h+var_B8]
0x180005347  lea     rcx, [rsp+150h+var_108]
0x18000534c  call    UpdateAccessMaskForGUID
0x180005351  inc     ebx
0x180005353  jmp     short loc_1800052FA
0x180005355  mov     rcx, [rbp+50h+var_D0]; hKey
0x180005359  call    cs:__imp_RegCloseKey
0x18000535f  mov     rcx, [rsp+150h+var_F0]; hKey
0x180005364  call    cs:__imp_RegCloseKey
0x18000536a  inc     r15d
0x18000536d  jmp     loc_1800051E8
0x180005372  test    edx, edx
0x180005374  jz      loc_18000503B
0x18000537a  cmp     edx, 1
0x18000537d  jnz     loc_1800050B4
0x180005383  jmp     loc_18000503B
0x180005388  mov     rdx, r14
0x18000538b  mov     rcx, rbx
0x18000538e  call    WPDLibRemoveDuplicateEntries
0x180005393  mov     [rsp+150h+var_108], rax
0x180005398  test    rax, rax
0x18000539b  jz      loc_1800050AB
0x1800053a1  mov     r8, [rsi]
0x1800053a4  lea     rdx, [rsp+150h+var_108]
0x1800053a9  lea     rcx, [rsp+150h+pSecurityDescriptor]
0x1800053ae  call    MergeUserLists
0x1800053b3  jmp     loc_1800050AB
0x1800053b8  mov     rcx, rsi; hMem
0x1800053bb  call    cs:__imp_LocalFree
0x1800053c1  jmp     loc_1800050B4
0x1800053c6  mov     [rax], rsi
0x1800053c9  jmp     loc_180004FC6
0x1800053ce  mov     rcx, [rdi+8]; pDacl
0x1800053d2  lea     r8, [rsp+150h+pSecurityDescriptor]
0x1800053d7  xor     edx, edx; pSacl
0x1800053d9  mov     [rsp+150h+pSecurityDescriptor], r12
0x1800053de  call    GetSecurityDescriptorForACL
0x1800053e3  test    eax, eax
0x1800053e5  jnz     short loc_1800053FB
0x1800053e7  mov     rcx, [rsp+150h+pSecurityDescriptor]; pSecurityDescriptor
0x1800053ec  mov     [rdi+10h], rcx
0x1800053f0  call    cs:__imp_GetSecurityDescriptorLength
0x1800053f6  mov     [rdi+18h], eax
0x1800053f9  jmp     short loc_180005409
0x1800053fb  mov     rcx, [rdi+8]; hMem
0x1800053ff  call    cs:__imp_LocalFree
0x180005405  mov     [rdi+8], r12
0x180005409  mov     rdi, [rdi]
  ... truncated ...
```
