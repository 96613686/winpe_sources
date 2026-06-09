# DllRegisterServer

- ea: `0x18001ccb0`
- end: `0x18001cea0`
- name: `DllRegisterServer`
- size: `496`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180010cd0`
- `0x18001ccb0`
- `0x1800388c0`
- `0x180038a94`
- `0x18008f600`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001cd6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001cda1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001cd6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001cda1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cd30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cd30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdb2`
- `msdmo!DMORegister` at `0x18001ce65`
- `msdmo!DMORegister` at `0x18001ce65`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DMO_PARTIAL_MEDIATYPE pOutTypes; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v4; // [rsp+70h] [rbp-90h]
  __int128 v5; // [rsp+80h] [rbp-80h]
  DMO_PARTIAL_MEDIATYPE pInTypes; // [rsp+90h] [rbp-70h] BYREF
  __int128 v7; // [rsp+B0h] [rbp-50h]
  __int128 v8; // [rsp+C0h] [rbp-40h]
  __int128 v9; // [rsp+D0h] [rbp-30h]
  __int128 v10; // [rsp+E0h] [rbp-20h]
  __int128 v11; // [rsp+F0h] [rbp-10h]
  __int128 v12; // [rsp+100h] [rbp+0h]
  WCHAR SubKey[80]; // [rsp+110h] [rbp+10h] BYREF

  result = sub_180038A94((__int64)&rclsid, "WMAudio Decoder DMO");
  if ( result >= 0 )
  {
    result = sub_1800388C0(&rclsid, SubKey);
    if ( result >= 0 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 2u, &hKey) )
      {
        *(_DWORD *)Data = 8390656;
        RegSetValueExW(hKey, L"Merit", 0, 4u, Data, 4u);
        *(_DWORD *)Data = 256;
        RegSetValueExW(hKey, L"WMSDKMerit", 0, 4u, Data, 4u);
        RegCloseKey(hKey);
      }
      pInTypes.subtype = (GUID)xmmword_18009F120;
      pInTypes.type = (GUID)xmmword_18009F070;
      v8 = xmmword_18009F130;
      v7 = xmmword_18009F070;
      v10 = xmmword_18009F140;
      v9 = xmmword_18009F070;
      v12 = xmmword_18009F150;
      v11 = xmmword_18009F070;
      pOutTypes.subtype = (GUID)xmmword_18009F0D0;
      pOutTypes.type = (GUID)xmmword_18009F070;
      v5 = xmmword_18009F0E0;
      v4 = xmmword_18009F070;
      result = DMORegister(L"WMAudio Decoder DMO", &rclsid, &guidCategory, 0, 4u, &pInTypes, 2u, &pOutTypes);
      if ( result >= 0 )
        return sub_18008F600(1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ccb0  mov     [rsp-8+arg_0], rbx
0x18001ccb5  push    rbp
0x18001ccb6  lea     rbp, [rsp-0C0h]
0x18001ccbe  sub     rsp, 1C0h
0x18001ccc5  mov     rax, cs:__security_cookie
0x18001cccc  xor     rax, rsp
0x18001cccf  mov     [rbp+0C0h+var_10], rax
0x18001ccd6  lea     rdx, aWmaudioDecoder; "WMAudio Decoder DMO"
0x18001ccdd  lea     rcx, rclsid
0x18001cce4  call    sub_180038A94
0x18001cce9  test    eax, eax
0x18001cceb  js      loc_18001CE7F
0x18001ccf1  lea     rdx, [rbp+0C0h+SubKey]
0x18001ccf5  lea     rcx, rclsid
0x18001ccfc  call    sub_1800388C0
0x18001cd01  test    eax, eax
0x18001cd03  js      loc_18001CE7F
0x18001cd09  lea     rax, [rsp+1C0h+hKey]
0x18001cd0e  mov     [rsp+1C0h+hKey], 0
0x18001cd17  mov     r9d, 2; samDesired
0x18001cd1d  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18001cd22  xor     r8d, r8d; ulOptions
0x18001cd25  lea     rdx, [rbp+0C0h+SubKey]; lpSubKey
0x18001cd29  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001cd30  call    cs:RegOpenKeyExW
0x18001cd37  nop     dword ptr [rax+rax+00h]
0x18001cd3c  mov     ebx, 4
0x18001cd41  test    eax, eax
0x18001cd43  jnz     short loc_18001CDBE
0x18001cd45  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001cd4a  lea     rax, [rsp+1C0h+Data]
0x18001cd4f  mov     [rsp+1C0h+cbData], ebx; cbData
0x18001cd53  lea     rdx, ValueName; "Merit"
0x18001cd5a  mov     r9d, ebx; dwType
0x18001cd5d  mov     [rsp+1C0h+phkResult], rax; lpData
0x18001cd62  xor     r8d, r8d; Reserved
0x18001cd65  mov     dword ptr [rsp+1C0h+Data], 800800h
0x18001cd6d  call    cs:RegSetValueExW
0x18001cd74  nop     dword ptr [rax+rax+00h]
0x18001cd79  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001cd7e  lea     rax, [rsp+1C0h+Data]
0x18001cd83  mov     [rsp+1C0h+cbData], ebx; cbData
0x18001cd87  lea     rdx, aWmsdkmerit; "WMSDKMerit"
0x18001cd8e  mov     r9d, ebx; dwType
0x18001cd91  mov     [rsp+1C0h+phkResult], rax; lpData
0x18001cd96  xor     r8d, r8d; Reserved
0x18001cd99  mov     dword ptr [rsp+1C0h+Data], 100h
0x18001cda1  call    cs:RegSetValueExW
0x18001cda8  nop     dword ptr [rax+rax+00h]
0x18001cdad  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001cdb2  call    cs:RegCloseKey
0x18001cdb9  nop     dword ptr [rax+rax+00h]
0x18001cdbe  movups  xmm1, cs:xmmword_18009F070
0x18001cdc5  lea     rax, [rsp+1C0h+var_170]
0x18001cdca  xor     r9d, r9d; dwFlags
0x18001cdcd  movups  xmm0, cs:xmmword_18009F120
0x18001cdd4  mov     [rsp+1C0h+pOutTypes], rax; pOutTypes
0x18001cdd9  lea     r8, guidCategory; guidCategory
0x18001cde0  lea     rax, [rbp+0C0h+pInTypes]
0x18001cde4  mov     [rsp+1C0h+cOutTypes], 2; cOutTypes
0x18001cdec  movdqu  xmmword ptr [rbp+0C0h+pInTypes.subtype.Data1], xmm0
0x18001cdf1  mov     qword ptr [rsp+1C0h+cbData], rax; pInTypes
0x18001cdf6  lea     rdx, rclsid; clsidDMO
0x18001cdfd  movups  xmm0, cs:xmmword_18009F130
0x18001ce04  lea     rcx, szName; "WMAudio Decoder DMO"
0x18001ce0b  mov     dword ptr [rsp+1C0h+phkResult], ebx; cInTypes
0x18001ce0f  movdqu  xmmword ptr [rbp+0C0h+pInTypes.type.Data1], xmm1
0x18001ce14  movdqu  [rbp+0C0h+var_100], xmm0
0x18001ce19  movups  xmm0, cs:xmmword_18009F140
0x18001ce20  movdqu  [rbp+0C0h+var_110], xmm1
0x18001ce25  movdqu  [rbp+0C0h+var_E0], xmm0
0x18001ce2a  movups  xmm0, cs:xmmword_18009F150
0x18001ce31  movdqu  [rbp+0C0h+var_F0], xmm1
0x18001ce36  movdqu  [rbp+0C0h+var_C0], xmm0
0x18001ce3b  movups  xmm0, cs:xmmword_18009F0D0
0x18001ce42  movdqu  [rbp+0C0h+var_D0], xmm1
0x18001ce47  movdqu  xmmword ptr [rsp+1C0h+var_170.subtype.Data1], xmm0
0x18001ce4d  movups  xmm0, cs:xmmword_18009F0E0
0x18001ce54  movdqu  xmmword ptr [rsp+1C0h+var_170.type.Data1], xmm1
0x18001ce5a  movdqu  [rbp+0C0h+var_140], xmm0
0x18001ce5f  movdqu  [rsp+1C0h+var_150], xmm1
0x18001ce65  call    cs:DMORegister
0x18001ce6c  nop     dword ptr [rax+rax+00h]
0x18001ce71  test    eax, eax
0x18001ce73  js      short loc_18001CE7F
0x18001ce75  mov     ecx, 1
0x18001ce7a  call    sub_18008F600
0x18001ce7f  mov     rcx, [rbp+0C0h+var_10]
0x18001ce86  xor     rcx, rsp; StackCookie
0x18001ce89  call    __security_check_cookie
0x18001ce8e  mov     rbx, [rsp+1C0h+arg_0]
0x18001ce96  add     rsp, 1C0h
0x18001ce9d  pop     rbp
0x18001ce9e  retn
```
