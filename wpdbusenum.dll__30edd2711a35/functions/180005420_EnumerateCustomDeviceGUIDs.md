# EnumerateCustomDeviceGUIDs

- ea: `0x180005420`
- end: `0x180005664`
- name: `EnumerateCustomDeviceGUIDs`
- size: `580`
- prototype: `__int64 __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004f10`

## callees

- `0x180005420`
- `0x180007f68`
- `0x1800097d0`
- `0x1800138c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000560d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005618`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000562a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000560d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005618`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000562a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000546a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000550b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000559d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000546a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000550b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000559d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005552`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005552`
- `KERNEL32!RegEnumValueW` at `0x1800055d6`
- `KERNEL32!RegEnumValueW` at `0x1800055d6`

## string_xrefs

- `0x1800054d6`: `Deny_Read`
- `0x1800054c8`: `Deny_Write`

## pseudocode

```c
__int64 __fastcall EnumerateCustomDeviceGUIDs(HKEY a1)
{
  unsigned int v2; // esi
  const WCHAR *v3; // rbx
  unsigned int v4; // edi
  DWORD i; // ebx
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY v11; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v13; // [rsp+68h] [rbp-98h] BYREF
  __int128 v14; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[64]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  phkResult = 0;
  cchValueName = 0;
  if ( RegOpenKeyExW(a1, L"SOFTWARE\\Policies\\Microsoft\\Windows\\RemovableStorageDevices\\Custom", 0, 0x20019u, &hKey) )
    return 0;
  v2 = 0;
  v13 = 0;
  while ( v2 < 4 )
  {
    if ( v2 )
    {
      if ( v2 == 1 )
      {
        v3 = L"Deny_Read";
        v4 = 4;
      }
      else if ( v2 == 2 )
      {
        v3 = L"Deny_Write";
        v4 = 2;
      }
      else
      {
        v3 = L"Deny_Execute";
        v4 = 1;
      }
    }
    else
    {
      v3 = L"Deny_All";
      v4 = 7;
    }
    if ( !RegOpenKeyExW(hKey, v3, 0, 0x20019u, &phkResult) )
    {
      *(_DWORD *)Data = 0;
      Type = 4;
      cbData = 4;
      if ( RegQueryValueExW(phkResult, v3, 0, &Type, Data, &cbData) )
      {
        *(_DWORD *)Data = 0;
      }
      else if ( *(_DWORD *)Data == 1 )
      {
        v11 = 0;
        v14 = 0;
        if ( !RegOpenKeyExW(phkResult, L"List", 0, 0x20019u, &v11) )
        {
          for ( i = 0; ; ++i )
          {
            cchValueName = 64;
            if ( RegEnumValueW(v11, i, ValueName, &cchValueName, 0, 0, 0, 0)
              || !(unsigned int)WPDLibConvertStringGUIDToGUID(ValueName, &v14) )
            {
              break;
            }
            UpdateAccessMaskForGUID(&v13, &v14, v4);
          }
          RegCloseKey(v11);
        }
      }
      RegCloseKey(phkResult);
    }
    ++v2;
  }
  RegCloseKey(hKey);
  return v13;
}

