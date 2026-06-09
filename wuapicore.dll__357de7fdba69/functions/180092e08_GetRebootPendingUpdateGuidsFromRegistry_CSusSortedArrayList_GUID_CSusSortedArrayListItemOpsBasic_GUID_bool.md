# GetRebootPendingUpdateGuidsFromRegistry(CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> &,bool)

- ea: `0x180092e08`
- end: `0x180092fa4`
- name: `?GetRebootPendingUpdateGuidsFromRegistry@@YAJAEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@_N@Z`
- size: `412`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180069b60`
- `0x180092ce4`

## callees

- `0x180037340`
- `0x180091d18`
- `0x180092e08`
- `0x180093cf4`
- `0x18009ae75`
- `0x18009b050`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180092f28`
- `RPCRT4!UuidFromStringW` at `0x180092f28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092e82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180092e82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092f78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092f78`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180092eee`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180092eee`

## pseudocode

```c
__int64 __fastcall GetRebootPendingUpdateGuidsFromRegistry(__int64 a1)
{
  int v1; // eax
  __int64 v3; // rdx
  int v4; // edi
  __int64 v5; // r8
  wchar_t **v6; // r9
  const WCHAR *RegKeyPath; // rax
  DWORD v8; // esi
  LSTATUS v9; // eax
  int v10; // eax
  HKEY hKey; // [rsp+40h] [rbp-69h] BYREF
  REGSAM samDesired; // [rsp+48h] [rbp-61h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-5Dh] BYREF
  DWORD cbData; // [rsp+50h] [rbp-59h] BYREF
  DWORD cchValueName; // [rsp+54h] [rbp-55h] BYREF
  UUID Uuid; // [rsp+58h] [rbp-51h] BYREF
  WCHAR ValueName; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v19[110]; // [rsp+72h] [rbp-37h] BYREF

  v1 = *(_DWORD *)(a1 + 20);
  hKey = 0;
  if ( v1 )
    *(_DWORD *)(a1 + 20) -= v1;
  samDesired = 1;
  v4 = SetRegistryType(a1, &samDesired);
  if ( v4 >= 0 )
  {
    RegKeyPath = (const WCHAR *)GetRegKeyPath(6, v3, v5, v6);
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegKeyPath, 0, samDesired, &hKey) )
    {
LABEL_8:
      v4 = 0;
      goto LABEL_18;
    }
    v8 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        ValueName = 0;
        memset_0(v19, 0, 0x62u);
        cchValueName = 50;
        Type = 0;
        samDesired = 0;
        cbData = 4;
        Uuid = 0;
        v9 = RegEnumValueW(hKey, v8++, &ValueName, &cchValueName, 0, &Type, (LPBYTE)&samDesired, &cbData);
        if ( !v9 )
          break;
        if ( v9 != 234 )
          goto LABEL_8;
      }
      if ( Type == 4 && cbData == 4 && samDesired <= 2 && !UuidFromStringW(&ValueName, &Uuid) )
      {
        if ( samDesired )
        {
          v10 = CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Add(a1, &Uuid, 1);
          v4 = v10;
          if ( v10 < 0 && v10 != -2145124333 )
            break;
        }
      }
    }
  }
  if ( *(_DWORD *)(a1 + 20) )
    *(_DWORD *)(a1 + 20) = 0;
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180092e08  mov     [rsp-8+arg_8], rbx
0x180092e0d  mov     [rsp-8+arg_10], rsi
0x180092e12  push    rbp
0x180092e13  push    rdi
0x180092e14  push    r14
0x180092e16  lea     rbp, [rsp-47h]
0x180092e1b  sub     rsp, 0F0h
0x180092e22  mov     rax, cs:__security_cookie
0x180092e29  xor     rax, rsp
0x180092e2c  mov     [rbp+57h+var_20], rax
0x180092e30  mov     eax, [rcx+14h]
0x180092e33  xor     r14d, r14d
0x180092e36  mov     [rbp+57h+hKey], r14
0x180092e3a  mov     rbx, rcx
0x180092e3d  test    eax, eax
0x180092e3f  jz      short loc_180092E44
0x180092e41  sub     [rcx+14h], eax
0x180092e44  lea     rdx, [rbp+57h+samDesired]
0x180092e48  mov     [rbp+57h+samDesired], 1
0x180092e4f  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x180092e54  mov     edi, eax
0x180092e56  test    eax, eax
0x180092e58  js      loc_180092F65
0x180092e5e  mov     ecx, 6
0x180092e63  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x180092e68  mov     r9d, [rbp+57h+samDesired]; samDesired
0x180092e6c  lea     rcx, [rbp+57h+hKey]
0x180092e70  mov     [rsp+100h+phkResult], rcx; phkResult
0x180092e75  xor     r8d, r8d; ulOptions
0x180092e78  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180092e7f  mov     rdx, rax; lpSubKey
0x180092e82  call    cs:__imp_RegOpenKeyExW
0x180092e88  test    eax, eax
0x180092e8a  jnz     short loc_180092F01
0x180092e8c  mov     esi, r14d
0x180092e8f  xor     edx, edx; Val
0x180092e91  mov     [rbp+57h+ValueName], r14w
0x180092e96  lea     rcx, [rbp+57h+var_8E]; void *
0x180092e9a  lea     r8d, [rdx+62h]; Size
0x180092e9e  call    memset_0
0x180092ea3  mov     rcx, [rbp+57h+hKey]; hKey
0x180092ea7  lea     rax, [rbp+57h+cbData]
0x180092eab  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180092eb0  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180092eb4  lea     rax, [rbp+57h+samDesired]
0x180092eb8  mov     [rbp+57h+cchValueName], 32h ; '2'
0x180092ebf  mov     [rsp+100h+lpData], rax; lpData
0x180092ec4  lea     r8, [rbp+57h+ValueName]; lpValueName
0x180092ec8  lea     rax, [rbp+57h+Type]
0x180092ecc  mov     [rbp+57h+Type], r14d
0x180092ed0  xorps   xmm0, xmm0
0x180092ed3  mov     [rsp+100h+lpType], rax; lpType
0x180092ed8  mov     edx, esi; dwIndex
0x180092eda  mov     [rsp+100h+phkResult], r14; lpReserved
0x180092edf  mov     [rbp+57h+samDesired], r14d
0x180092ee3  mov     [rbp+57h+cbData], 4
0x180092eea  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180092eee  call    cs:__imp_RegEnumValueW
0x180092ef4  inc     esi
0x180092ef6  test    eax, eax
0x180092ef8  jz      short loc_180092F06
0x180092efa  cmp     eax, 0EAh
0x180092eff  jz      short loc_180092E8F
0x180092f01  mov     edi, r14d
0x180092f04  jmp     short loc_180092F6F
0x180092f06  cmp     [rbp+57h+Type], 4
0x180092f0a  jnz     short loc_180092E8F
0x180092f0c  cmp     [rbp+57h+cbData], 4
0x180092f10  jnz     loc_180092E8F
0x180092f16  cmp     [rbp+57h+samDesired], 2
0x180092f1a  ja      loc_180092E8F
0x180092f20  lea     rdx, [rbp+57h+Uuid]; Uuid
0x180092f24  lea     rcx, [rbp+57h+ValueName]; StringUuid
0x180092f28  call    cs:__imp_UuidFromStringW
0x180092f2e  test    eax, eax
0x180092f30  jnz     loc_180092E8F
0x180092f36  cmp     [rbp+57h+samDesired], r14d
0x180092f3a  jz      loc_180092E8F
0x180092f40  lea     r8d, [rax+1]
0x180092f44  mov     rcx, rbx
0x180092f47  lea     rdx, [rbp+57h+Uuid]
0x180092f4b  call    ?Add@?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@QEAAJAEBU_GUID@@K@Z; CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Add(_GUID const &,ulong)
0x180092f50  mov     edi, eax
0x180092f52  test    eax, eax
0x180092f54  jns     loc_180092E8F
0x180092f5a  cmp     eax, 80240013h
0x180092f5f  jz      loc_180092E8F
0x180092f65  mov     eax, [rbx+14h]
0x180092f68  test    eax, eax
0x180092f6a  jz      short loc_180092F6F
0x180092f6c  sub     [rbx+14h], eax
0x180092f6f  mov     rcx, [rbp+57h+hKey]; hKey
0x180092f73  test    rcx, rcx
0x180092f76  jz      short loc_180092F7E
0x180092f78  call    cs:__imp_RegCloseKey
0x180092f7e  mov     eax, edi
0x180092f80  mov     rcx, [rbp+57h+var_20]
0x180092f84  xor     rcx, rsp; StackCookie
0x180092f87  call    __security_check_cookie
0x180092f8c  lea     r11, [rsp+100h+var_10]
0x180092f94  mov     rbx, [r11+28h]
0x180092f98  mov     rsi, [r11+30h]
0x180092f9c  mov     rsp, r11
0x180092f9f  pop     r14
0x180092fa1  pop     rdi
0x180092fa2  pop     rbp
0x180092fa3  retn
```
