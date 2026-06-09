# GetCommitPendingUpdateGuidsFromRegistry(CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> &)

- ea: `0x18012f914`
- end: `0x18012fb6c`
- name: `?GetCommitPendingUpdateGuidsFromRegistry@@YAJAEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@@Z`
- size: `600`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180027bb4`
- `0x180027c38`

## callees

- `0x180033adc`
- `0x18012f914`
- `0x180131a30`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012fab5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18012fab5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012fa1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012fad2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012faee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012fa1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012fad2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012faee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f978`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012fa42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f978`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012fa42`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18012f9c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18012f9c0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18012fb46`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18012fb46`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18012fa03`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18012fa03`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCommitPendingUpdateGuidsFromRegistry(__int64 a1, __int64 a2, __int64 a3, wchar_t **a4)
{
  const WCHAR *RegKeyPath; // rax
  DWORD i; // ebx
  DWORD v7; // edi
  LSTATUS v8; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp-80h] BYREF
  GUID pclsid; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ValueName[56]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[264]; // [rsp+110h] [rbp+10h] BYREF

  hKey = 0;
  cSubKeys = 0;
  RegKeyPath = (const WCHAR *)GetRegKeyPath(2, a2, a3, a4);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegKeyPath, 0, 0x20019u, &hKey)
    && !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) )
  {
    for ( i = 0; i < cSubKeys; ++i )
    {
      memset(Name, 0, 0x208u);
      phkResult = 0;
      if ( !RegEnumKeyW(hKey, i, Name, 0x104u) )
      {
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        if ( !RegOpenKeyExW(hKey, Name, 0, 1u, &phkResult) )
        {
          v7 = 0;
          do
          {
            while ( 1 )
            {
              memset(ValueName, 0, 100);
              cchValueName = 50;
              Type = 0;
              *(_DWORD *)Data = 0;
              cbData = 4;
              pclsid = 0;
              v8 = RegEnumValueW(phkResult, v7++, ValueName, &cchValueName, 0, &Type, Data, &cbData);
              if ( v8 )
                break;
              if ( Type == 4 && cbData == 4 && *(_DWORD *)Data == 1 && CLSIDFromString(ValueName, &pclsid) >= 0 )
                CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Add(a1, &pclsid, 1);
            }
          }
          while ( v8 == 234 );
        }
      }
      if ( phkResult )
        RegCloseKey(phkResult);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18012f914  mov     [rsp-8+arg_8], rbx
0x18012f919  mov     [rsp-8+arg_10], rsi
0x18012f91e  push    rbp
0x18012f91f  push    rdi
0x18012f920  push    r14
0x18012f922  lea     rbp, [rsp-230h]
0x18012f92a  sub     rsp, 330h
0x18012f931  mov     rax, cs:__security_cookie
0x18012f938  xor     rax, rsp
0x18012f93b  mov     [rbp+240h+var_20], rax
0x18012f942  mov     rsi, rcx
0x18012f945  xor     r14d, r14d
0x18012f948  mov     [rsp+340h+hKey], r14
0x18012f94d  mov     [rsp+340h+cSubKeys], r14d
0x18012f952  lea     ecx, [r14+2]
0x18012f956  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x18012f95b  lea     rcx, [rsp+340h+hKey]
0x18012f960  mov     [rsp+340h+phkResult], rcx; phkResult
0x18012f965  mov     r9d, 20019h; samDesired
0x18012f96b  xor     r8d, r8d; ulOptions
0x18012f96e  mov     rdx, rax; lpSubKey
0x18012f971  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18012f978  call    cs:__imp_RegOpenKeyExW
0x18012f97e  test    eax, eax
0x18012f980  jnz     loc_18012FAE4
0x18012f986  mov     [rsp+340h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18012f98b  mov     [rsp+340h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18012f990  mov     [rsp+340h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18012f995  mov     [rsp+340h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18012f99a  mov     [rsp+340h+lpcValues], r14; lpcValues
0x18012f99f  mov     [rsp+340h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18012f9a4  mov     [rsp+340h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18012f9a9  lea     rax, [rsp+340h+cSubKeys]
0x18012f9ae  mov     [rsp+340h+phkResult], rax; lpcSubKeys
0x18012f9b3  xor     r9d, r9d; lpReserved
0x18012f9b6  xor     r8d, r8d; lpcchClass
0x18012f9b9  xor     edx, edx; lpClass
0x18012f9bb  mov     rcx, [rsp+340h+hKey]; hKey
0x18012f9c0  call    cs:__imp_RegQueryInfoKeyW
0x18012f9c6  test    eax, eax
0x18012f9c8  jnz     loc_18012FAE4
0x18012f9ce  mov     ebx, r14d
0x18012f9d1  cmp     [rsp+340h+cSubKeys], r14d
0x18012f9d6  jbe     loc_18012FAE4
0x18012f9dc  xor     edx, edx; Val
0x18012f9de  mov     r8d, 208h; Size
0x18012f9e4  lea     rcx, [rbp+240h+Name]; void *
0x18012f9e8  call    memset
0x18012f9ed  mov     [rsp+340h+var_2D0], r14
0x18012f9f2  mov     r9d, 104h; cchName
0x18012f9f8  lea     r8, [rbp+240h+Name]; lpName
0x18012f9fc  mov     edx, ebx; dwIndex
0x18012f9fe  mov     rcx, [rsp+340h+hKey]; hKey
0x18012fa03  call    cs:__imp_RegEnumKeyW
0x18012fa09  test    eax, eax
0x18012fa0b  jnz     loc_18012FAC8
0x18012fa11  mov     rcx, [rsp+340h+var_2D0]; hKey
0x18012fa16  test    rcx, rcx
0x18012fa19  jz      short loc_18012FA26
0x18012fa1b  call    cs:__imp_RegCloseKey
0x18012fa21  mov     [rsp+340h+var_2D0], r14
0x18012fa26  lea     rax, [rsp+340h+var_2D0]
0x18012fa2b  mov     [rsp+340h+phkResult], rax; phkResult
0x18012fa30  mov     r9d, 1; samDesired
0x18012fa36  xor     r8d, r8d; ulOptions
0x18012fa39  lea     rdx, [rbp+240h+Name]; lpSubKey
0x18012fa3d  mov     rcx, [rsp+340h+hKey]; hKey
0x18012fa42  call    cs:__imp_RegOpenKeyExW
0x18012fa48  test    eax, eax
0x18012fa4a  jnz     short loc_18012FAC8
0x18012fa4c  mov     edi, r14d
0x18012fa4f  mov     [rbp+240h+ValueName], r14w
0x18012fa54  xor     edx, edx; Val
0x18012fa56  lea     r8d, [rdx+62h]; Size
0x18012fa5a  lea     rcx, [rbp+240h+var_29E]; void *
0x18012fa5e  call    memset
0x18012fa63  mov     [rbp+240h+cchValueName], 32h ; '2'
0x18012fa6a  mov     [rsp+340h+Type], r14d
0x18012fa6f  mov     dword ptr [rsp+340h+Data], r14d
0x18012fa74  mov     [rsp+340h+cbData], 4
0x18012fa7c  xorps   xmm0, xmm0
0x18012fa7f  movups  xmmword ptr [rbp+240h+pclsid.Data1], xmm0
0x18012fa83  lea     rax, [rsp+340h+cbData]
0x18012fa88  mov     [rsp+340h+lpcValues], rax; lpcbData
0x18012fa8d  lea     rax, [rsp+340h+Data]
0x18012fa92  mov     [rsp+340h+lpcbMaxClassLen], rax; lpData
0x18012fa97  lea     rax, [rsp+340h+Type]
0x18012fa9c  mov     [rsp+340h+lpcbMaxSubKeyLen], rax; lpType
0x18012faa1  mov     [rsp+340h+phkResult], r14; lpReserved
0x18012faa6  lea     r9, [rbp+240h+cchValueName]; lpcchValueName
0x18012faaa  lea     r8, [rbp+240h+ValueName]; lpValueName
0x18012faae  mov     edx, edi; dwIndex
0x18012fab0  mov     rcx, [rsp+340h+var_2D0]; hKey
0x18012fab5  call    cs:__imp_RegEnumValueW
0x18012fabb  inc     edi
0x18012fabd  test    eax, eax
0x18012fabf  jz      short loc_18012FB1D
0x18012fac1  cmp     eax, 0EAh
0x18012fac6  jz      short loc_18012FA4F
0x18012fac8  mov     rcx, [rsp+340h+var_2D0]; hKey
0x18012facd  test    rcx, rcx
0x18012fad0  jz      short loc_18012FAD8
0x18012fad2  call    cs:__imp_RegCloseKey
0x18012fad8  inc     ebx
0x18012fada  cmp     ebx, [rsp+340h+cSubKeys]
0x18012fade  jb      loc_18012F9DC
0x18012fae4  mov     rcx, [rsp+340h+hKey]; hKey
0x18012fae9  test    rcx, rcx
0x18012faec  jz      short loc_18012FAF4
0x18012faee  call    cs:__imp_RegCloseKey
0x18012faf4  xor     eax, eax
0x18012faf6  mov     rcx, [rbp+240h+var_20]
0x18012fafd  xor     rcx, rsp; StackCookie
0x18012fb00  call    __security_check_cookie
0x18012fb05  lea     r11, [rsp+340h+var_10]
0x18012fb0d  mov     rbx, [r11+28h]
0x18012fb11  mov     rsi, [r11+30h]
0x18012fb15  mov     rsp, r11
0x18012fb18  pop     r14
0x18012fb1a  pop     rdi
0x18012fb1b  pop     rbp
0x18012fb1c  retn
0x18012fb1d  cmp     [rsp+340h+Type], 4
0x18012fb22  jnz     loc_18012FA4F
0x18012fb28  cmp     [rsp+340h+cbData], 4
0x18012fb2d  jnz     loc_18012FA4F
0x18012fb33  cmp     dword ptr [rsp+340h+Data], 1
0x18012fb38  jnz     loc_18012FA4F
0x18012fb3e  lea     rdx, [rbp+240h+pclsid]; pclsid
0x18012fb42  lea     rcx, [rbp+240h+ValueName]; lpsz
0x18012fb46  call    cs:__imp_CLSIDFromString
0x18012fb4c  test    eax, eax
0x18012fb4e  js      loc_18012FA4F
0x18012fb54  mov     r8d, 1
0x18012fb5a  lea     rdx, [rbp+240h+pclsid]
0x18012fb5e  mov     rcx, rsi
0x18012fb61  call    ?Add@?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@QEAAJAEBU_GUID@@K@Z; CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Add(_GUID const &,ulong)
0x18012fb66  jmp     loc_18012FA4F
```