```

## disassembly

```asm
0x180005420  push    rbp
0x180005422  push    r14
0x180005424  lea     rbp, [rsp-18h]
0x180005429  sub     rsp, 118h
0x180005430  mov     rax, cs:__security_cookie
0x180005437  xor     rax, rsp
0x18000543a  mov     [rbp+20h+var_20], rax
0x18000543e  xor     r14d, r14d
0x180005441  lea     rax, [rsp+120h+hKey]
0x180005446  mov     r9d, 20019h; samDesired
0x18000544c  mov     [rsp+120h+hKey], r14
0x180005451  xor     r8d, r8d; ulOptions
0x180005454  mov     [rsp+120h+var_D8], r14
0x180005459  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180005460  mov     [rsp+120h+cchValueName], r14d
0x180005465  mov     [rsp+120h+phkResult], rax; phkResult
0x18000546a  call    cs:__imp_RegOpenKeyExW
0x180005470  test    eax, eax
0x180005472  jz      short loc_18000547B
0x180005474  xor     eax, eax
0x180005476  jmp     loc_18000564D
0x18000547b  mov     [rsp+120h+arg_8], rbx
0x180005483  mov     [rsp+120h+arg_10], rsi
0x18000548b  mov     esi, r14d
0x18000548e  mov     [rsp+120h+var_10], rdi
0x180005496  mov     [rsp+120h+var_B8], r14
0x18000549b  cmp     esi, 4
0x18000549e  jnb     loc_180005625
0x1800054a4  mov     eax, esi
0x1800054a6  test    esi, esi
0x1800054a8  jz      short loc_1800054E4
0x1800054aa  sub     eax, 1
0x1800054ad  jz      short loc_1800054D6
0x1800054af  sub     eax, 1
0x1800054b2  jz      short loc_1800054C8
0x1800054b4  cmp     eax, 1
0x1800054b7  jnz     loc_180005625
0x1800054bd  lea     rbx, aDenyExecute; "Deny_Execute"
0x1800054c4  mov     edi, eax
0x1800054c6  jmp     short loc_1800054F0
0x1800054c8  lea     rbx, aDenyWrite; "Deny_Write"
0x1800054cf  mov     edi, 2
0x1800054d4  jmp     short loc_1800054F0
0x1800054d6  lea     rbx, aDenyRead; "Deny_Read"
0x1800054dd  mov     edi, 4
0x1800054e2  jmp     short loc_1800054F0
0x1800054e4  lea     rbx, aDenyAll; "Deny_All"
0x1800054eb  mov     edi, 7
0x1800054f0  mov     rcx, [rsp+120h+hKey]; hKey
0x1800054f5  lea     rax, [rsp+120h+var_D8]
0x1800054fa  mov     r9d, 20019h; samDesired
0x180005500  mov     [rsp+120h+phkResult], rax; phkResult
0x180005505  xor     r8d, r8d; ulOptions
0x180005508  mov     rdx, rbx; lpSubKey
0x18000550b  call    cs:__imp_RegOpenKeyExW
0x180005511  test    eax, eax
0x180005513  jnz     loc_18000561E
0x180005519  mov     rcx, [rsp+120h+var_D8]; hKey
0x18000551e  lea     rax, [rsp+120h+cbData]
0x180005523  mov     [rsp+120h+lpcbData], rax; lpcbData
0x180005528  lea     r9, [rsp+120h+Type]; lpType
0x18000552d  lea     rax, [rsp+120h+Data]
0x180005532  mov     dword ptr [rsp+120h+Data], r14d
0x180005537  xor     r8d, r8d; lpReserved
0x18000553a  mov     [rsp+120h+phkResult], rax; lpData
0x18000553f  mov     rdx, rbx; lpValueName
0x180005542  mov     [rsp+120h+Type], 4
0x18000554a  mov     [rsp+120h+cbData], 4
0x180005552  call    cs:__imp_RegQueryValueExW
0x180005558  test    eax, eax
0x18000555a  jz      short loc_180005566
0x18000555c  mov     dword ptr [rsp+120h+Data], r14d
0x180005561  jmp     loc_180005613
0x180005566  cmp     dword ptr [rsp+120h+Data], 1
0x18000556b  jnz     loc_180005613
0x180005571  mov     rcx, [rsp+120h+var_D8]; hKey
0x180005576  lea     rax, [rsp+120h+var_C8]
0x18000557b  xorps   xmm0, xmm0
0x18000557e  mov     [rsp+120h+phkResult], rax; phkResult
0x180005583  mov     r9d, 20019h; samDesired
0x180005589  mov     [rsp+120h+var_C8], r14
0x18000558e  xor     r8d, r8d; ulOptions
0x180005591  lea     rdx, aList; "List"
0x180005598  movups  [rsp+120h+var_B0], xmm0
0x18000559d  call    cs:__imp_RegOpenKeyExW
0x1800055a3  test    eax, eax
0x1800055a5  jnz     short loc_180005613
0x1800055a7  mov     ebx, r14d
0x1800055aa  mov     rcx, [rsp+120h+var_C8]; hKey
0x1800055af  lea     r9, [rsp+120h+cchValueName]; lpcchValueName
0x1800055b4  mov     [rsp+120h+var_E8], r14; lpcbData
0x1800055b9  lea     r8, [rbp+20h+ValueName]; lpValueName
0x1800055bd  mov     [rsp+120h+lpData], r14; lpData
0x1800055c2  mov     edx, ebx; dwIndex
0x1800055c4  mov     [rsp+120h+lpcbData], r14; lpType
0x1800055c9  mov     [rsp+120h+phkResult], r14; lpReserved
0x1800055ce  mov     [rsp+120h+cchValueName], 40h ; '@'
0x1800055d6  call    cs:__imp_RegEnumValueW
0x1800055dc  test    eax, eax
0x1800055de  jnz     short loc_180005608
0x1800055e0  lea     rdx, [rsp+120h+var_B0]
0x1800055e5  lea     rcx, [rbp+20h+ValueName]
0x1800055e9  call    WPDLibConvertStringGUIDToGUID
0x1800055ee  test    eax, eax
0x1800055f0  jz      short loc_180005608
0x1800055f2  mov     r8d, edi
0x1800055f5  lea     rdx, [rsp+120h+var_B0]
0x1800055fa  lea     rcx, [rsp+120h+var_B8]
0x1800055ff  call    UpdateAccessMaskForGUID
0x180005604  inc     ebx
0x180005606  jmp     short loc_1800055AA
0x180005608  mov     rcx, [rsp+120h+var_C8]; hKey
0x18000560d  call    cs:__imp_RegCloseKey
0x180005613  mov     rcx, [rsp+120h+var_D8]; hKey
0x180005618  call    cs:__imp_RegCloseKey
0x18000561e  inc     esi
0x180005620  jmp     loc_18000549B
0x180005625  mov     rcx, [rsp+120h+hKey]; hKey
0x18000562a  call    cs:__imp_RegCloseKey
0x180005630  mov     rax, [rsp+120h+var_B8]
0x180005635  mov     rdi, [rsp+120h+var_10]
0x18000563d  mov     rsi, [rsp+120h+arg_10]
0x180005645  mov     rbx, [rsp+120h+arg_8]
0x18000564d  mov     rcx, [rbp+20h+var_20]
0x180005651  xor     rcx, rsp; StackCookie
0x180005654  call    __security_check_cookie
0x180005659  add     rsp, 118h
0x180005660  pop     r14
0x180005662  pop     rbp
0x180005663  retn
```
